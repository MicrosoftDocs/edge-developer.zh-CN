---
description: 新的 CSS 网格调试工具、Webauthn 工具、可移动工具和计算边栏面板。
title: 'DevTools (Microsoft Edge 87 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0f4e0aaeba55f584697d1817f7ea54044dfdd380
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514352"
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
# <a name="whats-new-in-devtools-microsoft-edge-87"></a>DevTools 87 (Microsoft Edge中的新增)   

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="improving-devtools-localization"></a>改进 DevTools 本地化  

为了满足翻译需求，Microsoft Edge团队侧重于提高翻译质量。  从 Microsoft Edge版本 87 开始，锁定多个字符串和术语，即使其他语言显示其余的 DevTools，这些字符串和术语也不会改变。  受影响字符串和术语的列表包括以下内容。  

*   **Lighthouse 工具中的**字符串。  
*   术语 `service worker` 。  
*   一些 **网络工具** 筛选器，如 `URL` `XHR` 、、 `JS` 和 `CSS` 。  
*   [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]控制台实用程序 API。  
    
现在，在控制台中[为](/microsoft-edge/devtools-guide-chromium/console/index.md)使用 DevTools 本地化版本的用户提供[$0。][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]   感谢全球开发人员社区帮助改进开发人员工具Microsoft Edge本地化。  继续 [发送本地化质量反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ，以改进在所有区域设置中对 DevTools 的支持。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1136655"。][CR1136655]  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   **具有** 非本地化筛选器的网络窗格  
:::image-end:::  

## <a name="move-tools-between-top-and-bottom-panels"></a>在顶部和底部面板之间移动工具  

DevTools 现在支持在顶部和底部面板之间移动工具。  通过同时查看两个工具的任意组合来自定义 DevTools 并提高工作效率。  例如，将"源****"工具移动到**** 底部\ (的同时查看"元素"和"源") 。 ****  若要在开放源代码项目中查看此功能的Chromium，请导航到"问题[#1075732"。][CR1075732]  

:::row:::
   :::column span="":::
      若要将任何顶部工具移动到底部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击\) ，然后选择"移动到**底部"。**  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="移动到底部" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         移动到底部  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      若要将任何底部工具移动到顶部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击\) ，然后选择"移动到**顶部"。**  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="移动到顶部" lightbox="../../media/2020/10/move-to-top.msft.png":::
         移动到顶部  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## <a name="save-and-export-using-the-network-console"></a>使用网络控制台保存和导出  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

网络 **控制台** 工具现在改进了与 [Postman v2.1][PostmanSchemaJsonCollectionv210Index] 和 [OpenAPI v2 架构][SwaggerSpecificationV2] 的兼容性。  若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 功能，然后选择启用网络控制台旁边的 **复选框**。  有关网络控制台 **详细信息，请**导航到启用 [网络控制台实验功能][DevtoolsExperimentalFeaturesEnableNetworkConsole]。  此实验现在支持以下操作。  

*   保存和导出集合和环境。  
*   在网络控制台工具中编辑和导出 **环境变量** 集。  
    
若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1093687"。][CR1093687]  

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

## <a name="improved-css-grid-tooling"></a>改进的 CSS 网格工具  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

开发人员Microsoft Edge工具现在支持以下功能来检查、查看和调试 CSS 网格。  

*   使用 Inspect 工具显示简化的网格 **覆盖，或** 获取有关永久性覆盖的更多详细信息。  
*   若要启用持久网格覆盖，请选择"元素"工具中网格容器元素旁边的网格图标，**** 或在"布局"工具**中选择**网格。  
*   你可以为多个网格启用永久性覆盖。  
*   新的 **布局** 工具允许你轻松切换网格覆盖，并为每个覆盖层配置外观和内容。  
    
