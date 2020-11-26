---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 54d62de00a89a3c433fd77e9ec20945adbfc19c3
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "11191608"
---
# <span data-ttu-id="9b94c-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="9b94c-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="9b94c-105">WebView2 SDK 的新版本以与 Microsoft Edge (Chromium ) 浏览器相同的常规节奏提供，每六周大约每六周。</span><span class="sxs-lookup"><span data-stu-id="9b94c-105">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

## <span data-ttu-id="9b94c-106">发布和预发布程序包</span><span class="sxs-lookup"><span data-stu-id="9b94c-106">Release and prerelease package</span></span>  

<span data-ttu-id="9b94c-107">WebView2 NuGet 程序包包含发布和预发布程序包。</span><span class="sxs-lookup"><span data-stu-id="9b94c-107">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="9b94c-108">**发布程序包**向前兼容，包含以下组件。</span><span class="sxs-lookup"><span data-stu-id="9b94c-108">The **release package** is forward compatible and contains the following components.</span></span>  

*   [<span data-ttu-id="9b94c-109">Win32 C/c + + Api</span><span class="sxs-lookup"><span data-stu-id="9b94c-109">Win32 C/C++ APIs</span></span>][ReferenceWin32]
*   <span data-ttu-id="9b94c-110">.NET Api：  [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]和 [Core][DotnetMicrosoftWebWebview2CoreNamespace]。</span><span class="sxs-lookup"><span data-stu-id="9b94c-110">.NET APIs:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace].</span></span>  
    
<span data-ttu-id="9b94c-111">SDK 中的 Api 完全受支持。</span><span class="sxs-lookup"><span data-stu-id="9b94c-111">APIs in the SDK are fully supported.</span></span>  

<span data-ttu-id="9b94c-112">**预发布程序包**是发布程序包的一个包含实验性[api](#experimental-apis)的超集。</span><span class="sxs-lookup"><span data-stu-id="9b94c-112">The **prerelease package** is a superset of the release package with [Experimental APIs](#experimental-apis).</span></span>  

### <span data-ttu-id="9b94c-113">路线图</span><span class="sxs-lookup"><span data-stu-id="9b94c-113">Roadmap</span></span>  

<span data-ttu-id="9b94c-114">发布包包含所有稳定、受支持的 Win32 C/c + + 和 .NET Api。</span><span class="sxs-lookup"><span data-stu-id="9b94c-114">The release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="9b94c-115">预发布程序包包含可能会根据你的反馈进行更改的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="9b94c-115">The prerelease package contains experimental APIs that are subject to change based on your feedback.</span></span>  

## <span data-ttu-id="9b94c-116">实验性 API</span><span class="sxs-lookup"><span data-stu-id="9b94c-116">Experimental APIs</span></span>  

<span data-ttu-id="9b94c-117">Web 视图团队正在查找未来版本中可能包含的实验性 Api 的反馈。</span><span class="sxs-lookup"><span data-stu-id="9b94c-117">The WebView team is seeking feedback on experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="9b94c-118">实验中的 Api 标记为 `experimental` 在 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="9b94c-118">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="9b94c-119">若要帮助你评估实验性 Api 并共享你的反馈，请导航到 " [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]" 存储库。</span><span class="sxs-lookup"><span data-stu-id="9b94c-119">To help you evaluate the Experimental APIs and share your feedback, navigate to the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="9b94c-120">可从 SDK 向 SDK 引入、修改和删除实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="9b94c-120">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="9b94c-121">避免在生产应用中使用实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="9b94c-121">Avoid using the experimental APIs in production apps.</span></span>  

> [!NOTE]
> <span data-ttu-id="9b94c-122">在已安装版本的 WebView2 运行时中，实验性 Api 可能不可用。</span><span class="sxs-lookup"><span data-stu-id="9b94c-122">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <span data-ttu-id="9b94c-123">匹配 WebView2 运行时版本</span><span class="sxs-lookup"><span data-stu-id="9b94c-123">Matching WebView2 Runtime versions</span></span>  
<span data-ttu-id="9b94c-124">WebView2 应用需要用户安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="9b94c-124">WebView2 apps require users to install a [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2].</span></span>  <span data-ttu-id="9b94c-125">WebView2 运行时将自动更新到最新版本的可用版本。</span><span class="sxs-lookup"><span data-stu-id="9b94c-125">The WebView2 Runtime automatically updates to the latest version available.</span></span>  <span data-ttu-id="9b94c-126">在某些情况下，用户可能希望停止自动 WebView2 运行时更新，这可能会导致应用兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="9b94c-126">In some scenarios, users may want to stop automatic WebView2 Runtime updates, which may cause app compatibility issues.</span></span>  

<span data-ttu-id="9b94c-127">如果停止 WebView2 运行时更新，请确保你了解你的应用所需的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="9b94c-127">If WebView2 Runtime updates are stopped, ensure you understand the minimum version of the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] required by your app.</span></span>  <span data-ttu-id="9b94c-128">请考虑以下两个项目：</span><span class="sxs-lookup"><span data-stu-id="9b94c-128">Consider the following two items:</span></span>  

