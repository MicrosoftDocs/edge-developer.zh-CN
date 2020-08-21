---
title: '开发工具包 Microsoft Edge 85 (中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f569414a95336278c93b1bbafd57153ca902df12
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942193"
---
# Microsoft Edge 85 实用 (版的新增)   

## 来自 Microsoft Edge 开发人员工具团队公告  

以下部分是你可能在 Microsoft Edge DevTools 团队中错过的通知的列表。  查看公告，尝试使用 DevTools 中的新功能、VS 代码扩展等。  若要在开发工具中了解最新和最出色功能，请下载 [Microsoft Edge 预览渠道并][MicrosoftEdgePreviewChannels] 在 Twitter 上按照 [Microsoft Edge DevTools 团队一并关注 Microsoft Edge DevTools 团队][EdgeDevToolsTwitterAccount]。  

### CSS 网格调试功能  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   实质功能  
:::image-end:::  

Microsoft Edge 开发工具团队与 Chrome DevTools 团队和 Chromium 社区进行协作，为 DevTools 添加新的 CSS 网格调试功能。  您现在能够将网格行的数字、网格行和扩展的网格线显示为页面覆盖。  此外，即将推出对网格工具的更多改进。  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   CSS 网格调试功能
:::image-end:::  

> [!NOTE]
> 若要启用实用功能，请参阅" [启用实用功能"][DevtoolsExperimentalFeaturesTurnOn] 并选中"启用 **新 CSS 网格调试功能"旁边的复选框**。  
> 
> 要试用示例，请参阅 [CSS 网格规划器示例][CodepenRachelweilYzwBzKM]。  

