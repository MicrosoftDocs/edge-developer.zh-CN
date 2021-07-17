---
description: "\"更多工具\"按钮、开始使用 DevTools 扩展的上下文内文档、控制台中增加了对屏幕阅读器的支持等。"
title: 'DevTools (Microsoft Edge 92) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 09e1438ae7fd6547a7dd14757f54f370c9008773
ms.sourcegitcommit: 1dd6376784c394087fe2938acaa069212cf7656e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "11659426"
---
# <a name="whats-new-in-devtools-microsoft-edge-92"></a>DevTools 92 (Microsoft Edge中的新增) 

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]

> [!TIP]
> **Microsoft Build 2021**会议于 5 月 25-27 日召开。  下面是 Build 中有关 DevTools 更新的视频[：Microsoft Edge |平台状态][YoutubeEdgeStateOfThePlatform]- Microsoft Edge为开发人员提供了一个极具吸引力且一致的平台。  随着旧版浏览器逐步退出支持，Edge 即将成为 Microsoft 在 Windows 10 上唯一受支持的浏览器。  加入我们，了解边缘平台、工具和 Web 应用的最新信息。


## <a name="the-close-button-is-no-longer-hidden-when-devtools-is-narrow"></a>当 DevTools 较窄时，不再隐藏"关闭"按钮

<!-- Title: DevTools is now easier to close -->
<!-- Subtitle: The Close button in DevTools is always displayed, even when DevTools is docked to the right and the DevTools viewport is narrow. -->

在 Microsoft Edge版本 91 或更早版本中，**** 当 DevTools 视口较窄时，不显示关闭 DevTools 的"关闭"按钮。  在 Microsoft Edge版本 92 中，**** 无论 DevTools 视口宽度如何，DevTools 中的"关闭"按钮始终存在。

:::image type="complex" source="../../media/2021/05/close-devtools-button-always-displayed.msft.png" alt-text="即使视区较窄，现在也显示"关闭 DevTools"按钮" lightbox="../../media/2021/05/close-devtools-button-always-displayed.msft.png":::
   即使 **视** 区较窄，现在也显示"关闭 DevTools"按钮
:::image-end:::


## <a name="add-tools-quickly-with-the-new-more-tools-button"></a>使用新的"更多工具"按钮快速添加工具

<!-- Title: Add tools quickly with the new More Tools button -->
<!-- Subtitle: Learn about a new convenient way to open tools in Microsoft Edge DevTools. -->

有一种在 DevTools 中打开更多工具的Microsoft Edge："更多工具**** `+` () 菜单。 " **更多工具** "菜单显示在主面板中的工具栏和箱的工具栏上。 从"更多工具 **"菜单中选择** 工具会将该工具添加到工具栏。

若要对任一工具栏上的选项卡重新排序，请选择并拖动选项卡。

"**更多工具**"菜单作为实验在 Microsoft Edge 89 中可用，现在始终存在。

:::image type="complex" source="../../media/2021/05/more-tools-button.msft.png" alt-text="上方工具栏和"箱"工具栏上的"更多工具"按钮" lightbox="../../media/2021/05/more-tools-button.msft.png":::
   上方 **工具栏和** "箱"工具栏上的"更多工具"按钮
:::image-end:::

:::image type="complex" source="../../media/2021/05/more-tools-menu.msft.png" alt-text=""更多工具"菜单" lightbox="../../media/2021/05/more-tools-menu.msft.png":::
   " **更多工具"** 菜单
:::image-end:::


## <a name="improvements-for-hovering-selecting-and-closing-tools"></a>悬停、选择和关闭工具的改进

<!-- Title: Improvements to tab interactions -->
<!-- Subtitle: Interactions related to hovering, selecting, and closing tools are more predictable. -->

