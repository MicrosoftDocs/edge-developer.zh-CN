---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 实验
ms.openlocfilehash: 612b3b83aee1ee9035982e58e008395ec3645b2b
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408302"
---
# <a name="experimental-features"></a>实验功能  

Microsoft Edge DevTools 提供对仍在开发中的实验性功能的访问权限。  您可以在发布每个 [功能之前](#providing-feedback-on-experimental-features) 进行测试并提供反馈。  

尽管实验功能在 Microsoft Edge 的所有渠道中都可用，但你可能会使用 Microsoft Edge Canary 渠道获取最新的实验功能。  

## <a name="turn-on-experimental-features"></a>打开实验性功能  

若要在 Microsoft Edge (\) 或关闭\) 实验功能，请完成以下步骤。  

1.  [打开 DevTools][DevtoolsOpenIndex]。  
    *   选择 `Control` + `Shift` + `I` \ (Windows、Linux\) 或 `Command` + `Option` + `I` \ (macOS\) 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。  
1.  打开" [设置"][DevToolsCustomizeIndexSettings] 窗格。  
    *   选择 `Shift` + `?` 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。  
1.  在"设置"窗格 **的左侧** ，选择"实验 **"** 部分。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text=""设置"中的"实验"页面" lightbox="../media/experiments-devtools.msft.png":::
       " **设置"** 中的"实验 **"页面**  
    :::image-end:::  
    
1.  在 **实验** 页面上，滚动浏览所有可用实验功能的列表，并选中要测试的每个功能旁边的复选框。  
1.  关闭并重新打开 Microsoft Edge DevTools。  
    
> [!NOTE]
> 实验性功能会不断更新，并且可能会导致性能问题。  若要关闭实验功能，请打开实验 **页面** 并清除要关闭的实验功能复选框。  

## <a name="highlighted-experimental-features"></a>突出显示的实验功能  

以下各节介绍 Microsoft Edge 中提供的新实验功能。  

