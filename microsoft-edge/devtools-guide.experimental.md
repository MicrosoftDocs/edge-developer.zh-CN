---
description: 了解 Microsoft Edge 开发人员工具
title: Microsoft Edge 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: microsoft edge, web 开发, f12 工具, devtools
experimental: false
experiment_id: 51fe4b97-3e55-41
ms.openlocfilehash: 3aee2ab67c6e703a0a31b58b5bf985a23fcbb481
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986218"
---
# <span data-ttu-id="7e30e-104">Microsoft Edge 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="7e30e-104">Microsoft Edge Developer Tools</span></span>  

> [!NOTE]
> <span data-ttu-id="7e30e-105">Microsoft Edge DevTools 帮助 web 开发人员构建和测试网站。</span><span class="sxs-lookup"><span data-stu-id="7e30e-105">The Microsoft Edge DevTools help web developers build and test websites.</span></span>  <span data-ttu-id="7e30e-106">如果意外打开了 DevTools，只需按下 `F12` 即可关闭。</span><span class="sxs-lookup"><span data-stu-id="7e30e-106">If you accidentally opened the DevTools, just press `F12` to close.</span></span>  

<span data-ttu-id="7e30e-107">Microsoft Edge DevTools 是通过[开放源代码](https://github.com/Microsoft/ChakraCore)（针对新式前端工作流进行了优化）[生成的，](https://www.typescriptlang.org/)现在可在 Microsoft Store 中作为[独立的 Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)使用。</span><span class="sxs-lookup"><span data-stu-id="7e30e-107">The Microsoft Edge DevTools are built with [TypeScript](https://www.typescriptlang.org/), powered by [open source](https://github.com/Microsoft/ChakraCore), optimized for modern front-end workflows, and now available as a [standalone Windows 10 app](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) in the Microsoft Store!</span></span>

<span data-ttu-id="7e30e-108">有关最新功能的详细信息，请参阅 [\*Windows 10 (EdgeHTML 17) 的最新更新 DevTools \*](./devtools-guide/whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="7e30e-108">For more on the latest features, check out [*DevTools in the latest update of Windows 10 (EdgeHTML 17)*](./devtools-guide/whats-new.md).</span></span>

## <span data-ttu-id="7e30e-109">核心工具</span><span class="sxs-lookup"><span data-stu-id="7e30e-109">Core tools</span></span>

![Microsoft Edge 开发工具](./devtools-guide/media/devtools.png)

<span data-ttu-id="7e30e-111">Microsoft Edge DevTools 包括：</span><span class="sxs-lookup"><span data-stu-id="7e30e-111">The Microsoft Edge DevTools include:</span></span>

 - <span data-ttu-id="7e30e-112">" [**元素**](./devtools-guide/elements.md) " 面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 转变断点</span><span class="sxs-lookup"><span data-stu-id="7e30e-112">An [**Elements**](./devtools-guide/elements.md) panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>
 - <span data-ttu-id="7e30e-113">用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点以及在所选窗口或框架的上下文中运行 JavaScript 的[**控制台**](./devtools-guide/console.md)</span><span class="sxs-lookup"><span data-stu-id="7e30e-113">A [**Console**](./devtools-guide/console.md) to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>
 - <span data-ttu-id="7e30e-114">用于逐句通过代码、设置监视和断点、实时编辑代码以及检查 web 存储和 cookie 缓存的[**调试器**](./devtools-guide/debugger.md)</span><span class="sxs-lookup"><span data-stu-id="7e30e-114">A [**Debugger**](./devtools-guide/debugger.md) to step through code, set watches and breakpoints, live edit your code, and inspect your web storage and cookie caches</span></span>
 - <span data-ttu-id="7e30e-115">用于监视和检查来自网络和浏览器缓存的请求和响应的 [**网络**](./devtools-guide/network.md) 面板</span><span class="sxs-lookup"><span data-stu-id="7e30e-115">A [**Network**](./devtools-guide/network.md) panel to monitor and inspect requests and responses from the network and browser cache</span></span> 
 - <span data-ttu-id="7e30e-116">用于分析你的网站所需的时间和系统资源的 [**性能**](./devtools-guide/performance.md) 面板</span><span class="sxs-lookup"><span data-stu-id="7e30e-116">A [**Performance**](./devtools-guide/performance.md) panel to profile the time and system resources required by your site</span></span>
 - <span data-ttu-id="7e30e-117">用于测量内存资源使用情况并比较不同代码执行状态的堆快照的 [**内存**](./devtools-guide/memory.md) 面板</span><span class="sxs-lookup"><span data-stu-id="7e30e-117">A [**Memory**](./devtools-guide/memory.md) panel to measure your use of memory resources and compare heap snapshots at different states of code execution</span></span>
 - <span data-ttu-id="7e30e-118">用于使用不同浏览器配置文件、屏幕分辨率和 GPS 位置坐标测试网站的 [**仿真**](./devtools-guide/emulation.md) 面板</span><span class="sxs-lookup"><span data-stu-id="7e30e-118">An [**Emulation**](./devtools-guide/emulation.md) panel to test your site with different browser profiles, screen resolutions, and GPS location coordinates</span></span>

<span data-ttu-id="7e30e-119">请继续发送您的 [反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="7e30e-119">Please keep sending your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>

> [!TIP]
> <span data-ttu-id="7e30e-120">**[从任何浏览器免费测试 Microsoft edge](https://developer.microsoft.com/microsoft-edge/tools/remote/)**：我们与 [BrowserStack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud) 合作，在 microsoft edge 上提供免费实时和自动测试。</span><span class="sxs-lookup"><span data-stu-id="7e30e-120">**[Test on Microsoft Edge free from any browser](https://developer.microsoft.com/microsoft-edge/tools/remote/)**: We partnered with [BrowserStack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud) to provide free live and automated testing on Microsoft Edge.</span></span>

## <span data-ttu-id="7e30e-121">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="7e30e-121">Microsoft Store app</span></span>

<span data-ttu-id="7e30e-122">**Microsoft Edge DevTools** [现在可](./devtools-guide/whats-new.md)用作 microsoft Store 中的独立[Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)，除了浏览器中 (`F12`) 工具体验。</span><span class="sxs-lookup"><span data-stu-id="7e30e-122">The **Microsoft Edge DevTools** are [now available for preview](./devtools-guide/whats-new.md) as a standalone [Windows 10 app from the Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab), in addition to the in-browser (`F12`) tooling experience.</span></span> <span data-ttu-id="7e30e-123">应用商店版本提供了一个*选择器*面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。</span><span class="sxs-lookup"><span data-stu-id="7e30e-123">With the store version comes a *chooser* panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span>

### <span data-ttu-id="7e30e-124">本地调试</span><span class="sxs-lookup"><span data-stu-id="7e30e-124">Local debugging</span></span>

<span data-ttu-id="7e30e-125">若要在本地调试页面，只需启动 *Microsoft Edge DevTools* 应用。</span><span class="sxs-lookup"><span data-stu-id="7e30e-125">To debug a page locally, simply launch the *Microsoft Edge DevTools* app.</span></span> <span data-ttu-id="7e30e-126">选择器的 **本地** 面板将显示所有活动的 EdgeHTML 内容进程，包括打开的边缘浏览器选项卡、运行 [PWAs](./progressive-web-apps-edgehtml/index.md) (*WWAHost.exe* 进程) 和 [web 视图](./webview.md) 控件。</span><span class="sxs-lookup"><span data-stu-id="7e30e-126">The **Local** panel of the chooser will display all of the active EdgeHTML content processes, including open Edge browser tabs, running [PWAs](./progressive-web-apps-edgehtml/index.md) (*WWAHost.exe* processes), and [webview](./webview.md) controls.</span></span> <span data-ttu-id="7e30e-127">单击所需的目标以附加并打开 DevTools 的新选项卡实例。</span><span class="sxs-lookup"><span data-stu-id="7e30e-127">Click on your desired target to attach and open a new tab instance of the DevTools.</span></span>

![DevTools 应用的“本地”面板](./devtools-guide/media/chooser_local.png)

### <span data-ttu-id="7e30e-129">远程调试</span><span class="sxs-lookup"><span data-stu-id="7e30e-129">Remote debugging</span></span>

<span data-ttu-id="7e30e-130">*Microsoft Edge DevTools*应用通过我们新发布的[**DevTools 协议**](./devtools-protocol/index.md)引入了对远程计算机上的页面调试的基本支持。</span><span class="sxs-lookup"><span data-stu-id="7e30e-130">The *Microsoft Edge DevTools* app introduces basic support for debugging pages on a remote machine via our newly released [**DevTools Protocol**](./devtools-protocol/index.md).</span></span> <span data-ttu-id="7e30e-131">通过此版本，可在 [**调试程序**](./devtools-guide/debugger.md) 面板中远程访问核心 funtionality，减去 Web 存储、服务工作人员、缓存 API 和 IndexedDB) 的缓存检查 (。</span><span class="sxs-lookup"><span data-stu-id="7e30e-131">With this release comes remote access to core funtionality in the [**Debugger**](./devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> <span data-ttu-id="7e30e-132">远程调试仅限于 *Microsoft Edge* 运行 *桌面* 主机，并且支持其他 EdgeHTML 主机和在未来版本中推出的 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="7e30e-132">Remote debugging is limited to *Microsoft Edge* running *desktop* hosts, with support for other EdgeHTML hosts and Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="7e30e-133">若要开始，请查看“[DevTools 协议](./devtools-protocol/index.md)”文档的“[*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)”部分。</span><span class="sxs-lookup"><span data-stu-id="7e30e-133">To get started, check out the [*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) section of the [DevTools Protocol](./devtools-protocol/index.md) docs.</span></span>

![DevTools 应用“远程”面板](./devtools-guide/media/chooser_remote.png)

## <span data-ttu-id="7e30e-135">常规快捷方式</span><span class="sxs-lookup"><span data-stu-id="7e30e-135">General Shortcuts</span></span>

<span data-ttu-id="7e30e-136">这些快捷方式控制主 DevTools 窗口和/或跨所有工具工作。</span><span class="sxs-lookup"><span data-stu-id="7e30e-136">These shortcuts control the main DevTools window and/or work across all tools.</span></span>

<span data-ttu-id="7e30e-137">操作</span><span class="sxs-lookup"><span data-stu-id="7e30e-137">Action</span></span> | <span data-ttu-id="7e30e-138">快捷方式</span><span class="sxs-lookup"><span data-stu-id="7e30e-138">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="7e30e-139">显示/隐藏 DevTools (打开上一次查看的面板) </span><span class="sxs-lookup"><span data-stu-id="7e30e-139">Show/Hide DevTools (opens to last viewed panel)</span></span> | <span data-ttu-id="7e30e-140">F12，Ctrl + Shift + I</span><span class="sxs-lookup"><span data-stu-id="7e30e-140">F12, Ctrl+Shift+I</span></span>
<span data-ttu-id="7e30e-141">切换停靠 (脱开/下/右) </span><span class="sxs-lookup"><span data-stu-id="7e30e-141">Toggle docking (Undock/Bottom/Right)</span></span> | <span data-ttu-id="7e30e-142">Ctrl + Shift + D</span><span class="sxs-lookup"><span data-stu-id="7e30e-142">Ctrl+Shift+D</span></span> 
<span data-ttu-id="7e30e-143">在调试程序中显示不可编辑的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="7e30e-143">Show non-editable HTML source code in Debugger</span></span> | <span data-ttu-id="7e30e-144">Ctrl + U</span><span class="sxs-lookup"><span data-stu-id="7e30e-144">Ctrl+U</span></span>
<span data-ttu-id="7e30e-145">在任何其他工具底部显示/隐藏“控制台”</span><span class="sxs-lookup"><span data-stu-id="7e30e-145">Show/hide Console at the bottom of any other tool</span></span>  | <span data-ttu-id="7e30e-146">Ctrl +**\`**</span><span class="sxs-lookup"><span data-stu-id="7e30e-146">Ctrl+**\`**</span></span>
<span data-ttu-id="7e30e-147">切换到 DOM 资源管理器 (的元素) </span><span class="sxs-lookup"><span data-stu-id="7e30e-147">Switch to Elements (DOM Explorer)</span></span> | <span data-ttu-id="7e30e-148">Ctrl + 1</span><span class="sxs-lookup"><span data-stu-id="7e30e-148">Ctrl+1</span></span>
<span data-ttu-id="7e30e-149">切换到“控制台”</span><span class="sxs-lookup"><span data-stu-id="7e30e-149">Switch to Console</span></span> |  <span data-ttu-id="7e30e-150">Ctrl + 2</span><span class="sxs-lookup"><span data-stu-id="7e30e-150">Ctrl+2</span></span>
<span data-ttu-id="7e30e-151">切换到“调试程序”</span><span class="sxs-lookup"><span data-stu-id="7e30e-151">Switch to Debugger</span></span> | <span data-ttu-id="7e30e-152">Ctrl + 3</span><span class="sxs-lookup"><span data-stu-id="7e30e-152">Ctrl+3</span></span>
<span data-ttu-id="7e30e-153">切换到“网络”</span><span class="sxs-lookup"><span data-stu-id="7e30e-153">Switch to Network</span></span> | <span data-ttu-id="7e30e-154">Ctrl + 4</span><span class="sxs-lookup"><span data-stu-id="7e30e-154">Ctrl+4</span></span>
<span data-ttu-id="7e30e-155">切换到“性能”</span><span class="sxs-lookup"><span data-stu-id="7e30e-155">Switch to Performance</span></span> | <span data-ttu-id="7e30e-156">Ctrl + 5</span><span class="sxs-lookup"><span data-stu-id="7e30e-156">Ctrl+5</span></span>
<span data-ttu-id="7e30e-157">切换到“内存”</span><span class="sxs-lookup"><span data-stu-id="7e30e-157">Switch to Memory</span></span> | <span data-ttu-id="7e30e-158">Ctrl + 6</span><span class="sxs-lookup"><span data-stu-id="7e30e-158">Ctrl+6</span></span>
<span data-ttu-id="7e30e-159">切换到“枚举”</span><span class="sxs-lookup"><span data-stu-id="7e30e-159">Switch to Emulation</span></span> | <span data-ttu-id="7e30e-160">Ctrl + 7</span><span class="sxs-lookup"><span data-stu-id="7e30e-160">Ctrl+7</span></span>
<span data-ttu-id="7e30e-161">帮助文档</span><span class="sxs-lookup"><span data-stu-id="7e30e-161">Help Document</span></span> | <span data-ttu-id="7e30e-162">F1</span><span class="sxs-lookup"><span data-stu-id="7e30e-162">F1</span></span>
<span data-ttu-id="7e30e-163">下一个工具</span><span class="sxs-lookup"><span data-stu-id="7e30e-163">Next tool</span></span> | <span data-ttu-id="7e30e-164">Ctrl + F6</span><span class="sxs-lookup"><span data-stu-id="7e30e-164">Ctrl+F6</span></span>
<span data-ttu-id="7e30e-165">上一个工具</span><span class="sxs-lookup"><span data-stu-id="7e30e-165">Previous tool</span></span> | <span data-ttu-id="7e30e-166">Ctrl + Shift + F6</span><span class="sxs-lookup"><span data-stu-id="7e30e-166">Ctrl+Shift+F6</span></span>
<span data-ttu-id="7e30e-167">以前的工具 (历史记录) </span><span class="sxs-lookup"><span data-stu-id="7e30e-167">Previous tool (from history)</span></span> | <span data-ttu-id="7e30e-168">Ctrl + Shift + [</span><span class="sxs-lookup"><span data-stu-id="7e30e-168">Ctrl+Shift+[</span></span>
<span data-ttu-id="7e30e-169">"下一工具" ("历史记录") </span><span class="sxs-lookup"><span data-stu-id="7e30e-169">Next tool (from history)</span></span> | <span data-ttu-id="7e30e-170">Ctrl + Shift +]</span><span class="sxs-lookup"><span data-stu-id="7e30e-170">Ctrl+Shift+]</span></span>
<span data-ttu-id="7e30e-171">下一个子框架</span><span class="sxs-lookup"><span data-stu-id="7e30e-171">Next Subframe</span></span>    | <span data-ttu-id="7e30e-172">F6</span><span class="sxs-lookup"><span data-stu-id="7e30e-172">F6</span></span>
<span data-ttu-id="7e30e-173">上一个子框架</span><span class="sxs-lookup"><span data-stu-id="7e30e-173">Previous Subframe</span></span> | <span data-ttu-id="7e30e-174">Shift + F6</span><span class="sxs-lookup"><span data-stu-id="7e30e-174">Shift+F6</span></span>
<span data-ttu-id="7e30e-175">搜索框中的下一个匹配项</span><span class="sxs-lookup"><span data-stu-id="7e30e-175">Next match in Search box</span></span> | <span data-ttu-id="7e30e-176">F3</span><span class="sxs-lookup"><span data-stu-id="7e30e-176">F3</span></span>
<span data-ttu-id="7e30e-177">搜索框中的上一个匹配项</span><span class="sxs-lookup"><span data-stu-id="7e30e-177">Previous match in Search box</span></span> | <span data-ttu-id="7e30e-178">Shift+F3</span><span class="sxs-lookup"><span data-stu-id="7e30e-178">Shift+F3</span></span>
<span data-ttu-id="7e30e-179">在搜索框中查找</span><span class="sxs-lookup"><span data-stu-id="7e30e-179">Find in search box</span></span> | <span data-ttu-id="7e30e-180">Ctrl+F</span><span class="sxs-lookup"><span data-stu-id="7e30e-180">Ctrl+F</span></span>
<span data-ttu-id="7e30e-181">将焦点放在底部的控制台上</span><span class="sxs-lookup"><span data-stu-id="7e30e-181">Give focus to console at the bottom</span></span> | <span data-ttu-id="7e30e-182">Alt + Shift + I</span><span class="sxs-lookup"><span data-stu-id="7e30e-182">Alt+Shift+I</span></span>
<span data-ttu-id="7e30e-183">停靠/取消停靠工具 (切换停靠) </span><span class="sxs-lookup"><span data-stu-id="7e30e-183">Dock/undock tools (toggle docking)</span></span> | <span data-ttu-id="7e30e-184">Ctrl+P</span><span class="sxs-lookup"><span data-stu-id="7e30e-184">Ctrl+P</span></span>  
<span data-ttu-id="7e30e-185">启动 DevTools 到“控制台”</span><span class="sxs-lookup"><span data-stu-id="7e30e-185">Launch DevTools to Console</span></span> | <span data-ttu-id="7e30e-186">Ctrl + Shift + J</span><span class="sxs-lookup"><span data-stu-id="7e30e-186">Ctrl+Shift+J</span></span>
<span data-ttu-id="7e30e-187">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="7e30e-187">Refresh the page.</span></span> <span data-ttu-id="7e30e-188">**注意：** 如果你在断点处进行调试和暂停，这将首先继续执行。</span><span class="sxs-lookup"><span data-stu-id="7e30e-188">**Note:** if you're debugging and paused at a breakpoint, this resumes execution first.</span></span> | <span data-ttu-id="7e30e-189">Ctrl + Shift + F5 或 Ctrl + R</span><span class="sxs-lookup"><span data-stu-id="7e30e-189">Ctrl+Shift+F5 or Ctrl+R</span></span>

## <span data-ttu-id="7e30e-190">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="7e30e-190">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./devtools-guide-chromium/includes/contact-devtools-team-note.md)]  
