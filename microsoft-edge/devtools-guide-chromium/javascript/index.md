---
description: 了解如何使用 Microsoft Edge DevTools 查找和修复 JavaScript bug。
title: 在 Microsoft Edge DevTools 中开始使用调试 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: bff87ca36c484689134f284514bbab353b8b99b6
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124787"
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

# 在 Microsoft Edge DevTools 中开始使用调试 JavaScript  

本教程将指导你在 DevTools 中调试 JavaScript 问题的基本工作流。  

## 步骤1：重现 bug  

在调试的第一步中始终是查找始终重现 bug 的一系列操作。  

1.  选择 " **打开演示**"。  保留 `Control` \ (Windows、Linux \ ) 或 `Command` \ (macOS \ ) 并在新选项卡中打开演示。  
    
    [打开演示][OpenDebugJSDemo]  
    
1.  `5`在 "**数字 1** " 文本框中输入。  
1.  `1`在 "**数字 2** " 文本框中输入。  
1.  选择 " **添加号码 1" 和 "数字 2**"。  按钮下方的标签显示 "" `5 + 1 = 51` 。  结果应为 `6` 。  这是你要修复的 bug。  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       Is 的结果 `5 + 1` 是 `51` ，但应该 `6`  
    :::image-end:::  
    
## 步骤2：熟悉 "源" 面板 UI  

DevTools 为不同的任务提供了许多不同的工具，例如更改 CSS、分析页面加载性能和监视网络请求。  " **源** " 面板是你在其中调试 JavaScript 的位置。  

1.  按 `Control` + `Shift` + `J` \ (Windows、Linux \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开 DevTools。  此快捷方式将打开 **控制台** 面板。  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-console-empty.msft.png":::
       **控制台**面板  
    :::image-end:::  
    
1.  单击 " **源** " 选项卡。  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-sections.msft.png":::
       " **源** " 面板  
    :::image-end:::  
    
" **源** " 面板 UI 有3个部分。  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   " **源** " 面板 UI 的3个部分  
:::image-end:::  

1.  " **文件导航器** " 窗格 \ (上图中的第一节 \ ) 。  页面请求的每个文件都在此处列出。  
1.  " **代码编辑器** " 窗格 \ (上图中的第二部分 \ ) 。  在 " **文件导航器** " 窗格中选择文件后，该文件的内容将显示在此处。  
1.  **JavaScript 调试**窗格 \ 上图中 (第3节 ) 。  用于检查页面的 JavaScript 的各种工具。  如果 DevTools 窗口宽，此窗格将显示在 " **代码编辑器** " 窗格的右侧。  
    
## 步骤3：使用断点暂停代码  

调试此类问题的常见方法是将许多语句插入到 `console.log()` 代码中，以便在脚本运行时检查值。  例如：  

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

此 `console.log()` 方法可能会使作业完成，但 **断点** 能够更快地完成工作。  断点使你可以在运行时中间暂停代码，并在该时刻检查所有值。  与方法相比，断点有几个优点 `console.log()` ：  

*   通过 `console.log()` ，你需要手动打开源代码，查找相关代码，插入 `console.log()` 语句，然后重新加载页面，以便在控制台中查看消息。  利用断点，您可以暂停在相关代码上，而无需了解代码的结构。  
*   在你的 `console.log()` 语句中，你需要显式指定要检查的每个值。  有了断点，DevTools 将显示当时的所有变量的值。  有时，你甚至不知道的代码会影响你的代码。  

简言之，断点可帮助你查找和修复 bug，比方法更快 `console.log()` 。  

如果返回一个步骤并考虑应用的工作方式，则可以让你有兴趣地猜测) 的 sum (`5 + 1 = 51` 在 `click` 与 " **Add Number 1" 和 "number 2** " 按钮关联的事件侦听器中得到计算。  因此，你可能希望在侦听器运行的时间周围暂停代码 `click` 。  **事件侦听器断点** 使你可以执行以下操作：  

1.  在 " **JavaScript 调试** " 窗格中，选择 " **事件侦听器断点** " 以展开该部分。  DevTools 显示可展开的事件类别（如 **动画** 和 **剪贴板**）的列表。  
1.  在 **鼠标** 事件类别旁边，选择 **展开** \ (![ 展开图标 ][ImageExpandIcon] \ ) 。  DevTools 显示鼠标事件（如 **单击** 和 **mousedown**）的列表。  每个事件旁边都有一个复选框。  
1.  选中 " **单击** " 复选框。  DevTools 现已设置为在 *任何* `click` 事件侦听器运行时自动暂停。  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       已启用 " **单击** " 复选框  
    :::image-end:::  
    
1.  返回演示，再次选择 " **添加号码 1" 和 "数字 2** "。  DevTools 暂停演示并突出显示 " **源** " 面板中的一行代码。  DevTools 应在的行16中暂停 `get-started.js` 。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    如果在其他代码行上暂停，请按 " **恢复脚本执行** " \ (![ 恢复脚本执行 ][ImageResumeIcon] \ ) ，直到暂停在正确的行上。  
    
    > [!NOTE]
    > 如果你在其他行暂停，则你有一个浏览器扩展，它 `click` 在你访问的每个页面上注册一个事件侦听器。  已暂停在扩展的 `click` 侦听器中。  如果你使用 InPrivate 模式 **浏览 private**（这将禁用所有扩展），你可能会看到每次都在所需的代码行上暂停。  

<!--todo: add inprivate section when available -->  

**事件侦听器断点** 只是 DevTools 中可用的多种类型的断点之一。  它值得 memorizing 所有不同类型，因为每种类型最终有助于尽可能快地调试不同的方案。  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## 步骤4：逐句通过代码  

Bug 的一个常见原因是，脚本的运行顺序不正确。  单步执行你的代码，使你能够遍历代码的运行时，一次一行，然后以与预期不同的顺序确定其运行的确切位置。  立即试用：  

1.  选择 " **逐过程按下一个函数调用** \" ("按 ![ 步骤 over 下一个函数调用 ][ImageOverIcon] \" ) 。  DevTools 在不单步执行的情况下运行以下代码。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > DevTools 跳过几行代码。  这是因为 `inputsAreEmpty()` 计算结果为 false，因此语句的代码块不 `if` 会运行。  
    
1.  在 DevTools 的 " **源** " 面板中，选择 " **单步执行下一个函数调用** \" (![ "单步执行下一个函数调用 \ ) " 单步执行 ][ImageIntoIcon] 函数的运行时 `updateLabel()` ，一次一行。  
    
