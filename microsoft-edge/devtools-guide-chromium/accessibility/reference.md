---
description: Microsoft Edge 开发工具辅助功能的综合参考。
title: 辅助功能参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: a82dec6ffd7e3fb44143ea103fc9756afcd1a161
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564572"
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
# <a name="accessibility-reference"></a><span data-ttu-id="f66fb-104">辅助功能参考</span><span class="sxs-lookup"><span data-stu-id="f66fb-104">Accessibility reference</span></span>  

<span data-ttu-id="f66fb-105">本页是 Microsoft Edge 开发工具辅助功能的综合参考。</span><span class="sxs-lookup"><span data-stu-id="f66fb-105">This page is a comprehensive reference of accessibility features in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="f66fb-106">适用于以下 web 开发人员： </span><span class="sxs-lookup"><span data-stu-id="f66fb-106">It is intended for web developers who:</span></span>  

*   <span data-ttu-id="f66fb-107">基本了解开发工具，例如如何打开它。</span><span class="sxs-lookup"><span data-stu-id="f66fb-107">Have a basic understanding of DevTools, such as how to open it.</span></span>  
*   <span data-ttu-id="f66fb-108">熟悉[辅助功能原理和最佳做法][MDNAccessibility]。</span><span class="sxs-lookup"><span data-stu-id="f66fb-108">Are familiar with [accessibility principles and best practices][MDNAccessibility].</span></span>  
    
<span data-ttu-id="f66fb-109">此参考的目的是帮助你发现开发工具中提供的所有工具，可帮助你检查页面的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="f66fb-109">The purpose of this reference is to help you discover all of the tools available in DevTools that help you examine the accessibility of a page.</span></span>  

<span data-ttu-id="f66fb-110">如果正在使用屏幕阅读器等辅助技术导航开发工具时寻求帮助，请导航至[使用辅助技术导航 Microsoft Edge 开发工具][DevtoolsAccessibilityNavigation]。</span><span class="sxs-lookup"><span data-stu-id="f66fb-110">If you are looking for help on navigating DevTools with an assistive technology like a screen reader, navigate to [Navigating Microsoft Edge DevTools With Assistive Technology][DevtoolsAccessibilityNavigation].</span></span>  

## <a name="overview-of-accessibility-features-in-microsoft-edge-devtools"></a><span data-ttu-id="f66fb-111">Microsoft Edge 开发工具中的辅助功能概述</span><span class="sxs-lookup"><span data-stu-id="f66fb-111">Overview of accessibility features in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f66fb-112">本部分介绍了开发工具如何适应整个辅助功能工具包。</span><span class="sxs-lookup"><span data-stu-id="f66fb-112">This section explains how DevTools fits into your overall accessibility toolkit.</span></span>  

<span data-ttu-id="f66fb-113">确定页面是否可访问时，需要记住 2 个一般性问题：</span><span class="sxs-lookup"><span data-stu-id="f66fb-113">When determining whether a page is accessible, you need to have 2 general questions in mind:</span></span>  

1.  <span data-ttu-id="f66fb-114">是否可以使用键盘或[屏幕阅读器][MDNScreenReader]浏览页面？</span><span class="sxs-lookup"><span data-stu-id="f66fb-114">Are you able to navigate the page with a keyboard or [screen reader][MDNScreenReader]?</span></span>  
1.  <span data-ttu-id="f66fb-115">页面的元素是否正确标记了屏幕阅读器？</span><span class="sxs-lookup"><span data-stu-id="f66fb-115">Are the elements of the page properly marked up for screen readers?</span></span>  
    
<span data-ttu-id="f66fb-116">通常，开发工具应该可帮助你修复与问题 2 相关的错误，因为这些错误很容易以自动方式检测。</span><span class="sxs-lookup"><span data-stu-id="f66fb-116">In general, DevTools should help you fix errors related to question #2, because these errors are easy to detect in an automated fashion.</span></span>  <span data-ttu-id="f66fb-117">问题 1 同样重要，但遗憾的是，开发工具没有用。</span><span class="sxs-lookup"><span data-stu-id="f66fb-117">Question #1 is just as important, but unfortunately DevTools does not help you there.</span></span>  <span data-ttu-id="f66fb-118">查找问题 1 相关错误的唯一方法是尝试自己使用带有键盘或屏幕阅读器的页面。</span><span class="sxs-lookup"><span data-stu-id="f66fb-118">The only way to find errors related to question #1 is to try using a page with a keyboard or screen reader yourself.</span></span>  <!--To learn more, navigate to [How To Do An Accessibility Review][AccessibilityReview].  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <a name="audit-the-accessibility-of-a-page"></a><span data-ttu-id="f66fb-119">审核页面的辅助功能</span><span class="sxs-lookup"><span data-stu-id="f66fb-119">Audit the accessibility of a page</span></span>  

