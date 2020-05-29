---
title: 调试渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ce389ad10073efd318e5fa4df59d78fd40b7ebeb
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601878"
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





# <span data-ttu-id="915d7-103">调试渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="915d7-103">Debug Progressive Web Apps</span></span>   



<span data-ttu-id="915d7-104">使用**应用程序**面板检查、修改和调试 web 应用清单、服务工作人员和服务工作人员缓存。</span><span class="sxs-lookup"><span data-stu-id="915d7-104">Use the **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

<span data-ttu-id="915d7-105">本指南仅讨论**应用程序**面板的渐进 Web 应用功能。</span><span class="sxs-lookup"><span data-stu-id="915d7-105">This guide only discusses the Progressive Web App features of the **Application** panel.</span></span>  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### <span data-ttu-id="915d7-106">摘要</span><span class="sxs-lookup"><span data-stu-id="915d7-106">Summary</span></span>  

*   <span data-ttu-id="915d7-107">使用**清单**窗格检查 web 应用清单和触发器添加到主屏幕事件。</span><span class="sxs-lookup"><span data-stu-id="915d7-107">Use the **Manifest** pane to inspect your web app manifest and trigger Add to Homescreen events.</span></span>  
*   <span data-ttu-id="915d7-108">将 "**服务工作人员**" 窗格用于整个服务工作人员相关的任务，例如注销或更新服务、模拟推送事件、脱机或停止服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="915d7-108">Use the **Service Workers** pane for a whole range of service-worker-related tasks, like unregistering or updating a service, emulating push events, going offline, or stopping a service worker.</span></span>  
*   <span data-ttu-id="915d7-109">从 "**缓存存储**" 窗格中查看服务工作人员缓存。</span><span class="sxs-lookup"><span data-stu-id="915d7-109">View your service worker cache from the **Cache Storage** pane.</span></span>  
*   <span data-ttu-id="915d7-110">从 "**清除存储**" 窗格中，注销服务工作人员并通过单个按钮单击清除所有存储和缓存。</span><span class="sxs-lookup"><span data-stu-id="915d7-110">Unregister a service worker and clear all storage and caches with a single button click from the **Clear storage** pane.</span></span>  

## <span data-ttu-id="915d7-111">Web app 清单</span><span class="sxs-lookup"><span data-stu-id="915d7-111">Web app manifest</span></span>   

<span data-ttu-id="915d7-112">如果你希望你的用户能够将应用添加到其移动 homescreens，你需要 web 应用清单。</span><span class="sxs-lookup"><span data-stu-id="915d7-112">If you want your users to be able to add your app to their mobile homescreens, you need a web app manifest.</span></span>  <span data-ttu-id="915d7-113">该清单定义应用在主屏幕上的显示方式，在从主屏幕启动时，以及应用在启动时的外观。</span><span class="sxs-lookup"><span data-stu-id="915d7-113">The manifest defines how the app appears on the homescreen, where to direct the user when launching from homescreen, and what the app looks like on launch.</span></span>  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

<span data-ttu-id="915d7-114">设置清单后，您可以使用 "**应用程序**" 面板的**清单**窗格进行检查。</span><span class="sxs-lookup"><span data-stu-id="915d7-114">Once you've got your manifest set up, you can use the **Manifest** pane of the **Application** panel to inspect it.</span></span>  

> ##### <span data-ttu-id="915d7-115">图 1</span><span class="sxs-lookup"><span data-stu-id="915d7-115">Figure 1</span></span>  
> <span data-ttu-id="915d7-116">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="915d7-116">The **Manifest** Pane</span></span>  
> ![清单窗格][ImageManifest]  

*   <span data-ttu-id="915d7-118">若要查看清单源，请单击 "**应用清单**标签 \" 下的链接 \ （ `https://airhorner.com/manifest.json` [**见图 1**](#figure-1)] \）。</span><span class="sxs-lookup"><span data-stu-id="915d7-118">To look at the manifest source, click the link below **App Manifest** label \(`https://airhorner.com/manifest.json` in [**Figure 1**](#figure-1)]\).</span></span>  
<!-- *   Press the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   <span data-ttu-id="915d7-119">"**标识**" 和 "**演示文稿**" 部分仅在更易于用户友好的显示中显示清单源中的字段。</span><span class="sxs-lookup"><span data-stu-id="915d7-119">The **Identity** and **Presentation** sections just display fields from the manifest source in a more user-friendly display.</span></span>  
*   <span data-ttu-id="915d7-120">"**图标**" 部分显示您已指定的每个图标。</span><span class="sxs-lookup"><span data-stu-id="915d7-120">The **Icons** section displays every icon that you've specified.</span></span>  

