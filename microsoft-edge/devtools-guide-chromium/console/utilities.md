---
title: 控制台实用工具 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: efa03e02813d718514f73445bc0dceb3a1a83f39
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708778"
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

# <span data-ttu-id="56136-103">控制台实用工具 API 参考</span><span class="sxs-lookup"><span data-stu-id="56136-103">Console Utilities API Reference</span></span>  

<span data-ttu-id="56136-104">控制台实用工具 API 包含一组用于执行常见任务的便捷命令：选择和检查 DOM 元素，以可读格式显示数据、停止和启动探查器以及监视 DOM 事件。</span><span class="sxs-lookup"><span data-stu-id="56136-104">The Console Utilities API contains a collection of convenience commands for performing common tasks:  selecting and inspecting DOM elements, displaying data in readable format, stopping and starting the profiler, and monitoring DOM events.</span></span>  

> [!WARNING]
> <span data-ttu-id="56136-105">以下命令仅适用于 Microsoft Edge DevTools 控制台。</span><span class="sxs-lookup"><span data-stu-id="56136-105">The following commands only work in the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="56136-106">如果从脚本运行，则命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="56136-106">The commands do not work if run from your scripts.</span></span>  

<span data-ttu-id="56136-107">要查找 `console.log()` `console.error()` 和其余 `console.*` 方法？</span><span class="sxs-lookup"><span data-stu-id="56136-107">Looking for `console.log()`, `console.error()`, and the rest of the `console.*` methods?</span></span>  <span data-ttu-id="56136-108">请参阅[控制台 API 参考][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="56136-108">See [Console API Reference][DevToolsConsoleApi].</span></span>  

## <span data-ttu-id="56136-109">最近计算的表达式</span><span class="sxs-lookup"><span data-stu-id="56136-109">Recently Evaluated Expression</span></span>  

```console
$_
```  

<span data-ttu-id="56136-110">返回最近计算的表达式的值。</span><span class="sxs-lookup"><span data-stu-id="56136-110">Returns the value of the most recently evaluated expression.</span></span>  

<span data-ttu-id="56136-111">在下图中，计算一个简单的表达式 \ （ `2 + 2` \）。</span><span class="sxs-lookup"><span data-stu-id="56136-111">In the following figure, a simple expression \(`2 + 2`\) is evaluated.</span></span>  <span data-ttu-id="56136-112">`$_`然后计算属性，其中包含相同的值。</span><span class="sxs-lookup"><span data-stu-id="56136-112">The `$_` property is then evaluated, which contains the same value.</span></span>  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$ _ 是最近计算的表达式" lightbox="../media/console-arithmatic.msft.png":::
   <span data-ttu-id="56136-114">图1： `$_` 是最近计算的表达式</span><span class="sxs-lookup"><span data-stu-id="56136-114">Figure 1:  `$_` is the most recently evaluated expression</span></span>  
:::image-end:::  

<span data-ttu-id="56136-115">在下图中，计算的表达式最初包含一个名称数组。</span><span class="sxs-lookup"><span data-stu-id="56136-115">In the following figure, the evaluated expression initially contains an array of names.</span></span>  <span data-ttu-id="56136-116">计算 `$_.length` 以查找数组的长度，更改中存储的值 `$_` 成为最新计算的表达式 `4` 。</span><span class="sxs-lookup"><span data-stu-id="56136-116">Evaluating `$_.length` to find the length of the array, the value stored in `$_` changes to become the latest evaluated expression, `4`.</span></span>  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="评估新命令时 $ _ 更改" lightbox="../media/console-array-length.msft.png":::
   <span data-ttu-id="56136-118">图2： `$_` 评估新命令时的更改</span><span class="sxs-lookup"><span data-stu-id="56136-118">Figure 2:  `$_` changes when new commands are evaluated</span></span>  
:::image-end:::  

## <span data-ttu-id="56136-119">最近选择的元素或 JavaScript 对象</span><span class="sxs-lookup"><span data-stu-id="56136-119">Recently Selected Element Or JavaScript Object</span></span>  

```console
$0
```  

<span data-ttu-id="56136-120">返回最近选择的元素或 JavaScript 对象。</span><span class="sxs-lookup"><span data-stu-id="56136-120">Returns the most recently selected element or JavaScript object.</span></span>  `$1` <span data-ttu-id="56136-121">返回最近选择的第二个项，依此类推。</span><span class="sxs-lookup"><span data-stu-id="56136-121">returns the second most recently selected one, and so on.</span></span>  <span data-ttu-id="56136-122">`$0`、、 `$1` `$2` 、 `$3` 和 `$4` 命令可用作对在 "**元素**" 面板中检查过的最后五个 DOM 元素或在 "**内存**" 面板中选择的最后五个 JavaScript 堆对象的历史参考。</span><span class="sxs-lookup"><span data-stu-id="56136-122">The `$0`, `$1`, `$2`, `$3`, and `$4` commands work as a historical reference to the last five DOM elements inspected within the **Elements** panel or the last five JavaScript heap objects selected in the **Memory** panel.</span></span>  

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

<span data-ttu-id="56136-123">下图中，在 `img` "**元素**" 面板中选择了一个元素。</span><span class="sxs-lookup"><span data-stu-id="56136-123">In the following figure, an `img` element is selected in the **Elements** panel.</span></span>  <span data-ttu-id="56136-124">在该**控制台**抽屉中，已 `$0` 评估并显示相同的元素。</span><span class="sxs-lookup"><span data-stu-id="56136-124">In the **Console** drawer, `$0` has been evaluated and displays the same element.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   <span data-ttu-id="56136-126">图3：</span><span class="sxs-lookup"><span data-stu-id="56136-126">Figure 3:  The</span></span> `$0`  
:::image-end:::  

<span data-ttu-id="56136-127">在下图中，图像显示在同一页面中选择的不同元素。</span><span class="sxs-lookup"><span data-stu-id="56136-127">In the following figure, the image shows a different element selected in the same page.</span></span>  <span data-ttu-id="56136-128">" `$0` 当前" 指的是新选定的元素，同时 `$1` 返回以前选择的元素。</span><span class="sxs-lookup"><span data-stu-id="56136-128">The `$0` now refers to the newly selected element, while `$1` returns the previously selected one.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   <span data-ttu-id="56136-130">图4：</span><span class="sxs-lookup"><span data-stu-id="56136-130">Figure 4:  The</span></span> `$1`  
:::image-end:::  

## <span data-ttu-id="56136-131">查询选择器</span><span class="sxs-lookup"><span data-stu-id="56136-131">Query Selector</span></span>  

```console
$(selector, [startNode])
```  

<span data-ttu-id="56136-132">返回具有指定 CSS 选择器的第一个 DOM 元素的引用。</span><span class="sxs-lookup"><span data-stu-id="56136-132">Returns the reference to the first DOM element with the specified CSS selector.</span></span>  <span data-ttu-id="56136-133">此方法是[querySelector （）][MDNDocumentQuerySelector]方法的别名。</span><span class="sxs-lookup"><span data-stu-id="56136-133">This method is an alias for the [document.querySelector()][MDNDocumentQuerySelector] method.</span></span>  

<span data-ttu-id="56136-134">在下图中，返回对文档中第一个元素的引用 `<img>` 。</span><span class="sxs-lookup"><span data-stu-id="56136-134">In the following figure, a reference to the first `<img>` element in the document is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$ （' Img '）" lightbox="../media/console-element-selector-image.msft.png":::
   <span data-ttu-id="56136-136">图5：</span><span class="sxs-lookup"><span data-stu-id="56136-136">Figure 5:  The</span></span> `$('img')`  
:::image-end:::  

<span data-ttu-id="56136-137">将鼠标悬停在返回的结果上，打开上下文菜单 \ （右键单击 \），然后在 "**元素" 面板中选择 "显示"** 以在 DOM 中查找它，或通过**滚动查看**以在页面上显示它。</span><span class="sxs-lookup"><span data-stu-id="56136-137">Hover on the returned result, open the contextual menu \(right-click\), and select **Reveal in Elements Panel** to find it in the DOM or **Scroll in to View** to show it on the page.</span></span>  

<span data-ttu-id="56136-138">在下图中，返回对当前所选元素的引用，并显示 src 属性。</span><span class="sxs-lookup"><span data-stu-id="56136-138">In the following figure, a reference to the currently selected element is returned and the src property is displayed.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$ （"Img"） src" lightbox="../media/console-element-selector-image-source.msft.png":::
   <span data-ttu-id="56136-140">图6：</span><span class="sxs-lookup"><span data-stu-id="56136-140">Figure 6:  The</span></span> `$('img').src`  
:::image-end:::  

<span data-ttu-id="56136-141">此方法还支持第二个参数 startNode，该参数指定要从中搜索元素的 "element" 或节点。</span><span class="sxs-lookup"><span data-stu-id="56136-141">This method also supports a second parameter, startNode, that specifies an "element" or Node from which to search for elements.</span></span>  <span data-ttu-id="56136-142">参数的默认值为 `document` 。</span><span class="sxs-lookup"><span data-stu-id="56136-142">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="56136-143">下图中，在 `img` `title--image` 返回并显示正确的后，将找到第一个元素 `src` 。</span><span class="sxs-lookup"><span data-stu-id="56136-143">In the following figure, the first `img` element is found after the `title--image` and displays the `src` properly is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$ （"Img"、querySelector （"title-image"））。 src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   <span data-ttu-id="56136-145">图7：</span><span class="sxs-lookup"><span data-stu-id="56136-145">Figure 7:  The</span></span> `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="56136-146">如果你使用的库（如 jQuery）使用，则将 `$` 覆盖该功能，并将其 `$` 与该库中的实现对应。</span><span class="sxs-lookup"><span data-stu-id="56136-146">If you are using a library such as jQuery that uses `$`, the functionality is overwritten, and `$` corresponds to the implementation from that library.</span></span>  

## <span data-ttu-id="56136-147">所有查询选择器</span><span class="sxs-lookup"><span data-stu-id="56136-147">Query Selector All</span></span>  

```console
$$(selector, [startNode])
```  

<span data-ttu-id="56136-148">返回与指定的 CSS 选择器匹配的元素数组。</span><span class="sxs-lookup"><span data-stu-id="56136-148">Returns an array of elements that match the specified CSS selector.</span></span>  <span data-ttu-id="56136-149">此方法等效于调用[querySelectorAll （）][MDNDocumentQuerySelectorAll]方法。</span><span class="sxs-lookup"><span data-stu-id="56136-149">This method is equivalent to calling the [document.querySelectorAll()][MDNDocumentQuerySelectorAll] method.</span></span>  

<span data-ttu-id="56136-150">在以下代码示例和图中，使用 `$$()` 创建 `<img>` 当前文档中所有元素的数组，并显示 `src` 每个元素的属性值。</span><span class="sxs-lookup"><span data-stu-id="56136-150">In the following code sample and figure, use `$$()` to create an array of all `<img>` elements in the current document and display the value of the `src` property for each element.</span></span>  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="使用 $ $ （）选择文档中的所有图像并显示源" lightbox="../media/console-element-selector-image-all.msft.png":::
   <span data-ttu-id="56136-152">图8：使用 `$$()` 以选择文档中的所有图像并显示源</span><span class="sxs-lookup"><span data-stu-id="56136-152">Figure 8:  Using `$$()` to select all images in the document and display the sources</span></span>  
:::image-end:::  

<span data-ttu-id="56136-153">此方法还支持第二个参数 startNode，用于指定要从中搜索元素的元素或节点。</span><span class="sxs-lookup"><span data-stu-id="56136-153">This method also supports a second parameter, startNode, that specifies an element or Node from which to search for elements.</span></span>  <span data-ttu-id="56136-154">参数的默认值为 `document` 。</span><span class="sxs-lookup"><span data-stu-id="56136-154">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="56136-155">在以下代码示例和图中，已修改版本的上一个代码示例和图用于 `$$()` 创建在 `<img>` 所选节点之后出现在当前文档中的所有元素的数组。</span><span class="sxs-lookup"><span data-stu-id="56136-155">In the following code sample and figure, a modified version of the previous code sample and figure uses `$$()` to create an array of all `<img>` elements that appear in the current document after the selected Node.</span></span>  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="使用 $ $ （）选择文档中指定的 <div> 元素之后出现的所有图像并显示源" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   <span data-ttu-id="56136-157">图9： `$$()` 选择在文档中的指定元素之后显示的所有图像 `<div>` 并显示源</span><span class="sxs-lookup"><span data-stu-id="56136-157">Figure 9:  Using `$$()` to select all images that appear after the specified `<div>` element in the document and display the sources</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="56136-158">`Shift` + `Enter` 在控制台中按键以开始新行，而不运行脚本。</span><span class="sxs-lookup"><span data-stu-id="56136-158">Press `Shift`+`Enter` in the console to start a new line without running the script.</span></span>  

## <span data-ttu-id="56136-159">XPath</span><span class="sxs-lookup"><span data-stu-id="56136-159">XPath</span></span>  

```console
$x(path, [startNode])
```  

<span data-ttu-id="56136-160">返回与指定 XPath 表达式匹配的 DOM 元素数组。</span><span class="sxs-lookup"><span data-stu-id="56136-160">Returns an array of DOM elements that match the specified XPath expression.</span></span>  

<span data-ttu-id="56136-161">在以下代码示例和图中， `<p>` 返回页面上的所有元素。</span><span class="sxs-lookup"><span data-stu-id="56136-161">In the following code sample and figure, all of the `<p>` elements on the page are returned.</span></span>  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="使用 XPath 选择器" lightbox="../media/console-array-xpath.msft.png":::
   <span data-ttu-id="56136-163">图10：使用 XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="56136-163">Figure 10:  Using an XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="56136-164">在以下代码示例和图中， `<p>` 返回包含元素的所有元素 `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="56136-164">In the following code sample and figure, all of the `<p>` elements that contain `<a>` elements are returned.</span></span>  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="使用更复杂的 XPath 选择器" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   <span data-ttu-id="56136-166">图11：使用更复杂的 XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="56136-166">Figure 11:  Using a more complicated XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="56136-167">与其他选择器命令相似， `$x(path)` 具有可选的第二个参数， `startNode` 用于指定要从中搜索元素的元素或节点。</span><span class="sxs-lookup"><span data-stu-id="56136-167">Similar to the other selector commands, `$x(path)` has an optional second parameter, `startNode`, that specifies an element or Node from which to search for elements.</span></span>  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="将 XPath 选择器与 startNode 结合使用" lightbox="../media/console-array-xpath-startnode.msft.png":::
   <span data-ttu-id="56136-169">图12：使用 XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="56136-169">Figure 12:  Using an XPath selector with</span></span> `startNode`  
:::image-end:::  

## <span data-ttu-id="56136-170">消除</span><span class="sxs-lookup"><span data-stu-id="56136-170">clear</span></span>  

```console
clear()
```  

<span data-ttu-id="56136-171">清除历史记录的控制台。</span><span class="sxs-lookup"><span data-stu-id="56136-171">Clears the console of the history.</span></span>  

```console
clear()
```  

## <span data-ttu-id="56136-172">copy</span><span class="sxs-lookup"><span data-stu-id="56136-172">copy</span></span>  

```console
copy(object)
```  

<span data-ttu-id="56136-173">该 `copy(object)` 方法将指定对象的字符串表示形式复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="56136-173">The `copy(object)` method copies a string representation of the specified object to the clipboard.</span></span>  

```console
copy($0)
```  

## <span data-ttu-id="56136-174">调试</span><span class="sxs-lookup"><span data-stu-id="56136-174">debug</span></span>  

```console
debug(method)
```  

>[!NOTE]
> <span data-ttu-id="56136-175">[Chromium 问题 #1050237][MonorailIssue1050237]使用该函数跟踪 bug `debug()` 。</span><span class="sxs-lookup"><span data-stu-id="56136-175">The [Chromium issue #1050237][MonorailIssue1050237] is tracking a bug with the `debug()` function.</span></span>  <span data-ttu-id="56136-176">如果遇到此问题，请尝试改为[使用断点][DevtoolsJavascriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="56136-176">If you encounter the issue, try [using breakpoints][DevtoolsJavascriptBreakpoints] instead.</span></span>  

<span data-ttu-id="56136-177">当你请求指定的方法时，将调用调试器并在 "**源**" 面板上的方法内中断，从而使你可以逐句通过代码并调试它。</span><span class="sxs-lookup"><span data-stu-id="56136-177">When you request the specified method, the debugger is invoked and breaks inside the method on the **Sources** panel allowing you to step through the code and debug it.</span></span>  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="使用 debug 在方法中中断（）" lightbox="../media/console-debug-text.msft.png":::
   <span data-ttu-id="56136-179">图13：在方法中中断</span><span class="sxs-lookup"><span data-stu-id="56136-179">Figure 13:  Breaking inside a method with</span></span> `debug()`  
:::image-end:::  

<span data-ttu-id="56136-180">用于 `undebug(method)` 停止中断方法，或使用 UI 禁用所有断点。</span><span class="sxs-lookup"><span data-stu-id="56136-180">Use `undebug(method)` to stop breaking on the method, or use the UI to disable all breakpoints.</span></span>  

<span data-ttu-id="56136-181">有关断点的详细信息，请参阅[用断点暂停代码][DevToolsJavascriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="56136-181">For more information on breakpoints, see [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

## <span data-ttu-id="56136-182">dir</span><span class="sxs-lookup"><span data-stu-id="56136-182">dir</span></span>  

```console
dir(object)
```  

<span data-ttu-id="56136-183">显示指定对象的所有属性的对象样式列表。</span><span class="sxs-lookup"><span data-stu-id="56136-183">Displays an object-style listing of all of the properties for the specified object.</span></span>  <span data-ttu-id="56136-184">此方法是[console for dir （）][MDNConsoleDir]方法的别名。</span><span class="sxs-lookup"><span data-stu-id="56136-184">This method is an alias for the [console.dir()][MDNConsoleDir] method.</span></span>  

<span data-ttu-id="56136-185">`document.head`在控制台中计算以显示和标记之间的 `<head>` HTML `</head>` 。</span><span class="sxs-lookup"><span data-stu-id="56136-185">Evaluate `document.head` in the Console to display the HTML between the `<head>` and `</head>` tags.</span></span>  <span data-ttu-id="56136-186">在以下代码示例和图中，在控制台中使用后将显示一个对象样式的列表 `console.dir()` 。</span><span class="sxs-lookup"><span data-stu-id="56136-186">In the following code sample and figure, an object-style listing is displayed after using `console.dir()` in the Console.</span></span>  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="记录文档 head with dir （）方法" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   <span data-ttu-id="56136-188">图14：日志 `document.head` 记录 `dir()` 方法</span><span class="sxs-lookup"><span data-stu-id="56136-188">Figure 14:  Logging `document.head` with `dir()` method</span></span>  
:::image-end:::  

<span data-ttu-id="56136-189">有关详细信息，请参阅 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 控制台 API 中的条目。</span><span class="sxs-lookup"><span data-stu-id="56136-189">For more information, see the [`console.dir()`][DevToolsConsoleApiConsoleDirObject] entry in the Console API.</span></span>  

## <span data-ttu-id="56136-190">dirxml</span><span class="sxs-lookup"><span data-stu-id="56136-190">dirxml</span></span>  

```console
dirxml(object)
```  

<span data-ttu-id="56136-191">打印指定对象的 XML 表示形式，如在 "**元素**" 选项卡中所示。 此方法等效于[dirxml （）][MDNConsoleDirxml]方法。</span><span class="sxs-lookup"><span data-stu-id="56136-191">Prints an XML representation of the specified object, as seen in the **Elements** tab.  This method is equivalent to the [console.dirxml()][MDNConsoleDirxml] method.</span></span>  

## <span data-ttu-id="56136-192">查看</span><span class="sxs-lookup"><span data-stu-id="56136-192">inspect</span></span>  

```console
inspect(object/method)
```  

<span data-ttu-id="56136-193">打开并选择相应面板中的指定元素或对象： "元素" 面板中的 "**元素**" 面板或 JavaScript 堆对象的 "**内存**" 面板。</span><span class="sxs-lookup"><span data-stu-id="56136-193">Opens and selects the specified element or object in the appropriate panel:  either the **Elements** panel for DOM elements or the **Memory** panel for JavaScript heap objects.</span></span>  

<span data-ttu-id="56136-194">在以下代码示例和图中，在 " `document.body` **元素**" 面板中打开。</span><span class="sxs-lookup"><span data-stu-id="56136-194">In the following code sample and figure, the `document.body` opens in the **Elements** panel.</span></span>  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="使用 "检查" （）检查元素" lightbox="../media/console-inspect-document-body.msft.png":::
   <span data-ttu-id="56136-196">图15：检查元素</span><span class="sxs-lookup"><span data-stu-id="56136-196">Figure 15:  Inspecting an element with</span></span> `inspect()`  
:::image-end:::  

<span data-ttu-id="56136-197">传递要检查的方法时，该方法将在 "**源**" 面板中打开文档以供您检查。</span><span class="sxs-lookup"><span data-stu-id="56136-197">When passing a method to inspect, the method opens the document in the **Sources** panel for you to inspect.</span></span>  

## <span data-ttu-id="56136-198">getEventListeners</span><span class="sxs-lookup"><span data-stu-id="56136-198">getEventListeners</span></span>  

```console
getEventListeners(object)
```  

<span data-ttu-id="56136-199">返回在指定对象上注册的事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="56136-199">Returns the event listeners registered on the specified object.</span></span>  <span data-ttu-id="56136-200">返回值是一个对象，其中包含每个已注册事件类型的数组 \ （如 `click` 或 `keydown` \）。</span><span class="sxs-lookup"><span data-stu-id="56136-200">The return value is an object that contains an array for each registered event type \(such as `click` or `keydown`\).</span></span>  <span data-ttu-id="56136-201">每个数组的成员都是描述为每种类型注册的侦听器的对象。</span><span class="sxs-lookup"><span data-stu-id="56136-201">The members of each array are objects that describe the listener registered for each type.</span></span>  <span data-ttu-id="56136-202">在以下代码示例图中，列出了在文档对象上注册的所有事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="56136-202">In the following code sample figure, all of the event listeners registered on the document object are listed.</span></span>  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="使用 getEventListeners （文档）的输出" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   <span data-ttu-id="56136-204">图16：使用的结果</span><span class="sxs-lookup"><span data-stu-id="56136-204">Figure 16:  The result of using</span></span> `getEventListeners(document)`  
:::image-end:::  

<span data-ttu-id="56136-205">如果在指定对象上注册了多个侦听器，则该数组包含每个侦听器的成员。</span><span class="sxs-lookup"><span data-stu-id="56136-205">If more than one listener is registered on the specified object, then the array contains a member for each listener.</span></span>  <span data-ttu-id="56136-206">下图中，事件的文档元素上注册了两个事件侦听器 `click` 。</span><span class="sxs-lookup"><span data-stu-id="56136-206">In the following figure, there are two event listeners registered on the document element for the `click` event.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="多个侦听器" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   <span data-ttu-id="56136-208">图17：多个侦听器</span><span class="sxs-lookup"><span data-stu-id="56136-208">Figure 17:  Multiple listeners</span></span>  
:::image-end:::  

<span data-ttu-id="56136-209">你可以进一步展开以下每个对象以浏览属性。</span><span class="sxs-lookup"><span data-stu-id="56136-209">You may further expand each of the following objects to explore the properties.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="侦听器对象的展开视图" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   <span data-ttu-id="56136-211">图18：侦听器对象的展开视图</span><span class="sxs-lookup"><span data-stu-id="56136-211">Figure 18:  Expanded view of listener object</span></span>  
:::image-end:::  

## <span data-ttu-id="56136-212">键</span><span class="sxs-lookup"><span data-stu-id="56136-212">keys</span></span>  

```console
keys(object)
```  

<span data-ttu-id="56136-213">返回一个数组，其中包含属于指定对象的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="56136-213">Returns an array containing the names of the properties belonging to the specified object.</span></span>  <span data-ttu-id="56136-214">若要获取相同属性的关联值，请使用 `values()` 。</span><span class="sxs-lookup"><span data-stu-id="56136-214">To get the associated values of the same properties, use `values()`.</span></span>  

<span data-ttu-id="56136-215">例如，假设你的应用程序定义了以下对象。</span><span class="sxs-lookup"><span data-stu-id="56136-215">For example, suppose your application defined the following object.</span></span>  

```console
var player1 = { "name":  "Ted", "level": 42 }
```  

<span data-ttu-id="56136-216">在以下代码示例和图中，结果假定 `player1` 在键入 `keys(player1)` 和 `values(player1)` 在控制台中之前已在全局命名空间中定义了 \ （对于简单性 \）。</span><span class="sxs-lookup"><span data-stu-id="56136-216">In the following code samples and figure, the result assumes `player1` was defined in the global namespace \(for simplicity\) prior to typing `keys(player1)` and `values(player1)` in the console.</span></span>  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="键（）和值（）命令" lightbox="../media/console-keys-values.msft.png":::
   <span data-ttu-id="56136-218">图19： `keys()` 和 `values()` 命令</span><span class="sxs-lookup"><span data-stu-id="56136-218">Figure 19:  The `keys()` and `values()` commands</span></span>  
:::image-end:::  

## <span data-ttu-id="56136-219">监视器</span><span class="sxs-lookup"><span data-stu-id="56136-219">monitor</span></span>  

```console
monitor(method)
```  

<span data-ttu-id="56136-220">向控制台记录一条消息，指示方法名称以及调用时传递给该方法的参数。</span><span class="sxs-lookup"><span data-stu-id="56136-220">Logs a message to the console that indicates the method name along with the arguments that are passed to the method when it was called.</span></span>  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="Monitor （）方法" lightbox="../media/console-function-monitor-sum.msft.png":::
   <span data-ttu-id="56136-222">图20： `monitor()` 方法</span><span class="sxs-lookup"><span data-stu-id="56136-222">Figure 20:  The `monitor()` method</span></span>  
:::image-end:::  

<span data-ttu-id="56136-223">用于 `unmonitor(method)` 停止监视。</span><span class="sxs-lookup"><span data-stu-id="56136-223">Use `unmonitor(method)` to cease monitoring.</span></span>  

## <span data-ttu-id="56136-224">monitorEvents</span><span class="sxs-lookup"><span data-stu-id="56136-224">monitorEvents</span></span>  

```console
monitorEvents(object[, events])
```  

<span data-ttu-id="56136-225">当指定的对象上发生其中一个指定的事件时，事件对象将被记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="56136-225">When one of the specified events occurs on the specified object, the event object is logged to the console.</span></span>  <span data-ttu-id="56136-226">你可以指定要监视的单个事件、事件数组或映射到预定义事件集合的常规事件类型之一。</span><span class="sxs-lookup"><span data-stu-id="56136-226">You may specify a single event to monitor, an array of events, or one of the generic events types that are mapped to a predefined collection of events.</span></span>  <span data-ttu-id="56136-227">请参阅以下代码示例和图。</span><span class="sxs-lookup"><span data-stu-id="56136-227">See the following code sample and figure.</span></span>  

<span data-ttu-id="56136-228">以下监视窗口对象上的所有大小调整事件。</span><span class="sxs-lookup"><span data-stu-id="56136-228">The following monitors all resize events on the window object.</span></span>  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="监视窗口调整大小事件" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   <span data-ttu-id="56136-230">图21：监视窗口调整大小事件</span><span class="sxs-lookup"><span data-stu-id="56136-230">Figure 21:  Monitoring window resize events</span></span>  
:::image-end:::  

<span data-ttu-id="56136-231">以下定义一个数组，用于监视 `resize` `scroll` 窗口对象上的两个事件和事件。</span><span class="sxs-lookup"><span data-stu-id="56136-231">The following defines an array to monitor both `resize` and `scroll` events on the window object.</span></span>  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

<span data-ttu-id="56136-232">你还可以指定一个可用的事件类型，这些字符串映射到预定义的事件集。</span><span class="sxs-lookup"><span data-stu-id="56136-232">You may also specify one of the available types of events, strings that map to predefined sets of events.</span></span>  <span data-ttu-id="56136-233">下表显示可用的事件类型和关联的事件映射。</span><span class="sxs-lookup"><span data-stu-id="56136-233">The table below displays the available event types and the associated event mappings.</span></span>  

| <span data-ttu-id="56136-234">事件类型</span><span class="sxs-lookup"><span data-stu-id="56136-234">Event type</span></span> | <span data-ttu-id="56136-235">相应的映射事件</span><span class="sxs-lookup"><span data-stu-id="56136-235">Corresponding mapped events</span></span> |  
|:--- |:--- |  
| `mouse` | <span data-ttu-id="56136-236">"单击"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"鼠标悬停"、""、"mousewheel"</span><span class="sxs-lookup"><span data-stu-id="56136-236">"click", "dblclick", "mousedown", "mousemove", "mouseout", "mouseover", "mouseup", "mousewheel"</span></span> |  
| `key` | <span data-ttu-id="56136-237">"keydown"、"keypress"、"keyup"、"textInput"</span><span class="sxs-lookup"><span data-stu-id="56136-237">"keydown", "keypress", "keyup", "textInput"</span></span> |  
| `touch` | <span data-ttu-id="56136-238">"touchcancel", "touchend", "touchmove", "touchstart"</span><span class="sxs-lookup"><span data-stu-id="56136-238">"touchcancel", "touchend", "touchmove", "touchstart"</span></span> |  
| `control` | <span data-ttu-id="56136-239">"模糊"、"更改"、"焦点"、"重置"、"调整大小"、"滚动"、"选择"、"提交"、"缩放"</span><span class="sxs-lookup"><span data-stu-id="56136-239">"blur", "change", "focus", "reset", "resize", "scroll", "select", "submit", "zoom"</span></span> |  

<span data-ttu-id="56136-240">在以下代码示例中， `key` `key` "**元素**" 面板中当前已选中了与输入文本字段上的事件相对应的事件类型。</span><span class="sxs-lookup"><span data-stu-id="56136-240">In the following code sample, the `key` event type corresponding to `key` events on an input text field are currently selected in the **Elements** panel.</span></span>  

```console
monitorEvents($0, "key");
```  

<span data-ttu-id="56136-241">下图显示了在文本字段中键入字符后的示例输出。</span><span class="sxs-lookup"><span data-stu-id="56136-241">In the following figure the sample output after typing a character in the text field is displayed.</span></span>  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="监视键事件" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   <span data-ttu-id="56136-243">图22：监视键事件</span><span class="sxs-lookup"><span data-stu-id="56136-243">Figure 22:  Monitoring key events</span></span>  
:::image-end:::  

## <span data-ttu-id="56136-244">profile</span><span class="sxs-lookup"><span data-stu-id="56136-244">profile</span></span>  

```console
profile([name])
```  

<span data-ttu-id="56136-245">启动具有可选名称的 JavaScript CPU 性能分析会话。</span><span class="sxs-lookup"><span data-stu-id="56136-245">Starts a JavaScript CPU profiling session with an optional name.</span></span>  <span data-ttu-id="56136-246">[ProfileEnd （）](#profileend)方法完成配置文件并在 "**内存**" 面板中显示结果。</span><span class="sxs-lookup"><span data-stu-id="56136-246">The [profileEnd()](#profileend) method completes the profile and displays the results in the **Memory** panel.</span></span>  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="56136-247">运行该 `profile()` 方法以开始分析。</span><span class="sxs-lookup"><span data-stu-id="56136-247">Run the `profile()` method to start profiling.</span></span>  
    
    ```console
    profile("My profile")
    ```  
    
1.  <span data-ttu-id="56136-248">运行[profileEnd （）](#profileend)方法以停止分析并在 "**内存**" 面板中显示结果。</span><span class="sxs-lookup"><span data-stu-id="56136-248">Run the [profileEnd()](#profileend) method to stop profiling and display the results in the **Memory** panel.</span></span>  

<span data-ttu-id="56136-249">配置文件也可能是嵌套的。</span><span class="sxs-lookup"><span data-stu-id="56136-249">Profiles may also be nested.</span></span>  <span data-ttu-id="56136-250">在以下代码示例和图中，无论顺序如何，结果都是相同的。</span><span class="sxs-lookup"><span data-stu-id="56136-250">In the following code samples and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> <span data-ttu-id="56136-251">多个 CPU 配置文件可能同时运行，您无需按创建顺序将其关闭。</span><span class="sxs-lookup"><span data-stu-id="56136-251">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <span data-ttu-id="56136-252">profileEnd</span><span class="sxs-lookup"><span data-stu-id="56136-252">profileEnd</span></span>  

```console
profileEnd([name])
```  

<span data-ttu-id="56136-253">完成 JavaScript CPU 分析会话并在 "**内存**" 面板中显示结果。</span><span class="sxs-lookup"><span data-stu-id="56136-253">Completes a JavaScript CPU profiling session and displays the results in the **Memory** panel.</span></span>  <span data-ttu-id="56136-254">您必须运行[配置文件（）](#profile)方法。</span><span class="sxs-lookup"><span data-stu-id="56136-254">You must be running the [profile()](#profile) method.</span></span>  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="56136-255">运行[配置文件（）](#profile)方法开始分析。</span><span class="sxs-lookup"><span data-stu-id="56136-255">Run the [profile()](#profile) method to start profiling.</span></span>  
1.  <span data-ttu-id="56136-256">运行 `profileEnd()` 方法以停止分析并在 "**内存**" 面板中显示结果。</span><span class="sxs-lookup"><span data-stu-id="56136-256">Run the `profileEnd()` method to stop profiling and display the results in the **Memory** panel.</span></span>  
    
    ```console
    profileEnd("My profile")
    ```  

<span data-ttu-id="56136-257">配置文件也可能是嵌套的。</span><span class="sxs-lookup"><span data-stu-id="56136-257">Profiles may also be nested.</span></span>  <span data-ttu-id="56136-258">在以下代码示例和图中，无论顺序如何，结果都是相同的。</span><span class="sxs-lookup"><span data-stu-id="56136-258">In the following code sample and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

<span data-ttu-id="56136-259">结果在 "**内存**" 面板中显示为堆快照。</span><span class="sxs-lookup"><span data-stu-id="56136-259">The result appears as a Heap Snapshot in the **Memory** panel.</span></span>  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="分组的配置文件" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   <span data-ttu-id="56136-261">图23：分组的配置文件</span><span class="sxs-lookup"><span data-stu-id="56136-261">Figure 23:  Grouped profiles</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="56136-262">多个 CPU 配置文件可能同时运行，您无需按创建顺序将其关闭。</span><span class="sxs-lookup"><span data-stu-id="56136-262">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <span data-ttu-id="56136-263">queryObjects</span><span class="sxs-lookup"><span data-stu-id="56136-263">queryObjects</span></span>  

```console
queryObjects(Constructor)
```  

<span data-ttu-id="56136-264">返回使用指定构造函数创建的对象数组。</span><span class="sxs-lookup"><span data-stu-id="56136-264">Return an array of objects created with the specified constructor.</span></span>  <span data-ttu-id="56136-265">的范围 `queryObjects()` 是当前在控制台中选定的运行时上下文。</span><span class="sxs-lookup"><span data-stu-id="56136-265">The scope of `queryObjects()` is the currently-selected runtime context in the console.</span></span>

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      <span data-ttu-id="56136-266">返回 all `Promises` 。</span><span class="sxs-lookup"><span data-stu-id="56136-266">Returns all `Promises`.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      <span data-ttu-id="56136-267">返回所有 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="56136-267">Returns all HTML elements.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      <span data-ttu-id="56136-268">返回使用实例化的所有对象 `new functionName()` 。</span><span class="sxs-lookup"><span data-stu-id="56136-268">Returns all objects that were instantiated using `new functionName()`.</span></span>  
   :::column-end:::
:::row-end:::  

---  

## <span data-ttu-id="56136-269">表</span><span class="sxs-lookup"><span data-stu-id="56136-269">table</span></span>  

```console
table(data[, columns])
```  

<span data-ttu-id="56136-270">基于带有可选列标题的数据对象，基于表格格式记录对象数据。</span><span class="sxs-lookup"><span data-stu-id="56136-270">Logs object data with table formatting based upon the data object in with optional column headings.</span></span>  <span data-ttu-id="56136-271">在以下代码示例和图中，显示了在控制台中使用表的名称列表。</span><span class="sxs-lookup"><span data-stu-id="56136-271">In the following code sample and figure, a list of names using a table in the console is displayed.</span></span>  

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

:::image type="complex" source="../media/console-table-display.msft.png" alt-text="Table （）方法的结果" lightbox="../media/console-table-display.msft.png":::
   <span data-ttu-id="56136-273">图24：方法的结果 `table()`</span><span class="sxs-lookup"><span data-stu-id="56136-273">Figure 24:  The result of the `table()` method</span></span>  
:::image-end:::  

## <span data-ttu-id="56136-274">undebug</span><span class="sxs-lookup"><span data-stu-id="56136-274">undebug</span></span>  

```console
undebug(method)
```  

<span data-ttu-id="56136-275">停止对指定方法的调试，以便在调用该方法时不再调用调试器。</span><span class="sxs-lookup"><span data-stu-id="56136-275">Stops the debugging of the specified method so that when the method is called, the debugger is no longer invoked.</span></span>  

```console
undebug(getData);
```  

## <span data-ttu-id="56136-276">unmonitor</span><span class="sxs-lookup"><span data-stu-id="56136-276">unmonitor</span></span>  

```console
unmonitor(method)
```  

<span data-ttu-id="56136-277">停止对指定方法的监视。</span><span class="sxs-lookup"><span data-stu-id="56136-277">Stops the monitoring of the specified method.</span></span>  <span data-ttu-id="56136-278">此方法与[monitor （）](#monitor)方法配合使用。</span><span class="sxs-lookup"><span data-stu-id="56136-278">This method is used in concert with the [monitor()](#monitor) method.</span></span>  

```console
unmonitor(getData);
```  

## <span data-ttu-id="56136-279">unmonitorEvents</span><span class="sxs-lookup"><span data-stu-id="56136-279">unmonitorEvents</span></span>  

```console
unmonitorEvents(object[, events])
```  

<span data-ttu-id="56136-280">停止监视指定对象和事件的事件。</span><span class="sxs-lookup"><span data-stu-id="56136-280">Stops monitoring events for the specified object and events.</span></span>  <span data-ttu-id="56136-281">例如，以下事件将停止窗口对象上的所有事件监视。</span><span class="sxs-lookup"><span data-stu-id="56136-281">For example, the following stops all event monitoring on the window object.</span></span>  

```console
unmonitorEvents(window);
```  

<span data-ttu-id="56136-282">你还可以有选择地停止监视对象上的特定事件。</span><span class="sxs-lookup"><span data-stu-id="56136-282">You may also selectively stop monitoring specific events on an object.</span></span>  <span data-ttu-id="56136-283">例如，以下代码开始监视 `mouse` 当前所选元素上的所有事件，然后停止监视 `mousemove` 事件 \ （可能减少控制台输出中的干扰 \）。</span><span class="sxs-lookup"><span data-stu-id="56136-283">For example, the following code starts monitoring all `mouse` events on the currently selected element, and then stops monitoring `mousemove` events \(perhaps to reduce noise in the console output\).</span></span>  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## <span data-ttu-id="56136-284">相对值</span><span class="sxs-lookup"><span data-stu-id="56136-284">values</span></span>  

```console
values(object)
```  

<span data-ttu-id="56136-285">返回一个数组，其中包含属于指定对象的所有属性的值。</span><span class="sxs-lookup"><span data-stu-id="56136-285">Returns an array containing the values of all properties belonging to the specified object.</span></span>  

```console
values(object);
```  

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
> <span data-ttu-id="56136-295">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="56136-295">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="56136-296">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/utilities)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="56136-296">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/utilities) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="56136-298">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="56136-298">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
