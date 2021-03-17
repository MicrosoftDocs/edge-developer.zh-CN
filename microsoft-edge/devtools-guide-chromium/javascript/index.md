---
description: 了解如何使用 Microsoft Edge DevTools 查找和修复 JavaScript Bug。
title: 在 Microsoft Edge DevTools 中调试 JavaScript 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: bbfb766bcc03e4c4fe0f975f1ecfccbef08084be
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
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

本文将指导你调试 DevTools 中任何 JavaScript 问题的基本工作流。  

## <a name="step-1-reproduce-the-bug"></a>步骤 1：重现 Bug  

查找一系列持续重现 Bug 的操作始终是调试的第一步。  

1.  选择 **"打开演示"。**  按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后打开新浏览器选项卡中的演示。  
    
    [打开演示][OpenDebugJSDemo]  
    
1.  在 `5` " **数字 1"文本框** 中输入。  
1.  在 `1` "数字 **2"文本框** 中输入。  
1.  选择 **"添加数字 1"和"数字 2"。**  按钮下方的标签显示 `5 + 1 = 51` 。  结果应为 `6` 。  接下来，修复 Bug 的添加错误。  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 的结果为 51，但应为 6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` 结果为 `51` ，但应为 `6`  
    :::image-end:::  
    
## <a name="step-2-get-familiar-with-the-sources-tool-ui"></a>步骤 2：熟悉源工具 UI  

DevTools 为不同的任务提供了许多不同的工具。  不同的任务包括更改 CSS、分析页面加载性能和监视网络请求。  " **源** "工具是调试 JavaScript 的地方。  

1.  若要在**** DevTools 中打开控制台工具，请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="控制台工具" lightbox="../media/javascript-console-empty.msft.png":::
       控制台**工具**  
    :::image-end:::  
    
1.  选择" **源"** 工具。  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="源工具" lightbox="../media/javascript-sources-sections.msft.png":::
       源**工具**  
    :::image-end:::  
    
源 **工具** UI 有三个部分。  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="源工具 UI 的 3 个部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   源工具 UI 的 3**个部分**  
:::image-end:::  

1.  文件 **导航器** 面板 \ (上图\第 1 部分) 。  此处列出了网页请求的所有文件。  
1.  上 **图\ (** 第 2 节中的代码编辑器面板) 。  在"文件导航器"窗格中 **选择** 文件后，该文件的内容将显示在此处。  
1.  上 **图中的 JavaScript** 调试 (第 3 部分) 。  用于检查网页的 JavaScript 的各种工具。  如果 DevTools 窗口很宽，则此窗格显示在"代码编辑器" **窗格的右侧** 。  
    
## <a name="step-3-pause-the-code-with-a-breakpoint"></a>步骤 3：使用断点暂停代码  

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

`console.log()`方法可能会完成作业，但**断**点可以更快地完成。  断点允许你在运行时中间暂停代码，并检查此时的所有值。  断点与方法相比具有以下 `console.log()` 优点。  

*   使用 ，需要手动打开源代码、查找相关代码、插入语句，然后刷新网页以显示控制台 `console.log()` `console.log()` **中的消息**。  对于断点，您可能会暂停相关代码，甚至不知道代码的构建方式。  
*   在 `console.log()` 语句中，需要明确指定要检查的每个值。  对于断点，DevTools 显示当时所有变量的值。  有时，影响代码的变量被隐藏和混淆。  
    
简而言之，断点可以帮助你更快地查找和修复 `console.log()` Bug。  

如果你后退一步并思考应用的工作原理，你可能会有根据地猜出错误的总和 \ (\) 是在与"添加数字 `5 + 1 = 51` 1"和"数字 `click` **2"** 按钮关联的事件侦听器中计算的。  因此，你可能想要在侦听器运行时暂停 `click` 代码。  **事件侦听器断点** 使你可以完全实现此要求：  

1.  在 **"JavaScript 调试"** 窗格中，选择 **"事件侦听器断点"** 以展开部分。  DevTools 显示可展开事件类别的列表，如 **动画** 和 **剪贴板**。  
1.  在鼠标事件 **类别** 旁边， **选择展开** \ (![ 展开图标 ](../media/expand-icon.msft.png) \) 。  DevTools 显示鼠标事件的列表 **，如单击** 和 **鼠标按下**。  每个事件旁边都有一个复选框。  
1.  选择单击 旁边的 **复选框**。  DevTools 现在设置为在任何事件侦听器运行时 `click` 自动暂停。  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="选择单击旁边的复选框" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       选择单击旁边的 **复选框**  
    :::image-end:::  
    
1.  返回到演示，再次选择"**添加数字 1"和"数字 2"。**  DevTools 暂停演示，并突出显示"源"工具中的一 **行** 代码。  DevTools 应在 的第 16 行暂停 `get-started.js` 。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    如果您在其他代码行上暂停，请选择"恢复脚本 **执行" (** Resume Script ![ Execution ](../media/resume-script-run-icon.msft.png) \) 直到您暂停到正确的行。  
    
    > [!NOTE]
    > 如果您在另一行上暂停，则有一个浏览器扩展，该扩展在所访问的每一个 `click` 网页上注册事件侦听器。  在扩展的 `click` 侦听器中暂停。  如果使用 InPrivate 模式在**** 专用 中浏览，这将禁用所有扩展，您可能会看到每次在所需的代码行上暂停。  

<!--todo: add inprivate section when available -->  

**事件侦听器断点** 只是 DevTools 中提供的许多类型的断点之一。  记住所有不同类型的以帮助你尽快调试不同的方案。  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <a name="step-4-step-through-the-code"></a>步骤 4：逐步执行代码  

Bug 的一个常见原因是脚本按错误的顺序运行。  单步执行代码允许你演练代码的运行时。  一次执行一行，以帮助你准确了解代码以与预期不同的顺序运行。  立即尝试：  

1.  Choose **Step over next function call** \ (Step over next function call ![ ](../media/step-over-icon.msft.png) \) .  DevTools 无需单步执行即可运行以下代码。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > DevTools 跳过几行代码。  这是因为计算 `inputsAreEmpty()` 结果为 false，因此语句的代码 `if` 块不会运行。  
    
1.  在**** DevTools 的"源"工具上，选择"单步执行下一个函数调用**\ (** 单步执行下一个函数调用 ![ ](../media/step-into-icon.msft.png) \) "以逐步完成函数的运行时，一次一行 `updateLabel()` 。  
    
一次查看一行是单步执行代码的基本概念。  如果查看 中的代码 `get-started.js` ，则 bug 可能位于 函数中的 `updateLabel()` 某一位置。  与其单步执行每行代码，不如使用另一种类型的断点来暂停代码，使代码更接近 bug 的可能位置。  

## <a name="step-5-set-a-line-of-code-breakpoint"></a>步骤 5：设置代码行断点  

代码行断点是最常见的断点类型。  当到达要暂停的特定代码行时，请使用代码行断点。  

1.  查看 中的最后一行代码 `updateLabel()` ：  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  在左侧，此特定代码行的编号显示为 **34**。  选择第 **34 行**。  DevTools 在 **34**左侧显示一个红色图标。  红色图标表示代码行断点位于此行上。  DevTools 始终在运行此代码行之前暂停。  
1.  Choose **Resume script execution** \ (Resume script execution ![ ](../media/resume-script-run-icon.msft.png) \) .  脚本将继续运行，直到到达第 33 行。  在行 31、32 和 33 上，DevTools 在每一行上打印分号右边的 、 和 `addend1` `addend2` `sum` 值。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools 暂停第 34 行的代码行断点" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       DevTools 暂停第 34 行的代码行断点  
    :::image-end:::  
    
## <a name="step-6-check-variable-values"></a>步骤 6：检查变量值  

、 `addend1` 和 `addend2` `sum` 的值看起来可疑。  这些值用引号括起来。  引号表示值是字符串，这是解释 Bug 原因的一个很好的假设。  收集有关情况详细信息。  DevTools 提供了许多用于检查变量值的工具。  

### <a name="method-1-the-scope-panel"></a>方法 1：范围面板  

如果暂停一行代码，"范围"面板**** 将显示当前定义的本地和全局变量以及每个变量的值。  它还会显示关闭变量（如果适用）。  双击变量值进行编辑。  如果未在代码行上暂停，则 **"范围"** 面板为空。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text=""范围"窗格" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   " **范围"** 窗格  
:::image-end:::  

### <a name="method-2-watch-expressions"></a>方法 2：监视表达式  

监视 **表达式** 面板允许你随着时间的推移监视变量的值。  正如该名称所示， **监视表达式** 不限于变量。  你可以将任何有效的 JavaScript 表达式存储在 **监视表达式 中**。  立即尝试。  

1.  选择" **监视"** 面板。  
1.  Choose **Add Expression** \ (Add Expression ![ ](../media/add-expression-icon.msft.png) \) .  
1.  键入 `typeof sum`。  
1.  选择 `Enter`。  DevTools 显示 `typeof sum: "string"` 。  冒号右边的值是监视表达式的结果。  
    
> [!NOTE]
> 在" **监视表达式** "窗格 \ (右) \下图中，将显示 `typeof sum` 监视表达式。  如果 DevTools 窗口很大，则" **监视表达式** "窗格位于"事件侦听器断点"窗格 **的** 右侧。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="监视表达式面板" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   监视 **表达式** 面板  
:::image-end:::  

如所怀疑的，当应为数字时，将作为字符串 `sum` 进行评估。  现在确认值类型是 Bug 的原因。  

### <a name="method-3-the-console"></a>方法 3：控制台  

控制台 **允许你** 查看 `console.log()` 消息，还可以使用它来评估任意 JavaScript 语句。  对于调试，可以使用 **控制台** 测试潜在 Bug 修复。  立即尝试。  

1.  如果 **控制台工具** 已关闭，请选择 `Escape` 将其打开。  控制台 **工具** 将在 DevTools 窗口的下面板中打开。  
1.  在控制台 **中**，键入 `parseInt(addend1) + parseInt(addend2)` 。  该工具的语句暂停在代码行上，其中 和 `addend1` `addend2` 位于范围内。  
1.  选择 `Enter`。  DevTools 评估语句并打印 `6` ，这是预期演示生成的结果。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="控制台工具，在评估 parseInt (addend1) + parseInt (addend2) " lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       评估 **后的** 控制台工具 `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <a name="step-7-apply-a-fix"></a>步骤 7：应用修补程序  

