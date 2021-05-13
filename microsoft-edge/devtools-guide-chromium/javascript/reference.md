---
description: 在此 Microsoft Edge DevTools 调试功能的全面参考中发现新的调试工作流。
title: 使用调试程序功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6b15d317d4c720ab5ad76b7047532df101f69376
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564124"
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
# <a name="use-the-debugger-features"></a><span data-ttu-id="3a64e-104">使用调试程序功能</span><span class="sxs-lookup"><span data-stu-id="3a64e-104">Use the debugger features</span></span>

<span data-ttu-id="3a64e-105">本文介绍了如何在 DevTools Microsoft Edge调试器，包括如何设置代码行断点。</span><span class="sxs-lookup"><span data-stu-id="3a64e-105">This article covers how to use the debugger in Microsoft Edge DevTools, including how to set a line-of-code breakpoint.</span></span>  <span data-ttu-id="3a64e-106">若要设置其他类型的断点，请参阅使用断点 [暂停代码][DevToolsJavascriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="3a64e-106">To set other types of breakpoints, see [Pause your code with breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

<span data-ttu-id="3a64e-107">若要了解调试的基础知识，请导航到[Microsoft Edge DevTools][DevToolsJavascriptGetStarted]中调试 JavaScript 的入门，这是一个使用基于表单的现有网页的教程。</span><span class="sxs-lookup"><span data-stu-id="3a64e-107">To learn the basics of debugging, navigate to [Get started with debugging JavaScript in Microsoft Edge DevTools][DevToolsJavascriptGetStarted], which is a tutorial that uses an existing, form-based webpage.</span></span>  <span data-ttu-id="3a64e-108">本教程具有屏幕捕获，因此你可以浏览它。</span><span class="sxs-lookup"><span data-stu-id="3a64e-108">The tutorial has screen captures, so you can skim it.</span></span>  <span data-ttu-id="3a64e-109">您可以使用演示网页轻松试用调试器功能。</span><span class="sxs-lookup"><span data-stu-id="3a64e-109">You can easily try out the debugger features by using the demo webpage.</span></span>

## <a name="view-and-edit-javascript-code"></a><span data-ttu-id="3a64e-110">查看和编辑 JavaScript 代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-110">View and edit JavaScript code</span></span>

<span data-ttu-id="3a64e-111">修复 Bug 时，经常希望尝试对 JavaScript 代码进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="3a64e-111">When fixing a bug, you often want to try out some changes to your JavaScript code.</span></span>  <span data-ttu-id="3a64e-112">无需在外部编辑器或 IDE 中进行更改，将文件重新上载到服务器，然后刷新页面;相反，若要测试更改，可以直接在 DevTools 中编辑 JavaScript 代码并立即查看结果。</span><span class="sxs-lookup"><span data-stu-id="3a64e-112">You don't need to make the changes in an external editor or IDE, re-upload the file to the server, and then refresh the page; instead, to test changes, you can edit your JavaScript code directly in DevTools and see the result immediately.</span></span>  

<span data-ttu-id="3a64e-113">若要查看和编辑 JavaScript 文件，请运行：</span><span class="sxs-lookup"><span data-stu-id="3a64e-113">To view and edit a JavaScript file:</span></span>  

1.  <span data-ttu-id="3a64e-114">导航到 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="3a64e-114">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="3a64e-115">在 **导航器窗格中** ，选择你的文件，以在编辑器窗格中 **打开** 它。</span><span class="sxs-lookup"><span data-stu-id="3a64e-115">In the **Navigator** pane, select your file, to open it in the **Editor** pane.</span></span>
1.  <span data-ttu-id="3a64e-116">在" **编辑器"** 窗格中，编辑文件。</span><span class="sxs-lookup"><span data-stu-id="3a64e-116">In the **Editor** pane, edit your file.</span></span>  
1.  <span data-ttu-id="3a64e-117">选择 `Ctrl`+`S` \(Windows、Linux\) 或 `Command`+`S` \(macOS\) 进行保存。</span><span class="sxs-lookup"><span data-stu-id="3a64e-117">Select `Ctrl`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="3a64e-118">然后，DevTools 将 JavaScript 文件加载至 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3a64e-118">DevTools then loads the JavaScript file into the JavaScript engine of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="编辑器窗格" lightbox="../media/javascript-sources-html-minified.msft.png":::
       <span data-ttu-id="3a64e-120">“**编辑器**”窗格</span><span class="sxs-lookup"><span data-stu-id="3a64e-120">The **Editor** pane</span></span>  
    :::image-end:::  
     
## <a name="reformat-a-minified-javascript-file-with-pretty-print"></a><span data-ttu-id="3a64e-121">使用非常打印重新设置缩小的 JavaScript 文件</span><span class="sxs-lookup"><span data-stu-id="3a64e-121">Reformat a minified JavaScript file with pretty-print</span></span>

<span data-ttu-id="3a64e-122">若要使缩小的文件可读，请选择"编辑器"窗格底部的\*\*\*\*"格式 ![ \ (Format ](../media/format-icon.msft.png) **\) "** 按钮。</span><span class="sxs-lookup"><span data-stu-id="3a64e-122">To make a minified file human-readable, choose the **Format** \(![Format](../media/format-icon.msft.png)\) button at the bottom of the **Editor** pane.</span></span>

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="格式按钮" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   <span data-ttu-id="3a64e-124">“**格式**”按钮</span><span class="sxs-lookup"><span data-stu-id="3a64e-124">The **Format** button</span></span>  
:::image-end:::  

## <a name="set-a-breakpoint-to-pause-code"></a><span data-ttu-id="3a64e-125">设置断点以暂停代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-125">Set a breakpoint, to pause code</span></span>

<span data-ttu-id="3a64e-126">若要在运行时期间暂停代码，请设置一个断点。</span><span class="sxs-lookup"><span data-stu-id="3a64e-126">To pause your code in the middle of the runtime, set a breakpoint.</span></span>  <span data-ttu-id="3a64e-127">最基本的和已知的断点类型是代码行断点。</span><span class="sxs-lookup"><span data-stu-id="3a64e-127">The most basic and well-known type of breakpoint is a line-of-code breakpoint.</span></span>

<span data-ttu-id="3a64e-128">知道需要调查的确切代码区域时，使用代码行断点。</span><span class="sxs-lookup"><span data-stu-id="3a64e-128">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="3a64e-129">DevTools 始终在指定的代码行暂停，然后再运行它。</span><span class="sxs-lookup"><span data-stu-id="3a64e-129">DevTools always pauses at the specified line of code, before running it.</span></span>

<span data-ttu-id="3a64e-130">设置代码行断点：</span><span class="sxs-lookup"><span data-stu-id="3a64e-130">To set a line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="3a64e-131">导航到 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="3a64e-131">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="3a64e-132">打开包含代码行的文件。</span><span class="sxs-lookup"><span data-stu-id="3a64e-132">Open the file that contains the line of code.</span></span>  
1.  <span data-ttu-id="3a64e-133">选择代码行的行号左侧的区域。</span><span class="sxs-lookup"><span data-stu-id="3a64e-133">Select the area to the left of the line number for the line of code.</span></span>  <span data-ttu-id="3a64e-134">或者，右键单击行号，然后选择"**添加断点"。**</span><span class="sxs-lookup"><span data-stu-id="3a64e-134">Or, right-click the line number and then choose **Add breakpoint**.</span></span>  <span data-ttu-id="3a64e-135">然后，行号旁边会出现一个红色圆圈，指示断点。</span><span class="sxs-lookup"><span data-stu-id="3a64e-135">A red circle then appears next to the line number, indicating a breakpoint.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="3a64e-137">代码行断点</span><span class="sxs-lookup"><span data-stu-id="3a64e-137">A line-of-code breakpoint</span></span>  
    :::image-end:::  

<span data-ttu-id="3a64e-138">代码行断点设置效率可能较低，尤其是在您不知道具体查找位置或代码库较大时。</span><span class="sxs-lookup"><span data-stu-id="3a64e-138">Line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if your codebase is large.</span></span>  <span data-ttu-id="3a64e-139">若要在调试时节省时间，请了解如何以及何时使用其他类型的断点。</span><span class="sxs-lookup"><span data-stu-id="3a64e-139">To save time when debugging, learn how and when to use the other types of breakpoints.</span></span>  <span data-ttu-id="3a64e-140">有关详细信息，请导航到["使用断点暂停代码"。][DevToolsJavascriptBreakpoints]</span><span class="sxs-lookup"><span data-stu-id="3a64e-140">For more information, navigate to [Pause your code with breakpoints][DevToolsJavascriptBreakpoints].</span></span>

## <a name="step-through-code"></a><span data-ttu-id="3a64e-141">单步执行代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-141">Step through code</span></span>  

<span data-ttu-id="3a64e-142">在断点暂停代码后，逐步执行代码，一次一行，一直调查控制流和属性值。</span><span class="sxs-lookup"><span data-stu-id="3a64e-142">After your code is paused at a breakpoint, step through the code, one line at a time, investigating control flow and property values along the way.</span></span>  

### <a name="step-over-line-of-code"></a><span data-ttu-id="3a64e-143">逐步执行代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-143">Step over line of code</span></span>  

<span data-ttu-id="3a64e-144">当暂停包含与正在调试的问题不相关的函数的代码行时，选择"单步执行**\ (** 单步 ![ 执行 \) "按钮以在不单步执行的情况下运行函数。 ](../media/step-over-icon.msft.png)</span><span class="sxs-lookup"><span data-stu-id="3a64e-144">When paused on a line of code containing a function that isn't relevant to the problem you are debugging, choose the **Step over** \(![Step over](../media/step-over-icon.msft.png)\) button to run the function without stepping into it.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="选择逐步执行" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   <span data-ttu-id="3a64e-146">选择“**逐步执行**”</span><span class="sxs-lookup"><span data-stu-id="3a64e-146">Choose **Step over**</span></span>  
:::image-end:::  

<span data-ttu-id="3a64e-147">例如，假设您正在调试以下代码段。</span><span class="sxs-lookup"><span data-stu-id="3a64e-147">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="3a64e-148">你已在 `A` 上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-148">You are paused on `A`.</span></span>  <span data-ttu-id="3a64e-149">选择“**逐步执行**”后，DevTools 将运行要逐步执行的函数中的所有代码，即 `B` 和 `C`。</span><span class="sxs-lookup"><span data-stu-id="3a64e-149">After you choose **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="3a64e-150">DevTools 随后在 `D` 上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-150">DevTools then pauses on `D`.</span></span>  

### <a name="step-into-line-of-code"></a><span data-ttu-id="3a64e-151">逐行执行代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-151">Step into line of code</span></span>  

<span data-ttu-id="3a64e-152">暂停包含与正在调试的问题相关的函数调用的代码行时，选择“**逐行执行** \(![逐行执行](../media/step-into-icon.msft.png)\) "按钮以进一步调查该函数。</span><span class="sxs-lookup"><span data-stu-id="3a64e-152">When paused on a line of code containing a function call that is related to the problem you are debugging, choose the **Step into** \(![Step into](../media/step-into-icon.msft.png)\) button to investigate that function further.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="选择逐行执行" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   <span data-ttu-id="3a64e-154">选择“**逐行执行**”</span><span class="sxs-lookup"><span data-stu-id="3a64e-154">Choose **Step into**</span></span>  
:::image-end:::  

<span data-ttu-id="3a64e-155">例如，假设您正在调试以下代码段。</span><span class="sxs-lookup"><span data-stu-id="3a64e-155">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="3a64e-156">你已在 `A` 上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-156">You are paused on `A`.</span></span>  <span data-ttu-id="3a64e-157">选择“**逐行执行**”后，DevTools 将运行此代码行，然后在 `B` 上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-157">After you choose **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <a name="step-out-of-line-of-code"></a><span data-ttu-id="3a64e-158">执行剩余代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-158">Step out of line of code</span></span>  

<span data-ttu-id="3a64e-159">当暂停在与正在调试的问题不相关的函数内时，选择"单步执行 **\ (** 单步执行 \) "按钮以运行函数的其余 ![ ](../media/step-out-icon.msft.png) 代码。</span><span class="sxs-lookup"><span data-stu-id="3a64e-159">When paused inside of a function that isn't related to the problem you are debugging, choose the **Step out** \(![Step out](../media/step-out-icon.msft.png)\) button to run the rest of the code of the function.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="选择执行剩余" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   <span data-ttu-id="3a64e-161">选择 **“执行剩余”**</span><span class="sxs-lookup"><span data-stu-id="3a64e-161">Choose **Step out**</span></span>  
:::image-end:::  

<span data-ttu-id="3a64e-162">例如，假设您正在调试以下代码段。</span><span class="sxs-lookup"><span data-stu-id="3a64e-162">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="3a64e-163">你已在 `A` 上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-163">You are paused on `A`.</span></span>  <span data-ttu-id="3a64e-164">选择“**执行剩余**”后，DevTools 将运行 `getName()` 中代码的剩余部分，在此示例中为 `B`，然后在 `C` 上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-164">After you choose **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <a name="run-all-code-up-to-a-specific-line"></a><span data-ttu-id="3a64e-165">运行所有代码到特定行</span><span class="sxs-lookup"><span data-stu-id="3a64e-165">Run all code up to a specific line</span></span>  

<span data-ttu-id="3a64e-166">调试长函数时，可能有许多代码与正在调试的问题不相关。</span><span class="sxs-lookup"><span data-stu-id="3a64e-166">When debugging a long function, there may be a lot of code that isn't related to the problem you are debugging.</span></span>  

<span data-ttu-id="3a64e-167">你可以选择逐行执行，但这很繁琐。</span><span class="sxs-lookup"><span data-stu-id="3a64e-167">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="3a64e-168">您可以选择在感兴趣的行上设置代码行断点，然后选择 Resume **脚本** 执行 \ (Resume 脚本执行 ![ \) 按钮，但有一种更快的方法 ](../media/resume-script-run-icon.msft.png) 。</span><span class="sxs-lookup"><span data-stu-id="3a64e-168">You may choose to set a line-of-code breakpoint on the line in which you are interested and then choose the **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\) button, but there is a faster way.</span></span>  

