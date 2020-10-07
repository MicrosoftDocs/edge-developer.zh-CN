---
description: How to view Application Cache data from the Application panel of Microsoft Edge DevTools.
title: View Application Cache Data With Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: ed742f24900786c3c5b31ec2a026ddbf9d16ccb6
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993322"
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

# <span data-ttu-id="1b90d-104">View Application Cache data with Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="1b90d-104">View Application Cache data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="1b90d-105">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span><span class="sxs-lookup"><span data-stu-id="1b90d-105">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span></span>  

<span data-ttu-id="1b90d-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span><span class="sxs-lookup"><span data-stu-id="1b90d-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <span data-ttu-id="1b90d-107">View Application Cache data</span><span class="sxs-lookup"><span data-stu-id="1b90d-107">View Application Cache data</span></span>  

1.  <span data-ttu-id="1b90d-108">Select the **Sources** tab to open the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="1b90d-108">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="1b90d-109">The **Manifest** pane usually opens by default.</span><span class="sxs-lookup"><span data-stu-id="1b90d-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="1b90d-111">The **Manifest** pane</span><span class="sxs-lookup"><span data-stu-id="1b90d-111">The **Manifest** pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="1b90d-112">Expand the **Application Cache** section and choose a cache to view the resources.</span><span class="sxs-lookup"><span data-stu-id="1b90d-112">Expand the **Application Cache** section and choose a cache to view the resources.</span></span>  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       <span data-ttu-id="1b90d-114">The **Application Cache** pane</span><span class="sxs-lookup"><span data-stu-id="1b90d-114">The **Application Cache** pane</span></span>  
    :::image-end:::  

<span data-ttu-id="1b90d-115">Each row of the table represents a cached resource.</span><span class="sxs-lookup"><span data-stu-id="1b90d-115">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="1b90d-116">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span><span class="sxs-lookup"><span data-stu-id="1b90d-116">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="1b90d-117">Category</span><span class="sxs-lookup"><span data-stu-id="1b90d-117">Category</span></span> | <span data-ttu-id="1b90d-118">Details</span><span class="sxs-lookup"><span data-stu-id="1b90d-118">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="1b90d-119">This resource was explicitly listed in the manifest.</span><span class="sxs-lookup"><span data-stu-id="1b90d-119">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="1b90d-120">The URL is a fallback for another resource.</span><span class="sxs-lookup"><span data-stu-id="1b90d-120">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="1b90d-121">The URL of the other resource is not listed in DevTools.</span><span class="sxs-lookup"><span data-stu-id="1b90d-121">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="1b90d-122">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span><span class="sxs-lookup"><span data-stu-id="1b90d-122">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="1b90d-123">The manifest specified that the resource must come from the network.</span><span class="sxs-lookup"><span data-stu-id="1b90d-123">The manifest specified that the resource must come from the network.</span></span> |  

<!--todo:  replace "Master" phrasing if possible.  -->  

<span data-ttu-id="1b90d-124">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span><span class="sxs-lookup"><span data-stu-id="1b90d-124">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span></span>  <span data-ttu-id="1b90d-125">The **Application Cache** may have the following states.</span><span class="sxs-lookup"><span data-stu-id="1b90d-125">The **Application Cache** may have the following states.</span></span>  

| <span data-ttu-id="1b90d-126">State</span><span class="sxs-lookup"><span data-stu-id="1b90d-126">State</span></span> | <span data-ttu-id="1b90d-127">Details</span><span class="sxs-lookup"><span data-stu-id="1b90d-127">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="1b90d-128">The manifest is being fetched and checked for updates.</span><span class="sxs-lookup"><span data-stu-id="1b90d-128">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="1b90d-129">Resources are being added to the cache.</span><span class="sxs-lookup"><span data-stu-id="1b90d-129">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="1b90d-130">The cache has no new changes.</span><span class="sxs-lookup"><span data-stu-id="1b90d-130">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="1b90d-131">The cache is being deleted.</span><span class="sxs-lookup"><span data-stu-id="1b90d-131">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="1b90d-132">A new version of the cache is available.</span><span class="sxs-lookup"><span data-stu-id="1b90d-132">A new version of the cache is available.</span></span> |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer Tools | Microsoft Docs"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "Offline Web applications - HTML Standard"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "Resources in an application cache | MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web APIs | MDN"  

> [!NOTE]
> <span data-ttu-id="1b90d-137">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1b90d-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1b90d-138">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="1b90d-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="1b90d-140">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1b90d-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
