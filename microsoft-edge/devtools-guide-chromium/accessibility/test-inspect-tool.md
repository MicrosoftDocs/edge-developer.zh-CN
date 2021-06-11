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
# <a name="use-the-inspect-tool-to-detect-accessibility-issues-by-hovering-over-the-webpage"></a>使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题

当您 **将** 鼠标悬停在呈现的网页上时，Inspect 工具将显示有关各个元素的信息，包括辅助功能信息。
相比之下，" **问题"** 工具会自动报告整个网页的问题。

检查 **工具** 按钮 \(Inspect ![ ](../media/inspect-icon.msft.png) \) 位于 DevTools 的左上角。  选择" **检查工具"** 按钮时，该按钮将变为蓝色，指示 **"检查** "工具处于活动状态。

当 **Inspect 工具** 处于活动状态时，将鼠标悬停在呈现网页上的任何元素上将显示 **Inspect** 覆盖。 此覆盖层显示有关该元素的常规信息和辅助功能信息。  "**检查"覆盖****层的**"辅助功能"部分显示有关文本颜色对比度、屏幕阅读器文本和键盘支持的信息。

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="Inspect 工具，将元素的区域作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    **Inspect**工具，将元素的区域作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示
:::image-end:::


## <a name="check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a>检查各个元素的文本对比度、屏幕阅读器文本和键盘支持

<!-- Inspect tool: Accessibility section of overlay -->

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  选择**** DevTools 左上角的"检查 \(检查 \) "按钮，使图标突出显示为蓝色 ![ ](../media/inspect-icon.msft.png) () 。

    :::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="若要打开"检查"工具，请选择"检查"按钮" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
        若要打开"检查 **"** 工具，请选择" **检查"** 按钮
    :::image-end:::

1.  将鼠标悬停在呈现的演示网页中的任意元素上。  Inspect **工具** 在呈现的网页中的 元素下方显示信息覆盖层。

    :::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="Inspect 工具，将元素的布局作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
        **Inspect**工具，将元素的布局作为多色覆盖层显示，将元素的详细信息作为大型信息覆盖层显示
    :::image-end:::

检查覆盖 **的底部有** 一个 **辅助功能** 部分，其中包含以下信息：

*   **对比度** 定义低视力用户能否理解元素。  [WCAG][WCAG]准则定义的对比率指示是否有足够的对比度 (绿色选中标记图标) 或 (橙色感叹号-点) 。 [][W3CContrastRatio]

*   **名称和****角色**是屏幕阅读器等辅助技术将报告有关元素的内容。
    *   **Name**是元素的文本 `a` 内容。  对于 元素 `<a href="/">About Us</a>` **，Inspect** 工具中显示的 Name 为"关于我们"。
    *   **元素**的角色。  这通常是元素名称，如 `article` `img` 、、 `link` 或 `heading` 。  `div`和 `span` 元素称为 `generic` 。

*   **键盘可聚焦** 指示用户是否可以访问元素，而不考虑输入设备。
    *   绿色选中标记图标指示元素是键盘可聚焦的。
    *   带对角线的灰色圆圈表示元素不可通过键盘聚焦。


## <a name="additional-information-in-the-inspect-overlay"></a>检查覆盖层中的附加信息

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

"检查"覆盖**的顶部**（位于"辅助功能"部分上方****）列出了元素的以下详细信息。

*   布局类型。 如果元素是使用弹性框或网格放置的，则图标 \(![网格布局图标](../media/grid-icon.msft.png)\) 显示。
*   元素的名称，如 、 `h1` `h2` 或 `div` 。
*   元素的尺寸（以像素为单位）。
*   作为颜色样本的颜色颜色 (或较小的、彩色的) 和字符串形式 (如 `#336699`) 。
*   字体信息，如大小和字体系列。
*   边距和填充（以像素为单位）。


## <a name="identify-nested-regions-using-color-highlighting"></a>使用颜色突出显示标识嵌套区域 

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

除了信息覆盖之外 **，Inspect** 工具还提供区域颜色，类似于在"元素"工具的 DOM 树 **中** 悬停。

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  选择**** DevTools 左上角的"检查"按钮 \(Inspect 工具图标 \) ，使按钮突出显示为蓝色 ![ ](../media/inspect-icon.msft.png) () 。

1.  将鼠标悬停在呈现的演示网页的不同部分上。  网页中的每个元素现在都显示一个多色覆盖。 此多色覆盖层可以显示元素内部的嵌套区域。 例如，将鼠标悬停在"猫"的 **左边距上**。  Inspect **工具** 使用不同颜色突出显示 **"猫** "部分的几个矩形部分，显示来自网页上 CSS 弹性框定义的布局。

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="使用 Inspect 工具时的多色弹性框覆盖和信息覆盖" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    使用 Inspect 工具时的多色弹性框覆盖 **和信息** 覆盖
:::image-end:::

若要配置网格覆盖或弹性框覆盖，请在 **"元素**"工具中选择"布局 **"** 选项卡。 有关详细信息，请导航到"[检查 CSS 网格"。](..\css\grid.md)


## <a name="use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a>使用"检查"工具将鼠标悬停在网页上方以突出显示 DOM 和 CSS

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  选择**** DevTools (左上角的"检查"按钮 \) "检查"工具 \) ，以便该按钮突出显示为 (![ ](../media/inspect-icon.msft.png) 蓝色) 。

1.  选择" **元素"** 工具。

1.  在 **"检查** "工具处于活动状态时，将鼠标悬停在呈现的网页的不同部分上。  在 **"元素** "工具中，HTML DOM 树会自动展开以显示有关您将鼠标悬停在的元素的信息。  悬停不会导致" **样式"** 窗格更新。

1.  现在，选择呈现的网页内的任何元素。  " **元素** "工具会自动打开并显示 DOM 树中元素的 HTML。 该工具还会在"样式"窗格中的 **元素上显示** 应用的 CSS。  选择呈现网页上的元素将关闭 **"检查"** 工具。

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="有关所选元素的详细信息将显示在"元素"工具中" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    有关所选元素的详细信息将显示在 **"** 元素"工具中
:::image-end:::

在呈现的页面中选择元素后，可以使用"样式"选项卡**** (附近的"辅助功能"选项卡) 查看****"辅助功能树"并使用"源顺序查看器******"。**


## <a name="see-also"></a>另请参阅

*  [检查节点](../dom/index.md#inspect-a-node)
*  [使用 Inspect 工具检查默认状态下的文本颜色对比度](test-inspect-text-contrast.md)
*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "对比率|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web 内容辅助功能指南|W3C"