默认情况下，这些功能为打开状态。  有关功能详细信息，请导航到 [CSS 网格][DevtoolsCssGrid]。  若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[#1047356"。][CR1047356]  此外，Microsoft Edge开发人员工具团队正在与 Chrome DevTools 团队和 Chromium 社区协作，向 DevTools 添加新的弹性框工具功能。  有关开放源代码项目中 flexbox 工具Chromium，导航到"问题[#1136394"。][CR1136394]  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="具有网格的布局工具" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   **具有** 网格的布局工具  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a>在“设置”中自定义键盘快捷方式  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

现在，你可以为 DevTools 中任何操作自定义键盘快捷方式。  自 Microsoft Edge版本 84 起，你可以选择在 Visual Studio Code**** 和**DevTools** (键盘快捷方式的默认) [预设][DevtoolsCustomizeShortcuts]。  从 Microsoft Edge版本 87 开始，你可以打开启用键盘快捷方式**编辑器**实验以进一[步自定义键盘快捷方式][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  

若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 功能，然后选择启用键盘快捷方式编辑器旁边的 **复选框**。  有关自定义和编辑快捷方式详细信息，请导航至 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#174309"][CR174309]。  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="用于暂停脚本的自定义快捷方式" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   用于暂停脚本的自定义快捷方式  
:::image-end:::  

## <a name="introducing-the-microsoft-edge-tools-for-visual-studio-code-extension"></a>Microsoft Edge工具扩展Visual Studio Code  

适用于**Visual Studio Code**和 Network **for Visual Studio Code**的 Elements 现在合并到新的 Microsoft Edge [Developer Tools for Visual Studio Code][VisualStudioCodeMarketplaceMsEdgedevtools]扩展中。  将 Microsoft Edge DevTools 用于以下活动，而无需保留Microsoft Visual Studio代码。  

*   调试 DOM  
*   编辑 CSS  
*   检查网络流量  

借助扩展，Microsoft Edge浏览器，连接到浏览器的现有实例，或者直接从编辑器使用无头浏览器。  若要开始提供和归档有关此扩展的反馈问题，请导航到 Microsoft Edge[上的][GithubMicrosoftVscodeEdgeDevtools]Visual Studio Code 开发人员GitHub。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="在完整浏览器模式下使用扩展的屏幕截图" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         在完整浏览器模式下使用扩展的屏幕截图  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="在无头模式下使用扩展屏幕截图" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         在无头模式下使用扩展屏幕截图  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-webauthn-tool"></a>新 WebAuthn 工具  

在早期版本的 Microsoft Edge，没有本机 WebAuthn 调试支持。  您需要物理验证器来使用 Web 身份验证 API 测试 [Web 应用程序][GithubW3cWebauthn]。  使用新的 **WebAuthn** 工具，无需使用任何物理验证器即可执行以下操作。

*   模拟验证器
*   自定义验证器的属性
*   检查验证器状态
    
有关**WebAuthn**功能详细信息，请导航到"模拟验证器"，并在开发人员工具中Microsoft Edge [WebAuthn。][DevtoolsWebauthnIndex]  

您可以使用新的[WebAuthn][DevtoolsWebauthnIndex]工具模拟验证器[][GithubW3cWebauthn]并调试 Web 身份验证 API。  若要打开**WebAuthn**工具，请选择自定义和控制**DevTools** \ (`...` \) 图标>**更多工具**  >  **WebAuthn。**  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1034663"。][CR1034663]  

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

### <a name="elements-tool-updates"></a>“元素”工具更新  

#### <a name="view-the-computed-sidebar-pane-in-the-styles-pane"></a>查看"样式"窗格中的"计算边栏"窗格  

切换 **"样式"** 窗格中的"计算 **"** 窗格。  默认情况下 **，"****样式"窗格中**的计算窗格是折叠的。  若要切换它，请选择该按钮。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1073899"。][CR1073899]  

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

#### <a name="grouping-css-properties-in-the-computed-panel"></a>在计算面板中对 CSS 属性进行分组  

若要以更少的滚动量查看应用的 CSS，请按"计算"窗格中的类别对 CSS **属性进行** 分组。  在检查 CSS 时，还可以有选择地专注于一组相关属性。  从" **元素"** 工具中，选择一个元素。  若要将 \ (或取消组合\) CSS 属性，请切换 **"组"** 复选框。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题#1096230、#1084673和[#1106251。][CR1106251] [][CR1096230] [][CR1084673]  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="对 CSS 属性进行分组" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   对 CSS 属性进行分组  
:::image-end:::  

### <a name="lighthouse-64-in-the-lighthouse-tool"></a>Lighthouse 工具中的 Lighthouse 6.4  

**Lighthouse**工具现在运行 Lighthouse 6.4。  有关更改的完整列表，请导航到 ["Lighthouse"发行说明][GithubGoogleChromeLighthouseReleasesV641]。  若要在开源项目中查看此功能Chromium，请导航到"问题[#772558"。][CR772558]  

### <a name="performancemark-events-in-the-timings-section"></a>performance.mark () "计时"部分中的事件  

" **性能"** 工具中记录的"计时" [部分现在][DevtoolsGuideChromiumEvaluatePerformanceReference] 标记 `performance.mark()` 事件。  若要试用此功能并度量 JavaScript 代码的性能，请 `performance.mark()` 向代码添加事件。  例如，以下代码段在循环之前和之后添加标记，该循环使用增量 7 从 0 循环到 `for` 1000。  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

然后，打开 ["性能"][DevtoolsGuideChromiumEvaluatePerformanceReference] 工具并导航到" **计时"部分** 以录制 JavaScript 代码。  `performance.mark()`您添加的事件现在将显示在录制中。  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="Performance.mark 事件" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` 事件  
:::image-end:::  

### <a name="new-resource-type-and-url-filters-in-the-network-tool"></a>网络工具中的新资源类型和 URL 筛选器  

使用 Network `resource-type` `url` 工具中的 new 和 **关键字** 筛选网络请求。  例如，使用 `resource-type:image` 将焦点放在作为图像的网络请求上。  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="资源类型筛选器" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   资源类型筛选器  
:::image-end:::  

若要发现更多特殊关键字（如 和 `resource-type` `url` ），请导航到 [按属性 筛选请求][DevtoolsNetworkReferenceFilterRequestsProperties]。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1121141#1104188。][CR1121141] [][CR1104188]  

### <a name="frame-details-view-updates"></a>框架详细信息视图更新  

#### <a name="display-coep-and-coop-reporting-to-endpoint"></a>向终结点显示 COEP 和 COOP 报告  

查看"安全与隔离"部分下的跨源嵌入器策略 \ (COEP\) 和跨源打开器策略 \ (COOP\) `reporting to` **&** 终结点。  报告 [API][MdnReportingApi] 定义一个新的 HTTP 标头，它为你提供了一种指定浏览器服务器终结点以 `Report-To` 发送警告和错误的方法。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1051466"。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="报告到终结点" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   `reporting to`终结点  
:::image-end:::  

#### <a name="display-coep-and-coop-report-only-mode"></a>显示 COEP 和 COOP 仅报告模式  

DevTools 现在显示设置为模式的 COEP 和 `report-only` COOP `report-only` 的标签。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1051466"。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="仅报告模式标签" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   `report-only`模式标签  
:::image-end:::  

### <a name="view-and-fix-color-contrast-issues-in-the-css-overview-tool"></a>在 CSS 概述工具中查看和修复颜色对比度问题  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

CSS **概述** 工具现在显示页面上具有颜色对比度问题的元素列表。  下面的演示页面包含颜色对比度问题的示例。  

[CSS 概述辅助颜色演示][GlitchCssOverviewAccessibleColorsDemo]  

若要启用此实验，设置****  >  **实验"** 下，选中 **"CSS 概述"** 复选框。  若要查看具有颜色对比度问题的元素的列表，在对比度问题上，选择******文本**。  若要在"元素"工具 **中打开** 元素，请选择列表中的元素。  为了帮助修复对比度问题，Microsoft Edge开发人员工具[自动提供颜色建议][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[#1120316"。][CR1120316]  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低色对比度问题" lightbox="../../media/2020/10/css-overview.msft.png":::
   低色对比度问题  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "&quot;元素&quot;工具中的&quot;属性&quot;窗格弃用 - DevTools (Microsoft Edge 84 中的) |Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能 - DevTools (Microsoft Edge 85) |Microsoft Docs"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane "&quot;样式&quot;窗格中的可访问颜色建议 - DevTools (Microsoft Edge 86 中的新增) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象 - 控制台实用程序 API |Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 中的键盘快捷方式 | Microsoft Docs"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "性能分析参考|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 API - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "启用网络控制台 - 实验功能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器 - 实验|Microsoft Docs"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "打开实验性功能 - 实验|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表 - 控制台 API 参考|Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 DevTools Microsoft Edge中的&quot;覆盖&quot;选项卡查找未使用的 JavaScript 和 CSS |Microsoft Docs"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "检查 CSS 网格|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "设置 - 自定义 Microsoft Edge 开发工具 | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "使用&quot;呈现&quot;选项卡分析呈现性能 - 性能分析参考|Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "查看和调试媒体播放器|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "按属性筛选请求 - 网络分析参考|Microsoft Docs"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "在 DevTools Microsoft Edge中模拟验证器并调试 WebAuthn |Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge工具Visual Studio Code |Visual Studio Code"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定|Chromium Bug"
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR1034663]: https://crbug.com/1034663 "为 WebAuthn 测试 API 应用程序创建|Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table 工具|Chromium Bug"  
[CR1051466]: https://crbug.com/1051466 "支持 DevTools | 中的 COOP/COEP 调试Chromium Bug"  
[CR1073899]: https://crbug.com/1073899 "计算样式选项卡在响应模式下消失|Chromium Bug"  
[CR1075732]: https://crbug.com/1075732 "DevTools 个性化 - &quot;开发工具&quot;选项卡|Chromium Bug"  
[CR1084673]: https://crbug.com/1084673 "DevTools：改进我们呈现 CSS 自定义属性 ( (，) 。CSS 变量) 及其值|Chromium Bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播综合网络请求|Chromium Bug"  
[CR1096230]: https://crbug.com/1096230 "在计算样式窗格中按类别分组 CSS |Chromium Bug"  
[CR1104188]: https://crbug.com/1104188 "在搜索完整 URL 搜索时，网络工具搜索找不到|Chromium Bug"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools：改进&quot;计算样式&quot;选项卡|Chromium Bug"  
[CR1120316]: https://crbug.com/1120316 "突出显示 CSS 概述和颜色>对比度|ChromiumBug"  
[CR1121141]: https://crbug.com/1121141 "允许在网络日志日志中按资源类型|Chromium Bug"  
[CR1121312]: https://crbug.com/1121312 "设置&quot;更多工具&quot;菜单中删除|Chromium Bug"  
[CR1136394]: https://crbug.com/1136394 "Flexbox 工具|ChromiumBug"  
[CR1136655]: https://crbug.com/1136655 "开发工具：本地化 V2 |Chromium Bug"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "报告 API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v6.4.1 - GoogleChrome/lighthouse |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证|GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "你好！|小故障"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman 集合格式 v2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 规范|Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-87)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
