---
description: 使用呈现工具中的模拟 CSS 媒体功能首选 (减少运动下拉列表) 关闭 UI 动画，检查网页是否可用。
title: 验证页面是否可用，同时关闭 UI 动画
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: ec30925b706b4b1c6dfaaa6ce66a38fab8759ac2
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597252"
---
# <a name="verify-that-the-page-is-usable-with-ui-animation-turned-off"></a><span data-ttu-id="c5971-104">验证页面是否可用，同时关闭 UI 动画</span><span class="sxs-lookup"><span data-stu-id="c5971-104">Verify that the page is usable with UI animation turned off</span></span>

<span data-ttu-id="c5971-105">网页不应向在操作系统中关闭动画的用户显示动画。</span><span class="sxs-lookup"><span data-stu-id="c5971-105">A webpage should not show animations to a user who turned off animations in the operating system.</span></span>  <span data-ttu-id="c5971-106">动画可以帮助产品的可用性，但它们也会导致干扰、混淆或混乱。</span><span class="sxs-lookup"><span data-stu-id="c5971-106">Animations can help the usability of a product, but they can also cause distraction, confusion, or nausea.</span></span>

<span data-ttu-id="c5971-107">若要检查网页是否可使用 UI 动画关闭 (运动) ，在呈现工具中，使用**模拟 CSS**媒体\*\*\*\* 功能首选减少运动下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c5971-107">To check that a webpage is usable with UI animation turned off (reduced motion), in the **Rendering** tool, use the **Emulate CSS media feature prefers-reduced-motion** dropdown list.</span></span>

<span data-ttu-id="c5971-108">在辅助功能测试演示网页中，关闭操作系统中的动画或使用 DevTools 模拟该设置时，当您选择边栏导航菜单的链接时，网页不会使用平滑滚动。</span><span class="sxs-lookup"><span data-stu-id="c5971-108">In the accessibility-testing demo webpage, when you turn off animations in the operating system, or emulate that settings by using DevTools, the webpage doesn't use smooth scrolling when you select the links of the sidebar navigation menu.</span></span>  <span data-ttu-id="c5971-109">这是通过以下方法实现的：在媒体查询中将平滑滚动设置包装在 CSS 中，然后使用 **呈现** 工具模拟操作系统设置，以减小动画效果。</span><span class="sxs-lookup"><span data-stu-id="c5971-109">This is achieved by wrapping the smooth-scrolling setting in CSS in a media query, and then using the **Rendering** tool to emulate the operating system setting for reduced animation.</span></span>

<span data-ttu-id="c5971-110">若要检查页面是否可用，请关闭动画：</span><span class="sxs-lookup"><span data-stu-id="c5971-110">To check whether the page is usable with animations turned off:</span></span>

