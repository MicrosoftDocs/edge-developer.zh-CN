---
description: 使用"问题"工具的"辅助功能"部分自动测试网页的辅助功能问题。
title: 自动测试网页中的辅助功能问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 1cba9db1744235dfbfd2a007e33d1101452aab31
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624736"
---
# <a name="automatically-test-a-webpage-for-accessibility-issues"></a><span data-ttu-id="bdee5-104">自动测试网页中的辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="bdee5-104">Automatically test a webpage for accessibility issues</span></span>

<span data-ttu-id="bdee5-105">问题**工具\*\*\*\*包括辅助功能部分**，可自动报告图像上缺少可选文本、表单字段上缺少标签以及文本颜色对比度不足等问题。</span><span class="sxs-lookup"><span data-stu-id="bdee5-105">The **Issues** tool includes an **Accessibility** section that automatically reports issues such as missing alternative text on images, missing labels on form fields, and insufficient contrast of text colors.</span></span>  <span data-ttu-id="bdee5-106">问题**工具**位于 DevTools 底部的"箱"内。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bdee5-106">The **Issues** tool is within the **Drawer** at the bottom of DevTools.</span></span>  <span data-ttu-id="bdee5-107">本文使用辅助功能测试演示网页逐步介绍了如何使用问题工具的**辅助功能\*\*\*\*部分。**</span><span class="sxs-lookup"><span data-stu-id="bdee5-107">This article uses the accessibility-testing demo webpage to step through using the **Accessibility** section of the **Issues** tool.</span></span>

<span data-ttu-id="bdee5-108">有几种打开问题 **工具的方法** ，例如：</span><span class="sxs-lookup"><span data-stu-id="bdee5-108">There are several ways to open the **Issues** tool, such as:</span></span>
*  <span data-ttu-id="bdee5-109">选择 DevTools \*\* (右上角\*\* 的"问题") "问题" ![ 计数器 ](../media/issues-counter-icon.msft.png) \) 。</span><span class="sxs-lookup"><span data-stu-id="bdee5-109">Select the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) in the upper right of DevTools.</span></span>
*  <span data-ttu-id="bdee5-110">在" **元素** "工具的 DOM 树中 **，Shift+单击** 元素上的波浪下划线。</span><span class="sxs-lookup"><span data-stu-id="bdee5-110">In the **Elements** tool, in the DOM tree, **Shift+click** a wavy underline on an element.</span></span>
*  <span data-ttu-id="bdee5-111">在"**命令"菜单中**，键入 `issues` ，然后选择"**显示问题"。**</span><span class="sxs-lookup"><span data-stu-id="bdee5-111">In the **Command Menu**, type `issues`, and then select **Show Issues**.</span></span>


## <a name="view-the-accessibility-section-of-the-issues-tool"></a><span data-ttu-id="bdee5-112">查看问题工具的辅助功能部分</span><span class="sxs-lookup"><span data-stu-id="bdee5-112">View the Accessibility section of the Issues tool</span></span>

1.  <span data-ttu-id="bdee5-113">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="bdee5-113">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>  <span data-ttu-id="bdee5-114">在右上角，"问题"计数器 **\ (** Issues 计数器 \) 显示为语音气泡图标以及自动检测到 ![ ](../media/issues-counter-icon.msft.png) 的问题数。</span><span class="sxs-lookup"><span data-stu-id="bdee5-114">In the upper right, the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) appears, as a speech-bubble icon along with the number of automatically detected issues.</span></span>  <span data-ttu-id="bdee5-115">浏览器中可能会显示不同的数字，并且该数字可能会随着使用 DevTools 而更新。</span><span class="sxs-lookup"><span data-stu-id="bdee5-115">A different number might appear in your browser, and the number might update as you use DevTools.</span></span>

    :::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text="DevTools 中的"问题"计数器，指示当前文档中的问题数" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
        <span data-ttu-id="bdee5-117">DevTools 中的"问题"计数器，指示当前文档中的问题数\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bdee5-117">The **Issues counter** in DevTools, indicating how many problems there are in the current document</span></span>
    :::image-end:::

