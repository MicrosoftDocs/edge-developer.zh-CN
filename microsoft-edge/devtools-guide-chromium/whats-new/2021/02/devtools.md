---
description: CSS 弹性框调试支持、网页上的性能提示显示、问题工具更新等
title: DevTools 中的新增功能 (Microsoft Edge 90)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.localizationpriority: high
ms.openlocfilehash: e220bbbe0a545b7cc539d0c77deb2ecb070decc0
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439743"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-90"></a>DevTools 中的新增功能 (Microsoft Edge 90)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="group-tools-together-in-focus-mode"></a>在焦点模式下将工具组合在一起  

<!-- Title: Grouping the tools in Focus Mode  -->  
<!-- Subtitle: Organize your favorite tools into groups with the new Focus Mode UI.  -->  

焦点模式是一个试验界面，允许你根据自己的调试方案将不同工具组合在一起。  左侧显示的新“**活动栏**”包括预定义的工具组，如“**布局**”和“**调试**”。  若要自定义每个工具组，请使用“**关闭**”(`X`) 图标关闭工具，或使用“**更多工具**”(`+`) 图标添加新工具。  

若要启用试验，请导航至“[启用试验功能][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]”，然后选择“**焦点模式和 DevTools 工具提示**”和“**启用 + 按钮选项卡菜单以打开更多工具**”旁边的复选框。  有关此功能的详细信息，或者要用问题和想法进行评论，请导航到 [DevTools：焦点模式 UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]。  

:::image type="complex" source="../../media/2021/02/focus-mode.msft.png" alt-text="显示“活动栏”" lightbox="../../media/2021/02/focus-mode.msft.png":::
   显示“**活动栏**”  
:::image-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a>通过信息丰富的工具提示了解 DevTools  

<!-- Title: DevTools Tooltips  -->  
<!-- Subtitle: Learn more about how to use DevTools with informative DevTools tooltips.  -->  

DevTools 工具提示功能可帮助你了解所有不同的工具和窗格。  选择“**活动栏**”底部的“帮助”(`?`) 图标，以便在 DevTools 中切换工具提示。  当工具提示打开时，请将鼠标悬停在 DevTools 的每个概述区域上，以了解有关如何使用工具的更多信息。  若要启用试验，请导航至“[启用试验功能][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]”，然后选择“**焦点模式和 DevTools 工具提示**”和“**启用 + 按钮选项卡菜单以打开更多工具**”旁边的复选框。  有关此功能的详细信息，或者要用问题和想法进行评论，请导航到 [DevTools：焦点模式 UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]。  

:::image type="complex" source="../../media/2021/02/focus-mode-and-tooltips-help.msft.png" alt-text="选择“活动栏”中的“帮助”(?) 图标以显示工具提示" lightbox="../../media/2021/02/focus-mode-and-tooltips-help.msft.png":::
   选择“**活动栏**”中的“帮助”(`?`) 图标以显示工具提示  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a>在“设置”中自定义键盘快捷方式  

<!-- Title: Change keyboard shortcuts in Settings  -->  
<!-- TODO:  Rachel's feedback is about the fact that this experimental feature is turned on by default, may have separate section in What's New for experimental features)  -->  
<!-- Subtitle: Make DevTools work better for you by creating new keyboard shortcuts for any action in the DevTools.  -->  

现在，你可以为 DevTools 中的任何操作自定义键盘快捷方式。  若要编辑键盘快捷方式，请完成以下操作。  

1.  打开 DevTools，然后选择“**设置**” > “**快捷方式**”。  
1.  选择要自定义的操作。  
1.  选择“编辑”（![“编辑键盘快捷方式”图标](../../media/2021/02/edit-keyboard-shortcut-icon.msft.png)）图标。  
1.  选择要绑定到操作的按键。  
1.  选中复选标记（![复选标记键盘快捷方式图标](../../media/2021/02/checkmark-keyboard-shortcut-icon.msft.png)）图标。  
    
