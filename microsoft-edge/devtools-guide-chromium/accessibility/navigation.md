---
title: 导航 Microsoft Edge DevTools 与辅助技术
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 544d6a6ecb8dabe262e7c28aa7fc072610604be0
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986053"
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

# <span data-ttu-id="b1a8c-103">导航 Microsoft Edge DevTools 与辅助技术</span><span class="sxs-lookup"><span data-stu-id="b1a8c-103">Navigate Microsoft Edge DevTools with assistive technology</span></span>  

<span data-ttu-id="b1a8c-104">以下文章旨在帮助主要依靠辅助技术（如屏幕阅读器）访问和使用 [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain]的用户。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-104">The following article aims to help users who primarily rely on assistive technology like screen readers access and use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span></span>  <span data-ttu-id="b1a8c-105">[Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] 是内置于 Microsoft edge 浏览器中的一套 web 开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-105">[Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  <span data-ttu-id="b1a8c-106">如果您要查找与改善网页辅助功能相关的 DevTools 功能，请参阅 [辅助功能参考][DevtoolsAccessibilityReference]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-106">If you are looking for DevTools features related to improving the accessibility of a web page,  see [Accessibility Reference][DevtoolsAccessibilityReference].</span></span>  

<span data-ttu-id="b1a8c-107">DevTools 的辅助功能是一个正在进行的工作。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-107">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="b1a8c-108">某些面板和选项卡比其他面板和选项卡更适用于辅助技术。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-108">Some panels and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="b1a8c-109">本指南将指导你完成最易于访问和突出显示你可能遇到的特定问题的面板。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-109">This guide walks you through the panels which are the most accessible and highlights specific issues you may encounter along the way.</span></span>  

## <span data-ttu-id="b1a8c-110">概述</span><span class="sxs-lookup"><span data-stu-id="b1a8c-110">Overview</span></span>  

<span data-ttu-id="b1a8c-111">在开始之前，它有助于获得有关 DevTools UI 的结构的心理模型。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-111">Before starting, it helps to have a mental model of how the DevTools UI is structured.</span></span>  <span data-ttu-id="b1a8c-112">DevTools 分为一系列的面板，这些面板分为一个 [ARIA tablist][W3CWaiAriaTablist]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-112">DevTools is divided into a series of panels which are organized into an [ARIA tablist][W3CWaiAriaTablist].</span></span>  

<span data-ttu-id="b1a8c-113">例如：</span><span class="sxs-lookup"><span data-stu-id="b1a8c-113">For example:</span></span>  

*   <span data-ttu-id="b1a8c-114">通过 " **元素** " 面板，你可以 [查看和更改 DOM 节点] [DevtoolsDomIndexNavigateDomTreeKeyboard] 或 [CSS][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-114">The **Elements** panel lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="b1a8c-115">[控制台面板][DevtoolsConsoleIndex]允许您读取 JavaScript 日志和实时编辑对象。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-115">The [Console panel][DevtoolsConsoleIndex] lets you read JavaScript logs and live edit objects.</span></span>  

<span data-ttu-id="b1a8c-116">在每个面板的内容区域内，有许多不同的工具，这些工具通常称为文档中的选项卡或窗格。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-116">Within the content area of each panel, there are a number of different tools, often referred to as tabs or panes in the documentation.</span></span>  
<span data-ttu-id="b1a8c-117">例如，" **元素** " 面板包含用于检查事件侦听器、辅助功能树以及更多的其他选项卡。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-117">For instance, the **Elements** panel contains additional tabs to inspect event listeners, the accessibility tree, and much more.</span></span>  <span data-ttu-id="b1a8c-118">选项卡和窗格之间的区别稍有不同。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-118">The distinction between tabs and panes is somewhat arbitrary.</span></span>  <span data-ttu-id="b1a8c-119">你可能看到一个术语或另一个术语的唯一原因是与官方 DevTools 文档的其余部分保持一致。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-119">The only reason you may see one term or the other is to maintain consistency with the rest of the official DevTools documentation.</span></span>  

## <span data-ttu-id="b1a8c-120">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="b1a8c-120">Keyboard shortcuts</span></span>  

<span data-ttu-id="b1a8c-121">[DevTools 键盘快捷方式参考] [DevtoolsShortcuts] 是一个非常有用的 cheatsheet。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-121">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.</span></span>  <span data-ttu-id="b1a8c-122">在浏览不同的面板时，请务必将其加入书签并重新引用它。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-122">Be sure to bookmark it and refer back to it as you explore the different panels.</span></span>  

## <span data-ttu-id="b1a8c-123">打开开发工具</span><span class="sxs-lookup"><span data-stu-id="b1a8c-123">Open DevTools</span></span>  

<span data-ttu-id="b1a8c-124">若要开始使用，请参阅 [打开 Microsoft Edge DevTools] [DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-124">To get started, see [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="b1a8c-125">有多种方法可以打开 DevTools，方法是通过键盘快捷方式或菜单项打开。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-125">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <span data-ttu-id="b1a8c-126">在面板之间导航</span><span class="sxs-lookup"><span data-stu-id="b1a8c-126">Navigate between panels</span></span>  

### <span data-ttu-id="b1a8c-127">通过键盘导航</span><span class="sxs-lookup"><span data-stu-id="b1a8c-127">Navigate by keyboard</span></span>  

*   <span data-ttu-id="b1a8c-128">在 DevTools 打开的情况下，选择 `Control` + `]` \ (Windows \ ) 或 `Command` + `]` \ (macOS \ ) 以重点关注下一个面板。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-128">With DevTools open, select `Control`+`]` \(Windows\) or `Command`+`]` \(macOS\) to focus the next panel.</span></span>  
*   <span data-ttu-id="b1a8c-129">选择 `Control` + `[` \ (Windows \ ) 或 `Command` + `[` \ (macOS \ ) 以重点介绍上一个面板。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-129">Select `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) to focus the previous panel.</span></span>  
*   <span data-ttu-id="b1a8c-130">也可以使用将 `Shift` + `Tab` 焦点移动到面板的[ARIA tablist][W3CWaiAriaTablist]中并使用箭头键更改面板，但使用前面提到的快捷方式可能会更快。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-130">It is also possible to use `Shift`+`Tab` to move focus into the [ARIA tablist][W3CWaiAriaTablist] of a panel and use the arrow keys to change panels, though it may be faster to use the previously mentioned shortcuts.</span></span>  

**<span data-ttu-id="b1a8c-131">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-131">Known issues</span></span>**  

*   <span data-ttu-id="b1a8c-132">在每个面板激活后，某些面板（如 " **控制台** " 和 " **性能** " 面板）可能会将焦点移到 "面板内容" 区域。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-132">Some panels, such as the **Console** and **Performance** panels, may move focus into the panel content area as soon as each panel is activated.</span></span>  <span data-ttu-id="b1a8c-133">这可能导致很难通过箭头键进行导航。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-133">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="b1a8c-134">将宣布所选面板的名称，但仅在它已阅读面板中的焦点内容后才会。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-134">The name of the selected panel is announced, but only after it has read the focused content in the panel.</span></span>  <span data-ttu-id="b1a8c-135">这可能会使错过的事情变得非常容易。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-135">This may make it very easy to miss.</span></span>  

### <span data-ttu-id="b1a8c-136">通过命令菜单导航</span><span class="sxs-lookup"><span data-stu-id="b1a8c-136">Navigate by Command Menu</span></span>  

<span data-ttu-id="b1a8c-137">若要聚焦特定面板，请使用 " [命令" 菜单][DevtoolsCommandMenuIndex]：</span><span class="sxs-lookup"><span data-stu-id="b1a8c-137">To focus a specific panel, use the [Command Menu][DevtoolsCommandMenuIndex]:</span></span>  

1.  <span data-ttu-id="b1a8c-138">在 DevTools 打开的情况下，选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-138">With DevTools open, select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="b1a8c-139">**命令菜单**是模糊搜索记忆式键入 combobox。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-139">The **Command Menu** is a fuzzy search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="b1a8c-140">键入要打开的面板的名称，然后使用键盘上的 " `Down Arrow` 导航到正确的" 选项。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-140">Type the name of the panel you want to open, then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="b1a8c-141">选择 `Enter` 以运行命令。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-141">Select `Enter` to run a command.</span></span>  

<span data-ttu-id="b1a8c-142">完成以下操作以打开 " **元素** " 面板。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-142">Complete the following actions to open the **Elements** panel.</span></span>  

1.  <span data-ttu-id="b1a8c-143">打开 " **命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-143">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="b1a8c-144">`E`然后键入 `L` 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-144">Type `E` then `L`.</span></span>  <span data-ttu-id="b1a8c-145">**"面板 > 显示元素**" 选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-145">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="b1a8c-146">选择 `Enter` 以运行打开面板的命令。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-146">Select `Enter` to run the command that opens the panel.</span></span>  

<span data-ttu-id="b1a8c-147">以这种方式打开面板，将焦点定向到面板的内容。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-147">Open a panel this way directs focus to the contents of the panel.</span></span>  <span data-ttu-id="b1a8c-148">在 " **元素** " 面板的情况下，焦点移到 **DOM 树**中。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-148">In the case of the **Elements** panel, focus moves into the **DOM Tree**.</span></span>  

## <span data-ttu-id="b1a8c-149">元素面板</span><span class="sxs-lookup"><span data-stu-id="b1a8c-149">Elements panel</span></span>  

### <span data-ttu-id="b1a8c-150">检查页面上的元素</span><span class="sxs-lookup"><span data-stu-id="b1a8c-150">Inspect an element on the page</span></span>  

1.  <span data-ttu-id="b1a8c-151">使用屏幕阅读器中的光标导航到要检查的元素。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-151">Navigate to the element you want to inspect using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="b1a8c-152">在元素上使用鼠标进行右键单击以打开上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-152">Simulate a right-click using a mouse on the element to open the context menu.</span></span>  
1.  <span data-ttu-id="b1a8c-153">选择 " **检查** " 选项。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-153">Choose the **Inspect** option.</span></span>  <span data-ttu-id="b1a8c-154">此 [打开元素面板并聚焦 DOM 树中的元素] [DevtoolsDomIndexViewDomNodes]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-154">This [opens the Elements panel and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span></span>  

<span data-ttu-id="b1a8c-155">**DOM 树**布局为[ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-155">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="b1a8c-156">有关示例，请参阅 [使用键盘导航 **DOM 树** ] [DevtoolsDomIndexNavigateDomTreeKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-156">For an example, see [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span></span>  

### <span data-ttu-id="b1a8c-157">复制 DOM 树中元素的代码</span><span class="sxs-lookup"><span data-stu-id="b1a8c-157">Copy the code for an element in the DOM Tree</span></span>  

1.  <span data-ttu-id="b1a8c-158">当焦点位于 **DOM 树**中的某个节点上时，将鼠标悬停在节点上并打开上下文菜单 \ (右键单击 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-158">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="b1a8c-159">展开 " **复制** " 选项。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-159">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="b1a8c-160">选择 " **复制 outerHTML**"。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-160">Select **Copy outerHTML**.</span></span>  

**<span data-ttu-id="b1a8c-161">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-161">Known issues</span></span>**  

*   <span data-ttu-id="b1a8c-162">**复制 outerHTML** 通常不选择当前节点，而是选择父节点。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-162">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="b1a8c-163">但是，该元素的内容应仍在已复制的 outerHTML 中。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-163">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <span data-ttu-id="b1a8c-164">在 DOM 树中修改元素的属性</span><span class="sxs-lookup"><span data-stu-id="b1a8c-164">Modify the attributes of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="b1a8c-165">将焦点置于 **DOM 树**中的某个节点上，然后选择 `Enter` 以使其可编辑。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-165">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="b1a8c-166">选择 `Tab` 以在属性值之间移动。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-166">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="b1a8c-167">当你听到 "space" 时，你位于空的文本输入中，并且能够键入新的属性值。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-167">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="b1a8c-168">选择 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) ，接受更改并收听该元素的所有内容。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-168">Select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

**<span data-ttu-id="b1a8c-169">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-169">Known issues</span></span>**  

*   <span data-ttu-id="b1a8c-170">键入文本输入时，您不会收到任何反馈。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-170">When you type into the text input you get no feedback.</span></span>  <span data-ttu-id="b1a8c-171">如果你进行了键入错误，并使用箭头键浏览你的输入，你也不会收到任何反馈。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-171">If you make a typo and use the arrow keys to explore your input you also get no feedback.</span></span>  <span data-ttu-id="b1a8c-172">检查工作的最简单方法是接受更改，然后侦听要宣布的整个元素。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-172">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <span data-ttu-id="b1a8c-173">在 DOM 树中编辑元素的 HTML</span><span class="sxs-lookup"><span data-stu-id="b1a8c-173">Edit the HTML of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="b1a8c-174">将焦点置于 **DOM 树**中的某个节点上，然后选择 `Enter` 以使其可编辑。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-174">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="b1a8c-175">选择 `Tab` 以在属性值之间移动。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-175">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="b1a8c-176">例如，当听到元素的名称（例如，在 `h2` 文本输入中）时，可能会更改元素的类型。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-176">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="b1a8c-177">选择 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 以接受更改。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-177">Select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="b1a8c-178">例如，当你键入 `h3` 并选择 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 时，元素的开始和结束标记会 `h3` 发生更改。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-178">For example, when you type `h3` and select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span></span>  

## <span data-ttu-id="b1a8c-179">"元素" 面板选项卡</span><span class="sxs-lookup"><span data-stu-id="b1a8c-179">Elements panel tabs</span></span>  

<span data-ttu-id="b1a8c-180">" **元素** " 面板包含用于检查内容的其他选项卡，例如应用于某个元素的 CSS 或 "辅助功能" 树中的相关位置。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-180">The **Elements** panel contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="b1a8c-181">将焦点置于 **DOM 树**中的某个节点上，选择， `Tab` 直到听到 " **样式** " 窗格处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-181">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** pane is selected.</span></span>  
*   <span data-ttu-id="b1a8c-182">使用 `Right Arrow` 浏览其他可用的选项卡。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-182">Use the `Right Arrow` to explore other available tabs.</span></span>  

<span data-ttu-id="b1a8c-183">**DOM 树**将具有属性的元素 `href` 转换为可设定焦点的链接，因此你可能需要选择多次 `Tab` 才能到达 "**样式**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-183">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span></span>  

**<span data-ttu-id="b1a8c-184">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-184">Known issues</span></span>**  

<span data-ttu-id="b1a8c-185">" **DOM 断点** " 和 " **属性** " 选项卡不能通过键盘访问。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-185">The **DOM Breakpoints** and **Properties** tabs are not keyboard accessible.</span></span>  

### <span data-ttu-id="b1a8c-186">"样式" 窗格</span><span class="sxs-lookup"><span data-stu-id="b1a8c-186">Styles pane</span></span>  

<span data-ttu-id="b1a8c-187">在 " **样式** " 窗格中，查找用于筛选样式的控件，切换元素状态 \ (例如 [： "活动][MDNActive] " 和 [： "焦点][MDNFocus]\" ) 、切换类以及添加新类。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-187">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="b1a8c-188">还有一个功能强大的样式检查工具，可用于浏览和修改当前应用于 **DOM 树**中焦点的元素的样式。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-188">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="b1a8c-189">了解 " **样式** " 窗格的关键概念是它仅显示 **DOM 树**中当前选定的节点的样式。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-189">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="b1a8c-190">例如，假设你已检查完节点的样式 `<header>` ，现在想要查看节点的样式 `<footer>` 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-190">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="b1a8c-191">若要执行此操作，首先需要选择 `<footer>` **DOM 树**中的节点。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-191">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="b1a8c-192">你可能会发现使用 " [检查](#inspect-an-element-on-the-page) 工作流" 来检查节点的常规邻近 `footer` 节点 \ (（如页脚中的链接 \ ) ，它侧重于 **DOM 树**），然后使用键盘导航到你感兴趣的确切节点。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-192">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <span data-ttu-id="b1a8c-193">导航 "样式" 窗格</span><span class="sxs-lookup"><span data-stu-id="b1a8c-193">Navigate the Styles pane</span></span>  

<span data-ttu-id="b1a8c-194">因为所有样式工具都以一种方式进行连接，而另一种方式是返回到 " **样式** " 窗格，所以在此工具中首先成为专家是有意义的。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-194">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span></span>  

*   <span data-ttu-id="b1a8c-195">将焦点置于 " **样式** " 窗格上，选择 `Tab` 以将焦点移动到其中并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-195">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="b1a8c-196">选择 `Tab` ，直到第一个样式变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-196">Select `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="b1a8c-197">如果您使用的是屏幕阅读器，则第一个样式将宣布为 `element.style {}` 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-197">If you are using a screen reader this first style is announced as `element.style {}`.</span></span>  
*   <span data-ttu-id="b1a8c-198">选择 `Down Arrow` 以按升序顺序导航样式列表。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-198">Select `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="b1a8c-199">屏幕阅读器将从 CSS 文件的名称、出现样式的行号以及样式的名称开始宣布每个样式。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-199">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="b1a8c-200">例如，`main.css:233 .card__img {}`。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-200">For example, `main.css:233 .card__img {}`.</span></span>  
*   <span data-ttu-id="b1a8c-201">选择 `Enter` 以更详细地检查样式。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-201">Select `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="b1a8c-202">焦点从样式名称的可编辑版本开始。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-202">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="b1a8c-203">选择 `Tab` 以在每个 CSS 属性的可编辑版本和相应值之间移动。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-203">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span></span>  <span data-ttu-id="b1a8c-204">每个样式块的结尾是一个空白的可编辑文本字段，可用于添加其他 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-204">At the end of each style block is a blank editable text field which you may use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="b1a8c-205">你可以继续选择在 `Tab` 样式列表中移动，或选择 `Escape` 退出模式并返回到通过箭头键导航。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-205">You may continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="b1a8c-206">有关其他快捷方式，请参阅 [样式窗格键盘参考] [DevtoolsShortcutsStylesPaneKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-206">For additional shortcuts, see [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span></span>  

**<span data-ttu-id="b1a8c-207">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-207">Known issues</span></span>**  

*   <span data-ttu-id="b1a8c-208">如果使用 " **筛选器** 可编辑文本" 字段，则无法再导航样式列表。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-208">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <span data-ttu-id="b1a8c-209">切换元素状态</span><span class="sxs-lookup"><span data-stu-id="b1a8c-209">Toggle element state</span></span>  

<span data-ttu-id="b1a8c-210">切换元素的状态，例如 `:active` 或 `:focus` ：</span><span class="sxs-lookup"><span data-stu-id="b1a8c-210">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="b1a8c-211">导航到 " **样式** " 窗格，然后选择 `Tab` " **切换元素状态** " 按钮获得焦点。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-211">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="b1a8c-212">选择 `Enter` 以展开元素状态的集合。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-212">Select `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="b1a8c-213">元素状态显示为一组复选框。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-213">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="b1a8c-214">选择 " `Tab` 直到第一个状态" `:active` ，"有焦点"。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-214">Select `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="b1a8c-215">选择 `Space` 以启用它。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-215">Select `Space` to enable it.</span></span>  <span data-ttu-id="b1a8c-216">如果 DOM 树中的当前选定元素具有 `:active` 样式，则现在将其应用。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-216">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="b1a8c-217">"保持" `Tab` 以浏览所有可用状态。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-217">Hold `Tab` to explore all of the available states.</span></span>  

#### <span data-ttu-id="b1a8c-218">添加现有类</span><span class="sxs-lookup"><span data-stu-id="b1a8c-218">Add an existing class</span></span>  

<span data-ttu-id="b1a8c-219">" **切换元素状态** " 按钮旁边是 " **元素类** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-219">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="b1a8c-220">若要将焦点移动到该文件，请选择 `Tab` 并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-220">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="b1a8c-221">焦点移到标记为 " **添加新类**" 的编辑文本字段中。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-221">Focus moves into an edit text field labeled **Add New Class**.</span></span>  

<span data-ttu-id="b1a8c-222">**元素类**按钮主要用于将现有类添加到元素。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-222">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="b1a8c-223">例如，如果你的样式表包含名为的帮助程序类，则 `.clearfix` 可以在 `.` "编辑文本" 字段中选择以查看类的建议列表，并使用 `Down Arrow` 查找 `.clearfix` 建议。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-223">For example, if your stylesheet contained a helper class named `.clearfix` you may select `.` inside of the edit text field to see a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="b1a8c-224">或者键入类名，然后选择 `Enter` 应用。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-224">Or type the class name out yourself and select `Enter` to apply it.</span></span>  

#### <span data-ttu-id="b1a8c-225">添加新样式规则</span><span class="sxs-lookup"><span data-stu-id="b1a8c-225">Add a new style rule</span></span>  

<span data-ttu-id="b1a8c-226">" **元素类** " 按钮旁边是 " **新建样式规则** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-226">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="b1a8c-227">若要将焦点移动到该文件，请选择 `Tab` 并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-227">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="b1a8c-228">焦点移到 "样式" 检查器内的可编辑文本字段中。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-228">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="b1a8c-229">字段的初始文本内容是 **DOM 树**中所选元素的标记名称。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-229">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="b1a8c-230">你可以在此字段中键入所需的任何类名称，然后选择 `Tab` 将 CSS 属性分配给该字段。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-230">You may type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span></span>  

### <span data-ttu-id="b1a8c-231">计算选项卡</span><span class="sxs-lookup"><span data-stu-id="b1a8c-231">Computed tab</span></span>  

<span data-ttu-id="b1a8c-232">将焦点置于 " **计算** " 选项卡上，选择 `Tab` 以将焦点移动到其中并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-232">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="b1a8c-233">在 " **计算** " 选项卡中有一些控件，用于探索哪些 CSS 属性实际应用于某个元素的具体程度。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-233">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add computed tab section when available  -->  

#### <span data-ttu-id="b1a8c-234">浏览所有计算样式</span><span class="sxs-lookup"><span data-stu-id="b1a8c-234">Explore all computed styles</span></span>  

<span data-ttu-id="b1a8c-235">选择 `Tab` ，直到到达计算样式的集合。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-235">Select `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="b1a8c-236">它们显示为一个 [ARIA 树][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-236">These are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="b1a8c-237">展开 listbox 将显示哪些 CSS 选择器应用了计算样式。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-237">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="b1a8c-238">这些选择程序按具体程度进行组织。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-238">These selectors are organized by specificity.</span></span>  <span data-ttu-id="b1a8c-239">屏幕阅读器宣布计算值、当前匹配的 CSS 选择器、包含选择器的样式表的文件名以及选择器的行号。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-239">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

**<span data-ttu-id="b1a8c-240">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-240">Known issues</span></span>**  

*   <span data-ttu-id="b1a8c-241">如果使用 " **筛选** 文本" 字段，则无法再检查样式。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-241">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <span data-ttu-id="b1a8c-242">事件侦听器选项卡</span><span class="sxs-lookup"><span data-stu-id="b1a8c-242">Event listeners tab</span></span>  

<span data-ttu-id="b1a8c-243">在 " **元素** " 面板中，你可以使用 " **事件侦听器** " 选项卡检查应用到元素的事件侦听器。 将焦点置于 " **样式** " 窗格上，选择 `Right Arrow` 导航到 " **事件侦听器** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-243">From within the **Elements** panel you may inspect the event listeners applied to an element using the **Event Listeners** tab.  With focus on the **Styles** pane, select the `Right Arrow` to navigate to the **Event Listeners** tab.</span></span>  

#### <span data-ttu-id="b1a8c-244">浏览事件侦听器</span><span class="sxs-lookup"><span data-stu-id="b1a8c-244">Explore event listeners</span></span>  

<span data-ttu-id="b1a8c-245">事件侦听器以 [ARIA 树][W3CWaiAriaTree]的形式呈现。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-245">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="b1a8c-246">你可以使用箭头键进行导航。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-246">You may use the arrow keys to navigate them.</span></span>  <span data-ttu-id="b1a8c-247">屏幕阅读器将宣布事件侦听器附加到的 DOM 对象的名称，以及定义事件侦听器和行号的文件名。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-247">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <span data-ttu-id="b1a8c-248">辅助功能窗格</span><span class="sxs-lookup"><span data-stu-id="b1a8c-248">Accessibility pane</span></span>  

<span data-ttu-id="b1a8c-249">焦点位于 " **辅助功能** " 窗格上，选择 `Tab` 以将焦点移动到其中并浏览内容。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-249">With focus on the **Accessibility** pane, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="b1a8c-250">在 " [辅助功能" 窗格][DevtoolsAccessibilityReference] 中，有用于浏览辅助功能树、应用于元素的 ARIA 属性和计算的辅助功能属性的控件。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-250">On the [Accessibility pane][DevtoolsAccessibilityReference] there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  

#### <span data-ttu-id="b1a8c-251">辅助功能树</span><span class="sxs-lookup"><span data-stu-id="b1a8c-251">Accessibility Tree</span></span>  

<span data-ttu-id="b1a8c-252">**辅助功能树**显示为一个[ARIA 树][W3CWaiAriaTree]，其中每个树都 `treeitem` 对应于 DOM 中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-252">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="b1a8c-253">树宣布所选节点的已计算角色。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-253">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="b1a8c-254">类中的泛型元素（如 `div` 和 `span` ）在树中被宣布为 "GenericContainer"。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-254">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="b1a8c-255">使用箭头键遍历树并浏览父子关系。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-255">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

**<span data-ttu-id="b1a8c-256">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-256">Known issues</span></span>**  

*   <span data-ttu-id="b1a8c-257">**辅助功能**窗格使用的[ARIA 树][W3CWaiAriaTree]的类型可能无法在 Microsoft Edge 中正确地向 macOS 屏幕阅读器（如 VoiceOver）公开。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-257">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** pane may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="b1a8c-258">订阅 [Chromium 问题 #868480][ChromiumIssues868480] 将收到有关此问题的进度。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-258">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="b1a8c-259">每个 **ARIA 属性** 和 **计算属性** 部分均标记为一个 [ARIA 树][W3CWaiAriaTree]，但每个都不是焦点管理，并且不是键盘可操作。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-259">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <span data-ttu-id="b1a8c-260">审核面板</span><span class="sxs-lookup"><span data-stu-id="b1a8c-260">Audits panel</span></span>  

<span data-ttu-id="b1a8c-261">" **审核** " 面板你应该针对网站运行一系列测试，以检查与性能、辅助功能、SEO 以及许多其他类别相关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-261">The **Audits** panel you should run a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <span data-ttu-id="b1a8c-262">配置和运行审核</span><span class="sxs-lookup"><span data-stu-id="b1a8c-262">Configure and run an audit</span></span>  

1.  <span data-ttu-id="b1a8c-263">首次打开 " **审核** " 面板时，焦点将放置在窗体末尾的 " **运行审核** " 按钮上。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-263">When the **Audits** panel is first opened, focus is placed on the **Run Audit** button at the end of the form.</span></span>  <span data-ttu-id="b1a8c-264">默认情况下，该窗体配置为对模拟的3G 连接上的每个类别使用 "移动仿真" 运行审核。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-264">By default the form is configured to run audits for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="b1a8c-265">`Shift` + `Tab` 在浏览模式下使用或向后导航以更改审核设置。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-265">Use `Shift`+`Tab` or navigate back in Browse mode to change the audit settings.</span></span>  
1.  <span data-ttu-id="b1a8c-266">准备好运行审核时，请导航回 " **运行审核** " 按钮并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-266">When you are ready to run the audit, navigate back to the **Run Audit** button and select `Enter`.</span></span>  
1.  <span data-ttu-id="b1a8c-267">焦点将移动到带有 " **取消** " 按钮的模式窗口，使您可以退出审核。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-267">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="b1a8c-268">当审核运行并多次刷新页面时，你可能会听到一系列 earcons。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-268">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

**<span data-ttu-id="b1a8c-269">已知问题</span><span class="sxs-lookup"><span data-stu-id="b1a8c-269">Known issues</span></span>**  

*   <span data-ttu-id="b1a8c-270">配置窗体的不同部分当前不与元素一起标记 `fieldset` 。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-270">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="b1a8c-271">在浏览模式中导航以确定与每个部分关联的控件可能更容易。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-271">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="b1a8c-272">审核完成运行时，没有 earcon 或活动区域公告。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-272">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="b1a8c-273">通常需要30秒，之后才能导航到结果。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-273">Generally it takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="b1a8c-274">使用浏览模式可能是达到结果的最简单方式。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-274">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <span data-ttu-id="b1a8c-275">导航审核报告</span><span class="sxs-lookup"><span data-stu-id="b1a8c-275">Navigate the audit report</span></span>  

<span data-ttu-id="b1a8c-276">审核报告已组织为与每个审核类别对应的分区。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-276">The audit report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="b1a8c-277">将打开报表，其中包含每个类别的分数列表。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-277">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="b1a8c-278">这些分数也是可以用于跳转到相关部分的链接。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-278">These scores are also links which are able to be used to skip to the relevant sections.</span></span>  <span data-ttu-id="b1a8c-279">在每个部分中都是可扩展 `details` 元素，其中包含与已通过或失败的审核相关的信息。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-279">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="b1a8c-280">默认情况下，仅显示失败的审核。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-280">By default, only failing audits are shown.</span></span>  <span data-ttu-id="b1a8c-281">每个部分都以 `details` 包含所有已传递审核的最终元素结尾。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-281">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="b1a8c-282">若要运行新审核，请使用 `Shift` + `Tab` 退出报告并查找 "**执行审核**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-282">To run a new audit, use `Shift`+`Tab` to exit the report and look for the **Perform An Audit** button.</span></span>  

## <span data-ttu-id="b1a8c-283">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="b1a8c-283">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "辅助功能参考 |Microsoft 文档"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "辅助功能窗格-辅助功能参考 |Microsoft 文档"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 |Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md # view-dom-节点 "查看 DOM 节点-开始查看和更改 DOM |Microsoft 文档 "  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md # "导航"-dom 树-带键盘 "使用键盘浏览 DOM"-开始查看和更改 DOM |Microsoft 文档 "  
[DevtoolsOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档 "  
[DevtoolsShortcuts]: ../shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档 "  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md # 样式-窗格-键盘快捷方式 "样式窗格" 键盘快捷方式-Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档 "  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "问题 868480-将 ARIA 树作为 Mac 辅助功能中的表公开"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新问题-MicrosoftDocs/edge-开发人员 |GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active "：活动 |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus "：焦点 |MDN"  

[MonorailChromiumIssues]: https://crbug.com "问题-chromium-Monorail"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (角色) -易于访问的富 Internet 应用 (WAI-ARIA-ARIA) 1.1 |W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "树 (角色) -易于访问的富 Internet 应用程序 (WAI-ARIA) 1.1 |W3C"  

> [!NOTE]
> <span data-ttu-id="b1a8c-302">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-302">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b1a8c-303">原始页面在[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation)找到，并且由 "Dodson" （ ([Rob Dodson][RobDodson] ）投稿人、Google WebFundamentals \ ) 创作。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-303">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b1a8c-305">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b1a8c-305">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
