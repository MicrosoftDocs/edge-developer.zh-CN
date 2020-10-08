---
description: 所有关于3D 视图以及如何使用它的信息。
title: 3D 视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: ba1125654c46be6ef4da99efc9ba027ba5e40672
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986078"
---
# 3D 视图  

通过在[文档对象模型 (DOM) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文中导航，使用**3d 视图**调试 web 应用程序。  通过它，你可以执行以下任务。  

*   [浏览转换为3D 透视的网页](#3d-dom)  
*   [基于 z 索引堆栈上下文进行调试](#z-index)  
*   清除 "DOM" 窗格或 " [z-索引" 窗格](#change-the-scope-of-your-exploration)[上的一些混乱情况](#changing-your-view)  
*   [选择用于最佳调试 DOM 问题](#dom-color-type)或[z 索引问题](#z-index-color-type)的配色方案  

如果想要浏览3D 视图项目的早期原型并自己运行代码，请参阅 [3D 视图示例][GithubMicrosoftedgeDevtoolssamples3dview]。   

在左侧，有两个可用于调试体验的窗格。  

1.  " [Z-索引](#z-index) " 窗格。  在 web 应用程序中使用 z 索引上下文浏览不同的元素。  " **Z-索引** " 窗格是默认窗格。  
1.  [3D DOM](#3d-dom)窗格。  使用所有元素轻松浏览整个 DOM。  若要访问该窗格，请在 " **Z-索引**" 窗格旁边的 " **DOM** " 窗格中选择。  
    
在右侧，画布将显示从 [Z 索引](#z-index) 或 [3d DOM](#3d-dom)中选择的内容。  

## 导航画布  

:::image type="complex" source="../media/canvas.png" alt-text="3D 视图的画布" lightbox="../media/canvas.png":::
   3D 视图的画布  
:::image-end:::  

### 键盘快捷方式  

*   旋转 DOM：若要水平旋转，请按 `left-arrow` 和 `right-arrow` 键。  若要垂直旋转，请按 `up-arrow` 和 `down-arrow` 键。  
*   导航 DOM：若要在相邻元素之间移动，请选择一个元素，然后按 " `up-arrow` 和" `down-arrow` 键。  

### 鼠标控件  

*   旋转 DOM：在画布空间周围选择和拖动。  
*   在 DOM 中移动：打开上下文菜单 \ (右键单击 \ ) 并按希望 DOM 移动的方向拖动。  
*   缩放：在触摸板上拖动两根手指或使用鼠标上的滚轮。  

### 屏幕上的控件  

:::image type="complex" source="../media/controls-small.png" alt-text="3D 视图的画布" lightbox="../media/controls-small.png":::
   屏幕上的控件  
:::image-end:::  

*   将画布视图重置为原始视图：选择 " **重置照相机** " 按钮，或选择 "重置照相机" 按钮，或选择 " **在视图中重置元素" 和 "重新中心相机** \" (侧向刷新图标 \ )   
*   刷新画布 \ (例如，如果浏览器发生更改或切换到设备仿真器视图 \ ) ：选择 "重 **拍快照** " 按钮，或选择 " **拍摄新快照** " 按钮 \ (刷新图标 \ ) 。  

## Z-索引  

:::image type="complex" source="../media/z-index-view-box.png" alt-text="3D 视图的画布" lightbox="../media/z-index-view-box.png":::
   Z-索引视图  
:::image-end:::  

虽然 " **Z-索引** " 窗格具有与 **3d DOM** 窗格共享的功能，但这些窗格仍具有特定于窗格的元素。  

### 利用堆栈上下文突出显示元素  

利用 "堆栈上下文" 设置的 " **突出显示元素** "，你可以为画布上的元素启用 \ (和 off \ ) 的 z 索引标记。  默认情况下，复选框处于选中状态。  

### 更改您的勘探的范围  

" **显示所有元素** " 按钮是在更改下面的设置后显示 DOM 的所有元素的最快方式。  

" **仅显示具有堆栈上下文的元素** " 按钮删除不带堆栈上下文的元素，并拼合 DOM 以便更轻松地进行导航。  

" **隔离选定元素** " 按钮实质上是三个按钮。  " **隔离选定元素** " 按钮下面有两个复选框： " **显示所有父项** " 复选框，并 **仅保留具有 "新建堆栈上下文** " 复选框的父项。  

默认情况下，" **显示所有家长** " 复选框处于选中状态。  如果在 "画布" 窗格上选择某个元素并选择 " **隔离选定元素** " 按钮，则画布仅显示该元素和任何父元素。  

如果选中 " **仅保留新堆栈上下文的父项** " 复选框，然后选择 " **隔离所选元素** " 按钮，则画布仅显示具有新堆栈上下文的元素和父元素。  

如果取消选中两个复选框，然后选择 " **隔离选定元素** " 按钮，则画布仅显示您在第一个位置中选择的元素。  

在 **3D DOM** 面板的最下方，找到 " **隐藏具有与父项相同的绘制顺序** " 复选框的元素。  选中并取消选中复选框将根据您的选择刷新元素。  如果选中，共享绘制顺序的元素将拼合到父项。  

这些选项旨在清理在你的画布中创建更复杂的网页的一些混乱程度。  

### Z-索引颜色类型  

这是你的画布中的 DOM 可以使用的不同可视化效果。  无论是将它用于趣味，还是因为可视化效果帮助你更好地可视化 DOM，DevTools 有三种不同的 colorways 和 **背景色** 设置。  单选按钮使你可以切换选项，并选择最适合你的项目的颜色类型 (或喜欢的最大 ) 。  

## 3D DOM  

:::image type="complex" source="../media/dom-purple-box.png" alt-text="3D 视图的画布" lightbox="../media/dom-purple-box.png":::
   DOM 视图  
:::image-end:::  

如果你想要使用更多常规调试视图，而不是 z 索引体验，则 **3D DOM** 将为 DOM 提供整体外观。  由于删除了 z 索引上下文，因此 DOM 更紧密地堆叠。  **3D DOM**窗格具有类似的功能，但有一些细微差别。  

### 更改视图  

在 **3D DOM** 窗格上，" **隔离选定元素** " 按钮包含 " **子** 元素" 和 " **包含父项** " 复选框。  默认情况下，两个复选框均被选中，这意味着选择画布上的元素后选择 " **隔离选定的元素** " 按钮应显示所选元素、元素的父元素和元素的子元素。  取消选中 " **包含子** 元素" 复选框，然后再次选择 " **隔离选定元素** " 按钮将显示所选元素和元素的父元素。  如果选择 " **包含儿童** " 复选框并取消选择 " **包括家长** " 复选框，然后选择 " **隔离所选元素** " 按钮，则画布将显示该元素和任何子元素。  如果取消选中两个复选框，然后选择 " **隔离选定元素** " 按钮，则画布仅显示您以前选择的元素。  

"控件" 窗格上标题为 " **嵌套级别** " 的 "页面" 旁边带有数字的滑块。  该数字表示文档的层数。  将滑块向左拖动会导致最外层的图层 peel 离开，直到将嵌套级别设置为1，这将仅显示 DOM 中的最远距离元素。  如果你尝试进一步了解较低级别中发生的情况，则拖动滑块可使你删除一些混乱效果。  

### DOM 颜色类型  

除了 **热度地图-紫色到白色**、 **热度地图**、 **热度地图**和 **使用 "背景色** " 单选按钮，还有 **使用屏幕纹理**。  屏幕纹理通过将网页中的内容直接显示在元素上来将上下文添加到调试体验。  在 **3D DOM** 窗格上，"  **颜色类型** " 设置仍是正在进行的工作，因为某些网站在3d 视图中呈现屏幕纹理较难。  

## 与 Microsoft Edge 开发人员工具团队联系

Microsoft Edge Devtools 团队正在处理 UI，并根据用户（如用户）向3D 视图添加更多功能。  请发送反馈，帮助改进 Microsoft Edge DevTools。  只需选择 DevTools 中的反馈图标，或按 `Alt` + `Shift` + `I` \ (Windows \ ) 或按下 `Option` + `Shift` + `I` \ (macOS \ ) 并输入 DevTools 的任何反馈或功能请求。  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D 视图-MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