| 实验性功能 | Microsoft Edge 版本 |  
|:--- |:--- |  
| [启用 Webhint](#enable-webhint) | 85 或更高版本 |  
| [启用网络控制台](#enable-network-console) | 85 或更高版本 |  
| [源订单查看器](#source-order-viewer) | 86 或更高版本 |  
| [在 3D 视图中启用复合层](#enable-composited-layers-in-3d-view) | 87 或更高版本 |  
| [在"样式"窗格中启用新的字体编辑器工具](#enable-new-font-editor-tool-within-the-styles-pane) | 89 或更高版本 |  
| [启用新的 CSS Flexbox 调试功能](#enable-new-css-flexbox-debugging-features) | 89 或更高版本 |  
| [启用 + 按钮选项卡菜单以打开更多工具](#enable--button-tab-menus-to-open-more-tools) | 89 或更高版本 |  
| ["启用欢迎"选项卡](#enable-welcome-tool) | 89 或更高版本 |  

### <a name="enable-webhint"></a>启用 Webhint  

[webhint][WebhintMain] 是一个开放源代码工具，可为网站和本地网页提供实时反馈。  Webhint 提供 [的反馈类型][WebhintMain]。  

*   辅助功能  
*   跨浏览器兼容性  
*   安全性  
*   性能  
*   渐进式 Web (PBA)   
*   其他常见的 Web 开发问题  
    
[Webhint 实验][WebhintMain]在问题面板中显示[Webhint][DevtoolsIssuesIndex]反馈。  选择一个问题，在网站上显示解决方案文档和受影响资源的列表。  选择资源链接以在 DevTools******中**打开**** 相关的"网络、源"或"元素"窗格。  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../media/experiments-webhint.msft.png":::
   问题面板中的 **webhint** 反馈  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-network-console"></a>启用网络控制台  

**网络控制台** 是实验通过 HTTP 提出综合网络请求的工作主题。  可以使用网络 **控制台实验** 发送 Web API 请求。  

打开实验后，请确保重新启动 DevTools。  若要使用 **网络控制台**，请完成以下步骤。  

1.  打开" **网络"** 窗格。  
1.  查找要更改和重新发送的网络请求。  
1.  打开上下文菜单 \ (右键单击\) ，然后选择编辑 **和重播**。  
1.  当网络 **控制台打开** 时，编辑网络请求信息。  
1.  选择 **"发送"。**  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="控制台箱中的网络控制台" lightbox="../media/network-network-console.msft.png":::
   **控制台箱****中的网络**控制台  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="source-order-viewer"></a>源订单查看器  

**源订单** 查看器是显示网页源中元素顺序的实验。  屏幕显示顺序可能与源的顺序不同，这会使屏幕阅读器和键盘用户混淆。  使用 **"源顺序查看器** "实验可查找屏幕显示顺序和源顺序之间的差异。  

打开实验后，请确保重新启动 DevTools。  若要使用 **源订单查看器**，请完成以下步骤。  

1.  打开 **"元素"** 工具。  
1.  打开 **"辅助功能"** 窗格， (底部\) 面板。  
1.  在" **源订单查看器"** 部分下，选中" **显示源订单"** 复选框。  
1.  突出显示任何 HTML 元素以显示网页源中顺序的覆盖。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text=""辅助功能"窗格中的"源订单查看器"" lightbox="../media/experiments-source-order-viewer.msft.png":::
   **"辅助功能"** 窗格中 **的"源订单查看器** "  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <a name="enable-composited-layers-in-3d-view"></a>在 3D 视图中启用复合层  

现在，你可以将 Layers 与 z 索引和文档对象模型 \ (DOM\) 一起可视化。  此功能可帮助您在不经常切换上下文的情况下进行调试。  您确定减少上下文切换是一个主要的难点。  并非始终清楚您编写的代码对 Web 应用有何影响。  为获得全面的视觉调试体验， 已将3D 视图和复合层组合到一起。  

打开实验后，请确保重新启动 DevTools。  若要使用 **复合层**，请完成以下步骤。  

1.  在"箱"上，选择 **"3D 视图"** 工具。  
1.  打开 **"复合层"** 窗格。  
1.  将显示应用的所有绘制图层。  使用你自己的 Web 应用试用此功能。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   **复合层** 窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-new-font-editor-tool-within-the-styles-pane"></a>在"样式"窗格中启用新的字体编辑器工具  

现在，可以使用新的可视 [字体编辑器][DevtoolsInspectStylesEditFonts] 来编辑字体。  使用它定义字体和字体特征。  可视 **字体编辑器** 可帮助您完成以下操作。  

*   在不同字体属性的单位之间切换  
*   在不同字体属性的关键字之间切换  
*   转换单位  
*   生成准确的 CSS 代码  
    
打开实验后，请确保重新启动 DevTools。  若要使用新的可视化 **字体编辑器，** 请完成以下步骤。  

1.  打开 **"元素"** 工具。  
1.  打开 **"样式"** 窗格。  
1.  选择" **字体编辑器"** 图标。  
    
有关新的可视字体编辑器 **的详细信息**，请导航到 [DevTools][DevtoolsInspectStylesEditFonts]的样式窗格中的编辑 CSS 字体样式和设置。  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="突出显示可视字体编辑器窗格" lightbox="../media/font-editor-open.msft.png":::
   突出显示可视 **字体编辑器** 窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-new-css-flexbox-debugging-features"></a>启用新的 CSS Flexbox 调试功能  

此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS Flexbox 布局。  若要预览最新的实验功能， [请打开此实验](#turn-on-experimental-features) 并重新加载 DevTools。  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a>使用 Inspect 工具在 Flexbox 布局上显示永久性覆盖  

Inspect **工具** 提供了一种快速方法，通过将鼠标悬停在网站中的 CSS Flexbox 布局来标识和可视化它们。  选择 **DevTools** (左上角的"检查 \ (检查 ![ ](../media/inspect-icon.msft.png) \) "图标。  然后，在调试网站时，将鼠标悬停在弹性容器上，以显示弹性容器周围的轮廓。  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="使用 Inspect 工具显示 Flexbox 容器" lightbox="../media/flexbox-hover.msft.png":::
   使用 Inspect 工具显示 Flexbox**容器**  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a>在 Flexbox 布局上显示永久性覆盖  

在 Microsoft Edge 版本 89 或更高版本中，实验 CSS Flexbox 功能还提供了在 Flexbox 布局上打开永久性覆盖的选项。  永久性覆盖具有以下优点。  

*   滚动、移动鼠标并使用 DevTools 的其他功能时，永久性覆盖在网页上仍然可见。
*   可以同时使用多个永久性覆盖，以便你可以一次查看多个 Flexbox 布局。  
*   永久性覆盖提供颜色配置选项。  
    
若要切换 Flexbox 布局上的永久性覆盖，请使用下列操作之一。  

*   选择 **"元素"** 工具的 DOM 树中显示的任意 Flexbox 容器旁边的 Flexbox **椭圆图标** 。  
*   打开位于" **元素** "工具 **中的新布局** 面板，并选中要突出显示的每个 Flexbox 容器旁边的复选框。  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools 中的弹性图标和布局面板" lightbox="../media/flexbox-overlay.msft.png":::
   DevTools **中的** 弹性图标和布局面板  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a>配置永久性覆盖  

若要为 CSS 网格或 Flexbox 布局配置永久覆盖的选项，请使用"布局 **"** 窗格。  "**布局**"窗格位于"样式"**** 和"计算"窗格**** 旁边的"元素 **"工具**中。  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="布局面板" lightbox="../media/flexbox-layout.msft.png":::
   布局面板  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable--button-tab-menus-to-open-more-tools"></a>启用 + 按钮选项卡菜单以打开更多工具  

现在，可以使用新的"更多工具"\ (**** `+` \) 图标打开更多工具。  打开"启用 **+** 按钮"选项卡菜单以打开更多工具实验并重新加载 DevTools 后，DevTools 顶部的选项卡组右侧将显示加号 \ (`+` \) 。  若要显示可添加到选项卡栏的其他工具的列表，请选择新的"更多工具"\ (**** `+` \) 图标。  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="顶部窗格中的更多工具" lightbox="../media/experiments-more-tools-button.msft.png":::
   **顶部窗格中** 的更多工具
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-welcome-tool"></a>启用欢迎工具

此实验使用新的欢迎 **工具** 替换新增 **功能** 工具。  它显示以下内容的刷新设计。  

*   指向开发人员文档的链接  
*   最新功能  
*   发行说明  
*   联系 Microsoft Edge DevTools 团队的选项  
    
每次 **更新** Microsoft Edge 后，欢迎工具都会自动打开。  若要防止每次更新后显示**欢迎**工具，请清除"欢迎使用工具"标题**** 下每个更新后"打开"**** 选项卡旁边的复选框。  

如果你更喜欢原始的**新增**功能工具，请导航到设置实验[][DevtoolsCustomizeIndexSettings]并删除"  >  **** 启用欢迎"选项卡旁边的**复选框**。  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="欢迎工具" lightbox="../media/experiments-welcome.msft.png":::
   **欢迎** 工具  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a>以前的实验功能  

*   [3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本 83 或更高版本中默认处于打开状态。  
*   [启用支持以在面板][DevtoolsCustomizeIndex] 之间移动选项卡现在可用，Microsoft Edge 版本 85 或更高版本中默认处于打开状态。  
*   [将 DevTools][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] 中的键盘快捷方式与 Microsoft Visual Studio Code 现在可用，在 Microsoft Edge 版本 86 或更高版本中默认处于打开状态。  
*   [编辑 DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] 中任何操作键盘快捷方式现已可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。  
*   [启用新的 CSS 网格调试功能][DevtoolsCssGrid] 现已可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。  
*   [模拟：支持双屏模式][DevtoolsDeviceModeDualScreenAndFoldables] 现在可用，在 Microsoft Edge 版本 90 或更高版本中默认处于打开状态。  

    
## <a name="providing-feedback-on-experimental-features"></a>提供有关实验性功能的反馈  

提供有关 Microsoft Edge DevTools 实验或与 DevTools 相关的任何其他内容的反馈。  

*   使用 DevTools 中的 **"发送** 反馈"图标发送反馈  
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
[DevtoolsCustomizeIndex]: ../customize/index.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools]: ../customize/shortcuts.md#edit-keyboard-shortcuts-for-any-action-in-the-devtools "编辑 DevTools 工具中任何操作|Microsoft Docs"  
[DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode]: ../customize/shortcuts.md#match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code "将 DevTools 中的键盘快捷方式与 Microsoft Visual Studio Code |Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 服务中通过设备模式模拟移动设备|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "在 DevTools | 中的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsOpenIndex]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "模拟 Microsoft Edge DevTools |Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
