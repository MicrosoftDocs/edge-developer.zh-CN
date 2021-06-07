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
# <a name="whats-new-in-devtools-microsoft-edge-92"></a><span data-ttu-id="6500c-104">DevTools 92 (Microsoft Edge中的新增) </span><span class="sxs-lookup"><span data-stu-id="6500c-104">What's New In DevTools (Microsoft Edge 92)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

> [!TIP]
> <span data-ttu-id="6500c-105">**Microsoft Build 2021**会议于 5 月 25-27 日召开。</span><span class="sxs-lookup"><span data-stu-id="6500c-105">The **Microsoft Build 2021** conference was on May 25-27.</span></span>  <span data-ttu-id="6500c-106">下面是 Build 中有关 DevTools 更新的视频[：Microsoft Edge |平台状态][YoutubeEdgeStateOfThePlatform]- Microsoft Edge为开发人员提供了一个极具吸引力且一致的平台。</span><span class="sxs-lookup"><span data-stu-id="6500c-106">Here's a video from Build about the updates to DevTools: [Microsoft Edge | State of the Platform][YoutubeEdgeStateOfThePlatform] - Microsoft Edge brings a compelling and consistent platform with tools for developers.</span></span>  <span data-ttu-id="6500c-107">随着旧版浏览器逐步退出支持，Edge 即将成为 Microsoft 在 Windows 10 上唯一受支持的浏览器。</span><span class="sxs-lookup"><span data-stu-id="6500c-107">As our legacy browsers phase out of support, Edge will soon be the only supported browser from Microsoft on Windows 10.</span></span>  <span data-ttu-id="6500c-108">加入我们，了解边缘平台、工具和 Web 应用的最新信息。</span><span class="sxs-lookup"><span data-stu-id="6500c-108">Join us to learn about the latest across the Edge platform, tools, and web apps.</span></span>


## <a name="the-close-button-is-no-longer-hidden-when-devtools-is-narrow"></a><span data-ttu-id="6500c-109">当 DevTools 较窄时，不再隐藏"关闭"按钮</span><span class="sxs-lookup"><span data-stu-id="6500c-109">The Close button is no longer hidden when DevTools is narrow</span></span>

<!-- Title: DevTools is now easier to close -->  
<!-- Subtitle: The Close button in DevTools is always displayed, even when DevTools is docked to the right and the DevTools viewport is narrow. -->  

<span data-ttu-id="6500c-110">在 Microsoft Edge版本 91 或更早版本中，\*\*\*\* 当 DevTools 视口较窄时，不显示关闭 DevTools 的"关闭"按钮。</span><span class="sxs-lookup"><span data-stu-id="6500c-110">In Microsoft Edge version 91 or earlier, the **Close** button to close DevTools isn't displayed when the DevTools viewport is narrow.</span></span>  <span data-ttu-id="6500c-111">在 Microsoft Edge版本 92 中，\*\*\*\* 无论 DevTools 视口宽度如何，DevTools 中的"关闭"按钮始终存在。</span><span class="sxs-lookup"><span data-stu-id="6500c-111">In Microsoft Edge version 92, the **Close** button in the DevTools is always present, regardless of the DevTools viewport width.</span></span>

:::image type="complex" source="../../media/2021/05/close-devtools-button-always-displayed.msft.png" alt-text="即使视区较窄，现在也显示"关闭 DevTools"按钮" lightbox="../../media/2021/05/close-devtools-button-always-displayed.msft.png":::
   <span data-ttu-id="6500c-113">即使 **视** 区较窄，现在也显示"关闭 DevTools"按钮</span><span class="sxs-lookup"><span data-stu-id="6500c-113">The **Close** DevTools button is now present even when the viewport is narrow</span></span>  
:::image-end:::  


## <a name="add-tools-quickly-with-the-new-more-tools-button"></a><span data-ttu-id="6500c-114">使用新的"更多工具"按钮快速添加工具</span><span class="sxs-lookup"><span data-stu-id="6500c-114">Add tools quickly with the new More Tools button</span></span>

<!-- Title: Add tools quickly with the new More Tools button -->  
<!-- Subtitle: Learn about a new convenient way to open tools in Microsoft Edge DevTools. -->  

