---
title: 查看 Microsoft Edge DevTools 中的应用程序缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: fc1800fc54e5fb0d7998c62ce163ece7a461dd82
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931205"
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

# <span data-ttu-id="fdead-103">查看 Microsoft Edge DevTools 中的应用程序缓存数据</span><span class="sxs-lookup"><span data-stu-id="fdead-103">View Application Cache data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="fdead-104">[正在从 web 平台中删除][HTMLStandardOfflineWebApplications]应用程序缓存 API。</span><span class="sxs-lookup"><span data-stu-id="fdead-104">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span></span>  

<span data-ttu-id="fdead-105">本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 [应用程序缓存][MDNWebAPIsWindowApplicationCache] 资源。</span><span class="sxs-lookup"><span data-stu-id="fdead-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <span data-ttu-id="fdead-106">查看应用程序缓存数据</span><span class="sxs-lookup"><span data-stu-id="fdead-106">View Application Cache data</span></span>  

1.  <span data-ttu-id="fdead-107">选择 " **源** " 选项卡以打开 " **源** " 面板。</span><span class="sxs-lookup"><span data-stu-id="fdead-107">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="fdead-108">默认情况下， **清单** 窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="fdead-108">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="fdead-110">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="fdead-110">The **Manifest** pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="fdead-111">展开 " **应用程序缓存** " 部分，然后选择缓存以查看资源。</span><span class="sxs-lookup"><span data-stu-id="fdead-111">Expand the **Application Cache** section and choose a cache to view the resources.</span></span>  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text=""应用程序缓存" 窗格" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       <span data-ttu-id="fdead-113">" **应用程序缓存** " 窗格</span><span class="sxs-lookup"><span data-stu-id="fdead-113">The **Application Cache** pane</span></span>  
    :::image-end:::  

<span data-ttu-id="fdead-114">表的每一行表示一个缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="fdead-114">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="fdead-115">" **类型** " 列表示 [资源的类别][MDNHTMLResourcesInAnApplicationCache]。</span><span class="sxs-lookup"><span data-stu-id="fdead-115">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="fdead-116">类别</span><span class="sxs-lookup"><span data-stu-id="fdead-116">Category</span></span> | <span data-ttu-id="fdead-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="fdead-117">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="fdead-118">此资源已在清单中明确列出。</span><span class="sxs-lookup"><span data-stu-id="fdead-118">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="fdead-119">该 URL 是其他资源的备用 URL。</span><span class="sxs-lookup"><span data-stu-id="fdead-119">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="fdead-120">其他资源的 URL 未在 DevTools 中列出。</span><span class="sxs-lookup"><span data-stu-id="fdead-120">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="fdead-121">`manifest`资源的属性指示缓存是资源的父项。</span><span class="sxs-lookup"><span data-stu-id="fdead-121">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="fdead-122">指定资源必须来自网络的清单。</span><span class="sxs-lookup"><span data-stu-id="fdead-122">The manifest specified that the resource must come from the network.</span></span> |  

<!--todo:  replace "Master" phrasing if possible.  -->  

<span data-ttu-id="fdead-123">在表底部有状态图标，指示你的网络连接和 **应用程序缓存**的状态。</span><span class="sxs-lookup"><span data-stu-id="fdead-123">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span></span>  <span data-ttu-id="fdead-124">**应用程序缓存**可能具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="fdead-124">The **Application Cache** may have the following states.</span></span>  

| <span data-ttu-id="fdead-125">State</span><span class="sxs-lookup"><span data-stu-id="fdead-125">State</span></span> | <span data-ttu-id="fdead-126">详细信息</span><span class="sxs-lookup"><span data-stu-id="fdead-126">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="fdead-127">清单将被提取并检查更新。</span><span class="sxs-lookup"><span data-stu-id="fdead-127">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="fdead-128">正在将资源添加到缓存。</span><span class="sxs-lookup"><span data-stu-id="fdead-128">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="fdead-129">缓存没有新更改。</span><span class="sxs-lookup"><span data-stu-id="fdead-129">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="fdead-130">正在删除缓存。</span><span class="sxs-lookup"><span data-stu-id="fdead-130">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="fdead-131">缓存的新版本可用。</span><span class="sxs-lookup"><span data-stu-id="fdead-131">A new version of the cache is available.</span></span> |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "脱机 Web 应用程序-HTML 标准"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "应用程序缓存中的资源 |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "ApplicationCache-Web Api |MDN"  

> [!NOTE]
> <span data-ttu-id="fdead-136">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="fdead-136">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fdead-137">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="fdead-137">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="fdead-139">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="fdead-139">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
