---
description: 波浪下划线突出显示元素工具、服务工作者更新时间线等中的代码问题。
title: 'DevTools (Microsoft Edge 91 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 69fcd29f9b4cae9ec290798b767fbe54793cb2fd
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624778"
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
# <a name="whats-new-in-devtools-microsoft-edge-91"></a>DevTools (Microsoft Edge 91 中的新增)   

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="wavy-underlines-highlight-code-issues-and-improvements-in-elements-tool"></a>波浪下划线突出显示元素工具中的代码问题和改进  

<!--  Title: Get code hints in Elements tool  -->  
<!--  Subtitle: Wavy underlines like the ones you see in Visual Studio Code now display in the Elements tool.  Underlines alert you to code issues related to accessibility, compatibility, security, performance, and  so on.  -->  

在大多数新式 ID 中，文本下的波浪下划线指示语法错误。   在 Microsoft Edge 91 或更高版本中，在"元素"工具的**DOM**视图中，HTML 下会显示**波浪下划线。**  波浪下划线表示与辅助功能、兼容性、性能等相关的代码问题和建议。  若要详细了解如何查看和编辑问题，请导航到使用问题工具查找和 [修复问题][DevtoolsIssuesIndex]。  

若要打开 **问题** 工具并了解有关该问题以及如何修复它，请完成以下操作之一。  

*   选择并按住 `Shift` ，然后选择任何波浪下划线。  
*   完成以下操作。  
    1.  悬停在任何波浪下划线上。  
    1.  打开上下文菜单\（右键单击\）。  
    1.  选择 **"在问题中显示"。**  
        
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues.msft.png" alt-text="在"元素"工具中选择带下划线的错误" lightbox="../../media/2021/04/elements-iframe-highlight-issues.msft.png":::
         在"元素"工具中选择 **带下划线** 的错误  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png" alt-text="在问题工具中显示错误详细信息" lightbox="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png":::
         在问题工具 **中显示错误** 详细信息  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a>通过信息丰富的工具提示了解 DevTools  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<!--  Title: Learn more about DevTools with DevTools Tooltips  -->  
<!--  Subtitle: Informative overlays are now available in the default DevTools interface.  -->  

DevTools 工具提示功能可帮助你了解 DevTools 中所有不同的工具和窗格。  若要关闭工具提示，请选择 `Esc` 。  若要打开工具提示，请完成以下操作之一。  

*   选择 `Ctrl` + `Shift` + `H` \ (Windows/Linux\) `Cmd` + `Shift` + `H` 或 \ (macOS\) 。  
*   [打开命令菜单，][DevtoolsCommandMenuIndexOpenCommandMenu] 然后键入 `tooltips` 。  
*   Choose **Customize and control DevTools** \ (`...` \) > **Help**Toggle the  >  **DevTools Tooltips**.  

此外，如果你打开焦点模式和 [DevTools][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] 工具提示实验，还可以选择活动栏底部的切换 **DevTools** 工具提示 \ (`?` \) **按钮**。  

若要显示有关如何使用 DevTools 的信息，请打开工具提示，然后将鼠标悬停在 DevTools 的每个大纲区域上。  

:::image type="complex" source="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png" alt-text="将鼠标悬停在"问题"工具突出显示区域中的任何位置，以显示更多详细信息" lightbox="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png":::
   将鼠标悬停在"问题"工具突出显示区域 **中的任何位置，** 以显示更多详细信息  
:::image-end:::  

## <a name="service-worker-update-timeline"></a>服务工作者更新时间线  

<!--todo:  Update the linked [Service Worker improvements][DevtoolsServiceWorkerIndex] article.  -->  

<!--  Title: The tasks associated with your Service Worker  -->  
<!--  Subtitle: Debug with Service Worker Update Cycle  -->  

在 Microsoft Edge 91 或更高版本中，如果您是渐进式 Web 应用开发人员或服务工作者开发人员，则使用 Application 工具将服务工作者的更新生命周期显示为**时间线**。  此功能可帮助您了解服务工作者在下列每个阶段所花的时间。  

