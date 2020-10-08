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
# <span data-ttu-id="8277a-104">Microsoft Edge 中的本机消息</span><span class="sxs-lookup"><span data-stu-id="8277a-104">Native messaging in Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="8277a-105">本机消息传递体系结构概述</span><span class="sxs-lookup"><span data-stu-id="8277a-105">Native messaging architecture overview</span></span>

<span data-ttu-id="8277a-106">通过 Windows 10 创意者更新，Microsoft Edge 扩展可以使用本机消息功能与配套的通用 Windows 平台 (UWP) 应用进行通信。</span><span class="sxs-lookup"><span data-stu-id="8277a-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform (UWP) app.</span></span>  <span data-ttu-id="8277a-107">在高级别上，Microsoft Edge 扩展将相同的 Api 用于本机消息作为 Chrome 和 Firefox 扩展。</span><span class="sxs-lookup"><span data-stu-id="8277a-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span></span> <span data-ttu-id="8277a-108">但是，将需要使用通用 Windows 平台来实现本机消息主机。</span><span class="sxs-lookup"><span data-stu-id="8277a-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span></span>

> [!NOTE]
> <span data-ttu-id="8277a-109">以下概述 (通过 AppService) 连接到 UWP 应用的方法是支持 Microsoft Edge 扩展和本机组件之间的通信的唯一支持机制。</span><span class="sxs-lookup"><span data-stu-id="8277a-109">The method outlined below (connecting to a UWP app via AppService) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span></span> <span data-ttu-id="8277a-110">有关如何启用与旧版 Win32 组件的通信的详细信息，请参阅本指南的 " [添加桌面桥组件](#adding-a-desktop-bridge-component) " 部分。</span><span class="sxs-lookup"><span data-stu-id="8277a-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span></span> 

 <span data-ttu-id="8277a-111">Microsoft Edge 的本机消息传递体系结构将现有 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API 用作基础进程间通信 (IPC) 基础结构。</span><span class="sxs-lookup"><span data-stu-id="8277a-111">Microsoft Edge's native messaging architecture leverages the existing [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API as the underlying inter-process communication (IPC) infrastructure.</span></span> <span data-ttu-id="8277a-112">UWP 应用使用 `AppService` API 与其他 API 进行通信。</span><span class="sxs-lookup"><span data-stu-id="8277a-112">UWP apps use the `AppService` API to communicate with one another.</span></span> <span data-ttu-id="8277a-113">因此，Microsoft Edge 扩展现在可以与 UWP 应用进行通信。</span><span class="sxs-lookup"><span data-stu-id="8277a-113">Because of this, Microsoft Edge extensions can now communicate with UWP apps.</span></span>

![本机消息传递体系结构](./../media/native-messaging-architecture.png)


### <span data-ttu-id="8277a-115">何时以及何时不使用本机消息</span><span class="sxs-lookup"><span data-stu-id="8277a-115">When and when not to use native messaging</span></span>

<span data-ttu-id="8277a-116">本机消息向扩展添加一个全新的图层。</span><span class="sxs-lookup"><span data-stu-id="8277a-116">Native messaging adds a whole new layer to your extension.</span></span> <span data-ttu-id="8277a-117">通过为你的扩展实现 UWP 配套应用，你可以使用以下可能功能：</span><span class="sxs-lookup"><span data-stu-id="8277a-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span></span>

* <span data-ttu-id="8277a-118">同步数据 (例如带有配套的 UWP 应用的凭据) 。</span><span class="sxs-lookup"><span data-stu-id="8277a-118">Synchronize data (e.g. credentials) with a companion UWP app.</span></span>
* <span data-ttu-id="8277a-119">实现更强的加密/解密算法在 web Api 中不可用。</span><span class="sxs-lookup"><span data-stu-id="8277a-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span></span>
* <span data-ttu-id="8277a-120">访问无法通过 web Api 访问的资源，例如硬件或 USB 设备</span><span class="sxs-lookup"><span data-stu-id="8277a-120">Access resources that are not accessible through web APIs, e.g. hardware or USB devices</span></span>

<span data-ttu-id="8277a-121">由于安全或策略限制，某些情况下不能使用本机消息：</span><span class="sxs-lookup"><span data-stu-id="8277a-121">There are a few instances where native messaging can't be used due to security or policy restrictions:</span></span>

* <span data-ttu-id="8277a-122">修改 Microsoft Edge 或 Windows 中的用户设置，例如更改默认浏览器或搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="8277a-122">Modifying user settings in either Microsoft Edge or Windows, e.g. changing the default browser or search provider.</span></span>
* <span data-ttu-id="8277a-123">与应用和扩展的 Microsoft 应用商店策略冲突的操作。</span><span class="sxs-lookup"><span data-stu-id="8277a-123">Actions that violate Microsoft Store policies for both apps and extensions.</span></span>
* <span data-ttu-id="8277a-124">通过本机消息主机将数据传输到远程终结点。</span><span class="sxs-lookup"><span data-stu-id="8277a-124">Transferring data to remote endpoint via native message host.</span></span>
* <span data-ttu-id="8277a-125">允许其他应用下载更改扩展行为的内容。</span><span class="sxs-lookup"><span data-stu-id="8277a-125">Allowing other apps to download content that changes extension behavior.</span></span>

