---
description: 将键盘快捷方式与Visual Studio Code、模拟 Surface Duo 和 Samsung Foldy Fold、CSS 网格覆盖改进等匹配。
title: 'DevTools (Microsoft Edge 86) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ec2219e9ebdd5d79c61bcaa813f7784246b1f5d0
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564943"
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
# <a name="whats-new-in-devtools-microsoft-edge-86"></a>DevTools 86 (Microsoft Edge中的新增)   

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>来自 Microsoft Edge 开发人员工具团队公告  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### <a name="match-keyboard-shortcuts-in-devtools-to-visual-studio-code"></a>将 DevTools 中的键盘快捷方式与Visual Studio Code  

在 Microsoft Edge 86 中，你可以将 DevTools 中的键盘快捷方式与代码 中的Microsoft Visual Studio[匹配][VisualStudioCodeMain]。  

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="将 DevTools 中的键盘快捷方式与Visual Studio Code" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   将 DevTools 中的键盘快捷方式与Visual Studio Code  
:::image-end:::  

若要激活此功能，请导航到自定义开发人员工具中的Microsoft Edge[快捷方式][DevtoolsCustomizeShortcuts]。  

例如，用于暂停或继续运行脚本的键盘快捷方式在 Visual Studio Code[为][VisualStudioCodeShortcutsKeyboardWindows] `F5` 。  使用**DevTools (Default) **预设，DevTools 中的同一快捷方式是 ，但在选择 Visual Studio Code 预设时，该快捷方式现在也是 `F8` **** `F5` 。  

