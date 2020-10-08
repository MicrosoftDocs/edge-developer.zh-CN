---
description: 了解 Microsoft Edge DevTools 调试功能的此全面参考中的新调试工作流。
title: JavaScript 调试引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f11dfb52e97dcec20d1e6c4f3adeee7010857a33
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993420"
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

# JavaScript febugging 参考  

通过以下完整的 Microsoft Edge DevTools 调试功能参考发现新的调试工作流。  

有关调试的基础知识，请参阅 [开始在 Microsoft Edge DevTools 中调试 JavaScript][DevToolsJavascriptGetStarted] 。  

## 暂停带断点的代码  

设置断点，以便你可以在运行时的中间暂停代码。  

请参阅 [暂停带断点的代码][DevToolsJavascriptBreakpoints] ，了解如何设置断点。  

## 逐句通过代码  

代码暂停后，逐个遍历它，一次一行，以调查控制流和属性值的方式。  

### 跳过代码行  

当在包含与你调试的问题不相关的函数的代码行上暂停时，请单击 " **步骤超过** \ (![ ][ImageStepOverIcon] \ ) " 按钮以运行该函数，而无需单步执行该函数。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   选择 "**逐步骤**"  
:::image-end:::  

例如，假设你正在调试以下代码片段。  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name); // D
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name; // C
}
```  

您已暂停 `A` 。  通过按 " **逐步骤**"，DevTools 将运行你正在执行的函数中的所有代码，即 `B` 和 `C` 。  DevTools 然后暂停 `D` 。  

### 单步执行代码行  

当暂停包含与你正在调试的问题相关的函数调用的代码行时，请单击 **步骤** " (单步执行" ![ ) " ][ImageStepIntoIcon] 按钮，以进一步调查该功能。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   选择**单步**执行  
:::image-end:::  

例如，假设你正在调试以下代码片段。  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name);
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name;
}
```  

您已暂停 `A` 。  通过按 " **单步执行**"，DevTools 将运行此行代码，然后暂停 `B` 。  

### 跳出代码行  

当在与你调试的问题不相关的函数内暂停时，请单击 " **跳出** " (" ![ 跳出" ][ImageStepOutIcon] ) 按钮以运行函数的其余代码。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   选择 "**跳出**"  
:::image-end:::  

例如，假设你正在调试以下代码片段。  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName();
    updateName(name); // C
}
function getName() {
    var name = app.first + ' ' + app.last; // A
    return name; // B
}
```  

您已暂停 `A` 。  通过按 " **跳出**"，DevTools 将运行中的其余代码 `getName()` ，这就是在 `B` 此示例中，然后暂停 `C` 。  

### 运行到特定行的所有代码  

调试长函数时，可能有许多与你正在调试的问题无关的代码。  

你可以选择单步执行所有行，但这是单调乏味的。  你可以选择在感兴趣的行上设置代码行断点，然后单击 " **恢复脚本执行** " (" ![ 恢复脚本执行" ][ImageResumeScriptExecutionIcon] \ ) 按钮，但有更快的方法。  

右键单击您感兴趣的代码行，然后选择 " **继续到此处**"。  DevTools 运行到该点的所有代码，然后在该行上暂停。  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   选择 "**继续到此处**"  
:::image-end:::  

### 重启调用堆栈的 top 函数  

在一行代码中暂停时，右键单击 " **调用堆栈** " 窗格中的任意位置，然后选择 " **重新启动帧** " 以在调用堆栈中 top 函数的第一行暂停。  Top 函数是最后运行的函数。  

下面的代码片段是用于执行分步操作的示例。  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

您已暂停 `A` 。  单击 " **重启帧**" 后，你应该暂停在 `B` ，不进行任何设置断点或按 " **恢复脚本执行**"。  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   选择 "**重启帧**"  
:::image-end:::  

### 恢复脚本运行时  

若要在暂停脚本后继续运行时，请单击 " **恢复脚本执行** " (" ![ 恢复脚本执行" ][ImageResumeScriptExecutionIcon] \ ) 按钮。  DevTools 运行脚本，直到出现下一个断点（如果有）。  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   选择 "**恢复脚本执行**"  
:::image-end:::  

#### 强制脚本运行时  

若要忽略所有断点并强制脚本恢复运行，请单击并按住 " **恢复脚本执行** " (" ![ 恢复脚本执行 \ ][ImageResumeScriptExecutionIcon] ) " 按钮，然后选择 " **强制** 脚本执行" (![ 强制脚本执行 ][ImageForceScriptExecutionIcon] \ ) "按钮。  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   选择 "**强制脚本执行**"  
:::image-end:::  

### 更改线程上下文  

处理 web 工作人员或服务工作者时，单击 " **线程** " 窗格中列出的上下文以切换到该上下文。  蓝色箭头图标表示当前选择的上下文。  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   " **线程** " 窗格  
:::image-end:::  

例如，假设你的主脚本和你的服务工作脚本中的断点暂停。  你希望查看服务工作上下文的本地属性和全局属性，但 " **源** " 面板显示的是主脚本上下文。  通过单击 " **线程** " 窗格中的 "服务工作人员" 条目，你应该能够切换到该上下文。  

## 查看和编辑本地、关闭和全局属性  

当在一行代码上暂停时，请使用 " **范围** " 窗格查看和编辑本地、关闭和全局范围中的属性和变量值。  

*   双击属性值进行更改。  
*   不可枚举的属性将呈灰色。  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   " **范围** " 窗格  
:::image-end:::  

## 查看当前调用堆栈  

当在一行代码上暂停时，请使用 " **调用堆栈** " 窗格查看向您提供此点的调用堆栈。  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

单击某个条目可跳转到调用该函数的代码行。  蓝色箭头图标表示当前突出显示的函数 DevTools。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   " **调用堆栈** " 窗格  
:::image-end:::  

> [!NOTE]
> 在代码行上未暂停时，" **调用堆栈** " 窗格为空。  

### 复制堆栈跟踪  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

右键单击 " **调用堆栈** " 窗格中的任意位置，然后选择 " **复制堆栈跟踪** " 将当前调用堆栈复制到剪贴板。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   选择 "**复制堆栈跟踪**"  
:::image-end:::  

以下代码片段是输出的示例。  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onClick (get-started.js:15)
```  

