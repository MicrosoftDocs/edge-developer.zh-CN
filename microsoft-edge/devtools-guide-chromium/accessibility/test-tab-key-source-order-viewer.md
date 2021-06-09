---
description: 若要快速查看页面各节的 Tab 键顺序，请使用辅助功能工具中"样式"选项卡右边的"源顺序查看器"。
title: 使用源订单查看器测试键盘支持
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 7e90221b581280a6eb63cee4d073622a80871903
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597249"
---
# <a name="test-keyboard-support-using-the-source-order-viewer"></a><span data-ttu-id="0bf43-104">使用源订单查看器测试键盘支持</span><span class="sxs-lookup"><span data-stu-id="0bf43-104">Test keyboard support using the Source Order Viewer</span></span>

<span data-ttu-id="0bf43-105">文档的源顺序对于辅助技术非常重要，并且可能不同于元素在呈现页面上的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="0bf43-105">The source order of a document is important for assistive technology, and can be different than the order in which elements appear on the rendered page.</span></span>  <span data-ttu-id="0bf43-106">使用 CSS，您可以直观地对页面元素进行重新排序，但这并不意味着屏幕阅读器等辅助技术将按相同的顺序表示页面元素。</span><span class="sxs-lookup"><span data-stu-id="0bf43-106">Using CSS, you can re-order page elements in a visual way, but that doesn't mean that assistive technology such as screen readers would represent page elements in the same order.</span></span>  

<span data-ttu-id="0bf43-107">为了确保文档具有逻辑顺序，可以使用源顺序查看器用指定文档源代码\*\*\*\* 中顺序的数字标记不同的页面元素。</span><span class="sxs-lookup"><span data-stu-id="0bf43-107">To ensure that the document has a logical order, you can use the **Source Order Viewer** to label different page elements with numbers that specify the order in the source code of the document.</span></span>  <span data-ttu-id="0bf43-108">源**订单查看器**位于"样式"\*\*\*\* 选项卡 (的"辅助功能"选项卡) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0bf43-108">The **Source Order Viewer** is in the **Accessibility** tab (near the **Styles** tab).</span></span>


## <a name="analyzing-the-order-of-keyboard-access-through-sections-of-the-page"></a><span data-ttu-id="0bf43-109">通过页面的各个部分分析键盘访问的顺序</span><span class="sxs-lookup"><span data-stu-id="0bf43-109">Analyzing the order of keyboard access through sections of the page</span></span>

<span data-ttu-id="0bf43-110">辅助功能 [测试演示][DevToolsA11yErrorsDemopage] 网页有一个反直观的 Tab 键顺序，在此顺序中，键盘用户只有在按 Tab 键浏览所有"更多"链接后才能访问边栏 **导航** 菜单。</span><span class="sxs-lookup"><span data-stu-id="0bf43-110">The [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] has a counterintuitive tabbing order, where keyboard users access the sidebar navigation menu only after tabbing through all the **More** links.</span></span>  <span data-ttu-id="0bf43-111">边栏导航菜单是进入页面内容深度的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0bf43-111">The sidebar navigation menu is meant to be a shortcut to reach deep into the page content.</span></span>  <span data-ttu-id="0bf43-112">但是，因为你需要在到达边栏导航菜单之前浏览整个页面，所以该导航菜单对键盘用户无效。</span><span class="sxs-lookup"><span data-stu-id="0bf43-112">But because you need to go through the entire page before you reach the sidebar navigation menu, that navigation menu is ineffective for keyboard users.</span></span>

