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





# <span data-ttu-id="fb2cc-104">了解 Microsoft Edge DevTools 的安全问题</span><span class="sxs-lookup"><span data-stu-id="fb2cc-104">Understand security issues with Microsoft Edge DevTools</span></span>   

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  See **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <span data-ttu-id="fb2cc-105">打开 "安全" 面板</span><span class="sxs-lookup"><span data-stu-id="fb2cc-105">Open the Security panel</span></span>   

<span data-ttu-id="fb2cc-106">**安全**面板是检查页面安全性的 DevTools 中的主要位置。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-106">The **Security** panel is the main place in DevTools for inspecting the security of a page.</span></span>  

1.  <span data-ttu-id="fb2cc-107">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-107">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="fb2cc-108">单击 " **安全** " 选项卡以打开 " **安全** " 面板。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-108">Click the **Security** tab to open the **Security** panel.</span></span>  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-secure.msft.png":::
       <span data-ttu-id="fb2cc-110">**安全**面板</span><span class="sxs-lookup"><span data-stu-id="fb2cc-110">The **Security** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fb2cc-111">常见问题</span><span class="sxs-lookup"><span data-stu-id="fb2cc-111">Common problems</span></span>   

### <span data-ttu-id="fb2cc-112">不安全的主要来源</span><span class="sxs-lookup"><span data-stu-id="fb2cc-112">Non-secure main origins</span></span>   

<span data-ttu-id="fb2cc-113">当页面的主来源不安全时， **安全概述** 显示 **此页面不安全**。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-113">When the main origin of a page is not secure, the **Security Overview** says **This page is not secure**.</span></span>  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-non-secure.msft.png":::
   <span data-ttu-id="fb2cc-115">非安全页面</span><span class="sxs-lookup"><span data-stu-id="fb2cc-115">A non-secure page</span></span>  
:::image-end:::  

<span data-ttu-id="fb2cc-116">当通过 HTTP 请求访问的 URL 时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-116">This problem occurs when the URL that you visited was requested over HTTP.</span></span>  <span data-ttu-id="fb2cc-117">若要使其安全，你需要通过 HTTPS 请求它。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-117">To make it secure you need to request it over HTTPS.</span></span>  <span data-ttu-id="fb2cc-118">例如，如果你查看地址栏中的 URL，它可能看起来类似于 `http://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-118">For example, if you look at the URL in your address bar, it probably looks similar to `http://example.com`.</span></span>  <span data-ttu-id="fb2cc-119">若要使其安全，应显示 URL `https://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-119">To make it secure the URL should be `https://example.com`.</span></span>  

<span data-ttu-id="fb2cc-120">如果你已在服务器上设置了 HTTPS，则你需要执行以下操作来解决此问题：将你的服务器配置为将所有 HTTP 请求重定向到 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-120">If you already set up HTTPS on your server, all you need to do to fix this problem is configure your server to redirect all HTTP requests to HTTPS.</span></span>  

<span data-ttu-id="fb2cc-121">如果您没有在服务器上设置 HTTPS， [我们的加密][LetsEncrypt] 功能提供了一种免费且相对简单的启动过程的方式。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-121">If you have not set up HTTPS on your server, [Let's Encrypt][LetsEncrypt] provides a free and relatively-easy way to start the process.</span></span>  <span data-ttu-id="fb2cc-122">或者，你可能会考虑在 CDN 上托管你的网站。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-122">Or, you might consider hosting your site on a CDN.</span></span>  <span data-ttu-id="fb2cc-123">默认情况下，HTTPS 上最主要的 Cdn 主机站点。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-123">Most major CDNs host sites on HTTPS by default now.</span></span>  

> [!TIP]
> <span data-ttu-id="fb2cc-124">[Webhint][Webhint]中的 "[使用 HTTPS][WebhintUseHttps] " 提示可帮助自动执行确保所有 HTTP 请求定向到 HTTPS 的过程。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-124">The [Use HTTPS][WebhintUseHttps] hint in [webhint][Webhint] may help automate the process of making sure that all HTTP requests are directed to HTTPS.</span></span>  

### <span data-ttu-id="fb2cc-125">混合内容</span><span class="sxs-lookup"><span data-stu-id="fb2cc-125">Mixed content</span></span>   

<span data-ttu-id="fb2cc-126">**混合内容** 意味着页面的主原始位置是安全的，但是页面请求的资源来自不安全来源。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-126">**Mixed content** means that the main origin of a page is secure, but the page requested resources from non-secure origins.</span></span>  <span data-ttu-id="fb2cc-127">混合内容页面只是部分受保护的，因为 HTTP 内容可以被嗅探者访问，并且容易受到中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-127">Mixed content pages are only partially protected because the HTTP content is accessible to sniffers and vulnerable to man-in-the-middle attacks.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   <span data-ttu-id="fb2cc-129">混合内容</span><span class="sxs-lookup"><span data-stu-id="fb2cc-129">Mixed content</span></span>  
:::image-end:::  

<span data-ttu-id="fb2cc-130">在上图中，单击 " **在网络面板中查看1个请求** " 以打开 " **网络** " 面板并应用 `mixed-content:displayed` 筛选器，以便 **网络日志** 仅显示不安全的资源。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-130">In the previous figure, click **View 1 request in Network panel** to open the **Network** panel and apply the `mixed-content:displayed` filter so that the **Network Log** only shows non-secure resources.</span></span>  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="安全面板" lightbox="../media/security-network-filter.msft.png":::
   <span data-ttu-id="fb2cc-132">**网络日志**中的混合资源</span><span class="sxs-lookup"><span data-stu-id="fb2cc-132">Mixed resources in the **Network Log**</span></span>  
:::image-end:::  

## <span data-ttu-id="fb2cc-133">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="fb2cc-133">View details</span></span>   

### <span data-ttu-id="fb2cc-134">查看主原始证书</span><span class="sxs-lookup"><span data-stu-id="fb2cc-134">View main origin certificate</span></span>   

<span data-ttu-id="fb2cc-135">从 **安全概述**中，单击 " **查看证书** " 以快速检查主源的证书。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-135">From the **Security Overview**, click **View certificate** to quickly inspect the certificate for the main origin.</span></span>  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   <span data-ttu-id="fb2cc-137">主原始证书</span><span class="sxs-lookup"><span data-stu-id="fb2cc-137">A main origin certificate</span></span>  
:::image-end:::  

### <span data-ttu-id="fb2cc-138">查看来源详细信息</span><span class="sxs-lookup"><span data-stu-id="fb2cc-138">View origin details</span></span>   

<span data-ttu-id="fb2cc-139">单击左侧导航栏中的其中一个条目以查看来源的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-139">Click one of the entries in the left-hand nav to view the details of the origin.</span></span>  <span data-ttu-id="fb2cc-140">从 "详细信息" 页面，您可以查看连接和证书信息。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-140">From the details page you are able to view connection and certificate information.</span></span>  <span data-ttu-id="fb2cc-141">还会显示证书透明信息（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-141">Certificate transparency information is also shown when available.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   <span data-ttu-id="fb2cc-143">主要来源详细信息</span><span class="sxs-lookup"><span data-stu-id="fb2cc-143">Main origin details</span></span>  
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
> <span data-ttu-id="fb2cc-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fb2cc-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/security/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/security/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="fb2cc-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="fb2cc-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
