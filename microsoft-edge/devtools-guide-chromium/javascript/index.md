---
description: 了解如何使用 Microsoft Edge DevTools 查找和修复 JavaScript Bug。
title: 在 Microsoft Edge DevTools 中调试 JavaScript 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/09/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b036fc87149d13446ab1bc05afc8fc8631d27c8d
ms.sourcegitcommit: e737277744dd25a7585c113eef22a2aa4d4c167f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "11325944"
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
# 开始在 Microsoft Edge DevTools 中调试 JavaScript  

本文将指导你调试 DevTools 中任何 JavaScript 问题的基本工作流。  

## 步骤 1：重现 Bug  

查找一系列持续重现 Bug 的操作始终是调试的第一步。  

1.  选择 **"打开演示"。**  按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后打开新浏览器选项卡中的演示。  
    
    [打开演示][OpenDebugJSDemo]  
    
1.  在 `5` 数字 **1 文本框** 中输入。  
1.  在 `1` " **数字 2"** 文本框中输入。  
1.  选择 **"添加数字 1"和"数字 2"。**  按钮下方的标签显示 `5 + 1 = 51` 。  结果应为 `6` 。  接下来，修复作为 Bug 的添加错误。  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果为 51，但应为 6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` 结果， `51` 但应 `6`  
    :::image-end:::  
    
## 步骤 2：熟悉源面板 UI  

DevTools 为不同的任务提供了许多不同的工具。  不同的任务包括更改 CSS、分析页面加载性能和监视网络请求。  " **源** "面板是调试 JavaScript 的地方。  

1.  按 \ (`Control` + `Shift` + `J` Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开 DevTools。  此快捷方式将打开 **控制台** 面板。  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="控制台面板" lightbox="../media/javascript-console-empty.msft.png":::
       控制台**工具**  
    :::image-end:::  
    
1.  选择 **"源"** 工具。  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text=""源"面板" lightbox="../media/javascript-sources-sections.msft.png":::
       " **源"** 面板  
    :::image-end:::  
    
源 **面板** UI 有三个部分。  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="源面板 UI 的 3 个部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   源面板 UI 的 3**个部分**  
:::image-end:::  

1.  文件 **导航器** 窗格 \ (上图的第 1 部分\) 。  此处列出了网页请求的所有文件。  
1.  " **代码编辑器** "窗格 \ (上图的第 2 部分\) 。  在"文件导航器"**** 窗格中选择文件后，该文件的内容会显示在此处。  
1.  上 **图中的 JavaScript** 调试窗格 \ (Section 3\) 。  用于检查网页的 JavaScript 的各种工具。  如果 DevTools 窗口很宽，则此窗格显示在代码编辑器 **窗格的右侧** 。  
    
## 步骤 3：使用断点暂停代码  

调试此类问题的常见方法是在代码中插入多个语句，然后在脚本运行时 `console.log()` 检查值。  例如：  

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

`console.log()`虽然该方法可能会完成工作，但断点可以**** 更快地完成。  断点允许你在运行时中间暂停代码，并检查当时的所有值。  断点与该方法相比有一 `console.log()` 些优势：  

*   With `console.log()` ， you need to manually open the source code， find the relevant code， insert the `console.log()` statements， and then refresh the webpage to display the messages in the **Console.**  使用断点时，您可能会暂停相关代码，甚至不知道代码的构建方式。  
*   在 `console.log()` 语句中，需要显式指定要检查的每个值。  使用断点时，DevTools 将同时显示所有变量的值。  有时，影响代码的变量被隐藏和混淆。  
    
简而言之，断点可以帮助你更快地查找和修复 `console.log()` Bug，而不是方法。  

如果你后退一步并思考应用的工作原理，你可能会有根据地猜测错误的总和 \ (\) 是在与"添加数字 1"和"数字 `5 + 1 = 51` `click` **2"** 按钮关联的事件侦听器中计算的。  因此，您可能想要在侦听器运行时暂停 `click` 代码。  **事件侦听器断点** 让你可以完全实现此要求：  

1.  在 **JavaScript 调试** 窗格中，选择 **事件侦听器断点** 以展开该部分。  DevTools 显示可展开事件类别的列表，如 **动画** 和 **剪贴板**。  
1.  在" **鼠标** 事件"类别旁边， **选择"** 展开 (![ 展开图标 ][ImageExpandIcon] \) 。  DevTools 显示鼠标事件的列表，如 **单击** 和 **鼠标按下**。  每个事件旁边都有一个复选框。  
1.  选中复选框，单击 **旁边的复选框**。  DevTools 现在设置为在任何事件侦听器运行时 `click` 自动暂停。  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="选中单击旁边的复选框" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       选中单击旁边的 **复选框**  
    :::image-end:::  
    
1.  返回到演示，再次选择"**添加数字 1"和"数字 2"。**  DevTools 暂停演示，并突出显示"源"面板中的一 **行** 代码。  DevTools 应在 第 16 行中暂停 `get-started.js` 。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    如果暂停另一行代码，请按 Resume **Script Execution** \ (![ Resume Script Execution ][ImageResumeIcon] \) 直到您暂停到正确的行。  
    
    > [!NOTE]
    > 如果您在另一行上暂停，则具有一个浏览器扩展，该扩展在所访问的每一个网页上注册 `click` 事件侦听器。  你已暂停到 `click` 扩展的侦听器中。  如果使用 InPrivate 模式在**** 禁用所有扩展的专用模式下进行浏览，你可能会看到每次在所需的代码行上暂停。  

<!--todo: add inprivate section when available -->  

**事件侦听器断点** 只是 DevTools 中提供的许多类型的断点之一。  记住所有不同类型的内容，以帮助你尽快调试不同的方案。  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## 步骤 4：逐步执行代码  

出现 Bug 的一个常见原因是脚本按错误的顺序运行。  单步执行代码允许你演练代码的运行时。  一次完成一行，以帮助你准确了解代码以与预期不同的顺序运行在哪里。  立即尝试：  

1.  Choose **Step over next function call** \ (Step over next function call ![ ][ImageOverIcon] \) .  DevTools 无需单步执行即可运行以下代码。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > DevTools 跳过几行代码。  这是因为计算 `inputsAreEmpty()` 结果为 false，因此语句的代码块 `if` 不会运行。  
    
1.  在**** DevTools 的"源"面板上，选择"单步执行下一个函数调用**\ (** 单步执行下一个函数调用 ![ ][ImageIntoIcon] \) 以单步执行函数运行时，一次一行。 `updateLabel()`  
    
一次查看一行是逐步执行代码的一个基本概念。  如果您查看其中的代码 `get-started.js` ，则会看到该 Bug 可能位于函数 `updateLabel()` 中的某一位置。  与其逐行执行每行代码，不如使用另一种类型的断点将代码暂停到更接近 bug 的可能位置的位置。  

## 步骤 5：设置代码行断点  

代码行断点是最常见的断点类型。  当您到达要暂停的特定代码行时，请使用代码行断点。  

1.  查看以下代码的最后一行 `updateLabel()` ：  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  在左侧，此特定代码行的编号显示为**34。**  选择第 **34 行**。  DevTools 将红色图标放在 **34 的左侧**。  红色图标表示代码行断点位于此行上。  DevTools 始终在运行此代码行之前暂停。  
1.  Choose **Resume script execution** \ (Resume script execution ![ ][ImageResumeIcon] \) .  脚本继续运行，直到到达第 33 行。  在行 31、32 和 33 上，DevTools 在每行中打印分号的右边和 `addend1` `addend2` `sum` 分号的值。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools 暂停于第 34 行的代码行断点上" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       DevTools 暂停于第 34 行的代码行断点上  
    :::image-end:::  
    
## 步骤 6：检查变量值  

， `addend1` `addend2` 的值， `sum` 看起来可疑。  这些值用引号括起来。  引号表示值是一个字符串，这是一个很好的假设，可以解释 Bug 的原因。  收集有关情况详细信息。  DevTools 提供了许多用于检查变量值的工具。  

### 方法 1：范围窗格  

如果暂停一行代码，"范围"窗格**** 将显示当前定义的本地和全局变量以及每个变量的值。  它还会显示关闭变量（如果适用）。  双击变量值进行编辑。  如果不在代码行上暂停，则 **"范围"** 窗格为空。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text=""范围"窗格" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   " **范围"** 窗格  
:::image-end:::  

### 方法 2：监视表达式  

通过 **"** 监视表达式"窗格，可以随着时间的推移监视变量的值。  正如名称所示， **监视表达式** 不限于变量。  你可以将任何有效的 JavaScript 表达式存储在 **监视表达式中**。  立即尝试。  

1.  选择 **"监视"** 窗格。  
1.  Choose **Add Expression** \ (Add Expression ![ ][ImageAddIcon] \) .  
1.  键入 `typeof sum`。  
1.  选择 `Enter`。  DevTools 显示 `typeof sum: "string"` 。  冒号右边的值是监视表达式的结果。  
    
> [!NOTE]
> 在" **监视表达式** "窗格 \ (右下\) 中，将显示 `typeof sum` 监视表达式。  如果 DevTools 窗口很大，则 **监视** 表达式窗格位于事件侦听器断点窗格 **的右侧** 。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="监视表达式窗格" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   监视 **表达式** 窗格  
:::image-end:::  

正如所怀疑的，当应为数字时，正在作为字符串 `sum` 进行评估。  现在确认值类型是 Bug 的原因。  

### 方法 3：控制台  

控制台 **允许你** 查看消息，还可以使用它来评估 `console.log()` 任意 JavaScript 语句。  对于调试，可以使用 **控制台** 测试潜在 Bug 修复。  立即尝试。  

1.  如果 **控制台收** 银机已关闭，请选择 `Escape` 将其打开。  控制台 **箱** 在 DevTools 窗口的下面板中打开。  
1.  在控制台 **中**，键入 `parseInt(addend1) + parseInt(addend2)` 。  工具的语句暂停在一行代码上，并且 `addend1` `addend2` 位于范围内。  
1.  选择 `Enter`。  DevTools 计算语句并打印 `6` ，这是预期演示产生的结果。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="在评估 parseInt (addend1) + parseInt (addend2) " lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       评估 **后的** 控制台箱 `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## 步骤 7：应用修补程序  

