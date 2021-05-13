---
description: 开发人员工具控制台中提供的便利Microsoft Edge引用。
title: 控制台实用工具 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 436f2807c5fab1723ca6cc93fddc68d9ecf12db7
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564530"
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

控制台实用程序 API 包含一组方便命令，用于完成以下常见任务。  

*   选择并检查 DOM 元素  
*   以可读格式显示数据  
*   停止并启动探查器  
*   监视 DOM 事件  
    
> [!WARNING]
> 以下命令仅适用于开发人员Microsoft Edge**控制台**。  如果从脚本运行，则命令不起作用。  

有关 和 方法以及方法其余部分的信息， `console.log()` `console.error()` `console.*` 请导航到"控制台 API[参考"。][DevToolsConsoleApi]  

## <a name="recently-evaluated-expression"></a>最近计算表达式  

### <a name="console-syntax"></a>控制台语法  

```console
$_
```  

此命令返回最近计算表达式的值。  

### <a name="console-example"></a>控制台示例  

在下图中，将计算一个简单的表达式 \ (`2 + 2` \) 。  然后 `$_` 计算属性，其中包含相同的值。  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$_ 是最近评估的表达式" lightbox="../media/console-arithmatic.msft.png":::
   `$_` 是最近计算表达式  
:::image-end:::  

在下图中，计算表达式最初包含一个名称数组。  计算 以查找数组的长度，存储在 中的值 `$_.length` `$_` 将成为最新的计算表达式 `4` 。  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="$_ 评估新命令时的更改" lightbox="../media/console-array-length.msft.png":::
   `$_` 评估新命令时更改  
:::image-end:::  

---  

## <a name="recently-chosen-element-or-javascript-object"></a>最近选择的元素或 JavaScript 对象  

### <a name="console-syntax"></a>控制台语法  

```console
$0
```  

此命令返回最近选择的元素或 JavaScript 对象。  `$1` 返回第二个最近选择一个，等等。  、 、 和 命令用作对在元素工具中检查的最后 `$0` `$1` `$2` `$3` `$4` 五个 DOM******** 元素或内存工具中选定的最后五个 JavaScript 堆对象的历史引用。  

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
      &nbsp;
   :::column-end:::
:::row-end:::  

### <a name="console-example"></a>控制台示例  

在下图中， `img` 在"元素"工具中选择了 **一个元素** 。  在 **控制台箱** 中 `$0` ，已进行评估并显示相同的元素。  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   该 `$0`  
:::image-end:::  

下图中，图像显示在同一网页中选择的不同元素。  `$0`现在引用新选择的元素，而 `$1` 返回之前选择的元素。  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   该 `$1`  
:::image-end:::  

---  

## <a name="query-selector"></a>查询选择器  

### <a name="console-syntax"></a>控制台语法  

```console
$(selector, [startNode])
```  

此命令返回对具有指定 CSS 选择器的第一个 DOM 元素的引用。  此方法是 [document.querySelector ][MdnDocsWebApiDocumentQueryselector] () 别名。  

### <a name="console-example"></a>控制台示例  

在下图中，将返回对网页 `<img>` 中第一个元素的引用。  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$ ('img') " lightbox="../media/console-element-selector-image.msft.png":::
   该 `$('img')`  
:::image-end:::  

若要在 DOM 中查找第一个元素或在网页上查找并显示该元素，请完成以下操作。  

1.  将鼠标悬停在返回的结果上。  
1.  打开上下文菜单\（右键单击\）。  
1.  选择 **"元素面板"中的"展示"。**  

在下图中，将返回对当前选择的元素的引用， `src` 并显示 属性。  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$ ('img') .src" lightbox="../media/console-element-selector-image-source.msft.png":::
   该 `$('img').src`  
:::image-end:::  

此方法还支持第二个参数 ，用于指定要搜索的元素或 `startNode` 节点。  参数的默认值为 `document` 。  

