---
description: A tutorial on the most popular network-related features in Microsoft Edge DevTools.
title: Inspect Network Activity In Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 3629c2d3711716d6d4a837b29bffef4786eb6d3f
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993448"
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





# <span data-ttu-id="cbcdc-104">Inspect network activity in Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="cbcdc-104">Inspect network activity in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="cbcdc-105">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-105">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="cbcdc-106">See [Network Reference][DevtoolsNetworkReference] if you want to browse features instead.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-106">See [Network Reference][DevtoolsNetworkReference] if you want to browse features instead.</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <span data-ttu-id="cbcdc-107">When to use the Network panel</span><span class="sxs-lookup"><span data-stu-id="cbcdc-107">When to use the Network panel</span></span>   

<span data-ttu-id="cbcdc-108">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-108">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="cbcdc-109">The most common use cases for the Network panel are:</span><span class="sxs-lookup"><span data-stu-id="cbcdc-109">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="cbcdc-110">Making sure that resources are actually being uploaded or downloaded at all.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-110">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="cbcdc-111">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-111">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  
    
<span data-ttu-id="cbcdc-112">If you are looking for ways to improve page load performance, **do not** start with the Network panel.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-112">If you are looking for ways to improve page load performance, **do not** start with the Network panel.</span></span>  <span data-ttu-id="cbcdc-113">There are many types of load performance issues that are not related to network activity.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-113">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="cbcdc-114">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-114">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="cbcdc-115">See [Optimize Website Speed][DevtoolsSpeedGetStarted].</span><span class="sxs-lookup"><span data-stu-id="cbcdc-115">See [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <span data-ttu-id="cbcdc-116">Open the Network panel</span><span class="sxs-lookup"><span data-stu-id="cbcdc-116">Open the Network panel</span></span>   

<span data-ttu-id="cbcdc-117">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-117">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="cbcdc-118">Open the [Get Started Demo][GlitchNetworkGetStarted].</span><span class="sxs-lookup"><span data-stu-id="cbcdc-118">Open the [Get Started Demo][GlitchNetworkGetStarted].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="The demo" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       <span data-ttu-id="cbcdc-120">The demo</span><span class="sxs-lookup"><span data-stu-id="cbcdc-120">The demo</span></span>  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="The demo" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="cbcdc-121">[Open DevTools][DevToolsOpen] by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="cbcdc-121">[Open DevTools][DevToolsOpen] by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="cbcdc-122">The **Console** panel opens.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-122">The **Console** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="The demo" lightbox="../media/network-glitch-console.msft.png":::
       <span data-ttu-id="cbcdc-124">The **Console**</span><span class="sxs-lookup"><span data-stu-id="cbcdc-124">The **Console**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="cbcdc-125">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span><span class="sxs-lookup"><span data-stu-id="cbcdc-125">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="The demo" lightbox="../media/network-glitch-console-bottom.msft.png":::
       <span data-ttu-id="cbcdc-127">DevTools docked to the bottom of the window</span><span class="sxs-lookup"><span data-stu-id="cbcdc-127">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-128">Select the **Network** tab.  The Network panel opens.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-128">Select the **Network** tab.  The Network panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-bottom.msft.png":::
       <span data-ttu-id="cbcdc-130">DevTools docked to the bottom of the window</span><span class="sxs-lookup"><span data-stu-id="cbcdc-130">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
<span data-ttu-id="cbcdc-131">Right now the Network panel is empty.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-131">Right now the Network panel is empty.</span></span>  <span data-ttu-id="cbcdc-132">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-132">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <span data-ttu-id="cbcdc-133">Log network activity</span><span class="sxs-lookup"><span data-stu-id="cbcdc-133">Log network activity</span></span>   