*   **安装**  
*   **Wait**  
*   **激活**  
    
:::image type="complex" source="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png" alt-text="查看服务工作者的更新周期中的时间线" lightbox="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png":::
   查看 **服务** 工作者 **的更新周期** 中的时间线  
:::image-end:::  

有关服务工作者的生命周期详细信息，请导航到"服务工作[线程生命周期"。][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]  有关在 DevTools 中为渐进式 Web 应用和服务工作者调试工具的信息，请导航到"[服务工作器改进"。][DevtoolsServiceWorkerIndex]  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1066604"。][CR1066604]  

## <a name="progressive-web-apps-no-longer-display-warnings-for-non-square-icons"></a>渐进式 Web 应用不再显示非方形图标的警告  

<!--  Title: Non-square icons in app manifest no longer produce warnings  -->  
<!--  Subtitle: As long as square icons are included in the app manifest, non-square icons no longer produce warnings  -->  

在[Microsoft Edge 版本 90][DevtoolsWhatsNew202102Devtools]或更早版本中，如果 PWA 的 Web App 清单包含非方形图标，则每个非方形图标**** 的"错误和警告"部分会显示警告。  在Microsoft Edge版本 91 或更高版本中，**** 如果至少提供一**** 个正方形图标，则应用程序工具中的清单部分不会显示警告。  如果未提供任何方形图标，则会显示一条警告消息。  

```output
Most operating systems require square icons.  Please include at least one square icon in the array.  
```  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png" alt-text="在 Microsoft Edge 版本 90 或更早版本中，对于非正方形的每个图标，将显示错误" lightbox="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png":::
         在 Microsoft Edge 版本 90 或更早版本中，对于非正方形的每个图标，将显示错误  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png" alt-text="在 Microsoft Edge 版本 91 或更高版本中，提供至少一个正方形图标时不会显示任何错误" lightbox="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png":::
         在 Microsoft Edge 版本 91 或更高版本中，提供至少一个正方形图标时不会显示任何错误  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

若要在 Web 应用程序清单中查看错误和警告，请导航到 **"应用程序"** 工具并选择"清单 **"** 部分。  错误和警告列在"错误和警告 **"** 标题下。  有关 Web 应用部件清单的信息，请导航到"使用 Web 应用清单"将 [渐进式 Web 应用集成到操作系统中][ProgressiveWebAppsWebappmanifests]。  若要创建要包括在 Web 应用清单中的图标，请导航到 [PWABuilder Image Generator][PwabuilderImagegenerator]。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题 "[1185945][CR1185945]。  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a>本地化的 DevTools 现在Chromium的浏览器中受支持  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

从 Microsoft Edge[版本 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]开始，Microsoft Edge开发人员工具以你自己的语言显示。  许多开发人员使用 StackOverflow 等其他开发人员工具，Visual Studio Code语言进行开发，而不只是使用英语。  开发人员Microsoft Edge、Chrome DevTools 团队和 Google Lighthouse 团队协作，在所有基于 Chromium 的浏览器中提供相同的体验。  若要详细了解如何在语言中使用 DevTools，请导航到"[更改 DevTools 语言设置"。][DevtoolsCustomizeLocalization]  有关开放源代码项目中有关此功能的协作Chromium，请导航到 [1136655][CR1136655]。  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edge浏览器和 DevTools 设置为日语" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   Microsoft Edge浏览器和 DevTools 设置为日语  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a>使用键盘导航到 CSS 变量  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

从[Microsoft Edge版本 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]开始，"**** 样式"窗格将显示 CSS 变量并提供指向每个变量的定义的链接。  在 Microsoft Edge 版本 91 或更高版本中，可以使用箭头键轻松导航到 CSS 变量。  若要在"样式 **"窗格中打开** 定义，请将鼠标悬停在变量上，然后选择 `Enter` 。  有关 CSS 变量详细信息，请导航到使用 CSS 自定义属性 ([变量) 。 ][MdnDocsWebCssUsingCssCustomProperties]  若要在开放源代码项目中查看此功能Chromium，请导航到"问题 "[1187735][CR1187735]。  