已重新格式化每个工具的选项卡，以减少意外关闭工具的可能性。  在主工具栏和箱的工具栏的每个选项卡上，我们添加了：
*  选项卡周围的间距。
*  选项卡中关闭 `x` () 按钮的间距。
*  将鼠标悬停在选项卡上时的背景颜色。
*  用于关闭选项卡 () `x` 按钮的工具提示。
*  选项卡的关闭 `x` () 按钮的较高对比度。

例如，当你在"性能"工具**** 中，将鼠标悬停在"**** 网络"工具的选项卡上时，这些改进有助于防止意外关闭 **"网络"** 工具。

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-before.msft.png" alt-text="重新格式化前的选项卡" lightbox="../../media/2021/05/hovering-on-tool-tab-before.msft.png":::
           重新格式化前的选项卡 :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-after.msft.png" alt-text="重新格式化后的选项卡" lightbox="../../media/2021/05/hovering-on-tool-tab-after.msft.png":::
           重新格式化后的选项卡 :::image-end:::
    :::column-end:::
:::row-end:::

这些改进对于本地化 DevTools 的用户尤其相关，在这些用户中，选项卡可能更窄且更容易意外关闭。

:::image type="complex" source="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png" alt-text="具有窄选项卡的本地化 DevTools" lightbox="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png":::
   具有窄选项卡的本地化 DevTools
:::image-end:::

我们还通过向主工具栏和收银机工具栏添加"更多工具"菜单，[](#add-tools-quickly-with-the-new-more-tools-button)更轻松地重新添加关闭的工具。


## <a name="better-support-for-screen-readers-in-the-console"></a>在控制台中更好地支持屏幕阅读器

<!-- Title: Better screen reader support in the Console -->
<!-- Subtitle: Assistive technologies can now announce autocomplete suggestions and evaluated expressions in the Console. -->

在Microsoft Edge版本 92 之前，在**控制台**中，屏幕阅读器等辅助技术未宣布自动完成建议或已评估表达式的结果。 This has been fixed now.

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png" alt-text="在控制台中，屏幕阅读器现在宣布当前选择的自动完成建议" lightbox="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png":::
           在 **控制台中**，屏幕阅读器现在宣布当前选择的自动完成建议 :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png" alt-text="在控制台中，屏幕阅读器现在宣布计算表达式的结果" lightbox="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png":::
           在 **控制台中**，屏幕阅读器现在宣布计算表达式的结果 :::image-end:::
    :::column-end:::
:::row-end:::


## <a name="source-order-viewer"></a>源订单查看器

<!--  Title: Source Order Viewer -->
<!--  Subtitle: The new Source Order Viewer displays numbers on the webpage indicating the order of page elements in the source file, independently of how the page sections are positioned by CSS. -->

现在，您可以查看呈现网页上覆盖的源元素的顺序，以便进行更好的辅助功能检查。

HTML 文档中的内容顺序对于搜索引擎优化和辅助功能非常重要。  CSS 允许开发人员创建在屏幕上看起来与 HTML 源文档中的顺序不同的内容。  这是一个辅助功能问题，因为屏幕阅读器用户可能会获得令人困惑的体验。

:::image type="complex" source="../../media/2021/05/source-order-viewer.msft.png" alt-text="激活源顺序查看器将源中的元素顺序作为页面上的覆盖显示" lightbox="../../media/2021/05/source-order-viewer.msft.png":::
   激活源 **顺序查看器** 将源中的元素顺序作为页面上的覆盖显示
:::image-end:::

有关详细信息，请导航到使用 [源订单查看器测试键盘支持](../../../accessibility/test-tab-key-source-order-viewer.md)。

若要在开放源代码项目中查看此功能Chromium历史记录，请导航到"问题[1094406"。][CR1094406]


## <a name="user-agent-client-hints-for-devices-in-the-network-conditions-tab"></a>User-Agent条件选项卡中的设备提示客户端提示

<!--  Title: User-Agent Client Hints -->
<!--  Subtitle: Access information about a user's browser in an ergonomic way that preserves privacy. -->

