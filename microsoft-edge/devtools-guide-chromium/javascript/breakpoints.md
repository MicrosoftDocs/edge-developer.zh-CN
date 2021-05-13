---
description: 了解在 Microsoft Edge 开发工具中暂停代码的所有方法。
title: 如何在 Microsoft Edge 开发工具中使用断点暂停代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: fda536deb7177b933013120fc11b0896acfbbe5c
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564173"
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
# <a name="how-to-pause-your-code-with-breakpoints-in-microsoft-edge-devtools"></a><span data-ttu-id="4411f-104">如何在 Microsoft Edge 开发工具中使用断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="4411f-104">How to pause your code with breakpoints in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="4411f-105">使用断点暂停 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="4411f-105">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="4411f-106">本文介绍了 DevTools 中提供的每种断点类型，以及何时使用以及如何设置每种类型。</span><span class="sxs-lookup"><span data-stu-id="4411f-106">This article explains each type of breakpoint available in DevTools, as well as when to use and how to set each type.</span></span>

<span data-ttu-id="4411f-107">有关使用现有网页的介绍性教程，请导航到在开发人员工具中Microsoft Edge [JavaScript 入门][DevtoolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="4411f-107">For an introductory tutorial using an existing webpage, navigate to [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>

## <a name="overview-of-when-to-use-each-breakpoint-type"></a><span data-ttu-id="4411f-108">何时使用各断点类型的概述</span><span class="sxs-lookup"><span data-stu-id="4411f-108">Overview of when to use each breakpoint type</span></span>  

<span data-ttu-id="4411f-109">最著名的断点类型是代码行。</span><span class="sxs-lookup"><span data-stu-id="4411f-109">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="4411f-110">但代码行断点设置效率可能较低，尤其是在不知道具体查找位置，或者正使用大型代码库时。</span><span class="sxs-lookup"><span data-stu-id="4411f-110">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="4411f-111">通过了解如何以及何时使用其他类型的断点，可在调试时节省自己的时间。</span><span class="sxs-lookup"><span data-stu-id="4411f-111">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="4411f-112">断点类型</span><span class="sxs-lookup"><span data-stu-id="4411f-112">Breakpoint Type</span></span> | <span data-ttu-id="4411f-113">使用此类型，如果希望暂停...</span><span class="sxs-lookup"><span data-stu-id="4411f-113">Use This When You Want To Pause...</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="4411f-114">代码行</span><span class="sxs-lookup"><span data-stu-id="4411f-114">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="4411f-115">在代码的准确区域上。</span><span class="sxs-lookup"><span data-stu-id="4411f-115">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="4411f-116">条件代码行</span><span class="sxs-lookup"><span data-stu-id="4411f-116">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="4411f-117">在代码的准确区域上，但仅在某些其他条件为 true 时。</span><span class="sxs-lookup"><span data-stu-id="4411f-117">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="4411f-118">DOM</span><span class="sxs-lookup"><span data-stu-id="4411f-118">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="4411f-119">在更改或删除特定 DOM 节点或子节点的代码上。</span><span class="sxs-lookup"><span data-stu-id="4411f-119">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="4411f-120">XHR</span><span class="sxs-lookup"><span data-stu-id="4411f-120">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="4411f-121">XHR URL 包含字符串模式时。</span><span class="sxs-lookup"><span data-stu-id="4411f-121">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="4411f-122">事件侦听器</span><span class="sxs-lookup"><span data-stu-id="4411f-122">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="4411f-123">在发生事件后运行的代码上，例如 `click`，运行。</span><span class="sxs-lookup"><span data-stu-id="4411f-123">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="4411f-124">异常</span><span class="sxs-lookup"><span data-stu-id="4411f-124">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="4411f-125">在引发已捕获或未捕获异常的代码行上。</span><span class="sxs-lookup"><span data-stu-id="4411f-125">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="4411f-126">函数</span><span class="sxs-lookup"><span data-stu-id="4411f-126">Function</span></span>](#function-breakpoints) | <span data-ttu-id="4411f-127">每当运行特定的命令、函数或方法时。</span><span class="sxs-lookup"><span data-stu-id="4411f-127">Whenever a specific command, function, or method is run.</span></span>  |  

## <a name="line-of-code-breakpoints"></a><span data-ttu-id="4411f-128">代码行断点</span><span class="sxs-lookup"><span data-stu-id="4411f-128">Line-of-code breakpoints</span></span>  

<span data-ttu-id="4411f-129">知道需要调查的确切代码区域时，使用代码行断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-129">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="4411f-130">开发工具始终在运行此代码行之前暂停。</span><span class="sxs-lookup"><span data-stu-id="4411f-130">DevTools always pauses before this line of code is run.</span></span>  

<span data-ttu-id="4411f-131">在开发工具中设置代码行断点：</span><span class="sxs-lookup"><span data-stu-id="4411f-131">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="4411f-132">选择“**源**”工具。</span><span class="sxs-lookup"><span data-stu-id="4411f-132">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="4411f-133">打开包含要中断的代码行的文件。</span><span class="sxs-lookup"><span data-stu-id="4411f-133">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="4411f-134">转到代码行。</span><span class="sxs-lookup"><span data-stu-id="4411f-134">Go the line of code.</span></span>  
1.  <span data-ttu-id="4411f-135">代码行的左侧是行号列。</span><span class="sxs-lookup"><span data-stu-id="4411f-135">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="4411f-136">选择。</span><span class="sxs-lookup"><span data-stu-id="4411f-136">Choose it.</span></span>  <span data-ttu-id="4411f-137">行号列旁边出现红色图标。</span><span class="sxs-lookup"><span data-stu-id="4411f-137">A red icon appears next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="4411f-139">代码行断点</span><span class="sxs-lookup"><span data-stu-id="4411f-139">A line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <a name="line-of-code-breakpoints-in-your-code"></a><span data-ttu-id="4411f-140">代码中的代码行断点</span><span class="sxs-lookup"><span data-stu-id="4411f-140">Line-of-code breakpoints in your code</span></span>  

<span data-ttu-id="4411f-141">从代码运行 `debugger` 方法，以暂停在此行。</span><span class="sxs-lookup"><span data-stu-id="4411f-141">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="4411f-142">这与[代码行断点](#line-of-code-breakpoints)等效，只是断点在代码中设置，而不是在开发工具 UI 中设置的。</span><span class="sxs-lookup"><span data-stu-id="4411f-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <a name="conditional-line-of-code-breakpoints"></a><span data-ttu-id="4411f-143">条件代码行断点</span><span class="sxs-lookup"><span data-stu-id="4411f-143">Conditional line-of-code breakpoints</span></span>  

<span data-ttu-id="4411f-144">如果知道需要调查的确切代码区域时，但仅在某些其他条件为 true 时才想暂停，请使用条件代码行断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="4411f-145">设置条件代码行断点：</span><span class="sxs-lookup"><span data-stu-id="4411f-145">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="4411f-146">选择“**源**”工具。</span><span class="sxs-lookup"><span data-stu-id="4411f-146">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="4411f-147">打开包含要中断的代码行的文件。</span><span class="sxs-lookup"><span data-stu-id="4411f-147">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="4411f-148">转到代码行。</span><span class="sxs-lookup"><span data-stu-id="4411f-148">Go the line of code.</span></span>  
1.  <span data-ttu-id="4411f-149">代码行的左侧是行号列。</span><span class="sxs-lookup"><span data-stu-id="4411f-149">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="4411f-150">将鼠标悬停在行号上，打开上下文菜单 \(右键单击\)。</span><span class="sxs-lookup"><span data-stu-id="4411f-150">Hover on the line number and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="4411f-151">选择“**添加条件断点**”。</span><span class="sxs-lookup"><span data-stu-id="4411f-151">Choose **Add conditional breakpoint**.</span></span>  <span data-ttu-id="4411f-152">代码行下方将显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="4411f-152">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="4411f-153">在对话框中输入条件。</span><span class="sxs-lookup"><span data-stu-id="4411f-153">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="4411f-154">选择 `Enter` 以激活断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-154">Select `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="4411f-155">行号列旁边的图标。</span><span class="sxs-lookup"><span data-stu-id="4411f-155">An icon next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件代码行断点" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       <span data-ttu-id="4411f-157">条件代码行断点</span><span class="sxs-lookup"><span data-stu-id="4411f-157">A conditional line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <a name="manage-line-of-code-breakpoints"></a><span data-ttu-id="4411f-158">管理代码行断点</span><span class="sxs-lookup"><span data-stu-id="4411f-158">Manage line-of-code breakpoints</span></span>  

<span data-ttu-id="4411f-159">使用“**断点**”窗格可禁用或删除单个位置中的代码行断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-159">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="断点窗格" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   <span data-ttu-id="4411f-161">**断点**窗格</span><span class="sxs-lookup"><span data-stu-id="4411f-161">The **Breakpoints** panel</span></span>  
:::image-end:::  

*   <span data-ttu-id="4411f-162">选中条目旁边的复选框以禁用该断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-162">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="4411f-163">将鼠标悬停在某个项上并打开上下文菜单 \(右键单击\) 删除该断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-163">Hover on an entry and open the contextual menu \(right-click\) to remove that breakpoint.</span></span>  
*   <span data-ttu-id="4411f-164">将鼠标悬停在“**断点**”窗格中的任意位置，然后打开上下文菜单 \(右键单击\) 以停用所有断点、禁用所有断点或删除所有断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-164">Hover anywhere in the **Breakpoints** pane and open the contextual menu \(right-click\) to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="4411f-165">禁用所有断点等效于取消选中每个断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-165">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="4411f-166">取消激活所有断点将指示开发工具忽略所有代码行断点，但也要保持启用状态，以使每个断点都与重新激活每个断点时的状态相同。</span><span class="sxs-lookup"><span data-stu-id="4411f-166">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="“断点”窗格中的已停用断点" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       <span data-ttu-id="4411f-168">“**断点**”窗格中的已停用断点</span><span class="sxs-lookup"><span data-stu-id="4411f-168">Deactivated breakpoints in the **Breakpoints** pane</span></span>  
    :::image-end:::  
    
## <a name="dom-change-breakpoints"></a><span data-ttu-id="4411f-169">DOM 更改断点</span><span class="sxs-lookup"><span data-stu-id="4411f-169">DOM change breakpoints</span></span>  

<span data-ttu-id="4411f-170">想要暂停更改 DOM 节点或子级的代码时，请使用 DOM 更改断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-170">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="4411f-171">设置 DOM 更改断点类型：</span><span class="sxs-lookup"><span data-stu-id="4411f-171">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="4411f-172">选择“**元素**”工具。</span><span class="sxs-lookup"><span data-stu-id="4411f-172">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="4411f-173">转到要设置断点的元素。</span><span class="sxs-lookup"><span data-stu-id="4411f-173">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="4411f-174">将鼠标悬停在元素上并打开上下文菜单 \(右键单击\)。</span><span class="sxs-lookup"><span data-stu-id="4411f-174">Hover on the element and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="4411f-175">将鼠标悬停在“**中断**”上，然后选择“**子树修改**”，“**属性修改**”或“**节点删除**”。</span><span class="sxs-lookup"><span data-stu-id="4411f-175">Hover on **Break on**, then choose **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="用于创建 DOM 更改断点的上下文菜单" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       <span data-ttu-id="4411f-177">用于创建 DOM 更改断点的上下文菜单</span><span class="sxs-lookup"><span data-stu-id="4411f-177">The context menu for creating a DOM change breakpoint</span></span>  
    :::image-end:::  
    
### <a name="types-of-dom-change-breakpoints"></a><span data-ttu-id="4411f-178">DOM 更改断点类型</span><span class="sxs-lookup"><span data-stu-id="4411f-178">Types of DOM change breakpoints</span></span>  

*   <span data-ttu-id="4411f-179">**子树修改**。</span><span class="sxs-lookup"><span data-stu-id="4411f-179">**Subtree modifications**.</span></span>  <span data-ttu-id="4411f-180">删除或添加当前选定的节点的子节点，或者更改子节点的内容时触发。</span><span class="sxs-lookup"><span data-stu-id="4411f-180">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="4411f-181">子节点属性更改时，或对当前选定的节点进行任何更改时不触发。</span><span class="sxs-lookup"><span data-stu-id="4411f-181">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  
*   <span data-ttu-id="4411f-182">**属性修改**：在当前选定的节点上添加或删除属性时触发，或当属性值更改时触发。</span><span class="sxs-lookup"><span data-stu-id="4411f-182">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  
*   <span data-ttu-id="4411f-183">**节点删除**：删除当前选定的节点时触发。</span><span class="sxs-lookup"><span data-stu-id="4411f-183">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  
    
## <a name="xhrfetch-breakpoints"></a><span data-ttu-id="4411f-184">XHR/Fetch 断点</span><span class="sxs-lookup"><span data-stu-id="4411f-184">XHR/Fetch breakpoints</span></span>  

<span data-ttu-id="4411f-185">当 XHR 的请求 URL 包含指定字符串时，若要中断，请使用 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-185">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="4411f-186">开发工具将在 XHR 运行 `send()` 方法的代码行上暂停。</span><span class="sxs-lookup"><span data-stu-id="4411f-186">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="4411f-187">此功能还适用于 [Fetch API][MDNFetchApi] 请求。</span><span class="sxs-lookup"><span data-stu-id="4411f-187">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="4411f-188">例如，当网页请求 URL 不正确，并且希望快速找到导致错误请求的 AJAX 或 Fetch 源代码时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="4411f-188">One example of when this is helpful is when your webpage is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="4411f-189">设置 XHR 断点：</span><span class="sxs-lookup"><span data-stu-id="4411f-189">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="4411f-190">选择“**源**”工具。</span><span class="sxs-lookup"><span data-stu-id="4411f-190">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="4411f-191">展开“**XHR 断点**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4411f-191">Expand the **XHR Breakpoints** panel.</span></span>  
1.  <span data-ttu-id="4411f-192">选择“**添加断点**”。</span><span class="sxs-lookup"><span data-stu-id="4411f-192">Choose **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="4411f-193">输入要中断的字符串。</span><span class="sxs-lookup"><span data-stu-id="4411f-193">Enter the string which you want to break on.</span></span>  <span data-ttu-id="4411f-194">当此字符串存在于 XHR 请求 URL 中的任何位置时，开发工具将暂停。</span><span class="sxs-lookup"><span data-stu-id="4411f-194">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="4411f-195">选择 `Enter` 以确认。</span><span class="sxs-lookup"><span data-stu-id="4411f-195">Select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="创建 XHR 断点" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       <span data-ttu-id="4411f-197">创建 XHR 断点</span><span class="sxs-lookup"><span data-stu-id="4411f-197">Create an XHR breakpoint</span></span>  
    :::image-end:::  
    
## <a name="event-listener-breakpoints"></a><span data-ttu-id="4411f-198">事件侦听器断点</span><span class="sxs-lookup"><span data-stu-id="4411f-198">Event listener breakpoints</span></span>  

<span data-ttu-id="4411f-199">如果想在事件触发后运行的事件侦听器代码上暂停时，请使用事件侦听器断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-199">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="4411f-200">可以选择特定事件，如 `click`，或事件类别，如所有鼠标事件。</span><span class="sxs-lookup"><span data-stu-id="4411f-200">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="4411f-201">选择“**源**”工具。</span><span class="sxs-lookup"><span data-stu-id="4411f-201">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="4411f-202">展开“**事件侦听器断点**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4411f-202">Expand the **Event Listener Breakpoints** panel.</span></span>  <span data-ttu-id="4411f-203">开发工具显示事件类别的列表，如 **动画**。</span><span class="sxs-lookup"><span data-stu-id="4411f-203">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="4411f-204">检查这些类别之一可在触发该类别的任何事件时暂停，或展开该类别并检查特定事件。</span><span class="sxs-lookup"><span data-stu-id="4411f-204">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="创建事件侦听器断点" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       <span data-ttu-id="4411f-206">创建事件侦听器断点</span><span class="sxs-lookup"><span data-stu-id="4411f-206">Create an event listener breakpoint</span></span>  
    :::image-end:::  
    
## <a name="exception-breakpoints"></a><span data-ttu-id="4411f-207">异常断</span><span class="sxs-lookup"><span data-stu-id="4411f-207">Exception breakpoints</span></span>  

<span data-ttu-id="4411f-208">想要暂停引发已捕获或未捕获异常的代码行时，请使用异常断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-208">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="4411f-209">选择“**源**”工具。</span><span class="sxs-lookup"><span data-stu-id="4411f-209">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="4411f-210">选择“**因异常暂停**” \(![ 因异常暂停 ](../media/pause-on-exceptions-icon.msft.png) \)。</span><span class="sxs-lookup"><span data-stu-id="4411f-210">Choose **Pause on exceptions** \(![Pause on exceptions](../media/pause-on-exceptions-icon.msft.png)\).</span></span>  <span data-ttu-id="4411f-211">图标在启用时变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="4411f-211">The icon turns blue when enabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="“因异常暂停”按钮" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       <span data-ttu-id="4411f-213">“**因异常暂停**”按钮</span><span class="sxs-lookup"><span data-stu-id="4411f-213">The **Pause on exceptions** button</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4411f-214">**可选**。</span><span class="sxs-lookup"><span data-stu-id="4411f-214">**Optional**.</span></span>  <span data-ttu-id="4411f-215">如果还想捕获异常时暂停，请选中“**捕获异常时暂停**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4411f-215">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="因未捕获异常暂停" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       <span data-ttu-id="4411f-217">因未捕获异常暂停</span><span class="sxs-lookup"><span data-stu-id="4411f-217">Paused on an uncaught exception</span></span>  
    :::image-end:::  
    
## <a name="function-breakpoints"></a><span data-ttu-id="4411f-218">函数断点</span><span class="sxs-lookup"><span data-stu-id="4411f-218">Function breakpoints</span></span>  

<span data-ttu-id="4411f-219">如果要在运行特定功能时暂停，请运行 `debug(method)` 方法，其中 `method` 是要调试的命令、函数或方法。</span><span class="sxs-lookup"><span data-stu-id="4411f-219">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="4411f-220">可以在代码中插入 `debug()`（如`console.log()`语句）或从开发工具控制台运行方法。</span><span class="sxs-lookup"><span data-stu-id="4411f-220">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="4411f-221">等效于在函数第一行上“[代码行断点](#line-of-code-breakpoints)”设置。</span><span class="sxs-lookup"><span data-stu-id="4411f-221">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <a name="make-sure-the-target-function-is-in-scope"></a><span data-ttu-id="4411f-222">确保目标函数在作用域内</span><span class="sxs-lookup"><span data-stu-id="4411f-222">Make sure the target function is in scope</span></span>  

<span data-ttu-id="4411f-223">如果要调试的函数不在作用域内，开发工具将引发 `ReferenceError`。</span><span class="sxs-lookup"><span data-stu-id="4411f-223">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

```javascript
(function () {
    function hey() {
        console.log('hey');
    }
    function yo() {
        console.log('yo');
    }
    debug(yo); // This works.
    yo();
})();
debug(hey); // This does not work.  hey() is out of scope.
```  

<span data-ttu-id="4411f-224">如果要从开发工具控制台运行 `debug()` 方法，确保目标函数位于作用域内则比较困难。</span><span class="sxs-lookup"><span data-stu-id="4411f-224">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="4411f-225">下面是一个策略：</span><span class="sxs-lookup"><span data-stu-id="4411f-225">Here is one strategy:</span></span>  

1.  <span data-ttu-id="4411f-226">在函数作用域内的某个位置设置[代码行断点](#line-of-code-breakpoints)。</span><span class="sxs-lookup"><span data-stu-id="4411f-226">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="4411f-227">触发断点。</span><span class="sxs-lookup"><span data-stu-id="4411f-227">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="4411f-228">代码仍在代码行断点处暂停时，在开发工具控制台中运行 `debug()` 方法。</span><span class="sxs-lookup"><span data-stu-id="4411f-228">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  
    
## <a name="related-articles"></a><span data-ttu-id="4411f-229">相关文章</span><span class="sxs-lookup"><span data-stu-id="4411f-229">Related articles</span></span>

*   <span data-ttu-id="4411f-230">[使用调试器功能][DevtoolsJavascriptReference] - 使用"源"工具 **中的调试器** UI。</span><span class="sxs-lookup"><span data-stu-id="4411f-230">[Use the debugger features][DevtoolsJavascriptReference] - Using the UI of the debugger in the **Sources** tool.</span></span>
*   <span data-ttu-id="4411f-231">[在 DevTools][DevtoolsJavascriptIndex] Microsoft Edge JavaScript 入门 - 使用现有网页的介绍性教程。</span><span class="sxs-lookup"><span data-stu-id="4411f-231">[Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex] - An introductory tutorial using an existing webpage.</span></span>
*   <span data-ttu-id="4411f-232">[源工具概述][DevtoolsSourcesIndex]- 调试器是源工具\*\*\*\* 的一部分，其中包括 JavaScript 编辑器。</span><span class="sxs-lookup"><span data-stu-id="4411f-232">[Sources tool overview][DevtoolsSourcesIndex] - The debugger is part of the **Sources** tool, which includes a JavaScript editor.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4411f-233">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="4411f-233">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsJavascriptReference]: ./reference.md "使用调试器功能|Microsoft Docs"  

[DevtoolsJavascriptIndex]: index.md "在 Microsoft Edge 开发工具中调试 JavaScript 入门 | Microsoft Docs"  

[DevtoolsSourcesIndex]: ../sources/index.md "源工具概述 | Microsoft Docs"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "Fetch API | MDN"  

> [!NOTE]
> <span data-ttu-id="4411f-238">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="4411f-238">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4411f-239">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="4411f-239">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="4411f-241">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="4411f-241">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
