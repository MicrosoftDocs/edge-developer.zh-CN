---
description: Microsoft Edge DevTools 中的辅助功能的全面参考。
title: 辅助功能参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 39b0b8c36cea017b9976ea4e80e92ea93896a671
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993266"
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

# 辅助功能参考  

此页面是 Microsoft Edge DevTools 中辅助功能的完整参考。  它适用于以下情况的 web 开发人员：  

*   对 DevTools 有一个基本的理解，例如如何将其打开。  
*   熟悉 [辅助功能原则和最佳做法][MDNAccessibility]。  
    
本参考旨在帮助你发现 DevTools 中提供的所有工具，这些工具可帮助你检查页面的辅助功能。  

如果要查找有关使用辅助技术（如屏幕阅读器）导航 DevTools 的帮助，请参阅 [使用辅助技术导航 Microsoft Edge DevTools][DevtoolsAccessibilityNavigation] 。  

## Microsoft Edge DevTools 中辅助功能的概述  

本部分介绍 DevTools 如何融入你的整体辅助功能工具包。  

确定页面是否可访问时，需要考虑两个常见问题：  

1.  是否可以使用键盘或 [屏幕阅读器][MDNScreenReader]导航页面？  
1.  页面元素是否已正确标记为屏幕阅读器？  
    
通常，DevTools 应帮助你修复与 #2 问题相关的错误，因为这些错误非常容易以自动方式进行检测。  问题 #1 同样重要，但很遗憾，DevTools 不会对您有所帮助。  查找与问题相关的错误的唯一方式 #1 是尝试自己在页面上使用键盘或屏幕阅读器。  <!--See [How To Do An Accessibility Review][AccessibilityReview] to learn more.  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## 审核页面的辅助功能  

> [!NOTE]
> " **审核** " 面板提供了指向第三方网站上托管的内容的链接。  Microsoft 不承担任何责任，也不能控制这些网站的内容和可能收集的任何数据。  

一般情况下，使用 "审核" 面板确定是否：  

*   已正确标记屏幕阅读器的页面。  
*   页面上的文本元素具有足够的对比度比率。  请参阅 [查看颜色选取器中的文本元素的对比度](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker)。  

若要审核页面，请执行以下操作：  

1.  转到要审核的 URL。  
1.  在 DevTools 中，单击 " **审核** " 选项卡。 DevTools 显示了各种配置选项。  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="配置审核" lightbox="../media/accessibility-audits-pane.msft.png":::
       配置审核  
    :::image-end:::  
    
    > [!NOTE]
    > 本部分中的屏幕截图是使用版本79的 Microsoft Edge 所得到的。  你可以检查你正在运行的版本 `edge://version` 。  " **审核** " 面板 UI 在早期版本的 Microsoft Edge 中看起来有所不同，但常规工作流是相同的。  
    
1.  对于 " **设备**"，如果要模拟移动设备，请选择 " **移动** "。  此选项将更改你的用户代理字符串并调整视区的大小。  如果页面的移动版本显示不同于桌面版本，此选项可能会对审核结果产生显著影响。  
1.  在 " **审核** " 部分中，确保已启用 **辅助功能** 。  如果要从报表中排除其他类别，请禁用其他类别。  如果想要发现提高页面质量的其他方法，请将其保留为启用状态。  
1.  **限制**部分允许你阻止网络和 CPU，这在分析负载性能时非常有用。  此选项应与你的辅助功能分数无关，因此你可以使用你喜欢的任何内容。  
1.  " **清除存储** " 复选框允许你在加载页面之前清除所有存储空间，或在页面加载之间保留存储。  此选项也可能与你的辅助功能分数不相关，因此你可以使用你喜欢的任何内容。  
1.  单击 " **运行审核**"。 10到30秒后，DevTools 将提供一个报表。  你的报表提供了有关如何改进页面辅助功能的各种提示。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="报表" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       报表  
    :::image-end:::  
    
1.  单击审核以了解详细信息。  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="有关审核的详细信息" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       有关审核的详细信息  
    :::image-end:::  
    
1.  单击 " **了解详细信息** " 以查看该审核的文档。  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="查看审核文档" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       查看审核文档  
    :::image-end:::  
    
### 另请参阅： aXe 扩展名  

您可能希望使用 [aXe 扩展][ChromeWebStoreAxe] ，而不是 " **审核** " 面板。  
AXe 扩展通常提供相同的信息，因为它是为 "审核" 面板加电的基础引擎。  AXe 扩展具有不同的 UI，并以略微不同的方式描述审核。  
AXe 扩展在 " **审核** " 面板上的一个优点是，它使您能够检查和突出显示失败的节点。  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="AXe 扩展" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   AXe 扩展  
:::image-end:::  

