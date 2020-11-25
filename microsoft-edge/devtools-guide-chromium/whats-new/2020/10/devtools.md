---
description: 新的 CSS 网格调试工具、Webauthn 工具、可移动工具和计算的边栏面板。
title: DevTools (Microsoft Edge 87) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: b972468ad21f3a64985a00aecbe29836032b3334
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "11190003"
---
# DevTools (Microsoft Edge 87) 中的新增功能  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## 改进 DevTools 本地化  

为了满足您的翻译需求，Microsoft Edge DevTools 团队致力于改进翻译质量。  从 Microsoft Edge 版本87开始，将锁定多个字符串和术语，即使 DevTools 的其余部分以其他语言显示，也不会更改。  受影响的字符串和术语的列表包括以下。  

*   **Lighthouse**工具中的字符串。  
*   术语 `service worker` 。  
*   某些 **网络** 工具筛选器，如、 `URL` 、 `XHR` `JS` 和 `CSS` 。  
*   [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]控制台实用工具 API。  
    
[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] 目前在 DevTools 的本地化版本的用户的 [控制台](/microsoft-edge/devtools-guide-chromium/console/index.md) 中可用。   感谢您参加全球开发人员社区，帮助改进 Microsoft Edge DevTools 的本地化。  继续 [发送本地化质量反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ，以改进对所有区域设置中的 DevTools 的支持。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1136655][CR1136655]"。  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   具有非本地化筛选器的**网络**窗格  
:::image-end:::  

## 在顶部面板和底部面板之间移动工具  