## <span data-ttu-id="8277a-126">演示</span><span class="sxs-lookup"><span data-stu-id="8277a-126">Demos</span></span>

<span data-ttu-id="8277a-127">若要了解同时具有配套的 UWP 应用和桌面桥的 Microsoft Edge 本机消息扩展的外观，请参阅 GitHub 上的 [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) 和 [DigitalSigning (c + +) ](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) 示例。</span><span class="sxs-lookup"><span data-stu-id="8277a-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span></span>

### <span data-ttu-id="8277a-128">工作原理</span><span class="sxs-lookup"><span data-stu-id="8277a-128">How it works</span></span>

<span data-ttu-id="8277a-129">示例的 Microsoft Edge 扩展组件使用其内容脚本来检测用户何时键入应加密的信息。</span><span class="sxs-lookup"><span data-stu-id="8277a-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span></span> <span data-ttu-id="8277a-130">该扩展通过本机消息将其与桌面桥组件进行通信。</span><span class="sxs-lookup"><span data-stu-id="8277a-130">The extension communicates this to the Desktop Bridge component via native messaging.</span></span> <span data-ttu-id="8277a-131">当用户准备提交数据时，扩展会将加密的值返回到网站。</span><span class="sxs-lookup"><span data-stu-id="8277a-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span></span>

> [!NOTE]
> <span data-ttu-id="8277a-132">此示例仅适用于使用自定义事件与扩展名的内容脚本进行通信的网页。</span><span class="sxs-lookup"><span data-stu-id="8277a-132">This sample will only work on a webpage that uses custom events to communicate with the extension's content script.</span></span> <span data-ttu-id="8277a-133">示例文件夹包含一个 [.html 文件](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) ，用于测试扩展名。</span><span class="sxs-lookup"><span data-stu-id="8277a-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span></span>

<span data-ttu-id="8277a-134">在此示例中，UWP 应用用于将来自桌面桥的响应传递到 Microsoft Edge，然后通过回调将其发送到 Microsoft Edge 扩展。</span><span class="sxs-lookup"><span data-stu-id="8277a-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span></span> <span data-ttu-id="8277a-135">虽然此示例在主应用中运行本机消息主机，但它也可以作为后台任务运行。</span><span class="sxs-lookup"><span data-stu-id="8277a-135">While this example has the native messaging host run in the main app, it's also able to run as a background task.</span></span> <span data-ttu-id="8277a-136">在两者之间切换需要编辑扩展的后台脚本，将字符串中的字符串更改 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` 为 `"NativeMessagingHostOutOfProcess"` 。</span><span class="sxs-lookup"><span data-stu-id="8277a-136">Switching between the two requires editing the extension's background script, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span></span>

## <span data-ttu-id="8277a-137">Chrome vs Microsoft Edge 实现</span><span class="sxs-lookup"><span data-stu-id="8277a-137">Chrome vs Microsoft Edge implementation</span></span>

<span data-ttu-id="8277a-138">虽然 Chrome 会使用消息传递 Api 的路由以使其扩展能够与应用通信，但 Microsoft Edge 利用了 API，该 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) api 现在支持 Microsoft Edge 扩展和 UWP 应用进行通信。</span><span class="sxs-lookup"><span data-stu-id="8277a-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span></span>

<span data-ttu-id="8277a-139">本节详细介绍了 Chrome 和 Microsoft Edge 如何处理本机消息实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="8277a-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span></span>

### <span data-ttu-id="8277a-140">注册和主机清单</span><span class="sxs-lookup"><span data-stu-id="8277a-140">Registration and host manifest</span></span>
<span data-ttu-id="8277a-141">为了让你的扩展能够将你的应用识别为本机消息主机，将需要注册该应用。</span><span class="sxs-lookup"><span data-stu-id="8277a-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span></span>


