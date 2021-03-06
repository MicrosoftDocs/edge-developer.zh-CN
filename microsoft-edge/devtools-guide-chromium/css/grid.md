---
description: 了解如何使用 Microsoft Edge DevTools 查看和更改页面 CSS 的 CSS。
title: 检查 Microsoft Edge DevTools 中的 CSS 网格
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 5e4b20690eac3a692f6428f391def102a4f78ecb
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398768"
---
# <a name="inspect-css-grid"></a><span data-ttu-id="e3932-104">检查 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="e3932-104">Inspect CSS Grid</span></span>  

<span data-ttu-id="e3932-105">本文将引导你识别网站上 CSS 网格和使用可自定义网格覆盖调试网格布局问题。</span><span class="sxs-lookup"><span data-stu-id="e3932-105">This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.</span></span>  

<span data-ttu-id="e3932-106">本文中的图表中使用的示例取自以下网页。</span><span class="sxs-lookup"><span data-stu-id="e3932-106">The examples used in the figures in this article are taken from the following webpages.</span></span>  

*   [<span data-ttu-id="e3932-107">"新鲜结果"框</span><span class="sxs-lookup"><span data-stu-id="e3932-107">Fruit box</span></span>][JecFyiDemoCssGridFruit]  
*   [<span data-ttu-id="e3932-108">"包装箱"</span><span class="sxs-lookup"><span data-stu-id="e3932-108">Snack box</span></span>][JecFyiDemoCssGridSnack]  

## <a name="before-you-begin"></a><span data-ttu-id="e3932-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="e3932-109">Before you begin</span></span>  

<span data-ttu-id="e3932-110">CSS 网格是一种强大的 Web 布局范例。</span><span class="sxs-lookup"><span data-stu-id="e3932-110">CSS Grid is a powerful layout paradigm for the web.</span></span>  <span data-ttu-id="e3932-111">MDN 上的 [CSS 网格][MdnCssGridLayout] 布局指南是开始了解 CSS 网格和许多功能的一个很好的位置。</span><span class="sxs-lookup"><span data-stu-id="e3932-111">A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide][MdnCssGridLayout] on MDN.</span></span>  

## <a name="discover-css-grids"></a><span data-ttu-id="e3932-112">发现 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="e3932-112">Discover CSS grids</span></span>  

<span data-ttu-id="e3932-113">如果页面上的 HTML 元素已应用或已应用，则"元素"面板中旁边会显示 `display: grid` `display: inline-grid` `grid` [锁][DevtoolsGuideChromiumOpen] 屏提醒。</span><span class="sxs-lookup"><span data-stu-id="e3932-113">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements][DevtoolsGuideChromiumOpen] panel.</span></span>  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="发现网格" lightbox="../media/grid-discover-grid.msft.png":::
   <span data-ttu-id="e3932-115">发现网格</span><span class="sxs-lookup"><span data-stu-id="e3932-115">Discover grid</span></span>  
:::image-end:::  

<span data-ttu-id="e3932-116">选择锁屏提醒以切换页面上网格覆盖的显示。</span><span class="sxs-lookup"><span data-stu-id="e3932-116">Choose the badge to toggle the display of a grid overlay on the page.</span></span>  <span data-ttu-id="e3932-117">覆盖层显示在元素上，其布局与网格类似，以显示网格线和轨的位置：</span><span class="sxs-lookup"><span data-stu-id="e3932-117">The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:</span></span>  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="切换网格锁屏提醒" lightbox="../media/grid-highlight-grid.msft.png":::
   <span data-ttu-id="e3932-119">切换网格锁屏提醒</span><span class="sxs-lookup"><span data-stu-id="e3932-119">Toggle grid badge</span></span>  
:::image-end:::  

<span data-ttu-id="e3932-120">打开 **"布局"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="e3932-120">Open the **Layout** pane.</span></span>  <span data-ttu-id="e3932-121">当在页面上包含网格时，布局窗格包括\*\*\*\* 一个**Grid**部分，其中包含用于查看网格的多种选项。</span><span class="sxs-lookup"><span data-stu-id="e3932-121">When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.</span></span>  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="布局窗格" lightbox="../media/grid-layout-pane.msft.png":::
   <span data-ttu-id="e3932-123">**布局** 窗格</span><span class="sxs-lookup"><span data-stu-id="e3932-123">**Layout** pane</span></span>  
