---
title: 'Microsoft Edge 81 实开发人员 (工具中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8e9e6885d04c7ad15a688b51cee4c16440d3ca1e
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942093"
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

# DevTools （Microsoft Edge 81）中的新增功能  

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
| Chinese (Simplified) - 中文(简体)（简体）| Chinese (Traditional) - 中文(繁體)（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

DevTools 将自动匹配 Microsoft Edge 的语言 `edge://settings/languages` 。  

如果你希望 Microsoft Edge 使用一种语言，而你的 DevTools 仍使用英语，请按 `F1` DevTools 打开"设置 ["][Settings] 并禁用 **匹配浏览器语言**。  

> ##### 图 2  
> 常规工具  
> ![常规工具][ImageLocalizedGerman]  

**主机消息** 未进行本地化。  在 DevTools UI 中使用的字符串仅以用于 Microsoft Edge 的语言显示。  

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

若要访问 3D 视图，在 `Ctrl`  +  `Shift`  +  `P` 3D 视图中**键入内容，** 然后选择"**显示 3D 视图**"。  

我们正在处理 UI 并向 3D 视图添加更多功能，因此请向我们发送你的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium [问题#987787][crbug987787]  

### Visual Studio代码扩展  

DevTools 团队还发布了 [用于 Visual Studio Code \ (VS Code\) ][VisualStudioCode] 的一些扩展，它允许你直接从文本编辑器使用 DevTools 的功能！ 请参阅以下扩展项：  

#### Microsoft Edge 的元素  

通过将 [Microsoft Edge \ (m Chromium\) 按钮扩展添加到的元素，从 VS ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] 代码内使用元素工具。  

> ##### 图 5  
> VS 代码中的元素工具，使用适用于 Microsoft Edge 扩展的 ![ VS 代码中的元素扩展"元素"工具][ImageElementsVisualStudioCode]  

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

[了解有关如何从中调试 Microsoft Edge 表Visual Studio。][MicrosoftVisualStudio]  

### 跟踪防护主机消息  

跟踪防护是 Microsoft Edge 中唯一的功能，可防止你被之前尚未访问过的网站进行跟踪。  默认跟踪防护设置是"平衡模式"，为了使体验保持平衡隐私和 Web 兼容性的体验，这将对第三方跟踪程序和已知的义务跟踪器进行保护。  为了在特定跟踪器被阻止时，为更深入地了解网页的兼容性，我们还在跟踪器被阻止时在主机中添加了警告邮件。  

> ##### 图 9  
> 跟踪防护阻止对跟踪器的存储的访问时主机中的消息  
> ![跟踪防护阻止对跟踪器的存储的访问时主机中的消息][ImageTrackingPrevention]  

[了解有关跟踪防护和在隐私和 Web 之间余额之间余额的详细信息][TrackingPrevention]。  

## 来自 Chromium 项目的公告  

以下部分公布给开源 Chromium 项目的 Microsoft Edge 81 中可用的其他功能。  

### 设备模式下支持  

[启用设备工具栏后][DeviceToolbar]，请从"设备"列表中模拟马达 G4 视区**的**大小。  

> ##### 图 10  
> 模拟 Moto G4 视区  
> ![模拟 Moto G4 视区][ImageMotoG4]  

单击 ["显示设备][DeviceFrame] 框架"以在视区的 Moto G4 硬件中显示 Moto G4 硬件。  

> ##### 图 11  
> 显示 Moto G4 硬件  
> ![显示 Moto G4 硬件][ImageMotoG4Frame]  

相关功能：  

*   打开 ["命令"][CommandMenu] 菜单并 `Capture screenshot` 运行命令以获取视区的屏幕截图，该视区包括 Moto G4 (在启用 **"显示**) 。  
*   [将网络和 CPU 恢复][ThrottleNetworkAndCpu] 为更准确地模拟移动用户的 Web 浏览条件。  

Chromium [问题#924693][crbug924693]  

### Cookie 相关的更新  

#### 在 Cookie 窗格中阻止 Cookie  

应用程序面板中的 Cookie 窗格现在显示了带有黄色背景的 Cookie。  

> ##### 图 12  
> 在应用程序面板的 Cookie 窗格中阻止 Cookie  
> ![在应用程序面板的 Cookie 窗格中阻止 Cookie][ImageBlockedCookies]  

Chromium [问题#1030258][crbug|::ref1::|]  

#### Cookie 窗格中的 Cookie 优先级  

网络和应用程序面板中的 Cookie 表现包含" **优先级"** 列。  

> [!CAUTION]
> 基于 Chromium 的浏览器（如 Microsoft Edge）是唯一支持 Cookie 优先级的浏览器。  

Chromium [#1026879][crbug1026879]  

#### 编辑所有 Cookie 值  

Cookie 表中的所有单元格现在都可编辑，"大小 **"列中的** 单元格除外，因为该列表示 Cookie 的网络大小（字节）。  请参阅 [字段][CookiesFields] ，获取每列的说明。  

> ##### 图 13  
> 编辑 Cookie 值  
> ![编辑 Cookie 值][ImageEditCookie]  

#### 以网站Node.js复制以包括 Cookie 数据  

右键单击网络请求并选择**Copy**  >  **"复制副本"作为 Node.js提**，以获取 `fetch` 包括 Cookie 数据的表达式。  

> ##### 图 14  
> 以提Node.js复制  
> ![以提Node.js复制][ImageCopyFetch]  

Chromium [问题#1029826][crbug1029826]  

### 更多准确的 Web 应用清单图标  

以前，应用程序面板中的清单窗格为了显示 Web 应用清单图标而发送了自己的请求。  开发工具现在显示 Microsoft Edge 使用的确实清单图标。  

> ##### 图 15  
> 清单窗格中的图标  
> ![清单窗格中的图标][ImageManifestIcon]  

Chromium [问题#985402][crbug985402]  

### 将鼠标指悬停在 CSS 内容属性上可查看未捕获的值  

将鼠标悬停在 `content` 属性值上以查看未被接受的值版本。  

例如，当你 [检查][CSSContentDemo] `p::after` pseudo-element 时，可以在"样式"窗格中看到转义字符串：  

> ##### 图 16  
> 已转换的字符串  
> ![已转换的字符串][ImageEscapedString]  

将鼠标悬停 `content` 在您看到一个未使用的值上时：  

> ##### 图 17  
> 未入的值  
> ![未入的值][ImageUnescapedString]  

### 在主机中更详细的源映射错误  

该控制台现在提供了有关源映射加载或分析失败的原因的更多详细信息。  之前，它只提供了一个错误但不解解问题出现的问题。  

> ##### 图 18  
> 主机中的源映射加载错误  
> ![主机中的源映射加载错误][ImageSourcemapError]  

### 用于禁用滚动的设置，将趋移文件末尾  

打开["设置][Settings]**"，然后禁用**  >  **"首**  >  **选项源"，允许以前结**束文件的一项时间，禁止你在源面板中很好地**滚**动文件的末尾。  

> ##### 图 19  
> 禁用"设置"**中文件的"允许滚动即将结束"**  
> ![禁用"允许滚动"文件的终止][ImageSettings]  

> ##### 图 20  
> 源面板中现已禁用通过文件的末尾滚动  
> ![源面板中现已禁用通过文件的末尾滚动][ImageScroll]  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- <<../../_shared/devtools-feedback.md>>  

<<../../_shared/canary.md>>  

<<../../_shared/discover.md>> -->  

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2020/01/a11y-performance-tool.msft.gif "图 1：DevTools 中的性能工具，可通过键盘导航和屏幕阅读器改进"  
[ImageLocalizedGerman]: ../../images/2020/01/localized-devtools.msft.png "图 2：常规工作区中的 DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2020/01/webhint-browser-extension.msft.png "图 3：安装 Web hint 浏览器扩展时 Microsoft Edge DevTools 中的"提示"选项卡"  
[Image3DView]: ../../images/2020/01/3dview.msft.png "图 4：Microsoft Edge 开发工具中的 3D 视图"  
[ImageElementsVisualStudioCode]: ../../images/2020/01/elements-for-edge.msft.png "图 5：使用 Microsoft Edge 扩展的元素 ，VS 代码中的元素工具"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2020/01/vscode-debugger.msft.png "图 6：使用 VS 代码的 Microsoft Edge 扩展的调试程序"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2020/01/webhint-vscode-extension.msft.png "图 7：Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件"  
[ImageVisualStudioLaunchWebApp]: ../../images/2020/01/vs.msft.png "图 8：Visual Studio并通过在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用的选项"  
[ImageTrackingPrevention]: ../../images/2020/01/tracking-prevention.msft.png "图 9：跟踪阻止对跟踪器的存储的访问权限时，主机中的邮件" 
[ImageMotoG4]: ../../images/2020/01/motog4.msft.png "图 10：模拟 Moto G4 视区" 
[ImageMotoG4Frame]: ../../images/2020/01/motog4frame.msft.png "图 11：显示 Moto G4 硬件" 
[ImageBlockedCookies]: ../../images/2020/01/blockedcookies.msft.png "图 12：在应用程序面板的 Cookie 窗格中阻止 Cookie"
[ImageEditCookie]: ../../images/2020/01/editcookie.msft.png "图 13：编辑 Cookie 值"
[ImageCopyFetch]: ../../images/2020/01/fetchcookies.msft.png "图 14：作为提Node.js复制"
[ImageManifestIcon]: ../../images/2020/01/manifesticons.msft.png "图 15：清单窗格中的图标"
[ImageEscapedString]: ../../images/2020/01/escapedstring.msft.png "图 16：转码的字符串"
[ImageUnescapedString]: ../../images/2020/01/unescapedstring.msft.png "图 17：未转动的值"
[ImageSourcemapError]: ../../images/2020/01/sourcemap.msft.png "图 18：主机中的源映射加载错误"
[ImageSettings]: ../../images/2020/01/settings.msft.png "图 19：禁用"设置"中文件的过时端文件"
[ImageScroll]: ../../images/2020/01/scrollingsources.msft.png "图 20：源面板中现已禁用通过文件末尾滚动"

<!-- links -->  

[DeviceToolbar]: ../../../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中使用设备模式模拟移动视区"
[DeviceFrame]: ../../../device-mode/index.md#show-device-frame "选择"显示设备框架"以显示视区中物理设备框架。"
[CommandMenu]: ../../../command-menu/index.md "使用 Microsoft Edge 开发人员工具命令菜单运行命令"  
[ThrottleNetworkAndCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "将网络和 CPU 固定到更准确地模拟移动用户的 Web 浏览条件。"
[crbug924693]: https://crbug.com/924693 "924693：功能请求：将 Moto G4 添加到设备模式列表"
[crbug1030258]: https://crbug.com/1030258 "1030258"
[crbug1026879]: https://crbug.com/1026879 "1026879：开发者主机中的"Cookie"选项卡不如此优先级显示优先级"
[CookiesFields]: ../../../storage/cookies.md#fields "Cookie 表中的字段"
[crbug1029826]: https://crbug.com/1029826 "1029826：网络选项卡 -> 右键单击可请求 ->复制 -> 副本作为提取值，无需复制 Cookie"
[crbug985402]: https://crbug.com/985402 "985402：Web 应用清单图标错误字符串比较为复选"
[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "未转接的 CSS 内容的演示"
[Settings]: ../../../customize/index.md#settings "使用"设置"自定义 Microsoft Edge 开发工具"
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge 的调试程序"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge 元素与代码扩展"  
[crbug963183]: https://crbug.com/963183 "963183 - DevTools 不符合 WCAG 兼容性"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools 的本地化能力"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D 视图"
[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider Addons"  
[MicrosoftVisualStudio]: ../../../../visual-studio/index.md "Visual Studio"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载 Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 调试程序 - 使用比Visual Studio出版"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium\) - Visual Studio Marketplace 的元素"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio 商场"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |Webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint 代码扩展 |Webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "在 Microsoft Edge 博客文章中提进跟踪防护"

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面是在此处找到的，由[here](https://developers.google.com/web/updates/2020/01/devtools/index)[Kayce Basques][KayceBasques] \ (Technical Writer、Chrome DevTools 和 & Lighthouse\) 编写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  