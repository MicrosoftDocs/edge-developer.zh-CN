---
description: 了解 WebView2 的下一步
title: Microsoft Edge Web Edge Web 图2的路线图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: dcc9a92ee4db4c41a024aee565dfafe22b185e2a
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698174"
---
# <span data-ttu-id="00986-104">Microsoft Edge WebView2 路线图</span><span class="sxs-lookup"><span data-stu-id="00986-104">Microsoft Edge WebView2 roadmap</span></span>

##### <span data-ttu-id="00986-105">上次更新时间：2020年5月</span><span class="sxs-lookup"><span data-stu-id="00986-105">Last Updated: May 2020</span></span>

<span data-ttu-id="00986-106">WebView2 控件允许开发人员在其本机应用程序中嵌入 web 技术。</span><span class="sxs-lookup"><span data-stu-id="00986-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span> <span data-ttu-id="00986-107">本文档概述了 WebView2 的预期路线图。</span><span class="sxs-lookup"><span data-stu-id="00986-107">This document outlines the prospective roadmap for WebView2.</span></span> 

> [!NOTE]
> <span data-ttu-id="00986-108">WebView2 正在进行活动开发，并且路线图将根据市场变化和客户反馈继续发展，因此请注意，此处概述的计划不详尽，并且可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="00986-108">WebView2 is under active development and the roadmap will continue to evolve based on market changes and customer feedback, so please note that the plans outlined here aren't exhaustive and are subject to change.</span></span> 

<span data-ttu-id="00986-109">如果您对路线图有顾虑或疑问，请在[反馈](https://github.com/MicrosoftEdge/WebViewFeedback)存储库中留下反馈。</span><span class="sxs-lookup"><span data-stu-id="00986-109">If you have concerns or questions about the Roadmap, please leave feedback in the [feedback repo](https://github.com/MicrosoftEdge/WebViewFeedback).</span></span>

<span data-ttu-id="00986-110">WebView2 团队有几个重要工作要做：</span><span class="sxs-lookup"><span data-stu-id="00986-110">The WebView2 team has a few major efforts underway:</span></span>

1.  <span data-ttu-id="00986-111">WebView2 运行时安装程序（2020年4季度）</span><span class="sxs-lookup"><span data-stu-id="00986-111">WebView2 Runtime Installer (Q4 2020)</span></span>
2.  <span data-ttu-id="00986-112">固定版本（第4季度2020）</span><span class="sxs-lookup"><span data-stu-id="00986-112">Fixed Version (Q4 2020)</span></span>
3.  <span data-ttu-id="00986-113">常规可用性</span><span class="sxs-lookup"><span data-stu-id="00986-113">General Availability</span></span> 
    *   <span data-ttu-id="00986-114">Win32 C/c + + （2020年4季度）</span><span class="sxs-lookup"><span data-stu-id="00986-114">Win32 C/C++ (Q4 2020)</span></span>
    *   <span data-ttu-id="00986-115">.NET （第4季度2020）</span><span class="sxs-lookup"><span data-stu-id="00986-115">.NET (Q4 2020)</span></span>
    *   [<span data-ttu-id="00986-116">WinUI 3。0</span><span class="sxs-lookup"><span data-stu-id="00986-116">WinUI 3.0</span></span>](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)

## <span data-ttu-id="00986-117">WebView2 运行时 & 安装程序</span><span class="sxs-lookup"><span data-stu-id="00986-117">WebView2 Runtime & Installer</span></span>

<span data-ttu-id="00986-118">WebView2 长[绿](./concepts/distribution.md#microsoft-edge-webview2-runtime)分布模型将允许你在你的用户计算机上安装 WebView2 运行时并将其作为目标或链。</span><span class="sxs-lookup"><span data-stu-id="00986-118">WebView2 [Evergreen](./concepts/distribution.md#microsoft-edge-webview2-runtime) distribution model will allow you to target or chain install the WebView2 Runtime onto your user's machine.</span></span> <span data-ttu-id="00986-119">WebView2 运行时和安装程序的预览版预计将在2020年第3季度提供，2020第4季度上市。</span><span class="sxs-lookup"><span data-stu-id="00986-119">A preview of the WebView2 Runtime and installer is expected to be available Q3 2020 and GA in Q4 2020.</span></span>

## <span data-ttu-id="00986-120">已修复版本</span><span class="sxs-lookup"><span data-stu-id="00986-120">Fixed version</span></span>

<span data-ttu-id="00986-121">WebView2[固定](./concepts/distribution.md#roadmap)的分发模型允许你将 Microsoft Edge 二进制文件打包到本机应用程序中。</span><span class="sxs-lookup"><span data-stu-id="00986-121">WebView2 [Fixed](./concepts/distribution.md#roadmap) distribution model allows you to package the Microsoft Edge binaries inside your native application.</span></span> <span data-ttu-id="00986-122">工程工作的当前用途是在第3季度2020和第 4 2020 季度正式推出的预览版准备就绪。</span><span class="sxs-lookup"><span data-stu-id="00986-122">Engineering work is currently under way with a preview anticipated to be ready towards the end of  Q3 2020 and GA Q4 2020.</span></span>

## <span data-ttu-id="00986-123">常规可用性</span><span class="sxs-lookup"><span data-stu-id="00986-123">General availability</span></span> 

### <span data-ttu-id="00986-124">Win32 C/c + +</span><span class="sxs-lookup"><span data-stu-id="00986-124">Win32 C/C++</span></span>

<span data-ttu-id="00986-125">Win32 C/c + + SDK 预计将在 WebView2 运行时和安装程序 GA 之后的2020年第4季度公开。</span><span class="sxs-lookup"><span data-stu-id="00986-125">The Win32 C/C++ SDK is expected to GA in Q4 2020, shortly after the WebView2 Runtime and installer GA.</span></span>

### <span data-ttu-id="00986-126">.NET</span><span class="sxs-lookup"><span data-stu-id="00986-126">.NET</span></span>

<span data-ttu-id="00986-127">.NET SDK 包装 Win32 C/c + + SDK。</span><span class="sxs-lookup"><span data-stu-id="00986-127">The .NET SDK wraps the Win32 C/C++ SDK.</span></span> <span data-ttu-id="00986-128">.NET SDK 预计将在第4季度2020中的 Win32 C/c + + GA 之后正式推出。</span><span class="sxs-lookup"><span data-stu-id="00986-128">The .NET SDK is expected to GA shortly after the Win32 C/C++ GA in Q4 2020.</span></span>

### <span data-ttu-id="00986-129">WinUI 3。0</span><span class="sxs-lookup"><span data-stu-id="00986-129">WinUI 3.0</span></span>

<span data-ttu-id="00986-130">你可以通过[WIN UI 3.0](/uwp/toolkits/winui3/)（当前使用 alpha）将 WEBVIEW2 带入 UWP 应用程序。</span><span class="sxs-lookup"><span data-stu-id="00986-130">You can bring WebView2 to UWP applications through [Win UI 3.0](/uwp/toolkits/winui3/), currently in alpha.</span></span> <span data-ttu-id="00986-131">签出[WINDOWS UI 库路线图](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)以保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="00986-131">Checkout the [Windows UI Library Roadmap](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md) to keep up to date.</span></span>  