如果你找到该 Bug 的修复程序，请通过编辑代码并重新运行演示来尝试修复。  你可以直接在 DevTools UI 中编辑 JavaScript 代码并应用修复程序。  立即尝试。  

1.  Choose **Resume script execution** \ (Resume script execution ![ ](../media/resume-script-run-icon.msft.png) \) .  
1.  在代码 **编辑器中**，将 第 32 行 `var sum = addend1 + addend2` 替换为 `var sum = parseInt(addend1) + parseInt(addend2)` 。  
1.  选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。  
1.  Choose **Deactivate breakpoints** \ (![ Deactivate breakpoints ](../media/deactivate-breakpoints-button-icon.msft.png) \) .  它将更改蓝色，以指示选项处于活动状态。  设置 **Deactivate 断点** 时，DevTools 将忽略你设置的任何断点。  
1.  尝试使用不同值的演示。  演示现在计算正确。  
    
> [!CAUTION]
> 此工作流仅对浏览器中运行的代码应用修补程序。  它不会修复访问网页的所有用户的代码。  为此，需要修复服务器上的代码。  

## <a name="next-steps"></a>后续步骤  

恭喜你！  现在，你已了解如何在调试 JavaScript 时充分利用 Microsoft Edge DevTools。  本文中学习的工具和方法可以为您节省很多时间。  

本文仅教您设置断点两种方法。  DevTools 提供了许多其他方法，包括以下设置。  

*   仅在您提供的条件为 true 时触发的条件断点。  
*   捕获或不捕获的异常的断点。  
*   请求的 URL 与提供的子字符串匹配时触发的 XHR 断点。  
    
有关何时以及如何使用每种类型的信息，请导航到"使用断点[暂停代码"。][DevtoolsJavscriptBreakpoints]  

本文不介绍几个代码单步执行控件。  有关详细信息，请导航到"[逐行代码"。][DevtoolsJavascriptReferenceStepThroughCode]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

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
