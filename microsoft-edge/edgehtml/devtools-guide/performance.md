---
description: 使用"性能"面板在用户交互期间分析页面的响应性
title: DevTools - 性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 性能， 配置文件， 帧速率， fps， CPU 使用率， JavaScript 执行
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 561cfe62f7db492ce3914b4daba8ccf8c0a62a8a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232143"
---
# <span data-ttu-id="3be63-104">性能</span><span class="sxs-lookup"><span data-stu-id="3be63-104">Performance</span></span>

<span data-ttu-id="3be63-105">性能 **面板** 提供用于分析和分析 UI 在用户交互过程中的响应性的工具。</span><span class="sxs-lookup"><span data-stu-id="3be63-105">The **Performance** panel offers tools for profiling and analyzing the responsiveness of your UI during the course of user interaction.</span></span> <span data-ttu-id="3be63-106">通过它，你可以：</span><span class="sxs-lookup"><span data-stu-id="3be63-106">With it, you can:</span></span>

 - <span data-ttu-id="3be63-107">[测量页面](#recording-a-profile) 各个组件的执行时间</span><span class="sxs-lookup"><span data-stu-id="3be63-107">[Measure execution times](#recording-a-profile) of the various components of your page</span></span> 
 - <span data-ttu-id="3be63-108">[向下钻取](#timeline-ruler) 到运行页面的 CPU 周期最多的地方，以及为用户提供的结果视觉效果</span><span class="sxs-lookup"><span data-stu-id="3be63-108">[Drill down to where you're spending the most CPU cycles](#timeline-ruler) to run your page and the resulting visual effect for your users</span></span>
 - <span data-ttu-id="3be63-109">[获取使用页面执行时间的进程](#timeline-details) 的分步细分</span><span class="sxs-lookup"><span data-stu-id="3be63-109">[Get a step-by-step breakdown of the processes](#timeline-details) consuming page execution time</span></span> 
 - <span data-ttu-id="3be63-110">[演练 JavaScript 调用堆栈](#javascript-call-stacks) ，以确定代价高昂的操作，例如需要布局重新计算的操作</span><span class="sxs-lookup"><span data-stu-id="3be63-110">[Walk your JavaScript call stacks](#javascript-call-stacks) to identify costly operations, such as those requiring layout recalculations</span></span> 

![DevTools 性能面板](./media/performance.png)

## <span data-ttu-id="3be63-112">录制配置文件</span><span class="sxs-lookup"><span data-stu-id="3be63-112">Recording a profile</span></span>

<span data-ttu-id="3be63-113">分析页面性能的第一步是，当你执行特定用户方案时捕获配置文件，例如尝试修复的性能 bug 的重新说明步骤，或者你想要优化以提供更好的用户体验的典型用例。</span><span class="sxs-lookup"><span data-stu-id="3be63-113">The first step to analyzing the performance of your page is to capture a profile as you perform a particular user scenario, such as the repro steps of a performance bug you're trying to fix, or a typical use case you want to optimize for a better user experience.</span></span> 

### <span data-ttu-id="3be63-114">工具栏</span><span class="sxs-lookup"><span data-stu-id="3be63-114">Toolbar</span></span>

<span data-ttu-id="3be63-115">使用**工具栏上的**"开始停止  /  \*\*\*\*" (或) 启动和结束 `Ctrl+E` 性能跟踪。</span><span class="sxs-lookup"><span data-stu-id="3be63-115">Use the **Start** / **Stop** buttons on the toolbar (or `Ctrl+E`) to initiate and conclude your performance trace.</span></span> <span data-ttu-id="3be63-116">在"性能"选项卡上，绿色指示器\*\*\*\* 将闪烁以指示正在录制。</span><span class="sxs-lookup"><span data-stu-id="3be63-116">A green indicator will apear on the **Performance** tab to indicate a recording is in progress.</span></span> 

![性能面板工具栏](./media/performance_toolbar.png)

<span data-ttu-id="3be63-118">在停止配置文件时将生成性能报告。</span><span class="sxs-lookup"><span data-stu-id="3be63-118">A performance report will generate upon stopping the profile.</span></span> <span data-ttu-id="3be63-119">你可以选择将其保存到磁盘 `Ctrl+S` () ， () `Ctrl+O` 在 DevTools 中重新加载它。</span><span class="sxs-lookup"><span data-stu-id="3be63-119">You can choose to save it to disk (`Ctrl+S`) and reload (`Ctrl+O`) in  DevTools at a later time.</span></span>  <span data-ttu-id="3be63-120">DevTools 诊断会话与 *.diagsession 扩展一起* 保存。</span><span class="sxs-lookup"><span data-stu-id="3be63-120">DevTools diagnostic sessions are saved with the *.diagsession* extension.</span></span>

<span data-ttu-id="3be63-121">录制配置文件时，请注意以下一些情况：</span><span class="sxs-lookup"><span data-stu-id="3be63-121">Here are some things to keep in mind when recording a profile:</span></span>

- <span data-ttu-id="3be63-122">执行捕获尝试分析的方案所需的最最短操作。</span><span class="sxs-lookup"><span data-stu-id="3be63-122">Perform the fewest actions you need to capture the scenario you're trying to analyze.</span></span> <span data-ttu-id="3be63-123">与页面不相随的操作会产生额外的数据，并且会使结果变得混乱。</span><span class="sxs-lookup"><span data-stu-id="3be63-123">Extraneous actions with the page will produce extra data and clutter your results.</span></span>

- <span data-ttu-id="3be63-124">探查器将自动标记报告中的主要应用生命周期事件，如页面导航 [、DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面 [加载](https://developer.mozilla.org/docs/Web/Events/load)。</span><span class="sxs-lookup"><span data-stu-id="3be63-124">The profiler will automatically mark major app lifecycle events in the report, such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load).</span></span> <span data-ttu-id="3be63-125">可以通过从代码或控制台内调用 [Performance.mark () ](https://developer.mozilla.org/docs/Web/API/Performance/mark) 方法来添加自定义标记。</span><span class="sxs-lookup"><span data-stu-id="3be63-125">You can add custom markers by calling the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the console.</span></span> 

- <span data-ttu-id="3be63-126">如果初始页面加载时间对分析非常重要，请确保从网络面板 (清除浏览器缓存) 以确保从网络加载所有[](./network.md)页面资源。</span><span class="sxs-lookup"><span data-stu-id="3be63-126">If initial page load times are important to your analysis, make sure to clear your browser cache (from the [Network](./network.md) panel) to ensure all page resources are loading from the network.</span></span>

- <span data-ttu-id="3be63-127">有时，这有助于记录多个会话和/或跨不同计算机对同一方案进行采样，以更好地了解通配符中的性能问题。</span><span class="sxs-lookup"><span data-stu-id="3be63-127">Sometimes it helps to record multiple sessions and/or sample the same scenario across different machines to better understand the performance issue in the wild.</span></span>

## <span data-ttu-id="3be63-128">日程表标尺</span><span class="sxs-lookup"><span data-stu-id="3be63-128">Timeline ruler</span></span>

<span data-ttu-id="3be63-129">时间线用作滑动标尺。</span><span class="sxs-lookup"><span data-stu-id="3be63-129">The timeline works as a sliding ruler.</span></span> <span data-ttu-id="3be63-130">使用它将报告范围限制为特定时间范围， (关注的事件范围) 时间范围。</span><span class="sxs-lookup"><span data-stu-id="3be63-130">Use it to limit the scope of the report to the particular timeframe (or span of events) of interest.</span></span> <span data-ttu-id="3be63-131">拖动黑色**幻灯片**控件以限制希望调查和筛选出日程表和[JavaScript](#javascript-call-stacks)调用堆栈报告中的外在分析数据的范围[](#timeline-details)，具体操作在"详细信息"窗格*下。*</span><span class="sxs-lookup"><span data-stu-id="3be63-131">Drag the black **slide controls** to limit the time range you wish to investigate and filter out extraneous profiling data from the [Timeline](#timeline-details) and [JavaScript call stacks](#javascript-call-stacks) reports in the lower *Details pane*.</span></span> 

<span data-ttu-id="3be63-132">你将在标尺上看到两种类型的标记：</span><span class="sxs-lookup"><span data-stu-id="3be63-132">You will see two types of markers on the ruler:</span></span>

 - <span data-ttu-id="3be63-133">**时间线上的应用** 生命周期标记 (如页面导航 [、DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面 [加载) 记录](https://developer.mozilla.org/docs/Web/Events/load) 配置文件时自动记录。</span><span class="sxs-lookup"><span data-stu-id="3be63-133">**App lifecycle marks** on the timeline (such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load)) are automatically logged as you record a profile.</span></span>

 - <span data-ttu-id="3be63-134">**用户标记** 是自定义标记，你可以选择从代码或 DevTools 控制台内调用 [Performance.mark () ](https://developer.mozilla.org/docs/Web/API/Performance/mark) 方法进行 [**添加**](./console.md)。</span><span class="sxs-lookup"><span data-stu-id="3be63-134">**User marks** are custom markers you can choose to add  with calls to the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span> <span data-ttu-id="3be63-135">可以使用[Performance.measure () ](https://developer.mozilla.org/docs/Web/API/Performance/measure)方法将开始标记和结束标记分组为一个命名度量值。 \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="3be63-135">You can group *start* and *end* marks together as a single, named measure with the [Performance.measure()](https://developer.mozilla.org/docs/Web/API/Performance/measure) method.</span></span> 

<span data-ttu-id="3be63-136">选择一个时间范围后，可以从工具栏进一步放大，或者重置缩放和\*\*\*\* 清除选择以\*\*\*\* 返回到性能跟踪视图的完整视图 (未选择任何) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3be63-136">Once you have selected a time range, you can further **Zoom in** from the toolbar, or **Reset zoom** and **Clear selection** to return to the full view of the performance trace (with no time range selected).</span></span> <span data-ttu-id="3be63-137">这些控件也可从右键单击上下文菜单中获得。</span><span class="sxs-lookup"><span data-stu-id="3be63-137">These controls are also available from the right-click context menu.</span></span>

![性能面板时间线](./media/performance_timeline.png)

### <span data-ttu-id="3be63-139">CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="3be63-139">CPU utilization</span></span>

<span data-ttu-id="3be63-140">CPU **使用率百分比** 时间线图按类别描述运行页面所需的各种浏览器子系统使用的处理资源：</span><span class="sxs-lookup"><span data-stu-id="3be63-140">The **CPU utilization %** timeline graph describes the processing resources consumed by the various browser subsystems required to run the page, broken out by category:</span></span>

#### <span data-ttu-id="3be63-141">正在加载</span><span class="sxs-lookup"><span data-stu-id="3be63-141">Loading</span></span>
<span data-ttu-id="3be63-142">指示检索应用程序资源和分析 HTML 和 CSS 所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-142">Indicates time spent retrieving app resources and parsing HTML and CSS.</span></span> <span data-ttu-id="3be63-143">这可能包括网络请求。</span><span class="sxs-lookup"><span data-stu-id="3be63-143">This can include network requests.</span></span> <span data-ttu-id="3be63-144">以下关联事件记录在 [时间线中](#timeline-details)：</span><span class="sxs-lookup"><span data-stu-id="3be63-144">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="3be63-145">事件</span><span class="sxs-lookup"><span data-stu-id="3be63-145">Event</span></span> | <span data-ttu-id="3be63-146">描述</span><span class="sxs-lookup"><span data-stu-id="3be63-146">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3be63-147">CssParsing</span><span class="sxs-lookup"><span data-stu-id="3be63-147">CssParsing</span></span>  | <span data-ttu-id="3be63-148">遇到需要分析的新 CSS 内容。</span><span class="sxs-lookup"><span data-stu-id="3be63-148">New CSS content was encountered that needed to be parsed.</span></span>
<span data-ttu-id="3be63-149">HtmlParsing</span><span class="sxs-lookup"><span data-stu-id="3be63-149">HtmlParsing</span></span> | <span data-ttu-id="3be63-150">遇到需要解析为节点并插入到 DOM 的新 HTML 内容。</span><span class="sxs-lookup"><span data-stu-id="3be63-150">New HTML content was encountered that needed to be parsed into nodes and inserted into the DOM.</span></span>
<span data-ttu-id="3be63-151">HttpRequest</span><span class="sxs-lookup"><span data-stu-id="3be63-151">HttpRequest</span></span> | <span data-ttu-id="3be63-152">在 DOM 中遇到远程资源，或创建了需要进行 HTTP 请求的 XMLHttpRequest。</span><span class="sxs-lookup"><span data-stu-id="3be63-152">A remote resource was encountered in the DOM or an XMLHttpRequest was created that required an HTTP request to be made.</span></span>
<span data-ttu-id="3be63-153">HtmlSpeculativeDownloading</span><span class="sxs-lookup"><span data-stu-id="3be63-153">HtmlSpeculativeDownloading</span></span> | <span data-ttu-id="3be63-154">正在搜索页面的 HTML 内容以查找所需资源，以便尽快计划其 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="3be63-154">The page's HTML content was being searched for required resources so that the HTTP requests for them could be scheduled as quickly as possible.</span></span>


#### <span data-ttu-id="3be63-155">脚本</span><span class="sxs-lookup"><span data-stu-id="3be63-155">Scripting</span></span>
<span data-ttu-id="3be63-156">指示分析和执行 JavaScript 所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-156">Indicates time spent parsing and executing JavaScript.</span></span> <span data-ttu-id="3be63-157">这包括 DOM 事件、计时器、脚本评估和动画帧回调。</span><span class="sxs-lookup"><span data-stu-id="3be63-157">This includes DOM events, timers, script evaluation, and animation frame callbacks.</span></span> <span data-ttu-id="3be63-158">以下关联事件记录在 [时间线中](#timeline-details)：</span><span class="sxs-lookup"><span data-stu-id="3be63-158">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="3be63-159">事件</span><span class="sxs-lookup"><span data-stu-id="3be63-159">Event</span></span> | <span data-ttu-id="3be63-160">描述</span><span class="sxs-lookup"><span data-stu-id="3be63-160">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3be63-161">DomEvent</span><span class="sxs-lookup"><span data-stu-id="3be63-161">DomEvent</span></span> | <span data-ttu-id="3be63-162">在 DOM 对象上触发了事件。</span><span class="sxs-lookup"><span data-stu-id="3be63-162">An event was fired on a DOM object.</span></span>
<span data-ttu-id="3be63-163">EvaluatingScript</span><span class="sxs-lookup"><span data-stu-id="3be63-163">EvaluatingScript</span></span> | <span data-ttu-id="3be63-164">在 `<script>` DOM 中遇到新元素，需要进行分析和执行。</span><span class="sxs-lookup"><span data-stu-id="3be63-164">A new `<script>` element was encountered in the DOM and needed to be parsed and executed.</span></span>
<span data-ttu-id="3be63-165">EventHandler</span><span class="sxs-lookup"><span data-stu-id="3be63-165">EventHandler</span></span> | <span data-ttu-id="3be63-166">已触发注册的事件侦听器以响应正在触发的 DOM 事件。</span><span class="sxs-lookup"><span data-stu-id="3be63-166">A registered event listener was triggered in response to a DOM event being fired.</span></span>
<span data-ttu-id="3be63-167">帧</span><span class="sxs-lookup"><span data-stu-id="3be63-167">Frame</span></span> | <span data-ttu-id="3be63-168">准备新帧时，触发了已注册的回调，以便它可以参与视觉更改。</span><span class="sxs-lookup"><span data-stu-id="3be63-168">While a new frame was being prepared a registered callback was triggered so that it could contribute visual changes.</span></span>
<span data-ttu-id="3be63-169">测量</span><span class="sxs-lookup"><span data-stu-id="3be63-169">Measure</span></span> | <span data-ttu-id="3be63-170">使用该方法测量了特定于应用 `performance.measure()` 的方案。</span><span class="sxs-lookup"><span data-stu-id="3be63-170">An app-specific scenario was measured using the `performance.measure()` method.</span></span>
<span data-ttu-id="3be63-171">MediaQueryListener</span><span class="sxs-lookup"><span data-stu-id="3be63-171">MediaQueryListener</span></span> | <span data-ttu-id="3be63-172">注册的媒体查询失效，导致在其关联的侦听器查询 () 。</span><span class="sxs-lookup"><span data-stu-id="3be63-172">A registered media query was invalidated which resulted in the execution of its associated listener(s).</span></span>
<span data-ttu-id="3be63-173">MutationObserver</span><span class="sxs-lookup"><span data-stu-id="3be63-173">MutationObserver</span></span> | <span data-ttu-id="3be63-174">修改了一个或多个观察到的 DOM 元素，这导致执行一个与一个一体机关联的回调。</span><span class="sxs-lookup"><span data-stu-id="3be63-174">One or more observed DOM elements were modified which resulted in the execution of a MutationObserver's associated callback.</span></span>
<span data-ttu-id="3be63-175">TimerFired</span><span class="sxs-lookup"><span data-stu-id="3be63-175">TimerFired</span></span> | <span data-ttu-id="3be63-176">计划的计时器已过，导致执行其关联的回调。</span><span class="sxs-lookup"><span data-stu-id="3be63-176">A scheduled timer elapsed which resulted in the execution of its associated callback.</span></span>
<span data-ttu-id="3be63-177">WindowsRuntimeAsyncCallback</span><span class="sxs-lookup"><span data-stu-id="3be63-177">WindowsRuntimeAsyncCallback</span></span> | <span data-ttu-id="3be63-178">异步操作由触发回调的 Windows 运行时对象 `Promise` 完成。</span><span class="sxs-lookup"><span data-stu-id="3be63-178">An async operation was completed by a Windows Runtime object which triggered a `Promise` callback.</span></span>
<span data-ttu-id="3be63-179">WindowsRuntimeEvent</span><span class="sxs-lookup"><span data-stu-id="3be63-179">WindowsRuntimeEvent</span></span> | <span data-ttu-id="3be63-180">在触发注册侦听器的 Windows 运行时对象上触发了事件。</span><span class="sxs-lookup"><span data-stu-id="3be63-180">An event was fired on a Windows Runtime object which triggered a registered listener.</span></span>

#### <span data-ttu-id="3be63-181">GC</span><span class="sxs-lookup"><span data-stu-id="3be63-181">GC</span></span>
<span data-ttu-id="3be63-182">指示收集不再使用的对象的内存所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-182">Indicates time spent collecting memory for objects that are no longer in use.</span></span> <span data-ttu-id="3be63-183">以下关联事件记录在 [时间线中](#timeline-details)：</span><span class="sxs-lookup"><span data-stu-id="3be63-183">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="3be63-184">事件</span><span class="sxs-lookup"><span data-stu-id="3be63-184">Event</span></span> | <span data-ttu-id="3be63-185">描述</span><span class="sxs-lookup"><span data-stu-id="3be63-185">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3be63-186">GarbageCollection</span><span class="sxs-lookup"><span data-stu-id="3be63-186">GarbageCollection</span></span> | <span data-ttu-id="3be63-187">JavaScript 运行时审核应用的当前内存使用情况，以确定不再引用的对象，因此可以收集这些对象。</span><span class="sxs-lookup"><span data-stu-id="3be63-187">The JavaScript runtime audited the app's current memory usage in order to determine which objects aren't being referenced anymore and could therefore be collected.</span></span>

#### <span data-ttu-id="3be63-188">样式设置</span><span class="sxs-lookup"><span data-stu-id="3be63-188">Styling</span></span>
<span data-ttu-id="3be63-189">指示计算元素演示文稿和布局所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-189">Indicates time spent calculating element presentation and layout.</span></span> <span data-ttu-id="3be63-190">以下关联事件记录在 [时间线中](#timeline-details)：</span><span class="sxs-lookup"><span data-stu-id="3be63-190">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="3be63-191">事件</span><span class="sxs-lookup"><span data-stu-id="3be63-191">Event</span></span> | <span data-ttu-id="3be63-192">描述</span><span class="sxs-lookup"><span data-stu-id="3be63-192">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3be63-193">AlignedBeat</span><span class="sxs-lookup"><span data-stu-id="3be63-193">AlignedBeat</span></span> | <span data-ttu-id="3be63-194">已处理对 DOM 进行挂起的视觉更改，以便可以更新应用的显示。</span><span class="sxs-lookup"><span data-stu-id="3be63-194">Pending visual changes that were made to the DOM were processed so that the app's display could be updated.</span></span>
<span data-ttu-id="3be63-195">CssCalculation</span><span class="sxs-lookup"><span data-stu-id="3be63-195">CssCalculation</span></span> | <span data-ttu-id="3be63-196">对 DOM 进行了更改或添加了新的 CSS 内容，要求重新计算所有受影响的元素的样式属性。</span><span class="sxs-lookup"><span data-stu-id="3be63-196">Changes were made to the DOM or new CSS content was added, requiring the style properties of all affected elements to be recalculated.</span></span>
<span data-ttu-id="3be63-197">布局</span><span class="sxs-lookup"><span data-stu-id="3be63-197">Layout</span></span> | <span data-ttu-id="3be63-198">对 DOM 进行了更改，要求计算所有受影响的元素的大小和/或位置。</span><span class="sxs-lookup"><span data-stu-id="3be63-198">Changes were made to the DOM that required the size and/or position of all affected elements to be computed.</span></span>

#### <span data-ttu-id="3be63-199">呈现</span><span class="sxs-lookup"><span data-stu-id="3be63-199">Rendering</span></span>
<span data-ttu-id="3be63-200">指示绘制屏幕所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-200">Indicates time spent in painting the screen.</span></span> <span data-ttu-id="3be63-201">以下关联事件记录在 [时间线中](#timeline-details)：</span><span class="sxs-lookup"><span data-stu-id="3be63-201">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="3be63-202">事件</span><span class="sxs-lookup"><span data-stu-id="3be63-202">Event</span></span> | <span data-ttu-id="3be63-203">描述</span><span class="sxs-lookup"><span data-stu-id="3be63-203">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3be63-204">画图</span><span class="sxs-lookup"><span data-stu-id="3be63-204">Paint</span></span> | <span data-ttu-id="3be63-205">对 DOM 进行了可视更改，要求重新绘制页面的所有受影响的部分。</span><span class="sxs-lookup"><span data-stu-id="3be63-205">Visual changes were made to the DOM that required all affected portions of the page to be redrawn.</span></span>
<span data-ttu-id="3be63-206">RenderLayer</span><span class="sxs-lookup"><span data-stu-id="3be63-206">RenderLayer</span></span> | <span data-ttu-id="3be63-207">对 DOM 文件的独立呈现片段进行了视觉更改 (称为层) 需要重新绘制页面各自的部分。</span><span class="sxs-lookup"><span data-stu-id="3be63-207">Visual changes were made to an independently rendered fragment of the DOM (called a layer) which required its respective portion of the page to be redrawn.</span></span>

#### <span data-ttu-id="3be63-208">图像解码</span><span class="sxs-lookup"><span data-stu-id="3be63-208">Image decoding</span></span>
<span data-ttu-id="3be63-209">指示解压缩和解码图像所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-209">Indicates time spent decompressing and decoding images.</span></span> <span data-ttu-id="3be63-210">以下关联事件记录在 [时间线中](#timeline-details)：</span><span class="sxs-lookup"><span data-stu-id="3be63-210">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="3be63-211">事件</span><span class="sxs-lookup"><span data-stu-id="3be63-211">Event</span></span> | <span data-ttu-id="3be63-212">描述</span><span class="sxs-lookup"><span data-stu-id="3be63-212">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3be63-213">ImageDecoded</span><span class="sxs-lookup"><span data-stu-id="3be63-213">ImageDecoded</span></span> | <span data-ttu-id="3be63-214">图像包含在 DOM 中，需要将图像的原始格式解压缩为位图。</span><span class="sxs-lookup"><span data-stu-id="3be63-214">An image was included into the DOM and needed be to decompressed from its original format into a bitmap.</span></span>

### <span data-ttu-id="3be63-215">可视吞吐量</span><span class="sxs-lookup"><span data-stu-id="3be63-215">Visual throughput</span></span>

<span data-ttu-id="3be63-216">**"FPS (FPS**) 图显示分析方案（其中 60 FPS 是理想显示速率）期间估计每秒*帧数* (FPS) 。</span><span class="sxs-lookup"><span data-stu-id="3be63-216">The **Visual throughput (FPS)** graph shows the estimated *frames per second* (FPS) during the course of the profiling scenario, where 60 FPS is the ideal display rate.</span></span> <span data-ttu-id="3be63-217">帧速率下降表示性能瓶颈，帧速率为零意味着帧完全被丢弃。</span><span class="sxs-lookup"><span data-stu-id="3be63-217">Dips in the frame rate indicate performance bottlenecks and a frame rate of zero means that frames are getting dropped entirely.</span></span>

## <span data-ttu-id="3be63-218">时间线详细信息</span><span class="sxs-lookup"><span data-stu-id="3be63-218">Timeline details</span></span>

<span data-ttu-id="3be63-219">使用最下层的详细信息窗格获取页面上所发生事件的完整细目。</span><span class="sxs-lookup"><span data-stu-id="3be63-219">Use the lowermost details pane to get the full breakdown of what happened on the page.</span></span> <span data-ttu-id="3be63-220">" **日程表详细信息** "选项卡提供了各种浏览器子系统内所发生事件的细分。</span><span class="sxs-lookup"><span data-stu-id="3be63-220">The **Timeline details** tab provides a breakdown of events that occurred within the various browser subsystems.</span></span>

![性能时间线详细信息窗格](./media/performance_details_timeline.png)

1. **<span data-ttu-id="3be63-222">事件列表排序控件</span><span class="sxs-lookup"><span data-stu-id="3be63-222">Event list sort control</span></span>**

    <span data-ttu-id="3be63-223">使用"**按下拉列表排序**"控件在开始时间或[](#event-list)持续时间之间切换事件\*\* 列表顺序 (*包括) 。*</span><span class="sxs-lookup"><span data-stu-id="3be63-223">Use the **Sort by** dropdown control to toggle the [Event list](#event-list) order between *Start time* or *Duration (inclusive*).</span></span> <span data-ttu-id="3be63-224">这还会更改所选日程表 [详细信息的视图](#selected-timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="3be63-224">This also changes the view of the [Selected timeline details](#selected-timeline-details).</span></span>

2. **<span data-ttu-id="3be63-225">按帧分组事件</span><span class="sxs-lookup"><span data-stu-id="3be63-225">Group events by frame</span></span>**

    <span data-ttu-id="3be63-226">使用按\*\*\*\* 帧切换的组顶级事件，将顶级事件 (HTML 分析、布局 *、DOM*事件等 ) 分组到其相应的工作单元 (或"frame") 中（动画/视觉更新发生期间）。</span><span class="sxs-lookup"><span data-stu-id="3be63-226">Use the **Group top level events by frames** toggle to group top-level events (*HTML parsing, Layout, DOM event,* etc.) into their corresponding unit of work (or "frame") during periods of time where animations/visual updates were occurring.</span></span> <span data-ttu-id="3be63-227">帧被视为与其他事件一样，因此可以排序/筛选它们，并提供在事件列表中单击时包含\*\*[时间摘要](#event-list)。</span><span class="sxs-lookup"><span data-stu-id="3be63-227">The frames are treated like other events, so they can be sorted/filtered and provide an *Inclusive time* summary when clicked in the [Event list](#event-list).</span></span>

3. **<span data-ttu-id="3be63-228">事件列表筛选器控件</span><span class="sxs-lookup"><span data-stu-id="3be63-228">Event list filter controls</span></span>**

    <span data-ttu-id="3be63-229">使用 **"筛选器事件"** 菜单配置时间线详细信息中显示的 [事件类型](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="3be63-229">Use the **Filter events** menu to configure the types of events shown in the [timeline details](#timeline-details).</span></span> 

    ![用于筛选性能事件的控件](./media/performance_filter_events.png) 

    <span data-ttu-id="3be63-231">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="3be63-231">The following filters are available:</span></span>

   - <span data-ttu-id="3be63-232">**图像解码**：显示在后台线程上 (的事件，例如图像解码、GC) 。</span><span class="sxs-lookup"><span data-stu-id="3be63-232">**Image decoding**: Show events which occurred on a background thread (e.g. Image decoding, GC).</span></span> 
   - <span data-ttu-id="3be63-233">**网络流量**：显示已网络绑定的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="3be63-233">**Network traffic**: Show HTTP requests which were network-bound.</span></span>
   - <span data-ttu-id="3be63-234">**UI 活动**：显示 UI 线程和/或呈现线程上 (的事件，例如 DOM 事件处理程序、布局) 。</span><span class="sxs-lookup"><span data-stu-id="3be63-234">**UI activity**: Show events which occurred on the UI thread and/or render thread (e.g. DOM event handlers, Layout).</span></span>
   - <span data-ttu-id="3be63-235">**用户度量**：显示指示对 performance.measure () 方法的调用的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="3be63-235">**User measures**: Show custom events which indicate calls to the performance.measure() method.</span></span>

     <span data-ttu-id="3be63-236">可以进一步按包含持续时间筛选顶级事件。</span><span class="sxs-lookup"><span data-stu-id="3be63-236">You can further filter top-level events by their inclusive duration.</span></span>

### <span data-ttu-id="3be63-237">事件列表</span><span class="sxs-lookup"><span data-stu-id="3be63-237">Event list</span></span>

<span data-ttu-id="3be63-238">事件*列表*按时间顺序列出所选时间跨度内发生的[](#cpu-utilization)浏览器子系统事件。</span><span class="sxs-lookup"><span data-stu-id="3be63-238">The *Event list* gives you a chronological list of [browser subsystem events](#cpu-utilization) that occurred during the selected span of time.</span></span> 

<span data-ttu-id="3be63-239">单击任何条目以填充 **该项目的 Selected** 事件详细信息图表。</span><span class="sxs-lookup"><span data-stu-id="3be63-239">Click on any entry to populate the **Selected event details** chart for that item.</span></span> <span data-ttu-id="3be63-240">具有嵌套事件/函数的条目将显示其执行函数所花费的包含的\*\* (\*\* 时间及其调用**) 的其他任何函数，以及仅在调用函数本身的正文中花费**的独占\*\* (时间（) 次）。</span><span class="sxs-lookup"><span data-stu-id="3be63-240">Entries with nested events / functions will show their **inclusive** (time spent executing the function *and* any other functions it called) and **exclusive** (time spent only within the body of the calling function itself) times displayed in the chart.</span></span>

<span data-ttu-id="3be63-241">右键单击任何项以打开上下文菜单以仅筛选时间线到该事件，并查看调试器 (或元素面板中负责事件的源代码[\*\*\*\*](./debugger.md)（如果适用) ）。 [\*\*\*\*](./elements.md)</span><span class="sxs-lookup"><span data-stu-id="3be63-241">Right-click on any entry to open the context menu to filter the timeline to only that event and view the source code responsible for the event in the [**Debugger**](./debugger.md) (or [**Elements**](./elements.md) panel, if applicable).</span></span>

### <span data-ttu-id="3be63-242">选定的日程表详细信息</span><span class="sxs-lookup"><span data-stu-id="3be63-242">Selected timeline details</span></span>

<span data-ttu-id="3be63-243">" *选定的时间线详细信息* "提供了选定时间跨度内包含非独占/独占事件时间的详细条形图。</span><span class="sxs-lookup"><span data-stu-id="3be63-243">The *Selected timeline details* provides a detailed bar graph of inclusive/exclusive event times during the selected time span.</span></span> <span data-ttu-id="3be63-244">当使用事件 (\*排序 \*) 按持续时间排序 **时**，运行时间最长的事件将在图中直观地突出。</span><span class="sxs-lookup"><span data-stu-id="3be63-244">When you sort by *Duration (inclusive)* using the **Event list sort control**, the longest running events will visually stand out in this chart.</span></span> 

### <span data-ttu-id="3be63-245">选定的事件详细信息</span><span class="sxs-lookup"><span data-stu-id="3be63-245">Selected event details</span></span>

<span data-ttu-id="3be63-246">此报告提供有关所选事件的详细信息，包括开始时间、执行\*\* 线程类型 (例如，下载 *、UI、\*\*呈现*) 以及\*\* 特定于特定事件类型的其他上下文详细信息。</span><span class="sxs-lookup"><span data-stu-id="3be63-246">This report provides further information about the selected event, including *Start time*, the executing thread type (for example, *Download*, *UI*, *Render*), and other contextual details specific to the specific event type.</span></span> <span data-ttu-id="3be63-247">例如， *事件侦听器* 类型提供指向回调函数和计划调用 *堆栈* 的 *调试程序链接*。</span><span class="sxs-lookup"><span data-stu-id="3be63-247">For example, *Event listener* types provide debugger links to the *Callback function* and *Scheduling call stack*.</span></span>

## <span data-ttu-id="3be63-248">JavaScript 调用堆栈</span><span class="sxs-lookup"><span data-stu-id="3be63-248">JavaScript call stacks</span></span>

![JavaScript 调用堆栈的性能计时](./media/performance_details_javascript.png)

<span data-ttu-id="3be63-250">JavaScript **调用堆栈** 选项卡为在选定时间范围内运行脚本函数提供 CPU 使用率信息和计时：</span><span class="sxs-lookup"><span data-stu-id="3be63-250">The **JavaScript call stacks** tab provides CPU usage information and timings for the script functions that ran during the selected time range:</span></span>

 <span data-ttu-id="3be63-251">列</span><span class="sxs-lookup"><span data-stu-id="3be63-251">Column</span></span> | <span data-ttu-id="3be63-252">描述</span><span class="sxs-lookup"><span data-stu-id="3be63-252">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3be63-253">函数名称</span><span class="sxs-lookup"><span data-stu-id="3be63-253">Function name</span></span> | <span data-ttu-id="3be63-254">浏览器或用户定义函数的名称。</span><span class="sxs-lookup"><span data-stu-id="3be63-254">Name of browser or user-defined function.</span></span>
<span data-ttu-id="3be63-255">非独占 CPU (%) </span><span class="sxs-lookup"><span data-stu-id="3be63-255">Inclusive CPU (%)</span></span> | <span data-ttu-id="3be63-256">此函数和此函数调用的函数中所选 CPU 活动的百分比。</span><span class="sxs-lookup"><span data-stu-id="3be63-256">Percentage of selected CPU activity in this function and in functions called by this function.</span></span>
<span data-ttu-id="3be63-257">独占 CPU (%) </span><span class="sxs-lookup"><span data-stu-id="3be63-257">Exclusive CPU (%)</span></span> | <span data-ttu-id="3be63-258">此函数中所选 CPU 活动的百分比，不包括此函数调用的函数中的活动。</span><span class="sxs-lookup"><span data-stu-id="3be63-258">Percentage of selected CPU activity in this function, excluding activity in functions called by this function.</span></span>
<span data-ttu-id="3be63-259">非独占 CPU (毫秒) </span><span class="sxs-lookup"><span data-stu-id="3be63-259">Inclusive CPU (ms)</span></span> | <span data-ttu-id="3be63-260">在此函数和此函数调用的函数中执行代码所花费的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-260">CPU time spent executing code in this function and in functions called by this function.</span></span>
<span data-ttu-id="3be63-261">独占 CPU (ms ms) </span><span class="sxs-lookup"><span data-stu-id="3be63-261">Exclusive CPU (ms)</span></span> | <span data-ttu-id="3be63-262">在此函数中执行代码所花费的 CPU 时间，不包括此函数调用的函数中的时间。</span><span class="sxs-lookup"><span data-stu-id="3be63-262">CPU time spent executing code in this function, excluding time in functions called by this function.</span></span>
<span data-ttu-id="3be63-263">URL</span><span class="sxs-lookup"><span data-stu-id="3be63-263">URL</span></span> | <span data-ttu-id="3be63-264">URL () 发生堆栈帧的位置。</span><span class="sxs-lookup"><span data-stu-id="3be63-264">URL(s) where stack frame occurred.</span></span> <span data-ttu-id="3be63-265">基于标准的 Web API (来自浏览器的函数调用) *标记为 [DOM]*。</span><span class="sxs-lookup"><span data-stu-id="3be63-265">Function calls originating from the browser (standards-based web APIs) are labeled as *[DOM]*.</span></span>

## <span data-ttu-id="3be63-266">快捷方式</span><span class="sxs-lookup"><span data-stu-id="3be63-266">Shortcuts</span></span>

| <span data-ttu-id="3be63-267">操作</span><span class="sxs-lookup"><span data-stu-id="3be63-267">Action</span></span>                         | <span data-ttu-id="3be63-268">快捷方式</span><span class="sxs-lookup"><span data-stu-id="3be63-268">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="3be63-269">启动/停止分析会话</span><span class="sxs-lookup"><span data-stu-id="3be63-269">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="3be63-270">导入分析会话</span><span class="sxs-lookup"><span data-stu-id="3be63-270">Import profiling session</span></span>       | `Ctrl` + `O` |
| <span data-ttu-id="3be63-271">导出分析会话</span><span class="sxs-lookup"><span data-stu-id="3be63-271">Export profiling session</span></span>       | `Ctrl` + `S` |

## <span data-ttu-id="3be63-272">已知问题</span><span class="sxs-lookup"><span data-stu-id="3be63-272">Known Issues</span></span>

### <span data-ttu-id="3be63-273">启动分析会话时出错</span><span class="sxs-lookup"><span data-stu-id="3be63-273">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="3be63-274">如果看到以下错误消息：在"\*\*\*\* 性能"工具中启动分析会话时出错，请按照以下步骤操作以寻找解决方法。</span><span class="sxs-lookup"><span data-stu-id="3be63-274">If you see this error message: **An error occurred while starting the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="3be63-275">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="3be63-275">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="3be63-276">在"运行"对话框中，输入**services.msc。**</span><span class="sxs-lookup"><span data-stu-id="3be63-276">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="3be63-278">找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。</span><span class="sxs-lookup"><span data-stu-id="3be63-278">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="3be63-280">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="3be63-280">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="3be63-282">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="3be63-282">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="3be63-283">现在，你应该能够开始分析。</span><span class="sxs-lookup"><span data-stu-id="3be63-283">You should now be able to begin profiling.</span></span>
![known-issues-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="3be63-285">是否仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="3be63-285">Still running into problems?</span></span> <span data-ttu-id="3be63-286">请使用"发送反馈"图标 **向我们发送反馈** ！</span><span class="sxs-lookup"><span data-stu-id="3be63-286">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)

### <span data-ttu-id="3be63-288">停止分析会话时出错。</span><span class="sxs-lookup"><span data-stu-id="3be63-288">An error occurred while stopping the profiling session.</span></span>

<span data-ttu-id="3be63-289">如果看到以下错误消息：在停止\*\*\*\* 性能工具中的分析会话时出错，请按照以下步骤操作以寻找解决方法。</span><span class="sxs-lookup"><span data-stu-id="3be63-289">If you see this error message: **An error occurred while stopping the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="3be63-290">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="3be63-290">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="3be63-291">在"运行"对话框中，输入**services.msc。**</span><span class="sxs-lookup"><span data-stu-id="3be63-291">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="3be63-293">找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。</span><span class="sxs-lookup"><span data-stu-id="3be63-293">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="3be63-295">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="3be63-295">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="3be63-297">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="3be63-297">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="3be63-298">现在，你应该能够开始分析。</span><span class="sxs-lookup"><span data-stu-id="3be63-298">You should now be able to begin profiling.</span></span>
![known-issues-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="3be63-300">是否仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="3be63-300">Still running into problems?</span></span> <span data-ttu-id="3be63-301">请使用"发送反馈"图标 **向我们发送反馈** ！</span><span class="sxs-lookup"><span data-stu-id="3be63-301">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)
