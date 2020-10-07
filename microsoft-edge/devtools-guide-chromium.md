---
description: Get to know the Microsoft Edge (Chromium) Developer Tools
title: Microsoft Edge (Chromium) Developer Tools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: ba925c402d33ba75c558006c7c43c5dc05515911
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003934"
---
# <span data-ttu-id="47e5f-104">Microsoft Edge (Chromium) Developer Tools</span><span class="sxs-lookup"><span data-stu-id="47e5f-104">Microsoft Edge (Chromium) Developer Tools</span></span>  

<span data-ttu-id="47e5f-105">Microsoft Edge has adopted the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms.</span><span class="sxs-lookup"><span data-stu-id="47e5f-105">Microsoft Edge has adopted the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms.</span></span>  <span data-ttu-id="47e5f-106">This change should make it easier for you to build and test your websites in Microsoft Edge and ensure that each works as expected even while viewed in a different Chromium-based browser \(such as Google Chrome, Vivaldi, Opera, or Brave\).</span><span class="sxs-lookup"><span data-stu-id="47e5f-106">This change should make it easier for you to build and test your websites in Microsoft Edge and ensure that each works as expected even while viewed in a different Chromium-based browser \(such as Google Chrome, Vivaldi, Opera, or Brave\).</span></span>  

<span data-ttu-id="47e5f-107">As the web has grown in usage across an ever-widening array of device types, the complexity and overhead involved in testing websites has exploded.</span><span class="sxs-lookup"><span data-stu-id="47e5f-107">As the web has grown in usage across an ever-widening array of device types, the complexity and overhead involved in testing websites has exploded.</span></span> <span data-ttu-id="47e5f-108">Since web developers \(particularly those at small companies\) must test against so many different systems, you may find it nearly impossible to ensure that sites work well on all device types and all browsers.</span><span class="sxs-lookup"><span data-stu-id="47e5f-108">Since web developers \(particularly those at small companies\) must test against so many different systems, you may find it nearly impossible to ensure that sites work well on all device types and all browsers.</span></span>  <span data-ttu-id="47e5f-109">Now that Microsoft Edge is based on Chromium, the Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers and provided a best-in-class developer tooling experience, both inside the browser and with the other developer tools you use every day \(such as Visual Studio Code\).</span><span class="sxs-lookup"><span data-stu-id="47e5f-109">Now that Microsoft Edge is based on Chromium, the Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers and provided a best-in-class developer tooling experience, both inside the browser and with the other developer tools you use every day \(such as Visual Studio Code\).</span></span>  

