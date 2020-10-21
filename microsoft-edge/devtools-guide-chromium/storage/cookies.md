---
description: 了解如何使用 Microsoft Edge DevTools 查看、编辑和删除页面的 HTTP cookie。
title: 查看、编辑和删除 Microsoft Edge DevTools 中的 Cookie
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 328771aa254dac1f851535a44126ea220dc95a9c
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125480"
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

# <span data-ttu-id="75ee4-104">查看、编辑和删除 Microsoft Edge DevTools 中的 cookie</span><span class="sxs-lookup"><span data-stu-id="75ee4-104">View, edit, and delete cookies with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="75ee4-105">[HTTP cookie][MDNHTTPCookies] 主要用于管理用户会话、存储用户个性化首选项和跟踪用户行为。</span><span class="sxs-lookup"><span data-stu-id="75ee4-105">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span></span>  <span data-ttu-id="75ee4-106">Cookie 也是由您在 web 上看到的所有令人讨厌的 "此页面使用 cookies" 同意表单的原因。</span><span class="sxs-lookup"><span data-stu-id="75ee4-106">Cookies are also the cause of all of the annoying "this page uses cookies" consent forms that you see across the web.</span></span>  <span data-ttu-id="75ee4-107">以下指南教你如何查看、编辑和删除具有 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]的页面的 HTTP cookie。</span><span class="sxs-lookup"><span data-stu-id="75ee4-107">The following guide teaches you how to view, edit, and delete the HTTP cookies for a page with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="75ee4-108">打开 "Cookie" 窗格</span><span class="sxs-lookup"><span data-stu-id="75ee4-108">Open the Cookies pane</span></span>  

1.  <span data-ttu-id="75ee4-109">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="75ee4-109">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="75ee4-110">选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="75ee4-110">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="75ee4-111">将打开 " **清单** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="75ee4-111">The **Manifest** pane should open.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="75ee4-113">图1：清单窗格</span><span class="sxs-lookup"><span data-stu-id="75ee4-113">Figure 1:  The Manifest pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="75ee4-114">在 " **存储** " 下展开 " **cookie**"，然后选择一个原点。</span><span class="sxs-lookup"><span data-stu-id="75ee4-114">Under **Storage** expand **Cookies**, then select an origin.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-cookies-selected.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-cookies-selected.msft.png":::
       <span data-ttu-id="75ee4-116">图2： "Cookie" 窗格</span><span class="sxs-lookup"><span data-stu-id="75ee4-116">Figure 2:  The Cookies pane</span></span>  
    :::image-end:::  

## <span data-ttu-id="75ee4-117">字段</span><span class="sxs-lookup"><span data-stu-id="75ee4-117">Fields</span></span>  

<span data-ttu-id="75ee4-118">**Cookies**表包含以下字段。</span><span class="sxs-lookup"><span data-stu-id="75ee4-118">The **Cookies** table contains the following fields.</span></span>  

