---
description: 了解 Microsoft Edge (EdgeHTML) Developer Tools
title: Microsoft Edge (EdgeHTML) Developer Tools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/10/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 开发, f12 工具, devtools
experimental: true
experiment_id: 51fe4b97-3e55-41
ms.localizationpriority: high
ms.openlocfilehash: cba59764805c0be0e9d2c57c1a3d87ca4d14943e
ms.sourcegitcommit: 1e33cd41e5afb2e6dbdc19353011ff6c2b019f9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2020
ms.locfileid: "10866069"
---
# <span data-ttu-id="2d8f4-104">Microsoft Edge (EdgeHTML) Developer Tools</span><span class="sxs-lookup"><span data-stu-id="2d8f4-104">Microsoft Edge (EdgeHTML) Developer Tools</span></span>  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

<span data-ttu-id="2d8f4-105">Microsoft Edge \(EdgeHTML\) DevTools 是使用 [TypeScript][|::ref1::|Index] 构建的，由[开放源代码][GithubMicrosoftChakracore]提供支持，并已针对新式前端工作流进行了优化，当前在 Microsoft Store 中作为[独立 Windows 10 应用][MicrosoftStoreEdgeDevtoolsPreview]提供！</span><span class="sxs-lookup"><span data-stu-id="2d8f4-105">The Microsoft Edge \(EdgeHTML\) DevTools are built with [TypeScript][|::ref1::|Index], powered by [open source][GithubMicrosoftChakracore], optimized for modern front-end workflows, and now available as a [standalone Windows 10 app][MicrosoftStoreEdgeDevtoolsPreview] in the Microsoft Store!</span></span>  

