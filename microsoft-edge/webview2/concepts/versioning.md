---
description: 用于 Microsoft Edge WebView2 的版本模型
title: 了解 WebView2 SDK 版本
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b292f59e264293a958eb619d04b751203cb517ac
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461176"
---
# <a name="understand-webview2-sdk-versions"></a><span data-ttu-id="4f73a-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="4f73a-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="4f73a-105">新版本的 WebView2 SDK 的发布常规节奏与 Microsoft Edge \ (Chromium\) 浏览器相同，大约每六周发布一次。</span><span class="sxs-lookup"><span data-stu-id="4f73a-105">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

## <a name="release-and-prerelease-package"></a><span data-ttu-id="4f73a-106">发布和预发布包</span><span class="sxs-lookup"><span data-stu-id="4f73a-106">Release and prerelease package</span></span>  

<span data-ttu-id="4f73a-107">WebView2 NuGet 程序包包含发布和预发布包。</span><span class="sxs-lookup"><span data-stu-id="4f73a-107">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="4f73a-108">发布 **包与** 向前兼容，并包含以下组件。</span><span class="sxs-lookup"><span data-stu-id="4f73a-108">The **release package** is forward compatible and contains the following components.</span></span>  

*   [<span data-ttu-id="4f73a-109">Win32 C/C++ API</span><span class="sxs-lookup"><span data-stu-id="4f73a-109">Win32 C/C++ APIs</span></span>][ReferenceWin32]
*   <span data-ttu-id="4f73a-110">.NET [API：WPF、WinForms][DotnetMicrosoftWebWebview2WpfNamespace]和[Core][DotnetMicrosoftWebWebview2CoreNamespace]。 [][DotnetMicrosoftWebWebview2WinformsNamespace]</span><span class="sxs-lookup"><span data-stu-id="4f73a-110">.NET APIs:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace].</span></span>  
    
<span data-ttu-id="4f73a-111">SDK 中的 API 完全受支持。</span><span class="sxs-lookup"><span data-stu-id="4f73a-111">APIs in the SDK are fully supported.</span></span>  

<span data-ttu-id="4f73a-112">**预发布包是**包含实验性 API 的发布包[的超集](#experimental-apis)。</span><span class="sxs-lookup"><span data-stu-id="4f73a-112">The **prerelease package** is a superset of the release package with [Experimental APIs](#experimental-apis).</span></span>  <span data-ttu-id="4f73a-113">避免使用预发布 SDK 生成生产应用。</span><span class="sxs-lookup"><span data-stu-id="4f73a-113">Avoid using the prerelease SDK to build production apps.</span></span>  

### <a name="roadmap"></a><span data-ttu-id="4f73a-114">路线图</span><span class="sxs-lookup"><span data-stu-id="4f73a-114">Roadmap</span></span>  

<span data-ttu-id="4f73a-115">该发行版包含所有稳定且受支持的 Win32 C/C++ 和 .NET API。</span><span class="sxs-lookup"><span data-stu-id="4f73a-115">The release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="4f73a-116">预发布包包含实验性 API，这些 API 可能会根据你的反馈发生变化。</span><span class="sxs-lookup"><span data-stu-id="4f73a-116">The prerelease package contains experimental APIs that are subject to change based on your feedback.</span></span>  

## <a name="experimental-apis"></a><span data-ttu-id="4f73a-117">实验性 API</span><span class="sxs-lookup"><span data-stu-id="4f73a-117">Experimental APIs</span></span>  

<span data-ttu-id="4f73a-118">WebView 团队正在寻求有关将来版本中可能包含的实验性 API 的反馈。</span><span class="sxs-lookup"><span data-stu-id="4f73a-118">The WebView team is seeking feedback on experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="4f73a-119">实验性 API 在 `experimental` SDK 中标记为 。</span><span class="sxs-lookup"><span data-stu-id="4f73a-119">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="4f73a-120">若要帮助你评估实验性 API 并分享你的反馈，请导航到 [WebView 反馈存储库][GithubMicrosoftedgeWebviewfeedback]。</span><span class="sxs-lookup"><span data-stu-id="4f73a-120">To help you evaluate the Experimental APIs and share your feedback, navigate to the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="4f73a-121">实验性 API 可以在 SDK 中引入、修改和删除。</span><span class="sxs-lookup"><span data-stu-id="4f73a-121">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="4f73a-122">避免在生产应用中使用实验性 API。</span><span class="sxs-lookup"><span data-stu-id="4f73a-122">Avoid using the experimental APIs in production apps.</span></span>  

> [!NOTE]
> <span data-ttu-id="4f73a-123">实验性 API 可能在你的已安装版本的 WebView2 运行时中不可用。</span><span class="sxs-lookup"><span data-stu-id="4f73a-123">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <a name="matching-webview2-runtime-versions"></a><span data-ttu-id="4f73a-124">匹配的 WebView2 运行时版本</span><span class="sxs-lookup"><span data-stu-id="4f73a-124">Matching WebView2 Runtime versions</span></span>  
<span data-ttu-id="4f73a-125">WebView2 应用要求用户安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="4f73a-125">WebView2 apps require users to install a [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2].</span></span>  <span data-ttu-id="4f73a-126">WebView2 运行时自动更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="4f73a-126">The WebView2 Runtime automatically updates to the latest version available.</span></span>  <span data-ttu-id="4f73a-127">在某些情况下，用户可能需要停止自动 WebView2 运行时更新，这可能会导致应用兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="4f73a-127">In some scenarios, users may want to stop automatic WebView2 Runtime updates, which may cause app compatibility issues.</span></span>  

<span data-ttu-id="4f73a-128">如果 WebView2 运行时更新已停止，请确保了解应用所需的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="4f73a-128">If WebView2 Runtime updates are stopped, ensure you understand the minimum version of the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] required by your app.</span></span>  <span data-ttu-id="4f73a-129">请考虑以下两项：</span><span class="sxs-lookup"><span data-stu-id="4f73a-129">Consider the following two items:</span></span>  

