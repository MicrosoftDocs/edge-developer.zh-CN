---
description: Microsoft Edge DevTools 控制台中提供的便利命令参考。
title: 控制台实用工具 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: c6a0356bd590809f9164aa62fd42156f901cef0f
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483280"
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
# <a name="console-utilities-api-reference"></a><span data-ttu-id="8ad8a-104">控制台实用工具 API 参考</span><span class="sxs-lookup"><span data-stu-id="8ad8a-104">Console Utilities API reference</span></span>  

<span data-ttu-id="8ad8a-105">控制台实用程序 API 包含一组方便命令，用于完成以下常见任务。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-105">The Console Utilities API contains a collection of convenience commands to complete the following common tasks.</span></span>  

*   <span data-ttu-id="8ad8a-106">选择并检查 DOM 元素</span><span class="sxs-lookup"><span data-stu-id="8ad8a-106">Choose and inspect DOM elements</span></span>  
*   <span data-ttu-id="8ad8a-107">以可读格式显示数据</span><span class="sxs-lookup"><span data-stu-id="8ad8a-107">Display data in readable format</span></span>  
*   <span data-ttu-id="8ad8a-108">停止并启动探查器</span><span class="sxs-lookup"><span data-stu-id="8ad8a-108">Stop and start the profiler</span></span>  
*   <span data-ttu-id="8ad8a-109">监视 DOM 事件</span><span class="sxs-lookup"><span data-stu-id="8ad8a-109">Monitor DOM events</span></span>  
    
> [!WARNING]
> <span data-ttu-id="8ad8a-110">以下命令仅适用于 Microsoft Edge DevTools **控制台**。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-110">The following commands only work in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="8ad8a-111">如果从脚本运行，则命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-111">The commands do not work if run from your scripts.</span></span>  

<span data-ttu-id="8ad8a-112">有关 和 方法以及方法其余部分的信息， `console.log()` `console.error()` `console.*` 请导航到"控制台 API[参考"。][DevToolsConsoleApi]</span><span class="sxs-lookup"><span data-stu-id="8ad8a-112">For more information about the `console.log()` and `console.error()` methods and the rest of the `console.*` methods, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  

## <a name="recently-evaluated-expression"></a><span data-ttu-id="8ad8a-113">最近计算表达式</span><span class="sxs-lookup"><span data-stu-id="8ad8a-113">Recently evaluated expression</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-114">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-114">Console syntax</span></span>  

```console
$_
```  

<span data-ttu-id="8ad8a-115">此命令返回最近计算表达式的值。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-115">This command returns the value of the most recently evaluated expression.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-116">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-116">Console example</span></span>  

<span data-ttu-id="8ad8a-117">在下图中，将计算一个简单的表达式 \ (`2 + 2` \) 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-117">In the following figure, a simple expression \(`2 + 2`\) is evaluated.</span></span>  <span data-ttu-id="8ad8a-118">然后 `$_` 计算属性，其中包含相同的值。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-118">The `$_` property is then evaluated, which contains the same value.</span></span>  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$_ 是最近评估的表达式" lightbox="../media/console-arithmatic.msft.png":::
   `$_` <span data-ttu-id="8ad8a-120">是最近计算表达式</span><span class="sxs-lookup"><span data-stu-id="8ad8a-120">is the most recently evaluated expression</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-121">在下图中，计算表达式最初包含一个名称数组。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-121">In the following figure, the evaluated expression initially contains an array of names.</span></span>  <span data-ttu-id="8ad8a-122">计算 以查找数组的长度，存储在 中的值 `$_.length` `$_` 将成为最新的计算表达式 `4` 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-122">Evaluating `$_.length` to find the length of the array, the value stored in `$_` becomes the latest evaluated expression, `4`.</span></span>  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="$_ 评估新命令时的更改" lightbox="../media/console-array-length.msft.png":::
   `$_` <span data-ttu-id="8ad8a-124">评估新命令时更改</span><span class="sxs-lookup"><span data-stu-id="8ad8a-124">changes when new commands are evaluated</span></span>  
:::image-end:::  

---  

## <a name="recently-chosen-element-or-javascript-object"></a><span data-ttu-id="8ad8a-125">最近选择的元素或 JavaScript 对象</span><span class="sxs-lookup"><span data-stu-id="8ad8a-125">Recently chosen element or JavaScript object</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-126">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-126">Console syntax</span></span>  

```console
$0
```  

<span data-ttu-id="8ad8a-127">此命令返回最近选择的元素或 JavaScript 对象。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-127">This command returns the most recently chosen element or JavaScript object.</span></span>  `$1` <span data-ttu-id="8ad8a-128">返回第二个最近选择一个，等等。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-128">returns the second most recently chosen one, and so on.</span></span>  <span data-ttu-id="8ad8a-129">、 、 和 命令用作对在元素工具中检查的最后 `$0` `$1` `$2` `$3` `$4` 五个 DOM\*\*\*\*\*\*\*\* 元素或内存工具中选定的最后五个 JavaScript 堆对象的历史引用。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-129">The `$0`, `$1`, `$2`, `$3`, and `$4` commands work as a historical reference to the last five DOM elements inspected within the **Elements** tool or the last five JavaScript heap objects chosen in the **Memory** tool.</span></span>  

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

