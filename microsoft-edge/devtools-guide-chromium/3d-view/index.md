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
# <span data-ttu-id="59919-104">3D 视图</span><span class="sxs-lookup"><span data-stu-id="59919-104">3D View</span></span>  

<span data-ttu-id="59919-105">通过在[文档对象模型 (DOM) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文中导航，使用**3d 视图**调试 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="59919-105">Use the **3D View** to debug your web application by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  <span data-ttu-id="59919-106">通过它，你可以执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="59919-106">With it you are able to perform the following tasks.</span></span>  

*   [<span data-ttu-id="59919-107">浏览转换为3D 透视的网页</span><span class="sxs-lookup"><span data-stu-id="59919-107">Explore the web page translated into a 3D perspective</span></span>](#3d-dom)  
*   [<span data-ttu-id="59919-108">基于 z 索引堆栈上下文进行调试</span><span class="sxs-lookup"><span data-stu-id="59919-108">Debug based on z-index stacking context</span></span>](#z-index)  
*   <span data-ttu-id="59919-109">清除 "DOM" 窗格或 " [z-索引" 窗格](#change-the-scope-of-your-exploration)[上的一些混乱情况](#changing-your-view)</span><span class="sxs-lookup"><span data-stu-id="59919-109">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>  
*   <span data-ttu-id="59919-110">[选择用于最佳调试 DOM 问题](#dom-color-type)或[z 索引问题](#z-index-color-type)的配色方案</span><span class="sxs-lookup"><span data-stu-id="59919-110">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>  

<span data-ttu-id="59919-111">如果想要浏览3D 视图项目的早期原型并自己运行代码，请参阅 [3D 视图示例][GithubMicrosoftedgeDevtoolssamples3dview]。</span><span class="sxs-lookup"><span data-stu-id="59919-111">If you want to explore an early prototype of 3D View project and run the code yourself, see [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span></span>   

<span data-ttu-id="59919-112">在左侧，有两个可用于调试体验的窗格。</span><span class="sxs-lookup"><span data-stu-id="59919-112">On the left side, there are two panes that you are able to use for your debugging experience.</span></span>  

1.  <span data-ttu-id="59919-113">" [Z-索引](#z-index) " 窗格。</span><span class="sxs-lookup"><span data-stu-id="59919-113">The [Z-index](#z-index) pane.</span></span>  <span data-ttu-id="59919-114">在 web 应用程序中使用 z 索引上下文浏览不同的元素。</span><span class="sxs-lookup"><span data-stu-id="59919-114">Navigate through the different elements in the web application with the z-index context in mind.</span></span>  <span data-ttu-id="59919-115">" **Z-索引** " 窗格是默认窗格。</span><span class="sxs-lookup"><span data-stu-id="59919-115">The **Z-index** pane is the default pane.</span></span>  
1.  <span data-ttu-id="59919-116">[3D DOM](#3d-dom)窗格。</span><span class="sxs-lookup"><span data-stu-id="59919-116">The [3D DOM](#3d-dom) pane.</span></span>  <span data-ttu-id="59919-117">使用所有元素轻松浏览整个 DOM。</span><span class="sxs-lookup"><span data-stu-id="59919-117">Explore the DOM as a whole with all the elements at your fingertips.</span></span>  <span data-ttu-id="59919-118">若要访问该窗格，请在 " **Z-索引**" 窗格旁边的 " **DOM** " 窗格中选择。</span><span class="sxs-lookup"><span data-stu-id="59919-118">To access the pane, select on the **DOM** pane next to the **Z-index** pane.</span></span>  
    
<span data-ttu-id="59919-119">在右侧，画布将显示从 [Z 索引](#z-index) 或 [3d DOM](#3d-dom)中选择的内容。</span><span class="sxs-lookup"><span data-stu-id="59919-119">On the right side, the canvas displays your selections from the [Z-index](#z-index) or [3D DOM](#3d-dom).</span></span>  

## <span data-ttu-id="59919-120">导航画布</span><span class="sxs-lookup"><span data-stu-id="59919-120">Navigating the canvas</span></span>  

:::image type="complex" source="../media/canvas.png" alt-text="3D 视图的画布" lightbox="../media/canvas.png":::
   <span data-ttu-id="59919-122">3D 视图的画布</span><span class="sxs-lookup"><span data-stu-id="59919-122">Canvas of 3D View</span></span>  
:::image-end:::  

### <span data-ttu-id="59919-123">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="59919-123">Keyboard shortcuts</span></span>  

*   <span data-ttu-id="59919-124">旋转 DOM：若要水平旋转，请按 `left-arrow` 和 `right-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="59919-124">Rotate the DOM:  To rotate horizontally, press the `left-arrow` and `right-arrow` keys.</span></span>  <span data-ttu-id="59919-125">若要垂直旋转，请按 `up-arrow` 和 `down-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="59919-125">To rotate vertically, press the `up-arrow` and `down-arrow` keys.</span></span>  
*   <span data-ttu-id="59919-126">导航 DOM：若要在相邻元素之间移动，请选择一个元素，然后按 " `up-arrow` 和" `down-arrow` 键。</span><span class="sxs-lookup"><span data-stu-id="59919-126">Navigate the DOM:  To move through the adjacent elements, select an element and press the `up-arrow` and `down-arrow` keys.</span></span>  

### <span data-ttu-id="59919-127">鼠标控件</span><span class="sxs-lookup"><span data-stu-id="59919-127">Mouse controls</span></span>  

*   <span data-ttu-id="59919-128">旋转 DOM：在画布空间周围选择和拖动。</span><span class="sxs-lookup"><span data-stu-id="59919-128">Rotate the DOM:  Select and drag around the canvas space.</span></span>  
*   <span data-ttu-id="59919-129">在 DOM 中移动：打开上下文菜单 \ (右键单击 \ ) 并按希望 DOM 移动的方向拖动。</span><span class="sxs-lookup"><span data-stu-id="59919-129">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span></span>  
*   <span data-ttu-id="59919-130">缩放：在触摸板上拖动两根手指或使用鼠标上的滚轮。</span><span class="sxs-lookup"><span data-stu-id="59919-130">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>  

### <span data-ttu-id="59919-131">屏幕上的控件</span><span class="sxs-lookup"><span data-stu-id="59919-131">On-screen controls</span></span>  

:::image type="complex" source="../media/controls-small.png" alt-text="屏幕上的控件" lightbox="../media/controls-small.png":::
   <span data-ttu-id="59919-133">屏幕上的控件</span><span class="sxs-lookup"><span data-stu-id="59919-133">On-screen controls</span></span>  
:::image-end:::  

*   <span data-ttu-id="59919-134">将画布视图重置为原始视图：选择 " **重置照相机** " 按钮，或选择 "重置照相机" 按钮，或选择 " **在视图中重置元素" 和 "重新中心相机** \" (侧向刷新图标 \ ) </span><span class="sxs-lookup"><span data-stu-id="59919-134">Reset the canvas view to the original view:  Select the **Reset camera** button, or select the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span></span>  
*   <span data-ttu-id="59919-135">刷新画布 \ (例如，如果浏览器发生更改或切换到设备仿真器视图 \ ) ：选择 "重 **拍快照** " 按钮，或选择 " **拍摄新快照** " 按钮 \ (刷新图标 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="59919-135">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Select the **Retake snapshot** button or select the **Take new snapshot** button \(refresh icon\).</span></span>  

## <span data-ttu-id="59919-136">Z-索引</span><span class="sxs-lookup"><span data-stu-id="59919-136">Z-index</span></span>  

:::image type="complex" source="../media/z-index-view-box.png" alt-text="Z-索引视图" lightbox="../media/z-index-view-box.png":::
   <span data-ttu-id="59919-138">Z-索引视图</span><span class="sxs-lookup"><span data-stu-id="59919-138">Z-index view</span></span>  
:::image-end:::  

<span data-ttu-id="59919-139">虽然 " **Z-索引** " 窗格具有与 **3d DOM** 窗格共享的功能，但这些窗格仍具有特定于窗格的元素。</span><span class="sxs-lookup"><span data-stu-id="59919-139">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span></span>  

### <span data-ttu-id="59919-140">利用堆栈上下文突出显示元素</span><span class="sxs-lookup"><span data-stu-id="59919-140">Highlight elements with stacking context</span></span>  

<span data-ttu-id="59919-141">利用 "堆栈上下文" 设置的 " **突出显示元素** "，你可以为画布上的元素启用 \ (和 off \ ) 的 z 索引标记。</span><span class="sxs-lookup"><span data-stu-id="59919-141">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span></span>  <span data-ttu-id="59919-142">默认情况下，复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="59919-142">The checkbox is selected by default.</span></span>  

### <span data-ttu-id="59919-143">更改您的勘探的范围</span><span class="sxs-lookup"><span data-stu-id="59919-143">Change the scope of your exploration</span></span>  

<span data-ttu-id="59919-144">" **显示所有元素** " 按钮是在更改下面的设置后显示 DOM 的所有元素的最快方式。</span><span class="sxs-lookup"><span data-stu-id="59919-144">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below.</span></span>  

<span data-ttu-id="59919-145">" **仅显示具有堆栈上下文的元素** " 按钮删除不带堆栈上下文的元素，并拼合 DOM 以便更轻松地进行导航。</span><span class="sxs-lookup"><span data-stu-id="59919-145">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span></span>  

<span data-ttu-id="59919-146">" **隔离选定元素** " 按钮实质上是三个按钮。</span><span class="sxs-lookup"><span data-stu-id="59919-146">The **Isolate selected element** button is essentially three buttons in one.</span></span>  <span data-ttu-id="59919-147">" **隔离选定元素** " 按钮下面有两个复选框： " **显示所有父项** " 复选框，并 **仅保留具有 "新建堆栈上下文** " 复选框的父项。</span><span class="sxs-lookup"><span data-stu-id="59919-147">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span></span>  

<span data-ttu-id="59919-148">默认情况下，" **显示所有家长** " 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="59919-148">The **Show all parents** checkbox is selected by default.</span></span>  <span data-ttu-id="59919-149">如果在 "画布" 窗格上选择某个元素并选择 " **隔离选定元素** " 按钮，则画布仅显示该元素和任何父元素。</span><span class="sxs-lookup"><span data-stu-id="59919-149">If you select an element on the canvas pane and select **Isolate selected element** button, the canvas only displays the element and any parents.</span></span>  

<span data-ttu-id="59919-150">如果选中 " **仅保留新堆栈上下文的父项** " 复选框，然后选择 " **隔离所选元素** " 按钮，则画布仅显示具有新堆栈上下文的元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59919-150">If you select the **Keep only parents with new stacking context** checkbox, and select **Isolate selected element** button, the canvas only displays the element and the parents that have a new stacking context.</span></span>  

<span data-ttu-id="59919-151">如果取消选中两个复选框，然后选择 " **隔离选定元素** " 按钮，则画布仅显示您在第一个位置中选择的元素。</span><span class="sxs-lookup"><span data-stu-id="59919-151">If you deselect both of the checkboxes and select **Isolate selected element** button, the canvas only displays the element you chose in the first place.</span></span>  

<span data-ttu-id="59919-152">在 **3D DOM** 面板的最下方，找到 " **隐藏具有与父项相同的绘制顺序** " 复选框的元素。</span><span class="sxs-lookup"><span data-stu-id="59919-152">At the very bottom of the **3D DOM** panel, locate the **Hide elements with the same paint order as their parent** checkbox.</span></span>  <span data-ttu-id="59919-153">选中并取消选中复选框将根据您的选择刷新元素。</span><span class="sxs-lookup"><span data-stu-id="59919-153">Selecting and deselecting the checkbox refreshes the elements based on your selection.</span></span>  <span data-ttu-id="59919-154">如果选中，共享绘制顺序的元素将拼合到父项。</span><span class="sxs-lookup"><span data-stu-id="59919-154">If selected, elements that share paint order are flattened to the parent.</span></span>  

<span data-ttu-id="59919-155">这些选项旨在清理在你的画布中创建更复杂的网页的一些混乱程度。</span><span class="sxs-lookup"><span data-stu-id="59919-155">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>  

### <span data-ttu-id="59919-156">Z-索引颜色类型</span><span class="sxs-lookup"><span data-stu-id="59919-156">Z-index color type</span></span>  

<span data-ttu-id="59919-157">这是你的画布中的 DOM 可以使用的不同可视化效果。</span><span class="sxs-lookup"><span data-stu-id="59919-157">The are the different visualizations you may use for the DOM in your canvas.</span></span>  <span data-ttu-id="59919-158">无论是将它用于趣味，还是因为可视化效果帮助你更好地可视化 DOM，DevTools 有三种不同的 colorways 和 **背景色** 设置。</span><span class="sxs-lookup"><span data-stu-id="59919-158">Whether you use it for fun or because the visualizations help you visualize the DOM better, The DevTools has three different colorways as well as a **background color** setting.</span></span>  <span data-ttu-id="59919-159">单选按钮使你可以切换选项，并选择最适合你的项目的颜色类型 (或喜欢的最大 ) 。</span><span class="sxs-lookup"><span data-stu-id="59919-159">The radio buttons allow you to toggle through the options and pick the color type most appropriate for your project \(or that you like the most\).</span></span>  

## <span data-ttu-id="59919-160">3D DOM</span><span class="sxs-lookup"><span data-stu-id="59919-160">3D DOM</span></span>  

:::image type="complex" source="../media/dom-purple-box.png" alt-text="DOM 视图" lightbox="../media/dom-purple-box.png":::
   <span data-ttu-id="59919-162">DOM 视图</span><span class="sxs-lookup"><span data-stu-id="59919-162">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="59919-163">如果你想要使用更多常规调试视图，而不是 z 索引体验，则 **3D DOM** 将为 DOM 提供整体外观。</span><span class="sxs-lookup"><span data-stu-id="59919-163">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span></span>  <span data-ttu-id="59919-164">由于删除了 z 索引上下文，因此 DOM 更紧密地堆叠。</span><span class="sxs-lookup"><span data-stu-id="59919-164">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span>  <span data-ttu-id="59919-165">**3D DOM**窗格具有类似的功能，但有一些细微差别。</span><span class="sxs-lookup"><span data-stu-id="59919-165">The **3D DOM** pane has similar functionality, but there are a few nuances.</span></span>  

### <span data-ttu-id="59919-166">更改视图</span><span class="sxs-lookup"><span data-stu-id="59919-166">Changing your view</span></span>  

<span data-ttu-id="59919-167">在 **3D DOM** 窗格上，" **隔离选定元素** " 按钮包含 " **子** 元素" 和 " **包含父项** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="59919-167">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span></span>  <span data-ttu-id="59919-168">默认情况下，两个复选框均被选中，这意味着选择画布上的元素后选择 " **隔离选定的元素** " 按钮应显示所选元素、元素的父元素和元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="59919-168">By default both checkboxes are selected, which means that selecting the **Isolate selected element** button after selecting an element on the canvas should display the element chosen, the parents of the element, and the children of the element.</span></span>  <span data-ttu-id="59919-169">取消选中 " **包含子** 元素" 复选框，然后再次选择 " **隔离选定元素** " 按钮将显示所选元素和元素的父元素。</span><span class="sxs-lookup"><span data-stu-id="59919-169">Deselecting the **Include children** checkbox and selecting the **Isolate selected element** button again should display the selected element and the parents of the element.</span></span>  <span data-ttu-id="59919-170">如果选择 " **包含儿童** " 复选框并取消选择 " **包括家长** " 复选框，然后选择 " **隔离所选元素** " 按钮，则画布将显示该元素和任何子元素。</span><span class="sxs-lookup"><span data-stu-id="59919-170">If you select the **Include children** checkbox and deselect the **Include parents** checkbox before selecting **Isolate selected element** button, the canvas then displays the element and any children.</span></span>  <span data-ttu-id="59919-171">如果取消选中两个复选框，然后选择 " **隔离选定元素** " 按钮，则画布仅显示您以前选择的元素。</span><span class="sxs-lookup"><span data-stu-id="59919-171">If you deselect both checkboxes and select **Isolate selected element** button, the canvas only displays the element you previously selected.</span></span>  

<span data-ttu-id="59919-172">"控件" 窗格上标题为 " **嵌套级别** " 的 "页面" 旁边带有数字的滑块。</span><span class="sxs-lookup"><span data-stu-id="59919-172">A slider on the control pane titled **Nesting level for page** with a number next to it.</span></span>  <span data-ttu-id="59919-173">该数字表示文档的层数。</span><span class="sxs-lookup"><span data-stu-id="59919-173">The number indicates the number of layers for the document.</span></span>  <span data-ttu-id="59919-174">将滑块向左拖动会导致最外层的图层 peel 离开，直到将嵌套级别设置为1，这将仅显示 DOM 中的最远距离元素。</span><span class="sxs-lookup"><span data-stu-id="59919-174">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to 1, which displays only the furthest back element in the DOM.</span></span>  <span data-ttu-id="59919-175">如果你尝试进一步了解较低级别中发生的情况，则拖动滑块可使你删除一些混乱效果。</span><span class="sxs-lookup"><span data-stu-id="59919-175">Dragging the slider allows you to remove some of the clutter if you are trying to get a closer look at what is happening in the lower levels.</span></span>  

### <span data-ttu-id="59919-176">DOM 颜色类型</span><span class="sxs-lookup"><span data-stu-id="59919-176">DOM color type</span></span>  

<span data-ttu-id="59919-177">除了 **热度地图-紫色到白色**、 **热度地图**、 **热度地图**和 **使用 "背景色** " 单选按钮，还有 **使用屏幕纹理**。</span><span class="sxs-lookup"><span data-stu-id="59919-177">In addition to the **Heatmap - Purple to White**, **Heatmap - Blue to Yellow**, **Heatmap - Rainbow**, and **Use background color** radio buttons, there is **Use screen texture**.</span></span>  <span data-ttu-id="59919-178">屏幕纹理通过将网页中的内容直接显示在元素上来将上下文添加到调试体验。</span><span class="sxs-lookup"><span data-stu-id="59919-178">The screen texture adds context to your debugging experience by displaying the content from the web page directly onto the elements.</span></span>  <span data-ttu-id="59919-179">在 **3D DOM** 窗格上，"  **颜色类型** " 设置仍是正在进行的工作，因为某些网站在3d 视图中呈现屏幕纹理较难。</span><span class="sxs-lookup"><span data-stu-id="59919-179">On the **3D DOM** pane, the  **color type** setting is still a work in progress, since some websites have a harder time rendering screen texture in the 3D View.</span></span>  

## <span data-ttu-id="59919-180">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="59919-180">Getting in touch with the Microsoft Edge DevTools team</span></span>

<span data-ttu-id="59919-181">Microsoft Edge Devtools 团队正在处理 UI，并根据用户（如用户）向3D 视图添加更多功能。</span><span class="sxs-lookup"><span data-stu-id="59919-181">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on asks from users like you.</span></span>  <span data-ttu-id="59919-182">请发送反馈，帮助改进 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="59919-182">Please send your feedback to help improve the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="59919-183">只需选择 DevTools 中的反馈图标，或按 `Alt` + `Shift` + `I` \ (Windows \ ) 或按下 `Option` + `Shift` + `I` \ (macOS \ ) 并输入 DevTools 的任何反馈或功能请求。</span><span class="sxs-lookup"><span data-stu-id="59919-183">Simply select the feedback icon in the DevTools or press `Alt`+`Shift`+`I` \(Windows\) or press `Option`+`Shift`+`I` \(macOS\) and enter any feedback or feature requests you have for the DevTools.</span></span>  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D 视图-MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
