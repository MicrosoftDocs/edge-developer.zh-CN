---
title: 在 Microsoft Edge DevTools 中开始使用调试 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 06df1fd4d6457a3f02be85b95959bdc353865495
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581822"
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







# <span data-ttu-id="1210f-103">在 Microsoft Edge DevTools 中开始使用调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="1210f-103">Get Started with Debugging JavaScript in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="1210f-104">本教程将指导你在 DevTools 中调试 JavaScript 问题的基本工作流。</span><span class="sxs-lookup"><span data-stu-id="1210f-104">This tutorial teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <span data-ttu-id="1210f-105">步骤1：重现 bug</span><span class="sxs-lookup"><span data-stu-id="1210f-105">Step 1: Reproduce the bug</span></span>   

<span data-ttu-id="1210f-106">在调试的第一步中始终是查找始终重现 bug 的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="1210f-106">Finding a series of actions that consistently reproduces a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="1210f-107">单击 "**打开演示**"。</span><span class="sxs-lookup"><span data-stu-id="1210f-107">Click **Open Demo**.</span></span>  <span data-ttu-id="1210f-108">保留 `Control` \ （Windows \）或 `Command` \ （macOS \），并在新选项卡中打开演示。</span><span class="sxs-lookup"><span data-stu-id="1210f-108">Hold `Control` \(Windows\) or `Command` \(macOS\) and open the demo in a new tab.</span></span>  

    <span data-ttu-id="1210f-109">[开放演示][OpenDebugJSDemo]</span><span class="sxs-lookup"><span data-stu-id="1210f-109">[Open Demo][OpenDebugJSDemo]</span></span>  

1.  <span data-ttu-id="1210f-110">`5`在 "**数字 1** " 文本框中输入。</span><span class="sxs-lookup"><span data-stu-id="1210f-110">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="1210f-111">`1`在 "**数字 2** " 文本框中输入。</span><span class="sxs-lookup"><span data-stu-id="1210f-111">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="1210f-112">单击 "**添加号码 1" 和 "数字 2**"。</span><span class="sxs-lookup"><span data-stu-id="1210f-112">Click **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="1210f-113">按钮下方的标签显示 "" `5 + 1 = 51` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-113">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="1210f-114">结果应为 `6` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-114">The result should be `6`.</span></span>  <span data-ttu-id="1210f-115">这是你要修复的 bug。</span><span class="sxs-lookup"><span data-stu-id="1210f-115">This is the bug you are going to fix.</span></span>  
    
    > ##### <span data-ttu-id="1210f-116">图 1</span><span class="sxs-lookup"><span data-stu-id="1210f-116">Figure 1</span></span>  
    > <span data-ttu-id="1210f-117">Is 的结果 `5 + 1` 是 `51` ，但应该</span><span class="sxs-lookup"><span data-stu-id="1210f-117">The result of `5 + 1` is `51`, but should be</span></span> `6`  
    > ![5 + 1 的结果是51，但应该是6][ImageJSBugs]  

## <span data-ttu-id="1210f-119">步骤2：熟悉 "源" 面板 UI</span><span class="sxs-lookup"><span data-stu-id="1210f-119">Step 2: Get familiar with the Sources panel UI</span></span>   

<span data-ttu-id="1210f-120">DevTools 为不同的任务提供了许多不同的工具，例如更改 CSS、分析页面加载性能和监视网络请求。</span><span class="sxs-lookup"><span data-stu-id="1210f-120">DevTools provides a lot of different tools for different tasks, such as changing CSS, profiling page load performance, and monitoring network requests.</span></span>  <span data-ttu-id="1210f-121">"**源**" 面板是你在其中调试 JavaScript 的位置。</span><span class="sxs-lookup"><span data-stu-id="1210f-121">The **Sources** panel is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="1210f-122">通过按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="1210f-122">Open DevTools by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) .</span></span>  <span data-ttu-id="1210f-123">此快捷方式将打开**控制台**面板。</span><span class="sxs-lookup"><span data-stu-id="1210f-123">This shortcut opens the **Console** panel.</span></span>  
    
    > ##### <span data-ttu-id="1210f-124">图 2</span><span class="sxs-lookup"><span data-stu-id="1210f-124">Figure 2</span></span>  
    > <span data-ttu-id="1210f-125">**控制台**面板</span><span class="sxs-lookup"><span data-stu-id="1210f-125">The **Console** panel</span></span>  
    > ![控制台面板][ImageJSConsole]  

