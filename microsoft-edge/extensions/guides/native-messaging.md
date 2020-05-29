---
description: 了解如何使用本机消息功能让你的分机与配套的 UWP 应用进行通信。
title: 扩展-本机消息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员、本机、消息传递、uwp
ms.openlocfilehash: 83f80e112180317c38763225c1cdd015da4238b0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563276"
---
# Microsoft Edge 中的本机消息  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## 本机消息传递体系结构概述

通过 Windows 10 创意者更新，Microsoft Edge 扩展可以使用本机消息与配套的通用 Windows 平台（UWP）应用进行通信。  在高级别上，Microsoft Edge 扩展将相同的 Api 用于本机消息作为 Chrome 和 Firefox 扩展。 但是，将需要使用通用 Windows 平台来实现本机消息主机。

> [!NOTE]
> 下面概述的方法（通过 AppService 连接到 UWP 应用）是启用 Microsoft Edge 扩展和本机组件之间的通信的唯一受支持的机制。 有关如何启用与旧版 Win32 组件的通信的详细信息，请参阅本指南的 "[添加桌面桥组件](#adding-a-desktop-bridge-component)" 部分。 

 Microsoft Edge 的本机消息传递体系结构将现有 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API 用作基础进程间通信（IPC）基础结构。 UWP 应用使用 `AppService` API 与其他 API 进行通信。 因此，Microsoft Edge 扩展现在可以与 UWP 应用进行通信。

![本机消息传递体系结构](./../media/native-messaging-architecture.png)


### 何时以及何时不使用本机消息

本机消息向扩展添加一个全新的图层。 通过为你的扩展实现 UWP 配套应用，你可以使用以下可能功能：

* 将数据（如凭据）与配套的 UWP 应用同步。
* 实现更强的加密/解密算法在 web Api 中不可用。
* 访问无法通过 web Api 访问的资源，例如硬件或 USB 设备

由于安全或策略限制，某些情况下不能使用本机消息：

* 修改 Microsoft Edge 或 Windows 中的用户设置，例如更改默认浏览器或搜索提供程序。
* 与应用和扩展的 Microsoft 应用商店策略冲突的操作。
* 通过本机消息主机将数据传输到远程终结点。
* 允许其他应用下载更改扩展行为的内容。

## 演示

若要了解同时具有配套的 UWP 应用和桌面桥的 Microsoft Edge 本机消息扩展的外观，请参阅 GitHub 上的[SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput)和[DigitalSigning （c + +）](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning)示例。

### 工作原理

示例的 Microsoft Edge 扩展组件使用其内容脚本来检测用户何时键入应加密的信息。 该扩展通过本机消息将其与桌面桥组件进行通信。 当用户准备提交数据时，扩展会将加密的值返回到网站。

> [!NOTE]
> 此示例仅适用于使用自定义事件与扩展名的内容脚本进行通信的网页。 示例文件夹包含一个[.html 文件](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html)，用于测试扩展名。

