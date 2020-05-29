---
description: 使用控制台命令行与正在运行的页面交互
title: DevTools-Console-命令行
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、控制台命令行
ms.custom: seodec18
ms.openlocfilehash: c661736e5ea264f60279c89cfa0f9c55361d2288
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564322"
---
# <span data-ttu-id="ec09d-104">控制台命令行</span><span class="sxs-lookup"><span data-stu-id="ec09d-104">Console command line</span></span>

<span data-ttu-id="ec09d-105">使用 Console 命令行查看和更改页面上的值，并在使用 Visual Studio [*IntelliSense*](/visualstudio/ide/javascript-intellisense)自动代码完成时即时执行调试代码。</span><span class="sxs-lookup"><span data-stu-id="ec09d-105">Use the Console command line to view and change values on a page and execute debug code on the fly, all while taking advantage of Visual Studio [*IntelliSense*](/visualstudio/ide/javascript-intellisense) auto code completion.</span></span> 

<span data-ttu-id="ec09d-106">只需在命令行提示符处输入任何有效的 JavaScript，然后按 `Enter` 执行即可。</span><span class="sxs-lookup"><span data-stu-id="ec09d-106">Simply enter any valid JavaScript at the command line prompt and press `Enter` to execute.</span></span> <span data-ttu-id="ec09d-107">对于多行输入，用 `Shift+Enter` 来添加换行符。</span><span class="sxs-lookup"><span data-stu-id="ec09d-107">For multi-line input use `Shift+Enter` to add a line-break.</span></span> <span data-ttu-id="ec09d-108">使用 `Up` 和 `Down` 箭头键浏览你在当前 DevTools 会话期间输入的上一个控制台命令。</span><span class="sxs-lookup"><span data-stu-id="ec09d-108">Use the `Up` and `Down` arrow keys to navigate through previous console commands you entered during the current  DevTools session.</span></span> <span data-ttu-id="ec09d-109">除了标准 JavaScript 和[控制台 API](./console-api.md)，控制台还支持以下命令：</span><span class="sxs-lookup"><span data-stu-id="ec09d-109">In addition to standard JavaScript and the [Console API](./console-api.md), the Console also supports the following commands for:</span></span>

 - [<span data-ttu-id="ec09d-110">选择 DOM 对象</span><span class="sxs-lookup"><span data-stu-id="ec09d-110">Selecting DOM objects</span></span>](#dom-selectors)
 - [<span data-ttu-id="ec09d-111">检查对象属性</span><span class="sxs-lookup"><span data-stu-id="ec09d-111">Inspecting object properties</span></span>](#object-inspection)
 - [<span data-ttu-id="ec09d-112">查找给定对象上的所有事件侦听器</span><span class="sxs-lookup"><span data-stu-id="ec09d-112">Finding all the event listeners on a given object</span></span>](#event-listeners)

<span data-ttu-id="ec09d-113">在命令行中输入的脚本在当前所选窗口的[全局范围](/scripting/javascript/advanced/variable-scope-javascript)内执行，除非页面在断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="ec09d-113">Script entered in the command line executes in the [global scope](/scripting/javascript/advanced/variable-scope-javascript) of the currently selected window, unless the page is paused at a breakpoint.</span></span> <span data-ttu-id="ec09d-114">在暂停页面时输入的控制台命令将在调用堆栈内当前函数的[本地范围](/scripting/javascript/advanced/variable-scope-javascript)内执行。</span><span class="sxs-lookup"><span data-stu-id="ec09d-114">Console commands entered while the page is paused will execute in the [local scope](/scripting/javascript/advanced/variable-scope-javascript) of the current function within the call stack.</span></span>

<span data-ttu-id="ec09d-115">控制台的 "**目标**执行上下文" 下拉列表位于 "控制台输出" 区域的正上方。</span><span class="sxs-lookup"><span data-stu-id="ec09d-115">The Console has a **Target** execution context drop-down just above the Console output area.</span></span> <span data-ttu-id="ec09d-116">默认选择是 **_top**的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="ec09d-116">The default selection is the top-level document, **_top**.</span></span> <span data-ttu-id="ec09d-117">文档或运行扩展中的任何 iframe 也将显示为选项，使你可以在这些范围内交替运行命令。</span><span class="sxs-lookup"><span data-stu-id="ec09d-117">Any iframes in the document or running extensions will also appear as options, allowing you to alternately run commands within those scopes.</span></span>

## <span data-ttu-id="ec09d-118">DOM 选择器</span><span class="sxs-lookup"><span data-stu-id="ec09d-118">DOM selectors</span></span>
<span data-ttu-id="ec09d-119">这些控制台选择器提供简单的 shorthands 来快速访问 DOM 中的对象：</span><span class="sxs-lookup"><span data-stu-id="ec09d-119">These console selectors provide simple shorthands for quickly accessing objects within the DOM:</span></span>

### <span data-ttu-id="ec09d-120">$ （*CSS 选择器字符串*）</span><span class="sxs-lookup"><span data-stu-id="ec09d-120">$(*CSS selector string*)</span></span>
<span data-ttu-id="ec09d-121">返回文档中与指定的[CSS 选择器](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)（或逗号分隔的选择器组）字符串匹配的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="ec09d-121">Returns the first element within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="ec09d-122">[QuerySelector （）](https://developer.mozilla.org/docs/Web/API/Document/querySelector)的速记。</span><span class="sxs-lookup"><span data-stu-id="ec09d-122">Shorthand for [document.querySelector()](https://developer.mozilla.org/docs/Web/API/Document/querySelector).</span></span>

<span data-ttu-id="ec09d-123">示例：打开控制台并键入， `$('#main')` 以返回 `id='main'` 此页面上的 div 对象。</span><span class="sxs-lookup"><span data-stu-id="ec09d-123">Example: Open the console and type `$('#main')` to return the div object with `id='main'` on this page.</span></span>

!["$" 选择器示例用法](../media/console_cmd_$.png)

### <span data-ttu-id="ec09d-125">$ $ （*CSS 选择器字符串*）</span><span class="sxs-lookup"><span data-stu-id="ec09d-125">$$(*CSS selector string*)</span></span>
<span data-ttu-id="ec09d-126">返回文档中与指定的[CSS 选择器](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)（或逗号分隔的选择器组）字符串匹配的元素数组。</span><span class="sxs-lookup"><span data-stu-id="ec09d-126">Returns an array of elements within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="ec09d-127">[QuerySelectorAll （）](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)的速记。</span><span class="sxs-lookup"><span data-stu-id="ec09d-127">Shorthand for [document.querySelectorAll()](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll).</span></span>

<span data-ttu-id="ec09d-128">示例：打开控制台并键入， `$$('.container')` 以返回此页面上的所有 div 对象 `class='container'` 。</span><span class="sxs-lookup"><span data-stu-id="ec09d-128">Example: Open the console and type `$$('.container')` to return all the div objects with `class='container'` on this page.</span></span>

![使用 "$ $" 选择器的示例](../media/console_cmd_$$.png)

### <span data-ttu-id="ec09d-130">$0、$1、$2,.。。</span><span class="sxs-lookup"><span data-stu-id="ec09d-130">$0, $1, $2,...</span></span>
<span data-ttu-id="ec09d-131">返回在 "[**元素**](../elements.md)" 面板中选择的最后一个元素，其中 `$0` 表示当前选定 `$1` 的项目，是选定项目之前的项目。</span><span class="sxs-lookup"><span data-stu-id="ec09d-131">Returns the last elements selected in the [**Elements**](../elements.md) panel, where `$0` represents the currently selected item, `$1` was the selected item before that, and so on.</span></span>

<span data-ttu-id="ec09d-132">示例：打开 DevTools 到 "**元素**" 选项卡，按 `CTRL + B` 激活 "**选择元素**" 工具，然后通过鼠标单击此页面上的某些区域。</span><span class="sxs-lookup"><span data-stu-id="ec09d-132">Example: Open  DevTools to the **Elements** tab, press `CTRL + B` to activate the **Select element** tool and click some area on this page with your mouse.</span></span> <span data-ttu-id="ec09d-133">现在打开控制台，然后键入 `$0` 以返回刚刚单击的元素。</span><span class="sxs-lookup"><span data-stu-id="ec09d-133">Now open the Console and type `$0` to return the element you just clicked.</span></span>

!["$0" 选择器示例用法](../media/console_cmd_$0.png)

### <span data-ttu-id="ec09d-135">$x （*XPath 表达式*）</span><span class="sxs-lookup"><span data-stu-id="ec09d-135">$x(*XPath expression*)</span></span>
<span data-ttu-id="ec09d-136">返回由指定[XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript)表达式匹配的元素数组。</span><span class="sxs-lookup"><span data-stu-id="ec09d-136">Returns an array of elements matched by the specified [XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) expression.</span></span> 

<span data-ttu-id="ec09d-137">示例：打开控制台并键入， `$x('//script[@defer]')` 返回 `<script>` 此页面上包含属性的所有元素 `defer` 。</span><span class="sxs-lookup"><span data-stu-id="ec09d-137">Example: Open the console and type `$x('//script[@defer]')` to return all the `<script>` elements on this page that contain a `defer` attribute.</span></span>

![使用 "$x" 选择器的示例](../media/console_cmd_$x.png)

## <span data-ttu-id="ec09d-139">对象检查</span><span class="sxs-lookup"><span data-stu-id="ec09d-139">Object inspection</span></span>

<span data-ttu-id="ec09d-140">这些命令提供了检查对象属性的快速方法。</span><span class="sxs-lookup"><span data-stu-id="ec09d-140">These commands provide quick ways to inspect the properties of an object.</span></span> <span data-ttu-id="ec09d-141">指定的对象必须在全局命名空间中定义或在调试器的当前范围内定义。</span><span class="sxs-lookup"><span data-stu-id="ec09d-141">The specified object must either be defined in the global namespace or the current scope of the debugger.</span></span>

### <span data-ttu-id="ec09d-142">dir （*对象*）</span><span class="sxs-lookup"><span data-stu-id="ec09d-142">dir(*object*)</span></span>
<span data-ttu-id="ec09d-143">返回指定对象的属性的树视图列表。</span><span class="sxs-lookup"><span data-stu-id="ec09d-143">Returns a tree view list of properties for the specified object.</span></span>

<span data-ttu-id="ec09d-144">示例：打开控制台并键入， `dir(document)` 以查看代表此页面的 document 对象的对象属性。</span><span class="sxs-lookup"><span data-stu-id="ec09d-144">Example: Open the console and type `dir(document)` to see the object properties for the document object representing this page.</span></span>

!["Dir" 方法的使用示例](../media/console_cmd_dir.png)

### <span data-ttu-id="ec09d-146">键（*对象*）</span><span class="sxs-lookup"><span data-stu-id="ec09d-146">keys(*object*)</span></span>
<span data-ttu-id="ec09d-147">返回附加到指定对象的属性名称数组。</span><span class="sxs-lookup"><span data-stu-id="ec09d-147">Returns an array of property names attached to the specified object.</span></span>

<span data-ttu-id="ec09d-148">示例：打开控制台并键入， `keys(window)` 返回在全局窗口对象上定义的所有属性。</span><span class="sxs-lookup"><span data-stu-id="ec09d-148">Example: Open the console and type `keys(window)` to return all of the properties defined on the global window object.</span></span>

!["Keys" 方法的用法示例](../media/console_cmd_keys.png)

### <span data-ttu-id="ec09d-150">值（*对象*）</span><span class="sxs-lookup"><span data-stu-id="ec09d-150">values(*object*)</span></span>
<span data-ttu-id="ec09d-151">返回附加到指定对象的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="ec09d-151">Returns an array of property values attached to the specified object.</span></span>

<span data-ttu-id="ec09d-152">示例：打开控制台并键入 `values(window)` ，返回在全局窗口对象上定义的所有属性（键）的值。</span><span class="sxs-lookup"><span data-stu-id="ec09d-152">Example: Open the console and type `values(window)` to return the values of all the properties (keys) defined on the global window object.</span></span>

!["Values" 方法的使用示例](../media/console_cmd_values.png)

## <span data-ttu-id="ec09d-154">事件侦听器</span><span class="sxs-lookup"><span data-stu-id="ec09d-154">Event listeners</span></span>

<span data-ttu-id="ec09d-155">此命令允许你检查注册到给定对象的事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec09d-155">This command allows you to inspect the event listeners registered to a given object.</span></span> <span data-ttu-id="ec09d-156">指定的对象必须在全局命名空间中定义或在调试器的当前范围内定义。</span><span class="sxs-lookup"><span data-stu-id="ec09d-156">The specified object must either be defined in the global namespace or the current scope of the  debugger.</span></span>

### <span data-ttu-id="ec09d-157">getEventListeners （*对象*）</span><span class="sxs-lookup"><span data-stu-id="ec09d-157">getEventListeners(*object*)</span></span>
<span data-ttu-id="ec09d-158">返回一个对象，其中包含给定对象上每个已注册事件类型的键。</span><span class="sxs-lookup"><span data-stu-id="ec09d-158">Returns an object containing a key for each registered event type on the given object.</span></span> <span data-ttu-id="ec09d-159">每个键的值是一个事件侦听器数组及其相关信息。</span><span class="sxs-lookup"><span data-stu-id="ec09d-159">The value of each key is an array of event listeners and their related info.</span></span> 

<span data-ttu-id="ec09d-160">示例：打开 "控制台" 和 "键入" `getEventListeners(document)` 以查看此页面上的 "文档" 对象上注册的所有事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec09d-160">Example: Open the console and type `getEventListeners(document)` to see all the event listeners registered on the document object of this page.</span></span>

![使用 "getEventListeners" 方法的示例](../media/console_cmd_getEventListeners.png)
