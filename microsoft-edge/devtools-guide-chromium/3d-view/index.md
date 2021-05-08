---
description: 所有关于 3D 视图及其使用方法。
title: 3D 视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: bd91939a19f02a426834a85ef92eca388f8f1eda
ms.sourcegitcommit: 5e218b24fb21fcfa9c82b99f17373fed1ba5a21c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "11203968"
---
# <a name="3d-view"></a><span data-ttu-id="b188c-104">3D 视图</span><span class="sxs-lookup"><span data-stu-id="b188c-104">3D View</span></span>  

<span data-ttu-id="b188c-105">使用 **3D 视图** 通过浏览文档对象模型和 [DOM ][MDNDocumentObjectModel] (或 [z 索引][MDNZIndex]) 上下文来调试 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="b188c-105">Use the **3D View** to debug your web app by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  <span data-ttu-id="b188c-106">通过它，您可以完成以下任务。</span><span class="sxs-lookup"><span data-stu-id="b188c-106">With it, you may complete the following tasks.</span></span>  

*   [<span data-ttu-id="b188c-107">浏览翻译为 3D 视角的网页</span><span class="sxs-lookup"><span data-stu-id="b188c-107">Explore the web page translated into a 3D perspective</span></span>](#3d-dom)  
*   [<span data-ttu-id="b188c-108">基于 z 索引堆栈上下文进行调试</span><span class="sxs-lookup"><span data-stu-id="b188c-108">Debug based on z-index stacking context</span></span>](#z-index)  
*   [<span data-ttu-id="b188c-109">通过复合层从 3D 视图访问图层工具功能</span><span class="sxs-lookup"><span data-stu-id="b188c-109">Access the Layers tool functionality from 3D View with composited layers</span></span>](#composited-layers)  
*   <span data-ttu-id="b188c-110">[清除 DOM 窗格或](#changing-your-view) z 索引窗格中的 [一些待筛选邮件](#change-the-scope-of-your-exploration)</span><span class="sxs-lookup"><span data-stu-id="b188c-110">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>  
*   <span data-ttu-id="b188c-111">[选取配色方案以最好地调试 DOM 问题](#dom-color-type) 或 [z 索引问题](#z-index-color-type)</span><span class="sxs-lookup"><span data-stu-id="b188c-111">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>  

<span data-ttu-id="b188c-112">如果你想要探索 3D 视图项目的早期原型并自己运行代码，请导航到["3D 视图示例"。][GithubMicrosoftedgeDevtoolssamples3dview]</span><span class="sxs-lookup"><span data-stu-id="b188c-112">If you want to explore an early prototype of 3D View project and run the code yourself, navigate to [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span></span>  

<span data-ttu-id="b188c-113">在左侧，有三个窗格可以用于调试体验。</span><span class="sxs-lookup"><span data-stu-id="b188c-113">On the left side, there are three panes that you may use for your debugging experience.</span></span>  

*   <span data-ttu-id="b188c-114">Z [索引](#z-index) 窗格。</span><span class="sxs-lookup"><span data-stu-id="b188c-114">The [Z-index](#z-index) pane.</span></span>  <span data-ttu-id="b188c-115">在 Web 应用中的不同元素中导航，并注意 z-index 上下文。</span><span class="sxs-lookup"><span data-stu-id="b188c-115">Navigate through the different elements in the web app with the z-index context in mind.</span></span>  <span data-ttu-id="b188c-116">Z **索引窗格** 是默认窗格。</span><span class="sxs-lookup"><span data-stu-id="b188c-116">The **Z-index** pane is the default pane.</span></span>  
*   <span data-ttu-id="b188c-117">[3D DOM](#3d-dom)窗格。</span><span class="sxs-lookup"><span data-stu-id="b188c-117">The [3D DOM](#3d-dom) pane.</span></span>  <span data-ttu-id="b188c-118">通过可轻松访问的所有元素，作为一个整体探索 DOM。</span><span class="sxs-lookup"><span data-stu-id="b188c-118">Explore the DOM as a whole with all the elements easily accessible.</span></span>  <span data-ttu-id="b188c-119">若要访问该窗格，请选择 **Z 索引** 窗格旁边的 **DOM** 窗格。</span><span class="sxs-lookup"><span data-stu-id="b188c-119">To access the pane, choose the **DOM** pane next to the **Z-index** pane.</span></span>  
*   <span data-ttu-id="b188c-120">复合 [层窗格](#composited-layers) 。</span><span class="sxs-lookup"><span data-stu-id="b188c-120">The [Composited Layers](#composited-layers) pane.</span></span>  <span data-ttu-id="b188c-121">添加另一个 3D 元素以从层角度创建更全面的体验。</span><span class="sxs-lookup"><span data-stu-id="b188c-121">Add another 3D element to create a more comprehensive experience from a layers perspective.</span></span>  <span data-ttu-id="b188c-122">若要访问窗格，请选择 **"DOM"** 窗格旁边的"复合层"窗格。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b188c-122">To access the pane, choose the **Composited Layers** pane next to the **DOM** pane.</span></span>  
    
<span data-ttu-id="b188c-123">在右侧，画布显示来自[Z 索引](#z-index)[、3D DOM](#3d-dom)或[复合层的选择](#composited-layers)。</span><span class="sxs-lookup"><span data-stu-id="b188c-123">On the right side, the canvas displays your selections from the [Z-index](#z-index), [3D DOM](#3d-dom), or [Composited Layers](#composited-layers).</span></span>  

## <a name="navigating-the-canvas"></a><span data-ttu-id="b188c-124">在画布上导航</span><span class="sxs-lookup"><span data-stu-id="b188c-124">Navigating the canvas</span></span>  

:::image type="complex" source="../media/3d-view-canvas.msft.png" alt-text="3D 视图画布" lightbox="../media/3d-view-canvas.msft.png":::
   <span data-ttu-id="b188c-126">3D 视图画布</span><span class="sxs-lookup"><span data-stu-id="b188c-126">Canvas of 3D View</span></span>  
:::image-end:::  

### <a name="keyboard-shortcuts"></a><span data-ttu-id="b188c-127">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="b188c-127">Keyboard shortcuts</span></span>  

*   <span data-ttu-id="b188c-128">旋转 DOM：若要水平旋转，请选择 `left-arrow` 和 `right-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="b188c-128">Rotate the DOM:  To rotate horizontally, select the `left-arrow` and `right-arrow` keys.</span></span>  <span data-ttu-id="b188c-129">若要垂直旋转，请选择 `up-arrow` 和 `down-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="b188c-129">To rotate vertically, select the `up-arrow` and `down-arrow` keys.</span></span>  
*   <span data-ttu-id="b188c-130">导航 DOM：若要在相邻的元素间移动，请选择一个元素，然后选择 `up-arrow` 和 `down-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="b188c-130">Navigate the DOM:  To move through the adjacent elements, choose an element and select the `up-arrow` and `down-arrow` keys.</span></span>  

### <a name="mouse-controls"></a><span data-ttu-id="b188c-131">鼠标控件</span><span class="sxs-lookup"><span data-stu-id="b188c-131">Mouse controls</span></span>  

*   <span data-ttu-id="b188c-132">旋转 DOM：选择并拖动画布空间。</span><span class="sxs-lookup"><span data-stu-id="b188c-132">Rotate the DOM:  Choose and drag around the canvas space.</span></span>  
*   <span data-ttu-id="b188c-133">平移 DOM：打开上下文菜单 \ (右键单击\) 并按希望 DOM 移动的方向拖动。</span><span class="sxs-lookup"><span data-stu-id="b188c-133">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span></span>  
*   <span data-ttu-id="b188c-134">缩放：在触摸板上拖动两根手指或使用鼠标上的滚动盘。</span><span class="sxs-lookup"><span data-stu-id="b188c-134">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>  

### <a name="on-screen-controls"></a><span data-ttu-id="b188c-135">屏幕控件</span><span class="sxs-lookup"><span data-stu-id="b188c-135">On-screen controls</span></span>  

:::image type="complex" source="../media/3d-view-controls-small.msft.png" alt-text="屏幕控件" lightbox="../media/3d-view-controls-small.msft.png":::
   <span data-ttu-id="b188c-137">屏幕控件</span><span class="sxs-lookup"><span data-stu-id="b188c-137">On-screen controls</span></span>  
:::image-end:::  

*   <span data-ttu-id="b188c-138">将画布视图重置为原始视图：选择"重置\*\*\*\* 相机"按钮，或选择"重置视图中的元素"，然后重新居中相机**\ (** 侧向刷新图标\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="b188c-138">Reset the canvas view to the original view:  Choose the **Reset camera** button, or choose the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span></span>  
*   <span data-ttu-id="b188c-139">刷新画布 \ (例如，如果浏览器发生更改或切换到设备仿真器视图\) ：选择"重新拍摄快照"按钮或选择"获取新快照\*\*\*\*"按钮 \ (刷新\*\*\*\* 图标\) 。</span><span class="sxs-lookup"><span data-stu-id="b188c-139">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Choose the **Retake snapshot** button or choose the **Take new snapshot** button \(refresh icon\).</span></span>  

## <a name="z-index"></a><span data-ttu-id="b188c-140">Z 索引</span><span class="sxs-lookup"><span data-stu-id="b188c-140">Z-index</span></span>  

:::image type="complex" source="../media/3d-view-z-index-view-box.msft.png" alt-text="Z 索引视图" lightbox="../media/3d-view-z-index-view-box.msft.png":::
   <span data-ttu-id="b188c-142">Z 索引视图</span><span class="sxs-lookup"><span data-stu-id="b188c-142">Z-index view</span></span>  
:::image-end:::  

<span data-ttu-id="b188c-143">虽然 **Z 索引** 窗格具有与 **3D DOM** 窗格的共享功能，但窗格仍具有该窗格特有的元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-143">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span></span>  

### <a name="highlight-elements-with-stacking-context"></a><span data-ttu-id="b188c-144">使用堆叠上下文突出显示元素</span><span class="sxs-lookup"><span data-stu-id="b188c-144">Highlight elements with stacking context</span></span>  

<span data-ttu-id="b188c-145">使用 **堆叠上下文设置突出显示** 元素允许你打开 \ (和 off\) 画布上元素的 z-index 标记。</span><span class="sxs-lookup"><span data-stu-id="b188c-145">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span></span>  <span data-ttu-id="b188c-146">默认情况下选中复选框。</span><span class="sxs-lookup"><span data-stu-id="b188c-146">The checkbox is chosen by default.</span></span>  

### <a name="change-the-scope-of-your-exploration"></a><span data-ttu-id="b188c-147">更改你的探索范围</span><span class="sxs-lookup"><span data-stu-id="b188c-147">Change the scope of your exploration</span></span>  

<span data-ttu-id="b188c-148">" **显示所有元素** "按钮是在更改其下方的设置后显示 DOM 的所有元素的最快方法。</span><span class="sxs-lookup"><span data-stu-id="b188c-148">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below it.</span></span>  

<span data-ttu-id="b188c-149">" **仅显示具有堆叠上下文** 的元素"按钮删除元素而不堆叠上下文并平展 DOM 以简化导航。</span><span class="sxs-lookup"><span data-stu-id="b188c-149">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span></span>  

<span data-ttu-id="b188c-150">" **隔离所选元素"** 按钮实质上是一个中的三个按钮。</span><span class="sxs-lookup"><span data-stu-id="b188c-150">The **Isolate selected element** button is essentially three buttons in one.</span></span>  <span data-ttu-id="b188c-151">"隔离所选元素"按钮下方\*\*\*\* 有两个复选框："显示\*\*\*\* 所有父元素"复选框和"仅保留具有新堆叠**上下文的父项"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b188c-151">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span></span>  

<span data-ttu-id="b188c-152">默认情况下 **，"** 显示所有家长"复选框已打开。</span><span class="sxs-lookup"><span data-stu-id="b188c-152">The **Show all parents** checkbox is turned on by default.</span></span>  <span data-ttu-id="b188c-153">若要在画布上显示元素和任何父元素，请选择一个元素并选择"隔离 **所选元素"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b188c-153">To display the element and any parents on the canvas, choose an element and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="b188c-154">若要在画布上显示具有新堆叠上下文的元素和父元素，请打开"仅保留具有新\*\*\*\* 堆叠上下文的父元素"设置并选择"隔离所选元素 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b188c-154">To display the element and the parents that have a new stacking context on the canvas, turn on the **Keep only parents with new stacking context** setting and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="b188c-155">若要在画布上显示你选择的元素，请关闭这两个设置，然后选择" **隔离所选元素"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b188c-155">To display the element you chose on the canvas, turn off both the settings and choose **Isolate selected element** button.</span></span>  

<span data-ttu-id="b188c-156">在 **3D DOM** 窗格底部，找到"隐藏与父元素的绘制顺序相同的 **元素"复选框** 。</span><span class="sxs-lookup"><span data-stu-id="b188c-156">At the bottom of the **3D DOM** pane, locate the **Hide elements with the same paint order as their parent** checkbox.</span></span>  <span data-ttu-id="b188c-157">选择并取消选中复选框将基于你的选择刷新元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-157">Choosing and deselecting the checkbox refreshes the elements based on your choice.</span></span>  <span data-ttu-id="b188c-158">如果选中，共享绘制顺序的元素将平展到父元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-158">If chosen, elements that share paint order are flattened to the parent.</span></span>  

<span data-ttu-id="b188c-159">这些选项旨在清除一些更复杂的网页在画布上创建的混乱情况。</span><span class="sxs-lookup"><span data-stu-id="b188c-159">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>  

### <a name="z-index-color-type"></a><span data-ttu-id="b188c-160">Z 索引颜色类型</span><span class="sxs-lookup"><span data-stu-id="b188c-160">Z-index color type</span></span>  

<span data-ttu-id="b188c-161">是你可能在画布中用于 DOM 的不同可视化效果。</span><span class="sxs-lookup"><span data-stu-id="b188c-161">The are the different visualizations you may use for the DOM in your canvas.</span></span>  <span data-ttu-id="b188c-162">无论是为了有趣还是因为可视化效果有助于更好地可视化 DOM，DevTools 都有不同的颜色通道和" **使用背景色"** 选项。</span><span class="sxs-lookup"><span data-stu-id="b188c-162">Whether you use it for fun or because the visualizations help you visualize the DOM better, the DevTools have different colorways and a **Use background color** option.</span></span>  <span data-ttu-id="b188c-163">Z**索引窗格**与**3D DOM**窗格共享**紫色到白色**和背景色。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b188c-163">The **Z-index** pane shares the **Purple to White** and **Background Color** with the **3D DOM** pane.</span></span>  <span data-ttu-id="b188c-164">考虑到添加了 z 索引标签的可视元素，你的反馈导致颜色选项的数量减少。</span><span class="sxs-lookup"><span data-stu-id="b188c-164">Given the added visual element of the z-index labels, your feedback that led to a reduction in the number of color options.</span></span>  <span data-ttu-id="b188c-165">新的简单性改进了 z-index 调试体验。</span><span class="sxs-lookup"><span data-stu-id="b188c-165">The new simplicity improves the z-index debugging experience.</span></span>  <span data-ttu-id="b188c-166">单选按钮允许你切换选项并选取颜色类型。</span><span class="sxs-lookup"><span data-stu-id="b188c-166">The radio buttons allow you to toggle through the options and pick the color type.</span></span>  <span data-ttu-id="b188c-167">颜色类型最适用于你的项目，或最喜欢的颜色类型。</span><span class="sxs-lookup"><span data-stu-id="b188c-167">The color type is either most appropriate for your project or one that you like the most.</span></span>  

## <a name="3d-dom"></a><span data-ttu-id="b188c-168">3D DOM</span><span class="sxs-lookup"><span data-stu-id="b188c-168">3D DOM</span></span>  

:::image type="complex" source="../media/3d-view-dom-purple-box.msft.png" alt-text="DOM 视图" lightbox="../media/3d-view-dom-purple-box.msft.png":::
   <span data-ttu-id="b188c-170">DOM 视图</span><span class="sxs-lookup"><span data-stu-id="b188c-170">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="b188c-171">如果你想要获得更多常规调试视图，而不是 z 索引体验 **，3D DOM** 会提供 DOM 的整体外观。</span><span class="sxs-lookup"><span data-stu-id="b188c-171">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span></span>  <span data-ttu-id="b188c-172">由于删除了 z-index 上下文，因此 DOM 的堆叠更为紧密和干净。</span><span class="sxs-lookup"><span data-stu-id="b188c-172">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span>  <span data-ttu-id="b188c-173">**3D DOM**窗格具有类似的功能，但存在一些细微差别。</span><span class="sxs-lookup"><span data-stu-id="b188c-173">The **3D DOM** pane has similar functionality, but there are a few nuances.</span></span>  

### <a name="changing-your-view"></a><span data-ttu-id="b188c-174">更改视图</span><span class="sxs-lookup"><span data-stu-id="b188c-174">Changing your view</span></span>  

<span data-ttu-id="b188c-175">在 **3D DOM** 窗格中，" **隔离** 所选元素"按钮具有" **包括子** 元素"和" **包括父项"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b188c-175">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span></span>  <span data-ttu-id="b188c-176">默认情况下，这两个复选框都打开。</span><span class="sxs-lookup"><span data-stu-id="b188c-176">Both checkboxes are turned on by default.</span></span>  <span data-ttu-id="b188c-177">这意味着，如果在选择元素后\*\*\*\* 选择"隔离所选元素"按钮，画布将显示所选元素、元素的父元素和元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-177">That means if you choose the **Isolate selected element** button after you choose an element, the canvas displays the chosen element, the parents of the element, and the children of the element.</span></span>  <span data-ttu-id="b188c-178">关闭" **包含子元素** "设置，然后再次选择" **隔离所选元素** "按钮以显示所选元素和元素的父元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-178">Turn off the **Include children** setting and choose the **Isolate selected element** button again to display the chosen element and the parents of the element.</span></span>  <span data-ttu-id="b188c-179">如果打开" **包含** 子元素"设置并关闭" **包含** 父元素"设置，然后选择"隔离 **所选** 元素"按钮，画布将显示元素和任何子元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-179">If you turn on the **Include children** setting and turn off the **Include parents** setting and then choose the **Isolate selected element** button, the canvas displays the element and any children.</span></span>  <span data-ttu-id="b188c-180">如果同时关闭这两个设置并选择" **隔离所选元素** "按钮，画布将仅显示之前选择的元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-180">If you turn off both settings and choose the **Isolate selected element** button, the canvas only displays the element you previously chose.</span></span>  

<span data-ttu-id="b188c-181">控件窗格上名为 **"嵌套级别的页面"的滑块，** 旁边有一个数字。</span><span class="sxs-lookup"><span data-stu-id="b188c-181">A slider on the control pane named **Nesting level for page** with a number next to it.</span></span>  <span data-ttu-id="b188c-182">数字指示文档的图层数。</span><span class="sxs-lookup"><span data-stu-id="b188c-182">The number indicates the number of layers for the document.</span></span>  <span data-ttu-id="b188c-183">向左拖动滑块会导致最外面的图层消失，直到你将嵌套层设置为 ，这将仅显示 DOM 中最远 `1` 的后退元素。</span><span class="sxs-lookup"><span data-stu-id="b188c-183">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to `1`, which displays only the furthest back element in the DOM.</span></span>  <span data-ttu-id="b188c-184">若要删除某些待筛选邮件，请拖动滑块。</span><span class="sxs-lookup"><span data-stu-id="b188c-184">To remove some of the clutter, drag the slider.</span></span>  <span data-ttu-id="b188c-185">它可以帮助你仔细查看较低级别中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="b188c-185">It helps you get a closer look at what is happening in the lower levels.</span></span>  

### <a name="dom-color-type"></a><span data-ttu-id="b188c-186">DOM 颜色类型</span><span class="sxs-lookup"><span data-stu-id="b188c-186">DOM color type</span></span>  

<span data-ttu-id="b188c-187">**3D DOM**窗格显示以下选项。</span><span class="sxs-lookup"><span data-stu-id="b188c-187">The **3D DOM** pane displays the following options.</span></span>  

*   <span data-ttu-id="b188c-188">三种不同的颜色。</span><span class="sxs-lookup"><span data-stu-id="b188c-188">Three different colorways.</span></span>  
    *   **<span data-ttu-id="b188c-189">热度图 - 紫色到白色</span><span class="sxs-lookup"><span data-stu-id="b188c-189">Heatmap - Purple to White</span></span>**  
    *   **<span data-ttu-id="b188c-190">热度图 - 蓝色到黄色</span><span class="sxs-lookup"><span data-stu-id="b188c-190">Heatmap - Blue to Yellow</span></span>**  
    *   **<span data-ttu-id="b188c-191">热图 - 红红</span><span class="sxs-lookup"><span data-stu-id="b188c-191">Heatmap - Rainbow</span></span>**  
*   **<span data-ttu-id="b188c-192">使用背景色</span><span class="sxs-lookup"><span data-stu-id="b188c-192">Use background color</span></span>**  
*   **<span data-ttu-id="b188c-193">使用屏幕纹理</span><span class="sxs-lookup"><span data-stu-id="b188c-193">Use screen texture</span></span>**  
    
<span data-ttu-id="b188c-194">使用 **屏幕纹理选项** 将上下文添加到你的调试体验。</span><span class="sxs-lookup"><span data-stu-id="b188c-194">The **Use screen texture** option adds context to your debugging experience.</span></span>  <span data-ttu-id="b188c-195">它直接将网页中的内容显示在元素上。</span><span class="sxs-lookup"><span data-stu-id="b188c-195">It directly displays the content from the webpage onto the elements.</span></span>  

## <a name="composited-layers"></a><span data-ttu-id="b188c-196">复合层</span><span class="sxs-lookup"><span data-stu-id="b188c-196">Composited layers</span></span>

:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="b188c-198">**复合层** 窗格</span><span class="sxs-lookup"><span data-stu-id="b188c-198">**Composited Layers** pane</span></span>
:::image-end:::  

<span data-ttu-id="b188c-199">The **Composited Layers** pane opens the elements of the **Layers** tool without changing contexts.</span><span class="sxs-lookup"><span data-stu-id="b188c-199">The **Composited Layers** pane opens the elements of the **Layers** tool without changing contexts.</span></span>  <span data-ttu-id="b188c-200">你仍然可以访问每个图层的详细信息，并拥有慢速**滚动\*\*\*\*画图。**</span><span class="sxs-lookup"><span data-stu-id="b188c-200">You may still access the details of each of the layers and have the **Slow scroll rects** and **Paint**.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b188c-201">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="b188c-201">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="b188c-202">开发人员Microsoft Edge团队正在处理 UI，并基于你的反馈向 3D 视图添加更多功能。</span><span class="sxs-lookup"><span data-stu-id="b188c-202">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on your feedback.</span></span>  <span data-ttu-id="b188c-203">发送反馈以帮助改进开发人员Microsoft Edge开发工具。</span><span class="sxs-lookup"><span data-stu-id="b188c-203">Send your feedback to help improve the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="b188c-204">在\*\*\*\* DevTools 中选择"发送反馈"图标，或在 Windows/Linux 或 macOS 上选择，然后输入你的 `Alt` + `Shift` + `I` `Option` + `Shift` + `I` DevTools 的任何反馈或功能请求。</span><span class="sxs-lookup"><span data-stu-id="b188c-204">Choose the **Send Feedback** icon in the DevTools or select `Alt`+`Shift`+`I` on Windows/Linux or `Option`+`Shift`+`I` on macOS and enter any feedback or feature requests you have for the DevTools.</span></span>  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft EdgeDevTools 3D 视图 - MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
