---
description: 了解 WebView2 的下一步
title: Microsoft Edge Web Edge Web 图2的路线图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 99e743db0c1fb17ea46405b08e1ed074a3386068
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182358"
---
# Microsoft Edge WebView2 路线图  

##### 上次更新时间：2020年11月  

WebView2 控件允许开发人员在其本机应用程序中嵌入 web 技术。  下页概述了 WebView2 的预期路线图。  

> [!NOTE]
> WebView2 正在进行活动开发，并根据市场变化和客户反馈继续发展路线图，因此请注意，此处概述的计划不详尽，并且可能会发生更改。  

如果对路线图有疑问或问题，请在 [反馈][GithubMicrosoftedgeWebviewfeedbackMain]存储库中提供反馈。  

WebView2 团队正在制定后续更新的主要成果。  

:::row:::
   :::column span="1":::
      WebView2 运行时安装程序  
   :::column-end:::
   :::column span="2":::
      *   2020年4季度
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      已修复版本  
   :::column-end:::
   :::column span="2":::
      *   2020年4季度  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      常规可用性  
   :::column-end:::
   :::column span="2":::
      *   Win32 C/c + + \ (第4季度 2020 \ )   
      *    (第4季度 2020 \ ) 的 .NET \  
      *   [WinUI 3.0][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## WebView2 运行时和安装程序  

使用长[绿分布模型][ConceptDistributionEvergreenModel]，你可以将 WebView2 运行时作为目标或链接到你的用户计算机。  长绿 WebView2 运行时和安装程序已达到常规可用性 (\ ) 。  

## 已修复版本  

[固定版本分发模型][ConceptsDistributionFixedVersionModel] 允许你将 Microsoft Edge 二进制文件打包到本机应用程序中。  固定版本已达到常规可用性 \ (GA \ ) 。  

## 常规可用性  

### Win32 C/c + +  

Win32 C/c + + SDK 已达到 GA。  

### .NET  

.NET SDK 已上市。 

### WinUI 3.0  

你可以使用 [WIN UI 3.0][UwpToolkitsWinui3Index]（当前在 alpha 中）访问 UWP 应用程序中的 WebView2。  有关保持最新状态的详细信息，请参阅 [WINDOWS UI 库路线图][GithubMicrosoftUiXamlRoadmap]。  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "长绿分布模型-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分布模型-使用 WebView2 | 的应用程序的分发Microsoft 文档"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI 库3.0 预览 1 (可能 2020) |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI 库路线图-microsoft/microsoft-UI-xaml |GitHub"  
