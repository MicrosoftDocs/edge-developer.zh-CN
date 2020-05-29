---
description: 了解 Microsoft Edge （EdgeHTML）开发工具
title: Microsoft Edge （EdgeHTML）开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/05/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、f12 工具、devtools
experimental: true
experiment_id: 51fe4b97-3e55-41
localization_priority: Priority
ms.openlocfilehash: 56edfa3aa39fc20d37d95fb8fde029a702732336
ms.sourcegitcommit: 985cfb79a64951afd5beb7981b26afbed30a8972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "10629502"
---
# <span data-ttu-id="efd25-104">Microsoft Edge （EdgeHTML）开发人员工具</span><span class="sxs-lookup"><span data-stu-id="efd25-104">Microsoft Edge (EdgeHTML) Developer Tools</span></span>  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

<span data-ttu-id="efd25-105">Microsoft Edge \ （EdgeHTML \） DevTools 是使用[TypeScript][|::ref1::|Index]（由[开放源代码][GithubMicrosoftChakracore]支持）针对新式前端工作流进行了优化，现在可在 Microsoft Store 中以[独立 Windows 10 应用][MicrosoftStoreEdgeDevtoolsPreview]的形式提供！</span><span class="sxs-lookup"><span data-stu-id="efd25-105">The Microsoft Edge \(EdgeHTML\) DevTools are built with [TypeScript][|::ref1::|Index], powered by [open source][GithubMicrosoftChakracore], optimized for modern front-end workflows, and now available as a [standalone Windows 10 app][MicrosoftStoreEdgeDevtoolsPreview] in the Microsoft Store!</span></span>  

