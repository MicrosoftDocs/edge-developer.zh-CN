---
description: 了解如何使用 Microsoft Edge DevTools 查看、编辑和删除页面的 HTTP Cookie。
title: 使用 Microsoft Edge DevTools 查看、编辑和删除 Cookie
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: c208ca628fe91ed5922bc36566be2b9bdd20ec0b
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439680"
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

# <a name="view-edit-and-delete-cookies-with-microsoft-edge-devtools"></a><span data-ttu-id="f38d7-104">使用 Microsoft Edge DevTools 查看、编辑和删除 Cookie</span><span class="sxs-lookup"><span data-stu-id="f38d7-104">View, edit, and delete cookies with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f38d7-105">[HTTP Cookie][MDNHTTPCookies] 主要用于管理用户会话、存储用户个性化首选项和跟踪用户行为。</span><span class="sxs-lookup"><span data-stu-id="f38d7-105">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span></span>  <span data-ttu-id="f38d7-106">Cookie 也是导致各种网页上出现麻烦的 **此页面使用 Cookie** 许可表单的源头。</span><span class="sxs-lookup"><span data-stu-id="f38d7-106">Cookies are also the cause of all of the annoying **this page uses cookies** consent forms that are found across the web.</span></span>  <span data-ttu-id="f38d7-107">以下指南将指导你如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除网页的 HTTP Cookie。</span><span class="sxs-lookup"><span data-stu-id="f38d7-107">The following guide teaches you how to view, edit, and delete the HTTP cookies for a webpage with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="open-the-cookies-pane"></a><span data-ttu-id="f38d7-108">打开“Cookie”窗格</span><span class="sxs-lookup"><span data-stu-id="f38d7-108">Open the Cookies pane</span></span>  

1.  <span data-ttu-id="f38d7-109">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="f38d7-109">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="f38d7-110">选择“**应用程序**”选项卡以打开“**应用程序**”面板。</span><span class="sxs-lookup"><span data-stu-id="f38d7-110">Choose the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="f38d7-111">“**清单**”窗格应打开。</span><span class="sxs-lookup"><span data-stu-id="f38d7-111">The **Manifest** pane should open.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="f38d7-113">图 1：清单窗格</span><span class="sxs-lookup"><span data-stu-id="f38d7-113">Figure 1:  The Manifest pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="f38d7-114">在“**存储**“下，展开 “**Cookie**”，然后选择一个源。</span><span class="sxs-lookup"><span data-stu-id="f38d7-114">Under **Storage** expand **Cookies**, then select an origin.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-cookies-selected.msft.png" alt-text="“Cookie”窗格" lightbox="../media/storage-application-storage-cookies-selected.msft.png":::
       <span data-ttu-id="f38d7-116">图 2：“Cookie” 窗格</span><span class="sxs-lookup"><span data-stu-id="f38d7-116">Figure 2:  The Cookies pane</span></span>  
    :::image-end:::  

## <a name="fields"></a><span data-ttu-id="f38d7-117">字段</span><span class="sxs-lookup"><span data-stu-id="f38d7-117">Fields</span></span>  

<span data-ttu-id="f38d7-118">**Cookies** 表包含以下字段。</span><span class="sxs-lookup"><span data-stu-id="f38d7-118">The **Cookies** table contains the following fields.</span></span>  

