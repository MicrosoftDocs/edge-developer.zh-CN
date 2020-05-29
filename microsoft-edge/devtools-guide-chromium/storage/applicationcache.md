---
title: 查看 Microsoft Edge DevTools 中的应用程序缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6ce3087e9c719efbcf4d9ebceb860edd0ed0c3b6
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612093"
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





# <span data-ttu-id="8b387-103">查看 Microsoft Edge DevTools 中的应用程序缓存数据</span><span class="sxs-lookup"><span data-stu-id="8b387-103">View Application Cache Data With Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="8b387-104">[正在从 web 平台中删除][HTMLStandardOfflineWebApplications]应用程序缓存 API。</span><span class="sxs-lookup"><span data-stu-id="8b387-104">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span></span>  

<span data-ttu-id="8b387-105">本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]检查[应用程序缓存][MDNWebAPIsWindowApplicationCache]资源。</span><span class="sxs-lookup"><span data-stu-id="8b387-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <span data-ttu-id="8b387-106">查看应用程序缓存数据</span><span class="sxs-lookup"><span data-stu-id="8b387-106">View Application Cache Data</span></span>   

1.  <span data-ttu-id="8b387-107">选择 "**源**" 选项卡以打开 "**源**" 面板。</span><span class="sxs-lookup"><span data-stu-id="8b387-107">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="8b387-108">默认情况下，**清单**窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="8b387-108">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="8b387-109">图 1</span><span class="sxs-lookup"><span data-stu-id="8b387-109">Figure 1</span></span>  
    > <span data-ttu-id="8b387-110">清单窗格</span><span class="sxs-lookup"><span data-stu-id="8b387-110">The Manifest pane</span></span>  
    > ![清单窗格][ImageManifestPane]  

1.  <span data-ttu-id="8b387-112">展开 "**应用程序缓存**" 部分，然后单击缓存以查看资源。</span><span class="sxs-lookup"><span data-stu-id="8b387-112">Expand the **Application Cache** section and click a cache to view the resources.</span></span>  
    
    > ##### <span data-ttu-id="8b387-113">图 2</span><span class="sxs-lookup"><span data-stu-id="8b387-113">Figure 2</span></span>  
    > <span data-ttu-id="8b387-114">"应用程序缓存" 窗格</span><span class="sxs-lookup"><span data-stu-id="8b387-114">The Application Cache pane</span></span>  
    > !["应用程序缓存" 窗格][ImageApplicationCachePane]  

<span data-ttu-id="8b387-116">表的每一行表示一个缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="8b387-116">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="8b387-117">"**类型**" 列表示[资源的类别][MDNHTMLResourcesInAnApplicationCache]。</span><span class="sxs-lookup"><span data-stu-id="8b387-117">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="8b387-118">类型</span><span class="sxs-lookup"><span data-stu-id="8b387-118">Category</span></span> | <span data-ttu-id="8b387-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="8b387-119">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="8b387-120">此资源已在清单中明确列出。</span><span class="sxs-lookup"><span data-stu-id="8b387-120">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="8b387-121">该 URL 是其他资源的备用 URL。</span><span class="sxs-lookup"><span data-stu-id="8b387-121">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="8b387-122">其他资源的 URL 未在 DevTools 中列出。</span><span class="sxs-lookup"><span data-stu-id="8b387-122">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="8b387-123">`manifest`资源上的属性指示此缓存是资源的父项。</span><span class="sxs-lookup"><span data-stu-id="8b387-123">The `manifest` attribute on the resource indicated that this cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="8b387-124">指定此资源必须来自网络的清单。</span><span class="sxs-lookup"><span data-stu-id="8b387-124">The manifest specified that this resource must come from the network.</span></span> |  

<span data-ttu-id="8b387-125">在表底部有状态图标，指示你的网络连接和应用程序缓存的状态。</span><span class="sxs-lookup"><span data-stu-id="8b387-125">At the bottom of the table there are status icons indicating your network connection and the status of the Application Cache.</span></span>  <span data-ttu-id="8b387-126">应用程序缓存可能具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="8b387-126">The Application Cache may have the following states.</span></span>  

| <span data-ttu-id="8b387-127">State</span><span class="sxs-lookup"><span data-stu-id="8b387-127">State</span></span> | <span data-ttu-id="8b387-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="8b387-128">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="8b387-129">清单将被提取并检查更新。</span><span class="sxs-lookup"><span data-stu-id="8b387-129">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="8b387-130">正在将资源添加到缓存。</span><span class="sxs-lookup"><span data-stu-id="8b387-130">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="8b387-131">缓存没有新更改。</span><span class="sxs-lookup"><span data-stu-id="8b387-131">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="8b387-132">正在删除缓存。</span><span class="sxs-lookup"><span data-stu-id="8b387-132">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="8b387-133">缓存的新版本可用。</span><span class="sxs-lookup"><span data-stu-id="8b387-133">A new version of the cache is available.</span></span> |  

<!--   -->  



<!-- image links -->  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "图1：清单窗格"  
[ImageApplicationCachePane]: /microsoft-edge/devtools-guide-chromium/media/storage-cache-pane-cache-storage-resources.msft.png "图2： "应用程序缓存" 窗格"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "脱机 Web 应用程序-HTML 标准"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "应用程序缓存中的资源 |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "ApplicationCache-Web Api |MDN"  

> [!NOTE]
> <span data-ttu-id="8b387-140">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8b387-140">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8b387-141">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="8b387-141">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="8b387-143">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8b387-143">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
