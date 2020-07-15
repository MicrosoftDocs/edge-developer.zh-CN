---
description: 提供可能会影响网站兼容性的高影响更改的摘要
title: Microsoft Edge 中的影响网站兼容性的更改
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台
ms.openlocfilehash: 0785544d0245827f58f3f7c71edd5a18a3d12404
ms.sourcegitcommit: d982699ee25e8704fcaad7a15b4d8d015aef2f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "10868763"
---
# Microsoft Edge 中的影响网站兼容性的更改  

Web 不断发展，以改进用户体验、安全性和隐私。  在某些情况下，所做的更改可能会显著影响现有页面的功能。  下表总结了 Microsoft Edge 团队当前正在跟踪的最高影响的更改。  请经常回来查看;Microsoft Edge 团队将在思考演变、时间线实体化和新更改发布时，更新以下页面。  

| “更改” | Stable 渠道 | 实验 | 其他信息 |  
|:--- |:--- |:--- |:--- |
| Cookie 默认为 `SameSite=Lax` | [Chrome 或 Chrome + 1](#release-comments)  | V82、Dev v82 | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus5088147346030592]。  |  
| 引用策略：默认为 `strict-origin-when-cross-origin` | [Chrome 或 Chrome + 1](#release-comments)  | V79、Dev v79 | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus6251880185331712]。  |  
| 在页面消除期间禁止同步 XmlHttpRequest | [Chrome + 1](#release-comments) \ （Edge v83 \） |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  匹配的 Chrome，Microsoft Edge 提供组策略以禁用此更改，直到 Edge v88。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus4664843055398912]。  |  
| 显示提示权限请求的微妙提示 | Edge v84 |  | 安静通知请求在地址栏中显示一个微妙的请求图标，用于使用或 API 请求的网站通知权限 `Notifications` `Push` ，替换完整或标准权限飞出提示 UI。  此功能当前已为所有用户启用。  若要退出静音通知请求，请转到 `edge://settings/content/notifications` 。  将来，在某些情况下，Microsoft Edge 团队可能会探索重新启用完全飞出通知提示。  |  
| 默认情况下禁用 TLS/1.0 和 TLS/1。1 | Edge v84 |  | 若要帮助发现受影响的网站，你可以将该 `edge://flags/#display-legacy-tls-warnings` 标志设置为导致 Microsoft Edge 在加载需要旧版 TLS 协议的页面时显示非阻止 "不安全" 通知。  [SSLMinVersion][DeployedEdgePoliciesSSLMinVersion]组策略允许重新启用 TLS/1.0 和 tls/1.1;该策略将保持可用，直到 Edge 88。  |  
| 阻止混合内容下载 | [Chrome + 1](#release-comments) \ （Edge v86 \）  |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[google 安全博客条目][GoogleBlogSecurity20200206]。  在 Chrome 之后的一个版本计划中，Microsoft 推出针对警告或阻止的文件类型的推出计划。  |  
| 弃用 AppCache | [Chrome + 1](#release-comments) \ （Edge v86 \）  |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息，请参阅[WebDev 文档][WebDevAppCacheRemoval]。  针对 "弃用" 的 Microsoft 推出计划计划在 Chrome 之后的一个发布。  请求[AppCache OriginTrial 令牌][AppCacheOriginTrial]允许网站继续使用已弃用的 API，直到 Edge v90。  |  
| 删除 Adobe Flash | Edge v88  |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息，请查看[Adobe Flash Chromium 路线图][ChromiumFlashRoadmapSupportRemoved]。  | 
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

<!-- links -->  

[DeployedEdgePoliciesSSLMinVersion]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin-Microsoft Edge-政策 |Microsoft 文档"  

[ChromePlatformStatus4664843055398912]: https://www.chromestatus.com/feature/4664843055398912 "在页面消除 JavaScript | 中不允许同步 XHRChrome 平台状态"  
[ChromePlatformStatus5088147346030592]: https://www.chromestatus.com/feature/5088147346030592 "Cookies 默认为 SameSite = 不严格 |Chrome 平台状态"  
[ChromePlatformStatus6251880185331712]: https://www.chromestatus.com/feature/6251880185331712 "引用策略：默认为严格的原始时间-跨线 |Chrome 平台状态"  

[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "从 Chromium 中删除的 Flash 支持（目标： Chrome 88 +-Jan 2021）-Flash 路线图 |Chromium 项目"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "保护用户不受 Google Chrome-Google Online 安全博客中的不安全下载" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal/ "AppCache 删除"
[AppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial 令牌"
