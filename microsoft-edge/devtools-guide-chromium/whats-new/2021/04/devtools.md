---
description: 波浪下划线突出显示元素工具、服务工作者更新时间线等中的代码问题。
title: 'DevTools (Microsoft Edge 91 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 473b2537b631a77a182c04b6986051a4ce7aae03
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564817"
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

在大多数新式 ID 中，文本下的波浪下划线指示语法错误。   在 Microsoft Edge 91 或更高版本中，在"元素"工具的**DOM**视图中，HTML 下会显示**波浪下划线。**  波浪下划线表示与辅助功能、兼容性、性能等相关的代码问题和建议。  若要详细了解如何查看和编辑问题，请导航到查找并修复开发人员Microsoft Edge[工具中的问题][DevtoolsIssuesIndex]。  

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

在 Microsoft Edge 91 或更高版本中，如果您是渐进式 Web 应用或服务工作者开发人员，您可以在应用程序工具中将服务工作者的更新生命周期显示为**时间线**。  此功能可帮助您了解服务工作者在下列每个阶段所花的时间。  

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

在 Microsoft Edge 版本[90][DevtoolsWhatsNew202102Devtools]或更早版本中，如果您在 PWA 的 Web 应用清单中包含非方形图标，则应用程序工具中的"清单****"部分将在"错误和**** 警告"下显示每个非方形图标的警告。 ****  在Microsoft Edge版本 91 或更高版本中，**** 如果至少提供一**** 个正方形图标，则应用程序工具中的清单部分不会显示警告。  如果未提供任何方形图标，则会显示一条警告消息。  

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

若要在 Web 应用程序清单中查看错误和警告，请导航到 **"应用程序"** 工具并选择"清单 **"** 部分。  错误和警告列在"错误和警告 **"** 标题下。  有关 Web 应用部件清单的信息，请导航到"使用 Web 应用清单"将 [渐进式 Web 应用集成到操作系统中][ProgressiveWebAppsWebappmanifests]。  若要创建要包括在 Web 应用清单中的图标，请导航到 [PWABuilder Image Generator][PwabuilderImagegenerator]。  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1185945"。][CR1185945]  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a>本地化的 DevTools 现在Chromium的浏览器中受支持  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

从 Microsoft Edge[版本 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]开始，Microsoft Edge开发人员工具以你自己的语言显示。  许多开发人员使用 StackOverflow 等其他开发人员工具，Visual Studio Code语言进行开发，而不只是使用英语。  开发人员Microsoft Edge、Chrome DevTools 团队和 Google Lighthouse 团队协作，在所有基于 Chromium 的浏览器中提供相同的体验。  若要详细了解如何在语言中使用 DevTools，请导航到"[更改 DevTools 语言设置"。][DevtoolsCustomizeLocalization]  有关开放源代码项目中有关此功能的协作Chromium，请导航到[1136655。][CR1136655]  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edge浏览器和 DevTools 设置为日语" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   Microsoft Edge浏览器和 DevTools 设置为日语  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a>使用键盘导航到 CSS 变量  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

从[Microsoft Edge版本 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]开始，"**** 样式"窗格将显示 CSS 变量并提供指向每个变量的定义的链接。  在 Microsoft Edge 版本 91 或更高版本中，可以使用箭头键轻松导航到 CSS 变量。  若要在"样式 **"窗格中打开** 定义，请将鼠标悬停在变量上，然后选择 `Enter` 。  有关 CSS 变量详细信息，请导航到使用 CSS 自定义属性 ([变量) 。 ][MdnDocsWebCssUsingCssCustomProperties]  若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1187735"。][CR1187735]  

:::image type="complex" source="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png" alt-text="--theme-body-background CSS 变量在"样式"窗格中突出显示" lightbox="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png":::
   " `--theme-body-background` 样式"窗格中突出显示的**** CSS 变量  
:::image-end:::  

## <a name="issues-are-automatically-sorted-by-severity"></a>问题按严重性自动排序  

<!-- Title: Display Issues in severity order  -->  
<!-- Subtitle: Entries in the Issues tool now display in severity order and allow you to focus your updates on the most important issues. -->  

