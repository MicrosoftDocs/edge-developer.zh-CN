---
description: 了解在 Microsoft Edge DevTools 中暂停代码的所有方法。
title: 如何使用 Microsoft Edge DevTools 中的断点暂停代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 3d50b7b105aa9a9018ba61e44147f46f3d340079
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439512"
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

# <a name="how-to-pause-your-code-with-breakpoints-in-microsoft-edge-devtools"></a><span data-ttu-id="85809-104">如何使用 Microsoft Edge DevTools 中的断点暂停代码</span><span class="sxs-lookup"><span data-stu-id="85809-104">How to pause your code with breakpoints in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="85809-105">使用断点暂停 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="85809-105">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="85809-106">本指南介绍了 DevTools 中提供的每种断点类型，以及何时使用以及如何设置每种类型。</span><span class="sxs-lookup"><span data-stu-id="85809-106">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span></span>  <span data-ttu-id="85809-107">有关调试过程的实践教程，请导航到开始在 Microsoft [Edge DevTools][DevtoolsJavascriptIndex]中调试 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="85809-107">For a hands-on tutorial of the debugging process, navigate to [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>  

## <a name="overview-of-when-to-use-each-breakpoint-type"></a><span data-ttu-id="85809-108">何时使用每种断点类型的概述</span><span class="sxs-lookup"><span data-stu-id="85809-108">Overview of when to use each breakpoint type</span></span>  