<span data-ttu-id="6500c-115">有一种在 DevTools 中打开更多工具的Microsoft Edge："更多工具\*\*\*\* `+` () 菜单。</span><span class="sxs-lookup"><span data-stu-id="6500c-115">There's a new way to open more tools in Microsoft Edge DevTools: the **More Tools** (`+`) menu.</span></span> <span data-ttu-id="6500c-116">" **更多工具** "菜单显示在主面板中的工具栏和箱的工具栏上。</span><span class="sxs-lookup"><span data-stu-id="6500c-116">The **More Tools** menu appears on the toolbar in the main panel and on the toolbar of the drawer.</span></span> <span data-ttu-id="6500c-117">从"更多工具 **"菜单中选择** 工具会将该工具添加到工具栏。</span><span class="sxs-lookup"><span data-stu-id="6500c-117">Selecting a tool from the **More Tools** menu adds the tool to the toolbar.</span></span>

<span data-ttu-id="6500c-118">若要对任一工具栏上的选项卡重新排序，请选择并拖动选项卡。</span><span class="sxs-lookup"><span data-stu-id="6500c-118">To reorder the tabs on either toolbar, select and drag the tabs.</span></span>  

<span data-ttu-id="6500c-119">"**更多工具**"菜单作为实验在 Microsoft Edge 89 中可用，现在始终存在。</span><span class="sxs-lookup"><span data-stu-id="6500c-119">The **More Tools** menu was available as an experiment in Microsoft Edge version 89, and is now always present.</span></span>

:::image type="complex" source="../../media/2021/05/more-tools-button.msft.png" alt-text="上方工具栏和"箱"工具栏上的"更多工具"按钮" lightbox="../../media/2021/05/more-tools-button.msft.png":::
   <span data-ttu-id="6500c-121">上方 **工具栏和** "箱"工具栏上的"更多工具"按钮</span><span class="sxs-lookup"><span data-stu-id="6500c-121">The **More Tools** button on the upper toolbar and drawer toolbar</span></span>
:::image-end:::  

:::image type="complex" source="../../media/2021/05/more-tools-menu.msft.png" alt-text=""更多工具"菜单" lightbox="../../media/2021/05/more-tools-menu.msft.png":::
   <span data-ttu-id="6500c-123">" **更多工具"** 菜单</span><span class="sxs-lookup"><span data-stu-id="6500c-123">The **More Tools** menu</span></span>
:::image-end:::  


## <a name="improvements-for-hovering-selecting-and-closing-tools"></a><span data-ttu-id="6500c-124">悬停、选择和关闭工具的改进</span><span class="sxs-lookup"><span data-stu-id="6500c-124">Improvements for hovering, selecting, and closing tools</span></span>

<!-- Title: Improvements to tab interactions -->
<!-- Subtitle: Interactions related to hovering, selecting, and closing tools are more predictable. -->

<span data-ttu-id="6500c-125">已重新格式化每个工具的选项卡，以减少意外关闭工具的可能性。</span><span class="sxs-lookup"><span data-stu-id="6500c-125">Tabs for each tool have been reformatted to reduce the chance of accidentally closing a tool.</span></span>  <span data-ttu-id="6500c-126">在主工具栏和箱的工具栏的每个选项卡上，我们添加了：</span><span class="sxs-lookup"><span data-stu-id="6500c-126">On each tab in the main toolbar and in the toolbar of the drawer, we added:</span></span>
*  <span data-ttu-id="6500c-127">选项卡周围的间距。</span><span class="sxs-lookup"><span data-stu-id="6500c-127">Spacing around the tab.</span></span>
*  <span data-ttu-id="6500c-128">选项卡中关闭 `x` () 按钮的间距。</span><span class="sxs-lookup"><span data-stu-id="6500c-128">Spacing around the close (`x`) button in the tab.</span></span>
*  <span data-ttu-id="6500c-129">将鼠标悬停在选项卡上时的背景颜色。</span><span class="sxs-lookup"><span data-stu-id="6500c-129">A background color when hovering over the tab.</span></span>
*  <span data-ttu-id="6500c-130">用于关闭选项卡 () `x` 按钮的工具提示。</span><span class="sxs-lookup"><span data-stu-id="6500c-130">A tooltip for the close (`x`) button of the tab.</span></span>
*  <span data-ttu-id="6500c-131">选项卡的关闭 `x` () 按钮的较高对比度。</span><span class="sxs-lookup"><span data-stu-id="6500c-131">Higher contrast for the close (`x`) button of the tab.</span></span>

