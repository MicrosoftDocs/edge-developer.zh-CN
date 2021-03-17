---
description: Microsoft Edge DevTools 中的辅助功能的全面参考。
title: 辅助功能参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: fce6dec3883cbcc758780a9fedb4c0fb2a8d0a4c
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439252"
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

此页面全面引用了 Microsoft Edge DevTools 中的辅助功能。  它适用于 Web 开发人员，他们：  

*   基本了解 DevTools，例如如何打开它。  
*   熟悉 [辅助功能原则和最佳做法][MDNAccessibility]。  
    
此参考的目的是帮助你发现 DevTools 中提供的所有工具，这些工具可帮助你检查页面的辅助功能。  

如果你正在寻找有关使用屏幕阅读器等辅助技术导航 DevTools 的帮助，请导航到使用辅助技术导航 [Microsoft Edge DevTools][DevtoolsAccessibilityNavigation]。  

## <a name="overview-of-accessibility-features-in-microsoft-edge-devtools"></a>Microsoft Edge DevTools 中的辅助功能概述  

本部分介绍了 DevTools 如何适应整个辅助功能工具包。  

在确定页面是否可访问时，您需要记住两个一般问题：  

1.  你能否使用键盘或屏幕阅读器导航 [页面][MDNScreenReader]？  
1.  页面元素是否针对屏幕阅读器正确标记？  
    
通常，DevTools 应该可帮助你修复与问题#2相关的错误，因为这些错误很容易以自动方式检测。  问题#1一样重要，但遗憾的是，DevTools 没有帮助。  查找与问题相关的错误的唯一#1是尝试使用具有键盘或屏幕阅读器的页面。  <!--To learn more, navigate to [How To Do An Accessibility Review][AccessibilityReview].  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <a name="audit-the-accessibility-of-a-page"></a>审核页面的辅助功能  

> [!NOTE]
> **审核工具**提供指向第三方网站上承载的内容的链接。  Microsoft 不负责也不控制这些网站的内容以及可能收集的任何数据。  

通常，使用审核面板来确定：  

*   为屏幕阅读器正确标记了页面。  
*   页面上的文本元素具有足够的对比率。  导航 [到查看颜色选取器中文本元素的对比率](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)。  

审核页面：  

1.  导航到要审核的 URL。  
1.  在 DevTools 中，选择 **"审核"** 工具。  DevTools 显示各种配置选项。  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="配置审核" lightbox="../media/accessibility-audits-pane.msft.png":::
       配置审核  
    :::image-end:::  
    
    > [!NOTE]
    > 本部分中的屏幕截图是 Microsoft Edge 版本 79 的屏幕截图。  你可以检查运行的版本 `edge://version` 。  在 **早期版本** 的 Microsoft Edge 中，审核工具 UI 看起来有所不同，但常规工作流是相同的。  
    
1.  对于 **"** 设备 **"，** 如果要模拟移动设备，请选择"移动"。  此选项将更改用户代理字符串并调整视口的大小。  如果页面的移动版本显示方式与桌面版本不同，则此选项可能会显著影响审核结果。  
1.  在 **"审核"** 部分，确保 **已启用** 辅助功能。  如果要从报告中排除其他类别，请禁用这些类别。  如果希望发现其他方法提高页面质量，请将其保持启用状态。  
1.  限制 **部分允许您** 限制网络和 CPU，这在分析负载性能时很有用。  此选项应该与辅助功能分数无关，因此可以使用你喜欢的任何内容。  
1.  " **清除存储** "复选框允许你在加载页面之前清除所有存储，或在页面加载之间保留存储。  此选项也可能与你的辅助功能分数无关，因此你可以使用你喜欢的任何内容。  
1.  选择 **"运行审核"。** 10 到 30 秒后，DevTools 将提供一个报告。  你的报告为你提供了有关如何改进页面辅助功能的各种提示。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="报告" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       报告  
    :::image-end:::  
    
1.  选择审核以了解其更多信息。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="有关审核详细信息" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       有关审核详细信息  
    :::image-end:::  
    
1.  选择 **"了解** 更多"以查看该审核的文档。  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="查看审核文档" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       查看审核文档  
    :::image-end:::  
    
### <a name="see-also-axe-extension"></a>另请参阅：aXe 扩展  

你可能更喜欢使用 [aXe 扩展][ChromeWebStoreAxe] ，而不是 **审核** 工具。  
aXe 扩展通常提供相同的信息，因为它是支持审核面板的基础引擎。  aXe 扩展具有不同的 UI，并且对审核描述略有不同。  
aXe 扩展具有的一个优势是****，它使您能够检查和突出显示失败节点。  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="aXe 扩展" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   aXe 扩展  
:::image-end:::  

