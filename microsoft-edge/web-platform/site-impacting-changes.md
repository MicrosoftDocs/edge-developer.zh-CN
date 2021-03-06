---
description: 提供可能会影响站点兼容性的高影响更改的摘要
title: Microsoft Edge 中影响网站兼容性的更改
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/27/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台
ms.openlocfilehash: 815a350dc82d02e77354f3079880df9ce81750b7
ms.sourcegitcommit: 412ec98cd9f57f74af69acad0a317d1dffa3b323
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2021
ms.locfileid: "11640602"
---
# <a name="site-compatibility-impacting-changes-coming-to-microsoft-edge"></a>Microsoft Edge 中影响网站兼容性的更改  

Web 平台是一组用于构建网页的技术。  这些技术包括 HTML、CSS、JavaScript 和许多其他开放标准。  Web 平台不断发展以改进用户体验、安全性和隐私。  在某些情况下，更改可能会影响现有网页的功能。  有关即将推出的项目 Web Chromium更改的信息，请导航到 Chrome[平台状态发布时间线][ChromestatusFeaturesSchedule]。  

Microsoft Edge项目对 Web 平台进行几乎所有上游Chromium更改。  原因包括功能和兼容性原因。  Microsoft 保持对浏览器的完全Microsoft Edge，并可以延迟或拒绝更改。  该Microsoft Edge团队决定更改是否对浏览器用户的好处。  下表中Microsoft Edge计划Chromium时间或行为更改的功能区域。  该表还突出显示了团队正在跟踪Microsoft Edge影响大的更改。  

经常查看本文。  当Microsoft Edge发展、日程表稳定以及宣布新更改时，该团队会更新本文。  

