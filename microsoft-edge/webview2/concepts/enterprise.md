---
description: 了解如何管理 WebView2 应用程序
title: 管理 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、企业、组策略、可管理性
ms.openlocfilehash: 1eb8b9dc1637daa8d10004ab8c340fe9ae33e38b
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11057858"
---
# 管理 WebView2 应用程序  

[WebView2][WebView2Landing] 是开发人员用于构建其应用程序的一个组件，开发人员可能在用户设备上部署自更新 [的 Evergreen WebView2 运行时][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] 来为应用程序提供电源。  本文档讨论 IT 管理员如何管理 WebView2 应用程序和运行时。  欢迎 IT 管理员和开发人员在 [WebView2 反馈存储库上提供反馈][GithubMicrosoftedgeWebviewfeddback]。  

## WebView2 的组策略  

IT 管理员可以使用组策略对象 \ (GPO\) 为 WebView2 配置策略设置。  以下策略集适用于/不适用于 WebView2，  

*   [Microsoft Edge -][EdgeUpdatePolicies]更新策略可供 IT 管理员管理 WebView2 运行时的安装和更新方面。  浏览器Microsoft Edge WebView2 运行时使用相同的更新机制进行更新。  除非策略（如 ）特定于通道，否则它同时适用于 `Update` 浏览器和 WebView2 运行时。  例如，允许 IT 管理员设置每天的时间，以禁止浏览器和 `UpdateSuppressed` WebView2 运行时自动更新。  这使 IT 管理员能够为浏览器和 WebView2 运行时配置一次首选项和代理，以控制其网络带宽/流量或用于其他目的。  IT 管理员可能会按照Microsoft Edge[指南配置][ConfigureMicrosoftEdge]Microsoft Edge - 更新策略。  
*   [Microsoft Edge -][EdgeBrowserPolicies]浏览器策略不适用于 WebView2 应用程序。  这是设计使的，因为应用和浏览器具有不同的用例，并且 IT 管理员可能不知道哪些应用程序使用 WebView2。  在 WebView2 上应用浏览器策略可能会产生意想不到的后果。  例如，IT 管理员可能会阻止浏览器中的 JavaScript，并且所有使用 JavaScript 的 WebView2 应用都已损坏。  
*   \ (即将推出\) 特定于 WebView2 的策略 – 如果直接管理 WebView2 有意义，WebView2 将公开一小组额外的组策略。  我们建议应用开发人员实施自己的组策略来管理对 WebView2 的使用，因为 IT 管理员管理应用比直接管理 WebView2 更为简单。  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "了解 WebView2 运行时和安装程序 (Preview) - 使用 WebView2 |Microsoft Docs"  

[WebView2Landing]: ../index.md "WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge - 更新策略|Microsoft Docs"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - 浏览器策略|Microsoft Docs"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "在Microsoft Edge上配置策略Windows |Microsoft Docs"  


[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  