有关自定义和编辑快捷方式的详细信息，请导航到“[自定义 Microsoft Edge DevTools 中的键盘快捷方式][DevtoolsCustomizeShortcuts]”。  若要在 Chromium 开源项目中查看此功能的实时更新，请导航至问题 [174309][CR174309]。  

:::image type="complex" source="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png" alt-text="在编辑模式下使用快捷方式在“DevTools 设置”的“快捷方式”上自定义键盘快捷方式" lightbox="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png":::
   在编辑模式下使用快捷方式在“[DevTools 设置][DevtoolsCustomizeIndexSettings]”的“快捷方式”上自定义键盘快捷方式  
:::image-end:::  

## <a name="microsoft-edge-devtools-for-visual-studio-code-extension-update-114"></a>Microsoft Edge DevTools for Visual Studio Code 扩展更新 1.1.4  

<!-- Title: Edge Devtools for Visual Studio code extension update 1.1.4  -->  
<!-- Subtitle: Latest changes including a favicon is displayed next to each of the instances and console messages from the browser are displayed in the console of Visual Studio Code.  -->  

适用于 Microsoft Visual Studio Code 的 [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] 扩展版本 1.1.4 现在在每个 DevTools 实例旁边显示一个网站图标。  来自 Microsoft Edge 的控制台消息现在显示在 Microsoft Visual Studio Code 的“**输出**”下的“**DevTools 控制台**”中。  Microsoft Visual Studio Code 会自动更新扩展。  若要手动更新到版本 1.1.4，请导航至“[手动更新扩展][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]”。  你可以在 [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools] 上提交问题并参与提升扩展。  

:::row:::
   :::column span="":::
      下图显示了来自 Microsoft Edge 的“**控制台**”工具中记录的示例网页的消息。  
   :::column-end:::
   :::column span="":::
      下图显示了来自 Microsoft Visual Studio Code 的“**输出**”下的“**DevTools 控制台**”中记录的示例网页的相同消息。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png" alt-text="在 Microsoft Edge DevTools 的控制台中显示消息" lightbox="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png":::
         在 Microsoft Edge DevTools 的控制台中显示消息  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png" alt-text="在 Microsoft Visual Studio Code 的“输出”下的“DevTools 控制台”中显示相同消息" lightbox="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png":::
         在 Microsoft Visual Studio Code 的“输出”下的“DevTools 控制台”中显示相同消息  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-flexbox-editing-with-visual-flexbox-editor-and-multiple-overlays"></a>通过可视弹性框编辑器和多个覆盖改进了 CSS 弹性框编辑  

<!-- Title: Try different CSS flexbox layouts with the visual flexbox editor  -->  
<!-- Subtitle: In the Styles pane, choose the icon that appears next to display: flex to try different layout properties for flex containers.  -->  

DevTools 现在具有专用的 CSS 弹性框调试工具。  如果将 `display: flex` 或 `display: inline-flex` CSS 样式应用于 HTML 元素，则“**元素**”工具中该元素旁边将显示 `flex` 图标。  若要在网页上显示（或隐藏）弹性覆盖，请选择 `flex` 图标。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1166710][CR1166710] 和 [1175699][CR1175699]。  

:::row:::
   :::column span="":::
      若要打开**弹性框**编辑器，请导航至“**样式**”窗格，然后选择 `display: flex` 或 `display: inline-flex` 样式旁边的新图标。  **弹性框**编辑器提供了一种快速编辑弹性框属性的方法。  
   :::column-end:::
   :::column span="":::
      此外，“**布局**”窗格中的“**弹性框**”部分将显示网页上的所有弹性框元素。  你可以切换每个元素的覆盖。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-styles-display-flex-window.msft.png" alt-text="CSS 弹性框调试工具" lightbox="../../media/2021/02/elements-styles-display-flex-window.msft.png":::
         CSS 弹性框调试工具  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png" alt-text="“布局”窗格中的“弹性框”部分" lightbox="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png":::
         “**布局**”窗格中的“**弹性框**”部分  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="keyboard-navigation-improvements-for-network-requests"></a>网络请求的键盘导航改进  