<span data-ttu-id="2d8f4-106">有关最新功能的详细信息，请参阅 [Windows 10 最新更新中的 DevTools (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew]。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-106">For more on the latest features, check out [DevTools in the latest update of Windows 10 (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  

## <span data-ttu-id="2d8f4-107">核心工具</span><span class="sxs-lookup"><span data-stu-id="2d8f4-107">Core tools</span></span>  

:::image type="complex" source="./devtools-guide/media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
   <span data-ttu-id="2d8f4-109">Microsoft Edge (EdgeHTML) DevTools</span><span class="sxs-lookup"><span data-stu-id="2d8f4-109">Microsoft Edge (EdgeHTML) DevTools</span></span>
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

<span data-ttu-id="2d8f4-110">Microsoft Edge \(EdgeHTML\) DevTools 包括：</span><span class="sxs-lookup"><span data-stu-id="2d8f4-110">The Microsoft Edge \(EdgeHTML\) DevTools include:</span></span>  

*   <span data-ttu-id="2d8f4-111">“[元素][DevtoolsGuideEdgehtml|::ref2::|]”面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 变化断点</span><span class="sxs-lookup"><span data-stu-id="2d8f4-111">An [Elements][DevtoolsGuideEdgehtml|::ref2::|] panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="2d8f4-112">[控制台][DevtoolsGuideEdgehtml|::ref3::|]，用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点，并在所选窗口或框架的上下文中运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="2d8f4-112">A [Console][DevtoolsGuideEdgehtml|::ref3::|] to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="2d8f4-113">[调试程序][DevtoolsGuideEdgehtml|::ref4::|]，用于逐步执行代码、设置监视和断点、实时编辑代码以及检查 Web 存储和 Cookie 缓存</span><span class="sxs-lookup"><span data-stu-id="2d8f4-113">A [Debugger][DevtoolsGuideEdgehtml|::ref4::|] to step through code, set watches and breakpoints, live edit your code, and inspect your web storage and cookie caches</span></span>  
*   <span data-ttu-id="2d8f4-114">“[网络][DevtoolsGuideEdgehtml|::ref5::|]”面板，用于从网络和浏览器缓存监视和检查请求和响应</span><span class="sxs-lookup"><span data-stu-id="2d8f4-114">A [Network][DevtoolsGuideEdgehtml|::ref5::|] panel to monitor and inspect requests and responses from the network and browser cache</span></span>  
*   <span data-ttu-id="2d8f4-115">“[性能][DevtoolsGuideEdgehtml|::ref6::|]”面板，用于分析网站所需的时间和系统资源</span><span class="sxs-lookup"><span data-stu-id="2d8f4-115">A [Performance][DevtoolsGuideEdgehtml|::ref6::|] panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="2d8f4-116">“[内存][DevtoolsGuideEdgehtml|::ref7::|]”面板，用于衡量内存资源的使用情况，并比较代码运行时的不同状态下的堆快照</span><span class="sxs-lookup"><span data-stu-id="2d8f4-116">A [Memory][DevtoolsGuideEdgehtml|::ref7::|] panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="2d8f4-117">“[存储][DevtoolsGuideEdgehtml|::ref8::|]”面板，用于检查和管理 Web 存储、IndexedDB、Cookie 和缓存数据</span><span class="sxs-lookup"><span data-stu-id="2d8f4-117">A [Storage][DevtoolsGuideEdgehtml|::ref8::|] panel for inspecting and managing your web storage, IndexedDB, cookies and cache data</span></span>  
*   <span data-ttu-id="2d8f4-118">“[服务工作进程][DevtoolsGuideEdgehtmlServiceworkers]”面板，用于管理和调试服务工作进程</span><span class="sxs-lookup"><span data-stu-id="2d8f4-118">A [Service Workers][DevtoolsGuideEdgehtmlServiceworkers] panel for managing and debugging your service workers</span></span>  
*   <span data-ttu-id="2d8f4-119">“[枚举][DevtoolsGuideEdgehtml|::ref9::|]”面板，可使用不同的浏览器配置文件、屏幕分辨率和 GPS 位置坐标来测试网站</span><span class="sxs-lookup"><span data-stu-id="2d8f4-119">An [Emulation][DevtoolsGuideEdgehtml|::ref9::|] panel to test your site with different browser profiles, screen resolutions, and GPS location coordinates</span></span>  

<span data-ttu-id="2d8f4-120">请继续发送你的[反馈和功能请求](#feedback)！</span><span class="sxs-lookup"><span data-stu-id="2d8f4-120">Please keep sending your [feedback and feature requests](#feedback)!</span></span>  

> [!TIP]
> <span data-ttu-id="2d8f4-121">[从任何浏览器免费测试 Microsoft Edge \(EdgeHTML)][BrowserstackEdgehtml]。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-121">[Test on Microsoft Edge \(EdgeHTML\) free from any browser][BrowserstackEdgehtml].</span></span>  
> <span data-ttu-id="2d8f4-122">Microsoft Edge 团队与 [BrowserStack][BrowserstackEdgehtml] 合作，在 Microsoft Edge \(EdgeHTML) 上提供免费的实时和自动化测试。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-122">The Microsoft Edge team partnered with [BrowserStack][BrowserstackEdgehtml] to provide free live and automated testing on Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="2d8f4-123">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="2d8f4-123">Microsoft Store app</span></span>  

<span data-ttu-id="2d8f4-124">除了浏览器内 \(`F12`\) 工具体验之前，**Microsoft Edge \(EdgeHTML\) DevTools** 当前还作为独立 [Windows 10 应用在 [Microsoft Store][DevtoolsGuideEdgehtmlWhatsnew] 上提供][MicrosoftStoreEdgeDevtoolsPreview]。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-124">The **Microsoft Edge \(EdgeHTML\) DevTools** are [now available][DevtoolsGuideEdgehtmlWhatsnew] as a standalone [Windows 10 app from the Microsoft Store][MicrosoftStoreEdgeDevtoolsPreview], in addition to the in-browser \(`F12`\) tooling experience.</span></span>  <span data-ttu-id="2d8f4-125">应用商店版本提供了一个**选择器**面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-125">With the store version comes a **chooser** panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span>  

### <span data-ttu-id="2d8f4-126">本地调试</span><span class="sxs-lookup"><span data-stu-id="2d8f4-126">Local debugging</span></span>  

<span data-ttu-id="2d8f4-127">若要在本地调试页面，只需启动 Microsoft Edge DevTools 应用。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-127">To debug a page locally, simply launch the Microsoft Edge DevTools app.</span></span>  <span data-ttu-id="2d8f4-128">选择器的“**本地**”面板将显示所有活动的 EdgeHTML 内容进程，包括打开的 Edge 浏览器选项卡、运行的 [PWA][PwasEdgehtmlIndex]\（`WWAHost.exe` 进程\）和 [webview][HostingWebview] 控件。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-128">The **Local** panel of the chooser displays all of the active EdgeHTML content processes, including open Edge browser tabs, running [PWAs][PwasEdgehtmlIndex] \(`WWAHost.exe` processes\), and [webview][HostingWebview] controls.</span></span>  <span data-ttu-id="2d8f4-129">选择所需目标，并打开 DevTools 的新选项卡实例。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-129">Select your desired target to attach and open a new tab instance of the DevTools.</span></span>  

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="DevTools 应用的“本地”面板":::
   <span data-ttu-id="2d8f4-131">DevTools 应用的“本地”面板</span><span class="sxs-lookup"><span data-stu-id="2d8f4-131">DevTools app Local panel</span></span>
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### <span data-ttu-id="2d8f4-132">远程调试</span><span class="sxs-lookup"><span data-stu-id="2d8f4-132">Remote debugging</span></span>  

<span data-ttu-id="2d8f4-133">Microsoft Edge DevTools 应用引入了对通过我们最新发布的 [DevTools 协议][DevtoolsProtocolEdgehtmlIndex]在远程计算机上调试页面的基本支持。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-133">The Microsoft Edge DevTools app introduces basic support for debugging pages on a remote machine via our newly released [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex].</span></span>  <span data-ttu-id="2d8f4-134">在最新版本中，可以远程访问“[调试程序][DevtoolsGuideEdgehtml|::ref10::|]”、“[元素][DevtoolsGuideEdgehtml|::ref11::|]”（用于只读操作）和“[控制台][DevtoolsGuideEdgehtml|::ref12::|]”面板中的核心功能。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-134">With the latest release comes remote access to core functionality in the [Debugger][DevtoolsGuideEdgehtml|::ref10::|], [Elements][DevtoolsGuideEdgehtml|::ref11::|] \(for read-only operations\), and [Console][DevtoolsGuideEdgehtml|::ref12::|] panels.</span></span>  <span data-ttu-id="2d8f4-135">远程调试仅限于运行桌面主机的 Microsoft Edge \(EdgeHTML\)，将来的版本将支持其他 EdgeHTML 主机和 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-135">Remote debugging is limited to Microsoft Edge \(EdgeHTML\) running desktop hosts, with support for other EdgeHTML hosts and Windows 10 devices coming in future releases.</span></span>  

<span data-ttu-id="2d8f4-136">若要开始，请查看“[DevTools 协议][DevtoolsProtocolEdgehtmlIndex]”文档的“[*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview]”部分。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-136">To get started, check out the [*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview] section of the [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex] docs.</span></span>  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="DevTools 应用“远程”面板":::
   <span data-ttu-id="2d8f4-138">DevTools 应用“远程”面板</span><span class="sxs-lookup"><span data-stu-id="2d8f4-138">DevTools app Remote panel</span></span>
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## <span data-ttu-id="2d8f4-139">常规快捷方式</span><span class="sxs-lookup"><span data-stu-id="2d8f4-139">General Shortcuts</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="2d8f4-140">所有快捷方式都已在最新 Windows 版本中验证。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-140">All shortcuts have been verified in the most recent version of Windows.</span></span>  
> <span data-ttu-id="2d8f4-141">如果无法使用快捷方式，请更新你的 Windows 副本。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-141">If you are unable to use a shortcut, please update your copy of Windows.</span></span>  

<span data-ttu-id="2d8f4-142">这些快捷方式控制主 DevTools 窗口，并应在所有工具中正常工作。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-142">These shortcuts control the main DevTools window and should work across all tools.</span></span>  

| <span data-ttu-id="2d8f4-143">操作</span><span class="sxs-lookup"><span data-stu-id="2d8f4-143">Action</span></span> | <span data-ttu-id="2d8f4-144">快捷方式</span><span class="sxs-lookup"><span data-stu-id="2d8f4-144">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="2d8f4-145">显示/隐藏 DevTools\（打开至上次查看的面板\）</span><span class="sxs-lookup"><span data-stu-id="2d8f4-145">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12`<span data-ttu-id="2d8f4-146">, `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="2d8f4-146">, `Ctrl`+`Shift`+</span></span>`I` |  
| <span data-ttu-id="2d8f4-147">切换扩展连接\（移除/下/右\）</span><span class="sxs-lookup"><span data-stu-id="2d8f4-147">Toggle docking \(Undock/Bottom/Right\)</span></span> | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="2d8f4-148">打开文件</span><span class="sxs-lookup"><span data-stu-id="2d8f4-148">Open file</span></span> | `Ctrl`<span data-ttu-id="2d8f4-149">+`P`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="2d8f4-149">+`P`, `Ctrl`+</span></span>`O` |  
| <span data-ttu-id="2d8f4-150">在调试程序中显示不可编辑的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="2d8f4-150">Show non-editable HTML source code in Debugger</span></span> | `Ctrl`+`U` |  
| <span data-ttu-id="2d8f4-151">在任何其他工具底部显示/隐藏“控制台”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-151">Show/hide Console at the bottom of any other tool</span></span>  | `Ctrl`+`` ` `` |  
| <span data-ttu-id="2d8f4-152">切换到“元素”\（DOM 资源管理器\）</span><span class="sxs-lookup"><span data-stu-id="2d8f4-152">Switch to Elements \(DOM Explorer\)</span></span> | `Ctrl`+`1` |  
| <span data-ttu-id="2d8f4-153">切换到“控制台”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-153">Switch to Console</span></span> |  `Ctrl`+`2` |  
| <span data-ttu-id="2d8f4-154">切换到“调试程序”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-154">Switch to Debugger</span></span> | `Ctrl`+`3` |  
| <span data-ttu-id="2d8f4-155">切换到“网络”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-155">Switch to Network</span></span> | `Ctrl`+`4` |  
| <span data-ttu-id="2d8f4-156">切换到“性能”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-156">Switch to Performance</span></span> | `Ctrl`+`5` |  
| <span data-ttu-id="2d8f4-157">切换到“内存”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-157">Switch to Memory</span></span> | `Ctrl`+`6` |  
| <span data-ttu-id="2d8f4-158">切换到“枚举”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-158">Switch to Emulation</span></span> | `Ctrl`+`7` |  
| <span data-ttu-id="2d8f4-159">帮助文档</span><span class="sxs-lookup"><span data-stu-id="2d8f4-159">Help Document</span></span> | `F1` |  
| <span data-ttu-id="2d8f4-160">下一个工具</span><span class="sxs-lookup"><span data-stu-id="2d8f4-160">Next tool</span></span> | `Ctrl`+`F6` |  
| <span data-ttu-id="2d8f4-161">上一个工具</span><span class="sxs-lookup"><span data-stu-id="2d8f4-161">Previous tool</span></span> | `Ctrl`+`Shift`+`F6` |  
| <span data-ttu-id="2d8f4-162">上一个工具\（来自历史记录\）</span><span class="sxs-lookup"><span data-stu-id="2d8f4-162">Previous tool \(from history\)</span></span> | `Ctrl`+`Shift`+`[` |  
| <span data-ttu-id="2d8f4-163">下一个工具\（来自历史记录\）</span><span class="sxs-lookup"><span data-stu-id="2d8f4-163">Next tool \(from history\)</span></span> | `Ctrl`+`Shift`+`]` |  
| <span data-ttu-id="2d8f4-164">下一个子框架</span><span class="sxs-lookup"><span data-stu-id="2d8f4-164">Next Subframe</span></span> | `F6` |  
| <span data-ttu-id="2d8f4-165">上一个子框架</span><span class="sxs-lookup"><span data-stu-id="2d8f4-165">Previous Subframe</span></span> | `Shift`+`F6` |  
| <span data-ttu-id="2d8f4-166">搜索框中的下一个匹配项</span><span class="sxs-lookup"><span data-stu-id="2d8f4-166">Next match in Search box</span></span> | `F3` |  
| <span data-ttu-id="2d8f4-167">搜索框中的上一个匹配项</span><span class="sxs-lookup"><span data-stu-id="2d8f4-167">Previous match in Search box</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="2d8f4-168">在搜索框中查找</span><span class="sxs-lookup"><span data-stu-id="2d8f4-168">Find in search box</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="2d8f4-169">将焦点放在底部的控制台上</span><span class="sxs-lookup"><span data-stu-id="2d8f4-169">Give focus to console at the bottom</span></span> | `Alt`+`Shift`+`I` |  
| <span data-ttu-id="2d8f4-170">启动 DevTools 到“控制台”</span><span class="sxs-lookup"><span data-stu-id="2d8f4-170">Launch DevTools to Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="2d8f4-171">刷新页面</span><span class="sxs-lookup"><span data-stu-id="2d8f4-171">Refresh the page</span></span> | `Ctrl`<span data-ttu-id="2d8f4-172">+`Shift`+`F5`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="2d8f4-172">+`Shift`+`F5`, `Ctrl`+</span></span>`R` |  

> [!NOTE]
> <span data-ttu-id="2d8f4-173">如果你正在调试并在断点处暂停，则“**刷新页面**”操作会首先恢复运行时。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-173">If you are debugging and paused at a breakpoint, the **Refresh the page** action resumes the runtime first.</span></span>  

## <span data-ttu-id="2d8f4-174">反馈</span><span class="sxs-lookup"><span data-stu-id="2d8f4-174">Feedback</span></span>  

<span data-ttu-id="2d8f4-175">请发送你的反馈以帮助改进 Microsoft Edge \(EdgeHTML\) DevTools！</span><span class="sxs-lookup"><span data-stu-id="2d8f4-175">Please send your feedback to help improve the Microsoft Edge \(EdgeHTML\) DevTools for you!</span></span>  <span data-ttu-id="2d8f4-176">只需打开工具 \(`F12`\) 并选择“[发送反馈](#microsoft-edge-edgehtml-developer-tools)”按钮。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-176">Simply open the tools \(`F12`\) and select the [Send feedback](#microsoft-edge-edgehtml-developer-tools) button.</span></span>  

<span data-ttu-id="2d8f4-177">成为 [Windows 预览体验成员][WindowsInsiderProgram]，预览[即将推出的 DevTools 最新功能][DevtoolsGuideEdgehtmlWhatsnew]。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-177">Become a [Windows Insider][WindowsInsiderProgram] to preview the [latest features coming to the DevTools][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  <span data-ttu-id="2d8f4-178">使用 Windows 反馈中心应用发布、投票、跟踪和获取对常规 Windows 建议和问题的支持。</span><span class="sxs-lookup"><span data-stu-id="2d8f4-178">Use the Windows Feedback Hub app to post, up-vote, track and get support for general Windows suggestions and problems.</span></span>  

<!-- image links  -->  

<!--[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge (EdgeHTML) DevTools"  -->  
<!--[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app Local panel"  -->  
<!--[ImageDevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools app Remote panel"  -->  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "控制台"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "调试程序"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "元素"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "枚举"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "内存"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "网络"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "性能"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "服务工作进程"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "存储"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新 Windows 10 更新中的 DevTools (EdgeHTML 18)"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) DevTools 协议"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 应用的 WebView (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows 上的渐进式 Web 应用 (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools 预览版"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows 预览体验计划"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge 浏览器免费测试 | BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore | GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
