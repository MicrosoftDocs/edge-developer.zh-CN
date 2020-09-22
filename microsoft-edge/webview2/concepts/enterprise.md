---
description: 了解如何管理 WebView2 应用程序
title: 管理 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、企业、组策略、可管理性
ms.openlocfilehash: 1eb8b9dc1637daa8d10004ab8c340fe9ae33e38b
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11057858"
---
# 管理 WebView2 应用程序  

[WebView2][WebView2Landing] 是开发人员用于构建其应用程序的组件，开发人员可以在用户设备上部署 [自更新长绿][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] 应用程序来为其应用程序加电。  本文档讨论了 IT 管理员可以如何管理 WebView2 应用程序和运行时。  来自 IT 管理员和开发人员的反馈是欢迎使用 [WebView2 反馈][GithubMicrosoftedgeWebviewfeddback]存储库。  

## WebView2 的组策略  

IT 管理员可以使用组策略对象 \ (GPO \ ) 配置 WebView2 的策略设置。  以下策略集是/不适用于 WebView2。  

*   [Microsoft Edge-更新策略][EdgeUpdatePolicies] 可供 IT 管理员管理 WebView2 运行时的安装和更新方面。  Microsoft Edge 浏览器和 WebView2 运行时使用相同的更新机制进行更新。  除非某个策略（如 `Update` ）是特定于信道的，否则它将同时适用于浏览器和 WebView2 运行时。  例如， `UpdateSuppressed` 允许 IT 管理员在每天对浏览器和 WebView2 运行时都取消自动更新的时间设置。  这使 IT 管理员可以为浏览器和 WebView2 运行时配置首选项和代理，以便控制其网络带宽/流量或用于其他用途。  IT 管理员可按照 [Microsoft edge 指南][ConfigureMicrosoftEdge] 配置 Microsoft edge 更新策略。  
*   [Microsoft Edge-浏览器策略][EdgeBrowserPolicies] 不适用于 WebView2 应用程序。  这是设计使然，因为应用和浏览器具有不同的使用情形，并且 IT 管理员可能不知道哪些应用程序使用 WebView2。  在 WebView2 上应用浏览器策略可能会产生意想不到的后果。  例如，IT 管理员可能会在浏览器中阻止 JavaScript，并且所有使用 JavaScript 的 WebView2 应用均已损坏。  
*   \ (即将推出 ) WebView2 特定的策略-WebView2 将在管理 WebView2 直接有意义的情况下公开一组较少的其他组策略。  我们建议应用开发人员实现自己的组策略以管理其对 WebView2 的使用，因为它更直接管理应用，而不是直接管理 WebView2。  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "了解 WebView2 运行时和安装程序 (预览版使用 WebView2 | 的应用程序) 分布Microsoft 文档"  

[WebView2Landing]: ../index.md "Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge-更新策略 |Microsoft 文档"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge-浏览器策略 |Microsoft 文档"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "在 Windows | 上配置 Microsoft Edge 策略设置Microsoft 文档"  


[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
