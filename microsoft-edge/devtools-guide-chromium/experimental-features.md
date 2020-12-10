---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: b2b2e591834f1c75d51ec98523e2752d67a2d354
ms.sourcegitcommit: 6571bcc0b7f1c4c9d6ead65081374bab87cd4469
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203897"
---
# 实验功能  

Microsoft Edge DevTools 提供对仍在开发中的实验功能的访问权限。  你可以在发布每个功能之前测试和 [提供反馈](#providing-feedback-on-experimental-features) 。  

尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。  

## 启用实验功能  

若要在 Microsoft Edge 中打开 " (" 或 "关闭" ) 实验功能，请完成以下步骤。  

1.  [打开 DevTools][DevtoolsOpen]。  
    *   选择 `Control` + `Shift` + `I` \ (Windows、Linux \ ) 或 `Command` + `Option` + `I` \ (macOS \ ) 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  打开 " [设置][DevToolsCustomizeSettings] " 窗格。  
    *   选择 `Shift` + `?` 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  在 " **设置** " 窗格的左侧，选择 " **实验** " 部分。  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.msft.png":::
       DevTools**设置**中的实验列表  
    :::image-end:::  
    
1.  在 " **实验** " 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。  
1.  关闭并重新打开 Microsoft Edge DevTools。  
    
> [!NOTE]
> 实验性功能将不断更新，并可能导致性能问题。  若要关闭实验功能，请打开 " **试验** " 页面，然后清除要关闭的实验功能的复选框。  

## 突出显示实验功能  

以下部分介绍 Microsoft Edge 中可用的新实验功能。  

