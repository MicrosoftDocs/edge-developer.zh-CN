---
description: 强制Microsoft Edge开发人员工具进入配色方案预览模式。
title: '强制Microsoft Edge开发工具进入配色方案预览模式 (CSS 首选配色方案) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: dc2911ce7a7fcbeef7763099541822b5cd6cf053
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597067"
---
# <a name="dark-or-light-color-scheme-simulation"></a>深色或浅色配色方案模拟  

许多操作系统都有一种以较暗或更浅的颜色显示任何应用程序的方法。  在深色模式操作系统中具有浅色主题的 Web 产品很正常，并且对于某些用户来说可能是一个辅助功能问题。  

对于网页，您可以使用首选配色 [方案][MDNPrefersColorScheme] CSS 媒体查询来检测用户是否希望以较暗或更浅的配色方案显示产品。  然后，若要测试结果，Microsoft Edge [DevTools][DevtoolsIndex]模拟从深色模式到浅色模式的变化，而无需更改整个操作系统的设置。  

**模拟深色或浅色主题：**

1.  打开“**命令菜单**”。  
    1.  选择 `Ctrl` + `Shift` + `P` \ (Windows/Linux\) `Command` + `Shift` + `P` 或 \ (macOS\) 。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **命令菜单**  
        :::image-end:::  
        
1.  键入 `emulate color` ，选择模拟 **CSS prefers-color-scheme： dark** 或 Emulate CSS **prefers-color-scheme： light，** 然后选择 `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="命令菜单中的配色方案选项" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       命令菜单中的 **配色方案** 选项  
    :::image-end:::  
    
    > [!IMPORTANT]
    > 只需键入或不会显示正确的工具，因为还有一种方法可以选择 `dark` `light` [DevTools 的主题][DevtoolsCustomizeDarkTheme]。  如果想知道要选择什么，请确保选择的是呈现菜单项，而不是**外观**菜单项****。  

1.  选择配色方案后，刷新当前文档以显示模拟模式。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="DevTools Microsoft Edge模拟光模式" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       DevTools Microsoft Edge模拟光模式  
    :::image-end:::  
    
    像查看任何其他网页一样查看和更改 CSS。  有关详细信息，请导航到开始[查看和更改 CSS。][DevtoolsCssIndex]  


## <a name="see-also"></a>另请参阅

* [检查深色主题和浅主题的对比度问题](test-dark-mode.md)


<!-- links -->  
[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsCustomizeDarkTheme]: ../customize/dark-theme.md "在 DevTools Microsoft Edge中启用深色|Microsoft Docs"
[DevtoolsCssIndex]: ../css/index.md "开始查看和更改 CSS |Microsoft Docs"  
<!-- external links -->
[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
