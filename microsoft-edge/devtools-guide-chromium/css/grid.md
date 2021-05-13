---
description: 了解如何使用 Microsoft Edge 开发人员工具查看和更改页面的 CSS。
title: 检查 Microsoft Edge 开发人员工具中的 CSS 网格
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
ms.openlocfilehash: 68493fae5e96ef1b2c7ed1205d67fd2b4cf67df5
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564453"
---
# <a name="inspect-css-grid"></a><span data-ttu-id="905a5-104">检查 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="905a5-104">Inspect CSS Grid</span></span>  

<span data-ttu-id="905a5-105">本文将引导你识别网站上的 CSS 网格并使用可自定义的网格叠加层来调试网格布局问题。</span><span class="sxs-lookup"><span data-stu-id="905a5-105">This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.</span></span>  

<span data-ttu-id="905a5-106">本文图表中使用的示例来自以下网页。</span><span class="sxs-lookup"><span data-stu-id="905a5-106">The examples used in the figures in this article are taken from the following webpages.</span></span>  

*   [<span data-ttu-id="905a5-107">水果盒</span><span class="sxs-lookup"><span data-stu-id="905a5-107">Fruit box</span></span>][JecFyiDemoCssGridFruit]  
*   [<span data-ttu-id="905a5-108">小吃盒</span><span class="sxs-lookup"><span data-stu-id="905a5-108">Snack box</span></span>][JecFyiDemoCssGridSnack]  

## <a name="before-you-begin"></a><span data-ttu-id="905a5-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="905a5-109">Before you begin</span></span>  

<span data-ttu-id="905a5-110">CSS 网格是一种强大的 Web 布局范例。</span><span class="sxs-lookup"><span data-stu-id="905a5-110">CSS Grid is a powerful layout paradigm for the web.</span></span>  <span data-ttu-id="905a5-111">可通过 MDN 上的 [CSS 网格布局指南][MdnCssGridLayout]开始了解 CSS 网格和许多功能。</span><span class="sxs-lookup"><span data-stu-id="905a5-111">A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide][MdnCssGridLayout] on MDN.</span></span>  

## <a name="discover-css-grids"></a><span data-ttu-id="905a5-112">探索 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="905a5-112">Discover CSS grids</span></span>  

<span data-ttu-id="905a5-113">如果页面上的 HTML 元素应用了 `display: grid` 或 `display: inline-grid`，则“[元素][DevtoolsGuideChromiumOpen]”面板中该元素的旁边会显示一个 `grid` 徽章。</span><span class="sxs-lookup"><span data-stu-id="905a5-113">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements][DevtoolsGuideChromiumOpen] panel.</span></span>  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="探索网格" lightbox="../media/grid-discover-grid.msft.png":::
   <span data-ttu-id="905a5-115">探索网格</span><span class="sxs-lookup"><span data-stu-id="905a5-115">Discover grid</span></span>  
:::image-end:::  

<span data-ttu-id="905a5-116">选择徽章以切换页面上的网格叠加层显示。</span><span class="sxs-lookup"><span data-stu-id="905a5-116">Choose the badge to toggle the display of a grid overlay on the page.</span></span>  <span data-ttu-id="905a5-117">叠加层显示在元素上方，布局类似于网格，可显示网格线和轨道的位置：</span><span class="sxs-lookup"><span data-stu-id="905a5-117">The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:</span></span>  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="切换网格徽章" lightbox="../media/grid-highlight-grid.msft.png":::
   <span data-ttu-id="905a5-119">切换网格徽章</span><span class="sxs-lookup"><span data-stu-id="905a5-119">Toggle grid badge</span></span>  
:::image-end:::  

<span data-ttu-id="905a5-120">打开“**布局**”窗格。</span><span class="sxs-lookup"><span data-stu-id="905a5-120">Open the **Layout** pane.</span></span>  <span data-ttu-id="905a5-121">当网格包含在页面上时，“**布局**”窗格将包括“**网格**”部分，其中包含许多用于查看网格的选项。</span><span class="sxs-lookup"><span data-stu-id="905a5-121">When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.</span></span>  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="“布局”窗格" lightbox="../media/grid-layout-pane.msft.png":::
   <span data-ttu-id="905a5-123">“**布局**”窗格</span><span class="sxs-lookup"><span data-stu-id="905a5-123">**Layout** pane</span></span>  
:::image-end:::  

<span data-ttu-id="905a5-124">“**布局**”窗格中的“**网格**”部分包含以下 2 个子部分。</span><span class="sxs-lookup"><span data-stu-id="905a5-124">The **Grid** section in the **Layout** pane contains the following 2 sub-sections.</span></span>  

