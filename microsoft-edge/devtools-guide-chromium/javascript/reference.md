---
description: 了解 Microsoft Edge DevTools 调试功能的此全面参考中的新调试工作流。
title: JavaScript 调试引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f11dfb52e97dcec20d1e6c4f3adeee7010857a33
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993420"
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

# <span data-ttu-id="22fec-104">JavaScript febugging 参考</span><span class="sxs-lookup"><span data-stu-id="22fec-104">JavaScript febugging reference</span></span>  

<span data-ttu-id="22fec-105">通过以下完整的 Microsoft Edge DevTools 调试功能参考发现新的调试工作流。</span><span class="sxs-lookup"><span data-stu-id="22fec-105">Discover new debugging workflows with the following comprehensive reference of Microsoft Edge DevTools debugging features.</span></span>  

<span data-ttu-id="22fec-106">有关调试的基础知识，请参阅 [开始在 Microsoft Edge DevTools 中调试 JavaScript][DevToolsJavascriptGetStarted] 。</span><span class="sxs-lookup"><span data-stu-id="22fec-106">See [Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] to learn the basics of debugging.</span></span>  

## <span data-ttu-id="22fec-107">暂停带断点的代码</span><span class="sxs-lookup"><span data-stu-id="22fec-107">Pause code with breakpoints</span></span>  

<span data-ttu-id="22fec-108">设置断点，以便你可以在运行时的中间暂停代码。</span><span class="sxs-lookup"><span data-stu-id="22fec-108">Set a breakpoint so that you are able to pause your code in the middle of the runtime.</span></span>  

<span data-ttu-id="22fec-109">请参阅 [暂停带断点的代码][DevToolsJavascriptBreakpoints] ，了解如何设置断点。</span><span class="sxs-lookup"><span data-stu-id="22fec-109">See [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints] to learn how to set breakpoints.</span></span>  

## <span data-ttu-id="22fec-110">逐句通过代码</span><span class="sxs-lookup"><span data-stu-id="22fec-110">Step through code</span></span>  

<span data-ttu-id="22fec-111">代码暂停后，逐个遍历它，一次一行，以调查控制流和属性值的方式。</span><span class="sxs-lookup"><span data-stu-id="22fec-111">Once your code is paused, step through it, one line at a time, investigating control flow and property values along the way.</span></span>  

### <span data-ttu-id="22fec-112">跳过代码行</span><span class="sxs-lookup"><span data-stu-id="22fec-112">Step over line of code</span></span>  

<span data-ttu-id="22fec-113">当在包含与你调试的问题不相关的函数的代码行上暂停时，请单击 " **步骤超过** \ (![ ][ImageStepOverIcon] \ ) " 按钮以运行该函数，而无需单步执行该函数。</span><span class="sxs-lookup"><span data-stu-id="22fec-113">When paused on a line of code containing a function that is not relevant to the problem you are debugging, click the **Step over** \(![Step over][ImageStepOverIcon]\) button to run the function without stepping into it.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="选择 "逐步骤"" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   <span data-ttu-id="22fec-115">选择 "**逐步骤**"</span><span class="sxs-lookup"><span data-stu-id="22fec-115">Select **Step over**</span></span>  
:::image-end:::  

<span data-ttu-id="22fec-116">例如，假设你正在调试以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="22fec-116">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name); // D
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name; // C
}
```  

<span data-ttu-id="22fec-117">您已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-117">You are paused on `A`.</span></span>  <span data-ttu-id="22fec-118">通过按 " **逐步骤**"，DevTools 将运行你正在执行的函数中的所有代码，即 `B` 和 `C` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-118">By pressing **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="22fec-119">DevTools 然后暂停 `D` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-119">DevTools then pauses on `D`.</span></span>  

### <span data-ttu-id="22fec-120">单步执行代码行</span><span class="sxs-lookup"><span data-stu-id="22fec-120">Step into line of code</span></span>  

<span data-ttu-id="22fec-121">当暂停包含与你正在调试的问题相关的函数调用的代码行时，请单击 **步骤** " (单步执行" ![ ) " ][ImageStepIntoIcon] 按钮，以进一步调查该功能。</span><span class="sxs-lookup"><span data-stu-id="22fec-121">When paused on a line of code containing a function call that is related to the problem you are debugging, click the **Step into** \(![Step into][ImageStepIntoIcon]\) button to investigate that function further.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="选择单步执行" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   <span data-ttu-id="22fec-123">选择**单步**执行</span><span class="sxs-lookup"><span data-stu-id="22fec-123">Select **Step into**</span></span>  
:::image-end:::  

<span data-ttu-id="22fec-124">例如，假设你正在调试以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="22fec-124">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name);
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name;
}
```  