## <a name="the-accessibility-panel"></a>辅助功能面板  

辅助功能 **面板** 是查看 DOM 节点的辅助功能树、ARIA 属性和计算辅助功能属性的地方。  

打开 **辅助功能面板** ：  

1.  选择" **元素"** 工具。  
1.  在 **DOM 树中**，选择要检查的元素。  
1.  选择 **"辅助功能"** 面板。  此面板可能隐藏在更多 **选项卡** \ (![ 选项卡 ](../media/more-tabs-icon.msft.png) \) 按钮后面。  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="在辅助功能面板中检查 DevTools 主页的 h1 元素" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   检查 `h1` 辅助功能面板中的 DevTools **主页** 元素  
:::image-end:::  

### <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a>查看元素在辅助功能树中的位置  

辅助功能 [树是][MDNAccessibilityTree] DOM 树的子集。  它仅包含 DOM 树中的元素，这些元素对于在屏幕阅读器中显示页面内容非常有用。  

从辅助功能面板检查元素在辅助功能树 [中](#the-accessibility-panel) 的位置。  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text=""辅助功能树"部分" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   " **辅助功能树"** 部分  
:::image-end:::  

### <a name="view-the-aria-attributes-of-an-element"></a>查看元素的 ARIA 属性  

ARIA 属性确保屏幕阅读器具有为了正确表示页面内容而需要的所有信息。  

在辅助功能面板中查看元素 [的](#the-accessibility-panel) ARIA 属性。  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="ARIA 属性部分" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   ARIA **属性** 部分  
:::image-end:::  

### <a name="view-the-computed-accessibility-properties-of-an-element"></a>查看元素的计算辅助功能属性  

> [!NOTE]
> 如果要查找已计算的 CSS 属性，请导航到 ["计算"][DevtoolsCssReferenceViewActuallyAppliedElements] 面板。  

一些辅助功能属性由浏览器动态计算。  这些属性显示在辅助功能面板 **的"计算** 属性 **"** 部分。  

在辅助功能面板中查看元素的计算 [辅助功能](#the-accessibility-panel) 属性。  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="辅助功能面板的"计算属性"部分" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   辅助功能 **面板** 的" **计算属性"** 部分  
:::image-end:::  

## <a name="view-the-contrast-ratio-of-a-text-element-in-the-color-picker"></a>查看颜色选取器中文本元素的对比率  

一些低视力用户不会将区域视为非常亮或非常暗的区域。  所有内容通常以相同的亮度显示，这使得难以区分轮廓和边缘。  

对比率测量文本的前景和背景的亮度差异。  如果你的文本的对比度比率较低，那么这些低视力用户实际上可能会将你的网站体验为空白屏幕。  

颜色选取器可帮助你验证文本是否满足建议的对比率级别：  

1.  选择" **元素"** 工具。  
1.  在 **DOM 树中**，选择要检查的文本元素。  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="检查 DOM 树中的段落" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       检查 **DOM 树中的段落**  
    :::image-end:::  
    
1.  在 **"样式** "面板中，选择元素值旁边的 `color` 颜色正方形。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="元素的颜色属性" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       `color`元素的属性  
    :::image-end:::  
    
1.  检查 **颜色选取器** 中的"对比率"部分。  一个选中标记表示元素满足最低 [建议][W3CContrastMinimum]。  两个选中标记表示它符合增强 [的建议][W3CContrastEnhanced]。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="颜色选取器中的"对比率"部分显示 2 个选中标记和值 13.97" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       颜色 **选取器** 中的"对比率"部分显示 2 个选中标记和一个值 `13.97`  
    :::image-end:::  
    
1.  有关详细信息，请选择"对 **比率"** 部分。  颜色选取器顶部的可视化选取器中将出现一行。  如果当前颜色符合建议，则该行的同一侧任何内容也符合建议。  如果当前颜色不满足建议，则同一侧的颜色也不满足建议。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="可视选取器中的对比率线" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       可视 **选取器** 中的对比率线  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "使用辅助技术工具导航 Microsoft Edge |Microsoft Docs"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "仅查看实际应用于元素的 CSS - CSS 参考|Microsoft Docs"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe - Web 辅助功能测试 - Chrome Web Store"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "AOM (辅助功能) |MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "辅助功能|MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "屏幕阅读器|MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "增强 (AAA 级别的) 对比度|W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "对比度 (级别 AA) 最低|W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
