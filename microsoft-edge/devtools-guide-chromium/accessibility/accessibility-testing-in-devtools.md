---
description: 使用 DevTools 开始测试辅助功能问题
title: 使用 DevTools 的辅助功能测试概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f6ec0652bbbb7d7e60a69877a9d44a7a2fd636a5
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624792"
---
# <a name="overview-of-accessibility-testing-using-devtools"></a><span data-ttu-id="53bfd-104">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="53bfd-104">Overview of accessibility testing using DevTools</span></span>

<span data-ttu-id="53bfd-105">本文介绍可在 DevTools 中用于测试辅助功能问题的一些功能。</span><span class="sxs-lookup"><span data-stu-id="53bfd-105">In this article, we cover some of the features you can use in DevTools to test for accessibility problems.</span></span>  <span data-ttu-id="53bfd-106">我们将使用 DevTools 的不同功能检测演示页面中的辅助功能问题，并讨论如何解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-106">We go through using different features of DevTools to detect the accessibility problems in a demo page, and we discuss how to fix them.</span></span>  <span data-ttu-id="53bfd-107">打开 [新选项卡][DevToolsA11yErrorsDemopage] 中的演示页面，尝试一下自己，然后可以一起测试。</span><span class="sxs-lookup"><span data-stu-id="53bfd-107">Open the [demo page][DevToolsA11yErrorsDemopage] in a new tab to try it out yourself and you can test along.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-demopage.msft.png" alt-text="本文中使用的演示页面具有一些辅助功能问题" lightbox="../media/a11y-testing-basics-demopage.msft.png":::
    <span data-ttu-id="53bfd-109">本文中使用的演示页面具有一些辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-109">The demo page used in this article with a few accessibility issues</span></span>
:::image-end:::


## <a name="automated-testing-by-using-the-issues-tool"></a><span data-ttu-id="53bfd-110">使用问题工具自动测试</span><span class="sxs-lookup"><span data-stu-id="53bfd-110">Automated testing by using the Issues tool</span></span>

<span data-ttu-id="53bfd-111">When you open the demo page in the browser and open DevTools， notice that some issues are automatically detected in the **Issues counter**.</span><span class="sxs-lookup"><span data-stu-id="53bfd-111">When you open the demo page in the browser and open DevTools, notice that some issues are automatically detected in the **Issues counter**.</span></span>  <span data-ttu-id="53bfd-112">Select the **Issues counter** \ (Issues ![ counter ](../media/issues-counter-icon.msft.png) \) to open the Issues [tool][DevToolsIssuesTool] to view the issues and more information.</span><span class="sxs-lookup"><span data-stu-id="53bfd-112">Select the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) to open the [Issues tool][DevToolsIssuesTool] to view the issues and more information.</span></span>

:::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text=""问题"计数器显示当前网页中的问题个个，并打开"问题"工具" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
    <span data-ttu-id="53bfd-114">"问题"计数器显示当前网页中的问题个个，并打开"问题"工具</span><span class="sxs-lookup"><span data-stu-id="53bfd-114">The Issues counter shows how many problems there are in the current webpage, and opens the Issues tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-115">对于本文，我们将重点介绍问题**工具**的**辅助功能部分。**</span><span class="sxs-lookup"><span data-stu-id="53bfd-115">For this article, we'll focus on the **Accessibility** section of the **Issues** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="问题工具中显示的辅助功能警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
    <span data-ttu-id="53bfd-117">问题工具中显示的辅助功能警告</span><span class="sxs-lookup"><span data-stu-id="53bfd-117">Accessibility warnings displayed in the Issues tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-118">有关详细演练步骤，请导航到查看 [问题工具的辅助功能部分][DevToolsAccessibilityTestIssuesToolViewAccSection]。</span><span class="sxs-lookup"><span data-stu-id="53bfd-118">For detailed walkthrough steps, navigate to [View the Accessibility section of the Issues tool][DevToolsAccessibilityTestIssuesToolViewAccSection].</span></span>


### <a name="automatically-checking-that-input-fields-have-labels"></a><span data-ttu-id="53bfd-119">自动检查输入字段是否包含标签</span><span class="sxs-lookup"><span data-stu-id="53bfd-119">Automatically checking that input fields have labels</span></span>

<span data-ttu-id="53bfd-120">显示的第一个警告是 `Form elements must have labels: Element has no title attribute. Element has no placeholder attribute` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-120">The first warning displayed is `Form elements must have labels: Element has no title attribute. Element has no placeholder attribute`.</span></span>  <span data-ttu-id="53bfd-121">展开此部分并选择"在元素中打开\*\*\*\*"链接时，将打开 **"** 元素"工具，同时在 DOM 树中突出显示元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-121">When you expand this section and then select the **Open in Elements** link, the **Elements** tool opens, with the element highlighted in the DOM tree.</span></span>  <span data-ttu-id="53bfd-122">" **样式** "选项卡显示应用于 元素的 CSS。</span><span class="sxs-lookup"><span data-stu-id="53bfd-122">The **Styles** tab shows the CSS that's applied to the element.</span></span>

<span data-ttu-id="53bfd-123">有关详细演练步骤，请导航到"[验证输入字段是否包含标签"。][DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]</span><span class="sxs-lookup"><span data-stu-id="53bfd-123">For detailed walkthrough steps, navigate to [Verify that input fields have labels][DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels].</span></span>

:::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="在"问题"工具中选择链接后显示有问题的 HTML 的元素工具" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
    <span data-ttu-id="53bfd-125">在"问题"工具中选择链接后显示有问题的 HTML 的元素工具</span><span class="sxs-lookup"><span data-stu-id="53bfd-125">Elements tool showing the problematic HTML after selecting the link in the Issues tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-126">在这种情况下，HTML 具有 `label` 不起作用的元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-126">In this case, the HTML has a `label` element that doesn't work.</span></span>

```html
<label>Search</label>
<input type="search">
<input type="submit" value="go">
```

<span data-ttu-id="53bfd-127">此处元素的使用有误，因为 元素和 元素之间 `label` `label` 没有 `input` 连接。</span><span class="sxs-lookup"><span data-stu-id="53bfd-127">The use of the `label` element here is wrong, because there's no connection between the `label` element and the `input` element.</span></span>  <span data-ttu-id="53bfd-128">当您选择搜索标签时，有效的 HTML 标签将焦点放在搜索输入 **文本框** 上。</span><span class="sxs-lookup"><span data-stu-id="53bfd-128">A valid HTML label would put focus on the search input textbox when you select the **Search** label.</span></span> 

<span data-ttu-id="53bfd-129">可以通过将 元素嵌套在 元素中，或添加指向 元素属性的属性来 `input` `label` `for` `id` 解决此问题 `input` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-129">You can solve this problem by either nesting the `input` element in a `label` element, or adding a `for` attribute that points to an `id` attribute of the `input` element.</span></span>  <span data-ttu-id="53bfd-130">若要查看正确的连接，请选择"捐赠 **"表单** 上的"其他"标签。</span><span class="sxs-lookup"><span data-stu-id="53bfd-130">To view a correct connection, select the **Other** label on the donation form.</span></span>

<span data-ttu-id="53bfd-131">还可以选择问题工具中的说明 **性** 链接获取此信息。</span><span class="sxs-lookup"><span data-stu-id="53bfd-131">You can also select the explanatory links in the **Issues** tool to get this information.</span></span>

:::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="问题工具中指向有关问题的更深入信息的链接" lightbox="../media/a11y-testing-more-information-links.msft.png":::
    <span data-ttu-id="53bfd-133">问题 **工具中** 指向有关问题的更深入信息的链接</span><span class="sxs-lookup"><span data-stu-id="53bfd-133">Links in the **Issues** tool pointing to more in-depth information about the issue</span></span>
:::image-end:::


### <a name="automatically-checking-that-images-have-alt-text"></a><span data-ttu-id="53bfd-134">自动检查图像是否包含替换文字</span><span class="sxs-lookup"><span data-stu-id="53bfd-134">Automatically checking that images have alt text</span></span>

<span data-ttu-id="53bfd-135">另一个自动检测到的问题是，页面中的许多图像没有任何替代文本。</span><span class="sxs-lookup"><span data-stu-id="53bfd-135">The other automatically detected problem is that many of the images in the page don't have any alternative text.</span></span>  <span data-ttu-id="53bfd-136">如果展开警告 `Images must have alternate text: Element has no title attribute` ，将获取具有此问题的四个图像实例。</span><span class="sxs-lookup"><span data-stu-id="53bfd-136">If you expand the `Images must have alternate text: Element has no title attribute` warning, you get four instances of images with that problem.</span></span>

:::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="问题工具，报告缺少可选文本的图像" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
    <span data-ttu-id="53bfd-138">问题 **工具** ，报告缺少可选文本的图像</span><span class="sxs-lookup"><span data-stu-id="53bfd-138">The **Issues** tool, reporting images with missing alternative text</span></span>
:::image-end:::

<span data-ttu-id="53bfd-139">有关详细演练步骤，请导航到["验证图像是否具有替换文字"。][DevtoolsAccessibilityTestIssuesToolCheckAltText]</span><span class="sxs-lookup"><span data-stu-id="53bfd-139">For detailed walkthrough steps, navigate to [Verify that images have alt text][DevtoolsAccessibilityTestIssuesToolCheckAltText].</span></span>


### <a name="automatically-checking-that-text-colors-have-enough-contrast"></a><span data-ttu-id="53bfd-140">自动检查文本颜色是否具有足够的对比度</span><span class="sxs-lookup"><span data-stu-id="53bfd-140">Automatically checking that text colors have enough contrast</span></span>

<span data-ttu-id="53bfd-141">" **问题** "工具还报告页面上的两个元素没有足够的对比度。</span><span class="sxs-lookup"><span data-stu-id="53bfd-141">The **Issues** tool also reports when two elements on the page don't have enough contrast.</span></span>

:::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="问题工具中报告的对比度问题" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
    <span data-ttu-id="53bfd-143">问题工具中报告的 **对比度** 问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-143">Contrast problems reported in the **Issues** tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-144">问题 **工具** 提供警告的详细说明。</span><span class="sxs-lookup"><span data-stu-id="53bfd-144">The **Issues** tool provides detailed explanations of the warning.</span></span>  <span data-ttu-id="53bfd-145">向下钻取时，将获取具有此问题的元素的列表。</span><span class="sxs-lookup"><span data-stu-id="53bfd-145">When you drill down, you get a list of the elements that have this issue.</span></span>  <span data-ttu-id="53bfd-146">在 **"问题** "工具中，选择指向某个元素的链接将在呈现的页面上突出显示该元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-146">In the **Issues** tool, selecting a link that points to an element will highlight that element on the rendered page.</span></span>

:::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="选择指向该页面的链接后突出显示的页面中的元素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
    <span data-ttu-id="53bfd-148">选择指向该页面的链接后突出显示的页面中的元素</span><span class="sxs-lookup"><span data-stu-id="53bfd-148">Element in the page highlighted after selecting the link to it</span></span>
:::image-end:::

<span data-ttu-id="53bfd-149">有关详细演练步骤，请导航到"[验证文本颜色是否具有足够的对比度"。][DevtoolsAccessibilityTestIssuesToolCheckContrast]</span><span class="sxs-lookup"><span data-stu-id="53bfd-149">For detailed walkthrough steps, navigate to [Verify that text colors have enough contrast][DevtoolsAccessibilityTestIssuesToolCheckContrast].</span></span>


