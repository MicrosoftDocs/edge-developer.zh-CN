---
description: 提供可能会影响站点兼容性的高影响更改的摘要
title: Microsoft Edge 中影响网站兼容性的更改
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台
ms.openlocfilehash: 810c4e0a3e4c719987fbc374330599a58f055166
ms.sourcegitcommit: bbbf722067f1d255f59ab384e66798f8b77ef609
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "11574573"
---
# <a name="site-compatibility-impacting-changes-coming-to-microsoft-edge"></a>Microsoft Edge 中影响网站兼容性的更改  

Web 平台是一组用于构建网页的技术。  这些技术包括 HTML、CSS、JavaScript 和许多其他开放标准。  Web 平台不断发展以改进用户体验、安全性和隐私。  在某些情况下，更改可能会影响现有网页的功能。  有关即将推出的项目 Web Chromium更改的信息，请导航到 Chrome[平台状态发布时间线][ChromestatusFeaturesSchedule]。  

Microsoft Edge项目对 Web 平台进行几乎所有上游Chromium更改。  原因包括功能和兼容性原因。  Microsoft 保持对浏览器的完全Microsoft Edge，并可以延迟或拒绝更改。  该Microsoft Edge团队决定更改是否对浏览器用户的好处。  下表中Microsoft Edge计划Chromium时间或行为更改的功能区域。  该表还突出显示了团队正在跟踪Microsoft Edge影响大的更改。  

经常查看本文。  当Microsoft Edge发展、日程表稳定以及宣布新更改时，该团队会更新本文。  

