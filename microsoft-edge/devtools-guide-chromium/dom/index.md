---
description: 如何查看节点、搜索节点、编辑节点、控制台中的引用节点、节点更改中断等。
title: 查看和更改 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 5b12b984aed7e35ce11dd45e8bc33f5d5fd454f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231102"
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

# <span data-ttu-id="9e494-104">查看和更改 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="9e494-104">Get started with viewing and changing the DOM</span></span>  

<span data-ttu-id="9e494-105">完成这些交互式教程，了解使用 Microsoft Edge DevTools 查看和更改页面 DOM 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="9e494-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="9e494-106">本教程假定你了解 DOM 和 HTML 的区别。</span><span class="sxs-lookup"><span data-stu-id="9e494-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="9e494-107">导航到 [附录：HTML 与 DOM，](#appendix-html-versus-the-dom) 了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="9e494-107">Navigate to [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="9e494-108">打开 DOM 示例</span><span class="sxs-lookup"><span data-stu-id="9e494-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="9e494-109">按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择 **DOM 示例** 以在新建选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="9e494-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="9e494-110">DOM 示例</span><span class="sxs-lookup"><span data-stu-id="9e494-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="9e494-111">查看 DOM 节点</span><span class="sxs-lookup"><span data-stu-id="9e494-111">View DOM nodes</span></span>  

<span data-ttu-id="9e494-112">在"元素"面板的 DOM 树中，您可以在 DevTools 中执行所有与 DOM 相关的活动。</span><span class="sxs-lookup"><span data-stu-id="9e494-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="9e494-113">检查节点</span><span class="sxs-lookup"><span data-stu-id="9e494-113">Inspect a node</span></span>  

<span data-ttu-id="9e494-114">当你对特定 DOM 节点感兴趣时， **检查** 是打开 DevTools 并调查该节点的一种快速方法。</span><span class="sxs-lookup"><span data-stu-id="9e494-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="9e494-115">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-116">在 **"检查节点"下**，右选择 **"一角"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-116">Under **Inspect a Node**, right-choose **Michelangelo** and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="9e494-118">检查节点</span><span class="sxs-lookup"><span data-stu-id="9e494-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="9e494-119">将 **打开** DevTools 的元素面板。</span><span class="sxs-lookup"><span data-stu-id="9e494-119">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="9e494-120">在 **DOM 树中突出显示**。</span><span class="sxs-lookup"><span data-stu-id="9e494-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="突出显示"一文集"节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="9e494-122">突出显示 `Michelangelo` 节点</span><span class="sxs-lookup"><span data-stu-id="9e494-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="9e494-123">单击\*\*\*\* ![ DevTools (左上角的"检查) 检查 \) ][ImageInspectIcon] 图标。</span><span class="sxs-lookup"><span data-stu-id="9e494-123">Click the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text=""检查"图标" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="9e494-125">" **检查"** 图标</span><span class="sxs-lookup"><span data-stu-id="9e494-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="9e494-126">在 **"检查节点"** 下，单击 **"东京"** 文本。</span><span class="sxs-lookup"><span data-stu-id="9e494-126">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="9e494-127">现在 `<li>Tokyo</li>` ，在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="9e494-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="9e494-128">检查节点也是查看和更改节点样式的第一步。</span><span class="sxs-lookup"><span data-stu-id="9e494-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="9e494-129">导航到["查看和更改 CSS 入门"。][DevToolsCssGetStarted]</span><span class="sxs-lookup"><span data-stu-id="9e494-129">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="9e494-130">使用键盘导航 DOM 树</span><span class="sxs-lookup"><span data-stu-id="9e494-130">Navigate the DOM Tree with a keyboard</span></span>  

