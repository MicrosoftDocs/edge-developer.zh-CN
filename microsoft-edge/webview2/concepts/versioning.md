---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: a47c7295e87cf4295f8cdf898b62aa3b550aa9a5
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120337"
---
# <span data-ttu-id="cc5db-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="cc5db-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="cc5db-105">若要开发 WebView2 应用程序，必须安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 或 [非稳定的 Microsoft Edge 通道][MicrosoftedgeinsiderDownload]。</span><span class="sxs-lookup"><span data-stu-id="cc5db-105">To develop a WebView2 application, you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload].</span></span>  <span data-ttu-id="cc5db-106">SDK 的 NuGet 程序包版本中包含所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="cc5db-106">The minimum version that's required is included in the NuGet package version of the SDK.</span></span>  <span data-ttu-id="cc5db-107">例如，如果使用 `SDK package version 0.9.488` ，则必须安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 或 [不稳定的 Microsoft Edge 通道][MicrosoftedgeinsiderDownload] ，其内部版本号为488或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cc5db-107">For example, if you use the `SDK package version 0.9.488`, then you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of 488 or later.</span></span>  <span data-ttu-id="cc5db-108">还在 WebView2 [发行说明][Releasenotes]中指定所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="cc5db-108">The minimum version required is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="cc5db-109">WebView2 SDK 的新版本以与 Microsoft Edge (Chromium ) 浏览器相同的常规节奏提供，每六周大约每六周。</span><span class="sxs-lookup"><span data-stu-id="cc5db-109">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="cc5db-110">开发长时间 WebView2 应用程序时，请定期针对最新版本的 WebView2 运行时和非稳定的 Microsoft Edge 浏览器测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="cc5db-110">When developing Evergreen WebView2 applications, regularly test your application against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge browsers.</span></span>  <span data-ttu-id="cc5db-111">由于 web 平台不断发展，因此定期测试是确保应用程序按预期执行的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="cc5db-111">Because the web platform is constantly evolving, regular testing is the best way to ensure your application performs as intended.</span></span>  

## <span data-ttu-id="cc5db-112">发布和预发布程序包</span><span class="sxs-lookup"><span data-stu-id="cc5db-112">Release and prerelease package</span></span>  

