---
description: CSS 网格调试功能、使用网络控制台编辑和重播请求等。
title: 'DevTools (Microsoft Edge 85) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 5bd013fae617e9759aa91949acccf936d85f7160
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514359"
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
# <a name="whats-new-in-devtools-microsoft-edge-85"></a>DevTools 85 (Microsoft Edge中的新增)   

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>来自 Microsoft Edge 开发人员工具团队公告  

以下各节列出了你可能从 DevTools 团队中错过Microsoft Edge通知。  请查看公告以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。  若要随时了解开发人员工具中所有最新且最最好的功能，请下载[Microsoft Edge 预览][MicrosoftEdgePreviewChannels]频道，并按照 Twitter 上的[Microsoft Edge DevTools 团队。][EdgeDevToolsTwitterAccount]  

### <a name="css-grid-debugging-features"></a>CSS 网格调试功能  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

开发人员Microsoft Edge团队正在与 Chrome DevTools 团队和 Chromium 社区协作，以将新的 CSS 网格调试功能添加到 DevTools。  现在，你可以将网格线号、网格间隔和扩展网格线显示为页面上覆盖。  此外，网格工具的更多改进即将推出。  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   CSS 网格调试功能
:::image-end:::  

> [!NOTE]
> 若要启用实验，请导航到" [打开实验][DevtoolsExperimentalFeaturesTurnOn] 功能"，然后选中"启用新的 CSS 网格调试功能 **"旁边的复选框**。  
> 
> 若要使用示例试用实验，请导航到 [CSS 网格规划器示例][CodepenRachelweilYzwBzKM]。  

