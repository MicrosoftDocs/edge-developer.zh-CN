---
description: Learn how to view, edit, and delete the HTTP cookies for a page using Microsoft Edge DevTools.
title: View, Edit, And Delete Cookies With Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: eaaf4663504fc674fd70dc1ca9e0357febb529e0
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993238"
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

# <span data-ttu-id="a83a4-104">View, edit, and delete cookies with Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="a83a4-104">View, edit, and delete cookies with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="a83a4-105">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span><span class="sxs-lookup"><span data-stu-id="a83a4-105">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span></span>  <span data-ttu-id="a83a4-106">Cookies are also the cause of all of the annoying "this page uses cookies" consent forms that you see across the web.</span><span class="sxs-lookup"><span data-stu-id="a83a4-106">Cookies are also the cause of all of the annoying "this page uses cookies" consent forms that you see across the web.</span></span>  <span data-ttu-id="a83a4-107">The following guide teaches you how to view, edit, and delete the HTTP cookies for a page with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span><span class="sxs-lookup"><span data-stu-id="a83a4-107">The following guide teaches you how to view, edit, and delete the HTTP cookies for a page with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="a83a4-108">Open the Cookies pane</span><span class="sxs-lookup"><span data-stu-id="a83a4-108">Open the Cookies pane</span></span>  

1.  <span data-ttu-id="a83a4-109">[Open DevTools][DevToolsOpen].</span><span class="sxs-lookup"><span data-stu-id="a83a4-109">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="a83a4-110">Select the **Application** tab to open the **Application** panel.</span><span class="sxs-lookup"><span data-stu-id="a83a4-110">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="a83a4-111">The **Manifest** pane should open.</span><span class="sxs-lookup"><span data-stu-id="a83a4-111">The **Manifest** pane should open.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="a83a4-113">Figure 1:  The Manifest pane</span><span class="sxs-lookup"><span data-stu-id="a83a4-113">Figure 1:  The Manifest pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="a83a4-114">Under **Storage** expand **Cookies**, then select an origin.</span><span class="sxs-lookup"><span data-stu-id="a83a4-114">Under **Storage** expand **Cookies**, then select an origin.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-cookies-selected.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-cookies-selected.msft.png":::
       <span data-ttu-id="a83a4-116">Figure 2:  The Cookies pane</span><span class="sxs-lookup"><span data-stu-id="a83a4-116">Figure 2:  The Cookies pane</span></span>  
    :::image-end:::  

## <span data-ttu-id="a83a4-117">Fields</span><span class="sxs-lookup"><span data-stu-id="a83a4-117">Fields</span></span>  

<span data-ttu-id="a83a4-118">The **Cookies** table contains the following fields.</span><span class="sxs-lookup"><span data-stu-id="a83a4-118">The **Cookies** table contains the following fields.</span></span>  