<span data-ttu-id="9e494-131">选择 DOM 树中的节点后，可以使用键盘导航 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="9e494-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="9e494-132">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-133">在 **"使用键盘导航 DOM 树"** 下，右键选择 **"响铃"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-133">Under **Navigate the DOM Tree with a Keyboard**, right-choose **Ringo** and choose **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="9e494-134">在 DOM 树中选中。</span><span class="sxs-lookup"><span data-stu-id="9e494-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="检查 Ringo 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="9e494-136">检查 `Ringo` 节点</span><span class="sxs-lookup"><span data-stu-id="9e494-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="9e494-137">按 `Up` 箭头键 2 次。</span><span class="sxs-lookup"><span data-stu-id="9e494-137">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="9e494-138">已选中。</span><span class="sxs-lookup"><span data-stu-id="9e494-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="检查 ul 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="9e494-140">检查 `ul` 节点</span><span class="sxs-lookup"><span data-stu-id="9e494-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9e494-141">按 `Left` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="9e494-141">Press the `Left` arrow key.</span></span>  <span data-ttu-id="9e494-142">列表 `<ul>` 折叠。</span><span class="sxs-lookup"><span data-stu-id="9e494-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="9e494-143">再次 `Left` 按箭头键。</span><span class="sxs-lookup"><span data-stu-id="9e494-143">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="9e494-144">选择节点 `<ul>` 的父节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="9e494-145">在这种情况下，它是 `<div>` `navigate-the-dom-tree-with-a-keyboard-1` ID。</span><span class="sxs-lookup"><span data-stu-id="9e494-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="9e494-146">按 `Down` 箭头键 2 次，以便重新选择刚刚 `<ul>` 折叠的列表。</span><span class="sxs-lookup"><span data-stu-id="9e494-146">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="9e494-147">应如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e494-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="9e494-148">按 `Right` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="9e494-148">Press the `Right` arrow key.</span></span>  <span data-ttu-id="9e494-149">列表将展开。</span><span class="sxs-lookup"><span data-stu-id="9e494-149">The list expands.</span></span>  

### <span data-ttu-id="9e494-150">滚动到视图</span><span class="sxs-lookup"><span data-stu-id="9e494-150">Scroll into view</span></span>  

<span data-ttu-id="9e494-151">查看 DOM 树时，您可能会对当前不在视口中的 DOM 节点感兴趣。</span><span class="sxs-lookup"><span data-stu-id="9e494-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="9e494-152">例如，假设您滚动到页面底部，并且对页面顶部的节点 `<h1>` 感兴趣。</span><span class="sxs-lookup"><span data-stu-id="9e494-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="9e494-153">**滚动到视图中** 可快速重新定位视口，以便查看节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to review the node.</span></span>  