> [!NOTE]
> <span data-ttu-id="f66fb-120">**审核**工具提供指向第三方网站上托管的内容的链接。</span><span class="sxs-lookup"><span data-stu-id="f66fb-120">The **Audits** tool provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="f66fb-121">Microsoft 不负责也不控制这些网站的内容，并且可能会收集任何数据。</span><span class="sxs-lookup"><span data-stu-id="f66fb-121">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span></span>  

<span data-ttu-id="f66fb-122">通常，使用审核窗格来确定是否：</span><span class="sxs-lookup"><span data-stu-id="f66fb-122">In general, use the Audits panel to determine if:</span></span>  

*   <span data-ttu-id="f66fb-123">为屏幕阅读器正确标记了页面。</span><span class="sxs-lookup"><span data-stu-id="f66fb-123">A page is properly marked up for screen readers.</span></span>  
*   <span data-ttu-id="f66fb-124">页面上的文本元素具有足够的对比度。</span><span class="sxs-lookup"><span data-stu-id="f66fb-124">The text elements on a page have sufficient contrast ratios.</span></span>  <span data-ttu-id="f66fb-125">导航到[查看颜色选取器中的文本元素的对比率](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)。</span><span class="sxs-lookup"><span data-stu-id="f66fb-125">Navigate to [View the contrast ratio of a text element in the Color Picker](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker).</span></span>  

<span data-ttu-id="f66fb-126">审核页面：</span><span class="sxs-lookup"><span data-stu-id="f66fb-126">To audit a page:</span></span>  

1.  <span data-ttu-id="f66fb-127">导航到要审核的 URL。</span><span class="sxs-lookup"><span data-stu-id="f66fb-127">Navigate to the URL that you want to audit.</span></span>  
1.  <span data-ttu-id="f66fb-128">在开发工具中，选择**审核**工具。</span><span class="sxs-lookup"><span data-stu-id="f66fb-128">In DevTools, choose the **Audits** tool.</span></span>  <span data-ttu-id="f66fb-129">开发工具显示各种配置选项。</span><span class="sxs-lookup"><span data-stu-id="f66fb-129">DevTools shows you various configuration options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="配置审核" lightbox="../media/accessibility-audits-pane.msft.png":::
       <span data-ttu-id="f66fb-131">配置审核</span><span class="sxs-lookup"><span data-stu-id="f66fb-131">Configure audits</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="f66fb-132">此部分中屏幕截图取自 Microsoft Edge 版本 79。</span><span class="sxs-lookup"><span data-stu-id="f66fb-132">The screenshots in this section were taken with Microsoft Edge version 79.</span></span>  <span data-ttu-id="f66fb-133">可以在 `edge://version` 上查看正在运行的版本。</span><span class="sxs-lookup"><span data-stu-id="f66fb-133">You may check what version you are running at `edge://version`.</span></span>  <span data-ttu-id="f66fb-134">**审核**工具 UI 在早期版本的 Microsoft Edge 中看起来有所不同，但是一般的工作流程相同。</span><span class="sxs-lookup"><span data-stu-id="f66fb-134">The **Audits** tool UI looks different in earlier versions of Microsoft Edge, but the general workflow is the same.</span></span>  
    