1.  <span data-ttu-id="4f73a-130">若要成功加载 webview2 实例，需要 SDK 的最低版本，可以在要加载的最低 Microsoft [][Webview2Releasenotes] Edge 版本下的 WebView2**发行说明找到**。</span><span class="sxs-lookup"><span data-stu-id="4f73a-130">The minimum required version of the SDK in order to successfully load a webview2 instance is found in the WebView2 [Release Notes][Webview2Releasenotes] under **Minimum Microsoft Edge version to load**.</span></span>  <span data-ttu-id="4f73a-131">SDK 需要加载的最低版本仅在 Web 平台发生重大变化时更改。</span><span class="sxs-lookup"><span data-stu-id="4f73a-131">The minimum version to load required by the SDK only changes when a breaking change occurs in the web platform.</span></span>  <span data-ttu-id="4f73a-132">例如，对于 SDK [版本 1.0.622.22，][Webview2Releasenotes1062222]必须安装具有内部版本号或更新版本的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 或非稳定 [Microsoft Edge][MicrosoftedgeinsiderDownload] 通道 `86.0.616.0` 。</span><span class="sxs-lookup"><span data-stu-id="4f73a-132">For example, for SDK version [1.0.622.22][Webview2Releasenotes1062222], you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of `86.0.616.0` or newer.</span></span>   
1.  <span data-ttu-id="4f73a-133">支持应用中的接口和 API 所需的 NuGet 程序包的最低必需版本位于完全 API 兼容性下的 WebView2 [][Webview2Releasenotes]**发行说明中**。</span><span class="sxs-lookup"><span data-stu-id="4f73a-133">The minimum required version of the NuGet package required to support the interfaces and APIs in your app is found in the WebView2 [Release Notes][Webview2Releasenotes] under **Full API Compatibility**.</span></span>  <span data-ttu-id="4f73a-134">新接口和 API 会定期添加到 WebView2。</span><span class="sxs-lookup"><span data-stu-id="4f73a-134">New interfaces and APIs are added periodically to WebView2.</span></span>  <span data-ttu-id="4f73a-135">捆绑在 SDK 中的 API 和接口需要不同版本的 WebView2 运行时，因为 API 和接口会在不同的时间添加到 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="4f73a-135">APIs and interfaces bundled in an SDK require different versions of the WebView2 Runtime, because APIs and interface are added to the SDK at different times.</span></span>  <span data-ttu-id="4f73a-136">所需的 WebView2 运行时版本与首次引入 API 的 SDK 版本的内部版本号（即第三个数字）匹配。</span><span class="sxs-lookup"><span data-stu-id="4f73a-136">The required WebView2 Runtime version matches the build number, the third number, of the SDK version the API was first introduced in.</span></span>  <span data-ttu-id="4f73a-137">例如，在 SDK 版本 [1.0.622.22][Webview2Releasenotes1062222] 中添加的新 API 或接口需要 WebView2 运行时版本 `86.0.622.0` 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4f73a-137">For example, a new API or interface added in SDK version [1.0.622.22][Webview2Releasenotes1062222] requires the WebView2 Runtime version `86.0.622.0` or newer.</span></span>  <span data-ttu-id="4f73a-138">在稍后的 SDK 版本中添加的 API 或接口需要与 SDK 版本号相同的 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="4f73a-138">An API or interface added in a later SDK release requires a WebView2 Runtime that has the same version number as the SDK.</span></span>  <span data-ttu-id="4f73a-139">若要帮助你确定 WebView2 运行时版本是否支持接口或 API，请导航到确定 [WebView2 运行时要求](#determine-webview2-runtime-requirement)。</span><span class="sxs-lookup"><span data-stu-id="4f73a-139">To help you determine if the WebView2 Runtime version supports an interface or API, navigate to [Determine WebView2 Runtime requirement](#determine-webview2-runtime-requirement).</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="4f73a-140">开发 [Evergreen WebView2][Webview2ConceptsDistributionEvergreenDistributionMode]应用时，定期针对最新版本的 WebView2 运行时和非稳定 Microsoft Edge 渠道测试你的应用。</span><span class="sxs-lookup"><span data-stu-id="4f73a-140">When developing [Evergreen WebView2 apps][Webview2ConceptsDistributionEvergreenDistributionMode], regularly test your app against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge channels.</span></span>  <span data-ttu-id="4f73a-141">由于 Web 平台在不断演变，因此定期测试是确保应用按预期运行的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="4f73a-141">Because the web platform is constantly evolving, regular testing is the best way to ensure your app performs as intended.</span></span>  

