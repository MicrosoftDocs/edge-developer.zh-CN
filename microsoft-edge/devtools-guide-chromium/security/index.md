---
title: 了解 Microsoft Edge DevTools 的安全问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 05112d5270f41ce83daa935b8137c4a773ad25a0
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611908"
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





# <span data-ttu-id="fc704-103">了解 Microsoft Edge DevTools 的安全问题</span><span class="sxs-lookup"><span data-stu-id="fc704-103">Understand Security Issues With Microsoft Edge DevTools</span></span>   

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  See **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <span data-ttu-id="fc704-104">打开 "安全" 面板</span><span class="sxs-lookup"><span data-stu-id="fc704-104">Open the Security panel</span></span>   

<span data-ttu-id="fc704-105">**安全**面板是检查页面安全性的 DevTools 中的主要位置。</span><span class="sxs-lookup"><span data-stu-id="fc704-105">The **Security** panel is the main place in DevTools for inspecting the security of a page.</span></span>  

1.  <span data-ttu-id="fc704-106">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="fc704-106">[Open DevTools][DevToolsOpen].</span></span>  

1.  <span data-ttu-id="fc704-107">单击 "**安全**" 选项卡以打开 "**安全**" 面板。</span><span class="sxs-lookup"><span data-stu-id="fc704-107">Click the **Security** tab to open the **Security** panel.</span></span>  
    
    > ##### <span data-ttu-id="fc704-108">图 1</span><span class="sxs-lookup"><span data-stu-id="fc704-108">Figure 1</span></span>  
    > <span data-ttu-id="fc704-109">安全面板</span><span class="sxs-lookup"><span data-stu-id="fc704-109">The Security panel</span></span>  
    > ![安全面板][ImageSecurityPanel]  
    
## <span data-ttu-id="fc704-111">常见问题</span><span class="sxs-lookup"><span data-stu-id="fc704-111">Common problems</span></span>   

### <span data-ttu-id="fc704-112">不安全的主要来源</span><span class="sxs-lookup"><span data-stu-id="fc704-112">Non-secure main origins</span></span>   

<span data-ttu-id="fc704-113">当页面的主来源不安全时，**安全概述**显示**此页面不安全**。</span><span class="sxs-lookup"><span data-stu-id="fc704-113">When the main origin of a page is not secure, the **Security Overview** says **This page is not secure**.</span></span>  

> ##### <span data-ttu-id="fc704-114">图 2</span><span class="sxs-lookup"><span data-stu-id="fc704-114">Figure 2</span></span>  
> <span data-ttu-id="fc704-115">非安全页面</span><span class="sxs-lookup"><span data-stu-id="fc704-115">A non-secure page</span></span>  
> ![非安全页面][ImageNonSecurePage]  

<span data-ttu-id="fc704-117">当通过 HTTP 请求访问的 URL 时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="fc704-117">This problem occurs when the URL that you visited was requested over HTTP.</span></span>  <span data-ttu-id="fc704-118">若要使其安全，你需要通过 HTTPS 请求它。</span><span class="sxs-lookup"><span data-stu-id="fc704-118">To make it secure you need to request it over HTTPS.</span></span>  <span data-ttu-id="fc704-119">例如，如果你查看地址栏中的 URL，它可能看起来类似于 `http://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="fc704-119">For example, if you look at the URL in your address bar, it probably looks similar to `http://example.com`.</span></span>  <span data-ttu-id="fc704-120">若要使其安全，应显示 URL `https://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="fc704-120">To make it secure the URL should be `https://example.com`.</span></span>  

<span data-ttu-id="fc704-121">如果你已在服务器上设置了 HTTPS，则你需要执行以下操作来解决此问题：将你的服务器配置为将所有 HTTP 请求重定向到 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="fc704-121">If you already set up HTTPS on your server, all you need to do to fix this problem is configure your server to redirect all HTTP requests to HTTPS.</span></span>  