1.  <span data-ttu-id="f66fb-135">对于“**设备**”，如果要模拟移动设备，请选择“**移动设备**”。</span><span class="sxs-lookup"><span data-stu-id="f66fb-135">For **Device**, choose **Mobile** if you want to simulate a mobile device.</span></span>  <span data-ttu-id="f66fb-136">此选项将更改用户代理字符串并调整视口的大小。</span><span class="sxs-lookup"><span data-stu-id="f66fb-136">This option changes your user agent string and resizes the viewport.</span></span>  <span data-ttu-id="f66fb-137">如果页面的移动版本显示方式与桌面版本不同，则此选项可能会显著影响审核结果。</span><span class="sxs-lookup"><span data-stu-id="f66fb-137">If the mobile version of the page displays differently than the desktop version, this option may have a significant effect on the results of your audit.</span></span>  
1.  <span data-ttu-id="f66fb-138">在“**审核**”部分中，确保已启用“**辅助功能**”。</span><span class="sxs-lookup"><span data-stu-id="f66fb-138">In the **Audits** section, make sure that **Accessibility** is enabled.</span></span>  <span data-ttu-id="f66fb-139">如果要从报告中排除其他类别，请禁用它们。</span><span class="sxs-lookup"><span data-stu-id="f66fb-139">Disable the other categories if you want to exclude them from your report.</span></span>  <span data-ttu-id="f66fb-140">如果希望发现其他方法提高页面质量，请将其保持启用状态。</span><span class="sxs-lookup"><span data-stu-id="f66fb-140">Leave them enabled if you want to discover other ways to improve the quality of your page.</span></span>  
1.  <span data-ttu-id="f66fb-141">“\*\*限制 \*\*”部分可让你限制网络和 CPU，这在分析负载性能时非常有用。</span><span class="sxs-lookup"><span data-stu-id="f66fb-141">The **Throttling** section lets you throttle the network and CPU, which is useful when analyzing load performance.</span></span>  <span data-ttu-id="f66fb-142">此选项应该与辅助功能分数无关，因此可以使用自己喜欢的任何内容。</span><span class="sxs-lookup"><span data-stu-id="f66fb-142">This option should be irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="f66fb-143">“**清除存储空间**”复选框可让你在加载页面之前清除所有存储，或在页面加载之间保留存储。</span><span class="sxs-lookup"><span data-stu-id="f66fb-143">The **Clear Storage** checkbox lets you clear all storage before loading the page, or preserve storage between page loads.</span></span>  <span data-ttu-id="f66fb-144">此选项还可能与辅助功能分数无关，因此可以使用自己喜欢的任何内容。</span><span class="sxs-lookup"><span data-stu-id="f66fb-144">This option is also probably irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="f66fb-145">选择“**运行审核**”。</span><span class="sxs-lookup"><span data-stu-id="f66fb-145">Choose **Run Audits**.</span></span> <span data-ttu-id="f66fb-146">10 到 30 秒后，开发工具将提供一个报告。</span><span class="sxs-lookup"><span data-stu-id="f66fb-146">After 10 to 30 seconds, DevTools provides a report.</span></span>  <span data-ttu-id="f66fb-147">你的报告为你提供有关如何提高页面辅助功能的各种提示。</span><span class="sxs-lookup"><span data-stu-id="f66fb-147">Your report gives you various tips on how to improve the accessibility of the page.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="报告" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       <span data-ttu-id="f66fb-149">报告</span><span class="sxs-lookup"><span data-stu-id="f66fb-149">A report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f66fb-150">选择审核以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="f66fb-150">Choose an audit to learn more about it.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="有关审核的更多详细信息" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       <span data-ttu-id="f66fb-152">有关审核的更多详细信息</span><span class="sxs-lookup"><span data-stu-id="f66fb-152">More information about an audit</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f66fb-153">选择**了解更多信息**以查看该审核的文档。</span><span class="sxs-lookup"><span data-stu-id="f66fb-153">Choose **Learn More** to view the documentation of that audit.</span></span>  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="查看审核文档" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       <span data-ttu-id="f66fb-155">查看审核文档</span><span class="sxs-lookup"><span data-stu-id="f66fb-155">View the documentation of an audit</span></span>  
    :::image-end:::  
    
### <a name="see-also-axe-extension"></a><span data-ttu-id="f66fb-156">另请参阅：aXe 扩展</span><span class="sxs-lookup"><span data-stu-id="f66fb-156">See also: aXe extension</span></span>  

