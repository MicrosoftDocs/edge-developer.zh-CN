---
description: 探索 Microsoft Edge DevTools 中用于查看和更改 CSS 的新工作流。
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
ms.openlocfilehash: 84aacbb3961f6b8f6e9a0bda8823fecbbb26ec25
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439301"
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

# <a name="css-reference"></a><span data-ttu-id="b000e-104">CSS 参考</span><span class="sxs-lookup"><span data-stu-id="b000e-104">CSS reference</span></span>  

<span data-ttu-id="b000e-105">在以下与查看和更改 CSS 相关的 Microsoft Edge DevTools 功能综合参考中发现新的工作流。</span><span class="sxs-lookup"><span data-stu-id="b000e-105">Discover new workflows in the following comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="b000e-106">若要了解基础知识，请导航到 [“查看和更改 CSS 入门”][DevToolsCSSGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="b000e-106">To learn the basics, navigate to [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <a name="choose-an-element"></a><span data-ttu-id="b000e-107">选择元素</span><span class="sxs-lookup"><span data-stu-id="b000e-107">Choose an element</span></span>  

<span data-ttu-id="b000e-108">DevTools **元素** 工具可用于一次查看或更改一个元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="b000e-108">The **Elements** tool of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="b000e-109">所选元素在 **“DOM 树”** 上突出显示。</span><span class="sxs-lookup"><span data-stu-id="b000e-109">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="b000e-110">元素的样式显示在 **“样式”** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="b000e-110">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="b000e-111">有关教程，请导航到 [查看元素的 CSS][DevToolsCSSGetStartedTutorial]。</span><span class="sxs-lookup"><span data-stu-id="b000e-111">For a tutorial, navigate to [View the CSS for an element][DevToolsCSSGetStartedTutorial].</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-112">下图中，**“DOM 树”** 中突出显示的 `h1` 元素就是所选元素。</span><span class="sxs-lookup"><span data-stu-id="b000e-112">In the following figure, the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="b000e-113">在右侧的样式窗格中显示了元素的 **“样式”**。</span><span class="sxs-lookup"><span data-stu-id="b000e-113">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="b000e-114">在左侧，该元素在视区中突出显示，但只是因为当前在 **“DOM 树”** 中鼠标正悬停在它上方。</span><span class="sxs-lookup"><span data-stu-id="b000e-114">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-h1.msft.png":::
   <span data-ttu-id="b000e-116">所选元素的示例</span><span class="sxs-lookup"><span data-stu-id="b000e-116">An example of a selected element</span></span>  
:::image-end:::  

<span data-ttu-id="b000e-117">使用以下操作之一选择元素。</span><span class="sxs-lookup"><span data-stu-id="b000e-117">Use one the following actions to select an element.</span></span>  

*   <span data-ttu-id="b000e-118">在你的视区中，将鼠标悬停在元素上，打开上下文菜单 \(右键单击)，然后选择**检查**。</span><span class="sxs-lookup"><span data-stu-id="b000e-118">In your viewport, hover on the element, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
*   <span data-ttu-id="b000e-119">在 DevTools 中，选择 **“选择元素”** \(![“选择元素”](../media/select-an-element-icon.msft.png)\) 或选择 `Control`+`Shift`+`C` \(Windows，Linux\) 或 `Command`+`Shift`+`C` \(macOS\)，然后在视区中选择该元素。</span><span class="sxs-lookup"><span data-stu-id="b000e-119">In DevTools, choose **Select an element** \(![Select an element](../media/select-an-element-icon.msft.png)\) or select `Control`+`Shift`+`C` \(Windows, Linux\) or `Command`+`Shift`+`C` \(macOS\), and then choose the element in the viewport.</span></span>  
*   <span data-ttu-id="b000e-120">在 DevTools 中，选择 **“DOM 树”** 中的元素。</span><span class="sxs-lookup"><span data-stu-id="b000e-120">In DevTools, choose the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="b000e-121">在 DevTools 中，运行一个查询 (如在 **控制台** 中的 `document.querySelector('p')`)，将鼠标悬停在结果上，打开上下文菜单 \(右键单击\)，然后选择 **“在元素面板上显示 “**。</span><span class="sxs-lookup"><span data-stu-id="b000e-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, hover on the result, open the contextual menu \(right-click\), and choose **Reveal in Elements panel**.</span></span>  

## <a name="view-css"></a><span data-ttu-id="b000e-122">查看 CSS</span><span class="sxs-lookup"><span data-stu-id="b000e-122">View CSS</span></span>  

### <a name="view-the-external-stylesheet-where-a-rule-is-defined"></a><span data-ttu-id="b000e-123">查看已定义规则的外部样式表</span><span class="sxs-lookup"><span data-stu-id="b000e-123">View the external stylesheet where a rule is defined</span></span>  

<span data-ttu-id="b000e-124">在 **“样式”** 窗格中，选择 CSS 规则旁边的链接，以打开定义该规则的外部样式表。</span><span class="sxs-lookup"><span data-stu-id="b000e-124">In the **Styles** pane, choose the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  

<span data-ttu-id="b000e-125">如果是缩小样式表，请导航到 [使缩小文件可读][DevToolsJavascriptReferenceFormat]。</span><span class="sxs-lookup"><span data-stu-id="b000e-125">If the stylesheet is minified, navigate to [Make a minified file readable][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-126">在下图中，当你选择 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 后，将会带你到定义了 `.content h1:first-of-type` CSS 规则的 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 行2。</span><span class="sxs-lookup"><span data-stu-id="b000e-126">In the following figure, after you choose `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` you are taken to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="查看定义规则的样式表" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  <span data-ttu-id="b000e-128">查看定义规则的样式表</span><span class="sxs-lookup"><span data-stu-id="b000e-128">Viewing the stylesheet where a rule is defined</span></span>  
:::image-end:::  

### <a name="view-only-the-css-that-is-actually-applied-to-an-element"></a><span data-ttu-id="b000e-129">仅查看实际应用于元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="b000e-129">View only the CSS that is actually applied to an element</span></span>  

<span data-ttu-id="b000e-130">**“样式”** 面板显示应用于元素的所有规则，包括已覆盖声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-130">The **Styles** panel shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="b000e-131">当你对覆盖声明不感兴趣时，使用 **“计算”** 面板仅查看实际应用于元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="b000e-131">When you are not interested in overridden declarations, use the **Computed** panel to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="b000e-132">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-132">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="b000e-133">导航到 **“元素”** 工具中的 **“计算”** 面板。</span><span class="sxs-lookup"><span data-stu-id="b000e-133">Navigate to the **Computed** panel in the **Elements** tool.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-134">在宽的 DevTools 窗口中，**“计算”** 面板不存在。</span><span class="sxs-lookup"><span data-stu-id="b000e-134">On a wide DevTools window, the **Computed** panel does not exist.</span></span>  <span data-ttu-id="b000e-135">**“计算”** 面板中的内容会在 **“样式”** 面板中显示。</span><span class="sxs-lookup"><span data-stu-id="b000e-135">The contents of the **Computed** panel are shown on the **Styles** panel.</span></span>  

<span data-ttu-id="b000e-136">继承的属性不透明。</span><span class="sxs-lookup"><span data-stu-id="b000e-136">Inherited properties are opaque.</span></span>  <span data-ttu-id="b000e-137">若要显示所有继承的值，请选中 **“显示所有”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b000e-137">To display all inherited values, select the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-138">下图中，**“计算”** 面板显示应用于当前所选 `h1` 元素的 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="b000e-138">In the following figure, the **Computed** panel shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="“计算”面板" lightbox="../media/css-elements-computed-h1.msft.png":::
   <span data-ttu-id="b000e-140">**“计算”** 面板</span><span class="sxs-lookup"><span data-stu-id="b000e-140">The **Computed** panel</span></span>  
:::image-end:::  

### <a name="view-css-properties-in-alphabetical-order"></a><span data-ttu-id="b000e-141">按字母顺序查看 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="b000e-141">View CSS properties in alphabetical order</span></span>  

<span data-ttu-id="b000e-142">使用 **“计算”** 面板。</span><span class="sxs-lookup"><span data-stu-id="b000e-142">Use the **Computed** panel.</span></span>  <span data-ttu-id="b000e-143">导航到 [仅查看实际应用于元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-143">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-inherited-css-properties"></a><span data-ttu-id="b000e-144">查看继承的 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="b000e-144">View inherited CSS properties</span></span>  

<span data-ttu-id="b000e-145">选中 **“计算”** 面板中的 **“显示所有”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b000e-145">Check the **Show All** checkbox in the **Computed** panel.</span></span>  <span data-ttu-id="b000e-146">导航到 [仅查看实际应用于元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-146">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-the-box-model-for-an-element"></a><span data-ttu-id="b000e-147">查看元素的框模型</span><span class="sxs-lookup"><span data-stu-id="b000e-147">View the box model for an element</span></span>  

<span data-ttu-id="b000e-148">若要查看元素的 [框模型][MDNBoxModel]，请导航到 **“样式”** 面板。</span><span class="sxs-lookup"><span data-stu-id="b000e-148">To view [the box model][MDNBoxModel] of an element, navigate to the **Styles** panel.</span></span>  <span data-ttu-id="b000e-149">如果 DevTools 窗口较窄，则 **框模型** 图位于面板的底部。</span><span class="sxs-lookup"><span data-stu-id="b000e-149">If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the panel.</span></span>  

<span data-ttu-id="b000e-150">选择并编辑值以更改值。</span><span class="sxs-lookup"><span data-stu-id="b000e-150">Choose and edit on a value to change a value.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-151">下图中，**“样式”** 面板中的 **“框模型”** 图显示当前所选 `h1` 元素的框模型。</span><span class="sxs-lookup"><span data-stu-id="b000e-151">In the following figure, the **Box Model** diagram in the **Styles** panel shows the box model for the currently selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="框模型图" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   <span data-ttu-id="b000e-153">**“框模型”** 图</span><span class="sxs-lookup"><span data-stu-id="b000e-153">The **Box Model** diagram</span></span>  
:::image-end:::  

### <a name="search-and-filter-the-css-of-an-element"></a><span data-ttu-id="b000e-154">搜索和筛选元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="b000e-154">Search and filter the CSS of an element</span></span>  

<span data-ttu-id="b000e-155">使用 **“样式”** 和 **“计算”** 面板上的 **“过滤器”** 文本框来搜索特定的 CSS 属性或值。</span><span class="sxs-lookup"><span data-stu-id="b000e-155">Use the **Filter** text box on the **Styles** and **Computed** panels to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="b000e-156">若要在 **“计算”** 面板中同时搜索继承属性，请选中 **“全部显示”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b000e-156">To also search inherited properties in the **Computed** panel, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-157">下图中，筛选 **“样式”** 面板为只显示包含搜索查询的 `color` 规则。</span><span class="sxs-lookup"><span data-stu-id="b000e-157">In the following figure, the **Styles** panel is filtered to only show rules that include the search query `color`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="筛选“样式”面板" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   <span data-ttu-id="b000e-159">筛选 **“样式”** 面板</span><span class="sxs-lookup"><span data-stu-id="b000e-159">Filter the **Styles** panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b000e-160">下图中，筛选 **“计算”** 面板以仅显示包含搜索查询 `100%` 的声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-160">In the following figure, the **Computed** panel is filtered to only show declarations that include the search query `100%`.</span></span>  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="筛选 “计算” 面板" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   <span data-ttu-id="b000e-162">筛选 **“计算”** 面板</span><span class="sxs-lookup"><span data-stu-id="b000e-162">Filter the **Computed** panel</span></span>  
:::image-end:::  

### <a name="toggle-a-pseudo-class"></a><span data-ttu-id="b000e-163">切换伪类</span><span class="sxs-lookup"><span data-stu-id="b000e-163">Toggle a pseudo-class</span></span>  

<span data-ttu-id="b000e-164">完成以下操作以切换如 `:active`、`:focus`、`:hover` 或 `:visited` 的伪类。</span><span class="sxs-lookup"><span data-stu-id="b000e-164">Complete the following actions to toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`.</span></span>  

1.  <span data-ttu-id="b000e-165">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-165">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="b000e-166">在 **“元素”** 工具上，导航到 **“样式”** 面板。</span><span class="sxs-lookup"><span data-stu-id="b000e-166">On the **Elements** tool, navigate to the **Styles** panel.</span></span>  
1.  <span data-ttu-id="b000e-167">选择 **:hov**。</span><span class="sxs-lookup"><span data-stu-id="b000e-167">Choose **:hov**.</span></span>  
1.  <span data-ttu-id="b000e-168">勾选要启用的伪类。</span><span class="sxs-lookup"><span data-stu-id="b000e-168">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-169">下图中，切换 `:hover` 伪类。</span><span class="sxs-lookup"><span data-stu-id="b000e-169">In the following figure, toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="b000e-170">在视区中验证 `background-color: cornflowerblue` 声明是否正应用于该元素上，即使该元素实际上并未悬停。</span><span class="sxs-lookup"><span data-stu-id="b000e-170">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切换 :hover 伪类" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   <span data-ttu-id="b000e-172">切换 `:hover` 伪类</span><span class="sxs-lookup"><span data-stu-id="b000e-172">Toggle the `:hover` pseudo-class</span></span>  
:::image-end:::  

<span data-ttu-id="b000e-173">对于交互式教程，请导航到 [“向类添加伪静态”][DevToolsCSSGetStartedAddPseudoState]。</span><span class="sxs-lookup"><span data-stu-id="b000e-173">For an interactive tutorial, navigate to [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState].</span></span>  

### <a name="view-a-page-in-print-mode"></a><span data-ttu-id="b000e-174">在打印模式下查看页面</span><span class="sxs-lookup"><span data-stu-id="b000e-174">View a page in print mode</span></span>  

<span data-ttu-id="b000e-175">在打印模式下完成以下操作以查看页面。</span><span class="sxs-lookup"><span data-stu-id="b000e-175">Complete the following actions to view a page in print mode.</span></span>  

1.  <span data-ttu-id="b000e-176">[打开“命令”菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="b000e-176">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="b000e-177">开始键入 `Rendering` 并选择 `Show Rendering`。</span><span class="sxs-lookup"><span data-stu-id="b000e-177">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="b000e-178">对于 **“模拟 CSS 媒体”** 下拉菜单中，请选择 **打印**。</span><span class="sxs-lookup"><span data-stu-id="b000e-178">For the **Emulate CSS Media** dropdown, choose **print**.</span></span>  

### <a name="view-used-and-unused-css-with-the-coverage-tool"></a><span data-ttu-id="b000e-179">使用覆盖工具查看已使用和未使用的 CSS</span><span class="sxs-lookup"><span data-stu-id="b000e-179">View used and unused CSS with the Coverage tool</span></span>  

<span data-ttu-id="b000e-180">**“覆盖”** 工具显示页面实际使用 CSS。</span><span class="sxs-lookup"><span data-stu-id="b000e-180">The **Coverage** tool shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="b000e-181">在 DevTools 处于焦点时，选择 `Control`+`Shift`+`P` \(Windows，Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 时 [打开命令菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="b000e-181">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to [open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="b000e-182">开始键入 `coverage` 并选择 **“显示范围”**。</span><span class="sxs-lookup"><span data-stu-id="b000e-182">Start typing `coverage` and choose **Show Coverage**.</span></span>  <span data-ttu-id="b000e-183">出现 **“覆盖”** 工具。</span><span class="sxs-lookup"><span data-stu-id="b000e-183">The **Coverage** tool appears.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="从命令菜单中打开 “覆盖” 工具" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             <span data-ttu-id="b000e-185">从 **“命令”** 菜单中打开 **“覆盖”** 工具</span><span class="sxs-lookup"><span data-stu-id="b000e-185">Open the **Coverage** tool from the **Command Menu**</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="“覆盖”工具" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             <span data-ttu-id="b000e-187">**覆盖**工具</span><span class="sxs-lookup"><span data-stu-id="b000e-187">The **Coverage** tool</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="b000e-188">选择 **“开始仪表覆盖并刷新页面”** \(![开始仪表覆盖并刷新页面](../media/refresh-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-188">Choose **Start instrumenting coverage and refresh the page** \(![Start instrumenting coverage and refresh the page](../media/refresh-icon.msft.png)\).</span></span>  <span data-ttu-id="b000e-189">页面将刷新，**“覆盖”** 工具将提供浏览器加载的每个文件中使用多少 CSS \(和 JavaScript\) 的概述。</span><span class="sxs-lookup"><span data-stu-id="b000e-189">The page refreshes and the **Coverage** tool provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="b000e-190">绿色表示已使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="b000e-190">Green represents used CSS.</span></span>  <span data-ttu-id="b000e-191">红色表示未使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="b000e-191">Red represents unused CSS.</span></span>  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="已使用的和未使用的 CSS (和JavaScript) 的概述" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       <span data-ttu-id="b000e-193">已使用的和未使用的 CSS \(和JavaScript\) 的概述</span><span class="sxs-lookup"><span data-stu-id="b000e-193">An overview of how much CSS \(and JavaScript\) is used and unused</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="b000e-194">若要显示已使用 CSS 的逐行分类，请选择 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="b000e-194">To display a line-by-line breakdown of what CSS is used, choose a CSS file.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b000e-195">在下图中， `b66bc881.site-ltr.css` 的 145 至 147 行和 149 至 151 行未使用，而 163 至 166 行已使用。</span><span class="sxs-lookup"><span data-stu-id="b000e-195">In the following figure, lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="已使用和未使用 CSS 的逐行细目" lightbox="../media/css-sources-css-coverage.msft.png":::
       <span data-ttu-id="b000e-197">已使用和未使用 CSS 的逐行细目</span><span class="sxs-lookup"><span data-stu-id="b000e-197">A line-by-line breakdown of used and unused CSS</span></span>  
    :::image-end:::  
    
### <a name="force-print-preview-mode"></a><span data-ttu-id="b000e-198">强制打印预览模式</span><span class="sxs-lookup"><span data-stu-id="b000e-198">Force print preview mode</span></span>  

<span data-ttu-id="b000e-199">导航到 [“强制 DevTools 进入打印预览模式”][DevToolsCssPrintPreview]。</span><span class="sxs-lookup"><span data-stu-id="b000e-199">Navigate to [Force DevTools into Print Preview mode][DevToolsCssPrintPreview].</span></span>  

## <a name="change-css"></a><span data-ttu-id="b000e-200">更改 CSS</span><span class="sxs-lookup"><span data-stu-id="b000e-200">Change CSS</span></span>  

<!-- todo s/CSS declaration/declaration/ -->  

### <a name="add-a-css-declaration-to-an-element"></a><span data-ttu-id="b000e-201">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="b000e-201">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="b000e-202">声明顺序会影响元素的样式，请使用以下列表来帮助以不同方式添加声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-202">The order of declarations affects how an element is styled, use the following list to help you add declarations in different ways.</span></span>  

*   <span data-ttu-id="b000e-203">[添加内联声明](#add-an-inline-declaration)。</span><span class="sxs-lookup"><span data-stu-id="b000e-203">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="b000e-204">相当于向元素的 HTML 添加 `style` 属性。</span><span class="sxs-lookup"><span data-stu-id="b000e-204">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="b000e-205">[向“样式规则”添加声明](#add-a-declaration-to-a-style-rule)。</span><span class="sxs-lookup"><span data-stu-id="b000e-205">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="b000e-206">该使用什么工作流?</span><span class="sxs-lookup"><span data-stu-id="b000e-206">What workflow should you use?</span></span>** <span data-ttu-id="b000e-207">多数情况下，可能需要使用内联声明工作流。</span><span class="sxs-lookup"><span data-stu-id="b000e-207">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="b000e-208">内联声明具有比外部声明更高的特定性，因此内联工作流可确保更改在预期元素中生效。</span><span class="sxs-lookup"><span data-stu-id="b000e-208">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in your expected element.</span></span>  <span data-ttu-id="b000e-209">有关特定性详细信息，请导航到 [“选择器类型”][MDNSelectorTypes]。</span><span class="sxs-lookup"><span data-stu-id="b000e-209">For more information about specificity, navigate to [Selector Types][MDNSelectorTypes].</span></span>  

<span data-ttu-id="b000e-210">如果要调试任何元素样式，并且需要专门测试在不同位置定义声明时的情况，请使用其他工作流。</span><span class="sxs-lookup"><span data-stu-id="b000e-210">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <a name="add-an-inline-declaration"></a><span data-ttu-id="b000e-211">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="b000e-211">Add an inline declaration</span></span>  

<span data-ttu-id="b000e-212">完成以下操作以添加内联声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-212">Complete the following actions to add an inline declaration.</span></span>  

1.  <span data-ttu-id="b000e-213">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-213">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="b000e-214">在 **“样式”** 窗格中，选择 **element.style** 的括号。</span><span class="sxs-lookup"><span data-stu-id="b000e-214">In the **Styles** pane, choose between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="b000e-215">光标聚焦，以允许输入文本。</span><span class="sxs-lookup"><span data-stu-id="b000e-215">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="b000e-216">输入属性名称，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b000e-216">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="b000e-217">为该属性输入有效值，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b000e-217">Enter a valid value for that property and select `Enter`.</span></span>  <span data-ttu-id="b000e-218">在 **DOM 树** 中，验证 `style` 属性是否已添加到元素中。</span><span class="sxs-lookup"><span data-stu-id="b000e-218">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-219">下图中，`margin-top` 和 `background-color` 属性已应用于所选元素。</span><span class="sxs-lookup"><span data-stu-id="b000e-219">In the following figure, the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="b000e-220">在 **DOM 树** 验证声明是否反映在元素的 `style` 属性中。</span><span class="sxs-lookup"><span data-stu-id="b000e-220">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="添加内联声明" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   <span data-ttu-id="b000e-222">添加内联声明</span><span class="sxs-lookup"><span data-stu-id="b000e-222">Add inline declarations</span></span>  
:::image-end:::  

#### <a name="add-a-declaration-to-a-style-rule"></a><span data-ttu-id="b000e-223">向样式规则添加声明</span><span class="sxs-lookup"><span data-stu-id="b000e-223">Add a declaration to a style rule</span></span>  

<span data-ttu-id="b000e-224">完成以下操作以将声明添加到现有样式规则中。</span><span class="sxs-lookup"><span data-stu-id="b000e-224">Complete the following actions to add a declaration to an existing style rule.</span></span>  

1.  <span data-ttu-id="b000e-225">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-225">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="b000e-226">在 **“样式”** 窗格中，选择要添加声明的样式规则括号。</span><span class="sxs-lookup"><span data-stu-id="b000e-226">In the **Styles** pane, choose between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="b000e-227">光标聚焦，以允许输入文本。</span><span class="sxs-lookup"><span data-stu-id="b000e-227">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="b000e-228">输入属性名称，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b000e-228">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="b000e-229">为该属性输入有效值，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b000e-229">Enter a valid value for that property and select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="正在向样式规则添加声明" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   <span data-ttu-id="b000e-231">将 `border-bottom-style:groove` 声明添加到样式规则</span><span class="sxs-lookup"><span data-stu-id="b000e-231">Add the `border-bottom-style:groove` declaration to a style rule</span></span>  
:::image-end:::  

### <a name="change-a-declaration-name-or-value"></a><span data-ttu-id="b000e-232">更改声明名称或值</span><span class="sxs-lookup"><span data-stu-id="b000e-232">Change a declaration name or value</span></span>  

<span data-ttu-id="b000e-233">选择并编辑声明的名称或值以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="b000e-233">Choose and edit the name or value of a declaration to change it.</span></span>  <span data-ttu-id="b000e-234">对于通过 `0.1`、`1`、`10` 或 `100` 单位以快速递增或递减值的快捷方式，请导航到 [“使用键盘快捷方式更改声明值”](#change-declaration-values-with-keyboard-shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="b000e-234">For shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units, navigate to [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts).</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="更改声明值" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   <span data-ttu-id="b000e-236">更改 `border-bottom-style` 声明值</span><span class="sxs-lookup"><span data-stu-id="b000e-236">Change the value of the `border-bottom-style` declaration</span></span>  
:::image-end:::  

### <a name="change-declaration-values-with-keyboard-shortcuts"></a><span data-ttu-id="b000e-237">使用键盘快捷方式更改声明值</span><span class="sxs-lookup"><span data-stu-id="b000e-237">Change declaration values with keyboard shortcuts</span></span>  

<span data-ttu-id="b000e-238">编辑声明的值时，可以使用以下键盘快捷方式将该值增加特定的数量。</span><span class="sxs-lookup"><span data-stu-id="b000e-238">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a specific amount.</span></span>  

*   <span data-ttu-id="b000e-239">选择`Alt`+`Up` \(Windows，Linux\) 或 `Option`+`Up` \(macOS\) 按 `0.1` 增量。</span><span class="sxs-lookup"><span data-stu-id="b000e-239">Select `Alt`+`Up` \(Windows, Linux\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="b000e-240">选择 `Up` 按 `1` 改变数值，如果当前值介于 `-1` 和 `1` 之间则按 `0.1` 改变。</span><span class="sxs-lookup"><span data-stu-id="b000e-240">Select `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="b000e-241">选择 `Shift`+`Up` 按 `10` 增量。</span><span class="sxs-lookup"><span data-stu-id="b000e-241">Select `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="b000e-242">选择 `Shift`+`Page Up` \(Windows，Linux\) 或 `Shift`+`Command`+`Up` \(macOS\) 按 `100` 增量。</span><span class="sxs-lookup"><span data-stu-id="b000e-242">Select `Shift`+`Page Up` \(Windows, Linux\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="b000e-243">缩量也可以。</span><span class="sxs-lookup"><span data-stu-id="b000e-243">Decrementing also works.</span></span>  <span data-ttu-id="b000e-244">只要把上面提到的 `Up` 的每个实例都换成 `Down` 即可。</span><span class="sxs-lookup"><span data-stu-id="b000e-244">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <a name="add-a-class-to-an-element"></a><span data-ttu-id="b000e-245">向元素添加类</span><span class="sxs-lookup"><span data-stu-id="b000e-245">Add a class to an element</span></span>  

<span data-ttu-id="b000e-246">完成以下操作以向元素添加类。</span><span class="sxs-lookup"><span data-stu-id="b000e-246">Complete the following actions to add a class to an element.</span></span>  

1.  <span data-ttu-id="b000e-247">在  DOM 树 中 [选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-247">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="b000e-248">选择 **.cls**。</span><span class="sxs-lookup"><span data-stu-id="b000e-248">Choose **.cls**.</span></span>  
1.  <span data-ttu-id="b000e-249">在 **“添加新类”** 文本框中输入类的名称。</span><span class="sxs-lookup"><span data-stu-id="b000e-249">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="b000e-250">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b000e-250">Select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="“元素课堂”窗格" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   <span data-ttu-id="b000e-252">**“元素课堂”** 窗格</span><span class="sxs-lookup"><span data-stu-id="b000e-252">The **Element Classes** pane</span></span>  
:::image-end:::  

### <a name="toggle-a-class"></a><span data-ttu-id="b000e-253">切换类</span><span class="sxs-lookup"><span data-stu-id="b000e-253">Toggle a class</span></span>  

<span data-ttu-id="b000e-254">完成以下操作以启用或禁用元素上的类。</span><span class="sxs-lookup"><span data-stu-id="b000e-254">Complete the following actions to enable or disable a class on an element.</span></span>  

1.  <span data-ttu-id="b000e-255">在  DOM 树 中 [选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-255">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="b000e-256">打开 **“元素类”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="b000e-256">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="b000e-257">导航到 [向元素添加类](#add-a-class-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-257">Navigate to [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="b000e-258">在 **“添加新类”** 文本框下方是应用于特定元素的所有类。</span><span class="sxs-lookup"><span data-stu-id="b000e-258">Below the **Add New Class** text box are all of the classes applied to the specific element.</span></span>  
1.  <span data-ttu-id="b000e-259">切换要打开或关闭类旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="b000e-259">Toggle the checkbox next to the class that you want to turn on or off.</span></span>  

### <a name="add-a-style-rule"></a><span data-ttu-id="b000e-260">添加样式规则</span><span class="sxs-lookup"><span data-stu-id="b000e-260">Add a style rule</span></span>  

<span data-ttu-id="b000e-261">完成以下操作以添加新样式规则。</span><span class="sxs-lookup"><span data-stu-id="b000e-261">Complete the following actions to add a new style rule.</span></span>  

1.  <span data-ttu-id="b000e-262">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-262">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="b000e-263">选择 **“新样式规则”** \(![新样式规则](../media/new-style-rule-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-263">Choose **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\).</span></span>  <span data-ttu-id="b000e-264">DevTools 在 **element.style** 规则下方插入新规则。</span><span class="sxs-lookup"><span data-stu-id="b000e-264">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-265">下图中，DevTools 在选择 **“新样式规则”** 后添加 `h1.devsite-page-title` 样式规则。</span><span class="sxs-lookup"><span data-stu-id="b000e-265">In the following figure, DevTools adds the `h1.devsite-page-title` style rule after you choose **New Style Rule**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="添加新的样式规则" lightbox="../media/css-elements-styles-style-new.msft.png":::
   <span data-ttu-id="b000e-267">添加新的样式规则</span><span class="sxs-lookup"><span data-stu-id="b000e-267">Add a new style rule</span></span>  
:::image-end:::  

#### <a name="choose-which-stylesheet-to-add-a-rule-to"></a><span data-ttu-id="b000e-268">选择要添加规则的样式表</span><span class="sxs-lookup"><span data-stu-id="b000e-268">Choose which stylesheet to add a rule to</span></span>  

<span data-ttu-id="b000e-269">[添加新样式规则](#add-a-style-rule)时，选择并按住 **“新样式规则”** \(![新样式规则](../media/new-style-rule-icon.msft.png)\) 以选择要添加样式规则的样式表。</span><span class="sxs-lookup"><span data-stu-id="b000e-269">When [adding a new style rule](#add-a-style-rule), choose and hold **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\) to choose which stylesheet to add the style rule to.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="选择样式表" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   <span data-ttu-id="b000e-271">选择样式表</span><span class="sxs-lookup"><span data-stu-id="b000e-271">Choose a stylesheet</span></span>  
:::image-end:::  

#### <a name="add-a-style-rule-to-a-specific-location"></a><span data-ttu-id="b000e-272">向特定位置添加样式规则</span><span class="sxs-lookup"><span data-stu-id="b000e-272">Add a style rule to a specific location</span></span>  

<span data-ttu-id="b000e-273">完成以下操作以将样式规则添加到 **“样式“** 面板的特定位置。</span><span class="sxs-lookup"><span data-stu-id="b000e-273">Complete the following actions to add a style rule to a specific location in the **Styles** panel.</span></span>  

1.  <span data-ttu-id="b000e-274">将鼠标悬停在要添加新样式规则正上方的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="b000e-274">Hover on the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="b000e-275">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="b000e-275">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="b000e-276">选择 **插入“样式规则”** \(![在图标下方插入样式规则](../media/new-style-rule-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-276">Choose **Insert Style Rule Below** \(![Insert Style Rule Below icon](../media/new-style-rule-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="在下方插入样式规则" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **<span data-ttu-id="b000e-278">在下方插入样式规则</span><span class="sxs-lookup"><span data-stu-id="b000e-278">Insert Style Rule Below</span></span>**  
:::image-end:::  

### <a name="reveal-the-more-actions-toolbar"></a><span data-ttu-id="b000e-279">显示“更多操作”工具栏</span><span class="sxs-lookup"><span data-stu-id="b000e-279">Reveal the More Actions toolbar</span></span>  

<span data-ttu-id="b000e-280">通过 **“更多操作”** 工具栏，可执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="b000e-280">The **More Actions** toolbar lets you perform the following actions.</span></span>  

*   <span data-ttu-id="b000e-281">直接在所关注样式规则下面插入样式规则。</span><span class="sxs-lookup"><span data-stu-id="b000e-281">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="b000e-282">向所关注的样式规则添加`background-color`、`color`、`box-shadow` 或 `text-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-282">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="b000e-283">完成以下操作以显示 **“更多操作”** 工具栏。</span><span class="sxs-lookup"><span data-stu-id="b000e-283">Complete the following actions to reveal the **More Actions** toolbar.</span></span>  

1.  <span data-ttu-id="b000e-284">在 **“样式”** 面板中，将鼠标悬停在样式规则上。</span><span class="sxs-lookup"><span data-stu-id="b000e-284">In the **Styles** panel, hover on a style rule.</span></span>  <span data-ttu-id="b000e-285">在样式规则部分的右下角显示 **“更多操作”** \(`...`\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-285">**More Actions** \(`...`\) is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b000e-286">下图中，将鼠标悬停在 `.header-holder.has-default-focus` 样式规则上，在样式规则部分的右下方会显示出 **“更多操作”**。</span><span class="sxs-lookup"><span data-stu-id="b000e-286">In the following figure, hover on the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="显示“更多操作”" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       <span data-ttu-id="b000e-288">显示 **“更多操作”** \(`...`\)</span><span class="sxs-lookup"><span data-stu-id="b000e-288">Reveal **More Actions** \(`...`\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b000e-289">将鼠标停留在 **“更多行动”** \(`...`\) 上，可以看到上面提到的操作。</span><span class="sxs-lookup"><span data-stu-id="b000e-289">Hover on **More Actions** \(`...`\) to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b000e-290">将鼠标悬停在 **“更多动作“** 上，就会显示出 **“下方插入样式规则”** 操作。</span><span class="sxs-lookup"><span data-stu-id="b000e-290">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="“更多操作”工具栏" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       <span data-ttu-id="b000e-292">**“更多操作”** 工具栏</span><span class="sxs-lookup"><span data-stu-id="b000e-292">The **More Actions** toolbar</span></span>  
    :::image-end:::  
    
### <a name="toggle-a-declaration"></a><span data-ttu-id="b000e-293">切换声明</span><span class="sxs-lookup"><span data-stu-id="b000e-293">Toggle a declaration</span></span>  

<span data-ttu-id="b000e-294">完成下面的操作来切换单个声明的开启 (或关闭)。</span><span class="sxs-lookup"><span data-stu-id="b000e-294">Complete the folllwoing actions to toggle a single declaration on \(or off\).</span></span>  

1.  <span data-ttu-id="b000e-295">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-295">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="b000e-296">在 **“样式”** 窗格中，将鼠标悬停在定义声明的规则上。</span><span class="sxs-lookup"><span data-stu-id="b000e-296">In the **Styles** pane, hover on the rule that defines the declaration.</span></span>  <span data-ttu-id="b000e-297">每个声明旁边将显示复选框。</span><span class="sxs-lookup"><span data-stu-id="b000e-297">A checkbox appears next to each declaration.</span></span>  
1.  <span data-ttu-id="b000e-298">选中 \(或取消选中\) 声明旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="b000e-298">Check \(or uncheck\) the checkbox next to the declaration.</span></span>  <span data-ttu-id="b000e-299">取消选中声明时，DevTools 会将它划掉，表示它不再是活跃。</span><span class="sxs-lookup"><span data-stu-id="b000e-299">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="b000e-300">下图中，当前选中元素的 `margin-top` 属性已关闭。</span><span class="sxs-lookup"><span data-stu-id="b000e-300">In the following figure, the `margin-top` property for the currently selected element has been toggled off.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="切换声明" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   <span data-ttu-id="b000e-302">切换声明</span><span class="sxs-lookup"><span data-stu-id="b000e-302">Toggle a declaration</span></span>  
:::image-end:::  

### <a name="add-a-background-color-declaration"></a><span data-ttu-id="b000e-303">添加背景色声明</span><span class="sxs-lookup"><span data-stu-id="b000e-303">Add a background-color declaration</span></span>  

<span data-ttu-id="b000e-304">完成以下操作，向元素添加 `background-color` 声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-304">Complete the following actions to add a `background-color` declaration to an element.</span></span>  

1.  <span data-ttu-id="b000e-305">将鼠标悬停在要添加 `background-color` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="b000e-305">Hover on the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="b000e-306">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="b000e-306">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="b000e-307">选择 **“添加背景色”** \(![添加背景色图标](../media/add-background-color-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-307">Choose **Add Background Color** \(![Add Background Color icon](../media/add-background-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="背景色" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **<span data-ttu-id="b000e-309">背景色</span><span class="sxs-lookup"><span data-stu-id="b000e-309">Add Background Color</span></span>**  
:::image-end:::  

### <a name="add-a-color-declaration"></a><span data-ttu-id="b000e-310">添加颜色声明</span><span class="sxs-lookup"><span data-stu-id="b000e-310">Add a color declaration</span></span>  

<span data-ttu-id="b000e-311">完成以下操作，向元素添加 `color` 声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-311">Complete the following actions to add a `color` declaration to an element.</span></span>  

1.  <span data-ttu-id="b000e-312">将鼠标悬停在要添加 `color` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="b000e-312">Hover on the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="b000e-313">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="b000e-313">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="b000e-314">选择 **“添加颜色”** \(![添加颜色图标](../media/add-color-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-314">Choose **Add Color** \(![Add Color icon](../media/add-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="添加颜色" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **<span data-ttu-id="b000e-316">添加颜色</span><span class="sxs-lookup"><span data-stu-id="b000e-316">Add Color</span></span>**  
:::image-end:::  

### <a name="add-a-box-shadow-declaration"></a><span data-ttu-id="b000e-317">添加框阴影声明</span><span class="sxs-lookup"><span data-stu-id="b000e-317">Add a box-shadow declaration</span></span>  

<span data-ttu-id="b000e-318">完成以下操作以向元素添加 `box-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-318">Complete the follwoing actions to add a `box-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="b000e-319">将鼠标悬停在要添加 `box-shadow` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="b000e-319">Hover on the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="b000e-320">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="b000e-320">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="b000e-321">选择 **添加狂阴影** \(![添加框阴影图标](../media/add-box-shadow-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-321">Choose **Add Box Shadow** \(![Add Box Shadow icon](../media/add-box-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="添加框阴影" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **<span data-ttu-id="b000e-323">添加框阴影</span><span class="sxs-lookup"><span data-stu-id="b000e-323">Add Box Shadow</span></span>**  
:::image-end:::  

### <a name="add-a-text-shadow-declaration"></a><span data-ttu-id="b000e-324">添加文本阴影声明</span><span class="sxs-lookup"><span data-stu-id="b000e-324">Add a text-shadow declaration</span></span>  

<span data-ttu-id="b000e-325">完成以下操作，向元素添加 `text-shadow` 声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-325">Complete the following actions to add a `text-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="b000e-326">将鼠标悬停在要添加 `text-shadow` 声明的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="b000e-326">Hover on the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="b000e-327">[显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="b000e-327">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="b000e-328">选择 **“添加文本阴影”** \(![添加文本阴影图标](../media/add-text-shadow-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="b000e-328">Choose **Add Text Shadow** \(![Add Text Shadow icon](../media/add-text-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="添加文字阴影" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **<span data-ttu-id="b000e-330">添加文字阴影</span><span class="sxs-lookup"><span data-stu-id="b000e-330">Add Text Shadow</span></span>**  
:::image-end:::  

### <a name="change-colors-with-the-color-picker"></a><span data-ttu-id="b000e-331">使用颜色选取器更改颜色</span><span class="sxs-lookup"><span data-stu-id="b000e-331">Change colors with the Color Picker</span></span>  

<span data-ttu-id="b000e-332">**颜色选取器** 为更改 `color` 和 `background-color` 声明提供 GUI。</span><span class="sxs-lookup"><span data-stu-id="b000e-332">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="b000e-333">完成以下操作以打开 **“颜色选取器”**。</span><span class="sxs-lookup"><span data-stu-id="b000e-333">Complete the following actions to open the **Color Picker**.</span></span>  

1.  <span data-ttu-id="b000e-334">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="b000e-334">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="b000e-335">在 **“样式”** 面板中，找到 `color`、`background-color` 或要更改的类似声明。</span><span class="sxs-lookup"><span data-stu-id="b000e-335">In the **Styles** panel, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="b000e-336">在 `color`、`background-color` 或类似值左侧有个颜色预览的小方块。</span><span class="sxs-lookup"><span data-stu-id="b000e-336">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b000e-337">下图中，`rgba(0, 0, 0, 0.7)` 左侧的小方块是该颜色的预览。</span><span class="sxs-lookup"><span data-stu-id="b000e-337">In the following figure, the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="颜色预览" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       <span data-ttu-id="b000e-339">颜色预览</span><span class="sxs-lookup"><span data-stu-id="b000e-339">Color preview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b000e-340">选择预览以打开 **颜色选取器**。</span><span class="sxs-lookup"><span data-stu-id="b000e-340">Choose the preview to open the **Color Picker**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       <span data-ttu-id="b000e-342">**颜色选取器**</span><span class="sxs-lookup"><span data-stu-id="b000e-342">The **Color Picker**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="b000e-343">下图和列表介绍了了每个 **颜色选取器** 的 UI 元素。</span><span class="sxs-lookup"><span data-stu-id="b000e-343">The following figure and list descries of each of the UI elements of the **Color Picker**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="颜色选取器，已批注" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   <span data-ttu-id="b000e-345">**颜色选取器**，已批注</span><span class="sxs-lookup"><span data-stu-id="b000e-345">The **Color Picker**, annotated</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-346">1</span><span class="sxs-lookup"><span data-stu-id="b000e-346">1</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-347">色调</span><span class="sxs-lookup"><span data-stu-id="b000e-347">Shades</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-348">2</span><span class="sxs-lookup"><span data-stu-id="b000e-348">2</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-349">取色器</span><span class="sxs-lookup"><span data-stu-id="b000e-349">Eyedropper</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b000e-350">有关详细信息，请导航到 [用“取色器“在页面上打样着色](#sample-a-color-off-the-page-with-the-eyedropper)。</span><span class="sxs-lookup"><span data-stu-id="b000e-350">For more information, navigate to [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-351">3</span><span class="sxs-lookup"><span data-stu-id="b000e-351">3</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-352">复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="b000e-352">Copy To Clipboard</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b000e-353">将 **“显示值”** 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="b000e-353">Copy the **Display Value** to your clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-354">4</span><span class="sxs-lookup"><span data-stu-id="b000e-354">4</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-355">显示值</span><span class="sxs-lookup"><span data-stu-id="b000e-355">Display Value</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b000e-356">颜色的 RGBA、HSLA 或十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="b000e-356">The RGBA, HSLA, or Hex representation of the color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-357">5</span><span class="sxs-lookup"><span data-stu-id="b000e-357">5</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-358">调色板</span><span class="sxs-lookup"><span data-stu-id="b000e-358">Color Palette</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b000e-359">选择其中一个方块以更改该方块的颜色。</span><span class="sxs-lookup"><span data-stu-id="b000e-359">Choose one of the squares to change the color to that square.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-360">6</span><span class="sxs-lookup"><span data-stu-id="b000e-360">6</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-361">色调</span><span class="sxs-lookup"><span data-stu-id="b000e-361">Hue</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-362">7</span><span class="sxs-lookup"><span data-stu-id="b000e-362">7</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-363">不透明度</span><span class="sxs-lookup"><span data-stu-id="b000e-363">Opacity</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-364">8</span><span class="sxs-lookup"><span data-stu-id="b000e-364">8</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-365">显示值切换器</span><span class="sxs-lookup"><span data-stu-id="b000e-365">Display Value Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b000e-366">在当前颜色的 RGBA、HSLA 和十六进制表示形式之间切换。</span><span class="sxs-lookup"><span data-stu-id="b000e-366">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="b000e-367">9</span><span class="sxs-lookup"><span data-stu-id="b000e-367">9</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="b000e-368">调色板切换器</span><span class="sxs-lookup"><span data-stu-id="b000e-368">Color Palette Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b000e-369">在 [“材质设计调色板”][MaterialDesignColorSystem]、“自定义调色板”或“页面颜色调色板”之间切换。</span><span class="sxs-lookup"><span data-stu-id="b000e-369">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="b000e-370">DevTools 根据在样式表中所找到的颜色来生成页面调色板。</span><span class="sxs-lookup"><span data-stu-id="b000e-370">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  
   :::column-end:::
:::row-end:::  

#### <a name="sample-a-color-off-the-page-with-the-eyedropper"></a><span data-ttu-id="b000e-371">用“取色器“在页面上打样着色</span><span class="sxs-lookup"><span data-stu-id="b000e-371">Sample a color off the page with the Eyedropper</span></span>  

<span data-ttu-id="b000e-372">打开 **“颜色选取器”** 时，**“取色器”** \(![取色器](../media/eyedropper-icon.msft.png)\) 默认打开。</span><span class="sxs-lookup"><span data-stu-id="b000e-372">When you open the **Color Picker**, the **Eyedropper** \(![Eyedropper](../media/eyedropper-icon.msft.png)\) is on by default.</span></span>  <span data-ttu-id="b000e-373">完成以下操作，可将页面上的所选颜色改为其他颜色。</span><span class="sxs-lookup"><span data-stu-id="b000e-373">Complete the following actions to change the selected color to some other color on the page.</span></span>  

1.  <span data-ttu-id="b000e-374">将鼠标悬停在视区中的目标颜色上。</span><span class="sxs-lookup"><span data-stu-id="b000e-374">Hover on the target color in the viewport.</span></span>  
1.  <span data-ttu-id="b000e-375">选择以确认。</span><span class="sxs-lookup"><span data-stu-id="b000e-375">Choose to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b000e-376">下图中，**“颜色选取器”** 显示接近黑色的电流 `rgba(0,0,0,0.7)` 颜色值。</span><span class="sxs-lookup"><span data-stu-id="b000e-376">In the following figure, the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="b000e-377">特定的颜色应该更改为在你选择后变为当前视区中高亮的黑色版本。</span><span class="sxs-lookup"><span data-stu-id="b000e-377">The specific color should change to the version of black that is currently highlighted in the viewport after you chose it.</span></span>  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="使用取色器" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       <span data-ttu-id="b000e-379">使用取色器</span><span class="sxs-lookup"><span data-stu-id="b000e-379">Using the Eyedropper</span></span>  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b000e-380">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="b000e-380">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令 | Microsoft Docs"  
[DevToolsCSSGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档 | Microsoft Docs"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class " 向类添加伪状态 - 查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "查看元素的 CSS - 查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "强制 Microsoft Edge DevTools 进入打印预览模式(CSS 打印媒体类型) | Microsoft Docs"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#make-a-minified-file-readable "使缩小的文件可读 - JavaScript 调试参考 | Microsoft Docs"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统 - 材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "框模型 | MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型 - 特异性 | MDN"  

> [!NOTE]
> <span data-ttu-id="b000e-390">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b000e-390">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b000e-391">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="b000e-391">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b000e-393">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b000e-393">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  