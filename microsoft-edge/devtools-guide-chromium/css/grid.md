---
description: 了解如何使用 Microsoft Edge DevTools 查看和更改页面 CSS 的 CSS。
title: 检查 Microsoft Edge DevTools 中的 CSS 网格
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 1fe6bd1c8efd244315fb9a38777df6ea3e9b1a4d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231095"
---
# <span data-ttu-id="5b9ed-104">检查 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="5b9ed-104">Inspect CSS Grid</span></span>  

<span data-ttu-id="5b9ed-105">本文将引导你识别网站的 CSS 网格和使用可自定义网格覆盖调试网格布局问题。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-105">This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.</span></span>  

<span data-ttu-id="5b9ed-106">本文中的图表中使用的示例取自以下网页。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-106">The examples used in the figures in this article are taken from the following webpages.</span></span>  

*   [<span data-ttu-id="5b9ed-107">"干菜"框</span><span class="sxs-lookup"><span data-stu-id="5b9ed-107">Fruit box</span></span>][JecFyiDemoCssGridFruit]  
*   [<span data-ttu-id="5b9ed-108">"箱"框</span><span class="sxs-lookup"><span data-stu-id="5b9ed-108">Snack box</span></span>][JecFyiDemoCssGridSnack]  

## <span data-ttu-id="5b9ed-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="5b9ed-109">Before you begin</span></span>  

<span data-ttu-id="5b9ed-110">CSS 网格是一种强大的 Web 布局范例。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-110">CSS Grid is a powerful layout paradigm for the web.</span></span>  <span data-ttu-id="5b9ed-111">MDN 上的 CSS 网格布局指南是开始了解 [CSS][MdnCssGridLayout] 网格和许多功能的一个很好的位置。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-111">A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide][MdnCssGridLayout] on MDN.</span></span>  

## <span data-ttu-id="5b9ed-112">发现 CSS 网格</span><span class="sxs-lookup"><span data-stu-id="5b9ed-112">Discover CSS grids</span></span>  

