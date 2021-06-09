---
description: 使用页面上的"检查"工具的信息覆盖来检查默认状态下的文本颜色对比度，该页面上有一个包含"对比度"信息的"辅助功能"部分。
title: 使用 Inspect 工具检查默认状态下的文本颜色对比度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: ade9fd6d685f6f7cea6311b1645a527ece352a38
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597251"
---
# <a name="check-text-color-contrast-in-the-default-state-using-the-inspect-tool"></a><span data-ttu-id="1cfdb-104">使用 Inspect 工具检查默认状态下的文本颜色对比度</span><span class="sxs-lookup"><span data-stu-id="1cfdb-104">Check text-color contrast in the default state using the Inspect tool</span></span>

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

<span data-ttu-id="1cfdb-105">使用 Inspect 工具检查默认状态下的文本**颜色对比度。**</span><span class="sxs-lookup"><span data-stu-id="1cfdb-105">Check text color contrast in the default state by using the **Inspect** tool.</span></span>  <span data-ttu-id="1cfdb-106">" **检查** "工具在网页上的信息覆盖具有一个 **"** 辅助功能"部分，其中包含 **"对比度"** 信息。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-106">The **Inspect** tool's information overlay on the webpage has an **Accessibility** section that includes **Contrast** information.</span></span>

<span data-ttu-id="1cfdb-107">若要使用 Inspect 工具的信息覆盖层检查默认状态下的文本颜色对比度，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-107">To check text-color contrast in the default state using the Inspect tool's information overlay, perform the following steps.</span></span>

<!-- Inspect tool -->
<span data-ttu-id="1cfdb-108">对于具有文本的元素 **，Inspect** 工具的信息覆盖层显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="1cfdb-108">For elements that have text, the **Inspect** tool's information overlay shows the following:</span></span>
*  <span data-ttu-id="1cfdb-109">文本与背景颜色的对比率。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-109">The contrast ratio of text versus background colors.</span></span>
*  <span data-ttu-id="1cfdb-110">具有足够对比度的元素的绿色选中标记图标。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-110">A green check mark icon for elements with enough contrast.</span></span>
*  <span data-ttu-id="1cfdb-111">没有足够对比度的元素的黄色警报图标。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-111">A yellow alert icon for elements that don't have enough contrast.</span></span>

<span data-ttu-id="1cfdb-112">在某些情况下，将浏览器设置为浅色主题或深色主题会影响对比度。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-112">In some cases, contrast is affected by setting the browser to light theme or dark theme.</span></span>

<span data-ttu-id="1cfdb-113">例如，在演示页面上，边栏导航菜单的蓝色链接具有足够的对比度，但"发送状态"部分中的绿色\*\*\*\*"动物"链接\*\*\*\* 没有足够的对比度。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-113">As an example, on the demo page, the blue links of the sidebar navigation menu have enough contrast, but the green **Dogs** link in the **Donation status** section does not have enough contrast.</span></span>  <span data-ttu-id="1cfdb-114">使用 Inspect 工具查看 **这些** 元素，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1cfdb-114">Review those elements using the **Inspect** tool, as follows:</span></span>

