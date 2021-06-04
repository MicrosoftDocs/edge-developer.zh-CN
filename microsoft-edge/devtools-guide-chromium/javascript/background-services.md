---
description: 如何使用 Microsoft Edge DevTools 调试后台提取、后台同步、通知和推送通知。
title: 使用 Microsoft Edge DevTools 调试后台服务
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 4f5f52bcde976cea8432e3160a792438e5603e21
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564194"
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

Microsoft Edge DevTools 的**后台服务**部分是 JavaScript API 的一个工具集合，使你的网站能够在用户未打开网站时发送和接收更新。  
后台服务在功能上类似于 [后台进程][WikiBackgroundProcess]。  
Microsoft Edge DevTools 将以下每个 API 都作为后台服务：  

*   [后台提取](#background-fetch)  
*   [后台同步](#background-sync)  
*   [通知](#notifications)  
*   [推送消息](#push-messages)  
    
Microsoft Edge DevTools 可能会记录后台服务事件 3 天，即使 DevTools 未打开。  
后台服务事件日志可帮助你确保事件已按预期发送和接收。  你还可以检查每个事件的详细信息。  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="推送消息窗格" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   “**推送消息**”窗格  
:::image-end:::  

## <a name="background-fetch"></a>后台提取  

**后台提取 API**使**服务工作进程**能够可靠地下载大型资源（如电影或播客）作为后台服务。  若要记录后台提取事件 3 天，即使 DevTools 未打开：  

<!--Todo: add background fetch api section when available -->  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开“**应用程序**”工具。  
1.  打开“**后台提取**”面板。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="后台提取面板" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       “**后台提取**”面板  
    :::image-end:::  
    
1.  选择“**记录**”\(“![记录](../media/record-icon.msft.png)”\)。  
   触发某些后台提取活动后，DevTools 记录事件到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="后台提取面板中的事件日志" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       “**后台提取**”面板中的事件日志  
    :::image-end:::  
    
1.  选择一个事件以在表下方的空白区域查看其详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="在后台提取窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       在“**后台提取**”窗格中查看事件的详细信息  
    :::image-end:::  
    
## <a name="background-sync"></a>后台同步  

**后台同步 API**使脱机**服务工作进程**能够在重新建立可靠 Internet 连接后向服务器发送数据。  若要记录后台同步事件 3 天，即使 DevTools 未打开：  

<!--Todo: add background sync api section when available -->  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开“**应用程序**”工具。  
1.  打开“**后台同步**”窗格。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text="后台同步窗格" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       “**后台同步**”窗格  
    :::image-end:::  
    
1.  选择“**记录**”\(“![记录](../media/record-icon.msft.png)”\)。  
   触发某些后台同步活动后，DevTools 记录事件到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="后台同步窗格中的事件日志" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       “**后台同步**”窗格中的事件日志  
    :::image-end:::  
    
1.  选择一个事件以在表下方的空白区域查看其详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="在后台同步窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       在“**后台同步**”窗格中查看事件的详细信息  
    :::image-end:::  
    
## <a name="notifications"></a>通知  

**服务工作进程**从服务器接收一条[推送消息][MDNPush]后，服务工作进程使用[通知 API][MDNNotifications]向用户显示数据。  若要记录通知 3 天，即使 DevTools 未打开：  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开“**应用程序**”工具。  
1.  打开“**通知**”窗格。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="通知窗格" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       “**通知**”窗格  
    :::image-end:::  
    
1.  选择“**记录**”\(“![记录](../media/record-icon.msft.png)”\)。  
   触发某些通知活动后，DevTools 记录事件到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="通知窗格中的事件日志" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       “**通知**”窗格中的事件日志  
    :::image-end:::  
    
1.  选择一个事件以在表下方的空白区域查看其详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="在通知窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       在“**通知**”窗格中查看事件的详细信息  
    :::image-end:::  
    
## <a name="push-messages"></a>推送消息  

若要向用户显示推送通知，**服务工作进程**必须先使用[推送消息 API][MDNPush]从服务器接收数据。  当服务工作进程准备好显示通知时，它将使用[通知 API][MDNNotifications]。  若要记录推送消息 3 天，即使 DevTools 未打开：  

1.  [打开 DevTools][OpenDevTools]。  
1.  打开“**应用程序**”工具。  
1.  打开“**推送消息**”面板。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="打开推送消息窗格" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       打开“**推送消息**”窗格  
    :::image-end:::  
    
1.  选择“**记录**”\(“![记录](../media/record-icon.msft.png)”\)。  
    触发某些推送消息活动后，DevTools 记录事件到表中。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="推送消息窗格中的事件日志" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       “**推送消息**”窗格中的事件日志  
    :::image-end:::  
    
1.  选择一个事件以在表下方的空白区域查看详细信息。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="在推送消息窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       在“**推送消息**”窗格中查看事件的详细信息  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open/index.md "打开 Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API | MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API | MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process “后台进程 - Wikipedia”  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  
[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
