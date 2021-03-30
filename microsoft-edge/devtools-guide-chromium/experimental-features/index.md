---
description: Microsoft Edge DevTools 中的最新试验功能
title: 试验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools, 试验
no-loc:
- Enable webhint
- Enable Network Console
- Source Order Viewer
- Enable Composited Layers in 3D View
- Enable new Font Editor tool within the Styles pane
- Enable new CSS Flexbox debugging features
- Enable + button tab menus to open more tools
- Enable Welcome tab
- 3D View
- Turn on support to move tabs between panels
- Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code
- Edit keyboard shortcuts for any action in the DevTools
- Turn on new CSS grid debugging features
- 'Emulation: Support dual screen mode'
ms.openlocfilehash: c76830cb8bbcc597aa026f58e1926cd2f9bc2d62
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439582"
---
# <a name="experimental-features"></a>试验功能  

Microsoft Edge DevTools 提供对仍在开发中的试验功能的访问权限。  可以在每个功能发布之前对其进行测试并[提供反馈](#providing-feedback-on-experimental-features)。  

尽管试验功能在 Microsoft Edge 的所有渠道中均可用，但你可能会使用 Microsoft Edge Canary 渠道获取最新的试验功能。  

## <a name="turn-on-experimental-features"></a>打开试验功能  

若要在 Microsoft Edge 中打开\（或关闭\）试验功能，请完成以下步骤。  

1.  [打开 DevTools][DevtoolsOpenIndex]。  
    *   选择 `Control` + `Shift` + `I` \(Windows、Linux\) 或 `Command` + `Option` + `I` \(macOS\)。  有关更多信息，请导航至 [Microsoft Edge DevTools 键盘快捷键][DevtoolsShortcutsIndex]。  
1.  打开“[设置][DevToolsCustomizeIndexSettings]”窗格。  
    *   选择 `Shift`+`?`。  有关更多信息，请导航至 [Microsoft Edge DevTools 键盘快捷键][DevtoolsShortcutsIndex]。  
1.  在“**设置**”窗格左侧，选择“**试验**”部分。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="设置中的试验页面" lightbox="../media/experiments-devtools.msft.png":::
       **设置**中的**试验**页面  
    :::image-end:::  
    
1.  在“**试验**”页上，滚动浏览所有可用试验功能的列表，然后选中要测试的每个功能旁边的复选框。  
1.  关闭并重新打开 Microsoft Edge DevTools。  
    
> [!NOTE]
> 试验功能会不断更新，并且可能会导致性能问题。  若要关闭试验功能，请打开“**试验**”页面并清除要关闭的试验功能的复选框。  

## <a name="highlighted-experimental-features"></a>突出显示的试验功能  

以下各节介绍 Microsoft Edge 中提供的新试验功能。  

| 试验功能 | Microsoft Edge 版本 |  
|:--- |:--- |  
| [Enable webhint](#enable-webhint) | 85 或更高版本 |  
| [Enable Network Console](#enable-network-console) | 85 或更高版本 |  
| [Source Order Viewer](#source-order-viewer) | 86 或更高版本 |  
| [Enable Composited Layers in 3D View](#enable-composited-layers-in-3d-view) | 87 或更高版本 |  
| [Enable new Font Editor tool within the Styles pane](#enable-new-font-editor-tool-within-the-styles-pane) | 89 或更高版本 |  
| [Enable new CSS Flexbox debugging features](#enable-new-css-flexbox-debugging-features) | 89 或更高版本 |  
| [Enable + button tab menus to open more tools](#enable--button-tab-menus-to-open-more-tools) | 89 或更高版本 |  
| [Enable Welcome tab](#enable-welcome-tab) | 89 或更高版本 |  

### Enable webhint  

[webhint][WebhintMain] 是一个开源代码工具，可为网站和本地网页提供实时反馈。  [webhint][WebhintMain] 提供的反馈类型。  

*   辅助功能  
*   跨浏览器兼容性  
*   安全性  
*   性能  
*   渐进式 Web 应用 (PWA)  
*   其他常见的 Web 开发问题  
    
[Webhint][WebhintMain] 试验在“[问题][DevtoolsIssuesIndex]”面板中显示 webhint 反馈。  选择一个问题，在网站上显示解决方案文档和受影响资源的列表。  选择资源链接以在 DevTools 中打开相关的“**网络**”、“**源**”或“**元素**”窗格。  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../media/experiments-webhint.msft.png":::
   **问题**面板中的 webhint 反馈  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Enable Network Console  

**网络控制台**是试验通过 HTTP 提出综合网络请求的工作主题。  可以使用**网络控制台**试验发送 Web API 请求。  

打开试验后，确保重新启动 DevTools。  若要使用**网络控制台**，请完成以下步骤。  

1.  打开“**网络**”窗格。  
1.  查找要更改和重新发送的网络请求。  
1.  打开上下文菜单 \（右键单击\），然后选择“**编辑并重播**”。  
1.  当**网络控制台**打开时，编辑网络请求信息。  
1.  选择“**发送**”。  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="控制台工具箱中的网络控制台" lightbox="../media/network-network-console.msft.png":::
   **控制台**工具箱中的**网络控制台**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Source Order Viewer  

**Source Order Viewer** 是显示网页源中元素顺序的试验。  屏幕上的显示顺序可能与网页源的顺序不同，这会使屏幕阅读器和键盘用户感到困惑。  使用 **Source Order Viewer** 试验查找屏幕显示顺序和源顺序之间的差异。  

打开试验后，确保重新启动 DevTools。  若要使用 **Source Order Viewer**，请完成以下步骤。  

1.  打开“**元素**”工具。  
1.  打开工具箱 \（底部\）面板中的“**辅助功能**”窗格。  
1.  在 **Source Order Viewer** 部分下，选择“**显示源顺序**”复选框。  
1.  突出显示任何 HTML 元素，以显示该网页源中顺序的覆盖。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text=":::no-loc（源订单查看器）:::在辅助功能窗格中" lightbox="../media/experiments-source-order-viewer.msft.png"::: **Source Order Viewer** 在“**辅助功能**”窗格中  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### Enable Composited Layers in 3D View  

现在，你可以将层与 z 索引和文档对象模型 \(DOM\) 一起可视化。  此功能可帮助你进行调试，而无需频繁切换上下文。  你发现减少上下文切换是一个主要的痛点。  不能始终弄清楚你编写的代码对 Web 应用有何影响。  为了获得全面的视觉调试体验，现在已将 3D View 和复合层组合到一起。  

打开试验后，确保重新启动 DevTools。  若要使用**复合层**，请完成以下步骤。  

1.  在工具箱上，选择 **3D View** 工具。  
1.  打开“**复合层**”窗格。  
1.  此时将显示应用的所有绘制层。  使用你自己的 Web 应用试用此功能。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   **复合层**窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### Enable new Font Editor tool within the Styles pane  

现在可以使用新的可视[字体编辑器][DevtoolsInspectStylesEditFonts]来编辑字体。  使用它来定义字体和字体特征。  可视**字体编辑器**可帮助你完成以下操作。  

*   在不同字体属性的单位之间切换  
*   在不同字体属性的关键字之间切换  
*   转换单位  
*   生成准确的 CSS 代码  
    
打开试验后，确保重新启动 DevTools。  若要使用新的可视**字体编辑器**，请完成以下步骤。  

1.  打开“**元素**”工具。  
1.  打开“**样式**”窗格。  
1.  选择“**字体编辑器**”图标。  
    
有关新的可视内容**字体编辑器**的详细信息，请导航到“[在 DevTools 的样式窗格中编辑 CSS 字体样式和设置][DevtoolsInspectStylesEditFonts]”。  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="突出显示可视内容字体编辑器窗格" lightbox="../media/font-editor-open.msft.png":::
   突出显示可视内容**字体编辑器**窗格  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable new CSS Flexbox debugging features  

此试验功能提供了许多新的可视化效果，可帮助你调试 CSS 弹性框布局。  若要预览最新的试验功能，请[打开此试验](#turn-on-experimental-features)并重新加载 DevTools。  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a>使用检查工具在弹性框布局上显示持久覆盖层  

**检查**工具提供了一种快速识别和可视化网站 CSS 弹性框布局的方法，通过将鼠标悬停该布局上方来实现这一点。  选择 DevTools 左上角的“**检查**”\（![检查](../media/inspect-icon.msft.png)\）图标。  然后，在调试网站时，将鼠标悬停在弹性容器上方以在其周围显示轮廓。  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="使用检查工具显示弹性框容器" lightbox="../media/flexbox-hover.msft.png":::
   使用**检查**工具显示弹性框容器  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a>在弹性框布局上显示持久覆盖层  

在 Microsoft Edge 版本 89 或更高版本中，试验 CSS 弹性框功能还提供了在弹性框布局上打开持久覆盖层的选项。  持久覆盖层具有以下优点。  

*   滚动、移动鼠标和使用 DevTools 的其他功能时，持久覆盖层在网页上仍然可见。
*   可以同时使用多个持久覆盖层，以便你可以一次查看多个弹性框布局。  
*   持久覆盖层提供颜色配置选项。  
    
若要切换弹性框布局上的持久覆盖层，请使用下列操作之一。  

*   选择“**元素**”工具的 DOM 树中显示的所有弹性框容器旁边的“**弹性框**”椭圆形图标。  
*   打开位于“**元素**”工具中的新“**布局**”面板，然后选择要突出显示的每个弹性框容器旁边的复选框。  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools 中的弹性图标和布局面板" lightbox="../media/flexbox-overlay.msft.png":::
   DevTools 中的弹性图标和**布局**面板  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a>配置持久覆盖层  

若要为 CSS 网格或弹性框布局配置持久覆盖层的选项，请使用“**布局**”窗格。  “**布局**”窗格位于“**样式**”和“**计算**”窗格旁边的“**元素**”工具中。  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="布局面板" lightbox="../media/flexbox-layout.msft.png":::
   布局面板  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable + button tab menus to open more tools  

现在，可以使用新的“**更多工具**”\(`+`\) 图标打开更多工具。  打开 **Enable + button tab menus to open more tools** 试验并重新加载 DevTools 后，DevTools 顶部选项卡组的右侧将显示一个加号 \(`+`\)。  若要显示可添加到选项卡栏的其他工具的列表，请选择新的“**更多工具**”\(`+`\) 图标。  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="顶部窗格中的更多工具" lightbox="../media/experiments-more-tools-button.msft.png":::
   顶部窗格中的**更多工具**
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable Welcome tab

此试验使用新的**欢迎**工具替换**新增功能**工具。  它显示以下内容的更新设计。  

*   指向开发人员文档的链接  
*   最新功能  
*   发行说明  
*   用于联系 Microsoft Edge DevTools 团队的选项  
    
每次更新 Microsoft Edge 后，**欢迎**工具都会自动打开。  若要防止每次更新后显示**欢迎**工具，请清除“**欢迎**”标题下“**每次更新后打开选项卡**”旁边的复选框。  

如果你更喜欢原始的“**新增功能**”工具，请导航到“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后删除 **Enable Welcome tab** 旁边的复选框。  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="欢迎工具" lightbox="../media/experiments-welcome.msft.png":::
   **欢迎**工具  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a>以前的试验功能  

*   [3D View][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本 83 或更高版本中默认处于打开状态。  
*   [Turn on support to move tabs between panels][DevtoolsCustomizeIndex] 现在可用，在 Microsoft Edge 版本 85 或更高版本中默认处于打开状态。  
*   [Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] 现在可用，在 Microsoft Edge 版本 86 或更高版本中默认处于打开状态。  
*   [Edit keyboard shortcuts for any action in the DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] 现在可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。  
*   [Turn on new CSS grid debugging features][DevtoolsCssGrid] 现在可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。  
*   [Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] 现在可用，在 Microsoft Edge 版本 90 或更高版本中默认处于打开状态。  

## <a name="providing-feedback-on-experimental-features"></a>提供有关试验功能的反馈  

提供有关 Microsoft Edge DevTools 试验或与 DevTools 相关的任何其他内容的反馈。  

*   使用 DevTools 中的“**发送反馈**”图标发送反馈  
*   向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的发送反馈图标" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools 中的**发送反馈**图标  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md ":::no-loc（3D 视图）::: | Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "检查 Microsoft Edge DevTools 中的 CSS 网格 | Microsoft Docs"  
[DevtoolsCustomizeIndex]: ../customize/index.md "自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools]: ../customize/shortcuts.md#edit-keyboard-shortcuts-for-any-action-in-the-devtools ":::no-loc（为 DevTools 中的任何操作编辑键盘快捷方式）::: | Microsoft Docs"  
[DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode]: ../customize/shortcuts.md#match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code ":::no-loc（将 DevTools 中的键盘快捷方式与 Microsoft Visual Studio Code 相匹配）::: | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 | Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "在 DevTools 的“样式”窗格中编辑 CSS 字体样式和设置 | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsOpenIndex]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 | Microsoft Docs"  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "在 Microsoft Edge DevTools 中模拟双屏幕可折叠设备 | Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools | Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
