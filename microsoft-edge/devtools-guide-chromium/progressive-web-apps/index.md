---
description: 使用应用程序面板检查、修改和调试 Web 应用清单、服务工作者和服务工作者缓存。
title: 调试渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: aea01d25474a030e78ac0eaeaef3954ab7f4539f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398537"
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

# <a name="debug-progressive-web-apps"></a><span data-ttu-id="618ce-104">调试渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="618ce-104">Debug Progressive Web Apps</span></span>  

<span data-ttu-id="618ce-105">使用 **应用程序** 面板检查、修改和调试 Web 应用清单、服务工作者和服务工作者缓存。</span><span class="sxs-lookup"><span data-stu-id="618ce-105">Use the **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

<span data-ttu-id="618ce-106">本指南仅讨论应用程序面板的渐进式 **Web 应用** 功能。</span><span class="sxs-lookup"><span data-stu-id="618ce-106">This guide only discusses the Progressive Web App features of the **Application** panel.</span></span>  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### <a name="summary"></a><span data-ttu-id="618ce-107">摘要</span><span class="sxs-lookup"><span data-stu-id="618ce-107">Summary</span></span>  

*   <span data-ttu-id="618ce-108">使用清单 **窗格** 检查 Web 应用清单并触发"添加到主屏幕"事件。</span><span class="sxs-lookup"><span data-stu-id="618ce-108">Use the **Manifest** pane to inspect your web app manifest and trigger Add to Homescreen events.</span></span>  
*   <span data-ttu-id="618ce-109">对与\*\*\*\* 服务工作者相关的所有任务使用"服务工作者"窗格，例如取消注册或更新服务、模拟推送事件、脱机或停止服务工作者。</span><span class="sxs-lookup"><span data-stu-id="618ce-109">Use the **Service Workers** pane for a whole range of service-worker-related tasks, like unregistering or updating a service, emulating push events, going offline, or stopping a service worker.</span></span>  
*   <span data-ttu-id="618ce-110">从"缓存存储"窗格中查看 **服务工作线程** 缓存。</span><span class="sxs-lookup"><span data-stu-id="618ce-110">View your service worker cache from the **Cache Storage** pane.</span></span>  
*   <span data-ttu-id="618ce-111">通过"清除存储"窗格中的单个按钮取消注册服务工作器并 **清除所有存储和** 缓存。</span><span class="sxs-lookup"><span data-stu-id="618ce-111">Unregister a service worker and clear all storage and caches with a single button choose from the **Clear storage** pane.</span></span>  
    
## <a name="web-app-manifest"></a><span data-ttu-id="618ce-112">Web 应用清单</span><span class="sxs-lookup"><span data-stu-id="618ce-112">Web app manifest</span></span>  

<span data-ttu-id="618ce-113">如果希望用户能够将应用添加到其移动主屏幕，则需要 Web 应用清单。</span><span class="sxs-lookup"><span data-stu-id="618ce-113">If you want your users to be able to add your app to their mobile homescreens, you need a web app manifest.</span></span>  <span data-ttu-id="618ce-114">清单定义应用在主屏幕上的显示方式、从主屏幕启动时引导用户位置，以及应用在启动时的外观。</span><span class="sxs-lookup"><span data-stu-id="618ce-114">The manifest defines how the app appears on the homescreen, where to direct the user when launching from homescreen, and what the app looks like on launch.</span></span>  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

<span data-ttu-id="618ce-115">设置清单后，可以使用应用程序面板的清单窗格进行检查。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="618ce-115">After you have your manifest set up, you may use the **Manifest** pane of the **Application** panel to inspect it.</span></span>  

:::image type="complex" source="../media/manifest-pane.msft.png" alt-text="清单窗格" lightbox="../media/manifest-pane.msft.png":::
   <span data-ttu-id="618ce-117">清单**窗格**</span><span class="sxs-lookup"><span data-stu-id="618ce-117">The **Manifest** Pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="618ce-118">若要查看清单源，请选择上图中应用 **清单标签** \ (`https://airhorner.com/manifest.json` 下的链接\) 。</span><span class="sxs-lookup"><span data-stu-id="618ce-118">To look at the manifest source, choose the link below **App Manifest** label \(`https://airhorner.com/manifest.json` in the previous figure\).</span></span>  