<span data-ttu-id="f66fb-157">你可能更喜欢使用 “[aXe 扩展][ChromeWebStoreAxe]”而不是“**审核**”工具。</span><span class="sxs-lookup"><span data-stu-id="f66fb-157">You may prefer to use the [aXe extension][ChromeWebStoreAxe] rather than the **Audits** tool.</span></span>  
<span data-ttu-id="f66fb-158">aXe 扩展通常提供相同的信息，因为它是支持审核窗格的基础引擎。</span><span class="sxs-lookup"><span data-stu-id="f66fb-158">The aXe extension generally provides the same information, since it is the underlying engine that powers the Audits panel.</span></span>  <span data-ttu-id="f66fb-159">aXe 扩展具有不同的 UI，并且对审核的描述略有不同。</span><span class="sxs-lookup"><span data-stu-id="f66fb-159">The aXe extension has a different UI and describes audits slightly differently.</span></span>  
<span data-ttu-id="f66fb-160">ax 扩展相对于“**审核**”工具的一个优势是，可以检查并突出显示出现故障的节点。</span><span class="sxs-lookup"><span data-stu-id="f66fb-160">One advantage that the aXe extension has over the **Audits** tool is that it enables you to inspect and highlight failing nodes.</span></span>  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="aXe 扩展" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   <span data-ttu-id="f66fb-162">aXe 扩展</span><span class="sxs-lookup"><span data-stu-id="f66fb-162">The aXe extension</span></span>  
:::image-end:::  

## <a name="the-accessibility-panel"></a><span data-ttu-id="f66fb-163">辅助功能窗格</span><span class="sxs-lookup"><span data-stu-id="f66fb-163">The Accessibility panel</span></span>  

<span data-ttu-id="f66fb-164">在“**辅助功能**”窗格上，可以查看 DOM 节点的辅助功能树、ARIA 属性和计算出的辅助功能属性。</span><span class="sxs-lookup"><span data-stu-id="f66fb-164">The **Accessibility** panel is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span></span>  

<span data-ttu-id="f66fb-165">打开**辅助功能**窗格：</span><span class="sxs-lookup"><span data-stu-id="f66fb-165">To open the **Accessibility** panel:</span></span>  

1.  <span data-ttu-id="f66fb-166">选择“**元素**”工具。</span><span class="sxs-lookup"><span data-stu-id="f66fb-166">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="f66fb-167">在 **DOM 树**中，选择要检查的元素。</span><span class="sxs-lookup"><span data-stu-id="f66fb-167">In the **DOM Tree**, select the element which you want to inspect.</span></span>  
1.  <span data-ttu-id="f66fb-168">选择**辅助功能**窗格。</span><span class="sxs-lookup"><span data-stu-id="f66fb-168">Choose the **Accessibility** panel.</span></span>  <span data-ttu-id="f66fb-169">此窗格可能隐藏在**更多 选项卡** \(![更多 选项卡](../media/more-tabs-icon.msft.png)\) 按钮后面。</span><span class="sxs-lookup"><span data-stu-id="f66fb-169">This panel may be hidden behind the **More Tabs** \(![More Tabs](../media/more-tabs-icon.msft.png)\) button.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="在“辅助功能”窗格中检查开发工具主页的 h1 元素。" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   <span data-ttu-id="f66fb-171">在“**辅助功能**”窗格中检查开发工具主页的 `h1` 元素。</span><span class="sxs-lookup"><span data-stu-id="f66fb-171">Inspect the `h1` element of the DevTools homepage in the **Accessibility** panel</span></span>  
:::image-end:::  

### <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a><span data-ttu-id="f66fb-172">查看元素在辅助功能树中的位置</span><span class="sxs-lookup"><span data-stu-id="f66fb-172">View the position of an element in the accessibility tree</span></span>  

<span data-ttu-id="f66fb-173">[辅助功能树][MDNAccessibilityTree]是 DOM 树的子集。</span><span class="sxs-lookup"><span data-stu-id="f66fb-173">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span></span>  <span data-ttu-id="f66fb-174">它仅包含 DOM 树中的元素，这些元素对于在屏幕阅读器中显示页面内容非常有用。</span><span class="sxs-lookup"><span data-stu-id="f66fb-174">It only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span></span>  