<!-- Title: Navigate the request initiator chain in the Network tool with the keyboard  -->  
<!-- Subtitle: The Initiator pane may now be expanded or collapsed with the arrow keys.  -->  

以前，在“**发起程序**”窗格中，你无法使用键盘上的箭头键展开或折叠请求链，这与“**元素**”工具中的 DOM 不同。  当在“**网络**”工具中选择网络请求时，“**发起程序**”窗格将显示发起当前选定请求的请求链。  

在 Microsoft Edge 版本 90 中，在“**发起程序**”窗格中，你可以使用键盘上的箭头键展开或折叠请求链。  链中的焦点网络请求现在也会突出显示。  若要在“**网络**”工具中了解有关发起程序的更多信息，请导航至“[显示发起程序和依赖项][DevtoolsNetworkReferenceDisplayInitiatorsDependencies]”。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1158276][CR1158276] 和 [1160637][CR1160637]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain.msft.png" alt-text="选择一个网络请求，然后选择“发起程序”窗格" lightbox="../../media/2021/02/network-request-initiator-chain.msft.png":::
         选择一个网络请求，然后选择“**发起程序**”窗格  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png" alt-text="展开或折叠请求发起程序链并遵循突出显示的行" lightbox="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png":::
         展开或折叠请求发起程序链并遵循突出显示的行  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="filtering-in-the-console-is-more-consistent"></a>控制台中的筛选更加一致  

<!-- Title: Console improvements make filtering more consistent  -->  
<!-- Subtitle: The Log Levels dropdown is more clearly disabled when using filters in the Console sidebar.  -->  

当使用[控制台边栏][DevtoolsConsoleReferenceOpenConsoleSidebar]进行筛选时，“[日志级别][DevtoolsConsoleReferenceFilterByLogLevel]”下拉列表中的筛选器不可用。  以前，“**日志级别**”下拉列表在你悬停时会突出显示，即使从**控制台边栏**中选择了筛选器也是如此。  在 Microsoft Edge 版本 90 中，当你从**控制台边栏**中选择筛选器后将鼠标悬停在“**日志级别**”下拉列表上时，它不再突出显示。  若要了解有关**控制台**中的筛选的更多信息，请导航至“[筛选消息][DevtoolsConsoleReferenceFilterMessages]”。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-old.msft.png" alt-text="以前，如果打开控制台边栏并将鼠标悬停在“默认级别”上，它会突出显示" lightbox="../../media/2021/02/console-sidebar-default-levels-old.msft.png":::
         以前，如果打开**控制台边栏**并将鼠标悬停在“**默认级别**”上，它会突出显示  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-new.msft.png" alt-text="从 Microsoft Edge 90 开始，如果你选择控制台边栏并将鼠标悬停在“默认级别”上，它不会突出显示" lightbox="../../media/2021/02/console-sidebar-default-levels-new.msft.png":::
         从 Microsoft Edge 90 开始，如果你选择**控制台边栏**并将鼠标悬停在“**默认级别**”上，它不会突出显示  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="the-console-now-escapes-double-quote-characters"></a>控制台现在可对双引号字符进行转义  

以前，**控制台**不在 JavaScript 字符串中输出有效的双引号 (`"`) 字符。  从 Microsoft Edge 版本 90 开始，**控制台**将使用转义的双引号 (`"`) 字符输出 JavaScript 字符串。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1178530][CR1178530]。  

:::image type="complex" source="../../media/2021/02/console-string-formatted-double-quotes.msft.png" alt-text="控制台将使用转义的双引号 (&#0022;) 字符输出 JavaScript 字符串" lightbox="../../media/2021/02/console-string-formatted-double-quotes.msft.png":::
   **控制台**将使用转义的双引号 (`"`) 字符输出 JavaScript 字符串  
:::image-end:::  

### <a name="emulate-the-css-color-gamut-media-feature"></a>模拟 CSS 色域媒体功能  