## 忽略脚本或脚本模式  

当你希望在调试时忽略该脚本时，请将脚本标记为库代码。  当标记为 "库代码" 时，脚本将在 " **调用堆栈** " 窗格中被遮住，当你单步执行你的代码时，将不会单步执行脚本的函数。  

下面的代码片段是用于执行分步操作的示例。  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` 是您信任的第三方库。  如果您确信所调试的问题与第三方库无关，则将脚本标记为 **库代码**是有意义的。  

### 将脚本标记为 "编辑器" 窗格中的库代码  

完成以下操作以将脚本标记为 "**编辑器**" 窗格中的**库代码**。  

1.  打开文件。  
1.  右键单击任意位置。  
1.  选择 " **标记为库代码**"。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       将脚本标记为 "**编辑器**" 窗格中的**库代码**  
    :::image-end:::  
    
### 将脚本标记为 "调用堆栈" 窗格中的库代码  

Compelte folliwng 操作将脚本标记为 "**调用堆栈**" 窗格中的**库代码**。  

1.  右键单击脚本中的函数。  
1.  选择 " **标记为库代码**"。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       将脚本标记为 "**调用堆栈**" 窗格中的**库代码**  
    :::image-end:::  
    
### 将脚本标记为来自设置的库代码  

完成以下操作，从 " **设置**" 中标记单个脚本或脚本模式。  

1.  打开 " [设置][DevToolsCustomize]"。  
1.  转到 " **库代码** " 选项卡。  
1.  单击 " **添加图案**"。  
1.  输入脚本名称或要标记为 **库代码**的脚本名称的正则表达式模式。  
1.  单击**添加**。  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-framework-library-code.msft.png":::
       将脚本标记为来自**设置**的**库代码**  
    :::image-end:::  
    
## 从任意页面运行调试代码片段   

如果您发现自己在控制台中同时运行相同的调试代码，请考虑代码段。  代码段是你在 DevTools 内创作、存储和运行的运行时脚本。  

请参阅 [从任意页面运行代码片段][DevToolsJavascriptSnippets] 以了解详细信息。  

## 监视自定义 JavaScript 表达式的值  

使用 " **监视** " 窗格监视自定义表达式的值。  你可能会注意到任何有效的 JavaScript 表达式。  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   " **监视** " 窗格  
:::image-end:::  

*   单击 " **添加表达式** \ (![ 添加表达式 ][ImageAddExpressionIcon] \ ) " 按钮以创建新的监视表达式。  
*   单击 " **刷新** \ (![ refresh ][ImageRefreshIcon] \ ) " 按钮以刷新所有现有表达式的值。  逐句通过代码时，值会自动刷新。  
*   将鼠标悬停在某个表达式上，然后单击 " **删除表达式** \ (![ 删除表达式 ][ImageDeleteExpressionIcon] \ ) " 按钮将其删除。  

## 使 minified 文件易于阅读  

单击 " **格式** \ (![ 格式 ][ImageFormatIcon] \ ) " 按钮，使 minified 文件易于阅读。  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   " **格式** " 按钮  
:::image-end:::  

## 编辑脚本   

修复 bug 时，你经常希望测试对 JavaScript 代码所做的一些更改。  无需在外部编辑器或 IDE 中进行更改，然后重新加载页面。  你可以在 DevTools 中编辑脚本。  

完成以下操作以编辑脚本。  

1.  在 "**源**" 面板的 "**编辑器**" 窗格中打开该文件。  
1.  在 " **编辑器** " 窗格中进行更改。  
1.  按 `Ctrl` + `S` \ (Windows \ ) 或 `Command` + `S` \ (macOS \ ) 保存。  DevTools 将整个 JS 文件修补到 Microsoft Edge 的 JavaScript 引擎中。  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="选择 &quot;逐步骤&quot;" lightbox="../media/javascript-sources-html-minified.msft.png":::
       " **编辑器** " 窗格  
    :::image-end:::  
     
## 禁用 JavaScript   

请参阅 [禁用 Microsoft Edge DevTools JavaScript][DevToolsJavascriptDisable]。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageStepOverIcon]: ../media/step-over-icon.msft.png  
[ImageStepIntoIcon]: ../media/step-into-icon.msft.png  
[ImageStepOutIcon]: ../media/step-out-icon.msft.png  
[ImageResumeScriptExecutionIcon]: ../media/resume-script-run-icon.msft.png  
[ImageForceScriptExecutionIcon]: ../media/force-script-run-icon.msft.png  
[ImageAddExpressionIcon]: ../media/add-expression-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageDeleteExpressionIcon]: ../media/delete-expression-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools 中暂停带有断点的代码 |Microsoft 文档"  
[DevToolsJavascriptDisable]: ./disable.md "通过 Microsoft Edge DevTools 禁用 JavaScript |Microsoft 文档"  
[DevToolsJavascriptGetStarted]: ./index.md "开始使用 Microsoft Edge DevTools 中的 JavaScript 调试 |Microsoft 文档"  
[DevToolsJavascriptSnippets]: ./snippets.md "在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段 |Microsoft 文档"  
[DevToolsCustomize]: ../customize/index.md "自定义 Microsoft Edge DevTools |Microsoft 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
