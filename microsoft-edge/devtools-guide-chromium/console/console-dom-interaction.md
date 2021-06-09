---
description: 如何使用控制台工具在浏览器中与当前网页进行交互的概述
title: 使用控制台与 DOM 交互
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 56ce6b1d8f1ad98eeb9c141c2e9b002e7679d7de
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597013"
---
# <a name="use-the-console-to-interact-with-the-dom"></a><span data-ttu-id="80a2d-104">使用控制台与 DOM 交互</span><span class="sxs-lookup"><span data-stu-id="80a2d-104">Use the Console to interact with the DOM</span></span>

<span data-ttu-id="80a2d-105">控制台 **工具** 并不仅仅是用于 [日志记录信息][DevtoolsConsoleConsoleLog] 或 [运行任意 JavaScript][DevtoolsConsoleConsoleJavascript]。</span><span class="sxs-lookup"><span data-stu-id="80a2d-105">The **Console** tool isn't only for [logging information][DevtoolsConsoleConsoleLog] or to [run arbitrary JavaScript][DevtoolsConsoleConsoleJavascript].</span></span>  <span data-ttu-id="80a2d-106">这也是在浏览器中与网页交互的一种很好的方法。</span><span class="sxs-lookup"><span data-stu-id="80a2d-106">It also is a great way to interact with the webpage in the browser.</span></span>  <span data-ttu-id="80a2d-107">请考虑它是 Inspect 工具的 **脚本环境版本** 。</span><span class="sxs-lookup"><span data-stu-id="80a2d-107">Consider it a script-environment version of the **Inspect** tool.</span></span>  

## <a name="read-from-the-dom"></a><span data-ttu-id="80a2d-108">从 DOM 读取</span><span class="sxs-lookup"><span data-stu-id="80a2d-108">Read from the DOM</span></span>

<span data-ttu-id="80a2d-109">若要引用网页的标题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="80a2d-109">To reference the header of the webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="80a2d-110">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="80a2d-110">Open the **Console**.</span></span>
    *   <span data-ttu-id="80a2d-111">选择 `Control` + `Shift` + `J` \(Windows、Linux\) 或 `Command` + `Option` + `J` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="80a2d-111">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
1.  <span data-ttu-id="80a2d-112">在控制台中键入或复制并粘贴以下 **代码段**。</span><span class="sxs-lookup"><span data-stu-id="80a2d-112">Type or copy and paste the following code snippet in the **Console**.</span></span>  
    
    ```javascript
    document.querySelector('header')
    ```  
    
:::image type="complex" source="../media/console-dom-get-reference.msft.png" alt-text="若要在控制台中获取对标头的引用，请使用 document.querySelector" lightbox="../media/console-dom-get-reference.msft.png":::
    <span data-ttu-id="80a2d-114">若要在控制台中获取对标头的引用，请使用</span><span class="sxs-lookup"><span data-stu-id="80a2d-114">To get a reference to the header in console, use</span></span> `document.querySelector`  
:::image-end:::  

<span data-ttu-id="80a2d-115">如果选择鼠标 `Shift` + `Tab` 光标或将鼠标光标移到 HTML 结果上，DevTools 会突出显示标头。</span><span class="sxs-lookup"><span data-stu-id="80a2d-115">If you select `Shift`+`Tab` or move your mouse cursor over the HTML result, DevTools highlights the header for you.</span></span>  

:::image type="complex" source="../media/console-dom-highlight-element.msft.png" alt-text="DevTools 突出显示你在控制台中选择的部分" lightbox="../media/console-dom-highlight-element.msft.png":::
    <span data-ttu-id="80a2d-117">DevTools 突出显示你在控制台中选择 **的部分**</span><span class="sxs-lookup"><span data-stu-id="80a2d-117">DevTools highlights the section you choose in the **Console**</span></span>  
:::image-end:::  