*   <span data-ttu-id="905a5-125">叠加层显示设置</span><span class="sxs-lookup"><span data-stu-id="905a5-125">Overlay display settings</span></span>  
*   <span data-ttu-id="905a5-126">网格叠加层</span><span class="sxs-lookup"><span data-stu-id="905a5-126">Grid overlays</span></span>  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <a name="overlay-display-settings"></a><span data-ttu-id="905a5-127">叠加层显示设置</span><span class="sxs-lookup"><span data-stu-id="905a5-127">Overlay display settings</span></span>  

<span data-ttu-id="905a5-128">“**叠加层显示设置**”由以下 2 部分组成。</span><span class="sxs-lookup"><span data-stu-id="905a5-128">The **Overlay display settings** consists of following 2 parts.</span></span>  

*   <span data-ttu-id="905a5-129">从下拉菜单中选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="905a5-129">Choose one of the following options from the dropdown menu.</span></span>  
    
    | <span data-ttu-id="905a5-130">线条选项</span><span class="sxs-lookup"><span data-stu-id="905a5-130">Line option</span></span> | <span data-ttu-id="905a5-131">详细信息</span><span class="sxs-lookup"><span data-stu-id="905a5-131">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="905a5-132">隐藏线条标签</span><span class="sxs-lookup"><span data-stu-id="905a5-132">Hide line labels</span></span>** | <span data-ttu-id="905a5-133">隐藏每个网格叠加层的线条标签。</span><span class="sxs-lookup"><span data-stu-id="905a5-133">Hide the labels of the lines for each grid overlay.</span></span> |  
    | **<span data-ttu-id="905a5-134">显示线条编号</span><span class="sxs-lookup"><span data-stu-id="905a5-134">Show line numbers</span></span>** | <span data-ttu-id="905a5-135">显示每个网格叠加层的线条编号（默认选中）。</span><span class="sxs-lookup"><span data-stu-id="905a5-135">Display the numbers of the lines for each grid overlay \(selected by default\).</span></span> |  
    | **<span data-ttu-id="905a5-136">显示线条名称</span><span class="sxs-lookup"><span data-stu-id="905a5-136">Show line names</span></span>** | <span data-ttu-id="905a5-137">显示每个网格叠加层的线条名称（倘若提供了名称）。</span><span class="sxs-lookup"><span data-stu-id="905a5-137">Display the names of the lines for each grid overlay when names are provided.</span></span> |  
    
*  <span data-ttu-id="905a5-138">选中以下选项旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="905a5-138">Choose the checkbox next the following options.</span></span>  
    
    | <span data-ttu-id="905a5-139">选项</span><span class="sxs-lookup"><span data-stu-id="905a5-139">Option</span></span> | <span data-ttu-id="905a5-140">详细信息</span><span class="sxs-lookup"><span data-stu-id="905a5-140">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="905a5-141">显示轨道大小</span><span class="sxs-lookup"><span data-stu-id="905a5-141">Show track sizes</span></span>**  | <span data-ttu-id="905a5-142">显示（或隐藏）轨道的大小。</span><span class="sxs-lookup"><span data-stu-id="905a5-142">Display \(or hide\) the sizes of the tracks.</span></span> |  
    | **<span data-ttu-id="905a5-143">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="905a5-143">Show area names</span></span>** | <span data-ttu-id="905a5-144">显示（或隐藏）区域的名称（倘若提供了名称）。</span><span class="sxs-lookup"><span data-stu-id="905a5-144">Display \(or hide\) the names of the area, when names are provided.</span></span> |  
    | **<span data-ttu-id="905a5-145">延伸网格线</span><span class="sxs-lookup"><span data-stu-id="905a5-145">Extend grid lines</span></span>** | <span data-ttu-id="905a5-146">显示（或隐藏）沿每个轴的网格尺寸延伸。</span><span class="sxs-lookup"><span data-stu-id="905a5-146">Displays \(or hides\) the extensions of the grid dimensions along each axis.</span></span>  <span data-ttu-id="905a5-147">默认情况下，网格线仅在设置了 `display: grid` 或 `display: inline-grid` CSS 的元素内显示。</span><span class="sxs-lookup"><span data-stu-id="905a5-147">By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it.</span></span> |  
    
<span data-ttu-id="905a5-148">以下各节提供了每个**叠加层显示设置**的详细信息。</span><span class="sxs-lookup"><span data-stu-id="905a5-148">The following sections provide details for each of the **Overlay display settings**.</span></span>  

