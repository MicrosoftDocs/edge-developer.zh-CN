---
description: 如何从 Microsoft Edge DevTools 的应用程序面板查看缓存数据。
title: 使用 Microsoft Edge DevTools 查看缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 7e0523e3293bbdafa9c3575344714da708fffe62
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397536"
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

# <a name="view-cache-data-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 查看缓存数据  

本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 [缓存][MDNCache] 数据。  

如果您尝试检查 HTTP [缓存][MDNHTTPCaching] 数据，则这不是您需要的指南。  在网络日志的 **"大小** "列中 **查找信息**。  导航到["记录网络活动"。][DevtoolsNetworkLogActivity]  

## <a name="view-cache-data"></a>查看缓存数据  

1.  选择 **"应用程序"** 选项卡以打开 **应用程序** 面板。  清单 **窗格** 通常默认打开。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       清单**窗格**  
    :::image-end:::  
    
1.  展开 **"缓存存储** "部分以查看可用的缓存。  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="可用缓存" lightbox="../media/storage-application-cache-storage.msft.png":::
       可用缓存  
    :::image-end:::  
    
1.  选择缓存以查看内容。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="查看缓存的内容" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       查看缓存的内容  
    :::image-end:::  
    
1.  选择一个资源以查看表下部分中 HTTP 标头。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="查看资源的 HTTP 标头" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       查看资源的 HTTP 标头  
    :::image-end:::  
    
1.  选择 **"** 预览"以查看资源的内容。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="查看资源的内容" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       查看资源的内容  
    :::image-end:::  
    
## <a name="refresh-a-resource"></a>刷新资源  

1.  [查看缓存的数据](#view-cache-data)。  
1.  选择要刷新的资源。  DevTools 突出显示它以指示已选择它。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="选择要刷新的资源" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       选择要刷新的资源  
    :::image-end:::  
    
1.  Choose **Refresh** \ (![ Refresh ][ImageRefreshIcon] \) .  
    
## <a name="filter-resources"></a>筛选资源  

1.  [查看缓存的数据](#view-cache-data)。  
1.  使用 **"按路径筛选** "文本框筛选出与提供的路径不匹配的任何资源。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="筛选出与指定路径不匹配的资源" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       筛选出与指定路径不匹配的资源  
    :::image-end:::  
    
## <a name="delete-a-resource"></a>删除资源  

1.  [查看缓存的数据](#view-cache-data)。  
1.  选择要删除的资源。  DevTools 突出显示它以指示已选择它。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="选择要删除的资源" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       选择要删除的资源  
    :::image-end:::  
    
1.  Choose **Delete Selected** \ (Delete Selected ![ ][ImageDeleteIcon] \) .  
    
## <a name="delete-all-cache-data"></a>删除所有缓存数据  

1.  打开**应用程序**  >  **清除存储**。  
1.  确保已启用 **"缓存存储"** 复选框。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text=""缓存存储"复选框" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       " **缓存存储"** 复选框  
    :::image-end:::  
    
1.  选择 **"清除网站数据"。**  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text=""清除网站数据"按钮" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       " **清除网站数据"** 按钮  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "记录网络活动|Microsoft Docs"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存|MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
