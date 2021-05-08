---
description: 了解如何使用 Microsoft Edge WebView2 Chromium DevTools 协议包在 WebView2 应用中使用 Chrome NuGet协议
title: 在 WebView2 中使用 Chrome DevTools 协议
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Chrome DevTools 协议
ms.openlocfilehash: 86846ee195406f78d5fd7c369f375ed1e359101a
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536369"
---
# <a name="use-chromium-devtools-protocol-in-webview2"></a><span data-ttu-id="d802c-104">在 WebView2 中使用 Chromium 开发工具协议</span><span class="sxs-lookup"><span data-stu-id="d802c-104">Use Chromium DevTools Protocol in WebView2</span></span>  

<span data-ttu-id="d802c-105">开发人员[Chromium协议][GitHubChromedevtoolsDevtoolsProtocol]提供了用于检测、检查、调试和配置文件的 API Chromium基于浏览器。</span><span class="sxs-lookup"><span data-stu-id="d802c-105">The [Chromium DevTools Protocol][GitHubChromedevtoolsDevtoolsProtocol] provides APIs to instrument, inspect, debug, and profile Chromium-based browsers.</span></span>  <span data-ttu-id="d802c-106">Chromium DevTools 协议是 Microsoft Edge \ (Chromium\) DevTools 的基础。</span><span class="sxs-lookup"><span data-stu-id="d802c-106">The Chromium DevTools Protocol is the foundation for the Microsoft Edge \(Chromium\) DevTools.</span></span>  <span data-ttu-id="d802c-107">将 Chromium DevTools 协议用于 WebView2 平台中未实现的功能。</span><span class="sxs-lookup"><span data-stu-id="d802c-107">Use the Chromium DevTools Protocol for features that aren't implemented in the WebView2 platform.</span></span>  <span data-ttu-id="d802c-108">有关开发人员工具Chromium功能的信息，请导航到 Chromium [DevTools 协议][GitHubChromedevtoolsDevtoolsProtocol]。</span><span class="sxs-lookup"><span data-stu-id="d802c-108">For more information about the Chromium DevTools Protocol functionality, navigate to [Chromium DevTools Protocol][GitHubChromedevtoolsDevtoolsProtocol].</span></span>  

