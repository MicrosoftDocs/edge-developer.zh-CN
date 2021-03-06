---
description: Microsoft Edge DevTools 控制台中提供的便利命令参考。
title: 控制台实用工具 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: e7253bf5402a03d1659f56ba083bb87e93b3af38
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398824"
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

# <a name="console-utilities-api-reference"></a>控制台实用工具 API 参考  

控制台实用工具 API 包含一组用于执行常见任务的便利命令：选择和检查 DOM 元素、以可读格式显示数据、停止和启动探查器以及监视 DOM 事件。  

> [!WARNING]
> 以下命令仅适用于 Microsoft Edge DevTools 控制台。  如果从脚本运行，则命令不起作用。  

对于 `console.log()` 方法 `console.error()` 的其余部分，导航到控制台 `console.*` API [参考][DevToolsConsoleApi]。  

## <a name="recently-evaluated-expression"></a>最近计算表达式  

```console
$_
```  

返回最近计算表达式的值。  

下图中将计算一个简单的表达式 \ (`2 + 2` \) \ 。  然后 `$_` 计算该属性，其中包含相同的值。  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$_ 是最近评估的表达式" lightbox="../media/console-arithmatic.msft.png":::
   图  `$_` 1：是最近评估的表达式  
:::image-end:::  

下图中，计算表达式最初包含一个名称数组。  求值以查找数组的长度，存储在更改中的值 `$_.length` `$_` 将成为最新的计算表达式 `4` 。  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="$_ 在评估新命令时的更改" lightbox="../media/console-array-length.msft.png":::
   图  `$_` 2：评估新命令时的更改  
:::image-end:::  

## <a name="recently-chosen-element-or-javascript-object"></a>最近选择的元素或 JavaScript 对象  

```console
$0
```  

返回最近选择的元素或 JavaScript 对象。  `$1` 返回第二个最近选择一个，等等。  、、和命令用作对在 Elements 工具中检查的最后 `$0` `$1` `$2` `$3` `$4` 五个 DOM******** 元素或内存工具中选定的最后五个 JavaScript 堆对象的历史引用。  

:::row:::
   :::column span="1":::
      ```console
      $0
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $1
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $2
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ```console
      $3
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $4
      ```  
   :::column-end:::
   :::column span="1":::
   :::column-end:::
:::row-end:::  

在下图中， `img` 元素工具中 **选择了一个元素** 。  在 **控制台** 箱 `$0` 中，已进行评估并显示相同的元素。  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   图 3： `$0`  
:::image-end:::  

下图显示了在同一页面中选择的不同元素。  现在 `$0` 引用新选择的元素，同时 `$1` 返回之前选定的元素。  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   图 4： `$1`  
:::image-end:::  

## <a name="query-selector"></a>查询选择器  

```console
$(selector, [startNode])
```  

返回对具有指定 CSS 选择器的第一个 DOM 元素的引用。  此方法是 [document.querySelector ][MDNDocumentQuerySelector] () 别名。  

在下图中，返回对文档中 `<img>` 第一个元素的引用。  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$ ('img') " lightbox="../media/console-element-selector-image.msft.png":::
   图 5： `$('img')`  
:::image-end:::  

将鼠标悬停在返回的结果上，打开上下文菜单 \ (右键单击\) ，然后选择"元素面板中的**** 展示"以在 DOM 中查找它，或滚动到**视图**以显示在页面上。  

在下图中，将返回对当前选定元素的引用，并显示 src 属性。  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$ ('img') .src" lightbox="../media/console-element-selector-image-source.msft.png":::
   图 6： `$('img').src`  
:::image-end:::  

此方法还支持第二个参数 startNode，该参数指定要搜索元素的"元素"或 Node。  参数的默认值为 `document` 。  

在下图中，找到后 `img` 的第一个元素 `title--image` ，并显示 `src` 正确返回。  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$ ('img'， document.querySelector ('title--image') ) .src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   图 7： `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> 如果使用的库（如 jQuery）使用，则功能将被覆盖，并对应于该库中 `$` `$` 的实现。  

## <a name="query-selector-all"></a>查询选择器全部  

