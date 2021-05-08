---
description: 将控制台工具用作 JavaScript Microsoft Edge开发人员工具简介。
title: 作为 JavaScript 环境的控制台
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， JavaScript， Web 开发， f12 工具， devtools
ms.openlocfilehash: f75ac6d728c9a69542b2f58df85248759267f76d
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483350"
---
# <a name="the-console-as-a-javascript-environment"></a><span data-ttu-id="fdfe9-104">作为 JavaScript 环境的控制台</span><span class="sxs-lookup"><span data-stu-id="fdfe9-104">The Console as a JavaScript environment</span></span>  

<span data-ttu-id="fdfe9-105">浏览器\*\*\*\* DevTools 中的控制台工具是一个[REPL][WikiReadEvalPrintLoop]环境。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-105">The **Console** tool inside the browser DevTools is a [REPL][WikiReadEvalPrintLoop] environment.</span></span>  <span data-ttu-id="fdfe9-106">这意味着你可以编写控制台中立即 **运行** 的任何 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-106">It means that you may write any JavaScript in the **Console** that runs immediately.</span></span>

<span data-ttu-id="fdfe9-107">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-107">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="fdfe9-108">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-108">Open the **Console**.</span></span>  
    *   <span data-ttu-id="fdfe9-109">选择 `Control` + `Shift` + `J` \(Windows、Linux\) 或 `Command` + `Option` + `J` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-109">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
1.  <span data-ttu-id="fdfe9-110">键入 `2 + 2`。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-110">Type `2 + 2`.</span></span>  <span data-ttu-id="fdfe9-111">**当您键入**时，控制台 `4` 已经在下一行上显示结果。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-111">The **Console** already displays the result `4` on the next line while you type it.</span></span>  <span data-ttu-id="fdfe9-112">该功能 `Eager evaluation` 可帮助你编写有效的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-112">The `Eager evaluation` feature helps you write valid JavaScript.</span></span>  <span data-ttu-id="fdfe9-113">键入错误或有效结果是否存在时，它将显示结果。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-113">It displays the result while you type whether it's wrong or if a valid result exists.</span></span>  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="控制台在键入时显示 2 + 2 实时的结果" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   <span data-ttu-id="fdfe9-115">**控制台** 在键入 `2 + 2` 实时内容时显示结果</span><span class="sxs-lookup"><span data-stu-id="fdfe9-115">**Console** displays the result of `2 + 2` live as you type it</span></span>  
:::image-end:::  

<span data-ttu-id="fdfe9-116">如果选择 ， `Enter` **控制台** 将运行 JavaScript 命令，为你提供结果，并允许编写下一个命令。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-116">If you select `Enter`, the **Console** runs the JavaScript command, gives you the result, and allows you to write the next command.</span></span>  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="连续运行多个 JavaScript 表达式" lightbox="../media/console-javascript-several-expressions.msft.png":::
   <span data-ttu-id="fdfe9-118">连续运行多个 JavaScript 表达式</span><span class="sxs-lookup"><span data-stu-id="fdfe9-118">Run several JavaScript expressions in succession</span></span>  
:::image-end:::  

## <a name="autocompletion-to-write-complex-expressions"></a><span data-ttu-id="fdfe9-119">编写复杂表达式的自动完成</span><span class="sxs-lookup"><span data-stu-id="fdfe9-119">Autocompletion to write complex expressions</span></span>

<span data-ttu-id="fdfe9-120">最后一个示例可能看起来不令人难看，但 **控制台** 可帮助你使用出色的自动完成功能编写复杂的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-120">The last example may seem scary, but the **Console** helps you write complex JavaScript using an excellent autocompletion feature.</span></span>  <span data-ttu-id="fdfe9-121">此功能是了解以前不知道的方法的一种好方法。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-121">This feature is a great way to learn about methods you didn't know before.</span></span>  

<span data-ttu-id="fdfe9-122">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-122">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="fdfe9-123">键入 `doc`。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-123">Type `doc`.</span></span>  
1.  <span data-ttu-id="fdfe9-124">从 `document` 下拉菜单中选择。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-124">Choose `document` from the dropdown menu.</span></span>  
1.  <span data-ttu-id="fdfe9-125">选择 `tab` 密钥进行选择。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-125">Select the `tab` key to choose it.</span></span>  
1.  <span data-ttu-id="fdfe9-126">键入 `.bo`。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-126">Type `.bo`.</span></span>  
1.  <span data-ttu-id="fdfe9-127">选择 `tab` 获取 `document.body` 。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-127">Select `tab` to get `document.body`.</span></span>  
1.  <span data-ttu-id="fdfe9-128">键入另 `.` 一个，获取当前网页正文中可用的可能属性和方法的大型列表。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-128">Type another `.` to get a large list of possible properties and methods available on the body of the current webpage.</span></span>  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 表达式的控制台自动完成" lightbox="../media/console-javascript-autocomplete.msft.png":::
   <span data-ttu-id="fdfe9-130">\*\*\*\* JavaScript 表达式的控制台自动完成</span><span class="sxs-lookup"><span data-stu-id="fdfe9-130">**Console** autocompletion of JavaScript expressions</span></span>  
