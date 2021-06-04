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
# <a name="microsoft-edge-webview2-roadmap"></a>Microsoft Edge WebView2 路线图  

> [!NOTE]
> Last Updated： November 2020  

WebView2 控件允许开发人员在其本机应用程序中嵌入 Web 技术。  以下页面概述了 WebView2 的潜在路线图。  

> [!NOTE]
> WebView2 正在积极开发，路线图将继续根据市场变化和客户反馈不断发展，因此请注意，此处概述的计划并不详尽，可能会发生更改。  

如果你对路线图有疑问或疑问，请从反馈存储库 [提供反馈][GithubMicrosoftedgeWebviewfeedbackMain]。  

WebView2 团队正在计划以下主要工作，用于将来的更新。  

:::row:::
   :::column span="1":::
      WebView2 运行时安装程序  
   :::column-end:::
   :::column span="2":::
      *   2020 年第 4 季度
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      已修复版本  
   :::column-end:::
   :::column span="2":::
      *   2020 年第 4 季度  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      通用  
   :::column-end:::
   :::column span="2":::
      *   Win32 C/C++ \(Q4 2020\)   
      *   .NET \(Q4 2020\)   
      *   [WinUI 3.0][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## <a name="webview2-runtime-and-installer"></a>WebView2 运行时和安装程序  

[使用常青分发][ConceptDistributionEvergreenModel] 模型，你可以将 WebView2 运行时的目标安装或链接安装到用户计算机上。  Evergreen WebView2 运行时和安装程序已到达通用版本 \(GA\) 。  

## <a name="fixed-version"></a>固定版本  

[固定版本分发模型][ConceptsDistributionFixedVersionModel] 允许你将 Microsoft Edge 二进制文件打包到本机应用程序中。  固定版本已达到通用版本 \(GA\) 。  

## <a name="general-availability"></a>通用  

### <a name="win32-cc"></a>Win32 C/C++  

Win32 C/C++ SDK 已到达 GA。  

### <a name="net"></a>.NET  

.NET SDK 已到达 GA。 

### <a name="winui-30"></a>WinUI 3.0  

可以使用 Win [UI 3.0][UwpToolkitsWinui3Index]访问 UWP 应用程序中的 WebView2，当前采用 alpha。  有关保持最新状态的信息，请导航到 [Windows UI 库路线图][GithubMicrosoftUiXamlRoadmap]。  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "常青分布模型 - 使用 WebView2 |Microsoft Docs"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分布模型 - 使用 WebView2 应用程序分发|Microsoft Docs"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI Library 3.0 Preview 1 (2020 年 5 月) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI 库路线图 - microsoft/microsoft-ui-xaml |GitHub"  
