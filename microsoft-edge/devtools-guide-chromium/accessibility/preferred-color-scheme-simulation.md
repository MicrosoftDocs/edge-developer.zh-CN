---
title: 强制 Microsoft Edge DevTools 进入配色方案预览模式（CSS 首选配色方案）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a83284b676ad388114a4a0ddb7ebdf2203ebcb90
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758061"
---
# 深色或浅色配色方案模拟  

操作系统可以以较暗或较亮的颜色显示任何应用程序。  在深色模式操作系统中拥有具有浅色主题的 web 产品是 grating，并且可能是某些用户的辅助功能问题。  在 web 上，你可以使用[喜欢的配色方案][MDNPrefersColorScheme]CSS 媒体查询来检测用户是否希望在较暗或更亮的颜色方案中查看你的产品。  使用[Microsoft Edge DevTools][DevtoolsGuideChromiumMain]模拟从深色到浅色模式的更改，而无需更改整个操作系统。  

1.  打开 "**命令" 菜单**。  
    1.  按 `Control` + `Shift` + `P` Windows 或 `Command` + `Shift` + `P` macOS。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **命令菜单**  
        :::image-end:::   
        
1.  类型 `emulate color` ，请选择 "**模拟 css 首选色"-颜色方案： "深色**" 或 "**模拟 css 首选色"-颜色方案： "浅色**"，然后按 `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="从 命令 菜单中选择的配色方案" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       从 "**命令**" 菜单中选择的配色方案  
    :::image-end:::  
    
    > [!IMPORTANT]
    > 只需键入 `dark` 或 `light` 不显示正确的工具，因为还有一种方法可为[DevTools 选择主题][DevtoolsGuideChromiumCustomizeDarkTheme]。  如果您想要选择哪些内容，请确保您选择的是 "**呈现**" 菜单项，而不是 "**外观**" 菜单项。  

1.  选择配色方案后，重新加载当前文档以查看模拟模式。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 中的模拟轻型模式" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       Microsoft Edge DevTools 中的模拟轻型模式  
    :::image-end:::  
    
    像查看其他网页一样查看和更改您的 CSS。  有关详细信息，请参阅[查看和更改 CSS 入门][DevtoolsGuideChromiumCssIndex]。  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge （Chromium）开发人员工具 Microsoft |Microsoft 文档"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "在 Microsoft Edge DevTools 中启用深色主题 |Microsoft 文档"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "首选-配色方案 |MDN"  
