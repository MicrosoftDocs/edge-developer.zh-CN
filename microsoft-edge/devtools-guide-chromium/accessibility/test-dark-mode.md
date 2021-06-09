---
description: 使用呈现工具中的"模拟 CSS 媒体功能首选-配色方案\"下拉列表) 检查深色主题和浅色主题 (的对比度问题。
title: 检查深色主题和浅主题的对比度问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 052c75b610ec872329f387e46819867f299a8ca9
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597285"
---
# <a name="check-for-contrast-issues-with-dark-theme-and-light-theme"></a><span data-ttu-id="361da-104">检查深色主题和浅主题的对比度问题</span><span class="sxs-lookup"><span data-stu-id="361da-104">Check for contrast issues with dark theme and light theme</span></span>

<!-- Rendering tool: Emulate CSS media feature prefers-color-scheme -->

<span data-ttu-id="361da-105">测试颜色辅助功能时，可能需要测试不同的显示颜色主题，以测试对比度问题。</span><span class="sxs-lookup"><span data-stu-id="361da-105">When testing color accessibility, there could be different display color themes that you need to test for contrast issues.</span></span>

<span data-ttu-id="361da-106">大多数操作系统都提供深色模式和浅色模式。</span><span class="sxs-lookup"><span data-stu-id="361da-106">Most operating systems come with a dark mode and a light mode.</span></span>  <span data-ttu-id="361da-107">您的网页可以使用 CSS 媒体查询对此操作系统设置做出反应。</span><span class="sxs-lookup"><span data-stu-id="361da-107">Your webpage can react to this operating system setting, by using a CSS media query.</span></span>  <span data-ttu-id="361da-108">您可以使用呈现工具中的 CSS 选项测试这些主题并测试 CSS 媒体查询，而无需更改 `prefers-color-scheme` **操作系统** 设置。</span><span class="sxs-lookup"><span data-stu-id="361da-108">You can test these themes and test your CSS media query without having to change your operating system setting, by using the `prefers-color-scheme` CSS options in the **Rendering** tool.</span></span>

<span data-ttu-id="361da-109">例如，辅助功能测试演示页面包括浅色主题和深色主题。</span><span class="sxs-lookup"><span data-stu-id="361da-109">As an example, the accessibility-testing demo page includes a light theme and a dark theme.</span></span>  <span data-ttu-id="361da-110">演示页面从操作系统继承深色或浅色主题设置。</span><span class="sxs-lookup"><span data-stu-id="361da-110">The demo page inherits the dark or light theme setting from the operating system.</span></span>  <span data-ttu-id="361da-111">如果我们使用 DevTools 模拟将操作系统设置为浅色方案，然后刷新演示网页，问题工具将显示六个\*\*\*\* 色对比度问题，而不是两个。</span><span class="sxs-lookup"><span data-stu-id="361da-111">If we use DevTools to simulate the operating system being set to a light scheme and then refresh the demo webpage, the **Issues** tool shows six color-contrast problems instead of two.</span></span>  <span data-ttu-id="361da-112"> (你可能会看到不同的数字。) </span><span class="sxs-lookup"><span data-stu-id="361da-112">(You might see different numbers.)</span></span>


<span data-ttu-id="361da-113">若要模拟用户的首选颜色主题选择：：</span><span class="sxs-lookup"><span data-stu-id="361da-113">To emulate a user's selection of preferred color theme:</span></span>

1.  <span data-ttu-id="361da-114">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="361da-114">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="361da-115">选择 **Esc** 打开 DevTools 底部的"箱"。</span><span class="sxs-lookup"><span data-stu-id="361da-115">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="361da-116">Select the **+** icon at the top of the Drawer to see the list of tools， and then select **Rendering**.</span><span class="sxs-lookup"><span data-stu-id="361da-116">Select the **+** icon at the top of the Drawer to see the list of tools, and then select **Rendering**.</span></span>  <span data-ttu-id="361da-117">将显示呈现工具。</span><span class="sxs-lookup"><span data-stu-id="361da-117">The Rendering tool appears.</span></span>

