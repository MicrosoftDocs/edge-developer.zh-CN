---
description: 如何从 Microsoft Edge DevTools 的应用程序面板查看缓存数据。
title: 使用 Microsoft Edge DevTools 查看缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 1f66419014682a316fa565c5ef2ab704f652637f
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564684"
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
# <a name="view-cache-data-with-microsoft-edge-devtools"></a><span data-ttu-id="74d4e-104">使用 Microsoft Edge DevTools 查看缓存数据</span><span class="sxs-lookup"><span data-stu-id="74d4e-104">View cache data with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="74d4e-105">本指南将演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查[缓存][MDNCache]数据。</span><span class="sxs-lookup"><span data-stu-id="74d4e-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Cache][MDNCache] data.</span></span>  

<span data-ttu-id="74d4e-106">如果要尝试检查 http [缓存][MDNHTTPCaching] 数据，则这不是你想要的指南。</span><span class="sxs-lookup"><span data-stu-id="74d4e-106">If you are trying to inspect [HTTP cache][MDNHTTPCaching] data, this is not the guide you want.</span></span>  <span data-ttu-id="74d4e-107">在"网络日志"字段的 **大小** 列中 **信息**。</span><span class="sxs-lookup"><span data-stu-id="74d4e-107">Look for the information in the **Size** column of the **Network Log**.</span></span>  <span data-ttu-id="74d4e-108">导航到 [记录网络][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="74d4e-108">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

## <a name="view-cache-data"></a><span data-ttu-id="74d4e-109">查看缓存数据</span><span class="sxs-lookup"><span data-stu-id="74d4e-109">View cache data</span></span>  

1.  <span data-ttu-id="74d4e-110">选择**应用程序**选项卡打开**应用程序**工具。</span><span class="sxs-lookup"><span data-stu-id="74d4e-110">Choose the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="74d4e-111">通常默认**清单**窗格打开。</span><span class="sxs-lookup"><span data-stu-id="74d4e-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="74d4e-113">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="74d4e-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="74d4e-114">展开 **缓存存储** 部分以查看可用的缓存。</span><span class="sxs-lookup"><span data-stu-id="74d4e-114">Expand the **Cache Storage** section to view available caches.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="可用缓存" lightbox="../media/storage-application-cache-storage.msft.png":::
       <span data-ttu-id="74d4e-116">可用缓存</span><span class="sxs-lookup"><span data-stu-id="74d4e-116">Available caches</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="74d4e-117">选择缓存以查看内容。</span><span class="sxs-lookup"><span data-stu-id="74d4e-117">Choose a cache to view the contents.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="查看缓存的内容" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       <span data-ttu-id="74d4e-119">查看缓存的内容</span><span class="sxs-lookup"><span data-stu-id="74d4e-119">View the contents of a cache</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="74d4e-120">选择资源以查看表下部分中的 HTTP 标题。</span><span class="sxs-lookup"><span data-stu-id="74d4e-120">Choose a resource to view the HTTP headers in the section below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="查看资源的 HTTP 标题" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       <span data-ttu-id="74d4e-122">查看资源的 HTTP 标题</span><span class="sxs-lookup"><span data-stu-id="74d4e-122">View the HTTP headers of a resource</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="74d4e-123">选择 **预览** 以查看资源的内容。</span><span class="sxs-lookup"><span data-stu-id="74d4e-123">Choose **Preview** to view the content of a resource.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="查看资源的内容" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       <span data-ttu-id="74d4e-125">查看资源的内容</span><span class="sxs-lookup"><span data-stu-id="74d4e-125">View the content of a resource</span></span>  
    :::image-end:::  
    
## <a name="refresh-a-resource"></a><span data-ttu-id="74d4e-126">刷新资源</span><span class="sxs-lookup"><span data-stu-id="74d4e-126">Refresh a resource</span></span>  

1.  <span data-ttu-id="74d4e-127">[查看缓存](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="74d4e-127">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="74d4e-128">选择要刷新的资源。</span><span class="sxs-lookup"><span data-stu-id="74d4e-128">Choose the resource that you want to refresh.</span></span>  <span data-ttu-id="74d4e-129">DevTools 会突出显示它以表明已选中。</span><span class="sxs-lookup"><span data-stu-id="74d4e-129">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="选择要刷新的资源" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       <span data-ttu-id="74d4e-131">选择要刷新的资源</span><span class="sxs-lookup"><span data-stu-id="74d4e-131">Choose a resource to refresh</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="74d4e-132">选择**刷新** \(![Refresh](../media/refresh-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="74d4e-132">Choose **Refresh** \(![Refresh](../media/refresh-icon.msft.png)\).</span></span>  
    
## <a name="filter-resources"></a><span data-ttu-id="74d4e-133">筛选资源</span><span class="sxs-lookup"><span data-stu-id="74d4e-133">Filter resources</span></span>  

1.  <span data-ttu-id="74d4e-134">[查看缓存](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="74d4e-134">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="74d4e-135">使用 **路径筛选"** 文本框来筛选与提供的路径不匹配的资源。</span><span class="sxs-lookup"><span data-stu-id="74d4e-135">Use the **Filter by Path** text box to filter out any resources that do not match the path that you provide.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="筛选与指定路径不匹配的资源" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       <span data-ttu-id="74d4e-137">筛选与指定路径不匹配的资源</span><span class="sxs-lookup"><span data-stu-id="74d4e-137">Filter out resources that do not match the specified path</span></span>  
    :::image-end:::  
    
## <a name="delete-a-resource"></a><span data-ttu-id="74d4e-138">删除资源</span><span class="sxs-lookup"><span data-stu-id="74d4e-138">Delete a resource</span></span>  

1.  <span data-ttu-id="74d4e-139">[查看缓存](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="74d4e-139">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="74d4e-140">选择要删除的资源。</span><span class="sxs-lookup"><span data-stu-id="74d4e-140">Choose the resource that you want to delete.</span></span>  <span data-ttu-id="74d4e-141">DevTools 会突出显示它以表明已选中。</span><span class="sxs-lookup"><span data-stu-id="74d4e-141">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="选择要删除的资源" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       <span data-ttu-id="74d4e-143">选择要删除的资源</span><span class="sxs-lookup"><span data-stu-id="74d4e-143">Choose a resource to delete</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="74d4e-144">选择 **删除** \（![删除](../media/delete-icon.msft.png)\）。</span><span class="sxs-lookup"><span data-stu-id="74d4e-144">Choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\).</span></span>  
    
## <a name="delete-all-cache-data"></a><span data-ttu-id="74d4e-145">删除所有缓存数据</span><span class="sxs-lookup"><span data-stu-id="74d4e-145">Delete all cache data</span></span>  

1.  <span data-ttu-id="74d4e-146">打开**应用程序** > **存储空间**。</span><span class="sxs-lookup"><span data-stu-id="74d4e-146">Open **Application** > **Clear Storage**.</span></span>  
1.  <span data-ttu-id="74d4e-147">确保已启用" **缓存存储** 复选框。</span><span class="sxs-lookup"><span data-stu-id="74d4e-147">Make sure that the **Cache Storage** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="缓存存储复选框" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       <span data-ttu-id="74d4e-149">**缓存存储** 复选框</span><span class="sxs-lookup"><span data-stu-id="74d4e-149">The **Cache Storage** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="74d4e-150">选择**清除网站数据**。</span><span class="sxs-lookup"><span data-stu-id="74d4e-150">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="清除网站数据按钮" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       <span data-ttu-id="74d4e-152">**清除网站数据**按钮</span><span class="sxs-lookup"><span data-stu-id="74d4e-152">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="74d4e-153">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="74d4e-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "记录网络活动|Microsoft Docs"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存|MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 | MDN"  

> [!NOTE]
> <span data-ttu-id="74d4e-158">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="74d4e-158">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="74d4e-159">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="74d4e-159">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="74d4e-161">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="74d4e-161">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
