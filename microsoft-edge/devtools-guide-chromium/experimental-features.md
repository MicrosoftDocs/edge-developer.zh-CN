---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: c78e9aa5e0b4d808dd67d607a954b185ddcf54e7
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003995"
---
# 实验功能  

Microsoft Edge DevTools 提供对仍在开发中的实验功能的访问权限。  你可以在发布每个功能之前测试和 p[提供反馈](#providing-feedback-on-experimental-features) 。  

尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。  

## 启用实验功能  

使用以下步骤打开 Microsoft Edge 中的 " (" 或 "关闭" ) 实验功能。  

1.  [打开 DevTools][DevtoolsOpen]。  
     *   选择 `Control` + `Shift` + `I` \ (Windows \ ) 或 `Command` + `Option` + `I` \ (macOS \ ) 。  有关详细信息，请参阅 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  打开 " [设置][DevToolsCustomizeSettings] " 窗格。  
    *   选择 `Shift` + `?` 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  在 " **设置** " 窗格的左侧，选择 " **实验** " 部分。  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.msft.png":::
       DevTools 设置中的实验列表  
    :::image-end:::  
    
1.  在 " **实验** " 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。  
1.  关闭并重新打开 Microsoft Edge DevTools。  

> [!NOTE]
> 实验性功能将不断更新，并可能导致性能问题。  若要关闭实验功能，请打开 " **试验** " 页面，然后清除要关闭的实验功能的复选框。  

## 突出显示实验功能  

以下部分介绍 Microsoft Edge 中可用的新实验功能。  