:::image-end:::  

<span data-ttu-id="e3932-124">" **布局** "窗格中的 **"网格** "部分包含以下 2 个子部分。</span><span class="sxs-lookup"><span data-stu-id="e3932-124">The **Grid** section in the **Layout** pane contains the following 2 sub-sections.</span></span>  

*   <span data-ttu-id="e3932-125">覆盖显示设置</span><span class="sxs-lookup"><span data-stu-id="e3932-125">Overlay display settings</span></span>  
*   <span data-ttu-id="e3932-126">网格覆盖</span><span class="sxs-lookup"><span data-stu-id="e3932-126">Grid overlays</span></span>  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <a name="overlay-display-settings"></a><span data-ttu-id="e3932-127">覆盖显示设置</span><span class="sxs-lookup"><span data-stu-id="e3932-127">Overlay display settings</span></span>  

<span data-ttu-id="e3932-128">覆盖 **显示设置由** 以下 2 部分组成。</span><span class="sxs-lookup"><span data-stu-id="e3932-128">The **Overlay display settings** consists of following 2 parts.</span></span>  

*   <span data-ttu-id="e3932-129">从下拉菜单中选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="e3932-129">Choose one of the following options from the dropdown menu.</span></span>  
    
    | <span data-ttu-id="e3932-130">行选项</span><span class="sxs-lookup"><span data-stu-id="e3932-130">Line option</span></span> | <span data-ttu-id="e3932-131">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3932-131">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="e3932-132">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="e3932-132">Hide line labels</span></span>** | <span data-ttu-id="e3932-133">隐藏每个网格覆盖线的标签。</span><span class="sxs-lookup"><span data-stu-id="e3932-133">Hide the labels of the lines for each grid overlay.</span></span> |  
    | **<span data-ttu-id="e3932-134">显示行号</span><span class="sxs-lookup"><span data-stu-id="e3932-134">Show line numbers</span></span>** | <span data-ttu-id="e3932-135">显示每个网格覆盖 \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="e3932-135">Display the numbers of the lines for each grid overlay \(selected by default\).</span></span> |  
    | **<span data-ttu-id="e3932-136">显示行名称</span><span class="sxs-lookup"><span data-stu-id="e3932-136">Show line names</span></span>** | <span data-ttu-id="e3932-137">提供名称时，显示每个网格覆盖层线条的名称。</span><span class="sxs-lookup"><span data-stu-id="e3932-137">Display the names of the lines for each grid overlay when names are provided.</span></span> |  
    
*  <span data-ttu-id="e3932-138">选择以下选项旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="e3932-138">Choose the checkbox next the following options.</span></span>  
    
    | <span data-ttu-id="e3932-139">选项</span><span class="sxs-lookup"><span data-stu-id="e3932-139">Option</span></span> | <span data-ttu-id="e3932-140">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3932-140">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="e3932-141">显示轨大小</span><span class="sxs-lookup"><span data-stu-id="e3932-141">Show track sizes</span></span>**  | <span data-ttu-id="e3932-142">显示 \ (或隐藏\) 跟踪的大小。</span><span class="sxs-lookup"><span data-stu-id="e3932-142">Display \(or hide\) the sizes of the tracks.</span></span> |  
    | **<span data-ttu-id="e3932-143">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="e3932-143">Show area names</span></span>** | <span data-ttu-id="e3932-144">当提供 (时，) \隐藏\隐藏区域名称。</span><span class="sxs-lookup"><span data-stu-id="e3932-144">Display \(or hide\) the names of the area, when names are provided.</span></span> |  
    | **<span data-ttu-id="e3932-145">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="e3932-145">Extend grid lines</span></span>** | <span data-ttu-id="e3932-146">显示 \ (或隐藏\) 沿每个轴的网格尺寸的扩展。</span><span class="sxs-lookup"><span data-stu-id="e3932-146">Displays \(or hides\) the extensions of the grid dimensions along each axis.</span></span>  <span data-ttu-id="e3932-147">默认情况下，网格线仅在元素内显示，或 `display: grid` CSS `display: inline-grid` 设置在元素内。</span><span class="sxs-lookup"><span data-stu-id="e3932-147">By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it.</span></span> |  
    
<span data-ttu-id="e3932-148">以下各节提供每个覆盖显示 **设置的详细信息**。</span><span class="sxs-lookup"><span data-stu-id="e3932-148">The following sections provide details for each of the **Overlay display settings**.</span></span>  