DevTools 现在支持在顶部面板和底部面板之间移动工具。  通过同时查看两个工具的组合，自定义您的 DevTools 并提高工作效率。  例如，通过将 "**源**" 工具移动到底部的 \ ) ，同时查看 "**元素**" 和 "**源**" 工具 (。  若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [#1075732][CR1075732]"。  

:::row:::
   :::column span="":::
      若要将任何顶部工具移到底部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **移至底部**"。  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="移至底部" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         移至底部  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      若要将任何底部工具移到顶部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **移至页首**"。  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="移到页首" lightbox="../../media/2020/10/move-to-top.msft.png":::
         移到页首  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## 使用网络控制台保存和导出  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

**网络控制台**工具现在改进了与[Postman v 2.1][PostmanSchemaJsonCollectionv210Index]和[OpenAPI v2][SwaggerSpecificationV2]架构的兼容性。  若要启用实验，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选择 " **启用网络控制台**" 旁边的复选框。  有关 **网络控制台**的详细信息，请导航以 [启用网络控制台实验功能][DevtoolsExperimentalFeaturesEnableNetworkConsole]。  此次实验现在支持下列操作。  

*   保存和导出集合和环境。  
*   在 **网络控制台** 工具中编辑和导出环境变量集。  
    
若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1093687][CR1093687]"。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="为新环境输入名称" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         为新环境输入名称  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="为新环境选择格式" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         为新环境选择格式  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 改进的 CSS 网格工具  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

Microsoft Edge DevTools 现在支持用于检查、查看和调试 CSS 网格的以下功能。  

*   使用 " **检查** " 工具显示简化的网格覆盖，或获取更详细的具有永久重叠的信息。  
*   若要启用永久网格覆盖，请选择 " **元素** " 工具中网格容器元素旁边的网格图标，或在 **布局** 工具中选择网格。  
*   你可以为多个网格启用永久覆盖。  
*   新的 **布局** 工具使你可以轻松地切换网格覆盖并配置每个网格的外观和内容。  
    
默认情况下，功能处于打开状态。  有关这些功能的详细信息，请导航到 " [CSS 网格][DevtoolsCssGrid]"。  若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [#1047356][CR1047356]"。  此外，Microsoft Edge DevTools 团队正与 Chrome DevTools 团队和 Chromium 社区协作，将新的 flexbox 工具功能添加到 DevTools。  有关 Chromium open source 项目中的 flexbox 工具的更新，请导航到 "问题 [#1136394][CR1136394]"。  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="带有网格的布局工具" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   带有网格的**布局**工具  
:::image-end:::  

## 在 "设置" 中自定义键盘快捷方式  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

现在，你可以自定义 DevTools 中任何操作的键盘快捷方式。  由于 Microsoft Edge 版本84，你可以在**Visual Studio 中选择 Visual Studio 代码**和 DevTools ([键盘快捷方式][DevtoolsCustomizeShortcuts]的**默认) **预设。  从 Microsoft Edge 版本87开始，你可以打开 " **启用键盘快捷方式编辑器** " 体验，进一步 [自定义键盘快捷方式][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  

若要启用实验，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选中 " **启用键盘快捷方式编辑器**" 旁边的复选框。  有关自定义和编辑快捷方式的详细信息，请导航以 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#174309][CR174309]"。  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="用于暂停脚本的自定义快捷方式" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   用于暂停脚本的自定义快捷方式  
:::image-end:::  

## 介绍 Visual Studio 代码扩展的 Microsoft Edge 工具  

Visual studio 代码和**网络 For Visual Studio 代码**扩展的**元素**现在合并到[visual Studio 代码扩展的新 Microsoft Edge 开发人员工具][VisualStudioCodeMarketplaceMsEdgedevtools]中。  在不退出 Visual Studio 代码的情况下使用 Microsoft Edge DevTools 执行下列活动。  

*   调试 DOM  
*   编辑 CSS  
*   检查网络流量  

使用扩展，启动 Microsoft Edge，连接到浏览器的现有实例，或直接从编辑器使用无外设浏览器。  若要开始对有关此扩展的反馈提出和归档问题，请导航到 GitHub 上 [Visual Studio 代码库的 Microsoft Edge 开发人员工具][GithubMicrosoftVscodeEdgeDevtools] 。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="在完整浏览器模式下使用扩展屏幕截图" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         在完整浏览器模式下使用扩展屏幕截图  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="在无外设模式的屏幕截图中使用扩展" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         在无外设模式的屏幕截图中使用扩展  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新的 WebAuthn 工具  

在早期版本的 Microsoft Edge 中，没有本机的 WebAuthn 调试支持。  您需要物理 authenticators 以通过 [Web 身份验证 API][GithubW3cWebauthn]测试 web 应用程序。  使用新的 " **WebAuthn** " 工具，你可以执行以下操作，而无需使用任何物理 authenticators。

*   模拟 authenticators
*   自定义 authenticators 的属性
*   检查 authenticators 的状态
    
有关 **WebAuthn** 功能的详细信息，请 [在 Microsoft Edge DevTools 中导航到模拟 Authenticators 和调试 WebAuthn][DevtoolsWebauthnIndex]。  

你可以通过新的 " [WebAuthn][DevtoolsWebauthnIndex] " 工具模拟 authenticators 和调试[WEB 身份验证 API][GithubW3cWebauthn] 。  若要打开 " **WebAuthn** " 工具，请选择 **"自定义和控制 DevTools** \ (`...` \ ) " 图标 > "**更多工具" 工具**  >  **WebAuthn**。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1034663][CR1034663]"。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="打开 "WebAuthn 工具"" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         打开 " **WebAuthn** 工具"  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn 工具" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         **WebAuthn** 工具  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### 元素工具更新  

#### 在 "样式" 窗格中查看 "计算的边栏" 窗格  

切换 "**样式**" 窗格中的**计算**窗格。  默认情况下，"**样式**" 窗格中的**计算**窗格处于折叠状态。  若要切换它，请选择该按钮。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1073899][CR1073899]"。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="打开 "计算的边栏" 窗格" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         打开 " **计算的边栏** " 窗格  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="计算的边栏窗格" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         **计算的边栏** 窗格  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### 在计算的面板中对 CSS 属性进行分组  

若要使用较少的滚动查看已应用的 CSS，请按 **计算** 窗格中的类别对 css 属性进行分组。  你还可以在检查你的 CSS 时有选择地将焦点放在一组相关的属性上。  从 " **元素** " 工具中，选择一个元素。  若要组 \ (或取消组合 ) CSS 属性，请切换 " **组** " 复选框。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题" [#1096230][CR1096230]、" [#1084673][CR1084673]" 和 " [#1106251][CR1106251]"。  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="对 CSS 属性进行分组" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   对 CSS 属性进行分组  
:::image-end:::  

### Lighthouse 工具中的 Lighthouse 6。4  

**Lighthouse**工具现在正在运行 Lighthouse 6.4。  有关更改的完整列表，请导航到 [Lighthouse 发行说明][GithubGoogleChromeLighthouseReleasesV641]。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#772558][CR772558]"。  

### 性能：在 "计时" 部分中标记 ( # A1 事件  

[性能][DevtoolsGuideChromiumEvaluatePerformanceReference]工具中的录制的 "**计时" 部分**现在标记 `performance.mark()` 事件。  若要尝试此功能并测量 JavaScript 代码的性能，请将 `performance.mark()` 事件添加到代码。  例如，以下代码片段 `for` 使用7的增量，在从0循环到1000的循环之前和之后添加标记。  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

然后，打开 " [性能][DevtoolsGuideChromiumEvaluatePerformanceReference] " 工具并导航到 " **计时" 部分** ，以记录你的 JavaScript 代码。  `performance.mark()`您添加的事件现在将显示在录制中。  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="性能。标记事件" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` 事件  
:::image-end:::  

### 网络工具中的新资源类型和 url 筛选器  

使用网络工具中的 "新建" `resource-type` 和 " `url` 关键字" 筛选网络请求。 **Network**  例如，使用 `resource-type:image` 重点关注图像的网络请求。  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="资源类型筛选器" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   资源类型筛选器  
:::image-end:::  

若要发现更多特殊关键字（如 `resource-type` 和 `url` ），请导航到 " [按属性筛选请求][DevtoolsNetworkReferenceFilterRequestsProperties]"。  若要在 Chromium open source 项目中查看此功能的实时更新，请导航到 [#1121141][CR1121141] 和 [#1104188][CR1104188]的问题。  

### 框架详细信息视图更新  

#### 将 COEP 和合作基金报告显示给终结点  

查看 " `reporting to` **安全 & 隔离** " 部分下的 "跨起源 Embedder 策略 \ (COEP \ ) 和跨源 Opener 策略 \ (合作基金 \ ) 终结点。  [报告 API][MdnReportingApi]定义了 `Report-To` 一个新的 HTTP 标头，为您提供了一种指定浏览器发送警告和错误的服务器终结点的方法。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1051466][CR1051466]"。  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="报告到终结点" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   该 `reporting to` 终结点  
:::image-end:::  

#### 显示 COEP 和合作基金报告模式  

DevTools 现在显示 `report-only` 设置为 "模式" 的 COEP 和市场活动的标签 `report-only` 。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1051466][CR1051466]"。  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="仅报告模式标签" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   `report-only`模式标签  
:::image-end:::  

### 查看和修复 CSS 概述工具中的颜色对比度问题  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

**CSS 概述**工具现在显示页面上出现颜色对比度问题的元素列表。  下面的演示页面包含颜色对比度问题的示例。  

[CSS 概述易于访问的颜色演示][GlitchCssOverviewAccessibleColorsDemo]  

若要启用此实验，请在 "**设置**  >  **实验**" 下，选择 " **CSS 概述**" 复选框。  若要查看具有颜色对比度问题的元素的列表，请在 **对比度问题**中选择 " **文本**"。  若要打开 " **元素** " 工具中的元素，请在列表中选择一个元素。  为了帮助解决对比度问题，Microsoft Edge DevTools [自动提供颜色建议][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1120316][CR1120316]"。  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低颜色对比度问题" lightbox="../../media/2020/10/css-overview.msft.png":::
   低颜色对比度问题  
:::image-end:::  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "弃用 "元素" 工具中的 "属性" 窗格-DevTools 中的新增功能 (Microsoft Edge 84) |Microsoft 文档"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能-DevTools 中的新增功能 (Microsoft Edge 85) |Microsoft 文档"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane ""样式" 窗格中的辅助颜色建议-DevTools 中的新增功能 (Microsoft Edge 86) |Microsoft 文档"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象-控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "性能分析参考 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 Api-实验性功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "启用网络控制台-实验性功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器-实验性功能 |Microsoft 文档"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在折叠和双屏幕设备上测试-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实验功能-实验功能 |Microsoft 文档"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-控制台 API 参考 |Microsoft 文档"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码。Microsoft 文档"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "检查 CSS 网格 |Microsoft 文档"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "通过 "呈现" 选项卡分析呈现性能-性能分析参考 |Microsoft 文档"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "查看和调试媒体播放器信息 |Microsoft 文档"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "按属性筛选请求-网络分析参考 |Microsoft 文档"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "在 Microsoft Edge DevTools | 中模拟 authenticators 和调试 WebAuthn |Microsoft 文档"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "适用于 Visual Studio 代码的 Microsoft Edge 工具 |Visual Studio 代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium bug"  
[CR1034663]: https://crbug.com/1034663 "为 "WebAuthn 测试 API" 创建前端 |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/表格工具 |Chromium bug"  
[CR1051466]: https://crbug.com/1051466 "在 DevTools | 中支持合作基金/COEP 调试Chromium bug"  
[CR1073899]: https://crbug.com/1073899 ""计算样式" 选项卡在 "响应模式" 中消失 |Chromium bug"  
[CR1075732]: https://crbug.com/1075732 "DevTools 个性化-可移动选项卡 |Chromium bug"  
[CR1084673]: https://crbug.com/1084673 "DevTools：改进了显示 CSS 自定义属性的方式 ( # B1 也称为) 。CSS 变量) 及其值 |Chromium bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播合成网络请求的工具 |Chromium bug"  
[CR1096230]: https://crbug.com/1096230 "按计算样式窗格中的类别对 CSS 属性进行分组 |Chromium bug"  
[CR1104188]: https://crbug.com/1104188 "网络工具搜索在搜索完整 URL 时找不到结果 |Chromium bug"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools：改进 "计算样式" 选项卡 |Chromium bug"  
[CR1120316]: https://crbug.com/1120316 "在 "CSS 概述 > 颜色" 下突出显示 "不良对比度" |Chromium Bug"  
[CR1121141]: https://crbug.com/1121141 "允许按网络日志 | 中的资源类型进行筛选Chromium bug"  
[CR1121312]: https://crbug.com/1121312 "应从 "其他工具" 菜单中删除 "设置" |Chromium bug"  
[CR1136394]: https://crbug.com/1136394 "Flexbox 工具 |Chromium Bug"  
[CR1136655]: https://crbug.com/1136655 "Devtools：本地化 V2 |Chromium bug"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "报告 API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v 6.4.1-GoogleChrome/lighthouse |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证 |GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "你好！ |故障"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman 集合格式 v 2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 规范 |Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/updates/2020/10/devtools/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  