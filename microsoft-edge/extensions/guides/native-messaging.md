---
description: Learn about how you can use native messaging to have your extension communicate with a companion UWP app.
title: Extensions - Native messaging
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer, native, messaging, uwp
ms.openlocfilehash: 83f80e112180317c38763225c1cdd015da4238b0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563276"
---
# <span data-ttu-id="8d5e7-104">Native messaging in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8d5e7-104">Native messaging in Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="8d5e7-105">Native messaging architecture overview</span><span class="sxs-lookup"><span data-stu-id="8d5e7-105">Native messaging architecture overview</span></span>

<span data-ttu-id="8d5e7-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform (UWP) app.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform (UWP) app.</span></span>  <span data-ttu-id="8d5e7-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span></span> <span data-ttu-id="8d5e7-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span></span>

> [!NOTE]
> <span data-ttu-id="8d5e7-109">The method outlined below (connecting to a UWP app via AppService) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-109">The method outlined below (connecting to a UWP app via AppService) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span></span> <span data-ttu-id="8d5e7-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span></span> 

 <span data-ttu-id="8d5e7-111">Microsoft Edge's native messaging architecture leverages the existing [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API as the underlying inter-process communication (IPC) infrastructure.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-111">Microsoft Edge's native messaging architecture leverages the existing [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API as the underlying inter-process communication (IPC) infrastructure.</span></span> <span data-ttu-id="8d5e7-112">UWP apps use the `AppService` API to communicate with one another.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-112">UWP apps use the `AppService` API to communicate with one another.</span></span> <span data-ttu-id="8d5e7-113">Because of this, Microsoft Edge extensions can now communicate with UWP apps.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-113">Because of this, Microsoft Edge extensions can now communicate with UWP apps.</span></span>

![native messaging architecture](./../media/native-messaging-architecture.png)


### <span data-ttu-id="8d5e7-115">When and when not to use native messaging</span><span class="sxs-lookup"><span data-stu-id="8d5e7-115">When and when not to use native messaging</span></span>

<span data-ttu-id="8d5e7-116">Native messaging adds a whole new layer to your extension.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-116">Native messaging adds a whole new layer to your extension.</span></span> <span data-ttu-id="8d5e7-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span></span>

* <span data-ttu-id="8d5e7-118">Synchronize data (e.g. credentials) with a companion UWP app.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-118">Synchronize data (e.g. credentials) with a companion UWP app.</span></span>
* <span data-ttu-id="8d5e7-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span></span>
* <span data-ttu-id="8d5e7-120">Access resources that are not accessible through web APIs, e.g. hardware or USB devices</span><span class="sxs-lookup"><span data-stu-id="8d5e7-120">Access resources that are not accessible through web APIs, e.g. hardware or USB devices</span></span>

<span data-ttu-id="8d5e7-121">There are a few instances where native messaging can't be used due to security or policy restrictions:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-121">There are a few instances where native messaging can't be used due to security or policy restrictions:</span></span>

* <span data-ttu-id="8d5e7-122">Modifying user settings in either Microsoft Edge or Windows, e.g. changing the default browser or search provider.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-122">Modifying user settings in either Microsoft Edge or Windows, e.g. changing the default browser or search provider.</span></span>
* <span data-ttu-id="8d5e7-123">Actions that violate Microsoft Store policies for both apps and extensions.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-123">Actions that violate Microsoft Store policies for both apps and extensions.</span></span>
* <span data-ttu-id="8d5e7-124">Transferring data to remote endpoint via native message host.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-124">Transferring data to remote endpoint via native message host.</span></span>
* <span data-ttu-id="8d5e7-125">Allowing other apps to download content that changes extension behavior.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-125">Allowing other apps to download content that changes extension behavior.</span></span>

## <span data-ttu-id="8d5e7-126">Demos</span><span class="sxs-lookup"><span data-stu-id="8d5e7-126">Demos</span></span>

<span data-ttu-id="8d5e7-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span></span>

### <span data-ttu-id="8d5e7-128">How it works</span><span class="sxs-lookup"><span data-stu-id="8d5e7-128">How it works</span></span>

<span data-ttu-id="8d5e7-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span></span> <span data-ttu-id="8d5e7-130">The extension communicates this to the Desktop Bridge component via native messaging.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-130">The extension communicates this to the Desktop Bridge component via native messaging.</span></span> <span data-ttu-id="8d5e7-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span></span>

> [!NOTE]
> <span data-ttu-id="8d5e7-132">This sample will only work on a webpage that uses custom events to communicate with the extension's content script.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-132">This sample will only work on a webpage that uses custom events to communicate with the extension's content script.</span></span> <span data-ttu-id="8d5e7-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span></span>

<span data-ttu-id="8d5e7-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span></span> <span data-ttu-id="8d5e7-135">While this example has the native messaging host run in the main app, it's also able to run as a background task.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-135">While this example has the native messaging host run in the main app, it's also able to run as a background task.</span></span> <span data-ttu-id="8d5e7-136">Switching between the two requires editing the extension's background script, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-136">Switching between the two requires editing the extension's background script, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span></span>

## <span data-ttu-id="8d5e7-137">Chrome vs Microsoft Edge implementation</span><span class="sxs-lookup"><span data-stu-id="8d5e7-137">Chrome vs Microsoft Edge implementation</span></span>

<span data-ttu-id="8d5e7-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span></span>

<span data-ttu-id="8d5e7-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span></span>

### <span data-ttu-id="8d5e7-140">Registration and host manifest</span><span class="sxs-lookup"><span data-stu-id="8d5e7-140">Registration and host manifest</span></span>
<span data-ttu-id="8d5e7-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span></span>


<span data-ttu-id="8d5e7-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span></span>

<span data-ttu-id="8d5e7-143">The following JSON is an example of how the config file can be set up:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-143">The following JSON is an example of how the config file can be set up:</span></span>

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

<span data-ttu-id="8d5e7-144">To install this file, the app would need to:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-144">To install this file, the app would need to:</span></span>

1. <span data-ttu-id="8d5e7-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span></span>
   - `HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

     <span data-ttu-id="8d5e7-146">or</span><span class="sxs-lookup"><span data-stu-id="8d5e7-146">or</span></span>
   - `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

2. <span data-ttu-id="8d5e7-147">Set the default value of that key to the full path to the manifest file, e.g.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-147">Set the default value of that key to the full path to the manifest file, e.g.</span></span>  `[HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"`




<span data-ttu-id="8d5e7-148">For Microsoft Edge, in order to register an [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx)(native messaging host) you'll need to include the UWP companion app in the same package as your extension and specify the [AppService extension](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in your project's `Package.appxmanifest` file.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-148">For Microsoft Edge, in order to register an [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx)(native messaging host) you'll need to include the UWP companion app in the same package as your extension and specify the [AppService extension](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in your project's `Package.appxmanifest` file.</span></span> <span data-ttu-id="8d5e7-149">The `EntryPoint` and `Name` attributes can be configured by you:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-149">The `EntryPoint` and `Name` attributes can be configured by you:</span></span>

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


<span data-ttu-id="8d5e7-150">You'll also need to set which extension(s) are allowed to connect to the service.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-150">You'll also need to set which extension(s) are allowed to connect to the service.</span></span> <span data-ttu-id="8d5e7-151">Because Microsoft Edge doesn't have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-151">Because Microsoft Edge doesn't have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span></span> <span data-ttu-id="8d5e7-152">Since Microsoft Edge will be establishing the connection on behalf of the extension, the app can look up the caller's Package Family Name to determine if they're being connected by Microsoft Edge to control or authenticate the caller.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-152">Since Microsoft Edge will be establishing the connection on behalf of the extension, the app can look up the caller's Package Family Name to determine if they're being connected by Microsoft Edge to control or authenticate the caller.</span></span> <span data-ttu-id="8d5e7-153">E.g.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-153">E.g.</span></span> 

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



### <span data-ttu-id="8d5e7-154">Message sending</span><span class="sxs-lookup"><span data-stu-id="8d5e7-154">Message sending</span></span>

<span data-ttu-id="8d5e7-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span></span>

<span data-ttu-id="8d5e7-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span></span> 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```

<span data-ttu-id="8d5e7-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span></span> <span data-ttu-id="8d5e7-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span></span> <span data-ttu-id="8d5e7-159">Extensions can also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-159">Extensions can also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span></span> 

<span data-ttu-id="8d5e7-160">Microsoft Edge uses the same construct as Chrome's native messaging API to allow Microsoft Edge extensions to specify which app service to connect to.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-160">Microsoft Edge uses the same construct as Chrome's native messaging API to allow Microsoft Edge extensions to specify which app service to connect to.</span></span> <span data-ttu-id="8d5e7-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span></span> <span data-ttu-id="8d5e7-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span></span> <span data-ttu-id="8d5e7-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span></span> <span data-ttu-id="8d5e7-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span></span> 

<span data-ttu-id="8d5e7-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span></span>  

> [!NOTE]
> <span data-ttu-id="8d5e7-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span></span> <span data-ttu-id="8d5e7-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span></span>





### <span data-ttu-id="8d5e7-168">Communication protocol</span><span class="sxs-lookup"><span data-stu-id="8d5e7-168">Communication protocol</span></span>

<span data-ttu-id="8d5e7-169">Communication protocol for native messaging determines how messages are formatted before sending.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-169">Communication protocol for native messaging determines how messages are formatted before sending.</span></span>

<span data-ttu-id="8d5e7-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span></span> <span data-ttu-id="8d5e7-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span></span>


<span data-ttu-id="8d5e7-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span></span> <span data-ttu-id="8d5e7-173">On startup, the background task's `Run` method will be invoked:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-173">On startup, the background task's `Run` method will be invoked:</span></span>  

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

<span data-ttu-id="8d5e7-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) event will be raised.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) event will be raised.</span></span> <span data-ttu-id="8d5e7-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object.</span></span> <span data-ttu-id="8d5e7-176">:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-176">:</span></span>

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```

<span data-ttu-id="8d5e7-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) will be added to the `ValueSet` object.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) will be added to the `ValueSet` object.</span></span> <span data-ttu-id="8d5e7-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span></span>

### <span data-ttu-id="8d5e7-179">Callback</span><span class="sxs-lookup"><span data-stu-id="8d5e7-179">Callback</span></span>

<span data-ttu-id="8d5e7-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span></span>

<span data-ttu-id="8d5e7-181">Microsoft Edge uses the [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) object's [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) method to let the app send a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object back to the extension.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-181">Microsoft Edge uses the [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) object's [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) method to let the app send a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object back to the extension.</span></span>


### <span data-ttu-id="8d5e7-182">Message size limit</span><span class="sxs-lookup"><span data-stu-id="8d5e7-182">Message size limit</span></span>
<span data-ttu-id="8d5e7-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span></span>

<span data-ttu-id="8d5e7-184">Chrome has the following message size limitations:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-184">Chrome has the following message size limitations:</span></span>
- <span data-ttu-id="8d5e7-185">Single message limit from native messaging host: 1 MB</span><span class="sxs-lookup"><span data-stu-id="8d5e7-185">Single message limit from native messaging host: 1 MB</span></span>
- <span data-ttu-id="8d5e7-186">Single message limit sent to native messaging host: 4 GB</span><span class="sxs-lookup"><span data-stu-id="8d5e7-186">Single message limit sent to native messaging host: 4 GB</span></span>

<span data-ttu-id="8d5e7-187">For Microsoft Edge, while `AppService` has no limit on message size (dependent on memory), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-187">For Microsoft Edge, while `AppService` has no limit on message size (dependent on memory), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span></span>
- <span data-ttu-id="8d5e7-188">Single message limit from UWP app to extension: 1 MB</span><span class="sxs-lookup"><span data-stu-id="8d5e7-188">Single message limit from UWP app to extension: 1 MB</span></span>
- <span data-ttu-id="8d5e7-189">Single message limit from extension to UWP app: 100 MB</span><span class="sxs-lookup"><span data-stu-id="8d5e7-189">Single message limit from extension to UWP app: 100 MB</span></span>



### <span data-ttu-id="8d5e7-190">Native messaging connections</span><span class="sxs-lookup"><span data-stu-id="8d5e7-190">Native messaging connections</span></span>

<span data-ttu-id="8d5e7-191">There are two types of connections for native messaging; persistent and non-persistent.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-191">There are two types of connections for native messaging; persistent and non-persistent.</span></span>
<span data-ttu-id="8d5e7-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span></span> <span data-ttu-id="8d5e7-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span></span>

#### <span data-ttu-id="8d5e7-194">Persistent</span><span class="sxs-lookup"><span data-stu-id="8d5e7-194">Persistent</span></span>

<span data-ttu-id="8d5e7-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="8d5e7-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span></span>

<span data-ttu-id="8d5e7-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) and keeps it running until the port is destroyed.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) and keeps it running until the port is destroyed.</span></span> <span data-ttu-id="8d5e7-198">The following snippet shows how a persistent connection is established from within a UWP app.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-198">The following snippet shows how a persistent connection is established from within a UWP app.</span></span> 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```

#### <span data-ttu-id="8d5e7-199">Non-persistent</span><span class="sxs-lookup"><span data-stu-id="8d5e7-199">Non-persistent</span></span>

<span data-ttu-id="8d5e7-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span></span> <span data-ttu-id="8d5e7-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span></span>

<span data-ttu-id="8d5e7-202">Microsoft Edge will terminate the connection after every messages' response has been received.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-202">Microsoft Edge will terminate the connection after every messages' response has been received.</span></span> <span data-ttu-id="8d5e7-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse).</span></span>

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

### <span data-ttu-id="8d5e7-204">Permission</span><span class="sxs-lookup"><span data-stu-id="8d5e7-204">Permission</span></span>

<span data-ttu-id="8d5e7-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you'll need to declare the `"nativeMessaging"` permission in you `manifest.json` file.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you'll need to declare the `"nativeMessaging"` permission in you `manifest.json` file.</span></span>


## <span data-ttu-id="8d5e7-206">App services</span><span class="sxs-lookup"><span data-stu-id="8d5e7-206">App services</span></span>
<span data-ttu-id="8d5e7-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span></span>

### <span data-ttu-id="8d5e7-208">Performance</span><span class="sxs-lookup"><span data-stu-id="8d5e7-208">Performance</span></span>

<span data-ttu-id="8d5e7-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span></span> <span data-ttu-id="8d5e7-210">This means that app services can run as long as Microsoft Edge is running.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-210">This means that app services can run as long as Microsoft Edge is running.</span></span>

<span data-ttu-id="8d5e7-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span></span> <span data-ttu-id="8d5e7-212">This method of communication produces low latency.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-212">This method of communication produces low latency.</span></span> <span data-ttu-id="8d5e7-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service (~80ms to startup the background task on some devices).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service (~80ms to startup the background task on some devices).</span></span> <span data-ttu-id="8d5e7-214">After start-up, performance on slow CPU devices should be good.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-214">After start-up, performance on slow CPU devices should be good.</span></span> 


### <span data-ttu-id="8d5e7-215">Memory</span><span class="sxs-lookup"><span data-stu-id="8d5e7-215">Memory</span></span>
<span data-ttu-id="8d5e7-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span></span> <span data-ttu-id="8d5e7-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span></span> <span data-ttu-id="8d5e7-218">The usual background task memory caps are enforced on app services.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-218">The usual background task memory caps are enforced on app services.</span></span> <span data-ttu-id="8d5e7-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span></span> <span data-ttu-id="8d5e7-220">This number goes up as the devices scale up.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-220">This number goes up as the devices scale up.</span></span>


## <span data-ttu-id="8d5e7-221">Creating an extension with native messaging</span><span class="sxs-lookup"><span data-stu-id="8d5e7-221">Creating an extension with native messaging</span></span>

<span data-ttu-id="8d5e7-222">In order to test native messaging, your extension needs a Package Family Name.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-222">In order to test native messaging, your extension needs a Package Family Name.</span></span> <span data-ttu-id="8d5e7-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span></span> 


<span data-ttu-id="8d5e7-224">To create your extension with native messaging in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-224">To create your extension with native messaging in Visual Studio:</span></span>

1. <span data-ttu-id="8d5e7-225">Create a UWP project in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-225">Create a UWP project in Visual Studio.</span></span>
2. <span data-ttu-id="8d5e7-226">[Add `AppService` to your UWP app](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-226">[Add `AppService` to your UWP app](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>
   - <span data-ttu-id="8d5e7-227">You can optionally [configure `AppService` to be hosted in the main app](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-227">You can optionally [configure `AppService` to be hosted in the main app](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span></span>
3. <span data-ttu-id="8d5e7-228">Build and test your UWP project.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-228">Build and test your UWP project.</span></span>
   - <span data-ttu-id="8d5e7-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span></span>
4. <span data-ttu-id="8d5e7-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span></span> <span data-ttu-id="8d5e7-231">The extension files can be added into a folder named `Extension` in the UWP project.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-231">The extension files can be added into a folder named `Extension` in the UWP project.</span></span> <span data-ttu-id="8d5e7-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span> <span data-ttu-id="8d5e7-233">Make sure `manifest.json` is also configured with these properties.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-233">Make sure `manifest.json` is also configured with these properties.</span></span>
5. <span data-ttu-id="8d5e7-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span></span>

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

6. <span data-ttu-id="8d5e7-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span></span>
7. <span data-ttu-id="8d5e7-236">Build and [deploy](#deploying) the UWP project (with the optional Desktop Bridge component).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-236">Build and [deploy](#deploying) the UWP project (with the optional Desktop Bridge component).</span></span>
8. <span data-ttu-id="8d5e7-237">[Package](#packaging) your native messaging extension once it's ready for Store submission</span><span class="sxs-lookup"><span data-stu-id="8d5e7-237">[Package](#packaging) your native messaging extension once it's ready for Store submission</span></span>

> [!NOTE]
> <span data-ttu-id="8d5e7-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span></span>


## <span data-ttu-id="8d5e7-239">Adding a Desktop Bridge component</span><span class="sxs-lookup"><span data-stu-id="8d5e7-239">Adding a Desktop Bridge component</span></span> 
<span data-ttu-id="8d5e7-240">If you want to add a Desktop Bridge component to your package, you'll need to create and build your Win32 project in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-240">If you want to add a Desktop Bridge component to your package, you'll need to create and build your Win32 project in Visual Studio.</span></span> <span data-ttu-id="8d5e7-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span></span> <span data-ttu-id="8d5e7-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span></span>

1. <span data-ttu-id="8d5e7-243">Add the Win32 project to the same solution as the UWP project.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-243">Add the Win32 project to the same solution as the UWP project.</span></span> 

2. <span data-ttu-id="8d5e7-244">Set the Win32 project as a dependent project for the UWP project:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-244">Set the Win32 project as a dependent project for the UWP project:</span></span>

    ![setting up project dependencies](./../media/project-dependencies.PNG)

3. <span data-ttu-id="8d5e7-246">Create a `Win32` folder within the UWP project.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-246">Create a `Win32` folder within the UWP project.</span></span> <span data-ttu-id="8d5e7-247">Copy the necessary binaries for the `Win32` project to this folder.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-247">Copy the necessary binaries for the `Win32` project to this folder.</span></span> <span data-ttu-id="8d5e7-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>

    ![folder with win32 and UWP app files in it](./../media/desktop-bridge.png)

4. <span data-ttu-id="8d5e7-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span></span> <span data-ttu-id="8d5e7-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span></span>

    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```


5. <span data-ttu-id="8d5e7-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span></span>

    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```

## <span data-ttu-id="8d5e7-253">Deploying</span><span class="sxs-lookup"><span data-stu-id="8d5e7-253">Deploying</span></span>
<span data-ttu-id="8d5e7-254">Once you have configured your UWP project (and optionally Win32 project) as outlined above, you are ready to deploy the solution using Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-254">Once you have configured your UWP project (and optionally Win32 project) as outlined above, you are ready to deploy the solution using Visual Studio.</span></span>

![build inprocess project](../media/native-message-uwp-debug.PNG)

<span data-ttu-id="8d5e7-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span></span>

![extension showing in Microsoft Edge](../media/secureextension.png)

## <span data-ttu-id="8d5e7-258">Packaging</span><span class="sxs-lookup"><span data-stu-id="8d5e7-258">Packaging</span></span>

> [!NOTE]
> <span data-ttu-id="8d5e7-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="8d5e7-260">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-260">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>


<span data-ttu-id="8d5e7-261">You can generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-261">You can generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span></span>


![Creating Store package](../media/create-store-package.PNG)

## <span data-ttu-id="8d5e7-263">Debugging</span><span class="sxs-lookup"><span data-stu-id="8d5e7-263">Debugging</span></span>
<span data-ttu-id="8d5e7-264">The instructions for debugging vary depending on which component you want to test out:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-264">The instructions for debugging vary depending on which component you want to test out:</span></span>

### <span data-ttu-id="8d5e7-265">Debugging the extension</span><span class="sxs-lookup"><span data-stu-id="8d5e7-265">Debugging the extension</span></span>
<span data-ttu-id="8d5e7-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span></span> <span data-ttu-id="8d5e7-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span></span>


### <span data-ttu-id="8d5e7-268">Debugging the UWP app</span><span class="sxs-lookup"><span data-stu-id="8d5e7-268">Debugging the UWP app</span></span>
<span data-ttu-id="8d5e7-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span><span class="sxs-lookup"><span data-stu-id="8d5e7-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="8d5e7-270">You'll need to debug the UWP app only once the process starts.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-270">You'll need to debug the UWP app only once the process starts.</span></span> <span data-ttu-id="8d5e7-271">This can be configured via the project's Property page:</span><span class="sxs-lookup"><span data-stu-id="8d5e7-271">This can be configured via the project's Property page:</span></span>

1.  <span data-ttu-id="8d5e7-272">In Visual Studio, right click your UWP app project</span><span class="sxs-lookup"><span data-stu-id="8d5e7-272">In Visual Studio, right click your UWP app project</span></span>
2.  <span data-ttu-id="8d5e7-273">Select Properties</span><span class="sxs-lookup"><span data-stu-id="8d5e7-273">Select Properties</span></span>
3.  <span data-ttu-id="8d5e7-274">Check "Do not launch, but debug my code when it starts"</span><span class="sxs-lookup"><span data-stu-id="8d5e7-274">Check "Do not launch, but debug my code when it starts"</span></span>

    ![selecting do not launch box](../media/native-message-do-not-launch.png)

<span data-ttu-id="8d5e7-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span></span> <span data-ttu-id="8d5e7-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span></span>


### <span data-ttu-id="8d5e7-278">Debugging the Desktop Bridge</span><span class="sxs-lookup"><span data-stu-id="8d5e7-278">Debugging the Desktop Bridge</span></span>
<span data-ttu-id="8d5e7-279">Even though there are various [methods for debugging a Desktop Bridge](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) (converted Win32 app), the only one applicable for this scenarios is the PLMDebug option.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-279">Even though there are various [methods for debugging a Desktop Bridge](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) (converted Win32 app), the only one applicable for this scenarios is the PLMDebug option.</span></span> <span data-ttu-id="8d5e7-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span><span class="sxs-lookup"><span data-stu-id="8d5e7-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span></span>
