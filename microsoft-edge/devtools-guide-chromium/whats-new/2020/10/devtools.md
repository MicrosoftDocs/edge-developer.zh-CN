---
description: 新的 CSS 网格调试工具、Webauthn 工具、可移动工具和计算边栏面板。
title: 'Microsoft Edge 87 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/26/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 88e6678880172a7a494bcf73c74874aeb70c24b9
ms.sourcegitcommit: e737277744dd25a7585c113eef22a2aa4d4c167f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "11325957"
---
# Microsoft Edge 87 (DevTools 中的新增)   

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## 改进 DevTools 本地化  

为了满足翻译需求，Microsoft Edge DevTools 团队专注于提高翻译质量。  从 Microsoft Edge 版本 87 开始，锁定了多个字符串和术语，即使开发人员工具的其余部分以其他语言显示，也不会改变。  受影响字符串和术语的列表包括以下内容。  

*   **Lighthouse**工具中的字符串。  
*   术语 `service worker` 。  
*   一些 **网络** 工具筛选器，例如 `URL` ， `XHR` 和 `JS` `CSS` 。  
*   [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]控制台实用程序 API。  
    
现在，在控制台中[为](/microsoft-edge/devtools-guide-chromium/console/index.md)使用本地化版本的 DevTools 的用户提供了[$0。][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]   感谢全球开发人员社区帮助改进 Microsoft Edge DevTools 的本地化。  继续 [发送本地化质量反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ，以改进所有区域设置中对 DevTools 的支持。  若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#1136655。][CR1136655]  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   **具有** 非本地化筛选器的网络窗格  
:::image-end:::  

## 在顶部和底部面板之间移动工具  

DevTools 现在支持在顶部和底部面板之间移动工具。  通过同时查看两个工具的任意组合来自定义 DevTools 并提高工作效率。  例如，将"源****"工具移动到**** 底部\ (，同时查看"元素"和"源") 。 ****  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[#1075732。][CR1075732]  

:::row:::
   :::column span="":::
      若要将任何顶部工具移到底部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击\) ，然后选择"移动到**底部"。**  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="移动到底部" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         移动到底部  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      若要将任何底部工具移到顶部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击\) ，然后选择"移动到**顶部"。**  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="移动到顶部" lightbox="../../media/2020/10/move-to-top.msft.png":::
         移动到顶部  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## 使用网络控制台保存和导出  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验功能":::
   实验功能  
:::image-end:::  

网络 **控制台** 工具现在改进了与 [Postman v2.1][PostmanSchemaJsonCollectionv210Index] 和 [OpenAPI v2][SwaggerSpecificationV2] 架构的兼容性。  若要启用实验，请导航到" [打开实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "功能并选择"启用网络控制台 **"旁边的复选框**。  有关网络控制台 **详细信息，** 请导航到 ["启用网络控制台实验"功能][DevtoolsExperimentalFeaturesEnableNetworkConsole]。  此实验现在支持以下操作。  

*   保存和导出集合和环境。  
*   在网络控制台工具中编辑和导出 **环境变量** 集。  
    
若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#1093687。][CR1093687]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="输入新环境的名称" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         输入新环境的名称  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="选择新环境的格式" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         选择新环境的格式  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 改进的 CSS 网格工具  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验功能":::
   实验功能  
:::image-end:::  

Microsoft Edge DevTools 现在支持以下功能来检查、查看和调试 CSS 网格。  

*   使用"检查"工具显示简化的**** 网格覆盖，或获取有关持久覆盖的更多详细信息。  
*   若要启用持久网格覆盖，请选择 **"** 元素"工具中的网格容器元素旁边的网格图标，或在布局 **工具中选择网格** 。  
*   你可以为多个网格启用永久性覆盖。  
*   新的 **布局** 工具允许你轻松切换网格覆盖，并为每个覆盖层配置外观和内容。  
    