<!--### Simulate Add to Homescreen events   -->

<!--A web app can only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, this criteria can be inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You can test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Clicking on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--![add to desktop shelf][ImageDesktopShelf]  -->

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature cannot yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you can successfully add your app to your desktop shelf, then it'll work for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you can connect a real mobile device to DevTools via **remote debugging**, and then click the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## <span data-ttu-id="915d7-121">服务工作人员</span><span class="sxs-lookup"><span data-stu-id="915d7-121">Service workers</span></span>   

<span data-ttu-id="915d7-122">服务工作者是未来 web 平台中的一种基本技术。</span><span class="sxs-lookup"><span data-stu-id="915d7-122">Service workers are a fundamental technology in the future web platform.</span></span>  <span data-ttu-id="915d7-123">它们是浏览器在后台运行的脚本，这些脚本独立于网页。</span><span class="sxs-lookup"><span data-stu-id="915d7-123">They are scripts that the browser runs in the background, separate from a web page.</span></span>  <span data-ttu-id="915d7-124">这些脚本使你能够访问不需要网页或用户交互的功能，如推送通知、后台同步和脱机体验。</span><span class="sxs-lookup"><span data-stu-id="915d7-124">These scripts enable you to access features that don't need a web page or user interaction, like push notifications, background sync, and offline experiences.</span></span>  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  

<!--TODO:  Link to sections when available. -->  

<span data-ttu-id="915d7-125">"**应用程序**" 面板中的 "**服务工作人员**" 窗格是 DevTools 检查和调试服务工作人员的主要位置。</span><span class="sxs-lookup"><span data-stu-id="915d7-125">The **Service Workers** pane in the **Application** panel is the main place in DevTools to inspect and debug service workers.</span></span>  

> ##### <span data-ttu-id="915d7-126">图 2</span><span class="sxs-lookup"><span data-stu-id="915d7-126">Figure 2</span></span>  
> <span data-ttu-id="915d7-127">"**服务工作人员**" 窗格</span><span class="sxs-lookup"><span data-stu-id="915d7-127">The **Service Workers** Pane</span></span>  
> <span data-ttu-id="915d7-128">![服务工作人员窗格][ImageServiceWorkersPane]</span><span class="sxs-lookup"><span data-stu-id="915d7-128">![The Service Workers pane][ImageServiceWorkersPane]</span></span>  