> [!CAUTION]
> <span data-ttu-id="d802c-109">WebView2 Microsoft Edge团队不维护或支持 Chromium Tools 协议。</span><span class="sxs-lookup"><span data-stu-id="d802c-109">The Microsoft Edge WebView2 team does not maintain or support the Chromium DevTools Protocol.</span></span>  <span data-ttu-id="d802c-110">Chromium开发人员工具协议由开源项目Chromium维护。</span><span class="sxs-lookup"><span data-stu-id="d802c-110">The Chromium DevTools Protocol is maintained by the open source Chromium project.</span></span>  
> 
> <span data-ttu-id="d802c-111">若要发送有关未来 WebView2 平台功能的建议，请导航到 ["WebView 反馈][GithubMicrosoftedgeWebview2feedback] "并提交问题。</span><span class="sxs-lookup"><span data-stu-id="d802c-111">To send your suggestions for future WebView2 platform features, navigate to [WebView Feedback][GithubMicrosoftedgeWebview2feedback] and submit an issue.</span></span>  

<span data-ttu-id="d802c-112">若要在 WebView2 Chromium DevTools 协议 API，请使用以下任一操作。</span><span class="sxs-lookup"><span data-stu-id="d802c-112">To use the Chromium DevTools Protocol API in WebView2, use either of the following actions.</span></span>  

*   <span data-ttu-id="d802c-113">安装并使用[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview) ][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet 包 \ (.NET\) 。</span><span class="sxs-lookup"><span data-stu-id="d802c-113">Install and use the [Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet package \(.NET\).</span></span>  
*   <span data-ttu-id="d802c-114">运行下列方法之一。</span><span class="sxs-lookup"><span data-stu-id="d802c-114">Run one of the following methods.</span></span>  
    *   <span data-ttu-id="d802c-115">[.NET：CallDevToolsProtocolAsync][DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString] [、GetDevToolsProtocolEventReceiver][DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]</span><span class="sxs-lookup"><span data-stu-id="d802c-115">.NET:  [CallDevToolsProtocolAsync][DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString], [GetDevToolsProtocolEventReceiver][DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]</span></span>  
    *   <span data-ttu-id="d802c-116">Win32  [C/C++：CallDevToolsProtocolMethod][Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod] [、ICoreWebView2DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]</span><span class="sxs-lookup"><span data-stu-id="d802c-116">Win32 C/C++:  [CallDevToolsProtocolMethod][Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod], [ICoreWebView2DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]</span></span>  
    
## <a name="use-devtoolsprotocolhelper-preview"></a><span data-ttu-id="d802c-117">使用 DevToolsProtocolHelper (Preview) </span><span class="sxs-lookup"><span data-stu-id="d802c-117">Use DevToolsProtocolHelper (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="d802c-118">[Microsoft.Web.WebView2.DevToolsProtocolExtension][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet目前处于技术预览阶段。</span><span class="sxs-lookup"><span data-stu-id="d802c-118">The [Microsoft.Web.WebView2.DevToolsProtocolExtension][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet package is currently in technical preview.</span></span>  <span data-ttu-id="d802c-119">在预览版中，请勿在生产应用中使用程序包。</span><span class="sxs-lookup"><span data-stu-id="d802c-119">While in preview, refrain from using the package in production apps.</span></span>

<span data-ttu-id="d802c-120">[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview) ][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]是 WebView2 团队创建的 NuGet 包，可轻松访问 Chromium DevTools 协议功能。</span><span class="sxs-lookup"><span data-stu-id="d802c-120">[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] is a NuGet package created by the WebView2 team that provides easy access to Chromium DevTools Protocol features.</span></span>  <span data-ttu-id="d802c-121">以下示例介绍如何在 WebView2 控件的 Chromium DevTools 协议中使用地理位置功能。</span><span class="sxs-lookup"><span data-stu-id="d802c-121">The following examples describe how to use the geolocation functionality in Chromium DevTools Protocol in your WebView2 control.</span></span>  <span data-ttu-id="d802c-122">你可以遵循类似的模式来使用其他 Chromium DevTools 协议功能。</span><span class="sxs-lookup"><span data-stu-id="d802c-122">You may follow a similar pattern to use other Chromium DevTools Protocol features.</span></span>  

## <a name="step-1-create-a-webpage-to-find-your-geolocation"></a><span data-ttu-id="d802c-123">步骤 1：创建网页以查找地理位置</span><span class="sxs-lookup"><span data-stu-id="d802c-123">Step 1: Create a webpage to find your geolocation</span></span>  

<span data-ttu-id="d802c-124">若要创建 `HTML file` 以查找地理位置，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="d802c-124">To create an `HTML file` to find your geolocation, complete following the actions.</span></span>  

1.  <span data-ttu-id="d802c-125">打开Visual Studio Code \ (或你选择的 IDE\) 。</span><span class="sxs-lookup"><span data-stu-id="d802c-125">Open Visual Studio Code \(or an IDE of your choice\).</span></span>  
1.  <span data-ttu-id="d802c-126">创建新 `.html` 文件。</span><span class="sxs-lookup"><span data-stu-id="d802c-126">Create a new `.html` file.</span></span>  
1.  <span data-ttu-id="d802c-127">将以下代码段复制并粘贴到新 `.html` 文件中。</span><span class="sxs-lookup"><span data-stu-id="d802c-127">Copy and paste the following code snippet in your new `.html` file.</span></span>  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <title>Geolocation Finder</title>
    </head>
    <body>
        <button id="display">Display Location</button>
        <div id="message"></div>
    </body>
    
    <script>
        const btn = document.getElementById('display');
        // Find the user location.
        btn.addEventListener('click', function () {
            navigator.geolocation.getCurrentPosition(onSuccess, onError);
        });
        
        // Update message to display the latitude and longitude coordinates.
        function onSuccess(position) {
            const {latitude, longitude} = position.coords;
            message.textContent = `Your location: (${latitude},${longitude})`;
        }
        
        function onError() {
            message.textContent = `Operation Failed`;
        }
    </script>
    </html>
    ```  
    
1.  <span data-ttu-id="d802c-128">使用 `.html` 文件名 保存文件 `geolocation.html` 。</span><span class="sxs-lookup"><span data-stu-id="d802c-128">Save the `.html` file with the filename `geolocation.html`.</span></span>  
1.  <span data-ttu-id="d802c-129">打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d802c-129">Open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="d802c-130">打开 `geolocation.html` 文件。</span><span class="sxs-lookup"><span data-stu-id="d802c-130">Open the `geolocation.html` file.</span></span>  
1.  <span data-ttu-id="d802c-131">若要显示纬度和经度坐标，请选择"显示 **位置"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="d802c-131">To display your latitude and longitude coordinates, choose the **Display Location** button.</span></span>  <span data-ttu-id="d802c-132">若要验证和比较地理位置，请将坐标复制并粘贴到 中 [https://www.bing.com/maps][BingMaps] 。</span><span class="sxs-lookup"><span data-stu-id="d802c-132">To verify and compare your geolocation, copy and paste your coordinates in [https://www.bing.com/maps][BingMaps].</span></span>  
    
    :::image type="complex" source="./media/geolocater-browser.png" alt-text="在用户位置中显示用户的地理位置Microsoft Edge" lightbox="./media/geolocater-browser.png":::
       <span data-ttu-id="d802c-134">在用户位置中显示用户的地理位置Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d802c-134">Display the geolocation coordinates of the user in Microsoft Edge</span></span>  
    :::image-end:::  
    
## <a name="step-2-display-geolocationhtml-in-a-webview2"></a><span data-ttu-id="d802c-135">步骤 2：geolocation.htmWebView2 中显示 geolocation.html</span><span class="sxs-lookup"><span data-stu-id="d802c-135">Step 2: Display geolocation.html in a WebView2</span></span>  

1.  <span data-ttu-id="d802c-136">若要创建 WebView2 应用，请使用以下入门指南或 WebView2 示例之一。</span><span class="sxs-lookup"><span data-stu-id="d802c-136">To create a WebView2 app, use either of the following getting started guides or WebView2 samples.</span></span>  
    *   [<span data-ttu-id="d802c-137">WebView2 在表单Windows入门</span><span class="sxs-lookup"><span data-stu-id="d802c-137">Getting Started with WebView2 in Windows Forms</span></span>][Webview2GettingstartedWinforms]  
    *   [<span data-ttu-id="d802c-138">WPF 中的 WebView2 入门</span><span class="sxs-lookup"><span data-stu-id="d802c-138">Getting Started with WebView2 in WPF</span></span>][Webview2GettingstartedWpf]  
    *   [<span data-ttu-id="d802c-139">WebView2 示例</span><span class="sxs-lookup"><span data-stu-id="d802c-139">WebView2 samples</span></span>][GithubMicrosoftedgeWebview2samples]  
        
1.  <span data-ttu-id="d802c-140">将 WebView2 控件的初始导航设置为 `geolocation.html` 。</span><span class="sxs-lookup"><span data-stu-id="d802c-140">Set the initial navigation of the WebView2 control to `geolocation.html`.</span></span>  
    
    ```csharp
    webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    ```  
    
1.  <span data-ttu-id="d802c-141">确保 `geolocation.html` 文件显示在 WebView2 控件应用中。</span><span class="sxs-lookup"><span data-stu-id="d802c-141">Ensure the `geolocation.html` file displays in your WebView2 control app.</span></span>  
    
    :::image type="complex" source="./media/initial-geolocate.png" alt-text="在 WebView2 geolocater.htm应用中显示 geolocater.html 文件" lightbox="./media/initial-geolocate.png":::
       <span data-ttu-id="d802c-143">在 `geolocation.html` WebView2 控件应用中显示文件</span><span class="sxs-lookup"><span data-stu-id="d802c-143">Display the `geolocation.html` file in your WebView2 control app</span></span>  
    :::image-end:::  
    
## <a name="step-3-install-the-devtoolsprotocolhelper-nuget-package"></a><span data-ttu-id="d802c-144">步骤 3：安装 DevToolsProtocolHelper NuGet包</span><span class="sxs-lookup"><span data-stu-id="d802c-144">Step 3: Install the DevToolsProtocolHelper NuGet package</span></span>  

<span data-ttu-id="d802c-145">使用 NuGet 下载 `Microsoft.Web.WebView2.DevToolsProtocolExtension` 。</span><span class="sxs-lookup"><span data-stu-id="d802c-145">Use NuGet to download `Microsoft.Web.WebView2.DevToolsProtocolExtension`.</span></span>  <span data-ttu-id="d802c-146">若要安装程序包，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="d802c-146">To install the package, complete the following actions.</span></span>  

1.  <span data-ttu-id="d802c-147">选择**Project**  >  **管理NuGet程序包**  >  **浏览"。**</span><span class="sxs-lookup"><span data-stu-id="d802c-147">Choose **Project** > **Manage NuGet Packages** > **Browse**.</span></span>  
1.  <span data-ttu-id="d802c-148">键入 `Microsoft.Web.WebView2.DevToolsProtocolExtension` 并选择 **"Microsoft.Web.WebView2.DevToolsProtocolExtension**  >  **安装"。**</span><span class="sxs-lookup"><span data-stu-id="d802c-148">Type `Microsoft.Web.WebView2.DevToolsProtocolExtension` and choose **Microsoft.Web.WebView2.DevToolsProtocolExtension** > **Install**.</span></span>   
    
:::image type="complex" source="./media/cdpnuget.png" alt-text="确保 Microsoft.Web.WebView2.DevToolsProtocolExtension 显示在Visual Studio NuGet 程序包管理器" lightbox="./media/cdpnuget.png":::
   <span data-ttu-id="d802c-150">确保**Microsoft.Web.WebView2.DevToolsProtocolExtension**显示在Visual Studio NuGet 程序包管理器</span><span class="sxs-lookup"><span data-stu-id="d802c-150">Ensure **Microsoft.Web.WebView2.DevToolsProtocolExtension** displays in the Visual Studio NuGet Package Manager</span></span>  
:::image-end:::  

## <a name="step-4-use-devtools-protocol-helper"></a><span data-ttu-id="d802c-151">步骤 4：使用 DevTools 协议帮助程序</span><span class="sxs-lookup"><span data-stu-id="d802c-151">Step 4: Use DevTools Protocol Helper</span></span>  

1.  <span data-ttu-id="d802c-152">将 `DevToolsProtocolExtension` 命名空间添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="d802c-152">Add the `DevToolsProtocolExtension` namespace to your project.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    using Microsoft.Web.WebView2.Core.DevToolsProtocolExtension;
    ```  
    
1.  <span data-ttu-id="d802c-153">实例化 `DevToolsProtocolHelper` 对象并导航到 `geolocation.html` 。</span><span class="sxs-lookup"><span data-stu-id="d802c-153">Instantiate the `DevToolsProtocolHelper` object and navigate to `geolocation.html`.</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webView.CoreWebView2.GetDevToolsProtocolHelper(); 
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    }
    ```  
    
1.  <span data-ttu-id="d802c-154">运行 [setGeoLocationOverrideAsync][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride] 方法。</span><span class="sxs-lookup"><span data-stu-id="d802c-154">Run the [setGeoLocationOverrideAsync][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride] method.</span></span>  <span data-ttu-id="d802c-155">有关详细信息，请导航到 [setGeolocationOverride][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]。</span><span class="sxs-lookup"><span data-stu-id="d802c-155">For more information, navigate to [setGeolocationOverride][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride].</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webview.CoreWebView2.GetDevToolsProtocolHelper();
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
        
        // Latitude and longitude for Paris, France.
        double latitude = 48.857024082572565;  
        double longitude = 2.3161581601457386;  
        double accuracy = 1;
        await helper.Emulation.setGeolocationOverrideAsync(latitude, longitude, accuracy);
        
    }
    ```  
    
