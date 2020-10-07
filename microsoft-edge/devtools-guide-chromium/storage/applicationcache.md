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

# View Application Cache data with Microsoft Edge DevTools  

> [!WARNING]
> The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].  

This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.  

## View Application Cache data  

1.  Select the **Sources** tab to open the **Sources** panel.  The **Manifest** pane usually opens by default.  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-manifest.msft.png":::
       The **Manifest** pane  
    :::image-end:::  

1.  Expand the **Application Cache** section and choose a cache to view the resources.  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       The **Application Cache** pane  
    :::image-end:::  

Each row of the table represents a cached resource.  

The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].  

| Category | Details |  
|:--- |:--- |  
| `Explicit` | This resource was explicitly listed in the manifest. |  
| `Fallback` | The URL is a fallback for another resource.  The URL of the other resource is not listed in DevTools. |  
| `Master` | The `manifest` attribute on the resource indicates that the cache is the parent of the resource. |  
| `Network` | The manifest specified that the resource must come from the network. |  

<!--todo:  replace "Master" phrasing if possible.  -->  

At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.  The **Application Cache** may have the following states.  

| State | Details |  
|:--- |:--- |  
| `CHECKING` | The manifest is being fetched and checked for updates. |  
| `DOWNLOADING` | Resources are being added to the cache. |  
| `IDLE` | The cache has no new changes. |  
| `OBSOLETE` | The cache is being deleted. |  
| `UPDATEREADY` |  A new version of the cache is available. |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer Tools | Microsoft Docs"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "Offline Web applications - HTML Standard"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "Resources in an application cache | MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web APIs | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
