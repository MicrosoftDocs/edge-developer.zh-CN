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
# 检查 CSS 网格  

本文将向你介绍如何使用可自定义的网格重叠在网站上识别 CSS 网格和调试网格布局问题。  

本文中的图表中使用的示例来自以下网页。  

*   [水果包装盒][JecFyiDemoCssGridFruit]  
*   [零食框][JecFyiDemoCssGridSnack]  

## 开始之前  

CSS 网格是 web 的一个强大的布局模式。  有关 CSS 网格和许多功能入门的绝佳位置是有关 MDN 的 [Css 网格布局指南][MdnCssGridLayout] 。  

## 探索 CSS 网格  

当页面上已有或应用了 HTML 元素时 `display: grid` `display: inline-grid` ， `grid` " [元素][DevtoolsGuideChromiumOpen] " 面板中的标记旁边会显示一个标记。  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="探索网格" lightbox="../media/grid-discover-grid.msft.png":::
   探索网格  
:::image-end:::  

选择锁屏提醒以切换页面上的网格覆盖的显示。  覆盖层将出现在元素上方，布局类似于网格以显示网格线的位置和轨道：  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="探索网格" lightbox="../media/grid-highlight-grid.msft.png":::
   切换网格标记  
:::image-end:::  

打开 " **布局** " 窗格。  当页面上包含网格时， **布局** 窗格包括一个 **网格** 部分，其中包含用于查看网格的许多选项。  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="探索网格" lightbox="../media/grid-layout-pane.msft.png":::
   **布局** 窗格  
:::image-end:::  

"**布局**" 窗格中的 "**网格**" 部分包含以下两个子部分。  

*   覆盖显示设置  
*   网格覆盖  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## 覆盖显示设置  

**覆盖显示设置**由以下2个部分组成。  

*   从下拉菜单中选择以下选项之一。  
    
    | 行选项 | 详细信息 |  
    |:--- |:--- |  
    | **隐藏行标签** | 隐藏每个网格覆盖的行的标签。 |  
    | **显示行号** | 显示每个网格覆盖的行数 \ (默认选中 \ ) 。 |  
    | **显示行名称** | 在提供名称时显示每个网格覆盖的行的名称。 |  
    
*  选中以下选项旁的复选框。  
    
    | 选项 | 详细信息 |  
    |:--- |:--- |  
    | **显示曲目大小**  | 显示 \ (或隐藏 \ ) 轨道的大小。 |  
    | **显示区域名称** | 当提供名称时，显示 "\ (" 或 "隐藏 \ ) " 区域的名称。 |  
    | **扩展网格线** | 显示 \ (或隐藏 \ ) 沿每个轴的网格尺寸的扩展。  默认情况下，网格线仅显示 `display: grid` `display: inline-grid` 在其上设置了 "" 或 "CSS" 的元素内。 |  
    
以下部分提供了每个 **覆盖显示设置**的详细信息。  

### 显示行号  

默认情况下，在网格覆盖区域上显示正值和负数。  

有关网格覆盖中的负数的详细信息，请导航到 [具有 CSS 网格的基于行的位置][MdnLineBasedPlacementCssGrid]。  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="探索网格" lightbox="../media/grid-show-line-numbers.msft.png":::
   显示行号  
:::image-end:::  

### 隐藏行标签  

选择 " **隐藏行标签** " 以隐藏行号。  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="探索网格" lightbox="../media/grid-hide-line-labels.msft.png":::
   隐藏行标签  
:::image-end:::  

### 显示行名称  

<!--todo: @rachel verify the link and text for line name -->  
有关网格覆盖中的行名称的详细信息，请导航到 [使用命名网格线的布局][MdnLayoutUsingNamedGridLines]。  

选择 " **显示行名称** " 以查看行名称，而不是数字。  在该示例中，4行具有名称： `left` 、 `middle1` 、 `middle2` 和 `right` 。  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="探索网格" lightbox="../media/grid-show-line-names.msft.png":::
   **显示行名称**  
:::image-end:::  

### 显示曲目大小  

启用 " **显示跟踪大小** " 复选框以查看网格的轨道大小。  

DevTools 显示 `[authored size]` `[computed size]` 在每个行标签中。  

| 大小 | 详细信息 |  
|:--- |:--- |  
| **已创作大小** | 如果未定义 \ ) ，则在样式表中定义的大小为 \ (省略。 |  
| **计算大小** | 屏幕上的实际大小。 |  

在演示中， `snack-box` 列的大小在 CSS 中定义 `grid-template-columns:1fr 2fr;` 。  因此，列的行标签既显示了创作的，也显示了计算的大小。  

| 跟踪大小 | 已创作大小 | 计算大小 |  
|:--- |:--- |:--- |  
| **1fr** &#x2022; **96.66 px** | 1fr | 96.66 px |  
| **2fr** &#x2022; **193.32 px** | 2fr | 193.32 px |  

由于没有在样式表中定义的行大小，行标签仅显示计算的大小。  

| 跟踪大小 | 已创作大小 | 计算大小 |  
|:--- |:--- |:--- |  
| **80px** | &nbsp;| 80px |  
| **80px** | &nbsp;| 80px |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="探索网格" lightbox="../media/grid-show-track-sizes.msft.png":::
   **显示曲目大小**  
:::image-end:::  

### 显示区域名称  

若要查看区域名称，请启用 " **显示区域名称** " 复选框。  在此示例中，网格中有3个区域： " **top**"、" **bottom1** " 和 " **bottom2**"。  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="探索网格" lightbox="../media/grid-show-area-names.msft.png":::
   **显示区域名称**  
:::image-end:::  

### 扩展网格线  

启用 " **扩展网格线** " 复选框，将网格线沿每个轴延伸到视区的边缘。  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="探索网格" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **扩展网格线**  
:::image-end:::  

## 网格覆盖  

" **网格覆盖** " 部分包含页面上显示的网格的列表，每个网格都有一个复选框和各种选项。  

### 启用多个网格的重叠视图  

<!--todo: @zoher verify and provide updates -->  

若要显示多个网格的覆盖网格，请选择网格每个名称旁边的复选框。  在此示例中，已启用2个网格覆盖，每个网格覆盖都以不同颜色表示。  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="探索网格" lightbox="../media/grid-grid-overlays.msft.png":::
   启用多个网格的重叠视图  
:::image-end:::  

### 自定义网格覆盖色  

若要打开颜色选取器并自定义网格覆盖颜色，请选择网格覆盖名称旁边的框。  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="探索网格" lightbox="../media/grid-grid-overlays-color.msft.png":::
   自定义网格覆盖色  
:::image-end:::  

### 突出显示网格  

若要突出显示 " **元素** " 面板中的 HTML 元素并在网页上滚动到该元素，请选择 " **元素" 面板中的 "显示元素** "， (![ "元素" 面板中的 "显示元素" 图标 ][ImageShowElementInElementsPanelIcon] \ ) 图标。  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="探索网格" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   突出显示网格  
:::image-end:::  

## 与 Microsoft Edge 开发人员工具团队联系  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/css/grid) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
