---
description: 有关使用辅助技术（如屏幕阅读器）导航 Microsoft Edge 开发工具的指南。
title: 使用辅助技术导航 Microsoft Edge 开发工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 343ce99188234b40dd8554e3db8bf303876e7b2f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398432"
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

# <a name="navigate-microsoft-edge-devtools-with-assistive-technology"></a><span data-ttu-id="85fd7-104">使用辅助技术导航 Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="85fd7-104">Navigate Microsoft Edge DevTools with assistive technology</span></span>  

<span data-ttu-id="85fd7-105">以下文章旨在帮助主要依赖于辅助技术（如屏幕阅读器）的用户访问和使用 [Microsoft Edge 开发工具][MicrosoftEdgeDevtoolsMain]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-105">The following article aims to help users who primarily rely on assistive technology like screen readers access and use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span></span>  <span data-ttu-id="85fd7-106">[Microsoft Edge 开发工具][MicrosoftEdgeDevtoolsMain] 是内置于 Microsoft Edge 浏览器的一套 Web 开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="85fd7-106">[Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  <span data-ttu-id="85fd7-107">如果正在查找与改进网页辅助功能相关的开发工具功能，请导航到[辅助功能参考][DevtoolsAccessibilityReference]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-107">If you are looking for DevTools features related to improving the accessibility of a web page,  navigate to [Accessibility Reference][DevtoolsAccessibilityReference].</span></span>  

<span data-ttu-id="85fd7-108">开发工具的辅助功能是一项正在进行中的工作。</span><span class="sxs-lookup"><span data-stu-id="85fd7-108">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="85fd7-109">与其他面板和选项卡相比，某些面板和选项卡与辅助技术的配合工作效果更好。</span><span class="sxs-lookup"><span data-stu-id="85fd7-109">Some panels and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="85fd7-110">本指南将引导你浏览最容易访问的面板，并重点介绍你在这一过程中可能遇到的特定问题。</span><span class="sxs-lookup"><span data-stu-id="85fd7-110">This guide walks you through the panels which are the most accessible and highlights specific issues you may encounter along the way.</span></span>  

## <a name="overview"></a><span data-ttu-id="85fd7-111">概述</span><span class="sxs-lookup"><span data-stu-id="85fd7-111">Overview</span></span>  

<span data-ttu-id="85fd7-112">在开始之前，首先建立关于开发工具 UI 构建方式的思维模型，这一点对于下一步学习将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="85fd7-112">Before starting, it helps to have a mental model of how the DevTools UI is structured.</span></span>  <span data-ttu-id="85fd7-113">开发工具划分为一系列面板，这些面板组织为一个 [ARIA 选项卡列表][W3CWaiAriaTablist]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-113">DevTools is divided into a series of panels which are organized into an [ARIA tablist][W3CWaiAriaTablist].</span></span>  

<span data-ttu-id="85fd7-114">例如：</span><span class="sxs-lookup"><span data-stu-id="85fd7-114">For example:</span></span>  

*   <span data-ttu-id="85fd7-115">元素**工具**允许你 [查看和更改 DOM 节点][DevtoolsDomIndexNavigateDomTreeKeyboard] 或[CSS。][DevtoolsCssIndex]</span><span class="sxs-lookup"><span data-stu-id="85fd7-115">The **Elements** tool lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="85fd7-116">通过“[控制台面板][DevtoolsConsoleIndex]”可以读取 JavaScript 日志和实时编辑对象。</span><span class="sxs-lookup"><span data-stu-id="85fd7-116">The [Console panel][DevtoolsConsoleIndex] lets you read JavaScript logs and live edit objects.</span></span>  

<span data-ttu-id="85fd7-117">每个面板的内容区域中有许多不同的工具，在文档中通常称为选项卡或窗格。</span><span class="sxs-lookup"><span data-stu-id="85fd7-117">Within the content area of each panel, there are a number of different tools, often referred to as tabs or panes in the documentation.</span></span>  
<span data-ttu-id="85fd7-118">例如 **，Elements** 工具包含用于检查事件侦听器、辅助功能树等的其他选项卡。</span><span class="sxs-lookup"><span data-stu-id="85fd7-118">For instance, the **Elements** tool contains additional tabs to inspect event listeners, the accessibility tree, and much more.</span></span>  <span data-ttu-id="85fd7-119">选项卡和窗格之间的区别在一定程度上是任意的。</span><span class="sxs-lookup"><span data-stu-id="85fd7-119">The distinction between tabs and panes is somewhat arbitrary.</span></span>  <span data-ttu-id="85fd7-120">可能审阅某一个术语的唯一原因只是为了与官方开发工具文档的其余部分保持一致。</span><span class="sxs-lookup"><span data-stu-id="85fd7-120">The only reason you may review one term or the other is to maintain consistency with the rest of the official DevTools documentation.</span></span>  

## <a name="keyboard-shortcuts"></a><span data-ttu-id="85fd7-121">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="85fd7-121">Keyboard shortcuts</span></span>  

