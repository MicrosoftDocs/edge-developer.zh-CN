---
description: 使用控制台 API 以编程方式调试和配置文件代码
title: DevTools - 控制台 - 控制台 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 控制台 api
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46a74b80b504358ff7dbea40970528c8e2b228cf
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232152"
---
# <span data-ttu-id="c3896-104">主机 API</span><span class="sxs-lookup"><span data-stu-id="c3896-104">Console API</span></span>

<span data-ttu-id="c3896-105">控制台 *API* 通过全局对象提供对 DevTools 控制台的命令行和编程访问， `console` 从而允许您：</span><span class="sxs-lookup"><span data-stu-id="c3896-105">The *Console API* provides command-line and programmatic access to the  DevTools Console through the global `console` object, allowing you to:</span></span>

 - <span data-ttu-id="c3896-106">[记录代码中的](#logging-custom-messages) 自定义消息</span><span class="sxs-lookup"><span data-stu-id="c3896-106">[Log custom messages](#logging-custom-messages) from you code</span></span>
 - <span data-ttu-id="c3896-107">[检查对象和元素并](#inspecting-objects-and-elements) 记录其信息</span><span class="sxs-lookup"><span data-stu-id="c3896-107">[Inspect objects and elements](#inspecting-objects-and-elements) and log their information</span></span>
 - <span data-ttu-id="c3896-108">[通过设置断言、](#testing-and-measuring) 计时器和计数器测试和测量代码</span><span class="sxs-lookup"><span data-stu-id="c3896-108">[Test and measure your code](#testing-and-measuring) by setting assertions, timers and counters</span></span>
 - <span data-ttu-id="c3896-109">[获取堆的快照](#taking-heap-snapshots) ，以评估运行代码的内存消耗并确定内存泄漏</span><span class="sxs-lookup"><span data-stu-id="c3896-109">[Take snapshots of the heap](#taking-heap-snapshots) to assess the memory consumption of your running code and identify memory leaks</span></span>
 - <span data-ttu-id="c3896-110">[跟踪调用堆栈](#tracing-callstacks) ，了解从何处调用代码</span><span class="sxs-lookup"><span data-stu-id="c3896-110">[Trace your callstacks](#tracing-callstacks) to understand where your code is being called from</span></span> 
 - <span data-ttu-id="c3896-111">[组织日志输出](#organizing-log-output) 以简化调试</span><span class="sxs-lookup"><span data-stu-id="c3896-111">[Organize your log output](#organizing-log-output) to streamline your debugging</span></span>

<span data-ttu-id="c3896-112">以下是 Microsoft Edge 当前支持的命令和格式参数。</span><span class="sxs-lookup"><span data-stu-id="c3896-112">The following are the commands and formatting parameters currently supported by Microsoft Edge.</span></span> <span data-ttu-id="c3896-113">它们在主要浏览器上类似地工作。</span><span class="sxs-lookup"><span data-stu-id="c3896-113">They work similarly on major browsers.</span></span>

## <span data-ttu-id="c3896-114">记录自定义消息</span><span class="sxs-lookup"><span data-stu-id="c3896-114">Logging custom messages</span></span>

<span data-ttu-id="c3896-115">代码可以将多种类型的自定义消息发送到控制台，包括：</span><span class="sxs-lookup"><span data-stu-id="c3896-115">Your code can send several types of custom messages to the console, including:</span></span>

<span data-ttu-id="c3896-116">消息类型</span><span class="sxs-lookup"><span data-stu-id="c3896-116">Message type</span></span>  | &nbsp;   |
:------------------- | :------ |
<span data-ttu-id="c3896-117">[\*\*error () \*\*](https://developer.mozilla.org/docs/Web/API/Console/error) and [ \*\*exception () \*\*](https://developer.mozilla.org/docs/Web/API/Console/error)</span><span class="sxs-lookup"><span data-stu-id="c3896-117">[**error()**](https://developer.mozilla.org/docs/Web/API/Console/error) and [**exception()**](https://developer.mozilla.org/docs/Web/API/Console/error)</span></span>| <span data-ttu-id="c3896-118">严重错误和故障</span><span class="sxs-lookup"><span data-stu-id="c3896-118">Critical errors and failures</span></span>
[**<span data-ttu-id="c3896-119">warn () </span><span class="sxs-lookup"><span data-stu-id="c3896-119">warn()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/warn) | <span data-ttu-id="c3896-120">可能的错误或意外行为</span><span class="sxs-lookup"><span data-stu-id="c3896-120">Possible errors or unexpected behavior</span></span> 
[**<span data-ttu-id="c3896-121">info () </span><span class="sxs-lookup"><span data-stu-id="c3896-121">info()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/info) | <span data-ttu-id="c3896-122">有用但非关键的信息</span><span class="sxs-lookup"><span data-stu-id="c3896-122">Useful, but non-critical information</span></span>
<span data-ttu-id="c3896-123">[\*\*log () \*\*](https://developer.mozilla.org/docs/Web/API/Console/log) and [ \*\*debug () \*\*](https://developer.mozilla.org/docs/Web/API/Console/log)</span><span class="sxs-lookup"><span data-stu-id="c3896-123">[**log()**](https://developer.mozilla.org/docs/Web/API/Console/log) and [**debug()**](https://developer.mozilla.org/docs/Web/API/Console/log)</span></span> | <span data-ttu-id="c3896-124">常规调试 (控制台中生成系统警报图标) </span><span class="sxs-lookup"><span data-stu-id="c3896-124">General debugging (without generating a system alert icon in the console)</span></span>

   
<span data-ttu-id="c3896-125">你可以对这些信息进行分组和筛选，以及从控制台面板中从 Microsoft Edge 生成的其他消息。</span><span class="sxs-lookup"><span data-stu-id="c3896-125">You can group and filter these along with the other messages generated from Microsoft Edge from the  Console panel.</span></span> <span data-ttu-id="c3896-126">所有自定义邮件方法都需要一个字符串 (消息) 可选格式替换参数。</span><span class="sxs-lookup"><span data-stu-id="c3896-126">All custom message methods require a string (message) parameter and optional format substitution parameters.</span></span> <span data-ttu-id="c3896-127">Microsoft Edge 支持以下格式选项：</span><span class="sxs-lookup"><span data-stu-id="c3896-127">Microsoft Edge supports the following formatting options:</span></span>

<span data-ttu-id="c3896-128">Format 参数</span><span class="sxs-lookup"><span data-stu-id="c3896-128">Format parameter</span></span> | &nbsp;
:------------------- | :--- |
**<span data-ttu-id="c3896-129">%b</span><span class="sxs-lookup"><span data-stu-id="c3896-129">%b</span></span>** | <span data-ttu-id="c3896-130">二进制文件</span><span class="sxs-lookup"><span data-stu-id="c3896-130">Binary</span></span>
**<span data-ttu-id="c3896-131">%c</span><span class="sxs-lookup"><span data-stu-id="c3896-131">%c</span></span>** | <span data-ttu-id="c3896-132">内联 CSS 样式 (请参阅下面的示例) </span><span class="sxs-lookup"><span data-stu-id="c3896-132">Inline CSS style (see example below)</span></span>
<span data-ttu-id="c3896-133">**%d** **、%i**</span><span class="sxs-lookup"><span data-stu-id="c3896-133">**%d**, **%i**</span></span> | <span data-ttu-id="c3896-134">整型</span><span class="sxs-lookup"><span data-stu-id="c3896-134">Integer</span></span> 
**<span data-ttu-id="c3896-135">%f</span><span class="sxs-lookup"><span data-stu-id="c3896-135">%f</span></span>** | <span data-ttu-id="c3896-136">Float</span><span class="sxs-lookup"><span data-stu-id="c3896-136">Float</span></span>  
**<span data-ttu-id="c3896-137">%s</span><span class="sxs-lookup"><span data-stu-id="c3896-137">%s</span></span>** | <span data-ttu-id="c3896-138">字符串</span><span class="sxs-lookup"><span data-stu-id="c3896-138">String</span></span> 
**<span data-ttu-id="c3896-139">%x</span><span class="sxs-lookup"><span data-stu-id="c3896-139">%x</span></span>** | <span data-ttu-id="c3896-140">十六进制</span><span class="sxs-lookup"><span data-stu-id="c3896-140">Hexadecimal</span></span> 
**<span data-ttu-id="c3896-141">%e</span><span class="sxs-lookup"><span data-stu-id="c3896-141">%e</span></span>** | <span data-ttu-id="c3896-142">Exponent</span><span class="sxs-lookup"><span data-stu-id="c3896-142">Exponent</span></span> 

<span data-ttu-id="c3896-143">例如，下面显示了如何在日志消息中包括字符串和整数变量：</span><span class="sxs-lookup"><span data-stu-id="c3896-143">For example, here's how you would include string and integer variables in your log message:</span></span>

```javascript
var myText = 'pieces';
var myVal = 5;
console.log("The number of %s is %d.", myText, myVal);
```

>`The number of pieces is 5.`

<span data-ttu-id="c3896-144">下面介绍如何将绿色突出显示效果添加到具有内联 CSS `%c` () ：</span><span class="sxs-lookup"><span data-stu-id="c3896-144">And here's how you might add a green highlight effect to a log message with inline CSS (`%c`):</span></span>

```javascript
console.log("%cHighlight this log message in green", "background-color: #10ff00; text-transform: uppercase;");
```

![具有内联样式的控制台日志](../media/console_api_css.png)

## <span data-ttu-id="c3896-146">检查对象和元素</span><span class="sxs-lookup"><span data-stu-id="c3896-146">Inspecting objects and elements</span></span>

<span data-ttu-id="c3896-147">可检查对象显示在具有可展开节点的折叠树视图中的控制台中。</span><span class="sxs-lookup"><span data-stu-id="c3896-147">Inspectable objects appear in the console in a collapsed tree view with expandable nodes.</span></span> <span data-ttu-id="c3896-148">控制台检测是发送 DOM 节点 (div) 还是 JavaScript 对象 (如事件) ，并自动将其显示为检测到的类型。</span><span class="sxs-lookup"><span data-stu-id="c3896-148">The console detects whether you are sending a DOM node (like a div) or a JavaScript object (like an event) and displays them as the detected type automatically.</span></span>

<span data-ttu-id="c3896-149">还可以强制特定输出：</span><span class="sxs-lookup"><span data-stu-id="c3896-149">You can also force a specific output:</span></span>

<span data-ttu-id="c3896-150">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-150">Command</span></span> | &nbsp;
:------------------- | :--- |
[**<span data-ttu-id="c3896-151">dir () </span><span class="sxs-lookup"><span data-stu-id="c3896-151">dir()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/dir) | <span data-ttu-id="c3896-152">显示为可检查的 JavaScript 对象</span><span class="sxs-lookup"><span data-stu-id="c3896-152">Displays as inspectable JavaScript object</span></span>
[**<span data-ttu-id="c3896-153">dirxml () </span><span class="sxs-lookup"><span data-stu-id="c3896-153">dirxml()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/dirxml) | <span data-ttu-id="c3896-154">显示为可检查 DOM 节点</span><span class="sxs-lookup"><span data-stu-id="c3896-154">Displays as inspectable DOM node</span></span>

<span data-ttu-id="c3896-155">例如，尝试打开控制台并比较此页面上 `<div id='main'>` 元素的以下输出：</span><span class="sxs-lookup"><span data-stu-id="c3896-155">For example, try opening the console and compare the following outputs for the `<div id='main'>` element on this page:</span></span>

```javascript
console.dir(document.querySelector('#main'));
console.dirxml(document.querySelector('#main'));
```

!["dir"与"dirxml"输出的比较](../media/console_api_dir.png)

### <span data-ttu-id="c3896-157">选择"元素" **面板中的** 元素</span><span class="sxs-lookup"><span data-stu-id="c3896-157">Selecting an element in the **Elements** panel</span></span>

<span data-ttu-id="c3896-158">可以直接从控制台中选择页面的 HTML 树上下文中的元素，以便立即进行布局和样式调试。</span><span class="sxs-lookup"><span data-stu-id="c3896-158">You can select an element within the HTML tree context of the page directly from the console for immediate layout and style debugging.</span></span>

<span data-ttu-id="c3896-159">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-159">Command</span></span> | &nbsp;
:------------------- | :--- |
**<span data-ttu-id="c3896-160">选择 () </span><span class="sxs-lookup"><span data-stu-id="c3896-160">select()</span></span>** | <span data-ttu-id="c3896-161">切换到元素 **面板** ，将焦点设置到指定的元素。</span><span class="sxs-lookup"><span data-stu-id="c3896-161">Switches to the **Elements** panel and sets focus to the specified element.</span></span>

<span data-ttu-id="c3896-162">例如，如果在此页面上打开控制台并键入：</span><span class="sxs-lookup"><span data-stu-id="c3896-162">For example, if you open the console on this page and type:</span></span>

```javascript
console.select(document.querySelector("body"));
```

<span data-ttu-id="c3896-163">如果 DevTools 尚未 (，它将切换到"元素"面板) 将[*HTML*](../elements.md#html-tree-view)树视图中的焦点设置为指定的元素。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c3896-163">The DevTools will switch to the **Elements** panel (if its not already the current) and set focus in the [*HTML tree view*](../elements.md#html-tree-view) to the specified element.</span></span>

!["select"方法的示例](../media/console_api_select.png)

## <span data-ttu-id="c3896-165">测试和衡量</span><span class="sxs-lookup"><span data-stu-id="c3896-165">Testing and measuring</span></span>

### <span data-ttu-id="c3896-166">测试代码</span><span class="sxs-lookup"><span data-stu-id="c3896-166">Testing your code</span></span>

<span data-ttu-id="c3896-167">将控制台 API 测试断言添加到代码中，以便当代码在浏览器中运行时进行单元测试和调试。</span><span class="sxs-lookup"><span data-stu-id="c3896-167">Add Console API test assertions to your code for unit testing and debugging your code as it runs in the browser.</span></span>

<span data-ttu-id="c3896-168">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-168">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="c3896-169">assert () </span><span class="sxs-lookup"><span data-stu-id="c3896-169">assert()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/assert) | <span data-ttu-id="c3896-170">如果提供的表达式计算结果为 *false，* 则记录控制台错误消息。</span><span class="sxs-lookup"><span data-stu-id="c3896-170">Logs a console error message if the provided expression evaluates to *false*.</span></span>

<span data-ttu-id="c3896-171">除了作为可测试断言提供的逻辑表达式之外，还可以添加可选消息和格式参数，就像用于其他自定义控制台 [消息一样](#logging-custom-messages)。</span><span class="sxs-lookup"><span data-stu-id="c3896-171">In addition to the logical expression you supply as the testable assertion, you can add an optional message and formatting parameters as you would use with other [custom console messages](#logging-custom-messages).</span></span> <span data-ttu-id="c3896-172">例如：</span><span class="sxs-lookup"><span data-stu-id="c3896-172">For example:</span></span>

```javascript
var x = 26.8;
console.assert(x < 25, 'The value of x is %f (it is NOT less than %i)', x, 25);
```

!["assert"方法的示例](../media/console_api_assert.png)

### <span data-ttu-id="c3896-174">计算代码中的执行次数</span><span class="sxs-lookup"><span data-stu-id="c3896-174">Counting executions in your code</span></span>

<span data-ttu-id="c3896-175">可以在代码中设置计数器，以跟踪周围代码的执行次数。</span><span class="sxs-lookup"><span data-stu-id="c3896-175">You can set counters in your code to keep track of how many times the surrounding code gets executed.</span></span> <span data-ttu-id="c3896-176">设置计数器有助于确保代码如期运行，并帮助您诊断性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="c3896-176">Setting counters can help ensure your code is running as expected and assist you in diagnosing performance bottlenecks.</span></span>

<span data-ttu-id="c3896-177">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-177">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="c3896-178">count () </span><span class="sxs-lookup"><span data-stu-id="c3896-178">count()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/count) | <span data-ttu-id="c3896-179">为给定标签增加并记录 ( \*次数 \* 。</span><span class="sxs-lookup"><span data-stu-id="c3896-179">Increments and logs the number of times *count()* for the given label has been executed.</span></span>
[**<span data-ttu-id="c3896-180">countReset () </span><span class="sxs-lookup"><span data-stu-id="c3896-180">countReset()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/countReset) | <span data-ttu-id="c3896-181">将给定计数器标签的计数重置为零。</span><span class="sxs-lookup"><span data-stu-id="c3896-181">Resets the count to zero for the given counter label.</span></span>

<span data-ttu-id="c3896-182">例如，在控制台中执行以下行：</span><span class="sxs-lookup"><span data-stu-id="c3896-182">For example, executing the following lines in console:</span></span>

```javascript
console.count('My Counter');
console.count('My Counter');
console.countReset('My Counter');
console.count('My Counter');
```

 <span data-ttu-id="c3896-183">.</span><span class="sxs-lookup"><span data-stu-id="c3896-183">.</span></span> <span data-ttu-id="c3896-184">.</span><span class="sxs-lookup"><span data-stu-id="c3896-184">.</span></span> <span data-ttu-id="c3896-185">.</span><span class="sxs-lookup"><span data-stu-id="c3896-185">.</span></span> <span data-ttu-id="c3896-186">将导致：</span><span class="sxs-lookup"><span data-stu-id="c3896-186">will result in:</span></span>
> <span data-ttu-id="c3896-187">我的计数器：1</span><span class="sxs-lookup"><span data-stu-id="c3896-187">My Counter: 1</span></span>

### <span data-ttu-id="c3896-188">对代码进行计时</span><span class="sxs-lookup"><span data-stu-id="c3896-188">Timing your code</span></span>

<span data-ttu-id="c3896-189">使用标记的计时器检测代码，以测量完成给定操作所花的时间。</span><span class="sxs-lookup"><span data-stu-id="c3896-189">Instrument your code with labeled timers to measure how long it takes to complete a given operation.</span></span>

<span data-ttu-id="c3896-190">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-190">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="c3896-191">time () </span><span class="sxs-lookup"><span data-stu-id="c3896-191">time()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/time) | <span data-ttu-id="c3896-192">使用给定标签启动计时器。</span><span class="sxs-lookup"><span data-stu-id="c3896-192">Starts a timer with the given label.</span></span>
[**<span data-ttu-id="c3896-193">timeEnd () </span><span class="sxs-lookup"><span data-stu-id="c3896-193">timeEnd()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/timeEnd) | <span data-ttu-id="c3896-194">使用给定标签结束计时器，并报告已用时间 (毫秒) 。</span><span class="sxs-lookup"><span data-stu-id="c3896-194">Ends the timer with the given label and reports the time elapsed (in milliseconds).</span></span>
[**<span data-ttu-id="c3896-195">timeStamp () </span><span class="sxs-lookup"><span data-stu-id="c3896-195">timeStamp()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/timeStamp) | <span data-ttu-id="c3896-196">报告当前系统的时间 (毫秒) 。</span><span class="sxs-lookup"><span data-stu-id="c3896-196">Reports the current system time (in milliseconds).</span></span>

<span data-ttu-id="c3896-197">例如，请尝试在控制台中执行以下行：</span><span class="sxs-lookup"><span data-stu-id="c3896-197">For example, try executing the following lines in console:</span></span>

```javascript
console.time('My Timer');
console.timeEnd('My Timer');
```

### <span data-ttu-id="c3896-198">获取堆快照</span><span class="sxs-lookup"><span data-stu-id="c3896-198">Taking heap snapshots</span></span>

<span data-ttu-id="c3896-199">获取堆的快照，以评估运行代码的内存消耗并确定内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="c3896-199">Take snapshots of the heap to assess the memory consumption of your running code and identify memory leaks.</span></span>

<span data-ttu-id="c3896-200">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-200">Command</span></span> | &nbsp;
:------------ | :-------------
**<span data-ttu-id="c3896-201">takeHeapSnapshot () </span><span class="sxs-lookup"><span data-stu-id="c3896-201">takeHeapSnapshot()</span></span>** | <span data-ttu-id="c3896-202">捕获有关当前 JavaScript 堆及其已分配对象的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c3896-202">Captures details about the current JavaScript heap and its allocated objects.</span></span>

<span data-ttu-id="c3896-203">必须运行 DevTools [](../memory.md#toolbar)内存探查器才能获取堆快照。</span><span class="sxs-lookup"><span data-stu-id="c3896-203">The  DevTools [memory profiler](../memory.md#toolbar) must be running in order to take heap snapshots.</span></span> <span data-ttu-id="c3896-204">每个快照将在"内存"面板的 [*"快照"摘要*](../memory.md#snapshot-summary) 中显示为 [**磁贴，以**](../memory.md) 进一步检查。</span><span class="sxs-lookup"><span data-stu-id="c3896-204">Each snapshot will appear as a tile in the [*Snapshot summary*](../memory.md#snapshot-summary) of the [**Memory**](../memory.md) panel for further inspection.</span></span>

## <span data-ttu-id="c3896-205">跟踪调用代码</span><span class="sxs-lookup"><span data-stu-id="c3896-205">Tracing callstacks</span></span>

<span data-ttu-id="c3896-206">了解代码的调用位置、正在运行的代码以及执行所花的时间在分析速度慢或意外行为时可能很有用。</span><span class="sxs-lookup"><span data-stu-id="c3896-206">Understanding where your code is being called from, what code is running, and how long that execution takes can be useful in analyzing slowness or unexpected behavior.</span></span> <span data-ttu-id="c3896-207">堆栈跟踪显示代码从跟踪请求向上到达路径时所经过的执行路径。</span><span class="sxs-lookup"><span data-stu-id="c3896-207">A stack trace shows you the execution path your code took to reach it, from the trace request upward through the path.</span></span> 

<span data-ttu-id="c3896-208">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-208">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="c3896-209">trace () </span><span class="sxs-lookup"><span data-stu-id="c3896-209">trace()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/trace) | <span data-ttu-id="c3896-210">输出当前脚本执行调用堆栈的跟踪。</span><span class="sxs-lookup"><span data-stu-id="c3896-210">Outputs a trace of the current script execution callstack.</span></span>

<span data-ttu-id="c3896-211">例如，在控制台中运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="c3896-211">For example, running the following code in the console:</span></span>

```javascript
function a(){
  c();
}
function b(){
  c();
}
function c(){
  console.trace()
}
function d(){
  b();
}

a();
d();
```

<span data-ttu-id="c3896-212">.</span><span class="sxs-lookup"><span data-stu-id="c3896-212">.</span></span> <span data-ttu-id="c3896-213">.</span><span class="sxs-lookup"><span data-stu-id="c3896-213">.</span></span> <span data-ttu-id="c3896-214">.</span><span class="sxs-lookup"><span data-stu-id="c3896-214">.</span></span> <span data-ttu-id="c3896-215">将输出以下堆栈跟踪：</span><span class="sxs-lookup"><span data-stu-id="c3896-215">will output the following stack traces:</span></span>
> <span data-ttu-id="c3896-216"> (eval code：8：3) at a (eval code：2：3) at eval code (eval code：14：1) 的 console. ( trace () </span><span class="sxs-lookup"><span data-stu-id="c3896-216">console.trace() at c (eval code:8:3) at a (eval code:2:3) at eval code (eval code:14:1)</span></span>
> 
> <span data-ttu-id="c3896-217">console.trace () at c (eval code：8：3) at b (eval code：5：3) at d (eval code：11：3) at eval code (eval code：15：1) </span><span class="sxs-lookup"><span data-stu-id="c3896-217">console.trace() at c (eval code:8:3) at b (eval code:5:3) at d (eval code:11:3) at eval code (eval code:15:1)</span></span>

## <span data-ttu-id="c3896-218">组织日志输出</span><span class="sxs-lookup"><span data-stu-id="c3896-218">Organizing log output</span></span>

<span data-ttu-id="c3896-219">若要清除所有以前的控制台输出，请使用 \*console.clear () \* (或 `CTRL + L`) 。</span><span class="sxs-lookup"><span data-stu-id="c3896-219">To simply clear all previous console output, use *console.clear()* (or `CTRL + L`).</span></span> <span data-ttu-id="c3896-220">这不会清除控制台命令历史记录的后退 (你仍可以使用向上和向下箭头键遍历它) 。</span><span class="sxs-lookup"><span data-stu-id="c3896-220">This does not clear the backstack of your console command history (you can still traverse it with the up and down arrow keys).</span></span>

<span data-ttu-id="c3896-221">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-221">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="c3896-222">clear () </span><span class="sxs-lookup"><span data-stu-id="c3896-222">clear()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/clear) | <span data-ttu-id="c3896-223">清除所有以前的控制台输出。</span><span class="sxs-lookup"><span data-stu-id="c3896-223">Clears all previous console output.</span></span>

<span data-ttu-id="c3896-224">如果代码输出大量控制台消息，可以使用以下命令直观地将它们组织到嵌套块中：</span><span class="sxs-lookup"><span data-stu-id="c3896-224">If your code outputs a lot of console messages, you can visually organize them into nested blocks with the following commands:</span></span>

 <span data-ttu-id="c3896-225">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-225">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="c3896-226">group () </span><span class="sxs-lookup"><span data-stu-id="c3896-226">group()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/group) | <span data-ttu-id="c3896-227">使用指定的可选 (开始控制台输出的新嵌套) 级别。</span><span class="sxs-lookup"><span data-stu-id="c3896-227">Starts a new level of nesting for console output with the specified (optional) label.</span></span>
[**<span data-ttu-id="c3896-228">groupCollapsed () </span><span class="sxs-lookup"><span data-stu-id="c3896-228">groupCollapsed()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/groupCollapsed) | <span data-ttu-id="c3896-229">为具有指定 (可选) 标签的控制台输出启动新的嵌套级别，但分组控件默认为折叠，并且必须通过单击箭头控件) 来展开 (以显示子输出。</span><span class="sxs-lookup"><span data-stu-id="c3896-229">Starts a new level of nesting for console output with the specified (optional) label, however the grouping control is collapsed by default and must be expanded (by clicking on the arrow control) to display the child output.</span></span>
[**<span data-ttu-id="c3896-230">groupEnd () </span><span class="sxs-lookup"><span data-stu-id="c3896-230">groupEnd()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/groupEnd) | <span data-ttu-id="c3896-231">结束指定标签的嵌套组。</span><span class="sxs-lookup"><span data-stu-id="c3896-231">Ends the nesting group for the specified label.</span></span>

<span data-ttu-id="c3896-232">例如，尝试在控制台中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="c3896-232">For example, try entering the following commands in the console:</span></span>

```javascript
console.groupCollapsed('Group 1');
console.log('In Group 1');
console.groupCollapsed('Group 1.1');
console.log('In Group 1.1');
console.groupEnd('Group 1.1');
console.groupEnd('Group 1');
console.log('No longer in a group');
```

<span data-ttu-id="c3896-233">.</span><span class="sxs-lookup"><span data-stu-id="c3896-233">.</span></span> <span data-ttu-id="c3896-234">.</span><span class="sxs-lookup"><span data-stu-id="c3896-234">.</span></span> <span data-ttu-id="c3896-235">.</span><span class="sxs-lookup"><span data-stu-id="c3896-235">.</span></span> <span data-ttu-id="c3896-236">然后展开组 *1* 和 *组 1.1* 控件以查看日志注释的嵌套方式：</span><span class="sxs-lookup"><span data-stu-id="c3896-236">and then expand the *Group 1* and *Group 1.1* controls to see how the log comments are nested:</span></span>

![对控制台中的邮件进行分组](../media/console_api_group.png)

<span data-ttu-id="c3896-238">有时，以表格形式可视化 JavaScript 对象或数组简单列表。</span><span class="sxs-lookup"><span data-stu-id="c3896-238">Sometimes its easier to visualize a JavaScript object or array in tabular form, rather than a flat list.</span></span> <span data-ttu-id="c3896-239">为此，可以使用 \*console.table () \* 命令：</span><span class="sxs-lookup"><span data-stu-id="c3896-239">For that, you can use the *console.table()* command:</span></span>

<span data-ttu-id="c3896-240">命令</span><span class="sxs-lookup"><span data-stu-id="c3896-240">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="c3896-241">table () </span><span class="sxs-lookup"><span data-stu-id="c3896-241">table()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/table) | <span data-ttu-id="c3896-242">以表格形式将提供的数组或对象输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="c3896-242">Outputs the supplied array or object to the console in tabular form.</span></span>

<span data-ttu-id="c3896-243">例如，以下对象数组：</span><span class="sxs-lookup"><span data-stu-id="c3896-243">For example, the following object array:</span></span>

```javascript
var orders = [{'Size':'XL', 'Quantity':1},{'Size':'M', 'Quantity':3}, {'Size':'L', 'Quantity':2}];
console.table(orders);
```

<span data-ttu-id="c3896-244">.</span><span class="sxs-lookup"><span data-stu-id="c3896-244">.</span></span> <span data-ttu-id="c3896-245">.</span><span class="sxs-lookup"><span data-stu-id="c3896-245">.</span></span> <span data-ttu-id="c3896-246">.</span><span class="sxs-lookup"><span data-stu-id="c3896-246">.</span></span> <span data-ttu-id="c3896-247">将在控制台中呈现为此表：</span><span class="sxs-lookup"><span data-stu-id="c3896-247">will render as this table in the console:</span></span>

![在控制台中将对象数组显示为表](../media/console_api_table.png)
