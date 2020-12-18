---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 实验
ms.openlocfilehash: fbdeeb08599285a9cfa6edd467282cfbabbadd74
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232377"
---
# 实验功能  

Microsoft Edge DevTools 提供对仍处于开发中的实验性功能的访问权限。  您可以在发布每个 [功能之前](#providing-feedback-on-experimental-features) 进行测试并提供反馈。  

虽然实验功能在 Microsoft Edge 的所有频道中均可用，但您可以使用 Microsoft Edge Canary 渠道获取最新的实验功能。  

## 打开实验性功能  

若要在 Microsoft Edge 中 (\) 或关闭\) 实验功能，请完成以下步骤。  

1.  [打开 DevTools。][DevtoolsOpenMain]  
    *   选择 `Control` + `Shift` + `I` \ (Windows、Linux\) `Command` + `Option` + `I` 或 \ (macOS\) 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  打开 ["设置"][DevToolsCustomizeSettings] 窗格。  
    *   选择 `Shift` + `?` 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  在"设置"窗格的 **左侧，选择** " **实验"** 部分。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="../media/experiments-devtools.msft.png":::
       DevTools 设置中的实验 **列表**  
    :::image-end:::  
    
1.  在 **"实验** "页上，滚动浏览所有可用实验功能的列表，并选中要测试的每个功能旁边的复选框。  
1.  关闭并重新打开 Microsoft Edge DevTools。  
    
> [!NOTE]
> 实验性功能会不断更新，并且可能会导致性能问题。  若要关闭实验功能，请打开"实验 **"页并** 清除要关闭的实验功能复选框。  

## 突出显示的实验功能  

以下各节介绍 Microsoft Edge 中提供的新实验功能。  