## <a name="manipulate-the-dom"></a><span data-ttu-id="80a2d-118">操作 DOM</span><span class="sxs-lookup"><span data-stu-id="80a2d-118">Manipulate the DOM</span></span>

<span data-ttu-id="80a2d-119">您也可以操作网页。</span><span class="sxs-lookup"><span data-stu-id="80a2d-119">You may manipulate the webpage, too.</span></span>  <span data-ttu-id="80a2d-120">例如，如果复制并粘贴或在控制台中键入以下内容，标题周围\*\*\*\* 将显示绿色边框。</span><span class="sxs-lookup"><span data-stu-id="80a2d-120">For example, if you copy and paste or type the following into the **Console**, a green border displays around the header.</span></span>

```javascript
document.querySelector('header').style.border = '2em solid green'
```  

:::image type="complex" source="../media/console-dom-add-border.msft.png" alt-text="若要向元素添加边框，请使用控制台" lightbox="../media/console-dom-add-border.msft.png":::
    <span data-ttu-id="80a2d-122">若要向元素添加边框，请使用 **控制台**</span><span class="sxs-lookup"><span data-stu-id="80a2d-122">To add a border to an element, use the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-123">根据网页的复杂性，可能很难找到正确的要操作的元素。</span><span class="sxs-lookup"><span data-stu-id="80a2d-123">Depending on the complexity of the webpage, It may be daunting to find the right element to manipulate.</span></span>  <span data-ttu-id="80a2d-124">但可以使用 **Inspect** 工具帮助你。</span><span class="sxs-lookup"><span data-stu-id="80a2d-124">But you may use the **Inspect** tool to help you.</span></span>  <span data-ttu-id="80a2d-125">假设你想要操作页 `Documentation` 眉中的部分。</span><span class="sxs-lookup"><span data-stu-id="80a2d-125">Say you want to manipulate the `Documentation` part in the header.</span></span>

:::image type="complex" source="../media/console-dom-highlight-documentation.msft.png" alt-text="显示你在屏幕上检查的元素" lightbox="../media/console-dom-highlight-documentation.msft.png":::
    <span data-ttu-id="80a2d-127">显示你在屏幕上检查的元素</span><span class="sxs-lookup"><span data-stu-id="80a2d-127">Display the element that you inspect on the screen</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-128">若要获取对要操作的元素的直接引用，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="80a2d-128">To get a direct reference to the element to manipulate, complete the following actions.</span></span>  

1.  <span data-ttu-id="80a2d-129">使用 **Inspect** 工具选择元素。</span><span class="sxs-lookup"><span data-stu-id="80a2d-129">Use the **Inspect** tool to choose the element.</span></span>  

    :::image type="complex" source="../media/console-dom-use-inspector-to-get-element.msft.png" alt-text="若要选择元素，请使用 Inspect 工具" lightbox="../media/console-dom-use-inspector-to-get-element.msft.png":::
        <span data-ttu-id="80a2d-131">若要选择元素，请使用 **Inspect** 工具</span><span class="sxs-lookup"><span data-stu-id="80a2d-131">To choose an element, use the **Inspect** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="80a2d-132">选择它，DevTools 跳转到 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="80a2d-132">Choose it and DevTools jumps to the **Elements** tool.</span></span>  
