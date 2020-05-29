---
description: 在用户交互期间使用 "性能" 面板分析页面的 responsivenes
title: DevTools-性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、性能、配置文件、帧速率、fps、CPU 使用率、JavaScript 执行
ms.custom: seodec18
ms.openlocfilehash: aecf3cf49592dbf1f24231e76f14ddc2ca1228c3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563475"
---
# <span data-ttu-id="73d08-104">性能</span><span class="sxs-lookup"><span data-stu-id="73d08-104">Performance</span></span>

<span data-ttu-id="73d08-105">"**性能**" 面板提供了用于分析和分析用户交互期间的 UI 响应的工具。</span><span class="sxs-lookup"><span data-stu-id="73d08-105">The **Performance** panel offers tools for profiling and analyzing the responsiveness of your UI during the course of user interaction.</span></span> <span data-ttu-id="73d08-106">有了它，您可以：</span><span class="sxs-lookup"><span data-stu-id="73d08-106">With it, you can:</span></span>

 - <span data-ttu-id="73d08-107">测量页面各个组件的[执行时间](#recording-a-profile)</span><span class="sxs-lookup"><span data-stu-id="73d08-107">[Measure execution times](#recording-a-profile) of the various components of your page</span></span> 
 - <span data-ttu-id="73d08-108">向[下钻取到你要花费最多 CPU 周期的位置](#timeline-ruler)，以运行你的页面和你的用户的结果视觉效果</span><span class="sxs-lookup"><span data-stu-id="73d08-108">[Drill down to where you're spending the most CPU cycles](#timeline-ruler) to run your page and the resulting visual effect for your users</span></span>
 - <span data-ttu-id="73d08-109">[获取](#timeline-details)消耗页面执行时间的进程的分步细分</span><span class="sxs-lookup"><span data-stu-id="73d08-109">[Get a step-by-step breakdown of the processes](#timeline-details) consuming page execution time</span></span> 
 - <span data-ttu-id="73d08-110">[遍历 JavaScript 调用堆栈](#javascript-call-stacks)以标识成本高昂的操作，例如那些需要布局重新计算的操作</span><span class="sxs-lookup"><span data-stu-id="73d08-110">[Walk your JavaScript call stacks](#javascript-call-stacks) to identify costly operations, such as those requiring layout recalculations</span></span> 

![DevTools 性能面板](./media/performance.png)

## <span data-ttu-id="73d08-112">录制配置文件</span><span class="sxs-lookup"><span data-stu-id="73d08-112">Recording a profile</span></span>

<span data-ttu-id="73d08-113">分析页面性能的第一步是在执行特定用户方案（如尝试修复的性能 bug 的重现步骤）中捕获配置文件，或者想要为获得更好的用户体验而优化的典型使用情形。</span><span class="sxs-lookup"><span data-stu-id="73d08-113">The first step to analyzing the performance of your page is to capture a profile as you perform a particular user scenario, such as the repro steps of a performance bug you're trying to fix, or a typical use case you want to optimize for a better user experience.</span></span> 

### <span data-ttu-id="73d08-114">工具栏</span><span class="sxs-lookup"><span data-stu-id="73d08-114">Toolbar</span></span>

<span data-ttu-id="73d08-115">使用工具栏上的 "**开始**  /  **停止**" 按钮（或 `Ctrl+E` ）启动并结束性能跟踪。</span><span class="sxs-lookup"><span data-stu-id="73d08-115">Use the **Start** / **Stop** buttons on the toolbar (or `Ctrl+E`) to initiate and conclude your performance trace.</span></span> <span data-ttu-id="73d08-116">绿色指示器将在 "**性能**" 选项卡上显示，指示正在进行录制。</span><span class="sxs-lookup"><span data-stu-id="73d08-116">A green indicator will apear on the **Performance** tab to indicate a recording is in progress.</span></span> 

![性能面板工具栏](./media/performance_toolbar.png)

<span data-ttu-id="73d08-118">性能报告将在停止配置文件时生成。</span><span class="sxs-lookup"><span data-stu-id="73d08-118">A performance report will generate upon stopping the profile.</span></span> <span data-ttu-id="73d08-119">你可以选择将其保存到 disk （ `Ctrl+S` ），稍后再 `Ctrl+O` 在 DevTools 中重新加载（）。</span><span class="sxs-lookup"><span data-stu-id="73d08-119">You can choose to save it to disk (`Ctrl+S`) and reload (`Ctrl+O`) in  DevTools at a later time.</span></span>  <span data-ttu-id="73d08-120">DevTools 诊断会话将以*diagsession*扩展名保存。</span><span class="sxs-lookup"><span data-stu-id="73d08-120">DevTools diagnostic sessions are saved with the *.diagsession* extension.</span></span>

<span data-ttu-id="73d08-121">以下是录制配置文件时需要记住的一些事项：</span><span class="sxs-lookup"><span data-stu-id="73d08-121">Here are some things to keep in mind when recording a profile:</span></span>

- <span data-ttu-id="73d08-122">执行捕获你要分析的方案所需的最少操作。</span><span class="sxs-lookup"><span data-stu-id="73d08-122">Perform the fewest actions you need to capture the scenario you're trying to analyze.</span></span> <span data-ttu-id="73d08-123">页面上的无关操作将产生额外的数据并令您的结果混乱。</span><span class="sxs-lookup"><span data-stu-id="73d08-123">Extraneous actions with the page will produce extra data and clutter your results.</span></span>

- <span data-ttu-id="73d08-124">探查器将自动标记报表中的主要应用生命周期事件，例如页面导航、 [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面[加载](https://developer.mozilla.org/docs/Web/Events/load)。</span><span class="sxs-lookup"><span data-stu-id="73d08-124">The profiler will automatically mark major app lifecycle events in the report, such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load).</span></span> <span data-ttu-id="73d08-125">你可以通过从你的代码或控制台中调用[Performance （）](https://developer.mozilla.org/docs/Web/API/Performance/mark)方法来添加自定义标记。</span><span class="sxs-lookup"><span data-stu-id="73d08-125">You can add custom markers by calling the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the console.</span></span> 

- <span data-ttu-id="73d08-126">如果初始页面加载时间对分析非常重要，请确保清除浏览器缓存（从 "[网络](./network.md)" 面板）以确保从网络加载所有页面资源。</span><span class="sxs-lookup"><span data-stu-id="73d08-126">If initial page load times are important to your analysis, make sure to clear your browser cache (from the [Network](./network.md) panel) to ensure all page resources are loading from the network.</span></span>

- <span data-ttu-id="73d08-127">有时，你可以在不同的计算机上记录多个会话和/或采样相同的方案，从而更好地了解通配符中的性能问题。</span><span class="sxs-lookup"><span data-stu-id="73d08-127">Sometimes it helps to record multiple sessions and/or sample the same scenario across different machines to better understand the performance issue in the wild.</span></span>

## <span data-ttu-id="73d08-128">日程表标尺</span><span class="sxs-lookup"><span data-stu-id="73d08-128">Timeline ruler</span></span>

<span data-ttu-id="73d08-129">时间线作为滑动标尺工作。</span><span class="sxs-lookup"><span data-stu-id="73d08-129">The timeline works as a sliding ruler.</span></span> <span data-ttu-id="73d08-130">使用它将报表的范围限制为感兴趣的特定时间范围（或事件范围）。</span><span class="sxs-lookup"><span data-stu-id="73d08-130">Use it to limit the scope of the report to the particular timeframe (or span of events) of interest.</span></span> <span data-ttu-id="73d08-131">拖动黑色**幻灯片控件**以限制你想要调查的时间范围，并从下一个*详细信息窗格*中的 "[时间线](#timeline-details)" 和 " [JavaScript 调用堆栈](#javascript-call-stacks)" 报告中筛选无关的分析数据。</span><span class="sxs-lookup"><span data-stu-id="73d08-131">Drag the black **slide controls** to limit the time range you wish to investigate and filter out extraneous profiling data from the [Timeline](#timeline-details) and [JavaScript call stacks](#javascript-call-stacks) reports in the lower *Details pane*.</span></span> 

<span data-ttu-id="73d08-132">您将在标尺上看到两种类型的标记：</span><span class="sxs-lookup"><span data-stu-id="73d08-132">You will see two types of markers on the ruler:</span></span>

 - <span data-ttu-id="73d08-133">录制配置文件时，会自动记录日程表上的**应用生命周期标记**（如页面导航、 [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面[加载](https://developer.mozilla.org/docs/Web/Events/load)）。</span><span class="sxs-lookup"><span data-stu-id="73d08-133">**App lifecycle marks** on the timeline (such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load)) are automatically logged as you record a profile.</span></span>

 - <span data-ttu-id="73d08-134">**用户标记**是自定义标记，您可以选择在代码或 DevTools[**控制台**](./console.md)中添加对性能的调用[。标记（）](https://developer.mozilla.org/docs/Web/API/Performance/mark)方法。</span><span class="sxs-lookup"><span data-stu-id="73d08-134">**User marks** are custom markers you can choose to add  with calls to the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span> <span data-ttu-id="73d08-135">你可以将*开始*标记和*结束*标记组合为一个具有[Performance. measure （）](https://developer.mozilla.org/docs/Web/API/Performance/measure)方法的单个命名度量值。</span><span class="sxs-lookup"><span data-stu-id="73d08-135">You can group *start* and *end* marks together as a single, named measure with the [Performance.measure()](https://developer.mozilla.org/docs/Web/API/Performance/measure) method.</span></span> 

<span data-ttu-id="73d08-136">选择时间范围后，可以从工具栏进一步**放大**，或**重置缩放**和**清除选择**以返回到性能跟踪的完整视图（不选择时间范围）。</span><span class="sxs-lookup"><span data-stu-id="73d08-136">Once you have selected a time range, you can further **Zoom in** from the toolbar, or **Reset zoom** and **Clear selection** to return to the full view of the performance trace (with no time range selected).</span></span> <span data-ttu-id="73d08-137">也可通过右键单击上下文菜单使用这些控件。</span><span class="sxs-lookup"><span data-stu-id="73d08-137">These controls are also available from the right-click context menu.</span></span>

![性能面板日程表](./media/performance_timeline.png)

### <span data-ttu-id="73d08-139">CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="73d08-139">CPU utilization</span></span>

<span data-ttu-id="73d08-140">" **CPU 使用率%** 时序表" 图表描述运行页面时所需的各种浏览器子系统所占用的处理资源，按类别划分：</span><span class="sxs-lookup"><span data-stu-id="73d08-140">The **CPU utilization %** timeline graph describes the processing resources consumed by the various browser subsystems required to run the page, broken out by category:</span></span>

#### <span data-ttu-id="73d08-141">正在加载</span><span class="sxs-lookup"><span data-stu-id="73d08-141">Loading</span></span>
<span data-ttu-id="73d08-142">指示检索应用资源和分析 HTML 和 CSS 所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-142">Indicates time spent retrieving app resources and parsing HTML and CSS.</span></span> <span data-ttu-id="73d08-143">这可能包括网络请求。</span><span class="sxs-lookup"><span data-stu-id="73d08-143">This can include network requests.</span></span> <span data-ttu-id="73d08-144">以下关联事件将记录在[时间线](#timeline-details)中：</span><span class="sxs-lookup"><span data-stu-id="73d08-144">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="73d08-145">事件</span><span class="sxs-lookup"><span data-stu-id="73d08-145">Event</span></span> | <span data-ttu-id="73d08-146">描述</span><span class="sxs-lookup"><span data-stu-id="73d08-146">Description</span></span>
:------------ | :-------------
<span data-ttu-id="73d08-147">CssParsing</span><span class="sxs-lookup"><span data-stu-id="73d08-147">CssParsing</span></span>  | <span data-ttu-id="73d08-148">遇到需要分析的新 CSS 内容。</span><span class="sxs-lookup"><span data-stu-id="73d08-148">New CSS content was encountered that needed to be parsed.</span></span>
<span data-ttu-id="73d08-149">HtmlParsing</span><span class="sxs-lookup"><span data-stu-id="73d08-149">HtmlParsing</span></span> | <span data-ttu-id="73d08-150">遇到需要解析为节点并插入到 DOM 中的新 HTML 内容。</span><span class="sxs-lookup"><span data-stu-id="73d08-150">New HTML content was encountered that needed to be parsed into nodes and inserted into the DOM.</span></span>
<span data-ttu-id="73d08-151">HttpRequest</span><span class="sxs-lookup"><span data-stu-id="73d08-151">HttpRequest</span></span> | <span data-ttu-id="73d08-152">在 DOM 中遇到远程资源，或者创建了需要进行 HTTP 请求的 XMLHttpRequest。</span><span class="sxs-lookup"><span data-stu-id="73d08-152">A remote resource was encountered in the DOM or an XMLHttpRequest was created that required an HTTP request to be made.</span></span>
<span data-ttu-id="73d08-153">HtmlSpeculativeDownloading</span><span class="sxs-lookup"><span data-stu-id="73d08-153">HtmlSpeculativeDownloading</span></span> | <span data-ttu-id="73d08-154">正在搜索所需资源的页面 HTML 内容，以便能够尽快安排这些资源的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="73d08-154">The page's HTML content was being searched for required resources so that the HTTP requests for them could be scheduled as quickly as possible.</span></span>


#### <span data-ttu-id="73d08-155">运行</span><span class="sxs-lookup"><span data-stu-id="73d08-155">Scripting</span></span>
<span data-ttu-id="73d08-156">指示分析和执行 JavaScript 所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-156">Indicates time spent parsing and executing JavaScript.</span></span> <span data-ttu-id="73d08-157">这包括 DOM 事件、计时器、脚本求值和动画帧回调。</span><span class="sxs-lookup"><span data-stu-id="73d08-157">This includes DOM events, timers, script evaluation, and animation frame callbacks.</span></span> <span data-ttu-id="73d08-158">以下关联事件将记录在[时间线](#timeline-details)中：</span><span class="sxs-lookup"><span data-stu-id="73d08-158">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="73d08-159">事件</span><span class="sxs-lookup"><span data-stu-id="73d08-159">Event</span></span> | <span data-ttu-id="73d08-160">描述</span><span class="sxs-lookup"><span data-stu-id="73d08-160">Description</span></span>
:------------ | :-------------
<span data-ttu-id="73d08-161">DomEvent</span><span class="sxs-lookup"><span data-stu-id="73d08-161">DomEvent</span></span> | <span data-ttu-id="73d08-162">在 DOM 对象上触发了事件。</span><span class="sxs-lookup"><span data-stu-id="73d08-162">An event was fired on a DOM object.</span></span>
<span data-ttu-id="73d08-163">EvaluatingScript</span><span class="sxs-lookup"><span data-stu-id="73d08-163">EvaluatingScript</span></span> | <span data-ttu-id="73d08-164">`<script>`在 DOM 中遇到新元素，需要对其进行分析和执行。</span><span class="sxs-lookup"><span data-stu-id="73d08-164">A new `<script>` element was encountered in the DOM and needed to be parsed and executed.</span></span>
<span data-ttu-id="73d08-165">EventHandler</span><span class="sxs-lookup"><span data-stu-id="73d08-165">EventHandler</span></span> | <span data-ttu-id="73d08-166">为响应正在触发的 DOM 事件而触发的已注册事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="73d08-166">A registered event listener was triggered in response to a DOM event being fired.</span></span>
<span data-ttu-id="73d08-167">帧</span><span class="sxs-lookup"><span data-stu-id="73d08-167">Frame</span></span> | <span data-ttu-id="73d08-168">当新框架准备就绪时，将触发已注册的回调，以便它可以参与视觉更改。</span><span class="sxs-lookup"><span data-stu-id="73d08-168">While a new frame was being prepared a registered callback was triggered so that it could contribute visual changes.</span></span>
<span data-ttu-id="73d08-169">测量</span><span class="sxs-lookup"><span data-stu-id="73d08-169">Measure</span></span> | <span data-ttu-id="73d08-170">使用方法测量特定于应用的方案 `performance.measure()` 。</span><span class="sxs-lookup"><span data-stu-id="73d08-170">An app-specific scenario was measured using the `performance.measure()` method.</span></span>
<span data-ttu-id="73d08-171">MediaQueryListener</span><span class="sxs-lookup"><span data-stu-id="73d08-171">MediaQueryListener</span></span> | <span data-ttu-id="73d08-172">已注册的媒体查询已失效，从而导致执行其关联的侦听器。</span><span class="sxs-lookup"><span data-stu-id="73d08-172">A registered media query was invalidated which resulted in the execution of its associated listener(s).</span></span>
<span data-ttu-id="73d08-173">MutationObserver</span><span class="sxs-lookup"><span data-stu-id="73d08-173">MutationObserver</span></span> | <span data-ttu-id="73d08-174">已修改一个或多个观测的 DOM 元素，这些元素导致执行 MutationObserver 的关联回调。</span><span class="sxs-lookup"><span data-stu-id="73d08-174">One or more observed DOM elements were modified which resulted in the execution of a MutationObserver's associated callback.</span></span>
<span data-ttu-id="73d08-175">TimerFired</span><span class="sxs-lookup"><span data-stu-id="73d08-175">TimerFired</span></span> | <span data-ttu-id="73d08-176">计划的计时器已过，导致执行其关联的回调。</span><span class="sxs-lookup"><span data-stu-id="73d08-176">A scheduled timer elapsed which resulted in the execution of its associated callback.</span></span>
<span data-ttu-id="73d08-177">WindowsRuntimeAsyncCallback</span><span class="sxs-lookup"><span data-stu-id="73d08-177">WindowsRuntimeAsyncCallback</span></span> | <span data-ttu-id="73d08-178">异步操作由触发回调的 Windows 运行时对象完成 `Promise` 。</span><span class="sxs-lookup"><span data-stu-id="73d08-178">An async operation was completed by a Windows Runtime object which triggered a `Promise` callback.</span></span>
<span data-ttu-id="73d08-179">WindowsRuntimeEvent</span><span class="sxs-lookup"><span data-stu-id="73d08-179">WindowsRuntimeEvent</span></span> | <span data-ttu-id="73d08-180">在触发已注册侦听器的 Windows 运行时对象上触发了事件。</span><span class="sxs-lookup"><span data-stu-id="73d08-180">An event was fired on a Windows Runtime object which triggered a registered listener.</span></span>

#### <span data-ttu-id="73d08-181">GC</span><span class="sxs-lookup"><span data-stu-id="73d08-181">GC</span></span>
<span data-ttu-id="73d08-182">指示为不再使用的对象收集内存所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-182">Indicates time spent collecting memory for objects that are no longer in use.</span></span> <span data-ttu-id="73d08-183">以下关联事件将记录在[时间线](#timeline-details)中：</span><span class="sxs-lookup"><span data-stu-id="73d08-183">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="73d08-184">事件</span><span class="sxs-lookup"><span data-stu-id="73d08-184">Event</span></span> | <span data-ttu-id="73d08-185">描述</span><span class="sxs-lookup"><span data-stu-id="73d08-185">Description</span></span>
:------------ | :-------------
<span data-ttu-id="73d08-186">GarbageCollection</span><span class="sxs-lookup"><span data-stu-id="73d08-186">GarbageCollection</span></span> | <span data-ttu-id="73d08-187">JavaScript 运行时已审核应用的当前内存使用情况，以确定不再引用哪些对象，从而可以回收这些对象。</span><span class="sxs-lookup"><span data-stu-id="73d08-187">The JavaScript runtime audited the app's current memory usage in order to determine which objects aren't being referenced anymore and could therefore be collected.</span></span>

#### <span data-ttu-id="73d08-188">样式设置</span><span class="sxs-lookup"><span data-stu-id="73d08-188">Styling</span></span>
<span data-ttu-id="73d08-189">指示计算元素演示文稿和布局所用的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-189">Indicates time spent calculating element presentation and layout.</span></span> <span data-ttu-id="73d08-190">以下关联事件将记录在[时间线](#timeline-details)中：</span><span class="sxs-lookup"><span data-stu-id="73d08-190">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="73d08-191">事件</span><span class="sxs-lookup"><span data-stu-id="73d08-191">Event</span></span> | <span data-ttu-id="73d08-192">描述</span><span class="sxs-lookup"><span data-stu-id="73d08-192">Description</span></span>
:------------ | :-------------
<span data-ttu-id="73d08-193">AlignedBeat</span><span class="sxs-lookup"><span data-stu-id="73d08-193">AlignedBeat</span></span> | <span data-ttu-id="73d08-194">已处理对 DOM 所做的挂起的可视更改，以便可以更新应用的显示。</span><span class="sxs-lookup"><span data-stu-id="73d08-194">Pending visual changes that were made to the DOM were processed so that the app's display could be updated.</span></span>
<span data-ttu-id="73d08-195">CssCalculation</span><span class="sxs-lookup"><span data-stu-id="73d08-195">CssCalculation</span></span> | <span data-ttu-id="73d08-196">已对 DOM 进行了更改，或者添加了新的 CSS 内容，需要重新计算所有受影响的元素的样式属性。</span><span class="sxs-lookup"><span data-stu-id="73d08-196">Changes were made to the DOM or new CSS content was added, requiring the style properties of all affected elements to be recalculated.</span></span>
<span data-ttu-id="73d08-197">布局</span><span class="sxs-lookup"><span data-stu-id="73d08-197">Layout</span></span> | <span data-ttu-id="73d08-198">对 DOM 进行了更改，需要计算所有受影响的元素的大小和/或位置。</span><span class="sxs-lookup"><span data-stu-id="73d08-198">Changes were made to the DOM that required the size and/or position of all affected elements to be computed.</span></span>

#### <span data-ttu-id="73d08-199">呈现</span><span class="sxs-lookup"><span data-stu-id="73d08-199">Rendering</span></span>
<span data-ttu-id="73d08-200">指示绘制屏幕所用的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-200">Indicates time spent in painting the screen.</span></span> <span data-ttu-id="73d08-201">以下关联事件将记录在[时间线](#timeline-details)中：</span><span class="sxs-lookup"><span data-stu-id="73d08-201">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="73d08-202">事件</span><span class="sxs-lookup"><span data-stu-id="73d08-202">Event</span></span> | <span data-ttu-id="73d08-203">说明</span><span class="sxs-lookup"><span data-stu-id="73d08-203">Description</span></span>
:------------ | :-------------
<span data-ttu-id="73d08-204">画图</span><span class="sxs-lookup"><span data-stu-id="73d08-204">Paint</span></span> | <span data-ttu-id="73d08-205">对 DOM 进行了可视更改，需要重新绘制页面的所有受影响的部分。</span><span class="sxs-lookup"><span data-stu-id="73d08-205">Visual changes were made to the DOM that required all affected portions of the page to be redrawn.</span></span>
<span data-ttu-id="73d08-206">RenderLayer</span><span class="sxs-lookup"><span data-stu-id="73d08-206">RenderLayer</span></span> | <span data-ttu-id="73d08-207">对 DOM 的独立呈现片段（称为图层）进行了可视更改，从而需要重绘页面各自的部分。</span><span class="sxs-lookup"><span data-stu-id="73d08-207">Visual changes were made to an independently rendered fragment of the DOM (called a layer) which required its respective portion of the page to be redrawn.</span></span>

#### <span data-ttu-id="73d08-208">图像解码</span><span class="sxs-lookup"><span data-stu-id="73d08-208">Image decoding</span></span>
<span data-ttu-id="73d08-209">指示解压缩和解码图像所用的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-209">Indicates time spent decompressing and decoding images.</span></span> <span data-ttu-id="73d08-210">以下关联事件将记录在[时间线](#timeline-details)中：</span><span class="sxs-lookup"><span data-stu-id="73d08-210">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="73d08-211">事件</span><span class="sxs-lookup"><span data-stu-id="73d08-211">Event</span></span> | <span data-ttu-id="73d08-212">说明</span><span class="sxs-lookup"><span data-stu-id="73d08-212">Description</span></span>
:------------ | :-------------
<span data-ttu-id="73d08-213">ImageDecoded</span><span class="sxs-lookup"><span data-stu-id="73d08-213">ImageDecoded</span></span> | <span data-ttu-id="73d08-214">DOM 中已包含一个图像，需要将其从其原始格式解压缩到位图中。</span><span class="sxs-lookup"><span data-stu-id="73d08-214">An image was included into the DOM and needed be to decompressed from its original format into a bitmap.</span></span>

### <span data-ttu-id="73d08-215">视觉吞吐量</span><span class="sxs-lookup"><span data-stu-id="73d08-215">Visual throughput</span></span>

<span data-ttu-id="73d08-216">"**视觉吞吐量（FPS）** " 图形显示分析方案期间*每秒估计帧*（fps），其中 60 FPS 是理想的显示速率。</span><span class="sxs-lookup"><span data-stu-id="73d08-216">The **Visual throughput (FPS)** graph shows the estimated *frames per second* (FPS) during the course of the profiling scenario, where 60 FPS is the ideal display rate.</span></span> <span data-ttu-id="73d08-217">帧速率中的 dip 表示性能瓶颈，帧速率为零意味着完全删除帧。</span><span class="sxs-lookup"><span data-stu-id="73d08-217">Dips in the frame rate indicate performance bottlenecks and a frame rate of zero means that frames are getting dropped entirely.</span></span>

## <span data-ttu-id="73d08-218">日程表详细信息</span><span class="sxs-lookup"><span data-stu-id="73d08-218">Timeline details</span></span>

<span data-ttu-id="73d08-219">使用 "调换详细信息" 窗格全面了解页面上发生的情况。</span><span class="sxs-lookup"><span data-stu-id="73d08-219">Use the lowermost details pane to get the full breakdown of what happened on the page.</span></span> <span data-ttu-id="73d08-220">"**时间线详细信息**" 选项卡提供了在各种浏览器子系统中发生的事件的细目。</span><span class="sxs-lookup"><span data-stu-id="73d08-220">The **Timeline details** tab provides a breakdown of events that occurred within the various browser subsystems.</span></span>

![性能日程表详细信息窗格](./media/performance_details_timeline.png)

1. **<span data-ttu-id="73d08-222">事件列表排序控件</span><span class="sxs-lookup"><span data-stu-id="73d08-222">Event list sort control</span></span>**

    <span data-ttu-id="73d08-223">使用 "**排序依据**" 下拉列表控件在 "*开始时间*" 或 "*持续时间" （包含*）之间切换[事件列表](#event-list)顺序。</span><span class="sxs-lookup"><span data-stu-id="73d08-223">Use the **Sort by** dropdown control to toggle the [Event list](#event-list) order between *Start time* or *Duration (inclusive*).</span></span> <span data-ttu-id="73d08-224">这还会更改[所选日程表详细信息](#selected-timeline-details)的视图。</span><span class="sxs-lookup"><span data-stu-id="73d08-224">This also changes the view of the [Selected timeline details](#selected-timeline-details).</span></span>

2. **<span data-ttu-id="73d08-225">按帧对事件进行分组</span><span class="sxs-lookup"><span data-stu-id="73d08-225">Group events by frame</span></span>**

    <span data-ttu-id="73d08-226">在发生动画/视觉更新的时间段内，使用 "**按框架切换组顶层事件**" 切换到 "组顶层事件" （*HTML 分析、布局、DOM 事件*等）。</span><span class="sxs-lookup"><span data-stu-id="73d08-226">Use the **Group top level events by frames** toggle to group top-level events (*HTML parsing, Layout, DOM event,* etc.) into their corresponding unit of work (or "frame") during periods of time where animations/visual updates were occurring.</span></span> <span data-ttu-id="73d08-227">这些帧被视为其他事件，因此可以对它们进行排序/筛选，并在[事件列表](#event-list)中单击时提供*非独占时间*摘要。</span><span class="sxs-lookup"><span data-stu-id="73d08-227">The frames are treated like other events, so they can be sorted/filtered and provide an *Inclusive time* summary when clicked in the [Event list](#event-list).</span></span>

3. **<span data-ttu-id="73d08-228">事件列表筛选控件</span><span class="sxs-lookup"><span data-stu-id="73d08-228">Event list filter controls</span></span>**

    <span data-ttu-id="73d08-229">使用 "**筛选事件**" 菜单配置[日程表详细信息](#timeline-details)中显示的事件类型。</span><span class="sxs-lookup"><span data-stu-id="73d08-229">Use the **Filter events** menu to configure the types of events shown in the [timeline details](#timeline-details).</span></span> 

    ![用于筛选性能事件的控件](./media/performance_filter_events.png) 

    <span data-ttu-id="73d08-231">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="73d08-231">The following filters are available:</span></span>

   - <span data-ttu-id="73d08-232">**图像解码**：显示在后台线程上发生的事件（例如，图像解码、GC）。</span><span class="sxs-lookup"><span data-stu-id="73d08-232">**Image decoding**: Show events which occurred on a background thread (e.g. Image decoding, GC).</span></span> 
   - <span data-ttu-id="73d08-233">**网络流量**：显示网络绑定的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="73d08-233">**Network traffic**: Show HTTP requests which were network-bound.</span></span>
   - <span data-ttu-id="73d08-234">**Ui 活动**：显示在 UI 线程和/或呈现线程上发生的事件（例如，DOM 事件处理程序、布局）。</span><span class="sxs-lookup"><span data-stu-id="73d08-234">**UI activity**: Show events which occurred on the UI thread and/or render thread (e.g. DOM event handlers, Layout).</span></span>
   - <span data-ttu-id="73d08-235">**用户度量值**：显示用于指示对 performance （）方法的调用的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="73d08-235">**User measures**: Show custom events which indicate calls to the performance.measure() method.</span></span>

     <span data-ttu-id="73d08-236">你可以按其非独占持续时间进一步筛选顶级事件。</span><span class="sxs-lookup"><span data-stu-id="73d08-236">You can further filter top-level events by their inclusive duration.</span></span>

### <span data-ttu-id="73d08-237">事件列表</span><span class="sxs-lookup"><span data-stu-id="73d08-237">Event list</span></span>

<span data-ttu-id="73d08-238">*事件列表*提供按时间顺序排列所选时间范围内出现的[浏览器子系统事件](#cpu-utilization)的列表。</span><span class="sxs-lookup"><span data-stu-id="73d08-238">The *Event list* gives you a chronological list of [browser subsystem events](#cpu-utilization) that occurred during the selected span of time.</span></span> 

<span data-ttu-id="73d08-239">单击任意条目以填充该项目的**选定事件详细信息**图表。</span><span class="sxs-lookup"><span data-stu-id="73d08-239">Click on any entry to populate the **Selected event details** chart for that item.</span></span> <span data-ttu-id="73d08-240">具有嵌套事件/函数的条目将显示它们的**非独占**时间（执行函数所花费*的时间以及*它调用的任何其他函数）和**独占**式（仅限在调用函数本身的主体内所花的时间）图表中显示的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-240">Entries with nested events / functions will show their **inclusive** (time spent executing the function *and* any other functions it called) and **exclusive** (time spent only within the body of the calling function itself) times displayed in the chart.</span></span>

<span data-ttu-id="73d08-241">右键单击任何条目以打开上下文菜单，以仅将日程表筛选到该事件，并在[**调试程序**](./debugger.md)（或 "[**元素**](./elements.md)" 面板中）查看负责事件的源代码（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="73d08-241">Right-click on any entry to open the context menu to filter the timeline to only that event and view the source code responsible for the event in the [**Debugger**](./debugger.md) (or [**Elements**](./elements.md) panel, if applicable).</span></span>

### <span data-ttu-id="73d08-242">所选日程表详细信息</span><span class="sxs-lookup"><span data-stu-id="73d08-242">Selected timeline details</span></span>

<span data-ttu-id="73d08-243">*所选日程表详细信息*提供所选时间范围内非独占/独占事件时间的详细条形图。</span><span class="sxs-lookup"><span data-stu-id="73d08-243">The *Selected timeline details* provides a detailed bar graph of inclusive/exclusive event times during the selected time span.</span></span> <span data-ttu-id="73d08-244">使用**事件列表排序控件**按*持续时间（包含）* 进行排序时，最长的运行事件将在此图表中直观地突出。</span><span class="sxs-lookup"><span data-stu-id="73d08-244">When you sort by *Duration (inclusive)* using the **Event list sort control**, the longest running events will visually stand out in this chart.</span></span> 

### <span data-ttu-id="73d08-245">所选事件详细信息</span><span class="sxs-lookup"><span data-stu-id="73d08-245">Selected event details</span></span>

<span data-ttu-id="73d08-246">此报表提供有关所选事件的进一步信息，包括*开始时间*、执行线程类型（例如，*下载*、 *UI*、*呈现*）和特定于特定事件类型的其他上下文详细信息。</span><span class="sxs-lookup"><span data-stu-id="73d08-246">This report provides further information about the selected event, including *Start time*, the executing thread type (for example, *Download*, *UI*, *Render*), and other contextual details specific to the specific event type.</span></span> <span data-ttu-id="73d08-247">例如，*事件侦听器*类型提供指向*回调函数*和*调度调用堆栈*的调试器链接。</span><span class="sxs-lookup"><span data-stu-id="73d08-247">For example, *Event listener* types provide debugger links to the *Callback function* and *Scheduling call stack*.</span></span>

## <span data-ttu-id="73d08-248">JavaScript 调用堆栈</span><span class="sxs-lookup"><span data-stu-id="73d08-248">JavaScript call stacks</span></span>

![JavaScript 调用堆栈的性能计时](./media/performance_details_javascript.png)

<span data-ttu-id="73d08-250">**JavaScript "调用堆栈**" 选项卡提供在所选时间范围内运行的脚本函数的 CPU 使用信息和计时：</span><span class="sxs-lookup"><span data-stu-id="73d08-250">The **JavaScript call stacks** tab provides CPU usage information and timings for the script functions that ran during the selected time range:</span></span>

 <span data-ttu-id="73d08-251">列</span><span class="sxs-lookup"><span data-stu-id="73d08-251">Column</span></span> | <span data-ttu-id="73d08-252">描述</span><span class="sxs-lookup"><span data-stu-id="73d08-252">Description</span></span>
:------------ | :-------------
<span data-ttu-id="73d08-253">函数名称</span><span class="sxs-lookup"><span data-stu-id="73d08-253">Function name</span></span> | <span data-ttu-id="73d08-254">浏览器或用户定义函数的名称。</span><span class="sxs-lookup"><span data-stu-id="73d08-254">Name of browser or user-defined function.</span></span>
<span data-ttu-id="73d08-255">非独占 CPU （%）</span><span class="sxs-lookup"><span data-stu-id="73d08-255">Inclusive CPU (%)</span></span> | <span data-ttu-id="73d08-256">此函数以及此函数调用的函数中所选 CPU 活动的百分比。</span><span class="sxs-lookup"><span data-stu-id="73d08-256">Percentage of selected CPU activity in this function and in functions called by this function.</span></span>
<span data-ttu-id="73d08-257">独占 CPU （%）</span><span class="sxs-lookup"><span data-stu-id="73d08-257">Exclusive CPU (%)</span></span> | <span data-ttu-id="73d08-258">此函数中所选 CPU 活动的百分比，不包括此函数调用的函数中的活动。</span><span class="sxs-lookup"><span data-stu-id="73d08-258">Percentage of selected CPU activity in this function, excluding activity in functions called by this function.</span></span>
<span data-ttu-id="73d08-259">非独占 CPU （ms）</span><span class="sxs-lookup"><span data-stu-id="73d08-259">Inclusive CPU (ms)</span></span> | <span data-ttu-id="73d08-260">执行此函数中的代码以及此函数调用的函数所用的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-260">CPU time spent executing code in this function and in functions called by this function.</span></span>
<span data-ttu-id="73d08-261">独占 CPU （ms）</span><span class="sxs-lookup"><span data-stu-id="73d08-261">Exclusive CPU (ms)</span></span> | <span data-ttu-id="73d08-262">执行此函数中的代码所用的 CPU 时间，不包括此函数调用的函数中的时间。</span><span class="sxs-lookup"><span data-stu-id="73d08-262">CPU time spent executing code in this function, excluding time in functions called by this function.</span></span>
<span data-ttu-id="73d08-263">URL</span><span class="sxs-lookup"><span data-stu-id="73d08-263">URL</span></span> | <span data-ttu-id="73d08-264">出现堆栈帧的 URL。</span><span class="sxs-lookup"><span data-stu-id="73d08-264">URL(s) where stack frame occurred.</span></span> <span data-ttu-id="73d08-265">源自浏览器（基于标准的 web Api）的函数调用标记为 *[DOM]*。</span><span class="sxs-lookup"><span data-stu-id="73d08-265">Function calls originating from the browser (standards-based web APIs) are labeled as *[DOM]*.</span></span>

## <span data-ttu-id="73d08-266">指向</span><span class="sxs-lookup"><span data-stu-id="73d08-266">Shortcuts</span></span>

| <span data-ttu-id="73d08-267">操作</span><span class="sxs-lookup"><span data-stu-id="73d08-267">Action</span></span>                         | <span data-ttu-id="73d08-268">快捷方式</span><span class="sxs-lookup"><span data-stu-id="73d08-268">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="73d08-269">开始/停止分析会话</span><span class="sxs-lookup"><span data-stu-id="73d08-269">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="73d08-270">导入性能分析会话</span><span class="sxs-lookup"><span data-stu-id="73d08-270">Import profiling session</span></span>       | `Ctrl` + `O` |
| <span data-ttu-id="73d08-271">导出分析会话</span><span class="sxs-lookup"><span data-stu-id="73d08-271">Export profiling session</span></span>       | `Ctrl` + `S` |

## <span data-ttu-id="73d08-272">已知问题</span><span class="sxs-lookup"><span data-stu-id="73d08-272">Known Issues</span></span>

### <span data-ttu-id="73d08-273">启动分析会话时出错</span><span class="sxs-lookup"><span data-stu-id="73d08-273">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="73d08-274">如果你看到此错误消息：在性能工具中**启动分析会话时出错**，请按照以下步骤进行解决。</span><span class="sxs-lookup"><span data-stu-id="73d08-274">If you see this error message: **An error occurred while starting the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="73d08-275">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="73d08-275">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="73d08-276">在 "运行" 对话框中，输入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="73d08-276">In the Run dialog, enter **services.msc**.</span></span>
![已知问题-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="73d08-278">找到**Microsoft （R）诊断中心标准收集器服务**，然后右键单击它。</span><span class="sxs-lookup"><span data-stu-id="73d08-278">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![已知问题-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="73d08-280">重新启动**Microsoft （R）诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="73d08-280">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![已知问题-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="73d08-282">关闭 "Microsoft Edge 开发工具" 和 "选项卡"。打开新选项卡，导航到您的页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="73d08-282">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="73d08-283">现在，你应该能够开始分析。</span><span class="sxs-lookup"><span data-stu-id="73d08-283">You should now be able to begin profiling.</span></span>
![已知问题-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="73d08-285">仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="73d08-285">Still running into problems?</span></span> <span data-ttu-id="73d08-286">请使用 "**发送反馈**" 图标向我们发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="73d08-286">Please send us your feedback using the **Send feedback** icon!</span></span> 

![已知问题-5](./media/known_issues_5.PNG)

### <span data-ttu-id="73d08-288">停止性能分析会话时出错。</span><span class="sxs-lookup"><span data-stu-id="73d08-288">An error occurred while stopping the profiling session.</span></span>

<span data-ttu-id="73d08-289">如果你看到此错误消息：在性能工具中**停止分析会话时发生错误**，请按照以下步骤进行解决。</span><span class="sxs-lookup"><span data-stu-id="73d08-289">If you see this error message: **An error occurred while stopping the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="73d08-290">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="73d08-290">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="73d08-291">在 "运行" 对话框中，输入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="73d08-291">In the Run dialog, enter **services.msc**.</span></span>
![已知问题-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="73d08-293">找到**Microsoft （R）诊断中心标准收集器服务**，然后右键单击它。</span><span class="sxs-lookup"><span data-stu-id="73d08-293">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![已知问题-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="73d08-295">重新启动**Microsoft （R）诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="73d08-295">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![已知问题-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="73d08-297">关闭 "Microsoft Edge 开发工具" 和 "选项卡"。打开新选项卡，导航到您的页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="73d08-297">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="73d08-298">现在，你应该能够开始分析。</span><span class="sxs-lookup"><span data-stu-id="73d08-298">You should now be able to begin profiling.</span></span>
![已知问题-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="73d08-300">仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="73d08-300">Still running into problems?</span></span> <span data-ttu-id="73d08-301">请使用 "**发送反馈**" 图标向我们发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="73d08-301">Please send us your feedback using the **Send feedback** icon!</span></span> 

![已知问题-5](./media/known_issues_5.PNG)