<span data-ttu-id="cbcdc-134">To view the network activity that a page causes:</span><span class="sxs-lookup"><span data-stu-id="cbcdc-134">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="cbcdc-135">Reload the page.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-135">Reload the page.</span></span>  <span data-ttu-id="cbcdc-136">The Network panel logs all network activity in the **Network Log**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-136">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network.msft.png":::
       <span data-ttu-id="cbcdc-138">The **Network Log**</span><span class="sxs-lookup"><span data-stu-id="cbcdc-138">The **Network Log**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="cbcdc-139">Each row of the **Network Log** represents a resource.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-139">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="cbcdc-140">By default the resources are listed chronologically.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-140">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="cbcdc-141">The top resource is usually the main HTML document.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-141">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="cbcdc-142">The bottom resource is whatever was requested last.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-142">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="cbcdc-143">Each column represents information about a resource.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-143">Each column represents information about a resource.</span></span>  <span data-ttu-id="cbcdc-144">In the previous figure the default columns are displayed.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-144">In the previous figure the default columns are displayed.</span></span>  

    *   <span data-ttu-id="cbcdc-145">**Status**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-145">**Status**.</span></span>  <span data-ttu-id="cbcdc-146">The HTTP status code for response.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-146">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="cbcdc-147">**Type**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-147">**Type**.</span></span>  <span data-ttu-id="cbcdc-148">The resource type.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-148">The resource type.</span></span>  
    *   <span data-ttu-id="cbcdc-149">**Initiator**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-149">**Initiator**.</span></span>  <span data-ttu-id="cbcdc-150">The cause of the resource request.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-150">The cause of the resource request.</span></span>  <span data-ttu-id="cbcdc-151">Selecting a link in the Initiator column takes you to the source code that caused the request.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-151">Selecting a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="cbcdc-152">**Time**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-152">**Time**.</span></span>  <span data-ttu-id="cbcdc-153">The duration of the request.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-153">The duration of the request.</span></span>  
    *   <span data-ttu-id="cbcdc-154">**Waterfall**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-154">**Waterfall**.</span></span>  <span data-ttu-id="cbcdc-155">A graphical representation of the different stages of the request.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-155">A graphical representation of the different stages of the request.</span></span>  <span data-ttu-id="cbcdc-156">Hover over a Waterfall to see a breakdown.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-156">Hover over a Waterfall to see a breakdown.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="cbcdc-157">The graph above the Network Log is called the Overview.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-157">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="cbcdc-158">You will not use the Overview graph in this tutorial, so you may hide it.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-158">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="cbcdc-159">See [Hide the Overview pane][DevtoolsReferenceHideOverview].</span><span class="sxs-lookup"><span data-stu-id="cbcdc-159">See [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
    
1.  <span data-ttu-id="cbcdc-160">After you open DevTools, it records network activity in the Network Log.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-160">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="cbcdc-161">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-161">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="cbcdc-162">Now, select the **Get Data** button in the demo.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-162">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="cbcdc-163">Look at the bottom of the **Network Log** again.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-163">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="cbcdc-164">You should see a new resource called `getstarted.json`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-164">You should see a new resource called `getstarted.json`.</span></span>  <span data-ttu-id="cbcdc-165">Selecting the **Get Data** button caused the page to request this file.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-165">Selecting the **Get Data** button caused the page to request this file.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       <span data-ttu-id="cbcdc-167">A new resource in the **Network Log**</span><span class="sxs-lookup"><span data-stu-id="cbcdc-167">A new resource in the **Network Log**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="cbcdc-168">Show more information</span><span class="sxs-lookup"><span data-stu-id="cbcdc-168">Show more information</span></span>   

<span data-ttu-id="cbcdc-169">The columns of the Network Log are configurable.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-169">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="cbcdc-170">You may hide columns that you are not using.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-170">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="cbcdc-171">There are also many columns that are hidden by default which you may find useful.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-171">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="cbcdc-172">Right-click the header of the Network Log table and select **Domain**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-172">Right-click the header of the Network Log table and select **Domain**.</span></span>  <span data-ttu-id="cbcdc-173">The domain of each resource is now shown.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-173">The domain of each resource is now shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       <span data-ttu-id="cbcdc-175">Enable the Domain column</span><span class="sxs-lookup"><span data-stu-id="cbcdc-175">Enable the Domain column</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="cbcdc-176">See the full URL of a resource by hovering over the cell in the **Name** column.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-176">See the full URL of a resource by hovering over the cell in the **Name** column.</span></span>  
    
## <span data-ttu-id="cbcdc-177">Simulate a slower network connection</span><span class="sxs-lookup"><span data-stu-id="cbcdc-177">Simulate a slower network connection</span></span>   