1.  <span data-ttu-id="80a2d-133">选择 `...` DOM 树中元素旁边的菜单。</span><span class="sxs-lookup"><span data-stu-id="80a2d-133">Choose the `...` menu next to the element in the DOM tree.</span></span>  
    
    :::image type="complex" source="../media/console-dom-overflow-menu-in-elements.msft.png" alt-text="所选元素显示在"元素"工具的 DOM 树中，选择溢出菜单以获取更多功能" lightbox="../media/console-dom-overflow-menu-in-elements.msft.png":::
        <span data-ttu-id="80a2d-135">所选元素显示在"元素"工具的 DOM **树中，** 选择溢出菜单以获取更多功能</span><span class="sxs-lookup"><span data-stu-id="80a2d-135">The chosen element displays in the DOM tree of the **Elements** tool, choose the overflow menu to get more features</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="80a2d-136">打开上下文菜单并选择 `Copy`  >  `Copy JS Path` 。</span><span class="sxs-lookup"><span data-stu-id="80a2d-136">Open the contextual menu and choose `Copy` > `Copy JS Path`.</span></span>  
    
    :::image type="complex" source="../media/console-dom-copy-JS-path.msft.png" alt-text="从"元素"工具的 DOM 树中的元素复制 JavaScript 路径" lightbox="../media/console-dom-copy-JS-path.msft.png":::
        <span data-ttu-id="80a2d-138">从"元素"工具的 DOM 树中的 **元素** 复制 JavaScript 路径</span><span class="sxs-lookup"><span data-stu-id="80a2d-138">Copy the JavaScript path from an element in the DOM tree of the **Elements** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="80a2d-139">返回到 **控制台并粘贴** 命令。</span><span class="sxs-lookup"><span data-stu-id="80a2d-139">Go back to the **Console** and paste the command.</span></span>  
    
<span data-ttu-id="80a2d-140">若要将链接文本更改为 `My Playground` ，请 `.textContent = "My Playground"` 添加到之前粘贴的命令中。</span><span class="sxs-lookup"><span data-stu-id="80a2d-140">To change the text of the link to `My Playground`, add `.textContent = "My Playground"` to the command you previously pasted.</span></span>  

:::image type="complex" source="../media/console-dom-change-content.msft.png" alt-text="使用控制台更改元素的内容" lightbox="../media/console-dom-change-content.msft.png":::
    <span data-ttu-id="80a2d-142">使用 **控制台** 更改元素的内容</span><span class="sxs-lookup"><span data-stu-id="80a2d-142">Use the **Console** to change the content of an element</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-143">使用你想要在控制台中执行的任何 JavaScript DOM **操作**。</span><span class="sxs-lookup"><span data-stu-id="80a2d-143">Use any JavaScript DOM manipulations you want to do in the **Console**.</span></span>  <span data-ttu-id="80a2d-144">为了更方便， **控制台** 提供了一些帮助程序方法。</span><span class="sxs-lookup"><span data-stu-id="80a2d-144">To make it more convenient, the **Console** comes with a few helper methods.</span></span>  

## <a name="helpful-console-utility-methods"></a><span data-ttu-id="80a2d-145">有用的控制台实用程序方法</span><span class="sxs-lookup"><span data-stu-id="80a2d-145">Helpful Console utility methods</span></span>  

<span data-ttu-id="80a2d-146">许多便利的方法和快捷方式都作为控制台 [实用程序提供][DevtoolsConsoleUtilities]给你。</span><span class="sxs-lookup"><span data-stu-id="80a2d-146">Many convenience methods and shortcuts are available to you as [Console Utilities][DevtoolsConsoleUtilities].</span></span>  <span data-ttu-id="80a2d-147">其中一些方法非常强大，也是您可能作为过去一系列语句撰写 `console.log()` 的一些内容。</span><span class="sxs-lookup"><span data-stu-id="80a2d-147">Some of the methods are incredibly powerful and are things you probably wrote as a series of `console.log()` statements in the past.</span></span>

### <a name="the-power-to-the-"></a><span data-ttu-id="80a2d-148">$ 的电源</span><span class="sxs-lookup"><span data-stu-id="80a2d-148">The power to the $</span></span>

<span data-ttu-id="80a2d-149">`$`控制台中具有特殊**功能**，你可能从 jQuery 中记住这一点。</span><span class="sxs-lookup"><span data-stu-id="80a2d-149">The `$` has special powers in **Console** and you may remember that from jQuery.</span></span>