1.  <span data-ttu-id="bdee5-118">选择" **问题"计数器**。</span><span class="sxs-lookup"><span data-stu-id="bdee5-118">Select the **Issues counter**.</span></span>  <span data-ttu-id="bdee5-119">"**问题**"工具将在 DevTools 底部的"箱"中打开。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bdee5-119">The **Issues** tool opens, in the **Drawer** at the bottom of DevTools.</span></span>

    :::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="问题工具中显示的辅助功能警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
        <span data-ttu-id="bdee5-121">问题工具中显示的辅助功能警告</span><span class="sxs-lookup"><span data-stu-id="bdee5-121">Accessibility warnings displayed in the Issues tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="bdee5-122">在" **问题"** 选项卡上，展开 **"辅助功能"** 部分。</span><span class="sxs-lookup"><span data-stu-id="bdee5-122">On the **Issues** tab, expand the **Accessibility** section.</span></span>


## <a name="verify-that-input-fields-have-labels"></a><span data-ttu-id="bdee5-123">验证输入字段是否包含标签</span><span class="sxs-lookup"><span data-stu-id="bdee5-123">Verify that input fields have labels</span></span>

<span data-ttu-id="bdee5-124">若要检查输入字段是否连接了标签，请使用问题工具，\*\*\*\* 该工具会自动检查整个网页，并报告辅助功能**部分中的此问题**。</span><span class="sxs-lookup"><span data-stu-id="bdee5-124">To check whether input fields have labels connected to them, use the **Issues** tool, which automatically checks the entire webpage and reports this issue in the **Accessibility** section.</span></span>

1.  <span data-ttu-id="bdee5-125">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="bdee5-125">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="bdee5-126">在右上角，选择问题 **计数器** \ (![ 问题计数器 ](../media/issues-counter-icon.msft.png) \) 。</span><span class="sxs-lookup"><span data-stu-id="bdee5-126">In the upper right, select the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\).</span></span>  <span data-ttu-id="bdee5-127">"**问题**"工具将在 DevTools 底部的"箱"中打开。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bdee5-127">The **Issues** tool opens, in the **Drawer** at the bottom of DevTools.</span></span>

1.  <span data-ttu-id="bdee5-128">在" **问题"** 选项卡上，展开 **"辅助功能"** 部分。</span><span class="sxs-lookup"><span data-stu-id="bdee5-128">On the **Issues** tab, expand the **Accessibility** section.</span></span>

1.  <span data-ttu-id="bdee5-129">展开 **警告** `Form elements must have labels: Element has no title attribute Element has no placeholder attribute` 。</span><span class="sxs-lookup"><span data-stu-id="bdee5-129">Expand the **Warning** `Form elements must have labels: Element has no title attribute Element has no placeholder attribute`.</span></span>

