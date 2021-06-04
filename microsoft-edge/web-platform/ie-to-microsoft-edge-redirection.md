---
description: 将用户从Microsoft Edge移动到Internet Explorer
title: 将用户从Microsoft Edge移动到Internet Explorer
author: MSEdgeTeam
ms.date: 11/13/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， Internet Explorer
ms.openlocfilehash: c2106955ed79bd28dc1f847dee220944bb014689
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461134"
---
# <a name="moving-users-to-microsoft-edge-from-internet-explorer"></a>将用户从Microsoft Edge移动到Internet Explorer  

许多新式网站具有的设计与 Internet Explorer \(IE\) 。  当 IE 用户访问不兼容的公共网站时，用户可能会收到一条消息。  该消息表明该网站与浏览器不兼容。  消息显示后，用户需要手动切换到新式浏览器。  为了最大限度地减少中断，从版本 84 开始，Microsoft Edge支持自动重定向用户的新功能。  当 IE 用户导航到与 IE 不兼容的网站时，Windows自动将用户重定向到Microsoft Edge。  To review the websites on the list， navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].

本文介绍以下概念。  

*   网站添加到列表的原因  
*   重定向的用户体验  
*   请求更新列表  
    
## <a name="why-is-a-website-added-to-the-ie-compatibility-list"></a>为什么将网站添加到 IE 兼容性列表？  

IE 兼容性列表仅在发生以下操作时添加网站。  

*   向 IE 用户显示一条消息，建议出于兼容性原因，用户应使用不同的浏览器。  
*   所有者请求将网站添加到 IE 兼容性列表。  

## <a name="redirection-experience"></a>重定向体验

当重定向到Microsoft Edge时，用户将显示在下一个屏幕截图中的一次对话框。  该对话框为用户提供以下信息。  

*   它说明了重定向网站的原因。  
*   它会提示用户同意将浏览数据和首选项从 IE 复制到 Microsoft Edge。  

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

如果用户未通过选中"始终显示我的浏览数据和首选项Internet Explorer复选框同意，用户可以选择"继续**浏览"** 以继续****   浏览会话。  

最后，网站不兼容横幅将显示在每个重定向的地址栏下。  下图显示了网站不兼容横幅的示例。

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="有关新式网站的通知，并提示将Microsoft Edge设置为默认浏览器或浏览Microsoft Edge" lightbox="../media/neededge-banner.msft.png":::
   有关新式网站的通知，并提示将Microsoft Edge设置为默认浏览器或浏览Microsoft Edge  
:::image-end:::

网站不兼容横幅为用户提供了以下详细信息。  

*   建议用户切换到Microsoft Edge。  
*   要设置为Microsoft Edge浏览器的优惠。  
*   为用户提供浏览Microsoft Edge。    
    
将网站从 Internet Explorer Microsoft Edge 时，将发生以下操作之一。

*   如果活动 IE 选项卡之前没有内容，它将关闭。  
*   如果活动 IE 选项卡之前包含内容，它将导航到 [Microsoft][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]支持页面，说明网站被重定向到 Microsoft Edge 的原因。  

> [!NOTE]
> 重定向后，用户可以继续对不在 IE 兼容性列表中的网站使用 IE。  

## <a name="request-an-update-to-the-ie-compatibility-list"></a>请求更新 IE 兼容性列表  

IE 兼容性列表是上一个 XML [microsoft.com。][MicrosoftOfficialHome]  此列表会定期更新，以响应用户和网站开发人员有关添加或删除网站的请求。  对列表的更新会自动下载到用户计算机。  

通过电子邮件将以下信息 [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] IE 兼容性列表中添加或删除的网站。    

*   所有者名称  
*   公司标题  
*   电子邮件地址  
*   公司名称  
*   街道地址  
*   网站地址  
    
IE 兼容性列表在一周内更新。

> [!NOTE]
> IE 兼容性列表设计为仅适用于公共网站。  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "向用户发送电子邮件 ietoedge@microsoft.com"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft 官方主页"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "需要Microsoft Edge v1 xml 文件|Microsoft Edge"  

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "尝试访问的网站无法与Internet Explorer |Microsoft Office支持"  
