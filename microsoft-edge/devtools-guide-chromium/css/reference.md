---
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 4f0370b83d8c939476a1ed378dbdf750101c9527
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843964"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  







# <span data-ttu-id="c83ab-103">CSS 参考</span><span class="sxs-lookup"><span data-stu-id="c83ab-103">CSS Reference</span></span>   



<span data-ttu-id="c83ab-104">在此完整参考 Microsoft Edge DevTools 与查看和更改 CSS 相关的功能中发现新工作流。</span><span class="sxs-lookup"><span data-stu-id="c83ab-104">Discover new workflows in this comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="c83ab-105">请参阅[查看和更改 CSS 开始][DevToolsCSSGetStarted]了解基础知识。</span><span class="sxs-lookup"><span data-stu-id="c83ab-105">See [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted] to learn the basics.</span></span>  

## <span data-ttu-id="c83ab-106">选择一个元素</span><span class="sxs-lookup"><span data-stu-id="c83ab-106">Select an element</span></span>   

<span data-ttu-id="c83ab-107">DevTools 的 "**元素**" 面板使你可以一次查看或更改一个元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="c83ab-107">The **Elements** panel of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="c83ab-108">所选元素在**DOM 树**中突出显示。</span><span class="sxs-lookup"><span data-stu-id="c83ab-108">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="c83ab-109">元素的样式显示在 "**样式**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="c83ab-109">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="c83ab-110">请参阅查看教程的[元素的 CSS][DevToolsCSSGetStartedTutorial] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-110">See [View the CSS for an element][DevToolsCSSGetStartedTutorial] for a tutorial.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-111">在[图 1](#figure-1)中，在 `h1` **DOM 树**中突出显示的元素是所选元素。</span><span class="sxs-lookup"><span data-stu-id="c83ab-111">In [Figure 1](#figure-1), the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="c83ab-112">在右侧，元素的样式显示在 "**样式**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="c83ab-112">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="c83ab-113">在左侧，元素在视区中突出显示，但仅因为鼠标当前在**DOM 树**中悬停在其上方。</span><span class="sxs-lookup"><span data-stu-id="c83ab-113">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

> ##### <span data-ttu-id="c83ab-114">图 1</span><span class="sxs-lookup"><span data-stu-id="c83ab-114">Figure 1</span></span>  
> <span data-ttu-id="c83ab-115">所选元素的示例</span><span class="sxs-lookup"><span data-stu-id="c83ab-115">An example of a selected element</span></span>  
> ![所选元素的示例][ImageSelectedElement]  

<span data-ttu-id="c83ab-117">有多种方法可用于选择元素：</span><span class="sxs-lookup"><span data-stu-id="c83ab-117">There are many ways to select an element:</span></span>  

*   <span data-ttu-id="c83ab-118">在视区中，右键单击元素，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="c83ab-118">In your viewport, right-click the element and select **Inspect**.</span></span>  
*   <span data-ttu-id="c83ab-119">在 DevTools 中，单击 "**选择元素**"， ![ 选择一个元素 ][ImageSelectAnElementIcon] 或按 `Control` + `Shift` + `C` \ （Windows \）或 `Command` + `Shift` + `C` \ （macOS \），然后单击视区中的元素。</span><span class="sxs-lookup"><span data-stu-id="c83ab-119">In DevTools, click **Select an element** ![Select an element][ImageSelectAnElementIcon] or press `Control`+`Shift`+`C` \(Windows\) or `Command`+`Shift`+`C` \(macOS\), and then click the element in the viewport.</span></span>  
*   <span data-ttu-id="c83ab-120">在 DevTools 中，单击**DOM 树**中的元素。</span><span class="sxs-lookup"><span data-stu-id="c83ab-120">In DevTools, click the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="c83ab-121">在 DevTools 中，运行一个如 `document.querySelector('p')` 在**控制台**中的查询，右键单击结果，然后选择 **"在元素中显示" 面板**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, right-click the result, and then select **Reveal in Elements panel**.</span></span>  

## <span data-ttu-id="c83ab-122">查看 CSS</span><span class="sxs-lookup"><span data-stu-id="c83ab-122">View CSS</span></span>   

### <span data-ttu-id="c83ab-123">查看定义规则的外部样式表</span><span class="sxs-lookup"><span data-stu-id="c83ab-123">View the external stylesheet where a rule is defined</span></span>   

<span data-ttu-id="c83ab-124">在 "**样式**" 窗格中，单击 CSS 规则旁边的链接以打开定义该规则的外部样式表。</span><span class="sxs-lookup"><span data-stu-id="c83ab-124">In the **Styles** pane, click the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  

