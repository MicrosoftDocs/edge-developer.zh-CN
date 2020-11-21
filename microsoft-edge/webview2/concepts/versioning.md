---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 132ccab0f9f378eedd8c83a7404c350161556f2e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182393"
---
# <span data-ttu-id="86519-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="86519-104">Understand WebView2 SDK versions</span></span>

<span data-ttu-id="86519-105">WebView2 SDK 的新版本以与 Microsoft Edge (Chromium ) 浏览器相同的常规节奏提供，每六周大约每六周。</span><span class="sxs-lookup"><span data-stu-id="86519-105">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

## <span data-ttu-id="86519-106">发布和预发布程序包</span><span class="sxs-lookup"><span data-stu-id="86519-106">Release and prerelease package</span></span>  

<span data-ttu-id="86519-107">WebView2 NuGet 程序包包含发布和预发布程序包。</span><span class="sxs-lookup"><span data-stu-id="86519-107">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="86519-108">发布程序包向前兼容，包含 [Win32 C/c + + api][ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="86519-108">The release package is forward compatible and contains the [Win32 C/C++ APIs][ReferenceWin32].</span></span>  <span data-ttu-id="86519-109">此 SDK 中的 Api 完全受支持。</span><span class="sxs-lookup"><span data-stu-id="86519-109">APIs in this SDK are fully supported.</span></span>  

<span data-ttu-id="86519-110">预发布程序包是发布程序包的一个超集，下面列出了其他组件。</span><span class="sxs-lookup"><span data-stu-id="86519-110">The prerelease package is a superset of the release package with the additional components listed below.</span></span>  

*   <span data-ttu-id="86519-111">.NET Api： [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]和 [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span><span class="sxs-lookup"><span data-stu-id="86519-111">.NET APIs: [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span></span>  
*   <span data-ttu-id="86519-112">实验性 Api：有关详细信息，请导航到 [实验性 api](#experimental-apis) 部分。</span><span class="sxs-lookup"><span data-stu-id="86519-112">Experimental APIs:  For more information, navigate to the [Experimental APIs](#experimental-apis) section.</span></span>  

### <span data-ttu-id="86519-113">路线图</span><span class="sxs-lookup"><span data-stu-id="86519-113">Roadmap</span></span>  

<span data-ttu-id="86519-114">发布包包含所有稳定的、受支持的 Win32 C/c + + Api。</span><span class="sxs-lookup"><span data-stu-id="86519-114">The release package contains all of the stable, supported Win32 C/C++ APIs.</span></span>  <span data-ttu-id="86519-115">将来，发布版程序包将包含所有稳定的、受支持的 .NET Api （当它们正式可用时）。</span><span class="sxs-lookup"><span data-stu-id="86519-115">In the future, the release package will contain all stable, supported .NET APIs when they're made generally available.</span></span>  <span data-ttu-id="86519-116">预发布程序包包含可能会根据你的反馈进行更改的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="86519-116">The prerelease package contains experimental APIs that are subject to change based on your feedback.</span></span> 

## <span data-ttu-id="86519-117">实验性 API</span><span class="sxs-lookup"><span data-stu-id="86519-117">Experimental APIs</span></span>  

<span data-ttu-id="86519-118">Web 视图团队正在查找未来版本中可能包含的实验性 Api 的反馈。</span><span class="sxs-lookup"><span data-stu-id="86519-118">The WebView team is seeking feedback on experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="86519-119">实验中的 Api 标记为 `experimental` 在 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="86519-119">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="86519-120">你可以使用 [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。</span><span class="sxs-lookup"><span data-stu-id="86519-120">You can evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="86519-121">可从 SDK 向 SDK 引入、修改和删除实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="86519-121">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="86519-122">避免在生产应用中使用实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="86519-122">Avoid using the experimental APIs in production apps.</span></span>  

> [!NOTE]
> <span data-ttu-id="86519-123">在已安装版本的 WebView2 运行时中，实验性 Api 可能不可用。</span><span class="sxs-lookup"><span data-stu-id="86519-123">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <span data-ttu-id="86519-124">匹配 WebView2 运行时版本</span><span class="sxs-lookup"><span data-stu-id="86519-124">Matching WebView2 Runtime versions</span></span>  
<span data-ttu-id="86519-125">WebView2 应用程序要求用户安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="86519-125">WebView2 applications require users to install a [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2].</span></span> <span data-ttu-id="86519-126">WebView2 运行时将自动更新到最新的可用版本。</span><span class="sxs-lookup"><span data-stu-id="86519-126">The WebView2 Runtime updates automatically to the latest version that's available.</span></span> <span data-ttu-id="86519-127">在某些情况下，用户可能需要停止自动 WebView2 运行时更新，这可能会导致应用程序兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="86519-127">In some scenarios, users may need to stop automatic WebView2 Runtime updates, which can cause application compatibility issues.</span></span>

<span data-ttu-id="86519-128">如果 WebView2 运行时更新已停止，请确保你了解你的应用程序所需的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="86519-128">If WebView2 Runtime updates are stopped, ensure you understand the minimum version of the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] that's required by your application.</span></span> <span data-ttu-id="86519-129">请考虑以下两个项目：</span><span class="sxs-lookup"><span data-stu-id="86519-129">Consider the following two items:</span></span>  

1. <span data-ttu-id="86519-130">SDK 的最低要求版本可在 WebView2 [发行说明][Releasenotes] 中的 **最低 WebView2 运行时版本**下找到。</span><span class="sxs-lookup"><span data-stu-id="86519-130">The minimum required version of the SDK, which can be found in the WebView2 [Release Notes][Releasenotes] under **minimum WebView2 Runtime version**.</span></span> <span data-ttu-id="86519-131">例如，对于 SDK 版本[1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222)，你必须安装[WebView2 运行时][MicrosoftDeveloperEdgeWebview2]或具有**86.0.616.0**或更高版本号的[非稳定 Microsoft Edge 通道][MicrosoftedgeinsiderDownload]。</span><span class="sxs-lookup"><span data-stu-id="86519-131">For example, for SDK version [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222), you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of **86.0.616.0** or later.</span></span> <span data-ttu-id="86519-132">只有当 web 平台中存在重大更改时，SDK 所需的最低版本才会更改。</span><span class="sxs-lookup"><span data-stu-id="86519-132">The minimum version required by the SDK will only change when there's a breaking change in the web platform.</span></span>

2. <span data-ttu-id="86519-133">支持应用中使用的接口和 Api 所需的 NuGet 程序包所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="86519-133">The minimum required version of the NuGet package that's required to support the interfaces and APIs used in your app.</span></span> <span data-ttu-id="86519-134">新的接口和 Api 会定期添加到 WebView2。</span><span class="sxs-lookup"><span data-stu-id="86519-134">New interfaces and APIs are added periodically to WebView2.</span></span> <span data-ttu-id="86519-135">在 SDK 中捆绑的 Api 和接口将需要不同版本的 WebView2 运行时，因为它们在不同的时间添加到了 SDK。</span><span class="sxs-lookup"><span data-stu-id="86519-135">APIs and interfaces bundled in an SDK will require different versions of the WebView2 Runtime because they were added to the SDK at different times.</span></span>  <span data-ttu-id="86519-136">所需的 WebView2 运行时版本与第一次引入 API 的 SDK 版本的内部版本号（第三个数字）相匹配。</span><span class="sxs-lookup"><span data-stu-id="86519-136">The required WebView2 Runtime version matches the build number, the third number, of the SDK version the API was first introduced in.</span></span> <span data-ttu-id="86519-137">例如，SDK 版本 [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222) 中添加的新 API 或接口将需要 WebView2 运行时版本：86.0。**622**。</span><span class="sxs-lookup"><span data-stu-id="86519-137">For example, a new API or interface added in SDK version [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222) will need the WebView2 Runtime version: 86.0.**622**.0.</span></span> <span data-ttu-id="86519-138">在后续 SDK 版本中添加的 API 或接口需要具有与 SDK 相同版本号的 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="86519-138">An API or interface added in a subsequent SDK release requires the WebView2 Runtime that has the same version number as the SDK.</span></span> <span data-ttu-id="86519-139">你可以确定 WebView2 运行时版本是否支持 [以编程方式](#determine-webview2-runtime-requirement)支持接口或 API。</span><span class="sxs-lookup"><span data-stu-id="86519-139">You can determine if the WebView2 Runtime version supports an interface or API [programmatically](#determine-webview2-runtime-requirement).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86519-140">开发长时间 [WebView2 应用程序](distribution.md#evergreen-distribution-mode)时，请定期针对最新版本的 WebView2 运行时和非稳定的 Microsoft Edge 浏览器测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="86519-140">When developing [Evergreen WebView2 applications](distribution.md#evergreen-distribution-mode), regularly test your application against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge browsers.</span></span>  <span data-ttu-id="86519-141">由于 web 平台不断发展，因此定期测试是确保应用程序按预期执行的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="86519-141">Because the web platform is constantly evolving, regular testing is the best way to ensure your application performs as intended.</span></span>  

### <span data-ttu-id="86519-142">确定 WebView2 运行时要求</span><span class="sxs-lookup"><span data-stu-id="86519-142">Determine WebView2 Runtime requirement</span></span>

<span data-ttu-id="86519-143">请考虑以下项目，具体取决于您使用的是哪个 SDK：</span><span class="sxs-lookup"><span data-stu-id="86519-143">Depending on which SDK you use, consider the following items:</span></span> 

*   <span data-ttu-id="86519-144">**Win32 C/c + +**。</span><span class="sxs-lookup"><span data-stu-id="86519-144">**Win32 C/C++**.</span></span>  <span data-ttu-id="86519-145">使用 `QueryInterface` 获取新接口时，请检查返回值 `E_NOINTERFACE` 。</span><span class="sxs-lookup"><span data-stu-id="86519-145">When using `QueryInterface` to obtain a new interface, check for a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="86519-146">此值可能指示 WebView2 运行时是以前的版本，并且不支持该接口。</span><span class="sxs-lookup"><span data-stu-id="86519-146">This value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span> <span data-ttu-id="86519-147">导航到 WebView2API 示例以查看其工作原理的 [示例](https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622) 。</span><span class="sxs-lookup"><span data-stu-id="86519-147">Navigate to the WebView2API Sample for an [example](https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622) of how this works.</span></span>
*   <span data-ttu-id="86519-148">**.Net 和 WinUI**。</span><span class="sxs-lookup"><span data-stu-id="86519-148">**.NET and WinUI**.</span></span>  <span data-ttu-id="86519-149">`No such interface supported`在使用已添加到最新 sdk 的方法、属性和事件时，检查异常。</span><span class="sxs-lookup"><span data-stu-id="86519-149">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="86519-150">如果 WebView2 运行时是早期版本，并且不支持这些 Api，则可能会发生此异常。</span><span class="sxs-lookup"><span data-stu-id="86519-150">This exception may occur when the WebView2 Runtime is a previous version, and doesn't support those APIs.</span></span>  

<span data-ttu-id="86519-151">如果 API 不可用，请考虑删除关联的功能，或通知用户他们需要更新其 WebView2 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="86519-151">If an API is unavailable, consider removing the associated feature, or inform your users that they need to update their version of the WebView2 Runtime.</span></span>  



 

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->  

[Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 命名空间 | WebView2 命名空间 |Microsoft 文档"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 c + + 参考 |Microsoft 文档"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 开发人员"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  