1. <span data-ttu-id="bdee5-130">选择" **在元素中打开"** 链接。</span><span class="sxs-lookup"><span data-stu-id="bdee5-130">Select the **Open in Elements** link.</span></span>

    :::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="在"问题"工具中选择链接后显示有问题的 HTML 的元素工具" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
        <span data-ttu-id="bdee5-132">在"问题"工具中选择链接后显示有问题的 HTML **的元素** 工具</span><span class="sxs-lookup"><span data-stu-id="bdee5-132">Elements tool showing the problematic HTML after selecting the link in the **Issues** tool</span></span> :::image-end:::

    <span data-ttu-id="bdee5-133">将 **打开"** 元素"工具，同时在 DOM 树中突出显示元素。</span><span class="sxs-lookup"><span data-stu-id="bdee5-133">The **Elements** tool opens, with the element highlighted in the DOM tree.</span></span>  <span data-ttu-id="bdee5-134">" **样式** "窗格显示元素应用的 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="bdee5-134">The **Styles** pane displays the applied CSS rules for the element.</span></span>  <span data-ttu-id="bdee5-135">现在将显示以下代码。</span><span class="sxs-lookup"><span data-stu-id="bdee5-135">The following code is now displayed.</span></span>

    ```html
    <label>Search</label>
    <input type="search">
    <input type="submit" value="go">
    ```

    <span data-ttu-id="bdee5-136">在以上代码中，元素使用不正确，因为 元素和特定元素 `label` `label` 之间没有 `input` 连接。</span><span class="sxs-lookup"><span data-stu-id="bdee5-136">In the above code, the `label` element is used incorrectly, because there is no connection between the `label` element and a particular `input` element.</span></span>  <span data-ttu-id="bdee5-137">若要将 `label` 元素连接到特定 `input` 元素，请使用以下任一选项。</span><span class="sxs-lookup"><span data-stu-id="bdee5-137">To connect the `label` element to a specific `input` element, use any of the following options.</span></span>
    *   <span data-ttu-id="bdee5-138">将 `input` 元素嵌套在 `label` 元素中。</span><span class="sxs-lookup"><span data-stu-id="bdee5-138">Nest the `input` element within the `label` element.</span></span>
    *   <span data-ttu-id="bdee5-139">在 `label` 元素中，添加 `for` 与 元素的属性 `id` 匹配的 `input` 属性。</span><span class="sxs-lookup"><span data-stu-id="bdee5-139">In the `label` element, add a `for` attribute that matches an `id` attribute of the `input` element.</span></span>

    <span data-ttu-id="bdee5-140">还有另一种方法可以测试元素之间缺少连接。</span><span class="sxs-lookup"><span data-stu-id="bdee5-140">There's also another way to test for lack of connections between elements.</span></span> <span data-ttu-id="bdee5-141">在" **元素"** 工具中， `<label>Search</label>` 选择 DOM 树中的元素。</span><span class="sxs-lookup"><span data-stu-id="bdee5-141">In the **Elements** tool, select the `<label>Search</label>` element in the DOM tree.</span></span>  <span data-ttu-id="bdee5-142">在网页上，请注意，焦点只出现在 **搜索** 标签上，而不是输入文本框上。</span><span class="sxs-lookup"><span data-stu-id="bdee5-142">On the webpage, notice that focus only appears on the **Search** label, and not the input textbox.</span></span>  <span data-ttu-id="bdee5-143">正确的实现将焦点放在输入 `search` 文本框和 **搜索标签** 上。</span><span class="sxs-lookup"><span data-stu-id="bdee5-143">The correct implementation would put focus on the `search` input textbox and the **Search** label.</span></span>

1.  <span data-ttu-id="bdee5-144">作为正确连接的示例，选择"捐赠 **"表单** 上的"其他"标签。</span><span class="sxs-lookup"><span data-stu-id="bdee5-144">As an example of a correct connection, select the **Other** label on the donation form.</span></span>  <span data-ttu-id="bdee5-145">焦点指示器框正确显示在"其他"标签旁边的输入文本框上，因为\*\*\*\* 存在匹配 `for` 值 `id` 和属性值。</span><span class="sxs-lookup"><span data-stu-id="bdee5-145">A focus-indicator box correctly appears on the input textbox next to the **Other** label, because there are matching `for` and `id` attribute values.</span></span>

1.  <span data-ttu-id="bdee5-146">在" **问题"工具**中，选择"进一步 **阅读** "以了解有关问题有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdee5-146">In the **Issues tool**, select **Further reading** to learn more about the issue.</span></span>  <span data-ttu-id="bdee5-147">若要打开新选项卡中的链接，请按**Ctrl**单击 Windows/Linux 上的链接，或单击 + \*\*\*\*\*\*\*\* + \*\*\*\* macOS 上的链接的命令。</span><span class="sxs-lookup"><span data-stu-id="bdee5-147">To open the link in a new tab, **Ctrl**+**click** the link on Windows/Linux, or **Command**+**click** the link on macOS.</span></span>

    :::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="指向有关问题的更深入信息的"问题"选项卡上的链接" lightbox="../media/a11y-testing-more-information-links.msft.png":::
        <span data-ttu-id="bdee5-149">指向 **有关问题的** 更深入信息的"问题"选项卡上的链接</span><span class="sxs-lookup"><span data-stu-id="bdee5-149">Link on the **Issues** tab pointing to more in-depth information about the issue</span></span>
    :::image-end:::


## <a name="verify-that-images-have-alt-text"></a><span data-ttu-id="bdee5-150">验证图像是否包含替换文字</span><span class="sxs-lookup"><span data-stu-id="bdee5-150">Verify that images have alt text</span></span>

<span data-ttu-id="bdee5-151">基本辅助功能测试要求确保为图像 (_可选_ 文字) 可选文字。</span><span class="sxs-lookup"><span data-stu-id="bdee5-151">Basic accessibility testing requires making sure alternative text (also called _alt text_) is provided for images.</span></span>

