---
description: 分析边栏菜单中缺少键盘焦点指示，因为链接上的焦点状态缺少 CSS 伪类规则，再加上该链接没有大纲设置。
title: 分析边栏菜单中键盘焦点的缺失
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3626de9bdc2cce266efafe4b1b2e8fff501a74f7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597299"
---
# <a name="analyze-the-lack-of-indication-of-keyboard-focus-in-a-sidebar-menu"></a><span data-ttu-id="f3753-104">分析边栏菜单中键盘焦点的缺失</span><span class="sxs-lookup"><span data-stu-id="f3753-104">Analyze the lack of indication of keyboard focus in a sidebar menu</span></span>

<!-- Inspect tool, and CSS rules: pseudo-classes for states -->

<span data-ttu-id="f3753-105">在辅助功能测试演示页中，使用键盘时，包含蓝色链接的边栏导航菜单不会直观地指示哪个链接具有焦点。</span><span class="sxs-lookup"><span data-stu-id="f3753-105">In the accessibility-testing demo page, the sidebar navigation menu with blue links doesn't visually indicate which link has focus, when using a keyboard.</span></span>  <span data-ttu-id="f3753-106">为了找出为什么边栏菜单使键盘用户感到困惑，我们将查找适用于 和 状态的 CSS 伪类规则，以及链接大纲的 `hover` `focus` CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="f3753-106">To find out why the sidebar menu is confusing to keyboard users, we'll look for CSS pseudo-class rules for the `hover` and `focus` states, along with the CSS property for link outlines.</span></span>  

<span data-ttu-id="f3753-107">此分析发现边栏导航菜单的链接中缺少键盘焦点指示的原因是：</span><span class="sxs-lookup"><span data-stu-id="f3753-107">This analysis finds that the lack of indication of keyboard focus in the links of the sidebar navigation menu is because:</span></span>
*  <span data-ttu-id="f3753-108">链接 `a` 的 CSS 属性设置为 `outline: none` 。</span><span class="sxs-lookup"><span data-stu-id="f3753-108">The `a` links have a CSS property setting of `outline: none`.</span></span>
*  <span data-ttu-id="f3753-109">这些 `a` 链接缺少状态 CSS 伪类 `:focus` 规则。</span><span class="sxs-lookup"><span data-stu-id="f3753-109">The `a` links lack a CSS pseudo-class rule for the `:focus` state.</span></span>

<span data-ttu-id="f3753-110">若要导航到 CSS，我们将使用 **Inspect** 工具突出显示边栏导航菜单上的蓝色链接，然后查看定义该链接的元素的 DOM 树和 `a` CSS。</span><span class="sxs-lookup"><span data-stu-id="f3753-110">To navigate to the CSS, we'll use the **Inspect** tool to highlight a blue link on the sidebar navigation menu, and then view the DOM tree and CSS for the `a` element that defines that link.</span></span>

1.  <span data-ttu-id="f3753-111">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f3753-111">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="f3753-112">选择\*\*\*\* DevTools 左上角的"检查 \ (检查图标 \) "按钮，以便该按钮突出显示为 (![ ](../media/inspect-icon.msft.png) 蓝色) 。</span><span class="sxs-lookup"><span data-stu-id="f3753-112">Select the **Inspect** \(![Inspect icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="f3753-113">将鼠标悬停在边栏导航菜单中的蓝色 **"猫** "链接上。</span><span class="sxs-lookup"><span data-stu-id="f3753-113">Hover over the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="f3753-114">将显示 Inspect 覆盖层，显示 `a` 元素是可键盘聚焦的。</span><span class="sxs-lookup"><span data-stu-id="f3753-114">The Inspect overlay appears, showing that the `a` element is keyboard-focusable.</span></span>  <span data-ttu-id="f3753-115">但是覆盖层不会显示当链接具有焦点时没有视觉指示。</span><span class="sxs-lookup"><span data-stu-id="f3753-115">But the overlay doesn't show that there's no visual indication when the link has focus.</span></span>

    <span data-ttu-id="f3753-116">接下来，我们将检查此链接的 CSS 样式。</span><span class="sxs-lookup"><span data-stu-id="f3753-116">Next, we'll inspect the CSS styling of this link.</span></span>
 