<span data-ttu-id="fc704-122">如果您没有在服务器上设置 HTTPS，[我们的加密][LetsEncrypt]功能提供了一种免费且相对简单的启动过程的方式。</span><span class="sxs-lookup"><span data-stu-id="fc704-122">If you have not set up HTTPS on your server, [Let's Encrypt][LetsEncrypt] provides a free and relatively-easy way to start the process.</span></span>  <span data-ttu-id="fc704-123">或者，你可能会考虑在 CDN 上托管你的网站。</span><span class="sxs-lookup"><span data-stu-id="fc704-123">Or, you might consider hosting your site on a CDN.</span></span>  <span data-ttu-id="fc704-124">默认情况下，HTTPS 上最主要的 Cdn 主机站点。</span><span class="sxs-lookup"><span data-stu-id="fc704-124">Most major CDNs host sites on HTTPS by default now.</span></span>  

> [!TIP]
> <span data-ttu-id="fc704-125">[Webhint][Webhint]中的 "[使用 HTTPS][WebhintUseHttps] " 提示可帮助自动执行确保所有 HTTP 请求定向到 HTTPS 的过程。</span><span class="sxs-lookup"><span data-stu-id="fc704-125">The [Use HTTPS][WebhintUseHttps] hint in [webhint][Webhint] may help automate the process of making sure that all HTTP requests are directed to HTTPS.</span></span>  

### <span data-ttu-id="fc704-126">混合内容</span><span class="sxs-lookup"><span data-stu-id="fc704-126">Mixed content</span></span>   

<span data-ttu-id="fc704-127">**混合内容**意味着页面的主原始位置是安全的，但是页面请求的资源来自不安全来源。</span><span class="sxs-lookup"><span data-stu-id="fc704-127">**Mixed content** means that the main origin of a page is secure, but the page requested resources from non-secure origins.</span></span>  <span data-ttu-id="fc704-128">混合内容页面只是部分受保护的，因为 HTTP 内容可以被嗅探者访问，并且容易受到中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="fc704-128">Mixed content pages are only partially protected because the HTTP content is accessible to sniffers and vulnerable to man-in-the-middle attacks.</span></span>  

> ##### <span data-ttu-id="fc704-129">图 3</span><span class="sxs-lookup"><span data-stu-id="fc704-129">Figure 3</span></span>  
> <span data-ttu-id="fc704-130">混合内容</span><span class="sxs-lookup"><span data-stu-id="fc704-130">Mixed content</span></span>  
> ![混合内容][ImageMixedContent]  

<span data-ttu-id="fc704-132">在[图 3](#figure-3)中，单击 **"在网络面板中查看1个请求**" 以打开 "**网络**" 面板并应用 `mixed-content:displayed` 筛选器，以便**网络日志**仅显示不安全的资源。</span><span class="sxs-lookup"><span data-stu-id="fc704-132">In [Figure 3](#figure-3), click **View 1 request in Network panel** to open the **Network** panel and apply the `mixed-content:displayed` filter so that the **Network Log** only shows non-secure resources.</span></span>  

> ##### <span data-ttu-id="fc704-133">图 4</span><span class="sxs-lookup"><span data-stu-id="fc704-133">Figure 4</span></span>  
> <span data-ttu-id="fc704-134">网络日志中的混合资源</span><span class="sxs-lookup"><span data-stu-id="fc704-134">Mixed resources in the Network Log</span></span>  
> ![网络日志中的混合资源][ImageMixedResourcesNetworkLog]  

## <span data-ttu-id="fc704-136">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="fc704-136">View details</span></span>   

### <span data-ttu-id="fc704-137">查看主原始证书</span><span class="sxs-lookup"><span data-stu-id="fc704-137">View main origin certificate</span></span>   

<span data-ttu-id="fc704-138">从**安全概述**中，单击 "**查看证书**" 以快速检查主源的证书。</span><span class="sxs-lookup"><span data-stu-id="fc704-138">From the **Security Overview**, click **View certificate** to quickly inspect the certificate for the main origin.</span></span>  

> ##### <span data-ttu-id="fc704-139">图 5</span><span class="sxs-lookup"><span data-stu-id="fc704-139">Figure 5</span></span>  
> <span data-ttu-id="fc704-140">主原始证书</span><span class="sxs-lookup"><span data-stu-id="fc704-140">A main origin certificate</span></span>  
> ![主原始证书][ImageCertificate]  

### <span data-ttu-id="fc704-142">查看来源详细信息</span><span class="sxs-lookup"><span data-stu-id="fc704-142">View origin details</span></span>   

<span data-ttu-id="fc704-143">单击左侧导航栏中的其中一个条目以查看来源的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fc704-143">Click one of the entries in the left-hand nav to view the details of the origin.</span></span>  <span data-ttu-id="fc704-144">从 "详细信息" 页面，您可以查看连接和证书信息。</span><span class="sxs-lookup"><span data-stu-id="fc704-144">From the details page you are able to view connection and certificate information.</span></span>  <span data-ttu-id="fc704-145">还会显示证书透明信息（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="fc704-145">Certificate transparency information is also shown when available.</span></span>  

> ##### <span data-ttu-id="fc704-146">图 6</span><span class="sxs-lookup"><span data-stu-id="fc704-146">Figure 6</span></span>  
> <span data-ttu-id="fc704-147">主要来源详细信息</span><span class="sxs-lookup"><span data-stu-id="fc704-147">Main origin details</span></span>  
> ![主要来源详细信息][ImageOriginDetails]  

 



<!-- image links -->  

[ImageSecurityPanel]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-secure.msft.png "图1：安全面板"  
[ImageNonSecurePage]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-non-secure.msft.png "图2：不安全的页面"  
[ImageMixedContent]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-mixed-secure.msft.png "图3：混合内容"  
[ImageMixedResourcesNetworkLog]: /microsoft-edge/devtools-guide-chromium/media/security-network-filter.msft.png "图4：网络日志中的混合资源"  
[ImageCertificate]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-secure-view-certificate.msft.png "图5：主原始证书"  
[ImageOriginDetails]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-mixed-secure-main-origin.msft.png "图6：主原始详细信息"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  


[LetsEncrypt]: https://letsencrypt.org "我们的加密-免费的 SSL/TLS 证书"  

[Webhint]: https://webhint.io "webhint"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "使用 HTTPS |webhint 文档"  

<!--[mixed]: /web/fundamentals/security/prevent-mixed-content/what-is-mixed-content ""  -->

> [!NOTE]
> <span data-ttu-id="fc704-160">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="fc704-160">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fc704-161">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/security/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="fc704-161">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/security/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="fc704-163">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="fc704-163">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
