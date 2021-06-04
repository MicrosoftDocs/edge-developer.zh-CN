---
description: Microsoft Edge 开发工具辅助功能的综合参考。
title: 辅助功能参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: a82dec6ffd7e3fb44143ea103fc9756afcd1a161
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564572"
---
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
# <a name="accessibility-reference"></a>辅助功能参考  

本页是 Microsoft Edge 开发工具辅助功能的综合参考。  适用于以下 web 开发人员：   

*   基本了解开发工具，例如如何打开它。  
*   熟悉[辅助功能原理和最佳做法][MDNAccessibility]。  
    
此参考的目的是帮助你发现开发工具中提供的所有工具，可帮助你检查页面的辅助功能。  

如果正在使用屏幕阅读器等辅助技术导航开发工具时寻求帮助，请导航至[使用辅助技术导航 Microsoft Edge 开发工具][DevtoolsAccessibilityNavigation]。  

## <a name="overview-of-accessibility-features-in-microsoft-edge-devtools"></a>Microsoft Edge 开发工具中的辅助功能概述  

本部分介绍了开发工具如何适应整个辅助功能工具包。  

确定页面是否可访问时，需要记住 2 个一般性问题：  

1.  是否可以使用键盘或[屏幕阅读器][MDNScreenReader]浏览页面？  
1.  页面的元素是否正确标记了屏幕阅读器？  
    
通常，开发工具应该可帮助你修复与问题 2 相关的错误，因为这些错误很容易以自动方式检测。  问题 1 同样重要，但遗憾的是，开发工具没有用。  查找问题 1 相关错误的唯一方法是尝试自己使用带有键盘或屏幕阅读器的页面。  <!--To learn more, navigate to [How To Do An Accessibility Review][AccessibilityReview].  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <a name="audit-the-accessibility-of-a-page"></a>审核页面的辅助功能  

> [!NOTE]
> **审核**工具提供指向第三方网站上托管的内容的链接。  Microsoft 不负责也不控制这些网站的内容，并且可能会收集任何数据。  

通常，使用审核窗格来确定是否：  

*   为屏幕阅读器正确标记了页面。  
*   页面上的文本元素具有足够的对比度。  导航到[查看颜色选取器中的文本元素的对比率](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)。  

审核页面：  

1.  导航到要审核的 URL。  
1.  在开发工具中，选择**审核**工具。  开发工具显示各种配置选项。  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="配置审核" lightbox="../media/accessibility-audits-pane.msft.png":::
       配置审核  
    :::image-end:::  
    
    > [!NOTE]
    > 此部分中屏幕截图取自 Microsoft Edge 版本 79。  可以在 `edge://version` 上查看正在运行的版本。  **审核**工具 UI 在早期版本的 Microsoft Edge 中看起来有所不同，但是一般的工作流程相同。  
    
1.  对于“**设备**”，如果要模拟移动设备，请选择“**移动设备**”。  此选项将更改用户代理字符串并调整视口的大小。  如果页面的移动版本显示方式与桌面版本不同，则此选项可能会显著影响审核结果。  
1.  在“**审核**”部分中，确保已启用“**辅助功能**”。  如果要从报告中排除其他类别，请禁用它们。  如果希望发现其他方法提高页面质量，请将其保持启用状态。  
1.  “**限制 **”部分可让你限制网络和 CPU，这在分析负载性能时非常有用。  此选项应该与辅助功能分数无关，因此可以使用自己喜欢的任何内容。  
1.  “**清除存储空间**”复选框可让你在加载页面之前清除所有存储，或在页面加载之间保留存储。  此选项还可能与辅助功能分数无关，因此可以使用自己喜欢的任何内容。  
1.  选择“**运行审核**”。 10 到 30 秒后，开发工具将提供一个报告。  你的报告为你提供有关如何提高页面辅助功能的各种提示。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="报告" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       报告  
    :::image-end:::  
    
1.  选择审核以了解更多信息。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="有关审核的更多详细信息" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       有关审核的更多详细信息  
    :::image-end:::  
    
1.  选择**了解更多信息**以查看该审核的文档。  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="查看审核文档" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       查看审核文档  
    :::image-end:::  
    
### <a name="see-also-axe-extension"></a>另请参阅：aXe 扩展  

你可能更喜欢使用 “[aXe 扩展][ChromeWebStoreAxe]”而不是“**审核**”工具。  
aXe 扩展通常提供相同的信息，因为它是支持审核窗格的基础引擎。  aXe 扩展具有不同的 UI，并且对审核的描述略有不同。  
ax 扩展相对于“**审核**”工具的一个优势是，可以检查并突出显示出现故障的节点。  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="aXe 扩展" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   aXe 扩展  
:::image-end:::  

