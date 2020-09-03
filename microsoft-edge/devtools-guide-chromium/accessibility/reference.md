---
description: Microsoft Edge DevTools 中的辅助功能的全面参考。
title: 辅助功能参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 39b0b8c36cea017b9976ea4e80e92ea93896a671
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993266"
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

# <span data-ttu-id="13750-104">辅助功能参考</span><span class="sxs-lookup"><span data-stu-id="13750-104">Accessibility reference</span></span>  

<span data-ttu-id="13750-105">此页面是 Microsoft Edge DevTools 中辅助功能的完整参考。</span><span class="sxs-lookup"><span data-stu-id="13750-105">This page is a comprehensive reference of accessibility features in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="13750-106">它适用于以下情况的 web 开发人员：</span><span class="sxs-lookup"><span data-stu-id="13750-106">It is intended for web developers who:</span></span>  

*   <span data-ttu-id="13750-107">对 DevTools 有一个基本的理解，例如如何将其打开。</span><span class="sxs-lookup"><span data-stu-id="13750-107">Have a basic understanding of DevTools, such as how to open it.</span></span>  
*   <span data-ttu-id="13750-108">熟悉 [辅助功能原则和最佳做法][MDNAccessibility]。</span><span class="sxs-lookup"><span data-stu-id="13750-108">Are familiar with [accessibility principles and best practices][MDNAccessibility].</span></span>  
    
<span data-ttu-id="13750-109">本参考旨在帮助你发现 DevTools 中提供的所有工具，这些工具可帮助你检查页面的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="13750-109">The purpose of this reference is to help you discover all of the tools available in DevTools that help you examine the accessibility of a page.</span></span>  

<span data-ttu-id="13750-110">如果要查找有关使用辅助技术（如屏幕阅读器）导航 DevTools 的帮助，请参阅 [使用辅助技术导航 Microsoft Edge DevTools][DevtoolsAccessibilityNavigation] 。</span><span class="sxs-lookup"><span data-stu-id="13750-110">See [Navigating Microsoft Edge DevTools With Assistive Technology][DevtoolsAccessibilityNavigation] if you are looking for help on navigating DevTools with an assistive technology like a screen reader.</span></span>  

## <span data-ttu-id="13750-111">Microsoft Edge DevTools 中辅助功能的概述</span><span class="sxs-lookup"><span data-stu-id="13750-111">Overview of accessibility features in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="13750-112">本部分介绍 DevTools 如何融入你的整体辅助功能工具包。</span><span class="sxs-lookup"><span data-stu-id="13750-112">This section explains how DevTools fits into your overall accessibility toolkit.</span></span>  

<span data-ttu-id="13750-113">确定页面是否可访问时，需要考虑两个常见问题：</span><span class="sxs-lookup"><span data-stu-id="13750-113">When determining whether a page is accessible, you need to have 2 general questions in mind:</span></span>  

1.  <span data-ttu-id="13750-114">是否可以使用键盘或 [屏幕阅读器][MDNScreenReader]导航页面？</span><span class="sxs-lookup"><span data-stu-id="13750-114">Are you able to navigate the page with a keyboard or [screen reader][MDNScreenReader]?</span></span>  
1.  <span data-ttu-id="13750-115">页面元素是否已正确标记为屏幕阅读器？</span><span class="sxs-lookup"><span data-stu-id="13750-115">Are the elements of the page properly marked up for screen readers?</span></span>  
    
