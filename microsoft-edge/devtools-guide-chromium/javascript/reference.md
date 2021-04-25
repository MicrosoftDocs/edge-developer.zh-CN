---
description: 在此 Microsoft Edge DevTools 调试功能的全面参考中发现新的调试工作流。
title: 使用调试程序功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6fb90a70e0aac9f556fa9f5f02afee1fd5b4962e
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519602"
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

# <a name="use-the-debugger-features"></a>使用调试程序功能

本文介绍了如何使用 Microsoft Edge DevTools 中的调试器，包括如何设置代码行断点。  若要设置其他类型的断点，请参阅使用断点 [暂停代码][DevToolsJavascriptBreakpoints]。  

若要了解调试的基础知识，请导航到 [Microsoft Edge DevTools][DevToolsJavascriptGetStarted]中的调试 JavaScript 入门，这是一个使用基于表单的现有网页的教程。  本教程具有屏幕捕获，因此你可以浏览它。  您可以使用演示网页轻松试用调试器功能。

## <a name="view-and-edit-javascript-code"></a>查看和编辑 JavaScript 代码

修复 Bug 时，经常希望尝试对 JavaScript 代码进行一些更改。  无需在外部编辑器或 IDE 中进行更改，将文件重新上载到服务器，然后刷新页面;相反，若要测试更改，可以直接在 DevTools 中编辑 JavaScript 代码并立即查看结果。  

若要查看和编辑 JavaScript 文件，请运行：  

1.  导航到 **"源"** 工具。  
1.  在 **导航器窗格中** ，选择你的文件，以在编辑器窗格中 **打开** 它。
1.  在" **编辑器"** 窗格中，编辑文件。  
1.  选择 `Ctrl`+`S` \(Windows、Linux\) 或 `Command`+`S` \(macOS\) 进行保存。  然后，DevTools 将 JavaScript 文件加载至 Microsoft Edge 的 JavaScript 引擎。  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="编辑器窗格" lightbox="../media/javascript-sources-html-minified.msft.png":::
       “**编辑器**”窗格  
    :::image-end:::  
     
## <a name="reformat-a-minified-javascript-file-with-pretty-print"></a>使用非常打印重新设置缩小的 JavaScript 文件

若要使缩小的文件可读，请选择"编辑器"窗格底部的****"格式 ![ \ (Format ](../media/format-icon.msft.png) **\) "** 按钮。

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="格式按钮" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   “**格式**”按钮  
:::image-end:::  

## <a name="set-a-breakpoint-to-pause-code"></a>设置断点以暂停代码

若要在运行时期间暂停代码，请设置一个断点。  最基本的和已知的断点类型是代码行断点。

知道需要调查的确切代码区域时，使用代码行断点。  DevTools 始终在指定的代码行暂停，然后再运行它。

设置代码行断点：  

1.  导航到 **"源"** 工具。  
1.  打开包含代码行的文件。  
1.  选择代码行的行号左侧的区域。  或者，右键单击行号，然后选择"**添加断点"。**  然后，行号旁边会出现一个红色圆圈，指示断点。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       代码行断点  
    :::image-end:::  

代码行断点设置效率可能较低，尤其是在您不知道具体查找位置或代码库较大时。  若要在调试时节省时间，请了解如何以及何时使用其他类型的断点。  有关详细信息，请导航到["使用断点暂停代码"。][DevToolsJavascriptBreakpoints]

## <a name="step-through-code"></a>单步执行代码  

在断点暂停代码后，逐步执行代码，一次一行，一直调查控制流和属性值。  

### <a name="step-over-line-of-code"></a>逐步执行代码  

当暂停包含与正在调试的问题不相关的函数的代码行时，选择"单步执行**\ (** 单步 ![ 执行 \) "按钮以在不单步执行的情况下运行函数。 ](../media/step-over-icon.msft.png)  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="选择逐步执行" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
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

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="选择逐行执行" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
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

当暂停在与正在调试的问题不相关的函数内时，选择"单步执行 **\ (** 单步执行 \) "按钮以运行函数的其余 ![ ](../media/step-out-icon.msft.png) 代码。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="选择执行剩余" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
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