<span data-ttu-id="bdee5-152">若要自动检查是否为图像提供了替换文字，请使用 **问题工具，** 该工具具有 **辅助功能** 部分。</span><span class="sxs-lookup"><span data-stu-id="bdee5-152">To automatically check whether alt text is provided for images, use the **Issues** tool, which has an **Accessibility** section.</span></span>  <span data-ttu-id="bdee5-153">问题**工具**位于 DevTools\*\*\*\* 底部的"箱"中。</span><span class="sxs-lookup"><span data-stu-id="bdee5-153">The **Issues** tool is located in the **Drawer** at the bottom of DevTools.</span></span>

1.  <span data-ttu-id="bdee5-154">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="bdee5-154">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="bdee5-155">若要打开 **"问题"** 工具，请选择\*\*\*\* DevTools 右上角的"问题"计数器。</span><span class="sxs-lookup"><span data-stu-id="bdee5-155">To open the **Issues** tool, select the **Issues** counter in the upper right of DevTools.</span></span>

1.  <span data-ttu-id="bdee5-156">在" **问题"** 选项卡上，展开警告 `Images must have alternate text: Element has no title attribute` 。</span><span class="sxs-lookup"><span data-stu-id="bdee5-156">On the **Issues** tab, expand the warning `Images must have alternate text: Element has no title attribute`.</span></span>  <span data-ttu-id="bdee5-157">有四种图像实例缺少替换文字。</span><span class="sxs-lookup"><span data-stu-id="bdee5-157">There are four instances of images that lack alt text.</span></span>

    :::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="问题工具报告缺少可选文本的图像" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
        <span data-ttu-id="bdee5-159">问题工具报告缺少可选文本的图像</span><span class="sxs-lookup"><span data-stu-id="bdee5-159">The Issues tool reporting images that are missing alternative text</span></span>
    :::image-end:::

