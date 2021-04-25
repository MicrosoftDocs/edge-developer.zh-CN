---
description: 探索 Microsoft Edge DevTools 中用于查看和更改 CSS 的新工作流。
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
ms.openlocfilehash: bddbf14e73f5c29bfd4757c9cd6d255f419c331f
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519329"
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

# <a name="css-reference"></a><span data-ttu-id="22c2c-104">CSS 参考</span><span class="sxs-lookup"><span data-stu-id="22c2c-104">CSS reference</span></span>  

<span data-ttu-id="22c2c-105">在以下与查看和更改 CSS 相关的 Microsoft Edge DevTools 功能综合参考中发现新的工作流。</span><span class="sxs-lookup"><span data-stu-id="22c2c-105">Discover new workflows in the following comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="22c2c-106">若要了解基础知识，请导航到 [“查看和更改 CSS 入门”][DevToolsCSSGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="22c2c-106">To learn the basics, navigate to [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <a name="choose-an-element"></a><span data-ttu-id="22c2c-107">选择元素</span><span class="sxs-lookup"><span data-stu-id="22c2c-107">Choose an element</span></span>  

<span data-ttu-id="22c2c-108">DevTools **元素** 工具可用于一次查看或更改一个元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="22c2c-108">The **Elements** tool of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="22c2c-109">所选元素在 **“DOM 树”** 上突出显示。</span><span class="sxs-lookup"><span data-stu-id="22c2c-109">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="22c2c-110">元素的样式显示在 **“样式”** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="22c2c-110">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="22c2c-111">有关教程，请导航到 [查看元素的 CSS][DevToolsCSSGetStartedTutorial]。</span><span class="sxs-lookup"><span data-stu-id="22c2c-111">For a tutorial, navigate to [View the CSS for an element][DevToolsCSSGetStartedTutorial].</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-112">下图中，**“DOM 树”** 中突出显示的 `h1` 元素就是所选元素。</span><span class="sxs-lookup"><span data-stu-id="22c2c-112">In the following figure, the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="22c2c-113">在右侧的样式窗格中显示了元素的 **“样式”**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-113">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="22c2c-114">在左侧，该元素在视区中突出显示，但只是因为当前在 **“DOM 树”** 中鼠标正悬停在它上方。</span><span class="sxs-lookup"><span data-stu-id="22c2c-114">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-h1.msft.png":::
   <span data-ttu-id="22c2c-116">所选元素的示例</span><span class="sxs-lookup"><span data-stu-id="22c2c-116">An example of a selected element</span></span>  
:::image-end:::  

<span data-ttu-id="22c2c-117">使用以下操作之一选择元素。</span><span class="sxs-lookup"><span data-stu-id="22c2c-117">Use one the following actions to select an element.</span></span>  

*   <span data-ttu-id="22c2c-118">在你的视区中，将鼠标悬停在元素上，打开上下文菜单 \(右键单击)，然后选择**检查**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-118">In your viewport, hover on the element, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
*   <span data-ttu-id="22c2c-119">在 DevTools 中，选择 **“选择元素”** \(![“选择元素”](../media/select-an-element-icon.msft.png)\) 或选择 `Control`+`Shift`+`C` \(Windows，Linux\) 或 `Command`+`Shift`+`C` \(macOS\)，然后在视区中选择该元素。</span><span class="sxs-lookup"><span data-stu-id="22c2c-119">In DevTools, choose **Select an element** \(![Select an element](../media/select-an-element-icon.msft.png)\) or select `Control`+`Shift`+`C` \(Windows, Linux\) or `Command`+`Shift`+`C` \(macOS\), and then choose the element in the viewport.</span></span>  
*   <span data-ttu-id="22c2c-120">在 DevTools 中，选择 **“DOM 树”** 中的元素。</span><span class="sxs-lookup"><span data-stu-id="22c2c-120">In DevTools, choose the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="22c2c-121">在 DevTools 中，运行一个查询 (如在 **控制台** 中的 `document.querySelector('p')`)，将鼠标悬停在结果上，打开上下文菜单 \(右键单击\)，然后选择 **“在元素面板上显示 “**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, hover on the result, open the contextual menu \(right-click\), and choose **Reveal in Elements panel**.</span></span>  

## <a name="view-css"></a><span data-ttu-id="22c2c-122">查看 CSS</span><span class="sxs-lookup"><span data-stu-id="22c2c-122">View CSS</span></span>  

### <a name="view-the-external-stylesheet-where-a-rule-is-defined"></a><span data-ttu-id="22c2c-123">查看已定义规则的外部样式表</span><span class="sxs-lookup"><span data-stu-id="22c2c-123">View the external stylesheet where a rule is defined</span></span>  

<span data-ttu-id="22c2c-124">在 **“样式”** 窗格中，选择 CSS 规则旁边的链接，以打开定义该规则的外部样式表。</span><span class="sxs-lookup"><span data-stu-id="22c2c-124">In the **Styles** pane, choose the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  <span data-ttu-id="22c2c-125">样式表将在"源" **工具的** "编辑器" **窗格中** 打开。</span><span class="sxs-lookup"><span data-stu-id="22c2c-125">The stylesheet opens in the **Editor** pane of the **Sources** tool.</span></span>  

<span data-ttu-id="22c2c-126">如果样式表缩小，请选择"编辑器"窗格\*\*\*\* 底部的"格式 ![ \ (格式 ](../media/format-icon.msft.png) **\) "** 按钮。</span><span class="sxs-lookup"><span data-stu-id="22c2c-126">If the stylesheet is minified, choose the **Format** \(![Format](../media/format-icon.msft.png)\) button, at the bottom of the **Editor** pane.</span></span>  <span data-ttu-id="22c2c-127">有关详细信息，请导航到[重新设置一个缩小的 JavaScript 文件与非常打印。][DevToolsJavascriptReferenceFormat]</span><span class="sxs-lookup"><span data-stu-id="22c2c-127">For more information, navigate to [Reformat a minified JavaScript file with pretty-print][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-128">在下图中，当你选择 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 后，将会带你到定义了 `.content h1:first-of-type` CSS 规则的 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 行2。</span><span class="sxs-lookup"><span data-stu-id="22c2c-128">In the following figure, after you choose `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` you are taken to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="查看定义规则的样式表" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  <span data-ttu-id="22c2c-130">查看定义规则的样式表</span><span class="sxs-lookup"><span data-stu-id="22c2c-130">Viewing the stylesheet where a rule is defined</span></span>  
:::image-end:::  

### <a name="view-only-the-css-that-is-actually-applied-to-an-element"></a><span data-ttu-id="22c2c-131">仅查看实际应用于元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="22c2c-131">View only the CSS that is actually applied to an element</span></span>  

<span data-ttu-id="22c2c-132">**“样式”** 面板显示应用于元素的所有规则，包括已覆盖声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-132">The **Styles** panel shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="22c2c-133">当你对覆盖声明不感兴趣时，使用 **“计算”** 面板仅查看实际应用于元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="22c2c-133">When you are not interested in overridden declarations, use the **Computed** panel to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="22c2c-134">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-134">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="22c2c-135">导航到 **“元素”** 工具中的 **“计算”** 面板。</span><span class="sxs-lookup"><span data-stu-id="22c2c-135">Navigate to the **Computed** panel in the **Elements** tool.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-136">在宽的 DevTools 窗口中，**“计算”** 面板不存在。</span><span class="sxs-lookup"><span data-stu-id="22c2c-136">On a wide DevTools window, the **Computed** panel does not exist.</span></span>  <span data-ttu-id="22c2c-137">**“计算”** 面板中的内容会在 **“样式”** 面板中显示。</span><span class="sxs-lookup"><span data-stu-id="22c2c-137">The contents of the **Computed** panel are shown on the **Styles** panel.</span></span>  

<span data-ttu-id="22c2c-138">继承的属性不透明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-138">Inherited properties are opaque.</span></span>  <span data-ttu-id="22c2c-139">若要显示所有继承的值，请选中 **“显示所有”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="22c2c-139">To display all inherited values, select the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-140">下图中，**“计算”** 面板显示应用于当前所选 `h1` 元素的 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="22c2c-140">In the following figure, the **Computed** panel shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="“计算”面板" lightbox="../media/css-elements-computed-h1.msft.png":::
   <span data-ttu-id="22c2c-142">**“计算”** 面板</span><span class="sxs-lookup"><span data-stu-id="22c2c-142">The **Computed** panel</span></span>  
:::image-end:::  

### <a name="view-css-properties-in-alphabetical-order"></a><span data-ttu-id="22c2c-143">按字母顺序查看 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="22c2c-143">View CSS properties in alphabetical order</span></span>  

<span data-ttu-id="22c2c-144">使用 **“计算”** 面板。</span><span class="sxs-lookup"><span data-stu-id="22c2c-144">Use the **Computed** panel.</span></span>  <span data-ttu-id="22c2c-145">导航到 [仅查看实际应用于元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-145">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-inherited-css-properties"></a><span data-ttu-id="22c2c-146">查看继承的 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="22c2c-146">View inherited CSS properties</span></span>  

<span data-ttu-id="22c2c-147">选中 **“计算”** 面板中的 **“显示所有”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="22c2c-147">Check the **Show All** checkbox in the **Computed** panel.</span></span>  <span data-ttu-id="22c2c-148">导航到 [仅查看实际应用于元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-148">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-the-box-model-for-an-element"></a><span data-ttu-id="22c2c-149">查看元素的框模型</span><span class="sxs-lookup"><span data-stu-id="22c2c-149">View the box model for an element</span></span>  

<span data-ttu-id="22c2c-150">若要查看元素的 [框模型][MDNBoxModel]，请导航到 **“样式”** 面板。</span><span class="sxs-lookup"><span data-stu-id="22c2c-150">To view [the box model][MDNBoxModel] of an element, navigate to the **Styles** panel.</span></span>  <span data-ttu-id="22c2c-151">如果 DevTools 窗口较窄，则 **框模型** 图位于面板的底部。</span><span class="sxs-lookup"><span data-stu-id="22c2c-151">If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the panel.</span></span>  

<span data-ttu-id="22c2c-152">选择并编辑值以更改值。</span><span class="sxs-lookup"><span data-stu-id="22c2c-152">Choose and edit on a value to change a value.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-153">下图中，**“样式”** 面板中的 **“框模型”** 图显示当前所选 `h1` 元素的框模型。</span><span class="sxs-lookup"><span data-stu-id="22c2c-153">In the following figure, the **Box Model** diagram in the **Styles** panel shows the box model for the currently selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="框模型图" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   <span data-ttu-id="22c2c-155">**“框模型”** 图</span><span class="sxs-lookup"><span data-stu-id="22c2c-155">The **Box Model** diagram</span></span>  
:::image-end:::  

### <a name="search-and-filter-the-css-of-an-element"></a><span data-ttu-id="22c2c-156">搜索和筛选元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="22c2c-156">Search and filter the CSS of an element</span></span>  

<span data-ttu-id="22c2c-157">使用 **“样式”** 和 **“计算”** 面板上的 **“过滤器”** 文本框来搜索特定的 CSS 属性或值。</span><span class="sxs-lookup"><span data-stu-id="22c2c-157">Use the **Filter** text box on the **Styles** and **Computed** panels to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="22c2c-158">若要在 **“计算”** 面板中同时搜索继承属性，请选中 **“全部显示”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="22c2c-158">To also search inherited properties in the **Computed** panel, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-159">下图中，筛选 **“样式”** 面板为只显示包含搜索查询的 `color` 规则。</span><span class="sxs-lookup"><span data-stu-id="22c2c-159">In the following figure, the **Styles** panel is filtered to only show rules that include the search query `color`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="筛选“样式”面板" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   <span data-ttu-id="22c2c-161">筛选 **“样式”** 面板</span><span class="sxs-lookup"><span data-stu-id="22c2c-161">Filter the **Styles** panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="22c2c-162">下图中，筛选 **“计算”** 面板以仅显示包含搜索查询 `100%` 的声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-162">In the following figure, the **Computed** panel is filtered to only show declarations that include the search query `100%`.</span></span>  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="筛选 “计算” 面板" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   <span data-ttu-id="22c2c-164">筛选 **“计算”** 面板</span><span class="sxs-lookup"><span data-stu-id="22c2c-164">Filter the **Computed** panel</span></span>  
:::image-end:::  

### <a name="toggle-a-pseudo-class"></a><span data-ttu-id="22c2c-165">切换伪类</span><span class="sxs-lookup"><span data-stu-id="22c2c-165">Toggle a pseudo-class</span></span>  

<span data-ttu-id="22c2c-166">完成以下操作以切换如 `:active`、`:focus`、`:hover` 或 `:visited` 的伪类。</span><span class="sxs-lookup"><span data-stu-id="22c2c-166">Complete the following actions to toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`.</span></span>  

1.  <span data-ttu-id="22c2c-167">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-167">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="22c2c-168">在 **“元素”** 工具上，导航到 **“样式”** 面板。</span><span class="sxs-lookup"><span data-stu-id="22c2c-168">On the **Elements** tool, navigate to the **Styles** panel.</span></span>  
1.  <span data-ttu-id="22c2c-169">选择 **:hov**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-169">Choose **:hov**.</span></span>  
1.  <span data-ttu-id="22c2c-170">勾选要启用的伪类。</span><span class="sxs-lookup"><span data-stu-id="22c2c-170">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-171">下图中，切换 `:hover` 伪类。</span><span class="sxs-lookup"><span data-stu-id="22c2c-171">In the following figure, toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="22c2c-172">在视区中验证 `background-color: cornflowerblue` 声明是否正应用于该元素上，即使该元素实际上并未悬停。</span><span class="sxs-lookup"><span data-stu-id="22c2c-172">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切换 :hover 伪类" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   <span data-ttu-id="22c2c-174">切换 `:hover` 伪类</span><span class="sxs-lookup"><span data-stu-id="22c2c-174">Toggle the `:hover` pseudo-class</span></span>  
:::image-end:::  

<span data-ttu-id="22c2c-175">对于交互式教程，请导航到 [“向类添加伪静态”][DevToolsCSSGetStartedAddPseudoState]。</span><span class="sxs-lookup"><span data-stu-id="22c2c-175">For an interactive tutorial, navigate to [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState].</span></span>  

### <a name="view-a-page-in-print-mode"></a><span data-ttu-id="22c2c-176">在打印模式下查看页面</span><span class="sxs-lookup"><span data-stu-id="22c2c-176">View a page in print mode</span></span>  

<span data-ttu-id="22c2c-177">在打印模式下完成以下操作以查看页面。</span><span class="sxs-lookup"><span data-stu-id="22c2c-177">Complete the following actions to view a page in print mode.</span></span>  

1.  <span data-ttu-id="22c2c-178">[打开“命令”菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="22c2c-178">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="22c2c-179">开始键入 `Rendering` 并选择 `Show Rendering`。</span><span class="sxs-lookup"><span data-stu-id="22c2c-179">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="22c2c-180">对于 **“模拟 CSS 媒体”** 下拉菜单中，请选择 **打印**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-180">For the **Emulate CSS Media** dropdown, choose **print**.</span></span>  

### <a name="view-used-and-unused-css-with-the-coverage-tool"></a><span data-ttu-id="22c2c-181">使用覆盖工具查看已使用和未使用的 CSS</span><span class="sxs-lookup"><span data-stu-id="22c2c-181">View used and unused CSS with the Coverage tool</span></span>  

<span data-ttu-id="22c2c-182">**“覆盖”** 工具显示页面实际使用 CSS。</span><span class="sxs-lookup"><span data-stu-id="22c2c-182">The **Coverage** tool shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="22c2c-183">在 DevTools 处于焦点时，选择 `Control`+`Shift`+`P` \(Windows，Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 时 [打开命令菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="22c2c-183">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to [open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="22c2c-184">开始键入 `coverage` 并选择 **“显示范围”**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-184">Start typing `coverage` and choose **Show Coverage**.</span></span>  <span data-ttu-id="22c2c-185">出现 **“覆盖”** 工具。</span><span class="sxs-lookup"><span data-stu-id="22c2c-185">The **Coverage** tool appears.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="从命令菜单中打开 “覆盖” 工具" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             <span data-ttu-id="22c2c-187">从 **“命令”** 菜单中打开 **“覆盖”** 工具</span><span class="sxs-lookup"><span data-stu-id="22c2c-187">Open the **Coverage** tool from the **Command Menu**</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="“覆盖”工具" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             <span data-ttu-id="22c2c-189">**覆盖**工具</span><span class="sxs-lookup"><span data-stu-id="22c2c-189">The **Coverage** tool</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="22c2c-190">选择 **“开始仪表覆盖并刷新页面”** \(![开始仪表覆盖并刷新页面](../media/refresh-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-190">Choose **Start instrumenting coverage and refresh the page** \(![Start instrumenting coverage and refresh the page](../media/refresh-icon.msft.png)\).</span></span>  <span data-ttu-id="22c2c-191">页面将刷新，**“覆盖”** 工具将提供浏览器加载的每个文件中使用多少 CSS \(和 JavaScript\) 的概述。</span><span class="sxs-lookup"><span data-stu-id="22c2c-191">The page refreshes and the **Coverage** tool provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="22c2c-192">绿色表示已使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="22c2c-192">Green represents used CSS.</span></span>  <span data-ttu-id="22c2c-193">红色表示未使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="22c2c-193">Red represents unused CSS.</span></span>  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="已使用的和未使用的 CSS (和JavaScript) 的概述" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       <span data-ttu-id="22c2c-195">已使用的和未使用的 CSS \(和JavaScript\) 的概述</span><span class="sxs-lookup"><span data-stu-id="22c2c-195">An overview of how much CSS \(and JavaScript\) is used and unused</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="22c2c-196">若要显示已使用 CSS 的逐行分类，请选择 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="22c2c-196">To display a line-by-line breakdown of what CSS is used, choose a CSS file.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="22c2c-197">在下图中， `b66bc881.site-ltr.css` 的 145 至 147 行和 149 至 151 行未使用，而 163 至 166 行已使用。</span><span class="sxs-lookup"><span data-stu-id="22c2c-197">In the following figure, lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="已使用和未使用 CSS 的逐行细目" lightbox="../media/css-sources-css-coverage.msft.png":::
       <span data-ttu-id="22c2c-199">已使用和未使用 CSS 的逐行细目</span><span class="sxs-lookup"><span data-stu-id="22c2c-199">A line-by-line breakdown of used and unused CSS</span></span>  
    :::image-end:::  
    
### <a name="force-print-preview-mode"></a><span data-ttu-id="22c2c-200">强制打印预览模式</span><span class="sxs-lookup"><span data-stu-id="22c2c-200">Force print preview mode</span></span>  

<span data-ttu-id="22c2c-201">导航到 [“强制 DevTools 进入打印预览模式”][DevToolsCssPrintPreview]。</span><span class="sxs-lookup"><span data-stu-id="22c2c-201">Navigate to [Force DevTools into Print Preview mode][DevToolsCssPrintPreview].</span></span>  

## <a name="change-css"></a><span data-ttu-id="22c2c-202">更改 CSS</span><span class="sxs-lookup"><span data-stu-id="22c2c-202">Change CSS</span></span>  

<!-- todo s/CSS declaration/declaration/ -->  

### <a name="add-a-css-declaration-to-an-element"></a><span data-ttu-id="22c2c-203">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-203">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="22c2c-204">声明顺序会影响元素的样式，请使用以下列表来帮助以不同方式添加声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-204">The order of declarations affects how an element is styled, use the following list to help you add declarations in different ways.</span></span>  

*   <span data-ttu-id="22c2c-205">[添加内联声明](#add-an-inline-declaration)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-205">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="22c2c-206">相当于向元素的 HTML 添加 `style` 属性。</span><span class="sxs-lookup"><span data-stu-id="22c2c-206">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="22c2c-207">[向“样式规则”添加声明](#add-a-declaration-to-a-style-rule)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-207">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="22c2c-208">该使用什么工作流?</span><span class="sxs-lookup"><span data-stu-id="22c2c-208">What workflow should you use?</span></span>** <span data-ttu-id="22c2c-209">多数情况下，可能需要使用内联声明工作流。</span><span class="sxs-lookup"><span data-stu-id="22c2c-209">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="22c2c-210">内联声明具有比外部声明更高的特定性，因此内联工作流可确保更改在预期元素中生效。</span><span class="sxs-lookup"><span data-stu-id="22c2c-210">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in your expected element.</span></span>  <span data-ttu-id="22c2c-211">有关特定性详细信息，请导航到 [“选择器类型”][MDNSelectorTypes]。</span><span class="sxs-lookup"><span data-stu-id="22c2c-211">For more information about specificity, navigate to [Selector Types][MDNSelectorTypes].</span></span>  

<span data-ttu-id="22c2c-212">如果要调试任何元素样式，并且需要专门测试在不同位置定义声明时的情况，请使用其他工作流。</span><span class="sxs-lookup"><span data-stu-id="22c2c-212">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <a name="add-an-inline-declaration"></a><span data-ttu-id="22c2c-213">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-213">Add an inline declaration</span></span>  

<span data-ttu-id="22c2c-214">完成以下操作以添加内联声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-214">Complete the following actions to add an inline declaration.</span></span>  

1.  <span data-ttu-id="22c2c-215">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-215">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="22c2c-216">在 **“样式”** 窗格中，选择 **element.style** 的括号。</span><span class="sxs-lookup"><span data-stu-id="22c2c-216">In the **Styles** pane, choose between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="22c2c-217">光标聚焦，以允许输入文本。</span><span class="sxs-lookup"><span data-stu-id="22c2c-217">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="22c2c-218">输入属性名称，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="22c2c-218">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="22c2c-219">为该属性输入有效值，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="22c2c-219">Enter a valid value for that property and select `Enter`.</span></span>  <span data-ttu-id="22c2c-220">在 **DOM 树** 中，验证 `style` 属性是否已添加到元素中。</span><span class="sxs-lookup"><span data-stu-id="22c2c-220">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-221">下图中，`margin-top` 和 `background-color` 属性已应用于所选元素。</span><span class="sxs-lookup"><span data-stu-id="22c2c-221">In the following figure, the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="22c2c-222">在 **DOM 树** 验证声明是否反映在元素的 `style` 属性中。</span><span class="sxs-lookup"><span data-stu-id="22c2c-222">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="添加内联声明" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   <span data-ttu-id="22c2c-224">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-224">Add inline declarations</span></span>  
:::image-end:::  

#### <a name="add-a-declaration-to-a-style-rule"></a><span data-ttu-id="22c2c-225">向样式规则添加声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-225">Add a declaration to a style rule</span></span>  

<span data-ttu-id="22c2c-226">完成以下操作以将声明添加到现有样式规则中。</span><span class="sxs-lookup"><span data-stu-id="22c2c-226">Complete the following actions to add a declaration to an existing style rule.</span></span>  

1.  <span data-ttu-id="22c2c-227">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-227">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="22c2c-228">在 **“样式”** 窗格中，选择要添加声明的样式规则括号。</span><span class="sxs-lookup"><span data-stu-id="22c2c-228">In the **Styles** pane, choose between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="22c2c-229">光标聚焦，以允许输入文本。</span><span class="sxs-lookup"><span data-stu-id="22c2c-229">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="22c2c-230">输入属性名称，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="22c2c-230">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="22c2c-231">为该属性输入有效值，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="22c2c-231">Enter a valid value for that property and select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="正在向样式规则添加声明" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   <span data-ttu-id="22c2c-233">将 `border-bottom-style:groove` 声明添加到样式规则</span><span class="sxs-lookup"><span data-stu-id="22c2c-233">Add the `border-bottom-style:groove` declaration to a style rule</span></span>  
:::image-end:::  

### <a name="change-a-declaration-name-or-value"></a><span data-ttu-id="22c2c-234">更改声明名称或值</span><span class="sxs-lookup"><span data-stu-id="22c2c-234">Change a declaration name or value</span></span>  

<span data-ttu-id="22c2c-235">选择并编辑声明的名称或值以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="22c2c-235">Choose and edit the name or value of a declaration to change it.</span></span>  <span data-ttu-id="22c2c-236">对于通过 `0.1`、`1`、`10` 或 `100` 单位以快速递增或递减值的快捷方式，请导航到 [“使用键盘快捷方式更改声明值”](#change-declaration-values-with-keyboard-shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-236">For shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units, navigate to [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts).</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="更改声明值" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   <span data-ttu-id="22c2c-238">更改 `border-bottom-style` 声明值</span><span class="sxs-lookup"><span data-stu-id="22c2c-238">Change the value of the `border-bottom-style` declaration</span></span>  
:::image-end:::  

### <a name="change-declaration-values-with-keyboard-shortcuts"></a><span data-ttu-id="22c2c-239">使用键盘快捷方式更改声明值</span><span class="sxs-lookup"><span data-stu-id="22c2c-239">Change declaration values with keyboard shortcuts</span></span>  

<span data-ttu-id="22c2c-240">编辑声明的值时，可以使用以下键盘快捷方式将该值增加特定的数量。</span><span class="sxs-lookup"><span data-stu-id="22c2c-240">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a specific amount.</span></span>  

*   <span data-ttu-id="22c2c-241">选择`Alt`+`Up` \(Windows，Linux\) 或 `Option`+`Up` \(macOS\) 按 `0.1` 增量。</span><span class="sxs-lookup"><span data-stu-id="22c2c-241">Select `Alt`+`Up` \(Windows, Linux\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="22c2c-242">选择 `Up` 按 `1` 改变数值，如果当前值介于 `-1` 和 `1` 之间则按 `0.1` 改变。</span><span class="sxs-lookup"><span data-stu-id="22c2c-242">Select `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="22c2c-243">选择 `Shift`+`Up` 按 `10` 增量。</span><span class="sxs-lookup"><span data-stu-id="22c2c-243">Select `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="22c2c-244">选择 `Shift`+`Page Up` \(Windows，Linux\) 或 `Shift`+`Command`+`Up` \(macOS\) 按 `100` 增量。</span><span class="sxs-lookup"><span data-stu-id="22c2c-244">Select `Shift`+`Page Up` \(Windows, Linux\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="22c2c-245">缩量也可以。</span><span class="sxs-lookup"><span data-stu-id="22c2c-245">Decrementing also works.</span></span>  <span data-ttu-id="22c2c-246">只要把上面提到的 `Up` 的每个实例都换成 `Down` 即可。</span><span class="sxs-lookup"><span data-stu-id="22c2c-246">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <a name="add-a-class-to-an-element"></a><span data-ttu-id="22c2c-247">向元素添加类</span><span class="sxs-lookup"><span data-stu-id="22c2c-247">Add a class to an element</span></span>  

<span data-ttu-id="22c2c-248">完成以下操作以向元素添加类。</span><span class="sxs-lookup"><span data-stu-id="22c2c-248">Complete the following actions to add a class to an element.</span></span>  

1.  <span data-ttu-id="22c2c-249">在 \*\* DOM 树\*\* 中 [选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-249">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="22c2c-250">选择 **.cls**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-250">Choose **.cls**.</span></span>  
1.  <span data-ttu-id="22c2c-251">在 **“添加新类”** 文本框中输入类的名称。</span><span class="sxs-lookup"><span data-stu-id="22c2c-251">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="22c2c-252">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="22c2c-252">Select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="“元素课堂”窗格" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   <span data-ttu-id="22c2c-254">**“元素课堂”** 窗格</span><span class="sxs-lookup"><span data-stu-id="22c2c-254">The **Element Classes** pane</span></span>  
:::image-end:::  

### <a name="toggle-a-class"></a><span data-ttu-id="22c2c-255">切换类</span><span class="sxs-lookup"><span data-stu-id="22c2c-255">Toggle a class</span></span>  

<span data-ttu-id="22c2c-256">完成以下操作以启用或禁用元素上的类。</span><span class="sxs-lookup"><span data-stu-id="22c2c-256">Complete the following actions to enable or disable a class on an element.</span></span>  

1.  <span data-ttu-id="22c2c-257">在 \*\* DOM 树\*\* 中 [选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-257">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="22c2c-258">打开 **“元素类”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="22c2c-258">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="22c2c-259">导航到 [向元素添加类](#add-a-class-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-259">Navigate to [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="22c2c-260">在 **“添加新类”** 文本框下方是应用于特定元素的所有类。</span><span class="sxs-lookup"><span data-stu-id="22c2c-260">Below the **Add New Class** text box are all of the classes applied to the specific element.</span></span>  
1.  <span data-ttu-id="22c2c-261">切换要打开或关闭类旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="22c2c-261">Toggle the checkbox next to the class that you want to turn on or off.</span></span>  

### <a name="add-a-style-rule"></a><span data-ttu-id="22c2c-262">添加样式规则</span><span class="sxs-lookup"><span data-stu-id="22c2c-262">Add a style rule</span></span>  

<span data-ttu-id="22c2c-263">完成以下操作以添加新样式规则。</span><span class="sxs-lookup"><span data-stu-id="22c2c-263">Complete the following actions to add a new style rule.</span></span>  

1.  <span data-ttu-id="22c2c-264">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-264">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="22c2c-265">选择 **“新样式规则”** \(![新样式规则](../media/new-style-rule-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-265">Choose **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\).</span></span>  <span data-ttu-id="22c2c-266">DevTools 在 **element.style** 规则下方插入新规则。</span><span class="sxs-lookup"><span data-stu-id="22c2c-266">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-267">下图中，DevTools 在选择 **“新样式规则”** 后添加 `h1.devsite-page-title` 样式规则。</span><span class="sxs-lookup"><span data-stu-id="22c2c-267">In the following figure, DevTools adds the `h1.devsite-page-title` style rule after you choose **New Style Rule**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="添加新的样式规则" lightbox="../media/css-elements-styles-style-new.msft.png":::
   <span data-ttu-id="22c2c-269">添加新的样式规则</span><span class="sxs-lookup"><span data-stu-id="22c2c-269">Add a new style rule</span></span>  
:::image-end:::  

#### <a name="choose-which-stylesheet-to-add-a-rule-to"></a><span data-ttu-id="22c2c-270">选择要添加规则的样式表</span><span class="sxs-lookup"><span data-stu-id="22c2c-270">Choose which stylesheet to add a rule to</span></span>  

<span data-ttu-id="22c2c-271">[添加新样式规则](#add-a-style-rule)时，选择并按住 **“新样式规则”** \(![新样式规则](../media/new-style-rule-icon.msft.png)\) 以选择要添加样式规则的样式表。</span><span class="sxs-lookup"><span data-stu-id="22c2c-271">When [adding a new style rule](#add-a-style-rule), choose and hold **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\) to choose which stylesheet to add the style rule to.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="选择样式表" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   <span data-ttu-id="22c2c-273">选择样式表</span><span class="sxs-lookup"><span data-stu-id="22c2c-273">Choose a stylesheet</span></span>  
:::image-end:::  

#### <a name="add-a-style-rule-to-a-specific-location"></a><span data-ttu-id="22c2c-274">向特定位置添加样式规则</span><span class="sxs-lookup"><span data-stu-id="22c2c-274">Add a style rule to a specific location</span></span>  

<span data-ttu-id="22c2c-275">完成以下操作以将样式规则添加到 **“样式“** 面板的特定位置。</span><span class="sxs-lookup"><span data-stu-id="22c2c-275">Complete the following actions to add a style rule to a specific location in the **Styles** panel.</span></span>  

1.  <span data-ttu-id="22c2c-276">将鼠标悬停在要添加新样式规则正上方的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-276">Hover on the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="22c2c-277">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-277">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="22c2c-278">选择 **插入“样式规则”** \(![在图标下方插入样式规则](../media/new-style-rule-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-278">Choose **Insert Style Rule Below** \(![Insert Style Rule Below icon](../media/new-style-rule-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="在下方插入样式规则" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **<span data-ttu-id="22c2c-280">在下方插入样式规则</span><span class="sxs-lookup"><span data-stu-id="22c2c-280">Insert Style Rule Below</span></span>**  
:::image-end:::  

### <a name="reveal-the-more-actions-toolbar"></a><span data-ttu-id="22c2c-281">显示“更多操作”工具栏</span><span class="sxs-lookup"><span data-stu-id="22c2c-281">Reveal the More Actions toolbar</span></span>  

<span data-ttu-id="22c2c-282">通过 **“更多操作”** 工具栏，可执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="22c2c-282">The **More Actions** toolbar lets you perform the following actions.</span></span>  

*   <span data-ttu-id="22c2c-283">直接在所关注样式规则下面插入样式规则。</span><span class="sxs-lookup"><span data-stu-id="22c2c-283">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="22c2c-284">向所关注的样式规则添加`background-color`、`color`、`box-shadow` 或 `text-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-284">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="22c2c-285">完成以下操作以显示 **“更多操作”** 工具栏。</span><span class="sxs-lookup"><span data-stu-id="22c2c-285">Complete the following actions to reveal the **More Actions** toolbar.</span></span>  

1.  <span data-ttu-id="22c2c-286">在 **“样式”** 面板中，将鼠标悬停在样式规则上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-286">In the **Styles** panel, hover on a style rule.</span></span>  <span data-ttu-id="22c2c-287">在样式规则部分的右下角显示 **“更多操作”** \(`...`\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-287">**More Actions** \(`...`\) is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="22c2c-288">下图中，将鼠标悬停在 `.header-holder.has-default-focus` 样式规则上，在样式规则部分的右下方会显示出 **“更多操作”**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-288">In the following figure, hover on the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="显示“更多操作”" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       <span data-ttu-id="22c2c-290">显示 **“更多操作”** \(`...`\)</span><span class="sxs-lookup"><span data-stu-id="22c2c-290">Reveal **More Actions** \(`...`\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="22c2c-291">将鼠标停留在 **“更多行动”** \(`...`\) 上，可以看到上面提到的操作。</span><span class="sxs-lookup"><span data-stu-id="22c2c-291">Hover on **More Actions** \(`...`\) to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="22c2c-292">将鼠标悬停在 **“更多动作“** 上，就会显示出 **“下方插入样式规则”** 操作。</span><span class="sxs-lookup"><span data-stu-id="22c2c-292">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="“更多操作”工具栏" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       <span data-ttu-id="22c2c-294">**“更多操作”** 工具栏</span><span class="sxs-lookup"><span data-stu-id="22c2c-294">The **More Actions** toolbar</span></span>  
    :::image-end:::  
    
### <a name="toggle-a-declaration"></a><span data-ttu-id="22c2c-295">切换声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-295">Toggle a declaration</span></span>  

<span data-ttu-id="22c2c-296">完成下面的操作来切换单个声明的开启 (或关闭)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-296">Complete the folllwoing actions to toggle a single declaration on \(or off\).</span></span>  

1.  <span data-ttu-id="22c2c-297">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-297">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="22c2c-298">在 **“样式”** 窗格中，将鼠标悬停在定义声明的规则上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-298">In the **Styles** pane, hover on the rule that defines the declaration.</span></span>  <span data-ttu-id="22c2c-299">每个声明旁边将显示复选框。</span><span class="sxs-lookup"><span data-stu-id="22c2c-299">A checkbox appears next to each declaration.</span></span>  
1.  <span data-ttu-id="22c2c-300">选中 \(或取消选中\) 声明旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="22c2c-300">Check \(or uncheck\) the checkbox next to the declaration.</span></span>  <span data-ttu-id="22c2c-301">取消选中声明时，DevTools 会将它划掉，表示它不再是活跃。</span><span class="sxs-lookup"><span data-stu-id="22c2c-301">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="22c2c-302">下图中，当前选中元素的 `margin-top` 属性已关闭。</span><span class="sxs-lookup"><span data-stu-id="22c2c-302">In the following figure, the `margin-top` property for the currently selected element has been toggled off.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="切换声明" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   <span data-ttu-id="22c2c-304">切换声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-304">Toggle a declaration</span></span>  
:::image-end:::  

### <a name="add-a-background-color-declaration"></a><span data-ttu-id="22c2c-305">添加背景色声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-305">Add a background-color declaration</span></span>  

<span data-ttu-id="22c2c-306">完成以下操作，向元素添加 `background-color` 声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-306">Complete the following actions to add a `background-color` declaration to an element.</span></span>  

1.  <span data-ttu-id="22c2c-307">将鼠标悬停在要添加 `background-color` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-307">Hover on the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="22c2c-308">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-308">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="22c2c-309">选择 **“添加背景色”** \(![添加背景色图标](../media/add-background-color-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-309">Choose **Add Background Color** \(![Add Background Color icon](../media/add-background-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="背景色" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **<span data-ttu-id="22c2c-311">背景色</span><span class="sxs-lookup"><span data-stu-id="22c2c-311">Add Background Color</span></span>**  
:::image-end:::  

### <a name="add-a-color-declaration"></a><span data-ttu-id="22c2c-312">添加颜色声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-312">Add a color declaration</span></span>  

<span data-ttu-id="22c2c-313">完成以下操作，向元素添加 `color` 声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-313">Complete the following actions to add a `color` declaration to an element.</span></span>  

1.  <span data-ttu-id="22c2c-314">将鼠标悬停在要添加 `color` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-314">Hover on the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="22c2c-315">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-315">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="22c2c-316">选择 **“添加颜色”** \(![添加颜色图标](../media/add-color-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-316">Choose **Add Color** \(![Add Color icon](../media/add-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="添加颜色" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **<span data-ttu-id="22c2c-318">添加颜色</span><span class="sxs-lookup"><span data-stu-id="22c2c-318">Add Color</span></span>**  
:::image-end:::  

### <a name="add-a-box-shadow-declaration"></a><span data-ttu-id="22c2c-319">添加框阴影声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-319">Add a box-shadow declaration</span></span>  

<span data-ttu-id="22c2c-320">完成以下操作以向元素添加 `box-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-320">Complete the follwoing actions to add a `box-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="22c2c-321">将鼠标悬停在要添加 `box-shadow` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-321">Hover on the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="22c2c-322">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-322">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="22c2c-323">选择 **添加狂阴影** \(![添加框阴影图标](../media/add-box-shadow-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-323">Choose **Add Box Shadow** \(![Add Box Shadow icon](../media/add-box-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="添加框阴影" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **<span data-ttu-id="22c2c-325">添加框阴影</span><span class="sxs-lookup"><span data-stu-id="22c2c-325">Add Box Shadow</span></span>**  
:::image-end:::  

### <a name="add-a-text-shadow-declaration"></a><span data-ttu-id="22c2c-326">添加文本阴影声明</span><span class="sxs-lookup"><span data-stu-id="22c2c-326">Add a text-shadow declaration</span></span>  

<span data-ttu-id="22c2c-327">完成以下操作，向元素添加 `text-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-327">Complete the following actions to add a `text-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="22c2c-328">将鼠标悬停在要添加 `text-shadow` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-328">Hover on the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="22c2c-329">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-329">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="22c2c-330">选择 **“添加文本阴影”** \(![添加文本阴影图标](../media/add-text-shadow-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-330">Choose **Add Text Shadow** \(![Add Text Shadow icon](../media/add-text-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="添加文字阴影" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **<span data-ttu-id="22c2c-332">添加文字阴影</span><span class="sxs-lookup"><span data-stu-id="22c2c-332">Add Text Shadow</span></span>**  
:::image-end:::  

### <a name="change-colors-with-the-color-picker"></a><span data-ttu-id="22c2c-333">使用颜色选取器更改颜色</span><span class="sxs-lookup"><span data-stu-id="22c2c-333">Change colors with the Color Picker</span></span>  

<span data-ttu-id="22c2c-334">**颜色选取器** 为更改 `color` 和 `background-color` 声明提供 GUI。</span><span class="sxs-lookup"><span data-stu-id="22c2c-334">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="22c2c-335">完成以下操作以打开 **“颜色选取器”**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-335">Complete the following actions to open the **Color Picker**.</span></span>  

1.  <span data-ttu-id="22c2c-336">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-336">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="22c2c-337">在 **“样式”** 面板中，找到 `color`、`background-color` 或要更改的类似声明。</span><span class="sxs-lookup"><span data-stu-id="22c2c-337">In the **Styles** panel, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="22c2c-338">在 `color`、`background-color` 或类似值左侧有个颜色预览的小方块。</span><span class="sxs-lookup"><span data-stu-id="22c2c-338">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="22c2c-339">下图中，`rgba(0, 0, 0, 0.7)` 左侧的小方块是该颜色的预览。</span><span class="sxs-lookup"><span data-stu-id="22c2c-339">In the following figure, the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="颜色预览" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       <span data-ttu-id="22c2c-341">颜色预览</span><span class="sxs-lookup"><span data-stu-id="22c2c-341">Color preview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="22c2c-342">选择预览以打开 **颜色选取器**。</span><span class="sxs-lookup"><span data-stu-id="22c2c-342">Choose the preview to open the **Color Picker**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       <span data-ttu-id="22c2c-344">**颜色选取器**</span><span class="sxs-lookup"><span data-stu-id="22c2c-344">The **Color Picker**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="22c2c-345">下图和列表介绍了了每个 **颜色选取器** 的 UI 元素。</span><span class="sxs-lookup"><span data-stu-id="22c2c-345">The following figure and list descries of each of the UI elements of the **Color Picker**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="颜色选取器，已批注" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   <span data-ttu-id="22c2c-347">**颜色选取器**，已批注</span><span class="sxs-lookup"><span data-stu-id="22c2c-347">The **Color Picker**, annotated</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-348">1</span><span class="sxs-lookup"><span data-stu-id="22c2c-348">1</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-349">色调</span><span class="sxs-lookup"><span data-stu-id="22c2c-349">Shades</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-350">2</span><span class="sxs-lookup"><span data-stu-id="22c2c-350">2</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-351">取色器</span><span class="sxs-lookup"><span data-stu-id="22c2c-351">Eyedropper</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="22c2c-352">有关详细信息，请导航到 [用“取色器“在页面上打样着色](#sample-a-color-off-the-page-with-the-eyedropper)。</span><span class="sxs-lookup"><span data-stu-id="22c2c-352">For more information, navigate to [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-353">3</span><span class="sxs-lookup"><span data-stu-id="22c2c-353">3</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-354">复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="22c2c-354">Copy To Clipboard</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="22c2c-355">将 **“显示值”** 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="22c2c-355">Copy the **Display Value** to your clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-356">4</span><span class="sxs-lookup"><span data-stu-id="22c2c-356">4</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-357">显示值</span><span class="sxs-lookup"><span data-stu-id="22c2c-357">Display Value</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="22c2c-358">颜色的 RGBA、HSLA 或十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="22c2c-358">The RGBA, HSLA, or Hex representation of the color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-359">5</span><span class="sxs-lookup"><span data-stu-id="22c2c-359">5</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-360">调色板</span><span class="sxs-lookup"><span data-stu-id="22c2c-360">Color Palette</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="22c2c-361">选择其中一个方块以更改该方块的颜色。</span><span class="sxs-lookup"><span data-stu-id="22c2c-361">Choose one of the squares to change the color to that square.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-362">6</span><span class="sxs-lookup"><span data-stu-id="22c2c-362">6</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-363">色调</span><span class="sxs-lookup"><span data-stu-id="22c2c-363">Hue</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-364">7</span><span class="sxs-lookup"><span data-stu-id="22c2c-364">7</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-365">不透明度</span><span class="sxs-lookup"><span data-stu-id="22c2c-365">Opacity</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-366">8</span><span class="sxs-lookup"><span data-stu-id="22c2c-366">8</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-367">显示值切换器</span><span class="sxs-lookup"><span data-stu-id="22c2c-367">Display Value Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="22c2c-368">在当前颜色的 RGBA、HSLA 和十六进制表示形式之间切换。</span><span class="sxs-lookup"><span data-stu-id="22c2c-368">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="22c2c-369">9</span><span class="sxs-lookup"><span data-stu-id="22c2c-369">9</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="22c2c-370">调色板切换器</span><span class="sxs-lookup"><span data-stu-id="22c2c-370">Color Palette Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="22c2c-371">在 [“材质设计调色板”][MaterialDesignColorSystem]、“自定义调色板”或“页面颜色调色板”之间切换。</span><span class="sxs-lookup"><span data-stu-id="22c2c-371">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="22c2c-372">DevTools 根据在样式表中所找到的颜色来生成页面调色板。</span><span class="sxs-lookup"><span data-stu-id="22c2c-372">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  
   :::column-end:::
:::row-end:::  

#### <a name="sample-a-color-off-the-page-with-the-eyedropper"></a><span data-ttu-id="22c2c-373">用“取色器“在页面上打样着色</span><span class="sxs-lookup"><span data-stu-id="22c2c-373">Sample a color off the page with the Eyedropper</span></span>  

<span data-ttu-id="22c2c-374">打开 **“颜色选取器”** 时，**“取色器”** \(![取色器](../media/eyedropper-icon.msft.png)\) 默认打开。</span><span class="sxs-lookup"><span data-stu-id="22c2c-374">When you open the **Color Picker**, the **Eyedropper** \(![Eyedropper](../media/eyedropper-icon.msft.png)\) is on by default.</span></span>  <span data-ttu-id="22c2c-375">完成以下操作，可将页面上的所选颜色改为其他颜色。</span><span class="sxs-lookup"><span data-stu-id="22c2c-375">Complete the following actions to change the selected color to some other color on the page.</span></span>  

1.  <span data-ttu-id="22c2c-376">将鼠标悬停在视区中的目标颜色上。</span><span class="sxs-lookup"><span data-stu-id="22c2c-376">Hover on the target color in the viewport.</span></span>  
1.  <span data-ttu-id="22c2c-377">选择以确认。</span><span class="sxs-lookup"><span data-stu-id="22c2c-377">Choose to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="22c2c-378">下图中，**“颜色选取器”** 显示接近黑色的电流 `rgba(0,0,0,0.7)` 颜色值。</span><span class="sxs-lookup"><span data-stu-id="22c2c-378">In the following figure, the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="22c2c-379">特定的颜色应该更改为在你选择后变为当前视区中高亮的黑色版本。</span><span class="sxs-lookup"><span data-stu-id="22c2c-379">The specific color should change to the version of black that is currently highlighted in the viewport after you chose it.</span></span>  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="使用取色器" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       <span data-ttu-id="22c2c-381">使用取色器</span><span class="sxs-lookup"><span data-stu-id="22c2c-381">Using the Eyedropper</span></span>  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="22c2c-382">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="22c2c-382">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令 | Microsoft Docs"  
[DevToolsCSSGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档 | Microsoft Docs"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class " 向类添加伪状态 - 查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "查看元素的 CSS - 查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "强制 Microsoft Edge DevTools 进入打印预览模式(CSS 打印媒体类型) | Microsoft Docs"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#reformat-a-minified-javascript-file-with-pretty-print "重新设置缩小的 JavaScript 文件，并采用非常打印的字体 - 使用调试器|Microsoft Docs"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统 - 材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "框模型 | MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型 - 特异性 | MDN"  

> [!NOTE]
> <span data-ttu-id="22c2c-392">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="22c2c-392">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="22c2c-393">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="22c2c-393">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="22c2c-395">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="22c2c-395">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  