*   `$_` <span data-ttu-id="80a2d-150">存储最后一个命令的结果。</span><span class="sxs-lookup"><span data-stu-id="80a2d-150">stores the result of the last command.</span></span>  <span data-ttu-id="80a2d-151">因此，如果你键入 `2 + 2` 并选择 `Enter` ，然后键入 ，控制台 `$_` 将显示\*\*\*\* `4` 你 。</span><span class="sxs-lookup"><span data-stu-id="80a2d-151">So, if you type `2 + 2` and select `Enter`, and then type `$_`, the **Console** displays you `4`.</span></span>
*   `$0` <span data-ttu-id="80a2d-152">`$4`是最后检查的元素的堆栈， `$0` 始终为最新元素。</span><span class="sxs-lookup"><span data-stu-id="80a2d-152">to `$4` is a stack of the last inspected elements `$0` is always the newest one.</span></span>  <span data-ttu-id="80a2d-153">因此，在上一示例中，你只需在 **Inspect** 工具中选择 元素并键入 `$0.textContent = "My Playground"` ，以获得相同的效果。</span><span class="sxs-lookup"><span data-stu-id="80a2d-153">So in the earlier example, you just chose the element in the **Inspect** tool and type `$0.textContent = "My Playground"` to get the same effect.</span></span>
*   `$x()` <span data-ttu-id="80a2d-154">允许您使用 XPATH 选择 DOM 元素。</span><span class="sxs-lookup"><span data-stu-id="80a2d-154">allows you to choose DOM elements using XPATH.</span></span>
*   `$()` <span data-ttu-id="80a2d-155">`$$()`和 是 和 的 `document.querySelector()` 较短版本 `document.querySelectorAll()` 。</span><span class="sxs-lookup"><span data-stu-id="80a2d-155">and `$$()` are shorter versions of for `document.querySelector()` and `document.querySelectorAll()`.</span></span>  
    
<span data-ttu-id="80a2d-156">例如，以下代码段检索网页 \ (中所有的链接，就像 \) 的简短内容一 `$$('a')` 样，将链接显示为可排序表以复制和粘贴到 Excel 中。 `document.querySelectorAll('a')`</span><span class="sxs-lookup"><span data-stu-id="80a2d-156">For example, the following code snippet retrieves all the links in the webpage \(as `$$('a')` is short for `document.querySelectorAll('a')`\) and displays the links as a sortable table to copy and paste, for example, into Excel.</span></span>

```javascript
console.table($$('a'),['href','text']);
```  

:::image type="complex" source="../media/console-dom-get-all-links.msft.png" alt-text="获取网页中所有的链接，将结果显示为表格" lightbox="../media/console-dom-get-all-links.msft.png":::
    <span data-ttu-id="80a2d-158">获取网页中所有的链接，将结果显示为表格</span><span class="sxs-lookup"><span data-stu-id="80a2d-158">Get all links in the webpage and display the result as a table</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-159">但是，如果你不希望显示信息，但希望获取它作为数据。</span><span class="sxs-lookup"><span data-stu-id="80a2d-159">However, if you don't want to display the information, but you want to grab it as data.</span></span>  <span data-ttu-id="80a2d-160">快捷方式 `$$('a')` 提供定位链接以及每个链接的所有属性。</span><span class="sxs-lookup"><span data-stu-id="80a2d-160">The `$$('a')` shortcut provides the anchor links and all of the properties for each one.</span></span>  <span data-ttu-id="80a2d-161">问题是您只需要链接和相关文本。</span><span class="sxs-lookup"><span data-stu-id="80a2d-161">The problem is that you only want the links and the related text.</span></span>  

