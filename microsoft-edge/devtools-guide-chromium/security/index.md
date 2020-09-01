---
title: 了解 Microsoft Edge DevTools 的安全问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 850dde157a673a84a3e603f22a5e54abd90bde5d
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984293"
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





# <span data-ttu-id="669b8-103">了解 Microsoft Edge DevTools 的安全问题</span><span class="sxs-lookup"><span data-stu-id="669b8-103">Understand security issues with Microsoft Edge DevTools</span></span>   

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  See **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <span data-ttu-id="669b8-104">打开 "安全" 面板</span><span class="sxs-lookup"><span data-stu-id="669b8-104">Open the Security panel</span></span>   

<span data-ttu-id="669b8-105">**安全**面板是检查页面安全性的 DevTools 中的主要位置。</span><span class="sxs-lookup"><span data-stu-id="669b8-105">The **Security** panel is the main place in DevTools for inspecting the security of a page.</span></span>  

1.  <span data-ttu-id="669b8-106">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="669b8-106">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="669b8-107">单击 " **安全** " 选项卡以打开 " **安全** " 面板。</span><span class="sxs-lookup"><span data-stu-id="669b8-107">Click the **Security** tab to open the **Security** panel.</span></span>  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-secure.msft.png":::
       <span data-ttu-id="669b8-109">**安全**面板</span><span class="sxs-lookup"><span data-stu-id="669b8-109">The **Security** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="669b8-110">常见问题</span><span class="sxs-lookup"><span data-stu-id="669b8-110">Common problems</span></span>   

### <span data-ttu-id="669b8-111">不安全的主要来源</span><span class="sxs-lookup"><span data-stu-id="669b8-111">Non-secure main origins</span></span>   

<span data-ttu-id="669b8-112">当页面的主来源不安全时， **安全概述** 显示 **此页面不安全**。</span><span class="sxs-lookup"><span data-stu-id="669b8-112">When the main origin of a page is not secure, the **Security Overview** says **This page is not secure**.</span></span>  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="非安全页面" lightbox="../media/security-security-overview-non-secure.msft.png":::
   <span data-ttu-id="669b8-114">非安全页面</span><span class="sxs-lookup"><span data-stu-id="669b8-114">A non-secure page</span></span>  
:::image-end:::  

<span data-ttu-id="669b8-115">当通过 HTTP 请求访问的 URL 时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="669b8-115">This problem occurs when the URL that you visited was requested over HTTP.</span></span>  <span data-ttu-id="669b8-116">若要使其安全，你需要通过 HTTPS 请求它。</span><span class="sxs-lookup"><span data-stu-id="669b8-116">To make it secure you need to request it over HTTPS.</span></span>  <span data-ttu-id="669b8-117">例如，如果你查看地址栏中的 URL，它可能看起来类似于 `http://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="669b8-117">For example, if you look at the URL in your address bar, it probably looks similar to `http://example.com`.</span></span>  <span data-ttu-id="669b8-118">若要使其安全，应显示 URL `https://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="669b8-118">To make it secure the URL should be `https://example.com`.</span></span>  

<span data-ttu-id="669b8-119">如果你已在服务器上设置了 HTTPS，则你需要执行以下操作来解决此问题：将你的服务器配置为将所有 HTTP 请求重定向到 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="669b8-119">If you already set up HTTPS on your server, all you need to do to fix this problem is configure your server to redirect all HTTP requests to HTTPS.</span></span>  