<span data-ttu-id="85fd7-122">[DevTools 键盘快捷方式参考][DevtoolsShortcuts] 是一个有用的速查表。</span><span class="sxs-lookup"><span data-stu-id="85fd7-122">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.</span></span>  <span data-ttu-id="85fd7-123">请确保将其添加为书签，以便在浏览不同面板时进行参考。</span><span class="sxs-lookup"><span data-stu-id="85fd7-123">Be sure to bookmark it and refer back to it as you explore the different panels.</span></span>  

## <a name="open-devtools"></a><span data-ttu-id="85fd7-124">打开开发工具</span><span class="sxs-lookup"><span data-stu-id="85fd7-124">Open DevTools</span></span>  

<span data-ttu-id="85fd7-125">若要开始，请导航到 [打开 Microsoft Edge 开发工具] [DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-125">To get started, navigate to [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="85fd7-126">开发工具有多种打开方式，可以通过键盘快捷方式，也可通过菜单项将其打开。</span><span class="sxs-lookup"><span data-stu-id="85fd7-126">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <a name="navigate-between-panels"></a><span data-ttu-id="85fd7-127">在面板之间导航</span><span class="sxs-lookup"><span data-stu-id="85fd7-127">Navigate between panels</span></span>  

### <a name="navigate-by-keyboard"></a><span data-ttu-id="85fd7-128">使用键盘导航</span><span class="sxs-lookup"><span data-stu-id="85fd7-128">Navigate by keyboard</span></span>  

*   <span data-ttu-id="85fd7-129">开发工具打开后，选择 `Control`+`]` \(Windows, Linux\) 或 `Command`+`]` \(macOS\) 以聚焦下一个面板。</span><span class="sxs-lookup"><span data-stu-id="85fd7-129">With DevTools open, select `Control`+`]` \(Windows, Linux\) or `Command`+`]` \(macOS\) to focus the next panel.</span></span>  
*   <span data-ttu-id="85fd7-130">选择 `Control`+`[` \(Windows, Linux\) 或 `Command`+`[` \(macOS\) 以聚焦上一个面板。</span><span class="sxs-lookup"><span data-stu-id="85fd7-130">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) to focus the previous panel.</span></span>  
*   <span data-ttu-id="85fd7-131">还可使用 `Shift`+`Tab` 将焦点移动到面板的“[ARIA 选项卡列表][W3CWaiAriaTablist]”，并使用箭头键更改面板，不过使用前面提及的快捷方式可能更快。</span><span class="sxs-lookup"><span data-stu-id="85fd7-131">It is also possible to use `Shift`+`Tab` to move focus into the [ARIA tablist][W3CWaiAriaTablist] of a panel and use the arrow keys to change panels, though it may be faster to use the previously mentioned shortcuts.</span></span>  

**<span data-ttu-id="85fd7-132">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-132">Known issues</span></span>**  

*   <span data-ttu-id="85fd7-133">一旦激活每个面板，**某些**面板（\*\*\*\* 如控制台和性能工具）可能会将焦点移到面板内容区域中。</span><span class="sxs-lookup"><span data-stu-id="85fd7-133">Some panels, such as the **Console** and **Performance** tools, may move focus into the panel content area as soon as each panel is activated.</span></span>  <span data-ttu-id="85fd7-134">这可能使得使用箭头键导航更加困难。</span><span class="sxs-lookup"><span data-stu-id="85fd7-134">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="85fd7-135">将会播报所选面板的名称，但仅在读取面板中的重点内容之后才会播报。</span><span class="sxs-lookup"><span data-stu-id="85fd7-135">The name of the selected panel is announced, but only after it has read the focused content in the panel.</span></span>  <span data-ttu-id="85fd7-136">这种方式可能会让用户很容易忽略这一信息。</span><span class="sxs-lookup"><span data-stu-id="85fd7-136">This may make it very easy to miss.</span></span>  

### <a name="navigate-by-command-menu"></a><span data-ttu-id="85fd7-137">按命令菜单导航</span><span class="sxs-lookup"><span data-stu-id="85fd7-137">Navigate by Command Menu</span></span>  

<span data-ttu-id="85fd7-138">若要聚焦于特定面板，请使用“[命令菜单][DevtoolsCommandMenuIndex]”：</span><span class="sxs-lookup"><span data-stu-id="85fd7-138">To focus a specific panel, use the [Command Menu][DevtoolsCommandMenuIndex]:</span></span>  

1.  <span data-ttu-id="85fd7-139">打开开发工具，选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 以打开“**命令菜单**”。</span><span class="sxs-lookup"><span data-stu-id="85fd7-139">With DevTools open, select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="85fd7-140">“**命令菜单** 是一个模糊搜索自动完成的组合框。</span><span class="sxs-lookup"><span data-stu-id="85fd7-140">The **Command Menu** is a fuzzy search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="85fd7-141">键入想要打开的面板名称，然后使用键盘上的 `Down Arrow` 导航到正确选项。</span><span class="sxs-lookup"><span data-stu-id="85fd7-141">Type the name of the panel you want to open, then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="85fd7-142">选择 `Enter` 以运行命令。</span><span class="sxs-lookup"><span data-stu-id="85fd7-142">Select `Enter` to run a command.</span></span>  