:::image type="complex" source="../media/console-dom-too-much-link-information.msft.png" alt-text="$$ 快捷方式返回的信息过多" lightbox="../media/console-dom-too-much-link-information.msft.png":::
    <span data-ttu-id="80a2d-163">快捷方式 `$$` 返回的信息过多</span><span class="sxs-lookup"><span data-stu-id="80a2d-163">The `$$` shortcut returns far too much information</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-164">快捷方式 `$$` 具有一项有趣的额外功能。</span><span class="sxs-lookup"><span data-stu-id="80a2d-164">The `$$` shortcut has an interesting extra feature.</span></span>  <span data-ttu-id="80a2d-165">快捷方式为你提供所有方法，而不是返回纯 `NodeList` `document.querySelectorAll()` like `$$` `Array` 。</span><span class="sxs-lookup"><span data-stu-id="80a2d-165">Instead of returning a pure `NodeList` like `document.querySelectorAll()`, the `$$` shortcut gives you all of the `Array` methods.</span></span>  <span data-ttu-id="80a2d-166">使用 `map()` 方法将信息减少为你需要的信息。</span><span class="sxs-lookup"><span data-stu-id="80a2d-166">Use `map()` method to reduce the information to what you need.</span></span>  

```javascript
$$('a').map(a => {
    return {url: a.href, text: a.innerText}
})
```  

<span data-ttu-id="80a2d-167">代码段将返回所有链接的 Array，作为具有 `url` 和 `text` 属性的对象。</span><span class="sxs-lookup"><span data-stu-id="80a2d-167">The code snippet returns an Array of all the links as objects with `url` and `text` properties.</span></span>  

:::image type="complex" source="../media/console-dom-filter-link-data.msft.png" alt-text="使用 $$ 上的映射将信息筛选到最低" lightbox="../media/console-dom-filter-link-data.msft.png":::
    <span data-ttu-id="80a2d-169">使用 map on `$$` 将信息筛选到最低</span><span class="sxs-lookup"><span data-stu-id="80a2d-169">Use map on `$$` to filter information down to the bare minimum</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-170">您尚未完成，多个链接是网页的内部链接或具有空文本。</span><span class="sxs-lookup"><span data-stu-id="80a2d-170">You aren't done yet, several links are internal links to the webpage or have empty text.</span></span>  <span data-ttu-id="80a2d-171">使用 filter 方法可删除内部链接。</span><span class="sxs-lookup"><span data-stu-id="80a2d-171">Use the filter method to get rid of the internal links.</span></span>  

```javascript
$$('a').map(a => {
    return {text: a.innerText, url: a.href}
}).filter(a => {
    return a.text !== '' && !a.url.match('docs.microsoft.com')
})
```  

:::image type="complex" source="../media/console-dom-filter-out-empty-links.msft.png" alt-text="获取不为空且为外部的链接" lightbox="../media/console-dom-filter-out-empty-links.msft.png":::
    <span data-ttu-id="80a2d-173">获取不为空且为外部的链接</span><span class="sxs-lookup"><span data-stu-id="80a2d-173">Get the links that aren't empty and are external</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-174">如网页开始部分显示，您还可以更改这些元素。</span><span class="sxs-lookup"><span data-stu-id="80a2d-174">As displayed at the start of the webpage, you may also change these elements.</span></span>  <span data-ttu-id="80a2d-175">例如，以下代码段在所有外部链接周围创建绿色边框：</span><span class="sxs-lookup"><span data-stu-id="80a2d-175">For example, the following code snippet creates a green border around all external links:</span></span>

```javascript
$$('a[href^="https://"]').forEach(
  a => a.style.border = '1px solid green'
)
```  

:::image type="complex" source="../media/console-dom-highlight-links.msft.png" alt-text="若要突出显示所有外部链接，请在每个链接周围添加绿色边框" lightbox="../media/console-dom-highlight-links.msft.png":::
    <span data-ttu-id="80a2d-177">若要突出显示所有外部链接，请在每个链接周围添加绿色边框</span><span class="sxs-lookup"><span data-stu-id="80a2d-177">To highlight all external links, add a green border around each</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-178">使用 CSS 选择器功能，而不是编写复杂的 JavaScript 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="80a2d-178">Instead of writing complex JavaScript to filter results, use the power of CSS selectors.</span></span>  