<span data-ttu-id="cc5db-113">WebView2 NuGet 程序包包含发布和预发布程序包。</span><span class="sxs-lookup"><span data-stu-id="cc5db-113">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="cc5db-114">发布程序包向前兼容，包含 [Win32 C/c + + api][ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="cc5db-114">The release package is forward compatible and contains the [Win32 C/C++ APIs][ReferenceWin32].</span></span>  <span data-ttu-id="cc5db-115">此 SDK 中的 Api 完全受支持。</span><span class="sxs-lookup"><span data-stu-id="cc5db-115">APIs in this SDK are fully supported.</span></span>  

<span data-ttu-id="cc5db-116">预发布程序包是发布程序包的一个超集，下面列出了其他组件。</span><span class="sxs-lookup"><span data-stu-id="cc5db-116">The prerelease package is a superset of the release package with the additional components listed below.</span></span>  

*   <span data-ttu-id="cc5db-117">.NET Api： [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]和 [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span><span class="sxs-lookup"><span data-stu-id="cc5db-117">.NET APIs: [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span></span>  
*   <span data-ttu-id="cc5db-118">实验性 Api：有关详细信息，请导航到 [实验性 api](#experimental-apis) 部分。</span><span class="sxs-lookup"><span data-stu-id="cc5db-118">Experimental APIs:  For more information, navigate to the [Experimental APIs](#experimental-apis) section.</span></span>  

## <span data-ttu-id="cc5db-119">实验性 API</span><span class="sxs-lookup"><span data-stu-id="cc5db-119">Experimental APIs</span></span>  

<span data-ttu-id="cc5db-120">Web 视图团队正在测试未来版本中可能包含的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="cc5db-120">The WebView team is testing experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="cc5db-121">实验中的 Api 标记为 `experimental` 在 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="cc5db-121">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="cc5db-122">实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。</span><span class="sxs-lookup"><span data-stu-id="cc5db-122">Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="cc5db-123">你可以使用 [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。</span><span class="sxs-lookup"><span data-stu-id="cc5db-123">You can evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="cc5db-124">避免在生产应用中使用实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="cc5db-124">Avoid using the experimental APIs in production apps.</span></span>  

## <span data-ttu-id="cc5db-125">匹配 WebView2 运行时版本</span><span class="sxs-lookup"><span data-stu-id="cc5db-125">Matching WebView2 Runtime versions</span></span>  

<span data-ttu-id="cc5db-126">使用特定 SDK 版本编写 WebView2 应用时，你的应用的用户可以使用多个兼容版本的 WebView2 运行时运行它。</span><span class="sxs-lookup"><span data-stu-id="cc5db-126">When writing a WebView2 app using a particular SDK version, users of your app may run it with several compatible versions of the WebView2 Runtime.</span></span>  <span data-ttu-id="cc5db-127">Web 视图团队正在处理兼容的 WebView2 运行时版本，该版本包含来自以前版本的运行时和新的非实验性 Api 的非实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="cc5db-127">The WebView team is working on a compatible WebView2 Runtime version that contains non-experimental APIs from previous versions of the Runtime and new non-experimental APIs.</span></span>  

<span data-ttu-id="cc5db-128">请考虑以下项目，具体取决于您使用的是哪个 SDK：</span><span class="sxs-lookup"><span data-stu-id="cc5db-128">Depending on which SDK you use, consider the following items:</span></span> 

*   <span data-ttu-id="cc5db-129">**Win32 C/c + +**。</span><span class="sxs-lookup"><span data-stu-id="cc5db-129">**Win32 C/C++**.</span></span>  <span data-ttu-id="cc5db-130">使用 `QueryInterface` 获取新接口时，请检查返回值 `E_NOINTERFACE` 。</span><span class="sxs-lookup"><span data-stu-id="cc5db-130">When using `QueryInterface` to obtain a new interface, check for a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="cc5db-131">此值可能指示 WebView2 运行时是以前的版本，并且不支持该接口。</span><span class="sxs-lookup"><span data-stu-id="cc5db-131">This value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span>  
*   <span data-ttu-id="cc5db-132">**.Net 和 WinUI**。</span><span class="sxs-lookup"><span data-stu-id="cc5db-132">**.NET and WinUI**.</span></span>  <span data-ttu-id="cc5db-133">`No such interface supported`在使用已添加到最新 sdk 的方法、属性和事件时，检查异常。</span><span class="sxs-lookup"><span data-stu-id="cc5db-133">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="cc5db-134">如果 WebView2 运行时是早期版本，并且不支持这些 Api，则可能会发生此异常。</span><span class="sxs-lookup"><span data-stu-id="cc5db-134">This exception may occur when the WebView2 Runtime is a previous version, and doesn't support those APIs.</span></span>  

<span data-ttu-id="cc5db-135">如果 API 不可用，请考虑删除关联的功能，或通知用户他们需要更新其 WebView2 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="cc5db-135">If an API is unavailable, consider removing the associated feature, or inform your users that they need to update their version of the WebView2 Runtime.</span></span>  

<span data-ttu-id="cc5db-136">可从 SDK 向 SDK 引入、修改和删除实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="cc5db-136">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="cc5db-137">在已安装版本的 WebView2 运行时中，实验性 Api 可能不可用。</span><span class="sxs-lookup"><span data-stu-id="cc5db-137">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <span data-ttu-id="cc5db-138">路线图</span><span class="sxs-lookup"><span data-stu-id="cc5db-138">Roadmap</span></span>  

<span data-ttu-id="cc5db-139">发布包包含所有稳定的、受支持的 Win32 C/c + + Api。</span><span class="sxs-lookup"><span data-stu-id="cc5db-139">The release package contains all of the stable, supported Win32 C/C++ APIs.</span></span>  <span data-ttu-id="cc5db-140">将来，发布版程序包将包含所有稳定的、受支持的 .NET Api （当它们正式可用时）。</span><span class="sxs-lookup"><span data-stu-id="cc5db-140">In the future, the release package will contain all stable, supported .NET APIs when they are made generally available.</span></span>  <span data-ttu-id="cc5db-141">预发行程序包包含可能会根据你的反馈和共享见解更改的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="cc5db-141">The prerelease package contains experimental APIs that are subject to change based upon your feedback and shared insights.</span></span>  

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
