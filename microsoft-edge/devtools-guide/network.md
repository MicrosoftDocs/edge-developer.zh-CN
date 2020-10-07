---
description: Use the Network panel to monitor and profile page resource requests
title: DevTools - Network
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, network, load time, http, https, browser cache, HAR
ms.custom: seodec18
ms.openlocfilehash: 0b190f5163f9b7a9f9920877a94577177053e4f6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563463"
---
# <span data-ttu-id="60cdb-104">Network</span><span class="sxs-lookup"><span data-stu-id="60cdb-104">Network</span></span>

<span data-ttu-id="60cdb-105">Use the **Network** panel to monitor, inspect and profile the requests and responses sent over the wire.</span><span class="sxs-lookup"><span data-stu-id="60cdb-105">Use the **Network** panel to monitor, inspect and profile the requests and responses sent over the wire.</span></span> <span data-ttu-id="60cdb-106">With it, you can:</span><span class="sxs-lookup"><span data-stu-id="60cdb-106">With it, you can:</span></span>

 - <span data-ttu-id="60cdb-107">[Browse a record of all the resource requests](#network-summary) made by the page</span><span class="sxs-lookup"><span data-stu-id="60cdb-107">[Browse a record of all the resource requests](#network-summary) made by the page</span></span>
 - <span data-ttu-id="60cdb-108">[Measure the load time of your site](#summary-bar) for new and returning users</span><span class="sxs-lookup"><span data-stu-id="60cdb-108">[Measure the load time of your site](#summary-bar) for new and returning users</span></span> 
 - <span data-ttu-id="60cdb-109">[Inspect the headers, message bodies, parameters, and cookies](#request-details) exchanged between your page and the network</span><span class="sxs-lookup"><span data-stu-id="60cdb-109">[Inspect the headers, message bodies, parameters, and cookies](#request-details) exchanged between your page and the network</span></span>
 - <span data-ttu-id="60cdb-110">[Identify the network events causing bottlenecks](#timings) in the load time of your site</span><span class="sxs-lookup"><span data-stu-id="60cdb-110">[Identify the network events causing bottlenecks](#timings) in the load time of your site</span></span>

![The Microsoft Edge  DevTools Network panel](./media/network.png)

## <span data-ttu-id="60cdb-112">Network summary</span><span class="sxs-lookup"><span data-stu-id="60cdb-112">Network summary</span></span>

<span data-ttu-id="60cdb-113">When you open  DevTools, network profiling is turned on by default.</span><span class="sxs-lookup"><span data-stu-id="60cdb-113">When you open  DevTools, network profiling is turned on by default.</span></span> <span data-ttu-id="60cdb-114">All the network traffic from your active browser tab is recorded in the network summary list, even while you are working in a different  DevTools panel than *Network*.</span><span class="sxs-lookup"><span data-stu-id="60cdb-114">All the network traffic from your active browser tab is recorded in the network summary list, even while you are working in a different  DevTools panel than *Network*.</span></span>

![In-progress network profiling indicator](./media/network_profile_indicator.png)

### <span data-ttu-id="60cdb-116">Toolbar</span><span class="sxs-lookup"><span data-stu-id="60cdb-116">Toolbar</span></span>

<span data-ttu-id="60cdb-117">The toolbar provides controls for profiling and filtering the network activity of your page.</span><span class="sxs-lookup"><span data-stu-id="60cdb-117">The toolbar provides controls for profiling and filtering the network activity of your page.</span></span> 

![Network profiler toolbar](./media/network_toolbar.png)

1. <span data-ttu-id="60cdb-119">**Start / Stop profiling session**: By default, network profiling is turned on, and network traffic will be logged in the [**Network profiler**](#network-request-list) list.</span><span class="sxs-lookup"><span data-stu-id="60cdb-119">**Start / Stop profiling session**: By default, network profiling is turned on, and network traffic will be logged in the [**Network profiler**](#network-request-list) list.</span></span> <span data-ttu-id="60cdb-120">You can turn off network capture with the **Stop** (`Ctrl+E`) button.</span><span class="sxs-lookup"><span data-stu-id="60cdb-120">You can turn off network capture with the **Stop** (`Ctrl+E`) button.</span></span>

2. <span data-ttu-id="60cdb-121">**Export as HAR**: You can save the current network profiling session (`Ctrl+S`) as a JSON-formatted [HTTP Archive (HAR)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) file.</span><span class="sxs-lookup"><span data-stu-id="60cdb-121">**Export as HAR**: You can save the current network profiling session (`Ctrl+S`) as a JSON-formatted [HTTP Archive (HAR)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) file.</span></span> 

3. <span data-ttu-id="60cdb-122">**Content type filter**: Filter the network request list by specific content requests (*Documents, Style sheets, Images, Scripts, Media, Fonts, XHR, Other*).</span><span class="sxs-lookup"><span data-stu-id="60cdb-122">**Content type filter**: Filter the network request list by specific content requests (*Documents, Style sheets, Images, Scripts, Media, Fonts, XHR, Other*).</span></span> <span data-ttu-id="60cdb-123">By default all content types are shown.</span><span class="sxs-lookup"><span data-stu-id="60cdb-123">By default all content types are shown.</span></span>

4. <span data-ttu-id="60cdb-124">**Find**: Filter (`Ctrl+F`) the network request list by entry names (resource paths) containing a specified search string.</span><span class="sxs-lookup"><span data-stu-id="60cdb-124">**Find**: Filter (`Ctrl+F`) the network request list by entry names (resource paths) containing a specified search string.</span></span>

5. <span data-ttu-id="60cdb-125">**Always refresh from server**: Depressing this button will force page resources to load from the network rather than the browser cache.</span><span class="sxs-lookup"><span data-stu-id="60cdb-125">**Always refresh from server**: Depressing this button will force page resources to load from the network rather than the browser cache.</span></span> <span data-ttu-id="60cdb-126">You can refresh the page from  network a single time by pressing `Ctrl+F5`.</span><span class="sxs-lookup"><span data-stu-id="60cdb-126">You can refresh the page from  network a single time by pressing `Ctrl+F5`.</span></span>

6. <span data-ttu-id="60cdb-127">**Bypass Service Worker for all network requests**: Disable your registered service workers as network proxies.</span><span class="sxs-lookup"><span data-stu-id="60cdb-127">**Bypass Service Worker for all network requests**: Disable your registered service workers as network proxies.</span></span> 

7. <span data-ttu-id="60cdb-128">Clear buttons</span><span class="sxs-lookup"><span data-stu-id="60cdb-128">Clear buttons</span></span>

   - <span data-ttu-id="60cdb-129">**Clear cache**: Removes all resources stored in the browser cache (and emulates a first-time experience loading the page).</span><span class="sxs-lookup"><span data-stu-id="60cdb-129">**Clear cache**: Removes all resources stored in the browser cache (and emulates a first-time experience loading the page).</span></span>
   - <span data-ttu-id="60cdb-130">**Clear cookies**: Removes all cookies for the given domain (and emulates a first-time experience of the site).</span><span class="sxs-lookup"><span data-stu-id="60cdb-130">**Clear cookies**: Removes all cookies for the given domain (and emulates a first-time experience of the site).</span></span>
   - <span data-ttu-id="60cdb-131">**Clear entries on navigate**: Recorded traffic is cleared upon page navigation.</span><span class="sxs-lookup"><span data-stu-id="60cdb-131">**Clear entries on navigate**: Recorded traffic is cleared upon page navigation.</span></span> <span data-ttu-id="60cdb-132">This is turned on by default.</span><span class="sxs-lookup"><span data-stu-id="60cdb-132">This is turned on by default.</span></span>
   - <span data-ttu-id="60cdb-133">**Clear session**: Clears all network request entries from the **Network summary** list.</span><span class="sxs-lookup"><span data-stu-id="60cdb-133">**Clear session**: Clears all network request entries from the **Network summary** list.</span></span>

### <span data-ttu-id="60cdb-134">Network request list</span><span class="sxs-lookup"><span data-stu-id="60cdb-134">Network request list</span></span>

<span data-ttu-id="60cdb-135">All network traffic is recorded to a list (until cleared upon navigation, manually cleared, or  DevTools are closed).</span><span class="sxs-lookup"><span data-stu-id="60cdb-135">All network traffic is recorded to a list (until cleared upon navigation, manually cleared, or  DevTools are closed).</span></span> <span data-ttu-id="60cdb-136">Clicking on any entry will open a more [detailed view of the request](#request-details).</span><span class="sxs-lookup"><span data-stu-id="60cdb-136">Clicking on any entry will open a more [detailed view of the request](#request-details).</span></span>

![Network request list](./media/network_request_list.png)

<span data-ttu-id="60cdb-138">The network request list includes the following info:</span><span class="sxs-lookup"><span data-stu-id="60cdb-138">The network request list includes the following info:</span></span> 

<span data-ttu-id="60cdb-139">Column</span><span class="sxs-lookup"><span data-stu-id="60cdb-139">Column</span></span> | <span data-ttu-id="60cdb-140">描述</span><span class="sxs-lookup"><span data-stu-id="60cdb-140">Description</span></span> 
:------------ | :------------- 
**<span data-ttu-id="60cdb-141">Name</span><span class="sxs-lookup"><span data-stu-id="60cdb-141">Name</span></span>** | <span data-ttu-id="60cdb-142">Name and URL path of the request</span><span class="sxs-lookup"><span data-stu-id="60cdb-142">Name and URL path of the request</span></span>
**<span data-ttu-id="60cdb-143">Protocol</span><span class="sxs-lookup"><span data-stu-id="60cdb-143">Protocol</span></span>** |  <span data-ttu-id="60cdb-144">Type of protocol for the request (such as *HTTPS, HTTP/2*)</span><span class="sxs-lookup"><span data-stu-id="60cdb-144">Type of protocol for the request (such as *HTTPS, HTTP/2*)</span></span>
**<span data-ttu-id="60cdb-145">Method</span><span class="sxs-lookup"><span data-stu-id="60cdb-145">Method</span></span>** |    <span data-ttu-id="60cdb-146">[HTTP method](https://developer.mozilla.org/docs/Web/HTTP/Methods) used for the request</span><span class="sxs-lookup"><span data-stu-id="60cdb-146">[HTTP method](https://developer.mozilla.org/docs/Web/HTTP/Methods) used for the request</span></span>
**<span data-ttu-id="60cdb-147">Result</span><span class="sxs-lookup"><span data-stu-id="60cdb-147">Result</span></span>** |    <span data-ttu-id="60cdb-148">[HTTP response status](https://developer.mozilla.org/docs/Web/HTTP/Status)  code</span><span class="sxs-lookup"><span data-stu-id="60cdb-148">[HTTP response status](https://developer.mozilla.org/docs/Web/HTTP/Status)  code</span></span>
**<span data-ttu-id="60cdb-149">Content type</span><span class="sxs-lookup"><span data-stu-id="60cdb-149">Content type</span></span>** |  <span data-ttu-id="60cdb-150">Type of media requested ([MIME type](https://en.wikipedia.org/wiki/Media_type))</span><span class="sxs-lookup"><span data-stu-id="60cdb-150">Type of media requested ([MIME type](https://en.wikipedia.org/wiki/Media_type))</span></span>
**<span data-ttu-id="60cdb-151">Received</span><span class="sxs-lookup"><span data-stu-id="60cdb-151">Received</span></span>** | <span data-ttu-id="60cdb-152">Size of the response as delivered by the server (not calculated for cached responses)</span><span class="sxs-lookup"><span data-stu-id="60cdb-152">Size of the response as delivered by the server (not calculated for cached responses)</span></span>
**<span data-ttu-id="60cdb-153">Time</span><span class="sxs-lookup"><span data-stu-id="60cdb-153">Time</span></span>** |  <span data-ttu-id="60cdb-154">Time to load the server response (not calculated for cached responses)</span><span class="sxs-lookup"><span data-stu-id="60cdb-154">Time to load the server response (not calculated for cached responses)</span></span>
**<span data-ttu-id="60cdb-155">Initiator</span><span class="sxs-lookup"><span data-stu-id="60cdb-155">Initiator</span></span>** | <span data-ttu-id="60cdb-156">Subsystem responsible for initiating the request (such as *Parser, Redirect, Script, Other*)</span><span class="sxs-lookup"><span data-stu-id="60cdb-156">Subsystem responsible for initiating the request (such as *Parser, Redirect, Script, Other*)</span></span>
**<span data-ttu-id="60cdb-157">Timeline</span><span class="sxs-lookup"><span data-stu-id="60cdb-157">Timeline</span></span>** | <span data-ttu-id="60cdb-158">Visual timeline for the network events of the request (such as *Stalled, Resolving(DNS), Connecting(TCP), SSL, Sending, Waiting(TTFB), Downloading*).</span><span class="sxs-lookup"><span data-stu-id="60cdb-158">Visual timeline for the network events of the request (such as *Stalled, Resolving(DNS), Connecting(TCP), SSL, Sending, Waiting(TTFB), Downloading*).</span></span> <span data-ttu-id="60cdb-159">Hovering over the chart provides the more granular breakdown of network [network timings](#timings)).</span><span class="sxs-lookup"><span data-stu-id="60cdb-159">Hovering over the chart provides the more granular breakdown of network [network timings](#timings)).</span></span>

### <span data-ttu-id="60cdb-160">Summary bar</span><span class="sxs-lookup"><span data-stu-id="60cdb-160">Summary bar</span></span>

<span data-ttu-id="60cdb-161">The bar at the bottom of **Network** panel summarizes the total number of HTTP network errors, requests, data transfered, and load times during the network profiling session (i.e., since  DevTools were opened and recording network traffic).</span><span class="sxs-lookup"><span data-stu-id="60cdb-161">The bar at the bottom of **Network** panel summarizes the total number of HTTP network errors, requests, data transfered, and load times during the network profiling session (i.e., since  DevTools were opened and recording network traffic).</span></span>

![Network summary bar](./media/network_summary_bar.png)

<span data-ttu-id="60cdb-163">**Elapsed time** means the time between the start of the profiling session and when the last resource was downloaded from the network.</span><span class="sxs-lookup"><span data-stu-id="60cdb-163">**Elapsed time** means the time between the start of the profiling session and when the last resource was downloaded from the network.</span></span> <span data-ttu-id="60cdb-164">Resources fetched from the browser cache do not accrue time to this number.</span><span class="sxs-lookup"><span data-stu-id="60cdb-164">Resources fetched from the browser cache do not accrue time to this number.</span></span> 

<span data-ttu-id="60cdb-165">**DOM load time** means the time between the start of the profiling session and when the [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) event was fired to indicate that the structure of the page document has been loaded and parsed (though not necessarily any stylesheets, images or subframes).</span><span class="sxs-lookup"><span data-stu-id="60cdb-165">**DOM load time** means the time between the start of the profiling session and when the [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) event was fired to indicate that the structure of the page document has been loaded and parsed (though not necessarily any stylesheets, images or subframes).</span></span>

<span data-ttu-id="60cdb-166">**Page load time** time means the time between the start of the profiling session and when the [load](https://developer.mozilla.org/docs/Web/Events/load) event was fired to indicate that the page document (and all its resources) has been fully loaded.</span><span class="sxs-lookup"><span data-stu-id="60cdb-166">**Page load time** time means the time between the start of the profiling session and when the [load](https://developer.mozilla.org/docs/Web/Events/load) event was fired to indicate that the page document (and all its resources) has been fully loaded.</span></span>

## <span data-ttu-id="60cdb-167">Request details</span><span class="sxs-lookup"><span data-stu-id="60cdb-167">Request details</span></span>

<span data-ttu-id="60cdb-168">Clicking on any entry in the [**Network summary**](#network-summary) list will open the [**Request details**](#request-details) pane with further information in each of the following tabs.</span><span class="sxs-lookup"><span data-stu-id="60cdb-168">Clicking on any entry in the [**Network summary**](#network-summary) list will open the [**Request details**](#request-details) pane with further information in each of the following tabs.</span></span>

![Network request details pane](./media/network_request_details.png)

### <span data-ttu-id="60cdb-170">Headers</span><span class="sxs-lookup"><span data-stu-id="60cdb-170">Headers</span></span>
<span data-ttu-id="60cdb-171">Displays the [HTTP headers](https://developer.mozilla.org/docs/Web/HTTP/Headers) sent to and received from the server.</span><span class="sxs-lookup"><span data-stu-id="60cdb-171">Displays the [HTTP headers](https://developer.mozilla.org/docs/Web/HTTP/Headers) sent to and received from the server.</span></span> <span data-ttu-id="60cdb-172">Right-click on any header entry to copy it (`Ctrl+C`) to the clipboard.</span><span class="sxs-lookup"><span data-stu-id="60cdb-172">Right-click on any header entry to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="60cdb-173">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span><span class="sxs-lookup"><span data-stu-id="60cdb-173">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="60cdb-174">Body</span><span class="sxs-lookup"><span data-stu-id="60cdb-174">Body</span></span>
<span data-ttu-id="60cdb-175">Displays the body data (if available) of the request and response payloads.</span><span class="sxs-lookup"><span data-stu-id="60cdb-175">Displays the body data (if available) of the request and response payloads.</span></span>

<span data-ttu-id="60cdb-176">Image content is displayed with dimensions and size data.</span><span class="sxs-lookup"><span data-stu-id="60cdb-176">Image content is displayed with dimensions and size data.</span></span>

<span data-ttu-id="60cdb-177">Text content appears in a (read-only) editor with options to format minified content with **Pretty print** and/or **Word wrap** for easier readability.</span><span class="sxs-lookup"><span data-stu-id="60cdb-177">Text content appears in a (read-only) editor with options to format minified content with **Pretty print** and/or **Word wrap** for easier readability.</span></span>

![Body tab of the request details pane](./media/network_details_body.png)

### <span data-ttu-id="60cdb-179">Parameters</span><span class="sxs-lookup"><span data-stu-id="60cdb-179">Parameters</span></span>
<span data-ttu-id="60cdb-180">Displays query string parameters for GET requests.</span><span class="sxs-lookup"><span data-stu-id="60cdb-180">Displays query string parameters for GET requests.</span></span> <span data-ttu-id="60cdb-181">While the parameters of POST requests are sent in the headers, GET requests include them in the URL.</span><span class="sxs-lookup"><span data-stu-id="60cdb-181">While the parameters of POST requests are sent in the headers, GET requests include them in the URL.</span></span> <span data-ttu-id="60cdb-182">They're broken out here for easier reading.</span><span class="sxs-lookup"><span data-stu-id="60cdb-182">They're broken out here for easier reading.</span></span>

<span data-ttu-id="60cdb-183">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span><span class="sxs-lookup"><span data-stu-id="60cdb-183">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="60cdb-184">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span><span class="sxs-lookup"><span data-stu-id="60cdb-184">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="60cdb-185">Cookies</span><span class="sxs-lookup"><span data-stu-id="60cdb-185">Cookies</span></span>
<span data-ttu-id="60cdb-186">Displays cookies that are sent or received as key/value pairs.</span><span class="sxs-lookup"><span data-stu-id="60cdb-186">Displays cookies that are sent or received as key/value pairs.</span></span>

<span data-ttu-id="60cdb-187">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span><span class="sxs-lookup"><span data-stu-id="60cdb-187">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="60cdb-188">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span><span class="sxs-lookup"><span data-stu-id="60cdb-188">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

<span data-ttu-id="60cdb-189">You can clear the stored cookies for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button).</span><span class="sxs-lookup"><span data-stu-id="60cdb-189">You can clear the stored cookies for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button).</span></span> 

### <span data-ttu-id="60cdb-190">Timings</span><span class="sxs-lookup"><span data-stu-id="60cdb-190">Timings</span></span>

<span data-ttu-id="60cdb-191">The **Timings** tab provides a timeline of network events involved in the loading of the selected resource.</span><span class="sxs-lookup"><span data-stu-id="60cdb-191">The **Timings** tab provides a timeline of network events involved in the loading of the selected resource.</span></span> <span data-ttu-id="60cdb-192">This is similar to the information found in the *Timeline* column of the [Network request list](#network-request-list), but also includes the events leading up to the request being sent over the wire, such as time spent waiting (*Stalled*) in the request queue, DNS resolution, and establishing the TCP connection.</span><span class="sxs-lookup"><span data-stu-id="60cdb-192">This is similar to the information found in the *Timeline* column of the [Network request list](#network-request-list), but also includes the events leading up to the request being sent over the wire, such as time spent waiting (*Stalled*) in the request queue, DNS resolution, and establishing the TCP connection.</span></span> 

![Timings tab of the request details pane](./media/network_details_timings.png)

<span data-ttu-id="60cdb-194">Redirections to/from other resources are noted, and clicking on the link will set focus to that resource in the network [request details](#request details) pane.</span><span class="sxs-lookup"><span data-stu-id="60cdb-194">Redirections to/from other resources are noted, and clicking on the link will set focus to that resource in the network [request details](#request details) pane.</span></span>

<span data-ttu-id="60cdb-195">Resouces loaded from the cache are not affected by network latency, so no network *Timings* chart will display.</span><span class="sxs-lookup"><span data-stu-id="60cdb-195">Resouces loaded from the cache are not affected by network latency, so no network *Timings* chart will display.</span></span>

![Redirected resource loaded from the cache](./media/network_details_timings_cache_redirect.png)

<span data-ttu-id="60cdb-197">Here are the different network events you might see for a given resource, in chronological order:</span><span class="sxs-lookup"><span data-stu-id="60cdb-197">Here are the different network events you might see for a given resource, in chronological order:</span></span>

#### <span data-ttu-id="60cdb-198">Stalled</span><span class="sxs-lookup"><span data-stu-id="60cdb-198">Stalled</span></span>

<span data-ttu-id="60cdb-199">Time spent waiting for an available network connection in the request queue.</span><span class="sxs-lookup"><span data-stu-id="60cdb-199">Time spent waiting for an available network connection in the request queue.</span></span> <span data-ttu-id="60cdb-200">For HTTP 1.0/1.1, Microsoft Edge allows a maximum of six (6) simultaneous TCP connections per hostname.</span><span class="sxs-lookup"><span data-stu-id="60cdb-200">For HTTP 1.0/1.1, Microsoft Edge allows a maximum of six (6) simultaneous TCP connections per hostname.</span></span> 

#### <span data-ttu-id="60cdb-201">Resolving (DNS)</span><span class="sxs-lookup"><span data-stu-id="60cdb-201">Resolving (DNS)</span></span>

<span data-ttu-id="60cdb-202">Time spent looking up the IP address for the hostname of the resource in the DNS ([Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)).</span><span class="sxs-lookup"><span data-stu-id="60cdb-202">Time spent looking up the IP address for the hostname of the resource in the DNS ([Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)).</span></span>

#### <span data-ttu-id="60cdb-203">Connecting (TCP)</span><span class="sxs-lookup"><span data-stu-id="60cdb-203">Connecting (TCP)</span></span>

<span data-ttu-id="60cdb-204">Time spent establishing the TCP ([Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) connection.</span><span class="sxs-lookup"><span data-stu-id="60cdb-204">Time spent establishing the TCP ([Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) connection.</span></span>

#### <span data-ttu-id="60cdb-205">SSL</span><span class="sxs-lookup"><span data-stu-id="60cdb-205">SSL</span></span>

<span data-ttu-id="60cdb-206">Time spent negotiating a SSL ([Secure Sockets Layer](https://en.wikipedia.org/wiki/Transport_Layer_Security))  connection with the [proxy server](https://en.wikipedia.org/wiki/Proxy_server) for the host.</span><span class="sxs-lookup"><span data-stu-id="60cdb-206">Time spent negotiating a SSL ([Secure Sockets Layer](https://en.wikipedia.org/wiki/Transport_Layer_Security))  connection with the [proxy server](https://en.wikipedia.org/wiki/Proxy_server) for the host.</span></span>

#### <span data-ttu-id="60cdb-207">Sending</span><span class="sxs-lookup"><span data-stu-id="60cdb-207">Sending</span></span>

<span data-ttu-id="60cdb-208">Time spent sending the resource request.</span><span class="sxs-lookup"><span data-stu-id="60cdb-208">Time spent sending the resource request.</span></span>

#### <span data-ttu-id="60cdb-209">Waiting (TTFB)</span><span class="sxs-lookup"><span data-stu-id="60cdb-209">Waiting (TTFB)</span></span>

<span data-ttu-id="60cdb-210">Time spent waiting for the first byte of the response from the host server ("time to first byte", or *TTFB*).</span><span class="sxs-lookup"><span data-stu-id="60cdb-210">Time spent waiting for the first byte of the response from the host server ("time to first byte", or *TTFB*).</span></span>

#### <span data-ttu-id="60cdb-211">Downloading</span><span class="sxs-lookup"><span data-stu-id="60cdb-211">Downloading</span></span>

<span data-ttu-id="60cdb-212">Time spent reading the response from the server.</span><span class="sxs-lookup"><span data-stu-id="60cdb-212">Time spent reading the response from the server.</span></span>

## <span data-ttu-id="60cdb-213">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="60cdb-213">Shortcuts</span></span>

| <span data-ttu-id="60cdb-214">Action</span><span class="sxs-lookup"><span data-stu-id="60cdb-214">Action</span></span>                         | <span data-ttu-id="60cdb-215">Shortcut</span><span class="sxs-lookup"><span data-stu-id="60cdb-215">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="60cdb-216">Start / Stop profiling session</span><span class="sxs-lookup"><span data-stu-id="60cdb-216">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="60cdb-217">Export as HAR</span><span class="sxs-lookup"><span data-stu-id="60cdb-217">Export as HAR</span></span>                  | `Ctrl` + `S` |
| <span data-ttu-id="60cdb-218">Find</span><span class="sxs-lookup"><span data-stu-id="60cdb-218">Find</span></span>                           | `Ctrl` + `F` |
| <span data-ttu-id="60cdb-219">Copy</span><span class="sxs-lookup"><span data-stu-id="60cdb-219">Copy</span></span>                           | `Ctrl` + `C` |

## <span data-ttu-id="60cdb-220">Known Issues</span><span class="sxs-lookup"><span data-stu-id="60cdb-220">Known Issues</span></span>

### <span data-ttu-id="60cdb-221">The network collection agent failed to start.</span><span class="sxs-lookup"><span data-stu-id="60cdb-221">The network collection agent failed to start.</span></span>

<span data-ttu-id="60cdb-222">If you see this error message: **The network collection agent failed to start** in the Network tool, follow these steps for a workaround.</span><span class="sxs-lookup"><span data-stu-id="60cdb-222">If you see this error message: **The network collection agent failed to start** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="60cdb-223">Press `Windows Key` + `R`.</span><span class="sxs-lookup"><span data-stu-id="60cdb-223">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="60cdb-224">In the Run dialog, enter **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="60cdb-224">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="60cdb-226">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span><span class="sxs-lookup"><span data-stu-id="60cdb-226">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="60cdb-228">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span><span class="sxs-lookup"><span data-stu-id="60cdb-228">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="60cdb-230">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span><span class="sxs-lookup"><span data-stu-id="60cdb-230">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="60cdb-231">You should now see a Play badge next to **Network** and the network requests for your webpage.</span><span class="sxs-lookup"><span data-stu-id="60cdb-231">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![known-issues-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="60cdb-233">Still running into problems?</span><span class="sxs-lookup"><span data-stu-id="60cdb-233">Still running into problems?</span></span> <span data-ttu-id="60cdb-234">Please send us your feedback using the **Send feedback** icon!</span><span class="sxs-lookup"><span data-stu-id="60cdb-234">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)

### <span data-ttu-id="60cdb-236">The network collection agent failed to stop.</span><span class="sxs-lookup"><span data-stu-id="60cdb-236">The network collection agent failed to stop.</span></span>

<span data-ttu-id="60cdb-237">If you see this error message: **The network collection agent failed to stop** in the Network tool, follow these steps for a workaround.</span><span class="sxs-lookup"><span data-stu-id="60cdb-237">If you see this error message: **The network collection agent failed to stop** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="60cdb-238">Press `Windows Key` + `R`.</span><span class="sxs-lookup"><span data-stu-id="60cdb-238">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="60cdb-239">In the Run dialog, enter **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="60cdb-239">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="60cdb-241">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span><span class="sxs-lookup"><span data-stu-id="60cdb-241">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="60cdb-243">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span><span class="sxs-lookup"><span data-stu-id="60cdb-243">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="60cdb-245">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span><span class="sxs-lookup"><span data-stu-id="60cdb-245">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="60cdb-246">You should now see a Play badge next to **Network** and the network requests for your webpage.</span><span class="sxs-lookup"><span data-stu-id="60cdb-246">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![known-issues-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="60cdb-248">Still running into problems?</span><span class="sxs-lookup"><span data-stu-id="60cdb-248">Still running into problems?</span></span> <span data-ttu-id="60cdb-249">Please send us your feedback using the **Send feedback** icon!</span><span class="sxs-lookup"><span data-stu-id="60cdb-249">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)