<!-- *   Choose the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   <span data-ttu-id="618ce-119">" **标识** " **和** "演示文稿"部分仅以更用户友好的显示方式显示清单源中的字段。</span><span class="sxs-lookup"><span data-stu-id="618ce-119">The **Identity** and **Presentation** sections just display fields from the manifest source in a more user-friendly display.</span></span>  
*   <span data-ttu-id="618ce-120">" **图标** "部分显示你指定的每个图标。</span><span class="sxs-lookup"><span data-stu-id="618ce-120">The **Icons** section displays every icon that you've specified.</span></span>  
    
<!--### Simulate Add to Homescreen events  -->

<!--A web app may only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, the criteria is potentially inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You may test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Choosing on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="../media/io.msft.png" alt-text="Add to desktop shelf" lightbox="../media/io.msft.png":::
   Add to desktop shelf  
:::image-end:::
-->  

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature may not yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you may successfully add your app to your desktop shelf, then it works for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you may connect a real mobile device to DevTools via **remote debugging**, and then choose the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## <a name="service-workers"></a><span data-ttu-id="618ce-121">服务工作者</span><span class="sxs-lookup"><span data-stu-id="618ce-121">Service workers</span></span>  

<span data-ttu-id="618ce-122">服务工作者是未来 Web 平台中的基础技术。</span><span class="sxs-lookup"><span data-stu-id="618ce-122">Service workers are a fundamental technology in the future web platform.</span></span>  <span data-ttu-id="618ce-123">它们是浏览器在后台运行的脚本，独立于网页。</span><span class="sxs-lookup"><span data-stu-id="618ce-123">They are scripts that the browser runs in the background, separate from a web page.</span></span>  <span data-ttu-id="618ce-124">这些脚本允许你访问无需网页或用户交互的功能，如推送通知、后台同步和脱机体验。</span><span class="sxs-lookup"><span data-stu-id="618ce-124">The scripts allow you to access features that without the need of a web page or user interaction, like push notifications, background sync, and offline experiences.</span></span>  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

<span data-ttu-id="618ce-125">应用程序**面板**中的"服务工作人员\*\*\*\*"窗格是 DevTools 中用于检查和调试服务工作者的主要位置。</span><span class="sxs-lookup"><span data-stu-id="618ce-125">The **Service Workers** pane in the **Application** panel is the main place in DevTools to inspect and debug service workers.</span></span>  

:::image type="complex" source="../media/service-workers-pane.msft.png" alt-text=""服务工作人员"窗格" lightbox="../media/service-workers-pane.msft.png":::
   <span data-ttu-id="618ce-127">" **服务工作人员"** 窗格</span><span class="sxs-lookup"><span data-stu-id="618ce-127">The **Service Workers** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="618ce-128">如果将服务工作器安装到当前打开的页面，则它会在此窗格中列出。</span><span class="sxs-lookup"><span data-stu-id="618ce-128">If a service worker is installed to the currently open page, then it is listed on this pane.</span></span>  <span data-ttu-id="618ce-129">例如，在上图中，为 范围安装了一个服务工作器 `https://weather-pwa-sample.firebaseapp.com` 。</span><span class="sxs-lookup"><span data-stu-id="618ce-129">For example, in the previous figure, there is a service worker installed for the scope of `https://weather-pwa-sample.firebaseapp.com`.</span></span>  