你可以选择逐行执行，但这很繁琐。  您可以选择在感兴趣的行上设置代码行断点，然后选择 Resume **脚本** 执行 \ (Resume 脚本执行 ![ \) 按钮，但有一种更快的方法 ](../media/resume-script-run-icon.msft.png) 。  

将鼠标悬停在你感兴趣的代码行上，打开上下文菜单 \(右键单击\) ，然后选择“**继续至此处**”。  DevTools 会运行所有代码，一直运行到该处，然后暂停到该行。  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="选择继续至此处" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   选择“**继续至此处**”  
:::image-end:::  

### <a name="restart-the-top-function-of-the-call-stack"></a>重新启动调用的顶部函数  

若要暂停调用堆栈中顶部函数的第一行，同时在代码行上暂停，请将鼠标悬停在"调用堆栈"窗格中的任意位置****，打开上下文菜单 \ (右键单击\) ，然后选择"**重新启动**帧"。  top 函数是最后一个运行的函数。  

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

你已在 `A` 上暂停。  选择重启**帧后**，应暂停在 上 `B` ，无需设置断点或选择 **"恢复脚本执行"。**  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="选择重启帧" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   选择 **重启帧**  
:::image-end:::  

### <a name="resume-script-runtime"></a>恢复脚本运行时  

若要在脚本暂停后继续运行时，请选择 Resume **script execution** \ (Resume script ![ execution ](../media/resume-script-run-icon.msft.png) \) button。  DevTools 将一直运行脚本，直到下一个断点（如果有）。  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="选择恢复脚本执行" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   选择“**恢复脚本执行**”  
:::image-end:::  

#### <a name="force-script-runtime"></a>强制脚本运行时  

若要忽略所有断点并强制脚本继续运行，请选择并按住 Resume**脚本**执行 \ (Resume 脚本执行 \) 按钮，然后选择"强制脚本执行 ![ ](../media/resume-script-run-icon.msft.png) \ (强制脚本执行**** ![ ](../media/force-script-run-icon.msft.png) \) "按钮。  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="选择强制脚本执行" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   选择“**强制脚本执行**”  
:::image-end:::  

### <a name="change-thread-context"></a>更改线程上下文  

使用 Web 工作进程或服务工作进程时，选择“**线程**”窗格中列出的上下文以切换到该上下文。  蓝色箭头图标表示当前选定的上下文。  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="线程窗格" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   “**线程**”窗格  
:::image-end:::  

例如，你在主脚本和服务工作进程脚本的断点上暂停。  您希望查看服务工作器上下文的本地和全局属性，但 **Sources** 工具显示主脚本上下文。  若要切换到服务工作器上下文，在" **线程** "窗格中，选择服务工作器条目。  

## <a name="view-and-edit-properties-and-variables"></a>查看和编辑属性和变量

在代码行上暂停时，使用“**范围**”窗格查看和编辑本地、关闭和全局范围中的属性和变量的值。  

*   双击某个属性值以更改该值。  
*   不可枚举的属性显示为灰色。  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="范围窗格" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   “**范围**”窗格  
:::image-end:::  

## <a name="watch-the-values-of-javascript-expressions"></a>观看 JavaScript 表达式的值  

使用“**监视**”窗格观察自定义表达式的值。  你可以观看任何有效的 JavaScript 表达式。  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="监视窗格" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   “**监视**”窗格  
:::image-end:::  

*   若要创建新的监视表达式，请选择"添加 **监视** 表达式 \ (![ 添加监视表达式 ](../media/add-expression-icon.msft.png) \) 按钮。  
*   若要刷新所有现有表达式的值，请选择"刷新 **\ (** ![ 刷新 ](../media/refresh-icon.msft.png) \) "按钮。  逐步执行代码时，值将自动刷新。  
*   若要删除监视表达式，请右键单击该表达式，然后选择"删除 **监视** 表达式 \ (![ 删除监视表达式 ](../media/delete-expression-icon.msft.png) \) "。  