### <a name="console-example"></a><span data-ttu-id="8ad8a-130">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-130">Console example</span></span>  

<span data-ttu-id="8ad8a-131">在下图中， `img` 在"元素"工具中选择了 **一个元素** 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-131">In the following figure, an `img` element is chosen in the **Elements** tool.</span></span>  <span data-ttu-id="8ad8a-132">在 **控制台箱** 中 `$0` ，已进行评估并显示相同的元素。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-132">In the **Console** drawer, `$0` has been evaluated and displays the same element.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   <span data-ttu-id="8ad8a-134">该</span><span class="sxs-lookup"><span data-stu-id="8ad8a-134">The</span></span> `$0`  
:::image-end:::  

<span data-ttu-id="8ad8a-135">下图中，图像显示在同一网页中选择的不同元素。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-135">In the following figure, the image displays a different element chosen in the same webpage.</span></span>  <span data-ttu-id="8ad8a-136">`$0`现在引用新选择的元素，而 `$1` 返回之前选择的元素。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-136">The `$0` now refers to the newly chosen element, while `$1` returns the previously chosen one.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   <span data-ttu-id="8ad8a-138">该</span><span class="sxs-lookup"><span data-stu-id="8ad8a-138">The</span></span> `$1`  
:::image-end:::  

---  

## <a name="query-selector"></a><span data-ttu-id="8ad8a-139">查询选择器</span><span class="sxs-lookup"><span data-stu-id="8ad8a-139">Query selector</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-140">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-140">Console syntax</span></span>  

```console
$(selector, [startNode])
```  

<span data-ttu-id="8ad8a-141">此命令返回对具有指定 CSS 选择器的第一个 DOM 元素的引用。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-141">This command returns the reference to the first DOM element with the specified CSS selector.</span></span>  <span data-ttu-id="8ad8a-142">此方法是 [document.querySelector ][MdnDocsWebApiDocumentQueryselector] () 别名。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-142">This method is an alias for the [document.querySelector()][MdnDocsWebApiDocumentQueryselector] method.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-143">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-143">Console example</span></span>  

<span data-ttu-id="8ad8a-144">在下图中，将返回对网页 `<img>` 中第一个元素的引用。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-144">In the following figure, a reference to the first `<img>` element in the webpage is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$ ('img') " lightbox="../media/console-element-selector-image.msft.png":::
   <span data-ttu-id="8ad8a-146">该</span><span class="sxs-lookup"><span data-stu-id="8ad8a-146">The</span></span> `$('img')`  
:::image-end:::  

<span data-ttu-id="8ad8a-147">若要在 DOM 中查找第一个元素或在网页上查找并显示该元素，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-147">To find the first element in the DOM or to find and display it on the webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ad8a-148">将鼠标悬停在返回的结果上。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-148">Hover on the returned result.</span></span>  
1.  <span data-ttu-id="8ad8a-149">打开上下文菜单\（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-149">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="8ad8a-150">选择 **"元素面板"中的"展示"。**</span><span class="sxs-lookup"><span data-stu-id="8ad8a-150">Choose **Reveal in Elements Panel**.</span></span>  

<span data-ttu-id="8ad8a-151">在下图中，将返回对当前选择的元素的引用， `src` 并显示 属性。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-151">In the following figure, a reference to the currently chosen element is returned and the `src` property is displayed.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$ ('img') .src" lightbox="../media/console-element-selector-image-source.msft.png":::
   <span data-ttu-id="8ad8a-153">该</span><span class="sxs-lookup"><span data-stu-id="8ad8a-153">The</span></span> `$('img').src`  
:::image-end:::  

<span data-ttu-id="8ad8a-154">此方法还支持第二个参数 ，用于指定要搜索的元素或 `startNode` 节点。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-154">This method also supports a second parameter, `startNode`, that specifies an element or node from which to search for elements.</span></span>  <span data-ttu-id="8ad8a-155">参数的默认值为 `document` 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-155">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="8ad8a-156">在下图中，找到 `img` 元素后的第一个元素 `title--image` ，并返回 `src` `img` 元素的 属性。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-156">In the following figure, the first `img` element after the `title--image` element is found, and the `src` property of the `img` element is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$ ('img'， document.querySelector ('title--image') ) .src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   <span data-ttu-id="8ad8a-158">该</span><span class="sxs-lookup"><span data-stu-id="8ad8a-158">The</span></span> `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="8ad8a-159">如果使用的库（如 jQuery）使用 ，则功能将被覆盖，并且对应于该库中 `$` `$` 的实现。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-159">If you are using a library such as jQuery that uses `$`, the functionality is overwritten, and `$` corresponds to the implementation from that library.</span></span>  

---  

## <a name="query-selector-all"></a><span data-ttu-id="8ad8a-160">查询选择器全部</span><span class="sxs-lookup"><span data-stu-id="8ad8a-160">Query selector all</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-161">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-161">Console syntax</span></span>  

