---
description: 在此 Microsoft Edge DevTools 调试功能的全面参考中发现新的调试工作流。
title: JavaScript 调试引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2944e054a08a901d2e1752fa7c4e48ae110f5787
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439456"
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

# <a name="javascript-debugging-reference"></a>JavaScript 调试引用  

通过以下 Microsoft Edge DevTools 调试功能的全面参考发现新的调试工作流。  

若要了解调试的基础知识，请导航到 [Microsoft Edge DevTools][DevToolsJavascriptGetStarted]中的调试 JavaScript 入门。  

## <a name="pause-code-with-breakpoints"></a>使用断点暂停代码  

设置断点，以便可以在运行时中间暂停代码。  

若要了解如何设置断点，请导航到“[使用断点暂停代码][DevToolsJavascriptBreakpoints]”。  

## <a name="step-through-code"></a>单步执行代码  

暂停代码后，一次分步执行一行，一直调查控制流和属性值。  

### <a name="step-over-line-of-code"></a>逐步执行代码  

当暂停包含与正在调试的问题不相关的函数的代码行时，选择“**逐步执行** \(![逐步执行](../media/step-over-icon.msft.png)\)”按钮以运行该函数，而无需单步执行。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="选择“逐步执行”" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   选择“**逐步执行**”  
:::image-end:::  

例如，假设您正在调试以下代码段。  

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

你已在 `A` 上暂停。  选择“**逐步执行**”后，DevTools 将运行要逐步执行的函数中的所有代码，即 `B` 和 `C`。  DevTools 随后在 `D` 上暂停。  

### <a name="step-into-line-of-code"></a>逐行执行代码  

暂停包含与正在调试的问题相关的函数调用的代码行时，选择“**逐行执行** \(![逐行执行](../media/step-into-icon.msft.png)\) "按钮以进一步调查该函数。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="选择“逐行执行”" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   选择“**逐行执行**”  
:::image-end:::  

例如，假设您正在调试以下代码段。  

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

你已在 `A` 上暂停。  选择“**逐行执行**”后，DevTools 将运行此代码行，然后在 `B` 上暂停。  

### <a name="step-out-of-line-of-code"></a>执行剩余代码  

当暂停在与正在调试的问题不相关的函数内时，选择“**执行剩余** \(![执行剩余](../media/step-out-icon.msft.png)\)”按钮以运行函数的剩余代码。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="选择“执行剩余”" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   选择 **“执行剩余”**  
:::image-end:::  

例如，假设您正在调试以下代码段。  

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

你已在 `A` 上暂停。  选择“**执行剩余**”后，DevTools 将运行 `getName()` 中代码的剩余部分，在此示例中为 `B`，然后在 `C` 上暂停。  

### <a name="run-all-code-up-to-a-specific-line"></a>运行所有代码到特定行  

调试长函数时，可能有许多代码与正在调试的问题不相关。  

你可以选择逐行执行，但这很繁琐。  您可以选择在感兴趣的行上设置代码行断点，然后选择“**Resume Script Execution** \(![Resume Script Execution](../media/resume-script-run-icon.msft.png)\) "按钮，但有一个更快的方法。  

将鼠标悬停在你感兴趣的代码行上，打开上下文菜单 \(右键单击\) ，然后选择“**继续至此处**”。  DevTools 会运行所有代码，一直运行到该处，然后暂停到该行。  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="选择“继续至此处”" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   选择“**继续至此处**”  
:::image-end:::  

### <a name="restart-the-top-function-of-the-call-stack"></a>重新启动调用的顶部函数  

若要暂停调用堆叠中顶部函数的第一行，当暂停在代码行上时，请将鼠标悬停在“**调用堆叠**”窗格中的任意位置，打开上下文菜单 \(右键单击\)，然后选择“**重新启动框架**”。  top 函数是最后一个运行的函数。  

下面的代码段是一个分步执行示例。  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

