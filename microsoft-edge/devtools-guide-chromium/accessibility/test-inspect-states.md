---
description: 在"样式"窗格中使用"切换元素状态"检查元素的所有状态（如悬停状态期间的文本对比度）的辅助功能。
title: 验证元素的所有状态是否可访问
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 129a89f94925de24a4e649bd91f513de031d6b4a
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597281"
---
# <a name="verify-accessibility-of-all-states-of-elements"></a><span data-ttu-id="58837-104">验证所有元素状态可访问性</span><span class="sxs-lookup"><span data-stu-id="58837-104">Verify accessibility of all states of elements</span></span>

<!-- 5. STYLES: TOGGLE STATE -->

<span data-ttu-id="58837-105">检查元素的所有状态（如状态期间的文本颜色对比度）的 `hover` 辅助功能。</span><span class="sxs-lookup"><span data-stu-id="58837-105">Check the accessibility of all states of elements, such as text color contrast during the `hover` state.</span></span>  <span data-ttu-id="58837-106">检查 **工具** 一次报告一个状态辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="58837-106">The **Inspect** tool reports accessibility issues for one state at a time.</span></span>  <span data-ttu-id="58837-107">若要检查元素的各种状态是否可访问，请在"样式"选项卡\*\*\*\* 中，选择 **"\：hov** (**Toggle 元素状态**) "，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="58837-107">To check accessibility of the various states of elements, in the **Styles** tab, select **\:hov** (**Toggle Element State**), as described in this article.</span></span> <span data-ttu-id="58837-108">我们首先显示为什么使用 **Inspect** 工具需要状态模拟，然后展示如何使用状态模拟。</span><span class="sxs-lookup"><span data-stu-id="58837-108">We first show why state simulation is necessary using the **Inspect** tool, and then we show how to use state simulation.</span></span>


## <a name="checking-text-color-contrast-in-the-default-state"></a><span data-ttu-id="58837-109">检查默认状态下的文本颜色对比度</span><span class="sxs-lookup"><span data-stu-id="58837-109">Checking text color contrast in the default state</span></span>

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

<span data-ttu-id="58837-110">除了问题工具中的自动颜色对比度测试之外，您还可以\*\*\*\* 使用**Inspect**工具检查各个页面元素是否具有足够的对比度。</span><span class="sxs-lookup"><span data-stu-id="58837-110">In addition to the automatic color-contrast tests in the **Issues** tool, you can also use the **Inspect** tool to check whether individual page elements have enough contrast.</span></span>  <span data-ttu-id="58837-111">如果对比度信息可用，" **检查** "覆盖层将显示对比率和复选框项。</span><span class="sxs-lookup"><span data-stu-id="58837-111">If contrast information is available, the **Inspect** overlay shows the contrast ratio and a checkbox item.</span></span>  <span data-ttu-id="58837-112">绿色选中标记图标表示对比度足够，黄色警报图标表示对比度不足。</span><span class="sxs-lookup"><span data-stu-id="58837-112">A green check mark icon indicates there's enough contrast, and a yellow alert icon indicates that there's not enough contrast.</span></span>

<span data-ttu-id="58837-113">例如，边栏导航菜单中的链接具有足够的对比度。</span><span class="sxs-lookup"><span data-stu-id="58837-113">For example, the links in the sidebar navigation menu have enough contrast.</span></span>  <span data-ttu-id="58837-114">但"自愿 **"** 状态部分中的绿色\*\*\*\*"动物"列表项没有足够的对比度，因此"检查"覆盖层中的警告**会进行**标记。</span><span class="sxs-lookup"><span data-stu-id="58837-114">But the green **Dogs** list item in the **Donation status** section doesn't have enough contrast, and so is flagged by a warning in the **Inspect** overlay.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="边栏导航菜单中的链接具有足够的对比度，如检查覆盖中所示" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            <span data-ttu-id="58837-116">边栏导航菜单中的链接具有足够的对比度，如检查**覆盖中所示**</span><span class="sxs-lookup"><span data-stu-id="58837-116">The links in the sidebar navigation menu have enough contrast, as shown in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text=""检查"覆盖层中的警告标记了对比度不足的元素" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            <span data-ttu-id="58837-118">"检查"覆盖层中的警告标记了对比度 **不足** 的元素</span><span class="sxs-lookup"><span data-stu-id="58837-118">An element that doesn't have enough contrast is flagged by a warning in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
:::row-end:::
        

## <a name="hovering-when-the-inspect-tool-is-active-doesnt-show-the-text-color-contrast-for-the-hover-state"></a><span data-ttu-id="58837-119">当 Inspect 工具处于活动状态时悬停不会显示悬停状态的文本颜色对比度</span><span class="sxs-lookup"><span data-stu-id="58837-119">Hovering when the Inspect tool is active doesn't show the text-color contrast for the hover state</span></span>

