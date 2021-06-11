---
description: 使用颜色选取器测试文本颜色对比度。
title: 使用颜色选取器测试文本颜色对比度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f4ba5f3706460c443ae06a393e5ef63e5d336229
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597317"
---
<!-- this article was created on 05/11/2021 by moving a section out from the "Accessibility reference" article (reference.md) -->
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="test-text-color-contrast-using-the-color-picker"></a>使用颜色选取器测试文本颜色对比度

低视力用户可能无法看到非常明亮或非常暗的区域。  所有内容通常以相同的亮度级别显示，这使得难以区分轮廓和边缘。  

对比率测量文本的前景和背景的亮度差。  如果文本的对比度比率较低，则低视力用户可能会将网站体验为空白屏幕。  

在 DevTools 中，查看文本元素的对比率的一个方法就是从"样式"选项卡使用 **颜色选取** 器。 颜色选取器可帮助你验证文本是否满足建议的对比率级别。

**若要使用颜色选取器检查文本颜色对比度：**

1.  在 DevTools 中，选择 **"元素"** 工具。  
1.  在 **DOM 树**中，选择要检查的文本元素。  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="检查 DOM 树中的段落" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       检查 **DOM 树**中的段落  
    :::image-end:::  
    
1.  在 **"样式**"选项卡上，**** 找到应用于元素的颜色属性，然后选择颜色属性旁边的**颜色**正方形。
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="元素的颜色属性" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       元素的 `color` 属性  
    :::image-end:::  
    
1.  检查 **颜色选取器** 中的"对比率"部分。  一个选中标记表示元素满足最低 [建议][W3CContrastMinimum]。  两个选中标记表示它符合增强 [的建议][W3CContrastEnhanced]。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="颜色选取器中的对比率部分显示 2 个选中标记和 13.97 值" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       颜色 **选取器** 中的"对比率"部分显示 2 个选中标记和一个值 `13.97`  
    :::image-end:::  
    
1.  有关详细信息，请选择"对 **比率"** 部分以展开它。  在颜色选取器顶部的可视选取器中，显示两行，在可视选取器中运行，以及一个圆表示当前颜色。  如果当前颜色符合建议，则该行的同一侧任何内容也符合建议。  如果当前颜色不满足建议，则同一侧的颜色也不符合建议。  

    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="可视选取器中的对比率行" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       可视选取器中的**对比率**行  
    :::image-end:::  

1. 若要尝试不同的颜色，请在可视化选取器中选择，或在颜色选取器底部选择颜色样本。
    

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  


<!-- links -->  
[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "对比度级别（增强） AAA | W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "对比度 (级别 AA) 最低|W3C"  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
