---
description: 在此 Microsoft Edge DevTools 调试功能的全面参考中发现新的调试工作流。
title: JavaScript 调试引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 09a2d61269b2fe3a23a57ce58eb1c89b12a7639c
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398474"
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

# <a name="javascript-debugging-reference"></a><span data-ttu-id="9d2f5-104">JavaScript 调试引用</span><span class="sxs-lookup"><span data-stu-id="9d2f5-104">JavaScript debugging reference</span></span>  

<span data-ttu-id="9d2f5-105">通过以下 Microsoft Edge DevTools 调试功能的全面参考发现新的调试工作流。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-105">Discover new debugging workflows with the following comprehensive reference of Microsoft Edge DevTools debugging features.</span></span>  

<span data-ttu-id="9d2f5-106">若要了解调试的基础知识，请导航到 [Microsoft Edge DevTools][DevToolsJavascriptGetStarted]中的调试 JavaScript 入门。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-106">To learn the basics of debugging, navigate to [Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted].</span></span>  

## <a name="pause-code-with-breakpoints"></a><span data-ttu-id="9d2f5-107">使用断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="9d2f5-107">Pause code with breakpoints</span></span>  

<span data-ttu-id="9d2f5-108">设置断点，以便可以在运行时中间暂停代码。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-108">Set a breakpoint so that you are able to pause your code in the middle of the runtime.</span></span>  

<span data-ttu-id="9d2f5-109">若要了解如何设置断点，请导航到"使用断[点暂停代码"。][DevToolsJavascriptBreakpoints]</span><span class="sxs-lookup"><span data-stu-id="9d2f5-109">To learn how to set breakpoints, navigate to [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

## <a name="step-through-code"></a><span data-ttu-id="9d2f5-110">分步执行代码</span><span class="sxs-lookup"><span data-stu-id="9d2f5-110">Step through code</span></span>  

<span data-ttu-id="9d2f5-111">暂停代码后，一次单步执行一行，一直调查控制流和属性值。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-111">Once your code is paused, step through it, one line at a time, investigating control flow and property values along the way.</span></span>  

### <a name="step-over-line-of-code"></a><span data-ttu-id="9d2f5-112">逐行代码</span><span class="sxs-lookup"><span data-stu-id="9d2f5-112">Step over line of code</span></span>  

<span data-ttu-id="9d2f5-113">在包含与正在调试的问题不相关的函数的一行代码上暂停时，选择"单 **步执行** \ (单步执行 ![ \) "按钮，无需单步执行即可运行 ][ImageStepOverIcon] 该函数。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-113">When paused on a line of code containing a function that is not relevant to the problem you are debugging, choose the **Step over** \(![Step over][ImageStepOverIcon]\) button to run the function without stepping into it.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="选择"逐步执行"" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   <span data-ttu-id="9d2f5-115">选择 **"逐步执行"**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-115">Choose **Step over**</span></span>  
:::image-end:::  

<span data-ttu-id="9d2f5-116">例如，假设您正在调试以下代码段。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-116">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="9d2f5-117">你已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-117">You are paused on `A`.</span></span>  <span data-ttu-id="9d2f5-118">选择" **单步执行"后**，DevTools 将运行你正在单步执行的函数中的所有代码， `B` 即 `C` 和 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-118">After you choose **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="9d2f5-119">然后，DevTools 暂停 `D` 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-119">DevTools then pauses on `D`.</span></span>  

### <a name="step-into-line-of-code"></a><span data-ttu-id="9d2f5-120">分步执行代码行</span><span class="sxs-lookup"><span data-stu-id="9d2f5-120">Step into line of code</span></span>  

<span data-ttu-id="9d2f5-121">当暂停包含与正在调试的问题相关的函数调用的代码行时，选择"单步执行 **\ (** 单步执行 ![ \) "按钮以进一步调查该 ][ImageStepIntoIcon] 函数。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-121">When paused on a line of code containing a function call that is related to the problem you are debugging, choose the **Step into** \(![Step into][ImageStepIntoIcon]\) button to investigate that function further.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="选择"步骤"" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   <span data-ttu-id="9d2f5-123">选择 **"步骤"**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-123">Choose **Step into**</span></span>  
:::image-end:::  

