---
description: 如何从 Microsoft Edge DevTools 的应用程序面板查看缓存数据。
title: 查看 Microsoft Edge DevTools 中的缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 5ab5fd0b3b504443e495f1d5108907a4551e6ac6
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125438"
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

# <span data-ttu-id="9d15c-104">查看 Microsoft Edge DevTools 中的缓存数据</span><span class="sxs-lookup"><span data-stu-id="9d15c-104">View cache data with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="9d15c-105">本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 [缓存][MDNCache] 数据。</span><span class="sxs-lookup"><span data-stu-id="9d15c-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Cache][MDNCache] data.</span></span>  

<span data-ttu-id="9d15c-106">如果您尝试检查 [HTTP 缓存][MDNHTTPCaching] 数据，这不是您所需的指南。</span><span class="sxs-lookup"><span data-stu-id="9d15c-106">If you are trying to inspect [HTTP cache][MDNHTTPCaching] data, this is not the guide you want.</span></span>  <span data-ttu-id="9d15c-107">在**网络日志**的 "**大小**" 列中查找信息。</span><span class="sxs-lookup"><span data-stu-id="9d15c-107">Look for the information in the **Size** column of the **Network Log**.</span></span>  <span data-ttu-id="9d15c-108">请参阅 [记录网络活动][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="9d15c-108">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

## <span data-ttu-id="9d15c-109">查看缓存数据</span><span class="sxs-lookup"><span data-stu-id="9d15c-109">View cache data</span></span>  

1.  <span data-ttu-id="9d15c-110">选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="9d15c-110">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="9d15c-111">默认情况下， **清单** 窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="9d15c-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="9d15c-113">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="9d15c-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d15c-114">展开 " **缓存存储** " 部分以查看可用缓存。</span><span class="sxs-lookup"><span data-stu-id="9d15c-114">Expand the **Cache Storage** section to view available caches.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-cache-storage.msft.png":::
       <span data-ttu-id="9d15c-116">可用缓存</span><span class="sxs-lookup"><span data-stu-id="9d15c-116">Available caches</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d15c-117">选择缓存以查看内容。</span><span class="sxs-lookup"><span data-stu-id="9d15c-117">Select a cache to view the contents.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       <span data-ttu-id="9d15c-119">查看缓存的内容</span><span class="sxs-lookup"><span data-stu-id="9d15c-119">View the contents of a cache</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d15c-120">在表下方的部分中选择要查看其 HTTP 标头的资源。</span><span class="sxs-lookup"><span data-stu-id="9d15c-120">Select a resource to view the HTTP headers in the section below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       <span data-ttu-id="9d15c-122">查看资源的 HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="9d15c-122">View the HTTP headers of a resource</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d15c-123">选择 " **预览** " 以查看资源的内容。</span><span class="sxs-lookup"><span data-stu-id="9d15c-123">Choose **Preview** to view the content of a resource.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       <span data-ttu-id="9d15c-125">查看资源的内容</span><span class="sxs-lookup"><span data-stu-id="9d15c-125">View the content of a resource</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9d15c-126">刷新资源</span><span class="sxs-lookup"><span data-stu-id="9d15c-126">Refresh a resource</span></span>  

1.  <span data-ttu-id="9d15c-127">[查看缓存的数据](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="9d15c-127">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="9d15c-128">选择要刷新的资源。</span><span class="sxs-lookup"><span data-stu-id="9d15c-128">Select the resource that you want to refresh.</span></span>  <span data-ttu-id="9d15c-129">DevTools 将突出显示它以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="9d15c-129">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       <span data-ttu-id="9d15c-131">选择要刷新的资源</span><span class="sxs-lookup"><span data-stu-id="9d15c-131">Select a resource to refresh</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d15c-132">选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="9d15c-132">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="9d15c-133">筛选资源</span><span class="sxs-lookup"><span data-stu-id="9d15c-133">Filter resources</span></span>  

1.  <span data-ttu-id="9d15c-134">[查看缓存的数据](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="9d15c-134">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="9d15c-135">使用 " **按路径筛选** " 文本框筛选出与您提供的路径不匹配的任何资源。</span><span class="sxs-lookup"><span data-stu-id="9d15c-135">Use the **Filter by Path** text box to filter out any resources that do not match the path that you provide.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       <span data-ttu-id="9d15c-137">筛选出与指定路径不匹配的资源</span><span class="sxs-lookup"><span data-stu-id="9d15c-137">Filter out resources that do not match the specified path</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9d15c-138">删除资源</span><span class="sxs-lookup"><span data-stu-id="9d15c-138">Delete a resource</span></span>  

1.  <span data-ttu-id="9d15c-139">[查看缓存的数据](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="9d15c-139">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="9d15c-140">选择要删除的资源。</span><span class="sxs-lookup"><span data-stu-id="9d15c-140">Select the resource that you want to delete.</span></span>  <span data-ttu-id="9d15c-141">DevTools 将突出显示它以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="9d15c-141">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       <span data-ttu-id="9d15c-143">选择要删除的资源</span><span class="sxs-lookup"><span data-stu-id="9d15c-143">Select a resource to delete</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d15c-144">选择 " **删除所选** \ (" ![ 删除所选 ][ImageDeleteIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="9d15c-144">Choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="9d15c-145">删除所有缓存数据</span><span class="sxs-lookup"><span data-stu-id="9d15c-145">Delete all cache data</span></span>  

1.  <span data-ttu-id="9d15c-146">打开**应用程序**  >  **清除存储**。</span><span class="sxs-lookup"><span data-stu-id="9d15c-146">Open **Application** > **Clear Storage**.</span></span>  
1.  <span data-ttu-id="9d15c-147">请确保已启用 " **缓存存储** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="9d15c-147">Make sure that the **Cache Storage** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       <span data-ttu-id="9d15c-149">" **缓存存储** " 复选框</span><span class="sxs-lookup"><span data-stu-id="9d15c-149">The **Cache Storage** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d15c-150">选择 " **清除网站数据**"。</span><span class="sxs-lookup"><span data-stu-id="9d15c-150">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       <span data-ttu-id="9d15c-152">" **清除网站数据** " 按钮</span><span class="sxs-lookup"><span data-stu-id="9d15c-152">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9d15c-153">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="9d15c-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "记录网络活动 |Microsoft 文档"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 |MDN"  

> [!NOTE]
> <span data-ttu-id="9d15c-158">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9d15c-158">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9d15c-159">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9d15c-159">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9d15c-161">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9d15c-161">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
