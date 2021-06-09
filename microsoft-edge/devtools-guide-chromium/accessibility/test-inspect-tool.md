---
description: 将鼠标悬停在网页上方，使用"检查"工具检测辅助功能问题。
title: 使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: c95116d38e5b0bda88af43ef8bfde4204b8cb372
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597255"
---
# <a name="use-the-inspect-tool-to-detect-accessibility-issues-by-hovering-over-the-webpage"></a><span data-ttu-id="75904-104">使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="75904-104">Use the Inspect tool to detect accessibility issues by hovering over the webpage</span></span>

<span data-ttu-id="75904-105">当您 **将** 鼠标悬停在呈现的网页上时，Inspect 工具将显示有关各个元素的信息，包括辅助功能信息。</span><span class="sxs-lookup"><span data-stu-id="75904-105">The **Inspect** tool displays information about individual elements as you hover over the rendered webpage, including accessibility information.</span></span>
<span data-ttu-id="75904-106">相比之下，" **问题"** 工具会自动报告整个网页的问题。</span><span class="sxs-lookup"><span data-stu-id="75904-106">In contrast, the **Issues** tool automatically reports issues for the entire webpage.</span></span>

<span data-ttu-id="75904-107">检查 **工具** 按钮 \ (Inspect ![ ](../media/inspect-icon.msft.png) \) 位于 DevTools 的左上角。</span><span class="sxs-lookup"><span data-stu-id="75904-107">The **Inspect** tool button \(![Inspect](../media/inspect-icon.msft.png)\) is in the upper-left corner of DevTools.</span></span>  <span data-ttu-id="75904-108">选择" **检查工具"** 按钮时，该按钮将变为蓝色，指示 **"检查** "工具处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="75904-108">When you select the **Inspect** tool button, the button turns blue, indicating that the **Inspect** tool is active.</span></span>

<span data-ttu-id="75904-109">当 **Inspect 工具** 处于活动状态时，将鼠标悬停在呈现网页上的任何元素上将显示 **Inspect** 覆盖。</span><span class="sxs-lookup"><span data-stu-id="75904-109">When the **Inspect** tool is active, hovering over any element on the rendered webpage displays the **Inspect** overlay.</span></span> <span data-ttu-id="75904-110">此覆盖层显示有关该元素的常规信息和辅助功能信息。</span><span class="sxs-lookup"><span data-stu-id="75904-110">This overlay displays general information and accessibility information about that element.</span></span>  <span data-ttu-id="75904-111">"**检查"覆盖\*\*\*\*层的**"辅助功能"部分显示有关文本颜色对比度、屏幕阅读器文本和键盘支持的信息。</span><span class="sxs-lookup"><span data-stu-id="75904-111">The **Accessibility** section of the **Inspect** overlay displays information about text-color contrast, screen reader text, and keyboard support.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="Inspect 工具，将元素的区域作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    <span data-ttu-id="75904-113">**Inspect**工具，将元素的区域作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示</span><span class="sxs-lookup"><span data-stu-id="75904-113">The **Inspect** tool, showing the element's area as a multicolor overlay, and showing the element's details as a large information overlay</span></span>
:::image-end:::


## <a name="check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a><span data-ttu-id="75904-114">检查各个元素的文本对比度、屏幕阅读器文本和键盘支持</span><span class="sxs-lookup"><span data-stu-id="75904-114">Check individual elements for text contrast, screen reader text, and keyboard support</span></span>

<!-- Inspect tool: Accessibility section of overlay -->

1.  <span data-ttu-id="75904-115">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="75904-115">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="75904-116">选择\*\*\*\* DevTools 左上角的"检查 \ (检查 \) "按钮，使图标突出显示为蓝色 ![ ](../media/inspect-icon.msft.png) () 。</span><span class="sxs-lookup"><span data-stu-id="75904-116">Select the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

    :::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="若要打开"检查"工具，请选择"检查"按钮" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
        <span data-ttu-id="75904-118">若要打开"检查 **"** 工具，请选择" **检查"** 按钮</span><span class="sxs-lookup"><span data-stu-id="75904-118">To turn on the **Inspect** tool, select the **Inspect** button</span></span>
    :::image-end:::

