---
description: A comprehensive reference on every feature and behavior related to the Console UI in Microsoft Edge DevTools.
title: Console Reference
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 6a79031e6efbc4b83b83685f32e060a6268dbb2a
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993140"
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





# <span data-ttu-id="98b19-104">Console Reference</span><span class="sxs-lookup"><span data-stu-id="98b19-104">Console Reference</span></span>   



<span data-ttu-id="98b19-105">This page is a reference of features related to the Microsoft Edge DevTools Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-105">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="98b19-106">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span><span class="sxs-lookup"><span data-stu-id="98b19-106">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="98b19-107">If not, see [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span><span class="sxs-lookup"><span data-stu-id="98b19-107">If not, see [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="98b19-108">If you are looking for the API reference on functions like `console.log()` see [Console API Reference][DevToolsConsoleApi].</span><span class="sxs-lookup"><span data-stu-id="98b19-108">If you are looking for the API reference on functions like `console.log()` see [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="98b19-109">For the reference on functions like `monitorEvents()`, see [Console Utilities API Reference][DevToolsConsoleUtilities].</span><span class="sxs-lookup"><span data-stu-id="98b19-109">For the reference on functions like `monitorEvents()`, see [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="98b19-110">Open the Console</span><span class="sxs-lookup"><span data-stu-id="98b19-110">Open the Console</span></span>   

<span data-ttu-id="98b19-111">You may open the Console as a [panel](#open-the-console-panel) or as a [tab in the Drawer](#open-the-console-tab-in-the-drawer).</span><span class="sxs-lookup"><span data-stu-id="98b19-111">You may open the Console as a [panel](#open-the-console-panel) or as a [tab in the Drawer](#open-the-console-tab-in-the-drawer).</span></span>  

### <span data-ttu-id="98b19-112">Open the Console panel</span><span class="sxs-lookup"><span data-stu-id="98b19-112">Open the Console panel</span></span>   

<span data-ttu-id="98b19-113">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="98b19-113">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="The Console panel" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="98b19-115">The **Console** panel</span><span class="sxs-lookup"><span data-stu-id="98b19-115">The **Console** panel</span></span>  
:::image-end:::  

<span data-ttu-id="98b19-116">To open the Console panel from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span><span class="sxs-lookup"><span data-stu-id="98b19-116">To open the Console panel from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="The Console panel" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="98b19-118">The command to show the **Console** panel</span><span class="sxs-lookup"><span data-stu-id="98b19-118">The command to show the **Console** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="98b19-119">Open the Console tab in the Drawer</span><span class="sxs-lookup"><span data-stu-id="98b19-119">Open the Console tab in the Drawer</span></span>   

<span data-ttu-id="98b19-120">Press `Escape` or click **Customize And Control DevTools** \(`...`\) and then select **Show console drawer**.</span><span class="sxs-lookup"><span data-stu-id="98b19-120">Press `Escape` or click **Customize And Control DevTools** \(`...`\) and then select **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="The Console panel" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="98b19-122">Show console drawer</span><span class="sxs-lookup"><span data-stu-id="98b19-122">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="98b19-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tab open.</span><span class="sxs-lookup"><span data-stu-id="98b19-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tab open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="The Console panel" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="98b19-125">The **Console** tab in the **Drawer**</span><span class="sxs-lookup"><span data-stu-id="98b19-125">The **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="98b19-126">To open the Console tab from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span><span class="sxs-lookup"><span data-stu-id="98b19-126">To open the Console tab from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="The Console panel" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="98b19-128">The command to show the **Console** tab in the **Drawer**</span><span class="sxs-lookup"><span data-stu-id="98b19-128">The command to show the **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

### <span data-ttu-id="98b19-129">Open Console Settings</span><span class="sxs-lookup"><span data-stu-id="98b19-129">Open Console Settings</span></span>   

<span data-ttu-id="98b19-130">Click **Console Settings** \(![Console Settings][ImageSettingsButtonIcon]\).</span><span class="sxs-lookup"><span data-stu-id="98b19-130">Click **Console Settings** \(![Console Settings][ImageSettingsButtonIcon]\).</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="The Console panel" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="98b19-132">Console Settings</span><span class="sxs-lookup"><span data-stu-id="98b19-132">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="98b19-133">The links below explain each setting:</span><span class="sxs-lookup"><span data-stu-id="98b19-133">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="98b19-134">Hide Network</span><span class="sxs-lookup"><span data-stu-id="98b19-134">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="98b19-135">Preserve Log</span><span class="sxs-lookup"><span data-stu-id="98b19-135">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="98b19-136">Selected Context Only</span><span class="sxs-lookup"><span data-stu-id="98b19-136">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="98b19-137">Group Similar</span><span class="sxs-lookup"><span data-stu-id="98b19-137">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="98b19-138">Log XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="98b19-138">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="98b19-139">Eager Evaluation</span><span class="sxs-lookup"><span data-stu-id="98b19-139">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="98b19-140">Autocomplete From History</span><span class="sxs-lookup"><span data-stu-id="98b19-140">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  
    
### <span data-ttu-id="98b19-141">Open the Console Sidebar</span><span class="sxs-lookup"><span data-stu-id="98b19-141">Open the Console Sidebar</span></span>   

<span data-ttu-id="98b19-142">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\) to show the Sidebar, which is useful for filtering.</span><span class="sxs-lookup"><span data-stu-id="98b19-142">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\) to show the Sidebar, which is useful for filtering.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="The Console panel" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   <span data-ttu-id="98b19-144">**Console** Sidebar</span><span class="sxs-lookup"><span data-stu-id="98b19-144">**Console** Sidebar</span></span>  
:::image-end:::  