### <a name="determine-webview2-runtime-requirement"></a><span data-ttu-id="4f73a-142">确定 WebView2 运行时要求</span><span class="sxs-lookup"><span data-stu-id="4f73a-142">Determine WebView2 Runtime requirement</span></span>  

<span data-ttu-id="4f73a-143">根据你使用哪个 SDK，请考虑以下项：</span><span class="sxs-lookup"><span data-stu-id="4f73a-143">Depending on which SDK you use, consider the following items:</span></span>  

*   <span data-ttu-id="4f73a-144">**Win32 C/C++**。</span><span class="sxs-lookup"><span data-stu-id="4f73a-144">**Win32 C/C++**.</span></span>  <span data-ttu-id="4f73a-145">使用 `QueryInterface` 获取新接口时，请验证 的返回值 `E_NOINTERFACE` 。</span><span class="sxs-lookup"><span data-stu-id="4f73a-145">When using `QueryInterface` to obtain a new interface, verify a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="4f73a-146">值可能指示 WebView2 运行时是早期版本，并且不支持该接口。</span><span class="sxs-lookup"><span data-stu-id="4f73a-146">The value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span>  <span data-ttu-id="4f73a-147">有关其工作方式的示例，请导航到第 [622 行 - AppWindow.cpp][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]。</span><span class="sxs-lookup"><span data-stu-id="4f73a-147">For an example of how it works, navigate to [Line 622 - AppWindow.cpp][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622].</span></span>  
*   <span data-ttu-id="4f73a-148">**.NET 和 WinUI**。</span><span class="sxs-lookup"><span data-stu-id="4f73a-148">**.NET and WinUI**.</span></span>  <span data-ttu-id="4f73a-149">在使用已添加到最新 SDK 的方法、属性和事件时检查 `No such interface supported` 异常。</span><span class="sxs-lookup"><span data-stu-id="4f73a-149">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="4f73a-150">当 WebView2 运行时是早期版本，并且不支持 API 时，可能会发生异常。</span><span class="sxs-lookup"><span data-stu-id="4f73a-150">The exception may occur when the WebView2 Runtime is a previous version, and does not support the APIs.</span></span>  
    
<span data-ttu-id="4f73a-151">如果 API 不可用，请考虑删除关联的功能，或通知用户需要更新 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="4f73a-151">If an API is unavailable, consider removing the associated feature, or inform your users that an update to the WebView2 Runtime is required.</span></span>  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "常青分发模式 - 使用 WebView2 分配|Microsoft Docs"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK |Microsoft Docs"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22 - WebView2 SDK |Microsoft Docs"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述|Microsoft Docs"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 命名空间|Microsoft Docs"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 命名空间|Microsoft Docs"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 命名空间|Microsoft Docs"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ 参考|Microsoft Docs"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 开发人员"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "第 622 行 - AppWindow.cpp - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  
