---
description: 了解如何使用 Microsoft Edge DevTools 查找和修复 JavaScript Bug。
title: 在 Microsoft Edge DevTools 中调试 JavaScript 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: bbfb766bcc03e4c4fe0f975f1ecfccbef08084be
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439463"
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
# <a name="get-started-with-debugging-javascript-in-microsoft-edge-devtools"></a><span data-ttu-id="3e036-104">在 Microsoft Edge DevTools 中调试 JavaScript 入门</span><span class="sxs-lookup"><span data-stu-id="3e036-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="3e036-105">本文将指导你调试 DevTools 中任何 JavaScript 问题的基本工作流。</span><span class="sxs-lookup"><span data-stu-id="3e036-105">This article teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <a name="step-1-reproduce-the-bug"></a><span data-ttu-id="3e036-106">步骤 1：重现 Bug</span><span class="sxs-lookup"><span data-stu-id="3e036-106">Step 1: Reproduce the bug</span></span>  

<span data-ttu-id="3e036-107">查找一系列持续重现 Bug 的操作始终是调试的第一步。</span><span class="sxs-lookup"><span data-stu-id="3e036-107">Finding a series of actions that consistently reproduce a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="3e036-108">选择 **"打开演示"。**</span><span class="sxs-lookup"><span data-stu-id="3e036-108">Choose **Open Demo**.</span></span>  <span data-ttu-id="3e036-109">按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后打开新浏览器选项卡中的演示。</span><span class="sxs-lookup"><span data-stu-id="3e036-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and open the demo in a new browser tab.</span></span>  
    
    [<span data-ttu-id="3e036-110">打开演示</span><span class="sxs-lookup"><span data-stu-id="3e036-110">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="3e036-111">在 `5` " **数字 1"文本框** 中输入。</span><span class="sxs-lookup"><span data-stu-id="3e036-111">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="3e036-112">在 `1` "数字 **2"文本框** 中输入。</span><span class="sxs-lookup"><span data-stu-id="3e036-112">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="3e036-113">选择 **"添加数字 1"和"数字 2"。**</span><span class="sxs-lookup"><span data-stu-id="3e036-113">Choose **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="3e036-114">按钮下方的标签显示 `5 + 1 = 51` 。</span><span class="sxs-lookup"><span data-stu-id="3e036-114">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="3e036-115">结果应为 `6` 。</span><span class="sxs-lookup"><span data-stu-id="3e036-115">The result should be `6`.</span></span>  <span data-ttu-id="3e036-116">接下来，修复 Bug 的添加错误。</span><span class="sxs-lookup"><span data-stu-id="3e036-116">Next, fix the addition error that is the bug.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果为 51，但应为 6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` <span data-ttu-id="3e036-118">结果为 `51` ，但应为</span><span class="sxs-lookup"><span data-stu-id="3e036-118">results in `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <a name="step-2-get-familiar-with-the-sources-tool-ui"></a><span data-ttu-id="3e036-119">步骤 2：熟悉源工具 UI</span><span class="sxs-lookup"><span data-stu-id="3e036-119">Step 2: Get familiar with the Sources tool UI</span></span>  

<span data-ttu-id="3e036-120">DevTools 为不同的任务提供了许多不同的工具。</span><span class="sxs-lookup"><span data-stu-id="3e036-120">DevTools provides many different tools for different tasks.</span></span>  <span data-ttu-id="3e036-121">不同的任务包括更改 CSS、分析页面加载性能和监视网络请求。</span><span class="sxs-lookup"><span data-stu-id="3e036-121">Different tasks include changing CSS, profiling page-load performance, and monitoring network requests.</span></span>  <span data-ttu-id="3e036-122">" **源** "工具是调试 JavaScript 的地方。</span><span class="sxs-lookup"><span data-stu-id="3e036-122">The **Sources** tool is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="3e036-123">若要在\*\*\*\* DevTools 中打开控制台工具，请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="3e036-123">To open the **Console** tool in DevTools, select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="控制台工具" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="3e036-125">控制台**工具**</span><span class="sxs-lookup"><span data-stu-id="3e036-125">The **Console** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e036-126">选择" **源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="3e036-126">Choose the **Sources** tool.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="源工具" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="3e036-128">源**工具**</span><span class="sxs-lookup"><span data-stu-id="3e036-128">The **Sources** tool</span></span>  
    :::image-end:::  
    
<span data-ttu-id="3e036-129">源 **工具** UI 有三个部分。</span><span class="sxs-lookup"><span data-stu-id="3e036-129">The **Sources** tool UI has three parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="源工具 UI 的 3 个部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="3e036-131">源工具 UI 的 3**个部分**</span><span class="sxs-lookup"><span data-stu-id="3e036-131">The 3 parts of the **Sources** tool UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="3e036-132">文件 **导航器** 面板 \ (上图\第 1 部分) 。</span><span class="sxs-lookup"><span data-stu-id="3e036-132">The **File Navigator** panel \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="3e036-133">此处列出了网页请求的所有文件。</span><span class="sxs-lookup"><span data-stu-id="3e036-133">Every file that the webpage requests is listed here.</span></span>  
1.  <span data-ttu-id="3e036-134">上 **图\ (** 第 2 节中的代码编辑器面板) 。</span><span class="sxs-lookup"><span data-stu-id="3e036-134">The **Code Editor** panel \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="3e036-135">在"文件导航器"窗格中 **选择** 文件后，该文件的内容将显示在此处。</span><span class="sxs-lookup"><span data-stu-id="3e036-135">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="3e036-136">上 **图中的 JavaScript** 调试 (第 3 部分) 。</span><span class="sxs-lookup"><span data-stu-id="3e036-136">The **JavaScript Debugging** panel \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="3e036-137">用于检查网页的 JavaScript 的各种工具。</span><span class="sxs-lookup"><span data-stu-id="3e036-137">Various tools for inspecting the JavaScript for the webpage.</span></span>  <span data-ttu-id="3e036-138">如果 DevTools 窗口很宽，则此窗格显示在"代码编辑器" **窗格的右侧** 。</span><span class="sxs-lookup"><span data-stu-id="3e036-138">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  
    
## <a name="step-3-pause-the-code-with-a-breakpoint"></a><span data-ttu-id="3e036-139">步骤 3：使用断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="3e036-139">Step 3: Pause the code with a breakpoint</span></span>  

<span data-ttu-id="3e036-140">调试此类问题的常见方法是在代码中插入多个语句，然后在脚本运行时 `console.log()` 检查值。</span><span class="sxs-lookup"><span data-stu-id="3e036-140">A common method for debugging this type of problem is to insert several `console.log()` statements into the code and then to inspect values as the script runs.</span></span>  <span data-ttu-id="3e036-141">例如：</span><span class="sxs-lookup"><span data-stu-id="3e036-141">For example:</span></span>  

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

<span data-ttu-id="3e036-142">`console.log()`方法可能会完成作业，但**断**点可以更快地完成。</span><span class="sxs-lookup"><span data-stu-id="3e036-142">The `console.log()` method may get the job done, but **breakpoints** get it done faster.</span></span>  <span data-ttu-id="3e036-143">断点允许你在运行时中间暂停代码，并检查此时的所有值。</span><span class="sxs-lookup"><span data-stu-id="3e036-143">A breakpoint allows you to pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="3e036-144">断点与方法相比具有以下 `console.log()` 优点。</span><span class="sxs-lookup"><span data-stu-id="3e036-144">Breakpoints have the following advantages over the `console.log()` method.</span></span>  

*   <span data-ttu-id="3e036-145">使用 ，需要手动打开源代码、查找相关代码、插入语句，然后刷新网页以显示控制台 `console.log()` `console.log()` **中的消息**。</span><span class="sxs-lookup"><span data-stu-id="3e036-145">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then refresh the webpage to display the messages in the **Console**.</span></span>  <span data-ttu-id="3e036-146">对于断点，您可能会暂停相关代码，甚至不知道代码的构建方式。</span><span class="sxs-lookup"><span data-stu-id="3e036-146">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="3e036-147">在 `console.log()` 语句中，需要明确指定要检查的每个值。</span><span class="sxs-lookup"><span data-stu-id="3e036-147">In your `console.log()` statements, you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="3e036-148">对于断点，DevTools 显示当时所有变量的值。</span><span class="sxs-lookup"><span data-stu-id="3e036-148">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="3e036-149">有时，影响代码的变量被隐藏和混淆。</span><span class="sxs-lookup"><span data-stu-id="3e036-149">Sometimes variables that affect your code are hidden and obfuscated.</span></span>  
    
<span data-ttu-id="3e036-150">简而言之，断点可以帮助你更快地查找和修复 `console.log()` Bug。</span><span class="sxs-lookup"><span data-stu-id="3e036-150">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="3e036-151">如果你后退一步并思考应用的工作原理，你可能会有根据地猜出错误的总和 \ (\) 是在与"添加数字 `5 + 1 = 51` 1"和"数字 `click` **2"** 按钮关联的事件侦听器中计算的。</span><span class="sxs-lookup"><span data-stu-id="3e036-151">If you step back and think about how the app works, you may make an educated guess that the incorrect sum \(`5 + 1 = 51`\) is computed in the `click` event listener associated with the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="3e036-152">因此，你可能想要在侦听器运行时暂停 `click` 代码。</span><span class="sxs-lookup"><span data-stu-id="3e036-152">So, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="3e036-153">**事件侦听器断点** 使你可以完全实现此要求：</span><span class="sxs-lookup"><span data-stu-id="3e036-153">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="3e036-154">在 **"JavaScript 调试"** 窗格中，选择 **"事件侦听器断点"** 以展开部分。</span><span class="sxs-lookup"><span data-stu-id="3e036-154">In the **JavaScript Debugging** pane, choose **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="3e036-155">DevTools 显示可展开事件类别的列表，如 **动画** 和 **剪贴板**。</span><span class="sxs-lookup"><span data-stu-id="3e036-155">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="3e036-156">在鼠标事件 **类别** 旁边， **选择展开** \ (![ 展开图标 ](../media/expand-icon.msft.png) \) 。</span><span class="sxs-lookup"><span data-stu-id="3e036-156">Next to the **Mouse** event category, choose **Expand** \(![Expand icon](../media/expand-icon.msft.png)\).</span></span>  <span data-ttu-id="3e036-157">DevTools 显示鼠标事件的列表 **，如单击** 和 **鼠标按下**。</span><span class="sxs-lookup"><span data-stu-id="3e036-157">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="3e036-158">每个事件旁边都有一个复选框。</span><span class="sxs-lookup"><span data-stu-id="3e036-158">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="3e036-159">选择单击 旁边的 **复选框**。</span><span class="sxs-lookup"><span data-stu-id="3e036-159">Choose the checkbox next to **click**.</span></span>  <span data-ttu-id="3e036-160">DevTools 现在设置为在任何事件侦听器运行时 `click` 自动暂停。</span><span class="sxs-lookup"><span data-stu-id="3e036-160">DevTools is now set up to automatically pause when any `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="选择单击旁边的复选框" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="3e036-162">选择单击旁边的 **复选框**</span><span class="sxs-lookup"><span data-stu-id="3e036-162">Choose the checkbox next to **click**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e036-163">返回到演示，再次选择"**添加数字 1"和"数字 2"。**</span><span class="sxs-lookup"><span data-stu-id="3e036-163">Back on the demo, choose **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="3e036-164">DevTools 暂停演示，并突出显示"源"工具中的一 **行** 代码。</span><span class="sxs-lookup"><span data-stu-id="3e036-164">DevTools pauses the demo and highlights a line of code in the **Sources** tool.</span></span>  <span data-ttu-id="3e036-165">DevTools 应在 的第 16 行暂停 `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="3e036-165">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="3e036-166">如果您在其他代码行上暂停，请选择"恢复脚本 **执行" (** Resume Script ![ Execution ](../media/resume-script-run-icon.msft.png) \) 直到您暂停到正确的行。</span><span class="sxs-lookup"><span data-stu-id="3e036-166">If you pause on a different line of code, choose **Resume Script Execution** \(![Resume Script Execution](../media/resume-script-run-icon.msft.png)\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3e036-167">如果您在另一行上暂停，则有一个浏览器扩展，该扩展在所访问的每一个 `click` 网页上注册事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="3e036-167">If you paused on a different line, you have a browser extension that registers a `click` event listener on every webpage that you visit.</span></span>  <span data-ttu-id="3e036-168">在扩展的 `click` 侦听器中暂停。</span><span class="sxs-lookup"><span data-stu-id="3e036-168">You are paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="3e036-169">如果使用 InPrivate 模式在\*\*\*\* 专用 中浏览，这将禁用所有扩展，您可能会看到每次在所需的代码行上暂停。</span><span class="sxs-lookup"><span data-stu-id="3e036-169">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="3e036-170">**事件侦听器断点** 只是 DevTools 中提供的许多类型的断点之一。</span><span class="sxs-lookup"><span data-stu-id="3e036-170">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="3e036-171">记住所有不同类型的以帮助你尽快调试不同的方案。</span><span class="sxs-lookup"><span data-stu-id="3e036-171">Memorize all the different types to help you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <a name="step-4-step-through-the-code"></a><span data-ttu-id="3e036-172">步骤 4：逐步执行代码</span><span class="sxs-lookup"><span data-stu-id="3e036-172">Step 4: Step through the code</span></span>  

<span data-ttu-id="3e036-173">Bug 的一个常见原因是脚本按错误的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="3e036-173">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="3e036-174">单步执行代码允许你演练代码的运行时。</span><span class="sxs-lookup"><span data-stu-id="3e036-174">Stepping through your code allows you to walk through the runtime of your code.</span></span>  <span data-ttu-id="3e036-175">一次执行一行，以帮助你准确了解代码以与预期不同的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="3e036-175">You walk through one line at a time to help you figure out exactly where your code is running in a different order than you expect.</span></span>  <span data-ttu-id="3e036-176">立即尝试：</span><span class="sxs-lookup"><span data-stu-id="3e036-176">Try it now:</span></span>  

1.  <span data-ttu-id="3e036-177">Choose **Step over next function call** \ (Step over next function call ![ ](../media/step-over-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="3e036-177">Choose **Step over next function call** \(![Step over next function call](../media/step-over-icon.msft.png)\).</span></span>  <span data-ttu-id="3e036-178">DevTools 无需单步执行即可运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="3e036-178">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="3e036-179">DevTools 跳过几行代码。</span><span class="sxs-lookup"><span data-stu-id="3e036-179">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="3e036-180">这是因为计算 `inputsAreEmpty()` 结果为 false，因此语句的代码 `if` 块不会运行。</span><span class="sxs-lookup"><span data-stu-id="3e036-180">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="3e036-181">在\*\*\*\* DevTools 的"源"工具上，选择"单步执行下一个函数调用**\ (** 单步执行下一个函数调用 ![ ](../media/step-into-icon.msft.png) \) "以逐步完成函数的运行时，一次一行 `updateLabel()` 。</span><span class="sxs-lookup"><span data-stu-id="3e036-181">On the **Sources** tool of DevTools, choose **Step into next function call** \(![Step into next function call](../media/step-into-icon.msft.png)\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="3e036-182">一次查看一行是单步执行代码的基本概念。</span><span class="sxs-lookup"><span data-stu-id="3e036-182">Reviewing one line at a time is the basic idea of stepping through code.</span></span>  <span data-ttu-id="3e036-183">如果查看 中的代码 `get-started.js` ，则 bug 可能位于 函数中的 `updateLabel()` 某一位置。</span><span class="sxs-lookup"><span data-stu-id="3e036-183">If you review the code in `get-started.js`, the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="3e036-184">与其单步执行每行代码，不如使用另一种类型的断点来暂停代码，使代码更接近 bug 的可能位置。</span><span class="sxs-lookup"><span data-stu-id="3e036-184">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <a name="step-5-set-a-line-of-code-breakpoint"></a><span data-ttu-id="3e036-185">步骤 5：设置代码行断点</span><span class="sxs-lookup"><span data-stu-id="3e036-185">Step 5: Set a line-of-code breakpoint</span></span>  

<span data-ttu-id="3e036-186">代码行断点是最常见的断点类型。</span><span class="sxs-lookup"><span data-stu-id="3e036-186">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="3e036-187">当到达要暂停的特定代码行时，请使用代码行断点。</span><span class="sxs-lookup"><span data-stu-id="3e036-187">When you get to the specific line of code you want to pause, use a line-of-code breakpoint.</span></span>  

1.  <span data-ttu-id="3e036-188">查看 中的最后一行代码 `updateLabel()` ：</span><span class="sxs-lookup"><span data-stu-id="3e036-188">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="3e036-189">在左侧，此特定代码行的编号显示为 **34**。</span><span class="sxs-lookup"><span data-stu-id="3e036-189">On the left, the number of this particular line of code is displayed as **34**.</span></span>  <span data-ttu-id="3e036-190">选择第 **34 行**。</span><span class="sxs-lookup"><span data-stu-id="3e036-190">Choose line **34**.</span></span>  <span data-ttu-id="3e036-191">DevTools 在 **34**左侧显示一个红色图标。</span><span class="sxs-lookup"><span data-stu-id="3e036-191">DevTools displays a red icon to the left of **34**.</span></span>  <span data-ttu-id="3e036-192">红色图标表示代码行断点位于此行上。</span><span class="sxs-lookup"><span data-stu-id="3e036-192">The red icon indicates that a line-of-code breakpoint is on this line.</span></span>  <span data-ttu-id="3e036-193">DevTools 始终在运行此代码行之前暂停。</span><span class="sxs-lookup"><span data-stu-id="3e036-193">DevTools always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="3e036-194">Choose **Resume script execution** \ (Resume script execution ![ ](../media/resume-script-run-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="3e036-194">Choose **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\).</span></span>  <span data-ttu-id="3e036-195">脚本将继续运行，直到到达第 33 行。</span><span class="sxs-lookup"><span data-stu-id="3e036-195">The script continues to run until it reaches line 33.</span></span>  <span data-ttu-id="3e036-196">在行 31、32 和 33 上，DevTools 在每一行上打印分号右边的 、 和 `addend1` `addend2` `sum` 值。</span><span class="sxs-lookup"><span data-stu-id="3e036-196">On lines 31, 32, and 33, DevTools prints the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools 暂停第 34 行的代码行断点" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="3e036-198">DevTools 暂停第 34 行的代码行断点</span><span class="sxs-lookup"><span data-stu-id="3e036-198">DevTools pauses on the line-of-code breakpoint on line 34</span></span>  
    :::image-end:::  
    
## <a name="step-6-check-variable-values"></a><span data-ttu-id="3e036-199">步骤 6：检查变量值</span><span class="sxs-lookup"><span data-stu-id="3e036-199">Step 6: Check variable values</span></span>  

<span data-ttu-id="3e036-200">、 `addend1` 和 `addend2` `sum` 的值看起来可疑。</span><span class="sxs-lookup"><span data-stu-id="3e036-200">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="3e036-201">这些值用引号括起来。</span><span class="sxs-lookup"><span data-stu-id="3e036-201">The values are wrapped in quotes.</span></span>  <span data-ttu-id="3e036-202">引号表示值是字符串，这是解释 Bug 原因的一个很好的假设。</span><span class="sxs-lookup"><span data-stu-id="3e036-202">The quotations mean that the value is a string, which is a good hypothesis to explain the cause of the bug.</span></span>  <span data-ttu-id="3e036-203">收集有关情况详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e036-203">Gather more information about the situation.</span></span>  <span data-ttu-id="3e036-204">DevTools 提供了许多用于检查变量值的工具。</span><span class="sxs-lookup"><span data-stu-id="3e036-204">DevTools provides many tools for examining variable values.</span></span>  

### <a name="method-1-the-scope-panel"></a><span data-ttu-id="3e036-205">方法 1：范围面板</span><span class="sxs-lookup"><span data-stu-id="3e036-205">Method 1: The Scope panel</span></span>  

<span data-ttu-id="3e036-206">如果暂停一行代码，"范围"面板\*\*\*\* 将显示当前定义的本地和全局变量以及每个变量的值。</span><span class="sxs-lookup"><span data-stu-id="3e036-206">If you pause on a line of code, the **Scope** panel displays the local and global variables that are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="3e036-207">它还会显示关闭变量（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="3e036-207">It also displays closure variables, as applicable.</span></span>  <span data-ttu-id="3e036-208">双击变量值进行编辑。</span><span class="sxs-lookup"><span data-stu-id="3e036-208">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="3e036-209">如果未在代码行上暂停，则 **"范围"** 面板为空。</span><span class="sxs-lookup"><span data-stu-id="3e036-209">If you don't pause on a line of code, the **Scope** panel is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text=""范围"窗格" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="3e036-211">" **范围"** 窗格</span><span class="sxs-lookup"><span data-stu-id="3e036-211">The **Scope** pane</span></span>  
:::image-end:::  

### <a name="method-2-watch-expressions"></a><span data-ttu-id="3e036-212">方法 2：监视表达式</span><span class="sxs-lookup"><span data-stu-id="3e036-212">Method 2: Watch Expressions</span></span>  

<span data-ttu-id="3e036-213">监视 **表达式** 面板允许你随着时间的推移监视变量的值。</span><span class="sxs-lookup"><span data-stu-id="3e036-213">The **Watch Expressions** panel lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="3e036-214">正如该名称所示， **监视表达式** 不限于变量。</span><span class="sxs-lookup"><span data-stu-id="3e036-214">As the name implies, **Watch Expressions** aren't limited to variables.</span></span>  <span data-ttu-id="3e036-215">你可以将任何有效的 JavaScript 表达式存储在 **监视表达式 中**。</span><span class="sxs-lookup"><span data-stu-id="3e036-215">You may store any valid JavaScript expression in a **Watch Expression**.</span></span>  <span data-ttu-id="3e036-216">立即尝试。</span><span class="sxs-lookup"><span data-stu-id="3e036-216">Try it now.</span></span>  

1.  <span data-ttu-id="3e036-217">选择" **监视"** 面板。</span><span class="sxs-lookup"><span data-stu-id="3e036-217">Choose the **Watch** panel.</span></span>  
1.  <span data-ttu-id="3e036-218">Choose **Add Expression** \ (Add Expression ![ ](../media/add-expression-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="3e036-218">Choose **Add Expression** \(![Add Expression](../media/add-expression-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="3e036-219">键入 `typeof sum`。</span><span class="sxs-lookup"><span data-stu-id="3e036-219">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="3e036-220">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="3e036-220">Select `Enter`.</span></span>  <span data-ttu-id="3e036-221">DevTools 显示 `typeof sum: "string"` 。</span><span class="sxs-lookup"><span data-stu-id="3e036-221">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="3e036-222">冒号右边的值是监视表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="3e036-222">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="3e036-223">在" **监视表达式** "窗格 \ (右) \下图中，将显示 `typeof sum` 监视表达式。</span><span class="sxs-lookup"><span data-stu-id="3e036-223">In the **Watch Expression** pane \(bottom-right\) in the following figure, the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="3e036-224">如果 DevTools 窗口很大，则" **监视表达式** "窗格位于"事件侦听器断点"窗格 **的** 右侧。</span><span class="sxs-lookup"><span data-stu-id="3e036-224">If your DevTools window is large, the **Watch Expression** pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="监视表达式面板" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="3e036-226">监视 **表达式** 面板</span><span class="sxs-lookup"><span data-stu-id="3e036-226">The **Watch Expression** panel</span></span>  
:::image-end:::  

<span data-ttu-id="3e036-227">如所怀疑的，当应为数字时，将作为字符串 `sum` 进行评估。</span><span class="sxs-lookup"><span data-stu-id="3e036-227">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="3e036-228">现在确认值类型是 Bug 的原因。</span><span class="sxs-lookup"><span data-stu-id="3e036-228">You now confirmed value type is the cause of the bug.</span></span>  

### <a name="method-3-the-console"></a><span data-ttu-id="3e036-229">方法 3：控制台</span><span class="sxs-lookup"><span data-stu-id="3e036-229">Method 3: The Console</span></span>  

<span data-ttu-id="3e036-230">控制台 **允许你** 查看 `console.log()` 消息，还可以使用它来评估任意 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="3e036-230">The **Console** allows you to view `console.log()` messages and you may also use it to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="3e036-231">对于调试，可以使用 **控制台** 测试潜在 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="3e036-231">For debugging, you may use the **Console** to test potential fixes for bugs.</span></span>  <span data-ttu-id="3e036-232">立即尝试。</span><span class="sxs-lookup"><span data-stu-id="3e036-232">Try it now.</span></span>  

1.  <span data-ttu-id="3e036-233">如果 **控制台工具** 已关闭，请选择 `Escape` 将其打开。</span><span class="sxs-lookup"><span data-stu-id="3e036-233">If the **Console** tool is closed, select `Escape` to open it.</span></span>  <span data-ttu-id="3e036-234">控制台 **工具** 将在 DevTools 窗口的下面板中打开。</span><span class="sxs-lookup"><span data-stu-id="3e036-234">The **Console** tool opens in the lower panel of the DevTools window.</span></span>  
1.  <span data-ttu-id="3e036-235">在控制台 **中**，键入 `parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="3e036-235">In the **Console**, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="3e036-236">该工具的语句暂停在代码行上，其中 和 `addend1` `addend2` 位于范围内。</span><span class="sxs-lookup"><span data-stu-id="3e036-236">The statement the tool is paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="3e036-237">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="3e036-237">Select `Enter`.</span></span>  <span data-ttu-id="3e036-238">DevTools 评估语句并打印 `6` ，这是预期演示生成的结果。</span><span class="sxs-lookup"><span data-stu-id="3e036-238">DevTools evaluates the statement and prints `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="控制台工具，在评估 parseInt (addend1) + parseInt (addend2) " lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="3e036-240">评估 **后的** 控制台工具</span><span class="sxs-lookup"><span data-stu-id="3e036-240">The **Console** tool, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <a name="step-7-apply-a-fix"></a><span data-ttu-id="3e036-241">步骤 7：应用修补程序</span><span class="sxs-lookup"><span data-stu-id="3e036-241">Step 7: Apply a fix</span></span>  

<span data-ttu-id="3e036-242">如果你找到该 Bug 的修复程序，请通过编辑代码并重新运行演示来尝试修复。</span><span class="sxs-lookup"><span data-stu-id="3e036-242">If you find a fix for the bug, try out your fix by editing the code and rerunning the demo.</span></span>  <span data-ttu-id="3e036-243">你可以直接在 DevTools UI 中编辑 JavaScript 代码并应用修复程序。</span><span class="sxs-lookup"><span data-stu-id="3e036-243">You may edit JavaScript code directly within the DevTools UI and apply the fix.</span></span>  <span data-ttu-id="3e036-244">立即尝试。</span><span class="sxs-lookup"><span data-stu-id="3e036-244">Try it now.</span></span>  

1.  <span data-ttu-id="3e036-245">Choose **Resume script execution** \ (Resume script execution ![ ](../media/resume-script-run-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="3e036-245">Choose **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="3e036-246">在代码 **编辑器中**，将 第 32 行 `var sum = addend1 + addend2` 替换为 `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="3e036-246">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="3e036-247">选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="3e036-247">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="3e036-248">Choose **Deactivate breakpoints** \ (![ Deactivate breakpoints ](../media/deactivate-breakpoints-button-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="3e036-248">Choose **Deactivate breakpoints** \(![Deactivate breakpoints](../media/deactivate-breakpoints-button-icon.msft.png)\).</span></span>  <span data-ttu-id="3e036-249">它将更改蓝色，以指示选项处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3e036-249">It changes blue to indicate the option is active.</span></span>  <span data-ttu-id="3e036-250">设置 **Deactivate 断点** 时，DevTools 将忽略你设置的任何断点。</span><span class="sxs-lookup"><span data-stu-id="3e036-250">While **Deactivate breakpoints** is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="3e036-251">尝试使用不同值的演示。</span><span class="sxs-lookup"><span data-stu-id="3e036-251">Try out the demo with different values.</span></span>  <span data-ttu-id="3e036-252">演示现在计算正确。</span><span class="sxs-lookup"><span data-stu-id="3e036-252">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="3e036-253">此工作流仅对浏览器中运行的代码应用修补程序。</span><span class="sxs-lookup"><span data-stu-id="3e036-253">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="3e036-254">它不会修复访问网页的所有用户的代码。</span><span class="sxs-lookup"><span data-stu-id="3e036-254">It does not fix the code for all users that visit your webpage.</span></span>  <span data-ttu-id="3e036-255">为此，需要修复服务器上的代码。</span><span class="sxs-lookup"><span data-stu-id="3e036-255">To do that, you need to fix the code that is on your servers.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="3e036-256">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3e036-256">Next steps</span></span>  

<span data-ttu-id="3e036-257">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="3e036-257">Congratulations!</span></span>  <span data-ttu-id="3e036-258">现在，你已了解如何在调试 JavaScript 时充分利用 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="3e036-258">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="3e036-259">本文中学习的工具和方法可以为您节省很多时间。</span><span class="sxs-lookup"><span data-stu-id="3e036-259">The tools and methods you learned in this article may save you countless hours.</span></span>  

<span data-ttu-id="3e036-260">本文仅教您设置断点两种方法。</span><span class="sxs-lookup"><span data-stu-id="3e036-260">This article only taught you two ways to set breakpoints.</span></span>  <span data-ttu-id="3e036-261">DevTools 提供了许多其他方法，包括以下设置。</span><span class="sxs-lookup"><span data-stu-id="3e036-261">DevTools offers many other ways including the following settings.</span></span>  

*   <span data-ttu-id="3e036-262">仅在您提供的条件为 true 时触发的条件断点。</span><span class="sxs-lookup"><span data-stu-id="3e036-262">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="3e036-263">捕获或不捕获的异常的断点。</span><span class="sxs-lookup"><span data-stu-id="3e036-263">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="3e036-264">请求的 URL 与提供的子字符串匹配时触发的 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="3e036-264">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="3e036-265">有关何时以及如何使用每种类型的信息，请导航到"使用断点[暂停代码"。][DevtoolsJavscriptBreakpoints]</span><span class="sxs-lookup"><span data-stu-id="3e036-265">For more information about when and how to use each type, navigate to [Pause Your Code With Breakpoints][DevtoolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="3e036-266">本文不介绍几个代码单步执行控件。</span><span class="sxs-lookup"><span data-stu-id="3e036-266">A couple of code stepping controls aren't explained in this article.</span></span>  <span data-ttu-id="3e036-267">有关详细信息，请导航到"[逐行代码"。][DevtoolsJavascriptReferenceStepThroughCode]</span><span class="sxs-lookup"><span data-stu-id="3e036-267">For more information, navigate to [Step over line of code][DevtoolsJavascriptReferenceStepThroughCode].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3e036-268">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="3e036-268">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools |Microsoft Docs"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "分步执行代码 - JavaScript 调试|Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示|小故障"  

> [!NOTE]
> <span data-ttu-id="3e036-272">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3e036-272">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3e036-273">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="3e036-273">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3e036-275">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3e036-275">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