<span data-ttu-id="cbcdc-178">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-178">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="cbcdc-179">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-179">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="cbcdc-180">Select the **Throttling** dropdown, which is set to **Online** by default.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-180">Select the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-throttling.msft.png":::
       <span data-ttu-id="cbcdc-182">Enable throttling</span><span class="sxs-lookup"><span data-stu-id="cbcdc-182">Enable throttling</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-183">Select **Slow 3G**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-183">Select **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       <span data-ttu-id="cbcdc-185">Select Slow 3G</span><span class="sxs-lookup"><span data-stu-id="cbcdc-185">Select Slow 3G</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-186">Long-press **Reload** \(![Reload][ImageRefreshIcon]\) and then select **Empty Cache And Hard Reload**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-186">Long-press **Reload** \(![Reload][ImageRefreshIcon]\) and then select **Empty Cache And Hard Reload**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="The demo" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **<span data-ttu-id="cbcdc-188">Empty Cache And Hard Reload</span><span class="sxs-lookup"><span data-stu-id="cbcdc-188">Empty Cache And Hard Reload</span></span>**  
    :::image-end:::  
    
    <span data-ttu-id="cbcdc-189">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache], which speeds up the page load.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-189">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache], which speeds up the page load.</span></span>  <span data-ttu-id="cbcdc-190">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-190">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="cbcdc-191">This is helpful when you want to see how a first-time visitor experiences a page load.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-191">This is helpful when you want to see how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="cbcdc-192">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-192">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  
    
## <span data-ttu-id="cbcdc-193">Capture screenshots</span><span class="sxs-lookup"><span data-stu-id="cbcdc-193">Capture screenshots</span></span>   

<span data-ttu-id="cbcdc-194">Screenshots let you see how a page looked over time while it was loading.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-194">Screenshots let you see how a page looked over time while it was loading.</span></span>  