:::image type="complex" source="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png" alt-text="--theme-body-background CSS 变量在"样式"窗格中突出显示" lightbox="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png":::
   " `--theme-body-background` 样式"窗格中突出显示的**** CSS 变量  
:::image-end:::  

## <a name="issues-are-automatically-sorted-by-severity"></a>问题按严重性自动排序  

<!-- Title: Display Issues in severity order  -->  
<!-- Subtitle: Entries in the Issues tool now display in severity order and allow you to focus your updates on the most important issues. -->  

问题 **工具** 显示改进网站的建议，包括辅助功能、性能、安全性等。 根据你的反馈，现在会自动按严重性对问题进行排序。  在每个反馈类别中，每个标记为"错误"的问题**** 首先出现，然后关注标记为"警告"的每个**** 问题，然后每个标记为"提示"**的问题**。  为了帮助你优化问题，为将来的更新计划了额外的筛选器选项。  若要详细了解如何查看问题，请导航到使用 [问题工具查找和修复问题][DevtoolsIssuesIndex]。  

:::image type="complex" source="../../media/2021/04/elements-issues-ordered-issues.msft.png" alt-text=""问题"工具按严重性显示排序的问题" lightbox="../../media/2021/04/elements-issues-ordered-issues.msft.png":::
   " **问题** "工具按严重性显示排序的问题  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-117"></a>Microsoft Edge开发人员工具Visual Studio Code 1.1.7 版  

<!-- Title: Microsoft Edge DevTools for Visual Studio version 1.1.7  -->  
<!-- Subtitle: Increased target closure reliability, automatically update the side panel, new contextual menu for settings and Changelog, and more. -->  

Microsoft Edge [Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.7 提供了来自 Microsoft Edge 版本[88 的][DevtoolsWhatsNew202011Devtools]DevTools。  此扩展现在ARM设备，不再依赖调试器[进行Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge]扩展。  版本 1.1.7 包括以下 Bug 修复和改进。  

*   更新了目标关闭的可靠性。  
*   更新了侧面板，以在调试创建或销毁的目标时自动刷新。  
*   添加了一个新的上下文菜单，可让你更快地访问扩展设置和最新的 Changelog。  
*   更新并简化了扩展文档（包括最新功能）的发布。  
    
若要手动更新到版本 1.1.7，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]  你可以在 [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools] 上提交问题并参与提升扩展。  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="visualize-css-scroll-snap"></a>可视化 CSS 滚动贴靠  

现在，可以在"元素 `scroll-snap` "工具中**** 切换锁屏提醒，以检查 CSS 滚动对齐方式。  当网页上的 HTML 元素应用于该元素时，会在"元素"工具中旁边 `scroll-snap-type` `scroll-snap` **显示锁** 屏提醒。  选择锁屏提醒以在网页上 (或关闭\) 滚动贴贴显示。  To review an example webpage， navigate to [Scroll Snap Demo][GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml].  在示例中，点显示在对齐边缘上。  滚动端口具有纯色轮廓，而贴靠项具有短划线轮廓。  滚动填充填充为绿色，而滚动边距填充为橙色。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[862450"。][CR862450]  

:::image type="complex" source="../../media/2021/04/elements-scroll-snap-highlight.msft.png" alt-text="CSS 滚动对齐" lightbox="../../media/2021/04/elements-scroll-snap-highlight.msft.png":::
   CSS 滚动对齐  
:::image-end:::  

### <a name="new-memory-inspector-tool"></a>新内存检查器工具  

使用新的 **内存检查器** 工具检查 `ArrayBuffer` JavaScript 和 Wasm 内存中的 。  打开 [JS 演示网页中的][GlitchMemoryInspectorDemoJsHtml] 内存。  在 **"源** "工具中， `memory-write-wasm` 打开文件，在行 处设置断点 `0x03c` 。  刷新网页。  展开调试 **器** 窗格中的"范围"部分。  新图标显示在缓冲区值 **旁边** 。  选择它以打开新的 **内存检查器** 工具。  

若要了解有关"源"工具中的调试 **的详细信息** ，请导航到"使用调试器"窗格 [调试 JavaScript 代码][DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode]。  若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1166577][CR1166577]。  

