---
description: 了解如何使用本机消息传递让扩展与配套 UWP 应用进行通信。
title: 本机消息传递|扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 本机， 消息传递， uwp
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9a306055b8f86b92aa5c3e7cd6de44f2386307d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399356"
---
# <a name="native-messaging-in-microsoft-edge"></a><span data-ttu-id="9d86c-104">Microsoft Edge 中的本机消息传递</span><span class="sxs-lookup"><span data-stu-id="9d86c-104">Native messaging in Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <a name="native-messaging-architecture-overview"></a><span data-ttu-id="9d86c-105">本机邮件体系结构概述</span><span class="sxs-lookup"><span data-stu-id="9d86c-105">Native messaging architecture overview</span></span>  

<span data-ttu-id="9d86c-106">借助 Windows 10 创意者更新，Microsoft Edge 扩展可以使用本机消息传递与配套通用 Windows 平台 \ (UWP\) 应用进行通信。</span><span class="sxs-lookup"><span data-stu-id="9d86c-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform \(UWP\) app.</span></span>  <span data-ttu-id="9d86c-107">在高级别上，Microsoft Edge 扩展对本机消息传递使用与 Chrome 和 Firefox 扩展相同的 API。</span><span class="sxs-lookup"><span data-stu-id="9d86c-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span></span>  <span data-ttu-id="9d86c-108">但是，本机消息传递主机将需要使用通用 Windows 平台实现。</span><span class="sxs-lookup"><span data-stu-id="9d86c-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span></span>  

> [!NOTE]
> <span data-ttu-id="9d86c-109">\ (AppService\) 连接到 UWP 应用的方法是支持在 Microsoft Edge 扩展和本机组件之间启用通信的唯一机制。</span><span class="sxs-lookup"><span data-stu-id="9d86c-109">The method outlined below \(connecting to a UWP app via AppService\) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span></span>  <span data-ttu-id="9d86c-110">请参阅本指南的"添加 [桌面桥](#adding-a-desktop-bridge-component) 组件"部分，详细了解如何启用与旧版 Win32 组件的通信。</span><span class="sxs-lookup"><span data-stu-id="9d86c-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span></span>  

<span data-ttu-id="9d86c-111">Microsoft Edge 中的本机消息传递体系结构利用现有 API 作为基础进程间通信 [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) \ (IPC\) 基础结构。</span><span class="sxs-lookup"><span data-stu-id="9d86c-111">The native messaging architecture in Microsoft Edge leverages the existing [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) API as the underlying inter-process communication \(IPC\) infrastructure.</span></span>  <span data-ttu-id="9d86c-112">UWP 应用使用 `AppService` API 相互通信。</span><span class="sxs-lookup"><span data-stu-id="9d86c-112">UWP apps use the `AppService` API to communicate with one another.</span></span>  <span data-ttu-id="9d86c-113">因此，Microsoft Edge 扩展现在能够与 UWP 应用进行通信。</span><span class="sxs-lookup"><span data-stu-id="9d86c-113">Because of this, Microsoft Edge extensions are now able to communicate with UWP apps.</span></span>  

![本机消息传递体系结构](../media/native-messaging-architecture.png)  

### <a name="when-and-when-not-to-use-native-messaging"></a><span data-ttu-id="9d86c-115">何时以及何时不使用本机消息传递</span><span class="sxs-lookup"><span data-stu-id="9d86c-115">When and when not to use native messaging</span></span>  

<span data-ttu-id="9d86c-116">本机消息传递会向扩展添加新层。</span><span class="sxs-lookup"><span data-stu-id="9d86c-116">Native messaging adds a whole new layer to your extension.</span></span>  <span data-ttu-id="9d86c-117">通过为扩展实现 UWP 配套应用，你可以使用以下可能性：</span><span class="sxs-lookup"><span data-stu-id="9d86c-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span></span>  

*   <span data-ttu-id="9d86c-118">将数据 \ (例如凭据\) UWP 应用同步。</span><span class="sxs-lookup"><span data-stu-id="9d86c-118">Synchronize data \(for example credentials\) with a companion UWP app.</span></span>  
*   <span data-ttu-id="9d86c-119">实现 Web API 中不可用的更强大的加密/解密算法。</span><span class="sxs-lookup"><span data-stu-id="9d86c-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span></span>  
*   <span data-ttu-id="9d86c-120">无法通过 Web API 访问的资源，例如硬件或 USB 设备</span><span class="sxs-lookup"><span data-stu-id="9d86c-120">Access resources that are not accessible through web APIs, for example hardware or USB devices</span></span>  

<span data-ttu-id="9d86c-121">在某些情况下，由于安全或策略限制，不应使用本机邮件：</span><span class="sxs-lookup"><span data-stu-id="9d86c-121">There are a few instances where native messaging should not be used due to security or policy restrictions:</span></span>  

*   <span data-ttu-id="9d86c-122">修改 Microsoft Edge 或 Windows 中的用户设置，例如更改默认浏览器或搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="9d86c-122">Modifying user settings in either Microsoft Edge or Windows, for example changing the default browser or search provider.</span></span>  
*   <span data-ttu-id="9d86c-123">违反应用和扩展的 Microsoft Store 策略的操作。</span><span class="sxs-lookup"><span data-stu-id="9d86c-123">Actions that violate Microsoft Store policies for both apps and extensions.</span></span>  
*   <span data-ttu-id="9d86c-124">通过本机邮件主机将数据传输到远程终结点。</span><span class="sxs-lookup"><span data-stu-id="9d86c-124">Transferring data to remote endpoint via native message host.</span></span>  
*   <span data-ttu-id="9d86c-125">允许其他应用下载更改扩展行为的内容。</span><span class="sxs-lookup"><span data-stu-id="9d86c-125">Allowing other apps to download content that changes extension behavior.</span></span>  

