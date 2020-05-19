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
ms.openlocfilehash: 4b64509e63acb966a95c32c4560c3ddcefebd5e4
ms.sourcegitcommit: 5bdffe91a6594f77eeffa4e864fda90a02784771
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "10659683"
---
# Microsoft Edge WebView2 路线图

##### 上次更新时间：2020年5月

WebView2 控件允许开发人员在其本机应用程序中嵌入 web 技术。 本文档概述了 WebView2 的预期路线图。 

> [!NOTE]
> WebView2 正在进行活动开发，并且路线图将根据市场变化和客户反馈继续发展，因此请注意，此处概述的计划不详尽，并且可能会发生更改。 

如果您对路线图有顾虑或疑问，请在[反馈](https://github.com/MicrosoftEdge/WebViewFeedback)存储库中留下反馈。

WebView2 团队有几个重要工作要做：

1.  WebView2 运行时安装程序（2020年4季度）
2.  固定版本（第4季度2020）
3.  常规可用性 
    *   Win32 C/c + + （2020年4季度）
    *   .NET （第4季度2020）
    *   WinUI 3.0 （Q2 2021）

## WebView2 运行时 & 安装程序

WebView2 长[绿](./concepts/distribution.md#microsoft-edge-webview2-runtime)分布模型将允许你在你的用户计算机上安装 WebView2 运行时并将其作为目标或链。 WebView2 运行时和安装程序的预览版预计将在2020年第3季度提供，2020第4季度上市。

## 已修复版本

WebView2[固定](./concepts/distribution.md#roadmap)的分发模型允许你将 Microsoft Edge 二进制文件打包到本机应用程序中。 工程工作的当前用途是在第3季度2020和第 4 2020 季度正式推出的预览版准备就绪。

## 常规可用性 

### Win32 C/c + +

Win32 C/c + + SDK 预计将在 WebView2 运行时和安装程序 GA 之后的2020年第4季度公开。

### .NET

.NET SDK 包装 Win32 C/c + + SDK。 .NET SDK 预计将在第4季度2020中的 Win32 C/c + + GA 之后正式推出。

### WinUI 3。0

你可以通过[WIN UI 3.0](/uwp/toolkits/winui3/)（当前使用 alpha）将 WEBVIEW2 带入 UWP 应用程序。 签出[WINDOWS UI 库路线图](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)以保持最新状态。  
