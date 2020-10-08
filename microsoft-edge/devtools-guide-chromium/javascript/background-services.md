---
description: 如何通过 Microsoft Edge DevTools 调试后台提取、后台同步、通知和推送消息。
title: 通过 Microsoft Edge DevTools 调试后台服务
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 1724bd3a5e45734555650c3d46e377161a3a7c65
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992867"
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





# <span data-ttu-id="0b301-104">通过 Microsoft Edge DevTools 调试后台服务</span><span class="sxs-lookup"><span data-stu-id="0b301-104">Debug Background Services With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="0b301-105">Microsoft Edge DevTools 的 " **后台服务** " 部分是用于 JavaScript api 的工具集合，可使你的网站即使在用户未打开网站时也可以发送和接收更新。</span><span class="sxs-lookup"><span data-stu-id="0b301-105">The **Background Services** section of Microsoft Edge DevTools is a collection of tools for the JavaScript APIs that enables your website to send and receive updates even when a user does not have your website open.</span></span>  
<span data-ttu-id="0b301-106">后台服务在功能上类似于 [后台进程] [WikiBackgroundProcess]。</span><span class="sxs-lookup"><span data-stu-id="0b301-106">A background service is functionally similar to a [background process][WikiBackgroundProcess].</span></span>  
<span data-ttu-id="0b301-107">Microsoft Edge DevTools 将以下每个 Api 视为后台服务：</span><span class="sxs-lookup"><span data-stu-id="0b301-107">Microsoft Edge DevTools considers each of the following APIs to be a background service:</span></span>  

