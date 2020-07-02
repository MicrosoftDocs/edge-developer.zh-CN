---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 059bbeb34f372af0cef944e484599c0b50543cc9
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844423"
---
# <span data-ttu-id="403db-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="403db-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="403db-105">WebView2 依赖于 Microsoft Edge 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="403db-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="403db-106">每个 WebView2 SDK 都要求安装最低版本的浏览器。</span><span class="sxs-lookup"><span data-stu-id="403db-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="403db-107">最小版本反映在 SDK 的程序包版本中。</span><span class="sxs-lookup"><span data-stu-id="403db-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="403db-108">例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="403db-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="403db-109">浏览器版本也在 WebView2[发行说明][Releasenotes]中指定。</span><span class="sxs-lookup"><span data-stu-id="403db-109">The browser version is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="403db-110">有关浏览器的最新版本的详细信息，请参阅[浏览器通道][DeployedgeChannels]。</span><span class="sxs-lookup"><span data-stu-id="403db-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="403db-111">WebView2 当前处于预览版中。</span><span class="sxs-lookup"><span data-stu-id="403db-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="403db-112">尽管 Web 视图团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但由于较新版本的浏览器可能不支持较旧的 SDK 版本，因此不能保证它的兼容性。</span><span class="sxs-lookup"><span data-stu-id="403db-112">While the WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed since newer versions of the browser may not support older SDK versions.</span></span>  <span data-ttu-id="403db-113">如果浏览器版本和 Sdk 之间存在中断的更改，则 Web 视图团队将指定[发行说明][Releasenotes]中的更改。</span><span class="sxs-lookup"><span data-stu-id="403db-113">If there are breaking changes between browser versions and SDKs, the WebView team specifies the changes in the [release notes][Releasenotes].</span></span>  

<span data-ttu-id="403db-114">将来，Web 视图团队计划更改 WebView2 应用程序的分布模型。</span><span class="sxs-lookup"><span data-stu-id="403db-114">In the future, the  WebView team plans to change the distribution model for WebView2 applications.</span></span>  <span data-ttu-id="403db-115">有关详细信息，请参阅查看长[绿分布模式][DistributionEvergreenMode]。</span><span class="sxs-lookup"><span data-stu-id="403db-115">For more information, see see [Evergreen distribution mode][DistributionEvergreenMode].</span></span>  
 
## <span data-ttu-id="403db-116">发布和预发布程序包</span><span class="sxs-lookup"><span data-stu-id="403db-116">Release and pre-release package</span></span>  

<span data-ttu-id="403db-117">在预览中，发布程序包中包含以下。</span><span class="sxs-lookup"><span data-stu-id="403db-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="403db-118">[Win32 C/c + + api][ReferenceWin3209538]：在公开时，SDK 中的 api 应保持不变。</span><span class="sxs-lookup"><span data-stu-id="403db-118">[Win32 C/C++ APIs][ReferenceWin3209538]: APIs in the SDK that are expected to remain the same at GA.</span></span> 

<span data-ttu-id="403db-119">在预览中，预发布程序包包含以下组件。</span><span class="sxs-lookup"><span data-stu-id="403db-119">In preview, the pre-release package contains the following components.</span></span>  

*   <span data-ttu-id="403db-120">.NET Api： [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]和[Core][ReferenceDotnet09538]</span><span class="sxs-lookup"><span data-stu-id="403db-120">.NET APIs: [WPF][ReferenceWpf09515], [WinForms][ReferenceWinforms09515], and [Core][ReferenceDotnet09538]</span></span>
*   <span data-ttu-id="403db-121">实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="403db-121">Experimental APIs.</span></span>  <span data-ttu-id="403db-122">有关详细信息，请参阅[实验性 api](#experimental-apis)部分。</span><span class="sxs-lookup"><span data-stu-id="403db-122">For more information, see the [Experimental APIs](#experimental-apis) section.</span></span>  

### <span data-ttu-id="403db-123">实验性 API</span><span class="sxs-lookup"><span data-stu-id="403db-123">Experimental APIs</span></span>  

<span data-ttu-id="403db-124">Web 视图团队是测试表示未来的名为实验 Api 的功能的 Api。</span><span class="sxs-lookup"><span data-stu-id="403db-124">The WebView Team is testing APIs that represent future functionality named Experimental APIs.</span></span>  <span data-ttu-id="403db-125">实验中的 Api 标记为 `experimental` 在 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="403db-125">The Experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="403db-126">某些实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。</span><span class="sxs-lookup"><span data-stu-id="403db-126">Some Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="403db-127">在发布之前，你应该会认为所有实验性 Api 都有更改。</span><span class="sxs-lookup"><span data-stu-id="403db-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="403db-128">请使用[Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。</span><span class="sxs-lookup"><span data-stu-id="403db-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>   

> [!CAUTION]
> <span data-ttu-id="403db-129">避免在生产应用程序中使用实验的 Api。</span><span class="sxs-lookup"><span data-stu-id="403db-129">Avoid using the experimental APIs in production applications.</span></span>  

### <span data-ttu-id="403db-130">路线图</span><span class="sxs-lookup"><span data-stu-id="403db-130">Roadmap</span></span>  

<span data-ttu-id="403db-131">在 WebView2 达到稳定的常规可用状态后，发布程序包包含所有稳定的、受支持的 Win32 C/c + + 和 .NET Api。</span><span class="sxs-lookup"><span data-stu-id="403db-131">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="403db-132">预发布程序包包含要根据开发人员反馈和共享见解更改的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="403db-132">The pre-release package contains experimental APIs that are subject to change based upon developer feedback and shared insights.</span></span>  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