### <a name="verify-that-the-webpage-layout-is-usable-when-narrow"></a><span data-ttu-id="53bfd-150">验证网页布局在较窄时是否可用</span><span class="sxs-lookup"><span data-stu-id="53bfd-150">Verify that the webpage layout is usable when narrow</span></span>

<!-- by design, this section doesn't have a corresponding how-to article -->

<span data-ttu-id="53bfd-151">辅助功能的一个重要部分是确保 Web 产品在较窄的视口上良好工作。</span><span class="sxs-lookup"><span data-stu-id="53bfd-151">An important part of accessibility is to make sure that your web products work well on a narrow viewport.</span></span> <span data-ttu-id="53bfd-152">许多用户需要缩放页面才能使用它，这意味着没有太多空间。</span><span class="sxs-lookup"><span data-stu-id="53bfd-152">Many users need to zoom the page to be able to use it, and this means that there is not much space left.</span></span> <span data-ttu-id="53bfd-153">当空间不足时，多列布局应转换为单列布局，内容按可理解的顺序放置。</span><span class="sxs-lookup"><span data-stu-id="53bfd-153">When there is not enough space, your multi-column layout should turn into a single-column layout, with content placed in an understandable order.</span></span> <span data-ttu-id="53bfd-154">这意味着将最重要的内容放置在页面顶部，将其他内容放置在页面的更下一层。</span><span class="sxs-lookup"><span data-stu-id="53bfd-154">This means placing the most important content at the top of the page, and placing additional content further down the page.</span></span>

<span data-ttu-id="53bfd-155">通过缩小浏览器窗口范围，使用箭头键滚动页面，可以看到演示页面的顶部导航栏具有一些辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-155">By making the browser window narrow and using the arrow keys to scroll the page, you can see that the top navigation bar of the demo page has some accessibility issues.</span></span>  <span data-ttu-id="53bfd-156">顶部导航栏与 **"** 搜索"窗体重叠，如上图所示，需要修复该问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-156">The top navigation bar overlaps the **Search** form, as shown in the previous image, and that issue needs to be fixed.</span></span>

<span data-ttu-id="53bfd-157">可以通过调整浏览器窗口的大小来模拟较窄的视区，但测试设计响应性更好的方法就是使用 **设备仿真** 工具。</span><span class="sxs-lookup"><span data-stu-id="53bfd-157">You can simulate a narrow viewport by resizing the browser window, but a better way to test the responsiveness of your design is to use the **Device Emulation** tool.</span></span>  <span data-ttu-id="53bfd-158">以下是设备仿真 **工具的一** 些功能，可帮助你查找任何网站的辅助功能问题：</span><span class="sxs-lookup"><span data-stu-id="53bfd-158">Here are some features of the **Device Emulation** tool that help you find accessibility issues of any website:</span></span>

*  <span data-ttu-id="53bfd-159">无需调整浏览器窗口的大小，即可调整页面大小并测试 CSS [媒体][DevToolsMediaQueries] 查询是否触发布局更改。</span><span class="sxs-lookup"><span data-stu-id="53bfd-159">Without resizing the browser window, resize the page and test whether your [CSS media queries][DevToolsMediaQueries] trigger a change in layout.</span></span>
*  <span data-ttu-id="53bfd-160">检查是否使用鼠标的依赖项。</span><span class="sxs-lookup"><span data-stu-id="53bfd-160">Check for dependencies that use a mouse.</span></span> <span data-ttu-id="53bfd-161">默认情况下，设备仿真假定为触摸设备。</span><span class="sxs-lookup"><span data-stu-id="53bfd-161">By default, device emulation assumes a touch device.</span></span> <span data-ttu-id="53bfd-162">这意味着产品依赖于悬停交互的任何功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="53bfd-162">This means that any functionality of your product that relies on hover interaction will not work.</span></span> 
*  <span data-ttu-id="53bfd-163">通过模拟不同的设备、缩放级别和像素比率执行视觉测试。</span><span class="sxs-lookup"><span data-stu-id="53bfd-163">Do visual testing by simulating different devices, zoom levels, and pixel ratios.</span></span>
*  <span data-ttu-id="53bfd-164">测试产品在不可靠连接或用户脱机时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="53bfd-164">Test how your product behaves on unreliable connections or when the user is offline.</span></span>  <span data-ttu-id="53bfd-165">在低速连接上向用户显示最重要的交互也是辅助功能注意事项。</span><span class="sxs-lookup"><span data-stu-id="53bfd-165">Showing the most important interactions to a user on a slow connection is also an accessibility consideration.</span></span>