## <span data-ttu-id="98b19-145">View messages</span><span class="sxs-lookup"><span data-stu-id="98b19-145">View messages</span></span>   

<span data-ttu-id="98b19-146">This section contains features that change how messages are presented in the Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-146">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="98b19-147">See [View messages][DevToolsConsoleViewMessages] for a hands-on walkthrough.</span><span class="sxs-lookup"><span data-stu-id="98b19-147">See [View messages][DevToolsConsoleViewMessages] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="98b19-148">Disable message grouping</span><span class="sxs-lookup"><span data-stu-id="98b19-148">Disable message grouping</span></span>   

<span data-ttu-id="98b19-149">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-149">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="98b19-150">See [Log XHR and Fetch requests](#log-xhr-and-fetch-requests) for an example.</span><span class="sxs-lookup"><span data-stu-id="98b19-150">See [Log XHR and Fetch requests](#log-xhr-and-fetch-requests) for an example.</span></span>  

### <span data-ttu-id="98b19-151">Log XHR and Fetch requests</span><span class="sxs-lookup"><span data-stu-id="98b19-151">Log XHR and Fetch requests</span></span>   

<span data-ttu-id="98b19-152">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span><span class="sxs-lookup"><span data-stu-id="98b19-152">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="The Console panel" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="98b19-154">Log `XMLHttpRequest` and `Fetch` requests</span><span class="sxs-lookup"><span data-stu-id="98b19-154">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  
<span data-ttu-id="98b19-155">The top message in previous figure displays the default grouping behavior of the **Console**.</span><span class="sxs-lookup"><span data-stu-id="98b19-155">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="The Console panel" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <span data-ttu-id="98b19-156">Persist messages across page loads</span><span class="sxs-lookup"><span data-stu-id="98b19-156">Persist messages across page loads</span></span>   

<span data-ttu-id="98b19-157">By default the Console clears whenever you load a new page.</span><span class="sxs-lookup"><span data-stu-id="98b19-157">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="98b19-158">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span><span class="sxs-lookup"><span data-stu-id="98b19-158">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <span data-ttu-id="98b19-159">Hide network messages</span><span class="sxs-lookup"><span data-stu-id="98b19-159">Hide network messages</span></span>   