[色域][ChromestatusFeature5354410980933632]媒体查询会模拟浏览器和你正在测试的设备支持的大致颜色范围。  “**模拟 CSS 媒体功能色域**”下的下拉列表包含 DevTools 可能模拟的颜色空间。  例如，若要触发 `color-gamut: p3` 媒体查询，请从下拉列表中选择“**色域：p3**”。  

若要模拟 CSS 色域媒体功能，请完成以下操作。  

1.  打开“[命令菜单][DevtoolsCommandMenuIndex]”。  
1.  键入 `Rendering`。  
1.  运行“**显示呈现**”命令。  
1.  导航到“**模拟 CSS 媒体功能色域**”并选择一个选项。  

若要了解有关 `color-gamut` 功能的更多信息，请导航到“[颜色显示质量：‘色域’功能][CsswgDraftsMediaqueries4ColorGamut]”。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1073887][CR1073887]。  

:::image type="complex" source="../../media/2021/02/rendering-css-color-gamut.msft.png" alt-text="模拟 CSS 色域媒体功能" lightbox="../../media/2021/02/rendering-css-color-gamut.msft.png":::
   模拟 CSS 色域媒体功能  
:::image-end:::  

### <a name="improved-progressive-web-apps-tooling"></a>改进了渐进式 Web 应用工具  

#### <a name="pwa-installability-warning-in-the-console"></a>控制台中的 PWA 可安装性警告  

现在，“**控制台**”现在将显示更详细的[渐进式 Web 应用 (PWA)][ProgressiveWebAppsIndex] 可安装性警告消息，其中包含指向“[改进渐进式 Web 应用脱机支持检测][ChromeDeveloperBlogImprovedPwaOfflineDetection]”的链接。  

:::image type="complex" source="../../media/2021/02/console-pwa-installability.msft.png" alt-text="“控制台”工具中的 PWA 可安装性警告" lightbox="../../media/2021/02/console-pwa-installability.msft.png":::
   “**控制台**”工具中的 PWA 可安装性警告  
:::image-end:::  

#### <a name="pwa-description-length-warning-in-the-manifest-pane"></a>“清单”窗格中的 PWA 说明长度警告

如果清单说明超过了 324 个字符，“**清单**”窗格现在将显示一条警告消息。  

:::image type="complex" source="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png" alt-text="PWA 说明截断警告" lightbox="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png":::
   PWA 说明截断警告  
:::image-end:::  

若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [965802][CR965802]、[1146450][CR1146450] 和 [1169689][CR1169689]。  

### <a name="new-remote-address-space-column-in-the-network-tool"></a>“网络”工具中新的“远程地址空间”列  

<!-- does not work in canary 90.0.813.0 -->  
新的“**远程地址空间**”列显示每个网络资源的网络 IP 地址空间。  若要显示新的“远程地址空间”列，请完成以下操作。  

1.  导航到“**网络**”工具。  
1.  在“请求”表中，将鼠标悬停在标题行上，然后打开上下文菜单（右键单击）。  若要了解如何在“请求”表中添加或删除列，请导航到“[添加或删除列][DevtoolsNetworkReferenceAddRemoveColumns]。  
1.  选择“**远程地址空间**”。  
    
现在，“请求”表将显示一个标题为“**远程地址空间**”的新列。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1128885][CR1128885]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png" alt-text="在上下文菜单中，选择“远程地址空间”" lightbox="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png":::
         在上下文菜单中，选择“**远程地址空间**”  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-remote-address-space.msft.png" alt-text="“请求”表现在显示“远程地址空间”列" lightbox="../../media/2021/02/network-requests-remote-address-space.msft.png":::
         “请求”表现在显示“**远程地址空间**”列 :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-allowed-and-disallowed-features-in-the-frame-details-view"></a>在“框架详细信息”视图中显示允许和禁止的功能  

“框架详细信息”视图现在显示受“[权限策略][GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]”控制的允许和禁止的浏览器功能列表。  “权限策略”是一种 Web 平台 API，它允许（或阻止）网页在单个框架或其嵌入的 iframe 中使用浏览器功能。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1158827][CR1158827]。  

