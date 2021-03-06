---
description: 模拟 Microsoft Edge DevTools 中的视觉缺陷。
title: '模拟 Microsoft Edge DevTools 中色盲 (缺陷) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/09/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: eec3c95bac93e600acf1887c8d31cea2173c6aee
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397872"
---
# <a name="emulate-vision-deficiencies"></a>模仿视觉缺陷

为了更好地满足色 [盲用户][ColorblindawarenessMain] \ (色盲\) 的需求 [，Microsoft Edge DevTools][DevtoolsIndex] 允许你模拟特定的颜色视觉缺陷。  模拟 **视觉缺陷** 工具模拟以下类别。  

| 颜色视力缺陷 | 详细信息 |  
|:--- |:--- |  
| 模糊的视觉 | 用户难以专注于细节。 |  
| 红色盲 | 用户无法感知任何红色光。 |  
| 绿色盲 | 用户无法感知任何绿色光。 |  
| 黄蓝色盲 | 用户无法感知任何蓝色光。 |  
| 全色盲 | 用户无法感知任何颜色，从而将所有颜色都缩小为灰色底纹。 |  

## <a name="navigate-to-the-rendering-tools"></a>导航到呈现工具  

若要模拟对 Web 产品应用的视觉缺陷，请打开 [呈现工具][DevtoolsRenderingToolsIndex]。  

1.  若要打开呈现工具，请选择 `...` 工具栏中的菜单项  
1.  选择 **更多工具**  
1.  选择 **"呈现"**  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="打开呈现工具" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       打开 **呈现工具**  
    :::image-end:::  

" **呈现** "菜单显示在箱中。  

1.  向下滚动到 `Emulate vision deficiencies` 菜单项，然后选择下拉菜单以显示选项。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="呈现器上的"模拟视力缺陷"菜单" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       呈现 **器上的"模拟** 视觉缺陷 **"** 菜单  
    :::image-end:::  
    
1.  选择一个选项。  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text=""模拟视力缺陷"菜单选项" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       " **模拟视觉缺陷"菜单** 选项  
    :::image-end:::  
    
1.  主窗口显示应用于当前页面的所选选项的模拟。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="使用 **模糊的视觉** 模拟显示" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             使用**模糊视觉模拟显示**  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="使用 **Achromatopoma** 模拟显示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             使用 **Achromatopoma 模拟** 显示 :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <a name="use-the-command-menu"></a>使用命令菜单  

您还可以使用 **命令菜单** 访问不同的模拟。  

1.  选择 `Control` + `Shift` + `P` \ (Windows/Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开**命令菜单**。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `emulate` ，选择要模拟的，然后选择 `Enter` 。  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="命令菜单中提供的不同模拟选项" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       命令菜单中提供的不同模拟 **选项**  
    :::image-end:::  
    
> [!IMPORTANT]
> 模拟 **视觉缺陷工具** 模拟每个缺陷的人如何查看你的产品的近似值。  每个人都不同，因此视觉缺陷因人而异。  为了更好地满足用户的需求，请避免任何可能导致问题的颜色组合。  模拟 **视觉缺陷** 工具不是产品的完整辅助功能评估。  相反， **模拟视觉缺陷** 工具应为您提供一个很好的第一步以避免出现问题。  

<!-- links -->  

[DevToolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsRenderingToolsIndex]: ../rendering-tools/index.md "分析运行时性能|Microsoft Docs"  

[ColorblindawarenessMain]: http://www.colourblindawareness.org "色盲意识组织"  

[AmfcbMain]: https://www.amfcb.org "美国色盲组织 (AFCB) "  
