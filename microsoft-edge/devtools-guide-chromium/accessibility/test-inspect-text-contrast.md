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
# <a name="check-text-color-contrast-in-the-default-state-using-the-inspect-tool"></a>使用 Inspect 工具检查默认状态下的文本颜色对比度

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

使用 Inspect 工具检查默认状态下的文本**颜色对比度。**  " **检查** "工具在网页上的信息覆盖具有一个 **"** 辅助功能"部分，其中包含 **"对比度"** 信息。

若要使用 Inspect 工具的信息覆盖层检查默认状态下的文本颜色对比度，请执行以下步骤。

<!-- Inspect tool -->
对于具有文本的元素 **，Inspect** 工具的信息覆盖层显示以下内容：
*  文本与背景颜色的对比率。
*  具有足够对比度的元素的绿色选中标记图标。
*  没有足够对比度的元素的黄色警报图标。

在某些情况下，将浏览器设置为浅色主题或深色主题会影响对比度。

例如，在演示页面上，边栏导航菜单的蓝色链接具有足够的对比度，但"发送状态"部分中的绿色****"动物"链接**** 没有足够的对比度。  使用 Inspect 工具查看 **这些** 元素，如下所示：

1.  打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。 然后选择 **F12** 以打开 DevTools。

1.  选择 DevTools 左上角的"检查 **\ (** 检查"按钮 \) 按钮，使图标以蓝色 (![ ](../media/inspect-icon.msft.png) 突出显示) 。

1.  在呈现的网页中，将鼠标悬停在边栏导航菜单的蓝色 **"猫** "链接上。  将显示 **Inspect** 工具的信息覆盖层。  在信息**覆盖的**"辅助功能"部分中，"对比度"行上会显示一个**** 绿色选中标记，指示此元素具有足够的文本颜色与背景色对比度。

    :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="菜单项具有足够的对比度，如 Inspect 工具中所示" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
        菜单项具有足够的对比度，如 Inspect 工具中所示
    :::image-end:::

1.  在呈现的网页的"私人 **状态"** 部分，将鼠标悬停在 **"动物"** 链接上。  **Inspect 工具**的信息覆盖层在 Contrast 行上显示橙色感叹号****，指示此元素没有足够的文本与背景色对比度。

    :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="对比度不足的元素，如 Inspect 工具中的警告所示" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
        对比度不足的元素，如 Inspect 工具中的警告所示
    :::image-end:::


## <a name="different-options-to-inspect-text-color-contrast-in-devtools"></a>在 DevTools 中检查文本颜色对比度的不同选项

使用以下 DevTools 功能检查文本颜色对比度。

*  使用 **检查** 工具 (网页上的信息覆盖) 检查单个页面元素是否具有足够的文本颜色对比度。  Inspect **** 工具的信息覆盖包括一个 **"辅助功能"** 部分，其中包含 **"对比度**"信息行。  检查 **工具** 只显示当前状态的文本对比度信息。  此方法在当前文章中进行了介绍。

*  当 **文本** 和背景色的对比度不够时，问题工具将自动报告整个网页的任何颜色对比度问题。  验证文本颜色是否具有足够的 [对比度中介绍了此方法](test-issues-tool.md#verify-that-text-colors-have-enough-contrast)。

*  通过使用"样式"窗格中的"切换元素状态"模拟非默认状态，如状态，如验证元素的所有 `hover` [状态辅助功能中所述](test-inspect-states.md)。 **** ****


## <a name="see-also"></a>另请参阅

*  [验证所有元素状态可访问性][DevtoolsAccessibilityTestInspectStates]
*  [使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题](test-inspect-tool.md)
*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityTestInspectStates]: test-inspect-states.md "验证元素的所有状态是否可访问|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
