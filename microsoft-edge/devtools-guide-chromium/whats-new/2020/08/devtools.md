---
description: 将键盘快捷方式匹配到Visual Studio代码、模拟 Surface Duo 和 Samsung 一起折叠、CSS 网格覆盖改进等。
title: 'Microsoft Edge 86 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 3853f097877fc45b14ceb0674309cb35b58a0aa6
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398614"
---
# <a name="whats-new-in-devtools-microsoft-edge-86"></a>Microsoft Edge 86 (DevTools 中的新增)   

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>来自 Microsoft Edge 开发人员工具团队公告  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### <a name="match-keyboard-shortcuts-in-devtools-to-visual-studio-code"></a>将 DevTools 中的键盘快捷方式与Visual Studio代码匹配  

在 Microsoft Edge 86 中，你可以将 DevTools 中的键盘快捷方式与 Microsoft Visual Studio [代码中的快捷方式匹配][VisualStudioCode]。  

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="将 DevTools 中的键盘快捷方式与Visual Studio代码匹配" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   将 DevTools 中的键盘快捷方式与Visual Studio代码匹配  
:::image-end:::  

若要激活此功能，请导航到 ["自定义 Microsoft Edge DevTools"中的键盘快捷方式][DevtoolsCustomizeShortcuts]。  

例如，用于暂停或继续运行代码中的脚本的键盘 [快捷方式Visual Studio为][VisualStudioCodeShortcutsKeyboardWindows] `F5` 。  使用**DevTools (默认**) 预设，在 DevTools 中相同的快捷方式是，但当你选择 Visual Studio 代码预设时， `F8` 该快捷方式现在也是**** `F5` 。  

