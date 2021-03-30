---
description: 使用"元素"面板检查页面的 HTML、CSS、DOM 和辅助功能。
title: DevTools - 元素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 元素， html， css， dom 断点， 事件， 辅助功能
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 14052bc40b9f94e628f0b575ede6c1ca8ccf179a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232133"
---
# <span data-ttu-id="37986-104">元素</span><span class="sxs-lookup"><span data-stu-id="37986-104">Elements</span></span>

<span data-ttu-id="37986-105">" **元素** "面板可帮助你：</span><span class="sxs-lookup"><span data-stu-id="37986-105">The **Elements** panel helps you to:</span></span>

* <span data-ttu-id="37986-106">[标识和编辑当前页面的 HTML](#html-tree-view) 树中的元素</span><span class="sxs-lookup"><span data-stu-id="37986-106">[Identify and edit elements in the HTML tree](#html-tree-view) of the current page</span></span>
* <span data-ttu-id="37986-107">[检查和修改页面上的 CSS，](./elements/styles.md) 包括伪状态和伪元素</span><span class="sxs-lookup"><span data-stu-id="37986-107">[Inspect and modify CSS](./elements/styles.md) on the page, including pseudo-states and pseudo-elements</span></span>
* <span data-ttu-id="37986-108">[了解页面上发生的 CSS](./elements/computed.md) 布局和样式级联</span><span class="sxs-lookup"><span data-stu-id="37986-108">[Understand the CSS layout and style cascade](./elements/computed.md) happening on the page</span></span>
* <span data-ttu-id="37986-109">[跟踪未授权事件处理程序](./elements/events.md) ，以便你可以调试它们</span><span class="sxs-lookup"><span data-stu-id="37986-109">[Track down rogue event handlers](./elements/events.md) so you can debug them</span></span>
* <span data-ttu-id="37986-110">[设置调试断点，以便意外的视觉更改](./elements/dom-breakpoints.md) 跳转到导致它们的代码</span><span class="sxs-lookup"><span data-stu-id="37986-110">[Set debugging breakpoints for unexpected visual changes](./elements/dom-breakpoints.md) to jump into the code causing them</span></span>
* <span data-ttu-id="37986-111">[获取有关页面上使用的字体](./elements/fonts.md) 及其加载位置的详细信息</span><span class="sxs-lookup"><span data-stu-id="37986-111">[Get detailed information about the fonts used on the page](./elements/fonts.md) and where they're loading from</span></span>
* <span data-ttu-id="37986-112">[从屏幕阅读器的角度查看页面以](./elements/accessibility.md) 验证和测试辅助功能</span><span class="sxs-lookup"><span data-stu-id="37986-112">[View your page from a screen reader's point of view](./elements/accessibility.md) to verify and test accessibility</span></span> 
* <span data-ttu-id="37986-113">[在调试页面 UI](./elements/changes.md) 时，查看 CSS 更改的运行差异</span><span class="sxs-lookup"><span data-stu-id="37986-113">[Review a running diff of the CSS changes](./elements/changes.md) you make as you debug the UI of your page</span></span>

## <span data-ttu-id="37986-114">HTML 树视图</span><span class="sxs-lookup"><span data-stu-id="37986-114">HTML tree view</span></span>

![Microsoft Edge DevTools 元素面板](./media/elements.png)

1. <span data-ttu-id="37986-116">使用**Select 元素** () 在 HTML 树视图中通过单击该元素在页面中找到 `Ctrl+B` 该元素。 </span><span class="sxs-lookup"><span data-stu-id="37986-116">Use the **Select element** (`Ctrl+B`) tool to locate an element in the **HTML tree view** by clicking on it in the page.</span></span>

2. <span data-ttu-id="37986-117">使用 **元素突出显示** () 工具，通过将鼠标悬停在 HTML 树视图中的某个元素，找到 `Ctrl+Shift+L` **页面上的元素**。</span><span class="sxs-lookup"><span data-stu-id="37986-117">Use the **Element highlighting** (`Ctrl+Shift+L`) tool to locate an element on the page by hovering over it in the **HTML tree view**.</span></span>

3. <span data-ttu-id="37986-118">打开 **颜色选取** 器 () 查看当前页面上 `Ctrl+K` 使用的颜色列表。</span><span class="sxs-lookup"><span data-stu-id="37986-118">Open the **Color picker** (`Ctrl+K`) tool to see a list of the colors in use on the current page.</span></span> <span data-ttu-id="37986-119">单击列表上的颜色将提供有关色调、饱和度 (亮度、Alpha 颜色、alpha) 。</span><span class="sxs-lookup"><span data-stu-id="37986-119">Clicking on a color on the list will provide further details (Hue, Saturation, Lightness, Alpha).</span></span> <span data-ttu-id="37986-120">当您*单击*"样式"窗格中的颜色值旁边的彩色正方形时，颜色选取器也会打开，从而 允许您编辑页面元素的颜色并立即查看结果。</span><span class="sxs-lookup"><span data-stu-id="37986-120">The *Color picker* also opens when you click on the colored square next to a color value in the **Styles** pane, allowing you to edit the color of a page element and immediately see the results.</span></span>

4. <span data-ttu-id="37986-121">" 辅助功能 () 按钮将打开"辅助功能"树窗格，显示页面的结构，就像它向辅助技术（如 `Ctrl+Shift+A` Windows[讲述](https://support.microsoft.com/help/22798/windows-10-narrator-get-started)[](./elements/accessibility.md)人屏幕阅读器）显示一样。</span><span class="sxs-lookup"><span data-stu-id="37986-121">The **Accessibility tree** (`Ctrl+Shift+A`) button will open the [Accessibility tree](./elements/accessibility.md) pane showing the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader.</span></span>

5. <span data-ttu-id="37986-122">您还可以 **通过** () 属性或文本内容，在 HTML 树视图中查找元素 `Ctrl+F` 的名称。</span><span class="sxs-lookup"><span data-stu-id="37986-122">You can also **Find** (`Ctrl+F`) an element in the HTML tree view by searching for its tag name, attributes, or text content.</span></span>

### <span data-ttu-id="37986-123">编辑元素</span><span class="sxs-lookup"><span data-stu-id="37986-123">Editing elements</span></span>

<span data-ttu-id="37986-124">可以通过在 HTML 树视图中右键单击某个元素，然后从上下文菜单中选择"编辑 **为 HTML"** 来编辑元素。</span><span class="sxs-lookup"><span data-stu-id="37986-124">You can edit an element by right-clicking on it within the HTML tree view and selecting **Edit as HTML** from the context menu.</span></span> <span data-ttu-id="37986-125">上下文菜单还提供了删除、剪切、复制、粘贴、设置 CSS 伪类 (*：active*、 *：focus*、 *：hover*、 *：visited*) 和添加属性的选项。</span><span class="sxs-lookup"><span data-stu-id="37986-125">The context menu also provides options to delete, cut, copy, paste, set CSS pseudo-classes (*:active*, *:focus*, *:hover*, *:visited*) and add attributes.</span></span> <span data-ttu-id="37986-126">编辑属性和/或其值的另一种方式是从 HTML 树视图中双击它。</span><span class="sxs-lookup"><span data-stu-id="37986-126">Another way to edit an attribute and/or its value is to double-click it from the HTML tree view.</span></span>

![HTML 树视图上下文菜单](./media/elements_html_tree_context.png)

> [!NOTE]
> <span data-ttu-id="37986-128">编辑 HTML 树不会影响基础源标记。</span><span class="sxs-lookup"><span data-stu-id="37986-128">Editing the HTML tree does not affect the underlying source markup.</span></span> <span data-ttu-id="37986-129">刷新页面将还原更改，并仅呈现由页面源确定的布局。</span><span class="sxs-lookup"><span data-stu-id="37986-129">Refreshing the page will revert your changes and render only the layout determined by the page source.</span></span> <span data-ttu-id="37986-130">如果希望整个 **页面** 打开上下文菜单 (，可以右键单击所需的元素 () 或全局元素，将修改后的 HTML 复制到剪贴板 `html` 中。</span><span class="sxs-lookup"><span data-stu-id="37986-130">You can **Copy** your modified HTML to the clipboard by right-clicking the desired element (or the global `html` element, if you want the entire page) to open up the context menu.</span></span> <span data-ttu-id="37986-131"> (**剪\切\**和粘贴**选项也可用) 。</span><span class="sxs-lookup"><span data-stu-id="37986-131">(**Cut** and **Paste** options are also available).</span></span>

<span data-ttu-id="37986-132">在 ["样式](./elements/styles.md) "窗格中，还可以添加/删除/编辑 CSS 伪状态和伪元素。</span><span class="sxs-lookup"><span data-stu-id="37986-132">From the [Styles](./elements/styles.md) pane you can also add/delete/edit CSS pseudo-states and pseudo-elements.</span></span>

## <span data-ttu-id="37986-133">工具窗格</span><span class="sxs-lookup"><span data-stu-id="37986-133">Tool Panes</span></span>

<span data-ttu-id="37986-134">选择感兴趣的页面元素后，可以使用工具窗格进一步检查其不同的样式和辅助功能属性、查看其事件侦听器和设置 DOM 破坏断点。</span><span class="sxs-lookup"><span data-stu-id="37986-134">Once you have selected a page element of interest, you can use the tool panes to further inspect its different styles and accessibility properties, view its event listeners, and set DOM mutation breakpoints.</span></span>

!["元素"面板上的"工具"窗格](./media/elements_toolpanes.png)

1. <span data-ttu-id="37986-136">[**样式**](./elements/styles.md)：当前应用的样式由样式表组织</span><span class="sxs-lookup"><span data-stu-id="37986-136">[**Styles**](./elements/styles.md): Currently applied styles organized by stylesheet</span></span>

2. <span data-ttu-id="37986-137">[**计算：**](./elements/computed.md)当前应用的样式由 CSS 属性组织</span><span class="sxs-lookup"><span data-stu-id="37986-137">[**Computed**](./elements/computed.md): Currently applied styles organized by CSS attributes</span></span>

3. <span data-ttu-id="37986-138">[**事件 ：**](./elements/events.md)在当前元素和上级元素上注册的事件侦听器</span><span class="sxs-lookup"><span data-stu-id="37986-138">[**Events**](./elements/events.md): Event listeners registered on the current element and ancestor elements</span></span>

4. <span data-ttu-id="37986-139">[**DOM 断点**](./elements/dom-breakpoints.md)：DOM 分解断点</span><span class="sxs-lookup"><span data-stu-id="37986-139">[**DOM breakpoints**](./elements/dom-breakpoints.md): DOM Mutation Breakpoints</span></span> 

5. <span data-ttu-id="37986-140">[**字体**](./elements/fonts.md)：当前为选定元素应用的字体</span><span class="sxs-lookup"><span data-stu-id="37986-140">[**Fonts**](./elements/fonts.md): Currently applied fonts for a selected element</span></span>

6. <span data-ttu-id="37986-141">[**辅助功能**](./elements/accessibility.md)：辅助功能属性</span><span class="sxs-lookup"><span data-stu-id="37986-141">[**Accessibility**](./elements/accessibility.md):  Accessibility properties</span></span>

7. <span data-ttu-id="37986-142">[**更改**](./elements/changes.md)：诊断会话期间对 CSS 所做的更改</span><span class="sxs-lookup"><span data-stu-id="37986-142">[**Changes**](./elements/changes.md): CSS changes made during diagnostic session</span></span>  

## <span data-ttu-id="37986-143">快捷方式</span><span class="sxs-lookup"><span data-stu-id="37986-143">Shortcuts</span></span>

| <span data-ttu-id="37986-144">操作</span><span class="sxs-lookup"><span data-stu-id="37986-144">Action</span></span>               | <span data-ttu-id="37986-145">快捷方式</span><span class="sxs-lookup"><span data-stu-id="37986-145">Shortcut</span></span>               |
|:---------------------|:-----------------------|
| <span data-ttu-id="37986-146">元素面板</span><span class="sxs-lookup"><span data-stu-id="37986-146">Elements panel</span></span>       | `Ctrl` + `1`           |
| <span data-ttu-id="37986-147">元素突出显示</span><span class="sxs-lookup"><span data-stu-id="37986-147">Element highlighting</span></span> | `Ctrl` + `Shift` + `L` |
| <span data-ttu-id="37986-148">Select 元素</span><span class="sxs-lookup"><span data-stu-id="37986-148">Select element</span></span>       | `Ctrl` + `B`           |
| <span data-ttu-id="37986-149">颜色选取器</span><span class="sxs-lookup"><span data-stu-id="37986-149">Color picker</span></span>         | `Ctrl` + `K`           |
| <span data-ttu-id="37986-150">辅助功能树</span><span class="sxs-lookup"><span data-stu-id="37986-150">Accessibility tree</span></span>   | `Ctrl` + `Shift` + `A` |