```console
$$(selector, [startNode])
```  

<span data-ttu-id="8ad8a-162">此命令返回匹配指定 CSS 选择器的元素数组。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-162">This command returns an array of elements that match the specified CSS selector.</span></span>  <span data-ttu-id="8ad8a-163">此方法等效于运行 [document.querySelectorAll () ][MdnDocsWebApiDocumentQueryselectorall] 方法。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-163">This method is equivalent to running the [document.querySelectorAll()][MdnDocsWebApiDocumentQueryselectorall] method.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-164">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-164">Console example</span></span>  

<span data-ttu-id="8ad8a-165">在下面的代码示例和图中，使用 创建当前网页中所有元素的数组 `$$()` `<img>` 并显示每个 `src` 元素的 属性值。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-165">In the following code sample and figure, use `$$()` to create an array of all `<img>` elements in the current webpage and display the value of the `src` property for each element.</span></span>  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="使用 $$ () 选择网页中的所有图像并显示源" lightbox="../media/console-element-selector-image-all.msft.png":::
   <span data-ttu-id="8ad8a-167">用于 `$$()` 选择网页中所有图像并显示源</span><span class="sxs-lookup"><span data-stu-id="8ad8a-167">Using `$$()` to choose all images in the webpage and display the sources</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-168">此方法还支持第二个参数 ，用于指定要搜索的元素或 `startNode` 节点。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-168">This method also supports a second parameter, `startNode`, that specifies an element or node from which to search for elements.</span></span>  <span data-ttu-id="8ad8a-169">参数的默认值为 `document` 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-169">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="8ad8a-170">在下面的代码示例和图中，上一个代码示例和图的修改版本用于创建一个数组，该数组包含当前网页中所选节点之后 `$$()` `<img>` 出现的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-170">In the following code sample and figure, a modified version of the previous code sample and figure uses `$$()` to create an array of all `<img>` elements that appear in the current webpage after the chosen node.</span></span>  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="使用 $$ () 选择在网页中的指定 div <div>后显示的所有图像并显示源" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   <span data-ttu-id="8ad8a-172">用于 `$$()` 选择网页中指定元素之后显示的所有图像 `<div>` 并显示源</span><span class="sxs-lookup"><span data-stu-id="8ad8a-172">Using `$$()` to choose all images that appear after the specified `<div>` element in the webpage and display the sources</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="8ad8a-173">在 `Shift` + `Enter` 控制台**中选择以**在不运行脚本的情况下启动新行。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-173">Select `Shift`+`Enter` in the **Console** to start a new line without running the script.</span></span>  

---  

## <a name="xpath"></a><span data-ttu-id="8ad8a-174">XPath</span><span class="sxs-lookup"><span data-stu-id="8ad8a-174">XPath</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-175">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-175">Console syntax</span></span>  

```console
$x(path, [startNode])
```  

<span data-ttu-id="8ad8a-176">此命令返回匹配指定 XPath 表达式的 DOM 元素的数组。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-176">This command returns an array of DOM elements that match the specified XPath expression.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-177">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-177">Console example</span></span>  

<span data-ttu-id="8ad8a-178">在下面的代码示例和图中，将返回 `<p>` 网页上的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-178">In the following code sample and figure, all of the `<p>` elements on the webpage are returned.</span></span>  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="使用 XPath 选择器" lightbox="../media/console-array-xpath.msft.png":::
   <span data-ttu-id="8ad8a-180">使用 XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="8ad8a-180">Using an XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-181">在下面的代码示例和图中，将返回 `<p>` 包含元素 `<a>` 的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-181">In the following code sample and figure, all of the `<p>` elements that contain `<a>` elements are returned.</span></span>  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="使用更复杂的 XPath 选择器" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   <span data-ttu-id="8ad8a-183">使用更复杂的 XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="8ad8a-183">Using a more complicated XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-184">与其他选择器命令类似，具有可选的第二个参数 ，用于指定要搜索的元素或 `$x(path)` `startNode` 节点。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-184">Similar to the other selector commands, `$x(path)` has an optional second parameter, `startNode`, that specifies an element or node from which to search for elements.</span></span>  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="将 XPath 选择器与 startNode 一同使用" lightbox="../media/console-array-xpath-startnode.msft.png":::
   <span data-ttu-id="8ad8a-186">将 XPath 选择器与</span><span class="sxs-lookup"><span data-stu-id="8ad8a-186">Using an XPath selector with</span></span> `startNode`  
:::image-end:::  

---  

## <a name="clear"></a><span data-ttu-id="8ad8a-187">clear</span><span class="sxs-lookup"><span data-stu-id="8ad8a-187">clear</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-188">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-188">Console syntax</span></span>  

```console
clear()
```  

<span data-ttu-id="8ad8a-189">此命令清除历史记录的控制台。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-189">This commnad clears the console of the history.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-190">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-190">Console example</span></span>  

```console
clear()
```  