<span data-ttu-id="8277a-142">对于 [Chrome 本机消息](https://developer.chrome.com/extensions/nativeMessaging) 主机注册，你的应用需要在定义本机消息主机配置的 Windows 文件系统中的任意位置安装清单文件。</span><span class="sxs-lookup"><span data-stu-id="8277a-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span></span>

<span data-ttu-id="8277a-143">下面的 JSON 是如何设置配置文件的示例：</span><span class="sxs-lookup"><span data-stu-id="8277a-143">The following JSON is an example of how the config file can be set up:</span></span>

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

<span data-ttu-id="8277a-144">若要安装此文件，应用需要：</span><span class="sxs-lookup"><span data-stu-id="8277a-144">To install this file, the app would need to:</span></span>

1. <span data-ttu-id="8277a-145">在定义主机配置的注册表中的预定义位置注册清单文件：</span><span class="sxs-lookup"><span data-stu-id="8277a-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span></span>
   - `HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

     <span data-ttu-id="8277a-146">或者</span><span class="sxs-lookup"><span data-stu-id="8277a-146">or</span></span>
   - `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

2. <span data-ttu-id="8277a-147">将该注册表项的默认值设置为清单文件的完整路径，例如</span><span class="sxs-lookup"><span data-stu-id="8277a-147">Set the default value of that key to the full path to the manifest file, e.g.</span></span>  `[HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"`




<span data-ttu-id="8277a-148">对于 Microsoft Edge，为了注册 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) (本机消息主机) ，你需要将 UWP 配套应用包含在与你的扩展名相同的程序包中，并在你的项目文件中指定 [AppService 扩展名](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) `Package.appxmanifest` 。</span><span class="sxs-lookup"><span data-stu-id="8277a-148">For Microsoft Edge, in order to register an [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx)(native messaging host) you'll need to include the UWP companion app in the same package as your extension and specify the [AppService extension](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in your project's `Package.appxmanifest` file.</span></span> <span data-ttu-id="8277a-149">`EntryPoint`和 `Name` 属性可以配置：</span><span class="sxs-lookup"><span data-stu-id="8277a-149">The `EntryPoint` and `Name` attributes can be configured by you:</span></span>

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


<span data-ttu-id="8277a-150">你还需要设置允许哪些扩展 (s) 连接到该服务。</span><span class="sxs-lookup"><span data-stu-id="8277a-150">You'll also need to set which extension(s) are allowed to connect to the service.</span></span> <span data-ttu-id="8277a-151">由于 Microsoft Edge `"allowed_origins"` 在其 package.appxmanifest 中没有等效的清单属性，因此需要在运行时由 UWP 应用确定并强制执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8277a-151">Because Microsoft Edge doesn't have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span></span> <span data-ttu-id="8277a-152">由于 Microsoft Edge 将代表扩展建立连接，因此应用可以查找呼叫者的程序包系列名称，以确定它们是否通过 Microsoft Edge 进行连接以控制或验证呼叫者。</span><span class="sxs-lookup"><span data-stu-id="8277a-152">Since Microsoft Edge will be establishing the connection on behalf of the extension, the app can look up the caller's Package Family Name to determine if they're being connected by Microsoft Edge to control or authenticate the caller.</span></span> <span data-ttu-id="8277a-153">例如</span><span class="sxs-lookup"><span data-stu-id="8277a-153">E.g.</span></span> 

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



### <span data-ttu-id="8277a-154">消息发送</span><span class="sxs-lookup"><span data-stu-id="8277a-154">Message sending</span></span>

<span data-ttu-id="8277a-155">对于一个应用和一个用于相互通信的扩展，需要向其发送消息和发送消息。</span><span class="sxs-lookup"><span data-stu-id="8277a-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span></span>

<span data-ttu-id="8277a-156">Chrome 扩展使用 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API 使用非持久性信道将消息发送到本机主机来启动消息。</span><span class="sxs-lookup"><span data-stu-id="8277a-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span></span> 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```

<span data-ttu-id="8277a-157">第一个参数是本机主机的名称，该名称是在清单的注册表中查找的 "Chrome"。</span><span class="sxs-lookup"><span data-stu-id="8277a-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span></span> <span data-ttu-id="8277a-158">清单指定了 Chrome 将在沙盒中启动的 .exe，并使用 std i/o 发送消息。</span><span class="sxs-lookup"><span data-stu-id="8277a-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span></span> <span data-ttu-id="8277a-159">扩展还可以使用 API 建立永久通道 `runtime.connectNative` ，该通道采用本机主机的名称作为唯一参数。</span><span class="sxs-lookup"><span data-stu-id="8277a-159">Extensions can also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span></span> 

<span data-ttu-id="8277a-160">Microsoft Edge 使用与 Chrome 的本机消息处理 API 相同的构造，以允许 Microsoft Edge 扩展指定要连接的应用服务。</span><span class="sxs-lookup"><span data-stu-id="8277a-160">Microsoft Edge uses the same construct as Chrome's native messaging API to allow Microsoft Edge extensions to specify which app service to connect to.</span></span> <span data-ttu-id="8277a-161">中的第一个参数 `runtime.sendNativeMessage` 指定应用服务名称。</span><span class="sxs-lookup"><span data-stu-id="8277a-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span></span> <span data-ttu-id="8277a-162">在 " [注册和主机清单](#registration-and-host-manifest) " 部分中，这是 `"com.microsoft.inventory"` 。</span><span class="sxs-lookup"><span data-stu-id="8277a-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span></span> <span data-ttu-id="8277a-163">Microsoft Edge 扩展平台将本机消息主机限制为一个 UWP 应用，该应用打包在与扩展相同的 AppX 中。</span><span class="sxs-lookup"><span data-stu-id="8277a-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span></span> <span data-ttu-id="8277a-164">这将减少与尝试通过篡改清单条目连接 Microsoft Edge 与其他程序包系列名称关联的恶意攻击的任何安全风险。</span><span class="sxs-lookup"><span data-stu-id="8277a-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span></span> 

