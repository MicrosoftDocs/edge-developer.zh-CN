---
title: 模仿 Microsoft Edge DevTools 中的视觉缺陷（色盲）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0b608f5fe67724eee81aeb993577ee9b45cbca09
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758062"
---
# 模仿视觉缺陷

全球各地约有8% 的男士和0.5% 的女人有一个[颜色远景缺陷][ColorblindawarenessMain]，其中通常称为 "色盲"。  [Microsoft Edge DevTools][MicrosoftEdgeDevTools]使你能够模拟各种已知的缺陷，并提供你的产品预览版供你查看。  

| 颜色缺陷 | 详细信息 |  
|:--- |:--- |  
| 模糊视觉效果 |  |   
| Protanopia | 无法感觉任何红光。 |  
| Deuteranopia | 无法感觉任何绿色光。 |  
| Tritanopia | 无法感觉任何蓝色光线。 |  
| Achromatopsia | 除了灰色底纹之外，无法感觉任何颜色。 |  

## 导航到 "渲染工具"  

若要测试当前 web 产品的色彩不足，请打开 "[渲染工具][RenderingTools]"。  

1.  通过选择 `...` 工具栏中的菜单项打开呈现工具  
1.  选择 `More tools`  
1.  选择 `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="打开渲染工具" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       打开**渲染工具**  
    :::image-end:::  

**呈现**菜单显示在 DevTools 的下半部分。  

1.  向下滚动到 `Emulate Vision deficiencies` 菜单项，然后从选项中进行选择。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="渲染工具的 "模拟远景缺陷" 菜单" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       **渲染**工具的 "**模拟远景缺陷**" 菜单  
    :::image-end:::  
    
1.  选择任何选项  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text=""模拟远景缺陷" 菜单选项" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       "**模拟远景缺陷**" 菜单选项  
    :::image-end:::  
    
1.  当前页面将以模拟其对具有所选缺陷的用户显示的方式进行显示。  

    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="模糊视觉模拟中的 Microsoft Edge 开发人员工具文档" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             使用**模糊视觉**模拟进行显示  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Achromatopsia 视觉模拟中的 Microsoft Edge 开发人员工具文档" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             使用**Achromatopsia 视觉**模拟进行显示 :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## 使用 "命令" 菜单  

您也可以通过使用 "**命令" 菜单**来访问不同的模拟，而无需使用各种菜单。  

1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `emulate` ，选择要模拟的内容，然后按 `Enter` 。  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text=""命令" 菜单中提供的不同模拟选项" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       "**命令" 菜单**中提供的不同模拟选项  
    :::image-end:::  
    
> [!IMPORTANT]
> 模拟工具近似于具有每种缺陷的人可以查看您的产品。  每个人都是不同的，因此视力缺陷在人员间的严重性方面各不相同。  为了更好地满足用户需求，请避免可能出现问题的任何颜色组合。  模拟工具不是对产品辅助功能的完全评估，但你应该先有一个良好的步骤来避免最大的缺陷。  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org ""彩色盲人" 感知组织"  
[AmfcbMain]: https://www.amfcb.org "色盲（AFCB）的美洲地基"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge （Chromium）着色工具"  