```console
$$(selector, [startNode])
```  

返回与指定的 CSS 选择器匹配的元素数组。  此方法等效于运行 [document.querySelectorAll () ][MDNDocumentQuerySelectorAll] 方法。  

在下面的代码示例和图中，用于创建当前文档中所有元素的数组并显示每个元素 `$$()` `<img>` `src` 的属性值。  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="使用 $$ () 选择文档中的所有图像并显示源" lightbox="../media/console-element-selector-image-all.msft.png":::
   图 8： `$$()` 用于选择文档中的所有图像并显示源  
:::image-end:::  

此方法还支持第二个参数 startNode，该参数指定用于搜索元素的元素或 Node。  参数的默认值为 `document` 。  

在下面的代码示例和图中，上一个代码示例和图的修改版本用于创建一个数组，该数组包含当前文档中选定节点之后 `$$()` `<img>` 的所有元素。  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="使用 $$ () 选择文档中指定 <div> 元素之后显示的所有图像并显示源" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   图 9：用于选择文档中指定元素之后显示的所有图像 `$$()` `<div>` 并显示源  
:::image-end:::  

> [!NOTE]
> 在 `Shift` + `Enter` 控制台中选择以在不运行脚本的情况下启动新行。  

## <a name="xpath"></a>XPath  

```console
$x(path, [startNode])
```  

返回与指定的 XPath 表达式匹配的 DOM 元素数组。  

在下面的代码示例和图中，将返回页面上 `<p>` 的所有元素。  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="使用 XPath 选择器" lightbox="../media/console-array-xpath.msft.png":::
   图 10：使用 XPath 选择器  
:::image-end:::  

在下面的代码示例和图中，将返回包含 `<p>` 元素 `<a>` 的所有元素。  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="使用更复杂的 XPath 选择器" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   图 11：使用更复杂的 XPath 选择器  
:::image-end:::  

与其他选择器命令类似，具有可选的第二个参数，用于指定要搜索元素的元素或 `$x(path)` `startNode` Node。  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="将 XPath 选择器与 startNode 一同使用" lightbox="../media/console-array-xpath-startnode.msft.png":::
   图 12：将 XPath 选择器与 `startNode`  
:::image-end:::  

## <a name="clear"></a>clear  

```console
clear()
```  

清除历史记录的控制台。  

```console
clear()
```  

## <a name="copy"></a>copy  

```console
copy(object)
```  

该方法 `copy(object)` 将指定对象的字符串表示形式复制到剪贴板。  

```console
copy($0)
```  

## <a name="debug"></a>调试  

```console
debug(method)
```  

>[!NOTE]
> [Chromium 问题#1050237][MonorailIssue1050237]跟踪函数的 `debug()` Bug。  如果遇到问题，请尝试 [改为使用][DevtoolsJavascriptBreakpoints] 断点。  

请求指定方法时，将调用调试程序，并中断 **源** 工具上的方法，从而允许您逐步执行代码并调试它。  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="使用调试工具在方法 () " lightbox="../media/console-debug-text.msft.png":::
   图 13：使用 `debug()`  
:::image-end:::  

用于 `undebug(method)` 停止在方法上中断，或使用 UI 禁用所有断点。  

有关断点详细信息，请导航到"使用断[点暂停代码"。][DevToolsJavascriptBreakpoints]  

## <a name="dir"></a>dir  

```console
dir(object)
```  

显示指定对象的所有属性的对象样式列表。  此方法是 [console.dir ][MDNConsoleDir] () 别名。  

在 `document.head` 控制台中计算以显示与标记之间的 `<head>` `</head>` HTML。  在下面的代码示例和图中，在控制台中使用后将显示对象 `console.dir()` 样式列表。  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="使用 dir () 记录 document.head" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   图 14：使用 `document.head` 方法 `dir()` 日志记录  
:::image-end:::  

有关详细信息，请导航到 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 控制台 API 中的条目。  

## <a name="dirxml"></a>dirxml  

```console
dirxml(object)
```  

打印指定对象的 XML 表示形式，如 **元素** 工具中显示。  此方法等效于 [console.dirxml () ][MDNConsoleDirxml] 方法。  

