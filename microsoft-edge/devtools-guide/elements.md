---
description: Use the Elements panel to inspect the HTML, CSS, DOM, and accessibility of your page.
title: DevTools - Elements
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, elements, html, css, dom breakpoints, events, accessibility
ms.custom: seodec18
ms.openlocfilehash: 8948ddb3291bd122521e0b0800c0113a576d49e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564293"
---
# <span data-ttu-id="6a54e-104">Elements</span><span class="sxs-lookup"><span data-stu-id="6a54e-104">Elements</span></span>

<span data-ttu-id="6a54e-105">The **Elements** panel helps you to:</span><span class="sxs-lookup"><span data-stu-id="6a54e-105">The **Elements** panel helps you to:</span></span>

* <span data-ttu-id="6a54e-106">[Identify and edit elements in the HTML tree](#html-tree-view) of the current page</span><span class="sxs-lookup"><span data-stu-id="6a54e-106">[Identify and edit elements in the HTML tree](#html-tree-view) of the current page</span></span>
* <span data-ttu-id="6a54e-107">[Inspect and modify CSS](./elements/styles.md) on the page, including pseudo-states and pseudo-elements</span><span class="sxs-lookup"><span data-stu-id="6a54e-107">[Inspect and modify CSS](./elements/styles.md) on the page, including pseudo-states and pseudo-elements</span></span>
* <span data-ttu-id="6a54e-108">[Understand the CSS layout and style cascade](./elements/computed.md) happening on the page</span><span class="sxs-lookup"><span data-stu-id="6a54e-108">[Understand the CSS layout and style cascade](./elements/computed.md) happening on the page</span></span>
* <span data-ttu-id="6a54e-109">[Track down rogue event handlers](./elements/events.md) so you can debug them</span><span class="sxs-lookup"><span data-stu-id="6a54e-109">[Track down rogue event handlers](./elements/events.md) so you can debug them</span></span>
* <span data-ttu-id="6a54e-110">[Set debugging breakpoints for unexpected visual changes](./elements/dom-breakpoints.md) to jump into the code causing them</span><span class="sxs-lookup"><span data-stu-id="6a54e-110">[Set debugging breakpoints for unexpected visual changes](./elements/dom-breakpoints.md) to jump into the code causing them</span></span>
* <span data-ttu-id="6a54e-111">[Get detailed information about the fonts used on the page](./elements/fonts.md) and where they're loading from</span><span class="sxs-lookup"><span data-stu-id="6a54e-111">[Get detailed information about the fonts used on the page](./elements/fonts.md) and where they're loading from</span></span>
* <span data-ttu-id="6a54e-112">[View your page from a screen reader's point of view](./elements/accessibility.md) to verify and test accessibility</span><span class="sxs-lookup"><span data-stu-id="6a54e-112">[View your page from a screen reader's point of view](./elements/accessibility.md) to verify and test accessibility</span></span> 
* <span data-ttu-id="6a54e-113">[Review a running diff of the CSS changes](./elements/changes.md) you make as you debug the UI of your page</span><span class="sxs-lookup"><span data-stu-id="6a54e-113">[Review a running diff of the CSS changes](./elements/changes.md) you make as you debug the UI of your page</span></span>

## <span data-ttu-id="6a54e-114">HTML tree view</span><span class="sxs-lookup"><span data-stu-id="6a54e-114">HTML tree view</span></span>

![The Microsoft Edge DevTools Elements panel](./media/elements.png)

1. <span data-ttu-id="6a54e-116">Use the **Select element** (`Ctrl+B`) tool to locate an element in the **HTML tree view** by clicking on it in the page.</span><span class="sxs-lookup"><span data-stu-id="6a54e-116">Use the **Select element** (`Ctrl+B`) tool to locate an element in the **HTML tree view** by clicking on it in the page.</span></span>

2. <span data-ttu-id="6a54e-117">Use the **Element highlighting** (`Ctrl+Shift+L`) tool to locate an element on the page by hovering over it in the **HTML tree view**.</span><span class="sxs-lookup"><span data-stu-id="6a54e-117">Use the **Element highlighting** (`Ctrl+Shift+L`) tool to locate an element on the page by hovering over it in the **HTML tree view**.</span></span>

3. <span data-ttu-id="6a54e-118">Open the **Color picker** (`Ctrl+K`) tool to see a list of the colors in use on the current page.</span><span class="sxs-lookup"><span data-stu-id="6a54e-118">Open the **Color picker** (`Ctrl+K`) tool to see a list of the colors in use on the current page.</span></span> <span data-ttu-id="6a54e-119">Clicking on a color on the list will provide further details (Hue, Saturation, Lightness, Alpha).</span><span class="sxs-lookup"><span data-stu-id="6a54e-119">Clicking on a color on the list will provide further details (Hue, Saturation, Lightness, Alpha).</span></span> <span data-ttu-id="6a54e-120">The *Color picker* also opens when you click on the colored square next to a color value in the **Styles** pane, allowing you to edit the color of a page element and immediately see the results.</span><span class="sxs-lookup"><span data-stu-id="6a54e-120">The *Color picker* also opens when you click on the colored square next to a color value in the **Styles** pane, allowing you to edit the color of a page element and immediately see the results.</span></span>

4. <span data-ttu-id="6a54e-121">The **Accessibility tree** (`Ctrl+Shift+A`) button will open the [Accessibility tree](./elements/accessibility.md) pane showing the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader.</span><span class="sxs-lookup"><span data-stu-id="6a54e-121">The **Accessibility tree** (`Ctrl+Shift+A`) button will open the [Accessibility tree](./elements/accessibility.md) pane showing the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader.</span></span>

5. <span data-ttu-id="6a54e-122">You can also **Find** (`Ctrl+F`) an element in the HTML tree view by searching for its tag name, attributes, or text content.</span><span class="sxs-lookup"><span data-stu-id="6a54e-122">You can also **Find** (`Ctrl+F`) an element in the HTML tree view by searching for its tag name, attributes, or text content.</span></span>

### <span data-ttu-id="6a54e-123">Editing elements</span><span class="sxs-lookup"><span data-stu-id="6a54e-123">Editing elements</span></span>

<span data-ttu-id="6a54e-124">You can edit an element by right-clicking on it within the HTML tree view and selecting **Edit as HTML** from the context menu.</span><span class="sxs-lookup"><span data-stu-id="6a54e-124">You can edit an element by right-clicking on it within the HTML tree view and selecting **Edit as HTML** from the context menu.</span></span> <span data-ttu-id="6a54e-125">The context menu also provides options to delete, cut, copy, paste, set CSS pseudo-classes (*:active*, *:focus*, *:hover*, *:visited*) and add attributes.</span><span class="sxs-lookup"><span data-stu-id="6a54e-125">The context menu also provides options to delete, cut, copy, paste, set CSS pseudo-classes (*:active*, *:focus*, *:hover*, *:visited*) and add attributes.</span></span> <span data-ttu-id="6a54e-126">Another way to edit an attribute and/or its value is to double-click it from the HTML tree view.</span><span class="sxs-lookup"><span data-stu-id="6a54e-126">Another way to edit an attribute and/or its value is to double-click it from the HTML tree view.</span></span>

![HTML tree view context menu](./media/elements_html_tree_context.png)

> [!NOTE]
> <span data-ttu-id="6a54e-128">Editing the HTML tree does not affect the underlying source markup.</span><span class="sxs-lookup"><span data-stu-id="6a54e-128">Editing the HTML tree does not affect the underlying source markup.</span></span> <span data-ttu-id="6a54e-129">Refreshing the page will revert your changes and render only the layout determined by the page source.</span><span class="sxs-lookup"><span data-stu-id="6a54e-129">Refreshing the page will revert your changes and render only the layout determined by the page source.</span></span> <span data-ttu-id="6a54e-130">You can **Copy** your modified HTML to the clipboard by right-clicking the desired element (or the global `html` element, if you want the entire page) to open up the context menu.</span><span class="sxs-lookup"><span data-stu-id="6a54e-130">You can **Copy** your modified HTML to the clipboard by right-clicking the desired element (or the global `html` element, if you want the entire page) to open up the context menu.</span></span> <span data-ttu-id="6a54e-131">(**Cut** and **Paste** options are also available).</span><span class="sxs-lookup"><span data-stu-id="6a54e-131">(**Cut** and **Paste** options are also available).</span></span>

<span data-ttu-id="6a54e-132">From the [Styles](./elements/styles.md) pane you can also add/delete/edit CSS pseudo-states and pseudo-elements.</span><span class="sxs-lookup"><span data-stu-id="6a54e-132">From the [Styles](./elements/styles.md) pane you can also add/delete/edit CSS pseudo-states and pseudo-elements.</span></span>

## <span data-ttu-id="6a54e-133">Tool Panes</span><span class="sxs-lookup"><span data-stu-id="6a54e-133">Tool Panes</span></span>

<span data-ttu-id="6a54e-134">Once you have selected a page element of interest, you can use the tool panes to further inspect its different styles and accessibility properties, view its event listeners, and set DOM mutation breakpoints.</span><span class="sxs-lookup"><span data-stu-id="6a54e-134">Once you have selected a page element of interest, you can use the tool panes to further inspect its different styles and accessibility properties, view its event listeners, and set DOM mutation breakpoints.</span></span>

![Tools panes on the Elements panel](./media/elements_toolpanes.png)

1. <span data-ttu-id="6a54e-136">[**Styles**](./elements/styles.md): Currently applied styles organized by stylesheet</span><span class="sxs-lookup"><span data-stu-id="6a54e-136">[**Styles**](./elements/styles.md): Currently applied styles organized by stylesheet</span></span>

2. <span data-ttu-id="6a54e-137">[**Computed**](./elements/computed.md): Currently applied styles organized by CSS attributes</span><span class="sxs-lookup"><span data-stu-id="6a54e-137">[**Computed**](./elements/computed.md): Currently applied styles organized by CSS attributes</span></span>

3. <span data-ttu-id="6a54e-138">[**Events**](./elements/events.md): Event listeners registered on the current element and ancestor elements</span><span class="sxs-lookup"><span data-stu-id="6a54e-138">[**Events**](./elements/events.md): Event listeners registered on the current element and ancestor elements</span></span>

4. <span data-ttu-id="6a54e-139">[**DOM breakpoints**](./elements/dom-breakpoints.md): DOM Mutation Breakpoints</span><span class="sxs-lookup"><span data-stu-id="6a54e-139">[**DOM breakpoints**](./elements/dom-breakpoints.md): DOM Mutation Breakpoints</span></span> 

5. <span data-ttu-id="6a54e-140">[**Fonts**](./elements/fonts.md): Currently applied fonts for a selected element</span><span class="sxs-lookup"><span data-stu-id="6a54e-140">[**Fonts**](./elements/fonts.md): Currently applied fonts for a selected element</span></span>

6. <span data-ttu-id="6a54e-141">[**Accessibility**](./elements/accessibility.md):  Accessibility properties</span><span class="sxs-lookup"><span data-stu-id="6a54e-141">[**Accessibility**](./elements/accessibility.md):  Accessibility properties</span></span>

7. <span data-ttu-id="6a54e-142">[**Changes**](./elements/changes.md): CSS changes made during diagnostic session</span><span class="sxs-lookup"><span data-stu-id="6a54e-142">[**Changes**](./elements/changes.md): CSS changes made during diagnostic session</span></span>  

## <span data-ttu-id="6a54e-143">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="6a54e-143">Shortcuts</span></span>

| <span data-ttu-id="6a54e-144">Action</span><span class="sxs-lookup"><span data-stu-id="6a54e-144">Action</span></span>               | <span data-ttu-id="6a54e-145">Shortcut</span><span class="sxs-lookup"><span data-stu-id="6a54e-145">Shortcut</span></span>               |
|:---------------------|:-----------------------|
| <span data-ttu-id="6a54e-146">Elements panel</span><span class="sxs-lookup"><span data-stu-id="6a54e-146">Elements panel</span></span>       | `Ctrl` + `1`           |
| <span data-ttu-id="6a54e-147">Element highlighting</span><span class="sxs-lookup"><span data-stu-id="6a54e-147">Element highlighting</span></span> | `Ctrl` + `Shift` + `L` |
| <span data-ttu-id="6a54e-148">Select element</span><span class="sxs-lookup"><span data-stu-id="6a54e-148">Select element</span></span>       | `Ctrl` + `B`           |
| <span data-ttu-id="6a54e-149">Color picker</span><span class="sxs-lookup"><span data-stu-id="6a54e-149">Color picker</span></span>         | `Ctrl` + `K`           |
| <span data-ttu-id="6a54e-150">Accessibility tree</span><span class="sxs-lookup"><span data-stu-id="6a54e-150">Accessibility tree</span></span>   | `Ctrl` + `Shift` + `A` |
