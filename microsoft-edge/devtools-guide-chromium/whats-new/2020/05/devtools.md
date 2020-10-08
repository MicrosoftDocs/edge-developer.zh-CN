---
description: 在 Windows 高对比度模式中使用 DevTools，将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配，以及更多。
title: DevTools (Microsoft Edge 84) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 2752dec8bc7c4eec34ddde05a7dedff7bebef05f
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015487"
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

# DevTools (Microsoft Edge 84) 中的新增功能  

## 来自 Microsoft Edge 开发人员工具团队公告  

以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！ 查看它们以尝试 DevTools、Visual Studio 代码扩展等中的新功能。  若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。  

### 在 Windows 高对比度模式下使用 DevTools

Microsoft Edge DevTools 现在在 Windows 处于高对比度模式下显示为高对比度模式。  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/high-contrast.msft.png":::
   高对比度模式下的 Microsoft Edge DevTools  
:::image-end:::  

[按照说明在 Windows 中打开 "高对比度" 模式][MicrosoftSupportWindows10HighContrastMode]。  通过按或，在 Microsoft Edge 中打开 DevTools `F12` `Ctrl` + `Shift` + `I` 。  DevTools 在 "高对比度" 模式下显示。  

> [!NOTE]
> Microsoft Edge DevTools 目前支持 Windows 上的高对比度模式，但不支持 macOS 上的高对比度模式。 

Chromium 问题 [#1048378][CR1048378]  

### 将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配  

从你的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team) 和 [Chromium 公共问题跟踪][CRIssuesList]器开始，Microsoft Edge DevTools 团队发现你希望能够在 DevTools 中自定义键盘快捷方式。  在 Microsoft Edge 84 中，你现在可以将 DevTools 中的键盘快捷方式与 [Visual Studio 代码][VSCode]匹配，这只是团队在为快捷方式自定义而处理的功能之一。  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   高对比度模式下的 Microsoft Edge DevTools  
:::image-end:::  

若要尝试实验，请按下 "DevTools" `?` 或选择 ![ ][ImageSettingsIcon] DevTools 右上角的 DevTools "设置" 图标来打开 "设置"。  导航到 " **实验** " 部分，然后选中 **"启用自定义键盘快捷方式设置" 选项卡， (需要重新加载) **。  现在重新加载 DevTools，再次打开 "设置"，然后导航到 " **快捷方式** " 部分。  

选择 " **)  (DevTools** " 中的 "选择"，然后选择 "**匹配预设的快捷方式**" 下拉列表，然后选择**Visual Studio 代码**  DevTools 中的键盘快捷方式现在与 Visual Studio 代码中等效操作的快捷方式相匹配。  

例如，在 [Visual Studio 代码][VSCodeShortcuts] 中暂停或继续运行脚本的键盘快捷方式是 `F5` 。  通过 **DevTools (Default) ** 预置，DevTools 中的同一快捷方式， `F8` 但在 **Visual Studio 代码** 中，该快捷方式现在也是如此 `F5` 。  

此功能目前可在 Microsoft Edge 84 中提供，因此请与团队分享你的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！  