在此示例中，UWP 应用用于将来自桌面桥的响应传递到 Microsoft Edge，然后通过回调将其发送到 Microsoft Edge 扩展。 虽然此示例在主应用中运行本机消息主机，但它也可以作为后台任务运行。 在两者之间切换需要编辑扩展的后台脚本，将字符串中的字符串更改 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` 为 `"NativeMessagingHostOutOfProcess"` 。

## Chrome vs Microsoft Edge 实现

虽然 Chrome 会使用消息传递 Api 的路由以使其扩展能够与应用通信，但 Microsoft Edge 利用了 API，该 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) api 现在支持 Microsoft Edge 扩展和 UWP 应用进行通信。

本节详细介绍了 Chrome 和 Microsoft Edge 如何处理本机消息实现之间的差异。

### 注册和主机清单
为了让你的扩展能够将你的应用识别为本机消息主机，将需要注册该应用。


对于[Chrome 本机消息](https://developer.chrome.com/extensions/nativeMessaging)主机注册，你的应用需要在定义本机消息主机配置的 Windows 文件系统中的任意位置安装清单文件。

下面的 JSON 是如何设置配置文件的示例：

```json
{
   "name": "com.my_company.my_application",
   "description": "My Application",
   "path": "C:\\ProgramFiles\\MyApplication\\chrome_native_messaging_host.exe",
   "type": "stdio",
   "allowed_origins": [
      "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
    ]
}
```

若要安装此文件，应用需要：

1. 在定义主机配置的注册表中的预定义位置注册清单文件：
   - `HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

     或者
   - `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

2. 将该注册表项的默认值设置为清单文件的完整路径，例如  `[HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"`




对于 Microsoft Edge，为了注册 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) （本机消息主机），你需要将 UWP 配套应用包含在与你的扩展名相同的程序包中，并在你的项目文件中指定[AppService 扩展名](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) `Package.appxmanifest` 。 `EntryPoint`和 `Name` 属性可以配置：

```xml
...
<Applications>    
    <Application Id="App"         
        <Extensions>        
            <uap:Extension Category="windows.appService" EntryPoint="MyAppService.Inventory">          
            <uap:AppService Name="com.microsoft.inventory"/>        
            </uap:Extension>      
        </Extensions>      
        ...    
    </Application>
</Applications>
```


你还需要设置允许哪些扩展名连接到该服务。 由于 Microsoft Edge `"allowed_origins"` 在其 package.appxmanifest 中没有等效的清单属性，因此需要在运行时由 UWP 应用确定并强制执行此操作。 由于 Microsoft Edge 将代表扩展建立连接，因此应用可以查找呼叫者的程序包系列名称，以确定它们是否通过 Microsoft Edge 进行连接以控制或验证呼叫者。 例如 

```csharp
protected async override void
OnBackgroundActivated(BackgroundActivatedEventArgs args)
{
    IBackgroundTaskInstance taskInstance = args.TaskInstance;
    if (taskInstance.TriggerDetails is AppServiceTriggerDetails)
    {
        AppServiceTriggerDetails appService = taskInstance.TriggerDetails as AppServiceTriggerDetails;
        if (appService.CallerPackageFamilyName == EdgePFN)
        {
            // Establish the connection
        }
        else
        {
            // Reject the connection
        }
    }
}
```



### 消息发送

对于一个应用和一个用于相互通信的扩展，需要向其发送消息和发送消息。