在下图中，找到 `img` 元素后的第一个元素 `title--image` ，并返回 `src` `img` 元素的 属性。  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$ ('img'， document.querySelector ('title--image') ) .src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   该 `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> 如果使用的库（如 jQuery）使用 ，则功能将被覆盖，并且对应于该库中 `$` `$` 的实现。  

---  

## <a name="query-selector-all"></a>查询选择器全部  

### <a name="console-syntax"></a>控制台语法  

```console
$$(selector, [startNode])
```  

此命令返回匹配指定 CSS 选择器的元素数组。  此方法等效于运行 [document.querySelectorAll () ][MdnDocsWebApiDocumentQueryselectorall] 方法。  

### <a name="console-example"></a>控制台示例  

在下面的代码示例和图中，使用 创建当前网页中所有元素的数组 `$$()` `<img>` 并显示每个 `src` 元素的 属性值。  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="使用 $$ () 选择网页中的所有图像并显示源" lightbox="../media/console-element-selector-image-all.msft.png":::
   用于 `$$()` 选择网页中所有图像并显示源  
:::image-end:::  

此方法还支持第二个参数 ，用于指定要搜索的元素或 `startNode` 节点。  参数的默认值为 `document` 。  

在下面的代码示例和图中，上一个代码示例和图的修改版本用于创建一个数组，该数组包含当前网页中所选节点之后 `$$()` `<img>` 出现的所有元素。  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="使用 $$ () 选择在网页中的指定 div <div>后显示的所有图像并显示源" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   用于 `$$()` 选择网页中指定元素之后显示的所有图像 `<div>` 并显示源  
:::image-end:::  

> [!NOTE]
> 在 `Shift` + `Enter` 控制台**中选择以**在不运行脚本的情况下启动新行。  

---  

## <a name="xpath"></a>XPath  

### <a name="console-syntax"></a>控制台语法  

```console
$x(path, [startNode])
```  

此命令返回匹配指定 XPath 表达式的 DOM 元素的数组。  

### <a name="console-example"></a>控制台示例  

在下面的代码示例和图中，将返回 `<p>` 网页上的所有元素。  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="使用 XPath 选择器" lightbox="../media/console-array-xpath.msft.png":::
   使用 XPath 选择器  
:::image-end:::  

在下面的代码示例和图中，将返回 `<p>` 包含元素 `<a>` 的所有元素。  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="使用更复杂的 XPath 选择器" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   使用更复杂的 XPath 选择器  
:::image-end:::  

与其他选择器命令类似，具有可选的第二个参数 ，用于指定要搜索的元素或 `$x(path)` `startNode` 节点。  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="将 XPath 选择器与 startNode 一同使用" lightbox="../media/console-array-xpath-startnode.msft.png":::
   将 XPath 选择器与 `startNode`  
:::image-end:::  

---  

## <a name="clear"></a>clear  

### <a name="console-syntax"></a>控制台语法  

```console
clear()
```  

此命令清除历史记录的控制台。  

### <a name="console-example"></a>控制台示例  

```console
clear()
```  

## <a name="copy"></a>copy  

### <a name="console-syntax"></a>控制台语法  

```console
copy(object)
```  

此方法将指定对象的字符串表示形式复制到剪贴板。  

### <a name="console-example"></a>控制台示例  

```console
copy($0)
```  

---  

## <a name="debug"></a>调试  

### <a name="console-syntax"></a>控制台语法  

```console
debug(method)
```  

>[!NOTE]
> Chromium[跟踪#1050237][CR1050237] Bug 时出现 `debug()` 的问题。  如果遇到问题，请尝试改为 [使用断][DevtoolsJavascriptBreakpoints] 点。  

请求指定方法时，调试程序在 Sources 工具的 方法内调用**和中断。**  它允许你逐步调试代码。  

### <a name="console-example"></a>控制台示例  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="使用调试工具在方法 () " lightbox="../media/console-debug-text.msft.png":::
   在方法内使用 `debug()`  
:::image-end:::  

用于 `undebug(method)` 停止方法上的中断，或使用 UI 关闭所有断点。  

有关断点详细信息，请导航到如何在[DevTools][DevtoolsJavascriptBreakpoints]中暂停包含断Microsoft Edge代码。  

---  

## <a name="dir"></a>dir  

### <a name="console-syntax"></a>控制台语法  

```console
dir(object)
```  

此命令显示指定对象的所有属性的对象样式列表。  此方法是 [console.dir ][MdnDocsWebApiConsoleDir] () 别名。  

在 `document.head` 控制台 **中进行评估** ，以显示 和 标记 `<head>` 之间的 `</head>` HTML。  

### <a name="console-example"></a>控制台示例  

在下面的代码示例和图中，在控制台 中使用 后将显示对象 `console.dir()` 样式 **列表**。  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="使用 dir 方法记录 document.head () 方法" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   使用 `document.head` 方法 `dir()` 日志记录  
:::image-end:::  

有关详细信息，请导航到控制台 API[中的 console.dir () 。][DevToolsConsoleApiConsoleDirObject]  

---  

## <a name="dirxml"></a>dirxml  

### <a name="console-syntax"></a>控制台语法  

```console
dirxml(object)
```  

此命令打印指定对象的 XML 表示形式，如 **元素** 工具中显示。  此方法等效于 [console.dirxml () ][MdnDocsWebApiConsoleDirxml] 方法。  

---  

## <a name="inspect"></a>inspect  

### <a name="console-syntax"></a>控制台语法  

```console
inspect(object/method)
```  

此命令将在适当的面板中打开并选择指定的元素或对象：DOM 元素的 **Elements** 工具或 JavaScript 堆对象的 **Memory** 工具。  

### <a name="console-example"></a>控制台示例  

在下面的代码示例和图中，将在 `document.body` "元素"工具 **中** 打开 。  

### <a name="console-example"></a>控制台示例  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="检查元素并检查 () " lightbox="../media/console-inspect-document-body.msft.png":::
   使用 检查元素 `inspect()`  
:::image-end:::  

传递要检查的方法时，该方法将在 **"** 源"工具中打开网页供你检查。  

---  

## <a name="geteventlisteners"></a>getEventListeners  

### <a name="console-syntax"></a>控制台语法  

```console
getEventListeners(object)
```  

此命令返回在指定对象上注册的事件侦听器。  返回值是包含每个已注册事件类型 \ (（如 或 `click` `keydown` \) ）的数组的对象。  每个数组的成员是描述为每种类型注册的侦听器的对象。  

### <a name="console-example"></a>控制台示例  

下面的代码段和图列出了在 对象上注册的所有事件 `document` 侦听器。  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="使用 getEventListeners 文档库 (输出) " lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   使用 的结果 `getEventListeners(document)`  
:::image-end:::  

如果指定对象上注册了多个侦听器，则数组将包含每个侦听器的成员。  下图中，在 事件的 元素上注册了两 `document` 个 `click` 事件侦听器。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="多个侦听器" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   多个侦听器  
:::image-end:::  

可以进一步展开以下每个对象来浏览属性。  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="侦听器对象的扩展视图" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   侦听器对象的扩展视图  
:::image-end:::  

---  

## <a name="keys"></a>键  

### <a name="console-syntax"></a>控制台语法  

```console
keys(object)
```  

此命令返回一个数组，其中包含属于指定对象的属性的名称。  若要获取相同属性的关联值，请使用 `values()` 。  

### <a name="console-example"></a>控制台示例  

例如，假设应用程序定义了以下对象。  

```console
var player1 = {"name": "Ted", "level": 42}
```  

在下面的代码示例和图中，为了简单起见，在键入和在控制台中) 在全局命名空间 \ (中定义了 `player1` `keys(player1)` `values(player1)` 结果假定。  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="键 () 和值 () 命令" lightbox="../media/console-keys-values.msft.png":::
   和 `keys()` `values()` 命令  
:::image-end:::  

---  

## <a name="monitor"></a>监视器  

### <a name="console-syntax"></a>控制台语法  

```console
monitor(method)
```  

此命令向控制台记录一条消息，指示方法名称以及作为请求的一部分传递给方法的参数。  

### <a name="console-example"></a>控制台示例  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="监视器 () 方法" lightbox="../media/console-function-monitor-sum.msft.png":::
   `monitor()`方法  
:::image-end:::  

用于 `unmonitor(method)` 结束监视。  

---  

## <a name="monitorevents"></a>monitorEvents  

### <a name="console-syntax"></a>控制台语法  

```console
monitorEvents(object[, events])
```  

当指定对象上发生指定事件之一时，该事件对象将记录到控制台。  可以指定要监视的单个事件、事件数组或映射到预定义的事件集合的泛型事件类型之一。  

### <a name="console-example"></a>控制台示例  

查看以下代码示例和图。  

下面监视 window 对象上的所有调整大小事件。  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="监视窗口大小事件" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   监视窗口大小事件  
:::image-end:::  

以下代码段定义一个数组，用于监视窗口对象上的 和 `resize` `scroll` 事件。  

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

在下面的代码示例中，当前在 Elements 工具中选择了与输入文本字段上的事件 `key` `key` 对应的 **事件** 类型。  

```console
monitorEvents($0, "key");
```  

下图显示了在文本字段中键入字符后的示例输出。  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="监视关键事件" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   监视关键事件  
:::image-end:::  

---  

## <a name="profile"></a>profile  

### <a name="console-syntax"></a>控制台语法  

```console
profile([name])
```  

此命令使用可选名称启动 JavaScript CPU 分析会话。  [profileEnd () ](#profileend)方法完成配置文件，并显示内存工具**中**的结果。  <!--Navigate to [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJsRuntime].  -->  

### <a name="console-example"></a>控制台示例  

1.  运行 `profile()` 方法以开始分析。  
    
    ```console
    profile("My profile")
    ```  
    
1.  运行 [profileEnd () ](#profileend) 方法停止分析和在内存工具 **中显示** 结果。  

配置文件也可以嵌套。  在下面的代码示例和图中，无论顺序如何，结果都是相同的。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> 多个 CPU 配置文件可以同时运行，并且不需要按照创建顺序关闭每个配置文件。  

---  

## <a name="profileend"></a>profileEnd  

### <a name="console-syntax"></a>控制台语法  

```console
profileEnd([name])
```  

此命令完成 JavaScript CPU 分析会话，并显示内存工具 **中** 的结果。  必须运行配置文件 [ () ](#profile) 方法。  <!--Navigate to [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJsRuntime].  -->  

### <a name="console-example"></a>控制台示例  

1.  运行 [配置文件 () ](#profile) 方法开始分析。  
1.  运行 `profileEnd()` 方法以停止分析，在内存工具中 **显示** 结果。  
    
    ```console
    profileEnd("My profile")
    ```  

配置文件也可以嵌套。  在下面的代码示例和图中，无论顺序如何，结果都是相同的。  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

结果在内存工具中显示为堆 **快照** 。  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="分组配置文件" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   分组配置文件  
:::image-end:::  

> [!NOTE]
> 多个 CPU 配置文件可以同时运行，并且不需要按照创建顺序关闭每个配置文件。  

---  

## <a name="queryobjects"></a>queryObjects  

### <a name="console-syntax"></a>控制台语法  

```console
queryObjects(Constructor)
```  

此命令返回使用指定构造函数创建的对象数组。  的范围 `queryObjects()` 是控制台 中当前选择的运行时 **上下文**。  

### <a name="console-example"></a>控制台示例  

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

### <a name="console-syntax"></a>控制台语法  

```console
table(data[, columns])
```  

此命令根据数据对象（列标题为可选）使用表格式记录对象数据。  

### <a name="console-example"></a>控制台示例  

下面的代码示例和图显示了使用控制台中的表的名称列表。  

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

:::image type="complex" source="../media/console-table-display.msft.png" alt-text="table 方法 () 结果" lightbox="../media/console-table-display.msft.png":::
   方法 `table()` 的结果  
:::image-end:::  

---  

## <a name="undebug"></a>undebug  

### <a name="console-syntax"></a>控制台语法  

```console
undebug(method)
```  

此命令停止对指定方法的调试。 因此，当请求该方法时，将不再调用调试器。  

### <a name="console-example"></a>控制台示例  

```console
undebug(getData);
```  

---  

## <a name="unmonitor"></a>unmonitor  

### <a name="console-syntax"></a>控制台语法  

```console
unmonitor(method)
```  

此命令停止对指定方法的监视。  此方法与监视器和 () [一起 ](#monitor) 使用。  

### <a name="console-example"></a>控制台示例  

```console
unmonitor(getData);
```  

---  

## <a name="unmonitorevents"></a>unmonitorEvents  

### <a name="console-syntax"></a>控制台语法  

```console
unmonitorEvents(object[, events])
```  

此命令停止监视指定对象和事件的事件。  

### <a name="console-example"></a>控制台示例  

例如，以下代码段停止窗口对象上的所有事件监视。  

```console
unmonitorEvents(window);
```  

还可以有选择地停止监视对象上的特定事件。  例如，以下代码开始监视当前选择的元素上的所有事件，然后停止监视 `mouse` `mousemove` 事件 \ (也许以减少控制台输出\) 。  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

---  

## <a name="values"></a>values  

### <a name="console-syntax"></a>控制台语法  

```console
values(object)
```  

此命令返回一个数组，其中包含属于指定对象的所有属性的值。  

### <a name="console-example"></a>控制台示例  

```console
values(object);
```  

---  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  
[DevToolsConsoleApiConsoleDirObject]: ./api.md#dir "dir - 控制台 API |Microsoft Docs"  

[DevtoolsJavascriptBreakpoints]: ../javascript/breakpoints.md "如何在 Microsoft Edge 开发工具中使用断点暂停代码 | Microsoft Doc"  

[DevtoolsRenderingToolsJsRuntime]: ../rendering-tools/js-runtime.md "加快 JavaScript 运行时|Microsoft Docs"  

[CR1050237]: https://crbug.com/1050237 "问题 1050237：调试 (函数) 运行|Chromium Bug"  

[MdnDocsWebApiConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console.dir () |MDN"  
[MdnDocsWebApiConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Console.dirxml () |MDN"  
[MdnDocsWebApiDocumentQueryselector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "Document.querySelector () |MDN"  
[MdnDocsWebApiDocumentQueryselectorall]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "Document.querySelectorAll () |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/utilities)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
