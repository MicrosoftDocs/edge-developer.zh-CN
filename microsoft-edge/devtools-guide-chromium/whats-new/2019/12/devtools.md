---
description: 辅助功能改进，使用其他语言的 DevTools 等。
title: DevTools (Microsoft Edge 80) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8f82f46cd683433a37614bcf15745e1de9f31ffb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015466"
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

# DevTools (Microsoft Edge 80) 中的新增功能  

## 来自 Microsoft Edge 开发人员工具团队公告  

以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！ 查看它们以尝试 DevTools、Visual Studio 代码扩展等中的新功能。  若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。  

### 对 DevTools 的辅助功能改进  

DevTools 团队已向 Chromium 提供170更改，以解决 DevTools 中的高影响力颜色对比度、键盘和屏幕阅读器问题。  每个构建 web 的开发人员都应该能够使用 DevTools。  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   DevTools 中的 **性能** 工具改进了键盘导航和屏幕阅读器  
:::image-end:::  

希望了解如何让您的网页对所有用户都易于访问？  下载 Microsoft Edge 的 [辅助功能见解][AccessibilityInsights] 和 [webhint][WebhintBrowserExtension] 扩展以开始使用。  

如果您使用屏幕阅读器或键盘在 DevTools 中导航，请 [发推至][PostTweetEdgeDevTools] "发送反馈" 或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标！  

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
| Chinese (Simplified) - 中文（简体）| Chinese (Traditional) - 中文（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

导航到 `edge://flags` "启用已 **本地化的开发人员工具** " 标志并将其设置为 " **启用**"。  还将 " **开发工具" 试验** 标志设置为 " **启用**"。  重启 Microsoft Edge 并打开 DevTools。  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  DevTools 与你用于 Microsoft Edge 的语言相匹配 `edge://settings/languages` 。  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   德语中的 DevTools  
:::image-end:::  

如果您想要使用的 DevTools 语言与可用的语言不同，请 [tweet][PostTweetEdgeDevTools] ，或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标。  