<span data-ttu-id="3a64e-169">将鼠标悬停在你感兴趣的代码行上，打开上下文菜单 \(右键单击\) ，然后选择“**继续至此处**”。</span><span class="sxs-lookup"><span data-stu-id="3a64e-169">Hover on the line of code in which you are interested, open the contextual menu \(right-click\), and choose **Continue to here**.</span></span>  <span data-ttu-id="3a64e-170">DevTools 会运行所有代码，一直运行到该处，然后暂停到该行。</span><span class="sxs-lookup"><span data-stu-id="3a64e-170">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="选择继续至此处" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   <span data-ttu-id="3a64e-172">选择“**继续至此处**”</span><span class="sxs-lookup"><span data-stu-id="3a64e-172">Choose **Continue to here**</span></span>  
:::image-end:::  

### <a name="restart-the-top-function-of-the-call-stack"></a><span data-ttu-id="3a64e-173">重新启动调用的顶部函数</span><span class="sxs-lookup"><span data-stu-id="3a64e-173">Restart the top function of the call stack</span></span>  

<span data-ttu-id="3a64e-174">若要暂停调用堆栈中顶部函数的第一行，同时在代码行上暂停，请将鼠标悬停在"调用堆栈"窗格中的任意位置\*\*\*\*，打开上下文菜单 \ (右键单击\) ，然后选择"**重新启动**帧"。</span><span class="sxs-lookup"><span data-stu-id="3a64e-174">To pause on the first line of the top function in your call stack, while paused on a line of code, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Restart frame**.</span></span>  <span data-ttu-id="3a64e-175">top 函数是最后一个运行的函数。</span><span class="sxs-lookup"><span data-stu-id="3a64e-175">The top function is the last function that was run.</span></span>  

