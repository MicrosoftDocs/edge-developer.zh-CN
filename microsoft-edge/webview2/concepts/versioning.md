---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b673a2b250e46959a2eabaeb88cd8535f9a271e4
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "11118980"
---
# <span data-ttu-id="d3c34-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="d3c34-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="d3c34-105">WebView2 依赖于 Microsoft Edge 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="d3c34-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="d3c34-106">每个 WebView2 SDK 都要求安装最低版本的浏览器。</span><span class="sxs-lookup"><span data-stu-id="d3c34-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="d3c34-107">最小版本反映在 SDK 的程序包版本中。</span><span class="sxs-lookup"><span data-stu-id="d3c34-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="d3c34-108">例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d3c34-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="d3c34-109">浏览器版本也在 WebView2 [发行说明][Releasenotes]中指定。</span><span class="sxs-lookup"><span data-stu-id="d3c34-109">The browser version is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="d3c34-110">有关最新版本的 Microsoft Edge 浏览器的详细信息，请导航到 [浏览器频道][DeployedgeChannels]。</span><span class="sxs-lookup"><span data-stu-id="d3c34-110">For more information about the latest release of the Microsoft Edge browser, navigate to [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="d3c34-111">WebView2 当前处于预览版中。</span><span class="sxs-lookup"><span data-stu-id="d3c34-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="d3c34-112">尽管 Web 视图团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但不能保证它，因为较新版本的浏览器可能不支持以前的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="d3c34-112">While the WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed because newer versions of the browser may not support previous SDK versions.</span></span>  <span data-ttu-id="d3c34-113">如果浏览器版本和 Sdk 之间存在重大更改，则会在 [发行说明][Releasenotes]中指定这些更改。</span><span class="sxs-lookup"><span data-stu-id="d3c34-113">If there are breaking changes between browser versions and SDKs, the changes are specified in the [Release Notes][Releasenotes].</span></span>  

<span data-ttu-id="d3c34-114">将来，Web 视图团队计划更改 WebView2 应用的分布模型。</span><span class="sxs-lookup"><span data-stu-id="d3c34-114">In the future, the WebView team plans to change the distribution model for WebView2 apps.</span></span>  <span data-ttu-id="d3c34-115">有关详细信息，请导航到长 [绿分布模式][DistributionEvergreenMode]。</span><span class="sxs-lookup"><span data-stu-id="d3c34-115">For more information, navigate to [Evergreen distribution mode][DistributionEvergreenMode].</span></span>  

## <span data-ttu-id="d3c34-116">发布和预发布程序包</span><span class="sxs-lookup"><span data-stu-id="d3c34-116">Release and prerelease package</span></span>  

<span data-ttu-id="d3c34-117">在预览中，发布程序包中包含以下。</span><span class="sxs-lookup"><span data-stu-id="d3c34-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="d3c34-118">[Win32 C/c + + api][ReferenceWin32]：在公开时，SDK 中的 api 应保持不变。</span><span class="sxs-lookup"><span data-stu-id="d3c34-118">[Win32 C/C++ APIs][ReferenceWin32]: APIs in the SDK that are expected to remain the same at GA.</span></span>  

<span data-ttu-id="d3c34-119">在预览中，预发行程序包包含以下组件。</span><span class="sxs-lookup"><span data-stu-id="d3c34-119">In preview, the prerelease package contains the following components.</span></span>  