<span data-ttu-id="6500c-132">例如，当你在"性能"工具\*\*\*\* 中，将鼠标悬停在"\*\*\*\* 网络"工具的选项卡上时，这些改进有助于防止意外关闭 **"网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="6500c-132">For example, when you are in the **Performance** tool and you hover over the **Network** tool's tab, these improvements help prevent accidentally closing the **Network** tool.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-before.msft.png" alt-text="重新格式化前的选项卡" lightbox="../../media/2021/05/hovering-on-tool-tab-before.msft.png":::
           <span data-ttu-id="6500c-134">重新格式化前的选项卡</span><span class="sxs-lookup"><span data-stu-id="6500c-134">Tabs before reformatting</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-after.msft.png" alt-text="重新格式化后的选项卡" lightbox="../../media/2021/05/hovering-on-tool-tab-after.msft.png":::
           <span data-ttu-id="6500c-136">重新格式化后的选项卡</span><span class="sxs-lookup"><span data-stu-id="6500c-136">Tabs after reformatting</span></span> :::image-end:::
    :::column-end:::
:::row-end:::

<span data-ttu-id="6500c-137">这些改进对于本地化 DevTools 的用户尤其相关，在这些用户中，选项卡可能更窄且更容易意外关闭。</span><span class="sxs-lookup"><span data-stu-id="6500c-137">These improvements are especially relevant for users of localized DevTools, in which the tabs may be narrower and easier to accidentally close.</span></span>

:::image type="complex" source="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png" alt-text="具有窄选项卡的本地化 DevTools" lightbox="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png":::
   <span data-ttu-id="6500c-139">具有窄选项卡的本地化 DevTools</span><span class="sxs-lookup"><span data-stu-id="6500c-139">Localized DevTools with narrow tabs</span></span>
:::image-end:::

<span data-ttu-id="6500c-140">我们还通过向主工具栏和收银机工具栏添加"更多工具"菜单，[](#add-tools-quickly-with-the-new-more-tools-button)更轻松地重新添加关闭的工具。</span><span class="sxs-lookup"><span data-stu-id="6500c-140">We also made it easier to re-add a tool that you closed by adding a [More Tools menu](#add-tools-quickly-with-the-new-more-tools-button) to the main toolbar and drawer toolbar.</span></span>


## <a name="better-support-for-screen-readers-in-the-console"></a><span data-ttu-id="6500c-141">在控制台中更好地支持屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="6500c-141">Better support for screen readers in the Console</span></span>

<!-- Title: Better screen reader support in the Console -->
<!-- Subtitle: Assistive technologies can now announce autocomplete suggestions and evaluated expressions in the Console. -->

<span data-ttu-id="6500c-142">在Microsoft Edge版本 92 之前，在**控制台**中，屏幕阅读器等辅助技术未宣布自动完成建议或已评估表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="6500c-142">Prior to Microsoft Edge version 92, in the **Console**, assistive technologies such as screen readers didn't announce autocomplete suggestions or the results of evaluated expressions.</span></span> <span data-ttu-id="6500c-143">This has been fixed now.</span><span class="sxs-lookup"><span data-stu-id="6500c-143">This has been fixed now.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png" alt-text="在控制台中，屏幕阅读器现在宣布当前选择的自动完成建议" lightbox="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png":::
           <span data-ttu-id="6500c-145">在 **控制台中**，屏幕阅读器现在宣布当前选择的自动完成建议</span><span class="sxs-lookup"><span data-stu-id="6500c-145">In the **Console**, screen readers now announce the currently selected autocomplete suggestion</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png" alt-text="在控制台中，屏幕阅读器现在宣布计算表达式的结果" lightbox="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png":::
           <span data-ttu-id="6500c-147">在 **控制台中**，屏幕阅读器现在宣布计算表达式的结果</span><span class="sxs-lookup"><span data-stu-id="6500c-147">In the **Console**, screen readers now announce the result of an evaluated expression</span></span> :::image-end:::
    :::column-end:::
:::row-end:::


## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-118"></a><span data-ttu-id="6500c-148">Microsoft Edge开发人员工具Visual Studio Code 1.1.8 版</span><span class="sxs-lookup"><span data-stu-id="6500c-148">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.8</span></span>

<span data-ttu-id="6500c-149">适用于[Microsoft Edge Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] Visual Studio Code 1.1.8 Microsoft Visual Studio开发人员工具自上一版本起发生了以下更改。</span><span class="sxs-lookup"><span data-stu-id="6500c-149">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.8 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="6500c-150">Microsoft Visual Studio Code 会自动更新扩展。</span><span class="sxs-lookup"><span data-stu-id="6500c-150">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="6500c-151">若要手动更新到版本 1.1.8，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]</span><span class="sxs-lookup"><span data-stu-id="6500c-151">To manually update to version 1.1.8, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  

