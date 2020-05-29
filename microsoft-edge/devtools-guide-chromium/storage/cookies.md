---
title: 查看、编辑和删除 Microsoft Edge DevTools 中的 Cookie
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 084c4116cd4c9c5e70b2fe341257fa68ba2c8ae7
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612066"
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





# <span data-ttu-id="6a0ac-103">查看、编辑和删除 Microsoft Edge DevTools 中的 Cookie</span><span class="sxs-lookup"><span data-stu-id="6a0ac-103">View, Edit, And Delete Cookies With Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="6a0ac-104">[HTTP cookie][MDNHTTPCookies]主要用于管理用户会话、存储用户个性化首选项和跟踪用户行为。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-104">[HTTP Cookies][MDNHTTPCookies] are mainly used to manage user sessions, store user personalization preferences, and track user behavior.</span></span>  <span data-ttu-id="6a0ac-105">它们也是导致所有这些令人讨厌的 "此页面使用 cookie" 同意表单的原因。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-105">They are also the cause of all of those annoying "this page uses cookies" consent forms that you see across the web.</span></span>  <span data-ttu-id="6a0ac-106">本指南教你如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]查看、编辑和删除页面上的 HTTP cookie。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-106">This guide teaches you how to view, edit, and delete the HTTP cookies for a page with [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="6a0ac-107">打开 "Cookie" 窗格</span><span class="sxs-lookup"><span data-stu-id="6a0ac-107">Open the Cookies pane</span></span>   

1.  <span data-ttu-id="6a0ac-108">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-108">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="6a0ac-109">选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-109">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="6a0ac-110">将打开 "**清单**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-110">The **Manifest** pane should open.</span></span>  
    
    > ##### <span data-ttu-id="6a0ac-111">图 1</span><span class="sxs-lookup"><span data-stu-id="6a0ac-111">Figure 1</span></span>  
    > <span data-ttu-id="6a0ac-112">清单窗格</span><span class="sxs-lookup"><span data-stu-id="6a0ac-112">The Manifest pane</span></span>  
    > ![清单窗格][ImageManifest]  

1.  <span data-ttu-id="6a0ac-114">在 "**存储**" 下展开 " **cookie**"，然后选择一个原点。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-114">Under **Storage** expand **Cookies**, then select an origin.</span></span>  
    
    > ##### <span data-ttu-id="6a0ac-115">图 2</span><span class="sxs-lookup"><span data-stu-id="6a0ac-115">Figure 2</span></span>  
    > <span data-ttu-id="6a0ac-116">"Cookie" 窗格</span><span class="sxs-lookup"><span data-stu-id="6a0ac-116">The Cookies pane</span></span>  
    > !["Cookie" 窗格][ImageCookies]  

## <span data-ttu-id="6a0ac-118">字段</span><span class="sxs-lookup"><span data-stu-id="6a0ac-118">Fields</span></span>   

<span data-ttu-id="6a0ac-119">**Cookies**表包含以下字段：</span><span class="sxs-lookup"><span data-stu-id="6a0ac-119">The **Cookies** table contains the following fields:</span></span>  