<span data-ttu-id="3a64e-176">下面的代码段是一个分步执行示例。</span><span class="sxs-lookup"><span data-stu-id="3a64e-176">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="3a64e-177">你已在 `A` 上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-177">You are paused on `A`.</span></span>  <span data-ttu-id="3a64e-178">选择重启**帧后**，应暂停在 上 `B` ，无需设置断点或选择 **"恢复脚本执行"。**</span><span class="sxs-lookup"><span data-stu-id="3a64e-178">After choosing **Restart frame**, you should be paused on `B`, without ever setting a breakpoint or choosing **Resume script execution**.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="选择重启帧" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   <span data-ttu-id="3a64e-180">选择 **重启帧**</span><span class="sxs-lookup"><span data-stu-id="3a64e-180">Choose **Restart frame**</span></span>  
:::image-end:::  

### <a name="resume-script-runtime"></a><span data-ttu-id="3a64e-181">恢复脚本运行时</span><span class="sxs-lookup"><span data-stu-id="3a64e-181">Resume script runtime</span></span>  

<span data-ttu-id="3a64e-182">若要在脚本暂停后继续运行时，请选择 Resume **script execution** \ (Resume script ![ execution ](../media/resume-script-run-icon.msft.png) \) button。</span><span class="sxs-lookup"><span data-stu-id="3a64e-182">To continue the runtime after a pause of your script, choose the **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\) button.</span></span>  <span data-ttu-id="3a64e-183">DevTools 将一直运行脚本，直到下一个断点（如果有）。</span><span class="sxs-lookup"><span data-stu-id="3a64e-183">DevTools runs the script up until the next breakpoint, if any.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="选择恢复脚本执行" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   <span data-ttu-id="3a64e-185">选择“**恢复脚本执行**”</span><span class="sxs-lookup"><span data-stu-id="3a64e-185">Choose **Resume script execution**</span></span>  
:::image-end:::  