<span data-ttu-id="58837-120">**Inspect**工具的信息覆盖层仅表示单个状态。</span><span class="sxs-lookup"><span data-stu-id="58837-120">The **Inspect** tool's information overlay only represents a single state.</span></span>  <span data-ttu-id="58837-121">页面上的元素可以有不同的状态，所有这些状态都需要进行测试。</span><span class="sxs-lookup"><span data-stu-id="58837-121">Elements on the page can have different states, all of which need to be tested.</span></span>  <span data-ttu-id="58837-122">例如，当你将鼠标指针悬停在辅助功能测试演示页面的菜单上时，你得到一个更改颜色的动画。</span><span class="sxs-lookup"><span data-stu-id="58837-122">For example, when you hover the mouse pointer over the menu of the accessibility-testing demo page, you get an animation that changes the colors.</span></span> <span data-ttu-id="58837-123">执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="58837-123">Perform the following steps.</span></span>

1.  <span data-ttu-id="58837-124">打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。</span><span class="sxs-lookup"><span data-stu-id="58837-124">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.</span></span>

1.  <span data-ttu-id="58837-125">将鼠标悬停在边栏导航菜单中的蓝色菜单项上。</span><span class="sxs-lookup"><span data-stu-id="58837-125">Hover over the blue menu items in the sidebar navigation menu.</span></span>  <span data-ttu-id="58837-126">请注意，每个项目都有一个动画。</span><span class="sxs-lookup"><span data-stu-id="58837-126">Notice that each item has an animation.</span></span>

    :::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="鼠标指针悬停在不同的菜单项上时显示不同的颜色" lightbox="../media/a11y-testing-hover.msft.png":::
        <span data-ttu-id="58837-128">鼠标指针悬停在不同的菜单项上时显示不同的颜色</span><span class="sxs-lookup"><span data-stu-id="58837-128">The menu item showing different colors when the mouse pointer is over it</span></span>
    :::image-end:::
    
<span data-ttu-id="58837-129">现在，使用 Inspect 工具。</span><span class="sxs-lookup"><span data-stu-id="58837-129">Now, use the Inspect tool.</span></span> <span data-ttu-id="58837-130">使用 Inspect 工具时，将鼠标悬停在菜单项上时，不会运行菜单项上的动画。</span><span class="sxs-lookup"><span data-stu-id="58837-130">When the Inspect tool is used, animations on the menu items won't run when you hover over them.</span></span>  <span data-ttu-id="58837-131">使用 Inspect 工具时，你无法达到菜单项上的状态来测试对比率，因为你的样式中的状态 `hover` `hover` 不会触发。</span><span class="sxs-lookup"><span data-stu-id="58837-131">When using the Inspect tool, you can't reach the `hover` state on menu items to test the contrast ratio, because the `hover` state in your styles isn't triggered.</span></span>  
    
<span data-ttu-id="58837-132">若要确认动画不运行，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="58837-132">To confirm that your animations don't run, perform the following steps.</span></span>
    