| 实验性功能 | Microsoft Edge 版本 |  
|:--- |:--- |  
| [仿真：支持双重屏幕模式](#emulation-support-dual-screen-mode) | 84或更高版本 |  
| [启用新的 CSS 网格调试功能](#enable-new-css-grid-debugging-features) | 85或更高版本 |  
| [启用支持以在面板之间移动选项卡](#enable-support-to-move-tabs-between-panels) | 85或更高版本 |  
| [启用 webhint](#enable-webhint) | 85或更高版本 |  
| [启用网络控制台](#enable-network-console) | 85或更高版本 |  
| [源订单查看器](#source-order-viewer) | 86或更高版本 |  
| [启用键盘快捷方式编辑器](#enable-keyboard-shortcut-editor) | 87或更高版本 |  
| [在3D 视图中打开复合图层](#turn-on-composited-layers-in-3d-view) | 87或更高版本 |  

### 仿真：支持双重屏幕模式  

提供用于模拟 Microsoft Edge 中的两个新的双屏幕和可折叠设备的附加功能。  

*   [Surface 双核][SurfaceDevicesDuo]  
*   [Samsung Galaxy 折页][SamsungMobileGalaxyFold]  
    
模拟设备并在以下姿势之间切换。  

*   单屏幕或折叠的状况  
*   双屏幕或展开的状况  
    
[启用实验性 Web 平台 api](#enable-experimental-apis) 并使用 [CSS 媒体屏幕生成功能][DualScreenDocsCssMedia] 和 [JavaScript getWindowSegments API][DualScreenDocsJSAPI] 来增强您的网站 \ (或适用于双屏幕和可折叠设备的应用 \ ) 。  

:::image type="complex" source="./media/experiments-surface-duo-emulation.msft.png" alt-text="在 Microsoft Edge 中模拟 Surface 双核" lightbox="./media/experiments-surface-duo-emulation.msft.png":::  
   在 Microsoft Edge 中模拟 Surface 双核  
:::image-end:::  

#### 启用实验性 Api  

若要使用 [CSS 媒体屏幕生成功能][DualScreenDocsCssMedia] 和 [JavaScript getWindowSegments API][DualScreenDocsJSAPI]，请打开 `Experimental Web Platform features` Microsoft Edge 中的标志。  完成以下步骤。  

1.  导航到 `edge://flags` 。  
1.  在 " **搜索标志** " 文本框中，输入 `Experimental Web Platform features` ，选择实验性的 **Web 平台功能** 标志，将 " **已禁用** " 更改为 " **已启用**"。  
1.  重启 Microsoft Edge。  
    
:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="启用实验性 Web 平台功能标志" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   启用实验性 Web 平台功能标志  
:::image-end:::  

> [!NOTE]
> 如果你使用[CSS 媒体查询][DualScreenDocsCssMedia]或[JavaScript WINDOWS Segment 枚举 API][DualScreenDocsJSAPI]来增强你的网站或适用于[surface 双核][SurfaceDevicesDuo]的应用，你还必须在[Surface 双核][SurfaceDevicesDuo]设备上启用[Android Microsoft Edge 应用][GooglePlayMicrosoftEdge]中的**实验性 Web 平台功能**标志。  
> 
> 如果在[桌面 Microsoft edge][MicrosoftEdge]中启用了实验性的**Web 平台功能**标志，并且在[Android microsoft edge 应用][GooglePlayMicrosoftEdge]中禁用了该标志，则桌面 microsoft edge 中的 Surface 双核模拟器中的网站或应用的行为与[Surface 双核][SurfaceDevicesDuo]上的[Android Microsoft edge 应用][GooglePlayMicrosoftEdge]不匹配。  确保标志在 Android 和桌面 Microsoft Edge 中匹配，以便在 [桌面 Microsoft edge][MicrosoftEdge]中成功使用 Surface 双核模拟器。  

#### 在折叠和双屏幕设备上进行测试  

当您在 Microsoft Edge 的双屏幕状态下模拟 [Surface 双核][SurfaceDevicesDuo] 时，接缝 \ (在您的网站或应用上绘制的两个屏幕 ) 之间的空间。  

仿真显示与在[Surface 双核][SurfaceDevicesDuo]上运行的[Microsoft Edge Android 应用][GooglePlayMicrosoftEdge]中呈现的你的网站 \ (或应用 \ ) 的方式相匹配。  您可能需要更新您的网站 \ (或应用 \ ) ，以便更好地沿接缝显示。  有关将您的网站 \ (或 app \ ) 调整到接缝的详细信息，请导航到 " [如何处理接缝][DualScreenIntroductionHowWorkSeam]"。  

[设备工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport]具有其他功能，可帮助你在多个姿势和方向中测试你的网站或应用。  选择 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "，将视区旋转为横向方向。 将该功能与 **span** \ (![ span ][ImageSpanIcon] \ ) 组合在单个屏幕或折叠的姿势或已展开的屏幕或已展开的之间切换。  同时，这些功能支持在所有四种可能的姿势和方向中测试你的网站或应用。  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="双屏幕和折叠设备的姿势和方向的矩阵" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   双屏幕和折叠设备的姿势和方向的矩阵  
:::image-end:::  

 (ExperimentalApis \ ) 图标中的 **实验 Web 平台功能** \ " ![ ][ImageExperimentalApisIcon] 显示实验性 **web 平台功能** 标志的状态。  如果标志处于打开状态，则会突出显示该图标。  如果该标志已关闭，则不会突出显示该图标。  若要打开 " (" 或 "关闭" ) 标志，请导航到 `edge://flags` "标志" 并切换。  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

下面是可帮助你增强网站的其他资源 (或适用于双屏幕设备的应用 \ ) 。  

*   有关在双屏幕设备上进行 web 开发的详细信息，请导航到 [双屏幕 web 体验][DualScreenWebIndex]。  
*   安装 [Surface 双核模拟器][DualScreenAndroidUseEmulator]。  它与 Microsoft Edge 中的仿真器不同，模拟运行 Android 的 Surface 双核，并与 [Android Studio][AndroidDeveloperStudio]集成。  有关详细信息，请导航到 [获取 Surface 双核 SDK][DualScreenAndroidGetDuoSdk]。  
    
> [!NOTE]
> 以下是当前已知问题的列表。  
> 
> *   当使用 [Microsoft 远程桌面客户端][RemoteDesktopClientDocs] 连接到远程电脑并模拟 [Surface 双核][SurfaceDevicesDuo] 或 [Samsung Galaxy 折页][SamsungMobileGalaxyFold]时，指针可能会晃动或断断续续。  如果遇到问题，请 [发送反馈](#providing-feedback-on-experimental-features)。  

### 启用新的 CSS 网格调试功能  

此实验功能提供了许多新的可视化效果，可帮助你调试 CSS 网格布局。  若要预览最新实验功能，请 [启用此实验](#turn-on-experimental-features) 并重新加载 DevTools。  此体验默认情况下在 Microsoft Edge 版本87或更高版本中打开。  

#### 利用 "检查" 工具查看悬停的网格重叠  

" **检查** " 工具提供了一种通过鼠标悬停在网站中来标识和可视化 CSS 网格布局的快速方法。  选择 DevTools 左上角的 " **检查** \ (![ 检查 ](./media/inspect-icon.msft.png) \ ) " 图标。  然后，将鼠标悬停在正在调试的网站上的网格元素上。  大纲显示在网格周围，阴影指示网格间隙的位置（如果存在）。  

:::image type="complex" source="./media/grid-inspect.msft.png" alt-text="通过 "检查" 工具查看网格" lightbox="./media/grid-inspect.msft.png":::
   通过 "检查" 工具查看网格  
:::image-end:::  

#### 查看永久网格覆盖  

在 Microsoft Edge 版本86或更高版本中，实验性 CSS 网格功能还提供了启用持久网格覆盖的选项。  永久性覆盖提供多项好处。  

*   滚动、移动鼠标和使用 DevTools 的其他功能时，永久叠加在页面上保持可见。  
*   可以同时启用多个永久覆盖，从而允许同时查看多个网格布局。  
*   永久覆盖提供许多配置选项，如在网格区域中隐藏或显示名称、网格间隙、轨道大小等。  
    
切换永久网格覆盖的两种方式。  

*   选择 "**元素**" 工具的 DOM 树中显示的任何网格元素旁边的 "**网格**" 椭圆图标。  
    
    :::image type="complex" source="./media/grid-adorner.msft.png" alt-text=""元素" 工具中的 "网格椭圆" 图标" lightbox="./media/grid-adorner.msft.png":::
       " **元素** " 工具中的 "网格椭圆" 图标  
    :::image-end:::  
    
*   打开位于 "元素" 工具中的新 **版式** 面板，然后选择要突出显示的每个网格元素旁边的复选框。  
    
    :::image type="complex" source="./media/grid-layout-zoom.msft.png" alt-text="DevTools 中的版式面板" lightbox="./media/grid-layout-zoom.msft.png":::
       DevTools 中的**版式**面板  
    :::image-end:::  
    
#### 配置永久重叠  

在 Microsoft Edge 版本86或更高版本中，新的 **版式** 面板位于 " **元素** " 工具中和 " **样式** " 和 " **计算** " 选项卡旁边。  " **布局** " 面板图面为永久叠加的配置选项。  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="./media/experiments-grid.msft.png":::
   CSS 网格调试功能  
:::image-end:::  

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
*    (PWAs) 的渐进式 Web 应用  
*   其他常见 web 开发问题  
    
[Webhint][WebhintMain]实验将在 "[问题][DevtoolsIssues]" 面板中显示 webhint 反馈。  选择一个问题以显示解决方案文档和您的网站上受影响的资源列表。  选择资源链接以打开 DevTools 中的相关 **网络**、 **源**或 **元素** 窗格。  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="./media/experiments-webhint.msft.png":::
   " **问题** " 面板中的 webhint 反馈  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用网络控制台  

**网络控制台** 是通过 HTTP 建立综合网络请求的实验的工作标题。  你可以使用 **网络控制台** 实验来发送 web API 请求。  

启用实验后，确保重新启动 DevTools。  若要使用 **网络控制台**，请完成以下步骤。  

1.  打开 " **网络** " 窗格。  
1.  查找要更改和重新发送的网络请求。  
1.  打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **编辑并重播**"。  
1.  当 **网络控制台** 打开时，请编辑网络请求信息。  
1.  选择 " **发送**"。  
    
:::image type="complex" source="./media/network-network-console.msft.png" alt-text="控制台抽屉中的网络控制台" lightbox="./media/network-network-console.msft.png":::
   **控制台**抽屉中的**网络控制台**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 源订单查看器  

**源顺序查看器** 是显示页面源中的元素顺序的实验。  屏幕显示顺序可能与源的顺序不同，迷惑屏幕阅读器和键盘用户。  使用 **源顺序查看器** 实验查找屏幕显示顺序和源顺序之间的差异。  

启用实验后，确保重新启动 DevTools。  若要使用 " **源顺序查看器**"，请完成以下步骤。  

1.  打开 " **元素** " 窗格。  
1.  打开抽屉 \ (底部 \ ) 面板中的 " **辅助功能** " 窗格。  
1.  在 " **源顺序查看器** " 部分下，选择 " **显示源顺序** " 复选框。  
1.  突出显示任何 HTML 元素以显示页面源中顺序的覆盖图。  
    
:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text=""辅助功能" 窗格中的 "源顺序查看器"" lightbox="./media/experiments-source-order-viewer.msft.png":::
   "**辅助功能**" 窗格中的 "**源顺序查看器**"  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### 启用键盘快捷方式编辑器

启用 " **启用键盘快捷方式编辑器** " 实验后，您现在可以自定义 DevTools 中任何操作的键盘快捷方式。  若要自定义特定操作的键盘快捷方式，请完成以下步骤。  

1.  [打开 DevTools][DevtoolsOpenMain]。  
1.  打开 " [设置][DevToolsCustomizeSettings]"。
    *   选择 `Shift` + `?` 。  
1.  导航到 " **快捷方式** " 页面。  
1.  选择要自定义的操作。  
1.  选择 " **编辑** \ (![ EditKeyboardShortcut ][ImageEditKeyboardShortcutIcon] \ ) " 图标。  
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="从 "设置" 中的 "快捷方式" 页面选择要自定义的操作" lightbox="./media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       从 "[设置][DevToolsCustomizeSettings]" 中的 "**快捷方式**" 页面选择要自定义的操作
    :::image-end:::  
    
1.  在键盘上，选择要绑定到操作的键。
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="选择要分配给操作的键" lightbox="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择要分配给操作的键
    :::image-end:::  
    
1.  若要保存新的键盘快捷方式，请选择 "选中标记 \ (![CheckmarkKeyboardShortcut][ImageCheckmarkKeyboardShortcutIcon]\ ) 图标。
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="选择复选标记图标以保存新的键盘快捷方式" lightbox="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择复选标记图标以保存新的键盘快捷方式
    :::image-end:::  
    
1.  选择新的键盘快捷方式以触发 DevTools 中的操作。  
    
在 " **快捷方式** " 页面上， **自定义键盘快捷方式** \ (![ CustomKeyboardShortcut ][ImageCustomKeyboardShortcutIcon] \ ) 图标显示已自定义的键盘快捷方式。  若要重置所有快捷方式，请选择 " **还原默认快捷方式**"。  

在编辑操作的键盘快捷方式时，若要放弃所做的更改，请选择 "X (![ XKeyboardShortcut ][ImageXKeyboardShortcutIcon] \ ) " 图标。  若要删除特定操作的快捷方式，请选择 " **删除快捷方式** \ (![ DeleteKeyboardShortcut ][ImageDeleteKeyboardShortcutIcon] \ ) " 图标。  若要为操作添加多个快捷方式，请选择 " **添加快捷方式**"。

> [!NOTE]
> 如果键盘快捷方式当前已分配给另一个操作，您将无法保存它以执行新操作。  必须先删除上一个操作的键盘快捷方式，然后再将其添加到新操作。  

<!--Available in Microsoft Edge version 87 and later.  -->

### 在3D 视图中打开复合图层

现在，你可以在 z 索引和文档对象模型 \ (DOM \ ) 中可视化层。  此功能可帮助你在不切换上下文的情况下进行调试。  您发现减少上下文切换是一个主要难点。  你编写的代码对你的 web 应用的影响并非总是很清楚。  为了获得全面的可视化调试体验，现在组合了3D 视图和复合图层。  启用实验后，确保重新启动 DevTools。  若要使用 **合成图层**，请完成以下步骤。  

1.  在抽屉上，选择 " **3D 视图** " 工具。  
1.  打开 " **复合图层** " 窗格。  
1.  将显示应用的所有已绘制的图层。  在你自己的 web 应用中试用此功能。  
    
:::image type="complex" source="./media/experiments-layers.msft.png" alt-text=""复合图层" 窗格" lightbox="./media/experiments-layers.msft.png":::
   "**复合图层**" 窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

## 以前的实验功能  

*   [3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。  
*   [自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在在 Microsoft Edge 版本86或更高版本中可用且默认情况下处于打开状态。  

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
[ImageEditKeyboardShortcutIcon]: ./media/edit-keyboard-shortcut-icon.msft.png  
[ImageCheckmarkKeyboardShortcutIcon]: ./media/checkmark-keyboard-shortcut-icon.msft.png  
[ImageCustomKeyboardShortcutIcon]: ./media/custom-keyboard-shortcut-icon.msft.png  
[ImageDeleteKeyboardShortcutIcon]: ./media/delete-keyboard-shortcut-icon.msft.png  
[ImageXKeyboardShortcutIcon]: ./media/discard-changes-keyboard-shortcut-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D 视图 |Microsoft 文档"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ./device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 |Microsoft Edge"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpenMain]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏幕 web 体验 |Microsoft 文档"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface 双核仿真器 |Microsoft 文档"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用双屏幕设备的接缝简介 |Microsoft 文档"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface 双核仿真器 |Microsoft 文档"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "适用于双屏幕检测的 CSS 媒体屏幕扩展功能 |Microsoft 文档"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft 文档"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端 |Microsoft 文档"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface 双核 |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy 折页 |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
