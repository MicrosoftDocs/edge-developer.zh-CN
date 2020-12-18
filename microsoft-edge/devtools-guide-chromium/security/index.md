---
description: 使用安全面板确保页面受到 HTTPS 的完全保护。
title: 了解 Microsoft Edge DevTools 的安全问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 5bef22eae8deacc81e31cf6d1c7791e016541346
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230612"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# 了解 Microsoft Edge DevTools 的安全问题  

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  Navigate to **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## 打开安全面板  

安全 **面板** 是 DevTools 中用于检查页面安全性的主要位置。  

1.  [打开 DevTools。][DevToolsOpen]  
1.  选择 **"安全** "选项卡以打开 **安全** 面板。  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-secure.msft.png":::
       安全**面板**  
    :::image-end:::  
    
## 常见问题  

### 非安全主源  

当页面的主源不安全时，安全概述**指出此页面不安全**。 ****  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="非安全页面" lightbox="../media/security-security-overview-non-secure.msft.png":::
   非安全页面  
:::image-end:::  

通过 HTTP 请求访问的 URL 时，会出现此问题。  若要确保安全性，您需要通过 HTTPS 请求它。  例如，如果您查看地址栏中的 URL，它可能类似于 `http://example.com` 。  若要确保 URL 安全，URL 应为 `https://example.com` 。  

如果已在服务器上设置 HTTPS，则解决此问题只需将服务器配置为将所有 HTTP 请求重定向到 HTTPS。  

如果尚未在服务器上设置 HTTPS，那么"让我们加密[][LetsEncrypt]"将提供一种免费且相对简单的启动过程的方法。  或者，你可以考虑在 CDN 上托管你的网站。  默认情况下，HTTPS 上的大多数主要 CDN 都承载网站。  

> [!TIP]
> Webhint 中的["使用][Webhint] [HTTPS"][WebhintUseHttps]提示可帮助自动执行确保所有 HTTP 请求都定向到 HTTPS 的过程。  

### 混合内容  

**混合** 内容意味着页面的主源是安全的，但页面从非安全源请求资源。  混合内容页仅部分受到保护，因为探查器可以访问 HTTP 内容，并且易受中间人攻击。  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="混合内容" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   混合内容  
:::image-end:::  

在上图中，选择"网络"面板中的"查看**1"** 请求以打开网络面板并应用筛选器，以便网络日志只显示非**** `mixed-content:displayed` 安全资源。 ****  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="网络日志中的混合资源" lightbox="../media/security-network-filter.msft.png":::
   网络日志中的 **混合资源**  
:::image-end:::  

## 查看详细信息  

### 查看主源证书  

从" **安全概述"** 中， **选择"查看证书** "以快速检查主源的证书。  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="主源证书" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   主源证书  
:::image-end:::  

### 查看源详细信息  

选择左侧导航中的条目之一以查看源的详细信息。  在详细信息页中，您可以查看连接和证书信息。  证书透明度信息也会在可用时显示。  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="主源详细信息" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   主源详细信息  
:::image-end:::  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  
[DevToolsOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[LetsEncrypt]: https://letsencrypt.org "加密 - 免费 SSL/TLS 证书"  

[Webhint]: https://webhint.io "webhint"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "使用 HTTPS |webhint 文档"  

<!--[mixed]: /web/fundamentals/security/prevent-mixed-content/what-is-mixed-content ""  -->

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/security/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
