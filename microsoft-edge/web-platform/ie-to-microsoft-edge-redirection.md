---
description: 从 Internet Explorer 将用户移动到 Microsoft Edge
title: 从 Internet Explorer 将用户移动到 Microsoft Edge
author: MSEdgeTeam
ms.date: 11/13/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台、internet explorer
ms.openlocfilehash: 872bd5ec52f471e4958ef7354c046ec30f1ba72e
ms.sourcegitcommit: 62258ce0ef469948ca8af42141d02aa9719243f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168359"
---
# 从 Internet Explorer 将用户移动到 Microsoft Edge  

许多现代网站的设计与 Internet Explorer 不兼容 (IE \ ) 。  当 IE 用户访问不兼容的公共网站时，用户可能会收到一条消息。  该消息表明网站与浏览器不兼容。  消息显示后，用户应手动切换到新式浏览器。  为了最大程度地减少中断（从版本84开始），Microsoft Edge 支持自动重定向用户的新功能。  当 IE 用户导航到与 IE 不兼容的网站时，Windows 会自动将用户重定向到 Microsoft Edge。  若要查看列表中的网站，请导航到 " [需要 Microsoft Edge 列表][MicrosoftEdgeNeededgeV1]"。

本文介绍以下概念。  

*   网站添加到列表的原因  
*   重定向的用户体验  
*   请求列表更新  
    
## 为什么将网站添加到 IE 兼容性列表？  

IE 兼容性列表仅在发生以下操作时才会添加网站。  

*   向 IE 用户显示一条消息，建议用户应出于兼容性原因使用其他浏览器。  
*   将网站添加到 IE 兼容性列表的所有者请求。  

## 重定向体验

在重定向到 Microsoft Edge 时，将在下一个屏幕截图中显示该用户的一次性对话框。  该对话框向用户提供以下信息。  

*   它介绍了重定向网站的原因。  
*   它提示用户同意将浏览数据和首选项从 IE 复制到 Microsoft Edge。  

:::row:::
   :::column span="":::
      将导入以下浏览数据。  
      
      *   收藏夹  
      *   密码  
      *   搜索引擎  
      *   打开选项卡  
      *   历史记录  
      *   “设置”  
      *   Cookie  
      *   主页  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/neededge-dialog1.msft.png" alt-text="浏览通知并提示导入数据和首选项" lightbox="../media/neededge-dialog1.msft.png":::
         浏览通知并提示导入数据和首选项  
      :::image-end:::  
   :::column-end:::
:::row-end:::

如果用户不同意选择 "**始终从 Internet Explorer 中的浏览数据和首选项**" 复选框，则用户可以选择 "**继续浏览**   " 以继续浏览会话。  

最后，在每次重定向的地址栏下显示网站不兼容标题。  下图显示了一个网站不兼容标题示例。

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="有关新式网站的通知，并提示将 Microsoft Edge 设置为默认浏览器或浏览 Microsoft Edge" lightbox="../media/neededge-banner.msft.png":::
   有关新式网站的通知，并提示将 Microsoft Edge 设置为默认浏览器或浏览 Microsoft Edge  
:::image-end:::

网站兼容性横幅向用户提供以下详细信息。  

*   建议用户切换到 Microsoft Edge。  
*   提供将 Microsoft Edge 设置为默认浏览器。  
*   为用户提供浏览 Microsoft Edge 的选项。    
    
当网站从 Internet Explorer 重定向到 Microsoft Edge 时，将发生以下操作之一。

*   如果活动 IE 选项卡没有以前的内容，则它将被关闭。  
*   如果 "活动 IE" 选项卡具有以前的内容，它将导航到 [microsoft 支持页面，该页面解释了网站重定向到 Microsoft Edge 的原因][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]。  

> [!NOTE]
> 重定向后，用户可以继续对不在 IE 兼容性列表中的网站使用 IE。  

## 请求对 IE 兼容性列表的更新  

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

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "Internet Explorer | 无法使用您尝试访问的网站Microsoft Office 支持"  