*   <span data-ttu-id="915d7-129">如果将服务工作人员安装到当前打开的页面，则会看到此窗格中列出了该工作人员。</span><span class="sxs-lookup"><span data-stu-id="915d7-129">If a service worker is installed to the currently open page, then you'll see it listed on this pane.</span></span>  <span data-ttu-id="915d7-130">例如，在[**图 2**](#figure-2)中，已为的作用域安装了一个服务工作人员 `https://weather-pwa-sample.firebaseapp.com` 。</span><span class="sxs-lookup"><span data-stu-id="915d7-130">For example, in [**Figure 2**](#figure-2) there's a service worker installed for the scope of `https://weather-pwa-sample.firebaseapp.com`.</span></span>  
*   <span data-ttu-id="915d7-131">**脱机**复选框将 DevTools 置于脱机模式。</span><span class="sxs-lookup"><span data-stu-id="915d7-131">The **Offline** checkbox puts DevTools into offline mode.</span></span>  <span data-ttu-id="915d7-132">这等效于 "**网络**" 面板中可用的脱机模式，或 " `Go offline` [命令" 菜单][DevtoolsCommandMenuIndex]中的选项。</span><span class="sxs-lookup"><span data-stu-id="915d7-132">This is equivalent to the offline mode available from the **Network** panel, or the `Go offline` option in the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
*   <span data-ttu-id="915d7-133">"**重新加载时的更新**" 复选框强制服务工作者在每次加载页面时进行更新。</span><span class="sxs-lookup"><span data-stu-id="915d7-133">The **Update on reload** checkbox forces the service worker to update on every page load.</span></span>  
*   <span data-ttu-id="915d7-134">"**绕过网络**" 复选框将绕过服务工作人员，并强制浏览器转到网络以获取请求的资源。</span><span class="sxs-lookup"><span data-stu-id="915d7-134">The **Bypass for network** checkbox bypasses the service worker and forces the browser to go to the network for requested resources.</span></span>  
*   <span data-ttu-id="915d7-135">"**更新**" 按钮对指定的服务工作人员执行一次性更新。</span><span class="sxs-lookup"><span data-stu-id="915d7-135">The **Update** button performs a one-time update of the specified service worker.</span></span>  
*   <span data-ttu-id="915d7-136">**Push**按钮模拟没有负载的推送通知 \ （也称为**tickle**\）。</span><span class="sxs-lookup"><span data-stu-id="915d7-136">The **Push** button emulates a push notification without a payload \(also known as a **tickle**\).</span></span>  
*   <span data-ttu-id="915d7-137">"**同步**" 按钮可模拟后台同步事件。</span><span class="sxs-lookup"><span data-stu-id="915d7-137">The **Sync** button emulates a background sync event.</span></span>  
*   <span data-ttu-id="915d7-138">"**注销**" 按钮将注销指定的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="915d7-138">The **Unregister** button unregisters the specified service worker.</span></span>  <span data-ttu-id="915d7-139">查看[清除存储](#clear-storage)，了解一种注销服务工作人员的方法，并通过单个按钮单击来擦除存储和缓存。</span><span class="sxs-lookup"><span data-stu-id="915d7-139">Check out [Clear storage](#clear-storage) for a way to unregister a service worker and wipe storage and caches with a single button click.</span></span>  
*   <span data-ttu-id="915d7-140">**源**行告诉你当前运行的服务工作线程何时安装。</span><span class="sxs-lookup"><span data-stu-id="915d7-140">The **Source** line tells you when the currently running service worker was installed.</span></span>  <span data-ttu-id="915d7-141">该链接是服务工作人员的源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="915d7-141">The link is the name of the service worker's source file.</span></span>  <span data-ttu-id="915d7-142">单击该链接即可将你发送到服务工作人员的源。</span><span class="sxs-lookup"><span data-stu-id="915d7-142">Clicking on the link sends you to the service worker's source.</span></span>  
*   <span data-ttu-id="915d7-143">**状态**行告诉你服务工作人员的状态。</span><span class="sxs-lookup"><span data-stu-id="915d7-143">The **Status** line tells you the status of the service worker.</span></span>  <span data-ttu-id="915d7-144">绿色状态指示器（ `#36` [**图 2**](#figure-2)\）旁边的 ID 号适用于当前处于活动状态的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="915d7-144">The ID number next to the green status indicator \(`#36` in [**Figure 2**](#figure-2)\) is for the currently active Service Worker.</span></span>  <span data-ttu-id="915d7-145">在 "状态" 旁边，你将看到 "**开始**" 按钮 \ （如果服务工作者已停止 \）或 "**停止**" 按钮 \ （如果服务工作者正在运行 \）。</span><span class="sxs-lookup"><span data-stu-id="915d7-145">Next to the status you'll see a **start** button \(if the service worker is stopped\) or a **stop** button \(if the service worker is running\).</span></span>  <span data-ttu-id="915d7-146">服务工作人员设计为在任何时候停止和启动浏览器。</span><span class="sxs-lookup"><span data-stu-id="915d7-146">Service workers are designed to be stopped and started by the browser at any time.</span></span>  <span data-ttu-id="915d7-147">使用**停止**按钮显式停止服务工作人员可以模拟该情况。</span><span class="sxs-lookup"><span data-stu-id="915d7-147">Explicitly stopping your service worker using the **stop** button can simulate that.</span></span>  <span data-ttu-id="915d7-148">停止服务工作人员是测试你的代码在服务工作人员再次启动时的行为方式的一种极佳方式。</span><span class="sxs-lookup"><span data-stu-id="915d7-148">Stopping your service worker is a great way to test how your code behaves when the service worker starts back up again.</span></span>  <span data-ttu-id="915d7-149">由于有关永久全局状态的错误假设，它经常会显示 bug。</span><span class="sxs-lookup"><span data-stu-id="915d7-149">It frequently reveals bugs due to faulty assumptions about persistent global state.</span></span>  
*   <span data-ttu-id="915d7-150">"**客户端**" 行告诉你服务工作者的作用范围。</span><span class="sxs-lookup"><span data-stu-id="915d7-150">The **Clients** line tells you the origin that the service worker is scoped to.</span></span>  <span data-ttu-id="915d7-151">当您启用 "**全部显示**" 复选框时，"**焦点**" 按钮非常有用。</span><span class="sxs-lookup"><span data-stu-id="915d7-151">The **focus** button is mostly useful when you've enabled the **show all** checkbox.</span></span>  <span data-ttu-id="915d7-152">启用该复选框时，将列出所有已注册的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="915d7-152">When that checkbox is enabled, all registered service workers are listed.</span></span>  <span data-ttu-id="915d7-153">如果单击在其他选项卡中运行的服务工作人员旁边的 "**焦点**" 按钮，则 Microsoft Edge 焦点位于该选项卡上。</span><span class="sxs-lookup"><span data-stu-id="915d7-153">If you click on the **focus** button next to a service worker that is running in a different tab, Microsoft Edge focuses on that tab.</span></span>  

<span data-ttu-id="915d7-154">如果服务工作人员导致任何错误，则会显示一个名为 "**错误**" 的新标签。</span><span class="sxs-lookup"><span data-stu-id="915d7-154">If the service worker causes any errors, a new label called **Errors** shows up.</span></span>  

<!--![service worker with errors][ImageServiceWorkerErrors]  -->

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## <span data-ttu-id="915d7-155">服务工作人员缓存</span><span class="sxs-lookup"><span data-stu-id="915d7-155">Service worker caches</span></span> 

<span data-ttu-id="915d7-156">"**缓存存储**" 窗格提供使用 \ （服务工作者 \）[缓存 API][MDNWebCacheAPI]缓存的资源的只读列表。</span><span class="sxs-lookup"><span data-stu-id="915d7-156">The **Cache Storage** pane provides a read-only list of resources that have been cached using the \(service worker\) [Cache API][MDNWebCacheAPI].</span></span>  

> ##### <span data-ttu-id="915d7-157">图 3</span><span class="sxs-lookup"><span data-stu-id="915d7-157">Figure 3</span></span>  
> <span data-ttu-id="915d7-158">"**缓存存储**" 窗格</span><span class="sxs-lookup"><span data-stu-id="915d7-158">The **Cache Storage** Pane</span></span>  
> <span data-ttu-id="915d7-159">![缓存存储窗格][ImageServiceWorkersCachePane]</span><span class="sxs-lookup"><span data-stu-id="915d7-159">![The Cache Storage Pane][ImageServiceWorkersCachePane]</span></span>  

> [!NOTE]
> <span data-ttu-id="915d7-160">第一次打开缓存并向其添加资源时，DevTools 可能不会检测更改。</span><span class="sxs-lookup"><span data-stu-id="915d7-160">The first time you open a cache and add a resource to it, DevTools might not detect the change.</span></span>  <span data-ttu-id="915d7-161">重新加载页面，你应该可以看到缓存。</span><span class="sxs-lookup"><span data-stu-id="915d7-161">Reload the page and you should see the cache.</span></span>  

<span data-ttu-id="915d7-162">如果打开了两个或多个缓存，则会在 "**缓存存储**" 下拉列表下方看到它们。</span><span class="sxs-lookup"><span data-stu-id="915d7-162">If you've got two or more caches open, you'll see them listed below the **Cache Storage** dropdown.</span></span>  

> ##### <span data-ttu-id="915d7-163">图 4</span><span class="sxs-lookup"><span data-stu-id="915d7-163">Figure 4</span></span>  
> <span data-ttu-id="915d7-164">"**缓存存储**" 下拉列表</span><span class="sxs-lookup"><span data-stu-id="915d7-164">The **Cache Storage** dropdown</span></span>  
> <span data-ttu-id="915d7-165">![缓存存储下拉列表][ImageMultipleCaches]</span><span class="sxs-lookup"><span data-stu-id="915d7-165">![The Cache Storage dropdown][ImageMultipleCaches]</span></span>  

## <span data-ttu-id="915d7-166">配额使用情况</span><span class="sxs-lookup"><span data-stu-id="915d7-166">Quota usage</span></span> 

<span data-ttu-id="915d7-167">"缓存存储" 窗格中的某些响应可能标记为 "不**透明**"。</span><span class="sxs-lookup"><span data-stu-id="915d7-167">Some responses within the Cache Storage pane may be flagged as being "**opaque**".</span></span>  <span data-ttu-id="915d7-168">这是指从不同来源（例如从**CDN**或远程 API）检索的响应未启用[CORS][FetchHttpCorsProtocol] 。</span><span class="sxs-lookup"><span data-stu-id="915d7-168">This refers to a response retrieved from a different origin, like from a **CDN** or remote API, when [CORS][FetchHttpCorsProtocol] is not enabled.</span></span>  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

<span data-ttu-id="915d7-169">为了避免跨域信息的泄漏，对用于计算存储配额限制的不透明响应的大小增加了明显的填充值（例如是否 `QuotaExceeded` 引发了异常 \）和由 **`navigator.storage`** API 报告。</span><span class="sxs-lookup"><span data-stu-id="915d7-169">In order to avoid leakage of cross-domain information, there's significant padding added to the size of an opaque response used for calculating storage quota limits \(for example whether a `QuotaExceeded` exception is thrown\) and reported by the **`navigator.storage`** API.</span></span>  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

<span data-ttu-id="915d7-170">此填充的详细信息因浏览器的不同而不同，但对于 Microsoft Edge，这意味着任何单个缓存的不透明响应对总体存储使用率的**最小大小**[约为7兆字节][ChromiumIssues796060#c17]。</span><span class="sxs-lookup"><span data-stu-id="915d7-170">The details of this padding vary from browser to browser, but for Microsoft Edge, this means that the **minimum size** that any single cached opaque response contributes to the overall storage usage is [approximately 7 megabytes][ChromiumIssues796060#c17].</span></span>  <span data-ttu-id="915d7-171">在确定要缓存的不透明响应的数量时，应牢记这一点，因为你可以比其他预期更快地减少存储配额限制，具体取决于不透明资源的实际大小。</span><span class="sxs-lookup"><span data-stu-id="915d7-171">You should keep this in mind when determining how many opaque responses you want to cache, since you could easily exceeded storage quota limitations much sooner than you'd otherwise expect based on the actual size of the opaque resources.</span></span>  

<span data-ttu-id="915d7-172">相关指南：</span><span class="sxs-lookup"><span data-stu-id="915d7-172">Related Guides:</span></span>  

*   [<span data-ttu-id="915d7-173">堆栈溢出：不透明答复适用的限制是什么？</span><span class="sxs-lookup"><span data-stu-id="915d7-173">Stack Overflow: What limitations apply to opaque responses?</span></span>][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->

<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## <span data-ttu-id="915d7-174">清除存储空间</span><span class="sxs-lookup"><span data-stu-id="915d7-174">Clear storage</span></span> 

<span data-ttu-id="915d7-175">在开发渐进式 web 应用时，"**清除存储**" 窗格是非常有用的功能。</span><span class="sxs-lookup"><span data-stu-id="915d7-175">The **Clear Storage** pane is a very useful feature when developing progressive web apps.</span></span>  <span data-ttu-id="915d7-176">此窗格允许你注销服务工作人员并通过单个按钮单击来清除所有缓存和存储。</span><span class="sxs-lookup"><span data-stu-id="915d7-176">This pane lets you unregister service workers and clear all caches and storage with a single button click.</span></span>  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->

<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides 

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->

<!--TODO  -->

 



<!-- image links -->  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/manifest-pane.msft.png "图1：清单窗格"  
<!--[ImageDesktopShelf]: /microsoft-edge/devtools-guide-chromium/media/io.msft.png "Add to desktop shelf"  -->
<span data-ttu-id="915d7-178">[ImageServiceWorkersPane]：/microsoft-edge/devtools-guide-chromium/media/service-workers-pane.msft.png "图2：服务工作者窗格"</span><span class="sxs-lookup"><span data-stu-id="915d7-178">[ImageServiceWorkersPane]: /microsoft-edge/devtools-guide-chromium/media/service-workers-pane.msft.png "Figure 2: The Service Workers pane"</span></span>  
<!--[ImageServiceWorkerErrors]: /microsoft-edge/devtools-guide-chromium/media/sw-error.msft.png "Service worker with errors"  -->
<span data-ttu-id="915d7-179">[ImageServiceWorkersCachePane]：/microsoft-edge/devtools-guide-chromium/media/cache-pane-cache-storage-resources.msft.png "图3：缓存存储" 窗格 "</span><span class="sxs-lookup"><span data-stu-id="915d7-179">[ImageServiceWorkersCachePane]: /microsoft-edge/devtools-guide-chromium/media/cache-pane-cache-storage-resources.msft.png "Figure 3: The Cache Storage Pane"</span></span>  
<span data-ttu-id="915d7-180">[ImageMultipleCaches]：/microsoft-edge/devtools-guide-chromium/media/cache-pane-cache-storage.msft.png "图4：**缓存存储**" 下拉列表 "</span><span class="sxs-lookup"><span data-stu-id="915d7-180">[ImageMultipleCaches]: /microsoft-edge/devtools-guide-chromium/media/cache-pane-cache-storage.msft.png "Figure 4: The **Cache Storage** dropdown"</span></span>  

<!-- links -->  

[DevtoolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium 问题796060：当分析代码位于 html 中时，缓存存储值将在每次刷新时上升"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "缓存-Web Api |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "堆栈溢出：不透明答复适用的限制是什么？"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> <span data-ttu-id="915d7-185">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="915d7-185">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="915d7-186">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="915d7-186">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="915d7-188">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="915d7-188">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
