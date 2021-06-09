---
description: 有关使用辅助技术（如屏幕阅读器）导航 Microsoft Edge 开发工具的指南。
title: 使用辅助技术导航 Microsoft Edge 开发工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2cb57a8ea1ea34506b4698d80ae0981d8716f3d2
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597103"
---
<!-- Copyright Rob Dodson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="navigate-microsoft-edge-devtools-with-assistive-technology"></a><span data-ttu-id="f5883-104">使用辅助技术导航 Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="f5883-104">Navigate Microsoft Edge DevTools with assistive technology</span></span>  

<span data-ttu-id="f5883-105">本文可帮助主要依赖于辅助技术的用户（如屏幕阅读器）使用[Microsoft Edge DevTools。][MicrosoftEdgeDevtoolsMain]</span><span class="sxs-lookup"><span data-stu-id="f5883-105">This article helps users who primarily rely on assistive technology such as screen readers use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span></span>  <span data-ttu-id="f5883-106">DevTools 是内置于 Web 浏览器的一Microsoft Edge工具。</span><span class="sxs-lookup"><span data-stu-id="f5883-106">DevTools is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  

<span data-ttu-id="f5883-107">有关改善网页辅助功能的 DevTools 功能，请参阅 [DevTools][DevtoolsAccessibilityReference] 中的辅助功能测试和使用 [DevTools](accessibility-testing-in-devtools.md)的辅助功能测试概述。</span><span class="sxs-lookup"><span data-stu-id="f5883-107">For DevTools features related to improving the accessibility of a web page, see [Accessibility-testing features in DevTools][DevtoolsAccessibilityReference] and [Overview of accessibility testing using DevTools](accessibility-testing-in-devtools.md).</span></span>

<span data-ttu-id="f5883-108">开发工具的辅助功能是一项正在进行中的工作。</span><span class="sxs-lookup"><span data-stu-id="f5883-108">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="f5883-109">某些工具和选项卡在辅助技术方面比使用其他工具和选项卡更好。</span><span class="sxs-lookup"><span data-stu-id="f5883-109">Some tools and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="f5883-110">本指南将指导你完成最可访问的工具和选项卡，并重点说明你一直遇到的特定问题。</span><span class="sxs-lookup"><span data-stu-id="f5883-110">This guide walks you through the tools and tabs which are the most accessible, and highlights specific issues you may encounter along the way.</span></span>  

## <a name="overview"></a><span data-ttu-id="f5883-111">概述</span><span class="sxs-lookup"><span data-stu-id="f5883-111">Overview</span></span>  

<span data-ttu-id="f5883-112">DevTools 分为一系列工具。</span><span class="sxs-lookup"><span data-stu-id="f5883-112">DevTools is divided into a series of tools.</span></span>  <span data-ttu-id="f5883-113"> (在命令菜单中\，\*\*\** 工具称为面板 。) 工具组织__ 到主工具栏和箱工具栏上的[ARIA][W3CWaiAriaTablist]选项卡列表中。</span><span class="sxs-lookup"><span data-stu-id="f5883-113">(Within the **Command Menu**, tools are referred to as _panels_.)  Tools are organized into an [ARIA tablist][W3CWaiAriaTablist] on the main toolbar and on the drawer toolbar.</span></span>

<span data-ttu-id="f5883-114">以下是工具示例：</span><span class="sxs-lookup"><span data-stu-id="f5883-114">The following are examples of tools:</span></span>

*   <span data-ttu-id="f5883-115">元素 **工具** 允许你 [查看和更改 DOM 节点][DevtoolsDomIndexNavigateDomTreeKeyboard] 或 [CSS][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="f5883-115">The **Elements** tool lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="f5883-116">控制台 **工具** 允许你读取 JavaScript 日志和实时编辑对象。</span><span class="sxs-lookup"><span data-stu-id="f5883-116">The **Console** tool lets you read JavaScript logs and live-edit objects.</span></span>  <span data-ttu-id="f5883-117">有关详细信息，请导航到"[使用控制台"。][DevtoolsConsoleIndex]</span><span class="sxs-lookup"><span data-stu-id="f5883-117">For more information, navigate to [Use the Console][DevtoolsConsoleIndex].</span></span>

<span data-ttu-id="f5883-118">在每个工具中，都有一组或多组选项卡。</span><span class="sxs-lookup"><span data-stu-id="f5883-118">Within each tool, there are one or more sets of tabs.</span></span>  <span data-ttu-id="f5883-119">例如， **元素** 工具包含一组选项卡，包括 **样式**、 **事件**侦听器 **和辅助功能**。</span><span class="sxs-lookup"><span data-stu-id="f5883-119">For example, the **Elements** tool contains a set of tabs including **Styles**, **Event Listeners**, and **Accessibility**.</span></span>

## <a name="keyboard-shortcuts"></a><span data-ttu-id="f5883-120">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="f5883-120">Keyboard shortcuts</span></span>  