### <a name="show-line-numbers"></a><span data-ttu-id="e3932-149">显示行号</span><span class="sxs-lookup"><span data-stu-id="e3932-149">Show line numbers</span></span>  

<span data-ttu-id="e3932-150">默认情况下，正负行号显示在网格覆盖上。</span><span class="sxs-lookup"><span data-stu-id="e3932-150">By default, the positive and negative line numbers are displayed on the grid overlay.</span></span>  

<span data-ttu-id="e3932-151">有关网格覆盖层中负数的信息，请导航到使用 CSS Grid 的基于 [行的位置][MdnLineBasedPlacementCssGrid]。</span><span class="sxs-lookup"><span data-stu-id="e3932-151">For more information about negative numbers in the grid overlay, navigate to [Line-based placement with CSS Grid][MdnLineBasedPlacementCssGrid].</span></span>  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="显示行号" lightbox="../media/grid-show-line-numbers.msft.png":::
   <span data-ttu-id="e3932-153">显示行号</span><span class="sxs-lookup"><span data-stu-id="e3932-153">Display line numbers</span></span>  
:::image-end:::  

### <a name="hide-line-labels"></a><span data-ttu-id="e3932-154">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="e3932-154">Hide line labels</span></span>  

<span data-ttu-id="e3932-155">选择 **"隐藏行标签** "以隐藏行号。</span><span class="sxs-lookup"><span data-stu-id="e3932-155">Choose **Hide line labels** to hide the line numbers.</span></span>  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="隐藏行标签" lightbox="../media/grid-hide-line-labels.msft.png":::
   <span data-ttu-id="e3932-157">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="e3932-157">Hide line labels</span></span>  
:::image-end:::  

### <a name="show-line-names"></a><span data-ttu-id="e3932-158">显示行名称</span><span class="sxs-lookup"><span data-stu-id="e3932-158">Show line names</span></span>  

<span data-ttu-id="e3932-159">有关网格覆盖层中线条名称的信息，请导航到 [使用命名网格线布局][MdnLayoutUsingNamedGridLines]。</span><span class="sxs-lookup"><span data-stu-id="e3932-159">For more information about line names in the grid overlay, navigate to [Layout using named grid lines][MdnLayoutUsingNamedGridLines].</span></span>  

<span data-ttu-id="e3932-160">选择 **"显示行名称** "以查看行名称而不是数字。</span><span class="sxs-lookup"><span data-stu-id="e3932-160">Choose **Show line names** to view the line names instead of numbers.</span></span>  <span data-ttu-id="e3932-161">在示例中，4 行的名称为： `left` 、 `middle1` 和 `middle2` `right` 。</span><span class="sxs-lookup"><span data-stu-id="e3932-161">In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.</span></span>  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="显示行名称" lightbox="../media/grid-show-line-names.msft.png":::
   **<span data-ttu-id="e3932-163">显示行名称</span><span class="sxs-lookup"><span data-stu-id="e3932-163">Show line names</span></span>**  
:::image-end:::  

### <a name="show-track-sizes"></a><span data-ttu-id="e3932-164">显示轨大小</span><span class="sxs-lookup"><span data-stu-id="e3932-164">Show track sizes</span></span>  

<span data-ttu-id="e3932-165">启用 **"显示轨大小"** 复选框以查看网格的轨大小。</span><span class="sxs-lookup"><span data-stu-id="e3932-165">Enable the **Show track sizes** checkbox to view the track sizes of the grid.</span></span>  

<span data-ttu-id="e3932-166">DevTools 显示 `[authored size]` 并 `[computed size]` 在每个行标签中。</span><span class="sxs-lookup"><span data-stu-id="e3932-166">DevTools displays `[authored size]` and `[computed size]` in each line label.</span></span>  

| <span data-ttu-id="e3932-167">大小</span><span class="sxs-lookup"><span data-stu-id="e3932-167">Size</span></span> | <span data-ttu-id="e3932-168">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3932-168">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="e3932-169">创作大小</span><span class="sxs-lookup"><span data-stu-id="e3932-169">authored size</span></span>** | <span data-ttu-id="e3932-170">如果尚未定义\ (，则省略样式表 \) 。</span><span class="sxs-lookup"><span data-stu-id="e3932-170">The size defined in stylesheet \(omitted if not defined\).</span></span> |  
| **<span data-ttu-id="e3932-171">计算大小</span><span class="sxs-lookup"><span data-stu-id="e3932-171">computed size</span></span>** | <span data-ttu-id="e3932-172">屏幕上的实际大小。</span><span class="sxs-lookup"><span data-stu-id="e3932-172">The actual size on screen.</span></span> |  

