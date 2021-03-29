---
description: 了解如何使用 Microsoft Edge 开发工具查找并修复 JavaScript bug。
title: 在 Microsoft Edge DevTools 中调试 JavaScript 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: bbfb766bcc03e4c4fe0f975f1ecfccbef08084be
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439463"
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
# <a name="get-started-with-debugging-javascript-in-microsoft-edge-devtools"></a>在 Microsoft Edge DevTools 中调试 JavaScript 入门  

本文指导你如何在开发工具中调试 JavaScript 问题的基本工作流程。  

## <a name="step-1-reproduce-the-bug"></a>步骤 1：重现 Bug  

查找一系列持续重现 Bug 的操作始终是调试的第一步。  

1.  选择“**打开演示**”。  按住 `Control` \(Windows, Linux\) 或 `Command` \(macOS\) ，然后在新的浏览器选项卡中打开演示。  
    
    [打开演示][OpenDebugJSDemo]  
    
1.  在“**数字 1 **”文本框中输入 `5`。  
1.  在“**数字 2 **”文本框中输入 `1`。  
1.  选择“**添加数字 1 和数字 2**”。  按钮下方的标签显示 `5 + 1 = 51`。  结果应为 `6`。  接下来，修复作为 bug 的加法错误。  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果为 51，但应为 6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` 结果为 `51` ，但应为 `6`  
    :::image-end:::  
    
## <a name="step-2-get-familiar-with-the-sources-tool-ui"></a>步骤 2：熟悉源工具 UI  

开发工具为不同的任务提供了许多工具。  不同的任务包括更改 CSS、分析页面加载性能以及监视网络请求。  **源**工具是调试 JavaScript 的地方。  

1.  如果要在开发工具中打开**控制台**工具，选择 `Control`+`Shift`+`J` \(Windows, Linux\) 或 `Command`+`Option`+`J` \(macOS\)。  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="控制台工具" lightbox="../media/javascript-console-empty.msft.png":::
       **控制台**工具  
    :::image-end:::  
    
1.  选择“**源**”工具。  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="源工具" lightbox="../media/javascript-sources-sections.msft.png":::
       **源**工具  
    :::image-end:::  
    
**源**工具 UI 有三个部分。  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="源工具 UI 的 3 个部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   **源**工具 UI 的 3 个部分  
:::image-end:::  

1.  **文件导航器**窗格\(上图中的第 1 部分\)。  此处列出了网页请求的所有文件。  
1.  **代码编辑器**窗格\(上图中的第 2 部分\)。  在**文件导航器**窗格中选择一个文件后，文件的内容在此处显示。  
1.  **JavaScript 调试**窗格\(上图中的第 3 部分\)。  用于检查网页的 JavaScript 的各种工具。  如果开发工具的窗口很宽，则此窗格显示在**代码编辑器**窗格的右侧。  
    
## <a name="step-3-pause-the-code-with-a-breakpoint"></a>步骤 3：使用断点暂停代码  

调试此类问题的常见方法是在代码中插入多个 `console.log()` 语句，然后在脚本运行时检查值。  例如：  

```javascript
function updateLabel() {
    var addend1 = getNumber1();
    console.log('addend1:', addend1);
    var addend2 = getNumber2();
    console.log('addend2:', addend2);
    var sum = addend1 + addend2;
    console.log('sum:', sum);
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
}
```  

`console.log()` 方法可​​以完成工作，但是**断点**可以更快地完成工作。  断点允许在运行时中间暂停代码，并检查此时的所有值。  与`console.log()`方法相比，断点具有以下优点。  

*   使用 `console.log()`，需要手动打开源代码，找到相关代码，插入 `console.log()` 语句，然后刷新网页以在**控制台**中显示消息。  使用断点，可能会暂停相关代码，甚至不知道代码的结构。  
*   在 `console.log()` 语句中，需要显式指定要检查的每个值。  通过断点，开发工具会及时显示所有变量的值。  有时，影响代码的变量被隐藏和混淆。  
    
简而言之，断点可以比 `console.log()` 方法更快地查找和修复错误。  

如果退后一步，想一想应用程序的工作方式，可能会做出有根据的猜测，即在与**添加数字 1 和数字 2**按钮相关联的 `click`事件侦听器中计算出错误的总和 \(`5 + 1 = 51`\)。  因此，可能想在 `click` 侦听器运行期间暂停代码。  **事件侦听器断点**可以完全实现此要求：  

1.  在 “**JavaScript 调试**”窗格中，选择“**事件侦听器断点**”以展开该部分。  开发工具显示可展开事件类别的列表，如**动画**和**剪贴板**。  
1.  在**鼠标**事件类别旁，选择“**展开**” \(![展开图标](../media/expand-icon.msft.png)\)。  开发工具显示鼠标事件的列表，如**单击**和**鼠标按下**。  每个事件旁边都有一个复选框。  
1.  选中“**单击**”旁边的复选框。  现在开发工具设置为在运行任何 `click` 事件侦听器时自动暂停。  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="选中“单击”旁边的复选框" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       选中“**单击**”旁边的复选框  
    :::image-end:::  
    
1.  返回到演示，再次选择“**添加数字 1 和"数字 2**”。  开发工具暂停演示并在“**源**”具中突出显示一行代码。  开发工具应该暂停在 `get-started.js` 中的第 16 行。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    如果在其他代码上暂停，请选择“**继续执行脚本**” \(![继续执行脚本](../media/resume-script-run-icon.msft.png)\)，直到在正确的行上暂停。  
    
    > [!NOTE]
    > 如果在另一行暂停，则将拥有一个浏览器扩展，此扩展会在你访问的每个网页上注册一个 `click` 事件侦听器。  你已在扩展的 `click` 侦听器中暂停。  如果使用 InPrivate 模式以**在专用模式中浏览**，这会禁用所有扩展，可能会看到每次在指定的代码行上暂停。  

<!--todo: add inprivate section when available -->  

**事件侦听器断点**只是开发工具中提供的许多类型的断点之一。  记住所有不同的类型，以帮助你尽快调试不同的方案。  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <a name="step-4-step-through-the-code"></a>步骤 4：单步执行代码  

Bug 的一个常见原因是脚本以错误的顺序运行。  单步执行代码允许你演练代码的运行时。  一次浏览一行，以准确确定代码的位置以与不同的顺序运行。  立即尝试：  

1.  选择“**单步跳过下一函数调用**” \(![单步跳过下一函数调用](../media/step-over-icon.msft.png)\)。  DevTools 无需步入即可运行以下代码。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > 开发工具跳过几行代码。  这是因为 `inputsAreEmpty()` 的计算结果为 false，因此 `if` 语句的代码块不会运行。  
    
1.  在开发工具的“** 源**”工具上，选择”**单步执行下一函数调用**” \(![单步执行下一函数调用](../media/step-into-icon.msft.png)\) 以逐步运行 `updateLabel()` 函数，一次一行。  
    
一次查看一行是单步执行代码的基本概念。  如果查看 `get-started.js` 中的代码，则该错误可能在 `updateLabel()` 函数中。  可以使用另一种类型的断点来将代码暂停在错误的可能位置附近，而不是单步执行代码的每一行。  

## <a name="step-5-set-a-line-of-code-breakpoint"></a>步骤 5：设置代码行断点  

代码行断点是最常见的断点类型。  到达要暂停的特定代码行时，使用代码行断点。  

1.  查看 `updateLabel()` 中的最后一行代码：  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  在左侧，此特定代码行的编号显示为 **34**。  选择第 **34** 行。  开发工具在 **34** 的左侧显示一个红色图标。  红色图标表示代码行断点位于此行上。  开发工具始终在运行此代码行之前暂停。  
1.  选择“**继续脚本执行**” \(继续脚本执行 ![ ](../media/resume-script-run-icon.msft.png) \)。  脚本将继续运行，直到到达第 33 行。  在第 31、32 和 33 行上，开发工具在每行的分号右边打印`addend1`、`addend2` 和 `sum` 的值。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="开发工具在第 34 行的代码行断点处暂停" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       开发工具在第 34 行的代码行断点处暂停  
    :::image-end:::  
    
## <a name="step-6-check-variable-values"></a>步骤 6：检查变量值  

`addend1`、`addend2` 和 `sum` 的值看起来可疑。  这些值用引号括起来。  引号表示此值是一个字符串，这是解释错误原因的一个很好的假设。  收集有关情况的更多信息。  开发工具提供了许多用于检查变量值的工具。  

### <a name="method-1-the-scope-panel"></a>方法 1：作用域窗格  

如果暂停在一行代码上，**作用域**面板将显示当前定义的局部变量和全局变量以及每个变量的值。  如果适用，它还会显示关闭变量。  双击变量值进行编辑。  如果未在代码行上暂停，则“**作用域**”窗格为空。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="作用域窗格" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   **作用域**窗格  
:::image-end:::  

### <a name="method-2-watch-expressions"></a>方法 2：监视表达式  

通过**监视表达式**窗格，可随着时间监视变量值。  正如该名称所示， **监视表达式**不限于变量。  可以将任何有效的 JavaScript 表达式存储在**监视表达式**中。  立即尝试。  

1.  选择**监视**窗格。  
1.  选择**添加表达式** \(![添加表达式](../media/add-expression-icon.msft.png)\)。  
1.  键入 `typeof sum`。  
1.  选择 `Enter`。  开发工具显示 `typeof sum: "string"`。  冒号右边的值是监视表达式的结果。  
    
> [!NOTE]
> 在下图的“**监视表达式**窗格”\(右下\)中，显示 `typeof sum`“监视表达式”。  如果开发工具窗口很大，则**监视表达式**窗格位于**事件侦听器断点**窗格的右侧。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="监视表达式窗格" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   **监视表达式**窗格  
:::image-end:::  

正如猜想的那样，如果应为数字， `sum` 被评估为字符串。  现在确认值类型是 Bug 的原因。  

### <a name="method-3-the-console"></a>方法 3：控制台  

**控制台**允许查看 `console.log()` 消息，也可以使用它来评估任意 JavaScript 语句。  为了进行调试，可以使用**控制台**测试潜在的 bug 修补程序。  立即尝试。  

1.  如果**控制台**工具已关闭，请选择 `Escape` 以将其打开。  **控制台**工具将在开发工具窗口的下部窗格中打开。  
1.  在**控制台**中，键入 `parseInt(addend1) + parseInt(addend2)`。  工具的语句暂停在作用域为 `addend1` 和 `addend2` 的代码行上。  
1.  选择 `Enter`。  开发工具将评估该语句并打印 `6`，这是预期演示生成的结果。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="评估 parseInt (addend1) + parseInt (addend2) 后的控制台工具" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       评估后的**控制台**工具 `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <a name="step-7-apply-a-fix"></a>步骤 7：应用修补程序  