:::image-end:::  

## <a name="console-history"></a><span data-ttu-id="fdfe9-131">控制台历史记录</span><span class="sxs-lookup"><span data-stu-id="fdfe9-131">Console history</span></span>

<span data-ttu-id="fdfe9-132">与许多其他命令行体验一样，您也有命令历史记录。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-132">As with many other command-line experiences, you also have a history of commands.</span></span>  <span data-ttu-id="fdfe9-133">选择 `Arrow Up` 以显示之前输入的命令。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-133">Select `Arrow Up` to display the commands you entered before.</span></span>  <span data-ttu-id="fdfe9-134">自动完成还会保留以前键入的命令的历史记录。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-134">Autocompletion also keeps a history of the commands you previously typed.</span></span>  <span data-ttu-id="fdfe9-135">可以键入之前命令的前几个字母，之前的选项会显示在文本框中。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-135">You may type the first few letters of earlier commands and your previous choices display in a textbox.</span></span>  

<span data-ttu-id="fdfe9-136">此外， **控制台** 还提供了很多实用程序 [方法][DevtoolsConsoleUtilities] ，可简化您的生活。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-136">Also, the **Console** also offers quite a few [utility methods][DevtoolsConsoleUtilities] that make your life easier.</span></span>  <span data-ttu-id="fdfe9-137">例如， `$_` 始终包含控制台 中运行的最后一个表达式 **的结果**。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-137">For example, `$_` always contains the result of the last expression you ran in the **Console**.</span></span>

:::image type="complex" source="../media/console-javascript-console-history.msft.png" alt-text="控制台中的 $_ 表达式始终包含最后的结果" lightbox="../media/console-javascript-console-history.msft.png":::
    <span data-ttu-id="fdfe9-139">控制台 `$_` 中的表达式 **始终** 包含最后的结果</span><span class="sxs-lookup"><span data-stu-id="fdfe9-139">The `$_` expression in the **Console** always contains the last result</span></span>  
:::image-end:::  

## <a name="multiline-edits"></a><span data-ttu-id="fdfe9-140">多行编辑</span><span class="sxs-lookup"><span data-stu-id="fdfe9-140">Multiline edits</span></span>

<span data-ttu-id="fdfe9-141">默认情况下， **控制台只** 为你提供一行来编写 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-141">By default, the **Console** only gives you one line to write your JavaScript expression.</span></span>  <span data-ttu-id="fdfe9-142">选择 时，代码将运行 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-142">You code runs when you select `Enter`.</span></span> <span data-ttu-id="fdfe9-143">单行限制可能会使您费时无用。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-143">The one line limitation may frustrate you.</span></span>  <span data-ttu-id="fdfe9-144">若要绕绕一行限制，请选择 `Shift` + `Enter` 而不是 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-144">To work around the one line limitation, select `Shift`+`Enter` instead of `Enter`.</span></span>  <span data-ttu-id="fdfe9-145">在下面的示例中，显示的值是按顺序运行的所有行的结果。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-145">In the following example, the value displayed is the result of all the lines run in order.</span></span>  

:::image type="complex" source="../media/console-javascript-multiline.msft.png" alt-text="选择 Shift+Enter 可编写几行 JavaScript，并按顺序运行生成的值" lightbox="../media/console-javascript-multiline.msft.png":::
   <span data-ttu-id="fdfe9-147">选择 `Shift` + `Enter` 以写入几行 JavaScript，并按顺序运行生成的值</span><span class="sxs-lookup"><span data-stu-id="fdfe9-147">Select `Shift`+`Enter` to write several lines of JavaScript and the resulting value is run in order</span></span>  
:::image-end:::  

<span data-ttu-id="fdfe9-148">如果在控制台中启动多行 **语句，它**将自动识别并缩进。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-148">If you start a multiline statement in the **Console**, it gets automatically recognized and indented.</span></span>  <span data-ttu-id="fdfe9-149">例如，如果启动带大括号的块语句。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-149">For example, if you start a block statement with a curly brace.</span></span>  

:::image type="complex" source="../media/console-javascript-automatic-lineindent.msft.png" alt-text="控制台已使用大括号和缩进来识别多行表达式" lightbox="../media/console-javascript-automatic-lineindent.msft.png":::
    <span data-ttu-id="fdfe9-151">**控制台** 已使用大括号和缩进来识别多行表达式</span><span class="sxs-lookup"><span data-stu-id="fdfe9-151">**Console** already recognizes multiline expressions using curly braces and indents each for you</span></span>  