1.  <span data-ttu-id="361da-118">在模拟 **CSS 媒体功能 prefers-color-scheme** 下拉列表中，选择 **prefers-color-scheme： light**。</span><span class="sxs-lookup"><span data-stu-id="361da-118">In the **Emulate CSS media feature prefers-color-scheme** dropdown list, select **prefers-color-scheme: light**.</span></span>      <span data-ttu-id="361da-119">网页使用 重新呈现 `light-theme.css` 。</span><span class="sxs-lookup"><span data-stu-id="361da-119">The webpage is re-rendered using `light-theme.css`.</span></span>


    :::image type="complex" source="../media/a11y-testing-simulating-light-mode.msft.png" alt-text="使用呈现工具模拟光线模式并触发文档的其他主题" lightbox="../media/a11y-testing-simulating-light-mode.msft.png":::
        <span data-ttu-id="361da-121">使用呈现工具模拟光线模式并触发文档的其他主题</span><span class="sxs-lookup"><span data-stu-id="361da-121">Using the Rendering tool to simulate a light mode and triggering the other theme of the document</span></span>
    :::image-end:::


1.  <span data-ttu-id="361da-122">选择 **"问题** "工具，然后展开 **"辅助功能"** 部分。</span><span class="sxs-lookup"><span data-stu-id="361da-122">Select the **Issues** tool, and then expand the **Accessibility** section.</span></span>  <span data-ttu-id="361da-123">根据各种因素，你可能会收到 `Insufficient color contrast` 警告。</span><span class="sxs-lookup"><span data-stu-id="361da-123">Depending on various factors, you might get `Insufficient color contrast` warnings.</span></span> <span data-ttu-id="361da-124">请注意， **在受影响的资源** 中，有 6 个元素的颜色对比度不足。</span><span class="sxs-lookup"><span data-stu-id="361da-124">Notice in **AFFECTED RESOURCES** there are 6 elements with insufficient color contrast.</span></span>
    
    :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="由于浅色主题更改而检测到的新对比度问题" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
        <span data-ttu-id="361da-126">由于浅色主题更改而检测到的新对比度问题</span><span class="sxs-lookup"><span data-stu-id="361da-126">New contrast issues detected because of the change to light theme</span></span>
    :::image-end:::
    
    <span data-ttu-id="361da-127">在我们的演示页面上，页面的 **"私人** 状态"部分在浅色模式下不可读，需要更改。</span><span class="sxs-lookup"><span data-stu-id="361da-127">On our demo page, the **Donation status** section of the page is unreadable in light mode, and needs to change.</span></span> 
    
    :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="在浅色模式下，"接收状态"部分有对比度问题" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
        <span data-ttu-id="361da-129">在 **浅色模式下** ，"接收状态"部分有对比度问题</span><span class="sxs-lookup"><span data-stu-id="361da-129">The **Donation Status** section has contrast issues in light mode</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="361da-130">在 DevTools 中，选择 **"元素**"工具，然后选择 macOS 上的 Windows/Linux 或 Command+F 上的**Ctrl+F。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="361da-130">In DevTools, select the **Elements** tool, and then select **Ctrl+F** on Windows/Linux or **Command+F** on macOS.</span></span>  <span data-ttu-id="361da-131">将显示 **"** 查找"文本框，以在 HTML DOM 树中搜索。</span><span class="sxs-lookup"><span data-stu-id="361da-131">The **Find** textbox appears, to search within the HTML DOM tree.</span></span>
 
1.  <span data-ttu-id="361da-132">输入 `scheme` 。</span><span class="sxs-lookup"><span data-stu-id="361da-132">Enter `scheme`.</span></span>  <span data-ttu-id="361da-133">找到以下 CSS 媒体查询，现在可更新相应的 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="361da-133">The following CSS media queries are found, and the corresponding CSS files can now be updated.</span></span>

    ```html
    <link rel="stylesheet" href="css/light-theme.css" media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)">
    <link rel="stylesheet" href="css/dark-theme.css" media="(prefers-color-scheme: dark)">
    ```


## <a name="see-also"></a><span data-ttu-id="361da-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="361da-134">See also</span></span>

*  [<span data-ttu-id="361da-135">深色或浅色配色方案模拟</span><span class="sxs-lookup"><span data-stu-id="361da-135">Dark or light color scheme simulation</span></span>][DevToolsColorSchemeSimulation]
*  [<span data-ttu-id="361da-136">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="361da-136">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="361da-137">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="361da-137">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "深色或浅色配色方案模拟|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
