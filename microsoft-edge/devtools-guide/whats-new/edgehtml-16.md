---
description: Features added to the Microsoft Edge DevTools in the Windows 10 Fall Creators Update (EdgeHTML 16)
title: DevTools in EdgeHTML 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, edgehtml 16
ms.custom: seodec18
ms.openlocfilehash: 78ede81e022cc8f0f623ecd33fd2303314ec9cb0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563438"
---
# <span data-ttu-id="88bc7-104">DevTools in the Windows 10 Fall Creators Update (EdgeHTML 16)</span><span class="sxs-lookup"><span data-stu-id="88bc7-104">DevTools in the Windows 10 Fall Creators Update (EdgeHTML 16)</span></span>

<span data-ttu-id="88bc7-105">With this release we started a major DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today!</span><span class="sxs-lookup"><span data-stu-id="88bc7-105">With this release we started a major DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today!</span></span> 

<span data-ttu-id="88bc7-106">Here are the Microsoft Edge DevTools features that shipped with the [Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) ([EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)).</span><span class="sxs-lookup"><span data-stu-id="88bc7-106">Here are the Microsoft Edge DevTools features that shipped with the [Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) ([EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)).</span></span>

## <span data-ttu-id="88bc7-107">Ancestor event listeners</span><span class="sxs-lookup"><span data-stu-id="88bc7-107">Ancestor event listeners</span></span> 

<span data-ttu-id="88bc7-108">The **Events** pane now adds the option to view event listeners registered on any ancestor of the currently selected element (in the **Elements** panel), in addition to those on the element itself.</span><span class="sxs-lookup"><span data-stu-id="88bc7-108">The **Events** pane now adds the option to view event listeners registered on any ancestor of the currently selected element (in the **Elements** panel), in addition to those on the element itself.</span></span> <span data-ttu-id="88bc7-109">Additionally, you can now group the event listener display by either *Event* or *Element*.</span><span class="sxs-lookup"><span data-stu-id="88bc7-109">Additionally, you can now group the event listener display by either *Event* or *Element*.</span></span> 

![Event listener inspection pane](../media/elements_ancestor_events.png)

## <span data-ttu-id="88bc7-111">DOM mutation breakpoints</span><span class="sxs-lookup"><span data-stu-id="88bc7-111">DOM mutation breakpoints</span></span>

<span data-ttu-id="88bc7-112">You can now set DOM mutation breakpoints to break into the Debugger whenever a selected element node changes.</span><span class="sxs-lookup"><span data-stu-id="88bc7-112">You can now set DOM mutation breakpoints to break into the Debugger whenever a selected element node changes.</span></span> <span data-ttu-id="88bc7-113">From the **Elements** panel, rt-click on any element in the DOM tree view and select one or more of the following:</span><span class="sxs-lookup"><span data-stu-id="88bc7-113">From the **Elements** panel, rt-click on any element in the DOM tree view and select one or more of the following:</span></span>

 - <span data-ttu-id="88bc7-114">Break on Node removed</span><span class="sxs-lookup"><span data-stu-id="88bc7-114">Break on Node removed</span></span>
 - <span data-ttu-id="88bc7-115">Break on Subtree modified</span><span class="sxs-lookup"><span data-stu-id="88bc7-115">Break on Subtree modified</span></span>
 - <span data-ttu-id="88bc7-116">Break on Attribute modified</span><span class="sxs-lookup"><span data-stu-id="88bc7-116">Break on Attribute modified</span></span>

<span data-ttu-id="88bc7-117">You can manage your mutation breakpoints from the **DOM breakpoints** pane in the **Elements** or **Debugger** panels.</span><span class="sxs-lookup"><span data-stu-id="88bc7-117">You can manage your mutation breakpoints from the **DOM breakpoints** pane in the **Elements** or **Debugger** panels.</span></span>