:::image-end:::  

## <a name="network-requests-using-top-level-await"></a><span data-ttu-id="fdfe9-152">使用顶级 await 请求的网络 () </span><span class="sxs-lookup"><span data-stu-id="fdfe9-152">Network requests using top-level await()</span></span>  

<span data-ttu-id="fdfe9-153">除了在你自己的脚本中， **控制台** 还 [支持顶级 await][GithubTc39ProposalTopLevelAwait] 在它内运行任意异步 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-153">Other than in your own scripts, **Console** supports [top level await][GithubTc39ProposalTopLevelAwait] to run arbitrary asynchronous JavaScript in it.</span></span>  <span data-ttu-id="fdfe9-154">例如，使用 API 时 `fetch` 无需使用 `await` async 函数包装语句。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-154">For example, use the `fetch` API without wrapping the `await` statement with an async function.</span></span>  

<span data-ttu-id="fdfe9-155">若要获取 Microsoft Edge 开发人员工具 Visual Studio Code [GitHub][GithubMicrosoftVscodeEdgeDevtools]存储库上归档的最后 50 个问题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-155">To get the last 50 issues filed on the [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] GitHub repo, complete the following actions.</span></span>  

1.  <span data-ttu-id="fdfe9-156">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-156">Open the **Console**.</span></span>  
1.  <span data-ttu-id="fdfe9-157">复制并粘贴以下代码段，获取包含 10 个条目的对象。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-157">Copy and paste the following code snippet to get an object that contains 10 entries.</span></span>  
    
    ```javascript
    await ( await fetch(
    'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
    )).json();
    ```  
    
:::image type="complex" source="../media/console-javascript-top-level-await.msft.png" alt-text="控制台显示顶级异步提取请求的结果" lightbox="../media/console-javascript-top-level-await.msft.png":::
    <span data-ttu-id="fdfe9-159">**控制台** 显示顶级异步请求 `fetch` 的结果</span><span class="sxs-lookup"><span data-stu-id="fdfe9-159">**Console** displays the result of a top-level async `fetch` request</span></span>  
:::image-end:::  

<span data-ttu-id="fdfe9-160">这 10 个条目很难识别，因为会显示大量信息。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-160">The 10 entries are hard to recognize, since a lot of information is displayed.</span></span>  <span data-ttu-id="fdfe9-161">幸运的是，您可以使用 log 方法仅 `console.table()` 接收您感兴趣的信息。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-161">Luckily enough, you may use the `console.table()` log method to only receive the information in which you're interested.</span></span>  

:::image type="complex" source="../media/console-javascript-filtered-with-table.msft.png" alt-text="使用 console.table 以人工可读格式显示最后的结果" lightbox="../media/console-javascript-filtered-with-table.msft.png":::
    <span data-ttu-id="fdfe9-163">使用 可读格式显示最后的结果</span><span class="sxs-lookup"><span data-stu-id="fdfe9-163">Display the last result in a human readable format using</span></span> `console.table`  
:::image-end:::  

<span data-ttu-id="fdfe9-164">若要重用从表达式返回的数据，可以使用 `copy()` 控制台 的实用程序 **方法**。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-164">To reuse the data returned from an expression, you may use the `copy()` utility method of the **Console**.</span></span>  <span data-ttu-id="fdfe9-165">以下代码段发送请求并将响应数据复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-165">The following code snippet sends the request and copies the data from the response to the clipboard.</span></span>  

```javascript
copy(await (await fetch(
'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
)).json())
```  

<span data-ttu-id="fdfe9-166">使用 **控制台** 作为实践 JavaScript 功能和进行一些快速计算很好的方法。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-166">Use the **Console** as a great way to practice JavaScript functionality and to do some quick calculations.</span></span>  <span data-ttu-id="fdfe9-167">真正的功能是，您有权访问 [window][MdnDocsWebApiWindow] 对象。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-167">The real power is the fact that you have access to the [window][MdnDocsWebApiWindow] object.</span></span>  <span data-ttu-id="fdfe9-168">你可以 [与控制台 中的 DOM 交互][DevtoolsConsoleConsoleDomInteraction]。</span><span class="sxs-lookup"><span data-stu-id="fdfe9-168">You may [interact with the DOM in Console][DevtoolsConsoleConsoleDomInteraction].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="fdfe9-169">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="fdfe9-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "使用控制台与 DOM 服务器|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubTc39ProposalTopLevelAwait]: https://github.com/tc39/proposal-top-level-await "ECMAScript 建议：顶级 await - tc39/proposal-top-level-await |GitHub"

[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口|MDN"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval–print 循环|Wikipedia"  