<span data-ttu-id="80a2d-179">若要为网页上不是内嵌图像的所有图像创建 和 信息的表， `src` `alt` 请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="80a2d-179">To create a table of the `src` and `alt` information for all images on the webpage that aren't inline images, complete the following actions.</span></span>  

1.  <span data-ttu-id="80a2d-180">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="80a2d-180">Open the **Console**.</span></span>  
1.  <span data-ttu-id="80a2d-181">键入或复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="80a2d-181">Type or copy and paste the following code snippet.</span></span>  

```javascript
console.table($$('img:not([src^=data])'), ['src','alt'])
```  

:::image type="complex" source="../media/console-dom-complex-CSS-selector.msft.png" alt-text="若要选择元素，请使用复杂的 CSS 选择器" lightbox="../media/console-dom-complex-CSS-selector.msft.png":::
    <span data-ttu-id="80a2d-183">若要选择元素，请使用复杂的 CSS 选择器</span><span class="sxs-lookup"><span data-stu-id="80a2d-183">To choose elements, use a complex CSS selector</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-184">准备好进行更复杂的示例了吗？</span><span class="sxs-lookup"><span data-stu-id="80a2d-184">Ready for an even more complex example?</span></span>  <span data-ttu-id="80a2d-185">通过 markdown 生成的 HTML 网页（如本文）具有每个标题的自动 ID 值，以允许您深层链接到该部分。</span><span class="sxs-lookup"><span data-stu-id="80a2d-185">HTML webpages generated from markdown like this article, have automatic ID values for each heading to allow you to deep link to that section.</span></span>  <span data-ttu-id="80a2d-186">例如，对 `# New features` 进行更改 `<h1 id="new-features">New features</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="80a2d-186">For example, a `# New features` changes to `<h1 id="new-features">New features</h1>`.</span></span>  

<span data-ttu-id="80a2d-187">若要列出要复制和粘贴的所有自动标题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="80a2d-187">To list of all of the automatic headings to copy and paste, complete the following actions.</span></span>  

1.  <span data-ttu-id="80a2d-188">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="80a2d-188">Open the **Console**.</span></span>  
1.  <span data-ttu-id="80a2d-189">键入或复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="80a2d-189">Type or copy and paste the following code snippet.</span></span>  

```javascript
let out = '';
$$('#main [id]').filter(
    elm => {return elm.nodeName.startsWith('H')}
).forEach(elm => {
   out += elm.innerText + "\n" + 
          document.location.href + '#' +
          elm.id + "\n";
});
console.log(out);
```  

<span data-ttu-id="80a2d-190">结果是包含每个标题的内容的文本，后跟指向该标题的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="80a2d-190">The result is text that contains content for each heading followed by the full URL that points to it.</span></span>  

:::image type="complex" source="../media/console-dom-get-generated-headings.msft.png" alt-text="从网页获取所有标题和生成的 URL" lightbox="../media/console-dom-get-generated-headings.msft.png":::
    <span data-ttu-id="80a2d-192">从网页获取所有标题和生成的 URL</span><span class="sxs-lookup"><span data-stu-id="80a2d-192">Get all the headings and the generated URLs from the webpage</span></span>  
:::image-end:::  

### <a name="clean-up-with-clear-and-copy"></a><span data-ttu-id="80a2d-193">清除并复制</span><span class="sxs-lookup"><span data-stu-id="80a2d-193">Clean up with clear and copy</span></span>

<span data-ttu-id="80a2d-194">在控制台中 **开发时**，情况可能会变得混乱。</span><span class="sxs-lookup"><span data-stu-id="80a2d-194">When developing in the **Console**, things may get messy.</span></span>  <span data-ttu-id="80a2d-195">你可能会觉得在复制和粘贴时尝试选择结果感到沮丧。</span><span class="sxs-lookup"><span data-stu-id="80a2d-195">You may find it frustrating to try to choose results while you copy and paste.</span></span>  <span data-ttu-id="80a2d-196">以下两种实用程序方法可帮助您。</span><span class="sxs-lookup"><span data-stu-id="80a2d-196">The following two utility methods help you.</span></span>  