Chromium问题[#174309][CR174309]  

### <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a>模拟 Surface Duo 和 Samsung Galaxy Fold  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

现在，你能够在两台新设备上测试网站或应用的外观[：Surface Duo][MicrosoftSurfaceDevicesDuo]和[Samsung 在][SamsungMobileGalaxyFold]Microsoft Edge。  

为帮助增强用于双屏幕和可折叠设备的网站或应用，请在[模拟设备][DevtoolsDeviceModeIndex]时使用以下功能。  

*   [跨越][DevtoolsDeviceModeDualScreenAndFoldables]，即你的网站（或应用）跨两个屏幕显示。
*   [呈现接缝][DualScreenIntroductionHowWorkSeam]，即两个屏幕之间的空间。
*   启用实验性 Web 平台 API 以访问新的[CSS 媒体][DualScreenWebCssMediaSpanning]屏幕跨越功能以及[JavaScript getWindowSegments API。][DualScreenWebJavascriptGetwindowsegments]  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="Surface Duo 的设备模拟" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   Surface Duo 的设备模拟  
:::image-end:::  

若要启用此实验功能，请导航到[打开实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]，然后选择"模拟 **： 支持双**屏幕模式"旁边的复选框。  

有关此功能的信息，请导航到模拟开发人员工具中的双屏幕和可折叠Microsoft Edge[设备][DevtoolsDeviceModeDualScreenAndFoldables]。  

Chromium问题[：#1054281][CR1054281]  

### <a name="css-grid-overlay-improvements-and-new-experimental-grid-features"></a>CSS 网格覆盖改进和新的实验网格功能  

感谢你提供有关改进的 CSS 网格覆盖的正面反馈。  CSS 网格覆盖现在默认启用，不需要你启用实验。  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="article 元素的 CSS 网格覆盖" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   元素的 CSS 网格 `article` 覆盖  
:::image-end:::  

> [!NOTE]
> 有关网格覆盖层详细信息，请导航到 [CSS 网格调试功能][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]。  

开发人员Microsoft Edge团队和 Chrome DevTools 团队共同协作开发其他功能。  新功能包括多个覆盖，这些覆盖是永久性的，并且通过"元素"**** 工具上的新"布局"窗格**可配置**。  

若要启用此实验功能，请导航到[打开实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]，然后选择"重启) 后的元素"中的"启用新的 **CSS 网格 **调试功能 (配置选项"旁边的复选框。  

有关此功能详细信息，请导航到"检查[开发人员工具Microsoft Edge CSS 网格"][DevtoolsCssGrid]。  

Chromium问题[：#1047356][CR1047356]  

### <a name="table-copied-from-the-console-preserves-formatting"></a>从控制台复制的表保留格式  

在 Microsoft Edge 85 或更早版本中，复制的格式 `console.table` 丢失。  如果从表控制台 API 复制[][DevtoolsConsoleApiTable]并粘贴了输出，则仅保留表的文本。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="表 85 或Microsoft Edge控制台 API 输出" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` Microsoft Edge 85 或更早版本中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="表 85 或更早版本Microsoft Edge控制台 API 输出粘贴到 Visual Studio Code" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` 粘贴到 Microsoft Edge 85 或更早版本中的控制台 API Visual Studio Code  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 Microsoft Edge 86 或更高版本中，从**控制台**复制表时，格式设置现已保留。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="表 86 或Microsoft Edge控制台 API 输出" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` Microsoft Edge 86 或更高版本中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="表 86 Microsoft Edge更高版本的控制台 API 输出粘贴到 Visual Studio Code" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` 粘贴到 Microsoft Edge 86 或更高版本中的控制台 API Visual Studio Code  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium问题：[#1115011][CR1115011]  

### <a name="source-order-viewer-for-easier-accessibility-testing"></a>源订单查看器，便于辅助功能测试  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

新的辅助功能帮助程序显示源中元素的顺序。  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="激活 显示源顺序" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   激活 **显示源顺序**  
:::image-end:::  

利用此功能，可以更轻松地测试屏幕阅读器和键盘用户体验网站或应用的方式。  屏幕阅读器和键盘导航取决于网站或应用的源代码中按特定顺序放置的内容，以便与呈现的页面匹配。  源顺序查看器显示呈现的页面和源代码之间潜在的顺序差异。  

若要启用此实验功能，请导航到[打开实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]，然后选择"启用源订单查看器"旁边的**复选框。**  

有关此实验的更多信息，请导航到 [Source Order Viewer][DevtoolsExperimentalFeaturesSourceOrderViewer]。  

Chromium问题[：#1094406][CR1094406]  

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

在 Microsoft Edge 84 和 85 中，"元素****"工具的第一个搜索结果未突出显示。  其余搜索结果已正确突出显示。  

感谢你发送反馈并帮助改进Chromium。  您的反馈发现了开放[#1103316][CR1103316]中的问题Chromium问题。  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="在 84 或更高版本的元素Microsoft Edge突出显示第一个搜索结果" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   在 84 或更高版本中的 **"** 元素"Microsoft Edge突出显示第一个搜索结果  
:::image-end:::  

此问题现已在所有版本的 Microsoft Edge 中Microsoft Edge。  

Chromium问题[：#1103316][CR1103316]  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-media-tool"></a>新媒体工具  

DevTools 现在在 [Media][DevtoolsMediaPanelIndex] 工具中显示媒体播放器信息。  

若要打开新的 **媒体工具** ，请完成以下步骤。  

1.  Choose **Customize and control DevTools** \(`...` \) > More **tools**  >  **Media**.  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="新媒体工具" lightbox="../../media/2020/08/media-panel.msft.png":::
       新 **媒体** 工具  
    :::image-end:::  

在 DevTools 中的新 **媒体** 工具之前，有关视频播放器的日志记录和调试信息位于" **最近使用播放器"** 设置下。  若要打开" **最近的玩家"** 设置，请导航 `edge://media-internals` 到并选择 **"玩家"** 工具。  

更快查看实时内容并检查潜在问题，包括以下示例。  

*   为什么丢弃帧？  
*   为什么 JavaScript 以意外方式与玩家交互？  

### <a name="capture-node-screenshots-using-the-elements-tool-context-menu"></a>使用"元素"工具上下文菜单捕获节点屏幕截图  

现在，可以使用"元素"工具中的上下文菜单捕获 **节点屏幕截图** 。  

例如，若要获取目录的屏幕截图，请将鼠标悬停在 元素上，打开上下文菜单 \(右键单击\) ，然后选择捕获 **节点屏幕截图**。  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="捕获节点屏幕截图" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   捕获节点屏幕截图  
:::image-end:::  

Chromium问题[：#1100253][CR1100253]  

### <a name="issues-tool-updates"></a>问题工具更新  

控制台工具上的" **问题"警告** 栏现已替换为常规消息。  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text="控制台消息中的问题" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   控制台消息中的问题  
:::image-end:::  

默认情况下，第三方 Cookie 问题在"问题"工具中 **处于隐藏** 状态。  启用新的 **"包含第三方 Cookie 问题** "复选框以查看问题。  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="第三方 Cookie 问题复选框" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   第三方 Cookie 问题复选框  
:::image-end:::  

Chromium问题： [1096481][CR1096481]、 [1068116][CR1068116]、 [1080589][CR1080589]  

### <a name="emulate-missing-local-fonts"></a>模拟缺少的本地字体  

打开 ["呈现"工具][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] 并使用新的 **"禁用本地字体"功能** 模拟规则 `local()` 中缺少 `@font-face` 的源。  

例如，当字体安装在你的设备上并且该规则使用它作为字体时，Microsoft Edge `Rubik` `@font-face src` 使用设备 `local()` 中的本地字体文件。  

启用 **"禁用本地** 字体"后，DevTools 将忽略 `local()` 字体，并提取网络的每个字体。  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="模拟缺少的本地字体" lightbox="../../media/2020/08/disable-font.msft.png":::
   模拟缺少的本地字体  
:::image-end:::  

如果在开发过程中使用同一字体的两个不同副本，例如以下示例。  

*   设计工具的本地字体。  
*   代码的 Web 字体。  

使用 **"禁用本地** 字体"可以更轻松地完成以下任务。  

*   调试并度量 Web 字体的加载性能和优化。  
*   验证 CSS 规则 `@font-face` 的准确性。  
*   发现设备上安装的本地版本与 Web 字体之间的差异。  

Chromium问题[：#384968][CR384968]  

### <a name="emulate-inactive-users"></a>模拟非活动用户  

空闲 [检测 API][WebDevIdleDetection] 允许开发人员检测非活动用户，并响应空闲状态更改。  你现在可以使用 DevTools 在 **传感器** 工具中模拟用户状态和屏幕状态中的空闲状态更改，而不是等待实际空闲状态更改。  You may open the **Sensors** tool from the [Drawer][DevtoolsCustomizeIndexDrawer].  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="模拟非活动用户" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   模拟非活动用户  
:::image-end:::  

Chromium问题[：#1090802][CR1090802]  

### <a name="emulate-prefers-reduced-data"></a>模拟 prefers-reduced-data  

> [!NOTE]
> 在 Microsoft Edge 86 中，若要启用此功能，请导航到"实验 `edge://flags#enable-experimental-web-platform-features` **性 Web 平台功能"标志并打开**。  模拟选项仅在启用标志时显示。  

首选 [的缩减数据][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] 媒体查询可检测减少数据的用户内容首选项。  如果选中，用户将接收使用较少数据的备用页面内容。  

你现在可以使用 DevTools 模拟 `prefers-reduced-data` 媒体查询。  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="模拟 prefers-reduced-data" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   模拟 prefers-reduced-data  
:::image-end:::  

Chromium问题[：#1096068][CR1096068]  

### <a name="support-for-new-javascript-features"></a>支持新的 JavaScript 功能  

DevTools 现在更好地支持以下 JavaScript 语言功能。  

| JavaScript 语言功能 | 详细信息 |  
|:--- |:--- |  
| [逻辑赋值运算符][V8FeaturesLogicalAssignment] | DevTools 现在支持使用控制台和源工具中的新 、 和 运算符 `&&=` `||=` `??=` 进行逻辑分配。 **** ****  |  
| 彩色数字 [分隔符][V8FeaturesNumericSeparators] | DevTools 现在在"源"工具中正确打印数字 **分隔** 符。  |  

Chromium问题[：1086817][CR1086817] [、1080569][CR1080569]  

### <a name="lighthouse-62-in-the-lighthouse-panel"></a>Lighthouse 面板中的 Lighthouse 6.2  

**Lighthouse**工具现在运行 Lighthouse 6.2。  有关更改的完整列表，请导航到 ["Lighthouse"发行说明][GithubGooglechromeLighthouseV620]。  

Chromium问题[：#772558][CR772558]  

### <a name="deprecation-of-other-origins-listing-in-the-service-workers-pane"></a>在"服务工作者"窗格中弃用其他源列表  

DevTools 现在提供来自服务工作者**** 窗格 \(**应用程序**工具 >**服务**工作者窗格\) 的链接，以查看来自其他源的服务工作者的完整列表。  若要在不打开 DevTools 的情况下访问列表，请导航到 `edge://service-worker-internals/?devtools` 。  

以前，DevTools 显示一个嵌套在****"应用程序工具""服务>**窗格下**的列表。  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="链接到其他来源" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   链接到其他来源  
:::image-end:::  

Chromium问题[：#807440][CR807440]  

### <a name="show-coverage-summary-for-filtered-items"></a>显示已筛选项目的范围摘要  

DevTools 现在动态重新计算并显示覆盖信息的摘要。  在覆盖工具中应用筛选器时， [将触发动态][DevtoolsCoverageIndex] 显示。  在 **覆盖工具** 始终显示所有覆盖信息的摘要之前。  

在下图的第一个中，摘要最初显示，在下图的第二个汇总中，将在应用 CSS 筛选 `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` 后显示摘要。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="覆盖摘要" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         覆盖摘要  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="已筛选项目的范围摘要" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         已筛选项目的范围摘要  
      :::image-end:::  
   :::column-end:::
:::row-end:::

Chromium问题[：#1061385][CR1090802]  

### <a name="new-frame-details-view-in-application-panel"></a>应用程序面板中的新帧详细信息视图  

DevTools 现在显示每个帧的详细视图。  若要访问它，请选择"应用程序"工具中" **框架** "菜单下的 **图** 文框。  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="应用程序面板中框架的新详细视图" lightbox="../../media/2020/08/frame-details.msft.png":::
   应用程序工具中帧的新 **详细** 视图  
:::image-end:::  

Chromium问题[：#1093247][CR1093247]  

#### <a name="frame-details-for-opened-windows"></a>打开的窗口的框架详细信息  

打开窗口，弹出窗口现在也显示在框架树下。  打开的窗口的详细视图包括其他安全信息。  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="打开的窗口的新框架详细视图" lightbox="../../media/2020/08/window-opener.msft.png":::
   打开的窗口的新框架详细视图  
:::image-end:::  

Chromium问题：[#1107766][CR1107766]  

#### <a name="security-and-isolation-information"></a>安全和隔离信息  

安全上下文 [、Cross-Origin-Embedder-Policy (COEP) ][WebDevCoopCoep]和 [Cross-Origin-Opener-Policy (COOP) ][WebDevCoopCoep] 现在显示在帧详细信息中。  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="安全和隔离信息" lightbox="../../media/2020/08/coep-coop.msft.png":::
   安全和隔离信息  
:::image-end:::  

将来，Microsoft Edge开发人员工具团队和 Chrome DevTools 团队计划向框架详细信息添加更多安全信息。  

Chromium问题[：#1051466][CR1051466]  

### <a name="elements-and-network-panel-updates"></a>元素和网络面板更新  

#### <a name="accessible-color-suggestion-in-the-styles-pane"></a>"样式"窗格中的可访问颜色建议  

DevTools 现在为低颜色对比度文本提供颜色建议。  

在下面的示例中， `h1` 具有低对比度文本。  若要修复此问题，请打开"样式"窗格中 `color` 属性 **的颜色选取** 器。  展开"对比率 **"部分** 后，DevTools 将提供 AA 和 AAA 颜色建议。  选择建议的颜色以应用该颜色。  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="颜色选取器建议 AA 和 AAA 颜色建议" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   颜色选取器建议 AA 和 AAA 颜色建议  
:::image-end:::  

Chromium问题[：#1093227][CR1093227]  

#### <a name="reinstate-properties-pane-in-the-elements-panel"></a>恢复"元素"面板中的"属性"窗格  

" **属性** "窗格已返回。  它在[84 Microsoft Edge弃用][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]。  开发人员Microsoft Edge团队和 Chrome DevTools 团队正在计划对检查元素属性的改进。  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="元素面板中的属性窗格" lightbox="../../media/2020/08/properties-pane.msft.png":::
   **"** 元素"工具 **中的"属性"** 窗格  
:::image-end:::  

Chromium问题：  <!--  [#1105205][CR1105205],  -->  [#1116085][CR1116085]  

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

现在，在"样式"窗格中编辑属性时，导入的字体将添加到 CSS `font-family` **自动完成** 列表中。  

例如，如果 `monospace` 是本地计算机上安装的自定义字体，则它显示在 CSS 完成列表中。  在早期版本的 Microsoft Edge 中，不显示字体。

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="自动完成自定义字体" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   自动完成自定义字体  
:::image-end:::  

Chromium问题：[#1106221][CR1106221]  

#### <a name="consistently-display-resource-type-in-network-panel"></a>在网络面板中一致地显示资源类型  

DevTools 现在一致地显示与原始网络请求相同的资源类型，当重定向 \(HTTP 状态代码 `/ Redirect` 为 302\) 时追加到 Type 列值。 ****  

以前，DevTools 有时将类型 `Other` 更改为 。  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="显示重定向资源类型" lightbox="../../media/2020/08/network-redirect.msft.png":::
   显示重定向资源类型  
:::image-end:::  

Chromium问题[：#997694][CR997694]  

#### <a name="clear-buttons-in-the-elements-and-network-tools"></a>"元素和网络"工具中的"清除"按钮  

以下文本框现在具有 **"清除"** 按钮。  

*   "样式"窗格和网络 **工具** 中的 **筛选器** 文本框。  
*   元素工具中的 DOM **搜索文本框** 。  

选择" **清除"** 按钮以删除任何输入的文本。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="元素面板中的清除按钮" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         "元素"工具中的 **"清除"** 按钮  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="清除网络面板中的按钮" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         网络工具中的  **"清除"** 按钮  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium问题[：#1067184][CR1067184]  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel "&quot;元素&quot;面板中的&quot;属性&quot;窗格弃用 - DevTools (Microsoft Edge 84) |Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能 - DevTools (Microsoft Edge 85) |Microsoft Docs"  

[DevtoolsConsoleApiTable]: ../../../console/api.md#table "表 - 控制台 API 参考|Microsoft Docs"  
[DevtoolsCoverageIndex]: ../../../coverage/index.md "使用 DevTools Microsoft Edge中的&quot;覆盖&quot;选项卡查找未使用的 JavaScript 和 CSS |Microsoft Docs"  
[DevtoolsCssGrid]: ../../../css/grid.md "检查 Microsoft Edge DevTools 中的 CSS 网格 | Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: ../../../customize/index.md#drawer "设置 - 自定义 Microsoft Edge 开发工具 | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: ../../../customize/shortcuts.md "自定义 Microsoft Edge DevTools 中的键盘快捷方式 | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: ../../../device-mode/index.md "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenAndFoldables]: ../../../device-mode/dual-screen-and-foldables.md "在 DevTools Microsoft Edge中模拟双屏幕和可折叠|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: ../../../evaluate-performance/reference.md#analyze-rendering-performance-with-the-rendering-tool "使用呈现工具分析呈现性能 - 性能分析|Microsoft Docs"  
<!--  [DevtoolsExperimentalFeaturesEnableExperimentalApis]: ../../../experimental-features/index.md#enable-experimental-apis "Enable experimental APIs - Experimental features | Microsoft Docs"  -->  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]： ../../../experimental-features/index.md#emulation-support-dual-screen-mode "Emulation： Support dual screen mode - Experimental features |Microsoft Docs"  
[DevtoolsExperimentalFeaturesSourceOrderViewer]： ../../../experimental-features/index.md#source-order-viewer "Source Order Viewer - Experimental features |Microsoft Docs"
<!--  [DevtoolsExperimentalFeaturesTestOnFoldableDualScreenDevices]: ../../../experimental-features/index.md#test-on-foldable-and-dual-screen-devices "Test on foldable and dual-screen devices - Experimental features | Microsoft Docs"  -->  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]： ../../../experimental-features/index.md#turn-on-experimental-features "Turn on experimental features - Experimental features |Microsoft Docs"  
[DevtoolsMediaPanelIndex]： ../../../media-panel/index.md "View and debug media players information |Microsoft Docs"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "如何处理接缝 - 双屏幕设备简介| Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏幕检测的 CSS 媒体屏幕跨越功能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript AP | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCodeMain]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Code键盘快捷方式Windows"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定|Chromium Bug"
[CR384968]: https://crbug.com/384968 "忽略本地字体 () 选项|Chromium Bug"  
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR807440]: https://crbug.com/807440 "Chrome 会锁定大量 SW |Chromium Bug"  
[CR997694]: https://crbug.com/997694 "网络面板筛选器中的&quot;xhr\"筛选器下不会显示状态为 302 的 XHR |Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table 工具|Chromium Bug"  
[CR1051466]: https://crbug.com/1051466 "支持 DevTools | 中的 COOP/COEP 调试Chromium Bug"  
[CR1054281]: https://crbug.com/1054281 "功能请求：DevTools 应模拟可折叠和双屏幕设备|Chromium Bug"  
[CR1067184]: https://crbug.com/1067184 "功能请求：清除 Network & 元素上的筛选器按钮 -> 样式筛选器|Chromium Bug"  
[CR1068116]: https://crbug.com/1068116 "☂发货问题面板|Chromium Bug"  
[CR1080569]: https://crbug.com/1080569 "视点不支持逻辑赋值运算符|Chromium Bug"  
[CR1080589]: https://crbug.com/1080589 "按第三方/第一方分类|Chromium Bug"  
[CR1086817]: https://crbug.com/1086817 "acorn 不支持数字分隔符|Chromium Bug"  
[CR1090802]: https://crbug.com/1090802 "模拟空闲检测 API 中的空闲状态|Chromium Bug"  
[CR1093227]: https://crbug.com/1093227 "DevTools：建议最接近的辅助颜色|Chromium Bug"  
[CR1093247]: https://crbug.com/1093247 "在应用程序面板应用程序中显示有关框架|Chromium Bug"  
[CR1094406]: https://crbug.com/1094406 "开发人员需要 AT 的源订单查看器 https://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools：支持模拟首选的缩减数据媒体|Chromium Bug"  
[CR1096481]: https://crbug.com/1096481 "问题横幅放置|Chromium Bug"  
[CR1100253]: https://crbug.com/1100253 "在元素上下文菜单菜单中添加屏幕截图节点|Chromium Bug"  
[CR1103316]: https://crbug.com/1103316 "元素搜索不会解析第一 (搜索结果上突出显示) 文本等|Chromium Bug"  
[CR1103854]: https://crbug.com/1103854 "开发人员工具工具中的模糊处理 X-Client-Data |Chromium Bug"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]：" &quot;将导入的字体添加到样式面板中的字体系列 https://crbug.com/1106221 自动完成|Chromium Bug"  
[CR1107766]："显示有关由框架树树中的 https://crbug.com/1107766 'window.open () '生成的帧|Chromium Bug"  
[CR1115011]：" 从控制台复制表时，表的结构不会保留在| https://crbug.com/1115011Chromium Bug"  
[CR1116085]： https://crbug.com/1116085 "Please bring back the DevTools Properties inspector |Chromium Bug"  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "prefers-reduced-data - 第 5 级媒体|W3C CSS 工作组编辑器草稿"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v6.2.0 - GoogleChrome/lighthouse |GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "协议缓冲区|Google 开发人员"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "逻辑分配|V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数字分隔符|V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "使用 COOP 和 COEP 工具使您的网站&quot;跨源隔离|web.dev"  
[WebDevIdleDetection]: https://web.dev/idle-detection "使用空闲检测 API 工具检测非活动|web.dev"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "避免使用非复合|web.dev"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-86)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