## <a name="demos"></a><span data-ttu-id="9d86c-126">演示</span><span class="sxs-lookup"><span data-stu-id="9d86c-126">Demos</span></span>  

<span data-ttu-id="9d86c-127">若要了解同时具有配套 UWP 应用和桌面桥的 Microsoft Edge 本机消息传递扩展的外观，请查看 GitHub 上的 [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) 和 [DigitalSigning (C++) ](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) 示例。</span><span class="sxs-lookup"><span data-stu-id="9d86c-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span></span>  

### <a name="how-it-works"></a><span data-ttu-id="9d86c-128">工作原理</span><span class="sxs-lookup"><span data-stu-id="9d86c-128">How it works</span></span>  

<span data-ttu-id="9d86c-129">此示例的 Microsoft Edge 扩展组件使用其内容脚本检测用户何时键入应加密的信息。</span><span class="sxs-lookup"><span data-stu-id="9d86c-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span></span>  <span data-ttu-id="9d86c-130">扩展通过本机消息将此功能传达给桌面桥组件。</span><span class="sxs-lookup"><span data-stu-id="9d86c-130">The extension communicates this to the Desktop Bridge component via native messaging.</span></span>  <span data-ttu-id="9d86c-131">当用户准备好提交数据时，扩展将返回一个加密值返回到网站。</span><span class="sxs-lookup"><span data-stu-id="9d86c-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span></span>  

> [!NOTE]
> <span data-ttu-id="9d86c-132">此示例仅适用于使用自定义事件与扩展的内容脚本进行通信的网页。</span><span class="sxs-lookup"><span data-stu-id="9d86c-132">This sample will only work on a webpage that uses custom events to communicate with the content script of the extension.</span></span>  <span data-ttu-id="9d86c-133">示例文件夹包含一个 [.html 文件](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) ，用于测试扩展名。</span><span class="sxs-lookup"><span data-stu-id="9d86c-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span></span>  

<span data-ttu-id="9d86c-134">此示例中，UWP 应用用于将响应从桌面桥传递到 Microsoft Edge，然后通过回调将响应发送到 Microsoft Edge 扩展。</span><span class="sxs-lookup"><span data-stu-id="9d86c-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span></span>  <span data-ttu-id="9d86c-135">虽然此示例在主应用中运行本机消息传递主机，但它也可以作为后台任务运行。</span><span class="sxs-lookup"><span data-stu-id="9d86c-135">While this example has the native messaging host run in the main app, it is also able to run as a background task.</span></span>  <span data-ttu-id="9d86c-136">在两者之间切换需要编辑扩展的后台脚本，将字符串内部更改 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` 为 `"NativeMessagingHostOutOfProcess"` 。</span><span class="sxs-lookup"><span data-stu-id="9d86c-136">Switching between the two requires editing the background script of the extension, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span></span>  

## <a name="chrome-vs-microsoft-edge-implementation"></a><span data-ttu-id="9d86c-137">Chrome 与 Microsoft Edge 实现</span><span class="sxs-lookup"><span data-stu-id="9d86c-137">Chrome vs Microsoft Edge implementation</span></span>  

<span data-ttu-id="9d86c-138">尽管 Chrome 使用消息传递 API 作为扩展与应用进行通信的路由，但 Microsoft Edge 利用现在使 Microsoft Edge 扩展和 UWP 应用能够进行通信的 [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) API。</span><span class="sxs-lookup"><span data-stu-id="9d86c-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span></span>  

<span data-ttu-id="9d86c-139">本部分详细介绍 Chrome 和 Microsoft Edge 如何处理本机消息传递实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="9d86c-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span></span>  

### <a name="registration-and-host-manifest"></a><span data-ttu-id="9d86c-140">注册和主机清单</span><span class="sxs-lookup"><span data-stu-id="9d86c-140">Registration and host manifest</span></span>  

<span data-ttu-id="9d86c-141">为了让应用被扩展识别为本机消息传递主机，需要注册应用。</span><span class="sxs-lookup"><span data-stu-id="9d86c-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span></span>  

