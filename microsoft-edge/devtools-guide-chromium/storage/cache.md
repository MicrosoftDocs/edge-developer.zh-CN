---
title: 查看 Microsoft Edge DevTools 中的缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 82356777f209b86f88de1ee53b212947d969ff8a
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612071"
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





# <span data-ttu-id="a0f57-103">查看 Microsoft Edge DevTools 中的缓存数据</span><span class="sxs-lookup"><span data-stu-id="a0f57-103">View Cache Data With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="a0f57-104">本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]检查[缓存][MDNCache]数据。</span><span class="sxs-lookup"><span data-stu-id="a0f57-104">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Cache][MDNCache] data.</span></span>  

<span data-ttu-id="a0f57-105">如果您尝试检查[HTTP 缓存][MDNHTTPCaching]数据，这不是您所需的指南。</span><span class="sxs-lookup"><span data-stu-id="a0f57-105">If you are trying to inspect [HTTP cache][MDNHTTPCaching] data, this is not the guide you want.</span></span>  
<span data-ttu-id="a0f57-106">在**网络日志**的 "**大小**" 列中查找信息。</span><span class="sxs-lookup"><span data-stu-id="a0f57-106">Look for the information in the **Size** column of the **Network Log**.</span></span>  <span data-ttu-id="a0f57-107">请参阅[记录网络活动][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="a0f57-107">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

## <span data-ttu-id="a0f57-108">查看缓存数据</span><span class="sxs-lookup"><span data-stu-id="a0f57-108">View cache data</span></span>   

1.  <span data-ttu-id="a0f57-109">选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="a0f57-109">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="a0f57-110">默认情况下，**清单**窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="a0f57-110">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-111">图 1</span><span class="sxs-lookup"><span data-stu-id="a0f57-111">Figure 1</span></span>  
    > <span data-ttu-id="a0f57-112">清单窗格</span><span class="sxs-lookup"><span data-stu-id="a0f57-112">The Manifest pane</span></span>  
    > ![清单窗格][ImageManifestPane]  

1.  <span data-ttu-id="a0f57-114">展开 "**缓存存储**" 部分以查看可用缓存。</span><span class="sxs-lookup"><span data-stu-id="a0f57-114">Expand the **Cache Storage** section to view available caches.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-115">图 2</span><span class="sxs-lookup"><span data-stu-id="a0f57-115">Figure 2</span></span>  
    > <span data-ttu-id="a0f57-116">可用缓存</span><span class="sxs-lookup"><span data-stu-id="a0f57-116">Available caches</span></span>  
    > ![可用缓存][ImageCache]  

1.  <span data-ttu-id="a0f57-118">选择缓存以查看内容。</span><span class="sxs-lookup"><span data-stu-id="a0f57-118">Select a cache to view the contents.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-119">图 3</span><span class="sxs-lookup"><span data-stu-id="a0f57-119">Figure 3</span></span>  
    > <span data-ttu-id="a0f57-120">查看缓存的内容</span><span class="sxs-lookup"><span data-stu-id="a0f57-120">Viewing the contents of a cache</span></span>  
    > ![查看缓存的内容][ImageCacheView]  

1.  <span data-ttu-id="a0f57-122">在表下方的部分中选择要查看其 HTTP 标头的资源。</span><span class="sxs-lookup"><span data-stu-id="a0f57-122">Select a resource to view the HTTP headers in the section below the table.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-123">图 4</span><span class="sxs-lookup"><span data-stu-id="a0f57-123">Figure 4</span></span>  
    > <span data-ttu-id="a0f57-124">查看资源的 HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="a0f57-124">Viewing the HTTP headers of a resource</span></span>  
    > ![查看资源的 HTTP 标头][ImageViewCacheResource]  

1.  <span data-ttu-id="a0f57-126">选择 "**预览**" 以查看资源的内容。</span><span class="sxs-lookup"><span data-stu-id="a0f57-126">Select **Preview** to view the content of a resource.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-127">图 5</span><span class="sxs-lookup"><span data-stu-id="a0f57-127">Figure 5</span></span>  
    > <span data-ttu-id="a0f57-128">查看资源的内容</span><span class="sxs-lookup"><span data-stu-id="a0f57-128">Viewing the content of a resource</span></span>  
    > ![查看资源的内容][ImageCacheContent]  

## <span data-ttu-id="a0f57-130">刷新资源</span><span class="sxs-lookup"><span data-stu-id="a0f57-130">Refresh a resource</span></span>   

1.  <span data-ttu-id="a0f57-131">[查看缓存的数据](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-131">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="a0f57-132">选择要刷新的资源。</span><span class="sxs-lookup"><span data-stu-id="a0f57-132">Select the resource that you want to refresh.</span></span>  <span data-ttu-id="a0f57-133">DevTools 将突出显示它以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="a0f57-133">DevTools highlights it to indicate that it is selected.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-134">图 6</span><span class="sxs-lookup"><span data-stu-id="a0f57-134">Figure 6</span></span>  
    > <span data-ttu-id="a0f57-135">选择资源</span><span class="sxs-lookup"><span data-stu-id="a0f57-135">Selecting a resource</span></span>  
    > ![选择资源][ImageCacheSelected]  

1.  <span data-ttu-id="a0f57-137">选择 "**刷新** ![ 刷新" ][ImageRefreshIcon] 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-137">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  

## <span data-ttu-id="a0f57-138">筛选资源</span><span class="sxs-lookup"><span data-stu-id="a0f57-138">Filter resources</span></span>   

1.  <span data-ttu-id="a0f57-139">[查看缓存的数据](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-139">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="a0f57-140">使用 "**按路径筛选**" 文本框筛选出与您提供的路径不匹配的任何资源。</span><span class="sxs-lookup"><span data-stu-id="a0f57-140">Use the **Filter by Path** text box to filter out any resources that do not match the path that you provide.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-141">图 7</span><span class="sxs-lookup"><span data-stu-id="a0f57-141">Figure 7</span></span>  
    > <span data-ttu-id="a0f57-142">筛选出与指定路径不匹配的资源</span><span class="sxs-lookup"><span data-stu-id="a0f57-142">Filtering out resources that do not match the specified path</span></span>  
    > ![筛选出与指定路径不匹配的资源][ImageCacheFilter]  

## <span data-ttu-id="a0f57-144">删除资源</span><span class="sxs-lookup"><span data-stu-id="a0f57-144">Delete a resource</span></span>   

1.  <span data-ttu-id="a0f57-145">[查看缓存的数据](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-145">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="a0f57-146">选择要删除的资源。</span><span class="sxs-lookup"><span data-stu-id="a0f57-146">Select the resource that you want to delete.</span></span>  <span data-ttu-id="a0f57-147">DevTools 将突出显示它以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="a0f57-147">DevTools highlights it to indicate that it is selected.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-148">图 8</span><span class="sxs-lookup"><span data-stu-id="a0f57-148">Figure 8</span></span>  
    > <span data-ttu-id="a0f57-149">选择资源</span><span class="sxs-lookup"><span data-stu-id="a0f57-149">Selecting a resource</span></span>  
    > ![选择资源][ImageCacheSelected2]  

1.  <span data-ttu-id="a0f57-151">选择 "**删除**所选 ![ 删除" ][ImageDeleteIcon] 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-151">Select **Delete Selected** ![Delete Selected][ImageDeleteIcon].</span></span>  

## <span data-ttu-id="a0f57-152">删除所有缓存数据</span><span class="sxs-lookup"><span data-stu-id="a0f57-152">Delete all cache data</span></span>   

1.  <span data-ttu-id="a0f57-153">打开**应用程序**  >  **清除存储**。</span><span class="sxs-lookup"><span data-stu-id="a0f57-153">Open **Application** > **Clear Storage**.</span></span>  
1.  <span data-ttu-id="a0f57-154">请确保已启用 "**缓存存储**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a0f57-154">Make sure that the **Cache Storage** checkbox is enabled.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-155">图 9</span><span class="sxs-lookup"><span data-stu-id="a0f57-155">Figure 9</span></span>  
    > <span data-ttu-id="a0f57-156">"**缓存存储**" 复选框</span><span class="sxs-lookup"><span data-stu-id="a0f57-156">The **Cache Storage** checkbox</span></span>  
    > !["缓存存储" 复选框][ImageCacheCheckbox]  

1.  <span data-ttu-id="a0f57-158">选择 "**清除网站数据**"。</span><span class="sxs-lookup"><span data-stu-id="a0f57-158">Select **Clear site data**.</span></span>  
    
    > ##### <span data-ttu-id="a0f57-159">图 10</span><span class="sxs-lookup"><span data-stu-id="a0f57-159">Figure 10</span></span>  
    > <span data-ttu-id="a0f57-160">"**清除网站数据**" 按钮</span><span class="sxs-lookup"><span data-stu-id="a0f57-160">The **Clear Site Data** button</span></span>  
    > !["清除网站数据" 按钮][ImageCacheClearSite]  

<!--  -->  



<!-- image links -->  

[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "图1：清单窗格"  
[ImageCache]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage.msft.png "图2：可用缓存"  
[ImageCacheView]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-root-headers.msft.png "图3：查看缓存的内容"  
[ImageViewCacheResource]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-index-headers.msft.png "图4：查看资源的 HTTP 标头"  
[ImageCacheContent]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-js-preview.msft.png "图5：查看资源的内容"  
[ImageCacheSelected]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-refresh.msft.png "图6：选择资源"  
[ImageCacheFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-filter.msft.png "图7：筛选出与指定路径不匹配的资源"  
[ImageCacheSelected2]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-delete-selected.msft.png "图8：选择资源"  
[ImageCacheCheckbox]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-cache-storage-checkbox.msft.png "图9： "缓存存储" 复选框"  
[ImageCacheClearSite]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png "图10： "清除网站数据" 按钮"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevtoolsNetworkLogActivity]: /microsoft-edge/network/index#log-network-activity  "记录网络活动"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 |MDN"  

> [!NOTE]
> <span data-ttu-id="a0f57-176">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a0f57-176">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a0f57-177">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cache)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="a0f57-177">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="a0f57-179">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a0f57-179">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