<span data-ttu-id="8277a-165">这意味着，除了在 API 中指定的名称之外，Microsoft Edge 还将使用与扩展名相同的程序包系列名称 `AppService` 来唯一标识应用服务的提供程序。</span><span class="sxs-lookup"><span data-stu-id="8277a-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span></span>  

> [!NOTE]
> <span data-ttu-id="8277a-166">这将不会由 [Microsoft Edge 扩展工具包](./porting-chrome-extensions.md)轻松转换。</span><span class="sxs-lookup"><span data-stu-id="8277a-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span></span> <span data-ttu-id="8277a-167">任何指定权限的扩展 `"nativeMessaging"` 将被标记为需要此组件的手动转换。</span><span class="sxs-lookup"><span data-stu-id="8277a-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span></span>





### <span data-ttu-id="8277a-168">通信协议</span><span class="sxs-lookup"><span data-stu-id="8277a-168">Communication protocol</span></span>

<span data-ttu-id="8277a-169">用于本机消息的通信协议确定发送邮件之前如何设置其格式。</span><span class="sxs-lookup"><span data-stu-id="8277a-169">Communication protocol for native messaging determines how messages are formatted before sending.</span></span>

<span data-ttu-id="8277a-170">Chrome 在单独的进程中启动每个本机消息传递主机，并使用标准输入和标准输出与它进行通信。</span><span class="sxs-lookup"><span data-stu-id="8277a-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span></span> <span data-ttu-id="8277a-171">相同格式用于以两种方向发送邮件：每条消息都使用 JSON 进行序列化，UTF-8 编码，前面是32位消息长度（以本机字节顺序为单位）。</span><span class="sxs-lookup"><span data-stu-id="8277a-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span></span>


<span data-ttu-id="8277a-172">对于 Microsoft Edge，实现应用服务的后台任务/主要应用将由平台启动。</span><span class="sxs-lookup"><span data-stu-id="8277a-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span></span> <span data-ttu-id="8277a-173">启动时，将调用后台任务的 `Run` 方法：</span><span class="sxs-lookup"><span data-stu-id="8277a-173">On startup, the background task's `Run` method will be invoked:</span></span>  

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

