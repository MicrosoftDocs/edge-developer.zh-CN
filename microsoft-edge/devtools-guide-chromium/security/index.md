---
description: 使用 "安全" 面板确保页面完全受 HTTPS 保护。
title: 了解 Microsoft Edge DevTools 的安全问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 2538f80b08c8162d27f075775075a8b81c5f7725
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993574"
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

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  See **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## 打开 "安全" 面板   

**安全**面板是检查页面安全性的 DevTools 中的主要位置。  

1.  [打开 DevTools][DevToolsOpen]。  
1.  单击 " **安全** " 选项卡以打开 " **安全** " 面板。  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-secure.msft.png":::
       **安全**面板  
    :::image-end:::  
    
## 常见问题   

### 不安全的主要来源   

当页面的主来源不安全时， **安全概述** 显示 **此页面不安全**。  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-non-secure.msft.png":::
   非安全页面  
:::image-end:::  

当通过 HTTP 请求访问的 URL 时，会出现此问题。  若要使其安全，你需要通过 HTTPS 请求它。  例如，如果你查看地址栏中的 URL，它可能看起来类似于 `http://example.com` 。  若要使其安全，应显示 URL `https://example.com` 。  

如果你已在服务器上设置了 HTTPS，则你需要执行以下操作来解决此问题：将你的服务器配置为将所有 HTTP 请求重定向到 HTTPS。  

如果您没有在服务器上设置 HTTPS， [我们的加密][LetsEncrypt] 功能提供了一种免费且相对简单的启动过程的方式。  或者，你可能会考虑在 CDN 上托管你的网站。  默认情况下，HTTPS 上最主要的 Cdn 主机站点。  

> [!TIP]
> [Webhint][Webhint]中的 "[使用 HTTPS][WebhintUseHttps] " 提示可帮助自动执行确保所有 HTTP 请求定向到 HTTPS 的过程。  

### 混合内容   

**混合内容** 意味着页面的主原始位置是安全的，但是页面请求的资源来自不安全来源。  混合内容页面只是部分受保护的，因为 HTTP 内容可以被嗅探者访问，并且容易受到中间人攻击。  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   混合内容  
:::image-end:::  

在上图中，单击 " **在网络面板中查看1个请求** " 以打开 " **网络** " 面板并应用 `mixed-content:displayed` 筛选器，以便 **网络日志** 仅显示不安全的资源。  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="安全面板" lightbox="../media/security-network-filter.msft.png":::
   **网络日志**中的混合资源  
:::image-end:::  

## 查看详细信息   

### 查看主原始证书   

从 **安全概述**中，单击 " **查看证书** " 以快速检查主源的证书。  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   主原始证书  
:::image-end:::  

### 查看来源详细信息   

单击左侧导航栏中的其中一个条目以查看来源的详细信息。  从 "详细信息" 页面，您可以查看连接和证书信息。  还会显示证书透明信息（如果可用）。  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   主要来源详细信息  
:::image-end:::  

<!--  
 


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevToolsOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  


[LetsEncrypt]: https://letsencrypt.org "我们的加密-免费的 SSL/TLS 证书"  

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