<span data-ttu-id="5b9ed-113">当页面上的 HTML 元素具有或应用于该元素时，该元素旁边会显示一个锁 `display: grid` `display: inline-grid` `grid` 屏提醒，显示在 ["元素][DevtoolsGuideChromiumOpen] "面板中。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-113">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements][DevtoolsGuideChromiumOpen] panel.</span></span>  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="发现网格" lightbox="../media/grid-discover-grid.msft.png":::
   <span data-ttu-id="5b9ed-115">发现网格</span><span class="sxs-lookup"><span data-stu-id="5b9ed-115">Discover grid</span></span>  
:::image-end:::  

<span data-ttu-id="5b9ed-116">选择锁屏提醒以切换页面上网格覆盖的显示。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-116">Select the badge to toggle the display of a grid overlay on the page.</span></span>  <span data-ttu-id="5b9ed-117">覆盖层显示在元素上，其布局与网格类似，以显示网格线和轨的位置：</span><span class="sxs-lookup"><span data-stu-id="5b9ed-117">The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:</span></span>  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="切换网格锁屏提醒" lightbox="../media/grid-highlight-grid.msft.png":::
   <span data-ttu-id="5b9ed-119">切换网格锁屏提醒</span><span class="sxs-lookup"><span data-stu-id="5b9ed-119">Toggle grid badge</span></span>  
:::image-end:::  

<span data-ttu-id="5b9ed-120">打开 **"布局"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-120">Open the **Layout** pane.</span></span>  <span data-ttu-id="5b9ed-121">当页面上包含网格时，布局窗格包括一\*\*\*\* 个**Grid**部分，其中包含用于查看网格的多种选项。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-121">When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.</span></span>  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="布局窗格" lightbox="../media/grid-layout-pane.msft.png":::
   <span data-ttu-id="5b9ed-123">**布局** 窗格</span><span class="sxs-lookup"><span data-stu-id="5b9ed-123">**Layout** pane</span></span>  
:::image-end:::  

<span data-ttu-id="5b9ed-124">布局 **窗格中** 的 **"网格** "部分包含以下 2 个子部分。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-124">The **Grid** section in the **Layout** pane contains the following 2 sub-sections.</span></span>  

*   <span data-ttu-id="5b9ed-125">覆盖显示设置</span><span class="sxs-lookup"><span data-stu-id="5b9ed-125">Overlay display settings</span></span>  
*   <span data-ttu-id="5b9ed-126">网格覆盖</span><span class="sxs-lookup"><span data-stu-id="5b9ed-126">Grid overlays</span></span>  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <span data-ttu-id="5b9ed-127">覆盖显示设置</span><span class="sxs-lookup"><span data-stu-id="5b9ed-127">Overlay display settings</span></span>  

<span data-ttu-id="5b9ed-128">覆盖 **显示设置由** 以下 2 部分组成。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-128">The **Overlay display settings** consists of following 2 parts.</span></span>  

*   <span data-ttu-id="5b9ed-129">从下拉菜单中选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-129">Choose one of the following options from the dropdown menu.</span></span>  
    
    | <span data-ttu-id="5b9ed-130">行选项</span><span class="sxs-lookup"><span data-stu-id="5b9ed-130">Line option</span></span> | <span data-ttu-id="5b9ed-131">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b9ed-131">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="5b9ed-132">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="5b9ed-132">Hide line labels</span></span>** | <span data-ttu-id="5b9ed-133">隐藏每个网格覆盖线的标签。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-133">Hide the labels of the lines for each grid overlay.</span></span> |  
    | **<span data-ttu-id="5b9ed-134">显示行号</span><span class="sxs-lookup"><span data-stu-id="5b9ed-134">Show line numbers</span></span>** | <span data-ttu-id="5b9ed-135">显示每个网格覆盖 \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-135">Display the numbers of the lines for each grid overlay \(selected by default\).</span></span> |  
    | **<span data-ttu-id="5b9ed-136">显示行名称</span><span class="sxs-lookup"><span data-stu-id="5b9ed-136">Show line names</span></span>** | <span data-ttu-id="5b9ed-137">提供名称时，显示每个网格覆盖层的线条名称。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-137">Display the names of the lines for each grid overlay when names are provided.</span></span> |  
    
*  <span data-ttu-id="5b9ed-138">选择以下选项旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-138">Choose the checkbox next the following options.</span></span>  
    
    | <span data-ttu-id="5b9ed-139">选项</span><span class="sxs-lookup"><span data-stu-id="5b9ed-139">Option</span></span> | <span data-ttu-id="5b9ed-140">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b9ed-140">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="5b9ed-141">显示轨大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-141">Show track sizes</span></span>**  | <span data-ttu-id="5b9ed-142">显示 \ (或 hide\) 跟踪的大小。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-142">Display \(or hide\) the sizes of the tracks.</span></span> |  
    | **<span data-ttu-id="5b9ed-143">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="5b9ed-143">Show area names</span></span>** | <span data-ttu-id="5b9ed-144">当提供 (时，显示 \) 或 hide\) 区域的名称。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-144">Display \(or hide\) the names of the area, when names are provided.</span></span> |  
    | **<span data-ttu-id="5b9ed-145">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="5b9ed-145">Extend grid lines</span></span>** | <span data-ttu-id="5b9ed-146">显示 \ (或隐藏\) 沿每个轴的网格尺寸的扩展。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-146">Displays \(or hides\) the extensions of the grid dimensions along each axis.</span></span>  <span data-ttu-id="5b9ed-147">默认情况下，网格线仅在元素内显示，或者 `display: grid` `display: inline-grid` 对元素设置了 CSS。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-147">By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it.</span></span> |  
    
<span data-ttu-id="5b9ed-148">以下各节提供每个覆盖显示 **设置的详细信息**。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-148">The following sections provide details for each of the **Overlay display settings**.</span></span>  