### <a name="show-line-numbers"></a><span data-ttu-id="905a5-149">显示线条编号</span><span class="sxs-lookup"><span data-stu-id="905a5-149">Show line numbers</span></span>  

<span data-ttu-id="905a5-150">默认情况下，网格叠加层上会显示正数和负数线条编号。</span><span class="sxs-lookup"><span data-stu-id="905a5-150">By default, the positive and negative line numbers are displayed on the grid overlay.</span></span>  

<span data-ttu-id="905a5-151">有关网格叠加层中负数的详细信息，请导航至“[CSS 网格基于线条的放置][MdnLineBasedPlacementCssGrid]”。</span><span class="sxs-lookup"><span data-stu-id="905a5-151">For more information about negative numbers in the grid overlay, navigate to [Line-based placement with CSS Grid][MdnLineBasedPlacementCssGrid].</span></span>  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="显示线条编号" lightbox="../media/grid-show-line-numbers.msft.png":::
   <span data-ttu-id="905a5-153">显示线条编号</span><span class="sxs-lookup"><span data-stu-id="905a5-153">Display line numbers</span></span>  
:::image-end:::  

### <a name="hide-line-labels"></a><span data-ttu-id="905a5-154">隐藏线条标签</span><span class="sxs-lookup"><span data-stu-id="905a5-154">Hide line labels</span></span>  

<span data-ttu-id="905a5-155">选择“**隐藏线条标签**”以隐藏线条编号。</span><span class="sxs-lookup"><span data-stu-id="905a5-155">Choose **Hide line labels** to hide the line numbers.</span></span>  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="隐藏线条标签" lightbox="../media/grid-hide-line-labels.msft.png":::
   <span data-ttu-id="905a5-157">隐藏线条标签</span><span class="sxs-lookup"><span data-stu-id="905a5-157">Hide line labels</span></span>  
:::image-end:::  

### <a name="show-line-names"></a><span data-ttu-id="905a5-158">显示线条名称</span><span class="sxs-lookup"><span data-stu-id="905a5-158">Show line names</span></span>  

<span data-ttu-id="905a5-159">有关网格叠加层中的线条名称的详细信息，请导航至“[使用命名网格线的布局][MdnLayoutUsingNamedGridLines]”。</span><span class="sxs-lookup"><span data-stu-id="905a5-159">For more information about line names in the grid overlay, navigate to [Layout using named grid lines][MdnLayoutUsingNamedGridLines].</span></span>  

<span data-ttu-id="905a5-160">选择“**显示线条名称**”以查看线条名称而不是编号。</span><span class="sxs-lookup"><span data-stu-id="905a5-160">Choose **Show line names** to view the line names instead of numbers.</span></span>  <span data-ttu-id="905a5-161">在示例中，4 条线的名称为：`left`、`middle1`、`middle2` 和 `right`。</span><span class="sxs-lookup"><span data-stu-id="905a5-161">In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.</span></span>  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="显示线条名称" lightbox="../media/grid-show-line-names.msft.png":::
   **<span data-ttu-id="905a5-163">显示线条名称</span><span class="sxs-lookup"><span data-stu-id="905a5-163">Show line names</span></span>**  
:::image-end:::  

### <a name="show-track-sizes"></a><span data-ttu-id="905a5-164">显示轨道大小</span><span class="sxs-lookup"><span data-stu-id="905a5-164">Show track sizes</span></span>  

<span data-ttu-id="905a5-165">启用“**显示轨道大小**”复选框以查看网格的轨道大小。</span><span class="sxs-lookup"><span data-stu-id="905a5-165">Enable the **Show track sizes** checkbox to view the track sizes of the grid.</span></span>  

<span data-ttu-id="905a5-166">开发人员工具在每个线条标签中显示 `[authored size]` 和 `[computed size]`。</span><span class="sxs-lookup"><span data-stu-id="905a5-166">DevTools displays `[authored size]` and `[computed size]` in each line label.</span></span>  

| <span data-ttu-id="905a5-167">大小</span><span class="sxs-lookup"><span data-stu-id="905a5-167">Size</span></span> | <span data-ttu-id="905a5-168">详细信息</span><span class="sxs-lookup"><span data-stu-id="905a5-168">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="905a5-169">创作大小</span><span class="sxs-lookup"><span data-stu-id="905a5-169">authored size</span></span>** | <span data-ttu-id="905a5-170">样式表中定义的大小（如果未定义则忽略）。</span><span class="sxs-lookup"><span data-stu-id="905a5-170">The size defined in stylesheet \(omitted if not defined\).</span></span> |  
| **<span data-ttu-id="905a5-171">计算大小</span><span class="sxs-lookup"><span data-stu-id="905a5-171">computed size</span></span>** | <span data-ttu-id="905a5-172">屏幕上的实际大小。</span><span class="sxs-lookup"><span data-stu-id="905a5-172">The actual size on screen.</span></span> |  