:::image type="complex" source="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png" alt-text="内存检查器工具" lightbox="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png":::
   **内存检查器** 工具  
:::image-end:::  

### <a name="new-badge-settings-pane-in-the-elements-tool"></a>"元素"工具中的"新建锁屏提醒设置"窗格  

现在，使用"元素 **"** 工具中的**** 锁屏提醒设置打开 \ (或 off\) 单个锁屏提醒。  使用此功能在检查网页时自定义重要锁屏提醒并专注于重要锁屏提醒。  若要在"元素"工具顶部显示 **锁屏提醒** 设置窗格，请完成以下操作。  

1.  将鼠标悬停在任何元素上。  
1.  打开上下文菜单\（右键单击\）。  
1.  选择**锁屏提醒设置...**  
    
若要显示 \ (或隐藏\) 锁屏提醒，请选择 "\ ("或删除) 锁屏提醒名称旁边的复选框。  

<!--  To review the history of this feature in the Chromium open-source project, navigate to Issue [1066772][CR1066772].  -->  

:::image type="complex" source="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png" alt-text=""元素"工具中的锁屏提醒设置窗格" lightbox="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png":::
   **"元素"** 工具中的锁屏提醒 **设置** 窗格  
:::image-end:::  

### <a name="enhanced-image-preview-with-aspect-ratio-information"></a>具有纵横比信息的增强图像预览  

DevTools 中的图像预览已增强，可显示更多信息，包括以下详细信息。  

*   呈现的大小  
*   呈现的纵横比  
*   固有大小  
*   固有纵横比  
*   文件大小  
    
该信息可帮助你更好地了解图像和应用优化。  当你选择图像预览时，网络工具中也**** 提供图像纵横比信息。  

:::row:::
   :::column span="":::
      在 **"元素** "工具中，图像预览现在显示有关图像的详细信息。  
   :::column-end:::
   :::column span="":::
      此外，当你选择图像预览时，网络工具中**** 还会提供图像纵横比信息。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png" alt-text="元素工具中的纵横比信息的图像预览" lightbox="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png":::
         元素工具中的纵横比信息 **的图像** 预览  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/network-img-name-filters-preview.msft.png" alt-text="网络工具中的图像纵横比信息" lightbox="../../media/2021/04/network-img-name-filters-preview.msft.png":::
         网络工具中的图像纵 **横比** 信息  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1149832][CR1149832]和 [1170656][CR1170656]。  

### <a name="new-options-to-configure-content-encodings-in-the-network-conditions-tool"></a>在网络条件工具中配置内容编码的新选项 

在 **"网络**"工具中，选择"限制"下拉菜单旁边的"更多网络**** 条件 **..."** 按钮以打开 **"网络条件"** 工具。  若要测试服务器响应是否针对不支持[gzip、brotli][GnuSoftwareGzipManual]或其他将来的浏览器进行了正确编码[][|::ref1::|Main]，请完成 `Content-Encoding` 以下操作。  

1.  打开 **"网络条件"** 工具
1.  导航到 **接受的内容编码**。 
1.  删除要测试的 `Content-Encoding` 旁边的复选框。  
    
若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1162042][CR1162042]。  

:::image type="complex" source="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png" alt-text="新增更多网络条件...按钮将打开"网络条件"工具以配置内容编码" lightbox="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png":::
   新建 **更多网络条件...** 按钮将打开 **网络条件** 工具进行配置 `Content-Encoding`  
:::image-end:::  

### <a name="styles-pane-enhancements"></a>样式窗格增强功能  

#### <a name="new-shortcut-to-display-computed-value-in-the-styles-pane"></a>在"样式"窗格中显示计算值的新快捷方式  

现在，若要在"样式"窗格中显示计算出的 CSS **值，** 请完成以下操作。  

1.  将鼠标悬停在 CSS 属性上。  
1.  打开上下文菜单\（右键单击\）。  
1.  选择 **"查看计算值"。**  
    