User-Agent客户端提示现在适用于"网络条件"工具中"用户 **代理** " **字段中** 的设备。  User-Agent客户端提示是客户端提示 API 的一个新扩展，它使你能够以一种保留隐私的轻松方式访问有关用户浏览器的信息。

:::image type="complex" source="../../media/2021/05/user-agent.msft.png" alt-text="用户代理" lightbox="../../media/2021/05/user-agent.msft.png":::
   用户代理
:::image-end:::

有关详细信息，请导航到["用户代理客户端提示"。](../../../../web-platform/user-agent-guidance.md#user-agent-client-hints)

若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1174299"。][CR1174299]


## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-118"></a>Microsoft Edge开发人员工具Visual Studio Code 1.1.8 版

适用于[Microsoft Edge Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] Visual Studio Code 1.1.8 Microsoft Visual Studio开发人员工具自上一版本起发生了以下更改。  Microsoft Visual Studio Code 会自动更新扩展。  若要手动更新到版本 1.1.8，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]

可以在[vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools]存储库上提交问题并GitHub扩展。

### <a name="in-context-documentation-and-ui-to-make-it-easier-to-use-the-devtools-extension"></a>上下文内文档和 UI，以便更轻松地使用 DevTools 扩展

<!-- Title: In-context documentation and UI make it easier to get started using the Developer Tools extension -->
<!-- Subtitle: The Microsoft Edge Developer Tools for Visual Studio Code extension now presents helpful text, buttons, and links, and opens a documentation page with guidance on how to get started. -->

Microsoft Edge 开发人员工具[for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]扩展的版本 1.1.8 现在提供了一种更简单的方式来启动 Microsoft Edge 的新实例，提供说明、按钮、链接和文档页来指导您。

*  选择 Visual Studio Code 的活动**栏中**的"Microsoft Edge 工具"**** 按钮时 **，Microsoft Edge**工具： 目标面板现在会提供说明性文本、按钮和链接来指导你，而不是空白面板。

*  当您从 Microsoft Edge 中打开 Visual Studio Code 的新实例时，Microsoft Edge将显示一个介绍如何使用开发人员工具扩展的起始页，而不是空白页。

*  the **Microsoft Edge Tools： Targets panel** now has a Generate launch.js**on** button and instructions， to help launch your project for debugging in Microsoft Edge.

有关详细信息，请导航到["使用工具"。][GithubIoDevToolsUsing]


## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]


### <a name="css-grid-editor"></a>CSS 网格编辑器

现在，您可以使用新的 CSS 网格编辑器预览和创作 CSS 网格布局。

如果页面上的 HTML 元素已应用或已应用，"样式"选项卡中旁边会显示一个网格图标。单击网格图标可显示或隐藏 `display: grid` `display: inline-grid` CSS 网格编辑器。 **** 在 CSS 网格编辑器中，选择 (图标，) 以预览呈现 `justify-content: space-around` 页面中的布局。  弹性布局的工作方式类似。

:::image type="complex" source="../../media/2021/05/css-grid-editor.msft.png" alt-text="CSS 网格编辑器" lightbox="../../media/2021/05/css-grid-editor.msft.png":::
   CSS 网格编辑器
:::image-end:::

<!-- screenshot uses https://jec.fyi -->

若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1203241"。][CR1203241]


### <a name="support-for-const-redeclarations-in-the-console"></a>控制台中对 const 重新声明的支持

控制台现在支持在单独的 REPL 脚本中重新声明变量 (例如，除了现有和重新声明之外，还支持在控制台) 中运行语句 `const` `let` `class` 。  此支持允许你对变量进行不同的声明试验 `const` ，而无需刷新页面。  以前，如果重新声明绑定，DevTools 会抛出语法 `const` 错误。

请参阅下面的示例。 `const` redeclaration is supported across separate REPL scripts (refer to variable `a`) .  请注意，以下方案在设计上不受支持：

