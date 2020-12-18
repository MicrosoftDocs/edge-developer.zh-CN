---
description: 了解 Microsoft Edge (Chromium) 开发人员工具
title: Microsoft Edge (Chromium) 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: fcae8f0974244e87ba781b94221cb5d8a1bb3dce
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232052"
---
# <span data-ttu-id="cb732-104">Microsoft Edge (Chromium) 开发人员工具概述</span><span class="sxs-lookup"><span data-stu-id="cb732-104">Microsoft Edge (Chromium) Developer Tools overview</span></span>  

<span data-ttu-id="cb732-105">Microsoft Edge 已采用 Chromium 开放源代码项目，以创建更好的 Web 兼容性和减少不同基础 Web 平台的碎片。</span><span class="sxs-lookup"><span data-stu-id="cb732-105">Microsoft Edge has adopted the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms.</span></span>  <span data-ttu-id="cb732-106">此更改应该可以更轻松地在 Microsoft Edge 中生成和测试网站，并确保每个网站按预期运行，即使在不同的基于 Chromium 的浏览器 \ (如 Google Chrome、Vivaldi、Opera 或 Cookie\) 中查看。</span><span class="sxs-lookup"><span data-stu-id="cb732-106">This change should make it easier for you to build and test your websites in Microsoft Edge and ensure that each works as expected even while viewed in a different Chromium-based browser \(such as Google Chrome, Vivaldi, Opera, or Brave\).</span></span>  