1.  <span data-ttu-id="c5971-111">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="c5971-111">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="c5971-112">在 DevTools 顶部，选择"\*\*\*\* 源"工具，然后在左侧的\*\*\*\*"导航"窗格中，选择 `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="c5971-112">At the top of DevTools, select the **Sources** tool, and then in the **Navigation** pane on the left, select `styles.css`.</span></span>  <span data-ttu-id="c5971-113">CSS 文件显示在"编辑器 **"** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="c5971-113">The CSS file appears in the **Editor** pane.</span></span>

1.  <span data-ttu-id="c5971-114">选择 macOS 上的 Windows/Linux 或**Command+F 上的 Ctrl+F，** 然后输入\*\*\*\* `@media` 。</span><span class="sxs-lookup"><span data-stu-id="c5971-114">Select **Ctrl+F** on Windows/Linux or **Command+F** on macOS, and then enter `@media`.</span></span>  <span data-ttu-id="c5971-115">将显示以下 CSS 媒体查询，确认它在网页上使用。</span><span class="sxs-lookup"><span data-stu-id="c5971-115">The following CSS media query is displayed, which confirms that it is used on the webpage.</span></span>

    ```css
    @media (prefers-reduced-motion: no-preference) {
      html {
        scroll-behavior: smooth;
      }
    }
    ```

    <span data-ttu-id="c5971-116">接下来，模拟操作系统设置以减少动画，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5971-116">Next, emulate the operating system setting to reduce animation, as follows.</span></span>

1.  <span data-ttu-id="c5971-117">选择 **Esc** 打开 DevTools 底部的"箱"。</span><span class="sxs-lookup"><span data-stu-id="c5971-117">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="c5971-118">Select the **More tools** () button at the top of the Drawer to see the list **+** of tools， and then select **Rendering**.</span><span class="sxs-lookup"><span data-stu-id="c5971-118">Select the **More tools** (**+**) button at the top of the Drawer to see the list of tools, and then select **Rendering**.</span></span>  

1.  <span data-ttu-id="c5971-119">在"**模拟 CSS 媒体功能首选-减少运动**"下拉列表中，选择 **"首选-减少运动：减少"。**</span><span class="sxs-lookup"><span data-stu-id="c5971-119">In the **Emulate CSS media feature prefers-reduced-motion** dropdown list, select **prefers-reduced-motion: reduced**.</span></span>

    :::image type="complex" source="../media/a11y-testing-simulating-reduced-motion.msft.png" alt-text="模拟减少运动和 CSS，以确保仅在用户需要时发生平滑滚动" lightbox="../media/a11y-testing-simulating-reduced-motion.msft.png":::
        <span data-ttu-id="c5971-121">模拟减少运动和 CSS，以确保仅在用户需要时发生平滑滚动</span><span class="sxs-lookup"><span data-stu-id="c5971-121">Simulating reduced motion and the CSS that makes sure that smooth scrolling only happens when the user wants it</span></span>
    :::image-end:::

1.  <span data-ttu-id="c5971-122">在网页中，选择蓝色菜单项，如 **"云**"或 **"Alpacas"。**</span><span class="sxs-lookup"><span data-stu-id="c5971-122">In the webpage, select the blue menu items, such as **Horses** or **Alpacas**.</span></span>  <span data-ttu-id="c5971-123">现在，网页立即滚动到选定部分，而不是使用平滑滚动动画。</span><span class="sxs-lookup"><span data-stu-id="c5971-123">Now the webpage instantly scrolls to the selected section, rather than using the smooth-scrolling animation.</span></span>

1.  <span data-ttu-id="c5971-124">在 **呈现工具中** ，在 **"模拟 CSS 媒体功能首选减少运动**"下，选择" **无模拟** "以删除此设置。</span><span class="sxs-lookup"><span data-stu-id="c5971-124">In the **Rendering** tool, below **Emulate CSS media feature prefers-reduced-motion**, select **No emulation** to remove this setting.</span></span>
   
<span data-ttu-id="c5971-125">请注意，即使使用上述媒体查询和模拟设置，演示网页仍运行以下动画。</span><span class="sxs-lookup"><span data-stu-id="c5971-125">Notice that the demo webpage still runs the following animations, even with the above media query and emulation settings.</span></span> <span data-ttu-id="c5971-126">生成 Web 产品时，请确保修复所有类似的动画。</span><span class="sxs-lookup"><span data-stu-id="c5971-126">When building your web product, ensure you fix all similar animations.</span></span>  
*  <span data-ttu-id="c5971-127">将鼠标悬停在蓝色菜单项上的动画。</span><span class="sxs-lookup"><span data-stu-id="c5971-127">Animation of the blue menu items when you hover over them.</span></span>
*  <span data-ttu-id="c5971-128">将鼠标悬停在"更多"\*\*\*\* 链接上的圆圈的动画。</span><span class="sxs-lookup"><span data-stu-id="c5971-128">Animation of the circles on the **More** links when you hover over them.</span></span>



## <a name="see-also"></a><span data-ttu-id="c5971-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5971-129">See also</span></span>

*  [<span data-ttu-id="c5971-130">减少运动模拟</span><span class="sxs-lookup"><span data-stu-id="c5971-130">Reduced motion simulation</span></span>](reduced-motion-simulation.md)
*  [<span data-ttu-id="c5971-131">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="c5971-131">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c5971-132">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="c5971-132">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