## <a name="copy"></a><span data-ttu-id="8ad8a-191">copy</span><span class="sxs-lookup"><span data-stu-id="8ad8a-191">copy</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-192">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-192">Console syntax</span></span>  

```console
copy(object)
```  

<span data-ttu-id="8ad8a-193">此方法将指定对象的字符串表示形式复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-193">This method copies a string representation of the specified object to the clipboard.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-194">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-194">Console example</span></span>  

```console
copy($0)
```  

---  

## <a name="debug"></a><span data-ttu-id="8ad8a-195">调试</span><span class="sxs-lookup"><span data-stu-id="8ad8a-195">debug</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-196">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-196">Console syntax</span></span>  

```console
debug(method)
```  

>[!NOTE]
> <span data-ttu-id="8ad8a-197">[Chromium 问题#1050237][CR1050237]函数跟踪 `debug()` Bug。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-197">The [Chromium issue #1050237][CR1050237] is tracking a bug with the `debug()` function.</span></span>  <span data-ttu-id="8ad8a-198">如果遇到问题，请尝试改为 [使用断][DevtoolsJavascriptBreakpoints] 点。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-198">If you encounter the issue, try using [breakpoints][DevtoolsJavascriptBreakpoints] instead.</span></span>  

<span data-ttu-id="8ad8a-199">请求指定方法时，调试程序在 Sources 工具的 方法内调用**和中断。**</span><span class="sxs-lookup"><span data-stu-id="8ad8a-199">When you request the specified method, the debugger invokes and breaks inside the method on the **Sources** tool.</span></span>  <span data-ttu-id="8ad8a-200">它允许你逐步调试代码。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-200">It allows you to step through and debug the code.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-201">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-201">Console example</span></span>  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="使用调试工具在方法 () " lightbox="../media/console-debug-text.msft.png":::
   <span data-ttu-id="8ad8a-203">在方法内使用</span><span class="sxs-lookup"><span data-stu-id="8ad8a-203">Breaking inside a method with</span></span> `debug()`  
:::image-end:::  

<span data-ttu-id="8ad8a-204">用于 `undebug(method)` 停止方法上的中断，或使用 UI 关闭所有断点。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-204">Use `undebug(method)` to stop breaking on the method, or use the UI to turn off all breakpoints.</span></span>  

<span data-ttu-id="8ad8a-205">有关断点详细信息，请导航到如何使用 [Microsoft Edge DevTools][DevtoolsJavascriptBreakpoints]中的断点暂停代码。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-205">For more information on breakpoints, navigate to [How to pause your code with breakpoints in Microsoft Edge DevTools][DevtoolsJavascriptBreakpoints].</span></span>  

---  

## <a name="dir"></a><span data-ttu-id="8ad8a-206">dir</span><span class="sxs-lookup"><span data-stu-id="8ad8a-206">dir</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-207">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-207">Console syntax</span></span>  

```console
dir(object)
```  

<span data-ttu-id="8ad8a-208">此命令显示指定对象的所有属性的对象样式列表。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-208">This command displays an object-style listing of all of the properties for the specified object.</span></span>  <span data-ttu-id="8ad8a-209">此方法是 [console.dir ][MdnDocsWebApiConsoleDir] () 别名。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-209">This method is an alias for the [console.dir()][MdnDocsWebApiConsoleDir] method.</span></span>  

<span data-ttu-id="8ad8a-210">在 `document.head` 控制台 **中进行评估** ，以显示 和 标记 `<head>` 之间的 `</head>` HTML。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-210">Evaluate `document.head` in the **Console** to display the HTML between the `<head>` and `</head>` tags.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-211">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-211">Console example</span></span>  

<span data-ttu-id="8ad8a-212">在下面的代码示例和图中，在控制台 中使用 后将显示对象 `console.dir()` 样式 **列表**。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-212">In the following code sample and figure, an object-style listing is displayed after using `console.dir()` in the **Console**.</span></span>  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="使用 dir 方法记录 document.head () 方法" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   <span data-ttu-id="8ad8a-214">使用 `document.head` 方法 `dir()` 日志记录</span><span class="sxs-lookup"><span data-stu-id="8ad8a-214">Logging `document.head` with `dir()` method</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-215">有关详细信息，请导航到控制台 API[中的 console.dir () 。][DevToolsConsoleApiConsoleDirObject]</span><span class="sxs-lookup"><span data-stu-id="8ad8a-215">For more information, navigate to [console.dir()][DevToolsConsoleApiConsoleDirObject] in the Console API.</span></span>  

---  

## <a name="dirxml"></a><span data-ttu-id="8ad8a-216">dirxml</span><span class="sxs-lookup"><span data-stu-id="8ad8a-216">dirxml</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-217">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-217">Console syntax</span></span>  

```console
dirxml(object)
```  

<span data-ttu-id="8ad8a-218">此命令打印指定对象的 XML 表示形式，如 **元素** 工具中显示。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-218">This command prints an XML representation of the specified object, as displayed in the **Elements** tool.</span></span>  <span data-ttu-id="8ad8a-219">此方法等效于 [console.dirxml () ][MdnDocsWebApiConsoleDirxml] 方法。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-219">This method is equivalent to the [console.dirxml()][MdnDocsWebApiConsoleDirxml] method.</span></span>  

---  

## <a name="inspect"></a><span data-ttu-id="8ad8a-220">inspect</span><span class="sxs-lookup"><span data-stu-id="8ad8a-220">inspect</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-221">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-221">Console syntax</span></span>  

```console
inspect(object/method)
```  

<span data-ttu-id="8ad8a-222">此命令将在适当的面板中打开并选择指定的元素或对象：DOM 元素的 **Elements** 工具或 JavaScript 堆对象的 **Memory** 工具。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-222">This command opens and chooses the specified element or object in the appropriate panel:  either the **Elements** tool for DOM elements or the **Memory** tool for JavaScript heap objects.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-223">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-223">Console example</span></span>  

<span data-ttu-id="8ad8a-224">在下面的代码示例和图中，将在 `document.body` "元素"工具 **中** 打开 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-224">In the following code sample and figure, the `document.body` opens in the **Elements** tool.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-225">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-225">Console example</span></span>  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="检查元素并检查 () " lightbox="../media/console-inspect-document-body.msft.png":::
   <span data-ttu-id="8ad8a-227">使用 检查元素</span><span class="sxs-lookup"><span data-stu-id="8ad8a-227">Inspecting an element with</span></span> `inspect()`  
:::image-end:::  

<span data-ttu-id="8ad8a-228">传递要检查的方法时，该方法将在 **"** 源"工具中打开网页供你检查。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-228">When passing a method to inspect, the method opens the webpage in the **Sources** tool for you to inspect.</span></span>  

---  

## <a name="geteventlisteners"></a><span data-ttu-id="8ad8a-229">getEventListeners</span><span class="sxs-lookup"><span data-stu-id="8ad8a-229">getEventListeners</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-230">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-230">Console syntax</span></span>  

```console
getEventListeners(object)
```  

<span data-ttu-id="8ad8a-231">此命令返回在指定对象上注册的事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-231">This command returns the event listeners registered on the specified object.</span></span>  <span data-ttu-id="8ad8a-232">返回值是包含每个已注册事件类型 \ (（如 或 `click` `keydown` \) ）的数组的对象。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-232">The return value is an object that contains an array for each registered event type \(such as `click` or `keydown`\).</span></span>  <span data-ttu-id="8ad8a-233">每个数组的成员是描述为每种类型注册的侦听器的对象。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-233">The members of each array are objects that describe the listener registered for each type.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-234">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-234">Console example</span></span>  

<span data-ttu-id="8ad8a-235">下面的代码段和图列出了在 对象上注册的所有事件 `document` 侦听器。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-235">In the following code snippet and figure, all of the event listeners registered on the `document` object are listed.</span></span>  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="使用 getEventListeners 文档库 (输出) " lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   <span data-ttu-id="8ad8a-237">使用 的结果</span><span class="sxs-lookup"><span data-stu-id="8ad8a-237">The result of using</span></span> `getEventListeners(document)`  
:::image-end:::  

<span data-ttu-id="8ad8a-238">如果指定对象上注册了多个侦听器，则数组将包含每个侦听器的成员。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-238">If more than one listener is registered on the specified object, then the array contains a member for each listener.</span></span>  <span data-ttu-id="8ad8a-239">下图中，在 事件的 元素上注册了两 `document` 个 `click` 事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-239">In the following figure, two event listeners are registered on the `document` element for the `click` event.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="多个侦听器" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   <span data-ttu-id="8ad8a-241">多个侦听器</span><span class="sxs-lookup"><span data-stu-id="8ad8a-241">Multiple listeners</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-242">可以进一步展开以下每个对象来浏览属性。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-242">You may further expand each of the following objects to explore the properties.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="侦听器对象的扩展视图" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   <span data-ttu-id="8ad8a-244">侦听器对象的扩展视图</span><span class="sxs-lookup"><span data-stu-id="8ad8a-244">Expanded view of listener object</span></span>  
:::image-end:::  

---  

## <a name="keys"></a><span data-ttu-id="8ad8a-245">键</span><span class="sxs-lookup"><span data-stu-id="8ad8a-245">keys</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-246">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-246">Console syntax</span></span>  

```console
keys(object)
```  

<span data-ttu-id="8ad8a-247">此命令返回一个数组，其中包含属于指定对象的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-247">This command returns an array containing the names of the properties belonging to the specified object.</span></span>  <span data-ttu-id="8ad8a-248">若要获取相同属性的关联值，请使用 `values()` 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-248">To get the associated values of the same properties, use `values()`.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-249">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-249">Console example</span></span>  

<span data-ttu-id="8ad8a-250">例如，假设应用程序定义了以下对象。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-250">For example, suppose your application defined the following object.</span></span>  

```console
var player1 = {"name": "Ted", "level": 42}
```  

<span data-ttu-id="8ad8a-251">在下面的代码示例和图中，为了简单起见，在键入和在控制台中) 在全局命名空间 \ (中定义了 `player1` `keys(player1)` `values(player1)` 结果假定。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-251">In the following code samples and figure, the result assumes `player1` was defined in the global namespace \(for simplicity\) before you type `keys(player1)` and `values(player1)` in the console.</span></span>  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="键 () 和值 () 命令" lightbox="../media/console-keys-values.msft.png":::
   <span data-ttu-id="8ad8a-253">和 `keys()` `values()` 命令</span><span class="sxs-lookup"><span data-stu-id="8ad8a-253">The `keys()` and `values()` commands</span></span>  
:::image-end:::  

---  

## <a name="monitor"></a><span data-ttu-id="8ad8a-254">监视器</span><span class="sxs-lookup"><span data-stu-id="8ad8a-254">monitor</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-255">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-255">Console syntax</span></span>  

```console
monitor(method)
```  

<span data-ttu-id="8ad8a-256">此命令向控制台记录一条消息，指示方法名称以及作为请求的一部分传递给方法的参数。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-256">This command logs a message to the console that indicates the method name along with the arguments passed to the method as part of a request.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-257">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-257">Console example</span></span>  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="监视器 () 方法" lightbox="../media/console-function-monitor-sum.msft.png":::
   <span data-ttu-id="8ad8a-259">`monitor()`方法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-259">The `monitor()` method</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-260">用于 `unmonitor(method)` 结束监视。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-260">Use `unmonitor(method)` to end monitoring.</span></span>  

---  

## <a name="monitorevents"></a><span data-ttu-id="8ad8a-261">monitorEvents</span><span class="sxs-lookup"><span data-stu-id="8ad8a-261">monitorEvents</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-262">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-262">Console syntax</span></span>  

```console
monitorEvents(object[, events])
```  

<span data-ttu-id="8ad8a-263">当指定对象上发生指定事件之一时，该事件对象将记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-263">When one of the specified events occurs on the specified object, the event object is logged to the console.</span></span>  <span data-ttu-id="8ad8a-264">可以指定要监视的单个事件、事件数组或映射到预定义的事件集合的泛型事件类型之一。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-264">You may specify a single event to monitor, an array of events, or one of the generic events types that are mapped to a predefined collection of events.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-265">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-265">Console example</span></span>  

<span data-ttu-id="8ad8a-266">查看以下代码示例和图。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-266">Review the following code sample and figure.</span></span>  

<span data-ttu-id="8ad8a-267">下面监视 window 对象上的所有调整大小事件。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-267">The following monitors all resize events on the window object.</span></span>  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="监视窗口大小事件" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   <span data-ttu-id="8ad8a-269">监视窗口大小事件</span><span class="sxs-lookup"><span data-stu-id="8ad8a-269">Monitoring window resize events</span></span>  
:::image-end:::  

<span data-ttu-id="8ad8a-270">以下代码段定义一个数组，用于监视窗口对象上的 和 `resize` `scroll` 事件。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-270">The following code snippet defines an array to monitor both `resize` and `scroll` events on the window object.</span></span>  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

<span data-ttu-id="8ad8a-271">还可以指定一种可用的事件类型，即映射到预定义的事件集的字符串。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-271">You may also specify one of the available types of events, strings that map to predefined sets of events.</span></span>  <span data-ttu-id="8ad8a-272">下表显示可用的事件类型和关联的事件映射。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-272">The following table displays the available event types and the associated event mappings.</span></span>  

| <span data-ttu-id="8ad8a-273">事件类型</span><span class="sxs-lookup"><span data-stu-id="8ad8a-273">Event type</span></span> | <span data-ttu-id="8ad8a-274">相应的映射事件</span><span class="sxs-lookup"><span data-stu-id="8ad8a-274">Corresponding mapped events</span></span> |  
|:--- |:--- |  
| `mouse` | <span data-ttu-id="8ad8a-275">"click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mouseover"、"mouseup"、"mousewheel"</span><span class="sxs-lookup"><span data-stu-id="8ad8a-275">"click", "dblclick", "mousedown", "mousemove", "mouseout", "mouseover", "mouseup", "mousewheel"</span></span> |  
| `key` | <span data-ttu-id="8ad8a-276">"keydown"、"keypress"、"keyup"、"textInput"</span><span class="sxs-lookup"><span data-stu-id="8ad8a-276">"keydown", "keypress", "keyup", "textInput"</span></span> |  
| `touch` | <span data-ttu-id="8ad8a-277">"touchcancel"、"touchend"、"touchmove"、"touchstart"</span><span class="sxs-lookup"><span data-stu-id="8ad8a-277">"touchcancel", "touchend", "touchmove", "touchstart"</span></span> |  
| `control` | <span data-ttu-id="8ad8a-278">"blur"、"change"、"focus"、"reset"、"resize"、"scroll"、"select"、"submit"、"zoom"</span><span class="sxs-lookup"><span data-stu-id="8ad8a-278">"blur", "change", "focus", "reset", "resize", "scroll", "select", "submit", "zoom"</span></span> |  

<span data-ttu-id="8ad8a-279">在下面的代码示例中，当前在 Elements 工具中选择了与输入文本字段上的事件 `key` `key` 对应的 **事件** 类型。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-279">In the following code sample, the `key` event type corresponding to `key` events on an input text field are currently chosen in the **Elements** tool.</span></span>  

```console
monitorEvents($0, "key");
```  

<span data-ttu-id="8ad8a-280">下图显示了在文本字段中键入字符后的示例输出。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-280">In the following figure, the sample output after typing a character in the text field is displayed.</span></span>  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="监视关键事件" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   <span data-ttu-id="8ad8a-282">监视关键事件</span><span class="sxs-lookup"><span data-stu-id="8ad8a-282">Monitoring key events</span></span>  
:::image-end:::  

---  

## <a name="profile"></a><span data-ttu-id="8ad8a-283">profile</span><span class="sxs-lookup"><span data-stu-id="8ad8a-283">profile</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-284">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-284">Console syntax</span></span>  

```console
profile([name])
```  

<span data-ttu-id="8ad8a-285">此命令使用可选名称启动 JavaScript CPU 分析会话。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-285">This command starts a JavaScript CPU profiling session with an optional name.</span></span>  <span data-ttu-id="8ad8a-286">[profileEnd () ](#profileend)方法完成配置文件，并显示内存工具**中**的结果。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-286">The [profileEnd()](#profileend) method completes the profile and displays the results in the **Memory** tool.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJsRuntime].  -->  

### <a name="console-example"></a><span data-ttu-id="8ad8a-287">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-287">Console example</span></span>  

1.  <span data-ttu-id="8ad8a-288">运行 `profile()` 方法以开始分析。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-288">Run the `profile()` method to start profiling.</span></span>  
    
    ```console
    profile("My profile")
    ```  
    
1.  <span data-ttu-id="8ad8a-289">运行 [profileEnd () ](#profileend) 方法停止分析和在内存工具 **中显示** 结果。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-289">Run the [profileEnd()](#profileend) method to stop profiling and display the results in the **Memory** tool.</span></span>  

<span data-ttu-id="8ad8a-290">配置文件也可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-290">Profiles may also be nested.</span></span>  <span data-ttu-id="8ad8a-291">在下面的代码示例和图中，无论顺序如何，结果都是相同的。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-291">In the following code samples and figure, the result is the same whatever the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> <span data-ttu-id="8ad8a-292">多个 CPU 配置文件可以同时运行，并且不需要按照创建顺序关闭每个配置文件。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-292">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

---  

## <a name="profileend"></a><span data-ttu-id="8ad8a-293">profileEnd</span><span class="sxs-lookup"><span data-stu-id="8ad8a-293">profileEnd</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-294">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-294">Console syntax</span></span>  

```console
profileEnd([name])
```  

<span data-ttu-id="8ad8a-295">此命令完成 JavaScript CPU 分析会话，并显示内存工具 **中** 的结果。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-295">This command completes a JavaScript CPU profiling session and displays the results in the **Memory** tool.</span></span>  <span data-ttu-id="8ad8a-296">必须运行配置文件 [ () ](#profile) 方法。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-296">You must be running the [profile()](#profile) method.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJsRuntime].  -->  

### <a name="console-example"></a><span data-ttu-id="8ad8a-297">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-297">Console example</span></span>  

1.  <span data-ttu-id="8ad8a-298">运行 [配置文件 () ](#profile) 方法开始分析。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-298">Run the [profile()](#profile) method to start profiling.</span></span>  
1.  <span data-ttu-id="8ad8a-299">运行 `profileEnd()` 方法以停止分析，在内存工具中 **显示** 结果。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-299">Run the `profileEnd()` method to stop profiling and display the results in the **Memory** tool.</span></span>  
    
    ```console
    profileEnd("My profile")
    ```  

<span data-ttu-id="8ad8a-300">配置文件也可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-300">Profiles may also be nested.</span></span>  <span data-ttu-id="8ad8a-301">在下面的代码示例和图中，无论顺序如何，结果都是相同的。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-301">In the following code sample and figure, the result is the same whatever the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

<span data-ttu-id="8ad8a-302">结果在内存工具中显示为堆 **快照** 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-302">The result appears as a Heap Snapshot in the **Memory** tool.</span></span>  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="分组配置文件" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   <span data-ttu-id="8ad8a-304">分组配置文件</span><span class="sxs-lookup"><span data-stu-id="8ad8a-304">Grouped profiles</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="8ad8a-305">多个 CPU 配置文件可以同时运行，并且不需要按照创建顺序关闭每个配置文件。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-305">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

---  

## <a name="queryobjects"></a><span data-ttu-id="8ad8a-306">queryObjects</span><span class="sxs-lookup"><span data-stu-id="8ad8a-306">queryObjects</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-307">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-307">Console syntax</span></span>  

```console
queryObjects(Constructor)
```  

<span data-ttu-id="8ad8a-308">此命令返回使用指定构造函数创建的对象数组。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-308">This command returns an array of objects created with the specified constructor.</span></span>  <span data-ttu-id="8ad8a-309">的范围 `queryObjects()` 是控制台 中当前选择的运行时 **上下文**。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-309">The scope of `queryObjects()` is the currently chosen runtime context in the **Console**.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-310">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-310">Console example</span></span>  

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      <span data-ttu-id="8ad8a-311">返回所有 `Promises` 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-311">Returns all `Promises`.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      <span data-ttu-id="8ad8a-312">返回所有 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-312">Returns all HTML elements.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      <span data-ttu-id="8ad8a-313">返回使用 实例化的所有对象 `new functionName()` 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-313">Returns all objects that were instantiated using `new functionName()`.</span></span>  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a><span data-ttu-id="8ad8a-314">table</span><span class="sxs-lookup"><span data-stu-id="8ad8a-314">table</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-315">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-315">Console syntax</span></span>  

```console
table(data[, columns])
```  

<span data-ttu-id="8ad8a-316">此命令根据数据对象（列标题为可选）使用表格式记录对象数据。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-316">This command logs object data with table formatting based upon the data object in with optional column headings.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-317">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-317">Console example</span></span>  

<span data-ttu-id="8ad8a-318">下面的代码示例和图显示了使用控制台中的表的名称列表。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-318">In the following code sample and figure, a list of names using a table in the console is displayed.</span></span>  

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
   <span data-ttu-id="8ad8a-320">方法 `table()` 的结果</span><span class="sxs-lookup"><span data-stu-id="8ad8a-320">The result of the `table()` method</span></span>  
:::image-end:::  

---  

## <a name="undebug"></a><span data-ttu-id="8ad8a-321">undebug</span><span class="sxs-lookup"><span data-stu-id="8ad8a-321">undebug</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-322">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-322">Console syntax</span></span>  

```console
undebug(method)
```  

<span data-ttu-id="8ad8a-323">此命令停止对指定方法的调试。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-323">This command stops the debug of the specified method.</span></span> <span data-ttu-id="8ad8a-324">因此，当请求该方法时，将不再调用调试器。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-324">So when the method is requested, the debugger is no longer invoked.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-325">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-325">Console example</span></span>  

```console
undebug(getData);
```  

---  

## <a name="unmonitor"></a><span data-ttu-id="8ad8a-326">unmonitor</span><span class="sxs-lookup"><span data-stu-id="8ad8a-326">unmonitor</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-327">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-327">Console syntax</span></span>  

```console
unmonitor(method)
```  

<span data-ttu-id="8ad8a-328">此命令停止对指定方法的监视。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-328">This command stops the monitoring of the specified method.</span></span>  <span data-ttu-id="8ad8a-329">此方法与监视器和 () [一起 ](#monitor) 使用。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-329">This method is used in concert with the [monitor()](#monitor) method.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-330">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-330">Console example</span></span>  

```console
unmonitor(getData);
```  

---  

## <a name="unmonitorevents"></a><span data-ttu-id="8ad8a-331">unmonitorEvents</span><span class="sxs-lookup"><span data-stu-id="8ad8a-331">unmonitorEvents</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-332">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-332">Console syntax</span></span>  

```console
unmonitorEvents(object[, events])
```  

<span data-ttu-id="8ad8a-333">此命令停止监视指定对象和事件的事件。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-333">This command stops monitoring events for the specified object and events.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-334">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-334">Console example</span></span>  

<span data-ttu-id="8ad8a-335">例如，以下代码段停止窗口对象上的所有事件监视。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-335">For example, the following code snippet stops all event monitoring on the window object.</span></span>  

```console
unmonitorEvents(window);
```  

<span data-ttu-id="8ad8a-336">还可以有选择地停止监视对象上的特定事件。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-336">You may also selectively stop monitoring specific events on an object.</span></span>  <span data-ttu-id="8ad8a-337">例如，以下代码开始监视当前选择的元素上的所有事件，然后停止监视 `mouse` `mousemove` 事件 \ (也许以减少控制台输出\) 。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-337">For example, the following code starts monitoring all `mouse` events on the currently chosen element, and then stops monitoring `mousemove` events \(perhaps to reduce noise in the console output\).</span></span>  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

---  

## <a name="values"></a><span data-ttu-id="8ad8a-338">values</span><span class="sxs-lookup"><span data-stu-id="8ad8a-338">values</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="8ad8a-339">控制台语法</span><span class="sxs-lookup"><span data-stu-id="8ad8a-339">Console syntax</span></span>  

```console
values(object)
```  

<span data-ttu-id="8ad8a-340">此命令返回一个数组，其中包含属于指定对象的所有属性的值。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-340">This command returns an array containing the values of all properties belonging to the specified object.</span></span>  

### <a name="console-example"></a><span data-ttu-id="8ad8a-341">控制台示例</span><span class="sxs-lookup"><span data-stu-id="8ad8a-341">Console example</span></span>  

```console
values(object);
```  

---  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="8ad8a-342">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="8ad8a-342">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="8ad8a-352">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-352">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8ad8a-353">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/utilities)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-353">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/utilities) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8ad8a-355">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8ad8a-355">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
