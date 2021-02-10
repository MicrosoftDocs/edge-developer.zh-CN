---
description: 了解如何使用 Microsoft Edge DevTools 查找和修复 JavaScript Bug。
title: 在 Microsoft Edge DevTools 中调试 JavaScript 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/09/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b036fc87149d13446ab1bc05afc8fc8631d27c8d
ms.sourcegitcommit: e737277744dd25a7585c113eef22a2aa4d4c167f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "11325944"
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
# <span data-ttu-id="67f4b-104">开始在 Microsoft Edge DevTools 中调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="67f4b-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="67f4b-105">本文将指导你调试 DevTools 中任何 JavaScript 问题的基本工作流。</span><span class="sxs-lookup"><span data-stu-id="67f4b-105">This article teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <span data-ttu-id="67f4b-106">步骤 1：重现 Bug</span><span class="sxs-lookup"><span data-stu-id="67f4b-106">Step 1: Reproduce the bug</span></span>  

<span data-ttu-id="67f4b-107">查找一系列持续重现 Bug 的操作始终是调试的第一步。</span><span class="sxs-lookup"><span data-stu-id="67f4b-107">Finding a series of actions that consistently reproduce a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="67f4b-108">选择 **"打开演示"。**</span><span class="sxs-lookup"><span data-stu-id="67f4b-108">Choose **Open Demo**.</span></span>  <span data-ttu-id="67f4b-109">按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后打开新浏览器选项卡中的演示。</span><span class="sxs-lookup"><span data-stu-id="67f4b-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and open the demo in a new browser tab.</span></span>  
    
    [<span data-ttu-id="67f4b-110">打开演示</span><span class="sxs-lookup"><span data-stu-id="67f4b-110">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="67f4b-111">在 `5` 数字 **1 文本框** 中输入。</span><span class="sxs-lookup"><span data-stu-id="67f4b-111">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="67f4b-112">在 `1` " **数字 2"** 文本框中输入。</span><span class="sxs-lookup"><span data-stu-id="67f4b-112">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="67f4b-113">选择 **"添加数字 1"和"数字 2"。**</span><span class="sxs-lookup"><span data-stu-id="67f4b-113">Choose **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="67f4b-114">按钮下方的标签显示 `5 + 1 = 51` 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-114">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="67f4b-115">结果应为 `6` 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-115">The result should be `6`.</span></span>  <span data-ttu-id="67f4b-116">接下来，修复作为 Bug 的添加错误。</span><span class="sxs-lookup"><span data-stu-id="67f4b-116">Next, fix the addition error that is the bug.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果为 51，但应为 6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` <span data-ttu-id="67f4b-118">结果， `51` 但应</span><span class="sxs-lookup"><span data-stu-id="67f4b-118">results in `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <span data-ttu-id="67f4b-119">步骤 2：熟悉源面板 UI</span><span class="sxs-lookup"><span data-stu-id="67f4b-119">Step 2: Get familiar with the Sources panel UI</span></span>  

<span data-ttu-id="67f4b-120">DevTools 为不同的任务提供了许多不同的工具。</span><span class="sxs-lookup"><span data-stu-id="67f4b-120">DevTools provides many different tools for different tasks.</span></span>  <span data-ttu-id="67f4b-121">不同的任务包括更改 CSS、分析页面加载性能和监视网络请求。</span><span class="sxs-lookup"><span data-stu-id="67f4b-121">Different tasks include changing CSS, profiling page-load performance, and monitoring network requests.</span></span>  <span data-ttu-id="67f4b-122">" **源** "面板是调试 JavaScript 的地方。</span><span class="sxs-lookup"><span data-stu-id="67f4b-122">The **Sources** panel is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="67f4b-123">按 \ (`Control` + `Shift` + `J` Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="67f4b-123">Open DevTools by pressing `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="67f4b-124">此快捷方式将打开 **控制台** 面板。</span><span class="sxs-lookup"><span data-stu-id="67f4b-124">This shortcut opens the **Console** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="控制台面板" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="67f4b-126">控制台**工具**</span><span class="sxs-lookup"><span data-stu-id="67f4b-126">The **Console** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67f4b-127">选择 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="67f4b-127">Choose the **Sources** tool.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text=""源"面板" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="67f4b-129">" **源"** 面板</span><span class="sxs-lookup"><span data-stu-id="67f4b-129">The **Sources** panel</span></span>  
    :::image-end:::  
    
<span data-ttu-id="67f4b-130">源 **面板** UI 有三个部分。</span><span class="sxs-lookup"><span data-stu-id="67f4b-130">The **Sources** panel UI has three parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="源面板 UI 的 3 个部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="67f4b-132">源面板 UI 的 3**个部分**</span><span class="sxs-lookup"><span data-stu-id="67f4b-132">The 3 parts of the **Sources** panel UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="67f4b-133">文件 **导航器** 窗格 \ (上图的第 1 部分\) 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-133">The **File Navigator** pane \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="67f4b-134">此处列出了网页请求的所有文件。</span><span class="sxs-lookup"><span data-stu-id="67f4b-134">Every file that the webpage requests is listed here.</span></span>  
1.  <span data-ttu-id="67f4b-135">" **代码编辑器** "窗格 \ (上图的第 2 部分\) 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-135">The **Code Editor** pane \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="67f4b-136">在"文件导航器"\*\*\*\* 窗格中选择文件后，该文件的内容会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="67f4b-136">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="67f4b-137">上 **图中的 JavaScript** 调试窗格 \ (Section 3\) 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-137">The **JavaScript Debugging** pane \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="67f4b-138">用于检查网页的 JavaScript 的各种工具。</span><span class="sxs-lookup"><span data-stu-id="67f4b-138">Various tools for inspecting the JavaScript for the webpage.</span></span>  <span data-ttu-id="67f4b-139">如果 DevTools 窗口很宽，则此窗格显示在代码编辑器 **窗格的右侧** 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-139">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  
    
## <span data-ttu-id="67f4b-140">步骤 3：使用断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="67f4b-140">Step 3: Pause the code with a breakpoint</span></span>  

<span data-ttu-id="67f4b-141">调试此类问题的常见方法是在代码中插入多个语句，然后在脚本运行时 `console.log()` 检查值。</span><span class="sxs-lookup"><span data-stu-id="67f4b-141">A common method for debugging this type of problem is to insert several `console.log()` statements into the code and then to inspect values as the script runs.</span></span>  <span data-ttu-id="67f4b-142">例如：</span><span class="sxs-lookup"><span data-stu-id="67f4b-142">For example:</span></span>  

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

<span data-ttu-id="67f4b-143">`console.log()`虽然该方法可能会完成工作，但断点可以\*\*\*\* 更快地完成。</span><span class="sxs-lookup"><span data-stu-id="67f4b-143">The `console.log()` method may get the job done, but **breakpoints** get it done faster.</span></span>  <span data-ttu-id="67f4b-144">断点允许你在运行时中间暂停代码，并检查当时的所有值。</span><span class="sxs-lookup"><span data-stu-id="67f4b-144">A breakpoint lets you pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="67f4b-145">断点与该方法相比有一 `console.log()` 些优势：</span><span class="sxs-lookup"><span data-stu-id="67f4b-145">Breakpoints have a few advantages over the `console.log()` method:</span></span>  

*   <span data-ttu-id="67f4b-146">With `console.log()` ， you need to manually open the source code， find the relevant code， insert the `console.log()` statements， and then refresh the webpage to display the messages in the **Console.**</span><span class="sxs-lookup"><span data-stu-id="67f4b-146">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then refresh the webpage to display the messages in the **Console**.</span></span>  <span data-ttu-id="67f4b-147">使用断点时，您可能会暂停相关代码，甚至不知道代码的构建方式。</span><span class="sxs-lookup"><span data-stu-id="67f4b-147">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="67f4b-148">在 `console.log()` 语句中，需要显式指定要检查的每个值。</span><span class="sxs-lookup"><span data-stu-id="67f4b-148">In your `console.log()` statements, you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="67f4b-149">使用断点时，DevTools 将同时显示所有变量的值。</span><span class="sxs-lookup"><span data-stu-id="67f4b-149">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="67f4b-150">有时，影响代码的变量被隐藏和混淆。</span><span class="sxs-lookup"><span data-stu-id="67f4b-150">Sometimes variables that affect your code are hidden and obfuscated.</span></span>  
    
<span data-ttu-id="67f4b-151">简而言之，断点可以帮助你更快地查找和修复 `console.log()` Bug，而不是方法。</span><span class="sxs-lookup"><span data-stu-id="67f4b-151">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="67f4b-152">如果你后退一步并思考应用的工作原理，你可能会有根据地猜测错误的总和 \ (\) 是在与"添加数字 1"和"数字 `5 + 1 = 51` `click` **2"** 按钮关联的事件侦听器中计算的。</span><span class="sxs-lookup"><span data-stu-id="67f4b-152">If you step back and think about how the app works, you may make an educated guess that the incorrect sum \(`5 + 1 = 51`\) is computed in the `click` event listener associated with the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="67f4b-153">因此，您可能想要在侦听器运行时暂停 `click` 代码。</span><span class="sxs-lookup"><span data-stu-id="67f4b-153">So, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="67f4b-154">**事件侦听器断点** 让你可以完全实现此要求：</span><span class="sxs-lookup"><span data-stu-id="67f4b-154">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="67f4b-155">在 **JavaScript 调试** 窗格中，选择 **事件侦听器断点** 以展开该部分。</span><span class="sxs-lookup"><span data-stu-id="67f4b-155">In the **JavaScript Debugging** pane, choose **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="67f4b-156">DevTools 显示可展开事件类别的列表，如 **动画** 和 **剪贴板**。</span><span class="sxs-lookup"><span data-stu-id="67f4b-156">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="67f4b-157">在" **鼠标** 事件"类别旁边， **选择"** 展开 (![ 展开图标 ][ImageExpandIcon] \) 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-157">Next to the **Mouse** event category, choose **Expand** \(![Expand icon][ImageExpandIcon]\).</span></span>  <span data-ttu-id="67f4b-158">DevTools 显示鼠标事件的列表，如 **单击** 和 **鼠标按下**。</span><span class="sxs-lookup"><span data-stu-id="67f4b-158">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="67f4b-159">每个事件旁边都有一个复选框。</span><span class="sxs-lookup"><span data-stu-id="67f4b-159">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="67f4b-160">选中复选框，单击 **旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="67f4b-160">Choose the checkbox next to **click**.</span></span>  <span data-ttu-id="67f4b-161">DevTools 现在设置为在任何事件侦听器运行时 `click` 自动暂停。</span><span class="sxs-lookup"><span data-stu-id="67f4b-161">DevTools is now set up to automatically pause when any `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="选中单击旁边的复选框" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="67f4b-163">选中单击旁边的 **复选框**</span><span class="sxs-lookup"><span data-stu-id="67f4b-163">Choose the checkbox next to **click**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67f4b-164">返回到演示，再次选择"**添加数字 1"和"数字 2"。**</span><span class="sxs-lookup"><span data-stu-id="67f4b-164">Back on the demo, choose **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="67f4b-165">DevTools 暂停演示，并突出显示"源"面板中的一 **行** 代码。</span><span class="sxs-lookup"><span data-stu-id="67f4b-165">DevTools pauses the demo and highlights a line of code in the **Sources** panel.</span></span>  <span data-ttu-id="67f4b-166">DevTools 应在 第 16 行中暂停 `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-166">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="67f4b-167">如果暂停另一行代码，请按 Resume **Script Execution** \ (![ Resume Script Execution ][ImageResumeIcon] \) 直到您暂停到正确的行。</span><span class="sxs-lookup"><span data-stu-id="67f4b-167">If you pause on a different line of code, press **Resume Script Execution** \(![Resume Script Execution][ImageResumeIcon]\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="67f4b-168">如果您在另一行上暂停，则具有一个浏览器扩展，该扩展在所访问的每一个网页上注册 `click` 事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="67f4b-168">If you paused on a different line, you have a browser extension that registers a `click` event listener on every webpage that you visit.</span></span>  <span data-ttu-id="67f4b-169">你已暂停到 `click` 扩展的侦听器中。</span><span class="sxs-lookup"><span data-stu-id="67f4b-169">You were paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="67f4b-170">如果使用 InPrivate 模式在\*\*\*\* 禁用所有扩展的专用模式下进行浏览，你可能会看到每次在所需的代码行上暂停。</span><span class="sxs-lookup"><span data-stu-id="67f4b-170">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="67f4b-171">**事件侦听器断点** 只是 DevTools 中提供的许多类型的断点之一。</span><span class="sxs-lookup"><span data-stu-id="67f4b-171">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="67f4b-172">记住所有不同类型的内容，以帮助你尽快调试不同的方案。</span><span class="sxs-lookup"><span data-stu-id="67f4b-172">Memorize all the different types to help you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <span data-ttu-id="67f4b-173">步骤 4：逐步执行代码</span><span class="sxs-lookup"><span data-stu-id="67f4b-173">Step 4: Step through the code</span></span>  

<span data-ttu-id="67f4b-174">出现 Bug 的一个常见原因是脚本按错误的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="67f4b-174">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="67f4b-175">单步执行代码允许你演练代码的运行时。</span><span class="sxs-lookup"><span data-stu-id="67f4b-175">Stepping through your code allows you to walk through the runtime of your code.</span></span>  <span data-ttu-id="67f4b-176">一次完成一行，以帮助你准确了解代码以与预期不同的顺序运行在哪里。</span><span class="sxs-lookup"><span data-stu-id="67f4b-176">You walk through one line at a time to help you figure out exactly where your code is running in a different order than you expect.</span></span>  <span data-ttu-id="67f4b-177">立即尝试：</span><span class="sxs-lookup"><span data-stu-id="67f4b-177">Try it now:</span></span>  

1.  <span data-ttu-id="67f4b-178">Choose **Step over next function call** \ (Step over next function call ![ ][ImageOverIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="67f4b-178">Choose **Step over next function call** \(![Step over next function call][ImageOverIcon]\).</span></span>  <span data-ttu-id="67f4b-179">DevTools 无需单步执行即可运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="67f4b-179">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="67f4b-180">DevTools 跳过几行代码。</span><span class="sxs-lookup"><span data-stu-id="67f4b-180">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="67f4b-181">这是因为计算 `inputsAreEmpty()` 结果为 false，因此语句的代码块 `if` 不会运行。</span><span class="sxs-lookup"><span data-stu-id="67f4b-181">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="67f4b-182">在\*\*\*\* DevTools 的"源"面板上，选择"单步执行下一个函数调用**\ (** 单步执行下一个函数调用 ![ ][ImageIntoIcon] \) 以单步执行函数运行时，一次一行。 `updateLabel()`</span><span class="sxs-lookup"><span data-stu-id="67f4b-182">On the **Sources** panel of DevTools, choose **Step into next function call** \(![Step into next function call][ImageIntoIcon]\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="67f4b-183">一次查看一行是逐步执行代码的一个基本概念。</span><span class="sxs-lookup"><span data-stu-id="67f4b-183">Reviewing one line at a time is the basic idea of stepping through code.</span></span>  <span data-ttu-id="67f4b-184">如果您查看其中的代码 `get-started.js` ，则会看到该 Bug 可能位于函数 `updateLabel()` 中的某一位置。</span><span class="sxs-lookup"><span data-stu-id="67f4b-184">If you look at the code in `get-started.js`, you see that the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="67f4b-185">与其逐行执行每行代码，不如使用另一种类型的断点将代码暂停到更接近 bug 的可能位置的位置。</span><span class="sxs-lookup"><span data-stu-id="67f4b-185">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <span data-ttu-id="67f4b-186">步骤 5：设置代码行断点</span><span class="sxs-lookup"><span data-stu-id="67f4b-186">Step 5: Set a line-of-code breakpoint</span></span>  

<span data-ttu-id="67f4b-187">代码行断点是最常见的断点类型。</span><span class="sxs-lookup"><span data-stu-id="67f4b-187">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="67f4b-188">当您到达要暂停的特定代码行时，请使用代码行断点。</span><span class="sxs-lookup"><span data-stu-id="67f4b-188">When you get to the specific line of code you want to pause, use a line-of-code breakpoint.</span></span>  

1.  <span data-ttu-id="67f4b-189">查看以下代码的最后一行 `updateLabel()` ：</span><span class="sxs-lookup"><span data-stu-id="67f4b-189">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="67f4b-190">在左侧，此特定代码行的编号显示为**34。**</span><span class="sxs-lookup"><span data-stu-id="67f4b-190">On the left, the number of this particular line of code is displayed as **34**.</span></span>  <span data-ttu-id="67f4b-191">选择第 **34 行**。</span><span class="sxs-lookup"><span data-stu-id="67f4b-191">Choose line **34**.</span></span>  <span data-ttu-id="67f4b-192">DevTools 将红色图标放在 **34 的左侧**。</span><span class="sxs-lookup"><span data-stu-id="67f4b-192">DevTools puts a red icon to the left of **34**.</span></span>  <span data-ttu-id="67f4b-193">红色图标表示代码行断点位于此行上。</span><span class="sxs-lookup"><span data-stu-id="67f4b-193">The red icon indicates that a line-of-code breakpoint is on this line.</span></span>  <span data-ttu-id="67f4b-194">DevTools 始终在运行此代码行之前暂停。</span><span class="sxs-lookup"><span data-stu-id="67f4b-194">DevTools always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="67f4b-195">Choose **Resume script execution** \ (Resume script execution ![ ][ImageResumeIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="67f4b-195">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  <span data-ttu-id="67f4b-196">脚本继续运行，直到到达第 33 行。</span><span class="sxs-lookup"><span data-stu-id="67f4b-196">The script continues running until it reaches line 33.</span></span>  <span data-ttu-id="67f4b-197">在行 31、32 和 33 上，DevTools 在每行中打印分号的右边和 `addend1` `addend2` `sum` 分号的值。</span><span class="sxs-lookup"><span data-stu-id="67f4b-197">On lines 31, 32, and 33, DevTools prints the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools 暂停于第 34 行的代码行断点上" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="67f4b-199">DevTools 暂停于第 34 行的代码行断点上</span><span class="sxs-lookup"><span data-stu-id="67f4b-199">DevTools pauses on the line-of-code breakpoint on line 34</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="67f4b-200">步骤 6：检查变量值</span><span class="sxs-lookup"><span data-stu-id="67f4b-200">Step 6: Check variable values</span></span>  

<span data-ttu-id="67f4b-201">， `addend1` `addend2` 的值， `sum` 看起来可疑。</span><span class="sxs-lookup"><span data-stu-id="67f4b-201">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="67f4b-202">这些值用引号括起来。</span><span class="sxs-lookup"><span data-stu-id="67f4b-202">The values are wrapped in quotes.</span></span>  <span data-ttu-id="67f4b-203">引号表示值是一个字符串，这是一个很好的假设，可以解释 Bug 的原因。</span><span class="sxs-lookup"><span data-stu-id="67f4b-203">The quotations mean that the value is a string, which is a good hypothesis to explain the cause of the bug.</span></span>  <span data-ttu-id="67f4b-204">收集有关情况详细信息。</span><span class="sxs-lookup"><span data-stu-id="67f4b-204">Gather more information about the situation.</span></span>  <span data-ttu-id="67f4b-205">DevTools 提供了许多用于检查变量值的工具。</span><span class="sxs-lookup"><span data-stu-id="67f4b-205">DevTools provides many tools for examining variable values.</span></span>  

### <span data-ttu-id="67f4b-206">方法 1：范围窗格</span><span class="sxs-lookup"><span data-stu-id="67f4b-206">Method 1: The Scope pane</span></span>  

<span data-ttu-id="67f4b-207">如果暂停一行代码，"范围"窗格\*\*\*\* 将显示当前定义的本地和全局变量以及每个变量的值。</span><span class="sxs-lookup"><span data-stu-id="67f4b-207">If you pause on a line of code, the **Scope** pane displays the local and global variables that are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="67f4b-208">它还会显示关闭变量（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="67f4b-208">It also displays closure variables, as applicable.</span></span>  <span data-ttu-id="67f4b-209">双击变量值进行编辑。</span><span class="sxs-lookup"><span data-stu-id="67f4b-209">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="67f4b-210">如果不在代码行上暂停，则 **"范围"** 窗格为空。</span><span class="sxs-lookup"><span data-stu-id="67f4b-210">If you don't pause on a line of code, the **Scope** pane is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text=""范围"窗格" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="67f4b-212">" **范围"** 窗格</span><span class="sxs-lookup"><span data-stu-id="67f4b-212">The **Scope** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="67f4b-213">方法 2：监视表达式</span><span class="sxs-lookup"><span data-stu-id="67f4b-213">Method 2: Watch Expressions</span></span>  

<span data-ttu-id="67f4b-214">通过 **"** 监视表达式"窗格，可以随着时间的推移监视变量的值。</span><span class="sxs-lookup"><span data-stu-id="67f4b-214">The **Watch Expressions** pane lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="67f4b-215">正如名称所示， **监视表达式** 不限于变量。</span><span class="sxs-lookup"><span data-stu-id="67f4b-215">As the name implies, **Watch Expressions** aren't limited to variables.</span></span>  <span data-ttu-id="67f4b-216">你可以将任何有效的 JavaScript 表达式存储在 **监视表达式中**。</span><span class="sxs-lookup"><span data-stu-id="67f4b-216">You may store any valid JavaScript expression in a **Watch Expression**.</span></span>  <span data-ttu-id="67f4b-217">立即尝试。</span><span class="sxs-lookup"><span data-stu-id="67f4b-217">Try it now.</span></span>  

1.  <span data-ttu-id="67f4b-218">选择 **"监视"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="67f4b-218">Choose the **Watch** pane.</span></span>  
1.  <span data-ttu-id="67f4b-219">Choose **Add Expression** \ (Add Expression ![ ][ImageAddIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="67f4b-219">Choose **Add Expression** \(![Add Expression][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="67f4b-220">键入 `typeof sum`。</span><span class="sxs-lookup"><span data-stu-id="67f4b-220">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="67f4b-221">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="67f4b-221">Select `Enter`.</span></span>  <span data-ttu-id="67f4b-222">DevTools 显示 `typeof sum: "string"` 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-222">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="67f4b-223">冒号右边的值是监视表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="67f4b-223">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="67f4b-224">在" **监视表达式** "窗格 \ (右下\) 中，将显示 `typeof sum` 监视表达式。</span><span class="sxs-lookup"><span data-stu-id="67f4b-224">In the **Watch Expression** pane \(bottom-right\) in the following figure, the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="67f4b-225">如果 DevTools 窗口很大，则 **监视** 表达式窗格位于事件侦听器断点窗格 **的右侧** 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-225">If your DevTools window is large, the **Watch Expression** pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="监视表达式窗格" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="67f4b-227">监视 **表达式** 窗格</span><span class="sxs-lookup"><span data-stu-id="67f4b-227">The **Watch Expression** pane</span></span>  
:::image-end:::  

<span data-ttu-id="67f4b-228">正如所怀疑的，当应为数字时，正在作为字符串 `sum` 进行评估。</span><span class="sxs-lookup"><span data-stu-id="67f4b-228">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="67f4b-229">现在确认值类型是 Bug 的原因。</span><span class="sxs-lookup"><span data-stu-id="67f4b-229">You now confirmed value type is the cause of the bug.</span></span>  

### <span data-ttu-id="67f4b-230">方法 3：控制台</span><span class="sxs-lookup"><span data-stu-id="67f4b-230">Method 3: The Console</span></span>  

<span data-ttu-id="67f4b-231">控制台 **允许你** 查看消息，还可以使用它来评估 `console.log()` 任意 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="67f4b-231">The **Console** allows you to view `console.log()` messages and you may also use it to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="67f4b-232">对于调试，可以使用 **控制台** 测试潜在 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="67f4b-232">For debugging, you may use the **Console** to test potential fixes for bugs.</span></span>  <span data-ttu-id="67f4b-233">立即尝试。</span><span class="sxs-lookup"><span data-stu-id="67f4b-233">Try it now.</span></span>  

1.  <span data-ttu-id="67f4b-234">如果 **控制台收** 银机已关闭，请选择 `Escape` 将其打开。</span><span class="sxs-lookup"><span data-stu-id="67f4b-234">If the **Console** drawer is closed, select `Escape` to open it.</span></span>  <span data-ttu-id="67f4b-235">控制台 **箱** 在 DevTools 窗口的下面板中打开。</span><span class="sxs-lookup"><span data-stu-id="67f4b-235">The **Console** drawer opens in the lower panel of the DevTools window.</span></span>  
1.  <span data-ttu-id="67f4b-236">在控制台 **中**，键入 `parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-236">In the **Console**, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="67f4b-237">工具的语句暂停在一行代码上，并且 `addend1` `addend2` 位于范围内。</span><span class="sxs-lookup"><span data-stu-id="67f4b-237">The statement the tool is paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="67f4b-238">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="67f4b-238">Select `Enter`.</span></span>  <span data-ttu-id="67f4b-239">DevTools 计算语句并打印 `6` ，这是预期演示产生的结果。</span><span class="sxs-lookup"><span data-stu-id="67f4b-239">DevTools evaluates the statement and prints `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="在评估 parseInt (addend1) + parseInt (addend2) " lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="67f4b-241">评估 **后的** 控制台箱</span><span class="sxs-lookup"><span data-stu-id="67f4b-241">The **Console** drawer, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <span data-ttu-id="67f4b-242">步骤 7：应用修补程序</span><span class="sxs-lookup"><span data-stu-id="67f4b-242">Step 7: Apply a fix</span></span>  

<span data-ttu-id="67f4b-243">如果找到该 Bug 的修复程序，请通过编辑代码并重新运行演示来尝试修复。</span><span class="sxs-lookup"><span data-stu-id="67f4b-243">If you find a fix for the bug, try out your fix by editing the code and rerunning the demo.</span></span>  <span data-ttu-id="67f4b-244">你可以直接在 DevTools UI 中编辑 JavaScript 代码并应用修复程序。</span><span class="sxs-lookup"><span data-stu-id="67f4b-244">You may edit JavaScript code directly within the DevTools UI and apply the fix.</span></span>  <span data-ttu-id="67f4b-245">立即尝试。</span><span class="sxs-lookup"><span data-stu-id="67f4b-245">Try it now.</span></span>  

1.  <span data-ttu-id="67f4b-246">Choose **Resume script execution** \ (Resume script execution ![ ][ImageResumeIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="67f4b-246">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  
1.  <span data-ttu-id="67f4b-247">在代码 **编辑器中**，将第 32 行替换为 `var sum = addend1 + addend2` `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="67f4b-247">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="67f4b-248">选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="67f4b-248">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="67f4b-249">Choose **Deactivate breakpoints** \ (![ Deactivate breakpoints ][ImageDeactivateIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="67f4b-249">Choose **Deactivate breakpoints** \(![Deactivate breakpoints][ImageDeactivateIcon]\).</span></span>  <span data-ttu-id="67f4b-250">它更改为蓝色以指示选项处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="67f4b-250">It changes blue to indicate the option is active.</span></span>  <span data-ttu-id="67f4b-251">在 **设置 Deactivate** 断点时，DevTools 将忽略你设置的任何断点。</span><span class="sxs-lookup"><span data-stu-id="67f4b-251">While **Deactivate breakpoints** is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="67f4b-252">尝试使用不同值的演示。</span><span class="sxs-lookup"><span data-stu-id="67f4b-252">Try out the demo with different values.</span></span>  <span data-ttu-id="67f4b-253">演示现在计算正确。</span><span class="sxs-lookup"><span data-stu-id="67f4b-253">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="67f4b-254">此工作流仅对浏览器中运行的代码应用修补程序。</span><span class="sxs-lookup"><span data-stu-id="67f4b-254">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="67f4b-255">它不会修复访问网页的所有用户的代码。</span><span class="sxs-lookup"><span data-stu-id="67f4b-255">It does not fix the code for all users that visit your webpage.</span></span>  <span data-ttu-id="67f4b-256">为此，您需要修复服务器上的代码。</span><span class="sxs-lookup"><span data-stu-id="67f4b-256">To do that, you need to fix the code that is on your servers.</span></span>  

## <span data-ttu-id="67f4b-257">后续步骤</span><span class="sxs-lookup"><span data-stu-id="67f4b-257">Next steps</span></span>  

<span data-ttu-id="67f4b-258">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="67f4b-258">Congratulations!</span></span>  <span data-ttu-id="67f4b-259">现在，你已了解如何在调试 JavaScript 时充分利用 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="67f4b-259">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="67f4b-260">本文中学习的工具和方法可以为您节省数百个小时。</span><span class="sxs-lookup"><span data-stu-id="67f4b-260">The tools and methods you learned in this article may save you countless hours.</span></span>  

<span data-ttu-id="67f4b-261">本文仅介绍设置断点的两种方法。</span><span class="sxs-lookup"><span data-stu-id="67f4b-261">This article only taught you two ways to set breakpoints.</span></span>  <span data-ttu-id="67f4b-262">DevTools 提供了许多其他方法，包括以下设置。</span><span class="sxs-lookup"><span data-stu-id="67f4b-262">DevTools offers many other ways including the following settings.</span></span>  

*   <span data-ttu-id="67f4b-263">仅在您提供的条件为 true 时触发的条件断点。</span><span class="sxs-lookup"><span data-stu-id="67f4b-263">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="67f4b-264">捕获或不捕获的异常的断点。</span><span class="sxs-lookup"><span data-stu-id="67f4b-264">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="67f4b-265">当请求的 URL 与提供的子字符串匹配时触发的 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="67f4b-265">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="67f4b-266">有关何时以及如何使用每种类型，请导航到"使用断点暂停[代码"。][DevtoolsJavscriptBreakpoints]</span><span class="sxs-lookup"><span data-stu-id="67f4b-266">For more information about when and how to use each type, navigate to [Pause Your Code With Breakpoints][DevtoolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="67f4b-267">本文中未介绍几个代码单步执行控件。</span><span class="sxs-lookup"><span data-stu-id="67f4b-267">A couple of code stepping controls aren't explained in this article.</span></span>  <span data-ttu-id="67f4b-268">有关详细信息，请导航到["逐行代码"。][DevtoolsJavascriptReferenceStepThroughCode]</span><span class="sxs-lookup"><span data-stu-id="67f4b-268">For more information, navigate to [Step over line of code][DevtoolsJavascriptReferenceStepThroughCode].</span></span>  

## <span data-ttu-id="67f4b-269">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="67f4b-269">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: ../media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageIntoIcon]: ../media/step-into-icon.msft.png  
[ImageOverIcon]: ../media/step-over-icon.msft.png  
[ImageResumeIcon]: ../media/resume-script-run-icon.msft.png  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools |Microsoft Docs"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "分步执行代码 - JavaScript 调试|Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示|小故障"  

> [!NOTE]
> <span data-ttu-id="67f4b-273">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="67f4b-273">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="67f4b-274">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="67f4b-274">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="67f4b-276">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="67f4b-276">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
