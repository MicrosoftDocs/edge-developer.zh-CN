---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 实验
ms.openlocfilehash: 018364d4debc1791685a028c337f61f85865ef6b
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313041"
---
# 实验功能  

Microsoft Edge DevTools 提供对仍处于开发中的实验性功能的访问权限。  您可以在发布每个 [功能之前](#providing-feedback-on-experimental-features) 进行测试并提供反馈。  

虽然实验功能在 Microsoft Edge 的所有频道中均可用，但您可以使用 Microsoft Edge Canary 渠道获取最新的实验功能。  

## 打开实验性功能  

若要在 Microsoft Edge 中 (\) 或关闭\) 实验功能，请完成以下步骤。  

1.  [打开 DevTools。][DevtoolsOpenMain]  
    *   选择 `Control` + `Shift` + `I` \ (Windows、Linux\) `Command` + `Option` + `I` 或 \ (macOS\) 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  打开 ["设置"][DevToolsCustomizeIndexSettings] 窗格。  
    *   选择 `Shift` + `?` 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  在"设置"窗格的 **左侧，选择** "实验 **"** 部分。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text=""设置"中的"实验"页" lightbox="../media/experiments-devtools.msft.png":::
       " **设置"** 中的"实验 **"页**  
    :::image-end:::  
    
1.  在 **"实验** "页上，滚动浏览所有可用实验功能的列表，并选中要测试的每个功能旁边的复选框。  
1.  关闭并重新打开 Microsoft Edge DevTools。  
    
> [!NOTE]
> 实验性功能会不断更新，并且可能会导致性能问题。  若要关闭实验功能，请打开"实验 **"页并** 清除要关闭的实验功能复选框。  

## 突出显示的实验功能  

以下各节介绍 Microsoft Edge 中提供的新实验功能。  

