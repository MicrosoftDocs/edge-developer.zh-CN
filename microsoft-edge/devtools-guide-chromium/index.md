---
description: 了解 Microsoft Edge (Chromium) 开发人员工具
title: Microsoft Edge (Chromium) 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: fa407393f8ecb79a3382294742bf9061787ec04a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397699"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a><span data-ttu-id="e30bc-104">Microsoft Edge (Chromium) 开发人员工具概述</span><span class="sxs-lookup"><span data-stu-id="e30bc-104">Microsoft Edge (Chromium) Developer Tools overview</span></span>  

<span data-ttu-id="e30bc-105">Microsoft Edge 已采用 Chromium 开放源代码项目。</span><span class="sxs-lookup"><span data-stu-id="e30bc-105">Microsoft Edge has adopted the Chromium open-source project.</span></span>  <span data-ttu-id="e30bc-106">新的 Microsoft Edge 浏览器可提供更好的 Web 兼容性并减少不同 Web 平台的碎片。</span><span class="sxs-lookup"><span data-stu-id="e30bc-106">The new Microsoft Edge browser creates better web compatibility and reduces the fragmentation of different web platforms.</span></span>  <span data-ttu-id="e30bc-107">此更改应便于你在 Microsoft Edge 中生成和测试网页。</span><span class="sxs-lookup"><span data-stu-id="e30bc-107">The change should make it easier for you to build and test your webpages in Microsoft Edge.</span></span>  <span data-ttu-id="e30bc-108">新的 Microsoft Edge 应在其他基于 Chromium 的浏览器中打开时帮助网页按预期工作。</span><span class="sxs-lookup"><span data-stu-id="e30bc-108">The new Microsoft Edge should help your webpages work as expected when opened in other Chromium-based browsers.</span></span>  <span data-ttu-id="e30bc-109">基于 Chromium 的浏览器包括 Google Chrome、Vivaldi、Opera、Opera 和新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e30bc-109">Chromium-based browsers include Google Chrome, Vivaldi, Opera, Brave, and the new Microsoft Edge.</span></span>  

<span data-ttu-id="e30bc-110">在不断扩展的设备类型数组中，Web 的使用已增长。</span><span class="sxs-lookup"><span data-stu-id="e30bc-110">The web has grown in usage across an ever-widening array of device types.</span></span>  <span data-ttu-id="e30bc-111">测试网页所涉及的复杂性和开销迅速增加。</span><span class="sxs-lookup"><span data-stu-id="e30bc-111">The complexity and overhead involved in testing webpages has rapidly grown.</span></span>  <span data-ttu-id="e30bc-112">您需要针对许多不同的系统测试 Web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="e30bc-112">Web developers like you need to test against many different systems.</span></span>  <span data-ttu-id="e30bc-113">为了确保网页在所有设备类型和浏览器中正常工作，你可能会发现它几乎不可能，尤其是在你在一家小型公司工作时。</span><span class="sxs-lookup"><span data-stu-id="e30bc-113">To ensure your webpages work well on all device types and browsers, you may find it nearly impossible, particularly if you work at a small company.</span></span>  <span data-ttu-id="e30bc-114">新的 Microsoft Edge 现在基于 Chromium。</span><span class="sxs-lookup"><span data-stu-id="e30bc-114">The new Microsoft Edge is now based on Chromium.</span></span>  <span data-ttu-id="e30bc-115">Microsoft Edge 团队通过使 Microsoft Edge Web 平台与其他基于 Chromium 的浏览器保持一致来简化矩阵。</span><span class="sxs-lookup"><span data-stu-id="e30bc-115">The Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers.</span></span>  <span data-ttu-id="e30bc-116">新的 Microsoft Edge 提供了一流的开发体验。</span><span class="sxs-lookup"><span data-stu-id="e30bc-116">The new Microsoft Edge provides a best-in-class development experience.</span></span>  <span data-ttu-id="e30bc-117">体验是在浏览器内以及你日常使用的其他开发人员工具（如 Visual Studio 代码）中完成的。</span><span class="sxs-lookup"><span data-stu-id="e30bc-117">The experience is accomplished inside the browser and along with the other developer tools you use everyday, such as Visual Studio Code.</span></span>  