<span data-ttu-id="c83ab-125">如果样式表是 minified，请参阅[使 minified 文件易于阅读][DevToolsJavascriptReferenceFormat]。</span><span class="sxs-lookup"><span data-stu-id="c83ab-125">If the stylesheet is minified, see [Make a minified file readable][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-126">在[图 2](#figure-2)中，单击 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` "转到" 第2行 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` ，其中 `.content h1:first-of-type` 定义了 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="c83ab-126">In [Figure 2](#figure-2), clicking `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` takes you to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

> ##### <span data-ttu-id="c83ab-127">图 2</span><span class="sxs-lookup"><span data-stu-id="c83ab-127">Figure 2</span></span>  
> <span data-ttu-id="c83ab-128">查看定义规则的样式表</span><span class="sxs-lookup"><span data-stu-id="c83ab-128">Viewing the stylesheet where a rule is defined</span></span>  
> ![查看定义规则的样式表][ImageViewRuleStylesheet]  

### <span data-ttu-id="c83ab-130">仅查看实际应用到元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="c83ab-130">View only the CSS that is actually applied to an element</span></span>   

<span data-ttu-id="c83ab-131">"**样式**" 选项卡显示适用于元素的所有规则，包括已重写的声明。</span><span class="sxs-lookup"><span data-stu-id="c83ab-131">The **Styles** tab shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="c83ab-132">当你对替代声明不感兴趣时，请使用 "**计算**" 选项卡仅查看实际应用于元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="c83ab-132">When you are not interested in overridden declarations, use the **Computed** tab to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="c83ab-133">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-133">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="c83ab-134">转到 "**元素**" 面板中的 "**计算**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c83ab-134">Go to the **Computed** tab in the **Elements** panel.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-135">在宽 DevTools 窗口中，**计算**的选项卡不存在。</span><span class="sxs-lookup"><span data-stu-id="c83ab-135">On a wide DevTools window, the **Computed** tab does not exist.</span></span>  <span data-ttu-id="c83ab-136">**计算**的选项卡的内容显示在 "**样式**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="c83ab-136">The contents of the **Computed** tab are shown on the **Styles** tab.</span></span>  

<span data-ttu-id="c83ab-137">继承的属性是不透明的。</span><span class="sxs-lookup"><span data-stu-id="c83ab-137">Inherited properties are opaque.</span></span>  <span data-ttu-id="c83ab-138">选中 "**全部显示**" 复选框以查看所有继承值。</span><span class="sxs-lookup"><span data-stu-id="c83ab-138">Check the **Show All** checkbox to see all inherited values.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-139">在[图 3](#figure-3)中，"**计算**" 选项卡显示了应用于当前所选元素的 CSS 属性 `h1` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-139">In [Figure 3](#figure-3), the **Computed** tab shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

> ##### <span data-ttu-id="c83ab-140">图 3</span><span class="sxs-lookup"><span data-stu-id="c83ab-140">Figure 3</span></span>  
> <span data-ttu-id="c83ab-141">**计算**选项卡</span><span class="sxs-lookup"><span data-stu-id="c83ab-141">The **Computed** tab</span></span>  
> ![计算选项卡][ImageComputedTab]  

### <span data-ttu-id="c83ab-143">按字母顺序查看 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="c83ab-143">View CSS properties in alphabetical order</span></span>   

<span data-ttu-id="c83ab-144">使用 "**计算**" 选项卡。 请参阅[仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-144">Use the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="c83ab-145">查看继承的 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="c83ab-145">View inherited CSS properties</span></span>   

<span data-ttu-id="c83ab-146">选中 "**计算**" 选项卡中的 "**全部显示**" 复选框。 请参阅[仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-146">Check the **Show All** checkbox in the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="c83ab-147">查看元素的 box 模型</span><span class="sxs-lookup"><span data-stu-id="c83ab-147">View the box model for an element</span></span>   

<span data-ttu-id="c83ab-148">若要查看元素[的方框模型][MDNBoxModel]，请转到 "**样式**" 选项卡。 如果 DevTools 窗口较窄，则**框模型**图位于选项卡的底部。</span><span class="sxs-lookup"><span data-stu-id="c83ab-148">To view [the box model][MDNBoxModel] of an element, go to the **Styles** tab.  If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the tab.</span></span>  

<span data-ttu-id="c83ab-149">若要更改值，请双击它。</span><span class="sxs-lookup"><span data-stu-id="c83ab-149">To change a value, double-click on it.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-150">在[图 4](#figure-4)中，"**样式**" 选项卡中的**方框模型**图显示了当前所选元素的框模型 `h1` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-150">In [Figure 4](#figure-4), the **Box Model** diagram in the **Styles** tab shows the box model for the currently selected `h1` element.</span></span>  

> ##### <span data-ttu-id="c83ab-151">图 4</span><span class="sxs-lookup"><span data-stu-id="c83ab-151">Figure 4</span></span>  
> <span data-ttu-id="c83ab-152">**方框模型**图</span><span class="sxs-lookup"><span data-stu-id="c83ab-152">The **Box Model** diagram</span></span>  
> ![方框模型图][ImageBoxModel]  

### <span data-ttu-id="c83ab-154">搜索和筛选元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="c83ab-154">Search and filter the CSS of an element</span></span>   

<span data-ttu-id="c83ab-155">使用 "**样式**" 和 "**计算**" 选项卡上的 "**筛选器**" 文本框搜索特定的 CSS 属性或值。</span><span class="sxs-lookup"><span data-stu-id="c83ab-155">Use the **Filter** text box on the **Styles** and **Computed** tabs to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="c83ab-156">若要同时在 "**计算**" 选项卡中搜索继承的属性，请选中 "**全部显示**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c83ab-156">To also search inherited properties in the **Computed** tab, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-157">在[图 5](#figure-5)中，筛选 "**样式**" 选项卡以仅显示包含搜索查询的规则 `color` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-157">In [Figure 5](#figure-5), the **Styles** tab is filtered to only show rules that include the search query `color`.</span></span>  

> ##### <span data-ttu-id="c83ab-158">图 5</span><span class="sxs-lookup"><span data-stu-id="c83ab-158">Figure 5</span></span>  
> <span data-ttu-id="c83ab-159">筛选 "**样式**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="c83ab-159">Filtering the **Styles** tab</span></span>  
> ![筛选 "样式" 选项卡][ImageStylesFilter]  

> [!NOTE]
> <span data-ttu-id="c83ab-161">在[图 6](#figure-6)中，"**计算**" 选项卡已筛选为仅显示包含 "搜索" 查询的声明 `100%` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-161">In [Figure 6](#figure-6), the **Computed** tab is filtered to only show declarations that include the search query `100%`.</span></span>  

> ##### <span data-ttu-id="c83ab-162">图 6</span><span class="sxs-lookup"><span data-stu-id="c83ab-162">Figure 6</span></span>  
> <span data-ttu-id="c83ab-163">筛选**计算**的选项卡</span><span class="sxs-lookup"><span data-stu-id="c83ab-163">Filtering the **Computed** tab</span></span>  
> ![筛选计算的选项卡][ImageComputerFilter]  

### <span data-ttu-id="c83ab-165">切换伪类</span><span class="sxs-lookup"><span data-stu-id="c83ab-165">Toggle a pseudo-class</span></span>   

<span data-ttu-id="c83ab-166">若要切换伪类（如、、 `:active` 或），请 `:focus` `:hover` `:visited` 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-166">To toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`:</span></span>  

1.  <span data-ttu-id="c83ab-167">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-167">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="c83ab-168">在 "**元素**" 面板上，转到 "**样式**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c83ab-168">On the **Elements** panel, go to the **Styles** tab.</span></span>  
1.  <span data-ttu-id="c83ab-169">单击 **： hov**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-169">Click **:hov**.</span></span>  
1.  <span data-ttu-id="c83ab-170">检查要启用的伪类。</span><span class="sxs-lookup"><span data-stu-id="c83ab-170">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-171">在[图 7](#figure-7)中，切换 `:hover` 伪类。</span><span class="sxs-lookup"><span data-stu-id="c83ab-171">In [Figure 7](#figure-7), toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="c83ab-172">在视区中，验证 `background-color: cornflowerblue` 是否将声明应用于该元素，即使该元素实际上不是悬停在该元素上。</span><span class="sxs-lookup"><span data-stu-id="c83ab-172">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

> ##### <span data-ttu-id="c83ab-173">图 7</span><span class="sxs-lookup"><span data-stu-id="c83ab-173">Figure 7</span></span>  
> <span data-ttu-id="c83ab-174">切换 `:hover` 伪类</span><span class="sxs-lookup"><span data-stu-id="c83ab-174">Toggling the `:hover` pseudo-class</span></span>  
> ![切换：悬停伪类][ImagePseudoClass]  

<span data-ttu-id="c83ab-176">有关交互式教程，请参阅[向类添加伪][DevToolsCSSGetStartedAddPseudoState]状态。</span><span class="sxs-lookup"><span data-stu-id="c83ab-176">See [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState] for an interactive tutorial.</span></span> 

### <span data-ttu-id="c83ab-177">在打印模式下查看页面</span><span class="sxs-lookup"><span data-stu-id="c83ab-177">View a page in print mode</span></span>   

<span data-ttu-id="c83ab-178">若要以打印模式查看页面，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-178">To view a page in print mode:</span></span>  
1.  <span data-ttu-id="c83ab-179">[打开 "命令" 菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="c83ab-179">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="c83ab-180">开始键入 `Rendering` 并选择 `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-180">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="c83ab-181">对于 "**模拟 CSS 媒体**" 下拉列表，选择 "**打印**"。</span><span class="sxs-lookup"><span data-stu-id="c83ab-181">For the **Emulate CSS Media** dropdown, select **print**.</span></span>  

### <span data-ttu-id="c83ab-182">使用 "覆盖范围" 选项卡查看使用和未使用的 CSS</span><span class="sxs-lookup"><span data-stu-id="c83ab-182">View used and unused CSS with the Coverage tab</span></span>   

<span data-ttu-id="c83ab-183">"覆盖范围" 选项卡显示页面实际使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="c83ab-183">The Coverage tab shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="c83ab-184">`Control` + `Shift` + `P` 当 DevTools 处于焦点时，按 \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="c83ab-184">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to open the Command Menu.</span></span>  
1.  <span data-ttu-id="c83ab-185">开始键入 `coverage` ，然后选择 "**显示覆盖率**"。</span><span class="sxs-lookup"><span data-stu-id="c83ab-185">Start typing `coverage` and select **Show Coverage**.</span></span>  <span data-ttu-id="c83ab-186">将显示 "覆盖范围" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c83ab-186">The Coverage tab appears.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-187">图 8</span><span class="sxs-lookup"><span data-stu-id="c83ab-187">Figure 8</span></span>  
    > <span data-ttu-id="c83ab-188">从 "命令" 菜单打开 "覆盖范围" 选项卡</span><span class="sxs-lookup"><span data-stu-id="c83ab-188">Opening the Coverage tab from the Command Menu</span></span>  
    > ![从 "命令" 菜单打开 "覆盖范围" 选项卡][ImageCommandMenu]  
    
    > ##### <span data-ttu-id="c83ab-190">图 9</span><span class="sxs-lookup"><span data-stu-id="c83ab-190">Figure 9</span></span>  
    > <span data-ttu-id="c83ab-191">"覆盖范围" 选项卡</span><span class="sxs-lookup"><span data-stu-id="c83ab-191">The Coverage tab</span></span>  
    > !["覆盖范围" 选项卡][ImageCoverageEmpty]  
    
1.  <span data-ttu-id="c83ab-193">单击 "**开始检测覆盖率" 并刷新页面 "** ![ 开始检测覆盖率" 并刷新页面 ][ImageRefreshIcon] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-193">Click **Start instrumenting coverage and refresh the page** ![Start instrumenting coverage and refresh the page][ImageRefreshIcon].</span></span>  <span data-ttu-id="c83ab-194">页面刷新和 "覆盖率" 选项卡提供浏览器加载的每个文件中使用的 CSS \ （和 JavaScript \）的概述。</span><span class="sxs-lookup"><span data-stu-id="c83ab-194">The page refreshes and the Coverage tab provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="c83ab-195">绿色表示使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="c83ab-195">Green represents used CSS.</span></span>  <span data-ttu-id="c83ab-196">红色表示未使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="c83ab-196">Red represents unused CSS.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-197">图 10</span><span class="sxs-lookup"><span data-stu-id="c83ab-197">Figure 10</span></span>  
    > <span data-ttu-id="c83ab-198">有关使用和未使用的 CSS （和 JavaScript）数量的概述</span><span class="sxs-lookup"><span data-stu-id="c83ab-198">An overview of how much CSS (and JavaScript) is used and unused</span></span>  
    > ![有关使用和未使用的 CSS （和 JavaScript）数量的概述][ImageCoverageOverview]  

1.  <span data-ttu-id="c83ab-200">单击一个 CSS 文件以查看逐行分解它所使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="c83ab-200">Click a CSS file to see a line-by-line breakdown of what CSS it uses.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c83ab-201">在[图 11](#figure-11)中，145到147和149到 151 `b66bc881.site-ltr.css` 未使用，而使用行163到166。</span><span class="sxs-lookup"><span data-stu-id="c83ab-201">In [Figure 11](#figure-11), lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-202">图 11</span><span class="sxs-lookup"><span data-stu-id="c83ab-202">Figure 11</span></span>  
    > <span data-ttu-id="c83ab-203">已使用和未使用的 CSS 的逐行划分</span><span class="sxs-lookup"><span data-stu-id="c83ab-203">A line-by-line breakdown of used and unused CSS</span></span>  
    > ![已使用和未使用的 CSS 的逐行划分][ImageCoverageDetail]  
    
### <span data-ttu-id="c83ab-205">强制打印预览模式</span><span class="sxs-lookup"><span data-stu-id="c83ab-205">Force print preview mode</span></span>   

<span data-ttu-id="c83ab-206">请参阅[强制 DevTools 进入打印预览模式][DevToolsCssPrintPreview]。</span><span class="sxs-lookup"><span data-stu-id="c83ab-206">See [Force DevTools Into Print Preview Mode][DevToolsCssPrintPreview].</span></span>  

## <span data-ttu-id="c83ab-207">更改 CSS</span><span class="sxs-lookup"><span data-stu-id="c83ab-207">Change CSS</span></span>   

<!-- todo s/CSS declaration/declaration/ -->  

### <span data-ttu-id="c83ab-208">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-208">Add a CSS declaration to an element</span></span>   

<span data-ttu-id="c83ab-209">由于声明的顺序影响元素的样式，因此你可以采用不同的方式添加声明：</span><span class="sxs-lookup"><span data-stu-id="c83ab-209">Since the order of declarations affects how an element is styled, you may add declarations in different ways:</span></span>  

*   <span data-ttu-id="c83ab-210">[添加内联声明](#add-an-inline-declaration)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-210">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="c83ab-211">等效于将 `style` 属性添加到元素的 HTML。</span><span class="sxs-lookup"><span data-stu-id="c83ab-211">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="c83ab-212">[将声明添加到样式规则](#add-a-declaration-to-a-style-rule)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-212">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="c83ab-213">应该使用哪个工作流？</span><span class="sxs-lookup"><span data-stu-id="c83ab-213">What workflow should you use?</span></span>** <span data-ttu-id="c83ab-214">在大多数情况下，你可能希望使用内联声明工作流。</span><span class="sxs-lookup"><span data-stu-id="c83ab-214">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="c83ab-215">内联声明具有比外部声明更高的形式，因此内联工作流可确保所做的更改在元素中按预期效果生效。</span><span class="sxs-lookup"><span data-stu-id="c83ab-215">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in the element as you would expect.</span></span>  <span data-ttu-id="c83ab-216">有关详细信息，请参阅[选择器类型][MDNSelectorTypes]。</span><span class="sxs-lookup"><span data-stu-id="c83ab-216">See [Selector Types][MDNSelectorTypes] for more on specificity.</span></span>  

<span data-ttu-id="c83ab-217">如果你正在调试元素的任何样式，并且你需要专门测试在不同位置定义声明时所发生的情况，请使用其他工作流。</span><span class="sxs-lookup"><span data-stu-id="c83ab-217">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <span data-ttu-id="c83ab-218">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-218">Add an inline declaration</span></span>   

<span data-ttu-id="c83ab-219">要添加内联声明，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-219">To add an inline declaration:</span></span>  

1.  <span data-ttu-id="c83ab-220">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-220">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="c83ab-221">在 "**样式**" 窗格中，在元素的方括号之间单击 **。 "样式**" 部分。</span><span class="sxs-lookup"><span data-stu-id="c83ab-221">In the **Styles** pane, click between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="c83ab-222">光标焦点，允许您输入文本。</span><span class="sxs-lookup"><span data-stu-id="c83ab-222">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="c83ab-223">输入属性名称，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-223">Enter a property name and press `Enter`.</span></span>  
1.  <span data-ttu-id="c83ab-224">输入该属性的有效值，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-224">Enter a valid value for that property and press `Enter`.</span></span>  <span data-ttu-id="c83ab-225">在**DOM 树**中，验证是否已将某个 `style` 属性添加到该元素。</span><span class="sxs-lookup"><span data-stu-id="c83ab-225">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-226">在[图 12](#figure-12)中，"" `margin-top` 和 "属性" `background-color` 已应用于所选元素。</span><span class="sxs-lookup"><span data-stu-id="c83ab-226">In [Figure 12](#figure-12), the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="c83ab-227">在**DOM 树**中，验证声明是否反映在元素的 `style` 属性中。</span><span class="sxs-lookup"><span data-stu-id="c83ab-227">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

> ##### <span data-ttu-id="c83ab-228">图 12</span><span class="sxs-lookup"><span data-stu-id="c83ab-228">Figure 12</span></span>  
> <span data-ttu-id="c83ab-229">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-229">Adding inline declarations</span></span>  
> ![添加内联声明][ImageInlineDeclarations]  

#### <span data-ttu-id="c83ab-231">将声明添加到样式规则</span><span class="sxs-lookup"><span data-stu-id="c83ab-231">Add a declaration to a style rule</span></span>   

<span data-ttu-id="c83ab-232">将声明添加到现有样式规则：</span><span class="sxs-lookup"><span data-stu-id="c83ab-232">To add a declaration to an existing style rule:</span></span>  

1.  <span data-ttu-id="c83ab-233">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-233">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="c83ab-234">在 "**样式**" 窗格中，单击要向其中添加声明的样式规则的方括号。</span><span class="sxs-lookup"><span data-stu-id="c83ab-234">In the **Styles** pane, click between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="c83ab-235">光标焦点，允许您输入文本。</span><span class="sxs-lookup"><span data-stu-id="c83ab-235">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="c83ab-236">输入属性名称，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-236">Enter a property name and press `Enter`.</span></span>  
1.  <span data-ttu-id="c83ab-237">输入该属性的有效值，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-237">Enter a valid value for that property and press `Enter`.</span></span>  

> ##### <span data-ttu-id="c83ab-238">图 13</span><span class="sxs-lookup"><span data-stu-id="c83ab-238">Figure 13</span></span>  
> <span data-ttu-id="c83ab-239">将 `border-bottom-style:groove` 声明添加到样式规则</span><span class="sxs-lookup"><span data-stu-id="c83ab-239">Adding the `border-bottom-style:groove` declaration to a style rule</span></span>  
> ![将声明添加到样式规则][ImageAddDeclarationExistingRule]  

### <span data-ttu-id="c83ab-241">更改声明名称或值</span><span class="sxs-lookup"><span data-stu-id="c83ab-241">Change a declaration name or value</span></span>   

<span data-ttu-id="c83ab-242">双击声明的名称或值以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="c83ab-242">Double-click the name or value of a declaration to change it.</span></span>  <span data-ttu-id="c83ab-243">请参阅使用快捷键的[键盘快捷方式更改声明值](#change-declaration-values-with-keyboard-shortcuts)，快速将值按 `0.1` 、、 `1` `10` 或单位递减或递减 `100` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-243">See [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts) for shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units.</span></span>  

> ##### <span data-ttu-id="c83ab-244">图 14</span><span class="sxs-lookup"><span data-stu-id="c83ab-244">Figure 14</span></span>  
> <span data-ttu-id="c83ab-245">更改的值</span><span class="sxs-lookup"><span data-stu-id="c83ab-245">Changing the value of the</span></span> `border-bottom-style`  
> ![更改声明的值][ImageAddDeclarationExistingRule2]  

### <span data-ttu-id="c83ab-247">通过键盘快捷方式更改声明值</span><span class="sxs-lookup"><span data-stu-id="c83ab-247">Change declaration values with keyboard shortcuts</span></span>   

<span data-ttu-id="c83ab-248">编辑声明的值时，可以使用以下键盘快捷方式按固定量增加值：</span><span class="sxs-lookup"><span data-stu-id="c83ab-248">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a fixed amount:</span></span>  

*   <span data-ttu-id="c83ab-249">按 `Alt` + `Up` \ （Windows \）或 `Option` + `Up` \ （macOS \）递增 `0.1` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-249">Press `Alt`+`Up` \(Windows\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="c83ab-250">按下 `Up` 以更改值 `1` ，或者 `0.1` 如果当前值介于和之间，则 `-1` 按 `1` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-250">Press `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="c83ab-251">按 " `Shift` + `Up` 增加方式" `10` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-251">Press `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="c83ab-252">按 `Shift` + `Page Up` \ （Windows \）或 `Shift` + `Command` + `Up` \ （macOS \）将值增加 `100` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-252">Press `Shift`+`Page Up` \(Windows\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="c83ab-253">减量也有效。</span><span class="sxs-lookup"><span data-stu-id="c83ab-253">Decrementing also works.</span></span>  <span data-ttu-id="c83ab-254">只需将上面提及的每个实例替换 `Up` 为 `Down` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-254">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <span data-ttu-id="c83ab-255">向元素添加类</span><span class="sxs-lookup"><span data-stu-id="c83ab-255">Add a class to an element</span></span>   

<span data-ttu-id="c83ab-256">要向元素添加类，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-256">To add a class to an element:</span></span>  

1.  <span data-ttu-id="c83ab-257">在**DOM 树**中[选择该元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-257">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="c83ab-258">单击 " **. cls**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-258">Click **.cls**.</span></span>  
1.  <span data-ttu-id="c83ab-259">在 "**添加新类**" 文本框中输入类的名称。</span><span class="sxs-lookup"><span data-stu-id="c83ab-259">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="c83ab-260">按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-260">Press `Enter`.</span></span>  

> ##### <span data-ttu-id="c83ab-261">图 15</span><span class="sxs-lookup"><span data-stu-id="c83ab-261">Figure 15</span></span>  
> <span data-ttu-id="c83ab-262">"**元素类**" 窗格</span><span class="sxs-lookup"><span data-stu-id="c83ab-262">The **Element Classes** pane</span></span>  
> !["元素类" 窗格][ImageElementClasses]  

### <span data-ttu-id="c83ab-264">切换类</span><span class="sxs-lookup"><span data-stu-id="c83ab-264">Toggle a class</span></span>   

<span data-ttu-id="c83ab-265">启用或禁用元素上的类：</span><span class="sxs-lookup"><span data-stu-id="c83ab-265">To enable or disable a class on an element:</span></span>  

1.  <span data-ttu-id="c83ab-266">在**DOM 树**中[选择该元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-266">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="c83ab-267">打开 "**元素类**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="c83ab-267">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="c83ab-268">请参阅[向元素添加类](#add-a-class-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-268">See [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="c83ab-269">在 "**添加新类**" 文本框下方是应用于此元素的所有类。</span><span class="sxs-lookup"><span data-stu-id="c83ab-269">Below the **Add New Class** text box are all of the classes that are being applied to this element.</span></span>  
1.  <span data-ttu-id="c83ab-270">切换要启用或禁用的类旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="c83ab-270">Toggle the checkbox next to the class that you want to enable or disable.</span></span>  

### <span data-ttu-id="c83ab-271">添加样式规则</span><span class="sxs-lookup"><span data-stu-id="c83ab-271">Add a style rule</span></span>   

<span data-ttu-id="c83ab-272">要添加新的样式规则，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-272">To add a new style rule:</span></span>  

1.  <span data-ttu-id="c83ab-273">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-273">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="c83ab-274">单击 "**新建样式规则**" ![ 新样式规则 ][ImageNewStyleRuleIcon] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-274">Click **New Style Rule** ![New Style Rule][ImageNewStyleRuleIcon].</span></span>  <span data-ttu-id="c83ab-275">DevTools 在元素下方插入新规则 **。 style**规则。</span><span class="sxs-lookup"><span data-stu-id="c83ab-275">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-276">在[图 16](#figure-16)中，DevTools 在 `h1.devsite-page-title` 单击 "**新建样式规则**" 后添加样式规则。</span><span class="sxs-lookup"><span data-stu-id="c83ab-276">In [Figure 16](#figure-16), DevTools adds the `h1.devsite-page-title` style rule after clicking **New Style Rule**.</span></span>  

> ##### <span data-ttu-id="c83ab-277">图 16</span><span class="sxs-lookup"><span data-stu-id="c83ab-277">Figure 16</span></span>  
> <span data-ttu-id="c83ab-278">添加新样式规则</span><span class="sxs-lookup"><span data-stu-id="c83ab-278">Adding a new style rule</span></span>  
> ![添加新样式规则][ImageStyleRule]  

#### <span data-ttu-id="c83ab-280">选择要向其添加规则的样式表</span><span class="sxs-lookup"><span data-stu-id="c83ab-280">Choose which stylesheet to add a rule to</span></span>   

<span data-ttu-id="c83ab-281">[添加新样式规则](#add-a-style-rule)时，单击并按住**新的样式规则** ![ 新样式规则， ][ImageNewStyleRuleIcon] 选择要向其添加样式规则的样式表。</span><span class="sxs-lookup"><span data-stu-id="c83ab-281">When [adding a new style rule](#add-a-style-rule), click and hold **New Style Rule** ![New Style Rule][ImageNewStyleRuleIcon] to choose which stylesheet to add the style rule to.</span></span>  

> ##### <span data-ttu-id="c83ab-282">图 17</span><span class="sxs-lookup"><span data-stu-id="c83ab-282">Figure 17</span></span>  
> <span data-ttu-id="c83ab-283">选择样式表</span><span class="sxs-lookup"><span data-stu-id="c83ab-283">Choosing a stylesheet</span></span>  
> ![选择样式表][ImageChooseStylesheet]  

#### <span data-ttu-id="c83ab-285">将样式规则添加到特定位置</span><span class="sxs-lookup"><span data-stu-id="c83ab-285">Add a style rule to a specific location</span></span>   

<span data-ttu-id="c83ab-286">若要将样式规则添加到 "**样式**" 选项卡中的特定位置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-286">To add a style rule to a specific location in the **Styles** tab:</span></span>  

1.  <span data-ttu-id="c83ab-287">将鼠标悬停在要添加新样式规则的正上方的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="c83ab-287">Hover over the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="c83ab-288">[显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-288">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="c83ab-289">单击下方的 "插入**样式规则**" 下方 ![ 的 "插入样式规则" ][ImageNewStyleRuleIcon] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-289">Click **Insert Style Rule Below** ![Insert Style Rule Below][ImageNewStyleRuleIcon].</span></span>  

> ##### <span data-ttu-id="c83ab-290">图18</span><span class="sxs-lookup"><span data-stu-id="c83ab-290">Figure 18</span></span>  
> **<span data-ttu-id="c83ab-291">在下方插入样式规则</span><span class="sxs-lookup"><span data-stu-id="c83ab-291">Insert Style Rule Below</span></span>**  
> ![在下方插入样式规则][ImageInsertStyleRuleBelow]  

### <span data-ttu-id="c83ab-293">显示 "更多操作" 工具栏</span><span class="sxs-lookup"><span data-stu-id="c83ab-293">Reveal the More Actions toolbar</span></span>   

<span data-ttu-id="c83ab-294">"**更多操作**" 工具栏使您能够：</span><span class="sxs-lookup"><span data-stu-id="c83ab-294">The **More Actions** toolbar lets you:</span></span>  

*   <span data-ttu-id="c83ab-295">直接在你的重点所在的下插入样式规则。</span><span class="sxs-lookup"><span data-stu-id="c83ab-295">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="c83ab-296">向 `background-color` `color` `box-shadow` 你关注的样式规则添加、、或 `text-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="c83ab-296">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="c83ab-297">要显示 "**更多操作**" 工具栏，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-297">To reveal the **More Actions** toolbar:</span></span>  

1.  <span data-ttu-id="c83ab-298">在 "**样式**" 选项卡中，将鼠标悬停在样式规则上。</span><span class="sxs-lookup"><span data-stu-id="c83ab-298">In the **Styles** tab, hover over a style rule.</span></span>  <span data-ttu-id="c83ab-299">**更多操作** `...`显示在样式规则部分的右下角。</span><span class="sxs-lookup"><span data-stu-id="c83ab-299">**More Actions** `...` is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c83ab-300">在[图 19](#figure-19)中，将鼠标悬停在样式规则上，并显示 " `.header-holder.has-default-focus` 样式规则" 部分右下角的 "**更多操作**"。</span><span class="sxs-lookup"><span data-stu-id="c83ab-300">In [Figure 19](#figure-19), hover over the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-301">图19</span><span class="sxs-lookup"><span data-stu-id="c83ab-301">Figure 19</span></span>  
    > <span data-ttu-id="c83ab-302">泄漏**更多操作**</span><span class="sxs-lookup"><span data-stu-id="c83ab-302">Revealing **More Actions**</span></span>  
    > ![泄漏更多操作][ImageRevealMore]  
    
1.  <span data-ttu-id="c83ab-304">将鼠标悬停在**更多操作**上 `...` 以显示上述操作。</span><span class="sxs-lookup"><span data-stu-id="c83ab-304">Hover over **More Actions** `...` to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c83ab-305">将鼠标悬停在**更多操作**之后，将显示 "**下方的插入样式规则**" 操作。</span><span class="sxs-lookup"><span data-stu-id="c83ab-305">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-306">图20</span><span class="sxs-lookup"><span data-stu-id="c83ab-306">Figure 20</span></span>  
    > <span data-ttu-id="c83ab-307">"**更多操作**" 工具栏</span><span class="sxs-lookup"><span data-stu-id="c83ab-307">The **More Actions** toolbar</span></span>  
    > !["更多操作" 工具栏][ImageInsertStyleRuleBelow2]  
    
### <span data-ttu-id="c83ab-309">切换声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-309">Toggle a declaration</span></span>   

<span data-ttu-id="c83ab-310">若要打开或关闭单个声明，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-310">To toggle a single declaration on or off:</span></span>  

1.  <span data-ttu-id="c83ab-311">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-311">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="c83ab-312">在 "**样式**" 窗格中，将鼠标悬停在定义声明的规则上方。</span><span class="sxs-lookup"><span data-stu-id="c83ab-312">In the **Styles** pane, hover over the rule that defines the declaration.</span></span>  <span data-ttu-id="c83ab-313">复选框显示在每个声明的旁边。</span><span class="sxs-lookup"><span data-stu-id="c83ab-313">Checkboxes appear next to each declaration.</span></span>  
1.  <span data-ttu-id="c83ab-314">选中或取消选中声明旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="c83ab-314">Check or uncheck the checkbox next to the declaration.</span></span>  <span data-ttu-id="c83ab-315">取消选中某个声明后，DevTools 将其置于外，以指示它不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c83ab-315">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="c83ab-316">在[图 21](#figure-21)中， `margin-top` 当前所选元素的属性已关闭。</span><span class="sxs-lookup"><span data-stu-id="c83ab-316">In [Figure 21](#figure-21), the `margin-top` property for the currently selected element has been toggled off.</span></span>  

> ##### <span data-ttu-id="c83ab-317">图21</span><span class="sxs-lookup"><span data-stu-id="c83ab-317">Figure 21</span></span>  
> <span data-ttu-id="c83ab-318">切换声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-318">Toggling a declaration</span></span>  
> ![切换声明][ImageToggleDeclaration]  

### <span data-ttu-id="c83ab-320">添加背景色声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-320">Add a background-color declaration</span></span>   

<span data-ttu-id="c83ab-321">若要向 `background-color` 元素添加声明，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-321">To add a `background-color` declaration to an element:</span></span>  

1.  <span data-ttu-id="c83ab-322">将鼠标悬停在要向其添加声明的样式规则上 `background-color` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-322">Hover over the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="c83ab-323">[显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-323">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="c83ab-324">单击 "**添加背景色**" ![ 添加背景色 ][ImageAddBackgroundColorIcon] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-324">Click **Add Background Color** ![Add Background Color][ImageAddBackgroundColorIcon].</span></span>  

> ##### <span data-ttu-id="c83ab-325">图22</span><span class="sxs-lookup"><span data-stu-id="c83ab-325">Figure 22</span></span>  
> **<span data-ttu-id="c83ab-326">添加背景色</span><span class="sxs-lookup"><span data-stu-id="c83ab-326">Add Background Color</span></span>**  
> ![添加背景色][ImageAddBackgroundColor]  

### <span data-ttu-id="c83ab-328">添加颜色声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-328">Add a color declaration</span></span>   

<span data-ttu-id="c83ab-329">若要向 `color` 元素添加声明，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-329">To add a `color` declaration to an element:</span></span>  

1.  <span data-ttu-id="c83ab-330">将鼠标悬停在要向其添加声明的样式规则上 `color` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-330">Hover over the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="c83ab-331">[显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-331">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="c83ab-332">单击 "**添加颜色**" " ![ 添加颜色" ][ImageAddColorIcon] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-332">Click **Add Color** ![Add Color][ImageAddColorIcon].</span></span>  

> ##### <span data-ttu-id="c83ab-333">图23</span><span class="sxs-lookup"><span data-stu-id="c83ab-333">Figure 23</span></span>  
> **<span data-ttu-id="c83ab-334">添加颜色</span><span class="sxs-lookup"><span data-stu-id="c83ab-334">Add Color</span></span>**  
> ![添加颜色][ImageAddColor]  

### <span data-ttu-id="c83ab-336">添加 box-阴影声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-336">Add a box-shadow declaration</span></span>   

<span data-ttu-id="c83ab-337">若要向 `box-shadow` 元素添加声明，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-337">To add a `box-shadow` declaration to an element:</span></span>  

1.  <span data-ttu-id="c83ab-338">将鼠标悬停在要向其添加声明的样式规则上 `box-shadow` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-338">Hover over the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="c83ab-339">[显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-339">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="c83ab-340">单击 "**添加框阴影** ![ 添加框阴影" ][ImageAddBoxShadowIcon] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-340">Click **Add Box Shadow** ![Add Box Shadow][ImageAddBoxShadowIcon].</span></span>  

> ##### <span data-ttu-id="c83ab-341">图24</span><span class="sxs-lookup"><span data-stu-id="c83ab-341">Figure 24</span></span>  
> **<span data-ttu-id="c83ab-342">添加框阴影</span><span class="sxs-lookup"><span data-stu-id="c83ab-342">Add Box Shadow</span></span>**  
> ![添加框阴影][ImageAddBoxShadow]  

### <span data-ttu-id="c83ab-344">添加文本阴影声明</span><span class="sxs-lookup"><span data-stu-id="c83ab-344">Add a text-shadow declaration</span></span>   

<span data-ttu-id="c83ab-345">若要向 `text-shadow` 元素添加声明，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-345">To add a `text-shadow` declaration to an element:</span></span>  

1.  <span data-ttu-id="c83ab-346">将鼠标悬停在要向其添加声明的样式规则上 `text-shadow` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-346">Hover over the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="c83ab-347">[显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-347">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="c83ab-348">单击 "**添加文本阴影**" ![ 添加文本阴影 ][ImageAddTextShadowIcon] 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-348">Click **Add Text Shadow** ![Add Text Shadow][ImageAddTextShadowIcon].</span></span>  

> ##### <span data-ttu-id="c83ab-349">图25</span><span class="sxs-lookup"><span data-stu-id="c83ab-349">Figure 25</span></span>  
> **<span data-ttu-id="c83ab-350">添加文本阴影</span><span class="sxs-lookup"><span data-stu-id="c83ab-350">Add Text Shadow</span></span>**  
> ![添加文本阴影][ImageAddTextShadow]  

### <span data-ttu-id="c83ab-352">通过拾色器更改颜色</span><span class="sxs-lookup"><span data-stu-id="c83ab-352">Change colors with the Color Picker</span></span>   

<span data-ttu-id="c83ab-353">**颜色选取器**提供了用于更改 `color` 和声明的 GUI `background-color` 。</span><span class="sxs-lookup"><span data-stu-id="c83ab-353">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="c83ab-354">要打开**拾色器**，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-354">To open the **Color Picker**:</span></span>  

1.  <span data-ttu-id="c83ab-355">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-355">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="c83ab-356">在 "**样式**" 选项卡中，找到 `color` `background-color` 要更改的、或类似的声明。</span><span class="sxs-lookup"><span data-stu-id="c83ab-356">In the **Styles** tab, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="c83ab-357">在 " `color` 、" `background-color` 或 "类似" 值的左侧，有一个小方块，它是颜色的预览。</span><span class="sxs-lookup"><span data-stu-id="c83ab-357">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c83ab-358">在[图 26](#figure-26)中，左侧的小方块 `rgba(0, 0, 0, 0.7)` 是该颜色的预览。</span><span class="sxs-lookup"><span data-stu-id="c83ab-358">In [Figure 26](#figure-26), the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-359">图26</span><span class="sxs-lookup"><span data-stu-id="c83ab-359">Figure 26</span></span>  
    > <span data-ttu-id="c83ab-360">颜色预览</span><span class="sxs-lookup"><span data-stu-id="c83ab-360">Color preview</span></span>  
    > ![颜色预览][ImageColorPreview]  
    
1.  <span data-ttu-id="c83ab-362">单击预览以打开**颜色选取器**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-362">Click the preview to open the **Color Picker**.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-363">图27</span><span class="sxs-lookup"><span data-stu-id="c83ab-363">Figure 27</span></span>  
    > <span data-ttu-id="c83ab-364">**颜色选取器**</span><span class="sxs-lookup"><span data-stu-id="c83ab-364">The **Color Picker**</span></span>  
    > ![颜色选取器][ImageColorPicker]  
    
<span data-ttu-id="c83ab-366">下面是对**颜色选取器**的每个 UI 元素的说明：</span><span class="sxs-lookup"><span data-stu-id="c83ab-366">Here is a description of each of the UI elements of the **Color Picker**:</span></span>  

> ##### <span data-ttu-id="c83ab-367">图28</span><span class="sxs-lookup"><span data-stu-id="c83ab-367">Figure 28</span></span>  
> <span data-ttu-id="c83ab-368">颜色选取器，批注</span><span class="sxs-lookup"><span data-stu-id="c83ab-368">The Color Picker, annotated</span></span>  
> ![颜色选取器，批注][ImageColorPickerAnnotated]  

1.  <span data-ttu-id="c83ab-370">**底纹**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-370">**Shades**.</span></span>  
1.  <span data-ttu-id="c83ab-371">**吸管**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-371">**Eyedropper**.</span></span>  <span data-ttu-id="c83ab-372">请参阅[使用取色器在页面上示例颜色](#sample-a-color-off-the-page-with-the-eyedropper)。</span><span class="sxs-lookup"><span data-stu-id="c83ab-372">See [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
1.  <span data-ttu-id="c83ab-373">**复制到剪贴板**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-373">**Copy To Clipboard**.</span></span>  <span data-ttu-id="c83ab-374">将**显示值**复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="c83ab-374">Copy the **Display Value** to your clipboard.</span></span>  
1.  <span data-ttu-id="c83ab-375">**显示值**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-375">**Display Value**.</span></span>  <span data-ttu-id="c83ab-376">颜色的 RGBA、HSLA 或十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="c83ab-376">The RGBA, HSLA, or Hex representation of the color.</span></span>  
1.  <span data-ttu-id="c83ab-377">**调色板**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-377">**Color Palette**.</span></span>  <span data-ttu-id="c83ab-378">单击其中一个方框以更改该正方形的颜色。</span><span class="sxs-lookup"><span data-stu-id="c83ab-378">Click one of these squares to change the color to that square.</span></span>  
1.  <span data-ttu-id="c83ab-379">**色调**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-379">**Hue**.</span></span>  
1.  <span data-ttu-id="c83ab-380">**Opacity**。</span><span class="sxs-lookup"><span data-stu-id="c83ab-380">**Opacity**.</span></span>  
1.  <span data-ttu-id="c83ab-381">**显示值切换**器。</span><span class="sxs-lookup"><span data-stu-id="c83ab-381">**Display Value Switcher**.</span></span>  <span data-ttu-id="c83ab-382">在当前颜色的 RGBA、HSLA 和十六进制表示形式之间切换。</span><span class="sxs-lookup"><span data-stu-id="c83ab-382">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
1.  <span data-ttu-id="c83ab-383">**调色板切换**器。</span><span class="sxs-lookup"><span data-stu-id="c83ab-383">**Color Palette Switcher**.</span></span>  <span data-ttu-id="c83ab-384">在[材料设计调色板][MaterialDesignColorSystem]、自定义调色板或页面颜色调色板之间切换。</span><span class="sxs-lookup"><span data-stu-id="c83ab-384">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="c83ab-385">DevTools 基于在样式表中找到的颜色生成页面调色板。</span><span class="sxs-lookup"><span data-stu-id="c83ab-385">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  

#### <span data-ttu-id="c83ab-386">使用滴管对页面进行颜色取样</span><span class="sxs-lookup"><span data-stu-id="c83ab-386">Sample a color off the page with the Eyedropper</span></span>   

<span data-ttu-id="c83ab-387">打开 "**颜色选取器**" 时，默认情况下，"**滴管**" ![ 取色器 ][ImageEyedropperIcon] 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="c83ab-387">When you open the **Color Picker**, the **Eyedropper** ![Eyedropper][ImageEyedropperIcon] is on by default.</span></span>  <span data-ttu-id="c83ab-388">若要将所选颜色更改为页面上的其他颜色，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c83ab-388">To change the selected color to some other color on the page:</span></span>  

1.  <span data-ttu-id="c83ab-389">将鼠标悬停在视区中的目标颜色上。</span><span class="sxs-lookup"><span data-stu-id="c83ab-389">Hover over the target color in the viewport.</span></span>  
1.  <span data-ttu-id="c83ab-390">单击以确认。</span><span class="sxs-lookup"><span data-stu-id="c83ab-390">Click to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c83ab-391">在[图 29](#figure-29)中，**颜色选取器**显示当前颜色值 `rgba(0,0,0,0.7)` ，它接近黑色。</span><span class="sxs-lookup"><span data-stu-id="c83ab-391">In [Figure 29](#figure-29), the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="c83ab-392">单击黑色后，此颜色应更改为当前在视区中突出显示的黑色。</span><span class="sxs-lookup"><span data-stu-id="c83ab-392">This color should change to the black that is currently highlighted in the viewport once the black was clicked.</span></span>  
    
    > ##### <span data-ttu-id="c83ab-393">图29</span><span class="sxs-lookup"><span data-stu-id="c83ab-393">Figure 29</span></span>  
    > <span data-ttu-id="c83ab-394">使用取色器</span><span class="sxs-lookup"><span data-stu-id="c83ab-394">Using the Eyedropper</span></span>  
    > ![使用取色器][ImageUsingEyedropper]  
    
 



<!-- image links -->  

[ImageAddBackgroundColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: /microsoft-edge/devtools-guide-chromium/media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-an-element-icon.msft.png  

[ImageSelectedElement]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1.msft.png "图1：所选元素的示例"  
[ImageViewRuleStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-highlight.msft.png "图2：查看定义规则的样式表"  
[ImageComputedTab]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-h1.msft.png "图3：计算的选项卡"  
[ImageBoxModel]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-2.msft.png "图4：方框模型图"  
[ImageStylesFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-color.msft.png "图5：筛选 "样式" 选项卡"  
[ImageComputerFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-filter-100.msft.png "图6：筛选计算的选项卡"  
[ImagePseudoClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-hov-hover.msft.png "图7：切换：悬停伪类"  
[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-coverage.msft.png "图8：从 "命令" 菜单打开 "覆盖范围" 选项卡"  
[ImageCoverageEmpty]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-empty.msft.png "图9： "覆盖范围" 选项卡"  
[ImageCoverageOverview]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-run.msft.png "图10：使用和未使用过多少 CSS （和 JavaScript）的概述"  
[ImageCoverageDetail]: /microsoft-edge/devtools-guide-chromium/media/css-sources-css-coverage.msft.png "图11：已使用和未使用的 CSS 的逐行划分"  
[ImageInlineDeclarations]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-margin-top-background-color.msft.png "图12：添加内联声明"  
[ImageAddDeclarationExistingRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style.msft.png "图13：将声明添加到样式规则"  
[ImageAddDeclarationExistingRule2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style-dropdown.msft.png "图14：更改声明的值"  
[ImageElementClasses]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-classes.msft.png "图15： "元素类" 窗格"  
[ImageStyleRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new.msft.png "图16：添加新样式规则"  
[ImageChooseStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new-select-exisiting.msft.png "图17：选择样式表"  
[ImageInsertStyleRuleBelow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-insert-style-rule-below.msft.png "图18：在下方插入样式规则"  
[ImageRevealMore]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-new-rule-styles.msft.png "图19：泄漏更多操作"  
[ImageInsertStyleRuleBelow2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png "图20： "更多操作" 工具栏"  
[ImageToggleDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-deactivated.msft.png "图21：切换声明"  
[ImageAddBackgroundColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-background-color.msft.png "图22：添加背景色"  
[ImageAddColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-color.msft.png "图23：添加颜色"  
[ImageAddBoxShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-box-shadow.msft.png "图24：添加框阴影"  
[ImageAddTextShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-text-shadow.msft.png "图25：添加文本阴影"  
[ImageColorPreview]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-overlay-color-box.msft.png "图26：颜色预览"  
[ImageColorPicker]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker.msft.png "图27：颜色选取器"  
[ImageColorPickerAnnotated]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker-annotated.msft.png "图28：颜色选取器，已批注"  
[ImageUsingEyedropper]: /microsoft-edge/devtools-guide-chromium/media/css-color-picker-eye-dropper.msft.png "图29：使用取色器"  

<!-- links -->  

[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevToolsCSSGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门"  
[DevToolsCSSGetStartedAddPseudoState]: /microsoft-edge/devtools-guide-chromium/css/index#add-a-pseudostate-to-a-class "向课堂添加伪状态-查看和更改 CSS 入门"  
[DevToolsCSSGetStartedTutorial]: /microsoft-edge/devtools-guide-chromium/css/index#view-the-css-for-an-element "查看元素的 CSS-如何查看和更改 CSS 入门"  
[DevToolsCssPrintPreview]: /microsoft-edge/devtools-guide-chromium/css/print-preview "强制 Microsoft Edge DevTools 进入打印预览模式（CSS 打印媒体类型）"  
[DevToolsJavascriptReferenceFormat]: /microsoft-edge/devtools-guide-chromium/javascript/reference#make-a-minified-file-readable "使 minified 文件易于阅读-JavaScript 调试参考"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统-材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "方框模型 |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型-"自由" |MDN"  

> [!NOTE]
> <span data-ttu-id="c83ab-434">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="c83ab-434">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c83ab-435">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="c83ab-435">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="c83ab-437">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="c83ab-437">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
