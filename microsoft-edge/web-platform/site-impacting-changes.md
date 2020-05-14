---
description: 此页面提供可能会影响网站兼容性的高影响更改的摘要
title: 网站兼容性-影响到 Microsoft Edge 的更改
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台
ms.openlocfilehash: c35f38bd43255ab9a8c965c8fa9f3b1c8a95bff6
ms.sourcegitcommit: 1760ea15e83045168aec6bf507bc4fe7dfb5568f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652298"
---
# 网站兼容性-影响到 Microsoft Edge 的更改  

Web 不断发展，以改进用户体验、安全性和隐私。  在某些情况下，所做的更改可能会显著影响现有页面的功能。  下表总结了 Microsoft Edge 团队当前正在跟踪的最高影响的更改。  请经常回来查看;Microsoft Edge 团队将在思考演变、时间表实体化和新更改发布时更新此页面。  

| “更改” | Stable 渠道 | 实验 | 其他信息 |  
|:--- |:--- |:--- |:--- |
| Cookie 默认为 `SameSite=Lax` | [Chrome 或 Chrome + 1](#release-comments)  | V82、Dev v82 | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus5088147346030592]。  |  
| 引用策略：默认为 `strict-origin-when-cross-origin` | [Chrome 或 Chrome + 1](#release-comments)  | V79、Dev v79 | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus6251880185331712]。  |  
| 在页面消除期间禁止同步 XmlHttpRequest | [Chrome + 1](#release-comments) \ （Edge v83 \） |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  匹配的 Chrome，Microsoft Edge 将提供一个组策略来禁用此更改，直到 Edge 88。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus4664843055398912]。  |  
| 显示提示权限请求的微妙提示 |  | V83、Dev v83 | 用户现在可以选择在中发出静音通知请求 `edge://settings/content/notifications` 。  启用此设置后，Microsoft Edge 将在地址栏中为请求使用或 API 向用户发送通知的网站显示一个微妙的请求图标 `Notifications` `Push` 。  这种精致的图标取代了浮出权限提示。  在所有请求通知权限的网站上，在 "未线" 和 "开发" 的实验中，对于某些用户，默认情况下会打开此行为。  用户可能会选择退出 `edge://settings/content/notifications` 。  将来，Microsoft edge 团队可能会根据用户行为和其他输入来浏览在特定情况下显示出控件提示。  |  
| 默认情况下禁用 TLS/1.0 和 TLS/1。1 | Edge v84 |  | 若要帮助发现受影响的网站，你可以将该 `edge://flags/#display-legacy-tls-warnings` 标志设置为导致 Microsoft Edge 在加载需要旧版 TLS 协议的页面时显示非阻止 "不安全" 通知。  [SSLMinVersion][DeployedEdgePoliciesSSLMinVersion]组策略允许重新启用 TLS/1.0 和 tls/1.1;该策略将保持可用，直到 Edge 88。  |  
| 阻止混合内容下载 | [Chrome + 1](#release-comments) \ （Edge v85 \）  |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[google 安全博客条目][GoogleBlogSecurity20200206]。  在 Chrome 之后的一个版本计划中，Microsoft 推出针对警告或阻止的文件类型的推出计划。  |  

##### 发布评论  

:::row:::
   :::column span="1":::
      Chrome + 1
   :::column-end:::
   :::column span="2":::
      根据用户和开发人员的反馈，指示的功能或更改将在 Chrome 后附带一个版本。
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Chrome 或 Chrome + 1
   :::column-end:::
   :::column span="2":::
      根据用户和开发人员的反馈，指定的功能或更改将在同一时间或在 Chrome 后发布。
   :::column-end:::
:::row-end:::


<!-- image links -->  

<!-- links -->  

[DeployedEdgePoliciesSSLMinVersion]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin-Microsoft Edge-策略"  

[ChromePlatformStatus4664843055398912]: https://www.chromestatus.com/feature/4664843055398912 "不允许 XHR 中的同步页面消除 JavaScript-Chrome 平台状态"  
[ChromePlatformStatus5088147346030592]: https://www.chromestatus.com/feature/5088147346030592 "Cookie 默认为 SameSite = 不严格-Chrome 平台状态"  
[ChromePlatformStatus6251880185331712]: https://www.chromestatus.com/feature/6251880185331712 "引用策略：默认情况下为 "严格"-"在原点时"-"交叉时"-Chrome 平台状态"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "保护用户不受 Google Chrome-Google Online 安全博客中的不安全下载"  
