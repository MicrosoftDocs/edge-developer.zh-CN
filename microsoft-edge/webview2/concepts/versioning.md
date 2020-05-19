---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8463ce403af069cf25dbf7b08bb49d44c1e54501
ms.sourcegitcommit: f1aa8925f7985a2bbfd951f188a8c19c97e4ff6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "10659564"
---
# <span data-ttu-id="8fabc-104">了解浏览器版本和 WebView2</span><span class="sxs-lookup"><span data-stu-id="8fabc-104">Understanding browser versions and WebView2</span></span>  

<span data-ttu-id="8fabc-105">WebView2 依赖于 Microsoft Edge 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="8fabc-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="8fabc-106">每个 WebView2 SDK 都要求安装最低版本的浏览器。</span><span class="sxs-lookup"><span data-stu-id="8fabc-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="8fabc-107">此浏览器版本在我们的[发行说明][Webview2Releasenotes]中指定。</span><span class="sxs-lookup"><span data-stu-id="8fabc-107">This browser version is specified in our [Release Notes][Webview2Releasenotes].</span></span>  <span data-ttu-id="8fabc-108">你可能会看到 SDK 的程序包版本中反映的最低版本。</span><span class="sxs-lookup"><span data-stu-id="8fabc-108">You may see the minimum version reflected in the package version of the SDK.</span></span>  <span data-ttu-id="8fabc-109">例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8fabc-109">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="8fabc-110">有关浏览器的最新版本的详细信息，请参阅[浏览器通道][DeployedgeChannels]。</span><span class="sxs-lookup"><span data-stu-id="8fabc-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="8fabc-111">WebView2 当前处于预览版中。</span><span class="sxs-lookup"><span data-stu-id="8fabc-111">WebView2 is currently in Preview.</span></span>  <span data-ttu-id="8fabc-112">虽然 Microsoft Edge Web 服务团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但不保证某些较新版本的浏览器可能不支持旧版 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="8fabc-112">While, the Microsoft Edge WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed as some newer versions of the browser may not support older SDK versions.</span></span>  <span data-ttu-id="8fabc-113">如果浏览器版本和 Sdk 之间存在重大更改，Microsoft Edge Web 视图团队将显示[发行说明][Webview2Releasenotes]中的更改。</span><span class="sxs-lookup"><span data-stu-id="8fabc-113">If there are breaking changes between browser versions and SDKs, the Microsoft Edge WebView team indicates the changes in the [release notes][Webview2Releasenotes].</span></span>  

<span data-ttu-id="8fabc-114">将来，Microsoft Edge Web 视图团队计划更改分布模型。</span><span class="sxs-lookup"><span data-stu-id="8fabc-114">In the future, the Microsoft Edge WebView team plans to change the distribution model.</span></span>  <span data-ttu-id="8fabc-115">Microsoft Edge Web 视图团队计划从 WebView2 删除 Microsoft Edge 浏览器的直接依赖关系。</span><span class="sxs-lookup"><span data-stu-id="8fabc-115">The Microsoft Edge WebView team plans to remove the direct dependency on the Microsoft Edge browser from WebView2.</span></span>  <!--To learn more, see [WebView2 Runtime][Webview2IndexEdgeRuntime] in the [Distribution][Webview2Distibution] section.  -->  

<!--todo: dd link to distribution.md after publication  -->  

## <span data-ttu-id="8fabc-116">实验性 API</span><span class="sxs-lookup"><span data-stu-id="8fabc-116">Experimental APIs</span></span>  

<span data-ttu-id="8fabc-117">尽管 WebView2 是预览，但 SDK 中的 Api 应在 GA 上市时保持不变。</span><span class="sxs-lookup"><span data-stu-id="8fabc-117">While WebView2 is a preview, the APIs in the SDK are expected to remain the same at GA.</span></span>  <span data-ttu-id="8fabc-118">SDK 中包含[实验性 api][Webview2ReferenceWin3209488Experimental] 。</span><span class="sxs-lookup"><span data-stu-id="8fabc-118">There are [experimental APIs][Webview2ReferenceWin3209488Experimental] included in the SDK.</span></span>  <span data-ttu-id="8fabc-119">请评估实验性 Api 并使用 " [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]" 存储库发送反馈。</span><span class="sxs-lookup"><span data-stu-id="8fabc-119">Please evaluate the experimental APIs and send your feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

### <span data-ttu-id="8fabc-120">路线图</span><span class="sxs-lookup"><span data-stu-id="8fabc-120">Roadmap</span></span>  

<span data-ttu-id="8fabc-121">在 WebView2 达到稳定的常规可用状态并释放 1.0.0 SDK 时，Microsoft Edge Web Edge 团队计划将所有实验 Api 移动到一个预发布程序包。</span><span class="sxs-lookup"><span data-stu-id="8fabc-121">After WebView2 reaches a stable general available state and we release the 1.0.0 SDK, the Microsoft Edge WebView team plans to move all experimental APIs to a pre-release package.</span></span>  <span data-ttu-id="8fabc-122">预发布程序包继续允许反馈和深入了解最新功能，而稳定的发布版本保持向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="8fabc-122">The pre-release package continues to allow for feedback and insight into the latest features, while the stable release version maintains backward compatibility.</span></span>  

<!--links -->

[Webview2Distibution]: ./distribution.md "不存在 |Microsoft 文档"  
[Webview2IndexEdgeRuntime]: ../index.md#microsoft-edge-webview2-runtime "Microsoft Edge WebView2 运行时-Microsoft Edge WebView2 （开发者预览版） |Microsoft 文档"  
[Webview2ReferenceWin3209488Experimental]: ../reference/win32/0-9-488-reference-webview2.md#experimental "实验性引用（WebView2） |Microsoft 文档"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
