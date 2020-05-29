---
title: 查看和更改 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 4dee8b4e3ea927e72c0f98517f264b2c1d453013
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607445"
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





# <span data-ttu-id="0be45-103">查看和更改 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="0be45-103">Get Started With Viewing And Changing The DOM</span></span>   



<span data-ttu-id="0be45-104">完成这些交互式教程，了解有关使用 Microsoft Edge DevTools 查看和更改页面 DOM 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="0be45-104">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="0be45-105">本教程假定你知道 DOM 和 HTML 之间的区别。</span><span class="sxs-lookup"><span data-stu-id="0be45-105">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="0be45-106">有关说明，请参阅[附录： HTML 和 DOM](#appendix-html-versus-the-dom) 。</span><span class="sxs-lookup"><span data-stu-id="0be45-106">See [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="0be45-107">Open DOM 示例</span><span class="sxs-lookup"><span data-stu-id="0be45-107">Open DOM Examples</span></span>  

1.  <span data-ttu-id="0be45-108">保留 `Control` \ （Windows \）或 `Command` \ （macOS \），然后单击 " **DOM 示例**" 以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="0be45-108">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="0be45-109">DOM 示例</span><span class="sxs-lookup"><span data-stu-id="0be45-109">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="0be45-110">查看 DOM 节点</span><span class="sxs-lookup"><span data-stu-id="0be45-110">View DOM nodes</span></span>   

<span data-ttu-id="0be45-111">在 "元素" 面板的 DOM 树中，你可以在 DevTools 中执行所有与 DOM 相关的活动。</span><span class="sxs-lookup"><span data-stu-id="0be45-111">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="0be45-112">检查节点</span><span class="sxs-lookup"><span data-stu-id="0be45-112">Inspect a node</span></span>   

<span data-ttu-id="0be45-113">当你对特定的 DOM 节点感兴趣时，请使用 "**检查**" 快速打开 DevTools 并调查该节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-113">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="0be45-114">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-114">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-115">在 "**检查节点**" 下，右键单击 " **Michelangelo** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-115">Under **Inspect a Node**, right-click **Michelangelo** and select **Inspect**.</span></span>  
    
    > ##### <span data-ttu-id="0be45-116">图 1</span><span class="sxs-lookup"><span data-stu-id="0be45-116">Figure 1</span></span>  
    > <span data-ttu-id="0be45-117">检查节点</span><span class="sxs-lookup"><span data-stu-id="0be45-117">Inspecting a node</span></span>  
    > ![检查节点][ImageInspectingNode]  
    
    1.  <span data-ttu-id="0be45-119">将打开 DevTools 的 "**元素**" 面板。</span><span class="sxs-lookup"><span data-stu-id="0be45-119">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="0be45-120">在**DOM 树**中突出显示。</span><span class="sxs-lookup"><span data-stu-id="0be45-120">is highlighted in the **DOM Tree**.</span></span>  
        
        > ##### <span data-ttu-id="0be45-121">图 2</span><span class="sxs-lookup"><span data-stu-id="0be45-121">Figure 2</span></span>  
        > <span data-ttu-id="0be45-122">突出显示 Michelangelo 节点</span><span class="sxs-lookup"><span data-stu-id="0be45-122">Highlighting the Michelangelo node</span></span>  
        > ![突出显示 Michelangelo 节点][ImageHighlightingMichelangeloNode]  
        
        1.  <span data-ttu-id="0be45-124">单击 DevTools 左上角的 "**检查** ![ 检查" ][ImageInspectIcon] 图标。</span><span class="sxs-lookup"><span data-stu-id="0be45-124">Click the **Inspect** ![Inspect][ImageInspectIcon] icon in the top-left corner of DevTools.</span></span>  
            
            > ##### <span data-ttu-id="0be45-125">图 3</span><span class="sxs-lookup"><span data-stu-id="0be45-125">Figure 3</span></span>  
            > <span data-ttu-id="0be45-126">"检查" 图标</span><span class="sxs-lookup"><span data-stu-id="0be45-126">The Inspect icon</span></span>  
            > !["检查" 图标][ImageInspect]  
            
