---
description: 模拟命令菜单中的颜色视觉缺陷、停靠到左侧等。
title: DevTools （Microsoft Edge 83）中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: c329dfba980b882b6e538447e52902e4d0cc985b
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514415"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-83"></a>DevTools （Microsoft Edge 83）中的新增功能  

按照更新的 Chromium 计划，我们将调整即将推出的 Microsoft Edge 版本的计划，并取消 Microsoft Edge 82 版本。 有关详细信息，请查看我们的 [博客文章][WindowsBlogStableRelease]。  

下面是 Microsoft Edge 83 的 DevTools 中提供的新功能。  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>来自 Microsoft Edge 开发人员工具团队公告  

以下各节列出了你可能从 DevTools 团队中错过Microsoft Edge通知。  请查看公告以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。  若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。  

### <a name="remotely-debug-microsoft-edge-on-windows-10-devices"></a>在 Windows 10 设备上远程调试 Microsoft Edge  

现在，[Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 \(Beta\)][RemoteTools] 应用。  使用此扩展 Windows Device [Portal][WindowsUwpDebugTestPerfDevicePortal]的应用，你可以从开发计算机上运行的 Microsoft Edge 实例连接到远程 Windows 10 设备，显示目标列表 \ (Microsoft Edge 中所有选项卡，PBA 在 Windows 10 设备上打开\) ，并针对在远程[][ProgressiveWebAppsChromiumIndex]Windows 10 设备上运行的目标使用开发计算机上 DevTools。  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="现在，Microsoft Store 中提供 Microsoft Edge 远程工具 (Beta) 应用" lightbox="../../media/2020/03/remote-tools.msft.png":::
   [Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 (Beta)][RemoteTools] 应用  
:::image-end:::  

