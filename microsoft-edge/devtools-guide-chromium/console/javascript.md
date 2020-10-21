---
description: 了解如何在控制台中运行 JavaScript。
title: 开始在控制台中运行 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 6537cb07b52ef6b8be4b1ea7d9420bf2307d3fd5
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125242"
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

# <span data-ttu-id="be285-104">开始在控制台中运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="be285-104">Get Started With Running JavaScript In The Console</span></span>  

<span data-ttu-id="be285-105">此交互式教程介绍如何在 Microsoft Edge DevTools **控制台**中运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="be285-105">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="be285-106">有关如何将消息记录到 **控制台**的详细信息，请导航到 [记录消息的入门][DevToolsConsoleLoggingMessages]。</span><span class="sxs-lookup"><span data-stu-id="be285-106">For more information about how to log messages to the **Console**, navigate to [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="be285-107">有关如何暂停 JavaScript 代码并逐行执行一行的详细信息，请导航到 [开始使用调试 JavaScript][DevToolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="be285-107">For more information about how to pause JavaScript code and step through it one line at a time, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="该控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   <span data-ttu-id="be285-109">该 **控制台**</span><span class="sxs-lookup"><span data-stu-id="be285-109">The **Console**</span></span>  
:::image-end:::  

## <span data-ttu-id="be285-110">概述</span><span class="sxs-lookup"><span data-stu-id="be285-110">Overview</span></span>  

<span data-ttu-id="be285-111">该 **控制台** 是一个 [复制][WikiReadEvalPrintLoop]，它代表读取、计算、打印和循环。</span><span class="sxs-lookup"><span data-stu-id="be285-111">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="be285-112">它将读取你在其中键入的 JavaScript，计算你的代码，打印你的 [表达式][2alityExpressionsVersusStatements]的结果，然后循环回到第一步。</span><span class="sxs-lookup"><span data-stu-id="be285-112">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <span data-ttu-id="be285-113">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="be285-113">Set up DevTools</span></span>  

<span data-ttu-id="be285-114">本教程旨在让你打开演示并自行尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="be285-114">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="be285-115">当您进行物理跟踪时，更有可能会在以后记忆工作流。</span><span class="sxs-lookup"><span data-stu-id="be285-115">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="be285-116">选择 `Control` + `Shift` + `J` \ (Windows、Linux \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 以打开**控制台**。</span><span class="sxs-lookup"><span data-stu-id="be285-116">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="be285-117">保留 `Control` \ (Windows、Linux \ ) 或 `Command` \ (macOS \ ) 并选择 "要在新窗口中打开的 **控制台 Javascript 示例** "。</span><span class="sxs-lookup"><span data-stu-id="be285-117">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **Console Javascript Example** to open in a new window.</span></span>  
    
    *   [<span data-ttu-id="be285-118">控制台 Javascript 示例</span><span class="sxs-lookup"><span data-stu-id="be285-118">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="该控制台" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       <span data-ttu-id="be285-120">控制台 JavaScript 示例页面位于左侧，DevTools 在右侧</span><span class="sxs-lookup"><span data-stu-id="be285-120">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="be285-121">查看和更改页面的 JavaScript 或 DOM</span><span class="sxs-lookup"><span data-stu-id="be285-121">View and change the JavaScript or DOM of the page</span></span>  

<span data-ttu-id="be285-122">生成或调试页面时，在 **控制台** 中运行语句以更改页面的外观和运行方式通常很有用。</span><span class="sxs-lookup"><span data-stu-id="be285-122">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="be285-123">注意按钮中的文本。</span><span class="sxs-lookup"><span data-stu-id="be285-123">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="be285-124">`document.getElementById('hello').textContent = 'Hello, Console!'`在**控制台**中键入，然后选择 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="be285-124">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then select `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="be285-125">注意按钮内的文本如何更改。</span><span class="sxs-lookup"><span data-stu-id="be285-125">Notice how the text inside the button changes.</span></span>  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="该控制台" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       <span data-ttu-id="be285-127">计算表达式后的 **控制台** 外观</span><span class="sxs-lookup"><span data-stu-id="be285-127">How the **Console** looks after evaluating the expression</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="be285-128">在你所评估的代码下方看到 `"Hello, Console!"` 。</span><span class="sxs-lookup"><span data-stu-id="be285-128">Below the code that you evaluated you see `"Hello, Console!"`.</span></span>  <span data-ttu-id="be285-129">撤回复制操作的4个步骤：读取、评估、打印、循环。</span><span class="sxs-lookup"><span data-stu-id="be285-129">Recall the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="be285-130">在计算代码后，复制将打印表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="be285-130">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="be285-131">因此 `"Hello, Console!"` 必须是评估结果 `document.getElementById('hello').textContent = 'Hello, Console!'` 。</span><span class="sxs-lookup"><span data-stu-id="be285-131">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <span data-ttu-id="be285-132">运行与页面无关的任意 JavaScript</span><span class="sxs-lookup"><span data-stu-id="be285-132">Run arbitrary JavaScript that is not related to the page</span></span>  

<span data-ttu-id="be285-133">有时，你只需要一个代码背景，你可以在其中测试某些代码，或者尝试你不熟悉的新 JavaScript 功能。</span><span class="sxs-lookup"><span data-stu-id="be285-133">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="be285-134">控制台是这些类型的实验的理想位置。</span><span class="sxs-lookup"><span data-stu-id="be285-134">The Console is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="be285-135">`5 + 15`在控制台中键入，然后选择 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="be285-135">Type `5 + 15` in the Console and select `Enter` to evaluate the expression.</span></span> <span data-ttu-id="be285-136">该控制台将打印出你的代码下方的表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="be285-136">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="be285-137">在下图中，你的 **控制台** 应在计算表达式后显示结果。</span><span class="sxs-lookup"><span data-stu-id="be285-137">In the following figure, your **Console** should display the result after evaluating the expression.</span></span>  

1.  <span data-ttu-id="be285-138">在 **控制台**中键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="be285-138">Type the following code into the **Console**.</span></span>  <span data-ttu-id="be285-139">尝试按字符键入，而不是复制粘贴。</span><span class="sxs-lookup"><span data-stu-id="be285-139">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20)
    ```  
    
    <span data-ttu-id="be285-140">如果不熟悉 `b=20` 语法，请导航以 [定义函数参数的默认值][Esma6DefaultParameterValues]。</span><span class="sxs-lookup"><span data-stu-id="be285-140">If you are unfamiliar with the `b=20` syntax, navigate to [define default values for function arguments][Esma6DefaultParameterValues].</span></span>  
    
1.  <span data-ttu-id="be285-141">现在，运行刚定义的函数。</span><span class="sxs-lookup"><span data-stu-id="be285-141">Now, run the function that you just defined.</span></span>  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="该控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             <span data-ttu-id="be285-143">在计算代码段中的表达式后，将显示该**控制台**</span><span class="sxs-lookup"><span data-stu-id="be285-143">The **Console** displays after evaluating the expressions in the code snippet</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` <span data-ttu-id="be285-144">计算结果为 `45` ：当 `add` 调用函数时不带第二个参数时， `b` 默认为 `20` 。</span><span class="sxs-lookup"><span data-stu-id="be285-144">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <span data-ttu-id="be285-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="be285-145">Next steps</span></span>  

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="be285-146">DevTools 允许你在运行期间暂停脚本。</span><span class="sxs-lookup"><span data-stu-id="be285-146">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="be285-147">暂停时，您可以使用该 **控制台** 查看和更改 `window` `DOM` 该时刻的页面或页面。</span><span class="sxs-lookup"><span data-stu-id="be285-147">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="be285-148">工作流可用于功能强大的调试工作流。</span><span class="sxs-lookup"><span data-stu-id="be285-148">The workflow makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="be285-149">对于交互式教程，请导航到 [开始使用调试 JavaScript][DevToolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="be285-149">For an interactive tutorial, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

<span data-ttu-id="be285-150">该 **控制台** 还具有一组便利功能，使您能够更轻松地与页面交互。</span><span class="sxs-lookup"><span data-stu-id="be285-150">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="be285-151">例如：</span><span class="sxs-lookup"><span data-stu-id="be285-151">For example:</span></span>  

*   <span data-ttu-id="be285-152">键入，而不是键入 `document.querySelector()` 来选择元素 `$()` 。</span><span class="sxs-lookup"><span data-stu-id="be285-152">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="be285-153">此语法是 jQuery 的灵感，但实际上并不是 jQuery。</span><span class="sxs-lookup"><span data-stu-id="be285-153">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="be285-154">它只是的一个别名 `document.querySelector()` 。</span><span class="sxs-lookup"><span data-stu-id="be285-154">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="be285-155">在该函数的第一行上有效地设置断点。</span><span class="sxs-lookup"><span data-stu-id="be285-155">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="be285-156">返回包含指定对象的键的数组。</span><span class="sxs-lookup"><span data-stu-id="be285-156">returns an array containing the keys of the specified object.</span></span>  

<span data-ttu-id="be285-157">有关便利函数的详细信息，请导航到 [控制台实用工具 API 参考][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="be285-157">For more information about the convenience functions, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="be285-158">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="be285-158">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

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
> <span data-ttu-id="be285-167">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="be285-167">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="be285-168">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/javascript)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="be285-168">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="be285-170">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="be285-170">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
