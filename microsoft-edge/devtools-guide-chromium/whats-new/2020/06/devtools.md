---
description: CSS 网格调试功能，通过网络控制台编辑和重播请求等。
title: DevTools (Microsoft Edge 85) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 01651bdf0f36f7c175f843655c275695a680b6c1
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015459"
---
# DevTools (Microsoft Edge 85) 中的新增功能  

## 来自 Microsoft Edge 开发人员工具团队公告  

以下部分是您可能已错过的 Microsoft Edge DevTools 团队的公告列表。  请参阅公告以尝试 DevTools、Visual Studio 代码扩展等中的新功能。  若要随时了解开发人员工具中的所有最新功能和最新功能，请下载 [Microsoft edge 预览频道][MicrosoftEdgePreviewChannels] 并 [关注 Twitter 上的 microsoft edge DevTools 团队][EdgeDevToolsTwitterAccount]。  

### CSS 网格调试功能  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   实验性功能  
:::image-end:::  

Microsoft Edge DevTools 团队正与 Chrome DevTools 团队和 Chromium 社区协作，将新的 CSS 网格调试功能添加到 DevTools。  现在，你可以将网格线编号、网格间距和扩展网格线显示为页面覆盖。  此外，即将推出对网格工具的更多改进。  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   CSS 网格调试功能
:::image-end:::  

> [!NOTE]
> 若要启用实验，请参阅启用 [实验功能][DevtoolsExperimentalFeaturesTurnOn] ，然后选中 " **启用新 CSS 网格调试功能**" 旁边的复选框。  
> 
> 若要试用有关示例的实验，请参阅 [CSS 网格 planner 示例][CodepenRachelweilYzwBzKM]。  

