---
description: 了解 Microsoft Edge (Chromium) 开发人员工具
title: Microsoft Edge (Chromium) 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: c1168e25c99302a9d195c756c6049881b5dfe91f
ms.sourcegitcommit: 2fa65cca74c5214601900579c0ce9f946ad8a27e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10991182"
---
# <span data-ttu-id="c32c3-104">Microsoft Edge (Chromium) 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="c32c3-104">Microsoft Edge (Chromium) Developer Tools</span></span>  

<span data-ttu-id="c32c3-105">Microsoft Edge 采用了 Chromium open 源项目以创建更好的 web 兼容性，并减少不同基础 web 平台的碎片。</span><span class="sxs-lookup"><span data-stu-id="c32c3-105">Microsoft Edge has adopted the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms.</span></span>  <span data-ttu-id="c32c3-106">此更改使你能够更轻松地在 Microsoft Edge 中构建和测试你的网站，并确保每个网站在不同的基于 Chromium 的浏览器 (（如 Google Chrome、Vivaldi、Opera 或 Brave \ ) ）中都可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="c32c3-106">This change should make it easier for you to build and test your websites in Microsoft Edge and ensure that each works as expected even while viewed in a different Chromium-based browser \(such as Google Chrome, Vivaldi, Opera, or Brave\).</span></span>  

<span data-ttu-id="c32c3-107">随着网络在不断扩大的各种设备类型数组中的使用日益增加，测试网站所涉及的复杂性和开销也随之增加。</span><span class="sxs-lookup"><span data-stu-id="c32c3-107">As the web has grown in usage across an ever-widening array of device types, the complexity and overhead involved in testing websites has exploded.</span></span> <span data-ttu-id="c32c3-108">由于 web 开发人员在小型公司 (尤其是在小型公司 ) 必须针对如此多的不同系统进行测试，因此你可能会发现几乎无法确保网站在所有设备类型和所有浏览器上都能正常工作。</span><span class="sxs-lookup"><span data-stu-id="c32c3-108">Since web developers \(particularly those at small companies\) must test against so many different systems, you may find it nearly impossible to ensure that sites work well on all device types and all browsers.</span></span>  <span data-ttu-id="c32c3-109">既然 Microsoft Edge 基于 Chromium，Microsoft Edge 团队通过将 Microsoft Edge web 平台与其他基于 Chromium 的浏览器相协调，并在浏览器内以及你 (每天使用的其他开发人员工具（如 Visual Studio Code \ ) ）中提供了最佳的开发工具体验。</span><span class="sxs-lookup"><span data-stu-id="c32c3-109">Now that Microsoft Edge is based on Chromium, the Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers and provided a best-in-class developer tooling experience, both inside the browser and with the other developer tools you use every day \(such as Visual Studio Code\).</span></span>  