## <a name="inspect"></a>inspect  

```console
inspect(object/method)
```  

在相应的面板中打开并选择指定的元素或对象：DOM 元素的元素**** 工具或 JavaScript 堆对象的**** Memory 工具。  

在下面的代码示例和图中，将在 `document.body` Elements 工具 **中** 打开。  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="使用检查属性检查 () " lightbox="../media/console-inspect-document-body.msft.png":::
   图 15：使用 `inspect()`  
:::image-end:::  

传递要检查的方法时，该方法将在 **源** 工具中打开文档供您检查。  

## <a name="geteventlisteners"></a>getEventListeners  

```console
getEventListeners(object)
```  

返回指定对象上注册的事件侦听器。  返回值是包含每个已注册事件类型 \ (如 `click` `keydown` 或 \) 的数组的对象。  每个数组的成员都是描述为每种类型注册的侦听器的对象。  下面的代码示例图列出了在文档对象上注册的所有事件侦听器。  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="使用 getEventListeners 文档 (输出) " lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   图 16：使用的结果 `getEventListeners(document)`  
:::image-end:::  

如果指定对象上注册了多个侦听器，则数组包含每个侦听器的成员。  下图中为事件在文档元素上注册了两个 `click` 事件侦听器。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="多个侦听器" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   图 17：多个侦听器  
:::image-end:::  

您可以进一步展开以下每个对象以浏览属性。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="侦听器对象的扩展视图" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   图 18：侦听器对象的扩展视图  
:::image-end:::  

## <a name="keys"></a>键  

```console
keys(object)
```  

返回一个数组，其中包含属于指定对象的属性的名称。  若要获取相同属性的关联值，请使用 `values()` 。  

例如，假设应用程序定义了以下对象。  

```console
var player1 =   
```  