### <span data-ttu-id="5b9ed-149">显示行号</span><span class="sxs-lookup"><span data-stu-id="5b9ed-149">Show line numbers</span></span>  

<span data-ttu-id="5b9ed-150">默认情况下，正负行号显示在网格覆盖上。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-150">By default, the positive and negative line numbers are displayed on the grid overlay.</span></span>  

<span data-ttu-id="5b9ed-151">有关网格覆盖层中的负数详细信息，请导航到 CSS 网格的基于 [行的位置][MdnLineBasedPlacementCssGrid]。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-151">For more information about negative numbers in the grid overlay, navigate to [Line-based placement with CSS Grid][MdnLineBasedPlacementCssGrid].</span></span>  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="显示行号" lightbox="../media/grid-show-line-numbers.msft.png":::
   <span data-ttu-id="5b9ed-153">显示行号</span><span class="sxs-lookup"><span data-stu-id="5b9ed-153">Display line numbers</span></span>  
:::image-end:::  

### <span data-ttu-id="5b9ed-154">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="5b9ed-154">Hide line labels</span></span>  

<span data-ttu-id="5b9ed-155">选择 **"隐藏行标签** "可隐藏行号。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-155">Select **Hide line labels** to hide the line numbers.</span></span>  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="隐藏行标签" lightbox="../media/grid-hide-line-labels.msft.png":::
   <span data-ttu-id="5b9ed-157">隐藏行标签</span><span class="sxs-lookup"><span data-stu-id="5b9ed-157">Hide line labels</span></span>  
:::image-end:::  

### <span data-ttu-id="5b9ed-158">显示行名称</span><span class="sxs-lookup"><span data-stu-id="5b9ed-158">Show line names</span></span>  

<span data-ttu-id="5b9ed-159">有关网格覆盖层中线条名称的信息，请导航到 [使用命名网格线的布局][MdnLayoutUsingNamedGridLines]。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-159">For more information about line names in the grid overlay, navigate to [Layout using named grid lines][MdnLayoutUsingNamedGridLines].</span></span>  

<span data-ttu-id="5b9ed-160">选择 **"显示行名称** "以查看行名称而不是数字。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-160">Select **Show line names** to view the line names instead of numbers.</span></span>  <span data-ttu-id="5b9ed-161">在示例中，4 行的名称为： `left` 、 `middle1` 和 `middle2` `right` 。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-161">In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.</span></span>  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="显示行名称" lightbox="../media/grid-show-line-names.msft.png":::
   **<span data-ttu-id="5b9ed-163">显示行名称</span><span class="sxs-lookup"><span data-stu-id="5b9ed-163">Show line names</span></span>**  
:::image-end:::  

### <span data-ttu-id="5b9ed-164">显示轨大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-164">Show track sizes</span></span>  

<span data-ttu-id="5b9ed-165">启用 **"显示轨大小"** 复选框以查看网格的轨大小。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-165">Enable the **Show track sizes** checkbox to view the track sizes of the grid.</span></span>  

<span data-ttu-id="5b9ed-166">DevTools 显示 `[authored size]` 并 `[computed size]` 显示在每个行标签中。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-166">DevTools displays `[authored size]` and `[computed size]` in each line label.</span></span>  

| <span data-ttu-id="5b9ed-167">大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-167">Size</span></span> | <span data-ttu-id="5b9ed-168">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b9ed-168">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="5b9ed-169">创作大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-169">authored size</span></span>** | <span data-ttu-id="5b9ed-170">如果尚未定义\ (，则省略样式表 \) 。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-170">The size defined in stylesheet \(omitted if not defined\).</span></span> |  
| **<span data-ttu-id="5b9ed-171">计算大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-171">computed size</span></span>** | <span data-ttu-id="5b9ed-172">屏幕上的实际大小。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-172">The actual size on screen.</span></span> |  

