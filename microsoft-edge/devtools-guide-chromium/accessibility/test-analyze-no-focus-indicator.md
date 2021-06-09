---
description: 分析边栏菜单中缺少键盘焦点指示，因为链接上的焦点状态缺少 CSS 伪类规则，再加上该链接没有大纲设置。
title: 分析边栏菜单中键盘焦点的缺失
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3626de9bdc2cce266efafe4b1b2e8fff501a74f7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597299"
---
# <a name="analyze-the-lack-of-indication-of-keyboard-focus-in-a-sidebar-menu"></a>分析边栏菜单中键盘焦点的缺失

<!-- Inspect tool, and CSS rules: pseudo-classes for states -->

在辅助功能测试演示页中，使用键盘时，包含蓝色链接的边栏导航菜单不会直观地指示哪个链接具有焦点。  为了找出为什么边栏菜单使键盘用户感到困惑，我们将查找适用于 和 状态的 CSS 伪类规则，以及链接大纲的 `hover` `focus` CSS 属性。  

此分析发现边栏导航菜单的链接中缺少键盘焦点指示的原因是：
*  链接 `a` 的 CSS 属性设置为 `outline: none` 。
*  这些 `a` 链接缺少状态 CSS 伪类 `:focus` 规则。

若要导航到 CSS，我们将使用 **Inspect** 工具突出显示边栏导航菜单上的蓝色链接，然后查看定义该链接的元素的 DOM 树和 `a` CSS。

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  选择**** DevTools 左上角的"检查 \ (检查图标 \) "按钮，以便该按钮突出显示为 (![ ](../media/inspect-icon.msft.png) 蓝色) 。

1.  将鼠标悬停在边栏导航菜单中的蓝色 **"猫** "链接上。  将显示 Inspect 覆盖层，显示 `a` 元素是可键盘聚焦的。  但是覆盖层不会显示当链接具有焦点时没有视觉指示。

    接下来，我们将检查此链接的 CSS 样式。
 
1.  选择边栏导航菜单中的 **"猫** "链接。  检查 **工具** 将关闭， **并且元素** 工具将打开，突出显示 `a` DOM 树中的节点。

1.  选择" **样式"** 选项卡。 将显示 CSS `#sidebar nav li a` 规则，以及指向 中行号的链接 `styles.css` 。

    :::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="检查菜单中的链接的源代码和应用样式" lightbox="../media/a11y-testing-menu-link.msft.png":::
        检查菜单中的链接的源代码和应用样式
    :::image-end:::
    
1.  选择 CSS 文件的链接。  CSS 文件将在"源" **工具中** 打开。

    :::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="应用于"源"工具中链接的样式" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
        应用于"源"工具中链接的样式
    :::image-end:::
    
页面样式具有 CSS 伪类规则，用于指示在使用鼠标时位于哪个 `hover` 菜单项上 `#sidebar nav li a:hover` ：。  但是，没有 CSS 伪类规则，该状态在使用键盘时直观地指示您位于哪个菜单项上， `focus` 例如 `#sidebar nav li a:focus` 。

此外，请注意链接的 CSS 属性设置为 `outline: none` 。  这是一种常见做法，当你使用键盘关注元素时，删除浏览器自动添加到元素的大纲。  不使用 `focus` 样式设置会导致用户混淆。


## <a name="see-also"></a>另请参阅 

*  [跟踪哪些元素有焦点](focus.md)
*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
