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

# <a name="console-utilities-api-reference"></a><span data-ttu-id="ec411-104">控制台实用工具 API 参考</span><span class="sxs-lookup"><span data-stu-id="ec411-104">Console Utilities API reference</span></span>  

<span data-ttu-id="ec411-105">控制台实用工具 API 包含一组用于执行常见任务的便利命令：选择和检查 DOM 元素、以可读格式显示数据、停止和启动探查器以及监视 DOM 事件。</span><span class="sxs-lookup"><span data-stu-id="ec411-105">The Console Utilities API contains a collection of convenience commands for performing common tasks:  selecting and inspecting DOM elements, displaying data in readable format, stopping and starting the profiler, and monitoring DOM events.</span></span>  

> [!WARNING]
> <span data-ttu-id="ec411-106">以下命令仅适用于 Microsoft Edge DevTools 控制台。</span><span class="sxs-lookup"><span data-stu-id="ec411-106">The following commands only work in the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="ec411-107">如果从脚本运行，则命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="ec411-107">The commands do not work if run from your scripts.</span></span>  

<span data-ttu-id="ec411-108">对于 `console.log()` 方法 `console.error()` 的其余部分，导航到控制台 `console.*` API [参考][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="ec411-108">For the `console.log()` and `console.error()` methods the rest of the `console.*` methods, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  

## <a name="recently-evaluated-expression"></a><span data-ttu-id="ec411-109">最近计算表达式</span><span class="sxs-lookup"><span data-stu-id="ec411-109">Recently Evaluated Expression</span></span>  

```console
$_
```  

<span data-ttu-id="ec411-110">返回最近计算表达式的值。</span><span class="sxs-lookup"><span data-stu-id="ec411-110">Returns the value of the most recently evaluated expression.</span></span>  

<span data-ttu-id="ec411-111">下图中将计算一个简单的表达式 \ (`2 + 2` \) \ 。</span><span class="sxs-lookup"><span data-stu-id="ec411-111">In the following figure, a simple expression \(`2 + 2`\) is evaluated.</span></span>  <span data-ttu-id="ec411-112">然后 `$_` 计算该属性，其中包含相同的值。</span><span class="sxs-lookup"><span data-stu-id="ec411-112">The `$_` property is then evaluated, which contains the same value.</span></span>  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$_ 是最近评估的表达式" lightbox="../media/console-arithmatic.msft.png":::
   <span data-ttu-id="ec411-114">图  `$_` 1：是最近评估的表达式</span><span class="sxs-lookup"><span data-stu-id="ec411-114">Figure 1:  `$_` is the most recently evaluated expression</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-115">下图中，计算表达式最初包含一个名称数组。</span><span class="sxs-lookup"><span data-stu-id="ec411-115">In the following figure, the evaluated expression initially contains an array of names.</span></span>  <span data-ttu-id="ec411-116">求值以查找数组的长度，存储在更改中的值 `$_.length` `$_` 将成为最新的计算表达式 `4` 。</span><span class="sxs-lookup"><span data-stu-id="ec411-116">Evaluating `$_.length` to find the length of the array, the value stored in `$_` changes to become the latest evaluated expression, `4`.</span></span>  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="$_ 在评估新命令时的更改" lightbox="../media/console-array-length.msft.png":::
   <span data-ttu-id="ec411-118">图  `$_` 2：评估新命令时的更改</span><span class="sxs-lookup"><span data-stu-id="ec411-118">Figure 2:  `$_` changes when new commands are evaluated</span></span>  
:::image-end:::  

## <a name="recently-chosen-element-or-javascript-object"></a><span data-ttu-id="ec411-119">最近选择的元素或 JavaScript 对象</span><span class="sxs-lookup"><span data-stu-id="ec411-119">Recently Chosen Element Or JavaScript Object</span></span>  

```console
$0
```  

<span data-ttu-id="ec411-120">返回最近选择的元素或 JavaScript 对象。</span><span class="sxs-lookup"><span data-stu-id="ec411-120">Returns the most recently selected element or JavaScript object.</span></span>  `$1` <span data-ttu-id="ec411-121">返回第二个最近选择一个，等等。</span><span class="sxs-lookup"><span data-stu-id="ec411-121">returns the second most recently selected one, and so on.</span></span>  <span data-ttu-id="ec411-122">、、和命令用作对在 Elements 工具中检查的最后 `$0` `$1` `$2` `$3` `$4` 五个 DOM\*\*\*\*\*\*\*\* 元素或内存工具中选定的最后五个 JavaScript 堆对象的历史引用。</span><span class="sxs-lookup"><span data-stu-id="ec411-122">The `$0`, `$1`, `$2`, `$3`, and `$4` commands work as a historical reference to the last five DOM elements inspected within the **Elements** tool or the last five JavaScript heap objects selected in the **Memory** tool.</span></span>  

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

<span data-ttu-id="ec411-123">在下图中， `img` 元素工具中 **选择了一个元素** 。</span><span class="sxs-lookup"><span data-stu-id="ec411-123">In the following figure, an `img` element is selected in the **Elements** tool.</span></span>  <span data-ttu-id="ec411-124">在 **控制台** 箱 `$0` 中，已进行评估并显示相同的元素。</span><span class="sxs-lookup"><span data-stu-id="ec411-124">In the **Console** drawer, `$0` has been evaluated and displays the same element.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   <span data-ttu-id="ec411-126">图 3：</span><span class="sxs-lookup"><span data-stu-id="ec411-126">Figure 3:  The</span></span> `$0`  
:::image-end:::  

<span data-ttu-id="ec411-127">下图显示了在同一页面中选择的不同元素。</span><span class="sxs-lookup"><span data-stu-id="ec411-127">In the following figure, the image shows a different element selected in the same page.</span></span>  <span data-ttu-id="ec411-128">现在 `$0` 引用新选择的元素，同时 `$1` 返回之前选定的元素。</span><span class="sxs-lookup"><span data-stu-id="ec411-128">The `$0` now refers to the newly selected element, while `$1` returns the previously selected one.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   <span data-ttu-id="ec411-130">图 4：</span><span class="sxs-lookup"><span data-stu-id="ec411-130">Figure 4:  The</span></span> `$1`  
:::image-end:::  

## <a name="query-selector"></a><span data-ttu-id="ec411-131">查询选择器</span><span class="sxs-lookup"><span data-stu-id="ec411-131">Query Selector</span></span>  

```console
$(selector, [startNode])
```  

<span data-ttu-id="ec411-132">返回对具有指定 CSS 选择器的第一个 DOM 元素的引用。</span><span class="sxs-lookup"><span data-stu-id="ec411-132">Returns the reference to the first DOM element with the specified CSS selector.</span></span>  <span data-ttu-id="ec411-133">此方法是 [document.querySelector ][MDNDocumentQuerySelector] () 别名。</span><span class="sxs-lookup"><span data-stu-id="ec411-133">This method is an alias for the [document.querySelector()][MDNDocumentQuerySelector] method.</span></span>  

<span data-ttu-id="ec411-134">在下图中，返回对文档中 `<img>` 第一个元素的引用。</span><span class="sxs-lookup"><span data-stu-id="ec411-134">In the following figure, a reference to the first `<img>` element in the document is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$ ('img') " lightbox="../media/console-element-selector-image.msft.png":::
   <span data-ttu-id="ec411-136">图 5：</span><span class="sxs-lookup"><span data-stu-id="ec411-136">Figure 5:  The</span></span> `$('img')`  
:::image-end:::  

<span data-ttu-id="ec411-137">将鼠标悬停在返回的结果上，打开上下文菜单 \ (右键单击\) ，然后选择"元素面板中的\*\*\*\* 展示"以在 DOM 中查找它，或滚动到**视图**以显示在页面上。</span><span class="sxs-lookup"><span data-stu-id="ec411-137">Hover on the returned result, open the contextual menu \(right-click\), and choose **Reveal in Elements Panel** to find it in the DOM or **Scroll in to View** to show it on the page.</span></span>  

<span data-ttu-id="ec411-138">在下图中，将返回对当前选定元素的引用，并显示 src 属性。</span><span class="sxs-lookup"><span data-stu-id="ec411-138">In the following figure, a reference to the currently selected element is returned and the src property is displayed.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$ ('img') .src" lightbox="../media/console-element-selector-image-source.msft.png":::
   <span data-ttu-id="ec411-140">图 6：</span><span class="sxs-lookup"><span data-stu-id="ec411-140">Figure 6:  The</span></span> `$('img').src`  
:::image-end:::  

<span data-ttu-id="ec411-141">此方法还支持第二个参数 startNode，该参数指定要搜索元素的"元素"或 Node。</span><span class="sxs-lookup"><span data-stu-id="ec411-141">This method also supports a second parameter, startNode, that specifies an "element" or Node from which to search for elements.</span></span>  <span data-ttu-id="ec411-142">参数的默认值为 `document` 。</span><span class="sxs-lookup"><span data-stu-id="ec411-142">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="ec411-143">在下图中，找到后 `img` 的第一个元素 `title--image` ，并显示 `src` 正确返回。</span><span class="sxs-lookup"><span data-stu-id="ec411-143">In the following figure, the first `img` element is found after the `title--image` and displays the `src` properly is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$ ('img'， document.querySelector ('title--image') ) .src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   <span data-ttu-id="ec411-145">图 7：</span><span class="sxs-lookup"><span data-stu-id="ec411-145">Figure 7:  The</span></span> `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ec411-146">如果使用的库（如 jQuery）使用，则功能将被覆盖，并对应于该库中 `$` `$` 的实现。</span><span class="sxs-lookup"><span data-stu-id="ec411-146">If you are using a library such as jQuery that uses `$`, the functionality is overwritten, and `$` corresponds to the implementation from that library.</span></span>  

## <a name="query-selector-all"></a><span data-ttu-id="ec411-147">查询选择器全部</span><span class="sxs-lookup"><span data-stu-id="ec411-147">Query Selector All</span></span>  

```console
$$(selector, [startNode])
```  

<span data-ttu-id="ec411-148">返回与指定的 CSS 选择器匹配的元素数组。</span><span class="sxs-lookup"><span data-stu-id="ec411-148">Returns an array of elements that match the specified CSS selector.</span></span>  <span data-ttu-id="ec411-149">此方法等效于运行 [document.querySelectorAll () ][MDNDocumentQuerySelectorAll] 方法。</span><span class="sxs-lookup"><span data-stu-id="ec411-149">This method is equivalent to running the [document.querySelectorAll()][MDNDocumentQuerySelectorAll] method.</span></span>  

<span data-ttu-id="ec411-150">在下面的代码示例和图中，用于创建当前文档中所有元素的数组并显示每个元素 `$$()` `<img>` `src` 的属性值。</span><span class="sxs-lookup"><span data-stu-id="ec411-150">In the following code sample and figure, use `$$()` to create an array of all `<img>` elements in the current document and display the value of the `src` property for each element.</span></span>  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="使用 $$ () 选择文档中的所有图像并显示源" lightbox="../media/console-element-selector-image-all.msft.png":::
   <span data-ttu-id="ec411-152">图 8： `$$()` 用于选择文档中的所有图像并显示源</span><span class="sxs-lookup"><span data-stu-id="ec411-152">Figure 8:  Using `$$()` to select all images in the document and display the sources</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-153">此方法还支持第二个参数 startNode，该参数指定用于搜索元素的元素或 Node。</span><span class="sxs-lookup"><span data-stu-id="ec411-153">This method also supports a second parameter, startNode, that specifies an element or Node from which to search for elements.</span></span>  <span data-ttu-id="ec411-154">参数的默认值为 `document` 。</span><span class="sxs-lookup"><span data-stu-id="ec411-154">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="ec411-155">在下面的代码示例和图中，上一个代码示例和图的修改版本用于创建一个数组，该数组包含当前文档中选定节点之后 `$$()` `<img>` 的所有元素。</span><span class="sxs-lookup"><span data-stu-id="ec411-155">In the following code sample and figure, a modified version of the previous code sample and figure uses `$$()` to create an array of all `<img>` elements that appear in the current document after the selected Node.</span></span>  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="使用 $$ () 选择文档中指定 <div> 元素之后显示的所有图像并显示源" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   <span data-ttu-id="ec411-157">图 9：用于选择文档中指定元素之后显示的所有图像 `$$()` `<div>` 并显示源</span><span class="sxs-lookup"><span data-stu-id="ec411-157">Figure 9:  Using `$$()` to select all images that appear after the specified `<div>` element in the document and display the sources</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ec411-158">在 `Shift` + `Enter` 控制台中选择以在不运行脚本的情况下启动新行。</span><span class="sxs-lookup"><span data-stu-id="ec411-158">Select `Shift`+`Enter` in the console to start a new line without running the script.</span></span>  

## <a name="xpath"></a><span data-ttu-id="ec411-159">XPath</span><span class="sxs-lookup"><span data-stu-id="ec411-159">XPath</span></span>  

```console
$x(path, [startNode])
```  

<span data-ttu-id="ec411-160">返回与指定的 XPath 表达式匹配的 DOM 元素数组。</span><span class="sxs-lookup"><span data-stu-id="ec411-160">Returns an array of DOM elements that match the specified XPath expression.</span></span>  

<span data-ttu-id="ec411-161">在下面的代码示例和图中，将返回页面上 `<p>` 的所有元素。</span><span class="sxs-lookup"><span data-stu-id="ec411-161">In the following code sample and figure, all of the `<p>` elements on the page are returned.</span></span>  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="使用 XPath 选择器" lightbox="../media/console-array-xpath.msft.png":::
   <span data-ttu-id="ec411-163">图 10：使用 XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="ec411-163">Figure 10:  Using an XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-164">在下面的代码示例和图中，将返回包含 `<p>` 元素 `<a>` 的所有元素。</span><span class="sxs-lookup"><span data-stu-id="ec411-164">In the following code sample and figure, all of the `<p>` elements that contain `<a>` elements are returned.</span></span>  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="使用更复杂的 XPath 选择器" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   <span data-ttu-id="ec411-166">图 11：使用更复杂的 XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="ec411-166">Figure 11:  Using a more complicated XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-167">与其他选择器命令类似，具有可选的第二个参数，用于指定要搜索元素的元素或 `$x(path)` `startNode` Node。</span><span class="sxs-lookup"><span data-stu-id="ec411-167">Similar to the other selector commands, `$x(path)` has an optional second parameter, `startNode`, that specifies an element or Node from which to search for elements.</span></span>  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="将 XPath 选择器与 startNode 一同使用" lightbox="../media/console-array-xpath-startnode.msft.png":::
   <span data-ttu-id="ec411-169">图 12：将 XPath 选择器与</span><span class="sxs-lookup"><span data-stu-id="ec411-169">Figure 12:  Using an XPath selector with</span></span> `startNode`  
:::image-end:::  

## <a name="clear"></a><span data-ttu-id="ec411-170">clear</span><span class="sxs-lookup"><span data-stu-id="ec411-170">clear</span></span>  

```console
clear()
```  

<span data-ttu-id="ec411-171">清除历史记录的控制台。</span><span class="sxs-lookup"><span data-stu-id="ec411-171">Clears the console of the history.</span></span>  

```console
clear()
```  

## <a name="copy"></a><span data-ttu-id="ec411-172">copy</span><span class="sxs-lookup"><span data-stu-id="ec411-172">copy</span></span>  

```console
copy(object)
```  

<span data-ttu-id="ec411-173">该方法 `copy(object)` 将指定对象的字符串表示形式复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="ec411-173">The `copy(object)` method copies a string representation of the specified object to the clipboard.</span></span>  

```console
copy($0)
```  

## <a name="debug"></a><span data-ttu-id="ec411-174">调试</span><span class="sxs-lookup"><span data-stu-id="ec411-174">debug</span></span>  

```console
debug(method)
```  

>[!NOTE]
> <span data-ttu-id="ec411-175">[Chromium 问题#1050237][MonorailIssue1050237]跟踪函数的 `debug()` Bug。</span><span class="sxs-lookup"><span data-stu-id="ec411-175">The [Chromium issue #1050237][MonorailIssue1050237] is tracking a bug with the `debug()` function.</span></span>  <span data-ttu-id="ec411-176">如果遇到问题，请尝试 [改为使用][DevtoolsJavascriptBreakpoints] 断点。</span><span class="sxs-lookup"><span data-stu-id="ec411-176">If you encounter the issue, try [using breakpoints][DevtoolsJavascriptBreakpoints] instead.</span></span>  

<span data-ttu-id="ec411-177">请求指定方法时，将调用调试程序，并中断 **源** 工具上的方法，从而允许您逐步执行代码并调试它。</span><span class="sxs-lookup"><span data-stu-id="ec411-177">When you request the specified method, the debugger is invoked and breaks inside the method on the **Sources** tool allowing you to step through the code and debug it.</span></span>  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="使用调试工具在方法 () " lightbox="../media/console-debug-text.msft.png":::
   <span data-ttu-id="ec411-179">图 13：使用</span><span class="sxs-lookup"><span data-stu-id="ec411-179">Figure 13:  Breaking inside a method with</span></span> `debug()`  
:::image-end:::  

<span data-ttu-id="ec411-180">用于 `undebug(method)` 停止在方法上中断，或使用 UI 禁用所有断点。</span><span class="sxs-lookup"><span data-stu-id="ec411-180">Use `undebug(method)` to stop breaking on the method, or use the UI to disable all breakpoints.</span></span>  

<span data-ttu-id="ec411-181">有关断点详细信息，请导航到"使用断[点暂停代码"。][DevToolsJavascriptBreakpoints]</span><span class="sxs-lookup"><span data-stu-id="ec411-181">For more information on breakpoints, navigate to [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

## <a name="dir"></a><span data-ttu-id="ec411-182">dir</span><span class="sxs-lookup"><span data-stu-id="ec411-182">dir</span></span>  

```console
dir(object)
```  

<span data-ttu-id="ec411-183">显示指定对象的所有属性的对象样式列表。</span><span class="sxs-lookup"><span data-stu-id="ec411-183">Displays an object-style listing of all of the properties for the specified object.</span></span>  <span data-ttu-id="ec411-184">此方法是 [console.dir ][MDNConsoleDir] () 别名。</span><span class="sxs-lookup"><span data-stu-id="ec411-184">This method is an alias for the [console.dir()][MDNConsoleDir] method.</span></span>  

<span data-ttu-id="ec411-185">在 `document.head` 控制台中计算以显示与标记之间的 `<head>` `</head>` HTML。</span><span class="sxs-lookup"><span data-stu-id="ec411-185">Evaluate `document.head` in the Console to display the HTML between the `<head>` and `</head>` tags.</span></span>  <span data-ttu-id="ec411-186">在下面的代码示例和图中，在控制台中使用后将显示对象 `console.dir()` 样式列表。</span><span class="sxs-lookup"><span data-stu-id="ec411-186">In the following code sample and figure, an object-style listing is displayed after using `console.dir()` in the Console.</span></span>  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="使用 dir () 记录 document.head" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   <span data-ttu-id="ec411-188">图 14：使用 `document.head` 方法 `dir()` 日志记录</span><span class="sxs-lookup"><span data-stu-id="ec411-188">Figure 14:  Logging `document.head` with `dir()` method</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-189">有关详细信息，请导航到 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 控制台 API 中的条目。</span><span class="sxs-lookup"><span data-stu-id="ec411-189">For more information, navigate to [`console.dir()`][DevToolsConsoleApiConsoleDirObject] entry in the Console API.</span></span>  

## <a name="dirxml"></a><span data-ttu-id="ec411-190">dirxml</span><span class="sxs-lookup"><span data-stu-id="ec411-190">dirxml</span></span>  

```console
dirxml(object)
```  

<span data-ttu-id="ec411-191">打印指定对象的 XML 表示形式，如 **元素** 工具中显示。</span><span class="sxs-lookup"><span data-stu-id="ec411-191">Prints an XML representation of the specified object, as displayed in the **Elements** tool.</span></span>  <span data-ttu-id="ec411-192">此方法等效于 [console.dirxml () ][MDNConsoleDirxml] 方法。</span><span class="sxs-lookup"><span data-stu-id="ec411-192">This method is equivalent to the [console.dirxml()][MDNConsoleDirxml] method.</span></span>  

## <a name="inspect"></a><span data-ttu-id="ec411-193">inspect</span><span class="sxs-lookup"><span data-stu-id="ec411-193">inspect</span></span>  

```console
inspect(object/method)
```  

<span data-ttu-id="ec411-194">在相应的面板中打开并选择指定的元素或对象：DOM 元素的元素\*\*\*\* 工具或 JavaScript 堆对象的\*\*\*\* Memory 工具。</span><span class="sxs-lookup"><span data-stu-id="ec411-194">Opens and selects the specified element or object in the appropriate panel:  either the **Elements** tool for DOM elements or the **Memory** tool for JavaScript heap objects.</span></span>  

<span data-ttu-id="ec411-195">在下面的代码示例和图中，将在 `document.body` Elements 工具 **中** 打开。</span><span class="sxs-lookup"><span data-stu-id="ec411-195">In the following code sample and figure, the `document.body` opens in the **Elements** tool.</span></span>  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="使用检查属性检查 () " lightbox="../media/console-inspect-document-body.msft.png":::
   <span data-ttu-id="ec411-197">图 15：使用</span><span class="sxs-lookup"><span data-stu-id="ec411-197">Figure 15:  Inspecting an element with</span></span> `inspect()`  
:::image-end:::  

<span data-ttu-id="ec411-198">传递要检查的方法时，该方法将在 **源** 工具中打开文档供您检查。</span><span class="sxs-lookup"><span data-stu-id="ec411-198">When passing a method to inspect, the method opens the document in the **Sources** tool for you to inspect.</span></span>  

## <a name="geteventlisteners"></a><span data-ttu-id="ec411-199">getEventListeners</span><span class="sxs-lookup"><span data-stu-id="ec411-199">getEventListeners</span></span>  

```console
getEventListeners(object)
```  

<span data-ttu-id="ec411-200">返回指定对象上注册的事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec411-200">Returns the event listeners registered on the specified object.</span></span>  <span data-ttu-id="ec411-201">返回值是包含每个已注册事件类型 \ (如 `click` `keydown` 或 \) 的数组的对象。</span><span class="sxs-lookup"><span data-stu-id="ec411-201">The return value is an object that contains an array for each registered event type \(such as `click` or `keydown`\).</span></span>  <span data-ttu-id="ec411-202">每个数组的成员都是描述为每种类型注册的侦听器的对象。</span><span class="sxs-lookup"><span data-stu-id="ec411-202">The members of each array are objects that describe the listener registered for each type.</span></span>  <span data-ttu-id="ec411-203">下面的代码示例图列出了在文档对象上注册的所有事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec411-203">In the following code sample figure, all of the event listeners registered on the document object are listed.</span></span>  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="使用 getEventListeners 文档 (输出) " lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   <span data-ttu-id="ec411-205">图 16：使用的结果</span><span class="sxs-lookup"><span data-stu-id="ec411-205">Figure 16:  The result of using</span></span> `getEventListeners(document)`  
:::image-end:::  

<span data-ttu-id="ec411-206">如果指定对象上注册了多个侦听器，则数组包含每个侦听器的成员。</span><span class="sxs-lookup"><span data-stu-id="ec411-206">If more than one listener is registered on the specified object, then the array contains a member for each listener.</span></span>  <span data-ttu-id="ec411-207">下图中为事件在文档元素上注册了两个 `click` 事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec411-207">In the following figure, there are two event listeners registered on the document element for the `click` event.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="多个侦听器" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   <span data-ttu-id="ec411-209">图 17：多个侦听器</span><span class="sxs-lookup"><span data-stu-id="ec411-209">Figure 17:  Multiple listeners</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-210">您可以进一步展开以下每个对象以浏览属性。</span><span class="sxs-lookup"><span data-stu-id="ec411-210">You may further expand each of the following objects to explore the properties.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="侦听器对象的扩展视图" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   <span data-ttu-id="ec411-212">图 18：侦听器对象的扩展视图</span><span class="sxs-lookup"><span data-stu-id="ec411-212">Figure 18:  Expanded view of listener object</span></span>  
:::image-end:::  

## <a name="keys"></a><span data-ttu-id="ec411-213">键</span><span class="sxs-lookup"><span data-stu-id="ec411-213">keys</span></span>  

```console
keys(object)
```  

<span data-ttu-id="ec411-214">返回一个数组，其中包含属于指定对象的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ec411-214">Returns an array containing the names of the properties belonging to the specified object.</span></span>  <span data-ttu-id="ec411-215">若要获取相同属性的关联值，请使用 `values()` 。</span><span class="sxs-lookup"><span data-stu-id="ec411-215">To get the associated values of the same properties, use `values()`.</span></span>  

<span data-ttu-id="ec411-216">例如，假设应用程序定义了以下对象。</span><span class="sxs-lookup"><span data-stu-id="ec411-216">For example, suppose your application defined the following object.</span></span>  

```console
var player1 =   
```  

<span data-ttu-id="ec411-217">在下面的代码示例和图中，为了简单起见，在键入之前和在控制台中) 在全局命名空间 \ (中定义 `player1` `keys(player1)` `values(player1)` 结果。</span><span class="sxs-lookup"><span data-stu-id="ec411-217">In the following code samples and figure, the result assumes `player1` was defined in the global namespace \(for simplicity\) prior to typing `keys(player1)` and `values(player1)` in the console.</span></span>  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="键 () 和值 () 命令" lightbox="../media/console-keys-values.msft.png":::
   <span data-ttu-id="ec411-219">图 19：And `keys()` `values()` 命令</span><span class="sxs-lookup"><span data-stu-id="ec411-219">Figure 19:  The `keys()` and `values()` commands</span></span>  
:::image-end:::  

## <a name="monitor"></a><span data-ttu-id="ec411-220">监视器</span><span class="sxs-lookup"><span data-stu-id="ec411-220">monitor</span></span>  

```console
monitor(method)
```  

<span data-ttu-id="ec411-221">向控制台记录一条消息，指示方法名称以及调用该方法时传递给该方法的参数。</span><span class="sxs-lookup"><span data-stu-id="ec411-221">Logs a message to the console that indicates the method name along with the arguments that are passed to the method when it was called.</span></span>  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="监视器 () 方法" lightbox="../media/console-function-monitor-sum.msft.png":::
   <span data-ttu-id="ec411-223">图 20： `monitor()` 方法</span><span class="sxs-lookup"><span data-stu-id="ec411-223">Figure 20:  The `monitor()` method</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-224">用于 `unmonitor(method)` 停止监视。</span><span class="sxs-lookup"><span data-stu-id="ec411-224">Use `unmonitor(method)` to cease monitoring.</span></span>  

## <a name="monitorevents"></a><span data-ttu-id="ec411-225">monitorEvents</span><span class="sxs-lookup"><span data-stu-id="ec411-225">monitorEvents</span></span>  

```console
monitorEvents(object[, events])
```  

<span data-ttu-id="ec411-226">当指定对象上发生指定事件之一时，该事件对象将记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="ec411-226">When one of the specified events occurs on the specified object, the event object is logged to the console.</span></span>  <span data-ttu-id="ec411-227">可以指定要监视的单个事件、事件数组或映射到预定义的事件集合的泛型事件类型之一。</span><span class="sxs-lookup"><span data-stu-id="ec411-227">You may specify a single event to monitor, an array of events, or one of the generic events types that are mapped to a predefined collection of events.</span></span>  <span data-ttu-id="ec411-228">查看以下代码示例和图。</span><span class="sxs-lookup"><span data-stu-id="ec411-228">Review the following code sample and figure.</span></span>  

<span data-ttu-id="ec411-229">下面监视窗口对象上的所有调整大小事件。</span><span class="sxs-lookup"><span data-stu-id="ec411-229">The following monitors all resize events on the window object.</span></span>  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="监视窗口大小事件" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   <span data-ttu-id="ec411-231">图 21：监视窗口大小调整事件</span><span class="sxs-lookup"><span data-stu-id="ec411-231">Figure 21:  Monitoring window resize events</span></span>  
:::image-end:::  

<span data-ttu-id="ec411-232">下面定义了一个数组，用于监视窗口对象上的两 `resize` `scroll` 者以及事件。</span><span class="sxs-lookup"><span data-stu-id="ec411-232">The following defines an array to monitor both `resize` and `scroll` events on the window object.</span></span>  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

<span data-ttu-id="ec411-233">还可以指定一种可用的事件类型，即映射到预定义的事件集的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec411-233">You may also specify one of the available types of events, strings that map to predefined sets of events.</span></span>  <span data-ttu-id="ec411-234">下表显示可用的事件类型和关联的事件映射。</span><span class="sxs-lookup"><span data-stu-id="ec411-234">The following table displays the available event types and the associated event mappings.</span></span>  

| <span data-ttu-id="ec411-235">事件类型</span><span class="sxs-lookup"><span data-stu-id="ec411-235">Event type</span></span> | <span data-ttu-id="ec411-236">相应的映射事件</span><span class="sxs-lookup"><span data-stu-id="ec411-236">Corresponding mapped events</span></span> |  
|:--- |:--- |  
| `mouse` | <span data-ttu-id="ec411-237">"click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mouseover"、"mouseup"、"mousewheel"</span><span class="sxs-lookup"><span data-stu-id="ec411-237">"click", "dblclick", "mousedown", "mousemove", "mouseout", "mouseover", "mouseup", "mousewheel"</span></span> |  
| `key` | <span data-ttu-id="ec411-238">"keydown"、"keypress"、"keyup"、"textInput"</span><span class="sxs-lookup"><span data-stu-id="ec411-238">"keydown", "keypress", "keyup", "textInput"</span></span> |  
| `touch` | <span data-ttu-id="ec411-239">"touchcancel"、"touchend"、"touchmove"、"touchstart"</span><span class="sxs-lookup"><span data-stu-id="ec411-239">"touchcancel", "touchend", "touchmove", "touchstart"</span></span> |  
| `control` | <span data-ttu-id="ec411-240">"blur"、"change"、"focus"、"reset"、"resize"、"scroll"、"select"、"submit"、"zoom"</span><span class="sxs-lookup"><span data-stu-id="ec411-240">"blur", "change", "focus", "reset", "resize", "scroll", "select", "submit", "zoom"</span></span> |  

<span data-ttu-id="ec411-241">在下面的代码示例中，当前在 Elements 工具中选择了与输入文本字段上的事件 `key` `key` 对应的事件类型。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ec411-241">In the following code sample, the `key` event type corresponding to `key` events on an input text field are currently selected in the **Elements** tool.</span></span>  

```console
monitorEvents($0, "key");
```  

<span data-ttu-id="ec411-242">下图显示了在文本字段中键入字符后的示例输出。</span><span class="sxs-lookup"><span data-stu-id="ec411-242">In the following figure the sample output after typing a character in the text field is displayed.</span></span>  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="监视关键事件" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   <span data-ttu-id="ec411-244">图 22：监视关键事件</span><span class="sxs-lookup"><span data-stu-id="ec411-244">Figure 22:  Monitoring key events</span></span>  
:::image-end:::  

## <a name="profile"></a><span data-ttu-id="ec411-245">profile</span><span class="sxs-lookup"><span data-stu-id="ec411-245">profile</span></span>  

```console
profile([name])
```  

<span data-ttu-id="ec411-246">使用可选名称启动 JavaScript CPU 分析会话。</span><span class="sxs-lookup"><span data-stu-id="ec411-246">Starts a JavaScript CPU profiling session with an optional name.</span></span>  <span data-ttu-id="ec411-247">[profileEnd () ](#profileend)方法完成配置文件，并显示**内存工具中**的结果。</span><span class="sxs-lookup"><span data-stu-id="ec411-247">The [profileEnd()](#profileend) method completes the profile and displays the results in the **Memory** tool.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="ec411-248">运行 `profile()` 该方法以开始分析。</span><span class="sxs-lookup"><span data-stu-id="ec411-248">Run the `profile()` method to start profiling.</span></span>  
    
    ```console
    profile("My profile")
    ```  
    
1.  <span data-ttu-id="ec411-249">运行 [profileEnd () ](#profileend) 方法以停止分析，并显示 **内存工具中** 的结果。</span><span class="sxs-lookup"><span data-stu-id="ec411-249">Run the [profileEnd()](#profileend) method to stop profiling and display the results in the **Memory** tool.</span></span>  

<span data-ttu-id="ec411-250">配置文件也可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="ec411-250">Profiles may also be nested.</span></span>  <span data-ttu-id="ec411-251">在下面的代码示例和图中，无论顺序如何，结果都是相同的。</span><span class="sxs-lookup"><span data-stu-id="ec411-251">In the following code samples and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> <span data-ttu-id="ec411-252">多个 CPU 配置文件可以同时运行，并且不需要按创建顺序关闭每个配置文件。</span><span class="sxs-lookup"><span data-stu-id="ec411-252">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <a name="profileend"></a><span data-ttu-id="ec411-253">profileEnd</span><span class="sxs-lookup"><span data-stu-id="ec411-253">profileEnd</span></span>  

```console
profileEnd([name])
```  

<span data-ttu-id="ec411-254">完成 JavaScript CPU 分析会话，并显示 **内存工具中** 的结果。</span><span class="sxs-lookup"><span data-stu-id="ec411-254">Completes a JavaScript CPU profiling session and displays the results in the **Memory** tool.</span></span>  <span data-ttu-id="ec411-255">您必须运行 [配置文件 () 方法 ](#profile) 。</span><span class="sxs-lookup"><span data-stu-id="ec411-255">You must be running the [profile()](#profile) method.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="ec411-256">运行 [配置文件 () ](#profile) 方法开始分析。</span><span class="sxs-lookup"><span data-stu-id="ec411-256">Run the [profile()](#profile) method to start profiling.</span></span>  
1.  <span data-ttu-id="ec411-257">运行 `profileEnd()` 该方法以停止分析，在"内存"工具 **中显示** 结果。</span><span class="sxs-lookup"><span data-stu-id="ec411-257">Run the `profileEnd()` method to stop profiling and display the results in the **Memory** tool.</span></span>  
    
    ```console
    profileEnd("My profile")
    ```  

<span data-ttu-id="ec411-258">配置文件也可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="ec411-258">Profiles may also be nested.</span></span>  <span data-ttu-id="ec411-259">在下面的代码示例中，无论顺序如何，结果都是相同的。</span><span class="sxs-lookup"><span data-stu-id="ec411-259">In the following code sample and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

<span data-ttu-id="ec411-260">结果在内存工具中显示为堆 **快照** 。</span><span class="sxs-lookup"><span data-stu-id="ec411-260">The result appears as a Heap Snapshot in the **Memory** tool.</span></span>  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="分组配置文件" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   <span data-ttu-id="ec411-262">图 23：分组配置文件</span><span class="sxs-lookup"><span data-stu-id="ec411-262">Figure 23:  Grouped profiles</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ec411-263">多个 CPU 配置文件可以同时运行，并且不需要按创建顺序关闭每个配置文件。</span><span class="sxs-lookup"><span data-stu-id="ec411-263">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <a name="queryobjects"></a><span data-ttu-id="ec411-264">queryObjects</span><span class="sxs-lookup"><span data-stu-id="ec411-264">queryObjects</span></span>  

```console
queryObjects(Constructor)
```  

<span data-ttu-id="ec411-265">返回使用指定构造函数创建的对象数组。</span><span class="sxs-lookup"><span data-stu-id="ec411-265">Return an array of objects created with the specified constructor.</span></span>  <span data-ttu-id="ec411-266">范围 `queryObjects()` 是控制台中当前选择的运行时上下文。</span><span class="sxs-lookup"><span data-stu-id="ec411-266">The scope of `queryObjects()` is the currently-selected runtime context in the console.</span></span>

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      <span data-ttu-id="ec411-267">返回所有 `Promises` 。</span><span class="sxs-lookup"><span data-stu-id="ec411-267">Returns all `Promises`.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      <span data-ttu-id="ec411-268">返回所有 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="ec411-268">Returns all HTML elements.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      <span data-ttu-id="ec411-269">返回使用 实例化的所有对象 `new functionName()` 。</span><span class="sxs-lookup"><span data-stu-id="ec411-269">Returns all objects that were instantiated using `new functionName()`.</span></span>  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a><span data-ttu-id="ec411-270">table</span><span class="sxs-lookup"><span data-stu-id="ec411-270">table</span></span>  

```console
table(data[, columns])
```  

<span data-ttu-id="ec411-271">使用基于数据对象的表格格式记录对象数据，并添加可选列标题。</span><span class="sxs-lookup"><span data-stu-id="ec411-271">Logs object data with table formatting based upon the data object in with optional column headings.</span></span>  <span data-ttu-id="ec411-272">在下面的代码示例和图中，将显示使用控制台中的表的名称列表。</span><span class="sxs-lookup"><span data-stu-id="ec411-272">In the following code sample and figure, a list of names using a table in the console is displayed.</span></span>  

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
   <span data-ttu-id="ec411-274">图 24：方法 `table()` 的结果</span><span class="sxs-lookup"><span data-stu-id="ec411-274">Figure 24:  The result of the `table()` method</span></span>  
:::image-end:::  

## <a name="undebug"></a><span data-ttu-id="ec411-275">undebug</span><span class="sxs-lookup"><span data-stu-id="ec411-275">undebug</span></span>  

```console
undebug(method)
```  

<span data-ttu-id="ec411-276">停止对指定方法的调试，以便调用该方法时，将不再调用调试器。</span><span class="sxs-lookup"><span data-stu-id="ec411-276">Stops the debugging of the specified method so that when the method is called, the debugger is no longer invoked.</span></span>  

```console
undebug(getData);
```  

## <a name="unmonitor"></a><span data-ttu-id="ec411-277">unmonitor</span><span class="sxs-lookup"><span data-stu-id="ec411-277">unmonitor</span></span>  

```console
unmonitor(method)
```  

<span data-ttu-id="ec411-278">停止对指定方法的监视。</span><span class="sxs-lookup"><span data-stu-id="ec411-278">Stops the monitoring of the specified method.</span></span>  <span data-ttu-id="ec411-279">此方法与监视器或 [ () 一起 ](#monitor) 使用。</span><span class="sxs-lookup"><span data-stu-id="ec411-279">This method is used in concert with the [monitor()](#monitor) method.</span></span>  

```console
unmonitor(getData);
```  

## <a name="unmonitorevents"></a><span data-ttu-id="ec411-280">unmonitorEvents</span><span class="sxs-lookup"><span data-stu-id="ec411-280">unmonitorEvents</span></span>  

```console
unmonitorEvents(object[, events])
```  

<span data-ttu-id="ec411-281">停止监视指定对象和事件的事件。</span><span class="sxs-lookup"><span data-stu-id="ec411-281">Stops monitoring events for the specified object and events.</span></span>  <span data-ttu-id="ec411-282">例如，以下操作将停止窗口对象上的所有事件监视。</span><span class="sxs-lookup"><span data-stu-id="ec411-282">For example, the following stops all event monitoring on the window object.</span></span>  

```console
unmonitorEvents(window);
```  

<span data-ttu-id="ec411-283">还可以有选择地停止监视对象上的特定事件。</span><span class="sxs-lookup"><span data-stu-id="ec411-283">You may also selectively stop monitoring specific events on an object.</span></span>  <span data-ttu-id="ec411-284">例如，以下代码开始监视当前选定元素上的所有事件，然后停止 `mouse` `mousemove` 监视事件 \ (可能以减少控制台输出\) 。</span><span class="sxs-lookup"><span data-stu-id="ec411-284">For example, the following code starts monitoring all `mouse` events on the currently selected element, and then stops monitoring `mousemove` events \(perhaps to reduce noise in the console output\).</span></span>  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## <a name="values"></a><span data-ttu-id="ec411-285">值</span><span class="sxs-lookup"><span data-stu-id="ec411-285">values</span></span>  

```console
values(object)
```  

<span data-ttu-id="ec411-286">返回一个数组，其中包含属于指定对象的所有属性的值。</span><span class="sxs-lookup"><span data-stu-id="ec411-286">Returns an array containing the values of all properties belonging to the specified object.</span></span>  

```console
values(object);
```  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ec411-287">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="ec411-287">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="ec411-297">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ec411-297">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ec411-298">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/utilities)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ec411-298">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/utilities) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ec411-300">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ec411-300">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
