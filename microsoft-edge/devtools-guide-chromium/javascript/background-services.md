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





# <span data-ttu-id="f4bf7-103">通过 Microsoft Edge DevTools 调试后台服务</span><span class="sxs-lookup"><span data-stu-id="f4bf7-103">Debug Background Services With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="f4bf7-104">Microsoft Edge DevTools 的 "**后台服务**" 部分是用于 JavaScript api 的工具集合，可使你的网站即使在用户未打开网站时也可以发送和接收更新。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-104">The **Background Services** section of Microsoft Edge DevTools is a collection of tools for the JavaScript APIs that enables your website to send and receive updates even when a user does not have your website open.</span></span>  
<span data-ttu-id="f4bf7-105">后台服务在功能上类似于 [后台进程] [WikiBackgroundProcess]。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-105">A background service is functionally similar to a [background process][WikiBackgroundProcess].</span></span>  
<span data-ttu-id="f4bf7-106">Microsoft Edge DevTools 将以下每个 Api 视为后台服务：</span><span class="sxs-lookup"><span data-stu-id="f4bf7-106">Microsoft Edge DevTools considers each of the following APIs to be a background service:</span></span>  

*   [<span data-ttu-id="f4bf7-107">后台获取</span><span class="sxs-lookup"><span data-stu-id="f4bf7-107">Background Fetch</span></span>](#background-fetch)  
*   [<span data-ttu-id="f4bf7-108">后台同步</span><span class="sxs-lookup"><span data-stu-id="f4bf7-108">Background Sync</span></span>](#background-sync)  
*   [<span data-ttu-id="f4bf7-109">通知</span><span class="sxs-lookup"><span data-stu-id="f4bf7-109">Notifications</span></span>](#notifications)  
*   [<span data-ttu-id="f4bf7-110">推送邮件</span><span class="sxs-lookup"><span data-stu-id="f4bf7-110">Push Messages</span></span>](#push-messages)  

<span data-ttu-id="f4bf7-111">Microsoft Edge DevTools 可以记录3天的后台服务事件，即使 DevTools 未打开也是如此。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-111">Microsoft Edge DevTools can log background service events for 3 days, even when DevTools is not open.</span></span>  
<span data-ttu-id="f4bf7-112">这可以帮助你确保按预期发送和接收事件。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-112">This can help you make sure that events are being sent and received as expected.</span></span>  <span data-ttu-id="f4bf7-113">你还可以检查每个事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-113">You can also inspect the details of each event.</span></span>  

> ##### <span data-ttu-id="f4bf7-114">图 1</span><span class="sxs-lookup"><span data-stu-id="f4bf7-114">Figure 1</span></span>  
> <span data-ttu-id="f4bf7-115">在 "推送消息" 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="f4bf7-115">Viewing the details of an event in the Push Messaging pane</span></span>  
> ![在 "推送消息" 窗格中查看事件的详细信息][PushDetails]  

## <span data-ttu-id="f4bf7-117">后台获取</span><span class="sxs-lookup"><span data-stu-id="f4bf7-117">Background Fetch</span></span>   

<span data-ttu-id="f4bf7-118">*后台获取 API*\* 使**服务工作者**能够以后台服务的形式可靠地下载大型资源（如电影或播客）。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-118">The *Background Fetch API*\* enables a **service worker** to reliably download large resources, like movies or podcasts, as a background service.</span></span>  <span data-ttu-id="f4bf7-119">若要在3天内记录后台提取事件（即使 DevTools 未打开）：</span><span class="sxs-lookup"><span data-stu-id="f4bf7-119">To log Background Fetch event for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background fetch api section when available -->  

1.  <span data-ttu-id="f4bf7-120">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-120">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="f4bf7-121">打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-121">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="f4bf7-122">打开 "**后台获取**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-122">Open the **Background Fetch** pane.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-123">图 2</span><span class="sxs-lookup"><span data-stu-id="f4bf7-123">Figure 2</span></span>  
    > <span data-ttu-id="f4bf7-124">"背景获取" 窗格</span><span class="sxs-lookup"><span data-stu-id="f4bf7-124">The Background Fetch pane</span></span>  
    > !["背景获取" 窗格][FetchEmpty]  
    
1.  <span data-ttu-id="f4bf7-126">单击 "**录制** ![ 记录" ][ImageRecordIcon] 。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-126">Click **Record** ![Record][ImageRecordIcon].</span></span>  
   <span data-ttu-id="f4bf7-127">触发某些后台获取活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-127">After triggering some Background Fetch activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-128">图 3</span><span class="sxs-lookup"><span data-stu-id="f4bf7-128">Figure 3</span></span>  
    > <span data-ttu-id="f4bf7-129">后台提取窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="f4bf7-129">A log of events in the Background Fetch pane</span></span>  
    > ![后台提取窗格中的事件日志][FetchLog]  
    
1.  <span data-ttu-id="f4bf7-131">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-131">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-132">图 4</span><span class="sxs-lookup"><span data-stu-id="f4bf7-132">Figure 4</span></span>  
    > <span data-ttu-id="f4bf7-133">在 "后台提取" 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="f4bf7-133">Viewing the details of an event in the Background Fetch pane</span></span>  
    > ![在 "后台提取" 窗格中查看事件的详细信息][FetchDetails]  

## <span data-ttu-id="f4bf7-135">后台同步</span><span class="sxs-lookup"><span data-stu-id="f4bf7-135">Background Sync</span></span>   

<span data-ttu-id="f4bf7-136">**后台同步 API**使脱机**服务工作人员**能够在服务器重新建立可靠的 internet 连接后向其发送数据。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-136">The **Background Sync API** enables an offline **service worker** to send data to a server once it has re-established a reliable internet connection.</span></span>  <span data-ttu-id="f4bf7-137">若要记录3天的后台同步事件（即使 DevTools 未打开）：</span><span class="sxs-lookup"><span data-stu-id="f4bf7-137">To log Background Sync events for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background sync api section when available -->  

1.  <span data-ttu-id="f4bf7-138">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-138">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="f4bf7-139">打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-139">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="f4bf7-140">打开 "**后台同步**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-140">Open the **Background Sync** pane.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-141">图 5</span><span class="sxs-lookup"><span data-stu-id="f4bf7-141">Figure 5</span></span>  
    > <span data-ttu-id="f4bf7-142">"后台同步" 窗格</span><span class="sxs-lookup"><span data-stu-id="f4bf7-142">The Background Sync pane</span></span>  
    > !["后台同步" 窗格][SyncEmpty]  
    
1.  <span data-ttu-id="f4bf7-144">单击 "**录制** ![ 记录" ][ImageRecordIcon] 。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-144">Click **Record** ![Record][ImageRecordIcon].</span></span>  
   <span data-ttu-id="f4bf7-145">触发某些后台同步活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-145">After triggering some Background Sync activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-146">图 6</span><span class="sxs-lookup"><span data-stu-id="f4bf7-146">Figure 6</span></span>  
    > <span data-ttu-id="f4bf7-147">"后台同步" 窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="f4bf7-147">A log of events in the Background Sync pane</span></span>  
    > !["后台同步" 窗格中的事件日志][SyncLog]  
    
1.  <span data-ttu-id="f4bf7-149">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-149">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-150">图 7</span><span class="sxs-lookup"><span data-stu-id="f4bf7-150">Figure 7</span></span>  
    > <span data-ttu-id="f4bf7-151">在 "后台同步" 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="f4bf7-151">Viewing the details of an event in the Background Sync pane</span></span>  
    > ![在 "后台同步" 窗格中查看事件的详细信息][SyncDetails]  
    
## <span data-ttu-id="f4bf7-153">通知</span><span class="sxs-lookup"><span data-stu-id="f4bf7-153">Notifications</span></span> 

<span data-ttu-id="f4bf7-154">**服务工作人员**从服务器收到[推送消息][MDNPush]后，服务工作人员使用[通知 API][MDNNotifications]将数据显示给用户。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-154">After a **service worker** has received a [Push Message][MDNPush] from a server, the service worker uses the [Notifications API][MDNNotifications] to display the data to a user.</span></span>  <span data-ttu-id="f4bf7-155">要记录3天的通知（即使 DevTools 未打开）：</span><span class="sxs-lookup"><span data-stu-id="f4bf7-155">To log Notifications for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="f4bf7-156">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-156">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="f4bf7-157">打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-157">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="f4bf7-158">打开 "**通知**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-158">Open the **Notifications** pane.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-159">图 8</span><span class="sxs-lookup"><span data-stu-id="f4bf7-159">Figure 8</span></span>  
    > <span data-ttu-id="f4bf7-160">"通知" 窗格</span><span class="sxs-lookup"><span data-stu-id="f4bf7-160">The Notifications pane</span></span>  
    > !["通知" 窗格][NotificationsEmpty]  
    
1.  <span data-ttu-id="f4bf7-162">单击 "**录制** ![ 记录" ][ImageRecordIcon] 。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-162">Click **Record** ![Record][ImageRecordIcon].</span></span>  
   <span data-ttu-id="f4bf7-163">触发某些通知活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-163">After triggering some Notifications activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-164">图 9</span><span class="sxs-lookup"><span data-stu-id="f4bf7-164">Figure 9</span></span>  
    > <span data-ttu-id="f4bf7-165">"通知" 窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="f4bf7-165">A log of events in the Notifications pane</span></span>  
    > !["通知" 窗格中的事件日志][NotificationsLog]  
    
1.  <span data-ttu-id="f4bf7-167">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-167">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-168">图 10</span><span class="sxs-lookup"><span data-stu-id="f4bf7-168">Figure 10</span></span>  
    > <span data-ttu-id="f4bf7-169">在 "通知" 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="f4bf7-169">Viewing the details of an event in the Notifications pane</span></span>  
    > ![在 "通知" 窗格中查看事件的详细信息][NotificationsDetails]  
    
## <span data-ttu-id="f4bf7-171">推送邮件</span><span class="sxs-lookup"><span data-stu-id="f4bf7-171">Push Messages</span></span> 

<span data-ttu-id="f4bf7-172">若要向用户显示推送通知，**服务工作人员**必须首先使用[推送消息 API][MDNPush]从服务器接收数据。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-172">To display a push notification to a user, a **service worker** must first use the [Push Message API][MDNPush] to receive data from a server.</span></span>  <span data-ttu-id="f4bf7-173">当服务工作者准备好显示通知时，它将使用[通知 API][MDNNotifications]。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-173">When the service worker is ready to display the notification, it uses the [Notifications API][MDNNotifications].</span></span>  <span data-ttu-id="f4bf7-174">若要在3天内记录推送消息，即使在 DevTools 未打开的情况下也是如此：</span><span class="sxs-lookup"><span data-stu-id="f4bf7-174">To log Push Messages for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="f4bf7-175">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-175">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="f4bf7-176">打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-176">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="f4bf7-177">打开 "**推送消息**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-177">Open the **Push Messaging** pane.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-178">图 11</span><span class="sxs-lookup"><span data-stu-id="f4bf7-178">Figure 11</span></span>  
    > <span data-ttu-id="f4bf7-179">"推送消息" 窗格</span><span class="sxs-lookup"><span data-stu-id="f4bf7-179">The Push Messaging pane</span></span>  
    > !["推送消息" 窗格][PushEmpty]  

1.  <span data-ttu-id="f4bf7-181">单击 "**录制** ![ 记录" ][ImageRecordIcon] 。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-181">Click **Record** ![Record][ImageRecordIcon].</span></span>  
    <span data-ttu-id="f4bf7-182">触发某些推送消息活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-182">After triggering some Push Message activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-183">图 12</span><span class="sxs-lookup"><span data-stu-id="f4bf7-183">Figure 12</span></span>  
    > <span data-ttu-id="f4bf7-184">"推送消息" 窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="f4bf7-184">A log of events in the Push Messaging pane</span></span>  
    > !["推送消息" 窗格中的事件日志][PushLog]  

1.  <span data-ttu-id="f4bf7-186">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-186">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="f4bf7-187">图 13</span><span class="sxs-lookup"><span data-stu-id="f4bf7-187">Figure 13</span></span>  
    > <span data-ttu-id="f4bf7-188">在 "推送消息" 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="f4bf7-188">Viewing the details of an event in the Push Messaging pane</span></span>  
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
<span data-ttu-id="f4bf7-206">[WikiBackgroundProcess]： https://en.wikipedia.org/wiki/Background_process "后台进程-维基百科"</span><span class="sxs-lookup"><span data-stu-id="f4bf7-206">[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "Background process - Wikipedia"</span></span>  

> [!NOTE]
> <span data-ttu-id="f4bf7-207">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-207">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f4bf7-208">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-208">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  
[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="f4bf7-210">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f4bf7-210">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
