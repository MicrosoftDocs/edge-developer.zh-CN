---
description: 了解 WebView2 接下来将做什么
title: WebView 2 Microsoft Edge路线图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 7b67e4a6844ead0f845667a70df8657745ece938
ms.sourcegitcommit: 8f37c931ecde4d58223113f7e3b42d37cc3df97f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2021
ms.locfileid: "11643418"
---
# <a name="microsoft-edge-webview2-roadmap"></a><span data-ttu-id="0e9ac-104">Microsoft EdgeWebView2 路线图</span><span class="sxs-lookup"><span data-stu-id="0e9ac-104">Microsoft Edge WebView2 roadmap</span></span>  

> [!NOTE]
> <span data-ttu-id="0e9ac-105">Last Updated： July 2021</span><span class="sxs-lookup"><span data-stu-id="0e9ac-105">Last Updated:  July 2021</span></span>  

<span data-ttu-id="0e9ac-106">WebView2 控件允许开发人员在其本机应用程序中嵌入 Web 技术。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span>  <span data-ttu-id="0e9ac-107">以下页面概述了 WebView2 的潜在路线图。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-107">The following page outlines the prospective roadmap for WebView2.</span></span>  

> [!NOTE]
> <span data-ttu-id="0e9ac-108">WebView2 正在积极开发，路线图将继续根据市场变化和客户反馈不断发展，因此请注意，此处概述的计划并不详尽，可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-108">WebView2 is under active development and the roadmap continues to evolve based on market changes and customer feedback, so please note that the plans outlined here are not exhaustive and are subject to change.</span></span>  

<span data-ttu-id="0e9ac-109">如果你对路线图有疑问或疑问，请从反馈存储库 [提供反馈][GithubMicrosoftedgeWebviewfeedbackMain]。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-109">If you have concerns or questions about the Roadmap, provide your feedback in the [feedback repo][GithubMicrosoftedgeWebviewfeedbackMain].</span></span>  

<span data-ttu-id="0e9ac-110">WebView2 团队正在计划以下主要工作，用于将来的更新。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-110">The WebView2 team is planning the following major efforts for future updates.</span></span>  

* <span data-ttu-id="0e9ac-111">UWP 预览版</span><span class="sxs-lookup"><span data-stu-id="0e9ac-111">UWP Preview</span></span>
* <span data-ttu-id="0e9ac-112">MacOS 预览版</span><span class="sxs-lookup"><span data-stu-id="0e9ac-112">MacOS Preview</span></span>
* <span data-ttu-id="0e9ac-113">Xbox 预览版</span><span class="sxs-lookup"><span data-stu-id="0e9ac-113">Xbox Preview</span></span>
* <span data-ttu-id="0e9ac-114">HoloLens预览</span><span class="sxs-lookup"><span data-stu-id="0e9ac-114">HoloLens Preview</span></span>

## <a name="webview2-runtime-and-installer"></a><span data-ttu-id="0e9ac-115">WebView2 运行时和安装程序</span><span class="sxs-lookup"><span data-stu-id="0e9ac-115">WebView2 Runtime and Installer</span></span>  

<span data-ttu-id="0e9ac-116">[使用常青分发][ConceptDistributionEvergreenModel] 模型，你可以将 WebView2 运行时的目标安装或链接安装到用户计算机上。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-116">[Evergreen distribution model][ConceptDistributionEvergreenModel] allows you to target or chain install the WebView2 Runtime onto your user's machine.</span></span>  <span data-ttu-id="0e9ac-117">Evergreen WebView2 运行时和安装程序已到达通用版本 \ (GA\) 。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-117">The Evergreen WebView2 Runtime and installer has reached General Availability \(GA\).</span></span>  

## <a name="fixed-version"></a><span data-ttu-id="0e9ac-118">固定版本</span><span class="sxs-lookup"><span data-stu-id="0e9ac-118">Fixed version</span></span>  

<span data-ttu-id="0e9ac-119">[固定版本分发模型][ConceptsDistributionFixedVersionModel]允许你将Microsoft Edge二进制文件打包到本机应用程序中。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-119">[Fixed version distribution model][ConceptsDistributionFixedVersionModel] allows you to package the Microsoft Edge binaries inside your native application.</span></span>  <span data-ttu-id="0e9ac-120">固定版本已达到通用版本 \ (GA\) 。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-120">The Fixed Version has reached General Availability \(GA\).</span></span>  

## <a name="general-availability"></a><span data-ttu-id="0e9ac-121">通用</span><span class="sxs-lookup"><span data-stu-id="0e9ac-121">General availability</span></span>  

### <a name="win32-cc"></a><span data-ttu-id="0e9ac-122">Win32 C/C++</span><span class="sxs-lookup"><span data-stu-id="0e9ac-122">Win32 C/C++</span></span>  

<span data-ttu-id="0e9ac-123">Win32 C/C++ SDK 已到达 GA。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-123">The Win32 C/C++ SDK has reached GA.</span></span>  

### <a name="net"></a><span data-ttu-id="0e9ac-124">.NET</span><span class="sxs-lookup"><span data-stu-id="0e9ac-124">.NET</span></span>  

<span data-ttu-id="0e9ac-125">.NET SDK 已到达 GA。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-125">The .NET SDK has reached GA.</span></span> 

### <a name="windows-ui-library-3"></a><span data-ttu-id="0e9ac-126">WindowsUI 库 3</span><span class="sxs-lookup"><span data-stu-id="0e9ac-126">Windows UI Library 3</span></span>

<span data-ttu-id="0e9ac-127">可以使用 Windows App SDK 中的 WinUI3 Windows UI 库 3 (访问) [WebView2][UwpToolkitsWinui3Index] Windows控件。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-127">You can access WebView2 controls in your applications using [Windows UI Library 3 (WinUI3)][UwpToolkitsWinui3Index] with the Windows App SDK.</span></span> <span data-ttu-id="0e9ac-128">This is currently in preview.</span><span class="sxs-lookup"><span data-stu-id="0e9ac-128">This is currently in preview.</span></span> <span data-ttu-id="0e9ac-129">有关详细信息，请导航到[Windows App SDK 路线图][WindowsAppSDK|::ref1::|]。</span><span class="sxs-lookup"><span data-stu-id="0e9ac-129">For more information, navigate to the [Windows App SDK roadmap][WindowsAppSDK|::ref1::|].</span></span>

 
<!-- links -->  

[WindowsAppSDKRoadmap]: https://github.com/microsoft/WindowsAppSDK/blob/main/docs/roadmap.md "路线图"
[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "常青分布模型 - 使用 WebView2 |Microsoft Docs"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分布模型 - 使用 WebView2 应用程序分发|Microsoft Docs"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "WindowsUI Library 3.0 Preview 1 (2020 年 5 月) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "WindowsUI 库路线图 - microsoft/microsoft-ui-xaml |GitHub"  
