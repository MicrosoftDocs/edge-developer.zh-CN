---
description: 如何从开发人员工具的应用程序面板中查看Microsoft Edge缓存数据。
title: 使用 DevTools Microsoft Edge应用程序缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 71e71555940d74f2071178be2e6daf0ec2f49dfd
ms.sourcegitcommit: d0a6959c5338cf1927093b4a9ed29a0bc0390b43
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "11615419"
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
# <a name="view-application-cache-data-with-microsoft-edge-devtools"></a><span data-ttu-id="77c83-104">使用 DevTools Microsoft Edge应用程序缓存数据</span><span class="sxs-lookup"><span data-stu-id="77c83-104">View Application Cache data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="77c83-105">应用程序缓存已弃用，应避免使用它。</span><span class="sxs-lookup"><span data-stu-id="77c83-105">The Application Cache is deprecated, and you should avoid using it.</span></span>  <span data-ttu-id="77c83-106">将从 Web 平台中删除应用程序缓存 API。</span><span class="sxs-lookup"><span data-stu-id="77c83-106">The Application Cache API is being removed from the web platform.</span></span>  <span data-ttu-id="77c83-107">有关详细信息，请导航到["准备 AppCache 删除"。][WebDevAppcacheRemoval]</span><span class="sxs-lookup"><span data-stu-id="77c83-107">For more information, navigate to [Preparing for AppCache removal][WebDevAppcacheRemoval].</span></span>

<span data-ttu-id="77c83-108">本指南演示如何使用[DevTools Microsoft Edge检查][MicrosoftEdgeDevTools][应用程序缓存][MDNWebAPIsWindowApplicationCache]资源。</span><span class="sxs-lookup"><span data-stu-id="77c83-108">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <a name="view-application-cache-data"></a><span data-ttu-id="77c83-109">查看应用程序缓存数据</span><span class="sxs-lookup"><span data-stu-id="77c83-109">View Application Cache data</span></span>  

1.  <span data-ttu-id="77c83-110">在 DevTools 顶部，选择" **应用程序"** 工具。</span><span class="sxs-lookup"><span data-stu-id="77c83-110">At the top of DevTools, choose the **Application** tool.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="77c83-112">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="77c83-112">The **Manifest** pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="77c83-113">展开" **应用程序缓存** "部分并选择缓存以查看资源。</span><span class="sxs-lookup"><span data-stu-id="77c83-113">Expand the **Application Cache** section and choose a cache to view the resources.</span></span>  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text=""应用程序缓存"窗格" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       <span data-ttu-id="77c83-115">" **应用程序缓存"** 窗格</span><span class="sxs-lookup"><span data-stu-id="77c83-115">The **Application Cache** pane</span></span>  
    :::image-end:::  

<span data-ttu-id="77c83-116">表格的每一行都代表一个缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="77c83-116">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="77c83-117">" **类型** " [列表示资源 的类别][MDNHTMLResourcesInAnApplicationCache]。</span><span class="sxs-lookup"><span data-stu-id="77c83-117">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="77c83-118">类别</span><span class="sxs-lookup"><span data-stu-id="77c83-118">Category</span></span> | <span data-ttu-id="77c83-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="77c83-119">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="77c83-120">此资源在清单中显式列出。</span><span class="sxs-lookup"><span data-stu-id="77c83-120">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="77c83-121">URL 是另一个资源的回退。</span><span class="sxs-lookup"><span data-stu-id="77c83-121">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="77c83-122">其他资源的 URL 未在 DevTools 中列出。</span><span class="sxs-lookup"><span data-stu-id="77c83-122">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="77c83-123">`manifest`资源上的 属性指示缓存是资源的父项。</span><span class="sxs-lookup"><span data-stu-id="77c83-123">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="77c83-124">清单指定资源必须来自网络。</span><span class="sxs-lookup"><span data-stu-id="77c83-124">The manifest specified that the resource must come from the network.</span></span> |  

<!--todo:  replace "Master" phrasing if possible.  -->  

<span data-ttu-id="77c83-125">在表底部有状态图标，指示网络连接和应用程序缓存 **的状态**。</span><span class="sxs-lookup"><span data-stu-id="77c83-125">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span></span>  <span data-ttu-id="77c83-126">应用程序 **缓存** 可能具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="77c83-126">The **Application Cache** may have the following states.</span></span>  

| <span data-ttu-id="77c83-127">State</span><span class="sxs-lookup"><span data-stu-id="77c83-127">State</span></span> | <span data-ttu-id="77c83-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="77c83-128">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="77c83-129">正在提取清单并检查更新。</span><span class="sxs-lookup"><span data-stu-id="77c83-129">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="77c83-130">资源将添加到缓存中。</span><span class="sxs-lookup"><span data-stu-id="77c83-130">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="77c83-131">缓存没有新的更改。</span><span class="sxs-lookup"><span data-stu-id="77c83-131">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="77c83-132">正在删除缓存。</span><span class="sxs-lookup"><span data-stu-id="77c83-132">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="77c83-133">提供新版本的缓存。</span><span class="sxs-lookup"><span data-stu-id="77c83-133">A new version of the cache is available.</span></span> |  

<!-- links -->  
[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
<!-- external links: -->
[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "应用程序缓存缓存中的|MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web API |MDN"  

[WebDevAppcacheRemoval]: https://web.dev/appcache-removal "准备 AppCache 删除|web.dev"  

> [!NOTE]
> <span data-ttu-id="77c83-138">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="77c83-138">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="77c83-139">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="77c83-139">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="77c83-141">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="77c83-141">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