*   <span data-ttu-id="618ce-130">" **脱机** "复选框将 DevTools 置于脱机模式。</span><span class="sxs-lookup"><span data-stu-id="618ce-130">The **Offline** checkbox puts DevTools into offline mode.</span></span>  <span data-ttu-id="618ce-131">这等效于从网络工具或命令菜单中的选项\*\*\*\* 提供的 `Go offline` [脱机模式][DevtoolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="618ce-131">This is equivalent to the offline mode available from the **Network** tool, or the `Go offline` option in the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
*   <span data-ttu-id="618ce-132">重新加载 **时更新复选框** 强制服务工作者每次加载页面时进行更新。</span><span class="sxs-lookup"><span data-stu-id="618ce-132">The **Update on reload** checkbox forces the service worker to update on every page load.</span></span>  
*   <span data-ttu-id="618ce-133">" **绕过网络"** 复选框将绕过服务工作者，并强制浏览器转到网络，以请求资源。</span><span class="sxs-lookup"><span data-stu-id="618ce-133">The **Bypass for network** checkbox bypasses the service worker and forces the browser to go to the network for requested resources.</span></span>  
*   <span data-ttu-id="618ce-134">" **更新** "按钮执行指定服务工作者的一次更新。</span><span class="sxs-lookup"><span data-stu-id="618ce-134">The **Update** button performs a one-time update of the specified service worker.</span></span>  
*   <span data-ttu-id="618ce-135">推送**按钮**模拟没有有效负载的推送通知 (代码**\) 。**</span><span class="sxs-lookup"><span data-stu-id="618ce-135">The **Push** button emulates a push notification without a payload \(also known as a **tickle**\).</span></span>  
*   <span data-ttu-id="618ce-136">" **同步** "按钮模拟后台同步事件。</span><span class="sxs-lookup"><span data-stu-id="618ce-136">The **Sync** button emulates a background sync event.</span></span>  
*   <span data-ttu-id="618ce-137">" **取消注册"** 按钮将取消注册指定的服务工作线程。</span><span class="sxs-lookup"><span data-stu-id="618ce-137">The **Unregister** button unregisters the specified service worker.</span></span>  <span data-ttu-id="618ce-138">查看 ["清除存储](#clear-storage) "，了解通过单一按钮选择注销服务工作器以及擦除存储和缓存的方法。</span><span class="sxs-lookup"><span data-stu-id="618ce-138">Check out [Clear storage](#clear-storage) for a way to unregister a service worker and wipe storage and caches with a single button choose.</span></span>  
*   <span data-ttu-id="618ce-139">源 **行** 将告知您当前正在运行的服务工作线程的安装时间。</span><span class="sxs-lookup"><span data-stu-id="618ce-139">The **Source** line tells you when the currently running service worker was installed.</span></span>  <span data-ttu-id="618ce-140">该链接是服务工作者的源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="618ce-140">The link is the name of the source file of the service worker.</span></span>  <span data-ttu-id="618ce-141">选择链接将你发送到服务工作者的源。</span><span class="sxs-lookup"><span data-stu-id="618ce-141">Choosing on the link sends you to the source of the service worker.</span></span>  
*   <span data-ttu-id="618ce-142">状态 **行** 将告知您服务工作线程的状态。</span><span class="sxs-lookup"><span data-stu-id="618ce-142">The **Status** line tells you the status of the service worker.</span></span>  <span data-ttu-id="618ce-143">上图中绿色状态指示器 \ (\) 表示当前活动服务工作线程的 ID `#36` 号。</span><span class="sxs-lookup"><span data-stu-id="618ce-143">The ID number next to the green status indicator \(`#36` in previous figure\) is for the currently active Service Worker.</span></span>  <span data-ttu-id="618ce-144">在状态旁边，如果服务\*\*\*\* 工作线程已停止，则 (\) ，或者，如果服务工作进程正在运行，则\*\*\*\* 显示停止按钮 \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="618ce-144">Next to the status, a **start** button \(if the service worker is stopped\) or a **stop** button \(if the service worker is running\) is displayed.</span></span>  <span data-ttu-id="618ce-145">服务工作者设计为随时由浏览器停止和启动。</span><span class="sxs-lookup"><span data-stu-id="618ce-145">Service workers are designed to be stopped and started by the browser at any time.</span></span>  <span data-ttu-id="618ce-146">使用停止按钮显式停止 **服务工作者可能会** 模拟这一点。</span><span class="sxs-lookup"><span data-stu-id="618ce-146">Explicitly stopping your service worker using the **stop** button may simulate that.</span></span>  <span data-ttu-id="618ce-147">停止服务工作者是测试服务工作线程再次启动备份时代码行为方式的一种很好方法。</span><span class="sxs-lookup"><span data-stu-id="618ce-147">Stopping your service worker is a great way to test how your code behaves when the service worker starts back up again.</span></span>  <span data-ttu-id="618ce-148">由于对永久性全局状态的错误假设，它经常显示 Bug。</span><span class="sxs-lookup"><span data-stu-id="618ce-148">It frequently reveals bugs due to faulty assumptions about persistent global state.</span></span>  
*   <span data-ttu-id="618ce-149">客户端 **行** 会告知您服务工作器作用域的源。</span><span class="sxs-lookup"><span data-stu-id="618ce-149">The **Clients** line tells you the origin that the service worker is scoped to.</span></span>  <span data-ttu-id="618ce-150">当你 **启用** "全部显示"复选框时，焦点 **按钮非常有用** 。</span><span class="sxs-lookup"><span data-stu-id="618ce-150">The **focus** button is mostly useful when you've enabled the **show all** checkbox.</span></span>  <span data-ttu-id="618ce-151">启用该复选框后，将列出所有注册的服务工作者。</span><span class="sxs-lookup"><span data-stu-id="618ce-151">When that checkbox is enabled, all registered service workers are listed.</span></span>  <span data-ttu-id="618ce-152">如果选择其他选项卡中运行\*\*\*\* 的服务工作线程旁边的焦点按钮，Microsoft Edge 将焦点放在该选项卡上。</span><span class="sxs-lookup"><span data-stu-id="618ce-152">If you choose on the **focus** button next to a service worker that is running in a different tab, Microsoft Edge focuses on that tab.</span></span>  
    
<span data-ttu-id="618ce-153">如果服务工作线程导致任何错误，将显示名为 **"错误** "的新标签。</span><span class="sxs-lookup"><span data-stu-id="618ce-153">If the service worker causes any errors, a new label called **Errors** shows up.</span></span>  

<!--  
:::image type="complex" source="../media/sw-error.msft.png" alt-text="Service worker with errors" lightbox="../media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## <a name="service-worker-caches"></a><span data-ttu-id="618ce-154">服务工作线程缓存</span><span class="sxs-lookup"><span data-stu-id="618ce-154">Service worker caches</span></span>  

<span data-ttu-id="618ce-155">缓存 **存储** 窗格提供已使用 \ (Service worker\) [缓存 API][MDNWebCacheAPI]缓存的资源的只读列表。</span><span class="sxs-lookup"><span data-stu-id="618ce-155">The **Cache Storage** pane provides a read-only list of resources that have been cached using the \(service worker\) [Cache API][MDNWebCacheAPI].</span></span>  

:::image type="complex" source="../media/cache-pane-cache-storage-resources.msft.png" alt-text="缓存存储窗格" lightbox="../media/cache-pane-cache-storage-resources.msft.png":::
   <span data-ttu-id="618ce-157">缓存 **存储** 窗格</span><span class="sxs-lookup"><span data-stu-id="618ce-157">The **Cache Storage** Pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="618ce-158">首次打开缓存并添加资源时，DevTools 可能无法检测到更改。</span><span class="sxs-lookup"><span data-stu-id="618ce-158">The first time you open a cache and add a resource to it, DevTools may not detect the change.</span></span>  <span data-ttu-id="618ce-159">刷新页面并显示缓存。</span><span class="sxs-lookup"><span data-stu-id="618ce-159">Refresh the page and to display the cache.</span></span>  

<span data-ttu-id="618ce-160">如果您打开了两个或多个缓存，则缓存会显示在下面的 **"** 缓存存储"下拉列表下。</span><span class="sxs-lookup"><span data-stu-id="618ce-160">If you have two or more caches open, the caches display under the following **Cache Storage** dropdown.</span></span>  

:::image type="complex" source="../media/cache-pane-cache-storage.msft.png" alt-text=""缓存存储"下拉列表" lightbox="../media/cache-pane-cache-storage.msft.png":::
   <span data-ttu-id="618ce-162">" **缓存存储"** 下拉列表</span><span class="sxs-lookup"><span data-stu-id="618ce-162">The **Cache Storage** dropdown</span></span>  
:::image-end:::  

## <a name="quota-usage"></a><span data-ttu-id="618ce-163">配额使用情况</span><span class="sxs-lookup"><span data-stu-id="618ce-163">Quota usage</span></span>  

<span data-ttu-id="618ce-164">缓存存储窗格中 **的一** 些响应可能标记为"不透明"。</span><span class="sxs-lookup"><span data-stu-id="618ce-164">Some responses within the **Cache Storage** pane may be flagged as being "opaque".</span></span>  <span data-ttu-id="618ce-165">这是指未启用[CORS][FetchHttpCorsProtocol]时从不同源（如**CDN**或远程 API）检索到的响应。</span><span class="sxs-lookup"><span data-stu-id="618ce-165">This refers to a response retrieved from a different origin, like from a **CDN** or remote API, when [CORS][FetchHttpCorsProtocol] is not enabled.</span></span>  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

<span data-ttu-id="618ce-166">为了避免跨域信息泄露，会向用于计算存储配额限制的不透明响应的大小添加大量填充 (例如是否引发 `QuotaExceeded` 异常\) API 报告异常。 `navigator.storage`</span><span class="sxs-lookup"><span data-stu-id="618ce-166">In order to avoid leakage of cross-domain information, significant padding is added to the size of an opaque response used for calculating storage quota limits \(for example whether a `QuotaExceeded` exception is thrown\) and reported by the `navigator.storage` API.</span></span>  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

<span data-ttu-id="618ce-167">此填充的详细信息因浏览器而异，但对于 Microsoft Edge，这意味着任何单个缓存的不透明响应对\*\*\*\* 整体存储使用率的影响最小大小约为[7 MB。][ChromiumIssues796060#c17]</span><span class="sxs-lookup"><span data-stu-id="618ce-167">The details of this padding vary from browser to browser, but for Microsoft Edge, this means that the **minimum size** that any single cached opaque response contributes to the overall storage usage is [approximately 7 megabytes][ChromiumIssues796060#c17].</span></span>  <span data-ttu-id="618ce-168">在确定要缓存的不透明响应数量时，请记住填充，因为根据不透明资源的实际大小，你可以轻松超过存储配额限制，这比否则预期要快得多。</span><span class="sxs-lookup"><span data-stu-id="618ce-168">Remember the padding when determining how many opaque responses you want to cache, since you may easily exceed storage quota limitations much sooner than you otherwise expect based on the actual size of the opaque resources.</span></span>  

<span data-ttu-id="618ce-169">相关指南：</span><span class="sxs-lookup"><span data-stu-id="618ce-169">Related Guides:</span></span>  

*   [<span data-ttu-id="618ce-170">Stack Overflow：哪些限制适用于不透明的响应？</span><span class="sxs-lookup"><span data-stu-id="618ce-170">Stack Overflow: What limitations apply to opaque responses?</span></span>][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## <a name="clear-storage"></a><span data-ttu-id="618ce-171">清除存储</span><span class="sxs-lookup"><span data-stu-id="618ce-171">Clear storage</span></span>  

<span data-ttu-id="618ce-172">" **清除存储** "窗格是开发渐进式 Web 应用时非常有用的功能。</span><span class="sxs-lookup"><span data-stu-id="618ce-172">The **Clear Storage** pane is a very useful feature when developing progressive web apps.</span></span>  <span data-ttu-id="618ce-173">通过此窗格，可以取消注册服务工作者，并清除所有缓存和存储，并可以选择单个按钮。</span><span class="sxs-lookup"><span data-stu-id="618ce-173">This pane lets you unregister service workers and clear all caches and storage with a single button choose.</span></span>  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides   

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="618ce-174">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="618ce-174">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium 问题 796060：当分析代码位于 html 中时，缓存存储值每次刷新时会上升"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 - Web API |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "Stack Overflow：哪些限制适用于不透明的响应？"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> <span data-ttu-id="618ce-179">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="618ce-179">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="618ce-180">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="618ce-180">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="618ce-182">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="618ce-182">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