:::image type="complex" source="../../media/2021/02/application-frames-permissions-policy.msft.png" alt-text="基于权限策略允许和禁止的功能" lightbox="../../media/2021/02/application-frames-permissions-policy.msft.png":::
   基于权限策略允许和禁止的功能  
:::image-end:::  

### <a name="new-sameparty-column-in-the-cookies-pane"></a>“Cookie”窗格中新的“SameParty”列  

“**应用程序**”工具中的“**Cookie**”窗格现在显示每个 Cookie 的 `SameParty` 属性。  `SameParty` 属性是一个新的布尔属性，用于指示在对相同[第一方集][GithubPrivacycgFirstPartySets]的起源的请求中是否包含 cookie。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1161427][CR1161427]。  

:::image type="complex" source="../../media/2021/02/application-storage-cookies-sameparty.msft.png" alt-text="“Cookie”窗格中的“SameParty”列" lightbox="../../media/2021/02/application-storage-cookies-sameparty.msft.png":::
   “**Cookie**”窗格中的“**SameParty**”列  
:::image-end:::  

### <a name="fndisplayname-property-in-the-console-tool-is-now-deprecated"></a>“控制台”工具中的 fn.displayName 属性现已弃用  

以前，`fn.displayName` 属性允许你控制要在 `error.stack` 和 DevTools 堆栈跟踪中显示的函数的调试名称。  从 Microsoft Edge 版本 90 开始，`fn.displayName` 属性现已弃用，并替换为 `fn.name` 属性。  使用标准 `Object.defineProperty` 方法定义 `fn.name` 属性。  若要了解有关 `fn.name` 的更多信息，请导航至 [Function.name][MdnJavascriptReferenceGlobalObjectsFunctionName]。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1177685][CR1177685]。  

:::image type="complex" source="../../media/2021/02/console-display-name-name.msft.png" alt-text="用于控制函数的调试名称的 fn.name 属性示例" lightbox="../../media/2021/02/console-display-name-name.msft.png":::
   用于控制函数的调试名称的 `fn.name` 属性示例  
:::image-end:::  

### <a name="full-accessibility-tree-view-in-the-elements-tool"></a>“元素”工具中的完整辅助功能树视图  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

此试验在“**元素**”工具中提供**完整的辅助功能树视图**。  “[辅助功能][DevtoolsAccessibilityReferenceTheAccessibilityPane]”窗格提供部分辅助功能树视图，其显示从根节点到被检查节点的直接上级链。  
启用此试验并重新加载 DevTools 后，请选择以下按钮之一以在“元素”工具中切换网页上所有元素的显示。  

*   若要显示完整的辅助功能树视图，请选择“**切换到辅助功能树视图**”。  
*   若要显示 DOM 树视图，请选择“**切换到 DOM 树视图**”。  
    
若要启用试验，请导航至“[启用试验功能][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]”，然后选中“**在‘元素’窗格中启用完整的辅助功能树视图**”旁边的复选框。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [887173][CR887173]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png" alt-text="显示 DOM 树视图" lightbox="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png":::
         显示 **DOM 视图**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png" alt-text="显示完整的辅助功能树视图" lightbox="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png":::
         显示**完整的辅助功能树视图**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsAccessibilityReferenceTheAccessibilityPane]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#the-accessibility-pane "“辅助功能”窗格 - 辅助功能参考 | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterByLogLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "按日志级别筛选 - 控制台参考 | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterMessages]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-messages "筛选消息 - 控制台参考 | Microsoft Docs"  