<span data-ttu-id="47e5f-110">If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.</span><span class="sxs-lookup"><span data-stu-id="47e5f-110">If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.</span></span>  <span data-ttu-id="47e5f-111">The Microsoft Edge \(Chromium\) Developer Tools function in the same way as the developer tools you already know and use.</span><span class="sxs-lookup"><span data-stu-id="47e5f-111">The Microsoft Edge \(Chromium\) Developer Tools function in the same way as the developer tools you already know and use.</span></span>  <span data-ttu-id="47e5f-112">For more information, see [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span><span class="sxs-lookup"><span data-stu-id="47e5f-112">For more information, see [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   <span data-ttu-id="47e5f-114">Microsoft Edge (Chromium) DevTools</span><span class="sxs-lookup"><span data-stu-id="47e5f-114">Microsoft Edge (Chromium) DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="47e5f-115">If you are checking out the next version of Microsoft Edge and you previously developed in Microsoft Edge \(EdgeHTML\), you now have some great new tools that should make it easier and faster to build and test your websites in Microsoft Edge!</span><span class="sxs-lookup"><span data-stu-id="47e5f-115">If you are checking out the next version of Microsoft Edge and you previously developed in Microsoft Edge \(EdgeHTML\), you now have some great new tools that should make it easier and faster to build and test your websites in Microsoft Edge!</span></span>  

## <span data-ttu-id="47e5f-116">Open the DevTools</span><span class="sxs-lookup"><span data-stu-id="47e5f-116">Open the DevTools</span></span>  

<span data-ttu-id="47e5f-117">If you have never used the DevTools before, the Microsoft Edge Developer Tools are a set of tools built directly into the Microsoft Edge browser.</span><span class="sxs-lookup"><span data-stu-id="47e5f-117">If you have never used the DevTools before, the Microsoft Edge Developer Tools are a set of tools built directly into the Microsoft Edge browser.</span></span>  <span data-ttu-id="47e5f-118">With these DevTools, you are able to do the following.</span><span class="sxs-lookup"><span data-stu-id="47e5f-118">With these DevTools, you are able to do the following.</span></span>  

*   <span data-ttu-id="47e5f-119">Inspect and make changes to your HTML website</span><span class="sxs-lookup"><span data-stu-id="47e5f-119">Inspect and make changes to your HTML website</span></span>  
*   <span data-ttu-id="47e5f-120">Edit CSS and instantly see preview how your website renders</span><span class="sxs-lookup"><span data-stu-id="47e5f-120">Edit CSS and instantly see preview how your website renders</span></span>  
*   <span data-ttu-id="47e5f-121">See all the `console.log()` statements from your front-end JavaScript code</span><span class="sxs-lookup"><span data-stu-id="47e5f-121">See all the `console.log()` statements from your front-end JavaScript code</span></span>  
*   <span data-ttu-id="47e5f-122">Debug your script by setting breakpoints and stepping through it line by line</span><span class="sxs-lookup"><span data-stu-id="47e5f-122">Debug your script by setting breakpoints and stepping through it line by line</span></span>  

<span data-ttu-id="47e5f-123">all directly within the browser.</span><span class="sxs-lookup"><span data-stu-id="47e5f-123">all directly within the browser.</span></span>  <span data-ttu-id="47e5f-124">These are just examples of some of the features the DevTools provide to make it easier and faster for you to build and test your websites in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="47e5f-124">These are just examples of some of the features the DevTools provide to make it easier and faster for you to build and test your websites in Microsoft Edge.</span></span>  

<span data-ttu-id="47e5f-125">To open the DevTools</span><span class="sxs-lookup"><span data-stu-id="47e5f-125">To open the DevTools</span></span>  

*   <span data-ttu-id="47e5f-126">press</span><span class="sxs-lookup"><span data-stu-id="47e5f-126">press</span></span> `F12` 
*   <span data-ttu-id="47e5f-127">press `Ctrl`+`Shift`+`I` on Windows \(`Command`+`Option`+`I` on macOS\)</span><span class="sxs-lookup"><span data-stu-id="47e5f-127">press `Ctrl`+`Shift`+`I` on Windows \(`Command`+`Option`+`I` on macOS\)</span></span>  

<span data-ttu-id="47e5f-128">If you want to see the HTML or CSS for an element on your site, right-click the element and select **Inspect** to jump into the Elements panel.</span><span class="sxs-lookup"><span data-stu-id="47e5f-128">If you want to see the HTML or CSS for an element on your site, right-click the element and select **Inspect** to jump into the Elements panel.</span></span>  <span data-ttu-id="47e5f-129">You may also press `Ctrl`+`Shift`+`C` on Windows \(`Command`+`Option`+`C` on macOS\) to open the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="47e5f-129">You may also press `Ctrl`+`Shift`+`C` on Windows \(`Command`+`Option`+`C` on macOS\) to open the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel.</span></span>  

<span data-ttu-id="47e5f-130">If you want to see logs from your front-end JavaScript code or quickly run some script, press `Ctrl`+`Shift`+`J` on Windows or `Command`+`Option`+`J` on macOS to launch the Console panel in the DevTools.</span><span class="sxs-lookup"><span data-stu-id="47e5f-130">If you want to see logs from your front-end JavaScript code or quickly run some script, press `Ctrl`+`Shift`+`J` on Windows or `Command`+`Option`+`J` on macOS to launch the Console panel in the DevTools.</span></span>  

## <span data-ttu-id="47e5f-131">Core tools</span><span class="sxs-lookup"><span data-stu-id="47e5f-131">Core tools</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   <span data-ttu-id="47e5f-133">Microsoft Edge (Chromium) DevTools core tools</span><span class="sxs-lookup"><span data-stu-id="47e5f-133">Microsoft Edge (Chromium) DevTools core tools</span></span>  
:::image-end::: 

<span data-ttu-id="47e5f-134">The Microsoft Edge \(Chromium\) DevTools include the following panels.</span><span class="sxs-lookup"><span data-stu-id="47e5f-134">The Microsoft Edge \(Chromium\) DevTools include the following panels.</span></span>  

*   <span data-ttu-id="47e5f-135">An **Elements** panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span><span class="sxs-lookup"><span data-stu-id="47e5f-135">An **Elements** panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="47e5f-136">**控制台**，用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点，并在所选窗口或框架的上下文中运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="47e5f-136">A **Console** to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="47e5f-137">A **Sources** panel to open and live edit your code, set breakpoints, step through code, and see the state of your website one line of JavaScript at a time</span><span class="sxs-lookup"><span data-stu-id="47e5f-137">A **Sources** panel to open and live edit your code, set breakpoints, step through code, and see the state of your website one line of JavaScript at a time</span></span>  
*   <span data-ttu-id="47e5f-138">A **Network** panel to monitor and inspect requests and responses from the network and browser cache</span><span class="sxs-lookup"><span data-stu-id="47e5f-138">A **Network** panel to monitor and inspect requests and responses from the network and browser cache</span></span>   
*   <span data-ttu-id="47e5f-139">“**性能**”面板，用于分析网站所需的时间和系统资源</span><span class="sxs-lookup"><span data-stu-id="47e5f-139">A **Performance** panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="47e5f-140">A **Memory** panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span><span class="sxs-lookup"><span data-stu-id="47e5f-140">A **Memory** panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="47e5f-141">An **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span><span class="sxs-lookup"><span data-stu-id="47e5f-141">An **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  <span data-ttu-id="47e5f-142">You may also inspect and manage storage, databases, and caches from the **Application** panel.</span><span class="sxs-lookup"><span data-stu-id="47e5f-142">You may also inspect and manage storage, databases, and caches from the **Application** panel.</span></span>  
*   <span data-ttu-id="47e5f-143">A **Security** panel to debug security issues and ensure that you have properly implemented HTTPS on your website.</span><span class="sxs-lookup"><span data-stu-id="47e5f-143">A **Security** panel to debug security issues and ensure that you have properly implemented HTTPS on your website.</span></span>  <span data-ttu-id="47e5f-144">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span><span class="sxs-lookup"><span data-stu-id="47e5f-144">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span></span>  
*   <span data-ttu-id="47e5f-145">An **Audits** panel \(now renamed **Lighthouse**\) to run an audit of your website.</span><span class="sxs-lookup"><span data-stu-id="47e5f-145">An **Audits** panel \(now renamed **Lighthouse**\) to run an audit of your website.</span></span>  <span data-ttu-id="47e5f-146">The results of the audit help you improve the quality of your site in the following ways.</span><span class="sxs-lookup"><span data-stu-id="47e5f-146">The results of the audit help you improve the quality of your site in the following ways.</span></span>  
    *   <span data-ttu-id="47e5f-147">Catch common errors related to making your website accessible, secure, performant, and so on.</span><span class="sxs-lookup"><span data-stu-id="47e5f-147">Catch common errors related to making your website accessible, secure, performant, and so on.</span></span>  
    *   <span data-ttu-id="47e5f-148">Fix each error.</span><span class="sxs-lookup"><span data-stu-id="47e5f-148">Fix each error.</span></span>  
    *   <span data-ttu-id="47e5f-149">Build a PWA.</span><span class="sxs-lookup"><span data-stu-id="47e5f-149">Build a PWA.</span></span>  

[!INCLUDE [audits-panel-note](./devtools-guide-chromium/includes/audits-panel-note.md)]  

<span data-ttu-id="47e5f-150">Please send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span><span class="sxs-lookup"><span data-stu-id="47e5f-150">Please send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <span data-ttu-id="47e5f-151">Extensions</span><span class="sxs-lookup"><span data-stu-id="47e5f-151">Extensions</span></span>  

<span data-ttu-id="47e5f-152">You may have used extensions to the DevTools to help you diagnose and debug issues when building your websites or apps.</span><span class="sxs-lookup"><span data-stu-id="47e5f-152">You may have used extensions to the DevTools to help you diagnose and debug issues when building your websites or apps.</span></span>  <span data-ttu-id="47e5f-153">You may acquire extensions for Microsoft Edge from the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page.</span><span class="sxs-lookup"><span data-stu-id="47e5f-153">You may acquire extensions for Microsoft Edge from the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page.</span></span>  <span data-ttu-id="47e5f-154">From the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page, you may browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span><span class="sxs-lookup"><span data-stu-id="47e5f-154">From the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page, you may browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span></span>  

<span data-ttu-id="47e5f-155">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span><span class="sxs-lookup"><span data-stu-id="47e5f-155">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   <span data-ttu-id="47e5f-157">Chrome Web Store in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="47e5f-157">Chrome Web Store in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="47e5f-158">At the top, select **Allow extensions from other stores** and then select **Allow** in the dialog that appears.</span><span class="sxs-lookup"><span data-stu-id="47e5f-158">At the top, select **Allow extensions from other stores** and then select **Allow** in the dialog that appears.</span></span>  

> [!NOTE]
> <span data-ttu-id="47e5f-159">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span><span class="sxs-lookup"><span data-stu-id="47e5f-159">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span></span>  

<span data-ttu-id="47e5f-160">Select **Add to Chrome** to add your DevTools extension to Microsoft Edge!</span><span class="sxs-lookup"><span data-stu-id="47e5f-160">Select **Add to Chrome** to add your DevTools extension to Microsoft Edge!</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   <span data-ttu-id="47e5f-162">Adding extension from Chrome Web Store to Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="47e5f-162">Adding extension from Chrome Web Store to Microsoft Edge</span></span>  
:::image-end:::  

## <span data-ttu-id="47e5f-163">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="47e5f-163">Shortcuts</span></span>  

<span data-ttu-id="47e5f-164">These shortcuts control the main DevTools window, work across all tools, or both.</span><span class="sxs-lookup"><span data-stu-id="47e5f-164">These shortcuts control the main DevTools window, work across all tools, or both.</span></span>  

| <span data-ttu-id="47e5f-165">Action</span><span class="sxs-lookup"><span data-stu-id="47e5f-165">Action</span></span> | <span data-ttu-id="47e5f-166">Windows</span><span class="sxs-lookup"><span data-stu-id="47e5f-166">Windows</span></span> | <span data-ttu-id="47e5f-167">macOS</span><span class="sxs-lookup"><span data-stu-id="47e5f-167">macOS</span></span> |  
|:--- |:--- | :--- |  
| <span data-ttu-id="47e5f-168">Show/Hide DevTools \(opens to last viewed panel\)</span><span class="sxs-lookup"><span data-stu-id="47e5f-168">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12` <span data-ttu-id="47e5f-169">or `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="47e5f-169">or `Ctrl`+`Shift`+</span></span>`I` | `Command`+`Option`+`I` |  
| <span data-ttu-id="47e5f-170">Show the Console panel</span><span class="sxs-lookup"><span data-stu-id="47e5f-170">Show the Console panel</span></span> | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| <span data-ttu-id="47e5f-171">Show the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span><span class="sxs-lookup"><span data-stu-id="47e5f-171">Show the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| <span data-ttu-id="47e5f-172">Show Settings</span><span class="sxs-lookup"><span data-stu-id="47e5f-172">Show Settings</span></span> | `?` <span data-ttu-id="47e5f-173">or `Fn`+</span><span class="sxs-lookup"><span data-stu-id="47e5f-173">or `Fn`+</span></span>`F1` | `?` <span data-ttu-id="47e5f-174">or `Fn`+</span><span class="sxs-lookup"><span data-stu-id="47e5f-174">or `Fn`+</span></span>`F1` |  
| <span data-ttu-id="47e5f-175">Show the next panel</span><span class="sxs-lookup"><span data-stu-id="47e5f-175">Show the next panel</span></span> | `Ctrl`+`]` | `Command`+`]` |  
| <span data-ttu-id="47e5f-176">Show the previous panel</span><span class="sxs-lookup"><span data-stu-id="47e5f-176">Show the previous panel</span></span> | `Ctrl`+`[` | `Command`+`[` |  
| <span data-ttu-id="47e5f-177">Dock the DevTools in the last position used.</span><span class="sxs-lookup"><span data-stu-id="47e5f-177">Dock the DevTools in the last position used.</span></span>  <span data-ttu-id="47e5f-178">If the DevTools remain in the default position for the entire session, this shortcut undocks the DevTools into a separate window</span><span class="sxs-lookup"><span data-stu-id="47e5f-178">If the DevTools remain in the default position for the entire session, this shortcut undocks the DevTools into a separate window</span></span> | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| <span data-ttu-id="47e5f-179">Toggle **Device Mode**</span><span class="sxs-lookup"><span data-stu-id="47e5f-179">Toggle **Device Mode**</span></span> | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| <span data-ttu-id="47e5f-180">Toggle **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span><span class="sxs-lookup"><span data-stu-id="47e5f-180">Toggle **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| <span data-ttu-id="47e5f-181">Show the Command Menu</span><span class="sxs-lookup"><span data-stu-id="47e5f-181">Show the Command Menu</span></span> | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| <span data-ttu-id="47e5f-182">Show/Hide the Drawer</span><span class="sxs-lookup"><span data-stu-id="47e5f-182">Show/Hide the Drawer</span></span> | `Esc` | `Esc` |  
| <span data-ttu-id="47e5f-183">Refresh.</span><span class="sxs-lookup"><span data-stu-id="47e5f-183">Refresh.</span></span>  <span data-ttu-id="47e5f-184">This refreshes the page using the cache.</span><span class="sxs-lookup"><span data-stu-id="47e5f-184">This refreshes the page using the cache.</span></span>  | `F5` <span data-ttu-id="47e5f-185">or `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="47e5f-185">or `Ctrl`+</span></span>`R` | `Command`+`R` |  
| <span data-ttu-id="47e5f-186">Hard Refresh.</span><span class="sxs-lookup"><span data-stu-id="47e5f-186">Hard Refresh.</span></span>  <span data-ttu-id="47e5f-187">This forces Microsoft Edge to download resources again and reload.</span><span class="sxs-lookup"><span data-stu-id="47e5f-187">This forces Microsoft Edge to download resources again and reload.</span></span>  <span data-ttu-id="47e5f-188">It is possible that the used resources may come from a cached version</span><span class="sxs-lookup"><span data-stu-id="47e5f-188">It is possible that the used resources may come from a cached version</span></span> | `Ctrl`<span data-ttu-id="47e5f-189">+`F5` or `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="47e5f-189">+`F5` or `Ctrl`+`Shift`+</span></span>`R` | `Command`+`Shift`+`R` |  
| <span data-ttu-id="47e5f-190">Search for text within the current panel.</span><span class="sxs-lookup"><span data-stu-id="47e5f-190">Search for text within the current panel.</span></span>  <span data-ttu-id="47e5f-191">Not supported in the Audits, Application, and Security panels</span><span class="sxs-lookup"><span data-stu-id="47e5f-191">Not supported in the Audits, Application, and Security panels</span></span> | `Ctrl`+`F` | `Command`+`F` |  
| <span data-ttu-id="47e5f-192">Show the Search panel in the Drawer, which lets you search for text across all loaded resources</span><span class="sxs-lookup"><span data-stu-id="47e5f-192">Show the Search panel in the Drawer, which lets you search for text across all loaded resources</span></span> | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| <span data-ttu-id="47e5f-193">Open a file in the Sources panel</span><span class="sxs-lookup"><span data-stu-id="47e5f-193">Open a file in the Sources panel</span></span> | `Ctrl`<span data-ttu-id="47e5f-194">+`O` or `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="47e5f-194">+`O` or `Ctrl`+</span></span>`P` | `Command`<span data-ttu-id="47e5f-195">+`O` or `Command`+</span><span class="sxs-lookup"><span data-stu-id="47e5f-195">+`O` or `Command`+</span></span>`P` |  
| <span data-ttu-id="47e5f-196">Zoom in</span><span class="sxs-lookup"><span data-stu-id="47e5f-196">Zoom in</span></span> | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| <span data-ttu-id="47e5f-197">Zoom out</span><span class="sxs-lookup"><span data-stu-id="47e5f-197">Zoom out</span></span> | `Ctrl`+`-` | `Command`+`-` |  
| <span data-ttu-id="47e5f-198">Restore default zoom level</span><span class="sxs-lookup"><span data-stu-id="47e5f-198">Restore default zoom level</span></span> | `Ctrl`+`0` | `Command`+`0` |  
| <span data-ttu-id="47e5f-199">Run snippet</span><span class="sxs-lookup"><span data-stu-id="47e5f-199">Run snippet</span></span> | `Ctrl`<span data-ttu-id="47e5f-200">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then press</span><span class="sxs-lookup"><span data-stu-id="47e5f-200">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` | <span data-ttu-id="47e5f-201">Press `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then press</span><span class="sxs-lookup"><span data-stu-id="47e5f-201">Press `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` |  
| <span data-ttu-id="47e5f-202">Show non-editable HTML source code in a new tab</span><span class="sxs-lookup"><span data-stu-id="47e5f-202">Show non-editable HTML source code in a new tab</span></span> | `Ctrl`+`U` | <span data-ttu-id="47e5f-203">N/A</span><span class="sxs-lookup"><span data-stu-id="47e5f-203">N/A</span></span> |  

> [!NOTE]
> <span data-ttu-id="47e5f-204">If you are debugging and paused at a breakpoint, the **Refresh** shortcut resumes the runtime first.</span><span class="sxs-lookup"><span data-stu-id="47e5f-204">If you are debugging and paused at a breakpoint, the **Refresh** shortcut resumes the runtime first.</span></span>  

## <span data-ttu-id="47e5f-205">See also</span><span class="sxs-lookup"><span data-stu-id="47e5f-205">See also</span></span>  

*   [<span data-ttu-id="47e5f-206">DevTools for Beginners: Get Started with HTML and the DOM</span><span class="sxs-lookup"><span data-stu-id="47e5f-206">DevTools for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideChromiumBeginnersHtml]  
*   [<span data-ttu-id="47e5f-207">Microsoft Edge (Chromium) DevTools Protocol</span><span class="sxs-lookup"><span data-stu-id="47e5f-207">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolChromiumIndex]  

## <span data-ttu-id="47e5f-208">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="47e5f-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<span data-ttu-id="47e5f-209">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span><span class="sxs-lookup"><span data-stu-id="47e5f-209">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "DevTools for Beginners: Get Started with HTML and the DOM | Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/08/devtools "What's new in the Microsoft Edge (Chromium) DevTools | Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools Protocol | Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge Add-ons"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Download Microsoft Edge Insider Channels"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "Extensions | Chrome Web Store"  
