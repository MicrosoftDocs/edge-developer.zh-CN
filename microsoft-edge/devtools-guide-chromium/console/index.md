---
description: Microsoft Edge 开发人员工具中的控制台工具简介。
title: 使用控制台
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3f2f8c01a9bc9c4f40158f0959ba5b60e03bfb80
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483183"
---
# <a name="use-the-console"></a><span data-ttu-id="53c37-104">使用控制台</span><span class="sxs-lookup"><span data-stu-id="53c37-104">Use the Console</span></span>  

<span data-ttu-id="53c37-105">DevTools 的控制台工具可帮助你完成多项任务。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53c37-105">The **Console** tool of the DevTools helps you with several tasks.</span></span>  <span data-ttu-id="53c37-106">以下列表包含一些任务。</span><span class="sxs-lookup"><span data-stu-id="53c37-106">The following list includes some of the tasks.</span></span>  

*   <span data-ttu-id="53c37-107">了解为什么某些内容在当前项目中无法工作， [并跟踪问题][DevtoolsConsoleConsoleDebugJavascript]。</span><span class="sxs-lookup"><span data-stu-id="53c37-107">Find out why something isn't working in the current project and [track down problems][DevtoolsConsoleConsoleDebugJavascript].</span></span>  
*   <span data-ttu-id="53c37-108">[以日志消息获取有关浏览器中][DevtoolsConsoleConsoleFilters] Web 项目的信息。</span><span class="sxs-lookup"><span data-stu-id="53c37-108">[Get information about the web project][DevtoolsConsoleConsoleFilters] in the browser as log messages.</span></span>  
*   <span data-ttu-id="53c37-109">[将信息][DevtoolsConsoleConsoleLog] 记录在脚本中以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="53c37-109">[Log information][DevtoolsConsoleConsoleLog] in scripts for debugging purposes.</span></span>  
*   <span data-ttu-id="53c37-110">[尝试 JavaScript 表达式][DevtoolsConsoleConsoleJavascript] 在 [REPL 环境中][WikiReadEvalPrintLoop] 活动。</span><span class="sxs-lookup"><span data-stu-id="53c37-110">[Try JavaScript expressions][DevtoolsConsoleConsoleJavascript] live in a [REPL][WikiReadEvalPrintLoop] environment.</span></span>  
*   <span data-ttu-id="53c37-111">使用 JavaScript[与浏览器中][DevtoolsConsoleConsoleDomInteraction]的 Web 项目交互。</span><span class="sxs-lookup"><span data-stu-id="53c37-111">[Interact with the web project in the browser][DevtoolsConsoleConsoleDomInteraction] using JavaScript.</span></span>  
    