*  `const` REPL 脚本中不允许重新声明页面脚本。
*  `const` 不允许在同一 REPL 脚本中重新声明， (引用变量 `b`) 。

:::image type="complex" source="../../media/2021/05/support-for-const-redeclaration.msft.png" alt-text="控制台中允许重新声明 const 变量" lightbox="../../media/2021/05/support-for-const-redeclaration.msft.png":::
   控制台中允许重新声明 const 变量
:::image-end:::

若要了解如何运行单个 REPL 脚本或多行 REPL 脚本，请导航到作为 [JavaScript 环境的](../../../console/console-javascript.md)控制台。
    
若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1076427"。][CR1076427]


### <a name="new-shortcut-to-view-iframe-details"></a>查看 iframe 详细信息的新快捷方式

若要快速查看详细信息，现在可以右键单击"元素"工具中的元素， `iframe` `iframe` 然后选择"显示**iframe 详细信息"。** ****

:::image type="complex" source="../../media/2021/05/show-iframe-details.msft.png" alt-text="iframe 详细信息视图" lightbox="../../media/2021/05/show-iframe-details.msft.png":::
   iframe 详细信息视图
:::image-end:::

这将在应用程序工具 `iframe` 中显示有关 **的详细信息** 。  在 **应用程序工具** 中，可以检查文档详细信息、安全和隔离状态、权限策略等，以调试潜在问题。

:::image type="complex" source="../../media/2021/05/show-iframe-details-application-tool.msft.png" alt-text="应用程序工具中的帧详细信息" lightbox="../../media/2021/05/show-iframe-details-application-tool.msft.png":::
   应用程序工具中的 **帧** 详细信息
:::image-end:::

<!-- demo page: https://wolfib.github.io/web-demos/ esp https://wolfib.github.io/web-demos/jsIframe.html -->

若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1192084"。][CR1192084]


### <a name="enhanced-cors-debugging-support"></a>增强的 CORS 调试支持

跨源资源共享 (CORS) 错误现在在"问题"选项卡 **中** 显示。 CORS 错误的潜在原因有很多。  单击展开每个问题以了解潜在原因和解决方案。

:::image type="complex" source="../../media/2021/05/cors-debugging-support.msft.png" alt-text=""问题"选项卡中的 CORS 问题" lightbox="../../media/2021/05/cors-debugging-support.msft.png":::
   "问题"选项卡中的 CORS 问题
:::image-end:::

<!-- screenshot uses http://cors-errors.glitch.me -->

若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1141824"。][CR1141824]


### <a name="renamed-xhr-filter-to-fetchxhr"></a>将 XHR 筛选器重命名为 Fetch\/XHR

在 **网络工具** 中 **，XHR** 筛选器现在重命名为 **Fetch/XHR**。 此更改使此筛选器包括 和 `XMLHttpRequest` API `Fetch` 网络请求更加清晰。

:::image type="complex" source="../../media/2021/05/fetch-xhr.msft.png" alt-text="网络工具现在显示 Fetch/XHR 而不是 XHR" lightbox="../../media/2021/05/fetch-xhr.msft.png":::
   网络 **工具** 现在显示 **Fetch/XHR** 而不是 **XHR**
:::image-end:::

有关详细信息，请导航到：
*  [XMLHttpRequest 规范][XhrSpecWhatwgOrg]
*  [Fetch spec][FetchSpecWhatwgOrg]

若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1201398"。][CR1201398]


### <a name="filter-wasm-resource-type-in-the-network-tool"></a>网络工具中的 Filter Wasm 资源类型

在 **"网络** "工具中，现在可以选择新的 **Wasm** 筛选器来筛选 WebAssembly 网络请求。

:::image type="complex" source="../../media/2021/05/wasm-network-requests.msft.png" alt-text="按 Wasm 筛选" lightbox="../../media/2021/05/wasm-network-requests.msft.png":::
   按 Wasm 筛选
