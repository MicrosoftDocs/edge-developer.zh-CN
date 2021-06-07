---
description: "\"更多工具\"按钮、开始使用 DevTools 扩展的上下文内文档、控制台中增加了对屏幕阅读器的支持等。"
title: 'DevTools (Microsoft Edge 92) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: ebd512800b8e55b5e9c0001c314a7c08fd242d5d
ms.sourcegitcommit: 30817cd9ae187a716d14d06962eb23b32dd54548
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "11590847"
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


## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  


## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubIoDevToolsUsing]: https://microsoft.github.io/vscode-edge-devtools/using.html "使用工具|GitHub"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge开发人员工具Visual Studio Code |Visual StudioMarketplace"  

[YoutubeEdgeStateOfThePlatform]: https://www.youtube.com/watch?v=sU0WRZ0kkNo "Microsoft Edge：平台服务|YouTube"

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