Chromium问题[#1047356][CR1047356]  

### <a name="edit-and-replay-requests-with-the-network-console"></a>使用网络控制台编辑和重播请求  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

你现在可以使用网络控制台**在**网络日志中对请求使用[编辑和][DevtoolsNetworkIndexLogActivity]**重播**。  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="使用网络控制台在 NetworkLog 中编辑和重播请求" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   使用网络控制台在 [NetworkLog][DevtoolsNetworkIndexLogActivity] 中编辑和 **重播请求**  
:::image-end:::  

网络控制台是一个新 **面板，它将** 在 [DevTools"][DevtoolsCustomizeIndexDrawer] 箱"中打开，并自动填充 HTTP 请求的信息。  若要显示从服务器返回的响应，请编辑请求 \ (\) 并选择"发送 **"。**  

您还可以使用网络 **控制台** 直接从 DevTools 创建和发送 HTTP 请求。  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="网络控制台面板" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   网络 **控制台** 面板  
:::image-end:::  

> [!TIP]
> 若要在 **主 \ (** top\) 面板（而不是 [DevTools 箱][DevtoolsCustomizeIndexDrawer]）中显示网络控制台，请导航到在面板 [之间移动工具](#move-tools-between-panels)。  

> [!NOTE]
> 若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOn] 功能，然后选择启用网络 **控制台旁边的复选框**。  
> 
> 打开网络 [日志][DevtoolsNetworkIndexLogActivity]，打开上下文菜单 \ (右键单击\) ，然后选择编辑 **和重播**。  

Chromium问题[#1093687][CR1093687]  

### <a name="service-worker-respondwith-events-in-the-timing-tab"></a>服务工作者 respondWith"计时"选项卡中的事件  

网络 **工具** 的" **计时"** 选项卡现在包括 `respondWith` 服务工作器事件。  服务工作线程事件显示从服务工作进程事件处理程序开始运行前一段时间到处理程序承诺得到实现的时间 `respondWith` `fetch` `respondWith` `fetch` 的持续时间。  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text=""网络"面板的"计时"选项卡中的 respondWith 服务工作线程事件" lightbox="../../media/2020/06/timing-tab.msft.png":::
   网络 `respondWith` 工具的" **计时"** 选项卡中的服务 **工作器** 事件  
:::image-end:::  

展开 **收到的响应** 以显示来自响应的其他信息， `fetch` 如 `CacheStorageCacheName` 、 `serviceWorkerResponseSource` 和 `ResponseTime` 。  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="展开收到的响应以显示提取响应中的附加信息" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   展开 **收到的响应** 以显示来自响应的其他 `fetch` 信息  
:::image-end:::  

Chromium问题[#1066579][CR1066579]  

### <a name="webhint-feedback-in-the-issues-panel"></a>问题面板中的 webhint 反馈  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

[webhint][WebhintMain] 是一个开放源代码工具，提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWA 和其他常见 Web 开发问题实时反馈。  查看"问题"面板中的 [webhint][DevtoolsIssues] 反馈。  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   问题面板中的 webhint 反馈  
:::image-end:::  

> [!NOTE]
> 若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOn] 功能，然后选择启用 **Webhint 旁边的复选框**。  
> 
> 打开" [问题][DevtoolsIssues] "面板以显示来自 Webhint 的反馈。  

Chromium问题[#1070378][CR1070378]  

### <a name="move-tools-between-panels"></a>在面板之间移动工具  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   试验功能  
:::image-end:::  

通常，元素和网络等工具**** 只能在**** DevTools 的主 \ (\) 面板中打开。  同样，诸如**3D 视图**和**** 问题等工具可能只能在 DevTools (底部\) 面板中打开。  现在，你能够通过在顶部和底部面板之间移动工具来自定义 DevTools 布局。  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="在面板之间移动工具" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   在面板之间移动工具  
:::image-end:::  

> [!NOTE]
> 若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOn] 功能，然后选择启用支持以在面板之间 **移动选项卡旁边的复选框**。  

Chromium问题[#897944][CR897944]  

### <a name="improved-initiator-tooltip-in-the-network-panel"></a>网络面板中改进的发起人工具提示  

在 Microsoft Edge 83 和 84 中，"发起者"列的工具提示显示在使用水平滚动条显示的"网络日志[][DevtoolsNetworkIndexLogActivity]"中，显示资源请求的原因。  你仅能够在工具提示中水平滚动来显示发起请求的调用堆栈。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="84 中的发起Microsoft Edge提示" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   84 中的发起Microsoft Edge提示  
:::image-end:::  

从 Microsoft Edge 85 开始，现在可以在工具提示中显示 Initiator 调用堆栈，而无需水平滚动。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="85 中的发起Microsoft Edge提示" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   85 中的发起Microsoft Edge提示
:::image-end:::  

Chromium问题[#1069404][CR1069404]  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

以下各节宣布 85 Microsoft Edge开放源代码管理项目中提供的其他Chromium功能。  

### <a name="style-editing-for-css-in-js-frameworks"></a>CSS-in-JS 框架的样式编辑  

现在 **，"** 样式"窗格更好地支持使用 CSS 对象模型和 [CSSOM ][CsswgDraftsCssom] (API 创建的) 样式。  许多 CSS-in-JS 框架和库在构建样式的底层使用 CSSOM API。  

现在您可以使用可构造样式表编辑在 JavaScript [中添加的样式][WicgConstructStylesheet]。  可构造的样式表是使用 Shadow DOM 时创建和分发可重用样式 [的一种新方式][MdnShadowDom]。  

例如，使用 `h1` `CSSStyleSheet` \ (CSSOM API\) 添加的样式以前不可编辑。  样式现在在"样式"面板中 **可** 编辑。  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="将随 CSSStyleSheet 一起添加的 h1 样式的背景属性从粉色更改为浅色" lightbox="../../media/2020/06/css-in-js.msft.png":::
   将 `background` 随 一起 `h1` 添加的样式 `CSSStyleSheet` 的属性从 更改 `pink` 到 `lightblue` 。
:::image-end:::  

通过使用 [CSS-in-JS][CodepenZoherghadyaliAbdgrpz]的示例试用此功能。

Chromium问题[#946975][CR946975]  

### <a name="lighthouse-6-in-the-lighthouse-panel"></a>Lighthouse 面板中的"浅楼 6"  

**"灯楼**"面板现在运行"Lighthouse 6"。  有关所有更改的完整列表，请导航到 [v6.0.0 发行说明][GithubGoogleChromeLighthouse600]。  

Lighthouse 6.0 向报告引入了三个新指标：最大内容量 画图 \ (LCP\) 、累积布局班次 \ (CLS\) 和总阻止时间 \ (TBT\) 。  

性能分数公式也进行了重新加权，以更好地反映用户的加载体验。  

Chromium问题[#772558][CR772558]  

#### <a name="first-meaningful-paint-deprecation"></a>First Meaningful 画图弃用  

First Meaningful 画图 \ (FMP\) is deprecated in Lighthouse 6.0.  FMP 也从"性能" **面板中删除** 。  **最大的 Contentful 画图**FMP 的建议替代项。  <!--For an explanation of why it was deprecated, navigate to [First Meaningful Paint][WebDevFirstMeaningfulPaint].  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

Chromium问题[#1096008][CR1096008]  

### <a name="support-for-new-javascript-features"></a>支持新的 JavaScript 功能  

DevTools 现在更好地支持一些最新的 JavaScript 语言功能。  

:::row:::
   :::column span="1":::
      [可选链接][V8DevOptionalChaining] 语法自动完成  
   :::column-end:::
   :::column span="2":::
      控制台中的属性自动完成现在**** 支持可选的链接语法，例如，除了 和 之外， `name?.` 现在也可以 `name.` `name[` 正常工作。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      用于私有字段 [的语法突出显示][V8DevClassFieldsPrivate]  
   :::column-end:::
   :::column span="2":::
      私有类字段现在在"源"面板中正确突出显示了语法 **并非常打印** 。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Nullish [并集运算符的语法突出显示][V8DevNullishCoalescing]
   :::column-end:::
   :::column span="2":::
      DevTools 现在可以在"源"面板中正确打印空的"并 **排"运算符** 。  
   :::column-end:::
:::row-end:::  

[][CR1083797] [][CR1073903]Chromium、#1073903、#1083214、#1083797 [][CR1083214]  

### <a name="new-app-shortcut-warnings-in-the-manifest-pane"></a>清单窗格中的新应用快捷方式警告  

**应用快捷方式** 可帮助用户在 Web 应用中快速启动常见任务或推荐任务。  

<!--todo: add App shortcuts when section is live  -->  

" **清单** "窗格现在显示针对以下条件的警告。  

* 应用快捷方式图标小于 96x96 像素  
* 应用快捷方式图标和清单图标不是方形 \ (，因为图标将被忽略\)   

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="应用快捷方式警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   应用快捷方式警告  
:::image-end:::  

Chromium问题[#955497][CR955497]  

### <a name="consistent-display-of-the-computed-pane"></a>"计算"窗格的一致显示  

现在 **，"** 元素"工具**** 中的"计算"窗格在所有视口大小中一致地显示为窗格。  以前 **，当**DevTools**** 视口的宽度较窄时，计算窗格合并在"样式"窗格中。  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="即使 DevTools 较窄，计算窗格也一致显示为单独的窗格" lightbox="../../media/2020/06/computed-pane.msft.png":::
   即使**** DevTools 较窄，计算窗格也一致显示为单独的窗格。
:::image-end:::  

Chromium问题[#1073899][CR1073899]  

### <a name="bytecode-offsets-for-webassembly-files"></a>WebAssembly 文件的字节码偏移  

DevTools 现在使用字节码偏移来显示 Wasm 反汇编的行号。  
行号使查看二进制数据更加清晰，并且与 Wasm 运行时引用位置的方式更加一致。  

Chromium问题[#1071432][CR1071432]  

### <a name="line-wise-copy-and-cut-in-sources-panel"></a>在"源面板"中按照行进行复制和剪切  

当在"源"面板编辑器中执行复制[][DevtoolsSourcesEditCssJavascript]或剪切操作时，DevTools 会复制或剪切当前内容行。  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="当光标位于第 5 行的末尾时，从 DevTools pen.js复制整行并粘贴到Visual Studio Code" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   当光标位于第 5 行的末尾时，从 DevToolspen.js复制整行，并粘贴到 Visual Studio Code [。][VisualStudioCode] ****
:::image-end:::  

Chromium问题[#800028][CR800028]

### <a name="console-settings-updates"></a>控制台设置更新  

#### <a name="ungroup-same-console-messages"></a>取消同一控制台消息的组  

控制台**控制台中的**组相似设置现在适用于重复消息。  以前，它只应用于类似的邮件。  

例如，以前，DevTools 未取消分组邮件，即使未取消选中" `hello` **组** 相似"。  现在， `hello` 邮件已取消组合。  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="取消选中"类似组"时，hello 消息将取消分组" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   取消 **选中"类似** 组"时 `hello` ，邮件将取消分组
:::image-end:::  

通过向控制台发送重复消息的示例试用 [此功能][CodepenZoherghadyaliZyrjgdJ]。  

Chromium问题[#1082963][CR1082963]  

### <a name="persisting-selected-context-only-settings"></a>持久化"仅选定上下文"设置  

控制台**控制台中的"所选**上下文设置现在保留。  以前，每次关闭并重新打开 DevTools 时，设置都会重置。  更改使设置行为与其他控制台选项设置一。  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="选定的仅上下文设置" lightbox="../../media/2020/06/selected-context.msft.png":::
   **选定的仅上下文** 设置  
:::image-end:::  

Chromium问题[#1055875][CR1055875]  

### <a name="performance-panel-updates"></a>性能面板更新  

#### <a name="javascript-compilation-cache-information-in-performance-tool"></a>性能工具中的 JavaScript **编译缓存** 信息  

[JavaScript 编译缓存信息][V8DevCodeCaching] 现在始终显示在"性能 **"工具的** "摘要 **"面板** 中。  以前，如果未发生代码缓存，DevTools 不会显示与代码缓存相关的任何内容。  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript 编译缓存信息" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   JavaScript 编译缓存信息  
:::image-end:::  

Chromium问题[#912581][CR912581]  

#### <a name="navigation-timing-alignment-in-the-performance-panel"></a>"性能"面板中的导航计时对齐方式  

用于 **根据** 录制开始的时间在标尺中显示时间的性能面板。  用户导航的录制时间现已更改，其中 DevTools 现在显示相对于导航的标尺时间。  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="在性能工具中对齐导航计时" lightbox="../../media/2020/06/nav-timing.msft.png":::
   在性能工具中 **对齐导航** 计时  
:::image-end:::  

First 画图、First Contentful 画图 和 Largest Contentful 画图 事件的时间更新为相对于导航的开始，这意味着计时与 报告 `DOMContentLoaded` 的时间匹配 `PerformanceObserver` 。  

Chromium问题[#974550][CR974550]  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a>断点、条件断点和登录点的新图标  

" **源** "面板具有针对断点、条件断点和日志的新设计。  断点用红色圆圈表示，就像Visual Studio Code Visual Studio [][VisualStudioCode] [。][VisualStudio]  添加图标以区分条件断点和日志点。  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="断点" lightbox="../../media/2020/06/breakpoints.msft.png":::
   断点  
:::image-end:::  

Chromium 问题 [#1041830][CR1041830]  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "使用 Microsoft Edge 开发工具命令菜单运行命令"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "设置 - 自定义 Microsoft Edge 开发工具 | Microsoft Docs"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "打开试验功能 - 试验功能 | Microsoft Docs"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "编辑 CSS 和 JavaScript - 源面板概述|Microsoft Docs"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动 - 在 DevTools Microsoft Edge中检查网络|Microsoft Docs"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS-in-JS 框架样式编辑|CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "将重复消息发送到控制台|CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS 网格规划器示例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR800028]: https://crbug.com/800028 "在 Chrome 更新后，开发人员工具编辑器中的重复行快捷方式|Chromium Bug"  
[CR912581]: https://crbug.com/912581 "在 DevTools/about：tracing |Chromium Bug"  
[CR946975]: https://crbug.com/946975 "DevTools 样式边栏不能与构造的样式表|Chromium Bug"  
[CR955497]: https://crbug.com/955497 "PBA 应用图标快捷方式菜单|Chromium Bug"  
[CR974550]: https://crbug.com/974550 "Perf 面板和 performanceObserver 组件之间的指标不匹配|Chromium Bug"  
[CR1041830]: https://crbug.com/1041830 "改进断点|Chromium Bug"  
[CR1055875]: https://crbug.com/1055875 "关闭并重新打开&quot;开发人员工具&quot;菜单后，&quot;所选上下文仅控制台&quot;设置的值不会|Chromium Bug"  
[CR1066579]: https://crbug.com/1066579 "DevTools： Show ServiceWorkers Fetch Timeline per request in Network panel |Chromium Bug"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic Developer Experience |Chromium Bug"  
[CR1073899]: https://crbug.com/1073899 "计算样式选项卡在响应模式下消失|Chromium Bug"  
[CR1073903]: https://crbug.com/1073903 "DevTools：语法突出显示对私有字段|Chromium Bug"  
[CR1082963]: https://crbug.com/1082963 "无法禁用控制台的组类似的邮件行为|Chromium Bug"  
[CR1083214]: https://crbug.com/1083214 "视点不支持可选链接|Chromium Bug"  
[CR1083797]: https://crbug.com/1083797 "为空值并成一体而损坏的|Chromium Bug"  
[CR1096008]: https://crbug.com/1096008 "删除 FMP |Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table 工具|Chromium Bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播综合网络请求|Chromium Bug"  
[CR1070378]: https://crbug.com/1070378 "将 Webhint 集成到 DevTools |Chromium Bug"  
[CR1069404]: https://crbug.com/1069404 "[开发人员工具] 小部件弹出窗口太窄|Chromium Bug"  
[CR897944]: https://crbug.com/897944 "可拖动的开发人员工具|Chromium Bug"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "使用卷影 DOM |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge 预览频道"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"
[VisualStudioCode]: https://code.visualstudio.com/ "Visual Studio 代码"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS 对象模型 (CSSOM) |W3C CSS 工作组编辑器草稿"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "私有类字段 - 公共和私有类|V8.开发"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "适用于 JavaScript 开发人员的代码|V8.开发"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 将|V8.开发"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "可选链接|V8.开发"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "可构造的样式表|Web Incubator CG"

<!--[WebDevLighthouseWhatsNew60]: https://web.dev/lighthouse-whats-new-6.0 "What's New in Lighthouse 6.0 | Web.Dev"  -->  
<!--[WebDevVitalsCoreWeb]: https://web.dev/vitals#core-web-vitals "Core Web Vitals - Web Vitals | Web.Dev"  -->  
<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebFundamentalComponentsShadowdom]: /web/fundamentals/web-components/shadowdom  -->  
<!--[WebDevLcp]: https://web.dev/lcp "Largest Contentful Paint (LCP) | Web.Dev"  -->  
<!--[WebDevFirstMeaningfulPaint]: https://web.dev/first-meaningful-paint "First Meaningful Paint | Web.Dev"  -->  
<!--[WhatsNew201902ConstructableStylesheets]: ../../2019/02/constructable-stylesheets.md "Constructable Stylesheets: seamless reusable styles | Microsoft Docs"  -->  

[TheWebWeWant]: https://webwewant.fyi/ "我们想要的网络"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-85)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
