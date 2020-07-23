---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: acf3103f39d33586ee0614aeb0f10de0ab71c89a
ms.sourcegitcommit: b3555043e9d5aefa5a9e36ba4d73934d41559f49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894310"
---
# <span data-ttu-id="be219-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="be219-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="be219-105">WebView2 依赖于 Microsoft Edge 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="be219-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="be219-106">每个 WebView2 SDK 都要求安装最低版本的浏览器。</span><span class="sxs-lookup"><span data-stu-id="be219-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="be219-107">最小版本反映在 SDK 的程序包版本中。</span><span class="sxs-lookup"><span data-stu-id="be219-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="be219-108">例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="be219-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="be219-109">浏览器版本也在 WebView2[发行说明][Releasenotes]中指定。</span><span class="sxs-lookup"><span data-stu-id="be219-109">The browser version is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="be219-110">有关浏览器的最新版本的详细信息，请参阅[浏览器通道][DeployedgeChannels]。</span><span class="sxs-lookup"><span data-stu-id="be219-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="be219-111">WebView2 当前处于预览版中。</span><span class="sxs-lookup"><span data-stu-id="be219-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="be219-112">尽管 Web 视图团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但不能保证它，因为较新版本的浏览器可能不支持以前的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="be219-112">While the WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed because newer versions of the browser may not support previous SDK versions.</span></span>  <span data-ttu-id="be219-113">如果浏览器版本和 Sdk 之间存在中断更改，我们将在[发行说明][Releasenotes]中指定更改。</span><span class="sxs-lookup"><span data-stu-id="be219-113">If there are breaking changes between browser versions and SDKs, we specify the changes in the [Release Notes][Releasenotes].</span></span>  

<span data-ttu-id="be219-114">将来，我们打算更改 WebView2 应用程序的分布模型。</span><span class="sxs-lookup"><span data-stu-id="be219-114">In the future, we plan to change the distribution model for WebView2 applications.</span></span>  <span data-ttu-id="be219-115">有关详细信息，请参阅长[绿分布模式][DistributionEvergreenMode]。</span><span class="sxs-lookup"><span data-stu-id="be219-115">For more information, see [Evergreen distribution mode][DistributionEvergreenMode].</span></span>  
 
## <span data-ttu-id="be219-116">发布和预发布程序包</span><span class="sxs-lookup"><span data-stu-id="be219-116">Release and pre-release package</span></span>  

<span data-ttu-id="be219-117">在预览中，发布程序包中包含以下。</span><span class="sxs-lookup"><span data-stu-id="be219-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="be219-118">[Win32 C/c + + api][ReferenceWin3209538]：在公开时，SDK 中的 api 应保持不变。</span><span class="sxs-lookup"><span data-stu-id="be219-118">[Win32 C/C++ APIs][ReferenceWin3209538]: APIs in the SDK that are expected to remain the same at GA.</span></span>  

<span data-ttu-id="be219-119">在预览中，预发布程序包包含以下组件。</span><span class="sxs-lookup"><span data-stu-id="be219-119">In preview, the pre-release package contains the following components.</span></span>  

*   <span data-ttu-id="be219-120">.NET Api： [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]和[Core][ReferenceDotnet09538]</span><span class="sxs-lookup"><span data-stu-id="be219-120">.NET APIs: [WPF][ReferenceWpf09515], [WinForms][ReferenceWinforms09515], and [Core][ReferenceDotnet09538]</span></span>  
*   <span data-ttu-id="be219-121">实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="be219-121">Experimental APIs.</span></span>  <span data-ttu-id="be219-122">有关详细信息，请参阅[实验性 api](#experimental-apis)部分。</span><span class="sxs-lookup"><span data-stu-id="be219-122">For more information, see the [Experimental APIs](#experimental-apis) section.</span></span>  

## <span data-ttu-id="be219-123">实验性 API</span><span class="sxs-lookup"><span data-stu-id="be219-123">Experimental APIs</span></span>  

<span data-ttu-id="be219-124">我们测试的实验 Api 可能表示将来的功能。</span><span class="sxs-lookup"><span data-stu-id="be219-124">We are testing experimental APIs that may represent future functionality.</span></span>  <span data-ttu-id="be219-125">实验中的 Api 标记为 `experimental` 在 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="be219-125">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="be219-126">实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。</span><span class="sxs-lookup"><span data-stu-id="be219-126">Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="be219-127">在发布之前，你应该会认为所有实验性 Api 都有更改。</span><span class="sxs-lookup"><span data-stu-id="be219-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="be219-128">请使用[Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。</span><span class="sxs-lookup"><span data-stu-id="be219-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>   

> [!CAUTION]
> <span data-ttu-id="be219-129">避免在生产应用程序中使用实验的 Api。</span><span class="sxs-lookup"><span data-stu-id="be219-129">Avoid using the experimental APIs in production applications.</span></span>  

## <span data-ttu-id="be219-130">路线图</span><span class="sxs-lookup"><span data-stu-id="be219-130">Roadmap</span></span>  

<span data-ttu-id="be219-131">在 WebView2 达到稳定的常规可用状态后，发布程序包包含所有稳定的、受支持的 Win32 C/c + + 和 .NET Api。</span><span class="sxs-lookup"><span data-stu-id="be219-131">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="be219-132">预发布程序包包含要根据开发人员反馈和共享见解更改的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="be219-132">The pre-release package contains experimental APIs that are subject to change based upon developer feedback and shared insights.</span></span>  

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