Chrome 扩展使用 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API 使用非持久性信道将消息发送到本机主机来启动消息。 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```

第一个参数是本机主机的名称，该名称是在清单的注册表中查找的 "Chrome"。 清单指定了 Chrome 将在沙盒中启动的 .exe，并使用 std i/o 发送消息。 扩展还可以使用 API 建立永久通道 `runtime.connectNative` ，该通道采用本机主机的名称作为唯一参数。 

Microsoft Edge 使用与 Chrome 的本机消息处理 API 相同的构造，以允许 Microsoft Edge 扩展指定要连接的应用服务。 中的第一个参数 `runtime.sendNativeMessage` 指定应用服务名称。 在 "[注册和主机清单](#registration-and-host-manifest)" 部分中，这是 `"com.microsoft.inventory"` 。 Microsoft Edge 扩展平台将本机消息主机限制为一个 UWP 应用，该应用打包在与扩展相同的 AppX 中。 这将减少与尝试通过篡改清单条目连接 Microsoft Edge 与其他程序包系列名称关联的恶意攻击的任何安全风险。 

这意味着，除了在 API 中指定的名称之外，Microsoft Edge 还将使用与扩展名相同的程序包系列名称 `AppService` 来唯一标识应用服务的提供程序。  

> [!NOTE]
> 这将不会由[Microsoft Edge 扩展工具包](./porting-chrome-extensions.md)轻松转换。 任何指定权限的扩展 `"nativeMessaging"` 将被标记为需要此组件的手动转换。





### 通信协议

用于本机消息的通信协议确定发送邮件之前如何设置其格式。

Chrome 在单独的进程中启动每个本机消息传递主机，并使用标准输入和标准输出与它进行通信。 相同格式用于以两种方向发送邮件：每条消息都使用 JSON 进行序列化，UTF-8 编码，前面是32位消息长度（以本机字节顺序为单位）。


对于 Microsoft Edge，实现应用服务的后台任务/主要应用将由平台启动。 启动时，将调用后台任务的 `Run` 方法：  

```csharp
public void Run(IBackgroundTaskInstance taskInstance)    
{
    this.backgroundTaskDeferral = taskInstance.GetDeferral();
    // Get a deferral so that the service isn't terminated.
    taskInstance.Canceled += OnTaskCanceled;
    // Associate a cancellation handler with the background task.
    // Retrieve the app service connection and set up a listener for incoming app service requests.
    var details = taskInstance.TriggerDetails as AppServiceTriggerDetails;
    appServiceconnection = details.AppServiceConnection;
    appServiceconnection.RequestReceived += OnRequestReceived;
}
```

当你的扩展向 UWP 应用发送消息时， [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) 将引发此事件。 然后，此 JSON 格式消息将 stringified 到对象的第一个 KeyValue 对 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 。 :

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```

如果你的 UWP 应用将答复发送回你的扩展，则会将 a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) 添加到该 `ValueSet` 对象。 该 `Key` 属性将被 Microsoft Edge 忽略，但该 `Value` 属性将包含有效的 JSON 字符串。

### 叫

对于回调，Chrome 用法 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 允许回调函数处理发送消息的任何异步响应。

Microsoft Edge 使用 [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) 对象的 [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) 方法让应用将 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 对象发送回扩展。


### 邮件大小限制
在扩展和应用之间来回发送的邮件对 Chrome 和 Microsoft Edge 的邮件大小限制不同。

Chrome 具有下列邮件大小限制：
- 来自本机消息主机的单个邮件限制： 1 MB
- 发送到本机消息主机的单个消息限制： 4 GB

对于 Microsoft Edge，虽然 `AppService` 没有对邮件大小（取决于内存）的限制，但 Microsoft edge 通过强制执行下列邮件大小限制来保护自己免受对本机应用的行为：
- 从 UWP 应用到扩展的单个邮件限制： 1 MB
- 从扩展到 UWP 应用的单个邮件限制： 100 MB



### 本机消息连接

本机消息有两种类型的连接;永久性和非持久。
**永久**连接是一直保持运行的连接，直到该端口被销毁。 **非持久**连接是一次打开一条消息并在传递后关闭的连接。

#### 永久性