1.  <span data-ttu-id="9e494-154">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-155">在 **"滚动到视图**"下，右选择 **"Magritte"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-155">Under **Scroll into View**, right-choose **Magritte** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="9e494-156">滚动到 DOM 示例页的底部。</span><span class="sxs-lookup"><span data-stu-id="9e494-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="9e494-157">仍 `<li>Magritte</li>` 应在 DOM 树中选择节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="9e494-158">如果不是，请返回到" [滚动到视图](#scroll-into-view) "并重新开始。</span><span class="sxs-lookup"><span data-stu-id="9e494-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="9e494-159">将鼠标悬停在节点上，打开上下文菜单 `<li>Magritte</li>` \ (右键单击\) ，然后选择 **"滚动到视图"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-159">Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.</span></span>  <span data-ttu-id="9e494-160">视区将向上滚动，以便你可以查看 **Magritte** 节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-160">Your viewport scrolls back up so that you may review the **Magritte** node.</span></span>  <span data-ttu-id="9e494-161">导航到 [附录：如果](#appendix-missing-options) 无法查看"滚动到视图"选项，则 **缺少** 选项。</span><span class="sxs-lookup"><span data-stu-id="9e494-161">Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to review the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="滚动到视图" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="9e494-163">滚动到视图</span><span class="sxs-lookup"><span data-stu-id="9e494-163">Scroll into view</span></span>**  
    :::image-end:::  

### <span data-ttu-id="9e494-164">搜索节点</span><span class="sxs-lookup"><span data-stu-id="9e494-164">Search for nodes</span></span>  

<span data-ttu-id="9e494-165">您可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="9e494-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="9e494-166">将光标焦点放在 **"元素"面板** 上。</span><span class="sxs-lookup"><span data-stu-id="9e494-166">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="9e494-167">选择 `Control` + `F` \ (Windows、Linux\) `Command` + `F` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="9e494-167">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="9e494-168">搜索栏将在 DOM 树的底部打开。</span><span class="sxs-lookup"><span data-stu-id="9e494-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="9e494-169">键入 `The Moon is a Harsh Mistress`。</span><span class="sxs-lookup"><span data-stu-id="9e494-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="9e494-170">最后一句在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="9e494-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="在搜索栏中突出显示查询" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="9e494-172">在搜索栏中突出显示查询</span><span class="sxs-lookup"><span data-stu-id="9e494-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9e494-173">如上所述，搜索栏还支持 CSS 和 XPath 选择器。</span><span class="sxs-lookup"><span data-stu-id="9e494-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="9e494-174">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="9e494-174">Edit the DOM</span></span>  

<span data-ttu-id="9e494-175">您可以直接编辑 DOM，并查看更改对页面有何影响。</span><span class="sxs-lookup"><span data-stu-id="9e494-175">You may edit the DOM on the fly and review how the changes affect the page.</span></span>  

### <span data-ttu-id="9e494-176">编辑内容</span><span class="sxs-lookup"><span data-stu-id="9e494-176">Edit content</span></span>  

<span data-ttu-id="9e494-177">若要编辑节点的内容，请双击 DOM 树中的内容。</span><span class="sxs-lookup"><span data-stu-id="9e494-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="9e494-178">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-179">在 **"编辑内容**"下，右选择 **"Michelle"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-179">Under **Edit Content**, right-choose **Michelle** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-180">在 DOM 树中，双击 `Michelle` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="9e494-181">换句话说，双击和 之间的 `<li>` 文本 `</li>` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="9e494-182">文本将突出显示以指示已选中。</span><span class="sxs-lookup"><span data-stu-id="9e494-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="编辑文本" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="9e494-184">编辑文本</span><span class="sxs-lookup"><span data-stu-id="9e494-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9e494-185">删除 `Michelle` ，键入 `Leela` ，然后选择 `Enter` 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="9e494-185">Delete `Michelle`, type `Leela`, then select `Enter` to confirm the change.</span></span>  <span data-ttu-id="9e494-186">DOM 中的文本从**Michelle 更改为\*\*\*\*小雷**。</span><span class="sxs-lookup"><span data-stu-id="9e494-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="9e494-187">编辑属性</span><span class="sxs-lookup"><span data-stu-id="9e494-187">Edit attributes</span></span>  

<span data-ttu-id="9e494-188">若要编辑属性，请双击属性名称或值。</span><span class="sxs-lookup"><span data-stu-id="9e494-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="9e494-189">按照说明了解如何向节点添加属性。</span><span class="sxs-lookup"><span data-stu-id="9e494-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="9e494-190">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-191">在 **"编辑属性"下**，右选择 **"放大**"，然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-191">Under **Edit Attributes**, right-choose **Howard** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="9e494-192">双击 `<li>` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-192">Double-click `<li>`.</span></span>  <span data-ttu-id="9e494-193">突出显示文本以指示节点已选中。</span><span class="sxs-lookup"><span data-stu-id="9e494-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="编辑节点" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="9e494-195">编辑节点</span><span class="sxs-lookup"><span data-stu-id="9e494-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9e494-196">按 `Right` 箭头键，添加空格，键入 `style="background-color:gold"` ，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-196">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then select `Enter`.</span></span>  <span data-ttu-id="9e494-197">节点的背景颜色将更改为金色。</span><span class="sxs-lookup"><span data-stu-id="9e494-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="向节点添加样式属性" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="9e494-199">向 `style` 节点添加属性</span><span class="sxs-lookup"><span data-stu-id="9e494-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="9e494-200">编辑节点类型</span><span class="sxs-lookup"><span data-stu-id="9e494-200">Edit node type</span></span>  

<span data-ttu-id="9e494-201">若要编辑节点的类型，请双击该类型，然后键入新类型。</span><span class="sxs-lookup"><span data-stu-id="9e494-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="9e494-202">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-203">在 **"编辑节点类型"下**，右选择 **"百**科"，然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-203">Under **Edit Node Type**, right-choose **Hank** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-204">双击 `<li>` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-204">Double-click `<li>`.</span></span>  <span data-ttu-id="9e494-205">文本 `li` 突出显示。</span><span class="sxs-lookup"><span data-stu-id="9e494-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="9e494-206">删除 `li` ，键入 `button` ，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-206">Delete `li`, type `button`, then select `Enter`.</span></span>  <span data-ttu-id="9e494-207">节点 `<li>` 将更改到 `<button>` 节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="将节点类型更改为按钮" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="9e494-209">将节点类型更改为</span><span class="sxs-lookup"><span data-stu-id="9e494-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <span data-ttu-id="9e494-210">对 DOM 节点重新排序</span><span class="sxs-lookup"><span data-stu-id="9e494-210">Reorder DOM nodes</span></span>  

<span data-ttu-id="9e494-211">拖动节点以重新排序。</span><span class="sxs-lookup"><span data-stu-id="9e494-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="9e494-212">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-213">在 **"重新排序 DOM 节点**"下，右选择**Elvis Presley**并选择 **"检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-213">Under **Reorder DOM Nodes**, right-choose **Elvis Presley** and choose **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9e494-214">它是列表中的最后一项。</span><span class="sxs-lookup"><span data-stu-id="9e494-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="9e494-215">在 DOM 树中，拖动 `<li>Elvis Presley</li>` 到列表顶部。</span><span class="sxs-lookup"><span data-stu-id="9e494-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="将节点拖动到列表顶部" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="9e494-217">将节点拖动到列表顶部</span><span class="sxs-lookup"><span data-stu-id="9e494-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="9e494-218">强制状态</span><span class="sxs-lookup"><span data-stu-id="9e494-218">Force state</span></span>  

<span data-ttu-id="9e494-219">你可以强制节点保持状态，包括 `:active` 、 和 `:hover` `:focus` `:visited` `:focus-within` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="9e494-220">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-221">在 **"强制"** 状态下，将鼠标悬停在 **"四分之一"上**。</span><span class="sxs-lookup"><span data-stu-id="9e494-221">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="9e494-222">背景色变为橙色。</span><span class="sxs-lookup"><span data-stu-id="9e494-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="9e494-223">右选择 **"四角"，** 然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-223">Right-choose **The Lord of the Flies** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-224">右键单击 `<li class="demo--hover">The Lord of the Flies</li>` 并选择 **"强制状态**  >  **：悬停"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-224">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and choose **Force State** > **:hover**.</span></span>  <span data-ttu-id="9e494-225">导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="9e494-225">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  <span data-ttu-id="9e494-226">即使你实际上没有将鼠标悬停在节点上，背景颜色仍保持橙色。</span><span class="sxs-lookup"><span data-stu-id="9e494-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="9e494-227">隐藏节点</span><span class="sxs-lookup"><span data-stu-id="9e494-227">Hide a node</span></span>  

<span data-ttu-id="9e494-228">选择 `H` 以隐藏节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-228">Select `H` to hide a node.</span></span>  

1.  <span data-ttu-id="9e494-229">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-230">在 **"隐藏节点"** 下，右选择 **"星形我的目的地"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-230">Under **Hide a node**, right-choose **The Stars My Destination** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-231">按 `H` 该键。</span><span class="sxs-lookup"><span data-stu-id="9e494-231">Press the `H` key.</span></span>  <span data-ttu-id="9e494-232">节点处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="9e494-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="隐藏后的节点在 DOM 树中的外观" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="9e494-234">隐藏后的节点在 DOM 树中的外观</span><span class="sxs-lookup"><span data-stu-id="9e494-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9e494-235">再次 `H` 按该键。</span><span class="sxs-lookup"><span data-stu-id="9e494-235">Press the `H` key again.</span></span>  <span data-ttu-id="9e494-236">节点将再次显示。</span><span class="sxs-lookup"><span data-stu-id="9e494-236">The node is shown again.</span></span>  

### <span data-ttu-id="9e494-237">删除节点</span><span class="sxs-lookup"><span data-stu-id="9e494-237">Delete a node</span></span>  

<span data-ttu-id="9e494-238">选择 `Delete` 以删除节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-238">Select `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="9e494-239">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-240">在 **"删除节点"下**，右选择 **"基础**"，然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-240">Under **Delete a Node**, right-choose **Foundation** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-241">按 `Delete` 该键。</span><span class="sxs-lookup"><span data-stu-id="9e494-241">Press the `Delete` key.</span></span>  <span data-ttu-id="9e494-242">删除节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="9e494-243">选择 `Control` + `Z` \ (Windows、Linux\) `Command` + `Z` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="9e494-243">Select `Control`+`Z` \(Windows, Linux\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="9e494-244">最后一个操作将撤消，节点将重新出现。</span><span class="sxs-lookup"><span data-stu-id="9e494-244">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="9e494-245">控制台中的访问节点</span><span class="sxs-lookup"><span data-stu-id="9e494-245">Access nodes in the Console</span></span>  

<span data-ttu-id="9e494-246">DevTools 提供了一些快捷方式，用于从控制台访问 DOM 节点或获取对每个节点的 JavaScript 引用。</span><span class="sxs-lookup"><span data-stu-id="9e494-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="9e494-247">引用当前选定的节点，其价格为 $0</span><span class="sxs-lookup"><span data-stu-id="9e494-247">Reference the currently-selected node with $0</span></span>  

<span data-ttu-id="9e494-248">检查节点时，节点旁边的文本意味着可以使用变量 `== $0` 在控制台中引用此节点 `$0` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="9e494-249">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-250">在 **"引用当前选定的节点与 $0"** 下，右选择"深暗**的**左手"，然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-250">Under **Reference the currently-selected node with $0**, right-choose **The Left Hand of Darkness** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-251">按 `Escape` 该键打开控制台箱。</span><span class="sxs-lookup"><span data-stu-id="9e494-251">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="9e494-252">键入 `$0` 并按 `Enter` 该键。</span><span class="sxs-lookup"><span data-stu-id="9e494-252">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="9e494-253">表达式的结果显示计算 `$0` 结果为 `<li>The Left Hand of Darkness</li>` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="控制台中第一个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="9e494-255">控制台中第一 `$0` 个表达式 **的结果**</span><span class="sxs-lookup"><span data-stu-id="9e494-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9e494-256">将鼠标悬停在结果上方。</span><span class="sxs-lookup"><span data-stu-id="9e494-256">Hover over the result.</span></span>  <span data-ttu-id="9e494-257">该节点在视口中突出显示。</span><span class="sxs-lookup"><span data-stu-id="9e494-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="9e494-258">在 `<li>Dune</li>` DOM 树中单击， `$0` 再次键入控制台，然后再次 `Enter` 选择。</span><span class="sxs-lookup"><span data-stu-id="9e494-258">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then select `Enter` again.</span></span>  <span data-ttu-id="9e494-259">现在， `$0` 计算结果为 `<li>Dune</li>` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="控制台中第二个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="9e494-261">控制台中第 `$0` 二个表达式 **的结果**</span><span class="sxs-lookup"><span data-stu-id="9e494-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="9e494-262">存储为全局变量</span><span class="sxs-lookup"><span data-stu-id="9e494-262">Store as global variable</span></span>  

<span data-ttu-id="9e494-263">如果需要多次引用回节点，请存储为全局变量。</span><span class="sxs-lookup"><span data-stu-id="9e494-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="9e494-264">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-265">在 **"存储作为全局变量"下**，右选择 **"大睡眠"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-265">Under **Store as global variable**, right-choose **The Big Sleep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-266">在 `<li>The Big Sleep</li>` DOM 树中右键单击并选择 **"存储"作为全局变量**。</span><span class="sxs-lookup"><span data-stu-id="9e494-266">Right-click `<li>The Big Sleep</li>` in the DOM Tree and choose **Store as global variable**.</span></span>  <span data-ttu-id="9e494-267">导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="9e494-267">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="9e494-268">在 `temp1` 控制台中键入，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-268">Type `temp1` in the Console and then select `Enter`.</span></span>  <span data-ttu-id="9e494-269">表达式的结果显示变量计算结果为节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 表达式的结果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="9e494-271">表达式 `temp1` 的结果</span><span class="sxs-lookup"><span data-stu-id="9e494-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="9e494-272">复制 JS 路径</span><span class="sxs-lookup"><span data-stu-id="9e494-272">Copy JS path</span></span>  

<span data-ttu-id="9e494-273">当你需要在自动测试中引用该节点时，将 JavaScript 路径复制到该节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="9e494-274">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-275">在 **"复制 JS 路径**"下，右选择 **"放大百分之百"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-275">Under **Copy JS path**, right-choose **The Brothers Karamazov** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-276">在 `<li>The Brothers Karamazov</li>` DOM 树中右键单击，然后选择 **"复制**  >  **JS 路径"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-276">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and choose **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="9e494-277">`document.querySelector()`解析为节点的表达式已复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="9e494-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="9e494-278">选择 `Control` + `V` \ (Windows、Linux\) 或 `Command` + `V` \ (macOS\) 将表达式粘贴到控制台中。</span><span class="sxs-lookup"><span data-stu-id="9e494-278">Select `Control`+`V` \(Windows, Linux\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="9e494-279">选择 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="9e494-279">Select `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="复制 JS 路径表达式的结果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="9e494-281">复制 JS **路径** 表达式的结果</span><span class="sxs-lookup"><span data-stu-id="9e494-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <span data-ttu-id="9e494-282">DOM 更改中断</span><span class="sxs-lookup"><span data-stu-id="9e494-282">Break on DOM changes</span></span>  

<span data-ttu-id="9e494-283">DevTools 使您能够在 JavaScript 修改 DOM 时暂停页面的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="9e494-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="9e494-284">中断属性修改</span><span class="sxs-lookup"><span data-stu-id="9e494-284">Break on attribute modifications</span></span>  

<span data-ttu-id="9e494-285">当您想要暂停导致节点的任何属性更改的 JavaScript 时，请使用属性修改断点。</span><span class="sxs-lookup"><span data-stu-id="9e494-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="9e494-286">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-287">在**属性修改中断下**，右选择**Sauerkraut，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-287">Under **Break on attribute modifications**, right-choose **Sauerkraut** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-288">在 DOM 树中，右键单击 `<li id="target">Sauerkraut</li>` 并选择"属性**修改时**  >  **中断"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-288">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and choose **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="9e494-289">导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="9e494-289">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="中断属性修改" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="9e494-291">中断属性修改</span><span class="sxs-lookup"><span data-stu-id="9e494-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="9e494-292">下一步，将指示你单击暂停页面代码的按钮。</span><span class="sxs-lookup"><span data-stu-id="9e494-292">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="9e494-293">暂停页面后，你无法再滚动页面。</span><span class="sxs-lookup"><span data-stu-id="9e494-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="9e494-294">必须选择" **恢复** 脚本 ![ " ("恢复脚本") 使页面可再次 ][ImageResumeScriptIcon] 滚动。</span><span class="sxs-lookup"><span data-stu-id="9e494-294">You must choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="在何处继续运行脚本" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="9e494-296">在何处继续运行脚本</span><span class="sxs-lookup"><span data-stu-id="9e494-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9e494-297">单击 **上面的"设置背景** "按钮。</span><span class="sxs-lookup"><span data-stu-id="9e494-297">Click the **Set Background** button above.</span></span>  <span data-ttu-id="9e494-298">这会将 `style` 节点的属性设置为 `background-color:thistle` 。</span><span class="sxs-lookup"><span data-stu-id="9e494-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="9e494-299">DevTools 暂停页面并突出显示导致属性更改的代码。</span><span class="sxs-lookup"><span data-stu-id="9e494-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="9e494-300">选择 **"恢复脚本** (![ 恢复脚本 ][ImageResumeScriptIcon] \) ，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="9e494-300">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span></span>  
    
### <span data-ttu-id="9e494-301">节点删除时中断</span><span class="sxs-lookup"><span data-stu-id="9e494-301">Break on node removal</span></span>  

<span data-ttu-id="9e494-302">如果要在删除特定节点时暂停，请使用节点删除断点。</span><span class="sxs-lookup"><span data-stu-id="9e494-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="9e494-303">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-304">在 **"删除节点时中断"下**，右选择 **"管理**程序"，然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-304">Under **Break on Node Removal**, right-choose **Neuromancer** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-305">在 DOM 树中，右键单击 `<li id="target">Neuromancer</li>` 并选择"**删除节点**  >  **时中断"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-305">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and choose **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="9e494-306">导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="9e494-306">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="9e494-307">单击 **上面的"删除** "按钮。</span><span class="sxs-lookup"><span data-stu-id="9e494-307">Click the **Delete** button above.</span></span>  <span data-ttu-id="9e494-308">DevTools 暂停页面并突出显示导致删除节点的代码。</span><span class="sxs-lookup"><span data-stu-id="9e494-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="9e494-309">Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="9e494-309">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
### <span data-ttu-id="9e494-310">在子树修改上中断</span><span class="sxs-lookup"><span data-stu-id="9e494-310">Break on subtree modifications</span></span>  

<span data-ttu-id="9e494-311">在节点上放入子树修改断点后，当添加或删除节点的任何后代时，DevTools 将暂停页面。</span><span class="sxs-lookup"><span data-stu-id="9e494-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="9e494-312">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="9e494-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9e494-313">在 **"子树修改的**中断"下，右选择"深度时射击 **"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-313">Under **Break on Subtree Modifications**, right-choose **A Fire Upon The Deep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="9e494-314">在 DOM 树中，右键单击上方的节点，然后选择"在子树修改 `<ul id="target">` `<li>A Fire Upon the Deep</li>` **时**  >  **中断"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-314">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and choose **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="9e494-315">导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="9e494-315">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="9e494-316">选择 **"添加子级"。**</span><span class="sxs-lookup"><span data-stu-id="9e494-316">Choose **Add Child**.</span></span>  <span data-ttu-id="9e494-317">代码会暂停，因为 `<li>` 节点已添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="9e494-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="9e494-318">Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="9e494-318">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
## <span data-ttu-id="9e494-319">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9e494-319">Next steps</span></span>  

<span data-ttu-id="9e494-320">这涵盖了 DevTools 中大部分与 DOM 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="9e494-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="9e494-321">通过右键单击 DOM 树中的节点并尝试本教程未涵盖的其他选项，你可以发现其余的节点。</span><span class="sxs-lookup"><span data-stu-id="9e494-321">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="9e494-322">导航到 [元素面板键盘快捷方式][DevToolsShortcutsElements]。</span><span class="sxs-lookup"><span data-stu-id="9e494-322">Navigate to [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="9e494-323">查看 [Microsoft Edge DevTools 主页][MicrosoftEdgeDevTools] ，了解可以使用 DevTools 执行的所有其他功能。</span><span class="sxs-lookup"><span data-stu-id="9e494-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <span data-ttu-id="9e494-324">附录：HTML 与 DOM</span><span class="sxs-lookup"><span data-stu-id="9e494-324">Appendix: HTML versus the DOM</span></span>  

<span data-ttu-id="9e494-325">下一节快速介绍了 HTML 和 DOM 的区别。</span><span class="sxs-lookup"><span data-stu-id="9e494-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9e494-326">当您使用 Web 浏览器请求页面时，服务器将返回类似以下代码段的 HTML</span><span class="sxs-lookup"><span data-stu-id="9e494-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

      ```html
      <!doctype html>
      <html>
          <head>
              <title>Hello, world!</title>
          </head>
          <body>
              <h1>Hello, world!</h1>
              <p>This is a hypertext document on the World Wide Web.</p>
              <script src="/script.js" async></script>
          </body>
      </html>
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="9e494-327">浏览器分析 HTML 并创建对象树，如以下列表所示。</span><span class="sxs-lookup"><span data-stu-id="9e494-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
      ```dom
      html
          head
              title
          body
              h1
              p
              script
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9e494-328">此表示页面内容的对象或节点树称为 DOM。</span><span class="sxs-lookup"><span data-stu-id="9e494-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9e494-329">现在它看起来与 HTML 相同，但假定 HTML 底部引用的脚本运行以下代码段。</span><span class="sxs-lookup"><span data-stu-id="9e494-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="9e494-330">该代码将删除该 `h1` 节点，并将另 `p` 一个节点添加到 DOM。</span><span class="sxs-lookup"><span data-stu-id="9e494-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="9e494-331">完整的 DOM 现在将显示以下列表。</span><span class="sxs-lookup"><span data-stu-id="9e494-331">The complete DOM now displays the following list.</span></span>  
      
      ```dom
      html
          head
              title
          body
              p
              script
              p
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9e494-332">页面的 HTML 现在不同于 DOM。</span><span class="sxs-lookup"><span data-stu-id="9e494-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="9e494-333">换句话说，HTML 表示初始页面内容，DOM 表示当前页面内容。</span><span class="sxs-lookup"><span data-stu-id="9e494-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="9e494-334">当 JavaScript 添加、删除或编辑节点时，DOM 将不同于 HTML。</span><span class="sxs-lookup"><span data-stu-id="9e494-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="9e494-335">导航 [到 DOM 简介][MDNIntroductionToDOM] 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="9e494-335">Navigate to [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <span data-ttu-id="9e494-336">附录：缺少选项</span><span class="sxs-lookup"><span data-stu-id="9e494-336">Appendix: Missing options</span></span>  

<span data-ttu-id="9e494-337">本教程中的许多说明都指示你右键单击 DOM 树中的节点，然后从弹出的上下文菜单中选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="9e494-337">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="9e494-338">如果未显示上下文菜单中的指定选项，请尝试右键单击离开节点文本。</span><span class="sxs-lookup"><span data-stu-id="9e494-338">If the specified option in the context menu is not displayed, try right-clicking away from the node text.</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="如果未显示所有选项，选择什么位置" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="9e494-340">如果未显示所有选项，选择什么位置</span><span class="sxs-lookup"><span data-stu-id="9e494-340">Where to choose if all of the options are not displayed</span></span>  
:::image-end:::  

## <span data-ttu-id="9e494-341">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="9e494-341">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具 |Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "查看和更改 CSS 入门 |Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-panel-keyboard-shortcuts "元素面板键盘快捷方式 - Microsoft Edge DevTools 键盘快捷方式 |Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM 示例 |小故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 |MDN"  

> [!NOTE]
> <span data-ttu-id="9e494-347">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9e494-347">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9e494-348">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9e494-348">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9e494-350">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9e494-350">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
