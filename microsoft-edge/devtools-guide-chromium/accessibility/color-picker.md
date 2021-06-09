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
# <a name="test-text-color-contrast-using-the-color-picker"></a><span data-ttu-id="ea4e6-104">使用颜色选取器测试文本颜色对比度</span><span class="sxs-lookup"><span data-stu-id="ea4e6-104">Test text-color contrast using the Color Picker</span></span>

<span data-ttu-id="ea4e6-105">低视力用户可能无法看到非常明亮或非常暗的区域。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-105">People with low vision may not see areas that are very bright or very dark.</span></span>  <span data-ttu-id="ea4e6-106">所有内容通常以相同的亮度级别显示，这使得难以区分轮廓和边缘。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-106">Everything tends to appear at about the same level of brightness, which makes it hard to distinguish outlines and edges.</span></span>  

<span data-ttu-id="ea4e6-107">对比率测量文本的前景和背景的亮度差。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-107">Contrast ratio measures the difference in brightness between the foreground and background of text.</span></span>  <span data-ttu-id="ea4e6-108">如果文本的对比度比率较低，则低视力用户可能会将网站体验为空白屏幕。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-108">If your text has a low contrast ratio, then people with low vision may experience your site as a blank screen.</span></span>  

<span data-ttu-id="ea4e6-109">在 DevTools 中，查看文本元素的对比率的一个方法就是从"样式"选项卡使用 **颜色选取** 器。 颜色选取器可帮助你验证文本是否满足建议的对比率级别。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-109">In DevTools, one way to view the contrast ratio of a text element is to use the Color Picker, from the **Styles** tab.  The Color Picker helps you verify that your text meets recommended contrast ratio levels.</span></span>

**<span data-ttu-id="ea4e6-110">若要使用颜色选取器检查文本颜色对比度：</span><span class="sxs-lookup"><span data-stu-id="ea4e6-110">To check the text-color contrast using the Color Picker:</span></span>**

1.  <span data-ttu-id="ea4e6-111">在 DevTools 中，选择 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-111">In DevTools, select the **Elements** tool.</span></span>  
1.  <span data-ttu-id="ea4e6-112">在 **DOM 树**中，选择要检查的文本元素。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-112">In the **DOM Tree**, select the text element that you want to inspect.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="检查 DOM 树中的段落" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       <span data-ttu-id="ea4e6-114">检查 **DOM 树**中的段落</span><span class="sxs-lookup"><span data-stu-id="ea4e6-114">Inspect a paragraph in the **DOM Tree**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea4e6-115">在 **"样式**"选项卡上，\*\*\*\* 找到应用于元素的颜色属性，然后选择颜色属性旁边的**颜色**正方形。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-115">On the **Styles** tab, locate the **color** property that's applied to the element, and then select the color square next to the **color** property.</span></span>
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="元素的颜色属性" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       <span data-ttu-id="ea4e6-117">元素的 `color` 属性</span><span class="sxs-lookup"><span data-stu-id="ea4e6-117">The `color` property of the element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea4e6-118">检查 **颜色选取器** 中的"对比率"部分。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-118">Examine the **Contrast Ratio** section of the Color Picker.</span></span>  <span data-ttu-id="ea4e6-119">一个选中标记表示元素满足最低 [建议][W3CContrastMinimum]。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-119">One check mark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span></span>  <span data-ttu-id="ea4e6-120">两个选中标记表示它符合增强 [的建议][W3CContrastEnhanced]。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-120">Two check marks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="颜色选取器中的"对比率"部分显示 2 个选中标记和 13.97 值" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       <span data-ttu-id="ea4e6-122">颜色 **选取器** 中的"对比率"部分显示 2 个选中标记和一个值</span><span class="sxs-lookup"><span data-stu-id="ea4e6-122">The **Contrast Ratio** section of the Color Picker shows 2 check marks and a value of</span></span> `13.97`  
    :::image-end:::  
    
1.  <span data-ttu-id="ea4e6-123">有关详细信息，请选择"对 **比率"** 部分以展开它。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-123">For more information, select the **Contrast ratio** section to expand it.</span></span>  <span data-ttu-id="ea4e6-124">在颜色选取器顶部的可视选取器中，显示两行，在可视选取器中运行，以及一个圆表示当前颜色。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-124">In the visual picker at the top of the Color Picker, two lines appear, running across the visual picker, along with a circle for the current color.</span></span>  <span data-ttu-id="ea4e6-125">如果当前颜色符合建议，则该行的同一侧任何内容也符合建议。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-125">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span></span>  <span data-ttu-id="ea4e6-126">如果当前颜色不满足建议，则同一侧的颜色也不符合建议。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-126">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span></span>  

    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="可视选取器中的对比率行" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       <span data-ttu-id="ea4e6-128">可视选取器中的**对比率**行</span><span class="sxs-lookup"><span data-stu-id="ea4e6-128">The **Contrast Ratio** Line in the visual picker</span></span>  
    :::image-end:::  

1. <span data-ttu-id="ea4e6-129">若要尝试不同的颜色，请在可视化选取器中选择，或在颜色选取器底部选择颜色样本。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-129">To try different colors, select within the visual picker, or select a color swatch at the bottom of the Color Picker.</span></span>
    

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ea4e6-130">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="ea4e6-130">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> <span data-ttu-id="ea4e6-131">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-131">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ea4e6-132">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-132">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ea4e6-134">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ea4e6-134">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- links -->  
[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "对比度级别（增强） AAA | W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "对比度 (级别 AA) 最低|W3C"  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
