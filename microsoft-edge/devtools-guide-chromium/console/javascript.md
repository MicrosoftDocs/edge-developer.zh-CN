---
title: 开始在控制台中运行 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 7e91d9844b2926bc8302331c6b9d971922d27ea3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982250"
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







# <span data-ttu-id="9b913-103">开始在控制台中运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="9b913-103">Get Started With Running JavaScript In The Console</span></span>   



<span data-ttu-id="9b913-104">此交互式教程介绍如何在 Microsoft Edge DevTools **控制台**中运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="9b913-104">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="9b913-105">有关如何将消息记录到 **控制台**的详细信息，请参阅 [记录消息入门][DevToolsConsoleLoggingMessages]。</span><span class="sxs-lookup"><span data-stu-id="9b913-105">For more information about how to log messages to the **Console**, see [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="9b913-106">有关如何暂停 JavaScript 代码并一次单步执行一行的详细信息，请参阅 [开始使用调试 JavaScript][DevToolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="9b913-106">For more information about how to pause JavaScript code and step through it one line at a time, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="该控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   <span data-ttu-id="9b913-108">该 **控制台**</span><span class="sxs-lookup"><span data-stu-id="9b913-108">The **Console**</span></span>  
:::image-end:::  

## <span data-ttu-id="9b913-109">概述</span><span class="sxs-lookup"><span data-stu-id="9b913-109">Overview</span></span>   

<span data-ttu-id="9b913-110">该 **控制台** 是一个 [复制][WikiReadEvalPrintLoop]，它代表读取、计算、打印和循环。</span><span class="sxs-lookup"><span data-stu-id="9b913-110">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="9b913-111">它将读取你在其中键入的 JavaScript，计算你的代码，打印你的 [表达式][2alityExpressionsVersusStatements]的结果，然后循环回到第一步。</span><span class="sxs-lookup"><span data-stu-id="9b913-111">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <span data-ttu-id="9b913-112">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="9b913-112">Set up DevTools</span></span>   

<span data-ttu-id="9b913-113">本教程旨在让你打开演示并自行尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="9b913-113">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="9b913-114">当您进行物理跟踪时，更有可能会在以后记忆工作流。</span><span class="sxs-lookup"><span data-stu-id="9b913-114">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="9b913-115">按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开**控制台**。</span><span class="sxs-lookup"><span data-stu-id="9b913-115">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="9b913-116">保留 `Control` \ (Windows \ ) 或 `Command` \ (macOS \ ) ，然后单击 " **Console Javascript 示例** " 以在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="9b913-116">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Javascript Example** to open in a new window.</span></span>  
    
    *   [<span data-ttu-id="9b913-117">控制台 Javascript 示例</span><span class="sxs-lookup"><span data-stu-id="9b913-117">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="控制台 JavaScript 示例页面位于左侧，DevTools 在右侧" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       <span data-ttu-id="9b913-119">控制台 JavaScript 示例页面位于左侧，DevTools 在右侧</span><span class="sxs-lookup"><span data-stu-id="9b913-119">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9b913-120">查看和更改页面的 JavaScript 或 DOM</span><span class="sxs-lookup"><span data-stu-id="9b913-120">View and change the JavaScript or DOM of the page</span></span>   

<span data-ttu-id="9b913-121">生成或调试页面时，在 **控制台** 中运行语句以更改页面的外观和运行方式通常很有用。</span><span class="sxs-lookup"><span data-stu-id="9b913-121">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="9b913-122">注意按钮中的文本。</span><span class="sxs-lookup"><span data-stu-id="9b913-122">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="9b913-123">`document.getElementById('hello').textContent = 'Hello, Console!'`在**控制台**中键入，然后按 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="9b913-123">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then press `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="9b913-124">注意按钮内的文本如何更改。</span><span class="sxs-lookup"><span data-stu-id="9b913-124">Notice how the text inside the button changes.</span></span>  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="计算表达式后的控制台外观" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       <span data-ttu-id="9b913-126">计算表达式后的 **控制台** 外观</span><span class="sxs-lookup"><span data-stu-id="9b913-126">How the **Console** looks after evaluating the expression</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9b913-127">在你所评估的代码下方看到 `"Hello, Console!"` 。</span><span class="sxs-lookup"><span data-stu-id="9b913-127">Below the code that you evaluated you see `"Hello, Console!"`.</span></span>  <span data-ttu-id="9b913-128">撤回复制操作的4个步骤：读取、评估、打印、循环。</span><span class="sxs-lookup"><span data-stu-id="9b913-128">Recall the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="9b913-129">在计算代码后，复制将打印表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="9b913-129">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="9b913-130">因此 `"Hello, Console!"` 必须是评估结果 `document.getElementById('hello').textContent = 'Hello, Console!'` 。</span><span class="sxs-lookup"><span data-stu-id="9b913-130">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <span data-ttu-id="9b913-131">运行与页面无关的任意 JavaScript</span><span class="sxs-lookup"><span data-stu-id="9b913-131">Run arbitrary JavaScript that is not related to the page</span></span>   

<span data-ttu-id="9b913-132">有时，你只需要一个代码背景，你可以在其中测试某些代码，或者尝试你不熟悉的新 JavaScript 功能。</span><span class="sxs-lookup"><span data-stu-id="9b913-132">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="9b913-133">控制台是这些类型的实验的理想位置。</span><span class="sxs-lookup"><span data-stu-id="9b913-133">The Console is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="9b913-134">`5 + 15`在控制台中键入，然后按 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="9b913-134">Type `5 + 15` in the Console and press `Enter` to evaluate the expression.</span></span> <span data-ttu-id="9b913-135">该控制台将打印出你的代码下方的表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="9b913-135">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="9b913-136">在下图中，你的 **控制台** 应在计算表达式后显示结果。</span><span class="sxs-lookup"><span data-stu-id="9b913-136">In the following figure, your **Console** should display the result after evaluating the expression.</span></span>  

1.  <span data-ttu-id="9b913-137">在 **控制台**中键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="9b913-137">Type the following code into the **Console**.</span></span>  <span data-ttu-id="9b913-138">尝试按字符键入，而不是复制粘贴。</span><span class="sxs-lookup"><span data-stu-id="9b913-138">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20) { return a + b; }
    ```  
    
    <span data-ttu-id="9b913-139">如果不熟悉 `b=20` 语法，请参阅 [定义函数参数的默认值][Esma6DefaultParameterValues]。</span><span class="sxs-lookup"><span data-stu-id="9b913-139">If you are unfamiliar with the `b=20` syntax, see [define default values for function arguments][Esma6DefaultParameterValues].</span></span>  
    
1.  <span data-ttu-id="9b913-140">现在，运行刚定义的函数。</span><span class="sxs-lookup"><span data-stu-id="9b913-140">Now, run the function that you just defined.</span></span>  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="在计算代码段中的表达式后，将显示该控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             <span data-ttu-id="9b913-142">在计算代码段中的表达式后，将显示该**控制台**</span><span class="sxs-lookup"><span data-stu-id="9b913-142">The **Console** displays after evaluating the expressions in the code snippet</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` <span data-ttu-id="9b913-143">计算结果为 `45` ：当 `add` 调用函数时不带第二个参数时， `b` 默认为 `20` 。</span><span class="sxs-lookup"><span data-stu-id="9b913-143">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <span data-ttu-id="9b913-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9b913-144">Next steps</span></span>   

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="9b913-145">DevTools 允许你在运行期间暂停脚本。</span><span class="sxs-lookup"><span data-stu-id="9b913-145">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="9b913-146">暂停时，您可以使用该 **控制台** 查看和更改 `window` `DOM` 该时刻的页面或页面。</span><span class="sxs-lookup"><span data-stu-id="9b913-146">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="9b913-147">工作流可用于功能强大的调试工作流。</span><span class="sxs-lookup"><span data-stu-id="9b913-147">The workflow makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="9b913-148">有关交互式教程，请参阅 [开始使用调试 JavaScript][DevToolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="9b913-148">For an interactive tutorial, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

<span data-ttu-id="9b913-149">该 **控制台** 还具有一组便利功能，使您能够更轻松地与页面交互。</span><span class="sxs-lookup"><span data-stu-id="9b913-149">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="9b913-150">例如：</span><span class="sxs-lookup"><span data-stu-id="9b913-150">For example:</span></span>  

*   <span data-ttu-id="9b913-151">键入，而不是键入 `document.querySelector()` 来选择元素 `$()` 。</span><span class="sxs-lookup"><span data-stu-id="9b913-151">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="9b913-152">此语法是 jQuery 的灵感，但实际上并不是 jQuery。</span><span class="sxs-lookup"><span data-stu-id="9b913-152">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="9b913-153">它只是的一个别名 `document.querySelector()` 。</span><span class="sxs-lookup"><span data-stu-id="9b913-153">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="9b913-154">在该函数的第一行上有效地设置断点。</span><span class="sxs-lookup"><span data-stu-id="9b913-154">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="9b913-155">返回包含指定对象的键的数组。</span><span class="sxs-lookup"><span data-stu-id="9b913-155">returns an array containing the keys of the specified object.</span></span>  

<!--See [Console Utilities API Reference][DevToolsConsoleUtilities] to explore all the convenience functions.  -->  

<!--todo: add console utilities api reference section when available  -->  

 



<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "在控制台中记录邮件的入门 |Microsoft 文档"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "控制台参考 |Microsoft 文档"  
[DevToolsConsoleUtilities]: ./utilities.md "控制台实用工具 API 参考 |Microsoft 文档"  
[DevToolsJavascriptIndex]: ../javascript/index.md "在 Microsoft Edge DevTools 中开始使用调试 JavaScript"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript 中的表达式和语句"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "默认参数值-扩展参数处理-ECMAScript 6 ——新功能：概述 & 比较"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "控制台 Javascript 示例 |故障"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "阅读-评估-"打印循环"-维基百科"  

> [!NOTE]
> <span data-ttu-id="9b913-164">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9b913-164">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9b913-165">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/javascript)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9b913-165">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9b913-167">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9b913-167">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
