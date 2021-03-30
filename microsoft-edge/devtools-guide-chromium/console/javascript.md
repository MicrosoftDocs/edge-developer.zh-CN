---
description: 了解如何在控制台中运行 JavaScript。
title: 开始在控制台中运行 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: c1d6c393b6278f4622cf80576ccc8f9c70bdb6b5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398817"
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

# <a name="get-started-with-running-javascript-in-the-console"></a><span data-ttu-id="55dc8-104">开始在控制台中运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="55dc8-104">Get started with running JavaScript in the Console</span></span>  

<span data-ttu-id="55dc8-105">此交互式教程介绍如何在 Microsoft Edge DevTools 控制台中运行**JavaScript。**</span><span class="sxs-lookup"><span data-stu-id="55dc8-105">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="55dc8-106">若要详细了解如何将消息记录到**控制台**，请导航到"日志记录消息[入门"。][DevToolsConsoleLoggingMessages]</span><span class="sxs-lookup"><span data-stu-id="55dc8-106">For more information about how to log messages to the **Console**, navigate to [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="55dc8-107">若要详细了解如何暂停 JavaScript 代码并一次单行执行，请导航到"调试 [JavaScript][DevToolsJavascriptIndex]入门"。</span><span class="sxs-lookup"><span data-stu-id="55dc8-107">For more information about how to pause JavaScript code and step through it one line at a time, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   <span data-ttu-id="55dc8-109">**控制台**</span><span class="sxs-lookup"><span data-stu-id="55dc8-109">The **Console**</span></span>  
:::image-end:::  

## <a name="overview"></a><span data-ttu-id="55dc8-110">概述</span><span class="sxs-lookup"><span data-stu-id="55dc8-110">Overview</span></span>  

<span data-ttu-id="55dc8-111">控制台 **是** 一 [个 REPL，][WikiReadEvalPrintLoop]它代表读取、评估、打印和循环。</span><span class="sxs-lookup"><span data-stu-id="55dc8-111">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="55dc8-112">它读取您键入的 JavaScript，计算代码，输出表达式的结果，然后循环回第一步。 [][2alityExpressionsVersusStatements]</span><span class="sxs-lookup"><span data-stu-id="55dc8-112">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <a name="set-up-devtools"></a><span data-ttu-id="55dc8-113">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="55dc8-113">Set up DevTools</span></span>  

<span data-ttu-id="55dc8-114">本教程旨在让你打开演示并自己尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="55dc8-114">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="55dc8-115">当您实际跟进时，您以后更有可能记住工作流。</span><span class="sxs-lookup"><span data-stu-id="55dc8-115">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="55dc8-116">选择 `Control` + `Shift` + `J` \(Windows、Linux\) 或 `Command` + `Option` + `J` \(macOS\) 打开**控制台**。</span><span class="sxs-lookup"><span data-stu-id="55dc8-116">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="55dc8-117">按住 `Control` \(Windows、Linux\) 或 `Command` \(macOS\) ，然后选择控制台 **Javascript 示例** 以在一个新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="55dc8-117">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **Console Javascript Example** to open in a new window.</span></span>  
    
    *   [<span data-ttu-id="55dc8-118">控制台 Javascript 示例</span><span class="sxs-lookup"><span data-stu-id="55dc8-118">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="左侧的控制台 JavaScript 示例页面，右侧为 DevTools" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       <span data-ttu-id="55dc8-120">左侧的控制台 JavaScript 示例页面，右侧为 DevTools</span><span class="sxs-lookup"><span data-stu-id="55dc8-120">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
## <a name="view-and-change-the-javascript-or-dom-of-the-page"></a><span data-ttu-id="55dc8-121">查看和更改页面的 JavaScript 或 DOM</span><span class="sxs-lookup"><span data-stu-id="55dc8-121">View and change the JavaScript or DOM of the page</span></span>  

<span data-ttu-id="55dc8-122">生成或调试页面时，在控制台中运行语句以更改页面的外观或运行 方式通常很有用。</span><span class="sxs-lookup"><span data-stu-id="55dc8-122">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="55dc8-123">请注意按钮中的文本。</span><span class="sxs-lookup"><span data-stu-id="55dc8-123">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="55dc8-124">在 `document.getElementById('hello').textContent = 'Hello, Console!'` 控制台 **中键入** ，然后选择 `Enter` 计算表达式。</span><span class="sxs-lookup"><span data-stu-id="55dc8-124">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then select `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="55dc8-125">请注意按钮内的文本如何更改。</span><span class="sxs-lookup"><span data-stu-id="55dc8-125">Notice how the text inside the button changes.</span></span>  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="控制台在计算表达式后的外观" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       <span data-ttu-id="55dc8-127">控制台 **在** 计算表达式后的外观</span><span class="sxs-lookup"><span data-stu-id="55dc8-127">How the **Console** looks after evaluating the expression</span></span>  
    :::image-end:::  
    
    `"Hello, Console!"`<span data-ttu-id="55dc8-128">，显示在您评估的代码下方。</span><span class="sxs-lookup"><span data-stu-id="55dc8-128">, is displayed below the code that you evaluated.</span></span>  <span data-ttu-id="55dc8-129">请记住 REPL 的 4 个步骤：读取、评估、打印、循环。</span><span class="sxs-lookup"><span data-stu-id="55dc8-129">Remember the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="55dc8-130">计算代码后，REPL 将输出表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="55dc8-130">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="55dc8-131">因此 `"Hello, Console!"` ，必须是计算的结果 `document.getElementById('hello').textContent = 'Hello, Console!'` 。</span><span class="sxs-lookup"><span data-stu-id="55dc8-131">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <a name="run-arbitrary-javascript-that-is-not-related-to-the-page"></a><span data-ttu-id="55dc8-132">运行与页面不相关的任意 JavaScript</span><span class="sxs-lookup"><span data-stu-id="55dc8-132">Run arbitrary JavaScript that is not related to the page</span></span>  

<span data-ttu-id="55dc8-133">有时，你只需一个代码场，可以在其中测试某些代码，或尝试不熟悉的新 JavaScript 功能。</span><span class="sxs-lookup"><span data-stu-id="55dc8-133">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="55dc8-134">控制台 **是** 这些类型的实验的一个理想位置。</span><span class="sxs-lookup"><span data-stu-id="55dc8-134">The **Console** is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="55dc8-135">在 `5 + 15` 控制台中键入并选择 `Enter` 计算表达式。</span><span class="sxs-lookup"><span data-stu-id="55dc8-135">Type `5 + 15` in the Console and select `Enter` to evaluate the expression.</span></span> <span data-ttu-id="55dc8-136">控制台将输出代码下方的表达式结果。</span><span class="sxs-lookup"><span data-stu-id="55dc8-136">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="55dc8-137">下图中 **，控制台应在** 计算表达式后显示结果。</span><span class="sxs-lookup"><span data-stu-id="55dc8-137">In the following figure, your **Console** should display the result after evaluating the expression.</span></span>  

1.  <span data-ttu-id="55dc8-138">在控制台中键入以下 **代码**。</span><span class="sxs-lookup"><span data-stu-id="55dc8-138">Type the following code into the **Console**.</span></span>  <span data-ttu-id="55dc8-139">请尝试按字符键入它，而不是复制粘贴它。</span><span class="sxs-lookup"><span data-stu-id="55dc8-139">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20)
    ```  
    
    <span data-ttu-id="55dc8-140">如果您不熟悉语法， `b=20` 请导航以 [定义函数参数的默认值][Esma6DefaultParameterValues]。</span><span class="sxs-lookup"><span data-stu-id="55dc8-140">If you are unfamiliar with the `b=20` syntax, navigate to [define default values for function arguments][Esma6DefaultParameterValues].</span></span>  
    
1.  <span data-ttu-id="55dc8-141">现在，运行刚定义的函数。</span><span class="sxs-lookup"><span data-stu-id="55dc8-141">Now, run the function that you just defined.</span></span>  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="控制台在计算代码段中的表达式后显示" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             <span data-ttu-id="55dc8-143">控制台 **在** 计算代码段中的表达式后显示</span><span class="sxs-lookup"><span data-stu-id="55dc8-143">The **Console** displays after evaluating the expressions in the code snippet</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` <span data-ttu-id="55dc8-144">计算结果为，因为在没有第二个参数的情况下调用函数 `45` `add` `b` 时，默认为 `20` 。</span><span class="sxs-lookup"><span data-stu-id="55dc8-144">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="55dc8-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="55dc8-145">Next steps</span></span>  

<!--To explore more features related to running JavaScript in the **Console**, navigate to [Run JavaScript][DevToolsConsoleReference].  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="55dc8-146">DevTools 允许你在运行过程中暂停脚本。</span><span class="sxs-lookup"><span data-stu-id="55dc8-146">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="55dc8-147">暂停时，可以使用控制台在此时查看和更改 页面 `window` `DOM` 或页面。</span><span class="sxs-lookup"><span data-stu-id="55dc8-147">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="55dc8-148">工作流可创建功能强大的调试工作流。</span><span class="sxs-lookup"><span data-stu-id="55dc8-148">The workflow makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="55dc8-149">对于交互式教程，导航到["调试 JavaScript 入门"。][DevToolsJavascriptIndex]</span><span class="sxs-lookup"><span data-stu-id="55dc8-149">For an interactive tutorial, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

<span data-ttu-id="55dc8-150">控制台 **还** 具有一组方便功能，可更轻松地与页面进行交互。</span><span class="sxs-lookup"><span data-stu-id="55dc8-150">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="55dc8-151">例如：</span><span class="sxs-lookup"><span data-stu-id="55dc8-151">For example:</span></span>  

*   <span data-ttu-id="55dc8-152">键入 ，而不是键入 `document.querySelector()` 以选择元素 `$()` 。</span><span class="sxs-lookup"><span data-stu-id="55dc8-152">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="55dc8-153">此语法受 jQuery 启发，但实际上并不是 jQuery。</span><span class="sxs-lookup"><span data-stu-id="55dc8-153">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="55dc8-154">它只是一个别名 `document.querySelector()` 。</span><span class="sxs-lookup"><span data-stu-id="55dc8-154">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="55dc8-155">有效设置该函数的第一行上的断点。</span><span class="sxs-lookup"><span data-stu-id="55dc8-155">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="55dc8-156">返回包含指定对象的键的数组。</span><span class="sxs-lookup"><span data-stu-id="55dc8-156">returns an array containing the keys of the specified object.</span></span>  

<span data-ttu-id="55dc8-157">有关便利函数详细信息，请导航到 [控制台实用工具 API 参考][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="55dc8-157">For more information about the convenience functions, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="55dc8-158">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="55dc8-158">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "开始在控制台中记录|Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "控制台参考|Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "控制台实用工具 API 参考|Microsoft Docs"  
[DevToolsJavascriptIndex]: ../javascript/index.md "开始在 Microsoft Edge DevTools |Microsoft Docs"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript 中的表达式与语句"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "默认参数值 - 扩展参数处理 - ECMAScript 6 — 新功能：概述&比较"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "控制台 Javascript 示例|小故障"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "Read-eval–print 循环 - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="55dc8-167">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="55dc8-167">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="55dc8-168">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/javascript)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="55dc8-168">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="55dc8-170">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="55dc8-170">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