<span data-ttu-id="f5883-121">[DevTools 键盘快捷方式参考][DevtoolsShortcuts]是一本有用的工作表。</span><span class="sxs-lookup"><span data-stu-id="f5883-121">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheat sheet.</span></span>  <span data-ttu-id="f5883-122">请务必在浏览不同的工具时为它添加书签并引用回它。</span><span class="sxs-lookup"><span data-stu-id="f5883-122">Be sure to bookmark it and refer back to it as you explore the different tools.</span></span>

## <a name="open-devtools"></a><span data-ttu-id="f5883-123">打开开发工具</span><span class="sxs-lookup"><span data-stu-id="f5883-123">Open DevTools</span></span>  

<span data-ttu-id="f5883-124">若要开始，请导航到 [打开 Microsoft Edge 开发工具] [DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="f5883-124">To get started, navigate to [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="f5883-125">开发工具有多种打开方式，可以通过键盘快捷方式，也可通过菜单项将其打开。</span><span class="sxs-lookup"><span data-stu-id="f5883-125">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <a name="navigate-between-tools"></a><span data-ttu-id="f5883-126">在工具之间导航</span><span class="sxs-lookup"><span data-stu-id="f5883-126">Navigate between tools</span></span>

### <a name="navigate-by-keyboard"></a><span data-ttu-id="f5883-127">使用键盘导航</span><span class="sxs-lookup"><span data-stu-id="f5883-127">Navigate by keyboard</span></span>  

*   <span data-ttu-id="f5883-128">打开 DevTools 后，选择 `Control` + `]` \ (Windows、Linux\) 或 `Command` + `]` \ (macOS\) 将焦点移到主工具栏上的下一个工具。</span><span class="sxs-lookup"><span data-stu-id="f5883-128">With DevTools open, select `Control`+`]` \(Windows, Linux\) or `Command`+`]` \(macOS\) to move focus to the next tool on the main toolbar.</span></span>
*   <span data-ttu-id="f5883-129">选择 `Control` + `[` \ (Windows、Linux\) 或 `Command` + \ (macOS\) 将焦点移到主工具栏上的上 `[` 一个工具。</span><span class="sxs-lookup"><span data-stu-id="f5883-129">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) to move focus to the previous tool on the main toolbar.</span></span>
*   <span data-ttu-id="f5883-130">选择 `Tab` 或 `Shift` + 重复选择，直到焦点移到主工具栏或箱工具栏的选项卡，然后使用箭头键在工具 `Tab` 之间移动。</span><span class="sxs-lookup"><span data-stu-id="f5883-130">Select `Tab` or `Shift`+`Tab` repeatedly until focus moves to the tabs of the main toolbar or drawer toolbar, and then use the arrow keys to move among the tools.</span></span>

**<span data-ttu-id="f5883-131">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-131">Known issues</span></span>**  

*   <span data-ttu-id="f5883-132">一旦选择控制台**和性能**工具，某些\*\*\*\* 工具（如控制台和性能工具）可能会将焦点移到工具的内容区域中。</span><span class="sxs-lookup"><span data-stu-id="f5883-132">Some tools, such as the **Console** and **Performance** tools, may move focus into the tool's content area as soon as the tool is selected.</span></span>  <span data-ttu-id="f5883-133">这可能使得使用箭头键导航更加困难。</span><span class="sxs-lookup"><span data-stu-id="f5883-133">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="f5883-134">选定工具的名称将公布，但仅在宣布该工具中重点内容后公布。</span><span class="sxs-lookup"><span data-stu-id="f5883-134">The name of the selected tool is announced, but only after announcing the focused content in the tool.</span></span>  <span data-ttu-id="f5883-135">此通知序列可能会轻松错过工具的名称。</span><span class="sxs-lookup"><span data-stu-id="f5883-135">This sequence of announcements may make it easy to miss the name of the tool.</span></span>

### <a name="navigate-by-command-menu"></a><span data-ttu-id="f5883-136">按命令菜单导航</span><span class="sxs-lookup"><span data-stu-id="f5883-136">Navigate by Command Menu</span></span>  

<span data-ttu-id="f5883-137">若要选择特定工具，请使用命令 [菜单][DevtoolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="f5883-137">To select a specific tool, use the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  <span data-ttu-id="f5883-138">在命令菜单中，工具_称为面板。_</span><span class="sxs-lookup"><span data-stu-id="f5883-138">In the Command Menu, a tool is called a _panel_.</span></span>

1.  <span data-ttu-id="f5883-139">打开开发工具，选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 以打开“**命令菜单**”。</span><span class="sxs-lookup"><span data-stu-id="f5883-139">With DevTools open, select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="f5883-140">命令 **菜单** 是一个模糊搜索自动完成组合框。</span><span class="sxs-lookup"><span data-stu-id="f5883-140">The **Command Menu** is a fuzzy-search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="f5883-141">键入面板名称 (工具) ，然后使用键盘上的 导航 `Down Arrow` 到正确的选项。</span><span class="sxs-lookup"><span data-stu-id="f5883-141">Type the name of a panel (tool), and then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="f5883-142">选择 `Enter` 以运行命令。</span><span class="sxs-lookup"><span data-stu-id="f5883-142">Select `Enter` to run a command.</span></span>  

<span data-ttu-id="f5883-143">若要打开 **"元素"** 工具，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f5883-143">To open the **Elements** tool:</span></span>

1.  <span data-ttu-id="f5883-144">打开“**命令菜单**”。</span><span class="sxs-lookup"><span data-stu-id="f5883-144">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="f5883-145">键入 `E` ，然后键入 `L`。</span><span class="sxs-lookup"><span data-stu-id="f5883-145">Type `E` then `L`.</span></span>  <span data-ttu-id="f5883-146">选择“**面板>显示元素**”选项。</span><span class="sxs-lookup"><span data-stu-id="f5883-146">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="f5883-147">选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="f5883-147">Select `Enter`.</span></span>  

<span data-ttu-id="f5883-148">这样打开工具会将焦点放在工具的内容区域中。</span><span class="sxs-lookup"><span data-stu-id="f5883-148">Opening a tool this way puts focus in the content area of the tool.</span></span>  <span data-ttu-id="f5883-149">对于" **元素"工具** ，焦点将移动到 **DOM 树中**。</span><span class="sxs-lookup"><span data-stu-id="f5883-149">In the case of the **Elements** tool, focus moves into the **DOM Tree**.</span></span>

## <a name="elements-tool"></a><span data-ttu-id="f5883-150">元素工具</span><span class="sxs-lookup"><span data-stu-id="f5883-150">Elements tool</span></span>

### <a name="inspect-an-element-on-the-page"></a><span data-ttu-id="f5883-151">检查页面上的元素</span><span class="sxs-lookup"><span data-stu-id="f5883-151">Inspect an element on the page</span></span>  

1.  <span data-ttu-id="f5883-152">使用屏幕阅读器中的光标导航到要检查的元素。</span><span class="sxs-lookup"><span data-stu-id="f5883-152">Navigate to the element you want to inspect, using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="f5883-153">模拟右键单击元素以打开上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="f5883-153">Simulate a right-click on the element, to open the context menu.</span></span>  
1.  <span data-ttu-id="f5883-154">选择“**检查**”选项。</span><span class="sxs-lookup"><span data-stu-id="f5883-154">Choose the **Inspect** option.</span></span>  <span data-ttu-id="f5883-155">这将 [打开 Elements 工具并聚焦 DOM 树中的元素][DevtoolsDomIndexViewDomNodes]。</span><span class="sxs-lookup"><span data-stu-id="f5883-155">This [opens the Elements tool and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span></span>  

<span data-ttu-id="f5883-156">“**DOM 树**”已布局为 [ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="f5883-156">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="f5883-157">例如，导航到 [使用键盘导航“**DOM Tree**”][DevtoolsDomIndexNavigateDomTreeKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="f5883-157">For an example, navigate to [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span></span>  

### <a name="copy-the-code-for-an-element-in-the-dom-tree"></a><span data-ttu-id="f5883-158">复制 DOM 树中元素的代码</span><span class="sxs-lookup"><span data-stu-id="f5883-158">Copy the code for an element in the DOM Tree</span></span>  

1.  <span data-ttu-id="f5883-159">将焦点放在“**DOM 树**”中的节点上，然后将鼠标悬停在节点上，并打开上下文菜单 \（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="f5883-159">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="f5883-160">展开“**复制**”选项。</span><span class="sxs-lookup"><span data-stu-id="f5883-160">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="f5883-161">选择“**复制 outerHTML**”。</span><span class="sxs-lookup"><span data-stu-id="f5883-161">Choose **Copy outerHTML**.</span></span>  

**<span data-ttu-id="f5883-162">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-162">Known issues</span></span>**  

*   <span data-ttu-id="f5883-163">“**复制 outerHTML**”通常不会选择当前节点，而是选择父节点。</span><span class="sxs-lookup"><span data-stu-id="f5883-163">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="f5883-164">但是，该元素的内容应仍在复制的 outerHTML 中。</span><span class="sxs-lookup"><span data-stu-id="f5883-164">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <a name="modify-the-attributes-of-an-element-in-the-dom-tree"></a><span data-ttu-id="f5883-165">修改 DOM 树中元素的属性</span><span class="sxs-lookup"><span data-stu-id="f5883-165">Modify the attributes of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="f5883-166">将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。</span><span class="sxs-lookup"><span data-stu-id="f5883-166">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="f5883-167">选择 `Tab` 以在属性值之间移动。</span><span class="sxs-lookup"><span data-stu-id="f5883-167">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="f5883-168">听到“空格”声音时，你已位于空白文本输入内，并且能够键入新的属性值。</span><span class="sxs-lookup"><span data-stu-id="f5883-168">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="f5883-169">选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改并收听元素的全部内容。</span><span class="sxs-lookup"><span data-stu-id="f5883-169">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

**<span data-ttu-id="f5883-170">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-170">Known issues</span></span>**  

*   <span data-ttu-id="f5883-171">当你键入文本输入时，你未收到任何反馈。</span><span class="sxs-lookup"><span data-stu-id="f5883-171">When you type into the text input, you get no feedback.</span></span>  <span data-ttu-id="f5883-172">如果你输入了拼写错误并使用箭头键来浏览你的输入，你同样不会收到反馈。</span><span class="sxs-lookup"><span data-stu-id="f5883-172">If you make a typo and use the arrow keys to explore your input, you also get no feedback.</span></span>  <span data-ttu-id="f5883-173">检查工作最简单的方法是接受更改，然后收听要播报的整个元素。</span><span class="sxs-lookup"><span data-stu-id="f5883-173">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <a name="edit-the-html-of-an-element-in-the-dom-tree"></a><span data-ttu-id="f5883-174">编辑 DOM 树中元素的 HTML</span><span class="sxs-lookup"><span data-stu-id="f5883-174">Edit the HTML of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="f5883-175">将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。</span><span class="sxs-lookup"><span data-stu-id="f5883-175">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="f5883-176">选择 `Tab` 以在属性值之间移动。</span><span class="sxs-lookup"><span data-stu-id="f5883-176">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="f5883-177">当听到该元素的名称（例如，`h2`）时，你会位于文本输入内，并且可以更改元素的类型。</span><span class="sxs-lookup"><span data-stu-id="f5883-177">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="f5883-178">选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改。</span><span class="sxs-lookup"><span data-stu-id="f5883-178">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="f5883-179">例如，键入 `h3` 并选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 时，`h3` 元素的开始和结尾标记都会更改。</span><span class="sxs-lookup"><span data-stu-id="f5883-179">For example, when you type `h3` and select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span></span>  

## <a name="tabs-in-the-elements-tool"></a><span data-ttu-id="f5883-180">元素工具中的选项卡</span><span class="sxs-lookup"><span data-stu-id="f5883-180">Tabs in the Elements tool</span></span>

<span data-ttu-id="f5883-181">元素 **工具** 包含用于检查应用于元素的 CSS 或辅助功能树中相关位置等内容的其他选项卡。</span><span class="sxs-lookup"><span data-stu-id="f5883-181">The **Elements** tool contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="f5883-182">焦点在**DOM**树中的节点上时，选择直到 `Tab` 您听到已\*\*\*\* 选择样式选项卡。</span><span class="sxs-lookup"><span data-stu-id="f5883-182">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** tab is selected.</span></span>  
*   <span data-ttu-id="f5883-183">使用 `Right Arrow` 浏览其他可用的选项卡。</span><span class="sxs-lookup"><span data-stu-id="f5883-183">Use the `Right Arrow` to explore other available tabs.</span></span>

<span data-ttu-id="f5883-184">“**DOM 树**”将具有 `href` 属性的元素转换为可聚焦链接，因此可能需要多次选择 `Tab` 以访问“**样式**”窗格。</span><span class="sxs-lookup"><span data-stu-id="f5883-184">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span></span>  

**<span data-ttu-id="f5883-185">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-185">Known issues</span></span>**  

<span data-ttu-id="f5883-186">DOM **断点** 和 **属性** 选项卡不可通过键盘访问。</span><span class="sxs-lookup"><span data-stu-id="f5883-186">The **DOM Breakpoints** and **Properties** tabs are not keyboard-accessible.</span></span>  

### <a name="styles-pane"></a><span data-ttu-id="f5883-187">样式窗格</span><span class="sxs-lookup"><span data-stu-id="f5883-187">Styles pane</span></span>  

<span data-ttu-id="f5883-188">在“**样式**”窗格查找控件筛选样式、切换元素状态 \（如 [:active][MDNActive] 和 [:focus][MDNFocus]\）、切换类别和添加新类别。 </span><span class="sxs-lookup"><span data-stu-id="f5883-188">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="f5883-189">还有一个功能强大的样式检查工具，用于浏览和修改当前应用于“**DOM 树**”中处于焦点的元素的样式。</span><span class="sxs-lookup"><span data-stu-id="f5883-189">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="f5883-190">了解“**样式**”窗格的关键概念是它只显示“**DOM 树**”窗格中当前选中节点的样式。</span><span class="sxs-lookup"><span data-stu-id="f5883-190">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="f5883-191">例如，假设已完成对 `<header>` 节点样式的检查，并且现在希望查看 `<footer>` 节点的样式。</span><span class="sxs-lookup"><span data-stu-id="f5883-191">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="f5883-192">若要执行该操作，首先需要在“**DOM 树**”中选择 `<footer>` 节点。</span><span class="sxs-lookup"><span data-stu-id="f5883-192">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="f5883-193">如果使用 [检查](#inspect-an-element-on-the-page) 工作流检查位于 `footer` 节点 \（如页脚内的链接）邻近区域中的节点（该节点焦点为“**DOM 树**”），然后使用键盘导航到您感兴趣的确切节点，可能发现这一操作更为快速。</span><span class="sxs-lookup"><span data-stu-id="f5883-193">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <a name="navigate-the-styles-pane"></a><span data-ttu-id="f5883-194">导航“样式”窗格</span><span class="sxs-lookup"><span data-stu-id="f5883-194">Navigate the Styles pane</span></span>  

<span data-ttu-id="f5883-195">由于所有样式工具都以某种方式连接到“**样式**”窗格中，因此首先掌握此工具的使用具有重要意义。</span><span class="sxs-lookup"><span data-stu-id="f5883-195">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span></span>  

*   <span data-ttu-id="f5883-196">在焦点位于“**样式**”窗格时 ，选择 `Tab` 以将焦点移到内部并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="f5883-196">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="f5883-197">选择 `Tab` 直到第一个样式处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="f5883-197">Select `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="f5883-198">如果使用屏幕阅读器，则第一个样式将播报为 `element.style {}`。</span><span class="sxs-lookup"><span data-stu-id="f5883-198">If you are using a screen reader this first style is announced as `element.style {}`.</span></span>  
*   <span data-ttu-id="f5883-199">选择 `Down Arrow` 以按特定性顺序导航样式列表。</span><span class="sxs-lookup"><span data-stu-id="f5883-199">Select `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="f5883-200">屏幕阅读器将读出每个样式，播报以 CSS 文件名开头，再依次报出样式所在的行号以及样式的名称。</span><span class="sxs-lookup"><span data-stu-id="f5883-200">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="f5883-201">例如，`main.css:233 .card__img {}`。</span><span class="sxs-lookup"><span data-stu-id="f5883-201">For example, `main.css:233 .card__img {}`.</span></span>  
*   <span data-ttu-id="f5883-202">选择 `Enter` 以更详细地检查样式。</span><span class="sxs-lookup"><span data-stu-id="f5883-202">Select `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="f5883-203">焦点从样式名称的可编辑版本开始。</span><span class="sxs-lookup"><span data-stu-id="f5883-203">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="f5883-204">选择 `Tab` 以在每个 CSS 属性的可编辑版本和相应的值之间移动。</span><span class="sxs-lookup"><span data-stu-id="f5883-204">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span></span>  <span data-ttu-id="f5883-205">每个样式块的末尾都是一个空白的可编辑文本字段，可用于添加其他 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="f5883-205">At the end of each style block is a blank editable text field which you can use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="f5883-206">你可以继续选择在样式列表中移动，或者选择退出模式 `Tab` 并返回通过 `Escape` 箭头键导航。</span><span class="sxs-lookup"><span data-stu-id="f5883-206">You can continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="f5883-207">有关其他快捷方式，请导航到 [样式窗格键盘参考][DevtoolsShortcutsStylesPaneKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="f5883-207">For additional shortcuts, navigate to [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span></span>  

**<span data-ttu-id="f5883-208">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-208">Known issues</span></span>**  

*   <span data-ttu-id="f5883-209">如果你使用“**筛选器**”可编辑文本字段，则将不能再导航样式列表。</span><span class="sxs-lookup"><span data-stu-id="f5883-209">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <a name="toggle-element-state"></a><span data-ttu-id="f5883-210">切换元素状态</span><span class="sxs-lookup"><span data-stu-id="f5883-210">Toggle element state</span></span>  

<span data-ttu-id="f5883-211">若要切换元素的状态，如 `:active` 或 `:focus`：</span><span class="sxs-lookup"><span data-stu-id="f5883-211">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="f5883-212">导航到“**样式**”窗格并选择 `Tab`，直到“**切换元素状态**”按钮获得焦点。</span><span class="sxs-lookup"><span data-stu-id="f5883-212">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="f5883-213">选择 `Enter` 以展开元素状态的集合。</span><span class="sxs-lookup"><span data-stu-id="f5883-213">Select `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="f5883-214">元素状态将显示为一组复选框。</span><span class="sxs-lookup"><span data-stu-id="f5883-214">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="f5883-215">选择 `Tab`，直到第一个状态 `:active` 获得焦点。</span><span class="sxs-lookup"><span data-stu-id="f5883-215">Select `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="f5883-216">选择 `Space` 以将其启用。</span><span class="sxs-lookup"><span data-stu-id="f5883-216">Select `Space` to enable it.</span></span>  <span data-ttu-id="f5883-217">如果 DOM 树中当前选定的元素具有 `:active` 样式，则现在应用该样式。</span><span class="sxs-lookup"><span data-stu-id="f5883-217">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="f5883-218">按住 `Tab` 以浏览所有可用状态。</span><span class="sxs-lookup"><span data-stu-id="f5883-218">Hold `Tab` to explore all of the available states.</span></span>  

#### <a name="add-an-existing-class"></a><span data-ttu-id="f5883-219">添加现有类别</span><span class="sxs-lookup"><span data-stu-id="f5883-219">Add an existing class</span></span>  

<span data-ttu-id="f5883-220">“**元素类别**”按钮与“**切换元素状态**”按钮相邻。</span><span class="sxs-lookup"><span data-stu-id="f5883-220">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="f5883-221">若要将焦点移到它，请选择 `Tab` ，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="f5883-221">To move the focus to it, select `Tab` and then select `Enter`.</span></span>  <span data-ttu-id="f5883-222">焦点移到标记为添加新类的 **编辑文本字段**。</span><span class="sxs-lookup"><span data-stu-id="f5883-222">Focus moves into an edit text field labeled **Add new class**.</span></span>  

<span data-ttu-id="f5883-223">“**元素类别**”按钮主要用于向元素添加现有类别。</span><span class="sxs-lookup"><span data-stu-id="f5883-223">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="f5883-224">例如，如果您的样式表包含一个名为 的帮助程序类，您可以在编辑文本字段内选择 以显示类的建议列表，并使用 查找 `.clearfix` `.` `Down Arrow` `.clearfix` 建议。</span><span class="sxs-lookup"><span data-stu-id="f5883-224">For example, if your stylesheet contained a helper class named `.clearfix`, you can select `.` inside of the edit text field to display a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="f5883-225">或者自行键入类别名称，然后选择 `Enter` 以应用类别。</span><span class="sxs-lookup"><span data-stu-id="f5883-225">Or type the class name out yourself and select `Enter` to apply it.</span></span>  

#### <a name="add-a-new-style-rule"></a><span data-ttu-id="f5883-226">添加新的样式规则</span><span class="sxs-lookup"><span data-stu-id="f5883-226">Add a new style rule</span></span>  

<span data-ttu-id="f5883-227">“**新样式规则**”按钮与“**元素类别**”按钮相邻。</span><span class="sxs-lookup"><span data-stu-id="f5883-227">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="f5883-228">若要将焦点移到它，请选择 `Tab` ，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="f5883-228">To move the focus to it, select `Tab` and then select `Enter`.</span></span>  <span data-ttu-id="f5883-229">焦点将移到样式检查器内的可编辑文本字段中。</span><span class="sxs-lookup"><span data-stu-id="f5883-229">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="f5883-230">该字段的初始文本内容是在“**DOM 树**”中所选元素的标记名称。</span><span class="sxs-lookup"><span data-stu-id="f5883-230">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="f5883-231">您可以在此字段中键入您希望的任何类名称，然后选择为其分配 `Tab` CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="f5883-231">You can type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span></span>  

### <a name="computed-tab"></a><span data-ttu-id="f5883-232">已计算选项卡</span><span class="sxs-lookup"><span data-stu-id="f5883-232">Computed tab</span></span>  

<span data-ttu-id="f5883-233">在焦点位于“**已计算**”选项卡上时，选择 `Tab` 以将焦点移到内部并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="f5883-233">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="f5883-234">在“**已计算**”选项卡中，有一些控件用于浏览哪些 CSS 属性实际上是按特定性顺序应用于元素的。</span><span class="sxs-lookup"><span data-stu-id="f5883-234">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add Computed tab section when available  -->  

#### <a name="explore-all-computed-styles"></a><span data-ttu-id="f5883-235">浏览所有已计算的样式</span><span class="sxs-lookup"><span data-stu-id="f5883-235">Explore all computed styles</span></span>  

<span data-ttu-id="f5883-236">选择 `Tab`，直至到达已计算样式的集合。</span><span class="sxs-lookup"><span data-stu-id="f5883-236">Select `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="f5883-237">这些内容将显示为“[ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="f5883-237">These are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="f5883-238">展开列表框会显示哪些 CSS 选择器正在应用已计算样式。</span><span class="sxs-lookup"><span data-stu-id="f5883-238">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="f5883-239">这些选择器按特定性进行整理。</span><span class="sxs-lookup"><span data-stu-id="f5883-239">These selectors are organized by specificity.</span></span>  <span data-ttu-id="f5883-240">屏幕阅读器将播报已计算的值、当前哪个 CSS 选择器正在匹配、包含该选择器的样式表文件名以及选择器行号。</span><span class="sxs-lookup"><span data-stu-id="f5883-240">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

**<span data-ttu-id="f5883-241">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-241">Known issues</span></span>**  

*   <span data-ttu-id="f5883-242">如果使用“**筛选**”文本字段，则不再能够检查样式。</span><span class="sxs-lookup"><span data-stu-id="f5883-242">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <a name="event-listeners-tab"></a><span data-ttu-id="f5883-243">"事件侦听器"选项卡</span><span class="sxs-lookup"><span data-stu-id="f5883-243">Event Listeners tab</span></span>  

<span data-ttu-id="f5883-244">若要检查应用于元素的事件侦听器，请选择"元素"工具，然后选择"\*\*\*\* 事件侦听器"选项卡 ("\*\*\*\* 样式"选项卡) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f5883-244">To inspect the event listeners that are applied to an element, select the **Elements** tool and then select the **Event Listeners** tab (grouped with the **Styles** tab).</span></span>

#### <a name="explore-event-listeners"></a><span data-ttu-id="f5883-245">浏览事件侦听器</span><span class="sxs-lookup"><span data-stu-id="f5883-245">Explore event listeners</span></span>  

<span data-ttu-id="f5883-246">事件侦听器将显示为 [ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="f5883-246">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="f5883-247">可以使用箭头键导航它们。</span><span class="sxs-lookup"><span data-stu-id="f5883-247">You can use the arrow keys to navigate them.</span></span>  <span data-ttu-id="f5883-248">屏幕阅读器将播报事件侦听器所附加到的 DOM 对象名称，以及定义事件侦听器的文件名和行号。</span><span class="sxs-lookup"><span data-stu-id="f5883-248">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <a name="accessibility-tab"></a><span data-ttu-id="f5883-249">"辅助功能"选项卡</span><span class="sxs-lookup"><span data-stu-id="f5883-249">Accessibility tab</span></span>

<span data-ttu-id="f5883-250">在 `Tab` "元素"工具的"辅助功能 **"** 选项卡内选择要四 **处移动的** 键。</span><span class="sxs-lookup"><span data-stu-id="f5883-250">Select the `Tab` key to move around within the **Accessibility** tab in the **Elements** tool.</span></span>

<span data-ttu-id="f5883-251">" **辅助功能"** 选项卡位于"样式" **选项卡** 附近。在"辅助功能"选项卡上，有一些控件用于探索辅助功能树、应用于元素的 ARIA 属性以及计算出的辅助功能属性。</span><span class="sxs-lookup"><span data-stu-id="f5883-251">The **Accessibility** tab is near the **Styles** tab. On the Accessibility tab, there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  <span data-ttu-id="f5883-252">有关详细信息，请导航到使用 [辅助功能选项卡测试辅助功能][DevtoolsAccessibilityTab]。</span><span class="sxs-lookup"><span data-stu-id="f5883-252">For more information, navigate to [Test accessibility using the Accessibility tab][DevtoolsAccessibilityTab].</span></span>

#### <a name="accessibility-tree"></a><span data-ttu-id="f5883-253">辅助功能树</span><span class="sxs-lookup"><span data-stu-id="f5883-253">Accessibility Tree</span></span>  

<span data-ttu-id="f5883-254">**辅助功能树** 显示为 [ARIA 树][W3CWaiAriaTree]，其中每个 `treeitem` 对应 DOM 中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="f5883-254">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="f5883-255">树将播报选定节点的已计算角色。</span><span class="sxs-lookup"><span data-stu-id="f5883-255">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="f5883-256">通用元素（如 `div` 和 `span`）将在树中播报为 “GenericContainer”。</span><span class="sxs-lookup"><span data-stu-id="f5883-256">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="f5883-257">使用箭头键来遍历树并浏览父子级关系。</span><span class="sxs-lookup"><span data-stu-id="f5883-257">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

**<span data-ttu-id="f5883-258">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-258">Known issues</span></span>**  

*   <span data-ttu-id="f5883-259">对于 MacOS 屏幕阅读器（如\*\*\*\* VoiceOver）来说，"辅助功能"选项卡Microsoft Edge [ARIA][W3CWaiAriaTree]树的类型可能未正确公开。</span><span class="sxs-lookup"><span data-stu-id="f5883-259">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** tab may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="f5883-260">订阅 [Chromium 问题 #868480][ChromiumIssues868480] 以获取有关此问题进展的通知。</span><span class="sxs-lookup"><span data-stu-id="f5883-260">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="f5883-261">每个 **ARIA 属性** 和 **已计算属性** 部分都标记为 [ARIA 树][W3CWaiAriaTree]，但当前每个部分都不具有焦点管理且不可通过键盘操作。</span><span class="sxs-lookup"><span data-stu-id="f5883-261">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <a name="lighthouse-tool"></a><span data-ttu-id="f5883-262">Lighthouse 工具</span><span class="sxs-lookup"><span data-stu-id="f5883-262">Lighthouse tool</span></span>

<span data-ttu-id="f5883-263">**Lighthouse** 对网站运行一系列测试，以检查与性能、辅助功能、SEO 和大量其他类别相关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="f5883-263">**Lighthouse** runs a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <a name="configure-and-generate-a-report"></a><span data-ttu-id="f5883-264">配置和生成报告</span><span class="sxs-lookup"><span data-stu-id="f5883-264">Configure and generate a report</span></span>

1.  <span data-ttu-id="f5883-265">在 DevTools 中首次打开 **Lighthouse** 工具时，焦点将放置在"生成报告 **"按钮** 上。</span><span class="sxs-lookup"><span data-stu-id="f5883-265">When the **Lighthouse** tool is first opened in DevTools, focus is placed on the **Generate report** button.</span></span>  <span data-ttu-id="f5883-266">默认情况下，表单配置为在模拟 3G 连接上使用移动模拟来运行每个类别的报告。</span><span class="sxs-lookup"><span data-stu-id="f5883-266">By default, the form is configured to run reports for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="f5883-267">若要更改报告设置，请使用 将焦点放在 `Shift` + `Tab` **Lighthouse 设置上**，或导航回浏览模式。</span><span class="sxs-lookup"><span data-stu-id="f5883-267">To change the report settings, use `Shift`+`Tab` to put focus on **Lighthouse settings**, or navigate back in Browse mode.</span></span>  
1.  <span data-ttu-id="f5883-268">准备好运行报告后，导航回"生成 **报告"** 按钮并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="f5883-268">When you are ready to run the report, navigate back to the **Generate report** button and select `Enter`.</span></span>  
1.  <span data-ttu-id="f5883-269">焦点将移动到使用具有“**取消**”按钮的模式窗口，该按钮允许退出审核。</span><span class="sxs-lookup"><span data-stu-id="f5883-269">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="f5883-270">审核运行并多次刷新页面时，可能会听到一系列有声提示。</span><span class="sxs-lookup"><span data-stu-id="f5883-270">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

**<span data-ttu-id="f5883-271">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5883-271">Known issues</span></span>**  

*   <span data-ttu-id="f5883-272">配置窗体的不同部分当前未标记有 `fieldset` 元素。</span><span class="sxs-lookup"><span data-stu-id="f5883-272">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="f5883-273">在浏览模式下导航它们可能会更方便地了解与每个部分关联的控件。</span><span class="sxs-lookup"><span data-stu-id="f5883-273">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="f5883-274">审核结束运行后，不会发布任何有声提示或实时区域公告。</span><span class="sxs-lookup"><span data-stu-id="f5883-274">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="f5883-275">通常，审核需要大约 30 秒，在此之后，你将能够导航到结果。</span><span class="sxs-lookup"><span data-stu-id="f5883-275">Generally the audit takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="f5883-276">使用浏览模式可能是获取结果的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="f5883-276">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <a name="navigate-the-lighthouse-report"></a><span data-ttu-id="f5883-277">导航"浅楼"报表</span><span class="sxs-lookup"><span data-stu-id="f5883-277">Navigate the Lighthouse report</span></span>  

<span data-ttu-id="f5883-278">Lighthouse 报告分为与每个审核类别对应的部分。</span><span class="sxs-lookup"><span data-stu-id="f5883-278">The Lighthouse report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="f5883-279">报告打开时显示每个类别的分数列表。</span><span class="sxs-lookup"><span data-stu-id="f5883-279">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="f5883-280">这些分数也是可用于跳到相关部分的链接。</span><span class="sxs-lookup"><span data-stu-id="f5883-280">These scores are also links which you can use to skip to the relevant sections.</span></span>  <span data-ttu-id="f5883-281">每个章节内有可展开的 `details`元素，这些元素包含与审核通过或失败有关的信息。</span><span class="sxs-lookup"><span data-stu-id="f5883-281">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="f5883-282">默认情况下，仅显示失败的审核。</span><span class="sxs-lookup"><span data-stu-id="f5883-282">By default, only failing audits are shown.</span></span>  <span data-ttu-id="f5883-283">每节以最后一个 `details` 元素结尾，该元素包含所有通过的审核。</span><span class="sxs-lookup"><span data-stu-id="f5883-283">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="f5883-284">若要运行新审核，请使用 `Shift` + `Tab` 退出报告并选择"生成**报告"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="f5883-284">To run a new audit, use `Shift`+`Tab` to exit the report and select the **Generate report** button.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f5883-285">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="f5883-285">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"  
[DevtoolsAccessibilityTab]: accessibility-tab.md "使用&quot;辅助功能&quot;选项卡工具测试|Microsoft Docs"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令"  
[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 | Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md#view-dom-nodes“查看 DOM 节点 - 查看和更改 DOM 入门 | Microsoft 文档”  
<span data-ttu-id="f5883-293">[DevtoolsDomindexexNaviDomGateKeyboard]： .。/dom/index.md#navigate-dom-tree-with-dom-tree-with-a-keyboard“使用键盘导航 DOM 树 - 查看和更改 DOM 入门 | Microsoft 文档”</span><span class="sxs-lookup"><span data-stu-id="f5883-293">[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "Navigate the DOM Tree with a keyboard - Get started with viewing and changing the DOM | Microsoft Docs"</span></span>  
<span data-ttu-id="f5883-294">[DevtoolsOpen]：./open/index.md“打开 Microsoft Edge 开发工具 | Microsoft 文档”</span><span class="sxs-lookup"><span data-stu-id="f5883-294">[DevtoolsOpen]: ../open/index.md "Open Microsoft Edge DevTools | Microsoft Docs"</span></span>  
<span data-ttu-id="f5883-295">[DevtoolsShortcuts]：.。/shortcuts/index.md“Microsoft Edge 开发工具键盘快捷方式 | Microsoft 文档”</span><span class="sxs-lookup"><span data-stu-id="f5883-295">[DevtoolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"</span></span>  
<span data-ttu-id="f5883-296">[DevtoolsShortcutsStylesPaneKeyboard]： ../shortcuts/index.md#styles-panel-keyboard-shortcuts "Styles panel keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts |Microsoft Docs"</span><span class="sxs-lookup"><span data-stu-id="f5883-296">[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts/index.md#styles-panel-keyboard-shortcuts "Styles panel keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"</span></span>  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "问题 868480 - 在 Mac 辅助功能中以表的形式公开 ARIA 树"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新问题 - MicrosoftDocs/edge-developer - GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ":active | MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ":focus | MDN"  

[MonorailChromiumIssues]: https://crbug.com "问题 - chromium - Monorail"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "选项卡列表（角色） - 可访问的富 Internet 应用程序(WAI-ARIA) 1.1 | W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "树（角色） - 可访问的富 Internet 应用程序 (WAI-ARIA) 1.1 | W3C"  

> [!NOTE]
> <span data-ttu-id="f5883-304">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f5883-304">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f5883-305">[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) 可查找原始页面，其作者为 [Rob Dodson][RobDodson] \（参与者，Google WebFoundamentals\）。</span><span class="sxs-lookup"><span data-stu-id="f5883-305">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f5883-307">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f5883-307">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[RobDodson]: https://developers.google.com/web/resources/contributors#rob-dodson  
