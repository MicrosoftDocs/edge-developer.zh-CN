---
description: 了解在 Microsoft Edge DevTools 中查看和更改 CSS 的新工作流。
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: de0fb33e1e080045383f3c0fb50919297cbff5bc
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993070"
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

# <span data-ttu-id="24f0d-104">CSS 参考</span><span class="sxs-lookup"><span data-stu-id="24f0d-104">CSS reference</span></span>  

<span data-ttu-id="24f0d-105">在以下有关 Microsoft Edge DevTools 功能的完整参考中发现新工作流，这些功能与查看和更改 CSS 相关。</span><span class="sxs-lookup"><span data-stu-id="24f0d-105">Discover new workflows in the following comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="24f0d-106">请参阅 [查看和更改 CSS 开始][DevToolsCSSGetStarted] 了解基础知识。</span><span class="sxs-lookup"><span data-stu-id="24f0d-106">See [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted] to learn the basics.</span></span>  

## <span data-ttu-id="24f0d-107">选择一个元素</span><span class="sxs-lookup"><span data-stu-id="24f0d-107">Select an element</span></span>  

<span data-ttu-id="24f0d-108">DevTools 的 " **元素** " 面板使你可以一次查看或更改一个元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="24f0d-108">The **Elements** panel of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="24f0d-109">所选元素在 **DOM 树**中突出显示。</span><span class="sxs-lookup"><span data-stu-id="24f0d-109">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="24f0d-110">元素的样式显示在 " **样式** " 窗格中。</span><span class="sxs-lookup"><span data-stu-id="24f0d-110">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="24f0d-111">请参阅查看教程的 [元素的 CSS][DevToolsCSSGetStartedTutorial] 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-111">See [View the CSS for an element][DevToolsCSSGetStartedTutorial] for a tutorial.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-112">在下图中，在 `h1` **DOM 树** 中突出显示的元素是所选元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-112">In the following figure, the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="24f0d-113">在右侧，元素的样式显示在 " **样式** " 窗格中。</span><span class="sxs-lookup"><span data-stu-id="24f0d-113">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="24f0d-114">在左侧，元素在视区中突出显示，但仅因为鼠标当前在 **DOM 树**中悬停在其上方。</span><span class="sxs-lookup"><span data-stu-id="24f0d-114">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-h1.msft.png":::
   <span data-ttu-id="24f0d-116">所选元素的示例</span><span class="sxs-lookup"><span data-stu-id="24f0d-116">An example of a selected element</span></span>  
:::image-end:::  

<span data-ttu-id="24f0d-117">使用下列操作之一选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-117">Use one the following actions to select an element.</span></span>  

*   <span data-ttu-id="24f0d-118">在视区中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="24f0d-118">In your viewport, hover on the element, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
*   <span data-ttu-id="24f0d-119">在 DevTools 中，选择 "**选择元素**\ (![ 选择元素 ][ImageSelectAnElementIcon] \ ) 或选择 `Control` + `Shift` + `C` \ (Windows \ ) 或 `Command` + `Shift` + `C` \ (macOS \ ) "，然后选择视区中的元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-119">In DevTools, choose **Select an element** \(![Select an element][ImageSelectAnElementIcon]\) or select `Control`+`Shift`+`C` \(Windows\) or `Command`+`Shift`+`C` \(macOS\), and then choose the element in the viewport.</span></span>  
*   <span data-ttu-id="24f0d-120">在 DevTools 中，选择 **DOM 树**中的元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-120">In DevTools, choose the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="24f0d-121">在 DevTools 中，运行一个如 `document.querySelector('p')` 在 **控制台**中的查询，将鼠标悬停在结果上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 **"在元素中显示" 面板**。</span><span class="sxs-lookup"><span data-stu-id="24f0d-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, hover on the result, open the contextual menu \(right-click\), and select **Reveal in Elements panel**.</span></span>  

## <span data-ttu-id="24f0d-122">查看 CSS</span><span class="sxs-lookup"><span data-stu-id="24f0d-122">View CSS</span></span>  

### <span data-ttu-id="24f0d-123">查看定义规则的外部样式表</span><span class="sxs-lookup"><span data-stu-id="24f0d-123">View the external stylesheet where a rule is defined</span></span>  

<span data-ttu-id="24f0d-124">在 " **样式** " 窗格中，选择 CSS 规则旁边的链接以打开定义该规则的外部样式表。</span><span class="sxs-lookup"><span data-stu-id="24f0d-124">In the **Styles** pane, choose the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  

