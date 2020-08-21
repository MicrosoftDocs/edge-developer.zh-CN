---
title: 'Microsoft Edge 80 移动版 DevTools (新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 03fd78eddf54b68d072ba11401a897ad9f109058
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942145"
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

# Microsoft Edge 80 移动版 DevTools (新增)   

## 来自 Microsoft Edge 开发人员工具团队公告  

以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！ 请查看这些公告，尝试使用 DevTools 和 VS 代码扩展等中的新功能。  若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。  

### DevTools 的辅助功能改进  

DevTools 团队已对 Chromium 作了 170 更改，以解决 DevTools 中的高影响颜色对比度、键盘和屏幕阅读器问题。  构建 Web 的每个开发人员都应该能够使用 DevTools。  

> ##### 图 1  
> 通过键盘导航和屏幕阅读器改进，开发人员工具中的性能工具  
> ![通过键盘导航和屏幕阅读器改进，开发人员工具中的性能工具][ImagePerformanceToolKeyboardReaderImprovements]  

希望了解如何使您的网页对所有用户使用？  下载 Microsoft Edge [的辅助][AccessibilityInsights] 功能见解和 [WebHint][WebhintBrowserExtension] 扩展以开始使用。  

如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过 [tweett 发送][PostTweetEdgeDevTools] 或单击"发送反馈"图标来向我们 [发送你的反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！  

Chromium 问题 [#963183][crbug963183]  

### 使用其他语言的 DevTools  

许多开发人员将使用 StackOverflow 和 VS 代码等其他开发人员工具，不只是使用英语。  我们很高为将公布发布的 DevTools 的本地化，你现在可以使用除英语之外的 10 种语言之一：  

:::row:::
   :::column span="":::
      简体\)  (- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;
   :::column-end:::
   :::column span="":::
      中文 \ (Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      法语 – 法国 - 法&#231;出
   :::column-end:::
   :::column span="":::
      German - desch
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      意大利语 - 意大利语
   :::column-end:::
   :::column span="":::
      日语 -  &#26085;&#26412;&#35486;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      当理 -  &#54620;&#44397;&#50612;
   :::column-end:::
   :::column span="":::
      葡葡葡图 -&#234;葡表
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      俄语 –  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;
   :::column-end:::
   :::column span="":::
      西班牙语 - espa 通&#241;旧
   :::column-end:::
:::row-end:::

<!--  
|  |  |  
|:--- |:--- |  
| Chinese (Simplified) - 中文（简体）| Chinese (Traditional) - 中文（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

导航到 `edge://flags` "启用 **"本地化开发人员工具** 标志并将其设为 **"启用**"。  此外， **将开发人员工具实用标志** 设置为" **已启用**"。  重新启动 Microsoft Edge 并打开 DevTools。  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  DevTools 在 Microsoft Edge 中匹配。 `edge://settings/languages`  

> ##### 图 2  
> 常规工具  
> ![常规工具][ImageLocalizedGerman]  

如果要使用不同于可用语言的 DevTools， [请向我们提供推][PostTweetEdgeDevTools] 送或单击"发送反馈 ["](#getting-in-touch-with-microsoft-edge-devtools-team) 图标。  

Chromium [问题#941561][crbug941561]  

### Webhint Microsoft Edge 扩展  

通过 Webhint Microsoft Edge 扩展，可轻松浏览网页，并在 DevTools 中轻松浏览网页，并获取关于辅助功能、浏览器兼容性、安全性、性能等的反馈。  阅读更多信息 [https://webhint.io][Webhint] 。  

> ##### 图 3  
> 安装了 Webhint 浏览器扩展时 DevTools 中的"提示"选项卡  
> ![安装了 Webhint 浏览器扩展时 DevTools 中的"提示"选项卡][ImageHintsTabWebhintExtension]  

[试用 Microsoft Edge 中的 Webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。  安装扩展后，打开 DevTools，然后选择"提示"选项卡。 在此处，运行可自定义网站扫描。  要了解详细信息 [，请转到][WebhintBrowserExtension] webhint.io。

### 3D 视图  

通过 **在文档对象模型** [\ (DOM\) ][MDNDocumentObjectModel] 或 [z 索][MDNZIndex] 引堆叠上下文中导航，使用 3D 视图调试你的 Web 应用程序。  

> ##### 图 4  
> DevTools 中的 3D 视图  
> ![DevTools 中的 3D 视图][Image3DView]  

若要访问 3D 视图，请 `edge://flags` 导航到并确保"开发人员 **工具** "实实标志设置为 **"已启用**"。  重新启动 Microsoft Edge 并打开 DevTools。  在 `F1` DevTools 或转到"**Settings**设置"，导航**到实测部分**，然后选中 **"启用 3D 视图**"复选框。  现在，在 `Ctrl`  +  `Shift`  +  `P` **3D 视图中键入并**选择"显示**3D 视图**"。  

我们正在处理 UI，并向 3D 视图添加更多功能，因此请向我们发送反 [馈](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium [问题#987787][crbug987787]

### Visual Studio代码扩展  

DevTools 团队还发布了 [用于 Visual Studio Code \ (VS Code\) ][VisualStudioCode] 的一些扩展，它允许你直接从文本编辑器使用 DevTools 的功能！ 请参阅以下扩展项：  

#### Microsoft Edge 的元素  

通过将 [Microsoft Edge \ (m Chromium\) 按钮扩展添加到的元素，从 VS ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] 代码内使用元素工具。  

> ##### 图 5  
> 使用用于 Microsoft Edge 扩展的元素 VS 代码中的元素工具  
> ![使用用于 Microsoft Edge 扩展的元素 VS 代码中的元素工具][ImageElementsVisualStudioCode]  

有关详细信息，请查目[Microsoft Edge 中的元素与代码扩展。][VisualStudioCodeElementEdgeExtension]  

#### Microsoft Edge 调试程序  

借助 Microsoft Edge 的 [调试程序][VisualStudioMarketplaceDebuggerEdge] ，直接从 VS 代码在 Microsoft Edge 中运行的 JavaScript！  

> ##### 图 6  
> VS 代码中的 Microsoft Edge 扩展程序  
> ![VS 代码中的 Microsoft Edge 扩展程序][ImageDebuggerExtensionVisualStudioCode]  

有关详细信息，请了解如何从[VS 代码调试 Microsoft Edge。][VisualStudioCodeDebuggerEdgeExtension]  

#### webhint  

[Webhint][VisualStudioMarketplaceWebhintExtension] VS 代码扩展在你编写 `webhint` 时使用它改进网页！ 此扩展基于分析在工作区文件上运行和 `webhint` 报告诊断。  

> ##### 图 7  
> Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件  
> ![Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件][ImageWebhintVisualStudioCodeExtensionWorkspace]  

[了解有关 VS 代码 Webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。  

### Visual Studio集成
在 Visual Studio 2019 版本 16.2 或更高版本中，Visual Studio 使用调试器调试在 Microsoft Edge 中运行的 JavaScript。  [请Visual Studio 2019，][MicrosoftVisualStudioDownloads] 试用此功能！  

> ##### 图 8  
> Visual Studio在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用"的选项  
> ![Visual Studio在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用"的选项][ImageVisualStudioLaunchWebApp]  

[阅读我们的博客文章以了解如何从 microsoft Edge Visual Studio。][MicrosoftVisualStudioBlogDebugJavascript]  

### 跟踪防护主机消息  

跟踪防护是 Microsoft Edge 中唯一的功能，可防止你被之前尚未访问过的网站进行跟踪。  默认跟踪防护设置是"平衡模式"，为了使体验保持平衡隐私和 Web 兼容性的体验，这将对第三方跟踪程序和已知的义务跟踪器进行保护。  为了在特定跟踪器被阻止时，为更深入地了解网页的兼容性，我们还在跟踪器被阻止时在主机中添加了警告邮件。  

> ##### 图 9  
> 跟踪防护阻止对跟踪器的存储的访问时主机中的消息  
> ![跟踪防护阻止对跟踪器的存储的访问时主机中的消息][ImageTrackingPrevention]  

[了解有关跟踪防护和在隐私和 Web 之间余额之间余额的详细信息][TrackingPrevention]。  

## 来自 Chromium 项目的公告  

以下部分公布给开源 Chromium 项目的 Microsoft Edge 中提供的其他功能。  

### 对主机中的允许和上课绑定的支持  

现在，主机支持兑换和 `let` `class` 语句。  重新声明是使用控制台试用新的 JavaScript 代码的 Web 开发人员的常见概用。  

> [!WARNING]
> 在主机之外或单台主机输入内，是否在脚本中重新声明 `let` `class` 导致 `SyntaxError` 。  

例如，以前在使用指南解读本地变量时， `let` 主机将威子数据将引发错误：  

> ##### 图 10  
> Microsoft Edge 79 中的主机显示了该按钮无法回收失败  
> ![Microsoft Edge 79 中的主机显示了该按钮无法回收失败][ImageConsoleRedeclarationFails]  

现在，主机允许重新声明：  

> ##### 图 11  
> Microsoft Edge 80 中的主机显示允许回收成功  
> ![Microsoft Edge 80 中的主机显示允许回收成功][ImageConsoleRedeclarationSucceeds]  

Chromium [问题#1004193][crbug1004193]  

### 改进了 WebAssembly 调试  

DevTools 已开始支持 [DWARF][DwarfHome]调试标准，这意味着在 DevTools 中通过代码逐步改进支持、设置断点并解决源语言的堆叠跟踪。  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
> ##### Figure  
> The new DWARF-powered WebAssembly debugging  
> ![The new DWARF-powered WebAssembly debugging][ImageDwarfPoweredWebAssemblyDebugging]  
-->  

### 网络面板更新  

#### "设计器"选项卡中的请求初始任务链接  

你现在能够以嵌套列表的形式查看网络请求的初级和依赖项。  这有助于你了解为何被请求了资源，或者由于脚本\ () 引发了哪些网络活动。  

> ##### 图 12  
> "指示器"选项卡中的请求初始任务链接  
> !["指示器"选项卡中的请求初始任务链接][ImageRequestInitiatorChain]  

在 ["网络"面板中记录网络活动之后][DevToolsNetworkIndex]，单击某个资源，然后转到 **"启动器"** 选项卡，以查看 **请求启动器中链接**：  

*   检查 **的资源为** 粗体。  在上面的屏幕截图中，是 `ai.2.min.js` 在检查的资源。  
*   检查的资源上方的资源就是 **初始值**。  在上面的屏幕截图中， `https://www.microsoftedgeinsider.com` 是初始的初始项 `ai.2.min.js` 。  换言之， `https://www.microsoftedgeinsider.com` 导致网络请求 `ai.2.min.js` 。  
*   已检查资源下方的资源是 **依赖项**。  在上面的屏幕截图中，是 `https://dc.services.visualstudio.com/v2/track` 一个依赖关系 `ai.2.min.js` 。  换言之， `ai.2.min.js` 导致网络请求 `https://dc.services.visualstudio.com/v2/track` 。  

> [!NOTE]
> 还可以通过保持此操作，然后将鼠标悬停在网络资源上来 `Shift` 访问指示器和依赖关系信息。  [查看视图指示器和依赖关系][DevToolsNetworkReferenceViewInitiatorsDependencies]。  

Chromium [问题#842488][crbug842488]  

#### 突出显示概述中所选的网络请求  

单击网络资源以检查网络资源后，网络面板现在会在概述中为该资源放置蓝 **色边框**。  这可以帮助您检测网络请求早于或晚于预期的。  

> ##### 图 13  
> 突出显示所检查资源的"概述"窗格  
> ![突出显示所检查资源的"概述"窗格][ImageOverviewPaneInspectedResource]  

Chromium [问题#988253][crbug988253]  

#### "网络"面板中的 URL 和路径列  

使用网络**面板**中的新 Path**和****URL**列查看每个网络资源的绝对路径或完整 URL。  

> ##### 图 14  
> 网络面板中新的路径和 URL 列  
> ![网络面板中新的路径和 URL 列][ImagePathNetworkPanel]  

右键单击**Waterfall 表标题**，选择路**径****或 URL**以显示新列。  

Chromium [问题#993366][crbug993366]  

#### 更新了用户代理字符串  

DevTools 支持通过"网络条件"选项卡设置自定义 **用户代理字符串** 。 用户代理字符串还影响附加到网络资源的 HTTP `User-Agent` 标头以及值 `navigator.userAgent` 。  

预定义的用户代理字符串已更新，以反过现代浏览器版本。  

> ##### 图 15  
> "网络条件"选项卡上的"用户代理"菜单  
> !["网络条件"选项卡上的"用户代理"菜单][ImageUserAgentNetworkConditionsTab]  

若要访问**网络条件，**[请打开命令菜单][DevToolsCommandMenuIndex]，并运行 `Show Network Conditions` 该命令。  

> [!NOTE]
> 你还可以在 [设备模式下设置用户代理字符串][DevToolsDeviceModeIndex]。  

Chromium [问题#1029031][crbug1029031]  

### "Audits"面板更新  

#### 新的配置 UI  

配置 UI 具有新的响应式设计，而且已经简化了控制选项。  有关 ["约定 UI"更改的详细信息，请参阅][GitHubGoogleChromeDevToolsAuditsPanelThrottling] "审批面板"视图。  

> ##### 图 16  
> 新的配置 UI  
> ![新的配置 UI][ImageConfigurationUI]  

### 范围选项卡更新  

#### 每个功能或每块覆盖模式  

"[封面"选项卡具有][DevToolsCoverageIndex]新的下拉菜单，允许您指定是否应为每个函数或每个块收集代码**覆盖数据**。 **per function**  **每个块** 覆盖范围更加详细，同样也更加收集开环。  默认情况下，DevTools **使用每个** 函数覆盖。  

> [!CAUTION]
> 你可能会看到大型代码覆盖 HTML 文件的差别，具体取决于是每个函数还**是****每个块模式使用**。  使用每个 **功能模式** 时，HTML 文件中的内联脚本将被作为函数处理。  如果该脚本在所有时运行，则 DevTools 将整个脚本标记为使用代码。  仅当脚本未在全部运行时，它将该脚本标记为未使用的代码时。  

> ##### 图 17  
> 封面模式下拉菜单  
> ![封面模式下拉菜单][ImageCoverageMode]  

#### 只有页面重新加载必须发出覆盖范围  

由于不可靠而删除不带页面重新加载的代码覆盖范围已被删除。  例如，如果运行时很长，并且 V8 垃圾收集器已将其清理，则函数可以报告为未使用。  

Chromium [问题#1004203][crbug1004203]  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2019/12/a11y-performance-tool.msft.gif "图 1：DevTools 中的性能工具，可通过键盘导航和屏幕阅读器改进"  
[ImageLocalizedGerman]: ../../images/2019/12/localized-devtools.msft.png "图 2：常规工作区中的 DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2019/12/webhint-browser-extension.msft.png "图 3：安装 Web hint 浏览器扩展时 Microsoft Edge DevTools 中的"提示"选项卡"  
[Image3DView]: ../../images/2019/12/3dview.msft.png "图 4：Microsoft Edge 开发工具中的 3D 视图"  
[ImageElementsVisualStudioCode]: ../../images/2019/12/elements-for-edge.msft.png "图 5：使用 Microsoft Edge 扩展的元素 ，VS 代码中的元素工具"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2019/12/vscode-debugger.msft.png "图 6：使用 VS 代码的 Microsoft Edge 扩展的调试程序"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2019/12/webhint-vscode-extension.msft.png "图 7：Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件"  
[ImageVisualStudioLaunchWebApp]: ../../images/2019/12/vs.msft.png "图 8：Visual Studio并通过在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用的选项"  
[ImageTrackingPrevention]: ../../images/2019/12/tracking-prevention.msft.png "图 9：跟踪阻止对跟踪器的存储的访问权限时，主机中的邮件"  
[ImageConsoleRedeclarationFails]: ../../images/2019/12/letbefore.msft.png "图 10：Microsoft Edge 79 中的主机显示了我们用于回收失败"  
[ImageConsoleRedeclarationSucceeds]: ../../images/2019/12/letafter.msft.png "图 11：Microsoft Edge 80 中的主机显示这是允许回收成功的"  
[ImageRequestInitiatorChain]: ../../images/2019/12/initiators.msft.png "图 12："指发器"选项卡中的请求发度器中链接"  
[ImageOverviewPaneInspectedResource]: ../../images/2019/12/overview.msft.png "图 13："概述"窗格突出显示检查的资源"  
[ImagePathNetworkPanel]: ../../images/2019/12/columns.msft.png "图 14："网络"面板中的新路径和 URL 列"  
[ImageUserAgentNetworkConditionsTab]: ../../images/2019/12/useragent.msft.png "图 15："网络条件"选项卡中的"用户代理"菜单"  
[ImageConfigurationUI]: ../../images/2019/12/start.msft.png "图 16：新的配置 UI"  
[ImageCoverageMode]: ../../images/2019/12/modes.msft.png "图 17："覆盖模式"下拉菜单"  

<!--[ImageDwarfPoweredWebAssemblyDebugging]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "使用 Microsoft Edge 开发人员工具命令菜单运行命令"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "在 Microsoft Edge DevTools 中，使用"覆盖"选项卡查找未使用的 JavaScript 和 CSS 代码"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "模拟移动版视区 - 在 Microsoft Edge DevTools 中模拟移动设备和设备模式"  
[DevToolsNetworkIndex]: ../../../network/index.md "检查 Microsoft Edge DevTools 中的网络活动"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: ../../../network/reference.md#view-initiators-and-dependencies "查看初级指示器和依赖关系 - 网络分析参考"  
[DevGuideEdgeHtmlWhatsNew]: ../../../../dev-guide/whats-new.md "EdgeHTML 中的新增功能"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge 的调试程序"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge 元素与代码扩展"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[crbug842488]: https://crbug.com/842488 "842488 - 将"初始指示人"字段添加到"页眉"选项卡 -"监视""  
[crbug988253]: https://crbug.com/988253 "988253 - Bug DevTools - 网络请求和时间线图之间无关联 - 监视"  
[crbug993366]: https://crbug.com/993366 "993366 - 请在网络请求列表中显示 URL 的路径部分 - 监视器"  
[crbug1004193]: https://crbug.com/1004193 "1004193 - V8 的 REPL 模式 - 监视"  
[crbug1004203]: https://crbug.com/1004203 "1004203 - 监视"  
[crbug1029031]: https://crbug.com/1029031 "1029031 - UA 过期的字符串 - 监视器" 
[crbug963183]: https://crbug.com/963183 "963183 - DevTools 不符合 WCAG 兼容性"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools 的本地化能力"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D 视图"

[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  

[DwarfHome]: https://dwarfstd.org "Dwarf 主页"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools 的审计审计面板决定 - GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider Addons"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "从 Microsoft Edge 中调试 Microsoft Edge 中的 JavaScript 初Visual Studio |Visual Studio客"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载 Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 调试程序 - 使用比Visual Studio出版"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium\) - Visual Studio Marketplace 的元素"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio 商场"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |Webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint 代码扩展 |Webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "在 Microsoft Edge 博客文章中提进跟踪防护"
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面是在此处找到的，由[here](https://developers.google.com/web/updates/2019/12/devtools/index)[Kayce Basques][KayceBasques] \ (Technical Writer、Chrome DevTools 和 & Lighthouse\) 编写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
