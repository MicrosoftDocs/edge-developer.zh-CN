---
description: 将键盘快捷方式与 Visual Studio 代码匹配、模拟 Surface 双核和 Samsung Galaxy 折页、CSS 网格覆盖改进等。
title: DevTools (Microsoft Edge 86) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 943eca7e73385513b264feb74ec37c450d5c5a2f
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004100"
---
# DevTools (Microsoft Edge 86) 中的新增功能  

## 来自 Microsoft Edge 开发人员工具团队公告  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### 将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配  

在 Microsoft Edge 86 中，你可以将 DevTools 中的键盘快捷方式与 [Visual Studio 代码][VisualStudioCode]中的快捷方式相匹配。 

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配  
:::image-end:::  

若要激活此功能，请导航到 [Microsoft Edge DevTools 中的自定义键盘快捷方式][DevtoolsCustomizeShortcuts]。  

例如，在 [Visual Studio 代码][VisualStudioCodeShortcutsKeyboardWindows] 中暂停或继续运行脚本的键盘快捷方式是 `F5` 。  通过 **DevTools (默认) ** 预设，DevTools 中的同一快捷方式 `F8` ，但选择 **Visual Studio Code** 预置时，该快捷方式现在也是如此 `F5` 。  

Chromium 问题 [#174309][CR174309]  

### 模拟 Surface 双核和 Samsung Galaxy 折页  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配":::
   实验性功能  
:::image-end:::  

现在，你可以在两个新设备上测试你的网站或应用的外观：在 Microsoft Edge 中，  [Surface 双核][MicrosoftSurfaceDevicesDuo] 和 [Samsung Galaxy 折页][SamsungMobileGalaxyFold] 。  

若要帮助增强适用于双屏幕和可折叠设备的网站或应用，请在 [模拟设备][DevtoolsDeviceModeIndex]时使用以下功能。  

*   [跨越][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]，即当你的网站 (或应用 \ ) 出现在两个屏幕上时。
*   [渲染接缝][DualScreenIntroductionHowWorkSeam]，即两个屏幕之间的空间。
*   [启用实验性 Web 平台 api][DevtoolsExperimentalFeaturesEnableExperimentalApis] 以访问新的 [CSS 媒体屏幕生成功能][DualScreenWebCssMediaSpanning] 和 [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments]。  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   Surface 双核设备仿真  
:::image-end:::  

若要启用此实验功能，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选择 " **模拟：支持双重屏幕模式**" 旁边的复选框。  

有关此实验的详细信息，请导航到 " [模拟：支持双重屏幕模式][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]"。  

Chromium 问题： [#1054281][CR1054281]  

### CSS 网格覆盖改进和新的实验性网格功能  

感谢您对改进的 CSS 网格覆盖的积极反馈。  现在，CSS 网格覆盖在默认情况下处于启用状态，不需要你启用实验。  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   元素的 CSS 网格覆盖 `article`  
:::image-end:::  

> [!NOTE]
> 有关网格覆盖的详细信息，请转到 [CSS 网格调试功能][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]。  

Microsoft Edge DevTools 团队和 Chrome DevTools 团队协作处理其他功能。  新功能包括在 "**元素**" 面板上的新**布局**窗格中具有持久性和可配置的多个覆盖。  

若要启用此实验功能，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选中 " **启用新 CSS 网格调试功能" 旁边的复选框 (在重新启动) 后，元素的 "布局" 侧栏窗格中可用的配置选项 **。  

有关此实验的详细信息，请导航以 [启用新的 CSS 网格调试功能][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]。  

Chromium 问题： [#1047356][CR1047356]  

### 从控制台复制的表保留格式  

在 Microsoft Edge 85 或更早版本中，已复制的格式 `console.table` 丢失。  如果从 [表][DevtoolsConsoleApiTable] 控制台 API 复制了输出并粘贴了该输出，则仅保留表的文本。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` Microsoft Edge 85 或更早版本中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` 从 Microsoft Edge 85 或更早版本粘贴到 Visual Studio 代码的控制台 API 输出  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 Microsoft Edge 86 或更高版本中，从 **控制台**复制表格时，格式现在将保留。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` Microsoft Edge 86 或更高版本中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` Microsoft Edge 86 或更高版本中粘贴到 Visual Studio 代码中的控制台 API 输出  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium 问题： [#1115011] [CR1115011]  

### 源顺序查看器，便于进行辅助功能测试  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配":::
   实验性功能  
:::image-end:::  

新的辅助功能帮助程序显示源中元素的顺序。  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   激活 "**显示源订单**"  
:::image-end:::  

此功能可让你更轻松地测试屏幕阅读器和键盘用户体验你的网站或应用的方式。  屏幕阅读器和键盘导航依赖于在网站或应用的源代码中按特定顺序放置的内容，以便与呈现的页面匹配。  源顺序查看器在呈现的页面和源代码之间按顺序显示潜在差异。  

若要启用此实验功能，请导航到 ["打开实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选中 " **启用源订单查看器**" 旁边的复选框。  

有关此实验的详细信息，请导航到 [启用源订单查看器][DevtoolsExperimentalFeaturesEnableSourceOrderViewer]。  

Chromium 问题： [#1094406][CR1094406]  

<!--
### DevTools language enhancements  

Your feedback and internal discoveries uncovered which text strings used in the Microsoft Edge feedback should remain untranslated or create confusion when translated.  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-stable.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="localization-improvements-chinese-complex-stable.msft.png":::
         Microsoft Edge DevTools 85 and earlier in Traditional Chinese  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png":::
         Microsoft Edge DevTools 86  or later in Traditional Chinese  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.  

The current effort to improve translation quality enables easier support for more languages in the future.  
-->  

### 突出显示 "元素" 工具中的所有搜索结果  

在 Microsoft Edge 84 和85中，" **元素** " 面板中的第一个搜索结果不突出显示。  剩余的搜索结果已正确突出显示。  

感谢您发送反馈并帮助改进 Chromium。  你的反馈发现问题 [#1103316][CR1103316] 在开放源代码 Chromium 项目中。  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   在 Microsoft Edge 84 或更高版本中突出显示 " **元素** " 面板上的第一个搜索结果  
:::image-end:::  

此问题现已在所有版本的 Microsoft Edge 中修复。  

Chromium 问题： [#1103316][CR1103316]  

## 来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新媒体面板  

DevTools 现在在 " [媒体][DevtoolsMediaIndex] " 面板中显示媒体播放器信息。  

若要打开新的 " **媒体** " 面板，请完成以下步骤。  

1.  选择 "**自定义和控制 DevTools** \ (`...` \ ) " >**更多工具**  >  **媒体**。  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/media-panel.msft.png":::
       新 **媒体** 面板  
    :::image-end:::  

在 DevTools 中的新 **媒体** 面板之前，有关视频播放器的日志记录和调试信息位于 " **最近使用的播放机** " 设置下。  若要打开 " **最近使用的播放器** " 设置，请转到 `edge://media-internals` 并选择 " **玩家** " 选项卡。  

查看实时内容并更快地检查潜在问题，包括以下示例。  

*   为什么删除框架？  
*   为什么 JavaScript 以意外的方式与玩家交互？  

### 使用 "元素" 面板上下文菜单捕获节点屏幕截图  

现在，你可以使用 " **元素** " 面板中的上下文菜单来捕获节点屏幕截图。  

例如，若要获取目录的屏幕截图，请将鼠标悬停在该元素上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **捕获节点屏幕截图**"。  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   捕获节点屏幕截图  
:::image-end:::  

Chromium 问题： [#1100253][CR1100253]  

### 问题工具更新  

**控制台**面板上的问题警告栏现在被替换为常规消息。  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   控制台消息中的问题  
:::image-end:::  

默认情况下，在 " **问题** " 工具中，第三方 cookie 问题现已隐藏。  启用 "新建 **包含第三方 cookie 问题** " 复选框以查看问题。  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   第三方 cookie 问题复选框  
:::image-end:::  

Chromium 问题： [1096481][CR1096481]、 [1068116][CR1068116]、 [1080589][CR1080589]  

### 模拟缺少的本地字体  

打开 [渲染工具][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] 并使用新的 " **禁用本地字体** " 功能来模拟 `local()` 规则中缺少的源 `@font-face` 。  

例如，当 `Rubik` 字体安装在设备上并且 `@font-face src` 规则使用它作为 `local()` 字体时，Microsoft Edge 将使用您的设备中的本地字体文件。  

启用 " **禁用本地字体** " 时，DevTools 将忽略 `local()` 字体并从网络中提取每个字体。  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/disable-font.msft.png":::
   模拟缺少的本地字体  
:::image-end:::  

如果在开发期间使用同一字体的两个不同副本，例如以下示例。  

*   设计工具的本地字体。  
*   代码的 web 字体。  

使用 " **禁用本地字体** "，让您能够更轻松地完成以下任务。  

*   调试和测量 web 字体的加载性能和优化。  
*   验证 CSS 规则的准确性 `@font-face` 。  
*   发现设备上安装的本地版本和 web 字体之间的差异。  

Chromium 问题： [#384968][CR384968]  

### 模拟非活动用户  

" [空闲检测" API][WebDevIdleDetection] 允许开发人员检测非活动用户并对空闲状态更改做出响应。  现在，你可以使用 DevTools 来模拟用户状态和屏幕状态的 **传感器** 工具中的空闲状态更改，而不是等待实际空闲状态更改。  您可以从[抽屉][DevtoolsCustomizeIndexDrawer]打开 "**传感器**" 工具。  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   模拟非活动用户  
:::image-end:::  

Chromium 问题： [#1090802][CR1090802]  

### 模拟首选数据-减少数据  

> [!NOTE]
> 在 Microsoft Edge 86 中，若要启用此功能，请转到 `edge://flags#enable-experimental-web-platform-features` 并打开 **实验性 Web 平台功能** 标志。  只有启用了标志，才会显示 "模拟" 选项。  

" [优先-减少-数据][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] 媒体" 查询检测减少数据的用户内容首选项。  如果选中此选项，用户将收到使用较少数据的备用页面内容。  

您现在可以使用 DevTools 模拟 `prefers-reduced-data` 媒体查询。  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   模拟首选数据-减少数据  
:::image-end:::  

Chromium 问题： [#1096068][CR1096068]  

### 对新的 JavaScript 功能的支持  

DevTools 现已更好地支持以下 JavaScript 语言功能。  

| JavaScript 语言功能 | 详细信息 |  
|:--- |:--- |  
| [逻辑赋值运算符][V8FeaturesLogicalAssignment] | DevTools 现在支持 `&&=` `||=` `??=` 在 " **控制台** " 和 " **源** " 面板中通过 "新建"、"和" 运算符进行逻辑赋值。  |  
| 整齐打印 [数值分隔符][V8FeaturesNumericSeparators] | DevTools 现已正确打印 " **源** " 面板中的数字分隔符。  |  

Chromium 问题： [1086817][CR1086817]、 [1080569][CR1080569]  

### Lighthouse 面板中的 Lighthouse 6。2  

**Lighthouse**面板现在正在运行 Lighthouse 6.2。  有关更改的完整列表，请转到 [Lighthouse 发行说明][GithubGooglechromeLighthouseV620]。  

Chromium 问题： [#772558][CR772558]  

### "服务工作人员" 窗格中的其他来源列表已过时  

DevTools 现在提供从 " **服务工作者** " 窗格 \ (**应用程序** 面板 > **服务工作者** 窗格 \ ) 的链接，以查看其他来源的服务工作人员的完整列表。  若要在不打开 DevTools 的情况下访问列表，请转到 `edge://service-worker-internals/?devtools` 。  

以前的 DevTools 显示了一个嵌套在 **应用程序** 面板 > **服务工作人员** 窗格下的列表。  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   链接到其他来源  
:::image-end:::  

Chromium 问题： [#807440][CR807440]  

### 显示已筛选项目的覆盖范围摘要  

DevTools 现已动态重新计算并显示覆盖范围信息的摘要。  当在 [覆盖范围][DevtoolsCoverageIndex] 工具中应用筛选器时，将触发动态显示。  **覆盖范围**工具始终显示所有覆盖范围信息的摘要之前。  

在下面的第一条数字中，摘要最初显示在 `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` 下图的第二个数字中， `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` 应用 CSS 筛选后将显示摘要。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         覆盖范围摘要  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         已筛选项目的覆盖范围摘要  
      :::image-end:::  
   :::column-end:::
:::row-end:::

Chromium 问题： [#1061385][CR1090802]  

### 应用程序面板中新的 "框架详细信息" 视图  

DevTools 现在显示每个帧的详细视图。  若要访问它，请在 "**应用程序**" 面板中的 "**框架**" 菜单下选择一个框架。  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/frame-details.msft.png":::
   **应用程序**面板中的框架的新详细视图  
:::image-end:::  

Chromium 问题： [#1093247][CR1093247]  

#### 打开的窗口的帧详细信息  

打开的窗口和弹出窗口现在也显示在框架树下方。  打开的窗口的详细视图包含其他安全信息。  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/window-opener.msft.png":::
   打开的窗口的新框架详细视图  
:::image-end:::  

Chromium 问题： [#1107766] [CR1107766]  

#### 安全性和隔离信息  

安全上下文、 [跨起源 Embedder-策略 (COEP) ][WebDevCoopCoep]和 [基于 Opener (的合作基金) ][WebDevCoopCoep] 现在将显示在 "帧详细信息" 中。  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/coep-coop.msft.png":::
   安全性和隔离信息  
:::image-end:::  

将来，Microsoft Edge DevTools 团队和 Chrome DevTools 团队计划向该帧的详细信息添加更多的安全信息。  

Chromium 问题： [#1051466][CR1051466]  

### 元素和网络面板更新  

#### "样式" 窗格中的辅助颜色建议  

DevTools 现在提供低颜色对比度文本的颜色建议。  

在下面的示例中， `h1` 具有低对比度文本。  若要解决此问题，请 `color` 在 " **样式** " 窗格中打开该属性的颜色选取器。  展开 " **对比度比率** " 部分后，DevTools 将提供 AA 和 AAA 颜色建议。  选择建议的颜色以应用颜色。  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   颜色选取器建议 AA 和 AAA 颜色建议  
:::image-end:::  

Chromium 问题： [#1093227][CR1093227]  

#### "元素" 面板中的 "恢复属性" 窗格  

" **属性** " 窗格将返回。  它已 [在 Microsoft Edge 84 中弃用][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]。  Microsoft Edge DevTools 团队和 Chrome DevTools 团队是对检查元素的属性进行规划的改进。  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/properties-pane.msft.png":::
   "**元素**" 面板中的 "**属性**" 窗格  
:::image-end:::  

Chromium 问题：  <!--  [#1105205][CR1105205],  -->  [#1116085][CR1116085]  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### "样式" 窗格中的 "自动完成" 自定义字体  

在编辑 "样式" 窗格中的属性时，导入的字体现在将添加到 CSS 自动完成列表 `font-family` 中。 **Styles**  

例如，如果 `monospace` 是在本地计算机上安装的自定义字体，它将显示在 CSS 完成列表中。 在早期版本的 Microsoft Edge 中，字体未显示。

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   自动完成自定义字体  
:::image-end:::  

Chromium 问题： [#1106221] [CR1106221]  

#### 在 "网络" 面板中一致地显示资源类型  

DevTools 现在与原始网络请求一致地显示相同的资源类型，并且 `/ Redirect` 在重定向 \ (HTTP 状态代码 302 \ ) 时，附加到 " **类型** " 列的值。  

以前 DevTools 将类型更改为 " `Other` 有时"。  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/network-redirect.msft.png":::
   显示重定向资源类型  
:::image-end:::  

Chromium 问题： [#997694][CR997694]  

#### 在 "元素" 和 "网络" 面板中清除按钮  

以下文本框现在具有 " **清除** " 按钮。  

*   " **样式** " 窗格和 " **网络** " 面板中的 "筛选" 文本框。  
*   " **元素** " 面板中的 "DOM 搜索" 文本框。  

选择 " **清除** " 按钮以删除任何输入文本。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         " **元素** " 面板中的 "清除" 按钮  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         "  **网络** " 面板中的 "清除" 按钮  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium 问题： [#1067184][CR1067184]  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools "设置" 图标"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel ""元素" 面板中 "属性" 窗格的弃用-DevTools 中的新增功能 (Microsoft Edge 84) |Microsoft 文档"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能-DevTools 中的新增功能 (Microsoft Edge 85) |Microsoft 文档"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 Api-实验性功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器-实验性功能 |Microsoft 文档"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在折叠和双屏幕设备上测试-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实验功能-实验功能 |Microsoft 文档"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-控制台 API 参考 |Microsoft 文档"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码。Microsoft 文档"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "通过 "呈现" 选项卡分析呈现性能-性能分析参考 |Microsoft 文档"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "查看和调试媒体播放器信息 |Microsoft 文档"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "如何使用双屏幕设备的接缝简介 |Microsoft 文档"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "适用于双屏幕检测的 CSS 媒体屏幕扩展功能 |Microsoft 文档"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft 文档"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码 "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "适用于 Windows 的 Visual Studio 代码键盘快捷方式"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface 双核"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"
[CR384968]: https://crbug.com/384968 "选项可忽略本地 ( # A1 字体 |Chromium bug"  
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium bug"  
[CR807440]: https://crbug.com/807440 "Chrome 通过大量的 SWs |Chromium bug"  
[CR997694]: https://crbug.com/997694 "302状态的 XHR 请求不会显示在 "网络" 面板中的 "XHR" 筛选器 |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/表格工具"  
[CR1051466]: https://crbug.com/1051466 "在 DevTools | 中支持合作基金/COEP 调试Chromium bug"  
[CR1054281]: https://crbug.com/1054281 "功能请求： DevTools 应模拟可折叠和双屏幕设备 |Chromium bug"  
[CR1067184]: https://crbug.com/1067184 "功能请求：网络 & 元素上的 "清除筛选" 按钮-> 样式筛选器输入 |Chromium bug"  
[CR1068116]: https://crbug.com/1068116 "☂装运问题面板 |Chromium bug"  
[CR1080569]: https://crbug.com/1080569 "acorn 不支持逻辑赋值运算符 |Chromium bug"  
[CR1080589]: https://crbug.com/1080589 "按第三方/第三方对问题进行分类Chromium bug"  
[CR1086817]: https://crbug.com/1086817 "acorn 不支持数值分隔符 |Chromium bug"  
[CR1090802]: https://crbug.com/1090802 "模拟来自空闲检测 API 的空闲状态更改 |Chromium bug"  
[CR1093227]: https://crbug.com/1093227 "DevTools：建议最接近的辅助颜色 |Chromium bug"  
[CR1093247]: https://crbug.com/1093247 "在应用程序面板中显示有关框架的信息 |Chromium bug"  
[CR1094406]: https://crbug.com/1094406 "开发人员希望使用源订单查看器 https://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools：支持模拟 "首选-减少-数据媒体" 功能 |Chromium bug"  
[CR1096481]: https://crbug.com/1096481 "问题横幅位置 |Chromium bug"  
[CR1100253]: https://crbug.com/1100253 "在元素上下文菜单中添加屏幕截图节点快捷方式 |Chromium bug"  
[CR1103316]: https://crbug.com/1103316 "在第一个搜索结果 | resolveNode 中，元素搜索不会 (突出显示文本等) Chromium bug"  
[CR1103854]: https://crbug.com/1103854 "在开发工具 | 中取消模糊处理 X 客户端数据值 |Chromium bug"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]： https://crbug.com/1106221 "在样式面板中将导入的字体添加到字体系列自动完成" |Chromium bug "  
[CR1107766]： https://crbug.com/1107766 "显示由" 窗口生成的帧的相关信息。在框架树中打开 ( # A1 "|Chromium bug "  
[CR1115011]： https://crbug.com/1115011 "从控制台复制表时不保留表的结构 |Chromium bug "  
[CR1116085]： https://crbug.com/1116085 "请返回 DevTools 属性检查器 |Chromium bug "  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "首选-减少-数据-媒体查询级别 5 |W3C CSS 工作组编辑器草稿"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v 6.2.0-GoogleChrome/lighthouse |GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "协议缓冲区 |Google 开发人员"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy 折页 |美国 Samsung"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "逻辑赋值 |V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数字分隔符 |V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "使用合作基金和 COEP 将您的网站设置为 "跨原点隔离" |web 开发"  
[WebDevIdleDetection]: https://web.dev/idle-detection "通过 "空闲检测 API" 检测非活动用户 |web 开发"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "避免非合成动画 |web 开发"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/updates/2020/08/devtools/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