## <a name="view-the-call-stack"></a>查看调用堆栈  

在代码行上暂停时，使用“**调用堆叠**”窗格查看让你到达此点的调用堆叠。  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

选择一个项以跳转到调用该函数的代码行。  蓝色箭头图标表示 DevTools 当前突出显示的函数。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="调用堆叠窗格" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   “**调用堆叠**”窗格  
:::image-end:::  

> [!NOTE]
> 当未在代码行上暂停时，“**调用堆叠**”窗格为空。  

### <a name="copy-stack-trace"></a>复制堆叠跟踪  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

若要将当前调用堆栈复制到剪贴板，请将鼠标悬停在"调用**** 堆栈"窗格中的任意位置，打开上下文菜单 \ (右键单击\) ，然后选择"复制堆栈跟踪 **"。**  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="选择复制堆叠跟踪" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
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

例如，在下面的代码段中，行使用 `A` `lib` ，这是第三方库。  如果您确信正在调试的问题与该第三方库不相关，那么将脚本标记为库代码 **是有意义的**。  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

### <a name="mark-a-script-as-library-code-from-the-editor-pane"></a>在编辑器窗格中将脚本标记为库代码  

若要从编辑器窗格中**将脚本标记为****库代码：**  

1.  打开文件。  
1.  将鼠标悬停在任意位置并打开上下文菜单 \(右键单击\)。  
1.  选择 **"添加脚本"忽略之前** (标记为**库代码的列表) 。**  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="在编辑器窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       从“**编辑器**”窗格中将脚本标记为**库代码**  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-the-call-stack-pane"></a>从调用堆叠窗格中将脚本标记为库代码  

若要从"调用堆栈 **"窗格中将** 脚本 **标记为库** 代码：  

1.  将鼠标悬停在脚本的函数上，然后打开上下文菜单 \(右键单击\)。  
1.  选择 **"添加脚本"忽略之前** (标记为**库代码的列表) 。**  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="从调用堆叠窗格中将脚本标记为库代码" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       从**调用堆叠**窗格中将脚本标记为**库代码**  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-settings"></a>在设置中将脚本标记为库代码  

若要从"设置"中标记单个脚本或脚本**模式：**  

1.  打开“[设置][DevToolsCustomize]”。  
1.  导航到“**库代码**”设置。  
1.  选择“**添加模式**”。  
1.  输入脚本名称或脚本名称的正则表达式模式，以标记为**库代码**。  
1.  选择“**添加**”。  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="在设置中将脚本标记为库代码" lightbox="../media/javascript-framework-library-code.msft.png":::
       在“**设置**”中将脚本标记为**库代码**  
    :::image-end:::  
    
## <a name="run-snippets-of-debug-code-from-any-page"></a>从任何页面运行调试代码的代码段  

如果你的控制台一次又一次地运行相同的调试代码，请考虑使用代码段。  代码段是你在 DevTools 中创作、存储和运行的运行时脚本。  

请参阅 [在任何网页上运行 JavaScript 代码段][DevToolsJavascriptSnippets]。  

## <a name="see-also"></a>另请参阅  

*   [Microsoft Edge DevTools][DevToolsJavascriptGetStarted] 中的调试 JavaScript 入门 - 使用现有代码和屏幕捕获的简单简短教程。
*   [源工具概述][DevToolsSourcesIndex] - **源工具** 包括 JavaScript 调试程序和编辑程序。
*   [使用 Microsoft Edge DevTools 禁用 JavaScript。][DevToolsJavascriptDisable]

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "如何在 Microsoft Edge DevTools 中用断点暂停代码 | Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "使用 Microsoft Edge DevTools 工具禁用 JavaScript | Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "在 Microsoft Edge 开发人员工具中调试 JavaScript 入门 | Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "使用 Microsoft Edge DevTools 工具在任意页面上运行 JavaScript | Microsoft Docs"  
[DevToolsSourcesIndex]: ../sources/index.md "源工具概述 | Microsoft Docs"  
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
