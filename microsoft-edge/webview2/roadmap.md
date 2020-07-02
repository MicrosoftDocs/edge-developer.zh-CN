---
description: 了解 WebView2 的下一步
title: Microsoft Edge Web Edge Web 图2的路线图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 151eca3da5909b9d418451617b6bf09319752c55
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844409"
---
# <span data-ttu-id="d39ae-104">Microsoft Edge WebView2 路线图</span><span class="sxs-lookup"><span data-stu-id="d39ae-104">Microsoft Edge WebView2 roadmap</span></span>  

##### <span data-ttu-id="d39ae-105">上次更新时间：2020年5月</span><span class="sxs-lookup"><span data-stu-id="d39ae-105">Last Updated: May 2020</span></span>  

<span data-ttu-id="d39ae-106">WebView2 控件允许开发人员在其本机应用程序中嵌入 web 技术。</span><span class="sxs-lookup"><span data-stu-id="d39ae-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span>  <span data-ttu-id="d39ae-107">下页概述了 WebView2 的预期路线图。</span><span class="sxs-lookup"><span data-stu-id="d39ae-107">The following page outlines the prospective roadmap for WebView2.</span></span>  

> [!NOTE]
> <span data-ttu-id="d39ae-108">WebView2 正在进行活动开发，并根据市场变化和客户反馈继续发展路线图，因此请注意，此处概述的计划不详尽，并且可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="d39ae-108">WebView2 is under active development and the roadmap continues to evolve based on market changes and customer feedback, so please note that the plans outlined here are not exhaustive and are subject to change.</span></span>  

<span data-ttu-id="d39ae-109">如果您对路线图有顾虑或疑问，请在[反馈][GithubMicrosoftedgeWebviewfeedbackMain]存储库中留下反馈。</span><span class="sxs-lookup"><span data-stu-id="d39ae-109">If you have concerns or questions about the Roadmap, please leave feedback in the [feedback repo][GithubMicrosoftedgeWebviewfeedbackMain].</span></span>  

