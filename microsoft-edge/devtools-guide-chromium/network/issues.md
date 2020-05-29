---
title: 网络问题指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 018a6ef89242d55cefaa974641be456f4501c557
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611803"
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

请参阅[入门][NetworkPerformance]了解网络面板的基础知识。  

## 已排队或已停止的请求   

### 症状  

同时下载六个请求。  之后，一系列请求将排队或停止。  当前六个请求中的一个完成时，队列中的请求之一将开始。  

在[图 1](#figure-1)的**瀑布**图中，资源的前六个请求 `edge-iconx1024.msft.png` 同时开始。  后续请求将停止，直到一个初始六个完成。  

> ##### 图 1  
> 网络面板中排队或停止的系列的示例  
> ![网络面板中排队或停止的系列的示例][ImageStalled]  

### 原因  

在单个域上发出的请求过多。  在 HTTP/1.0 或 HTTP/1.1 连接上，Microsoft Edge 允许每个主机最多同时有6个 TCP 连接。  

### 固定  

*   如果必须使用 HTTP/1.0 或 HTTP/1.1，则实现域 sharding。  
*   使用 HTTP/2。  请勿将域 sharding 与 HTTP/2 配合使用。  
*   删除或推迟不必要的请求，以便提前下载关键请求。  

## 将时间降低到第一个字节（TTFB）   

### 症状  

一个请求花费了很长时间等待接收来自服务器的第一个字节。  

在[图 2](#figure-2)中，**瀑布**图中的长绿条指示请求已等待很长时间。  这是通过使用配置文件来限制网络速度和增加延迟而进行模拟的。  

> ##### 图 2  
> 在第一个字节时间较慢的请求示例  
> ![在第一个字节时间较慢的请求示例][ImageSlowTimeToFirstByte]  

### 原因  

*   客户端和服务器之间的连接速度较慢。  
*   服务器响应速度较慢。  在本地托管服务器，以确定它是较慢的连接还是服务器。  如果您在访问本地服务器时仍遇到较慢的第一个字节 \ （TTFB \），则服务器速度较慢。  

### 固定  

*   如果连接速度较慢，请考虑在 CDN 上托管你的内容或更改托管提供商。  
*   如果服务器速度较慢，请考虑优化数据库查询、实现缓存或修改服务器配置。  

## 缓慢的内容下载   

### 症状  

下载请求需要较长时间。  

在[图 3](#figure-3)中，在 "瀑布" 旁边的 "**瀑布**图" 中，屏幕上的长蓝条表示下载时间较长。  

> ##### 图 3  
> 需要很长时间才能下载的请求的示例  
> ![需要很长时间才能下载的请求的示例][ImageSlowContentDownload]  

### 原因  

*   客户端和服务器之间的连接速度较慢。  
*   正在下载大量内容。  

### 固定  

*   请考虑在 CDN 上托管你的内容或更改托管提供商。  
*   通过优化您的请求发送更少的字节。  

## 参与知识  

是否有网络问题应添加到本指南？  

*   向[@EdgeDevTools][MicrosoftEdgeTweet]发送 tweet。  
*   选择 "**发送反馈** ![ ][ImageSendFeedbackIcon] " 在 DevTools 中发送反馈，或按 `Alt` + `Shift` + `I` \ （Windows \）或 `Option` + `Shift` + `I` \ （macOS \）提供反馈或功能请求。  
*   在 "文档" 存储库中[打开一个问题][WebFundamentalsIssue]。  

<!--   -->  



<!-- image links -->  

[ImageSendFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/media/smile-icon.msft.png  

[ImageStalled]: /microsoft-edge/devtools-guide-chromium/media/network-network-disabled-cache-resources-queue.msft.png "图1：网络面板中已排队或停止使用的系列的示例"  
[ImageSlowTimeToFirstByte]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-using-dial-up-profile.msft.png "图2：较慢时间到第一个字节的请求示例"  
[ImageSlowContentDownload]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-edge-devtools.msft.png "图3：下载需要很长时间的请求的示例"  

<!-- links -->  

[NetworkPerformance]: /microsoft-edge/devtools-guide-chromium/network/index "检查 Microsoft Edge DevTools 中的网络活动"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新问题-MicrosoftDocs/edge-开发人员"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/issues)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）和[Jonathan Garbee][JonathanGarbee] \ （Google Developer for Web 技术）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
