---
description: Emulate color vision deficiencies, Dock To Left in the Command Menu, and more.
title: What's new in DevTools (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f9eb306ab7b30495c91ff4a70797898459d7e722
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015480"
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

# DevTools （Microsoft Edge 83）中的新增功能  

按照更新的 Chromium 计划，我们将调整即将推出的 Microsoft Edge 版本的计划，并取消 Microsoft Edge 82 版本。 有关详细信息，请查看我们的 [博客文章][WindowsBlogStableRelease]。  

下面是 Microsoft Edge 83 的 DevTools 中提供的新功能。  

## 来自 Microsoft Edge 开发人员工具团队公告  

The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team! Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.  若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。  

### 在 Windows 10 设备上远程调试 Microsoft Edge  

现在，[Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 \(Beta\)][RemoteTools] 应用。  使用此应用程序扩展了[ Windows 设备门户][WindowsUwpDebugTestPerfDevicePortal]，你可以将开发计算机上运行的 Microsoft Edge 实例连接到远程 Windows 10 设备，请参阅目标列表\（Windows 10 设备上将打开 Microsoft Edge 和[ PWAs ][PprgressiveWebAppsChromiumIndex]中的所有选项卡\），然后针对远程 Windows 10 设备上运行的目标使用开发计算机上的 DevTools。  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/remote-tools.msft.png":::
   The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]  
:::image-end:::  

[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].  Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!  

### New ways to access Settings  

你可以自定义大量的 DevTools 设置，以使 DevTools 外观、感觉和工作方式达到你的要求。 在 Microsoft Edge 83 中，访问 DevTools 中的 [设置][DevtoolsCustomizeIndexSettings] 现在更为简单。 使用 "控制台警报" 和 "主菜单" 旁边的齿轮图标打开 "设置"。  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/settings.msft.png":::
   The gear icon opens **Settings** in the DevTools  
:::image-end:::  

You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/settings2.msft.png":::
   **Main Menu** > **More tools** > **Settings**  
:::image-end:::  

