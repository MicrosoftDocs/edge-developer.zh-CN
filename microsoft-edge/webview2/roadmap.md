---
description: 了解 WebView2 接下来将做什么
title: Microsoft Edge WebView 2 路线图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 0f51b5cab32bdb9b9aa9b6baceef5fe5a17eea54
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398411"
---
# <a name="microsoft-edge-webview2-roadmap"></a><span data-ttu-id="4e854-104">Microsoft Edge WebView2 路线图</span><span class="sxs-lookup"><span data-stu-id="4e854-104">Microsoft Edge WebView2 roadmap</span></span>  

> [!NOTE]
> <span data-ttu-id="4e854-105">Last Updated： November 2020</span><span class="sxs-lookup"><span data-stu-id="4e854-105">Last Updated:  November 2020</span></span>  

<span data-ttu-id="4e854-106">WebView2 控件允许开发人员在其本机应用程序中嵌入 Web 技术。</span><span class="sxs-lookup"><span data-stu-id="4e854-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span>  <span data-ttu-id="4e854-107">以下页面概述了 WebView2 的潜在路线图。</span><span class="sxs-lookup"><span data-stu-id="4e854-107">The following page outlines the prospective roadmap for WebView2.</span></span>  

> [!NOTE]
> <span data-ttu-id="4e854-108">WebView2 正在积极开发，路线图将继续根据市场变化和客户反馈不断发展，因此请注意，此处概述的计划并不详尽，可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="4e854-108">WebView2 is under active development and the roadmap continues to evolve based on market changes and customer feedback, so please note that the plans outlined here are not exhaustive and are subject to change.</span></span>  

<span data-ttu-id="4e854-109">如果你对路线图有疑问或疑问，请从反馈存储库 [提供反馈][GithubMicrosoftedgeWebviewfeedbackMain]。</span><span class="sxs-lookup"><span data-stu-id="4e854-109">If you have concerns or questions about the Roadmap, provide your feedback in the [feedback repo][GithubMicrosoftedgeWebviewfeedbackMain].</span></span>  

<span data-ttu-id="4e854-110">WebView2 团队正在计划以下主要工作，用于将来的更新。</span><span class="sxs-lookup"><span data-stu-id="4e854-110">The WebView2 team is planning the following major efforts for future updates.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="4e854-111">WebView2 运行时安装程序</span><span class="sxs-lookup"><span data-stu-id="4e854-111">WebView2 Runtime Installer</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="4e854-112">2020 年第 4 季度</span><span class="sxs-lookup"><span data-stu-id="4e854-112">Q4 2020</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="4e854-113">已修复版本</span><span class="sxs-lookup"><span data-stu-id="4e854-113">Fixed Version</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="4e854-114">2020 年第 4 季度</span><span class="sxs-lookup"><span data-stu-id="4e854-114">Q4 2020</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="4e854-115">通用</span><span class="sxs-lookup"><span data-stu-id="4e854-115">General Availability</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="4e854-116">Win32 C/C++ \ (Q4 2020\) </span><span class="sxs-lookup"><span data-stu-id="4e854-116">Win32 C/C++ \(Q4 2020\)</span></span>  
      *   <span data-ttu-id="4e854-117">.NET \ (Q4 2020\) </span><span class="sxs-lookup"><span data-stu-id="4e854-117">.NET \(Q4 2020\)</span></span>  
      *   [<span data-ttu-id="4e854-118">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="4e854-118">WinUI 3.0</span></span>][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## <a name="webview2-runtime-and-installer"></a><span data-ttu-id="4e854-119">WebView2 运行时和安装程序</span><span class="sxs-lookup"><span data-stu-id="4e854-119">WebView2 Runtime and Installer</span></span>  

<span data-ttu-id="4e854-120">[使用常青分发][ConceptDistributionEvergreenModel] 模型，你可以将 WebView2 运行时的目标安装或链接安装到用户计算机上。</span><span class="sxs-lookup"><span data-stu-id="4e854-120">[Evergreen distribution model][ConceptDistributionEvergreenModel] allows you to target or chain install the WebView2 Runtime onto your user's machine.</span></span>  <span data-ttu-id="4e854-121">Evergreen WebView2 运行时和安装程序已到达通用版本 \ (GA\) 。</span><span class="sxs-lookup"><span data-stu-id="4e854-121">The Evergreen WebView2 Runtime and installer has reached General Availability \(GA\).</span></span>  

## <a name="fixed-version"></a><span data-ttu-id="4e854-122">固定版本</span><span class="sxs-lookup"><span data-stu-id="4e854-122">Fixed version</span></span>  

<span data-ttu-id="4e854-123">[固定版本分发模型][ConceptsDistributionFixedVersionModel] 允许你将 Microsoft Edge 二进制文件打包到本机应用程序中。</span><span class="sxs-lookup"><span data-stu-id="4e854-123">[Fixed version distribution model][ConceptsDistributionFixedVersionModel] allows you to package the Microsoft Edge binaries inside your native application.</span></span>  <span data-ttu-id="4e854-124">固定版本已达到通用版本 \ (GA\) 。</span><span class="sxs-lookup"><span data-stu-id="4e854-124">The Fixed Version has reached General Availability \(GA\).</span></span>  

## <a name="general-availability"></a><span data-ttu-id="4e854-125">通用</span><span class="sxs-lookup"><span data-stu-id="4e854-125">General availability</span></span>  

### <a name="win32-cc"></a><span data-ttu-id="4e854-126">Win32 C/C++</span><span class="sxs-lookup"><span data-stu-id="4e854-126">Win32 C/C++</span></span>  

<span data-ttu-id="4e854-127">Win32 C/C++ SDK 已到达 GA。</span><span class="sxs-lookup"><span data-stu-id="4e854-127">The Win32 C/C++ SDK has reached GA.</span></span>  

### <a name="net"></a><span data-ttu-id="4e854-128">.NET</span><span class="sxs-lookup"><span data-stu-id="4e854-128">.NET</span></span>  

<span data-ttu-id="4e854-129">.NET SDK 已到达 GA。</span><span class="sxs-lookup"><span data-stu-id="4e854-129">The .NET SDK has reached GA.</span></span> 

### <a name="winui-30"></a><span data-ttu-id="4e854-130">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="4e854-130">WinUI 3.0</span></span>  

<span data-ttu-id="4e854-131">可以使用 Win [UI 3.0][UwpToolkitsWinui3Index]访问 UWP 应用程序中的 WebView2，当前采用 alpha。</span><span class="sxs-lookup"><span data-stu-id="4e854-131">You can access WebView2 in your UWP applications using [Win UI 3.0][UwpToolkitsWinui3Index], currently in alpha.</span></span>  <span data-ttu-id="4e854-132">有关保持最新状态的信息，请导航到 [Windows UI 库路线图][GithubMicrosoftUiXamlRoadmap]。</span><span class="sxs-lookup"><span data-stu-id="4e854-132">For more information about keeping up to date, navigate to [Windows UI Library Roadmap][GithubMicrosoftUiXamlRoadmap].</span></span>  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "常青分布模型 - 使用 WebView2 |Microsoft Docs"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分布模型 - 使用 WebView2 应用程序分发|Microsoft Docs"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI Library 3.0 Preview 1 (2020 年 5 月) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI 库路线图 - microsoft/microsoft-ui-xaml |GitHub"  