1.  <span data-ttu-id="0be45-128">在 "**检查节点**" 下，单击 "**东京**文本"。</span><span class="sxs-lookup"><span data-stu-id="0be45-128">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="0be45-129">现在， `<li>Tokyo</li>` 在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="0be45-129">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="0be45-130">检查节点也是查看和更改节点样式的第一步。</span><span class="sxs-lookup"><span data-stu-id="0be45-130">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="0be45-131">请参阅[查看和更改 CSS 入门][DevToolsCssGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="0be45-131">See [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="0be45-132">使用键盘导航 DOM 树</span><span class="sxs-lookup"><span data-stu-id="0be45-132">Navigate the DOM Tree with a keyboard</span></span>   

<span data-ttu-id="0be45-133">选择 DOM 树中的节点后，您可以使用键盘在 DOM 树中导航。</span><span class="sxs-lookup"><span data-stu-id="0be45-133">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="0be45-134">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-134">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-135">在 "**使用键盘导航 DOM 树**" 下，右键单击 " **Ringo** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-135">Under **Navigate the DOM Tree with a Keyboard**, right-click **Ringo** and select **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="0be45-136">在 DOM 树中处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="0be45-136">is selected in the DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="0be45-137">图 4</span><span class="sxs-lookup"><span data-stu-id="0be45-137">Figure 4</span></span>  
    > <span data-ttu-id="0be45-138">检查 Ringo 节点</span><span class="sxs-lookup"><span data-stu-id="0be45-138">Inspecting the Ringo node</span></span>  
    > ![检查 Ringo 节点][ImageInspectingRingoNode]  
    
    1.  <span data-ttu-id="0be45-140">按 `Up` 箭头键2次。</span><span class="sxs-lookup"><span data-stu-id="0be45-140">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="0be45-141">已选中。</span><span class="sxs-lookup"><span data-stu-id="0be45-141">is selected.</span></span>  
        
        > ##### <span data-ttu-id="0be45-142">图 5</span><span class="sxs-lookup"><span data-stu-id="0be45-142">Figure 5</span></span>  
        > <span data-ttu-id="0be45-143">检查 ul 节点</span><span class="sxs-lookup"><span data-stu-id="0be45-143">Inspecting the ul node</span></span>  
        > ![检查 ul 节点][ImageInspectingUlNode]  
        
    1.  <span data-ttu-id="0be45-145">按 `Left` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="0be45-145">Press the `Left` arrow key.</span></span>  <span data-ttu-id="0be45-146">`<ul>`列表折叠。</span><span class="sxs-lookup"><span data-stu-id="0be45-146">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="0be45-147">再次按 `Left` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="0be45-147">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="0be45-148">`<ul>`已选中节点的父节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-148">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="0be45-149">在这种情况下，它 `<div>` 具有 ID `navigate-the-dom-tree-with-a-keyboard-1` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-149">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="0be45-150">按 `Down` 箭头键2次，以便您重新选中 `<ul>` 刚才折叠的列表。</span><span class="sxs-lookup"><span data-stu-id="0be45-150">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="0be45-151">应如下所示：</span><span class="sxs-lookup"><span data-stu-id="0be45-151">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="0be45-152">按 `Right` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="0be45-152">Press the `Right` arrow key.</span></span>  <span data-ttu-id="0be45-153">该列表将展开。</span><span class="sxs-lookup"><span data-stu-id="0be45-153">The list expands.</span></span>  

### <span data-ttu-id="0be45-154">滚动到视图</span><span class="sxs-lookup"><span data-stu-id="0be45-154">Scroll into view</span></span>   

<span data-ttu-id="0be45-155">查看 DOM 树时，你可能会发现你对当前不在视口中的 DOM 节点感兴趣。</span><span class="sxs-lookup"><span data-stu-id="0be45-155">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="0be45-156">例如，假设你滚动到页面底部，并且你对 `<h1>` 页面顶部的节点感兴趣。</span><span class="sxs-lookup"><span data-stu-id="0be45-156">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="0be45-157">"**滚动到" 视图**可快速调整视区的位置，以便您能够看到该节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-157">**Scroll into view** lets you quickly reposition the viewport so that you are able to see the node.</span></span>  

1.  <span data-ttu-id="0be45-158">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-158">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-159">在 "**滚动到视图**" 下，右键单击 " **Magritte** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-159">Under **Scroll into View**, right-click **Magritte** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="0be45-160">滚动到 "DOM 示例" 页面的底部。</span><span class="sxs-lookup"><span data-stu-id="0be45-160">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="0be45-161">该 `<li>Magritte</li>` 节点应仍在你的 DOM 树中处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="0be45-161">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="0be45-162">如果不是，请返回到 "[查看](#scroll-into-view)" 并重新开始。</span><span class="sxs-lookup"><span data-stu-id="0be45-162">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="0be45-163">右键单击 `<li>Magritte</li>` 节点，然后选择 "**滚动到视图**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-163">Right-click the `<li>Magritte</li>` node and select **Scroll into view**.</span></span>  <span data-ttu-id="0be45-164">你的视区向后滚动，以便你可以看到**Magritte**节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-164">Your viewport scrolls back up so that you may see the **Magritte** node.</span></span>  <span data-ttu-id="0be45-165">如果无法看到 "**滚动到视图**" 选项，请参阅[附录： "缺少选项](#appendix-missing-options)"。</span><span class="sxs-lookup"><span data-stu-id="0be45-165">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.</span></span>
    
    > ##### <span data-ttu-id="0be45-166">图 6</span><span class="sxs-lookup"><span data-stu-id="0be45-166">Figure 6</span></span>  
    > <span data-ttu-id="0be45-167">滚动到视图</span><span class="sxs-lookup"><span data-stu-id="0be45-167">Scroll into view</span></span>  
    > ![滚动到视图][ImageScrollView]  

### <span data-ttu-id="0be45-169">搜索节点</span><span class="sxs-lookup"><span data-stu-id="0be45-169">Search for nodes</span></span>   

<span data-ttu-id="0be45-170">你可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="0be45-170">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="0be45-171">将光标聚焦在 "**元素**" 面板上。</span><span class="sxs-lookup"><span data-stu-id="0be45-171">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="0be45-172">按 `Control` + `F` \ （Windows \）或 `Command` + `F` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="0be45-172">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="0be45-173">搜索栏将在 DOM 树的底部打开。</span><span class="sxs-lookup"><span data-stu-id="0be45-173">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="0be45-174">键入 `The Moon is a Harsh Mistress`。</span><span class="sxs-lookup"><span data-stu-id="0be45-174">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="0be45-175">最后一句在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="0be45-175">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="0be45-176">图 7</span><span class="sxs-lookup"><span data-stu-id="0be45-176">Figure 7</span></span>  
    > <span data-ttu-id="0be45-177">在搜索栏中突出显示查询</span><span class="sxs-lookup"><span data-stu-id="0be45-177">Highlighting the query in the Search bar</span></span>  
    > ![在搜索栏中突出显示查询][ImageHighlightingQuerySearchBar]  
    
<span data-ttu-id="0be45-179">如上文所述，搜索栏还支持 CSS 和 XPath 选择器。</span><span class="sxs-lookup"><span data-stu-id="0be45-179">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="0be45-180">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="0be45-180">Edit the DOM</span></span>   

<span data-ttu-id="0be45-181">你可以动态编辑 DOM 并查看这些更改对页面的影响。</span><span class="sxs-lookup"><span data-stu-id="0be45-181">You may edit the DOM on the fly and see how those changes affect the page.</span></span>  

### <span data-ttu-id="0be45-182">编辑内容</span><span class="sxs-lookup"><span data-stu-id="0be45-182">Edit content</span></span>   

<span data-ttu-id="0be45-183">若要编辑节点的内容，请双击 DOM 树中的内容。</span><span class="sxs-lookup"><span data-stu-id="0be45-183">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="0be45-184">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-184">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-185">在 "**编辑内容**" 下，右键单击 " **Michelle** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-185">Under **Edit Content**, right-click **Michelle** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-186">在 DOM 树中，双击 `Michelle` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-186">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="0be45-187">换句话说，双击 and 之间的文本 `<li>` `</li>` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-187">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="0be45-188">文本将突出显示，以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="0be45-188">The text is highlighted to indicate that it is selected.</span></span>  
        
        > ##### <span data-ttu-id="0be45-189">图 8</span><span class="sxs-lookup"><span data-stu-id="0be45-189">Figure 8</span></span>  
        > <span data-ttu-id="0be45-190">编辑文本</span><span class="sxs-lookup"><span data-stu-id="0be45-190">Editing the text</span></span>  
        > ![编辑文本][ImageEditingText]  
        
    1.  <span data-ttu-id="0be45-192">删除 `Michelle` ，键入 `Leela` ，然后按 `Enter` 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="0be45-192">Delete `Michelle`, type `Leela`, then press `Enter` to confirm the change.</span></span>  <span data-ttu-id="0be45-193">DOM 中的文本从**Michelle**更改为**Leela**。</span><span class="sxs-lookup"><span data-stu-id="0be45-193">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="0be45-194">编辑属性</span><span class="sxs-lookup"><span data-stu-id="0be45-194">Edit attributes</span></span>   

<span data-ttu-id="0be45-195">若要编辑属性，请双击属性名称或值。</span><span class="sxs-lookup"><span data-stu-id="0be45-195">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="0be45-196">按照说明操作，了解如何向节点添加属性。</span><span class="sxs-lookup"><span data-stu-id="0be45-196">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="0be45-197">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-197">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-198">在 "**编辑属性**" 下，右键单击 " **Howard** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-198">Under **Edit Attributes**, right-click **Howard** and select **Inspect**.</span></span>  

1.  <span data-ttu-id="0be45-199">双击 `<li>` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-199">Double-click `<li>`.</span></span>  <span data-ttu-id="0be45-200">文本将突出显示，以指示节点已选中。</span><span class="sxs-lookup"><span data-stu-id="0be45-200">The text is highlighted to indicate that the node is selected.</span></span>  
    
    > ##### <span data-ttu-id="0be45-201">图 9</span><span class="sxs-lookup"><span data-stu-id="0be45-201">Figure 9</span></span>  
    > <span data-ttu-id="0be45-202">编辑节点</span><span class="sxs-lookup"><span data-stu-id="0be45-202">Editing the node</span></span>  
    > ![编辑节点][ImageEditingNode]  
    
1.  <span data-ttu-id="0be45-204">按 `Right` 箭头键，添加一个空格，键入 `style="background-color:gold"` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-204">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then press `Enter`.</span></span>  <span data-ttu-id="0be45-205">节点的背景色将更改为 "金色"。</span><span class="sxs-lookup"><span data-stu-id="0be45-205">The background color of the node changes to gold.</span></span>  
    
    > ##### <span data-ttu-id="0be45-206">图 10</span><span class="sxs-lookup"><span data-stu-id="0be45-206">Figure 10</span></span>  
    > <span data-ttu-id="0be45-207">向节点添加样式属性</span><span class="sxs-lookup"><span data-stu-id="0be45-207">Adding a style attribute to the node</span></span>  
    > ![向节点添加样式属性][ImageAddingStyleAttributeNode]  
    
### <span data-ttu-id="0be45-209">编辑节点类型</span><span class="sxs-lookup"><span data-stu-id="0be45-209">Edit node type</span></span>   

<span data-ttu-id="0be45-210">若要编辑节点类型，请双击该类型，然后键入新类型。</span><span class="sxs-lookup"><span data-stu-id="0be45-210">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="0be45-211">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-211">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-212">在 "**编辑节点类型**" 下，右键单击 " **Hank** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-212">Under **Edit Node Type**, right-click **Hank** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-213">双击 `<li>` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-213">Double-click `<li>`.</span></span>  <span data-ttu-id="0be45-214">文本 `li` 突出显示。</span><span class="sxs-lookup"><span data-stu-id="0be45-214">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="0be45-215">删除 `li` ，键入 `button` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-215">Delete `li`, type `button`, then press `Enter`.</span></span>  <span data-ttu-id="0be45-216">`<li>`节点将更改为 `<button>` 节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-216">The `<li>` node changes to a `<button>` node.</span></span>  
        
        > ##### <span data-ttu-id="0be45-217">图 11</span><span class="sxs-lookup"><span data-stu-id="0be45-217">Figure 11</span></span>  
        > <span data-ttu-id="0be45-218">将 "节点类型" 更改为 "按钮"</span><span class="sxs-lookup"><span data-stu-id="0be45-218">Changing the node type to button</span></span>  
        > ![将 "节点类型" 更改为 "按钮"][ImageChangingNodeButton]  
        
### <span data-ttu-id="0be45-220">重新排序 DOM 节点</span><span class="sxs-lookup"><span data-stu-id="0be45-220">Reorder DOM nodes</span></span>   

<span data-ttu-id="0be45-221">拖动节点以对其重新排序。</span><span class="sxs-lookup"><span data-stu-id="0be45-221">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="0be45-222">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-222">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-223">在 "**重新排序 DOM 节点**" 下，右键单击 " **Elvis Presley** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-223">Under **Reorder DOM Nodes**, right-click **Elvis Presley** and select **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0be45-224">它是列表中的最后一项。</span><span class="sxs-lookup"><span data-stu-id="0be45-224">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="0be45-225">在 DOM 树中，拖动 `<li>Elvis Presley</li>` 到列表的顶部。</span><span class="sxs-lookup"><span data-stu-id="0be45-225">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        > ##### <span data-ttu-id="0be45-226">图 12</span><span class="sxs-lookup"><span data-stu-id="0be45-226">Figure 12</span></span>  
        > <span data-ttu-id="0be45-227">将节点拖动到列表顶部</span><span class="sxs-lookup"><span data-stu-id="0be45-227">Dragging the node to the top of the list</span></span>  
        > ![将节点拖动到列表顶部][ImageDraggingNodeTopList]  
        
### <span data-ttu-id="0be45-229">强制状态</span><span class="sxs-lookup"><span data-stu-id="0be45-229">Force state</span></span>   

<span data-ttu-id="0be45-230">你可以强制节点保留在状态中，包括、、、 `:active` `:hover` `:focus` `:visited` 和 `:focus-within` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-230">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="0be45-231">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-231">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-232">在 "**强制状态**" 下，将鼠标悬停在**Lord 的**上方。</span><span class="sxs-lookup"><span data-stu-id="0be45-232">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="0be45-233">背景色变为橙色。</span><span class="sxs-lookup"><span data-stu-id="0be45-233">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="0be45-234">右键单击 "**飞入" 的 Lord** ，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-234">Right-click **The Lord of the Flies** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-235">右键单击 `<li class="demo--hover">The Lord of the Flies</li>` 并选择 "**强制状态**  >  **：悬停**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-235">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and select **Force State** > **:hover**.</span></span>  <span data-ttu-id="0be45-236">如果看不到此选项，请参阅[附录：缺少选项](#appendix-missing-options)。</span><span class="sxs-lookup"><span data-stu-id="0be45-236">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  <span data-ttu-id="0be45-237">虽然实际上不会将鼠标悬停在节点上，但背景色仍为橙色。</span><span class="sxs-lookup"><span data-stu-id="0be45-237">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="0be45-238">隐藏节点</span><span class="sxs-lookup"><span data-stu-id="0be45-238">Hide a node</span></span>   

<span data-ttu-id="0be45-239">按 " `H` 隐藏节点"。</span><span class="sxs-lookup"><span data-stu-id="0be45-239">Press `H` to hide a node.</span></span>  

1.  <span data-ttu-id="0be45-240">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-240">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-241">在 "**隐藏节点**" 下，右键单击**星形 "我的目的地"** ，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-241">Under **Hide a node**, right-click **The Stars My Destination** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-242">按 `H` 键。</span><span class="sxs-lookup"><span data-stu-id="0be45-242">Press the `H` key.</span></span>  <span data-ttu-id="0be45-243">节点已隐藏。</span><span class="sxs-lookup"><span data-stu-id="0be45-243">The node is hidden.</span></span>  
        
        > ##### <span data-ttu-id="0be45-244">图 13</span><span class="sxs-lookup"><span data-stu-id="0be45-244">Figure 13</span></span>  
        > <span data-ttu-id="0be45-245">节点在隐藏后在 DOM 树中的显示效果</span><span class="sxs-lookup"><span data-stu-id="0be45-245">What the node looks like in the DOM Tree after it is hidden</span></span>  
        > ![节点在隐藏后在 DOM 树中的显示效果][ImageNodeDomTreeAfterHidden]  
        
    1.  <span data-ttu-id="0be45-247">再次按下 `H` 键。</span><span class="sxs-lookup"><span data-stu-id="0be45-247">Press the `H` key again.</span></span>  <span data-ttu-id="0be45-248">将再次显示该节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-248">The node is shown again.</span></span>  

### <span data-ttu-id="0be45-249">删除节点</span><span class="sxs-lookup"><span data-stu-id="0be45-249">Delete a node</span></span>   

<span data-ttu-id="0be45-250">按 `Delete` 以删除节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-250">Press `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="0be45-251">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-251">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-252">在 "**删除节点**" 下，右键单击 "**基础**"，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-252">Under **Delete a Node**, right-click **Foundation** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-253">按 `Delete` 键。</span><span class="sxs-lookup"><span data-stu-id="0be45-253">Press the `Delete` key.</span></span>  <span data-ttu-id="0be45-254">删除该节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-254">The node is deleted.</span></span>  
    1.  <span data-ttu-id="0be45-255">按 `Control` + `Z` \ （Windows \）或 `Command` + `Z` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="0be45-255">Press `Control`+`Z` \(Windows\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="0be45-256">最后一个操作将被撤消，并且该节点会再次出现。</span><span class="sxs-lookup"><span data-stu-id="0be45-256">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="0be45-257">访问控制台中的节点</span><span class="sxs-lookup"><span data-stu-id="0be45-257">Access nodes in the Console</span></span>   

<span data-ttu-id="0be45-258">DevTools 提供了从控制台访问 DOM 节点或获取每个节点的 JavaScript 引用的一些快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0be45-258">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="0be45-259">引用当前选定的具有 $0 的节点</span><span class="sxs-lookup"><span data-stu-id="0be45-259">Reference the currently-selected node with $0</span></span>   

<span data-ttu-id="0be45-260">检查节点时， `== $0` 节点旁边的文本意味着你可以使用该变量在控制台中引用此节点 `$0` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-260">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="0be45-261">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-261">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-262">在 "**引用当前选定的包含 $0 的节点**" 下，右键单击**暗度的左侧**，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-262">Under **Reference the currently-selected node with $0**, right-click **The Left Hand of Darkness** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-263">按 `Escape` 键打开控制台抽屉。</span><span class="sxs-lookup"><span data-stu-id="0be45-263">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="0be45-264">键入 `$0` ，然后按键 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-264">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="0be45-265">表达式的结果显示 `$0` 为 `<li>The Left Hand of Darkness</li>` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-265">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        > ##### <span data-ttu-id="0be45-266">图 14</span><span class="sxs-lookup"><span data-stu-id="0be45-266">Figure 14</span></span>  
        > <span data-ttu-id="0be45-267">控制台中第一个表达式的结果 `$0`</span><span class="sxs-lookup"><span data-stu-id="0be45-267">The result of the first `$0` expression in the Console</span></span>  
        > ![控制台中第一个 $0 表达式的结果][ImageFirstConsole]  
        
    1.  <span data-ttu-id="0be45-269">将鼠标悬停在结果上。</span><span class="sxs-lookup"><span data-stu-id="0be45-269">Hover over the result.</span></span>  <span data-ttu-id="0be45-270">节点在视区中突出显示。</span><span class="sxs-lookup"><span data-stu-id="0be45-270">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="0be45-271">单击 `<li>Dune</li>` DOM 树， `$0` 再次键入控制台，然后再次按下 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-271">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then press `Enter` again.</span></span>  <span data-ttu-id="0be45-272">现在， `$0` 计算结果为 `<li>Dune</li>` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-272">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        > ##### <span data-ttu-id="0be45-273">图 15</span><span class="sxs-lookup"><span data-stu-id="0be45-273">Figure 15</span></span>  
        > <span data-ttu-id="0be45-274">控制台中第二个 `$0` 表达式的结果是 ![ 控制台中第二个 $0 表达式的结果][ImageSecondConsole]</span><span class="sxs-lookup"><span data-stu-id="0be45-274">The result of the second `$0` expression in the Console ![The result of the second $0 expression in the Console][ImageSecondConsole]</span></span>  
        
### <span data-ttu-id="0be45-275">存储为全局变量</span><span class="sxs-lookup"><span data-stu-id="0be45-275">Store as global variable</span></span>   

<span data-ttu-id="0be45-276">如果需要多次引用某个节点，请将其存储为全局变量。</span><span class="sxs-lookup"><span data-stu-id="0be45-276">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="0be45-277">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-277">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-278">在 "**存储为全局变量**" 下，右键单击 **"大睡眠"** ，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-278">Under **Store as global variable**, right-click **The Big Sleep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-279">右键单击 `<li>The Big Sleep</li>` DOM 树，然后选择 "**存储为全局变量**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-279">Right-click `<li>The Big Sleep</li>` in the DOM Tree and select **Store as global variable**.</span></span>  <span data-ttu-id="0be45-280">如果看不到此选项，请参阅[附录：缺少选项](#appendix-missing-options)。</span><span class="sxs-lookup"><span data-stu-id="0be45-280">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  
    1.  <span data-ttu-id="0be45-281">`temp1`在控制台中键入，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-281">Type `temp1` in the Console and then press `Enter`.</span></span>  <span data-ttu-id="0be45-282">表达式的结果显示变量的计算结果为节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-282">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        > ##### <span data-ttu-id="0be45-283">图 16</span><span class="sxs-lookup"><span data-stu-id="0be45-283">Figure 16</span></span>  
        > <span data-ttu-id="0be45-284">Temp1 表达式的结果</span><span class="sxs-lookup"><span data-stu-id="0be45-284">The result of the temp1 expression</span></span>  
        > ![Temp1 表达式的结果][ImageResultTemp1]  
        
### <span data-ttu-id="0be45-286">复制 JS 路径</span><span class="sxs-lookup"><span data-stu-id="0be45-286">Copy JS path</span></span>   

<span data-ttu-id="0be45-287">如果需要在自动测试中引用节点，请将 JavaScript 路径复制到该节点。</span><span class="sxs-lookup"><span data-stu-id="0be45-287">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="0be45-288">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-288">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-289">在 "**复制 JS 路径**" 下，右键单击 **"比较 Karamazov"** ，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-289">Under **Copy JS path**, right-click **The Brothers Karamazov** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-290">`<li>The Brothers Karamazov</li>`在 DOM 树中单击鼠标右键，然后选择 "**复制**  >  **复制 JS 路径**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-290">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and select **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="0be45-291">`document.querySelector()`解析为该节点的表达式已复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0be45-291">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="0be45-292">按 `Control` + `V` \ （Windows \）或 `Command` + `V` \ （macOS \）将表达式粘贴到控制台。</span><span class="sxs-lookup"><span data-stu-id="0be45-292">Press `Control`+`V` \(Windows\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="0be45-293">按 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="0be45-293">Press `Enter` to evaluate the expression.</span></span>
        
        > ##### <span data-ttu-id="0be45-294">图 17</span><span class="sxs-lookup"><span data-stu-id="0be45-294">Figure 17</span></span>  
        > <span data-ttu-id="0be45-295">Copy JS 路径表达式的结果</span><span class="sxs-lookup"><span data-stu-id="0be45-295">The result of the Copy JS Path expression</span></span>  
        > ![Copy JS 路径表达式的结果][ImageResultCopyJSPath]  
        
## <span data-ttu-id="0be45-297">DOM 更改时中断</span><span class="sxs-lookup"><span data-stu-id="0be45-297">Break on DOM changes</span></span>   

<span data-ttu-id="0be45-298">DevTools 使你能够在 JavaScript 修改 DOM 时暂停页面的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="0be45-298">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="0be45-299">属性修改中断</span><span class="sxs-lookup"><span data-stu-id="0be45-299">Break on attribute modifications</span></span>   

<span data-ttu-id="0be45-300">当你希望暂停导致节点的任何属性更改的 JavaScript 时，请使用属性修改断点。</span><span class="sxs-lookup"><span data-stu-id="0be45-300">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="0be45-301">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-301">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-302">在 "**属性修改时中断**" 下，右键单击 " **Sauerkraut** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-302">Under **Break on attribute modifications**, right-click **Sauerkraut** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-303">在 DOM 树中，右键单击 `<li id="target">Sauerkraut</li>` 并选择 **"**  >  **属性修改**时中断"。</span><span class="sxs-lookup"><span data-stu-id="0be45-303">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and select **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="0be45-304">请参阅附录：如果无法看到此选项，则为 "[缺少选项](#appendix-missing-options)"。</span><span class="sxs-lookup"><span data-stu-id="0be45-304">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>
        
        > ##### <span data-ttu-id="0be45-305">图18</span><span class="sxs-lookup"><span data-stu-id="0be45-305">Figure 18</span></span>  
        > <span data-ttu-id="0be45-306">属性修改中断</span><span class="sxs-lookup"><span data-stu-id="0be45-306">Break on attribute modifications</span></span>  
        > ![属性修改中断][ImageBreakAttributeModification]  
        
    1.  <span data-ttu-id="0be45-308">在下一步中，你将指示你单击暂停页面代码的按钮。</span><span class="sxs-lookup"><span data-stu-id="0be45-308">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="0be45-309">页面暂停后，您将无法再滚动页面。</span><span class="sxs-lookup"><span data-stu-id="0be45-309">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="0be45-310">必须单击 "**恢复脚本** ![ 恢复脚本 ][ImageResumeScriptIcon] " 才能使页面再次滚动。</span><span class="sxs-lookup"><span data-stu-id="0be45-310">You must click **Resume Script** ![Resume Script][ImageResumeScriptIcon] in order to make the page scrollable again.</span></span>
        
        > ##### <span data-ttu-id="0be45-311">图19</span><span class="sxs-lookup"><span data-stu-id="0be45-311">Figure 19</span></span>  
        > <span data-ttu-id="0be45-312">恢复运行脚本的位置</span><span class="sxs-lookup"><span data-stu-id="0be45-312">Where to resume script running</span></span>  
        > ![恢复运行脚本的位置][ImageResumeScript]  
        
    1.  <span data-ttu-id="0be45-314">单击上面的 "**设置背景**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="0be45-314">Click the **Set Background** button above.</span></span>  <span data-ttu-id="0be45-315">这会将 `style` 节点的属性设置为 `background-color:thistle` 。</span><span class="sxs-lookup"><span data-stu-id="0be45-315">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="0be45-316">DevTools 暂停页面并突出显示导致属性更改的代码。</span><span class="sxs-lookup"><span data-stu-id="0be45-316">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="0be45-317">如前面所述，单击 "**恢复脚本** ![ 恢复脚本 ][ImageResumeScriptIcon] "。</span><span class="sxs-lookup"><span data-stu-id="0be45-317">Click **Resume Script** ![Resume Script][ImageResumeScriptIcon], as mentioned earlier.</span></span>  
    
### <span data-ttu-id="0be45-318">节点删除时中断</span><span class="sxs-lookup"><span data-stu-id="0be45-318">Break on node removal</span></span>   

<span data-ttu-id="0be45-319">如果要在删除特定节点时暂停，请使用节点删除断点。</span><span class="sxs-lookup"><span data-stu-id="0be45-319">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="0be45-320">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-320">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-321">在 "**节点删除时中断**" 下，右键单击 " **Neuromancer** "，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-321">Under **Break on Node Removal**, right-click **Neuromancer** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-322">在 DOM 树中，右键单击 `<li id="target">Neuromancer</li>` 并选择 **"**  >  **删除节点**时中断"。</span><span class="sxs-lookup"><span data-stu-id="0be45-322">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and select **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="0be45-323">请参阅附录：如果无法看到此选项，则为 "[缺少选项](#appendix-missing-options)"。</span><span class="sxs-lookup"><span data-stu-id="0be45-323">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="0be45-324">单击上面的 "**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="0be45-324">Click the **Delete** button above.</span></span>  <span data-ttu-id="0be45-325">DevTools 暂停页面并突出显示导致节点被删除的代码。</span><span class="sxs-lookup"><span data-stu-id="0be45-325">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="0be45-326">单击 "**恢复脚本** ![ 恢复脚本" ][ImageResumeScriptIcon] 。</span><span class="sxs-lookup"><span data-stu-id="0be45-326">Click **Resume Script** ![Resume Script][ImageResumeScriptIcon].</span></span>  
    
### <span data-ttu-id="0be45-327">子树修改中断</span><span class="sxs-lookup"><span data-stu-id="0be45-327">Break on subtree modifications</span></span>   

<span data-ttu-id="0be45-328">在节点上放置子树修改断点后，在添加或删除节点的任何子代时，DevTools 将暂停页面。</span><span class="sxs-lookup"><span data-stu-id="0be45-328">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="0be45-329">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="0be45-329">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="0be45-330">在 "**子树修改时中断**" 下，右键单击**深度的火**，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-330">Under **Break on Subtree Modifications**, right-click **A Fire Upon The Deep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="0be45-331">在 DOM 树中，右键单击 `<ul id="target">` （上面的节点 `<li>A Fire Upon the Deep</li>` ），然后选择 "在**Break On**  >  **子树修改**时中断"。</span><span class="sxs-lookup"><span data-stu-id="0be45-331">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and select **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="0be45-332">请参阅附录：如果无法看到此选项，则为 "[缺少选项](#appendix-missing-options)"。</span><span class="sxs-lookup"><span data-stu-id="0be45-332">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="0be45-333">单击 "**添加子级**"。</span><span class="sxs-lookup"><span data-stu-id="0be45-333">Click **Add Child**.</span></span>  <span data-ttu-id="0be45-334">由于 `<li>` 节点已添加到列表，代码暂停。</span><span class="sxs-lookup"><span data-stu-id="0be45-334">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="0be45-335">单击 "**恢复脚本** ![ 恢复脚本" ][ImageResumeScriptIcon] 。</span><span class="sxs-lookup"><span data-stu-id="0be45-335">Click **Resume Script** ![Resume Script][ImageResumeScriptIcon].</span></span>  
    
## <span data-ttu-id="0be45-336">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0be45-336">Next steps</span></span>   

<span data-ttu-id="0be45-337">这涉及 DevTools 中的大部分与 DOM 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="0be45-337">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="0be45-338">你可以通过右键单击 DOM 树中的节点并试用本教程中未介绍的其他选项来发现其余部分。</span><span class="sxs-lookup"><span data-stu-id="0be45-338">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="0be45-339">另请参阅["元素" 面板键盘快捷方式][DevToolsShortcutsElements]。</span><span class="sxs-lookup"><span data-stu-id="0be45-339">See also [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="0be45-340">查看[Microsoft Edge DevTools 主页][MicrosoftEdgeDevTools]以了解你可以通过 DevTools 执行的其他操作。</span><span class="sxs-lookup"><span data-stu-id="0be45-340">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  



## <span data-ttu-id="0be45-341">附录： HTML 与 DOM</span><span class="sxs-lookup"><span data-stu-id="0be45-341">Appendix: HTML versus the DOM</span></span>   

<span data-ttu-id="0be45-342">本节将快速介绍 HTML 和 DOM 之间的区别。</span><span class="sxs-lookup"><span data-stu-id="0be45-342">This section quickly explains the difference between HTML and the DOM.</span></span>  

<span data-ttu-id="0be45-343">使用 web 浏览器请求页面时，服务器将返回 HTML，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0be45-343">When you use a web browser to request a page, the server returns HTML like this:</span></span>  

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

<span data-ttu-id="0be45-344">浏览器分析 HTML 并创建对象树，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0be45-344">The browser parses the HTML and creates a tree of objects like this:</span></span>  

```dom
html
  head
    title
  body
    h1
    p
    script
```  

<span data-ttu-id="0be45-345">表示页面内容的此对象树（即表示页面内容的节点）称为 DOM。</span><span class="sxs-lookup"><span data-stu-id="0be45-345">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  <span data-ttu-id="0be45-346">现在，它看起来与 HTML 相同，但假设 HTML 底部引用的脚本运行此代码：</span><span class="sxs-lookup"><span data-stu-id="0be45-346">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs this code:</span></span>  

```javascript
const h1 = document.querySelector('h1');
h1.parentElement.removeChild(h1);
const p = document.createElement('p');
p.textContent = 'Wildcard!';
document.body.appendChild(p);
```  

<span data-ttu-id="0be45-347">该代码将删除 `h1` 节点，并将另一个 `p` 节点添加到 DOM。</span><span class="sxs-lookup"><span data-stu-id="0be45-347">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="0be45-348">完整的 DOM 现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="0be45-348">The complete DOM now looks like this:</span></span>  

```dom
html
  head
    title
  body
    p
    script
    p
```  

<span data-ttu-id="0be45-349">页面的 HTML 现在与 DOM 不同。</span><span class="sxs-lookup"><span data-stu-id="0be45-349">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="0be45-350">换句话说，HTML 表示初始页面内容，DOM 表示当前页面内容。</span><span class="sxs-lookup"><span data-stu-id="0be45-350">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="0be45-351">当 JavaScript 添加、删除或编辑节点时，DOM 将与 HTML 不同。</span><span class="sxs-lookup"><span data-stu-id="0be45-351">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="0be45-352">请参阅[DOM 简介][MDNIntroductionToDOM]以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="0be45-352">See [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view   

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and select **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    > ##### Figure 19  
    > Scroll into view  
    > ![Scroll into view][ImageScrollView]  
    -->  

## <span data-ttu-id="0be45-353">附录：缺少选项</span><span class="sxs-lookup"><span data-stu-id="0be45-353">Appendix: Missing options</span></span>   

<span data-ttu-id="0be45-354">本教程中的许多说明将指导你右键单击 DOM 树中的节点，然后从弹出的上下文菜单中选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="0be45-354">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="0be45-355">如果在上下文菜单中看不到指定的选项，请尝试右键单击节点文本以外的位置。</span><span class="sxs-lookup"><span data-stu-id="0be45-355">If you do not see the specified option in the context menu, try right-clicking away from the node text.</span></span>  

> ##### <span data-ttu-id="0be45-356">图20</span><span class="sxs-lookup"><span data-stu-id="0be45-356">Figure 20</span></span>  
> <span data-ttu-id="0be45-357">如果未看到所有选项，请单击的位置</span><span class="sxs-lookup"><span data-stu-id="0be45-357">Where to click if you are not seeing all the options</span></span>  
> ![如果未看到所有选项，请单击的位置][ImageNotSeeingAllOptions]  

<!-- image links -->  

[ImageInspectIcon]: /microsoft-edge/devtools-guide-chromium/media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: /microsoft-edge/devtools-guide-chromium/media/resume-script-icon.msft.png  

[ImageInspectingNode]: /microsoft-edge/devtools-guide-chromium/media/dom-glitch-dom-examples-michelangelo-inspect.msft.png "图1：检查节点"  
[ImageHighlightingMichelangeloNode]: /microsoft-edge/devtools-guide-chromium/media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png "图2：突出显示 Michelangelo 节点"  
[ImageInspect]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-select-element-page-inspect.msft.png "图3： "检查" 图标"  
[ImageInspectingRingoNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png "图4：检查 Ringo 节点"  
[ImageInspectingUlNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png "图5：检查 ul 节点"  
[ImageScrollView]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png "图6：滚动到视图"  
[ImageHighlightingQuerySearchBar]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-search-nodes-highlight.msft.png "图7：在搜索栏中突出显示查询"  
[ImageEditingText]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-content.msft.png "图8：编辑文本"  
[ImageEditingNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-attributes-highlighted.msft.png "图9：编辑节点"  
[ImageAddingStyleAttributeNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-attributes-inline-css.msft.png "图10：向节点添加样式属性"  
[ImageChangingNodeButton]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-node-type-button.msft.png "图11：将节点类型更改为按钮"  
[ImageDraggingNodeTopList]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-reorder-dom-nodes.msft.png "图12：将节点拖动到列表顶部"  
[ImageNodeDomTreeAfterHidden]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-hide-a-node.msft.png "图13：隐藏的节点在 DOM 树中的显示效果"  
[ImageFirstConsole]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png "图14：控制台中第一个 $0 表达式的结果"  
[ImageSecondConsole]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png "图15：控制台中第二个 $0 表达式的结果"  
[ImageResultTemp1]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png "图16： temp1 表达式的结果"  
[ImageResultCopyJSPath]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png "图17：复制 JS 路径表达式的结果"  
[ImageBreakAttributeModification]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png "图18：在属性修改时中断"  
[ImageResumeScript]: /microsoft-edge/devtools-guide-chromium/media/dom-break-attribute-modifications-sources-paused-on.msft.png "图19：运行脚本的恢复位置"  
[ImageNotSeeingAllOptions]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-right-click-right-side.msft.png "图20：如果未看到所有选项，请在何处单击"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge \ （Chromium \）开发人员工具"  
[DevToolsCssGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门"  
[DevToolsShortcutsElements]: /microsoft-edge/devtools-guide-chromium/shortcuts#elements-panel-keyboard-shortcuts "元素面板键盘快捷方式-Microsoft Edge DevTools 键盘快捷方式"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge （Chromium） DevTools DOM 示例 |故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 |MDN"  

> [!NOTE]
> <span data-ttu-id="0be45-384">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0be45-384">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0be45-385">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="0be45-385">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="0be45-387">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0be45-387">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