如果找到该 Bug 的修复程序，请通过编辑代码并重新运行演示来尝试修复。  你可以直接在 DevTools UI 中编辑 JavaScript 代码并应用修复程序。  立即尝试。  

1.  Choose **Resume script execution** \ (Resume script execution ![ ][ImageResumeIcon] \) .  
1.  在代码 **编辑器中**，将第 32 行替换为 `var sum = addend1 + addend2` `var sum = parseInt(addend1) + parseInt(addend2)` 。  
1.  选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。  
1.  Choose **Deactivate breakpoints** \ (![ Deactivate breakpoints ][ImageDeactivateIcon] \) .  它更改为蓝色以指示选项处于活动状态。  在 **设置 Deactivate** 断点时，DevTools 将忽略你设置的任何断点。  
1.  尝试使用不同值的演示。  演示现在计算正确。  
    
> [!CAUTION]
> 此工作流仅对浏览器中运行的代码应用修补程序。  它不会修复访问网页的所有用户的代码。  为此，您需要修复服务器上的代码。  

## 后续步骤  

恭喜你！  现在，你已了解如何在调试 JavaScript 时充分利用 Microsoft Edge DevTools。  本文中学习的工具和方法可以为您节省数百个小时。  

本文仅介绍设置断点的两种方法。  DevTools 提供了许多其他方法，包括以下设置。  

*   仅在您提供的条件为 true 时触发的条件断点。  
*   捕获或不捕获的异常的断点。  
*   当请求的 URL 与提供的子字符串匹配时触发的 XHR 断点。  
    
有关何时以及如何使用每种类型，请导航到"使用断点暂停[代码"。][DevtoolsJavscriptBreakpoints]  

本文中未介绍几个代码单步执行控件。  有关详细信息，请导航到["逐行代码"。][DevtoolsJavascriptReferenceStepThroughCode]  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: ../media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageIntoIcon]: ../media/step-into-icon.msft.png  
[ImageOverIcon]: ../media/step-over-icon.msft.png  
[ImageResumeIcon]: ../media/resume-script-run-icon.msft.png  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools |Microsoft Docs"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "分步执行代码 - JavaScript 调试|Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "打开演示|小故障"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