Chromium [#1047356][CR1047356]  

### 使用网络控制台编辑和重播请求  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   实质功能  
:::image-end:::  

你现在可以使用" **网络网络控制台** "在 [网络日志中的][DevtoolsNetworkIndexLogActivity] 请求上进行 **编辑和重播**。  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="使用网络控制台编辑和重播 NetworkLog 中的请求" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   使用网络控制台编辑并重播 [NetworkLog][DevtoolsNetworkIndexLogActivity] **中的请求**  
:::image-end:::  

新面板将在**Network Console**[DevTools 绘][DevtoolsCustomizeIndexDrawer]图器中打开网络控制台，并用 HTTP 请求的信息自动填充。  若要查看从服务器返回的响应，请编辑请求 \ (如需要它）并 ) 选择 **"发送**"。  

您也可以使用" **网络控制台"** 直接从 DevTools 创建并发送 HTTP 请求。  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text=""网络控制台"面板" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   " **网络控制台"** 面板  
:::image-end:::  

> [!TIP]
> 若要查看 **主** \ (top\) 面板中"网络控制台"而不是 [DevTools Drawer，][DevtoolsCustomizeIndexDrawer]请参阅在 [面板之间移动工具](#move-tools-between-panels)。  

> [!NOTE]
> 若要启用实例，请参阅" [启用实用功能][DevtoolsExperimentalFeaturesTurnOn] "，并选中"启用网络控制台 **"旁边的复选框**。  
> 
> 打开网络 [日志][DevtoolsNetworkIndexLogActivity]，打开上下文菜单 \ (右键单击\) ，然后选择" **编辑"和"重播**"。  

Chromium [问题#1093687][CR1093687]  

### 在"计时"选项卡中的服务工作者响应事件  

" **网络"面板** 的"计 **时** "选项卡现包含 `respondWith` 服务工作者事件。  服务工作者事件会在服务工作者事件处理程序开始在设置处理程序 `respondWith` `fetch` `respondWith` promise 时开始运行至该时间之前的 `fetch` 持续时间。  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="The service Worker 事件（网页板的"计时"选项卡）中的 respondWith Service Worker 事件" lightbox="../../media/2020/06/timing-tab.msft.png":::
   " `respondWith` 网络"面板的"**计时"选项卡**中的服务**Network**工作者事件  
:::image-end:::  

展开收到 **的响应，** 查看来自回复的更多 `fetch` 信息，如与响应 `CacheStorageCacheName` `serviceWorkerResponseSource` 之间的其他 `ResponseTime` 信息。  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="展开收到的响应以查看来自提取响应的更多信息" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   展开 **收到的响应** 以查看来自回复 `fetch` 的更多信息  
:::image-end:::  

Chromium [问题#1066579][CR1066579]  

### 问题面板中的 WebHint 反馈  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   实质功能  
:::image-end:::  

[webhint 是][WebhintMain] 一款开源工具，可提供有关辅助功能、跨浏览器兼容性、安全性、性能、PWA 和其他常见网站开发问题的实时反馈。  现在你可以在问题面板中查看网络 [提示反][DevtoolsIssues] 馈。  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="问题面板中的 WebHint 反馈" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   问题面板中的 WebHint 反馈  
:::image-end:::  

> [!NOTE]
> 若要启用实用功能，请参见 ["启用实用功能"，][DevtoolsExperimentalFeaturesTurnOn] 并选中"启用 **webhint"旁边的复选框**。  
> 
> 打开问题 [面板][DevtoolsIssues] ，以查看来自 Webhint 的反馈。  

Chromium [问题#1070378][CR1070378]  

### 在面板之间移动工具  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   实质功能  
:::image-end:::  

通常，元素和网络**等**工具只能在**Network**DevTools 的主 \ (top\) 面板中打开。  同样 **，3D 视图** 和 **问题** 等工具只能在 DevTools 绘图器 \ (底\) 面板中打开。  现在你可以通过在顶部和底部面板之间移动工具自定义 DevTools 布局。  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="在面板之间移动选项卡" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   在面板之间移动选项卡  
:::image-end:::  

> [!NOTE]
> 若要启用实效果，请参阅" [启用实用功能"并][DevtoolsExperimentalFeaturesTurnOn] 选中"启用支持 **"在面板之间移动选项卡旁边的复选框**。  

Chromium [问题#897944][CR897944]  

### 改进了网络面板中的"初始平行器工具提示"  

在 Microsoft Edge 83 和 84 中，"初始窗口"列的工具提示，其中显示资源请求的起始结点，即在 [显示了][DevtoolsNetworkIndexLogActivity] 水平滚动条的"网络日志"中。  您只能看到通过在工具提示中水平滚动来发出请求的调用堆叠。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 中的初始方工具提示" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   Microsoft Edge 84 中的初始方工具提示  
:::image-end:::  

从 Microsoft Edge 85 开始，你现在可以看到工具提示中的初始呼叫堆叠，无需水平滚动。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 中的初始表工具提示" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   Microsoft Edge 85 中的初始表工具提示
:::image-end:::  

Chromium [问题#1069404][CR1069404]  

## 来自 Chromium 项目的公告  

以下部分公布给开源 Chromium 项目的 Microsoft Edge 85 中可用的其他功能。  

### CSS 内的 CSS 框架的样式编辑  

" **样式** "窗格现在支持更好的支持编辑 [使用 CSS 对象模型和 CSSOM (或 API 创建) ][CsswgDraftsCssom] 样式。  许多 CSS 内的 JS 框架和库都使用本机下的 CSSOM API 构造样式。  

你现在可以使用构造样式表编辑 JavaScript [中添加的样式][WicgConstructStylesheet]。  在使用 Shadow DOM 时，构造样式表是一种用于创建和分发 [可重复使用的样式的新方法][MdnShadowDom]。  

例如，使用 `h1` `CSSStyleSheet` \ (CSSOM API 添加的样式之前) 不可编辑。  现在，这些样式在"样式"窗格中 **可编辑** 。  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="更改 h1 样式的背景属性以 CSSStyleSheet 的形式从头更改为浅蓝色" lightbox="../../media/2020/06/css-in-js.msft.png":::
   更改添加的 `background` 样式 `h1` 的属性来自 `CSSStyleSheet` 其他 `pink` 位置 `lightblue` 。
:::image-end:::  

请让此功能试用 [使用 CSS 内 JS 的示例][CodepenZoherghadyaliAbdgrpz]。

Chromium [问题#946975][CR946975]  

### Lighthouse 面板中的浅色 6  

**光照面板**现在运行了浅色house 6。  有关所有更改的完整列表，请 [访问 v6.0.0 发行说明][GithubGoogleChromeLighthouse600]。  

Lighthouse 6.0 向报表中引入了三个新的指标：内容最大画图 \ (LCP\) 、累计布局 Shift \ (CLS\) 和总阻止时间 \ (TBT\) 。  

性能分数公式也经过重新正确对分析，可更好地反射用户的加载体验。  

Chromium [问题#772558][CR772558]  

#### First Meaningful Paint deprecation  

First Meaningful Paint \ (FMP\) in Lighthouse 6.0 中已弃用。  "性能"面板也已删除 FMP。 **Performance**  **建议 FMP 使用最** 大的内容画图替换。  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

Chromium [问题#1096008][CR1096008]  

### 支持新的 JavaScript 功能  

DevTools 现在支持某些最新的 JavaScript 语言功能。  

:::row:::
   :::column span="1":::
      [可选][V8DevOptionalChaining] 交换语法自动完成  
   :::column-end:::
   :::column span="2":::
      现在，主机中的属性 **自动完成** 功能自动完成（例如，你现在也可在此效果上有  `name?.` `name.` 效 `name[` ）。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      私有字段的语法 [突出显示][V8DevClassFieldsPrivate]  
   :::column-end:::
   :::column span="2":::
      私有类字段现在可以在"源"面板中正确突出显示、预先 **打印的语法** 。****  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Nullish 成本运 [算符的语法突出显示][V8DevNullishCoalescing]
   :::column-end:::
   :::column span="2":::
      DevTools 现在可以正确地预先打印源面板中的 Nullish 副本 **运算** 符。  
   :::column-end:::
:::row-end:::  

Chromium [#1073903、][CR1073903] [#1083214][CR1083214]等 [#1083797][CR1083797]  

### 清单窗格中的新应用快捷方式警告  

**应用快捷方式** 可帮助用户在 Web 应用中快速启动常规任务或推荐的任务。  

<!--todo: add App shortcuts when section is live  -->  

清 **单窗格** 现在显示以下条件的警告。  

* 应用快捷方式图标小于 96x96 像素  
* 应用快捷方式图标和清单图标不是方形 \ (，，由于图标被忽略\)   

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="应用快捷方式警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   应用快捷方式警告  
:::image-end:::  

Chromium [问题#955497][CR955497]  

### "计算"窗格的一个一体显示  

"**元素"面**板中的计算后**Elements**面板现在所有视区大小上以一个窗格形式显示一定。  如果 DevTools**视口的**宽度缩小**Styles**，则以前计算的窗格会合并到"样式"窗格中。  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="计算的窗格一直显示为单独的窗格，即使 DevTools 变窄时也是如此" lightbox="../../media/2020/06/computed-pane.msft.png":::
   计算 **的窗格** 一直显示为单独的窗格，即使 DevTools 变窄时也是如此。
:::image-end:::  

Chromium [问题#1073899][CR1073899]  

### WebAssembly 文件的字节码偏移  

DevTools 现在使用字节码偏移量来显示以人区分的数目形式显示。  
使用行号，你可以更清楚地查看库数据，与 Wasm 运行时引用位置的方式更加一一体。  

Chromium [问题#1071432][CR1071432]  

### "源面板"中的行复制和剪切  

在源面板编辑器中执行不带选择内容的复制或剪 [切时][DevtoolsSourcesEditCssJavascript]，DevTools 会复制或剪切当前内容行。  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="光标位于第 5 行的末尾，从 DevTools pen.js复制整行并粘贴 VS 代码" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   光标位于第 5 行的末尾，从开发pen.js复制整个行 **pen.js** 见并粘贴 [VS 代码][VSCode]。
:::image-end:::  

Chromium [问题#800028][CR800028]

### 主机设置更新  

#### 取消组合相同主机消息  

**现将在控制台**设置中的组相似的切换按钮用于重复的邮件。  以前它仅应用于类似的邮件。  

例如，以前，甚至不取消组合邮件 `hello` ，即使 **未选中相** 似的组也是如此。  现在， `hello` 将取消组合该消息。  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="取消选中相似形状时，头堆消息会取消组合" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   取消 **选中相似的组合** 后，会 `hello` 取消组合该邮件。
:::image-end:::  

请尝试以下 [功能，它具有向主机发送重复消息的示例][CodepenZoherghadyaliZyrjgdJ]。  

Chromium [问题#1082963][CR1082963]  

### 仅保存所选上下文设置  

现在 **将持久保存主** 机设置中的选定上下文设置。  以前，每次关闭并重新打开 VvTools 后都会重置设置。  更改使设置行为与其他"主机设置"选项一一一一然。  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="所选上下文仅设置" lightbox="../../media/2020/06/selected-context.msft.png":::
   **所选上下文仅** 设置  
:::image-end:::  

Chromium [问题#1055875][CR1055875]  

### 性能面板更新  

#### JavaScript 编译缓存信息（Performance 面板中）  

[JavaScript 编译缓存信息现在][V8DevCodeCaching] 始终显示在性能面板的"摘要"选项卡中。  以前，如果未发生代码代码并未显示与代码转换相关的任何内容，则 DevTools 未显示任何与代码转换相关内容。  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript 编译缓存信息" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   JavaScript 编译缓存信息  
:::image-end:::  

Chromium [#912581][CR912581]  

#### "性能"面板中的导航计时对齐方式  

用于 **根据** 录制开始时间在标尺中显示时间的时间面板。  对于用户导航的录制计时，计时已更改，其中 DevTools 现在显示相对于导航的标尺时间。  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="在 Performance 面板中对齐导航计时" lightbox="../../media/2020/06/nav-timing.msft.png":::
   在 Performance 面板中对齐 **导航计** 时  
:::image-end:::  

"首次画图"、"第一画图"、"第一画图"和"最大内容画图"事件更新为相对于导航 `DOMContentLoaded` 开始的开头，这意味着计时匹配由你报告的排时 `PerformanceObserver` 匹配。  

Chromium [问题#974550][CR974550]  

### 断点、条件断点和日志点的新图标  

" **源** 语言"面板提供用于断点、条件断点和逻辑的新设计。  断点由复数环表示，就像[VS][VSCode]代码和信[Visual Studio。][VS]  为区分条件断点和登录点都添加图标。  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="断点" lightbox="../../media/2020/06/breakpoints.msft.png":::
   断点  
:::image-end:::  

Chromium [问题#1041830][CR1041830]  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft 文档"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "使用 Microsoft Edge DevTools 命令菜单 |Microsoft 文档"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "绘图器 - 自定义 Microsoft Edge 开发工具 |Microsoft 文档"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实用功能 - 实用功能 |Microsoft 文档"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "查找并解决 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "编辑 CSS 和 JavaScript - 源面板概述 |Microsoft 文档"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动 - 在 Microsoft Edge DevTools 中检查网络活动 |Microsoft 文档"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS 内的框架的样式编辑 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "将重复的消息发送到控制台 |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS 网格规划器示例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR772558]: https://crbug.com/772558 "DevTools：更新到修简版 |Chromium bug"  
[CR800028]: https://crbug.com/800028 "Chrome 更新 | 后，开发人员工具编辑器中的重复线快捷方式无法正常工作 |Chromium bug"  
[CR912581]: https://crbug.com/912581 "公开 DevTools 中的 V8 编码存档的脚本/about：tracing |Chromium bug"  
[CR946975]: https://crbug.com/946975 "DevTools 样式边栏不支持构造样式表 |Chromium bug"  
[CR955497]: https://crbug.com/955497 "PWA 的应用图标快捷菜单|Chromium bug"  
[CR974550]: https://crbug.com/974550 "指标在 Perf 面板和性能Observer |Chromium bug"  
[CR1041830]: https://crbug.com/1041830 "改善断点的颜色 |Chromium bug"  
[CR1055875]: https://crbug.com/1055875 "关闭并重新打开开发人员工具 |后，选定上下文设置仅保留主机设置的值Chromium bug"  
[CR1066579]: https://crbug.com/1066579 "DevTools：在网络面板中显示对每个请求的 ServiceWorkers 提取时间线 |Chromium bug"  
[CR1071432]: https://crbug.com/1071432 "很多普通开发人员体验 |Chromium bug"  
[CR1073899]: https://crbug.com/1073899 "已计算的样式选项卡在响应模式中消失|Chromium bug"  
[CR1073903]: https://crbug.com/1073903 "DevTools：语法突出显示不适用于私有字段 |Chromium bug"  
[CR1082963]: https://crbug.com/1082963 "无法禁用主机类似消息行为|Chromium bug"  
[CR1083214]: https://crbug.com/1083214 "该链接不支持可选链接 |Chromium bug"  
[CR1083797]: https://crbug.com/1083797 "为 Nullish coal 定向考虑预出打印中断的问题Chromium bug"  
[CR1096008]: https://crbug.com/1096008 "删除 FMP |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/弹性 Xbox/表格工具 |Chromium bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播合规网络请求的工具 |Chromium bug"  
[CR1070378]: https://crbug.com/1070378 "将 Webhint 集成到 DevTools |Chromium bug"  
[CR1069404]: https://crbug.com/1069404 "[开发工具] 小组件弹出窗口太窄]Chromium bug"  
[CR897944]: https://crbug.com/897944 "可拖动开发人员面板 |Chromium bug"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "使用"shadow DOM"MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge 预览频道"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio代码"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS 对象模型 (CSSOM) |工作组编辑器草稿的 W3C CSS 工作"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "私有类字段 - 公共类字段和私有类字段 |V8。开发者"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "适用于 JavaScript 开发人员的代码库 |V8。开发者"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish coalescing |V8。开发者"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "可选链接 |V8。开发者"  

[WebhintMain]: https://webhint.io "Webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "构造样式表对象 |Web Incubator CG"

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
> 原始页面位于此处，[由 Jecelyn Yeen][JecelynYeen] \ (Developer advocate， Chrome DevTools\) 。 [here](https://developers.google.com/web/updates/2020/06/devtools/index)  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
