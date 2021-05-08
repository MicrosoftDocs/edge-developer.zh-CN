---
description: 了解如何管理 WebView2 应用程序
title: 管理 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、企业、组策略、可管理性
ms.openlocfilehash: 1eb8b9dc1637daa8d10004ab8c340fe9ae33e38b
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11057858"
---
# <span data-ttu-id="02601-104">管理 WebView2 应用程序</span><span class="sxs-lookup"><span data-stu-id="02601-104">Managing WebView2 applications</span></span>  

<span data-ttu-id="02601-105">[WebView2][WebView2Landing] 是开发人员用于构建其应用程序的一个组件，开发人员可能在用户设备上部署自更新 [的 Evergreen WebView2 运行时][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] 来为应用程序提供电源。</span><span class="sxs-lookup"><span data-stu-id="02601-105">[WebView2][WebView2Landing] is a component that developers use to build their applications, and the developers may deploy a [self-updating Evergreen WebView2 Runtime][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] on user device to power their applications.</span></span>  <span data-ttu-id="02601-106">本文档讨论 IT 管理员如何管理 WebView2 应用程序和运行时。</span><span class="sxs-lookup"><span data-stu-id="02601-106">This document discusses how IT admins may manage WebView2 applications and Runtime.</span></span>  <span data-ttu-id="02601-107">欢迎 IT 管理员和开发人员在 [WebView2 反馈存储库上提供反馈][GithubMicrosoftedgeWebviewfeddback]。</span><span class="sxs-lookup"><span data-stu-id="02601-107">Feedback from both IT admins and developers is welcome on [WebView2 Feedback repo][GithubMicrosoftedgeWebviewfeddback].</span></span>  

## <span data-ttu-id="02601-108">WebView2 的组策略</span><span class="sxs-lookup"><span data-stu-id="02601-108">Group policies for WebView2</span></span>  

<span data-ttu-id="02601-109">IT 管理员可以使用组策略对象 \ (GPO\) 为 WebView2 配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="02601-109">IT admins may use group policy objects \(GPO\) to configure policy settings for WebView2.</span></span>  <span data-ttu-id="02601-110">以下策略集适用于/不适用于 WebView2，</span><span class="sxs-lookup"><span data-stu-id="02601-110">The following set of policies are/are not applicable to WebView2,</span></span>  

*   <span data-ttu-id="02601-111">[Microsoft Edge -][EdgeUpdatePolicies]更新策略可供 IT 管理员管理 WebView2 运行时的安装和更新方面。</span><span class="sxs-lookup"><span data-stu-id="02601-111">[Microsoft Edge - Update policies][EdgeUpdatePolicies] are available for IT admins to manage the install and update aspects of the WebView2 Runtime.</span></span>  <span data-ttu-id="02601-112">浏览器Microsoft Edge WebView2 运行时使用相同的更新机制进行更新。</span><span class="sxs-lookup"><span data-stu-id="02601-112">The Microsoft Edge browser and WebView2 Runtime are updated using the same update mechanism.</span></span>  <span data-ttu-id="02601-113">除非策略（如 ）特定于通道，否则它同时适用于 `Update` 浏览器和 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="02601-113">Unless a policy, such as `Update`, is channel-specific, it applies to both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="02601-114">例如，允许 IT 管理员设置每天的时间，以禁止浏览器和 `UpdateSuppressed` WebView2 运行时自动更新。</span><span class="sxs-lookup"><span data-stu-id="02601-114">For example, `UpdateSuppressed` allows IT admins to set time during each day to suppress auto-update for both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="02601-115">这使 IT 管理员能够为浏览器和 WebView2 运行时配置一次首选项和代理，以控制其网络带宽/流量或用于其他目的。</span><span class="sxs-lookup"><span data-stu-id="02601-115">This enables IT admins to configure preferences and proxies once for both the browser and WebView2 Runtime to control their network bandwidth/traffic or for other purposes.</span></span>  <span data-ttu-id="02601-116">IT 管理员可能会按照Microsoft Edge[指南配置][ConfigureMicrosoftEdge]Microsoft Edge - 更新策略。</span><span class="sxs-lookup"><span data-stu-id="02601-116">IT admins may follow [Microsoft Edge's guide][ConfigureMicrosoftEdge] to configure Microsoft Edge - Update policies.</span></span>  
*   <span data-ttu-id="02601-117">[Microsoft Edge -][EdgeBrowserPolicies]浏览器策略不适用于 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="02601-117">[Microsoft Edge - Browser policies][EdgeBrowserPolicies] doesn't apply to WebView2 applications.</span></span>  <span data-ttu-id="02601-118">这是设计使的，因为应用和浏览器具有不同的用例，并且 IT 管理员可能不知道哪些应用程序使用 WebView2。</span><span class="sxs-lookup"><span data-stu-id="02601-118">This is by design because apps and browsers have different use cases, and IT admins may not be aware of what applications use WebView2.</span></span>  <span data-ttu-id="02601-119">在 WebView2 上应用浏览器策略可能会产生意想不到的后果。</span><span class="sxs-lookup"><span data-stu-id="02601-119">Applying browser policies on WebView2 may have unintended consequences.</span></span>  <span data-ttu-id="02601-120">例如，IT 管理员可能会阻止浏览器中的 JavaScript，并且所有使用 JavaScript 的 WebView2 应用都已损坏。</span><span class="sxs-lookup"><span data-stu-id="02601-120">For example, IT admins may block JavaScript in the browser and all WebView2 apps using JavaScript are broken.</span></span>  
*   <span data-ttu-id="02601-121">\ (即将推出\) 特定于 WebView2 的策略 – 如果直接管理 WebView2 有意义，WebView2 将公开一小组额外的组策略。</span><span class="sxs-lookup"><span data-stu-id="02601-121">\(Coming soon\) WebView2-specific policies – WebView2 will expose a small additional set of group policies in cases where managing WebView2 directly makes sense.</span></span>  <span data-ttu-id="02601-122">我们建议应用开发人员实施自己的组策略来管理对 WebView2 的使用，因为 IT 管理员管理应用比直接管理 WebView2 更为简单。</span><span class="sxs-lookup"><span data-stu-id="02601-122">We recommend app developers to implement their own group policies to manage their use of WebView2, as it is more straightforward for IT admins to manage the app rather than WebView2 directly.</span></span>  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "了解 WebView2 运行时和安装程序 (Preview) - 使用 WebView2 |Microsoft Docs"  

[WebView2Landing]: ../index.md "WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge - 更新策略|Microsoft Docs"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - 浏览器策略|Microsoft Docs"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "在Microsoft Edge上配置策略Windows |Microsoft Docs"  


[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  
