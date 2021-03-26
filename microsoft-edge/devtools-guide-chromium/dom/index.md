---
description: 如何查看节点、搜索节点、编辑节点、引用控制台中的节点、中断节点更改等。
title: 查看和更改 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
ms.openlocfilehash: e4c08fb2fd5f360f037502c04edabaabb873ba16
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439238"
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

# <a name="get-started-with-viewing-and-changing-the-dom"></a><span data-ttu-id="32708-104">查看和更改 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="32708-104">Get started with viewing and changing the DOM</span></span>  

<span data-ttu-id="32708-105">完成这些交互式教程以了解使用 Microsoft Edge 开发人员工具查看和更改页面 DOM 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="32708-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="32708-106">本教程假定你知道 DOM 和 HTML 之间的区别。</span><span class="sxs-lookup"><span data-stu-id="32708-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="32708-107">导航到“[附录：HTML 与 DOM](#appendix-html-versus-the-dom)”了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="32708-107">Navigate to [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <a name="open-dom-examples"></a><span data-ttu-id="32708-108">打开 DOM 示例</span><span class="sxs-lookup"><span data-stu-id="32708-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="32708-109">按住 `Control`（Windows、Linux）或 `Command` (macOS)，然后选择“**DOM 示例**”以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="32708-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="32708-110">DOM 示例</span><span class="sxs-lookup"><span data-stu-id="32708-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <a name="view-dom-nodes"></a><span data-ttu-id="32708-111">查看 DOM 节点</span><span class="sxs-lookup"><span data-stu-id="32708-111">View DOM nodes</span></span>  

<span data-ttu-id="32708-112">在“元素”面板的 DOM 树中，你可以在开发人员工具中执行所有 DOM 相关活动。</span><span class="sxs-lookup"><span data-stu-id="32708-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <a name="inspect-a-node"></a><span data-ttu-id="32708-113">检查节点</span><span class="sxs-lookup"><span data-stu-id="32708-113">Inspect a node</span></span>  

<span data-ttu-id="32708-114">当你对特定 DOM 节点感兴趣时，可通过“**检查**”快速打开开发人员工具并调查该节点。</span><span class="sxs-lookup"><span data-stu-id="32708-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="32708-115">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-116">在“**检查节点**”下，右键选择“**Michelangelo**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-116">Under **Inspect a Node**, right-choose **Michelangelo** and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="32708-118">检查节点</span><span class="sxs-lookup"><span data-stu-id="32708-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="32708-119">此时将打开开发人员工具的“**元素**”工具。</span><span class="sxs-lookup"><span data-stu-id="32708-119">The **Elements** tool of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="32708-120">将在“**DOM 树**”中突出显示。</span><span class="sxs-lookup"><span data-stu-id="32708-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="突出显示 Michelangelo 节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="32708-122">突出显示 `Michelangelo` 节点</span><span class="sxs-lookup"><span data-stu-id="32708-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="32708-123">选择开发人员工具左上角的“**检查**”（“![检查](../media/inspect-icon.msft.png)”）图标。</span><span class="sxs-lookup"><span data-stu-id="32708-123">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="“检查”图标" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="32708-125">“**检查**”图标</span><span class="sxs-lookup"><span data-stu-id="32708-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="32708-126">在“**检查节点**”下，选择“**Tokyo**”文本。</span><span class="sxs-lookup"><span data-stu-id="32708-126">Under **Inspect a Node**, choose the **Tokyo** text.</span></span>  <span data-ttu-id="32708-127">现在，`<li>Tokyo</li>` 在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="32708-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="32708-128">检查节点也是查看和更改节点样式的第一步。</span><span class="sxs-lookup"><span data-stu-id="32708-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="32708-129">导航到“[查看和更改 CSS 入门][DevToolsCssGetStarted]”。</span><span class="sxs-lookup"><span data-stu-id="32708-129">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <a name="navigate-the-dom-tree-with-a-keyboard"></a><span data-ttu-id="32708-130">使用键盘浏览 DOM 树</span><span class="sxs-lookup"><span data-stu-id="32708-130">Navigate the DOM Tree with a keyboard</span></span>  

<span data-ttu-id="32708-131">在 DOM 树中选择节点后，可使用键盘浏览 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="32708-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="32708-132">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-133">在“**使用键盘浏览 DOM 树**”下，右键选择“**Ringo**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-133">Under **Navigate the DOM Tree with a Keyboard**, right-choose **Ringo** and choose **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="32708-134">在 DOM 树中已选中。</span><span class="sxs-lookup"><span data-stu-id="32708-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="检查 Ringo 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="32708-136">检查 `Ringo` 节点</span><span class="sxs-lookup"><span data-stu-id="32708-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="32708-137">选择 `Up` 箭头键 2 次。</span><span class="sxs-lookup"><span data-stu-id="32708-137">Select the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="32708-138">已选中。</span><span class="sxs-lookup"><span data-stu-id="32708-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="检查 ul 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="32708-140">检查 `ul` 节点</span><span class="sxs-lookup"><span data-stu-id="32708-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="32708-141">选择 `Left` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="32708-141">Select the `Left` arrow key.</span></span>  <span data-ttu-id="32708-142">`<ul>` 列表会折叠。</span><span class="sxs-lookup"><span data-stu-id="32708-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="32708-143">再次选择 `Left` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="32708-143">Select the `Left` arrow key again.</span></span>  <span data-ttu-id="32708-144">`<ul>` 节点的父节点已被选中。</span><span class="sxs-lookup"><span data-stu-id="32708-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="32708-145">在这种情况下，它是 ID 为 `navigate-the-dom-tree-with-a-keyboard-1` 的 `<div>`。</span><span class="sxs-lookup"><span data-stu-id="32708-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="32708-146">选择 `Down` 箭头键 2 次，以便重新选择刚刚折叠的 `<ul>` 列表。</span><span class="sxs-lookup"><span data-stu-id="32708-146">Select the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="32708-147">应如下所示：</span><span class="sxs-lookup"><span data-stu-id="32708-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="32708-148">选择 `Right` 箭头键。</span><span class="sxs-lookup"><span data-stu-id="32708-148">Select the `Right` arrow key.</span></span>  <span data-ttu-id="32708-149">列表将展开。</span><span class="sxs-lookup"><span data-stu-id="32708-149">The list expands.</span></span>  

### <a name="scroll-into-view"></a><span data-ttu-id="32708-150">滚动到视图</span><span class="sxs-lookup"><span data-stu-id="32708-150">Scroll into view</span></span>  

<span data-ttu-id="32708-151">查看 DOM 树时，你可能会发现自己对当前不在视区中的 DOM 节点感兴趣。</span><span class="sxs-lookup"><span data-stu-id="32708-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="32708-152">例如，假设你滚动到页面底部，并且你对页面顶部的 `<h1>` 节点感兴趣。</span><span class="sxs-lookup"><span data-stu-id="32708-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="32708-153">“**滚动到视图**”可让你快速重新定位视区，以便能够查看节点。</span><span class="sxs-lookup"><span data-stu-id="32708-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to review the node.</span></span>  

1.  <span data-ttu-id="32708-154">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-155">在“**滚动到视图**”下，右键选择“**Magritte**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-155">Under **Scroll into View**, right-choose **Magritte** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="32708-156">滚动到“DOM 示例”页面的底部。</span><span class="sxs-lookup"><span data-stu-id="32708-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="32708-157">仍应在 DOM 树中选择 `<li>Magritte</li>` 节点。</span><span class="sxs-lookup"><span data-stu-id="32708-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="32708-158">如果没有，请返回到“[滚动到视图](#scroll-into-view)”，然后重新开始。</span><span class="sxs-lookup"><span data-stu-id="32708-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="32708-159">将鼠标悬停在 `<li>Magritte</li>` 节点上，打开上下文菜单（右键单击），然后选择“**滚动到视图**”。</span><span class="sxs-lookup"><span data-stu-id="32708-159">Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.</span></span>  <span data-ttu-id="32708-160">视区将向上滚动，以便你可以查看 **Magritte** 节点。</span><span class="sxs-lookup"><span data-stu-id="32708-160">Your viewport scrolls back up so that you may review the **Magritte** node.</span></span>  <span data-ttu-id="32708-161">如果无法查看“**滚动到视图**”选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。</span><span class="sxs-lookup"><span data-stu-id="32708-161">Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to review the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="滚动到视图" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="32708-163">滚动到视图</span><span class="sxs-lookup"><span data-stu-id="32708-163">Scroll into view</span></span>**  
    :::image-end:::  

### <a name="search-for-nodes"></a><span data-ttu-id="32708-164">搜索节点</span><span class="sxs-lookup"><span data-stu-id="32708-164">Search for nodes</span></span>  

<span data-ttu-id="32708-165">可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="32708-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="32708-166">将光标焦点放在“**元素**”工具上。</span><span class="sxs-lookup"><span data-stu-id="32708-166">Focus your cursor on the **Elements** tool.</span></span>  
1.  <span data-ttu-id="32708-167">选择 `Control`+`F`（Windows、Linux）或 `Command`+`F` (macOS)。</span><span class="sxs-lookup"><span data-stu-id="32708-167">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="32708-168">搜索栏在 DOM 树的底部打开。</span><span class="sxs-lookup"><span data-stu-id="32708-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="32708-169">键入 `The Moon is a Harsh Mistress`。</span><span class="sxs-lookup"><span data-stu-id="32708-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="32708-170">最后一句在 DOM 树中突出显示。</span><span class="sxs-lookup"><span data-stu-id="32708-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="在搜索栏中突出显示查询" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="32708-172">在搜索栏中突出显示查询</span><span class="sxs-lookup"><span data-stu-id="32708-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32708-173">如上所述，搜索栏还支持 CSS 和 XPath 选择器。</span><span class="sxs-lookup"><span data-stu-id="32708-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <a name="edit-the-dom"></a><span data-ttu-id="32708-174">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="32708-174">Edit the DOM</span></span>  

<span data-ttu-id="32708-175">你可以快速编辑 DOM 并查看更改对页面有何影响。</span><span class="sxs-lookup"><span data-stu-id="32708-175">You may edit the DOM on the fly and review how the changes affect the page.</span></span>  

### <a name="edit-content"></a><span data-ttu-id="32708-176">编辑内容</span><span class="sxs-lookup"><span data-stu-id="32708-176">Edit content</span></span>  

<span data-ttu-id="32708-177">若要编辑节点的内容，请双击 DOM 树中的内容。</span><span class="sxs-lookup"><span data-stu-id="32708-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="32708-178">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-179">在“**编辑内容**”下，右键选择“**Michelle**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-179">Under **Edit Content**, right-choose **Michelle** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-180">在 DOM 树中，双击 `Michelle`。</span><span class="sxs-lookup"><span data-stu-id="32708-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="32708-181">换言之，双击 `<li>` 和 `</li>` 之间的文本。</span><span class="sxs-lookup"><span data-stu-id="32708-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="32708-182">此时将突出显示文本，表明该文本已被选中。</span><span class="sxs-lookup"><span data-stu-id="32708-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="编辑文本" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="32708-184">编辑文本</span><span class="sxs-lookup"><span data-stu-id="32708-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="32708-185">删除 `Michelle`，键入 `Leela`，然后选择 `Enter` 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="32708-185">Delete `Michelle`, type `Leela`, then select `Enter` to confirm the change.</span></span>  <span data-ttu-id="32708-186">DOM 中的文本从 **Michelle** 更改为 **Leela**。</span><span class="sxs-lookup"><span data-stu-id="32708-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <a name="edit-attributes"></a><span data-ttu-id="32708-187">编辑属性</span><span class="sxs-lookup"><span data-stu-id="32708-187">Edit attributes</span></span>  

<span data-ttu-id="32708-188">若要编辑属性，请双击属性名称或值。</span><span class="sxs-lookup"><span data-stu-id="32708-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="32708-189">按照说明了解如何向节点添加属性。</span><span class="sxs-lookup"><span data-stu-id="32708-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="32708-190">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-191">在“**编辑属性**”下，右键选择“**Howard**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-191">Under **Edit Attributes**, right-choose **Howard** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="32708-192">双击 `<li>`。</span><span class="sxs-lookup"><span data-stu-id="32708-192">Double-click `<li>`.</span></span>  <span data-ttu-id="32708-193">此时将突出显示文本，表示节点已被选中。</span><span class="sxs-lookup"><span data-stu-id="32708-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="编辑节点" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="32708-195">编辑节点</span><span class="sxs-lookup"><span data-stu-id="32708-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32708-196">选择 `Right` 箭头键，添加空格，键入 `style="background-color:gold"`，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="32708-196">Select the `Right` arrow key, add a space, type `style="background-color:gold"`, and then select `Enter`.</span></span>  <span data-ttu-id="32708-197">节点的背景色将更改为金色。</span><span class="sxs-lookup"><span data-stu-id="32708-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="向节点添加样式属性" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="32708-199">向 `style` 节点添加属性</span><span class="sxs-lookup"><span data-stu-id="32708-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <a name="edit-node-type"></a><span data-ttu-id="32708-200">编辑节点类型</span><span class="sxs-lookup"><span data-stu-id="32708-200">Edit node type</span></span>  

<span data-ttu-id="32708-201">若要编辑节点的类型，请双击该类型，然后键入新类型。</span><span class="sxs-lookup"><span data-stu-id="32708-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="32708-202">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-203">在“**编辑节点类型**”下，右键选择“**Hank**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-203">Under **Edit Node Type**, right-choose **Hank** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-204">双击 `<li>`。</span><span class="sxs-lookup"><span data-stu-id="32708-204">Double-click `<li>`.</span></span>  <span data-ttu-id="32708-205">文本 `li` 将突出显示。</span><span class="sxs-lookup"><span data-stu-id="32708-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="32708-206">删除 `li`，键入 `button`，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="32708-206">Delete `li`, type `button`, then select `Enter`.</span></span>  <span data-ttu-id="32708-207">节点 `<li>` 将更改为 `<button>` 节点。</span><span class="sxs-lookup"><span data-stu-id="32708-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="将节点类型更改为按钮" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="32708-209">将节点类型更改为</span><span class="sxs-lookup"><span data-stu-id="32708-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <a name="reorder-dom-nodes"></a><span data-ttu-id="32708-210">对 DOM 节点重新排序</span><span class="sxs-lookup"><span data-stu-id="32708-210">Reorder DOM nodes</span></span>  

<span data-ttu-id="32708-211">拖动节点以重新排序。</span><span class="sxs-lookup"><span data-stu-id="32708-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="32708-212">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-213">在“**对 DOM 节点重新排序**”下，右键选择“**Elvis Presley**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-213">Under **Reorder DOM Nodes**, right-choose **Elvis Presley** and choose **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="32708-214">它是列表中的最后一项。</span><span class="sxs-lookup"><span data-stu-id="32708-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="32708-215">在 DOM 树中，将 `<li>Elvis Presley</li>` 拖动到列表顶部。</span><span class="sxs-lookup"><span data-stu-id="32708-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="将节点拖动到列表顶部" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="32708-217">将节点拖动到列表顶部</span><span class="sxs-lookup"><span data-stu-id="32708-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <a name="force-state"></a><span data-ttu-id="32708-218">强制状态</span><span class="sxs-lookup"><span data-stu-id="32708-218">Force state</span></span>  

<span data-ttu-id="32708-219">可强制节点保持 `:active`、`:hover`、`:focus`、`:visited` 和 `:focus-within` 等状态。</span><span class="sxs-lookup"><span data-stu-id="32708-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="32708-220">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-221">在“**强制状态**”下，将鼠标悬停在“**The Lord of the Flies**”上。</span><span class="sxs-lookup"><span data-stu-id="32708-221">Under **Force state**, hover on **The Lord of the Flies**.</span></span>  <span data-ttu-id="32708-222">背景色变为橙色。</span><span class="sxs-lookup"><span data-stu-id="32708-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="32708-223">将鼠标悬停在“**The Lord of the Flies**”上，打开上下文菜单（右键单击），然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-223">Hover on **The Lord of the Flies**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-224">将鼠标悬停在 `<li class="demo--hover">The Lord of the Flies</li>` 上，打开上下文菜单（右键单击），然后选择“**强制状态** > **：hover**”。</span><span class="sxs-lookup"><span data-stu-id="32708-224">Hover on `<li class="demo--hover">The Lord of the Flies</li>`, open the contextual menu \(right-click\), and choose **Force State** > **:hover**.</span></span>  <span data-ttu-id="32708-225">如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。</span><span class="sxs-lookup"><span data-stu-id="32708-225">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  <span data-ttu-id="32708-226">即使你实际上没有将鼠标悬停在节点上，背景色仍保持橙色。</span><span class="sxs-lookup"><span data-stu-id="32708-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <a name="hide-a-node"></a><span data-ttu-id="32708-227">隐藏节点</span><span class="sxs-lookup"><span data-stu-id="32708-227">Hide a node</span></span>  

<span data-ttu-id="32708-228">选择 `H` 以隐藏节点。</span><span class="sxs-lookup"><span data-stu-id="32708-228">Select `H` to hide a node.</span></span>  

1.  <span data-ttu-id="32708-229">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-230">在“**隐藏节点**”下，右键选择“**The Stars My Destination**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-230">Under **Hide a node**, right-choose **The Stars My Destination** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-231">选择 `H` 键。</span><span class="sxs-lookup"><span data-stu-id="32708-231">Select the `H` key.</span></span>  <span data-ttu-id="32708-232">节点处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="32708-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="节点隐藏后在 DOM 树中的外观" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="32708-234">节点隐藏后在 DOM 树中的外观</span><span class="sxs-lookup"><span data-stu-id="32708-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="32708-235">再次选择 `H` 键。</span><span class="sxs-lookup"><span data-stu-id="32708-235">Select the `H` key again.</span></span>  <span data-ttu-id="32708-236">节点将再次显示。</span><span class="sxs-lookup"><span data-stu-id="32708-236">The node is shown again.</span></span>  

### <a name="delete-a-node"></a><span data-ttu-id="32708-237">删除节点</span><span class="sxs-lookup"><span data-stu-id="32708-237">Delete a node</span></span>  

<span data-ttu-id="32708-238">选择 `Delete` 以删除节点。</span><span class="sxs-lookup"><span data-stu-id="32708-238">Select `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="32708-239">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-240">在“**删除节点**”下，右键选择“**Foundation**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-240">Under **Delete a Node**, right-choose **Foundation** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-241">选择 `Delete` 键。</span><span class="sxs-lookup"><span data-stu-id="32708-241">Select the `Delete` key.</span></span>  <span data-ttu-id="32708-242">节点将被删除。</span><span class="sxs-lookup"><span data-stu-id="32708-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="32708-243">选择 `Control`+`Z`（Windows、Linux）或 `Command`+`Z` (macOS)。</span><span class="sxs-lookup"><span data-stu-id="32708-243">Select `Control`+`Z` \(Windows, Linux\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="32708-244">最后一个操作将被撤消，节点将重新出现。</span><span class="sxs-lookup"><span data-stu-id="32708-244">The last action is undone and the node reappears.</span></span>  

## <a name="access-nodes-in-the-console"></a><span data-ttu-id="32708-245">访问控制台中的节点</span><span class="sxs-lookup"><span data-stu-id="32708-245">Access nodes in the Console</span></span>  

<span data-ttu-id="32708-246">开发人员工具提供了从控制台访问 DOM 节点或获取每个节点的 JavaScript 引用的一些快捷方式。</span><span class="sxs-lookup"><span data-stu-id="32708-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <a name="reference-the-currently-selected-node-with-0"></a><span data-ttu-id="32708-247">使用 $0 引用当前选定的节点</span><span class="sxs-lookup"><span data-stu-id="32708-247">Reference the currently-selected node with $0</span></span>  

<span data-ttu-id="32708-248">当你检查节点时，节点旁边的 `== $0` 文本意味着可以在控制台中使用变量 `$0` 引用此节点。</span><span class="sxs-lookup"><span data-stu-id="32708-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="32708-249">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-250">在“**使用 $0 引用当前选定的节点**”下，右键选择“**The Left Hand of Darkness**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-250">Under **Reference the currently-selected node with $0**, right-choose **The Left Hand of Darkness** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-251">选择 `Escape` 键以打开控制台抽屉。</span><span class="sxs-lookup"><span data-stu-id="32708-251">Select the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="32708-252">键入 `$0` 并选择 `Enter` 键。</span><span class="sxs-lookup"><span data-stu-id="32708-252">Type `$0` and select the `Enter` key.</span></span>  <span data-ttu-id="32708-253">表达式的结果显示 `$0` 的计算结果为 `<li>The Left Hand of Darkness</li>`。</span><span class="sxs-lookup"><span data-stu-id="32708-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="控制台中第一个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="32708-255">**控制台**中第一个 `$0` 表达式的结果</span><span class="sxs-lookup"><span data-stu-id="32708-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="32708-256">将鼠标悬停在结果上。</span><span class="sxs-lookup"><span data-stu-id="32708-256">Hover on the result.</span></span>  <span data-ttu-id="32708-257">节点在视区中突出显示。</span><span class="sxs-lookup"><span data-stu-id="32708-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="32708-258">在 DOM 树中选择 `<li>Dune</li>`，在控制台中再次键入 `$0`，然后再次选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="32708-258">Choose `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then select `Enter` again.</span></span>  <span data-ttu-id="32708-259">现在，`$0` 的计算结果为 `<li>Dune</li>`。</span><span class="sxs-lookup"><span data-stu-id="32708-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="控制台中第二个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="32708-261">**控制台**中第二个 `$0` 表达式的结果</span><span class="sxs-lookup"><span data-stu-id="32708-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <a name="store-as-global-variable"></a><span data-ttu-id="32708-262">存储为全局变量</span><span class="sxs-lookup"><span data-stu-id="32708-262">Store as global variable</span></span>  

<span data-ttu-id="32708-263">如果需要多次引用某节点，请将其存储为全局变量。</span><span class="sxs-lookup"><span data-stu-id="32708-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="32708-264">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-265">在“**存储为全局变量**”下，将鼠标悬停在“**The Big Sleep**”上，打开上下文菜单（右键单击），然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-265">Under **Store as global variable**, hover on **The Big Sleep**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-266">将鼠标悬停在 DOM 树中的 `<li>The Big Sleep</li>` 上，打开上下文菜单（右键单击），然后选择“**存储为全局变量**”。</span><span class="sxs-lookup"><span data-stu-id="32708-266">Hover on `<li>The Big Sleep</li>` in the DOM Tree, open the contextual menu \(right-click\), and choose **Store as global variable**.</span></span>  <span data-ttu-id="32708-267">如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。</span><span class="sxs-lookup"><span data-stu-id="32708-267">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="32708-268">在控制台中键入 `temp1`，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="32708-268">Type `temp1` in the Console and then select `Enter`.</span></span>  <span data-ttu-id="32708-269">表达式的结果显示变量的计算结果为节点。</span><span class="sxs-lookup"><span data-stu-id="32708-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 表达式的结果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="32708-271">`temp1` 表达式的结果</span><span class="sxs-lookup"><span data-stu-id="32708-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <a name="copy-js-path"></a><span data-ttu-id="32708-272">复制 JS 路径</span><span class="sxs-lookup"><span data-stu-id="32708-272">Copy JS path</span></span>  

<span data-ttu-id="32708-273">当你需要在自动测试中引用 JavaScript 路径时，请将其复制到节点。</span><span class="sxs-lookup"><span data-stu-id="32708-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="32708-274">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-275">在“**复制 JS 路径**”下，将鼠标悬停在“**The Brothers Karamazov**”上，打开上下文菜单（右键单击），然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-275">Under **Copy JS path**, hover on **The Brothers Karamazov**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-276">将鼠标悬停在 DOM 树中的 `<li>The Brothers Karamazov</li>` 上，打开上下文菜单（右键单击），然后选择“**复制”** > “**复制 JS 路径**”。</span><span class="sxs-lookup"><span data-stu-id="32708-276">Hover on `<li>The Brothers Karamazov</li>` in the DOM Tree, open the contextual menu \(right-click\), and choose **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="32708-277">解析为节点的 `document.querySelector()` 表达式已复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="32708-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="32708-278">选择 `Control`+`V`（Windows、Linux）或 `Command`+`V` (macOS) 以将表达式粘贴到控制台中。</span><span class="sxs-lookup"><span data-stu-id="32708-278">Select `Control`+`V` \(Windows, Linux\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="32708-279">选择 `Enter` 以计算表达式。</span><span class="sxs-lookup"><span data-stu-id="32708-279">Select `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="“复制 JS 路径”表达式的结果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="32708-281">“**复制 JS 路径**”表达式的结果</span><span class="sxs-lookup"><span data-stu-id="32708-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <a name="break-on-dom-changes"></a><span data-ttu-id="32708-282">中断 DOM 更改</span><span class="sxs-lookup"><span data-stu-id="32708-282">Break on DOM changes</span></span>  

<span data-ttu-id="32708-283">开发人员工具使你可以在 JavaScript 修改 DOM 时暂停页面的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="32708-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <a name="break-on-attribute-modifications"></a><span data-ttu-id="32708-284">中断属性修改</span><span class="sxs-lookup"><span data-stu-id="32708-284">Break on attribute modifications</span></span>  

<span data-ttu-id="32708-285">如果要暂停导致节点任何属性发生更改的 JavaScript，请使用属性修改断点。</span><span class="sxs-lookup"><span data-stu-id="32708-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="32708-286">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-287">在“**中断属性修改**”下，右键选择“**Sauerkraut**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-287">Under **Break on attribute modifications**, right-choose **Sauerkraut** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-288">在 DOM 树中，将鼠标悬停在 `<li id="target">Sauerkraut</li>` 上，打开上下文菜单（右键单击），然后选择“**中断** > **属性修改**”。</span><span class="sxs-lookup"><span data-stu-id="32708-288">In the DOM Tree, hover on `<li id="target">Sauerkraut</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="32708-289">如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。</span><span class="sxs-lookup"><span data-stu-id="32708-289">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="中断属性修改" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="32708-291">中断属性修改</span><span class="sxs-lookup"><span data-stu-id="32708-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="32708-292">在下一步骤中，系统将指示你选择用于暂停页面代码的按钮。</span><span class="sxs-lookup"><span data-stu-id="32708-292">In the next step you are going to be instructed to choose a button that pauses the code of the page.</span></span>  <span data-ttu-id="32708-293">页面暂停后，你将无法再滚动页面。</span><span class="sxs-lookup"><span data-stu-id="32708-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="32708-294">必须选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”），才能使页面再次滚动。</span><span class="sxs-lookup"><span data-stu-id="32708-294">You must choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="在何处继续运行脚本" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="32708-296">在何处继续运行脚本</span><span class="sxs-lookup"><span data-stu-id="32708-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="32708-297">选择上面的“**设置背景**”按钮。</span><span class="sxs-lookup"><span data-stu-id="32708-297">Choose the **Set Background** button above.</span></span>  <span data-ttu-id="32708-298">这会将节点的 `style` 属性设置为 `background-color:thistle`。</span><span class="sxs-lookup"><span data-stu-id="32708-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="32708-299">开发人员工具将暂停页面并突出显示导致属性发生更改的代码。</span><span class="sxs-lookup"><span data-stu-id="32708-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="32708-300">如上所述，选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”）。</span><span class="sxs-lookup"><span data-stu-id="32708-300">Choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\), as mentioned earlier.</span></span>  
    
### <a name="break-on-node-removal"></a><span data-ttu-id="32708-301">中断节点删除</span><span class="sxs-lookup"><span data-stu-id="32708-301">Break on node removal</span></span>  

<span data-ttu-id="32708-302">如果要在删除特定节点时暂停，请使用节点删除断点。</span><span class="sxs-lookup"><span data-stu-id="32708-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="32708-303">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-304">在“**中断节点删除**”下，右键选择“**Neuromancer**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-304">Under **Break on Node Removal**, right-choose **Neuromancer** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-305">在 DOM 树中，将鼠标悬停在 `<li id="target">Neuromancer</li>` 上，打开上下文菜单（右键单击），然后选择“**中断** > **节点删除**”。</span><span class="sxs-lookup"><span data-stu-id="32708-305">In the DOM Tree, hover on `<li id="target">Neuromancer</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="32708-306">如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。</span><span class="sxs-lookup"><span data-stu-id="32708-306">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="32708-307">选择上面的“**删除**”按钮。</span><span class="sxs-lookup"><span data-stu-id="32708-307">Choose the **Delete** button above.</span></span>  <span data-ttu-id="32708-308">开发人员工具将暂停页面并突出显示导致节点被删除的代码。</span><span class="sxs-lookup"><span data-stu-id="32708-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="32708-309">选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”）。</span><span class="sxs-lookup"><span data-stu-id="32708-309">Choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\).</span></span>  
    
### <a name="break-on-subtree-modifications"></a><span data-ttu-id="32708-310">中断子树修改</span><span class="sxs-lookup"><span data-stu-id="32708-310">Break on subtree modifications</span></span>  

<span data-ttu-id="32708-311">在节点上放置子树修改断点后，在添加或删除节点的任何后代时，开发人员工具将暂停页面。</span><span class="sxs-lookup"><span data-stu-id="32708-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="32708-312">[打开 DOM 示例](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="32708-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="32708-313">在“**中断子树修改**”下，右键选择“**A Fire Upon The Deep**”，然后选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="32708-313">Under **Break on Subtree Modifications**, right-choose **A Fire Upon The Deep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="32708-314">在 DOM 树中，将鼠标悬停在 `<ul id="target">` 上（该节点位于 `<li>A Fire Upon the Deep</li>` 上方），打开上下文菜单（右键单击），然后选择“**中断** > **子树修改**”。</span><span class="sxs-lookup"><span data-stu-id="32708-314">In the DOM Tree, hover on `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="32708-315">如果未显示该选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。</span><span class="sxs-lookup"><span data-stu-id="32708-315">If the option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).</span></span>  
    1.  <span data-ttu-id="32708-316">选择“**添加子级**。</span><span class="sxs-lookup"><span data-stu-id="32708-316">Choose **Add Child**.</span></span>  <span data-ttu-id="32708-317">由于向列表中添加了 `<li>` 节点，因此代码将暂停。</span><span class="sxs-lookup"><span data-stu-id="32708-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="32708-318">选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”）。</span><span class="sxs-lookup"><span data-stu-id="32708-318">Choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\).</span></span>  
    
## <a name="next-steps"></a><span data-ttu-id="32708-319">后续步骤</span><span class="sxs-lookup"><span data-stu-id="32708-319">Next steps</span></span>  

<span data-ttu-id="32708-320">它涵盖了开发人员工具中与 DOM 相关的大部分功能。</span><span class="sxs-lookup"><span data-stu-id="32708-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="32708-321">通过将鼠标悬停在 DOM 树中的节点上，打开上下文菜单（右键单击）并尝试本教程中未涵盖的其他选项，你能够发现其余功能。</span><span class="sxs-lookup"><span data-stu-id="32708-321">You are able to discover the rest of the features by hovering on nodes in the DOM Tree, opening the contextual menu \(right-click\), and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="32708-322">导航至“[‘元素’面板键盘快捷方式][DevToolsShortcutsElements]”。</span><span class="sxs-lookup"><span data-stu-id="32708-322">Navigate to [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="32708-323">查看 [Microsoft Edge 开发人员工具主页][MicrosoftEdgeDevTools]，了解可使用开发人员工具执行的所有其他内容。</span><span class="sxs-lookup"><span data-stu-id="32708-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <a name="appendix-html-versus-the-dom"></a><span data-ttu-id="32708-324">附录：HTML 与 DOM</span><span class="sxs-lookup"><span data-stu-id="32708-324">Appendix: HTML versus the DOM</span></span>  

<span data-ttu-id="32708-325">以下部分快速介绍了 HTML 和 DOM 之间的区别。</span><span class="sxs-lookup"><span data-stu-id="32708-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="32708-326">当你使用 Web 浏览器请求页面时，服务器将返回 HTML，如以下代码片段</span><span class="sxs-lookup"><span data-stu-id="32708-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

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
      <span data-ttu-id="32708-327">浏览器将分析 HTML 并创建一个对象树，如以下列表。</span><span class="sxs-lookup"><span data-stu-id="32708-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
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

<span data-ttu-id="32708-328">这一表示页面内容的对象或节点树称为 DOM。</span><span class="sxs-lookup"><span data-stu-id="32708-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="32708-329">现在，它看起来与 HTML 相同，但假设在 HTML 底部引用的脚本运行以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="32708-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="32708-330">该代码删除了 `h1` 节点，并将另一个 `p` 节点添加到 DOM。</span><span class="sxs-lookup"><span data-stu-id="32708-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="32708-331">完整的 DOM 现在显示以下列表。</span><span class="sxs-lookup"><span data-stu-id="32708-331">The complete DOM now displays the following list.</span></span>  
      
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

<span data-ttu-id="32708-332">页面的 HTML 现在与 DOM 不同。</span><span class="sxs-lookup"><span data-stu-id="32708-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="32708-333">换句话说，HTML 表示初始页面内容，而 DOM 表示当前页面内容。</span><span class="sxs-lookup"><span data-stu-id="32708-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="32708-334">当 JavaScript 添加、删除或编辑节点时，DOM 将与 HTML 不同。</span><span class="sxs-lookup"><span data-stu-id="32708-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="32708-335">导航到“[DOM 简介][MDNIntroductionToDOM]”以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="32708-335">Navigate to [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.  Your viewport scrolls back up so that the **Magritte** node is displayed.  If you the **Scroll into view** option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <a name="appendix-missing-options"></a><span data-ttu-id="32708-336">附录：缺少选项</span><span class="sxs-lookup"><span data-stu-id="32708-336">Appendix: Missing options</span></span>  

<span data-ttu-id="32708-337">本教程中的许多说明指示你将鼠标悬停在 DOM 树中的某个节点上，打开上下文菜单（右键单击），然后从弹出的上下文菜单中选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="32708-337">Many of the instructions in this tutorial instruct you to hover on a node in the DOM Tree, open the contextual menu \(right-click\), and then choose an option from the context menu that pops up.</span></span>  <span data-ttu-id="32708-338">如果未显示上下文菜单中的指定选项，请尝试将鼠标悬停在节点文本之外并打开上下文菜单（右键单击）。</span><span class="sxs-lookup"><span data-stu-id="32708-338">If the specified option in the context menu is not displayed, try hovering away from the node text and opening the contextual menu \(right-click\).</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="未显示所有选项时在何处选择" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="32708-340">未显示所有选项时在何处选择</span><span class="sxs-lookup"><span data-stu-id="32708-340">Where to choose if all of the options are not displayed</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="32708-341">联系 Microsoft Edge 开发人员工具团队</span><span class="sxs-lookup"><span data-stu-id="32708-341">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-tool-keyboard-shortcuts "“元素”工具键盘快捷方式 - Microsoft Edge 开发人员工具键盘快捷方式 | Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) 开发人员工具 DOM 示例 | Glitch"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 | MDN"  

> [!NOTE]
> <span data-ttu-id="32708-347">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="32708-347">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="32708-348">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="32708-348">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="32708-350">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="32708-350">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