1.  <span data-ttu-id="58837-133">选择 DevTools 左上角的"检查 **\ (** 检查"按钮 \) 按钮，以便图标以蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。</span><span class="sxs-lookup"><span data-stu-id="58837-133">Select the **Inspect** \(![the Inspect button](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="58837-134">将鼠标悬停在边栏导航菜单上的蓝色链接上。</span><span class="sxs-lookup"><span data-stu-id="58837-134">Hover over the blue links on the sidebar navigation menu.</span></span>  <span data-ttu-id="58837-135">菜单项的动画不会运行。</span><span class="sxs-lookup"><span data-stu-id="58837-135">The animations for the menu items don't run.</span></span> <span data-ttu-id="58837-136">相反，菜单项使用弹性框覆盖的颜色和突出显示来显示。</span><span class="sxs-lookup"><span data-stu-id="58837-136">Instead, the menu items are displayed using colors and highlights for the flexbox overlay.</span></span>

<span data-ttu-id="58837-137">如此检查是否有足够的文本对比度是不够的，因为页面上的元素可能具有不同的状态。</span><span class="sxs-lookup"><span data-stu-id="58837-137">Checking for sufficient text contrast this way isn't enough, because the elements on the page could have different states.</span></span>


## <a name="use-state-simulation-to-simulate-the-hover-state-of-an-animated-menu-item"></a><span data-ttu-id="58837-138">使用状态模拟模拟动画菜单项的悬停状态</span><span class="sxs-lookup"><span data-stu-id="58837-138">Use state simulation to simulate the hover state of an animated menu item</span></span> 

<!-- Elements tool: Styles pane: Toggle Element State -->

<span data-ttu-id="58837-139">当 **Inspect** 工具处于活动状态时，你需要模拟菜单项的状态，而不是将鼠标悬停在动画元素上。</span><span class="sxs-lookup"><span data-stu-id="58837-139">When the **Inspect** tool is active, instead of hovering over an animated element, you need to simulate the state of the menu item.</span></span>  <span data-ttu-id="58837-140">若要模拟菜单项的状态，请使用"样式" **窗格中的状态模拟** 。</span><span class="sxs-lookup"><span data-stu-id="58837-140">To simulate the state of a menu item, use the state simulation in the **Styles** pane.</span></span>  <span data-ttu-id="58837-141">" **样式"** 窗格有一个 **\：hov** (**Toggle Element State**) 按钮，该按钮显示一组标记为 **"Force 元素状态"的复选框**。</span><span class="sxs-lookup"><span data-stu-id="58837-141">The **Styles** pane has a **\:hov** (**Toggle Element State**) button, which displays a group of checkboxes labeled **Force element state**.</span></span>

<span data-ttu-id="58837-142">若要在使用 Inspect 工具时打开悬停状态：</span><span class="sxs-lookup"><span data-stu-id="58837-142">To turn on the hover state while using the Inspect tool:</span></span>

1.  <span data-ttu-id="58837-143">如果尚未打开，请打开新选项卡 [中的][DevToolsA11yErrorsDemopage] 辅助功能测试演示网页。 然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="58837-143">If it's not open already, open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="58837-144">选择 DevTools 左上角的"检查 **\ (** 检查工具按钮 \) "按钮，使图标以蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。</span><span class="sxs-lookup"><span data-stu-id="58837-144">Select the **Inspect** \(![Inspect tool button](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="58837-145">在呈现的网页中，选择边栏导航菜单中的蓝色 **"猫** "链接。</span><span class="sxs-lookup"><span data-stu-id="58837-145">In the rendered webpage, select the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="58837-146">将 **打开"** 元素"工具，并选中 `<a href="#cats">Cats</a>` 元素。</span><span class="sxs-lookup"><span data-stu-id="58837-146">The **Elements** tool opens, with the element `<a href="#cats">Cats</a>` selected.</span></span>

    :::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="检查元素工具中具有悬停状态的元素" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
        <span data-ttu-id="58837-148">检查元素工具中具有悬停状态的元素</span><span class="sxs-lookup"><span data-stu-id="58837-148">Inspecting the element that has a hover state in the Elements tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="58837-149">选择"**样式"** 选项卡。 所选 `a` 元素在应用于它的 CSS 中具有一个状态，但在"样式"窗格中不可见 `hover` 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="58837-149">Select the **Styles** tab.  The selected `a` element has a `hover` state in the CSS that is applied to it, but that's not visible in the **Styles** pane.</span></span> 

1.  <span data-ttu-id="58837-150">在 **样式** 窗格中的样式规则右侧， `#sidebar nav li a` 选择 `styles.css` 链接。</span><span class="sxs-lookup"><span data-stu-id="58837-150">In the **Styles** pane, to the right of the style rule `#sidebar nav li a`, select the `styles.css` link.</span></span>  <span data-ttu-id="58837-151">将 **打开"** 源"工具。</span><span class="sxs-lookup"><span data-stu-id="58837-151">The **Sources** tool opens.</span></span>  <span data-ttu-id="58837-152">然后查找 CSS 伪类规则 `#sidebar nav li a:hover` 。</span><span class="sxs-lookup"><span data-stu-id="58837-152">Then find the CSS pseudo-class rule `#sidebar nav li a:hover`.</span></span>  <span data-ttu-id="58837-153">当 Inspect 工具处于活动状态时， **此规则** 不运行。</span><span class="sxs-lookup"><span data-stu-id="58837-153">This rule doesn't run when the **Inspect** tool is active.</span></span>  <span data-ttu-id="58837-154">我们将在下一步中模拟运行此状态规则。</span><span class="sxs-lookup"><span data-stu-id="58837-154">We'll simulate running this state rule in the next steps.</span></span>

1.  <span data-ttu-id="58837-155">选择" **元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="58837-155">Select the **Elements** tool.</span></span>  <span data-ttu-id="58837-156">然后在"**样式"** 窗格中，选择"：hov (\*\*Toggle 元素状态) \*\*按钮。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="58837-156">Then in the **Styles** pane, select the **:hov** (**Toggle Element State**) button.</span></span>  <span data-ttu-id="58837-157">显示 **复选框的 Force** 元素状态组。</span><span class="sxs-lookup"><span data-stu-id="58837-157">The **Force element state** group of checkboxes is displayed.</span></span>

    :::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="显示所有选项的状态模拟工具" lightbox="../media/a11y-testing-state-simulation.msft.png":::
        <span data-ttu-id="58837-159">显示所有选项的状态模拟工具</span><span class="sxs-lookup"><span data-stu-id="58837-159">The state simulation tool showing all the options</span></span>
    :::image-end:::

1.  <span data-ttu-id="58837-160">选中 **"：hover"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="58837-160">Select the **:hover** checkbox.</span></span>  <span data-ttu-id="58837-161">在 DOM 中，元素左侧将出现一个黄色点，指示元素 `<a href="#cats">Cats</a>` 具有模拟状态。</span><span class="sxs-lookup"><span data-stu-id="58837-161">In the DOM, to the left of the element `<a href="#cats">Cats</a>`, a yellow dot appears, indicating that the element has a simulated state.</span></span>  <span data-ttu-id="58837-162">" **猫** "菜单项现在显示在网页中，就像指针悬停在它上方一样。</span><span class="sxs-lookup"><span data-stu-id="58837-162">The **Cats** menu item now appears in the webpage as if the pointer were hovering over it.</span></span>  <span data-ttu-id="58837-163">菜单项上的动画可能会运行。</span><span class="sxs-lookup"><span data-stu-id="58837-163">The animation on the menu item might run.</span></span>

    :::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="模拟悬停状态的开发工具" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
        <span data-ttu-id="58837-165">模拟悬停状态的开发工具</span><span class="sxs-lookup"><span data-stu-id="58837-165">DevTools simulating a hover state</span></span>
    :::image-end:::

    <span data-ttu-id="58837-166">应用模拟状态后，可以再次使用 **Inspect** 工具在用户将鼠标悬停在元素上时检查元素的对比度，如下所示。</span><span class="sxs-lookup"><span data-stu-id="58837-166">After the simulated state is applied, you can use the **Inspect** tool again to check the contrast of the element when the user hovers over it, as follows.</span></span>

1.  <span data-ttu-id="58837-167">选择 DevTools 左上角的"检查 **\ (** 检查器图标 \) "按钮，以便该图标在蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。</span><span class="sxs-lookup"><span data-stu-id="58837-167">Select the **Inspect** \(![Inspector icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="58837-168">将鼠标悬停在边栏导航菜单中的蓝色 **"猫** "链接上。</span><span class="sxs-lookup"><span data-stu-id="58837-168">Hover over the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="58837-169">由于模拟悬停动画，该链接现在为浅蓝色。</span><span class="sxs-lookup"><span data-stu-id="58837-169">The link is now light blue, because of the simulated hover animation.</span></span>  <span data-ttu-id="58837-170">将显示**Inspect**工具的信息覆盖层，在"对比度"行中显示橙色感叹\*\*\*\* 号，指示对比度不够高。</span><span class="sxs-lookup"><span data-stu-id="58837-170">The **Inspect** tool's information overlay appears, showing an orange exclamation point in the **Contrast** row, indicating that the contrast isn't high enough.</span></span>

    :::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="在模拟悬停状态中测试元素的对比度" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
        <span data-ttu-id="58837-172">在模拟悬停状态中测试元素的对比度</span><span class="sxs-lookup"><span data-stu-id="58837-172">Testing the contrast of an element in a simulated hover state</span></span>
    :::image-end:::

<span data-ttu-id="58837-173">状态模拟也是检查你是否认为不同的用户需求（如键盘用户的需求）的一个好方法。</span><span class="sxs-lookup"><span data-stu-id="58837-173">State simulation is also a good way to check whether you considered different user needs, such as the needs of keyboard users.</span></span>  <span data-ttu-id="58837-174">通过使用 **Force 元素状态** 复选框，你可以模拟状态，发现 UI 在具有焦点时 `:focus` 保持不变。</span><span class="sxs-lookup"><span data-stu-id="58837-174">By using the **Force element state** checkboxes, you can simulate the `:focus` state to discover that the UI remains unchanged when it has focus.</span></span> <span data-ttu-id="58837-175">当元素具有焦点时缺少指示器是一个问题。</span><span class="sxs-lookup"><span data-stu-id="58837-175">This lack of an indicator when an element has focus is a problem.</span></span>


## <a name="see-also"></a><span data-ttu-id="58837-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58837-176">See also</span></span>

*  [<span data-ttu-id="58837-177">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="58837-177">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="58837-178">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="58837-178">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