<span data-ttu-id="8277a-174">当你的扩展向 UWP 应用发送消息时， [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) 将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="8277a-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) event will be raised.</span></span> <span data-ttu-id="8277a-175">然后，此 JSON 格式消息将 stringified 到对象的第一个 KeyValue 对 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 。</span><span class="sxs-lookup"><span data-stu-id="8277a-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object.</span></span> <span data-ttu-id="8277a-176">:</span><span class="sxs-lookup"><span data-stu-id="8277a-176">:</span></span>

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```

<span data-ttu-id="8277a-177">如果你的 UWP 应用将答复发送回你的扩展，则会将 a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) 添加到该 `ValueSet` 对象。</span><span class="sxs-lookup"><span data-stu-id="8277a-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) will be added to the `ValueSet` object.</span></span> <span data-ttu-id="8277a-178">该 `Key` 属性将被 Microsoft Edge 忽略，但该 `Value` 属性将包含有效的 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="8277a-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span></span>

### <span data-ttu-id="8277a-179">叫</span><span class="sxs-lookup"><span data-stu-id="8277a-179">Callback</span></span>

<span data-ttu-id="8277a-180">对于回调，Chrome 用法 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 允许回调函数处理发送消息的任何异步响应。</span><span class="sxs-lookup"><span data-stu-id="8277a-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span></span>

<span data-ttu-id="8277a-181">Microsoft Edge 使用 [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) 对象的 [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) 方法让应用将 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 对象发送回扩展。</span><span class="sxs-lookup"><span data-stu-id="8277a-181">Microsoft Edge uses the [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) object's [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) method to let the app send a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object back to the extension.</span></span>


### <span data-ttu-id="8277a-182">邮件大小限制</span><span class="sxs-lookup"><span data-stu-id="8277a-182">Message size limit</span></span>
<span data-ttu-id="8277a-183">在扩展和应用之间来回发送的邮件对 Chrome 和 Microsoft Edge 的邮件大小限制不同。</span><span class="sxs-lookup"><span data-stu-id="8277a-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span></span>

<span data-ttu-id="8277a-184">Chrome 具有下列邮件大小限制：</span><span class="sxs-lookup"><span data-stu-id="8277a-184">Chrome has the following message size limitations:</span></span>
- <span data-ttu-id="8277a-185">来自本机消息主机的单个邮件限制： 1 MB</span><span class="sxs-lookup"><span data-stu-id="8277a-185">Single message limit from native messaging host: 1 MB</span></span>
- <span data-ttu-id="8277a-186">发送到本机消息主机的单个消息限制： 4 GB</span><span class="sxs-lookup"><span data-stu-id="8277a-186">Single message limit sent to native messaging host: 4 GB</span></span>

<span data-ttu-id="8277a-187">对于 Microsoft Edge，虽然对 `AppService` 邮件大小没有限制 (依赖于内存) ，但 Microsoft Edge 通过强制执行下列邮件大小限制来防止自身对本机应用的行为：</span><span class="sxs-lookup"><span data-stu-id="8277a-187">For Microsoft Edge, while `AppService` has no limit on message size (dependent on memory), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span></span>
- <span data-ttu-id="8277a-188">从 UWP 应用到扩展的单个邮件限制： 1 MB</span><span class="sxs-lookup"><span data-stu-id="8277a-188">Single message limit from UWP app to extension: 1 MB</span></span>
- <span data-ttu-id="8277a-189">从扩展到 UWP 应用的单个邮件限制： 100 MB</span><span class="sxs-lookup"><span data-stu-id="8277a-189">Single message limit from extension to UWP app: 100 MB</span></span>



### <span data-ttu-id="8277a-190">本机消息连接</span><span class="sxs-lookup"><span data-stu-id="8277a-190">Native messaging connections</span></span>

<span data-ttu-id="8277a-191">本机消息有两种类型的连接;永久性和非持久。</span><span class="sxs-lookup"><span data-stu-id="8277a-191">There are two types of connections for native messaging; persistent and non-persistent.</span></span>
<span data-ttu-id="8277a-192">**永久**连接是一直保持运行的连接，直到该端口被销毁。</span><span class="sxs-lookup"><span data-stu-id="8277a-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span></span> <span data-ttu-id="8277a-193">**非持久**连接是一次打开一条消息并在传递后关闭的连接。</span><span class="sxs-lookup"><span data-stu-id="8277a-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span></span>

#### <span data-ttu-id="8277a-194">永久性</span><span class="sxs-lookup"><span data-stu-id="8277a-194">Persistent</span></span>

<span data-ttu-id="8277a-195">对于 Chrome，通过使用创建消息传递端口来建立持久连接 [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。</span><span class="sxs-lookup"><span data-stu-id="8277a-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="8277a-196">端口创建后，Chrome 将启动一个本机消息传递主机进程，该进程将一直保持运行，直到它销毁的端口。</span><span class="sxs-lookup"><span data-stu-id="8277a-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span></span>

<span data-ttu-id="8277a-197">对于 Microsoft Edge，一旦使用消息传送端口创建 `runtime.connectNative` ，Microsoft Edge 将启动 [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) 并一直运行，直到该端口损坏。</span><span class="sxs-lookup"><span data-stu-id="8277a-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) and keeps it running until the port is destroyed.</span></span> <span data-ttu-id="8277a-198">以下代码段显示了如何从 UWP 应用内建立持久连接。</span><span class="sxs-lookup"><span data-stu-id="8277a-198">The following snippet shows how a persistent connection is established from within a UWP app.</span></span> 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```

#### <span data-ttu-id="8277a-199">非持久</span><span class="sxs-lookup"><span data-stu-id="8277a-199">Non-persistent</span></span>

<span data-ttu-id="8277a-200">当使用 Chrome 发送邮件时 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) ，如果不创建邮件端口，Chrome 将为每条消息启动新的本机消息传递主机进程。</span><span class="sxs-lookup"><span data-stu-id="8277a-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span></span> <span data-ttu-id="8277a-201">由主机进程生成的第一条消息将作为对原始请求的响应处理，并将忽略所有其他消息。</span><span class="sxs-lookup"><span data-stu-id="8277a-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span></span>

<span data-ttu-id="8277a-202">在收到每封邮件的响应后，Microsoft Edge 将终止连接。</span><span class="sxs-lookup"><span data-stu-id="8277a-202">Microsoft Edge will terminate the connection after every messages' response has been received.</span></span> <span data-ttu-id="8277a-203">以下代码片段显示与之建立的非持久连接， `AppServiceConnection` 该连接将在收到并存储为后在 UWP 应用内终止 [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) 。</span><span class="sxs-lookup"><span data-stu-id="8277a-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse).</span></span>

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

### <span data-ttu-id="8277a-204">权限</span><span class="sxs-lookup"><span data-stu-id="8277a-204">Permission</span></span>