*   <span data-ttu-id="f38d7-119">**名称**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-119">**Name**.</span></span>  <span data-ttu-id="f38d7-120">Cookie 的名称。</span><span class="sxs-lookup"><span data-stu-id="f38d7-120">The name of the cookie.</span></span>  
*   <span data-ttu-id="f38d7-121">**值**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-121">**Value**.</span></span>  <span data-ttu-id="f38d7-122">Cookie 的值。</span><span class="sxs-lookup"><span data-stu-id="f38d7-122">The value of the cookie.</span></span>  
*   <span data-ttu-id="f38d7-123">**域**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-123">**Domain**.</span></span>  <span data-ttu-id="f38d7-124">允许接收 Cookie 的主机。</span><span class="sxs-lookup"><span data-stu-id="f38d7-124">The hosts that are allowed to receive the cookie.</span></span>  <span data-ttu-id="f38d7-125">导航到 [Cookie 的范围][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="f38d7-125">Navigate to [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="f38d7-126">**路径**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-126">**Path**.</span></span>  <span data-ttu-id="f38d7-127">URL 必须存在于请求的 URL 中以发送 `Cookie` 标头。</span><span class="sxs-lookup"><span data-stu-id="f38d7-127">The URL that must exist in the requested URL in order to send the `Cookie` header.</span></span>  <span data-ttu-id="f38d7-128">导航到 [Cookie 的范围][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="f38d7-128">Navigate to [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="f38d7-129">**到期日期/最长期限**.</span><span class="sxs-lookup"><span data-stu-id="f38d7-129">**Expires / Max-Age**.</span></span>  <span data-ttu-id="f38d7-130">Cookie 的到期日期或最长期限。</span><span class="sxs-lookup"><span data-stu-id="f38d7-130">The expiration date or maximum age of the cookie.</span></span>  <span data-ttu-id="f38d7-131">导航到“[永久 Cookie][MDNHTTPCookiesPermanent]。</span><span class="sxs-lookup"><span data-stu-id="f38d7-131">Navigate to [Permanent cookies][MDNHTTPCookiesPermanent].</span></span>  <span data-ttu-id="f38d7-132">对于[会话 Cookie][MDNHTTPCookiesSession]，此值始终为 `Session`。</span><span class="sxs-lookup"><span data-stu-id="f38d7-132">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span></span>  
*   <span data-ttu-id="f38d7-133">**大小**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-133">**Size**.</span></span>  <span data-ttu-id="f38d7-134">Cookie 的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f38d7-134">The size, in bytes, of the cookie.</span></span>  
*   <span data-ttu-id="f38d7-135">**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-135">**HTTP**.</span></span>  <span data-ttu-id="f38d7-136">如果为 true，则此字段指示应仅通过 HTTP 使用 Cookie，不允许 JavaScript 修改。</span><span class="sxs-lookup"><span data-stu-id="f38d7-136">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span></span>  <span data-ttu-id="f38d7-137">导航到 [HttpOnly Cookie][MDNHTTPCookiesSecure]。</span><span class="sxs-lookup"><span data-stu-id="f38d7-137">Navigate to [HttpOnly cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="f38d7-138">**安全**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-138">**Secure**.</span></span>  <span data-ttu-id="f38d7-139">如果为 true，则此字段指示必须通过安全的 HTTPS 连接将 Cookie 发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="f38d7-139">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span></span>  <span data-ttu-id="f38d7-140">导航到“[安全 Cookie][MDNHTTPCookiesSecure]”。</span><span class="sxs-lookup"><span data-stu-id="f38d7-140">Navigate to [Secure cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="f38d7-141">**SameSite**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-141">**SameSite**.</span></span>  <span data-ttu-id="f38d7-142">包含 `strict`，当 Cookie 使用实验性 [Samesite][MDNHTTPCookiesSamesite] 属性时包含 `lax`。</span><span class="sxs-lookup"><span data-stu-id="f38d7-142">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span></span>  
*   <span data-ttu-id="f38d7-143">**优先级**。</span><span class="sxs-lookup"><span data-stu-id="f38d7-143">**Priority**.</span></span>  <span data-ttu-id="f38d7-144">包含 `low`、`medium` \(default\)，当 Cookie 使用已弃用的 [Cookie Priority][ChromiumIssue232693] 属性时包含 `high`。</span><span class="sxs-lookup"><span data-stu-id="f38d7-144">Contains `low`, `medium` \(default\), or `high` if the cookie is using the deprecated [cookie Priority][ChromiumIssue232693] attribute.</span></span>

## <a name="filter-cookies"></a><span data-ttu-id="f38d7-145">筛选 Cookie</span><span class="sxs-lookup"><span data-stu-id="f38d7-145">Filter cookies</span></span>  

<span data-ttu-id="f38d7-146">使用“**筛选器**”文本框按**名称**或**值**筛选 Cookie。</span><span class="sxs-lookup"><span data-stu-id="f38d7-146">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span></span>  <span data-ttu-id="f38d7-147">不支持按其他字段筛选。</span><span class="sxs-lookup"><span data-stu-id="f38d7-147">Filtering by other fields is not supported.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-filter-id.msft.png" alt-text="筛选出任何不包含文本 ID 的 Cookie" lightbox="../media/storage-application-storage-cookies-filter-id.msft.png":::
   <span data-ttu-id="f38d7-149">图 3：筛选出任何不包含文本的 Cookie</span><span class="sxs-lookup"><span data-stu-id="f38d7-149">Figure 3:  Filtering out any cookies that do not contain the text</span></span> `ID`  
:::image-end:::  

## <a name="edit-a-cookie"></a><span data-ttu-id="f38d7-150">编辑 Cookie</span><span class="sxs-lookup"><span data-stu-id="f38d7-150">Edit a cookie</span></span>  

<span data-ttu-id="f38d7-151">**名称**、**值**、**域**、**路径**和**过期日期/最长期限**字段是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="f38d7-151">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span></span>  
<span data-ttu-id="f38d7-152">双击某个字段进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f38d7-152">Double-click a field to edit it.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-rename.msft.png" alt-text="将 Cookie 的名称设置为 DEVTOOLS！" lightbox="../media/storage-application-storage-cookies-rename.msft.png":::
   <span data-ttu-id="f38d7-154">图 4：将 Cookie 的名称设置为</span><span class="sxs-lookup"><span data-stu-id="f38d7-154">Figure 4:  Setting the name of a cookie to</span></span> `DEVTOOLS!`  
:::image-end:::  

## <a name="delete-cookies"></a><span data-ttu-id="f38d7-155">删除 Cookie</span><span class="sxs-lookup"><span data-stu-id="f38d7-155">Delete cookies</span></span>  

<span data-ttu-id="f38d7-156">选择一个 Cookie 然后选择“**删除选中项** (![删除选中项](../media/delete-icon.msft.png)\)” 来删除某个 Cookie。</span><span class="sxs-lookup"><span data-stu-id="f38d7-156">Choose a cookie and choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\) to delete the specific cookie.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-delete-selected.msft.png" alt-text="删除特定 Cookie" lightbox="../media/storage-application-storage-cookies-delete-selected.msft.png":::
   <span data-ttu-id="f38d7-158">图 5：删除特定 Cookie</span><span class="sxs-lookup"><span data-stu-id="f38d7-158">Figure 5:  Deleting a specific cookie</span></span>  
:::image-end:::  

<span data-ttu-id="f38d7-159">选择“**清除所有** (![清除所有](../media/clear-icon.msft.png)\)” 来删除所有 Cookie。</span><span class="sxs-lookup"><span data-stu-id="f38d7-159">Choose **Clear All** \(![Clear All](../media/clear-icon.msft.png)\) to delete all cookies.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-clear-all.msft.png" alt-text="清除所有 Cookie" lightbox="../media/storage-application-storage-cookies-clear-all.msft.png":::
   <span data-ttu-id="f38d7-161">图 6：清除所有 Cookie</span><span class="sxs-lookup"><span data-stu-id="f38d7-161">Figure 6:  Clearing all cookies</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f38d7-162">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="f38d7-162">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  

[ChromiumIssue232693]: https://bugs.chromium.org/p/chromium/issues/detail?id=232693 "Chromium 问题 232693：实现 Cookie 优先字段 | Chromium Bug"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookie | MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP Cookie - 永久 cookie | MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP Cookie - SameSite cookie | MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP Cookie - Cookie | MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP Cookie - 安全和 HttpOnly Cookie | MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP Cookie - 会话 cookie | MDN"  

> [!NOTE]
> <span data-ttu-id="f38d7-172">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f38d7-172">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f38d7-173">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f38d7-173">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f38d7-175">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f38d7-175">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