| 实验性功能 | Microsoft Edge 版本 |  
|:--- |:--- |  
| [模拟：支持双屏幕模式](#emulation-support-dual-screen-mode) | 84 或更高版本 |  
| [启用新的 CSS 网格调试功能](#enable-new-css-grid-debugging-features) | 85 或更高版本 |  
| [支持在面板之间移动选项卡](#enable-support-to-move-tabs-between-panels) | 85 或更高版本 |  
| [启用 Webhint](#enable-webhint) | 85 或更高版本 |  
| [启用网络控制台](#enable-network-console) | 85 或更高版本 |  
| [源订单查看器](#source-order-viewer) | 86 或更高版本 |  
| [启用键盘快捷方式编辑器](#enable-keyboard-shortcut-editor) | 87 或更高版本 |  
| [在 3D 视图中打开复合层](#turn-on-composited-layers-in-3d-view) | 87 或更高版本 |  

### 模拟：支持双屏幕模式  

提供在 Microsoft Edge 中模拟两个新的双屏幕和可折叠设备的其他功能。  

*   [Surface Duo][SurfaceDevicesDuo]  
*   [三星百合][SamsungMobileGalaxyFold]  
    
模拟设备，并切换以下状态。  

*   单屏或折叠状态  
*   双屏或展开状态  
    
启用实验性 Web 平台[API，](#enable-experimental-apis)并使用[CSS 媒体][DualScreenDocsCssMedia]屏幕跨越功能以及[JavaScript getWindowSegments API][DualScreenDocsJSAPI]增强适用于双屏幕和可折叠设备的网站 \ (或 app\) 。  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="在 Microsoft Edge 中模拟 Surface Duo" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   在 Microsoft Edge 中模拟 Surface Duo  
:::image-end:::  

#### 启用实验性 API  

若要使用 [CSS 媒体屏幕跨越][DualScreenDocsCssMedia] 功能以及 [JavaScript getWindowSegments API，][DualScreenDocsJSAPI]请打开 `Experimental Web Platform features` Microsoft Edge 中的标志。  完成以下步骤。  

1.  导航到 `edge://flags` 。  
1.  在搜索**标志**文本框中，输入 `Experimental Web Platform features` 、选择实验**Web 平台功能**标志，然后更改为 **"已禁用"。** ****  
1.  重启 Microsoft Edge。  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="启用实验性 Web 平台功能标志" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   启用实验性 Web 平台功能标志  
:::image-end:::  

> [!NOTE]
> 如果你使用[CSS][DualScreenDocsCssMedia]媒体查询或[JavaScript Windows 段枚举 API][DualScreenDocsJSAPI]增强[Surface Duo][SurfaceDevicesDuo]的网站或应用，则还必须在[Surface Duo][SurfaceDevicesDuo]设备上的[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用中启用实验性**Web**平台功能标志。  
> 
> 如果在桌面[Microsoft Edge][MicrosoftEdge]中启用实验性**Web**平台功能标志，并且在 Android [Microsoft Edge][GooglePlayMicrosoftEdge]应用中禁用，则桌面 Microsoft Edge 的 Surface Duo 模拟器中的网站或应用的行为与[Surface Duo][SurfaceDevicesDuo]上的[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用不匹配。  确保标志在 Android 和桌面版 Microsoft Edge 之间匹配，以在桌面版 Microsoft Edge 中成功使用 Surface Duo [仿真器][MicrosoftEdge]。  

#### 在可折叠和双屏幕设备上测试  

当你在 Microsoft Edge 中模拟双屏幕状态中的 [Surface Duo][SurfaceDevicesDuo] 时，两个屏幕之间的 (\) 将绘制在网站或应用上。  

模拟显示与您的网站 \ (或 app\) 在 Surface Duo 上运行的 Microsoft [Edge Android][GooglePlayMicrosoftEdge] 应用中的呈现 [方式相匹配][SurfaceDevicesDuo]。  你可能需要更新网站 \ (或 app\) ，以更好地显示网站。  若要详细了解如何调整网站 \ (或 app\) 以适应变化，请导航到"如何使用[此目录"。][DualScreenIntroductionHowWorkSeam]  

设备 [工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport] 具有其他功能，可帮助你以多种状态和方向测试网站或应用。  Choose **Rotate** \ (![ Rotate ][ImageRotateIcon] \) to rotate the viewport to landscape orientation. 将此功能与 **Span** \ (Span \) 相结合，以在单屏或折叠、双屏或展开状态 ![ ][ImageSpanIcon] 之间进行切换。  这些功能共同支持在所有四种可能状态和方向中测试网站或应用。  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="双屏幕和可折叠设备状态和方向的矩阵" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   双屏幕和可折叠设备状态和方向的矩阵  
:::image-end:::  

实验 **Web 平台功能** \ (![ ExperimentalApis \) 图标显示实验 Web ][ImageExperimentalApisIcon] **平台功能标志** 的状态。  如果此标志已打开，则突出显示该图标。  如果关闭标志，则不突出显示图标。  若要打开 \ (或关闭\) ，请导航到并 `edge://flags` 切换该标志。  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

下面是可帮助您增强双屏幕设备的网站 \ (或 app\) 的其他资源。  

*   有关在双屏设备上进行 Web 开发的信息，请导航到 [双屏幕 Web 体验][DualScreenWebIndex]。  
*   安装 [Surface Duo 仿真器][DualScreenAndroidUseEmulator]。  它不同于 Microsoft Edge 中的仿真器，模拟运行 Android 的 Surface Duo，并且与 [Android Studio 集成][AndroidDeveloperStudio]。  有关详细信息，请导航到["获取 Surface Duo SDK"。][DualScreenAndroidGetDuoSdk]  
    
> [!NOTE]
> 以下是当前已知问题的列表。  
> 
> *   当使用 [Microsoft 远程桌面客户端][RemoteDesktopClientDocs] 连接到远程电脑并模拟 Surface [Duo][SurfaceDevicesDuo] 或 [Samsung 一][SamsungMobileGalaxyFold]起折叠时，指针可能会抖动或抖动。  如果遇到问题，请 [发送反馈](#providing-feedback-on-experimental-features)。  

### 启用新的 CSS 网格调试功能  

此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS 网格布局。  若要预览最新的实验功能，请 [启用此实验](#turn-on-experimental-features) 并重新加载 DevTools。  此实验在 Microsoft Edge 版本 87 或更高版本中默认处于打开状态。  

#### 使用"检查"工具查看悬停网格覆盖  

检查 **工具** 提供了一种快速方法，通过将鼠标悬停在网站中的 CSS 网格布局上来标识和可视化这些布局。  选择**** ![ DevTools (左上角的"检查) 检查 \) ][ImageInspectIcon] 图标。  然后，将鼠标悬停在要调试的网站上 Grid 元素上。  边框显示在网格周围，底纹表示网格间隙的位置（如果存在）。  

:::image type="complex" source="../media/grid-inspect.msft.png" alt-text="使用"检查"工具查看网格" lightbox="../media/grid-inspect.msft.png":::
   使用"检查"工具 **查看** 网格  
:::image-end:::  

#### 查看持久网格覆盖  

在 Microsoft Edge 版本 86 或更高版本中，实验 CSS 网格功能还提供了启用持久网格覆盖的选项。  永久性覆盖具有多个优势。  

*   滚动、移动鼠标并使用 DevTools 的其他功能时，永久性覆盖在页面上仍然可见。  
*   可以同时启用多个永久性覆盖，从而允许您一次查看多个网格布局。  
*   永久性覆盖提供了许多配置选项，例如隐藏或显示网格区域中的名称、网格间隙、跟踪大小等。  
    
切换持久网格覆盖的两种方法。  

*   选择 **"元素"** 工具的 DOM 树中显示的任何 Grid 元素旁边的" **网格"椭圆** 图标。  
    
    :::image type="complex" source="../media/grid-adorner.msft.png" alt-text="元素工具中的网格椭圆图标" lightbox="../media/grid-adorner.msft.png":::
       元素工具中的 **网格** 椭圆图标  
    :::image-end:::  
    
*   打开位于 **"元素** "工具中的新布局面板，并选中要突出显示的每个 Grid 元素旁边的复选框。  
    
    :::image type="complex" source="../media/grid-layout-zoom.msft.png" alt-text="DevTools 中的布局面板" lightbox="../media/grid-layout-zoom.msft.png":::
       **** DevTools 中的布局面板  
    :::image-end:::  
    
#### 配置永久性覆盖  

在 Microsoft Edge 版本 86**** 或更高版本中，新的布局面板位于 **"** 元素"工具**** 中的"样式"和"**计算"选项卡**旁边。  布局 **面板** 显示持久覆盖的配置选项。  

:::image type="complex" source="../media/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../media/experiments-grid.msft.png":::
   CSS 网格调试功能  
:::image-end:::  

### 支持在面板之间移动选项卡  

通常，元素和网络等工具**** 只能在位于**** DevTools 顶部的主面板中打开。  工具（**如 3D**视图和问题）通常仅在位于**** DevTools 底部的"箱"面板中打开。 ****  选择实验后，您可以在顶部和底部面板之间移动工具。  若要移动工具，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击\) ，然后选择"移动到顶部"或"**** 移动到**底部"。**   此实验允许你自定义 DevTools 布局。  若要显示或隐藏 **"箱"** 面板，请选择 `Escape` 。  

:::image type="complex" source="../media/experiments-move-panels.msft.png" alt-text="在面板之间移动选项卡" lightbox="../media/experiments-move-panels.msft.png":::
   在面板之间移动选项卡  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用 Webhint  

[webhint][WebhintMain] 是一个开源工具，可为网站和本地网页提供实时反馈。  Webhint 提供 [的反馈类型][WebhintMain]。  

*   辅助功能  
*   跨浏览器兼容性  
*   安全性  
*   性能  
*   渐进式 Web (PBA)   
*   其他常见的 Web 开发问题  
    
[Webhint 实验][WebhintMain]在"问题"面板中显示[Webhint][DevtoolsIssues]反馈。  选择一个问题，在网站上显示解决方案文档和受影响资源列表。  选择资源链接以在 DevTools******中**打开**相关的"** 网络、源"或"元素"窗格。  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../media/experiments-webhint.msft.png":::
   问题面板中的 webhint**反馈**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用网络控制台  

**网络控制台** 是通过 HTTP 进行综合网络请求的实验的工作主题。  可以使用网络 **控制台** 实验发送 Web API 请求。  

启用实验后，请确保重新启动 DevTools。  若要使用 **网络控制台**，请完成以下步骤。  

1.  打开 **"网络"** 窗格。  
1.  查找要更改和重新发送的网络请求。  
1.  打开上下文菜单 \ (右键单击\) ，然后选择"编辑**和重播"。**  
1.  当网络 **控制台打开** 时，编辑网络请求信息。  
1.  选择 **"发送"。**  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="控制台箱中的网络控制台" lightbox="../media/network-network-console.msft.png":::
   **控制台箱****中的网络控制台**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 源订单查看器  

**源顺序查看器** 是显示页面源中元素顺序的实验。  屏幕显示顺序可能与源的顺序不同，这会使屏幕阅读器和键盘用户混淆。  使用 **源订单查看器** 实验可查找屏幕显示顺序和源顺序之间的差异。  

启用实验后，请确保重新启动 DevTools。  若要使用 **源订单查看器**，请完成以下步骤。  

1.  打开 **"元素"** 窗格。  
1.  打开 **"下角** "\ (面板中的"辅助功能) 窗格。  
1.  在" **源订单查看器"** 部分下，选中" **显示源订单"** 复选框。  
1.  突出显示任何 HTML 元素以显示页面源中顺序的覆盖。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="辅助功能窗格中的源订单查看器" lightbox="../media/experiments-source-order-viewer.msft.png":::
   **辅助功能窗格中**的**源订单查看器**  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### 启用键盘快捷方式编辑器

打开 **"启用键盘** 快捷方式编辑器"实验后，你现在可以自定义 DevTools 中任何动作的键盘快捷方式。  若要为特定操作自定义键盘快捷方式，请完成以下步骤。  

1.  [打开 DevTools。][DevtoolsOpenMain]  
1.  打开["设置"。][DevToolsCustomizeSettings]
    *   选择 `Shift` + `?` 。  
1.  导航到 **"快捷方式"** 页。  
1.  选择要自定义的操作。  
1.  选择 **编辑** \ (![ EditKeyboardShortcut ][ImageEditKeyboardShortcutIcon] \) 图标。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="从"设置"中的"快捷方式"页选择要自定义的操作" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       从"设置"中的"快捷方式 **"** 页选择要自定义 [的操作][DevToolsCustomizeSettings]
    :::image-end:::  
    
1.  在键盘上，选择要绑定到该操作的键。
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="选择要分配给该操作的键" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择要分配给该操作的键
    :::image-end:::  
    
1.  若要保存新的键盘快捷方式，请选择选中标记 \ (![CheckmarkKeyboardShortcut][ImageCheckmarkKeyboardShortcutIcon]\) 图标。
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="选择选中标记图标以保存新的键盘快捷方式" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择选中标记图标以保存新的键盘快捷方式
    :::image-end:::  
    
1.  选择新的键盘快捷方式以在 DevTools 中触发该操作。  
    
在 **"快捷方式"** 页上，自定义键盘快捷方式 **\ (** ![ CustomKeyboardShortcut ][ImageCustomKeyboardShortcutIcon] \) 图标显示已自定义的键盘快捷方式。  若要重置所有快捷方式，请选择"**还原默认快捷方式"。**  

编辑操作键盘快捷方式时，若要放弃所做的更改，请选择 X \ (![ XKeyboardShortcut ][ImageXKeyboardShortcutIcon] \) 图标。  若要删除特定操作快捷方式，请选择"删除"快捷方式 **\ (** ![ DeleteKeyboardShortcut ][ImageDeleteKeyboardShortcutIcon] \) 图标。  若要为操作添加多个快捷方式，请选择"**添加快捷方式"。**

> [!NOTE]
> 如果键盘快捷方式当前已分配给另一个操作，则不能将其保存以用于新操作。  必须先删除上一个操作键盘快捷方式，然后将其添加到新操作。  

<!--Available in Microsoft Edge version 87 and later.  -->

### 在 3D 视图中打开复合层

现在，您可以可视化 Z 索引和文档对象模型 \ (DOM\) 。  此功能可帮助您在不经常切换上下文的情况下进行调试。  您确定减少上下文切换是一个主要的难点。  您编写的代码对 Web 应用有何影响并不总是很明显。  为获得全面的视觉调试体验， 已将3D 视图和复合层组合到一起。  启用实验后，请确保重新启动 DevTools。  若要使用 **复合层**，请完成以下步骤。  

1.  在箱中，选择 **3D 视图** 工具。  
1.  打开 **"复合层"** 窗格。  
1.  将显示应用的所有绘制图层。  使用你自己的 Web 应用试用此功能。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   **复合层** 窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

## 以前的实验功能  

*   [3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本 83 或更高版本中默认处于打开状态。  
*   [自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在可用，在 Microsoft Edge 版本 86 或更高版本中默认处于打开状态。  

## 提供有关实验性功能的反馈  

提供有关 Microsoft Edge DevTools 实验或与 DevTools 相关的任何其他内容的反馈。  

*   使用 DevTools 中的 **"发送反馈** "图标发送反馈  
*   向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文  

:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools 中的“**发送反馈**”图标  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageCheckmarkKeyboardShortcutIcon]: ../media/checkmark-keyboard-shortcut-icon.msft.png  
[ImageCustomKeyboardShortcutIcon]: ../media/custom-keyboard-shortcut-icon.msft.png  
[ImageDeleteKeyboardShortcutIcon]: ../media/delete-keyboard-shortcut-icon.msft.png  
[ImageEditKeyboardShortcutIcon]: ../media/edit-keyboard-shortcut-icon.msft.png  
[ImageExperimentalApisIcon]: ../media/experimental-apis-dark-icon.msft.png  
[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ../media/span-dark-icon.msft.png  
[ImageXKeyboardShortcutIcon]: ../media/discard-changes-keyboard-shortcut-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D 视图 | Microsoft Docs"  
[DevToolsCustomizeSettings]: ../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 |Microsoft Edge"  
[DevtoolsIssues]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "在 Microsoft Edge DevTools 中自定义键盘快捷方式 |Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏 Web 体验 |Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo 仿真器 |Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏设备简介 |Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 仿真器 |Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "用于双屏幕检测的 CSS 媒体屏幕跨越功能 |Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端 |Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "百分百 |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
