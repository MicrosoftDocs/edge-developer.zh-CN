---
description: 如何使用 Microsoft Edge DevTools 调试后台提取、后台同步、通知和推送消息。
title: 使用 Microsoft Edge DevTools 调试后台服务
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: cf3459e7b5f80a695a855ffdd0c249c2bc223d31
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398635"
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

# <a name="debug-background-services-with-microsoft-edge-devtools"></a><span data-ttu-id="add6a-104">使用 Microsoft Edge DevTools 调试后台服务</span><span class="sxs-lookup"><span data-stu-id="add6a-104">Debug Background Services with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="add6a-105">Microsoft \*\*\*\* Edge DevTools 的"后台服务"部分是 JavaScript API 的工具集合，可使您的网站发送和接收更新，即使用户未打开您的网站。</span><span class="sxs-lookup"><span data-stu-id="add6a-105">The **Background Services** section of Microsoft Edge DevTools is a collection of tools for the JavaScript APIs that enables your website to send and receive updates even when a user does not have your website open.</span></span>  
<span data-ttu-id="add6a-106">后台服务在功能上类似于 [后台进程][WikiBackgroundProcess]。</span><span class="sxs-lookup"><span data-stu-id="add6a-106">A background service is functionally similar to a [background process][WikiBackgroundProcess].</span></span>  
<span data-ttu-id="add6a-107">Microsoft Edge DevTools 将以下每个 API 都作为后台服务：</span><span class="sxs-lookup"><span data-stu-id="add6a-107">Microsoft Edge DevTools considers each of the following APIs to be a background service:</span></span>  

