---
description: 在 Microsoft Edge DevTools 中发现用于查看和更改 CSS 的新工作流。
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 84aacbb3961f6b8f6e9a0bda8823fecbbb26ec25
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
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

# <a name="css-reference"></a><span data-ttu-id="1c365-104">CSS 参考</span><span class="sxs-lookup"><span data-stu-id="1c365-104">CSS reference</span></span>  

<span data-ttu-id="1c365-105">以下有关查看和更改 CSS 的 Microsoft Edge DevTools 功能的综合参考中发现新工作流。</span><span class="sxs-lookup"><span data-stu-id="1c365-105">Discover new workflows in the following comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="1c365-106">若要了解基础知识，请导航到查看 [和更改 CSS 入门][DevToolsCSSGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="1c365-106">To learn the basics, navigate to [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <a name="choose-an-element"></a><span data-ttu-id="1c365-107">选择元素</span><span class="sxs-lookup"><span data-stu-id="1c365-107">Choose an element</span></span>  

<span data-ttu-id="1c365-108">DevTools 的 Elements 工具允许你一次查看或更改一个元素的 CSS。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1c365-108">The **Elements** tool of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="1c365-109">选定元素在 **DOM 树中突出显示**。</span><span class="sxs-lookup"><span data-stu-id="1c365-109">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="1c365-110">元素的样式显示在" **样式"窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="1c365-110">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="1c365-111">对于教程，导航到[查看元素 的 CSS。][DevToolsCSSGetStartedTutorial]</span><span class="sxs-lookup"><span data-stu-id="1c365-111">For a tutorial, navigate to [View the CSS for an element][DevToolsCSSGetStartedTutorial].</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-112">在下图中，DOM 树中突出显示 `h1` **的元素** 是所选元素。</span><span class="sxs-lookup"><span data-stu-id="1c365-112">In the following figure, the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="1c365-113">在右侧，元素的样式显示在" **样式"窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="1c365-113">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="1c365-114">在左侧，该元素在视口中突出显示，但仅仅是因为鼠标当前正悬停在**DOM 树 中。**</span><span class="sxs-lookup"><span data-stu-id="1c365-114">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="选定元素的示例" lightbox="../media/css-elements-styles-h1.msft.png":::
   <span data-ttu-id="1c365-116">选定元素的示例</span><span class="sxs-lookup"><span data-stu-id="1c365-116">An example of a selected element</span></span>  
:::image-end:::  

<span data-ttu-id="1c365-117">使用以下操作之一选择元素。</span><span class="sxs-lookup"><span data-stu-id="1c365-117">Use one the following actions to select an element.</span></span>  

*   <span data-ttu-id="1c365-118">在视口中，将鼠标悬停在 元素上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="1c365-118">In your viewport, hover on the element, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
*   <span data-ttu-id="1c365-119">在 DevTools 中，选择"选择元素**\ (** 选择元素 ![ \) "或选择 ](../media/select-an-element-icon.msft.png) `Control` + `Shift` + `C` \ (Windows、Linux\) 或 `Command` + `Shift` + `C` \ (macOS\) ，然后选择视口中的元素。</span><span class="sxs-lookup"><span data-stu-id="1c365-119">In DevTools, choose **Select an element** \(![Select an element](../media/select-an-element-icon.msft.png)\) or select `Control`+`Shift`+`C` \(Windows, Linux\) or `Command`+`Shift`+`C` \(macOS\), and then choose the element in the viewport.</span></span>  
*   <span data-ttu-id="1c365-120">在 DevTools 中，选择 **DOM**树中的 元素。</span><span class="sxs-lookup"><span data-stu-id="1c365-120">In DevTools, choose the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="1c365-121">在 DevTools 中，像在控制台中一样运行查询，将鼠标悬停在结果上，打开上下文菜单 \ (右键单击\) ，然后选择"元素"面板中的 `document.querySelector('p')` "**展示"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1c365-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, hover on the result, open the contextual menu \(right-click\), and choose **Reveal in Elements panel**.</span></span>  

## <a name="view-css"></a><span data-ttu-id="1c365-122">查看 CSS</span><span class="sxs-lookup"><span data-stu-id="1c365-122">View CSS</span></span>  

### <a name="view-the-external-stylesheet-where-a-rule-is-defined"></a><span data-ttu-id="1c365-123">查看定义规则的外部样式表</span><span class="sxs-lookup"><span data-stu-id="1c365-123">View the external stylesheet where a rule is defined</span></span>  

<span data-ttu-id="1c365-124">在 **"样式** "窗格中，选择 CSS 规则旁边的链接以打开定义该规则的外部样式表。</span><span class="sxs-lookup"><span data-stu-id="1c365-124">In the **Styles** pane, choose the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  

<span data-ttu-id="1c365-125">如果样式表已缩小，请导航到"[使缩小文件可读"。][DevToolsJavascriptReferenceFormat]</span><span class="sxs-lookup"><span data-stu-id="1c365-125">If the stylesheet is minified, navigate to [Make a minified file readable][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-126">在下图中，选择后，您将进入 定义 CSS 规则的第 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 2 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` `.content h1:first-of-type` 行。</span><span class="sxs-lookup"><span data-stu-id="1c365-126">In the following figure, after you choose `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` you are taken to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="查看定义规则的样式表" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  <span data-ttu-id="1c365-128">查看定义规则的样式表</span><span class="sxs-lookup"><span data-stu-id="1c365-128">Viewing the stylesheet where a rule is defined</span></span>  
:::image-end:::  

### <a name="view-only-the-css-that-is-actually-applied-to-an-element"></a><span data-ttu-id="1c365-129">仅查看实际应用于元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="1c365-129">View only the CSS that is actually applied to an element</span></span>  

<span data-ttu-id="1c365-130">" **样式** "面板显示应用于元素的所有规则，包括已替代的声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-130">The **Styles** panel shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="1c365-131">如果对重写声明不感兴趣，请使用 **Computed** 面板仅查看实际应用于元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="1c365-131">When you are not interested in overridden declarations, use the **Computed** panel to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="1c365-132">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="1c365-132">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="1c365-133">导航到 **"元素"工具** 中的"计算 **"** 面板。</span><span class="sxs-lookup"><span data-stu-id="1c365-133">Navigate to the **Computed** panel in the **Elements** tool.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-134">在宽的 DevTools 窗口中\*\*\*\*，计算面板不存在。</span><span class="sxs-lookup"><span data-stu-id="1c365-134">On a wide DevTools window, the **Computed** panel does not exist.</span></span>  <span data-ttu-id="1c365-135">"计算" **面板的内容** 显示在" **样式"面板** 上。</span><span class="sxs-lookup"><span data-stu-id="1c365-135">The contents of the **Computed** panel are shown on the **Styles** panel.</span></span>  

<span data-ttu-id="1c365-136">继承的属性是不透明的。</span><span class="sxs-lookup"><span data-stu-id="1c365-136">Inherited properties are opaque.</span></span>  <span data-ttu-id="1c365-137">若要显示所有继承的值，请选中" **全部显示"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c365-137">To display all inherited values, select the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-138">下图中，" **计算** "面板显示应用于当前选定元素的 CSS `h1` 属性。</span><span class="sxs-lookup"><span data-stu-id="1c365-138">In the following figure, the **Computed** panel shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="计算面板" lightbox="../media/css-elements-computed-h1.msft.png":::
   <span data-ttu-id="1c365-140">**计算面板**</span><span class="sxs-lookup"><span data-stu-id="1c365-140">The **Computed** panel</span></span>  
:::image-end:::  

### <a name="view-css-properties-in-alphabetical-order"></a><span data-ttu-id="1c365-141">按字母顺序查看 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="1c365-141">View CSS properties in alphabetical order</span></span>  

<span data-ttu-id="1c365-142">使用 **"计算"** 面板。</span><span class="sxs-lookup"><span data-stu-id="1c365-142">Use the **Computed** panel.</span></span>  <span data-ttu-id="1c365-143">导航[到"仅查看实际应用于元素的 CSS"。](#view-only-the-css-that-is-actually-applied-to-an-element)</span><span class="sxs-lookup"><span data-stu-id="1c365-143">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-inherited-css-properties"></a><span data-ttu-id="1c365-144">查看继承的 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="1c365-144">View inherited CSS properties</span></span>  

<span data-ttu-id="1c365-145">选中" **计算"面板** 中的"全部 **显示"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c365-145">Check the **Show All** checkbox in the **Computed** panel.</span></span>  <span data-ttu-id="1c365-146">导航[到"仅查看实际应用于元素的 CSS"。](#view-only-the-css-that-is-actually-applied-to-an-element)</span><span class="sxs-lookup"><span data-stu-id="1c365-146">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-the-box-model-for-an-element"></a><span data-ttu-id="1c365-147">查看元素的框模型</span><span class="sxs-lookup"><span data-stu-id="1c365-147">View the box model for an element</span></span>  

<span data-ttu-id="1c365-148">若要查看 [元素的框][MDNBoxModel] 模型，请导航到" **样式"** 面板。</span><span class="sxs-lookup"><span data-stu-id="1c365-148">To view [the box model][MDNBoxModel] of an element, navigate to the **Styles** panel.</span></span>  <span data-ttu-id="1c365-149">如果你的 DevTools 窗口较窄，则 **框** 模型图位于面板的底部。</span><span class="sxs-lookup"><span data-stu-id="1c365-149">If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the panel.</span></span>  

<span data-ttu-id="1c365-150">选择并编辑值以更改值。</span><span class="sxs-lookup"><span data-stu-id="1c365-150">Choose and edit on a value to change a value.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-151">在下图中 **，"样式** "面板中的"方框模型 **"图显示** 当前所选元素的框 `h1` 模型。</span><span class="sxs-lookup"><span data-stu-id="1c365-151">In the following figure, the **Box Model** diagram in the **Styles** panel shows the box model for the currently selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="方框模型图" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   <span data-ttu-id="1c365-153">方框 **模型** 图</span><span class="sxs-lookup"><span data-stu-id="1c365-153">The **Box Model** diagram</span></span>  
:::image-end:::  

### <a name="search-and-filter-the-css-of-an-element"></a><span data-ttu-id="1c365-154">搜索和筛选元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="1c365-154">Search and filter the CSS of an element</span></span>  

<span data-ttu-id="1c365-155">使用 **"样式**"和"计算\*\*\*\*"面板\*\*\*\* 上的"筛选器"文本框搜索特定的 CSS 属性或值。</span><span class="sxs-lookup"><span data-stu-id="1c365-155">Use the **Filter** text box on the **Styles** and **Computed** panels to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="1c365-156">若要同时在计算面板 **中搜索继承** 的属性，请选中" **全部显示"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c365-156">To also search inherited properties in the **Computed** panel, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-157">在下图中， **将筛选"样式** "面板，以只显示包含搜索查询 的规则 `color` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-157">In the following figure, the **Styles** panel is filtered to only show rules that include the search query `color`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="筛选"样式"面板" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   <span data-ttu-id="1c365-159">筛选 **"样式"** 面板</span><span class="sxs-lookup"><span data-stu-id="1c365-159">Filter the **Styles** panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="1c365-160">在下图中， **将筛选计算** 面板以只显示包含搜索查询 的声明 `100%` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-160">In the following figure, the **Computed** panel is filtered to only show declarations that include the search query `100%`.</span></span>  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="筛选"计算"面板" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   <span data-ttu-id="1c365-162">筛选 **"计算"** 面板</span><span class="sxs-lookup"><span data-stu-id="1c365-162">Filter the **Computed** panel</span></span>  
:::image-end:::  

### <a name="toggle-a-pseudo-class"></a><span data-ttu-id="1c365-163">切换伪类</span><span class="sxs-lookup"><span data-stu-id="1c365-163">Toggle a pseudo-class</span></span>  

<span data-ttu-id="1c365-164">完成以下操作以切换伪类，如 `:active` 、 `:focus` 、 或 `:hover` `:visited` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-164">Complete the following actions to toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`.</span></span>  

1.  <span data-ttu-id="1c365-165">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="1c365-165">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="1c365-166">在" **元素"** 工具上，导航到 **"样式"** 面板。</span><span class="sxs-lookup"><span data-stu-id="1c365-166">On the **Elements** tool, navigate to the **Styles** panel.</span></span>  
1.  <span data-ttu-id="1c365-167">选择 **：hov**。</span><span class="sxs-lookup"><span data-stu-id="1c365-167">Choose **:hov**.</span></span>  
1.  <span data-ttu-id="1c365-168">检查要启用的伪类。</span><span class="sxs-lookup"><span data-stu-id="1c365-168">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-169">在下图中，切换 `:hover` 伪类。</span><span class="sxs-lookup"><span data-stu-id="1c365-169">In the following figure, toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="1c365-170">在视口中，验证声明是否应用于元素，即使该元素实际上并未悬停在 `background-color: cornflowerblue` 上方。</span><span class="sxs-lookup"><span data-stu-id="1c365-170">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切换 ：hover 伪类" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   <span data-ttu-id="1c365-172">切换 `:hover` 伪类</span><span class="sxs-lookup"><span data-stu-id="1c365-172">Toggle the `:hover` pseudo-class</span></span>  
:::image-end:::  

<span data-ttu-id="1c365-173">对于交互式教程，导航到["将伪状态添加到类"。][DevToolsCSSGetStartedAddPseudoState]</span><span class="sxs-lookup"><span data-stu-id="1c365-173">For an interactive tutorial, navigate to [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState].</span></span>  

### <a name="view-a-page-in-print-mode"></a><span data-ttu-id="1c365-174">在打印模式下查看页面</span><span class="sxs-lookup"><span data-stu-id="1c365-174">View a page in print mode</span></span>  

<span data-ttu-id="1c365-175">完成以下操作以在打印模式下查看页面。</span><span class="sxs-lookup"><span data-stu-id="1c365-175">Complete the following actions to view a page in print mode.</span></span>  

1.  <span data-ttu-id="1c365-176">[打开命令菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="1c365-176">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="1c365-177">开始键入并选择 `Rendering` `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-177">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="1c365-178">对于"**模拟 CSS 媒体**"下拉列表，选择"打印 **"。**</span><span class="sxs-lookup"><span data-stu-id="1c365-178">For the **Emulate CSS Media** dropdown, choose **print**.</span></span>  

### <a name="view-used-and-unused-css-with-the-coverage-tool"></a><span data-ttu-id="1c365-179">使用"覆盖"工具查看已用和未使用的 CSS</span><span class="sxs-lookup"><span data-stu-id="1c365-179">View used and unused CSS with the Coverage tool</span></span>  

<span data-ttu-id="1c365-180">覆盖 **工具** 显示页面实际使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="1c365-180">The **Coverage** tool shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="1c365-181">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 而 DevTools 位于[][DevToolsCommandMenu]焦点中以打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="1c365-181">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to [open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="1c365-182">开始键入并选择 `coverage` "显示**覆盖"。**</span><span class="sxs-lookup"><span data-stu-id="1c365-182">Start typing `coverage` and choose **Show Coverage**.</span></span>  <span data-ttu-id="1c365-183">将显示 **"覆盖** "工具。</span><span class="sxs-lookup"><span data-stu-id="1c365-183">The **Coverage** tool appears.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="从命令菜单打开覆盖工具" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             <span data-ttu-id="1c365-185">从命令 **菜单** 打开覆盖 **工具**</span><span class="sxs-lookup"><span data-stu-id="1c365-185">Open the **Coverage** tool from the **Command Menu**</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="覆盖工具" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             <span data-ttu-id="1c365-187">覆盖**工具**</span><span class="sxs-lookup"><span data-stu-id="1c365-187">The **Coverage** tool</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="1c365-188">选择 **开始检测覆盖范围并刷新** 页面 \ (![ 开始检测范围并刷新 ](../media/refresh-icon.msft.png) 页面 \) 。</span><span class="sxs-lookup"><span data-stu-id="1c365-188">Choose **Start instrumenting coverage and refresh the page** \(![Start instrumenting coverage and refresh the page](../media/refresh-icon.msft.png)\).</span></span>  <span data-ttu-id="1c365-189">页面刷新和覆盖工具概述了\*\*\*\* 浏览器加载的每个文件使用多少 CSS \ (和 JavaScript\) 。</span><span class="sxs-lookup"><span data-stu-id="1c365-189">The page refreshes and the **Coverage** tool provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="1c365-190">绿色表示使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="1c365-190">Green represents used CSS.</span></span>  <span data-ttu-id="1c365-191">红色表示未使用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="1c365-191">Red represents unused CSS.</span></span>  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="使用和未使用 CSS (JavaScript) 概述" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       <span data-ttu-id="1c365-193">使用和未使用 CSS \ (JavaScript\) 的概述</span><span class="sxs-lookup"><span data-stu-id="1c365-193">An overview of how much CSS \(and JavaScript\) is used and unused</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="1c365-194">若要显示 CSS 使用的明细数据，请选择 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="1c365-194">To display a line-by-line breakdown of what CSS is used, choose a CSS file.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1c365-195">在下图中，未使用第 145 至 147 行以及 149 到 151 行，而 `b66bc881.site-ltr.css` 使用第 163 至 166 行。</span><span class="sxs-lookup"><span data-stu-id="1c365-195">In the following figure, lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="已使用和未使用的 CSS 的行细分" lightbox="../media/css-sources-css-coverage.msft.png":::
       <span data-ttu-id="1c365-197">已使用和未使用的 CSS 的行细分</span><span class="sxs-lookup"><span data-stu-id="1c365-197">A line-by-line breakdown of used and unused CSS</span></span>  
    :::image-end:::  
    
### <a name="force-print-preview-mode"></a><span data-ttu-id="1c365-198">强制打印预览模式</span><span class="sxs-lookup"><span data-stu-id="1c365-198">Force print preview mode</span></span>  

<span data-ttu-id="1c365-199">导航到 [强制 DevTools 进入打印预览模式][DevToolsCssPrintPreview]。</span><span class="sxs-lookup"><span data-stu-id="1c365-199">Navigate to [Force DevTools into Print Preview mode][DevToolsCssPrintPreview].</span></span>  

## <a name="change-css"></a><span data-ttu-id="1c365-200">更改 CSS</span><span class="sxs-lookup"><span data-stu-id="1c365-200">Change CSS</span></span>  

<!-- todo s/CSS declaration/declaration/ -->  

### <a name="add-a-css-declaration-to-an-element"></a><span data-ttu-id="1c365-201">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="1c365-201">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="1c365-202">声明的顺序会影响元素的样式，请使用以下列表来帮助你以不同方式添加声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-202">The order of declarations affects how an element is styled, use the following list to help you add declarations in different ways.</span></span>  

*   <span data-ttu-id="1c365-203">[添加内嵌声明](#add-an-inline-declaration)。</span><span class="sxs-lookup"><span data-stu-id="1c365-203">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="1c365-204">相当于将 `style` 属性添加到元素的 HTML。</span><span class="sxs-lookup"><span data-stu-id="1c365-204">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="1c365-205">[向样式规则添加声明](#add-a-declaration-to-a-style-rule)。</span><span class="sxs-lookup"><span data-stu-id="1c365-205">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="1c365-206">您应该使用什么工作流？</span><span class="sxs-lookup"><span data-stu-id="1c365-206">What workflow should you use?</span></span>** <span data-ttu-id="1c365-207">对于大多数方案，您可能想要使用内嵌声明工作流。</span><span class="sxs-lookup"><span data-stu-id="1c365-207">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="1c365-208">内嵌声明比外部声明具有更高的特定性，因此内联工作流可确保更改在预期元素中生效。</span><span class="sxs-lookup"><span data-stu-id="1c365-208">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in your expected element.</span></span>  <span data-ttu-id="1c365-209">有关特定性详细信息，请导航到选择 [器类型][MDNSelectorTypes]。</span><span class="sxs-lookup"><span data-stu-id="1c365-209">For more information about specificity, navigate to [Selector Types][MDNSelectorTypes].</span></span>  

<span data-ttu-id="1c365-210">如果要调试元素的任何样式，并且需要专门测试在不同位置定义声明时会发生什么情况，请使用其他工作流。</span><span class="sxs-lookup"><span data-stu-id="1c365-210">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <a name="add-an-inline-declaration"></a><span data-ttu-id="1c365-211">添加内嵌声明</span><span class="sxs-lookup"><span data-stu-id="1c365-211">Add an inline declaration</span></span>  

<span data-ttu-id="1c365-212">完成以下操作以添加内嵌声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-212">Complete the following actions to add an inline declaration.</span></span>  

1.  <span data-ttu-id="1c365-213">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="1c365-213">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="1c365-214">在 **"样式** "窗格中，在 **element.style** 节的括号之间选择。</span><span class="sxs-lookup"><span data-stu-id="1c365-214">In the **Styles** pane, choose between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="1c365-215">光标聚焦，允许您输入文本。</span><span class="sxs-lookup"><span data-stu-id="1c365-215">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="1c365-216">输入属性名称并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-216">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="1c365-217">输入该属性的有效值，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-217">Enter a valid value for that property and select `Enter`.</span></span>  <span data-ttu-id="1c365-218">在 **DOM 树**中，验证 `style` 属性已添加到 元素。</span><span class="sxs-lookup"><span data-stu-id="1c365-218">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-219">在下图中，和 `margin-top` `background-color` 属性已应用于选定元素。</span><span class="sxs-lookup"><span data-stu-id="1c365-219">In the following figure, the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="1c365-220">在 **DOM 树** 中，验证声明是否反映在 `style` 元素的 属性中。</span><span class="sxs-lookup"><span data-stu-id="1c365-220">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="添加内嵌声明" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   <span data-ttu-id="1c365-222">添加内嵌声明</span><span class="sxs-lookup"><span data-stu-id="1c365-222">Add inline declarations</span></span>  
:::image-end:::  

#### <a name="add-a-declaration-to-a-style-rule"></a><span data-ttu-id="1c365-223">向样式规则添加声明</span><span class="sxs-lookup"><span data-stu-id="1c365-223">Add a declaration to a style rule</span></span>  

<span data-ttu-id="1c365-224">完成以下操作以向现有样式规则添加声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-224">Complete the following actions to add a declaration to an existing style rule.</span></span>  

1.  <span data-ttu-id="1c365-225">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="1c365-225">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="1c365-226">在 **"样式** "窗格中，在要添加声明的样式规则的括号之间选择。</span><span class="sxs-lookup"><span data-stu-id="1c365-226">In the **Styles** pane, choose between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="1c365-227">光标聚焦，允许您输入文本。</span><span class="sxs-lookup"><span data-stu-id="1c365-227">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="1c365-228">输入属性名称并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-228">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="1c365-229">输入该属性的有效值，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-229">Enter a valid value for that property and select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="向样式规则添加声明" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   <span data-ttu-id="1c365-231">将 `border-bottom-style:groove` 声明添加到样式规则</span><span class="sxs-lookup"><span data-stu-id="1c365-231">Add the `border-bottom-style:groove` declaration to a style rule</span></span>  
:::image-end:::  

### <a name="change-a-declaration-name-or-value"></a><span data-ttu-id="1c365-232">更改声明名称或值</span><span class="sxs-lookup"><span data-stu-id="1c365-232">Change a declaration name or value</span></span>  

<span data-ttu-id="1c365-233">选择并编辑声明的名称或值以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="1c365-233">Choose and edit the name or value of a declaration to change it.</span></span>  <span data-ttu-id="1c365-234">对于通过、或单位快速递增或缩小值的快捷方式，请导航到"使用键盘快捷方式 `0.1` `1` `10` `100` [更改声明值"。](#change-declaration-values-with-keyboard-shortcuts)</span><span class="sxs-lookup"><span data-stu-id="1c365-234">For shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units, navigate to [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts).</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="更改声明的值" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   <span data-ttu-id="1c365-236">更改声明 `border-bottom-style` 的值</span><span class="sxs-lookup"><span data-stu-id="1c365-236">Change the value of the `border-bottom-style` declaration</span></span>  
:::image-end:::  

### <a name="change-declaration-values-with-keyboard-shortcuts"></a><span data-ttu-id="1c365-237">使用键盘快捷方式更改声明值</span><span class="sxs-lookup"><span data-stu-id="1c365-237">Change declaration values with keyboard shortcuts</span></span>  

<span data-ttu-id="1c365-238">编辑声明的值时，可以使用以下键盘快捷方式将值增加一定量。</span><span class="sxs-lookup"><span data-stu-id="1c365-238">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a specific amount.</span></span>  

*   <span data-ttu-id="1c365-239">选择 `Alt` + `Up` \ (Windows、Linux\) 或 `Option` + `Up` \ (macOS\) 递增 `0.1` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-239">Select `Alt`+`Up` \(Windows, Linux\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="1c365-240">选择 将值更改为 ，如果当前值介于 和 之间，则按 `Up` `1` `0.1` `-1` 更改 `1` 值。</span><span class="sxs-lookup"><span data-stu-id="1c365-240">Select `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="1c365-241">选择 `Shift` + `Up` 以按 递增 `10` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-241">Select `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="1c365-242">选择 `Shift` + `Page Up` \ (Windows、Linux\) 或 `Shift` + `Command` + `Up` \ (macOS\) `100` 将值递增。</span><span class="sxs-lookup"><span data-stu-id="1c365-242">Select `Shift`+`Page Up` \(Windows, Linux\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="1c365-243">减减也有效。</span><span class="sxs-lookup"><span data-stu-id="1c365-243">Decrementing also works.</span></span>  <span data-ttu-id="1c365-244">只需将上述每个 `Up` 实例替换为 `Down` 。</span><span class="sxs-lookup"><span data-stu-id="1c365-244">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <a name="add-a-class-to-an-element"></a><span data-ttu-id="1c365-245">向元素添加类</span><span class="sxs-lookup"><span data-stu-id="1c365-245">Add a class to an element</span></span>  

<span data-ttu-id="1c365-246">完成以下操作以向元素中添加类。</span><span class="sxs-lookup"><span data-stu-id="1c365-246">Complete the following actions to add a class to an element.</span></span>  

1.  <span data-ttu-id="1c365-247">[选择 DOM](#choose-an-element) 树 **中的 元素**。</span><span class="sxs-lookup"><span data-stu-id="1c365-247">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="1c365-248">选择 **".cls"。**</span><span class="sxs-lookup"><span data-stu-id="1c365-248">Choose **.cls**.</span></span>  
1.  <span data-ttu-id="1c365-249">在"添加新类"文本框 **中输入类** 的名称。</span><span class="sxs-lookup"><span data-stu-id="1c365-249">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="1c365-250">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="1c365-250">Select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text=""元素类"窗格" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   <span data-ttu-id="1c365-252">" **元素类"** 窗格</span><span class="sxs-lookup"><span data-stu-id="1c365-252">The **Element Classes** pane</span></span>  
:::image-end:::  

### <a name="toggle-a-class"></a><span data-ttu-id="1c365-253">切换类</span><span class="sxs-lookup"><span data-stu-id="1c365-253">Toggle a class</span></span>  

<span data-ttu-id="1c365-254">完成以下操作以启用或禁用元素上的类。</span><span class="sxs-lookup"><span data-stu-id="1c365-254">Complete the following actions to enable or disable a class on an element.</span></span>  

1.  <span data-ttu-id="1c365-255">[选择 DOM](#choose-an-element) 树 **中的 元素**。</span><span class="sxs-lookup"><span data-stu-id="1c365-255">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="1c365-256">打开 **"元素类"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="1c365-256">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="1c365-257">导航到["将类添加到元素"。](#add-a-class-to-an-element)</span><span class="sxs-lookup"><span data-stu-id="1c365-257">Navigate to [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="1c365-258">在" **添加新类** "文本框下方是应用于特定元素的所有类。</span><span class="sxs-lookup"><span data-stu-id="1c365-258">Below the **Add New Class** text box are all of the classes applied to the specific element.</span></span>  
1.  <span data-ttu-id="1c365-259">切换要打开或关闭的类旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="1c365-259">Toggle the checkbox next to the class that you want to turn on or off.</span></span>  

### <a name="add-a-style-rule"></a><span data-ttu-id="1c365-260">添加样式规则</span><span class="sxs-lookup"><span data-stu-id="1c365-260">Add a style rule</span></span>  

<span data-ttu-id="1c365-261">完成以下操作以添加新的样式规则。</span><span class="sxs-lookup"><span data-stu-id="1c365-261">Complete the following actions to add a new style rule.</span></span>  

1.  <span data-ttu-id="1c365-262">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="1c365-262">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="1c365-263">Choose **New Style Rule** \ (New Style Rule ![ ](../media/new-style-rule-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="1c365-263">Choose **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\).</span></span>  <span data-ttu-id="1c365-264">DevTools 在 **element.style 规则下插入一个新** 规则。</span><span class="sxs-lookup"><span data-stu-id="1c365-264">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-265">在下图中，DevTools 在选择"新建样式规则"后 `h1.devsite-page-title` **添加样式规则**。</span><span class="sxs-lookup"><span data-stu-id="1c365-265">In the following figure, DevTools adds the `h1.devsite-page-title` style rule after you choose **New Style Rule**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="添加新的样式规则" lightbox="../media/css-elements-styles-style-new.msft.png":::
   <span data-ttu-id="1c365-267">添加新的样式规则</span><span class="sxs-lookup"><span data-stu-id="1c365-267">Add a new style rule</span></span>  
:::image-end:::  

#### <a name="choose-which-stylesheet-to-add-a-rule-to"></a><span data-ttu-id="1c365-268">选择要向哪个样式表添加规则</span><span class="sxs-lookup"><span data-stu-id="1c365-268">Choose which stylesheet to add a rule to</span></span>  

<span data-ttu-id="1c365-269">添加新[样式规则](#add-a-style-rule)时，选择并按住"新建\*\*\*\* 样式规则" ("新建样式规则) 以选择要向哪个样式 ![ ](../media/new-style-rule-icon.msft.png) 表添加样式规则。</span><span class="sxs-lookup"><span data-stu-id="1c365-269">When [adding a new style rule](#add-a-style-rule), choose and hold **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\) to choose which stylesheet to add the style rule to.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="选择样式表" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   <span data-ttu-id="1c365-271">选择样式表</span><span class="sxs-lookup"><span data-stu-id="1c365-271">Choose a stylesheet</span></span>  
:::image-end:::  

#### <a name="add-a-style-rule-to-a-specific-location"></a><span data-ttu-id="1c365-272">将样式规则添加到特定位置</span><span class="sxs-lookup"><span data-stu-id="1c365-272">Add a style rule to a specific location</span></span>  

<span data-ttu-id="1c365-273">完成以下操作，将样式规则添加到"样式"面板中的 **特定** 位置。</span><span class="sxs-lookup"><span data-stu-id="1c365-273">Complete the following actions to add a style rule to a specific location in the **Styles** panel.</span></span>  

1.  <span data-ttu-id="1c365-274">将鼠标悬停在要添加新样式规则的正上方的样式规则上。</span><span class="sxs-lookup"><span data-stu-id="1c365-274">Hover on the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="1c365-275">[显示" **更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="1c365-275">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="1c365-276">Choose **Insert Style Rule below** \ (Insert Style Rule below icon ![ ](../media/new-style-rule-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="1c365-276">Choose **Insert Style Rule Below** \(![Insert Style Rule Below icon](../media/new-style-rule-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="在下方插入样式规则" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **<span data-ttu-id="1c365-278">在下方插入样式规则</span><span class="sxs-lookup"><span data-stu-id="1c365-278">Insert Style Rule Below</span></span>**  
:::image-end:::  

### <a name="reveal-the-more-actions-toolbar"></a><span data-ttu-id="1c365-279">显示"更多操作"工具栏</span><span class="sxs-lookup"><span data-stu-id="1c365-279">Reveal the More Actions toolbar</span></span>  

<span data-ttu-id="1c365-280">" **更多操作** "工具栏允许您执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="1c365-280">The **More Actions** toolbar lets you perform the following actions.</span></span>  

*   <span data-ttu-id="1c365-281">在重点样式规则正下方插入样式规则。</span><span class="sxs-lookup"><span data-stu-id="1c365-281">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="1c365-282">将 `background-color` 、 `color` `box-shadow` 、 或 `text-shadow` 声明添加到你侧重于的样式规则。</span><span class="sxs-lookup"><span data-stu-id="1c365-282">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="1c365-283">完成以下操作以显示"更多 **操作"** 工具栏。</span><span class="sxs-lookup"><span data-stu-id="1c365-283">Complete the following actions to reveal the **More Actions** toolbar.</span></span>  

1.  <span data-ttu-id="1c365-284">在" **样式"** 面板中，将鼠标悬停在样式规则上。</span><span class="sxs-lookup"><span data-stu-id="1c365-284">In the **Styles** panel, hover on a style rule.</span></span>  <span data-ttu-id="1c365-285">**更多操作** \ (\) 在样式规则部分右下 `...` 角显示。</span><span class="sxs-lookup"><span data-stu-id="1c365-285">**More Actions** \(`...`\) is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1c365-286">在下图中，将鼠标悬停在样式规则上，"更多操作"显示于样式规则节的 `.header-holder.has-default-focus` 右下角。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1c365-286">In the following figure, hover on the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="显示更多操作" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       <span data-ttu-id="1c365-288">显示 **更多操作** \ (`...` \) </span><span class="sxs-lookup"><span data-stu-id="1c365-288">Reveal **More Actions** \(`...`\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c365-289">将鼠标 **悬停在"更多** 操作 (`...` \) 可显示上述操作。</span><span class="sxs-lookup"><span data-stu-id="1c365-289">Hover on **More Actions** \(`...`\) to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1c365-290">将 **鼠标悬停在"更多** 操作"上后，显示"插入样式规则下方 **"操作**。</span><span class="sxs-lookup"><span data-stu-id="1c365-290">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text=""更多操作"工具栏" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       <span data-ttu-id="1c365-292">" **更多操作"** 工具栏</span><span class="sxs-lookup"><span data-stu-id="1c365-292">The **More Actions** toolbar</span></span>  
    :::image-end:::  
    
### <a name="toggle-a-declaration"></a><span data-ttu-id="1c365-293">切换声明</span><span class="sxs-lookup"><span data-stu-id="1c365-293">Toggle a declaration</span></span>  

<span data-ttu-id="1c365-294">完成创建操作以在 \ (或 off\) 上切换单个) 。</span><span class="sxs-lookup"><span data-stu-id="1c365-294">Complete the folllwoing actions to toggle a single declaration on \(or off\).</span></span>  

1.  <span data-ttu-id="1c365-295">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="1c365-295">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="1c365-296">在 **"样式** "窗格中，将鼠标悬停在定义声明的规则上。</span><span class="sxs-lookup"><span data-stu-id="1c365-296">In the **Styles** pane, hover on the rule that defines the declaration.</span></span>  <span data-ttu-id="1c365-297">每个声明旁边都显示一个复选框。</span><span class="sxs-lookup"><span data-stu-id="1c365-297">A checkbox appears next to each declaration.</span></span>  
1.  <span data-ttu-id="1c365-298">选中\ (或取消选中\) 声明旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="1c365-298">Check \(or uncheck\) the checkbox next to the declaration.</span></span>  <span data-ttu-id="1c365-299">取消选中声明时，DevTools 会交叉它以指示它不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="1c365-299">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c365-300">在下图中， `margin-top` 当前所选元素的属性已切换为关闭。</span><span class="sxs-lookup"><span data-stu-id="1c365-300">In the following figure, the `margin-top` property for the currently selected element has been toggled off.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="切换声明" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   <span data-ttu-id="1c365-302">切换声明</span><span class="sxs-lookup"><span data-stu-id="1c365-302">Toggle a declaration</span></span>  
:::image-end:::  

### <a name="add-a-background-color-declaration"></a><span data-ttu-id="1c365-303">添加背景色声明</span><span class="sxs-lookup"><span data-stu-id="1c365-303">Add a background-color declaration</span></span>  

<span data-ttu-id="1c365-304">完成以下操作以向 `background-color` 元素添加声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-304">Complete the following actions to add a `background-color` declaration to an element.</span></span>  

1.  <span data-ttu-id="1c365-305">将鼠标悬停在要添加声明的样式 `background-color` 规则上。</span><span class="sxs-lookup"><span data-stu-id="1c365-305">Hover on the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="1c365-306">[显示" **更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="1c365-306">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="1c365-307">Choose **Add Background Color** \ (Add Background Color icon ![ ](../media/add-background-color-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="1c365-307">Choose **Add Background Color** \(![Add Background Color icon](../media/add-background-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="添加背景色" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **<span data-ttu-id="1c365-309">添加背景色</span><span class="sxs-lookup"><span data-stu-id="1c365-309">Add Background Color</span></span>**  
:::image-end:::  

### <a name="add-a-color-declaration"></a><span data-ttu-id="1c365-310">添加颜色声明</span><span class="sxs-lookup"><span data-stu-id="1c365-310">Add a color declaration</span></span>  

<span data-ttu-id="1c365-311">完成以下操作以向 `color` 元素添加声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-311">Complete the following actions to add a `color` declaration to an element.</span></span>  

1.  <span data-ttu-id="1c365-312">将鼠标悬停在要添加声明的样式 `color` 规则上。</span><span class="sxs-lookup"><span data-stu-id="1c365-312">Hover on the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="1c365-313">[显示" **更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="1c365-313">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="1c365-314">Choose **Add Color** \ (Add Color icon ![ ](../media/add-color-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="1c365-314">Choose **Add Color** \(![Add Color icon](../media/add-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="添加颜色" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **<span data-ttu-id="1c365-316">添加颜色</span><span class="sxs-lookup"><span data-stu-id="1c365-316">Add Color</span></span>**  
:::image-end:::  

### <a name="add-a-box-shadow-declaration"></a><span data-ttu-id="1c365-317">添加框阴影声明</span><span class="sxs-lookup"><span data-stu-id="1c365-317">Add a box-shadow declaration</span></span>  

<span data-ttu-id="1c365-318">完成以下操作以向 `box-shadow` 元素添加声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-318">Complete the follwoing actions to add a `box-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="1c365-319">将鼠标悬停在要添加声明的样式 `box-shadow` 规则上。</span><span class="sxs-lookup"><span data-stu-id="1c365-319">Hover on the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="1c365-320">[显示" **更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="1c365-320">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="1c365-321">Choose **Add Box Shadow** \ (Add Box Shadow icon ![ ](../media/add-box-shadow-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="1c365-321">Choose **Add Box Shadow** \(![Add Box Shadow icon](../media/add-box-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="添加框阴影" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **<span data-ttu-id="1c365-323">添加框阴影</span><span class="sxs-lookup"><span data-stu-id="1c365-323">Add Box Shadow</span></span>**  
:::image-end:::  

### <a name="add-a-text-shadow-declaration"></a><span data-ttu-id="1c365-324">添加文本阴影声明</span><span class="sxs-lookup"><span data-stu-id="1c365-324">Add a text-shadow declaration</span></span>  

<span data-ttu-id="1c365-325">完成以下操作以向 `text-shadow` 元素添加声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-325">Complete the following actions to add a `text-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="1c365-326">将鼠标悬停在要添加声明的样式 `text-shadow` 规则上。</span><span class="sxs-lookup"><span data-stu-id="1c365-326">Hover on the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="1c365-327">[显示" **更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="1c365-327">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="1c365-328">Choose **Add Text Shadow** \ (Add Text Shadow icon ![ ](../media/add-text-shadow-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="1c365-328">Choose **Add Text Shadow** \(![Add Text Shadow icon](../media/add-text-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="添加文本阴影" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **<span data-ttu-id="1c365-330">添加文本阴影</span><span class="sxs-lookup"><span data-stu-id="1c365-330">Add Text Shadow</span></span>**  
:::image-end:::  

### <a name="change-colors-with-the-color-picker"></a><span data-ttu-id="1c365-331">使用颜色选取器更改颜色</span><span class="sxs-lookup"><span data-stu-id="1c365-331">Change colors with the Color Picker</span></span>  

<span data-ttu-id="1c365-332">颜色 **选取器** 提供用于更改和声明 `color` 的 `background-color` GUI。</span><span class="sxs-lookup"><span data-stu-id="1c365-332">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="1c365-333">完成以下操作以打开 **颜色选取器**。</span><span class="sxs-lookup"><span data-stu-id="1c365-333">Complete the following actions to open the **Color Picker**.</span></span>  

1.  <span data-ttu-id="1c365-334">[选择元素](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="1c365-334">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="1c365-335">在 **"样式** "面板中，查找要更改的 、 或类似 `color` `background-color` 声明。</span><span class="sxs-lookup"><span data-stu-id="1c365-335">In the **Styles** panel, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="1c365-336">在 、 或类似值的左侧，有一个小 `color` `background-color` 正方形，它是颜色预览。</span><span class="sxs-lookup"><span data-stu-id="1c365-336">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1c365-337">在下图中，左侧的小正方形 `rgba(0, 0, 0, 0.7)` 是该颜色的预览。</span><span class="sxs-lookup"><span data-stu-id="1c365-337">In the following figure, the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="颜色预览" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       <span data-ttu-id="1c365-339">颜色预览</span><span class="sxs-lookup"><span data-stu-id="1c365-339">Color preview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c365-340">选择预览以打开 **颜色选取器**。</span><span class="sxs-lookup"><span data-stu-id="1c365-340">Choose the preview to open the **Color Picker**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       <span data-ttu-id="1c365-342">颜色 **选取器**</span><span class="sxs-lookup"><span data-stu-id="1c365-342">The **Color Picker**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="1c365-343">下图和列表对颜色选取器的每个 UI 元素的**descries。**</span><span class="sxs-lookup"><span data-stu-id="1c365-343">The following figure and list descries of each of the UI elements of the **Color Picker**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="已批注的颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   <span data-ttu-id="1c365-345">已 **批注的颜色**选取器</span><span class="sxs-lookup"><span data-stu-id="1c365-345">The **Color Picker**, annotated</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-346">1</span><span class="sxs-lookup"><span data-stu-id="1c365-346">1</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-347">底纹</span><span class="sxs-lookup"><span data-stu-id="1c365-347">Shades</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-348">2</span><span class="sxs-lookup"><span data-stu-id="1c365-348">2</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-349">目视器</span><span class="sxs-lookup"><span data-stu-id="1c365-349">Eyedropper</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1c365-350">有关详细信息，请导航到使用目 [视器从页面上采样颜色](#sample-a-color-off-the-page-with-the-eyedropper)。</span><span class="sxs-lookup"><span data-stu-id="1c365-350">For more information, navigate to [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-351">3</span><span class="sxs-lookup"><span data-stu-id="1c365-351">3</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-352">复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="1c365-352">Copy To Clipboard</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1c365-353">将 **"显示值"** 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1c365-353">Copy the **Display Value** to your clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-354">4</span><span class="sxs-lookup"><span data-stu-id="1c365-354">4</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-355">显示值</span><span class="sxs-lookup"><span data-stu-id="1c365-355">Display Value</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1c365-356">颜色的 RGBA、HSLA 或 Hex 表示形式。</span><span class="sxs-lookup"><span data-stu-id="1c365-356">The RGBA, HSLA, or Hex representation of the color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-357">5</span><span class="sxs-lookup"><span data-stu-id="1c365-357">5</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-358">调色板</span><span class="sxs-lookup"><span data-stu-id="1c365-358">Color Palette</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1c365-359">选择其中一个正方形以将颜色更改为该正方形。</span><span class="sxs-lookup"><span data-stu-id="1c365-359">Choose one of the squares to change the color to that square.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-360">6</span><span class="sxs-lookup"><span data-stu-id="1c365-360">6</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-361">Hue</span><span class="sxs-lookup"><span data-stu-id="1c365-361">Hue</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-362">7</span><span class="sxs-lookup"><span data-stu-id="1c365-362">7</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-363">Opacity</span><span class="sxs-lookup"><span data-stu-id="1c365-363">Opacity</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-364">8</span><span class="sxs-lookup"><span data-stu-id="1c365-364">8</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-365">显示值切换器</span><span class="sxs-lookup"><span data-stu-id="1c365-365">Display Value Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1c365-366">在当前颜色的 RGBA、HSLA 和 Hex 表示法之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="1c365-366">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1c365-367">9</span><span class="sxs-lookup"><span data-stu-id="1c365-367">9</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="1c365-368">调色板切换器</span><span class="sxs-lookup"><span data-stu-id="1c365-368">Color Palette Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1c365-369">在"材料 [设计"调色板][MaterialDesignColorSystem]、自定义调色板或页面颜色调色板之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="1c365-369">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="1c365-370">DevTools 根据它在样式表内找到的颜色生成页面调色板。</span><span class="sxs-lookup"><span data-stu-id="1c365-370">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  
   :::column-end:::
:::row-end:::  

#### <a name="sample-a-color-off-the-page-with-the-eyedropper"></a><span data-ttu-id="1c365-371">使用目视器为页面采样颜色</span><span class="sxs-lookup"><span data-stu-id="1c365-371">Sample a color off the page with the Eyedropper</span></span>  

<span data-ttu-id="1c365-372">打开颜色 **选取器**时，取色器 **\ (** 取色器 ![ ](../media/eyedropper-icon.msft.png) \) 默认打开。</span><span class="sxs-lookup"><span data-stu-id="1c365-372">When you open the **Color Picker**, the **Eyedropper** \(![Eyedropper](../media/eyedropper-icon.msft.png)\) is on by default.</span></span>  <span data-ttu-id="1c365-373">完成以下操作，将所选颜色更改为页面上的某种其他颜色。</span><span class="sxs-lookup"><span data-stu-id="1c365-373">Complete the following actions to change the selected color to some other color on the page.</span></span>  

1.  <span data-ttu-id="1c365-374">将鼠标悬停在视口中的目标颜色上。</span><span class="sxs-lookup"><span data-stu-id="1c365-374">Hover on the target color in the viewport.</span></span>  
1.  <span data-ttu-id="1c365-375">选择确认。</span><span class="sxs-lookup"><span data-stu-id="1c365-375">Choose to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1c365-376">在下图中，颜色 **选取** 器显示 的当前颜色值 `rgba(0,0,0,0.7)` 接近黑色。</span><span class="sxs-lookup"><span data-stu-id="1c365-376">In the following figure, the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="1c365-377">选择后，特定颜色应更改为当前在视口中突出显示的黑色版本。</span><span class="sxs-lookup"><span data-stu-id="1c365-377">The specific color should change to the version of black that is currently highlighted in the viewport after you chose it.</span></span>  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="使用目视器" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       <span data-ttu-id="1c365-379">使用目视器</span><span class="sxs-lookup"><span data-stu-id="1c365-379">Using the Eyedropper</span></span>  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1c365-380">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="1c365-380">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令"  
[DevToolsCSSGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "向类添加伪状态 - 查看和更改 CSS |Microsoft Docs"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "查看元素的 CSS - 查看和更改 CSS |Microsoft Docs"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "强制 Microsoft Edge DevTools 进入打印预览模式 (CSS 打印媒体类型) |Microsoft Docs"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#make-a-minified-file-readable "使缩小文件可读 - JavaScript 调试|Microsoft Docs"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统 - 材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "方框模型|MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型 - 特定|MDN"  

> [!NOTE]
> <span data-ttu-id="1c365-390">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1c365-390">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1c365-391">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="1c365-391">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="1c365-393">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1c365-393">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  