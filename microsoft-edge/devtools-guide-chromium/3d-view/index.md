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
# <span data-ttu-id="9f455-104">3D 视图</span><span class="sxs-lookup"><span data-stu-id="9f455-104">3D View</span></span>  

<span data-ttu-id="9f455-105">通过在[文档对象模型 (DOM) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文中导航，使用**3d 视图**调试 web 应用。</span><span class="sxs-lookup"><span data-stu-id="9f455-105">Use the **3D View** to debug your web app by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  <span data-ttu-id="9f455-106">通过它，你可以完成以下任务。</span><span class="sxs-lookup"><span data-stu-id="9f455-106">With it, you may complete the following tasks.</span></span>  

*   [<span data-ttu-id="9f455-107">浏览转换为3D 透视的网页</span><span class="sxs-lookup"><span data-stu-id="9f455-107">Explore the web page translated into a 3D perspective</span></span>](#3d-dom)  
*   [<span data-ttu-id="9f455-108">基于 z 索引堆栈上下文进行调试</span><span class="sxs-lookup"><span data-stu-id="9f455-108">Debug based on z-index stacking context</span></span>](#z-index)  
*   [<span data-ttu-id="9f455-109">使用复合图层从3D 视图访问 "图层" 工具功能</span><span class="sxs-lookup"><span data-stu-id="9f455-109">Access the Layers tool functionality from 3D View with composited layers</span></span>](#composited-layers)  
*   <span data-ttu-id="9f455-110">清除 "DOM" 窗格或 " [z-索引" 窗格](#change-the-scope-of-your-exploration)[上的一些混乱情况](#changing-your-view)</span><span class="sxs-lookup"><span data-stu-id="9f455-110">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>  
*   <span data-ttu-id="9f455-111">[选择用于最佳调试 DOM 问题](#dom-color-type)或[z 索引问题](#z-index-color-type)的配色方案</span><span class="sxs-lookup"><span data-stu-id="9f455-111">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>  

<span data-ttu-id="9f455-112">如果想要浏览3D 视图项目的早期原型并自行运行代码，请导航到 " [3D 视图" 示例][GithubMicrosoftedgeDevtoolssamples3dview]。</span><span class="sxs-lookup"><span data-stu-id="9f455-112">If you want to explore an early prototype of 3D View project and run the code yourself, navigate to [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span></span>  

<span data-ttu-id="9f455-113">在左侧，有三个可用于调试体验的窗格。</span><span class="sxs-lookup"><span data-stu-id="9f455-113">On the left side, there are three panes that you may use for your debugging experience.</span></span>  

*   <span data-ttu-id="9f455-114">" [Z-索引](#z-index) " 窗格。</span><span class="sxs-lookup"><span data-stu-id="9f455-114">The [Z-index](#z-index) pane.</span></span>  <span data-ttu-id="9f455-115">在 web 应用中使用 z 索引上下文浏览不同的元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-115">Navigate through the different elements in the web app with the z-index context in mind.</span></span>  <span data-ttu-id="9f455-116">" **Z-索引** " 窗格是默认窗格。</span><span class="sxs-lookup"><span data-stu-id="9f455-116">The **Z-index** pane is the default pane.</span></span>  
*   <span data-ttu-id="9f455-117">[3D DOM](#3d-dom)窗格。</span><span class="sxs-lookup"><span data-stu-id="9f455-117">The [3D DOM](#3d-dom) pane.</span></span>  <span data-ttu-id="9f455-118">将 DOM 视为一个整体，可轻松访问所有元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-118">Explore the DOM as a whole with all the elements easily accessible.</span></span>  <span data-ttu-id="9f455-119">若要访问该窗格，请选择 " **Z-索引**" 窗格旁边的 " **DOM** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="9f455-119">To access the pane, choose the **DOM** pane next to the **Z-index** pane.</span></span>  
*   <span data-ttu-id="9f455-120">" [复合图层](#composited-layers) " 窗格。</span><span class="sxs-lookup"><span data-stu-id="9f455-120">The [Composited Layers](#composited-layers) pane.</span></span>  <span data-ttu-id="9f455-121">添加另一个3D 元素，以从图层角度创建更全面的体验。</span><span class="sxs-lookup"><span data-stu-id="9f455-121">Add another 3D element to create a more comprehensive experience from a layers perspective.</span></span>  <span data-ttu-id="9f455-122">若要访问该窗格，请选择 " **DOM** " 窗格旁边的 "**复合图层**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="9f455-122">To access the pane, choose the **Composited Layers** pane next to the **DOM** pane.</span></span>  
    
<span data-ttu-id="9f455-123">在右侧，画布将显示从 [Z 索引](#z-index)、 [3D DOM](#3d-dom)或 [合成图层](#composited-layers)中选择的内容。</span><span class="sxs-lookup"><span data-stu-id="9f455-123">On the right side, the canvas displays your selections from the [Z-index](#z-index), [3D DOM](#3d-dom), or [Composited Layers](#composited-layers).</span></span>  

## <span data-ttu-id="9f455-124">导航画布</span><span class="sxs-lookup"><span data-stu-id="9f455-124">Navigating the canvas</span></span>  

:::image type="complex" source="../media/3d-view-canvas.msft.png" alt-text="3D 视图的画布" lightbox="../media/3d-view-canvas.msft.png":::
   <span data-ttu-id="9f455-126">3D 视图的画布</span><span class="sxs-lookup"><span data-stu-id="9f455-126">Canvas of 3D View</span></span>  
:::image-end:::  

### <span data-ttu-id="9f455-127">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="9f455-127">Keyboard shortcuts</span></span>  

*   <span data-ttu-id="9f455-128">旋转 DOM：若要水平旋转，请选择 " `left-arrow` 和" `right-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="9f455-128">Rotate the DOM:  To rotate horizontally, select the `left-arrow` and `right-arrow` keys.</span></span>  <span data-ttu-id="9f455-129">若要垂直旋转，请选择 " `up-arrow` 与" `down-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="9f455-129">To rotate vertically, select the `up-arrow` and `down-arrow` keys.</span></span>  
*   <span data-ttu-id="9f455-130">导航 DOM：若要在相邻元素之间移动，请选择一个元素，然后选择 " `up-arrow` 和" `down-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="9f455-130">Navigate the DOM:  To move through the adjacent elements, choose an element and select the `up-arrow` and `down-arrow` keys.</span></span>  

### <span data-ttu-id="9f455-131">鼠标控件</span><span class="sxs-lookup"><span data-stu-id="9f455-131">Mouse controls</span></span>  

*   <span data-ttu-id="9f455-132">旋转 DOM：在画布空间周围选择和拖动。</span><span class="sxs-lookup"><span data-stu-id="9f455-132">Rotate the DOM:  Choose and drag around the canvas space.</span></span>  
*   <span data-ttu-id="9f455-133">在 DOM 中移动：打开上下文菜单 \ (右键单击 \ ) 并按希望 DOM 移动的方向拖动。</span><span class="sxs-lookup"><span data-stu-id="9f455-133">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span></span>  
*   <span data-ttu-id="9f455-134">缩放：在触摸板上拖动两根手指或使用鼠标上的滚轮。</span><span class="sxs-lookup"><span data-stu-id="9f455-134">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>  

### <span data-ttu-id="9f455-135">屏幕上的控件</span><span class="sxs-lookup"><span data-stu-id="9f455-135">On-screen controls</span></span>  

:::image type="complex" source="../media/3d-view-controls-small.msft.png" alt-text="屏幕上的控件" lightbox="../media/3d-view-controls-small.msft.png":::
   <span data-ttu-id="9f455-137">屏幕上的控件</span><span class="sxs-lookup"><span data-stu-id="9f455-137">On-screen controls</span></span>  
:::image-end:::  

*   <span data-ttu-id="9f455-138">将画布视图重置为原始视图：选择 " **重置照相机** " 按钮，或选择 "重置照相机" 按钮，或选择 " **在视图中重置元素" 和 "重新中心相机** \" (侧向刷新图标 \ ) </span><span class="sxs-lookup"><span data-stu-id="9f455-138">Reset the canvas view to the original view:  Choose the **Reset camera** button, or choose the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span></span>  
*   <span data-ttu-id="9f455-139">刷新画布 \ (例如，如果浏览器发生更改或切换到设备仿真器视图 \ ) ：选择 "重 **拍快照** " 按钮，或选择 " **拍摄新快照** " 按钮 \ (刷新图标 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="9f455-139">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Choose the **Retake snapshot** button or choose the **Take new snapshot** button \(refresh icon\).</span></span>  

## <span data-ttu-id="9f455-140">Z-索引</span><span class="sxs-lookup"><span data-stu-id="9f455-140">Z-index</span></span>  

:::image type="complex" source="../media/3d-view-z-index-view-box.msft.png" alt-text="Z-索引视图" lightbox="../media/3d-view-z-index-view-box.msft.png":::
   <span data-ttu-id="9f455-142">Z-索引视图</span><span class="sxs-lookup"><span data-stu-id="9f455-142">Z-index view</span></span>  
:::image-end:::  

<span data-ttu-id="9f455-143">虽然 " **Z-索引** " 窗格具有与 **3d DOM** 窗格共享的功能，但这些窗格仍具有特定于窗格的元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-143">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span></span>  

### <span data-ttu-id="9f455-144">利用堆栈上下文突出显示元素</span><span class="sxs-lookup"><span data-stu-id="9f455-144">Highlight elements with stacking context</span></span>  

<span data-ttu-id="9f455-145">利用 "堆栈上下文" 设置的 " **突出显示元素** "，你可以为画布上的元素启用 \ (和 off \ ) 的 z 索引标记。</span><span class="sxs-lookup"><span data-stu-id="9f455-145">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span></span>  <span data-ttu-id="9f455-146">默认情况下选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="9f455-146">The checkbox is chosen by default.</span></span>  

### <span data-ttu-id="9f455-147">更改您的勘探的范围</span><span class="sxs-lookup"><span data-stu-id="9f455-147">Change the scope of your exploration</span></span>  

<span data-ttu-id="9f455-148">" **显示所有元素** " 按钮是在更改下方的设置后显示 DOM 的所有元素的最快方式。</span><span class="sxs-lookup"><span data-stu-id="9f455-148">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below it.</span></span>  

<span data-ttu-id="9f455-149">" **仅显示具有堆栈上下文的元素** " 按钮删除不带堆栈上下文的元素，并拼合 DOM 以便更轻松地进行导航。</span><span class="sxs-lookup"><span data-stu-id="9f455-149">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span></span>  

<span data-ttu-id="9f455-150">" **隔离选定元素** " 按钮实质上是三个按钮。</span><span class="sxs-lookup"><span data-stu-id="9f455-150">The **Isolate selected element** button is essentially three buttons in one.</span></span>  <span data-ttu-id="9f455-151">" **隔离选定元素** " 按钮下面有两个复选框： " **显示所有父项** " 复选框，并 **仅保留具有 "新建堆栈上下文** " 复选框的父项。</span><span class="sxs-lookup"><span data-stu-id="9f455-151">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span></span>  

<span data-ttu-id="9f455-152">默认情况下，" **显示所有家长** " 复选框处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="9f455-152">The **Show all parents** checkbox is turned on by default.</span></span>  <span data-ttu-id="9f455-153">若要在画布上显示元素和任何父元素，请选择一个元素，然后选择 " **隔离选定元素** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="9f455-153">To display the element and any parents on the canvas, choose an element and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="9f455-154">若要显示在画布上具有新的堆栈上下文的元素和父元素，请打开 " **仅保留父项并使用新堆栈上下文** " 设置，然后选择 " **隔离所选元素** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="9f455-154">To display the element and the parents that have a new stacking context on the canvas, turn on the **Keep only parents with new stacking context** setting and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="9f455-155">若要显示你在画布上选择的元素，请关闭 "设置"，然后选择 " **隔离所选元素** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="9f455-155">To display the element you chose on the canvas, turn off both the settings and choose **Isolate selected element** button.</span></span>  

<span data-ttu-id="9f455-156">在 **3D DOM** 窗格底部，找到 " **隐藏具有与父项相同的绘制顺序的元素** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="9f455-156">At the bottom of the **3D DOM** pane, locate the **Hide elements with the same paint order as their parent** checkbox.</span></span>  <span data-ttu-id="9f455-157">选择并取消选中复选框将根据您的选择刷新元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-157">Choosing and deselecting the checkbox refreshes the elements based on your choice.</span></span>  <span data-ttu-id="9f455-158">如果选中，共享绘制顺序的元素将拼合到父项。</span><span class="sxs-lookup"><span data-stu-id="9f455-158">If chosen, elements that share paint order are flattened to the parent.</span></span>  

<span data-ttu-id="9f455-159">这些选项旨在清理在你的画布中创建更复杂的网页的一些混乱程度。</span><span class="sxs-lookup"><span data-stu-id="9f455-159">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>  

### <span data-ttu-id="9f455-160">Z-索引颜色类型</span><span class="sxs-lookup"><span data-stu-id="9f455-160">Z-index color type</span></span>  

<span data-ttu-id="9f455-161">这是你的画布中的 DOM 可以使用的不同可视化效果。</span><span class="sxs-lookup"><span data-stu-id="9f455-161">The are the different visualizations you may use for the DOM in your canvas.</span></span>  <span data-ttu-id="9f455-162">无论是将它用于趣味，还是因为可视化效果帮助你更好地可视化 DOM，DevTools 具有不同的 colorways 和 " **使用背景色** " 选项。</span><span class="sxs-lookup"><span data-stu-id="9f455-162">Whether you use it for fun or because the visualizations help you visualize the DOM better, the DevTools have different colorways and a **Use background color** option.</span></span>  <span data-ttu-id="9f455-163">**Z-索引**窗格与**3d DOM**窗格共享**紫色到白色**和**背景色**。</span><span class="sxs-lookup"><span data-stu-id="9f455-163">The **Z-index** pane shares the **Purple to White** and **Background Color** with the **3D DOM** pane.</span></span>  <span data-ttu-id="9f455-164">假设添加了 z 索引标签的视觉元素，这会导致减少颜色选项的数量。</span><span class="sxs-lookup"><span data-stu-id="9f455-164">Given the added visual element of the z-index labels, your feedback that led to a reduction in the number of color options.</span></span>  <span data-ttu-id="9f455-165">新的简单性改进了 z 索引调试体验。</span><span class="sxs-lookup"><span data-stu-id="9f455-165">The new simplicity improves the z-index debugging experience.</span></span>  <span data-ttu-id="9f455-166">单选按钮允许您切换选项，并选择颜色类型。</span><span class="sxs-lookup"><span data-stu-id="9f455-166">The radio buttons allow you to toggle through the options and pick the color type.</span></span>  <span data-ttu-id="9f455-167">颜色类型最适合你的项目或你最喜欢的一种。</span><span class="sxs-lookup"><span data-stu-id="9f455-167">The color type is either most appropriate for your project or one that you like the most.</span></span>  

## <span data-ttu-id="9f455-168">3D DOM</span><span class="sxs-lookup"><span data-stu-id="9f455-168">3D DOM</span></span>  

:::image type="complex" source="../media/3d-view-dom-purple-box.msft.png" alt-text="DOM 视图" lightbox="../media/3d-view-dom-purple-box.msft.png":::
   <span data-ttu-id="9f455-170">DOM 视图</span><span class="sxs-lookup"><span data-stu-id="9f455-170">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="9f455-171">如果你想要使用更多常规调试视图，而不是 z 索引体验，则 **3D DOM** 将为 DOM 提供整体外观。</span><span class="sxs-lookup"><span data-stu-id="9f455-171">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span></span>  <span data-ttu-id="9f455-172">由于删除了 z 索引上下文，因此 DOM 更紧密地堆叠。</span><span class="sxs-lookup"><span data-stu-id="9f455-172">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span>  <span data-ttu-id="9f455-173">**3D DOM**窗格具有类似的功能，但有一些细微差别。</span><span class="sxs-lookup"><span data-stu-id="9f455-173">The **3D DOM** pane has similar functionality, but there are a few nuances.</span></span>  

### <span data-ttu-id="9f455-174">更改视图</span><span class="sxs-lookup"><span data-stu-id="9f455-174">Changing your view</span></span>  

<span data-ttu-id="9f455-175">在 **3D DOM** 窗格上，" **隔离选定元素** " 按钮包含 " **子** 元素" 和 " **包含父项** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="9f455-175">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span></span>  <span data-ttu-id="9f455-176">默认情况下，这两个复选框均处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="9f455-176">Both checkboxes are turned on by default.</span></span>  <span data-ttu-id="9f455-177">这意味着，如果选择元素后选择 " **隔离选定的元素** " 按钮，则画布将显示所选元素、元素的父元素和元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-177">That means if you choose the **Isolate selected element** button after you choose an element, the canvas displays the chosen element, the parents of the element, and the children of the element.</span></span>  <span data-ttu-id="9f455-178">关闭 " **包括子** 对象" 设置，然后再次选择 " **隔离选定的元素** " 按钮以显示所选元素和元素的父元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-178">Turn off the **Include children** setting and choose the **Isolate selected element** button again to display the chosen element and the parents of the element.</span></span>  <span data-ttu-id="9f455-179">如果打开 " **包括儿童** " 设置，然后关闭 " **包括父项** " 设置，然后选择 "使 **所选元素隔离** " 按钮，则画布将显示该元素和任何子元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-179">If you turn on the **Include children** setting and turn off the **Include parents** setting and then choose the **Isolate selected element** button, the canvas displays the element and any children.</span></span>  <span data-ttu-id="9f455-180">如果关闭这两个设置，然后选择 " **隔离选定元素** " 按钮，则画布仅显示您以前选择的元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-180">If you turn off both settings and choose the **Isolate selected element** button, the canvas only displays the element you previously chose.</span></span>  

<span data-ttu-id="9f455-181">控件窗格中名为 " **嵌套级别** " 的滑块，旁边有一个数字。</span><span class="sxs-lookup"><span data-stu-id="9f455-181">A slider on the control pane named **Nesting level for page** with a number next to it.</span></span>  <span data-ttu-id="9f455-182">该数字表示文档的层数。</span><span class="sxs-lookup"><span data-stu-id="9f455-182">The number indicates the number of layers for the document.</span></span>  <span data-ttu-id="9f455-183">将滑块向左拖动会导致最外层的图层 peel 离开，直到你离开了设置为的嵌套级别 `1` ，这将仅显示 DOM 中的后置元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-183">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to `1`, which displays only the furthest back element in the DOM.</span></span>  <span data-ttu-id="9f455-184">若要删除某些混乱，请拖动滑块。</span><span class="sxs-lookup"><span data-stu-id="9f455-184">To remove some of the clutter, drag the slider.</span></span>  <span data-ttu-id="9f455-185">它可帮助您更深入地了解较低级别中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="9f455-185">It helps you get a closer look at what is happening in the lower levels.</span></span>  

### <span data-ttu-id="9f455-186">DOM 颜色类型</span><span class="sxs-lookup"><span data-stu-id="9f455-186">DOM color type</span></span>  

<span data-ttu-id="9f455-187">**3D DOM**窗格显示以下选项。</span><span class="sxs-lookup"><span data-stu-id="9f455-187">The **3D DOM** pane displays the following options.</span></span>  

*   <span data-ttu-id="9f455-188">三个不同的 colorways。</span><span class="sxs-lookup"><span data-stu-id="9f455-188">Three different colorways.</span></span>  
    *   **<span data-ttu-id="9f455-189">热度地图-紫色到白</span><span class="sxs-lookup"><span data-stu-id="9f455-189">Heatmap - Purple to White</span></span>**  
    *   **<span data-ttu-id="9f455-190">热度地图-蓝到黄</span><span class="sxs-lookup"><span data-stu-id="9f455-190">Heatmap - Blue to Yellow</span></span>**  
    *   **<span data-ttu-id="9f455-191">热度地图-彩虹</span><span class="sxs-lookup"><span data-stu-id="9f455-191">Heatmap - Rainbow</span></span>**  
*   **<span data-ttu-id="9f455-192">使用背景色</span><span class="sxs-lookup"><span data-stu-id="9f455-192">Use background color</span></span>**  
*   **<span data-ttu-id="9f455-193">使用屏幕纹理</span><span class="sxs-lookup"><span data-stu-id="9f455-193">Use screen texture</span></span>**  
    
<span data-ttu-id="9f455-194">" **使用屏幕纹理** " 选项可将上下文添加到调试体验中。</span><span class="sxs-lookup"><span data-stu-id="9f455-194">The **Use screen texture** option adds context to your debugging experience.</span></span>  <span data-ttu-id="9f455-195">它直接将网页中的内容显示在元素上。</span><span class="sxs-lookup"><span data-stu-id="9f455-195">It directly displays the content from the webpage onto the elements.</span></span>  

## <span data-ttu-id="9f455-196">合成图层</span><span class="sxs-lookup"><span data-stu-id="9f455-196">Composited layers</span></span>

:::image type="complex" source="../media/experiments-layers.msft.png" alt-text=""复合图层" 窗格" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="9f455-198">"**复合图层**" 窗格</span><span class="sxs-lookup"><span data-stu-id="9f455-198">**Composited Layers** pane</span></span>
:::image-end:::  

<span data-ttu-id="9f455-199">" **复合图层** " 窗格在不更改上下文的情况下打开 " **图层** " 工具的元素。</span><span class="sxs-lookup"><span data-stu-id="9f455-199">The **Composited Layers** pane opens the elements of the **Layers** tool without changing contexts.</span></span>  <span data-ttu-id="9f455-200">您仍然可以访问每个图层的详细信息，并具有 **缓慢的滚动 rects** 和 **油漆**。</span><span class="sxs-lookup"><span data-stu-id="9f455-200">You may still access the details of each of the layers and have the **Slow scroll rects** and **Paint**.</span></span>

## <span data-ttu-id="9f455-201">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="9f455-201">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="9f455-202">Microsoft Edge Devtools 团队正在处理 UI，并根据你的反馈向3D 视图添加更多功能。</span><span class="sxs-lookup"><span data-stu-id="9f455-202">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on your feedback.</span></span>  <span data-ttu-id="9f455-203">发送反馈以帮助改进 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="9f455-203">Send your feedback to help improve the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="9f455-204">在 DevTools 中选择 "**发送反馈**" 图标，或选择 " `Alt` + `Shift` + `I` 在 Windows/Linux 上" 或 `Option` + `Shift` + `I` "在 macOS 上选择"，然后输入 DevTools 的任何反馈或功能请求。</span><span class="sxs-lookup"><span data-stu-id="9f455-204">Choose the **Send Feedback** icon in the DevTools or select `Alt`+`Shift`+`I` on Windows/Linux or `Option`+`Shift`+`I` on macOS and enter any feedback or feature requests you have for the DevTools.</span></span>  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D 视图-MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