*   [<span data-ttu-id="0b301-108">后台获取</span><span class="sxs-lookup"><span data-stu-id="0b301-108">Background Fetch</span></span>](#background-fetch)  
*   [<span data-ttu-id="0b301-109">后台同步</span><span class="sxs-lookup"><span data-stu-id="0b301-109">Background Sync</span></span>](#background-sync)  
*   [<span data-ttu-id="0b301-110">通知</span><span class="sxs-lookup"><span data-stu-id="0b301-110">Notifications</span></span>](#notifications)  
*   [<span data-ttu-id="0b301-111">推送邮件</span><span class="sxs-lookup"><span data-stu-id="0b301-111">Push Messages</span></span>](#push-messages)  
    
<span data-ttu-id="0b301-112">Microsoft Edge DevTools 可以记录3天的后台服务事件，即使 DevTools 未打开也是如此。</span><span class="sxs-lookup"><span data-stu-id="0b301-112">Microsoft Edge DevTools can log background service events for 3 days, even when DevTools is not open.</span></span>  
<span data-ttu-id="0b301-113">这可以帮助你确保按预期发送和接收事件。</span><span class="sxs-lookup"><span data-stu-id="0b301-113">This can help you make sure that events are being sent and received as expected.</span></span>  <span data-ttu-id="0b301-114">你还可以检查每个事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b301-114">You may also inspect the details of each event.</span></span>  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   <span data-ttu-id="0b301-116">在 " **推送消息** " 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="0b301-116">View the details of an event in the **Push Messaging** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="0b301-117">后台获取</span><span class="sxs-lookup"><span data-stu-id="0b301-117">Background Fetch</span></span>   

<span data-ttu-id="0b301-118">*后台获取 API*\* 使**服务工作者**能够以后台服务的形式可靠地下载大型资源（如电影或播客）。</span><span class="sxs-lookup"><span data-stu-id="0b301-118">The *Background Fetch API*\* enables a **service worker** to reliably download large resources, like movies or podcasts, as a background service.</span></span>  <span data-ttu-id="0b301-119">若要在3天内记录后台提取事件（即使 DevTools 未打开）：</span><span class="sxs-lookup"><span data-stu-id="0b301-119">To log Background Fetch event for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background fetch api section when available -->  

1.  <span data-ttu-id="0b301-120">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="0b301-120">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="0b301-121">打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="0b301-121">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="0b301-122">打开 " **后台获取** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b301-122">Open the **Background Fetch** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       <span data-ttu-id="0b301-124">" **背景获取** " 窗格</span><span class="sxs-lookup"><span data-stu-id="0b301-124">The **Background Fetch** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-125">单击 " **记录** \ (![ 记录 ][ImageRecordIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="0b301-125">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="0b301-126">触发某些后台获取活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="0b301-126">After triggering some Background Fetch activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       <span data-ttu-id="0b301-128">**后台提取**窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="0b301-128">A log of events in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-129">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b301-129">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       <span data-ttu-id="0b301-131">在 " **后台提取** " 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="0b301-131">View the details of an event in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0b301-132">后台同步</span><span class="sxs-lookup"><span data-stu-id="0b301-132">Background Sync</span></span>   

<span data-ttu-id="0b301-133">**后台同步 API**使脱机**服务工作人员**能够在服务器重新建立可靠的 internet 连接后向其发送数据。</span><span class="sxs-lookup"><span data-stu-id="0b301-133">The **Background Sync API** enables an offline **service worker** to send data to a server once it has re-established a reliable internet connection.</span></span>  <span data-ttu-id="0b301-134">若要记录3天的后台同步事件（即使 DevTools 未打开）：</span><span class="sxs-lookup"><span data-stu-id="0b301-134">To log Background Sync events for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background sync api section when available -->  

1.  <span data-ttu-id="0b301-135">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="0b301-135">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="0b301-136">打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="0b301-136">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="0b301-137">打开 " **后台同步** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b301-137">Open the **Background Sync** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       <span data-ttu-id="0b301-139">" **后台同步** " 窗格</span><span class="sxs-lookup"><span data-stu-id="0b301-139">The **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-140">单击 " **记录** \ (![ 记录 ][ImageRecordIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="0b301-140">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="0b301-141">触发某些后台同步活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="0b301-141">After triggering some Background Sync activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       <span data-ttu-id="0b301-143">" **后台同步** " 窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="0b301-143">A log of events in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-144">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b301-144">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       <span data-ttu-id="0b301-146">在 " **后台同步** " 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="0b301-146">View the details of an event in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0b301-147">通知</span><span class="sxs-lookup"><span data-stu-id="0b301-147">Notifications</span></span> 

<span data-ttu-id="0b301-148">**服务工作人员**从服务器收到[推送消息][MDNPush]后，服务工作人员使用[通知 API][MDNNotifications]将数据显示给用户。</span><span class="sxs-lookup"><span data-stu-id="0b301-148">After a **service worker** has received a [Push Message][MDNPush] from a server, the service worker uses the [Notifications API][MDNNotifications] to display the data to a user.</span></span>  <span data-ttu-id="0b301-149">要记录3天的通知（即使 DevTools 未打开）：</span><span class="sxs-lookup"><span data-stu-id="0b301-149">To log Notifications for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="0b301-150">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="0b301-150">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="0b301-151">打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="0b301-151">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="0b301-152">打开 " **通知** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b301-152">Open the **Notifications** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       <span data-ttu-id="0b301-154">" **通知** " 窗格</span><span class="sxs-lookup"><span data-stu-id="0b301-154">The **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-155">单击 " **记录** \ (![ 记录 ][ImageRecordIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="0b301-155">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="0b301-156">触发某些通知活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="0b301-156">After triggering some Notifications activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       <span data-ttu-id="0b301-158">" **通知** " 窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="0b301-158">A log of events in the **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-159">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b301-159">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       <span data-ttu-id="0b301-161">在 " **通知** " 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="0b301-161">View the details of an event in the **Notifications** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0b301-162">推送邮件</span><span class="sxs-lookup"><span data-stu-id="0b301-162">Push Messages</span></span> 

<span data-ttu-id="0b301-163">若要向用户显示推送通知， **服务工作人员** 必须首先使用 [推送消息 API][MDNPush] 从服务器接收数据。</span><span class="sxs-lookup"><span data-stu-id="0b301-163">To display a push notification to a user, a **service worker** must first use the [Push Message API][MDNPush] to receive data from a server.</span></span>  <span data-ttu-id="0b301-164">当服务工作者准备好显示通知时，它将使用 [通知 API][MDNNotifications]。</span><span class="sxs-lookup"><span data-stu-id="0b301-164">When the service worker is ready to display the notification, it uses the [Notifications API][MDNNotifications].</span></span>  <span data-ttu-id="0b301-165">若要在3天内记录推送消息，即使在 DevTools 未打开的情况下也是如此：</span><span class="sxs-lookup"><span data-stu-id="0b301-165">To log Push Messages for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="0b301-166">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="0b301-166">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="0b301-167">打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="0b301-167">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="0b301-168">打开 " **推送消息** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b301-168">Open the **Push Messaging** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       <span data-ttu-id="0b301-170">" **推送消息** " 窗格</span><span class="sxs-lookup"><span data-stu-id="0b301-170">The **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-171">单击 " **记录** \ (![ 记录 ][ImageRecordIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="0b301-171">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
    <span data-ttu-id="0b301-172">触发某些推送消息活动后，DevTools 会将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="0b301-172">After triggering some Push Message activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       <span data-ttu-id="0b301-174">" **推送消息** " 窗格中的事件日志</span><span class="sxs-lookup"><span data-stu-id="0b301-174">A log of events in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b301-175">单击某个事件可在表下方的空间中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b301-175">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="在 &quot;推送消息&quot; 窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       <span data-ttu-id="0b301-177">在 " **推送消息** " 窗格中查看事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="0b301-177">View the details of an event in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageRecordIcon]: ../media/record-icon.msft.png  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open.md "打开 Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
<span data-ttu-id="0b301-181">[WikiBackgroundProcess]： https://en.wikipedia.org/wiki/Background_process "后台进程-维基百科"</span><span class="sxs-lookup"><span data-stu-id="0b301-181">[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "Background process - Wikipedia"</span></span>  

> [!NOTE]
> <span data-ttu-id="0b301-182">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0b301-182">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0b301-183">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="0b301-183">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  
[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0b301-185">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0b301-185">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
