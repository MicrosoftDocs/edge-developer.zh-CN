---
description: 3D 视图、Visual Studio 与 Microsoft Edge 的集成等。
title: DevTools (Microsoft Edge 81) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3081ebb256a9ede637aaaddc3c3cdf7a70a201bb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015473"
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

以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！ 查看它们以尝试 DevTools、Visual Studio 代码扩展等中的新功能。  若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。  

### 对 DevTools 的辅助功能改进  

DevTools 团队已向 Chromium 提供170更改，以解决 DevTools 中的高影响力颜色对比度、键盘和屏幕阅读器问题。  每个构建 web 的开发人员都应该能够使用 DevTools。  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   DevTools 中的 **性能** 工具改进了键盘导航和屏幕阅读器  
:::image-end:::  

希望了解如何让您的网页对所有用户都易于访问？  下载 Microsoft Edge 的 [辅助功能见解][AccessibilityInsights] 和 [webhint][WebhintBrowserExtension] 扩展以开始使用。  

如果您使用屏幕阅读器或键盘在 DevTools 中导航，请通过 [发推至][PostTweetEdgeDevTools] 与我们联系或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标向我们发送您的反馈！  

Chromium 问题 [#963183][CR963183]  

### 使用其他语言的 DevTools  

许多开发人员使用其他开发人员工具，如 StackOverflow 和 Visual Studio 代码，采用其母语，而不仅仅是英语。  我们很高兴宣布 DevTools 的本地化，您现在可以使用英语之外的10种语言中的一种：  

:::row:::
   :::column span="":::
       (简体中文 \ ) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;
   :::column-end:::
   :::column span="":::
      中文 (传统版 \ ) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      法语-fran&#231;ais
   :::column-end:::
   :::column span="":::
      德语-德语
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      意大利语-意大利语
   :::column-end:::
   :::column span="":::
      日语- &#26085;&#26412;&#35486;
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      朝鲜语- &#54620;&#44397;&#50612;
   :::column-end:::
   :::column span="":::
      葡萄牙语-portugu&#234;s
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      俄语–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;
   :::column-end:::
   :::column span="":::
      西班牙语-espa&#241;ol
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

DevTools 将自动匹配您在的 Microsoft Edge 中使用的语言 `edge://settings/languages` 。  

如果你希望 Microsoft Edge 采用一种语言，并且你的 DevTools 保留为英语，请按 `F1` DevTools 打开 " [设置][Settings] "，然后禁用 " **匹配浏览器语言**"。  

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   德语中的 DevTools  
:::image-end:::  

不本地化**控制台**消息。  仅在 DevTools UI 中使用的字符串以用于 Microsoft Edge 的语言显示。  

如果您想要使用的 DevTools 语言与可用的语言不同，请 [tweet][PostTweetEdgeDevTools] ，或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标。  

Chromium 问题 [#941561][CR941561]  

### webhint Microsoft Edge 扩展  

Webhint Microsoft Edge 扩展使你能够轻松地浏览网页并在 DevTools 中获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。  阅读详细信息 [https://webhint.io][Webhint] 。  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   安装 webhint 浏览器扩展时，DevTools 中的 " **提示** " 选项卡  
:::image-end:::  

[在 Microsoft Edge 中尝试 webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。  安装扩展后，打开 DevTools 并选择 "提示" 选项卡。 在此处，运行可自定义的网站扫描。  请转到 [webhint.io][WebhintBrowserExtension] 以了解更多信息。  

### 3D 视图  

通过浏览[文档对象模型 (DOM \ ) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文，使用**3d 视图**调试 web 应用程序。  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/3dview.msft.png":::
   DevTools 中的3D 视图  
:::image-end:::  

若要访问3d 视图，请按 `Ctrl`  +  `Shift`  +  `P` ，在**3d 视图**中键入，然后选择 "**显示3d 视图**"。  

我们正在处理 UI 并向3D 视图添加更多功能，因此请向我们发送 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium 问题 [#987787][CR987787]  

### Visual Studio 代码扩展  

DevTools 团队还发布了一些适用于 [Visual Studio 代码][VisualStudioCode] 的扩展，可让你直接从文本编辑器中使用 DevTools 的强大功能！ 请查看下面的分机：  

#### Microsoft Edge 元素  

通过添加 [Microsoft Edge \ (Chromium \ ) ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual studio 代码扩展中的元素，从 Visual studio 代码中使用元素工具。  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   Visual Studio 代码中使用 Microsoft Edge 扩展的元素的 **元素** 工具  
:::image-end:::  

有关详细信息，请查看 [Microsoft Edge Visual Studio 代码扩展的元素][VisualStudioCodeElementEdgeExtension]。  

#### Microsoft Edge 调试器  

通过 [适用于 Microsoft edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio 代码扩展的调试器，直接从 Visual Studio 代码调试在 Microsoft edge 中运行的 JavaScript。  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   Visual Studio 代码中 Microsoft Edge 扩展的调试器  
:::image-end:::  

有关详细信息，请参阅 [如何从 Visual Studio 代码调试 Microsoft Edge][VisualStudioCodeDebuggerEdgeExtension]。  

#### webhint  

当你编写网页时， [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio 代码扩展使用 `webhint` 它来改进网页！ 此扩展基于分析对工作区文件运行和报告诊断 `webhint` 。  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   `.tsx`在 Visual Studio 代码中分析文件的 Webhint Visual Studio 代码扩展  
:::image-end:::  

[了解有关 Visual Studio 代码 webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。  

### Visual Studio 集成  

在 Visual Studio 2019 版本16.2 或更高版本中，使用 Visual Studio 调试器调试在 Microsoft Edge 中运行的 JavaScript。  [下载 Visual Studio 2019][MicrosoftVisualStudioDownloads] 以试用此功能！  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/vs.msft.png":::
   带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio  
:::image-end:::  

[了解有关从 Visual Studio 调试 Microsoft Edge 的详细信息][MicrosoftVisualStudio]。  

### 跟踪保护控制台消息  

"跟踪防护" 是 Microsoft Edge 中的一项独特功能，可防止您以前未访问过的网站对您进行跟踪。  默认跟踪防护设置为平衡模式，这将阻止第三方跟踪程序和已知恶意跟踪程序，以获取平衡隐私和 web 兼容性的体验。  若要在某些跟踪器被阻止时更深入地了解网页的兼容性，我们还在跟踪器被阻止时在控制台中添加了警告消息。  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   跟踪阻止阻止跟踪对存储的访问权限时的控制台中的消息  
:::image-end:::  

[阅读有关跟踪防护和隐私和 web 兼容性之间的平衡的详细信息][TrackingPrevention]。  

## 来自 Chromium 项目的公告  

以下各节宣布了在 Microsoft Edge 81 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。  

### 设备模式下的 Moto G4 支持  

[启用设备工具栏][DeviceToolbar]后，从**设备**列表中模拟 Moto G4 视区的尺寸。  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/motog4.msft.png":::
   模拟 Moto G4 视区  
:::image-end:::  

单击 " [显示设备帧][DeviceFrame] " 以显示视区周围的 Moto G4 硬件。  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/motog4frame.msft.png":::
   显示 Moto G4 硬件  
:::image-end:::  

相关功能：  

*   [Command Menu][CommandMenu] `Capture screenshot` 在启用 "**显示设备框架**") 之后，打开命令菜单并运行命令以获取包含 Moto G4 (硬件的视区的屏幕截图。  
*   [调节网络和 CPU][ThrottleNetworkAndCpu] 以更准确地模拟移动用户的 web 浏览条件。  

Chromium 问题 [#924693][CR924693]  

### 与 Cookie 相关的更新  

#### Cookie 窗格中阻止的 cookie  

"应用程序" 面板中的 "Cookie" 窗格现在显示黄色背景的被阻止的 cookie。  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   在 "应用程序" 面板的 "Cookie" 窗格中阻止的 cookie  
:::image-end:::  

Chromium 问题 [#1030258][CR1030258]  <!-- inaccessible  -->  

#### Cookie 窗格中的 cookie 优先级  

网络和应用程序面板中的 Cookie 表现在包含 " **优先级** " 列。  

> [!CAUTION]
> 基于 Chromium 的浏览器（如 Microsoft Edge）是唯一支持 cookie 优先级的浏览器。  

Chromium 问题 [#1026879][CR1026879]  

#### 编辑所有 cookie 值  

现在，Cookie 表中的所有单元格都是可编辑的，但 **Size** 列中的单元格，因为该列表示该 Cookie 的网络大小（以字节为单位）。  有关每个列的说明，请参阅 [字段][CookiesFields] 。  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/editcookie.msft.png":::
   编辑 cookie 值  
:::image-end:::  

#### 复制为 Node.js 提取以包括 cookie 数据  

右键单击网络请求并选择 "**复制**  >  **副本" Node.js** "获取" 以获取 `fetch` 包含 cookie 数据的表达式。  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   复制为 Node.js 提取  
:::image-end:::  

Chromium 问题 [#1029826][CR1029826]  

### 更准确的 web 应用清单图标  

以前，应用程序面板中的清单窗格发送了其自己的请求，以便显示 web 应用清单图标。  DevTools 现在显示 Microsoft Edge 使用的完全相同的清单图标。  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/manifesticons.msft.png":::
   清单窗格中的图标  
:::image-end:::  

Chromium 问题 [#985402][CR985402]  

### 将鼠标悬停在 CSS 内容属性上以查看非转义值  

将鼠标悬停在某个属性的值上 `content` 以查看该值的非转义版本。  

例如，在此 [演示][CSSContentDemo] 中，当你检查 `p::after` 伪元素时，在 "样式" 窗格中看到转义的字符串：  

:::image type="complex" source="../../images/2020/01/escapedstring.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/escapedstring.msft.png":::
   转义字符串  
:::image-end:::  

将鼠标悬停在值上时 `content` ，将看到非转义值：  

:::image type="complex" source="../../images/2020/01/unescapedstring.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/unescapedstring.msft.png":::
   非转义值  
:::image-end:::  

### 控制台中的更多详细源地图错误  

该控制台现在提供了有关为何无法加载或分析源映射的详细信息。  以前它只是在未解释出错的情况下提供了错误。  

:::image type="complex" source="../../images/2020/01/sourcemap.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/sourcemap.msft.png":::
   控制台中的源映射加载错误  
:::image-end:::  

### 用于禁用超过文件末尾的滚动的设置  

打开 "[设置][Settings]"，然后禁用**首选项**  >  **源**  >  **允许滚动浏览文件末尾**，以禁用在 "**源**" 面板中滚动浏览文件末尾更好的默认 UI 行为。  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/settings.msft.png":::
   在 "设置" 中禁用 " **允许滚动超过文件结尾** "  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   现在，在 "源" 面板中已禁用滚动超过文件末尾的功能  
:::image-end:::  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DeviceToolbar]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动区-在 Microsoft Edge DevTools 中使用设备模式模拟移动设备 |Microsoft 文档"
[DeviceFrame]: /microsoft-edge/devtools-guide-chromium/device-mode/index#show-device-frame "显示设备框架-在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 |Microsoft 文档"
[CommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[ThrottleNetworkAndCpu]: /microsoft-edge/devtools-guide-chromium/device-mode/index#throttle-the-network-and-cpu "通过 Microsoft Edge DevTools 中的设备模式对网络和 CPU 进行限制-模拟移动设备 |Microsoft 文档"
[Settings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"
[MicrosoftVisualStudio]: /microsoft-edge/visual-studio/index "Visual Studio |Microsoft 文档"  
[CookiesFields]: /microsoft-edge/devtools-guide-chromium/storage/cookies#fields "字段-查看、编辑和删除 Microsoft Edge DevTools 的 cookie |Microsoft 文档"  

[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio 代码扩展的调试器"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio 代码扩展的元素"  

[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://aka.ms/vscode "Visual Studio 代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 的调试器-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (的元素 \ ) Chromium \-Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"

[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进 Microsoft Edge 博客文章中的跟踪保护"

[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge 预览体验计划 Addons"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载适用于 Windows & Mac 的 Visual Studio 2019"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  

[CR924693]: https://crbug.com/924693 "功能请求：将 Moto G4 添加到设备模式列表 |Chromium Bug"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |Chromium Bug"  
[CR1026879]: https://crbug.com/1026879 "开发人员控制台中的 "Cookie" 选项卡不再显示优先级 |Chromium Bug"  
[CR1029826]: https://crbug.com/1029826 ""网络" 选项卡-> 右键单击以请求-> 复制 > 复制为 "获取" 不复制 cookie |Chromium Bug"  
[CR985402]: https://crbug.com/985402 "web 应用清单图标错误字符串很混乱 |Chromium Bug"  
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG 标准 |Chromium Bug"  
[CR941561]: https://crbug.com/941561 "DevTools | 的本地化Chromium Bug"  
[CR987787]: https://crbug.com/987787 "Dom 3D 视图 |Chromium Bug"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "非转义 CSS 内容的演示"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  

[TheWebWeWant]: https://aka.ms/webwewant "我们需要的网站"  
[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"  

[Webhint]: https://aka.ms/webhint "webhint"  

[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio 代码扩展 |webhint 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/updates/2020/01/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  