:::image-end:::

<!-- screenshot uses http://memory-inspector.glitch.me/demo-wasm.html -->

若要在开放源代码项目中查看此功能Chromium历史记录，请导航到"问题[1103638"。][CR1103638]


### <a name="compute-intersections-are-now-included-in-the-performance-tool"></a>计算交集现在包含在性能工具中

在性能 **工具** 中，DevTools **现在在** 图表上显示计算交集。 这些更改可帮助你识别交集项事件并调试交集器的潜在性能开销。

:::image type="complex" source="../../media/2021/05/compute-intersections-in-perf-tool.msft.png" alt-text="性能工具中的计算交集" lightbox="../../media/2021/05/compute-intersections-in-perf-tool.msft.png":::
   性能工具中的 **计算** 交集
:::image-end:::

<!-- screenshot uses https://googlechrome.github.io/samples/intersectionobserver -->

若要详细了解交集器，请导航到" [信任"，观察效果更好：Intersection Intersection v2][WebDevIntersectionObserverV2]。  有关使用饼图的信息，请导航到"[分析性能记录"。][DevtoolsEvaluatePerfRefAnalyzeAPerfRecording]  若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1199137"。][CR1199137]


## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。


## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]


<!-- links -->
[DevtoolsEvaluatePerfRefAnalyzeAPerfRecording]: ../../../evaluate-performance/reference.md#analyze-a-performance-recording "分析性能记录|Microsoft Docs"
<!-- external links -->
[XhrSpecWhatwgOrg]: https://xhr.spec.whatwg.org "XMLHttpRequest 规范|WHATWG"
[FetchSpecWhatwgOrg]: https://fetch.spec.whatwg.org "提取规格|WHATWG"

[WebDevIntersectionObserverV2]: https://web.dev/intersectionobserver-v2 "信任更好，观察效果更好：Intersection Intersection v2 |web.dev"

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"
[GithubIoDevToolsUsing]: https://microsoft.github.io/vscode-edge-devtools/using.html "使用工具|GitHub"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge开发人员工具Visual Studio Code |Visual StudioMarketplace"

[YoutubeEdgeStateOfThePlatform]: https://www.youtube.com/watch?v=sU0WRZ0kkNo "Microsoft Edge：平台服务|YouTube"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"
[CR1094406]: https://crbug.com/1094406 "问题1094406：开发人员希望源订单查看器|Chromium Bug"
[CR1174299]: https://crbug.com/1174299 "问题1174299：通过 Chrome DevTools 的&quot;网络条件&quot;选项卡更改 UA 字符串时丢弃的 UA 客户端|Chromium Bug"
[CR1203241]: https://crbug.com/1203241 "问题1203241：CSS 网格编辑器|Chromium Bug"
[CR1076427]: https://crbug.com/1076427 "问题1076427：DevTools 控制台应支持 const 重新声明|Chromium Bug"
[CR1192084]: https://crbug.com/1192084 "问题1192084：将&quot;显示帧详细信息&quot;右键单击选项添加到元素视图视图的 iframe /html |Chromium Bug"
[CR1141824]: https://crbug.com/1141824 "问题 1141824：改进 DevTools 中的 CORS 错误报告 | Chromium 漏洞"
[CR1201398]: https://crbug.com/1201398 "问题1201398：功能请求：在网络面板中重命名 XHR 类型|Chromium Bug"
[CR1103638]: https://crbug.com/1103638 "问题1103638：用于显示 WebAssembly 资源网络|Chromium Bug"
[CR1199137]: https://crbug.com/1199137 "问题1199137：在 perf 面板中显示 IntersectionObserver |Chromium Bug"

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。
> 原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-xx)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。

[ ![ Creative Commons License][CCby4Image]][CCA4IL] This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].

[CCA4IL]: https://creativecommons.org/licenses/by/4.0
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen
