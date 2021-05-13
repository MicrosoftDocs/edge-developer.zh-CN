---
description: 如何从开发人员工具的应用程序面板中查看Microsoft Edge缓存数据。
title: 使用 DevTools Microsoft Edge应用程序缓存数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ec0d1a003e621ecc2220c3eb0d03992bcd8fffa1
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565020"
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
# <a name="view-application-cache-data-with-microsoft-edge-devtools"></a>使用 DevTools Microsoft Edge应用程序缓存数据  

> [!WARNING]
> 应用程序缓存 API [正在从 Web 平台中删除][HTMLStandardOfflineWebApplications]。  

<!--todo: Replace [HTMLStandardOfflineWebApplications] with [WebDevAppcacheRemoval].  -->  

本指南演示如何使用[DevTools Microsoft Edge检查][MicrosoftEdgeDevTools][应用程序缓存][MDNWebAPIsWindowApplicationCache]资源。  

## <a name="view-application-cache-data"></a>查看应用程序缓存数据  

1.  在 DevTools 顶部，选择" **应用程序"** 工具。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       **清单**窗格  
    :::image-end:::  

1.  展开" **应用程序缓存** "部分并选择缓存以查看资源。  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text=""应用程序缓存"窗格" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       " **应用程序缓存"** 窗格  
    :::image-end:::  

表格的每一行都代表一个缓存的资源。  

" **类型** " [列表示资源 的类别][MDNHTMLResourcesInAnApplicationCache]。  

| 类别 | 详细信息 |  
|:--- |:--- |  
| `Explicit` | 此资源在清单中显式列出。 |  
| `Fallback` | URL 是另一个资源的回退。  其他资源的 URL 未在 DevTools 中列出。 |  
| `Master` | `manifest`资源上的 属性指示缓存是资源的父项。 |  
| `Network` | 清单指定资源必须来自网络。 |  

<!--todo:  replace "Master" phrasing if possible.  -->  

在表底部有状态图标，指示网络连接和应用程序缓存 **的状态**。  应用程序 **缓存** 可能具有以下状态。  

| State | 详细信息 |  
|:--- |:--- |  
| `CHECKING` | 正在提取清单并检查更新。 |  
| `DOWNLOADING` | 资源将添加到缓存中。 |  
| `IDLE` | 缓存没有新的更改。 |  
| `OBSOLETE` | 正在删除缓存。 |  
| `UPDATEREADY` |  提供新版本的缓存。 |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "脱机 Web 应用程序 - HTML Standard"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "应用程序缓存缓存中的|MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web API |MDN"  

[WebDevAppcacheRemoval]: https://web.dev/appcache-removal "准备 AppCache 删除|web.dev"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