Chromium 问题 [#174309][CR174309]  

### 远程调试 Surface 双核模拟器  

现在，你可以使用[Microsoft Edge DevTools][DevToolsChromiumGuide]的完整功能远程调试[Surface 双核处理器技术][DualScreensAndroidEmulator]中运行的 web 内容。  

借助 [Surface 双核模拟器][DualScreensAndroidEmulator]，你可以测试 web 内容在新的折叠和双屏幕设备上的呈现方式。  仿真器运行 Android 操作系统并提供 [Microsoft Edge Android 应用][AndroidEdge]。  在 [Microsoft edge 应用][AndroidEdge] 中加载你的 web 内容，并将其与 [microsoft edge DevTools][DevToolsChromiumGuide]进行调试。  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   Surface 双核模拟器上的 Microsoft Edge 应用  
:::image-end:::  

`edge://inspect` [Microsoft Edge][DesktopEdge]桌面实例中的页面显示**SurfaceDuoEmulator** ，其中列出了在[Surface 双核仿真器][DualScreensAndroidEmulator]上运行的打开的选项卡或[PWAs][PwaIndex] 。  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   `edge://inspect`页面显示在仿真器上运行的 Microsoft Edge 应用中打开的选项卡的列表
:::image-end:::  

为要调试的选项卡或 PWA 选择 " **检查** " 将打开 " [Microsoft Edge DevTools][DevToolsChromiumGuide]"。  [按照分步指南，在 Surface 双核模拟器上远程调试 web 内容][DevToolsRemoteDebugDuoEmulator]。  

### 更轻松地调整 DevTools 抽屉的大小  

在 Microsoft Edge 83 或更早版本中，你只能通过将 [DevTools 抽屉][DevToolsDrawer] 悬停在抽屉的工具栏内来调整其大小。  抽屉的行为与 DevTools 中的窗格的其他调整控件的行为不同，您将鼠标悬停在窗格边框上以调整其大小。  选择下图以查看如何在版本83或更早版本的 Microsoft Edge 中调整抽屉的大小。  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   在 Microsoft Edge 83 中调整 DevTools 抽屉的大小
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

从 Microsoft Edge 84 开始，您现在可以通过将抽屉悬停在抽屉的边框上来调整抽屉的大小。  此更改将 DevTools 抽屉大小的行为与 DevTools 中的其他窗格调整大小的方式对齐。  选择以下图像以查看 Microsoft Edge 84 中的 "操作调整大小"。  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   在 Microsoft Edge 84 中调整 DevTools 抽屉的大小
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

Chromium 问题 [#1076112][CR1076112]  

### Screencasting 导航按钮显示焦点  

当远程调试 [Android 设备][DevToolsRemoteDebugAndroid]、 [Windows 10 设备][DevToolsRemoteDebugWindows]或 [Surface 双核模拟器][DevToolsRemoteDebugDuoEmulator]时，可以使用 ![ DevTools 左上角的 "切换说明截屏视频" 图标切换 screencasting ][ImageScreencastingIcon] 。  如果启用了 screencasting，你可以从 DevTools 窗口中的远程设备上的 Microsoft Edge 中导航选项卡。  在 Microsoft Edge 84 中，这些导航按钮现在也可通过键盘访问。  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   按 `Shift` + `Tab` screencasted URL 栏中的说明将焦点放在 "**刷新**" 按钮上
:::image-end:::  

Chromium 问题 [#1081486][CR1081486]  

### 现在可以访问网络面板的详细信息窗格  

在 Microsoft Edge 84 中，当您为[网络日志][DevToolsNetworkLog]中的资源打开 "**网络**" 面板中的 "[详细信息" 窗格][DevToolsNetworkDetails]时，它们现在将获得焦点。  此更改允许屏幕阅读器读出 " **详细信息** " 窗格的内容并与之交互。  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/network-details.msft.png":::
   "**网络**" 面板中的 "**详细信息**" 窗格在打开时获得焦点
:::image-end:::  

Chromium 问题 [#963183][CR963183]  

## 来自 Chromium 项目的公告  

以下各节宣布了在 Microsoft Edge 84 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。  

### 通过 DevTools 抽屉中的新问题工具修复网站问题

DevTools 抽屉中的 "新建 **问题** " 工具可帮助减少 **控制台**的通知 fatigue 和混乱。  当前，该 **控制台** 是网站开发人员、库、框架和 Microsoft Edge 的中心位置，用于记录消息、警告和错误。  " **问题** " 工具将来自浏览器的警告聚合到 Microsoft Edge DevTools 中受影响的资源的链接，并提供有关如何解决这些问题的指南。  随着时间的推移，你应在 " **问题** " 工具（而不是 **控制台**）的 Microsoft Edge 呈现形式中看到更多警告，这有助于减少在 **控制台**中的混乱。  

若要开始使用，请参阅 [查找并修复 Microsoft Edge DevTools 问题工具的相关问题][DevtoolsIssuesIndex]。  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/issues.msft.png":::
   DevTools 抽屉中的 " **问题** " 工具  
:::image-end:::  

Chromium 问题 [#1068116][CR1068116]  

### 查看 "检查模式" 工具提示中的辅助功能信息  

" **检查模式** 工具提示" 现在指示元素是否具有可访问的 [名称和角色][WebhintHintsAxeNameRoleValue] 且可通过 [键盘获得焦点][WebhintHintsAxeKeyboard]。  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/a11y.msft.png":::
  带有辅助功能信息的 " **检查模式** " 工具提示  
:::image-end:::  

Chromium 问题 [#1040025][CR1040025]  

### 性能面板更新  

#### 查看页脚中的总阻塞时间信息  

记录加载性能后， **性能** 面板现在显示总阻塞时间 \ (TBT \ ) 页脚中的信息。  TBT 是一种加载性能指标，可帮助量化页面变得可用的时间。  它实质衡量页面的显示时间，因为内容呈现到屏幕 ) ，因此它的使用时间为 (;但实际上并不是可用的，因为 JavaScript 阻止主线程，因此页面不响应用户输入。  TBT 是 approximating 第一个输入延迟的主要指标。  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

若要获取总阻塞时间信息，请不要使用**Refresh Page** ![ 用于录制页面加载性能的刷新页面刷新页面图标 ][ImageRefreshPageIcon] 工作流。  

而是选择 " **录制** ![ 录制 ][ImageRecordIcon] " 图标，手动重新加载页面，等待页面加载，然后停止录制。  

如果你看到 `Total Blocking Time: Unavailable` ，Microsoft Edge DevTools 不会从 Microsoft edge 中的内部分析数据获取所需的信息。  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/tbt.msft.png":::
   **性能**面板录制的页脚中的总阻塞时间信息  
:::image-end:::  

Chromium 问题 [#1054381][CR1054381]  

#### "新体验" 部分中的布局切换事件  

"**性能**" 面板的 "新**体验**" 部分可帮助你检测布局切换。  累积布局切换 \ (CLS \ ) 是有助于量化不需要的视觉不稳定性的指标。

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

选择 " **布局移动** " 事件可在 " **摘要** " 窗格中查看布局切换的详细信息。  将鼠标悬停在 " **移动的源** " 和 " **移动到** " 字段上，以直观显示发生布局变化的位置。  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/cls.msft.png":::
   布局切换的详细信息  
:::image-end:::  

### 在控制台中获得更准确的承诺术语  

当日志记录时 `Promise` ， **控制台** 不正确地 `PromiseStatus` 将值设置为 `resolved` 。  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/resolved.msft.png":::
   使用旧术语的**控制台**示例 `resolved`  
:::image-end:::  

现在，该 **控制台** 使用 `fulfilled` 与规范对齐的术语 `Promise` 。  有关规范的详细信息 `Promise` ，请参阅 [GitHub 上的状态和 Fates](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)。  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/fulfilled.msft.png":::
  使用新术语的**控制台**示例 `fulfilled`  
:::image-end:::  

V8 问题 [#6751][CRV86751]  

### "样式" 窗格更新  

#### 对 revert 关键字的支持  

" **样式** " 窗格的 "自动完成" UI 现在检测到 " [还原][MDNRevert] CSS" 关键字，该关键字可将属性的级联值还原为应用于该元素的样式的上一个值。  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/revert.msft.png":::
  将属性的值设置为 "还原"  
:::image-end:::  

Chromium 问题 [#1075437][CR1075437]  

#### 图像预览  

将鼠标悬停 `background-image` 在 " **样式** " 窗格中的某个值上，可在工具提示中查看图像的预览。  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/image-preview.msft.png":::
  将鼠标悬停在某个 `background-image` 值上  
:::image-end:::  

Chromium 问题 [#1040019][CR1040019]  

#### 颜色选取器现在使用空格分隔的功能颜色表示法  

[CSS 颜色模块级别 4][CSSWGDraftsColor4Changes3] 指定颜色函数（例如 `rgb()` ）应支持以空格分隔的参数。  例如，`rgb(0, 0, 0)` 与 `rbg(0 0 0)` 等效。  

使用 [颜色选取器][DevtoolsCssReferenceColorPicker] 选择颜色或在 "样式" 窗格中通过按住并选择值在 " **样式** " 窗格中交替颜色表示时 `Shift` `background-color` ，应看到以空格分隔的参数语法。  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/color.msft.png":::
  在 " **样式** " 窗格中使用空格分隔的参数  
:::image-end:::  

还应在 " **计算** " 窗格和 " **检查模式** 工具提示" 中查看语法。  

Microsoft Edge DevTools 使用新语法，因为即将出现的 CSS 功能（如 [color ( # B1 ][CSSWGDraftsColor4Property] ）不支持弃用的逗号分隔参数语法。  

在大多数浏览器中，一段时间内支持空格分隔的参数语法。  有关详细信息，请参阅 [我是否可以使用：以空格分隔的功能颜色表示法？][CaniuseMDNSpaceSeparatedFunctionalColorNotations]  

Chromium 问题 [#1072952][CR1072952]  

### "元素" 面板中的 "属性" 窗格的弃用  

"**元素**" 面板中的 "**属性**" 窗格已弃用。  `console.dir($0)`改为在**控制台**中运行。  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/properties.msft.png":::
   "已弃用的 **属性** " 窗格  
:::image-end:::  

#### 参考  

*   [ ( # A1 的 console][DevtoolsConsoleApiDir]  
*   [$0][DevtoolsConsoleUtilitiesDom]  

### 清单窗格中的应用快捷方式支持  

应用快捷方式可帮助用户在 web 应用中快速启动常见或建议的任务。  仅为在用户的桌面或移动设备上安装的 [渐进 Web 应用][PwaIndex] 显示 "应用快捷方式" 菜单。  

<!--For more information, see [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  **清单**窗格中的应用快捷方式  
:::image-end:::  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge Devtools 团队取得联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/settings-icon.msft.png  
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/toggle-screencast-icon.msft.png  
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/refresh-page-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/record-icon.msft.png  

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "使用 Surface 双核仿真器 |Microsoft 文档"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir-控制台 API 参考 |Microsoft 文档"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象-控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "用颜色选取器更改颜色-CSS 参考 |Microsoft 文档"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义概述 |Microsoft 文档"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并修复 Microsoft Edge DevTools 问题选项卡 |Microsoft 文档"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "开始使用 "远程调试 Android 设备" |Microsoft 文档"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "远程调试 Surface 双核模拟器入门 |Microsoft 文档"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备入门 |Microsoft 文档"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "检查资源的详细信息 |Microsoft 文档"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动 |Microsoft 文档"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用 |Microsoft 文档"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android 应用"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "以空格分隔的功能颜色表示法-MDN |我是否可以使用"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"  
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG 标准 |Chromium bug"  
[CR1040019]: https://crbug.com/1040019 "DevTools：在 "样式" 窗格中轻松预览图像和背景图像 |Chromium bug"  
[CR1040025]: https://crbug.com/1040025 "DevTools：显示元素 popover | 中的基本 a11y 信息Chromium bug"  
[CR1048378]: https://crbug.com/1048378 "高对比度模式下的 DevTools UI 支持 |Chromium bug"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium bug"  
[CR1068116]: https://crbug.com/1068116 "发货问题面板 |Chromium bug"  
[CR1072952]: https://crbug.com/1072952 "DevTools：拾色器应生成新式 CSS 颜色语法 |Chromium bug"  
[CR1075437]: https://crbug.com/1075437 "DevTools：添加对 CSS "revert" 关键字/值的支持 |Chromium bug"  
[CR1076112]: https://crbug.com/1076112 "Devtools 个性化设置-抽屉调整人"  
[CR1081486]: https://crbug.com/1081486 "说明截屏视频模式中的导航按钮不可见的键盘焦点 |Chromium bug"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus 应为 "已完成"，而不是 "已解决" |V8 bug"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "从颜色 3-CSS 颜色模块级别4开始的更改 |W3C CSS 工作组编辑器草稿"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. 前景颜色： "Color"-CSS 颜色模块级别 4 |W3C CSS 工作组编辑器草稿"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新的 Microsoft Edge 简介"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "州和 Fates-domenic/承诺-解包 |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "还原 |MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "浏览器兼容性 |MDN"  

[VSCode]: https://code.visualstudio.com/ "Visual Studio 代码"  
[VSCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "适用于 Windows 的 Visual Studio 代码键盘快捷方式"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "Axe：键盘 |WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "Axe： Name Role Value |WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "在 Windows | 中打开或关闭高对比度模式Windows 支持"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"  

<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebdevCoreWebVitals]: https://alphabet-dev/vitals#core-web-vitals "Core Web Vitals | alphabet-dev"  -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/updates/2020/05/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
