---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 3862576134d1179fb24b2ce865f705b2bf1db8a6
ms.sourcegitcommit: de171a8e7ccd9f23846f3cd06519e4a0104f1c52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10757604"
---
# 了解 WebView2 SDK 版本  

WebView2 依赖于 Microsoft Edge 才能正常工作。 每个 WebView2 SDK 都要求安装最低版本的浏览器。  最小版本反映在 SDK 的程序包版本中。  例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。 浏览器版本也在 WebView2[发行说明][Webview2Releasenotes]中指定。  有关浏览器的最新版本的详细信息，请参阅[浏览器通道][DeployedgeChannels]。  

> [!NOTE]
> WebView2 当前处于预览版中。  虽然 Microsoft Edge Web 服务团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但不保证某些较新版本的浏览器可能不支持旧版 SDK 版本。  如果浏览器版本和 Sdk 之间存在重大更改，Microsoft Edge Web 视图团队将指定[发行说明][Webview2Releasenotes]中的更改。  

将来，WebView2 应用程序的分发模型将会发生变化。 有关详细信息，请参阅[WebView2 运行时][Webview2IndexEdgeRuntime]。  
 
## 发布和预发布程序包  

在预览中，发布程序包中包含以下。  

*   [Win32 C/c + + api][Webview2ReferenceWin3209538]：在公开时，SDK 中的 api 应保持不变。 

在预览中，预发布程序包包含以下项。  

*   .NET Api： [WPF][Webview2ReferenceWpf09515]、 [WinForms][Webview2ReferenceWinforms09515]和[Core][Webview2ReferenceDotnet09538]
*   实验性 Api。  有关详细信息，请参阅[Experimantal api](#experimental-apis)部分。  

### 实验性 API  

Web 视图团队是测试表示未来的名为实验 Api 的功能的 Api。  实验中的 Api 标记为 `experimental` 在 SDK 中。  某些实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。  在发布之前，你应该会认为所有实验性 Api 都有更改。  请使用[Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。   

> [!CAUTION]
> 避免在生产应用程序中使用实验的 Api。  

### 路线图  

在 WebView2 达到稳定的常规可用状态后，发布程序包包含所有稳定的、受支持的 Win32 C/c + + 和 .NET Api。  预发布程序包包含要根据开发人员反馈和共享见解更改的实验性 Api。  

<!--links -->

[Webview2IndexEdgeRuntime]: ./distribution.md#microsoft-edge-webview2-runtime "Microsoft Edge WebView2 运行时-使用 WebView2 | 的应用程序分发Microsoft 文档"  
[Webview2ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