<span data-ttu-id="53bfd-166">若要了解有关设备仿真**工具**的信息，请导航到在[DevTools Microsoft Edge模拟移动设备][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="53bfd-166">To learn more about the **Device Emulation** tool, navigate to [Emulate mobile devices in Microsoft Edge DevTools][DevToolsDeviceModeIndex].</span></span>


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a><span data-ttu-id="53bfd-167">DOM 树中的波浪下划线指示自动检测到的问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-167">Wavy underlines in the DOM tree indicate automatically detected issues</span></span>

<span data-ttu-id="53bfd-168">"元素"工具中的 DOM **树通过** 添加波浪下划线自动在 HTML 中直接标记问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-168">The DOM tree in the **Elements** tool automatically flags issues directly in the HTML by adding a wavy underline.</span></span>  <span data-ttu-id="53bfd-169">If you `Shift` + `click` any element that has a wavy underline， the **Issues** tool opens.</span><span class="sxs-lookup"><span data-stu-id="53bfd-169">If you `Shift`+`click` any element that has a wavy underline, the **Issues** tool opens.</span></span>

:::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="在 DOM 树中以波浪下划线显示的元素有问题。  Shift+单击元素以直接解决问题" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
    <span data-ttu-id="53bfd-172">在 DOM 树中以波浪下划线显示的元素有问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-172">An element that is shown with wavy underlining in the DOM tree has issues.</span></span>  `Shift`<span data-ttu-id="53bfd-173">+`click` 直接进入问题的 元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-173">+`click` the element to get directly to the issue.</span></span>
:::image-end:::

<span data-ttu-id="53bfd-174">问题工具发现的 **这些问题是一** 些可以避免的相对明显的辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-174">These issues that were found by the **Issues** tool are some relatively obvious accessibility problems that can be avoided.</span></span>  <span data-ttu-id="53bfd-175">使用 **问题** 工具及其指导性说明修复问题，可引导你实现可访问的产品。</span><span class="sxs-lookup"><span data-stu-id="53bfd-175">Using the **Issues** tool and its guided explanations to fix them sets you on the way towards an accessible product.</span></span>


## <a name="limits-of-automated-testing"></a><span data-ttu-id="53bfd-176">自动测试的限制</span><span class="sxs-lookup"><span data-stu-id="53bfd-176">Limits of automated testing</span></span>

<span data-ttu-id="53bfd-177">问题[工具][DevToolsIssuesTool][、辅助功能 Insights][AccessibilityInsights]和[Lighthouse][Lighthouse]是自动生成网页的辅助功能报告的工具。</span><span class="sxs-lookup"><span data-stu-id="53bfd-177">The [Issues tool][DevToolsIssuesTool], [Accessibility Insights][AccessibilityInsights], and [Lighthouse][Lighthouse] are tools that automatically generate an accessibility report for a webpage.</span></span>  <span data-ttu-id="53bfd-178">从此类工具获取自动报告只是辅助功能测试之旅的开始。</span><span class="sxs-lookup"><span data-stu-id="53bfd-178">Getting an automated report from such tools is only the beginning of your accessibility-testing journey.</span></span>

<span data-ttu-id="53bfd-179">辅助功能与人员交互有关，即在不同的技术环境中使用产品时具有不同的需求的人。</span><span class="sxs-lookup"><span data-stu-id="53bfd-179">Accessibility is about human interaction—people with different needs using your products within various technical environments.</span></span>  <span data-ttu-id="53bfd-180">此测试无法完全自动化，但需要用户验证产品。</span><span class="sxs-lookup"><span data-stu-id="53bfd-180">This testing can't be fully automated, but needs verification by a human navigating the product.</span></span>  <span data-ttu-id="53bfd-181">在最佳方案中，你有权访问具有不同辅助功能需求的测试人员和使用各种环境的测试人员。</span><span class="sxs-lookup"><span data-stu-id="53bfd-181">In the best scenario, you'd have access to testers with different accessibility needs, and testers using various environments.</span></span>  <span data-ttu-id="53bfd-182">但是，通过使用键盘进行导航并检查页面的不同部分，你已可以自己执行很多操作。</span><span class="sxs-lookup"><span data-stu-id="53bfd-182">But you can already do a lot yourself by using the keyboard to navigate and by inspecting different parts of the page.</span></span>

<span data-ttu-id="53bfd-183">在演示页面上，还有一些自动测试无法检测到的其他问题，包括：</span><span class="sxs-lookup"><span data-stu-id="53bfd-183">On the demo page, there are additional issues that automated testing can't detect including:</span></span> 

*  <span data-ttu-id="53bfd-184">与页面交互后出现的问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-184">Issues that arise after you interact with the page.</span></span> 
*  <span data-ttu-id="53bfd-185">与显示更改相关的问题，例如使窗口变窄。</span><span class="sxs-lookup"><span data-stu-id="53bfd-185">Issues related to changes in display, such as making the window narrow.</span></span>

<span data-ttu-id="53bfd-186">其中一个问题就是"捐赠"表单。</span><span class="sxs-lookup"><span data-stu-id="53bfd-186">One of those issues is the donation form.</span></span>  <span data-ttu-id="53bfd-187">使用鼠标时，可以单击不同的选项来赚钱。</span><span class="sxs-lookup"><span data-stu-id="53bfd-187">When you use a mouse, you can click the different options to donate money.</span></span>  <span data-ttu-id="53bfd-188">但是，当您尝试使用键盘访问该资金表单时，不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="53bfd-188">But when you try to use the keyboard to access the donation form, nothing happens.</span></span> <span data-ttu-id="53bfd-189">若要解决此问题，您需要使用 **Inspect** 工具。</span><span class="sxs-lookup"><span data-stu-id="53bfd-189">To solve this issue, you need to use the **Inspect** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-donation-form-issue.msft.png" alt-text="演示页面上的"资金"表单突出显示" lightbox="../media/a11y-testing-basics-donation-form-issue.msft.png":::
    <span data-ttu-id="53bfd-191">演示页面上的"资金"表单突出显示</span><span class="sxs-lookup"><span data-stu-id="53bfd-191">Donation form on the demo page is highlighted</span></span>
:::image-end:::


## <a name="using-the-inspect-tool-to-detect-accessibility-issues"></a><span data-ttu-id="53bfd-192">使用检查工具检测辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-192">Using the Inspect tool to detect accessibility issues</span></span>

<span data-ttu-id="53bfd-193">使用 **"检查** "工具通过将鼠标悬停在网页的某些部分来检测辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-193">Use the **Inspect** tool to detect accessibility issues by hovering over parts of the webpage.</span></span>  <span data-ttu-id="53bfd-194">Inspect \*\*\*\* \ (Inspect ![ \) 工具位于 ](../media/inspect-icon.msft.png) DevTools 的左上角。</span><span class="sxs-lookup"><span data-stu-id="53bfd-194">The **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) tool is in the top-left corner of DevTools.</span></span>  <span data-ttu-id="53bfd-195">通过选择"检查工具"按钮 **打开"检查** "工具。</span><span class="sxs-lookup"><span data-stu-id="53bfd-195">Turn on the Inspect tool by selecting the **Inspect** tool button.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="通过选择"检查工具"按钮打开"检查"工具" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
    <span data-ttu-id="53bfd-197">通过选择 **"检查** 工具"按钮 **打开"检查** "工具</span><span class="sxs-lookup"><span data-stu-id="53bfd-197">Turn on the **Inspect** tool by selecting the **Inspect** tool button</span></span>
:::image-end:::

<span data-ttu-id="53bfd-198">选择" **检查工具"** 按钮后，可以将指针移动到呈现页面上的任何元素上。</span><span class="sxs-lookup"><span data-stu-id="53bfd-198">After you select the **Inspect** tool button, you can move your pointer over any element on the rendered page.</span></span>  <span data-ttu-id="53bfd-199">Inspect 工具将元素的布局显示为多色弹性框覆盖，将元素详细信息作为类似于工具提示的信息覆盖显示。</span><span class="sxs-lookup"><span data-stu-id="53bfd-199">The Inspect tool shows the element's layout as a multicolored flexbox overlay, and shows element details as an information overlay similar to a tooltip.</span></span>

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="使用 Inspect 工具时的多色弹性框覆盖和信息覆盖" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    <span data-ttu-id="53bfd-201">使用 Inspect 工具时的多色弹性框覆盖 **和信息** 覆盖</span><span class="sxs-lookup"><span data-stu-id="53bfd-201">Multicolor flexbox overlay and information overlay when using the **Inspect** tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-202">检查工具的辅助功能**部分包括\*\*\*\*对比度线**（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="53bfd-202">The Inspect tool's **Accessibility** section includes a **Contrast** line, when applicable.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="检查工具的辅助功能部分包括对比度行（如果适用）" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    <span data-ttu-id="53bfd-204">检查工具的辅助功能**部分包括\*\*\*\*对比度行**（如果适用）</span><span class="sxs-lookup"><span data-stu-id="53bfd-204">The Inspect tool's **Accessibility** section includes a **Contrast** line, when applicable</span></span>
:::image-end:::

<span data-ttu-id="53bfd-205">有关详细演练步骤，请导航到使用颜色 [突出显示标识嵌套区域][DevtoolsAccessibilityTestInspectToolColorHighlighting]。</span><span class="sxs-lookup"><span data-stu-id="53bfd-205">For detailed walkthrough steps, navigate to [Identify nested regions using color highlighting][DevtoolsAccessibilityTestInspectToolColorHighlighting].</span></span>
<!-- = test-inspect-tool.md##identify-nested-regions-using-color-highlighting -->

<span data-ttu-id="53bfd-206">检查工具的信息覆盖的\*\*\*\* 上半部分显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="53bfd-206">The upper section of the **Inspect** tool's information overlay displays the following information:</span></span>

* <span data-ttu-id="53bfd-207">布局类型;如果元素是使用弹性框或网格定位的，则会看到相应的图标 \ (</span><span class="sxs-lookup"><span data-stu-id="53bfd-207">Layout type; if the element is positioned using a flexbox or grid, you see an appropriate icon \(</span></span>![网格布局图标](../media/grid-icon.msft.png)<span data-ttu-id="53bfd-209">\).</span><span class="sxs-lookup"><span data-stu-id="53bfd-209">\).</span></span>
* <span data-ttu-id="53bfd-210">元素的名称，如 、 **h1**或**div**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53bfd-210">The name of the element, such as **a**, **h1**, or **div**.</span></span>
* <span data-ttu-id="53bfd-211">元素的尺寸（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="53bfd-211">The dimensions of the element, in pixels.</span></span>
* <span data-ttu-id="53bfd-212">颜色作为颜色样本， (较小的彩色方形) 和格式化值 (如 `#336699`) 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-212">The color, as a color swatch (a small, colored square) and as a formatted value (such as `#336699`).</span></span>
* <span data-ttu-id="53bfd-213">字体信息 (大小和字体系列) 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-213">Font information (size and font families).</span></span>
* <span data-ttu-id="53bfd-214">边距和填充（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="53bfd-214">Margin and padding, in pixels.</span></span>

<span data-ttu-id="53bfd-215">检查 **覆盖** 的辅助功能 **部分** 如下一节所述。</span><span class="sxs-lookup"><span data-stu-id="53bfd-215">The **Accessibility** part of the **Inspect** overlay is described in the following section.</span></span>


### <a name="checking-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a><span data-ttu-id="53bfd-216">检查各个元素的文本对比度、屏幕阅读器文本和键盘支持</span><span class="sxs-lookup"><span data-stu-id="53bfd-216">Checking individual elements for text contrast, screen reader text, and keyboard support</span></span>

<span data-ttu-id="53bfd-217">Inspect **覆盖** 的"辅助功能 **"** 部分包含以下行：</span><span class="sxs-lookup"><span data-stu-id="53bfd-217">The **Accessibility** section of the **Inspect** overlay contains the following rows:</span></span>

*   <span data-ttu-id="53bfd-218">**对比度** 定义弱视用户能否理解元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-218">**Contrast** defines whether an element can be understood by people with impaired vision.</span></span>
    *   <span data-ttu-id="53bfd-219">[WCAG][WCAG]准则定义的对比率指示文本和背景颜色之间的对比度是否足够。 [][W3CContrastRatio]</span><span class="sxs-lookup"><span data-stu-id="53bfd-219">The [contrast ratio][W3CContrastRatio] as defined by the [WCAG Guidelines][WCAG] indicates whether there is enough contrast between text and background colors.</span></span>  <span data-ttu-id="53bfd-220">绿色选中标记图标表示没有足够的对比度，橙色感叹号图标表示对比度不足。</span><span class="sxs-lookup"><span data-stu-id="53bfd-220">A green check mark icon indicates there's enough contrast, and an orange exclamation-point icon indicates there's not enough contrast.</span></span>

*   <span data-ttu-id="53bfd-221">**名称和\*\*\*\*角色**指示哪些信息辅助技术（如屏幕阅读器）将报告有关元素的信息。</span><span class="sxs-lookup"><span data-stu-id="53bfd-221">**Name** and **Role** indicate what information assistive technology, such as screen readers, will report about the element.</span></span>
    *   <span data-ttu-id="53bfd-222">**Name**是元素的文本 `a` 内容。</span><span class="sxs-lookup"><span data-stu-id="53bfd-222">The **Name** is the text content of an `a` element.</span></span>  <span data-ttu-id="53bfd-223">对于 元素 `<a href="/">About Us</a>` **，Inspect** 工具中显示的 Name 为"关于我们"。</span><span class="sxs-lookup"><span data-stu-id="53bfd-223">For the element `<a href="/">About Us</a>`, the **Name** shown in the Inspect tool is "About Us".</span></span>
    *   <span data-ttu-id="53bfd-224">**元素**的角色。</span><span class="sxs-lookup"><span data-stu-id="53bfd-224">The **Role** of the element.</span></span>  <span data-ttu-id="53bfd-225">**Role**通常是元素名称，如 、 `article` 、 `img` 或 `link` `heading` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-225">The **Role** is usually the element name, such as `article`, `img` , `link`, or `heading`.</span></span>  <span data-ttu-id="53bfd-226">`div`和 `span` 元素表示为 `generic` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-226">The `div` and `span` elements are represented as `generic`.</span></span>

*   <span data-ttu-id="53bfd-227">**键盘可聚焦** 指示用户是否可以使用除鼠标外的其他输入设备访问元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-227">**Keyboard-focusable** indicates whether users can reach the element using input devices other than a mouse.</span></span>
    *   <span data-ttu-id="53bfd-228">绿色选中标记图标指示元素是键盘可聚焦的。</span><span class="sxs-lookup"><span data-stu-id="53bfd-228">A green check mark icon indicates that the element is keyboard-focusable.</span></span>
    *   <span data-ttu-id="53bfd-229">带对角线的灰色圆圈表示元素不可通过键盘聚焦。</span><span class="sxs-lookup"><span data-stu-id="53bfd-229">A gray circle with diagonal line indicates that the element isn't keyboard-focusable.</span></span>

<span data-ttu-id="53bfd-230">有关详细演练步骤，请导航到检查各个元素的文本 [对比度、屏幕阅读器文本和键盘支持][DevtoolsAccessibilityTestInspectToolIndivElems]。</span><span class="sxs-lookup"><span data-stu-id="53bfd-230">For detailed walkthrough steps, navigate to [Check individual elements for text contrast, screen reader text, and keyboard support][DevtoolsAccessibilityTestInspectToolIndivElems].</span></span>
<!-- = test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support -->


### <a name="using-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a><span data-ttu-id="53bfd-231">使用 Inspect 工具将鼠标悬停在网页上方以突出显示 DOM 和 CSS</span><span class="sxs-lookup"><span data-stu-id="53bfd-231">Using the Inspect tool to hover over the webpage to highlight the DOM and CSS</span></span>

<span data-ttu-id="53bfd-232">使用 **Inspect 工具** 时，选择呈现页上的元素将打开 **Elements** 工具。</span><span class="sxs-lookup"><span data-stu-id="53bfd-232">When using the **Inspect** tool, selecting an element on the rendered page opens the **Elements** tool.</span></span>  <span data-ttu-id="53bfd-233">DOM 树显示元素的 **HTML，Styles** 显示应用于元素的 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="53bfd-233">The DOM tree shows the HTML of the element, and **Styles** shows the CSS properties that are applied to the element.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="有关"元素"工具中显示的选定元素的详细信息" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    <span data-ttu-id="53bfd-235">有关"元素"工具中显示的选定元素的详细信息</span><span class="sxs-lookup"><span data-stu-id="53bfd-235">Details about the selected element displayed in the Elements tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-236">使用 **Inspect 工具** 时，将鼠标悬停在打开 **Elements** 的呈现页面的不同部分时，你会注意到 DOM 树会自动刷新。</span><span class="sxs-lookup"><span data-stu-id="53bfd-236">When using the **Inspect** tool, as you hover over different parts of the rendered page with **Elements** open, you'll notice that the DOM tree automatically refreshes.</span></span>

<span data-ttu-id="53bfd-237">有关详细演练步骤，请导航到"使用检查工具将鼠标悬停在网页上方"以突出显示[DOM 和 CSS。][DevtoolsAccessibilityTestInspectToolDomCss]</span><span class="sxs-lookup"><span data-stu-id="53bfd-237">For detailed walkthrough steps, navigate to [Use the Inspect tool to hover over the webpage to highlight the DOM and CSS][DevtoolsAccessibilityTestInspectToolDomCss].</span></span>
<!-- = test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css -->


## <a name="verify-keyboard-support-by-using-the-tab-and-enter-keys"></a><span data-ttu-id="53bfd-238">使用 Tab 键和 Enter 键验证键盘支持</span><span class="sxs-lookup"><span data-stu-id="53bfd-238">Verify keyboard support by using the Tab and Enter keys</span></span>

<span data-ttu-id="53bfd-239">并非所有用户都使用指针或触摸设备，并且某些用户可能有低视力。</span><span class="sxs-lookup"><span data-stu-id="53bfd-239">Not all people use pointer or touch devices, and some people may have low vision.</span></span> <span data-ttu-id="53bfd-240">若要适应这些方案，请确保 IS 与键盘一起工作。</span><span class="sxs-lookup"><span data-stu-id="53bfd-240">To cater for these scenarios, ensure that UIs work with keyboards.</span></span>

<span data-ttu-id="53bfd-241">通过使用 或 从元素跳到元素，可以使用键盘来 `Tab` 导航 `Shift+Tab` 页面。</span><span class="sxs-lookup"><span data-stu-id="53bfd-241">You can test using a keyboard to navigate the page, by using `Tab` or `Shift+Tab` to jump from element to element.</span></span>  <span data-ttu-id="53bfd-242">如果按下演示页面，则获得焦点的第一件事 `Tab` 是页面页眉中的 **搜索** 窗体。</span><span class="sxs-lookup"><span data-stu-id="53bfd-242">If you press `Tab` on the demo page, the first thing that receives focus is the **Search** form in the page header.</span></span>  <span data-ttu-id="53bfd-243">即使使用"问题"工具之前发现的标签问题，通过按"甚至"还可以提交表单，这样 `Enter` **操作仍然** 有效。</span><span class="sxs-lookup"><span data-stu-id="53bfd-243">Pressing `Enter` even allows you to submit the form, so that works, despite the label issue we discovered earlier when using the **Issues** tool.</span></span>

<span data-ttu-id="53bfd-244">有关详细演练步骤，请导航到使用 Tab 键和 Enter 键检查 [键盘支持](test-tab-enter-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-244">For detailed walkthrough steps, navigate to [Check for keyboard support by using the Tab and Enter keys](test-tab-enter-keys.md).</span></span>

<span data-ttu-id="53bfd-245">当按下 而不是 时，下一个获得焦点的元素是页面内容部分的第一个"更多"链接， `Tab` `Enter` 如大纲所指示。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53bfd-245">When you press `Tab` instead of `Enter`, the next element that gets focus is the first **More** link in the content section of the page, as indicated by an outline.</span></span>

:::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="使用 Tab 键导航页面。  焦点显示在页面中的"更多"链接上。" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
    <span data-ttu-id="53bfd-248">使用 键导航 `Tab` 页面。</span><span class="sxs-lookup"><span data-stu-id="53bfd-248">Navigating the page by using the `Tab` key.</span></span>  <span data-ttu-id="53bfd-249">焦点显示在页面中的 **"更多** "链接上。</span><span class="sxs-lookup"><span data-stu-id="53bfd-249">Focus is shown on a **More** link in the page.</span></span>
:::image-end:::

<span data-ttu-id="53bfd-250">在通过最后一个 **"更多** "链接后，页面将向上滚动，并且不清楚哪个元素具有焦点。</span><span class="sxs-lookup"><span data-stu-id="53bfd-250">After you go past the last **More** link, the page scrolls up, and it's unclear which element has focus.</span></span>

<span data-ttu-id="53bfd-251">如果你查看屏幕左下角或使用屏幕阅读器，你可以判断边栏导航菜单中的蓝色 **"猫** "链接具有焦点，因为浏览器显示 URL `#cats` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-251">If you look to the bottom left of the screen or if you use a screen reader, you can tell that the blue **Cats** link in the sidebar navigation menu has focus, because the browser shows the URL `#cats`.</span></span>

:::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="缺少焦点样式使无法知道你当前在页面中的什么位置。  唯一的提示是在窗口左下角显示链接目标。" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
    <span data-ttu-id="53bfd-254">缺少焦点样式使无法知道你当前在页面中的什么位置。</span><span class="sxs-lookup"><span data-stu-id="53bfd-254">A lack of focus styling makes it impossible to know where you currently are in the page.</span></span>  <span data-ttu-id="53bfd-255">唯一的提示是在窗口左下角显示链接目标。</span><span class="sxs-lookup"><span data-stu-id="53bfd-255">The only hint is the display of the link target in the bottom left of the window.</span></span>
:::image-end:::

<span data-ttu-id="53bfd-256">再次 `Tab` 选择，将你带至"发送"表单的输入文本框。</span><span class="sxs-lookup"><span data-stu-id="53bfd-256">Selecting `Tab` again takes you to the input textbox of the donation form.</span></span>  <span data-ttu-id="53bfd-257">但是，你无法到达输入文本框上方**的 50、100**或**200**个按钮。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53bfd-257">However, you can't reach the **50**, **100** or **200** buttons above the input textbox.</span></span>  <span data-ttu-id="53bfd-258">此外，当焦点位于该输入文本框上时，选择 `Enter` 不会提交表单。</span><span class="sxs-lookup"><span data-stu-id="53bfd-258">Also, when focus is on that input textbox, selecting `Enter` doesn't submit the form.</span></span>

:::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="在资金表单中，唯一一个可通过键盘访问的元素是输入文本字段" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
    <span data-ttu-id="53bfd-260">在捐赠窗体中，唯一一个可通过键盘访问的元素是文本字段</span><span class="sxs-lookup"><span data-stu-id="53bfd-260">The only keyboard-accessible element in the donation form is the text field</span></span>
:::image-end:::

<span data-ttu-id="53bfd-261">再次选择会将焦点放在顶部导航栏上，您可以选择转到页面的不同部分或网站的不同 `Tab` `Enter` 页面。</span><span class="sxs-lookup"><span data-stu-id="53bfd-261">Selecting `Tab` again puts focus on the top navigation bar, where you can select `Enter` to go to a different section of the page or a different page of the site.</span></span>  <span data-ttu-id="53bfd-262">你知道自己位于哪个元素上，因为有焦点轮廓。</span><span class="sxs-lookup"><span data-stu-id="53bfd-262">You know which element you are on, because there's a focus outline.</span></span>  <span data-ttu-id="53bfd-263">若要选择顶部导航栏中的链接，请使用 或 将焦点放在链接上， `Tab` `Shift+Tab` 然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-263">To select a link in the top navigation bar, use `Tab` or `Shift+Tab` to put focus on a link, and then select `Enter`.</span></span>

:::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="顶部导航栏具有突出显示和焦点轮廓，因此键盘可访问" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
    <span data-ttu-id="53bfd-265">顶部导航栏具有突出显示和焦点轮廓，因此键盘可访问</span><span class="sxs-lookup"><span data-stu-id="53bfd-265">The top navigation bar has a highlight and a focus outline, and thus is keyboard-accessible</span></span>
:::image-end:::

<span data-ttu-id="53bfd-266">我们发现了一些要修复的问题：</span><span class="sxs-lookup"><span data-stu-id="53bfd-266">We found some issues here to fix:</span></span>

* <span data-ttu-id="53bfd-267">使用键盘在页面上四处移动时，边栏导航菜单不会向用户显示 `Tab` 焦点位置。</span><span class="sxs-lookup"><span data-stu-id="53bfd-267">The sidebar navigation menu doesn't show users where the `Tab` focus is, when using keyboards to move around on the page.</span></span>
* <span data-ttu-id="53bfd-268">在使用键盘时，在"捐赠"表单上 **，**50、100、\*\* 和 200\*\* 个按钮和表单提交功能不起作用。</span><span class="sxs-lookup"><span data-stu-id="53bfd-268">On the donation form, the \*\*50, 100, \*\* and **200** buttons and form submit functionality doesn't work when using the keyboard.</span></span>
* <span data-ttu-id="53bfd-269">键盘 Tab 键顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="53bfd-269">The keyboard tab order is incorrect.</span></span> <span data-ttu-id="53bfd-270">键 `Tab` 在边栏导航菜单前\*\*\*\* 浏览页面上的所有"更多"链接。</span><span class="sxs-lookup"><span data-stu-id="53bfd-270">The `Tab` key navigates through all the **More** links on the page before the sidebar navigation menu.</span></span>  <span data-ttu-id="53bfd-271">此顺序没有帮助，因为边栏导航旨在将你导航到该 `Tab` 页面的不同部分。</span><span class="sxs-lookup"><span data-stu-id="53bfd-271">This `Tab` order isn't helpful because the sidebar navigation is intended to take you to the different sections of that page.</span></span> 

<span data-ttu-id="53bfd-272">让我们使用 DevTools 分析这些问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-272">Let's analyze these problems using DevTools.</span></span>


## <a name="analyze-keyboard-accessibility-issues-using-devtools"></a><span data-ttu-id="53bfd-273">使用 DevTools 分析键盘辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-273">Analyze keyboard accessibility issues using DevTools</span></span>


### <a name="analyzing-the-lack-of-indication-of-keyboard-focus-in-the-sidebar-menu"></a><span data-ttu-id="53bfd-274">分析边栏菜单中缺少键盘焦点的指示</span><span class="sxs-lookup"><span data-stu-id="53bfd-274">Analyzing the lack of indication of keyboard focus in the sidebar menu</span></span>

<span data-ttu-id="53bfd-275">若要了解为什么边栏导航未按预期优化以用于键盘，请首先使用**Inspect**工具突出显示边栏导航菜单中的链接，然后在 DOM 树中向下钻取到 元素。 `a`</span><span class="sxs-lookup"><span data-stu-id="53bfd-275">To find out why the sidebar navigation isn't optimized as expected for use with keyboards, start by using the **Inspect** tool to highlight a link in the sidebar navigation menu, and then drill down in the DOM tree to the `a` element.</span></span> 

:::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="检查边栏导航菜单中的链接的源代码和应用样式" lightbox="../media/a11y-testing-menu-link.msft.png":::
    <span data-ttu-id="53bfd-277">检查边栏导航菜单中的链接的源代码和应用样式</span><span class="sxs-lookup"><span data-stu-id="53bfd-277">Inspecting the source code and the applied styles of a link in the sidebar navigation menu</span></span>
:::image-end:::

<span data-ttu-id="53bfd-278">在 **"样式** "选项卡中，可以看到应用于链接的 CSS，如果选择指向 的链接，文件将在"源" `styles.css` 工具 **中** 打开。</span><span class="sxs-lookup"><span data-stu-id="53bfd-278">In the **Styles** tab, you can see the CSS that's applied to the link, and if you select the link to `styles.css`, the file opens in the **Sources** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="应用于链接的样式，如"源"工具中所示" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
    <span data-ttu-id="53bfd-280">应用于链接的样式，如"源"工具中所示</span><span class="sxs-lookup"><span data-stu-id="53bfd-280">The styles that are applied to the link, shown in the Sources tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-281">在以上示例中，当您使用鼠标时，页面的样式包含菜单项上的状态，但键盘用户的 `hover` `focus` CSS 中没有任何状态。</span><span class="sxs-lookup"><span data-stu-id="53bfd-281">In the above example, the styles of the page include a `hover` state on the menu item when you use a mouse, but there's no `focus` state in the CSS for keyboard users.</span></span>  

<span data-ttu-id="53bfd-282">此外，此示例中的链接使用 `outline: none` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-282">Also, in this example, the links use `outline: none`.</span></span> <span data-ttu-id="53bfd-283">此样式用于删除浏览器在具有焦点和使用键盘时自动添加到元素中的轮廓。</span><span class="sxs-lookup"><span data-stu-id="53bfd-283">This style is used to remove the outline that's automatically added by browsers to elements when they have focus and keyboards are used.</span></span>  <span data-ttu-id="53bfd-284">若要避免此问题，请勿使用 `outline: none` 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-284">To avoid this problem, don't use `outline: none`.</span></span>

<span data-ttu-id="53bfd-285">有关详细演练步骤，请导航到分析边栏菜单中缺少 [键盘焦点的指示](test-analyze-no-focus-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-285">For detailed walkthrough steps, navigate to [Analyze the lack of indication of keyboard focus in a sidebar menu](test-analyze-no-focus-indicator.md).</span></span>


### <a name="analyzing-the-lack-of-keyboard-support-in-the-donation-form"></a><span data-ttu-id="53bfd-286">分析在资金表单中缺少键盘支持</span><span class="sxs-lookup"><span data-stu-id="53bfd-286">Analyzing the lack of keyboard support in the donation form</span></span>

<span data-ttu-id="53bfd-287">使用 元素实现"支持"表单上的按钮，而自动测试工具无法将元素识别 `div` 为表单上的控件。</span><span class="sxs-lookup"><span data-stu-id="53bfd-287">The buttons on the donation form are implemented using the `div` element, which is not recognized by automated testing tools as a control on a form.</span></span>

<span data-ttu-id="53bfd-288">若要调查这一点，可以使用 **"检查** "工具将鼠标悬停在"捐赠"表单的按钮上。</span><span class="sxs-lookup"><span data-stu-id="53bfd-288">To investigate this, you can use the **Inspect** tool to hover over the donation form's buttons.</span></span>  <span data-ttu-id="53bfd-289">结果是它们都不是键盘可访问的，如信息覆盖的 **键盘** 可聚焦行上的灰色圈所指示。</span><span class="sxs-lookup"><span data-stu-id="53bfd-289">The result is that none of them are keyboard-accessible, as indicated by the gray ring on the **Keyboard-focusable** line of the information overlay.</span></span>  <span data-ttu-id="53bfd-290">如信息覆盖的\*\*\*\*"名称\*\*\*\*"和"角色"行所示，"捐赠"表单的按钮也没有任何名称，其角色为 (表示或元素 `generic` `div` `span`) ，这意味着它们不能通过辅助技术访问。</span><span class="sxs-lookup"><span data-stu-id="53bfd-290">As shown in the **Name** and **Role** lines of the information overlay, the buttons of the donation form also have no name, and have a role of `generic` (representing `div` or `span` elements), which means they aren't accessible to assistive technology.</span></span>

:::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="检查表单的按钮时，会显示它们无法通过键盘访问" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
    <span data-ttu-id="53bfd-292">检查表单的按钮时，会显示它们无法通过键盘访问</span><span class="sxs-lookup"><span data-stu-id="53bfd-292">Inspecting the buttons of the form shows that they aren't keyboard-accessible</span></span>
:::image-end:::

<span data-ttu-id="53bfd-293">有关详细演练步骤，请导航到分析表单中 [缺少键盘支持](test-analyze-no-keyboard-support.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-293">For detailed walkthrough steps, navigate to [Analyze the lack of keyboard support in a form](test-analyze-no-keyboard-support.md).</span></span>

<span data-ttu-id="53bfd-294">如果选择" **打开"按钮** ，" **检查** "工具将您导航到 **"元素** "工具，然后显示表单的 HTML。</span><span class="sxs-lookup"><span data-stu-id="53bfd-294">If you select the **Donate** button, the **Inspect** tool takes you to the **Elements** tool and shows you the form's HTML.</span></span>

```HTML
<div class="donationrow">
    <div class="donationbutton">50</div>
    <div class="donationbutton">100</div>
    <div class="donationbutton">200</div>
</div>
<div class="donationrow">
    <label for="freedonation">Other</label>
    <input id="freedonation" class="smallinput">
</div>
<div class="donationrow">
    <div class="submitbutton">Donate</div>
</div>
```

<span data-ttu-id="53bfd-295">使用 和 元素是有效的，这导致标签能够正常使用，并且 `label` `input` `input` 文本框是键盘可访问的。</span><span class="sxs-lookup"><span data-stu-id="53bfd-295">The use of the `label` and `input` elements are valid, which result in the label working as intended and the `input` textbox is keyboard-accessible.</span></span>  <span data-ttu-id="53bfd-296">表单的其余部分使用 `div` 元素，这些元素易于设置样式，但没有任何语义含义。</span><span class="sxs-lookup"><span data-stu-id="53bfd-296">The rest of the form uses `div` elements, which are easy to style but have no semantic meaning.</span></span>

<span data-ttu-id="53bfd-297">接下来，我们分析表单的 JavaScript 功能。</span><span class="sxs-lookup"><span data-stu-id="53bfd-297">Next, let's analyze the form's JavaScript functionality.</span></span> <span data-ttu-id="53bfd-298">在 **"元素**"中，选择" **事件** 侦听器"选项卡以分析表单的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="53bfd-298">In **Elements**, select the **Event Listeners** tab to analyze the form's JavaScript.</span></span>

:::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text=""事件侦听器"选项卡，包含指向表单的 JavaScript 的链接" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
    <span data-ttu-id="53bfd-300">" **事件侦听器"** 选项卡，包含指向表单的 JavaScript 的链接</span><span class="sxs-lookup"><span data-stu-id="53bfd-300">The **Event Listeners** tab, with a link to the JavaScript for the form</span></span>
:::image-end:::

<span data-ttu-id="53bfd-301">在 **"事件侦听器**"选项卡上，选择链接以打开"源"工具，然后检查负责表单 `buttons.js:18` 功能的\*\*\*\* JavaScript。</span><span class="sxs-lookup"><span data-stu-id="53bfd-301">On the **Event Listeners** tab, select the `buttons.js:18` link to open the **Sources** tool, and then inspect the JavaScript that's responsible for the form's functionality.</span></span>

:::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="负责"接收"表单功能的 JavaScript，显示在"源"工具中" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
    <span data-ttu-id="53bfd-303">负责"接收"表单功能的 JavaScript，显示在" **源"工具** 中</span><span class="sxs-lookup"><span data-stu-id="53bfd-303">The JavaScript that's responsible for the donation form's functionality, shown in the **Sources** tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-304">`click`建议将事件与按钮一同使用，因为事件同时用于 `click` 鼠标指针和键盘。</span><span class="sxs-lookup"><span data-stu-id="53bfd-304">Using `click` events with buttons is recommended because `click` events work with both mouse pointers and keyboards.</span></span>  <span data-ttu-id="53bfd-305">但是，由于元素不可通过键盘访问，并且"完成"按钮作为元素实现，因此此 JavaScript 仅在使用鼠标 `div` \*\*\*\* `div` 时运行。</span><span class="sxs-lookup"><span data-stu-id="53bfd-305">However, because a `div` element isn't keyboard-accessible, and the **Donate** button is implemented as a `div` element, this JavaScript only runs when a mouse is used.</span></span>

<span data-ttu-id="53bfd-306">使用 `div` 作为按钮是一个经典示例，其中需要额外 JavaScript 才能创建元素 `button` 提供的功能。</span><span class="sxs-lookup"><span data-stu-id="53bfd-306">Using a `div` as a button is a classic example where extra JavaScript is needed to create functionality that `button` elements provide.</span></span> <span data-ttu-id="53bfd-307">因此，这会导致无法访问体验。</span><span class="sxs-lookup"><span data-stu-id="53bfd-307">As a result, this leads to an experience that is inaccessible.</span></span>


### <a name="checking-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a><span data-ttu-id="53bfd-308">检查辅助功能树是否支持键盘和屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="53bfd-308">Checking the Accessibility Tree for keyboard and screen reader support</span></span>

<span data-ttu-id="53bfd-309">使用 **Inspect** 工具单独检查页面上的每个元素非常耗时。</span><span class="sxs-lookup"><span data-stu-id="53bfd-309">Using the **Inspect** tool to individually check each element on the page is time-consuming.</span></span>  <span data-ttu-id="53bfd-310">相反，使用 **"辅助功能"** 选项卡导航页面的 **"辅助功能树"。**</span><span class="sxs-lookup"><span data-stu-id="53bfd-310">Instead, use the **Accessibility** tab to navigate the page's **Accessibility Tree**.</span></span>  <span data-ttu-id="53bfd-311">辅助功能树指示页面向辅助技术（如屏幕阅读器）提供哪些信息。</span><span class="sxs-lookup"><span data-stu-id="53bfd-311">The Accessibility Tree indicates what information the page provides to assistive technology such as screen readers.</span></span>

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="辅助功能树中的"资金"表单按钮" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    <span data-ttu-id="53bfd-313">辅助功能树中的"资金 **"表单按钮**</span><span class="sxs-lookup"><span data-stu-id="53bfd-313">Donation form button in the **Accessibility Tree**</span></span>
:::image-end:::

<span data-ttu-id="53bfd-314">树中没有名称或角色为 的任何元素都是问题，因为该元素对键盘用户或使用辅助技术的用户 `generic` 不可用。</span><span class="sxs-lookup"><span data-stu-id="53bfd-314">Any element in the tree that doesn't have a name, or that has a role of `generic`, is a problem, because that element won't be available to keyboard users or to people using assistive technology.</span></span>

<span data-ttu-id="53bfd-315">有关详细演练步骤，请导航到检查 [辅助功能树，获取键盘和屏幕阅读器支持](test-accessibility-tree.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-315">For detailed walkthrough steps, navigate to [Check the Accessibility Tree for keyboard and screen reader support](test-accessibility-tree.md).</span></span>


### <a name="analyzing-the-order-of-keyboard-access-to-sections-of-the-page"></a><span data-ttu-id="53bfd-316">分析键盘访问页面部分的顺序</span><span class="sxs-lookup"><span data-stu-id="53bfd-316">Analyzing the order of keyboard access to sections of the page</span></span>

<span data-ttu-id="53bfd-317">另一个问题就是页面上的 Tab 键顺序不明确。</span><span class="sxs-lookup"><span data-stu-id="53bfd-317">Another issue is the unclear tab order on the page.</span></span>  <span data-ttu-id="53bfd-318">键盘用户只有在按 Tab 键浏览整个页面的所有"更多"链接后 **才能到达边** 栏导航菜单。</span><span class="sxs-lookup"><span data-stu-id="53bfd-318">Keyboard users reach the sidebar navigation menu only after tabbing through all the **More** links throughout the entire page.</span></span>  <span data-ttu-id="53bfd-319">本示例中，边栏导航菜单旨在作为该页面不同分区的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="53bfd-319">In this example, the sidebar navigation menu is intended to be a shortcut to different sections of that page.</span></span>  <span data-ttu-id="53bfd-320">此 Tab 键顺序会导致用户体验不佳。</span><span class="sxs-lookup"><span data-stu-id="53bfd-320">This tab order leads to a poor user experience.</span></span> 

<span data-ttu-id="53bfd-321">混乱顺序的原因是它 `Tab` 由文档的源顺序确定。</span><span class="sxs-lookup"><span data-stu-id="53bfd-321">The reason for the confusing `Tab` order is that it is determined by the source order of the document.</span></span>  <span data-ttu-id="53bfd-322">也可通过使用元素上的 属性来修改 Tab 键顺序，该元素使该元素 `tabindex` 退出默认源顺序。</span><span class="sxs-lookup"><span data-stu-id="53bfd-322">The tab order can also be modified by using the `tabindex` attribute on an element which takes that element out of the default source order.</span></span>

<span data-ttu-id="53bfd-323">在文档的源代码中，边栏导航菜单显示在页面主要内容之后。</span><span class="sxs-lookup"><span data-stu-id="53bfd-323">In the source code of the document, the sidebar navigation menu appears after the main content of the page.</span></span>  <span data-ttu-id="53bfd-324">边栏导航菜单显示在页面主要内容的上方，仅仅是因为边栏导航菜单已使用 CSS 定位。</span><span class="sxs-lookup"><span data-stu-id="53bfd-324">The sidebar navigation menu appears above the main content of the page only because the sidebar navigation menu has been positioned using CSS.</span></span>

<span data-ttu-id="53bfd-325">文档的源顺序对于辅助技术非常重要，并且可能不同于元素在呈现页面上的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="53bfd-325">The source order of a document is important for assistive technology, and can be different than the order in which elements appear on the rendered page.</span></span>  <span data-ttu-id="53bfd-326">使用 CSS，您可以直观地对页面元素进行重新排序，但这并不意味着屏幕阅读器等辅助技术将按与 CSS 相同的顺序表示页面元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-326">Using CSS, you can re-order page elements in a visual way, but that doesn't mean that assistive technology such as screen readers would represent page elements in the same order as that CSS.</span></span>

<span data-ttu-id="53bfd-327">可以使用"辅助功能"选项卡中的"源 **顺序** 查看器"测试 **页面元素** 的顺序。 一直向下滚动，然后选中" **显示源订单"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="53bfd-327">You can test the order of page elements by using the **Source Order Viewer** in the **Accessibility** tab.  Scroll down all the way and select the **Show Source Order** checkbox.</span></span>  <span data-ttu-id="53bfd-328">现在，当您在 **"** 元素"工具中导航 DOM 树（如选择元素）时，数值覆盖显示在呈现的页面的表示源顺序的各个 `header` 部分。</span><span class="sxs-lookup"><span data-stu-id="53bfd-328">Now, when you navigate the DOM tree in the **Elements** tool, such as selecting the `header` element, numeric overlays are displayed on sections of the rendered page which represent the source order.</span></span> 

:::image type="complex" source="../media/a11y-testing-source-order-viewer.msft.png" alt-text="打开"源订单查看器"将显示源代码中元素在页面上作为数字覆盖的顺序" lightbox="../media/a11y-testing-source-order-viewer.msft.png":::
    <span data-ttu-id="53bfd-330">打开" **源订单** 查看器"将显示源代码中元素在页面上作为数字覆盖的顺序</span><span class="sxs-lookup"><span data-stu-id="53bfd-330">Turning on the **Source Order Viewer** shows the order of the elements in the source code as numeric overlays on the page</span></span>
:::image-end:::

<span data-ttu-id="53bfd-331">有关详细演练步骤，请导航到使用源顺序 [查看器测试键盘支持](test-tab-key-source-order-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-331">For detailed walkthrough steps, navigate to [Test keyboard support using the Source Order Viewer](test-tab-key-source-order-viewer.md).</span></span>


## <a name="testing-contrast-of-text-colors-in-various-states"></a><span data-ttu-id="53bfd-332">测试不同状态的文本颜色的对比度</span><span class="sxs-lookup"><span data-stu-id="53bfd-332">Testing contrast of text colors in various states</span></span>

<span data-ttu-id="53bfd-333">检查 **工具** 一次报告一个状态辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-333">The **Inspect** tool reports accessibility issues for one state at a time.</span></span>  <span data-ttu-id="53bfd-334">首先，我们将介绍使用 Inspect 工具仅查看页面元素的静态状态的限制。</span><span class="sxs-lookup"><span data-stu-id="53bfd-334">First, we'll describe the limitation of using the Inspect tool to view only the static state of a page element.</span></span>  <span data-ttu-id="53bfd-335">然后，我们将介绍如何检查页面元素的其他状态，通过在"样式"选项卡上选择"切换元素状态 (\*\*\：hov \*\*) 切换 **元素状态** "。</span><span class="sxs-lookup"><span data-stu-id="53bfd-335">Then we'll explain how to inspect other states of a page element, by selecting **\:hov (Toggle Element State)** on the **Styles** tab.</span></span>

### <a name="checking-text-color-contrast-in-the-default-state"></a><span data-ttu-id="53bfd-336">检查默认状态下的文本颜色对比度</span><span class="sxs-lookup"><span data-stu-id="53bfd-336">Checking text color contrast in the default state</span></span>

<span data-ttu-id="53bfd-337">除了问题工具中的自动颜色对比度测试之外，您还可以\*\*\*\* 使用**Inspect**工具检查各个页面元素是否具有足够的对比度。</span><span class="sxs-lookup"><span data-stu-id="53bfd-337">In addition to the automatic color-contrast tests in the **Issues** tool, you can also use the **Inspect** tool to check whether individual page elements have enough contrast.</span></span>  <span data-ttu-id="53bfd-338">如果对比度信息可用，" **检查** "覆盖层将显示对比率和复选框项。</span><span class="sxs-lookup"><span data-stu-id="53bfd-338">If contrast information is available, the **Inspect** overlay shows the contrast ratio and a checkbox item.</span></span>  <span data-ttu-id="53bfd-339">绿色选中标记图标表示对比度足够高，黄色警报图标表示对比度不足。</span><span class="sxs-lookup"><span data-stu-id="53bfd-339">A green check mark icon indicates there's enough contrast, and a yellow alert icon indicates not enough contrast.</span></span>

<span data-ttu-id="53bfd-340">例如，边栏导航菜单中的链接具有足够的对比度，但"参与状态"部分中的\*\*\*\* 绿色"动物"列表\*\*\*\* 项没有。</span><span class="sxs-lookup"><span data-stu-id="53bfd-340">For example, the links in the sidebar navigation menu have enough contrast, but the green **Dogs** list item in the **Donation status** section doesn't.</span></span>  <span data-ttu-id="53bfd-341">"检查"覆盖层中的警告标记了对比度 **不足** 的元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-341">An element that doesn't have enough contrast is flagged by a warning in the **Inspect** overlay.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="边栏导航菜单中的链接具有足够的对比度，如检查覆盖中所示" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            <span data-ttu-id="53bfd-343">边栏导航菜单中的链接具有足够的对比度，如检查**覆盖中所示**</span><span class="sxs-lookup"><span data-stu-id="53bfd-343">The links in the sidebar navigation menu have enough contrast, as shown in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text=""检查"覆盖层中的警告标记了对比度不足的元素" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            <span data-ttu-id="53bfd-345">"检查"覆盖层中的警告标记了对比度 **不足** 的元素</span><span class="sxs-lookup"><span data-stu-id="53bfd-345">An element that doesn't have enough contrast is flagged by a warning in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
:::row-end:::

<span data-ttu-id="53bfd-346">这样 **使用 Inspect** 工具并不能完全测试元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-346">Using the **Inspect** tool in this way doesn't fully test your elements.</span></span> <span data-ttu-id="53bfd-347">页面上的元素可能具有不同的状态，所有这些状态都需要进行测试。</span><span class="sxs-lookup"><span data-stu-id="53bfd-347">Elements on the page may have different states, all of which need to be tested.</span></span> <span data-ttu-id="53bfd-348">例如，如果将鼠标悬停在边栏导航菜单上，请注意更改链接颜色动画。</span><span class="sxs-lookup"><span data-stu-id="53bfd-348">For example, if you hover the mouse over the sidebar navigation menu, notice the animation which changes the color of the links.</span></span>

:::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="鼠标指针悬停在不同的菜单项上时显示不同的颜色" lightbox="../media/a11y-testing-hover.msft.png":::
    <span data-ttu-id="53bfd-350">鼠标指针悬停在不同的菜单项上时显示不同的颜色</span><span class="sxs-lookup"><span data-stu-id="53bfd-350">The menu item showing different colors when the mouse pointer is over it</span></span>
:::image-end:::

### <a name="verify-accessibility-of-all-states-of-elements-such-as-the-contrast-on-hover"></a><span data-ttu-id="53bfd-351">验证元素的所有状态（如悬停时对比度）的辅助功能</span><span class="sxs-lookup"><span data-stu-id="53bfd-351">Verify accessibility of all states of elements, such as the contrast on hover</span></span>

<span data-ttu-id="53bfd-352">使用 DevTools 时，你需要模拟元素的所有状态，因为 **Inspect** 工具不会同时显示所有状态的信息。</span><span class="sxs-lookup"><span data-stu-id="53bfd-352">When using the DevTools, you'll need to simulate all states of your element, because the **Inspect** tool doesn't display information for all states at the same time.</span></span> <span data-ttu-id="53bfd-353">本示例中，使用**Inspect**工具时，你无法到达边栏导航菜单上的"猫"链接的状态来分析状态中的对比率，因为样式中的状态 `hover` \*\*\*\* `hover` `hover` 不会触发。</span><span class="sxs-lookup"><span data-stu-id="53bfd-353">In this example, when using the **Inspect** tool, you can't reach the `hover` state of the **Cats** link on the sidebar navigation menu to analyze the contrast ratio in a `hover` state, because the `hover` state in your styles isn't triggered.</span></span>  <span data-ttu-id="53bfd-354">相反，你需要使用"样式"选项卡中的状态模拟来模拟 **"猫**"**菜单项的状态。**</span><span class="sxs-lookup"><span data-stu-id="53bfd-354">Instead, you need to simulate the state of the **Cats** menu item, by using the state simulation in the **Styles** tab.</span></span>

<span data-ttu-id="53bfd-355">有关详细演练步骤，请导航到验证元素 [的所有状态是否可访问](test-inspect-states.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-355">For detailed walkthrough steps, navigate to [Verify accessibility of all states of elements](test-inspect-states.md).</span></span>

<span data-ttu-id="53bfd-356">打开检查 **工具** ，然后在呈现的页面中，选择边栏导航菜单中的蓝色 **"猫** "链接。</span><span class="sxs-lookup"><span data-stu-id="53bfd-356">Turn on the **Inspect** tool and then in the rendered page, select the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="53bfd-357">将 **打开"** 元素"工具， `a` 同时在 DOM 树中选择元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-357">The **Elements** tool opens, with the `a` element selected in the DOM tree.</span></span>  <span data-ttu-id="53bfd-358">如果需要，在 DOM 树中，导航到 CSS 中 `hover` 具有状态的元素。</span><span class="sxs-lookup"><span data-stu-id="53bfd-358">If needed, in the DOM tree, navigate to the element that has a `hover` state in the CSS.</span></span>  <span data-ttu-id="53bfd-359">在这种情况下，元素 `a` 具有 `hover` 状态。</span><span class="sxs-lookup"><span data-stu-id="53bfd-359">In this case, the `a` element has a `hover` state.</span></span>

:::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="检查元素工具中具有悬停状态的元素" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
    <span data-ttu-id="53bfd-361">检查元素工具中具有悬停状态的元素</span><span class="sxs-lookup"><span data-stu-id="53bfd-361">Inspecting the element that has a hover state in the Elements tool</span></span>
:::image-end:::

<span data-ttu-id="53bfd-362">在" **样式"** 选项卡上，选择 \*\*"\：hov (切换元素状态) \*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="53bfd-362">On the **Styles** tab, select the **\:hov (Toggle Element State)** button.</span></span>  <span data-ttu-id="53bfd-363">然后使用 **"Force 元素状态** "复选框选择要模拟的状态。</span><span class="sxs-lookup"><span data-stu-id="53bfd-363">Then use the **Force element state** checkboxes to choose which state to simulate.</span></span>

:::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="显示所有选项的状态模拟功能" lightbox="../media/a11y-testing-state-simulation.msft.png":::
    <span data-ttu-id="53bfd-365">显示所有选项的状态模拟功能</span><span class="sxs-lookup"><span data-stu-id="53bfd-365">The state simulation feature showing all the options</span></span>
:::image-end:::

<span data-ttu-id="53bfd-366">选中 **\：hover** 复选框。</span><span class="sxs-lookup"><span data-stu-id="53bfd-366">Select the **\:hover** checkbox.</span></span>  <span data-ttu-id="53bfd-367">现在 DOM 元素旁边将出现一个黄色点，指示 DOM 元素具有模拟状态。</span><span class="sxs-lookup"><span data-stu-id="53bfd-367">A yellow dot now appears next to the DOM element, indicating that the DOM element has a simulated state.</span></span>  <span data-ttu-id="53bfd-368">此外，边栏导航菜单中的 **"猫** "链接现在在页面中突出显示，就像鼠标指针悬停在它上方一样。</span><span class="sxs-lookup"><span data-stu-id="53bfd-368">Also, the **Cats** link in the sidebar navigation menu is now highlighted in the page, as if the mouse pointer were hovering over it.</span></span>

:::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="模拟悬停状态的开发工具" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
    <span data-ttu-id="53bfd-370">模拟悬停状态的开发工具</span><span class="sxs-lookup"><span data-stu-id="53bfd-370">DevTools simulating a hover state</span></span>
:::image-end:::

<span data-ttu-id="53bfd-371">应用模拟状态后，可以再次使用 **Inspect** 工具在用户将鼠标悬停在元素上时检查元素的对比度。</span><span class="sxs-lookup"><span data-stu-id="53bfd-371">After the simulated state is applied, you can use the **Inspect** tool again to check the contrast of the element when the user hovers over it.</span></span>  <span data-ttu-id="53bfd-372">在这种情况下，对比度不够高。</span><span class="sxs-lookup"><span data-stu-id="53bfd-372">In this case, the contrast isn't high enough.</span></span>

:::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="在模拟悬停状态中测试元素的对比度" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
    <span data-ttu-id="53bfd-374">在模拟悬停状态中测试元素的对比度</span><span class="sxs-lookup"><span data-stu-id="53bfd-374">Testing the contrast of an element in a simulated hover state</span></span>
:::image-end:::

<span data-ttu-id="53bfd-375">状态模拟也是检查你是否认为不同的用户需求的一个好方法。</span><span class="sxs-lookup"><span data-stu-id="53bfd-375">State simulation is also a good way to check whether you considered different user needs.</span></span>  <span data-ttu-id="53bfd-376">对于边栏导航菜单，你可以检测 `:focus` 状态是否具有对比度问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-376">For the sidebar navigation menu, you can detect that the `:focus` state has a contrast issue.</span></span>


## <a name="use-the-rendering-tool-to-test-accessibility-for-visual-impairment"></a><span data-ttu-id="53bfd-377">使用呈现工具测试辅助功能视觉障碍</span><span class="sxs-lookup"><span data-stu-id="53bfd-377">Use the Rendering tool to test accessibility for visual impairment</span></span>

### <a name="check-contrast-issues-with-dark-theme-and-light-themes"></a><span data-ttu-id="53bfd-378">检查深色主题和浅色主题的对比度问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-378">Check contrast issues with dark theme and light themes</span></span>

<span data-ttu-id="53bfd-379">在颜色辅助功能方面的另一个注意事项是，可能需要测试不同的主题，以检查对比度问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-379">Another consideration when it comes to color accessibility is that there could be different themes that you need to test for contrast issues.</span></span>  <span data-ttu-id="53bfd-380">大多数操作系统具有深色模式和浅色模式。</span><span class="sxs-lookup"><span data-stu-id="53bfd-380">Most operating systems have a dark mode and a light mode.</span></span>  <span data-ttu-id="53bfd-381">网页可以使用 CSS 媒体查询对这些不同的设置做出反应。</span><span class="sxs-lookup"><span data-stu-id="53bfd-381">Your webpage can react to these different settings using CSS media queries.</span></span>

<span data-ttu-id="53bfd-382">此演示页面具有浅色和深色主题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-382">This demo page has a light and a dark theme.</span></span>  <span data-ttu-id="53bfd-383">通过使用呈现工具中的深色或浅色配色方案模拟，无需更改操作系统 [即可][DevToolsColorSchemeSimulation] 测试这两 **个主题** 。</span><span class="sxs-lookup"><span data-stu-id="53bfd-383">You can test both themes without changing your operating system, by using [Dark or light color scheme simulation][DevToolsColorSchemeSimulation] in the **Rendering** tool.</span></span>  <span data-ttu-id="53bfd-384">到目前为止，本文查看了使用深色主题设置的操作系统的演示页面。</span><span class="sxs-lookup"><span data-stu-id="53bfd-384">So far, this article looked at the demo page with an operating system using a dark theme setting.</span></span>  <span data-ttu-id="53bfd-385">如果我们改为模拟光线方案，然后刷新页面，问题工具将显示六\*\*\*\* 个颜色对比度问题，而不是两个。</span><span class="sxs-lookup"><span data-stu-id="53bfd-385">If we instead simulate a light scheme and then refresh the page, the **Issues** tool shows six color contrast problems instead of two.</span></span>

<span data-ttu-id="53bfd-386">有关详细演练步骤，请导航到检查深色主题和浅色主题 [的对比度问题](test-dark-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-386">For detailed walkthrough steps, navigate to [Check for contrast issues with dark theme and light theme](test-dark-mode.md).</span></span>


<span data-ttu-id="53bfd-387">在呈现工具中 **切换到浅色** 主题时，请注意以下项目。</span><span class="sxs-lookup"><span data-stu-id="53bfd-387">When switching to a light theme in the **Rendering** tool, notice the following items.</span></span>

*  <span data-ttu-id="53bfd-388">由于浅色主题更改，检测到新的对比度问题。</span><span class="sxs-lookup"><span data-stu-id="53bfd-388">New contrast issues are detected because of the change to light theme.</span></span>
*  <span data-ttu-id="53bfd-389">页面 **的整个"接收状态** "部分在浅色模式下不可读取。</span><span class="sxs-lookup"><span data-stu-id="53bfd-389">The entire **Donation Status** section of the page is unreadable in light mode.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="由于浅色主题更改而检测到的新对比度问题" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
            <span data-ttu-id="53bfd-391">由于浅色主题更改而检测到的新对比度问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-391">New contrast issues detected because of the change to light theme</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="在浅色模式下标记为对比度问题的接收状态项目" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
            <span data-ttu-id="53bfd-393">在浅色模式下标记为对比度问题的接收状态项目</span><span class="sxs-lookup"><span data-stu-id="53bfd-393">The donation status items flagged as contrast issues when in light mode</span></span> :::image-end:::
    :::column-end:::
:::row-end:::


### <a name="verify-that-the-webpage-is-usable-by-people-with-color-blindness"></a><span data-ttu-id="53bfd-394">验证网页是否对色盲者可用</span><span class="sxs-lookup"><span data-stu-id="53bfd-394">Verify that the webpage is usable by people with color blindness</span></span>

<span data-ttu-id="53bfd-395">不同的接收状态使用红色 (绿色、黄色) 颜色作为区分资金状态的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="53bfd-395">The different donation states use color (red, green, yellow) as the only means to differentiate between the states of funding.</span></span>  <span data-ttu-id="53bfd-396">但是，你无法预期所有用户都体验这些颜色。</span><span class="sxs-lookup"><span data-stu-id="53bfd-396">You can't expect all of your users to experience these colors as intended, though.</span></span>  <span data-ttu-id="53bfd-397">如果你使用 DevTools 的视觉缺陷模拟功能，则通过模拟不同视觉的人如何理解你的设计，你可以发现这不够好。 [][DevToolsVisionDeficiencies]</span><span class="sxs-lookup"><span data-stu-id="53bfd-397">If you use the [vision deficiencies emulation][DevToolsVisionDeficiencies] feature of DevTools, you can find out that this is not good enough, by simulating how people with different vision would perceive your design.</span></span>
<span data-ttu-id="53bfd-398">有关详细演练步骤，请导航到验证页面是否适用于色 [盲用户](test-color-blindness.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-398">For detailed walkthrough steps, navigate to [Verify that the page is usable by people with color blindness](test-color-blindness.md).</span></span>
:::image type="complex" source="../media/a11y-testing-simulating-protanopia.msft.png" alt-text="将页面显示为具有亚特 <9> <9>色 (色盲) 可以看到页面" lightbox="../media/a11y-testing-simulating-protanopia.msft.png":::
    <span data-ttu-id="53bfd-400">显示页面，就像有亚特 <9>色 (色盲) 会看到页面</span><span class="sxs-lookup"><span data-stu-id="53bfd-400">Showing the page as if someone with protanopia (red color blindness) would see it</span></span>
:::image-end:::



### <a name="verify-that-the-webpage-is-usable-with-blurred-vision"></a><span data-ttu-id="53bfd-401">验证网页是否具有模糊视觉</span><span class="sxs-lookup"><span data-stu-id="53bfd-401">Verify that the webpage is usable with blurred vision</span></span>

<span data-ttu-id="53bfd-402">呈现工具的另一 **个** 有趣功能是，你可以模拟模糊的视觉。</span><span class="sxs-lookup"><span data-stu-id="53bfd-402">Another interesting feature of the **Rendering** tool is that you can simulate blurred vision.</span></span>  <span data-ttu-id="53bfd-403">如果我们从"模拟\*\*\*\* 视觉缺陷"下拉列表中选择"\*\*\*\* 模糊视觉"选项，可以看到上菜单中文本上的投影使阅读菜单项变得困难。</span><span class="sxs-lookup"><span data-stu-id="53bfd-403">If we choose the **Blurred vision** option from the **Emulate vision deficiencies** dropdown list, we can see that the drop shadow on the text in the upper menu makes it hard to read the menu items.</span></span>
<span data-ttu-id="53bfd-404">有关详细的演练步骤，请导航到验证 [页面是否可用模糊的视觉](test-blurred-vision.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-404">For detailed walkthrough steps, navigate to [Verify that the page is usable with blurred vision](test-blurred-vision.md).</span></span>

:::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="模拟模糊的页面可能会发现辅助功能问题" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
    <span data-ttu-id="53bfd-406">模拟模糊的页面可能会发现辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="53bfd-406">Simulating a blurred page can reveal accessibility issues</span></span>
:::image-end:::


### <a name="verify-that-the-page-is-usable-with-ui-animation-turned-off-reduced-motion"></a><span data-ttu-id="53bfd-407">验证页面是否可用，并关闭 UI 动画， (运动) </span><span class="sxs-lookup"><span data-stu-id="53bfd-407">Verify that the page is usable with UI animation turned off (reduced motion)</span></span>

<span data-ttu-id="53bfd-408">这些天操作系统提供的另一个设置是关闭动画的方法。</span><span class="sxs-lookup"><span data-stu-id="53bfd-408">Another setting that operating systems come with these days are a way to turn off animations.</span></span>  <span data-ttu-id="53bfd-409">动画可以帮助产品的可用性，但它们也会导致许多问题，包括混淆和混乱。</span><span class="sxs-lookup"><span data-stu-id="53bfd-409">Animations can help the usability of a product, but they can also cause a lot of problems, ranging from confusion to nausea.</span></span> <span data-ttu-id="53bfd-410">这就是产品不应向在操作系统中关闭动画的用户显示动画的原因。</span><span class="sxs-lookup"><span data-stu-id="53bfd-410">That's why your products should not show animations to users who turned them off in the operating system.</span></span>  <span data-ttu-id="53bfd-411">通过使用 CSS 媒体查询，您可以检查用户是否希望查看动画，并相应地将其关闭。</span><span class="sxs-lookup"><span data-stu-id="53bfd-411">By using a CSS media query, you can check whether the user wants to see animations, and turn them off accordingly.</span></span>  <span data-ttu-id="53bfd-412">而且，与深色和浅色模式很类似，有一种方法可以模拟使用 [DevTools 的减少运动][DevToolsReducedMotion]。</span><span class="sxs-lookup"><span data-stu-id="53bfd-412">And, much like with dark and light mode, there is a way to [simulate reduced motion using DevTools][DevToolsReducedMotion].</span></span>

<span data-ttu-id="53bfd-413">在此处的演示页中，当你选择边栏导航菜单的不同部分时，关闭动画将停止页面的平滑滚动。</span><span class="sxs-lookup"><span data-stu-id="53bfd-413">In the demo page here, turning off animations will stop the smooth scrolling of the page when you select different parts of the sidebar navigation menu.</span></span>  <span data-ttu-id="53bfd-414">这可以通过在媒体查询中将平滑滚动设置包装在 CSS 中实现：</span><span class="sxs-lookup"><span data-stu-id="53bfd-414">This is achieved by wrapping the smooth scrolling setting in CSS in a media query:</span></span>

:::image type="complex" source="../media/a11y-testing-simulating-reduced-motion.msft.png" alt-text="模拟减少运动和 CSS，以确保仅在用户需要时发生平滑滚动" lightbox="../media/a11y-testing-simulating-reduced-motion.msft.png":::
    <span data-ttu-id="53bfd-416">模拟减少运动和 CSS，以确保仅在用户需要时发生平滑滚动</span><span class="sxs-lookup"><span data-stu-id="53bfd-416">Simulating reduced motion and the CSS that makes sure that smooth scrolling only happens when the user wants it</span></span>
:::image-end:::

```css
@media (prefers-reduced-motion: no-preference) {
  html {
    scroll-behavior: smooth;
  }
}
```

<span data-ttu-id="53bfd-417">此 CSS 媒体查询有条件地运行"平滑滚动"动画。</span><span class="sxs-lookup"><span data-stu-id="53bfd-417">This CSS media query conditionally runs the "smooth scrolling" animation.</span></span>  <span data-ttu-id="53bfd-418">但是顶部导航栏、边栏导航菜单和更多链接的动画仍然\*\*\*\* 运行，即使用户不想看到动画。</span><span class="sxs-lookup"><span data-stu-id="53bfd-418">But the animation of the top navigation bar, sidebar navigation menu, and **More** links still run, even when the user doesn't want to see animations.</span></span> <span data-ttu-id="53bfd-419">这些其他动画需要有条件地运行，例如通过添加其他媒体查询。</span><span class="sxs-lookup"><span data-stu-id="53bfd-419">Those other animations need to be conditionally run, such as by adding additional media queries.</span></span>

<span data-ttu-id="53bfd-420">有关详细的演练步骤，请导航到验证页面是否可用，并关闭 [UI 动画](test-reduced-ui-motion.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-420">For detailed walkthrough steps, navigate to [Verify that the page is usable with UI animation turned off](test-reduced-ui-motion.md).</span></span>


## <a name="what-to-do-next"></a><span data-ttu-id="53bfd-421">下一步该怎么办？</span><span class="sxs-lookup"><span data-stu-id="53bfd-421">What to do next?</span></span>

<span data-ttu-id="53bfd-422">我们介绍了许多可用于确保捕获产品中的辅助功能问题的工具。</span><span class="sxs-lookup"><span data-stu-id="53bfd-422">We've covered quite a few tools you can use to make sure that you catch accessibility problems in your products.</span></span>  <span data-ttu-id="53bfd-423">这些工具的范围从自动检查和手动详细检查到不同状态和环境的模拟。</span><span class="sxs-lookup"><span data-stu-id="53bfd-423">Such tools range from automated checks and manual detail checks to simulation of different states and environments.</span></span>  <span data-ttu-id="53bfd-424">这些工具汇总在 [DevTools 中的辅助功能测试功能中](reference.md)。</span><span class="sxs-lookup"><span data-stu-id="53bfd-424">These tools are summarized in [Accessibility-testing features in DevTools](reference.md).</span></span>  <span data-ttu-id="53bfd-425">自动化工具无法找到产品的所有问题，因为许多辅助功能障碍仅在交互式使用期间出现。</span><span class="sxs-lookup"><span data-stu-id="53bfd-425">Automated tools can't find all the problems in a product, because many of the accessibility barriers show up only during interactive use.</span></span>

<span data-ttu-id="53bfd-426">这些工具均无法将正确的一轮产品测试替换为使用辅助技术并遵循检查所有所需测试的计划。</span><span class="sxs-lookup"><span data-stu-id="53bfd-426">None of these tools can replace a proper round of testing your products with people that use assistive technologies and following a plan to check for all the required tests.</span></span> <span data-ttu-id="53bfd-427">此外，您还可以使用[辅助功能][AccessibilityInsightsAssessment]评估[Insights。][AccessibilityInsights]</span><span class="sxs-lookup"><span data-stu-id="53bfd-427">You can also use the [Assessments][AccessibilityInsightsAssessment] feature of [Accessibility Insights][AccessibilityInsights].</span></span>  <span data-ttu-id="53bfd-428">您可能需要执行其他检查，例如：</span><span class="sxs-lookup"><span data-stu-id="53bfd-428">You may need to perform additional checks such as:</span></span>

* <span data-ttu-id="53bfd-429">放大时进行测试。</span><span class="sxs-lookup"><span data-stu-id="53bfd-429">Testing when zoomed-in.</span></span>
* <span data-ttu-id="53bfd-430">使用屏幕阅读器进行测试。</span><span class="sxs-lookup"><span data-stu-id="53bfd-430">Testing with screen readers.</span></span>
* <span data-ttu-id="53bfd-431">使用语音识别进行测试。</span><span class="sxs-lookup"><span data-stu-id="53bfd-431">Testing with voice recognition.</span></span>
* <span data-ttu-id="53bfd-432">在高对比度模式下进行测试。</span><span class="sxs-lookup"><span data-stu-id="53bfd-432">Testing in high-contrast mode.</span></span>

<span data-ttu-id="53bfd-433">了解改进 Web 产品的方法的另一个方法为使用[webhint 扩展Visual Studio Code。][WebhintForCode]</span><span class="sxs-lookup"><span data-stu-id="53bfd-433">Another way to find out what to do to improve your web product is to use the [webhint extension for Visual Studio Code][WebhintForCode].</span></span>  <span data-ttu-id="53bfd-434">此扩展标记源代码中易检测到的辅助功能问题，并提供了如何修复这些问题的见解。</span><span class="sxs-lookup"><span data-stu-id="53bfd-434">This extension flags the readily detectable accessibility problems in your source code and gives insights on how to fix them.</span></span>

:::image type="complex" source="../media/a11y-testing-webhint-in-vs-code.msft.png" alt-text="Webhint in Visual Studio Code， showing an accessibility issue by underlining the HTML element and showing an explanation of the problem" lightbox="../media/a11y-testing-webhint-in-vs-code.msft.png":::
    <span data-ttu-id="53bfd-436">Webhint in Visual Studio Code， showing an accessibility issue by underlining the HTML element and showing an explanation of the problem</span><span class="sxs-lookup"><span data-stu-id="53bfd-436">Webhint in Visual Studio Code, showing an accessibility issue by underlining the HTML element and showing an explanation of the problem</span></span>
:::image-end:::

<span data-ttu-id="53bfd-437">We're constantly working on new accessibility features for DevTools.</span><span class="sxs-lookup"><span data-stu-id="53bfd-437">We're constantly working on new accessibility features for DevTools.</span></span>  <span data-ttu-id="53bfd-438">如果缺少任何内容，请给我们发送消息，并告诉我们我们可以做什么。</span><span class="sxs-lookup"><span data-stu-id="53bfd-438">If there is anything you are missing, send us a message and tell us what we can do.</span></span>


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="53bfd-439">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="53bfd-439">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]


<!-- links -->
[DevToolsMediaQueries]: ../device-mode/index.md#show-media-queries "显示媒体查询 - 在 DevTools Microsoft Edge中模拟移动设备|Microsoft Docs"
[DevToolsDeviceModeIndex]: ../device-mode/index.md "在 Microsoft Edge 开发人员工具中模拟移动设备 | Microsoft Docs"
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "深色或浅色配色方案模拟|Microsoft Docs"
[DevToolsIssuesTool]: ../issues/index.md "使用问题工具查找并修复|Microsoft Docs"
[DevToolsReducedMotion]: ./reduced-motion-simulation.md "减少运动模拟|Microsoft Docs"
[DevToolsVisionDeficiencies]: ./emulate-vision-deficiencies.md "模拟视觉缺陷|Microsoft Docs"
<!-- links into test-issues-tool.md -->
[DevToolsAccessibilityTestIssuesToolViewAccSection]: test-issues-tool.md#view-the-accessibility-section-of-the-issues-tool "查看问题工具的辅助功能部分 - 自动测试网页的辅助功能问题|Microsoft Docs"
[DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]: test-issues-tool.md#verify-that-input-fields-have-labels "验证输入字段是否包含标签 - 自动测试网页的辅助功能|Microsoft Docs" 
[DevtoolsAccessibilityTestIssuesToolCheckAltText]: test-issues-tool.md#verify-that-images-have-alt-text "验证图像是否包含替换文字 - 自动测试网页的辅助功能|Microsoft Docs "
[DevtoolsAccessibilityTestIssuesToolCheckContrast]: test-issues-tool.md#verify-that-text-colors-have-enough-contrast "验证文本颜色是否具有足够的对比度 - 自动测试网页的辅助功能问题|Microsoft Docs"
<!-- links into test-inspect-tool.md -->
[DevtoolsAccessibilityTestInspectToolColorHighlighting]: test-inspect-tool.md#identify-nested-regions-using-color-highlighting "使用颜色突出显示标识嵌套区域 - 使用&quot;检查&quot;工具通过将鼠标悬停在网页上方来检测|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolIndivElems]: test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support "检查各个元素的文本对比度、屏幕阅读器文本和键盘支持 - 使用 Inspect 工具通过将鼠标悬停在网页页面上方来检测|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolDomCss]: test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css "使用&quot;检查&quot;工具将鼠标悬停在网页上方以突出显示 DOM 和 CSS - 使用&quot;检查&quot;工具通过将鼠标悬停在网页上方来检测|Microsoft Docs"
<!-- external links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "对比率|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web 内容辅助功能指南|W3C"
[AccessibilityInsightsAssessment]: https://accessibilityinsights.io/docs/en/web/getstarted/assessment/ "Web 应用程序辅助功能Insights中的|辅助功能Insights"
[AccessibilityInsights]: https://accessibilityinsights.io "辅助功能Insights"
[Lighthouse]: https://developers.google.com/web/tools/lighthouse/ "浅|Google"
[WebhintForCode]:https://aka.ms/webhint4code "webhint |Visual StudioMarketplace"