| 实验性功能 | Microsoft Edge 版本 |  
|:--- |:--- |  
| [启用自定义键盘快捷方式设置选项卡](#enable-custom-keyboard-shortcuts-settings-tab) | 84或更高版本 |
| [仿真：支持双重屏幕模式](#emulation-support-dual-screen-mode) | 84或更高版本 |  
| [启用新的 CSS 网格调试功能](#enable-new-css-grid-debugging-features) | 85或更高版本 |  
| [启用支持以在面板之间移动选项卡](#enable-support-to-move-tabs-between-panels) | 85或更高版本 |  
| [启用 webhint](#enable-webhint) | 85或更高版本 |  
| [启用网络控制台](#enable-network-console) | 85或更高版本 |  
| [启用源订单查看器](#enable-source-order-viewer) | 86或更高版本 |  

### 启用自定义键盘快捷方式设置选项卡  

在[DevTools 设置][DevToolsCustomizeSettings]中提供新的**快捷方式**页面，以便将 DevTools 中的[键盘快捷方式][DevToolsShortcuts]与[Microsoft Visual Studio 代码][VisualstudioCode]相匹配。  

启用实验后，使用 select 再次打开[DevTools 设置][DevToolsCustomizeSettings] `Shift` + `?` 。  导航到 "新建 **快捷方式** " 页面。  选择 " **)  (DevTools** " 中的 "选择"，然后选择 "**匹配预设的快捷方式**" 下拉列表，然后选择**Visual Studio 代码**  DevTools 中的键盘快捷方式现在与 Visual Studio 代码中等效操作的快捷方式相匹配。  

:::image type="complex" source="./media/experiments-keyboard-shortcut.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="./media/experiments-keyboard-shortcut.msft.png":::
   将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配  
:::image-end:::  

例如，在 Windows 上，在 [Visual Studio 代码][VisualstudioCodeShortcutsKeyboardWindows] 中暂停或继续运行脚本的键盘快捷方式是 `F5` 。  通过 **DevTools (默认) ** 预设，DevTools 中的相同快捷方式 `F8` 。  通过 **Visual Studio 代码** 预置，快捷方式也是 `F5` 。  

### 仿真：支持双重屏幕模式  

提供用于模拟 Microsoft Edge 中的两个新的双屏幕和可折叠设备的附加功能。  

*   [Surface 双核][SurfaceDevicesDuo]  
*   [Samsung Galaxy 折页][SamsungMobileGalaxyFold]  

模拟设备并在以下姿势之间切换。  

*   单屏幕或折叠的状况  
*   双屏幕或展开的状况  

使用 [启用实验性 api](#enable-experimental-apis) 增强你的网站 \ (或设备的应用 \ ) 。  你还可以使用 [CSS 媒体查询和 JavaScript Windows Segment 枚举 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]。  

<!-- This image was taken in Chromium Canary since we don't yet have an Edge Canary that has Stan's changes -->  

:::image type="complex" source="./media/experiments-dual-screen-emulation.msft.png" alt-text="在 Microsoft Edge 中模拟 Surface 双核" lightbox="./media/experiments-dual-screen-emulation.msft.png":::  
   在 Microsoft Edge 中模拟 Surface 双核  
:::image-end:::  

#### 启用实验性 Api  

若要在 Microsoft Edge DevTools 中 [启用此实验](#turn-on-experimental-features) ，请完成以下步骤。  

1.  导航到 `edge://flags` 。  
1.  在 " **搜索标志** " 文本框中，输入 `Experimental Web Platform features` ，选择实验性的 **Web 平台功能** 标志，将 " **已禁用** " 更改为 " **已启用**"。  
1.  重启 Microsoft Edge。  

若要增强适用于双屏幕和可折叠设备的网站或应用，请导航到 [CSS 媒体查询和 JavaScript Windows Segment 枚举 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]。

在 Microsoft Edge DevTools 中[打开此实验](#turn-on-experimental-features)。  

1.  在 Microsoft Edge 中打开新的选项卡，然后导航到 `edge://flags` 。  
1.  在 " **搜索标记** " 文本框中，输入 `Experimental Web Platform features` ，选择 " **实验性 Web 平台功能**"，"已 **禁用** " 更改为 " **启用**"。  
1.  重启 Microsoft Edge。  

有关为双屏幕和可折叠设备增强网站 \ (或 app \ ) 的详细信息，请导航到 [CSS 媒体查询和 JavaScript Windows Segment 枚举 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]。  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="启用实验性 Web 平台功能标志" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   启用实验性 Web 平台功能标志  
:::image-end:::  

> [!NOTE]
> 如果你使用[CSS 媒体查询或 JavaScript Windows Segment 枚举 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]来增强你的网站或适用于[surface 双核][SurfaceDevicesDuo]的应用，你还必须在[Surface 双核][SurfaceDevicesDuo]设备上启用[Android Microsoft Edge 应用][GooglePlayMicrosoftEdge]中的**实验性 Web 平台功能**标志。
> 
> 如果在[桌面 Microsoft edge][MicrosoftEdge]中启用了实验性的**Web 平台功能**标志并在[Android microsoft edge 应用][GooglePlayMicrosoftEdge]中禁用该标志，则桌面 microsoft edge 中的 Surface 双核模拟器中的网站或应用的行为将与[Surface 双核][SurfaceDevicesDuo]上的[Android Microsoft edge 应用][GooglePlayMicrosoftEdge]不匹配。  确保标志在 Android 和桌面 Microsoft Edge 中匹配，以便在 [桌面 Microsoft edge][MicrosoftEdge]中成功使用 Surface 双核模拟器。  

#### 在折叠和双屏幕设备上进行测试  

当你在 Microsoft Edge 的双屏幕状态下模拟 [Surface 双核][SurfaceDevicesDuo] 时，将在你的网站或应用上绘制 **接缝** 。  

> [!NOTE]
> **接缝**是两个屏幕之间的空间。  

您的网站的模拟显示 (或应用 \ ) 是正确的表示形式。  它与[Surface 双核][SurfaceDevicesDuo]上的[Microsoft Edge Android 应用][GooglePlayMicrosoftEdge]中的显示相匹配。  更新内容，使其更好地沿着 **接缝**显示。  有关将您的网站 \ (或 app \ ) 调整到 **接缝**的详细信息，请导航到如何使用 Surface 双核文档中 [的接缝][DualScreenIntroductionHowWorkSeam] 。  

[设备工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport]具有其他功能，可帮助你在多个姿势和方向中测试你的网站或应用。  选择 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "，将视区旋转为横向方向。 将该功能与 **span** \ (![ span ][ImageSpanIcon] \ ) 组合在单个屏幕或折叠的姿势或已展开的屏幕或已展开的之间切换。  同时，这些功能支持在所有四种可能的姿势和方向中测试你的网站或应用。  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="双屏幕和折叠设备的姿势和方向的矩阵" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   双屏幕和折叠设备的姿势和方向的矩阵  
:::image-end:::  

 (ExperimentalApis \ ) 图标中的 **实验 Web 平台功能** \ " ![ ][ImageExperimentalApisIcon] 显示实验性 **web 平台功能** 标志的状态。  如果标志处于打开状态，则会突出显示该图标。  如果该标志已关闭，则不会突出显示该图标。  若要打开或关闭标志 ) 的 \ (或关闭，请选择图标或导航到 `edge://flags` 该标志并切换。  

#### 其他资源  
*   有关开发的详细信息，请导航到 [双屏幕 web 体验][DualScreenWebIndex]。  
*   安装 Surface 双核模拟器]。  它与 Microsoft Edge 中的仿真器不同。  它模拟运行 Android 的 Surface 双核并与 [Android Studio][AndroidDeveloperStudio]集成。  有关详细信息，请导航到 [获取 Surface 双核 SDK][DualScreenAndroidGetDuoSdk]。  

### 启用新的 CSS 网格调试功能  

在调试具有 CSS 网格布局的网站时，改善页面上的可视化效果。  你可以在 DevTools 设置中进一步自定义覆盖。  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="./media/experiments-grid.msft.png":::
   CSS 网格调试功能  
:::image-end:::  

若要预览最新实验功能，请完成以下操作。  

1.  在 " **实验** " 部分中，选择 "重新启动) 复选框后，在" **布局边栏 "窗格中 (配置选项" 下的 "启用新 CSS 网格调试功能 ** "。  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用支持以在面板之间移动选项卡  

通常，诸如 **元素** 和 **网络** 之类的工具可能仅在位于 DevTools 顶部的主面板中打开。  通常仅在位于 DevTools 底部的**抽屉**面板中打开的**3D 视图**和**问题**等工具。  选择实验后，您可以在顶部面板和底部面板之间移动工具。  若要移动工具，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **移到页首** " 或 " **移至底部**"。   此实验允许你自定义 DevTools 布局。  若要显示或隐藏 **抽屉** 面板，请选择 `Escape` 。  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="在面板之间移动选项卡" lightbox="./media/experiments-move-panels.msft.png":::
   在面板之间移动选项卡  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用 webhint  

[webhint][WebhintMain] 是一种开放源工具，可提供网站和本地网页的实时反馈。  [Webhint][WebhintMain]提供的反馈类型。  

*   辅助功能  
*   跨浏览器兼容性  
*   安全性  
*   性能  
*   PWA  
*   其他常见 web 开发问题  

[Webhint][WebhintMain]实验将在 "[问题][DevtoolsIssues]" 面板中显示 webhint 反馈。  选择一个问题以显示解决方案文档和您的网站上受影响的资源列表。  选择资源链接以打开 DevTools 中的相关 **网络**、 **源**或 **元素** 窗格。  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="./media/experiments-webhint.msft.png":::
   " **问题** " 面板中的 webhint 反馈  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用网络控制台  

**网络控制台** 是通过 HTTP 建立综合网络请求的实验的工作标题。  你可以使用 **网络控制台** 实验来发送 web API 请求。  

启用实验后，确保重新启动 DevTools。  若要使用 **网络控制台**，请使用以下步骤。    

1.  打开 " **网络** " 窗格。  
1.  查找要更改和重新发送的网络请求。  
1.  打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **编辑并重播**"。  
1.  当 **网络控制台** 打开时，请编辑网络请求信息。  
1.  选择 " **发送**"。  

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="控制台抽屉中的网络控制台" lightbox="./media/network-network-console.msft.png":::
   **控制台**抽屉中的**网络控制台**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用源订单查看器  

**源顺序查看器** 是显示页面源中的元素顺序的实验。  屏幕显示顺序可能与源的顺序不同，迷惑屏幕阅读器和键盘用户。  使用 **源顺序查看器** 实验查找屏幕显示顺序和源顺序之间的差异。  

启用实验后，确保重新启动 DevTools。  要使用源订单查看器，请执行以下操作：  

1.  打开 " **元素** " 窗格。  
1.  打开抽屉 \ (底部 \ ) 面板中的 " **辅助功能** " 窗格。  
1.  在 " **源顺序查看器** " 部分中，选中 " **显示源顺序** " 复选框。  
1.  突出显示任何 HTML 元素以显示页面源中顺序的覆盖图。  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text=""辅助功能" 窗格中的 "源顺序查看器"" lightbox="./media/experiments-source-order-viewer.msft.png":::
   "**辅助功能**" 窗格中的 "**源顺序查看器**"  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## 以前的实验功能  

*   [3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。  

## 提供有关实验功能的反馈  

提供有关 Microsoft Edge DevTools 实验的反馈或与 DevTools 相关的任何其他内容。  

*   使用 DevTools 中的 " **发送反馈** " 图标发送反馈  
*   向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的 "发送反馈" 图标" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools 中的 " **发送反馈** " 图标  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageRotateIcon]: ./media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ./media/span-dark-icon.msft.png  
[ImageExperimentalApisIcon]: ./media/experimental-apis-dark-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D 视图 |Microsoft 文档"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ./device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 |Microsoft Edge"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏幕 web 体验 |Microsoft 文档"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface 双核仿真器 |Microsoft 文档"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用双屏幕设备的接缝简介 |Microsoft 文档"  

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface 双核 |Microsoft Surface"  

[VisualstudioCode]: https://code.visualstudio.com "Microsoft Visual Studio 代码"  
[VisualstudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "适用于 Windows 的 Visual Studio 代码键盘快捷方式 |Microsoft Visual Studio 代码"  

[GitHubMicrosoftedgeMsedgeexplainerFoldables]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "在折叠设备上启发式体验的 Web 平台基元 |GitHub"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy 折页 |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
