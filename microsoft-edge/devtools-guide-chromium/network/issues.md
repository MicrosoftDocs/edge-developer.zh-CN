---
description: 了解如何在 Microsoft Edge DevTools 的网络面板中检测网络问题。
title: 网络问题指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 4713dc252d428abbf5b60ee5f74a7316a102dab6
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125375"
---
<!-- Copyright Kayce Basques and Jonathan Garbee

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# 网络问题指南  

本指南介绍如何在 Microsoft Edge DevTools 的 "网络" 面板中检测网络问题或优化机会。  

请参阅 [入门][NetworkPerformance] 了解 **网络** 面板的基础知识。  

## 已排队或已停止的请求  

**症状**  

同时下载六个请求。  之后，一系列请求将排队或停止。  当前六个请求中的一个完成时，队列中的请求之一将开始。  

在下图中的 **瀑布** 图中，资源的前六个请求 `edge-iconx1024.msft.png` 同时开始。  后续请求将停止，直到一个初始六个完成。  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="网络面板中排队或停止的系列的示例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   **网络**面板中排队或停止的系列的示例  
:::image-end:::  

**原因**  

在单个域上发出的请求过多。  在 HTTP/1.0 或 HTTP/1.1 连接上，Microsoft Edge 允许每个主机最多同时有6个 TCP 连接。  

**固定**  

*   如果必须使用 HTTP/1.0 或 HTTP/1.1，则实现域 sharding。  
*   使用 HTTP/2。  请勿将域 sharding 与 HTTP/2 配合使用。  
*   删除或推迟不必要的请求，以便提前下载关键请求。  
    
## 在 TTFB) 的第一字节 (时间较慢  

**症状**  

一个请求花费了很长时间等待接收来自服务器的第一个字节。  

在下图中， **瀑布** 图中的长绿条指示请求已等待很长时间。  这是通过使用配置文件来限制网络速度和增加延迟而进行模拟的。  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="网络面板中排队或停止的系列的示例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   在第一个字节时间较慢的请求示例  
:::image-end:::  

**原因**  

*   客户端和服务器之间的连接速度较慢。  
*   服务器响应速度较慢。  在本地托管服务器，以确定它是较慢的连接还是服务器。  如果您在访问本地服务器时仍有较慢的第一个字节 \ (TTFB \ ) ，则服务器速度较慢。  
    
**固定**  

*   如果连接速度较慢，请考虑在 CDN 上托管你的内容或更改托管提供商。  
*   如果服务器速度较慢，请考虑优化数据库查询、实现缓存或修改服务器配置。  
    
## 缓慢的内容下载  

**症状**  

下载请求需要较长时间。  

在下图中，在 "瀑布" 旁边的 " **瀑布** 图" 中，长的蓝条表示下载时间较长。  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="网络面板中排队或停止的系列的示例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   需要很长时间才能下载的请求的示例  
:::image-end:::  

**原因**  

*   客户端和服务器之间的连接速度较慢。  
*   正在下载大量内容。  
    
**固定**  

*   请考虑在 CDN 上托管你的内容或更改托管提供商。  
*   通过优化您的请求发送更少的字节。  
    
<!--   ## Contribute knowledge  

Do you have a network issue that should be added to this guide?  

*   Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].  
*   Choose **Send Feedback** \(![Send Feedback][ImageSendFeedbackIcon]\) in the DevTools or select `Alt`+`Shift`+`I` \(Windows, Linux\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.  
*   [Open an issue][WebFundamentalsIssue] on the docs repo.  -->  
    
## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageSendFeedbackIcon]: ../media/smile-icon.msft.png  

<!-- links -->  

[NetworkPerformance]: ./index.md "检查 Microsoft Edge DevTools 中的网络活动 |Microsoft 文档"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新问题 - MicrosoftDocs/edge-developer"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/network/issues) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Jonathan Garbee][JonathanGarbee] \ (Google Developer for Web ) 技术。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
