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
# <span data-ttu-id="fb403-104">Microsoft Edge 中的本机消息传递</span><span class="sxs-lookup"><span data-stu-id="fb403-104">Native messaging in Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="fb403-105">本机消息传递体系结构概述</span><span class="sxs-lookup"><span data-stu-id="fb403-105">Native messaging architecture overview</span></span>

<span data-ttu-id="fb403-106">借助 Windows 10 创意者更新，Microsoft Edge 扩展可以使用本机消息传递与配套通用 Windows 平台 (UWP) 应用通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform (UWP) app.</span></span>  <span data-ttu-id="fb403-107">在高级别上，Microsoft Edge 扩展使用与 Chrome 和 Firefox 扩展相同的 API 进行本机消息传递。</span><span class="sxs-lookup"><span data-stu-id="fb403-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span></span> <span data-ttu-id="fb403-108">但是，本机消息传递主机将需要使用通用 Windows 平台实现。</span><span class="sxs-lookup"><span data-stu-id="fb403-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span></span>

> [!NOTE]
> <span data-ttu-id="fb403-109">通过 AppService (连接到 UWP 应用时) 介绍的方法是唯一支持在 Microsoft Edge 扩展和本机组件之间启用通信的机制。</span><span class="sxs-lookup"><span data-stu-id="fb403-109">The method outlined below (connecting to a UWP app via AppService) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span></span> <span data-ttu-id="fb403-110">请参阅本指南的"添加 [桌面桥](#adding-a-desktop-bridge-component) 组件"部分，详细了解如何启用与旧版 Win32 组件的通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span></span> 

 <span data-ttu-id="fb403-111">Microsoft Edge 的本机消息传递体系结构利用现有 API 作为 IPC 基础结构中 ([`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) 进程) 通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-111">Microsoft Edge's native messaging architecture leverages the existing [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API as the underlying inter-process communication (IPC) infrastructure.</span></span> <span data-ttu-id="fb403-112">UWP 应用使用 `AppService` API 相互通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-112">UWP apps use the `AppService` API to communicate with one another.</span></span> <span data-ttu-id="fb403-113">因此，Microsoft Edge 扩展现在可以与 UWP 应用通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-113">Because of this, Microsoft Edge extensions can now communicate with UWP apps.</span></span>

![本机消息传递体系结构](./../media/native-messaging-architecture.png)

### <span data-ttu-id="fb403-115">何时以及何时不使用本机消息传递</span><span class="sxs-lookup"><span data-stu-id="fb403-115">When and when not to use native messaging</span></span>

<span data-ttu-id="fb403-116">本机消息将一个全新层添加到扩展中。</span><span class="sxs-lookup"><span data-stu-id="fb403-116">Native messaging adds a whole new layer to your extension.</span></span> <span data-ttu-id="fb403-117">通过为扩展实现 UWP 配套应用，你可以使用以下可能性：</span><span class="sxs-lookup"><span data-stu-id="fb403-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span></span>

* <span data-ttu-id="fb403-118">将 (（例如，凭据) UWP 应用同步。</span><span class="sxs-lookup"><span data-stu-id="fb403-118">Synchronize data (e.g. credentials) with a companion UWP app.</span></span>
* <span data-ttu-id="fb403-119">实现 Web API 中不可用的更强的加密/解密算法。</span><span class="sxs-lookup"><span data-stu-id="fb403-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span></span>
* <span data-ttu-id="fb403-120">访问无法通过 Web API 访问的资源，例如硬件或 USB 设备</span><span class="sxs-lookup"><span data-stu-id="fb403-120">Access resources that are not accessible through web APIs, e.g. hardware or USB devices</span></span>

<span data-ttu-id="fb403-121">在少数情况下，由于安全或策略限制，本机邮件无法使用：</span><span class="sxs-lookup"><span data-stu-id="fb403-121">There are a few instances where native messaging can't be used due to security or policy restrictions:</span></span>

* <span data-ttu-id="fb403-122">修改 Microsoft Edge 或 Windows 中的用户设置，例如更改默认浏览器或搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb403-122">Modifying user settings in either Microsoft Edge or Windows, e.g. changing the default browser or search provider.</span></span>
* <span data-ttu-id="fb403-123">违反适用于应用和扩展的 Microsoft Store 策略的操作。</span><span class="sxs-lookup"><span data-stu-id="fb403-123">Actions that violate Microsoft Store policies for both apps and extensions.</span></span>
* <span data-ttu-id="fb403-124">通过本机邮件主机将数据传输到远程终结点。</span><span class="sxs-lookup"><span data-stu-id="fb403-124">Transferring data to remote endpoint via native message host.</span></span>
* <span data-ttu-id="fb403-125">允许其他应用下载更改扩展行为的内容。</span><span class="sxs-lookup"><span data-stu-id="fb403-125">Allowing other apps to download content that changes extension behavior.</span></span>

## <span data-ttu-id="fb403-126">演示</span><span class="sxs-lookup"><span data-stu-id="fb403-126">Demos</span></span>

<span data-ttu-id="fb403-127">若要了解同时具有配套 UWP 应用和桌面桥的 Microsoft Edge 本机消息传递扩展的外观，请查看 GitHub 上的 [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) 和 [DigitalSigning (C++ ](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning)) 示例。</span><span class="sxs-lookup"><span data-stu-id="fb403-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span></span>

### <span data-ttu-id="fb403-128">工作原理</span><span class="sxs-lookup"><span data-stu-id="fb403-128">How it works</span></span>

<span data-ttu-id="fb403-129">此示例的 Microsoft Edge 扩展组件使用其内容脚本检测用户何时键入应加密的信息。</span><span class="sxs-lookup"><span data-stu-id="fb403-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span></span> <span data-ttu-id="fb403-130">扩展通过本机消息将此功能传达给桌面桥组件。</span><span class="sxs-lookup"><span data-stu-id="fb403-130">The extension communicates this to the Desktop Bridge component via native messaging.</span></span> <span data-ttu-id="fb403-131">当用户准备好提交数据时，扩展将返回一个加密值返回到网站。</span><span class="sxs-lookup"><span data-stu-id="fb403-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span></span>

> [!NOTE]
> <span data-ttu-id="fb403-132">此示例仅适用于使用自定义事件与扩展的内容脚本通信的网页。</span><span class="sxs-lookup"><span data-stu-id="fb403-132">This sample will only work on a webpage that uses custom events to communicate with the extension's content script.</span></span> <span data-ttu-id="fb403-133">示例文件夹包含 [一个 .html 文件](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) ，用于测试扩展名。</span><span class="sxs-lookup"><span data-stu-id="fb403-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span></span>

<span data-ttu-id="fb403-134">本示例中，UWP 应用用于将响应从桌面桥传递到 Microsoft Edge，然后通过回调将响应发送到 Microsoft Edge 扩展。</span><span class="sxs-lookup"><span data-stu-id="fb403-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span></span> <span data-ttu-id="fb403-135">虽然此示例使本机消息传递主机在主应用中运行，但它也可以作为后台任务运行。</span><span class="sxs-lookup"><span data-stu-id="fb403-135">While this example has the native messaging host run in the main app, it's also able to run as a background task.</span></span> <span data-ttu-id="fb403-136">在两者之间切换需要编辑扩展的后台脚本，将字符串内部更改 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` 为 `"NativeMessagingHostOutOfProcess"` 。</span><span class="sxs-lookup"><span data-stu-id="fb403-136">Switching between the two requires editing the extension's background script, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span></span>

## <span data-ttu-id="fb403-137">Chrome 与 Microsoft Edge 实现</span><span class="sxs-lookup"><span data-stu-id="fb403-137">Chrome vs Microsoft Edge implementation</span></span>

<span data-ttu-id="fb403-138">尽管 Chrome 使用消息传递 API 作为扩展的路由来与应用通信，但 Microsoft Edge 利用 API 现在使 Microsoft Edge 扩展和 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) UWP 应用能够进行通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span></span>

<span data-ttu-id="fb403-139">本部分详细介绍 Chrome 和 Microsoft Edge 如何处理本机消息传递实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="fb403-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span></span>

### <span data-ttu-id="fb403-140">注册和主机清单</span><span class="sxs-lookup"><span data-stu-id="fb403-140">Registration and host manifest</span></span>
<span data-ttu-id="fb403-141">为了让应用被扩展识别为本机消息传递主机，需要注册它。</span><span class="sxs-lookup"><span data-stu-id="fb403-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span></span>

<span data-ttu-id="fb403-142">对于 [Chrome 本机消息传递主机](https://developer.chrome.com/extensions/nativeMessaging) 注册，你的应用需要在定义本机邮件主机配置的 Windows 文件系统中的任何位置安装清单文件。</span><span class="sxs-lookup"><span data-stu-id="fb403-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span></span>

<span data-ttu-id="fb403-143">以下 JSON 是设置配置文件的示例：</span><span class="sxs-lookup"><span data-stu-id="fb403-143">The following JSON is an example of how the config file can be set up:</span></span>

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

<span data-ttu-id="fb403-144">若要安装此文件，应用需要：</span><span class="sxs-lookup"><span data-stu-id="fb403-144">To install this file, the app would need to:</span></span>

1.  <span data-ttu-id="fb403-145">在定义主机配置的注册表中的预定义位置注册清单文件：</span><span class="sxs-lookup"><span data-stu-id="fb403-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span></span>
    -   ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
        <span data-ttu-id="fb403-146">或者</span><span class="sxs-lookup"><span data-stu-id="fb403-146">or</span></span>
        
    -   ```text
        HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
2.  <span data-ttu-id="fb403-147">将该键的默认值设置为清单文件的完整路径，例如</span><span class="sxs-lookup"><span data-stu-id="fb403-147">Set the default value of that key to the full path to the manifest file, e.g.</span></span> 
    
    ```text
    [HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
<span data-ttu-id="fb403-148">对于 Microsoft Edge，若要注册 (本机消息传递主机) 你需要将 UWP 配套应用作为扩展包括在相同的程序包中，并指定项目文件中 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) [AppService](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)扩展。 `Package.appxmanifest`</span><span class="sxs-lookup"><span data-stu-id="fb403-148">For Microsoft Edge, in order to register an [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx)(native messaging host) you'll need to include the UWP companion app in the same package as your extension and specify the [AppService extension](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in your project's `Package.appxmanifest` file.</span></span> <span data-ttu-id="fb403-149">And `EntryPoint` `Name` 属性可以配置：</span><span class="sxs-lookup"><span data-stu-id="fb403-149">The `EntryPoint` and `Name` attributes can be configured by you:</span></span>

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


<span data-ttu-id="fb403-150">你还需要设置允许 (服务) 的扩展名。</span><span class="sxs-lookup"><span data-stu-id="fb403-150">You'll also need to set which extension(s) are allowed to connect to the service.</span></span> <span data-ttu-id="fb403-151">由于 Microsoft Edge 的 AppxManifest 中没有等效的清单属性，因此需要在运行时由 UWP 应用确定和 `"allowed_origins"` 强制执行。</span><span class="sxs-lookup"><span data-stu-id="fb403-151">Because Microsoft Edge doesn't have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span></span> <span data-ttu-id="fb403-152">由于 Microsoft Edge 将代表扩展建立连接，因此应用可以查找呼叫者的程序包系列名称，以确定他们是否正在由 Microsoft Edge 连接以控制或验证呼叫者。</span><span class="sxs-lookup"><span data-stu-id="fb403-152">Since Microsoft Edge will be establishing the connection on behalf of the extension, the app can look up the caller's Package Family Name to determine if they're being connected by Microsoft Edge to control or authenticate the caller.</span></span> <span data-ttu-id="fb403-153">例如</span><span class="sxs-lookup"><span data-stu-id="fb403-153">E.g.</span></span> 

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

### <span data-ttu-id="fb403-154">邮件发送</span><span class="sxs-lookup"><span data-stu-id="fb403-154">Message sending</span></span>

<span data-ttu-id="fb403-155">若要使应用和扩展相互通信，需要向它们发送和发送消息。</span><span class="sxs-lookup"><span data-stu-id="fb403-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span></span>

<span data-ttu-id="fb403-156">Chrome 扩展使用 API 启动消息，以使用非永久性通道将消息传递至本机 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 主机。</span><span class="sxs-lookup"><span data-stu-id="fb403-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span></span> 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```  

<span data-ttu-id="fb403-157">第一个参数是本机主机的名称，Chrome 在注册表中查找清单。</span><span class="sxs-lookup"><span data-stu-id="fb403-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span></span> <span data-ttu-id="fb403-158">清单指定 Chrome 将在沙盒中启动的 .exe，邮件使用 std i/o 发送。</span><span class="sxs-lookup"><span data-stu-id="fb403-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span></span> <span data-ttu-id="fb403-159">扩展还可使用 API 建立永久性通道，该 API 将本机主机的名称作为 `runtime.connectNative` 唯一参数。</span><span class="sxs-lookup"><span data-stu-id="fb403-159">Extensions can also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span></span> 

<span data-ttu-id="fb403-160">Microsoft Edge 使用与 Chrome 的本机消息传递 API 相同的构造，以允许 Microsoft Edge 扩展指定要连接到的应用服务。</span><span class="sxs-lookup"><span data-stu-id="fb403-160">Microsoft Edge uses the same construct as Chrome's native messaging API to allow Microsoft Edge extensions to specify which app service to connect to.</span></span> <span data-ttu-id="fb403-161">第一个参数 `runtime.sendNativeMessage` 指定应用服务名称。</span><span class="sxs-lookup"><span data-stu-id="fb403-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span></span> <span data-ttu-id="fb403-162">在" [注册和主机清单"](#registration-and-host-manifest) 部分，这是 `"com.microsoft.inventory"` 。</span><span class="sxs-lookup"><span data-stu-id="fb403-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span></span> <span data-ttu-id="fb403-163">Microsoft Edge 扩展平台将本机消息传递主机限制为打包在扩展相同的 AppX 中的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="fb403-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span></span> <span data-ttu-id="fb403-164">这可缓解与恶意攻击（尝试通过篡改清单条目将 Microsoft Edge 连接到另一个程序包系列名称）关联的任何安全风险。</span><span class="sxs-lookup"><span data-stu-id="fb403-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span></span> 

<span data-ttu-id="fb403-165">这意味着，除了 API 中指定的名称之外，Microsoft Edge 还将使用与扩展相同的程序包系列名称来唯一地标识 `AppService` 应用服务的提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb403-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span></span>  

> [!NOTE]
> <span data-ttu-id="fb403-166">Microsoft Edge Extension [Toolkit。](./porting-chrome-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="fb403-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span></span> <span data-ttu-id="fb403-167">任何指定权限的 `"nativeMessaging"` 扩展将被标记为需要对此组件进行手动转换。</span><span class="sxs-lookup"><span data-stu-id="fb403-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span></span>

### <span data-ttu-id="fb403-168">通信协议</span><span class="sxs-lookup"><span data-stu-id="fb403-168">Communication protocol</span></span>

<span data-ttu-id="fb403-169">本机消息的通信协议确定邮件在发送前的格式设置。</span><span class="sxs-lookup"><span data-stu-id="fb403-169">Communication protocol for native messaging determines how messages are formatted before sending.</span></span>

<span data-ttu-id="fb403-170">Chrome 在单独的进程中启动每个本机消息传递主机，然后使用标准输入和标准输出与它进行通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span></span> <span data-ttu-id="fb403-171">相同的格式用于向两个方向发送邮件：每个邮件都使用 JSON、UTF-8 编码进行序列化，并且以本机字节顺序以 32 位邮件长度为前。</span><span class="sxs-lookup"><span data-stu-id="fb403-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span></span>

<span data-ttu-id="fb403-172">对于 Microsoft Edge，平台将启动实现应用服务的后台任务/主应用。</span><span class="sxs-lookup"><span data-stu-id="fb403-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span></span> <span data-ttu-id="fb403-173">启动时，将调用 `Run` 后台任务的方法：</span><span class="sxs-lookup"><span data-stu-id="fb403-173">On startup, the background task's `Run` method will be invoked:</span></span>  

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

<span data-ttu-id="fb403-174">当扩展向 UWP 应用发送消息时， [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) 将引发该事件。</span><span class="sxs-lookup"><span data-stu-id="fb403-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) event will be raised.</span></span> <span data-ttu-id="fb403-175">然后，此 JSON 格式的邮件将字符串化为对象的第一个 KeyValue [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 对。</span><span class="sxs-lookup"><span data-stu-id="fb403-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object.</span></span> <span data-ttu-id="fb403-176">:</span><span class="sxs-lookup"><span data-stu-id="fb403-176">:</span></span>

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```  

<span data-ttu-id="fb403-177">当 UWP 应用向扩展发送回响应时，将向 [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) 对象中添加 `ValueSet` 一个。</span><span class="sxs-lookup"><span data-stu-id="fb403-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) will be added to the `ValueSet` object.</span></span> <span data-ttu-id="fb403-178">Microsoft `Key` Edge 将忽略该属性，但 `Value` 该属性将包含有效的 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="fb403-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span></span>

### <span data-ttu-id="fb403-179">回调</span><span class="sxs-lookup"><span data-stu-id="fb403-179">Callback</span></span>

<span data-ttu-id="fb403-180">对于回调，Chrome [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 使用允许回调函数处理发送消息的任何异步响应。</span><span class="sxs-lookup"><span data-stu-id="fb403-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span></span>

<span data-ttu-id="fb403-181">Microsoft Edge [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) 使用对象的方法 [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) 让应用将对象 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 发送回扩展。</span><span class="sxs-lookup"><span data-stu-id="fb403-181">Microsoft Edge uses the [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) object's [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) method to let the app send a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object back to the extension.</span></span>


### <span data-ttu-id="fb403-182">邮件大小限制</span><span class="sxs-lookup"><span data-stu-id="fb403-182">Message size limit</span></span>
<span data-ttu-id="fb403-183">在扩展与应用之间来回发送的邮件对于 Chrome 和 Microsoft Edge 有不同的邮件大小限制。</span><span class="sxs-lookup"><span data-stu-id="fb403-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span></span>

<span data-ttu-id="fb403-184">Chrome 具有以下邮件大小限制：</span><span class="sxs-lookup"><span data-stu-id="fb403-184">Chrome has the following message size limitations:</span></span>
-   <span data-ttu-id="fb403-185">来自本机邮件主机的单个邮件限制：1 MB</span><span class="sxs-lookup"><span data-stu-id="fb403-185">Single message limit from native messaging host: 1 MB</span></span>
-   <span data-ttu-id="fb403-186">发送到本机邮件主机的单个邮件限制：4 GB</span><span class="sxs-lookup"><span data-stu-id="fb403-186">Single message limit sent to native messaging host: 4 GB</span></span>
    
<span data-ttu-id="fb403-187">对于 Microsoft Edge，虽然对邮件大小没有 (取决于内存) ，但 Microsoft Edge 通过限制以下邮件大小限制来防范本机应用行为 `AppService` 不当：</span><span class="sxs-lookup"><span data-stu-id="fb403-187">For Microsoft Edge, while `AppService` has no limit on message size (dependent on memory), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span></span>
-   <span data-ttu-id="fb403-188">从 UWP 应用到扩展的单个邮件限制：1 MB</span><span class="sxs-lookup"><span data-stu-id="fb403-188">Single message limit from UWP app to extension: 1 MB</span></span>
-   <span data-ttu-id="fb403-189">从扩展到 UWP 应用的单个邮件限制：100 MB</span><span class="sxs-lookup"><span data-stu-id="fb403-189">Single message limit from extension to UWP app: 100 MB</span></span>
    
### <span data-ttu-id="fb403-190">本机消息传递连接</span><span class="sxs-lookup"><span data-stu-id="fb403-190">Native messaging connections</span></span>

<span data-ttu-id="fb403-191">本机消息传递有两种类型的连接;持久和非永久。</span><span class="sxs-lookup"><span data-stu-id="fb403-191">There are two types of connections for native messaging; persistent and non-persistent.</span></span>
<span data-ttu-id="fb403-192">永久性 **连接** 是一个在端口被销毁之前一直运行的连接。</span><span class="sxs-lookup"><span data-stu-id="fb403-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span></span> <span data-ttu-id="fb403-193">非 **永久性** 连接是一个连接，一次打开一封邮件，在传递后关闭。</span><span class="sxs-lookup"><span data-stu-id="fb403-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span></span>

#### <span data-ttu-id="fb403-194">永久性</span><span class="sxs-lookup"><span data-stu-id="fb403-194">Persistent</span></span>

<span data-ttu-id="fb403-195">对于 Chrome，通过使用 创建消息端口来建立永久性连接 [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。</span><span class="sxs-lookup"><span data-stu-id="fb403-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="fb403-196">创建端口后，Chrome 将启动一个本机消息传递主机进程，该进程将一直运行，直到该端口被销毁。</span><span class="sxs-lookup"><span data-stu-id="fb403-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span></span>

<span data-ttu-id="fb403-197">对于 Microsoft Edge，一旦使用消息传递端口创建，Microsoft Edge 将启动该端口并保持其运行， `runtime.connectNative` [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) 直到该端口被销毁。</span><span class="sxs-lookup"><span data-stu-id="fb403-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) and keeps it running until the port is destroyed.</span></span> <span data-ttu-id="fb403-198">以下代码段演示如何从 UWP 应用内建立永久性连接。</span><span class="sxs-lookup"><span data-stu-id="fb403-198">The following snippet shows how a persistent connection is established from within a UWP app.</span></span> 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```  

#### <span data-ttu-id="fb403-199">非永久性</span><span class="sxs-lookup"><span data-stu-id="fb403-199">Non-persistent</span></span>

<span data-ttu-id="fb403-200">在 Chrome 中发送邮件时，无需创建邮件端口，Chrome 会针对每封邮件启动一 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 个新的本机邮件主机进程。</span><span class="sxs-lookup"><span data-stu-id="fb403-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span></span> <span data-ttu-id="fb403-201">主机进程生成的第一条消息将作为对原始请求的响应进行处理，在忽略后处理所有其他消息。</span><span class="sxs-lookup"><span data-stu-id="fb403-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span></span>

<span data-ttu-id="fb403-202">Microsoft Edge 将在收到每条消息的响应后终止连接。</span><span class="sxs-lookup"><span data-stu-id="fb403-202">Microsoft Edge will terminate the connection after every messages' response has been received.</span></span> <span data-ttu-id="fb403-203">以下代码段显示了一个非永久性连接，在接收请求并存储为请求后，该连接将在 `AppServiceConnection` UWP 应用中终止 [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) 。</span><span class="sxs-lookup"><span data-stu-id="fb403-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse).</span></span>

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

### <span data-ttu-id="fb403-204">权限</span><span class="sxs-lookup"><span data-stu-id="fb403-204">Permission</span></span>

<span data-ttu-id="fb403-205">为了允许本机消息传递与扩展一同使用，对于 Chrome 和 Microsoft Edge，你需要在文件中 `"nativeMessaging"` 声明 `manifest.json` 权限。</span><span class="sxs-lookup"><span data-stu-id="fb403-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you'll need to declare the `"nativeMessaging"` permission in you `manifest.json` file.</span></span>

## <span data-ttu-id="fb403-206">应用服务</span><span class="sxs-lookup"><span data-stu-id="fb403-206">App services</span></span>
<span data-ttu-id="fb403-207">本部分详细介绍应用服务对 Microsoft Edge 本机邮件性能和内存的影响。</span><span class="sxs-lookup"><span data-stu-id="fb403-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span></span>

### <span data-ttu-id="fb403-208">性能</span><span class="sxs-lookup"><span data-stu-id="fb403-208">Performance</span></span>

<span data-ttu-id="fb403-209">应用服务由前台应用"赞助"，它调用它们，用于本机消息传递目的为 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="fb403-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span></span> <span data-ttu-id="fb403-210">这意味着只要 Microsoft Edge 正在运行，应用服务就可以运行。</span><span class="sxs-lookup"><span data-stu-id="fb403-210">This means that app services can run as long as Microsoft Edge is running.</span></span>

<span data-ttu-id="fb403-211">对于延迟，应用服务使用命名管道，在初始连接后，允许两个应用直接通信。</span><span class="sxs-lookup"><span data-stu-id="fb403-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span></span> <span data-ttu-id="fb403-212">这种通信方法会产生低延迟。</span><span class="sxs-lookup"><span data-stu-id="fb403-212">This method of communication produces low latency.</span></span> <span data-ttu-id="fb403-213">启动托管应用服务 (约 80 毫秒以启动某些设备上后台任务的进程后，CPU 较慢的设备将遇到一些初始) 。</span><span class="sxs-lookup"><span data-stu-id="fb403-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service (~80ms to startup the background task on some devices).</span></span> <span data-ttu-id="fb403-214">启动后，较慢的 CPU 设备的性能应该良好。</span><span class="sxs-lookup"><span data-stu-id="fb403-214">After start-up, performance on slow CPU devices should be good.</span></span> 

### <span data-ttu-id="fb403-215">内存</span><span class="sxs-lookup"><span data-stu-id="fb403-215">Memory</span></span>
<span data-ttu-id="fb403-216">分配给应用服务的内存会从分配给 Microsoft Edge 的配额中取消。</span><span class="sxs-lookup"><span data-stu-id="fb403-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span></span> <span data-ttu-id="fb403-217">这意味着，如果 Microsoft Edge 启动的应用服务过多，它们可能会用完内存。</span><span class="sxs-lookup"><span data-stu-id="fb403-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span></span> <span data-ttu-id="fb403-218">常见的后台任务内存上限在应用服务上强制执行。</span><span class="sxs-lookup"><span data-stu-id="fb403-218">The usual background task memory caps are enforced on app services.</span></span> <span data-ttu-id="fb403-219">例如，在 512MB 设备上，应用服务后台任务不能大于 16MB。</span><span class="sxs-lookup"><span data-stu-id="fb403-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span></span> <span data-ttu-id="fb403-220">当设备向上扩展时，此数字会上升。</span><span class="sxs-lookup"><span data-stu-id="fb403-220">This number goes up as the devices scale up.</span></span>

## <span data-ttu-id="fb403-221">使用本机消息传递创建扩展</span><span class="sxs-lookup"><span data-stu-id="fb403-221">Creating an extension with native messaging</span></span>

<span data-ttu-id="fb403-222">为了测试本机消息传递，扩展需要程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="fb403-222">In order to test native messaging, your extension needs a Package Family Name.</span></span> <span data-ttu-id="fb403-223">Microsoft Edge 使用它来确定本机邮件主机标识，这意味着应打包扩展。</span><span class="sxs-lookup"><span data-stu-id="fb403-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span></span> 

<span data-ttu-id="fb403-224">若要在应用程序内使用本机消息传递创建Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="fb403-224">To create your extension with native messaging in Visual Studio:</span></span>

1.  <span data-ttu-id="fb403-225">在项目中创建 UWP Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fb403-225">Create a UWP project in Visual Studio.</span></span>
2.  <span data-ttu-id="fb403-226">[添加到 `AppService` 你的 UWP 应用](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。</span><span class="sxs-lookup"><span data-stu-id="fb403-226">[Add `AppService` to your UWP app](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>
    -   <span data-ttu-id="fb403-227">此时， [可以选择 `AppService` 配置为](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) 托管在主应用中，而不是后台任务中。</span><span class="sxs-lookup"><span data-stu-id="fb403-227">You can optionally [configure `AppService` to be hosted in the main app](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span></span>
3.  <span data-ttu-id="fb403-228">生成和测试 UWP 项目。</span><span class="sxs-lookup"><span data-stu-id="fb403-228">Build and test your UWP project.</span></span>
    -   <span data-ttu-id="fb403-229">可以选择添加桌面 [桥组件](#adding-a-desktop-bridge-component)。</span><span class="sxs-lookup"><span data-stu-id="fb403-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span></span>
4.  <span data-ttu-id="fb403-230">创建使用本机消息传递与 UWP 配套应用进行通信的 Microsoft Edge 扩展。</span><span class="sxs-lookup"><span data-stu-id="fb403-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span></span> <span data-ttu-id="fb403-231">扩展文件可以添加到 `Extension` UWP 项目中命名的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fb403-231">The extension files can be added into a folder named `Extension` in the UWP project.</span></span> <span data-ttu-id="fb403-232">此文件夹下的所有文件（包括子文件夹）都需要配置其属性，这样 `Build Action=Content` `Copy to Output Directory=Copy Always` 和 。</span><span class="sxs-lookup"><span data-stu-id="fb403-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span> <span data-ttu-id="fb403-233">请确保 `manifest.json` 还配置了这些属性。</span><span class="sxs-lookup"><span data-stu-id="fb403-233">Make sure `manifest.json` is also configured with these properties.</span></span>
5.  <span data-ttu-id="fb403-234">修改 `package.manifest.xml` 项目中的文件以包含扩展元数据，并添加以下代码将其转换为无头应用 `AppListEntry="none"` ：</span><span class="sxs-lookup"><span data-stu-id="fb403-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span></span>
    
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
    
6.  <span data-ttu-id="fb403-235">在本机消息传递 API 中使用 `AppService` 为 UWP 配置的名称。</span><span class="sxs-lookup"><span data-stu-id="fb403-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span></span>
7.  <span data-ttu-id="fb403-236">使用可选的 [桌面桥](#deploying) 组件 (生成和部署 UWP) 。</span><span class="sxs-lookup"><span data-stu-id="fb403-236">Build and [deploy](#deploying) the UWP project (with the optional Desktop Bridge component).</span></span>
8.  <span data-ttu-id="fb403-237">[准备好](#packaging) 提交应用商店后打包本机消息传递扩展</span><span class="sxs-lookup"><span data-stu-id="fb403-237">[Package](#packaging) your native messaging extension once it's ready for Store submission</span></span>
    
> [!NOTE]
> <span data-ttu-id="fb403-238">有关 [完整本机消息传递](#demos) 扩展的示例，请引用"演示"部分。</span><span class="sxs-lookup"><span data-stu-id="fb403-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span></span>

## <span data-ttu-id="fb403-239">添加桌面桥组件</span><span class="sxs-lookup"><span data-stu-id="fb403-239">Adding a Desktop Bridge component</span></span> 
<span data-ttu-id="fb403-240">如果要将桌面桥组件添加到程序包，则需要在 Visual Studio 中创建和生成 Win32 项目。</span><span class="sxs-lookup"><span data-stu-id="fb403-240">If you want to add a Desktop Bridge component to your package, you'll need to create and build your Win32 project in Visual Studio.</span></span> <span data-ttu-id="fb403-241">若要了解如何将 win32 应用转换为 UWP，请参阅通过桌面桥将应用移植到[Windows 10。](/windows/uwp/porting/desktop-to-uwp-root)</span><span class="sxs-lookup"><span data-stu-id="fb403-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span></span> <span data-ttu-id="fb403-242">内置Visual Studio后，可以通过执行以下步骤将 Win32 可执行文件添加到程序包中：</span><span class="sxs-lookup"><span data-stu-id="fb403-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span></span>

1.  <span data-ttu-id="fb403-243">将 Win32 项目添加到与 UWP 项目相同的解决方案。</span><span class="sxs-lookup"><span data-stu-id="fb403-243">Add the Win32 project to the same solution as the UWP project.</span></span> 
2.  <span data-ttu-id="fb403-244">将 Win32 项目设置为 UWP 项目的从属项目：</span><span class="sxs-lookup"><span data-stu-id="fb403-244">Set the Win32 project as a dependent project for the UWP project:</span></span>
    
    ![设置项目依赖项](./../media/project-dependencies.PNG)
    
3.  <span data-ttu-id="fb403-246">在 `Win32` UWP 项目中创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb403-246">Create a `Win32` folder within the UWP project.</span></span> <span data-ttu-id="fb403-247">将项目的必要二进制文件 `Win32` 复制到此文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb403-247">Copy the necessary binaries for the `Win32` project to this folder.</span></span> <span data-ttu-id="fb403-248">配置所有二进制文件的属性， `Build Action=Content` 例如. `Copy to Output Directory=Copy Always`</span><span class="sxs-lookup"><span data-stu-id="fb403-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>
    
    ![包含 win32 和 UWP 应用文件的文件夹](./../media/desktop-bridge.png)
    
4.  <span data-ttu-id="fb403-250">修改 UWP 项目文件，以使用 PostBuild 事件命令将项目所有必要的二进制文件 `Win32` 复制到此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fb403-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span></span> <span data-ttu-id="fb403-251">这可确保每次重新生成解决方案时将更新的二进制文件复制到文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb403-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span></span>
    
    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```
    
5.  <span data-ttu-id="fb403-252">通过 `package.manifest.xml` 向元素 `<desktop:Extension>` 添加元素进行修改 `<Extensions>` ：</span><span class="sxs-lookup"><span data-stu-id="fb403-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span></span>
    
    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```
    
## <span data-ttu-id="fb403-253">部署</span><span class="sxs-lookup"><span data-stu-id="fb403-253">Deploying</span></span>
<span data-ttu-id="fb403-254">配置 UWP 项目包和 (Win32 项目) 如上所述，即可使用 Visual Studio 部署解决方案。</span><span class="sxs-lookup"><span data-stu-id="fb403-254">Once you have configured your UWP project (and optionally Win32 project) as outlined above, you are ready to deploy the solution using Visual Studio.</span></span>

![生成 inprocess 项目](../media/native-message-uwp-debug.PNG)

<span data-ttu-id="fb403-256">正确部署解决方案后，你应该会看到 Microsoft Edge 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="fb403-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span></span>

![在 Microsoft Edge 中显示扩展](../media/secureextension.png)

## <span data-ttu-id="fb403-258">打包</span><span class="sxs-lookup"><span data-stu-id="fb403-258">Packaging</span></span>

> [!NOTE]
> <span data-ttu-id="fb403-259">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。</span><span class="sxs-lookup"><span data-stu-id="fb403-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="fb403-260">[如果你的请求是](https://aka.ms/extension-request) Microsoft Store 的一部分，请联系我们，我们将考虑你进行将来的更新。</span><span class="sxs-lookup"><span data-stu-id="fb403-260">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>

<span data-ttu-id="fb403-261">你可以生成应用商店程序包，以使用内置应用功能提交到 Windows 开发人员Visual Studio功能：</span><span class="sxs-lookup"><span data-stu-id="fb403-261">You can generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span></span>

![创建应用商店程序包](../media/create-store-package.PNG)

## <span data-ttu-id="fb403-263">调试</span><span class="sxs-lookup"><span data-stu-id="fb403-263">Debugging</span></span>
<span data-ttu-id="fb403-264">调试说明因要测试的组件而异：</span><span class="sxs-lookup"><span data-stu-id="fb403-264">The instructions for debugging vary depending on which component you want to test out:</span></span>

### <span data-ttu-id="fb403-265">调试扩展</span><span class="sxs-lookup"><span data-stu-id="fb403-265">Debugging the extension</span></span>
<span data-ttu-id="fb403-266">部署解决方案后，扩展将安装在 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="fb403-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span></span> <span data-ttu-id="fb403-267">请查看 [调试指南](./debugging-extensions.md) ，了解有关如何调试扩展的信息。</span><span class="sxs-lookup"><span data-stu-id="fb403-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span></span>


### <span data-ttu-id="fb403-268">调试 UWP 应用</span><span class="sxs-lookup"><span data-stu-id="fb403-268">Debugging the UWP app</span></span>
<span data-ttu-id="fb403-269">当扩展尝试使用本机消息传递 API 连接到它时 [，UWP 应用将启动](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)。</span><span class="sxs-lookup"><span data-stu-id="fb403-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="fb403-270">只需在进程启动后调试 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="fb403-270">You'll need to debug the UWP app only once the process starts.</span></span> <span data-ttu-id="fb403-271">这可以通过项目的"属性"页进行配置：</span><span class="sxs-lookup"><span data-stu-id="fb403-271">This can be configured via the project's Property page:</span></span>

1.  <span data-ttu-id="fb403-272">在Visual Studio中，右键单击 UWP 应用项目</span><span class="sxs-lookup"><span data-stu-id="fb403-272">In Visual Studio, right click your UWP app project</span></span>
2.  <span data-ttu-id="fb403-273">选择属性</span><span class="sxs-lookup"><span data-stu-id="fb403-273">Select Properties</span></span>
3.  <span data-ttu-id="fb403-274">选中"不启动，但在启动时调试代码"</span><span class="sxs-lookup"><span data-stu-id="fb403-274">Check "Do not launch, but debug my code when it starts"</span></span>
    
    ![选择"不启动"框](../media/native-message-do-not-launch.png)
    
<span data-ttu-id="fb403-276">In Visual Studio you can now set breakpoints in the code where you want to debug， then launch the debugger by pressing F5.</span><span class="sxs-lookup"><span data-stu-id="fb403-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span></span> <span data-ttu-id="fb403-277">与扩展交互以连接到 UWP 应用后，Visual Studio将自动附加到进程。</span><span class="sxs-lookup"><span data-stu-id="fb403-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span></span>

### <span data-ttu-id="fb403-278">调试桌面桥</span><span class="sxs-lookup"><span data-stu-id="fb403-278">Debugging the Desktop Bridge</span></span>
<span data-ttu-id="fb403-279">尽管调试已转换的 Win32 [ (桌面](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) 桥) ，但唯一适用于此方案的方法还是 PLMDebug 选项。</span><span class="sxs-lookup"><span data-stu-id="fb403-279">Even though there are various [methods for debugging a Desktop Bridge](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) (converted Win32 app), the only one applicable for this scenarios is the PLMDebug option.</span></span> <span data-ttu-id="fb403-280">还可以将调试代码添加到启动函数以执行特定时间等待，从而允许您将Visual Studio附加到进程。</span><span class="sxs-lookup"><span data-stu-id="fb403-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span></span>