[阅读我们的指南以设置 Windows 10 设备和开发计算机进行远程调试][DevtoolsRemoteDebuggingWindows]。  通过推文或选择发送反馈图标，告诉我们[][PostTweetEdgeDevTools]你的远程[调试](#getting-in-touch-with-microsoft-edge-devtools-team)体验！  

### <a name="new-ways-to-access-settings"></a>访问设置的新方法  

你可以自定义大量的 DevTools 设置，以使 DevTools 外观、感觉和工作方式达到你的要求。 在 Microsoft Edge 83 中，访问 DevTools 中的 [设置][DevtoolsCustomizeIndexSettings] 现在更为简单。  使用 "控制台警报" 和 "主菜单" 旁边的齿轮图标打开 "设置"。  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="齿轮图标会打开 DevTools 中的设置" lightbox="../../media/2020/03/settings.msft.png":::
   齿轮图标将 **打开** DevTools 中的"设置"  
:::image-end:::  

你还可以从**主菜单**下的"**更多工具**"下打开[设置][DevtoolsCustomizeIndexSettings]。

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="主菜单 > 更多工具 > 设置" lightbox="../../media/2020/03/settings2.msft.png":::
   **主菜单**  > **更多工具**  > **设置**  
:::image-end:::  

Chromium 问题 [#1050855][CR1050855]

### <a name="new-and-improved-infobars"></a>新增和改进的 infobars

DevTools 中的信息性通知栏 \(infobars\) 现在具有改进的外观和功能。 在 Microsoft Edge 83 中，infobars 更易于阅读和提供按钮，以便你能够立即执行相关操作。  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="用于在 Microsoft Edge 83 中整齐打印缩小文件的信息栏" lightbox="../../media/2020/03/infobar.msft.png":::
   用于在 Microsoft Edge 版本 83 中打印缩小文件的信息栏  
:::image-end:::  

Chromium 问题 [#1056348][CR1056348]

### <a name="navigate-the-color-picker-with-your-keyboard"></a>使用键盘导航颜色选取器  

[颜色选取器][DevtoolsCssReferenceColorPicker] 是 "[元素][DevtoolsCssIndex]" 面板中的 GUI 用于更改 `color` 和 `background-color` 声明。  在早期版本的 Microsoft Edge 中，无法使用键盘导航 [颜色选取器][DevtoolsCssReferenceColorPicker] 的 **阴影** 部分。  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="现在，你可以使用键盘在颜色选取器的 阴影 部分移动选取器" lightbox="../../media/2020/03/color-picker.msft.png":::
   现在，你可以使用键盘在 [颜色选取器][DevtoolsCssReferenceColorPicker]的**阴影** 部分移动选取器  
:::image-end:::  

在 Microsoft Edge 83 中，你可以使用键盘在颜色选取器的**阴影** 部分移动选取器。  

Chromium 问题 [#963183][CR963183]  

### <a name="properties-tab-now-populates-after-a-page-refresh"></a>现在，刷新页面后将填充“属性”选项卡  

在 Microsoft Edge 81 及更早版本中，在 "[元素][DevtoolsCssIndex]" 面板中的 **"属性"选项卡**因页面刷新而损坏。  刷新页面时，**"属性" 选项卡** 未填充当前所选元素的属性。  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="在 Microsoft Edge 81 及更早版本中，页面刷新后，属性 选项卡为空白" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   在 Microsoft Edge 81 及更早版本中，在页面刷新后，**"属性" 选项卡** 是空白的  
:::image-end:::  

在 Microsoft Edge 83 中，现在您可以在"属性"选项卡中刷新页面后显示当前**所选元素的属性**。  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="在 Microsoft Edge 83 中，属性 选项卡显示页面刷新后当前所选元素的属性" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   在 Microsoft Edge 83 中，**"属性" 选项卡** 显示页面刷新后当前所选元素的属性  
:::image-end:::  

Chromium 问题 [#1050999][CR1050999]  

### <a name="use-the-arrow-keys-to-scroll-in-the-changes-tool"></a>使用箭头键在 "更改" 工具中滚动  

**"更改" 工具** 跟踪你对 DevTools 中的 CSS 或 JavaScript 所做的任何更改。  可以使用"更改"工具快速**** 显示所有更改，并返回编辑器/IDE。  

若要打开**更改工具，** 请在 `Ctrl` + `Shift` + `P` DevTools 中选择以打开命令[菜单][DevToolsCommandMenuIndex]并键入 `changes` 。  选择并运行"**显示更改"** 命令以在**** DevTools 箱中打开"更改"工具。  

对缩小文件进行更改后，"更改"工具允许您水平滚动**** 以显示所有缩小代码。  从 Microsoft Edge 83 开始，你现在可以使用键盘上的箭头键水平滚动。  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="在 Microsoft Edge 83 中，可以使用箭头键水平滚动，以在"更改"工具中显示缩小代码" lightbox="../../media/2020/03/changes.msft.png":::
   在 Microsoft Edge 83 中，可以使用箭头键水平滚动，以在"更改"工具中显示对缩小代码**所做的更改**  
:::image-end:::  

如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过向我们发推文或[][PostTweetEdgeDevTools]选择"发送反馈"图标向我们发送[反馈](#getting-in-touch-with-microsoft-edge-devtools-team)！  

Chromium 问题 [#963183][CR963183]  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

以下各部分公布了 Microsoft Edge 83 中提供的其他功能，这些功能是对开源 Chromium 项目的贡献。  

### <a name="emulate-vision-deficiencies"></a>模仿视觉缺陷  

打开["渲染" 选项卡][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] ，使用新的"**模拟视觉缺陷**" 功能，更好地了解有不同类型视觉缺陷的人们如何体验你的网站。  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="模拟模糊的视觉效果" lightbox="../../media/2020/03/vision.msft.png":::
   模拟模糊的视觉效果  
:::image-end:::  

DevTools 能够模拟模糊的视觉和以下[颜色视觉缺陷类型][ColorBlindnessTypes]。  

| 颜色视觉缺陷 | 详细信息 |  
|:--- |:--- |  
| 红色盲 | 无法感觉任何红色的光线。 |  
| 绿色盲 | 无法感觉任何绿色的光线。 |  
| 黄蓝色盲 | 无法感觉任何蓝色的光线。 |  
| 全色盲 | 无法感觉任何颜色，灰色阴影除外\（极少\）。 |  

存在这些色觉缺陷的不太极端的版本，实际上它们更为常见。  
例如，红色弱降低了对红光的敏感性（与红色盲相对，后者完全无法感知红光）。 但是，这些 **-omaly** 视觉缺陷没有明确定义：每个有这种视觉缺陷的人是不同的，并且可能会看到不同的 \ (能够感知更多/更少的相关颜色\) 。  

通过在 DevTools 中进行更极端的仿真设计，可以保证红色弱、绿色弱、黄蓝色弱和全色弱的人也可访问你的 Web 应用。  

通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！  

Chromium 问题 [#1003700][CR1003700]  

### <a name="emulate-locales"></a>模拟语言环境  

通过在**传感器**  >  **位置**中设置位置来模拟语言环境。 [打开**命令菜单** ][DevToolsCommandMenuIndex]，然后键入`Sensors`以访问**传感器**选项卡。执行完这些操作后，DevTools 会修改当前的默认语言环境，从而影响以下代码。  

*   `Intl.*` 例如，API： `new Intl.NumberFormat().resolvedOptions().locale`  
*   其他可识别语言环境的 JavaScript API，例如`String.prototype.localeCompare`和`*.prototype.toLocaleString`，例如： `123_456..toLocaleString()`  
*   DOM API，如 `navigator.language` 和 `navigator.languages`  
*   [接受语言][MDNAcceptLanguage]HTTP 请求标头  

> [!NOTE]
> 对`navigator.language`和`navigator.languages`的更新不是立即可见的，只有在下一次导航或页面刷新后才可见。  只有后续请求才会反映对 `Accept-Language` HTTP 标头的更改。  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="模拟区域设置" lightbox="../../media/2020/03/locale.msft.png":::
   模拟区域设置  
:::image-end:::  

若要尝试演示，请导航到与 [区域设置相关的代码示例][MathiasByensLocaleDemo]。

Chromium 问题 [#1051822][CR1051822]

### <a name="cross-origin-embedder-policy-coep-debugging"></a>跨域嵌入程序策略 (COEP) 调试  

"网络" 面板现在提供[跨域嵌入程序策略 (COEP)][COEP] 调试信息。  

“**状态**”列现在提供有关为何阻止请求的快速说明，以及查看该请求标头以进行进一步调试的链接：  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="**状态**列中的阻止请求" lightbox="../../media/2020/03/status.msft.png":::
   "状态"**列中阻止的请求**  
:::image-end:::  

"**标头**" 选项卡上的 "**响应标头**" 部分提供了有关如何解决这些问题的更多指导：  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="“响应标头”部分中的更多指南" lightbox="../../media/2020/03/guidance.msft.png":::
   "响应头" **部分中的更多** 指南  
:::image-end:::  

通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！  

Chromium 问题 [#1051466][CR1051466]  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a>断点、条件断点和登录点的新图标  

"源"面板具有用于断点、条件断点和日志点的新图标：  

*   断点 \(![断点](../../media/2020/03/breakpoint.msft.png)\) 用红色圆圈表示。  
*   条件断点 \(![条件断点](../../media/2020/03/conditional.msft.png)\) 用半红半白圆表示。  
*   Logpoints \(![Logpoint](../../media/2020/03/logpoint.msft.png)\) 用带控制台图标的红色圆圈表示。  

新图标的动机是使 UI 与其他 GUI 调试工具 \(（通常为红色) 颜色断点\）更加一致，并便于一目了然地区分这 3 个功能。  

Chromium 问题 [#1041830][CR1041830]  

### <a name="view-network-requests-that-set-a-specific-cookie-path"></a>查看设置了特定 cookie 路径的网络请求  

使用网络工具中的新筛选器关键字可以专注于设置特定 Cookie `cookie-path` 路径的网络[请求][MDNCookiePath]。 ****  

查看[按属性过滤请求][DevtoolsNetworkReferenceFilterRequestsProperties]以发现更多关键词，例如`cookie-path`。

### <a name="dock-to-left-from-the-command-menu"></a>从 "命令" 菜单向左停靠  

打开 ["命令菜单"][DevToolsCommandMenuIndex]，并运行" `Dock to left` "命令以将 DevTools 移到视线的左侧。  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="DevTools 停靠在视线左侧" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   DevTools 停靠在视线左侧  
:::image-end:::  

> [!NOTE]
> 自 Microsoft Edge 75 以来，**停靠到左侧**功能已可用，但以前只能从[主菜单][DevtoolsCustomizePlacementsChangeMainMenu]中进行访问。  Microsoft Edge 83 中的新功能是，你现在可以从 "命令" 菜单中访问此功能。  

通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！  

Chromium 问题 [#1011679][CR1011679]  

### <a name="the-audits-panel-is-now-the-lighthouse-panel"></a>"审核" 面板现在是 "灯塔" 面板  

DevTools 团队经常从 Web 开发人员那里获得反馈，尽管可以从 DevTools 运行[灯塔][GithubGoogleChromeLighthouse]，但在尝试运行时却找不到“灯塔”面板，因此**审核**面板现在是**灯塔**面板。  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="灯塔面板" lightbox="../../media/2020/03/lighthouse.msft.png":::
   灯塔面板  
:::image-end:::  

> [!NOTE]
> **灯塔** 面板提供了指向第三方网站上托管内容的链接。  Microsoft 对这些网站及其可能收集的任何数据的内容不承担任何责任。  

### <a name="delete-all-local-overrides-in-a-folder"></a>删除文件夹中的所有本地覆盖  

设置本地覆盖**** 后，你可以将鼠标悬停在目录上，打开上下文菜单 \ (右键单击\) ，然后选择新的"删除所有覆盖"选项以删除该**** 文件夹中的所有局部覆盖。  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="删除所有覆盖" lightbox="../../media/2020/03/overrides.msft.png":::
   删除所有覆盖  
:::image-end:::  

通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！  

Chromium 问题 [#1016501][CR1016501]  

### <a name="updated-long-tasks-ui"></a>更新的长任务 UI  

**长任务**是长时间垄断了主线程，从而导致网页冻结的 JavaScript 代码。  

你已经能够[在“性能”面板中可视化长任务][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]了一段时间，但是在Microsoft Edge 83中，“性能”面板中的长任务可视化 UI 已更新。  现在，任务的长任务部分的颜色为带条纹红色背景。  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新的长任务 UI" lightbox="../../media/2020/03/long-task.msft.png":::
   新的长任务 UI  
:::image-end:::  

通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！  

Chromium 问题 [#1054447][CR1054447]  

### <a name="maskable-icon-support-in-the-manifest-pane"></a>"清单" 窗格中的可屏蔽图标支持  

Android Oreo 引入了自适应图标，可在不同的设备模型之间显示各种形状中的应用图标。  **可屏蔽图标**是支持自适应图标的新图标格式，使你可以确保[ PWA ][ProgressiveWebAppsChromiumIndex]图标在支持可屏蔽图标标准的设备上看起来不错。  

在**清单**窗格中启用新的**仅显示可屏蔽图标的最小安全区域**复选框，以检查可屏蔽图标在 Android Oreo 设备上看起来是否良好。  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="仅显示可屏蔽图标的最小安全区域复选框" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   " **仅显示可屏蔽图标的最小安全区域"** 复选框  
:::image-end:::  

> [!NOTE]
> 此功能在 Microsoft Edge 81 中发布。  ["DevTools （Microsoft Edge 81）"][WhatsNew81]中的新增功能未涵盖 Microsoft Edge 83 中介绍的更新。  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[WhatsNew81]: ../01/devtools.md "DevTools 中的新增功能 (Microsoft Edge 81) | Microsoft Docs"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "使用 Microsoft Edge 开发工具命令菜单运行命令"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "使用颜色选取器更改颜色|Microsoft Docs"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门 | Microsoft 文档"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "从主菜单菜单更改|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "查看主线程活动|Microsoft Docs"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "使用&quot;呈现&quot;选项卡功能分析|Microsoft Docs"  
[ProgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 应用上的渐进式 Web |Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备|Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "代码行断点 - 如何在 Microsoft Edge DevTools |Microsoft Docs"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "按属性筛选请求 - 网络分析参考|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools |Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows 设备门户概述"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 适用的远程工具 (Beta)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "在适用于 Microsoft Edge 的稳定频道版本上更新"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer - GitHub"  

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  
[TheWebWeWant]: https://webwewant.fyi "我们想要的网络"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "色盲类型"  

[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "接受语言|MDN"  
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives "Cookie 设置|MDN"  

[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "依赖于区域设置的代码示例"  

[CR963183]: https://crbug.com/963183 "问题 963183：DevTools 不符合 WCAG"  
[CR1003700]: https://crbug.com/1003700 "问题 1003700：添加 DevTools 支持颜色视觉缺陷模拟"  
[CR1011679]: https://crbug.com/1011679 "问题 1011679：使用命令菜单引入 &quot;停靠到左侧&quot;"  
[CR1016501]: https://crbug.com/1016501 "问题 1016501：功能请求：用于删除所有本地覆盖的按钮"  
[CR1050999]: https://crbug.com/1050999 "问题 1050999：“属性”选项卡"  
[CR1051466]: https://crbug.com/1051466 "问题 1051466：支持 DevTools 中的 COOP/COEP 调试"  
[CR1054447]: https://crbug.com/1054447 "问题 1054447：更新 DevTools 时间线中的性能指标"  
[CR1051822]: https://crbug.com/1051822 "问题 1051822：DevTools：将 UI 添加到仿真区域设置"
[CR1041830]: https://crbug.com/1041830 "问题 1041830：改进断点颜色"
[ CR1050855]: https://crbug.com/1050855  "问题 1050855：难以发现设置视图"
[CR1056348]: https://crbug.com/1056348 "问题 1056348：信息栏组件刷新"

[ COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn  "COOP 和 COEP 详解——跨域开放者策略"   
[ COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2  "COOP 和 COEP 详解——跨域嵌入程序策略"   

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "灯塔 | GitHub"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developer.chrome.com/blog/new-in-devtools-83)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