<span data-ttu-id="13750-116">通常，DevTools 应帮助你修复与 #2 问题相关的错误，因为这些错误非常容易以自动方式进行检测。</span><span class="sxs-lookup"><span data-stu-id="13750-116">In general, DevTools should help you fix errors related to question #2, because these errors are easy to detect in an automated fashion.</span></span>  <span data-ttu-id="13750-117">问题 #1 同样重要，但很遗憾，DevTools 不会对您有所帮助。</span><span class="sxs-lookup"><span data-stu-id="13750-117">Question #1 is just as important, but unfortunately DevTools does not help you there.</span></span>  <span data-ttu-id="13750-118">查找与问题相关的错误的唯一方式 #1 是尝试自己在页面上使用键盘或屏幕阅读器。</span><span class="sxs-lookup"><span data-stu-id="13750-118">The only way to find errors related to question #1 is to try using a page with a keyboard or screen reader yourself.</span></span>  <!--See [How To Do An Accessibility Review][AccessibilityReview] to learn more.  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <span data-ttu-id="13750-119">审核页面的辅助功能</span><span class="sxs-lookup"><span data-stu-id="13750-119">Audit the accessibility of a page</span></span>  

> [!NOTE]
> <span data-ttu-id="13750-120">" **审核** " 面板提供了指向第三方网站上托管的内容的链接。</span><span class="sxs-lookup"><span data-stu-id="13750-120">The **Audits** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="13750-121">Microsoft 不承担任何责任，也不能控制这些网站的内容和可能收集的任何数据。</span><span class="sxs-lookup"><span data-stu-id="13750-121">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span></span>  

<span data-ttu-id="13750-122">一般情况下，使用 "审核" 面板确定是否：</span><span class="sxs-lookup"><span data-stu-id="13750-122">In general, use the Audits panel to determine if:</span></span>  

*   <span data-ttu-id="13750-123">已正确标记屏幕阅读器的页面。</span><span class="sxs-lookup"><span data-stu-id="13750-123">A page is properly marked up for screen readers.</span></span>  
*   <span data-ttu-id="13750-124">页面上的文本元素具有足够的对比度比率。</span><span class="sxs-lookup"><span data-stu-id="13750-124">The text elements on a page have sufficient contrast ratios.</span></span>  <span data-ttu-id="13750-125">请参阅 [查看颜色选取器中的文本元素的对比度](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)。</span><span class="sxs-lookup"><span data-stu-id="13750-125">See [View the contrast ratio of a text element in the Color Picker](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker).</span></span>  

<span data-ttu-id="13750-126">若要审核页面，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13750-126">To audit a page:</span></span>  

1.  <span data-ttu-id="13750-127">转到要审核的 URL。</span><span class="sxs-lookup"><span data-stu-id="13750-127">Go to the URL that you want to audit.</span></span>  
1.  <span data-ttu-id="13750-128">在 DevTools 中，单击 " **审核** " 选项卡。 DevTools 显示了各种配置选项。</span><span class="sxs-lookup"><span data-stu-id="13750-128">In DevTools, click the **Audits** tab.  DevTools shows you various configuration options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="配置审核" lightbox="../media/accessibility-audits-pane.msft.png":::
       <span data-ttu-id="13750-130">配置审核</span><span class="sxs-lookup"><span data-stu-id="13750-130">Configure audits</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="13750-131">本部分中的屏幕截图是使用版本79的 Microsoft Edge 所得到的。</span><span class="sxs-lookup"><span data-stu-id="13750-131">The screenshots in this section were taken with version 79 of Microsoft Edge.</span></span>  <span data-ttu-id="13750-132">你可以检查你正在运行的版本 `edge://version` 。</span><span class="sxs-lookup"><span data-stu-id="13750-132">You may check what version you are running at `edge://version`.</span></span>  <span data-ttu-id="13750-133">" **审核** " 面板 UI 在早期版本的 Microsoft Edge 中看起来有所不同，但常规工作流是相同的。</span><span class="sxs-lookup"><span data-stu-id="13750-133">The **Audits** panel UI looks different in earlier versions of Microsoft Edge, but the general workflow is the same.</span></span>  
    