<span data-ttu-id="22fec-125">您已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-125">You are paused on `A`.</span></span>  <span data-ttu-id="22fec-126">通过按 " **单步执行**"，DevTools 将运行此行代码，然后暂停 `B` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-126">By pressing **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <span data-ttu-id="22fec-127">跳出代码行</span><span class="sxs-lookup"><span data-stu-id="22fec-127">Step out of line of code</span></span>  

<span data-ttu-id="22fec-128">当在与你调试的问题不相关的函数内暂停时，请单击 " **跳出** " (" ![ 跳出" ][ImageStepOutIcon] ) 按钮以运行函数的其余代码。</span><span class="sxs-lookup"><span data-stu-id="22fec-128">When paused inside of a function that is not related to the problem you are debugging, click the **Step out** \(![Step out][ImageStepOutIcon]\) button to run the rest of the code of the function.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="选择 "跳出"" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   <span data-ttu-id="22fec-130">选择 "**跳出**"</span><span class="sxs-lookup"><span data-stu-id="22fec-130">Select **Step out**</span></span>  
:::image-end:::  

<span data-ttu-id="22fec-131">例如，假设你正在调试以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="22fec-131">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName();
    updateName(name); // C
}
function getName() {
    var name = app.first + ' ' + app.last; // A
    return name; // B
}
```  

<span data-ttu-id="22fec-132">您已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-132">You are paused on `A`.</span></span>  <span data-ttu-id="22fec-133">通过按 " **跳出**"，DevTools 将运行中的其余代码 `getName()` ，这就是在 `B` 此示例中，然后暂停 `C` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-133">By pressing **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <span data-ttu-id="22fec-134">运行到特定行的所有代码</span><span class="sxs-lookup"><span data-stu-id="22fec-134">Run all code up to a specific line</span></span>  

<span data-ttu-id="22fec-135">调试长函数时，可能有许多与你正在调试的问题无关的代码。</span><span class="sxs-lookup"><span data-stu-id="22fec-135">When debugging a long function, there may be a lot of code that is not related to the problem you are debugging.</span></span>  

<span data-ttu-id="22fec-136">你可以选择单步执行所有行，但这是单调乏味的。</span><span class="sxs-lookup"><span data-stu-id="22fec-136">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="22fec-137">你可以选择在感兴趣的行上设置代码行断点，然后单击 " **恢复脚本执行** " (" ![ 恢复脚本执行" ][ImageResumeScriptExecutionIcon] \ ) 按钮，但有更快的方法。</span><span class="sxs-lookup"><span data-stu-id="22fec-137">You may choose to set a line-of-code breakpoint on the line in which you are interested and then click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button, but there is a faster way.</span></span>  

<span data-ttu-id="22fec-138">右键单击您感兴趣的代码行，然后选择 " **继续到此处**"。</span><span class="sxs-lookup"><span data-stu-id="22fec-138">Right-click the line of code in which you are interested, and select **Continue to here**.</span></span>  <span data-ttu-id="22fec-139">DevTools 运行到该点的所有代码，然后在该行上暂停。</span><span class="sxs-lookup"><span data-stu-id="22fec-139">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="选择 "继续到此处"" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   <span data-ttu-id="22fec-141">选择 "**继续到此处**"</span><span class="sxs-lookup"><span data-stu-id="22fec-141">Select **Continue to here**</span></span>  
:::image-end:::  

### <span data-ttu-id="22fec-142">重启调用堆栈的 top 函数</span><span class="sxs-lookup"><span data-stu-id="22fec-142">Restart the top function of the call stack</span></span>  

<span data-ttu-id="22fec-143">在一行代码中暂停时，右键单击 " **调用堆栈** " 窗格中的任意位置，然后选择 " **重新启动帧** " 以在调用堆栈中 top 函数的第一行暂停。</span><span class="sxs-lookup"><span data-stu-id="22fec-143">While paused on a line of code, right-click anywhere in the **Call Stack** pane and select **Restart Frame** to pause on the first line of the top function in your call stack.</span></span>  <span data-ttu-id="22fec-144">Top 函数是最后运行的函数。</span><span class="sxs-lookup"><span data-stu-id="22fec-144">The top function is the last function that was run.</span></span>  

<span data-ttu-id="22fec-145">下面的代码片段是用于执行分步操作的示例。</span><span class="sxs-lookup"><span data-stu-id="22fec-145">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="22fec-146">您已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="22fec-146">You are paused on `A`.</span></span>  <span data-ttu-id="22fec-147">单击 " **重启帧**" 后，你应该暂停在 `B` ，不进行任何设置断点或按 " **恢复脚本执行**"。</span><span class="sxs-lookup"><span data-stu-id="22fec-147">After clicking **Restart Frame**, you should be paused on `B`, without ever setting a breakpoint or pressing **Resume script execution**.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="选择 "重启帧"" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   <span data-ttu-id="22fec-149">选择 "**重启帧**"</span><span class="sxs-lookup"><span data-stu-id="22fec-149">Select **Restart Frame**</span></span>  
:::image-end:::  

### <span data-ttu-id="22fec-150">恢复脚本运行时</span><span class="sxs-lookup"><span data-stu-id="22fec-150">Resume script runtime</span></span>  

<span data-ttu-id="22fec-151">若要在暂停脚本后继续运行时，请单击 " **恢复脚本执行** " (" ![ 恢复脚本执行" ][ImageResumeScriptExecutionIcon] \ ) 按钮。</span><span class="sxs-lookup"><span data-stu-id="22fec-151">To continue the runtime after a pause of your script, click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button.</span></span>  <span data-ttu-id="22fec-152">DevTools 运行脚本，直到出现下一个断点（如果有）。</span><span class="sxs-lookup"><span data-stu-id="22fec-152">DevTools runs the script up until the next breakpoint, if any.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="选择 "恢复脚本执行"" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   <span data-ttu-id="22fec-154">选择 "**恢复脚本执行**"</span><span class="sxs-lookup"><span data-stu-id="22fec-154">Select **Resume script execution**</span></span>  
:::image-end:::  

#### <span data-ttu-id="22fec-155">强制脚本运行时</span><span class="sxs-lookup"><span data-stu-id="22fec-155">Force script runtime</span></span>  

<span data-ttu-id="22fec-156">若要忽略所有断点并强制脚本恢复运行，请单击并按住 " **恢复脚本执行** " (" ![ 恢复脚本执行 \ ][ImageResumeScriptExecutionIcon] ) " 按钮，然后选择 " **强制** 脚本执行" (![ 强制脚本执行 ][ImageForceScriptExecutionIcon] \ ) "按钮。</span><span class="sxs-lookup"><span data-stu-id="22fec-156">To ignore all breakpoints and force your script to resume running, click and hold the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button and then select the **Force script execution** \(![Force script execution][ImageForceScriptExecutionIcon]\) button.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="选择 "强制脚本执行"" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   <span data-ttu-id="22fec-158">选择 "**强制脚本执行**"</span><span class="sxs-lookup"><span data-stu-id="22fec-158">Select **Force script execution**</span></span>  
:::image-end:::  

### <span data-ttu-id="22fec-159">更改线程上下文</span><span class="sxs-lookup"><span data-stu-id="22fec-159">Change thread context</span></span>  

<span data-ttu-id="22fec-160">处理 web 工作人员或服务工作者时，单击 " **线程** " 窗格中列出的上下文以切换到该上下文。</span><span class="sxs-lookup"><span data-stu-id="22fec-160">When working with web workers or service workers, click on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="22fec-161">蓝色箭头图标表示当前选择的上下文。</span><span class="sxs-lookup"><span data-stu-id="22fec-161">The blue arrow icon represents which context is currently selected.</span></span>  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text=""线程" 窗格" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   <span data-ttu-id="22fec-163">" **线程** " 窗格</span><span class="sxs-lookup"><span data-stu-id="22fec-163">The **Threads** pane</span></span>  
:::image-end:::  

<span data-ttu-id="22fec-164">例如，假设你的主脚本和你的服务工作脚本中的断点暂停。</span><span class="sxs-lookup"><span data-stu-id="22fec-164">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="22fec-165">你希望查看服务工作上下文的本地属性和全局属性，但 " **源** " 面板显示的是主脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="22fec-165">You want to view the local and global properties for the service worker context, but the **Sources** panel is showing the main script context.</span></span>  <span data-ttu-id="22fec-166">通过单击 " **线程** " 窗格中的 "服务工作人员" 条目，你应该能够切换到该上下文。</span><span class="sxs-lookup"><span data-stu-id="22fec-166">By clicking on the service worker entry in the **Threads** pane, you should be able to switch to that context.</span></span>  

## <span data-ttu-id="22fec-167">查看和编辑本地、关闭和全局属性</span><span class="sxs-lookup"><span data-stu-id="22fec-167">View and edit local, closure, and global properties</span></span>  

<span data-ttu-id="22fec-168">当在一行代码上暂停时，请使用 " **范围** " 窗格查看和编辑本地、关闭和全局范围中的属性和变量值。</span><span class="sxs-lookup"><span data-stu-id="22fec-168">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="22fec-169">双击属性值进行更改。</span><span class="sxs-lookup"><span data-stu-id="22fec-169">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="22fec-170">不可枚举的属性将呈灰色。</span><span class="sxs-lookup"><span data-stu-id="22fec-170">Non-enumerable properties are greyed out.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text=""范围" 窗格" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   <span data-ttu-id="22fec-172">" **范围** " 窗格</span><span class="sxs-lookup"><span data-stu-id="22fec-172">The **Scope** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="22fec-173">查看当前调用堆栈</span><span class="sxs-lookup"><span data-stu-id="22fec-173">View the current call stack</span></span>  

<span data-ttu-id="22fec-174">当在一行代码上暂停时，请使用 " **调用堆栈** " 窗格查看向您提供此点的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="22fec-174">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="22fec-175">单击某个条目可跳转到调用该函数的代码行。</span><span class="sxs-lookup"><span data-stu-id="22fec-175">Click on an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="22fec-176">蓝色箭头图标表示当前突出显示的函数 DevTools。</span><span class="sxs-lookup"><span data-stu-id="22fec-176">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text=""调用堆栈" 窗格" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   <span data-ttu-id="22fec-178">" **调用堆栈** " 窗格</span><span class="sxs-lookup"><span data-stu-id="22fec-178">The **Call Stack** pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="22fec-179">在代码行上未暂停时，" **调用堆栈** " 窗格为空。</span><span class="sxs-lookup"><span data-stu-id="22fec-179">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <span data-ttu-id="22fec-180">复制堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="22fec-180">Copy stack trace</span></span>  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="22fec-181">右键单击 " **调用堆栈** " 窗格中的任意位置，然后选择 " **复制堆栈跟踪** " 将当前调用堆栈复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="22fec-181">Right-click anywhere in the **Call Stack** pane and select **Copy stack trace** to copy the current call stack to the clipboard.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="选择 "复制堆栈跟踪"" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   <span data-ttu-id="22fec-183">选择 "**复制堆栈跟踪**"</span><span class="sxs-lookup"><span data-stu-id="22fec-183">Select **Copy Stack Trace**</span></span>  
:::image-end:::  

<span data-ttu-id="22fec-184">以下代码片段是输出的示例。</span><span class="sxs-lookup"><span data-stu-id="22fec-184">The following code snippet is an example of the output.</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onClick (get-started.js:15)
```  

