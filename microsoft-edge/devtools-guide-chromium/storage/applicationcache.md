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





# 查看 Microsoft Edge DevTools 中的应用程序缓存数据   



> [!WARNING]
> [正在从 web 平台中删除][HTMLStandardOfflineWebApplications]应用程序缓存 API。  

本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]检查[应用程序缓存][MDNWebAPIsWindowApplicationCache]资源。  

## 查看应用程序缓存数据   

1.  选择 "**源**" 选项卡以打开 "**源**" 面板。  默认情况下，**清单**窗格是默认打开的。  
    
    > ##### 图 1  
    > 清单窗格  
    > ![清单窗格][ImageManifestPane]  

1.  展开 "**应用程序缓存**" 部分，然后单击缓存以查看资源。  
    
    > ##### 图 2  
    > "应用程序缓存" 窗格  
    > !["应用程序缓存" 窗格][ImageApplicationCachePane]  

表的每一行表示一个缓存的资源。  

"**类型**" 列表示[资源的类别][MDNHTMLResourcesInAnApplicationCache]。  

| 类型 | 详细信息 |  
|:--- |:--- |  
| `Explicit` | 此资源已在清单中明确列出。 |  
| `Fallback` | 该 URL 是其他资源的备用 URL。  其他资源的 URL 未在 DevTools 中列出。 |  
| `Master` | `manifest`资源上的属性指示此缓存是资源的父项。 |  
| `Network` | 指定此资源必须来自网络的清单。 |  

在表底部有状态图标，指示你的网络连接和应用程序缓存的状态。  应用程序缓存可能具有以下状态。  

| State | 详细信息 |  
|:--- |:--- |  
| `CHECKING` | 清单将被提取并检查更新。 |  
| `DOWNLOADING` | 正在将资源添加到缓存。 |  
| `IDLE` | 缓存没有新更改。 |  
| `OBSOLETE` | 正在删除缓存。 |  
| `UPDATEREADY` |  缓存的新版本可用。 |  

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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