| “更改” | 稳定渠道 | 实验 | 其他信息 |  
|:--- |:--- |:--- |:--- |
| Cookie 默认为 `SameSite=Lax` 和 `SameSite=None-requires-Secure` | [Chrome+1](#release-comments) \ (Edge v86\)   | Canary v82，Dev v82 | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Chrome 平台状态条目][ChromestatusFeature5088147346030592]。  |  
| 引用者策略：默认为 `strict-origin-when-cross-origin` | [Chrome+1](#release-comments) \ (Edge v86\)   | Canary v79，Dev v79 | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Chrome 平台状态条目][ChromestatusFeature6251880185331712]。  |  
| 禁止在页面 `XmlHttpRequest` 内同步解除 | [Chrome+1](#release-comments) \ (Edge v83\)  |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  匹配 Chrome，Microsoft Edge提供在 Edge v88 之前关闭此更改的组策略。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Chrome 平台状态条目][ChromestatusFeature4664843055398912]。  |  
| 显示通知权限请求的细微提示 | Edge v84 |  | 安静通知请求在使用 或 API 请求的网站通知权限的地址栏中显示一个细微的请求图标，以替换完整或 `Notifications` `Push` 标准权限飞出提示 UI。  此功能当前为所有用户启用。  若要选择退出安静通知请求，请导航到 `edge://settings/content/notifications` 。  将来，Microsoft Edge团队可能会探索在某些情况下重新启用完整的飞出通知提示。  |  
| 默认情况下关闭 TLS/1.0 和 TLS/1.1 | Edge v84 |  | [SSLMinVersion][DeployedgeMicrosoftEdgePoliciesSslversionmin]组策略允许重新启用 TLS/1.0 和 TLS/1.1;策略在 Edge v90 之前仍然可用。  |  
| 阻止混合内容下载 | [Chrome+1](#release-comments) \ (Edge v86\)   |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Google 安全博客条目][GoogleBlogSecurity20200206]。  有关要发出警告或阻止的文件类型的 Microsoft 推出计划计划在 Chrome 发布后发布一次。  |  
| 弃用 AppCache | [Chrome+1](#release-comments) \ (Edge v86\)   |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，请导航到 [WebDev 文档][WebDevAppCacheRemoval]。  Microsoft 推出计划弃用计划计划在 Chrome 后的一个版本中发布。  请求 [AppCache OriginTrial 令牌][ChromeDevelopersOrigintrialsAppCacheOriginTrial] 允许站点继续使用已弃用 API，直到 Edge v90。  |  
| 删除 Adobe Flash | Edge v88  |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，请导航到[Adobe Flash Chromium路线图][ChromiumFlashRoadmapSupportRemoved]。  | 
| 关闭和删除 FTP | Edge v88  | Edge Beta v87 | 在 Edge Beta v87 中，FTP 支持默认处于关闭状态;在 Edge Stable v87 中保持启用状态。  在 Edge v88 中，完全删除了 FTP 支持。  此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，请导航到 [Chrome 平台状态条目][ChromestatusFeature6246151319715840]。  具有仍然需要 FTP 支持的网站的企业可以通过将站点配置为使用 [IE][DeployedgeEdgeIeMode]模式来继续使用 FTP。  | 
| 自动升级混合内容图像 | Edge v88  |  | 对图像的非安全 \ (HTTP\) 会自动升级到 HTTPS;如果图像无法通过 HTTPS 访问，则图像下载将失败。 组 [策略][DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls] 可用于控制此功能。 此更改发生在Chromium项目上，Microsoft Edge项目。 有关详细信息，请导航到 [Chrome 平台状态条目][ChromestatusFeature4926989725073408]。  | 
| 阻止第三方 Cookie 时不允许 HTTP 身份验证  | Edge v87  |  | 从 Edge v87 开始，当针对第三方请求（使用[BlockThirdPartyCookies][DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies]策略或通过边缘 设置 页面）阻止 Cookie 时，也会禁止 HTTP 身份验证。 如果托管列表的终结点Enterprise HTTP[][DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy]身份验证，此更改可能会影响Internet Explorer模式站点列表下载。  若要允许将 Cookie 和 HTTP 身份验证同时用于Enterprise站点列表下载，请向[CookiesAllowedForURLs][DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls]策略添加匹配的 URL 模式。  |   

##### <a name="release-comments"></a>发布注释  

:::row:::
   :::column span="1":::
      Chrome+1  
   :::column-end:::
   :::column span="2":::
      根据用户和开发人员的反馈，指示的功能或更改在 Chrome 后发布一次。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Chrome 或 Chrome+1  
   :::column-end:::
   :::column span="2":::
      根据用户和开发人员的反馈，指示的功能或更改同时提供，或在 Chrome 发布后的一个版本中提供。  
   :::column-end:::
:::row-end:::

<!-- links -->  

[DeployedgeEdgeIeMode]: /deployedge/edge-ie-mode "关于 IE 模式|Microsoft Docs"  
[DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy]: /deployedge/edge-ie-mode-policies#configure-using-the-use-the-enterprise-mode-ie-website-list-policy "使用&quot;使用 Enterprise 模式 IE 网站列表策略 - 配置 IE 模式策略&quot;|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies]: /deployedge/microsoft-edge-policies#blockthirdpartycookies "BlockThirdPartyCookies - Microsoft Edge - 策略|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls]: /deployedge/microsoft-edge-policies#cookiesallowedforurls "CookiesAllowedForUrls - Microsoft Edge - 策略|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls]:  /deployedge/microsoft-edge-policies#insecurecontentallowedforurls "InsecureContentAllowedForUrls - Microsoft Edge - 策略|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesSslversionmin]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin - Microsoft Edge - 策略|Microsoft Docs"  

[ChromestatusFeaturesSchedule]: https://www.chromestatus.com/features/schedule "发布时间线|Chrome 平台状态"  
[ChromestatusFeature4664843055398912]: https://chromestatus.com/feature/4664843055398912 "禁止在页面解除 JavaScript 中同步 XHR |Chrome 平台状态"  
[ChromestatusFeature4926989725073408]: https://chromestatus.com/feature/4926989725073408 "自动升级图像混合内容|Chrome 平台状态"  
[ChromestatusFeature5088147346030592]: https://chromestatus.com/feature/5088147346030592 "Cookie 默认为 SameSite=Lax |Chrome 平台状态"  
[ChromestatusFeature6246151319715840]: https://chromestatus.com/feature/6246151319715840 "弃用 FTP 支持|Chrome 平台状态"  
[ChromestatusFeature6251880185331712]: https://chromestatus.com/feature/6251880185331712 "引用器策略：默认为 strict-origin-when-cross-origin |Chrome 平台状态"  

[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "Flash 支持已从目标Chromium (：Chrome 88+ - 2021 年 1 月 2021) - Flash 路线图|Chromium项目"  

[ChromeDevelopersOrigintrialsAppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial 令牌|Chrome 开发人员"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "在 Google Chrome 中防止用户下载不安全 - Google Online 安全博客" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal "准备 AppCache 删除|web.dev"  

<!--todo:  cleanup links  -->  