<span data-ttu-id="d39ae-110">WebView2 团队正在制定后续更新的主要成果。</span><span class="sxs-lookup"><span data-stu-id="d39ae-110">The WebView2 team is planning the following major efforts for future updates.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="d39ae-111">WebView2 运行时安装程序</span><span class="sxs-lookup"><span data-stu-id="d39ae-111">WebView2 Runtime Installer</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="d39ae-112">2020年4季度</span><span class="sxs-lookup"><span data-stu-id="d39ae-112">Q4 2020</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="d39ae-113">已修复版本</span><span class="sxs-lookup"><span data-stu-id="d39ae-113">Fixed Version</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="d39ae-114">2020年4季度</span><span class="sxs-lookup"><span data-stu-id="d39ae-114">Q4 2020</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="d39ae-115">常规可用性</span><span class="sxs-lookup"><span data-stu-id="d39ae-115">General Availability</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="d39ae-116">Win32 C/c + + \ （第4季度 2020 \）</span><span class="sxs-lookup"><span data-stu-id="d39ae-116">Win32 C/C++ \(Q4 2020\)</span></span>  
      *   <span data-ttu-id="d39ae-117">.NET \ （第4季度 2020 \）</span><span class="sxs-lookup"><span data-stu-id="d39ae-117">.NET \(Q4 2020\)</span></span>  
      *   [<span data-ttu-id="d39ae-118">WinUI 3。0</span><span class="sxs-lookup"><span data-stu-id="d39ae-118">WinUI 3.0</span></span>][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="d39ae-119">WebView2 运行时和安装程序</span><span class="sxs-lookup"><span data-stu-id="d39ae-119">WebView2 Runtime and Installer</span></span>  

<span data-ttu-id="d39ae-120">使用长[绿分布模型][ConceptDistributionEvergreenModel]，你可以将 WebView2 运行时作为目标或链接到你的用户计算机。</span><span class="sxs-lookup"><span data-stu-id="d39ae-120">[Evergreen distribution model][ConceptDistributionEvergreenModel] allows you to target or chain install the WebView2 Runtime onto your user's machine.</span></span>  <span data-ttu-id="d39ae-121">WebView2 运行时和安装程序的预览版预计将在2020年第3季度提供，2020第4季度上市。</span><span class="sxs-lookup"><span data-stu-id="d39ae-121">A preview of the WebView2 Runtime and installer is expected to be available Q3 2020 and GA in Q4 2020.</span></span>  

## <span data-ttu-id="d39ae-122">已修复版本</span><span class="sxs-lookup"><span data-stu-id="d39ae-122">Fixed version</span></span>  

<span data-ttu-id="d39ae-123">[固定版本分发模型][ConceptsDistributionFixedVersionModel]允许你将 Microsoft Edge 二进制文件打包到本机应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d39ae-123">[Fixed version distribution model][ConceptsDistributionFixedVersionModel] allows you to package the Microsoft Edge binaries inside your native application.</span></span>  <span data-ttu-id="d39ae-124">工程工作的当前用途是在第3季度2020和第 4 2020 季度正式推出的预览版准备就绪。</span><span class="sxs-lookup"><span data-stu-id="d39ae-124">Engineering work is currently under way with a preview anticipated to be ready towards the end of Q3 2020 and GA Q4 2020.</span></span>  

## <span data-ttu-id="d39ae-125">常规可用性</span><span class="sxs-lookup"><span data-stu-id="d39ae-125">General availability</span></span>  

### <span data-ttu-id="d39ae-126">Win32 C/c + +</span><span class="sxs-lookup"><span data-stu-id="d39ae-126">Win32 C/C++</span></span>  

<span data-ttu-id="d39ae-127">Win32 C/c + + SDK 预计将在 WebView2 运行时和安装程序 GA 之后的2020年第4季度公开。</span><span class="sxs-lookup"><span data-stu-id="d39ae-127">The Win32 C/C++ SDK is expected to GA in Q4 2020, shortly after the WebView2 Runtime and installer GA.</span></span>  

### <span data-ttu-id="d39ae-128">.NET</span><span class="sxs-lookup"><span data-stu-id="d39ae-128">.NET</span></span>  

<span data-ttu-id="d39ae-129">.NET SDK 包装 Win32 C/c + + SDK。</span><span class="sxs-lookup"><span data-stu-id="d39ae-129">The .NET SDK wraps the Win32 C/C++ SDK.</span></span>  <span data-ttu-id="d39ae-130">.NET SDK 预计将在第4季度2020中的 Win32 C/c + + GA 之后正式推出。</span><span class="sxs-lookup"><span data-stu-id="d39ae-130">The .NET SDK is expected to GA shortly after the Win32 C/C++ GA in Q4 2020.</span></span>  

### <span data-ttu-id="d39ae-131">WinUI 3。0</span><span class="sxs-lookup"><span data-stu-id="d39ae-131">WinUI 3.0</span></span>  

<span data-ttu-id="d39ae-132">你可以使用[WIN UI 3.0][UwpToolkitsWinui3Index]（当前在 alpha 中）访问 UWP 应用程序中的 WebView2。</span><span class="sxs-lookup"><span data-stu-id="d39ae-132">You are able to access WebView2 in your UWP applications using [Win UI 3.0][UwpToolkitsWinui3Index], currently in alpha.</span></span>  <span data-ttu-id="d39ae-133">有关保持最新状态的详细信息，请参阅[WINDOWS UI 库路线图][GithubMicrosoftUiXamlRoadmap]。</span><span class="sxs-lookup"><span data-stu-id="d39ae-133">For more information about keeping up to date, see [Windows UI Library Roadmap][GithubMicrosoftUiXamlRoadmap].</span></span>  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "长绿分布模型-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分布模型-使用 WebView2 | 的应用程序的分发Microsoft 文档"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI 库3.0 预览1（五月2020） |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI 库路线图-microsoft/microsoft-UI-xaml |GitHub"  
