---
description: 使用"辅助功能"选项卡测试辅助功能。
title: 使用"辅助功能"选项卡测试辅助功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 839feed56fc82af2b4d96a081c476696166075b9
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597321"
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
# <a name="test-accessibility-using-the-accessibility-tab"></a><span data-ttu-id="d5b30-104">使用"辅助功能"选项卡测试辅助功能</span><span class="sxs-lookup"><span data-stu-id="d5b30-104">Test accessibility using the Accessibility tab</span></span>

<span data-ttu-id="d5b30-105">" **辅助功能"** 选项卡是查看 DOM 节点的辅助功能树、ARIA 属性和计算辅助功能属性的地方。</span><span class="sxs-lookup"><span data-stu-id="d5b30-105">The **Accessibility** tab is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span></span>  

<span data-ttu-id="d5b30-106">若要打开 **"辅助功能"选项卡** ：</span><span class="sxs-lookup"><span data-stu-id="d5b30-106">To open the **Accessibility** tab:</span></span>

1.  <span data-ttu-id="d5b30-107">选择" **元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="d5b30-107">Select the **Elements** tool.</span></span>  
1.  <span data-ttu-id="d5b30-108">在 **DOM 树**中，选择要检查的元素。</span><span class="sxs-lookup"><span data-stu-id="d5b30-108">In the **DOM Tree**, select the element which you want to inspect.</span></span>  
1.  <span data-ttu-id="d5b30-109">选择 **"辅助功能"** 选项卡。 你可能需要先选择"更多选项卡\*\*\*\*"\ ("样式"选项卡) "更多选项卡"按钮 ![ ](../media/more-tabs-icon.msft.png) \) **按钮**。</span><span class="sxs-lookup"><span data-stu-id="d5b30-109">Select the **Accessibility** tab.  You might need to first select the **More tabs** \(![the More tabs button](../media/more-tabs-icon.msft.png)\) button to the right of the **Styles** tab.</span></span>

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="检查"辅助功能"选项卡中的 DevTools 主页的 h1 元素" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   <span data-ttu-id="d5b30-111">检查 `h1` "辅助功能"选项卡中的 DevTools **主页** 元素</span><span class="sxs-lookup"><span data-stu-id="d5b30-111">Inspect the `h1` element of the DevTools homepage in the **Accessibility** tab</span></span>
:::image-end:::  


## <a name="view-the-position-of-an-element-in-the-accessibility-tree"></a><span data-ttu-id="d5b30-112">查看元素在辅助功能树中的位置</span><span class="sxs-lookup"><span data-stu-id="d5b30-112">View the position of an element in the Accessibility Tree</span></span>

<span data-ttu-id="d5b30-113">[辅助功能树][MDNAccessibilityTree]是 DOM 树的子集。</span><span class="sxs-lookup"><span data-stu-id="d5b30-113">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span></span>  <span data-ttu-id="d5b30-114">辅助功能树仅包含 DOM 树中的元素，这些元素对于通过屏幕阅读器等辅助技术显示页面内容非常有用。</span><span class="sxs-lookup"><span data-stu-id="d5b30-114">The accessibility tree only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page through assistive technologies such as screen readers.</span></span>

<span data-ttu-id="d5b30-115">从"辅助功能"选项卡检查元素在辅助功能 **树中** 的位置。</span><span class="sxs-lookup"><span data-stu-id="d5b30-115">Inspect the position of an element in the accessibility tree from the **Accessibility** tab.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="辅助功能树部分" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   <span data-ttu-id="d5b30-117">**辅助功能树**部分</span><span class="sxs-lookup"><span data-stu-id="d5b30-117">The **Accessibility Tree** section</span></span>  
:::image-end:::  


## <a name="view-the-aria-attributes-of-an-element"></a><span data-ttu-id="d5b30-118">查看元素的 ARIA 属性</span><span class="sxs-lookup"><span data-stu-id="d5b30-118">View the ARIA attributes of an element</span></span>  

<span data-ttu-id="d5b30-119">ARIA 属性确保辅助技术（如屏幕阅读器）具有为了正确表示页面内容而需要的所有信息。</span><span class="sxs-lookup"><span data-stu-id="d5b30-119">ARIA attributes ensure that assistive technologies such as screen readers have all of the information that they need in order to properly represent the contents of a page.</span></span>  

<span data-ttu-id="d5b30-120">在"辅助功能"选项卡中查看元素 **的** ARIA 属性。</span><span class="sxs-lookup"><span data-stu-id="d5b30-120">View the ARIA attributes of an element in the **Accessibility** tab.</span></span>

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="ARIA 属性部分" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   <span data-ttu-id="d5b30-122">**ARIA 属性**部分</span><span class="sxs-lookup"><span data-stu-id="d5b30-122">The **ARIA Attributes** section</span></span>  
:::image-end:::  


## <a name="view-the-computed-accessibility-properties-of-an-element"></a><span data-ttu-id="d5b30-123">查看元素的计算出的属性</span><span class="sxs-lookup"><span data-stu-id="d5b30-123">View the computed accessibility properties of an element</span></span>  


<span data-ttu-id="d5b30-124">部分辅助功能属性由浏览器动态计算。</span><span class="sxs-lookup"><span data-stu-id="d5b30-124">Some accessibility properties are dynamically calculated by the browser.</span></span>  <span data-ttu-id="d5b30-125">这些属性显示在"辅助功能"选项卡\*\*\*\* 的"计算**属性"** 部分。</span><span class="sxs-lookup"><span data-stu-id="d5b30-125">These properties are displayed in the **Computed Properties** section of the **Accessibility** tab.</span></span>  

<span data-ttu-id="d5b30-126">在"辅助功能"选项卡中查看元素的计算 **辅助功能** 属性。</span><span class="sxs-lookup"><span data-stu-id="d5b30-126">View the computed accessibility properties of an element in the **Accessibility** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="d5b30-127">对于计算 CSS 属性，请使用" [计算"][DevtoolsCssReferenceViewActuallyAppliedElements] 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d5b30-127">For computed CSS properties, use the [Computed][DevtoolsCssReferenceViewActuallyAppliedElements] tab.</span></span>

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text=""辅助功能"选项卡的"计算属性"部分" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   <span data-ttu-id="d5b30-129">" **辅助功能"选项卡** 的" **计算属性"** 部分</span><span class="sxs-lookup"><span data-stu-id="d5b30-129">The **Computed Properties** section of the **Accessibility** tab</span></span>  
:::image-end:::  


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d5b30-130">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="d5b30-130">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> <span data-ttu-id="d5b30-131">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d5b30-131">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d5b30-132">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="d5b30-132">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="d5b30-134">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d5b30-134">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- links -->
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "仅查看实际应用于元素的 CSS - CSS 参考|Microsoft Docs"  
[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "辅助功能树 (AOM) | MDN"  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
