---
description: 控制台工具在开发人员工具Microsoft Edge简介。
title: 使用控制台
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: badcaae0ad637fe7a027f78d00daf9133789693e
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624743"
---
# <a name="use-the-console"></a>使用控制台  

DevTools 的控制台工具可帮助你完成多项任务。 ****  以下列表包含一些任务。  

*   了解为什么某些内容在当前项目中无法工作， [并跟踪问题][DevtoolsConsoleConsoleDebugJavascript]。  
*   [以日志消息获取有关浏览器中][DevtoolsConsoleConsoleFilters] Web 项目的信息。  
*   [将信息][DevtoolsConsoleConsoleLog] 记录在脚本中以便进行调试。  
*   [尝试 JavaScript 表达式][DevtoolsConsoleConsoleJavascript] 在 [REPL 环境中][WikiReadEvalPrintLoop] 活动。  
*   使用 JavaScript[与浏览器中][DevtoolsConsoleConsoleDomInteraction]的 Web 项目交互。  
    
控制台 **是** 一款很好的配套工具，可用于其他工具。  控制台 **提供了** 一种使用 JavaScript 编写功能、检查和处理当前网页的功能强大的方法。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-main.msft.png" alt-text="控制台工具在上方面板中打开" lightbox="../media/console-intro-console-main.msft.png":::
         控制台 **工具** 在上方面板中打开  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-panel.msft.png" alt-text="下面板中的控制台，其上方打开"元素"工具" lightbox="../media/console-intro-console-panel.msft.png":::
         **下** 面板中的控制台，其上方打开 **"元素** "工具  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

