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
# <a name="verify-that-the-page-is-usable-with-blurred-vision"></a>验证页面是否可借助模糊视图

<!-- Rendering tool: Emulate vision deficiencies: Blurred vision -->

若要模拟模糊的视觉，在 **呈现工具** 中，使用 **"模拟视觉缺陷"** 菜单。  当您将此功能与演示网页一同使用时，可以看到上菜单中文本的投影使阅读菜单项变得困难。

若要检查网页是否具有模糊的视觉，请进行查看：

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  选择 **Esc** 打开 DevTools 底部的"箱"。  Select the **+** icon at the top of the Drawer to display the list of tools， and then select **Rendering**.  

1.  在"**模拟视觉缺陷**"下拉列表中，选择"**模糊的视觉"。**

    :::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="模拟模糊的页面" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
        模拟模糊的页面
    :::image-end:::

    请注意，CSS 属性使上方菜单上的菜单项文本难以 `text-shadow` 阅读。 例如，查看 **"主页"、"****采用动物**"和其他菜单项。
    
1.  在 **呈现工具** 的" **模拟视觉缺陷"** 中，选择"无 **模拟** "以删除模糊的视觉模拟。


## <a name="see-also"></a>另请参阅

*  [模仿视觉缺陷](emulate-vision-deficiencies.md)
*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
