---
description: Use the Application panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.
title: Debug Progressive Web Apps
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 7eb71d0d57d8a9227a54b921f15dfe434ad6e65b
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993602"
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





# <span data-ttu-id="ff17e-104">Debug Progressive Web Apps</span><span class="sxs-lookup"><span data-stu-id="ff17e-104">Debug Progressive Web Apps</span></span>   



<span data-ttu-id="ff17e-105">Use the **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span><span class="sxs-lookup"><span data-stu-id="ff17e-105">Use the **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

<span data-ttu-id="ff17e-106">This guide only discusses the Progressive Web App features of the **Application** panel.</span><span class="sxs-lookup"><span data-stu-id="ff17e-106">This guide only discusses the Progressive Web App features of the **Application** panel.</span></span>  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### <span data-ttu-id="ff17e-107">Summary</span><span class="sxs-lookup"><span data-stu-id="ff17e-107">Summary</span></span>  

*   <span data-ttu-id="ff17e-108">Use the **Manifest** pane to inspect your web app manifest and trigger Add to Homescreen events.</span><span class="sxs-lookup"><span data-stu-id="ff17e-108">Use the **Manifest** pane to inspect your web app manifest and trigger Add to Homescreen events.</span></span>  
*   <span data-ttu-id="ff17e-109">Use the **Service Workers** pane for a whole range of service-worker-related tasks, like unregistering or updating a service, emulating push events, going offline, or stopping a service worker.</span><span class="sxs-lookup"><span data-stu-id="ff17e-109">Use the **Service Workers** pane for a whole range of service-worker-related tasks, like unregistering or updating a service, emulating push events, going offline, or stopping a service worker.</span></span>  
*   <span data-ttu-id="ff17e-110">View your service worker cache from the **Cache Storage** pane.</span><span class="sxs-lookup"><span data-stu-id="ff17e-110">View your service worker cache from the **Cache Storage** pane.</span></span>  
*   <span data-ttu-id="ff17e-111">Unregister a service worker and clear all storage and caches with a single button click from the **Clear storage** pane.</span><span class="sxs-lookup"><span data-stu-id="ff17e-111">Unregister a service worker and clear all storage and caches with a single button click from the **Clear storage** pane.</span></span>  
    
## <span data-ttu-id="ff17e-112">Web app manifest</span><span class="sxs-lookup"><span data-stu-id="ff17e-112">Web app manifest</span></span>   

<span data-ttu-id="ff17e-113">If you want your users to be able to add your app to their mobile homescreens, you need a web app manifest.</span><span class="sxs-lookup"><span data-stu-id="ff17e-113">If you want your users to be able to add your app to their mobile homescreens, you need a web app manifest.</span></span>  <span data-ttu-id="ff17e-114">The manifest defines how the app appears on the homescreen, where to direct the user when launching from homescreen, and what the app looks like on launch.</span><span class="sxs-lookup"><span data-stu-id="ff17e-114">The manifest defines how the app appears on the homescreen, where to direct the user when launching from homescreen, and what the app looks like on launch.</span></span>  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

<span data-ttu-id="ff17e-115">After you have your manifest set up, you can use the **Manifest** pane of the **Application** panel to inspect it.</span><span class="sxs-lookup"><span data-stu-id="ff17e-115">After you have your manifest set up, you can use the **Manifest** pane of the **Application** panel to inspect it.</span></span>  

:::image type="complex" source="./media/manifest-pane.msft.png" alt-text="The Manifest Pane" lightbox="./media/manifest-pane.msft.png":::
   <span data-ttu-id="ff17e-117">The **Manifest** Pane</span><span class="sxs-lookup"><span data-stu-id="ff17e-117">The **Manifest** Pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="ff17e-118">To look at the manifest source, click the link below **App Manifest** label \(`https://airhorner.com/manifest.json` in the previous figure\).</span><span class="sxs-lookup"><span data-stu-id="ff17e-118">To look at the manifest source, click the link below **App Manifest** label \(`https://airhorner.com/manifest.json` in the previous figure\).</span></span>  
