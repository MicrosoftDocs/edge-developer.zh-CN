---
description: 了解如何使用 Microsoft Edge DevTools 查看和更改页面 CSS 的 CSS。
title: 检查 Microsoft Edge DevTools 中的 CSS 网格
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 150aea57aa676580b554cc74292671ed567a0a2c
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "11133964"
---
# <span data-ttu-id="0dc66-104">检查 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="0dc66-104">Inspect CSS Grid</span></span>  

<span data-ttu-id="0dc66-105">本文将向你介绍如何使用可自定义的网格重叠在网站上识别 CSS 网格和调试网格布局问题。</span><span class="sxs-lookup"><span data-stu-id="0dc66-105">This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.</span></span>  

<span data-ttu-id="0dc66-106">本文中的图表中使用的示例来自以下网页。</span><span class="sxs-lookup"><span data-stu-id="0dc66-106">The examples used in the figures in this article are taken from the following webpages.</span></span>  

*   [<span data-ttu-id="0dc66-107">水果包装盒</span><span class="sxs-lookup"><span data-stu-id="0dc66-107">Fruit box</span></span>][JecFyiDemoCssGridFruit]  
*   [<span data-ttu-id="0dc66-108">零食框</span><span class="sxs-lookup"><span data-stu-id="0dc66-108">Snack box</span></span>][JecFyiDemoCssGridSnack]  

## <span data-ttu-id="0dc66-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="0dc66-109">Before you begin</span></span>  

<span data-ttu-id="0dc66-110">CSS 网格是 web 的一个强大的布局模式。</span><span class="sxs-lookup"><span data-stu-id="0dc66-110">CSS Grid is a powerful layout paradigm for the web.</span></span>  <span data-ttu-id="0dc66-111">有关 CSS 网格和许多功能入门的绝佳位置是有关 MDN 的 [Css 网格布局指南][MdnCssGridLayout] 。</span><span class="sxs-lookup"><span data-stu-id="0dc66-111">A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide][MdnCssGridLayout] on MDN.</span></span>  

## <span data-ttu-id="0dc66-112">探索 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="0dc66-112">Discover CSS grids</span></span>  

<span data-ttu-id="0dc66-113">当页面上已有或应用了 HTML 元素时 `display: grid` `display: inline-grid` ， `grid` " [元素][DevtoolsGuideChromiumOpen] " 面板中的标记旁边会显示一个标记。</span><span class="sxs-lookup"><span data-stu-id="0dc66-113">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements][DevtoolsGuideChromiumOpen] panel.</span></span>  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="探索网格" lightbox="../media/grid-discover-grid.msft.png":::
   <span data-ttu-id="0dc66-115">探索网格</span><span class="sxs-lookup"><span data-stu-id="0dc66-115">Discover grid</span></span>  
:::image-end:::  

<span data-ttu-id="0dc66-116">选择锁屏提醒以切换页面上的网格覆盖的显示。</span><span class="sxs-lookup"><span data-stu-id="0dc66-116">Select the badge to toggle the display of a grid overlay on the page.</span></span>  <span data-ttu-id="0dc66-117">覆盖层将出现在元素上方，布局类似于网格以显示网格线的位置和轨道：</span><span class="sxs-lookup"><span data-stu-id="0dc66-117">The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:</span></span>  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="探索网格" lightbox="../media/grid-highlight-grid.msft.png":::
   <span data-ttu-id="0dc66-119">切换网格标记</span><span class="sxs-lookup"><span data-stu-id="0dc66-119">Toggle grid badge</span></span>  
:::image-end:::  

<span data-ttu-id="0dc66-120">打开 " **布局** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="0dc66-120">Open the **Layout** pane.</span></span>  <span data-ttu-id="0dc66-121">当页面上包含网格时， **布局** 窗格包括一个 **网格** 部分，其中包含用于查看网格的许多选项。</span><span class="sxs-lookup"><span data-stu-id="0dc66-121">When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.</span></span>  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="探索网格" lightbox="../media/grid-layout-pane.msft.png":::
   <span data-ttu-id="0dc66-123">**布局** 窗格</span><span class="sxs-lookup"><span data-stu-id="0dc66-123">**Layout** pane</span></span>  
:::image-end:::  

