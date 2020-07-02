---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 059bbeb34f372af0cef944e484599c0b50543cc9
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844423"
---
# 了解 WebView2 SDK 版本  

WebView2 依赖于 Microsoft Edge 才能正常工作。  每个 WebView2 SDK 都要求安装最低版本的浏览器。  最小版本反映在 SDK 的程序包版本中。  例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。  浏览器版本也在 WebView2[发行说明][Releasenotes]中指定。  有关浏览器的最新版本的详细信息，请参阅[浏览器通道][DeployedgeChannels]。  

> [!NOTE]
> WebView2 当前处于预览版中。  尽管 Web 视图团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但由于较新版本的浏览器可能不支持较旧的 SDK 版本，因此不能保证它的兼容性。  如果浏览器版本和 Sdk 之间存在中断的更改，则 Web 视图团队将指定[发行说明][Releasenotes]中的更改。  

将来，Web 视图团队计划更改 WebView2 应用程序的分布模型。  有关详细信息，请参阅查看长[绿分布模式][DistributionEvergreenMode]。  
 
## 发布和预发布程序包  

在预览中，发布程序包中包含以下。  

*   [Win32 C/c + + api][ReferenceWin3209538]：在公开时，SDK 中的 api 应保持不变。 

在预览中，预发布程序包包含以下组件。  

*   .NET Api： [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]和[Core][ReferenceDotnet09538]
*   实验性 Api。  有关详细信息，请参阅[实验性 api](#experimental-apis)部分。  

### 实验性 API  

Web 视图团队是测试表示未来的名为实验 Api 的功能的 Api。  实验中的 Api 标记为 `experimental` 在 SDK 中。  某些实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。  在发布之前，你应该会认为所有实验性 Api 都有更改。  请使用[Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。   

> [!CAUTION]
> 避免在生产应用程序中使用实验的 Api。  

### 路线图  

在 WebView2 达到稳定的常规可用状态后，发布程序包包含所有稳定的、受支持的 Win32 C/c + + 和 .NET Api。  预发布程序包包含要根据开发人员反馈和共享见解更改的实验性 Api。  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "参考（WebView2） |Microsoft 文档"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