## <span data-ttu-id="22fec-185">忽略脚本或脚本模式</span><span class="sxs-lookup"><span data-stu-id="22fec-185">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="22fec-186">当你希望在调试时忽略该脚本时，请将脚本标记为库代码。</span><span class="sxs-lookup"><span data-stu-id="22fec-186">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="22fec-187">当标记为 "库代码" 时，脚本将在 " **调用堆栈** " 窗格中被遮住，当你单步执行你的代码时，将不会单步执行脚本的函数。</span><span class="sxs-lookup"><span data-stu-id="22fec-187">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="22fec-188">下面的代码片段是用于执行分步操作的示例。</span><span class="sxs-lookup"><span data-stu-id="22fec-188">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` <span data-ttu-id="22fec-189">是您信任的第三方库。</span><span class="sxs-lookup"><span data-stu-id="22fec-189">is a third-party library that you trust.</span></span>  <span data-ttu-id="22fec-190">如果您确信所调试的问题与第三方库无关，则将脚本标记为 **库代码**是有意义的。</span><span class="sxs-lookup"><span data-stu-id="22fec-190">If you are confident that the problem you are debugging is not related to the third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

### <span data-ttu-id="22fec-191">将脚本标记为 "编辑器" 窗格中的库代码</span><span class="sxs-lookup"><span data-stu-id="22fec-191">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="22fec-192">完成以下操作以将脚本标记为 "**编辑器**" 窗格中的**库代码**。</span><span class="sxs-lookup"><span data-stu-id="22fec-192">Complete the following actions to mark a script as **Library code** from the **Editor** pane.</span></span>  

