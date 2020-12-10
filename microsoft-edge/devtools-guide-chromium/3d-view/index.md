---
description: 所有关于3D 视图以及如何使用它的信息。
title: 3D 视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: bd91939a19f02a426834a85ef92eca388f8f1eda
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203968"
---
# 3D 视图  

通过在[文档对象模型 (DOM) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文中导航，使用**3d 视图**调试 web 应用。  通过它，你可以完成以下任务。  

*   [浏览转换为3D 透视的网页](#3d-dom)  
*   [基于 z 索引堆栈上下文进行调试](#z-index)  
*   [使用复合图层从3D 视图访问 "图层" 工具功能](#composited-layers)  
*   清除 "DOM" 窗格或 " [z-索引" 窗格](#change-the-scope-of-your-exploration)[上的一些混乱情况](#changing-your-view)  
*   [选择用于最佳调试 DOM 问题](#dom-color-type)或[z 索引问题](#z-index-color-type)的配色方案  

如果想要浏览3D 视图项目的早期原型并自行运行代码，请导航到 " [3D 视图" 示例][GithubMicrosoftedgeDevtoolssamples3dview]。  

在左侧，有三个可用于调试体验的窗格。  

*   " [Z-索引](#z-index) " 窗格。  在 web 应用中使用 z 索引上下文浏览不同的元素。  " **Z-索引** " 窗格是默认窗格。  
*   [3D DOM](#3d-dom)窗格。  将 DOM 视为一个整体，可轻松访问所有元素。  若要访问该窗格，请选择 " **Z-索引**" 窗格旁边的 " **DOM** " 窗格。  
*   " [复合图层](#composited-layers) " 窗格。  添加另一个3D 元素，以从图层角度创建更全面的体验。  若要访问该窗格，请选择 " **DOM** " 窗格旁边的 "**复合图层**" 窗格。  
    
在右侧，画布将显示从 [Z 索引](#z-index)、 [3D DOM](#3d-dom)或 [合成图层](#composited-layers)中选择的内容。  

## 导航画布  

:::image type="complex" source="../media/3d-view-canvas.msft.png" alt-text="3D 视图的画布" lightbox="../media/3d-view-canvas.msft.png":::
   3D 视图的画布  
:::image-end:::  

### 键盘快捷方式  

*   旋转 DOM：若要水平旋转，请选择 " `left-arrow` 和" `right-arrow` 键。  若要垂直旋转，请选择 " `up-arrow` 与" `down-arrow` 键。  
*   导航 DOM：若要在相邻元素之间移动，请选择一个元素，然后选择 " `up-arrow` 和" `down-arrow` 键。  

### 鼠标控件  

*   旋转 DOM：在画布空间周围选择和拖动。  
*   在 DOM 中移动：打开上下文菜单 \ (右键单击 \ ) 并按希望 DOM 移动的方向拖动。  
*   缩放：在触摸板上拖动两根手指或使用鼠标上的滚轮。  

### 屏幕上的控件  

:::image type="complex" source="../media/3d-view-controls-small.msft.png" alt-text="屏幕上的控件" lightbox="../media/3d-view-controls-small.msft.png":::
   屏幕上的控件  
:::image-end:::  

*   将画布视图重置为原始视图：选择 " **重置照相机** " 按钮，或选择 "重置照相机" 按钮，或选择 " **在视图中重置元素" 和 "重新中心相机** \" (侧向刷新图标 \ )   
*   刷新画布 \ (例如，如果浏览器发生更改或切换到设备仿真器视图 \ ) ：选择 "重 **拍快照** " 按钮，或选择 " **拍摄新快照** " 按钮 \ (刷新图标 \ ) 。  

## Z-索引  

:::image type="complex" source="../media/3d-view-z-index-view-box.msft.png" alt-text="Z-索引视图" lightbox="../media/3d-view-z-index-view-box.msft.png":::
   Z-索引视图  
:::image-end:::  

虽然 " **Z-索引** " 窗格具有与 **3d DOM** 窗格共享的功能，但这些窗格仍具有特定于窗格的元素。  

### 利用堆栈上下文突出显示元素  

利用 "堆栈上下文" 设置的 " **突出显示元素** "，你可以为画布上的元素启用 \ (和 off \ ) 的 z 索引标记。  默认情况下选中此复选框。  

### 更改您的勘探的范围  

" **显示所有元素** " 按钮是在更改下方的设置后显示 DOM 的所有元素的最快方式。  

" **仅显示具有堆栈上下文的元素** " 按钮删除不带堆栈上下文的元素，并拼合 DOM 以便更轻松地进行导航。  

" **隔离选定元素** " 按钮实质上是三个按钮。  " **隔离选定元素** " 按钮下面有两个复选框： " **显示所有父项** " 复选框，并 **仅保留具有 "新建堆栈上下文** " 复选框的父项。  

默认情况下，" **显示所有家长** " 复选框处于打开状态。  若要在画布上显示元素和任何父元素，请选择一个元素，然后选择 " **隔离选定元素** " 按钮。  

若要显示在画布上具有新的堆栈上下文的元素和父元素，请打开 " **仅保留父项并使用新堆栈上下文** " 设置，然后选择 " **隔离所选元素** " 按钮。  

若要显示你在画布上选择的元素，请关闭 "设置"，然后选择 " **隔离所选元素** " 按钮。  

在 **3D DOM** 窗格底部，找到 " **隐藏具有与父项相同的绘制顺序的元素** " 复选框。  选择并取消选中复选框将根据您的选择刷新元素。  如果选中，共享绘制顺序的元素将拼合到父项。  

这些选项旨在清理在你的画布中创建更复杂的网页的一些混乱程度。  

### Z-索引颜色类型  

这是你的画布中的 DOM 可以使用的不同可视化效果。  无论是将它用于趣味，还是因为可视化效果帮助你更好地可视化 DOM，DevTools 具有不同的 colorways 和 " **使用背景色** " 选项。  **Z-索引**窗格与**3d DOM**窗格共享**紫色到白色**和**背景色**。  假设添加了 z 索引标签的视觉元素，这会导致减少颜色选项的数量。  新的简单性改进了 z 索引调试体验。  单选按钮允许您切换选项，并选择颜色类型。  颜色类型最适合你的项目或你最喜欢的一种。  

## 3D DOM  

:::image type="complex" source="../media/3d-view-dom-purple-box.msft.png" alt-text="DOM 视图" lightbox="../media/3d-view-dom-purple-box.msft.png":::
   DOM 视图  
:::image-end:::  

如果你想要使用更多常规调试视图，而不是 z 索引体验，则 **3D DOM** 将为 DOM 提供整体外观。  由于删除了 z 索引上下文，因此 DOM 更紧密地堆叠。  **3D DOM**窗格具有类似的功能，但有一些细微差别。  

### 更改视图  

在 **3D DOM** 窗格上，" **隔离选定元素** " 按钮包含 " **子** 元素" 和 " **包含父项** " 复选框。  默认情况下，这两个复选框均处于打开状态。  这意味着，如果选择元素后选择 " **隔离选定的元素** " 按钮，则画布将显示所选元素、元素的父元素和元素的子元素。  关闭 " **包括子** 对象" 设置，然后再次选择 " **隔离选定的元素** " 按钮以显示所选元素和元素的父元素。  如果打开 " **包括儿童** " 设置，然后关闭 " **包括父项** " 设置，然后选择 "使 **所选元素隔离** " 按钮，则画布将显示该元素和任何子元素。  如果关闭这两个设置，然后选择 " **隔离选定元素** " 按钮，则画布仅显示您以前选择的元素。  

控件窗格中名为 " **嵌套级别** " 的滑块，旁边有一个数字。  该数字表示文档的层数。  将滑块向左拖动会导致最外层的图层 peel 离开，直到你离开了设置为的嵌套级别 `1` ，这将仅显示 DOM 中的后置元素。  若要删除某些混乱，请拖动滑块。  它可帮助您更深入地了解较低级别中发生的情况。  

### DOM 颜色类型  

**3D DOM**窗格显示以下选项。  

*   三个不同的 colorways。  
    *   **热度地图-紫色到白**  
    *   **热度地图-蓝到黄**  
    *   **热度地图-彩虹**  
*   **使用背景色**  
*   **使用屏幕纹理**  
    
" **使用屏幕纹理** " 选项可将上下文添加到调试体验中。  它直接将网页中的内容显示在元素上。  

## 合成图层

:::image type="complex" source="../media/experiments-layers.msft.png" alt-text=""复合图层" 窗格" lightbox="../media/experiments-layers.msft.png":::
   "**复合图层**" 窗格
:::image-end:::  

" **复合图层** " 窗格在不更改上下文的情况下打开 " **图层** " 工具的元素。  您仍然可以访问每个图层的详细信息，并具有 **缓慢的滚动 rects** 和 **油漆**。

## 与 Microsoft Edge 开发人员工具团队联系  

Microsoft Edge Devtools 团队正在处理 UI，并根据你的反馈向3D 视图添加更多功能。  发送反馈以帮助改进 Microsoft Edge DevTools。  在 DevTools 中选择 "**发送反馈**" 图标，或选择 " `Alt` + `Shift` + `I` 在 Windows/Linux 上" 或 `Option` + `Shift` + `I` "在 macOS 上选择"，然后输入 DevTools 的任何反馈或功能请求。  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D 视图-MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