<span data-ttu-id="bdee5-160">有关详细信息，导航到 [图像必须具有备用文本](https://dequeuniversity.com/rules/axe/4.1/image-alt)。</span><span class="sxs-lookup"><span data-stu-id="bdee5-160">For more information, navigate to [Images must have alternate text](https://dequeuniversity.com/rules/axe/4.1/image-alt).</span></span>


## <a name="verify-that-text-colors-have-enough-contrast"></a><span data-ttu-id="bdee5-161">验证文本颜色是否具有足够的对比度</span><span class="sxs-lookup"><span data-stu-id="bdee5-161">Verify that text colors have enough contrast</span></span>

<span data-ttu-id="bdee5-162">若要自动检查文本颜色是否具有足够的对比度，请使用问题 **工具，** 该工具 **具有辅助功能部分** 。</span><span class="sxs-lookup"><span data-stu-id="bdee5-162">To automatically check whether text colors have enough contrast, use the **Issues** tool, which has an **Accessibility** section.</span></span>  <span data-ttu-id="bdee5-163">问题**工具**位于 DevTools\*\*\*\* 底部的"箱"中。</span><span class="sxs-lookup"><span data-stu-id="bdee5-163">The **Issues** tool is located in the **Drawer** at the bottom of DevTools.</span></span>

1.  <span data-ttu-id="bdee5-164">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="bdee5-164">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="bdee5-165">若要打开 **"问题"** 工具，请选择\*\*\*\* DevTools 右上角的"问题"计数器。</span><span class="sxs-lookup"><span data-stu-id="bdee5-165">To open the **Issues** tool, select the **Issues** counter in the upper right of DevTools.</span></span>  <span data-ttu-id="bdee5-166">您可能会收到警告，指出演示网页上的两个元素的对比度不足。</span><span class="sxs-lookup"><span data-stu-id="bdee5-166">You may receive warnings that two elements on the demo webpage don't have enough contrast.</span></span>

    :::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="问题工具中报告的对比度问题" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
        <span data-ttu-id="bdee5-168">问题工具中报告的对比度问题</span><span class="sxs-lookup"><span data-stu-id="bdee5-168">Contrast problems reported in the Issues tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="bdee5-169">根据您的设置，"问题"\*\*\*\* 选项卡可能会显示一条警告，如用户可能由于颜色对比度不足而难以**阅读文本内容**。</span><span class="sxs-lookup"><span data-stu-id="bdee5-169">Depending on your settings, the **Issues** tab might have a warning like **Users may have difficulties reading text content due to insufficient color contrast**.</span></span>   <span data-ttu-id="bdee5-170">可以展开该警告，然后展开受影响的 **资源**。</span><span class="sxs-lookup"><span data-stu-id="bdee5-170">You can expand that warning, and then expand **Affected resources**.</span></span>  <span data-ttu-id="bdee5-171">将显示元素列表，其中具有对比度不足的元素列表。</span><span class="sxs-lookup"><span data-stu-id="bdee5-171">A list of elements appears with a list of elements that don't have enough contrast.</span></span>


1.  <span data-ttu-id="bdee5-172">选择 `li.high` 元素。</span><span class="sxs-lookup"><span data-stu-id="bdee5-172">Select the `li.high` element.</span></span>  <span data-ttu-id="bdee5-173">在呈现的网页中，突出显示**了"小**动物\*\*\*\*"部分中的"动物"链接，显示一个小的信息覆盖层。</span><span class="sxs-lookup"><span data-stu-id="bdee5-173">In the rendered webpage, the **Dogs** link in the **Donate** section is highlighted, displaying a small information overlay.</span></span>  <span data-ttu-id="bdee5-174">这是当您将鼠标悬停在"元素"工具中 DOM 树中的某个元素上时出现的 **相同** 覆盖。</span><span class="sxs-lookup"><span data-stu-id="bdee5-174">This is the same overlay that appears when you hover over an element in the DOM tree in the **Elements** tool.</span></span>

    :::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="在"受影响资源"部分选择链接后突出显示的网页中的元素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
        <span data-ttu-id="bdee5-176">在"受影响资源"部分选择链接后 **突出显示的网页中的** 元素</span><span class="sxs-lookup"><span data-stu-id="bdee5-176">Element in the webpage highlighted after selecting a link in the **Affected Resources** section</span></span>
    :::image-end:::


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a><span data-ttu-id="bdee5-177">DOM 树中的波浪下划线指示自动检测到的问题</span><span class="sxs-lookup"><span data-stu-id="bdee5-177">Wavy underlines in the DOM tree indicate automatically detected issues</span></span> 

<span data-ttu-id="bdee5-178">元素工具中的 DOM **树直接** 在 HTML 中用波浪下划线标记问题。</span><span class="sxs-lookup"><span data-stu-id="bdee5-178">The DOM tree in the **Elements** tool flags issues directly in the HTML with wavy underlines.</span></span>  <span data-ttu-id="bdee5-179">这些问题由问题**工具报告。**</span><span class="sxs-lookup"><span data-stu-id="bdee5-179">These issues are reported by the **Issues** tool.</span></span>  <span data-ttu-id="bdee5-180">当 **Shift+单击** 带波浪下划线的任何元素时，将显示 **"问题"** 工具。</span><span class="sxs-lookup"><span data-stu-id="bdee5-180">When you **Shift+click** any element with a wavy underline, the **Issues tool** is displayed.</span></span>

1.  <span data-ttu-id="bdee5-181">在" **元素** "工具的 DOM 树中 **，Shift+单击** 元素，其下 `<input type="search">` 有一条波浪线 `input` 。</span><span class="sxs-lookup"><span data-stu-id="bdee5-181">In the **Elements** tool, in the DOM tree, **Shift+click** the element `<input type="search">`, which has a wavy line under `input`.</span></span>  <span data-ttu-id="bdee5-182">将显示 **"** 问题"工具，并显示该元素的问题。</span><span class="sxs-lookup"><span data-stu-id="bdee5-182">The **Issues tool** is displayed, and shows the issue for that element.</span></span>

    :::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="DOM 视图中具有波浪下划线的元素有一个问题" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
        <span data-ttu-id="bdee5-184">DOM 视图中具有波浪下划线的元素有一个问题</span><span class="sxs-lookup"><span data-stu-id="bdee5-184">An element that has a wavy underline in the DOM view has an issue</span></span>
    :::image-end:::


## <a name="see-also"></a><span data-ttu-id="bdee5-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdee5-185">See also</span></span>

*  [<span data-ttu-id="bdee5-186">使用问题工具查找和修复问题</span><span class="sxs-lookup"><span data-stu-id="bdee5-186">Find and fix problems using the Issues tool</span></span>][DevToolsIssuesTool]
*  [<span data-ttu-id="bdee5-187">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="bdee5-187">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="bdee5-188">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="bdee5-188">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsIssuesTool]: ../issues/index.md "使用问题工具查找并修复|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
