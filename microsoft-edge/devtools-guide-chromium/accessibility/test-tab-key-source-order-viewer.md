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
# <a name="test-keyboard-support-using-the-source-order-viewer"></a>使用源订单查看器测试键盘支持

文档的源顺序对于辅助技术非常重要，并且可能不同于元素在呈现页面上的显示顺序。  使用 CSS，您可以直观地对页面元素进行重新排序，但这并不意味着屏幕阅读器等辅助技术将按相同的顺序表示页面元素。  

为了确保文档具有逻辑顺序，可以使用源顺序查看器用指定文档源代码**** 中顺序的数字标记不同的页面元素。  源**订单查看器**位于"样式"**** 选项卡 (的"辅助功能"选项卡) 。 ****


## <a name="analyzing-the-order-of-keyboard-access-through-sections-of-the-page"></a>通过页面的各个部分分析键盘访问的顺序

辅助功能 [测试演示][DevToolsA11yErrorsDemopage] 网页有一个反直观的 Tab 键顺序，在此顺序中，键盘用户只有在按 Tab 键浏览所有"更多"链接后才能访问边栏 **导航** 菜单。  边栏导航菜单是进入页面内容深度的快捷方式。  但是，因为你需要在到达边栏导航菜单之前浏览整个页面，所以该导航菜单对键盘用户无效。

演示 `Tab` 页面上的关键顺序为：
1. " **搜索** "字段，然后是"搜索 **"** 字段的 **"开始"** 按钮。
1. "**猫****"部分中的**"更多"按钮，用于导航到"猫"网页。  然后是其他 **更多** 按钮，用于"动物"、"动物"、"木马"和"Alpacas"。
1. 侧边栏导航菜单的蓝色链接："**猫**"、"动物****"和******"Alpacas"。** ****
1. 在"捐赠"表单中的"支持"文本框中。
1. 顶部导航栏中的按钮："主页"、"******采用一**只猫"、"一只猫"、"Jobs"和"关于******我们"。** ****
1. 浏览器的窗口顶部界面。

导致键顺序混乱的原因是，使用键盘时遇到的顺序由文档的 `Tab` 源顺序决定。  使用键盘遇到的顺序可以使用元素上的 属性进行修改，这将 `tabindex` 使该元素从源顺序中退出。

在文档的源代码中，边栏导航菜单显示在网页的主要内容之后。  CSS 用于将边栏导航菜单定位到网页大部分主要内容的上方。 

可以使用"辅助功能"选项卡中的"源 **顺序** 查看器"测试 **页面元素** 的顺序。 源 **订单查看器是** 一项实验性功能。 有关详细信息，请导航到"[源订单查看器"。](../experimental-features/index.md#source-order-viewer)


若要打开源订单查看器，请执行以下命令：

1.  在 DevTools 的右上角，选择"设置**\ (设置** ![ ](../media/settings-button-icon.msft.png) \) 按钮。  

1.  在 **"设置"** 下，选择"**实验"。**  

1.  选中" **源订单查看器"** 复选框。

1.  在页面的右上角，设置**X**以关闭设置页。 ****  在 DevTools 顶部，消息 **一个或多个设置已更改，要求重新加载生效。** 显示。  选择" **重新加载 DevTools"** 按钮。



若要激活源订单查看器并使用演示页面，请执行以下命令：

1.  打开 [新选项卡中的辅助功能测试][DevToolsA11yErrorsDemopage] 演示网页。 然后选择 **F12** 以打开 DevTools。

1.  在" **元素"** 工具中的"样式"选项卡 **的右侧** ，选择 **"辅助功能"** 选项卡。

1.  在" **源订单查看器** "部分，选中" **显示源订单"** 复选框。  在呈现的网页中，将显示数字，指示由源文件中的代码行顺序 `Tab` 控制的顺序。

1.  在"元素"工具的 DOM **树中，** 选择主要布局元素，如 `header` 元素。  数字覆盖现在显示在呈现的页面的各个部分，指示不同元素的源顺序。 

    :::image type="complex" source="../media/a11y-testing-source-order-viewer.msft.png" alt-text="激活源顺序查看器将源中的元素顺序作为页面上的覆盖显示" lightbox="../media/a11y-testing-source-order-viewer.msft.png":::
        激活源 **顺序查看器** 将源中的元素顺序作为页面上的覆盖显示
    :::image-end:::
    
1.  滚动页面以查看所有数字覆盖，包括页面页脚部分。


## <a name="see-also"></a>另请参阅

*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