*   <span data-ttu-id="6a0ac-120">**名称**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-120">**Name**.</span></span>  <span data-ttu-id="6a0ac-121">Cookie 的名称。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-121">The name of the cookie.</span></span>  
*   <span data-ttu-id="6a0ac-122">**值**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-122">**Value**.</span></span>  <span data-ttu-id="6a0ac-123">Cookie 的值。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-123">The value of the cookie.</span></span>  
*   <span data-ttu-id="6a0ac-124">**域**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-124">**Domain**.</span></span>  <span data-ttu-id="6a0ac-125">允许接收该 cookie 的主机。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-125">The hosts that are allowed to receive the cookie.</span></span>  <span data-ttu-id="6a0ac-126">请参阅[Cookie 范围][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-126">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="6a0ac-127">**路径**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-127">**Path**.</span></span>  <span data-ttu-id="6a0ac-128">必须存在于请求的 URL 中才能发送页眉的 URL `Cookie` 。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-128">The URL that must exist in the requested URL in order to send the `Cookie` header.</span></span>  <span data-ttu-id="6a0ac-129">请参阅[Cookie 范围][MDNHTTPCookiesScope]。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-129">See [Scope of cookies][MDNHTTPCookiesScope].</span></span>  
*   <span data-ttu-id="6a0ac-130">**过期/最大存留期**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-130">**Expires / Max-Age**.</span></span>  <span data-ttu-id="6a0ac-131">Cookie 的到期日期或最长期限。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-131">The expiration date or maximum age of the cookie.</span></span>  <span data-ttu-id="6a0ac-132">请参阅[永久 cookie][MDNHTTPCookiesPermanent]。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-132">See [Permanent cookies][MDNHTTPCookiesPermanent].</span></span>  <span data-ttu-id="6a0ac-133">对于[会话 cookie][MDNHTTPCookiesSession] ，此值始终为 `Session` 。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-133">For [session cookies][MDNHTTPCookiesSession] this value is always `Session`.</span></span>  
*   <span data-ttu-id="6a0ac-134">**大小**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-134">**Size**.</span></span>  <span data-ttu-id="6a0ac-135">Cookie 的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-135">The size, in bytes, of the cookie.</span></span>  
*   <span data-ttu-id="6a0ac-136">**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-136">**HTTP**.</span></span>  <span data-ttu-id="6a0ac-137">如果为 true，则此字段指示应仅通过 HTTP 使用该 cookie，并且不允许 JavaScript 修改。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-137">If true, this field indicates that the cookie should only be used over HTTP and JavaScript modification is not allowed.</span></span>  <span data-ttu-id="6a0ac-138">请参阅[HttpOnly cookie][MDNHTTPCookiesSecure]。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-138">See [HttpOnly cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="6a0ac-139">**安全**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-139">**Secure**.</span></span>  <span data-ttu-id="6a0ac-140">如果为 true，则此字段指示该 cookie 必须仅通过安全的 HTTPS 连接发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-140">If true, this field indicates that the cookie must be sent to the server only over a secure, HTTPS connection.</span></span>  <span data-ttu-id="6a0ac-141">请参阅[安全 cookie][MDNHTTPCookiesSecure]。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-141">See [Secure cookies][MDNHTTPCookiesSecure].</span></span>  
*   <span data-ttu-id="6a0ac-142">**SameSite**。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-142">**SameSite**.</span></span>  <span data-ttu-id="6a0ac-143">包含 `strict` 或 `lax` 如果 cookie 使用实验性的[Samesite][MDNHTTPCookiesSamesite]属性。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-143">Contains `strict` or `lax` if the cookie is using the experimental [Samesite][MDNHTTPCookiesSamesite] attribute.</span></span>  

## <span data-ttu-id="6a0ac-144">筛选 cookie</span><span class="sxs-lookup"><span data-stu-id="6a0ac-144">Filter cookies</span></span>   

<span data-ttu-id="6a0ac-145">使用 "**筛选**" 文本框按**名称**或**值**筛选 cookie。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-145">Use the **Filter** text box to filter cookies by **Name** or **Value**.</span></span>  <span data-ttu-id="6a0ac-146">不支持按其他字段进行筛选。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-146">Filtering by other fields is not supported.</span></span>  

> ##### <span data-ttu-id="6a0ac-147">图 3</span><span class="sxs-lookup"><span data-stu-id="6a0ac-147">Figure 3</span></span>  
> <span data-ttu-id="6a0ac-148">筛选出不包含文本的任何 cookie</span><span class="sxs-lookup"><span data-stu-id="6a0ac-148">Filtering out any cookies that do not contain the text</span></span> `ID`  
> ![筛选出不包含文本 ID 的任何 cookie][ImageCookiesFilter]  

## <span data-ttu-id="6a0ac-150">编辑 cookie</span><span class="sxs-lookup"><span data-stu-id="6a0ac-150">Edit a cookie</span></span>   

<span data-ttu-id="6a0ac-151">"**名称**"、"**值**"、"**域**"、"**路径**" 和 "有效期" **/"最大年龄**" 域可编辑</span><span class="sxs-lookup"><span data-stu-id="6a0ac-151">The **Name**, **Value**, **Domain**, **Path**, and **Expires / Max-Age** fields are editable.</span></span>  
<span data-ttu-id="6a0ac-152">双击字段以对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-152">Double-click a field to edit it.</span></span>  

> ##### <span data-ttu-id="6a0ac-153">图 4</span><span class="sxs-lookup"><span data-stu-id="6a0ac-153">Figure 4</span></span>  
> <span data-ttu-id="6a0ac-154">将 cookie 的名称设置为</span><span class="sxs-lookup"><span data-stu-id="6a0ac-154">Setting the name of a cookie to</span></span> `DEVTOOLS!`  
> ![将 cookie 的名称设置为 DEVTOOLS！][ImageEditCookie]  

## <span data-ttu-id="6a0ac-156">删除 Cookie</span><span class="sxs-lookup"><span data-stu-id="6a0ac-156">Delete cookies</span></span>   

<span data-ttu-id="6a0ac-157">选择一个 cookie，然后单击 "**删除**所选 ![ 删除项" ][ImageDeleteIcon] 以删除该 cookie。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-157">Select a cookie and then click **Delete Selected** ![Delete Selected][ImageDeleteIcon]  to delete that one cookie.</span></span>  

> ##### <span data-ttu-id="6a0ac-158">图 5</span><span class="sxs-lookup"><span data-stu-id="6a0ac-158">Figure 5</span></span>  
> <span data-ttu-id="6a0ac-159">删除特定的 cookie</span><span class="sxs-lookup"><span data-stu-id="6a0ac-159">Deleting a specific cookie</span></span>  
> ![删除特定的 cookie][ImageDeleteCookie]  

<span data-ttu-id="6a0ac-161">选择 "**清除**全部 ![ 清除" ][ImageClearIcon] 以删除所有 cookie。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-161">Select **Clear All** ![Clear All][ImageClearIcon]  to delete all cookies.</span></span>  

> ##### <span data-ttu-id="6a0ac-162">图 6</span><span class="sxs-lookup"><span data-stu-id="6a0ac-162">Figure 6</span></span>  
> <span data-ttu-id="6a0ac-163">清除所有 cookie</span><span class="sxs-lookup"><span data-stu-id="6a0ac-163">Clearing all cookies</span></span>  
> ![清除所有 cookie][ImageClearAllCookies]  

<!--    -->  

  

<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest-empty.msft.png "图1：清单窗格"  
[ImageCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-selected.msft.png "图2： "Cookie" 窗格"  
[ImageCookiesFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-filter-id.msft.png "图3：筛选出不包含文本 ID 的任何 cookie"  
[ImageEditCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-rename.msft.png "图4：将 cookie 的名称设置为 DEVTOOLS！"  
[ImageDeleteCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-delete-selected.msft.png "图5：删除特定的 cookie"  
[ImageClearAllCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-clear-all.msft.png "图6：清除所有 cookie"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookie |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP cookie-永久 cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP cookie-SameSite cookie |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie-cookie 范围 |MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP cookie-安全和 HttpOnly cookie |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP cookie-会话 cookie |MDN"  

> [!NOTE]
> <span data-ttu-id="6a0ac-179">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-179">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6a0ac-180">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-180">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cookies) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="6a0ac-182">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6a0ac-182">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