*   <span data-ttu-id="d3c34-120">.NET Api： [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]和 [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span><span class="sxs-lookup"><span data-stu-id="d3c34-120">.NET APIs: [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span></span>  
*   <span data-ttu-id="d3c34-121">实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="d3c34-121">Experimental APIs.</span></span>  <span data-ttu-id="d3c34-122">有关详细信息，请参阅 [实验性 api](#experimental-apis) 部分。</span><span class="sxs-lookup"><span data-stu-id="d3c34-122">For more information, see the [Experimental APIs](#experimental-apis) section.</span></span>  

## <span data-ttu-id="d3c34-123">实验性 API</span><span class="sxs-lookup"><span data-stu-id="d3c34-123">Experimental APIs</span></span>  

<span data-ttu-id="d3c34-124">Web 视图团队正在测试可能表示未来功能的实验 Api。</span><span class="sxs-lookup"><span data-stu-id="d3c34-124">The WebView team is testing experimental APIs that may represent future functionality.</span></span>  <span data-ttu-id="d3c34-125">实验中的 Api 标记为 `experimental` 在 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="d3c34-125">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="d3c34-126">实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。</span><span class="sxs-lookup"><span data-stu-id="d3c34-126">Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="d3c34-127">在发布之前，你应该会认为所有实验性 Api 都有更改。</span><span class="sxs-lookup"><span data-stu-id="d3c34-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="d3c34-128">请使用 [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。</span><span class="sxs-lookup"><span data-stu-id="d3c34-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="d3c34-129">避免在生产应用中使用实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="d3c34-129">Avoid using the experimental APIs in production apps.</span></span>  

## <span data-ttu-id="d3c34-130">匹配 WebView2 运行时版本</span><span class="sxs-lookup"><span data-stu-id="d3c34-130">Matching WebView2 Runtime versions</span></span>  

<span data-ttu-id="d3c34-131">使用特定 SDK 版本编写 WebView2 应用时，应用的用户可能会使用 WebView2 运行时的各种兼容版本运行该应用。</span><span class="sxs-lookup"><span data-stu-id="d3c34-131">When writing a WebView2 app using a particular SDK version, the users fo you app may run your it with various compatible versions of the WebView2 Runtime.</span></span>  <span data-ttu-id="d3c34-132">将来，较新的兼容 WebView2 运行时版本包含来自旧版兼容 WebView2 运行时版本的所有非实验性 Api 以及其他新的非实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="d3c34-132">In the future, a newer compatible WebView2 Runtime version contains all the non-experimental APIs from an older compatible WebView2 Runtime version plus additional new non-experimental APIs.</span></span>  

*   <span data-ttu-id="d3c34-133">**Win32 C/c + +** 开发人员在使用 `QueryInterface` 获取新接口时，应检查返回值 `E_NOINTERFACE` ，这可能指示 WebView2 运行时较旧且不支持该特定接口。</span><span class="sxs-lookup"><span data-stu-id="d3c34-133">**Win32 C/C++** developers, when using `QueryInterface` to obtain a new interface, should check for a return value of `E_NOINTERFACE`, which may indicate that the WebView2 Runtime is older and does not support that particular interface.</span></span>  
*   <span data-ttu-id="d3c34-134">**.NET and WinUI** `No such interface supported` 当使用在后续 sdk 中添加的方法、属性和事件时，.net 和 WinUI 开发人员应检查异常，当 WebView2 运行时较旧且不支持这些特定的 api 时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d3c34-134">**.NET and WinUI** developers should check for a `No such interface supported` exception when using methods, properties, and events added in later SDKs which may occur when the WebView2 Runtime is older and does not support those particular APIs.</span></span>  

<span data-ttu-id="d3c34-135">如果 API 不可用，请考虑禁用关联的功能（如有可能），或者向最终用户通知他们需要更新其 WebView2 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="d3c34-135">If an API is unavailable, consider disabling the associated feature, if possible, or otherwise informing the end user they need to update their WebView2 Runtime version.</span></span>  

<span data-ttu-id="d3c34-136">可从 SDK 向 SDK 引入、修改和删除实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="d3c34-136">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="d3c34-137">当尝试使用在 WebView2 运行时中不可用的实验 API 时，你可能会注意到以前描述的行为。</span><span class="sxs-lookup"><span data-stu-id="d3c34-137">When attempting to use an experimental API that is not available in the WebView2 Runtime you may observe the same previously described behavior.</span></span>  

## <span data-ttu-id="d3c34-138">路线图</span><span class="sxs-lookup"><span data-stu-id="d3c34-138">Roadmap</span></span>  

<span data-ttu-id="d3c34-139">在 WebView2 达到稳定的常规可用状态后，发布程序包包含所有稳定的、受支持的 Win32 C/c + + 和 .NET Api。</span><span class="sxs-lookup"><span data-stu-id="d3c34-139">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="d3c34-140">预发行程序包包含可能会根据你的反馈和共享见解更改的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="d3c34-140">The prerelease package contains experimental APIs that are subject to change based upon your feedback and shared insights.</span></span>  

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 命名空间 |Microsoft 文档"
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 命名空间 |Microsoft 文档"
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 命名空间 | WebView2 命名空间 |Microsoft 文档"
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 c + + 参考 |Microsoft 文档"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