## <a name="the-accessibility-panel"></a>辅助功能窗格  

在“**辅助功能**”窗格上，可以查看 DOM 节点的辅助功能树、ARIA 属性和计算出的辅助功能属性。  

打开**辅助功能**窗格：  

1.  选择“**元素**”工具。  
1.  在 **DOM 树**中，选择要检查的元素。  
1.  选择**辅助功能**窗格。  此窗格可能隐藏在**更多 选项卡** \(![更多 选项卡](../media/more-tabs-icon.msft.png)\) 按钮后面。  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="在辅助功能窗格中检查开发工具主页的 h1 元素。" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   在“**辅助功能**”窗格中检查开发工具主页的 `h1` 元素。  
:::image-end:::  

### <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a>查看元素在辅助功能树中的位置  

[辅助功能树][MDNAccessibilityTree]是 DOM 树的子集。  它仅包含 DOM 树中的元素，这些元素对于在屏幕阅读器中显示页面内容非常有用。  

从“[辅助功能](#the-accessibility-panel)“窗格检查元素辅助功能树中的元素位置。  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="辅助功能树部分" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   **辅助功能树**部分  
:::image-end:::  

### <a name="view-the-aria-attributes-of-an-element"></a>查看元素的 ARIA 属性  

ARIA 属性可确保屏幕阅读器拥有正确显示页面内容需要的所有信息。  

在[辅助功能](#the-accessibility-panel)窗格中查看元素的 ARIA 属性。  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="ARIA 属性部分" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   **ARIA 属性**部分  
:::image-end:::  

### <a name="view-the-computed-accessibility-properties-of-an-element"></a>查看元素的计算出的属性  

> [!NOTE]
> 如果要查找计算出的 CSS 属性，请导航到“[计算][DevtoolsCssReferenceViewActuallyAppliedElements]”窗格。  

部分辅助功能属性由浏览器动态计算。  这些属性显示在“**辅助功能 **”窗格的“**计算出的属性**”部分中。  

查看“[辅助功能](#the-accessibility-panel)”窗格中元素的计算出的属性。  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="辅助功能窗格计算属性部分" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   “**辅助功能**”窗格的“**计算出的属性**”部分  
:::image-end:::  

## <a name="view-the-contrast-ratio-of-a-text-element-in-the-color-picker"></a>查看颜色选取器中的文本元素的对比率  

部分弱视用户看不到非常明亮或非常暗的区域。  所有内容通常以相同的亮度显示，从而难以区分轮廓和边缘。  

对比率测量文本的前景和背景的亮度差。  如果您的文本的对比度低，那么这些弱视用户可能会以空白屏幕的形式实际体验网站。  

颜色选取器可帮助你验证文本是否满足建议的对比率级别：  

1.  选择“**元素**”工具。  
1.  在 **DOM 树**中，选择要检查的文本元素。  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="检查 DOM 树中的段落" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       检查 **DOM 树**中的段落  
    :::image-end:::  
    
1.  在“**样式**”窗格中，选择元素 `color` 值旁边的彩色方块。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="元素的颜色属性" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       元素的 `color` 属性  
    :::image-end:::  
    
1.  检查“颜色选取器”中的“**对比率**”部分。  一个选中标记表示元素满足[最低建议][W3CContrastMinimum]。  一个选中标记表示元素满足[增强建议][W3CContrastEnhanced]。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="颜色选取器中的“对比率”部分显示 2 个选中标记和值 13.97" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       颜色选取器中的“**对比率**”部分显示 2 个选中标记和值 `13.97`  
    :::image-end:::  
    
1.  有关详细信息，请选择“**对比率**”部分。  颜色选取器顶部的可视化选取器中将出现一行。  如果当前颜色符合建议，则该行的同一侧任何内容也符合建议。  如果当前颜色不满足建议，则同一侧的颜色也不符合建议。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="可视选取器中的对比率行" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       可视选取器中的**对比率**行  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "使用辅助技术导航 Microsoft Edge 开发工具 | Microsoft Docs"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "仅查看实际应用于元素的 CSS - CSS 参考 | Microsoft Docs"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe - Web 辅助功能测试 - Chrome Web Store"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "辅助功能树 (AOM) | MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "辅助功能 | MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "屏幕阅读器 | MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "对比度级别（增强） AAA | W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "对比度级别（最低） AA | W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
