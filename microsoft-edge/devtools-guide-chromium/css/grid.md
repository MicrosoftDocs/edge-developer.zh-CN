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
# <a name="inspect-css-grid"></a>检查 CSS 网格  

本文将引导你识别网站上的 CSS 网格并使用可自定义的网格叠加层来调试网格布局问题。  

本文图表中使用的示例来自以下网页。  

*   [水果盒][JecFyiDemoCssGridFruit]  
*   [小吃盒][JecFyiDemoCssGridSnack]  

## <a name="before-you-begin"></a>开始之前  

CSS 网格是一种强大的 Web 布局范例。  可通过 MDN 上的 [CSS 网格布局指南][MdnCssGridLayout]开始了解 CSS 网格和许多功能。  

## <a name="discover-css-grids"></a>探索 CSS 网格  

如果页面上的 HTML 元素应用了 `display: grid` 或 `display: inline-grid`，则“[元素][DevtoolsGuideChromiumOpen]”面板中该元素的旁边会显示一个 `grid` 徽章。  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="探索网格" lightbox="../media/grid-discover-grid.msft.png":::
   探索网格  
:::image-end:::  

选择徽章以切换页面上的网格叠加层显示。  叠加层显示在元素上方，布局类似于网格，可显示网格线和轨道的位置：  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="切换网格徽章" lightbox="../media/grid-highlight-grid.msft.png":::
   切换网格徽章  
:::image-end:::  

打开“**布局**”窗格。  当网格包含在页面上时，“**布局**”窗格将包括“**网格**”部分，其中包含许多用于查看网格的选项。  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="布局窗格" lightbox="../media/grid-layout-pane.msft.png":::
   “**布局**”窗格  
:::image-end:::  

“**布局**”窗格中的“**网格**”部分包含以下 2 个子部分。  

*   叠加层显示设置  
*   网格叠加层  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <a name="overlay-display-settings"></a>叠加层显示设置  

“**叠加层显示设置**”由以下 2 部分组成。  

*   从下拉菜单中选择以下选项之一。  
    
    | 线条选项 | 详细信息 |  
    |:--- |:--- |  
    | **隐藏线条标签** | 隐藏每个网格叠加层的线条标签。 |  
    | **显示线条编号** | 显示每个网格叠加层的线条编号（默认选中）。 |  
    | **显示线条名称** | 显示每个网格叠加层的线条名称（倘若提供了名称）。 |  
    
*  选中以下选项旁边的复选框。  
    
    | 选项 | 详细信息 |  
    |:--- |:--- |  
    | **显示轨道大小**  | 显示（或隐藏）轨道的大小。 |  
    | **显示区域名称** | 显示（或隐藏）区域的名称（倘若提供了名称）。 |  
    | **延伸网格线** | 显示（或隐藏）沿每个轴的网格尺寸延伸。  默认情况下，网格线仅在设置了 `display: grid` 或 `display: inline-grid` CSS 的元素内显示。 |  
    
以下各节提供了每个**叠加层显示设置**的详细信息。  

### <a name="show-line-numbers"></a>显示线条编号  

默认情况下，网格叠加层上会显示正数和负数线条编号。  

有关网格叠加层中负数的详细信息，请导航至“[CSS 网格基于线条的放置][MdnLineBasedPlacementCssGrid]”。  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="显示线条编号" lightbox="../media/grid-show-line-numbers.msft.png":::
   显示线条编号  
:::image-end:::  

### <a name="hide-line-labels"></a>隐藏线条标签  

选择“**隐藏线条标签**”以隐藏线条编号。  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="隐藏线条标签" lightbox="../media/grid-hide-line-labels.msft.png":::
   隐藏线条标签  
:::image-end:::  

### <a name="show-line-names"></a>显示线条名称  

有关网格叠加层中的线条名称的详细信息，请导航至“[使用命名网格线的布局][MdnLayoutUsingNamedGridLines]”。  

选择“**显示线条名称**”以查看线条名称而不是编号。  在示例中，4 条线的名称为：`left`、`middle1`、`middle2` 和 `right`。  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="显示线条名称" lightbox="../media/grid-show-line-names.msft.png":::
   **显示线条名称**  
:::image-end:::  

### <a name="show-track-sizes"></a>显示轨道大小  

启用“**显示轨道大小**”复选框以查看网格的轨道大小。  

开发人员工具在每个线条标签中显示 `[authored size]` 和 `[computed size]`。  

| 大小 | 详细信息 |  
|:--- |:--- |  
| **创作大小** | 样式表中定义的大小（如果未定义则忽略）。 |  
| **计算大小** | 屏幕上的实际大小。 |  

在演示中，`snack-box` 列大小在 `grid-template-columns:1fr 2fr;` CSS 中定义。  因此，列线条标签显示了创作大小和计算大小。  

| 轨道大小 | 创作大小 | 计算大小 |  
|:--- |:--- |:--- |  
| **1fr** &#x2022; **96.66px** | 1fr | 96.66px |  
| **2fr** &#x2022; **193.32px** | 2fr | 193.32px |  

行线条标签仅显示计算大小，因为样式表中未定义行大小。  

| 轨道大小 | 创作大小 | 计算大小 |  
|:--- |:--- |:--- |  
| **80px** | &nbsp;| 80px |  
| **80px** | &nbsp;| 80px |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="显示轨道大小" lightbox="../media/grid-show-track-sizes.msft.png":::
   **显示轨道大小**  
:::image-end:::  

### <a name="show-area-names"></a>显示区域名称  

若要查看区域名称，请启用“**显示区域名称**”复选框。  在示例中，网格中有 3 个区域：**top**、**bottom1** 和 **bottom2**。  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="显示区域名称" lightbox="../media/grid-show-area-names.msft.png":::
   **显示区域名称**  
:::image-end:::  

### <a name="extend-grid-lines"></a>延伸网格线  

启用“**延伸网格线**”复选框，将网格线沿每个轴延伸到视区的边缘。  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="延伸网格线" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **延伸网格线**  
:::image-end:::  

## <a name="grid-overlays"></a>网格叠加层  

“**网格叠加层**”部分包含页面上存在的网格列表，每个网格都带有一个复选框以及各种选项。  

### <a name="enable-overlay-views-of-multiple-grids"></a>启用多个网格的叠加视图  

若要显示多个网格的叠加网格，请选中每个网格名称旁边的复选框。  在示例中，启用了 2 个网格叠加层，每个叠加层以不同的颜色表示。  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="启用多个网格的叠加视图" lightbox="../media/grid-grid-overlays.msft.png":::
   启用多个网格的叠加视图  
:::image-end:::  

### <a name="customize-the-grid-overlay-color"></a>自定义网格叠加层颜色  

若要打开颜色选取器并自定义网格叠加层颜色，请选择网格叠加层名称旁边的框。  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="自定义网格叠加层颜色" lightbox="../media/grid-grid-overlays-color.msft.png":::
   自定义网格叠加层颜色  
:::image-end:::  

### <a name="highlight-the-grid"></a>突出显示网格  

若要在“**元素**”工具中突出显示 HTML 元素并在网页上滚动到该元素，请选择“**在‘元素’面板中显示元素**”（![“在‘元素’面板中显示元素”图标](../media/show-element-in-element-panel-icon.msft.png)）图标。  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="突出显示网格" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   突出显示网格  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发人员工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "打开 Microsoft Edge 开发人员工具 | Microsoft Docs"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS 网格 | jec.fyi"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS 网格 | jec.fyi"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局 | MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "使用命名网格线的布局 | MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "CSS 网格基于线条的放置 | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/css/grid)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
