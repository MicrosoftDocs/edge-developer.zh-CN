---
description: 在 Windows 10 秋季创意者更新（EdgeHTML 16）中添加到 Microsoft Edge DevTools 的功能
title: EdgeHTML 16 中的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、edgehtml 16
ms.custom: seodec18
ms.openlocfilehash: 78ede81e022cc8f0f623ecd33fd2303314ec9cb0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563438"
---
# <span data-ttu-id="692f2-104">Windows 10 秋季创意者更新中的 DevTools （EdgeHTML 16）</span><span class="sxs-lookup"><span data-stu-id="692f2-104">DevTools in the Windows 10 Fall Creators Update (EdgeHTML 16)</span></span>

<span data-ttu-id="692f2-105">在此版本中，我们为改进的可靠性和性能开始了重大 DevTools 重构工作，同时还添加了一组可开始使用今天的新功能！</span><span class="sxs-lookup"><span data-stu-id="692f2-105">With this release we started a major DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today!</span></span> 

<span data-ttu-id="692f2-106">下面是[Windows 10 秋季创意者更新](/windows/uwp/whats-new/windows-10-build-16299)（[EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)）随附的 Microsoft Edge DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="692f2-106">Here are the Microsoft Edge DevTools features that shipped with the [Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) ([EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)).</span></span>

## <span data-ttu-id="692f2-107">上级事件侦听器</span><span class="sxs-lookup"><span data-stu-id="692f2-107">Ancestor event listeners</span></span> 

<span data-ttu-id="692f2-108">"**事件**" 窗格现在添加用于查看在当前选定元素（在 "**元素**" 面板中）的任何上级上注册的事件侦听器的选项以及元素本身的任何上级。</span><span class="sxs-lookup"><span data-stu-id="692f2-108">The **Events** pane now adds the option to view event listeners registered on any ancestor of the currently selected element (in the **Elements** panel), in addition to those on the element itself.</span></span> <span data-ttu-id="692f2-109">此外，你现在可以按*事件*或*元素*对事件侦听器显示进行分组。</span><span class="sxs-lookup"><span data-stu-id="692f2-109">Additionally, you can now group the event listener display by either *Event* or *Element*.</span></span> 

![事件侦听器检查窗格](../media/elements_ancestor_events.png)

## <span data-ttu-id="692f2-111">DOM 转变断点</span><span class="sxs-lookup"><span data-stu-id="692f2-111">DOM mutation breakpoints</span></span>

<span data-ttu-id="692f2-112">现在，你可以将 DOM 转变断点设置为在所选元素节点发生更改时中断调试程序。</span><span class="sxs-lookup"><span data-stu-id="692f2-112">You can now set DOM mutation breakpoints to break into the Debugger whenever a selected element node changes.</span></span> <span data-ttu-id="692f2-113">从 "**元素**" 面板中，rt-单击 DOM 树视图中的任意元素，然后选择以下一个或多个操作：</span><span class="sxs-lookup"><span data-stu-id="692f2-113">From the **Elements** panel, rt-click on any element in the DOM tree view and select one or more of the following:</span></span>

 - <span data-ttu-id="692f2-114">删除节点上的中断</span><span class="sxs-lookup"><span data-stu-id="692f2-114">Break on Node removed</span></span>
 - <span data-ttu-id="692f2-115">已修改子树的中断</span><span class="sxs-lookup"><span data-stu-id="692f2-115">Break on Subtree modified</span></span>
 - <span data-ttu-id="692f2-116">属性被修改时中断</span><span class="sxs-lookup"><span data-stu-id="692f2-116">Break on Attribute modified</span></span>

<span data-ttu-id="692f2-117">你可以从 "**元素**" 或 "**调试器**" 面板中的 " **DOM 断点**" 窗格管理变化断点。</span><span class="sxs-lookup"><span data-stu-id="692f2-117">You can manage your mutation breakpoints from the **DOM breakpoints** pane in the **Elements** or **Debugger** panels.</span></span>

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="692f2-119">CSS at 规则支持</span><span class="sxs-lookup"><span data-stu-id="692f2-119">CSS at-rule support</span></span>

<span data-ttu-id="692f2-120">CSS "at" （@）规则现在表示在 "**样式**" 窗格上的其他 CSS 规则声明中，包括动画 `@keyframes` 规则（当前限于只读）、 `@supports` 功能查询和 `@media` 查询。</span><span class="sxs-lookup"><span data-stu-id="692f2-120">CSS "at" (@) rules are now represented among other CSS rule declarations on the **Styles** pane, including animation `@keyframes` rules (currently limited to read-only), `@supports` feature queries, and `@media` queries.</span></span>