1.  <span data-ttu-id="d802c-156">运行应用。</span><span class="sxs-lookup"><span data-stu-id="d802c-156">Run your app.</span></span>  
1.  <span data-ttu-id="d802c-157">若要显示法国巴黎的坐标，请选择" **显示位置"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="d802c-157">To display the coordinates of Paris, France, choose the **Display Location** button.</span></span>  
    
    :::image type="complex" source="./media/finallocation-cdp.png" alt-text="在 WebView2 .html显示带巴黎坐标的 WebView2 文件" lightbox="./media/finallocation-cdp.png":::
       <span data-ttu-id="d802c-159">在 `.html` WebView2 控件中显示文件以及巴黎的坐标</span><span class="sxs-lookup"><span data-stu-id="d802c-159">Display the `.html` file in a WebView2 control with the coordinates for Paris</span></span>  
    :::image-end:::  
    
## <a name="file-a-chromium-devtools-protocol-bug"></a><span data-ttu-id="d802c-160">提出开发人员Chromium协议 bug</span><span class="sxs-lookup"><span data-stu-id="d802c-160">File a Chromium DevTools Protocol bug</span></span>  

<span data-ttu-id="d802c-161">WebView2 团队不拥有 Chromium Tools 协议。</span><span class="sxs-lookup"><span data-stu-id="d802c-161">The WebView2 team doesn't own the Chromium DevTools Protocol.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="d802c-162">将反馈和 bug Chromium问题存储库。</span><span class="sxs-lookup"><span data-stu-id="d802c-162">Direct feedback and bugs to the Chromium Issues repo.</span></span>  

