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
# <a name="verify-accessibility-of-all-states-of-elements"></a>验证所有元素状态可访问性

<!-- 5. STYLES: TOGGLE STATE -->

检查元素的所有状态（如状态期间的文本颜色对比度）的 `hover` 辅助功能。  检查 **工具** 一次报告一个状态辅助功能问题。  若要检查元素的各种状态是否可访问，请在"样式"选项卡**** 中，选择 **"\：hov** (**Toggle 元素状态**) "，如本文所述。 我们首先显示为什么使用 **Inspect** 工具需要状态模拟，然后展示如何使用状态模拟。


## <a name="checking-text-color-contrast-in-the-default-state"></a>检查默认状态下的文本颜色对比度

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

除了问题工具中的自动颜色对比度测试之外，您还可以**** 使用**Inspect**工具检查各个页面元素是否具有足够的对比度。  如果对比度信息可用，" **检查** "覆盖层将显示对比率和复选框项。  绿色选中标记图标表示对比度足够，黄色警报图标表示对比度不足。

例如，边栏导航菜单中的链接具有足够的对比度。  但"自愿 **"** 状态部分中的绿色****"动物"列表项没有足够的对比度，因此"检查"覆盖层中的警告**会进行**标记。

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="边栏导航菜单中的链接具有足够的对比度，如检查覆盖中所示" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            边栏导航菜单中的链接具有足够的对比度，如检查**覆盖中所示** :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="检查覆盖层中的警告标记了对比度不足的元素" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            "检查"覆盖层中的警告标记了对比度 **不足** 的元素 :::image-end:::
    :::column-end:::
:::row-end:::
        

## <a name="hovering-when-the-inspect-tool-is-active-doesnt-show-the-text-color-contrast-for-the-hover-state"></a>当 Inspect 工具处于活动状态时悬停不会显示悬停状态的文本颜色对比度

**Inspect**工具的信息覆盖层仅表示单个状态。  页面上的元素可以有不同的状态，所有这些状态都需要进行测试。  例如，当你将鼠标指针悬停在辅助功能测试演示页面的菜单上时，你得到一个更改颜色的动画。 执行以下步骤。

1.  打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。

1.  将鼠标悬停在边栏导航菜单中的蓝色菜单项上。  请注意，每个项目都有一个动画。

    :::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="鼠标指针悬停在不同的菜单项上时显示不同的颜色" lightbox="../media/a11y-testing-hover.msft.png":::
        鼠标指针悬停在不同的菜单项上时显示不同的颜色
    :::image-end:::
    
现在，使用 Inspect 工具。 使用 Inspect 工具时，将鼠标悬停在菜单项上时，不会运行菜单项上的动画。  使用 Inspect 工具时，你无法达到菜单项上的状态来测试对比率，因为你的样式中的状态 `hover` `hover` 不会触发。  
    
若要确认动画不运行，请执行以下步骤。
    
1.  选择 DevTools 左上角的"检查 **\(** 检查"按钮 \) 按钮，以便图标以蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。

1.  将鼠标悬停在边栏导航菜单上的蓝色链接上。  菜单项的动画不会运行。 相反，菜单项使用弹性框覆盖的颜色和突出显示来显示。

如此检查是否有足够的文本对比度是不够的，因为页面上的元素可能具有不同的状态。


## <a name="use-state-simulation-to-simulate-the-hover-state-of-an-animated-menu-item"></a>使用状态模拟模拟动画菜单项的悬停状态 

<!-- Elements tool: Styles pane: Toggle Element State -->

当 **Inspect** 工具处于活动状态时，你需要模拟菜单项的状态，而不是将鼠标悬停在动画元素上。  若要模拟菜单项的状态，请使用"样式" **窗格中的状态模拟** 。  " **样式"** 窗格有一个 **\：hov** (**Toggle Element State**) 按钮，该按钮显示一组标记为 **"Force 元素状态"的复选框**。

若要在使用 Inspect 工具时打开悬停状态：

1.  如果尚未打开，请打开新选项卡 [中的][DevToolsA11yErrorsDemopage] 辅助功能测试演示网页。 然后选择 **F12** 以打开 DevTools。

1.  选择 DevTools 左上角的"检查 **\(** 检查工具按钮 \) "按钮，使图标以蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。

1.  在呈现的网页中，选择边栏导航菜单中的蓝色 **"猫** "链接。  将 **打开"** 元素"工具，并选中 `<a href="#cats">Cats</a>` 元素。

    :::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="检查元素工具中具有悬停状态的元素" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
        检查元素工具中具有悬停状态的元素
    :::image-end:::

1.  选择"**样式"** 选项卡。 所选 `a` 元素在应用于它的 CSS 中具有一个状态，但在"样式"窗格中不可见 `hover` 。 **** 

1.  在 **样式** 窗格中的样式规则右侧， `#sidebar nav li a` 选择 `styles.css` 链接。  将 **打开"** 源"工具。  然后查找 CSS 伪类规则 `#sidebar nav li a:hover` 。  当 Inspect 工具处于活动状态时， **此规则** 不运行。  我们将在下一步中模拟运行此状态规则。

1.  选择" **元素"** 工具。  然后在"**样式"** 窗格中，选择"：hov (**Toggle 元素状态) **按钮。 ****  显示 **复选框的 Force** 元素状态组。

    :::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="显示所有选项的状态模拟工具" lightbox="../media/a11y-testing-state-simulation.msft.png":::
        显示所有选项的状态模拟工具
    :::image-end:::

1.  选中 **"：hover"** 复选框。  在 DOM 中，元素左侧将出现一个黄色点，指示元素 `<a href="#cats">Cats</a>` 具有模拟状态。  " **猫** "菜单项现在显示在网页中，就像指针悬停在它上方一样。  菜单项上的动画可能会运行。

    :::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="模拟悬停状态的开发工具" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
        模拟悬停状态的开发工具
    :::image-end:::

    应用模拟状态后，可以再次使用 **Inspect** 工具在用户将鼠标悬停在元素上时检查元素的对比度，如下所示。

1.  选择 DevTools 左上角的"检查 **\(** 检查器图标 \) "按钮，以便该图标在蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。

1.  将鼠标悬停在边栏导航菜单中的蓝色 **"猫** "链接上。  由于模拟悬停动画，该链接现在为浅蓝色。  将显示**Inspect**工具的信息覆盖层，在"对比度"行中显示橙色感叹**** 号，指示对比度不够高。

    :::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="在模拟悬停状态中测试元素的对比度" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
        在模拟悬停状态中测试元素的对比度
    :::image-end:::

状态模拟也是检查你是否认为不同的用户需求（如键盘用户的需求）的一个好方法。  通过使用 **Force 元素状态** 复选框，你可以模拟状态，发现 UI 在具有焦点时 `:focus` 保持不变。 当元素具有焦点时缺少指示器是一个问题。


## <a name="see-also"></a>另请参阅

*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
