---
description: 如何使用 Microsoft Edge DevTools 调试后台提取、后台同步、通知和推送通知。
title: 使用 Microsoft Edge DevTools 调试后台服务
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 15023098c547d31bf46bd387f849b365c13b38f6
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439526"
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

# <a name="debug-background-services-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 调试后台服务  

Microsoft **** Edge DevTools 的"后台服务"部分是 JavaScript API 的工具集合，使您的网站能够在用户未打开网站时发送和接收更新。  
后台服务在功能上类似于 [后台进程][WikiBackgroundProcess]。  
Microsoft Edge DevTools 将以下每个 API 都作为后台服务：  

*   [后台提取](#background-fetch)  
*   [后台同步](#background-sync)  
*   [通知](#notifications)  
*   [推送消息](#push-messages)  
    
Microsoft Edge DevTools 可能会将后台服务事件记录 3 天，即使 DevTools 未打开。  
后台服务事件日志可帮助你确保事件已根据预期发送和接收。  您还可以检查每个事件的详细信息。  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text=""推送消息"窗格" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   " **推送消息"** 窗格  
:::image-end:::  

## <a name="background-fetch"></a>后台提取  

后台 **提取 API** 使 **服务工作者** 能够可靠地将大型资源（如电影或播客）下载为后台服务。  若要将后台提取事件记录 3 天，即使 DevTools 未打开：  

<!--Todo: add background fetch api section when available -->  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 **"应用程序"** 工具。  
1.  打开 **"后台提取"** 面板。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="后台提取面板" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       后台 **提取** 面板  
    :::image-end:::  
    
1.  Choose **Record** \ (![ Record ](../media/record-icon.msft.png) \) .  
   触发某些后台提取活动后，DevTools 将事件记录到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="后台提取面板中的事件日志" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       后台提取面板中的 **事件** 日志  
    :::image-end:::  
    
1.  选择一个事件，在表下方的空白区域查看其详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="在"后台提取"窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       在"后台提取"窗格中 **查看事件** 的详细信息  
    :::image-end:::  
    
## <a name="background-sync"></a>后台同步  

后台 **同步 API** 使脱机服务 **工作者能够在** 重新建立可靠的 Internet 连接后向服务器发送数据。  若要将后台同步事件记录 3 天，即使 DevTools 未打开：  

<!--Todo: add background sync api section when available -->  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 **"应用程序"** 工具。  
1.  打开 **"后台同步"** 窗格。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text=""后台同步"窗格" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       " **后台同步"** 窗格  
    :::image-end:::  
    
1.  Choose **Record** \ (![ Record ](../media/record-icon.msft.png) \) .  
   触发某些后台同步活动后，DevTools 将事件记录到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="后台同步窗格中的事件日志" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       后台同步窗格中 **的事件** 日志  
    :::image-end:::  
    
1.  选择一个事件，在表下方的空白区域查看其详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="在"后台同步"窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       在"后台同步"窗格中 **查看事件** 的详细信息  
    :::image-end:::  
    
## <a name="notifications"></a>通知  

在**服务工作者**从服务器收到一[][MDNPush]条推送消息后，服务工作者使用通知[API][MDNNotifications]向用户显示数据。  若要将通知记录 3 天，即使 DevTools 未打开：  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 **"应用程序"** 工具。  
1.  打开通知 **窗格** 。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="通知窗格" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       通知**窗格**  
    :::image-end:::  
    
1.  Choose **Record** \ (![ Record ](../media/record-icon.msft.png) \) .  
   触发一些通知活动后，DevTools 将事件记录到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="通知窗格中的事件日志" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       通知窗格中**的事件日志**  
    :::image-end:::  
    
1.  选择一个事件，在表下方的空白区域查看其详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="在通知窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       在通知窗格中查看 **事件** 的详细信息  
    :::image-end:::  
    
## <a name="push-messages"></a>推送消息  

若要向用户显示推送通知，服务工作者必须先使用**** 推送[消息 API][MDNPush]从服务器接收数据。  当服务工作者准备好显示通知时，它使用 [通知 API][MDNNotifications]。  若要将推送通知记录 3 天，即使 DevTools 未打开：  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 **"应用程序"** 工具。  
1.  打开 **"推送消息"** 面板。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="打开"推送消息"窗格" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       打开 **"推送消息"** 窗格  
    :::image-end:::  
    
1.  Choose **Record** \ (![ Record ](../media/record-icon.msft.png) \) .  
    触发一些推送消息活动后，DevTools 将事件记录到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text=""推送消息"窗格中的事件日志" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       "推送消息"窗格中 **的事件** 日志  
    :::image-end:::  
    
1.  选择一个事件以查看表下方空间的详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="在"推送消息"窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       在"推送消息"窗格中查看 **事件** 的详细信息  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open/index.md "打开 Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]： https://en.wikipedia.org/wiki/Background_process "Background process - Wikipedia"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  
[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