![DOM breakpoints pane](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="88bc7-119">CSS at-rule support</span><span class="sxs-lookup"><span data-stu-id="88bc7-119">CSS at-rule support</span></span>

<span data-ttu-id="88bc7-120">CSS "at" (@) rules are now represented among other CSS rule declarations on the **Styles** pane, including animation `@keyframes` rules (currently limited to read-only), `@supports` feature queries, and `@media` queries.</span><span class="sxs-lookup"><span data-stu-id="88bc7-120">CSS "at" (@) rules are now represented among other CSS rule declarations on the **Styles** pane, including animation `@keyframes` rules (currently limited to read-only), `@supports` feature queries, and `@media` queries.</span></span>

![CSS at-rules inspection from the  DevTools Style pane](../media/elements_at_rules.png)

## <span data-ttu-id="88bc7-122">CSS fonts pane</span><span class="sxs-lookup"><span data-stu-id="88bc7-122">CSS fonts pane</span></span>

<span data-ttu-id="88bc7-123">CSS `@font-face` rules now have their own dedicated **Fonts** pane that displays where the font is loaded from (*Local* or *Network*) and how many characters are using it.</span><span class="sxs-lookup"><span data-stu-id="88bc7-123">CSS `@font-face` rules now have their own dedicated **Fonts** pane that displays where the font is loaded from (*Local* or *Network*) and how many characters are using it.</span></span> <span data-ttu-id="88bc7-124">If a font is loaded from the network,  DevTools will display the rule that imported it along with its alias and font type.</span><span class="sxs-lookup"><span data-stu-id="88bc7-124">If a font is loaded from the network,  DevTools will display the rule that imported it along with its alias and font type.</span></span>

![CSS font information](../media/elements_fonts.png)

## <span data-ttu-id="88bc7-126">CSS pseudo-element support</span><span class="sxs-lookup"><span data-stu-id="88bc7-126">CSS pseudo-element support</span></span>

<span data-ttu-id="88bc7-127">The **Styles** pane now groups pseudo-elements under their own headings and no longer displays their content as crossed out.</span><span class="sxs-lookup"><span data-stu-id="88bc7-127">The **Styles** pane now groups pseudo-elements under their own headings and no longer displays their content as crossed out.</span></span>

**<span data-ttu-id="88bc7-128">Before:</span><span class="sxs-lookup"><span data-stu-id="88bc7-128">Before:</span></span>**
<br>
![Generated content was previously crossed out](../media/gc_before.png)

**<span data-ttu-id="88bc7-130">After:</span><span class="sxs-lookup"><span data-stu-id="88bc7-130">After:</span></span>**
<br>
![Generated content no longer displays with a strikethrough](../media/gc_after.png)

## <span data-ttu-id="88bc7-132">Console improvements</span><span class="sxs-lookup"><span data-stu-id="88bc7-132">Console improvements</span></span>

<span data-ttu-id="88bc7-133">The **Console** panel got a UX overhaul for improved usability and a faster, richer Intellisense experience.</span><span class="sxs-lookup"><span data-stu-id="88bc7-133">The **Console** panel got a UX overhaul for improved usability and a faster, richer Intellisense experience.</span></span>

<span data-ttu-id="88bc7-134">**Before:**
![Previous console</span><span class="sxs-lookup"><span data-stu-id="88bc7-134">**Before:**
![Previous console</span></span>](../media/console_old.png)

<span data-ttu-id="88bc7-135">**After:**
![New console</span><span class="sxs-lookup"><span data-stu-id="88bc7-135">**After:**
![New console</span></span>](../media/console_new.png)

<span data-ttu-id="88bc7-136">We also added these improvements:</span><span class="sxs-lookup"><span data-stu-id="88bc7-136">We also added these improvements:</span></span>

 -  <span data-ttu-id="88bc7-137">Use `Shift + Enter` to add an additional line to a command before executing it with `Enter`.</span><span class="sxs-lookup"><span data-stu-id="88bc7-137">Use `Shift + Enter` to add an additional line to a command before executing it with `Enter`.</span></span> <span data-ttu-id="88bc7-138">(Formerly there was a *Switch to multiline/single-line mode* toggle button.)</span><span class="sxs-lookup"><span data-stu-id="88bc7-138">(Formerly there was a *Switch to multiline/single-line mode* toggle button.)</span></span>

 - <span data-ttu-id="88bc7-139">The following new APIs are supported:</span><span class="sxs-lookup"><span data-stu-id="88bc7-139">The following new APIs are supported:</span></span>
    - <span data-ttu-id="88bc7-140">[**console.table(***object***)**](../console/console-api.md#organizing-log-output) method</span><span class="sxs-lookup"><span data-stu-id="88bc7-140">[**console.table(***object***)**](../console/console-api.md#organizing-log-output) method</span></span>
    - <span data-ttu-id="88bc7-141">[**getEventListeners(***object***)**](../console/command-line.md#event-listeners) command</span><span class="sxs-lookup"><span data-stu-id="88bc7-141">[**getEventListeners(***object***)**](../console/command-line.md#event-listeners) command</span></span>
    - <span data-ttu-id="88bc7-142">[**keys(***object***)**](../console/command-line.md#object-inspection) command</span><span class="sxs-lookup"><span data-stu-id="88bc7-142">[**keys(***object***)**](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="88bc7-143">[**values(***object***)**](../console/command-line.md#object-inspection) command</span><span class="sxs-lookup"><span data-stu-id="88bc7-143">[**values(***object***)**](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="88bc7-144">[**$x(***xpath expression***)**](../console/command-line.md#dom-selectors) selector</span><span class="sxs-lookup"><span data-stu-id="88bc7-144">[**$x(***xpath expression***)**](../console/command-line.md#dom-selectors) selector</span></span>

 - <span data-ttu-id="88bc7-145">The [**%c()**](../console/console-api.md#logging-custom-messages) formatting parameter is now supported</span><span class="sxs-lookup"><span data-stu-id="88bc7-145">The [**%c()**](../console/console-api.md#logging-custom-messages) formatting parameter is now supported</span></span>

## <span data-ttu-id="88bc7-146">Debugging improvements</span><span class="sxs-lookup"><span data-stu-id="88bc7-146">Debugging improvements</span></span>

<span data-ttu-id="88bc7-147">In addition to a suite of new features for debugging your [PWA service workers and cache](#progressive-web-app-debugging), the Debugger added these features:</span><span class="sxs-lookup"><span data-stu-id="88bc7-147">In addition to a suite of new features for debugging your [PWA service workers and cache](#progressive-web-app-debugging), the Debugger added these features:</span></span>

### <span data-ttu-id="88bc7-148">Consolidated debugging for shared resources</span><span class="sxs-lookup"><span data-stu-id="88bc7-148">Consolidated debugging for shared resources</span></span>

<span data-ttu-id="88bc7-149">Even when a resource, such as a file loaded from CDN, is referenced multiple times throughout your code,  DevTools will now provide a single debugging instance for that file where you can then set common breakpoints which will be hit regardless of where that file is referenced.</span><span class="sxs-lookup"><span data-stu-id="88bc7-149">Even when a resource, such as a file loaded from CDN, is referenced multiple times throughout your code,  DevTools will now provide a single debugging instance for that file where you can then set common breakpoints which will be hit regardless of where that file is referenced.</span></span> <span data-ttu-id="88bc7-150">(Previously each script reference was considered a unique resource would map to a separate set of breakpoints.)</span><span class="sxs-lookup"><span data-stu-id="88bc7-150">(Previously each script reference was considered a unique resource would map to a separate set of breakpoints.)</span></span>

### <span data-ttu-id="88bc7-151">Live edit JavaScript with *Edit-on-idle*</span><span class="sxs-lookup"><span data-stu-id="88bc7-151">Live edit JavaScript with *Edit-on-idle*</span></span>

<span data-ttu-id="88bc7-152">You can now edit your JavaScript live during a debugging session.</span><span class="sxs-lookup"><span data-stu-id="88bc7-152">You can now edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="88bc7-153">This feature was experimentally available (behind a flag) in the [previous](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) (*Windows 10 Creators Update*) release and now its a permanent feature.</span><span class="sxs-lookup"><span data-stu-id="88bc7-153">This feature was experimentally available (behind a flag) in the [previous](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) (*Windows 10 Creators Update*) release and now its a permanent feature.</span></span> <span data-ttu-id="88bc7-154">Simply select any script file from the **Debugger** panel, edit, then click **Save** (or `Ctrl+S`) to test your changes next time that section of code runs.</span><span class="sxs-lookup"><span data-stu-id="88bc7-154">Simply select any script file from the **Debugger** panel, edit, then click **Save** (or `Ctrl+S`) to test your changes next time that section of code runs.</span></span> 

![The debugger enables you to live edit script and diff the changes](../media/debugger_edit_buttons.png) 

<span data-ttu-id="88bc7-156">Click the **Compare document to original** button to view the diff of what you changed.</span><span class="sxs-lookup"><span data-stu-id="88bc7-156">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![Diff view of edited code in the Debugger](../media/debugger_edit_code.png) 

<span data-ttu-id="88bc7-158">Please be aware of the following constraints:</span><span class="sxs-lookup"><span data-stu-id="88bc7-158">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="88bc7-159">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span><span class="sxs-lookup"><span data-stu-id="88bc7-159">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="88bc7-160">Edits are saved in memory and flushed when the document is reloaded, thus you won’t be able to run edits inside a `DOMContentLoaded` handler, for example</span><span class="sxs-lookup"><span data-stu-id="88bc7-160">Edits are saved in memory and flushed when the document is reloaded, thus you won’t be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="88bc7-161">Currently there’s no way (such as a **Save As** option) to save your edits to disk from  DevTools</span><span class="sxs-lookup"><span data-stu-id="88bc7-161">Currently there’s no way (such as a **Save As** option) to save your edits to disk from  DevTools</span></span>

## <span data-ttu-id="88bc7-162">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="88bc7-162">Shortcuts</span></span>

<span data-ttu-id="88bc7-163">You can now launch DevTools to the last viewed panel (`Ctrl+Shift+I`) or directly to the Console (`Ctrl+Shift+J`) just like you would on other major browsers.</span><span class="sxs-lookup"><span data-stu-id="88bc7-163">You can now launch DevTools to the last viewed panel (`Ctrl+Shift+I`) or directly to the Console (`Ctrl+Shift+J`) just like you would on other major browsers.</span></span>

## <span data-ttu-id="88bc7-164">Progressive Web App debugging</span><span class="sxs-lookup"><span data-stu-id="88bc7-164">Progressive Web App debugging</span></span>

<span data-ttu-id="88bc7-165">Test out the experimental support for Progressive Web Apps (PWAs) in Microsoft Edge and  DevTools by selecting the **Enable service workers** option from `about:flags` (and restarting Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="88bc7-165">Test out the experimental support for Progressive Web Apps (PWAs) in Microsoft Edge and  DevTools by selecting the **Enable service workers** option from `about:flags` (and restarting Microsoft Edge).</span></span> <span data-ttu-id="88bc7-166">If a site makes use of **Service Workers** and/or the **Cache** API,  will populate entries in the **Debugger** panel for each origin, similar to how web storage and cookie inspection work.</span><span class="sxs-lookup"><span data-stu-id="88bc7-166">If a site makes use of **Service Workers** and/or the **Cache** API,  will populate entries in the **Debugger** panel for each origin, similar to how web storage and cookie inspection work.</span></span>

<span data-ttu-id="88bc7-167">Clicking on a specific service worker entry will open up the **Service Worker Overview**, where you can manage the service worker registration for the given scope and force a test push notification.</span><span class="sxs-lookup"><span data-stu-id="88bc7-167">Clicking on a specific service worker entry will open up the **Service Worker Overview**, where you can manage the service worker registration for the given scope and force a test push notification.</span></span> <span data-ttu-id="88bc7-168">You can also **Stop**/**Start** individual service workers and **Inspect** them from a separate debugger window:</span><span class="sxs-lookup"><span data-stu-id="88bc7-168">You can also **Stop**/**Start** individual service workers and **Inspect** them from a separate debugger window:</span></span>

![Service Worker Overview pane](../media/debugger_sw_overview.png)

<span data-ttu-id="88bc7-170">Please note the following about service worker debugging:</span><span class="sxs-lookup"><span data-stu-id="88bc7-170">Please note the following about service worker debugging:</span></span>

 - <span data-ttu-id="88bc7-171">Debugging a service worker will launch a new instance of the DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span><span class="sxs-lookup"><span data-stu-id="88bc7-171">Debugging a service worker will launch a new instance of the DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span> 
 - <span data-ttu-id="88bc7-172">The [Elements](../elements.md) and [Emulation](../emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span><span class="sxs-lookup"><span data-stu-id="88bc7-172">The [Elements](../elements.md) and [Emulation](../emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="88bc7-173">Currently network traffic for a service worker is only reported from the DevTools debugging instance for that worker, and not from the central instance for the page itself.</span><span class="sxs-lookup"><span data-stu-id="88bc7-173">Currently network traffic for a service worker is only reported from the DevTools debugging instance for that worker, and not from the central instance for the page itself.</span></span>

<span data-ttu-id="88bc7-174">Clicking on a specific cache entry will open up the **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs).</span><span class="sxs-lookup"><span data-stu-id="88bc7-174">Clicking on a specific cache entry will open up the **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs).</span></span>