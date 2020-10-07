---
description: CSS grid debugging features, Edit and Replay requests with the Network Console, and more.
title: What's new in DevTools (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 01651bdf0f36f7c175f843655c275695a680b6c1
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015459"
---
# <span data-ttu-id="5ac03-104">What's New In DevTools (Microsoft Edge 85)</span><span class="sxs-lookup"><span data-stu-id="5ac03-104">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <span data-ttu-id="5ac03-105">Announcements from the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="5ac03-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="5ac03-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span><span class="sxs-lookup"><span data-stu-id="5ac03-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="5ac03-107">See the announcements to try new features in the DevTools, Visual Studio Code extensions, and more.</span><span class="sxs-lookup"><span data-stu-id="5ac03-107">See the announcements to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="5ac03-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span><span class="sxs-lookup"><span data-stu-id="5ac03-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="5ac03-109">CSS grid debugging features</span><span class="sxs-lookup"><span data-stu-id="5ac03-109">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="Experimental feature":::
   <span data-ttu-id="5ac03-111">Experimental feature</span><span class="sxs-lookup"><span data-stu-id="5ac03-111">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-112">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span><span class="sxs-lookup"><span data-stu-id="5ac03-112">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="5ac03-113">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span><span class="sxs-lookup"><span data-stu-id="5ac03-113">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="5ac03-114">Plus, more improvements to the grid tools are coming soon.</span><span class="sxs-lookup"><span data-stu-id="5ac03-114">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="5ac03-116">CSS grid debugging features</span><span class="sxs-lookup"><span data-stu-id="5ac03-116">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5ac03-117">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span><span class="sxs-lookup"><span data-stu-id="5ac03-117">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="5ac03-118">To try out the experiment with a sample, see [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span><span class="sxs-lookup"><span data-stu-id="5ac03-118">To try out the experiment with a sample, see [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="5ac03-119">Chromium issue [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="5ac03-119">Chromium issue [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="5ac03-120">Edit and Replay requests with the Network Console</span><span class="sxs-lookup"><span data-stu-id="5ac03-120">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="Experimental feature":::
   <span data-ttu-id="5ac03-122">Experimental feature</span><span class="sxs-lookup"><span data-stu-id="5ac03-122">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-123">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span><span class="sxs-lookup"><span data-stu-id="5ac03-123">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="5ac03-125">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span><span class="sxs-lookup"><span data-stu-id="5ac03-125">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-126">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span><span class="sxs-lookup"><span data-stu-id="5ac03-126">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="5ac03-127">To see the response returned from the server, edit the request \(if needed\) and select **Send**.</span><span class="sxs-lookup"><span data-stu-id="5ac03-127">To see the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="5ac03-128">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span><span class="sxs-lookup"><span data-stu-id="5ac03-128">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="5ac03-130">The **Network Console** panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-130">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="5ac03-131">To see **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], see [moving tools between panels](#move-tools-between-panels).</span><span class="sxs-lookup"><span data-stu-id="5ac03-131">To see **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], see [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="5ac03-132">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable Network Console**.</span><span class="sxs-lookup"><span data-stu-id="5ac03-132">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="5ac03-133">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and select **Edit and Replay**.</span><span class="sxs-lookup"><span data-stu-id="5ac03-133">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and select **Edit and Replay**.</span></span>  

<span data-ttu-id="5ac03-134">Chromium issue [#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="5ac03-134">Chromium issue [#1093687][CR1093687]</span></span>  

### <span data-ttu-id="5ac03-135">Service worker respondWith events in the Timing tab</span><span class="sxs-lookup"><span data-stu-id="5ac03-135">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="5ac03-136">The **Timing** tab of the **Network** panel now includes `respondWith` service worker events.</span><span class="sxs-lookup"><span data-stu-id="5ac03-136">The **Timing** tab of the **Network** panel now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="5ac03-137">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span><span class="sxs-lookup"><span data-stu-id="5ac03-137">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="5ac03-139">The `respondWith` service worker event in the **Timing** tab of the **Network** panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-139">The `respondWith` service worker event in the **Timing** tab of the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-140">Expand **Response received** to see additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span><span class="sxs-lookup"><span data-stu-id="5ac03-140">Expand **Response received** to see additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="5ac03-142">Expand **Response received** to see additional information from the `fetch` response</span><span class="sxs-lookup"><span data-stu-id="5ac03-142">Expand **Response received** to see additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-143">Chromium issue [#1066579][CR1066579]</span><span class="sxs-lookup"><span data-stu-id="5ac03-143">Chromium issue [#1066579][CR1066579]</span></span>  

### <span data-ttu-id="5ac03-144">webhint feedback in the Issues panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-144">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="Experimental feature":::
   <span data-ttu-id="5ac03-146">Experimental feature</span><span class="sxs-lookup"><span data-stu-id="5ac03-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-147">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span><span class="sxs-lookup"><span data-stu-id="5ac03-147">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="5ac03-148">You are now able to see webhint feedback in the [Issues][DevtoolsIssues] panel.</span><span class="sxs-lookup"><span data-stu-id="5ac03-148">You are now able to see webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="5ac03-150">webhint feedback in the Issues panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-150">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5ac03-151">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable webhint**.</span><span class="sxs-lookup"><span data-stu-id="5ac03-151">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="5ac03-152">Open the [Issues][DevtoolsIssues] panel to see feedback from webhint.</span><span class="sxs-lookup"><span data-stu-id="5ac03-152">Open the [Issues][DevtoolsIssues] panel to see feedback from webhint.</span></span>  

<span data-ttu-id="5ac03-153">Chromium issue [#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="5ac03-153">Chromium issue [#1070378][CR1070378]</span></span>  

### <span data-ttu-id="5ac03-154">Move tools between panels</span><span class="sxs-lookup"><span data-stu-id="5ac03-154">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="Experimental feature":::
   <span data-ttu-id="5ac03-156">Experimental feature</span><span class="sxs-lookup"><span data-stu-id="5ac03-156">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-157">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span><span class="sxs-lookup"><span data-stu-id="5ac03-157">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="5ac03-158">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span><span class="sxs-lookup"><span data-stu-id="5ac03-158">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="5ac03-159">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span><span class="sxs-lookup"><span data-stu-id="5ac03-159">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="5ac03-161">Moving tabs between panels</span><span class="sxs-lookup"><span data-stu-id="5ac03-161">Moving tabs between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5ac03-162">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable support to move tabs between panels**.</span><span class="sxs-lookup"><span data-stu-id="5ac03-162">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="5ac03-163">Chromium issue [#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="5ac03-163">Chromium issue [#897944][CR897944]</span></span>  

### <span data-ttu-id="5ac03-164">Improved Initiator tooltip in the Network panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-164">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="5ac03-165">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span><span class="sxs-lookup"><span data-stu-id="5ac03-165">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="5ac03-166">You were only able to see the call stack that initiated the request by scrolling horizontally in the tooltip.</span><span class="sxs-lookup"><span data-stu-id="5ac03-166">You were only able to see the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="5ac03-168">The Initiator tooltip in Microsoft Edge 84</span><span class="sxs-lookup"><span data-stu-id="5ac03-168">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-169">Starting with Microsoft Edge 85, you are now able to see the Initiator call stack in the tooltip without scrolling horizontally.</span><span class="sxs-lookup"><span data-stu-id="5ac03-169">Starting with Microsoft Edge 85, you are now able to see the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="5ac03-171">The Initiator tooltip in Microsoft Edge 85</span><span class="sxs-lookup"><span data-stu-id="5ac03-171">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="5ac03-172">Chromium issue [#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="5ac03-172">Chromium issue [#1069404][CR1069404]</span></span>  

## <span data-ttu-id="5ac03-173">Announcements from the Chromium project</span><span class="sxs-lookup"><span data-stu-id="5ac03-173">Announcements from the Chromium project</span></span>  

<span data-ttu-id="5ac03-174">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span><span class="sxs-lookup"><span data-stu-id="5ac03-174">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="5ac03-175">Style editing for CSS-in-JS frameworks</span><span class="sxs-lookup"><span data-stu-id="5ac03-175">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="5ac03-176">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span><span class="sxs-lookup"><span data-stu-id="5ac03-176">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="5ac03-177">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span><span class="sxs-lookup"><span data-stu-id="5ac03-177">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="5ac03-178">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span><span class="sxs-lookup"><span data-stu-id="5ac03-178">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="5ac03-179">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span><span class="sxs-lookup"><span data-stu-id="5ac03-179">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="5ac03-180">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span><span class="sxs-lookup"><span data-stu-id="5ac03-180">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="5ac03-181">The styles are editable now in the **Styles** pane.</span><span class="sxs-lookup"><span data-stu-id="5ac03-181">The styles are editable now in the **Styles** pane.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="5ac03-183">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span><span class="sxs-lookup"><span data-stu-id="5ac03-183">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="5ac03-184">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span><span class="sxs-lookup"><span data-stu-id="5ac03-184">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="5ac03-185">Chromium issue [#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="5ac03-185">Chromium issue [#946975][CR946975]</span></span>  

### <span data-ttu-id="5ac03-186">Lighthouse 6 in the Lighthouse panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-186">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="5ac03-187">The **Lighthouse** panel is now running Lighthouse 6.</span><span class="sxs-lookup"><span data-stu-id="5ac03-187">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="5ac03-188">For a full list of all changes, see [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span><span class="sxs-lookup"><span data-stu-id="5ac03-188">For a full list of all changes, see [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="5ac03-189">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span><span class="sxs-lookup"><span data-stu-id="5ac03-189">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="5ac03-190">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span><span class="sxs-lookup"><span data-stu-id="5ac03-190">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="5ac03-191">Chromium issue [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="5ac03-191">Chromium issue [#772558][CR772558]</span></span>  

#### <span data-ttu-id="5ac03-192">First Meaningful Paint deprecation</span><span class="sxs-lookup"><span data-stu-id="5ac03-192">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="5ac03-193">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span><span class="sxs-lookup"><span data-stu-id="5ac03-193">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="5ac03-194">FMP has also been removed from the **Performance** panel.</span><span class="sxs-lookup"><span data-stu-id="5ac03-194">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="5ac03-195">**Largest Contentful Paint** is the recommended replacement for FMP.</span><span class="sxs-lookup"><span data-stu-id="5ac03-195">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="5ac03-196">Chromium issue [#1096008][CR1096008]</span><span class="sxs-lookup"><span data-stu-id="5ac03-196">Chromium issue [#1096008][CR1096008]</span></span>  

### <span data-ttu-id="5ac03-197">Support for new JavaScript features</span><span class="sxs-lookup"><span data-stu-id="5ac03-197">Support for new JavaScript features</span></span>  

<span data-ttu-id="5ac03-198">DevTools now has better support for some of the latest JavaScript language features.</span><span class="sxs-lookup"><span data-stu-id="5ac03-198">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="5ac03-199">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span><span class="sxs-lookup"><span data-stu-id="5ac03-199">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5ac03-200">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span><span class="sxs-lookup"><span data-stu-id="5ac03-200">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="5ac03-201">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span><span class="sxs-lookup"><span data-stu-id="5ac03-201">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5ac03-202">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="5ac03-202">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="5ac03-203">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span><span class="sxs-lookup"><span data-stu-id="5ac03-203">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5ac03-204">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="5ac03-204">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="5ac03-205">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span><span class="sxs-lookup"><span data-stu-id="5ac03-205">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <span data-ttu-id="5ac03-206">New app shortcut warnings in the Manifest pane</span><span class="sxs-lookup"><span data-stu-id="5ac03-206">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="5ac03-207">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span><span class="sxs-lookup"><span data-stu-id="5ac03-207">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="5ac03-208">The **Manifest** pane now shows warnings for the following conditions.</span><span class="sxs-lookup"><span data-stu-id="5ac03-208">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="5ac03-209">The app shortcut icons are smaller than 96x96 pixels</span><span class="sxs-lookup"><span data-stu-id="5ac03-209">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="5ac03-210">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span><span class="sxs-lookup"><span data-stu-id="5ac03-210">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="5ac03-212">App shortcut warnings</span><span class="sxs-lookup"><span data-stu-id="5ac03-212">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-213">Chromium issue [#955497][CR955497]</span><span class="sxs-lookup"><span data-stu-id="5ac03-213">Chromium issue [#955497][CR955497]</span></span>  

### <span data-ttu-id="5ac03-214">Consistent display of the Computed pane</span><span class="sxs-lookup"><span data-stu-id="5ac03-214">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="5ac03-215">The **Computed** pane in the **Elements** panel now displays consistently as a pane across all viewport sizes.</span><span class="sxs-lookup"><span data-stu-id="5ac03-215">The **Computed** pane in the **Elements** panel now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="5ac03-216">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span><span class="sxs-lookup"><span data-stu-id="5ac03-216">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="5ac03-218">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span><span class="sxs-lookup"><span data-stu-id="5ac03-218">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="5ac03-219">Chromium issue [#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="5ac03-219">Chromium issue [#1073899][CR1073899]</span></span>  

### <span data-ttu-id="5ac03-220">Bytecode offsets for WebAssembly files</span><span class="sxs-lookup"><span data-stu-id="5ac03-220">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="5ac03-221">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span><span class="sxs-lookup"><span data-stu-id="5ac03-221">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="5ac03-222">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span><span class="sxs-lookup"><span data-stu-id="5ac03-222">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="5ac03-223">Chromium issue [#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="5ac03-223">Chromium issue [#1071432][CR1071432]</span></span>  

### <span data-ttu-id="5ac03-224">Line-wise copy and cut in Sources Panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-224">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="5ac03-225">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span><span class="sxs-lookup"><span data-stu-id="5ac03-225">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="5ac03-227">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [Visual Studio Code][VSCode].</span><span class="sxs-lookup"><span data-stu-id="5ac03-227">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [Visual Studio Code][VSCode].</span></span>
:::image-end:::  

<span data-ttu-id="5ac03-228">Chromium issue [#800028][CR800028]</span><span class="sxs-lookup"><span data-stu-id="5ac03-228">Chromium issue [#800028][CR800028]</span></span>

### <span data-ttu-id="5ac03-229">Console Settings updates</span><span class="sxs-lookup"><span data-stu-id="5ac03-229">Console Settings updates</span></span>  

#### <span data-ttu-id="5ac03-230">Ungroup same console messages</span><span class="sxs-lookup"><span data-stu-id="5ac03-230">Ungroup same console messages</span></span>  

<span data-ttu-id="5ac03-231">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span><span class="sxs-lookup"><span data-stu-id="5ac03-231">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="5ac03-232">Previously it just applied to similar messages.</span><span class="sxs-lookup"><span data-stu-id="5ac03-232">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="5ac03-233">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span><span class="sxs-lookup"><span data-stu-id="5ac03-233">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="5ac03-234">Now, the `hello` messages are ungrouped.</span><span class="sxs-lookup"><span data-stu-id="5ac03-234">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="5ac03-236">When **Group similar** is unchecked, the `hello` messages are ungrouped</span><span class="sxs-lookup"><span data-stu-id="5ac03-236">When **Group similar** is unchecked, the `hello` messages are ungrouped</span></span>
:::image-end:::  

<span data-ttu-id="5ac03-237">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span><span class="sxs-lookup"><span data-stu-id="5ac03-237">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="5ac03-238">Chromium issue [#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="5ac03-238">Chromium issue [#1082963][CR1082963]</span></span>  

### <span data-ttu-id="5ac03-239">Persisting Selected context only settings</span><span class="sxs-lookup"><span data-stu-id="5ac03-239">Persisting Selected context only settings</span></span>  

<span data-ttu-id="5ac03-240">The **Selected context only** settings in Console Settings is now persisted.</span><span class="sxs-lookup"><span data-stu-id="5ac03-240">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="5ac03-241">Previously the settings were reset every time you closed and reopened DevTools.</span><span class="sxs-lookup"><span data-stu-id="5ac03-241">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="5ac03-242">The change makes the setting behavior consistent with other Console Settings options.</span><span class="sxs-lookup"><span data-stu-id="5ac03-242">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="5ac03-244">**Selected context only** setting</span><span class="sxs-lookup"><span data-stu-id="5ac03-244">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-245">Chromium issue [#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="5ac03-245">Chromium issue [#1055875][CR1055875]</span></span>  

### <span data-ttu-id="5ac03-246">Performance panel updates</span><span class="sxs-lookup"><span data-stu-id="5ac03-246">Performance panel updates</span></span>  

#### <span data-ttu-id="5ac03-247">JavaScript compilation cache information in Performance panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-247">JavaScript compilation cache information in Performance panel</span></span>  

<span data-ttu-id="5ac03-248">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the Summary tab of the Performance panel.</span><span class="sxs-lookup"><span data-stu-id="5ac03-248">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the Summary tab of the Performance panel.</span></span>  <span data-ttu-id="5ac03-249">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span><span class="sxs-lookup"><span data-stu-id="5ac03-249">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="5ac03-251">JavaScript compilation cache information</span><span class="sxs-lookup"><span data-stu-id="5ac03-251">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-252">Chromium issue [#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="5ac03-252">Chromium issue [#912581][CR912581]</span></span>  

#### <span data-ttu-id="5ac03-253">Navigation timing alignment in the Performance panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-253">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="5ac03-254">The **Performance** panel used to show times in the rulers based on when the recording started.</span><span class="sxs-lookup"><span data-stu-id="5ac03-254">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="5ac03-255">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span><span class="sxs-lookup"><span data-stu-id="5ac03-255">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="5ac03-257">Align navigation timing in **Performance** panel</span><span class="sxs-lookup"><span data-stu-id="5ac03-257">Align navigation timing in **Performance** panel</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-258">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span><span class="sxs-lookup"><span data-stu-id="5ac03-258">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="5ac03-259">Chromium issue [#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="5ac03-259">Chromium issue [#974550][CR974550]</span></span>  

### <span data-ttu-id="5ac03-260">New icons for breakpoints, conditional breakpoints, and logpoints</span><span class="sxs-lookup"><span data-stu-id="5ac03-260">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="5ac03-261">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span><span class="sxs-lookup"><span data-stu-id="5ac03-261">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="5ac03-262">Breakpoints are represented by a red circle, just like [Visual Studio Code][VSCode] and [Visual Studio][VS].</span><span class="sxs-lookup"><span data-stu-id="5ac03-262">Breakpoints are represented by a red circle, just like [Visual Studio Code][VSCode] and [Visual Studio][VS].</span></span>  <span data-ttu-id="5ac03-263">Icons are added to differentiate conditional breakpoints and logpoints.</span><span class="sxs-lookup"><span data-stu-id="5ac03-263">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="Experimental feature" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="5ac03-265">Breakpoints</span><span class="sxs-lookup"><span data-stu-id="5ac03-265">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="5ac03-266">Chromium issue [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="5ac03-266">Chromium issue [#1041830][CR1041830]</span></span>  

## <span data-ttu-id="5ac03-267">Download the Microsoft Edge preview channels</span><span class="sxs-lookup"><span data-stu-id="5ac03-267">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="5ac03-268">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="5ac03-268">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="5ac03-269">The preview channels give you access to the latest DevTools features.</span><span class="sxs-lookup"><span data-stu-id="5ac03-269">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="5ac03-270">Getting in touch with Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="5ac03-270">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) Developer Tools | Microsoft Docs"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "Run Commands With The Microsoft Edge DevTools Command Menu | Microsoft Docs"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "Drawer - Customize Microsoft Edge DevTools | Microsoft Docs"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "Turn on experimental features - Experimental features | Microsoft Docs"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "Find and fix problems with the Microsoft Edge DevTools Issues tool | Microsoft Docs"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "Edit CSS and JavaScript - Sources Panel Overview | Microsoft Docs"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "Log network activity - Inspect Network Activity In Microsoft Edge DevTools | Microsoft Docs"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "Style editing for CSS-in-JS frameworks | CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "Send duplicate messages to Console | CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS Grid planner example | CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR772558]: https://crbug.com/772558 "DevTools: Update to latest version of Lighthouse | Chromium bugs"  
[CR800028]: https://crbug.com/800028 "Duplicate line shortcut in Developer Tools editor not working after Chrome update | Chromium bugs"  
[CR912581]: https://crbug.com/912581 "Expose which scripts were code-cached by V8 in DevTools/about:tracing | Chromium bugs"  
[CR946975]: https://crbug.com/946975 "DevTools Styles Sidebar doesn't work with constructed stylesheets | Chromium bugs"  
[CR955497]: https://crbug.com/955497 "App Icon Shortcut menu for PWAs | Chromium bugs"  
[CR974550]: https://crbug.com/974550 "Metric mismatch between Perf panel and performanceObserver | Chromium bugs"  
[CR1041830]: https://crbug.com/1041830 "Improve colors for breakpoints | Chromium bugs"  
[CR1055875]: https://crbug.com/1055875 "The value of the Selected context only console setting does not persist after closing and reopening Developer Tools | Chromium bugs"  
[CR1066579]: https://crbug.com/1066579 "DevTools: Show ServiceWorkers Fetch Timeline per request in Network panel | Chromium bugs"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic Developer Experience | Chromium bugs"  
[CR1073899]: https://crbug.com/1073899 "Computed style tab disappears in responsive mode | Chromium bugs"  
[CR1073903]: https://crbug.com/1073903 "DevTools: Syntax highlighting doesn't work with private fields | Chromium bugs"  
[CR1082963]: https://crbug.com/1082963 "Can't disable console's Group similar messages behavior | Chromium bugs"  
[CR1083214]: https://crbug.com/1083214 "acorn doesn't support optional chaining | Chromium bugs"  
[CR1083797]: https://crbug.com/1083797 "Pretty printing broken for nullish coalescing | Chromium bugs"  
[CR1096008]: https://crbug.com/1096008 "Remove FMP | Chromium bugs"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table tooling | Chromium bugs"  
[CR1093687]: https://crbug.com/1093687 "Create tool for creating and replaying synthetic network requests | Chromium bugs"  
[CR1070378]: https://crbug.com/1070378 "Integrate webhint into DevTools | Chromium bugs"  
[CR1069404]: https://crbug.com/1069404 "[Dev Tools] widget popups are too all narrow | Chromium bugs"  
[CR897944]: https://crbug.com/897944 "Draggable devtool panels | Chromium bugs"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse | GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "New Issue - MicrosoftDocs/edge-developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "Using shadow DOM | MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge Preview Channels"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio Code"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS Object Model (CSSOM) | W3C CSS Working Group Editor Drafts"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | Post a Tweet"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter account"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "Private class fields - Public and private class fields | V8.Dev"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "Code caching for JavaScript developers | V8.Dev"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish coalescing | V8.Dev"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "Optional chaining | V8.Dev"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "Constructable Stylesheet Objects | Web Incubator CG"

<!--[WebDevLighthouseWhatsNew60]: https://web.dev/lighthouse-whats-new-6.0 "What's New in Lighthouse 6.0 | Web.Dev"  -->  
<!--[WebDevVitalsCoreWeb]: https://web.dev/vitals#core-web-vitals "Core Web Vitals - Web Vitals | Web.Dev"  -->  
<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebFundamentalComponentsShadowdom]: /web/fundamentals/web-components/shadowdom  -->  
<!--[WebDevLcp]: https://web.dev/lcp "Largest Contentful Paint (LCP) | Web.Dev"  -->  
<!--[WebDevFirstMeaningfulPaint]: https://web.dev/first-meaningful-paint "First Meaningful Paint | Web.Dev"  -->  
<!--[WhatsNew201902ConstructableStylesheets]: ../../2019/02/constructable-stylesheets.md "Constructable Stylesheets: seamless reusable styles | Microsoft Docs"  -->  

[TheWebWeWant]: https://webwewant.fyi/ "The Web We Want"  

> [!NOTE]
> <span data-ttu-id="5ac03-319">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5ac03-319">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5ac03-320">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span><span class="sxs-lookup"><span data-stu-id="5ac03-320">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5ac03-322">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5ac03-322">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