<span data-ttu-id="e3932-173">在演示中， `snack-box` 列大小在 CSS 中 `grid-template-columns:1fr 2fr;` 定义。</span><span class="sxs-lookup"><span data-stu-id="e3932-173">In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.</span></span>  <span data-ttu-id="e3932-174">因此，列行标签同时显示创作和计算的大小。</span><span class="sxs-lookup"><span data-stu-id="e3932-174">Therefore, the column line labels display both authored and computed sizes.</span></span>  

| <span data-ttu-id="e3932-175">轨大小</span><span class="sxs-lookup"><span data-stu-id="e3932-175">Track size</span></span> | <span data-ttu-id="e3932-176">创作大小</span><span class="sxs-lookup"><span data-stu-id="e3932-176">Authored size</span></span> | <span data-ttu-id="e3932-177">计算大小</span><span class="sxs-lookup"><span data-stu-id="e3932-177">Computed size</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e3932-178">**1fr** &#x2022; **96.66px**</span><span class="sxs-lookup"><span data-stu-id="e3932-178">**1fr** &#x2022; **96.66px**</span></span> | <span data-ttu-id="e3932-179">1fr</span><span class="sxs-lookup"><span data-stu-id="e3932-179">1fr</span></span> | <span data-ttu-id="e3932-180">96.66px</span><span class="sxs-lookup"><span data-stu-id="e3932-180">96.66px</span></span> |  
| <span data-ttu-id="e3932-181">**2fr** &#x2022; **193.32px**</span><span class="sxs-lookup"><span data-stu-id="e3932-181">**2fr** &#x2022; **193.32px**</span></span> | <span data-ttu-id="e3932-182">2fr</span><span class="sxs-lookup"><span data-stu-id="e3932-182">2fr</span></span> | <span data-ttu-id="e3932-183">193.32px</span><span class="sxs-lookup"><span data-stu-id="e3932-183">193.32px</span></span> |  

<span data-ttu-id="e3932-184">行行标签仅显示计算的大小，因为样式表没有定义行大小。</span><span class="sxs-lookup"><span data-stu-id="e3932-184">The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.</span></span>  

| <span data-ttu-id="e3932-185">轨大小</span><span class="sxs-lookup"><span data-stu-id="e3932-185">Track size</span></span> | <span data-ttu-id="e3932-186">创作大小</span><span class="sxs-lookup"><span data-stu-id="e3932-186">Authored size</span></span> | <span data-ttu-id="e3932-187">计算大小</span><span class="sxs-lookup"><span data-stu-id="e3932-187">Computed size</span></span> |  
|:--- |:--- |:--- |  
| **<span data-ttu-id="e3932-188">80px</span><span class="sxs-lookup"><span data-stu-id="e3932-188">80px</span></span>** | &nbsp;| <span data-ttu-id="e3932-189">80px</span><span class="sxs-lookup"><span data-stu-id="e3932-189">80px</span></span> |  
| **<span data-ttu-id="e3932-190">80px</span><span class="sxs-lookup"><span data-stu-id="e3932-190">80px</span></span>** | &nbsp;| <span data-ttu-id="e3932-191">80px</span><span class="sxs-lookup"><span data-stu-id="e3932-191">80px</span></span> |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="显示轨大小" lightbox="../media/grid-show-track-sizes.msft.png":::
   **<span data-ttu-id="e3932-193">显示轨大小</span><span class="sxs-lookup"><span data-stu-id="e3932-193">Show track sizes</span></span>**  
:::image-end:::  

### <a name="show-area-names"></a><span data-ttu-id="e3932-194">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="e3932-194">Show area names</span></span>  

<span data-ttu-id="e3932-195">若要查看区域名称，请启用"显示 **区域名称"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e3932-195">To view the area names, enable the **Show area names** checkbox.</span></span>  <span data-ttu-id="e3932-196">在示例中，网格中有 3 个区域：**顶部**、**底部 1**和**bottom2。**</span><span class="sxs-lookup"><span data-stu-id="e3932-196">In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.</span></span>  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="显示区域名称" lightbox="../media/grid-show-area-names.msft.png":::
   **<span data-ttu-id="e3932-198">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="e3932-198">Show area names</span></span>**  