[DevtoolsConsoleReferenceOpenConsoleSidebar]: /microsoft-edge/devtools-guide-chromium/console/reference#open-the-console-sidebar "打开控制台边栏 - 控制台参考 | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 中的键盘快捷方式 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexEnablePlusButtonTabMenusToOpenMoreTools]: /microsoft-edge/devtools-guide-chromium/experimental-features/index#enable--button-tab-menus-to-open-more-tools "启用 + 按钮选项卡菜单以打开更多工具 - 试验功能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features/index#turn-on-experimental-features "打开试验功能 - 试验功能 | Microsoft Docs"  
[DevtoolsNetworkReferenceAddRemoveColumns]: /microsoft-edge/devtools-guide-chromium/network/reference#add-or-remove-columns "添加或删除列 - 网络分析参考 | Microsoft Docs"  
[DevtoolsNetworkReferenceDisplayInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#display-initiators-and-dependencies "显示发起程序和依赖项 - 网络分析参考 | Microsoft Docs"  

[ProgressiveWebAppsIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用概述 | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  

[ChromeDeveloperBlogImprovedPwaOfflineDetection]: https://developer.chrome.com/blog/improved-pwa-offline-detection "改进渐进式 Web 应用脱机支持检测 | Chrome 开发人员"  

[ChromestatusFeature5354410980933632]: https://www.chromestatus.com/feature/5354410980933632 "色域媒体功能 | Chrome 平台状态"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR174309]: https://crbug.com/174309 "问题 174309：DevTools：允许自定义键盘快捷方式/键绑定 | Chromium bug"  
[CR887173]: https://crbug.com/887173 "问题 887173：DevTools：完整的辅助功能树检查 | Chromium bug"  
[CR965802]: https://crbug.com/965802 "问题 965802：实现更准确的服务工作进程脱机功能检测 | Chromium bug"  
[CR1073887]: https://crbug.com/1073887 "问题 1073887：DevTools：@media (color-gamut: ...) 颜色空间模拟 | Chromium bug"  
[CR1128885]: https://crbug.com/1128885 "问题 1128885：DevTools 对 CORS-RFC1918 的支持 | Chromium bug"  
[CR1146450]: https://crbug.com/1146450 "问题 1146450：[Android] 实施底页安装 | Chromium bug"  
[CR1158276]: https://crbug.com/1158276 "问题 1158276：在 DevTools 的“网络”部分中无法使用箭头键展开/收起“请求发起程序链”窗格 | Chromium bug"  
[CR1158827]: https://crbug.com/1158827 "问题 1158827：[权限策略] 实现对权限策略的 devtool 支持 | Chromium bug"  
[CR1160637]: https://crbug.com/1160637 "问题 1160637：在“开发人员工具”窗口的“网络”部分发现“请求发起程序链”上的焦点不完整 | Chromium bug"  
[CR1161427]: https://crbug.com/1161427 "问题 1161427：&#9730; 在 DevTools 中支持 SameParty Cookie 属性调试 | Chromium bug"  
[CR1166710]: https://crbug.com/1166710 "问题 1166710：默认情况下打开弹性框工具试验 | Chromium bug"  
[CR1169689]: https://crbug.com/1169689 "问题 1169689：PWA 安装底页不应具有类别 | Chromium bug"  
[CR1175699]: https://crbug.com/1175699 "问题 1175699：弹性框编辑器 | Chromium bug"  
[CR1177685]: https://crbug.com/1177685 "问题 1177685：删除非标准 fn.displayName 支持 | Chromium bug"  
[CR1178530]: https://crbug.com/1178530 "问题 1178530：在打印字符串时，控制台不会转义双引号 | Chromium bug"  

[CsswgDraftsMediaqueries4ColorGamut]: https://drafts.csswg.org/mediaqueries-4#color-gamut "颜色显示质量：“色域”功能 | CSS 工作组编辑器草稿"  

[GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/main/DevTools/FocusMode/explainer.md "DevTools：焦点模式 UI - MicrosoftEdge/MSEdgeExplainers | GitHub"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubPrivacycgFirstPartySets]: https://github.com/privacycg/first-party-sets "第一方集 | GitHub"  

[GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "权限策略解释器 | GitHub"  

[MdnJavascriptReferenceGlobalObjectsFunctionName]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Function/name "Function.name | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/updates/2021/02/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
