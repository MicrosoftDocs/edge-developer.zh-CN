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

# 查看 Microsoft Edge DevTools 中的应用程序缓存数据  

> [!WARNING]
> [正在从 web 平台中删除][HTMLStandardOfflineWebApplications]应用程序缓存 API。  

本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 [应用程序缓存][MDNWebAPIsWindowApplicationCache] 资源。  

## 查看应用程序缓存数据  

1.  选择 " **源** " 选项卡以打开 " **源** " 面板。  默认情况下， **清单** 窗格是默认打开的。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       **清单**窗格  
    :::image-end:::  

1.  展开 " **应用程序缓存** " 部分，然后选择缓存以查看资源。  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text=""应用程序缓存" 窗格" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       " **应用程序缓存** " 窗格  
    :::image-end:::  

表的每一行表示一个缓存的资源。  

" **类型** " 列表示 [资源的类别][MDNHTMLResourcesInAnApplicationCache]。  

| 类别 | 详细信息 |  
|:--- |:--- |  
| `Explicit` | 此资源已在清单中明确列出。 |  
| `Fallback` | 该 URL 是其他资源的备用 URL。  其他资源的 URL 未在 DevTools 中列出。 |  
| `Master` | `manifest`资源的属性指示缓存是资源的父项。 |  
| `Network` | 指定资源必须来自网络的清单。 |  

<!--todo:  replace "Master" phrasing if possible.  -->  

在表底部有状态图标，指示你的网络连接和 **应用程序缓存**的状态。  **应用程序缓存**可能具有以下状态。  

| State | 详细信息 |  
|:--- |:--- |  
| `CHECKING` | 清单将被提取并检查更新。 |  
| `DOWNLOADING` | 正在将资源添加到缓存。 |  
| `IDLE` | 缓存没有新更改。 |  
| `OBSOLETE` | 正在删除缓存。 |  
| `UPDATEREADY` |  缓存的新版本可用。 |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "脱机 Web 应用程序-HTML 标准"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "应用程序缓存中的资源 |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "ApplicationCache-Web Api |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