Chromium issue [#1050855][CR1050855]

### 新增和改进的 infobars

DevTools 中的信息性通知栏 \(infobars\) 现在具有改进的外观和功能。 在 Microsoft Edge 83 中，infobars 更易于阅读和提供按钮，以便你能够立即执行相关操作。  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/infobar.msft.png":::
   Infobar for pretty-printing a minified file in Microsoft Edge Version 83  
:::image-end:::  

Chromium issue [#1056348][CR1056348]

### 使用键盘导航颜色选取器  

[颜色选取器][DevtoolsCssReferenceColorPicker] 是 "[元素][DevtoolsCssIndex]" 面板中的 GUI 用于更改 `color` 和 `background-color` 声明。  在早期版本的 Microsoft Edge 中，无法使用键盘导航 [颜色选取器][DevtoolsCssReferenceColorPicker] 的 **阴影** 部分。  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/color-picker.msft.png":::
   You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]  
:::image-end:::  

在 Microsoft Edge 83 中，你可以使用键盘在颜色选取器的**阴影** 部分移动选取器。  

Chromium 问题 [#963183][CR963183]  

### 现在，刷新页面后将填充“属性”选项卡  

在 Microsoft Edge 81 及更早版本中，在 "[元素][DevtoolsCssIndex]" 面板中的 **"属性"选项卡**因页面刷新而损坏。  刷新页面时，**"属性" 选项卡** 未填充当前所选元素的属性。  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh  
:::image-end:::  

在 Microsoft Edge 83 中，你现在可以在 **"属性" 选项卡**中页面刷新后看到当前所选元素的属性。  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh  
:::image-end:::  

Chromium issue [#1050999][CR1050999]  

### 使用箭头键在 "更改" 工具中滚动  

**"更改" 工具** 跟踪你对 DevTools 中的 CSS 或 JavaScript 所做的任何更改。  你可使用 **"更改" 工具** 快速查看所有更改，并将其放回编辑器/IDE。  

按 DevTools 中的 "`Ctrl`+`Shift`+`P`"，打开 **"更改"工具**，以打开 "[命令菜单][DevToolsCommandMenuIndex]" 并键入 `changes`。  选择并运行 "**显示更改**" 命令以在 DevTools 抽屉中打开 **"更改" 工具**。  

对缩小文件进行更改后，**"更改" 工具** 可用于水平滚动以查看所有缩小代码。  从 Microsoft Edge 83 开始，你现在可以使用键盘上的箭头键水平滚动。  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/changes.msft.png":::
   In Microsoft Edge 83, you may scroll horizontally with the arrow keys to see the changes you made to your minified code in the **Changes tool**  
:::image-end:::  

If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!  

Chromium issue [#963183][CR963183]  

## 来自 Chromium 项目的公告  

以下各部分公布了 Microsoft Edge 83 中提供的其他功能，这些功能是对开源 Chromium 项目的贡献。  

### 模仿视觉缺陷  

打开["渲染" 选项卡][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] ，使用新的"**模拟视觉缺陷**" 功能，更好地了解有不同类型视觉缺陷的人们如何体验你的网站。  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/vision.msft.png":::
   Emulating blurred vision  
:::image-end:::  

DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].  

| 颜色视觉缺陷 | 详细信息 |  
|:--- |:--- |  
| 红色盲 | 无法感觉任何红色的光线。 |  
| 绿色盲 | 无法感觉任何绿色的光线。 |  
| 黄蓝色盲 | 无法感觉任何蓝色的光线。 |  
| 全色盲 | 无法感觉任何颜色，灰色阴影除外\（极少\）。 |  

存在这些色觉缺陷的不太极端的版本，实际上它们更为常见。  
例如，红色弱降低了对红光的敏感性（与红色盲相对，后者完全无法感知红光）。 但是，这些异常视力缺陷的定义不是很明确：每个视力缺陷者都不同，并且可能看到的事物都不相同（能够感知更多/更少的相关颜色）。  

通过在 DevTools 中进行更极端的仿真设计，可以保证红色弱、绿色弱、黄蓝色弱和全色弱的人也可访问你的 Web 应用。  

Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!  

Chromium issue [#1003700][CR1003700]  

### 模拟语言环境  

通过在**传感器**  >  **位置**中设置位置来模拟语言环境。 [打开**命令菜单** ][DevToolsCommandMenuIndex]，然后键入`Sensors`以访问**传感器**选项卡。执行完这些操作后，DevTools 会修改当前的默认语言环境，从而影响以下代码。  

*   `Intl.*` 例如，API： `new Intl.NumberFormat().resolvedOptions().locale`  
*   其他可识别语言环境的 JavaScript API，例如`String.prototype.localeCompare`和`*.prototype.toLocaleString`，例如： `123_456..toLocaleString()`  
*   DOM APIs such as `navigator.language` and `navigator.languages`  
*   The [Accept-Language][MDNAcceptLanguage] HTTP request header  

> [!NOTE]
> Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.  只有后续请求才会反映对 `Accept-Language` HTTP 标头的更改。  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/locale.msft.png":::
   Emulating a locale  
:::image-end:::  

To try a demo, see [Locale-dependent code example][MathiasByensLocaleDemo].

Chromium 问题 [#1051822][CR1051822]

### 跨域嵌入程序策略 (COEP) 调试  

"网络" 面板现在提供[跨域嵌入程序策略 (COEP)][COEP] 调试信息。  

“**状态**”列现在提供有关为何阻止请求的快速说明，以及查看该请求标头以进行进一步调试的链接：  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/status.msft.png":::
   Blocked requests in the **Status** column  
:::image-end:::  

The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/guidance.msft.png":::
   More guidance in the **Response Headers** section  
:::image-end:::  

Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!  

Chromium issue [#1051466][CR1051466]  

### New icons for breakpoints, conditional breakpoints, and logpoints  

The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:  

*   Breakpoints \(![Breakpoint](../../media/2020/03/breakpoint.msft.png)\) are represented by red circles.  
*   Conditional Breakpoints \(![Conditional Breakpoint](../../media/2020/03/conditional.msft.png)\) are represented by half-red half-white circles.  
*   Logpoints \(![Logpoint](../../media/2020/03/logpoint.msft.png)\) are represented by red circles with Console icons.  

The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.  

Chromium issue [#1041830][CR1041830]  

### View network requests that set a specific cookie path  

在**网络**面板中使用新的`cookie-path`过滤关键字来关注设置了特定[ cookie 路径][MDNCookiePath]的网络请求。  

查看[按属性过滤请求][DevtoolsNetworkReferenceFilterRequestsProperties]以发现更多关键词，例如`cookie-path`。

### 从 "命令" 菜单向左停靠  

打开 ["命令菜单"][DevToolsCommandMenuIndex]，并运行" `Dock to left` "命令以将 DevTools 移到视线的左侧。  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   DevTools docked to the left of the viewport  
:::image-end:::  

> [!NOTE]
> The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [Main Menu][DevtoolsCustomizePlacementsChangeMainMenu].  The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.  

Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!  

Chromium issue [#1011679][CR1011679]  

### "审核" 面板现在是 "灯塔" 面板  

DevTools 团队经常从 Web 开发人员那里获得反馈，尽管可以从 DevTools 运行[灯塔][GithubGoogleChromeLighthouse]，但在尝试运行时却找不到“灯塔”面板，因此**审核**面板现在是**灯塔**面板。  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/lighthouse.msft.png":::
   The Lighthouse panel  
:::image-end:::  

> [!NOTE]
> The **Lighthouse** panel provides links to content hosted on third-party websites.  Microsoft 对这些网站及其可能收集的任何数据的内容不承担任何责任。  

### 删除文件夹中的所有本地覆盖  

设置**本地覆盖**后可右键单击文件夹，然后选择新的 "**删除所有覆盖**" 选项以删除该文件夹中的所有本地覆盖。  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/overrides.msft.png":::
   Delete all overrides  
:::image-end:::  

Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!  

Chromium issue [#1016501][CR1016501]  

### 更新的长任务 UI  

**长任务**是长时间垄断了主线程，从而导致网页冻结的 JavaScript 代码。  

你已经能够[在“性能”面板中可视化长任务][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]了一段时间，但是在Microsoft Edge 83中，“性能”面板中的长任务可视化 UI 已更新。  现在，任务的长任务部分的颜色为带条纹红色背景。  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/long-task.msft.png":::
   The new Long Task UI  
:::image-end:::  

Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!  

Chromium issue [#1054447][CR1054447]  

### "清单" 窗格中的可屏蔽图标支持  

Android Oreo 引入了自适应图标，可在不同的设备模型之间显示各种形状中的应用图标。  **可屏蔽图标**是支持自适应图标的新图标格式，使你可以确保[ PWA ][PprgressiveWebAppsChromiumIndex]图标在支持可屏蔽图标标准的设备上看起来不错。  

在**清单**窗格中启用新的**仅显示可屏蔽图标的最小安全区域**复选框，以检查可屏蔽图标在 Android Oreo 设备上看起来是否良好。  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   The **Show only the minimum safe area for maskable icons** checkbox  
:::image-end:::  

> [!NOTE]
> This feature launched in Microsoft Edge 81.  The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].  

## Download the Microsoft Edge preview channels  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  The preview channels give you access to the latest DevTools features.  

## Getting in touch with Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[WhatsNew81]: ../01/devtools.md "What's New In DevTools (Microsoft Edge 81) | Microsoft Docs"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Run Commands With The Microsoft Edge DevTools Command Menu | Microsoft Docs"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "Change colors with the Color Picker | Microsoft Docs"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "Get Started With Viewing And Changing CSS | Microsoft Docs"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "Change placement from the main menu | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "View main thread activity | Microsoft Docs"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "Analyze rendering performance with the Rendering tab | Microsoft Docs"  
[PprgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Progressive Web Apps on Windows | Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Get Started with Remote Debugging Windows 10 Devices | Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "Line-of-code breakpoints - How To Pause Your Code With Breakpoints In Microsoft Edge DevTools | Microsoft Docs"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "Filter requests by properties - Network analysis reference | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "Settings - Customize Microsoft Edge DevTools  | Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal overview"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Remote Tools for Microsoft Edge (Beta)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview Channels"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "Update on Stable channel releases for Microsoft Edge"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "New Issue - MicrosoftDocs/edge-developer - GitHub"  

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | Post a Tweet"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter account"  
[TheWebWeWant]: https://webwewant.fyi "The Web We Want"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "Types of Colour Blindness"  

[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "Accept-Language | MDN"  
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives "Set-Cookie | MDN"  

[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "Locale-dependent code example"  

[CR963183]: https://crbug.com/963183 "问题 963183：DevTools 不符合 WCAG"  
[CR1003700]: https://crbug.com/1003700 "问题 1003700：添加 DevTools 支持颜色视觉缺陷模拟"  
[CR1011679]: https://crbug.com/1011679 "问题 1011679：使用命令菜单引入 "停靠到左侧""  
[CR1016501]: https://crbug.com/1016501 "问题 1016501：功能请求：用于删除所有本地覆盖的按钮"  
[CR1050999]: https://crbug.com/1050999 "问题 1050999：“属性”选项卡"  
[CR1051466]: https://crbug.com/1051466 "问题 1051466：支持 DevTools 中的 COOP/COEP 调试"  
[CR1054447]: https://crbug.com/1054447 "问题 1054447：更新 DevTools 时间线中的性能指标"  
[CR1051822]: https://crbug.com/1051822 "问题 1051822：DevTools：将 UI 添加到仿真区域设置"
[CR1041830]: https://crbug.com/1041830 "问题 1041830：改进断点颜色"
[ CR1050855]: https://crbug.com/1050855  "问题 1050855：难以发现设置视图"
[CR1056348]: https://crbug.com/1056348 "问题 1056348：信息栏组件刷新"

[ COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn  "COOP 和 COEP 详解——跨域开放者策略"   
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "COOP and COEP explained - Cross-Origin Embedder Policy"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse | GitHub"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/updates/2020/03/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
