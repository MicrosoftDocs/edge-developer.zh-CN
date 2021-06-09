---
description: 若要验证网页是否可使用模糊视觉，在"呈现"工具中，使用"模拟视觉缺陷"下拉列表。
title: 验证页面是否可借助模糊视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 2fc1a1cf7746591573fce07946c7fb11abf42705
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597288"
---
# <a name="verify-that-the-page-is-usable-with-blurred-vision"></a><span data-ttu-id="3562e-104">验证页面是否可借助模糊视图</span><span class="sxs-lookup"><span data-stu-id="3562e-104">Verify that the page is usable with blurred vision</span></span>

<!-- Rendering tool: Emulate vision deficiencies: Blurred vision -->

<span data-ttu-id="3562e-105">若要模拟模糊的视觉，在 **呈现工具** 中，使用 **"模拟视觉缺陷"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="3562e-105">To simulate blurred vision, in the **Rendering** tool, use the **Emulate vision deficiencies** menu.</span></span>  <span data-ttu-id="3562e-106">当您将此功能与演示网页一同使用时，可以看到上菜单中文本的投影使阅读菜单项变得困难。</span><span class="sxs-lookup"><span data-stu-id="3562e-106">When you use this feature with the demo webpage, you can see that the drop shadow on the text in the upper menu makes it hard to read the menu items.</span></span>

<span data-ttu-id="3562e-107">若要检查网页是否具有模糊的视觉，请进行查看：</span><span class="sxs-lookup"><span data-stu-id="3562e-107">To check whether a webpage is usable with blurred vision:</span></span>

1.  <span data-ttu-id="3562e-108">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="3562e-108">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="3562e-109">选择 **Esc** 打开 DevTools 底部的"箱"。</span><span class="sxs-lookup"><span data-stu-id="3562e-109">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="3562e-110">Select the **+** icon at the top of the Drawer to display the list of tools， and then select **Rendering**.</span><span class="sxs-lookup"><span data-stu-id="3562e-110">Select the **+** icon at the top of the Drawer to display the list of tools, and then select **Rendering**.</span></span>  

1.  <span data-ttu-id="3562e-111">在"**模拟视觉缺陷**"下拉列表中，选择"**模糊的视觉"。**</span><span class="sxs-lookup"><span data-stu-id="3562e-111">In the **Emulate vision deficiencies** dropdown list, select **Blurred vision**.</span></span>

    :::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="模拟模糊的页面" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
        <span data-ttu-id="3562e-113">模拟模糊的页面</span><span class="sxs-lookup"><span data-stu-id="3562e-113">Simulating a blurred page</span></span>
    :::image-end:::

    <span data-ttu-id="3562e-114">请注意，CSS 属性使上方菜单上的菜单项文本难以 `text-shadow` 阅读。</span><span class="sxs-lookup"><span data-stu-id="3562e-114">Notice that the `text-shadow` CSS property makes the text of the menu items difficult to read on the upper menu.</span></span> <span data-ttu-id="3562e-115">例如，查看 **"主页"、"\*\*\*\*采用动物**"和其他菜单项。</span><span class="sxs-lookup"><span data-stu-id="3562e-115">For example, review the **Home**, **Adopt a Pet**, and other menu items.</span></span>
    
1.  <span data-ttu-id="3562e-116">在 **呈现工具** 的" **模拟视觉缺陷"** 中，选择"无 **模拟** "以删除模糊的视觉模拟。</span><span class="sxs-lookup"><span data-stu-id="3562e-116">In the **Rendering** tool, in **Emulate vision deficiencies**, select **No emulation** to remove the blurred vision simulation.</span></span>


## <a name="see-also"></a><span data-ttu-id="3562e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3562e-117">See also</span></span>

*  [<span data-ttu-id="3562e-118">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="3562e-118">Emulate vision deficiencies</span></span>](emulate-vision-deficiencies.md)
*  [<span data-ttu-id="3562e-119">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="3562e-119">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3562e-120">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="3562e-120">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