<span data-ttu-id="8277a-205">为了为 Chrome 和 Microsoft Edge 启用本机消息传递，你需要 `"nativeMessaging"` 在文件中声明权限 `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="8277a-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you'll need to declare the `"nativeMessaging"` permission in you `manifest.json` file.</span></span>


## <span data-ttu-id="8277a-206">应用服务</span><span class="sxs-lookup"><span data-stu-id="8277a-206">App services</span></span>
<span data-ttu-id="8277a-207">本节详细介绍了应用服务对 Microsoft Edge 本机消息性能和内存的影响。</span><span class="sxs-lookup"><span data-stu-id="8277a-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span></span>

### <span data-ttu-id="8277a-208">性能</span><span class="sxs-lookup"><span data-stu-id="8277a-208">Performance</span></span>

<span data-ttu-id="8277a-209">应用服务由调用它们的前台应用 "赞助"，用于本机消息传递目的是 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8277a-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span></span> <span data-ttu-id="8277a-210">这意味着只要运行 Microsoft Edge，应用服务就可以运行。</span><span class="sxs-lookup"><span data-stu-id="8277a-210">This means that app services can run as long as Microsoft Edge is running.</span></span>

<span data-ttu-id="8277a-211">对延迟而言，应用服务使用 "命名管道"，在初始连接后，允许两个应用直接通信。</span><span class="sxs-lookup"><span data-stu-id="8277a-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span></span> <span data-ttu-id="8277a-212">这种通信方式产生较低的延迟。</span><span class="sxs-lookup"><span data-stu-id="8277a-212">This method of communication produces low latency.</span></span> <span data-ttu-id="8277a-213">Cpu 速度较慢的设备将在启动承载应用服务的进程后遇到一些初始延迟 (~ 80ms 以启动某些设备上的后台任务) 。</span><span class="sxs-lookup"><span data-stu-id="8277a-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service (~80ms to startup the background task on some devices).</span></span> <span data-ttu-id="8277a-214">启动后，CPU 设备速度较慢的性能应该很好。</span><span class="sxs-lookup"><span data-stu-id="8277a-214">After start-up, performance on slow CPU devices should be good.</span></span> 


### <span data-ttu-id="8277a-215">内存</span><span class="sxs-lookup"><span data-stu-id="8277a-215">Memory</span></span>
<span data-ttu-id="8277a-216">分配给应用服务的内存已从分配给 Microsoft Edge 的配额中取出。</span><span class="sxs-lookup"><span data-stu-id="8277a-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span></span> <span data-ttu-id="8277a-217">这意味着，如果 Microsoft Edge 启动过多的应用服务，可能会耗尽内存。</span><span class="sxs-lookup"><span data-stu-id="8277a-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span></span> <span data-ttu-id="8277a-218">在应用服务上强制使用常规后台任务内存上限。</span><span class="sxs-lookup"><span data-stu-id="8277a-218">The usual background task memory caps are enforced on app services.</span></span> <span data-ttu-id="8277a-219">例如，在512MB 设备上，应用服务后台任务不能大于16MB。</span><span class="sxs-lookup"><span data-stu-id="8277a-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span></span> <span data-ttu-id="8277a-220">当设备向上扩展时，此号码将上升。</span><span class="sxs-lookup"><span data-stu-id="8277a-220">This number goes up as the devices scale up.</span></span>


## <span data-ttu-id="8277a-221">使用本机消息创建扩展</span><span class="sxs-lookup"><span data-stu-id="8277a-221">Creating an extension with native messaging</span></span>

<span data-ttu-id="8277a-222">为了测试本机消息，你的扩展需要一个程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="8277a-222">In order to test native messaging, your extension needs a Package Family Name.</span></span> <span data-ttu-id="8277a-223">Microsoft Edge 使用此内容确定本机消息主机标识，这意味着你的扩展应打包。</span><span class="sxs-lookup"><span data-stu-id="8277a-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span></span> 


<span data-ttu-id="8277a-224">若要在 Visual Studio 中创建本机消息的扩展，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8277a-224">To create your extension with native messaging in Visual Studio:</span></span>

1. <span data-ttu-id="8277a-225">在 Visual Studio 中创建 UWP 项目。</span><span class="sxs-lookup"><span data-stu-id="8277a-225">Create a UWP project in Visual Studio.</span></span>
2. <span data-ttu-id="8277a-226">[添加 `AppService` 到 UWP 应用](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。</span><span class="sxs-lookup"><span data-stu-id="8277a-226">[Add `AppService` to your UWP app](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>
   - <span data-ttu-id="8277a-227">你可以选择 [配置 `AppService` 为在主应用中托管，](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) 而不是在此位置作为后台任务托管。</span><span class="sxs-lookup"><span data-stu-id="8277a-227">You can optionally [configure `AppService` to be hosted in the main app](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span></span>
3. <span data-ttu-id="8277a-228">构建和测试您的 UWP 项目。</span><span class="sxs-lookup"><span data-stu-id="8277a-228">Build and test your UWP project.</span></span>
   - <span data-ttu-id="8277a-229">你可以选择添加一个 [桌面桥组件](#adding-a-desktop-bridge-component)。</span><span class="sxs-lookup"><span data-stu-id="8277a-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span></span>
4. <span data-ttu-id="8277a-230">创建使用本机消息传递与 UWP 配套应用通信的 Microsoft Edge 扩展。</span><span class="sxs-lookup"><span data-stu-id="8277a-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span></span> <span data-ttu-id="8277a-231">扩展文件可以添加到 `Extension` UWP 项目中指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8277a-231">The extension files can be added into a folder named `Extension` in the UWP project.</span></span> <span data-ttu-id="8277a-232">此文件夹下的所有文件（包括子文件夹）都需要配置其属性，以便 `Build Action=Content` 和 `Copy to Output Directory=Copy Always` 。</span><span class="sxs-lookup"><span data-stu-id="8277a-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span> <span data-ttu-id="8277a-233">请确保 `manifest.json` 也配置了这些属性。</span><span class="sxs-lookup"><span data-stu-id="8277a-233">Make sure `manifest.json` is also configured with these properties.</span></span>
5. <span data-ttu-id="8277a-234">`package.manifest.xml`通过添加以下内容，在项目中修改文件以包括扩展元数据并将其转换为无头应用 `AppListEntry="none"` ：</span><span class="sxs-lookup"><span data-stu-id="8277a-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span></span>

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

6. <span data-ttu-id="8277a-235">`AppService`在本机消息 api 中使用为 UWP 配置的名称。</span><span class="sxs-lookup"><span data-stu-id="8277a-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span></span>
7. <span data-ttu-id="8277a-236">生成并 [部署](#deploying) UWP 项目 (，其中包含可选的桌面桥组件) 。</span><span class="sxs-lookup"><span data-stu-id="8277a-236">Build and [deploy](#deploying) the UWP project (with the optional Desktop Bridge component).</span></span>
8. <span data-ttu-id="8277a-237">在准备好提交应用商店时[打包](#packaging)您的本机消息扩展</span><span class="sxs-lookup"><span data-stu-id="8277a-237">[Package](#packaging) your native messaging extension once it's ready for Store submission</span></span>

> [!NOTE]
> <span data-ttu-id="8277a-238">有关完整本机消息扩展的示例，请参考 " [演示](#demos) " 部分。</span><span class="sxs-lookup"><span data-stu-id="8277a-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span></span>


## <span data-ttu-id="8277a-239">添加桌面桥组件</span><span class="sxs-lookup"><span data-stu-id="8277a-239">Adding a Desktop Bridge component</span></span> 
<span data-ttu-id="8277a-240">如果要将桌面桥组件添加到你的程序包，你需要在 Visual Studio 中创建和生成 Win32 项目。</span><span class="sxs-lookup"><span data-stu-id="8277a-240">If you want to add a Desktop Bridge component to your package, you'll need to create and build your Win32 project in Visual Studio.</span></span> <span data-ttu-id="8277a-241">有关如何将 win32 应用转换为 UWP 的信息，请参阅 [通过桌面桥将应用移植到 Windows 10](/windows/uwp/porting/desktop-to-uwp-root)。</span><span class="sxs-lookup"><span data-stu-id="8277a-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span></span> <span data-ttu-id="8277a-242">在 Visual Studio 中构建后，你可以通过执行以下步骤将 Win32 可执行文件添加到程序包：</span><span class="sxs-lookup"><span data-stu-id="8277a-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span></span>

1. <span data-ttu-id="8277a-243">将 Win32 项目添加到与 UWP 项目相同的解决方案中。</span><span class="sxs-lookup"><span data-stu-id="8277a-243">Add the Win32 project to the same solution as the UWP project.</span></span> 

2. <span data-ttu-id="8277a-244">将 Win32 项目设置为 UWP 项目的依赖项目：</span><span class="sxs-lookup"><span data-stu-id="8277a-244">Set the Win32 project as a dependent project for the UWP project:</span></span>

    ![设置项目相关性](./../media/project-dependencies.PNG)

3. <span data-ttu-id="8277a-246">`Win32`在 UWP 项目中创建一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="8277a-246">Create a `Win32` folder within the UWP project.</span></span> <span data-ttu-id="8277a-247">将项目所需的二进制文件复制 `Win32` 到此文件夹。</span><span class="sxs-lookup"><span data-stu-id="8277a-247">Copy the necessary binaries for the `Win32` project to this folder.</span></span> <span data-ttu-id="8277a-248">配置所有二进制文件的属性，例如 `Build Action=Content` 和 `Copy to Output Directory=Copy Always` 。</span><span class="sxs-lookup"><span data-stu-id="8277a-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>

    ![包含 win32 和 UWP 应用文件的文件夹](./../media/desktop-bridge.png)

4. <span data-ttu-id="8277a-250">修改 UWP 项目文件以使用 PostBuild 事件命令将项目的所有必需的二进制文件复制 `Win32` 到此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8277a-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span></span> <span data-ttu-id="8277a-251">这可确保每次重新生成解决方案时都将更新的二进制文件复制到文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8277a-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span></span>

    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```