对于 Chrome，通过使用创建消息传递端口来建立持久连接 [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。 端口创建后，Chrome 将启动一个本机消息传递主机进程，该进程将一直保持运行，直到它销毁的端口。

对于 Microsoft Edge，一旦使用消息传送端口创建 `runtime.connectNative` ，Microsoft Edge 将启动 [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) 并一直运行，直到该端口损坏。 以下代码段显示了如何从 UWP 应用内建立持久连接。 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```

#### 非持久

当使用 Chrome 发送邮件时 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) ，如果不创建邮件端口，Chrome 将为每条消息启动新的本机消息传递主机进程。 由主机进程生成的第一条消息将作为对原始请求的响应处理，并将忽略所有其他消息。

在收到每封邮件的响应后，Microsoft Edge 将终止连接。 以下代码片段显示与之建立的非持久连接， `AppServiceConnection` 该连接将在收到并存储为后在 UWP 应用内终止 [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) 。

```csharp
using (var connection = new AppServiceConnection())
{    
    //Set up a new app service connection
    connection.AppServiceName = "com.microsoft.randomnumbergenerator";
    connection.PackageFamilyName = "Microsoft.SDKSamples.AppServicesProvider.CS_8wekyb3d8bbwe";
    AppServiceConnectionStatus status = await connection.OpenAsync();
    AppServiceResponse response = await connection.SendMessageAsync(inputs);
}
```

### 权限

为了为 Chrome 和 Microsoft Edge 启用本机消息传递，你需要 `"nativeMessaging"` 在文件中声明权限 `manifest.json` 。


## 应用服务
本节详细介绍了应用服务对 Microsoft Edge 本机消息性能和内存的影响。

### 性能

应用服务由调用它们的前台应用 "赞助"，用于本机消息传递目的是 Microsoft Edge。 这意味着只要运行 Microsoft Edge，应用服务就可以运行。

对延迟而言，应用服务使用 "命名管道"，在初始连接后，允许两个应用直接通信。 这种通信方式产生较低的延迟。 在启动承载应用服务（~ 80ms 以启动某些设备上的后台任务）的进程后，具有较慢 Cpu 的设备将遇到一些初始延迟。 启动后，CPU 设备速度较慢的性能应该很好。 


### 内存
分配给应用服务的内存已从分配给 Microsoft Edge 的配额中取出。 这意味着，如果 Microsoft Edge 启动过多的应用服务，可能会耗尽内存。 在应用服务上强制使用常规后台任务内存上限。 例如，在512MB 设备上，应用服务后台任务不能大于16MB。 当设备向上扩展时，此号码将上升。


## 使用本机消息创建扩展

为了测试本机消息，你的扩展需要一个程序包系列名称。 Microsoft Edge 使用此内容确定本机消息主机标识，这意味着你的扩展应打包。 


若要在 Visual Studio 中创建本机消息的扩展，请执行以下操作：

1. 在 Visual Studio 中创建 UWP 项目。
2. [添加 `AppService` 到 UWP 应用](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。
   - 你可以选择[配置 `AppService` 为在主应用中托管，](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process)而不是在此位置作为后台任务托管。
3. 构建和测试您的 UWP 项目。
   - 你可以选择添加一个[桌面桥组件](#adding-a-desktop-bridge-component)。
4. 创建使用本机消息传递与 UWP 配套应用通信的 Microsoft Edge 扩展。 扩展文件可以添加到 `Extension` UWP 项目中指定的文件夹中。 此文件夹下的所有文件（包括子文件夹）都需要配置其属性，以便 `Build Action=Content` 和 `Copy to Output Directory=Copy Always` 。 请确保 `manifest.json` 也配置了这些属性。
5. `package.manifest.xml`通过添加以下内容，在项目中修改文件以包括扩展元数据并将其转换为无头应用 `AppListEntry="none"` ：

    ```xml
    <Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10" 
    xmlns:rescap="http://schemas.microsoft.com/appx/manifest/foundation/windows10/restrictedcapabilities" 
    xmlns:mp="http://schemas.microsoft.com/appx/2014/phone/manifest" 
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10" 
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap uap3 mp rescap build" 
    xmlns:build="http://schemas.microsoft.com/developer/appx/2015/build">

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.15063.0" MaxVersionTested="10.0.15063.0" />
    </Dependencies>

       <Application Id="App" Executable="$targetnametoken$.exe" EntryPoint="NativeMessagingHostInProcess.App">
          <uap:VisualElements AppListEntry="none"
            DisplayName="SecureInput"
            Square150x150Logo="Assets\Square150x150Logo.png"
            Square44x44Logo="Assets\Square44x44Logo.png"
            Description="NativeMessagingHostInProcess"
            BackgroundColor="transparent">
          </uap:VisualElements>
          <Extensions>
            <uap3:Extension Category="windows.appExtension">
                <uap3:AppExtension
                    Name="com.microsoft.edge.extension"
                    Id="EdgeExtension"
                    PublicFolder="Extension"
                    DisplayName="ms-resource:DisplayName">
                </uap3:AppExtension>
            </uap3:Extension>
          </Extensions>
    </Application>
    ```

6. `AppService`在本机消息 api 中使用为 UWP 配置的名称。
7. 生成和[部署](#deploying)UWP 项目（带有可选的桌面桥组件）。
8. 在准备好提交应用商店时[打包](#packaging)您的本机消息扩展

> [!NOTE]
> 有关完整本机消息扩展的示例，请参考 "[演示](#demos)" 部分。


## 添加桌面桥组件 
如果要将桌面桥组件添加到你的程序包，你需要在 Visual Studio 中创建和生成 Win32 项目。 有关如何将 win32 应用转换为 UWP 的信息，请参阅[通过桌面桥将应用移植到 Windows 10](/windows/uwp/porting/desktop-to-uwp-root)。 在 Visual Studio 中构建后，你可以通过执行以下步骤将 Win32 可执行文件添加到程序包：

1. 将 Win32 项目添加到与 UWP 项目相同的解决方案中。 

2. 将 Win32 项目设置为 UWP 项目的依赖项目：

    ![设置项目相关性](./../media/project-dependencies.PNG)

3. `Win32`在 UWP 项目中创建一个文件夹。 将项目所需的二进制文件复制 `Win32` 到此文件夹。 配置所有二进制文件的属性，例如 `Build Action=Content` 和 `Copy to Output Directory=Copy Always` 。

    ![包含 win32 和 UWP 应用文件的文件夹](./../media/desktop-bridge.png)

4. 修改 UWP 项目文件以使用 PostBuild 事件命令将项目的所有必需的二进制文件复制 `Win32` 到此文件夹中。 这可确保每次重新生成解决方案时都将更新的二进制文件复制到文件夹中。

    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```


5. `package.manifest.xml`通过将元素添加 `<desktop:Extension>` 到元素进行修改 `<Extensions>` ：

    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```

## 部署
按照上述说明配置 UWP 项目（和可选 Win32 项目）后，即可使用 Visual Studio 部署解决方案。

![生成进程内项目](../media/native-message-uwp-debug.PNG)

正确部署解决方案后，你应该会在 Microsoft Edge 中看到你的扩展。

![在 Microsoft Edge 中显示的扩展](../media/secureextension.png)

## 打包

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。 [通过你](https://aka.ms/extension-request)的请求成为 Microsoft Store 的一部分，我们将考虑你的未来更新。


你可以使用内置 Visual Studio 功能生成用于提交到 Windows 开发人员中心的应用商店包：


![创建存储包](../media/create-store-package.PNG)

## 调试
根据要测试的组件，调试说明会有所不同：

### 调试扩展
部署解决方案后，将在 Microsoft Edge 中安装扩展。 有关如何调试扩展的信息，请查看[调试](./debugging-extensions.md)指南。


### 调试 UWP 应用
当扩展尝试使用[本机消息 api](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)连接时，UWP 应用将启动。 只有在进程启动后才需要调试 UWP 应用。 这可以通过项目的属性页面进行配置：

1.  在 Visual Studio 中，右键单击你的 UWP 应用项目
2.  选择属性
3.  选中 "不启动，但在开始时调试我的代码"

    ![选择 "不启动" 框](../media/native-message-do-not-launch.png)

在 Visual Studio 中，你现在可以在要调试的代码中设置断点，然后按 F5 启动调试器。 与扩展连接以连接到 UWP 应用后，Visual Studio 将自动附加到该进程。


### 调试桌面桥
尽管有多种方法可[用于调试桌面桥](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug)（已转换的 Win32 应用），但唯一适用于这种情况的方法是 PLMDebug 选项。 你还可以将调试代码添加到启动函数以在特定时间执行等待，从而允许你将 Visual Studio 附加到进程。
