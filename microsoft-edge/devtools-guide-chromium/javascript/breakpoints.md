---
description: 了解你可以在 Microsoft Edge DevTools 中暂停代码的所有方式。
title: 如何在 Microsoft Edge DevTools 中暂停带有断点的代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 98c0e42657d9b0900d3eaca8af69f1c17abfcf06
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124808"
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

# <span data-ttu-id="f82ca-104">如何在 Microsoft Edge DevTools 中暂停带有断点的代码</span><span class="sxs-lookup"><span data-stu-id="f82ca-104">How to pause your code with breakpoints in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f82ca-105">使用断点暂停你的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="f82ca-105">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="f82ca-106">本指南介绍 DevTools 中可用的每种类型的断点以及何时使用以及如何设置每种类型。</span><span class="sxs-lookup"><span data-stu-id="f82ca-106">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span></span>  <span data-ttu-id="f82ca-107">有关调试过程的动手教程，请导航到 [Microsoft Edge DevTools 中的 "调试 JavaScript" 入门][DevtoolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="f82ca-107">For a hands-on tutorial of the debugging process, navigate to [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>  

## <span data-ttu-id="f82ca-108">有关何时使用每个断点类型的概述</span><span class="sxs-lookup"><span data-stu-id="f82ca-108">Overview of when to use each breakpoint type</span></span>  

