---
description: 使用 Tab 键和 Enter 键检查键盘支持。
title: 使用 Tab 和 Enter 键检查键盘支持
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 48151e16a9059b5ebaadca36f29447d4ad3be8c7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597248"
---
# <a name="check-for-keyboard-support-by-using-the-tab-and-enter-keys"></a>使用 Tab 和 Enter 键检查键盘支持


并非所有用户都有指针或触摸设备，并且并非所有用户都可以查看我们创建的 Web 项目。  这就是为什么用户界面至少与键盘一起工作非常重要的原因。  确保可以使用键将焦点移到网页上的每个表单控件，并确保可以使用该键 `Tab` `Enter` 提交表单。

可以通过多种方式测试键盘用户的网页可用性：
*  通过使用键盘，尤其是 、 `Tab` `Shift` + `Tab` 和 `Enter` 键。  本文中介绍了此方法。
*  使用 Inspect 工具检查单个元素的 **键盘** 支持。  检查工具的信息覆盖包括一个 **辅助功能** 部分，其中包括 **一个键盘可聚焦** 的行。  
*  检查 **问题报告的** 辅助功能 **部分** ，了解键盘支持问题。

若要使用键盘而不是鼠标检查演示页面的辅助功能问题，请执行以下步骤：

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页。

1.  使用键盘导航演示文档，使用 `Tab` 和 `Shift` + `Tab` 键从元素跳到另一个元素。  在演示网页上， `Tab` 该密钥首先将焦点移到部分中的搜索 `header` 表单。

1.  选择 `Tab` 以将焦点放在按钮上，然后选择单击 `Enter` 聚焦按钮。  例如，在演示页面中，选择将焦点放在"搜索" `Tab` 字段**** 上，然后选择 `Enter` 提交搜索。  此方法将产生与选择"开始" **按钮相同的结果** 。  选择 `Enter` 发送搜索 **表单** 可以正常工作。

1.  再次 `Tab` 选择。  您重点关注的下一个元素是网页部分中的第一个 **"** 更多"链接， `content` 如大纲所指示。
    
    :::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="使用键盘和 Tab 键导航文档。 焦点显示在文档中的链接上。" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
        使用键盘和 Tab 键导航文档。 焦点显示在文档中的链接上。
    :::image-end:::
    
1.  多次 `Tab` 选择，直到传递最后一个 **"更多"** 链接。  页面向上滚动，你似乎位于页面的某个元素上，但无法判断它是哪个元素。

1.  请注意左下角的 URL。  如果你查看屏幕左侧的左下角 (或者如果你使用屏幕阅读器) ，你意识到你位于带蓝色链接的边栏导航菜单上，因为浏览器显示"猫"链接指向 (**** `#cats`) 的 URL。

    :::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="缺少焦点样式使无法知道您当前在文档中的什么位置。 唯一的提示是在屏幕左下角显示链接目标" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
        缺少焦点样式使无法知道您当前在文档中的什么位置。 唯一的提示是在屏幕左下角显示链接目标。
    :::image-end:::

1.  再次 `Tab` 选择，以到达"捐赠"窗体中的条目字段。  但是，无法通过选择 到达文本框上方的按钮 `Tab` 。 你不能使用键盘将焦点放在**50、100**或**200**按钮上，然后选择它们。 ****  此外， `Enter` 选择时不会提交该资金申请。

    :::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="在资金表单中，唯一一个可通过键盘访问的元素是文本输入字段" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
        在资金表单中，唯一一个可通过键盘访问的元素是文本输入字段
    :::image-end:::
    
1.  再次选择会将焦点放在页面的顶部导航栏上，并包含"主页"、"采用一只猫"、"我的产品"、"作业"和"关于 `Tab` **我们"的菜单按钮**。 **** **** **** ****  选择 `Tab` 或 `Shift` + `Tab` 将焦点放在菜单按钮上，如焦点轮廓所指示。  然后选择 `Enter` 以访问网页的该部分。

    :::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="主菜单具有突出显示和焦点轮廓，因此键盘可访问" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
        主菜单具有突出显示和焦点轮廓，因此键盘可访问
    :::image-end:::
    
基于上述演练，我们发现需要修复的以下问题。

*  使用键盘时，边栏导航菜单的蓝色链接不会直观地指示哪个链接具有焦点。  有关详细信息，请导航到分析边栏菜单中缺少 [键盘焦点的指示](test-analyze-no-focus-indicator.md)。

*  在"资金"表单中，金额按钮和 **"四** 分百"按钮不能与键盘一起使用。  有关详细信息，请导航到 [分析表单中缺少键盘支持](test-analyze-no-keyboard-support.md)。

*  键盘通过页面各部分访问的顺序不正确。  在到达 **边栏导航** 菜单之前，可以浏览文档中的所有"更多"链接。  当键将焦点放在边栏导航菜单上时 `Tab` ，你已遍历所有页面内容。 边栏导航菜单旨在提供对页面内容的轻松访问。  若要详细了解如何解决此问题，请导航到使用源订单查看器 [测试键盘支持](test-tab-key-source-order-viewer.md)。


## <a name="see-also"></a>另请参阅

*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