问题 **工具** 显示改进网站的建议，包括辅助功能、性能、安全性等。 根据你的反馈，现在会自动按严重性对问题进行排序。  在每个反馈类别中，每个标记为"错误"的问题**** 首先出现，然后关注标记为"警告"的每个**** 问题，然后每个标记为"提示"**的问题**。  为了帮助你优化问题，为将来的更新计划了额外的筛选器选项。  若要详细了解如何查看问题，请导航到查找并修复开发人员Microsoft Edge[工具中的问题][DevtoolsIssuesIndex]。  

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

<!--## Announcements from the Chromium project  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### Ipsum et Chromium  

Lorem al lorem et Chromium  To review the history of this feature in the Chromium open-source project, navigate to Issue [xxxxxxx][CRxxxxxxx].  

:::image type="complex" source="../../media/2021/04/lorem-et-chromium.msft.png" alt-text="Ipsum et Chromium" lightbox="../../media/2021/04/lorem-et-chromium.msft.png":::
   Ipsum et Chromium  
:::image-end:::  -->  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]: ../../2020/01/devtools.md#using-the-devtools-in-other-languages "以其他语言使用 DevTools - DevTools (Microsoft Edge 81) |Microsoft Docs"  
[DevtoolsWhatsNew202011Devtools]: ../../2020/11/devtools.md "DevTools (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]: ../../../whats-new/2020/11/devtools.md#css-variable-definitions-in-styles-pane "样式窗格中的 CSS 变量定义 - DevTools (Microsoft Edge 88 中的新增) |Microsoft Docs"  
[DevtoolsWhatsNew202102Devtools]: ../02/devtools.md "DevTools （Microsoft Edge 90） 中的新增功能|Microsoft Docs"  
[DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode]: ../02/devtools.md#group-tools-together-in-focus-mode "在焦点模式下将工具组合在一起 - DevTools (Microsoft Edge 90 中的新增) |Microsoft Docs"  

[DevtoolsCommandMenuIndexOpenCommandMenu]: ../../../command-menu/index.md#open-the-command-menu "打开命令菜单 - 使用&quot;开发工具Microsoft Edge菜单运行命令|Microsoft Docs"  
[DevtoolsCustomizeLocalization]: ../../../customize/localization.md "更改 DevTools 语言设置 | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../../../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsServiceWorkerIndex]: ../../../service-workers/index.md "服务工作者改进|Microsoft Docs"  

[ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]: ../../../../progressive-web-apps-chromium/serviceworker.md#the-service-worker-lifecycle "服务工作线程生命周期 - 使用服务工作者管理网络请求和推送通知|Microsoft Docs"  
[ProgressiveWebAppsWebappmanifests]: ../../../../progressive-web-apps-chromium/webappmanifests.md "使用 Web 应用清单将渐进式 Web 应用集成到操作系统|Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
<!--[GithubMicrosoftVscodeEdgeDevtoolsPullxxx]: https://github.com/microsoft/vscode-edge-devtools/pull/xxx "Pull xxx: Lorem al Ipsum | GitHub"  -->  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerForEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR1066604]: https://crbug.com/1066604 "问题 1066604：DevTools：查看有关 ServiceWorker 安装和激活事件的详细信息|Chromium Bug"  
[CR1136655]: https://crbug.com/1136655 "问题 1136655：开发工具：本地化 V2 |Chromium Bug"  
[CR1185945]: https://crbug.com/1185945 "问题 1185945：清单警告表示所有图标都必须是方形|Chromium Bug"  
[CR1187735]: https://crbug.com/1187735 "问题 1187735：辅助功能：MAS2.1.1：键盘：无法调用&quot;Var (&quot;。) 键盘的 |Chromium Bug"  

[MdnDocsWebCssUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性（变量）| MDN"  

[PwabuilderImagegenerator]: https://www.pwabuilder.com/imageGenerator "图像生成器|PWABuilder"  

<!--  > [!NOTE]
> Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].  
> The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-91) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).  

[![Creative Commons License][CCby4Image]][CCA4IL]  
This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen
-->