<span data-ttu-id="0bf43-113">演示 `Tab` 页面上的关键顺序为：</span><span class="sxs-lookup"><span data-stu-id="0bf43-113">The `Tab` key order on the demo page is:</span></span>
1. <span data-ttu-id="0bf43-114">" **搜索** "字段，然后是"搜索 **"** 字段的 **"开始"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="0bf43-114">The **Search** field, then the **go** button for the **Search** field.</span></span>
1. <span data-ttu-id="0bf43-115">"**猫\*\*\*\*"部分中的**"更多"按钮，用于导航到"猫"网页。</span><span class="sxs-lookup"><span data-stu-id="0bf43-115">The **More** button in the **Cats** section, to navigate to a "Cats" webpage.</span></span>  <span data-ttu-id="0bf43-116">然后是其他 **更多** 按钮，用于"动物"、"动物"、"木马"和"Alpacas"。</span><span class="sxs-lookup"><span data-stu-id="0bf43-116">Then the other **More** buttons, for Dogs, Sheep, Horses, and then Alpacas.</span></span>
1. <span data-ttu-id="0bf43-117">侧边栏导航菜单的蓝色链接："**猫**"、"动物\*\*\*\*"和\*\*\*\*\*\*"Alpacas"。\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0bf43-117">The blue links of the sidebar navigation menu: **Cats**, **Dogs**, **Sheep**, **Horses**, and then **Alpacas**.</span></span>
1. <span data-ttu-id="0bf43-118">在"捐赠"表单中的"支持"文本框中。</span><span class="sxs-lookup"><span data-stu-id="0bf43-118">The donation textbox in the donation form.</span></span>
1. <span data-ttu-id="0bf43-119">顶部导航栏中的按钮："主页"、"\*\*\*\*\*\*采用一**只猫"、"一只猫"、"Jobs"和"关于\*\*\*\*\*\*我们"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0bf43-119">The buttons in the top navigation bar: **Home**, **Adopt a pet**, **Donate**, **Jobs**, and then **About Us**.</span></span>
1. <span data-ttu-id="0bf43-120">浏览器的窗口顶部界面。</span><span class="sxs-lookup"><span data-stu-id="0bf43-120">The browser's top-of-window interface.</span></span>

<span data-ttu-id="0bf43-121">导致键顺序混乱的原因是，使用键盘时遇到的顺序由文档的 `Tab` 源顺序决定。</span><span class="sxs-lookup"><span data-stu-id="0bf43-121">The reason for the confusing `Tab` key order is that the order experienced when using a keyboard is determined by the source order of the document.</span></span>  <span data-ttu-id="0bf43-122">使用键盘遇到的顺序可以使用元素上的 属性进行修改，这将 `tabindex` 使该元素从源顺序中退出。</span><span class="sxs-lookup"><span data-stu-id="0bf43-122">The order experienced using a keyboard can be modified using the `tabindex` attribute on elements, which takes that element out of the source order.</span></span>

<span data-ttu-id="0bf43-123">在文档的源代码中，边栏导航菜单显示在网页的主要内容之后。</span><span class="sxs-lookup"><span data-stu-id="0bf43-123">In the source code of the document, the sidebar navigation menu appears after the main content of the webpage.</span></span>  <span data-ttu-id="0bf43-124">CSS 用于将边栏导航菜单定位到网页大部分主要内容的上方。</span><span class="sxs-lookup"><span data-stu-id="0bf43-124">CSS was used to position the sidebar navigation menu above most of the main content of the webpage.</span></span> 