<span data-ttu-id="efd25-106">有关最新功能的详细信息，请查看[最新的 Windows 10 更新（EdgeHTML 18） DevTools][DevtoolsGuideEdgehtmlWhatsnew]。</span><span class="sxs-lookup"><span data-stu-id="efd25-106">For more on the latest features, check out [DevTools in the latest update of Windows 10 (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  

## <span data-ttu-id="efd25-107">核心工具</span><span class="sxs-lookup"><span data-stu-id="efd25-107">Core tools</span></span>  

:::image type="complex" source="./devtools-guide/media/devtools.png" alt-text="Microsoft Edge （EdgeHTML） DevTools":::
   <span data-ttu-id="efd25-109">Microsoft Edge （EdgeHTML） DevTools</span><span class="sxs-lookup"><span data-stu-id="efd25-109">Microsoft Edge (EdgeHTML) DevTools</span></span>
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

<span data-ttu-id="efd25-110">Microsoft Edge \ （EdgeHTML \） DevTools 包括：</span><span class="sxs-lookup"><span data-stu-id="efd25-110">The Microsoft Edge \(EdgeHTML\) DevTools include:</span></span>  

*   <span data-ttu-id="efd25-111">"[元素][DevtoolsGuideEdgehtml|::ref2::|]" 面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 转变断点</span><span class="sxs-lookup"><span data-stu-id="efd25-111">An [Elements][DevtoolsGuideEdgehtml|::ref2::|] panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="efd25-112">用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点以及在所选窗口或框架的上下文中运行 JavaScript 的[控制台][DevtoolsGuideEdgehtml|::ref3::|]</span><span class="sxs-lookup"><span data-stu-id="efd25-112">A [Console][DevtoolsGuideEdgehtml|::ref3::|] to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="efd25-113">用于逐句通过代码、设置监视和断点、实时编辑代码以及检查 web 存储和 cookie 缓存的[调试器][DevtoolsGuideEdgehtml|::ref4::|]</span><span class="sxs-lookup"><span data-stu-id="efd25-113">A [Debugger][DevtoolsGuideEdgehtml|::ref4::|] to step through code, set watches and breakpoints, live edit your code, and inspect your web storage and cookie caches</span></span>  
*   <span data-ttu-id="efd25-114">用于监视和检查来自网络和浏览器缓存的请求和响应的[网络][DevtoolsGuideEdgehtml|::ref5::|]面板</span><span class="sxs-lookup"><span data-stu-id="efd25-114">A [Network][DevtoolsGuideEdgehtml|::ref5::|] panel to monitor and inspect requests and responses from the network and browser cache</span></span>  
*   <span data-ttu-id="efd25-115">用于分析你的网站所需的时间和系统资源的[性能][DevtoolsGuideEdgehtml|::ref6::|]面板</span><span class="sxs-lookup"><span data-stu-id="efd25-115">A [Performance][DevtoolsGuideEdgehtml|::ref6::|] panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="efd25-116">测量内存资源使用情况和比较不同状态的代码运行时中的堆快照的[内存][DevtoolsGuideEdgehtml|::ref7::|]面板</span><span class="sxs-lookup"><span data-stu-id="efd25-116">A [Memory][DevtoolsGuideEdgehtml|::ref7::|] panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="efd25-117">用于检查和管理 web 存储、IndexedDB、cookie 和缓存数据的[存储][DevtoolsGuideEdgehtml|::ref8::|]面板</span><span class="sxs-lookup"><span data-stu-id="efd25-117">A [Storage][DevtoolsGuideEdgehtml|::ref8::|] panel for inspecting and managing your web storage, IndexedDB, cookies and cache data</span></span>  
*   <span data-ttu-id="efd25-118">用于管理和调试服务工作者的[服务工作者][DevtoolsGuideEdgehtmlServiceworkers]面板</span><span class="sxs-lookup"><span data-stu-id="efd25-118">A [Service Workers][DevtoolsGuideEdgehtmlServiceworkers] panel for managing and debugging your service workers</span></span>  
*   <span data-ttu-id="efd25-119">用于使用不同浏览器配置文件、屏幕分辨率和 GPS 位置坐标测试网站的[仿真][DevtoolsGuideEdgehtml|::ref9::|]面板</span><span class="sxs-lookup"><span data-stu-id="efd25-119">An [Emulation][DevtoolsGuideEdgehtml|::ref9::|] panel to test your site with different browser profiles, screen resolutions, and GPS location coordinates</span></span>  

<span data-ttu-id="efd25-120">请继续发送您的[反馈和功能请求](#feedback)！</span><span class="sxs-lookup"><span data-stu-id="efd25-120">Please keep sending your [feedback and feature requests](#feedback)!</span></span>  

> [!TIP]
> <span data-ttu-id="efd25-121">[通过任何浏览器免费在 Microsoft Edge \ （EdgeHTML \）中进行测试][BrowserstackEdgehtml]。</span><span class="sxs-lookup"><span data-stu-id="efd25-121">[Test on Microsoft Edge \(EdgeHTML\) free from any browser][BrowserstackEdgehtml].</span></span>  
> <span data-ttu-id="efd25-122">Microsoft Edge 团队与[BrowserStack][BrowserstackEdgehtml]合作，在 Microsoft Edge \ （EdgeHTML \）中提供免费实时实时和自动测试。</span><span class="sxs-lookup"><span data-stu-id="efd25-122">The Microsoft Edge team partnered with [BrowserStack][BrowserstackEdgehtml] to provide free live and automated testing on Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="efd25-123">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="efd25-123">Microsoft Store app</span></span>  

<span data-ttu-id="efd25-124">**Microsoft Edge \ （EdgeHTML \） DevTools** [现在可][DevtoolsGuideEdgehtmlWhatsnew]作为 microsoft Store 中的独立[Windows 10 应用][MicrosoftStoreEdgeDevtoolsPreview]，除了浏览器 \ （ `F12` \）工具体验。</span><span class="sxs-lookup"><span data-stu-id="efd25-124">The **Microsoft Edge \(EdgeHTML\) DevTools** are [now available][DevtoolsGuideEdgehtmlWhatsnew] as a standalone [Windows 10 app from the Microsoft Store][MicrosoftStoreEdgeDevtoolsPreview], in addition to the in-browser \(`F12`\) tooling experience.</span></span>  <span data-ttu-id="efd25-125">使用应用商店版本时，将出现一个**选择器**面板，用于附加到打开本地和远程页面目标以及选项卡式布局，以便在 DevTools 实例之间轻松切换。</span><span class="sxs-lookup"><span data-stu-id="efd25-125">With the store version comes a **chooser** panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span>  

### <span data-ttu-id="efd25-126">本地调试</span><span class="sxs-lookup"><span data-stu-id="efd25-126">Local debugging</span></span>  

<span data-ttu-id="efd25-127">若要在本地调试页面，只需启动 Microsoft Edge DevTools 应用。</span><span class="sxs-lookup"><span data-stu-id="efd25-127">To debug a page locally, simply launch the Microsoft Edge DevTools app.</span></span>  <span data-ttu-id="efd25-128">选择器的**本地**面板显示所有活动的 EdgeHTML 内容进程，包括打开的边缘浏览器选项卡、运行[PWAs][PwasEdgehtmlIndex] \ （ `WWAHost.exe` 进程 \）和[web 视图][HostingWebview]控件。</span><span class="sxs-lookup"><span data-stu-id="efd25-128">The **Local** panel of the chooser displays all of the active EdgeHTML content processes, including open Edge browser tabs, running [PWAs][PwasEdgehtmlIndex] \(`WWAHost.exe` processes\), and [webview][HostingWebview] controls.</span></span>  <span data-ttu-id="efd25-129">选择想要附加的目标，然后打开新的 DevTools 选项卡实例。</span><span class="sxs-lookup"><span data-stu-id="efd25-129">Select your desired target to attach and open a new tab instance of the DevTools.</span></span>  

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="DevTools app 本地面板":::
   <span data-ttu-id="efd25-131">DevTools app 本地面板</span><span class="sxs-lookup"><span data-stu-id="efd25-131">DevTools app Local panel</span></span>
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### <span data-ttu-id="efd25-132">远程调试</span><span class="sxs-lookup"><span data-stu-id="efd25-132">Remote debugging</span></span>  

<span data-ttu-id="efd25-133">Microsoft Edge DevTools 应用通过我们新发布的[DevTools 协议][DevtoolsProtocolEdgehtmlIndex]引入了对远程计算机上的页面调试的基本支持。</span><span class="sxs-lookup"><span data-stu-id="efd25-133">The Microsoft Edge DevTools app introduces basic support for debugging pages on a remote machine via our newly released [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex].</span></span>  <span data-ttu-id="efd25-134">使用最新版本，可远程访问[调试器][DevtoolsGuideEdgehtml|::ref10::|]、[元素][DevtoolsGuideEdgehtml|::ref11::|]\ （适用于只读操作 \）和[控制台][DevtoolsGuideEdgehtml|::ref12::|]面板中的核心功能。</span><span class="sxs-lookup"><span data-stu-id="efd25-134">With the latest release comes remote access to core functionality in the [Debugger][DevtoolsGuideEdgehtml|::ref10::|], [Elements][DevtoolsGuideEdgehtml|::ref11::|] \(for read-only operations\), and [Console][DevtoolsGuideEdgehtml|::ref12::|] panels.</span></span>  <span data-ttu-id="efd25-135">远程调试限制为运行桌面主机的 Microsoft Edge \ （EdgeHTML \），并支持未来版本中的其他 EdgeHTML 主机和 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="efd25-135">Remote debugging is limited to Microsoft Edge \(EdgeHTML\) running desktop hosts, with support for other EdgeHTML hosts and Windows 10 devices coming in future releases.</span></span>  

<span data-ttu-id="efd25-136">若要开始使用，请查看[DevTools 协议][DevtoolsProtocolEdgehtmlIndex]文档的[*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview]部分。</span><span class="sxs-lookup"><span data-stu-id="efd25-136">To get started, check out the [*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview] section of the [DevTools Protocol][DevtoolsProtocolEdgehtmlIndex] docs.</span></span>  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="DevTools 应用程序远程面板":::
   <span data-ttu-id="efd25-138">DevTools 应用程序远程面板</span><span class="sxs-lookup"><span data-stu-id="efd25-138">DevTools app Remote panel</span></span>
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## <span data-ttu-id="efd25-139">常规快捷方式</span><span class="sxs-lookup"><span data-stu-id="efd25-139">General Shortcuts</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="efd25-140">所有快捷方式均已在最新版本的 Windows 中验证。</span><span class="sxs-lookup"><span data-stu-id="efd25-140">All shortcuts have been verified in the most recent version of Windows.</span></span>  
> <span data-ttu-id="efd25-141">如果您无法使用快捷方式，请更新您的 Windows 副本。</span><span class="sxs-lookup"><span data-stu-id="efd25-141">If you are unable to use a shortcut, please update your copy of Windows.</span></span>  

<span data-ttu-id="efd25-142">这些快捷方式控制主 DevTools 窗口，并且应在所有工具中运行。</span><span class="sxs-lookup"><span data-stu-id="efd25-142">These shortcuts control the main DevTools window and should work across all tools.</span></span>  

| <span data-ttu-id="efd25-143">操作</span><span class="sxs-lookup"><span data-stu-id="efd25-143">Action</span></span> | <span data-ttu-id="efd25-144">快捷方式</span><span class="sxs-lookup"><span data-stu-id="efd25-144">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="efd25-145">显示/隐藏 DevTools \ （打开上次查看的面板 \）</span><span class="sxs-lookup"><span data-stu-id="efd25-145">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12`<span data-ttu-id="efd25-146">, `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="efd25-146">, `Ctrl`+`Shift`+</span></span>`I` |  
| <span data-ttu-id="efd25-147">切换坞站 \ （脱开/右下/右 \）</span><span class="sxs-lookup"><span data-stu-id="efd25-147">Toggle docking \(Undock/Bottom/Right\)</span></span> | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="efd25-148">打开文件</span><span class="sxs-lookup"><span data-stu-id="efd25-148">Open file</span></span> | `Ctrl`<span data-ttu-id="efd25-149">+`P`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="efd25-149">+`P`, `Ctrl`+</span></span>`O` |  
| <span data-ttu-id="efd25-150">在调试器中显示不可编辑的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="efd25-150">Show non-editable HTML source code in Debugger</span></span> | `Ctrl`+`U` |  
| <span data-ttu-id="efd25-151">在任何其他工具的底部显示/隐藏控制台</span><span class="sxs-lookup"><span data-stu-id="efd25-151">Show/hide Console at the bottom of any other tool</span></span>  | `Ctrl`+`` ` `` |  
| <span data-ttu-id="efd25-152">切换到元素 \ （DOM 资源管理器 \）</span><span class="sxs-lookup"><span data-stu-id="efd25-152">Switch to Elements \(DOM Explorer\)</span></span> | `Ctrl`+`1` |  
| <span data-ttu-id="efd25-153">切换到控制台</span><span class="sxs-lookup"><span data-stu-id="efd25-153">Switch to Console</span></span> |  `Ctrl`+`2` |  
| <span data-ttu-id="efd25-154">切换到调试器</span><span class="sxs-lookup"><span data-stu-id="efd25-154">Switch to Debugger</span></span> | `Ctrl`+`3` |  
| <span data-ttu-id="efd25-155">切换到网络</span><span class="sxs-lookup"><span data-stu-id="efd25-155">Switch to Network</span></span> | `Ctrl`+`4` |  
| <span data-ttu-id="efd25-156">切换到性能</span><span class="sxs-lookup"><span data-stu-id="efd25-156">Switch to Performance</span></span> | `Ctrl`+`5` |  
| <span data-ttu-id="efd25-157">切换到内存</span><span class="sxs-lookup"><span data-stu-id="efd25-157">Switch to Memory</span></span> | `Ctrl`+`6` |  
| <span data-ttu-id="efd25-158">切换到仿真</span><span class="sxs-lookup"><span data-stu-id="efd25-158">Switch to Emulation</span></span> | `Ctrl`+`7` |  
| <span data-ttu-id="efd25-159">帮助文档</span><span class="sxs-lookup"><span data-stu-id="efd25-159">Help Document</span></span> | `F1` |  
| <span data-ttu-id="efd25-160">下一个工具</span><span class="sxs-lookup"><span data-stu-id="efd25-160">Next tool</span></span> | `Ctrl`+`F6` |  
| <span data-ttu-id="efd25-161">上一个工具</span><span class="sxs-lookup"><span data-stu-id="efd25-161">Previous tool</span></span> | `Ctrl`+`Shift`+`F6` |  
| <span data-ttu-id="efd25-162">上一个工具 \ （来自历史记录 \）</span><span class="sxs-lookup"><span data-stu-id="efd25-162">Previous tool \(from history\)</span></span> | `Ctrl`+`Shift`+`[` |  
| <span data-ttu-id="efd25-163">下一个工具 \ （来自历史记录 \）</span><span class="sxs-lookup"><span data-stu-id="efd25-163">Next tool \(from history\)</span></span> | `Ctrl`+`Shift`+`]` |  
| <span data-ttu-id="efd25-164">下一个 Subframe</span><span class="sxs-lookup"><span data-stu-id="efd25-164">Next Subframe</span></span> | `F6` |  
| <span data-ttu-id="efd25-165">以前的 Subframe</span><span class="sxs-lookup"><span data-stu-id="efd25-165">Previous Subframe</span></span> | `Shift`+`F6` |  
| <span data-ttu-id="efd25-166">搜索框中的下一个匹配项</span><span class="sxs-lookup"><span data-stu-id="efd25-166">Next match in Search box</span></span> | `F3` |  
| <span data-ttu-id="efd25-167">搜索框中的上一个匹配项</span><span class="sxs-lookup"><span data-stu-id="efd25-167">Previous match in Search box</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="efd25-168">在搜索框中查找</span><span class="sxs-lookup"><span data-stu-id="efd25-168">Find in search box</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="efd25-169">向底部的控制台提供焦点</span><span class="sxs-lookup"><span data-stu-id="efd25-169">Give focus to console at the bottom</span></span> | `Alt`+`Shift`+`I` |  
| <span data-ttu-id="efd25-170">启动 DevTools 到 Console</span><span class="sxs-lookup"><span data-stu-id="efd25-170">Launch DevTools to Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="efd25-171">刷新页面</span><span class="sxs-lookup"><span data-stu-id="efd25-171">Refresh the page</span></span> | `Ctrl`<span data-ttu-id="efd25-172">+`Shift`+`F5`, `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="efd25-172">+`Shift`+`F5`, `Ctrl`+</span></span>`R` |  

> [!NOTE]
> <span data-ttu-id="efd25-173">如果在断点处调试和暂停，则**刷新页面**操作将首先恢复运行时。</span><span class="sxs-lookup"><span data-stu-id="efd25-173">If you are debugging and paused at a breakpoint, the **Refresh the page** action resumes the runtime first.</span></span>  

## <span data-ttu-id="efd25-174">反馈</span><span class="sxs-lookup"><span data-stu-id="efd25-174">Feedback</span></span>  

<span data-ttu-id="efd25-175">请发送反馈，帮助您改善 Microsoft Edge \ （EdgeHTML \） DevTools！</span><span class="sxs-lookup"><span data-stu-id="efd25-175">Please send your feedback to help improve the Microsoft Edge \(EdgeHTML\) DevTools for you!</span></span>  <span data-ttu-id="efd25-176">只需打开 "工具" `F12` ，然后选择 "[发送反馈](#microsoft-edge-edgehtml-developer-tools)" 按钮。</span><span class="sxs-lookup"><span data-stu-id="efd25-176">Simply open the tools \(`F12`\) and select the [Send feedback](#microsoft-edge-edgehtml-developer-tools) button.</span></span>  

<span data-ttu-id="efd25-177">成为[Windows 预览体验成员][WindowsInsiderProgram]，预览[即将 DevTools 的最新功能][DevtoolsGuideEdgehtmlWhatsnew]。</span><span class="sxs-lookup"><span data-stu-id="efd25-177">Become a [Windows Insider][WindowsInsiderProgram] to preview the [latest features coming to the DevTools][DevtoolsGuideEdgehtmlWhatsnew].</span></span>  <span data-ttu-id="efd25-178">使用 Windows 反馈中心应用对常规 Windows 建议和问题进行发布、向上投票、跟踪和获取支持。</span><span class="sxs-lookup"><span data-stu-id="efd25-178">Use the Windows Feedback Hub app to post, up-vote, track and get support for general Windows suggestions and problems.</span></span>  

<!-- image links  -->  

<!--[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge (EdgeHTML) DevTools"  -->  
<!--[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app Local panel"  -->  
<!--[ImageDevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools app Remote panel"  -->  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "控制"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "调试器"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "网元"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "仿真"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "闪存"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "网络"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "能"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "服务工作人员"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "Storage"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新 Windows 10 更新（EdgeHTML 18）中的 DevTools"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge （EdgeHTML） DevTools 协议"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[HostingWebview]: /microsoft-edge/hosting/webview "适用于 Windows 10 应用的 Web 视图（EdgeHTML）"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows 上的渐进式 Web 应用（EdgeHTML）"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools 预览"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows 预览体验计划"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge 浏览器免费测试 |BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore |GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
