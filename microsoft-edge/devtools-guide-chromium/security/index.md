---
description: 使用安全面板确保页面受到 HTTPS 的完全保护。
title: 了解开发人员工具Microsoft Edge安全问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 2e6aab865319e6ed7d108cddb77432f293153995
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565034"
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
# <a name="understand-security-issues-with-microsoft-edge-devtools"></a><span data-ttu-id="8521a-104">了解开发人员工具Microsoft Edge安全问题</span><span class="sxs-lookup"><span data-stu-id="8521a-104">Understand security issues with Microsoft Edge DevTools</span></span>  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  Navigate to **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <a name="open-the-security-panel"></a><span data-ttu-id="8521a-105">打开"安全"面板</span><span class="sxs-lookup"><span data-stu-id="8521a-105">Open the Security panel</span></span>  

<span data-ttu-id="8521a-106">安全 **面板** 是 DevTools 中用于检查页面安全性的主要位置。</span><span class="sxs-lookup"><span data-stu-id="8521a-106">The **Security** panel is the main place in DevTools for inspecting the security of a page.</span></span>  

1.  <span data-ttu-id="8521a-107">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="8521a-107">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="8521a-108">选择" **安全"** 选项卡以打开 **"安全"** 工具。</span><span class="sxs-lookup"><span data-stu-id="8521a-108">Choose the **Security** tab to open the **Security** tool.</span></span>  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="安全面板" lightbox="../media/security-security-overview-secure.msft.png":::
       <span data-ttu-id="8521a-110">安全**面板**</span><span class="sxs-lookup"><span data-stu-id="8521a-110">The **Security** panel</span></span>  
    :::image-end:::  
    
## <a name="common-problems"></a><span data-ttu-id="8521a-111">常见问题</span><span class="sxs-lookup"><span data-stu-id="8521a-111">Common problems</span></span>  

### <a name="non-secure-main-origins"></a><span data-ttu-id="8521a-112">非安全主源</span><span class="sxs-lookup"><span data-stu-id="8521a-112">Non-secure main origins</span></span>  

<span data-ttu-id="8521a-113">当页面的主源不安全时，安全概述指出**此页面不安全**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8521a-113">When the main origin of a page is not secure, the **Security Overview** says **This page is not secure**.</span></span>  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="非安全页面" lightbox="../media/security-security-overview-non-secure.msft.png":::
   <span data-ttu-id="8521a-115">非安全页面</span><span class="sxs-lookup"><span data-stu-id="8521a-115">A non-secure page</span></span>  
:::image-end:::  

<span data-ttu-id="8521a-116">当您访问的 URL 通过 HTTP 请求时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="8521a-116">This problem occurs when the URL that you visited was requested over HTTP.</span></span>  <span data-ttu-id="8521a-117">若要确保安全，您需要通过 HTTPS 请求它。</span><span class="sxs-lookup"><span data-stu-id="8521a-117">To make it secure you need to request it over HTTPS.</span></span>  <span data-ttu-id="8521a-118">例如，如果您查看地址栏中的 URL，它可能类似于 `http://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="8521a-118">For example, if you look at the URL in your address bar, it probably looks similar to `http://example.com`.</span></span>  <span data-ttu-id="8521a-119">若要确保 URL 安全，URL 应为 `https://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="8521a-119">To make it secure the URL should be `https://example.com`.</span></span>  

<span data-ttu-id="8521a-120">如果已在服务器上设置 HTTPS，则解决此问题只需将服务器配置为将所有 HTTP 请求重定向到 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="8521a-120">If you already set up HTTPS on your server, all you need to do to fix this problem is configure your server to redirect all HTTP requests to HTTPS.</span></span>  

<span data-ttu-id="8521a-121">如果您尚未在服务器上设置 HTTPS，Let's [Encrypt][LetsEncrypt] 提供了一种免费且相对简单的启动过程的方法。</span><span class="sxs-lookup"><span data-stu-id="8521a-121">If you have not set up HTTPS on your server, [Let's Encrypt][LetsEncrypt] provides a free and relatively-easy way to start the process.</span></span>  <span data-ttu-id="8521a-122">或者，你可以考虑将网站托管在CDN。</span><span class="sxs-lookup"><span data-stu-id="8521a-122">Or, you may consider hosting your site on a CDN.</span></span>  <span data-ttu-id="8521a-123">默认情况下，HTTPS 上的大多数主要 CDN 都承载网站。</span><span class="sxs-lookup"><span data-stu-id="8521a-123">Most major CDNs host sites on HTTPS by default now.</span></span>  