<span data-ttu-id="9d86c-142">对于 [Chrome 本机邮件](https://developer.chrome.com/extensions/nativeMessaging) 主机注册，你的应用需要在定义本机邮件主机配置的 Windows 文件系统中的任何位置安装清单文件。</span><span class="sxs-lookup"><span data-stu-id="9d86c-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span></span>  

<span data-ttu-id="9d86c-143">以下 JSON 是应用程序设置配置文件：</span><span class="sxs-lookup"><span data-stu-id="9d86c-143">The following JSON is an example of settings for the config file:</span></span>  

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

<span data-ttu-id="9d86c-144">若要安装此文件，应用需要：</span><span class="sxs-lookup"><span data-stu-id="9d86c-144">To install this file, the app would need to:</span></span>  

1.  <span data-ttu-id="9d86c-145">在定义主机配置的注册表中的预定义位置注册清单文件：</span><span class="sxs-lookup"><span data-stu-id="9d86c-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span></span>  
    *   `HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`  
        
        <span data-ttu-id="9d86c-146">or</span><span class="sxs-lookup"><span data-stu-id="9d86c-146">or</span></span>  
    *   `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`  
        
1.  <span data-ttu-id="9d86c-147">将键的默认值设置为清单文件的完整路径，例如</span><span class="sxs-lookup"><span data-stu-id="9d86c-147">Set the default value of that key to the full path to the manifest file, for example</span></span> `[HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"`  

<span data-ttu-id="9d86c-148">对于 Microsoft Edge，若要注册 \ (本机消息传递主机\) 必须在扩展相同的程序包中包括 UWP 配套应用，在项目文件中指定 [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) [AppService](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)扩展。 `Package.appxmanifest`</span><span class="sxs-lookup"><span data-stu-id="9d86c-148">For Microsoft Edge, in order to register an [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) \(native messaging host\) you must include the UWP companion app in the same package as your extension and specify the [AppService extension](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in the `Package.appxmanifest` file of your project.</span></span>  <span data-ttu-id="9d86c-149">And `EntryPoint` `Name` 属性可能由你配置：</span><span class="sxs-lookup"><span data-stu-id="9d86c-149">The `EntryPoint` and `Name` attributes may be configured by you:</span></span>  

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

<span data-ttu-id="9d86c-150">还需要设置允许哪些扩展连接到服务。</span><span class="sxs-lookup"><span data-stu-id="9d86c-150">You also need to set which extensions are allowed to connect to the service.</span></span>  <span data-ttu-id="9d86c-151">由于 Microsoft Edge 在其 AppxManifest 中没有等效的清单属性，因此，这需要由 UWP 应用在运行时确定 `"allowed_origins"` 和强制执行。</span><span class="sxs-lookup"><span data-stu-id="9d86c-151">Because Microsoft Edge does not have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span></span>  <span data-ttu-id="9d86c-152">由于 Microsoft Edge 代表扩展建立连接，因此应用会查找呼叫者的程序包系列名称，以确定 Microsoft Edge 是否正在连接扩展以控制呼叫者或对呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d86c-152">Since Microsoft Edge establishes the connection on behalf of the extension, the app looks up the Package Family Name of the caller to determine if extension is being connected by Microsoft Edge to control or authenticate the caller.</span></span>  <span data-ttu-id="9d86c-153">例如</span><span class="sxs-lookup"><span data-stu-id="9d86c-153">For example</span></span>   

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

### <a name="message-sending"></a><span data-ttu-id="9d86c-154">邮件发送</span><span class="sxs-lookup"><span data-stu-id="9d86c-154">Message sending</span></span>  

<span data-ttu-id="9d86c-155">若要使应用和扩展相互通信，需要向它们发送和发送消息。</span><span class="sxs-lookup"><span data-stu-id="9d86c-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span></span>  

<span data-ttu-id="9d86c-156">Chrome 扩展使用 API 启动消息，以使用非永久性通道向本机主机 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 传递消息。</span><span class="sxs-lookup"><span data-stu-id="9d86c-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span></span>  

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```  

<span data-ttu-id="9d86c-157">第一个参数是本机主机的名称，Chrome 在注册表中查找清单。</span><span class="sxs-lookup"><span data-stu-id="9d86c-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span></span>  <span data-ttu-id="9d86c-158">清单指定 Chrome 将在沙盒中启动的 .exe，邮件使用 std i/o 发送。</span><span class="sxs-lookup"><span data-stu-id="9d86c-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span></span>  
<span data-ttu-id="9d86c-159">扩展还使用 API 建立永久性通道，该 API 将本机主机的名称作为 `runtime.connectNative` 唯一参数。</span><span class="sxs-lookup"><span data-stu-id="9d86c-159">Extensions also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span></span>  

<span data-ttu-id="9d86c-160">Microsoft Edge 使用与 Chrome 中的本机消息传递 API 相同的构造，以允许 Microsoft Edge 扩展指定要连接到的应用服务。</span><span class="sxs-lookup"><span data-stu-id="9d86c-160">Microsoft Edge uses the same construct as the native messaging API in Chrome to allow Microsoft Edge extensions to specify which app service to connect to.</span></span>  <span data-ttu-id="9d86c-161">第一个参数 `runtime.sendNativeMessage` 指定应用服务名称。</span><span class="sxs-lookup"><span data-stu-id="9d86c-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span></span>  <span data-ttu-id="9d86c-162">在" [注册和主机清单"](#registration-and-host-manifest) 部分，这是 `"com.microsoft.inventory"` 。</span><span class="sxs-lookup"><span data-stu-id="9d86c-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span></span>  <span data-ttu-id="9d86c-163">Microsoft Edge 扩展平台将本机消息传递主机限制为打包在扩展相同的 AppX 中的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="9d86c-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span></span>  <span data-ttu-id="9d86c-164">这可以减少与恶意攻击相关的任何安全风险，恶意攻击尝试通过篡改清单条目将 Microsoft Edge 连接到另一个程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="9d86c-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span></span>  

<span data-ttu-id="9d86c-165">这意味着，除了 API 中指定的名称之外，Microsoft Edge 还将使用与扩展相同的程序包系列名称来唯一标识 `AppService` 应用服务的提供程序。</span><span class="sxs-lookup"><span data-stu-id="9d86c-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span></span>  

> [!NOTE]
> <span data-ttu-id="9d86c-166">这将不会由 Microsoft Edge 扩展服务器[轻松Toolkit。](./porting-chrome-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="9d86c-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span></span>  <span data-ttu-id="9d86c-167">指定权限的任何 `"nativeMessaging"` 扩展将被标记为需要手动转换此组件。</span><span class="sxs-lookup"><span data-stu-id="9d86c-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span></span>  

### <a name="communication-protocol"></a><span data-ttu-id="9d86c-168">通信协议</span><span class="sxs-lookup"><span data-stu-id="9d86c-168">Communication protocol</span></span>  

<span data-ttu-id="9d86c-169">本机邮件的通信协议确定邮件在发送前的格式。</span><span class="sxs-lookup"><span data-stu-id="9d86c-169">Communication protocol for native messaging determines how messages are formatted before sending.</span></span>  

<span data-ttu-id="9d86c-170">Chrome 在单独的进程中启动每个本机消息传递主机，然后使用标准输入和标准输出与主机进行通信。</span><span class="sxs-lookup"><span data-stu-id="9d86c-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span></span>  <span data-ttu-id="9d86c-171">相同的格式用于向两个方向发送邮件：每个邮件都使用 JSON、UTF-8 编码进行序列化，并且以本机字节顺序以 32 位消息长度为前。</span><span class="sxs-lookup"><span data-stu-id="9d86c-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span></span>  

<span data-ttu-id="9d86c-172">对于 Microsoft Edge，实现应用服务的后台任务/主应用由平台启动。</span><span class="sxs-lookup"><span data-stu-id="9d86c-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span></span>  <span data-ttu-id="9d86c-173">启动时， `Run` 将调用后台任务的方法：</span><span class="sxs-lookup"><span data-stu-id="9d86c-173">On startup, the `Run` method of the background task is invoked:</span></span>  

```csharp
public void Run(IBackgroundTaskInstance taskInstance)    
{
    this.backgroundTaskDeferral = taskInstance.GetDeferral();
    // Get a deferral so that the service is not stopped and ended.
    taskInstance.Canceled += OnTaskCanceled;
    // Associate a cancellation handler with the background task.
    // Retrieve the app service connection and set up a listener for incoming app service requests.
    var details = taskInstance.TriggerDetails as AppServiceTriggerDetails;
    appServiceconnection = details.AppServiceConnection;
    appServiceconnection.RequestReceived += OnRequestReceived;
}
```  

<span data-ttu-id="9d86c-174">当你的扩展向 UWP 应用发送消息时， [`onRequestReceived`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) 将引发该事件。</span><span class="sxs-lookup"><span data-stu-id="9d86c-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) event will be raised.</span></span>  <span data-ttu-id="9d86c-175">然后，此 JSON 格式的邮件将字符串化为对象的第一个 KeyValue [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) 对。</span><span class="sxs-lookup"><span data-stu-id="9d86c-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) object.</span></span>  <span data-ttu-id="9d86c-176">:</span><span class="sxs-lookup"><span data-stu-id="9d86c-176">:</span></span>  

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```  

<span data-ttu-id="9d86c-177">当你的 UWP 应用将响应发送回你的扩展时，将向 [`KeyValuePair`](/dotnet/api/system.collections.generic.keyvaluepair-2?view=netcore-3.1&preserve-view=true) 对象中添加 `ValueSet` 一个。</span><span class="sxs-lookup"><span data-stu-id="9d86c-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](/dotnet/api/system.collections.generic.keyvaluepair-2?view=netcore-3.1&preserve-view=true) will be added to the `ValueSet` object.</span></span>  <span data-ttu-id="9d86c-178">Microsoft `Key` Edge 将忽略该属性，但 `Value` 该属性将包含有效的 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="9d86c-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span></span>  

### <a name="callback"></a><span data-ttu-id="9d86c-179">回调</span><span class="sxs-lookup"><span data-stu-id="9d86c-179">Callback</span></span>  

<span data-ttu-id="9d86c-180">对于回调，Chrome [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 使用允许回调函数处理发送消息的任何异步响应。</span><span class="sxs-lookup"><span data-stu-id="9d86c-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span></span>  

<span data-ttu-id="9d86c-181">Microsoft Edge [`SendResponseAsync`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) 使用对象 [`AppServiceRequest`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) 的方法让应用将对象 [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) 发送回扩展。</span><span class="sxs-lookup"><span data-stu-id="9d86c-181">Microsoft Edge uses the [`SendResponseAsync`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) method  of the [`AppServiceRequest`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) object to let the app send a [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) object back to the extension.</span></span>  

### <a name="message-size-limit"></a><span data-ttu-id="9d86c-182">邮件大小限制</span><span class="sxs-lookup"><span data-stu-id="9d86c-182">Message size limit</span></span>  

<span data-ttu-id="9d86c-183">在扩展与应用之间来回发送的邮件对 Chrome 和 Microsoft Edge 有不同的邮件大小限制。</span><span class="sxs-lookup"><span data-stu-id="9d86c-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span></span>  

<span data-ttu-id="9d86c-184">Chrome 具有以下邮件大小限制：</span><span class="sxs-lookup"><span data-stu-id="9d86c-184">Chrome has the following message size limitations:</span></span>  

*   <span data-ttu-id="9d86c-185">来自本机邮件主机的单封邮件限制：1 MB</span><span class="sxs-lookup"><span data-stu-id="9d86c-185">Single message limit from native messaging host:  1 MB</span></span>  
*   <span data-ttu-id="9d86c-186">发送到本机邮件主机的单个邮件限制：4 GB</span><span class="sxs-lookup"><span data-stu-id="9d86c-186">Single message limit sent to native messaging host:  4 GB</span></span>  

<span data-ttu-id="9d86c-187">对于 Microsoft Edge，虽然对邮件大小 `AppService` 没有限制 \ (依赖于内存\) ，但 Microsoft Edge 通过限制以下邮件大小来自我保护，防止本机应用行为不正常：</span><span class="sxs-lookup"><span data-stu-id="9d86c-187">For Microsoft Edge, while `AppService` has no limit on message size \(dependent on memory\), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span></span>  

*   <span data-ttu-id="9d86c-188">从 UWP 应用到扩展的单个邮件限制：1 MB</span><span class="sxs-lookup"><span data-stu-id="9d86c-188">Single message limit from UWP app to extension: 1 MB</span></span>  
*   <span data-ttu-id="9d86c-189">从扩展到 UWP 应用的单个邮件限制：100 MB</span><span class="sxs-lookup"><span data-stu-id="9d86c-189">Single message limit from extension to UWP app: 100 MB</span></span>  

### <a name="native-messaging-connections"></a><span data-ttu-id="9d86c-190">本机消息传递连接</span><span class="sxs-lookup"><span data-stu-id="9d86c-190">Native messaging connections</span></span>  

<span data-ttu-id="9d86c-191">本机消息传递有两种类型的连接;持久性和非永久性。</span><span class="sxs-lookup"><span data-stu-id="9d86c-191">There are two types of connections for native messaging; persistent and non-persistent.</span></span>  
<span data-ttu-id="9d86c-192">永久性 **连接** 是一种在端口被销毁之前一直运行的连接。</span><span class="sxs-lookup"><span data-stu-id="9d86c-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span></span>  <span data-ttu-id="9d86c-193">非 **永久性** 连接是一个连接，一次打开一封邮件，在传递后关闭。</span><span class="sxs-lookup"><span data-stu-id="9d86c-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span></span>  

#### <a name="persistent"></a><span data-ttu-id="9d86c-194">永久性</span><span class="sxs-lookup"><span data-stu-id="9d86c-194">Persistent</span></span>  

<span data-ttu-id="9d86c-195">对于 Chrome，通过使用 创建消息端口来建立永久性连接 [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。</span><span class="sxs-lookup"><span data-stu-id="9d86c-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span>  <span data-ttu-id="9d86c-196">创建端口后，Chrome 将启动本机邮件主机进程，该进程将一直运行，直到其损坏的端口。</span><span class="sxs-lookup"><span data-stu-id="9d86c-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span></span>  

<span data-ttu-id="9d86c-197">对于 Microsoft Edge，使用创建消息端口后，Microsoft Edge 将启动该端口并保持其运行， `runtime.connectNative` [`AppServiceConnection`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) 直到该端口被销毁。</span><span class="sxs-lookup"><span data-stu-id="9d86c-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) and keeps it running until the port is destroyed.</span></span>  <span data-ttu-id="9d86c-198">以下代码段显示了如何在 UWP 应用中建立永久性连接。</span><span class="sxs-lookup"><span data-stu-id="9d86c-198">The following snippet shows how a persistent connection is established from within a UWP app.</span></span>  

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```  

#### <a name="non-persistent"></a><span data-ttu-id="9d86c-199">非永久性</span><span class="sxs-lookup"><span data-stu-id="9d86c-199">Non-persistent</span></span>  

<span data-ttu-id="9d86c-200">在 Chrome 中使用发送邮件时，无需创建消息端口，Chrome 会针对每封邮件启动 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 一个新的本机邮件主机进程。</span><span class="sxs-lookup"><span data-stu-id="9d86c-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span></span>  <span data-ttu-id="9d86c-201">主机进程生成的第一封邮件将作为对原始请求的响应进行处理，在忽略后处理所有其他消息。</span><span class="sxs-lookup"><span data-stu-id="9d86c-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span></span>  

<span data-ttu-id="9d86c-202">收到每条消息的每个响应后，Microsoft Edge 将停止并结束连接。</span><span class="sxs-lookup"><span data-stu-id="9d86c-202">Microsoft Edge stops and ends the connection after every response to each message has been received.</span></span>  <span data-ttu-id="9d86c-203">以下代码段显示了建立的非永久性连接，该连接将在收到请求并存储为一个请求后在 `AppServiceConnection` UWP 应用中终止 [`AppServiceResponse`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceResponse?view=winrt-19041&preserve-view=true) 。</span><span class="sxs-lookup"><span data-stu-id="9d86c-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceResponse?view=winrt-19041&preserve-view=true).</span></span>  

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

### <a name="permission"></a><span data-ttu-id="9d86c-204">权限</span><span class="sxs-lookup"><span data-stu-id="9d86c-204">Permission</span></span>  

<span data-ttu-id="9d86c-205">为了允许本机消息传递与扩展一同使用，对于 Chrome 和 Microsoft Edge，你必须在文件中 `"nativeMessaging"` 声明 `manifest.json` 权限。</span><span class="sxs-lookup"><span data-stu-id="9d86c-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you must declare the `"nativeMessaging"` permission in you `manifest.json` file.</span></span>  

## <a name="app-services"></a><span data-ttu-id="9d86c-206">应用服务</span><span class="sxs-lookup"><span data-stu-id="9d86c-206">App services</span></span>  

<span data-ttu-id="9d86c-207">本部分详细介绍应用服务对 Microsoft Edge 本机邮件性能和内存的影响。</span><span class="sxs-lookup"><span data-stu-id="9d86c-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span></span>  

### <a name="performance"></a><span data-ttu-id="9d86c-208">性能</span><span class="sxs-lookup"><span data-stu-id="9d86c-208">Performance</span></span>  

<span data-ttu-id="9d86c-209">应用服务由前台应用"赞助"，前台应用出于本机消息传递目的调用它们，即 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="9d86c-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span></span>  <span data-ttu-id="9d86c-210">这意味着，只要 Microsoft Edge 正在运行，应用服务就可以运行。</span><span class="sxs-lookup"><span data-stu-id="9d86c-210">This means that app services can run as long as Microsoft Edge is running.</span></span>  

<span data-ttu-id="9d86c-211">对于延迟，应用服务使用命名管道，在初始连接后，允许两个应用直接通信。</span><span class="sxs-lookup"><span data-stu-id="9d86c-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span></span>  <span data-ttu-id="9d86c-212">这种通信方法会产生低延迟。</span><span class="sxs-lookup"><span data-stu-id="9d86c-212">This method of communication produces low latency.</span></span>  <span data-ttu-id="9d86c-213">在启动托管应用服务 \ (~80 毫秒以在某些设备上启动后台任务的过程后，CPU 较慢的设备将遇到一些初始延迟) 。</span><span class="sxs-lookup"><span data-stu-id="9d86c-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service \(~80ms to startup the background task on some devices\).</span></span>  <span data-ttu-id="9d86c-214">启动后，较慢的 CPU 设备的性能应该良好。</span><span class="sxs-lookup"><span data-stu-id="9d86c-214">After start-up, performance on slow CPU devices should be good.</span></span>  

### <a name="memory"></a><span data-ttu-id="9d86c-215">内存</span><span class="sxs-lookup"><span data-stu-id="9d86c-215">Memory</span></span>  

<span data-ttu-id="9d86c-216">分配给应用服务的内存将超出分配给 Microsoft Edge 的配额。</span><span class="sxs-lookup"><span data-stu-id="9d86c-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span></span>  <span data-ttu-id="9d86c-217">这意味着，如果 Microsoft Edge 启动的应用服务过多，则它们可能会用完内存。</span><span class="sxs-lookup"><span data-stu-id="9d86c-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span></span>  <span data-ttu-id="9d86c-218">常见的后台任务内存上限在应用服务上强制执行。</span><span class="sxs-lookup"><span data-stu-id="9d86c-218">The usual background task memory caps are enforced on app services.</span></span>  <span data-ttu-id="9d86c-219">例如，在 512MB 设备上，应用服务后台任务不能大于 16MB。</span><span class="sxs-lookup"><span data-stu-id="9d86c-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span></span>  <span data-ttu-id="9d86c-220">当设备向上扩展时，此数字会上升。</span><span class="sxs-lookup"><span data-stu-id="9d86c-220">This number goes up as the devices scale up.</span></span>  

## <a name="creating-an-extension-with-native-messaging"></a><span data-ttu-id="9d86c-221">使用本机消息传递创建扩展</span><span class="sxs-lookup"><span data-stu-id="9d86c-221">Creating an extension with native messaging</span></span>  

<span data-ttu-id="9d86c-222">为了测试本机消息，扩展需要程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="9d86c-222">In order to test native messaging, your extension needs a Package Family Name.</span></span>  <span data-ttu-id="9d86c-223">Microsoft Edge 使用此标识来确定本机邮件主机标识，这意味着应打包扩展。</span><span class="sxs-lookup"><span data-stu-id="9d86c-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span></span>  

<span data-ttu-id="9d86c-224">若要在应用程序内使用本机消息传递创建扩展Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="9d86c-224">To create your extension with native messaging in Visual Studio:</span></span>  

1.  <span data-ttu-id="9d86c-225">在项目中创建 UWP Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="9d86c-225">Create a UWP project in Visual Studio.</span></span>  
1.  <span data-ttu-id="9d86c-226">[添加到 `AppService` 你的 UWP 应用](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。</span><span class="sxs-lookup"><span data-stu-id="9d86c-226">[Add `AppService` to your UWP app](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>  
    *   <span data-ttu-id="9d86c-227">此时， [可以选择 `AppService` ](/windows/uwp/launch-resume/convert-app-service-in-process) 配置为托管在主应用中，而不是后台任务。</span><span class="sxs-lookup"><span data-stu-id="9d86c-227">You can optionally [configure `AppService` to be hosted in the main app](/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span></span>  
1.  <span data-ttu-id="9d86c-228">生成和测试 UWP 项目。</span><span class="sxs-lookup"><span data-stu-id="9d86c-228">Build and test your UWP project.</span></span>  
    *   <span data-ttu-id="9d86c-229">可以选择添加桌面 [桥组件](#adding-a-desktop-bridge-component)。</span><span class="sxs-lookup"><span data-stu-id="9d86c-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span></span>  
1.  <span data-ttu-id="9d86c-230">创建使用本机消息传递与 UWP 配套应用进行通信的 Microsoft Edge 扩展。</span><span class="sxs-lookup"><span data-stu-id="9d86c-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span></span>  <span data-ttu-id="9d86c-231">扩展文件可以添加到 `Extension` UWP 项目中命名的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9d86c-231">The extension files can be added into a folder named `Extension` in the UWP project.</span></span>  <span data-ttu-id="9d86c-232">此文件夹下的所有文件（包括子文件夹）都需要配置其属性，这样和 `Build Action=Content` `Copy to Output Directory=Copy Always` 。</span><span class="sxs-lookup"><span data-stu-id="9d86c-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>  <span data-ttu-id="9d86c-233">请确保 `manifest.json` 还配置了这些属性。</span><span class="sxs-lookup"><span data-stu-id="9d86c-233">Make sure `manifest.json` is also configured with these properties.</span></span>  
1.  <span data-ttu-id="9d86c-234">修改 `package.manifest.xml` 项目中的文件以包含扩展元数据，并添加以下代码将其转换为无头应用 `AppListEntry="none"` ：</span><span class="sxs-lookup"><span data-stu-id="9d86c-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span></span>  
    
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
    
1.  <span data-ttu-id="9d86c-235">使用 `AppService` 本机消息 API 中为 UWP 配置的名称。</span><span class="sxs-lookup"><span data-stu-id="9d86c-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span></span>  
1.  <span data-ttu-id="9d86c-236">使用可选的桌面 [桥](#deploying) 组件\ (生成和部署 UWP 项目\) 。</span><span class="sxs-lookup"><span data-stu-id="9d86c-236">Build and [deploy](#deploying) the UWP project \(with the optional Desktop Bridge component\).</span></span>  
1.  <span data-ttu-id="9d86c-237">[准备好](#packaging) 提交应用商店后打包本机邮件扩展</span><span class="sxs-lookup"><span data-stu-id="9d86c-237">[Package](#packaging) your native messaging extension once it is ready for Store submission</span></span>  
    
> [!NOTE]
> <span data-ttu-id="9d86c-238">有关 [完整本机邮件](#demos) 扩展的示例，参考"演示"部分。</span><span class="sxs-lookup"><span data-stu-id="9d86c-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span></span>  

## <a name="adding-a-desktop-bridge-component"></a><span data-ttu-id="9d86c-239">添加桌面桥组件</span><span class="sxs-lookup"><span data-stu-id="9d86c-239">Adding a Desktop Bridge component</span></span>  

<span data-ttu-id="9d86c-240">如果要将桌面桥组件添加到程序包，则必须在 Visual Studio 中创建和生成 Win32 项目。</span><span class="sxs-lookup"><span data-stu-id="9d86c-240">If you want to add a Desktop Bridge component to your package, you must create and build your Win32 project in Visual Studio.</span></span>  <span data-ttu-id="9d86c-241">若要了解如何将 win32 应用转换为 UWP，请参阅通过桌面桥将应用移植到[Windows 10。](/windows/uwp/porting/desktop-to-uwp-root)</span><span class="sxs-lookup"><span data-stu-id="9d86c-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span></span>  <span data-ttu-id="9d86c-242">内置Visual Studio后，可以通过执行以下步骤将 Win32 可执行文件添加到包中：</span><span class="sxs-lookup"><span data-stu-id="9d86c-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span></span>  

1.  <span data-ttu-id="9d86c-243">将 Win32 项目添加到与 UWP 项目相同的解决方案。</span><span class="sxs-lookup"><span data-stu-id="9d86c-243">Add the Win32 project to the same solution as the UWP project.</span></span>  
1.  <span data-ttu-id="9d86c-244">将 Win32 项目设置为 UWP 项目的从属项目：</span><span class="sxs-lookup"><span data-stu-id="9d86c-244">Set the Win32 project as a dependent project for the UWP project:</span></span>  
    
    ![设置项目依赖项](../media/project-dependencies.png)  
    
1.  <span data-ttu-id="9d86c-246">在 `Win32` UWP 项目中创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="9d86c-246">Create a `Win32` folder within the UWP project.</span></span>  <span data-ttu-id="9d86c-247">将项目所需的二进制文件 `Win32` 复制到此文件夹。</span><span class="sxs-lookup"><span data-stu-id="9d86c-247">Copy the necessary binaries for the `Win32` project to this folder.</span></span>  <span data-ttu-id="9d86c-248">配置所有二进制文件的属性，如 `Build Action=Content` . `Copy to Output Directory=Copy Always`</span><span class="sxs-lookup"><span data-stu-id="9d86c-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>  
    
    ![包含 win32 和 UWP 应用文件的文件夹](../media/desktop-bridge.png)  
    
1.  <span data-ttu-id="9d86c-250">修改 UWP 项目文件，以使用 PostBuild 事件命令将项目的所有必要二进制文件 `Win32` 复制到此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9d86c-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span></span>  <span data-ttu-id="9d86c-251">这可确保每次重新生成解决方案时，更新后的二进制文件都会复制到文件夹。</span><span class="sxs-lookup"><span data-stu-id="9d86c-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span></span>  
    
    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```  
    
1.  <span data-ttu-id="9d86c-252">通过将 `package.manifest.xml` 元素 `<desktop:Extension>` 添加到元素进行修改 `<Extensions>` ：</span><span class="sxs-lookup"><span data-stu-id="9d86c-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span></span>  
    
    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```  
    
## <a name="deploying"></a><span data-ttu-id="9d86c-253">部署</span><span class="sxs-lookup"><span data-stu-id="9d86c-253">Deploying</span></span>  

<span data-ttu-id="9d86c-254">配置 UWP 项目 \ (和 （可选）Win32 项目\) （如上所述）后，即可使用 Visual Studio 部署解决方案。</span><span class="sxs-lookup"><span data-stu-id="9d86c-254">Once you have configured your UWP project \(and optionally Win32 project\) as outlined above, you are ready to deploy the solution using Visual Studio.</span></span>  

![生成进程内项目](../media/native-message-uwp-debug.png)  

<span data-ttu-id="9d86c-256">正确部署解决方案后，应在 Microsoft Edge 中查看扩展。</span><span class="sxs-lookup"><span data-stu-id="9d86c-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span></span>  

![在 Microsoft Edge 中显示扩展](../media/secureextension.png)  

## <a name="packaging"></a><span data-ttu-id="9d86c-258">打包</span><span class="sxs-lookup"><span data-stu-id="9d86c-258">Packaging</span></span>  

> [!NOTE]
> <span data-ttu-id="9d86c-259">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限功能。</span><span class="sxs-lookup"><span data-stu-id="9d86c-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="9d86c-260">[发送请求](https://developer.microsoft.com/microsoft-edge/extensions/requests/) 作为 Microsoft Store 的一部分，并考虑用于将来的更新。</span><span class="sxs-lookup"><span data-stu-id="9d86c-260">[Send a request](https://developer.microsoft.com/microsoft-edge/extensions/requests/) to be a part of the Microsoft Store, and be considered for future updates.</span></span>  

<span data-ttu-id="9d86c-261">你可以生成一个应用商店程序包，以使用内置功能提交到 Windows 开发人员Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="9d86c-261">You may generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span></span>  

![创建应用商店程序包](../media/create-store-package.png)  

## <a name="debugging"></a><span data-ttu-id="9d86c-263">调试</span><span class="sxs-lookup"><span data-stu-id="9d86c-263">Debugging</span></span>  

<span data-ttu-id="9d86c-264">调试说明因要测试的组件而异：</span><span class="sxs-lookup"><span data-stu-id="9d86c-264">The instructions for debugging vary depending on which component you want to test out:</span></span>  

### <a name="debugging-the-extension"></a><span data-ttu-id="9d86c-265">调试扩展</span><span class="sxs-lookup"><span data-stu-id="9d86c-265">Debugging the extension</span></span>  

<span data-ttu-id="9d86c-266">部署解决方案后，扩展将安装在 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="9d86c-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span></span>  <span data-ttu-id="9d86c-267">有关如何 [调试扩展的信息](./debugging-extensions.md) ，请查看调试指南。</span><span class="sxs-lookup"><span data-stu-id="9d86c-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span></span>  

### <a name="debugging-the-uwp-app"></a><span data-ttu-id="9d86c-268">调试 UWP 应用</span><span class="sxs-lookup"><span data-stu-id="9d86c-268">Debugging the UWP app</span></span>  

<span data-ttu-id="9d86c-269">当扩展尝试使用本机消息传递 API 连接到它时，UWP 应用 [将启动](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)。</span><span class="sxs-lookup"><span data-stu-id="9d86c-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span>  <span data-ttu-id="9d86c-270">只有在进程启动后，你才能调试 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="9d86c-270">You must debug the UWP app only once the process starts.</span></span>  <span data-ttu-id="9d86c-271">这可能使用项目的"属性"页进行配置：</span><span class="sxs-lookup"><span data-stu-id="9d86c-271">This may be configured using the Property page of the project:</span></span>  

1.  <span data-ttu-id="9d86c-272">In Visual Studio， hover on your UWP app project and open the contextual menu \ (right-click\) </span><span class="sxs-lookup"><span data-stu-id="9d86c-272">In Visual Studio, hover on your UWP app project and open the contextual menu \(right-click\)</span></span>  
1.  <span data-ttu-id="9d86c-273">选择 **属性**</span><span class="sxs-lookup"><span data-stu-id="9d86c-273">Select **Properties**</span></span>  
1.  <span data-ttu-id="9d86c-274">Check **Do not launch， but debug my code when it starts**</span><span class="sxs-lookup"><span data-stu-id="9d86c-274">Check **Do not launch, but debug my code when it starts**</span></span>  
    
    ![选择"不启动"框](../media/native-message-do-not-launch.png)  
    
<span data-ttu-id="9d86c-276">在Visual Studio现在可以在代码中设置要调试的断点，然后按 F5 启动调试器。</span><span class="sxs-lookup"><span data-stu-id="9d86c-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span></span>  <span data-ttu-id="9d86c-277">与扩展交互以连接到 UWP 应用后，Visual Studio将自动附加到进程。</span><span class="sxs-lookup"><span data-stu-id="9d86c-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span></span>  

### <a name="debugging-the-desktop-bridge"></a><span data-ttu-id="9d86c-278">调试桌面桥</span><span class="sxs-lookup"><span data-stu-id="9d86c-278">Debugging the Desktop Bridge</span></span>  

<span data-ttu-id="9d86c-279">尽管调试桌面桥 [\ (](/windows/msix/desktop/desktop-to-uwp-debug) 转换的 Win32 app\) 有各种方法，但适用于此方案的唯一方法是 PLMDebug 选项。</span><span class="sxs-lookup"><span data-stu-id="9d86c-279">Even though there are various [methods for debugging a Desktop Bridge](/windows/msix/desktop/desktop-to-uwp-debug) \(converted Win32 app\), the only one applicable for this scenarios is the PLMDebug option.</span></span>  <span data-ttu-id="9d86c-280">您还可以将调试代码添加到启动函数以执行特定时间等待，从而允许您将Visual Studio附加到进程。</span><span class="sxs-lookup"><span data-stu-id="9d86c-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span></span>  
