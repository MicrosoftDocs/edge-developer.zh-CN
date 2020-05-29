---
title: DevTools 中的新增功能（Microsoft Edge 83）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 17dab9120535ae11ea5a5456552d47dbd7f9e236
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684718"
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







# DevTools 中的新增功能（Microsoft Edge 83）   

  

按照更新后的 Chromium 计划，我们将调整即将开始的 Microsoft Edge 发布和取消 Microsoft Edge 82 版本的计划。 有关详细信息，请查看我们的[博客文章][WindowsBlogStableRelease]。

下面是 Microsoft Edge 83 的 DevTools 中可用的新功能。

## Microsoft Edge DevTools 团队的公告  

以下部分是您可能已错过的 Microsoft Edge DevTools 团队的公告列表！ 请查看这些功能，尝试 DevTools、VS 代码扩展等中的新功能。  若要随时了解开发人员工具中的所有最新功能和最新功能，请下载[Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。  

### 在 Windows 10 设备上远程调试 Microsoft Edge  

Microsoft [Edge 的远程工具 \ （Beta \）][RemoteTools]应用现已在[microsoft Store][MicrosoftStore]中提供。  使用此应用（扩展[Windows Device Portal][WindowsDevicePortal]），你可以从你的开发计算机上运行的 Microsoft Edge 实例连接到远程 windows 10 设备，查看目标列表 \ （Microsoft Edge 中的所有选项卡和[PWAs][PWADoc]在 Windows 10 设备 \），并针对在远程 Windows 10 设备上运行的目标使用你的开发计算机上的 DevTools。  

> ##### 图 1  
> [Microsoft Store][MicrosoftStore]中可用的[Microsoft Edge 远程工具（Beta）][RemoteTools]应用  
> ![Microsoft Store 中可用的 Microsoft Edge 远程工具（Beta）应用][ImageRemoteTools]  

[阅读有关设置 Windows 10 设备和开发计算机以进行远程调试的指南][RemoteDebuggingWin10]。  通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标，让我们了解你的远程调试体验！  

### 访问设置的新方法 

你可以自定义的 DevTools 设置有很多种，以使 DevTools 外观、感觉和工作方式符合你的需求。 在 Microsoft Edge 83 中，访问 DevTools 中的[设置][OverviewSettings]现在更加轻松。 打开设置，"控制台通知" 和 "主菜单" 旁边的齿轮图标。

> ##### 图 2 
> 齿轮图标在 DevTools 中打开 "设置 ![ "，"齿轮" 图标在 DevTools 中打开 "设置"][ImageSettingsGearIcon]  

您还可以在 "**更多工具**" 下的**主菜单**中打开 "[设置][OverviewSettings]"。

> ##### 图 3 
> 主菜单 > 更多工具 > 设置 ![ 主菜单 > 更多工具 > 设置][ImageSettingsMainMenu]  