你已在 `A` 上暂停。  选择“**重启框架**”后，应暂停在 `B` 上，无需设置断点或选择“**恢复脚本执行**”。  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="选择重启框架" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   选择“**重启框架**”  
:::image-end:::  

### <a name="resume-script-runtime"></a>恢复脚本运行时  

若要在脚本暂停后继续运行时，请选择“**恢复脚本执行** \(![恢复脚本执行](../media/resume-script-run-icon.msft.png)\)”按钮。  DevTools 将一直运行脚本，直到下一个断点（如果有）。  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="选择“恢复脚本执行”" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   选择“**恢复脚本执行**”  
:::image-end:::  

#### <a name="force-script-runtime"></a>强制脚本运行时  

若要忽略所有断点并强制脚本继续运行，请选择并按住“**恢复脚本执行** \(![恢复脚本执行](../media/resume-script-run-icon.msft.png)\)”按钮，然后选择“**强制脚本执行** \(![强制脚本执行](../media/force-script-run-icon.msft.png)\)”按钮。  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="选择“强制脚本执行”" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   选择“**强制脚本执行**”  
:::image-end:::  

### <a name="change-thread-context"></a>更改线程上下文  

使用 Web 工作进程或服务工作进程时，选择“**线程**”窗格中列出的上下文以切换到该上下文。  蓝色箭头图标表示当前选定的上下文。  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="“线程”窗格" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   “**线程**”窗格  
:::image-end:::  

例如，你在主脚本和服务工作进程脚本的断点上暂停。  你希望查看服务工作进程上下文的本地和全局属性，但“**源**”面板显示的是主脚本的上下文。  通过选择“**线程**”窗格中的服务工作进程项，这样应该就可以切换到目标上下文。  

## <a name="view-and-edit-local-closure-and-global-properties"></a>查看和编辑本地、关闭和全局属性  

在代码行上暂停时，使用“**范围**”窗格查看和编辑本地、关闭和全局范围中的属性和变量的值。  

*   双击某个属性值以更改该值。  
*   不可枚举的属性显示为灰色。  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="“范围”窗格" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   “**范围**”窗格  
:::image-end:::  

## <a name="view-the-current-call-stack"></a>查看当前调用堆叠  

在代码行上暂停时，使用“**调用堆叠**”窗格查看让你到达此点的调用堆叠。  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

选择一个项以跳转到调用该函数的代码行。  蓝色箭头图标表示 DevTools 当前突出显示的函数。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="“调用堆叠”窗格" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   “**调用堆叠**”窗格  
:::image-end:::  

> [!NOTE]
> 当未在代码行上暂停时，“**调用堆叠**”窗格为空。  

### <a name="copy-stack-trace"></a>复制堆叠跟踪  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

若要将当前调用堆叠复制到剪贴板，请将鼠标悬停在“**调用堆叠**”窗格中的任意位置，打开上下文菜单 \(右键单击\)，然后选择“**复制堆叠跟踪**”。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="选择"复制堆叠跟踪"" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   选择“**复制堆叠跟踪**”  
:::image-end:::  

以下代码段是一个输出示例。  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onChoose (get-started.js:15)
```  

## <a name="ignore-a-script-or-pattern-of-scripts"></a>忽略脚本或脚本模式  

若你想要在调试时忽略该脚本，请将脚本标记为库代码。  被标记为库代码时，脚本会在“**调用堆叠**”窗格中被遮盖，且你在单步执行代码时绝不会单步执行脚本的函数。  

下面的代码段是一个分步执行示例。  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` 是受信任的第三方库。  如果你确信正在调试的问题与第三方库不相关，那么将脚本标记为“**库代码**”是有意义的。  

### <a name="mark-a-script-as-library-code-from-the-editor-pane"></a>在“编辑器”窗格中将脚本标记为库代码  

完成以下操作来在“**编辑器**”窗格中将脚本标记为**库代码**。  

1.  打开文件。  
1.  将鼠标悬停在任意位置并打开上下文菜单 \(右键单击\)。  
1.  选择“**标记为库代码**”。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="在“编辑器”窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       从“**编辑器**”窗格中将脚本标记为**库代码**  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-the-call-stack-pane"></a>从“调用堆叠”窗格中将脚本标记为库代码  

