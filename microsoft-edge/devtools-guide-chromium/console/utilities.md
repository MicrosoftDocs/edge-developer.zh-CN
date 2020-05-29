---
title: 控制台实用工具 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 28b40f3f79928725d3d49418e01cf02247224370
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601794"
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





# 控制台实用工具 API 参考   



控制台实用工具 API 包含一组用于执行常见任务的便捷命令：选择和检查 DOM 元素，以可读格式显示数据、停止和启动探查器以及监视 DOM 事件。  

> [!WARNING]
> 以下命令仅适用于 Microsoft Edge DevTools 控制台。  如果从脚本运行，则命令不起作用。  

要查找 `console.log()` `console.error()` 和其余 `console.*` 方法？  请参阅[控制台 API 参考][DevToolsConsoleApi]。  

## 最近计算的表达式  

```console
$_
```  

返回最近计算的表达式的值。  

在[图 1](#figure-1)中，计算一个简单的表达式 \ （ `2 + 2` \）。  `$_`然后计算属性，其中包含相同的值。  

> ##### 图 1  
> `$_` 是最近计算的表达式  
> ![$ _ 是最近计算的表达式][ImageRecentExpression]  

在[图 2](#figure-2)中，计算的表达式最初包含一个名称数组。  计算 `$_.length` 以查找数组的长度，更改中存储的值 `$_` 成为最新计算的表达式 `4` 。  

> ##### 图 2  
> `$_` 评估新命令时的更改  
> ![评估新命令时 $ _ 更改][ImageChangedRecentExpression]  

## 最近选择的元素或 JavaScript 对象  

```console
$0
```  

返回最近选择的元素或 JavaScript 对象。  `$1` 返回最近选择的第二个项，依此类推。  `$0`、、 `$1` `$2` 、 `$3` 和 `$4` 命令可用作对在 "**元素**" 面板中检查过的最后五个 DOM 元素或在 "**内存**" 面板中选择的最后五个 JavaScript 堆对象的历史参考。  

```console
$1
```  

```console
$2
```  

```console
$3
```  

```console
$4
```  

在[图 3](#figure-3)中，在 `img` "**元素**" 面板中选择了一个元素。  在该**控制台**抽屉中，已 `$0` 评估并显示相同的元素。  

> ##### 图 3  
> 该 `$0`  
> ![$0][ImageElement0]  

在[图 4](#figure-4)中，图像显示在同一页面中选中的其他元素。  " `$0` 当前" 指的是新选定的元素，同时 `$1` 返回以前选择的元素。  

> ##### 图 4  
> 该 `$1`  
> ![$1][ImageElement1]  

## 查询选择器  

```console
$(selector, [startNode])
```  

返回具有指定 CSS 选择器的第一个 DOM 元素的引用。  此方法是[querySelector （）][MDNDocumentQuerySelector]方法的别名。  

在[图 5](#figure-5)中，返回对文档中第一个元素的引用 `<img>` 。  

> ##### 图 5  
> 该 `$('img')`  
> ![$ （' Img '）][ImageElementImg]  

右键单击返回的结果，然后选择 **"在元素中显示" 面板**以在 DOM 中查找它，或通过**滚动查看**以在页面上显示它。  

在[图 6](#figure-6)中，返回对当前所选元素的引用，并显示 src 属性。  

> ##### 图 6  
> 该 `$('img').src`  
> ![$ （"Img"） src][ImageElementImgSource]  

此方法还支持第二个参数 startNode，该参数指定要从中搜索元素的 "element" 或节点。  此参数的默认值为 `document` 。  

在[图 7](#figure-7)中，在 `img` `title--image` 返回和显示正确的后找到第一个元素 `src` 。  

> ##### 图 7  
> $ （"Img"、querySelector （"title-image"））。 src  
> ![$ （"Img"、querySelector （"title-image"））。 src][ImageElementImgNodeSource]  

> [!NOTE]
> 如果你使用的库（如 jQuery `$` ），此功能将被覆盖，并 `$` 与该库中的实现对应。  

## 所有查询选择器  

```console
$$(selector, [startNode])
```  

返回与指定的 CSS 选择器匹配的元素数组。  此方法等效于调用[querySelectorAll （）][MDNDocumentQuerySelectorAll]方法。  

在[图 8](#figure-8)中，使用 `$$()` 创建 `<img>` 当前文档中所有元素的数组，并显示 `src` 每个元素的属性值。  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

> ##### 图 8  
> `$$()`用于选择文档中的所有图像并显示源  
> ![使用 $ $ （）选择文档中的所有图像并显示源][ImageArrayElementImgSource]  

此方法还支持第二个参数 startNode，用于指定要从中搜索元素的元素或节点。  此参数的默认值为 `document` 。  

在[图 9](#figure-9)中，已修改版本的[图 8](#figure-8)用于 `$$()` 创建在 `<img>` 所选节点之后出现在当前文档中的所有元素的数组。  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

> ##### 图 9  
> `$$()`用于选择文档中指定元素之后出现的所有图像 `<div>` 并显示源  
> ![使用 $ $ （）选择文档中指定的 <div> 元素之后出现的所有图像并显示源][ImageArrayElementImgNodeSource]  

> [!NOTE]
> `Shift` + `Enter` 在控制台中按键以开始新行，而不运行脚本。  

## XPath  

```console
$x(path, [startNode])
```  

返回与指定 XPath 表达式匹配的 DOM 元素数组。  

在[图 10](#figure-10)中， `<p>` 返回页面上的所有元素。  

```console
$x("//p")
```  

> ##### 图 10  
> 使用 XPath 选择器  
> ![使用 XPath 选择器][ImageArrayXpath]  

在[图 11](#figure-11)中， `<p>` 将返回包含元素的所有元素 `<a>` 。  

```console
$x("//p[a]")
```  

> ##### 图 11  
> 使用更复杂的 XPath 选择器  
> ![使用更复杂的 XPath 选择器][ImageArrayXpathChild]  

与其他选择器命令相似， `$x(path)` 具有可选的第二个参数， `startNode` 用于指定要从中搜索元素的元素或节点。  

> ##### 图 12  
> 使用 XPath 选择器 `startNode`  
> ![将 XPath 选择器与 startNode 结合使用][ImageArrayXpathNode]  

## 消除  

```console
clear()
```  

清除历史记录的控制台。  

```console
clear()
```  

## copy  

```console
copy(object)
```  

该 `copy(object)` 方法将指定对象的字符串表示形式复制到剪贴板。  

```console
copy($0)
```  

## 调试  

```console
debug(method)
```  

>[!NOTE]
> [Chromium 问题 #1050237][MonorailIssue1050237]使用该函数跟踪 bug `debug()` 。  如果遇到此问题，请尝试改为[使用断点][DevtoolsJavascriptBreakpoints]。  

当你请求指定的方法时，将调用调试器并在 "**源**" 面板上的方法内中断，从而使你可以逐句通过代码并调试它。  

```console
debug("debug");
```  

> ##### 图 13  
> 在方法内中断 `debug()`  
> ![使用 debug 在方法中中断（）][ImageDebugMethod]  

用于 `undebug(method)` 停止中断方法，或使用 UI 禁用所有断点。  

有关断点的详细信息，请参阅[用断点暂停代码][DevToolsJavascriptBreakpoints]。  

## dir  

```console
dir(object)
```  

显示指定对象的所有属性的对象样式列表。  此方法是[console for dir （）][MDNConsoleDir]方法的别名。  

`document.head`在控制台中计算以显示和标记之间的 `<head>` HTML `</head>` 。  在[图 14](#figure-14)中，在控制台中使用后，将显示一个对象样式的列表 `console.dir()` 。  

```console
document.head;
dir(document.head);
```  

> ##### 图 14  
> `document.head`通过方法进行日志记录 `dir()`  
> ![记录文档 head with dir （）方法][ImageLogObject]  

有关详细信息，请参阅 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 控制台 API 中的条目。  

## dirxml  

```console
dirxml(object)
```  

打印指定对象的 XML 表示形式，如在 "**元素**" 选项卡中所示。 此方法等效于[dirxml （）][MDNConsoleDirxml]方法。  

## 查看  

```console
inspect(object/method)
```  

打开并选择相应面板中的指定元素或对象： "元素" 面板中的 "**元素**" 面板或 JavaScript 堆对象的 "**内存**" 面板。  

在[图 15](#figure-15)中，在 " `document.body` **元素**" 面板中打开。  

```console
inspect(document.body);
```  

> ##### 图 15  
> 检查元素 `inspect()`  
> ![使用 "检查" （）检查元素][ImageInspectElement]  

传递要检查的方法时，该方法将在 "**源**" 面板中打开文档以供您检查。  

## getEventListeners  

```console
getEventListeners(object)
```  

返回在指定对象上注册的事件侦听器。  返回值是一个对象，其中包含每个已注册事件类型的数组 \ （如 `click` 或 `keydown` \）。  每个数组的成员都是描述为每种类型注册的侦听器的对象。  在[图 16](#figure-16)中，列出了在文档对象上注册的所有事件侦听器。  

```console
getEventListeners(document);
```  

> ##### 图 16  
> 使用的输出 `getEventListeners(document)`  
> ![使用 getEventListeners （文档）的输出][ImageGetListeners]  

如果在指定对象上注册了多个侦听器，则该数组包含每个侦听器的成员。  在[图 16](#figure-16)中，事件的文档元素上注册了两个事件侦听器 `click` 。  

> ##### 图 17  
> 多个侦听器  
> ![多个侦听器][ImageMultipleListeners]  

你可以进一步展开以下每个对象以浏览属性。  

> ##### 图18  
> 侦听器对象的展开视图  
> ![侦听器对象的展开视图][ImageListenersExpanded]  

## 键  

```console
keys(object)
```  

返回一个数组，其中包含属于指定对象的属性的名称。  若要获取相同属性的关联值，请使用 `values()` 。  

例如，假设你的应用程序定义了以下对象。  

```console
var player1 = { "name":  "Ted", "level": 42 }
```  

在[图 19](#figure-19)中，结果假定 `player1` 在键入之前 `keys(player1)` 和在控制台中定义了全局命名空间 \ （对于简单性 \） `values(player1)` 。  

```console
keys(player1)
```  

```console
values(player1)
```  

> ##### 图19  
> `keys()`和 `values()` 命令  
> ![键（）和值（）命令][ImageConsoleKeysValues]  

## 监视器  

```console
monitor(method)
```  

向控制台记录一条消息，指示方法名称以及调用时传递给该方法的参数。  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

> ##### 图20  
> 该 `monitor()` 方法  
> ![Monitor （）方法][ImageConsoleMonitorSum]  

用于 `unmonitor(method)` 停止监视。  

## monitorEvents  

```console
monitorEvents(object[, events])
```  

当指定的对象上发生其中一个指定的事件时，事件对象将被记录到控制台。  你可以指定要监视的单个事件、事件数组或映射到预定义事件集合的常规事件类型之一。  请参阅[图 21](#figure-21)。  

以下监视窗口对象上的所有大小调整事件。  

```console
monitorEvents(window, "resize");
```  

> ##### 图21  
> 监视窗口调整大小事件  
> ![监视窗口调整大小事件][ImageMonitorResize]  

以下定义一个数组，用于监视 `resize` `scroll` 窗口对象上的两个事件和事件。  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

你还可以指定一个可用的事件类型，这些字符串映射到预定义的事件集。  下表显示可用的事件类型和关联的事件映射。  

| 事件类型 | 相应的映射事件 |  
|:--- |:--- |  
| `mouse` | "单击"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"鼠标悬停"、""、"mousewheel" |  
| `key` | "keydown"、"keypress"、"keyup"、"textInput" |  
| `touch` | "touchcancel", "touchend", "touchmove", "touchstart" |  
| `control` | "模糊"、"更改"、"焦点"、"重置"、"调整大小"、"滚动"、"选择"、"提交"、"缩放" |  

在[图 22](#figure-22)中，与 `key` 输入文本字段上的事件相对应的事件类型 `key` 当前在 "**元素**" 面板中处于选中状态。  

```console
monitorEvents($0, "key");
```  

在[图 22](#figure-22)中，显示了在文本字段中键入字符后的示例输出。  

> ##### 图22  
> 监视键事件  
> ![监视键事件][ImageMonitorKey]  

## profile  

```console
profile([name])
```  

启动具有可选名称的 JavaScript CPU 性能分析会话。  [ProfileEnd （）](#profileend)方法完成配置文件并在 "**内存**" 面板中显示结果。  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  运行该 `profile()` 方法以开始分析。  
    
    ```console
    profile("My profile")
    ```  
    
1.  运行[profileEnd （）](#profileend)方法以停止分析并在 "**内存**" 面板中显示结果。  

配置文件也可能是嵌套的。  在[图 23](#figure-23)中，无论顺序如何，结果都是相同的。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> 多个 CPU 配置文件可能同时运行，您无需按创建顺序将其关闭。  

## profileEnd  

```console
profileEnd([name])
```  

完成 JavaScript CPU 分析会话并在 "**内存**" 面板中显示结果。  您必须运行[配置文件（）](#profile)方法。  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  运行[配置文件（）](#profile)方法开始分析。  
1.  运行 `profileEnd()` 方法以停止分析并在 "**内存**" 面板中显示结果。  
    
    ```console
    profileEnd("My profile")
    ```  

配置文件也可能是嵌套的。  在[图 23](#figure-23)中，无论顺序如何，结果都是相同的。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

结果在 "**内存**" 面板中显示为堆快照。  

> ##### 图23  
> 分组的配置文件  
> ![分组的配置文件][ImageGroupedProfiles]  

> [!NOTE]
> 多个 CPU 配置文件可能同时运行，您无需按创建顺序将其关闭。  

## 表  

```console
table(data[, columns])
```  

基于带有可选列标题的数据对象，基于表格格式记录对象数据。  在[图 24](#figure-24)中，显示了在控制台中使用表格的名称列表。  

```console
var names = {
    0:  {
        firstName:  "John",
        lastName:  "Smith"
    },
    1:  {
        firstName:  "Jane",
        lastName:  "Doe"
    }
};
table(names);
```  

> ##### 图24  
> 该 `table()` 方法  
> ![Table （）方法][ImageConsoleTable]  

## undebug  

```console
undebug(method)
```  

停止对指定方法的调试，以便在调用该方法时不再调用调试器。  

```console
undebug(getData);
```  

## unmonitor  

```console
unmonitor(method)
```  

停止对指定方法的监视。  此方法与[monitor （）](#monitor)方法配合使用。  

```console
unmonitor(getData);
```  

## unmonitorEvents  

```console
unmonitorEvents(object[, events])
```  

停止监视指定对象和事件的事件。  例如，以下事件将停止窗口对象上的所有事件监视。  

```console
unmonitorEvents(window);
```  

你还可以有选择地停止监视对象上的特定事件。  例如，以下代码开始监视 `mouse` 当前所选元素上的所有事件，然后停止监视 `mousemove` 事件 \ （可能减少控制台输出中的干扰 \）。  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## 相对值  

```console
values(object)
```  

返回一个数组，其中包含属于指定对象的所有属性的值。  

```console
values(object);
```  

<!--   -->  



<!-- image links -->  

[ImageRecentExpression]: /microsoft-edge/devtools-guide-chromium/media/console-arithmatic.msft.png "图1： $ _ 是最新计算的表达式"  
[ImageChangedRecentExpression]: /microsoft-edge/devtools-guide-chromium/media/console-array-length.msft.png "图2：当评估新命令时 $ _ 更改"  
[ImageElement0]: /microsoft-edge/devtools-guide-chromium/media/console-image-highlighted-$0.msft.png "图3： $0"  
[ImageElement1]: /microsoft-edge/devtools-guide-chromium/media/console-image-highlighted-$1.msft.png "图4： $1"  
[ImageElementImg]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image.msft.png "图5： $ （"img"）"  
[ImageElementImgSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-source.msft.png "图6： $ （"img"） src"  
[ImageElementImgNodeSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-filter-source.msft.png "图7： $ （"img"，querySelector （"标题-图像"））。 src"  
[ImageArrayElementImgSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-all.msft.png "图8：使用 $ $ （）选择文档中的所有图像并显示源"  
[ImageArrayElementImgNodeSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-filter-all.msft.png "图9：使用 $ $ （）选择文档中指定 <div> 元素后出现的所有图像并显示源"  
[ImageArrayXpath]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath.msft.png "图10：使用 XPath 选择器"  
[ImageArrayXpathChild]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath-sub-element.msft.png "图11：使用更复杂的 XPath 选择器"  
[ImageArrayXpathNode]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath-startnode.msft.png "图12：在 startNode 中使用 XPath 选择器"  
[ImageDebugMethod]: /microsoft-edge/devtools-guide-chromium/media/console-debug-text.msft.png "图13：使用 "调试" （）在方法内中断"  
[ImageLogObject]: /microsoft-edge/devtools-guide-chromium/media/console-dir-document-head-expanded.msft.png "图14：用 dir （）方法记录文档正文"  
[ImageInspectElement]: /microsoft-edge/devtools-guide-chromium/media/console-inspect-document-body.msft.png "图15：使用 "检查" （）检查元素"  
[ImageGetListeners]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document.msft.png "图16：使用 getEventListeners （文档）的输出"  
[ImageMultipleListeners]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png "图17：多个侦听器"  
[ImageListenersExpanded]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png "图18：侦听器对象的展开视图"  
[ImageConsoleKeysValues]: /microsoft-edge/devtools-guide-chromium/media/console-keys-values.msft.png "图19：键（）和值（）命令"  
[ImageConsoleMonitorSum]: /microsoft-edge/devtools-guide-chromium/media/console-function-monitor-sum.msft.png "图20： monitor （）方法"  
[ImageMonitorResize]: /microsoft-edge/devtools-guide-chromium/media/console-monitor-events-resize-window.msft.png "图21：监视窗口调整大小事件"  
[ImageMonitorKey]: /microsoft-edge/devtools-guide-chromium/media/console-monitor-events-type-t-y.msft.png "图22：监视键事件"  
[ImageGroupedProfiles]: /microsoft-edge/devtools-guide-chromium/media/console-memory-multiple-cpu-profiles.msft.png "图23：分组的配置文件"  
[ImageConsoleTable]: /microsoft-edge/devtools-guide-chromium/media/console-table-display.msft.png "图24： table （）方法"  

<!-- links -->  

[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "控制台 API 参考"  
[DevToolsConsoleApiConsoleDirObject]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir-控制台 API 参考"  
[DevToolsJavascriptBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints "如何在 Microsoft Edge DevTools 中暂停带有断点的代码"  
[DevToolsRenderingToolsJSRuntime]: /microsoft-edge/devtools-guide-chromium/rendering-tools/js-runtime "加快 JavaScript 运行时"  

[MDNConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console for dir （） |MDN"  
[MDNConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Dirxml （） |MDN"  
[MDNDocumentQuerySelector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "QuerySelector （） |MDN"  
[MDNDocumentQuerySelectorAll]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "QuerySelectorAll （） |MDN"  

[MonorailIssue1050237]: https://bugs.chromium.org/p/chromium/issues/detail?id=1050237 "问题1050237：调试（函数）无法正常工作 |Monorail"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/utilities)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