5. <span data-ttu-id="8277a-252">`package.manifest.xml`通过将元素添加 `<desktop:Extension>` 到元素进行修改 `<Extensions>` ：</span><span class="sxs-lookup"><span data-stu-id="8277a-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span></span>

    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```

## <span data-ttu-id="8277a-253">部署</span><span class="sxs-lookup"><span data-stu-id="8277a-253">Deploying</span></span>
<span data-ttu-id="8277a-254">配置 UWP 项目 (和可选 Win32 项目) 如上所述，准备好使用 Visual Studio 部署解决方案。</span><span class="sxs-lookup"><span data-stu-id="8277a-254">Once you have configured your UWP project (and optionally Win32 project) as outlined above, you are ready to deploy the solution using Visual Studio.</span></span>

![生成进程内项目](../media/native-message-uwp-debug.PNG)

<span data-ttu-id="8277a-256">正确部署解决方案后，你应该会在 Microsoft Edge 中看到你的扩展。</span><span class="sxs-lookup"><span data-stu-id="8277a-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span></span>

![在 Microsoft Edge 中显示的扩展](../media/secureextension.png)

## <span data-ttu-id="8277a-258">包装</span><span class="sxs-lookup"><span data-stu-id="8277a-258">Packaging</span></span>

> [!NOTE]
> <span data-ttu-id="8277a-259">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。</span><span class="sxs-lookup"><span data-stu-id="8277a-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="8277a-260">[通过你](https://aka.ms/extension-request) 的请求成为 Microsoft Store 的一部分，我们将考虑你的未来更新。</span><span class="sxs-lookup"><span data-stu-id="8277a-260">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>


<span data-ttu-id="8277a-261">你可以使用内置 Visual Studio 功能生成用于提交到 Windows 开发人员中心的应用商店包：</span><span class="sxs-lookup"><span data-stu-id="8277a-261">You can generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span></span>


![创建存储包](../media/create-store-package.PNG)

## <span data-ttu-id="8277a-263">调试</span><span class="sxs-lookup"><span data-stu-id="8277a-263">Debugging</span></span>
<span data-ttu-id="8277a-264">根据要测试的组件，调试说明会有所不同：</span><span class="sxs-lookup"><span data-stu-id="8277a-264">The instructions for debugging vary depending on which component you want to test out:</span></span>

### <span data-ttu-id="8277a-265">调试扩展</span><span class="sxs-lookup"><span data-stu-id="8277a-265">Debugging the extension</span></span>
<span data-ttu-id="8277a-266">部署解决方案后，将在 Microsoft Edge 中安装扩展。</span><span class="sxs-lookup"><span data-stu-id="8277a-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span></span> <span data-ttu-id="8277a-267">有关如何调试扩展的信息，请查看 [调试](./debugging-extensions.md) 指南。</span><span class="sxs-lookup"><span data-stu-id="8277a-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span></span>


### <span data-ttu-id="8277a-268">调试 UWP 应用</span><span class="sxs-lookup"><span data-stu-id="8277a-268">Debugging the UWP app</span></span>
<span data-ttu-id="8277a-269">当扩展尝试使用 [本机消息 api](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)连接时，UWP 应用将启动。</span><span class="sxs-lookup"><span data-stu-id="8277a-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="8277a-270">只有在进程启动后才需要调试 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="8277a-270">You'll need to debug the UWP app only once the process starts.</span></span> <span data-ttu-id="8277a-271">这可以通过项目的属性页面进行配置：</span><span class="sxs-lookup"><span data-stu-id="8277a-271">This can be configured via the project's Property page:</span></span>

1.  <span data-ttu-id="8277a-272">在 Visual Studio 中，右键单击你的 UWP 应用项目</span><span class="sxs-lookup"><span data-stu-id="8277a-272">In Visual Studio, right click your UWP app project</span></span>
2.  <span data-ttu-id="8277a-273">选择属性</span><span class="sxs-lookup"><span data-stu-id="8277a-273">Select Properties</span></span>
3.  <span data-ttu-id="8277a-274">选中 "不启动，但在开始时调试我的代码"</span><span class="sxs-lookup"><span data-stu-id="8277a-274">Check "Do not launch, but debug my code when it starts"</span></span>

    ![选择 "不启动" 框](../media/native-message-do-not-launch.png)

<span data-ttu-id="8277a-276">在 Visual Studio 中，你现在可以在要调试的代码中设置断点，然后按 F5 启动调试器。</span><span class="sxs-lookup"><span data-stu-id="8277a-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span></span> <span data-ttu-id="8277a-277">与扩展连接以连接到 UWP 应用后，Visual Studio 将自动附加到该进程。</span><span class="sxs-lookup"><span data-stu-id="8277a-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span></span>


### <span data-ttu-id="8277a-278">调试桌面桥</span><span class="sxs-lookup"><span data-stu-id="8277a-278">Debugging the Desktop Bridge</span></span>
<span data-ttu-id="8277a-279">尽管有多种方法可 [用于调试桌面桥](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) (已转换的 Win32 应用) ，但唯一适用于这种情况的方法是 PLMDebug 选项。</span><span class="sxs-lookup"><span data-stu-id="8277a-279">Even though there are various [methods for debugging a Desktop Bridge](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) (converted Win32 app), the only one applicable for this scenarios is the PLMDebug option.</span></span> <span data-ttu-id="8277a-280">你还可以将调试代码添加到启动函数以在特定时间执行等待，从而允许你将 Visual Studio 附加到进程。</span><span class="sxs-lookup"><span data-stu-id="8277a-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span></span>