完成以下操作以从“**调用堆叠**”窗格中将脚本标记为**库代码**。  

1.  将鼠标悬停在脚本的函数上，然后打开上下文菜单 \(右键单击\)。  
1.  选择“**标记为库代码**”。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="从“调用堆叠”窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       从**调用堆叠**窗格中将脚本标记为**库代码**  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-settings"></a>在“设置”中将脚本标记为库代码  

完成以下操作以从“**设置**”中标记单个脚本或脚本模式。  

1.  打开“[设置][DevToolsCustomize]”。  
1.  导航到“**库代码**”设置。  
1.  选择“**添加模式**”。  
1.  输入脚本名称或脚本名称的正则表达式模式，以标记为**库代码**。  
1.  选择“**添加**”。  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="在“设置”中将脚本标记为库代码" lightbox="../media/javascript-framework-library-code.msft.png":::
       在“**设置**”中将脚本标记为**库代码**  
    :::image-end:::  
    
## <a name="run-snippets-of-debug-code-from-any-page"></a>从任何页面运行调试代码的代码段  

如果你的控制台一次又一次地运行相同的调试代码，请考虑使用代码段。  代码段是你在 DevTools 中创作、存储和运行的运行时脚本。  

若要了解更多信息，请导航到“[从任何页面运行代码段][DevToolsJavascriptSnippets]”。  

## <a name="watch-the-values-of-custom-javascript-expressions"></a>观看自定义 JavaScript 表达式的值  

使用“**监视**”窗格观察自定义表达式的值。  你可以观看任何有效的 JavaScript 表达式。  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="“监视”窗格" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   “**监视**”窗格  
:::image-end:::  

*   选择“**添加表达式** \(![添加表达式](../media/add-expression-icon.msft.png)\)”按钮以创建新的监视表达式。  
*   选择“**刷新** \(![刷新](../media/refresh-icon.msft.png)\)”按钮以刷新所有现有表达式的值。  逐步执行代码时，值将自动刷新。  
*   将鼠标悬停在表达式上并选择“**删除表达式** \(![删除表达式](../media/delete-expression-icon.msft.png)\)”按钮将其删除。  

## <a name="make-a-minified-file-readable"></a>使缩小文件可读  

选择“**格式** \(![格式](../media/format-icon.msft.png)\)” 按钮来使缩小文件可读。  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="“格式”按钮" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   “**格式**”按钮  
:::image-end:::  

## <a name="edit-a-script"></a>编辑脚本  

修复 Bug 时，通常需要测试对 JavaScript 代码的一些更改。  无需在外部编辑器或 IDE 中进行更改并刷新页面。  你可以在 DevTools 中编辑脚本。  

完成以下操作以编辑脚本。  

1.  在“**源**”面板的“**编辑器**”窗格中打开文件。  
1.  在“**编辑器**”窗格中进行更改。  
1.  选择 `Ctrl`+`S` \(Windows、Linux\) 或 `Command`+`S` \(macOS\) 进行保存。  DevTools 将整个 JS 文件修补到 Microsoft Edge 的 JavaScript 引擎中。  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="“编辑器”窗格" lightbox="../media/javascript-sources-html-minified.msft.png":::
       “**编辑器**”窗格  
    :::image-end:::  
     
## <a name="disable-javascript"></a>禁用 JavaScript  

导航到[使用 Microsoft Edge DevTools 禁用 JavaScript][DevToolsJavascriptDisable]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools 中用断点暂停代码 | Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "使用 Microsoft Edge DevTools 工具禁用 JavaScript | Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "在 Microsoft Edge 开发人员工具中调试 JavaScript 入门 | Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "使用 Microsoft Edge DevTools 工具在任意页面上运行 JavaScript | Microsoft Docs"  
[DevToolsCustomize]: ../customize/index.md "自定义 Microsoft Edge DevTools | Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