#### <a name="force-script-runtime"></a><span data-ttu-id="3a64e-186">强制脚本运行时</span><span class="sxs-lookup"><span data-stu-id="3a64e-186">Force script runtime</span></span>  

<span data-ttu-id="3a64e-187">若要忽略所有断点并强制脚本继续运行，请选择并按住 Resume**脚本**执行 \ (Resume 脚本执行 \) 按钮，然后选择"强制脚本执行 ![ ](../media/resume-script-run-icon.msft.png) \ (强制脚本执行\*\*\*\* ![ ](../media/force-script-run-icon.msft.png) \) "按钮。</span><span class="sxs-lookup"><span data-stu-id="3a64e-187">To ignore all breakpoints and force your script to continue to run, choose and hold the **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\) button and then choose the **Force script execution** \(![Force script execution](../media/force-script-run-icon.msft.png)\) button.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="选择强制脚本执行" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   <span data-ttu-id="3a64e-189">选择“**强制脚本执行**”</span><span class="sxs-lookup"><span data-stu-id="3a64e-189">Choose **Force script execution**</span></span>  
:::image-end:::  

### <a name="change-thread-context"></a><span data-ttu-id="3a64e-190">更改线程上下文</span><span class="sxs-lookup"><span data-stu-id="3a64e-190">Change thread context</span></span>  