<!-- *   Press the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   <span data-ttu-id="ff17e-119">The **Identity** and **Presentation** sections just display fields from the manifest source in a more user-friendly display.</span><span class="sxs-lookup"><span data-stu-id="ff17e-119">The **Identity** and **Presentation** sections just display fields from the manifest source in a more user-friendly display.</span></span>  
*   <span data-ttu-id="ff17e-120">The **Icons** section displays every icon that you've specified.</span><span class="sxs-lookup"><span data-stu-id="ff17e-120">The **Icons** section displays every icon that you've specified.</span></span>  
    
<!--### Simulate Add to Homescreen events   -->

<!--A web app can only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, this criteria can be inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You can test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Clicking on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="./media/io.msft.png" alt-text="The Manifest Pane" lightbox="./media/io.msft.png":::
   Add to desktop shelf  
:::image-end:::
-->  

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature cannot yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you can successfully add your app to your desktop shelf, then it'll work for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you can connect a real mobile device to DevTools via **remote debugging**, and then click the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## <span data-ttu-id="ff17e-121">Service workers</span><span class="sxs-lookup"><span data-stu-id="ff17e-121">Service workers</span></span>   

<span data-ttu-id="ff17e-122">Service workers are a fundamental technology in the future web platform.</span><span class="sxs-lookup"><span data-stu-id="ff17e-122">Service workers are a fundamental technology in the future web platform.</span></span>  <span data-ttu-id="ff17e-123">They are scripts that the browser runs in the background, separate from a web page.</span><span class="sxs-lookup"><span data-stu-id="ff17e-123">They are scripts that the browser runs in the background, separate from a web page.</span></span>  <span data-ttu-id="ff17e-124">These scripts enable you to access features that don't need a web page or user interaction, like push notifications, background sync, and offline experiences.</span><span class="sxs-lookup"><span data-stu-id="ff17e-124">These scripts enable you to access features that don't need a web page or user interaction, like push notifications, background sync, and offline experiences.</span></span>  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

<span data-ttu-id="ff17e-125">The **Service Workers** pane in the **Application** panel is the main place in DevTools to inspect and debug service workers.</span><span class="sxs-lookup"><span data-stu-id="ff17e-125">The **Service Workers** pane in the **Application** panel is the main place in DevTools to inspect and debug service workers.</span></span>  

:::image type="complex" source="./media/service-workers-pane.msft.png" alt-text="The Manifest Pane" lightbox="./media/service-workers-pane.msft.png":::
   <span data-ttu-id="ff17e-127">The **Service Workers** pane</span><span class="sxs-lookup"><span data-stu-id="ff17e-127">The **Service Workers** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="ff17e-128">If a service worker is installed to the currently open page, then you'll see it listed on this pane.</span><span class="sxs-lookup"><span data-stu-id="ff17e-128">If a service worker is installed to the currently open page, then you'll see it listed on this pane.</span></span>  <span data-ttu-id="ff17e-129">For example, in the previous figure, there is a service worker installed for the scope of `https://weather-pwa-sample.firebaseapp.com`.</span><span class="sxs-lookup"><span data-stu-id="ff17e-129">For example, in the previous figure, there is a service worker installed for the scope of `https://weather-pwa-sample.firebaseapp.com`.</span></span>  