![来自 DevTools 样式窗格的 CSS at 规则检查](../media/elements_at_rules.png)

## <span data-ttu-id="692f2-122">CSS 字体窗格</span><span class="sxs-lookup"><span data-stu-id="692f2-122">CSS fonts pane</span></span>

<span data-ttu-id="692f2-123">CSS `@font-face` 规则现在有自己的专用 "**字体**" 窗格，显示从何处加载字体（*本地*或*网络*）以及使用该字体的字符数。</span><span class="sxs-lookup"><span data-stu-id="692f2-123">CSS `@font-face` rules now have their own dedicated **Fonts** pane that displays where the font is loaded from (*Local* or *Network*) and how many characters are using it.</span></span> <span data-ttu-id="692f2-124">如果从网络加载字体，DevTools 将显示导入该字体及其别名和字体类型的规则。</span><span class="sxs-lookup"><span data-stu-id="692f2-124">If a font is loaded from the network,  DevTools will display the rule that imported it along with its alias and font type.</span></span>

![CSS 字体信息](../media/elements_fonts.png)

## <span data-ttu-id="692f2-126">CSS 伪元素支持</span><span class="sxs-lookup"><span data-stu-id="692f2-126">CSS pseudo-element support</span></span>

<span data-ttu-id="692f2-127">"**样式**" 窗格现在将伪元素分组在其自己的标题下，不再显示其内容，如带删除线。</span><span class="sxs-lookup"><span data-stu-id="692f2-127">The **Styles** pane now groups pseudo-elements under their own headings and no longer displays their content as crossed out.</span></span>

**<span data-ttu-id="692f2-128">之前：</span><span class="sxs-lookup"><span data-stu-id="692f2-128">Before:</span></span>**
<br>
![以前已删除生成的内容](../media/gc_before.png)

**<span data-ttu-id="692f2-130">之后：</span><span class="sxs-lookup"><span data-stu-id="692f2-130">After:</span></span>**
<br>
![带有删除线的生成内容不再显示](../media/gc_after.png)

## <span data-ttu-id="692f2-132">增强了控制台</span><span class="sxs-lookup"><span data-stu-id="692f2-132">Console improvements</span></span>

<span data-ttu-id="692f2-133">**控制台**面板为提高可用性和更快、更丰富的智能感知体验获得了 UX</span><span class="sxs-lookup"><span data-stu-id="692f2-133">The **Console** panel got a UX overhaul for improved usability and a faster, richer Intellisense experience.</span></span>