<span data-ttu-id="c32c3-110">如果您要签出 Microsoft Edge，并且主要是在基于 Chromium 的浏览器中开发，则应立即体验。</span><span class="sxs-lookup"><span data-stu-id="c32c3-110">If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.</span></span>  <span data-ttu-id="c32c3-111">Microsoft Edge \ (Chromium \ ) 开发人员工具的工作方式与你已了解和使用的开发人员工具相同。</span><span class="sxs-lookup"><span data-stu-id="c32c3-111">The Microsoft Edge \(Chromium\) Developer Tools function in the same way as the developer tools you already know and use.</span></span>  <span data-ttu-id="c32c3-112">有关详细信息，请参阅 [Microsoft Edge (Chromium) DevTools 中的新增功能][DevtoolsGuideChromiumWhatsNewIndex]。</span><span class="sxs-lookup"><span data-stu-id="c32c3-112">For more information, see [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   <span data-ttu-id="c32c3-114">Microsoft Edge (Chromium) DevTools</span><span class="sxs-lookup"><span data-stu-id="c32c3-114">Microsoft Edge (Chromium) DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="c32c3-115">如果您要签出下一版本的 Microsoft Edge，并且以前是在 Microsoft Edge \ (EdgeHTML \ ) 中开发的，现在您有了一些非常好的新工具，可让您在 Microsoft Edge 中更轻松、更快地构建和测试您的网站！</span><span class="sxs-lookup"><span data-stu-id="c32c3-115">If you are checking out the next version of Microsoft Edge and you previously developed in Microsoft Edge \(EdgeHTML\), you now have some great new tools that should make it easier and faster to build and test your websites in Microsoft Edge!</span></span>  

## <span data-ttu-id="c32c3-116">打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="c32c3-116">Open the DevTools</span></span>  

<span data-ttu-id="c32c3-117">如果您以前从未使用过 DevTools，则 Microsoft Edge 开发人员工具是一组直接内置于 Microsoft Edge 浏览器中的工具。</span><span class="sxs-lookup"><span data-stu-id="c32c3-117">If you have never used the DevTools before, the Microsoft Edge Developer Tools are a set of tools built directly into the Microsoft Edge browser.</span></span>  <span data-ttu-id="c32c3-118">通过这些 DevTools，你可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="c32c3-118">With these DevTools, you are able to do the following.</span></span>  

*   <span data-ttu-id="c32c3-119">检查并对 HTML 网站进行更改</span><span class="sxs-lookup"><span data-stu-id="c32c3-119">Inspect and make changes to your HTML website</span></span>  
*   <span data-ttu-id="c32c3-120">编辑 CSS 并立即查看预览您的网站呈现方式</span><span class="sxs-lookup"><span data-stu-id="c32c3-120">Edit CSS and instantly see preview how your website renders</span></span>  
*   <span data-ttu-id="c32c3-121">查看 `console.log()` 前端 JavaScript 代码中的所有语句</span><span class="sxs-lookup"><span data-stu-id="c32c3-121">See all the `console.log()` statements from your front-end JavaScript code</span></span>  
*   <span data-ttu-id="c32c3-122">通过设置断点并逐行逐行执行调试来调试你的脚本</span><span class="sxs-lookup"><span data-stu-id="c32c3-122">Debug your script by setting breakpoints and stepping through it line by line</span></span>  

<span data-ttu-id="c32c3-123">直接在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="c32c3-123">all directly within the browser.</span></span>  <span data-ttu-id="c32c3-124">以下是 DevTools 提供的一些功能的示例，可使你在 Microsoft Edge 中构建和测试网站变得更加轻松快捷。</span><span class="sxs-lookup"><span data-stu-id="c32c3-124">These are just examples of some of the features the DevTools provide to make it easier and faster for you to build and test your websites in Microsoft Edge.</span></span>  

<span data-ttu-id="c32c3-125">打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="c32c3-125">To open the DevTools</span></span>  

*   <span data-ttu-id="c32c3-126">按</span><span class="sxs-lookup"><span data-stu-id="c32c3-126">press</span></span> `F12` 
*   <span data-ttu-id="c32c3-127">按 `Ctrl` + `Shift` + `I` `Command` + `Option` + `I` macOS \ ) 上的 "Windows \ ("</span><span class="sxs-lookup"><span data-stu-id="c32c3-127">press `Ctrl`+`Shift`+`I` on Windows \(`Command`+`Option`+`I` on macOS\)</span></span>  

