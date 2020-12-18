---
description: 了解如何在控制台中运行 JavaScript。
title: 开始在控制台中运行 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ecd1a2fffb311990b6e743e99d038f1f2a519ee4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231088"
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

# 开始在控制台中运行 JavaScript  

此交互式教程介绍如何在 Microsoft Edge DevTools 控制台中运行**JavaScript。**  若要详细了解如何将消息记录到**控制台，** 请导航到"日志记录消息[入门"。][DevToolsConsoleLoggingMessages]  若要详细了解如何暂停 JavaScript 代码并一次单步执行一行，请导航到"调试[JavaScript 入门"。][DevToolsJavascriptIndex]  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   **控制台**  
:::image-end:::  

## 概述  

控制台**是**[一个 REPL，][WikiReadEvalPrintLoop]它代表读取、评估、打印和循环。  它读取您键入的 JavaScript，计算代码，输出表达式的结果，然后循环回第一步。 [][2alityExpressionsVersusStatements]  

## 设置 DevTools  

本教程旨在让你打开演示并自己尝试所有工作流。  当您实际跟进时，您以后更有可能会记住工作流。

1.  选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开**控制台**。  
1.  按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择控制台 **Javascript 示例** 以在一个新窗口中打开。  
    
    *   [控制台 Javascript 示例][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="左侧的控制台 JavaScript 示例页面，右侧为 DevTools" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       左侧的控制台 JavaScript 示例页面，右侧为 DevTools  
    :::image-end:::  
    
## 查看和更改页面的 JavaScript 或 DOM  

生成或调试页面时，在控制台中运行语句以更改页面的外观或运行**** 方式通常很有用。  
    
1.  请注意按钮中的文本。  
1.  在 `document.getElementById('hello').textContent = 'Hello, Console!'` 控制台 **中键入** ，然后选择 `Enter` 计算表达式。  请注意按钮内的文本如何更改。  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="评估表达式后控制台的外观" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       评估 **表达式** 后控制台的外观  
    :::image-end:::  
    
    在评估的代码下方，你将看到 `"Hello, Console!"` 。  回顾 REPL 的 4 个步骤：读取、评估、打印、循环。  在计算代码后，REPL 将输出表达式的结果。  因此 `"Hello, Console!"` ，计算的结果必须是 `document.getElementById('hello').textContent = 'Hello, Console!'` 。  
    
## 运行与页面不相关的任意 JavaScript  

有时，你只需一个代码场，可以在其中测试一些代码，或尝试你不熟悉的新 JavaScript 功能。  控制台 **是** 这些类型的实验的一个理想位置。  

1.  在 `5 + 15` 控制台中键入并选择 `Enter` 计算表达式。 控制台将输出代码下面的表达式结果。  下图中 **，控制台应在** 计算表达式后显示结果。  

1.  在控制台中键入以下 **代码**。  请尝试按字符键入它，而不是复制粘贴它。  
    
    ```javascript
    function add(a, b=20)
    ```  
    
    如果您不熟悉语法， `b=20` 请导航以 [定义函数参数的默认值][Esma6DefaultParameterValues]。  
    
1.  现在，运行刚定义的函数。  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="控制台在评估代码段中的表达式后显示" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             控制台 **在** 评估代码段中的表达式后显示  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` 计算结果为 ，因为在没有第二个参数的情况下调用函数 `45` `add` `b` 时，默认为 `20` 。  

## 后续步骤  

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

DevTools 允许你在运行期间暂停脚本。  暂停时，可以使用控制台在此时查看和更改**** 页面或 `window` `DOM` 页面。  工作流可创建功能强大的调试工作流。  对于交互式教程，导航到["调试 JavaScript 入门"。][DevToolsJavascriptIndex]  

控制台 **还** 具有一组方便功能，可更轻松地与页面进行交互。  例如：  

*   不要键入 `document.querySelector()` 以选择元素，请键入 `$()` 。  此语法受 jQuery 启发，但实际上并不是 jQuery。  它只是一个别名 `document.querySelector()` 。  
*   `debug(function)` 有效设置该函数的第一行上的断点。  
*   `keys(object)` 返回包含指定对象的键的数组。  

有关便利函数详细信息，请导航到 [控制台实用程序 API 参考][DevToolsConsoleUtilities]。  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "开始在控制台中记录消息 |Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "控制台参考 |Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 |Microsoft Docs"  
[DevToolsJavascriptIndex]: ../javascript/index.md "开始在 Microsoft Edge DevTools 中调试 JavaScript |Microsoft Docs"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript 中的表达式与语句"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "默认参数值 - 扩展参数处理 - ECMAScript 6 — 新功能：概述&比较"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "控制台 Javascript 示例 |小故障"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "Read–eval-print 循环 - Wikipedia"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/javascript)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