这是单步执行代码的基本概念。  如果你查看中的代码 `get-started.js` ，则会发现该 bug 可能位于函数中的某个位置 `updateLabel()` 。  你可以使用另一种类型的断点将代码暂停到更接近 bug 可能位置的位置，而不是单步执行每行代码。  

## 步骤5：设置代码行断点  

代码行断点是最常见的断点类型。  获取要暂停的特定代码行时，请使用代码行断点：  

1.  查看以下代码中的最后一行代码 `updateLabel()` ：  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  在代码的左侧，你可以看到此特定代码行的行号，即 **33**。  单击 " **33**"。  DevTools 将红色图标置于 **33**的左侧。  这意味着此行上有一行代码断点。  DevTools 现在将始终暂停，然后运行此行代码。  
1.  选择 " **恢复脚本执行** " \ (![ 恢复脚本执行 ][ImageResumeIcon] \ ) 。  脚本将继续运行，直至到达行33。  在30、31和32行上，DevTools 将在 `addend1` `addend2` `sum` 每一行的分号的右侧打印值。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       DevTools 在行32上的代码行断点处暂停  
    :::image-end:::  
    
## 步骤6：检查变量值  

`addend1`、 `addend2` 和 `sum` 看起来可疑的值。  它们包装在引号中，这意味着它们是字符串。  这是介绍 bug 原因的一个好假设。  现在是收集更多信息的时候了。  DevTools 提供许多用于检查变量值的工具。  

### 方法1： "范围" 窗格  

当你在一行代码上暂停时， **范围** 窗格将显示当前定义的本地和全局变量以及每个变量的值。  它还显示结束变量（如果适用）。  双击变量值以对其进行编辑。  如果在一行代码上未暂停，则 " **范围** " 窗格为空。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   " **范围** " 窗格  
:::image-end:::  

### 方法2：监视表达式  