<span data-ttu-id="f82ca-109">最著名的断点类型是代码行。</span><span class="sxs-lookup"><span data-stu-id="f82ca-109">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="f82ca-110">但是，设置代码行的断点可能效率较低，尤其是当你不知道确切的查找位置时，或者如果你使用的是大型代码库。</span><span class="sxs-lookup"><span data-stu-id="f82ca-110">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="f82ca-111">通过了解如何以及何时使用其他类型的断点，你可以在调试时节省时间。</span><span class="sxs-lookup"><span data-stu-id="f82ca-111">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="f82ca-112">断点类型</span><span class="sxs-lookup"><span data-stu-id="f82ca-112">Breakpoint Type</span></span> | <span data-ttu-id="f82ca-113">如果要暂停，请使用此操作 .。。</span><span class="sxs-lookup"><span data-stu-id="f82ca-113">Use This When You Want To Pause...</span></span>  |  
|:--- |:--- |  
| [<span data-ttu-id="f82ca-114">代码行</span><span class="sxs-lookup"><span data-stu-id="f82ca-114">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="f82ca-115">在确切的代码区域中。</span><span class="sxs-lookup"><span data-stu-id="f82ca-115">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="f82ca-116">条件代码行</span><span class="sxs-lookup"><span data-stu-id="f82ca-116">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="f82ca-117">在确切的代码区域中，但仅在某些其他条件为 true 时。</span><span class="sxs-lookup"><span data-stu-id="f82ca-117">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="f82ca-118">DOM</span><span class="sxs-lookup"><span data-stu-id="f82ca-118">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="f82ca-119">更改或删除特定的 DOM 节点或子级的代码。</span><span class="sxs-lookup"><span data-stu-id="f82ca-119">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="f82ca-120">XHR</span><span class="sxs-lookup"><span data-stu-id="f82ca-120">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="f82ca-121">当 XHR URL 包含字符串模式时。</span><span class="sxs-lookup"><span data-stu-id="f82ca-121">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="f82ca-122">事件侦听器</span><span class="sxs-lookup"><span data-stu-id="f82ca-122">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="f82ca-123">在事件（如）之后运行的代码上 `click` 运行。</span><span class="sxs-lookup"><span data-stu-id="f82ca-123">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="f82ca-124">异常</span><span class="sxs-lookup"><span data-stu-id="f82ca-124">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="f82ca-125">在引发已捕获或未捕获异常的代码行上。</span><span class="sxs-lookup"><span data-stu-id="f82ca-125">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="f82ca-126">函数</span><span class="sxs-lookup"><span data-stu-id="f82ca-126">Function</span></span>](#function-breakpoints) | <span data-ttu-id="f82ca-127">每当运行特定的命令、函数或方法时。</span><span class="sxs-lookup"><span data-stu-id="f82ca-127">Whenever a specific command, function, or method is run.</span></span>  |  

## <span data-ttu-id="f82ca-128">代码行断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-128">Line-of-code breakpoints</span></span>  

<span data-ttu-id="f82ca-129">当你知道需要调查的确切代码区域时，请使用代码行断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-129">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="f82ca-130">在运行此行代码之前，DevTools 始终暂停。</span><span class="sxs-lookup"><span data-stu-id="f82ca-130">DevTools always pauses before this line of code is run.</span></span>  

<span data-ttu-id="f82ca-131">在 DevTools 中设置代码行断点：</span><span class="sxs-lookup"><span data-stu-id="f82ca-131">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="f82ca-132">单击 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f82ca-132">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f82ca-133">打开包含要中断的代码行的文件。</span><span class="sxs-lookup"><span data-stu-id="f82ca-133">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="f82ca-134">转到代码行。</span><span class="sxs-lookup"><span data-stu-id="f82ca-134">Go the line of code.</span></span>  
1.  <span data-ttu-id="f82ca-135">代码行左侧是 "行号" 列。</span><span class="sxs-lookup"><span data-stu-id="f82ca-135">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="f82ca-136">单击它。</span><span class="sxs-lookup"><span data-stu-id="f82ca-136">Click on it.</span></span>  <span data-ttu-id="f82ca-137">"行号" 列旁边将显示一个红色图标。</span><span class="sxs-lookup"><span data-stu-id="f82ca-137">A red icon appears next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="f82ca-139">代码行断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-139">A line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f82ca-140">代码中的代码行断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-140">Line-of-code breakpoints in your code</span></span>  

<span data-ttu-id="f82ca-141">`debugger`从代码中运行该方法以在该行上暂停。</span><span class="sxs-lookup"><span data-stu-id="f82ca-141">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="f82ca-142">这等效于 [代码行断点](#line-of-code-breakpoints)，只不过断点是在代码中设置的，而不是在 DevTools UI 中设置的。</span><span class="sxs-lookup"><span data-stu-id="f82ca-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <span data-ttu-id="f82ca-143">条件代码行断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-143">Conditional line-of-code breakpoints</span></span>  

<span data-ttu-id="f82ca-144">当你知道需要调查的确切代码区域时，请使用条件代码行断点，但只希望在其他某些条件为 true 时暂停。</span><span class="sxs-lookup"><span data-stu-id="f82ca-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="f82ca-145">设置条件代码行断点：</span><span class="sxs-lookup"><span data-stu-id="f82ca-145">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="f82ca-146">单击 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f82ca-146">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f82ca-147">打开包含要中断的代码行的文件。</span><span class="sxs-lookup"><span data-stu-id="f82ca-147">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="f82ca-148">转到代码行。</span><span class="sxs-lookup"><span data-stu-id="f82ca-148">Go the line of code.</span></span>  
1.  <span data-ttu-id="f82ca-149">代码行左侧是 "行号" 列。</span><span class="sxs-lookup"><span data-stu-id="f82ca-149">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="f82ca-150">右键单击行号。</span><span class="sxs-lookup"><span data-stu-id="f82ca-150">Right-click the line number.</span></span>  
1.  <span data-ttu-id="f82ca-151">选择 " **添加条件断点**"。</span><span class="sxs-lookup"><span data-stu-id="f82ca-151">Choose **Add conditional breakpoint**.</span></span>  <span data-ttu-id="f82ca-152">将在代码行下方显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="f82ca-152">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="f82ca-153">在对话框中输入条件。</span><span class="sxs-lookup"><span data-stu-id="f82ca-153">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="f82ca-154">选择 `Enter` 以激活断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-154">Select `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="f82ca-155">"行号" 列旁边的图标。</span><span class="sxs-lookup"><span data-stu-id="f82ca-155">An icon next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       <span data-ttu-id="f82ca-157">条件代码行断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-157">A conditional line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f82ca-158">管理代码行断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-158">Manage line-of-code breakpoints</span></span>  

<span data-ttu-id="f82ca-159">使用 " **断点** " 窗格从单个位置禁用或删除代码行断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-159">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   <span data-ttu-id="f82ca-161">" **断点** " 面板</span><span class="sxs-lookup"><span data-stu-id="f82ca-161">The **Breakpoints** panel</span></span>  
:::image-end:::  

*   <span data-ttu-id="f82ca-162">选中某个条目旁边的复选框以禁用该断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-162">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="f82ca-163">右键单击某个条目以删除该断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-163">Right-click an entry to remove that breakpoint.</span></span>  
*   <span data-ttu-id="f82ca-164">右键单击 " **断点** " 窗格中的任意位置可停用所有断点、禁用所有断点或删除所有断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-164">Right-click anywhere in the **Breakpoints** pane to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="f82ca-165">禁用所有断点相当于取消选中每一个断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-165">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="f82ca-166">停用所有断点指示 DevTools 忽略所有代码行断点，但同时保持已启用状态，以便每个断点在重新激活时保持相同的状态。</span><span class="sxs-lookup"><span data-stu-id="f82ca-166">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       <span data-ttu-id="f82ca-168">" **断点** " 窗格中已停用的断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-168">Deactivated breakpoints in the **Breakpoints** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f82ca-169">DOM 更改断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-169">DOM change breakpoints</span></span>  

<span data-ttu-id="f82ca-170">如果要在更改了 DOM 节点或子级的代码上暂停，请使用 DOM 更改断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-170">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="f82ca-171">设置 DOM 更改断点：</span><span class="sxs-lookup"><span data-stu-id="f82ca-171">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="f82ca-172">单击 " **元素** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f82ca-172">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="f82ca-173">转到要在其上设置断点的元素。</span><span class="sxs-lookup"><span data-stu-id="f82ca-173">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="f82ca-174">右键单击该元素。</span><span class="sxs-lookup"><span data-stu-id="f82ca-174">Right-click the element.</span></span>  
1.  <span data-ttu-id="f82ca-175">将鼠标 **悬停在 "断开" 上**，然后选择 " **子树修改**、 **属性修改**或 **节点删除**"。</span><span class="sxs-lookup"><span data-stu-id="f82ca-175">Hover over **Break on**, then choose **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="代码行断点" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       <span data-ttu-id="f82ca-177">用于创建 DOM 更改断点的上下文菜单</span><span class="sxs-lookup"><span data-stu-id="f82ca-177">The context menu for creating a DOM change breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f82ca-178">DOM 的类型更改断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-178">Types of DOM change breakpoints</span></span>  

*   <span data-ttu-id="f82ca-179">**子树修改**。</span><span class="sxs-lookup"><span data-stu-id="f82ca-179">**Subtree modifications**.</span></span>  <span data-ttu-id="f82ca-180">当删除或添加当前选定节点的子节点时，或者子元素的内容发生更改时触发。</span><span class="sxs-lookup"><span data-stu-id="f82ca-180">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="f82ca-181">不会在子节点属性更改或对当前选定节点的任何更改上触发。</span><span class="sxs-lookup"><span data-stu-id="f82ca-181">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  
*   <span data-ttu-id="f82ca-182">**属性修改**：当在当前选定的节点上添加或删除属性时，或者当属性值发生更改时触发。</span><span class="sxs-lookup"><span data-stu-id="f82ca-182">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  
*   <span data-ttu-id="f82ca-183">**节点删除**：在删除当前选定的节点时触发。</span><span class="sxs-lookup"><span data-stu-id="f82ca-183">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  
    
## <span data-ttu-id="f82ca-184">XHR/Fetch 断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-184">XHR/Fetch breakpoints</span></span>  

<span data-ttu-id="f82ca-185">如果你希望在 XHR 的请求 URL 包含指定的字符串时中断，请使用 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-185">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="f82ca-186">DevTools 将在 XHR 运行该方法的代码行上暂停 `send()` 。</span><span class="sxs-lookup"><span data-stu-id="f82ca-186">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="f82ca-187">此功能还适用于 [获取 API][MDNFetchApi] 请求。</span><span class="sxs-lookup"><span data-stu-id="f82ca-187">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="f82ca-188">这样做很有用的一个示例是，当你看到你的页面请求不正确的 URL 时，你希望快速找到导致错误请求的 AJAX 或提取源代码。</span><span class="sxs-lookup"><span data-stu-id="f82ca-188">One example of when this is helpful is when you see that your page is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="f82ca-189">设置 XHR 断点：</span><span class="sxs-lookup"><span data-stu-id="f82ca-189">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="f82ca-190">单击 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f82ca-190">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f82ca-191">展开 " **XHR 断点** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="f82ca-191">Expand the **XHR Breakpoints** pane.</span></span>  
1.  <span data-ttu-id="f82ca-192">选择 " **添加断点**"。</span><span class="sxs-lookup"><span data-stu-id="f82ca-192">Choose **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="f82ca-193">输入要在其上中断的字符串。</span><span class="sxs-lookup"><span data-stu-id="f82ca-193">Enter the string which you want to break on.</span></span>  <span data-ttu-id="f82ca-194">当此字符串出现在 XHR 请求 URL 中的任何位置时，DevTools 暂停。</span><span class="sxs-lookup"><span data-stu-id="f82ca-194">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="f82ca-195">选择 `Enter` 以进行确认。</span><span class="sxs-lookup"><span data-stu-id="f82ca-195">Select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       <span data-ttu-id="f82ca-197">创建 XHR 断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-197">Create an XHR breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f82ca-198">事件侦听器断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-198">Event listener breakpoints</span></span>   

<span data-ttu-id="f82ca-199">如果要在激发事件后运行的事件侦听器代码上暂停，请使用事件侦听器断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-199">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="f82ca-200">你可以选择特定事件，例如事件的类别，如 `click` 所有鼠标事件。</span><span class="sxs-lookup"><span data-stu-id="f82ca-200">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="f82ca-201">单击 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f82ca-201">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f82ca-202">展开 " **事件侦听器断点** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="f82ca-202">Expand the **Event Listener Breakpoints** pane.</span></span>  <span data-ttu-id="f82ca-203">DevTools 显示事件类别的列表，例如 **动画**。</span><span class="sxs-lookup"><span data-stu-id="f82ca-203">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="f82ca-204">选中其中一个类别，以便在触发来自该类别的任何事件时暂停，或者展开类别并检查特定事件。</span><span class="sxs-lookup"><span data-stu-id="f82ca-204">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       <span data-ttu-id="f82ca-206">创建事件侦听器断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-206">Create an event listener breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f82ca-207">异常断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-207">Exception breakpoints</span></span>  

<span data-ttu-id="f82ca-208">当你希望在引发已捕获或未捕获异常的代码行上暂停时，请使用异常断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-208">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="f82ca-209">单击 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f82ca-209">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f82ca-210">选择 **"异常时暂停"** (![ "异常时暂停" ][ImagePauseOnExceptionsIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f82ca-210">Choose **Pause on exceptions** \(![Pause on exceptions][ImagePauseOnExceptionsIcon]\).</span></span>  <span data-ttu-id="f82ca-211">启用时图标变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="f82ca-211">The icon turns blue when enabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       <span data-ttu-id="f82ca-213">" **在例外时暂停"** 按钮</span><span class="sxs-lookup"><span data-stu-id="f82ca-213">The **Pause on exceptions** button</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f82ca-214">**可选**。</span><span class="sxs-lookup"><span data-stu-id="f82ca-214">**Optional**.</span></span>  <span data-ttu-id="f82ca-215">如果你还希望在捕获异常时（除了未捕获的异常）上暂停，请选中 " **捕获异常时暂停** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="f82ca-215">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       <span data-ttu-id="f82ca-217">已暂停未捕获的异常</span><span class="sxs-lookup"><span data-stu-id="f82ca-217">Paused on an uncaught exception</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f82ca-218">函数断点</span><span class="sxs-lookup"><span data-stu-id="f82ca-218">Function breakpoints</span></span>  

<span data-ttu-id="f82ca-219">`debug(method)`如果要在运行特定函数时暂停，请运行该方法，其中 `method` 是要调试的命令、函数或方法。</span><span class="sxs-lookup"><span data-stu-id="f82ca-219">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="f82ca-220">你可以在 `debug()` 代码中插入 (，如 `console.log()` 语句) 或从 DevTools 控制台运行该方法。</span><span class="sxs-lookup"><span data-stu-id="f82ca-220">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="f82ca-221">等效于在函数的第一行上设置 [代码行断点](#line-of-code-breakpoints) 。</span><span class="sxs-lookup"><span data-stu-id="f82ca-221">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <span data-ttu-id="f82ca-222">请确保目标函数在范围内</span><span class="sxs-lookup"><span data-stu-id="f82ca-222">Make sure the target function is in scope</span></span>  

<span data-ttu-id="f82ca-223">`ReferenceError`如果要调试的函数不在作用域内，DevTools 会引发 a。</span><span class="sxs-lookup"><span data-stu-id="f82ca-223">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

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

<span data-ttu-id="f82ca-224">如果从 DevTools 控制台运行该方法，确保目标函数在范围内非常复杂 `debug()` 。</span><span class="sxs-lookup"><span data-stu-id="f82ca-224">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="f82ca-225">下面是一个策略：</span><span class="sxs-lookup"><span data-stu-id="f82ca-225">Here is one strategy:</span></span>  

1.  <span data-ttu-id="f82ca-226">在函数在范围中的某个位置设置 [代码行断点](#line-of-code-breakpoints) 。</span><span class="sxs-lookup"><span data-stu-id="f82ca-226">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="f82ca-227">触发断点。</span><span class="sxs-lookup"><span data-stu-id="f82ca-227">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="f82ca-228">`debug()`在 DevTools 控制台中运行该方法，同时代码在代码行断点处仍处于暂停状态。</span><span class="sxs-lookup"><span data-stu-id="f82ca-228">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  
    
## <span data-ttu-id="f82ca-229">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="f82ca-229">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "开始使用 Microsoft Edge DevTools 中的 JavaScript 调试 |Microsoft 文档"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "获取 API |MDN"  

> [!NOTE]
> <span data-ttu-id="f82ca-232">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f82ca-232">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f82ca-233">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f82ca-233">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f82ca-235">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f82ca-235">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