<span data-ttu-id="53c37-112">控制台 **是** 一款很好的配套工具，可用于其他工具。</span><span class="sxs-lookup"><span data-stu-id="53c37-112">The **Console** is a great companion tool to use with others tools.</span></span>  <span data-ttu-id="53c37-113">控制台 **提供了** 一种使用 JavaScript 编写功能、检查和处理当前网页的功能强大的方法。</span><span class="sxs-lookup"><span data-stu-id="53c37-113">The **Console** provides a powerful way to script functionality, inspect, and manipulate the current webpage using JavaScript.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-main.msft.png" alt-text="控制台工具在上方面板中打开" lightbox="../media/console-intro-console-main.msft.png":::
         <span data-ttu-id="53c37-115">控制台 **工具** 在上方面板中打开</span><span class="sxs-lookup"><span data-stu-id="53c37-115">The **Console** tool open in the upper panel</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-panel.msft.png" alt-text="下面板中的控制台，其上方打开"元素"工具" lightbox="../media/console-intro-console-panel.msft.png":::
         <span data-ttu-id="53c37-117">**下** 面板中的控制台，其上方打开 **"元素** "工具</span><span class="sxs-lookup"><span data-stu-id="53c37-117">**Console** in the lower panel with the **Elements** tool open above it</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="53c37-118">直接打开控制台的最快方法为选择\*\*\*\* `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="53c37-118">The fastest way to directly open the **Console** is to select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

## <a name="error-reports-and-console"></a><span data-ttu-id="53c37-119">错误报告和控制台</span><span class="sxs-lookup"><span data-stu-id="53c37-119">Error reports and Console</span></span>  

<span data-ttu-id="53c37-120">**控制台** 是报告 JavaScript 和连接错误的默认位置。</span><span class="sxs-lookup"><span data-stu-id="53c37-120">**Console** is the default place where JavaScript and connectivity errors are reported.</span></span>  <span data-ttu-id="53c37-121">如果发生任何错误，DevTools 中的\*\*\*\*"设置"图标旁边会显示一个按钮，该按钮提供错误和警告的数量。</span><span class="sxs-lookup"><span data-stu-id="53c37-121">If any errors occur, a button displays next to the **Settings** icon in DevTools that provides the number of errors and warnings.</span></span>  <span data-ttu-id="53c37-122">选择它以打开 **控制台** 并显示问题。</span><span class="sxs-lookup"><span data-stu-id="53c37-122">Choose it to open the **Console** and display the problem.</span></span>  <span data-ttu-id="53c37-123">有关详细信息，请导航到"[控制台"中报告的"调试错误"。][DevtoolsConsoleConsoleDebugJavascript]</span><span class="sxs-lookup"><span data-stu-id="53c37-123">For more information, navigate to [Debug errors reported in Console][DevtoolsConsoleConsoleDebugJavascript].</span></span>  

:::image type="complex" source="../media/console-debug-displays-error.msft.png" alt-text="DevTools 提供有关控制台中错误的详细信息" lightbox="../media/console-debug-displays-error.msft.png":::
   <span data-ttu-id="53c37-125">DevTools 提供有关控制台中错误 **的详细信息**</span><span class="sxs-lookup"><span data-stu-id="53c37-125">DevTools gives detailed information about the error in the **Console**</span></span>  
:::image-end:::  

## <a name="inspect-and-filter-information-on-the-current-webpage"></a><span data-ttu-id="53c37-126">检查和筛选当前网页上的信息</span><span class="sxs-lookup"><span data-stu-id="53c37-126">Inspect and filter information on the current webpage</span></span>  

<span data-ttu-id="53c37-127">当你在网页上打开 DevTools 时，你很可能会显示记录到控制台的一些 **信息**。</span><span class="sxs-lookup"><span data-stu-id="53c37-127">When you open the DevTools on a webpage, you're likely to display a deluge of information logged to the **Console**.</span></span>  <span data-ttu-id="53c37-128">当您需要识别重要信息时，信息量将成为一个问题。</span><span class="sxs-lookup"><span data-stu-id="53c37-128">The amount of information becomes a problem when you need to identify important information.</span></span>  <span data-ttu-id="53c37-129">若要查看需要采取措施的重要信息，请使用 DevTools [中的问题][DevtoolsIssuesIndex] 工具。</span><span class="sxs-lookup"><span data-stu-id="53c37-129">To view the important information that needs action, use the [Issues][DevtoolsIssuesIndex] tool in DevTools.</span></span>  <span data-ttu-id="53c37-130">大部分噪音仍然存在，这就是在控制台中了解自动日志和 [筛选器][DevtoolsConsoleConsoleFilters] 选项的一个好 **办法的原因**。</span><span class="sxs-lookup"><span data-stu-id="53c37-130">Much of the noise remains, which is why it's a good idea to know about the [automated log and filter options][DevtoolsConsoleConsoleFilters] in the **Console**.</span></span>  

:::image type="complex" source="../media/console-intro-noise.msft.png" alt-text="包含控制台的完整消息的 DevTools" lightbox="../media/console-intro-noise.msft.png":::
   <span data-ttu-id="53c37-132">包含控制台的完整 **消息** 的 DevTools</span><span class="sxs-lookup"><span data-stu-id="53c37-132">DevTools with a **Console** full of messages</span></span>  
:::image-end:::  

## <a name="log-information-to-display-in-the-console"></a><span data-ttu-id="53c37-133">要显示在控制台中的日志信息</span><span class="sxs-lookup"><span data-stu-id="53c37-133">Log information to display in the Console</span></span>  

<span data-ttu-id="53c37-134">控制台最常见的用例是使用 方法\*\*\*\* 或其他类似方法从脚本 `console.log()` 中记录信息。</span><span class="sxs-lookup"><span data-stu-id="53c37-134">The most popular use case for the **Console** is logging information from your scripts using the `console.log()` method or other similar methods.</span></span>  <span data-ttu-id="53c37-135">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="53c37-135">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="53c37-136">若要打开**控制台**，请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="53c37-136">To open **Console**, select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
1.  <span data-ttu-id="53c37-137">导航到 [控制台消息示例：日志、信息、错误和警告][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]，或在控制台中复制并运行以下 **代码段**。</span><span class="sxs-lookup"><span data-stu-id="53c37-137">Navigate to [Console messages examples: log, info, error and warn][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml], or copy and run the following code snippet in the **Console**.</span></span>  
    
    ```javascript
    console.log('This is a log message');
    console.info('This is some information'); 
    console.error('This is an error');
    console.warn('This is a warning');
    console.log(document.body.getBoundingClientRect());
    console.table(document.body.getBoundingClientRect());
    let technologies = ["HTML", "CSS", "SVG", "ECMAScript"];
    console.groupCollapsed('Technolgies');
    technologies.forEach(tech => {console.info(tech);})
    console.groupEnd('Technolgies');
    ```  
    
1.  <span data-ttu-id="53c37-138">控制台 **显示** 结果。</span><span class="sxs-lookup"><span data-stu-id="53c37-138">The **Console** displays the results.</span></span>  
    
    :::image type="complex" source="../media/console-intro-logging.msft.png" alt-text="控制台已满由演示代码导致的消息" lightbox="../media/console-intro-logging.msft.png":::
       <span data-ttu-id="53c37-140">**控制台** 已满由演示代码导致的消息</span><span class="sxs-lookup"><span data-stu-id="53c37-140">**Console** full of messages caused by demo code</span></span>  
    :::image-end:::  
    
<span data-ttu-id="53c37-141">使用控制台 时，可以使用许多有用的 **方法**。</span><span class="sxs-lookup"><span data-stu-id="53c37-141">Many useful methods are available when you work with the **Console**.</span></span>  <span data-ttu-id="53c37-142">有关详细信息，请导航到"[控制台"工具中的"记录消息"。][DevtoolsConsoleConsoleLog]</span><span class="sxs-lookup"><span data-stu-id="53c37-142">For more information, navigate to [Log messages in the Console tool][DevtoolsConsoleConsoleLog].</span></span>  

## <a name="try-your-javascript-live-in-the-console"></a><span data-ttu-id="53c37-143">在控制台中尝试 JavaScript 实时</span><span class="sxs-lookup"><span data-stu-id="53c37-143">Try your JavaScript live in the Console</span></span>  

<span data-ttu-id="53c37-144">**控制台**不仅仅是记录信息的位置。</span><span class="sxs-lookup"><span data-stu-id="53c37-144">The **Console** isn't only a place to log information.</span></span>  <span data-ttu-id="53c37-145">控制台 **是** 一个 [REPL][WikiReadEvalPrintLoop] 环境。</span><span class="sxs-lookup"><span data-stu-id="53c37-145">The **Console** is a [REPL][WikiReadEvalPrintLoop] environment.</span></span>  <span data-ttu-id="53c37-146">在控制台中编写任何 JavaScript **时**，代码会立即运行。</span><span class="sxs-lookup"><span data-stu-id="53c37-146">When you write any JavaScript in the **Console**, the code runs immediately.</span></span>  <span data-ttu-id="53c37-147">你会发现测试一些新的 JavaScript 功能或执行一些快速计算会很有用。</span><span class="sxs-lookup"><span data-stu-id="53c37-147">You may find it useful to test some new JavaScript features or to do some quick calculations.</span></span>  <span data-ttu-id="53c37-148">此外，还可以从新式编辑环境获取所有预期功能，如自动完成、语法突出显示和历史记录。</span><span class="sxs-lookup"><span data-stu-id="53c37-148">Also, you get all of the features you expect from a modern editing environment, such as autocompletion, syntax highlighting, and history.</span></span>  <span data-ttu-id="53c37-149">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="53c37-149">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="53c37-150">导航到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="53c37-150">Navigate to the **Console**.</span></span>  
1.  <span data-ttu-id="53c37-151">键入 `2 + 2`。</span><span class="sxs-lookup"><span data-stu-id="53c37-151">Type `2 + 2`.</span></span>  
    
<span data-ttu-id="53c37-152">控制台 **将在** 以下行 `4` 中显示结果。</span><span class="sxs-lookup"><span data-stu-id="53c37-152">The **Console** displays the result `4` on the following line.</span></span>  <span data-ttu-id="53c37-153">此 **"期待** "评估功能可用于调试和验证代码中没有出错。</span><span class="sxs-lookup"><span data-stu-id="53c37-153">This **Eager evaluation** feature is useful to debug and verify that you aren't making mistakes in your code.</span></span>  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="控制台会在你键入时显示 2 + 2 实时的结果" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   <span data-ttu-id="53c37-155">**控制台**会在您键入 `2 + 2` 实时内容时显示它的结果</span><span class="sxs-lookup"><span data-stu-id="53c37-155">The **Console** displays the result of `2 + 2` live as you type it</span></span>  
:::image-end:::  

<span data-ttu-id="53c37-156">若要在控制台中运行 JavaScript\*\*\*\* 表达式并选择性地显示结果，请选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="53c37-156">To run the JavaScript expression in the **Console** and optionally display a result, select `Enter`.</span></span>  <span data-ttu-id="53c37-157">然后，你可以编写下一个 JavaScript 代码以在控制台 **中运行**。</span><span class="sxs-lookup"><span data-stu-id="53c37-157">Then, you may write the next JavaScript code to run in the **Console**.</span></span>  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="连续运行几行 JavaScript 代码" lightbox="../media/console-javascript-several-expressions.msft.png":::
   <span data-ttu-id="53c37-159">连续运行几行 JavaScript 代码</span><span class="sxs-lookup"><span data-stu-id="53c37-159">Run several lines of JavaScript code in succession</span></span>  
:::image-end:::  

<span data-ttu-id="53c37-160">默认情况下，在单行中运行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="53c37-160">By default, you run JavaScript code on a single line.</span></span>  <span data-ttu-id="53c37-161">若要运行一行，请键入 JavaScript，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="53c37-161">To run a line, type your JavaScript and then select `Enter`.</span></span>  <span data-ttu-id="53c37-162">若要绕绕单行限制，请选择 `Shift` + `Enter` 而不是 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="53c37-162">To work around the single-line limitation, select `Shift`+`Enter` instead of `Enter`.</span></span>  <span data-ttu-id="53c37-163">与其他命令行体验类似，若要访问之前的 JavaScript 命令，请选择 `Arrow-Up` 。</span><span class="sxs-lookup"><span data-stu-id="53c37-163">Similar to other command-line experiences, to access your previous JavaScript commands, select `Arrow-Up`.</span></span>  <span data-ttu-id="53c37-164">控制台的自动完成 **功能是了解** 不熟悉的方法的一种很好的方法。</span><span class="sxs-lookup"><span data-stu-id="53c37-164">The autocompletion feature of the **Console** is a great way to learn about unfamiliar methods.</span></span>  <span data-ttu-id="53c37-165">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="53c37-165">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="53c37-166">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="53c37-166">Open the **Console**.</span></span>  
1.  <span data-ttu-id="53c37-167">键入 `doc`。</span><span class="sxs-lookup"><span data-stu-id="53c37-167">Type `doc`.</span></span>  
1.  <span data-ttu-id="53c37-168">从 `document` 下拉菜单中选择。</span><span class="sxs-lookup"><span data-stu-id="53c37-168">Choose `document` from the dropdown menu.</span></span>  
1.  <span data-ttu-id="53c37-169">选择 `tab` 密钥进行选择。</span><span class="sxs-lookup"><span data-stu-id="53c37-169">Select the `tab` key to choose it.</span></span>  
1.  <span data-ttu-id="53c37-170">键入 `.bo`。</span><span class="sxs-lookup"><span data-stu-id="53c37-170">Type `.bo`.</span></span>  
1.  <span data-ttu-id="53c37-171">选择 `tab` 获取 `document.body` 。</span><span class="sxs-lookup"><span data-stu-id="53c37-171">Select `tab` to get `document.body`.</span></span>  
1.  <span data-ttu-id="53c37-172">键入另 `.` 一个，以显示当前网页正文中可用的属性和方法的完整列表。</span><span class="sxs-lookup"><span data-stu-id="53c37-172">Type another `.` to display the complete list of properties and methods available on the body of the current webpage.</span></span>  
    
<span data-ttu-id="53c37-173">有关使用控制台的所有方法详细信息，请导航到\*\*\*\*[作为 JavaScript 环境的控制台][DevtoolsConsoleConsoleJavascript]。</span><span class="sxs-lookup"><span data-stu-id="53c37-173">For more information about all the ways to work with **Console**, navigate to [Console as a JavaScript environment][DevtoolsConsoleConsoleJavascript].</span></span>  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 表达式的控制台自动完成" lightbox="../media/console-javascript-autocomplete.msft.png":::
   <span data-ttu-id="53c37-175">\*\*\*\* JavaScript 表达式的控制台自动完成</span><span class="sxs-lookup"><span data-stu-id="53c37-175">**Console** autocompletion of JavaScript expressions</span></span>  
:::image-end:::  

## <a name="interact-with-the-current-webpage-in-the-browser"></a><span data-ttu-id="53c37-176">在浏览器中与当前网页交互</span><span class="sxs-lookup"><span data-stu-id="53c37-176">Interact with the current webpage in the browser</span></span>  

<span data-ttu-id="53c37-177">**控制台**有权访问浏览器[的 Window][MdnDocsWebApiWindow]对象。</span><span class="sxs-lookup"><span data-stu-id="53c37-177">The **Console** has access to the [Window][MdnDocsWebApiWindow] object of the browser.</span></span>  <span data-ttu-id="53c37-178">您可以编写与当前网页交互的脚本。</span><span class="sxs-lookup"><span data-stu-id="53c37-178">You may write scripts that interact with the current webpage.</span></span>  <span data-ttu-id="53c37-179">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="53c37-179">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="53c37-180">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="53c37-180">Open the **Console**.</span></span>  
1.  <span data-ttu-id="53c37-181">复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="53c37-181">Copy and paste the following code snippet.</span></span>  
    
    ```javascript
    document.querySelector('h1').innerHTML
    ```  
    
:::image type="complex" source="../media/console-intro-reading-DOM.msft.png" alt-text="复制顶部标题 (h1) DOM 中的内容并显示在控制台中" lightbox="../media/console-intro-reading-DOM.msft.png":::
   <span data-ttu-id="53c37-183">从 DOM 复制顶部标题 `h1` \ (\) 内容，并显示在 **控制台中**</span><span class="sxs-lookup"><span data-stu-id="53c37-183">Copy the top heading \(`h1`\) content from the DOM and display in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="53c37-184">您还可以更改它，而不是仅从网页中读取。</span><span class="sxs-lookup"><span data-stu-id="53c37-184">Instead of only reading from the webpage, you may also change it.</span></span>  <span data-ttu-id="53c37-185">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="53c37-185">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="53c37-186">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="53c37-186">Open the **Console**.</span></span>  
1.  <span data-ttu-id="53c37-187">复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="53c37-187">Copy and paste the following code snippet.</span></span>  
    
    ```javascript
    document.querySelector('h1').innerHTML = 'Rocking the Console';
    ```  
    
:::image type="complex" source="../media/console-intro-wrtiting-DOM.msft.png" alt-text="在控制台中向 DOM 写入文本" lightbox="../media/console-intro-wrtiting-DOM.msft.png":::
   <span data-ttu-id="53c37-189">在控制台中向 DOM 写入 **文本**</span><span class="sxs-lookup"><span data-stu-id="53c37-189">Write text to the DOM in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="53c37-190">将网页的主要标题更改为 **"摇动控制台"。**</span><span class="sxs-lookup"><span data-stu-id="53c37-190">You changed the main heading of the webpage to **Rocking the Console**.</span></span>  <span data-ttu-id="53c37-191">控制台 **实用程序** 方法使访问和操作当前网页变得容易。</span><span class="sxs-lookup"><span data-stu-id="53c37-191">The **Console Utility** methods make it easy to access and manipulate the current webpage.</span></span>  <span data-ttu-id="53c37-192">有关详细信息，请导航到 [控制台实用程序 API 参考][DevtoolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="53c37-192">For more information, navigate to [Console Utilities API reference][DevtoolsConsoleUtilities].</span></span>  <span data-ttu-id="53c37-193">例如，若要在当前网页中所有链接周围添加绿色边框，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="53c37-193">For example, to add a green border around all the links in the current webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="53c37-194">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="53c37-194">Open the **Console**.</span></span>  
1.  <span data-ttu-id="53c37-195">复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="53c37-195">Copy and paste the following code snippet.</span></span>  
    
    ```javascript
    $$('a').forEach(a => a.style.border='1px solid lime');
    ```  
    

:::image type="complex" source="../media/console-intro-changing-styles.msft.png" alt-text="使用控制台操作选定元素" lightbox="../media/console-intro-changing-styles.msft.png":::
    <span data-ttu-id="53c37-197">使用控制台操作选定 **元素**</span><span class="sxs-lookup"><span data-stu-id="53c37-197">Manipulate a selection of elements using the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="53c37-198">有关使用 DOM 的信息，请导航到"[使用控制台与 DOM 进行交互"。][DevtoolsConsoleConsoleDomInteraction]</span><span class="sxs-lookup"><span data-stu-id="53c37-198">For more information about working with the DOM, navigate to [Use the Console to interact with the DOM][DevtoolsConsoleConsoleDomInteraction].</span></span>  

## <a name="learn-more-about-console"></a><span data-ttu-id="53c37-199">详细了解控制台</span><span class="sxs-lookup"><span data-stu-id="53c37-199">Learn more about Console</span></span>  

<span data-ttu-id="53c37-200">有关控制台详细信息 **，** 请导航到"控制台[][DevtoolsConsoleReference]参考["、"控制台实用程序 API][DevtoolsConsoleUtilities]参考"和"[控制台 API 参考"。][DevtoolsConsoleApi]</span><span class="sxs-lookup"><span data-stu-id="53c37-200">For more information about the **Console**, navigate to [Console reference][DevtoolsConsoleReference], [Console Utilities API reference][DevtoolsConsoleUtilities], and [Console API reference][DevtoolsConsoleApi].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="53c37-201">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="53c37-201">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  
[DevtoolsConsoleConsoleDebugJavascript]: ./console-debug-javascript.md "在控制台控制台中报告的调试|Microsoft Docs"  
[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "使用控制台与 DOM 服务器|Microsoft Docs" 
[DevtoolsConsoleConsoleFilters]: ./console-filters.md "筛选控制台消息|Microsoft Docs"  
[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "作为 JavaScript 环境的控制台|Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "在控制台工具控制台中记录|Microsoft Docs"  
[DevtoolsConsoleReference]: ./reference.md "控制台参考|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  

[DevtoolsIssuesIndex]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-demo.html "控制台消息示例：日志、信息、错误和警告|GitHub"  

[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口|MDN"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval–print 循环|Wikipedia"  