1.  <span data-ttu-id="f3753-117">选择边栏导航菜单中的 **"猫** "链接。</span><span class="sxs-lookup"><span data-stu-id="f3753-117">Select the **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="f3753-118">检查 **工具** 将关闭， **并且元素** 工具将打开，突出显示 `a` DOM 树中的节点。</span><span class="sxs-lookup"><span data-stu-id="f3753-118">The **Inspect** tool turns off, and the **Elements** tool opens, highlighting the `a` node in the DOM tree.</span></span>

1.  <span data-ttu-id="f3753-119">选择" **样式"** 选项卡。 将显示 CSS `#sidebar nav li a` 规则，以及指向 中行号的链接 `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="f3753-119">Select the **Styles** tab.  The CSS rule `#sidebar nav li a` appears, along with a link to a line number in `styles.css`.</span></span>

    :::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="检查菜单中的链接的源代码和应用样式" lightbox="../media/a11y-testing-menu-link.msft.png":::
        <span data-ttu-id="f3753-121">检查菜单中的链接的源代码和应用样式</span><span class="sxs-lookup"><span data-stu-id="f3753-121">Inspecting the source code and the applied styles of a link in the menu</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="f3753-122">选择 CSS 文件的链接。</span><span class="sxs-lookup"><span data-stu-id="f3753-122">Select the link to the CSS file.</span></span>  <span data-ttu-id="f3753-123">CSS 文件将在"源" **工具中** 打开。</span><span class="sxs-lookup"><span data-stu-id="f3753-123">The CSS file opens within the **Sources** tool.</span></span>

    :::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="应用于"源"工具中链接的样式" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
        <span data-ttu-id="f3753-125">应用于"源"工具中链接的样式</span><span class="sxs-lookup"><span data-stu-id="f3753-125">The styles applied to the link in the Sources tool</span></span>
    :::image-end:::
    
<span data-ttu-id="f3753-126">页面样式具有 CSS 伪类规则，用于指示在使用鼠标时位于哪个 `hover` 菜单项上 `#sidebar nav li a:hover` ：。</span><span class="sxs-lookup"><span data-stu-id="f3753-126">The styles of the page have a CSS pseudo-class rule for the `hover` state that indicates which menu item you are on when you use a mouse: `#sidebar nav li a:hover`.</span></span>  <span data-ttu-id="f3753-127">但是，没有 CSS 伪类规则，该状态在使用键盘时直观地指示您位于哪个菜单项上， `focus` 例如 `#sidebar nav li a:focus` 。</span><span class="sxs-lookup"><span data-stu-id="f3753-127">However, there is no CSS pseudo-class rule for the `focus` state to visually indicate which menu item you are on when you use a keyboard, such as `#sidebar nav li a:focus`.</span></span>

<span data-ttu-id="f3753-128">此外，请注意链接的 CSS 属性设置为 `outline: none` 。</span><span class="sxs-lookup"><span data-stu-id="f3753-128">Also, notice that the links have a CSS property setting of `outline: none`.</span></span>  <span data-ttu-id="f3753-129">这是一种常见做法，当你使用键盘关注元素时，删除浏览器自动添加到元素的大纲。</span><span class="sxs-lookup"><span data-stu-id="f3753-129">This is a common practice, to remove the outline which browsers automatically add to elements when you focus on them using a keyboard.</span></span>  <span data-ttu-id="f3753-130">不使用 `focus` 样式设置会导致用户混淆。</span><span class="sxs-lookup"><span data-stu-id="f3753-130">Not using `focus` styling causes confusion for your users.</span></span>


## <a name="see-also"></a><span data-ttu-id="f3753-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3753-131">See also</span></span> 

*  [<span data-ttu-id="f3753-132">跟踪哪些元素有焦点</span><span class="sxs-lookup"><span data-stu-id="f3753-132">Track which element has focus</span></span>](focus.md)
*  [<span data-ttu-id="f3753-133">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="f3753-133">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f3753-134">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="f3753-134">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
