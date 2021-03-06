---
description: 如何查看节点、搜索节点、编辑节点、控制台中的引用节点、中断节点更改等。
title: 开始查看和更改 DOM
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: bb2b733cfa3597c47f0a20de00e9c8b506e7c41c
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398327"
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

# <a name="get-started-with-viewing-and-changing-the-dom"></a><span data-ttu-id="5d14a-104">开始查看和更改 DOM</span><span class="sxs-lookup"><span data-stu-id="5d14a-104">Get started with viewing and changing the DOM</span></span>  

<span data-ttu-id="5d14a-105">完成这些交互式教程，了解使用 Microsoft Edge DevTools 查看和更改页面 DOM 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="5d14a-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="5d14a-106">本教程假定你了解 DOM 和 HTML 的区别。</span><span class="sxs-lookup"><span data-stu-id="5d14a-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="5d14a-107">导航到 [附录：HTML 与 DOM，](#appendix-html-versus-the-dom) 了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="5d14a-107">Navigate to [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <a name="open-dom-examples"></a><span data-ttu-id="5d14a-108">打开 DOM 示例</span><span class="sxs-lookup"><span data-stu-id="5d14a-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="5d14a-109">按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择 **DOM 示例** 以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="5d14a-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="5d14a-110">DOM 示例</span><span class="sxs-lookup"><span data-stu-id="5d14a-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <a name="view-dom-nodes"></a><span data-ttu-id="5d14a-111">查看 DOM 节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-111">View DOM nodes</span></span>  

<span data-ttu-id="5d14a-112">在"元素"面板的 DOM 树中，您可以在 DevTools 中执行所有与 DOM 相关的活动。</span><span class="sxs-lookup"><span data-stu-id="5d14a-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <a name="inspect-a-node"></a><span data-ttu-id="5d14a-113">检查节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-113">Inspect a node</span></span>  

<span data-ttu-id="5d14a-114">当你对特定的 DOM 节点感兴趣时， **检查** 是打开 DevTools 并调查该节点的一种快速方法。</span><span class="sxs-lookup"><span data-stu-id="5d14a-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="5d14a-115">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-116">在 **"检查节点"下**，右选择 **"一角"** 并选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-116">Under **Inspect a Node**, right-choose **Michelangelo** and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="5d14a-118">检查节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="5d14a-119">将 **打开** DevTools 的元素工具。</span><span class="sxs-lookup"><span data-stu-id="5d14a-119">The **Elements** tool of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="5d14a-120">在 **DOM 树中突出显示**。</span><span class="sxs-lookup"><span data-stu-id="5d14a-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="突出显示"一家"节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="5d14a-122">突出显示 `Michelangelo` 节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="5d14a-123">Choose the **Inspect** \ (![ Inspect ][ImageInspectIcon] \) icon in the top-left corner of DevTools.</span><span class="sxs-lookup"><span data-stu-id="5d14a-123">Choose the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text=""检查"图标" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="5d14a-125">" **检查"** 图标</span><span class="sxs-lookup"><span data-stu-id="5d14a-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="5d14a-126">在 **"检查节点"下**，选择 **"东京** "文本。</span><span class="sxs-lookup"><span data-stu-id="5d14a-126">Under **Inspect a Node**, choose the **Tokyo** text.</span></span>  <span data-ttu-id="5d14a-127">现在 `<li>Tokyo</li>` ，在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="5d14a-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="5d14a-128">检查节点也是查看和更改节点样式的第一步。</span><span class="sxs-lookup"><span data-stu-id="5d14a-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="5d14a-129">导航到["开始查看和更改 CSS"。][DevToolsCssGetStarted]</span><span class="sxs-lookup"><span data-stu-id="5d14a-129">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <a name="navigate-the-dom-tree-with-a-keyboard"></a><span data-ttu-id="5d14a-130">使用键盘导航 DOM 树</span><span class="sxs-lookup"><span data-stu-id="5d14a-130">Navigate the DOM Tree with a keyboard</span></span>  

<span data-ttu-id="5d14a-131">选择 DOM 树中的节点后，可以使用键盘导航 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="5d14a-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="5d14a-132">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-133">在 **"使用键盘导航 DOM 树"** 下，右键选择 **"圈"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-133">Under **Navigate the DOM Tree with a Keyboard**, right-choose **Ringo** and choose **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="5d14a-134">在 DOM 树中选中。</span><span class="sxs-lookup"><span data-stu-id="5d14a-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="检查 Ringo 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="5d14a-136">检查 `Ringo` 节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="5d14a-137">选择 `Up` 箭头键 2 次。</span><span class="sxs-lookup"><span data-stu-id="5d14a-137">Select the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="5d14a-138">已选中。</span><span class="sxs-lookup"><span data-stu-id="5d14a-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="检查 ul 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="5d14a-140">检查 `ul` 节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5d14a-141">选择 `Left` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="5d14a-141">Select the `Left` arrow key.</span></span>  <span data-ttu-id="5d14a-142">列表 `<ul>` 折叠。</span><span class="sxs-lookup"><span data-stu-id="5d14a-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="5d14a-143">再次 `Left` 选择箭头键。</span><span class="sxs-lookup"><span data-stu-id="5d14a-143">Select the `Left` arrow key again.</span></span>  <span data-ttu-id="5d14a-144">选择节点 `<ul>` 的父节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="5d14a-145">在这种情况下，它是具有 `<div>` ID 的 `navigate-the-dom-tree-with-a-keyboard-1` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="5d14a-146">选择 `Down` 箭头键 2 次，以便重新选择刚刚 `<ul>` 折叠的列表。</span><span class="sxs-lookup"><span data-stu-id="5d14a-146">Select the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="5d14a-147">应如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d14a-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="5d14a-148">选择 `Right` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="5d14a-148">Select the `Right` arrow key.</span></span>  <span data-ttu-id="5d14a-149">列表将展开。</span><span class="sxs-lookup"><span data-stu-id="5d14a-149">The list expands.</span></span>  

### <a name="scroll-into-view"></a><span data-ttu-id="5d14a-150">滚动到视图中</span><span class="sxs-lookup"><span data-stu-id="5d14a-150">Scroll into view</span></span>  

<span data-ttu-id="5d14a-151">查看 DOM 树时，您可能会对当前不在视口中的 DOM 节点感兴趣。</span><span class="sxs-lookup"><span data-stu-id="5d14a-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="5d14a-152">例如，假设您滚动到页面底部，并且对页面顶部的节点 `<h1>` 感兴趣。</span><span class="sxs-lookup"><span data-stu-id="5d14a-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="5d14a-153">**滚动到视图中** 可快速重新定位视区，以便查看节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to review the node.</span></span>  

1.  <span data-ttu-id="5d14a-154">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-155">在 **"滚动到视图"下**，右选择**Magritte**并选择 **"检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-155">Under **Scroll into View**, right-choose **Magritte** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="5d14a-156">滚动到 DOM 示例页的底部。</span><span class="sxs-lookup"><span data-stu-id="5d14a-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="5d14a-157">仍 `<li>Magritte</li>` 应在 DOM 树中选择节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="5d14a-158">如果没有，请返回到 ["滚动到视图"并](#scroll-into-view) 重新开始。</span><span class="sxs-lookup"><span data-stu-id="5d14a-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="5d14a-159">将鼠标悬停在节点上，打开上下文菜单 `<li>Magritte</li>` \ (右键单击\) ，然后选择 **"滚动到视图"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-159">Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.</span></span>  <span data-ttu-id="5d14a-160">视区将向上滚动，以便你可以查看 **Magritte** 节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-160">Your viewport scrolls back up so that you may review the **Magritte** node.</span></span>  <span data-ttu-id="5d14a-161">导航到 [附录：如果](#appendix-missing-options) 无法查看"滚动到视图"选项，则 **缺少** 选项。</span><span class="sxs-lookup"><span data-stu-id="5d14a-161">Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to review the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="滚动到视图中" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="5d14a-163">滚动到视图中</span><span class="sxs-lookup"><span data-stu-id="5d14a-163">Scroll into view</span></span>**  
    :::image-end:::  

### <a name="search-for-nodes"></a><span data-ttu-id="5d14a-164">搜索节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-164">Search for nodes</span></span>  

<span data-ttu-id="5d14a-165">您可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="5d14a-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="5d14a-166">将光标焦点放在 **"元素"** 工具上。</span><span class="sxs-lookup"><span data-stu-id="5d14a-166">Focus your cursor on the **Elements** tool.</span></span>  
1.  <span data-ttu-id="5d14a-167">选择 `Control` + `F` \ (Windows、Linux\) `Command` + `F` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-167">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="5d14a-168">搜索栏在 DOM 树的底部打开。</span><span class="sxs-lookup"><span data-stu-id="5d14a-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="5d14a-169">键入 `The Moon is a Harsh Mistress`。</span><span class="sxs-lookup"><span data-stu-id="5d14a-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="5d14a-170">最后一句在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="5d14a-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="在搜索栏中突出显示查询" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="5d14a-172">在搜索栏中突出显示查询</span><span class="sxs-lookup"><span data-stu-id="5d14a-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="5d14a-173">如上所述，搜索栏还支持 CSS 和 XPath 选择器。</span><span class="sxs-lookup"><span data-stu-id="5d14a-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <a name="edit-the-dom"></a><span data-ttu-id="5d14a-174">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="5d14a-174">Edit the DOM</span></span>  

<span data-ttu-id="5d14a-175">您可以直接编辑 DOM，并查看更改对页面的影响。</span><span class="sxs-lookup"><span data-stu-id="5d14a-175">You may edit the DOM on the fly and review how the changes affect the page.</span></span>  

### <a name="edit-content"></a><span data-ttu-id="5d14a-176">编辑内容</span><span class="sxs-lookup"><span data-stu-id="5d14a-176">Edit content</span></span>  

<span data-ttu-id="5d14a-177">若要编辑节点的内容，请双击 DOM 树中的内容。</span><span class="sxs-lookup"><span data-stu-id="5d14a-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="5d14a-178">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-179">在 **"编辑内容**"下，右选择 **"Michelle"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-179">Under **Edit Content**, right-choose **Michelle** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-180">在 DOM 树中，双击 `Michelle` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="5d14a-181">换句话说，双击和 之间的 `<li>` 文本 `</li>` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="5d14a-182">突出显示文本以指示已选中。</span><span class="sxs-lookup"><span data-stu-id="5d14a-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="编辑文本" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="5d14a-184">编辑文本</span><span class="sxs-lookup"><span data-stu-id="5d14a-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5d14a-185">删除 `Michelle` ，键入 `Leela` ，然后选择 `Enter` 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="5d14a-185">Delete `Michelle`, type `Leela`, then select `Enter` to confirm the change.</span></span>  <span data-ttu-id="5d14a-186">DOM 中的文本从**Michelle 更改为** **Leela。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <a name="edit-attributes"></a><span data-ttu-id="5d14a-187">编辑属性</span><span class="sxs-lookup"><span data-stu-id="5d14a-187">Edit attributes</span></span>  

<span data-ttu-id="5d14a-188">若要编辑属性，请双击属性名称或值。</span><span class="sxs-lookup"><span data-stu-id="5d14a-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="5d14a-189">按照说明了解如何向节点添加属性。</span><span class="sxs-lookup"><span data-stu-id="5d14a-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="5d14a-190">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-191">在 **"编辑属性"下**，右选择 **"** 放大"，然后选择 **"检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-191">Under **Edit Attributes**, right-choose **Howard** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="5d14a-192">双击 `<li>` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-192">Double-click `<li>`.</span></span>  <span data-ttu-id="5d14a-193">突出显示文本以指示节点已选中。</span><span class="sxs-lookup"><span data-stu-id="5d14a-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="编辑节点" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="5d14a-195">编辑节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5d14a-196">选择 `Right` 箭头键，添加空格，键入 `style="background-color:gold"` ，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-196">Select the `Right` arrow key, add a space, type `style="background-color:gold"`, and then select `Enter`.</span></span>  <span data-ttu-id="5d14a-197">节点的背景色将更改为金色。</span><span class="sxs-lookup"><span data-stu-id="5d14a-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="向节点添加样式属性" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="5d14a-199">向 `style` 节点添加属性</span><span class="sxs-lookup"><span data-stu-id="5d14a-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <a name="edit-node-type"></a><span data-ttu-id="5d14a-200">编辑节点类型</span><span class="sxs-lookup"><span data-stu-id="5d14a-200">Edit node type</span></span>  

<span data-ttu-id="5d14a-201">若要编辑节点的类型，请双击该类型，然后键入新类型。</span><span class="sxs-lookup"><span data-stu-id="5d14a-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="5d14a-202">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-203">在 **"编辑节点类型"下**，右选择 **"放大**"，然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-203">Under **Edit Node Type**, right-choose **Hank** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-204">双击 `<li>` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-204">Double-click `<li>`.</span></span>  <span data-ttu-id="5d14a-205">文本 `li` 突出显示。</span><span class="sxs-lookup"><span data-stu-id="5d14a-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="5d14a-206">删除 `li` ，键入 `button` ，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-206">Delete `li`, type `button`, then select `Enter`.</span></span>  <span data-ttu-id="5d14a-207">节点 `<li>` 将更改到 `<button>` 节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="将节点类型更改为按钮" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="5d14a-209">将节点类型更改为</span><span class="sxs-lookup"><span data-stu-id="5d14a-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <a name="reorder-dom-nodes"></a><span data-ttu-id="5d14a-210">对 DOM 节点重新排序</span><span class="sxs-lookup"><span data-stu-id="5d14a-210">Reorder DOM nodes</span></span>  

<span data-ttu-id="5d14a-211">拖动节点以重新排序。</span><span class="sxs-lookup"><span data-stu-id="5d14a-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="5d14a-212">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-213">在 **"重新排序 DOM 节点**"下，右选择**Elvis Presley，** 然后选择 **"检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-213">Under **Reorder DOM Nodes**, right-choose **Elvis Presley** and choose **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="5d14a-214">它是列表中的最后一项。</span><span class="sxs-lookup"><span data-stu-id="5d14a-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="5d14a-215">在 DOM 树中，拖动 `<li>Elvis Presley</li>` 到列表顶部。</span><span class="sxs-lookup"><span data-stu-id="5d14a-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="将节点拖动到列表顶部" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="5d14a-217">将节点拖动到列表顶部</span><span class="sxs-lookup"><span data-stu-id="5d14a-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <a name="force-state"></a><span data-ttu-id="5d14a-218">强制状态</span><span class="sxs-lookup"><span data-stu-id="5d14a-218">Force state</span></span>  

<span data-ttu-id="5d14a-219">你可以强制节点保持状态，包括 `:active` ， 、 `:hover` 和 `:focus` `:visited` `:focus-within` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="5d14a-220">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-221">在 **"强制"** 状态下，将鼠标悬停在 **"飞鸟"上**。</span><span class="sxs-lookup"><span data-stu-id="5d14a-221">Under **Force state**, hover on **The Lord of the Flies**.</span></span>  <span data-ttu-id="5d14a-222">背景色变为橙色。</span><span class="sxs-lookup"><span data-stu-id="5d14a-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="5d14a-223">悬停在 **"飞鸟"** 上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-223">Hover on **The Lord of the Flies**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-224">悬停在 `<li class="demo--hover">The Lord of the Flies</li>` 上，打开上下文菜单 \ (右键单击\) ，然后选择 **"强制**状态  >  **：hover"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-224">Hover on `<li class="demo--hover">The Lord of the Flies</li>`, open the contextual menu \(right-click\), and choose **Force State** > **:hover**.</span></span>  <span data-ttu-id="5d14a-225">导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="5d14a-225">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  <span data-ttu-id="5d14a-226">即使你实际上没有将鼠标悬停在节点上，背景颜色仍保持橙色。</span><span class="sxs-lookup"><span data-stu-id="5d14a-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <a name="hide-a-node"></a><span data-ttu-id="5d14a-227">隐藏节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-227">Hide a node</span></span>  

<span data-ttu-id="5d14a-228">选择 `H` 以隐藏节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-228">Select `H` to hide a node.</span></span>  

1.  <span data-ttu-id="5d14a-229">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-230">在 **"隐藏节点"下**，右选择 **"星形我的目的地"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-230">Under **Hide a node**, right-choose **The Stars My Destination** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-231">选择 `H` 密钥。</span><span class="sxs-lookup"><span data-stu-id="5d14a-231">Select the `H` key.</span></span>  <span data-ttu-id="5d14a-232">节点处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="5d14a-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="隐藏后的 DOM 树中的节点外观" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="5d14a-234">隐藏后的 DOM 树中的节点外观</span><span class="sxs-lookup"><span data-stu-id="5d14a-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5d14a-235">再次 `H` 选择该键。</span><span class="sxs-lookup"><span data-stu-id="5d14a-235">Select the `H` key again.</span></span>  <span data-ttu-id="5d14a-236">再次显示节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-236">The node is shown again.</span></span>  

### <a name="delete-a-node"></a><span data-ttu-id="5d14a-237">删除节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-237">Delete a node</span></span>  

<span data-ttu-id="5d14a-238">选择 `Delete` 以删除节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-238">Select `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="5d14a-239">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-240">在 **"删除节点"下**，右选择 **"基础**"，然后选择 **"检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-240">Under **Delete a Node**, right-choose **Foundation** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-241">选择 `Delete` 密钥。</span><span class="sxs-lookup"><span data-stu-id="5d14a-241">Select the `Delete` key.</span></span>  <span data-ttu-id="5d14a-242">删除节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="5d14a-243">选择 `Control` + `Z` \ (Windows、Linux\) `Command` + `Z` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-243">Select `Control`+`Z` \(Windows, Linux\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="5d14a-244">最后一个操作将撤消，节点将重新出现。</span><span class="sxs-lookup"><span data-stu-id="5d14a-244">The last action is undone and the node reappears.</span></span>  

## <a name="access-nodes-in-the-console"></a><span data-ttu-id="5d14a-245">控制台中的访问节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-245">Access nodes in the Console</span></span>  

<span data-ttu-id="5d14a-246">DevTools 提供了一些快捷方式，用于从控制台访问 DOM 节点或获取对每个节点的 JavaScript 引用。</span><span class="sxs-lookup"><span data-stu-id="5d14a-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <a name="reference-the-currently-selected-node-with-0"></a><span data-ttu-id="5d14a-247">使用 $0 引用当前选定的节点</span><span class="sxs-lookup"><span data-stu-id="5d14a-247">Reference the currently-selected node with $0</span></span>  

<span data-ttu-id="5d14a-248">检查节点时，节点旁边的文本意味着您可以在控制台中引用此节点 `== $0` 和变量 `$0` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="5d14a-249">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-250">在 **"引用当前选定的节点与 $0"** 下，右选择"暗色的左手 **"，** 然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-250">Under **Reference the currently-selected node with $0**, right-choose **The Left Hand of Darkness** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-251">选择 `Escape` 键以打开控制台箱。</span><span class="sxs-lookup"><span data-stu-id="5d14a-251">Select the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="5d14a-252">键入 `$0` 并选择 `Enter` 密钥。</span><span class="sxs-lookup"><span data-stu-id="5d14a-252">Type `$0` and select the `Enter` key.</span></span>  <span data-ttu-id="5d14a-253">表达式的结果显示计算 `$0` 结果为 `<li>The Left Hand of Darkness</li>` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="控制台中第一个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="5d14a-255">控制台中第一 `$0` 个表达式 **的结果**</span><span class="sxs-lookup"><span data-stu-id="5d14a-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5d14a-256">将鼠标悬停在结果上。</span><span class="sxs-lookup"><span data-stu-id="5d14a-256">Hover on the result.</span></span>  <span data-ttu-id="5d14a-257">该节点在视口中突出显示。</span><span class="sxs-lookup"><span data-stu-id="5d14a-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="5d14a-258">在 `<li>Dune</li>` DOM 树中选择， `$0` 再次在控制台中键入，然后再次 `Enter` 选择。</span><span class="sxs-lookup"><span data-stu-id="5d14a-258">Choose `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then select `Enter` again.</span></span>  <span data-ttu-id="5d14a-259">现在， `$0` 计算结果为 `<li>Dune</li>` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="控制台中第二个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="5d14a-261">控制台中第 `$0` 二个表达式 **的结果**</span><span class="sxs-lookup"><span data-stu-id="5d14a-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <a name="store-as-global-variable"></a><span data-ttu-id="5d14a-262">存储为全局变量</span><span class="sxs-lookup"><span data-stu-id="5d14a-262">Store as global variable</span></span>  

<span data-ttu-id="5d14a-263">如果需要多次引用节点，请存储为全局变量。</span><span class="sxs-lookup"><span data-stu-id="5d14a-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="5d14a-264">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-265">在**Store 作为全局变量**下，将**鼠标悬停在**"大睡眠"上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-265">Under **Store as global variable**, hover on **The Big Sleep**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-266">将鼠标悬停在 DOM 树中，打开上下文菜单 `<li>The Big Sleep</li>` \ (右键单击\) ，然后选择"存储" **作为全局变量**。</span><span class="sxs-lookup"><span data-stu-id="5d14a-266">Hover on `<li>The Big Sleep</li>` in the DOM Tree, open the contextual menu \(right-click\), and choose **Store as global variable**.</span></span>  <span data-ttu-id="5d14a-267">导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="5d14a-267">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="5d14a-268">在 `temp1` 控制台中键入，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-268">Type `temp1` in the Console and then select `Enter`.</span></span>  <span data-ttu-id="5d14a-269">表达式的结果显示变量计算结果为节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 表达式的结果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="5d14a-271">表达式 `temp1` 的结果</span><span class="sxs-lookup"><span data-stu-id="5d14a-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <a name="copy-js-path"></a><span data-ttu-id="5d14a-272">复制 JS 路径</span><span class="sxs-lookup"><span data-stu-id="5d14a-272">Copy JS path</span></span>  

<span data-ttu-id="5d14a-273">当你需要在自动测试中引用该节点时，将 JavaScript 路径复制到该节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="5d14a-274">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-275">在 **"复制 JS 路径**"下，将鼠标悬停在 **"小马马zov"** 上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-275">Under **Copy JS path**, hover on **The Brothers Karamazov**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-276">将鼠标悬停在 DOM 树中，打开上下文菜单 `<li>The Brothers Karamazov</li>` \ (右键单击\) ，然后选择 **"复制**  >  **JS 路径"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-276">Hover on `<li>The Brothers Karamazov</li>` in the DOM Tree, open the contextual menu \(right-click\), and choose **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="5d14a-277">解析 `document.querySelector()` 为节点的表达式已复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="5d14a-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="5d14a-278">选择 `Control` + `V` \ (Windows、Linux\) 或 `Command` + `V` \ (macOS\) 将表达式粘贴到控制台中。</span><span class="sxs-lookup"><span data-stu-id="5d14a-278">Select `Control`+`V` \(Windows, Linux\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="5d14a-279">选择 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="5d14a-279">Select `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="复制 JS 路径表达式的结果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="5d14a-281">复制 JS **路径** 表达式的结果</span><span class="sxs-lookup"><span data-stu-id="5d14a-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <a name="break-on-dom-changes"></a><span data-ttu-id="5d14a-282">中断 DOM 更改</span><span class="sxs-lookup"><span data-stu-id="5d14a-282">Break on DOM changes</span></span>  

<span data-ttu-id="5d14a-283">DevTools 使您能够在 JavaScript 修改 DOM 时暂停页面的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="5d14a-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <a name="break-on-attribute-modifications"></a><span data-ttu-id="5d14a-284">中断属性修改</span><span class="sxs-lookup"><span data-stu-id="5d14a-284">Break on attribute modifications</span></span>  

<span data-ttu-id="5d14a-285">若要暂停导致节点的任何属性更改的 JavaScript，请使用属性修改断点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="5d14a-286">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-287">在**属性修改中断下**，右选择**Sauerkraut，** 然后选择 **"检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-287">Under **Break on attribute modifications**, right-choose **Sauerkraut** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-288">在 DOM 树中，悬停在上，打开上下文菜单 `<li id="target">Sauerkraut</li>` \ (右键单击\) ，然后选择"属性修改时\*\*\*\* 中断  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-288">In the DOM Tree, hover on `<li id="target">Sauerkraut</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="5d14a-289">导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="5d14a-289">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="中断属性修改" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="5d14a-291">中断属性修改</span><span class="sxs-lookup"><span data-stu-id="5d14a-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="5d14a-292">下一步将指导你选择暂停页面代码的按钮。</span><span class="sxs-lookup"><span data-stu-id="5d14a-292">In the next step you are going to be instructed to choose a button that pauses the code of the page.</span></span>  <span data-ttu-id="5d14a-293">暂停页面后，你无法再滚动页面。</span><span class="sxs-lookup"><span data-stu-id="5d14a-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="5d14a-294">您必须选择 Resume **Script** \ (![ Resume Script ][ImageResumeScriptIcon] \) 才能使页面再次滚动。</span><span class="sxs-lookup"><span data-stu-id="5d14a-294">You must choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="在何处恢复脚本运行" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="5d14a-296">在何处恢复脚本运行</span><span class="sxs-lookup"><span data-stu-id="5d14a-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5d14a-297">选择 **上面的"设置背景** "按钮。</span><span class="sxs-lookup"><span data-stu-id="5d14a-297">Choose the **Set Background** button above.</span></span>  <span data-ttu-id="5d14a-298">这会将 `style` 节点的属性设置为 `background-color:thistle` 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="5d14a-299">DevTools 暂停页面并突出显示导致属性更改的代码。</span><span class="sxs-lookup"><span data-stu-id="5d14a-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="5d14a-300">选择 **"恢复** (![ 脚本 ][ImageResumeScriptIcon] \) ，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="5d14a-300">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span></span>  
    
### <a name="break-on-node-removal"></a><span data-ttu-id="5d14a-301">删除节点时中断</span><span class="sxs-lookup"><span data-stu-id="5d14a-301">Break on node removal</span></span>  

<span data-ttu-id="5d14a-302">如果要在删除特定节点时暂停，请使用节点删除断点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="5d14a-303">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-304">在 **"删除节点时中断"下**，右选择 **"管理**程序"，然后选择 **"检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-304">Under **Break on Node Removal**, right-choose **Neuromancer** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-305">在 DOM 树中，悬停在上，打开上下文菜单 `<li id="target">Neuromancer</li>` \ (右键单击\) ，然后选择"删除**节点时**中断  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-305">In the DOM Tree, hover on `<li id="target">Neuromancer</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="5d14a-306">导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。</span><span class="sxs-lookup"><span data-stu-id="5d14a-306">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="5d14a-307">选择 **上面的"删除** "按钮。</span><span class="sxs-lookup"><span data-stu-id="5d14a-307">Choose the **Delete** button above.</span></span>  <span data-ttu-id="5d14a-308">DevTools 暂停页面并突出显示导致删除节点的代码。</span><span class="sxs-lookup"><span data-stu-id="5d14a-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="5d14a-309">Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="5d14a-309">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
### <a name="break-on-subtree-modifications"></a><span data-ttu-id="5d14a-310">中断子树修改</span><span class="sxs-lookup"><span data-stu-id="5d14a-310">Break on subtree modifications</span></span>  

<span data-ttu-id="5d14a-311">在节点上放入子树修改断点后，当添加或删除节点的任何后代时，DevTools 将暂停页面。</span><span class="sxs-lookup"><span data-stu-id="5d14a-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="5d14a-312">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="5d14a-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5d14a-313">在 **"子树修改中断"下**，右选择 **"** 深度时射击"，然后选择"**检查"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-313">Under **Break on Subtree Modifications**, right-choose **A Fire Upon The Deep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="5d14a-314">在 DOM 树中，将鼠标悬停在上方的节点上，打开上下文菜单 `<ul id="target">` `<li>A Fire Upon the Deep</li>` \ (右键单击\) ，\*\*\*\* 然后选择"子树修改  >  \*\*\*\*"。</span><span class="sxs-lookup"><span data-stu-id="5d14a-314">In the DOM Tree, hover on `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="5d14a-315">如果未显示该选项，请导航到["附录：缺少选项"。](#appendix-missing-options)</span><span class="sxs-lookup"><span data-stu-id="5d14a-315">If the option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).</span></span>  
    1.  <span data-ttu-id="5d14a-316">选择 **"添加子级"。**</span><span class="sxs-lookup"><span data-stu-id="5d14a-316">Choose **Add Child**.</span></span>  <span data-ttu-id="5d14a-317">代码将暂停，因为 `<li>` 向列表中添加了节点。</span><span class="sxs-lookup"><span data-stu-id="5d14a-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="5d14a-318">Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="5d14a-318">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
## <a name="next-steps"></a><span data-ttu-id="5d14a-319">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5d14a-319">Next steps</span></span>  

<span data-ttu-id="5d14a-320">这涵盖了 DevTools 中与 DOM 相关的大多数功能。</span><span class="sxs-lookup"><span data-stu-id="5d14a-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="5d14a-321">通过将鼠标悬停在 DOM 树中的节点上，打开上下文菜单 \ (右键单击\) ，并尝试本教程未涵盖的其他选项，您可以发现其余功能。</span><span class="sxs-lookup"><span data-stu-id="5d14a-321">You are able to discover the rest of the features by hovering on nodes in the DOM Tree, opening the contextual menu \(right-click\), and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="5d14a-322">导航到 [元素面板键盘快捷方式][DevToolsShortcutsElements]。</span><span class="sxs-lookup"><span data-stu-id="5d14a-322">Navigate to [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="5d14a-323">查看 [Microsoft Edge DevTools 主页][MicrosoftEdgeDevTools] ，了解可以使用 DevTools 执行的所有其他功能。</span><span class="sxs-lookup"><span data-stu-id="5d14a-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <a name="appendix-html-versus-the-dom"></a><span data-ttu-id="5d14a-324">附录：HTML 与 DOM</span><span class="sxs-lookup"><span data-stu-id="5d14a-324">Appendix: HTML versus the DOM</span></span>  

<span data-ttu-id="5d14a-325">下一节快速介绍了 HTML 和 DOM 的区别。</span><span class="sxs-lookup"><span data-stu-id="5d14a-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="5d14a-326">使用 Web 浏览器请求页面时，服务器将返回 HTML，如以下代码段</span><span class="sxs-lookup"><span data-stu-id="5d14a-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

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
      <span data-ttu-id="5d14a-327">浏览器分析 HTML 并创建对象树，如以下列表所示。</span><span class="sxs-lookup"><span data-stu-id="5d14a-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
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

<span data-ttu-id="5d14a-328">此表示页面内容的对象或节点树称为 DOM。</span><span class="sxs-lookup"><span data-stu-id="5d14a-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="5d14a-329">现在它看起来与 HTML 相同，但假定 HTML 底部引用的脚本运行以下代码段。</span><span class="sxs-lookup"><span data-stu-id="5d14a-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="5d14a-330">该代码将删除该 `h1` 节点，并将另 `p` 一个节点添加到 DOM。</span><span class="sxs-lookup"><span data-stu-id="5d14a-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="5d14a-331">完整的 DOM 现在将显示以下列表。</span><span class="sxs-lookup"><span data-stu-id="5d14a-331">The complete DOM now displays the following list.</span></span>  
      
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

<span data-ttu-id="5d14a-332">页面的 HTML 现在不同于 DOM。</span><span class="sxs-lookup"><span data-stu-id="5d14a-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="5d14a-333">换句话说，HTML 表示初始页面内容，DOM 表示当前页面内容。</span><span class="sxs-lookup"><span data-stu-id="5d14a-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="5d14a-334">当 JavaScript 添加、删除或编辑节点时，DOM 将不同于 HTML。</span><span class="sxs-lookup"><span data-stu-id="5d14a-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="5d14a-335">导航 [到 DOM 简介][MDNIntroductionToDOM] 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="5d14a-335">Navigate to [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.  Your viewport scrolls back up so that the **Magritte** node is displayed.  If you the **Scroll into view** option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <a name="appendix-missing-options"></a><span data-ttu-id="5d14a-336">附录：缺少选项</span><span class="sxs-lookup"><span data-stu-id="5d14a-336">Appendix: Missing options</span></span>  

<span data-ttu-id="5d14a-337">本教程中的许多说明都指示你将鼠标悬停在 DOM 树中的节点上，打开上下文菜单 \ (右键单击\) ，然后从弹出的上下文菜单中选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="5d14a-337">Many of the instructions in this tutorial instruct you to hover on a node in the DOM Tree, open the contextual menu \(right-click\), and then choose an option from the context menu that pops up.</span></span>  <span data-ttu-id="5d14a-338">如果未显示上下文菜单中的指定选项，请尝试将鼠标悬停在节点文本之外，然后打开上下文菜单 \ (右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="5d14a-338">If the specified option in the context menu is not displayed, try hovering away from the node text and opening the contextual menu \(right-click\).</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="如果未显示所有选项，请选择什么位置" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="5d14a-340">如果未显示所有选项，请选择什么位置</span><span class="sxs-lookup"><span data-stu-id="5d14a-340">Where to choose if all of the options are not displayed</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="5d14a-341">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="5d14a-341">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具|Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-tool-keyboard-shortcuts "元素工具键盘快捷方式 - Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM 示例|小故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM |MDN"  

> [!NOTE]
> <span data-ttu-id="5d14a-347">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5d14a-347">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5d14a-348">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="5d14a-348">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5d14a-350">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5d14a-350">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