<span data-ttu-id="85fd7-143">完成以下操作以打开 **Elements** 工具。</span><span class="sxs-lookup"><span data-stu-id="85fd7-143">Complete the following actions to open the **Elements** tool.</span></span>  

1.  <span data-ttu-id="85fd7-144">打开“**命令菜单**”。</span><span class="sxs-lookup"><span data-stu-id="85fd7-144">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="85fd7-145">键入 `E` ，然后键入 `L`。</span><span class="sxs-lookup"><span data-stu-id="85fd7-145">Type `E` then `L`.</span></span>  <span data-ttu-id="85fd7-146">选择“**面板>显示元素**”选项。</span><span class="sxs-lookup"><span data-stu-id="85fd7-146">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="85fd7-147">选择 `Enter` 以运行命令打开面板。</span><span class="sxs-lookup"><span data-stu-id="85fd7-147">Select `Enter` to run the command that opens the panel.</span></span>  

<span data-ttu-id="85fd7-148">用这种方式打开一个面板会将焦点引导到面板的内容上。</span><span class="sxs-lookup"><span data-stu-id="85fd7-148">Open a panel this way directs focus to the contents of the panel.</span></span>  <span data-ttu-id="85fd7-149">对于 Elements 工具 **，焦点** 将移动到 **DOM 树中**。</span><span class="sxs-lookup"><span data-stu-id="85fd7-149">In the case of the **Elements** tool, focus moves into the **DOM Tree**.</span></span>  

## <a name="elements-panel"></a><span data-ttu-id="85fd7-150">元素面板</span><span class="sxs-lookup"><span data-stu-id="85fd7-150">Elements panel</span></span>  

### <a name="inspect-an-element-on-the-page"></a><span data-ttu-id="85fd7-151">检查页面上的元素</span><span class="sxs-lookup"><span data-stu-id="85fd7-151">Inspect an element on the page</span></span>  

1.  <span data-ttu-id="85fd7-152">在屏幕阅读器中，使用光标导航到要检查的元素。</span><span class="sxs-lookup"><span data-stu-id="85fd7-152">Navigate to the element you want to inspect using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="85fd7-153">使用鼠标模拟右键单击元素以打开上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="85fd7-153">Simulate a right-click using a mouse on the element to open the context menu.</span></span>  
1.  <span data-ttu-id="85fd7-154">选择“**检查**”选项。</span><span class="sxs-lookup"><span data-stu-id="85fd7-154">Choose the **Inspect** option.</span></span>  <span data-ttu-id="85fd7-155">此操作将 [打开元素面板并聚焦于 DOM 树中的元素][DevtoolsDomIndexViewDomNodes]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-155">This [opens the Elements panel and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span></span>  