<span data-ttu-id="5b9ed-173">在演示中， `snack-box` 列大小在 CSS 中 `grid-template-columns:1fr 2fr;` 定义。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-173">In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.</span></span>  <span data-ttu-id="5b9ed-174">因此，列行标签同时显示创作和计算的大小。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-174">Therefore, the column line labels display both authored and computed sizes.</span></span>  

| <span data-ttu-id="5b9ed-175">跟踪大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-175">Track size</span></span> | <span data-ttu-id="5b9ed-176">创作大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-176">Authored size</span></span> | <span data-ttu-id="5b9ed-177">计算大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-177">Computed size</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="5b9ed-178">**1fr** &#x2022; **96.66px**</span><span class="sxs-lookup"><span data-stu-id="5b9ed-178">**1fr** &#x2022; **96.66px**</span></span> | <span data-ttu-id="5b9ed-179">1fr</span><span class="sxs-lookup"><span data-stu-id="5b9ed-179">1fr</span></span> | <span data-ttu-id="5b9ed-180">96.66px</span><span class="sxs-lookup"><span data-stu-id="5b9ed-180">96.66px</span></span> |  
| <span data-ttu-id="5b9ed-181">**2fr** &#x2022; **193.32px**</span><span class="sxs-lookup"><span data-stu-id="5b9ed-181">**2fr** &#x2022; **193.32px**</span></span> | <span data-ttu-id="5b9ed-182">2fr</span><span class="sxs-lookup"><span data-stu-id="5b9ed-182">2fr</span></span> | <span data-ttu-id="5b9ed-183">193.32px</span><span class="sxs-lookup"><span data-stu-id="5b9ed-183">193.32px</span></span> |  

<span data-ttu-id="5b9ed-184">行行标签仅显示计算的大小，因为样式表没有定义行大小。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-184">The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.</span></span>  

| <span data-ttu-id="5b9ed-185">跟踪大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-185">Track size</span></span> | <span data-ttu-id="5b9ed-186">创作大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-186">Authored size</span></span> | <span data-ttu-id="5b9ed-187">计算大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-187">Computed size</span></span> |  
|:--- |:--- |:--- |  
| **<span data-ttu-id="5b9ed-188">80px</span><span class="sxs-lookup"><span data-stu-id="5b9ed-188">80px</span></span>** | &nbsp;| <span data-ttu-id="5b9ed-189">80px</span><span class="sxs-lookup"><span data-stu-id="5b9ed-189">80px</span></span> |  
| **<span data-ttu-id="5b9ed-190">80px</span><span class="sxs-lookup"><span data-stu-id="5b9ed-190">80px</span></span>** | &nbsp;| <span data-ttu-id="5b9ed-191">80px</span><span class="sxs-lookup"><span data-stu-id="5b9ed-191">80px</span></span> |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="显示轨大小" lightbox="../media/grid-show-track-sizes.msft.png":::
   **<span data-ttu-id="5b9ed-193">显示轨大小</span><span class="sxs-lookup"><span data-stu-id="5b9ed-193">Show track sizes</span></span>**  
:::image-end:::  

### <span data-ttu-id="5b9ed-194">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="5b9ed-194">Show area names</span></span>  

<span data-ttu-id="5b9ed-195">若要查看区域名称，请启用"显示 **区域名称"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-195">To view the area names, enable the **Show area names** checkbox.</span></span>  <span data-ttu-id="5b9ed-196">在示例中，网格中有 3 个区域：**顶部**、**底部 1**和**bottom2。**</span><span class="sxs-lookup"><span data-stu-id="5b9ed-196">In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.</span></span>  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="显示区域名称" lightbox="../media/grid-show-area-names.msft.png":::
   **<span data-ttu-id="5b9ed-198">显示区域名称</span><span class="sxs-lookup"><span data-stu-id="5b9ed-198">Show area names</span></span>**  
:::image-end:::  

### <span data-ttu-id="5b9ed-199">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="5b9ed-199">Extend grid lines</span></span>  