1.  <span data-ttu-id="13750-134">对于 " **设备**"，如果要模拟移动设备，请选择 " **移动** "。</span><span class="sxs-lookup"><span data-stu-id="13750-134">For **Device**, select **Mobile** if you want to simulate a mobile device.</span></span>  <span data-ttu-id="13750-135">此选项将更改你的用户代理字符串并调整视区的大小。</span><span class="sxs-lookup"><span data-stu-id="13750-135">This option changes your user agent string and resizes the viewport.</span></span>  <span data-ttu-id="13750-136">如果页面的移动版本显示不同于桌面版本，此选项可能会对审核结果产生显著影响。</span><span class="sxs-lookup"><span data-stu-id="13750-136">If the mobile version of the page displays differently than the desktop version, this option could have a significant effect on the results of your audit.</span></span>  
1.  <span data-ttu-id="13750-137">在 " **审核** " 部分中，确保已启用 **辅助功能** 。</span><span class="sxs-lookup"><span data-stu-id="13750-137">In the **Audits** section, make sure that **Accessibility** is enabled.</span></span>  <span data-ttu-id="13750-138">如果要从报表中排除其他类别，请禁用其他类别。</span><span class="sxs-lookup"><span data-stu-id="13750-138">Disable the other categories if you want to exclude them from your report.</span></span>  <span data-ttu-id="13750-139">如果想要发现提高页面质量的其他方法，请将其保留为启用状态。</span><span class="sxs-lookup"><span data-stu-id="13750-139">Leave them enabled if you want to discover other ways to improve the quality of your page.</span></span>  
1.  <span data-ttu-id="13750-140">**限制**部分允许你阻止网络和 CPU，这在分析负载性能时非常有用。</span><span class="sxs-lookup"><span data-stu-id="13750-140">The **Throttling** section lets you throttle the network and CPU, which is useful when analyzing load performance.</span></span>  <span data-ttu-id="13750-141">此选项应与你的辅助功能分数无关，因此你可以使用你喜欢的任何内容。</span><span class="sxs-lookup"><span data-stu-id="13750-141">This option should be irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="13750-142">" **清除存储** " 复选框允许你在加载页面之前清除所有存储空间，或在页面加载之间保留存储。</span><span class="sxs-lookup"><span data-stu-id="13750-142">The **Clear Storage** checkbox lets you clear all storage before loading the page, or preserve storage between page loads.</span></span>  <span data-ttu-id="13750-143">此选项也可能与你的辅助功能分数不相关，因此你可以使用你喜欢的任何内容。</span><span class="sxs-lookup"><span data-stu-id="13750-143">This option is also probably irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="13750-144">单击 " **运行审核**"。</span><span class="sxs-lookup"><span data-stu-id="13750-144">Click **Run Audits**.</span></span> <span data-ttu-id="13750-145">10到30秒后，DevTools 将提供一个报表。</span><span class="sxs-lookup"><span data-stu-id="13750-145">After 10 to 30 seconds, DevTools provides a report.</span></span>  <span data-ttu-id="13750-146">你的报表提供了有关如何改进页面辅助功能的各种提示。</span><span class="sxs-lookup"><span data-stu-id="13750-146">Your report gives you various tips on how to improve the accessibility of the page.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="报表" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       <span data-ttu-id="13750-148">报表</span><span class="sxs-lookup"><span data-stu-id="13750-148">A report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="13750-149">单击审核以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="13750-149">Click an audit to learn more about it.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="有关审核的详细信息" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       <span data-ttu-id="13750-151">有关审核的详细信息</span><span class="sxs-lookup"><span data-stu-id="13750-151">More information about an audit</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="13750-152">单击 " **了解详细信息** " 以查看该审核的文档。</span><span class="sxs-lookup"><span data-stu-id="13750-152">Click **Learn More** to view the documentation of that audit.</span></span>  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="查看审核文档" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       <span data-ttu-id="13750-154">查看审核文档</span><span class="sxs-lookup"><span data-stu-id="13750-154">View the documentation of an audit</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="13750-155">另请参阅： aXe 扩展名</span><span class="sxs-lookup"><span data-stu-id="13750-155">See also: aXe extension</span></span>  

