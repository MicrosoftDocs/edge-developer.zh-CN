---
description: 使用呈现工具中的"模拟 CSS 媒体功能首选-配色方案\"下拉列表) 检查深色主题和浅色主题 (的对比度问题。
title: 检查深色主题和浅主题的对比度问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 052c75b610ec872329f387e46819867f299a8ca9
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597285"
---
# <a name="check-for-contrast-issues-with-dark-theme-and-light-theme"></a>检查深色主题和浅主题的对比度问题

<!-- Rendering tool: Emulate CSS media feature prefers-color-scheme -->

测试颜色辅助功能时，可能需要测试不同的显示颜色主题，以测试对比度问题。

大多数操作系统都提供深色模式和浅色模式。  您的网页可以使用 CSS 媒体查询对此操作系统设置做出反应。  您可以使用呈现工具中的 CSS 选项测试这些主题并测试 CSS 媒体查询，而无需更改 `prefers-color-scheme` **操作系统** 设置。

例如，辅助功能测试演示页面包括浅色主题和深色主题。  演示页面从操作系统继承深色或浅色主题设置。  如果我们使用 DevTools 模拟将操作系统设置为浅色方案，然后刷新演示网页，问题工具将显示六个**** 色对比度问题，而不是两个。   (你可能会看到不同的数字。) 


若要模拟用户的首选颜色主题选择：：

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  选择 **Esc** 打开 DevTools 底部的"箱"。  Select the **+** icon at the top of the Drawer to see the list of tools， and then select **Rendering**.  将显示呈现工具。

1.  在模拟 **CSS 媒体功能 prefers-color-scheme** 下拉列表中，选择 **prefers-color-scheme： light**。      网页使用 重新呈现 `light-theme.css` 。


    :::image type="complex" source="../media/a11y-testing-simulating-light-mode.msft.png" alt-text="使用呈现工具模拟光线模式并触发文档的其他主题" lightbox="../media/a11y-testing-simulating-light-mode.msft.png":::
        使用呈现工具模拟光线模式并触发文档的其他主题
    :::image-end:::


1.  选择 **"问题** "工具，然后展开 **"辅助功能"** 部分。  根据各种因素，你可能会收到 `Insufficient color contrast` 警告。 请注意， **在受影响的资源** 中，有 6 个元素的颜色对比度不足。
    
    :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="由于浅色主题更改而检测到的新对比度问题" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
        由于浅色主题更改而检测到的新对比度问题
    :::image-end:::
    
    在我们的演示页面上，页面的 **"私人** 状态"部分在浅色模式下不可读，需要更改。 
    
    :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="在浅色模式下，接收状态部分有对比度问题" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
        在 **浅色模式下** ，"接收状态"部分有对比度问题
    :::image-end:::
    
1.  在 DevTools 中，选择 **"元素**"工具，然后选择 macOS 上的 Windows/Linux 或 Command+F 上的**Ctrl+F。** ****  将显示 **"** 查找"文本框，以在 HTML DOM 树中搜索。
 
1.  输入 `scheme` 。  找到以下 CSS 媒体查询，现在可更新相应的 CSS 文件。

    ```html
    <link rel="stylesheet" href="css/light-theme.css" media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)">
    <link rel="stylesheet" href="css/dark-theme.css" media="(prefers-color-scheme: dark)">
    ```


## <a name="see-also"></a>另请参阅

*  [深色或浅色配色方案模拟][DevToolsColorSchemeSimulation]
*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "深色或浅色配色方案模拟|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