Chromium 问题 [#941561][CR941561]  

### webhint Microsoft Edge 扩展  

Webhint Microsoft Edge 扩展使你能够轻松地浏览网页并在 DevTools 中获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。  阅读详细信息 [https://webhint.io][Webhint] 。  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   安装 webhint 浏览器扩展时，DevTools 中的 " **提示** " 选项卡  
:::image-end:::  

[在 Microsoft Edge 中尝试 webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。  安装扩展后，打开 DevTools 并选择 "提示" 选项卡。 在此处，运行可自定义的网站扫描。  请转到 [webhint.io][WebhintBrowserExtension] 以了解更多信息。

### 3D 视图  

通过浏览[文档对象模型 (DOM \ ) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文，使用**3d 视图**调试 web 应用程序。  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/3dview.msft.png":::
   DevTools 中的**3D 视图**  
:::image-end:::  

若要访问3D 视图，请导航到 `edge://flags` 并确保 " **开发人员工具实验** " 标志设置为 " **已启用**"。  重启 Microsoft Edge 并打开 DevTools。  按 `F1` DevTools 或转到 " **设置**"，导航到 " **实验** " 部分，然后选中 " **启用3d 视图** " 复选框。  现在，请按 `Ctrl`  +  `Shift`  +  `P` ，在**3d 视图**中键入，然后选择 "**显示3d 视图**"。  

我们正在处理 UI 并向3D 视图添加更多功能，请向我们发送您的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team)。  

Chromium 问题 [#987787][CR987787]

### Visual Studio 代码扩展  

DevTools 团队还发布了一些适用于 [Visual Studio 代码][VisualStudioCode] 的扩展，可让你直接从文本编辑器使用 DevTools 的强大功能。 查看以下扩展。  

#### Microsoft Edge 元素  

通过添加 [Microsoft Edge (Chromium) ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual studio 代码扩展中的元素，从 Visual studio 代码中使用元素工具。  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   Visual Studio 代码中使用 Microsoft Edge 扩展的元素的 **元素** 工具  
:::image-end:::  

有关详细信息，请查看 [Microsoft Edge Visual Studio 代码扩展的元素][VisualStudioCodeElementEdgeExtension]。  

#### Microsoft Edge 调试器  

通过 [适用于 Microsoft edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio 代码扩展的调试器，直接从 Visual Studio 代码调试在 Microsoft edge 中运行的 JavaScript。  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   Visual Studio 代码中 Microsoft Edge 扩展的调试器  
:::image-end:::  

有关详细信息，请参阅 [如何从 Visual Studio 代码调试 Microsoft Edge][VisualStudioCodeDebuggerEdgeExtension]。  

#### webhint  

当你编写网页时， [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio 代码扩展使用 `webhint` 它来改进网页！ 此扩展基于分析对工作区文件运行和报告诊断 `webhint` 。  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   `.tsx`在 Visual Studio 代码中分析文件的 Webhint Visual Studio 代码扩展  
:::image-end:::  

[了解有关 Visual Studio 代码 webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。  

### Visual Studio 集成
在 Visual Studio 2019 版本16.2 或更高版本中，使用 Visual Studio 调试器调试在 Microsoft Edge 中运行的 JavaScript。  [下载 Visual Studio 2019][MicrosoftVisualStudioDownloads] 以试用此功能！  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/vs.msft.png":::
   带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio  
:::image-end:::  

[阅读我们的博客文章，了解如何从 Visual Studio 调试 Microsoft Edge][MicrosoftVisualStudioBlogDebugJavascript]。  

### 跟踪保护控制台消息  

"跟踪防护" 是 Microsoft Edge 中的一项独特功能，可防止您以前未访问过的网站对您进行跟踪。  默认跟踪防护设置为平衡模式，这将阻止第三方跟踪程序和已知恶意跟踪程序，以获取平衡隐私和 web 兼容性的体验。  若要在某些跟踪器被阻止时更深入地了解网页的兼容性，我们还在跟踪器被阻止时在控制台中添加了警告消息。  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   跟踪阻止阻止跟踪对存储的访问权限时的 **控制台** 中的消息  
:::image-end:::  

[阅读有关跟踪防护和隐私和 web 兼容性之间的平衡的详细信息][TrackingPrevention]。  

## 来自 Chromium 项目的公告  

以下各节宣布了在 Microsoft Edge 80 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。  

### 在控制台中支持 let 和 class redeclarations  

现在，该 **控制台** 支持 redeclarations `let` 和 `class` 语句。  如果 web 开发人员使用控制台体验新的 JavaScript 代码，则无法重新声明。  

> [!WARNING]
> `let` `class` 在控制台外或单个控制台输入中的脚本中 Redeclaring 或语句仍会导致 a `SyntaxError` 。  

例如，以前，当重新声明本地变量时 `let` ，控制台引发错误：  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/letbefore.msft.png":::
   Microsoft Edge 79 中的 **控制台** ，显示 "允许重新声明" 失败  
:::image-end:::  

现在，该控制台允许重新声明：  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/letafter.msft.png":::
   Microsoft Edge 80 中的 **控制台** ，显示 "允许重新声明" 成功  
:::image-end:::  

Chromium 问题 [#1004193][CR1004193]  

### 改进的 WebAssembly 调试  

DevTools 已开始支持 [DWARF 调试标准][DwarfHome]，这意味着增加了对代码执行的支持、设置断点以及解析 DevTools 中的源语言的堆栈跟踪。  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### 网络面板更新  

#### 在 "启动器" 选项卡中请求启动器链  

现在，你可以查看作为嵌套列表的网络请求的发起方和依赖关系。  这可能会帮助你了解请求资源的原因或特定资源的哪些网络活动 (如脚本 \ ) 导致的。  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/initiators.msft.png":::
   " **启动器** " 选项卡中的请求发起人链  
:::image-end:::  

[在 "网络" 面板中记录网络活动][DevToolsNetworkIndex]后，单击资源，然后转到 "**启动器**" 选项卡以查看**请求启动器链**：  

*   已 **检查的资源** 为粗体。  在上面的屏幕截图中， `ai.2.min.js` 是已检查的资源。  
*   已检查资源上方的资源是 **启动器**。  在上面的屏幕截图中， `https://www.microsoftedgeinsider.com` 是的发起人 `ai.2.min.js` 。  换句话说， `https://www.microsoftedgeinsider.com` 导致网络请求 `ai.2.min.js` 。  
*   已检查资源下方的资源是 **依赖关系**。  在上面的屏幕截图中， `https://dc.services.visualstudio.com/v2/track` 是的依赖项 `ai.2.min.js` 。  换句话说， `ai.2.min.js` 导致网络请求 `https://dc.services.visualstudio.com/v2/track` 。  

> [!NOTE]
> 也可以通过按住 `Shift` 网络资源并将鼠标悬停在网络资源上来访问启动器和相关性信息。  请参阅 [查看发起人和依赖关系][DevToolsNetworkReferenceViewInitiatorsDependencies]。  

Chromium 问题 [#842488][CR842488]  

#### 在概述中突出显示所选的网络请求  

单击网络资源以对其进行检查后，网络面板 **现在将在**该资源周围放置一个蓝色边框。  这可以帮助你检测网络请求在之前或之后是否比预期发生。  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/overview.msft.png":::
   突出显示已检查资源的 **概述** 窗格  
:::image-end:::  

Chromium 问题 [#988253][CR988253]  

#### "网络" 面板中的 URL 和路径列  

使用 "**网络**" 面板中的 "新**路径**" 和 " **URL** " 列查看每个网络资源的绝对路径或完整 url。  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/columns.msft.png":::
   " **网络** " 面板中的新路径和 URL 列  
:::image-end:::  

右键单击 **瀑布** 表标题，然后选择 " **路径** " 或 " **URL** " 以显示新列。  

Chromium 问题 [#993366][CR993366]  

#### 已更新的用户代理字符串  

DevTools 支持通过 " **网络条件** " 选项卡设置自定义用户代理字符串。 用户代理字符串会影响 `User-Agent` 附加到网络资源的 HTTP 标头以及的值 `navigator.userAgent` 。  

预定义的用户代理字符串已更新，以反映新式浏览器版本。  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/useragent.msft.png":::
   " **网络条件** " 选项卡中的 "用户代理" 菜单  
:::image-end:::  

若要访问 **网络条件**，请 [打开命令菜单][DevToolsCommandMenuIndex] 并运行 `Show Network Conditions` 命令。  

> [!NOTE]
> 您也可以 [在设备模式下设置用户代理的字符串][DevToolsDeviceModeIndex]。  

Chromium 问题 [#1029031][CR1029031]  

### "审核" 面板更新  

#### 新的配置 UI  

配置 UI 具有新的响应式设计，并且限制配置选项已简化。  有关限制 UI 更改的详细信息，请参阅 [审核面板限制][GitHubGoogleChromeDevToolsAuditsPanelThrottling] 。  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/start.msft.png":::
   新的配置 UI  
:::image-end:::  

### 覆盖范围选项卡更新  

#### 每个函数或每块覆盖率模式  

" [覆盖范围" 选项卡][DevToolsCoverageIndex] 具有新的下拉菜单，可让你指定是否应 **按每个函数** 或 **每个块**收集代码覆盖率数据。  **每个块** 覆盖率更详细，但更昂贵的收集方式。  默认情况下，DevTools 使用 **每个函数** 覆盖率。  

> [!CAUTION]
> 你可能会看到 HTML 文件中的较大代码覆盖率有差异，具体取决于 **每个函数** 还是 **每块** 模式使用。  使用 **每个函数** 模式时，HTML 文件中的内联脚本将被视为函数。  如果脚本全部运行，则 DevTools 将整个脚本标记为使用的代码。  仅当脚本根本不运行时，DevTools 将脚本标记为未使用的代码。  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/modes.msft.png":::
   "覆盖模式" 下拉菜单  
:::image-end:::  

#### 覆盖范围现在必须由页面重装启动  

由于覆盖率数据不可靠，因此在没有页面重新加载的情况下切换代码覆盖率已被删除。  例如，如果运行时以前很长一段时间，并且 V8 垃圾回收器已清理过它，则可能会将函数报告为未使用。  

Chromium 问题 [#1004203][CR1004203]  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

<!--[../../images/2019/12/wasm.msft.png]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevToolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码。Microsoft 文档"  
[DevToolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动区-在 Microsoft Edge DevTools 中使用设备模式模拟移动设备 |Microsoft 文档"  
[DevToolsNetworkIndex]: /microsoft-edge/devtools-guide-chromium/network/index "检查 Microsoft Edge DevTools 中的网络活动 |Microsoft 文档"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#view-initiators-and-dependencies "查看启动器和相关性-网络分析参考 |Microsoft 文档"  
[DevGuideEdgeHtmlWhatsNew]: /microsoft-edge/dev-guide/whats-new "EdgeHTML | 中的新增功能 |Microsoft 文档"  
[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio 代码扩展的调试器 |Microsoft 文档"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio 代码扩展的元素 |Microsoft 文档"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "将启动器字段添加到 "页眉" 选项卡 |Chromium Bug"  
[CR988253]: https://crbug.com/988253 "Bug DevTools-网络请求与时间线图之间没有关联 |Chromium Bug"  
[CR993366]: https://crbug.com/993366 "请在网络面板请求列表 | 中显示 URL 的路径部分Chromium Bug"  
[CR1004193]: https://crbug.com/1004193 "V8 | 的复制模式Chromium Bug"  
[CR1004203]: https://crbug.com/1004203 "使代码覆盖率非常有意义 |Chromium Bug"  
[CR1029031]: https://crbug.com/1029031 "UA 字符串即将过时 |Chromium Bug" 
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG 标准 |Chromium Bug"
[CR941561]: https://crbug.com/941561 "DevTools | 的本地化Chromium Bug"
[CR987787]: https://crbug.com/987787 "Dom 3D 视图 |Chromium Bug"

[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  

[DwarfHome]: https://dwarfstd.org "Dwarf 主页"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools ' 审核面板限制-GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge 预览体验计划 Addons"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "从 Visual Studio 中的 Microsoft Edge 调试 JavaScript |Visual Studio 博客"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载适用于 Windows 的 Visual Studio 2019 & Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio 代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 的调试器-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (的元素 \ ) Chromium \-Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio 代码扩展 |webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进 Microsoft Edge 博客文章中的跟踪保护"
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/updates/2019/12/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