Chromium 问题 [#1047356][CR1047356]  

### 通过网络控制台编辑和重播请求  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能请求。:::

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   使用**网络控制台**编辑和重播[NetworkLog][DevtoolsNetworkIndexLogActivity]中的请求  
:::image-end:::  

新的面板， **网络控制台** 将在 [DevTools 抽屉][DevtoolsCustomizeIndexDrawer] 中打开，并自动填充 HTTP 请求的信息。  若要查看从服务器返回的响应，请在需要时编辑请求 \ (\ ) 然后选择 " **发送**"。  

您也可以使用 **网络控制台** 直接从 DevTools 创建和发送 HTTP 请求。  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   **网络控制台**面板  
:::image-end:::  

> [!TIP]
> 若要在主 \ (top \ ) 面板而不是[DevTools 抽屉][DevtoolsCustomizeIndexDrawer]中查看**网络控制台**，请参阅[在面板之间移动工具](#move-tools-between-panels)。  

> [!NOTE]
> 若要启用实验，请参阅启用 [实验功能][DevtoolsExperimentalFeaturesTurnOn] 和选择 **启用网络控制台**旁边的复选框。  
> 
> 打开 [网络日志][DevtoolsNetworkIndexLogActivity]，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **编辑并重播**"。  

Chromium 问题 [#1093687][CR1093687]  

### "计时" 选项卡中的服务工作人员 respondWith 事件  

"**网络**" 面板的 "**计时**" 选项卡现在包括 `respondWith` 服务辅助事件。  `respondWith`服务工作者事件显示在 `fetch` `respondWith` `fetch` 结算处理程序承诺的时间开始运行服务辅助事件处理程序之前的时间段内的持续时间。  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/timing-tab.msft.png":::
   " `respondWith` **网络**" 面板的 "**计时**" 选项卡中的服务工作人员事件  
:::image-end:::  

展开 " **已收到答复** "，以查看来自 `fetch` 、和的响应的其他信息 `CacheStorageCacheName` `serviceWorkerResponseSource` `ResponseTime` 。  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   展开 "**已收到答复**" 以查看来自响应的其他信息 `fetch`  
:::image-end:::  

Chromium 问题 [#1066579][CR1066579]  

### "问题" 面板中的 webhint 反馈  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能" 面板中看到 webhint 反馈。 ::: 

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   "问题" 面板中的 webhint 反馈  
:::image-end:::  

> [!NOTE]
> 若要启用实验，请参阅启用 [实验功能][DevtoolsExperimentalFeaturesTurnOn] 和选择 **启用 webhint**旁边的复选框。  
> 
> 打开 " [问题][DevtoolsIssues] " 面板，查看来自 webhint 的反馈。  

Chromium 问题 [#1070378][CR1070378]  

### 在面板之间移动工具  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能 (底部 \ ) 面板中打开。现在，你可以通过在顶部面板和底部面板之间移动工具来自定义 DevTools 布局。:::

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   在面板之间移动选项卡  
:::image-end:::  

> [!NOTE]
> 若要启用实验，请参阅启用 [实验功能][DevtoolsExperimentalFeaturesTurnOn] ，然后选中 " **启用支持" 以在面板之间移动选项卡**旁边的复选框。  

Chromium 问题 [#897944][CR897944]  

### 改进了 "网络" 面板中的发起程序工具提示  

在 Microsoft Edge 83 和84中，"发起人" 列的工具提示，其中显示了在使用水平滚动条显示的 [网络日志][DevtoolsNetworkIndexLogActivity] 中的资源请求原因。  你只能通过在工具提示中水平滚动来查看启动请求的调用堆栈。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   Microsoft Edge 84 中的发起程序工具提示  
:::image-end:::  

从 Microsoft Edge 85 开始，您现在可以在工具提示中看到启动器调用堆栈，而无需水平滚动。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   Microsoft Edge 85 中的发起程序工具提示
:::image-end:::  

Chromium 问题 [#1069404][CR1069404]  

## 来自 Chromium 项目的公告  

以下各节宣布了在 Microsoft Edge 85 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。  

### 对 .JS 中的 CSS 框架进行样式编辑  

现在，" **样式** " 窗格对通过 CSS 对象模型创建的样式有更好的支持 [ (CSSOM) ][CsswgDraftsCssom] api。  许多 CSS 中的 CSS 框架和库使用 CSSOM Api 来构建样式。  

现在，你可以使用 [Constructable 样式表][WicgConstructStylesheet]编辑在 JavaScript 中添加的样式。  Constructable 样式表是在使用 [影子 DOM][MdnShadowDom]时创建和分发可重用样式的新方法。  

例如， `h1` `CSSStyleSheet` 以前无法编辑用 \ (CSSOM api \ ) 添加的样式。  样式现在可在 " **样式** " 窗格中编辑。  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/css-in-js.msft.png":::
   `background` `h1` 将添加的样式的属性更改 `CSSStyleSheet` `pink` 为 `lightblue` 。
:::image-end:::  

为此功能提供一个 [使用在 .js 中使用 CSS 的示例][CodepenZoherghadyaliAbdgrpz]。

Chromium 问题 [#946975][CR946975]  

### Lighthouse 面板中的 Lighthouse 6  

**Lighthouse**面板现在正在运行 Lighthouse 6。  有关所有更改的完整列表，请参阅 [v 6.0.0 发行说明][GithubGoogleChromeLighthouse600]。  

Lighthouse 6.0 介绍报表的三个新指标：最大的 Contentful 油漆 \ (LCP \ ) ，累积布局 Shift \ (CLS \ ) 和总阻塞时间 \ (TBT \ ) 。  

性能分数公式也已 reweighted，以更好地反映用户的加载体验。  

Chromium 问题 [#772558][CR772558]  

#### 第一个有意义的画图弃用  

第一个有意义的油漆 \ (Lighthouse 6.0 中已弃用 FMP \ ) 。  FMP 也已从 " **性能** " 面板中删除。  **最大 Contentful 画图** 是推荐的 FMP 替换。  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

Chromium 问题 [#1096008][CR1096008]  

### 对新的 JavaScript 功能的支持  

DevTools 现在对某些最新的 JavaScript 语言功能提供了更好的支持。  

:::row:::
   :::column span="1":::
      [可选的链接][V8DevOptionalChaining] 语法自动完成  
   :::column-end:::
   :::column span="2":::
      现在， **控制台** 中的属性自动完成支持可选的链接语法，例如，  `name?.` 除了 `name.` 和 `name[` 。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      [私有字段][V8DevClassFieldsPrivate]的语法突出显示  
   :::column-end:::
   :::column span="2":::
      在 " **源** " 面板中，"专用类" 字段现已正确语法突出显示和打印。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      [Nullish 合并运算符][V8DevNullishCoalescing]的语法突出显示
   :::column-end:::
   :::column span="2":::
      DevTools 现已正确打印 " **源** " 面板中的 nullish 合并运算符。  
   :::column-end:::
:::row-end:::  

Chromium 问题 [#1073903][CR1073903]、 [#1083214][CR1083214] [#1083797][CR1083797]  

### 清单窗格中的新应用程序快捷方式警告  

**应用快捷方式** 可帮助用户在 web 应用中快速启动常见或建议的任务。  

<!--todo: add App shortcuts when section is live  -->  

**清单**窗格现在显示以下条件的警告。  

* 应用快捷方式图标小于96x96 像素  
* 应用快捷方式图标和清单图标不是方形 \ (，因为图标被忽略 \ )   

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   应用快捷方式警告  
:::image-end:::  

Chromium 问题 [#955497][CR955497]  

### 显示计算窗格的一致显示  

"**元素**" 面板中的**计算**窗格现在在所有视区大小中都以窗格的形式一致显示。  以前，当 DevTools 视口的宽度很窄时，将在 "**样式**" 窗格内合并**计算**窗格。  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/computed-pane.msft.png":::
   即使 DevTools 较窄， **计算** 窗格也会始终显示为单独的窗格。
:::image-end:::  

Chromium 问题 [#1073899][CR1073899]  

### WebAssembly 文件的字节码偏移量  

DevTools 现在使用字节码偏移来显示 Wasm 反汇编的行号。  
行号使你查看二进制数据更加清晰，并且更符合 Wasm 运行时引用位置的方式。  

Chromium 问题 [#1071432][CR1071432]  

### "源" 面板中的行式复制和剪切  

在 " [源" 面板编辑器][DevtoolsSourcesEditCssJavascript]中执行 "无选择时复制" 或 "剪切" 时，DevTools 将复制或剪切当前内容行。  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   将光标放在第5行的末尾，将 DevTools 中的整 **pen.js** 行复制到 [Visual Studio 代码][VSCode]中的 "" 和 "粘贴" 中。
:::image-end:::  

Chromium 问题 [#800028][CR800028]

### 控制台设置更新  

#### 取消组合相同的控制台消息  

在控制台设置中， **组类似** 的切换现在适用于重复邮件。  以前它刚刚应用到类似的消息。  

例如，以前，DevTools `hello` 即使未选中 " **组相似** "，也不会对邮件取消分组。  现在， `hello` 邮件已取消分组。  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   取消选中 " **组相似** " 时， `hello` 邮件将取消分组
:::image-end:::  

使用 [将重复消息发送到控制台的示例，][CodepenZoherghadyaliZyrjgdJ]为此功能提供一次尝试。  

Chromium 问题 [#1082963][CR1082963]  

### 保留所选仅限上下文设置  

" **仅** 在控制台设置中选择的上下文" 设置现在保持。  以前，每次您关闭并重新打开 DevTools 时，设置都将重置。  该更改使设置行为与其他控制台设置选项一致。  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/selected-context.msft.png":::
   **仅限所选上下文** 设置  
:::image-end:::  

Chromium 问题 [#1055875][CR1055875]  

### 性能面板更新  

#### 性能面板中的 JavaScript 编译缓存信息  

[JavaScript 编译缓存信息][V8DevCodeCaching] 现在始终显示在 "性能" 面板的 "摘要" 选项卡中。  以前，如果代码缓存未发生，DevTools 不会显示与代码缓存相关的任何内容。  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   JavaScript 编译缓存信息  
:::image-end:::  

Chromium 问题 [#912581][CR912581]  

#### "性能" 面板中的导航计时对齐方式  

" **性能** " 面板，用于根据录制开始时在标尺中显示时间。  对于用户导航的录制，计时现在已更改，其中 DevTools 现在显示相对于导航的标尺时间。  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/nav-timing.msft.png":::
   对齐 **性能** 面板中的导航计时  
:::image-end:::  

`DOMContentLoaded`第一次绘制、第一个 Contentful 画图和最大 Contentful 绘制事件的时间将更新为相对于导航的开始，这意味着计时计时与所报告的计时相匹配 `PerformanceObserver` 。  

Chromium 问题 [#974550][CR974550]  

### 用于断点、条件断点和 logpoints 的新图标  

" **源** " 面板具有新的断点、条件断点和 logpoints 设计。  断点通过红色圆圈表示，就像 [Visual Studio 代码][VSCode] 和 [visual studio][VS]一样。  添加图标以区分条件断点和 logpoints。  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="实验性功能" lightbox="../../media/2020/06/breakpoints.msft.png":::
   断点  
:::image-end:::  

Chromium 问题 [#1041830][CR1041830]  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义 Microsoft Edge DevTools |Microsoft 文档"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实验功能-实验功能 |Microsoft 文档"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "编辑 CSS 和 JavaScript-源代码面板概述 |Microsoft 文档"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动-在 Microsoft Edge DevTools 中检查网络活动 |Microsoft 文档"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "对 JS CSS 中的 CSS 进行样式编辑 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "将重复邮件发送到控制台 |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS 网格 planner 示例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium bug"  
[CR800028]: https://crbug.com/800028 "在 Chrome 更新后，开发工具编辑器中的 "复制行" 快捷方式不起作用 |Chromium bug"  
[CR912581]: https://crbug.com/912581 "在 DevTools/关于跟踪中公开由 V8 缓存的脚本代码：跟踪 |Chromium bug"  
[CR946975]: https://crbug.com/946975 "DevTools 样式侧栏不适用于构造的样式表 |Chromium bug"  
[CR955497]: https://crbug.com/955497 "适用于 PWAs | 的应用图标快捷菜单Chromium bug"  
[CR974550]: https://crbug.com/974550 "性能面板和 performanceObserver | 之间的跃点数不匹配Chromium bug"  
[CR1041830]: https://crbug.com/1041830 "改善断点的颜色 |Chromium bug"  
[CR1055875]: https://crbug.com/1055875 "在关闭并重新打开开发人员工具 | 后，所选 "仅限上下文" 控制台设置的值不会保留。Chromium bug"  
[CR1066579]: https://crbug.com/1066579 "DevTools：在 "网络" 面板中显示 ServiceWorkers 每个请求的提取时间线 |Chromium bug"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic 开发人员体验 |Chromium bug"  
[CR1073899]: https://crbug.com/1073899 ""计算样式" 选项卡在 "响应模式" 中消失 |Chromium bug"  
[CR1073903]: https://crbug.com/1073903 "DevTools：语法突出显示不能处理私有字段 |Chromium bug"  
[CR1082963]: https://crbug.com/1082963 "无法禁用控制台的 "分组类似消息" 行为 |Chromium bug"  
[CR1083214]: https://crbug.com/1083214 "acorn 不支持可选的链接 |Chromium bug"  
[CR1083797]: https://crbug.com/1083797 "Nullish 合并的整齐打印中断 |Chromium bug"  
[CR1096008]: https://crbug.com/1096008 "删除 FMP |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/表格工具 |Chromium bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播合成网络请求的工具 |Chromium bug"  
[CR1070378]: https://crbug.com/1070378 "将 webhint 集成到 DevTools |Chromium bug"  
[CR1069404]: https://crbug.com/1069404 "[开发工具] 小组件弹出组件太窄 |Chromium bug"  
[CR897944]: https://crbug.com/897944 "可拖动的 devtool 面板 |Chromium bug"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v 6.0.0-GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "使用影子 DOM |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge 预览频道"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio 代码"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS 对象模型 (CSSOM) |W3C CSS 工作组编辑器草稿"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "私有类字段-公共和私有类字段 |V8.开发"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "适用于 JavaScript 开发人员的代码缓存 |V8.开发"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 合并 |V8.开发"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "可选链接 |V8.开发"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "Constructable 样式表对象 |Web Incubator CG"

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
> 原始页面可在 [此处](https://developers.google.com/web/updates/2020/06/devtools/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