<span data-ttu-id="0dc66-124">"**布局**" 窗格中的 "**网格**" 部分包含以下两个子部分。</span><span class="sxs-lookup"><span data-stu-id="0dc66-124">The **Grid** section in the **Layout** pane contains the following 2 sub-sections.</span></span>  

*   <span data-ttu-id="0dc66-125">覆盖显示设置</span><span class="sxs-lookup"><span data-stu-id="0dc66-125">Overlay display settings</span></span>  
*   <span data-ttu-id="0dc66-126">网格覆盖</span><span class="sxs-lookup"><span data-stu-id="0dc66-126">Grid overlays</span></span>  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <span data-ttu-id="0dc66-127">覆盖显示设置</span><span class="sxs-lookup"><span data-stu-id="0dc66-127">Overlay display settings</span></span>  

<span data-ttu-id="0dc66-128">**覆盖显示设置**由以下2个部分组成。</span><span class="sxs-lookup"><span data-stu-id="0dc66-128">The **Overlay display settings** consists of following 2 parts.</span></span>  

*   <span data-ttu-id="0dc66-129">从下拉菜单中选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="0dc66-129">Choose one of the following options from the dropdown menu.</span></span>  
    
    | <span data-ttu-id="0dc66-130">行选项</span><span class="sxs-lookup"><span data-stu-id="0dc66-130">Line option</span></span> | <span data-ttu-id="0dc66-131">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dc66-131">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="0dc66-132">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="0dc66-132">Hide line labels</span></span>** | <span data-ttu-id="0dc66-133">隐藏每个网格覆盖的行的标签。</span><span class="sxs-lookup"><span data-stu-id="0dc66-133">Hide the labels of the lines for each grid overlay.</span></span> |  
    | **<span data-ttu-id="0dc66-134">显示行号</span><span class="sxs-lookup"><span data-stu-id="0dc66-134">Show line numbers</span></span>** | <span data-ttu-id="0dc66-135">显示每个网格覆盖的行数 \ (默认选中 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="0dc66-135">Display the numbers of the lines for each grid overlay \(selected by default\).</span></span> |  
    | **<span data-ttu-id="0dc66-136">显示行名称</span><span class="sxs-lookup"><span data-stu-id="0dc66-136">Show line names</span></span>** | <span data-ttu-id="0dc66-137">在提供名称时显示每个网格覆盖的行的名称。</span><span class="sxs-lookup"><span data-stu-id="0dc66-137">Display the names of the lines for each grid overlay when names are provided.</span></span> |  
    
*  <span data-ttu-id="0dc66-138">选中以下选项旁的复选框。</span><span class="sxs-lookup"><span data-stu-id="0dc66-138">Choose the checkbox next the following options.</span></span>  
    
    | <span data-ttu-id="0dc66-139">选项</span><span class="sxs-lookup"><span data-stu-id="0dc66-139">Option</span></span> | <span data-ttu-id="0dc66-140">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dc66-140">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="0dc66-141">显示曲目大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-141">Show track sizes</span></span>**  | <span data-ttu-id="0dc66-142">显示 \ (或隐藏 \ ) 轨道的大小。</span><span class="sxs-lookup"><span data-stu-id="0dc66-142">Display \(or hide\) the sizes of the tracks.</span></span> |  
    | **<span data-ttu-id="0dc66-143">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="0dc66-143">Show area names</span></span>** | <span data-ttu-id="0dc66-144">当提供名称时，显示 "\ (" 或 "隐藏 \ ) " 区域的名称。</span><span class="sxs-lookup"><span data-stu-id="0dc66-144">Display \(or hide\) the names of the area, when names are provided.</span></span> |  
    | **<span data-ttu-id="0dc66-145">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="0dc66-145">Extend grid lines</span></span>** | <span data-ttu-id="0dc66-146">显示 \ (或隐藏 \ ) 沿每个轴的网格尺寸的扩展。</span><span class="sxs-lookup"><span data-stu-id="0dc66-146">Displays \(or hides\) the extensions of the grid dimensions along each axis.</span></span>  <span data-ttu-id="0dc66-147">默认情况下，网格线仅显示 `display: grid` `display: inline-grid` 在其上设置了 "" 或 "CSS" 的元素内。</span><span class="sxs-lookup"><span data-stu-id="0dc66-147">By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it.</span></span> |  
    
<span data-ttu-id="0dc66-148">以下部分提供了每个 **覆盖显示设置**的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0dc66-148">The following sections provide details for each of the **Overlay display settings**.</span></span>  

### <span data-ttu-id="0dc66-149">显示行号</span><span class="sxs-lookup"><span data-stu-id="0dc66-149">Show line numbers</span></span>  

<span data-ttu-id="0dc66-150">默认情况下，在网格覆盖区域上显示正值和负数。</span><span class="sxs-lookup"><span data-stu-id="0dc66-150">By default, the positive and negative line numbers are displayed on the grid overlay.</span></span>  

<span data-ttu-id="0dc66-151">有关网格覆盖中的负数的详细信息，请导航到 [具有 CSS 网格的基于行的位置][MdnLineBasedPlacementCssGrid]。</span><span class="sxs-lookup"><span data-stu-id="0dc66-151">For more information about negative numbers in the grid overlay, navigate to [Line-based placement with CSS Grid][MdnLineBasedPlacementCssGrid].</span></span>  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="探索网格" lightbox="../media/grid-show-line-numbers.msft.png":::
   <span data-ttu-id="0dc66-153">显示行号</span><span class="sxs-lookup"><span data-stu-id="0dc66-153">Display line numbers</span></span>  
:::image-end:::  

### <span data-ttu-id="0dc66-154">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="0dc66-154">Hide line labels</span></span>  

<span data-ttu-id="0dc66-155">选择 " **隐藏行标签** " 以隐藏行号。</span><span class="sxs-lookup"><span data-stu-id="0dc66-155">Select **Hide line labels** to hide the line numbers.</span></span>  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="探索网格" lightbox="../media/grid-hide-line-labels.msft.png":::
   <span data-ttu-id="0dc66-157">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="0dc66-157">Hide line labels</span></span>  
:::image-end:::  

### <span data-ttu-id="0dc66-158">显示行名称</span><span class="sxs-lookup"><span data-stu-id="0dc66-158">Show line names</span></span>  

<!--todo: @rachel verify the link and text for line name -->  
<span data-ttu-id="0dc66-159">有关网格覆盖中的行名称的详细信息，请导航到 [使用命名网格线的布局][MdnLayoutUsingNamedGridLines]。</span><span class="sxs-lookup"><span data-stu-id="0dc66-159">For more information about line names in the grid overlay, navigate to [Layout using named grid lines][MdnLayoutUsingNamedGridLines].</span></span>  

<span data-ttu-id="0dc66-160">选择 " **显示行名称** " 以查看行名称，而不是数字。</span><span class="sxs-lookup"><span data-stu-id="0dc66-160">Select **Show line names** to view the line names instead of numbers.</span></span>  <span data-ttu-id="0dc66-161">在该示例中，4行具有名称： `left` 、 `middle1` 、 `middle2` 和 `right` 。</span><span class="sxs-lookup"><span data-stu-id="0dc66-161">In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.</span></span>  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="探索网格" lightbox="../media/grid-show-line-names.msft.png":::
   **<span data-ttu-id="0dc66-163">显示行名称</span><span class="sxs-lookup"><span data-stu-id="0dc66-163">Show line names</span></span>**  
:::image-end:::  

### <span data-ttu-id="0dc66-164">显示曲目大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-164">Show track sizes</span></span>  

<span data-ttu-id="0dc66-165">启用 " **显示跟踪大小** " 复选框以查看网格的轨道大小。</span><span class="sxs-lookup"><span data-stu-id="0dc66-165">Enable the **Show track sizes** checkbox to view the track sizes of the grid.</span></span>  

<span data-ttu-id="0dc66-166">DevTools 显示 `[authored size]` `[computed size]` 在每个行标签中。</span><span class="sxs-lookup"><span data-stu-id="0dc66-166">DevTools displays `[authored size]` and `[computed size]` in each line label.</span></span>  

| <span data-ttu-id="0dc66-167">大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-167">Size</span></span> | <span data-ttu-id="0dc66-168">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dc66-168">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="0dc66-169">已创作大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-169">authored size</span></span>** | <span data-ttu-id="0dc66-170">如果未定义 \ ) ，则在样式表中定义的大小为 \ (省略。</span><span class="sxs-lookup"><span data-stu-id="0dc66-170">The size defined in stylesheet \(omitted if not defined\).</span></span> |  
| **<span data-ttu-id="0dc66-171">计算大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-171">computed size</span></span>** | <span data-ttu-id="0dc66-172">屏幕上的实际大小。</span><span class="sxs-lookup"><span data-stu-id="0dc66-172">The actual size on screen.</span></span> |  

<span data-ttu-id="0dc66-173">在演示中， `snack-box` 列的大小在 CSS 中定义 `grid-template-columns:1fr 2fr;` 。</span><span class="sxs-lookup"><span data-stu-id="0dc66-173">In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.</span></span>  <span data-ttu-id="0dc66-174">因此，列的行标签既显示了创作的，也显示了计算的大小。</span><span class="sxs-lookup"><span data-stu-id="0dc66-174">Therefore, the column line labels display both authored and computed sizes.</span></span>  

| <span data-ttu-id="0dc66-175">跟踪大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-175">Track size</span></span> | <span data-ttu-id="0dc66-176">已创作大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-176">Authored size</span></span> | <span data-ttu-id="0dc66-177">计算大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-177">Computed size</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="0dc66-178">**1fr** &#x2022; **96.66 px**</span><span class="sxs-lookup"><span data-stu-id="0dc66-178">**1fr** &#x2022; **96.66px**</span></span> | <span data-ttu-id="0dc66-179">1fr</span><span class="sxs-lookup"><span data-stu-id="0dc66-179">1fr</span></span> | <span data-ttu-id="0dc66-180">96.66 px</span><span class="sxs-lookup"><span data-stu-id="0dc66-180">96.66px</span></span> |  
| <span data-ttu-id="0dc66-181">**2fr** &#x2022; **193.32 px**</span><span class="sxs-lookup"><span data-stu-id="0dc66-181">**2fr** &#x2022; **193.32px**</span></span> | <span data-ttu-id="0dc66-182">2fr</span><span class="sxs-lookup"><span data-stu-id="0dc66-182">2fr</span></span> | <span data-ttu-id="0dc66-183">193.32 px</span><span class="sxs-lookup"><span data-stu-id="0dc66-183">193.32px</span></span> |  

<span data-ttu-id="0dc66-184">由于没有在样式表中定义的行大小，行标签仅显示计算的大小。</span><span class="sxs-lookup"><span data-stu-id="0dc66-184">The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.</span></span>  

| <span data-ttu-id="0dc66-185">跟踪大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-185">Track size</span></span> | <span data-ttu-id="0dc66-186">已创作大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-186">Authored size</span></span> | <span data-ttu-id="0dc66-187">计算大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-187">Computed size</span></span> |  
|:--- |:--- |:--- |  
| **<span data-ttu-id="0dc66-188">80px</span><span class="sxs-lookup"><span data-stu-id="0dc66-188">80px</span></span>** | &nbsp;| <span data-ttu-id="0dc66-189">80px</span><span class="sxs-lookup"><span data-stu-id="0dc66-189">80px</span></span> |  
| **<span data-ttu-id="0dc66-190">80px</span><span class="sxs-lookup"><span data-stu-id="0dc66-190">80px</span></span>** | &nbsp;| <span data-ttu-id="0dc66-191">80px</span><span class="sxs-lookup"><span data-stu-id="0dc66-191">80px</span></span> |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="探索网格" lightbox="../media/grid-show-track-sizes.msft.png":::
   **<span data-ttu-id="0dc66-193">显示曲目大小</span><span class="sxs-lookup"><span data-stu-id="0dc66-193">Show track sizes</span></span>**  
:::image-end:::  

### <span data-ttu-id="0dc66-194">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="0dc66-194">Show area names</span></span>  

<span data-ttu-id="0dc66-195">若要查看区域名称，请启用 " **显示区域名称** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="0dc66-195">To view the area names, enable the **Show area names** checkbox.</span></span>  <span data-ttu-id="0dc66-196">在此示例中，网格中有3个区域： " **top**"、" **bottom1** " 和 " **bottom2**"。</span><span class="sxs-lookup"><span data-stu-id="0dc66-196">In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.</span></span>  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="探索网格" lightbox="../media/grid-show-area-names.msft.png":::
   **<span data-ttu-id="0dc66-198">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="0dc66-198">Show area names</span></span>**  
:::image-end:::  

### <span data-ttu-id="0dc66-199">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="0dc66-199">Extend grid lines</span></span>  

<span data-ttu-id="0dc66-200">启用 " **扩展网格线** " 复选框，将网格线沿每个轴延伸到视区的边缘。</span><span class="sxs-lookup"><span data-stu-id="0dc66-200">Enable the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.</span></span>  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="探索网格" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **<span data-ttu-id="0dc66-202">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="0dc66-202">Extend grid lines</span></span>**  
:::image-end:::  

## <span data-ttu-id="0dc66-203">网格覆盖</span><span class="sxs-lookup"><span data-stu-id="0dc66-203">Grid overlays</span></span>  

<span data-ttu-id="0dc66-204">" **网格覆盖** " 部分包含页面上显示的网格的列表，每个网格都有一个复选框和各种选项。</span><span class="sxs-lookup"><span data-stu-id="0dc66-204">The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.</span></span>  

### <span data-ttu-id="0dc66-205">启用多个网格的重叠视图</span><span class="sxs-lookup"><span data-stu-id="0dc66-205">Enable overlay views of multiple grids</span></span>  

<!--todo: @zoher verify and provide updates -->  

<span data-ttu-id="0dc66-206">若要显示多个网格的覆盖网格，请选择网格每个名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="0dc66-206">To display the overlay grid for multiple grids, choose the checkbox next to each name of the grid.</span></span>  <span data-ttu-id="0dc66-207">在此示例中，已启用2个网格覆盖，每个网格覆盖都以不同颜色表示。</span><span class="sxs-lookup"><span data-stu-id="0dc66-207">In the example, there are 2 grid overlays enabled that are each represented with different colors.</span></span>  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="探索网格" lightbox="../media/grid-grid-overlays.msft.png":::
   <span data-ttu-id="0dc66-209">启用多个网格的重叠视图</span><span class="sxs-lookup"><span data-stu-id="0dc66-209">Enable overlay views of multiple grids</span></span>  
:::image-end:::  

### <span data-ttu-id="0dc66-210">自定义网格覆盖色</span><span class="sxs-lookup"><span data-stu-id="0dc66-210">Customize the grid overlay color</span></span>  

<span data-ttu-id="0dc66-211">若要打开颜色选取器并自定义网格覆盖颜色，请选择网格覆盖名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="0dc66-211">To open the color picker and customize the grid overlay color, choose the box next to the name of the grid overlay.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="探索网格" lightbox="../media/grid-grid-overlays-color.msft.png":::
   <span data-ttu-id="0dc66-213">自定义网格覆盖色</span><span class="sxs-lookup"><span data-stu-id="0dc66-213">Customize the grid overlay color</span></span>  
:::image-end:::  

### <span data-ttu-id="0dc66-214">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="0dc66-214">Highlight the grid</span></span>  

<span data-ttu-id="0dc66-215">若要突出显示 " **元素** " 面板中的 HTML 元素并在网页上滚动到该元素，请选择 " **元素" 面板中的 "显示元素** "， (![ "元素" 面板中的 "显示元素" 图标 ][ImageShowElementInElementsPanelIcon] \ ) 图标。</span><span class="sxs-lookup"><span data-stu-id="0dc66-215">To highlight the HTML element in the **Elements** panel and scroll to it on the webpage, choose the **Show element in the Elements panel** \(![Show element in the Elements panel icon][ImageShowElementInElementsPanelIcon]\) icon.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="探索网格" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   <span data-ttu-id="0dc66-217">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="0dc66-217">Highlight the grid</span></span>  
:::image-end:::  

## <span data-ttu-id="0dc66-218">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="0dc66-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageShowElementInElementsPanelIcon]: ../media/show-element-in-element-panel-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS 网格 |jec"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS 网格 |jec"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局 |MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "使用命名网格线的布局 |MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "带有 CSS 网格的基于行的位置 |MDN"  

> [!NOTE]
> <span data-ttu-id="0dc66-225">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0dc66-225">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0dc66-226">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/css/grid) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。</span><span class="sxs-lookup"><span data-stu-id="0dc66-226">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0dc66-228">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0dc66-228">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