*   `copy()` <span data-ttu-id="80a2d-197">将你提供的任何内容复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="80a2d-197">copies whatever you give it to the clipboard.</span></span>  <span data-ttu-id="80a2d-198">`copy()`在将该方法与复制最后的结果混合使用时， `$_` 该方法尤其有用。</span><span class="sxs-lookup"><span data-stu-id="80a2d-198">The `copy()` method is especially useful when you mix it with `$_` that copies the last result.</span></span>
*   `clear()` <span data-ttu-id="80a2d-199">清除 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="80a2d-199">clears the **Console**.</span></span>

### <a name="read-and-monitor-events"></a><span data-ttu-id="80a2d-200">读取和监视事件</span><span class="sxs-lookup"><span data-stu-id="80a2d-200">Read and monitor events</span></span>

<span data-ttu-id="80a2d-201">Console 的另外两种有趣的 **实用程序方法处理** 事件处理。</span><span class="sxs-lookup"><span data-stu-id="80a2d-201">Two other interesting utility methods of **Console** deal with event handling.</span></span>

*   `getEventListeners(node)` <span data-ttu-id="80a2d-202">列出节点的所有事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="80a2d-202">lists all the event listeners of a node.</span></span>
*   `monitorEvents(node, events)` <span data-ttu-id="80a2d-203">监视和记录节点上发生的事件。</span><span class="sxs-lookup"><span data-stu-id="80a2d-203">monitors and logs the events that happen on a node.</span></span>

<span data-ttu-id="80a2d-204">若要列出分配给网页中第一个表单的所有事件侦听器，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="80a2d-204">To list all of the event listener assigned to the first form in the webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="80a2d-205">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="80a2d-205">Open the **Console**.</span></span>  
1.  <span data-ttu-id="80a2d-206">键入或复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="80a2d-206">Type or copy and paste the following code snippet.</span></span>  
    
    ```javascript
    getEventListeners($('form')); 
    ```  

:::image type="complex" source="../media/console-dom-get-form-events.msft.png" alt-text="获取网页中第一个表单的所有事件侦听器" lightbox="../media/console-dom-get-form-events.msft.png":::
    <span data-ttu-id="80a2d-208">获取网页中第一个表单的所有事件侦听器</span><span class="sxs-lookup"><span data-stu-id="80a2d-208">Get all events listeners for the first form in the webpage</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-209">监视时，每次对指定元素进行更改时，都会\*\*\*\* 在控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="80a2d-209">When you monitor, you to get a notification in the **Console** every time something changes to the specified elements.</span></span>  <span data-ttu-id="80a2d-210">将要侦听的事件定义为第二个参数。</span><span class="sxs-lookup"><span data-stu-id="80a2d-210">You define the events you want to listen to as a second parameter.</span></span>  <span data-ttu-id="80a2d-211">定义要监视的事件非常重要，否则将报告元素发生的任何事件。</span><span class="sxs-lookup"><span data-stu-id="80a2d-211">It is important for you to define the events that you want to monitor, otherwise any event happening to the element is reported.</span></span>

<span data-ttu-id="80a2d-212">若要每次滚动时在 **控制台** 中收到通知，请调整窗口大小，或当用户在搜索表单中输入内容时，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="80a2d-212">To get a notification in the **Console** every time you scroll, resize the window, or when the user types in the search form, complete the following actions.</span></span>  

1.  <span data-ttu-id="80a2d-213">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="80a2d-213">Open the **Console**.</span></span>  
1.  <span data-ttu-id="80a2d-214">键入或复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="80a2d-214">Type or copy and paste the following code snippet.</span></span>  
    
    ```javascript
    monitorEvents(window, ['resize', 'scroll']);
    monitorEvents($0, 'keyup');
    ```  
    
