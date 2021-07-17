---
description: 所有关于 3D 视图及其使用方法。
title: 3D 视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: bd91939a19f02a426834a85ef92eca388f8f1eda
ms.sourcegitcommit: 5e218b24fb21fcfa9c82b99f17373fed1ba5a21c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "11203968"
---
# <a name="3d-view"></a>3D 视图  

使用 **3D 视图** 通过浏览文档对象模型和 [DOM ][MDNDocumentObjectModel] (或 [z 索引][MDNZIndex]) 上下文来调试 Web 应用。  通过它，您可以完成以下任务。  

*   [浏览翻译为 3D 视角的网页](#3d-dom)  
*   [基于 z 索引堆栈上下文进行调试](#z-index)  
*   [通过复合层从 3D 视图访问图层工具功能](#composited-layers)  
*   [清除 DOM 窗格或](#changing-your-view) z 索引窗格中的 [一些待筛选邮件](#change-the-scope-of-your-exploration)  
*   [选取配色方案以最好地调试 DOM 问题](#dom-color-type) 或 [z 索引问题](#z-index-color-type)  

如果你想要探索 3D 视图项目的早期原型并自己运行代码，请导航到["3D 视图示例"。][GithubMicrosoftedgeDevtoolssamples3dview]  

在左侧，有三个窗格可以用于调试体验。  

*   Z [索引](#z-index) 窗格。  在 Web 应用中的不同元素中导航，并注意 z-index 上下文。  Z **索引窗格** 是默认窗格。  
*   [3D DOM](#3d-dom)窗格。  通过可轻松访问的所有元素，作为一个整体探索 DOM。  若要访问该窗格，请选择 **Z 索引** 窗格旁边的 **DOM** 窗格。  
*   复合 [层窗格](#composited-layers)。  添加另一个 3D 元素以从层角度创建更全面的体验。  若要访问窗格，请选择 **"DOM"** 窗格旁边的 **"复合层"** 窗格。  
    
在右侧，画布显示来自[Z 索引](#z-index)[、3D DOM](#3d-dom)或[复合层的选择](#composited-layers)。  

## <a name="navigating-the-canvas"></a>在画布上导航  

:::image type="complex" source="../media/3d-view-canvas.msft.png" alt-text="3D 视图画布" lightbox="../media/3d-view-canvas.msft.png":::
   3D 视图画布  
:::image-end:::  

### <a name="keyboard-shortcuts"></a>键盘快捷方式  

*   旋转 DOM：若要水平旋转，请选择 `left-arrow` 和 `right-arrow` 键。  若要垂直旋转，请选择 `up-arrow` 和 `down-arrow` 键。  
*   导航 DOM：若要在相邻的元素间移动，请选择一个元素，然后选择 `up-arrow` 和 `down-arrow` 键。  

### <a name="mouse-controls"></a>鼠标控件  

*   旋转 DOM：选择并拖动画布空间。  
*   平移 DOM：打开上下文菜单 \ (右键单击\) 并按希望 DOM 移动的方向拖动。  
*   缩放：在触摸板上拖动两根手指或使用鼠标上的滚动盘。  

### <a name="on-screen-controls"></a>屏幕控件  

:::image type="complex" source="../media/3d-view-controls-small.msft.png" alt-text="屏幕控件" lightbox="../media/3d-view-controls-small.msft.png":::
   屏幕控件  
:::image-end:::  

*   将画布视图重置为原始视图：选择 **"重置相机"** 按钮，或选择 **"重置视图中的元素"，然后重新居中相机**\(侧向刷新图标\) 按钮。  
*   刷新画布 \ (例如，如果浏览器发生更改或切换到设备仿真器视图\) ：选择 **"重新拍摄快照"** 按钮或选择"**获取新快照**"按钮 \(刷新图标\)。  

## <a name="z-index"></a>Z 索引  

:::image type="complex" source="../media/3d-view-z-index-view-box.msft.png" alt-text="Z 索引视图" lightbox="../media/3d-view-z-index-view-box.msft.png":::
   Z 索引视图  
:::image-end:::  

虽然 **Z 索引** 窗格具有与 **3D DOM** 窗格的共享功能，但窗格仍具有该窗格特有的元素。  

### <a name="highlight-elements-with-stacking-context"></a>使用堆叠上下文突出显示元素  

使用 **堆叠上下文设置突出显示** 元素允许你打开 \ (和 off\) 画布上元素的 z-index 标记。  默认情况下选中复选框。  

### <a name="change-the-scope-of-your-exploration"></a>更改探索范围  

" **显示所有元素** "按钮是在更改其下方的设置后显示 DOM 的所有元素的最快方法。  

" **仅显示具有堆叠上下文** 的元素"按钮删除元素而不堆叠上下文并平展 DOM 以简化导航。  

" **隔离所选元素"** 按钮实质上是一个中的三个按钮。  **"隔离所选元素"** 按钮下方有两个复选框：**"显示所有父元素"** 复选框和 **"仅保留具有新堆叠上下文的父项"** 复选框。  

默认情况下 **，"** 显示所有家长"复选框已打开。  若要在画布上显示元素和任何父元素，请选择一个元素并选择"隔离 **所选元素"** 按钮。  

若要在画布上显示具有新堆叠上下文的元素和父元素，请打开 **"仅保留具有新堆叠上下文的父元素"** 设置并选择 **"隔离所选元素"** 按钮。  

若要在画布上显示你选择的元素，请关闭这两个设置，然后选择" **隔离所选元素"** 按钮。  

在 **3D DOM** 窗格底部，找到"隐藏与父元素的绘制顺序相同的 **元素"复选框**。  选择并取消选中复选框将基于你的选择刷新元素。  如果选中，共享绘制顺序的元素将平展到父元素。  

这些选项旨在清除一些更复杂的网页在画布上创建的混乱情况。  

### <a name="z-index-color-type"></a>Z 索引颜色类型  

是你可能在画布中用于 DOM 的不同可视化效果。  无论是为了有趣还是因为可视化效果有助于更好地可视化 DOM，DevTools 都有不同的颜色通道和" **使用背景色"** 选项。  **Z索引**窗格与**3D DOM**窗格共享**紫色到白色**和**背景色**。   考虑到添加了 z 索引标签的可视元素，你的反馈导致颜色选项的数量减少。  新的简单性改进了 z-index 调试体验。  单选按钮允许你切换选项并选取颜色类型。  颜色类型最适用于你的项目，或最喜欢的颜色类型。  

## <a name="3d-dom"></a>3D DOM  

:::image type="complex" source="../media/3d-view-dom-purple-box.msft.png" alt-text="DOM 视图" lightbox="../media/3d-view-dom-purple-box.msft.png":::
   DOM 视图  
:::image-end:::  

如果你想要获得更多常规调试视图，而不是 z 索引体验 **，3D DOM** 会提供 DOM 的整体外观。  由于删除了 z-index 上下文，因此 DOM 的堆叠更为紧密和干净。  **3D DOM**窗格具有类似的功能，但存在一些细微差别。  

### <a name="changing-your-view"></a>更改视图  

在 **3D DOM** 窗格中，" **隔离** 所选元素"按钮具有" **包括子** 元素"和" **包括父项"** 复选框。  默认情况下，这两个复选框都打开。  这意味着，如果在选择元素后选择 **"隔离所选元素"** 按钮，画布将显示所选元素、元素的父元素和元素的子元素。  关闭" **包含子元素** "设置，然后再次选择" **隔离所选元素** "按钮以显示所选元素和元素的父元素。  如果打开" **包含** 子元素"设置并关闭" **包含** 父元素"设置，然后选择"隔离 **所选** 元素"按钮，画布将显示元素和任何子元素。  如果同时关闭这两个设置并选择" **隔离所选元素** "按钮，画布将仅显示之前选择的元素。  

控件窗格上名为 **"嵌套级别的页面"的滑块，** 旁边有一个数字。  数字指示文档的图层数。  向左拖动滑块会导致最外面的图层消失，直到你将嵌套层设置为 ，这将仅显示 DOM 中最远 `1` 的后退元素。  若要删除某些待筛选邮件，请拖动滑块。  它可以帮助你仔细查看较低级别中发生的情况。  

### <a name="dom-color-type"></a>DOM 颜色类型  

**3D DOM**窗格显示以下选项。  

*   三种不同的颜色。  
    *   **热度图 - 紫色到白色**  
    *   **热度图 - 蓝色到黄色**  
    *   **热图 - 红红**  
*   **使用背景色**  
*   **使用屏幕纹理**  
    
使用 **屏幕纹理选项** 将上下文添加到你的调试体验。  它直接将网页中的内容显示在元素上。  

## <a name="composited-layers"></a>复合层

:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   **复合层**窗格
:::image-end:::  

**复合层**窗格打开**层**工具的元素，而不更改上下文。  你仍然可以访问每个图层的详细信息，并拥有慢速**滚动****画图。**

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

开发人员Microsoft Edge团队正在处理 UI，并基于你的反馈向 3D 视图添加更多功能。  发送反馈以帮助改进开发人员Microsoft Edge开发工具。  在DevTools 中选择 **"发送反馈"** 图标，或在 Windows/Linux选择`Alt` + `Shift` + `I`或 macOS 上选择`Option` + `Shift` + `I`，然后输入你的 DevTools 的任何反馈或功能请求。  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft EdgeDevTools 3D 视图 - MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