<span data-ttu-id="85fd7-156">“**DOM 树**”已布局为 [ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-156">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="85fd7-157">例如，导航到 [使用键盘导航“**DOM Tree**”][DevtoolsDomIndexNavigateDomTreeKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-157">For an example, navigate to [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span></span>  

### <a name="copy-the-code-for-an-element-in-the-dom-tree"></a><span data-ttu-id="85fd7-158">复制 DOM 树中元素的代码</span><span class="sxs-lookup"><span data-stu-id="85fd7-158">Copy the code for an element in the DOM Tree</span></span>  

1.  <span data-ttu-id="85fd7-159">将焦点放在“**DOM 树**”中的节点上，然后将鼠标悬停在节点上，并打开上下文菜单 \（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="85fd7-159">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="85fd7-160">展开“**复制**”选项。</span><span class="sxs-lookup"><span data-stu-id="85fd7-160">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="85fd7-161">选择“**复制 outerHTML**”。</span><span class="sxs-lookup"><span data-stu-id="85fd7-161">Choose **Copy outerHTML**.</span></span>  

**<span data-ttu-id="85fd7-162">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-162">Known issues</span></span>**  

*   <span data-ttu-id="85fd7-163">“**复制 outerHTML**”通常不会选择当前节点，而是选择父节点。</span><span class="sxs-lookup"><span data-stu-id="85fd7-163">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="85fd7-164">但是，该元素的内容应仍在复制的 outerHTML 中。</span><span class="sxs-lookup"><span data-stu-id="85fd7-164">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <a name="modify-the-attributes-of-an-element-in-the-dom-tree"></a><span data-ttu-id="85fd7-165">修改 DOM 树中元素的属性</span><span class="sxs-lookup"><span data-stu-id="85fd7-165">Modify the attributes of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="85fd7-166">将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。</span><span class="sxs-lookup"><span data-stu-id="85fd7-166">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="85fd7-167">选择 `Tab` 以在属性值之间移动。</span><span class="sxs-lookup"><span data-stu-id="85fd7-167">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="85fd7-168">听到“空格”声音时，你已位于空白文本输入内，并且能够键入新的属性值。</span><span class="sxs-lookup"><span data-stu-id="85fd7-168">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="85fd7-169">选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改并收听元素的全部内容。</span><span class="sxs-lookup"><span data-stu-id="85fd7-169">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

**<span data-ttu-id="85fd7-170">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-170">Known issues</span></span>**  

*   <span data-ttu-id="85fd7-171">在键入文本输入时，无法获取任何反馈。</span><span class="sxs-lookup"><span data-stu-id="85fd7-171">When you type into the text input you get no feedback.</span></span>  <span data-ttu-id="85fd7-172">如果输入错误并使用箭头键来浏览输入，也将没有任何反馈。</span><span class="sxs-lookup"><span data-stu-id="85fd7-172">If you make a typo and use the arrow keys to explore your input you also get no feedback.</span></span>  <span data-ttu-id="85fd7-173">检查工作最简单的方法是接受更改，然后收听要播报的整个元素。</span><span class="sxs-lookup"><span data-stu-id="85fd7-173">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <a name="edit-the-html-of-an-element-in-the-dom-tree"></a><span data-ttu-id="85fd7-174">编辑 DOM 树中元素的 HTML</span><span class="sxs-lookup"><span data-stu-id="85fd7-174">Edit the HTML of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="85fd7-175">将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。</span><span class="sxs-lookup"><span data-stu-id="85fd7-175">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="85fd7-176">选择 `Tab` 以在属性值之间移动。</span><span class="sxs-lookup"><span data-stu-id="85fd7-176">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="85fd7-177">当听到该元素的名称（例如，`h2`）时，你会位于文本输入内，并且可以更改元素的类型。</span><span class="sxs-lookup"><span data-stu-id="85fd7-177">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="85fd7-178">选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改。</span><span class="sxs-lookup"><span data-stu-id="85fd7-178">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="85fd7-179">例如，键入 `h3` 并选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 时，`h3` 元素的开始和结尾标记都会更改。</span><span class="sxs-lookup"><span data-stu-id="85fd7-179">For example, when you type `h3` and select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span></span>  

## <a name="elements-tool-panels"></a><span data-ttu-id="85fd7-180">元素工具面板</span><span class="sxs-lookup"><span data-stu-id="85fd7-180">Elements tool panels</span></span>  

<span data-ttu-id="85fd7-181">元素 **工具** 包含用于检查应用于元素或辅助功能树中相关位置的 CSS 等内容的其他选项卡。</span><span class="sxs-lookup"><span data-stu-id="85fd7-181">The **Elements** tool contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="85fd7-182">将焦点放在“**DOM 树**”中的节点上时，选择 `Tab` 直至听到已选择“**样式**”。</span><span class="sxs-lookup"><span data-stu-id="85fd7-182">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** pane is selected.</span></span>  
*   <span data-ttu-id="85fd7-183">使用 `Right Arrow` 浏览其他可用的选项卡。</span><span class="sxs-lookup"><span data-stu-id="85fd7-183">Use the `Right Arrow` to explore other available tabs.</span></span>  

<span data-ttu-id="85fd7-184">“**DOM 树**”将具有 `href` 属性的元素转换为可聚焦链接，因此可能需要多次选择 `Tab` 以访问“**样式**”窗格。</span><span class="sxs-lookup"><span data-stu-id="85fd7-184">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span></span>  

**<span data-ttu-id="85fd7-185">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-185">Known issues</span></span>**  

<span data-ttu-id="85fd7-186">不能通过键盘访问“**DOM 断点**”和“**属性**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="85fd7-186">The **DOM Breakpoints** and **Properties** tabs are not keyboard accessible.</span></span>  

### <a name="styles-pane"></a><span data-ttu-id="85fd7-187">样式窗格</span><span class="sxs-lookup"><span data-stu-id="85fd7-187">Styles pane</span></span>  

<span data-ttu-id="85fd7-188">在“**样式**”窗格查找控件筛选样式、切换元素状态 \（如 [:active][MDNActive] 和 [:focus][MDNFocus]\）、切换类别和添加新类别。 </span><span class="sxs-lookup"><span data-stu-id="85fd7-188">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="85fd7-189">还有一个功能强大的样式检查工具，用于浏览和修改当前应用于“**DOM 树**”中处于焦点的元素的样式。</span><span class="sxs-lookup"><span data-stu-id="85fd7-189">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="85fd7-190">了解“**样式**”窗格的关键概念是它只显示“**DOM 树**”窗格中当前选中节点的样式。</span><span class="sxs-lookup"><span data-stu-id="85fd7-190">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="85fd7-191">例如，假设已完成对 `<header>` 节点样式的检查，并且现在希望查看 `<footer>` 节点的样式。</span><span class="sxs-lookup"><span data-stu-id="85fd7-191">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="85fd7-192">若要执行该操作，首先需要在“**DOM 树**”中选择 `<footer>` 节点。</span><span class="sxs-lookup"><span data-stu-id="85fd7-192">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="85fd7-193">如果使用 [检查](#inspect-an-element-on-the-page) 工作流检查位于 `footer` 节点 \（如页脚内的链接）邻近区域中的节点（该节点焦点为“**DOM 树**”），然后使用键盘导航到您感兴趣的确切节点，可能发现这一操作更为快速。</span><span class="sxs-lookup"><span data-stu-id="85fd7-193">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <a name="navigate-the-styles-pane"></a><span data-ttu-id="85fd7-194">导航“样式”窗格</span><span class="sxs-lookup"><span data-stu-id="85fd7-194">Navigate the Styles pane</span></span>  

<span data-ttu-id="85fd7-195">由于所有样式工具都以某种方式连接到“**样式**”窗格中，因此首先掌握此工具的使用具有重要意义。</span><span class="sxs-lookup"><span data-stu-id="85fd7-195">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span></span>  

*   <span data-ttu-id="85fd7-196">在焦点位于“**样式**”窗格时 ，选择 `Tab` 以将焦点移到内部并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="85fd7-196">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="85fd7-197">选择 `Tab` 直到第一个样式处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="85fd7-197">Select `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="85fd7-198">如果使用屏幕阅读器，则第一个样式将播报为 `element.style {}`。</span><span class="sxs-lookup"><span data-stu-id="85fd7-198">If you are using a screen reader this first style is announced as `element.style {}`.</span></span>  
*   <span data-ttu-id="85fd7-199">选择 `Down Arrow` 以按特定性顺序导航样式列表。</span><span class="sxs-lookup"><span data-stu-id="85fd7-199">Select `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="85fd7-200">屏幕阅读器将读出每个样式，播报以 CSS 文件名开头，再依次报出样式所在的行号以及样式的名称。</span><span class="sxs-lookup"><span data-stu-id="85fd7-200">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="85fd7-201">例如，`main.css:233 .card__img {}`。</span><span class="sxs-lookup"><span data-stu-id="85fd7-201">For example, `main.css:233 .card__img {}`.</span></span>  
*   <span data-ttu-id="85fd7-202">选择 `Enter` 以更详细地检查样式。</span><span class="sxs-lookup"><span data-stu-id="85fd7-202">Select `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="85fd7-203">焦点从样式名称的可编辑版本开始。</span><span class="sxs-lookup"><span data-stu-id="85fd7-203">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="85fd7-204">选择 `Tab` 以在每个 CSS 属性的可编辑版本和相应的值之间移动。</span><span class="sxs-lookup"><span data-stu-id="85fd7-204">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span></span>  <span data-ttu-id="85fd7-205">每个样式块的结尾处是一个空白的可编辑文本字段，可将其用于添加其他 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="85fd7-205">At the end of each style block is a blank editable text field which you may use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="85fd7-206">可以继续选择 `Tab` 以在样式列表中移动，或选择 `Escape` 以退出模式并返回到使用箭头键导航。</span><span class="sxs-lookup"><span data-stu-id="85fd7-206">You may continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="85fd7-207">有关其他快捷方式，请导航到 [样式窗格键盘参考][DevtoolsShortcutsStylesPaneKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-207">For additional shortcuts, navigate to [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span></span>  

**<span data-ttu-id="85fd7-208">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-208">Known issues</span></span>**  

*   <span data-ttu-id="85fd7-209">如果你使用“**筛选器**”可编辑文本字段，则将不能再导航样式列表。</span><span class="sxs-lookup"><span data-stu-id="85fd7-209">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <a name="toggle-element-state"></a><span data-ttu-id="85fd7-210">切换元素状态</span><span class="sxs-lookup"><span data-stu-id="85fd7-210">Toggle element state</span></span>  

<span data-ttu-id="85fd7-211">若要切换元素的状态，如 `:active` 或 `:focus`：</span><span class="sxs-lookup"><span data-stu-id="85fd7-211">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="85fd7-212">导航到“**样式**”窗格并选择 `Tab`，直到“**切换元素状态**”按钮获得焦点。</span><span class="sxs-lookup"><span data-stu-id="85fd7-212">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="85fd7-213">选择 `Enter` 以展开元素状态的集合。</span><span class="sxs-lookup"><span data-stu-id="85fd7-213">Select `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="85fd7-214">元素状态将显示为一组复选框。</span><span class="sxs-lookup"><span data-stu-id="85fd7-214">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="85fd7-215">选择 `Tab`，直到第一个状态 `:active` 获得焦点。</span><span class="sxs-lookup"><span data-stu-id="85fd7-215">Select `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="85fd7-216">选择 `Space` 以将其启用。</span><span class="sxs-lookup"><span data-stu-id="85fd7-216">Select `Space` to enable it.</span></span>  <span data-ttu-id="85fd7-217">如果 DOM 树中当前选定的元素具有 `:active` 样式，则现在应用该样式。</span><span class="sxs-lookup"><span data-stu-id="85fd7-217">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="85fd7-218">按住 `Tab` 以浏览所有可用状态。</span><span class="sxs-lookup"><span data-stu-id="85fd7-218">Hold `Tab` to explore all of the available states.</span></span>  

#### <a name="add-an-existing-class"></a><span data-ttu-id="85fd7-219">添加现有类别</span><span class="sxs-lookup"><span data-stu-id="85fd7-219">Add an existing class</span></span>  

<span data-ttu-id="85fd7-220">“**元素类别**”按钮与“**切换元素状态**”按钮相邻。</span><span class="sxs-lookup"><span data-stu-id="85fd7-220">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="85fd7-221">若要将焦点移动到此按钮上，请选择 `Tab`，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="85fd7-221">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="85fd7-222">焦点将移至一个标记为“**添加新类别**”的编辑文本字段。</span><span class="sxs-lookup"><span data-stu-id="85fd7-222">Focus moves into an edit text field labeled **Add New Class**.</span></span>  

<span data-ttu-id="85fd7-223">“**元素类别**”按钮主要用于向元素添加现有类别。</span><span class="sxs-lookup"><span data-stu-id="85fd7-223">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="85fd7-224">例如，如果样式表包含名为 `.clearfix` 的帮助程序类别，可选择编辑文本字段中的 `.` 以显示类别建议列表，并使用 `Down Arrow` 查找 `.clearfix` 建议。</span><span class="sxs-lookup"><span data-stu-id="85fd7-224">For example, if your stylesheet contained a helper class named `.clearfix` you may select `.` inside of the edit text field to display a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="85fd7-225">或者自行键入类别名称，然后选择 `Enter` 以应用类别。</span><span class="sxs-lookup"><span data-stu-id="85fd7-225">Or type the class name out yourself and select `Enter` to apply it.</span></span>  

#### <a name="add-a-new-style-rule"></a><span data-ttu-id="85fd7-226">添加新的样式规则</span><span class="sxs-lookup"><span data-stu-id="85fd7-226">Add a new style rule</span></span>  

<span data-ttu-id="85fd7-227">“**新样式规则**”按钮与“**元素类别**”按钮相邻。</span><span class="sxs-lookup"><span data-stu-id="85fd7-227">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="85fd7-228">若要将焦点移动到此按钮上，请选择 `Tab`，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="85fd7-228">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="85fd7-229">焦点将移到样式检查器内的可编辑文本字段中。</span><span class="sxs-lookup"><span data-stu-id="85fd7-229">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="85fd7-230">该字段的初始文本内容是在“**DOM 树**”中所选元素的标记名称。</span><span class="sxs-lookup"><span data-stu-id="85fd7-230">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="85fd7-231">可以在此字段中键入希望键入的任何类别名称，然后选择 `Tab` 以向其分配 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="85fd7-231">You may type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span></span>  

### <a name="computed-tab"></a><span data-ttu-id="85fd7-232">已计算选项卡</span><span class="sxs-lookup"><span data-stu-id="85fd7-232">Computed tab</span></span>  

<span data-ttu-id="85fd7-233">在焦点位于“**已计算**”选项卡上时，选择 `Tab` 以将焦点移到内部并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="85fd7-233">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="85fd7-234">在“**已计算**”选项卡中，有一些控件用于浏览哪些 CSS 属性实际上是按特定性顺序应用于元素的。</span><span class="sxs-lookup"><span data-stu-id="85fd7-234">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add computed tab section when available  -->  

#### <a name="explore-all-computed-styles"></a><span data-ttu-id="85fd7-235">浏览所有已计算的样式</span><span class="sxs-lookup"><span data-stu-id="85fd7-235">Explore all computed styles</span></span>  

<span data-ttu-id="85fd7-236">选择 `Tab`，直至到达已计算样式的集合。</span><span class="sxs-lookup"><span data-stu-id="85fd7-236">Select `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="85fd7-237">这些内容将显示为“[ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-237">These are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="85fd7-238">展开列表框会显示哪些 CSS 选择器正在应用已计算样式。</span><span class="sxs-lookup"><span data-stu-id="85fd7-238">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="85fd7-239">这些选择器按特定性进行整理。</span><span class="sxs-lookup"><span data-stu-id="85fd7-239">These selectors are organized by specificity.</span></span>  <span data-ttu-id="85fd7-240">屏幕阅读器将播报已计算的值、当前哪个 CSS 选择器正在匹配、包含该选择器的样式表文件名以及选择器行号。</span><span class="sxs-lookup"><span data-stu-id="85fd7-240">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

**<span data-ttu-id="85fd7-241">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-241">Known issues</span></span>**  

*   <span data-ttu-id="85fd7-242">如果使用“**筛选**”文本字段，则不再能够检查样式。</span><span class="sxs-lookup"><span data-stu-id="85fd7-242">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <a name="event-listeners-tab"></a><span data-ttu-id="85fd7-243">事件侦听器选项卡</span><span class="sxs-lookup"><span data-stu-id="85fd7-243">Event listeners tab</span></span>  

<span data-ttu-id="85fd7-244">在" **元素** "工具中，可以使用"事件侦听器"选项卡检查应用于元素 **的事件** 侦听器。 焦点在 **"样式"** 面板上时，选择以 `Right Arrow` 导航到 **"事件侦听器"** 面板。</span><span class="sxs-lookup"><span data-stu-id="85fd7-244">From within the **Elements** tool you may inspect the event listeners applied to an element using the **Event Listeners** tab.  With focus on the **Styles** panel, select the `Right Arrow` to navigate to the **Event Listeners** panel.</span></span>  

#### <a name="explore-event-listeners"></a><span data-ttu-id="85fd7-245">浏览事件侦听器</span><span class="sxs-lookup"><span data-stu-id="85fd7-245">Explore event listeners</span></span>  

<span data-ttu-id="85fd7-246">事件侦听器将显示为 [ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="85fd7-246">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="85fd7-247">可以使用箭头键导航。</span><span class="sxs-lookup"><span data-stu-id="85fd7-247">You may use the arrow keys to navigate them.</span></span>  <span data-ttu-id="85fd7-248">屏幕阅读器将播报事件侦听器所附加到的 DOM 对象名称，以及定义事件侦听器的文件名和行号。</span><span class="sxs-lookup"><span data-stu-id="85fd7-248">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <a name="accessibility-pane"></a><span data-ttu-id="85fd7-249">辅助功能窗格</span><span class="sxs-lookup"><span data-stu-id="85fd7-249">Accessibility pane</span></span>  

<span data-ttu-id="85fd7-250">在焦点位于“**辅助功能**”窗格时，选择 `Tab` 以将焦点移到内部并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="85fd7-250">With focus on the **Accessibility** pane, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="85fd7-251">在“[辅助功能窗格][DevtoolsAccessibilityReference] 上，有用于浏览辅助功能树、应用于元素的 ARIA 属性和已计算辅助功能属性的控件。</span><span class="sxs-lookup"><span data-stu-id="85fd7-251">On the [Accessibility pane][DevtoolsAccessibilityReference] there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  

#### <a name="accessibility-tree"></a><span data-ttu-id="85fd7-252">辅助功能树</span><span class="sxs-lookup"><span data-stu-id="85fd7-252">Accessibility Tree</span></span>  

<span data-ttu-id="85fd7-253">**辅助功能树** 显示为 [ARIA 树][W3CWaiAriaTree]，其中每个 `treeitem` 对应 DOM 中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="85fd7-253">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="85fd7-254">树将播报选定节点的已计算角色。</span><span class="sxs-lookup"><span data-stu-id="85fd7-254">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="85fd7-255">通用元素（如 `div` 和 `span`）将在树中播报为 “GenericContainer”。</span><span class="sxs-lookup"><span data-stu-id="85fd7-255">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="85fd7-256">使用箭头键来遍历树并浏览父子级关系。</span><span class="sxs-lookup"><span data-stu-id="85fd7-256">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

**<span data-ttu-id="85fd7-257">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-257">Known issues</span></span>**  

*   <span data-ttu-id="85fd7-258">“**辅助功能**” 窗格使用的 [ARIA 树][W3CWaiAriaTree] 类型可能未在 Microsoft Edge for macOS 屏幕阅读器（如 VoiceOver）中正确公开。 </span><span class="sxs-lookup"><span data-stu-id="85fd7-258">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** pane may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="85fd7-259">订阅 [Chromium 问题 #868480][ChromiumIssues868480] 以获取有关此问题进展的通知。</span><span class="sxs-lookup"><span data-stu-id="85fd7-259">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="85fd7-260">每个 **ARIA 属性** 和 **已计算属性** 部分都标记为 [ARIA 树][W3CWaiAriaTree]，但当前每个部分都不具有焦点管理且不可通过键盘操作。</span><span class="sxs-lookup"><span data-stu-id="85fd7-260">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <a name="audits-panel"></a><span data-ttu-id="85fd7-261">“审核”面板</span><span class="sxs-lookup"><span data-stu-id="85fd7-261">Audits panel</span></span>  

<span data-ttu-id="85fd7-262">审核 **工具** 应针对网站运行一系列测试，以检查与性能、辅助功能、SEO 和大量其他类别相关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="85fd7-262">The **Audits** tool you should run a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <a name="configure-and-run-an-audit"></a><span data-ttu-id="85fd7-263">配置和运行审核</span><span class="sxs-lookup"><span data-stu-id="85fd7-263">Configure and run an audit</span></span>  

1.  <span data-ttu-id="85fd7-264">首次**打开审核**工具时，焦点将放在表单末尾的"运行\*\*\*\* 审核"按钮上。</span><span class="sxs-lookup"><span data-stu-id="85fd7-264">When the **Audits** tool is first opened, focus is placed on the **Run Audit** button at the end of the form.</span></span>  <span data-ttu-id="85fd7-265">默认情况下，窗体配置为使用模拟 3G 连接上的移动仿真对每个类别运行审核。</span><span class="sxs-lookup"><span data-stu-id="85fd7-265">By default the form is configured to run audits for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="85fd7-266">使用`Shift`+`Tab`或导航回到浏览模式以更改审核设置。</span><span class="sxs-lookup"><span data-stu-id="85fd7-266">Use `Shift`+`Tab` or navigate back in Browse mode to change the audit settings.</span></span>  
1.  <span data-ttu-id="85fd7-267">准备好运行审核时，请导航回到“**运行审核**”按钮并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="85fd7-267">When you are ready to run the audit, navigate back to the **Run Audit** button and select `Enter`.</span></span>  
1.  <span data-ttu-id="85fd7-268">焦点将移动到使用具有“**取消**”按钮的模式窗口，该按钮允许退出审核。</span><span class="sxs-lookup"><span data-stu-id="85fd7-268">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="85fd7-269">审核运行并多次刷新页面时，可能会听到一系列有声提示。</span><span class="sxs-lookup"><span data-stu-id="85fd7-269">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

**<span data-ttu-id="85fd7-270">已知问题</span><span class="sxs-lookup"><span data-stu-id="85fd7-270">Known issues</span></span>**  

*   <span data-ttu-id="85fd7-271">配置窗体的不同部分当前未标记有 `fieldset` 元素。</span><span class="sxs-lookup"><span data-stu-id="85fd7-271">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="85fd7-272">在浏览模式下导航它们可能会更方便地了解与每个部分关联的控件。</span><span class="sxs-lookup"><span data-stu-id="85fd7-272">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="85fd7-273">审核结束运行后，不会发布任何有声提示或实时区域公告。</span><span class="sxs-lookup"><span data-stu-id="85fd7-273">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="85fd7-274">此过程通常需要大约 30 秒，然后你将能够导航到结果。</span><span class="sxs-lookup"><span data-stu-id="85fd7-274">Generally it takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="85fd7-275">使用浏览模式可能是获取结果的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="85fd7-275">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <a name="navigate-the-audit-report"></a><span data-ttu-id="85fd7-276">导航审核报告</span><span class="sxs-lookup"><span data-stu-id="85fd7-276">Navigate the audit report</span></span>  

<span data-ttu-id="85fd7-277">审核报告将组织成各个章节，对应每个审核类别。</span><span class="sxs-lookup"><span data-stu-id="85fd7-277">The audit report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="85fd7-278">报告打开时显示每个类别的分数列表。</span><span class="sxs-lookup"><span data-stu-id="85fd7-278">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="85fd7-279">这些分数也是可用于跳转到相关章节的链接。</span><span class="sxs-lookup"><span data-stu-id="85fd7-279">These scores are also links which are able to be used to skip to the relevant sections.</span></span>  <span data-ttu-id="85fd7-280">每个章节内有可展开的 `details`元素，这些元素包含与审核通过或失败有关的信息。</span><span class="sxs-lookup"><span data-stu-id="85fd7-280">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="85fd7-281">默认情况下，仅显示失败的审核。</span><span class="sxs-lookup"><span data-stu-id="85fd7-281">By default, only failing audits are shown.</span></span>  <span data-ttu-id="85fd7-282">每节以最后一个 `details` 元素结尾，该元素包含所有通过的审核。</span><span class="sxs-lookup"><span data-stu-id="85fd7-282">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="85fd7-283">若要运行新的审核，请使用 `Shift`+`Tab` 以退出报告并查找“**执行审核**”按钮。</span><span class="sxs-lookup"><span data-stu-id="85fd7-283">To run a new audit, use `Shift`+`Tab` to exit the report and look for the **Perform An Audit** button.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="85fd7-284">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="85fd7-284">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "辅助功能参考 | Microsoft 文档"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "辅助功能窗格 - 辅助功能参考 | Microsoft 文档"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令"  
[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 | Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md#view-dom-nodes“查看 DOM 节点 - 查看和更改 DOM 入门 | Microsoft 文档”  
<span data-ttu-id="85fd7-292">[DevtoolsDomindexexNaviDomGateKeyboard]： .。/dom/index.md#navigate-dom-tree-with-dom-tree-with-a-keyboard“使用键盘导航 DOM 树 - 查看和更改 DOM 入门 | Microsoft 文档”</span><span class="sxs-lookup"><span data-stu-id="85fd7-292">[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "Navigate the DOM Tree with a keyboard - Get started with viewing and changing the DOM | Microsoft Docs"</span></span>  
<span data-ttu-id="85fd7-293">[DevtoolsOpen]：./open/index.md“打开 Microsoft Edge 开发工具 | Microsoft 文档”</span><span class="sxs-lookup"><span data-stu-id="85fd7-293">[DevtoolsOpen]: ../open/index.md "Open Microsoft Edge DevTools | Microsoft Docs"</span></span>  
<span data-ttu-id="85fd7-294">[DevtoolsShortcuts]：.。/shortcuts/index.md“Microsoft Edge 开发工具键盘快捷方式 | Microsoft 文档”</span><span class="sxs-lookup"><span data-stu-id="85fd7-294">[DevtoolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"</span></span>  
<span data-ttu-id="85fd7-295">[DevtoolsShortcutsStylesPaneKeyboard]： ../shortcuts/index.md#styles-panel-keyboard-shortcuts "Styles panel keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts |Microsoft Docs"</span><span class="sxs-lookup"><span data-stu-id="85fd7-295">[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts/index.md#styles-panel-keyboard-shortcuts "Styles panel keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"</span></span>  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "问题 868480 - 在 Mac 辅助功能中以表的形式公开 ARIA 树"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新问题 - MicrosoftDocs/edge-developer - GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ":active | MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ":focus | MDN"  

[MonorailChromiumIssues]: https://crbug.com "问题 - chromium - Monorail"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "选项卡列表（角色） - 可访问的富 Internet 应用程序(WAI-ARIA) 1.1 | W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "树（角色） - 可访问的富 Internet 应用程序 (WAI-ARIA) 1.1 | W3C"  

> [!NOTE]
> <span data-ttu-id="85fd7-303">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="85fd7-303">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="85fd7-304">[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) 可查找原始页面，其作者为 [Rob Dodson][RobDodson] \（参与者，Google WebFoundamentals\）。</span><span class="sxs-lookup"><span data-stu-id="85fd7-304">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="85fd7-306">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="85fd7-306">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
