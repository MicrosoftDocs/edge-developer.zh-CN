---
description: 了解如何在 Microsoft Edge DevTools 的网络面板中检测网络问题。
title: 网络问题指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 9b92ca7b759fab80d7d829b31f605ccb8062a816
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439617"
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

# <a name="network-issues-guide"></a>网络问题指南  

本指南显示了如何在 Microsoft Edge DevTools 的网络面板中检测网络问题或优化机会。  

若要了解网络工具**的基础知识**，请导航到"[入门"。][NetworkPerformance]  

## <a name="queued-or-stalled-requests"></a>排队或停止的请求  

**症状**  

同时下载六个请求。  之后，一系列请求将排队或停止。  前六个请求之一完成之后，队列中的一个请求将启动。  

在 **下图的瀑布** 中，资产前六个 `edge-iconx1024.msft.png` 请求同时开始。  后续请求将停止，直到原始六个请求中的一个完成。  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="网络面板中排队或停止的系列的示例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   Network 工具中排队或停止的 **系列** 的示例  
:::image-end:::  

**原因**  

对单个域提出的请求过多。  在 HTTP/1.0 或 HTTP/1.1 连接上，Microsoft Edge 允许每个主机最多同时连接六个 TCP 连接。  

**修复**  

*   如果必须使用 HTTP/1.0 或 HTTP/1.1，则实现域 sharding。  
*   使用 HTTP/2。  不要将域分片与 HTTP/2 一同使用。  
*   删除或延迟不必要的请求，以便之前下载关键请求。  
    
## <a name="slow-time-to-first-byte-ttfb"></a>从 TTFB 文件 (字节)   

**症状**  

请求花费很长时间来等待从服务器接收第一个字节。  

下图中，瀑布中的绿色长条指示请求等待很长时间****。  这是使用配置文件来限制网络速度并添加延迟的模拟。  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="第一个字节时间较慢的请求示例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   第一个字节时间较慢的请求示例  
:::image-end:::  

**原因**  

*   客户端和服务器之间的连接速度很慢。  
*   服务器响应缓慢。  在本地托管服务器，以确定是连接速度慢还是速度慢。  如果访问本地服务器时，仍 (到第一字节 \ (TTFB\) ，则服务器速度很慢。  
    
**修复**  

*   如果连接速度较慢，请考虑在 CDN 上托管内容或更改宿主提供商。  
*   如果服务器运行缓慢，请考虑优化数据库查询、实现缓存或修改服务器配置。  
    
## <a name="slow-content-download"></a>慢速内容下载  

**症状**  

下载请求需要很长时间。  

下图中，瀑布旁的蓝色长条表示下载需要**** 很长时间。  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="需要很长时间下载的请求示例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   需要很长时间下载的请求示例  
:::image-end:::  

**原因**  

*   客户端和服务器之间的连接速度很慢。  
*   正在下载大量内容。  
    
**修复**  

*   请考虑在 CDN 上托管内容或更改宿主提供商。  
*   通过优化请求发送更少的字节。  
    
<!--   ## Contribute knowledge  

Do you have a network issue that should be added to this guide?  

*   Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].  
*   Choose **Send Feedback** \(![Send Feedback](../media/smile-icon.msft.png)\) in the DevTools or select `Alt`+`Shift`+`I` \(Windows, Linux\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.  
*   [Open an issue][WebFundamentalsIssue] on the docs repo.  -->  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[NetworkPerformance]: ./index.md "检查 Microsoft Edge DevTools |Microsoft Docs"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新问题 - MicrosoftDocs/edge-developer"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/network/issues)由位于此处的一位用户创作，作者是 (技术编写者[，Chrome][KayceBasques] DevTools \& Lighthouse\) 和[一个][JonathanGarbee]Google Developer Expert for Web Technology\) （该链接可能 (Google Developer Expert for Web Technology\) ）。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