若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1076198][CR1076198]。  

:::image type="complex" source="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png" alt-text="显示计算值的新快捷方式" lightbox="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png":::
   显示计算值的新快捷方式  
:::image-end:::  

#### <a name="support-for-the-accent-color-keyword"></a>支持主题色关键字  

"样式"窗格的自动完成**** UI 现在检测到 CSS 关键字，这允许您指定元素生成的 `accent-color` UI 控件的强调文字颜色。  元素生成的 UI 控件示例包括复选框或单选按钮。 有关实现实现状态Chromium导航到[功能：主题色 CSS 属性][ChromestatusFeature4752739957473280]。  若要启用此功能，请导航到 `edge://flags#enable-experimental-web-platform-features` ，将复选框设置为 **已启用**。  若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1092093][CR1092093]。  

:::image type="complex" source="../../media/2021/04/elements-styles-accent-color.msft.png" alt-text="强调文字颜色 CSS 关键字" lightbox="../../media/2021/04/elements-styles-accent-color.msft.png":::
   `accent-color` CSS 关键字
:::image-end:::  

### <a name="display-details-about-blocked-features-in-the-frame-details-view"></a>在"框架详细信息"视图中显示有关阻止的功能的详细信息  

权限策略是一个 Web 平台 API，它使网站能够允许或阻止在单个框架或它所嵌入的 `iframe` 中使用浏览器功能。 有关详细信息，请导航到["权限策略解释器"。][GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]  若要显示有关阻止功能的原因的详细信息，请完成以下操作。  

1.  导航到 [OOPIF 权限策略][GlitchPermissionPolicyDemoMain]。  
1.  导航到 **应用程序** 工具。  
1.  选择一个帧。  
1.  导航到 **"权限策略"** 部分。  
1.  导航到 **Disabled Features** 属性。  
1.  选择 **"显示详细信息"。**  
1.  选择每个策略旁边的图标以导航到阻止该功能的 或 `iframe` 网络请求。  
    
若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1158827][CR1158827]。  

:::image type="complex" source="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png" alt-text="框架详细信息视图中阻止的功能" lightbox="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png":::
   框架详细信息视图中阻止的功能  
:::image-end:::  

### <a name="filter-experiments-in-the-experiments-setting"></a>在实验设置中筛选实验  

使用新的实验筛选器更快地查找实验。  例如，若要打开代码问题的新实验，请完成以下操作。
``

1.  导航到**设置**  >  **实验。**  
1.  导航到 **"筛选器** "文本框。  
1.  键入 `issues`。  
    
:::image type="complex" source="../../media/2021/04/settings-experiments-filter-by-issues.msft.png" alt-text="在实验设置中筛选实验" lightbox="../../media/2021/04/settings-experiments-filter-by-issues.msft.png":::
   在实验设置 **中筛选** 实验  
:::image-end:::  

### <a name="new-vary-header-column-in-the-cache-storage-pane"></a>"缓存"存储窗格中的"新建 Vary Header"列  

使用" `Vary Header` 缓存地址"窗格中**的新存储**显示["不同][HttpwgSpecsRfc7231HtmlHeaderVary]HTTP 响应头"值。  若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1186049][CR1186049]。  

:::image type="complex" source="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png" alt-text="Vary Header 列" lightbox="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png":::
   Vary Header 列  
:::image-end:::  

### <a name="sources-tool-improvements"></a>源工具改进  

#### <a name="support-for-new-javascript-features"></a>支持新的 JavaScript 功能  

DevTools 现在支持新的专用品牌检查，即#foo [javaScript][V8DevFeaturesPrivateBrandChecks] 语言功能。  专用品牌检查功能扩展了 [in 运算符][MdnDocsWebJavascriptReferenceOperatorsIn] ，以支持特定对象的 [Private][V8DevFeaturesClassFieldsPrivateClassFields] 类字段。  在控制台和**源工具****中试用**它。  此外，若要检查私有字段，请完成以下操作。  