<span data-ttu-id="905a5-173">在演示中，`snack-box` 列大小在 `grid-template-columns:1fr 2fr;` CSS 中定义。</span><span class="sxs-lookup"><span data-stu-id="905a5-173">In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.</span></span>  <span data-ttu-id="905a5-174">因此，列线条标签显示了创作大小和计算大小。</span><span class="sxs-lookup"><span data-stu-id="905a5-174">Therefore, the column line labels display both authored and computed sizes.</span></span>  

| <span data-ttu-id="905a5-175">轨道大小</span><span class="sxs-lookup"><span data-stu-id="905a5-175">Track size</span></span> | <span data-ttu-id="905a5-176">创作大小</span><span class="sxs-lookup"><span data-stu-id="905a5-176">Authored size</span></span> | <span data-ttu-id="905a5-177">计算大小</span><span class="sxs-lookup"><span data-stu-id="905a5-177">Computed size</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="905a5-178">**1fr** &#x2022; **96.66px**</span><span class="sxs-lookup"><span data-stu-id="905a5-178">**1fr** &#x2022; **96.66px**</span></span> | <span data-ttu-id="905a5-179">1fr</span><span class="sxs-lookup"><span data-stu-id="905a5-179">1fr</span></span> | <span data-ttu-id="905a5-180">96.66px</span><span class="sxs-lookup"><span data-stu-id="905a5-180">96.66px</span></span> |  
| <span data-ttu-id="905a5-181">**2fr** &#x2022; **193.32px**</span><span class="sxs-lookup"><span data-stu-id="905a5-181">**2fr** &#x2022; **193.32px**</span></span> | <span data-ttu-id="905a5-182">2fr</span><span class="sxs-lookup"><span data-stu-id="905a5-182">2fr</span></span> | <span data-ttu-id="905a5-183">193.32px</span><span class="sxs-lookup"><span data-stu-id="905a5-183">193.32px</span></span> |  

<span data-ttu-id="905a5-184">行线条标签仅显示计算大小，因为样式表中未定义行大小。</span><span class="sxs-lookup"><span data-stu-id="905a5-184">The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.</span></span>  

| <span data-ttu-id="905a5-185">轨道大小</span><span class="sxs-lookup"><span data-stu-id="905a5-185">Track size</span></span> | <span data-ttu-id="905a5-186">创作大小</span><span class="sxs-lookup"><span data-stu-id="905a5-186">Authored size</span></span> | <span data-ttu-id="905a5-187">计算大小</span><span class="sxs-lookup"><span data-stu-id="905a5-187">Computed size</span></span> |  
|:--- |:--- |:--- |  
| **<span data-ttu-id="905a5-188">80px</span><span class="sxs-lookup"><span data-stu-id="905a5-188">80px</span></span>** | &nbsp;| <span data-ttu-id="905a5-189">80px</span><span class="sxs-lookup"><span data-stu-id="905a5-189">80px</span></span> |  
| **<span data-ttu-id="905a5-190">80px</span><span class="sxs-lookup"><span data-stu-id="905a5-190">80px</span></span>** | &nbsp;| <span data-ttu-id="905a5-191">80px</span><span class="sxs-lookup"><span data-stu-id="905a5-191">80px</span></span> |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="显示轨道大小" lightbox="../media/grid-show-track-sizes.msft.png":::
   **<span data-ttu-id="905a5-193">显示轨道大小</span><span class="sxs-lookup"><span data-stu-id="905a5-193">Show track sizes</span></span>**  
:::image-end:::  

### <a name="show-area-names"></a><span data-ttu-id="905a5-194">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="905a5-194">Show area names</span></span>  

<span data-ttu-id="905a5-195">若要查看区域名称，请启用“**显示区域名称**”复选框。</span><span class="sxs-lookup"><span data-stu-id="905a5-195">To view the area names, enable the **Show area names** checkbox.</span></span>  <span data-ttu-id="905a5-196">在示例中，网格中有 3 个区域：**top**、**bottom1** 和 **bottom2**。</span><span class="sxs-lookup"><span data-stu-id="905a5-196">In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.</span></span>  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="显示区域名称" lightbox="../media/grid-show-area-names.msft.png":::
   **<span data-ttu-id="905a5-198">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="905a5-198">Show area names</span></span>**  