1.  <span data-ttu-id="9b94c-129">SDK 的最低要求版本在 WebView2 [发行说明][Webview2Releasenotes] 中的 " **最低 WebView2 运行时版本**" 下找到。</span><span class="sxs-lookup"><span data-stu-id="9b94c-129">The minimum required version of the SDK, in found in the WebView2 [Release Notes][Webview2Releasenotes] under **minimum WebView2 Runtime version**.</span></span>  <span data-ttu-id="9b94c-130">例如，对于 SDK 版本 [1.0.622.22][Webview2Releasenotes1062222]，你必须使用内部版本号或更高版本安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 或 [非稳定 Microsoft Edge 通道][MicrosoftedgeinsiderDownload] `86.0.616.0` 。</span><span class="sxs-lookup"><span data-stu-id="9b94c-130">For example, for SDK version [1.0.622.22][Webview2Releasenotes1062222], you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of `86.0.616.0` or later.</span></span>  <span data-ttu-id="9b94c-131">只有当 web 平台中发生重大更改时，SDK 所需的最低版本才会发生更改。</span><span class="sxs-lookup"><span data-stu-id="9b94c-131">The minimum version required by the SDK only changes when a breaking change occurs in the web platform.</span></span>  
1.  <span data-ttu-id="9b94c-132">支持你在应用中使用的接口和 Api 所需的最低版本的 NuGet 程序包。</span><span class="sxs-lookup"><span data-stu-id="9b94c-132">The minimum required version of the NuGet package required to support the interfaces and APIs that you use in your app.</span></span>  <span data-ttu-id="9b94c-133">新的接口和 Api 会定期添加到 WebView2。</span><span class="sxs-lookup"><span data-stu-id="9b94c-133">New interfaces and APIs are added periodically to WebView2.</span></span>  <span data-ttu-id="9b94c-134">在 SDK 中捆绑的 Api 和接口需要不同版本的 WebView2 运行时，因为 Api 和接口在不同的时间添加到了 SDK。</span><span class="sxs-lookup"><span data-stu-id="9b94c-134">APIs and interfaces bundled in an SDK require different versions of the WebView2 Runtime, because APIs and interface are added to the SDK at different times.</span></span>  <span data-ttu-id="9b94c-135">所需的 WebView2 运行时版本与第一次引入 API 的 SDK 版本的内部版本号（第三个数字）相匹配。</span><span class="sxs-lookup"><span data-stu-id="9b94c-135">The required WebView2 Runtime version matches the build number, the third number, of the SDK version the API was first introduced in.</span></span>  <span data-ttu-id="9b94c-136">例如，在 SDK 版本 [1.0.622.22][Webview2Releasenotes1062222] 中添加的新 API 或接口需要 WebView2 运行时版本：  `86.0.622.0`  在更高版本的 SDK 版本中添加的 api 或接口需要具有与 SDK 相同的版本号的 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="9b94c-136">For example, a new API or interface added in SDK version [1.0.622.22][Webview2Releasenotes1062222] requires the WebView2 Runtime version:  `86.0.622.0`  An API or interface added in a later SDK release requires the WebView2 Runtime that has the same version number as the SDK.</span></span>  <span data-ttu-id="9b94c-137">为了帮助你确定 WebView2 运行时版本是否支持接口或 API，请导航以 [确定 WebView2 运行时要求](#determine-webview2-runtime-requirement)。</span><span class="sxs-lookup"><span data-stu-id="9b94c-137">To help you determine if the WebView2 Runtime version supports an interface or API, navigate to [Determine WebView2 Runtime requirement](#determine-webview2-runtime-requirement).</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="9b94c-138">开发长时间 [WebView2 应用][Webview2ConceptsDistributionEvergreenDistributionMode]时，请定期针对最新版本的 WebView2 运行时和非稳定的 Microsoft Edge 浏览器测试你的应用。</span><span class="sxs-lookup"><span data-stu-id="9b94c-138">When developing [Evergreen WebView2 apps][Webview2ConceptsDistributionEvergreenDistributionMode], regularly test your app against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge browsers.</span></span>  <span data-ttu-id="9b94c-139">由于 web 平台不断发展，因此定期测试是确保你的应用按预期执行的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="9b94c-139">Because the web platform is constantly evolving, regular testing is the best way to ensure your app performs as intended.</span></span>  

### <span data-ttu-id="9b94c-140">确定 WebView2 运行时要求</span><span class="sxs-lookup"><span data-stu-id="9b94c-140">Determine WebView2 Runtime requirement</span></span>  

<span data-ttu-id="9b94c-141">请考虑以下项目，具体取决于您使用的是哪个 SDK：</span><span class="sxs-lookup"><span data-stu-id="9b94c-141">Depending on which SDK you use, consider the following items:</span></span>  

*   <span data-ttu-id="9b94c-142">**Win32 C/c + +**。</span><span class="sxs-lookup"><span data-stu-id="9b94c-142">**Win32 C/C++**.</span></span>  <span data-ttu-id="9b94c-143">使用 `QueryInterface` 获取新接口时，请验证返回值 `E_NOINTERFACE` 。</span><span class="sxs-lookup"><span data-stu-id="9b94c-143">When using `QueryInterface` to obtain a new interface, verify a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="9b94c-144">该值可能指示 WebView2 运行时是以前的版本，并且不支持该接口。</span><span class="sxs-lookup"><span data-stu-id="9b94c-144">The value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span>  <span data-ttu-id="9b94c-145">有关其工作原理的示例，请导航到 " [行 622-AppWindow][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]"。</span><span class="sxs-lookup"><span data-stu-id="9b94c-145">For an example of how it works, navigate to [Line 622 - AppWindow.cpp][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622].</span></span>  
*   <span data-ttu-id="9b94c-146">**.Net 和 WinUI**。</span><span class="sxs-lookup"><span data-stu-id="9b94c-146">**.NET and WinUI**.</span></span>  <span data-ttu-id="9b94c-147">`No such interface supported`在使用已添加到最新 sdk 的方法、属性和事件时，检查异常。</span><span class="sxs-lookup"><span data-stu-id="9b94c-147">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="9b94c-148">当 WebView2 运行时是早期版本且不支持 Api 时，可能会发生异常。</span><span class="sxs-lookup"><span data-stu-id="9b94c-148">The exception may occur when the WebView2 Runtime is a previous version, and does not support the APIs.</span></span>  
    
<span data-ttu-id="9b94c-149">如果 API 不可用，请考虑删除关联的功能，或通知用户需要 WebView2 运行时的更新。</span><span class="sxs-lookup"><span data-stu-id="9b94c-149">If an API is unavailable, consider removing the associated feature, or inform your users that an update to the WebView2 Runtime is required.</span></span>  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用分发Microsoft 文档"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22-WebView2 SDK 的发行说明 |Microsoft 文档"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 命名空间 | WebView2 命名空间 |Microsoft 文档"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 c + + 参考 |Microsoft 文档"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 开发人员"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "Line 622-AppWindow-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  