<span data-ttu-id="0bf43-125">可以使用"辅助功能"选项卡中的"源 **顺序** 查看器"测试 **页面元素** 的顺序。 源 **订单查看器是** 一项实验性功能。</span><span class="sxs-lookup"><span data-stu-id="0bf43-125">You can test the order of page elements by using the **Source Order Viewer** in the **Accessibility** tab.  The **Source Order Viewer** is an experimental feature.</span></span> <span data-ttu-id="0bf43-126">有关详细信息，请导航到"[源订单查看器"。](../experimental-features/index.md#source-order-viewer)</span><span class="sxs-lookup"><span data-stu-id="0bf43-126">For more information, navigate to [Source Order Viewer](../experimental-features/index.md#source-order-viewer).</span></span>


<span data-ttu-id="0bf43-127">若要打开源订单查看器，请执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0bf43-127">To turn on the Source Order Viewer:</span></span>

1.  <span data-ttu-id="0bf43-128">在 DevTools 的右上角，选择"设置**\ (设置** ![ ](../media/settings-button-icon.msft.png) \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="0bf43-128">In DevTools, in the upper right, select the **Settings** \(![Settings button](../media/settings-button-icon.msft.png)\) button.</span></span>  

1.  <span data-ttu-id="0bf43-129">在 **"设置"** 下，选择"**实验"。**</span><span class="sxs-lookup"><span data-stu-id="0bf43-129">Below **Settings**, select **Experiments**.</span></span>  

1.  <span data-ttu-id="0bf43-130">选中" **源订单查看器"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="0bf43-130">Select the **Source Order Viewer** checkbox.</span></span>

1.  <span data-ttu-id="0bf43-131">在页面的右上角，设置**X**以关闭设置页。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0bf43-131">In the upper-right corner of the **Settings** page, select **X** to close the Settings page.</span></span>  <span data-ttu-id="0bf43-132">在 DevTools 顶部，消息 **一个或多个设置已更改，要求重新加载生效。**</span><span class="sxs-lookup"><span data-stu-id="0bf43-132">At the top of DevTools, the message **One or more settings have changed which require a reload to take effect.**</span></span> <span data-ttu-id="0bf43-133">显示。</span><span class="sxs-lookup"><span data-stu-id="0bf43-133">is displayed.</span></span>  <span data-ttu-id="0bf43-134">选择" **重新加载 DevTools"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="0bf43-134">Select the **Reload DevTools** button.</span></span>



<span data-ttu-id="0bf43-135">若要激活源订单查看器并使用演示页面，请执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0bf43-135">To activate and use the Source Order Viewer, with the demo page:</span></span>

1.  <span data-ttu-id="0bf43-136">打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。 然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="0bf43-136">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="0bf43-137">在" **元素"** 工具中的"样式"选项卡 **的右侧** ，选择 **"辅助功能"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0bf43-137">In the **Elements** tool, to the right of the **Styles** tab, select the **Accessibility** tab.</span></span>

1.  <span data-ttu-id="0bf43-138">在" **源订单查看器** "部分，选中" **显示源订单"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="0bf43-138">In the **Source Order Viewer** section, select the **Show source order** checkbox.</span></span>  <span data-ttu-id="0bf43-139">在呈现的网页中，将显示数字，指示由源文件中的代码行顺序 `Tab` 控制的顺序。</span><span class="sxs-lookup"><span data-stu-id="0bf43-139">In the rendered webpage, numbers appear, indicating the `Tab` order as controlled by the order of lines of code in the source file.</span></span>

1.  <span data-ttu-id="0bf43-140">在"元素"工具的 DOM **树中，** 选择主要布局元素，如 `header` 元素。</span><span class="sxs-lookup"><span data-stu-id="0bf43-140">In the DOM tree in the **Elements** tool, select a major layout element, such as the `header` element.</span></span>  <span data-ttu-id="0bf43-141">数字覆盖现在显示在呈现的页面的各个部分，指示不同元素的源顺序。</span><span class="sxs-lookup"><span data-stu-id="0bf43-141">Numeric overlays are now displayed on sections of the rendered page, which indicate the source order of the different elements.</span></span> 

    :::image type="complex" source="../media/a11y-testing-source-order-viewer.msft.png" alt-text="激活源顺序查看器将源中的元素顺序作为页面上的覆盖显示" lightbox="../media/a11y-testing-source-order-viewer.msft.png":::
        <span data-ttu-id="0bf43-143">激活源 **顺序查看器** 将源中的元素顺序作为页面上的覆盖显示</span><span class="sxs-lookup"><span data-stu-id="0bf43-143">Activating the **Source Order Viewer** shows the order of the elements in the source as overlays on the page</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="0bf43-144">滚动页面以查看所有数字覆盖，包括页面页脚部分。</span><span class="sxs-lookup"><span data-stu-id="0bf43-144">Scroll the page to see all of the numeric overlays, including on the page footer section.</span></span>


## <a name="see-also"></a><span data-ttu-id="0bf43-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf43-145">See also</span></span>

*  [<span data-ttu-id="0bf43-146">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="0bf43-146">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0bf43-147">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="0bf43-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