在下面的代码示例和图中，为了简单起见，在键入之前和在控制台中) 在全局命名空间 \ (中定义 `player1` `keys(player1)` `values(player1)` 结果。  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="键 () 和值 () 命令" lightbox="../media/console-keys-values.msft.png":::
   图 19：And `keys()` `values()` 命令  
:::image-end:::  

## <a name="monitor"></a>监视器  

```console
monitor(method)
```  

向控制台记录一条消息，指示方法名称以及调用该方法时传递给该方法的参数。  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="监视器 () 方法" lightbox="../media/console-function-monitor-sum.msft.png":::
   图 20： `monitor()` 方法  
:::image-end:::  

用于 `unmonitor(method)` 停止监视。  

## <a name="monitorevents"></a>monitorEvents  

```console
monitorEvents(object[, events])
```  

当指定对象上发生指定事件之一时，该事件对象将记录到控制台。  可以指定要监视的单个事件、事件数组或映射到预定义的事件集合的泛型事件类型之一。  查看以下代码示例和图。  

下面监视窗口对象上的所有调整大小事件。  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="监视窗口大小事件" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   图 21：监视窗口大小调整事件  
:::image-end:::  

下面定义了一个数组，用于监视窗口对象上的两 `resize` `scroll` 者以及事件。  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

还可以指定一种可用的事件类型，即映射到预定义的事件集的字符串。  下表显示可用的事件类型和关联的事件映射。  

| 事件类型 | 相应的映射事件 |  
|:--- |:--- |  
| `mouse` | "click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mouseover"、"mouseup"、"mousewheel" |  
| `key` | "keydown"、"keypress"、"keyup"、"textInput" |  
| `touch` | "touchcancel"、"touchend"、"touchmove"、"touchstart" |  
| `control` | "blur"、"change"、"focus"、"reset"、"resize"、"scroll"、"select"、"submit"、"zoom" |  

在下面的代码示例中，当前在 Elements 工具中选择了与输入文本字段上的事件 `key` `key` 对应的事件类型。 ****  

```console
monitorEvents($0, "key");
```  

下图显示了在文本字段中键入字符后的示例输出。  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="监视关键事件" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   图 22：监视关键事件  
:::image-end:::  

## <a name="profile"></a>profile  

```console
profile([name])
```  

使用可选名称启动 JavaScript CPU 分析会话。  [profileEnd () ](#profileend)方法完成配置文件，并显示**内存工具中**的结果。  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  运行 `profile()` 该方法以开始分析。  
    
    ```console
    profile("My profile")
    ```  
    
1.  运行 [profileEnd () ](#profileend) 方法以停止分析，并显示 **内存工具中** 的结果。  

配置文件也可以嵌套。  在下面的代码示例和图中，无论顺序如何，结果都是相同的。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> 多个 CPU 配置文件可以同时运行，并且不需要按创建顺序关闭每个配置文件。  

## <a name="profileend"></a>profileEnd  

```console
profileEnd([name])
```  

完成 JavaScript CPU 分析会话，并显示 **内存工具中** 的结果。  您必须运行 [配置文件 () 方法 ](#profile) 。  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  运行 [配置文件 () ](#profile) 方法开始分析。  
1.  运行 `profileEnd()` 该方法以停止分析，在"内存"工具 **中显示** 结果。  
    
    ```console
    profileEnd("My profile")
    ```  

配置文件也可以嵌套。  在下面的代码示例中，无论顺序如何，结果都是相同的。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

结果在内存工具中显示为堆 **快照** 。  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="分组配置文件" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   图 23：分组配置文件  
:::image-end:::  

> [!NOTE]
> 多个 CPU 配置文件可以同时运行，并且不需要按创建顺序关闭每个配置文件。  

## <a name="queryobjects"></a>queryObjects  

```console
queryObjects(Constructor)
```  

返回使用指定构造函数创建的对象数组。  范围 `queryObjects()` 是控制台中当前选择的运行时上下文。

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      返回所有 `Promises` 。  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      返回所有 HTML 元素。  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      返回使用 实例化的所有对象 `new functionName()` 。  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a>table  

```console
table(data[, columns])
```  

使用基于数据对象的表格格式记录对象数据，并添加可选列标题。  在下面的代码示例和图中，将显示使用控制台中的表的名称列表。  

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

:::image type="complex" source="../media/console-table-display.msft.png" alt-text="table () 方法的结果" lightbox="../media/console-table-display.msft.png":::
   图 24：方法 `table()` 的结果  
:::image-end:::  

## <a name="undebug"></a>undebug  

```console
undebug(method)
```  

停止对指定方法的调试，以便调用该方法时，将不再调用调试器。  

```console
undebug(getData);
```  

## <a name="unmonitor"></a>unmonitor  

```console
unmonitor(method)
```  

停止对指定方法的监视。  此方法与监视器或 [ () 一起 ](#monitor) 使用。  

```console
unmonitor(getData);
```  

## <a name="unmonitorevents"></a>unmonitorEvents  

```console
unmonitorEvents(object[, events])
```  

停止监视指定对象和事件的事件。  例如，以下操作将停止窗口对象上的所有事件监视。  

```console
unmonitorEvents(window);
```  

还可以有选择地停止监视对象上的特定事件。  例如，以下代码开始监视当前选定元素上的所有事件，然后停止 `mouse` `mousemove` 监视事件 \ (可能以减少控制台输出\) 。  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## <a name="values"></a>值  

```console
values(object)
```  

返回一个数组，其中包含属于指定对象的所有属性的值。  

```console
values(object);
```  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "控制台 API 参考"  
[DevToolsConsoleApiConsoleDirObject]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - 控制台 API 参考"  
[DevToolsJavascriptBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints "如何使用 Microsoft Edge DevTools 中的断点暂停代码"  
[DevToolsRenderingToolsJSRuntime]: /microsoft-edge/devtools-guide-chromium/rendering-tools/js-runtime "加快 JavaScript 运行时"  

[MDNConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console.dir () |MDN"  
[MDNConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Console.dirxml () |MDN"  
[MDNDocumentQuerySelector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "Document.querySelector () |MDN"  
[MDNDocumentQuerySelectorAll]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "Document.querySelectorAll () |MDN"  

[MonorailIssue1050237]: https://bugs.chromium.org/p/chromium/issues/detail?id=1050237 "问题 1050237：调试 (函数) 运行|Monorail"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/utilities)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