1.  <span data-ttu-id="cbcdc-195">Select \(![Network settings][ImageSettingsIcon]\) and select the **Capture screenshots** checkbox.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-195">Select \(![Network settings][ImageSettingsIcon]\) and select the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="cbcdc-196">Reload the page again via the **Empty Cache And Hard Reload** workflow.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-196">Reload the page again via the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="cbcdc-197">See [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-197">See [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="cbcdc-198">The Screenshots pane provides thumbnails of how the page looked at various points during the loading process.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-198">The Screenshots pane provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       <span data-ttu-id="cbcdc-200">Screenshots of the page load</span><span class="sxs-lookup"><span data-stu-id="cbcdc-200">Screenshots of the page load</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-201">Select the first thumbnail.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-201">Select the first thumbnail.</span></span>  <span data-ttu-id="cbcdc-202">DevTools shows you what network activity was occurring at that moment in time.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-202">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       <span data-ttu-id="cbcdc-204">The network activity that was happening during the first screenshot</span><span class="sxs-lookup"><span data-stu-id="cbcdc-204">The network activity that was happening during the first screenshot</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-205">Select \(![Network settings][ImageSettingsIcon]\) again and deselect the **Capture screenshots** checkbox to close the Screenshots pane.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-205">Select \(![Network settings][ImageSettingsIcon]\) again and deselect the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="cbcdc-206">Reload the page again.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-206">Reload the page again.</span></span>  
    
## <span data-ttu-id="cbcdc-207">Inspect the details of the resource</span><span class="sxs-lookup"><span data-stu-id="cbcdc-207">Inspect the details of the resource</span></span>   

<span data-ttu-id="cbcdc-208">Select a resource to learn more information about it.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-208">Select a resource to learn more information about it.</span></span>  <span data-ttu-id="cbcdc-209">Try it now:</span><span class="sxs-lookup"><span data-stu-id="cbcdc-209">Try it now:</span></span>  

1.  <span data-ttu-id="cbcdc-210">Select `getstarted.html`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-210">Select `getstarted.html`.</span></span>  <span data-ttu-id="cbcdc-211">The **Headers** tab is shown.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-211">The **Headers** tab is shown.</span></span>  <span data-ttu-id="cbcdc-212">Use this tab to inspect HTTP headers.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-212">Use this tab to inspect HTTP headers.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       <span data-ttu-id="cbcdc-214">The **Headers** tab</span><span class="sxs-lookup"><span data-stu-id="cbcdc-214">The **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-215">Select the **Preview** tab.  A basic rendering of the HTML is shown.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-215">Select the **Preview** tab.  A basic rendering of the HTML is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       <span data-ttu-id="cbcdc-217">The **Preview** tab</span><span class="sxs-lookup"><span data-stu-id="cbcdc-217">The **Preview** tab</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="cbcdc-218">This tab is helpful when an API returns an error code in HTML.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-218">This tab is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="cbcdc-219">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-219">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="cbcdc-220">Select the **Response** tab.  The HTML source code is shown.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-220">Select the **Response** tab.  The HTML source code is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       <span data-ttu-id="cbcdc-222">The **Response** tab</span><span class="sxs-lookup"><span data-stu-id="cbcdc-222">The **Response** tab</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="cbcdc-223">When a file is minified, selecting the **Format** \(![Format][ImageFormatIcon]\) button at the bottom of the **Response** tab re-formats the contents of the file for readability.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-223">When a file is minified, selecting the **Format** \(![Format][ImageFormatIcon]\) button at the bottom of the **Response** tab re-formats the contents of the file for readability.</span></span>  
    
1.  <span data-ttu-id="cbcdc-224">Select the **Timing** tab.  A breakdown of the network activity for this resource is shown.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-224">Select the **Timing** tab.  A breakdown of the network activity for this resource is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       <span data-ttu-id="cbcdc-226">The **Timing** tab</span><span class="sxs-lookup"><span data-stu-id="cbcdc-226">The **Timing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-227">Select **Close** \(![Close][ImageCloseIcon]\) to view the Network Log again.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-227">Select **Close** \(![Close][ImageCloseIcon]\) to view the Network Log again.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       <span data-ttu-id="cbcdc-229">The **Close** button</span><span class="sxs-lookup"><span data-stu-id="cbcdc-229">The **Close** button</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="cbcdc-230">Search network headers and responses</span><span class="sxs-lookup"><span data-stu-id="cbcdc-230">Search network headers and responses</span></span>   

<span data-ttu-id="cbcdc-231">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-231">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="cbcdc-232">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-232">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="cbcdc-233">Select **Search** \(![Search][ImageSearchIcon]\).</span><span class="sxs-lookup"><span data-stu-id="cbcdc-233">Select **Search** \(![Search][ImageSearchIcon]\).</span></span>  <span data-ttu-id="cbcdc-234">The Search pane opens to the left of the Network log.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-234">The Search pane opens to the left of the Network log.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       <span data-ttu-id="cbcdc-236">The **Search** pane</span><span class="sxs-lookup"><span data-stu-id="cbcdc-236">The **Search** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-237">Type `Cache-Control` and press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-237">Type `Cache-Control` and press `Enter`.</span></span>  <span data-ttu-id="cbcdc-238">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-238">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       <span data-ttu-id="cbcdc-240">Search results for</span><span class="sxs-lookup"><span data-stu-id="cbcdc-240">Search results for</span></span> `Cache-Control`  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-241">Select a result to view the resource in which the result was found.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-241">Select a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="cbcdc-242">If you are looking at the details of the resource, select a result to go directly to it.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-242">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="cbcdc-243">For example, if the query was found in a header, the Headers tab opens.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-243">For example, if the query was found in a header, the Headers tab opens.</span></span>   <span data-ttu-id="cbcdc-244">If the query was found in content, the **Response** tab opens.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-244">If the query was found in content, the **Response** tab opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       <span data-ttu-id="cbcdc-246">A search result highlighted in the **Headers** tab</span><span class="sxs-lookup"><span data-stu-id="cbcdc-246">A search result highlighted in the **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-247">Close the Search pane and the Headers tab.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-247">Close the Search pane and the Headers tab.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-search-close.msft.png":::
       <span data-ttu-id="cbcdc-249">The **Close** buttons</span><span class="sxs-lookup"><span data-stu-id="cbcdc-249">The **Close** buttons</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="cbcdc-250">Filter resources</span><span class="sxs-lookup"><span data-stu-id="cbcdc-250">Filter resources</span></span>   

<span data-ttu-id="cbcdc-251">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-251">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   <span data-ttu-id="cbcdc-253">The **Filters** toolbar</span><span class="sxs-lookup"><span data-stu-id="cbcdc-253">The **Filters** toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="cbcdc-254">The **Filters** toolbar should be enabled by default.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-254">The **Filters** toolbar should be enabled by default.</span></span>  <span data-ttu-id="cbcdc-255">If not:</span><span class="sxs-lookup"><span data-stu-id="cbcdc-255">If not:</span></span>  

1.  <span data-ttu-id="cbcdc-256">Select **Filter** \(![Filter][ImageFilterIcon]\) to show it.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-256">Select **Filter** \(![Filter][ImageFilterIcon]\) to show it.</span></span>  
    
### <span data-ttu-id="cbcdc-257">Filter by string, regular expression, or property</span><span class="sxs-lookup"><span data-stu-id="cbcdc-257">Filter by string, regular expression, or property</span></span>   

<span data-ttu-id="cbcdc-258">The **Filter** text box supports many different types of filtering.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-258">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="cbcdc-259">Type `png` into the **Filter** text box.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-259">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="cbcdc-260">Only the files that contain the text `png` are shown.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-260">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="cbcdc-261">In this case the only files that match the filter are the PNG images.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-261">In this case the only files that match the filter are the PNG images.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       <span data-ttu-id="cbcdc-263">A string filter</span><span class="sxs-lookup"><span data-stu-id="cbcdc-263">A string filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-264">Type `/.*\.[cj]s+$/`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-264">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="cbcdc-265">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-265">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       <span data-ttu-id="cbcdc-267">A regular expression filter</span><span class="sxs-lookup"><span data-stu-id="cbcdc-267">A regular expression filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-268">Type `-main.css`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-268">Type `-main.css`.</span></span>  <span data-ttu-id="cbcdc-269">DevTools filters out `main.css`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-269">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="cbcdc-270">If any other file matched the pattern they would also be filtered out.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-270">If any other file matched the pattern they would also be filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       <span data-ttu-id="cbcdc-272">A negative filter</span><span class="sxs-lookup"><span data-stu-id="cbcdc-272">A negative filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-273">Type `domain:cdn.glitch.com` into the **Filter** text box.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-273">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="cbcdc-274">DevTools filters out any resource with a URL that does not match this domain.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-274">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       <span data-ttu-id="cbcdc-276">A property filter</span><span class="sxs-lookup"><span data-stu-id="cbcdc-276">A property filter</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="cbcdc-277">See [Filter requests by properties][DevtoolsReferenceProperty] for the full list of filterable properties.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-277">See [Filter requests by properties][DevtoolsReferenceProperty] for the full list of filterable properties.</span></span>  
    
1.  <span data-ttu-id="cbcdc-278">Clear the **Filter** text box of any text.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-278">Clear the **Filter** text box of any text.</span></span>  
    
### <span data-ttu-id="cbcdc-279">Filter by resource type</span><span class="sxs-lookup"><span data-stu-id="cbcdc-279">Filter by resource type</span></span>   

<span data-ttu-id="cbcdc-280">To focus in on a certain type of file, such as stylesheets:</span><span class="sxs-lookup"><span data-stu-id="cbcdc-280">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="cbcdc-281">Select **CSS**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-281">Select **CSS**.</span></span>  <span data-ttu-id="cbcdc-282">All other file types are filtered out.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-282">All other file types are filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       <span data-ttu-id="cbcdc-284">Show CSS files only</span><span class="sxs-lookup"><span data-stu-id="cbcdc-284">Show CSS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-285">To also see scripts, hold `Control` \(Windows\) or `Command` \(macOS\) and then select **JS**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-285">To also see scripts, hold `Control` \(Windows\) or `Command` \(macOS\) and then select **JS**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       <span data-ttu-id="cbcdc-287">Show CSS and JS files only</span><span class="sxs-lookup"><span data-stu-id="cbcdc-287">Show CSS and JS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-288">Select **All** to remove the filters and see all resources again.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-288">Select **All** to remove the filters and see all resources again.</span></span>  
    
<span data-ttu-id="cbcdc-289">See [Filter requests][DevtoolsNetworkReferenceFilter] for other filtering workflows.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-289">See [Filter requests][DevtoolsNetworkReferenceFilter] for other filtering workflows.</span></span>  

## <span data-ttu-id="cbcdc-290">Block requests</span><span class="sxs-lookup"><span data-stu-id="cbcdc-290">Block requests</span></span>   

<span data-ttu-id="cbcdc-291">How does a page look and behave when some of the page resources are not available?</span><span class="sxs-lookup"><span data-stu-id="cbcdc-291">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="cbcdc-292">Does it fail completely, or is it still somewhat functional?</span><span class="sxs-lookup"><span data-stu-id="cbcdc-292">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="cbcdc-293">Block requests to find out:</span><span class="sxs-lookup"><span data-stu-id="cbcdc-293">Block requests to find out:</span></span>  

1.  <span data-ttu-id="cbcdc-294">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-294">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       <span data-ttu-id="cbcdc-296">The **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="cbcdc-296">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-297">Type `block`, select **Show Request Blocking**, and press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-297">Type `block`, select **Show Request Blocking**, and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **<span data-ttu-id="cbcdc-299">Show Request Blocking</span><span class="sxs-lookup"><span data-stu-id="cbcdc-299">Show Request Blocking</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-300">Select **Add Pattern** \(![Add Pattern][ImageAddIcon]\).</span><span class="sxs-lookup"><span data-stu-id="cbcdc-300">Select **Add Pattern** \(![Add Pattern][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="cbcdc-301">Type `main.css`.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-301">Type `main.css`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       <span data-ttu-id="cbcdc-303">Blocking</span><span class="sxs-lookup"><span data-stu-id="cbcdc-303">Blocking</span></span> `main.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-304">Select **Add**.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-304">Select **Add**.</span></span>  
1.  <span data-ttu-id="cbcdc-305">Reload the page.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-305">Reload the page.</span></span>  <span data-ttu-id="cbcdc-306">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-306">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="cbcdc-307">The `main.css` row in the Network Log.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-307">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="cbcdc-308">The red text means that the resource was blocked.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-308">The red text means that the resource was blocked.</span></span>
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="The demo" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` <span data-ttu-id="cbcdc-310">has been blocked</span><span class="sxs-lookup"><span data-stu-id="cbcdc-310">has been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cbcdc-311">Deselect the **Enable request blocking** checkbox.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-311">Deselect the **Enable request blocking** checkbox.</span></span>  

## <span data-ttu-id="cbcdc-312">Conclusion</span><span class="sxs-lookup"><span data-stu-id="cbcdc-312">Conclusion</span></span>  

<span data-ttu-id="cbcdc-313">Congratulations, you have completed the tutorial.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-313">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="cbcdc-314">You now know how to use the **Network** panel in the Microsoft Edge DevTools!</span><span class="sxs-lookup"><span data-stu-id="cbcdc-314">You now know how to use the **Network** panel in the Microsoft Edge DevTools!</span></span>

<!--




-->  

<span data-ttu-id="cbcdc-315">Check out the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span><span class="sxs-lookup"><span data-stu-id="cbcdc-315">Check out the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

<!--  
 


-->  

<!-- image links -->  

[ImageAddIcon]: ../media/add-icon.msft.png  
[ImageCloseIcon]: ../media/close-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: ../media/screenshots-icon.msft.png  
[ImageSearchIcon]: ../media/search-icon.msft.png  
[ImageSettingsIcon]: ../media/settings-icon.msft.png

<!-- links -->  

<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: ../customize/placement.md "Change Microsoft Edge DevTools placement | Microsoft Docs"  
[DevtoolsNetworkReference]: ./reference.md "Network analysis reference | Microsoft Docs"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "Filter requests - Network analysis reference | Microsoft Docs"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "Hide the Overview pane - Network analysis reference | Microsoft Docs"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "Filter requests by properties - Network analysis reference | Microsoft Docs"
[DevToolsOpen]: ../open.md "Open Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Optimize website speed with Microsoft Edge DevTools | Microsoft Docs"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "Inspect Network Activity Demo | Glitch"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP caching | MDN"  

> [!NOTE]
> <span data-ttu-id="cbcdc-325">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="cbcdc-325">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cbcdc-326">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="cbcdc-326">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="cbcdc-328">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="cbcdc-328">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
