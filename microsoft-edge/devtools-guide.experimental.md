---
description: 了解 Microsoft Edge 开发人员工具
title: Microsoft Edge 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: microsoft edge、web 开发、f12 工具、devtools
experimental: false
experiment_id: 51fe4b97-3e55-41
ms.openlocfilehash: 47b7a3f4f523170f4dfb6f3ef674cecfdc0e157c
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645327"
---
# <span data-ttu-id="a1c3e-104">Microsoft Edge 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="a1c3e-104">Microsoft Edge Developer Tools</span></span>  

> [!NOTE]
> <span data-ttu-id="a1c3e-105">Microsoft Edge DevTools 帮助 web 开发人员构建和测试网站。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-105">The Microsoft Edge DevTools help web developers build and test websites.</span></span>  <span data-ttu-id="a1c3e-106">如果意外打开了 DevTools，只需按下 `F12` 即可关闭。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-106">If you accidentally opened the DevTools, just press `F12` to close.</span></span>  

<span data-ttu-id="a1c3e-107">Microsoft Edge DevTools 是通过[开放源代码](https://github.com/Microsoft/ChakraCore)（针对新式前端工作流进行了优化）[生成的，](https://www.typescriptlang.org/)现在可在 Microsoft Store 中作为[独立的 Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)使用。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-107">The Microsoft Edge DevTools are built with [TypeScript](https://www.typescriptlang.org/), powered by [open source](https://github.com/Microsoft/ChakraCore), optimized for modern front-end workflows, and now available as a [standalone Windows 10 app](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) in the Microsoft Store!</span></span>

<span data-ttu-id="a1c3e-108">有关最新功能的详细信息，请查看[*最新的 Windows 10 更新（EdgeHTML 17） DevTools*](./devtools-guide/whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-108">For more on the latest features, check out [*DevTools in the latest update of Windows 10 (EdgeHTML 17)*](./devtools-guide/whats-new.md).</span></span>

## <span data-ttu-id="a1c3e-109">核心工具</span><span class="sxs-lookup"><span data-stu-id="a1c3e-109">Core tools</span></span>

![Microsoft Edge 开发工具](./devtools-guide/media/devtools.png)

<span data-ttu-id="a1c3e-111">Microsoft Edge DevTools 包括：</span><span class="sxs-lookup"><span data-stu-id="a1c3e-111">The Microsoft Edge DevTools include:</span></span>

 - <span data-ttu-id="a1c3e-112">"[**元素**](./devtools-guide/elements.md)" 面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 转变断点</span><span class="sxs-lookup"><span data-stu-id="a1c3e-112">An [**Elements**](./devtools-guide/elements.md) panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>
 - <span data-ttu-id="a1c3e-113">用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点以及在所选窗口或框架的上下文中运行 JavaScript 的[**控制台**](./devtools-guide/console.md)</span><span class="sxs-lookup"><span data-stu-id="a1c3e-113">A [**Console**](./devtools-guide/console.md) to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>
 - <span data-ttu-id="a1c3e-114">用于逐句通过代码、设置监视和断点、实时编辑代码以及检查 web 存储和 cookie 缓存的[**调试器**](./devtools-guide/debugger.md)</span><span class="sxs-lookup"><span data-stu-id="a1c3e-114">A [**Debugger**](./devtools-guide/debugger.md) to step through code, set watches and breakpoints, live edit your code, and inspect your web storage and cookie caches</span></span>
 - <span data-ttu-id="a1c3e-115">用于监视和检查来自网络和浏览器缓存的请求和响应的[**网络**](./devtools-guide/network.md)面板</span><span class="sxs-lookup"><span data-stu-id="a1c3e-115">A [**Network**](./devtools-guide/network.md) panel to monitor and inspect requests and responses from the network and browser cache</span></span> 
 - <span data-ttu-id="a1c3e-116">用于分析你的网站所需的时间和系统资源的[**性能**](./devtools-guide/performance.md)面板</span><span class="sxs-lookup"><span data-stu-id="a1c3e-116">A [**Performance**](./devtools-guide/performance.md) panel to profile the time and system resources required by your site</span></span>
 - <span data-ttu-id="a1c3e-117">用于测量内存资源使用情况并比较不同代码执行状态的堆快照的[**内存**](./devtools-guide/memory.md)面板</span><span class="sxs-lookup"><span data-stu-id="a1c3e-117">A [**Memory**](./devtools-guide/memory.md) panel to measure your use of memory resources and compare heap snapshots at different states of code execution</span></span>
 - <span data-ttu-id="a1c3e-118">用于使用不同浏览器配置文件、屏幕分辨率和 GPS 位置坐标测试网站的[**仿真**](./devtools-guide/emulation.md)面板</span><span class="sxs-lookup"><span data-stu-id="a1c3e-118">An [**Emulation**](./devtools-guide/emulation.md) panel to test your site with different browser profiles, screen resolutions, and GPS location coordinates</span></span>

<span data-ttu-id="a1c3e-119">请继续发送您的[反馈和功能请求](#feedback)！</span><span class="sxs-lookup"><span data-stu-id="a1c3e-119">Please keep sending your [feedback and feature requests](#feedback)!</span></span>

> [!TIP]
> <span data-ttu-id="a1c3e-120">**[从任何浏览器免费测试 Microsoft edge](https://developer.microsoft.com/microsoft-edge/tools/remote/)**：我们与[BrowserStack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud)合作，在 microsoft edge 上提供免费实时和自动测试。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-120">**[Test on Microsoft Edge free from any browser](https://developer.microsoft.com/microsoft-edge/tools/remote/)**: We partnered with [BrowserStack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud) to provide free live and automated testing on Microsoft Edge.</span></span>

## <span data-ttu-id="a1c3e-121">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="a1c3e-121">Microsoft Store app</span></span>

<span data-ttu-id="a1c3e-122">**Microsoft Edge DevTools** [现在可](./devtools-guide/whats-new.md)用作 microsoft Store 中的独立[Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)，除了浏览器（ `F12` ）工具体验。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-122">The **Microsoft Edge DevTools** are [now available for preview](./devtools-guide/whats-new.md) as a standalone [Windows 10 app from the Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab), in addition to the in-browser (`F12`) tooling experience.</span></span> <span data-ttu-id="a1c3e-123">使用应用商店版本时，将出现一个*选择器*面板，用于附加到打开本地和远程页面目标以及选项卡式布局，以便在 DevTools 实例之间轻松切换。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-123">With the store version comes a *chooser* panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span>

### <span data-ttu-id="a1c3e-124">本地调试</span><span class="sxs-lookup"><span data-stu-id="a1c3e-124">Local debugging</span></span>

<span data-ttu-id="a1c3e-125">若要在本地调试页面，只需启动*Microsoft Edge DevTools*应用。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-125">To debug a page locally, simply launch the *Microsoft Edge DevTools* app.</span></span> <span data-ttu-id="a1c3e-126">选择器的**本地**面板将显示所有活动的 EdgeHTML 内容进程，包括打开的边缘浏览器选项卡、运行[PWAs](./progressive-web-apps-edgehtml/index.md) （*WWAHost*进程）和[web 视图](./webview.md)控件。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-126">The **Local** panel of the chooser will display all of the active EdgeHTML content processes, including open Edge browser tabs, running [PWAs](./progressive-web-apps-edgehtml/index.md) (*WWAHost.exe* processes), and [webview](./webview.md) controls.</span></span> <span data-ttu-id="a1c3e-127">单击所需的目标以附加并打开 DevTools 的新选项卡实例。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-127">Click on your desired target to attach and open a new tab instance of the DevTools.</span></span>

![DevTools app 本地面板](./devtools-guide/media/chooser_local.png)

### <span data-ttu-id="a1c3e-129">远程调试</span><span class="sxs-lookup"><span data-stu-id="a1c3e-129">Remote debugging</span></span>

<span data-ttu-id="a1c3e-130">*Microsoft Edge DevTools*应用通过我们新发布的[**DevTools 协议**](./devtools-protocol/index.md)引入了对远程计算机上的页面调试的基本支持。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-130">The *Microsoft Edge DevTools* app introduces basic support for debugging pages on a remote machine via our newly released [**DevTools Protocol**](./devtools-protocol/index.md).</span></span> <span data-ttu-id="a1c3e-131">通过此版本，可在[**调试程序**](./devtools-guide/debugger.md)面板中远程访问核心 funtionality，减去缓存检查（对于 Web 存储、服务工作人员、缓存 API 和 IndexedDB）。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-131">With this release comes remote access to core funtionality in the [**Debugger**](./devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> <span data-ttu-id="a1c3e-132">远程调试仅限于*Microsoft Edge*运行*桌面*主机，并且支持其他 EdgeHTML 主机和在未来版本中推出的 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-132">Remote debugging is limited to *Microsoft Edge* running *desktop* hosts, with support for other EdgeHTML hosts and Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="a1c3e-133">若要开始使用，请查看[DevTools 协议](./devtools-protocol/index.md)文档的[*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)部分。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-133">To get started, check out the [*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) section of the [DevTools Protocol](./devtools-protocol/index.md) docs.</span></span>

![DevTools 应用程序远程面板](./devtools-guide/media/chooser_remote.png)

## <span data-ttu-id="a1c3e-135">反馈</span><span class="sxs-lookup"><span data-stu-id="a1c3e-135">Feedback</span></span>

<span data-ttu-id="a1c3e-136">请向我们发送您的反馈，以便我们可以继续为您改进 Microsoft Edge DevTools！</span><span class="sxs-lookup"><span data-stu-id="a1c3e-136">Please send us your feedback so we can continue improving the Microsoft Edge DevTools for you!</span></span> <span data-ttu-id="a1c3e-137">只需打开 "工具" （ `F12` ），然后单击 "[**发送反馈**](#microsoft-edge-developer-tools)" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-137">Simply open the tools (`F12`) and click the [**Send feedback**](#microsoft-edge-developer-tools) button.</span></span>

<span data-ttu-id="a1c3e-138">您还可以向[UserVoice 论坛](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/84475-f12-developer-tools)添加和投赞成票刀具请求，并成为[Windows 预览体验成员](https://insider.windows.com/)，以预览[即将进入 DevTools 的最新功能](./devtools-guide/whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-138">You can also add and upvote tooling requests to our [UserVoice forum](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/84475-f12-developer-tools) and become a [Windows Insider](https://insider.windows.com/) to preview the [latest features coming to the DevTools](./devtools-guide/whats-new.md).</span></span> <span data-ttu-id="a1c3e-139">使用 Windows**反馈中心**应用发布、投赞成票、跟踪和获取有关常规 Windows 建议和问题的支持。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-139">Use the Windows **Feedback Hub** app to post, upvote, track and get support for general Windows suggestions and problems.</span></span>

## <span data-ttu-id="a1c3e-140">常规快捷方式</span><span class="sxs-lookup"><span data-stu-id="a1c3e-140">General Shortcuts</span></span>

<span data-ttu-id="a1c3e-141">这些快捷方式控制主 DevTools 窗口和/或跨所有工具工作。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-141">These shortcuts control the main DevTools window and/or work across all tools.</span></span>

<span data-ttu-id="a1c3e-142">操作</span><span class="sxs-lookup"><span data-stu-id="a1c3e-142">Action</span></span> | <span data-ttu-id="a1c3e-143">快捷方式</span><span class="sxs-lookup"><span data-stu-id="a1c3e-143">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="a1c3e-144">显示/隐藏 DevTools （打开到上次查看的面板）</span><span class="sxs-lookup"><span data-stu-id="a1c3e-144">Show/Hide DevTools (opens to last viewed panel)</span></span> | <span data-ttu-id="a1c3e-145">F12，Ctrl + Shift + I</span><span class="sxs-lookup"><span data-stu-id="a1c3e-145">F12, Ctrl+Shift+I</span></span>
<span data-ttu-id="a1c3e-146">切换停靠（取消停靠/底部/右侧）</span><span class="sxs-lookup"><span data-stu-id="a1c3e-146">Toggle docking (Undock/Bottom/Right)</span></span> | <span data-ttu-id="a1c3e-147">Ctrl + Shift + D</span><span class="sxs-lookup"><span data-stu-id="a1c3e-147">Ctrl+Shift+D</span></span> 
<span data-ttu-id="a1c3e-148">在调试器中显示不可编辑的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="a1c3e-148">Show non-editable HTML source code in Debugger</span></span> | <span data-ttu-id="a1c3e-149">Ctrl + U</span><span class="sxs-lookup"><span data-stu-id="a1c3e-149">Ctrl+U</span></span>
<span data-ttu-id="a1c3e-150">在任何其他工具的底部显示/隐藏控制台</span><span class="sxs-lookup"><span data-stu-id="a1c3e-150">Show/hide Console at the bottom of any other tool</span></span>  | <span data-ttu-id="a1c3e-151">Ctrl +**\`**</span><span class="sxs-lookup"><span data-stu-id="a1c3e-151">Ctrl+**\`**</span></span>
<span data-ttu-id="a1c3e-152">切换到元素（DOM 资源管理器）</span><span class="sxs-lookup"><span data-stu-id="a1c3e-152">Switch to Elements (DOM Explorer)</span></span> | <span data-ttu-id="a1c3e-153">Ctrl + 1</span><span class="sxs-lookup"><span data-stu-id="a1c3e-153">Ctrl+1</span></span>
<span data-ttu-id="a1c3e-154">切换到控制台</span><span class="sxs-lookup"><span data-stu-id="a1c3e-154">Switch to Console</span></span> |  <span data-ttu-id="a1c3e-155">Ctrl + 2</span><span class="sxs-lookup"><span data-stu-id="a1c3e-155">Ctrl+2</span></span>
<span data-ttu-id="a1c3e-156">切换到调试器</span><span class="sxs-lookup"><span data-stu-id="a1c3e-156">Switch to Debugger</span></span> | <span data-ttu-id="a1c3e-157">Ctrl + 3</span><span class="sxs-lookup"><span data-stu-id="a1c3e-157">Ctrl+3</span></span>
<span data-ttu-id="a1c3e-158">切换到网络</span><span class="sxs-lookup"><span data-stu-id="a1c3e-158">Switch to Network</span></span> | <span data-ttu-id="a1c3e-159">Ctrl + 4</span><span class="sxs-lookup"><span data-stu-id="a1c3e-159">Ctrl+4</span></span>
<span data-ttu-id="a1c3e-160">切换到性能</span><span class="sxs-lookup"><span data-stu-id="a1c3e-160">Switch to Performance</span></span> | <span data-ttu-id="a1c3e-161">Ctrl + 5</span><span class="sxs-lookup"><span data-stu-id="a1c3e-161">Ctrl+5</span></span>
<span data-ttu-id="a1c3e-162">切换到内存</span><span class="sxs-lookup"><span data-stu-id="a1c3e-162">Switch to Memory</span></span> | <span data-ttu-id="a1c3e-163">Ctrl + 6</span><span class="sxs-lookup"><span data-stu-id="a1c3e-163">Ctrl+6</span></span>
<span data-ttu-id="a1c3e-164">切换到仿真</span><span class="sxs-lookup"><span data-stu-id="a1c3e-164">Switch to Emulation</span></span> | <span data-ttu-id="a1c3e-165">Ctrl + 7</span><span class="sxs-lookup"><span data-stu-id="a1c3e-165">Ctrl+7</span></span>
<span data-ttu-id="a1c3e-166">帮助文档</span><span class="sxs-lookup"><span data-stu-id="a1c3e-166">Help Document</span></span> | <span data-ttu-id="a1c3e-167">F1</span><span class="sxs-lookup"><span data-stu-id="a1c3e-167">F1</span></span>
<span data-ttu-id="a1c3e-168">下一个工具</span><span class="sxs-lookup"><span data-stu-id="a1c3e-168">Next tool</span></span> | <span data-ttu-id="a1c3e-169">Ctrl + F6</span><span class="sxs-lookup"><span data-stu-id="a1c3e-169">Ctrl+F6</span></span>
<span data-ttu-id="a1c3e-170">上一个工具</span><span class="sxs-lookup"><span data-stu-id="a1c3e-170">Previous tool</span></span> | <span data-ttu-id="a1c3e-171">Ctrl + Shift + F6</span><span class="sxs-lookup"><span data-stu-id="a1c3e-171">Ctrl+Shift+F6</span></span>
<span data-ttu-id="a1c3e-172">上一个工具（来自历史记录）</span><span class="sxs-lookup"><span data-stu-id="a1c3e-172">Previous tool (from history)</span></span> | <span data-ttu-id="a1c3e-173">Ctrl + Shift + [</span><span class="sxs-lookup"><span data-stu-id="a1c3e-173">Ctrl+Shift+[</span></span>
<span data-ttu-id="a1c3e-174">下一个工具（来自历史记录）</span><span class="sxs-lookup"><span data-stu-id="a1c3e-174">Next tool (from history)</span></span> | <span data-ttu-id="a1c3e-175">Ctrl + Shift +]</span><span class="sxs-lookup"><span data-stu-id="a1c3e-175">Ctrl+Shift+]</span></span>
<span data-ttu-id="a1c3e-176">下一个 Subframe</span><span class="sxs-lookup"><span data-stu-id="a1c3e-176">Next Subframe</span></span>    | <span data-ttu-id="a1c3e-177">F6</span><span class="sxs-lookup"><span data-stu-id="a1c3e-177">F6</span></span>
<span data-ttu-id="a1c3e-178">以前的 Subframe</span><span class="sxs-lookup"><span data-stu-id="a1c3e-178">Previous Subframe</span></span> | <span data-ttu-id="a1c3e-179">Shift + F6</span><span class="sxs-lookup"><span data-stu-id="a1c3e-179">Shift+F6</span></span>
<span data-ttu-id="a1c3e-180">搜索框中的下一个匹配项</span><span class="sxs-lookup"><span data-stu-id="a1c3e-180">Next match in Search box</span></span> | <span data-ttu-id="a1c3e-181">F3</span><span class="sxs-lookup"><span data-stu-id="a1c3e-181">F3</span></span>
<span data-ttu-id="a1c3e-182">搜索框中的上一个匹配项</span><span class="sxs-lookup"><span data-stu-id="a1c3e-182">Previous match in Search box</span></span> | <span data-ttu-id="a1c3e-183">Shift+F3</span><span class="sxs-lookup"><span data-stu-id="a1c3e-183">Shift+F3</span></span>
<span data-ttu-id="a1c3e-184">在搜索框中查找</span><span class="sxs-lookup"><span data-stu-id="a1c3e-184">Find in search box</span></span> | <span data-ttu-id="a1c3e-185">Ctrl+F</span><span class="sxs-lookup"><span data-stu-id="a1c3e-185">Ctrl+F</span></span>
<span data-ttu-id="a1c3e-186">向底部的控制台提供焦点</span><span class="sxs-lookup"><span data-stu-id="a1c3e-186">Give focus to console at the bottom</span></span> | <span data-ttu-id="a1c3e-187">Alt + Shift + I</span><span class="sxs-lookup"><span data-stu-id="a1c3e-187">Alt+Shift+I</span></span>
<span data-ttu-id="a1c3e-188">固定/取消固定工具（切换坞站）</span><span class="sxs-lookup"><span data-stu-id="a1c3e-188">Dock/undock tools (toggle docking)</span></span> | <span data-ttu-id="a1c3e-189">Ctrl+P</span><span class="sxs-lookup"><span data-stu-id="a1c3e-189">Ctrl+P</span></span>  
<span data-ttu-id="a1c3e-190">启动 DevTools 到 Console</span><span class="sxs-lookup"><span data-stu-id="a1c3e-190">Launch DevTools to Console</span></span> | <span data-ttu-id="a1c3e-191">Ctrl + Shift + J</span><span class="sxs-lookup"><span data-stu-id="a1c3e-191">Ctrl+Shift+J</span></span>
<span data-ttu-id="a1c3e-192">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-192">Refresh the page.</span></span> <span data-ttu-id="a1c3e-193">**注意：** 如果你在断点处进行调试和暂停，这将首先继续执行。</span><span class="sxs-lookup"><span data-stu-id="a1c3e-193">**Note:** if you're debugging and paused at a breakpoint, this resumes execution first.</span></span> | <span data-ttu-id="a1c3e-194">Ctrl + Shift + F5 或 Ctrl + R</span><span class="sxs-lookup"><span data-stu-id="a1c3e-194">Ctrl+Shift+F5 or Ctrl+R</span></span>