1.  <span data-ttu-id="22fec-193">打开文件。</span><span class="sxs-lookup"><span data-stu-id="22fec-193">Open the file.</span></span>  
1.  <span data-ttu-id="22fec-194">右键单击任意位置。</span><span class="sxs-lookup"><span data-stu-id="22fec-194">Right-click anywhere.</span></span>  
1.  <span data-ttu-id="22fec-195">选择 " **标记为库代码**"。</span><span class="sxs-lookup"><span data-stu-id="22fec-195">Select **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="将脚本标记为 "编辑器" 窗格中的库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       <span data-ttu-id="22fec-197">将脚本标记为 "**编辑器**" 窗格中的**库代码**</span><span class="sxs-lookup"><span data-stu-id="22fec-197">Mark a script as **Library code** from the **Editor** pane</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="22fec-198">将脚本标记为 "调用堆栈" 窗格中的库代码</span><span class="sxs-lookup"><span data-stu-id="22fec-198">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="22fec-199">Compelte folliwng 操作将脚本标记为 "**调用堆栈**" 窗格中的**库代码**。</span><span class="sxs-lookup"><span data-stu-id="22fec-199">Compelte the folliwng actions to mark a script as **Library code** from the **Call Stack** pane.</span></span>  

1.  <span data-ttu-id="22fec-200">右键单击脚本中的函数。</span><span class="sxs-lookup"><span data-stu-id="22fec-200">Right-click on a function from the script.</span></span>  
1.  <span data-ttu-id="22fec-201">选择 " **标记为库代码**"。</span><span class="sxs-lookup"><span data-stu-id="22fec-201">Select **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="将脚本标记为 "调用堆栈" 窗格中的库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       <span data-ttu-id="22fec-203">将脚本标记为 "**调用堆栈**" 窗格中的**库代码**</span><span class="sxs-lookup"><span data-stu-id="22fec-203">Mark a script as **Library code** from the **Call Stack** pane</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="22fec-204">将脚本标记为来自设置的库代码</span><span class="sxs-lookup"><span data-stu-id="22fec-204">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="22fec-205">完成以下操作，从 " **设置**" 中标记单个脚本或脚本模式。</span><span class="sxs-lookup"><span data-stu-id="22fec-205">Complete the following actions to mark a single script or pattern of scripts from **Settings**.</span></span>  

