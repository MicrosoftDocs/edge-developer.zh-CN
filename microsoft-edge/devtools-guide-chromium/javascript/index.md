---
description: 了解如何使用 Microsoft Edge 开发工具查找并修复 JavaScript bug。
title: 在 Microsoft Edge DevTools 中调试 JavaScript 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: a60bd0c734df18ba7424cde6a828abbd9e7135a9
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519371"
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
# <a name="get-started-with-debugging-javascript-in-microsoft-edge-devtools"></a><span data-ttu-id="69302-104">在 Microsoft Edge DevTools 中调试 JavaScript 入门</span><span class="sxs-lookup"><span data-stu-id="69302-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="69302-105">本文指导你如何在开发工具中调试 JavaScript 问题的基本工作流程。</span><span class="sxs-lookup"><span data-stu-id="69302-105">This article teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <a name="step-1-reproduce-the-bug"></a><span data-ttu-id="69302-106">步骤 1：重现 Bug</span><span class="sxs-lookup"><span data-stu-id="69302-106">Step 1: Reproduce the bug</span></span>  

<span data-ttu-id="69302-107">查找一系列持续重现 Bug 的操作始终是调试的第一步。</span><span class="sxs-lookup"><span data-stu-id="69302-107">Finding a series of actions that consistently reproduce a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="69302-108">选择以下"**打开演示**"链接，然后打开新选项卡中的网页。 若要打开新选项卡中的演示，请选择并按住 `Ctrl` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择"打开演示 **"。**</span><span class="sxs-lookup"><span data-stu-id="69302-108">Choose the following **Open Demo** link and open the webpage in a new tab.  To open the demo in a new tab, select and hold `Ctrl` \(Windows, Linux\) or `Command` \(macOS\), and then choose **Open Demo**.</span></span>  
    
    [<span data-ttu-id="69302-109">打开演示</span><span class="sxs-lookup"><span data-stu-id="69302-109">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="69302-110">在“\*\*数字 1 \*\*”文本框中输入 `5`。</span><span class="sxs-lookup"><span data-stu-id="69302-110">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="69302-111">在“\*\*数字 2 \*\*”文本框中输入 `1`。</span><span class="sxs-lookup"><span data-stu-id="69302-111">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="69302-112">选择“**添加数字 1 和数字 2**”。</span><span class="sxs-lookup"><span data-stu-id="69302-112">Choose **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="69302-113">按钮下方的标签显示 `5 + 1 = 51`。</span><span class="sxs-lookup"><span data-stu-id="69302-113">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="69302-114">结果应为 `6`。</span><span class="sxs-lookup"><span data-stu-id="69302-114">The result should be `6`.</span></span>  <span data-ttu-id="69302-115">接下来，修复作为 bug 的加法错误。</span><span class="sxs-lookup"><span data-stu-id="69302-115">Next, fix the addition error that is the bug.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果为 51，但应为 6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` <span data-ttu-id="69302-117">结果为 `51` ，但应为</span><span class="sxs-lookup"><span data-stu-id="69302-117">results in `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <a name="step-2-get-familiar-with-the-sources-tool-ui"></a><span data-ttu-id="69302-118">步骤 2：熟悉源工具 UI</span><span class="sxs-lookup"><span data-stu-id="69302-118">Step 2: Get familiar with the Sources tool UI</span></span>  

<span data-ttu-id="69302-119">开发工具为不同的任务提供了许多工具。</span><span class="sxs-lookup"><span data-stu-id="69302-119">DevTools provides many different tools for different tasks.</span></span>  <span data-ttu-id="69302-120">不同的任务包括更改 CSS、分析页面加载性能以及监视网络请求。</span><span class="sxs-lookup"><span data-stu-id="69302-120">Different tasks include changing CSS, profiling page-load performance, and monitoring network requests.</span></span>  <span data-ttu-id="69302-121">**源**工具是调试 JavaScript 的地方。</span><span class="sxs-lookup"><span data-stu-id="69302-121">The **Sources** tool is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="69302-122">如果要在开发工具中打开**控制台**工具，选择 `Control`+`Shift`+`J` \(Windows, Linux\) 或 `Command`+`Option`+`J` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="69302-122">To open the **Console** tool in DevTools, select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="控制台工具" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="69302-124">**控制台**工具</span><span class="sxs-lookup"><span data-stu-id="69302-124">The **Console** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="69302-125">选择“**源**”工具。</span><span class="sxs-lookup"><span data-stu-id="69302-125">Choose the **Sources** tool.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="源工具" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="69302-127">**源**工具</span><span class="sxs-lookup"><span data-stu-id="69302-127">The **Sources** tool</span></span>  
    :::image-end:::  
    
<span data-ttu-id="69302-128">**源**工具 UI 有三个部分。</span><span class="sxs-lookup"><span data-stu-id="69302-128">The **Sources** tool UI has three parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="源工具 UI 的 3 个部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="69302-130">**源**工具 UI 的 3 个部分</span><span class="sxs-lookup"><span data-stu-id="69302-130">The 3 parts of the **Sources** tool UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="69302-131">上 **图中导航器** 窗格 \ (第 1 部分) 。</span><span class="sxs-lookup"><span data-stu-id="69302-131">The **Navigator** pane \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="69302-132">此处列出了网页请求的所有文件。</span><span class="sxs-lookup"><span data-stu-id="69302-132">Every file that the webpage requests is listed here.</span></span>  
1.  <span data-ttu-id="69302-133">" **编辑器** "窗格 \ (上图第 2 部分) 。</span><span class="sxs-lookup"><span data-stu-id="69302-133">The **Editor** pane \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="69302-134">在导航器窗格中选择文件 **后** ，此窗格将显示该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="69302-134">After you choose a file in the **Navigator** pane, this pane displays the contents of the file.</span></span>  
1.  <span data-ttu-id="69302-135">调试 **器窗格** \ (图\第 3 部分) 。</span><span class="sxs-lookup"><span data-stu-id="69302-135">The **Debugger** pane \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="69302-136">此窗格提供用于检查网页的 JavaScript 的工具。</span><span class="sxs-lookup"><span data-stu-id="69302-136">This pane provides tools for inspecting the JavaScript for the webpage.</span></span>  <span data-ttu-id="69302-137">如果 DevTools 窗口很宽，则此窗格显示在"编辑器"窗格 **的右侧** 。</span><span class="sxs-lookup"><span data-stu-id="69302-137">If your DevTools window is wide, this pane is displayed to the right of the **Editor** pane.</span></span>  
    
## <a name="step-3-pause-the-code-with-a-breakpoint"></a><span data-ttu-id="69302-138">步骤 3：使用断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="69302-138">Step 3: Pause the code with a breakpoint</span></span>  

<span data-ttu-id="69302-139">调试此类问题的常见方法是在代码中插入多个 `console.log()` 语句，然后在脚本运行时检查值。</span><span class="sxs-lookup"><span data-stu-id="69302-139">A common method for debugging this type of problem is to insert several `console.log()` statements into the code and then to inspect values as the script runs.</span></span>  <span data-ttu-id="69302-140">例如：</span><span class="sxs-lookup"><span data-stu-id="69302-140">For example:</span></span>  

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

<span data-ttu-id="69302-141">`console.log()` 方法可​​以完成工作，但是**断点**可以更快地完成工作。</span><span class="sxs-lookup"><span data-stu-id="69302-141">The `console.log()` method may get the job done, but **breakpoints** get it done faster.</span></span>  <span data-ttu-id="69302-142">断点允许在运行时中间暂停代码，并检查此时的所有值。</span><span class="sxs-lookup"><span data-stu-id="69302-142">A breakpoint allows you to pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="69302-143">与`console.log()`方法相比，断点具有以下优点。</span><span class="sxs-lookup"><span data-stu-id="69302-143">Breakpoints have the following advantages over the `console.log()` method.</span></span>  

*   <span data-ttu-id="69302-144">使用 `console.log()`，需要手动打开源代码，找到相关代码，插入 `console.log()` 语句，然后刷新网页以在**控制台**中显示消息。</span><span class="sxs-lookup"><span data-stu-id="69302-144">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then refresh the webpage to display the messages in the **Console**.</span></span>  <span data-ttu-id="69302-145">使用断点，可能会暂停相关代码，甚至不知道代码的结构。</span><span class="sxs-lookup"><span data-stu-id="69302-145">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="69302-146">在 `console.log()` 语句中，需要显式指定要检查的每个值。</span><span class="sxs-lookup"><span data-stu-id="69302-146">In your `console.log()` statements, you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="69302-147">通过断点，开发工具会及时显示所有变量的值。</span><span class="sxs-lookup"><span data-stu-id="69302-147">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="69302-148">有时，影响代码的变量被隐藏和混淆。</span><span class="sxs-lookup"><span data-stu-id="69302-148">Sometimes variables that affect your code are hidden and obfuscated.</span></span>  
    
<span data-ttu-id="69302-149">简而言之，断点可以比 `console.log()` 方法更快地查找和修复错误。</span><span class="sxs-lookup"><span data-stu-id="69302-149">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="69302-150">如果退后一步，想一想应用程序的工作方式，可能会做出有根据的猜测，即在与**添加数字 1 和数字 2**按钮相关联的 `click`事件侦听器中计算出错误的总和 \(`5 + 1 = 51`\)。</span><span class="sxs-lookup"><span data-stu-id="69302-150">If you step back and think about how the app works, you may make an educated guess that the incorrect sum \(`5 + 1 = 51`\) is computed in the `click` event listener associated with the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="69302-151">因此，可能想在 `click` 侦听器运行期间暂停代码。</span><span class="sxs-lookup"><span data-stu-id="69302-151">So, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="69302-152">**事件侦听器断点**可以完全实现此要求：</span><span class="sxs-lookup"><span data-stu-id="69302-152">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="69302-153">在调试 **器窗格中** ，选择 **"事件侦听器断点"** 以展开部分。</span><span class="sxs-lookup"><span data-stu-id="69302-153">In the **Debugger** pane, choose **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="69302-154">开发工具显示可展开事件类别的列表，如**动画**和**剪贴板**。</span><span class="sxs-lookup"><span data-stu-id="69302-154">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="69302-155">在**鼠标**事件类别旁，选择“**展开**” \(![展开图标](../media/expand-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="69302-155">Next to the **Mouse** event category, choose **Expand** \(![Expand icon](../media/expand-icon.msft.png)\).</span></span>  <span data-ttu-id="69302-156">开发工具显示鼠标事件的列表，如**单击**和**鼠标按下**。</span><span class="sxs-lookup"><span data-stu-id="69302-156">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="69302-157">每个事件旁边都有一个复选框。</span><span class="sxs-lookup"><span data-stu-id="69302-157">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="69302-158">选中“**单击**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="69302-158">Choose the checkbox next to **click**.</span></span>  <span data-ttu-id="69302-159">现在开发工具设置为在运行任何 `click` 事件侦听器时自动暂停。</span><span class="sxs-lookup"><span data-stu-id="69302-159">DevTools is now set up to automatically pause when any `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="选中“单击”旁边的复选框" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="69302-161">选中“**单击**”旁边的复选框</span><span class="sxs-lookup"><span data-stu-id="69302-161">Choose the checkbox next to **click**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="69302-162">返回到演示，再次选择“**添加数字 1 和"数字 2**”。</span><span class="sxs-lookup"><span data-stu-id="69302-162">Back on the demo, choose **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="69302-163">开发工具暂停演示并在“**源**”具中突出显示一行代码。</span><span class="sxs-lookup"><span data-stu-id="69302-163">DevTools pauses the demo and highlights a line of code in the **Sources** tool.</span></span>  <span data-ttu-id="69302-164">开发工具应该暂停在 `get-started.js` 中的第 16 行。</span><span class="sxs-lookup"><span data-stu-id="69302-164">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="69302-165">如果在其他代码上暂停，请选择“**继续执行脚本**” \(![继续执行脚本](../media/resume-script-run-icon.msft.png)\)，直到在正确的行上暂停。</span><span class="sxs-lookup"><span data-stu-id="69302-165">If you pause on a different line of code, choose **Resume Script Execution** \(![Resume Script Execution](../media/resume-script-run-icon.msft.png)\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="69302-166">如果在另一行暂停，则将拥有一个浏览器扩展，此扩展会在你访问的每个网页上注册一个 `click` 事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="69302-166">If you paused on a different line, you have a browser extension that registers a `click` event listener on every webpage that you visit.</span></span>  <span data-ttu-id="69302-167">你已在扩展的 `click` 侦听器中暂停。</span><span class="sxs-lookup"><span data-stu-id="69302-167">You are paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="69302-168">如果使用 InPrivate 模式以**在专用模式中浏览**，这会禁用所有扩展，可能会看到每次在指定的代码行上暂停。</span><span class="sxs-lookup"><span data-stu-id="69302-168">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="69302-169">**事件侦听器断点**只是开发工具中提供的许多类型的断点之一。</span><span class="sxs-lookup"><span data-stu-id="69302-169">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="69302-170">记住所有不同的类型，以帮助你尽快调试不同的方案。</span><span class="sxs-lookup"><span data-stu-id="69302-170">Memorize all the different types to help you debug different scenarios as quickly as possible.</span></span>  <!--  To learn when and how to use each type, navigate to [Pause your code with breakpoints][JSBreakpoints].  -->  

## <a name="step-4-step-through-the-code"></a><span data-ttu-id="69302-171">步骤 4：单步执行代码</span><span class="sxs-lookup"><span data-stu-id="69302-171">Step 4: Step through the code</span></span>  

<span data-ttu-id="69302-172">Bug 的一个常见原因是脚本以错误的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="69302-172">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="69302-173">单步执行代码允许你演练代码的运行时。</span><span class="sxs-lookup"><span data-stu-id="69302-173">Stepping through your code allows you to walk through the runtime of your code.</span></span>  <span data-ttu-id="69302-174">一次浏览一行，以准确确定代码的位置以与不同的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="69302-174">You walk through one line at a time to help you figure out exactly where your code is running in a different order than you expect.</span></span>  <span data-ttu-id="69302-175">立即尝试：</span><span class="sxs-lookup"><span data-stu-id="69302-175">Try it now:</span></span>  

1.  <span data-ttu-id="69302-176">选择“**单步跳过下一函数调用**” \(![单步跳过下一函数调用](../media/step-over-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="69302-176">Choose **Step over next function call** \(![Step over next function call](../media/step-over-icon.msft.png)\).</span></span>  <span data-ttu-id="69302-177">DevTools 无需步入即可运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="69302-177">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="69302-178">开发工具跳过几行代码。</span><span class="sxs-lookup"><span data-stu-id="69302-178">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="69302-179">这是因为 `inputsAreEmpty()` 的计算结果为 false，因此 `if` 语句的代码块不会运行。</span><span class="sxs-lookup"><span data-stu-id="69302-179">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="69302-180">在开发工具的“\*\* 源**”工具上，选择”**单步执行下一函数调用\*\*” \(![单步执行下一函数调用](../media/step-into-icon.msft.png)\) 以逐步运行 `updateLabel()` 函数，一次一行。</span><span class="sxs-lookup"><span data-stu-id="69302-180">On the **Sources** tool of DevTools, choose **Step into next function call** \(![Step into next function call](../media/step-into-icon.msft.png)\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="69302-181">一次查看一行是单步执行代码的基本概念。</span><span class="sxs-lookup"><span data-stu-id="69302-181">Reviewing one line at a time is the basic idea of stepping through code.</span></span>  <span data-ttu-id="69302-182">如果查看 `get-started.js` 中的代码，则该错误可能在 `updateLabel()` 函数中。</span><span class="sxs-lookup"><span data-stu-id="69302-182">If you review the code in `get-started.js`, the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="69302-183">可以使用另一种类型的断点来将代码暂停在错误的可能位置附近，而不是单步执行代码的每一行。</span><span class="sxs-lookup"><span data-stu-id="69302-183">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <a name="step-5-set-a-line-of-code-breakpoint"></a><span data-ttu-id="69302-184">步骤 5：设置代码行断点</span><span class="sxs-lookup"><span data-stu-id="69302-184">Step 5: Set a line-of-code breakpoint</span></span>  

<span data-ttu-id="69302-185">代码行断点是最常见的断点类型。</span><span class="sxs-lookup"><span data-stu-id="69302-185">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="69302-186">到达要暂停的特定代码行时，使用代码行断点。</span><span class="sxs-lookup"><span data-stu-id="69302-186">When you get to the specific line of code you want to pause, use a line-of-code breakpoint.</span></span>  

1.  <span data-ttu-id="69302-187">查看 `updateLabel()` 中的最后一行代码：</span><span class="sxs-lookup"><span data-stu-id="69302-187">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="69302-188">在左侧，此特定代码行的编号显示为 **34**。</span><span class="sxs-lookup"><span data-stu-id="69302-188">On the left, the number of this particular line of code is displayed as **34**.</span></span>  <span data-ttu-id="69302-189">选择第 **34** 行。</span><span class="sxs-lookup"><span data-stu-id="69302-189">Choose line **34**.</span></span>  <span data-ttu-id="69302-190">开发工具在 **34** 的左侧显示一个红色图标。</span><span class="sxs-lookup"><span data-stu-id="69302-190">DevTools displays a red icon to the left of **34**.</span></span>  <span data-ttu-id="69302-191">红色图标表示代码行断点位于此行上。</span><span class="sxs-lookup"><span data-stu-id="69302-191">The red icon indicates that a line-of-code breakpoint is on this line.</span></span>  <span data-ttu-id="69302-192">开发工具始终在运行此代码行之前暂停。</span><span class="sxs-lookup"><span data-stu-id="69302-192">DevTools always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="69302-193">选择“**继续脚本执行**” \(继续脚本执行 ![ ](../media/resume-script-run-icon.msft.png) \)。</span><span class="sxs-lookup"><span data-stu-id="69302-193">Choose **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\).</span></span>  <span data-ttu-id="69302-194">脚本将继续运行，直到到达第 33 行。</span><span class="sxs-lookup"><span data-stu-id="69302-194">The script continues to run until it reaches line 33.</span></span>  <span data-ttu-id="69302-195">在第 31、32 和 33 行上，开发工具在每行的分号右边打印`addend1`、`addend2` 和 `sum` 的值。</span><span class="sxs-lookup"><span data-stu-id="69302-195">On lines 31, 32, and 33, DevTools prints the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="开发工具在第 34 行的代码行断点处暂停" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="69302-197">开发工具在第 34 行的代码行断点处暂停</span><span class="sxs-lookup"><span data-stu-id="69302-197">DevTools pauses on the line-of-code breakpoint on line 34</span></span>  
    :::image-end:::  
    
## <a name="step-6-check-variable-values"></a><span data-ttu-id="69302-198">步骤 6：检查变量值</span><span class="sxs-lookup"><span data-stu-id="69302-198">Step 6: Check variable values</span></span>  

<span data-ttu-id="69302-199">`addend1`、`addend2` 和 `sum` 的值看起来可疑。</span><span class="sxs-lookup"><span data-stu-id="69302-199">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="69302-200">这些值用引号括起来。</span><span class="sxs-lookup"><span data-stu-id="69302-200">The values are wrapped in quotes.</span></span>  <span data-ttu-id="69302-201">引号表示此值是一个字符串，这是解释错误原因的一个很好的假设。</span><span class="sxs-lookup"><span data-stu-id="69302-201">The quotations mean that the value is a string, which is a good hypothesis to explain the cause of the bug.</span></span>  <span data-ttu-id="69302-202">收集有关情况的更多信息。</span><span class="sxs-lookup"><span data-stu-id="69302-202">Gather more information about the situation.</span></span>  <span data-ttu-id="69302-203">开发工具提供了许多用于检查变量值的工具。</span><span class="sxs-lookup"><span data-stu-id="69302-203">DevTools provides many tools for examining variable values.</span></span>  

### <a name="method-1-the-scope-pane"></a><span data-ttu-id="69302-204">方法 1：范围窗格</span><span class="sxs-lookup"><span data-stu-id="69302-204">Method 1: The Scope pane</span></span>  

<span data-ttu-id="69302-205">如果暂停一行代码，"范围"窗格\*\*\*\* 将显示当前定义的本地和全局变量以及每个变量的值。</span><span class="sxs-lookup"><span data-stu-id="69302-205">If you pause on a line of code, the **Scope** pane displays the local and global variables that are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="69302-206">如果适用，它还会显示关闭变量。</span><span class="sxs-lookup"><span data-stu-id="69302-206">It also displays closure variables, as applicable.</span></span>  <span data-ttu-id="69302-207">双击变量值进行编辑。</span><span class="sxs-lookup"><span data-stu-id="69302-207">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="69302-208">如果不在代码行上暂停，则 **"范围"** 窗格为空。</span><span class="sxs-lookup"><span data-stu-id="69302-208">If you don't pause on a line of code, the **Scope** pane is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="范围窗格" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="69302-210">**作用域**窗格</span><span class="sxs-lookup"><span data-stu-id="69302-210">The **Scope** pane</span></span>  
:::image-end:::  

### <a name="method-2-watch-expressions"></a><span data-ttu-id="69302-211">方法 2：监视表达式</span><span class="sxs-lookup"><span data-stu-id="69302-211">Method 2: Watch Expressions</span></span>  

<span data-ttu-id="69302-212">监视 **窗格** 允许您监视变量的值，例如 (或) `sum` 表达式 (如 `typeof sum`) 。</span><span class="sxs-lookup"><span data-stu-id="69302-212">The **Watch** pane allows you to monitor the values of variables (such as `sum`) or expressions (such as `typeof sum`).</span></span>  <span data-ttu-id="69302-213">可以将任何有效的 JavaScript 表达式存储在监视表达式中。</span><span class="sxs-lookup"><span data-stu-id="69302-213">You may store any valid JavaScript expression in a Watch Expression.</span></span>  

1.  <span data-ttu-id="69302-214">选择" **监视"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="69302-214">Choose the **Watch** pane.</span></span>  
1.  <span data-ttu-id="69302-215">Choose **Add watch expression** \ (Add watch expression ![ ](../media/add-expression-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="69302-215">Choose **Add watch expression** \(![Add watch expression](../media/add-expression-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="69302-216">键入 `typeof sum`。</span><span class="sxs-lookup"><span data-stu-id="69302-216">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="69302-217">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="69302-217">Select `Enter`.</span></span>  <span data-ttu-id="69302-218">DevTools 显示 `typeof sum: "string"` 。</span><span class="sxs-lookup"><span data-stu-id="69302-218">DevTools displays `typeof sum: "string"`.</span></span>  <span data-ttu-id="69302-219">冒号右边的值是监视表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="69302-219">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="69302-220">下图中，监视 `typeof sum` 表达式显示在"监视" **窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="69302-220">In the following figure, the `typeof sum` Watch Expression is displayed in the **Watch** pane.</span></span>  <span data-ttu-id="69302-221">如果 DevTools 窗口很宽，\*\*\*\* 则"监视"窗格显示在\*\*\*\* 调试器窗格中，然后显示在右侧。</span><span class="sxs-lookup"><span data-stu-id="69302-221">If your DevTools window is wide, the **Watch** pane is displayed within the **Debugger** pane, which then appears on the right.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="监视窗格" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="69302-223">“**监视**”窗格</span><span class="sxs-lookup"><span data-stu-id="69302-223">The **Watch** pane</span></span>  
:::image-end:::  

<span data-ttu-id="69302-224">正如猜想的那样，如果应为数字， `sum` 被评估为字符串。</span><span class="sxs-lookup"><span data-stu-id="69302-224">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="69302-225">现在确认值类型是 Bug 的原因。</span><span class="sxs-lookup"><span data-stu-id="69302-225">You now confirmed value type is the cause of the bug.</span></span>  

### <a name="method-3-the-console"></a><span data-ttu-id="69302-226">方法 3：控制台</span><span class="sxs-lookup"><span data-stu-id="69302-226">Method 3: The Console</span></span>  

<span data-ttu-id="69302-227">**控制台**允许你查看 `console.log()` 输出。</span><span class="sxs-lookup"><span data-stu-id="69302-227">The **Console** allows you to view `console.log()` output.</span></span>  <span data-ttu-id="69302-228">当调试程序暂停在\*\*\*\* 代码语句上时，您还可以使用控制台评估任意 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="69302-228">You can also use the **Console** to evaluate arbitrary JavaScript statements while the debugger is paused at a code statement.</span></span>  <span data-ttu-id="69302-229">对于调试，可以使用 **控制台** 测试潜在 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="69302-229">For debugging, you can use the **Console** to test potential fixes for bugs.</span></span>

1.  <span data-ttu-id="69302-230">如果**控制台**工具已关闭，请选择 `Esc` 以将其打开。</span><span class="sxs-lookup"><span data-stu-id="69302-230">If the **Console** tool is closed, select `Esc` to open it.</span></span>  <span data-ttu-id="69302-231">控制台 **工具** 将在 DevTools 窗口的下窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="69302-231">The **Console** tool opens in the lower pane of the DevTools window.</span></span>  
1.  <span data-ttu-id="69302-232">在**控制台**中，键入 `parseInt(addend1) + parseInt(addend2)`。</span><span class="sxs-lookup"><span data-stu-id="69302-232">In the **Console**, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="69302-233">工具的语句暂停在作用域为 `addend1` 和 `addend2` 的代码行上。</span><span class="sxs-lookup"><span data-stu-id="69302-233">The statement the tool is paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="69302-234">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="69302-234">Select `Enter`.</span></span>  <span data-ttu-id="69302-235">开发工具将评估该语句并打印 `6`，这是预期演示生成的结果。</span><span class="sxs-lookup"><span data-stu-id="69302-235">DevTools evaluates the statement and prints `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="评估 parseInt (addend1) + parseInt (addend2) 后的控制台工具" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="69302-237">评估后的**控制台**工具</span><span class="sxs-lookup"><span data-stu-id="69302-237">The **Console** tool, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <a name="step-7-apply-a-fix"></a><span data-ttu-id="69302-238">步骤 7：应用修补程序</span><span class="sxs-lookup"><span data-stu-id="69302-238">Step 7: Apply a fix</span></span>  

<span data-ttu-id="69302-239">我们已确定该 Bug 的可能修复方法。</span><span class="sxs-lookup"><span data-stu-id="69302-239">We've identified a possible fix for the bug.</span></span>  <span data-ttu-id="69302-240">接下来，直接在 DevTools UI 中编辑 JavaScript 代码，然后重新运行演示以测试修复，如下所示。</span><span class="sxs-lookup"><span data-stu-id="69302-240">Next, edit the JavaScript code directly within the DevTools UI and then rerun the demo to test the fix, as follows.</span></span>

1.  <span data-ttu-id="69302-241">选择“**继续脚本执行**” \(继续脚本执行 ![ ](../media/resume-script-run-icon.msft.png) \)。</span><span class="sxs-lookup"><span data-stu-id="69302-241">Choose **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="69302-242">在" **编辑器"** 窗格中，将行替换为 `var sum = addend1 + addend2` `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="69302-242">In the **Editor** pane, replace the line `var sum = addend1 + addend2` with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="69302-243">选择 `Control`+`S` \(Windows、Linux\) 或 `Command`+`S` \(macOS\) 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="69302-243">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="69302-244">选择“**停用断点**” \(![停用断点](../media/deactivate-breakpoints-button-icon.msft.png) \)。</span><span class="sxs-lookup"><span data-stu-id="69302-244">Choose **Deactivate breakpoints** \(![Deactivate breakpoints](../media/deactivate-breakpoints-button-icon.msft.png)\).</span></span>  <span data-ttu-id="69302-245">它将更改蓝色，以指示选项处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="69302-245">It changes blue to indicate the option is active.</span></span>  <span data-ttu-id="69302-246">设置“**停用断点**”时，开发工具会忽略你设置的任何断点。</span><span class="sxs-lookup"><span data-stu-id="69302-246">While **Deactivate breakpoints** is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="69302-247">尝试使用具有不同值的演示。</span><span class="sxs-lookup"><span data-stu-id="69302-247">Try out the demo with different values.</span></span>  <span data-ttu-id="69302-248">演示现在计算正确。</span><span class="sxs-lookup"><span data-stu-id="69302-248">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="69302-249">此工作流仅对从服务器发送的代码的本地副本应用修补程序。</span><span class="sxs-lookup"><span data-stu-id="69302-249">This workflow only applies a fix to a local copy of the code sent from the server.</span></span>  <span data-ttu-id="69302-250">调试项目时，确定修补程序后，你仍然需要将修复应用到服务器上代码，例如编辑本地源代码，然后将固定代码重新部署到服务器。</span><span class="sxs-lookup"><span data-stu-id="69302-250">When debugging your project, after you identify the fix, you still need to apply that fix to the code on the server, such as by editing your local source code and then re-deploying your fixed code to the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69302-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69302-251">Next steps</span></span>  

<span data-ttu-id="69302-252">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="69302-252">Congratulations!</span></span>  <span data-ttu-id="69302-253">现在，你已了解如何在调试 JavaScript 时充分利用 Microsoft Edge 开发工具。</span><span class="sxs-lookup"><span data-stu-id="69302-253">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="69302-254">本文中学习的工具和方法可以为你节省很多时间。</span><span class="sxs-lookup"><span data-stu-id="69302-254">The tools and methods you learned in this article may save you countless hours.</span></span>  

<span data-ttu-id="69302-255">本文介绍了两种设置断点的方法。</span><span class="sxs-lookup"><span data-stu-id="69302-255">This article showed two ways to set breakpoints.</span></span>  <span data-ttu-id="69302-256">DevTools 还提供了在满足某些条件时设置断点以暂停代码的方法，例如：</span><span class="sxs-lookup"><span data-stu-id="69302-256">DevTools also provides ways to set breakpoints to pause your code when certain conditions are met, such as:</span></span>

*   <span data-ttu-id="69302-257">仅在提供的条件为 true 时触发的条件断点。</span><span class="sxs-lookup"><span data-stu-id="69302-257">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="69302-258">已捕获或未捕获异常的断点。</span><span class="sxs-lookup"><span data-stu-id="69302-258">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="69302-259">请求的 URL 与提供的子字符串匹配时触发的 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="69302-259">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="69302-260">有关何时以及如何使用每种类型的信息，请导航到"使用断点[暂停代码"。][DevToolsJavscriptBreakpoints]</span><span class="sxs-lookup"><span data-stu-id="69302-260">For more information about when and how to use each type, navigate to [Pause your code with breakpoints][DevToolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="69302-261">本文不介绍几个代码单步执行控件。</span><span class="sxs-lookup"><span data-stu-id="69302-261">A couple of code stepping controls aren't explained in this article.</span></span>  <span data-ttu-id="69302-262">有关详细信息，请导航到"使用 [调试器][DevToolsJavascriptReferenceStepThroughCode] 功能"文章中的逐行代码。</span><span class="sxs-lookup"><span data-stu-id="69302-262">For more information, navigate to [Step over line of code][DevToolsJavascriptReferenceStepThroughCode] in the "Use the debugger features" article.</span></span>

### <a name="see-also"></a><span data-ttu-id="69302-263">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69302-263">See also</span></span>

*   <span data-ttu-id="69302-264">[使用调试器功能][DevToolsJavascriptReference] - 使用"源"工具中的调试器 UI。</span><span class="sxs-lookup"><span data-stu-id="69302-264">[Use the debugger features][DevToolsJavascriptReference] - Using the UI of the debugger in the Sources tool.</span></span>
*   <span data-ttu-id="69302-265">[源工具概述][DevToolsSourcesIndex] - 介绍 JavaScript 调试工具和代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="69302-265">[Sources tool overview][DevToolsSourcesIndex] - Introduces the JavaScript debugger and code editor.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="69302-266">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="69302-266">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptReference]: ./reference.md "使用调试器功能|Microsoft Docs"  
[DevToolsSourcesIndex]: ../sources/index.md "源工具概述 | Microsoft Docs"  
[DevToolsJavscriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge 开发工具中使用断点暂停代码 | Microsoft Doc"
[DevToolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "分步执行代码 - 使用调试器|Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示 | 故障"  

> [!NOTE]
> <span data-ttu-id="69302-272">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="69302-272">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="69302-273">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="69302-273">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="69302-275">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="69302-275">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