<span data-ttu-id="13750-156">您可能希望使用 [aXe 扩展][ChromeWebStoreAxe] ，而不是 " **审核** " 面板。</span><span class="sxs-lookup"><span data-stu-id="13750-156">You may prefer to use the [aXe extension][ChromeWebStoreAxe] rather than the **Audits** panel.</span></span>  
<span data-ttu-id="13750-157">AXe 扩展通常提供相同的信息，因为它是为 "审核" 面板加电的基础引擎。</span><span class="sxs-lookup"><span data-stu-id="13750-157">The aXe extension generally provides the same information, since it is the underlying engine that powers the Audits panel.</span></span>  <span data-ttu-id="13750-158">AXe 扩展具有不同的 UI，并以略微不同的方式描述审核。</span><span class="sxs-lookup"><span data-stu-id="13750-158">The aXe extension has a different UI and describes audits slightly differently.</span></span>  
<span data-ttu-id="13750-159">AXe 扩展在 " **审核** " 面板上的一个优点是，它使您能够检查和突出显示失败的节点。</span><span class="sxs-lookup"><span data-stu-id="13750-159">One advantage that the aXe extension has over the **Audits** panel is that it enables you to inspect and highlight failing nodes.</span></span>  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="AXe 扩展" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   <span data-ttu-id="13750-161">AXe 扩展</span><span class="sxs-lookup"><span data-stu-id="13750-161">The aXe extension</span></span>  
:::image-end:::  

## <span data-ttu-id="13750-162">辅助功能窗格</span><span class="sxs-lookup"><span data-stu-id="13750-162">The Accessibility pane</span></span>  

<span data-ttu-id="13750-163">在 " **辅助功能** " 窗格中，你可以查看 DOM 节点的辅助功能树、ARIA 属性和计算的辅助功能属性。</span><span class="sxs-lookup"><span data-stu-id="13750-163">The **Accessibility** pane is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span></span>  

<span data-ttu-id="13750-164">打开 " **辅助功能** " 窗格：</span><span class="sxs-lookup"><span data-stu-id="13750-164">To open the **Accessibility** pane:</span></span>  

1.  <span data-ttu-id="13750-165">单击 " **元素** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="13750-165">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="13750-166">在 **DOM 树**中，选择要检查的元素。</span><span class="sxs-lookup"><span data-stu-id="13750-166">In the **DOM Tree**, select the element which you want to inspect.</span></span>  
1.  <span data-ttu-id="13750-167">单击 " **辅助功能** " 选项卡。 此选项卡可能隐藏在 " **更多选项卡** \ (![ 更多选项卡 ][ImageMoreTabsIcon] \ ) " 按钮之后。</span><span class="sxs-lookup"><span data-stu-id="13750-167">Click the **Accessibility** tab.  This tab may be hidden behind the **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) button.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="在 "辅助功能" 窗格中检查 DevTools 主页的 h1 元素" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   <span data-ttu-id="13750-169">`h1`在 "**辅助功能**" 窗格中检查 DevTools 主页的元素</span><span class="sxs-lookup"><span data-stu-id="13750-169">Inspect the `h1` element of the DevTools homepage in the **Accessibility** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="13750-170">查看辅助功能树中元素的位置</span><span class="sxs-lookup"><span data-stu-id="13750-170">View the position of an element in the accessibility tree</span></span>  

<span data-ttu-id="13750-171">[辅助功能树][MDNAccessibilityTree]是 DOM 树的子集。</span><span class="sxs-lookup"><span data-stu-id="13750-171">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span></span>  <span data-ttu-id="13750-172">它仅包含 DOM 树中的元素，这些元素适用于在屏幕阅读器中显示页面的内容。</span><span class="sxs-lookup"><span data-stu-id="13750-172">It only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span></span>  