<span data-ttu-id="85809-109">最已知的断点类型是代码行。</span><span class="sxs-lookup"><span data-stu-id="85809-109">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="85809-110">但代码行断点设置效率可能较低，尤其是在您不知道具体查找位置，或者您正使用大型代码库时。</span><span class="sxs-lookup"><span data-stu-id="85809-110">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="85809-111">通过了解如何以及何时使用其他类型的断点，在调试时可以节省自己的时间。</span><span class="sxs-lookup"><span data-stu-id="85809-111">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="85809-112">断点类型</span><span class="sxs-lookup"><span data-stu-id="85809-112">Breakpoint Type</span></span> | <span data-ttu-id="85809-113">在想要暂停时使用此...</span><span class="sxs-lookup"><span data-stu-id="85809-113">Use This When You Want To Pause...</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="85809-114">代码行</span><span class="sxs-lookup"><span data-stu-id="85809-114">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="85809-115">在代码的准确区域上。</span><span class="sxs-lookup"><span data-stu-id="85809-115">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="85809-116">条件代码行</span><span class="sxs-lookup"><span data-stu-id="85809-116">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="85809-117">在代码的准确区域上，但仅在某些其他条件为 true 时。</span><span class="sxs-lookup"><span data-stu-id="85809-117">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="85809-118">DOM</span><span class="sxs-lookup"><span data-stu-id="85809-118">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="85809-119">在更改或删除特定 DOM 节点或子节点的代码上。</span><span class="sxs-lookup"><span data-stu-id="85809-119">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="85809-120">XHR</span><span class="sxs-lookup"><span data-stu-id="85809-120">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="85809-121">当 XHR URL 包含字符串模式时。</span><span class="sxs-lookup"><span data-stu-id="85809-121">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="85809-122">事件侦听器</span><span class="sxs-lookup"><span data-stu-id="85809-122">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="85809-123">在运行事件（如 ）之后运行 `click` 的代码上运行。</span><span class="sxs-lookup"><span data-stu-id="85809-123">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="85809-124">异常</span><span class="sxs-lookup"><span data-stu-id="85809-124">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="85809-125">在引发捕获或不捕获异常的代码行上。</span><span class="sxs-lookup"><span data-stu-id="85809-125">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="85809-126">函数</span><span class="sxs-lookup"><span data-stu-id="85809-126">Function</span></span>](#function-breakpoints) | <span data-ttu-id="85809-127">每当运行特定命令、函数或方法时。</span><span class="sxs-lookup"><span data-stu-id="85809-127">Whenever a specific command, function, or method is run.</span></span>  |  

## <a name="line-of-code-breakpoints"></a><span data-ttu-id="85809-128">代码行断点</span><span class="sxs-lookup"><span data-stu-id="85809-128">Line-of-code breakpoints</span></span>  

<span data-ttu-id="85809-129">当您知道需要调查的代码的准确区域时，请使用代码行断点。</span><span class="sxs-lookup"><span data-stu-id="85809-129">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="85809-130">DevTools 始终在运行此代码行之前暂停。</span><span class="sxs-lookup"><span data-stu-id="85809-130">DevTools always pauses before this line of code is run.</span></span>  

<span data-ttu-id="85809-131">若要在 DevTools 中设置代码行断点：</span><span class="sxs-lookup"><span data-stu-id="85809-131">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="85809-132">选择" **源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="85809-132">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="85809-133">打开包含要中断的代码行的文件。</span><span class="sxs-lookup"><span data-stu-id="85809-133">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="85809-134">转到代码行。</span><span class="sxs-lookup"><span data-stu-id="85809-134">Go the line of code.</span></span>  
1.  <span data-ttu-id="85809-135">代码行左侧是行号列。</span><span class="sxs-lookup"><span data-stu-id="85809-135">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="85809-136">选择它。</span><span class="sxs-lookup"><span data-stu-id="85809-136">Choose it.</span></span>  <span data-ttu-id="85809-137">行号列旁边将显示一个红色图标。</span><span class="sxs-lookup"><span data-stu-id="85809-137">A red icon appears next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="85809-139">代码行断点</span><span class="sxs-lookup"><span data-stu-id="85809-139">A line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <a name="line-of-code-breakpoints-in-your-code"></a><span data-ttu-id="85809-140">代码中的代码行断点</span><span class="sxs-lookup"><span data-stu-id="85809-140">Line-of-code breakpoints in your code</span></span>  

<span data-ttu-id="85809-141">从 `debugger` 代码运行 方法以暂停该行。</span><span class="sxs-lookup"><span data-stu-id="85809-141">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="85809-142">这等效于代码 [行](#line-of-code-breakpoints)断点，只不过断点是在代码中设置的，而不是在 DevTools UI 中设置的。</span><span class="sxs-lookup"><span data-stu-id="85809-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <a name="conditional-line-of-code-breakpoints"></a><span data-ttu-id="85809-143">条件代码行断点</span><span class="sxs-lookup"><span data-stu-id="85809-143">Conditional line-of-code breakpoints</span></span>  

<span data-ttu-id="85809-144">如果您知道需要调查的代码的准确区域，但希望仅在满足其他某些条件时暂停，请使用条件的代码行断点。</span><span class="sxs-lookup"><span data-stu-id="85809-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="85809-145">设置条件代码行断点：</span><span class="sxs-lookup"><span data-stu-id="85809-145">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="85809-146">选择" **源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="85809-146">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="85809-147">打开包含要中断的代码行的文件。</span><span class="sxs-lookup"><span data-stu-id="85809-147">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="85809-148">转到代码行。</span><span class="sxs-lookup"><span data-stu-id="85809-148">Go the line of code.</span></span>  
1.  <span data-ttu-id="85809-149">代码行左侧是行号列。</span><span class="sxs-lookup"><span data-stu-id="85809-149">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="85809-150">将鼠标悬停在行号上，打开上下文菜单 \ (右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="85809-150">Hover on the line number and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="85809-151">选择 **"添加条件断点"。**</span><span class="sxs-lookup"><span data-stu-id="85809-151">Choose **Add conditional breakpoint**.</span></span>  <span data-ttu-id="85809-152">代码行下方将显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="85809-152">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="85809-153">在对话框中输入您的条件。</span><span class="sxs-lookup"><span data-stu-id="85809-153">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="85809-154">选择 `Enter` 以激活断点。</span><span class="sxs-lookup"><span data-stu-id="85809-154">Select `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="85809-155">行号列旁边的图标。</span><span class="sxs-lookup"><span data-stu-id="85809-155">An icon next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件代码行断点" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       <span data-ttu-id="85809-157">条件代码行断点</span><span class="sxs-lookup"><span data-stu-id="85809-157">A conditional line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <a name="manage-line-of-code-breakpoints"></a><span data-ttu-id="85809-158">管理代码行断点</span><span class="sxs-lookup"><span data-stu-id="85809-158">Manage line-of-code breakpoints</span></span>  

<span data-ttu-id="85809-159">使用 **"断点"** 窗格可禁用或删除单个位置中的代码行断点。</span><span class="sxs-lookup"><span data-stu-id="85809-159">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="断点面板" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   <span data-ttu-id="85809-161">断 **点** 面板</span><span class="sxs-lookup"><span data-stu-id="85809-161">The **Breakpoints** panel</span></span>  
:::image-end:::  

*   <span data-ttu-id="85809-162">选中某个条目旁边的复选框以禁用该断点。</span><span class="sxs-lookup"><span data-stu-id="85809-162">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="85809-163">将鼠标悬停在某个项上并打开上下文菜单 \ (右键单击\) 删除该断点。</span><span class="sxs-lookup"><span data-stu-id="85809-163">Hover on an entry and open the contextual menu \(right-click\) to remove that breakpoint.</span></span>  
*   <span data-ttu-id="85809-164">将鼠标悬停在"\*\*\*\* 断点"窗格中的任意位置，然后打开上下文菜单 \ (右键单击\) 以停用所有断点、禁用所有断点或删除所有断点。</span><span class="sxs-lookup"><span data-stu-id="85809-164">Hover anywhere in the **Breakpoints** pane and open the contextual menu \(right-click\) to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="85809-165">禁用所有断点等效于取消选中每个断点。</span><span class="sxs-lookup"><span data-stu-id="85809-165">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="85809-166">停用所有断点将指示 DevTools 忽略所有代码行断点，但还要保持启用状态，以便每个断点在重新激活每个断点时处于与之前相同的状态。</span><span class="sxs-lookup"><span data-stu-id="85809-166">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text=""断点"窗格中的已停用断点" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       <span data-ttu-id="85809-168">"断点"窗格中的**已停用断点**</span><span class="sxs-lookup"><span data-stu-id="85809-168">Deactivated breakpoints in the **Breakpoints** pane</span></span>  
    :::image-end:::  
    
## <a name="dom-change-breakpoints"></a><span data-ttu-id="85809-169">DOM 更改断点</span><span class="sxs-lookup"><span data-stu-id="85809-169">DOM change breakpoints</span></span>  

<span data-ttu-id="85809-170">当您想要暂停更改 DOM 节点或子级的代码时，请使用 DOM 更改断点。</span><span class="sxs-lookup"><span data-stu-id="85809-170">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="85809-171">若要设置 DOM 更改断点：</span><span class="sxs-lookup"><span data-stu-id="85809-171">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="85809-172">选择" **元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="85809-172">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="85809-173">转到要设置断点的元素。</span><span class="sxs-lookup"><span data-stu-id="85809-173">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="85809-174">将鼠标悬停在 元素上并打开上下文菜单 \ (右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="85809-174">Hover on the element and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="85809-175">Hover on **Break on**， then choose **Subtree modifications**， Attribute **modifications**， or **Node removal**.</span><span class="sxs-lookup"><span data-stu-id="85809-175">Hover on **Break on**, then choose **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="用于创建 DOM 更改断点的上下文菜单" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       <span data-ttu-id="85809-177">用于创建 DOM 更改断点的上下文菜单</span><span class="sxs-lookup"><span data-stu-id="85809-177">The context menu for creating a DOM change breakpoint</span></span>  
    :::image-end:::  
    
### <a name="types-of-dom-change-breakpoints"></a><span data-ttu-id="85809-178">DOM 更改断点的类型</span><span class="sxs-lookup"><span data-stu-id="85809-178">Types of DOM change breakpoints</span></span>  

*   <span data-ttu-id="85809-179">**子树修改**。</span><span class="sxs-lookup"><span data-stu-id="85809-179">**Subtree modifications**.</span></span>  <span data-ttu-id="85809-180">在删除或添加当前选定的节点的子节点，或者更改子节点的内容时触发。</span><span class="sxs-lookup"><span data-stu-id="85809-180">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="85809-181">在子节点属性更改时，或对当前选定的节点的任何更改时不触发。</span><span class="sxs-lookup"><span data-stu-id="85809-181">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  
*   <span data-ttu-id="85809-182">**属性修改**：在当前选定的节点上添加或删除属性时触发，或当属性值更改时触发。</span><span class="sxs-lookup"><span data-stu-id="85809-182">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  
*   <span data-ttu-id="85809-183">**节点删除**：在删除当前选定的节点时触发。</span><span class="sxs-lookup"><span data-stu-id="85809-183">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  
    
## <a name="xhrfetch-breakpoints"></a><span data-ttu-id="85809-184">XHR/Fetch 断点</span><span class="sxs-lookup"><span data-stu-id="85809-184">XHR/Fetch breakpoints</span></span>  

<span data-ttu-id="85809-185">当 XHR 的请求 URL 包含指定字符串时，若要中断，请使用 XHR 断点。</span><span class="sxs-lookup"><span data-stu-id="85809-185">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="85809-186">DevTools 将暂停 XHR 运行方法的代码 `send()` 行。</span><span class="sxs-lookup"><span data-stu-id="85809-186">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="85809-187">此功能还适用于提取 [API][MDNFetchApi] 请求。</span><span class="sxs-lookup"><span data-stu-id="85809-187">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="85809-188">例如，当您的网页请求的 URL 不正确，并且您希望快速找到导致错误请求的 AJAX 或 Fetch 源代码时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="85809-188">One example of when this is helpful is when your webpage is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="85809-189">设置 XHR 断点：</span><span class="sxs-lookup"><span data-stu-id="85809-189">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="85809-190">选择" **源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="85809-190">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="85809-191">展开 **"XHR 断点"** 面板。</span><span class="sxs-lookup"><span data-stu-id="85809-191">Expand the **XHR Breakpoints** panel.</span></span>  
1.  <span data-ttu-id="85809-192">选择 **"添加断点"。**</span><span class="sxs-lookup"><span data-stu-id="85809-192">Choose **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="85809-193">输入要中断的字符串。</span><span class="sxs-lookup"><span data-stu-id="85809-193">Enter the string which you want to break on.</span></span>  <span data-ttu-id="85809-194">当此字符串存在于 XHR 请求 URL 中的任何位置时，DevTools 将暂停。</span><span class="sxs-lookup"><span data-stu-id="85809-194">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="85809-195">选择 `Enter` 以确认。</span><span class="sxs-lookup"><span data-stu-id="85809-195">Select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="创建 XHR 断点" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       <span data-ttu-id="85809-197">创建 XHR 断点</span><span class="sxs-lookup"><span data-stu-id="85809-197">Create an XHR breakpoint</span></span>  
    :::image-end:::  
    
## <a name="event-listener-breakpoints"></a><span data-ttu-id="85809-198">事件侦听器断点</span><span class="sxs-lookup"><span data-stu-id="85809-198">Event listener breakpoints</span></span>  

<span data-ttu-id="85809-199">当你想要在触发事件后运行的事件侦听器代码上暂停时，请使用事件侦听器断点。</span><span class="sxs-lookup"><span data-stu-id="85809-199">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="85809-200">可以选择特定事件（如 ）或事件类别， `click` 如所有鼠标事件。</span><span class="sxs-lookup"><span data-stu-id="85809-200">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="85809-201">选择" **源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="85809-201">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="85809-202">展开" **事件侦听器断点"** 面板。</span><span class="sxs-lookup"><span data-stu-id="85809-202">Expand the **Event Listener Breakpoints** panel.</span></span>  <span data-ttu-id="85809-203">DevTools 显示事件类别的列表，如 **动画**。</span><span class="sxs-lookup"><span data-stu-id="85809-203">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="85809-204">检查其中一个类别以在触发该类别的任何事件时暂停，或者展开类别并检查特定事件。</span><span class="sxs-lookup"><span data-stu-id="85809-204">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="创建事件侦听器断点" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       <span data-ttu-id="85809-206">创建事件侦听器断点</span><span class="sxs-lookup"><span data-stu-id="85809-206">Create an event listener breakpoint</span></span>  
    :::image-end:::  
    
## <a name="exception-breakpoints"></a><span data-ttu-id="85809-207">异常断点</span><span class="sxs-lookup"><span data-stu-id="85809-207">Exception breakpoints</span></span>  

<span data-ttu-id="85809-208">当你想要暂停引发捕获或不捕获的异常的代码行时，请使用异常断点。</span><span class="sxs-lookup"><span data-stu-id="85809-208">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="85809-209">选择" **源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="85809-209">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="85809-210">Choose **Pause on exceptions** \ (![ Pause on exceptions ](../media/pause-on-exceptions-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="85809-210">Choose **Pause on exceptions** \(![Pause on exceptions](../media/pause-on-exceptions-icon.msft.png)\).</span></span>  <span data-ttu-id="85809-211">图标在启用时变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="85809-211">The icon turns blue when enabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text=""在异常时暂停"按钮" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       <span data-ttu-id="85809-213">" **在异常时暂停"** 按钮</span><span class="sxs-lookup"><span data-stu-id="85809-213">The **Pause on exceptions** button</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="85809-214">**可选**。</span><span class="sxs-lookup"><span data-stu-id="85809-214">**Optional**.</span></span>  <span data-ttu-id="85809-215">如果除了 **未** 捕获的异常之外，还想要在捕获的异常上暂停，请选中"暂停捕获的异常"复选框。</span><span class="sxs-lookup"><span data-stu-id="85809-215">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="在未记录异常上暂停" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       <span data-ttu-id="85809-217">在未记录异常上暂停</span><span class="sxs-lookup"><span data-stu-id="85809-217">Paused on an uncaught exception</span></span>  
    :::image-end:::  
    
## <a name="function-breakpoints"></a><span data-ttu-id="85809-218">函数断点</span><span class="sxs-lookup"><span data-stu-id="85809-218">Function breakpoints</span></span>  

<span data-ttu-id="85809-219">在想要在运行特定函数时暂停时运行 方法，其中 是你想要调试的命令、函数 `debug(method)` `method` 或方法。</span><span class="sxs-lookup"><span data-stu-id="85809-219">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="85809-220">你可以像 `debug()` 在开发人员控制台 (语句) 插入代码或运行 `console.log()` 方法。</span><span class="sxs-lookup"><span data-stu-id="85809-220">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="85809-221">等效于在函数 [的第一行](#line-of-code-breakpoints) 上设置代码行断点。</span><span class="sxs-lookup"><span data-stu-id="85809-221">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <a name="make-sure-the-target-function-is-in-scope"></a><span data-ttu-id="85809-222">确保目标函数在作用域内</span><span class="sxs-lookup"><span data-stu-id="85809-222">Make sure the target function is in scope</span></span>  

<span data-ttu-id="85809-223">如果你要调试的函数不在范围内，DevTools `ReferenceError` 将引发 。</span><span class="sxs-lookup"><span data-stu-id="85809-223">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

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

<span data-ttu-id="85809-224">如果你从 DevTools 控制台运行 方法，则确保目标函数在作用域 `debug()` 内比较复杂。</span><span class="sxs-lookup"><span data-stu-id="85809-224">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="85809-225">下面是一个策略：</span><span class="sxs-lookup"><span data-stu-id="85809-225">Here is one strategy:</span></span>  

1.  <span data-ttu-id="85809-226">在 [函数位于作用域中的](#line-of-code-breakpoints) 某位置设置代码行断点。</span><span class="sxs-lookup"><span data-stu-id="85809-226">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="85809-227">触发断点。</span><span class="sxs-lookup"><span data-stu-id="85809-227">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="85809-228">当代码仍在代码行断点上暂停时，在 `debug()` DevTools 控制台中运行 方法。</span><span class="sxs-lookup"><span data-stu-id="85809-228">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="85809-229">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="85809-229">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "开始在 Microsoft Edge 开发人员工具中调试 JavaScript |Microsoft Docs"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "提取 API |MDN"  

> [!NOTE]
> <span data-ttu-id="85809-232">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="85809-232">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="85809-233">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="85809-233">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="85809-235">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="85809-235">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
