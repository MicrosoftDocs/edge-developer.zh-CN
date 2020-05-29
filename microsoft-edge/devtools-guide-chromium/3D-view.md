---
description: 所有关于3D 视图以及如何使用它的信息。
title: 3D 视图
author: erdraud
ms.author: erdraud
ms.date: 11/27/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f2ae80426da71797d4bee4060d33965f04047e19
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562940"
---
# <span data-ttu-id="17c11-104">3D 视图</span><span class="sxs-lookup"><span data-stu-id="17c11-104">3D View</span></span>

<span data-ttu-id="17c11-105">通过浏览[文档对象模型](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)（DOM）或[z 索引](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index)堆栈上下文，使用**3d 视图**调试 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="17c11-105">Use the **3D View** to debug your web application by navigating through the [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) (DOM) or the [z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index) stacking context.</span></span> <span data-ttu-id="17c11-106">有了它，您可以：</span><span class="sxs-lookup"><span data-stu-id="17c11-106">With it you can:</span></span> 

- [<span data-ttu-id="17c11-107">浏览转换为 3D perspevtive 的网页</span><span class="sxs-lookup"><span data-stu-id="17c11-107">Explore the web page translated into a 3D perspevtive</span></span>](#3d-dom)
- [<span data-ttu-id="17c11-108">基于 z 索引堆栈上下文进行调试</span><span class="sxs-lookup"><span data-stu-id="17c11-108">Debug based on z-index stacking context</span></span>](#z-index)
- <span data-ttu-id="17c11-109">清除 "DOM" 窗格或 " [z 索引" 窗格](#change-the-scope-of-your-exploration)[中的一些混乱情况](#changing-your-view)</span><span class="sxs-lookup"><span data-stu-id="17c11-109">[Clear some of the clutter in the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>
- <span data-ttu-id="17c11-110">[选择用于最佳调试 DOM 问题](#dom-color-type)或[z 索引问题](#z-index-color-type)的配色方案</span><span class="sxs-lookup"><span data-stu-id="17c11-110">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>

<span data-ttu-id="17c11-111">有两个可用于调试体验的窗格。</span><span class="sxs-lookup"><span data-stu-id="17c11-111">There are two panes that you can use for your debugging experience.</span></span>

1. <span data-ttu-id="17c11-112">**Z-索引**在 web 应用程序中使用 z 索引上下文浏览不同的元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-112">**Z-index** Navigate through the different elements in the web application with the z-index context in mind.</span></span> <span data-ttu-id="17c11-113">这是默认窗格。</span><span class="sxs-lookup"><span data-stu-id="17c11-113">This is the default pane.</span></span>
2. <span data-ttu-id="17c11-114">**3D DOM**使用所有元素轻松浏览整个 DOM。</span><span class="sxs-lookup"><span data-stu-id="17c11-114">**3D DOM** Explore the DOM as a whole with all the elements at your fingertips.</span></span> <span data-ttu-id="17c11-115">若要访问此窗格，请单击 "Z 索引" 窗格旁边的 "DOM" 窗格。</span><span class="sxs-lookup"><span data-stu-id="17c11-115">To access this pane, click on the "DOM" pane next to the "Z-index" pane.</span></span>

![3D 视图的画布](./media/canvas.png)

## <span data-ttu-id="17c11-117">导航画布</span><span class="sxs-lookup"><span data-stu-id="17c11-117">Navigating the canvas</span></span>

### <span data-ttu-id="17c11-118">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="17c11-118">Keyboard shortcuts</span></span>
- <span data-ttu-id="17c11-119">旋转 DOM：使用向左和向右箭头键水平旋转，并使用向上和向下键垂直旋转。</span><span class="sxs-lookup"><span data-stu-id="17c11-119">Rotate the DOM: use the left and right arrow keys to rotate horizontally and use the up and down arrow keys to rotate vertically.</span></span>
- <span data-ttu-id="17c11-120">导航 DOM：如果已选定某个元素，则可以使用向上键和向下键在相邻元素之间移动</span><span class="sxs-lookup"><span data-stu-id="17c11-120">Navigate the DOM: if an element is selected, you can use the up and down arrow keys to move through the elements adjacent</span></span>

### <span data-ttu-id="17c11-121">鼠标控件</span><span class="sxs-lookup"><span data-stu-id="17c11-121">Mouse controls</span></span>
- <span data-ttu-id="17c11-122">旋转 DOM：在画布空间周围左键单击并拖动。</span><span class="sxs-lookup"><span data-stu-id="17c11-122">Rotate the DOM: left click and drag around the canvas space.</span></span>
- <span data-ttu-id="17c11-123">在 DOM 周围移动：右键单击并沿希望 DOM 移动的方向拖动。</span><span class="sxs-lookup"><span data-stu-id="17c11-123">Pan around the DOM: right click and drag in the direction you want the DOM to move.</span></span>
- <span data-ttu-id="17c11-124">缩放：在触摸板上拖动两根手指或使用鼠标上的滚轮。</span><span class="sxs-lookup"><span data-stu-id="17c11-124">Zoom: drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>

![屏幕上的控件](./media/controls-small.png)
### <span data-ttu-id="17c11-126">屏幕上的控件</span><span class="sxs-lookup"><span data-stu-id="17c11-126">On-screen controls</span></span>
- <span data-ttu-id="17c11-127">将画布视图重置为原始视图：单击标记为 "重置摄像头" 的按钮，或单击看上去像侧向 "刷新" 按钮的图标，并在 "重置视图和重新中心摄像头" 中显示 "重置元素"</span><span class="sxs-lookup"><span data-stu-id="17c11-127">Reset the canvas view to the original view: click the button labeled "Reset camera," or click on the icon that looks like a sideways refresh button and has "Reset elements in view and re-center camera"</span></span>
- <span data-ttu-id="17c11-128">刷新画布（例如，如果浏览器已更改或切换到设备仿真程序视图），请执行以下操作：单击显示 "重拍快照" 的按钮，或单击看起来像刷新图标的按钮，并将 "拍摄新快照" 作为悬停文本。</span><span class="sxs-lookup"><span data-stu-id="17c11-128">Refresh the canvas (e.g. if the browser changed or you switched to a device emulator view): click on the button that says "Retake snapshot," or click on the button that looks like a refresh icon and has "Take new snapshot" as the hover text.</span></span>

![Z-索引视图](./media/z-index-view-box.png)

## <span data-ttu-id="17c11-130">Z-索引</span><span class="sxs-lookup"><span data-stu-id="17c11-130">Z-index</span></span>

<span data-ttu-id="17c11-131">虽然 "Z-索引" 窗格具有与 "DOM" 窗格共享的功能，但它们仍具有特定于窗格的元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-131">While the Z-index pane has shared features with the DOM pane, they still have elements that are unique to the pane.</span></span>

### <span data-ttu-id="17c11-132">利用堆栈上下文突出显示元素</span><span class="sxs-lookup"><span data-stu-id="17c11-132">Highlight elements with stacking context</span></span>

<span data-ttu-id="17c11-133">此设置允许你为画布中的元素切换 "打开" 和 "关闭" 的 z 索引标记。</span><span class="sxs-lookup"><span data-stu-id="17c11-133">This setting allows you to toggle the z-index tags on and off for the elements in the canvas.</span></span> <span data-ttu-id="17c11-134">默认情况下，将选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="17c11-134">The checkbox will be selected by default.</span></span>

### <span data-ttu-id="17c11-135">更改您的勘探的范围</span><span class="sxs-lookup"><span data-stu-id="17c11-135">Change the scope of your exploration</span></span>

<span data-ttu-id="17c11-136">"**显示所有元素**" 按钮是在更改以下设置后显示所有 DOM 元素的最快方式。</span><span class="sxs-lookup"><span data-stu-id="17c11-136">The **Show all elements** button is the quickest way to display all the DOM's elements after changing the settings below.</span></span>

<span data-ttu-id="17c11-137">**仅显示具有堆栈上下文的元素**删除不带堆栈上下文的元素，并拼合 DOM 以便更轻松地进行导航。</span><span class="sxs-lookup"><span data-stu-id="17c11-137">**Show only elements with stacking context** removes elements without stacking context and flattens the DOM for easier navigation.</span></span>

<span data-ttu-id="17c11-138">**隔离选定的元素**筛选器实质上是一个中的三个按钮。</span><span class="sxs-lookup"><span data-stu-id="17c11-138">The **Isolate selected element** filter is essentially three buttons in one.</span></span> <span data-ttu-id="17c11-139">此按钮下面有两个复选框：一个是 "显示所有父级" 和 "仅保留具有新堆栈上下文的父级"。</span><span class="sxs-lookup"><span data-stu-id="17c11-139">There are two checkboxes below this button: one is "Show all parents" and "Keep only parents with new stacking context."</span></span> 

<span data-ttu-id="17c11-140">默认情况下，将选中 "显示所有父项" 复选框。</span><span class="sxs-lookup"><span data-stu-id="17c11-140">The "Show all parents" checkbox will be checked by default.</span></span> <span data-ttu-id="17c11-141">如果在 "画布" 窗格中选择一个元素，然后单击 "**隔离选定元素**"，则画布将仅显示该元素及其父元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-141">If you select an element in the canvas pane and click on **Isolate selected element**, the canvas will only display the element and its parents.</span></span>

<span data-ttu-id="17c11-142">如果选择 "仅保留新的堆栈上下文的父项"，然后单击 "**隔离选定元素**"，则画布将仅显示具有新堆栈上下文的元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-142">If you select the "Keep only parents with new stacking context," and click on **Isolate selected element**, the canvas will only display the element and the parents that have a new stacking context.</span></span>

<span data-ttu-id="17c11-143">如果取消选中两个复选框，然后单击 "**隔离选定元素**"，则画布将仅显示您在第一个位置中选择的元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-143">If you deselect both of the checkboxes and click on **Isolate selected element**, the canvas will only display the element you chose in the first place.</span></span>

<span data-ttu-id="17c11-144">在 "控件" 面板的最下方，**隐藏具有与父开关相同的绘制顺序的元素**。</span><span class="sxs-lookup"><span data-stu-id="17c11-144">At the very bottom of the controls panel, there is the **Hide elements with the same paint order as their parent** toggle.</span></span> <span data-ttu-id="17c11-145">选中并取消选中复选框将根据您的选择重新加载元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-145">Selecting and deselecting the checkbox will reload the elements based on your selection.</span></span> <span data-ttu-id="17c11-146">如果选中，共享绘制顺序的元素将拼合到父项。</span><span class="sxs-lookup"><span data-stu-id="17c11-146">If selected, elements that share paint order will be flattened to the parent.</span></span>

<span data-ttu-id="17c11-147">这些选项旨在清理在你的画布中创建更复杂的网页的一些混乱程度。</span><span class="sxs-lookup"><span data-stu-id="17c11-147">These options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>

### <span data-ttu-id="17c11-148">Z-索引颜色类型</span><span class="sxs-lookup"><span data-stu-id="17c11-148">Z-index color type</span></span>

<span data-ttu-id="17c11-149">以下是你的画布中的 DOM 可以使用的不同可视化效果。</span><span class="sxs-lookup"><span data-stu-id="17c11-149">These are the different visualizations you can use for the DOM in your canvas.</span></span> <span data-ttu-id="17c11-150">无论您是将其用于有趣的还是为了帮助您更好地可视化 DOM，我们都有三种不同的 colorways 和 "背景色" 设置。</span><span class="sxs-lookup"><span data-stu-id="17c11-150">Whether you use it for fun or because they help you visualize the DOM better, we have three different colorways as well as a "background color" setting.</span></span> <span data-ttu-id="17c11-151">单选按钮允许你切换选项，并选择最适合你的项目的颜色类型（或最喜欢的颜色类型）。</span><span class="sxs-lookup"><span data-stu-id="17c11-151">The radio buttons allow you to toggle through the options and pick the color type most appropriate for your project (or that you like the most).</span></span>

![DOM 视图](./media/dom-purple-box.png)

## <span data-ttu-id="17c11-153">3D DOM</span><span class="sxs-lookup"><span data-stu-id="17c11-153">3D DOM</span></span>

<span data-ttu-id="17c11-154">如果你想要使用更多常规调试视图，而不是 z 索引体验，则 3D DOM 将为 DOM 提供整体外观。</span><span class="sxs-lookup"><span data-stu-id="17c11-154">If you want to take more of a general debugging view, rather than the z-index experience, the 3D DOM gives an overall look of the DOM.</span></span> <span data-ttu-id="17c11-155">由于删除了 z 索引上下文，因此 DOM 更紧密地堆叠。</span><span class="sxs-lookup"><span data-stu-id="17c11-155">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span> <span data-ttu-id="17c11-156">此窗格具有类似的功能，但有一些细微差别。</span><span class="sxs-lookup"><span data-stu-id="17c11-156">This pane has similar functionality, but there are a few nuances.</span></span>

### <span data-ttu-id="17c11-157">更改视图</span><span class="sxs-lookup"><span data-stu-id="17c11-157">Changing your view</span></span>

<span data-ttu-id="17c11-158">在**3D DOM**窗格中，**隔离选定的元素**筛选器具有 "包含子级" 和 "包含父项"。</span><span class="sxs-lookup"><span data-stu-id="17c11-158">In the **3D DOM** pane, the **Isolate selected element** filter has "Include children" and "Include parents."</span></span> <span data-ttu-id="17c11-159">默认情况下，两个复选框均被选中，这意味着在画布中选择元素后单击 "**隔离选定的元素**" 按钮将显示所选元素、元素的父元素和元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-159">By default both checkboxes are selected, which means that clicking on the **Isolate selected element** button after selecting an element in the canvas would display the element chosen, the element's parents, and the element's children.</span></span> <span data-ttu-id="17c11-160">取消选择 "包含儿童" 复选框，然后再次单击 "**隔离选定元素**" 按钮将显示所选元素和元素的父元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-160">Deselecting the "Include children" checkbox and clicking the **Isolate selected element** button again would display the selected element and the element's parents.</span></span> <span data-ttu-id="17c11-161">如果选中 "包括儿童" 复选框，并取消选择 "包括父项" 复选框，然后单击 "包括父项" 复选框，则画布将显示该元素及其**子元素。**</span><span class="sxs-lookup"><span data-stu-id="17c11-161">If you select the "Include children" checkbox and deselect the "Include parents" checkbox before clicking on **Isolate selected element**, the canvas will then display the element and its children.</span></span> <span data-ttu-id="17c11-162">如果取消选中两个复选框，然后单击 "**隔离选定元素**"，则画布将仅显示您之前选择的元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-162">If you deselect both checkboxes and click on **Isolate selected element**, the canvas will only display the element you previously selected.</span></span>

<span data-ttu-id="17c11-163">你将注意到 "控件窗格" 中标题为 "**嵌套级别**" 的滑块，旁边有一个数字。</span><span class="sxs-lookup"><span data-stu-id="17c11-163">You'll notice a slider in the control pane titled **Nesting level** with a number next to it.</span></span> <span data-ttu-id="17c11-164">该数字表示文档中的图层数。</span><span class="sxs-lookup"><span data-stu-id="17c11-164">The number indicates the number of layers in the document.</span></span> <span data-ttu-id="17c11-165">将滑块向左拖动将导致最外层的图层 peel 消失，直到将嵌套级别1保留为1，仅显示 DOM 中最远的元素。</span><span class="sxs-lookup"><span data-stu-id="17c11-165">Dragging the slider to the left will cause the outermost layers to peel away until you are left with a nesting level of 1, displaying only the furthest back element in the DOM.</span></span> <span data-ttu-id="17c11-166">这允许你在尝试更仔细地查看较低级别中的内容时删除一些混乱效果。</span><span class="sxs-lookup"><span data-stu-id="17c11-166">This allows you to remove some of the clutter if you are trying to get a closer look at what is going on in the lower levels.</span></span>

### <span data-ttu-id="17c11-167">DOM 颜色类型</span><span class="sxs-lookup"><span data-stu-id="17c11-167">DOM color type</span></span>

<span data-ttu-id="17c11-168">你将注意除*紫色到白色*、*蓝色到黄色*、*彩虹*以及*使用背景色*选项之外，还有*使用屏幕纹理*。</span><span class="sxs-lookup"><span data-stu-id="17c11-168">You'll notice that, in addition to the *Purple to White*, *Blue to Yellow*, *Rainbow*, and *Use background color* options, there is *Use screen texture*.</span></span> <span data-ttu-id="17c11-169">屏幕纹理通过将网页中的内容直接显示在元素上来将上下文添加到调试体验。</span><span class="sxs-lookup"><span data-stu-id="17c11-169">The screen texture adds context to your debugging experience by displaying the content from the web page directly onto the elements.</span></span> <span data-ttu-id="17c11-170">这仍是一个正在进行的工作，因为某些网站在3D 视图中呈现其屏幕纹理时较难。</span><span class="sxs-lookup"><span data-stu-id="17c11-170">This is still a work in progress, as some websites have a harder time rendering their screen texture in the 3D View.</span></span> 

## <span data-ttu-id="17c11-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="17c11-171">Next steps</span></span>

<span data-ttu-id="17c11-172">我们正在处理 UI，并根据用户（如用户）向3D 视图添加更多功能。</span><span class="sxs-lookup"><span data-stu-id="17c11-172">We are working on the UI and adding more functionality to the 3D View based on asks from users like you.</span></span> <span data-ttu-id="17c11-173">请向我们发送您的反馈，以便我们可以继续为您改进 Microsoft Edge DevTools！</span><span class="sxs-lookup"><span data-stu-id="17c11-173">Please send us your feedback so we can continue improving the Microsoft Edge DevTools for you!</span></span> <span data-ttu-id="17c11-174">只需单击 DevTools 中的反馈图标或按 `Alt`  +  `Shift`  +  `I` Windows （ `Option`  +  `Shift`  +  `I` 在 Mac 上），然后输入 DevTools 的任何反馈或功能请求。</span><span class="sxs-lookup"><span data-stu-id="17c11-174">Simply click the feedback icon in the DevTools or press `Alt` + `Shift` + `I` on Windows (`Option` + `Shift` + `I` on Mac) and enter any feedback or feature requests you have for the DevTools.</span></span>