---
description: 从 Internet Explorer 将用户移动到 Microsoft Edge
title: 从 Internet Explorer 将用户移动到 Microsoft Edge
author: MSEdgeTeam
ms.date: 11/06/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台、internet explorer
ms.openlocfilehash: 2e1488359e405247e290ad8f6300c480a7e20af6
ms.sourcegitcommit: 6ef48c8cda392c6bf8217cff5f696ac620d10739
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163205"
---
# 从 Internet Explorer 将用户移动到 Microsoft Edge 

许多现代网站的设计与 Internet Explorer 不兼容 (IE \ ) 。  当 IE 用户访问不兼容的公共网站时，用户可能会收到一条消息。  该消息表明网站与浏览器不兼容。  消息显示后，用户应手动切换到新式浏览器。  为了最大程度地减少中断（从版本84开始），Microsoft Edge 支持自动重定向用户的新功能。  当 IE 用户导航到与 IE 不兼容的网站时，Windows 会自动将用户重定向到 Microsoft Edge。  若要查看列表中的网站，请导航到 " [需要 Microsoft Edge 列表][MicrosoftEdgeNeededgeV1]"。

本文介绍以下概念。  

*   重定向的用户体验  
*   如何请求列表更新  
    
## 为什么将网站添加到 IE 兼容性列表？  

IE 兼容性列表仅在发生以下操作时才会添加网站。  

*   向 IE 用户显示一条消息，建议用户应出于兼容性原因使用其他浏览器。  
*   将网站添加到 IE 兼容性列表的所有者请求。  
    
## 更新 IE 兼容性列表  

IE 兼容性列表是 [microsoft.com][MicrosoftOfficialHome]上的一个 XML 文件。  该列表会定期更新，以响应用户和网站开发人员请求以添加或删除网站。  对列表的更新会自动下载到用户计算机。  

将以下信息通过电子邮件发送到 [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] ，以便在 IE 兼容性列表中添加或删除您的网站。    

*   所有者姓名  
*   公司标题  
*   电子邮件地址  
*   公司名称  
*   街道地址  
*   网站地址  
    
> [!NOTE]
> IE 兼容性列表设计为仅使用公共网站。  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "向 ietoedge@microsoft.com 发送电子邮件"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft 官方家庭版"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "需要 Microsoft Edge 列表 v1 xml |Microsoft Edge"  
