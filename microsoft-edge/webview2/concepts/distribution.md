---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用程序的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 370b5da2d42412a08a5c7f8a7401496fa70e3065
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844402"
---
# 使用 WebView2 的应用程序的分发  

WebView2 控件利用 Microsoft Edge \ （Chromium \）平台。  打包和分发应用时，请确保在应用启动之前存在平台或 WebView2 运行时的副本。  下页介绍了 \ （开发人员 \）如何确保 WebView2 运行时已安装并使用 WebView2 应用程序的两种分布模式：长[绿](#evergreen-distribution-mode)和[固定版本](#fixed-version-distribution-mode)。  

## 长绿分布模式  

长时间分布模式可确保你的应用充分利用最新功能和安全更新。  长绿分布模式具有以下特征。  

*   Web 平台将自动更新，无需额外的精力。  
*   所有利用长绿分布模式的应用程序都使用平台二进制文件的共享副本，从而节省磁盘空间。  

应用程序可以将多个信道 WebView2 用作 web 平台。  默认情况下，WebView2 针对设备上提供的最稳定通道，该通道满足 WebView2 SDK 的最低版本要求。  以下频道按从最高到稳定的频道顺序列出。  

1.  WebView2 运行时 \ （预览版 \）  
1.  Microsoft Edge Beta 渠道  
1.  Microsoft Edge Dev 渠道  
1.  Microsoft Edge Canary 渠道    

> [!NOTE]
> 对于大多数开发人员，建议使用长绿分布模型。  

> [!IMPORTANT]
> Microsoft Edge 稳定通道不是 WebView2 的有效目标，因此稍后将介绍原因。  

有关版本控制的详细信息，请参阅[版本控制][ConceptsVersioning]和[全局][ReferenceWin3209538WebviewIdl]。  

### 了解 WebView2 运行时和安装程序（预览版）  

Microsoft Edge 稳定频道可能未安装在应用程序运行的所有用户计算机上。  你的应用程序可能使用长绿 WebView2 运行时和安装程序 \ （Preview \），而不要求用户安装 Microsoft Edge。  WebView2 运行时是用于运行 WebView2 应用程序的 Microsoft Edge 二进制文件的自定义副本。  安装 WebView2 运行时时，用户无法将其用作普通浏览器。  例如，没有桌面快捷方式、"开始" 菜单项、用户无法使用运行时二进制文件打开浏览器窗口等。  设备上的所有长绿 WebView2 应用程序都可能使用单个长时间 WebView2 运行时安装。  

今天预览期间，将同时更新长绿 WebView2 运行时和 Microsoft Edge 开发频道，并具有相同的版本。  在预览期间的未来，WebView2 团队计划更新 WebView2 运行时并匹配与 Microsoft Edge Beta 通道相同的版本。  将来当 WebView2 达到常规可用性 \ （GA \）时，WebView2 团队计划更新 WebView2 运行时，并与 Microsoft Edge 稳定通道匹配相同的版本。  GA 后，应用程序应在生产中使用 WebView2 运行时。  

> [!IMPORTANT]
> 预览期间不要在生产中发运 WebView2 应用程序。  

请使用以下工作流以确保长时间 WebView2 运行时可用。  

1.  下载最新的长[绿 WebView2 运行时安装程序][Webview2Installer]。  
1.  在应用程序安装程序或更新程序中包括安装程序。  
1.  在应用程序安装或更新期间，请检查用户计算机上是否已安装了长时间 WebView2 运行时。  如果不是，应用程序将调用安装程序以安装运行时。  

你可能需要更改上述工作流，具体取决于你的方案。  例如，你的应用程序安装程序可能会下载长绿 WebView2 运行时安装程序，而不是将其包含在你的应用程序包中。  

> [!NOTE]
> WebView2 运行时和 WebView2 运行时安装程序都在预览版中。  预览具有有限的初始范围，并且仅在 x64 上的 Windows 10 上以独立的单机安装的形式提供。  将来，计划对 Windows 7、x86 和 ARM64 的支持。  

### 使用 WebView2 运行时和非稳定 Microsoft Edge 通道的最佳做法  

预览期间请考虑以下建议。  

*   请确保使用长[绿 WebView2 运行时和安装程序][Webview2Installer]来开发或测试打包和分发管道。  将来，生产应用程序应包含安装程序。  
*   对于开发应用程序，你可以使用长绿 WebView2 运行时。  但是，当运行时从开发人员通道切换到 Beta 通道或稳定通道时，运行时内部版本号可能不符合最新的预览 WebView2 SDK 最低版本要求。  如果您想要使用最新的 SDK，请安装 Microsoft Edge 的 "未安装" 通道以确保设备上有兼容的版本。  有关版本控制的详细信息，请参阅[版本控制][ConceptsVersioning]。  
*   若要测试您的 web 内容，使其与不在稳定频道中提供的平台更改兼容，请根据需要使用相应的非稳定通道。  

## 固定版本分发模式  

> [!NOTE]
> 固定版本分发模型目前不可用。  

对于受限制的环境，有计划支持固定版本 \ （以前命名的 "携带后" \）分发模式。  固定版本分发模式允许你选择和打包特定版本的 WebView2 运行时。  固定版本分发模式允许你控制你的应用程序使用哪个版本的 WebView2 运行时，以及何时更新用户计算机。  固定版本分发模式不会接收任何自动更新，你应该计划手动应用更新。  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "了解浏览器版本和 WebView2 |Microsoft 文档"  
[ReferenceWin3209538WebviewIdl]: ../reference/win32/0-9-538/webview2-idl.md  "Globals |Microsoft 文档"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序"  