| 实验功能 | Microsoft Edge 版本 |  
|:--- |:--- |  
| [启用 Webhint](#enable-webhint) | 85 或更高版本 |  
| [启用网络控制台](#enable-network-console) | 85 或更高版本 |  
| [源订单查看器](#source-order-viewer) | 86 或更高版本 |  
| [启用键盘快捷方式编辑器](#enable-keyboard-shortcut-editor) | 87 或更高版本 |  
| [在 3D 视图中启用复合层](#enable-composited-layers-in-3d-view) | 87 或更高版本 |  
| [在"样式"窗格中启用新的字体编辑器工具](#) | 89 或更高版本 |  
| [启用新的 CSS Flexbox 调试功能](#enable-new-css-flexbox-debugging-features) | 89 或更高版本 |  
| [启用 + 按钮选项卡菜单以打开更多工具](#enable--button-tab-menus-to-open-more-tools) | 89 或更高版本 |  
| [启用欢迎选项卡](#enable-welcome-tool) | 89 或更高版本 |  

### 启用新的 CSS 网格调试功能  

此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS 网格布局。  若要预览最新的实验功能，请 [启用此实验](#turn-on-experimental-features) 并重新加载 DevTools。  此实验在 Microsoft Edge 版本 87 或更高版本中默认处于打开状态。  

#### 使用"检查"工具查看悬停网格覆盖  

检查 **工具** 提供了一种快速方法，通过将鼠标悬停在网站中的 CSS 网格布局上来识别并可视化这些布局。  选择**** ![ DevTools (左上角的"检查) 检查 \) ](../media/inspect-icon.msft.png) 图标。  然后，将鼠标悬停在要调试的网站上 Grid 元素上。  边框显示在网格周围，底纹指示网格间隙的位置（如果存在）。  

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

在 Microsoft Edge 版本 86**** 或更高版本中，新的布局面板位于 **"** 元素"工具**** 中的"样式"和"**计算**"选项卡旁边。  布局 **面板** 显示持久覆盖的配置选项。  

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

打开实验后，请确保重新启动 DevTools。  若要使用 **网络控制台**，请完成以下步骤。  

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

**源订单查看器** 是显示网页源中元素顺序的实验。  屏幕显示顺序可能与源的顺序不同，这会使屏幕阅读器和键盘用户混淆。  使用 **源订单查看器** 实验可查找屏幕显示顺序和源顺序之间的差异。  

打开实验后，请确保重新启动 DevTools。  若要使用 **源订单查看器**，请完成以下步骤。  

1.  打开 **"元素"** 工具。  
1.  在 **底部\下** 角的 (打开) 窗格。  
1.  在" **源订单查看器"** 部分下，选中" **显示源订单"** 复选框。  
1.  突出显示任何 HTML 元素以显示网页源中订单的覆盖层。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="辅助功能窗格中的源订单查看器" lightbox="../media/experiments-source-order-viewer.msft.png":::
   **辅助功能窗格中** 的 **源订单** 查看器  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### 启用键盘快捷方式编辑器

打开 **"启用键盘快捷方式编辑器** "实验后，你可以为 DevTools 中任何操作自定义键盘快捷方式。  若要为特定操作自定义键盘快捷方式，请完成以下步骤。  

1.  [打开 DevTools。][DevtoolsOpenMain]  
1.  打开["设置"。][DevToolsCustomizeIndexSettings]  
    *   选择 `Shift` + `?` 。  
1.  导航到 **"快捷方式"** 页。  
1.  选择要自定义的操作。  
1.  选择 **编辑** \ (![ EditKeyboardShortcut ](../media/edit-keyboard-shortcut-icon.msft.png) \) 图标。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="从"设置"中的"快捷方式"页选择要自定义的操作" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       从"设置"中的"快捷方式 **"** 页选择要自定义 [的操作][DevToolsCustomizeIndexSettings]  
    :::image-end:::  
    
1.  在键盘上，选择要绑定到该操作的键。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="选择要分配给该操作的键" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择要分配给该操作的键  
    :::image-end:::  
    
1.  若要保存新的键盘快捷方式，请选择选中标记 \ (![CheckmarkKeyboardShortcut](../media/checkmark-keyboard-shortcut-icon.msft.png)\) 图标。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="选择选中标记图标以保存新的键盘快捷方式" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择选中标记图标以保存新的键盘快捷方式  
    :::image-end:::  
    
1.  选择新的键盘快捷方式以在 DevTools 中触发该操作。  
    
在 **"快捷方式"** 页上，自定义键盘快捷方式 **\ (** ![ CustomKeyboardShortcut ](../media/custom-keyboard-shortcut-icon.msft.png) \) 图标显示自定义的键盘快捷方式。  若要重置所有快捷方式，请选择"**还原默认快捷方式"。**  

若要在编辑操作键盘快捷方式时放弃所做的更改，请选择 X \ (![ XKeyboardShortcut ](../media/discard-changes-keyboard-shortcut-icon.msft.png) \) 图标。  若要删除特定操作快捷方式，请选择"删除"快捷方式 **\ (** ![ DeleteKeyboardShortcut ](../media/delete-keyboard-shortcut-icon.msft.png) \) 图标。  若要为操作添加多个快捷方式，请选择"**添加快捷方式"。**  

> [!NOTE]
> 如果键盘快捷方式当前已分配给另一个操作，则不能将其保存以用于新操作。  必须先删除上一个操作键盘快捷方式，然后将其添加到新操作。  

<!--Available in Microsoft Edge version 87 and later.  -->  

### 在 3D 视图中启用复合层  

现在，您可以可视化 Z 索引和文档对象模型 \ (DOM\) 。  此功能可帮助您在不经常切换上下文的情况下进行调试。  您确定减少上下文切换是一个主要的难点。  您编写的代码对 Web 应用有何影响并不总是很明显。  为获得全面的视觉调试体验， 已将3D 视图和复合层组合到一起。  

打开实验后，请确保重新启动 DevTools。  若要使用 **复合层**，请完成以下步骤。  

1.  在箱中，选择 **3D 视图** 工具。  
1.  打开 **"复合层"** 窗格。  
1.  将显示应用的所有绘制图层。  使用你自己的 Web 应用试用此功能。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   **复合层** 窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### 在"样式"窗格中启用新的字体编辑器工具  

现在可以使用新的可视 [字体编辑器][DevtoolsInspectStylesEditFonts] 编辑字体。  使用它定义字体和字体特征。  可视 **字体编辑器** 可帮助您完成以下操作。  

*   在不同字体属性的单位之间切换  
*   在不同字体属性的关键字之间切换  
*   转换单位  
*   生成准确的 CSS 代码  
    
打开实验后，请确保重新启动 DevTools。  若要使用新的可视化 **字体编辑器**，请完成以下步骤。  

1.  打开 **"元素"** 工具。  
1.  打开 **"样式"** 窗格。  
1.  选择 **"字体编辑器"** 图标。  
    
有关新的可视字体**编辑器的详细信息，** 请导航到 DevTools 的"样式"窗格中的"编辑 CSS[字体样式和设置"。][DevtoolsInspectStylesEditFonts]  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="突出显示可视字体编辑器窗格" lightbox="../media/font-editor-open.msft.png":::
   突出显示 **可视字体编辑器** 窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### 启用新的 CSS Flexbox 调试功能  

此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS 弹性框布局。  若要预览最新的实验功能， [请打开此实验](#turn-on-experimental-features) 并重新加载 DevTools。  

#### 使用 Inspect 工具在 Flexbox 布局上显示永久性覆盖  

检查 **工具** 提供了一种快速方法，通过将鼠标悬停在网站中的 CSS 弹性框布局上来识别并可视化它们。  选择**** ![ DevTools (左上角的"检查) 检查 \) ](../media/inspect-icon.msft.png) 图标。  然后，在调试网站时，将鼠标悬停在弹性容器上，以在弹性容器周围显示轮廓。  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="使用检查工具显示 Flexbox 容器" lightbox="../media/flexbox-hover.msft.png":::
   使用检查工具显示 Flexbox**容器**  
:::image-end:::  

#### 在 Flexbox 布局上显示永久性覆盖  

在 Microsoft Edge 版本 89 或更高版本中，实验 CSS Flexbox 功能还提供了在 Flexbox 布局上打开永久性覆盖的选项。  持久覆盖具有以下优点。  

*   滚动、移动鼠标并使用 DevTools 的其他功能时，永久性覆盖在网页上仍然可见。
*   可以同时使用多个永久性覆盖，以便一次查看多个 Flexbox 布局。  
*   持久覆盖提供颜色配置选项。  
    
若要切换 Flexbox 布局上的永久性覆盖，请使用下列操作之一。  

*   选择 **"元素"** 工具的 DOM 树中显示的任意 Flexbox 容器旁边的 Flexbox **椭圆图标** 。  
*   打开位于 **"元素**"工具中的新布局**** 面板，并选中要突出显示的每个 Flexbox 容器旁边的复选框。  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools 中的弹性图标和布局面板" lightbox="../media/flexbox-overlay.msft.png":::
   DevTools 中的弹性图标和布局面板****  
:::image-end:::  

#### 配置永久性覆盖  

若要为 CSS 网格或 Flexbox 布局配置持久覆盖的选项，请使用"布局 **"** 窗格。  布局**窗格**位于"样式"和"**** 计算"窗格旁边的 **"** 元素 **"工具**中。  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="布局面板" lightbox="../media/flexbox-layout.msft.png":::
   布局面板  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### 启用 + 按钮选项卡菜单以打开更多工具  

现在，可以使用新的"更多工具"\ (**** `+` \) 图标打开更多工具。  打开"启用 **+** "按钮选项卡菜单以打开更多工具实验并重新加载 DevTools 后，在 DevTools 顶部的选项卡组右侧显示加号 `+` \ (\) 。  若要显示可以添加到选项卡栏的其他工具的列表，请选择新的"更多工具"\ (**** `+` \) 图标。  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="顶部窗格中的更多工具" lightbox="../media/experiments-more-tools-button.msft.png":::
   **顶部窗格中** 的更多工具
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### 启用欢迎工具

此实验将 **"新增功能"** 工具替换为新的 **欢迎** 工具。  它显示以下内容的刷新设计。  

*   指向开发人员文档的链接  
*   最新功能  
*   发行说明  
*   联系 Microsoft Edge DevTools 团队的选项  
    
每次 **更新** 到 Microsoft Edge 后，欢迎工具都会自动打开。  若要防止每次更新后显示**** 欢迎工具，请清除"欢迎"工具标题下**** 每个更新后"打开"选项卡**旁边的**复选框。  

如果你更喜欢原始的新增**功能工具，** 请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"并删除  >  ****"启用欢迎"**选项卡旁边的复选框**。  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="欢迎工具" lightbox="../media/experiments-welcome.msft.png":::
   **欢迎** 工具  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## 以前的实验功能  

*   [3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本 83 或更高版本中默认处于打开状态。  
*   [在 Microsoft][DevtoolsMoveTabs] Edge 版本 85 或更高版本中，现已启用支持以在面板之间移动选项卡，并且默认情况下处于打开状态。  
*   [自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在可用，在 Microsoft Edge 版本 86 或更高版本中默认处于打开状态。  
*   [模拟：支持双屏][DevtoolsDeviceModeDualScreenAndFoldables] 模式现在可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。  
*   [在][DevtoolsCssGrid] Microsoft Edge 版本 89 或更高版本中，现已启用新的 CSS 网格调试功能，并且默认处于打开状态。  
    
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

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D 视图 | Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsMoveTabs]: ../customize/index.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools |Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "在 DevTools | 中的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsIssues]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏幕 Web 体验|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏幕设备简介|Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "用于双屏检测方法的 CSS 媒体屏幕|Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "百年百|Samsung"  
[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "模拟 Microsoft Edge DevTools |Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
