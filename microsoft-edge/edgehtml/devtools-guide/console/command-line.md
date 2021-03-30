---
description: 使用控制台命令行与正在运行的页面交互
title: DevTools - 控制台 - 命令行
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 控制台命令行
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d7ea2bef9fa0014e4d61745636a06d508565df91
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232276"
---
# <span data-ttu-id="e04bf-104">控制台命令行</span><span class="sxs-lookup"><span data-stu-id="e04bf-104">Console command line</span></span>

<span data-ttu-id="e04bf-105">使用控制台命令行查看和更改页面上的值并同时执行调试代码，同时利用Visual Studio IntelliSense [*代码完成*](/visualstudio/ide/javascript-intellisense) 。</span><span class="sxs-lookup"><span data-stu-id="e04bf-105">Use the Console command line to view and change values on a page and execute debug code on the fly, all while taking advantage of Visual Studio [*IntelliSense*](/visualstudio/ide/javascript-intellisense) auto code completion.</span></span> 

<span data-ttu-id="e04bf-106">只需在命令行提示符处输入任何有效的 JavaScript，然后按 `Enter` 以执行。</span><span class="sxs-lookup"><span data-stu-id="e04bf-106">Simply enter any valid JavaScript at the command line prompt and press `Enter` to execute.</span></span> <span data-ttu-id="e04bf-107">对于多行输入 `Shift+Enter` ，用于添加换行符。</span><span class="sxs-lookup"><span data-stu-id="e04bf-107">For multi-line input use `Shift+Enter` to add a line-break.</span></span> <span data-ttu-id="e04bf-108">使用箭头 `Up` `Down` 键导航到当前 DevTools 会话期间输入的上一个控制台命令。</span><span class="sxs-lookup"><span data-stu-id="e04bf-108">Use the `Up` and `Down` arrow keys to navigate through previous console commands you entered during the current  DevTools session.</span></span> <span data-ttu-id="e04bf-109">除了标准 JavaScript 和 [控制台 API](./console-api.md)之外，控制台还支持以下命令：</span><span class="sxs-lookup"><span data-stu-id="e04bf-109">In addition to standard JavaScript and the [Console API](./console-api.md), the Console also supports the following commands for:</span></span>

 - [<span data-ttu-id="e04bf-110">选择 DOM 对象</span><span class="sxs-lookup"><span data-stu-id="e04bf-110">Selecting DOM objects</span></span>](#dom-selectors)
 - [<span data-ttu-id="e04bf-111">检查对象属性</span><span class="sxs-lookup"><span data-stu-id="e04bf-111">Inspecting object properties</span></span>](#object-inspection)
 - [<span data-ttu-id="e04bf-112">查找给定对象上的所有事件侦听器</span><span class="sxs-lookup"><span data-stu-id="e04bf-112">Finding all the event listeners on a given object</span></span>](#event-listeners)

<span data-ttu-id="e04bf-113">在命令行中输入的脚本将执行当前选定[](/scripting/javascript/advanced/variable-scope-javascript)窗口的全局范围，除非页面在断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="e04bf-113">Script entered in the command line executes in the [global scope](/scripting/javascript/advanced/variable-scope-javascript) of the currently selected window, unless the page is paused at a breakpoint.</span></span> <span data-ttu-id="e04bf-114">暂停页面时输入的控制台命令将在调用堆栈中的当前函数[](/scripting/javascript/advanced/variable-scope-javascript)的本地范围内执行。</span><span class="sxs-lookup"><span data-stu-id="e04bf-114">Console commands entered while the page is paused will execute in the [local scope](/scripting/javascript/advanced/variable-scope-javascript) of the current function within the call stack.</span></span>

<span data-ttu-id="e04bf-115">控制台 **在控制台输出** 区域正上方有一个目标执行上下文下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e04bf-115">The Console has a **Target** execution context drop-down just above the Console output area.</span></span> <span data-ttu-id="e04bf-116">默认选择是顶级文档 **，_top。**</span><span class="sxs-lookup"><span data-stu-id="e04bf-116">The default selection is the top-level document, **_top**.</span></span> <span data-ttu-id="e04bf-117">文档或运行扩展的任何 iframe 也将显示为选项，从而允许您在这些范围内交替运行命令。</span><span class="sxs-lookup"><span data-stu-id="e04bf-117">Any iframes in the document or running extensions will also appear as options, allowing you to alternately run commands within those scopes.</span></span>

## <span data-ttu-id="e04bf-118">DOM 选择器</span><span class="sxs-lookup"><span data-stu-id="e04bf-118">DOM selectors</span></span>
<span data-ttu-id="e04bf-119">这些控制台选择器提供了简单的简写，用于快速访问 DOM 中的对象：</span><span class="sxs-lookup"><span data-stu-id="e04bf-119">These console selectors provide simple shorthands for quickly accessing objects within the DOM:</span></span>

### <span data-ttu-id="e04bf-120">$ (\*CSS 选择器字符串) \*</span><span class="sxs-lookup"><span data-stu-id="e04bf-120">$(*CSS selector string*)</span></span>
<span data-ttu-id="e04bf-121">返回文档中与指定的 [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  选择器匹配的第一个元素 (或逗号分隔的选择器组) 字符串。</span><span class="sxs-lookup"><span data-stu-id="e04bf-121">Returns the first element within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="e04bf-122">[document.querySelector (的简写。） ](https://developer.mozilla.org/docs/Web/API/Document/querySelector)</span><span class="sxs-lookup"><span data-stu-id="e04bf-122">Shorthand for [document.querySelector()](https://developer.mozilla.org/docs/Web/API/Document/querySelector).</span></span>

<span data-ttu-id="e04bf-123">示例：打开控制台并键入 `$('#main')` 以返回此页面上的 div `id='main'` 对象。</span><span class="sxs-lookup"><span data-stu-id="e04bf-123">Example: Open the console and type `$('#main')` to return the div object with `id='main'` on this page.</span></span>

!["$"选择器的示例使用](../media/console_cmd_$.png)

### <span data-ttu-id="e04bf-125">$$ (\*CSS 选择器字符串) \*</span><span class="sxs-lookup"><span data-stu-id="e04bf-125">$$(*CSS selector string*)</span></span>
<span data-ttu-id="e04bf-126">返回文档中与指定的 [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  选择器匹配的元素数组 (或逗号分隔的选择器组) 字符串。</span><span class="sxs-lookup"><span data-stu-id="e04bf-126">Returns an array of elements within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="e04bf-127">[document.querySelectorAll () 的简写](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)。</span><span class="sxs-lookup"><span data-stu-id="e04bf-127">Shorthand for [document.querySelectorAll()](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll).</span></span>

<span data-ttu-id="e04bf-128">示例：打开控制台并键入以返回此 `$$('.container')` 页上包含 `class='container'` 的所有 div 对象。</span><span class="sxs-lookup"><span data-stu-id="e04bf-128">Example: Open the console and type `$$('.container')` to return all the div objects with `class='container'` on this page.</span></span>

!["$$"选择器的示例使用](../media/console_cmd_$$.png)

### <span data-ttu-id="e04bf-130">$0、$1、$2,...</span><span class="sxs-lookup"><span data-stu-id="e04bf-130">$0, $1, $2,...</span></span>
<span data-ttu-id="e04bf-131">返回"元素"面板中选定的[](../elements.md)最后一个元素，其中表示当前选定的项，是之前选定的项， `$0` `$1` 等等。</span><span class="sxs-lookup"><span data-stu-id="e04bf-131">Returns the last elements selected in the [**Elements**](../elements.md) panel, where `$0` represents the currently selected item, `$1` was the selected item before that, and so on.</span></span>

<span data-ttu-id="e04bf-132">示例：打开"元素"选项卡上的 DevTools，按以激活 Select 元素工具，然后使用鼠标单击此页上 `CTRL + B` 的某个区域。 </span><span class="sxs-lookup"><span data-stu-id="e04bf-132">Example: Open  DevTools to the **Elements** tab, press `CTRL + B` to activate the **Select element** tool and click some area on this page with your mouse.</span></span> <span data-ttu-id="e04bf-133">现在打开控制台并键入 `$0` 以返回你刚刚单击的元素。</span><span class="sxs-lookup"><span data-stu-id="e04bf-133">Now open the Console and type `$0` to return the element you just clicked.</span></span>

!["$0"选择器的示例使用](../media/console_cmd_$0.png)

### <span data-ttu-id="e04bf-135">$x (\*XPath 表达式) \*</span><span class="sxs-lookup"><span data-stu-id="e04bf-135">$x(*XPath expression*)</span></span>
<span data-ttu-id="e04bf-136">返回与指定的 [XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) 表达式匹配的元素数组。</span><span class="sxs-lookup"><span data-stu-id="e04bf-136">Returns an array of elements matched by the specified [XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) expression.</span></span> 

<span data-ttu-id="e04bf-137">示例：打开控制台并键入以返回此页上包含属性 `$x('//script[@defer]')` `<script>` 的所有 `defer` 元素。</span><span class="sxs-lookup"><span data-stu-id="e04bf-137">Example: Open the console and type `$x('//script[@defer]')` to return all the `<script>` elements on this page that contain a `defer` attribute.</span></span>

!["$x"选择器的示例使用](../media/console_cmd_$x.png)

## <span data-ttu-id="e04bf-139">对象检查</span><span class="sxs-lookup"><span data-stu-id="e04bf-139">Object inspection</span></span>

<span data-ttu-id="e04bf-140">这些命令提供了快速检查对象属性的方法。</span><span class="sxs-lookup"><span data-stu-id="e04bf-140">These commands provide quick ways to inspect the properties of an object.</span></span> <span data-ttu-id="e04bf-141">指定的对象必须在全局命名空间或调试器的当前作用域中定义。</span><span class="sxs-lookup"><span data-stu-id="e04bf-141">The specified object must either be defined in the global namespace or the current scope of the debugger.</span></span>

### <span data-ttu-id="e04bf-142">目录 (\*对象) \*</span><span class="sxs-lookup"><span data-stu-id="e04bf-142">dir(*object*)</span></span>
<span data-ttu-id="e04bf-143">返回指定对象的属性的树视图列表。</span><span class="sxs-lookup"><span data-stu-id="e04bf-143">Returns a tree view list of properties for the specified object.</span></span>

<span data-ttu-id="e04bf-144">示例：打开控制台并键入以查看表示此页面 `dir(document)` 的文档对象的对象属性。</span><span class="sxs-lookup"><span data-stu-id="e04bf-144">Example: Open the console and type `dir(document)` to see the object properties for the document object representing this page.</span></span>

!["dir"方法的示例使用](../media/console_cmd_dir.png)

### <span data-ttu-id="e04bf-146">键 (\*对象) \*</span><span class="sxs-lookup"><span data-stu-id="e04bf-146">keys(*object*)</span></span>
<span data-ttu-id="e04bf-147">返回附加到指定对象的属性名称的数组。</span><span class="sxs-lookup"><span data-stu-id="e04bf-147">Returns an array of property names attached to the specified object.</span></span>

<span data-ttu-id="e04bf-148">示例：打开控制台并键入以返回在全局窗口对象上 `keys(window)` 定义的所有属性。</span><span class="sxs-lookup"><span data-stu-id="e04bf-148">Example: Open the console and type `keys(window)` to return all of the properties defined on the global window object.</span></span>

!["keys"方法的示例使用](../media/console_cmd_keys.png)

### <span data-ttu-id="e04bf-150">值 (\*对象) \*</span><span class="sxs-lookup"><span data-stu-id="e04bf-150">values(*object*)</span></span>
<span data-ttu-id="e04bf-151">返回附加到指定对象的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="e04bf-151">Returns an array of property values attached to the specified object.</span></span>

<span data-ttu-id="e04bf-152">示例：打开控制台并键入以返回在全局窗口对象上 (`values(window)` 键) 的所有属性值。</span><span class="sxs-lookup"><span data-stu-id="e04bf-152">Example: Open the console and type `values(window)` to return the values of all the properties (keys) defined on the global window object.</span></span>

!["values"方法的示例使用](../media/console_cmd_values.png)

## <span data-ttu-id="e04bf-154">事件侦听器</span><span class="sxs-lookup"><span data-stu-id="e04bf-154">Event listeners</span></span>

<span data-ttu-id="e04bf-155">此命令允许您检查注册到给定对象的事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="e04bf-155">This command allows you to inspect the event listeners registered to a given object.</span></span> <span data-ttu-id="e04bf-156">指定的对象必须在全局命名空间或调试器的当前作用域中定义。</span><span class="sxs-lookup"><span data-stu-id="e04bf-156">The specified object must either be defined in the global namespace or the current scope of the  debugger.</span></span>

### <span data-ttu-id="e04bf-157">getEventListeners (\*对象) \*</span><span class="sxs-lookup"><span data-stu-id="e04bf-157">getEventListeners(*object*)</span></span>
<span data-ttu-id="e04bf-158">返回一个对象，该对象包含给定对象上每个已注册事件类型的键。</span><span class="sxs-lookup"><span data-stu-id="e04bf-158">Returns an object containing a key for each registered event type on the given object.</span></span> <span data-ttu-id="e04bf-159">每个键的值是一组事件侦听器及其相关信息。</span><span class="sxs-lookup"><span data-stu-id="e04bf-159">The value of each key is an array of event listeners and their related info.</span></span> 

<span data-ttu-id="e04bf-160">示例：打开控制台并键入以查看在此页的文档对象上注册 `getEventListeners(document)` 的所有事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="e04bf-160">Example: Open the console and type `getEventListeners(document)` to see all the event listeners registered on the document object of this page.</span></span>

!["getEventListeners"方法的示例使用](../media/console_cmd_getEventListeners.png)