<span data-ttu-id="98b19-160">By default the browser logs network messages to the **Console**.</span><span class="sxs-lookup"><span data-stu-id="98b19-160">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="98b19-161">In the following figure, the selected message represents an HTTP status code of `429`.</span><span class="sxs-lookup"><span data-stu-id="98b19-161">In the following figure, the selected message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="The Console panel" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="98b19-163">A `429` message in the **Console**</span><span class="sxs-lookup"><span data-stu-id="98b19-163">A `429` message in the **Console**</span></span>  
:::image-end:::  
<span data-ttu-id="98b19-164">To hide network messages:</span><span class="sxs-lookup"><span data-stu-id="98b19-164">To hide network messages:</span></span>  

1.  <span data-ttu-id="98b19-165">[Open Console Settings](#open-console-settings).</span><span class="sxs-lookup"><span data-stu-id="98b19-165">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="98b19-166">Enable the **Hide Network** checkbox.</span><span class="sxs-lookup"><span data-stu-id="98b19-166">Enable the **Hide Network** checkbox.</span></span>  
    
## <span data-ttu-id="98b19-167">Filter messages</span><span class="sxs-lookup"><span data-stu-id="98b19-167">Filter messages</span></span>   

<span data-ttu-id="98b19-168">There are many ways to filter out messages in the Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-168">There are many ways to filter out messages in the Console.</span></span>  

### <span data-ttu-id="98b19-169">Filter out browser messages</span><span class="sxs-lookup"><span data-stu-id="98b19-169">Filter out browser messages</span></span>   

<span data-ttu-id="98b19-170">[Open the Console Sidebar](#open-the-console-sidebar) and click **User Messages** to only show messages that came from the JavaScript of the page.</span><span class="sxs-lookup"><span data-stu-id="98b19-170">[Open the Console Sidebar](#open-the-console-sidebar) and click **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="The Console panel" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="98b19-172">View user messages</span><span class="sxs-lookup"><span data-stu-id="98b19-172">View user messages</span></span>  
:::image-end:::  

### <span data-ttu-id="98b19-173">Filter by log level</span><span class="sxs-lookup"><span data-stu-id="98b19-173">Filter by log level</span></span>   

<span data-ttu-id="98b19-174">DevTools assigns each `console.*` method a severity level.</span><span class="sxs-lookup"><span data-stu-id="98b19-174">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="98b19-175">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span><span class="sxs-lookup"><span data-stu-id="98b19-175">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="98b19-176">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span><span class="sxs-lookup"><span data-stu-id="98b19-176">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="98b19-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span><span class="sxs-lookup"><span data-stu-id="98b19-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="98b19-178">Every message that the browser logs to the Console has a severity level too.</span><span class="sxs-lookup"><span data-stu-id="98b19-178">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="98b19-179">You may hide any level of messages that you are not interested in.</span><span class="sxs-lookup"><span data-stu-id="98b19-179">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="98b19-180">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span><span class="sxs-lookup"><span data-stu-id="98b19-180">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="98b19-181">Click the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span><span class="sxs-lookup"><span data-stu-id="98b19-181">Click the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="The Console panel" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="98b19-183">The **Log Levels** dropdown</span><span class="sxs-lookup"><span data-stu-id="98b19-183">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="98b19-184">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and then clicking **Errors**, **Warnings**, **Info**, or **Verbose**.</span><span class="sxs-lookup"><span data-stu-id="98b19-184">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and then clicking **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="The Console panel" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="98b19-186">Use the Sidebar to view warnings</span><span class="sxs-lookup"><span data-stu-id="98b19-186">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <span data-ttu-id="98b19-187">Filter messages by URL</span><span class="sxs-lookup"><span data-stu-id="98b19-187">Filter messages by URL</span></span>   

<span data-ttu-id="98b19-188">Type `url:` followed by a URL to only view messages that came from that URL.</span><span class="sxs-lookup"><span data-stu-id="98b19-188">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="98b19-189">After you type `url:` DevTools shows all relevant URLs.</span><span class="sxs-lookup"><span data-stu-id="98b19-189">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="98b19-190">Domains also work.</span><span class="sxs-lookup"><span data-stu-id="98b19-190">Domains also work.</span></span>  <span data-ttu-id="98b19-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span><span class="sxs-lookup"><span data-stu-id="98b19-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="The Console panel" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="98b19-193">A URL filter</span><span class="sxs-lookup"><span data-stu-id="98b19-193">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="98b19-194">Type `-url:` to hide messages from that URL.</span><span class="sxs-lookup"><span data-stu-id="98b19-194">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="98b19-195">This is called a negative URL filter.</span><span class="sxs-lookup"><span data-stu-id="98b19-195">This is called a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="The Console panel" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="98b19-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span><span class="sxs-lookup"><span data-stu-id="98b19-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="98b19-198">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and then clicking the URL of the script containing the messages on which you want to focus.</span><span class="sxs-lookup"><span data-stu-id="98b19-198">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and then clicking the URL of the script containing the messages on which you want to focus.</span></span>  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="The Console panel" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="98b19-200">View the messages that came from</span><span class="sxs-lookup"><span data-stu-id="98b19-200">View the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <span data-ttu-id="98b19-201">Filter out messages from different contexts</span><span class="sxs-lookup"><span data-stu-id="98b19-201">Filter out messages from different contexts</span></span>   

<span data-ttu-id="98b19-202">Suppose that you have an advertisement \(ad\) on your page.</span><span class="sxs-lookup"><span data-stu-id="98b19-202">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="98b19-203">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-203">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="98b19-204">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and enable the **Selected Context Only** checkbox.</span><span class="sxs-lookup"><span data-stu-id="98b19-204">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and enable the **Selected Context Only** checkbox.</span></span>  

### <span data-ttu-id="98b19-205">Filter out messages that do not match a regular expression pattern</span><span class="sxs-lookup"><span data-stu-id="98b19-205">Filter out messages that do not match a regular expression pattern</span></span>   

<span data-ttu-id="98b19-206">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span><span class="sxs-lookup"><span data-stu-id="98b19-206">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="98b19-207">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span><span class="sxs-lookup"><span data-stu-id="98b19-207">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="The Console panel" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="98b19-209">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span><span class="sxs-lookup"><span data-stu-id="98b19-209">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <span data-ttu-id="98b19-210">Run JavaScript</span><span class="sxs-lookup"><span data-stu-id="98b19-210">Run JavaScript</span></span>   

<span data-ttu-id="98b19-211">This section contains features related to running JavaScript in the Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-211">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="98b19-212">See [Run JavaScript][DevToolsConsoleOverviewJavascript] for a hands-on walkthrough.</span><span class="sxs-lookup"><span data-stu-id="98b19-212">See [Run JavaScript][DevToolsConsoleOverviewJavascript] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="98b19-213">Re-run expressions from history</span><span class="sxs-lookup"><span data-stu-id="98b19-213">Re-run expressions from history</span></span>   

<span data-ttu-id="98b19-214">Press the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-214">Press the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="98b19-215">Press `Enter` to run that expression again.</span><span class="sxs-lookup"><span data-stu-id="98b19-215">Press `Enter` to run that expression again.</span></span>  

### <span data-ttu-id="98b19-216">Watch the value of an expression in real-time with Live Expressions</span><span class="sxs-lookup"><span data-stu-id="98b19-216">Watch the value of an expression in real-time with Live Expressions</span></span>   

<span data-ttu-id="98b19-217">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span><span class="sxs-lookup"><span data-stu-id="98b19-217">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="98b19-218">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span><span class="sxs-lookup"><span data-stu-id="98b19-218">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="98b19-219">The value of the expression updates in near real-time.</span><span class="sxs-lookup"><span data-stu-id="98b19-219">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="98b19-220">See [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span><span class="sxs-lookup"><span data-stu-id="98b19-220">See [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <span data-ttu-id="98b19-221">Disable Eager Evaluation</span><span class="sxs-lookup"><span data-stu-id="98b19-221">Disable Eager Evaluation</span></span>   

<span data-ttu-id="98b19-222">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span><span class="sxs-lookup"><span data-stu-id="98b19-222">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="98b19-223">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span><span class="sxs-lookup"><span data-stu-id="98b19-223">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <span data-ttu-id="98b19-224">Disable autocomplete from history</span><span class="sxs-lookup"><span data-stu-id="98b19-224">Disable autocomplete from history</span></span>   

<span data-ttu-id="98b19-225">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span><span class="sxs-lookup"><span data-stu-id="98b19-225">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="98b19-226">These expressions are prepended with the `>` character.</span><span class="sxs-lookup"><span data-stu-id="98b19-226">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="98b19-227">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span><span class="sxs-lookup"><span data-stu-id="98b19-227">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="98b19-228">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span><span class="sxs-lookup"><span data-stu-id="98b19-228">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="The Console panel" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="98b19-230">The autocomplete popup displays expressions from history</span><span class="sxs-lookup"><span data-stu-id="98b19-230">The autocomplete popup displays expressions from history</span></span>  
:::image-end:::  

### <span data-ttu-id="98b19-231">Select JavaScript context</span><span class="sxs-lookup"><span data-stu-id="98b19-231">Select JavaScript context</span></span>   

<span data-ttu-id="98b19-232">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span><span class="sxs-lookup"><span data-stu-id="98b19-232">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="The Console panel" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="98b19-234">The **JavaScript Context** dropdown</span><span class="sxs-lookup"><span data-stu-id="98b19-234">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="98b19-235">Suppose you have an ad on your page embedded in an `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="98b19-235">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="98b19-236">You want to run JavaScript in order to tweak the DOM of the ad.</span><span class="sxs-lookup"><span data-stu-id="98b19-236">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="98b19-237">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span><span class="sxs-lookup"><span data-stu-id="98b19-237">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="The Console panel" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="98b19-239">Select a different JavaScript context</span><span class="sxs-lookup"><span data-stu-id="98b19-239">Select a different JavaScript context</span></span>  
:::image-end:::  

## <span data-ttu-id="98b19-240">Clear the Console</span><span class="sxs-lookup"><span data-stu-id="98b19-240">Clear the Console</span></span>   

<span data-ttu-id="98b19-241">You may use any of the following workflows to clear the Console:</span><span class="sxs-lookup"><span data-stu-id="98b19-241">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="98b19-242">Click **Clear Console** \(![Clear Console][ImageClearConsoleIcon]\).</span><span class="sxs-lookup"><span data-stu-id="98b19-242">Click **Clear Console** \(![Clear Console][ImageClearConsoleIcon]\).</span></span>  
*   <span data-ttu-id="98b19-243">Right-click a message and then select **Clear Console**.</span><span class="sxs-lookup"><span data-stu-id="98b19-243">Right-click a message and then select **Clear Console**.</span></span>  
*   <span data-ttu-id="98b19-244">Type `clear()` in the Console and then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="98b19-244">Type `clear()` in the Console and then press `Enter`.</span></span>  
*   <span data-ttu-id="98b19-245">Call `console.clear()` from the JavaScript for your webpage.</span><span class="sxs-lookup"><span data-stu-id="98b19-245">Call `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="98b19-246">Press `Control`+`L` while the Console is in focus.</span><span class="sxs-lookup"><span data-stu-id="98b19-246">Press `Control`+`L` while the Console is in focus.</span></span>  
    
<!--
 

  
-->  

<!-- image links -->  

[ImageClearConsoleIcon]: ../media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: ../media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Run commands with the Microsoft Edge DevTools Command menu | Microsoft Docs"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "Viewing logged messages - Console overview | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "Console API reference | Microsoft Docs"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "Running JavaScript - Console overview | Microsoft Docs"  
[DevToolsConsoleJavascript]: ./javascript.md "Get started with running JavaScript in the Console | Microsoft Docs"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "Watch JavaScript expression values in real-time with Live Expressions | Microsoft Docs"  
[DevToolsConsoleLog]: ./log.md "Get started with logging messages in the Console | Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "Console Utilities API reference | Microsoft Docs"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "Browsing context | MDN"  

> [!NOTE]
> <span data-ttu-id="98b19-256">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="98b19-256">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="98b19-257">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="98b19-257">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="98b19-259">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="98b19-259">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