*   <span data-ttu-id="ff17e-130">The **Offline** checkbox puts DevTools into offline mode.</span><span class="sxs-lookup"><span data-stu-id="ff17e-130">The **Offline** checkbox puts DevTools into offline mode.</span></span>  <span data-ttu-id="ff17e-131">This is equivalent to the offline mode available from the **Network** panel, or the `Go offline` option in the [Command Menu][DevtoolsCommandMenuIndex].</span><span class="sxs-lookup"><span data-stu-id="ff17e-131">This is equivalent to the offline mode available from the **Network** panel, or the `Go offline` option in the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
*   <span data-ttu-id="ff17e-132">The **Update on reload** checkbox forces the service worker to update on every page load.</span><span class="sxs-lookup"><span data-stu-id="ff17e-132">The **Update on reload** checkbox forces the service worker to update on every page load.</span></span>  
*   <span data-ttu-id="ff17e-133">The **Bypass for network** checkbox bypasses the service worker and forces the browser to go to the network for requested resources.</span><span class="sxs-lookup"><span data-stu-id="ff17e-133">The **Bypass for network** checkbox bypasses the service worker and forces the browser to go to the network for requested resources.</span></span>  
*   <span data-ttu-id="ff17e-134">The **Update** button performs a one-time update of the specified service worker.</span><span class="sxs-lookup"><span data-stu-id="ff17e-134">The **Update** button performs a one-time update of the specified service worker.</span></span>  
*   <span data-ttu-id="ff17e-135">The **Push** button emulates a push notification without a payload \(also known as a **tickle**\).</span><span class="sxs-lookup"><span data-stu-id="ff17e-135">The **Push** button emulates a push notification without a payload \(also known as a **tickle**\).</span></span>  
*   <span data-ttu-id="ff17e-136">The **Sync** button emulates a background sync event.</span><span class="sxs-lookup"><span data-stu-id="ff17e-136">The **Sync** button emulates a background sync event.</span></span>  
*   <span data-ttu-id="ff17e-137">The **Unregister** button unregisters the specified service worker.</span><span class="sxs-lookup"><span data-stu-id="ff17e-137">The **Unregister** button unregisters the specified service worker.</span></span>  <span data-ttu-id="ff17e-138">Check out [Clear storage](#clear-storage) for a way to unregister a service worker and wipe storage and caches with a single button click.</span><span class="sxs-lookup"><span data-stu-id="ff17e-138">Check out [Clear storage](#clear-storage) for a way to unregister a service worker and wipe storage and caches with a single button click.</span></span>  
*   <span data-ttu-id="ff17e-139">The **Source** line tells you when the currently running service worker was installed.</span><span class="sxs-lookup"><span data-stu-id="ff17e-139">The **Source** line tells you when the currently running service worker was installed.</span></span>  <span data-ttu-id="ff17e-140">The link is the name of the service worker's source file.</span><span class="sxs-lookup"><span data-stu-id="ff17e-140">The link is the name of the service worker's source file.</span></span>  <span data-ttu-id="ff17e-141">Clicking on the link sends you to the service worker's source.</span><span class="sxs-lookup"><span data-stu-id="ff17e-141">Clicking on the link sends you to the service worker's source.</span></span>  
*   <span data-ttu-id="ff17e-142">The **Status** line tells you the status of the service worker.</span><span class="sxs-lookup"><span data-stu-id="ff17e-142">The **Status** line tells you the status of the service worker.</span></span>  <span data-ttu-id="ff17e-143">The ID number next to the green status indicator \(`#36` in previous figure\) is for the currently active Service Worker.</span><span class="sxs-lookup"><span data-stu-id="ff17e-143">The ID number next to the green status indicator \(`#36` in previous figure\) is for the currently active Service Worker.</span></span>  <span data-ttu-id="ff17e-144">Next to the status you'll see a **start** button \(if the service worker is stopped\) or a **stop** button \(if the service worker is running\).</span><span class="sxs-lookup"><span data-stu-id="ff17e-144">Next to the status you'll see a **start** button \(if the service worker is stopped\) or a **stop** button \(if the service worker is running\).</span></span>  <span data-ttu-id="ff17e-145">Service workers are designed to be stopped and started by the browser at any time.</span><span class="sxs-lookup"><span data-stu-id="ff17e-145">Service workers are designed to be stopped and started by the browser at any time.</span></span>  <span data-ttu-id="ff17e-146">Explicitly stopping your service worker using the **stop** button can simulate that.</span><span class="sxs-lookup"><span data-stu-id="ff17e-146">Explicitly stopping your service worker using the **stop** button can simulate that.</span></span>  <span data-ttu-id="ff17e-147">Stopping your service worker is a great way to test how your code behaves when the service worker starts back up again.</span><span class="sxs-lookup"><span data-stu-id="ff17e-147">Stopping your service worker is a great way to test how your code behaves when the service worker starts back up again.</span></span>  <span data-ttu-id="ff17e-148">It frequently reveals bugs due to faulty assumptions about persistent global state.</span><span class="sxs-lookup"><span data-stu-id="ff17e-148">It frequently reveals bugs due to faulty assumptions about persistent global state.</span></span>  
*   <span data-ttu-id="ff17e-149">The **Clients** line tells you the origin that the service worker is scoped to.</span><span class="sxs-lookup"><span data-stu-id="ff17e-149">The **Clients** line tells you the origin that the service worker is scoped to.</span></span>  <span data-ttu-id="ff17e-150">The **focus** button is mostly useful when you've enabled the **show all** checkbox.</span><span class="sxs-lookup"><span data-stu-id="ff17e-150">The **focus** button is mostly useful when you've enabled the **show all** checkbox.</span></span>  <span data-ttu-id="ff17e-151">When that checkbox is enabled, all registered service workers are listed.</span><span class="sxs-lookup"><span data-stu-id="ff17e-151">When that checkbox is enabled, all registered service workers are listed.</span></span>  <span data-ttu-id="ff17e-152">If you click on the **focus** button next to a service worker that is running in a different tab, Microsoft Edge focuses on that tab.</span><span class="sxs-lookup"><span data-stu-id="ff17e-152">If you click on the **focus** button next to a service worker that is running in a different tab, Microsoft Edge focuses on that tab.</span></span>  
    
<span data-ttu-id="ff17e-153">If the service worker causes any errors, a new label called **Errors** shows up.</span><span class="sxs-lookup"><span data-stu-id="ff17e-153">If the service worker causes any errors, a new label called **Errors** shows up.</span></span>  

<!--  
:::image type="complex" source="./media/sw-error.msft.png" alt-text="The Manifest Pane" lightbox="./media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## <span data-ttu-id="ff17e-154">Service worker caches</span><span class="sxs-lookup"><span data-stu-id="ff17e-154">Service worker caches</span></span> 

<span data-ttu-id="ff17e-155">The **Cache Storage** pane provides a read-only list of resources that have been cached using the \(service worker\) [Cache API][MDNWebCacheAPI].</span><span class="sxs-lookup"><span data-stu-id="ff17e-155">The **Cache Storage** pane provides a read-only list of resources that have been cached using the \(service worker\) [Cache API][MDNWebCacheAPI].</span></span>  

:::image type="complex" source="./media/cache-pane-cache-storage-resources.msft.png" alt-text="The Manifest Pane" lightbox="./media/cache-pane-cache-storage-resources.msft.png":::
   <span data-ttu-id="ff17e-157">The **Cache Storage** Pane</span><span class="sxs-lookup"><span data-stu-id="ff17e-157">The **Cache Storage** Pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ff17e-158">The first time you open a cache and add a resource to it, DevTools might not detect the change.</span><span class="sxs-lookup"><span data-stu-id="ff17e-158">The first time you open a cache and add a resource to it, DevTools might not detect the change.</span></span>  <span data-ttu-id="ff17e-159">Reload the page and you should see the cache.</span><span class="sxs-lookup"><span data-stu-id="ff17e-159">Reload the page and you should see the cache.</span></span>  

<span data-ttu-id="ff17e-160">If you have two or more caches open, you'll see them listed below the **Cache Storage** dropdown.</span><span class="sxs-lookup"><span data-stu-id="ff17e-160">If you have two or more caches open, you'll see them listed below the **Cache Storage** dropdown.</span></span>  

:::image type="complex" source="./media/cache-pane-cache-storage.msft.png" alt-text="The Manifest Pane" lightbox="./media/cache-pane-cache-storage.msft.png":::
   <span data-ttu-id="ff17e-162">The **Cache Storage** dropdown</span><span class="sxs-lookup"><span data-stu-id="ff17e-162">The **Cache Storage** dropdown</span></span>  
:::image-end:::  

## <span data-ttu-id="ff17e-163">Quota usage</span><span class="sxs-lookup"><span data-stu-id="ff17e-163">Quota usage</span></span> 

<span data-ttu-id="ff17e-164">Some responses within the **Cache Storage** pane may be flagged as being "opaque".</span><span class="sxs-lookup"><span data-stu-id="ff17e-164">Some responses within the **Cache Storage** pane may be flagged as being "opaque".</span></span>  <span data-ttu-id="ff17e-165">This refers to a response retrieved from a different origin, like from a **CDN** or remote API, when [CORS][FetchHttpCorsProtocol] is not enabled.</span><span class="sxs-lookup"><span data-stu-id="ff17e-165">This refers to a response retrieved from a different origin, like from a **CDN** or remote API, when [CORS][FetchHttpCorsProtocol] is not enabled.</span></span>  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

<span data-ttu-id="ff17e-166">In order to avoid leakage of cross-domain information, there's significant padding added to the size of an opaque response used for calculating storage quota limits \(for example whether a `QuotaExceeded` exception is thrown\) and reported by the `navigator.storage` API.</span><span class="sxs-lookup"><span data-stu-id="ff17e-166">In order to avoid leakage of cross-domain information, there's significant padding added to the size of an opaque response used for calculating storage quota limits \(for example whether a `QuotaExceeded` exception is thrown\) and reported by the `navigator.storage` API.</span></span>  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

<span data-ttu-id="ff17e-167">The details of this padding vary from browser to browser, but for Microsoft Edge, this means that the **minimum size** that any single cached opaque response contributes to the overall storage usage is [approximately 7 megabytes][ChromiumIssues796060#c17].</span><span class="sxs-lookup"><span data-stu-id="ff17e-167">The details of this padding vary from browser to browser, but for Microsoft Edge, this means that the **minimum size** that any single cached opaque response contributes to the overall storage usage is [approximately 7 megabytes][ChromiumIssues796060#c17].</span></span>  <span data-ttu-id="ff17e-168">You should keep this in mind when determining how many opaque responses you want to cache, since you could easily exceeded storage quota limitations much sooner than you'd otherwise expect based on the actual size of the opaque resources.</span><span class="sxs-lookup"><span data-stu-id="ff17e-168">You should keep this in mind when determining how many opaque responses you want to cache, since you could easily exceeded storage quota limitations much sooner than you'd otherwise expect based on the actual size of the opaque resources.</span></span>  

<span data-ttu-id="ff17e-169">Related Guides:</span><span class="sxs-lookup"><span data-stu-id="ff17e-169">Related Guides:</span></span>  

*   [<span data-ttu-id="ff17e-170">Stack Overflow: What limitations apply to opaque responses?</span><span class="sxs-lookup"><span data-stu-id="ff17e-170">Stack Overflow: What limitations apply to opaque responses?</span></span>][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## <span data-ttu-id="ff17e-171">Clear storage</span><span class="sxs-lookup"><span data-stu-id="ff17e-171">Clear storage</span></span> 

<span data-ttu-id="ff17e-172">The **Clear Storage** pane is a very useful feature when developing progressive web apps.</span><span class="sxs-lookup"><span data-stu-id="ff17e-172">The **Clear Storage** pane is a very useful feature when developing progressive web apps.</span></span>  <span data-ttu-id="ff17e-173">This pane lets you unregister service workers and clear all caches and storage with a single button click.</span><span class="sxs-lookup"><span data-stu-id="ff17e-173">This pane lets you unregister service workers and clear all caches and storage with a single button click.</span></span>  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides 

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
<!--TODO  -->

<!--  
 


-->  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ./command-menu/index.md "Run commands with the Microsoft Edge DevTools Command Menu | Microsoft Docs"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium Issue 796060: Cache Storage value rises on each refresh when Analytics code is in the html"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "Cache - Web APIs | MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "Stack Overflow: What limitations apply to opaque responses?"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> <span data-ttu-id="ff17e-178">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ff17e-178">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ff17e-179">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ff17e-179">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ff17e-181">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ff17e-181">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