Chromium 问题 [#174309][CR174309]  

### <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a>模拟 Surface Duo 和 Samsung 一起折叠  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

现在，你能够在两台新设备上测试网站或应用的外观：Microsoft Edge 中的 Surface  [Duo 和][MicrosoftSurfaceDevicesDuo] [Samsung 更新][SamsungMobileGalaxyFold] 折线。  

为了帮助增强适用于双屏和可折叠设备的网站或应用，在模拟设备时，请使用 [以下功能][DevtoolsDeviceModeIndex]。  

*   [跨越，][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]即你的网站 \ (或 app\) 跨两个屏幕显示。
*   [呈现接层][DualScreenIntroductionHowWorkSeam]，这是两个屏幕之间的空间。
*   [使实验性 Web 平台 API][DevtoolsExperimentalFeaturesEnableExperimentalApis]能够访问新的[CSS 媒体][DualScreenWebCssMediaSpanning]屏幕跨越功能以及[JavaScript getWindowSegments API。][DualScreenWebJavascriptGetwindowsegments]  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="Surface Duo 的设备仿真" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   Surface Duo 的设备仿真  
:::image-end:::  

若要打开此实验功能，请导航到" [打开实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 功能"并选择模拟旁边的复选框： **支持双屏模式**。  

有关此实验的信息，请导航到仿真 [：支持双屏模式][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]。  

Chromium 问题 [：#1054281][CR1054281]  

### <a name="css-grid-overlay-improvements-and-new-experimental-grid-features"></a>CSS 网格覆盖改进和新的实验网格功能  

感谢你提供有关改进的 CSS 网格覆盖的正面反馈。  CSS 网格覆盖现在默认启用，不需要你打开实验。  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="文章元素的 CSS 网格覆盖" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   元素的 CSS 网格 `article` 覆盖  
:::image-end:::  

> [!NOTE]
> 有关网格覆盖层详细信息，请导航到 [CSS 网格调试功能][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]。  

Microsoft Edge DevTools 团队和 Chrome DevTools 团队协作处理其他功能。  新功能包括多个覆盖，这些覆盖从"元素"工具上的新"布局****"窗格持久且**可配置**。  

若要启用此实验性功能，请导航[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]到"打开实验功能"并选择"启用新的 CSS 网格调试功能 (配置选项旁边的复选框，这些配置选项在重启后在元素的布局边栏窗格中 **) 。 **  

有关此实验的信息，请导航到["启用新的 CSS 网格调试功能"。][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]  

Chromium 问题 [：#1047356][CR1047356]  

### <a name="table-copied-from-the-console-preserves-formatting"></a>从控制台复制的表保留格式  

在 Microsoft Edge 85 或更早版本中，复制的格式 `console.table` 丢失。  如果复制了来自 [表控制台][DevtoolsConsoleApiTable] API 的输出并粘贴它，则只保留该表的文本。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="Microsoft Edge 85 或更早版本中的表控制台 API 输出" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` Microsoft Edge 85 或更早版本中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 85 或更早版本粘贴到 Visual Studio 代码的表控制台 API 输出" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` Microsoft Edge 85 或更早版本粘贴到 Visual Studio 代码中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 Microsoft Edge 86 或更高版本中，从 **控制台**复制表时，格式设置现已保留。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="Microsoft Edge 86 或更高版本中的表控制台 API 输出" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` Microsoft Edge 86 或更高版本中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 86 或更高版本的表控制台 API 输出粘贴到Visual Studio代码" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` Microsoft Edge 86 或更高版本的控制台 API 输出粘贴到Visual Studio代码  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium 问题：[#1115011][CR1115011]  

### <a name="source-order-viewer-for-easier-accessibility-testing"></a>源订单查看器，便于辅助功能测试  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

新的辅助功能帮助程序显示源中元素的顺序。  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="激活"显示源顺序"" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   激活 **"显示源顺序"**  
:::image-end:::  

利用此功能，可以更轻松地测试屏幕阅读器和键盘用户体验网站或应用的方式。  屏幕阅读器和键盘导航取决于网站或应用的源代码中按特定顺序放置的内容，以便与呈现的页面匹配。  源订单查看器显示呈现的页面和源代码之间潜在的顺序差异。  

若要打开此实验性功能，请导航到 ["打开实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 功能"，然后选择"启用源 **订单查看器"旁边的复选框**。  

有关此实验详细信息，请导航到["启用源订单查看器"。][DevtoolsExperimentalFeaturesEnableSourceOrderViewer]  

Chromium 问题 [：#1094406][CR1094406]  

<!--
### DevTools language enhancements  

Your feedback and internal discoveries uncovered which text strings used in the Microsoft Edge feedback should remain untranslated or create confusion when translated.  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-stable.msft.png" alt-text="Microsoft Edge DevTools in Traditional Chinese" lightbox="localization-improvements-chinese-complex-stable.msft.png":::
         Microsoft Edge DevTools 85 and earlier in Traditional Chinese  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png" alt-text="Microsoft Edge DevTools in Japanese" lightbox="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png":::
         Microsoft Edge DevTools 86  or later in Traditional Chinese  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.  

The current effort to improve translation quality enables easier support for more languages in the future.  
-->  

### <a name="highlight-all-search-results-in-elements-tool"></a>在"元素"工具中突出显示所有搜索结果  

在 Microsoft Edge 84 和 85 中****，"元素"工具的第一个搜索结果未突出显示。  其余搜索结果已正确突出显示。  

感谢你发送反馈并帮助改进 Chromium。  您的反馈发现了#1103316 [][CR1103316] Chromium 项目中的问题。  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="突出显示 Microsoft Edge 84 或更高版本中的"元素"面板上的第一个搜索结果" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   在 Microsoft Edge **** 84 或更高版本的元素工具上突出显示第一个搜索结果  
:::image-end:::  

此问题现已在 Microsoft Edge 的所有版本中得到解决。  

Chromium 问题 [：#1103316][CR1103316]  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-media-tool"></a>新媒体工具  

DevTools 现在在媒体工具中显示 [媒体播放器][DevtoolsMediaPanelIndex] 信息。  

若要打开新的 **媒体** 工具，请完成以下步骤。  

1.  Choose **Customize and control DevTools** \ (`...` \) > More **tools**  >  **Media**.  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="新媒体工具" lightbox="../../media/2020/08/media-panel.msft.png":::
       新 **媒体** 工具  
    :::image-end:::  

在 DevTools 中的新 **媒体** 工具之前，有关视频播放器的日志记录和调试信息位于"最近使用播放器 **"** 设置下。  若要打开 **"最近的玩家"** 设置，请导航 `edge://media-internals` 到并选择 **"玩家"** 工具。  

更快速地查看实时内容并检查潜在问题，包括以下示例。  

*   为什么丢弃帧？  
*   为什么 JavaScript 以意外方式与玩家交互？  

### <a name="capture-node-screenshots-using-the-elements-tool-context-menu"></a>使用"元素"工具上下文菜单捕获节点屏幕截图  

现在，可以使用"元素"工具中的上下文菜单捕获 **节点** 屏幕截图。  

例如，若要获取目录的屏幕截图，请将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，然后选择"捕获" **节点屏幕截图**。  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="捕获节点屏幕截图" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   捕获节点屏幕截图  
:::image-end:::  

Chromium 问题 [：#1100253][CR1100253]  

### <a name="issues-tool-updates"></a>问题工具更新  

控制台工具上的"问题"**** 警告栏现在替换为常规消息。  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text="控制台消息中的问题" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   控制台消息中的问题  
:::image-end:::  

默认情况下，第三方 Cookie 问题在"问题"工具 **中处于隐藏** 状态。  启用新的 **"包含第三方 Cookie 问题** "复选框以查看问题。  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="第三方 Cookie 问题复选框" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   第三方 Cookie 问题复选框  
:::image-end:::  

Chromium 问题：1096481、1068116、1080589 [][CR1096481] [][CR1068116] [][CR1080589]  

### <a name="emulate-missing-local-fonts"></a>模拟缺少的本地字体  

打开 [呈现工具并使用][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] 新的"禁用本地 **字体** "功能模拟规则 `local()` 中缺少 `@font-face` 的源。  

例如，当字体安装在设备上并且规则使用它作为字体时，Microsoft Edge 将使用设备中的本地 `Rubik` `@font-face src` `local()` 字体文件。  

启用 **"禁用本地字体** "后，DevTools 将忽略 `local()` 这些字体，然后从网络提取每个字体。  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="模拟缺少的本地字体" lightbox="../../media/2020/08/disable-font.msft.png":::
   模拟缺少的本地字体  
:::image-end:::  

如果在开发过程中使用同一字体的两个不同副本，例如以下示例。  

*   设计工具的本地字体。  
*   代码的 Web 字体。  

使用 **"禁用本地字体** "可以更轻松地完成以下任务。  

*   调试并度量 Web 字体的加载性能和优化。  
*   验证 CSS 规则 `@font-face` 的准确性。  
*   发现设备上安装的本地版本与 Web 字体之间的差异。  

Chromium 问题 [：#384968][CR384968]  

### <a name="emulate-inactive-users"></a>模拟非活动用户  

空闲 [检测 API][WebDevIdleDetection] 允许开发人员检测非活动用户，并响应空闲状态更改。  你现在可以使用 DevTools 在传感器工具中模拟用户状态和屏幕**** 状态中的空闲状态更改，而不是等待实际空闲状态更改。  You may open the **Sensors** tool from the [Drawer][DevtoolsCustomizeIndexDrawer].  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="模拟非活动用户" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   模拟非活动用户  
:::image-end:::  

Chromium 问题 [：#1090802][CR1090802]  

### <a name="emulate-prefers-reduced-data"></a>模拟首选-减少数据  

> [!NOTE]
> 在 Microsoft Edge 86 中，若要启用此功能，请导航到实验 `edge://flags#enable-experimental-web-platform-features` **性 Web 平台功能标志并打开它** 。  只有在启用标志时，才显示模拟选项。  

首选 [的缩减数据][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] 媒体查询可检测减少数据的用户内容首选项。  如果选中，用户将收到使用较少数据的备用页面内容。  

你现在可以使用 DevTools 模拟 `prefers-reduced-data` 媒体查询。  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="模拟首选-减少数据" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   模拟首选-减少数据  
:::image-end:::  

Chromium 问题 [：#1096068][CR1096068]  

### <a name="support-for-new-javascript-features"></a>支持新的 JavaScript 功能  

DevTools 现在更好地支持以下 JavaScript 语言功能。  

| JavaScript 语言功能 | 详细信息 |  
|:--- |:--- |  
| [逻辑赋值运算符][V8FeaturesLogicalAssignment] | DevTools 现在支持使用控制台和源工具中的新运算符和运算符 `&&=` `||=` `??=` 进行逻辑**** 分配。 ****  |  
| 彩色数字 [分隔符][V8FeaturesNumericSeparators] | DevTools 现在在源工具中正确打印数字 **分隔** 符。  |  

Chromium 问题 [：1086817][CR1086817] [、1080569][CR1080569]  

### <a name="lighthouse-62-in-the-lighthouse-panel"></a>Lighthouse 面板中的 Lighthouse 6.2  

**Lighthouse**工具现在运行 Lighthouse 6.2。  有关更改的完整列表，请导航到 [Lighthouse 发行说明][GithubGooglechromeLighthouseV620]。  

Chromium 问题 [：#772558][CR772558]  

### <a name="deprecation-of-other-origins-listing-in-the-service-workers-pane"></a>服务工作人员窗格中其他源列表的弃用  

DevTools 现在提供来自服务工作者**** 窗格 \ (**应用程序**工具 >**服务**工作者窗格\) 的链接，以查看来自其他源的服务工作者的完整列表。  若要在不打开 DevTools 的情况下访问列表，请导航到 `edge://service-worker-internals/?devtools` 。  

以前，DevTools 显示一个嵌套在**应用程序工具>****服务工作者窗格下**的列表。  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="链接到其他源" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   链接到其他源  
:::image-end:::  

Chromium 问题 [：#807440][CR807440]  

### <a name="show-coverage-summary-for-filtered-items"></a>显示已筛选项目的覆盖摘要  

DevTools 现在动态重新计算并显示覆盖信息的摘要。  在"覆盖"工具中应用筛选器时 [，将触发][DevtoolsCoverageIndex] 动态显示。  在 **"覆盖** "工具始终显示所有覆盖信息的摘要之前。  

在下列第一个图表中，摘要最初显示，在下列第二个图表上，摘要在 `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` 应用 CSS 筛选 `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` 后显示。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="范围摘要" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         范围摘要  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="已筛选项目的范围摘要" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         已筛选项目的范围摘要  
      :::image-end:::  
   :::column-end:::
:::row-end:::

Chromium 问题 [：#1061385][CR1090802]  

### <a name="new-frame-details-view-in-application-panel"></a>应用程序面板中的新帧详细信息视图  

DevTools 现在显示每个帧的详细视图。  若要访问它，请选择"应用程序"工具 **中的"** 框架"菜单 **下的** 图文框。  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="应用程序面板中框架的新详细视图" lightbox="../../media/2020/08/frame-details.msft.png":::
   应用程序工具中 **框架的新详细** 视图  
:::image-end:::  

Chromium 问题 [：#1093247][CR1093247]  

#### <a name="frame-details-for-opened-windows"></a>打开的窗口的框架详细信息  

打开窗口和弹出窗口现在也显示在框架树下。  打开的窗口的详细视图包括其他安全信息。  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="打开的窗口的新框架详细视图" lightbox="../../media/2020/08/window-opener.msft.png":::
   打开的窗口的新框架详细视图  
:::image-end:::  

Chromium 问题：[#1107766][CR1107766]  

#### <a name="security-and-isolation-information"></a>安全和隔离信息  

安全上下文 [、Cross-Origin-Embedder-Policy (COEP) ][WebDevCoopCoep]和 [Cross-Origin-Opener-Policy (COOP) 现在 ][WebDevCoopCoep] 显示在帧详细信息中。  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="安全和隔离信息" lightbox="../../media/2020/08/coep-coop.msft.png":::
   安全和隔离信息  
:::image-end:::  

将来，Microsoft Edge DevTools 团队和 Chrome DevTools 团队计划向框架详细信息添加更多安全信息。  

Chromium 问题 [：#1051466][CR1051466]  

### <a name="elements-and-network-panel-updates"></a>元素和网络面板更新  

#### <a name="accessible-color-suggestion-in-the-styles-pane"></a>"样式"窗格中的辅助颜色建议  

DevTools 现在提供低色对比度文本的颜色建议。  

在下面的示例中， `h1` 具有低对比度文本。  若要修复此问题，请打开"样式"窗格中 `color` 属性 **的颜色** 选取器。  展开"对 **比率"部分** 后，DevTools 将提供 AA 和 AAA 颜色建议。  选择建议的颜色以应用颜色。  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="颜色选取器建议 AA 和 AAA 颜色建议" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   颜色选取器建议 AA 和 AAA 颜色建议  
:::image-end:::  

Chromium 问题 [：#1093227][CR1093227]  

#### <a name="reinstate-properties-pane-in-the-elements-panel"></a>"元素"面板中的"恢复属性"窗格  

" **属性** "窗格已返回。  它在 [Microsoft Edge 84 中已弃用][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]。  Microsoft Edge DevTools 团队和 Chrome DevTools 团队正在计划改进以检查元素的属性。  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text=""元素"面板中的"属性"窗格" lightbox="../../media/2020/08/properties-pane.msft.png":::
   **"** 元素"工具 **中的"属性"** 窗格  
:::image-end:::  

Chromium 问题：  <!--  [#1105205][CR1105205],  -->  [#1116085][CR1116085]  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="Human-readable `X-Client-Data` header values" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### <a name="autocomplete-custom-fonts-in-the-styles-pane"></a>在"样式"窗格中自动完成自定义字体  

现在，在"样式"窗格中编辑属性时，导入的字体将添加到 CSS `font-family` 自动完成列表中。 ****  

例如， `monospace` 如果本地计算机上安装了自定义字体，则它会显示在 CSS 完成列表中。  在以前版本的 Microsoft Edge 中，不显示字体。

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="自动完成自定义字体" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   自动完成自定义字体  
:::image-end:::  

Chromium 问题：[#1106221][CR1106221]  

#### <a name="consistently-display-resource-type-in-network-panel"></a>在"网络"面板中一致地显示资源类型  

DevTools 现在一致地显示与原始网络请求相同的资源类型，当重定向 \ (HTTP 状态代码 `/ Redirect` 302\) 时追加到 Type**** 列值。  

以前，DevTools 有时将类型 `Other` 更改为。  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="显示重定向资源类型" lightbox="../../media/2020/08/network-redirect.msft.png":::
   显示重定向资源类型  
:::image-end:::  

Chromium 问题 [：#997694][CR997694]  

#### <a name="clear-buttons-in-the-elements-and-network-tools"></a>清除元素和网络工具中的按钮  

以下文本框现在具有 **"清除"** 按钮。  

*   "样式"窗格**和网络工具中的****筛选器**文本框。  
*   元素工具中的 DOM **搜索文本框** 。  

选择 **"清除** "按钮可删除任何输入的文本。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="清除"元素"面板中的按钮" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         "元素"工具中的 **"清除"** 按钮  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="清除网络面板中的按钮" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         清除网络工具  **中的** 按钮  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium 问题 [：#1067184][CR1067184]  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools 设置图标"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel "元素面板中的"属性"窗格弃用 - Microsoft Edge 84 (DevTools 中的新增) |Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能 - Microsoft Edge 85 (DevTools 中的新增) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 API - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器 - 实验|Microsoft Docs"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "打开实验性功能 - 实验|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表 - 控制台 API 参考|Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "在 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "箱 - 自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "使用"呈现"选项卡分析呈现性能 - 性能分析参考|Microsoft Docs"  
[DevtoolsMediaPanelIndex]: /microsoft-edge/devtools-guide-chromium/media-panel/index "查看和调试媒体播放器|Microsoft Docs"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "如何使用接点 - 双屏设备简介|Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏幕检测的 CSS 媒体屏幕|Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio代码 "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Windows 的代码键盘快捷方式"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定|Chromium Bug"
[CR384968]: https://crbug.com/384968 "用于忽略本地字体 () 选项|Chromium Bug"  
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR807440]: https://crbug.com/807440 "Chrome 会锁定大量 SW |Chromium Bug"  
[CR997694]: https://crbug.com/997694 "状态为 302 的 XHR 请求不会显示在网络面板中的"xhr"筛选器|Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/Table 工具|Chromium Bug"  
[CR1051466]: https://crbug.com/1051466 "支持 DevTools | 中的 COOP/COEP 调试Chromium Bug"  
[CR1054281]: https://crbug.com/1054281 "功能请求：DevTools 应模拟可折叠和双屏幕设备|Chromium Bug"  
[CR1067184]: https://crbug.com/1067184 "功能请求：清除 Network & 元素上的筛选器>样式筛选器|Chromium Bug"  
[CR1068116]: https://crbug.com/1068116 "☂发货问题面板|Chromium Bug"  
[CR1080569]: https://crbug.com/1080569 "acorn 不支持逻辑分配运算符|Chromium Bug"  
[CR1080589]: https://crbug.com/1080589 "按第三方/第一方网站分类|Chromium Bug"  
[CR1086817]: https://crbug.com/1086817 "acorn 不支持数字分隔符|Chromium Bug"  
[CR1090802]: https://crbug.com/1090802 "模拟空闲检测 API 中的空闲状态|Chromium Bug"  
[CR1093227]: https://crbug.com/1093227 "DevTools：建议最接近的辅助颜色|Chromium Bug"  
[CR1093247]: https://crbug.com/1093247 "显示有关应用程序面板中框架|Chromium Bug"  
[CR1094406]: https://crbug.com/1094406 "开发人员需要 AT 的源订单查看器 https://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools：支持模拟首选的减少数据媒体功能|Chromium Bug"  
[CR1096481]: https://crbug.com/1096481 "问题横幅放置|Chromium Bug"  
[CR1100253]: https://crbug.com/1100253 "在元素上下文菜单菜单中添加屏幕截图节点|Chromium Bug"  
[CR1103316]: https://crbug.com/1103316 "元素搜索不会解析Node (突出显示文本等) 第一个搜索结果|Chromium Bug"  
[CR1103854]: https://crbug.com/1103854 "开发人员工具中心中的 X-Client-Data 值|Chromium Bug"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]："将导入的字体添加到"样式"面板中的字体系列 https://crbug.com/1106221 |Chromium bug"  
[CR1107766]："显示有关框架树中 https://crbug.com/1107766 由"window.open () "生成的帧|Chromium bug"  
[CR1115011]："从控制台复制表时，不会保留该表 https://crbug.com/1115011 |Chromium bug"  
[CR1116085]：" https://crbug.com/1116085 请返回 DevTools 属性检查器|Chromium bug"  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "prefers-reduced-data - 媒体查询级别 5 |W3C CSS 工作组编辑器草稿"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v6.2.0 - GoogleChrome/lighthouse |GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "协议缓冲区|Google 开发人员"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "百分百折|三星美国"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "逻辑分配|V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数字分隔符|V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "使用 COOP 和 COEP 方法使您的网站"跨源隔离|web.dev"  
[WebDevIdleDetection]: https://web.dev/idle-detection "使用空闲检测 API 工具检测非活动|web.dev"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "避免使用非复合动画|web.dev"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/updates/2020/08/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