:::image-end:::  

### <a name="extend-grid-lines"></a><span data-ttu-id="e3932-199">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="e3932-199">Extend grid lines</span></span>  

<span data-ttu-id="e3932-200">启用 **"扩展网格线"** 复选框以沿每个轴将网格线扩展到视口的边缘。</span><span class="sxs-lookup"><span data-stu-id="e3932-200">Enable the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.</span></span>  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="扩展网格线" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **<span data-ttu-id="e3932-202">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="e3932-202">Extend grid lines</span></span>**  
:::image-end:::  

## <a name="grid-overlays"></a><span data-ttu-id="e3932-203">网格覆盖</span><span class="sxs-lookup"><span data-stu-id="e3932-203">Grid overlays</span></span>  

<span data-ttu-id="e3932-204">" **网格覆盖"** 部分包含页面上的网格列表，每个网格都有一个复选框，以及各种选项。</span><span class="sxs-lookup"><span data-stu-id="e3932-204">The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.</span></span>  

### <a name="enable-overlay-views-of-multiple-grids"></a><span data-ttu-id="e3932-205">启用多个网格的覆盖视图</span><span class="sxs-lookup"><span data-stu-id="e3932-205">Enable overlay views of multiple grids</span></span>  

<span data-ttu-id="e3932-206">若要显示多个网格的覆盖网格，请选中网格每个名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="e3932-206">To display the overlay grid for multiple grids, choose the checkbox next to each name of the grid.</span></span>  <span data-ttu-id="e3932-207">在示例中，启用了两个网格覆盖，每个网格覆盖层用不同的颜色表示。</span><span class="sxs-lookup"><span data-stu-id="e3932-207">In the example, there are 2 grid overlays enabled that are each represented with different colors.</span></span>  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="启用多个网格的覆盖视图" lightbox="../media/grid-grid-overlays.msft.png":::
   <span data-ttu-id="e3932-209">启用多个网格的覆盖视图</span><span class="sxs-lookup"><span data-stu-id="e3932-209">Enable overlay views of multiple grids</span></span>  
:::image-end:::  

### <a name="customize-the-grid-overlay-color"></a><span data-ttu-id="e3932-210">自定义网格覆盖颜色</span><span class="sxs-lookup"><span data-stu-id="e3932-210">Customize the grid overlay color</span></span>  

<span data-ttu-id="e3932-211">若要打开颜色选取器并自定义网格覆盖颜色，请选择网格覆盖的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="e3932-211">To open the color picker and customize the grid overlay color, choose the box next to the name of the grid overlay.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="自定义网格覆盖颜色" lightbox="../media/grid-grid-overlays-color.msft.png":::
   <span data-ttu-id="e3932-213">自定义网格覆盖颜色</span><span class="sxs-lookup"><span data-stu-id="e3932-213">Customize the grid overlay color</span></span>  
:::image-end:::  

### <a name="highlight-the-grid"></a><span data-ttu-id="e3932-214">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="e3932-214">Highlight the grid</span></span>  

<span data-ttu-id="e3932-215">若要在"元素"工具中\*\*\*\* 突出显示 HTML 元素并滚动到网页上，请选择"元素"面板\*\*\*\* \ ("元素"图标 \) 图标中的 Show ![ ][ImageShowElementInElementsPanelIcon] 元素。</span><span class="sxs-lookup"><span data-stu-id="e3932-215">To highlight the HTML element in the **Elements** tool and scroll to it on the webpage, choose the **Show element in the Elements panel** \(![Show element in the Elements panel icon][ImageShowElementInElementsPanelIcon]\) icon.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="突出显示网格" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   <span data-ttu-id="e3932-217">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="e3932-217">Highlight the grid</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e3932-218">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="e3932-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageShowElementInElementsPanelIcon]: ../media/show-element-in-element-panel-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS 网格|jec.fyi"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS 网格|jec.fyi"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局|MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "使用命名网格线布局|MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "使用 CSS 网格样式的基于线条|MDN"  

> [!NOTE]
> <span data-ttu-id="e3932-225">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e3932-225">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e3932-226">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/css/grid)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="e3932-226">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e3932-228">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e3932-228">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