## 辅助功能窗格  

在 " **辅助功能** " 窗格中，你可以查看 DOM 节点的辅助功能树、ARIA 属性和计算的辅助功能属性。  

打开 " **辅助功能** " 窗格：  

1.  单击 " **元素** " 选项卡。  
1.  在 **DOM 树**中，选择要检查的元素。  
1.  单击 " **辅助功能** " 选项卡。 此选项卡可能隐藏在 " **更多选项卡** \ (![ 更多选项卡 ][ImageMoreTabsIcon] \ ) " 按钮之后。  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="在 "辅助功能" 窗格中检查 DevTools 主页的 h1 元素" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   `h1`在 "**辅助功能**" 窗格中检查 DevTools 主页的元素  
:::image-end:::  

### 查看辅助功能树中元素的位置  

[辅助功能树][MDNAccessibilityTree]是 DOM 树的子集。  它仅包含 DOM 树中的元素，这些元素适用于在屏幕阅读器中显示页面的内容。  

在 "辅助 [功能" 窗格](#the-accessibility-pane)的 "辅助功能" 树中检查元素的位置。  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="辅助功能树部分" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   **辅助功能树**部分  
:::image-end:::  

### 查看元素的 ARIA 属性  

ARIA 属性确保屏幕阅读器具有它们所需的所有信息，以便正确地表示页面的内容。  

在 " [辅助功能" 窗格](#the-accessibility-pane)中查看元素的 ARIA 属性。  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="ARIA 属性部分" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   **ARIA 属性**部分  
:::image-end:::  

### 查看元素的计算辅助功能属性  

> [!NOTE]
> 如果要查找计算的 CSS 属性，请参阅 " [计算" 选项卡][DevtoolsCssReferenceViewActuallyAppliedElements]。  

某些辅助功能属性是由浏览器动态计算的。  这些属性显示在 "**辅助功能**" 窗格的 "**计算属性**" 部分中。  

在 " [辅助功能" 窗格](#the-accessibility-pane)中查看元素的计算辅助功能属性。  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text=""辅助功能" 窗格的 "计算属性" 部分" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   "**辅助功能**" 窗格的 "**计算属性**" 部分  
:::image-end:::  

## 查看颜色选取器中的文本元素的对比度比率  

某些视力较差的人看不到非常明亮或非常暗的区域。  所有内容往往都看起来几乎相同，这使区分轮廓和边缘变得很困难。  

对比度比率测量文本前景和背景之间的亮度差异。  如果文本的对比度较低，则这些视力较差的用户可能会以空白屏幕的形式体验您的网站。  

颜色选取器可帮助你验证文本是否满足建议的对比度比率：  

1.  单击 " **元素** " 选项卡。  
1.  在 **DOM 树**中，选择要检查的文本元素。  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="检查 DOM 树中的段落" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       检查**DOM 树**中的段落  
    :::image-end:::  
    
1.  在 " **样式** " 窗格中，单击元素值旁边的颜色方块 `color` 。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="元素的 color 属性" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       `color`元素的属性  
    :::image-end:::  
    
1.  检查拾色器的 " **对比度比率** " 部分。  一个复选标记表示该元素满足 [最低建议][W3CContrastMinimum]。  两个复选标记表示它符合 [增强的建议][W3CContrastEnhanced]。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="颜色选取器的 "对比度比率" 部分显示2个复选标记和值13.97。" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       颜色选取器的 " **对比度比率** " 部分显示2个复选标记，值为 `13.97`  
    :::image-end:::  
    
1.  单击 " **对比度比率** " 部分可查看详细信息。  可视选取器中的颜色选取器顶部会显示一条线。  如果当前颜色满足建议，则行的同一侧的任何内容也满足建议。  如果当前颜色不符合建议，则同一侧的任何内容也不能满足建议。  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="可视选取器中的 "对比度" 比率线" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       可视选取器中的 " **对比度" 比率** 线  
    :::image-end:::  
    
<!--## Feedback   -->  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "导航 Microsoft Edge DevTools 与辅助技术 |Microsoft 文档"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "仅查看实际应用到元素 CSS 引用的 CSS |Microsoft 文档"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe-Web 辅助功能测试-Chrome Web Store"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "辅助功能树 (AOM) |MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "辅助功能 |MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "屏幕阅读器 |MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "对比度 (增强) 级 AAA |W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "对比度 (最低) 级别 AA |W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