通过 " **监视表达式** " 选项卡，你可以监视一段时间内变量的值。  顾名思义，监视表达式不仅仅局限于变量。  你可以在监视表达式中存储任何有效的 JavaScript 表达式。  立即试用：  

1.  单击 " **监视** " 选项卡。  
1.  选择 " **添加表达式** \ (![ 添加表达式 ][ImageAddIcon] \ ) "。  
1.  键入 `typeof sum`。  
1.  选择 `Enter` 。  DevTools 显示 `typeof sum: "string"` 。  冒号右侧的值是监视表达式的结果。  
    
> [!NOTE]
> 在 "监视表达式" 窗格中 (右下角 \ ) 在下图中， `typeof sum` 显示监视表达式。  如果 DevTools 窗口较大，"监视表达式" 窗格位于 " **事件侦听器断点** " 窗格上方的右侧。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   " **监视表达式** " 窗格  
:::image-end:::  

如有怀疑， `sum` 当它应该是一个数字时，将被评估为字符串。  您现在已确认这是该 bug 的原因。  

### 方法3：控制台  

除了查看消息外 `console.log()` ，你还可以使用 Console 评估任意 JavaScript 语句。  在调试方面，您可以使用该控制台测试 bug 的潜在修复。  立即试用：  

1.  如果未打开该控制台抽屉，请选择 `Escape` 将其打开。  它将在 DevTools 窗口底部打开。  
1.  在控制台中，键入 `parseInt(addend1) + parseInt(addend2)` 。  此语句之所以有效，是因为你已暂停在范围内和的代码行上 `addend1` `addend2` 。  
1.  选择 `Enter` 。  DevTools 将计算该语句并将 `6` 其打印出来，这是你希望演示产生的结果。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="5 + 1 的结果是51，但应该是6" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       评估后的 **控制台** 抽屉 `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## 步骤7：应用修补程序  

如果发现 bug 的修补程序，请通过编辑代码并重新运行演示来尝试修复。  无需离开 DevTools 即可应用此修补程序。  你可以直接在 DevTools UI 内编辑 JavaScript 代码。  立即试用：  

1.  选择 " **恢复脚本执行** " \ (![ 恢复脚本执行 ][ImageResumeIcon] \ ) 。  
1.  在 **代码编辑器**中，将行32替换 `var sum = addend1 + addend2` 为 `var sum = parseInt(addend1) + parseInt(addend2)` 。  
1.  选择 `Control` + `S` \ (Windows、Linux \ ) 或 `Command` + `S` \ (macOS \ ) 保存您的更改。  
1.  选择 " **停用断点** \ (![ 停用断点 ][ImageDeactivateIcon] \ ) "。  它将更改为蓝色，以指示它处于活动状态。  设置此设置时，DevTools 忽略你设置的任何断点。  
1.  试用具有不同值的演示。  演示现在能够正确计算。  
    
> [!CAUTION]
> 此工作流仅将修补程序应用于浏览器中运行的代码。  它不会修复访问您的页面的所有用户的代码。  若要执行此操作，您需要修复服务器上的代码。  

## 后续步骤  

恭喜你！  你现在知道如何在调试 JavaScript 时充分利用 Microsoft Edge DevTools。  您在本教程中学到的工具和方法可能会为您节省无数小时。  

本教程仅介绍两种设置断点的方法。  DevTools 提供了许多其他方法，包括以下设置。  

*   仅当你提供的条件为 true 时才触发的条件断点。  
*   已捕获或未捕获的异常上的断点。  
*   当请求的 URL 与你提供的子字符串匹配时触发的 XHR 断点。  
    
有关何时以及如何使用每种类型的详细信息，请转到 [使用断点暂停代码][DevtoolsJavscriptBreakpoints]。  

本教程中有一些代码步进控件未介绍。  有关详细信息，请转到 [代码行][DevtoolsJavascriptReferenceStepThroughCode]。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: ../media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageIntoIcon]: ../media/step-into-icon.msft.png  
[ImageOverIcon]: ../media/step-over-icon.msft.png  
[ImageResumeIcon]: ../media/resume-script-run-icon.msft.png  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools 中暂停带有断点的代码 |Microsoft 文档"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "逐句通过代码-JavaScript 调试参考 |Microsoft 文档"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示 |故障"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
