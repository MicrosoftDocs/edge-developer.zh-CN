---
title: 模仿 Microsoft Edge DevTools 中的视觉缺陷（色盲）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b70499fa189d162fa7589966bab183f4c12f68f7
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843919"
---
# 模仿视觉缺陷

为了更好地满足用户使用[颜色视觉缺陷][ColorblindawarenessMain]的需要 \ （色盲 \）， [Microsoft Edge DevTools][MicrosoftEdgeDevTools]使你能够模拟特定的颜色视觉缺陷。  "**模拟远景缺陷**" 工具模拟以下类别。  

| 颜色远景缺陷 | 详细信息 |  
|:--- |:--- |  
| 模糊视觉效果 | 用户很难关注详细信息。 |   
| Protanopia | 用户无法感知任何红光。 |  
| Deuteranopia | 用户无法感知任何绿色光。 |  
| Tritanopia | 用户无法感知任何蓝色光线。 |  
| Achromatopsia | 用户无法感知任何颜色，这种颜色会将所有颜色降低为灰色底纹。 |  

## 导航到 "渲染工具"  

若要模拟为您的 web 产品应用的远景缺陷，请打开 "[渲染工具][RenderingTools]"。  

1.  通过选择 `...` 工具栏中的菜单项打开呈现工具  
1.  选择 `More tools`  
1.  选择 `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="打开渲染工具" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       打开**渲染工具**  
    :::image-end:::  

"**呈现**" 菜单显示在抽屉中。  

1.  向下滚动到 `Emulate vision deficiencies` 菜单项并选择下拉菜单以显示选项。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="呈现抽屉上的 模拟远景缺陷 菜单" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       **呈现**抽屉上的 "**模拟远景缺陷**" 菜单  
    :::image-end:::  
    
1.  选择一个选项。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="模拟远景缺陷 菜单选项" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       "**模拟远景缺陷**" 菜单选项  
    :::image-end:::  
    
1.  主窗口显示应用到当前页面的选定选项的模拟。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="使用 * * 模糊视觉效果 * * 模拟显示" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             使用**模糊视觉**模拟显示  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="使用 * * Achromatopsia * * 模拟显示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             使用**Achromatopsia**模拟进行显示 :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## 使用 "命令" 菜单  

您也可以使用 "**命令" 菜单**访问不同的模拟。  

1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `emulate` ，选择要模拟的内容，然后按 `Enter` 。  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="命令 菜单中提供的不同模拟选项" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       "**命令" 菜单**中提供的不同模拟选项  
    :::image-end:::  
    
> [!IMPORTANT]
> "**模拟远景处理不足**" 工具模拟每个缺陷的人可以查看你的产品的具体程度。  每个人都是不同的，因此视力缺陷在人员间的严重性方面各不相同。  为了更好地满足用户需求，请避免可能出现问题的任何颜色组合。  "**模拟远景缺陷**" 工具不是产品的完全辅助功能评估。  相反，"**模拟远景缺陷**" 工具应为您提供一个良好的第一步，以避免问题。  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org ""彩色盲人" 感知组织"  
[AmfcbMain]: https://www.amfcb.org "色盲（AFCB）的美洲地基"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge （Chromium）着色工具"  