:::image type="complex" source="../media/console-dom-monitor-events.msft.png" alt-text="控制台显示窗口上发生的每个滚动事件" lightbox="../media/console-dom-monitor-events.msft.png":::
    <span data-ttu-id="80a2d-216">**控制台** 显示窗口上发生的每个滚动事件</span><span class="sxs-lookup"><span data-stu-id="80a2d-216">**Console** displays every scroll event that happens on the Window</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-217">若要记录当前选择的元素上的任何键操作，请专注于标题中的搜索表单并选择一些键。</span><span class="sxs-lookup"><span data-stu-id="80a2d-217">To log any key action on the currently chosen element, focus on the search form in the header and select some keys.</span></span>  

:::image type="complex" source="../media/console-dom-monitor-key-events.msft.png" alt-text="控制台显示窗体上发生的键更新事件" lightbox="../media/console-dom-monitor-key-events.msft.png":::
    <span data-ttu-id="80a2d-219">**控制台** `keyup` 显示窗体上发生的事件</span><span class="sxs-lookup"><span data-stu-id="80a2d-219">**Console** displays `keyup` events that happen on the form</span></span>  
:::image-end:::  

<span data-ttu-id="80a2d-220">若要停止它，请删除通过以下代码段设置的监视。</span><span class="sxs-lookup"><span data-stu-id="80a2d-220">To stop it, remove the monitoring you set using the following code snippet.</span></span>  

```javascript
unmonitorEvents(window, ['resize', 'scroll']);
unmonitorEvents($0, 'key');
```  

## <a name="reuse-dom-manipulation-scripts"></a><span data-ttu-id="80a2d-221">重用 DOM 操作脚本</span><span class="sxs-lookup"><span data-stu-id="80a2d-221">Reuse DOM manipulation scripts</span></span>

<span data-ttu-id="80a2d-222">你可能会发现从控制台操作 DOM **非常有用**。</span><span class="sxs-lookup"><span data-stu-id="80a2d-222">You may find it useful to manipulate the DOM from the **Console**.</span></span>  <span data-ttu-id="80a2d-223">你很快就会遇到控制台作为开发 **平台** 的限制。</span><span class="sxs-lookup"><span data-stu-id="80a2d-223">You may soon run into the limitations of the **Console** as a development platform.</span></span>  <span data-ttu-id="80a2d-224">好消息是，DevTools [中的"][DevtoolsSourcesIndex] 源"工具提供了功能齐全的开发环境。</span><span class="sxs-lookup"><span data-stu-id="80a2d-224">The good news is that the [Sources][DevtoolsSourcesIndex] tool in DevTools offers a fully featured development environment.</span></span>  <span data-ttu-id="80a2d-225">在 **"源** "工具中，可以完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="80a2d-225">In the **Sources** tool, you may complete the following actions.</span></span>  

*   <span data-ttu-id="80a2d-226">将控制台脚本**存储为**[代码段][DevToolsJavascriptSnippets]。</span><span class="sxs-lookup"><span data-stu-id="80a2d-226">Store your scripts for the **Console** as [Snippets][DevToolsJavascriptSnippets].</span></span>  
*   <span data-ttu-id="80a2d-227">使用键盘快捷方式或编辑器在网页中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="80a2d-227">Run the scripts in a webpage using a keyboard shortcut or the editor.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="80a2d-228">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="80a2d-228">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "作为 JavaScript 环境的控制台|Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "控制台工具控制台中的|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  

[DevToolsJavascriptSnippets]: ../javascript/snippets.md "使用 Microsoft Edge DevTools 工具在任意页面上运行 JavaScript | Microsoft Docs"  
[DevtoolsSourcesIndex]: ../sources/index.md "源工具概述 | Microsoft Docs"  
