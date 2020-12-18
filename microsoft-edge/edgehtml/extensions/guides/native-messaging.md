---
description: 了解如何使用本机消息传递让扩展与配套 UWP 应用进行通信。
title: 扩展 - 本机消息传递
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 本机， 消息传递， uwp
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 983ae11822edabc0f27bd6c02f9397104b082ad6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232622"
---
# Microsoft Edge 中的本机消息传递  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## 本机消息传递体系结构概述

借助 Windows 10 创意者更新，Microsoft Edge 扩展可以使用本机消息传递与配套通用 Windows 平台 (UWP) 应用通信。  在高级别上，Microsoft Edge 扩展使用与 Chrome 和 Firefox 扩展相同的 API 进行本机消息传递。 但是，本机消息传递主机将需要使用通用 Windows 平台实现。

> [!NOTE]
> 通过 AppService (连接到 UWP 应用时) 介绍的方法是唯一支持在 Microsoft Edge 扩展和本机组件之间启用通信的机制。 请参阅本指南的"添加 [桌面桥](#adding-a-desktop-bridge-component) 组件"部分，详细了解如何启用与旧版 Win32 组件的通信。 

 Microsoft Edge 的本机消息传递体系结构利用现有 API 作为 IPC 基础结构中 ([`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) 进程) 通信。 UWP 应用使用 `AppService` API 相互通信。 因此，Microsoft Edge 扩展现在可以与 UWP 应用通信。

![本机消息传递体系结构](./../media/native-messaging-architecture.png)

### 何时以及何时不使用本机消息传递

本机消息将一个全新层添加到扩展中。 通过为扩展实现 UWP 配套应用，你可以使用以下可能性：

* 将 (（例如，凭据) UWP 应用同步。
* 实现 Web API 中不可用的更强的加密/解密算法。
* 访问无法通过 Web API 访问的资源，例如硬件或 USB 设备

在少数情况下，由于安全或策略限制，本机邮件无法使用：

* 修改 Microsoft Edge 或 Windows 中的用户设置，例如更改默认浏览器或搜索提供程序。
* 违反适用于应用和扩展的 Microsoft Store 策略的操作。
* 通过本机邮件主机将数据传输到远程终结点。
* 允许其他应用下载更改扩展行为的内容。

## 演示

若要了解同时具有配套 UWP 应用和桌面桥的 Microsoft Edge 本机消息传递扩展的外观，请查看 GitHub 上的 [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) 和 [DigitalSigning (C++ ](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning)) 示例。

### 工作原理

此示例的 Microsoft Edge 扩展组件使用其内容脚本检测用户何时键入应加密的信息。 扩展通过本机消息将此功能传达给桌面桥组件。 当用户准备好提交数据时，扩展将返回一个加密值返回到网站。

> [!NOTE]
> 此示例仅适用于使用自定义事件与扩展的内容脚本通信的网页。 示例文件夹包含 [一个 .html 文件](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) ，用于测试扩展名。

本示例中，UWP 应用用于将响应从桌面桥传递到 Microsoft Edge，然后通过回调将响应发送到 Microsoft Edge 扩展。 虽然此示例使本机消息传递主机在主应用中运行，但它也可以作为后台任务运行。 在两者之间切换需要编辑扩展的后台脚本，将字符串内部更改 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` 为 `"NativeMessagingHostOutOfProcess"` 。

## Chrome 与 Microsoft Edge 实现

尽管 Chrome 使用消息传递 API 作为扩展的路由来与应用通信，但 Microsoft Edge 利用 API 现在使 Microsoft Edge 扩展和 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) UWP 应用能够进行通信。

本部分详细介绍 Chrome 和 Microsoft Edge 如何处理本机消息传递实现之间的差异。

### 注册和主机清单
为了让应用被扩展识别为本机消息传递主机，需要注册它。

对于 [Chrome 本机消息传递主机](https://developer.chrome.com/extensions/nativeMessaging) 注册，你的应用需要在定义本机邮件主机配置的 Windows 文件系统中的任何位置安装清单文件。

以下 JSON 是设置配置文件的示例：

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

1.  在定义主机配置的注册表中的预定义位置注册清单文件：
    -   ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
        或者
        
    -   ```text
        HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
2.  将该键的默认值设置为清单文件的完整路径，例如 
    
    ```text
    [HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
对于 Microsoft Edge，若要注册 (本机消息传递主机) 你需要将 UWP 配套应用作为扩展包括在相同的程序包中，并指定项目文件中 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) [AppService](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)扩展。 `Package.appxmanifest` And `EntryPoint` `Name` 属性可以配置：

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


你还需要设置允许 (服务) 的扩展名。 由于 Microsoft Edge 的 AppxManifest 中没有等效的清单属性，因此需要在运行时由 UWP 应用确定和 `"allowed_origins"` 强制执行。 由于 Microsoft Edge 将代表扩展建立连接，因此应用可以查找呼叫者的程序包系列名称，以确定他们是否正在由 Microsoft Edge 连接以控制或验证呼叫者。 例如 

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

### 邮件发送

若要使应用和扩展相互通信，需要向它们发送和发送消息。

Chrome 扩展使用 API 启动消息，以使用非永久性通道将消息传递至本机 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 主机。 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```  

第一个参数是本机主机的名称，Chrome 在注册表中查找清单。 清单指定 Chrome 将在沙盒中启动的 .exe，邮件使用 std i/o 发送。 扩展还可使用 API 建立永久性通道，该 API 将本机主机的名称作为 `runtime.connectNative` 唯一参数。 

Microsoft Edge 使用与 Chrome 的本机消息传递 API 相同的构造，以允许 Microsoft Edge 扩展指定要连接到的应用服务。 第一个参数 `runtime.sendNativeMessage` 指定应用服务名称。 在" [注册和主机清单"](#registration-and-host-manifest) 部分，这是 `"com.microsoft.inventory"` 。 Microsoft Edge 扩展平台将本机消息传递主机限制为打包在扩展相同的 AppX 中的 UWP 应用。 这可缓解与恶意攻击（尝试通过篡改清单条目将 Microsoft Edge 连接到另一个程序包系列名称）关联的任何安全风险。 

这意味着，除了 API 中指定的名称之外，Microsoft Edge 还将使用与扩展相同的程序包系列名称来唯一地标识 `AppService` 应用服务的提供程序。  

> [!NOTE]
> Microsoft Edge Extension [Toolkit。](./porting-chrome-extensions.md) 任何指定权限的 `"nativeMessaging"` 扩展将被标记为需要对此组件进行手动转换。

### 通信协议

本机消息的通信协议确定邮件在发送前的格式设置。

Chrome 在单独的进程中启动每个本机消息传递主机，然后使用标准输入和标准输出与它进行通信。 相同的格式用于向两个方向发送邮件：每个邮件都使用 JSON、UTF-8 编码进行序列化，并且以本机字节顺序以 32 位邮件长度为前。

对于 Microsoft Edge，平台将启动实现应用服务的后台任务/主应用。 启动时，将调用 `Run` 后台任务的方法：  

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

当扩展向 UWP 应用发送消息时， [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) 将引发该事件。 然后，此 JSON 格式的邮件将字符串化为对象的第一个 KeyValue [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 对。 :

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```  

当 UWP 应用向扩展发送回响应时，将向 [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) 对象中添加 `ValueSet` 一个。 Microsoft `Key` Edge 将忽略该属性，但 `Value` 该属性将包含有效的 JSON 字符串。

### 回调

对于回调，Chrome [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 使用允许回调函数处理发送消息的任何异步响应。

Microsoft Edge [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) 使用对象的方法 [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) 让应用将对象 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 发送回扩展。


### 邮件大小限制
在扩展与应用之间来回发送的邮件对于 Chrome 和 Microsoft Edge 有不同的邮件大小限制。

Chrome 具有以下邮件大小限制：
-   来自本机邮件主机的单个邮件限制：1 MB
-   发送到本机邮件主机的单个邮件限制：4 GB
    
对于 Microsoft Edge，虽然对邮件大小没有 (取决于内存) ，但 Microsoft Edge 通过限制以下邮件大小限制来防范本机应用行为 `AppService` 不当：
-   从 UWP 应用到扩展的单个邮件限制：1 MB
-   从扩展到 UWP 应用的单个邮件限制：100 MB
    
### 本机消息传递连接

本机消息传递有两种类型的连接;持久和非永久。
永久性 **连接** 是一个在端口被销毁之前一直运行的连接。 非 **永久性** 连接是一个连接，一次打开一封邮件，在传递后关闭。

#### 永久性

对于 Chrome，通过使用 创建消息端口来建立永久性连接 [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。 创建端口后，Chrome 将启动一个本机消息传递主机进程，该进程将一直运行，直到该端口被销毁。

对于 Microsoft Edge，一旦使用消息传递端口创建，Microsoft Edge 将启动该端口并保持其运行， `runtime.connectNative` [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) 直到该端口被销毁。 以下代码段演示如何从 UWP 应用内建立永久性连接。 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```  

#### 非永久性

在 Chrome 中发送邮件时，无需创建邮件端口，Chrome 会针对每封邮件启动一 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 个新的本机邮件主机进程。 主机进程生成的第一条消息将作为对原始请求的响应进行处理，在忽略后处理所有其他消息。

Microsoft Edge 将在收到每条消息的响应后终止连接。 以下代码段显示了一个非永久性连接，在接收请求并存储为请求后，该连接将在 `AppServiceConnection` UWP 应用中终止 [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) 。

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

为了允许本机消息传递与扩展一同使用，对于 Chrome 和 Microsoft Edge，你需要在文件中 `"nativeMessaging"` 声明 `manifest.json` 权限。

## 应用服务
本部分详细介绍应用服务对 Microsoft Edge 本机邮件性能和内存的影响。

### 性能

应用服务由前台应用"赞助"，它调用它们，用于本机消息传递目的为 Microsoft Edge。 这意味着只要 Microsoft Edge 正在运行，应用服务就可以运行。

对于延迟，应用服务使用命名管道，在初始连接后，允许两个应用直接通信。 这种通信方法会产生低延迟。 启动托管应用服务 (约 80 毫秒以启动某些设备上后台任务的进程后，CPU 较慢的设备将遇到一些初始) 。 启动后，较慢的 CPU 设备的性能应该良好。 

### 内存
分配给应用服务的内存会从分配给 Microsoft Edge 的配额中取消。 这意味着，如果 Microsoft Edge 启动的应用服务过多，它们可能会用完内存。 常见的后台任务内存上限在应用服务上强制执行。 例如，在 512MB 设备上，应用服务后台任务不能大于 16MB。 当设备向上扩展时，此数字会上升。

## 使用本机消息传递创建扩展

为了测试本机消息传递，扩展需要程序包系列名称。 Microsoft Edge 使用它来确定本机邮件主机标识，这意味着应打包扩展。 

若要在应用程序内使用本机消息传递创建Visual Studio：

1.  在项目中创建 UWP Visual Studio。
2.  [添加到 `AppService` 你的 UWP 应用](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。
    -   此时， [可以选择 `AppService` 配置为](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) 托管在主应用中，而不是后台任务中。
3.  生成和测试 UWP 项目。
    -   可以选择添加桌面 [桥组件](#adding-a-desktop-bridge-component)。
4.  创建使用本机消息传递与 UWP 配套应用进行通信的 Microsoft Edge 扩展。 扩展文件可以添加到 `Extension` UWP 项目中命名的文件夹中。 此文件夹下的所有文件（包括子文件夹）都需要配置其属性，这样 `Build Action=Content` `Copy to Output Directory=Copy Always` 和 。 请确保 `manifest.json` 还配置了这些属性。
5.  修改 `package.manifest.xml` 项目中的文件以包含扩展元数据，并添加以下代码将其转换为无头应用 `AppListEntry="none"` ：
    
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
    
6.  在本机消息传递 API 中使用 `AppService` 为 UWP 配置的名称。
7.  使用可选的 [桌面桥](#deploying) 组件 (生成和部署 UWP) 。
8.  [准备好](#packaging) 提交应用商店后打包本机消息传递扩展
    
> [!NOTE]
> 有关 [完整本机消息传递](#demos) 扩展的示例，请引用"演示"部分。

## 添加桌面桥组件 
如果要将桌面桥组件添加到程序包，则需要在 Visual Studio 中创建和生成 Win32 项目。 若要了解如何将 win32 应用转换为 UWP，请参阅通过桌面桥将应用移植到[Windows 10。](/windows/uwp/porting/desktop-to-uwp-root) 内置Visual Studio后，可以通过执行以下步骤将 Win32 可执行文件添加到程序包中：

1.  将 Win32 项目添加到与 UWP 项目相同的解决方案。 
2.  将 Win32 项目设置为 UWP 项目的从属项目：
    
    ![设置项目依赖项](./../media/project-dependencies.PNG)
    
3.  在 `Win32` UWP 项目中创建文件夹。 将项目的必要二进制文件 `Win32` 复制到此文件夹。 配置所有二进制文件的属性， `Build Action=Content` 例如. `Copy to Output Directory=Copy Always`
    
    ![包含 win32 和 UWP 应用文件的文件夹](./../media/desktop-bridge.png)
    
4.  修改 UWP 项目文件，以使用 PostBuild 事件命令将项目所有必要的二进制文件 `Win32` 复制到此文件夹中。 这可确保每次重新生成解决方案时将更新的二进制文件复制到文件夹。
    
    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```
    
5.  通过 `package.manifest.xml` 向元素 `<desktop:Extension>` 添加元素进行修改 `<Extensions>` ：
    
    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```
    
## 部署
配置 UWP 项目包和 (Win32 项目) 如上所述，即可使用 Visual Studio 部署解决方案。

![生成 inprocess 项目](../media/native-message-uwp-debug.PNG)

正确部署解决方案后，你应该会看到 Microsoft Edge 中的扩展。

![在 Microsoft Edge 中显示扩展](../media/secureextension.png)

## 打包

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。 [如果你的请求是](https://aka.ms/extension-request) Microsoft Store 的一部分，请联系我们，我们将考虑你进行将来的更新。

你可以生成应用商店程序包，以使用内置应用功能提交到 Windows 开发人员Visual Studio功能：

![创建应用商店程序包](../media/create-store-package.PNG)

## 调试
调试说明因要测试的组件而异：

### 调试扩展
部署解决方案后，扩展将安装在 Microsoft Edge 中。 请查看 [调试指南](./debugging-extensions.md) ，了解有关如何调试扩展的信息。


### 调试 UWP 应用
当扩展尝试使用本机消息传递 API 连接到它时 [，UWP 应用将启动](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)。 只需在进程启动后调试 UWP 应用。 这可以通过项目的"属性"页进行配置：

1.  在Visual Studio中，右键单击 UWP 应用项目
2.  选择属性
3.  选中"不启动，但在启动时调试代码"
    
    ![选择"不启动"框](../media/native-message-do-not-launch.png)
    
In Visual Studio you can now set breakpoints in the code where you want to debug， then launch the debugger by pressing F5. 与扩展交互以连接到 UWP 应用后，Visual Studio将自动附加到进程。

### 调试桌面桥
尽管调试已转换的 Win32 [ (桌面](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) 桥) ，但唯一适用于此方案的方法还是 PLMDebug 选项。 还可以将调试代码添加到启动函数以执行特定时间等待，从而允许您将Visual Studio附加到进程。
