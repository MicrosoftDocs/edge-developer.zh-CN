---
description: 使用呈现工具中的"模拟视觉缺陷"下拉列表，检查具有色盲的人是否可使用此网页。
title: 验证页面是否由色盲用户可用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 54cd7230f0402bfeb4b5ee28d2bcd0947794676f
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597286"
---
# <a name="verify-that-the-page-is-usable-by-people-with-color-blindness"></a><span data-ttu-id="ae86f-104">验证页面是否由色盲用户可用</span><span class="sxs-lookup"><span data-stu-id="ae86f-104">Verify that the page is usable by people with color blindness</span></span>

<!-- Rendering tool: Emulate vision deficiencies: Protanopia -->

<span data-ttu-id="ae86f-105">若要检查网页是否由色盲人士使用，请在"呈现"工具中\*\*\*\*，**使用"模拟**视觉缺陷"下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ae86f-105">To check that a webpage is usable by people with color blindness, in the **Rendering** tool, use the **Emulate vision deficiencies** dropdown list.</span></span>

<span data-ttu-id="ae86f-106">在辅助功能测试演示网页上，不同的接收状态使用颜色作为区别的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="ae86f-106">On the accessibility-testing demo webpage, the different donation states use color as the only means of differentiation.</span></span>
*  <span data-ttu-id="ae86f-107">绿色表示已收到大量资金。</span><span class="sxs-lookup"><span data-stu-id="ae86f-107">Green means a high amount of donations have been received.</span></span>
*  <span data-ttu-id="ae86f-108">黄色表示已收到中等金额的笔款。</span><span class="sxs-lookup"><span data-stu-id="ae86f-108">Yellow means a medium amount of donations have been received.</span></span>
*  <span data-ttu-id="ae86f-109">红色表示已收到少量资金。</span><span class="sxs-lookup"><span data-stu-id="ae86f-109">Red means a low amount of donations have been received.</span></span>

<span data-ttu-id="ae86f-110">但是，你无法预期你的所有用户都如预期体验这些颜色。</span><span class="sxs-lookup"><span data-stu-id="ae86f-110">But you can't expect all of your users to experience these colors as intended.</span></span>  <span data-ttu-id="ae86f-111">通过使用呈现**工具的"** 模拟视觉缺陷"功能\*\*\*\*，你可以模拟不同视觉的人如何理解你的设计，发现此设计不够好。</span><span class="sxs-lookup"><span data-stu-id="ae86f-111">By using the **Emulate vision deficiencies** feature of the **Rendering** tool, you can find out that this design is not good enough, by simulating how people with different vision would perceive your design.</span></span>


<span data-ttu-id="ae86f-112">检查网页是否由色盲用户使用：</span><span class="sxs-lookup"><span data-stu-id="ae86f-112">To check whether a webpage is usable by people with color blindness:</span></span>

1.  <span data-ttu-id="ae86f-113">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="ae86f-113">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="ae86f-114">选择 **Esc** 打开 DevTools 底部的"箱"。</span><span class="sxs-lookup"><span data-stu-id="ae86f-114">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="ae86f-115">Select the **+** icon at the top of the Drawer to see the list of tools， and then select **Rendering**.</span><span class="sxs-lookup"><span data-stu-id="ae86f-115">Select the **+** icon at the top of the Drawer to see the list of tools, and then select **Rendering**.</span></span>  

1.  <span data-ttu-id="ae86f-116">在"**模拟视力**障碍"下拉列表中，选择 **"Protanopia"。**</span><span class="sxs-lookup"><span data-stu-id="ae86f-116">In the **Emulate vision deficiencies** dropdown list, select **Protanopia**.</span></span>  <span data-ttu-id="ae86f-117">_Protanopia_ 对红色光的敏感度降低，使得难以区分绿色、红色和黄色。</span><span class="sxs-lookup"><span data-stu-id="ae86f-117">_Protanopia_ is reduced sensitivity to red light, making it hard to differentiate green, red, and yellow.</span></span>

    :::image type="complex" source="../media/a11y-testing-simulating-protanopia.msft.png" alt-text="将文档作为具有 protanopia 的人显示将会看到它" lightbox="../media/a11y-testing-simulating-protanopia.msft.png":::
        <span data-ttu-id="ae86f-119">将文档作为具有 protanopia 的人显示将会看到它</span><span class="sxs-lookup"><span data-stu-id="ae86f-119">Showing the document as someone with protanopia would see it</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="ae86f-120">在 **呈现工具的** " **模拟视觉缺陷"下**，选择"无 **模拟** "以删除模拟。</span><span class="sxs-lookup"><span data-stu-id="ae86f-120">In the **Rendering** tool, below **Emulate vision deficiencies**, select **No emulation** to remove the simulation.</span></span>


## <a name="see-also"></a><span data-ttu-id="ae86f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae86f-121">See also</span></span>

*  <span data-ttu-id="ae86f-122">[模拟视觉缺陷][DevToolsVisionDeficiencies]- 定义"模拟视觉缺陷\*\*\*\*"下拉列表中的项目，包括 Protanopia、Deuteranopia、Tritanopia 和 Achromatopia。</span><span class="sxs-lookup"><span data-stu-id="ae86f-122">[Emulate vision deficiencies][DevToolsVisionDeficiencies] - Defines the items in the **Emulate vision deficiencies** dropdown list, including Protanopia, Deuteranopia, Tritanopia, and Achromatopsia.</span></span>
*  [<span data-ttu-id="ae86f-123">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="ae86f-123">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ae86f-124">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="ae86f-124">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsVisionDeficiencies]: ./emulate-vision-deficiencies.md "模拟视觉缺陷|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
