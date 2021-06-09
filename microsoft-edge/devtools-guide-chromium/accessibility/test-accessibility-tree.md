---
description: 检查辅助功能树是否支持键盘和屏幕阅读器。
title: 检查辅助功能树是否支持键盘和屏幕阅读器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 0ab5e5609485505d1ad5fa6e2fffced9af25edcb
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597300"
---
# <a name="check-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a><span data-ttu-id="722dd-104">检查辅助功能树是否支持键盘和屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="722dd-104">Check the Accessibility Tree for keyboard and screen reader support</span></span>

<!-- Accessibility tab: Accessibility Tree -->

<span data-ttu-id="722dd-105">多个 DevTools 功能检查键盘和屏幕阅读器支持。</span><span class="sxs-lookup"><span data-stu-id="722dd-105">Several DevTools features check for keyboard and screen reader support.</span></span>  <span data-ttu-id="722dd-106">使用 **Inspect** 工具单独检查每个页面元素的辅助功能可能会相当耗时。</span><span class="sxs-lookup"><span data-stu-id="722dd-106">Using the **Inspect** tool to check the accessibility of each page element individually can become pretty time-consuming.</span></span>  <span data-ttu-id="722dd-107">检查网页的另一种方式是使用 **辅助功能树**。</span><span class="sxs-lookup"><span data-stu-id="722dd-107">An alternative way to check a webpage is to use the **Accessibility Tree**.</span></span>  <span data-ttu-id="722dd-108">辅助功能 **树** 指示页面向辅助技术（如屏幕阅读器）提供哪些信息。</span><span class="sxs-lookup"><span data-stu-id="722dd-108">The **Accessibility Tree** indicates what information the page provides to assistive technology such as screen readers.</span></span>

<span data-ttu-id="722dd-109">辅助功能 **树** 是 DOM 树的子集，其中包含 DOM 树中的元素，这些元素对于在屏幕阅读器中显示页面内容非常有用。</span><span class="sxs-lookup"><span data-stu-id="722dd-109">The **Accessibility Tree** is a subset of the DOM tree, which contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span></span>  <span data-ttu-id="722dd-110">辅助功能**树位于**"元素"工具\*\*\*\* 的"辅助功能"选项卡\*\*\*\* ("**样式**"选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="722dd-110">The **Accessibility Tree** is in the **Accessibility** tab of the **Elements** tool (near the **Styles** tab).</span></span>


<span data-ttu-id="722dd-111">若要浏览将辅助功能树与演示页面一同使用：</span><span class="sxs-lookup"><span data-stu-id="722dd-111">To explore using the Accessibility Tree with the demo page:</span></span>

1.  <span data-ttu-id="722dd-112">打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。 然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="722dd-112">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="722dd-113">选择\*\*\*\* DevTools (左上角的"检查 "\) 图标 \) 按钮，使按钮突出显示为蓝色 ![ ](../media/inspect-icon.msft.png) () 。</span><span class="sxs-lookup"><span data-stu-id="722dd-113">Select the **Inspect** \(![the Inspect icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="722dd-114">在呈现的网页的"捐赠 **"部分** ，将鼠标悬停在 **"100"** 按钮上。</span><span class="sxs-lookup"><span data-stu-id="722dd-114">In the rendered webpage, in the **Donation** section, hover over the **100** button.</span></span>  <span data-ttu-id="722dd-115">将显示 **"检查** "工具覆盖。</span><span class="sxs-lookup"><span data-stu-id="722dd-115">The **Inspect** tool overlay appears.</span></span>

1.  <span data-ttu-id="722dd-116">在呈现的网页中，选择 **"100"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="722dd-116">In the rendered webpage, select the **100** button.</span></span>  <span data-ttu-id="722dd-117">在 DevTools 中， **将显示"元素** "工具。</span><span class="sxs-lookup"><span data-stu-id="722dd-117">In DevTools, the **Elements** tool is displayed.</span></span>  <span data-ttu-id="722dd-118">DOM 树显示 `div` **100 按钮的元素** 。</span><span class="sxs-lookup"><span data-stu-id="722dd-118">The DOM tree shows the `div` element for the **100** button.</span></span>  <span data-ttu-id="722dd-119">" **样式** "窗格显示元素的 CSS 设置。</span><span class="sxs-lookup"><span data-stu-id="722dd-119">The **Styles** pane shows the CSS settings for the element.</span></span>

1.  <span data-ttu-id="722dd-120">在" **样式"选项卡** 的右侧，选择 **"辅助功能"** 选项卡。 将显示 **元素的** 辅助功能树，并展开。</span><span class="sxs-lookup"><span data-stu-id="722dd-120">To the right of the **Styles** tab, select the **Accessibility** tab.  The **Accessibility Tree** for the element is displayed, and is expanded.</span></span>

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="辅助功能树工具中的"资金"表单按钮" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    <span data-ttu-id="722dd-122">辅助功能树工具中的"资金"表单按钮</span><span class="sxs-lookup"><span data-stu-id="722dd-122">Donation form button in the Accessibility Tree tool</span></span>
:::image-end:::

<span data-ttu-id="722dd-123">树中没有名称或具有 (角色的任何元素（如 `generic` 元素) ）都是一个问题，因为该元素对键盘用户或正在使用辅助技术的用户不可用。 `div`</span><span class="sxs-lookup"><span data-stu-id="722dd-123">Any element in the tree that doesn't have a name, or has a role of `generic` (such as the `div` element) is a problem, because that element won't be available to keyboard users, or to users who are using assistive technology.</span></span>


## <a name="see-also"></a><span data-ttu-id="722dd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="722dd-124">See also</span></span>

*  [<span data-ttu-id="722dd-125">查看元素在辅助功能树中的位置</span><span class="sxs-lookup"><span data-stu-id="722dd-125">View the position of an element in the Accessibility Tree</span></span>][DevtoolsAccessibilityAccessibilityTabViewTree]
*  [<span data-ttu-id="722dd-126">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="722dd-126">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="722dd-127">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="722dd-127">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityAccessibilityTabViewTree]: accessibility-tab.md#view-the-position-of-an-element-in-the-accessibility-tree "使用&quot;辅助功能&quot;选项卡视图元素在&quot;辅助功能树 - 测试辅助功能&quot;|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