Chromium 问题[#1050855][crbug1050855]

### 新增功能和改进的 infobars

DevTools 中的信息性通知条 \ （infobars \）现在具有改进的外观和更多功能。 在 Microsoft Edge 83 中，infobars 更易于阅读和提供按钮，以便你能够立即执行相关操作。

> ##### 图 4
> 有关在 microsoft edge 83 信息栏中打印 minified 文件 ![ 以便在 Microsoft edge 83 中美观打印 minified 文件的信息栏][ImageInfobar]  

Chromium 问题[#1056348][crbug1056348]

### 通过键盘导航拾色器  

[颜色选取器][ColorPicker]是 "[元素" 面板][ElementsDoc]中用于更改 `color` 和声明的 GUI `background-color` 。  在早期版本的 Microsoft Edge 中，无法通过键盘导航[拾色器][ColorPicker]的 "**底纹**" 部分。  

> ##### 图 5  
> 现在，你可以使用键盘移动[颜色选取器][ColorPicker]的 "**底纹**" 部分中的选择器  
> ![现在，你可以使用键盘移动颜色选取器的 "底纹" 部分中的选择器][ImageColorPicker]  

在 Microsoft Edge 83 中，你现在可以使用键盘在拾色器的 "**底纹**" 部分移动选择器。  

Chromium 问题[#963183][crbug963183]  

### "属性" 选项卡现在将在页面刷新后填充  

在 Microsoft Edge 81 及更早版本中，"[元素" 面板][ElementsDoc]中的 "**属性" 选项卡**因页面刷新而损坏。  刷新页面后，"属性"**选项卡**不会填充当前所选元素的属性。  

> ##### 图 6  
> 在 Microsoft Edge 81 及更早版本中，在页面刷新后，"**属性" 选项卡**为空  
> ![在 Microsoft Edge 81 及更早版本中，在页面刷新后，"属性" 选项卡为空][ImagePropertiesIn81]  

在 Microsoft Edge 83 中，你现在可以在 "**属性" 选项卡**中的页面刷新后查看当前所选元素的属性。  

> ##### 图 7  
> 在 Microsoft Edge 83 中，在页面刷新后，"**属性" 选项卡**显示当前选定元素的属性  
> ![在 Microsoft Edge 83 中，在页面刷新后，"属性" 选项卡显示当前选定元素的属性][ImagePropertiesIn82]  

Chromium 问题[#1050999][crbug1050999]  

### 使用箭头键在 "更改" 工具中滚动  

"**更改" 工具**跟踪你对 DevTools 中的 CSS 或 JavaScript 所做的任何更改。  你可以使用 "更改"**工具**快速查看所有更改并将这些更改恢复到编辑器/IDE。  

通过**Changes tool** `Ctrl` + `Shift` + `P` 在 DevTools 中按下以打开 "[命令" 菜单][DevToolsCommandMenuIndex]并键入， `changes` 打开 "更改" 工具。  选择并运行 "**显示更改**" 命令以打开 DevTools 抽屉中的 "**更改" 工具**。  

对 minified 文件进行更改后，"**更改" 工具**使您能够水平滚动查看所有 minified 代码。  从 Microsoft Edge 83 开始，您现在可以使用键盘上的箭头键水平滚动。  

> ##### 图 8  
> 在 Microsoft Edge 83 中，你可以通过箭头键水平滚动，以在 "**更改" 工具**中查看你对 minified 代码所做的更改  
> ![在 Microsoft Edge 83 中，你可以通过箭头键水平滚动以在 "更改" 工具中查看你的 minified 代码][ImageChanges]  

如果您使用屏幕阅读器或键盘在 DevTools 中导航，请向我们发送您的反馈[发推至][PostTweetEdgeDevTools]，或单击 "[反馈](#feedback)" 图标！  

Chromium 问题[#963183][crbug963183]  

## 来自 Chromium 项目的公告  

以下各节宣布了在 Microsoft Edge 83 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。  

### 模仿视觉缺陷   

打开 "[呈现" 选项卡][RenderingDoc]，并使用新的 "**模拟视觉缺陷**" 功能来更好地了解具有不同类型的视觉缺陷的人如何体验您的网站。  

> ##### 图 9  
> 模拟模糊的视觉效果  
> ![模拟模糊的视觉效果][ImageEmulatingBlurredVision]  

DevTools 可以模拟模糊的视觉效果和以下[类型的颜色视觉缺陷][ColorBlindnessTypes]。  

| 颜色远景缺陷 | 详细信息 |  
|:--- |:--- | 
| Protanopia | 无法感觉任何红光。 |  
| Deuteranopia | 无法感觉任何绿色光。 |  
| Tritanopia | 无法感觉任何蓝色光线。 |  
| Achromatopsia | 除了灰色阴影的情况外，无法感知任何颜色（非常少见）。 | 

这些颜色视觉缺陷的极端版本较少，并且事实上它们更为常见。
例如，protanomaly 缩小了红灯的灵敏度（相对于 protanopia，这是完全无法感知红灯的功能）。 但是，这些 omaly 的视觉缺陷不是明确定义的：每个具有此类远景缺陷的人不同，并且可能会以不同的方式查看内容（能够感知更多/更少的相关颜色）。

通过针对 DevTools 中更极端的模拟进行设计，你的 web 应用可保证可供具有 protanomaly、deuteranomaly、tritanomaly 和 achromatomaly 的用户访问。

通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！  

Chromium 问题[#1003700][crbug1003700]  

### 模拟区域设置 

通过在**传感器**位置设置位置来模拟语言环境  >  **Location**。 [打开 "**命令" 菜单**][DevToolsCommandMenuIndex]并键入 `Sensors` 以访问 "**传感器**" 选项卡。执行这些操作后，DevTools 将修改当前默认区域设置，从而影响以下内容：

- `Intl.*` Api，例如： `new Intl.NumberFormat().resolvedOptions().locale`
- 其他与区域设置兼容的 JavaScript Api `String.prototype.localeCompare` `*.prototype.toLocaleString` ，例如和和：`123_456..toLocaleString()`
- DOM Api，如 `navigator.language` 和 `navigator.languages`
- [`Accept-Language`][MDNAcceptLanguage]HTTP 请求标头

> ##### 图 10  
> 模拟区域设置  
> ![模拟区域设置][ImageEmulatingLocales]  

若要尝试演示，请参阅与[区域设置相关的代码示例][MathiasByensLocaleDemo]。

Chromium 问题[#1051822][crbug1051822]

### 跨起源 Embedder 策略 \ （COEP \）调试   

现在，网络面板提供了[跨起源 Embedder 策略][COEP]调试信息。  

"**状态**" 列现在提供了有关阻止请求的原因的快速说明，以及用于查看该请求的标题以进行进一步调试的链接：  

> ##### 图 11  
> "**状态**" 列中的被阻止的请求  
> !["状态" 列中的被阻止的请求][ImageNetworkStatus]  

"**页眉**" 选项卡的 "**响应标题**" 部分提供了有关如何解决这些问题的更多指导：  

> ##### 图 12  
> "响应标题" 部分中的更多指导  
> !["响应标题" 部分中的更多指导][ImageNetworkGuidance]  

通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！  

Chromium 问题[#1051466][crbug1051466]  

### 查看设置特定 cookie 路径的网络请求 

使用 " `cookie-path` **网络**" 面板中的新筛选器关键字来集中关注设置特定[cookie 路径][MDNCookiePath]的网络请求。

[通过属性查看筛选器请求][NetworkProperties]以发现更多类似 `cookie-path` 的关键字。

### 从 "命令" 菜单**停靠到左侧**   

打开 "[命令" 菜单][DevToolsCommandMenuIndex]并运行 `Dock to left` 命令，将 DevTools 移到视区左侧。  

> ##### 图 13  
> 停靠在视区左侧的 DevTools  
> ![停靠在视区左侧的 DevTools][ImageDockToLeft]  

> [!NOTE]
> 自 Microsoft Edge 75 后，"**停靠到左侧**" 功能现已提供，但以前只能从[**主菜单**][MainMenuDoc]访问它。  Microsoft Edge 83 中的新功能是您现在可以从 "命令" 菜单访问此功能。  

通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！  

Chromium 问题[#1011679][crbug1011679]  

### "**审核**" 面板现在是**Lighthouse**面板   

DevTools 团队经常获得来自 web 开发人员的反馈，尽管可以从 DevTools 运行[Lighthouse][GithubGoogleChromeLighthouse] ，但他们尝试了无法找到 "Lighthouse" 面板，因此 "**审核**" 面板现在是 " **Lighthouse** " 面板。  

> ##### 图 14  
> Lighthouse 面板  
> ![Lighthouse 面板][ImageLighthouse]  

> [!NOTE]
> **Lighthouse**面板提供了指向第三方网站上托管内容的链接。  Microsoft 不承担任何责任，也不能控制这些网站的内容和他们可能收集的任何数据。  

### 删除文件夹中的所有本地覆盖   

设置**本地替代**后，您可以右键单击某个文件夹，然后选择 "新建**删除全部替代**" 选项以删除该文件夹中的所有本地覆盖。  

> ##### 图 15  
> 删除所有替代  
> ![删除所有替代][ImageDeleteOverrides]  

通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！  

Chromium 问题[#1016501][crbug1016501]  

### 更新的长任务 UI   

较**长任务**是 monopolizes 主线程长时间的 JavaScript 代码，导致网页冻结。  

现在，你可以在[性能面板中可视化长任务][LongTasksInPerformancePanel]，但在 Microsoft Edge 83 中，"性能" 面板中的长任务可视化用户界面已更新。  现在，任务的长任务部分使用带条纹红色背景进行着色。  

> ##### 图 16  
> 新的长任务 UI  
> ![新的长任务 UI][ImageLongTask]  

通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！  

Chromium 问题[#1054447][crbug1054447]  

### 清单窗格中的屏蔽图标支持   

Android Oreo 引入了自适应图标，可在不同的设备模型中显示各种形状的应用图标。  **屏蔽图标**是支持自适应图标的新图标格式，使你能够确保[PWA][PWADoc]图标在支持可屏蔽图标标准的设备上看起来更美观。  

启用 "新建" 仅显示**清单**窗格中的 **"屏蔽图标的最小安全区域"** 复选框，以检查 Android Oreo 设备上的可屏蔽图标是否正常显示。  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

> ##### 图 17  
> "仅显示屏蔽图标的最小安全区域" 复选框  
> !["仅显示屏蔽图标的最小安全区域" 复选框][ImageMaskableIcons]  

> [!NOTE]
> 此功能在 Microsoft Edge 81 中启动。  Microsoft Edge 83 中介绍的更新未在[DevTools （Microsoft Edge 81）中的新增功能][WhatsNew81]中介绍。  

## 反馈   

  

若要讨论此文章中的新功能和更改，或与 DevTools 相关的任何其他内容，请执行以下操作：  

*   使用 DevTools 中的**反馈**图标发送反馈  
*   Tweet [@EdgeDevTools][PostTweetEdgeDevTools]  
*   向[我们需要的网站][TheWebWeWant]提交建议  
*   此文档在[edge-开发人员][GitHubMicrosoftDocsEdgeDeveloperNewIssue]存储库中的文件错误  

> ##### 图18  
> Microsoft Edge DevTools 中的 "**反馈**" 图标  
> ![Microsoft Edge DevTools 中的 * * 反馈 * * 图标][ImageFeedbackIcon]  

## 下载 Microsoft Edge 预览频道   

如果你使用的是 Windows 或 macOS，请考虑将[Microsoft Edge 预览通道][MicrosoftEdgePreviewChannels]用作默认开发浏览器。  预览频道使您可以访问最新的 DevTools 功能。  

<!-- <<../../_shared/devtools-feedback.md>>

<<../../_shared/canary.md>>

<<../../_shared/discover.md>> -->

  

<!-- image links -->  

[ImageRemoteTools]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/remote-tools.msft.png "图1： Microsoft Store 中可用的 Microsoft Edge 远程工具（Beta）应用"  
[ImageSettingsGearIcon]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/settings.msft.png "图2： "齿轮" 图标在 DevTools 中打开 "设置""
[ImageSettingsMainMenu]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/settings2.msft.png "图3：主菜单 > 更多工具 > 设置"
[ImageInfobar]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/infobar.msft.png "图4：在 Microsoft Edge 83 中美观打印 minified 文件的信息栏"
[ImageColorPicker]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/color-picker.msft.png "图5：您现在可以使用键盘在拾色器的 "底纹" 部分移动选择器"  
[ImagePropertiesIn81]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/properties-in-81.msft.png "图6：在 Microsoft Edge 81 及更早版本中，在页面刷新后，"属性" 选项卡为空"  
[ImagePropertiesIn82]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/properties-in-82.msft.png "图7：在 Microsoft Edge 83 中，在页面刷新后，"属性" 选项卡显示当前选定元素的属性"  
[ImageChanges]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/changes.msft.png "图8：在 Microsoft Edge 83 中，你可以通过箭头键水平滚动，以在 "更改" 工具中查看你的 minified 代码"  
[ImageEmulatingBlurredVision]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/vision.msft.png "图9：模拟模糊的视觉效果"  
[ImageEmulatingLocales]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/locale.msft.png "图10：模拟区域设置"
[ImageNetworkStatus]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/status.msft.png "图11： "状态" 列中的被阻止的请求"  
[ImageNetworkGuidance]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/guidance.msft.png "图12： "响应标题" 部分中的更多指导"  
[ImageDockToLeft]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/dock-to-left.msft.png "图13：停靠在视区左侧的 DevTools"  
[ImageLighthouse]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/lighthouse.msft.png "图14： Lighthouse 面板"  
[ImageDeleteOverrides]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/overrides.msft.png "图15：删除所有替代"  
[ImageLongTask]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/long-task.msft.png "图16：新的长任务 UI"  
[ImageMaskableIcons]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/maskable-icons.msft.png "图17： "仅显示屏蔽图标的最小安全区域" 复选框"  
[ImageFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/feedback-icon.msft.png "图18： Microsoft Edge DevTools 中的 "反馈" 图标"  

[ImageLineOfCodeBreakpoint]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/breakpoint.msft.png
[ImageLogpoint]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/logpoint.msft.png

<!-- links -->  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |发布 Tweet"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题-MicrosoftDocs/edge-开发人员"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[TheWebWeWant]: https://aka.ms/webwewant "我们需要的网站"  

[WhatsNew81]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/01/devtools "DevTools 中的新增功能（Microsoft Edge 81）"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[ColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "通过拾色器更改颜色"  
[ElementsDoc]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门"  
[MainMenuDoc]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "从主菜单更改位置"  
[LongTasksInPerformancePanel]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "查看主线程活动"  
[RenderingDoc]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "通过 "渲染" 选项卡分析渲染性能"  
[PWADoc]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用"  
[RemoteDebuggingWin10]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备入门"  
[LineOfCodeBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "代码行断点"
[NetworkProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties
[OverviewSettings]: /microsoft-edge/devtools-guide-chromium/customize/#settings

[WindowsDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal 概述"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 远程工具（Beta 版）"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  
[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20/update-stable-channel-releases/ "在适用于 Microsoft Edge 的稳定信道版本上更新"

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness/ "色盲的类型"  
[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "接受语言"
[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "与区域设置相关的代码示例"
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives

[crbug963183]: https://crbug.com/963183 "问题963183： DevTools 不符合 WCAG"  
[crbug1003700]: https://crbug.com/1003700 "问题1003700：为颜色远景缺陷模拟添加 DevTools 支持"  
[crbug1011679]: https://crbug.com/1011679 "问题1011679：使用 "命令" 菜单引入 "停靠到左侧""  
[crbug1016501]: https://crbug.com/1016501 "问题1016501：功能请求：用于删除所有本地替代的按钮"  
[crbug1050999]: https://crbug.com/1050999 "问题1050999： "属性" 选项卡"  
[crbug1051466]: https://crbug.com/1051466 "问题1051466：在 DevTools 中支持合作基金/COEP 调试"  
[crbug1054447]: https://crbug.com/1054447 "问题1054447：在 DevTools 时间线中更新性能指标"  
[crbug1051822]: https://crbug.com/1051822 "问题1051822： DevTools：将 UI 添加到仿真区域设置"
[crbug1041830]: https://crbug.com/1041830 "问题1041830：改善断点颜色"
[crbug1050855]: https://crbug.com/1050855 "问题1050855：设置视图难以发现"
[crbug1056348]: https://crbug.com/1056348 "问题1056348：信息栏组件刷新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "合作基金和 COEP 解释-跨起源 Opener 政策"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "合作基金和 COEP 解释-跨起源 Embedder 政策"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse GitHub 存储库"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/updates/2020/03/devtools/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