1.  <span data-ttu-id="1cfdb-115">打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。 然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-115">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="1cfdb-116">选择 DevTools 左上角的"检查 **\ (** 检查"按钮 \) 按钮，使图标以蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-116">Select the **Inspect** \(![Inspect button](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="1cfdb-117">在呈现的网页中，将鼠标悬停在边栏导航菜单的蓝色 **"猫** "链接上。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-117">In the rendered webpage, hover over the blue **Cats** link of the sidebar navigation menu.</span></span>  <span data-ttu-id="1cfdb-118">将显示 **Inspect** 工具的信息覆盖层。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-118">The **Inspect** tool's information overlay appears.</span></span>  <span data-ttu-id="1cfdb-119">在信息**覆盖的**"辅助功能"部分中，"对比度"行上会显示一个\*\*\*\* 绿色选中标记，指示此元素具有足够的文本颜色与背景色对比度。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-119">In the **Accessibility** section of the information overlay, a green checkmark appears on the **Contrast** row, indicating that this element has enough contrast of text color versus background color.</span></span>

    :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="菜单项具有足够的对比度，如 Inspect 工具中所示" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
        <span data-ttu-id="1cfdb-121">菜单项具有足够的对比度，如 Inspect 工具中所示</span><span class="sxs-lookup"><span data-stu-id="1cfdb-121">The menu items have enough contrast, as shown in the Inspect tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="1cfdb-122">在呈现的网页的"私人 **状态"** 部分，将鼠标悬停在 **"动物"** 链接上。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-122">In the rendered webpage, in the **Donation Status** section, hover over the **Dogs** link.</span></span>  <span data-ttu-id="1cfdb-123">**Inspect 工具**的信息覆盖层在 Contrast 行上显示橙色感叹号\*\*\*\*，指示此元素没有足够的文本与背景色对比度。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-123">The **Inspect** tool's information overlay shows an orange exclamation point on the **Contrast** row, indicating that this element doesn't have enough contrast of text versus background colors.</span></span>

    :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="对比度不足的元素，如 Inspect 工具中的警告所示" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
        <span data-ttu-id="1cfdb-125">对比度不足的元素，如 Inspect 工具中的警告所示</span><span class="sxs-lookup"><span data-stu-id="1cfdb-125">An element that doesn't have enough contrast, as shown by the warning in the Inspect tool</span></span>
    :::image-end:::


## <a name="different-options-to-inspect-text-color-contrast-in-devtools"></a><span data-ttu-id="1cfdb-126">在 DevTools 中检查文本颜色对比度的不同选项</span><span class="sxs-lookup"><span data-stu-id="1cfdb-126">Different options to inspect text-color contrast in DevTools</span></span>

<span data-ttu-id="1cfdb-127">使用以下 DevTools 功能检查文本颜色对比度。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-127">Use the following DevTools features to inspect text-color contrast.</span></span>

*  <span data-ttu-id="1cfdb-128">使用 **检查** 工具 (网页上的信息覆盖) 检查单个页面元素是否具有足够的文本颜色对比度。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-128">Use the **Inspect** tool (as an information overlay on the webpage) to check whether an individual page element has enough text-color contrast.</span></span>  <span data-ttu-id="1cfdb-129">Inspect \*\*\*\* 工具的信息覆盖包括一个 **"辅助功能"** 部分，其中包含 **"对比度**"信息行。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-129">The **Inspect** tool's information overlay includes an **Accessibility** section that has a **Contrast** information row.</span></span>  <span data-ttu-id="1cfdb-130">检查 **工具** 只显示当前状态的文本对比度信息。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-130">The **Inspect** tool only shows text-contrast information for the current state.</span></span>  <span data-ttu-id="1cfdb-131">此方法在当前文章中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-131">This approach is described in the current article.</span></span>

*  <span data-ttu-id="1cfdb-132">当 **文本** 和背景色的对比度不够时，问题工具将自动报告整个网页的任何颜色对比度问题。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-132">The **Issues** tool automatically reports any color-contrast issues for the entire webpage, when text and background color don't contrast enough.</span></span>  <span data-ttu-id="1cfdb-133">验证文本颜色是否具有足够的 [对比度中介绍了此方法](test-issues-tool.md#verify-that-text-colors-have-enough-contrast)。</span><span class="sxs-lookup"><span data-stu-id="1cfdb-133">This approach is described in [Verify that text colors have enough contrast](test-issues-tool.md#verify-that-text-colors-have-enough-contrast).</span></span>

*  <span data-ttu-id="1cfdb-134">通过使用"样式"窗格中的"切换元素状态"模拟非默认状态，如状态，如验证元素的所有 `hover` [状态辅助功能中所述](test-inspect-states.md)。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1cfdb-134">Emulate a non-default state, such as the `hover` state, by using **Toggle Element State** in the **Styles** pane, described in [Verify accessibility of all states of elements](test-inspect-states.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="1cfdb-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cfdb-135">See also</span></span>

*  [<span data-ttu-id="1cfdb-136">验证所有元素状态可访问性</span><span class="sxs-lookup"><span data-stu-id="1cfdb-136">Verify accessibility of all states of elements</span></span>][DevtoolsAccessibilityTestInspectStates]
*  [<span data-ttu-id="1cfdb-137">使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="1cfdb-137">Use the Inspect tool to detect accessibility issues by hovering over the webpage</span></span>](test-inspect-tool.md)
*  [<span data-ttu-id="1cfdb-138">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="1cfdb-138">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1cfdb-139">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="1cfdb-139">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityTestInspectStates]: test-inspect-states.md "验证元素的所有状态是否可访问|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