<span data-ttu-id="692f2-134">**之前：** 
![以前的控制台</span><span class="sxs-lookup"><span data-stu-id="692f2-134">**Before:**
![Previous console</span></span>](../media/console_old.png)

<span data-ttu-id="692f2-135">**在：** 
![新的控制台</span><span class="sxs-lookup"><span data-stu-id="692f2-135">**After:**
![New console</span></span>](../media/console_new.png)

<span data-ttu-id="692f2-136">我们还添加了以下改进：</span><span class="sxs-lookup"><span data-stu-id="692f2-136">We also added these improvements:</span></span>

 -  <span data-ttu-id="692f2-137">用于 `Shift + Enter` 在执行命令前将另一行添加到命令 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="692f2-137">Use `Shift + Enter` to add an additional line to a command before executing it with `Enter`.</span></span> <span data-ttu-id="692f2-138">（以前有一个*切换到多行/单行模式*切换按钮。）</span><span class="sxs-lookup"><span data-stu-id="692f2-138">(Formerly there was a *Switch to multiline/single-line mode* toggle button.)</span></span>

 - <span data-ttu-id="692f2-139">以下新 Api 受支持：</span><span class="sxs-lookup"><span data-stu-id="692f2-139">The following new APIs are supported:</span></span>
    - <span data-ttu-id="692f2-140">[**console. table （***object***）**](../console/console-api.md#organizing-log-output)方法</span><span class="sxs-lookup"><span data-stu-id="692f2-140">[**console.table(***object***)**](../console/console-api.md#organizing-log-output) method</span></span>
    - <span data-ttu-id="692f2-141">[**getEventListeners （***object***）**](../console/command-line.md#event-listeners)命令</span><span class="sxs-lookup"><span data-stu-id="692f2-141">[**getEventListeners(***object***)**](../console/command-line.md#event-listeners) command</span></span>
    - <span data-ttu-id="692f2-142">[**键（***对象***）**](../console/command-line.md#object-inspection)命令</span><span class="sxs-lookup"><span data-stu-id="692f2-142">[**keys(***object***)**](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="692f2-143">[**values （***object***）**](../console/command-line.md#object-inspection)命令</span><span class="sxs-lookup"><span data-stu-id="692f2-143">[**values(***object***)**](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="692f2-144">[**$x （***xpath 表达式***）**](../console/command-line.md#dom-selectors)选择器</span><span class="sxs-lookup"><span data-stu-id="692f2-144">[**$x(***xpath expression***)**](../console/command-line.md#dom-selectors) selector</span></span>

 - <span data-ttu-id="692f2-145">[**% C （）**](../console/console-api.md#logging-custom-messages)格式参数现在受支持</span><span class="sxs-lookup"><span data-stu-id="692f2-145">The [**%c()**](../console/console-api.md#logging-custom-messages) formatting parameter is now supported</span></span>

## <span data-ttu-id="692f2-146">调试改进</span><span class="sxs-lookup"><span data-stu-id="692f2-146">Debugging improvements</span></span>

<span data-ttu-id="692f2-147">除了用于调试[PWA 服务工作人员和缓存](#progressive-web-app-debugging)的一组新功能之外，调试器还添加了这些功能：</span><span class="sxs-lookup"><span data-stu-id="692f2-147">In addition to a suite of new features for debugging your [PWA service workers and cache](#progressive-web-app-debugging), the Debugger added these features:</span></span>

### <span data-ttu-id="692f2-148">共享资源的合并调试</span><span class="sxs-lookup"><span data-stu-id="692f2-148">Consolidated debugging for shared resources</span></span>

<span data-ttu-id="692f2-149">即使在你的代码中多次引用某个资源（如从 CDN 加载的文件），DevTools 现在也会为该文件提供单个调试实例，你可以在该文件中设置将命中的常用断点，而不管该文件的引用位置。</span><span class="sxs-lookup"><span data-stu-id="692f2-149">Even when a resource, such as a file loaded from CDN, is referenced multiple times throughout your code,  DevTools will now provide a single debugging instance for that file where you can then set common breakpoints which will be hit regardless of where that file is referenced.</span></span> <span data-ttu-id="692f2-150">（之前的每个脚本引用均被视为唯一资源将映射到单独的一组断点。）</span><span class="sxs-lookup"><span data-stu-id="692f2-150">(Previously each script reference was considered a unique resource would map to a separate set of breakpoints.)</span></span>

### <span data-ttu-id="692f2-151">实时编辑 JavaScript 和 *"空闲时编辑"*</span><span class="sxs-lookup"><span data-stu-id="692f2-151">Live edit JavaScript with *Edit-on-idle*</span></span>

<span data-ttu-id="692f2-152">现在，你可以在调试会话期间编辑 JavaScript live。</span><span class="sxs-lookup"><span data-stu-id="692f2-152">You can now edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="692f2-153">此功能在[上](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97)一个（*Windows 10 创意者更新*）版本中 experimentally 可用（在标志后面），现在是永久性的功能。</span><span class="sxs-lookup"><span data-stu-id="692f2-153">This feature was experimentally available (behind a flag) in the [previous](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) (*Windows 10 Creators Update*) release and now its a permanent feature.</span></span> <span data-ttu-id="692f2-154">只需从 "**调试器**" 面板中选择任意脚本文件，然后单击 "**保存**" （或 `Ctrl+S` ）以在下次运行该代码段时测试所做的更改。</span><span class="sxs-lookup"><span data-stu-id="692f2-154">Simply select any script file from the **Debugger** panel, edit, then click **Save** (or `Ctrl+S`) to test your changes next time that section of code runs.</span></span> 

![调试器使你能够实时编辑脚本并比较更改](../media/debugger_edit_buttons.png) 

<span data-ttu-id="692f2-156">单击 "**将文档与原始文档比较**" 按钮以查看更改内容的差异。</span><span class="sxs-lookup"><span data-stu-id="692f2-156">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![调试器中编辑代码的比较视图](../media/debugger_edit_code.png) 

<span data-ttu-id="692f2-158">请注意以下限制：</span><span class="sxs-lookup"><span data-stu-id="692f2-158">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="692f2-159">脚本编辑仅适用于外部 *.js*文件（而不是嵌入 `<script>` 在 *.html*中）</span><span class="sxs-lookup"><span data-stu-id="692f2-159">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="692f2-160">编辑保存在内存中，并在重新加载文档时进行刷新，因此你无法在处理程序内运行编辑 `DOMContentLoaded` ，例如</span><span class="sxs-lookup"><span data-stu-id="692f2-160">Edits are saved in memory and flushed when the document is reloaded, thus you won’t be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="692f2-161">目前没有办法（如 "**另存为**" 选项）将您的编辑内容从 DevTools 保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="692f2-161">Currently there’s no way (such as a **Save As** option) to save your edits to disk from  DevTools</span></span>

## <span data-ttu-id="692f2-162">指向</span><span class="sxs-lookup"><span data-stu-id="692f2-162">Shortcuts</span></span>

<span data-ttu-id="692f2-163">现在，你可以在最后一次查看的面板（）上启动 DevTools， `Ctrl+Shift+I` 也可以直接在控制台（）中启动它， `Ctrl+Shift+J` 就像在其他主流浏览器上一样。</span><span class="sxs-lookup"><span data-stu-id="692f2-163">You can now launch DevTools to the last viewed panel (`Ctrl+Shift+I`) or directly to the Console (`Ctrl+Shift+J`) just like you would on other major browsers.</span></span>

## <span data-ttu-id="692f2-164">渐进 Web 应用调试</span><span class="sxs-lookup"><span data-stu-id="692f2-164">Progressive Web App debugging</span></span>

<span data-ttu-id="692f2-165">通过从（和重启 Microsoft Edge）中选择 "**启用服务工作线程**" 选项，在 Microsoft Edge 和 DevTools 中测试累进 Web Apps （PWAs）的实验性支持 `about:flags` 。</span><span class="sxs-lookup"><span data-stu-id="692f2-165">Test out the experimental support for Progressive Web Apps (PWAs) in Microsoft Edge and  DevTools by selecting the **Enable service workers** option from `about:flags` (and restarting Microsoft Edge).</span></span> <span data-ttu-id="692f2-166">如果网站使用**服务工作者**和/或**缓存**API，将在**调试器**面板中为每个源填充条目，类似于 web 存储和 cookie 检查的工作方式。</span><span class="sxs-lookup"><span data-stu-id="692f2-166">If a site makes use of **Service Workers** and/or the **Cache** API,  will populate entries in the **Debugger** panel for each origin, similar to how web storage and cookie inspection work.</span></span>

<span data-ttu-id="692f2-167">单击特定的服务工作人员条目将打开 "**服务工作人员" 概览**，您可以在其中管理给定范围的服务工作人员注册并强制实施测试推送通知。</span><span class="sxs-lookup"><span data-stu-id="692f2-167">Clicking on a specific service worker entry will open up the **Service Worker Overview**, where you can manage the service worker registration for the given scope and force a test push notification.</span></span> <span data-ttu-id="692f2-168">您还可以**停止** / **启动**单个服务工作人员并从单独的调试器窗口**检查**它们：</span><span class="sxs-lookup"><span data-stu-id="692f2-168">You can also **Stop**/**Start** individual service workers and **Inspect** them from a separate debugger window:</span></span>

![服务工作人员概述窗格](../media/debugger_sw_overview.png)

<span data-ttu-id="692f2-170">请注意以下有关服务工作者调试的信息：</span><span class="sxs-lookup"><span data-stu-id="692f2-170">Please note the following about service worker debugging:</span></span>

 - <span data-ttu-id="692f2-171">调试服务工作人员将启动与页面工具分开的 DevTools 的新实例，因为服务工作人员可以在多个选项卡之间共享。</span><span class="sxs-lookup"><span data-stu-id="692f2-171">Debugging a service worker will launch a new instance of the DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span> 
 - <span data-ttu-id="692f2-172">如果服务工作者在后台运行，并且不直接控制应用的前端，则服务工作器调试器中不存在[元素](../elements.md)和[仿真](../emulation.md)面板。</span><span class="sxs-lookup"><span data-stu-id="692f2-172">The [Elements](../elements.md) and [Emulation](../emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="692f2-173">当前，服务工作者的网络流量仅从该工作人员的 DevTools 调试实例，而不是从页面本身的中央实例中报告。</span><span class="sxs-lookup"><span data-stu-id="692f2-173">Currently network traffic for a service worker is only reported from the DevTools debugging instance for that worker, and not from the central instance for the page itself.</span></span>

<span data-ttu-id="692f2-174">单击特定的缓存条目将打开**缓存**管理器，您可以在其中检查和删除缓存条目（*请求*和*响应*键/值对）。</span><span class="sxs-lookup"><span data-stu-id="692f2-174">Clicking on a specific cache entry will open up the **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs).</span></span>