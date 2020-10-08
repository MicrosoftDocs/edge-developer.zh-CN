---
description: 使用 "元素" 面板检查页面的 HTML、CSS、DOM 和辅助功能。
title: DevTools-元素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、元素、html、css、dom 断点、事件、辅助功能
ms.custom: seodec18
ms.openlocfilehash: 8948ddb3291bd122521e0b0800c0113a576d49e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564293"
---
# <span data-ttu-id="563de-104">元素</span><span class="sxs-lookup"><span data-stu-id="563de-104">Elements</span></span>

<span data-ttu-id="563de-105">" **元素** " 面板可帮助你：</span><span class="sxs-lookup"><span data-stu-id="563de-105">The **Elements** panel helps you to:</span></span>

* <span data-ttu-id="563de-106">在当前页的[HTML 树中标识和编辑元素](#html-tree-view)</span><span class="sxs-lookup"><span data-stu-id="563de-106">[Identify and edit elements in the HTML tree](#html-tree-view) of the current page</span></span>
* <span data-ttu-id="563de-107">在页面上[检查和修改 CSS](./elements/styles.md) ，包括伪状态和伪元素</span><span class="sxs-lookup"><span data-stu-id="563de-107">[Inspect and modify CSS](./elements/styles.md) on the page, including pseudo-states and pseudo-elements</span></span>
* <span data-ttu-id="563de-108">了解页面上发生[的 CSS 布局和样式级联](./elements/computed.md)</span><span class="sxs-lookup"><span data-stu-id="563de-108">[Understand the CSS layout and style cascade](./elements/computed.md) happening on the page</span></span>
* <span data-ttu-id="563de-109">[跟踪无管理事件处理程序](./elements/events.md) ，以便你可以调试它们</span><span class="sxs-lookup"><span data-stu-id="563de-109">[Track down rogue event handlers](./elements/events.md) so you can debug them</span></span>
* <span data-ttu-id="563de-110">[设置调试断点以使意外的可视更改](./elements/dom-breakpoints.md) 跳转到引起它们的代码</span><span class="sxs-lookup"><span data-stu-id="563de-110">[Set debugging breakpoints for unexpected visual changes](./elements/dom-breakpoints.md) to jump into the code causing them</span></span>
* <span data-ttu-id="563de-111">[获取有关页面上使用的字体](./elements/fonts.md) 以及加载位置的详细信息</span><span class="sxs-lookup"><span data-stu-id="563de-111">[Get detailed information about the fonts used on the page](./elements/fonts.md) and where they're loading from</span></span>
* <span data-ttu-id="563de-112">[通过屏幕阅读器的查看点查看页面](./elements/accessibility.md) ，验证和测试辅助功能</span><span class="sxs-lookup"><span data-stu-id="563de-112">[View your page from a screen reader's point of view](./elements/accessibility.md) to verify and test accessibility</span></span> 
* <span data-ttu-id="563de-113">查看你在调试页面 UI 时所做[的 CSS 更改的运行差异](./elements/changes.md)</span><span class="sxs-lookup"><span data-stu-id="563de-113">[Review a running diff of the CSS changes](./elements/changes.md) you make as you debug the UI of your page</span></span>

## <span data-ttu-id="563de-114">HTML 树视图</span><span class="sxs-lookup"><span data-stu-id="563de-114">HTML tree view</span></span>

![Microsoft Edge DevTools 元素面板](./media/elements.png)

1. <span data-ttu-id="563de-116">使用 **Select 元素** (`Ctrl+B`) 工具在页面中单击元素以在 " **HTML" 树视图** 中找到该元素。</span><span class="sxs-lookup"><span data-stu-id="563de-116">Use the **Select element** (`Ctrl+B`) tool to locate an element in the **HTML tree view** by clicking on it in the page.</span></span>

2. <span data-ttu-id="563de-117">使用 **元素突出显示** (`Ctrl+Shift+L`) 工具通过将元素悬停在 **HTML 树视图**中，在页面上查找元素。</span><span class="sxs-lookup"><span data-stu-id="563de-117">Use the **Element highlighting** (`Ctrl+Shift+L`) tool to locate an element on the page by hovering over it in the **HTML tree view**.</span></span>

3. <span data-ttu-id="563de-118">打开 " **颜色选取器** " (`Ctrl+K`) 工具 "以查看当前页面上使用的颜色列表。</span><span class="sxs-lookup"><span data-stu-id="563de-118">Open the **Color picker** (`Ctrl+K`) tool to see a list of the colors in use on the current page.</span></span> <span data-ttu-id="563de-119">单击列表上的颜色将提供更多详细信息 (色调、饱和度、亮度、Alpha) 。</span><span class="sxs-lookup"><span data-stu-id="563de-119">Clicking on a color on the list will provide further details (Hue, Saturation, Lightness, Alpha).</span></span> <span data-ttu-id="563de-120">在 "**样式**" 窗格中单击颜色值旁边的彩色方块时，*颜色选取器*也会打开，允许编辑页面元素的颜色并立即查看结果。</span><span class="sxs-lookup"><span data-stu-id="563de-120">The *Color picker* also opens when you click on the colored square next to a color value in the **Styles** pane, allowing you to edit the color of a page element and immediately see the results.</span></span>

4. <span data-ttu-id="563de-121">" **辅助功能树** (`Ctrl+Shift+A`) " 按钮将打开 " [辅助功能树](./elements/accessibility.md) " 窗格，其中显示页面的结构，其外观与辅助技术（如 [Windows 讲述人](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader）的结构相同。</span><span class="sxs-lookup"><span data-stu-id="563de-121">The **Accessibility tree** (`Ctrl+Shift+A`) button will open the [Accessibility tree](./elements/accessibility.md) pane showing the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader.</span></span>

5. <span data-ttu-id="563de-122">还可以**Find** `Ctrl+F` 通过搜索 HTML 树视图中的标记名称、属性或文本内容来查找 () 元素。</span><span class="sxs-lookup"><span data-stu-id="563de-122">You can also **Find** (`Ctrl+F`) an element in the HTML tree view by searching for its tag name, attributes, or text content.</span></span>

### <span data-ttu-id="563de-123">编辑元素</span><span class="sxs-lookup"><span data-stu-id="563de-123">Editing elements</span></span>

<span data-ttu-id="563de-124">你可以通过右键单击 HTML 树视图中的元素，然后从上下文菜单中选择 " **编辑为 HTML** " 来编辑该元素。</span><span class="sxs-lookup"><span data-stu-id="563de-124">You can edit an element by right-clicking on it within the HTML tree view and selecting **Edit as HTML** from the context menu.</span></span> <span data-ttu-id="563de-125">上下文菜单还提供用于删除、剪切、复制、粘贴、设置 CSS 伪类 (的选项： " *活动*"、 *： "焦点*" *： "悬停*"、"已 *访问* ") 和 "添加属性"。</span><span class="sxs-lookup"><span data-stu-id="563de-125">The context menu also provides options to delete, cut, copy, paste, set CSS pseudo-classes (*:active*, *:focus*, *:hover*, *:visited*) and add attributes.</span></span> <span data-ttu-id="563de-126">编辑属性和/或其值的另一种方法是在 HTML 树视图中双击它。</span><span class="sxs-lookup"><span data-stu-id="563de-126">Another way to edit an attribute and/or its value is to double-click it from the HTML tree view.</span></span>

![HTML 树视图上下文菜单](./media/elements_html_tree_context.png)

> [!NOTE]
> <span data-ttu-id="563de-128">编辑 HTML 树不会影响基础源标记。</span><span class="sxs-lookup"><span data-stu-id="563de-128">Editing the HTML tree does not affect the underlying source markup.</span></span> <span data-ttu-id="563de-129">刷新页面将还原所做的更改，并仅呈现由页面源确定的布局。</span><span class="sxs-lookup"><span data-stu-id="563de-129">Refreshing the page will revert your changes and render only the layout determined by the page source.</span></span> <span data-ttu-id="563de-130">若要 **将** 修改后的 HTML 复制到剪贴板，请右键单击所需的元素 (或全局 `html` 元素（如果希望整个页面) 打开上下文菜单）。</span><span class="sxs-lookup"><span data-stu-id="563de-130">You can **Copy** your modified HTML to the clipboard by right-clicking the desired element (or the global `html` element, if you want the entire page) to open up the context menu.</span></span> <span data-ttu-id="563de-131"> (" **剪切** " 和 " **粘贴** " 选项也可) 。</span><span class="sxs-lookup"><span data-stu-id="563de-131">(**Cut** and **Paste** options are also available).</span></span>

<span data-ttu-id="563de-132">从 " [样式](./elements/styles.md) " 窗格中，你还可以添加/删除/编辑 CSS 伪状态和伪元素。</span><span class="sxs-lookup"><span data-stu-id="563de-132">From the [Styles](./elements/styles.md) pane you can also add/delete/edit CSS pseudo-states and pseudo-elements.</span></span>

## <span data-ttu-id="563de-133">工具窗格</span><span class="sxs-lookup"><span data-stu-id="563de-133">Tool Panes</span></span>

<span data-ttu-id="563de-134">选择了感兴趣的页面元素后，你可以使用工具窗格来进一步检查其不同的样式和辅助功能属性，查看其事件侦听器，并设置 DOM 转变断点。</span><span class="sxs-lookup"><span data-stu-id="563de-134">Once you have selected a page element of interest, you can use the tool panes to further inspect its different styles and accessibility properties, view its event listeners, and set DOM mutation breakpoints.</span></span>

!["元素" 面板上的工具窗格](./media/elements_toolpanes.png)

1. <span data-ttu-id="563de-136">[**样式**](./elements/styles.md)：当前应用的样式，按样式表组织</span><span class="sxs-lookup"><span data-stu-id="563de-136">[**Styles**](./elements/styles.md): Currently applied styles organized by stylesheet</span></span>

2. <span data-ttu-id="563de-137">已[**计算**](./elements/computed.md)：当前应用的按 CSS 属性组织的样式</span><span class="sxs-lookup"><span data-stu-id="563de-137">[**Computed**](./elements/computed.md): Currently applied styles organized by CSS attributes</span></span>

3. <span data-ttu-id="563de-138">[**事件**](./elements/events.md)：在当前元素和上级元素上注册的事件侦听器</span><span class="sxs-lookup"><span data-stu-id="563de-138">[**Events**](./elements/events.md): Event listeners registered on the current element and ancestor elements</span></span>

4. <span data-ttu-id="563de-139">[**Dom 断点**](./elements/dom-breakpoints.md)： Dom 转变断点</span><span class="sxs-lookup"><span data-stu-id="563de-139">[**DOM breakpoints**](./elements/dom-breakpoints.md): DOM Mutation Breakpoints</span></span> 

5. <span data-ttu-id="563de-140">[**字体**](./elements/fonts.md)：当前对选定元素应用的字体</span><span class="sxs-lookup"><span data-stu-id="563de-140">[**Fonts**](./elements/fonts.md): Currently applied fonts for a selected element</span></span>

6. <span data-ttu-id="563de-141">[**辅助功能**](./elements/accessibility.md)：辅助功能属性</span><span class="sxs-lookup"><span data-stu-id="563de-141">[**Accessibility**](./elements/accessibility.md):  Accessibility properties</span></span>

7. <span data-ttu-id="563de-142">[**更改**](./elements/changes.md)：在诊断会话期间进行的 CSS 更改</span><span class="sxs-lookup"><span data-stu-id="563de-142">[**Changes**](./elements/changes.md): CSS changes made during diagnostic session</span></span>  

## <span data-ttu-id="563de-143">快捷方式</span><span class="sxs-lookup"><span data-stu-id="563de-143">Shortcuts</span></span>

| <span data-ttu-id="563de-144">操作</span><span class="sxs-lookup"><span data-stu-id="563de-144">Action</span></span>               | <span data-ttu-id="563de-145">快捷方式</span><span class="sxs-lookup"><span data-stu-id="563de-145">Shortcut</span></span>               |
|:---------------------|:-----------------------|
| <span data-ttu-id="563de-146">元素面板</span><span class="sxs-lookup"><span data-stu-id="563de-146">Elements panel</span></span>       | `Ctrl` + `1`           |
| <span data-ttu-id="563de-147">元素突出显示</span><span class="sxs-lookup"><span data-stu-id="563de-147">Element highlighting</span></span> | `Ctrl` + `Shift` + `L` |
| <span data-ttu-id="563de-148">选择元素</span><span class="sxs-lookup"><span data-stu-id="563de-148">Select element</span></span>       | `Ctrl` + `B`           |
| <span data-ttu-id="563de-149">颜色选取器</span><span class="sxs-lookup"><span data-stu-id="563de-149">Color picker</span></span>         | `Ctrl` + `K`           |
| <span data-ttu-id="563de-150">辅助功能树</span><span class="sxs-lookup"><span data-stu-id="563de-150">Accessibility tree</span></span>   | `Ctrl` + `Shift` + `A` |
