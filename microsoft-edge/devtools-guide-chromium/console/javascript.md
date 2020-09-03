---
description: 了解如何在控制台中运行 JavaScript。
title: 开始在控制台中运行 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
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







# 开始在控制台中运行 JavaScript   



此交互式教程介绍如何在 Microsoft Edge DevTools **控制台**中运行 JavaScript。  有关如何将消息记录到 **控制台**的详细信息，请参阅 [记录消息入门][DevToolsConsoleLoggingMessages]。  有关如何暂停 JavaScript 代码并一次单步执行一行的详细信息，请参阅 [开始使用调试 JavaScript][DevToolsJavascriptIndex]。  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="该控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   该 **控制台**  
:::image-end:::  

## 概述   

该 **控制台** 是一个 [复制][WikiReadEvalPrintLoop]，它代表读取、计算、打印和循环。  它将读取你在其中键入的 JavaScript，计算你的代码，打印你的 [表达式][2alityExpressionsVersusStatements]的结果，然后循环回到第一步。  

## 设置 DevTools   

本教程旨在让你打开演示并自行尝试所有工作流。  当您进行物理跟踪时，更有可能会在以后记忆工作流。

1.  按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开**控制台**。  
1.  保留 `Control` \ (Windows \ ) 或 `Command` \ (macOS \ ) ，然后单击 " **Console Javascript 示例** " 以在新窗口中打开。  
    
    *   [控制台 Javascript 示例][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="控制台 JavaScript 示例页面位于左侧，DevTools 在右侧" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       控制台 JavaScript 示例页面位于左侧，DevTools 在右侧  
    :::image-end:::  
    
## 查看和更改页面的 JavaScript 或 DOM   

生成或调试页面时，在 **控制台** 中运行语句以更改页面的外观和运行方式通常很有用。  
    
1.  注意按钮中的文本。  
1.  `document.getElementById('hello').textContent = 'Hello, Console!'`在**控制台**中键入，然后按 `Enter` 以计算表达式。  注意按钮内的文本如何更改。  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="计算表达式后的控制台外观" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       计算表达式后的 **控制台** 外观  
    :::image-end:::  
    
    在你所评估的代码下方看到 `"Hello, Console!"` 。  撤回复制操作的4个步骤：读取、评估、打印、循环。  在计算代码后，复制将打印表达式的结果。  因此 `"Hello, Console!"` 必须是评估结果 `document.getElementById('hello').textContent = 'Hello, Console!'` 。  
    
## 运行与页面无关的任意 JavaScript   

有时，你只需要一个代码背景，你可以在其中测试某些代码，或者尝试你不熟悉的新 JavaScript 功能。  控制台是这些类型的实验的理想位置。  

1.  `5 + 15`在控制台中键入，然后按 `Enter` 以计算表达式。 该控制台将打印出你的代码下方的表达式的结果。  在下图中，你的 **控制台** 应在计算表达式后显示结果。  

1.  在 **控制台**中键入以下代码。  尝试按字符键入，而不是复制粘贴。  
    
    ```javascript
    function add(a, b=20) { return a + b; }
    ```  
    
    如果不熟悉 `b=20` 语法，请参阅 [定义函数参数的默认值][Esma6DefaultParameterValues]。  
    
1.  现在，运行刚定义的函数。  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="在计算代码段中的表达式后，将显示该控制台" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             在计算代码段中的表达式后，将显示该**控制台**  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` 计算结果为 `45` ：当 `add` 调用函数时不带第二个参数时， `b` 默认为 `20` 。  

## 后续步骤   

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

DevTools 允许你在运行期间暂停脚本。  暂停时，您可以使用该 **控制台** 查看和更改 `window` `DOM` 该时刻的页面或页面。  工作流可用于功能强大的调试工作流。  有关交互式教程，请参阅 [开始使用调试 JavaScript][DevToolsJavascriptIndex]。  

该 **控制台** 还具有一组便利功能，使您能够更轻松地与页面交互。  例如：  

*   键入，而不是键入 `document.querySelector()` 来选择元素 `$()` 。  此语法是 jQuery 的灵感，但实际上并不是 jQuery。  它只是的一个别名 `document.querySelector()` 。  
*   `debug(function)` 在该函数的第一行上有效地设置断点。  
*   `keys(object)` 返回包含指定对象的键的数组。  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/javascript)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