<span data-ttu-id="669b8-120">如果您没有在服务器上设置 HTTPS， [我们的加密][LetsEncrypt] 功能提供了一种免费且相对简单的启动过程的方式。</span><span class="sxs-lookup"><span data-stu-id="669b8-120">If you have not set up HTTPS on your server, [Let's Encrypt][LetsEncrypt] provides a free and relatively-easy way to start the process.</span></span>  <span data-ttu-id="669b8-121">或者，你可能会考虑在 CDN 上托管你的网站。</span><span class="sxs-lookup"><span data-stu-id="669b8-121">Or, you might consider hosting your site on a CDN.</span></span>  <span data-ttu-id="669b8-122">默认情况下，HTTPS 上最主要的 Cdn 主机站点。</span><span class="sxs-lookup"><span data-stu-id="669b8-122">Most major CDNs host sites on HTTPS by default now.</span></span>  

> [!TIP]
> <span data-ttu-id="669b8-123">[Webhint][Webhint]中的 "[使用 HTTPS][WebhintUseHttps] " 提示可帮助自动执行确保所有 HTTP 请求定向到 HTTPS 的过程。</span><span class="sxs-lookup"><span data-stu-id="669b8-123">The [Use HTTPS][WebhintUseHttps] hint in [webhint][Webhint] may help automate the process of making sure that all HTTP requests are directed to HTTPS.</span></span>  

### <span data-ttu-id="669b8-124">混合内容</span><span class="sxs-lookup"><span data-stu-id="669b8-124">Mixed content</span></span>   

<span data-ttu-id="669b8-125">**混合内容** 意味着页面的主原始位置是安全的，但是页面请求的资源来自不安全来源。</span><span class="sxs-lookup"><span data-stu-id="669b8-125">**Mixed content** means that the main origin of a page is secure, but the page requested resources from non-secure origins.</span></span>  <span data-ttu-id="669b8-126">混合内容页面只是部分受保护的，因为 HTTP 内容可以被嗅探者访问，并且容易受到中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="669b8-126">Mixed content pages are only partially protected because the HTTP content is accessible to sniffers and vulnerable to man-in-the-middle attacks.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="混合内容" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   <span data-ttu-id="669b8-128">混合内容</span><span class="sxs-lookup"><span data-stu-id="669b8-128">Mixed content</span></span>  
:::image-end:::  

<span data-ttu-id="669b8-129">在上图中，单击 " **在网络面板中查看1个请求** " 以打开 " **网络** " 面板并应用 `mixed-content:displayed` 筛选器，以便 **网络日志** 仅显示不安全的资源。</span><span class="sxs-lookup"><span data-stu-id="669b8-129">In the previous figure, click **View 1 request in Network panel** to open the **Network** panel and apply the `mixed-content:displayed` filter so that the **Network Log** only shows non-secure resources.</span></span>  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="网络日志中的混合资源" lightbox="../media/security-network-filter.msft.png":::
   <span data-ttu-id="669b8-131">**网络日志**中的混合资源</span><span class="sxs-lookup"><span data-stu-id="669b8-131">Mixed resources in the **Network Log**</span></span>  
:::image-end:::  

## <span data-ttu-id="669b8-132">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="669b8-132">View details</span></span>   

### <span data-ttu-id="669b8-133">查看主原始证书</span><span class="sxs-lookup"><span data-stu-id="669b8-133">View main origin certificate</span></span>   

<span data-ttu-id="669b8-134">从 **安全概述**中，单击 " **查看证书** " 以快速检查主源的证书。</span><span class="sxs-lookup"><span data-stu-id="669b8-134">From the **Security Overview**, click **View certificate** to quickly inspect the certificate for the main origin.</span></span>  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="主原始证书" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   <span data-ttu-id="669b8-136">主原始证书</span><span class="sxs-lookup"><span data-stu-id="669b8-136">A main origin certificate</span></span>  
:::image-end:::  

### <span data-ttu-id="669b8-137">查看来源详细信息</span><span class="sxs-lookup"><span data-stu-id="669b8-137">View origin details</span></span>   

<span data-ttu-id="669b8-138">单击左侧导航栏中的其中一个条目以查看来源的详细信息。</span><span class="sxs-lookup"><span data-stu-id="669b8-138">Click one of the entries in the left-hand nav to view the details of the origin.</span></span>  <span data-ttu-id="669b8-139">从 "详细信息" 页面，您可以查看连接和证书信息。</span><span class="sxs-lookup"><span data-stu-id="669b8-139">From the details page you are able to view connection and certificate information.</span></span>  <span data-ttu-id="669b8-140">还会显示证书透明信息（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="669b8-140">Certificate transparency information is also shown when available.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="主要来源详细信息" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   <span data-ttu-id="669b8-142">主要来源详细信息</span><span class="sxs-lookup"><span data-stu-id="669b8-142">Main origin details</span></span>  
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
> <span data-ttu-id="669b8-148">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="669b8-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="669b8-149">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/security/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="669b8-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/security/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="669b8-151">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="669b8-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
