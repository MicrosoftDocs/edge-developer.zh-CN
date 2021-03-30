---
description: 了解如何管理 WebView2 应用程序
title: 管理 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、企业、组策略、可管理性
ms.openlocfilehash: 1eb8b9dc1637daa8d10004ab8c340fe9ae33e38b
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11057858"
---
# <span data-ttu-id="66c70-104">管理 WebView2 应用程序</span><span class="sxs-lookup"><span data-stu-id="66c70-104">Managing WebView2 applications</span></span>  

<span data-ttu-id="66c70-105">[WebView2][WebView2Landing] 是开发人员用于构建其应用程序的组件，开发人员可以在用户设备上部署 [自更新长绿][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] 应用程序来为其应用程序加电。</span><span class="sxs-lookup"><span data-stu-id="66c70-105">[WebView2][WebView2Landing] is a component that developers use to build their applications, and the developers may deploy a [self-updating Evergreen WebView2 Runtime][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] on user device to power their applications.</span></span>  <span data-ttu-id="66c70-106">本文档讨论了 IT 管理员可以如何管理 WebView2 应用程序和运行时。</span><span class="sxs-lookup"><span data-stu-id="66c70-106">This document discusses how IT admins may manage WebView2 applications and Runtime.</span></span>  <span data-ttu-id="66c70-107">来自 IT 管理员和开发人员的反馈是欢迎使用 [WebView2 反馈][GithubMicrosoftedgeWebviewfeddback]存储库。</span><span class="sxs-lookup"><span data-stu-id="66c70-107">Feedback from both IT admins and developers is welcome on [WebView2 Feedback repo][GithubMicrosoftedgeWebviewfeddback].</span></span>  

## <span data-ttu-id="66c70-108">WebView2 的组策略</span><span class="sxs-lookup"><span data-stu-id="66c70-108">Group policies for WebView2</span></span>  

<span data-ttu-id="66c70-109">IT 管理员可以使用组策略对象 \(GPO \ ) 配置 WebView2 的策略设置。</span><span class="sxs-lookup"><span data-stu-id="66c70-109">IT admins may use group policy objects \(GPO\) to configure policy settings for WebView2.</span></span>  <span data-ttu-id="66c70-110">以下策略集是/不适用于 WebView2。</span><span class="sxs-lookup"><span data-stu-id="66c70-110">The following set of policies are/are not applicable to WebView2,</span></span>  

*   <span data-ttu-id="66c70-111">[Microsoft Edge-更新策略][EdgeUpdatePolicies] 可供 IT 管理员管理 WebView2 运行时的安装和更新方面。</span><span class="sxs-lookup"><span data-stu-id="66c70-111">[Microsoft Edge - Update policies][EdgeUpdatePolicies] are available for IT admins to manage the install and update aspects of the WebView2 Runtime.</span></span>  <span data-ttu-id="66c70-112">Microsoft Edge 浏览器和 WebView2 运行时使用相同的更新机制进行更新。</span><span class="sxs-lookup"><span data-stu-id="66c70-112">The Microsoft Edge browser and WebView2 Runtime are updated using the same update mechanism.</span></span>  <span data-ttu-id="66c70-113">除非某个策略（如 `Update` ）是特定于信道的，否则它将同时适用于浏览器和 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="66c70-113">Unless a policy, such as `Update`, is channel-specific, it applies to both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="66c70-114">例如， `UpdateSuppressed` 允许 IT 管理员在每天对浏览器和 WebView2 运行时都取消自动更新的时间设置。</span><span class="sxs-lookup"><span data-stu-id="66c70-114">For example, `UpdateSuppressed` allows IT admins to set time during each day to suppress auto-update for both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="66c70-115">这使 IT 管理员可以为浏览器和 WebView2 运行时配置首选项和代理，以便控制其网络带宽/流量或用于其他用途。</span><span class="sxs-lookup"><span data-stu-id="66c70-115">This enables IT admins to configure preferences and proxies once for both the browser and WebView2 Runtime to control their network bandwidth/traffic or for other purposes.</span></span>  <span data-ttu-id="66c70-116">IT 管理员可按照 [Microsoft edge 指南][ConfigureMicrosoftEdge] 配置 Microsoft edge 更新策略。</span><span class="sxs-lookup"><span data-stu-id="66c70-116">IT admins may follow [Microsoft Edge's guide][ConfigureMicrosoftEdge] to configure Microsoft Edge - Update policies.</span></span>  
*   <span data-ttu-id="66c70-117">[Microsoft Edge-浏览器策略][EdgeBrowserPolicies] 不适用于 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="66c70-117">[Microsoft Edge - Browser policies][EdgeBrowserPolicies] doesn't apply to WebView2 applications.</span></span>  <span data-ttu-id="66c70-118">这是设计使然，因为应用和浏览器具有不同的使用情形，并且 IT 管理员可能不知道哪些应用程序使用 WebView2。</span><span class="sxs-lookup"><span data-stu-id="66c70-118">This is by design because apps and browsers have different use cases, and IT admins may not be aware of what applications use WebView2.</span></span>  <span data-ttu-id="66c70-119">在 WebView2 上应用浏览器策略可能会产生意想不到的后果。</span><span class="sxs-lookup"><span data-stu-id="66c70-119">Applying browser policies on WebView2 may have unintended consequences.</span></span>  <span data-ttu-id="66c70-120">例如，IT 管理员可能会在浏览器中阻止 JavaScript，并且所有使用 JavaScript 的 WebView2 应用均已损坏。</span><span class="sxs-lookup"><span data-stu-id="66c70-120">For example, IT admins may block JavaScript in the browser and all WebView2 apps using JavaScript are broken.</span></span>  
*   <span data-ttu-id="66c70-121">\(即将推出 ) WebView2 特定的策略-WebView2 将在管理 WebView2 直接有意义的情况下公开一组较少的其他组策略。</span><span class="sxs-lookup"><span data-stu-id="66c70-121">\(Coming soon\) WebView2-specific policies – WebView2 will expose a small additional set of group policies in cases where managing WebView2 directly makes sense.</span></span>  <span data-ttu-id="66c70-122">我们建议应用开发人员实现自己的组策略以管理其对 WebView2 的使用，因为它更直接管理应用，而不是直接管理 WebView2。</span><span class="sxs-lookup"><span data-stu-id="66c70-122">We recommend app developers to implement their own group policies to manage their use of WebView2, as it is more straightforward for IT admins to manage the app rather than WebView2 directly.</span></span>  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "了解 WebView2 运行时和安装程序 (预览版使用 WebView2 | 的应用程序) 分布Microsoft 文档"  

[WebView2Landing]: ../index.md "Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge-更新策略 |Microsoft 文档"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge-浏览器策略 |Microsoft 文档"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "在 Windows | 上配置 Microsoft Edge 策略设置Microsoft 文档"  


[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