*   <span data-ttu-id="a83a4-119">**Name**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-119">**Name**.</span></span>  <span data-ttu-id="a83a4-120">The name of the cookie.</span><span class="sxs-lookup"><span data-stu-id="a83a4-120">The name of the cookie.</span></span>  
*   <span data-ttu-id="a83a4-121">**Value**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-121">**Value**.</span></span>  <span data-ttu-id="a83a4-122">The value of the cookie.</span><span class="sxs-lookup"><span data-stu-id="a83a4-122">The value of the cookie.</span></span>  
*   <span data-ttu-id="a83a4-123">**Domain**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-123">**Domain**.</span></span>  <span data-ttu-id="a83a4-124">The hosts that are allowed to receive the cookie.</span><span class="sxs-lookup"><span data-stu-id="a83a4-124">The hosts that are allowed to receive the cookie.</span></span>  <span data-ttu-id="a83a4-125">See [Scope of cookies][MDNHTTPCookiesScope].</span><span class="sxs-lookup"><span data-stu-id="a83a4-125">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="a83a4-126">**Path**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-126">**Path**.</span></span>  <span data-ttu-id="a83a4-127">The URL that must exist in the requested URL in order to send the `Cookie` header.</span><span class="sxs-lookup"><span data-stu-id="a83a4-127">The URL that must exist in the requested URL in order to send the `Cookie` header.</span></span>  <span data-ttu-id="a83a4-128">See [Scope of cookies][MDNHTTPCookiesScope].</span><span class="sxs-lookup"><span data-stu-id="a83a4-128">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="a83a4-129">**Expires / Max-Age**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-129">**Expires / Max-Age**.</span></span>  <span data-ttu-id="a83a4-130">The expiration date or maximum age of the cookie.</span><span class="sxs-lookup"><span data-stu-id="a83a4-130">The expiration date or maximum age of the cookie.</span></span>  <span data-ttu-id="a83a4-131">See [Permanent cookies][MDNHTTPCookiesPermanent].</span><span class="sxs-lookup"><span data-stu-id="a83a4-131">See [Permanent cookies][MDNHTTPCookiesPermanent].</span></span>  <span data-ttu-id="a83a4-132">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span><span class="sxs-lookup"><span data-stu-id="a83a4-132">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span></span>  
*   <span data-ttu-id="a83a4-133">**Size**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-133">**Size**.</span></span>  <span data-ttu-id="a83a4-134">The size, in bytes, of the cookie.</span><span class="sxs-lookup"><span data-stu-id="a83a4-134">The size, in bytes, of the cookie.</span></span>  
*   <span data-ttu-id="a83a4-135">**HTTP**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-135">**HTTP**.</span></span>  <span data-ttu-id="a83a4-136">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span><span class="sxs-lookup"><span data-stu-id="a83a4-136">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span></span>  <span data-ttu-id="a83a4-137">See [HttpOnly cookies][MDNHTTPCookiesSecure].</span><span class="sxs-lookup"><span data-stu-id="a83a4-137">See [HttpOnly cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="a83a4-138">**Secure**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-138">**Secure**.</span></span>  <span data-ttu-id="a83a4-139">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span><span class="sxs-lookup"><span data-stu-id="a83a4-139">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span></span>  <span data-ttu-id="a83a4-140">See [Secure cookies][MDNHTTPCookiesSecure].</span><span class="sxs-lookup"><span data-stu-id="a83a4-140">See [Secure cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="a83a4-141">**SameSite**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-141">**SameSite**.</span></span>  <span data-ttu-id="a83a4-142">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span><span class="sxs-lookup"><span data-stu-id="a83a4-142">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span></span>  
*   <span data-ttu-id="a83a4-143">**Priority**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-143">**Priority**.</span></span>  <span data-ttu-id="a83a4-144">Contains `low`, `medium` \(default\), or `high` if the cookie is using the deprecated [cookie Priority][ChromiumIssue232693] attribute.</span><span class="sxs-lookup"><span data-stu-id="a83a4-144">Contains `low`, `medium` \(default\), or `high` if the cookie is using the deprecated [cookie Priority][ChromiumIssue232693] attribute.</span></span>

## <span data-ttu-id="a83a4-145">Filter cookies</span><span class="sxs-lookup"><span data-stu-id="a83a4-145">Filter cookies</span></span>  

<span data-ttu-id="a83a4-146">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span><span class="sxs-lookup"><span data-stu-id="a83a4-146">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span></span>  <span data-ttu-id="a83a4-147">Filtering by other fields is not supported.</span><span class="sxs-lookup"><span data-stu-id="a83a4-147">Filtering by other fields is not supported.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-filter-id.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-cookies-filter-id.msft.png":::
   <span data-ttu-id="a83a4-149">Figure 3:  Filtering out any cookies that do not contain the text</span><span class="sxs-lookup"><span data-stu-id="a83a4-149">Figure 3:  Filtering out any cookies that do not contain the text</span></span> `ID`  
:::image-end:::  

## <span data-ttu-id="a83a4-150">Edit a cookie</span><span class="sxs-lookup"><span data-stu-id="a83a4-150">Edit a cookie</span></span>  

<span data-ttu-id="a83a4-151">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span><span class="sxs-lookup"><span data-stu-id="a83a4-151">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span></span>  
<span data-ttu-id="a83a4-152">Double-click a field to edit it.</span><span class="sxs-lookup"><span data-stu-id="a83a4-152">Double-click a field to edit it.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-rename.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-cookies-rename.msft.png":::
   <span data-ttu-id="a83a4-154">Figure 4:  Setting the name of a cookie to</span><span class="sxs-lookup"><span data-stu-id="a83a4-154">Figure 4:  Setting the name of a cookie to</span></span> `DEVTOOLS!`  
:::image-end:::  

## <span data-ttu-id="a83a4-155">Delete cookies</span><span class="sxs-lookup"><span data-stu-id="a83a4-155">Delete cookies</span></span>  

<span data-ttu-id="a83a4-156">Select a cookie and select **Delete Selected** ![Delete Selected][ImageDeleteIcon]  to delete the specific cookie.</span><span class="sxs-lookup"><span data-stu-id="a83a4-156">Select a cookie and select **Delete Selected** ![Delete Selected][ImageDeleteIcon]  to delete the specific cookie.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-delete-selected.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-cookies-delete-selected.msft.png":::
   <span data-ttu-id="a83a4-158">Figure 5:  Deleting a specific cookie</span><span class="sxs-lookup"><span data-stu-id="a83a4-158">Figure 5:  Deleting a specific cookie</span></span>  
:::image-end:::  

<span data-ttu-id="a83a4-159">Select **Clear All** ![Clear All][ImageClearIcon]  to delete all cookies.</span><span class="sxs-lookup"><span data-stu-id="a83a4-159">Select **Clear All** ![Clear All][ImageClearIcon]  to delete all cookies.</span></span>  

:::image type="complex" source="../media/storage-application-storage-cookies-clear-all.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-cookies-clear-all.msft.png":::
   <span data-ttu-id="a83a4-161">Figure 6:  Clearing all cookies</span><span class="sxs-lookup"><span data-stu-id="a83a4-161">Figure 6:  Clearing all cookies</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) Developer Tools"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Open Microsoft Edge DevTools"  

[ChromiumIssue232693]: https://bugs.chromium.org/p/chromium/issues/detail?id=232693 "Chromium Issue 232693: Implementing Priority Field for Cookies | Chromium Bugs"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookies | MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP cookies - Permanent cookies | MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP cookies - SameSite cookies | MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookies - Scope of cookies | MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP cookies - Secure and HttpOnly cookies | MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP cookies - Session cookies | MDN"  

> [!NOTE]
> <span data-ttu-id="a83a4-171">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a83a4-171">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a83a4-172">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="a83a4-172">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="a83a4-174">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a83a4-174">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