1.  <span data-ttu-id="22fec-206">打开 " [设置][DevToolsCustomize]"。</span><span class="sxs-lookup"><span data-stu-id="22fec-206">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="22fec-207">转到 " **库代码** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="22fec-207">Go to the **Library code** tab.</span></span>  
1.  <span data-ttu-id="22fec-208">单击 " **添加图案**"。</span><span class="sxs-lookup"><span data-stu-id="22fec-208">Click **Add pattern**.</span></span>  
1.  <span data-ttu-id="22fec-209">输入脚本名称或要标记为 **库代码**的脚本名称的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="22fec-209">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="22fec-210">单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="22fec-210">Click **Add**.</span></span>  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="将脚本标记为来自设置的库代码" lightbox="../media/javascript-framework-library-code.msft.png":::
       <span data-ttu-id="22fec-212">将脚本标记为来自**设置**的**库代码**</span><span class="sxs-lookup"><span data-stu-id="22fec-212">Mark a script as **Library code** from **Settings**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="22fec-213">从任意页面运行调试代码片段</span><span class="sxs-lookup"><span data-stu-id="22fec-213">Run snippets of debug code from any page</span></span>   

<span data-ttu-id="22fec-214">如果您发现自己在控制台中同时运行相同的调试代码，请考虑代码段。</span><span class="sxs-lookup"><span data-stu-id="22fec-214">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="22fec-215">代码段是你在 DevTools 内创作、存储和运行的运行时脚本。</span><span class="sxs-lookup"><span data-stu-id="22fec-215">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="22fec-216">请参阅 [从任意页面运行代码片段][DevToolsJavascriptSnippets] 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="22fec-216">See [Run Snippets of Code From Any Page][DevToolsJavascriptSnippets] to learn more.</span></span>  