<span data-ttu-id="c32c3-128">如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择 " **检查** " 以跳转到 "元素" 面板。</span><span class="sxs-lookup"><span data-stu-id="c32c3-128">If you want to see the HTML or CSS for an element on your site, right-click the element and select **Inspect** to jump into the Elements panel.</span></span>  <span data-ttu-id="c32c3-129">你还可以按 `Ctrl` + `Shift` + `C` `Command` + `Option` + `C` macOS \ ) 上的 Windows \ (在 "**检查元素" 模式**下打开 DevTools，以便你在网站上选择元素并在 "**元素**" 面板中查看 HTML 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="c32c3-129">You may also press `Ctrl`+`Shift`+`C` on Windows \(`Command`+`Option`+`C` on macOS\) to open the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel.</span></span>  

<span data-ttu-id="c32c3-130">如果您想要查看前端 JavaScript 代码中的日志或快速运行某些脚本，请按 `Ctrl` + `Shift` + `J` Windows 或 `Command` + `Option` + `J` macOS 以启动 DevTools 中的控制台面板。</span><span class="sxs-lookup"><span data-stu-id="c32c3-130">If you want to see logs from your front-end JavaScript code or quickly run some script, press `Ctrl`+`Shift`+`J` on Windows or `Command`+`Option`+`J` on macOS to launch the Console panel in the DevTools.</span></span>  

## <span data-ttu-id="c32c3-131">核心工具</span><span class="sxs-lookup"><span data-stu-id="c32c3-131">Core tools</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools 核心工具":::
   <span data-ttu-id="c32c3-133">Microsoft Edge (Chromium) DevTools 核心工具</span><span class="sxs-lookup"><span data-stu-id="c32c3-133">Microsoft Edge (Chromium) DevTools core tools</span></span>  
:::image-end::: 

<span data-ttu-id="c32c3-134">Microsoft Edge \ (Chromium \ ) DevTools 包括以下面板。</span><span class="sxs-lookup"><span data-stu-id="c32c3-134">The Microsoft Edge \(Chromium\) DevTools include the following panels.</span></span>  

*   <span data-ttu-id="c32c3-135">“**元素**”面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 变化断点</span><span class="sxs-lookup"><span data-stu-id="c32c3-135">An **Elements** panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="c32c3-136">**控制台**，用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点，并在所选窗口或框架的上下文中运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="c32c3-136">A **Console** to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="c32c3-137">一个 " **源** " 面板，用于打开和实时编辑代码、设置断点、单步执行代码以及查看网站的状态一次 JavaScript 的每一行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="c32c3-137">A **Sources** panel to open and live edit your code, set breakpoints, step through code, and see the state of your website one line of JavaScript at a time</span></span>  
*   <span data-ttu-id="c32c3-138">“**网络**”面板，用于从网络和浏览器缓存监视和检查请求和响应</span><span class="sxs-lookup"><span data-stu-id="c32c3-138">A **Network** panel to monitor and inspect requests and responses from the network and browser cache</span></span>   
*   <span data-ttu-id="c32c3-139">“**性能**”面板，用于分析网站所需的时间和系统资源</span><span class="sxs-lookup"><span data-stu-id="c32c3-139">A **Performance** panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="c32c3-140">“**内存**”面板，用于衡量内存资源的使用情况，并比较代码运行时的不同状态下的堆快照</span><span class="sxs-lookup"><span data-stu-id="c32c3-140">A **Memory** panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="c32c3-141">用于检查、修改和调试 web 应用清单、服务工作人员和服务工作人员缓存的 **应用程序** 面板。</span><span class="sxs-lookup"><span data-stu-id="c32c3-141">An **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  <span data-ttu-id="c32c3-142">您也可以从 " **应用程序** " 面板中检查和管理存储、数据库和缓存。</span><span class="sxs-lookup"><span data-stu-id="c32c3-142">You may also inspect and manage storage, databases, and caches from the **Application** panel.</span></span>  
*   <span data-ttu-id="c32c3-143">用于调试安全问题的 **安全** 面板，并确保你在网站上正确实现了 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="c32c3-143">A **Security** panel to debug security issues and ensure that you have properly implemented HTTPS on your website.</span></span>  <span data-ttu-id="c32c3-144">HTTPS 为您的网站和用户提供网站上提供个人信息的重要安全和数据完整性。</span><span class="sxs-lookup"><span data-stu-id="c32c3-144">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span></span>  
*   <span data-ttu-id="c32c3-145">**审核**面板 \ (现在重命名**Lighthouse**\ ) 以运行网站审核。</span><span class="sxs-lookup"><span data-stu-id="c32c3-145">An **Audits** panel \(now renamed **Lighthouse**\) to run an audit of your website.</span></span>  <span data-ttu-id="c32c3-146">审核结果可帮助你通过以下方式改善网站的质量。</span><span class="sxs-lookup"><span data-stu-id="c32c3-146">The results of the audit help you improve the quality of your site in the following ways.</span></span>  
    *   <span data-ttu-id="c32c3-147">捕获与使网站易于访问、安全、性能等相关的常见错误。</span><span class="sxs-lookup"><span data-stu-id="c32c3-147">Catch common errors related to making your website accessible, secure, performant, and so on.</span></span>  
    *   <span data-ttu-id="c32c3-148">修复每个错误。</span><span class="sxs-lookup"><span data-stu-id="c32c3-148">Fix each error.</span></span>  
    *   <span data-ttu-id="c32c3-149">构建 PWA。</span><span class="sxs-lookup"><span data-stu-id="c32c3-149">Build a PWA.</span></span>  

[!INCLUDE [audits-panel-note](./devtools-guide-chromium/includes/audits-panel-note.md)]  

<span data-ttu-id="c32c3-150">请发送您的 [反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="c32c3-150">Please send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <span data-ttu-id="c32c3-151">Extensions</span><span class="sxs-lookup"><span data-stu-id="c32c3-151">Extensions</span></span>  

<span data-ttu-id="c32c3-152">你可能已使用 DevTools 的扩展，可帮助你在构建网站或应用时诊断和调试问题。</span><span class="sxs-lookup"><span data-stu-id="c32c3-152">You may have used extensions to the DevTools to help you diagnose and debug issues when building your websites or apps.</span></span>  <span data-ttu-id="c32c3-153">你可以从 [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] 页面获取 microsoft edge 的扩展。</span><span class="sxs-lookup"><span data-stu-id="c32c3-153">You may acquire extensions for Microsoft Edge from the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page.</span></span>  <span data-ttu-id="c32c3-154">从 " [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] " 页面中，您可以从 " **开发工具** " 类别中浏览 DevTools 扩展或搜索特定的扩展名。</span><span class="sxs-lookup"><span data-stu-id="c32c3-154">From the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page, you may browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span></span>  

<span data-ttu-id="c32c3-155">您也可以添加 [Chrome Web 应用商店][GoogleChromeWebstoreExtensions]的扩展。</span><span class="sxs-lookup"><span data-stu-id="c32c3-155">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge 中的 Chrome Web Store":::
   <span data-ttu-id="c32c3-157">Microsoft Edge 中的 Chrome Web Store</span><span class="sxs-lookup"><span data-stu-id="c32c3-157">Chrome Web Store in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="c32c3-158">在顶部，选择 " **允许其他存储中的扩展** "，然后在出现的对话框中选择 " **允许** "。</span><span class="sxs-lookup"><span data-stu-id="c32c3-158">At the top, select **Allow extensions from other stores** and then select **Allow** in the dialog that appears.</span></span>  

> [!NOTE]
> <span data-ttu-id="c32c3-159">从 Microsoft Store 以外的源安装的扩展未验证，可能会影响浏览器性能。</span><span class="sxs-lookup"><span data-stu-id="c32c3-159">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span></span>  

<span data-ttu-id="c32c3-160">选择 " **添加到 Chrome** " 以将你的 DevTools 扩展添加到 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="c32c3-160">Select **Add to Chrome** to add your DevTools extension to Microsoft Edge!</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="将 Chrome Web Store 中的扩展添加到 Microsoft Edge":::
   <span data-ttu-id="c32c3-162">将 Chrome Web Store 中的扩展添加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c32c3-162">Adding extension from Chrome Web Store to Microsoft Edge</span></span>  
:::image-end:::  

## <span data-ttu-id="c32c3-163">指向</span><span class="sxs-lookup"><span data-stu-id="c32c3-163">Shortcuts</span></span>  

<span data-ttu-id="c32c3-164">这些快捷方式控制主 DevTools 窗口，可在所有工具上工作，也可以同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="c32c3-164">These shortcuts control the main DevTools window, work across all tools, or both.</span></span>  

| <span data-ttu-id="c32c3-165">操作</span><span class="sxs-lookup"><span data-stu-id="c32c3-165">Action</span></span> | <span data-ttu-id="c32c3-166">Windows</span><span class="sxs-lookup"><span data-stu-id="c32c3-166">Windows</span></span> | <span data-ttu-id="c32c3-167">macOS</span><span class="sxs-lookup"><span data-stu-id="c32c3-167">macOS</span></span> |  
|:--- |:--- | :--- |  
| <span data-ttu-id="c32c3-168">显示/隐藏 DevTools\（打开至上次查看的面板\）</span><span class="sxs-lookup"><span data-stu-id="c32c3-168">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12` <span data-ttu-id="c32c3-169">或 `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="c32c3-169">or `Ctrl`+`Shift`+</span></span>`I` | `Command`+`Option`+`I` |  
| <span data-ttu-id="c32c3-170">显示控制台面板</span><span class="sxs-lookup"><span data-stu-id="c32c3-170">Show the Console panel</span></span> | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| <span data-ttu-id="c32c3-171">在 " **检查元素" 模式下** 显示 DevTools，使你可以在网站上选择元素并在 " **元素** " 面板中查看 HTML 和 CSS</span><span class="sxs-lookup"><span data-stu-id="c32c3-171">Show the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| <span data-ttu-id="c32c3-172">显示设置</span><span class="sxs-lookup"><span data-stu-id="c32c3-172">Show Settings</span></span> | `?` <span data-ttu-id="c32c3-173">或 `Fn`+</span><span class="sxs-lookup"><span data-stu-id="c32c3-173">or `Fn`+</span></span>`F1` | `?` <span data-ttu-id="c32c3-174">或 `Fn`+</span><span class="sxs-lookup"><span data-stu-id="c32c3-174">or `Fn`+</span></span>`F1` |  
| <span data-ttu-id="c32c3-175">显示下一个面板</span><span class="sxs-lookup"><span data-stu-id="c32c3-175">Show the next panel</span></span> | `Ctrl`+`]` | `Command`+`]` |  
| <span data-ttu-id="c32c3-176">显示上一个面板</span><span class="sxs-lookup"><span data-stu-id="c32c3-176">Show the previous panel</span></span> | `Ctrl`+`[` | `Command`+`[` |  
| <span data-ttu-id="c32c3-177">将 DevTools 固定在最后一个所用位置。</span><span class="sxs-lookup"><span data-stu-id="c32c3-177">Dock the DevTools in the last position used.</span></span>  <span data-ttu-id="c32c3-178">如果 DevTools 保留在整个会话的默认位置，此快捷方式会将 DevTools 取消停靠到一个单独的窗口中</span><span class="sxs-lookup"><span data-stu-id="c32c3-178">If the DevTools remain in the default position for the entire session, this shortcut undocks the DevTools into a separate window</span></span> | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| <span data-ttu-id="c32c3-179">切换 **设备模式**</span><span class="sxs-lookup"><span data-stu-id="c32c3-179">Toggle **Device Mode**</span></span> | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| <span data-ttu-id="c32c3-180">切换 " **检查元素" 模式** ，使您可以选择网站上的元素并在 " **元素** " 面板中查看 HTML 和 CSS</span><span class="sxs-lookup"><span data-stu-id="c32c3-180">Toggle **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| <span data-ttu-id="c32c3-181">显示命令菜单</span><span class="sxs-lookup"><span data-stu-id="c32c3-181">Show the Command Menu</span></span> | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| <span data-ttu-id="c32c3-182">显示/隐藏抽屉</span><span class="sxs-lookup"><span data-stu-id="c32c3-182">Show/Hide the Drawer</span></span> | `Esc` | `Esc` |  
| <span data-ttu-id="c32c3-183">恢复.</span><span class="sxs-lookup"><span data-stu-id="c32c3-183">Refresh.</span></span>  <span data-ttu-id="c32c3-184">这将刷新使用缓存的页面。</span><span class="sxs-lookup"><span data-stu-id="c32c3-184">This refreshes the page using the cache.</span></span>  | `F5` <span data-ttu-id="c32c3-185">或 `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="c32c3-185">or `Ctrl`+</span></span>`R` | `Command`+`R` |  
| <span data-ttu-id="c32c3-186">硬刷新。</span><span class="sxs-lookup"><span data-stu-id="c32c3-186">Hard Refresh.</span></span>  <span data-ttu-id="c32c3-187">这会强制 Microsoft Edge 再次下载资源并重新加载。</span><span class="sxs-lookup"><span data-stu-id="c32c3-187">This forces Microsoft Edge to download resources again and reload.</span></span>  <span data-ttu-id="c32c3-188">已使用的资源可能来自缓存的版本</span><span class="sxs-lookup"><span data-stu-id="c32c3-188">It is possible that the used resources may come from a cached version</span></span> | `Ctrl`<span data-ttu-id="c32c3-189">+`F5` 或 `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="c32c3-189">+`F5` or `Ctrl`+`Shift`+</span></span>`R` | `Command`+`Shift`+`R` |  
| <span data-ttu-id="c32c3-190">在当前面板中搜索文本。</span><span class="sxs-lookup"><span data-stu-id="c32c3-190">Search for text within the current panel.</span></span>  <span data-ttu-id="c32c3-191">在 "审核"、"应用程序" 和 "安全" 面板中不受支持</span><span class="sxs-lookup"><span data-stu-id="c32c3-191">Not supported in the Audits, Application, and Security panels</span></span> | `Ctrl`+`F` | `Command`+`F` |  
| <span data-ttu-id="c32c3-192">在抽屉中显示 "搜索" 面板，用于在所有已加载的资源中搜索文本</span><span class="sxs-lookup"><span data-stu-id="c32c3-192">Show the Search panel in the Drawer, which lets you search for text across all loaded resources</span></span> | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| <span data-ttu-id="c32c3-193">在 "源" 面板中打开文件</span><span class="sxs-lookup"><span data-stu-id="c32c3-193">Open a file in the Sources panel</span></span> | `Ctrl`<span data-ttu-id="c32c3-194">+`O` 或 `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="c32c3-194">+`O` or `Ctrl`+</span></span>`P` | `Command`<span data-ttu-id="c32c3-195">+`O` 或 `Command`+</span><span class="sxs-lookup"><span data-stu-id="c32c3-195">+`O` or `Command`+</span></span>`P` |  
| <span data-ttu-id="c32c3-196">放大</span><span class="sxs-lookup"><span data-stu-id="c32c3-196">Zoom in</span></span> | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| <span data-ttu-id="c32c3-197">缩小</span><span class="sxs-lookup"><span data-stu-id="c32c3-197">Zoom out</span></span> | `Ctrl`+`-` | `Command`+`-` |  
| <span data-ttu-id="c32c3-198">还原默认缩放级别</span><span class="sxs-lookup"><span data-stu-id="c32c3-198">Restore default zoom level</span></span> | `Ctrl`+`0` | `Command`+`0` |  
| <span data-ttu-id="c32c3-199">运行代码段</span><span class="sxs-lookup"><span data-stu-id="c32c3-199">Run snippet</span></span> | `Ctrl`<span data-ttu-id="c32c3-200">+`O`或者 `Ctrl` + `P` ，键入 `!` 后跟脚本的名称，然后按</span><span class="sxs-lookup"><span data-stu-id="c32c3-200">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` | <span data-ttu-id="c32c3-201">按 `Command` + `O` 或 `Command` + `P` ，然后键入 `!` 脚本名称，然后按</span><span class="sxs-lookup"><span data-stu-id="c32c3-201">Press `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` |  
| <span data-ttu-id="c32c3-202">在新选项卡中显示不可编辑的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="c32c3-202">Show non-editable HTML source code in a new tab</span></span> | `Ctrl`+`U` | <span data-ttu-id="c32c3-203">不适用</span><span class="sxs-lookup"><span data-stu-id="c32c3-203">N/A</span></span> |  

> [!NOTE]
> <span data-ttu-id="c32c3-204">如果在断点处调试和暂停， **刷新** 快捷方式将首先恢复运行时。</span><span class="sxs-lookup"><span data-stu-id="c32c3-204">If you are debugging and paused at a breakpoint, the **Refresh** shortcut resumes the runtime first.</span></span>  

## <span data-ttu-id="c32c3-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c32c3-205">See also</span></span>  

*   [<span data-ttu-id="c32c3-206">初学者的 DevTools： HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="c32c3-206">DevTools for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideChromiumBeginnersHtml]  
*   [<span data-ttu-id="c32c3-207">Microsoft Edge (Chromium) DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="c32c3-207">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolChromiumIndex]  

## <span data-ttu-id="c32c3-208">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="c32c3-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<span data-ttu-id="c32c3-209">如果你想要预览 DevTools 中的 [最新功能][DevtoolsGuideChromiumWhatsNewIndex]，请下载 [Microsoft Edge][MicrosoftedgeinsiderDownload]未安装，它将在夜间生成。</span><span class="sxs-lookup"><span data-stu-id="c32c3-209">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初学者的 DevTools： HTML 和 DOM 入门 |Microsoft 文档"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools "Microsoft Edge 中的新增功能 (Chromium) DevTools |Microsoft 文档"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools 协议 |Microsoft 文档"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展名 |Chrome Web Store"  