1.  导航到 **调试器** 窗格。  
1.  导航到" **范围"** 部分。  
    
若要在开放源代码项目中查看此功能Chromium，请导航到"问题[11374"。][CR11374]  

:::image type="complex" source="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png" alt-text="JavaScript 专用品牌检查" lightbox="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png":::
   JavaScript 专用品牌检查  
:::image-end:::  

#### <a name="enhanced-support-for-breakpoints-debugging"></a>增强了对断点调试的支持  

Webpack 和[Rollup][RollupjsMain]等新式 JavaScript 捆绑程序支持代码拆分。 [][WebpackJsMain]  若要了解有关代码拆分的更多信息，请导航到"[代码拆分"。][JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules]  在 Microsoft Edge 90 或更早版本中，DevTools 仅在单个捆绑包中设置断点。  在 Microsoft Edge版本 91 或更高版本中，调试共享组件时，DevTools 会正确设置多个捆绑包中的断点。  若要在 Chromium 开放源代码项目中查看此功能的历史记录，请导航到问题 [1142705][CR1142705]、979000 和 [1180794][CR1180794]。 [][CR979000]  

#### <a name="support-hover-preview-with-bracket-notation"></a>使用方括号表示法支持悬停预览  

DevTools 现在支持在使用源工具中的表示法的 JavaScript 成员表达式上 `[]` 悬停预览。 ****  若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1178305][CR1178305]。  

:::image type="complex" source="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png" alt-text="使用 [] 表示法支持悬停预览" lightbox="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png":::
   使用表示法支持 `[]` 悬停预览  
:::image-end:::  

#### <a name="improved-outline-of-html-files"></a>改进了 HTML 文件的大纲  

DevTools 现在具有对文件的更好的大纲 `.html` 支持。  在 **"源** "工具中，打开 `.html` 文件。  若要打开 \ (或关闭\) 代码大纲，请在 `Ctrl` + `Shift` + `O` Windows/Linux 或 `Cmd` + `Shift` + `O` macOS 上选择。  在下图中，DevTools 现在正确列出了大纲中的所有函数。  以前，DevTools 只显示一些函数。  若要在开放源代码项目中查看此功能的历史记录，Chromium问题[761019][CR761019]和 [1191465][CR1191465]。  

:::image type="complex" source="../../media/2021/04/sources-page-jobobbx-at.msft.png" alt-text=" 改进了 HTML 文件的大纲" lightbox="../../media/2021/04/sources-page-jobobbx-at.msft.png":::
   改进了 HTML 文件的大纲  
:::image-end:::  

#### <a name="proper-error-stack-traces-for-wasm-debugging"></a>Wasm 调试的正确错误堆栈跟踪  

在 Microsoft Edge 90 或更早版本中，DevTools 仅在错误堆栈跟踪中显示常规 Wasm 引用。  在 Microsoft Edge 91 或更高版本中，DevTools 解析内联函数请求，并显示 Wasm 调试的错误堆栈跟踪中的源位置。  若要了解有关控制台中的错误堆栈跟踪的详细信息 **，请导航**到 [错误][DevtoolsConsoleApiError]。  

在 Microsoft Edge 91 或更高版本中，DevTools 解析内联函数请求并显示 Wasm 调试的正确错误堆栈跟踪。  

:::row:::
   :::column span="":::
      在Microsoft Edge版本 90 及更早版本中，源位置不会显示在错误堆栈跟踪中。  源位置包括 `dsquare` 。  
   :::column-end:::
   :::column span="":::
      在Microsoft Edge版本 91 及更高版本中，源位置显示在错误堆栈跟踪中。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png" alt-text="Wasm 调试以前的错误堆栈跟踪" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png":::
         Wasm 调试的正确错误堆栈跟踪  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png" alt-text="Wasm 调试的正确错误堆栈跟踪" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png":::
         Wasm 调试的正确错误堆栈跟踪  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1189161][CR1189161]。  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]: ../../2020/01/devtools.md#using-the-devtools-in-other-languages "以其他语言使用 DevTools - DevTools (Microsoft Edge 81) |Microsoft Docs"  