如果找到该 Bug 的修补程序，请通过编辑代码并重新运行演示来尝试修复。  可以直接在开发工具 UI 中编辑 JavaScript 代码并应用修补程序。  立即尝试。  

1.  选择“**继续脚本执行**” \(继续脚本执行 ![ ](../media/resume-script-run-icon.msft.png) \)。  
1.  在**代码编辑器**中，将第 32 行、`var sum = addend1 + addend2` 替换为 `var sum = parseInt(addend1) + parseInt(addend2)`。  
1.  选择 `Control`+`S` \(Windows、Linux\) 或 `Command`+`S` \(macOS\) 以保存更改。  
1.  选择“**停用断点**” \(![停用断点](../media/deactivate-breakpoints-button-icon.msft.png) \)。  它将更改蓝色，以指示选项处于活动状态。  设置“**停用断点**”时，开发工具会忽略你设置的任何断点。  
1.  尝试使用具有不同值的演示。  演示现在计算正确。  
    
> [!CAUTION]
> 此工作流程仅将修复程序应用于浏览器中正在运行的代码。  它不会修复访问网页的所有用户的代码。  为此，需要修复服务器上的代码。  

## <a name="next-steps"></a>后续步骤  

祝贺你！  现在，你已了解如何在调试 JavaScript 时充分利用 Microsoft Edge 开发工具。  本文中学习的工具和方法可以为你节省很多时间。  

本文仅为你提供两种设置断点的方法。  开发工具提供了许多其他方法，包括以下设置。  

*   仅在提供的条件为 true 时触发的条件断点。  
*   已捕获或未捕获异常的断点。  
*   请求的 URL 与提供的子字符串匹配时触发的 XHR 断点。  
    
有关何时以及如何使用每种类型的更多信息，请导航至[使用断点暂停代码][DevtoolsJavscriptBreakpoints]。  

本文不介绍几个代码单步执行控件。  有关详细信息，请导航到“[单步跳过代码行][DevtoolsJavascriptReferenceStepThroughCode]”。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge 开发工具中使用断点暂停代码 | Microsoft Doc"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "单步执行代码 - JavaScript 调试引用 |Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示 | 故障"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