<span data-ttu-id="5b9ed-200">启用 **"扩展网格线"** 复选框以沿每个轴将网格线扩展到视口的边缘。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-200">Enable the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.</span></span>  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="扩展网格线" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **<span data-ttu-id="5b9ed-202">扩展网格线</span><span class="sxs-lookup"><span data-stu-id="5b9ed-202">Extend grid lines</span></span>**  
:::image-end:::  

## <span data-ttu-id="5b9ed-203">网格覆盖</span><span class="sxs-lookup"><span data-stu-id="5b9ed-203">Grid overlays</span></span>  

<span data-ttu-id="5b9ed-204">" **网格覆盖"** 部分包含页面上的网格列表，每个网格都有一个复选框，以及各种选项。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-204">The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.</span></span>  

### <span data-ttu-id="5b9ed-205">启用多个网格的覆盖视图</span><span class="sxs-lookup"><span data-stu-id="5b9ed-205">Enable overlay views of multiple grids</span></span>  

<span data-ttu-id="5b9ed-206">若要显示多个网格的覆盖网格，请选中每个网格名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-206">To display the overlay grid for multiple grids, choose the checkbox next to each name of the grid.</span></span>  <span data-ttu-id="5b9ed-207">在示例中，启用了 2 个网格覆盖，每个网格覆盖层用不同的颜色表示。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-207">In the example, there are 2 grid overlays enabled that are each represented with different colors.</span></span>  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="启用多个网格的覆盖视图" lightbox="../media/grid-grid-overlays.msft.png":::
   <span data-ttu-id="5b9ed-209">启用多个网格的覆盖视图</span><span class="sxs-lookup"><span data-stu-id="5b9ed-209">Enable overlay views of multiple grids</span></span>  
:::image-end:::  

### <span data-ttu-id="5b9ed-210">自定义网格覆盖颜色</span><span class="sxs-lookup"><span data-stu-id="5b9ed-210">Customize the grid overlay color</span></span>  

<span data-ttu-id="5b9ed-211">若要打开颜色选取器并自定义网格覆盖颜色，请选择网格覆盖的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-211">To open the color picker and customize the grid overlay color, choose the box next to the name of the grid overlay.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="自定义网格覆盖颜色" lightbox="../media/grid-grid-overlays-color.msft.png":::
   <span data-ttu-id="5b9ed-213">自定义网格覆盖颜色</span><span class="sxs-lookup"><span data-stu-id="5b9ed-213">Customize the grid overlay color</span></span>  
:::image-end:::  

### <span data-ttu-id="5b9ed-214">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="5b9ed-214">Highlight the grid</span></span>  

<span data-ttu-id="5b9ed-215">若要突出显示"元素"面板中的\*\*\*\* HTML 元素并滚动到网页上，请选择"元素"面板\*\*\*\* \ ("元素"图标 \) 图标中的 Show ![ ][ImageShowElementInElementsPanelIcon] 元素。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-215">To highlight the HTML element in the **Elements** panel and scroll to it on the webpage, choose the **Show element in the Elements panel** \(![Show element in the Elements panel icon][ImageShowElementInElementsPanelIcon]\) icon.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="突出显示网格" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   <span data-ttu-id="5b9ed-217">突出显示网格</span><span class="sxs-lookup"><span data-stu-id="5b9ed-217">Highlight the grid</span></span>  
:::image-end:::  

## <span data-ttu-id="5b9ed-218">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="5b9ed-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageShowElementInElementsPanelIcon]: ../media/show-element-in-element-panel-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS 网格 |jec.fyi"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS 网格 |jec.fyi"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局 |MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "使用命名网格线的布局 |MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "使用 CSS 网格的基于线条的位置 |MDN"  

> [!NOTE]
> <span data-ttu-id="5b9ed-225">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-225">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5b9ed-226">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/css/grid)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-226">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5b9ed-228">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5b9ed-228">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
