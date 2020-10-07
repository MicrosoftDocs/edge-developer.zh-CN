---
description: Learn how to run JavaScript in the Console.
title: Get Started With Running JavaScript In The Console
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: d31bcfbdf728e656c9a6fff882f939f8c24cd897
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993119"
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







# <span data-ttu-id="7720f-104">Get Started With Running JavaScript In The Console</span><span class="sxs-lookup"><span data-stu-id="7720f-104">Get Started With Running JavaScript In The Console</span></span>   



<span data-ttu-id="7720f-105">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span><span class="sxs-lookup"><span data-stu-id="7720f-105">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="7720f-106">For more information about how to log messages to the **Console**, see [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span><span class="sxs-lookup"><span data-stu-id="7720f-106">For more information about how to log messages to the **Console**, see [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="7720f-107">For more information about how to pause JavaScript code and step through it one line at a time, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span><span class="sxs-lookup"><span data-stu-id="7720f-107">For more information about how to pause JavaScript code and step through it one line at a time, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="The Console" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   <span data-ttu-id="7720f-109">The **Console**</span><span class="sxs-lookup"><span data-stu-id="7720f-109">The **Console**</span></span>  
:::image-end:::  

## <span data-ttu-id="7720f-110">Overview</span><span class="sxs-lookup"><span data-stu-id="7720f-110">Overview</span></span>   

<span data-ttu-id="7720f-111">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span><span class="sxs-lookup"><span data-stu-id="7720f-111">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="7720f-112">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span><span class="sxs-lookup"><span data-stu-id="7720f-112">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <span data-ttu-id="7720f-113">Set up DevTools</span><span class="sxs-lookup"><span data-stu-id="7720f-113">Set up DevTools</span></span>   

<span data-ttu-id="7720f-114">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span><span class="sxs-lookup"><span data-stu-id="7720f-114">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="7720f-115">When you physically follow along, you are more likely to remember the workflows later.</span><span class="sxs-lookup"><span data-stu-id="7720f-115">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="7720f-116">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span><span class="sxs-lookup"><span data-stu-id="7720f-116">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="7720f-117">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Javascript Example** to open in a new window.</span><span class="sxs-lookup"><span data-stu-id="7720f-117">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Javascript Example** to open in a new window.</span></span>  
    
    *   [<span data-ttu-id="7720f-118">Console Javascript Example</span><span class="sxs-lookup"><span data-stu-id="7720f-118">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="The Console" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       <span data-ttu-id="7720f-120">The Console JavaScript Example page on the left, and DevTools on the right</span><span class="sxs-lookup"><span data-stu-id="7720f-120">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="7720f-121">View and change the JavaScript or DOM of the page</span><span class="sxs-lookup"><span data-stu-id="7720f-121">View and change the JavaScript or DOM of the page</span></span>   

<span data-ttu-id="7720f-122">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span><span class="sxs-lookup"><span data-stu-id="7720f-122">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="7720f-123">Notice the text in the button.</span><span class="sxs-lookup"><span data-stu-id="7720f-123">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="7720f-124">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then press `Enter` to evaluate the expression.</span><span class="sxs-lookup"><span data-stu-id="7720f-124">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then press `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="7720f-125">Notice how the text inside the button changes.</span><span class="sxs-lookup"><span data-stu-id="7720f-125">Notice how the text inside the button changes.</span></span>  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="The Console" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       <span data-ttu-id="7720f-127">How the **Console** looks after evaluating the expression</span><span class="sxs-lookup"><span data-stu-id="7720f-127">How the **Console** looks after evaluating the expression</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="7720f-128">Below the code that you evaluated you see `"Hello, Console!"`.</span><span class="sxs-lookup"><span data-stu-id="7720f-128">Below the code that you evaluated you see `"Hello, Console!"`.</span></span>  <span data-ttu-id="7720f-129">Recall the 4 steps of REPL: read, evaluate, print, loop.</span><span class="sxs-lookup"><span data-stu-id="7720f-129">Recall the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="7720f-130">After evaluating your code, a REPL prints the result of the expression.</span><span class="sxs-lookup"><span data-stu-id="7720f-130">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="7720f-131">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span><span class="sxs-lookup"><span data-stu-id="7720f-131">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <span data-ttu-id="7720f-132">Run arbitrary JavaScript that is not related to the page</span><span class="sxs-lookup"><span data-stu-id="7720f-132">Run arbitrary JavaScript that is not related to the page</span></span>   

<span data-ttu-id="7720f-133">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span><span class="sxs-lookup"><span data-stu-id="7720f-133">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="7720f-134">The Console is a perfect place for these kinds of experiments.</span><span class="sxs-lookup"><span data-stu-id="7720f-134">The Console is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="7720f-135">Type `5 + 15` in the Console and press `Enter` to evaluate the expression.</span><span class="sxs-lookup"><span data-stu-id="7720f-135">Type `5 + 15` in the Console and press `Enter` to evaluate the expression.</span></span> <span data-ttu-id="7720f-136">The Console prints out the result of the expression below your code.</span><span class="sxs-lookup"><span data-stu-id="7720f-136">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="7720f-137">In the following figure, your **Console** should display the result after evaluating the expression.</span><span class="sxs-lookup"><span data-stu-id="7720f-137">In the following figure, your **Console** should display the result after evaluating the expression.</span></span>  

1.  <span data-ttu-id="7720f-138">Type the following code into the **Console**.</span><span class="sxs-lookup"><span data-stu-id="7720f-138">Type the following code into the **Console**.</span></span>  <span data-ttu-id="7720f-139">Try typing it out, character-by-character, rather than copy-pasting it.</span><span class="sxs-lookup"><span data-stu-id="7720f-139">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20) { return a + b; }
    ```  
    
    <span data-ttu-id="7720f-140">If you are unfamiliar with the `b=20` syntax, see [define default values for function arguments][Esma6DefaultParameterValues].</span><span class="sxs-lookup"><span data-stu-id="7720f-140">If you are unfamiliar with the `b=20` syntax, see [define default values for function arguments][Esma6DefaultParameterValues].</span></span>  
    
1.  <span data-ttu-id="7720f-141">Now, run the function that you just defined.</span><span class="sxs-lookup"><span data-stu-id="7720f-141">Now, run the function that you just defined.</span></span>  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="The Console" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             <span data-ttu-id="7720f-143">The **Console** displays after evaluating the expressions in the code snippet</span><span class="sxs-lookup"><span data-stu-id="7720f-143">The **Console** displays after evaluating the expressions in the code snippet</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` <span data-ttu-id="7720f-144">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span><span class="sxs-lookup"><span data-stu-id="7720f-144">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <span data-ttu-id="7720f-145">Next steps</span><span class="sxs-lookup"><span data-stu-id="7720f-145">Next steps</span></span>   

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="7720f-146">DevTools lets you pause a script in the middle of running.</span><span class="sxs-lookup"><span data-stu-id="7720f-146">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="7720f-147">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span><span class="sxs-lookup"><span data-stu-id="7720f-147">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="7720f-148">The workflow makes for a powerful debugging workflow.</span><span class="sxs-lookup"><span data-stu-id="7720f-148">The workflow makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="7720f-149">For an interactive tutorial, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span><span class="sxs-lookup"><span data-stu-id="7720f-149">For an interactive tutorial, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

<span data-ttu-id="7720f-150">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span><span class="sxs-lookup"><span data-stu-id="7720f-150">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="7720f-151">For example:</span><span class="sxs-lookup"><span data-stu-id="7720f-151">For example:</span></span>  

*   <span data-ttu-id="7720f-152">Rather than typing `document.querySelector()` to select an element, type `$()`.</span><span class="sxs-lookup"><span data-stu-id="7720f-152">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="7720f-153">This syntax is inspired by jQuery, but it is not actually jQuery.</span><span class="sxs-lookup"><span data-stu-id="7720f-153">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="7720f-154">It is just an alias for `document.querySelector()`.</span><span class="sxs-lookup"><span data-stu-id="7720f-154">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="7720f-155">effectively sets a breakpoint on the first line of that function.</span><span class="sxs-lookup"><span data-stu-id="7720f-155">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="7720f-156">returns an array containing the keys of the specified object.</span><span class="sxs-lookup"><span data-stu-id="7720f-156">returns an array containing the keys of the specified object.</span></span>  

<!--See [Console Utilities API Reference][DevToolsConsoleUtilities] to explore all the convenience functions.  -->  

<!--todo: add console utilities api reference section when available  -->  

 



<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "Get started with logging messages in the Console | Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "Console reference | Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "Console Utilities API reference | Microsoft Docs"  
[DevToolsJavascriptIndex]: ../javascript/index.md "Get started with debugging JavaScript in Microsoft Edge DevTools"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "Expressions versus statements in JavaScript"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "Default Parameter Values - Extended Parameter Handling - ECMAScript 6 — New Features: Overview & Comparison"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "Console Javascript Example | Glitch"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "Read–eval–print loop - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="7720f-165">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="7720f-165">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7720f-166">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/javascript)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="7720f-166">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="7720f-168">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="7720f-168">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