[DevtoolsWhatsNew202011Devtools]: ../../2020/11/devtools.md "DevTools (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]: ../../2020/11/devtools.md#css-variable-definitions-in-styles-pane "样式窗格中的 CSS 变量定义 - DevTools (Microsoft Edge 88 中的新增) |Microsoft Docs"  
[DevtoolsWhatsNew202102Devtools]: ../02/devtools.md "DevTools （Microsoft Edge 90） 中的新增功能|Microsoft Docs"  
[DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode]: ../02/devtools.md#group-tools-together-in-focus-mode "在焦点模式下将工具组合在一起 - DevTools (Microsoft Edge 90 中的新增) |Microsoft Docs"  

[DevtoolsCommandMenuIndexOpenCommandMenu]: ../../../command-menu/index.md#open-the-command-menu "打开命令菜单 - 使用&quot;开发工具Microsoft Edge菜单运行命令|Microsoft Docs"  
[DevtoolsConsoleApiError]: ../../../console/api.md#error "error - 控制台 API |Microsoft Docs"  
[DevtoolsCustomizeLocalization]: ../../../customize/localization.md "更改 DevTools 语言设置 | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../../../issues/index.md "使用问题工具查找并修复|Microsoft Docs"  
[DevtoolsServiceWorkerIndex]: ../../../service-workers/index.md "服务工作者改进|Microsoft Docs"  
[DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode]: ../../../sources/index.md#using-the-debugger-pane-to-debug-javascript-code "使用调试器窗格调试 JavaScript 代码 - 源工具概述|Microsoft Docs"  

[ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]: ../../../../progressive-web-apps-chromium/serviceworker.md#the-service-worker-lifecycle "服务工作线程生命周期 - 使用服务工作者管理网络请求和推送通知|Microsoft Docs"  
[ProgressiveWebAppsWebappmanifests]: ../../../../progressive-web-apps-chromium/webappmanifests.md "使用 Web 应用清单将渐进式 Web 应用集成到操作系统|Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
<!--[GithubMicrosoftVscodeEdgeDevtoolsPullxxx]: https://github.com/microsoft/vscode-edge-devtools/pull/xxx "Pull xxx: Lorem al Ipsum | GitHub"  -->  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerForEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  

[BrotliMain]: https://www.brotli.org "Brotli"  

[ChromestatusFeature4752739957473280]: https://chromestatus.com/feature/4752739957473280 "功能：强调文字颜色 CSS |Chrome 平台状态"  