1.  <span data-ttu-id="75904-119">将鼠标悬停在呈现的演示网页中的任意元素上。</span><span class="sxs-lookup"><span data-stu-id="75904-119">Hover over any element in the rendered demo webpage.</span></span>  <span data-ttu-id="75904-120">Inspect **工具** 在呈现的网页中的 元素下方显示信息覆盖层。</span><span class="sxs-lookup"><span data-stu-id="75904-120">The **Inspect** tool shows an information overlay below the element within the rendered webpage.</span></span>

    :::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="Inspect 工具，将元素的布局作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
        <span data-ttu-id="75904-122">**Inspect**工具，将元素的布局作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示</span><span class="sxs-lookup"><span data-stu-id="75904-122">The **Inspect** tool, showing the element's layout as a multicolor overlay, and showing the element's details as a large information overlay</span></span>
    :::image-end:::

<span data-ttu-id="75904-123">检查覆盖 **的底部有** 一个 **辅助功能** 部分，其中包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="75904-123">The bottom part of the **Inspect** overlay has an **Accessibility** section that contains the following information:</span></span>

*   <span data-ttu-id="75904-124">**对比度** 定义低视力用户能否理解元素。</span><span class="sxs-lookup"><span data-stu-id="75904-124">**Contrast** defines whether an element can be understood by people with low vision.</span></span>  <span data-ttu-id="75904-125">[WCAG][WCAG]准则定义的对比率指示是否有足够的对比度 (绿色选中标记图标) 或 (橙色感叹号-点) 。 [][W3CContrastRatio]</span><span class="sxs-lookup"><span data-stu-id="75904-125">The [contrast ratio][W3CContrastRatio] as defined by the [WCAG Guidelines][WCAG] indicates whether there is enough contrast (a green check mark icon) or not enough (an orange exclamation-point icon).</span></span>

*   <span data-ttu-id="75904-126">**名称和\*\*\*\*角色**是屏幕阅读器等辅助技术将报告有关元素的内容。</span><span class="sxs-lookup"><span data-stu-id="75904-126">**Name** and **Role** are what assistive technology such as screen readers will report about the element.</span></span>
    *   <span data-ttu-id="75904-127">**Name**是元素的文本 `a` 内容。</span><span class="sxs-lookup"><span data-stu-id="75904-127">The **Name** is the text content of an `a` element.</span></span>  <span data-ttu-id="75904-128">对于 元素 `<a href="/">About Us</a>` **，Inspect** 工具中显示的 Name 为"关于我们"。</span><span class="sxs-lookup"><span data-stu-id="75904-128">For the element `<a href="/">About Us</a>`, the **Name** shown in the Inspect tool is "About Us".</span></span>
    *   <span data-ttu-id="75904-129">**元素**的角色。</span><span class="sxs-lookup"><span data-stu-id="75904-129">The **Role** of the element.</span></span>  <span data-ttu-id="75904-130">这通常是元素名称，如 `article` `img` 、、 `link` 或 `heading` 。</span><span class="sxs-lookup"><span data-stu-id="75904-130">This is usually the element name, such as `article`, `img` , `link`, or `heading`.</span></span>  <span data-ttu-id="75904-131">`div`和 `span` 元素称为 `generic` 。</span><span class="sxs-lookup"><span data-stu-id="75904-131">The `div` and `span` elements are referred to as `generic`.</span></span>

*   <span data-ttu-id="75904-132">**键盘可聚焦** 指示用户是否可以访问元素，而不考虑输入设备。</span><span class="sxs-lookup"><span data-stu-id="75904-132">**Keyboard-focusable** indicates whether users can reach the element regardless of input device.</span></span>
    *   <span data-ttu-id="75904-133">绿色选中标记图标指示元素是键盘可聚焦的。</span><span class="sxs-lookup"><span data-stu-id="75904-133">A green check mark icon indicates that the element is keyboard-focusable.</span></span>
    *   <span data-ttu-id="75904-134">带对角线的灰色圆圈表示元素不可通过键盘聚焦。</span><span class="sxs-lookup"><span data-stu-id="75904-134">A gray circle with diagonal line indicates that the element isn't keyboard-focusable.</span></span>


## <a name="additional-information-in-the-inspect-overlay"></a><span data-ttu-id="75904-135">检查覆盖层中的附加信息</span><span class="sxs-lookup"><span data-stu-id="75904-135">Additional information in the Inspect overlay</span></span>

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

<span data-ttu-id="75904-136">"检查"覆盖**的顶部**（位于"辅助功能"部分上方\*\*\*\*）列出了元素的以下详细信息。</span><span class="sxs-lookup"><span data-stu-id="75904-136">The top part of the **Inspect** overlay, which is above the **Accessibility** section, lists the following details of the element.</span></span>

