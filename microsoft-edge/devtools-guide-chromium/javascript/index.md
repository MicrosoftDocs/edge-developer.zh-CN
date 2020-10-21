---
description: 了解如何使用 Microsoft Edge DevTools 查找和修复 JavaScript bug。
title: 在 Microsoft Edge DevTools 中开始使用调试 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: bff87ca36c484689134f284514bbab353b8b99b6
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124787"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <span data-ttu-id="f7dca-104">在 Microsoft Edge DevTools 中开始使用调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="f7dca-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f7dca-105">本教程将指导你在 DevTools 中调试 JavaScript 问题的基本工作流。</span><span class="sxs-lookup"><span data-stu-id="f7dca-105">This tutorial teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <span data-ttu-id="f7dca-106">步骤1：重现 bug</span><span class="sxs-lookup"><span data-stu-id="f7dca-106">Step 1: Reproduce the bug</span></span>  

<span data-ttu-id="f7dca-107">在调试的第一步中始终是查找始终重现 bug 的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="f7dca-107">Finding a series of actions that consistently reproduces a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="f7dca-108">选择 " **打开演示**"。</span><span class="sxs-lookup"><span data-stu-id="f7dca-108">Choose **Open Demo**.</span></span>  <span data-ttu-id="f7dca-109">保留 `Control` \ (Windows、Linux \ ) 或 `Command` \ (macOS \ ) 并在新选项卡中打开演示。</span><span class="sxs-lookup"><span data-stu-id="f7dca-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and open the demo in a new tab.</span></span>  
    
    [<span data-ttu-id="f7dca-110">打开演示</span><span class="sxs-lookup"><span data-stu-id="f7dca-110">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="f7dca-111">`5`在 "**数字 1** " 文本框中输入。</span><span class="sxs-lookup"><span data-stu-id="f7dca-111">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="f7dca-112">`1`在 "**数字 2** " 文本框中输入。</span><span class="sxs-lookup"><span data-stu-id="f7dca-112">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="f7dca-113">选择 " **添加号码 1" 和 "数字 2**"。</span><span class="sxs-lookup"><span data-stu-id="f7dca-113">Choose **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="f7dca-114">按钮下方的标签显示 "" `5 + 1 = 51` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-114">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="f7dca-115">结果应为 `6` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-115">The result should be `6`.</span></span>  <span data-ttu-id="f7dca-116">这是你要修复的 bug。</span><span class="sxs-lookup"><span data-stu-id="f7dca-116">This is the bug you are going to fix.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       <span data-ttu-id="f7dca-118">Is 的结果 `5 + 1` 是 `51` ，但应该</span><span class="sxs-lookup"><span data-stu-id="f7dca-118">The result of `5 + 1` is `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <span data-ttu-id="f7dca-119">步骤2：熟悉 "源" 面板 UI</span><span class="sxs-lookup"><span data-stu-id="f7dca-119">Step 2: Get familiar with the Sources panel UI</span></span>  

<span data-ttu-id="f7dca-120">DevTools 为不同的任务提供了许多不同的工具，例如更改 CSS、分析页面加载性能和监视网络请求。</span><span class="sxs-lookup"><span data-stu-id="f7dca-120">DevTools provides a lot of different tools for different tasks, such as changing CSS, profiling page load performance, and monitoring network requests.</span></span>  <span data-ttu-id="f7dca-121">" **源** " 面板是你在其中调试 JavaScript 的位置。</span><span class="sxs-lookup"><span data-stu-id="f7dca-121">The **Sources** panel is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="f7dca-122">按 `Control` + `Shift` + `J` \ (Windows、Linux \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f7dca-122">Open DevTools by pressing `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) .</span></span>  <span data-ttu-id="f7dca-123">此快捷方式将打开 **控制台** 面板。</span><span class="sxs-lookup"><span data-stu-id="f7dca-123">This shortcut opens the **Console** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="f7dca-125">**控制台**面板</span><span class="sxs-lookup"><span data-stu-id="f7dca-125">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f7dca-126">单击 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f7dca-126">Click the **Sources** tab.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="f7dca-128">" **源** " 面板</span><span class="sxs-lookup"><span data-stu-id="f7dca-128">The **Sources** panel</span></span>  
    :::image-end:::  
    