1.  <span data-ttu-id="1210f-127">单击 "**源**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1210f-127">Click the **Sources** tab.</span></span>  
    
    > ##### <span data-ttu-id="1210f-128">图 3</span><span class="sxs-lookup"><span data-stu-id="1210f-128">Figure 3</span></span>  
    > <span data-ttu-id="1210f-129">"**源**" 面板</span><span class="sxs-lookup"><span data-stu-id="1210f-129">The **Sources** panel</span></span>  
    > !["源" 面板][ImageJSSources]  

<span data-ttu-id="1210f-131">"**源**" 面板 UI 包含3个部分：</span><span class="sxs-lookup"><span data-stu-id="1210f-131">The **Sources** panel UI has 3 parts:</span></span>  

> ##### <span data-ttu-id="1210f-132">图 4</span><span class="sxs-lookup"><span data-stu-id="1210f-132">Figure 4</span></span>  
> <span data-ttu-id="1210f-133">"**源**" 面板 UI 的3个部分</span><span class="sxs-lookup"><span data-stu-id="1210f-133">The 3 parts of the **Sources** panel UI</span></span>  
> !["源" 面板 UI 的3个部分][ImageJSSourcesAnnotated]  

1.  <span data-ttu-id="1210f-135">"**文件导航器**" 窗格 \ （[图 4](#figure-4)中的第1节 \）。</span><span class="sxs-lookup"><span data-stu-id="1210f-135">The **File Navigator** pane \(Section 1 in [Figure 4](#figure-4)\).</span></span>  <span data-ttu-id="1210f-136">页面请求的每个文件都在此处列出。</span><span class="sxs-lookup"><span data-stu-id="1210f-136">Every file that the page requests is listed here.</span></span>  
1.  <span data-ttu-id="1210f-137">"**代码编辑器**" 窗格 \ （[图 4](#figure-4)中的第2节 \）。</span><span class="sxs-lookup"><span data-stu-id="1210f-137">The **Code Editor** pane \(Section 2 in [Figure 4](#figure-4)\).</span></span>  <span data-ttu-id="1210f-138">在 "**文件导航器**" 窗格中选择文件后，该文件的内容将显示在此处。</span><span class="sxs-lookup"><span data-stu-id="1210f-138">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="1210f-139">**JavaScript 调试**窗格 \ （[图 4](#figure-4)中的第3节 \）。</span><span class="sxs-lookup"><span data-stu-id="1210f-139">The **JavaScript Debugging** pane \(Section 3 in [Figure 4](#figure-4)\).</span></span>  <span data-ttu-id="1210f-140">用于检查页面的 JavaScript 的各种工具。</span><span class="sxs-lookup"><span data-stu-id="1210f-140">Various tools for inspecting the JavaScript for the page.</span></span>  <span data-ttu-id="1210f-141">如果 DevTools 窗口宽，此窗格将显示在 "**代码编辑器**" 窗格的右侧。</span><span class="sxs-lookup"><span data-stu-id="1210f-141">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  

## <span data-ttu-id="1210f-142">步骤3：使用断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="1210f-142">Step 3: Pause the code with a breakpoint</span></span>   

<span data-ttu-id="1210f-143">调试此类问题的常见方法是将许多语句插入到 `console.log()` 代码中，以便在脚本运行时检查值。</span><span class="sxs-lookup"><span data-stu-id="1210f-143">A common method for debugging a problem like this is to insert a lot of `console.log()` statements into the code, in order to inspect values as the script runs.</span></span>  <span data-ttu-id="1210f-144">例如：</span><span class="sxs-lookup"><span data-stu-id="1210f-144">For example:</span></span>  

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

<span data-ttu-id="1210f-145">此 `console.log()` 方法可能会使作业完成，但**断点**能够更快地完成工作。</span><span class="sxs-lookup"><span data-stu-id="1210f-145">The `console.log()` method may get the job done, but **breakpoints** are able to get it done faster.</span></span>  <span data-ttu-id="1210f-146">断点使你可以在运行时中间暂停代码，并在该时刻检查所有值。</span><span class="sxs-lookup"><span data-stu-id="1210f-146">A breakpoint lets you pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="1210f-147">与方法相比，断点有几个优点 `console.log()` ：</span><span class="sxs-lookup"><span data-stu-id="1210f-147">Breakpoints have a few advantages over the `console.log()` method:</span></span>  

*   <span data-ttu-id="1210f-148">通过 `console.log()` ，你需要手动打开源代码，查找相关代码，插入 `console.log()` 语句，然后重新加载页面，以便在控制台中查看消息。</span><span class="sxs-lookup"><span data-stu-id="1210f-148">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then reload the page in order to see the messages in the Console.</span></span>  <span data-ttu-id="1210f-149">利用断点，您可以暂停在相关代码上，而无需了解代码的结构。</span><span class="sxs-lookup"><span data-stu-id="1210f-149">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="1210f-150">在你的 `console.log()` 语句中，你需要显式指定要检查的每个值。</span><span class="sxs-lookup"><span data-stu-id="1210f-150">In your `console.log()` statements you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="1210f-151">有了断点，DevTools 将显示当时的所有变量的值。</span><span class="sxs-lookup"><span data-stu-id="1210f-151">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="1210f-152">有时，你甚至不知道的代码会影响你的代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-152">Sometimes there are variables affecting your code that you are not even aware of.</span></span>  

<span data-ttu-id="1210f-153">简言之，断点可帮助你查找和修复 bug，比方法更快 `console.log()` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-153">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="1210f-154">如果返回一个步骤并考虑应用的工作方式，则可以让你有兴趣地猜测 `5 + 1 = 51` 在 `click` 与 " **Add Number 1" 和 "number 2** " 按钮相关联的事件侦听器中获取了不正确的 sum （）。</span><span class="sxs-lookup"><span data-stu-id="1210f-154">If you take a step back and think about how the app works, you are able to make an educated guess that the incorrect sum (`5 + 1 = 51`) gets computed in the `click` event listener that is associated to the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="1210f-155">因此，你可能希望在侦听器运行的时间周围暂停代码 `click` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-155">Therefore, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="1210f-156">**事件侦听器断点**使你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1210f-156">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="1210f-157">在 " **JavaScript 调试**" 窗格中，单击 "**事件侦听器断点**" 以展开该部分。</span><span class="sxs-lookup"><span data-stu-id="1210f-157">In the **JavaScript Debugging** pane, click **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="1210f-158">DevTools 显示可展开的事件类别（如**动画**和**剪贴板**）的列表。</span><span class="sxs-lookup"><span data-stu-id="1210f-158">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="1210f-159">在**鼠标**事件类别旁边，单击 "**展开** ![ 展开" ][ImageExpandIcon] 图标。</span><span class="sxs-lookup"><span data-stu-id="1210f-159">Next to the **Mouse** event category, click **Expand** ![Expand icon][ImageExpandIcon].</span></span>  <span data-ttu-id="1210f-160">DevTools 显示鼠标事件（如**单击**和**mousedown**）的列表。</span><span class="sxs-lookup"><span data-stu-id="1210f-160">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="1210f-161">每个事件旁边都有一个复选框。</span><span class="sxs-lookup"><span data-stu-id="1210f-161">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="1210f-162">选中 "**单击**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1210f-162">Check the **click** checkbox.</span></span>  <span data-ttu-id="1210f-163">DevTools 现已设置为在*任何* `click` 事件侦听器运行时自动暂停。</span><span class="sxs-lookup"><span data-stu-id="1210f-163">DevTools is now set up to automatically pause when *any* `click` event listener runs.</span></span>  
    
    > ##### <span data-ttu-id="1210f-164">图 5</span><span class="sxs-lookup"><span data-stu-id="1210f-164">Figure 5</span></span>  
    > <span data-ttu-id="1210f-165">已启用 "**单击**" 复选框</span><span class="sxs-lookup"><span data-stu-id="1210f-165">The **click** checkbox is enabled</span></span>  
    > ![已启用 "单击" 复选框][ImageJSClickCheckbox]  
    
1.  <span data-ttu-id="1210f-167">返回到演示，再次单击 "**添加号码 1" 和 "数字 2** "。</span><span class="sxs-lookup"><span data-stu-id="1210f-167">Back on the demo, click **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="1210f-168">DevTools 暂停演示并突出显示 "**源**" 面板中的一行代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-168">DevTools pauses the demo and highlights a line of code in the **Sources** panel.</span></span>  <span data-ttu-id="1210f-169">DevTools 应在的行16中暂停 `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-169">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="1210f-170">如果在其他代码行暂停，请按 "**恢复脚本执行**" ![ 恢复脚本执行， ][ImageResumeIcon] 直到暂停在正确的行上。</span><span class="sxs-lookup"><span data-stu-id="1210f-170">If you pause on a different line of code, press **Resume Script Execution** ![Resume Script Execution][ImageResumeIcon] until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1210f-171">如果你在其他行暂停，则你有一个浏览器扩展，它 `click` 在你访问的每个页面上注册一个事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="1210f-171">If you paused on a different line, you have a browser extension that registers a `click` event listener on every page that you visit.</span></span>  <span data-ttu-id="1210f-172">已暂停在扩展的 `click` 侦听器中。</span><span class="sxs-lookup"><span data-stu-id="1210f-172">You were paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="1210f-173">如果你使用 InPrivate 模式**浏览 private**（这将禁用所有扩展），你可能会看到每次都在所需的代码行上暂停。</span><span class="sxs-lookup"><span data-stu-id="1210f-173">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="1210f-174">**事件侦听器断点**只是 DevTools 中可用的多种类型的断点之一。</span><span class="sxs-lookup"><span data-stu-id="1210f-174">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="1210f-175">它值得 memorizing 所有不同类型，因为每种类型最终有助于尽可能快地调试不同的方案。</span><span class="sxs-lookup"><span data-stu-id="1210f-175">It is worth memorizing all the different types, because each type ultimately helps you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <span data-ttu-id="1210f-176">步骤4：逐句通过代码</span><span class="sxs-lookup"><span data-stu-id="1210f-176">Step 4: Step through the code</span></span>   

<span data-ttu-id="1210f-177">Bug 的一个常见原因是，脚本的运行顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="1210f-177">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="1210f-178">单步执行你的代码，使你能够遍历代码的运行时，一次一行，然后以与预期不同的顺序确定其运行的确切位置。</span><span class="sxs-lookup"><span data-stu-id="1210f-178">Stepping through your code enables you to walk through the runtime of your code, one line at a time, and figure out exactly where it is running in a different order than you expected.</span></span>  <span data-ttu-id="1210f-179">立即试用：</span><span class="sxs-lookup"><span data-stu-id="1210f-179">Try it now:</span></span>  

1.  <span data-ttu-id="1210f-180">单击 "按后续**函数调用步骤**" ![ ][ImageOverIcon] 。</span><span class="sxs-lookup"><span data-stu-id="1210f-180">Click **Step over next function call** ![Step over next function call][ImageOverIcon].</span></span>  <span data-ttu-id="1210f-181">DevTools 在不单步执行的情况下运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-181">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  

    > [!NOTE]
    > <span data-ttu-id="1210f-182">DevTools 跳过几行代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-182">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="1210f-183">这是因为 `inputsAreEmpty()` 计算结果为 false，因此语句的代码块不 `if` 会运行。</span><span class="sxs-lookup"><span data-stu-id="1210f-183">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  

1.  <span data-ttu-id="1210f-184">在 DevTools 的 "**源**" 面板中，单击 "**单步执行下一函数调用**下一步函数调用" ![ 下一步函数调用 ][ImageIntoIcon] 以逐句通过函数的运行时 `updateLabel()` ，一次一行。</span><span class="sxs-lookup"><span data-stu-id="1210f-184">On the **Sources** panel of DevTools, click **Step into next function call** ![Step into next function call][ImageIntoIcon] to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  

<span data-ttu-id="1210f-185">这是单步执行代码的基本概念。</span><span class="sxs-lookup"><span data-stu-id="1210f-185">That is the basic idea of stepping through code.</span></span>  <span data-ttu-id="1210f-186">如果你查看中的代码 `get-started.js` ，则会发现该 bug 可能位于函数中的某个位置 `updateLabel()` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-186">If you look at the code in `get-started.js`, you see that the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="1210f-187">你可以使用另一种类型的断点将代码暂停到更接近 bug 可能位置的位置，而不是单步执行每行代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-187">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <span data-ttu-id="1210f-188">步骤5：设置代码行断点</span><span class="sxs-lookup"><span data-stu-id="1210f-188">Step 5: Set a line-of-code breakpoint</span></span>   

<span data-ttu-id="1210f-189">代码行断点是最常见的断点类型。</span><span class="sxs-lookup"><span data-stu-id="1210f-189">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="1210f-190">获取要暂停的特定代码行时，请使用代码行断点：</span><span class="sxs-lookup"><span data-stu-id="1210f-190">When you get the specific line of code that you want to pause on, use a line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="1210f-191">查看以下代码中的最后一行代码 `updateLabel()` ：</span><span class="sxs-lookup"><span data-stu-id="1210f-191">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="1210f-192">在代码的左侧，你可以看到此特定代码行的行号，即**33**。</span><span class="sxs-lookup"><span data-stu-id="1210f-192">To the left of the code you see the line number of this particular line of code, which is **33**.</span></span>  <span data-ttu-id="1210f-193">单击 " **33**"。</span><span class="sxs-lookup"><span data-stu-id="1210f-193">Click on **33**.</span></span>  <span data-ttu-id="1210f-194">DevTools 将红色图标置于**33**的左侧。</span><span class="sxs-lookup"><span data-stu-id="1210f-194">DevTools puts a red icon to the left of **33**.</span></span>  <span data-ttu-id="1210f-195">这意味着此行上有一行代码断点。</span><span class="sxs-lookup"><span data-stu-id="1210f-195">This means that there is a line-of-code breakpoint on this line.</span></span>  <span data-ttu-id="1210f-196">DevTools 现在将始终暂停，然后运行此行代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-196">DevTools now always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="1210f-197">单击 "**恢复脚本执行**" ![ 恢复脚本执行 ][ImageResumeIcon] 。</span><span class="sxs-lookup"><span data-stu-id="1210f-197">Click **Resume script execution** ![Resume script execution][ImageResumeIcon].</span></span>  <span data-ttu-id="1210f-198">脚本将继续运行，直至到达行33。</span><span class="sxs-lookup"><span data-stu-id="1210f-198">The script continues running until it reaches line 33.</span></span>  <span data-ttu-id="1210f-199">在30、31和32行上，DevTools 将在 `addend1` `addend2` `sum` 每一行的分号的右侧打印值。</span><span class="sxs-lookup"><span data-stu-id="1210f-199">On lines 30, 31, and 32, DevTools prints out the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    > ##### <span data-ttu-id="1210f-200">图 6</span><span class="sxs-lookup"><span data-stu-id="1210f-200">Figure 6</span></span>  
    > <span data-ttu-id="1210f-201">DevTools 在行32上的代码行断点处暂停</span><span class="sxs-lookup"><span data-stu-id="1210f-201">DevTools pauses on the line-of-code breakpoint on line 32</span></span>  
    > ![DevTools 在行32上的代码行断点处暂停][ImageJSLineOfCodeBreakpoint]  

## <span data-ttu-id="1210f-203">步骤6：检查变量值</span><span class="sxs-lookup"><span data-stu-id="1210f-203">Step 6: Check variable values</span></span>   

<span data-ttu-id="1210f-204">`addend1`、 `addend2` 和 `sum` 看起来可疑的值。</span><span class="sxs-lookup"><span data-stu-id="1210f-204">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="1210f-205">它们包装在引号中，这意味着它们是字符串。</span><span class="sxs-lookup"><span data-stu-id="1210f-205">They are wrapped in quotes, which means that they are strings.</span></span>  <span data-ttu-id="1210f-206">这是介绍 bug 原因的一个好假设。</span><span class="sxs-lookup"><span data-stu-id="1210f-206">This is a good hypothesis for the explaining the cause of the bug.</span></span>  <span data-ttu-id="1210f-207">现在是收集更多信息的时候了。</span><span class="sxs-lookup"><span data-stu-id="1210f-207">Now it is time to gather more information.</span></span>  <span data-ttu-id="1210f-208">DevTools 提供许多用于检查变量值的工具。</span><span class="sxs-lookup"><span data-stu-id="1210f-208">DevTools provides a lot of tools for examining variable values.</span></span>  

### <span data-ttu-id="1210f-209">方法1： "范围" 窗格</span><span class="sxs-lookup"><span data-stu-id="1210f-209">Method 1: The Scope pane</span></span>   

<span data-ttu-id="1210f-210">当你在一行代码上暂停时，**范围**窗格将显示当前定义的本地和全局变量以及每个变量的值。</span><span class="sxs-lookup"><span data-stu-id="1210f-210">When you pause on a line of code, the **Scope** pane shows you what local and global variables are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="1210f-211">它还显示结束变量（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="1210f-211">It also shows closure variables, when applicable.</span></span>  <span data-ttu-id="1210f-212">双击变量值以对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="1210f-212">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="1210f-213">如果在一行代码上未暂停，则 "**范围**" 窗格为空。</span><span class="sxs-lookup"><span data-stu-id="1210f-213">When you are not paused on a line of code, the **Scope** pane is empty.</span></span>  

> ##### <span data-ttu-id="1210f-214">图 7</span><span class="sxs-lookup"><span data-stu-id="1210f-214">Figure 7</span></span>  
> <span data-ttu-id="1210f-215">"**范围**" 窗格</span><span class="sxs-lookup"><span data-stu-id="1210f-215">The **Scope** pane</span></span>  
> !["范围" 窗格][ImageJSScope]  

### <span data-ttu-id="1210f-217">方法2：监视表达式</span><span class="sxs-lookup"><span data-stu-id="1210f-217">Method 2: Watch Expressions</span></span>   

<span data-ttu-id="1210f-218">通过 "**监视表达式**" 选项卡，你可以监视一段时间内变量的值。</span><span class="sxs-lookup"><span data-stu-id="1210f-218">The **Watch Expressions** tab lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="1210f-219">顾名思义，监视表达式不仅仅局限于变量。</span><span class="sxs-lookup"><span data-stu-id="1210f-219">As the name implies, Watch Expressions are not just limited to variables.</span></span>  <span data-ttu-id="1210f-220">你可以在监视表达式中存储任何有效的 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="1210f-220">You are able to store any valid JavaScript expression in a Watch Expression.</span></span>  <span data-ttu-id="1210f-221">立即试用：</span><span class="sxs-lookup"><span data-stu-id="1210f-221">Try it now:</span></span>  

1.  <span data-ttu-id="1210f-222">单击 "**监视**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1210f-222">Click the **Watch** tab.</span></span>  
1.  <span data-ttu-id="1210f-223">单击 "**添加表达式**" ![ 添加表达式 ][ImageAddIcon] 。</span><span class="sxs-lookup"><span data-stu-id="1210f-223">Click **Add Expression** ![Add Expression][ImageAddIcon].</span></span>  
1.  <span data-ttu-id="1210f-224">键入 `typeof sum`。</span><span class="sxs-lookup"><span data-stu-id="1210f-224">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="1210f-225">按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-225">Press `Enter`.</span></span>  <span data-ttu-id="1210f-226">DevTools 显示 `typeof sum: "string"` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-226">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="1210f-227">冒号右侧的值是监视表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="1210f-227">The value to the right of the colon is the result of your Watch Expression.</span></span>  

> [!NOTE]
> <span data-ttu-id="1210f-228">在[图 8](#figure-8)中的 "监视表达式" 窗格中 \ （右下角 \）， `typeof sum` 显示监视表达式。</span><span class="sxs-lookup"><span data-stu-id="1210f-228">In the Watch Expression pane \(bottom-right\) in [Figure 8](#figure-8), the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="1210f-229">如果 DevTools 窗口较大，"监视表达式" 窗格位于 "**事件侦听器断点**" 窗格上方的右侧。</span><span class="sxs-lookup"><span data-stu-id="1210f-229">If your DevTools window is large, the Watch Expression pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

> ##### <span data-ttu-id="1210f-230">图 8</span><span class="sxs-lookup"><span data-stu-id="1210f-230">Figure 8</span></span>  
> <span data-ttu-id="1210f-231">"监视表达式" 窗格</span><span class="sxs-lookup"><span data-stu-id="1210f-231">The Watch Expression pane</span></span>  
> !["监视表达式" 窗格][ImageJSWatchExpression]  

<span data-ttu-id="1210f-233">如有怀疑， `sum` 当它应该是一个数字时，将被评估为字符串。</span><span class="sxs-lookup"><span data-stu-id="1210f-233">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="1210f-234">您现在已确认这是该 bug 的原因。</span><span class="sxs-lookup"><span data-stu-id="1210f-234">You have now confirmed that this is the cause of the bug.</span></span>  

### <span data-ttu-id="1210f-235">方法3：控制台</span><span class="sxs-lookup"><span data-stu-id="1210f-235">Method 3: The Console</span></span>   

<span data-ttu-id="1210f-236">除了查看消息外 `console.log()` ，你还可以使用 Console 评估任意 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="1210f-236">In addition to viewing `console.log()` messages, you may also use the Console to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="1210f-237">在调试方面，您可以使用该控制台测试 bug 的潜在修复。</span><span class="sxs-lookup"><span data-stu-id="1210f-237">In terms of debugging, you may use the Console to test out potential fixes for bugs.</span></span>  <span data-ttu-id="1210f-238">立即试用：</span><span class="sxs-lookup"><span data-stu-id="1210f-238">Try it now:</span></span>  

1.  <span data-ttu-id="1210f-239">如果您没有打开的控制台，请按 `Escape` 将其打开。</span><span class="sxs-lookup"><span data-stu-id="1210f-239">If you do not have the Console drawer open, press `Escape` to open it.</span></span>  <span data-ttu-id="1210f-240">它将在 DevTools 窗口底部打开。</span><span class="sxs-lookup"><span data-stu-id="1210f-240">It opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="1210f-241">在控制台中，键入 `parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-241">In the Console, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="1210f-242">此语句之所以有效，是因为你已暂停在范围内和的代码行上 `addend1` `addend2` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-242">This statement works because you are paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="1210f-243">按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-243">Press `Enter`.</span></span>  <span data-ttu-id="1210f-244">DevTools 将计算该语句并将 `6` 其打印出来，这是你希望演示产生的结果。</span><span class="sxs-lookup"><span data-stu-id="1210f-244">DevTools evaluates the statement and prints out `6`, which is the result you expect the demo to produce.</span></span>  

> ##### <span data-ttu-id="1210f-245">图 9</span><span class="sxs-lookup"><span data-stu-id="1210f-245">Figure 9</span></span>  
> <span data-ttu-id="1210f-246">评估后的控制台抽屉</span><span class="sxs-lookup"><span data-stu-id="1210f-246">The Console drawer, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
> ![在评估 parseInt （addend1） + parseInt （addend2）之后的控制台抽屉][ImageJSConsoleEvaluated]  

## <span data-ttu-id="1210f-248">步骤7：应用修补程序</span><span class="sxs-lookup"><span data-stu-id="1210f-248">Step 7: Apply a fix</span></span>   

<span data-ttu-id="1210f-249">如果发现 bug 的修补程序，请通过编辑代码并重新运行演示来尝试修复。</span><span class="sxs-lookup"><span data-stu-id="1210f-249">If you find a fix for the bug, try out your fix by editing the code and re-running the demo.</span></span>  <span data-ttu-id="1210f-250">无需离开 DevTools 即可应用此修补程序。</span><span class="sxs-lookup"><span data-stu-id="1210f-250">You do not need to leave DevTools to apply the fix.</span></span>  <span data-ttu-id="1210f-251">你可以直接在 DevTools UI 内编辑 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-251">You are able to edit JavaScript code directly within the DevTools UI.</span></span>  <span data-ttu-id="1210f-252">立即试用：</span><span class="sxs-lookup"><span data-stu-id="1210f-252">Try it now:</span></span>  

1.  <span data-ttu-id="1210f-253">单击 "**恢复脚本执行**" ![ 恢复脚本执行 ][ImageResumeIcon] 。</span><span class="sxs-lookup"><span data-stu-id="1210f-253">Click **Resume script execution** ![Resume script execution][ImageResumeIcon].</span></span>  
1.  <span data-ttu-id="1210f-254">在**代码编辑器**中，将行32替换 `var sum = addend1 + addend2` 为 `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="1210f-254">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="1210f-255">按 `Control` + `S` \ （Windows \）或 `Command` + `S` \ （macOS \）保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1210f-255">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="1210f-256">单击 "**停用断点**" ![ 停用断点 ][ImageDeactivateIcon] 。</span><span class="sxs-lookup"><span data-stu-id="1210f-256">Click **Deactivate breakpoints** ![Deactivate breakpoints][ImageDeactivateIcon].</span></span>  <span data-ttu-id="1210f-257">它将更改为蓝色，以指示它处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="1210f-257">It changes blue to indicate that it is active.</span></span>  <span data-ttu-id="1210f-258">设置此设置时，DevTools 忽略你设置的任何断点。</span><span class="sxs-lookup"><span data-stu-id="1210f-258">While this is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="1210f-259">试用具有不同值的演示。</span><span class="sxs-lookup"><span data-stu-id="1210f-259">Try out the demo with different values.</span></span>  <span data-ttu-id="1210f-260">演示现在能够正确计算。</span><span class="sxs-lookup"><span data-stu-id="1210f-260">The demo now calculates correctly.</span></span>  

> [!CAUTION]
> <span data-ttu-id="1210f-261">此工作流仅将修补程序应用于浏览器中运行的代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-261">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="1210f-262">它不会修复访问您的页面的所有用户的代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-262">It does not fix the code for all users that visit your page.</span></span>  <span data-ttu-id="1210f-263">若要执行此操作，您需要修复服务器上的代码。</span><span class="sxs-lookup"><span data-stu-id="1210f-263">To do that, you need to fix the code that is on your servers.</span></span>  

## <span data-ttu-id="1210f-264">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1210f-264">Next steps</span></span>   

<span data-ttu-id="1210f-265">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="1210f-265">Congratulations!</span></span>  <span data-ttu-id="1210f-266">你现在知道如何在调试 JavaScript 时充分利用 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="1210f-266">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="1210f-267">您在本教程中学到的工具和方法可能会为您节省无数小时。</span><span class="sxs-lookup"><span data-stu-id="1210f-267">The tools and methods you learned in this tutorial may save you countless hours.</span></span>  

<span data-ttu-id="1210f-268">本教程仅介绍两种设置断点的方法。</span><span class="sxs-lookup"><span data-stu-id="1210f-268">This tutorial only showed you two ways to set breakpoints.</span></span>  <span data-ttu-id="1210f-269">DevTools 提供了许多其他方式，包括：</span><span class="sxs-lookup"><span data-stu-id="1210f-269">DevTools offers many other ways, including:</span></span>  

*   <span data-ttu-id="1210f-270">仅当你提供的条件为 true 时才触发的条件断点。</span><span class="sxs-lookup"><span data-stu-id="1210f-270">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="1210f-271">已捕获或未捕获的异常上的断点。</span><span class="sxs-lookup"><span data-stu-id="1210f-271">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="1210f-272">当请求的 URL 与你提供的子字符串匹配时触发的 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="1210f-272">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  

<!-- See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

<!--There are a couple of code stepping controls that were not explained in this tutorial.  See [Step over line of code][JSReferenceStepping] to learn more.  -->  

 



<!-- image links -->  

[ImageAddIcon]: /microsoft-edge/devtools-guide-chromium/media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: /microsoft-edge/devtools-guide-chromium/media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: /microsoft-edge/devtools-guide-chromium/media/expand-icon.msft.png  
[ImageIntoIcon]: /microsoft-edge/devtools-guide-chromium/media/step-into-icon.msft.png  
[ImageOverIcon]: /microsoft-edge/devtools-guide-chromium/media/step-over-icon.msft.png  
[ImageResumeIcon]: /microsoft-edge/devtools-guide-chromium/media/resume-script-run-icon.msft.png  

[ImageJSBugs]: /microsoft-edge/devtools-guide-chromium/media/javascript-js-demo-bad.msft.png "图1： 5 + 1 的结果是51，但应该是6"  
[ImageJSConsole]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-empty.msft.png "图2：控制台面板"  
[ImageJSSources]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-sections.msft.png "图3： "源" 面板"  
[ImageJSSourcesAnnotated]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-sections-annotated.msft.png "图4： "源" 面板 UI 的3个部分"  
[ImageJSClickCheckbox]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png "图5：已启用 "单击" 复选框"  
[ImageJSLineOfCodeBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused.msft.png "图6： DevTools 在行32上的代码行断点处暂停"  
[ImageJSScope]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-scope.msft.png "图7： "范围" 窗格"  
[ImageJSWatchExpression]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-watch.msft.png "图8： "监视表达式" 窗格"  
[ImageJSConsoleEvaluated]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-console.msft.png "在评估 parseInt （addend1） + parseInt （addend2）之后的控制台抽屉"  

<!-- links -->  

<!--[JSBreakpoints]: breakpoints.md "JavaScript Breakpoints"  -->  
<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->
<span data-ttu-id="1210f-282">[OpenDebugJSDemo]： https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示"</span><span class="sxs-lookup"><span data-stu-id="1210f-282">[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "Open Demo"</span></span>  
<!--[JSReferenceStepping]: reference.md#stepping "Reference Stepping"  -->

> [!NOTE]
> <span data-ttu-id="1210f-283">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1210f-283">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1210f-284">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="1210f-284">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="1210f-286">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1210f-286">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