<span data-ttu-id="e30bc-118">作为基于 Chromium 的浏览器开发人员，你应该熟悉新的 Microsoft Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="e30bc-118">As a Chromium-based browser developer, you should feel comfortable with the new Microsoft Edge browser.</span></span>  <span data-ttu-id="e30bc-119">Microsoft Edge \ (Chromium\) DevTools 的正常工作，就像你已了解和使用开发人员工具一样。</span><span class="sxs-lookup"><span data-stu-id="e30bc-119">The Microsoft Edge \(Chromium\) DevTools work just like the developer tools you already know and use.</span></span>  <span data-ttu-id="e30bc-120">Microsoft Edge \ (Chromium\) 开发人员工具通常称为 Microsoft Edge \ (Chromium\) DevTools 或 DevTools。</span><span class="sxs-lookup"><span data-stu-id="e30bc-120">The Microsoft Edge \(Chromium\) Developer Tools are often called the Microsoft Edge \(Chromium\) DevTools or DevTools.</span></span>  <span data-ttu-id="e30bc-121">有关详细信息，请导航到 Microsoft Edge 中的新增功能[ (Chromium) DevTools。][DevtoolsGuideChromiumWhatsNewIndex]</span><span class="sxs-lookup"><span data-stu-id="e30bc-121">For more information, navigate to [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span></span>  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./media/devtools.png":::
   <span data-ttu-id="e30bc-123">Microsoft Edge (Chromium) DevTools</span><span class="sxs-lookup"><span data-stu-id="e30bc-123">Microsoft Edge (Chromium) DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="e30bc-124">如果你之前为 Microsoft Edge \ (EdgeHTML\) 开发，并且正在评估新的 Microsoft Edge，它现在将提供出色的新工具，便于你更轻松快速地生成和测试网页。</span><span class="sxs-lookup"><span data-stu-id="e30bc-124">If you previously developed for Microsoft Edge \(EdgeHTML\) and are evaluating the new Microsoft Edge, it now provides great new tools for you to build and test your webpages easier and faster.</span></span>  

## <a name="open-the-devtools"></a><span data-ttu-id="e30bc-125">打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="e30bc-125">Open the DevTools</span></span>  

<span data-ttu-id="e30bc-126">Microsoft Edge DevTools 是直接内置于 Microsoft Edge 浏览器的一组工具。</span><span class="sxs-lookup"><span data-stu-id="e30bc-126">The Microsoft Edge DevTools are a set of tools built directly into the Microsoft Edge browser.</span></span>  <span data-ttu-id="e30bc-127">DevTools 允许你直接在浏览器中执行以下所有任务。</span><span class="sxs-lookup"><span data-stu-id="e30bc-127">The DevTools allows you to do the following tasks all directly within the browser.</span></span>  

*   <span data-ttu-id="e30bc-128">检查 HTML 网页并进行更改</span><span class="sxs-lookup"><span data-stu-id="e30bc-128">Inspect and make changes to your HTML webpage</span></span>  
*   <span data-ttu-id="e30bc-129">编辑 CSS 并立即查看预览网页呈现的方式</span><span class="sxs-lookup"><span data-stu-id="e30bc-129">Edit CSS and instantly see preview how your webpage renders</span></span>  
*   <span data-ttu-id="e30bc-130">查看前端 `console.log()` JavaScript 代码的所有语句</span><span class="sxs-lookup"><span data-stu-id="e30bc-130">Review all of the `console.log()` statements from your front-end JavaScript code</span></span>  
*   <span data-ttu-id="e30bc-131">调试脚本、设置断点并逐行调试代码</span><span class="sxs-lookup"><span data-stu-id="e30bc-131">Debug your script, set breakpoints, and step through your code line by line</span></span>  
    
<span data-ttu-id="e30bc-132">DevTools 提供的更多功能示例，使你在 Microsoft Edge 中生成和测试网页更加轻松快捷。</span><span class="sxs-lookup"><span data-stu-id="e30bc-132">More examples of the features that DevTools provide to make it easier and faster for you to build and test your webpage in Microsoft Edge.</span></span>  

<span data-ttu-id="e30bc-133">打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="e30bc-133">To open the DevTools</span></span>  

*   <span data-ttu-id="e30bc-134">选择</span><span class="sxs-lookup"><span data-stu-id="e30bc-134">Select</span></span> `F12` 
*   <span data-ttu-id="e30bc-135">选择 `Ctrl` + `Shift` + `I` \ (Windows/Linux\) `Command` + `Option` + `I` 或 \ (macOS\) </span><span class="sxs-lookup"><span data-stu-id="e30bc-135">Select `Ctrl`+`Shift`+`I` \(Windows/Linux\) or `Command`+`Option`+`I` \(macOS\)</span></span>  
    
<span data-ttu-id="e30bc-136">如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择"检查\*\*\*\*"以跳转到 **"元素**"工具。</span><span class="sxs-lookup"><span data-stu-id="e30bc-136">If you want to see the HTML or CSS for an element on your site, right-click the element and choose **Inspect** to jump into the **Elements** tool.</span></span>  <span data-ttu-id="e30bc-137">若要在检查元素模式下打开 DevTools，请选择\*\*\*\* `Ctrl` + `Shift` + `C` \ (Windows/Linux\) 或 `Command` + `Option` + `C` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="e30bc-137">To open the DevTools in **Inspect Element Mode**, select `Ctrl`+`Shift`+`C` \(Windows/Linux\)  or `Command`+`Option`+`C` \(macOS\).</span></span> <span data-ttu-id="e30bc-138">**使用 Inspect**元素模式，可以选择网页上的元素，在"元素"工具中显示 HTML**和**CSS。</span><span class="sxs-lookup"><span data-stu-id="e30bc-138">the **Inspect Element Mode** allows you to choose an element on the webpage and display the HTML and CSS in the **Elements** tool.</span></span>  

<span data-ttu-id="e30bc-139">如果要从前端 JavaScript 代码查看日志或快速运行某些脚本，请打开 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="e30bc-139">If you want to review logs from your front-end JavaScript code or quickly run some script, open the **Console**.</span></span>   <span data-ttu-id="e30bc-140">若要在\*\*\*\* DevTools 中启动控制台工具，请选择 `Ctrl` + `Shift` + `J` \ (Windows/Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="e30bc-140">To launch the **Console** tool in the DevTools, select `Ctrl`+`Shift`+`J` \(Windows/Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

## <a name="core-tools"></a><span data-ttu-id="e30bc-141">核心工具</span><span class="sxs-lookup"><span data-stu-id="e30bc-141">Core tools</span></span>  

:::image type="complex" source="./media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools 核心工具" lightbox="./media/devtools-core-tools.png":::
   <span data-ttu-id="e30bc-143">Microsoft Edge (Chromium) DevTools 核心工具</span><span class="sxs-lookup"><span data-stu-id="e30bc-143">Microsoft Edge (Chromium) DevTools core tools</span></span>  
:::image-end::: 

<span data-ttu-id="e30bc-144">Microsoft Edge \ (Chromium\) DevTools 包括以下工具。</span><span class="sxs-lookup"><span data-stu-id="e30bc-144">The Microsoft Edge \(Chromium\) DevTools include the following tools.</span></span>  

*   <span data-ttu-id="e30bc-145">用于 **编辑** HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 破坏断点的元素工具</span><span class="sxs-lookup"><span data-stu-id="e30bc-145">An **Elements** tool to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="e30bc-146">用于 **查看** 和筛选日志消息、检查 JavaScript 对象和 DOM 节点，以及运行所选窗口或框架上下文中的 JavaScript 的控制台</span><span class="sxs-lookup"><span data-stu-id="e30bc-146">A **Console** to review and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="e30bc-147">用于 **打开** 和编辑代码、设置断点、逐步执行代码并显示网页状态的来源工具</span><span class="sxs-lookup"><span data-stu-id="e30bc-147">A **Sources** tool to open and edit your code, set breakpoints, step through code, and display the state of your webpage</span></span>
*   <span data-ttu-id="e30bc-148">**用于**监视和检查来自网络和浏览器缓存的请求和响应的网络工具</span><span class="sxs-lookup"><span data-stu-id="e30bc-148">A **Network** tool to monitor and inspect requests and responses from the network and browser cache</span></span>   
*   <span data-ttu-id="e30bc-149">**用于**配置文件网站所需的时间和系统资源的性能工具</span><span class="sxs-lookup"><span data-stu-id="e30bc-149">A **Performance** tool to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="e30bc-150">**内存工具**，用于测量内存资源的使用，并比较代码运行时不同状态中的堆快照</span><span class="sxs-lookup"><span data-stu-id="e30bc-150">A **Memory** tool to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="e30bc-151">**用于检查**、修改和调试 Web 应用清单、服务工作者和服务工作器缓存的应用程序工具。</span><span class="sxs-lookup"><span data-stu-id="e30bc-151">An **Application** tool to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  <span data-ttu-id="e30bc-152">您还可以从应用程序工具检查和管理存储、数据库 **和** 缓存。</span><span class="sxs-lookup"><span data-stu-id="e30bc-152">You may also inspect and manage storage, databases, and caches from the **Application** tool.</span></span>  
*   <span data-ttu-id="e30bc-153">**用于**调试安全问题并确保你已正确在网页上实现 HTTPS 的安全工具。</span><span class="sxs-lookup"><span data-stu-id="e30bc-153">A **Security** tool to debug security issues and ensure that you have properly implemented HTTPS on your webpage.</span></span>  <span data-ttu-id="e30bc-154">HTTPS 为您的网站和用户提供您网站上的个人信息提供了关键安全性和数据完整性。</span><span class="sxs-lookup"><span data-stu-id="e30bc-154">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span></span>  
*   <span data-ttu-id="e30bc-155">审核 **工具** \ (现在重命名为 **Lighthouse**\) ，以运行对网页的审核。</span><span class="sxs-lookup"><span data-stu-id="e30bc-155">An **Audits** tool \(now renamed **Lighthouse**\) to run an audit of your webpage.</span></span>  <span data-ttu-id="e30bc-156">审核结果可帮助你通过以下方式提高网站质量。</span><span class="sxs-lookup"><span data-stu-id="e30bc-156">The results of the audit help you improve the quality of your site in the following ways.</span></span>  
    *   <span data-ttu-id="e30bc-157">捕获与使网页可访问性、安全性、性能等相关的常见错误。</span><span class="sxs-lookup"><span data-stu-id="e30bc-157">Catch common errors related to making your webpage accessible, secure, performant, and so on.</span></span>  
    *   <span data-ttu-id="e30bc-158">修复每个错误。</span><span class="sxs-lookup"><span data-stu-id="e30bc-158">Fix each error.</span></span>  
    *   <span data-ttu-id="e30bc-159">生成 PWA。</span><span class="sxs-lookup"><span data-stu-id="e30bc-159">Build a PWA.</span></span>  
        
[!INCLUDE [audits-panel-note](./includes/audits-panel-note.md)]  

<span data-ttu-id="e30bc-160">发送 [反馈和特性请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="e30bc-160">Send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <a name="extensions"></a><span data-ttu-id="e30bc-161">Extensions</span><span class="sxs-lookup"><span data-stu-id="e30bc-161">Extensions</span></span>  

<span data-ttu-id="e30bc-162">在生成网页 \ (或 apps\) 时，你可能会使用扩展访问 DevTools。</span><span class="sxs-lookup"><span data-stu-id="e30bc-162">You may have accessed DevTools using extensions when you diagnosed and debugged issues while you built your webpages \(or apps\).</span></span> <span data-ttu-id="e30bc-163">Microsoft Edge 扩展从 [Microsoft Edge 加载项获取][MicrosoftEdgeAddonsExtensions]。</span><span class="sxs-lookup"><span data-stu-id="e30bc-163">Microsoft Edge extensions are acquired from [Microsoft Edge Add-ons][MicrosoftEdgeAddonsExtensions].</span></span>  <span data-ttu-id="e30bc-164">在[Microsoft Edge 加载项上][MicrosoftEdgeAddonsExtensions]，从开发人员工具类别浏览 DevTools 扩展或搜索特定扩展。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e30bc-164">On [Microsoft Edge Add-ons][MicrosoftEdgeAddonsExtensions], browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span></span>  

<span data-ttu-id="e30bc-165">您还可以从 [Chrome Web Store 添加扩展][GoogleChromeWebstoreExtensions]。</span><span class="sxs-lookup"><span data-stu-id="e30bc-165">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span></span>  

:::image type="complex" source="./media/allow-extensions-from-stores.png" alt-text="Microsoft Edge 中的 Chrome Web Store" lightbox="./media/allow-extensions-from-stores.png":::
   <span data-ttu-id="e30bc-167">Microsoft Edge 中的 Chrome Web Store</span><span class="sxs-lookup"><span data-stu-id="e30bc-167">Chrome Web Store in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="e30bc-168">在顶部，选择"允许来自其他存储的扩展 **"，** 然后在出现的\*\*\*\* 对话框中选择"允许"。</span><span class="sxs-lookup"><span data-stu-id="e30bc-168">At the top, choose **Allow extensions from other stores** and then choose **Allow** in the dialog that appears.</span></span>  

> [!NOTE]
> <span data-ttu-id="e30bc-169">从 Microsoft Store 外的来源安装的扩展未经验证，可能会影响浏览器性能。</span><span class="sxs-lookup"><span data-stu-id="e30bc-169">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span></span>  

<span data-ttu-id="e30bc-170">选择 **"添加到 Chrome"** 以将 DevTools 扩展添加到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e30bc-170">Choose **Add to Chrome** to add your DevTools extension to Microsoft Edge.</span></span>  

:::image type="complex" source="./media/install-extension-from-chrome-store.png" alt-text="将 Chrome Web Store 中的扩展添加到 Microsoft Edge" lightbox="./media/install-extension-from-chrome-store.png":::
   <span data-ttu-id="e30bc-172">将 Chrome Web Store 中的扩展添加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e30bc-172">Add extension from Chrome Web Store to Microsoft Edge</span></span>  
:::image-end:::  

## <a name="shortcuts"></a><span data-ttu-id="e30bc-173">快捷方式</span><span class="sxs-lookup"><span data-stu-id="e30bc-173">Shortcuts</span></span>  

<span data-ttu-id="e30bc-174">以下快捷方式控制主 DevTools 窗口、跨所有工具或同时使用这两种工具。</span><span class="sxs-lookup"><span data-stu-id="e30bc-174">The following shortcuts control the main DevTools window, work across all tools, or both.</span></span>  

| <span data-ttu-id="e30bc-175">操作</span><span class="sxs-lookup"><span data-stu-id="e30bc-175">Action</span></span> | <span data-ttu-id="e30bc-176">Windows/Linux</span><span class="sxs-lookup"><span data-stu-id="e30bc-176">Windows/Linux</span></span> | <span data-ttu-id="e30bc-177">macOS</span><span class="sxs-lookup"><span data-stu-id="e30bc-177">macOS</span></span> |  
|:--- |:--- | :--- |  
| <span data-ttu-id="e30bc-178">显示/隐藏 DevTools \ (打开到上次查看的工具\) </span><span class="sxs-lookup"><span data-stu-id="e30bc-178">Show/Hide DevTools \(opens to last viewed tool\)</span></span> | `F12` <span data-ttu-id="e30bc-179">或 `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="e30bc-179">or `Ctrl`+`Shift`+</span></span>`I` | `Command`+`Option`+`I` |  
| <span data-ttu-id="e30bc-180">显示控制台</span><span class="sxs-lookup"><span data-stu-id="e30bc-180">Show the Console</span></span> | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| <span data-ttu-id="e30bc-181">在检查元素模式下显示 DevTools，允许你选择元素，在元素工具中显示 HTML**和**CSS \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e30bc-181">Show the DevTools in **Inspect Element Mode** that allows you to choose an element and display the HTML and CSS in the **Elements** tool</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| <span data-ttu-id="e30bc-182">显示设置</span><span class="sxs-lookup"><span data-stu-id="e30bc-182">Show Settings</span></span> | `?` <span data-ttu-id="e30bc-183">或 `Fn`+</span><span class="sxs-lookup"><span data-stu-id="e30bc-183">or `Fn`+</span></span>`F1` | `?` <span data-ttu-id="e30bc-184">或 `Fn`+</span><span class="sxs-lookup"><span data-stu-id="e30bc-184">or `Fn`+</span></span>`F1` |  
| <span data-ttu-id="e30bc-185">显示下一个面板</span><span class="sxs-lookup"><span data-stu-id="e30bc-185">Show the next panel</span></span> | `Ctrl`+`]` | `Command`+`]` |  
| <span data-ttu-id="e30bc-186">显示上一个面板</span><span class="sxs-lookup"><span data-stu-id="e30bc-186">Show the previous panel</span></span> | `Ctrl`+`[` | `Command`+`[` |  
| <span data-ttu-id="e30bc-187">将 DevTools 停靠在上次使用的位置。</span><span class="sxs-lookup"><span data-stu-id="e30bc-187">Dock the DevTools in the last position used.</span></span>  <span data-ttu-id="e30bc-188">如果 DevTools 在整个会话的默认位置保留，快捷方式将 DevTools 撤消到单独的窗口中</span><span class="sxs-lookup"><span data-stu-id="e30bc-188">If the DevTools remain in the default position for the entire session, the shortcut undocks the DevTools into a separate window</span></span> | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| <span data-ttu-id="e30bc-189">切换 **设备模式**</span><span class="sxs-lookup"><span data-stu-id="e30bc-189">Toggle **Device Mode**</span></span> | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| <span data-ttu-id="e30bc-190">切换 **检查元素模式** ，允许你选择元素，在元素工具中显示 HTML **和** CSS</span><span class="sxs-lookup"><span data-stu-id="e30bc-190">Toggle **Inspect Element Mode** that allows to you to choose an element and display the HTML and CSS in the **Elements** tool</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| <span data-ttu-id="e30bc-191">显示命令菜单</span><span class="sxs-lookup"><span data-stu-id="e30bc-191">Show the Command Menu</span></span> | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| <span data-ttu-id="e30bc-192">显示/隐藏"箱"</span><span class="sxs-lookup"><span data-stu-id="e30bc-192">Show/Hide the Drawer</span></span> | `Esc` | `Esc` |  
| <span data-ttu-id="e30bc-193">刷新。</span><span class="sxs-lookup"><span data-stu-id="e30bc-193">Refresh.</span></span>  <span data-ttu-id="e30bc-194">使用缓存刷新网页。</span><span class="sxs-lookup"><span data-stu-id="e30bc-194">Refreshes the webpage using the cache.</span></span>  | `F5` <span data-ttu-id="e30bc-195">或 `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="e30bc-195">or `Ctrl`+</span></span>`R` | `Command`+`R` |  
| <span data-ttu-id="e30bc-196">硬刷新。</span><span class="sxs-lookup"><span data-stu-id="e30bc-196">Hard Refresh.</span></span>  <span data-ttu-id="e30bc-197">强制 Microsoft Edge 重新下载资源并重新加载。</span><span class="sxs-lookup"><span data-stu-id="e30bc-197">Forces Microsoft Edge to download resources again and reload.</span></span>  <span data-ttu-id="e30bc-198">使用的资源可能来自缓存版本</span><span class="sxs-lookup"><span data-stu-id="e30bc-198">The resources that are used may come from a cached version</span></span> | `Ctrl`<span data-ttu-id="e30bc-199">+`F5` 或 `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="e30bc-199">+`F5` or `Ctrl`+`Shift`+</span></span>`R` | `Command`+`Shift`+`R` |  
| <span data-ttu-id="e30bc-200">在当前面板中搜索文本。</span><span class="sxs-lookup"><span data-stu-id="e30bc-200">Search for text within the current panel.</span></span>  <span data-ttu-id="e30bc-201">审核、应用程序和安全工具中不受支持</span><span class="sxs-lookup"><span data-stu-id="e30bc-201">Not supported in the Audits, Application, and Security tools</span></span> | `Ctrl`+`F` | `Command`+`F` |  
| <span data-ttu-id="e30bc-202">在"箱"中显示搜索工具，可让你跨所有加载的资源搜索文本</span><span class="sxs-lookup"><span data-stu-id="e30bc-202">Show the Search tool in the Drawer, which lets you search for text across all loaded resources</span></span> | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| <span data-ttu-id="e30bc-203">在"源"面板中打开文件</span><span class="sxs-lookup"><span data-stu-id="e30bc-203">Open a file in the Sources panel</span></span> | `Ctrl`<span data-ttu-id="e30bc-204">+`O` 或 `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="e30bc-204">+`O` or `Ctrl`+</span></span>`P` | `Command`<span data-ttu-id="e30bc-205">+`O` 或 `Command`+</span><span class="sxs-lookup"><span data-stu-id="e30bc-205">+`O` or `Command`+</span></span>`P` |  
| <span data-ttu-id="e30bc-206">放大</span><span class="sxs-lookup"><span data-stu-id="e30bc-206">Zoom in</span></span> | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| <span data-ttu-id="e30bc-207">缩小</span><span class="sxs-lookup"><span data-stu-id="e30bc-207">Zoom out</span></span> | `Ctrl`+`-` | `Command`+`-` |  
| <span data-ttu-id="e30bc-208">还原默认缩放级别</span><span class="sxs-lookup"><span data-stu-id="e30bc-208">Restore default zoom level</span></span> | `Ctrl`+`0` | `Command`+`0` |  
| <span data-ttu-id="e30bc-209">运行代码段</span><span class="sxs-lookup"><span data-stu-id="e30bc-209">Run snippet</span></span> | `Ctrl`<span data-ttu-id="e30bc-210">+`O``Ctrl` + `P` or ， type followed `!` by the name of the script， then select</span><span class="sxs-lookup"><span data-stu-id="e30bc-210">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then select</span></span> `Enter` | <span data-ttu-id="e30bc-211">Select `Command` + `O` or `Command` + `P` ， type `!` followed by the name of the script， then select</span><span class="sxs-lookup"><span data-stu-id="e30bc-211">Select `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then select</span></span> `Enter` |  
| <span data-ttu-id="e30bc-212">在新建选项卡中显示不可编辑的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="e30bc-212">Show non-editable HTML source code in a new tab</span></span> | `Ctrl`+`U` | <span data-ttu-id="e30bc-213">不适用</span><span class="sxs-lookup"><span data-stu-id="e30bc-213">N/A</span></span> |  

> [!NOTE]
> <span data-ttu-id="e30bc-214">如果在断点处调试并暂停，则 **刷新** 快捷方式将首先恢复运行时。</span><span class="sxs-lookup"><span data-stu-id="e30bc-214">If you are debugging and paused at a breakpoint, the **Refresh** shortcut resumes the runtime first.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e30bc-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e30bc-215">See also</span></span>  

*   [<span data-ttu-id="e30bc-216">适用于初学者的 DevTools：HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="e30bc-216">DevTools for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideChromiumBeginnersHtml]  
*   [<span data-ttu-id="e30bc-217">Microsoft Edge (Chromium) DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="e30bc-217">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolChromiumIndex]  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e30bc-218">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="e30bc-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<span data-ttu-id="e30bc-219">如果你想要预览即将进入 [DevTools][DevtoolsGuideChromiumWhatsNewIndex]的最新功能，请下载 [Microsoft Edge Canary，][MicrosoftedgeinsiderDownload]它于夜间生成。</span><span class="sxs-lookup"><span data-stu-id="e30bc-219">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "适用于初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/11/devtools "Microsoft Edge (DevTools) 中的新增|Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools 协议|Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展|Chrome Web Store"  