<span data-ttu-id="3a64e-191">使用 Web 工作进程或服务工作进程时，选择“**线程**”窗格中列出的上下文以切换到该上下文。</span><span class="sxs-lookup"><span data-stu-id="3a64e-191">When working with web workers or service workers, choose on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="3a64e-192">蓝色箭头图标表示当前选定的上下文。</span><span class="sxs-lookup"><span data-stu-id="3a64e-192">The blue arrow icon represents which context is currently selected.</span></span>  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="线程窗格" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   <span data-ttu-id="3a64e-194">“**线程**”窗格</span><span class="sxs-lookup"><span data-stu-id="3a64e-194">The **Threads** pane</span></span>  
:::image-end:::  

<span data-ttu-id="3a64e-195">例如，你在主脚本和服务工作进程脚本的断点上暂停。</span><span class="sxs-lookup"><span data-stu-id="3a64e-195">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="3a64e-196">您希望查看服务工作器上下文的本地和全局属性，但 **Sources** 工具显示主脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="3a64e-196">You want to view the local and global properties for the service worker context, but the **Sources** tool is showing the main script context.</span></span>  <span data-ttu-id="3a64e-197">若要切换到服务工作器上下文，在" **线程** "窗格中，选择服务工作器条目。</span><span class="sxs-lookup"><span data-stu-id="3a64e-197">To switch to the service worker context, in the **Threads** pane, choose the service worker entry.</span></span>  

## <a name="view-and-edit-properties-and-variables"></a><span data-ttu-id="3a64e-198">查看和编辑属性和变量</span><span class="sxs-lookup"><span data-stu-id="3a64e-198">View and edit properties and variables</span></span>

