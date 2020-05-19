---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8463ce403af069cf25dbf7b08bb49d44c1e54501
ms.sourcegitcommit: f1aa8925f7985a2bbfd951f188a8c19c97e4ff6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "10659564"
---
# 了解浏览器版本和 WebView2  

WebView2 依赖于 Microsoft Edge 才能正常工作。  每个 WebView2 SDK 都要求安装最低版本的浏览器。  此浏览器版本在我们的[发行说明][Webview2Releasenotes]中指定。  你可能会看到 SDK 的程序包版本中反映的最低版本。  例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。  有关浏览器的最新版本的详细信息，请参阅[浏览器通道][DeployedgeChannels]。  

> [!NOTE]
> WebView2 当前处于预览版中。  虽然 Microsoft Edge Web 服务团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但不保证某些较新版本的浏览器可能不支持旧版 SDK 版本。  如果浏览器版本和 Sdk 之间存在重大更改，Microsoft Edge Web 视图团队将显示[发行说明][Webview2Releasenotes]中的更改。  

将来，Microsoft Edge Web 视图团队计划更改分布模型。  Microsoft Edge Web 视图团队计划从 WebView2 删除 Microsoft Edge 浏览器的直接依赖关系。  <!--To learn more, see [WebView2 Runtime][Webview2IndexEdgeRuntime] in the [Distribution][Webview2Distibution] section.  -->  

<!--todo: dd link to distribution.md after publication  -->  

## 实验性 API  

尽管 WebView2 是预览，但 SDK 中的 Api 应在 GA 上市时保持不变。  SDK 中包含[实验性 api][Webview2ReferenceWin3209488Experimental] 。  请评估实验性 Api 并使用 " [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]" 存储库发送反馈。  

### 路线图  

在 WebView2 达到稳定的常规可用状态并释放 1.0.0 SDK 时，Microsoft Edge Web Edge 团队计划将所有实验 Api 移动到一个预发布程序包。  预发布程序包继续允许反馈和深入了解最新功能，而稳定的发布版本保持向后兼容性。  

<!--links -->

[Webview2Distibution]: ./distribution.md "不存在 |Microsoft 文档"  
[Webview2IndexEdgeRuntime]: ../index.md#microsoft-edge-webview2-runtime "Microsoft Edge WebView2 运行时-Microsoft Edge WebView2 （开发者预览版） |Microsoft 文档"  
[Webview2ReferenceWin3209488Experimental]: ../reference/win32/0-9-488-reference-webview2.md#experimental "实验性引用（WebView2） |Microsoft 文档"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