<span data-ttu-id="f7dca-129">" **源** " 面板 UI 有3个部分。</span><span class="sxs-lookup"><span data-stu-id="f7dca-129">The **Sources** panel UI has 3 parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="f7dca-131">" **源** " 面板 UI 的3个部分</span><span class="sxs-lookup"><span data-stu-id="f7dca-131">The 3 parts of the **Sources** panel UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="f7dca-132">" **文件导航器** " 窗格 \ (上图中的第一节 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-132">The **File Navigator** pane \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="f7dca-133">页面请求的每个文件都在此处列出。</span><span class="sxs-lookup"><span data-stu-id="f7dca-133">Every file that the page requests is listed here.</span></span>  
1.  <span data-ttu-id="f7dca-134">" **代码编辑器** " 窗格 \ (上图中的第二部分 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-134">The **Code Editor** pane \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="f7dca-135">在 " **文件导航器** " 窗格中选择文件后，该文件的内容将显示在此处。</span><span class="sxs-lookup"><span data-stu-id="f7dca-135">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="f7dca-136">**JavaScript 调试**窗格 \ 上图中 (第3节 ) 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-136">The **JavaScript Debugging** pane \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="f7dca-137">用于检查页面的 JavaScript 的各种工具。</span><span class="sxs-lookup"><span data-stu-id="f7dca-137">Various tools for inspecting the JavaScript for the page.</span></span>  <span data-ttu-id="f7dca-138">如果 DevTools 窗口宽，此窗格将显示在 " **代码编辑器** " 窗格的右侧。</span><span class="sxs-lookup"><span data-stu-id="f7dca-138">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  
    
## <span data-ttu-id="f7dca-139">步骤3：使用断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="f7dca-139">Step 3: Pause the code with a breakpoint</span></span>  

<span data-ttu-id="f7dca-140">调试此类问题的常见方法是将许多语句插入到 `console.log()` 代码中，以便在脚本运行时检查值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-140">A common method for debugging a problem like this is to insert a lot of `console.log()` statements into the code, in order to inspect values as the script runs.</span></span>  <span data-ttu-id="f7dca-141">例如：</span><span class="sxs-lookup"><span data-stu-id="f7dca-141">For example:</span></span>  

```javascript
function updateLabel() {
    var addend1 = getNumber1();
    console.log('addend1:', addend1);
    var addend2 = getNumber2();
    console.log('addend2:', addend2);
    var sum = addend1 + addend2;
    console.log('sum:', sum);
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
}
```  

<span data-ttu-id="f7dca-142">此 `console.log()` 方法可能会使作业完成，但 **断点** 能够更快地完成工作。</span><span class="sxs-lookup"><span data-stu-id="f7dca-142">The `console.log()` method may get the job done, but **breakpoints** are able to get it done faster.</span></span>  <span data-ttu-id="f7dca-143">断点使你可以在运行时中间暂停代码，并在该时刻检查所有值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-143">A breakpoint lets you pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="f7dca-144">与方法相比，断点有几个优点 `console.log()` ：</span><span class="sxs-lookup"><span data-stu-id="f7dca-144">Breakpoints have a few advantages over the `console.log()` method:</span></span>  

*   <span data-ttu-id="f7dca-145">通过 `console.log()` ，你需要手动打开源代码，查找相关代码，插入 `console.log()` 语句，然后重新加载页面，以便在控制台中查看消息。</span><span class="sxs-lookup"><span data-stu-id="f7dca-145">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then reload the page in order to see the messages in the Console.</span></span>  <span data-ttu-id="f7dca-146">利用断点，您可以暂停在相关代码上，而无需了解代码的结构。</span><span class="sxs-lookup"><span data-stu-id="f7dca-146">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="f7dca-147">在你的 `console.log()` 语句中，你需要显式指定要检查的每个值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-147">In your `console.log()` statements you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="f7dca-148">有了断点，DevTools 将显示当时的所有变量的值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-148">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="f7dca-149">有时，你甚至不知道的代码会影响你的代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-149">Sometimes there are variables affecting your code that you are not even aware of.</span></span>  

<span data-ttu-id="f7dca-150">简言之，断点可帮助你查找和修复 bug，比方法更快 `console.log()` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-150">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="f7dca-151">如果返回一个步骤并考虑应用的工作方式，则可以让你有兴趣地猜测) 的 sum (`5 + 1 = 51` 在 `click` 与 " **Add Number 1" 和 "number 2** " 按钮关联的事件侦听器中得到计算。</span><span class="sxs-lookup"><span data-stu-id="f7dca-151">If you take a step back and think about how the app works, you are able to make an educated guess that the incorrect sum (`5 + 1 = 51`) gets computed in the `click` event listener that is associated to the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="f7dca-152">因此，你可能希望在侦听器运行的时间周围暂停代码 `click` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-152">Therefore, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="f7dca-153">**事件侦听器断点** 使你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f7dca-153">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="f7dca-154">在 " **JavaScript 调试** " 窗格中，选择 " **事件侦听器断点** " 以展开该部分。</span><span class="sxs-lookup"><span data-stu-id="f7dca-154">In the **JavaScript Debugging** pane, choose **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="f7dca-155">DevTools 显示可展开的事件类别（如 **动画** 和 **剪贴板**）的列表。</span><span class="sxs-lookup"><span data-stu-id="f7dca-155">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="f7dca-156">在 **鼠标** 事件类别旁边，选择 **展开** \ (![ 展开图标 ][ImageExpandIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-156">Next to the **Mouse** event category, choose **Expand** \(![Expand icon][ImageExpandIcon]\).</span></span>  <span data-ttu-id="f7dca-157">DevTools 显示鼠标事件（如 **单击** 和 **mousedown**）的列表。</span><span class="sxs-lookup"><span data-stu-id="f7dca-157">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="f7dca-158">每个事件旁边都有一个复选框。</span><span class="sxs-lookup"><span data-stu-id="f7dca-158">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="f7dca-159">选中 " **单击** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="f7dca-159">Check the **click** checkbox.</span></span>  <span data-ttu-id="f7dca-160">DevTools 现已设置为在 *任何* `click` 事件侦听器运行时自动暂停。</span><span class="sxs-lookup"><span data-stu-id="f7dca-160">DevTools is now set up to automatically pause when *any* `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="f7dca-162">已启用 " **单击** " 复选框</span><span class="sxs-lookup"><span data-stu-id="f7dca-162">The **click** checkbox is enabled</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f7dca-163">返回演示，再次选择 " **添加号码 1" 和 "数字 2** "。</span><span class="sxs-lookup"><span data-stu-id="f7dca-163">Back on the demo, choose **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="f7dca-164">DevTools 暂停演示并突出显示 " **源** " 面板中的一行代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-164">DevTools pauses the demo and highlights a line of code in the **Sources** panel.</span></span>  <span data-ttu-id="f7dca-165">DevTools 应在的行16中暂停 `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-165">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="f7dca-166">如果在其他代码行上暂停，请按 " **恢复脚本执行** " \ (![ 恢复脚本执行 ][ImageResumeIcon] \ ) ，直到暂停在正确的行上。</span><span class="sxs-lookup"><span data-stu-id="f7dca-166">If you pause on a different line of code, press **Resume Script Execution** \(![Resume Script Execution][ImageResumeIcon]\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="f7dca-167">如果你在其他行暂停，则你有一个浏览器扩展，它 `click` 在你访问的每个页面上注册一个事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="f7dca-167">If you paused on a different line, you have a browser extension that registers a `click` event listener on every page that you visit.</span></span>  <span data-ttu-id="f7dca-168">已暂停在扩展的 `click` 侦听器中。</span><span class="sxs-lookup"><span data-stu-id="f7dca-168">You were paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="f7dca-169">如果你使用 InPrivate 模式 **浏览 private**（这将禁用所有扩展），你可能会看到每次都在所需的代码行上暂停。</span><span class="sxs-lookup"><span data-stu-id="f7dca-169">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="f7dca-170">**事件侦听器断点** 只是 DevTools 中可用的多种类型的断点之一。</span><span class="sxs-lookup"><span data-stu-id="f7dca-170">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="f7dca-171">它值得 memorizing 所有不同类型，因为每种类型最终有助于尽可能快地调试不同的方案。</span><span class="sxs-lookup"><span data-stu-id="f7dca-171">It is worth memorizing all the different types, because each type ultimately helps you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <span data-ttu-id="f7dca-172">步骤4：逐句通过代码</span><span class="sxs-lookup"><span data-stu-id="f7dca-172">Step 4: Step through the code</span></span>  

<span data-ttu-id="f7dca-173">Bug 的一个常见原因是，脚本的运行顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="f7dca-173">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="f7dca-174">单步执行你的代码，使你能够遍历代码的运行时，一次一行，然后以与预期不同的顺序确定其运行的确切位置。</span><span class="sxs-lookup"><span data-stu-id="f7dca-174">Stepping through your code enables you to walk through the runtime of your code, one line at a time, and figure out exactly where it is running in a different order than you expected.</span></span>  <span data-ttu-id="f7dca-175">立即试用：</span><span class="sxs-lookup"><span data-stu-id="f7dca-175">Try it now:</span></span>  

1.  <span data-ttu-id="f7dca-176">选择 " **逐过程按下一个函数调用** \" ("按 ![ 步骤 over 下一个函数调用 ][ImageOverIcon] \" ) 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-176">Choose **Step over next function call** \(![Step over next function call][ImageOverIcon]\).</span></span>  <span data-ttu-id="f7dca-177">DevTools 在不单步执行的情况下运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-177">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="f7dca-178">DevTools 跳过几行代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-178">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="f7dca-179">这是因为 `inputsAreEmpty()` 计算结果为 false，因此语句的代码块不 `if` 会运行。</span><span class="sxs-lookup"><span data-stu-id="f7dca-179">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="f7dca-180">在 DevTools 的 " **源** " 面板中，选择 " **单步执行下一个函数调用** \" (![ "单步执行下一个函数调用 \ ) " 单步执行 ][ImageIntoIcon] 函数的运行时 `updateLabel()` ，一次一行。</span><span class="sxs-lookup"><span data-stu-id="f7dca-180">On the **Sources** panel of DevTools, choose **Step into next function call** \(![Step into next function call][ImageIntoIcon]\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="f7dca-181">这是单步执行代码的基本概念。</span><span class="sxs-lookup"><span data-stu-id="f7dca-181">That is the basic idea of stepping through code.</span></span>  <span data-ttu-id="f7dca-182">如果你查看中的代码 `get-started.js` ，则会发现该 bug 可能位于函数中的某个位置 `updateLabel()` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-182">If you look at the code in `get-started.js`, you see that the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="f7dca-183">你可以使用另一种类型的断点将代码暂停到更接近 bug 可能位置的位置，而不是单步执行每行代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-183">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <span data-ttu-id="f7dca-184">步骤5：设置代码行断点</span><span class="sxs-lookup"><span data-stu-id="f7dca-184">Step 5: Set a line-of-code breakpoint</span></span>  

<span data-ttu-id="f7dca-185">代码行断点是最常见的断点类型。</span><span class="sxs-lookup"><span data-stu-id="f7dca-185">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="f7dca-186">获取要暂停的特定代码行时，请使用代码行断点：</span><span class="sxs-lookup"><span data-stu-id="f7dca-186">When you get the specific line of code that you want to pause on, use a line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="f7dca-187">查看以下代码中的最后一行代码 `updateLabel()` ：</span><span class="sxs-lookup"><span data-stu-id="f7dca-187">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="f7dca-188">在代码的左侧，你可以看到此特定代码行的行号，即 **33**。</span><span class="sxs-lookup"><span data-stu-id="f7dca-188">To the left of the code you see the line number of this particular line of code, which is **33**.</span></span>  <span data-ttu-id="f7dca-189">单击 " **33**"。</span><span class="sxs-lookup"><span data-stu-id="f7dca-189">Click on **33**.</span></span>  <span data-ttu-id="f7dca-190">DevTools 将红色图标置于 **33**的左侧。</span><span class="sxs-lookup"><span data-stu-id="f7dca-190">DevTools puts a red icon to the left of **33**.</span></span>  <span data-ttu-id="f7dca-191">这意味着此行上有一行代码断点。</span><span class="sxs-lookup"><span data-stu-id="f7dca-191">This means that there is a line-of-code breakpoint on this line.</span></span>  <span data-ttu-id="f7dca-192">DevTools 现在将始终暂停，然后运行此行代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-192">DevTools now always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="f7dca-193">选择 " **恢复脚本执行** " \ (![ 恢复脚本执行 ][ImageResumeIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-193">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  <span data-ttu-id="f7dca-194">脚本将继续运行，直至到达行33。</span><span class="sxs-lookup"><span data-stu-id="f7dca-194">The script continues running until it reaches line 33.</span></span>  <span data-ttu-id="f7dca-195">在30、31和32行上，DevTools 将在 `addend1` `addend2` `sum` 每一行的分号的右侧打印值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-195">On lines 30, 31, and 32, DevTools prints out the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="f7dca-197">DevTools 在行32上的代码行断点处暂停</span><span class="sxs-lookup"><span data-stu-id="f7dca-197">DevTools pauses on the line-of-code breakpoint on line 32</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f7dca-198">步骤6：检查变量值</span><span class="sxs-lookup"><span data-stu-id="f7dca-198">Step 6: Check variable values</span></span>  

<span data-ttu-id="f7dca-199">`addend1`、 `addend2` 和 `sum` 看起来可疑的值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-199">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="f7dca-200">它们包装在引号中，这意味着它们是字符串。</span><span class="sxs-lookup"><span data-stu-id="f7dca-200">They are wrapped in quotes, which means that they are strings.</span></span>  <span data-ttu-id="f7dca-201">这是介绍 bug 原因的一个好假设。</span><span class="sxs-lookup"><span data-stu-id="f7dca-201">This is a good hypothesis for the explaining the cause of the bug.</span></span>  <span data-ttu-id="f7dca-202">现在是收集更多信息的时候了。</span><span class="sxs-lookup"><span data-stu-id="f7dca-202">Now it is time to gather more information.</span></span>  <span data-ttu-id="f7dca-203">DevTools 提供许多用于检查变量值的工具。</span><span class="sxs-lookup"><span data-stu-id="f7dca-203">DevTools provides a lot of tools for examining variable values.</span></span>  

### <span data-ttu-id="f7dca-204">方法1： "范围" 窗格</span><span class="sxs-lookup"><span data-stu-id="f7dca-204">Method 1: The Scope pane</span></span>  

<span data-ttu-id="f7dca-205">当你在一行代码上暂停时， **范围** 窗格将显示当前定义的本地和全局变量以及每个变量的值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-205">When you pause on a line of code, the **Scope** pane shows you what local and global variables are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="f7dca-206">它还显示结束变量（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="f7dca-206">It also shows closure variables, when applicable.</span></span>  <span data-ttu-id="f7dca-207">双击变量值以对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f7dca-207">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="f7dca-208">如果在一行代码上未暂停，则 " **范围** " 窗格为空。</span><span class="sxs-lookup"><span data-stu-id="f7dca-208">When you are not paused on a line of code, the **Scope** pane is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="f7dca-210">" **范围** " 窗格</span><span class="sxs-lookup"><span data-stu-id="f7dca-210">The **Scope** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="f7dca-211">方法2：监视表达式</span><span class="sxs-lookup"><span data-stu-id="f7dca-211">Method 2: Watch Expressions</span></span>  

<span data-ttu-id="f7dca-212">通过 " **监视表达式** " 选项卡，你可以监视一段时间内变量的值。</span><span class="sxs-lookup"><span data-stu-id="f7dca-212">The **Watch Expressions** tab lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="f7dca-213">顾名思义，监视表达式不仅仅局限于变量。</span><span class="sxs-lookup"><span data-stu-id="f7dca-213">As the name implies, Watch Expressions are not just limited to variables.</span></span>  <span data-ttu-id="f7dca-214">你可以在监视表达式中存储任何有效的 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="f7dca-214">You are able to store any valid JavaScript expression in a Watch Expression.</span></span>  <span data-ttu-id="f7dca-215">立即试用：</span><span class="sxs-lookup"><span data-stu-id="f7dca-215">Try it now:</span></span>  

1.  <span data-ttu-id="f7dca-216">单击 " **监视** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f7dca-216">Click the **Watch** tab.</span></span>  
1.  <span data-ttu-id="f7dca-217">选择 " **添加表达式** \ (![ 添加表达式 ][ImageAddIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="f7dca-217">Choose **Add Expression** \(![Add Expression][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="f7dca-218">键入 `typeof sum`。</span><span class="sxs-lookup"><span data-stu-id="f7dca-218">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="f7dca-219">选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-219">Select `Enter`.</span></span>  <span data-ttu-id="f7dca-220">DevTools 显示 `typeof sum: "string"` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-220">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="f7dca-221">冒号右侧的值是监视表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="f7dca-221">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="f7dca-222">在 "监视表达式" 窗格中 (右下角 \ ) 在下图中， `typeof sum` 显示监视表达式。</span><span class="sxs-lookup"><span data-stu-id="f7dca-222">In the Watch Expression pane \(bottom-right\) in in the following figure, the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="f7dca-223">如果 DevTools 窗口较大，"监视表达式" 窗格位于 " **事件侦听器断点** " 窗格上方的右侧。</span><span class="sxs-lookup"><span data-stu-id="f7dca-223">If your DevTools window is large, the Watch Expression pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="f7dca-225">" **监视表达式** " 窗格</span><span class="sxs-lookup"><span data-stu-id="f7dca-225">The **Watch Expression** pane</span></span>  
:::image-end:::  

<span data-ttu-id="f7dca-226">如有怀疑， `sum` 当它应该是一个数字时，将被评估为字符串。</span><span class="sxs-lookup"><span data-stu-id="f7dca-226">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="f7dca-227">您现在已确认这是该 bug 的原因。</span><span class="sxs-lookup"><span data-stu-id="f7dca-227">You have now confirmed that this is the cause of the bug.</span></span>  

### <span data-ttu-id="f7dca-228">方法3：控制台</span><span class="sxs-lookup"><span data-stu-id="f7dca-228">Method 3: The Console</span></span>  

<span data-ttu-id="f7dca-229">除了查看消息外 `console.log()` ，你还可以使用 Console 评估任意 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="f7dca-229">In addition to viewing `console.log()` messages, you may also use the Console to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="f7dca-230">在调试方面，您可以使用该控制台测试 bug 的潜在修复。</span><span class="sxs-lookup"><span data-stu-id="f7dca-230">In terms of debugging, you may use the Console to test out potential fixes for bugs.</span></span>  <span data-ttu-id="f7dca-231">立即试用：</span><span class="sxs-lookup"><span data-stu-id="f7dca-231">Try it now:</span></span>  

1.  <span data-ttu-id="f7dca-232">如果未打开该控制台抽屉，请选择 `Escape` 将其打开。</span><span class="sxs-lookup"><span data-stu-id="f7dca-232">If you do not have the Console drawer open, select `Escape` to open it.</span></span>  <span data-ttu-id="f7dca-233">它将在 DevTools 窗口底部打开。</span><span class="sxs-lookup"><span data-stu-id="f7dca-233">It opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="f7dca-234">在控制台中，键入 `parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-234">In the Console, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="f7dca-235">此语句之所以有效，是因为你已暂停在范围内和的代码行上 `addend1` `addend2` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-235">This statement works because you are paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="f7dca-236">选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-236">Select `Enter`.</span></span>  <span data-ttu-id="f7dca-237">DevTools 将计算该语句并将 `6` 其打印出来，这是你希望演示产生的结果。</span><span class="sxs-lookup"><span data-stu-id="f7dca-237">DevTools evaluates the statement and prints out `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="f7dca-239">评估后的 **控制台** 抽屉</span><span class="sxs-lookup"><span data-stu-id="f7dca-239">The **Console** drawer, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <span data-ttu-id="f7dca-240">步骤7：应用修补程序</span><span class="sxs-lookup"><span data-stu-id="f7dca-240">Step 7: Apply a fix</span></span>  

<span data-ttu-id="f7dca-241">如果发现 bug 的修补程序，请通过编辑代码并重新运行演示来尝试修复。</span><span class="sxs-lookup"><span data-stu-id="f7dca-241">If you find a fix for the bug, try out your fix by editing the code and re-running the demo.</span></span>  <span data-ttu-id="f7dca-242">无需离开 DevTools 即可应用此修补程序。</span><span class="sxs-lookup"><span data-stu-id="f7dca-242">You do not need to leave DevTools to apply the fix.</span></span>  <span data-ttu-id="f7dca-243">你可以直接在 DevTools UI 内编辑 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-243">You are able to edit JavaScript code directly within the DevTools UI.</span></span>  <span data-ttu-id="f7dca-244">立即试用：</span><span class="sxs-lookup"><span data-stu-id="f7dca-244">Try it now:</span></span>  

1.  <span data-ttu-id="f7dca-245">选择 " **恢复脚本执行** " \ (![ 恢复脚本执行 ][ImageResumeIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-245">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  
1.  <span data-ttu-id="f7dca-246">在 **代码编辑器**中，将行32替换 `var sum = addend1 + addend2` 为 `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="f7dca-246">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="f7dca-247">选择 `Control` + `S` \ (Windows、Linux \ ) 或 `Command` + `S` \ (macOS \ ) 保存您的更改。</span><span class="sxs-lookup"><span data-stu-id="f7dca-247">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="f7dca-248">选择 " **停用断点** \ (![ 停用断点 ][ImageDeactivateIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="f7dca-248">Choose **Deactivate breakpoints** \(![Deactivate breakpoints][ImageDeactivateIcon]\).</span></span>  <span data-ttu-id="f7dca-249">它将更改为蓝色，以指示它处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="f7dca-249">It changes blue to indicate that it is active.</span></span>  <span data-ttu-id="f7dca-250">设置此设置时，DevTools 忽略你设置的任何断点。</span><span class="sxs-lookup"><span data-stu-id="f7dca-250">While this is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="f7dca-251">试用具有不同值的演示。</span><span class="sxs-lookup"><span data-stu-id="f7dca-251">Try out the demo with different values.</span></span>  <span data-ttu-id="f7dca-252">演示现在能够正确计算。</span><span class="sxs-lookup"><span data-stu-id="f7dca-252">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="f7dca-253">此工作流仅将修补程序应用于浏览器中运行的代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-253">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="f7dca-254">它不会修复访问您的页面的所有用户的代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-254">It does not fix the code for all users that visit your page.</span></span>  <span data-ttu-id="f7dca-255">若要执行此操作，您需要修复服务器上的代码。</span><span class="sxs-lookup"><span data-stu-id="f7dca-255">To do that, you need to fix the code that is on your servers.</span></span>  

## <span data-ttu-id="f7dca-256">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f7dca-256">Next steps</span></span>  

<span data-ttu-id="f7dca-257">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="f7dca-257">Congratulations!</span></span>  <span data-ttu-id="f7dca-258">你现在知道如何在调试 JavaScript 时充分利用 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="f7dca-258">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="f7dca-259">您在本教程中学到的工具和方法可能会为您节省无数小时。</span><span class="sxs-lookup"><span data-stu-id="f7dca-259">The tools and methods you learned in this tutorial may save you countless hours.</span></span>  

<span data-ttu-id="f7dca-260">本教程仅介绍两种设置断点的方法。</span><span class="sxs-lookup"><span data-stu-id="f7dca-260">This tutorial only showed you two ways to set breakpoints.</span></span>  <span data-ttu-id="f7dca-261">DevTools 提供了许多其他方法，包括以下设置。</span><span class="sxs-lookup"><span data-stu-id="f7dca-261">DevTools offers many other ways including the following settings.</span></span>  

*   <span data-ttu-id="f7dca-262">仅当你提供的条件为 true 时才触发的条件断点。</span><span class="sxs-lookup"><span data-stu-id="f7dca-262">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="f7dca-263">已捕获或未捕获的异常上的断点。</span><span class="sxs-lookup"><span data-stu-id="f7dca-263">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="f7dca-264">当请求的 URL 与你提供的子字符串匹配时触发的 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="f7dca-264">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="f7dca-265">有关何时以及如何使用每种类型的详细信息，请转到 [使用断点暂停代码][DevtoolsJavscriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="f7dca-265">For more information about when and how to use each type, go to [Pause Your Code With Breakpoints][DevtoolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="f7dca-266">本教程中有一些代码步进控件未介绍。</span><span class="sxs-lookup"><span data-stu-id="f7dca-266">There are a couple of code stepping controls that were not explained in this tutorial.</span></span>  <span data-ttu-id="f7dca-267">有关详细信息，请转到 [代码行][DevtoolsJavascriptReferenceStepThroughCode]。</span><span class="sxs-lookup"><span data-stu-id="f7dca-267">For more information, go to [Step over line of code][DevtoolsJavascriptReferenceStepThroughCode].</span></span>  

## <span data-ttu-id="f7dca-268">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="f7dca-268">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: ../media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageIntoIcon]: ../media/step-into-icon.msft.png  
[ImageOverIcon]: ../media/step-over-icon.msft.png  
[ImageResumeIcon]: ../media/resume-script-run-icon.msft.png  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools 中暂停带有断点的代码 |Microsoft 文档"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "逐句通过代码-JavaScript 调试参考 |Microsoft 文档"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示 |故障"  

> [!NOTE]
> <span data-ttu-id="f7dca-272">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f7dca-272">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f7dca-273">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f7dca-273">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f7dca-275">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f7dca-275">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