*   [<span data-ttu-id="add6a-108">后台提取</span><span class="sxs-lookup"><span data-stu-id="add6a-108">Background Fetch</span></span>](#background-fetch)  
*   [<span data-ttu-id="add6a-109">后台同步</span><span class="sxs-lookup"><span data-stu-id="add6a-109">Background Sync</span></span>](#background-sync)  
*   [<span data-ttu-id="add6a-110">通知</span><span class="sxs-lookup"><span data-stu-id="add6a-110">Notifications</span></span>](#notifications)  
*   [<span data-ttu-id="add6a-111">推送消息</span><span class="sxs-lookup"><span data-stu-id="add6a-111">Push Messages</span></span>](#push-messages)  
    
<span data-ttu-id="add6a-112">Microsoft Edge DevTools 可能会记录后台服务事件 3 天，即使 DevTools 未打开。</span><span class="sxs-lookup"><span data-stu-id="add6a-112">Microsoft Edge DevTools may log background service events for 3 days, even when DevTools is not open.</span></span>  
<span data-ttu-id="add6a-113">后台服务事件日志可帮助您确保事件是像预期一样发送和接收的。</span><span class="sxs-lookup"><span data-stu-id="add6a-113">The background service events log may help you make sure that events are being sent and received as expected.</span></span>  <span data-ttu-id="add6a-114">您还可以检查每个事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="add6a-114">You may also inspect the details of each event.</span></span>  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="推送消息窗格" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   <span data-ttu-id="add6a-116">推送 **消息** 窗格</span><span class="sxs-lookup"><span data-stu-id="add6a-116">The **Push Messaging** pane</span></span>  
:::image-end:::  

## <a name="background-fetch"></a><span data-ttu-id="add6a-117">后台提取</span><span class="sxs-lookup"><span data-stu-id="add6a-117">Background Fetch</span></span>  

<span data-ttu-id="add6a-118">后台 **提取 API** 使 **服务** 工作者能够可靠地下载大型资源（如电影或播客）作为后台服务。</span><span class="sxs-lookup"><span data-stu-id="add6a-118">The **Background Fetch API** enables a **service worker** to reliably download large resources, like movies or podcasts, as a background service.</span></span>  <span data-ttu-id="add6a-119">若要将后台提取事件记录 3 天，即使 DevTools 未打开，</span><span class="sxs-lookup"><span data-stu-id="add6a-119">To log Background Fetch event for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background fetch api section when available -->  

1.  <span data-ttu-id="add6a-120">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="add6a-120">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="add6a-121">打开 **应用程序** 工具。</span><span class="sxs-lookup"><span data-stu-id="add6a-121">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="add6a-122">打开 **"后台提取"** 面板。</span><span class="sxs-lookup"><span data-stu-id="add6a-122">Open the **Background Fetch** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="后台提取面板" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       <span data-ttu-id="add6a-124">后台 **提取** 面板</span><span class="sxs-lookup"><span data-stu-id="add6a-124">The **Background Fetch** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-125">Choose **Record** \ (![ Record ][ImageRecordIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="add6a-125">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="add6a-126">触发某些后台提取活动后，DevTools 将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="add6a-126">After triggering some Background Fetch activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="后台提取面板中的事件日志" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       <span data-ttu-id="add6a-128">后台提取面板中的 **事件** 日志</span><span class="sxs-lookup"><span data-stu-id="add6a-128">A log of events in the **Background Fetch** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-129">选择一个事件，在表下方的空格中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="add6a-129">Choose an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="在"后台提取"窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       <span data-ttu-id="add6a-131">在"后台提取"窗格中查看 **事件** 的详细信息</span><span class="sxs-lookup"><span data-stu-id="add6a-131">View the details of an event in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
## <a name="background-sync"></a><span data-ttu-id="add6a-132">后台同步</span><span class="sxs-lookup"><span data-stu-id="add6a-132">Background Sync</span></span>  

<span data-ttu-id="add6a-133">后台**同步 API**使脱机\*\*\*\* 服务工作者能够在重新建立可靠的 Internet 连接后向服务器发送数据。</span><span class="sxs-lookup"><span data-stu-id="add6a-133">The **Background Sync API** enables an offline **service worker** to send data to a server once it has re-established a reliable internet connection.</span></span>  <span data-ttu-id="add6a-134">若要将后台同步事件记录 3 天，即使 DevTools 未打开，</span><span class="sxs-lookup"><span data-stu-id="add6a-134">To log Background Sync events for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background sync api section when available -->  

1.  <span data-ttu-id="add6a-135">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="add6a-135">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="add6a-136">打开 **应用程序** 工具。</span><span class="sxs-lookup"><span data-stu-id="add6a-136">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="add6a-137">打开 **"后台同步"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="add6a-137">Open the **Background Sync** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text=""后台同步"窗格" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       <span data-ttu-id="add6a-139">" **后台同步"** 窗格</span><span class="sxs-lookup"><span data-stu-id="add6a-139">The **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-140">Choose **Record** \ (![ Record ][ImageRecordIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="add6a-140">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="add6a-141">触发某些后台同步活动后，DevTools 将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="add6a-141">After triggering some Background Sync activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="后台同步窗格中的事件日志" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       <span data-ttu-id="add6a-143">后台同步窗格中 **的事件** 日志</span><span class="sxs-lookup"><span data-stu-id="add6a-143">A log of events in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-144">选择一个事件，在表下方的空格中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="add6a-144">Choose an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="在"后台同步"窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       <span data-ttu-id="add6a-146">在"后台同步"窗格中查看 **事件** 的详细信息</span><span class="sxs-lookup"><span data-stu-id="add6a-146">View the details of an event in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
## <a name="notifications"></a><span data-ttu-id="add6a-147">通知</span><span class="sxs-lookup"><span data-stu-id="add6a-147">Notifications</span></span>  

<span data-ttu-id="add6a-148">在**服务工作者**从服务器收到推送[][MDNPush]消息后，服务工作者使用通知[API][MDNNotifications]向用户显示数据。</span><span class="sxs-lookup"><span data-stu-id="add6a-148">After a **service worker** has received a [Push Message][MDNPush] from a server, the service worker uses the [Notifications API][MDNNotifications] to display the data to a user.</span></span>  <span data-ttu-id="add6a-149">若要将通知记录 3 天，即使 DevTools 未打开，</span><span class="sxs-lookup"><span data-stu-id="add6a-149">To log Notifications for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="add6a-150">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="add6a-150">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="add6a-151">打开 **应用程序** 工具。</span><span class="sxs-lookup"><span data-stu-id="add6a-151">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="add6a-152">打开 **"通知"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="add6a-152">Open the **Notifications** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="通知窗格" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       <span data-ttu-id="add6a-154">通知**窗格**</span><span class="sxs-lookup"><span data-stu-id="add6a-154">The **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-155">Choose **Record** \ (![ Record ][ImageRecordIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="add6a-155">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="add6a-156">触发某些通知活动后，DevTools 将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="add6a-156">After triggering some Notifications activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="通知窗格中的事件日志" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       <span data-ttu-id="add6a-158">通知窗格中**的事件日志**</span><span class="sxs-lookup"><span data-stu-id="add6a-158">A log of events in the **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-159">选择一个事件，在表下方的空格中查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="add6a-159">Choose an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="在"通知"窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       <span data-ttu-id="add6a-161">在"通知"窗格中查看 **事件** 的详细信息</span><span class="sxs-lookup"><span data-stu-id="add6a-161">View the details of an event in the **Notifications** pane</span></span>  
    :::image-end:::  
    
## <a name="push-messages"></a><span data-ttu-id="add6a-162">推送消息</span><span class="sxs-lookup"><span data-stu-id="add6a-162">Push Messages</span></span>  

<span data-ttu-id="add6a-163">若要向用户显示推送通知，服务工作者必须先使用\*\*\*\* 推送[消息 API][MDNPush]从服务器接收数据。</span><span class="sxs-lookup"><span data-stu-id="add6a-163">To display a push notification to a user, a **service worker** must first use the [Push Message API][MDNPush] to receive data from a server.</span></span>  <span data-ttu-id="add6a-164">当服务工作者准备好显示通知时，它使用[通知 API。][MDNNotifications]</span><span class="sxs-lookup"><span data-stu-id="add6a-164">When the service worker is ready to display the notification, it uses the [Notifications API][MDNNotifications].</span></span>  <span data-ttu-id="add6a-165">若要记录推送消息 3 天，即使 DevTools 未打开，</span><span class="sxs-lookup"><span data-stu-id="add6a-165">To log Push Messages for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="add6a-166">[打开 DevTools][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="add6a-166">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="add6a-167">打开 **应用程序** 工具。</span><span class="sxs-lookup"><span data-stu-id="add6a-167">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="add6a-168">打开 **"推送消息"** 面板。</span><span class="sxs-lookup"><span data-stu-id="add6a-168">Open the **Push Messaging** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="打开"推送消息"窗格" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       <span data-ttu-id="add6a-170">打开 **"推送消息"** 窗格</span><span class="sxs-lookup"><span data-stu-id="add6a-170">Open the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-171">Choose **Record** \ (![ Record ][ImageRecordIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="add6a-171">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
    <span data-ttu-id="add6a-172">触发一些推送消息活动后，DevTools 将事件记录到表中。</span><span class="sxs-lookup"><span data-stu-id="add6a-172">After triggering some Push Message activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="推送消息窗格中的事件日志" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       <span data-ttu-id="add6a-174">推送消息窗格中 **的事件** 日志</span><span class="sxs-lookup"><span data-stu-id="add6a-174">A log of events in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="add6a-175">选择一个事件以查看表下方空间的详细信息。</span><span class="sxs-lookup"><span data-stu-id="add6a-175">Choose an event to view the details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="在"推送消息"窗格中查看事件的详细信息" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       <span data-ttu-id="add6a-177">在"推送消息"窗格中查看**事件的详细信息**</span><span class="sxs-lookup"><span data-stu-id="add6a-177">View the details of an event in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="add6a-178">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="add6a-178">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRecordIcon]: ../media/record-icon.msft.png  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open/index.md "打开 Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
<span data-ttu-id="add6a-182">[WikiBackgroundProcess]： https://en.wikipedia.org/wiki/Background_process "Background process - Wikipedia"</span><span class="sxs-lookup"><span data-stu-id="add6a-182">[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "Background process - Wikipedia"</span></span>  

> [!NOTE]
> <span data-ttu-id="add6a-183">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="add6a-183">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="add6a-184">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="add6a-184">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  
[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="add6a-186">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="add6a-186">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