<span data-ttu-id="3a64e-199">在代码行上暂停时，使用“**范围**”窗格查看和编辑本地、关闭和全局范围中的属性和变量的值。</span><span class="sxs-lookup"><span data-stu-id="3a64e-199">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="3a64e-200">双击某个属性值以更改该值。</span><span class="sxs-lookup"><span data-stu-id="3a64e-200">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="3a64e-201">不可枚举的属性显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="3a64e-201">Non-enumerable properties are greyed out.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="范围窗格" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   <span data-ttu-id="3a64e-203">“**范围**”窗格</span><span class="sxs-lookup"><span data-stu-id="3a64e-203">The **Scope** pane</span></span>  
:::image-end:::  

## <a name="watch-the-values-of-javascript-expressions"></a><span data-ttu-id="3a64e-204">观看 JavaScript 表达式的值</span><span class="sxs-lookup"><span data-stu-id="3a64e-204">Watch the values of JavaScript expressions</span></span>  

<span data-ttu-id="3a64e-205">使用“**监视**”窗格观察自定义表达式的值。</span><span class="sxs-lookup"><span data-stu-id="3a64e-205">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="3a64e-206">你可以观看任何有效的 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="3a64e-206">You can watch any valid JavaScript expression.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="监视窗格" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   <span data-ttu-id="3a64e-208">“**监视**”窗格</span><span class="sxs-lookup"><span data-stu-id="3a64e-208">The **Watch** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="3a64e-209">若要创建新的监视表达式，请选择"添加 **监视** 表达式 \ (![ 添加监视表达式 ](../media/add-expression-icon.msft.png) \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="3a64e-209">To create a new watch expression, select the **Add watch expression** \(![Add watch expression](../media/add-expression-icon.msft.png)\) button.</span></span>  
*   <span data-ttu-id="3a64e-210">若要刷新所有现有表达式的值，请选择"刷新 **\ (** ![ 刷新 ](../media/refresh-icon.msft.png) \) "按钮。</span><span class="sxs-lookup"><span data-stu-id="3a64e-210">To refresh the values of all existing expressions, select the **Refresh** \(![Refresh](../media/refresh-icon.msft.png)\) button.</span></span>  <span data-ttu-id="3a64e-211">逐步执行代码时，值将自动刷新。</span><span class="sxs-lookup"><span data-stu-id="3a64e-211">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="3a64e-212">若要删除监视表达式，请右键单击该表达式，然后选择"删除 **监视** 表达式 \ (![ 删除监视表达式 ](../media/delete-expression-icon.msft.png) \) "。</span><span class="sxs-lookup"><span data-stu-id="3a64e-212">To delete a watch expression, right-click the expression and then select **Delete watch expression** \(![Delete watch expression](../media/delete-expression-icon.msft.png)\).</span></span>  

## <a name="view-the-call-stack"></a><span data-ttu-id="3a64e-213">查看调用堆栈</span><span class="sxs-lookup"><span data-stu-id="3a64e-213">View the call stack</span></span>  

<span data-ttu-id="3a64e-214">在代码行上暂停时，使用“**调用堆叠**”窗格查看让你到达此点的调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="3a64e-214">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="3a64e-215">选择一个项以跳转到调用该函数的代码行。</span><span class="sxs-lookup"><span data-stu-id="3a64e-215">Choose an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="3a64e-216">蓝色箭头图标表示 DevTools 当前突出显示的函数。</span><span class="sxs-lookup"><span data-stu-id="3a64e-216">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="调用堆叠窗格" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   <span data-ttu-id="3a64e-218">“**调用堆叠**”窗格</span><span class="sxs-lookup"><span data-stu-id="3a64e-218">The **Call Stack** pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="3a64e-219">当未在代码行上暂停时，“**调用堆叠**”窗格为空。</span><span class="sxs-lookup"><span data-stu-id="3a64e-219">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <a name="copy-stack-trace"></a><span data-ttu-id="3a64e-220">复制堆叠跟踪</span><span class="sxs-lookup"><span data-stu-id="3a64e-220">Copy stack trace</span></span>  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="3a64e-221">若要将当前调用堆栈复制到剪贴板，请将鼠标悬停在"调用\*\*\*\* 堆栈"窗格中的任意位置，打开上下文菜单 \ (右键单击\) ，然后选择"复制堆栈跟踪 **"。**</span><span class="sxs-lookup"><span data-stu-id="3a64e-221">To copy the current call stack to the clipboard, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Copy stack trace**.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="选择复制堆叠跟踪" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   <span data-ttu-id="3a64e-223">选择“**复制堆叠跟踪**”</span><span class="sxs-lookup"><span data-stu-id="3a64e-223">Choose **Copy Stack Trace**</span></span>  
:::image-end:::  

