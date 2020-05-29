---
title: 通过 Microsoft Edge DevTools 调试后台服务
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0ac2a057307a939069cbb3b48ecd38c9de71e5db
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581829"
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





# 通过 Microsoft Edge DevTools 调试后台服务   



Microsoft Edge DevTools 的 "**后台服务**" 部分是用于 JavaScript api 的工具集合，可使你的网站即使在用户未打开网站时也可以发送和接收更新。  
后台服务在功能上类似于 [后台进程] [WikiBackgroundProcess]。  
Microsoft Edge DevTools 将以下每个 Api 视为后台服务：  

*   [后台获取](#background-fetch)  
*   [后台同步](#background-sync)  
*   [通知](#notifications)  
*   [推送邮件](#push-messages)  

Microsoft Edge DevTools 可以记录3天的后台服务事件，即使 DevTools 未打开也是如此。  
这可以帮助你确保按预期发送和接收事件。  你还可以检查每个事件的详细信息。  

> ##### 图 1  
> 在 "推送消息" 窗格中查看事件的详细信息  
> ![在 "推送消息" 窗格中查看事件的详细信息][PushDetails]  

## 后台获取   

*后台获取 API** 使**服务工作者**能够以后台服务的形式可靠地下载大型资源（如电影或播客）。  若要在3天内记录后台提取事件（即使 DevTools 未打开）：  

<!--Todo: add background fetch api section when available -->  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 "**应用程序**" 面板。  
1.  打开 "**后台获取**" 窗格。  
    
    > ##### 图 2  
    > "背景获取" 窗格  
    > !["背景获取" 窗格][FetchEmpty]  
    
1.  单击 "**录制** ![ 记录" ][ImageRecordIcon] 。  
   触发某些后台获取活动后，DevTools 会将事件记录到表中。  
    
    > ##### 图 3  
    > 后台提取窗格中的事件日志  
    > ![后台提取窗格中的事件日志][FetchLog]  
    
1.  单击某个事件可在表下方的空间中查看其详细信息。  
    
    > ##### 图 4  
    > 在 "后台提取" 窗格中查看事件的详细信息  
    > ![在 "后台提取" 窗格中查看事件的详细信息][FetchDetails]  

## 后台同步   

**后台同步 API**使脱机**服务工作人员**能够在服务器重新建立可靠的 internet 连接后向其发送数据。  若要记录3天的后台同步事件（即使 DevTools 未打开）：  

<!--Todo: add background sync api section when available -->  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 "**应用程序**" 面板。  
1.  打开 "**后台同步**" 窗格。  
    
    > ##### 图 5  
    > "后台同步" 窗格  
    > !["后台同步" 窗格][SyncEmpty]  
    
1.  单击 "**录制** ![ 记录" ][ImageRecordIcon] 。  
   触发某些后台同步活动后，DevTools 会将事件记录到表中。  
    
    > ##### 图 6  
    > "后台同步" 窗格中的事件日志  
    > !["后台同步" 窗格中的事件日志][SyncLog]  
    
1.  单击某个事件可在表下方的空间中查看其详细信息。  
    
    > ##### 图 7  
    > 在 "后台同步" 窗格中查看事件的详细信息  
    > ![在 "后台同步" 窗格中查看事件的详细信息][SyncDetails]  
    
## 通知 

**服务工作人员**从服务器收到[推送消息][MDNPush]后，服务工作人员使用[通知 API][MDNNotifications]将数据显示给用户。  要记录3天的通知（即使 DevTools 未打开）：  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 "**应用程序**" 面板。  
1.  打开 "**通知**" 窗格。  
    
    > ##### 图 8  
    > "通知" 窗格  
    > !["通知" 窗格][NotificationsEmpty]  
    
1.  单击 "**录制** ![ 记录" ][ImageRecordIcon] 。  
   触发某些通知活动后，DevTools 会将事件记录到表中。  
    
    > ##### 图 9  
    > "通知" 窗格中的事件日志  
    > !["通知" 窗格中的事件日志][NotificationsLog]  
    
1.  单击某个事件可在表下方的空间中查看其详细信息。  
    
    > ##### 图 10  
    > 在 "通知" 窗格中查看事件的详细信息  
    > ![在 "通知" 窗格中查看事件的详细信息][NotificationsDetails]  
    
## 推送邮件 

若要向用户显示推送通知，**服务工作人员**必须首先使用[推送消息 API][MDNPush]从服务器接收数据。  当服务工作者准备好显示通知时，它将使用[通知 API][MDNNotifications]。  若要在3天内记录推送消息，即使在 DevTools 未打开的情况下也是如此：  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开 "**应用程序**" 面板。  
1.  打开 "**推送消息**" 窗格。  
    
    > ##### 图 11  
    > "推送消息" 窗格  
    > !["推送消息" 窗格][PushEmpty]  

1.  单击 "**录制** ![ 记录" ][ImageRecordIcon] 。  
    触发某些推送消息活动后，DevTools 会将事件记录到表中。  
    
    > ##### 图 12  
    > "推送消息" 窗格中的事件日志  
    > !["推送消息" 窗格中的事件日志][PushLog]  

1.  单击某个事件可在表下方的空间中查看其详细信息。  
    
    > ##### 图 13  
    > 在 "推送消息" 窗格中查看事件的详细信息  
    > ![在 "推送消息" 窗格中查看事件的详细信息][PushDetails2]  
    
 



<!-- image links -->  

[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png  

[PushDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging.msft.png "图1：在 "推送消息" 窗格中查看事件的详细信息"  
[FetchEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-fetch-empty.msft.png "图2：背景获取窗格"  
[FetchLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-fetch.msft.png "图3：后台提取窗格中的事件日志"  
[FetchDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-fetch-details.msft.png "图4：在 "后台获取" 窗格中查看事件的详细信息"  
[SyncEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-sync-empty.msft.png "图5： "后台同步" 窗格"  
[SyncLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-sync.msft.png "图6： "后台同步" 窗格中的事件日志"  
[SyncDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-sync-details.msft.png "图7：在 "后台同步" 窗格中查看事件的详细信息"  
[NotificationsEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-notifications-empty.msft.png "图8： "通知" 窗格"  
[NotificationsLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-notifications.msft.png "图9： "通知" 窗格中的事件日志"  
[NotificationsDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-notifications-details.msft.png "图10：在 "通知" 窗格中查看事件的详细信息"  
[PushEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging-empty.msft.png "图11： "推送消息" 窗格"  
[PushLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging.msft.png "图12： "推送消息" 窗格中的事件日志"  
[PushDetails2]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging-details.msft.png "图13：在 "推送消息" 窗格中查看事件的详细信息"  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open.md "打开 Microsoft Edge （Chromium）开发人员工具"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]： https://en.wikipedia.org/wiki/Background_process "后台进程-维基百科"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  
[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