:::image-end:::  

### <a name="extend-grid-lines"></a><span data-ttu-id="905a5-199">延伸网格线</span><span class="sxs-lookup"><span data-stu-id="905a5-199">Extend grid lines</span></span>  

<span data-ttu-id="905a5-200">启用“**延伸网格线**”复选框，将网格线沿每个轴延伸到视区的边缘。</span><span class="sxs-lookup"><span data-stu-id="905a5-200">Enable the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.</span></span>  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="延伸网格线" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **<span data-ttu-id="905a5-202">延伸网格线</span><span class="sxs-lookup"><span data-stu-id="905a5-202">Extend grid lines</span></span>**  
:::image-end:::  

## <a name="grid-overlays"></a><span data-ttu-id="905a5-203">网格叠加层</span><span class="sxs-lookup"><span data-stu-id="905a5-203">Grid overlays</span></span>  

<span data-ttu-id="905a5-204">“**网格叠加层**”部分包含页面上存在的网格列表，每个网格都带有一个复选框以及各种选项。</span><span class="sxs-lookup"><span data-stu-id="905a5-204">The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.</span></span>  

### <a name="enable-overlay-views-of-multiple-grids"></a><span data-ttu-id="905a5-205">启用多个网格的叠加视图</span><span class="sxs-lookup"><span data-stu-id="905a5-205">Enable overlay views of multiple grids</span></span>  

<span data-ttu-id="905a5-206">若要显示多个网格的叠加网格，请选中每个网格名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="905a5-206">To display the overlay grid for multiple grids, choose the checkbox next to each name of the grid.</span></span>  <span data-ttu-id="905a5-207">在示例中，启用了 2 个网格叠加层，每个叠加层以不同的颜色表示。</span><span class="sxs-lookup"><span data-stu-id="905a5-207">In the example, there are 2 grid overlays enabled that are each represented with different colors.</span></span>  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="启用多个网格的叠加视图" lightbox="../media/grid-grid-overlays.msft.png":::
   <span data-ttu-id="905a5-209">启用多个网格的叠加视图</span><span class="sxs-lookup"><span data-stu-id="905a5-209">Enable overlay views of multiple grids</span></span>  
:::image-end:::  

### <a name="customize-the-grid-overlay-color"></a><span data-ttu-id="905a5-210">自定义网格叠加层颜色</span><span class="sxs-lookup"><span data-stu-id="905a5-210">Customize the grid overlay color</span></span>  

<span data-ttu-id="905a5-211">若要打开颜色选取器并自定义网格叠加层颜色，请选择网格叠加层名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="905a5-211">To open the color picker and customize the grid overlay color, choose the box next to the name of the grid overlay.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="自定义网格叠加层颜色" lightbox="../media/grid-grid-overlays-color.msft.png":::
   <span data-ttu-id="905a5-213">自定义网格叠加层颜色</span><span class="sxs-lookup"><span data-stu-id="905a5-213">Customize the grid overlay color</span></span>  
:::image-end:::  

### <a name="highlight-the-grid"></a><span data-ttu-id="905a5-214">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="905a5-214">Highlight the grid</span></span>  

<span data-ttu-id="905a5-215">若要在“**元素**”工具中突出显示 HTML 元素并在网页上滚动到该元素，请选择“**在‘元素’面板中显示元素**”（![“在‘元素’面板中显示元素”图标](../media/show-element-in-element-panel-icon.msft.png)）图标。</span><span class="sxs-lookup"><span data-stu-id="905a5-215">To highlight the HTML element in the **Elements** tool and scroll to it on the webpage, choose the **Show element in the Elements panel** \(![Show element in the Elements panel icon](../media/show-element-in-element-panel-icon.msft.png)\) icon.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="突出显示网格" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   <span data-ttu-id="905a5-217">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="905a5-217">Highlight the grid</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="905a5-218">联系 Microsoft Edge 开发人员工具团队</span><span class="sxs-lookup"><span data-stu-id="905a5-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "打开 Microsoft Edge 开发人员工具 | Microsoft Docs"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS 网格 | jec.fyi"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS 网格 | jec.fyi"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局 | MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "使用命名网格线的布局 | MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "CSS 网格基于线条的放置 | MDN"  

> [!NOTE]
> <span data-ttu-id="905a5-225">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="905a5-225">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="905a5-226">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/css/grid)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="905a5-226">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="905a5-228">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="905a5-228">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