## <span data-ttu-id="22fec-217">监视自定义 JavaScript 表达式的值</span><span class="sxs-lookup"><span data-stu-id="22fec-217">Watch the values of custom JavaScript expressions</span></span>  

<span data-ttu-id="22fec-218">使用 " **监视** " 窗格监视自定义表达式的值。</span><span class="sxs-lookup"><span data-stu-id="22fec-218">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="22fec-219">你可能会注意到任何有效的 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="22fec-219">You may watch any valid JavaScript expression.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text=""监视" 窗格" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   <span data-ttu-id="22fec-221">" **监视** " 窗格</span><span class="sxs-lookup"><span data-stu-id="22fec-221">The **Watch** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="22fec-222">单击 " **添加表达式** \ (![ 添加表达式 ][ImageAddExpressionIcon] \ ) " 按钮以创建新的监视表达式。</span><span class="sxs-lookup"><span data-stu-id="22fec-222">Click the **Add Expression** \(![Add Expression][ImageAddExpressionIcon]\) button to create a new watch expression.</span></span>  
*   <span data-ttu-id="22fec-223">单击 " **刷新** \ (![ refresh ][ImageRefreshIcon] \ ) " 按钮以刷新所有现有表达式的值。</span><span class="sxs-lookup"><span data-stu-id="22fec-223">Click the **Refresh** \(![Refresh][ImageRefreshIcon]\) button to refresh the values of all existing expressions.</span></span>  <span data-ttu-id="22fec-224">逐句通过代码时，值会自动刷新。</span><span class="sxs-lookup"><span data-stu-id="22fec-224">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="22fec-225">将鼠标悬停在某个表达式上，然后单击 " **删除表达式** \ (![ 删除表达式 ][ImageDeleteExpressionIcon] \ ) " 按钮将其删除。</span><span class="sxs-lookup"><span data-stu-id="22fec-225">Hover over an expression and click the **Delete Expression** \(![Delete Expression][ImageDeleteExpressionIcon]\) button to delete it.</span></span>  

## <span data-ttu-id="22fec-226">使 minified 文件易于阅读</span><span class="sxs-lookup"><span data-stu-id="22fec-226">Make a minified file readable</span></span>  

<span data-ttu-id="22fec-227">单击 " **格式** \ (![ 格式 ][ImageFormatIcon] \ ) " 按钮，使 minified 文件易于阅读。</span><span class="sxs-lookup"><span data-stu-id="22fec-227">Click the **Format** \(![Format][ImageFormatIcon]\) button to make a minified file human-readable.</span></span>  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text=""格式" 按钮" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   <span data-ttu-id="22fec-229">" **格式** " 按钮</span><span class="sxs-lookup"><span data-stu-id="22fec-229">The **Format** button</span></span>  
:::image-end:::  

