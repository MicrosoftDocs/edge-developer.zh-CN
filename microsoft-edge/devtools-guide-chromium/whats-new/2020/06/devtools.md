---
description: CSS 网格调试功能、使用网络控制台编辑和重播请求等。
title: 'Microsoft Edge 85 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 3085153b87f09c1b5aba8fbe43c42cef0851fa9c
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397753"
---
# <a name="whats-new-in-devtools-microsoft-edge-85"></a>Microsoft Edge 85 (DevTools 中的新增)   

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>来自 Microsoft Edge 开发人员工具团队公告  

以下各节列出了你可能从 Microsoft Edge DevTools 团队错过的公告。  查看通知以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。  若要了解开发人员工具中所有最新且最的功能，请下载[Microsoft Edge][MicrosoftEdgePreviewChannels]预览频道，并按照 Twitter 上的 Microsoft [Edge DevTools 团队。][EdgeDevToolsTwitterAccount]  

### <a name="css-grid-debugging-features"></a>CSS 网格调试功能  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

Microsoft Edge DevTools 团队正在与 Chrome DevTools 团队和 Chromium 社区协作，向 DevTools 添加新的 CSS 网格调试功能。  现在，你可以将网格线号、网格间隙和扩展网格线显示为页面覆盖。  此外，网格工具的更多改进即将推出。  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   CSS 网格调试功能
:::image-end:::  