> [!TIP]
> <span data-ttu-id="8521a-124">[Webhint][Webhint]中的"使用[HTTPS"][WebhintUseHttps]提示可帮助自动执行确保所有 HTTP 请求都定向到 HTTPS 的过程。</span><span class="sxs-lookup"><span data-stu-id="8521a-124">The [Use HTTPS][WebhintUseHttps] hint in [webhint][Webhint] may help automate the process of making sure that all HTTP requests are directed to HTTPS.</span></span>  

### <a name="mixed-content"></a><span data-ttu-id="8521a-125">混合内容</span><span class="sxs-lookup"><span data-stu-id="8521a-125">Mixed content</span></span>  

<span data-ttu-id="8521a-126">**混合** 内容意味着页面的主源是安全的，但页面从非安全源请求资源。</span><span class="sxs-lookup"><span data-stu-id="8521a-126">**Mixed content** means that the main origin of a page is secure, but the page requested resources from non-secure origins.</span></span>  <span data-ttu-id="8521a-127">混合内容页仅部分受保护，因为探查器可以访问 HTTP 内容，并且易受中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="8521a-127">Mixed content pages are only partially protected because the HTTP content is accessible to sniffers and vulnerable to man-in-the-middle attacks.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="混合内容" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   <span data-ttu-id="8521a-129">混合内容</span><span class="sxs-lookup"><span data-stu-id="8521a-129">Mixed content</span></span>  
:::image-end:::  

<span data-ttu-id="8521a-130">在上图中，选择"网络"面板中的"**查看 1**请求"以打开 **"** 网络"工具并应用筛选器，以便"网络日志"只显示 `mixed-content:displayed` 非安全资源。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8521a-130">In the previous figure, choose **View 1 request in Network panel** to open the **Network** tool and apply the `mixed-content:displayed` filter so that the **Network Log** only shows non-secure resources.</span></span>  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="网络日志中的混合资源" lightbox="../media/security-network-filter.msft.png":::
   <span data-ttu-id="8521a-132">网络日志中的 **混合资源**</span><span class="sxs-lookup"><span data-stu-id="8521a-132">Mixed resources in the **Network Log**</span></span>  
:::image-end:::  

## <a name="view-details"></a><span data-ttu-id="8521a-133">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="8521a-133">View details</span></span>  

### <a name="view-main-origin-certificate"></a><span data-ttu-id="8521a-134">查看主源证书</span><span class="sxs-lookup"><span data-stu-id="8521a-134">View main origin certificate</span></span>  

<span data-ttu-id="8521a-135">从" **安全概述"** 中， **选择"查看** 证书"以快速检查证书的主来源。</span><span class="sxs-lookup"><span data-stu-id="8521a-135">From the **Security Overview**, choose **View certificate** to quickly inspect the certificate for the main origin.</span></span>  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="主源证书" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   <span data-ttu-id="8521a-137">主源证书</span><span class="sxs-lookup"><span data-stu-id="8521a-137">A main origin certificate</span></span>  
:::image-end:::  

### <a name="view-origin-details"></a><span data-ttu-id="8521a-138">查看源详细信息</span><span class="sxs-lookup"><span data-stu-id="8521a-138">View origin details</span></span>  

<span data-ttu-id="8521a-139">选择左侧导航中的条目之一以查看源的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8521a-139">Choose one of the entries in the left-hand nav to view the details of the origin.</span></span>  <span data-ttu-id="8521a-140">在详细信息页中，可以查看连接和证书信息。</span><span class="sxs-lookup"><span data-stu-id="8521a-140">From the details page you are able to view connection and certificate information.</span></span>  <span data-ttu-id="8521a-141">证书透明度信息还会在可用时显示。</span><span class="sxs-lookup"><span data-stu-id="8521a-141">Certificate transparency information is also shown when available.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="主源详细信息" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   <span data-ttu-id="8521a-143">主源详细信息</span><span class="sxs-lookup"><span data-stu-id="8521a-143">Main origin details</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="8521a-144">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="8521a-144">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevToolsOpen]: ../open/index.md "打开 Microsoft Edge 开发人员工具 | Microsoft Docs"  

[LetsEncrypt]: https://letsencrypt.org "让我们进行加密 - 免费 SSL/TLS 证书"  

[Webhint]: https://webhint.io "webhint"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "使用 HTTPS |webhint 文档"  

<!--[mixed]: /web/fundamentals/security/prevent-mixed-content/what-is-mixed-content ""  -->

> [!NOTE]
> <span data-ttu-id="8521a-150">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8521a-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8521a-151">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/security/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="8521a-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/security/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8521a-153">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8521a-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
