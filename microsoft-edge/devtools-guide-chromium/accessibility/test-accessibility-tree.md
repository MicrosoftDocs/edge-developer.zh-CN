---
description: 检查辅助功能树是否支持键盘和屏幕阅读器。
title: 检查辅助功能树是否支持键盘和屏幕阅读器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 0ab5e5609485505d1ad5fa6e2fffced9af25edcb
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597300"
---
# <a name="check-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a>检查辅助功能树是否支持键盘和屏幕阅读器

<!-- Accessibility tab: Accessibility Tree -->

多个 DevTools 功能检查键盘和屏幕阅读器支持。  使用 **Inspect** 工具单独检查每个页面元素的辅助功能可能会相当耗时。  检查网页的另一种方式是使用 **辅助功能树**。  辅助功能 **树** 指示页面向辅助技术（如屏幕阅读器）提供哪些信息。

辅助功能 **树** 是 DOM 树的子集，其中包含 DOM 树中的元素，这些元素对于在屏幕阅读器中显示页面内容非常有用。  辅助功能**树位于**"元素"工具**** 的"辅助功能"选项卡**** ("**样式**"选项卡) 。


若要浏览将辅助功能树与演示页面一同使用：

1.  打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。 然后选择 **F12** 以打开 DevTools。

1.  选择**** DevTools (左上角的"检查 "\) 图标 \) 按钮，使按钮突出显示为蓝色 ![ ](../media/inspect-icon.msft.png) () 。

1.  在呈现的网页的"捐赠 **"部分** ，将鼠标悬停在 **"100"** 按钮上。  将显示 **"检查** "工具覆盖。

1.  在呈现的网页中，选择 **"100"** 按钮。  在 DevTools 中， **将显示"元素** "工具。  DOM 树显示 `div` **100 按钮的元素** 。  " **样式** "窗格显示元素的 CSS 设置。

1.  在" **样式"选项卡** 的右侧，选择 **"辅助功能"** 选项卡。 将显示 **元素的** 辅助功能树，并展开。

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="辅助功能树工具中的"资金"表单按钮" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    辅助功能树工具中的"资金"表单按钮
:::image-end:::

树中没有名称或具有 (角色的任何元素（如 `generic` 元素) ）都是一个问题，因为该元素对键盘用户或正在使用辅助技术的用户不可用。 `div`


## <a name="see-also"></a>另请参阅

*  [查看元素在辅助功能树中的位置][DevtoolsAccessibilityAccessibilityTabViewTree]
*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityAccessibilityTabViewTree]: accessibility-tab.md#view-the-position-of-an-element-in-the-accessibility-tree "使用&quot;辅助功能&quot;选项卡视图元素在&quot;辅助功能树 - 测试辅助功能&quot;|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