<span data-ttu-id="3a64e-224">以下代码段是一个输出示例。</span><span class="sxs-lookup"><span data-stu-id="3a64e-224">The following code snippet is an example of the output.</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onChoose (get-started.js:15)
```  

## <a name="ignore-a-script-or-pattern-of-scripts"></a><span data-ttu-id="3a64e-225">忽略脚本或脚本模式</span><span class="sxs-lookup"><span data-stu-id="3a64e-225">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="3a64e-226">若你想要在调试时忽略该脚本，请将脚本标记为库代码。</span><span class="sxs-lookup"><span data-stu-id="3a64e-226">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="3a64e-227">被标记为库代码时，脚本会在“**调用堆叠**”窗格中被遮盖，且你在单步执行代码时绝不会单步执行脚本的函数。</span><span class="sxs-lookup"><span data-stu-id="3a64e-227">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="3a64e-228">例如，在下面的代码段中，行使用 `A` `lib` ，这是第三方库。</span><span class="sxs-lookup"><span data-stu-id="3a64e-228">For example, in the following code snippet, line `A` uses `lib`, which is a third-party library.</span></span>  <span data-ttu-id="3a64e-229">如果您确信正在调试的问题与该第三方库不相关，那么将脚本标记为库代码 **是有意义的**。</span><span class="sxs-lookup"><span data-stu-id="3a64e-229">If you are confident that the problem you are debugging is not related to that third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

### <a name="mark-a-script-as-library-code-from-the-editor-pane"></a><span data-ttu-id="3a64e-230">在编辑器窗格中将脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-230">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="3a64e-231">若要从编辑器窗格中**将脚本标记为\*\*\*\*库代码：**</span><span class="sxs-lookup"><span data-stu-id="3a64e-231">To mark a script as **Library code** from the **Editor** pane:</span></span>  

1.  <span data-ttu-id="3a64e-232">打开文件。</span><span class="sxs-lookup"><span data-stu-id="3a64e-232">Open the file.</span></span>  
1.  <span data-ttu-id="3a64e-233">将鼠标悬停在任意位置并打开上下文菜单 \(右键单击\)。</span><span class="sxs-lookup"><span data-stu-id="3a64e-233">Hover anywhere and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="3a64e-234">选择 **"添加脚本"忽略之前** (标记为**库代码的列表) 。**</span><span class="sxs-lookup"><span data-stu-id="3a64e-234">Choose **Add script to ignore list** (previously shown as **Mark as Library code**).</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="在编辑器窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       <span data-ttu-id="3a64e-236">从“**编辑器**”窗格中将脚本标记为**库代码**</span><span class="sxs-lookup"><span data-stu-id="3a64e-236">Mark a script as **Library code** from the **Editor** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-the-call-stack-pane"></a><span data-ttu-id="3a64e-237">从调用堆叠窗格中将脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-237">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="3a64e-238">若要从"调用堆栈 **"窗格中将** 脚本 **标记为库** 代码：</span><span class="sxs-lookup"><span data-stu-id="3a64e-238">To mark a script as **Library code** from the **Call Stack** pane:</span></span>  

1.  <span data-ttu-id="3a64e-239">将鼠标悬停在脚本的函数上，然后打开上下文菜单 \(右键单击\)。</span><span class="sxs-lookup"><span data-stu-id="3a64e-239">Hover on a function from the script and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="3a64e-240">选择 **"添加脚本"忽略之前** (标记为**库代码的列表) 。**</span><span class="sxs-lookup"><span data-stu-id="3a64e-240">Choose **Add script to ignore list** (previously shown as **Mark as Library code**).</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="从调用堆叠窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       <span data-ttu-id="3a64e-242">从**调用堆叠**窗格中将脚本标记为**库代码**</span><span class="sxs-lookup"><span data-stu-id="3a64e-242">Mark a script as **Library code** from the **Call Stack** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-settings"></a><span data-ttu-id="3a64e-243">在设置中将脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="3a64e-243">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="3a64e-244">若要标记脚本的单个脚本或脚本模式 **，设置：**</span><span class="sxs-lookup"><span data-stu-id="3a64e-244">To mark a single script or pattern of scripts from **Settings**:</span></span>  

1.  <span data-ttu-id="3a64e-245">打开“[设置][DevToolsCustomize]”。</span><span class="sxs-lookup"><span data-stu-id="3a64e-245">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="3a64e-246">导航到“**库代码**”设置。</span><span class="sxs-lookup"><span data-stu-id="3a64e-246">Navigate to the **Library code** setting.</span></span>  
1.  <span data-ttu-id="3a64e-247">选择“**添加模式**”。</span><span class="sxs-lookup"><span data-stu-id="3a64e-247">Choose **Add pattern**.</span></span>  
1.  <span data-ttu-id="3a64e-248">输入脚本名称或脚本名称的正则表达式模式，以标记为**库代码**。</span><span class="sxs-lookup"><span data-stu-id="3a64e-248">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="3a64e-249">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="3a64e-249">Choose **Add**.</span></span>  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="在设置中将脚本标记为库代码" lightbox="../media/javascript-framework-library-code.msft.png":::
       <span data-ttu-id="3a64e-251">在“**设置**”中将脚本标记为**库代码**</span><span class="sxs-lookup"><span data-stu-id="3a64e-251">Mark a script as **Library code** from **Settings**</span></span>  
    :::image-end:::  
    
## <a name="run-snippets-of-debug-code-from-any-page"></a><span data-ttu-id="3a64e-252">从任何页面运行调试代码的代码段</span><span class="sxs-lookup"><span data-stu-id="3a64e-252">Run snippets of debug code from any page</span></span>  

<span data-ttu-id="3a64e-253">如果你的控制台一次又一次地运行相同的调试代码，请考虑使用代码段。</span><span class="sxs-lookup"><span data-stu-id="3a64e-253">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="3a64e-254">代码段是你在 DevTools 中创作、存储和运行的运行时脚本。</span><span class="sxs-lookup"><span data-stu-id="3a64e-254">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="3a64e-255">请参阅 [在任何网页上运行 JavaScript 代码段][DevToolsJavascriptSnippets]。</span><span class="sxs-lookup"><span data-stu-id="3a64e-255">See [Run snippets of JavaScript on any webpage][DevToolsJavascriptSnippets].</span></span>  

## <a name="see-also"></a><span data-ttu-id="3a64e-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a64e-256">See also</span></span>  

*   <span data-ttu-id="3a64e-257">[入门调试 JavaScript 在 Microsoft Edge DevTools][DevToolsJavascriptGetStarted] - 使用现有代码的简单简短教程，包含屏幕捕获。</span><span class="sxs-lookup"><span data-stu-id="3a64e-257">[Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] - A simple, short tutorial using existing code, with screen captures.</span></span>
*   <span data-ttu-id="3a64e-258">[源工具概述][DevToolsSourcesIndex] - **源工具** 包括 JavaScript 调试程序和编辑程序。</span><span class="sxs-lookup"><span data-stu-id="3a64e-258">[Sources tool overview][DevToolsSourcesIndex] - The **Sources** tool includes the JavaScript debugger and editor.</span></span>
*   <span data-ttu-id="3a64e-259">[使用 DevTools Microsoft Edge JavaScript。][DevToolsJavascriptDisable]</span><span class="sxs-lookup"><span data-stu-id="3a64e-259">[Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3a64e-260">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="3a64e-260">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools 中用断点暂停代码 | Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "使用 Microsoft Edge DevTools 工具禁用 JavaScript | Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "在 Microsoft Edge 开发人员工具中调试 JavaScript 入门 | Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "使用 Microsoft Edge DevTools 工具在任意页面上运行 JavaScript | Microsoft Docs"  
[DevToolsSourcesIndex]: ../sources/index.md "源工具概述 | Microsoft Docs"  
[DevToolsCustomize]: ../customize/index.md "自定义 Microsoft Edge DevTools | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="3a64e-267">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3a64e-267">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3a64e-268">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="3a64e-268">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3a64e-270">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3a64e-270">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