<span data-ttu-id="cb732-107">随着 Web 在设备类型的不断扩展的数组中的使用率增加，测试网站中涉及的复杂性和开销已大为增强。</span><span class="sxs-lookup"><span data-stu-id="cb732-107">As the web has grown in usage across an ever-widening array of device types, the complexity and overhead involved in testing websites has exploded.</span></span> <span data-ttu-id="cb732-108">由于 Web 开发人员\ (特别是小型公司的开发人员\) 必须针对如此多的不同系统进行测试，您可能会发现几乎不可能确保网站在所有设备类型和所有浏览器上都运行良好。</span><span class="sxs-lookup"><span data-stu-id="cb732-108">Since web developers \(particularly those at small companies\) must test against so many different systems, you may find it nearly impossible to ensure that sites work well on all device types and all browsers.</span></span>  <span data-ttu-id="cb732-109">现在，Microsoft Edge 基于 Chromium，Microsoft Edge 团队已经将 Microsoft Edge Web 平台与其他基于 Chromium 的浏览器保持一致，并提供了一流的开发人员工具体验，包括浏览器内部以及每天使用的其他开发人员工具（如 Visual Studio Code\) ）中的 (Chromium。</span><span class="sxs-lookup"><span data-stu-id="cb732-109">Now that Microsoft Edge is based on Chromium, the Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers and provided a best-in-class developer tooling experience, both inside the browser and with the other developer tools you use every day \(such as Visual Studio Code\).</span></span>  

<span data-ttu-id="cb732-110">如果你要签出 Microsoft Edge，并且主要在基于 Chromium 的浏览器中进行开发，你应该感觉在家吧。</span><span class="sxs-lookup"><span data-stu-id="cb732-110">If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.</span></span>  <span data-ttu-id="cb732-111">Microsoft Edge \ (Chromium\) 开发人员工具的功能方式与已了解和使用的开发人员工具相同。</span><span class="sxs-lookup"><span data-stu-id="cb732-111">The Microsoft Edge \(Chromium\) Developer Tools function in the same way as the developer tools you already know and use.</span></span>  <span data-ttu-id="cb732-112">有关详细信息，请导航到 [DevTools 中的 Microsoft Edge (Chromium) 新增功能][DevtoolsGuideChromiumWhatsNewIndex]。</span><span class="sxs-lookup"><span data-stu-id="cb732-112">For more information, navigate to [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span></span>  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./media/devtools.png":::
   <span data-ttu-id="cb732-114">Microsoft Edge (Chromium) DevTools</span><span class="sxs-lookup"><span data-stu-id="cb732-114">Microsoft Edge (Chromium) DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="cb732-115">如果你要签出新的 Microsoft Edge，并且你之前在 Microsoft Edge \ (EdgeHTML\) 中开发，你现在有一些出色的新工具，这些工具应该可以更轻松、更快地在 Microsoft Edge 中生成和测试你的网站。</span><span class="sxs-lookup"><span data-stu-id="cb732-115">If you are checking out the new Microsoft Edge and you previously developed in Microsoft Edge \(EdgeHTML\), you now have some great new tools that should make it easier and faster to build and test your websites in Microsoft Edge.</span></span>  

## <span data-ttu-id="cb732-116">打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="cb732-116">Open the DevTools</span></span>  

<span data-ttu-id="cb732-117">如果以前从未使用过 DevTools，Microsoft Edge 开发人员工具是直接内置于 Microsoft Edge 浏览器的一组工具。</span><span class="sxs-lookup"><span data-stu-id="cb732-117">If you have never used the DevTools before, the Microsoft Edge Developer Tools are a set of tools built directly into the Microsoft Edge browser.</span></span>  <span data-ttu-id="cb732-118">使用 DevTools，你可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="cb732-118">With the DevTools, you are able to do the following.</span></span>  

*   <span data-ttu-id="cb732-119">检查 HTML 网站并进行更改</span><span class="sxs-lookup"><span data-stu-id="cb732-119">Inspect and make changes to your HTML website</span></span>  
*   <span data-ttu-id="cb732-120">编辑 CSS 并立即查看网站呈现的预览</span><span class="sxs-lookup"><span data-stu-id="cb732-120">Edit CSS and instantly see preview how your website renders</span></span>  
*   <span data-ttu-id="cb732-121">查看前端 `console.log()` JavaScript 代码的所有语句</span><span class="sxs-lookup"><span data-stu-id="cb732-121">See all the `console.log()` statements from your front-end JavaScript code</span></span>  
*   <span data-ttu-id="cb732-122">通过设置断点并逐行执行来调试脚本</span><span class="sxs-lookup"><span data-stu-id="cb732-122">Debug your script by setting breakpoints and stepping through it line by line</span></span>  
    
<span data-ttu-id="cb732-123">全部直接在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="cb732-123">All directly within the browser.</span></span>  <span data-ttu-id="cb732-124">这些只是 DevTools 提供的一些功能的示例，以便更轻松地在 Microsoft Edge 中生成和测试网站。</span><span class="sxs-lookup"><span data-stu-id="cb732-124">These are just examples of some of the features the DevTools provide to make it easier and faster for you to build and test your websites in Microsoft Edge.</span></span>  

<span data-ttu-id="cb732-125">打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="cb732-125">To open the DevTools</span></span>  

*   <span data-ttu-id="cb732-126">选择</span><span class="sxs-lookup"><span data-stu-id="cb732-126">Select</span></span> `F12` 
*   <span data-ttu-id="cb732-127">在 `Ctrl` + `Shift` + `I` `Command` + `Option` + `I` macOS\ (Windows/Linux \) </span><span class="sxs-lookup"><span data-stu-id="cb732-127">Select `Ctrl`+`Shift`+`I` on Windows/Linux \(`Command`+`Option`+`I` on macOS\)</span></span>  
    
<span data-ttu-id="cb732-128">如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择"检查\*\*\*\*"跳转到"元素"面板。</span><span class="sxs-lookup"><span data-stu-id="cb732-128">If you want to see the HTML or CSS for an element on your site, right-click the element and select **Inspect** to jump into the Elements panel.</span></span>  <span data-ttu-id="cb732-129">还可以在 macOS\) 上按 Windows/Linux \ (以在"检查元素模式"中打开 `Ctrl` + `Shift` + `C` `Command` + `Option` + `C` DevTools，\*\*\*\*\*\*\*\* 这将允许你选择站点上的元素，并查看"元素"面板中的 HTML 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="cb732-129">You may also press `Ctrl`+`Shift`+`C` on Windows/Linux \(`Command`+`Option`+`C` on macOS\) to open the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel.</span></span>  

<span data-ttu-id="cb732-130">如果你希望从前端 JavaScript 代码查看日志或快速运行某些脚本，请在 Windows/Linux 或 macOS 上选择以在 `Ctrl` + `Shift` + `J` `Command` + `Option` + `J` DevTools\*\*\*\* 中启动控制台面板。</span><span class="sxs-lookup"><span data-stu-id="cb732-130">If you want to see logs from your front-end JavaScript code or quickly run some script, select `Ctrl`+`Shift`+`J` on Windows/Linux or `Command`+`Option`+`J` on macOS to launch the **Console** panel in the DevTools.</span></span>  

## <span data-ttu-id="cb732-131">核心工具</span><span class="sxs-lookup"><span data-stu-id="cb732-131">Core tools</span></span>  

:::image type="complex" source="./media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools 核心工具" lightbox="./media/devtools-core-tools.png":::
   <span data-ttu-id="cb732-133">Microsoft Edge (Chromium) DevTools 核心工具</span><span class="sxs-lookup"><span data-stu-id="cb732-133">Microsoft Edge (Chromium) DevTools core tools</span></span>  
:::image-end::: 

<span data-ttu-id="cb732-134">Microsoft Edge \ (Chromium\) DevTools 包括以下面板。</span><span class="sxs-lookup"><span data-stu-id="cb732-134">The Microsoft Edge \(Chromium\) DevTools include the following panels.</span></span>  

*   <span data-ttu-id="cb732-135">“**元素**”面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 变化断点</span><span class="sxs-lookup"><span data-stu-id="cb732-135">An **Elements** panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="cb732-136">**控制台**，用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点，并在所选窗口或框架的上下文中运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="cb732-136">A **Console** to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="cb732-137">一 **个** 源面板，用于打开和实时编辑代码、设置断点、逐步执行代码，并一次查看一行 JavaScript 的网站状态</span><span class="sxs-lookup"><span data-stu-id="cb732-137">A **Sources** panel to open and live edit your code, set breakpoints, step through code, and see the state of your website one line of JavaScript at a time</span></span>  
*   <span data-ttu-id="cb732-138">“**网络**”面板，用于从网络和浏览器缓存监视和检查请求和响应</span><span class="sxs-lookup"><span data-stu-id="cb732-138">A **Network** panel to monitor and inspect requests and responses from the network and browser cache</span></span>   
*   <span data-ttu-id="cb732-139">“**性能**”面板，用于分析网站所需的时间和系统资源</span><span class="sxs-lookup"><span data-stu-id="cb732-139">A **Performance** panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="cb732-140">“**内存**”面板，用于衡量内存资源的使用情况，并比较代码运行时的不同状态下的堆快照</span><span class="sxs-lookup"><span data-stu-id="cb732-140">A **Memory** panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="cb732-141">检查 **、** 修改和调试 Web 应用清单、服务工作者和服务工作者缓存的应用程序面板。</span><span class="sxs-lookup"><span data-stu-id="cb732-141">An **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  <span data-ttu-id="cb732-142">您还可以检查和管理应用程序面板中的存储、 **数据库和缓存** 。</span><span class="sxs-lookup"><span data-stu-id="cb732-142">You may also inspect and manage storage, databases, and caches from the **Application** panel.</span></span>  
*   <span data-ttu-id="cb732-143">**安全**面板，可调试安全问题并确保已在网站上正确实现 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="cb732-143">A **Security** panel to debug security issues and ensure that you have properly implemented HTTPS on your website.</span></span>  <span data-ttu-id="cb732-144">HTTPS 为您的网站和用户提供您网站上的个人信息提供了关键的安全性和数据完整性。</span><span class="sxs-lookup"><span data-stu-id="cb732-144">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span></span>  
*   <span data-ttu-id="cb732-145">审核 **面板** \ (现在重命名为 **Lighthouse**\) 以运行网站的审核。</span><span class="sxs-lookup"><span data-stu-id="cb732-145">An **Audits** panel \(now renamed **Lighthouse**\) to run an audit of your website.</span></span>  <span data-ttu-id="cb732-146">审核结果有助于通过以下方式提高网站质量。</span><span class="sxs-lookup"><span data-stu-id="cb732-146">The results of the audit help you improve the quality of your site in the following ways.</span></span>  
    *   <span data-ttu-id="cb732-147">捕获与使您的网站可访问性、安全性、性能高等相关的常见错误。</span><span class="sxs-lookup"><span data-stu-id="cb732-147">Catch common errors related to making your website accessible, secure, performant, and so on.</span></span>  
    *   <span data-ttu-id="cb732-148">修复每个错误。</span><span class="sxs-lookup"><span data-stu-id="cb732-148">Fix each error.</span></span>  
    *   <span data-ttu-id="cb732-149">生成 PWA。</span><span class="sxs-lookup"><span data-stu-id="cb732-149">Build a PWA.</span></span>  
        
[!INCLUDE [audits-panel-note](./includes/audits-panel-note.md)]  

<span data-ttu-id="cb732-150">请发送 [反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="cb732-150">Please send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <span data-ttu-id="cb732-151">Extensions</span><span class="sxs-lookup"><span data-stu-id="cb732-151">Extensions</span></span>  

<span data-ttu-id="cb732-152">你可能已使用 DevTools 扩展来帮助你在构建网站或应用时诊断和调试问题。</span><span class="sxs-lookup"><span data-stu-id="cb732-152">You may have used extensions to the DevTools to help you diagnose and debug issues when building your websites or apps.</span></span>  <span data-ttu-id="cb732-153">你可以从 Microsoft Edge 加载项页面获取 [Microsoft Edge 的][MicrosoftEdgeAddonsExtensions] 扩展。</span><span class="sxs-lookup"><span data-stu-id="cb732-153">You may acquire extensions for Microsoft Edge from the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page.</span></span>  <span data-ttu-id="cb732-154">从[Microsoft Edge 加载项][MicrosoftEdgeAddonsExtensions]页面，你可以从开发人员工具类别浏览 DevTools\*\*\*\* 扩展或搜索特定扩展。</span><span class="sxs-lookup"><span data-stu-id="cb732-154">From the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page, you may browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span></span>  

<span data-ttu-id="cb732-155">还可以从 [Chrome Web 应用商店添加扩展][GoogleChromeWebstoreExtensions]。</span><span class="sxs-lookup"><span data-stu-id="cb732-155">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span></span>  

:::image type="complex" source="./media/allow-extensions-from-stores.png" alt-text="Microsoft Edge 中的 Chrome Web Store" lightbox="./media/allow-extensions-from-stores.png":::
   <span data-ttu-id="cb732-157">Microsoft Edge 中的 Chrome Web Store</span><span class="sxs-lookup"><span data-stu-id="cb732-157">Chrome Web Store in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="cb732-158">在顶部，选择"允许来自其他存储的扩展 **"，** 然后在出现的\*\*\*\* 对话框中选择"允许"。</span><span class="sxs-lookup"><span data-stu-id="cb732-158">At the top, choose **Allow extensions from other stores** and then choose **Allow** in the dialog that appears.</span></span>  

> [!NOTE]
> <span data-ttu-id="cb732-159">从 Microsoft Store 外的其他源安装的扩展未经验证，可能会影响浏览器性能。</span><span class="sxs-lookup"><span data-stu-id="cb732-159">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span></span>  

<span data-ttu-id="cb732-160">选择 **"添加到 Chrome"** 以将 DevTools 扩展添加到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="cb732-160">Choose **Add to Chrome** to add your DevTools extension to Microsoft Edge.</span></span>  

:::image type="complex" source="./media/install-extension-from-chrome-store.png" alt-text="将扩展从 Chrome Web Store 添加到 Microsoft Edge" lightbox="./media/install-extension-from-chrome-store.png":::
   <span data-ttu-id="cb732-162">将扩展从 Chrome Web Store 添加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cb732-162">Adding extension from Chrome Web Store to Microsoft Edge</span></span>  
:::image-end:::  

## <span data-ttu-id="cb732-163">快捷方式</span><span class="sxs-lookup"><span data-stu-id="cb732-163">Shortcuts</span></span>  

<span data-ttu-id="cb732-164">这些快捷方式控制主 DevTools 窗口、跨所有工具或同时使用这两种工具。</span><span class="sxs-lookup"><span data-stu-id="cb732-164">These shortcuts control the main DevTools window, work across all tools, or both.</span></span>  

| <span data-ttu-id="cb732-165">操作</span><span class="sxs-lookup"><span data-stu-id="cb732-165">Action</span></span> | <span data-ttu-id="cb732-166">Windows/Linux</span><span class="sxs-lookup"><span data-stu-id="cb732-166">Windows/Linux</span></span> | <span data-ttu-id="cb732-167">macOS</span><span class="sxs-lookup"><span data-stu-id="cb732-167">macOS</span></span> |  
|:--- |:--- | :--- |  
| <span data-ttu-id="cb732-168">显示/隐藏 DevTools\（打开至上次查看的面板\）</span><span class="sxs-lookup"><span data-stu-id="cb732-168">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12` <span data-ttu-id="cb732-169">或 `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="cb732-169">or `Ctrl`+`Shift`+</span></span>`I` | `Command`+`Option`+`I` |  
| <span data-ttu-id="cb732-170">显示控制台面板</span><span class="sxs-lookup"><span data-stu-id="cb732-170">Show the Console panel</span></span> | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| <span data-ttu-id="cb732-171">在"检查元素模式"中\*\*\*\* 显示 DevTools，该模式允许你选择网站上的元素，并查看"元素"面板中的 HTML**和**CSS</span><span class="sxs-lookup"><span data-stu-id="cb732-171">Show the DevTools in **Inspect Element Mode** which lets you choose an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| <span data-ttu-id="cb732-172">显示设置</span><span class="sxs-lookup"><span data-stu-id="cb732-172">Show Settings</span></span> | `?` <span data-ttu-id="cb732-173">或 `Fn`+</span><span class="sxs-lookup"><span data-stu-id="cb732-173">or `Fn`+</span></span>`F1` | `?` <span data-ttu-id="cb732-174">或 `Fn`+</span><span class="sxs-lookup"><span data-stu-id="cb732-174">or `Fn`+</span></span>`F1` |  
| <span data-ttu-id="cb732-175">显示下一个面板</span><span class="sxs-lookup"><span data-stu-id="cb732-175">Show the next panel</span></span> | `Ctrl`+`]` | `Command`+`]` |  
| <span data-ttu-id="cb732-176">显示上一个面板</span><span class="sxs-lookup"><span data-stu-id="cb732-176">Show the previous panel</span></span> | `Ctrl`+`[` | `Command`+`[` |  
| <span data-ttu-id="cb732-177">将 DevTools 停靠在上次使用的位置。</span><span class="sxs-lookup"><span data-stu-id="cb732-177">Dock the DevTools in the last position used.</span></span>  <span data-ttu-id="cb732-178">如果 DevTools 在整个会话的默认位置保留，快捷方式将 DevTools 撤消到单独的窗口中</span><span class="sxs-lookup"><span data-stu-id="cb732-178">If the DevTools remain in the default position for the entire session, the shortcut undocks the DevTools into a separate window</span></span> | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| <span data-ttu-id="cb732-179">切换 **设备模式**</span><span class="sxs-lookup"><span data-stu-id="cb732-179">Toggle **Device Mode**</span></span> | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| <span data-ttu-id="cb732-180">切换 **检查元素模式** ，该模式允许你选择网站上的元素，并查看"元素" **面板中的** HTML 和 CSS</span><span class="sxs-lookup"><span data-stu-id="cb732-180">Toggle **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| <span data-ttu-id="cb732-181">显示命令菜单</span><span class="sxs-lookup"><span data-stu-id="cb732-181">Show the Command Menu</span></span> | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| <span data-ttu-id="cb732-182">显示/隐藏箱</span><span class="sxs-lookup"><span data-stu-id="cb732-182">Show/Hide the Drawer</span></span> | `Esc` | `Esc` |  
| <span data-ttu-id="cb732-183">刷新。</span><span class="sxs-lookup"><span data-stu-id="cb732-183">Refresh.</span></span>  <span data-ttu-id="cb732-184">使用缓存对页面进行重新设置。</span><span class="sxs-lookup"><span data-stu-id="cb732-184">Fefreshes the page using the cache.</span></span>  | `F5` <span data-ttu-id="cb732-185">或 `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="cb732-185">or `Ctrl`+</span></span>`R` | `Command`+`R` |  
| <span data-ttu-id="cb732-186">硬刷新。</span><span class="sxs-lookup"><span data-stu-id="cb732-186">Hard Refresh.</span></span>  <span data-ttu-id="cb732-187">强制 Microsoft Edge 再次下载资源并重新加载。</span><span class="sxs-lookup"><span data-stu-id="cb732-187">Forces Microsoft Edge to download resources again and reload.</span></span>  <span data-ttu-id="cb732-188">使用的资源可能来自缓存版本</span><span class="sxs-lookup"><span data-stu-id="cb732-188">It is possible that the used resources may come from a cached version</span></span> | `Ctrl`<span data-ttu-id="cb732-189">+`F5` 或 `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="cb732-189">+`F5` or `Ctrl`+`Shift`+</span></span>`R` | `Command`+`Shift`+`R` |  
| <span data-ttu-id="cb732-190">搜索当前面板中的文本。</span><span class="sxs-lookup"><span data-stu-id="cb732-190">Search for text within the current panel.</span></span>  <span data-ttu-id="cb732-191">在审核、应用程序和安全面板中不受支持</span><span class="sxs-lookup"><span data-stu-id="cb732-191">Not supported in the Audits, Application, and Security panels</span></span> | `Ctrl`+`F` | `Command`+`F` |  
| <span data-ttu-id="cb732-192">在"箱"中显示"搜索"面板，可让你跨所有加载的资源搜索文本</span><span class="sxs-lookup"><span data-stu-id="cb732-192">Show the Search panel in the Drawer, which lets you search for text across all loaded resources</span></span> | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| <span data-ttu-id="cb732-193">在"源"面板中打开文件</span><span class="sxs-lookup"><span data-stu-id="cb732-193">Open a file in the Sources panel</span></span> | `Ctrl`<span data-ttu-id="cb732-194">+`O` 或 `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="cb732-194">+`O` or `Ctrl`+</span></span>`P` | `Command`<span data-ttu-id="cb732-195">+`O` 或 `Command`+</span><span class="sxs-lookup"><span data-stu-id="cb732-195">+`O` or `Command`+</span></span>`P` |  
| <span data-ttu-id="cb732-196">放大</span><span class="sxs-lookup"><span data-stu-id="cb732-196">Zoom in</span></span> | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| <span data-ttu-id="cb732-197">缩小</span><span class="sxs-lookup"><span data-stu-id="cb732-197">Zoom out</span></span> | `Ctrl`+`-` | `Command`+`-` |  
| <span data-ttu-id="cb732-198">还原默认缩放级别</span><span class="sxs-lookup"><span data-stu-id="cb732-198">Restore default zoom level</span></span> | `Ctrl`+`0` | `Command`+`0` |  
| <span data-ttu-id="cb732-199">运行代码段</span><span class="sxs-lookup"><span data-stu-id="cb732-199">Run snippet</span></span> | `Ctrl`<span data-ttu-id="cb732-200">+`O``Ctrl` + `P` 或 ， `!` 键入后跟脚本的名称，然后按</span><span class="sxs-lookup"><span data-stu-id="cb732-200">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` | <span data-ttu-id="cb732-201">按 `Command` + `O` or `Command` + `P` ， `!` 键入后跟脚本的名称，然后按</span><span class="sxs-lookup"><span data-stu-id="cb732-201">Press `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` |  
| <span data-ttu-id="cb732-202">在新建选项卡中显示不可编辑的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="cb732-202">Show non-editable HTML source code in a new tab</span></span> | `Ctrl`+`U` | <span data-ttu-id="cb732-203">不适用</span><span class="sxs-lookup"><span data-stu-id="cb732-203">N/A</span></span> |  

> [!NOTE]
> <span data-ttu-id="cb732-204">如果你正在调试并暂停在断点，则 **刷新** 快捷方式将首先恢复运行时。</span><span class="sxs-lookup"><span data-stu-id="cb732-204">If you are debugging and paused at a breakpoint, the **Refresh** shortcut resumes the runtime first.</span></span>  

## <span data-ttu-id="cb732-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb732-205">See also</span></span>  

*   [<span data-ttu-id="cb732-206">适用于初学者的 DevTools：HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="cb732-206">DevTools for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideChromiumBeginnersHtml]  
*   [<span data-ttu-id="cb732-207">Microsoft Edge (Chromium) DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="cb732-207">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolChromiumIndex]  
    
## <span data-ttu-id="cb732-208">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="cb732-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<span data-ttu-id="cb732-209">如果你想要预览即将进入 [DevTools][DevtoolsGuideChromiumWhatsNewIndex]的最新功能，请下载 [Microsoft Edge Canary，该 Canary][MicrosoftedgeinsiderDownload]是夜间构建的。</span><span class="sxs-lookup"><span data-stu-id="cb732-209">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "适用于初学者的 DevTools：HTML 和 DOM 入门 |Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/11/devtools "Microsoft Edge (DevTools) 的新增功能 |Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools 协议 |Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展 |Chrome Web Store"  