<span data-ttu-id="24f0d-125">如果样式表是 minified，请参阅 [使 minified 文件易于阅读][DevToolsJavascriptReferenceFormat]。</span><span class="sxs-lookup"><span data-stu-id="24f0d-125">If the stylesheet is minified, see [Make a minified file readable][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-126">在下图中，选择 " `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 转到" 第2行 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` ，其中 `.content h1:first-of-type` 定义了 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="24f0d-126">In the following figure, after you choose `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` you are taken to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  <span data-ttu-id="24f0d-128">查看定义规则的样式表</span><span class="sxs-lookup"><span data-stu-id="24f0d-128">Viewing the stylesheet where a rule is defined</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-129">仅查看实际应用到元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="24f0d-129">View only the CSS that is actually applied to an element</span></span>  

<span data-ttu-id="24f0d-130">" **样式** " 选项卡显示适用于元素的所有规则，包括已重写的声明。</span><span class="sxs-lookup"><span data-stu-id="24f0d-130">The **Styles** tab shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="24f0d-131">当你对替代声明不感兴趣时，请使用 " **计算** " 选项卡仅查看实际应用于元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="24f0d-131">When you are not interested in overridden declarations, use the **Computed** tab to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="24f0d-132">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-132">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="24f0d-133">转到 "**元素**" 面板中的 "**计算**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24f0d-133">Go to the **Computed** tab in the **Elements** panel.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-134">在宽 DevTools 窗口中， **计算** 的选项卡不存在。</span><span class="sxs-lookup"><span data-stu-id="24f0d-134">On a wide DevTools window, the **Computed** tab does not exist.</span></span>  <span data-ttu-id="24f0d-135">**计算**的选项卡的内容显示在 "**样式**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="24f0d-135">The contents of the **Computed** tab are shown on the **Styles** tab.</span></span>  

<span data-ttu-id="24f0d-136">继承的属性是不透明的。</span><span class="sxs-lookup"><span data-stu-id="24f0d-136">Inherited properties are opaque.</span></span>  <span data-ttu-id="24f0d-137">选中 " **全部显示** " 复选框以查看所有继承值。</span><span class="sxs-lookup"><span data-stu-id="24f0d-137">Check the **Show All** checkbox to see all inherited values.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-138">在下图中，" **计算** " 选项卡显示应用于当前所选元素的 CSS 属性 `h1` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-138">In the following figure, the **Computed** tab shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-computed-h1.msft.png":::
   <span data-ttu-id="24f0d-140">**计算**选项卡</span><span class="sxs-lookup"><span data-stu-id="24f0d-140">The **Computed** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-141">按字母顺序查看 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="24f0d-141">View CSS properties in alphabetical order</span></span>  

<span data-ttu-id="24f0d-142">使用 " **计算** " 选项卡。 请参阅 [仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-142">Use the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="24f0d-143">查看继承的 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="24f0d-143">View inherited CSS properties</span></span>  

<span data-ttu-id="24f0d-144">选中 "**计算**" 选项卡中的 "**全部显示**" 复选框。 请参阅[仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-144">Check the **Show All** checkbox in the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="24f0d-145">查看元素的 box 模型</span><span class="sxs-lookup"><span data-stu-id="24f0d-145">View the box model for an element</span></span>  

<span data-ttu-id="24f0d-146">若要查看元素 [的方框模型][MDNBoxModel] ，请转到 " **样式** " 选项卡。 如果 DevTools 窗口较窄，则 **框模型** 图位于选项卡的底部。</span><span class="sxs-lookup"><span data-stu-id="24f0d-146">To view [the box model][MDNBoxModel] of an element, go to the **Styles** tab.  If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the tab.</span></span>  

<span data-ttu-id="24f0d-147">选择并编辑值以更改值。</span><span class="sxs-lookup"><span data-stu-id="24f0d-147">Choose and edit on a value to change a value.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-148">在下图中，"**样式**" 选项卡中的 "**方框模型**" 图显示了当前所选元素的框模型 `h1` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-148">In the following figure, the **Box Model** diagram in the **Styles** tab shows the box model for the currently selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   <span data-ttu-id="24f0d-150">**方框模型**图</span><span class="sxs-lookup"><span data-stu-id="24f0d-150">The **Box Model** diagram</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-151">搜索和筛选元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="24f0d-151">Search and filter the CSS of an element</span></span>  

<span data-ttu-id="24f0d-152">使用 "**样式**" 和 "**计算**" 选项卡上的 "**筛选器**" 文本框搜索特定的 CSS 属性或值。</span><span class="sxs-lookup"><span data-stu-id="24f0d-152">Use the **Filter** text box on the **Styles** and **Computed** tabs to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="24f0d-153">若要同时在 " **计算** " 选项卡中搜索继承的属性，请选中 " **全部显示** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="24f0d-153">To also search inherited properties in the **Computed** tab, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-154">在下图中，筛选 " **样式** " 选项卡以仅显示包含搜索查询的规则 `color` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-154">In the following figure, the **Styles** tab is filtered to only show rules that include the search query `color`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   <span data-ttu-id="24f0d-156">筛选 " **样式** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="24f0d-156">Filter the **Styles** tab</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="24f0d-157">在下图中，" **计算** " 选项卡将筛选为仅显示包含 "搜索" 查询的声明 `100%` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-157">In the following figure, the **Computed** tab is filtered to only show declarations that include the search query `100%`.</span></span>  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   <span data-ttu-id="24f0d-159">筛选 **计算** 的选项卡</span><span class="sxs-lookup"><span data-stu-id="24f0d-159">Filter the **Computed** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-160">切换伪类</span><span class="sxs-lookup"><span data-stu-id="24f0d-160">Toggle a pseudo-class</span></span>  

<span data-ttu-id="24f0d-161">完成以下操作，以切换伪类 `:active` ，如、 `:focus` 、 `:hover` 或 `:visited` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-161">Complete the following actions to toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`.</span></span>  

1.  <span data-ttu-id="24f0d-162">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-162">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="24f0d-163">在 " **元素** " 面板上，转到 " **样式** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24f0d-163">On the **Elements** panel, go to the **Styles** tab.</span></span>  
1.  <span data-ttu-id="24f0d-164">选择 **： hov**。</span><span class="sxs-lookup"><span data-stu-id="24f0d-164">Choose **:hov**.</span></span>  
1.  <span data-ttu-id="24f0d-165">检查要启用的伪类。</span><span class="sxs-lookup"><span data-stu-id="24f0d-165">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-166">在下图中，切换 `:hover` 伪类。</span><span class="sxs-lookup"><span data-stu-id="24f0d-166">In the following figure, toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="24f0d-167">在视区中，验证 `background-color: cornflowerblue` 是否将声明应用于该元素，即使该元素实际上不是悬停在该元素上。</span><span class="sxs-lookup"><span data-stu-id="24f0d-167">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   <span data-ttu-id="24f0d-169">切换 `:hover` 伪类</span><span class="sxs-lookup"><span data-stu-id="24f0d-169">Toggle the `:hover` pseudo-class</span></span>  
:::image-end:::  

<span data-ttu-id="24f0d-170">有关交互式教程，请参阅 [向类添加伪][DevToolsCSSGetStartedAddPseudoState]状态。</span><span class="sxs-lookup"><span data-stu-id="24f0d-170">For an interactive tutorial, see [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState].</span></span>  

### <span data-ttu-id="24f0d-171">在打印模式下查看页面</span><span class="sxs-lookup"><span data-stu-id="24f0d-171">View a page in print mode</span></span>  

<span data-ttu-id="24f0d-172">完成以下操作以在打印模式下查看页面。</span><span class="sxs-lookup"><span data-stu-id="24f0d-172">Complete the following actions to view a page in print mode.</span></span>  

1.  <span data-ttu-id="24f0d-173">[打开 "命令" 菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="24f0d-173">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="24f0d-174">开始键入 `Rendering` 并选择 `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-174">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="24f0d-175">对于 " **模拟 CSS 媒体** " 下拉列表，选择 " **打印**"。</span><span class="sxs-lookup"><span data-stu-id="24f0d-175">For the **Emulate CSS Media** dropdown, select **print**.</span></span>  

### <span data-ttu-id="24f0d-176">使用 "覆盖范围" 选项卡查看使用和未使用的 CSS</span><span class="sxs-lookup"><span data-stu-id="24f0d-176">View used and unused CSS with the Coverage tab</span></span>  

<span data-ttu-id="24f0d-177">"覆盖范围" 选项卡显示页面实际使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="24f0d-177">The Coverage tab shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="24f0d-178">选择 `Control` + `Shift` + `P` \ `Command` + `Shift` + `P` 当 DevTools 处于焦点时， (Windows \ ) 或 \ (macOS \ ) [打开 "命令" 菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="24f0d-178">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to [open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="24f0d-179">开始键入 `coverage` ，然后选择 " **显示覆盖率**"。</span><span class="sxs-lookup"><span data-stu-id="24f0d-179">Start typing `coverage` and select **Show Coverage**.</span></span>  <span data-ttu-id="24f0d-180">将显示 "覆盖范围" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24f0d-180">The Coverage tab appears.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="所选元素的示例" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             <span data-ttu-id="24f0d-182">从 "**命令" 菜单**打开 "**覆盖范围**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="24f0d-182">Open the **Coverage** tab from the **Command Menu**</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="所选元素的示例" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             <span data-ttu-id="24f0d-184">" **覆盖范围** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="24f0d-184">The **Coverage** tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="24f0d-185">选择 " **开始检测覆盖率" 并刷新页面** \ (" ![ 开始检测覆盖率" 并刷新页面 ][ImageRefreshIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-185">Choose **Start instrumenting coverage and refresh the page** \(![Start instrumenting coverage and refresh the page][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="24f0d-186">页面刷新，"覆盖率" 选项卡提供浏览器加载的每个文件中使用的 CSS \ (和 JavaScript ) 的概述。</span><span class="sxs-lookup"><span data-stu-id="24f0d-186">The page refreshes and the Coverage tab provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="24f0d-187">绿色表示使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="24f0d-187">Green represents used CSS.</span></span>  <span data-ttu-id="24f0d-188">红色表示未使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="24f0d-188">Red represents unused CSS.</span></span>  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="所选元素的示例" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       <span data-ttu-id="24f0d-190">有关使用和未使用的 CSS \ (和 JavaScript \ ) 多少的概述</span><span class="sxs-lookup"><span data-stu-id="24f0d-190">An overview of how much CSS \(and JavaScript\) is used and unused</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="24f0d-191">选择一个 CSS 文件以查看逐行分解它所使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="24f0d-191">Choose a CSS file to see a line-by-line breakdown of what CSS it uses.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="24f0d-192">在下图中，行145到147和149到 151 `b66bc881.site-ltr.css` 未使用，而使用行163到166。</span><span class="sxs-lookup"><span data-stu-id="24f0d-192">In the following figure, lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="所选元素的示例" lightbox="../media/css-sources-css-coverage.msft.png":::
       <span data-ttu-id="24f0d-194">已使用和未使用的 CSS 的逐行划分</span><span class="sxs-lookup"><span data-stu-id="24f0d-194">A line-by-line breakdown of used and unused CSS</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="24f0d-195">强制打印预览模式</span><span class="sxs-lookup"><span data-stu-id="24f0d-195">Force print preview mode</span></span>  

<span data-ttu-id="24f0d-196">请参阅 [强制 DevTools 进入打印预览模式][DevToolsCssPrintPreview]。</span><span class="sxs-lookup"><span data-stu-id="24f0d-196">See [Force DevTools into Print Preview mode][DevToolsCssPrintPreview].</span></span>  

## <span data-ttu-id="24f0d-197">更改 CSS</span><span class="sxs-lookup"><span data-stu-id="24f0d-197">Change CSS</span></span>  

<!-- todo s/CSS declaration/declaration/ -->  

### <span data-ttu-id="24f0d-198">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-198">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="24f0d-199">声明顺序影响元素的样式，使用以下列表可帮助你以不同的方式添加声明。</span><span class="sxs-lookup"><span data-stu-id="24f0d-199">The order of declarations affects how an element is styled, use the following list to help you add declarations in different ways.</span></span>  

*   <span data-ttu-id="24f0d-200">[添加内联声明](#add-an-inline-declaration)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-200">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="24f0d-201">等效于将 `style` 属性添加到元素的 HTML。</span><span class="sxs-lookup"><span data-stu-id="24f0d-201">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="24f0d-202">[将声明添加到样式规则](#add-a-declaration-to-a-style-rule)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-202">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="24f0d-203">应该使用哪个工作流？</span><span class="sxs-lookup"><span data-stu-id="24f0d-203">What workflow should you use?</span></span>** <span data-ttu-id="24f0d-204">在大多数情况下，你可能希望使用内联声明工作流。</span><span class="sxs-lookup"><span data-stu-id="24f0d-204">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="24f0d-205">内联声明具有比外部声明更高的程度，因此内联工作流可确保所做的更改会在你的预期元素中生效。</span><span class="sxs-lookup"><span data-stu-id="24f0d-205">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in your expected element.</span></span>  <span data-ttu-id="24f0d-206">有关具体程度的详细信息，请参阅 [选择器类型][MDNSelectorTypes]。</span><span class="sxs-lookup"><span data-stu-id="24f0d-206">For more information about specificity, see [Selector Types][MDNSelectorTypes].</span></span>  

<span data-ttu-id="24f0d-207">如果你正在调试元素的任何样式，并且你需要专门测试在不同位置定义声明时所发生的情况，请使用其他工作流。</span><span class="sxs-lookup"><span data-stu-id="24f0d-207">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <span data-ttu-id="24f0d-208">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-208">Add an inline declaration</span></span>  

<span data-ttu-id="24f0d-209">完成以下操作以添加内联声明。</span><span class="sxs-lookup"><span data-stu-id="24f0d-209">Complete the following actions to add an inline declaration.</span></span>  

1.  <span data-ttu-id="24f0d-210">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-210">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="24f0d-211">在 " **样式** " 窗格中，选择元素的方括号 **。 "样式** " 部分。</span><span class="sxs-lookup"><span data-stu-id="24f0d-211">In the **Styles** pane, choose between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="24f0d-212">光标焦点，允许您输入文本。</span><span class="sxs-lookup"><span data-stu-id="24f0d-212">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="24f0d-213">输入属性名称，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-213">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="24f0d-214">输入该属性的有效值，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-214">Enter a valid value for that property and select `Enter`.</span></span>  <span data-ttu-id="24f0d-215">在 **DOM 树**中，验证是否已将某个 `style` 属性添加到该元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-215">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-216">在下图中，"" `margin-top` 和 " `background-color` 属性" 已应用于所选元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-216">In the following figure, the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="24f0d-217">在 **DOM 树** 中，验证声明是否反映在元素的 `style` 属性中。</span><span class="sxs-lookup"><span data-stu-id="24f0d-217">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   <span data-ttu-id="24f0d-219">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-219">Add inline declarations</span></span>  
:::image-end:::  

#### <span data-ttu-id="24f0d-220">将声明添加到样式规则</span><span class="sxs-lookup"><span data-stu-id="24f0d-220">Add a declaration to a style rule</span></span>  

<span data-ttu-id="24f0d-221">完成以下操作以将声明添加到现有样式规则。</span><span class="sxs-lookup"><span data-stu-id="24f0d-221">Complete the following actions to add a declaration to an existing style rule.</span></span>  

1.  <span data-ttu-id="24f0d-222">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-222">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="24f0d-223">在 " **样式** " 窗格中，选择要向其中添加声明的样式规则的括号。</span><span class="sxs-lookup"><span data-stu-id="24f0d-223">In the **Styles** pane, choose between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="24f0d-224">光标焦点，允许您输入文本。</span><span class="sxs-lookup"><span data-stu-id="24f0d-224">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="24f0d-225">输入属性名称，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-225">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="24f0d-226">输入该属性的有效值，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-226">Enter a valid value for that property and select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   <span data-ttu-id="24f0d-228">将 `border-bottom-style:groove` 声明添加到样式规则</span><span class="sxs-lookup"><span data-stu-id="24f0d-228">Add the `border-bottom-style:groove` declaration to a style rule</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-229">更改声明名称或值</span><span class="sxs-lookup"><span data-stu-id="24f0d-229">Change a declaration name or value</span></span>  

<span data-ttu-id="24f0d-230">选择并编辑声明的名称或值，以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="24f0d-230">Choose and edit the name or value of a declaration to change it.</span></span>  <span data-ttu-id="24f0d-231">请参阅使用快捷键的 [键盘快捷方式更改声明值](#change-declaration-values-with-keyboard-shortcuts) ，快速将值按 `0.1` 、、 `1` `10` 或单位递减或递减 `100` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-231">See [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts) for shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   <span data-ttu-id="24f0d-233">更改声明的值 `border-bottom-style`</span><span class="sxs-lookup"><span data-stu-id="24f0d-233">Change the value of the `border-bottom-style` declaration</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-234">通过键盘快捷方式更改声明值</span><span class="sxs-lookup"><span data-stu-id="24f0d-234">Change declaration values with keyboard shortcuts</span></span>  

<span data-ttu-id="24f0d-235">编辑声明的值时，可以使用以下键盘快捷方式将值增加一个特定的量。</span><span class="sxs-lookup"><span data-stu-id="24f0d-235">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a specific amount.</span></span>  

*   <span data-ttu-id="24f0d-236">选择 `Alt` + `Up` \ (Windows \ ) 或 `Option` + `Up` \ (macOS \ ) 递增 `0.1` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-236">Select `Alt`+`Up` \(Windows\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="24f0d-237">选择 `Up` 以更改值 `1` ，或者 `0.1` 如果当前值介于和之间，则选择此值 `-1` `1` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-237">Select `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="24f0d-238">选择 " `Shift` + `Up` 增加方式" `10` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-238">Select `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="24f0d-239">选择 `Shift` + `Page Up` \ (Windows \ ) 或 `Shift` + `Command` + `Up` \ (macOS \ ) 将值增加 `100` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-239">Select `Shift`+`Page Up` \(Windows\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="24f0d-240">减量也有效。</span><span class="sxs-lookup"><span data-stu-id="24f0d-240">Decrementing also works.</span></span>  <span data-ttu-id="24f0d-241">只需将上面提及的每个实例替换 `Up` 为 `Down` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-241">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <span data-ttu-id="24f0d-242">向元素添加类</span><span class="sxs-lookup"><span data-stu-id="24f0d-242">Add a class to an element</span></span>  

<span data-ttu-id="24f0d-243">完成以下操作以将类添加到元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-243">Complete the following actions to add a class to an element.</span></span>  

1.  <span data-ttu-id="24f0d-244">在**DOM 树**中[选择该元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-244">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="24f0d-245">选择 **. cls**。</span><span class="sxs-lookup"><span data-stu-id="24f0d-245">Choose **.cls**.</span></span>  
1.  <span data-ttu-id="24f0d-246">在 " **添加新类** " 文本框中输入类的名称。</span><span class="sxs-lookup"><span data-stu-id="24f0d-246">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="24f0d-247">选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-247">Select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   <span data-ttu-id="24f0d-249">" **元素类** " 窗格</span><span class="sxs-lookup"><span data-stu-id="24f0d-249">The **Element Classes** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-250">切换类</span><span class="sxs-lookup"><span data-stu-id="24f0d-250">Toggle a class</span></span>  

<span data-ttu-id="24f0d-251">完成以下操作以在元素上启用或禁用类。</span><span class="sxs-lookup"><span data-stu-id="24f0d-251">Complete the following actions to enable or disable a class on an element.</span></span>  

1.  <span data-ttu-id="24f0d-252">在**DOM 树**中[选择该元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-252">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="24f0d-253">打开 " **元素类** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="24f0d-253">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="24f0d-254">请参阅 [向元素添加类](#add-a-class-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-254">See [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="24f0d-255">在 " **添加新类** " 文本框下方是应用于特定元素的所有类。</span><span class="sxs-lookup"><span data-stu-id="24f0d-255">Below the **Add New Class** text box are all of the classes that are being applied to the specific element.</span></span>  
1.  <span data-ttu-id="24f0d-256">切换要启用或禁用的类旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="24f0d-256">Toggle the checkbox next to the class that you want to enable or disable.</span></span>  

### <span data-ttu-id="24f0d-257">添加样式规则</span><span class="sxs-lookup"><span data-stu-id="24f0d-257">Add a style rule</span></span>  

<span data-ttu-id="24f0d-258">完成以下操作以添加新的样式规则。</span><span class="sxs-lookup"><span data-stu-id="24f0d-258">Complete the following actions to add a new style rule.</span></span>  

1.  <span data-ttu-id="24f0d-259">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-259">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="24f0d-260">选择 " **新建样式规则** \ (![ 新样式规则 ][ImageNewStyleRuleIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-260">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\).</span></span>  <span data-ttu-id="24f0d-261">DevTools 在元素下方插入新规则 **。 style** 规则。</span><span class="sxs-lookup"><span data-stu-id="24f0d-261">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-262">在下图中，DevTools 将添加 `h1.devsite-page-title` 样式规则，然后选择 " **新建样式规则**"。</span><span class="sxs-lookup"><span data-stu-id="24f0d-262">In the following figure, DevTools adds the `h1.devsite-page-title` style rule after you choose **New Style Rule**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-style-new.msft.png":::
   <span data-ttu-id="24f0d-264">添加新样式规则</span><span class="sxs-lookup"><span data-stu-id="24f0d-264">Add a new style rule</span></span>  
:::image-end:::  

#### <span data-ttu-id="24f0d-265">选择要向其添加规则的样式表</span><span class="sxs-lookup"><span data-stu-id="24f0d-265">Choose which stylesheet to add a rule to</span></span>  

<span data-ttu-id="24f0d-266">[添加新样式规则](#add-a-style-rule)时，选择并保留**新的样式**规则 \ (" ![ 新建样式规则 \ ) "，选择要向 ][ImageNewStyleRuleIcon] 其添加样式规则的样式表。</span><span class="sxs-lookup"><span data-stu-id="24f0d-266">When [adding a new style rule](#add-a-style-rule), choose and hold **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) to choose which stylesheet to add the style rule to.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   <span data-ttu-id="24f0d-268">选择样式表</span><span class="sxs-lookup"><span data-stu-id="24f0d-268">Choose a stylesheet</span></span>  
:::image-end:::  

#### <span data-ttu-id="24f0d-269">将样式规则添加到特定位置</span><span class="sxs-lookup"><span data-stu-id="24f0d-269">Add a style rule to a specific location</span></span>  

<span data-ttu-id="24f0d-270">完成以下操作，将样式规则添加到 " **样式** " 选项卡中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="24f0d-270">Complete the following actions to add a style rule to a specific location in the **Styles** tab.</span></span>  

1.  <span data-ttu-id="24f0d-271">将鼠标悬停在要添加新样式规则的正上方的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="24f0d-271">Hover over the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="24f0d-272">[显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-272">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="24f0d-273">选择 **下面的 "插入样式规则** \ (" ![ 下方的 "插入样式规则 \ ][ImageNewStyleRuleIcon] ) "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-273">Choose **Insert Style Rule Below** \(![Insert Style Rule Below][ImageNewStyleRuleIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **<span data-ttu-id="24f0d-275">在下方插入样式规则</span><span class="sxs-lookup"><span data-stu-id="24f0d-275">Insert Style Rule Below</span></span>**  
:::image-end:::  

### <span data-ttu-id="24f0d-276">显示 "更多操作" 工具栏</span><span class="sxs-lookup"><span data-stu-id="24f0d-276">Reveal the More Actions toolbar</span></span>  

<span data-ttu-id="24f0d-277">" **更多操作** " 工具栏使您可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="24f0d-277">The **More Actions** toolbar lets you perform the following actions.</span></span>  

*   <span data-ttu-id="24f0d-278">直接在你的重点所在的下插入样式规则。</span><span class="sxs-lookup"><span data-stu-id="24f0d-278">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="24f0d-279">向 `background-color` `color` `box-shadow` 你关注的样式规则添加、、或 `text-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="24f0d-279">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="24f0d-280">完成以下操作以显示 " **更多操作** " 工具栏。</span><span class="sxs-lookup"><span data-stu-id="24f0d-280">Complete the following actions to reveal the **More Actions** toolbar.</span></span>  

1.  <span data-ttu-id="24f0d-281">在 " **样式** " 选项卡中，将鼠标悬停在样式规则上。</span><span class="sxs-lookup"><span data-stu-id="24f0d-281">In the **Styles** tab, hover over a style rule.</span></span>  <span data-ttu-id="24f0d-282">**More Actions** `...` "样式规则" 部分右下角显示了 "更多操作 \ (\ ) "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-282">**More Actions** \(`...`\) is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="24f0d-283">在下图中，将鼠标悬停在 `.header-holder.has-default-focus` 样式规则上方，并显示 "样式规则" 部分右下角的 " **更多操作** "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-283">In the following figure, hover over the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       <span data-ttu-id="24f0d-285">显示 **更多操作** \ (`...` \ ) </span><span class="sxs-lookup"><span data-stu-id="24f0d-285">Reveal **More Actions** \(`...`\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="24f0d-286">将鼠标悬停在 " **更多操作** " 上 \ (`...` \ ) 以显示上述操作。</span><span class="sxs-lookup"><span data-stu-id="24f0d-286">Hover over **More Actions** \(`...`\) to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="24f0d-287">将鼠标悬停在**更多操作**之后，将显示 "**下方的插入样式规则**" 操作。</span><span class="sxs-lookup"><span data-stu-id="24f0d-287">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       <span data-ttu-id="24f0d-289">" **更多操作** " 工具栏</span><span class="sxs-lookup"><span data-stu-id="24f0d-289">The **More Actions** toolbar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="24f0d-290">切换声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-290">Toggle a declaration</span></span>  

<span data-ttu-id="24f0d-291">完成 folllwoing 操作以切换 \ (或 off \ ) 上的单个声明。</span><span class="sxs-lookup"><span data-stu-id="24f0d-291">Complete the folllwoing actions to toggle a single declaration on \(or off\).</span></span>  

1.  <span data-ttu-id="24f0d-292">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-292">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="24f0d-293">在 " **样式** " 窗格中，将鼠标悬停在定义声明的规则上方。</span><span class="sxs-lookup"><span data-stu-id="24f0d-293">In the **Styles** pane, hover over the rule that defines the declaration.</span></span>  <span data-ttu-id="24f0d-294">每个声明旁边都会显示一个复选框。</span><span class="sxs-lookup"><span data-stu-id="24f0d-294">A checkbox appears next to each declaration.</span></span>  
1.  <span data-ttu-id="24f0d-295">选中 \ (或取消选中 \ ) 声明旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="24f0d-295">Check \(or uncheck\) the checkbox next to the declaration.</span></span>  <span data-ttu-id="24f0d-296">取消选中某个声明后，DevTools 将其置于外，以指示它不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="24f0d-296">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="24f0d-297">下图中， `margin-top` 当前所选元素的属性已关闭。</span><span class="sxs-lookup"><span data-stu-id="24f0d-297">In the following figure, the `margin-top` property for the currently selected element has been toggled off.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   <span data-ttu-id="24f0d-299">切换声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-299">Toggle a declaration</span></span>  
:::image-end:::  

### <span data-ttu-id="24f0d-300">添加背景色声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-300">Add a background-color declaration</span></span>  

<span data-ttu-id="24f0d-301">完成以下操作以将声明添加 `background-color` 到元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-301">Complete the following actions to add a `background-color` declaration to an element.</span></span>  

1.  <span data-ttu-id="24f0d-302">将鼠标悬停在要向其添加声明的样式规则上 `background-color` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-302">Hover over the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="24f0d-303">[显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-303">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="24f0d-304">选择 " **添加背景色** \ (![ 添加背景色 ][ImageAddBackgroundColorIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-304">Choose **Add Background Color** \(![Add Background Color][ImageAddBackgroundColorIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **<span data-ttu-id="24f0d-306">添加背景色</span><span class="sxs-lookup"><span data-stu-id="24f0d-306">Add Background Color</span></span>**  
:::image-end:::  

### <span data-ttu-id="24f0d-307">添加颜色声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-307">Add a color declaration</span></span>  

<span data-ttu-id="24f0d-308">完成以下操作以将声明添加 `color` 到元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-308">Complete the following actions to add a `color` declaration to an element.</span></span>  

1.  <span data-ttu-id="24f0d-309">将鼠标悬停在要向其添加声明的样式规则上 `color` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-309">Hover over the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="24f0d-310">[显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-310">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="24f0d-311">选择 " **添加颜色** \" (" ![ 添加颜色 ][ImageAddColorIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-311">Choose **Add Color** \(![Add Color][ImageAddColorIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **<span data-ttu-id="24f0d-313">添加颜色</span><span class="sxs-lookup"><span data-stu-id="24f0d-313">Add Color</span></span>**  
:::image-end:::  

### <span data-ttu-id="24f0d-314">添加 box-阴影声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-314">Add a box-shadow declaration</span></span>  

<span data-ttu-id="24f0d-315">完成以下操作以将声明添加 `box-shadow` 到元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-315">Complete the follwoing actions to add a `box-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="24f0d-316">将鼠标悬停在要向其添加声明的样式规则上 `box-shadow` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-316">Hover over the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="24f0d-317">[显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-317">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="24f0d-318">选择 **"添加框阴影** \ (![ 添加框阴影 ][ImageAddBoxShadowIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-318">Choose **Add Box Shadow** \(![Add Box Shadow][ImageAddBoxShadowIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **<span data-ttu-id="24f0d-320">添加框阴影</span><span class="sxs-lookup"><span data-stu-id="24f0d-320">Add Box Shadow</span></span>**  
:::image-end:::  

### <span data-ttu-id="24f0d-321">添加文本阴影声明</span><span class="sxs-lookup"><span data-stu-id="24f0d-321">Add a text-shadow declaration</span></span>  

<span data-ttu-id="24f0d-322">完成以下操作以将声明添加 `text-shadow` 到元素。</span><span class="sxs-lookup"><span data-stu-id="24f0d-322">Complete the following actions to add a `text-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="24f0d-323">将鼠标悬停在要向其添加声明的样式规则上 `text-shadow` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-323">Hover over the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="24f0d-324">[显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-324">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="24f0d-325">选择 " **添加文本阴影** \ (![ 添加文本阴影 ][ImageAddTextShadowIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="24f0d-325">Choose **Add Text Shadow** \(![Add Text Shadow][ImageAddTextShadowIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **<span data-ttu-id="24f0d-327">添加文本阴影</span><span class="sxs-lookup"><span data-stu-id="24f0d-327">Add Text Shadow</span></span>**  
:::image-end:::  

### <span data-ttu-id="24f0d-328">使用颜色选取器更改颜色</span><span class="sxs-lookup"><span data-stu-id="24f0d-328">Change colors with the Color Picker</span></span>  

<span data-ttu-id="24f0d-329">**颜色选取器**提供了用于更改 `color` 和声明的 GUI `background-color` 。</span><span class="sxs-lookup"><span data-stu-id="24f0d-329">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="24f0d-330">完成以下操作以打开 " **拾色器**"。</span><span class="sxs-lookup"><span data-stu-id="24f0d-330">Complete the following actions to open the **Color Picker**.</span></span>  

1.  <span data-ttu-id="24f0d-331">[选择一个元素](#select-an-element)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-331">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="24f0d-332">在 " **样式** " 选项卡中，找到 `color` `background-color` 要更改的、或类似的声明。</span><span class="sxs-lookup"><span data-stu-id="24f0d-332">In the **Styles** tab, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="24f0d-333">在 " `color` 、" `background-color` 或 "类似" 值的左侧，有一个小方块，它是颜色的预览。</span><span class="sxs-lookup"><span data-stu-id="24f0d-333">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="24f0d-334">在下图中，左侧的小方块 `rgba(0, 0, 0, 0.7)` 是该颜色的预览。</span><span class="sxs-lookup"><span data-stu-id="24f0d-334">In the following figure, the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       <span data-ttu-id="24f0d-336">颜色预览</span><span class="sxs-lookup"><span data-stu-id="24f0d-336">Color preview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="24f0d-337">选择 "预览" 以打开 " **颜色选取器**"。</span><span class="sxs-lookup"><span data-stu-id="24f0d-337">Choose the preview to open the **Color Picker**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       <span data-ttu-id="24f0d-339">**颜色选取器**</span><span class="sxs-lookup"><span data-stu-id="24f0d-339">The **Color Picker**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="24f0d-340">下图，并列出了 **颜色选取器**的每个 UI 元素的 descries。</span><span class="sxs-lookup"><span data-stu-id="24f0d-340">The following figure and list descries of each of the UI elements of the **Color Picker**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   <span data-ttu-id="24f0d-342">**颜色选取器**，批注</span><span class="sxs-lookup"><span data-stu-id="24f0d-342">The **Color Picker**, annotated</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-343">raid-1</span><span class="sxs-lookup"><span data-stu-id="24f0d-343">1</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-344">阴影</span><span class="sxs-lookup"><span data-stu-id="24f0d-344">Shades</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-345">ppls-2</span><span class="sxs-lookup"><span data-stu-id="24f0d-345">2</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-346">变成</span><span class="sxs-lookup"><span data-stu-id="24f0d-346">Eyedropper</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="24f0d-347">有关详细信息，请参阅 [使用取色器在页面上示例颜色](#sample-a-color-off-the-page-with-the-eyedropper)。</span><span class="sxs-lookup"><span data-stu-id="24f0d-347">For more information, see [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-348">三维空间</span><span class="sxs-lookup"><span data-stu-id="24f0d-348">3</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-349">复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="24f0d-349">Copy To Clipboard</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="24f0d-350">将 **显示值** 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="24f0d-350">Copy the **Display Value** to your clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-351">第</span><span class="sxs-lookup"><span data-stu-id="24f0d-351">4</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-352">显示值</span><span class="sxs-lookup"><span data-stu-id="24f0d-352">Display Value</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="24f0d-353">颜色的 RGBA、HSLA 或十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="24f0d-353">The RGBA, HSLA, or Hex representation of the color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-354">级</span><span class="sxs-lookup"><span data-stu-id="24f0d-354">5</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-355">调色板</span><span class="sxs-lookup"><span data-stu-id="24f0d-355">Color Palette</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="24f0d-356">选择其中一个方框将颜色更改为该正方形。</span><span class="sxs-lookup"><span data-stu-id="24f0d-356">Choose one of the squares to change the color to that square.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-357">型</span><span class="sxs-lookup"><span data-stu-id="24f0d-357">6</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-358">色调</span><span class="sxs-lookup"><span data-stu-id="24f0d-358">Hue</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-359">7</span><span class="sxs-lookup"><span data-stu-id="24f0d-359">7</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-360">Opacity</span><span class="sxs-lookup"><span data-stu-id="24f0d-360">Opacity</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-361">个</span><span class="sxs-lookup"><span data-stu-id="24f0d-361">8</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-362">显示值切换器</span><span class="sxs-lookup"><span data-stu-id="24f0d-362">Display Value Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="24f0d-363">在当前颜色的 RGBA、HSLA 和十六进制表示形式之间切换。</span><span class="sxs-lookup"><span data-stu-id="24f0d-363">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24f0d-364">db-9</span><span class="sxs-lookup"><span data-stu-id="24f0d-364">9</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="24f0d-365">调色板切换器</span><span class="sxs-lookup"><span data-stu-id="24f0d-365">Color Palette Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="24f0d-366">在 [材料设计调色板][MaterialDesignColorSystem]、自定义调色板或页面颜色调色板之间切换。</span><span class="sxs-lookup"><span data-stu-id="24f0d-366">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="24f0d-367">DevTools 基于在样式表中找到的颜色生成页面调色板。</span><span class="sxs-lookup"><span data-stu-id="24f0d-367">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="24f0d-368">使用滴管对页面进行颜色取样</span><span class="sxs-lookup"><span data-stu-id="24f0d-368">Sample a color off the page with the Eyedropper</span></span>  

<span data-ttu-id="24f0d-369">打开 " **颜色选取器**" 时，默认情况下， **取色** 器 \ (![ 吸管 ][ImageEyedropperIcon] \ ) 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="24f0d-369">When you open the **Color Picker**, the **Eyedropper** \(![Eyedropper][ImageEyedropperIcon]\) is on by default.</span></span>  <span data-ttu-id="24f0d-370">完成以下操作以将所选颜色更改为页面上的其他颜色。</span><span class="sxs-lookup"><span data-stu-id="24f0d-370">Complete the following actions to change the selected color to some other color on the page.</span></span>  

1.  <span data-ttu-id="24f0d-371">将鼠标悬停在视区中的目标颜色上。</span><span class="sxs-lookup"><span data-stu-id="24f0d-371">Hover over the target color in the viewport.</span></span>  
1.  <span data-ttu-id="24f0d-372">选择 "确认"。</span><span class="sxs-lookup"><span data-stu-id="24f0d-372">Choose to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="24f0d-373">在下图中， **颜色选取器** 显示当前颜色值 `rgba(0,0,0,0.7)` ，它接近黑色。</span><span class="sxs-lookup"><span data-stu-id="24f0d-373">In the following figure, the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="24f0d-374">选择特定颜色后，该特定颜色应更改为当前在视区中突出显示的黑色版本。</span><span class="sxs-lookup"><span data-stu-id="24f0d-374">The specific color should change to the version of black that is currently highlighted in the viewport after you chose it.</span></span>  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="所选元素的示例" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       <span data-ttu-id="24f0d-376">使用取色器</span><span class="sxs-lookup"><span data-stu-id="24f0d-376">Using the Eyedropper</span></span>  
    :::image-end:::  
    
<!-- image links -->  

[ImageAddBackgroundColorIcon]: ../media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: ../media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: ../media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: ../media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: ../media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: ../media/select-an-element-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevToolsCSSGetStarted]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "向课堂添加伪状态-开始查看和更改 CSS |Microsoft 文档"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "查看元素的 CSS-开始使用查看和更改 CSS |Microsoft 文档"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "强制 Microsoft Edge DevTools 进入打印预览模式 (CSS 打印媒体类型) |Microsoft 文档"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#make-a-minified-file-readable "使 minified 文件可读-JavaScript 调试参考 |Microsoft 文档"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统-材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "方框模型 |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型-"自由" |MDN"  

> [!NOTE]
> <span data-ttu-id="24f0d-386">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="24f0d-386">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="24f0d-387">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="24f0d-387">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="24f0d-389">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="24f0d-389">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