*   <span data-ttu-id="75904-137">布局类型。</span><span class="sxs-lookup"><span data-stu-id="75904-137">Layout type.</span></span> <span data-ttu-id="75904-138">如果元素是使用弹性框或网格放置的，则图标 \ (</span><span class="sxs-lookup"><span data-stu-id="75904-138">If the element is positioned using a flexbox or grid, an icon \(</span></span>![网格布局图标](../media/grid-icon.msft.png)<span data-ttu-id="75904-140">\) 显示。</span><span class="sxs-lookup"><span data-stu-id="75904-140">\) is displayed.</span></span>
*   <span data-ttu-id="75904-141">元素的名称，如 、 `h1` `h2` 或 `div` 。</span><span class="sxs-lookup"><span data-stu-id="75904-141">Name of the element, such as `h1`, `h2`, or `div`.</span></span>
*   <span data-ttu-id="75904-142">元素的尺寸（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="75904-142">The dimensions of the element in pixels.</span></span>
*   <span data-ttu-id="75904-143">作为颜色样本的颜色颜色 (或较小的、彩色的) 和字符串形式 (如 `#336699`) 。</span><span class="sxs-lookup"><span data-stu-id="75904-143">The color as a color swatch (or a small, colored square) and as a string (such as `#336699`).</span></span>
*   <span data-ttu-id="75904-144">字体信息，如大小和字体系列。</span><span class="sxs-lookup"><span data-stu-id="75904-144">Font information, such as size and font families.</span></span>
*   <span data-ttu-id="75904-145">边距和填充（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="75904-145">Margin and padding in pixels.</span></span>


## <a name="identify-nested-regions-using-color-highlighting"></a><span data-ttu-id="75904-146">使用颜色突出显示标识嵌套区域</span><span class="sxs-lookup"><span data-stu-id="75904-146">Identify nested regions using color highlighting</span></span> 

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

<span data-ttu-id="75904-147">除了信息覆盖之外 **，Inspect** 工具还提供区域颜色，类似于在"元素"工具的 DOM 树 **中** 悬停。</span><span class="sxs-lookup"><span data-stu-id="75904-147">In addition to the information overlay, the **Inspect** tool also provides region-coloring that's similar to hovering in the DOM tree in the **Elements** tool.</span></span>

1.  <span data-ttu-id="75904-148">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="75904-148">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="75904-149">选择\*\*\*\* DevTools 左上角的"检查"按钮 \ (Inspect 工具图标 \) ，使按钮突出显示为蓝色 ![ ](../media/inspect-icon.msft.png) () 。</span><span class="sxs-lookup"><span data-stu-id="75904-149">Select the **Inspect** button \(![Inspect tool icon](../media/inspect-icon.msft.png)\) in the top-left corner of DevTools, so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="75904-150">将鼠标悬停在呈现的演示网页的不同部分上。</span><span class="sxs-lookup"><span data-stu-id="75904-150">Hover over different parts of the rendered demo webpage.</span></span>  <span data-ttu-id="75904-151">网页中的每个元素现在都显示一个多色覆盖。</span><span class="sxs-lookup"><span data-stu-id="75904-151">Each element in the webpage now displays with a multicolor overlay.</span></span> <span data-ttu-id="75904-152">此多色覆盖层可以显示元素内部的嵌套区域。</span><span class="sxs-lookup"><span data-stu-id="75904-152">This multicolor overlay can display nested regions inside of an element.</span></span> <span data-ttu-id="75904-153">例如，将鼠标悬停在"猫"的 **左边距上**。</span><span class="sxs-lookup"><span data-stu-id="75904-153">For example, hover over the left margin of **Cats**.</span></span>  <span data-ttu-id="75904-154">Inspect **工具** 使用不同颜色突出显示 **"猫** "部分的几个矩形部分，显示来自网页上 CSS 弹性框定义的布局。</span><span class="sxs-lookup"><span data-stu-id="75904-154">The **Inspect** tool highlights several rectangular portions of the **Cats** section with different colors, showing the layout that results from the CSS flexbox definitions on your webpage.</span></span>

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="使用 Inspect 工具时的多色弹性框覆盖和信息覆盖" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    <span data-ttu-id="75904-156">使用 Inspect 工具时的多色弹性框覆盖 **和信息** 覆盖</span><span class="sxs-lookup"><span data-stu-id="75904-156">Multicolor flexbox overlay and information overlay when using the **Inspect** tool</span></span>
:::image-end:::

<span data-ttu-id="75904-157">若要配置网格覆盖或弹性框覆盖，请在 **"元素**"工具中选择"布局 **"** 选项卡。 有关详细信息，请导航到"[检查 CSS 网格"。](..\css\grid.md)</span><span class="sxs-lookup"><span data-stu-id="75904-157">To configure the grid overlay or flexbox overlay, in the **Elements** tool, select the **Layout** tab.  For more information, navigate to [Inspect CSS Grid](..\css\grid.md).</span></span>


