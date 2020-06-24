---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 3862576134d1179fb24b2ce865f705b2bf1db8a6
ms.sourcegitcommit: de171a8e7ccd9f23846f3cd06519e4a0104f1c52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10757604"
---
# <span data-ttu-id="107d8-104">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="107d8-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="107d8-105">WebView2 依赖于 Microsoft Edge 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="107d8-105">WebView2 depends on Microsoft Edge to function.</span></span> <span data-ttu-id="107d8-106">每个 WebView2 SDK 都要求安装最低版本的浏览器。</span><span class="sxs-lookup"><span data-stu-id="107d8-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="107d8-107">最小版本反映在 SDK 的程序包版本中。</span><span class="sxs-lookup"><span data-stu-id="107d8-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="107d8-108">例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="107d8-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span> <span data-ttu-id="107d8-109">浏览器版本也在 WebView2[发行说明][Webview2Releasenotes]中指定。</span><span class="sxs-lookup"><span data-stu-id="107d8-109">The browser version is also specified in the WebView2 [Release Notes][Webview2Releasenotes].</span></span>  <span data-ttu-id="107d8-110">有关浏览器的最新版本的详细信息，请参阅[浏览器通道][DeployedgeChannels]。</span><span class="sxs-lookup"><span data-stu-id="107d8-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="107d8-111">WebView2 当前处于预览版中。</span><span class="sxs-lookup"><span data-stu-id="107d8-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="107d8-112">虽然 Microsoft Edge Web 服务团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但不保证某些较新版本的浏览器可能不支持旧版 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="107d8-112">While, the Microsoft Edge WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed as some newer versions of the browser may not support older SDK versions.</span></span>  <span data-ttu-id="107d8-113">如果浏览器版本和 Sdk 之间存在重大更改，Microsoft Edge Web 视图团队将指定[发行说明][Webview2Releasenotes]中的更改。</span><span class="sxs-lookup"><span data-stu-id="107d8-113">If there are breaking changes between browser versions and SDKs, the Microsoft Edge WebView team specifies the changes in the [release notes][Webview2Releasenotes].</span></span>  

<span data-ttu-id="107d8-114">将来，WebView2 应用程序的分发模型将会发生变化。</span><span class="sxs-lookup"><span data-stu-id="107d8-114">In the future, the distribution model for WebView2 applications will change.</span></span> <span data-ttu-id="107d8-115">有关详细信息，请参阅[WebView2 运行时][Webview2IndexEdgeRuntime]。</span><span class="sxs-lookup"><span data-stu-id="107d8-115">For more information, see [WebView2 Runtime][Webview2IndexEdgeRuntime].</span></span>  
 
## <span data-ttu-id="107d8-116">发布和预发布程序包</span><span class="sxs-lookup"><span data-stu-id="107d8-116">Release and pre-release package</span></span>  

<span data-ttu-id="107d8-117">在预览中，发布程序包中包含以下。</span><span class="sxs-lookup"><span data-stu-id="107d8-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="107d8-118">[Win32 C/c + + api][Webview2ReferenceWin3209538]：在公开时，SDK 中的 api 应保持不变。</span><span class="sxs-lookup"><span data-stu-id="107d8-118">[Win32 C/C++ APIs][Webview2ReferenceWin3209538]: APIs in the SDK that are expected to remain the same at GA.</span></span> 

<span data-ttu-id="107d8-119">在预览中，预发布程序包包含以下项。</span><span class="sxs-lookup"><span data-stu-id="107d8-119">In preview, the pre-release package contains the following.</span></span>  

*   <span data-ttu-id="107d8-120">.NET Api： [WPF][Webview2ReferenceWpf09515]、 [WinForms][Webview2ReferenceWinforms09515]和[Core][Webview2ReferenceDotnet09538]</span><span class="sxs-lookup"><span data-stu-id="107d8-120">.NET APIs: [WPF][Webview2ReferenceWpf09515], [WinForms][Webview2ReferenceWinforms09515], and [Core][Webview2ReferenceDotnet09538]</span></span>
*   <span data-ttu-id="107d8-121">实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="107d8-121">Experimental APIs.</span></span>  <span data-ttu-id="107d8-122">有关详细信息，请参阅[Experimantal api](#experimental-apis)部分。</span><span class="sxs-lookup"><span data-stu-id="107d8-122">For more information, see the [Experimantal APIs](#experimental-apis) section.</span></span>  

### <span data-ttu-id="107d8-123">实验性 API</span><span class="sxs-lookup"><span data-stu-id="107d8-123">Experimental APIs</span></span>  

<span data-ttu-id="107d8-124">Web 视图团队是测试表示未来的名为实验 Api 的功能的 Api。</span><span class="sxs-lookup"><span data-stu-id="107d8-124">The WebView Team is testing APIs that represent future functionality named Experimental APIs.</span></span>  <span data-ttu-id="107d8-125">实验中的 Api 标记为 `experimental` 在 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="107d8-125">The Experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="107d8-126">某些实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。</span><span class="sxs-lookup"><span data-stu-id="107d8-126">Some Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="107d8-127">在发布之前，你应该会认为所有实验性 Api 都有更改。</span><span class="sxs-lookup"><span data-stu-id="107d8-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="107d8-128">请使用[Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。</span><span class="sxs-lookup"><span data-stu-id="107d8-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>   

> [!CAUTION]
> <span data-ttu-id="107d8-129">避免在生产应用程序中使用实验的 Api。</span><span class="sxs-lookup"><span data-stu-id="107d8-129">Avoid using the experimental APIs in production applications.</span></span>  

### <span data-ttu-id="107d8-130">路线图</span><span class="sxs-lookup"><span data-stu-id="107d8-130">Roadmap</span></span>  

<span data-ttu-id="107d8-131">在 WebView2 达到稳定的常规可用状态后，发布程序包包含所有稳定的、受支持的 Win32 C/c + + 和 .NET Api。</span><span class="sxs-lookup"><span data-stu-id="107d8-131">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="107d8-132">预发布程序包包含要根据开发人员反馈和共享见解更改的实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="107d8-132">The pre-release package contains experimental APIs that are subject to change based upon developer feedback and shared insights.</span></span>  

<!--links -->

[Webview2IndexEdgeRuntime]: ./distribution.md#microsoft-edge-webview2-runtime "Microsoft Edge WebView2 运行时-使用 WebView2 | 的应用程序分发Microsoft 文档"  
[Webview2ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