<span data-ttu-id="6500c-152">可以在[vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools]存储库上提交问题并GitHub扩展。</span><span class="sxs-lookup"><span data-stu-id="6500c-152">You can file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

### <a name="in-context-documentation-and-ui-to-make-it-easier-to-use-the-devtools-extension"></a><span data-ttu-id="6500c-153">上下文内文档和 UI，以便更轻松地使用 DevTools 扩展</span><span class="sxs-lookup"><span data-stu-id="6500c-153">In-context documentation and UI to make it easier to use the DevTools extension</span></span>

<!-- Title: In-context documentation and UI make it easier to get started using the Developer Tools extension -->  
<!-- Subtitle: The Microsoft Edge Developer Tools for Visual Studio Code extension now presents helpful text, buttons, and links, and opens a documentation page with guidance on how to get started. -->  

<span data-ttu-id="6500c-154">Microsoft Edge 开发人员工具[for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]扩展的版本 1.1.8 现在提供了一种更简单的方式来启动 Microsoft Edge 的新实例，提供说明、按钮、链接和文档页来指导您。</span><span class="sxs-lookup"><span data-stu-id="6500c-154">Version 1.1.8 of the [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension now features a simpler way to start a new instance of Microsoft Edge, by presenting instructions, buttons, links, and a documentation page to guide you.</span></span>

*  <span data-ttu-id="6500c-155">选择 Visual Studio Code 的活动**栏中**的"Microsoft Edge 工具"\*\*\*\* 按钮时 **，Microsoft Edge**工具： 目标面板现在会提供说明性文本、按钮和链接来指导你，而不是空白面板。</span><span class="sxs-lookup"><span data-stu-id="6500c-155">When you select the **Microsoft Edge Tools** button in the **Activity Bar** of Visual Studio Code, the **Microsoft Edge Tools: Targets** panel now presents explanatory text, buttons, and links to guide you, instead of a blank panel.</span></span>

*  <span data-ttu-id="6500c-156">当您从 Microsoft Edge 中打开 Visual Studio Code 的新实例时，Microsoft Edge将显示一个介绍如何使用开发人员工具扩展的起始页，而不是空白页。</span><span class="sxs-lookup"><span data-stu-id="6500c-156">When you open a new instance of Microsoft Edge from within Visual Studio Code, Microsoft Edge now shows a start page that explains how to use the Developer Tools extension, instead of a blank page.</span></span>

*  <span data-ttu-id="6500c-157">the **Microsoft Edge Tools： Targets panel** now has a Generate launch.js**on** button and instructions， to help launch your project for debugging in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="6500c-157">The **Microsoft Edge Tools: Targets** panel now has a **Generate launch.json** button and instructions, to help launch your project for debugging in Microsoft Edge.</span></span>

<span data-ttu-id="6500c-158">有关详细信息，请导航到["使用工具"。][GithubIoDevToolsUsing]</span><span class="sxs-lookup"><span data-stu-id="6500c-158">For more information, navigate to [Using the tools][GithubIoDevToolsUsing].</span></span>


## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="6500c-159">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="6500c-159">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="6500c-160">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="6500c-160">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="6500c-161">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="6500c-161">The preview channels give you access to the latest DevTools features.</span></span>  


## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="6500c-162">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="6500c-162">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubIoDevToolsUsing]: https://microsoft.github.io/vscode-edge-devtools/using.html "使用工具|GitHub"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge开发人员工具Visual Studio Code |Visual StudioMarketplace"  

[YoutubeEdgeStateOfThePlatform]: https://www.youtube.com/watch?v=sU0WRZ0kkNo "Microsoft Edge：平台服务|YouTube"

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6500c-170">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6500c-170">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
