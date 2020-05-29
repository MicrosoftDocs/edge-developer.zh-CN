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





# 查看 Microsoft Edge DevTools 中的缓存数据   



本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]检查[缓存][MDNCache]数据。  

如果您尝试检查[HTTP 缓存][MDNHTTPCaching]数据，这不是您所需的指南。  
在**网络日志**的 "**大小**" 列中查找信息。  请参阅[记录网络活动][DevtoolsNetworkLogActivity]。  

## 查看缓存数据   

1.  选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。  默认情况下，**清单**窗格是默认打开的。  
    
    > ##### 图 1  
    > 清单窗格  
    > ![清单窗格][ImageManifestPane]  

1.  展开 "**缓存存储**" 部分以查看可用缓存。  
    
    > ##### 图 2  
    > 可用缓存  
    > ![可用缓存][ImageCache]  

1.  选择缓存以查看内容。  
    
    > ##### 图 3  
    > 查看缓存的内容  
    > ![查看缓存的内容][ImageCacheView]  

1.  在表下方的部分中选择要查看其 HTTP 标头的资源。  
    
    > ##### 图 4  
    > 查看资源的 HTTP 标头  
    > ![查看资源的 HTTP 标头][ImageViewCacheResource]  

1.  选择 "**预览**" 以查看资源的内容。  
    
    > ##### 图 5  
    > 查看资源的内容  
    > ![查看资源的内容][ImageCacheContent]  

## 刷新资源   

1.  [查看缓存的数据](#view-cache-data)。  
1.  选择要刷新的资源。  DevTools 将突出显示它以指示它已选中。  
    
    > ##### 图 6  
    > 选择资源  
    > ![选择资源][ImageCacheSelected]  

1.  选择 "**刷新** ![ 刷新" ][ImageRefreshIcon] 。  

## 筛选资源   

1.  [查看缓存的数据](#view-cache-data)。  
1.  使用 "**按路径筛选**" 文本框筛选出与您提供的路径不匹配的任何资源。  
    
    > ##### 图 7  
    > 筛选出与指定路径不匹配的资源  
    > ![筛选出与指定路径不匹配的资源][ImageCacheFilter]  

## 删除资源   

1.  [查看缓存的数据](#view-cache-data)。  
1.  选择要删除的资源。  DevTools 将突出显示它以指示它已选中。  
    
    > ##### 图 8  
    > 选择资源  
    > ![选择资源][ImageCacheSelected2]  

1.  选择 "**删除**所选 ![ 删除" ][ImageDeleteIcon] 。  

## 删除所有缓存数据   

1.  打开**应用程序**  >  **清除存储**。  
1.  请确保已启用 "**缓存存储**" 复选框。  
    
    > ##### 图 9  
    > "**缓存存储**" 复选框  
    > !["缓存存储" 复选框][ImageCacheCheckbox]  

1.  选择 "**清除网站数据**"。  
    
    > ##### 图 10  
    > "**清除网站数据**" 按钮  
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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cache)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