<span data-ttu-id="f66fb-175">从“[辅助功能](#the-accessibility-panel)“窗格检查元素辅助功能树中的元素位置。</span><span class="sxs-lookup"><span data-stu-id="f66fb-175">Inspect the position of an element in the accessibility tree from the [Accessibility](#the-accessibility-panel) panel.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="辅助功能树部分" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   <span data-ttu-id="f66fb-177">**辅助功能树**部分</span><span class="sxs-lookup"><span data-stu-id="f66fb-177">The **Accessibility Tree** section</span></span>  
:::image-end:::  

### <a name="view-the-aria-attributes-of-an-element"></a><span data-ttu-id="f66fb-178">查看元素的 ARIA 属性</span><span class="sxs-lookup"><span data-stu-id="f66fb-178">View the ARIA attributes of an element</span></span>  

<span data-ttu-id="f66fb-179">ARIA 属性可确保屏幕阅读器拥有正确显示页面内容需要的所有信息。</span><span class="sxs-lookup"><span data-stu-id="f66fb-179">ARIA attributes ensure that screen readers have all of the information that they need in order to properly represent the contents of a page.</span></span>  

<span data-ttu-id="f66fb-180">在[辅助功能](#the-accessibility-panel)窗格中查看元素的 ARIA 属性。</span><span class="sxs-lookup"><span data-stu-id="f66fb-180">View the ARIA attributes of an element in the [Accessibility](#the-accessibility-panel) panel.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="ARIA 属性部分" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   <span data-ttu-id="f66fb-182">**ARIA 属性**部分</span><span class="sxs-lookup"><span data-stu-id="f66fb-182">The **ARIA Attributes** section</span></span>  
:::image-end:::  

### <a name="view-the-computed-accessibility-properties-of-an-element"></a><span data-ttu-id="f66fb-183">查看元素的计算出的属性</span><span class="sxs-lookup"><span data-stu-id="f66fb-183">View the computed accessibility properties of an element</span></span>  

> [!NOTE]
> <span data-ttu-id="f66fb-184">如果要查找计算出的 CSS 属性，请导航到“[计算][DevtoolsCssReferenceViewActuallyAppliedElements]”窗格。</span><span class="sxs-lookup"><span data-stu-id="f66fb-184">If you are looking for computed CSS properties, navigate to [Computed][DevtoolsCssReferenceViewActuallyAppliedElements] panel.</span></span>  

<span data-ttu-id="f66fb-185">部分辅助功能属性由浏览器动态计算。</span><span class="sxs-lookup"><span data-stu-id="f66fb-185">Some accessibility properties are dynamically calculated by the browser.</span></span>  <span data-ttu-id="f66fb-186">这些属性显示在“**辅助功能 **”窗格的“**计算出的属性**”部分中。</span><span class="sxs-lookup"><span data-stu-id="f66fb-186">These properties are displayed in the **Computed Properties** section of the **Accessibility** panel.</span></span>  

<span data-ttu-id="f66fb-187">查看“[辅助功能](#the-accessibility-panel)”窗格中元素的计算出的属性。</span><span class="sxs-lookup"><span data-stu-id="f66fb-187">View the computed accessibility properties of an element in the [Accessibility](#the-accessibility-panel) panel.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="辅助功能窗格“计算属性”部分" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   <span data-ttu-id="f66fb-189">“**辅助功能**”窗格的“**计算出的属性**”部分</span><span class="sxs-lookup"><span data-stu-id="f66fb-189">The **Computed Properties** section of the **Accessibility** panel</span></span>  
:::image-end:::  

## <a name="view-the-contrast-ratio-of-a-text-element-in-the-color-picker"></a><span data-ttu-id="f66fb-190">查看颜色选取器中的文本元素的对比率</span><span class="sxs-lookup"><span data-stu-id="f66fb-190">View the contrast ratio of a text element in the Color Picker</span></span>  

<span data-ttu-id="f66fb-191">部分弱视用户看不到非常明亮或非常暗的区域。</span><span class="sxs-lookup"><span data-stu-id="f66fb-191">Some people with low vision do not see areas as very bright or very dark.</span></span>  <span data-ttu-id="f66fb-192">所有内容通常以相同的亮度显示，从而难以区分轮廓和边缘。</span><span class="sxs-lookup"><span data-stu-id="f66fb-192">Everything tends to appear at about the same brightness, which makes it hard to distinguish outlines and edges.</span></span>  

<span data-ttu-id="f66fb-193">对比率测量文本的前景和背景的亮度差。</span><span class="sxs-lookup"><span data-stu-id="f66fb-193">Contrast ratio measures the difference in brightness between the foreground and background of text.</span></span>  <span data-ttu-id="f66fb-194">如果您的文本的对比度低，那么这些弱视用户可能会以空白屏幕的形式实际体验网站。</span><span class="sxs-lookup"><span data-stu-id="f66fb-194">If your text has a low contrast ratio, then these low vision users may literally experience your site as a blank screen.</span></span>  

<span data-ttu-id="f66fb-195">颜色选取器可帮助你验证文本是否满足建议的对比率级别：</span><span class="sxs-lookup"><span data-stu-id="f66fb-195">The Color Picker helps you verify that your text meets recommended contrast ratio levels:</span></span>  

1.  <span data-ttu-id="f66fb-196">选择“**元素**”工具。</span><span class="sxs-lookup"><span data-stu-id="f66fb-196">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="f66fb-197">在 **DOM 树**中，选择要检查的文本元素。</span><span class="sxs-lookup"><span data-stu-id="f66fb-197">In the **DOM Tree**, select the text element that you want to inspect.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="检查 DOM 树中的段落" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       <span data-ttu-id="f66fb-199">检查 **DOM 树**中的段落</span><span class="sxs-lookup"><span data-stu-id="f66fb-199">Inspect a paragraph in the **DOM Tree**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f66fb-200">在“**样式**”窗格中，选择元素 `color` 值旁边的彩色方块。</span><span class="sxs-lookup"><span data-stu-id="f66fb-200">In the **Styles** panel, choose the color square next to the `color` value of the element.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="元素的颜色属性" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       <span data-ttu-id="f66fb-202">元素的 `color` 属性</span><span class="sxs-lookup"><span data-stu-id="f66fb-202">The `color` property of the element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f66fb-203">检查“颜色选取器”中的“**对比率**”部分。</span><span class="sxs-lookup"><span data-stu-id="f66fb-203">Check the **Contrast Ratio** section of the Color Picker.</span></span>  <span data-ttu-id="f66fb-204">一个选中标记表示元素满足[最低建议][W3CContrastMinimum]。</span><span class="sxs-lookup"><span data-stu-id="f66fb-204">One checkmark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span></span>  <span data-ttu-id="f66fb-205">一个选中标记表示元素满足[增强建议][W3CContrastEnhanced]。</span><span class="sxs-lookup"><span data-stu-id="f66fb-205">Two checkmarks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="颜色选取器中的“对比率”部分显示 2 个选中标记和值 13.97" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       <span data-ttu-id="f66fb-207">颜色选取器中的“**对比率**”部分显示 2 个选中标记和值</span><span class="sxs-lookup"><span data-stu-id="f66fb-207">The **Contrast Ratio** section of the Color Picker shows 2 checkmarks and a value of</span></span> `13.97`  
    :::image-end:::  
    
1.  <span data-ttu-id="f66fb-208">有关详细信息，请选择“**对比率**”部分。</span><span class="sxs-lookup"><span data-stu-id="f66fb-208">For more information, choose the **Contrast Ratio** section.</span></span>  <span data-ttu-id="f66fb-209">颜色选取器顶部的可视化选取器中将出现一行。</span><span class="sxs-lookup"><span data-stu-id="f66fb-209">A line appears in the visual picker at the top of the Color Picker.</span></span>  <span data-ttu-id="f66fb-210">如果当前颜色符合建议，则该行的同一侧任何内容也符合建议。</span><span class="sxs-lookup"><span data-stu-id="f66fb-210">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span></span>  <span data-ttu-id="f66fb-211">如果当前颜色不满足建议，则同一侧的颜色也不符合建议。</span><span class="sxs-lookup"><span data-stu-id="f66fb-211">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="可视选取器中的对比率行" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       <span data-ttu-id="f66fb-213">可视选取器中的**对比率**行</span><span class="sxs-lookup"><span data-stu-id="f66fb-213">The **Contrast Ratio** Line in the visual picker</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f66fb-214">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="f66fb-214">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "使用辅助技术导航 Microsoft Edge 开发工具 | Microsoft Docs"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "仅查看实际应用于元素的 CSS - CSS 参考 | Microsoft Docs"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe - Web 辅助功能测试 - Chrome Web Store"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "辅助功能树 (AOM) | MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "辅助功能 | MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "屏幕阅读器 | MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "对比度级别（增强） AAA | W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "对比度级别（最低） AA | W3C"  

> [!NOTE]
> <span data-ttu-id="f66fb-223">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f66fb-223">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f66fb-224">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f66fb-224">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f66fb-226">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f66fb-226">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