## <span data-ttu-id="22fec-230">编辑脚本</span><span class="sxs-lookup"><span data-stu-id="22fec-230">Edit a script</span></span>   

<span data-ttu-id="22fec-231">修复 bug 时，你经常希望测试对 JavaScript 代码所做的一些更改。</span><span class="sxs-lookup"><span data-stu-id="22fec-231">When fixing a bug, you often want to test out some changes to your JavaScript code.</span></span>  <span data-ttu-id="22fec-232">无需在外部编辑器或 IDE 中进行更改，然后重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="22fec-232">You do not need to make the changes in an external editor or IDE and then reload the page.</span></span>  <span data-ttu-id="22fec-233">你可以在 DevTools 中编辑脚本。</span><span class="sxs-lookup"><span data-stu-id="22fec-233">You may edit your script in DevTools.</span></span>  

<span data-ttu-id="22fec-234">完成以下操作以编辑脚本。</span><span class="sxs-lookup"><span data-stu-id="22fec-234">Complete the following actions to edit a script.</span></span>  

1.  <span data-ttu-id="22fec-235">在 "**源**" 面板的 "**编辑器**" 窗格中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="22fec-235">Open the file in the **Editor** pane of the **Sources** panel.</span></span>  
1.  <span data-ttu-id="22fec-236">在 " **编辑器** " 窗格中进行更改。</span><span class="sxs-lookup"><span data-stu-id="22fec-236">Make your changes in the **Editor** pane.</span></span>  
1.  <span data-ttu-id="22fec-237">按 `Ctrl` + `S` \ (Windows \ ) 或 `Command` + `S` \ (macOS \ ) 保存。</span><span class="sxs-lookup"><span data-stu-id="22fec-237">Press `Ctrl`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="22fec-238">DevTools 将整个 JS 文件修补到 Microsoft Edge 的 JavaScript 引擎中。</span><span class="sxs-lookup"><span data-stu-id="22fec-238">DevTools patches the entire JS file into the JavaScript engine of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text=""编辑器" 窗格" lightbox="../media/javascript-sources-html-minified.msft.png":::
       <span data-ttu-id="22fec-240">" **编辑器** " 窗格</span><span class="sxs-lookup"><span data-stu-id="22fec-240">The **Editor** pane</span></span>  
    :::image-end:::  
     
## <span data-ttu-id="22fec-241">禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="22fec-241">Disable JavaScript</span></span>   

<span data-ttu-id="22fec-242">请参阅 [禁用 Microsoft Edge DevTools JavaScript][DevToolsJavascriptDisable]。</span><span class="sxs-lookup"><span data-stu-id="22fec-242">See [Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>  

## <span data-ttu-id="22fec-243">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="22fec-243">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageStepOverIcon]: ../media/step-over-icon.msft.png  
[ImageStepIntoIcon]: ../media/step-into-icon.msft.png  
[ImageStepOutIcon]: ../media/step-out-icon.msft.png  
[ImageResumeScriptExecutionIcon]: ../media/resume-script-run-icon.msft.png  
[ImageForceScriptExecutionIcon]: ../media/force-script-run-icon.msft.png  
[ImageAddExpressionIcon]: ../media/add-expression-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageDeleteExpressionIcon]: ../media/delete-expression-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools 中暂停带有断点的代码 |Microsoft 文档"  
[DevToolsJavascriptDisable]: ./disable.md "通过 Microsoft Edge DevTools 禁用 JavaScript |Microsoft 文档"  
[DevToolsJavascriptGetStarted]: ./index.md "开始使用 Microsoft Edge DevTools 中的 JavaScript 调试 |Microsoft 文档"  
[DevToolsJavascriptSnippets]: ./snippets.md "在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段 |Microsoft 文档"  
[DevToolsCustomize]: ../customize/index.md "自定义 Microsoft Edge DevTools |Microsoft 文档"  

> [!NOTE]
> <span data-ttu-id="22fec-249">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="22fec-249">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="22fec-250">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="22fec-250">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="22fec-252">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="22fec-252">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