> [!NOTE]
> 若要启用实验，请导航到 ["打开实验][DevtoolsExperimentalFeaturesTurnOn] 功能"，并选中"启用新的 CSS 网格调试功能 **"旁边的复选框**。  
> 
> 若要使用示例试用实验，请导航到 [CSS 网格规划器示例][CodepenRachelweilYzwBzKM]。  

Chromium 问题 [#1047356][CR1047356]  

### <a name="edit-and-replay-requests-with-the-network-console"></a>使用网络控制台编辑和重播请求  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

你现在可以使用**网络控制台在**网络日志中对请求使用[编辑和][DevtoolsNetworkIndexLogActivity]**重播**。  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="使用网络控制台在 NetworkLog 中编辑和重播请求" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   使用网络控制台在 [NetworkLog][DevtoolsNetworkIndexLogActivity] 中编辑和 **重播请求**  
:::image-end:::  

网络控制台是一个新面板 **，它将在** [DevTools 的"][DevtoolsCustomizeIndexDrawer] 箱"中打开，并自动填充 HTTP 请求的信息。  若要显示从服务器返回的响应，请编辑请求 \ (如果需要\) 选择"发送 **"。**  

您还可以使用 **网络控制台** 直接从 DevTools 创建和发送 HTTP 请求。  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="网络控制台面板" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   网络 **控制台** 面板  
:::image-end:::  

> [!TIP]
> 若要在主 **\ (** top\) 面板（而不是 [DevTools 箱][DevtoolsCustomizeIndexDrawer]）中显示网络控制台，请导航到在面板之间 [移动工具](#move-tools-between-panels)。  

> [!NOTE]
> 若要启用实验，请导航到 ["打开实验][DevtoolsExperimentalFeaturesTurnOn] 功能"，然后选择"启用网络控制台 **"旁边的复选框**。  
> 
> 打开[网络日志][DevtoolsNetworkIndexLogActivity]，打开上下文菜单 \ (右键单击\) ，然后选择"编辑和**重播"。**  

Chromium 问题 [#1093687][CR1093687]  

### <a name="service-worker-respondwith-events-in-the-timing-tab"></a>服务工作者 respondWith 事件在"计时"选项卡中  

网络 **工具** 的 **"** 计时"选项卡现在包括 `respondWith` 服务工作器事件。  服务工作进程事件显示从服务工作进程事件处理程序开始运行前一段时间到处理程序承诺已解决 `respondWith` `fetch` 的时间的 `respondWith` `fetch` 持续时间。  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="Network 面板的"计时"选项卡中的 respondWith 服务工作者事件" lightbox="../../media/2020/06/timing-tab.msft.png":::
   网络 `respondWith` 工具的"计时"**** 选项卡中的**服务**工作者事件  
:::image-end:::  

展开 **收到的响应** 以显示来自响应的其他信息， `fetch` 如 `CacheStorageCacheName` `serviceWorkerResponseSource` ， 和 `ResponseTime` 。  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="展开收到的响应以显示提取响应的其他信息" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   展开 **收到的响应** 以显示响应的其他 `fetch` 信息  
:::image-end:::  

Chromium [问题#1066579][CR1066579]  

### <a name="webhint-feedback-in-the-issues-panel"></a>问题面板中的 webhint 反馈  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

[webhint][WebhintMain] 是一个开源工具，提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWA 和其他常见 Web 开发问题实时反馈。  在"问题"面板中查看 [Webhint][DevtoolsIssues] 反馈。  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   问题面板中的 webhint 反馈  
:::image-end:::  

> [!NOTE]
> 若要启用实验，请导航到 ["打开实验][DevtoolsExperimentalFeaturesTurnOn] 功能"，然后选择"启用 **Webhint"旁边的复选框**。  
> 
> 打开 ["问题][DevtoolsIssues] "面板以显示来自 Webhint 的反馈。  

Chromium 问题 [#1070378][CR1070378]  

### <a name="move-tools-between-panels"></a>在面板之间移动工具  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

通常，元素和网络等工具**** 只能在**** DevTools 的主 \ (top\) 面板中打开。  同样，工具（如**3D** **** 视图和问题）可能只能在 DevTools 的 (底部\) 面板中打开。  现在，你能够通过在顶部和底部面板之间移动工具来自定义 DevTools 布局。  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="在面板之间移动工具" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   在面板之间移动工具  
:::image-end:::  

> [!NOTE]
> 若要启用实验，请导航到 ["打开实验][DevtoolsExperimentalFeaturesTurnOn] 功能"，然后选择"启用支持以在面板之间 **移动选项卡"旁边的复选框**。  

Chromium 问题 [#897944][CR897944]  

### <a name="improved-initiator-tooltip-in-the-network-panel"></a>网络面板中改进的发起人工具提示  

在 Microsoft Edge 83 和 84 中，"发起人"列的工具提示显示在使用水平滚动条显示的 ["][DevtoolsNetworkIndexLogActivity] 网络日志中"中，显示资源请求的原因。  只有在工具提示中水平滚动，才能显示发起请求的调用堆栈。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 中的发起人工具提示" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   Microsoft Edge 84 中的发起人工具提示  
:::image-end:::  

从 Microsoft Edge 85 开始，现在可以在工具提示中显示发起者调用堆栈，而无需水平滚动。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 中的发起人工具提示" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   Microsoft Edge 85 中的发起人工具提示
:::image-end:::  

Chromium 问题 [#1069404][CR1069404]  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

以下各节宣布 Microsoft Edge 85 中提供的其他功能，这些功能对开源 Chromium 项目有贡献。  

### <a name="style-editing-for-css-in-js-frameworks"></a>CSS-in-JS 框架的样式编辑  

" **样式** "窗格现在更好地支持使用 CSS 对象模型和 [CSSOM ][CsswgDraftsCssom] (API 创建的) 样式。  许多 CSS-in-JS 框架和库使用底层 CSSOM API 构造样式。  

现在，您可以使用可构造样式表编辑在 JavaScript [中添加的样式][WicgConstructStylesheet]。  可构造样式表是使用 Shadow DOM 时创建和分发可重用样式 [的一种新方式][MdnShadowDom]。  

例如，使用 `h1` `CSSStyleSheet` \ (CSSOM API\) 添加的样式以前不可编辑。  样式现在在"样式"面板中 **可** 编辑。  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="将使用 CSSStyleSheet 添加的 h1 样式的背景属性从粉红色更改为浅色" lightbox="../../media/2020/06/css-in-js.msft.png":::
   将 `background` 添加的 `h1` 样式的属性从 `CSSStyleSheet` `pink` `lightblue`
:::image-end:::  

尝试使用使用 [CSS-in-JS 的示例来试用此功能][CodepenZoherghadyaliAbdgrpz]。

Chromium 问题 [#946975][CR946975]  

### <a name="lighthouse-6-in-the-lighthouse-panel"></a>Lighthouse 面板中的 Lighthouse 6  

**Lighthouse**面板现在运行 Lighthouse 6。  有关所有更改的完整列表，请导航到 [v6.0.0 发行说明][GithubGoogleChromeLighthouse600]。  

Lighthouse 6.0 向报告引入了三个新指标：最大内容绘制 \ (LCP\) 、累积布局 Shift \ (CLS\) 和总阻止时间 \ (TBT\) 。  

性能分数公式也进行了重新加权，以更好地反映用户的加载体验。  

Chromium 问题 [#772558][CR772558]  

#### <a name="first-meaningful-paint-deprecation"></a>First Meaningful Paint deprecation  

First Meaningful Paint \ (FMP\) 在 Lighthouse 6.0 中已弃用。  FMP 已从"性能" **面板** 中删除。  **最大内容绘制** 是 FMP 的推荐替换。  <!--For an explanation of why it was deprecated, navigate to [First Meaningful Paint][WebDevFirstMeaningfulPaint].  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

Chromium [问题#1096008][CR1096008]  

### <a name="support-for-new-javascript-features"></a>支持新的 JavaScript 功能  

DevTools 现在更好地支持一些最新的 JavaScript 语言功能。  

:::row:::
   :::column span="1":::
      [可选链接][V8DevOptionalChaining] 语法自动完成  
   :::column-end:::
   :::column span="2":::
      现在，控制台中的属性自动**** 完成支持可选的链接语法，例如，现在除了和 之外， `name?.` 属性自动完成 `name.` 还起作用 `name[` 。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      针对私有字段 [突出显示的语法][V8DevClassFieldsPrivate]  
   :::column-end:::
   :::column span="2":::
      私有类字段现在在"源"面板中正确突出显示了语法并非常 **打印** 。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Nullish [并集运算符的语法突出显示][V8DevNullishCoalescing]
   :::column-end:::
   :::column span="2":::
      DevTools 现在在"源"面板中正确打印空的并**排运算符。**  
   :::column-end:::
:::row-end:::  

Chromium[][CR1073903]问题[#1073903、#1083214、#1083797][CR1083214] [][CR1083797]  

### <a name="new-app-shortcut-warnings-in-the-manifest-pane"></a>清单窗格中的新应用快捷方式警告  

**应用快捷方式** 可帮助用户在 Web 应用中快速启动常见或推荐的任务。  

<!--todo: add App shortcuts when section is live  -->  

清单 **窗格** 现在显示以下条件的警告。  

* 应用快捷方式图标小于 96x96 像素  
* 应用快捷方式图标和清单图标不是方形 \ (，因为忽略这些图标\)   

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="应用快捷方式警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   应用快捷方式警告  
:::image-end:::  

Chromium [问题#955497][CR955497]  

### <a name="consistent-display-of-the-computed-pane"></a>计算窗格的一致显示  

" **元素"** 工具中的"计算" **窗格现在在所有** 视口大小中一致地显示为窗格。  以前 **，当**DevTools**** 视口的宽度较窄时，计算窗格合并在样式窗格中。  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="即使 DevTools 较窄，计算窗格也一致显示为单独的窗格" lightbox="../../media/2020/06/computed-pane.msft.png":::
   即使**** DevTools 较窄，计算窗格也一致显示为单独的窗格。
:::image-end:::  

Chromium 问题 [#1073899][CR1073899]  

### <a name="bytecode-offsets-for-webassembly-files"></a>WebAssembly 文件的字节码偏移量  

DevTools 现在使用字节码偏移来显示 Wasm 反汇编的行号。  
行号使查看二进制数据更加清晰，并且与 Wasm 运行时引用位置的方式更加一致。  

Chromium 问题 [#1071432][CR1071432]  

### <a name="line-wise-copy-and-cut-in-sources-panel"></a>源面板中的行复制和剪切  

当在源面板编辑器中执行复制或剪切[][DevtoolsSourcesEditCssJavascript]时，DevTools 复制或剪切当前内容行。  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="使用光标位于第 5 行的末尾，从 DevTools pen.js复制整行，并粘贴到Visual Studio代码" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   使用光标位于第 5 行的末尾，从 DevTools **pen.js复制整 ** 行，并粘贴到 Visual Studio [代码中][VisualStudioCode]。
:::image-end:::  

Chromium [问题#800028][CR800028]

### <a name="console-settings-updates"></a>控制台设置更新  

#### <a name="ungroup-same-console-messages"></a>取消对同一控制台消息的组  

控制台 **设置中的** 组相似切换现在适用于重复的邮件。  以前，它只应用于类似的邮件。  

例如，以前，DevTools 未取消对邮件的分组，即使未选中" `hello` **类似** 组"。  现在， `hello` 邮件已取消组合。  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="取消选中"类似组"时，Hello 消息将取消分组" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   取消 **选中"** 类似组"时， `hello` 邮件将取消分组
:::image-end:::  

尝试使用将重复消息发送到 [控制台的示例来试用此功能][CodepenZoherghadyaliZyrjgdJ]。  

Chromium 问题 [#1082963][CR1082963]  

### <a name="persisting-selected-context-only-settings"></a>仅保留所选上下文设置  

现在 **，"仅控制台设置** "中的"所选上下文"设置将保留。  以前，每次关闭并重新打开 DevTools 时，设置都会重置。  更改使设置行为与其他控制台设置选项一致。  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="仅所选上下文设置" lightbox="../../media/2020/06/selected-context.msft.png":::
   **仅所选上下文** 设置  
:::image-end:::  

Chromium 问题 [#1055875][CR1055875]  

### <a name="performance-panel-updates"></a>性能面板更新  

#### <a name="javascript-compilation-cache-information-in-performance-tool"></a>性能工具中的 JavaScript 编译 **缓存** 信息  

[JavaScript 编译缓存信息][V8DevCodeCaching]现在始终显示在性能**工具的"摘要****"面板**中。  以前，如果未发生代码缓存，DevTools 不会显示与代码缓存相关的任何内容。  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript 编译缓存信息" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   JavaScript 编译缓存信息  
:::image-end:::  

Chromium [问题#912581][CR912581]  

#### <a name="navigation-timing-alignment-in-the-performance-panel"></a>"性能"面板中的导航计时对齐方式  

**用于**根据录制开始的时间在标尺中显示时间的性能面板。  用户导航的录制时间现已更改，其中 DevTools 现在改为显示相对于导航的标尺时间。  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="在性能工具中对齐导航计时" lightbox="../../media/2020/06/nav-timing.msft.png":::
   在性能工具中 **对齐导航** 计时  
:::image-end:::  

"第一个绘制"、"第一个内容绘制"和"最大内容绘制"事件的时间将更新为相对于导航的开始，这意味着计时与报告 `DOMContentLoaded` 的时间匹配 `PerformanceObserver` 。  

Chromium 问题 [#974550][CR974550]  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a>断点、条件断点和登录点的新图标  

" **源** "面板具有针对断点、条件断点和日志点的新设计。  断点用红色圆圈表示，就像Visual Studio[代码][VisualStudioCode]和[Visual Studio。][VisualStudio]  添加图标以区分条件断点和日志点。  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="断点" lightbox="../../media/2020/06/breakpoints.msft.png":::
   断点  
:::image-end:::  

Chromium 问题 [#1041830][CR1041830]  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "使用 Microsoft Edge 开发工具命令菜单运行命令"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "箱 - 自定义 Microsoft Edge DevTools |Microsoft Docs"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "打开实验性功能 - 实验|Microsoft Docs"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "编辑 CSS 和 JavaScript - 源面板概述|Microsoft Docs"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动 - 检查 Microsoft Edge DevTools |Microsoft Docs"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "样式编辑 CSS-in-JS 框架|CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "将重复消息发送到控制台|CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS 网格规划器示例|CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR800028]: https://crbug.com/800028 "在 Chrome 更新后，开发人员工具编辑器中的重复行快捷方式|Chromium Bug"  
[CR912581]: https://crbug.com/912581 "在 DevTools/about：tracing |Chromium Bug"  
[CR946975]: https://crbug.com/946975 "DevTools 样式边栏不能与构造的样式表|Chromium Bug"  
[CR955497]: https://crbug.com/955497 "PWA 应用图标快捷菜单|Chromium Bug"  
[CR974550]: https://crbug.com/974550 "Perf 面板与 performanceObserver |Chromium Bug"  
[CR1041830]: https://crbug.com/1041830 "改进断点颜色|Chromium Bug"  
[CR1055875]: https://crbug.com/1055875 "关闭并重新打开开发人员工具后，"所选上下文仅控制台"设置的值不会|Chromium Bug"  
[CR1066579]: https://crbug.com/1066579 "DevTools： Show ServiceWorkers Fetch Timeline per request in Network panel |Chromium Bug"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic Developer Experience |Chromium Bug"  
[CR1073899]: https://crbug.com/1073899 "计算样式选项卡在响应模式下消失|Chromium Bug"  
[CR1073903]: https://crbug.com/1073903 "DevTools：语法突出显示不能用于专用字段|Chromium Bug"  
[CR1082963]: https://crbug.com/1082963 "无法禁用控制台的组类似的邮件行为|Chromium Bug"  
[CR1083214]: https://crbug.com/1083214 "acorn 不支持可选链接|Chromium Bug"  
[CR1083797]: https://crbug.com/1083797 "为了空的并网而中断的非常|Chromium Bug"  
[CR1096008]: https://crbug.com/1096008 "删除 FMP |Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/Table 工具|Chromium Bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播综合网络请求|Chromium Bug"  
[CR1070378]: https://crbug.com/1070378 "将 Webhint 集成到 DevTools |Chromium Bug"  
[CR1069404]: https://crbug.com/1069404 "[开发人员工具] 小组件弹出窗口太窄|Chromium Bug"  
[CR897944]: https://crbug.com/897944 "可拖动的开发工具面板|Chromium Bug"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "使用阴影 DOM |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge 预览频道"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"
[VisualStudioCode]: https://code.visualstudio.com/ "Visual Studio 代码"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS 对象模型 (CSSOM) |W3C CSS 工作组编辑器草稿"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "私有类字段 - 公共和私有类|V8.开发人员"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "适用于 JavaScript 开发人员的代码缓存|V8.开发人员"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "空的并|V8.开发人员"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "可选链接|V8.开发人员"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "可构造样式表对象|Web Incubator CG"

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
> 原始页面位于 [此处](https://developers.google.com/web/updates/2020/06/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