<span data-ttu-id="d802c-163">若要提交Chromium工具协议 bug 或问题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="d802c-163">To file a Chromium DevTools Protocol bug or issue, complete the following actions.</span></span>  

1.  <span data-ttu-id="d802c-164">提交 [Bug 报告][ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]。</span><span class="sxs-lookup"><span data-stu-id="d802c-164">File a [bug report][ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform].</span></span>  
1.  <span data-ttu-id="d802c-165">导航到 ["WebView 反馈"][GithubMicrosoftedgeWebview2feedback] 并打开新问题。</span><span class="sxs-lookup"><span data-stu-id="d802c-165">Navigate to [WebView Feedback][GithubMicrosoftedgeWebview2feedback] and open a new issue.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="d802c-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d802c-166">See also</span></span>  

*   [<span data-ttu-id="d802c-167">WebView2 示例</span><span class="sxs-lookup"><span data-stu-id="d802c-167">WebView2 samples</span></span>][GithubMicrosoftedgeWebview2samples]  
    
 <!-- links -->  

[Webview2GettingstartedWinforms]: /microsoft-edge/webview2/gettingstarted/winforms "Windows Forms | 中的 WebView2 入门Microsoft Docs"  
[Webview2GettingstartedWpf]: /microsoft-edge/webview2/gettingstarted/wpf "WPF | 中的 WebView2 入门Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2.getdevtoolsprotocoleventreceiver?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2.GetDevToolsProtocolEventReceiver (String) 方法 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString]: /dotnet/api/microsoft.web.webview2.core.corewebview2.calldevtoolsprotocolmethodasync?view=webview2-dotnet-1.0.774.44&preserve-view=true#Microsoft_Web_WebView2_Core_CoreWebView2_CallDevToolsProtocolMethodAsync_System_String_System_String_ "CoreWebView2.CallDevToolsProtocolMethodAsync (String， String) 方法 |Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-1.0.774.44&preserve-view=true#calldevtoolsprotocolmethod "CallDevToolsProtocolMethod - 接口 ICoreWebView2 |Microsoft Docs"  
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-1.0.774.44&preserve-view=true "interface ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  

[BingMaps]: https://www.bing.com/maps "必应地图"  

[GitHubChromedevtoolsDevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools 协议|GitHub"  
[GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]: https://chromedevtools.github.io/devtools-protocol/tot/Emulation/#method-setGeolocationOverride "Emulation.setGeolocationOverride - Chrome DevTools 协议|GitHub"  

[GithubMicrosoftedgeWebview2feedback]: https://github.com/MicrosoftEdge/WebView2Feedback "WebView 反馈|GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例|GitHub"  

[ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]: https://bugs.chromium.org/p/chromium/issues/entry?components=Platform%3EDevTools%3EPlatform "错误报告|ChromiumBug"  

[NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]: https://www.nuget.org/packages/Microsoft.Web.WebView2.DevToolsProtocolExtension "Microsoft.Web.WebView2.DevToolsProtocolExtension |NuGetQA 库"  