| “更改” | 稳定渠道 | 实验 | 其他信息 |  
|:--- |:--- |:--- |:--- |
| 弃用 WebRTC 的计划 B SDP 语义 | [Chrome+1](#release-comments) \ (Edge v94\)   |  | 此更改发生在Chromium项目上，Microsoft Edge项目。 此更改将弃用 SDP 中的旧会话 (协议) 称为计划 B。它将替换为统一计划，该计划是一种兼容规范且跨浏览器兼容的 SDP 格式。 有关详细信息，请导航到 [Chrome 平台状态][ChromestatusFeature5823036655665152] 条目和 PSA：计划 B SDP 弃用和删除的 [时间线 - 请迁移到统一计划][PSADeprecateWebRTCPlanB]。 Microsoft 推出计划弃用计划计划在 Chrome 后的一个版本中发布。 请求 [WebRTC 计划 B 反向源试用令牌][ChromeDevelopersOrigintrialsWebRTCPlanBOriginTrial] 允许网站继续使用已弃用 API，直到 Edge v96。 |
| Cookie 默认为 `SameSite=Lax` 和 `SameSite=None-requires-Secure` | [Chrome+1](#release-comments) \ (Edge v86\)   | Canary v82，Dev v82 | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Chrome 平台状态条目][ChromestatusFeature5088147346030592]。  |  
| 引用者策略：默认为 `strict-origin-when-cross-origin` | [Chrome+1](#release-comments) \ (Edge v86\)   | Canary v79，Dev v79 | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Chrome 平台状态条目][ChromestatusFeature6251880185331712]。  |  
| 禁止在页面 `XmlHttpRequest` 内同步解除 | [Chrome+1](#release-comments) \ (Edge v83\)  |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  匹配 Chrome，Microsoft Edge提供在 Edge v88 之前关闭此更改的组策略。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Chrome 平台状态条目][ChromestatusFeature4664843055398912]。  |  
| 显示通知权限请求的细微提示 | Edge v84 |  | 安静通知请求在使用 或 API 请求的网站通知权限的地址栏中显示一个细微的请求图标，以替换完整或 `Notifications` `Push` 标准权限飞出提示 UI。  此功能当前为所有用户启用。  若要选择退出安静通知请求，请导航到 `edge://settings/content/notifications` 。  将来，Microsoft Edge团队可能会探索在某些情况下重新启用完整的飞出通知提示。  |  
| 关闭 TLS/1.0 和 TLS/1.1 | Edge v84 |  |  |  
| 阻止混合内容下载 | [Chrome+1](#release-comments) \ (Edge v86\)   |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，包括 Google 为此更改计划的时间线，请导航到 [Google 安全博客条目][GoogleBlogSecurity20200206]。  有关要发出警告或阻止的文件类型的 Microsoft 推出计划计划在 Chrome 发布后发布一次。  |  
| 弃用 AppCache | [Chrome+1](#release-comments) \ (Edge v86\)   |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，请导航到 [WebDev 文档][WebDevAppCacheRemoval]。  Microsoft 推出计划弃用计划计划在 Chrome 后的一个版本中发布。  请求 [AppCache OriginTrial 令牌][ChromeDevelopersOrigintrialsAppCacheOriginTrial] 允许站点继续使用已弃用 API，直到 Edge v90。  |  
| 删除 Adobe Flash | Edge v88  |  | 此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，请导航到[Adobe Flash Chromium路线图][ChromiumFlashRoadmapSupportRemoved]。  | 
| 删除 FTP 支持 | Edge v88  | Edge Beta v87 | 在 Edge v88 中，完全删除了 FTP 支持。  此更改发生在Chromium项目上，Microsoft Edge项目。  有关详细信息，请导航到 [Chrome 平台状态条目][ChromestatusFeature6246151319715840]。  具有仍然需要 FTP 支持的网站的企业可以通过将站点配置为使用 [IE][DeployedgeEdgeIeMode]模式来继续使用 FTP。  | 
| 自动升级混合内容图像 | Edge v88  |  | 对图像的非安全 \ (HTTP\) 会自动升级到 HTTPS;如果图像无法通过 HTTPS 访问，则图像下载将失败。 组 [策略][DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls] 可用于控制此功能。 此更改发生在Chromium项目上，Microsoft Edge项目。 有关详细信息，请导航到 [Chrome 平台状态条目][ChromestatusFeature4926989725073408]。  | 
| 阻止第三方 Cookie 时不允许 HTTP 身份验证  | Edge v87  |  | 从 Edge v87 开始，当阻止第三方请求的 Cookie 时，使用 [BlockThirdPartyCookies][DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies] 策略或 中的开关也会禁止 `edge://settings` HTTP 身份验证。 如果托管列表的终结点Enterprise HTTP[][DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy]身份验证，此更改可能会影响Internet Explorer模式站点列表下载。  若要允许将 Cookie 和 HTTP 身份验证同时用于Enterprise站点列表下载，请向[CookiesAllowedForURLs][DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls]策略添加匹配的 URL 模式。  |
| 在 TLS 中删除 3DES  | Edge v93  |  | 从 Edge v93 开始，将TLS_RSA_WITH_3DES_EDE_CBC_SHA密码套件的支持。 此更改发生在Chromium项目上，Microsoft Edge项目。 有关详细信息，请导航到 [Chrome 平台状态条目][ChromestatusFeature6678134168485888]。 此外，在 Edge v93 中，兼容性策略可用于支持需要保留与过时服务器的兼容性的方案。 此兼容性策略将过时，并停止在 Edge v95 中运行。 请确保在更新之前更新受影响的服务器。 |
| 将专用网络请求限制为保护上下文  | Edge v93  |  | 从 Edge v93 开始，从 internet (访问本地 intranet) 需要通过 HTTPS 传递这些页面。 此更改发生在Chromium项目上，Microsoft Edge项目。 有关详细信息，请导航到 [Chrome 平台状态条目][ChromestatusFeature5436853517811712]。 有两种兼容性策略可用于支持需要保留与非安全页面的兼容性的方案 [：InsecurePrivateNetworkRequestAllowed][DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowed] 和 [InsecurePrivateNetworkRequestAllowedForUrls][DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowedForUrls]。 |

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
[DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowed]: /deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed "InsecurePrivateNetworkRequestsAllowed - Microsoft Edge - 策略|Microsoft Docs"
[DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowedForUrls]: /deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls "InsecurePrivateNetworkRequestsAllowedForUrls - Microsoft Edge - 策略|Microsoft Docs"

[ChromestatusFeaturesSchedule]: https://www.chromestatus.com/features/schedule "发布时间线|Chrome 平台状态"  
[ChromestatusFeature4664843055398912]: https://chromestatus.com/feature/4664843055398912 "禁止在页面解除 JavaScript 中同步 XHR |Chrome 平台状态"  
[ChromestatusFeature4926989725073408]: https://chromestatus.com/feature/4926989725073408 "自动升级图像混合内容|Chrome 平台状态"  
[ChromestatusFeature5088147346030592]: https://chromestatus.com/feature/5088147346030592 "Cookie 默认为 SameSite=Lax |Chrome 平台状态"  
[ChromestatusFeature6246151319715840]: https://chromestatus.com/feature/6246151319715840 "弃用 FTP 支持|Chrome 平台状态"  
[ChromestatusFeature6251880185331712]: https://chromestatus.com/feature/6251880185331712 "引用器策略：默认为 strict-origin-when-cross-origin |Chrome 平台状态"  
[ChromestatusFeature6678134168485888]: https://chromestatus.com/feature/6678134168485888 "在 TLS 服务中删除 3DES |Chrome 平台状态"
[ChromestatusFeature5436853517811712]: https://chromestatus.com/feature/5436853517811712 "限制子源的专用网络请求，以确保安全上下文|Chrome 平台状态"
[ChromestatusFeature5823036655665152]: https://www.chromestatus.com/feature/5823036655665152 "[WebRTC]弃用和删除计划 B (已弃) |Chrome 平台状态"
[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "Flash 支持已从目标Chromium (：Chrome 88+ - 2021 年 1 月 2021) - Flash 路线图|Chromium项目"  

[ChromeDevelopersOrigintrialsAppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial 令牌|Chrome 开发人员"  
[ChromeDevelopersOrigintrialsWebRTCPlanBOriginTrial]: https://developer.chrome.com/origintrials/#/view_trial/3892235977954951169 "WebRTC 计划 B 反向源试用令牌|Chrome 开发人员"

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "在 Google Chrome 中防止用户下载不安全 - Google Online 安全博客" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal "准备 AppCache 删除|web.dev"  

[PSADeprecateWebRTCPlanB]: https://groups.google.com/g/discuss-webrtc/c/UBtZfawdIAA/m/-UVQQcubBQAJ "PSA：计划 B SDP 弃用和删除的时间线 - 请迁移到统一计划"

<!--todo:  cleanup links  -->  