[CsswgDraftsCssUi4WidgetAccent]: https://drafts.csswg.org/css-ui-4/#widget-accent "小组件主题色：主题色属性 - CSS 基本用户界面模块级别 4 |CSS 工作组编辑器草稿"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR11374]: https://crbug.com/v8/11374 "问题 11374：对私有字段实施品牌打造检查"  
[CR761019]: https://crbug.com/761019 "问题 761019：&quot;转到符号&quot;会错过第一个函数，并且如果它包含所有键入的字符，则首选一个更糟的匹配"  
[CR862450]: https://crbug.com/862450 "问题 862450：[css-scroll-snap] 考虑为 css 滚动贴靠添加 Devtools 功能"  
[CR979000]: https://crbug.com/979000 "问题 979000：具有碰撞源路径的源映射不起作用。"  
[CR1066604]: https://crbug.com/1066604 "问题 1066604：DevTools：查看有关 ServiceWorker 安装和激活事件的详细信息|Chromium Bug"  
<!--  [CR1066772]: https://crbug.com/1066772 "Issue 1066772: "  locked  -->  
[CR1076198]：" https://crbug.com/1076198 问题 1076198：[功能请求] 从选项卡跳转到计算 `styles` 属性"  
[CR1092093]：" https://crbug.com/1092093 问题 1092093：通过支持&quot;accent-color&quot;CSS 属性，使窗体控件的颜色更可样式化"  
[CR1136655]：" https://crbug.com/1136655 问题 1136655：Devtools：本地化 V2 |Chromium Bug"  
[CR1142705]："问题 1142705：使用 webpack 时，两个源映射指向同一虚拟文件时断点停止 https://crbug.com/1142705 工作"  
[CR1149832]：" https://crbug.com/1149832 问题 1149832：功能请求：图像预览还应显示文件大小"  
[CR1158827]：" https://crbug.com/1158827 问题 1158827：[权限策略] 实现权限策略的开发人员支持"  
[CR1162042]： https://crbug.com/1162042 "问题 1162042：DevTools：支持禁用 gzip/brotli/jxl 内容编码"  
[CR1166577]：" https://crbug.com/1166577 问题 1166577：☂️线性内存检查器 1.0"  
[CR1170656]：" https://crbug.com/1170656 问题 1170656：显示固有纵横比"  
[CR1178305]："问题 1178305：调试器在悬停时不会显示已编制索引的元素 https://crbug.com/1178305 的属性值"  
[CR1180794]：" https://crbug.com/1180794 问题 1180794：断点不能与关闭编译器内线优化一起运行"  
[CR1185945]：" https://crbug.com/1185945 问题 1185945：清单警告表示所有图标都必须是方形|Chromium Bug"  
[CR1186049]：" https://crbug.com/1186049 问题 1186049：不同列：缓存查看器中的存储标题"  
[CR1187735]："问题 https://crbug.com/1187735 1187735：辅助功能：MAS2.1.1：键盘：无法调用'Var (。。) 键盘的 |Chromium Bug"  
[CR1189161]： https://crbug.com/1189161 "问题 1189161：堆栈跟踪不是 `new Error` 通过功能区转换的"  
[CR1191465]：" https://crbug.com/1191465 问题 1191465：Ctrl+Shift+O 断开 HTML"  

[GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "权限策略解释器 | GitHub"  

[GlitchMemoryInspectorDemoJsHtml]: https://memory-inspector.glitch.me/demo-js.html "JS |小故障"  
[GlitchMemoryInspectorDemoWasmHtml]: https://memory-inspector.glitch.me/demo-wasm.html "Wasm 内存|小故障"  

[GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml]: https://microsoft-edge-chromium-devtools.glitch.me/css-dbg-stories/css-scroll-snap.html "滚动贴靠演示|小故障"  

[GlitchPermissionPolicyDemoMain]: http://permission-policy-demo.glitch.me "OOPIF 权限策略|小故障"  

[GnuSoftwareGzipManual]: https://www.gnu.org/software/gzip/manual "gzip：数据压缩程序|省/市/市/省/市/市"  

[HttpwgSpecsRfc7231HtmlHeaderVary]: https://httpwg.org/specs/rfc7231.html#header.vary "Vary - HTTP/1.1 (超文本传输协议) ：语义和内容|IETF HTTP 工作组"  

[JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules]: https://webpack.js.org/guides/code-splitting/#:~:text=There%20are%20three%20general%20approaches%20to%20code%20splitting,Split%20code%20via%20inline%20function%20calls%20within%20modules. "可以使用三种常规方法拆分代码：入口点：使用条目配置手动拆分代码。 防止重复：使用条目依赖关系或 SplitChunksPlugin 进行重复数据读取和拆分块。 动态导入：通过模块中的内嵌函数调用拆分代码。- 代码拆分|webpack"  

[MdnDocsWebCssUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性（变量）| MDN"  

[MdnDocsWebJavascriptReferenceOperatorsIn]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/in "in 运算符|MDN"  

[PwabuilderImagegenerator]: https://www.pwabuilder.com/imageGenerator "图像生成器|PWABuilder"  

[RollupjsMain]: https://rollupjs.org "rollup.js"  

[V8DevFeaturesPrivateBrandChecks]: https://v8.dev/features/private-brand-checks "私有品牌检查 obj #foo中的品牌|V8"  
[V8DevFeaturesClassFieldsPrivateClassFields]: https://v8.dev/features/class-fields#private-class-fields "私有类字段 - 公共和私有类|V8"  

[WebpackJsMain]: https://webpack.js.org "webpack"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-91)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
