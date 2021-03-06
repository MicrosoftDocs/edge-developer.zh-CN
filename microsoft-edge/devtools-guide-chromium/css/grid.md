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
# <a name="inspect-css-grid"></a>检查 CSS 网格  

本文将引导你识别网站上 CSS 网格和使用可自定义网格覆盖调试网格布局问题。  

本文中的图表中使用的示例取自以下网页。  

*   ["新鲜结果"框][JecFyiDemoCssGridFruit]  
*   ["包装箱"][JecFyiDemoCssGridSnack]  

## <a name="before-you-begin"></a>开始之前  

CSS 网格是一种强大的 Web 布局范例。  MDN 上的 [CSS 网格][MdnCssGridLayout] 布局指南是开始了解 CSS 网格和许多功能的一个很好的位置。  

## <a name="discover-css-grids"></a>发现 CSS 网格  

如果页面上的 HTML 元素已应用或已应用，则"元素"面板中旁边会显示 `display: grid` `display: inline-grid` `grid` [锁][DevtoolsGuideChromiumOpen] 屏提醒。  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="发现网格" lightbox="../media/grid-discover-grid.msft.png":::
   发现网格  
:::image-end:::  

选择锁屏提醒以切换页面上网格覆盖的显示。  覆盖层显示在元素上，其布局与网格类似，以显示网格线和轨的位置：  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="切换网格锁屏提醒" lightbox="../media/grid-highlight-grid.msft.png":::
   切换网格锁屏提醒  
:::image-end:::  

打开 **"布局"** 窗格。  当在页面上包含网格时，布局窗格包括**** 一个**Grid**部分，其中包含用于查看网格的多种选项。  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="布局窗格" lightbox="../media/grid-layout-pane.msft.png":::
   **布局** 窗格  
:::image-end:::  

" **布局** "窗格中的 **"网格** "部分包含以下 2 个子部分。  

*   覆盖显示设置  
*   网格覆盖  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <a name="overlay-display-settings"></a>覆盖显示设置  

覆盖 **显示设置由** 以下 2 部分组成。  

*   从下拉菜单中选择以下选项之一。  
    
    | 行选项 | 详细信息 |  
    |:--- |:--- |  
    | **隐藏行标签** | 隐藏每个网格覆盖线的标签。 |  
    | **显示行号** | 显示每个网格覆盖 \ (\) 。 |  
    | **显示行名称** | 提供名称时，显示每个网格覆盖层线条的名称。 |  
    
*  选择以下选项旁边的复选框。  
    
    | 选项 | 详细信息 |  
    |:--- |:--- |  
    | **显示轨大小**  | 显示 \ (或隐藏\) 跟踪的大小。 |  
    | **显示区域名称** | 当提供 (时，) \隐藏\隐藏区域名称。 |  
    | **扩展网格线** | 显示 \ (或隐藏\) 沿每个轴的网格尺寸的扩展。  默认情况下，网格线仅在元素内显示，或 `display: grid` CSS `display: inline-grid` 设置在元素内。 |  
    
以下各节提供每个覆盖显示 **设置的详细信息**。  

### <a name="show-line-numbers"></a>显示行号  

默认情况下，正负行号显示在网格覆盖上。  

有关网格覆盖层中负数的信息，请导航到使用 CSS Grid 的基于 [行的位置][MdnLineBasedPlacementCssGrid]。  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="显示行号" lightbox="../media/grid-show-line-numbers.msft.png":::
   显示行号  
:::image-end:::  

### <a name="hide-line-labels"></a>隐藏行标签  

选择 **"隐藏行标签** "以隐藏行号。  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="隐藏行标签" lightbox="../media/grid-hide-line-labels.msft.png":::
   隐藏行标签  
:::image-end:::  

### <a name="show-line-names"></a>显示行名称  

有关网格覆盖层中线条名称的信息，请导航到 [使用命名网格线布局][MdnLayoutUsingNamedGridLines]。  

选择 **"显示行名称** "以查看行名称而不是数字。  在示例中，4 行的名称为： `left` 、 `middle1` 和 `middle2` `right` 。  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="显示行名称" lightbox="../media/grid-show-line-names.msft.png":::
   **显示行名称**  
:::image-end:::  

### <a name="show-track-sizes"></a>显示轨大小  

启用 **"显示轨大小"** 复选框以查看网格的轨大小。  

DevTools 显示 `[authored size]` 并 `[computed size]` 在每个行标签中。  

| 大小 | 详细信息 |  
|:--- |:--- |  
| **创作大小** | 如果尚未定义\ (，则省略样式表 \) 。 |  
| **计算大小** | 屏幕上的实际大小。 |  

在演示中， `snack-box` 列大小在 CSS 中 `grid-template-columns:1fr 2fr;` 定义。  因此，列行标签同时显示创作和计算的大小。  

| 轨大小 | 创作大小 | 计算大小 |  
|:--- |:--- |:--- |  
| **1fr** &#x2022; **96.66px** | 1fr | 96.66px |  
| **2fr** &#x2022; **193.32px** | 2fr | 193.32px |  

行行标签仅显示计算的大小，因为样式表没有定义行大小。  

| 轨大小 | 创作大小 | 计算大小 |  
|:--- |:--- |:--- |  
| **80px** | &nbsp;| 80px |  
| **80px** | &nbsp;| 80px |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="显示轨大小" lightbox="../media/grid-show-track-sizes.msft.png":::
   **显示轨大小**  
:::image-end:::  

### <a name="show-area-names"></a>显示区域名称  

若要查看区域名称，请启用"显示 **区域名称"** 复选框。  在示例中，网格中有 3 个区域：**顶部**、**底部 1**和**bottom2。**  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="显示区域名称" lightbox="../media/grid-show-area-names.msft.png":::
   **显示区域名称**  
:::image-end:::  

### <a name="extend-grid-lines"></a>扩展网格线  

启用 **"扩展网格线"** 复选框以沿每个轴将网格线扩展到视口的边缘。  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="扩展网格线" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **扩展网格线**  
:::image-end:::  

## <a name="grid-overlays"></a>网格覆盖  

" **网格覆盖"** 部分包含页面上的网格列表，每个网格都有一个复选框，以及各种选项。  

### <a name="enable-overlay-views-of-multiple-grids"></a>启用多个网格的覆盖视图  

若要显示多个网格的覆盖网格，请选中网格每个名称旁边的复选框。  在示例中，启用了两个网格覆盖，每个网格覆盖层用不同的颜色表示。  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="启用多个网格的覆盖视图" lightbox="../media/grid-grid-overlays.msft.png":::
   启用多个网格的覆盖视图  
:::image-end:::  

### <a name="customize-the-grid-overlay-color"></a>自定义网格覆盖颜色  

若要打开颜色选取器并自定义网格覆盖颜色，请选择网格覆盖的名称旁边的框。  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="自定义网格覆盖颜色" lightbox="../media/grid-grid-overlays-color.msft.png":::
   自定义网格覆盖颜色  
:::image-end:::  

### <a name="highlight-the-grid"></a>突出显示网格  

若要在"元素"工具中**** 突出显示 HTML 元素并滚动到网页上，请选择"元素"面板**** \ ("元素"图标 \) 图标中的 Show ![ ][ImageShowElementInElementsPanelIcon] 元素。  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="突出显示网格" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   突出显示网格  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/css/grid)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