*   <span data-ttu-id="75ee4-119">**名称**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-119">**Name**.</span></span>  <span data-ttu-id="75ee4-120">Cookie 的名称。</span><span class="sxs-lookup"><span data-stu-id="75ee4-120">The name of the cookie.</span></span>  
*   <span data-ttu-id="75ee4-121">**值**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-121">**Value**.</span></span>  <span data-ttu-id="75ee4-122">Cookie 的值。</span><span class="sxs-lookup"><span data-stu-id="75ee4-122">The value of the cookie.</span></span>  
*   <span data-ttu-id="75ee4-123">**域**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-123">**Domain**.</span></span>  <span data-ttu-id="75ee4-124">允许接收该 cookie 的主机。</span><span class="sxs-lookup"><span data-stu-id="75ee4-124">The hosts that are allowed to receive the cookie.</span></span>  <span data-ttu-id="75ee4-125">请参阅 [Cookie 范围][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="75ee4-125">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="75ee4-126">**路径**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-126">**Path**.</span></span>  <span data-ttu-id="75ee4-127">必须存在于请求的 URL 中才能发送页眉的 URL `Cookie` 。</span><span class="sxs-lookup"><span data-stu-id="75ee4-127">The URL that must exist in the requested URL in order to send the `Cookie` header.</span></span>  <span data-ttu-id="75ee4-128">请参阅 [Cookie 范围][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="75ee4-128">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="75ee4-129">**过期/最大存留期**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-129">**Expires / Max-Age**.</span></span>  <span data-ttu-id="75ee4-130">Cookie 的到期日期或最长期限。</span><span class="sxs-lookup"><span data-stu-id="75ee4-130">The expiration date or maximum age of the cookie.</span></span>  <span data-ttu-id="75ee4-131">请参阅 [永久 cookie][MDNHTTPCookiesPermanent]。</span><span class="sxs-lookup"><span data-stu-id="75ee4-131">See [Permanent cookies][MDNHTTPCookiesPermanent].</span></span>  <span data-ttu-id="75ee4-132">对于 [会话 cookie][MDNHTTPCookiesSession] ，此值始终为 `Session` 。</span><span class="sxs-lookup"><span data-stu-id="75ee4-132">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span></span>  
*   <span data-ttu-id="75ee4-133">**大小**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-133">**Size**.</span></span>  <span data-ttu-id="75ee4-134">Cookie 的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="75ee4-134">The size, in bytes, of the cookie.</span></span>  
*   <span data-ttu-id="75ee4-135">**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-135">**HTTP**.</span></span>  <span data-ttu-id="75ee4-136">如果为 true，则此字段指示应仅通过 HTTP 使用该 cookie，并且不允许 JavaScript 修改。</span><span class="sxs-lookup"><span data-stu-id="75ee4-136">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span></span>  <span data-ttu-id="75ee4-137">请参阅 [HttpOnly cookie][MDNHTTPCookiesSecure]。</span><span class="sxs-lookup"><span data-stu-id="75ee4-137">See [HttpOnly cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="75ee4-138">**安全**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-138">**Secure**.</span></span>  <span data-ttu-id="75ee4-139">如果为 true，则此字段指示该 cookie 必须仅通过安全的 HTTPS 连接发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="75ee4-139">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span></span>  <span data-ttu-id="75ee4-140">请参阅 [安全 cookie][MDNHTTPCookiesSecure]。</span><span class="sxs-lookup"><span data-stu-id="75ee4-140">See [Secure cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="75ee4-141">**SameSite**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-141">**SameSite**.</span></span>  <span data-ttu-id="75ee4-142">包含 `strict` 或 `lax` 如果 cookie 使用实验性的 [Samesite][MDNHTTPCookiesSamesite] 属性。</span><span class="sxs-lookup"><span data-stu-id="75ee4-142">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span></span>  
*   <span data-ttu-id="75ee4-143">**优先级**。</span><span class="sxs-lookup"><span data-stu-id="75ee4-143">**Priority**.</span></span>  <span data-ttu-id="75ee4-144">包含 `low` ， `medium` \ (默认 \ ) ，或者 `high` cookie 使用的是已否决的 [cookie 优先级][ChromiumIssue232693] 属性。</span><span class="sxs-lookup"><span data-stu-id="75ee4-144">Contains `low`, `medium` \(default\), or `high` if the cookie is using the deprecated [cookie Priority][ChromiumIssue232693] attribute.</span></span>

## <span data-ttu-id="75ee4-145">筛选 cookie</span><span class="sxs-lookup"><span data-stu-id="75ee4-145">Filter cookies</span></span>  

<span data-ttu-id="75ee4-146">使用 " **筛选** " 文本框按 **名称** 或 **值**筛选 cookie。</span><span class="sxs-lookup"><span data-stu-id="75ee4-146">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span></span>  <span data-ttu-id="75ee4-147">不支持按其他字段进行筛选。</span><span class="sxs-lookup"><span data-stu-id="75ee4-147">Filtering by other fields is not supported.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-filter-id.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-cookies-filter-id.msft.png":::
   <span data-ttu-id="75ee4-149">图3：筛选出不包含文本的任何 cookie</span><span class="sxs-lookup"><span data-stu-id="75ee4-149">Figure 3:  Filtering out any cookies that do not contain the text</span></span> `ID`  
:::image-end:::  

## <span data-ttu-id="75ee4-150">编辑 cookie</span><span class="sxs-lookup"><span data-stu-id="75ee4-150">Edit a cookie</span></span>  

<span data-ttu-id="75ee4-151">" **名称**"、" **值**"、" **域**"、" **路径**" 和 "有效期" **/"最大年龄** " 域可编辑</span><span class="sxs-lookup"><span data-stu-id="75ee4-151">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span></span>  
<span data-ttu-id="75ee4-152">双击字段以对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="75ee4-152">Double-click a field to edit it.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-rename.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-cookies-rename.msft.png":::
   <span data-ttu-id="75ee4-154">图4：将 cookie 的名称设置为</span><span class="sxs-lookup"><span data-stu-id="75ee4-154">Figure 4:  Setting the name of a cookie to</span></span> `DEVTOOLS!`  
:::image-end:::  

## <span data-ttu-id="75ee4-155">删除 Cookie</span><span class="sxs-lookup"><span data-stu-id="75ee4-155">Delete cookies</span></span>  

<span data-ttu-id="75ee4-156">选择一个 cookie，然后选择 " **删除**所选 ![ 删除" ][ImageDeleteIcon]  以删除特定的 cookie。</span><span class="sxs-lookup"><span data-stu-id="75ee4-156">Select a cookie and choose **Delete Selected** ![Delete Selected][ImageDeleteIcon]  to delete the specific cookie.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-delete-selected.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-cookies-delete-selected.msft.png":::
   <span data-ttu-id="75ee4-158">图5：删除特定的 cookie</span><span class="sxs-lookup"><span data-stu-id="75ee4-158">Figure 5:  Deleting a specific cookie</span></span>  
:::image-end:::  

<span data-ttu-id="75ee4-159">选择 " **清除**全部 ![ 清除" ][ImageClearIcon]  以删除所有 cookie。</span><span class="sxs-lookup"><span data-stu-id="75ee4-159">Choose **Clear All** ![Clear All][ImageClearIcon]  to delete all cookies.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-clear-all.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-cookies-clear-all.msft.png":::
   <span data-ttu-id="75ee4-161">图6：清除所有 cookie</span><span class="sxs-lookup"><span data-stu-id="75ee4-161">Figure 6:  Clearing all cookies</span></span>  
:::image-end:::  

## <span data-ttu-id="75ee4-162">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="75ee4-162">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  

[ChromiumIssue232693]: https://bugs.chromium.org/p/chromium/issues/detail?id=232693 "Chromium 问题232693：为 Cookies 实施优先级字段 |Chromium Bug"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookie |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP cookie-永久 cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP cookie-SameSite cookie |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie-cookie 范围 |MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP cookie-安全和 HttpOnly cookie |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP cookie-会话 cookie |MDN"  

> [!NOTE]
> <span data-ttu-id="75ee4-172">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="75ee4-172">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="75ee4-173">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="75ee4-173">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="75ee4-175">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="75ee4-175">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