直接打开控制台的最快方法为选择**** `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。  

## <a name="error-reports-and-console"></a>错误报告和控制台  

**控制台** 是报告 JavaScript 和连接错误的默认位置。  如果发生任何错误，"**** 问题"计数器将显示在 DevTools 中提供错误和警告**设置**图标旁边。  选择 **"问题"** 计数器以打开 **"问题** "工具并显示问题。  有关详细信息，请导航到"[控制台"中报告的"调试错误"。][DevtoolsConsoleConsoleDebugJavascript]

:::image type="complex" source="../media/console-debug-displays-error.msft.png" alt-text="DevTools 提供有关控制台中错误的详细信息" lightbox="../media/console-debug-displays-error.msft.png":::
   DevTools 提供有关控制台中错误 **的详细信息**  
:::image-end:::  

## <a name="inspect-and-filter-information-on-the-current-webpage"></a>检查和筛选当前网页上的信息  

When you open DevTools on a webpage， there may be the overwhelming amount of information in the **Console**.  当您需要识别重要信息时，信息量将成为一个问题。  若要查看需要采取措施的重要信息，请使用 DevTools [中的问题][DevtoolsIssuesIndex] 工具。

问题正在逐渐从控制台**移动到****问题工具**。  但是，控制台中仍有很多信息，这就是为什么在控制台**** 中了解自动日志和筛选器**选项是一**个好主意。  有关详细信息，请导航到"[筛选器控制台消息"。][DevtoolsConsoleConsoleFilters]

:::image type="complex" source="../media/console-intro-noise.msft.png" alt-text="包含控制台的完整消息的 DevTools" lightbox="../media/console-intro-noise.msft.png":::
   包含控制台的完整 **消息** 的 DevTools  
:::image-end:::  

## <a name="log-information-to-display-in-the-console"></a>要显示在控制台中的日志信息  

控制台最常见的用例是使用 方法**** 或其他类似方法从脚本 `console.log()` 中记录信息。  若要尝试，请完成以下操作。  

1.  若要打开**控制台**，请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。  
1.  导航到 [控制台消息示例：日志、信息、错误和警告][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]，或在控制台中复制并运行以下 **代码段**。  
    
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
    
1.  控制台 **显示** 结果。  
    
    :::image type="complex" source="../media/console-intro-logging.msft.png" alt-text="控制台已满由演示代码导致的消息" lightbox="../media/console-intro-logging.msft.png":::
       **控制台** 已满由演示代码导致的消息  
    :::image-end:::  
    
使用控制台 时，可以使用许多有用的 **方法**。  有关详细信息，请导航到"[控制台"工具中的"记录消息"。][DevtoolsConsoleConsoleLog]  

## <a name="try-your-javascript-live-in-the-console"></a>在控制台中尝试 JavaScript 实时  

**控制台**不仅仅是记录信息的位置。  控制台 **是** 一个 [REPL][WikiReadEvalPrintLoop] 环境。  在控制台中编写任何 JavaScript **时**，代码会立即运行。  你会发现测试一些新的 JavaScript 功能或执行一些快速计算会很有用。  此外，还可以从新式编辑环境获取所有预期功能，如自动完成、语法突出显示和历史记录。  若要尝试，请完成以下操作。  

1.  导航到 **控制台**。  
1.  键入 `2 + 2`。  
    
控制台 **将在** 以下行 `4` 中显示结果。  此 **"期待** "评估功能可用于调试和验证代码中没有出错。  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="控制台会在你键入时显示 2 + 2 实时的结果" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   **控制台**会在您键入 `2 + 2` 实时内容时显示它的结果  
:::image-end:::  

若要在控制台中运行 JavaScript**** 表达式并选择性地显示结果，请选择 `Enter` 。  然后，你可以编写下一个 JavaScript 代码以在控制台 **中运行**。  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="连续运行几行 JavaScript 代码" lightbox="../media/console-javascript-several-expressions.msft.png":::
   连续运行几行 JavaScript 代码  
:::image-end:::  

默认情况下，在单行中运行 JavaScript 代码。  若要运行一行，请键入 JavaScript，然后选择 `Enter` 。  若要绕绕单行限制，请选择 `Shift` + `Enter` 而不是 `Enter` 。  与其他命令行体验类似，若要访问之前的 JavaScript 命令，请选择 `Arrow-Up` 。  控制台的自动完成 **功能是了解** 不熟悉的方法的一种很好的方法。  若要尝试，请完成以下操作。  

1.  打开“**控制台**”。  
1.  键入 `doc`。  
1.  从 `document` 下拉菜单中选择。  
1.  选择 `tab` 密钥进行选择。  
1.  键入 `.bo`。  
1.  选择 `tab` 获取 `document.body` 。  
1.  键入另 `.` 一个，以显示当前网页正文中可用的属性和方法的完整列表。  
    
有关使用控制台的所有方法详细信息，请导航到****[作为 JavaScript 环境的控制台][DevtoolsConsoleConsoleJavascript]。  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 表达式的控制台自动完成" lightbox="../media/console-javascript-autocomplete.msft.png":::
   **** JavaScript 表达式的控制台自动完成  
:::image-end:::  

## <a name="interact-with-the-current-webpage-in-the-browser"></a>在浏览器中与当前网页交互  

**控制台**有权访问浏览器[的 Window][MdnDocsWebApiWindow]对象。  您可以编写与当前网页交互的脚本。  若要尝试，请完成以下操作。  

1.  打开“**控制台**”。  
1.  复制并粘贴以下代码段。  
    
    ```javascript
    document.querySelector('h1').innerHTML
    ```  
    
:::image type="complex" source="../media/console-intro-reading-DOM.msft.png" alt-text="复制顶部标题 (h1) DOM 中的内容并显示在控制台中" lightbox="../media/console-intro-reading-DOM.msft.png":::
   从 DOM 复制顶部标题 `h1` \ (\) 内容，并显示在 **控制台中**  
:::image-end:::  

还可以更改它，而不是仅从网页中读取。  若要尝试更改网页，请完成以下操作。  

1.  打开“**控制台**”。  
1.  复制并粘贴以下代码段。  
    
    ```javascript
    document.querySelector('h1').innerHTML = 'Rocking the Console';
    ```  
    
:::image type="complex" source="../media/console-intro-wrtiting-DOM.msft.png" alt-text="在控制台中向 DOM 写入文本" lightbox="../media/console-intro-wrtiting-DOM.msft.png":::
   在控制台中向 DOM 写入 **文本**  
:::image-end:::  

将网页的主要标题更改为 **"摇动控制台"。**  控制台 **实用程序** 方法使访问和操作当前网页变得容易。  有关详细信息，请导航到 [控制台实用程序 API 参考][DevtoolsConsoleUtilities]。  例如，若要在当前网页中所有链接周围添加绿色边框，请完成以下操作。  

1.  打开“**控制台**”。  
1.  复制并粘贴以下代码段。  
    
    ```javascript
    $$('a').forEach(a => a.style.border='1px solid lime');
    ```  
    
:::image type="complex" source="../media/console-intro-changing-styles.msft.png" alt-text="使用控制台操作选定元素" lightbox="../media/console-intro-changing-styles.msft.png":::
    使用控制台操作选定 **元素**  
:::image-end:::  

有关使用 DOM 的信息，请导航到"[使用控制台与 DOM 进行交互"。][DevtoolsConsoleConsoleDomInteraction]  

## <a name="learn-more-about-console"></a>详细了解控制台  

有关控制台详细信息 **，** 请导航到"控制台[][DevtoolsConsoleReference]参考["、"控制台实用程序 API][DevtoolsConsoleUtilities]参考"和"[控制台 API 参考"。][DevtoolsConsoleApi]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  
[DevtoolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  
[DevtoolsConsoleConsoleDebugJavascript]: ./console-debug-javascript.md "在控制台控制台中报告的调试|Microsoft Docs"  
[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "使用控制台与 DOM 服务器|Microsoft Docs" 
[DevtoolsConsoleConsoleFilters]: ./console-filters.md "筛选控制台消息|Microsoft Docs"  
[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "作为 JavaScript 环境的控制台|Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "在控制台工具控制台中记录|Microsoft Docs"  
[DevtoolsConsoleReference]: ./reference.md "控制台参考|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考|Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "使用问题工具查找并修复|Microsoft Docs"  
<!-- external links -->
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-demo.html "控制台消息示例：日志、信息、错误和警告|GitHub"  
[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口|MDN"  
[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval–print 循环|Wikipedia"  