<span data-ttu-id="13750-173">在 "辅助 [功能" 窗格](#the-accessibility-pane)的 "辅助功能" 树中检查元素的位置。</span><span class="sxs-lookup"><span data-stu-id="13750-173">Inspect the position of an element in the accessibility tree from the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="辅助功能树部分" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   <span data-ttu-id="13750-175">**辅助功能树**部分</span><span class="sxs-lookup"><span data-stu-id="13750-175">The **Accessibility Tree** section</span></span>  
:::image-end:::  

### <span data-ttu-id="13750-176">查看元素的 ARIA 属性</span><span class="sxs-lookup"><span data-stu-id="13750-176">View the ARIA attributes of an element</span></span>  

<span data-ttu-id="13750-177">ARIA 属性确保屏幕阅读器具有它们所需的所有信息，以便正确地表示页面的内容。</span><span class="sxs-lookup"><span data-stu-id="13750-177">ARIA attributes ensure that screen readers have all of the information that they need in order to properly represent the contents of a page.</span></span>  

<span data-ttu-id="13750-178">在 " [辅助功能" 窗格](#the-accessibility-pane)中查看元素的 ARIA 属性。</span><span class="sxs-lookup"><span data-stu-id="13750-178">View the ARIA attributes of an element in the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="ARIA 属性部分" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   <span data-ttu-id="13750-180">**ARIA 属性**部分</span><span class="sxs-lookup"><span data-stu-id="13750-180">The **ARIA Attributes** section</span></span>  
:::image-end:::  

### <span data-ttu-id="13750-181">查看元素的计算辅助功能属性</span><span class="sxs-lookup"><span data-stu-id="13750-181">View the computed accessibility properties of an element</span></span>  

> [!NOTE]
> <span data-ttu-id="13750-182">如果要查找计算的 CSS 属性，请参阅 " [计算" 选项卡][DevtoolsCssReferenceViewActuallyAppliedElements]。</span><span class="sxs-lookup"><span data-stu-id="13750-182">If you are looking for computed CSS properties, see the [Computed tab][DevtoolsCssReferenceViewActuallyAppliedElements].</span></span>  

<span data-ttu-id="13750-183">某些辅助功能属性是由浏览器动态计算的。</span><span class="sxs-lookup"><span data-stu-id="13750-183">Some accessibility properties are dynamically calculated by the browser.</span></span>  <span data-ttu-id="13750-184">这些属性显示在 "**辅助功能**" 窗格的 "**计算属性**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="13750-184">These properties are displayed in the **Computed Properties** section of the **Accessibility** pane.</span></span>  

