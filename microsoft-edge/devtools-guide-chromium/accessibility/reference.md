---
description: 开发人员工具中的辅助功能测试Microsoft Edge列表。
title: DevTools 中的辅助功能测试功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: a906d60bb74d927fd86c21af1535a8f62eb93cad
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597038"
---
# <a name="accessibility-testing-features-in-devtools"></a>DevTools 中的辅助功能测试功能

若要测试网页的辅助功能，请首先制作要测试的辅助功能方面的清单，然后使用相关的 DevTools 功能检查每个方面。

| 要检查的辅助功能方面 | DevTools 的功能 | 文章或副标题 |
|---|---|---|
| 验证图像是否包含替换文字 | **报告** > **辅助功能部分** 的问题工具 | [验证图像是否包含替换文字](test-issues-tool.md#verify-that-images-have-alt-text) |
| 验证键盘支持 | **检查** 工具> **覆盖的辅助功能** 部分 | [使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题](test-inspect-tool.md) |
| 验证键盘支持 | `Tab`、 `Shift+Tab` 和 `Enter` 键 | [使用 Tab 和 Enter 键检查键盘支持](test-tab-enter-keys.md) |
| 验证键盘支持：验证是否指示焦点 | **检查** 工具 **、"样式"** 选项卡和 **"源"** 工具 | [分析边栏菜单中键盘焦点的缺失](test-analyze-no-focus-indicator.md) |
| 验证键盘支持：验证窗体按钮是否可与键盘一同使用 | **检查**工具 **、"元素"工具中的 DOM****树和****"事件侦听器"** 选项卡 | [分析窗体中键盘支持缺失](test-analyze-no-keyboard-support.md) |
| 验证键盘支持：验证 `Tab` 键顺序 | **元素**工具>**源订单查看器>****辅助功能"选项卡** | [使用源订单查看器测试键盘支持](test-tab-key-source-order-viewer.md) |
| 验证文本是否具有足够的对比度 (，以便自动显示整个页面)  | **报告** > **辅助功能部分** 的问题工具 | [验证文本颜色是否具有足够的对比度](test-issues-tool.md#verify-that-text-colors-have-enough-contrast) |
| 验证文本是否具有足够的对比度 | **元素**工具>**颜色选取器>****样式"选项卡** | [使用颜色选取器测试文本颜色对比度](color-picker.md) |
| 验证文本是否具有足够的对比度 | **检查**覆盖>**对比度行**的"辅助功能">**部分** | [使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题](test-inspect-tool.md) |
| 验证文本是否具有足够的对比度：处于悬停状态 | **"** 元素 **">"选项卡** > **切换元素状态"** | [验证所有元素状态可访问性](test-inspect-states.md) |
| 验证文本是否具有足够的对比度：使用深色主题 (深色模式) 浅色主题 | **呈现** 工具> **模拟 CSS 媒体功能首选配色方案** | [检查深色主题和浅主题的对比度问题](test-dark-mode.md) |
| 验证屏幕阅读器支持：验证输入字段是否包含标签 | **报告** > **辅助功能部分** 的问题工具 | [验证输入字段是否包含标签](test-issues-tool.md#verify-that-input-fields-have-labels) |
| 验证屏幕阅读器支持 | **检查**覆盖 **>名称和角色**的>**辅助功能****部分** | [使用"检查"工具将鼠标悬停在网页上以检测辅助功能问题](test-inspect-tool.md) |
| 验证屏幕阅读器支持 | **元素**工具>**辅助功能选项卡>****辅助功能树** | [检查辅助功能树，获取键盘和屏幕阅读器支持](test-accessibility-tree.md)，以及使用 [辅助功能选项卡测试辅助功能](accessibility-tab.md) |
| 验证网页是否对色盲者可用 | **呈现** 工具> **模拟视觉缺陷** 下拉列表 | [验证页面是否由色盲用户可用](test-color-blindness.md) |
| 验证网页是否具有模糊视觉 | **呈现** 工具> **模拟视觉缺陷** 下拉列表 | [验证页面是否可借助模糊视图](test-blurred-vision.md) |
| 验证网页是否可用，并关闭 UI 动画， (运动效果)  | **呈现** 工具> **模拟 CSS 媒体功能首选减少运动** | [验证页面是否可用，同时关闭 UI 动画](test-reduced-ui-motion.md) |
| 验证网页布局在较窄时是否可用 | **设备仿真** 工具 | [验证网页布局在开发人员工具中的窄](accessibility-testing-in-devtools.md#verify-that-the-webpage-layout-is-usable-when-narrow)和模拟移动设备Microsoft Edge[可用](../device-mode/index.md) |


## <a name="see-also"></a>另请参阅

*   [使用 DevTools 的辅助功能测试概述][DevtoolsAccessibilityAccessibilitytestingindevtools]
*   [使用辅助技术导航 Microsoft Edge 开发工具][DevtoolsAccessibilityNavigation]
*   [辅助功能测试][DevtoolsAccessibilityTest]
*   [辅助功能原则和最佳做法][MDNAccessibility]
*   [屏幕阅读器][MDNScreenReader]


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->  
[DevtoolsAccessibilityTest]: ../../accessibility/test.md "辅助功能测试|Microsoft Docs"
[DevtoolsAccessibilityAccessibilitytestingindevtools]: accessibility-testing-in-devtools.md "使用 DevTools 工具的辅助功能测试|Microsoft Docs"
[DevtoolsAccessibilityNavigation]: ./navigation.md "使用Microsoft Edge技术工具导航到 DevTools |Microsoft Docs"  
<!-- external -->
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "辅助功能 | MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "屏幕阅读器 | MDN"  