## <a name="use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a><span data-ttu-id="75904-158">使用"检查"工具将鼠标悬停在网页上方以突出显示 DOM 和 CSS</span><span class="sxs-lookup"><span data-stu-id="75904-158">Use the Inspect tool to hover over the webpage to highlight the DOM and CSS</span></span>

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

1.  <span data-ttu-id="75904-159">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="75904-159">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="75904-160">选择\*\*\*\* DevTools (左上角的"检查"按钮 \) "检查"工具 \) ，以便该按钮突出显示为 (![ ](../media/inspect-icon.msft.png) 蓝色) 。</span><span class="sxs-lookup"><span data-stu-id="75904-160">Select the **Inspect** button \(![the Inspect tool](../media/inspect-icon.msft.png)\) in the top-left corner of DevTools, so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="75904-161">选择" **元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="75904-161">Select the **Elements** tool.</span></span>

1.  <span data-ttu-id="75904-162">在 **"检查** "工具处于活动状态时，将鼠标悬停在呈现的网页的不同部分上。</span><span class="sxs-lookup"><span data-stu-id="75904-162">With the **Inspect** tool active, hover over different parts of the rendered webpage.</span></span>  <span data-ttu-id="75904-163">在 **"元素** "工具中，HTML DOM 树会自动展开以显示有关您将鼠标悬停在的元素的信息。</span><span class="sxs-lookup"><span data-stu-id="75904-163">In the **Elements** tool, the HTML DOM tree automatically expands to show information about the element you hover over.</span></span>  <span data-ttu-id="75904-164">悬停不会导致" **样式"** 窗格更新。</span><span class="sxs-lookup"><span data-stu-id="75904-164">Hovering doesn't cause the **Styles** pane to update.</span></span>

1.  <span data-ttu-id="75904-165">现在，选择呈现的网页内的任何元素。</span><span class="sxs-lookup"><span data-stu-id="75904-165">Now select any element within the rendered webpage.</span></span>  <span data-ttu-id="75904-166">" **元素** "工具会自动打开并显示 DOM 树中元素的 HTML。</span><span class="sxs-lookup"><span data-stu-id="75904-166">The **Elements** tool automatically opens and displays the HTML of the element in the DOM tree.</span></span> <span data-ttu-id="75904-167">该工具还会在"样式"窗格中的 **元素上显示** 应用的 CSS。</span><span class="sxs-lookup"><span data-stu-id="75904-167">The tool also displays the applied CSS on the element in the **Styles** pane.</span></span>  <span data-ttu-id="75904-168">选择呈现网页上的元素将关闭 **"检查"** 工具。</span><span class="sxs-lookup"><span data-stu-id="75904-168">Selecting an element on the rendered webpage turns off the **Inspect** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="有关所选元素的详细信息将显示在"元素"工具中" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    <span data-ttu-id="75904-170">有关所选元素的详细信息将显示在 **"** 元素"工具中</span><span class="sxs-lookup"><span data-stu-id="75904-170">Details about the selected element are displayed in the **Elements** tool</span></span>
:::image-end:::

<span data-ttu-id="75904-171">在呈现的页面中选择元素后，可以使用"样式"选项卡\*\*\*\* (附近的"辅助功能"选项卡) 查看\*\*\*\*"辅助功能树"并使用"源顺序查看器\*\*\*\*\*\*"。\*\*</span><span class="sxs-lookup"><span data-stu-id="75904-171">After selecting an element in the rendered page, you could then use the **Accessibility** tab (near the **Styles** tab) to view the **Accessibility Tree** and use the **Source Order Viewer**.</span></span>


## <a name="see-also"></a><span data-ttu-id="75904-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75904-172">See also</span></span>

*  [<span data-ttu-id="75904-173">检查节点</span><span class="sxs-lookup"><span data-stu-id="75904-173">Inspect a node</span></span>](../dom/index.md#inspect-a-node)
*  [<span data-ttu-id="75904-174">使用 Inspect 工具检查默认状态下的文本颜色对比度</span><span class="sxs-lookup"><span data-stu-id="75904-174">Check text-color contrast in the default state using the Inspect tool</span></span>](test-inspect-text-contrast.md)
*  [<span data-ttu-id="75904-175">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="75904-175">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="75904-176">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="75904-176">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "对比率|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web 内容辅助功能指南|W3C"