<span data-ttu-id="13750-185">在 " [辅助功能" 窗格](#the-accessibility-pane)中查看元素的计算辅助功能属性。</span><span class="sxs-lookup"><span data-stu-id="13750-185">View the computed accessibility properties of an element in the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text=""辅助功能" 窗格的 "计算属性" 部分" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   <span data-ttu-id="13750-187">"**辅助功能**" 窗格的 "**计算属性**" 部分</span><span class="sxs-lookup"><span data-stu-id="13750-187">The **Computed Properties** section of the **Accessibility** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="13750-188">查看颜色选取器中的文本元素的对比度比率</span><span class="sxs-lookup"><span data-stu-id="13750-188">View the contrast ratio of a text element in the Color Picker</span></span>  

<span data-ttu-id="13750-189">某些视力较差的人看不到非常明亮或非常暗的区域。</span><span class="sxs-lookup"><span data-stu-id="13750-189">Some people with low vision do not see areas as very bright or very dark.</span></span>  <span data-ttu-id="13750-190">所有内容往往都看起来几乎相同，这使区分轮廓和边缘变得很困难。</span><span class="sxs-lookup"><span data-stu-id="13750-190">Everything tends to appear at about the same brightness, which makes it hard to distinguish outlines and edges.</span></span>  

<span data-ttu-id="13750-191">对比度比率测量文本前景和背景之间的亮度差异。</span><span class="sxs-lookup"><span data-stu-id="13750-191">Contrast ratio measures the difference in brightness between the foreground and background of text.</span></span>  <span data-ttu-id="13750-192">如果文本的对比度较低，则这些视力较差的用户可能会以空白屏幕的形式体验您的网站。</span><span class="sxs-lookup"><span data-stu-id="13750-192">If your text has a low contrast ratio, then these low vision users may literally experience your site as a blank screen.</span></span>  

<span data-ttu-id="13750-193">颜色选取器可帮助你验证文本是否满足建议的对比度比率：</span><span class="sxs-lookup"><span data-stu-id="13750-193">The Color Picker helps you verify that your text meets recommended contrast ratio levels:</span></span>  

1.  <span data-ttu-id="13750-194">单击 " **元素** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="13750-194">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="13750-195">在 **DOM 树**中，选择要检查的文本元素。</span><span class="sxs-lookup"><span data-stu-id="13750-195">In the **DOM Tree**, select the text element that you want to inspect.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="检查 DOM 树中的段落" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       <span data-ttu-id="13750-197">检查**DOM 树**中的段落</span><span class="sxs-lookup"><span data-stu-id="13750-197">Inspect a paragraph in the **DOM Tree**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="13750-198">在 " **样式** " 窗格中，单击元素值旁边的颜色方块 `color` 。</span><span class="sxs-lookup"><span data-stu-id="13750-198">In the **Styles** pane, click the color square next to the `color` value of the element.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="元素的 color 属性" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       <span data-ttu-id="13750-200">`color`元素的属性</span><span class="sxs-lookup"><span data-stu-id="13750-200">The `color` property of the element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="13750-201">检查拾色器的 " **对比度比率** " 部分。</span><span class="sxs-lookup"><span data-stu-id="13750-201">Check the **Contrast Ratio** section of the Color Picker.</span></span>  <span data-ttu-id="13750-202">一个复选标记表示该元素满足 [最低建议][W3CContrastMinimum]。</span><span class="sxs-lookup"><span data-stu-id="13750-202">One checkmark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span></span>  <span data-ttu-id="13750-203">两个复选标记表示它符合 [增强的建议][W3CContrastEnhanced]。</span><span class="sxs-lookup"><span data-stu-id="13750-203">Two checkmarks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="颜色选取器的 "对比度比率" 部分显示2个复选标记和值13.97。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       <span data-ttu-id="13750-205">颜色选取器的 " **对比度比率** " 部分显示2个复选标记，值为</span><span class="sxs-lookup"><span data-stu-id="13750-205">The **Contrast Ratio** section of the Color Picker shows 2 checkmarks and a value of</span></span> `13.97`  
    :::image-end:::  
    
1.  <span data-ttu-id="13750-206">单击 " **对比度比率** " 部分可查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="13750-206">Click the **Contrast Ratio** section to see more information.</span></span>  <span data-ttu-id="13750-207">可视选取器中的颜色选取器顶部会显示一条线。</span><span class="sxs-lookup"><span data-stu-id="13750-207">A line appears in the visual picker at the top of the Color Picker.</span></span>  <span data-ttu-id="13750-208">如果当前颜色满足建议，则行的同一侧的任何内容也满足建议。</span><span class="sxs-lookup"><span data-stu-id="13750-208">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span></span>  <span data-ttu-id="13750-209">如果当前颜色不符合建议，则同一侧的任何内容也不能满足建议。</span><span class="sxs-lookup"><span data-stu-id="13750-209">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="可视选取器中的 "对比度" 比率线" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       <span data-ttu-id="13750-211">可视选取器中的 " **对比度" 比率** 线</span><span class="sxs-lookup"><span data-stu-id="13750-211">The **Contrast Ratio** Line in the visual picker</span></span>  
    :::image-end:::  
    
<!--## Feedback   -->  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "导航 Microsoft Edge DevTools 与辅助技术 |Microsoft 文档"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "仅查看实际应用到元素 CSS 引用的 CSS |Microsoft 文档"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe-Web 辅助功能测试-Chrome Web Store"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "辅助功能树 (AOM) |MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "辅助功能 |MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "屏幕阅读器 |MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "对比度 (增强) 级 AAA |W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "对比度 (最低) 级别 AA |W3C"  

> [!NOTE]
> <span data-ttu-id="13750-220">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="13750-220">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="13750-221">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="13750-221">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="13750-223">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="13750-223">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