<span data-ttu-id="9d2f5-124">例如，假设您正在调试以下代码段。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-124">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="9d2f5-125">你已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-125">You are paused on `A`.</span></span>  <span data-ttu-id="9d2f5-126">选择" **进入"后**，DevTools 将运行此代码行，然后暂停 `B` 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-126">After you choose **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <a name="step-out-of-line-of-code"></a><span data-ttu-id="9d2f5-127">逐步退出代码行</span><span class="sxs-lookup"><span data-stu-id="9d2f5-127">Step out of line of code</span></span>  

<span data-ttu-id="9d2f5-128">当暂停在与正在调试的问题不相关的函数内时，选择"单步执行\*\*\*\* "\ ("退出 ![ \) 按钮以运行函数的其余 ][ImageStepOutIcon] 代码。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-128">When paused inside of a function that is not related to the problem you are debugging, choose the **Step out** \(![Step out][ImageStepOutIcon]\) button to run the rest of the code of the function.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="选择"退出"" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   <span data-ttu-id="9d2f5-130">选择 **"退出"**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-130">Choose **Step out**</span></span>  
:::image-end:::  

<span data-ttu-id="9d2f5-131">例如，假设您正在调试以下代码段。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-131">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="9d2f5-132">你已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-132">You are paused on `A`.</span></span>  <span data-ttu-id="9d2f5-133">选择" **逐步退出"** 后，DevTools 将运行其中的其他代码，该代码仅在此示例中运行， `getName()` `B` 然后暂停 `C` 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-133">After you choose **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <a name="run-all-code-up-to-a-specific-line"></a><span data-ttu-id="9d2f5-134">运行所有代码，最多运行一行</span><span class="sxs-lookup"><span data-stu-id="9d2f5-134">Run all code up to a specific line</span></span>  

<span data-ttu-id="9d2f5-135">调试长函数时，可能有许多代码与正在调试的问题不相关。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-135">When debugging a long function, there may be a lot of code that is not related to the problem you are debugging.</span></span>  

<span data-ttu-id="9d2f5-136">你可以选择逐一执行所有行，但这很繁琐。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-136">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="9d2f5-137">您可以选择在感兴趣的行上设置代码行断点，然后选择"恢复脚本执行 "\ (Resume Script \*\*\*\* ![ Execution \) 按钮，但有一种更快的方法 ][ImageResumeScriptExecutionIcon] 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-137">You may choose to set a line-of-code breakpoint on the line in which you are interested and then choose the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button, but there is a faster way.</span></span>  

<span data-ttu-id="9d2f5-138">将鼠标悬停在感兴趣的代码行上，打开上下文菜单 \ (右键单击\) ，然后选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-138">Hover on the line of code in which you are interested, open the contextual menu \(right-click\), and choose **Continue to here**.</span></span>  <span data-ttu-id="9d2f5-139">DevTools 运行所有代码，一直运行到该点，然后暂停该行。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-139">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="选择"继续"此处" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   <span data-ttu-id="9d2f5-141">选择 **"继续"此处**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-141">Choose **Continue to here**</span></span>  
:::image-end:::  

### <a name="restart-the-top-function-of-the-call-stack"></a><span data-ttu-id="9d2f5-142">重新启动调用堆栈的顶部函数</span><span class="sxs-lookup"><span data-stu-id="9d2f5-142">Restart the top function of the call stack</span></span>  

<span data-ttu-id="9d2f5-143">若要暂停调用堆栈中顶部函数的第一行，而暂停在代码行上，将鼠标悬停在调用堆栈窗格中的任意位置，打开\*\*\*\* 上下文菜单 \ (右键单击\) ，然后选择"重新启动帧 **"。**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-143">To pause on the first line of the top function in your call stack, while paused on a line of code, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Restart Frame**.</span></span>  <span data-ttu-id="9d2f5-144">顶部函数是最后一个运行的函数。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-144">The top function is the last function that was run.</span></span>  

<span data-ttu-id="9d2f5-145">下面的代码段是一个演示示例。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-145">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="9d2f5-146">你已暂停 `A` 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-146">You are paused on `A`.</span></span>  <span data-ttu-id="9d2f5-147">选择 **"重启帧**"后，应暂停打开，而无需设置断 `B` 点或选择 **"恢复脚本执行"。**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-147">After choosing **Restart Frame**, you should be paused on `B`, without ever setting a breakpoint or choosing **Resume script execution**.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="选择"重启帧"" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   <span data-ttu-id="9d2f5-149">选择 **"重启帧"**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-149">Choose **Restart Frame**</span></span>  
:::image-end:::  

### <a name="resume-script-runtime"></a><span data-ttu-id="9d2f5-150">恢复脚本运行时</span><span class="sxs-lookup"><span data-stu-id="9d2f5-150">Resume script runtime</span></span>  

<span data-ttu-id="9d2f5-151">若要在脚本暂停后继续运行时，请选择"恢复脚本执行\*\*\*\*"\ ("恢复脚本执行 ![ ][ImageResumeScriptExecutionIcon] ") 按钮。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-151">To continue the runtime after a pause of your script, choose the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button.</span></span>  <span data-ttu-id="9d2f5-152">DevTools 向上运行脚本，直到下一个断点（如果有）。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-152">DevTools runs the script up until the next breakpoint, if any.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="选择"恢复脚本执行"" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   <span data-ttu-id="9d2f5-154">选择 **"恢复脚本执行"**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-154">Choose **Resume script execution**</span></span>  
:::image-end:::  

#### <a name="force-script-runtime"></a><span data-ttu-id="9d2f5-155">强制脚本运行时</span><span class="sxs-lookup"><span data-stu-id="9d2f5-155">Force script runtime</span></span>  

<span data-ttu-id="9d2f5-156">若要忽略所有断点并强制脚本继续运行，请选择并按住"恢复脚本执行 **"\ (** 继续脚本执行 \) 按钮，然后选择"强制执行脚本 ![ ][ImageResumeScriptExecutionIcon] "\ ("\*\*\*\* 强制脚本执行 ![ ][ImageForceScriptExecutionIcon] ") 按钮。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-156">To ignore all breakpoints and force your script to resume running, choose and hold the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button and then choose the **Force script execution** \(![Force script execution][ImageForceScriptExecutionIcon]\) button.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="选择"强制执行脚本"" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   <span data-ttu-id="9d2f5-158">选择 **"强制执行脚本"**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-158">Choose **Force script execution**</span></span>  
:::image-end:::  

### <a name="change-thread-context"></a><span data-ttu-id="9d2f5-159">更改线程上下文</span><span class="sxs-lookup"><span data-stu-id="9d2f5-159">Change thread context</span></span>  

<span data-ttu-id="9d2f5-160">使用 Web 工作人员或服务工作者时，选择"线程"窗格中列出的\*\*\*\* 上下文以切换到该上下文。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-160">When working with web workers or service workers, choose on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="9d2f5-161">蓝色箭头图标表示当前选定的上下文。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-161">The blue arrow icon represents which context is currently selected.</span></span>  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text=""线程"窗格" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   <span data-ttu-id="9d2f5-163">" **线程"** 窗格</span><span class="sxs-lookup"><span data-stu-id="9d2f5-163">The **Threads** pane</span></span>  
:::image-end:::  

<span data-ttu-id="9d2f5-164">例如，假设您已暂停主脚本和服务工作线程脚本中的断点。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-164">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="9d2f5-165">您希望查看服务工作线程上下文的本地和全局属性，但"源"面板显示\*\*\*\* 主脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-165">You want to view the local and global properties for the service worker context, but the **Sources** panel is showing the main script context.</span></span>  <span data-ttu-id="9d2f5-166">通过选择"线程"窗格中的服务工作者条目\*\*\*\*，您应该能够切换到该上下文。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-166">By choosing on the service worker entry in the **Threads** pane, you should be able to switch to that context.</span></span>  

## <a name="view-and-edit-local-closure-and-global-properties"></a><span data-ttu-id="9d2f5-167">查看和编辑本地、关闭和全局属性</span><span class="sxs-lookup"><span data-stu-id="9d2f5-167">View and edit local, closure, and global properties</span></span>  

<span data-ttu-id="9d2f5-168">在代码行上暂停时，使用"范围"\*\*\*\* 窗格查看和编辑本地、关闭和全局范围中的属性和变量的值。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-168">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="9d2f5-169">双击某个属性值以更改它。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-169">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="9d2f5-170">不可枚举的属性灰度。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-170">Non-enumerable properties are greyed out.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text=""范围"窗格" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   <span data-ttu-id="9d2f5-172">" **范围"** 窗格</span><span class="sxs-lookup"><span data-stu-id="9d2f5-172">The **Scope** pane</span></span>  
:::image-end:::  

## <a name="view-the-current-call-stack"></a><span data-ttu-id="9d2f5-173">查看当前调用堆栈</span><span class="sxs-lookup"><span data-stu-id="9d2f5-173">View the current call stack</span></span>  

<span data-ttu-id="9d2f5-174">在一行代码上暂停时，使用"调用\*\*\*\* 堆栈"窗格查看已到达此点的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-174">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="9d2f5-175">选择一个条目以跳转到调用该函数的代码行。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-175">Choose an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="9d2f5-176">蓝色箭头图标表示 DevTools 当前突出显示的函数。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-176">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text=""调用堆栈"窗格" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   <span data-ttu-id="9d2f5-178">" **调用堆栈"** 窗格</span><span class="sxs-lookup"><span data-stu-id="9d2f5-178">The **Call Stack** pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="9d2f5-179">当代码行上未暂停时，" **调用堆栈** "窗格为空。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-179">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <a name="copy-stack-trace"></a><span data-ttu-id="9d2f5-180">复制堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="9d2f5-180">Copy stack trace</span></span>  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="9d2f5-181">若要将当前调用堆栈复制到剪贴板，请将鼠标悬停在"调用\*\*\*\* 堆栈"窗格中的任意位置，打开上下文菜单 \ (右键单击\) ，然后选择 **"** 复制堆栈跟踪"。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-181">to copy the current call stack to the clipboard, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Copy stack trace**.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="选择"复制堆栈跟踪"" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   <span data-ttu-id="9d2f5-183">选择 **"复制堆栈跟踪"**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-183">Choose **Copy Stack Trace**</span></span>  
:::image-end:::  

<span data-ttu-id="9d2f5-184">以下代码段是输出的一个示例。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-184">The following code snippet is an example of the output.</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onChoose (get-started.js:15)
```  

## <a name="ignore-a-script-or-pattern-of-scripts"></a><span data-ttu-id="9d2f5-185">忽略脚本或脚本模式</span><span class="sxs-lookup"><span data-stu-id="9d2f5-185">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="9d2f5-186">当你想要在调试时忽略该脚本时，将脚本标记为库代码。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-186">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="9d2f5-187">当标记为库代码时，脚本在"调用堆栈"窗格中\*\*\*\* 被遮盖，并且你永远不会在单步执行代码时单步执行脚本的功能。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-187">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="9d2f5-188">下面的代码段是一个演示示例。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-188">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` <span data-ttu-id="9d2f5-189">是信任的第三方库。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-189">is a third-party library that you trust.</span></span>  <span data-ttu-id="9d2f5-190">如果您确信正在调试的问题与第三方库不相关，那么将脚本标记为库代码 **是有意义的**。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-190">If you are confident that the problem you are debugging is not related to the third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

### <a name="mark-a-script-as-library-code-from-the-editor-pane"></a><span data-ttu-id="9d2f5-191">从编辑器窗格中将脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="9d2f5-191">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="9d2f5-192">完成以下操作，从编辑器窗格中将脚本**标记为\*\*\*\*库代码**。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-192">Complete the following actions to mark a script as **Library code** from the **Editor** pane.</span></span>  

1.  <span data-ttu-id="9d2f5-193">打开文件。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-193">Open the file.</span></span>  
1.  <span data-ttu-id="9d2f5-194">将鼠标悬停在任意位置并打开上下文菜单 \ (右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-194">Hover anywhere and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="9d2f5-195">选择 **"标记为库代码"。**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-195">Choose **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="从编辑器窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       <span data-ttu-id="9d2f5-197">从编辑器窗格中**将脚本标记为\*\*\*\*库代码**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-197">Mark a script as **Library code** from the **Editor** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-the-call-stack-pane"></a><span data-ttu-id="9d2f5-198">从"调用堆栈"窗格中将脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="9d2f5-198">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="9d2f5-199">完成以下操作，从"调用堆栈"\*\*\*\* 窗格中将脚本标记为**库**代码。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-199">Complete the following actions to mark a script as **Library code** from the **Call Stack** pane.</span></span>  

1.  <span data-ttu-id="9d2f5-200">将鼠标悬停在脚本的函数上，然后打开上下文菜单 \ (右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-200">Hover on a function from the script and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="9d2f5-201">选择 **"标记为库代码"。**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-201">Choose **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="从"调用堆栈"窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       <span data-ttu-id="9d2f5-203">从"调用堆栈 **"窗格中** 将脚本 **标记为库** 代码</span><span class="sxs-lookup"><span data-stu-id="9d2f5-203">Mark a script as **Library code** from the **Call Stack** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-settings"></a><span data-ttu-id="9d2f5-204">从"设置"中将脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="9d2f5-204">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="9d2f5-205">完成以下操作以标记"设置"中的单个脚本或 **脚本模式**。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-205">Complete the following actions to mark a single script or pattern of scripts from **Settings**.</span></span>  

1.  <span data-ttu-id="9d2f5-206">打开["设置"。][DevToolsCustomize]</span><span class="sxs-lookup"><span data-stu-id="9d2f5-206">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="9d2f5-207">导航到 **库代码** 设置。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-207">Navigate to the **Library code** setting.</span></span>  
1.  <span data-ttu-id="9d2f5-208">选择 **"添加模式"。**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-208">Choose **Add pattern**.</span></span>  
1.  <span data-ttu-id="9d2f5-209">输入脚本名称或脚本名称的正则表达式模式，以标记为 **库代码**。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-209">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="9d2f5-210">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-210">Choose **Add**.</span></span>  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="从"设置"中将脚本标记为库代码" lightbox="../media/javascript-framework-library-code.msft.png":::
       <span data-ttu-id="9d2f5-212">从"设置" **中将脚本标记为** 库 **代码**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-212">Mark a script as **Library code** from **Settings**</span></span>  
    :::image-end:::  
    
## <a name="run-snippets-of-debug-code-from-any-page"></a><span data-ttu-id="9d2f5-213">从任何页面运行调试代码的代码段</span><span class="sxs-lookup"><span data-stu-id="9d2f5-213">Run snippets of debug code from any page</span></span>  

<span data-ttu-id="9d2f5-214">如果你发现自己在控制台中一次又一次地运行相同的调试代码，请考虑使用代码段。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-214">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="9d2f5-215">代码段是你在 DevTools 中创作、存储和运行的运行时脚本。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-215">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="9d2f5-216">若要了解更多信息，请导航到"从任何[页面运行代码段"。][DevToolsJavascriptSnippets]</span><span class="sxs-lookup"><span data-stu-id="9d2f5-216">To learn more, navigate to [Run Snippets of Code From Any Page][DevToolsJavascriptSnippets].</span></span>  

## <a name="watch-the-values-of-custom-javascript-expressions"></a><span data-ttu-id="9d2f5-217">观看自定义 JavaScript 表达式的值</span><span class="sxs-lookup"><span data-stu-id="9d2f5-217">Watch the values of custom JavaScript expressions</span></span>  

<span data-ttu-id="9d2f5-218">使用 **监视** 窗格监视自定义表达式的值。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-218">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="9d2f5-219">你可以观看任何有效的 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-219">You may watch any valid JavaScript expression.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text=""监视"窗格" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   <span data-ttu-id="9d2f5-221">监视**窗格**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-221">The **Watch** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="9d2f5-222">选择 **"添加表达式** " (![ 添加表达式 ][ImageAddExpressionIcon] \) 按钮以创建新的监视表达式。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-222">Choose the **Add Expression** \(![Add Expression][ImageAddExpressionIcon]\) button to create a new watch expression.</span></span>  
*   <span data-ttu-id="9d2f5-223">选择 **"刷新** \ (![ ][ImageRefreshIcon] 刷新 \) "按钮以刷新所有现有表达式的值。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-223">Choose the **Refresh** \(![Refresh][ImageRefreshIcon]\) button to refresh the values of all existing expressions.</span></span>  <span data-ttu-id="9d2f5-224">值在逐步执行代码时自动刷新。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-224">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="9d2f5-225">将鼠标悬停在表达式上，然后选择"删除 **表达式 (** ![ 删除表达式 ][ImageDeleteExpressionIcon] \) 按钮将其删除。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-225">Hover on an expression and choose the **Delete Expression** \(![Delete Expression][ImageDeleteExpressionIcon]\) button to delete it.</span></span>  

## <a name="make-a-minified-file-readable"></a><span data-ttu-id="9d2f5-226">使缩小文件可读</span><span class="sxs-lookup"><span data-stu-id="9d2f5-226">Make a minified file readable</span></span>  

<span data-ttu-id="9d2f5-227">Choose the **Format** \ (![ Format ][ImageFormatIcon] \) button to make a minified file human-readable.</span><span class="sxs-lookup"><span data-stu-id="9d2f5-227">Choose the **Format** \(![Format][ImageFormatIcon]\) button to make a minified file human-readable.</span></span>  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text=""格式"按钮" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   <span data-ttu-id="9d2f5-229">" **格式"** 按钮</span><span class="sxs-lookup"><span data-stu-id="9d2f5-229">The **Format** button</span></span>  
:::image-end:::  

## <a name="edit-a-script"></a><span data-ttu-id="9d2f5-230">编辑脚本</span><span class="sxs-lookup"><span data-stu-id="9d2f5-230">Edit a script</span></span>  

<span data-ttu-id="9d2f5-231">修复 Bug 时，经常需要测试对 JavaScript 代码的一些更改。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-231">When fixing a bug, you often want to test out some changes to your JavaScript code.</span></span>  <span data-ttu-id="9d2f5-232">无需在外部编辑器或 IDE 中进行更改，然后刷新页面。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-232">You do not need to make the changes in an external editor or IDE and then refresh the page.</span></span>  <span data-ttu-id="9d2f5-233">您可以在 DevTools 中编辑脚本。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-233">You may edit your script in DevTools.</span></span>  

<span data-ttu-id="9d2f5-234">完成以下操作以编辑脚本。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-234">Complete the following actions to edit a script.</span></span>  

1.  <span data-ttu-id="9d2f5-235">在"源"面板 **的"** 编辑器" **窗格中打开** 该文件。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-235">Open the file in the **Editor** pane of the **Sources** panel.</span></span>  
1.  <span data-ttu-id="9d2f5-236">在编辑器窗格中 **进行更改** 。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-236">Make your changes in the **Editor** pane.</span></span>  
1.  <span data-ttu-id="9d2f5-237">选择 `Ctrl` + `S` " (Windows、Linux\) `Command` + `S` 或 \ (macOS\) 保存。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-237">Select `Ctrl`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="9d2f5-238">DevTools 将整个 JS 文件修补为 Microsoft Edge 的 JavaScript 引擎。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-238">DevTools patches the entire JS file into the JavaScript engine of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="编辑器窗格" lightbox="../media/javascript-sources-html-minified.msft.png":::
       <span data-ttu-id="9d2f5-240">编辑器**窗格**</span><span class="sxs-lookup"><span data-stu-id="9d2f5-240">The **Editor** pane</span></span>  
    :::image-end:::  
     
## <a name="disable-javascript"></a><span data-ttu-id="9d2f5-241">禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="9d2f5-241">Disable JavaScript</span></span>  

<span data-ttu-id="9d2f5-242">导航到[使用 Microsoft Edge DevTools 禁用 JavaScript。][DevToolsJavascriptDisable]</span><span class="sxs-lookup"><span data-stu-id="9d2f5-242">Navigate to [Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9d2f5-243">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="9d2f5-243">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "使用 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "开始在 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "在具有 Microsoft Edge DevTools 应用程序的任何页面上运行 JavaScript |Microsoft Docs"  
[DevToolsCustomize]: ../customize/index.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="9d2f5-249">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-249">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9d2f5-250">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-250">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9d2f5-252">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9d2f5-252">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