默认情况下，这些功能已打开。  有关功能详细信息，请导航到 [CSS 网格][DevtoolsCssGrid]。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[#1047356。][CR1047356]  此外，Microsoft Edge DevTools 团队正在与 Chrome DevTools 团队和 Chromium 社区协作，向 DevTools 添加新的弹性框工具功能。  有关 Chromium 开放源代码项目中弹性箱工具的更新，请导航到"问题[#1136394。][CR1136394]  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="具有网格的布局工具" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   **具有** 网格的布局工具  
:::image-end:::  

## 在"设置"中自定义键盘快捷方式  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验功能":::
   实验功能  
:::image-end:::  

现在，你可以为 DevTools 中任何操作自定义键盘快捷方式。  自 Microsoft Edge 版本 84 起，你可以选择 Visual Studio **Code** 和 **DevTools ** (键盘快捷方式) [预设][DevtoolsCustomizeShortcuts]。  从 Microsoft Edge 版本 87 开始，**** 可以启用键盘快捷方式编辑器实验以进一[步自定义键盘快捷方式][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  

若要启用实验，请导航到" [打开实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "功能并选择"启用键盘快捷方式编辑器 **"旁边的复选框**。  有关自定义和编辑快捷方式详细信息，请导航至 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  若要在 Chromium 开放源代码项目中查看此功能实时更新，请导航到"问题[#174309。][CR174309]  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="用于暂停脚本的自定义快捷方式" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   用于暂停脚本的自定义快捷方式  
:::image-end:::  

## Microsoft Edge Tools for Visual Studio Code extension  

代码 **扩展Visual Studio Network** **for Visual Studio** 的元素现在合并到新的 Microsoft Edge 开发人员工具中，Visual Studio [代码][VisualStudioCodeMarketplaceMsEdgedevtools] 扩展。  将 Microsoft Edge DevTools 用于以下活动，而无需保留Visual Studio代码。  

*   调试 DOM  
*   编辑 CSS  
*   检查网络流量  

借助扩展，启动 Microsoft Edge，连接到浏览器的现有实例，或者直接从编辑器使用无头浏览器。  若要开始提供和归档有关此扩展的反馈问题，请导航到 [GitHub][GithubMicrosoftVscodeEdgeDevtools] 上的 Microsoft Edge 开发人员工具Visual Studio代码存储库。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="在完整浏览器模式屏幕截图中使用该扩展" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         在完整浏览器模式屏幕截图中使用该扩展  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="在无头模式下使用扩展屏幕截图" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         在无头模式下使用扩展屏幕截图  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新的 WebAuthn 工具  

在早期版本的 Microsoft Edge 中，没有本机 WebAuthn 调试支持。  你需要物理验证器来测试 Web 应用程序与[Web 身份验证 API。][GithubW3cWebauthn]  使用新的 **WebAuthn** 工具，无需使用任何物理验证器即可执行下列操作。

*   模拟验证器
*   自定义验证器的属性
*   检查验证器状态
    
有关**WebAuthn**功能详细信息，请导航到"模拟验证器"，并在[Microsoft Edge DevTools 中调试 WebAuthn。][DevtoolsWebauthnIndex]  

您可以使用新的[WebAuthn][DevtoolsWebauthnIndex]工具模拟验证器并调试 Web 身份验证[API。][GithubW3cWebauthn]  若要打开**WebAuthn**工具，请选择"自定义和控制**DevTools** \ (`...` \) 图标>**更多**  >  **工具 WebAuthn。**  若要在 Chromium 开放源代码项目中查看此功能实时更新，请导航 [到][CR1034663]"问题#1034663。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="打开 WebAuthn 工具" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         打开 **WebAuthn** 工具  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn 工具" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         **WebAuthn** 工具  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### 元素工具更新  

#### 在"样式"窗格中查看计算边栏窗格  

切换 **"样式"****窗格中的计算窗格**。  默认情况下 **，"****样式**"窗格中的计算窗格是折叠的。  若要切换它，请选择该按钮。  若要在 Chromium 开放源代码项目中查看此功能实时更新，请导航到"问题[#1073899。][CR1073899]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="打开"计算边栏"窗格" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         打开 **"计算边栏"** 窗格  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="计算边栏窗格" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         **计算边栏** 窗格  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### 对计算面板中的 CSS 属性进行分组  

若要以更少的滚动量查看应用的 CSS，请按计算窗格中的类别对 CSS **属性进行** 分组。  在检查 CSS 时，还可以选择性地专注于一组相关属性。  从" **元素"** 工具中选择一个元素。  若要将 \ (或 ungroup\) CSS 属性，请切换 **"组"** 复选框。  若要在 Chromium 开放源代码项目中查看此功能实时更新，请导航到"问题"#1096230、#1084673[][CR1096230]和#1106251。 [][CR1084673] [][CR1106251]  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="对 CSS 属性进行分组" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   对 CSS 属性进行分组  
:::image-end:::  

### Lighthouse 工具中的 Lighthouse 6.4  

**Lighthouse**工具现在运行 Lighthouse 6.4。  有关更改的完整列表，请导航到 [Lighthouse 发行说明][GithubGoogleChromeLighthouseReleasesV641]。  若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#772558。][CR772558]  

### timings (中的 performance.mark () 事件  

" **性能"工具** 中记录的"计时" [部分现在][DevtoolsGuideChromiumEvaluatePerformanceReference] 标记 `performance.mark()` 事件。  若要试用此功能并测量 JavaScript 代码的性能，请 `performance.mark()` 向代码添加事件。  例如，以下代码段在循环之前和之后添加标记，该循环使用 7 的增量从 `for` 0 循环到 1000。  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

然后，打开 [性能][DevtoolsGuideChromiumEvaluatePerformanceReference] 工具并导航到" **计时"部分** 以记录 JavaScript 代码。  `performance.mark()`您添加的事件现在将显示在录制中。  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="Performance.mark 事件" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` 事件  
:::image-end:::  

### 网络工具中的新资源类型和 URL 筛选器  

使用网络 `resource-type` 工具 `url` 中的新增和关键字筛选**** 网络请求。  例如， `resource-type:image` 用于专注于作为图像的网络请求。  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="资源类型筛选器" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   资源类型筛选器  
:::image-end:::  

若要发现更多特殊关键字（如 `resource-type` `url` and），请导航到 [按属性筛选请求][DevtoolsNetworkReferenceFilterRequestsProperties]。  若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[][CR1104188]"#1121141#1104188。 [][CR1121141]  

### 框架详细信息视图更新  

#### 向终结点显示 COEP 和 COOP 报告  

查看"安全与隔离"部分下的跨源嵌入器策略 \ (COEP\) 和跨源开放器策略 \ (COOP\) `reporting to` **&** 终结点。  报告 [API][MdnReportingApi] 定义一个新的 HTTP 标头，用于指定浏览器的服务器终结点以 `Report-To` 发送警告和错误。  若要在 Chromium 开放源代码项目中查看此功能实时更新，请导航到"问题[#1051466。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="向终结点报告" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   `reporting to`终结点  
:::image-end:::  

#### 显示 COEP 和 COOP 仅报告模式  

DevTools 现在显示 `report-only` 设置为模式的 COEP 和 COOP `report-only` 的标签。  若要在 Chromium 开放源代码项目中查看此功能实时更新，请导航到"问题[#1051466。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="仅报告模式标签" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   模式 `report-only` 标签  
:::image-end:::  

### 在 CSS 概述工具中查看和修复颜色对比度问题  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验功能":::
   实验功能  
:::image-end:::  

**CSS 概述**工具现在显示页面上具有颜色对比度问题的元素列表。  下面的演示页面具有颜色对比度问题的示例。  

[CSS 概述辅助颜色演示][GlitchCssOverviewAccessibleColorsDemo]  

若要启用此实验，在"**设置**  >  **实验**"下，选择 **"CSS 概述"** 复选框。  若要查看具有颜色对比度问题的元素的列表，在对比度 **问题上，** 选择 **文本**。  若要在元素工具 **中打开** 元素，请选择列表中的元素。  为了帮助修复对比度问题，Microsoft Edge DevTools [自动提供颜色建议][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。  若要在 Chromium 开放源代码项目中查看此功能实时更新，请导航到"问题[#1120316。][CR1120316]  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低颜色对比度问题" lightbox="../../media/2020/10/css-overview.msft.png":::
   低颜色对比度问题  
:::image-end:::  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "元素工具中的"属性"窗格弃用 - Microsoft Edge 84 (DevTools 中的新增) |Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能 - Microsoft Edge 85 (DevTools 中的新增) |Microsoft Docs"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane ""样式"窗格中的可访问颜色建议 - Microsoft Edge 86 (DevTools 中的新增功能) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象 - 控制台实用程序 API |Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "性能分析参考|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 API - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "启用网络控制台 - 实验功能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器 - 实验|Microsoft Docs"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上测试 - 实验功能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "打开实验功能 - 实验|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表 - 控制台 API |Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的"覆盖"选项卡查找未使用的 JavaScript 和 CSS |Microsoft Docs"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "检查 CSS 网格|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "箱 - 自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "使用"呈现"选项卡分析呈现性能 - 性能分析参考|Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "查看和调试媒体播放器|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "按属性筛选请求 - 网络分析参考|Microsoft Docs"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "模拟验证器，并调试 Microsoft Edge DevTools |Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定|Chromium Bug"
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR1034663]: https://crbug.com/1034663 "为 WebAuthn 测试 API 应用程序创建|Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table 工具|Chromium Bug"  
[CR1051466]: https://crbug.com/1051466 "支持 DevTools |中的 COOP/COEP 调试Chromium Bug"  
[CR1073899]: https://crbug.com/1073899 "计算样式选项卡在响应模式下消失|Chromium Bug"  
[CR1075732]: https://crbug.com/1075732 "DevTools 个性化 - 选项卡|Chromium Bug"  
[CR1084673]: https://crbug.com/1084673 "DevTools：改进我们呈现 CSS 自定义属性的方式 (（即) ）。CSS 变量) 及其值|Chromium Bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播综合网络请求|Chromium Bug"  
[CR1096230]: https://crbug.com/1096230 "在计算样式窗格中按类别分组 CSS |Chromium Bug"  
[CR1104188]: https://crbug.com/1104188 "在搜索完整 URL 链接时，网络工具搜索找不到|Chromium Bug"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools：改进计算样式选项卡|Chromium Bug"  
[CR1120316]: https://crbug.com/1120316 "在"CSS 概述"下突出显示>对比度|Chromium Bugs"  
[CR1121141]: https://crbug.com/1121141 "允许在网络日志记录中按资源类型|Chromium Bug"  
[CR1121312]: https://crbug.com/1121312 "应从"更多工具"菜单中删除|Chromium Bug"  
[CR1136394]: https://crbug.com/1136394 "Flexbox 工具|Chromium Bugs"  
[CR1136655]: https://crbug.com/1136655 "开发工具：本地化 V2 |Chromium Bug"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "报告 API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v6.4.1 - GoogleChrome/lighthouse |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证|GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "你好！|小故障"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman 集合格式 v2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 规范|Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/updates/2020/10/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
