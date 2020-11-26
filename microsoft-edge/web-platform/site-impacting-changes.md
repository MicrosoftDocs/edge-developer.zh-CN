---
description: 提供可能会影响网站兼容性的高影响更改的摘要
title: Microsoft Edge 中影响网站兼容性的更改
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台
ms.openlocfilehash: 8c872546b29633cb22e0095fdd1a0326f89fc087
ms.sourcegitcommit: 5d3802721036dc7cd90e9e6f7ac90dc3acc24eec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "11191549"
---
# Microsoft Edge 中影响网站兼容性的更改  

web 正在不断发展，以改善用户体验、安全性和隐私性。  在某些情况下，所做的更改可能会显著影响现有页面的功能。  下表总结了 Microsoft Edge 团队当前正在跟踪的较高影响的更改。  经常查看本文;Microsoft Edge 团队将在思考演变、时间线实体化和新更改发布时，更新以下页面。  

| “更改” | 稳定渠道 | 实验 | 其他信息 |  
|:--- |:--- |:--- |:--- |
| Cookie 默认为 `SameSite=Lax` 和 `SameSite=None-requires-Secure` | [Chrome + 1](#release-comments) \ (Edge v86 \ )   | V82、Dev v82 | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息（包括 Google 的计划时间线进行此更改），请导航到 [Chrome 平台状态条目][ChromePlatformStatus5088147346030592]。  |  
| 引用策略：默认为 `strict-origin-when-cross-origin` | [Chrome + 1](#release-comments) \ (Edge v86 \ )   | V79、Dev v79 | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息（包括 Google 的计划时间线进行此更改），请导航到 [Chrome 平台状态条目][ChromePlatformStatus6251880185331712]。  |  
| `XmlHttpRequest`在页面消除中不允许同步 | [Chrome + 1](#release-comments) \ (Edge v83 \ )  |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  匹配的 Chrome，Microsoft Edge 提供了一个组策略来关闭此更改，直到 Edge v88。  有关详细信息（包括 Google 的计划时间线进行此更改），请导航到 [Chrome 平台状态条目][ChromePlatformStatus4664843055398912]。  |  
| 显示提示权限请求的微妙提示 | Edge v84 |  | 安静通知请求在地址栏中显示一个微妙的请求图标，用于使用或 API 请求的网站通知权限 `Notifications` `Push` ，替换完整或标准权限飞出提示 UI。  此功能当前已为所有用户启用。  若要退出静音通知请求，请导航到 `edge://settings/content/notifications` 。  将来，在某些情况下，Microsoft Edge 团队可能会探索重新启用完全飞出通知提示。  |  
| 默认关闭 TLS/1.0 和 TLS/1。1 | Edge v84 |  | [SSLMinVersion][DeployedgePoliciesSslversionmin]组策略允许重新启用 TLS/1.0 和 tls/1.1;该策略将保持可用，直到 Edge v90。  |  
| 阻止混合内容下载 | [Chrome + 1](#release-comments) \ (Edge v86 \ )   |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息（包括 Google 的计划时序表进行此更改），请导航到 [Google 安全博客条目][GoogleBlogSecurity20200206]。  在 Chrome 之后的一个版本计划中，Microsoft 推出针对警告或阻止的文件类型的推出计划。  |  
| 弃用 AppCache | [Chrome + 1](#release-comments) \ (Edge v86 \ )   |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息，请导航到 [WebDev 文档][WebDevAppCacheRemoval]。  针对 "弃用" 的 Microsoft 推出计划计划在 Chrome 之后的一个发布。  请求 [AppCache OriginTrial 令牌][ChromeDevelopersOrigintrialsAppCacheOriginTrial] 允许网站继续使用已弃用的 API，直到 Edge v90。  |  
| 删除 Adobe Flash | Edge v88  |  | 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息，请导航到 [Adobe Flash Chromium 路线图][ChromiumFlashRoadmapSupportRemoved]。  | 
| 关闭和删除 FTP | Edge v88  | Edge Beta v87 | 在 Edge Beta v87 中，默认情况下 FTP 支持处于关闭状态;在 Edge 稳定 v87，它将保持启用状态。  在 Edge v88 中，将完全删除 FTP 支持。  此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。  有关详细信息，请导航到 [Chrome 平台状态条目][ChromePlatformStatus6246151319715840]。  具有仍需要 FTP 支持的网站的企业可以通过将网站配置为使用 [IE 模式][DeployedgeEdgeIeMode]继续使用 ftp。  | 
| Autoupgrade 混合内容图像 | Edge v88  |  | 非安全 (HTTP) 对图像的引用将自动升级到 HTTPS;如果图像在 HTTPS 上不可用，则图像下载失败。 可以使用 [组策略][DeployedgePoliciesInsecurecontentallowedforurls] 控制此功能。 此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。 有关详细信息，请导航到 [Chrome 平台状态条目][ChromePlatformStatus4926989725073408]。  |  

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

[DeployedgeEdgeIeMode]: /deployedge/edge-ie-mode "关于 IE 模式 |Microsoft 文档"  
[DeployedgePoliciesInsecurecontentallowedforurls]:  /deployedge/microsoft-edge-policies#insecurecontentallowedforurls "InsecureContentAllowedForUrls-Microsoft Edge-政策 |Microsoft 文档"  
[DeployedgePoliciesSslversionmin]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin-Microsoft Edge-政策 |Microsoft 文档"  

[ChromePlatformStatus4664843055398912]: https://chromestatus.com/feature/4664843055398912 "在页面消除 JavaScript | 中不允许同步 XHRChrome 平台状态"  
[ChromePlatformStatus4926989725073408]: https://chromestatus.com/feature/4926989725073408 "Autoupgrade 图像混合内容 |Chrome 平台状态"  
[ChromePlatformStatus5088147346030592]: https://chromestatus.com/feature/5088147346030592 "Cookies 默认为 SameSite = 不严格 |Chrome 平台状态"  
[ChromePlatformStatus6246151319715840]: https://chromestatus.com/feature/6246151319715840 "弃用 FTP 支持 |Chrome 平台状态"  
[ChromePlatformStatus6251880185331712]: https://chromestatus.com/feature/6251880185331712 "引用策略：默认为严格的原始时间-跨线 |Chrome 平台状态"  

[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "从 Chromium 中删除的 Flash 支持 (目标： Chrome 88 +-2021) -Flash 路线图 |Chromium 项目"  

[ChromeDevelopersOrigintrialsAppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial token |Chrome 开发人员"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "保护用户不受 Google Chrome-Google Online 安全博客中的不安全下载" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal "准备 AppCache 删除 |web 开发"  

<!--todo:  cleanup links  -->  
