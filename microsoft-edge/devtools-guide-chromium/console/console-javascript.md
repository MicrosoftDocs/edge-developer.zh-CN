---
description: 将 Microsoft Edge 开发人员工具内的控制台工具用作 JavaScript 环境的简介。
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
# <a name="the-console-as-a-javascript-environment"></a>作为 JavaScript 环境的控制台  

浏览器**** DevTools 中的控制台工具是一个[REPL][WikiReadEvalPrintLoop]环境。  这意味着你可以编写控制台中立即 **运行** 的任何 JavaScript。

若要尝试，请完成以下操作。  

1.  打开“**控制台**”。  
    *   选择 `Control` + `Shift` + `J` \(Windows、Linux\) 或 `Command` + `Option` + `J` \(macOS\)。  
1.  键入 `2 + 2`。  **当您键入**时，控制台 `4` 已经在下一行上显示结果。  该功能 `Eager evaluation` 可帮助你编写有效的 JavaScript。  键入错误或有效结果是否存在时，它将显示结果。  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="控制台在键入时显示 2 + 2 实时的结果" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   **控制台** 在键入 `2 + 2` 实时内容时显示结果  
:::image-end:::  

如果选择 ， `Enter` **控制台** 将运行 JavaScript 命令，为你提供结果，并允许编写下一个命令。  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="连续运行多个 JavaScript 表达式" lightbox="../media/console-javascript-several-expressions.msft.png":::
   连续运行多个 JavaScript 表达式  
:::image-end:::  

## <a name="autocompletion-to-write-complex-expressions"></a>编写复杂表达式的自动完成

最后一个示例可能看起来不令人难看，但 **控制台** 可帮助你使用出色的自动完成功能编写复杂的 JavaScript。  此功能是了解以前不知道的方法的一种好方法。  

若要尝试，请完成以下操作。  

1.  键入 `doc`。  
1.  从 `document` 下拉菜单中选择。  
1.  选择 `tab` 密钥进行选择。  
1.  键入 `.bo`。  
1.  选择 `tab` 获取 `document.body` 。  
1.  键入另 `.` 一个，获取当前网页正文中可用的可能属性和方法的大型列表。  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 表达式的控制台自动完成" lightbox="../media/console-javascript-autocomplete.msft.png":::
   **** JavaScript 表达式的控制台自动完成  
:::image-end:::  

## <a name="console-history"></a>控制台历史记录

与许多其他命令行体验一样，您也有命令历史记录。  选择 `Arrow Up` 以显示之前输入的命令。  自动完成还会保留以前键入的命令的历史记录。  可以键入之前命令的前几个字母，之前的选项会显示在文本框中。  

此外， **控制台** 还提供了很多实用程序 [方法][DevtoolsConsoleUtilities] ，可简化您的生活。  例如， `$_` 始终包含控制台 中运行的最后一个表达式 **的结果**。

:::image type="complex" source="../media/console-javascript-console-history.msft.png" alt-text="控制台中的 $_ 表达式始终包含最后的结果" lightbox="../media/console-javascript-console-history.msft.png":::
    控制台 `$_` 中的表达式 **始终** 包含最后的结果  
:::image-end:::  

## <a name="multiline-edits"></a>多行编辑

默认情况下， **控制台只** 为你提供一行来编写 JavaScript 表达式。  选择 时，代码将运行 `Enter` 。 单行限制可能会使您费时无用。  若要绕绕一行限制，请选择 `Shift` + `Enter` 而不是 `Enter` 。  在下面的示例中，显示的值是按顺序运行的所有行的结果。  

:::image type="complex" source="../media/console-javascript-multiline.msft.png" alt-text="选择 Shift+Enter 可编写几行 JavaScript，并按顺序运行生成的值" lightbox="../media/console-javascript-multiline.msft.png":::
   选择 `Shift` + `Enter` 以写入几行 JavaScript，并按顺序运行生成的值  
:::image-end:::  

如果在控制台中启动多行 **语句，它**将自动识别并缩进。  例如，如果启动带大括号的块语句。  

:::image type="complex" source="../media/console-javascript-automatic-lineindent.msft.png" alt-text="控制台已使用大括号和缩进来识别多行表达式" lightbox="../media/console-javascript-automatic-lineindent.msft.png":::
    **控制台** 已使用大括号和缩进来识别多行表达式  
:::image-end:::  

## <a name="network-requests-using-top-level-await"></a>使用顶级 await 请求的网络 ()   

除了在你自己的脚本中， **控制台** 还 [支持顶级 await][GithubTc39ProposalTopLevelAwait] 在它内运行任意异步 JavaScript。  例如，使用 API 时 `fetch` 无需使用 `await` async 函数包装语句。  

若要获取 Microsoft Edge 开发人员工具 for [Visual Studio GitHub][GithubMicrosoftVscodeEdgeDevtools] 存储库中存档的最后 50 个问题，请完成以下操作。  

1.  打开“**控制台**”。  
1.  复制并粘贴以下代码段，获取包含 10 个条目的对象。  
    
    ```javascript
    await ( await fetch(
    'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
    )).json();
    ```  
    
:::image type="complex" source="../media/console-javascript-top-level-await.msft.png" alt-text="控制台显示顶级异步提取请求的结果" lightbox="../media/console-javascript-top-level-await.msft.png":::
    **控制台** 显示顶级异步请求 `fetch` 的结果  
:::image-end:::  

这 10 个条目很难识别，因为会显示大量信息。  幸运的是，您可以使用 log 方法仅 `console.table()` 接收您感兴趣的信息。  

:::image type="complex" source="../media/console-javascript-filtered-with-table.msft.png" alt-text="使用 console.table 以人工可读格式显示最后的结果" lightbox="../media/console-javascript-filtered-with-table.msft.png":::
    使用 可读格式显示最后的结果 `console.table`  
:::image-end:::  

若要重用从表达式返回的数据，可以使用 `copy()` 控制台 的实用程序 **方法**。  以下代码段发送请求并将响应数据复制到剪贴板。  

```javascript
copy(await (await fetch(
'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
)).json())
```  

使用 **控制台** 作为实践 JavaScript 功能和进行一些快速计算很好的方法。  真正的功能是，您有权访问 [window][MdnDocsWebApiWindow] 对象。  你可以 [与控制台 中的 DOM 交互][DevtoolsConsoleConsoleDomInteraction]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "使用控制台与 DOM 服务器|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubTc39ProposalTopLevelAwait]: https://github.com/tc39/proposal-top-level-await "ECMAScript 建议：顶级 await - tc39/proposal-top-level-await |GitHub"

[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口|MDN"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval–print 循环|Wikipedia"  
