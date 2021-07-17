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
# <a name="whats-new-in-devtools-microsoft-edge-92"></a><span data-ttu-id="f96eb-104">DevTools 92 (Microsoft Edge中的新增) </span><span class="sxs-lookup"><span data-stu-id="f96eb-104">What's New In DevTools (Microsoft Edge 92)</span></span>

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]

> [!TIP]
> <span data-ttu-id="f96eb-105">**Microsoft Build 2021**会议于 5 月 25-27 日召开。</span><span class="sxs-lookup"><span data-stu-id="f96eb-105">The **Microsoft Build 2021** conference was on May 25-27.</span></span>  <span data-ttu-id="f96eb-106">下面是 Build 中有关 DevTools 更新的视频[：Microsoft Edge |平台状态][YoutubeEdgeStateOfThePlatform]- Microsoft Edge为开发人员提供了一个极具吸引力且一致的平台。</span><span class="sxs-lookup"><span data-stu-id="f96eb-106">Here's a video from Build about the updates to DevTools: [Microsoft Edge | State of the Platform][YoutubeEdgeStateOfThePlatform] - Microsoft Edge brings a compelling and consistent platform with tools for developers.</span></span>  <span data-ttu-id="f96eb-107">随着旧版浏览器逐步退出支持，Edge 即将成为 Microsoft 在 Windows 10 上唯一受支持的浏览器。</span><span class="sxs-lookup"><span data-stu-id="f96eb-107">As our legacy browsers phase out of support, Edge will soon be the only supported browser from Microsoft on Windows 10.</span></span>  <span data-ttu-id="f96eb-108">加入我们，了解边缘平台、工具和 Web 应用的最新信息。</span><span class="sxs-lookup"><span data-stu-id="f96eb-108">Join us to learn about the latest across the Edge platform, tools, and web apps.</span></span>


## <a name="the-close-button-is-no-longer-hidden-when-devtools-is-narrow"></a><span data-ttu-id="f96eb-109">当 DevTools 较窄时，不再隐藏"关闭"按钮</span><span class="sxs-lookup"><span data-stu-id="f96eb-109">The Close button is no longer hidden when DevTools is narrow</span></span>

<!-- Title: DevTools is now easier to close -->
<!-- Subtitle: The Close button in DevTools is always displayed, even when DevTools is docked to the right and the DevTools viewport is narrow. -->

<span data-ttu-id="f96eb-110">在 Microsoft Edge版本 91 或更早版本中，\*\*\*\* 当 DevTools 视口较窄时，不显示关闭 DevTools 的"关闭"按钮。</span><span class="sxs-lookup"><span data-stu-id="f96eb-110">In Microsoft Edge version 91 or earlier, the **Close** button to close DevTools isn't displayed when the DevTools viewport is narrow.</span></span>  <span data-ttu-id="f96eb-111">在 Microsoft Edge版本 92 中，\*\*\*\* 无论 DevTools 视口宽度如何，DevTools 中的"关闭"按钮始终存在。</span><span class="sxs-lookup"><span data-stu-id="f96eb-111">In Microsoft Edge version 92, the **Close** button in the DevTools is always present, regardless of the DevTools viewport width.</span></span>

:::image type="complex" source="../../media/2021/05/close-devtools-button-always-displayed.msft.png" alt-text="即使视区较窄，现在也显示"关闭 DevTools"按钮" lightbox="../../media/2021/05/close-devtools-button-always-displayed.msft.png":::
   <span data-ttu-id="f96eb-113">即使 **视** 区较窄，现在也显示"关闭 DevTools"按钮</span><span class="sxs-lookup"><span data-stu-id="f96eb-113">The **Close** DevTools button is now present even when the viewport is narrow</span></span>
:::image-end:::


## <a name="add-tools-quickly-with-the-new-more-tools-button"></a><span data-ttu-id="f96eb-114">使用新的"更多工具"按钮快速添加工具</span><span class="sxs-lookup"><span data-stu-id="f96eb-114">Add tools quickly with the new More Tools button</span></span>

<!-- Title: Add tools quickly with the new More Tools button -->
<!-- Subtitle: Learn about a new convenient way to open tools in Microsoft Edge DevTools. -->

<span data-ttu-id="f96eb-115">有一种在 DevTools 中打开更多工具的Microsoft Edge："更多工具\*\*\*\* `+` () 菜单。</span><span class="sxs-lookup"><span data-stu-id="f96eb-115">There's a new way to open more tools in Microsoft Edge DevTools: the **More Tools** (`+`) menu.</span></span> <span data-ttu-id="f96eb-116">" **更多工具** "菜单显示在主面板中的工具栏和箱的工具栏上。</span><span class="sxs-lookup"><span data-stu-id="f96eb-116">The **More Tools** menu appears on the toolbar in the main panel and on the toolbar of the drawer.</span></span> <span data-ttu-id="f96eb-117">从"更多工具 **"菜单中选择** 工具会将该工具添加到工具栏。</span><span class="sxs-lookup"><span data-stu-id="f96eb-117">Selecting a tool from the **More Tools** menu adds the tool to the toolbar.</span></span>

<span data-ttu-id="f96eb-118">若要对任一工具栏上的选项卡重新排序，请选择并拖动选项卡。</span><span class="sxs-lookup"><span data-stu-id="f96eb-118">To reorder the tabs on either toolbar, select and drag the tabs.</span></span>

<span data-ttu-id="f96eb-119">"**更多工具**"菜单作为实验在 Microsoft Edge 89 中可用，现在始终存在。</span><span class="sxs-lookup"><span data-stu-id="f96eb-119">The **More Tools** menu was available as an experiment in Microsoft Edge version 89, and is now always present.</span></span>

:::image type="complex" source="../../media/2021/05/more-tools-button.msft.png" alt-text="上方工具栏和"箱"工具栏上的"更多工具"按钮" lightbox="../../media/2021/05/more-tools-button.msft.png":::
   <span data-ttu-id="f96eb-121">上方 **工具栏和** "箱"工具栏上的"更多工具"按钮</span><span class="sxs-lookup"><span data-stu-id="f96eb-121">The **More Tools** button on the upper toolbar and drawer toolbar</span></span>
:::image-end:::

:::image type="complex" source="../../media/2021/05/more-tools-menu.msft.png" alt-text=""更多工具"菜单" lightbox="../../media/2021/05/more-tools-menu.msft.png":::
   <span data-ttu-id="f96eb-123">" **更多工具"** 菜单</span><span class="sxs-lookup"><span data-stu-id="f96eb-123">The **More Tools** menu</span></span>
:::image-end:::


## <a name="improvements-for-hovering-selecting-and-closing-tools"></a><span data-ttu-id="f96eb-124">悬停、选择和关闭工具的改进</span><span class="sxs-lookup"><span data-stu-id="f96eb-124">Improvements for hovering, selecting, and closing tools</span></span>

<!-- Title: Improvements to tab interactions -->
<!-- Subtitle: Interactions related to hovering, selecting, and closing tools are more predictable. -->

<span data-ttu-id="f96eb-125">已重新格式化每个工具的选项卡，以减少意外关闭工具的可能性。</span><span class="sxs-lookup"><span data-stu-id="f96eb-125">Tabs for each tool have been reformatted to reduce the chance of accidentally closing a tool.</span></span>  <span data-ttu-id="f96eb-126">在主工具栏和箱的工具栏的每个选项卡上，我们添加了：</span><span class="sxs-lookup"><span data-stu-id="f96eb-126">On each tab in the main toolbar and in the toolbar of the drawer, we added:</span></span>
*  <span data-ttu-id="f96eb-127">选项卡周围的间距。</span><span class="sxs-lookup"><span data-stu-id="f96eb-127">Spacing around the tab.</span></span>
*  <span data-ttu-id="f96eb-128">选项卡中关闭 `x` () 按钮的间距。</span><span class="sxs-lookup"><span data-stu-id="f96eb-128">Spacing around the close (`x`) button in the tab.</span></span>
*  <span data-ttu-id="f96eb-129">将鼠标悬停在选项卡上时的背景颜色。</span><span class="sxs-lookup"><span data-stu-id="f96eb-129">A background color when hovering over the tab.</span></span>
*  <span data-ttu-id="f96eb-130">用于关闭选项卡 () `x` 按钮的工具提示。</span><span class="sxs-lookup"><span data-stu-id="f96eb-130">A tooltip for the close (`x`) button of the tab.</span></span>
*  <span data-ttu-id="f96eb-131">选项卡的关闭 `x` () 按钮的较高对比度。</span><span class="sxs-lookup"><span data-stu-id="f96eb-131">Higher contrast for the close (`x`) button of the tab.</span></span>

<span data-ttu-id="f96eb-132">例如，当你在"性能"工具\*\*\*\* 中，将鼠标悬停在"\*\*\*\* 网络"工具的选项卡上时，这些改进有助于防止意外关闭 **"网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="f96eb-132">For example, when you are in the **Performance** tool and you hover over the **Network** tool's tab, these improvements help prevent accidentally closing the **Network** tool.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-before.msft.png" alt-text="重新格式化前的选项卡" lightbox="../../media/2021/05/hovering-on-tool-tab-before.msft.png":::
           <span data-ttu-id="f96eb-134">重新格式化前的选项卡</span><span class="sxs-lookup"><span data-stu-id="f96eb-134">Tabs before reformatting</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/hovering-on-tool-tab-after.msft.png" alt-text="重新格式化后的选项卡" lightbox="../../media/2021/05/hovering-on-tool-tab-after.msft.png":::
           <span data-ttu-id="f96eb-136">重新格式化后的选项卡</span><span class="sxs-lookup"><span data-stu-id="f96eb-136">Tabs after reformatting</span></span> :::image-end:::
    :::column-end:::
:::row-end:::

<span data-ttu-id="f96eb-137">这些改进对于本地化 DevTools 的用户尤其相关，在这些用户中，选项卡可能更窄且更容易意外关闭。</span><span class="sxs-lookup"><span data-stu-id="f96eb-137">These improvements are especially relevant for users of localized DevTools, in which the tabs may be narrower and easier to accidentally close.</span></span>

:::image type="complex" source="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png" alt-text="具有窄选项卡的本地化 DevTools" lightbox="../../media/2021/05/hovering-reduced-chance-of-closing-tab.msft.png":::
   <span data-ttu-id="f96eb-139">具有窄选项卡的本地化 DevTools</span><span class="sxs-lookup"><span data-stu-id="f96eb-139">Localized DevTools with narrow tabs</span></span>
:::image-end:::

<span data-ttu-id="f96eb-140">我们还通过向主工具栏和收银机工具栏添加"更多工具"菜单，[](#add-tools-quickly-with-the-new-more-tools-button)更轻松地重新添加关闭的工具。</span><span class="sxs-lookup"><span data-stu-id="f96eb-140">We also made it easier to re-add a tool that you closed by adding a [More Tools menu](#add-tools-quickly-with-the-new-more-tools-button) to the main toolbar and drawer toolbar.</span></span>


## <a name="better-support-for-screen-readers-in-the-console"></a><span data-ttu-id="f96eb-141">在控制台中更好地支持屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="f96eb-141">Better support for screen readers in the Console</span></span>

<!-- Title: Better screen reader support in the Console -->
<!-- Subtitle: Assistive technologies can now announce autocomplete suggestions and evaluated expressions in the Console. -->

<span data-ttu-id="f96eb-142">在Microsoft Edge版本 92 之前，在**控制台**中，屏幕阅读器等辅助技术未宣布自动完成建议或已评估表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="f96eb-142">Prior to Microsoft Edge version 92, in the **Console**, assistive technologies such as screen readers didn't announce autocomplete suggestions or the results of evaluated expressions.</span></span> <span data-ttu-id="f96eb-143">This has been fixed now.</span><span class="sxs-lookup"><span data-stu-id="f96eb-143">This has been fixed now.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png" alt-text="在控制台中，屏幕阅读器现在宣布当前选择的自动完成建议" lightbox="../../media/2021/05/screen-reader-support-in-console-autocomplete.msft.png":::
           <span data-ttu-id="f96eb-145">在 **控制台中**，屏幕阅读器现在宣布当前选择的自动完成建议</span><span class="sxs-lookup"><span data-stu-id="f96eb-145">In the **Console**, screen readers now announce the currently selected autocomplete suggestion</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png" alt-text="在控制台中，屏幕阅读器现在宣布计算表达式的结果" lightbox="../../media/2021/05/screen-reader-support-in-console-evaluated-expression.msft.png":::
           <span data-ttu-id="f96eb-147">在 **控制台中**，屏幕阅读器现在宣布计算表达式的结果</span><span class="sxs-lookup"><span data-stu-id="f96eb-147">In the **Console**, screen readers now announce the result of an evaluated expression</span></span> :::image-end:::
    :::column-end:::
:::row-end:::


## <a name="source-order-viewer"></a><span data-ttu-id="f96eb-148">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="f96eb-148">Source Order Viewer</span></span>

<!--  Title: Source Order Viewer -->
<!--  Subtitle: The new Source Order Viewer displays numbers on the webpage indicating the order of page elements in the source file, independently of how the page sections are positioned by CSS. -->

<span data-ttu-id="f96eb-149">现在，您可以查看呈现网页上覆盖的源元素的顺序，以便进行更好的辅助功能检查。</span><span class="sxs-lookup"><span data-stu-id="f96eb-149">You can now view the order of source elements overlaid on the rendered webpage, for better accessibility inspection.</span></span>

<span data-ttu-id="f96eb-150">HTML 文档中的内容顺序对于搜索引擎优化和辅助功能非常重要。</span><span class="sxs-lookup"><span data-stu-id="f96eb-150">The order of content in an HTML document is important for search engine optimization and accessibility.</span></span>  <span data-ttu-id="f96eb-151">CSS 允许开发人员创建在屏幕上看起来与 HTML 源文档中的顺序不同的内容。</span><span class="sxs-lookup"><span data-stu-id="f96eb-151">CSS allows developers to create content that looks different in its on-screen order than the order in the HTML source document.</span></span>  <span data-ttu-id="f96eb-152">这是一个辅助功能问题，因为屏幕阅读器用户可能会获得令人困惑的体验。</span><span class="sxs-lookup"><span data-stu-id="f96eb-152">This is an accessibility problem, because screen-reader users could get a confusing experience.</span></span>

:::image type="complex" source="../../media/2021/05/source-order-viewer.msft.png" alt-text="激活源顺序查看器将源中的元素顺序作为页面上的覆盖显示" lightbox="../../media/2021/05/source-order-viewer.msft.png":::
   <span data-ttu-id="f96eb-154">激活源 **顺序查看器** 将源中的元素顺序作为页面上的覆盖显示</span><span class="sxs-lookup"><span data-stu-id="f96eb-154">Activating the **Source Order Viewer** shows the order of the elements in the source as overlays on the page</span></span>
:::image-end:::

<span data-ttu-id="f96eb-155">有关详细信息，请导航到使用 [源订单查看器测试键盘支持](../../../accessibility/test-tab-key-source-order-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="f96eb-155">For more information, navigate to [Test keyboard support using the Source Order Viewer](../../../accessibility/test-tab-key-source-order-viewer.md).</span></span>

<span data-ttu-id="f96eb-156">若要在开放源代码项目中查看此功能Chromium历史记录，请导航到"问题[1094406"。][CR1094406]</span><span class="sxs-lookup"><span data-stu-id="f96eb-156">To review the history of this feature in the Chromium open-source project, navigate to Issue [1094406][CR1094406].</span></span>


## <a name="user-agent-client-hints-for-devices-in-the-network-conditions-tab"></a><span data-ttu-id="f96eb-157">User-Agent条件选项卡中的设备提示客户端提示</span><span class="sxs-lookup"><span data-stu-id="f96eb-157">User-Agent Client Hints for devices in the Network conditions tab</span></span>

<!--  Title: User-Agent Client Hints -->
<!--  Subtitle: Access information about a user's browser in an ergonomic way that preserves privacy. -->

<span data-ttu-id="f96eb-158">User-Agent客户端提示现在适用于"网络条件"工具中"用户 **代理** " **字段中** 的设备。</span><span class="sxs-lookup"><span data-stu-id="f96eb-158">User-Agent Client Hints are now applied for devices in the **User agent** field in the **Network conditions** tool.</span></span>  <span data-ttu-id="f96eb-159">User-Agent客户端提示是客户端提示 API 的一个新扩展，它使你能够以一种保留隐私的轻松方式访问有关用户浏览器的信息。</span><span class="sxs-lookup"><span data-stu-id="f96eb-159">User-Agent Client Hints are a new expansion to the Client Hints API that enables you to access information about a user's browser in an ergonomic way that preserves privacy.</span></span>

:::image type="complex" source="../../media/2021/05/user-agent.msft.png" alt-text="用户代理" lightbox="../../media/2021/05/user-agent.msft.png":::
   <span data-ttu-id="f96eb-161">用户代理</span><span class="sxs-lookup"><span data-stu-id="f96eb-161">User agent</span></span>
:::image-end:::

<span data-ttu-id="f96eb-162">有关详细信息，请导航到["用户代理客户端提示"。](../../../../web-platform/user-agent-guidance.md#user-agent-client-hints)</span><span class="sxs-lookup"><span data-stu-id="f96eb-162">For more information, navigate to [User-Agent Client Hints](../../../../web-platform/user-agent-guidance.md#user-agent-client-hints).</span></span>

<span data-ttu-id="f96eb-163">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1174299"。][CR1174299]</span><span class="sxs-lookup"><span data-stu-id="f96eb-163">To review the history of this feature in the Chromium open-source project, navigate to Issue [1174299][CR1174299].</span></span>


## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-118"></a><span data-ttu-id="f96eb-164">Microsoft Edge开发人员工具Visual Studio Code 1.1.8 版</span><span class="sxs-lookup"><span data-stu-id="f96eb-164">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.8</span></span>

<span data-ttu-id="f96eb-165">适用于[Microsoft Edge Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] Visual Studio Code 1.1.8 Microsoft Visual Studio开发人员工具自上一版本起发生了以下更改。</span><span class="sxs-lookup"><span data-stu-id="f96eb-165">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.8 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="f96eb-166">Microsoft Visual Studio Code 会自动更新扩展。</span><span class="sxs-lookup"><span data-stu-id="f96eb-166">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="f96eb-167">若要手动更新到版本 1.1.8，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]</span><span class="sxs-lookup"><span data-stu-id="f96eb-167">To manually update to version 1.1.8, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>

<span data-ttu-id="f96eb-168">可以在[vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools]存储库上提交问题并GitHub扩展。</span><span class="sxs-lookup"><span data-stu-id="f96eb-168">You can file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>

### <a name="in-context-documentation-and-ui-to-make-it-easier-to-use-the-devtools-extension"></a><span data-ttu-id="f96eb-169">上下文内文档和 UI，以便更轻松地使用 DevTools 扩展</span><span class="sxs-lookup"><span data-stu-id="f96eb-169">In-context documentation and UI to make it easier to use the DevTools extension</span></span>

<!-- Title: In-context documentation and UI make it easier to get started using the Developer Tools extension -->
<!-- Subtitle: The Microsoft Edge Developer Tools for Visual Studio Code extension now presents helpful text, buttons, and links, and opens a documentation page with guidance on how to get started. -->

<span data-ttu-id="f96eb-170">Microsoft Edge 开发人员工具[for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]扩展的版本 1.1.8 现在提供了一种更简单的方式来启动 Microsoft Edge 的新实例，提供说明、按钮、链接和文档页来指导您。</span><span class="sxs-lookup"><span data-stu-id="f96eb-170">Version 1.1.8 of the [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension now features a simpler way to start a new instance of Microsoft Edge, by presenting instructions, buttons, links, and a documentation page to guide you.</span></span>

*  <span data-ttu-id="f96eb-171">选择 Visual Studio Code 的活动**栏中**的"Microsoft Edge 工具"\*\*\*\* 按钮时 **，Microsoft Edge**工具： 目标面板现在会提供说明性文本、按钮和链接来指导你，而不是空白面板。</span><span class="sxs-lookup"><span data-stu-id="f96eb-171">When you select the **Microsoft Edge Tools** button in the **Activity Bar** of Visual Studio Code, the **Microsoft Edge Tools: Targets** panel now presents explanatory text, buttons, and links to guide you, instead of a blank panel.</span></span>

*  <span data-ttu-id="f96eb-172">当您从 Microsoft Edge 中打开 Visual Studio Code 的新实例时，Microsoft Edge将显示一个介绍如何使用开发人员工具扩展的起始页，而不是空白页。</span><span class="sxs-lookup"><span data-stu-id="f96eb-172">When you open a new instance of Microsoft Edge from within Visual Studio Code, Microsoft Edge now shows a start page that explains how to use the Developer Tools extension, instead of a blank page.</span></span>

*  <span data-ttu-id="f96eb-173">the **Microsoft Edge Tools： Targets panel** now has a Generate launch.js**on** button and instructions， to help launch your project for debugging in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f96eb-173">The **Microsoft Edge Tools: Targets** panel now has a **Generate launch.json** button and instructions, to help launch your project for debugging in Microsoft Edge.</span></span>

<span data-ttu-id="f96eb-174">有关详细信息，请导航到["使用工具"。][GithubIoDevToolsUsing]</span><span class="sxs-lookup"><span data-stu-id="f96eb-174">For more information, navigate to [Using the tools][GithubIoDevToolsUsing].</span></span>


## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="f96eb-175">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="f96eb-175">Announcements from the Chromium project</span></span>

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]


### <a name="css-grid-editor"></a><span data-ttu-id="f96eb-176">CSS 网格编辑器</span><span class="sxs-lookup"><span data-stu-id="f96eb-176">CSS Grid editor</span></span>

<span data-ttu-id="f96eb-177">现在，您可以使用新的 CSS 网格编辑器预览和创作 CSS 网格布局。</span><span class="sxs-lookup"><span data-stu-id="f96eb-177">You can now preview and author CSS Grid layouts, using the new CSS Grid editor.</span></span>

<span data-ttu-id="f96eb-178">如果页面上的 HTML 元素已应用或已应用，"样式"选项卡中旁边会显示一个网格图标。单击网格图标可显示或隐藏 `display: grid` `display: inline-grid` CSS 网格编辑器。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f96eb-178">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a grid icon is displayed next to it in the **Styles** tab. Click the grid icon to display or hide the CSS grid editor.</span></span> <span data-ttu-id="f96eb-179">在 CSS 网格编辑器中，选择 (图标，) 以预览呈现 `justify-content: space-around` 页面中的布局。</span><span class="sxs-lookup"><span data-stu-id="f96eb-179">In the CSS grid editor, select any of the icons (such as `justify-content: space-around`) to preview the layout in the rendered page.</span></span>  <span data-ttu-id="f96eb-180">弹性布局的工作方式类似。</span><span class="sxs-lookup"><span data-stu-id="f96eb-180">Flex layout works similarly.</span></span>

:::image type="complex" source="../../media/2021/05/css-grid-editor.msft.png" alt-text="CSS 网格编辑器" lightbox="../../media/2021/05/css-grid-editor.msft.png":::
   <span data-ttu-id="f96eb-182">CSS 网格编辑器</span><span class="sxs-lookup"><span data-stu-id="f96eb-182">CSS Grid editor</span></span>
:::image-end:::

<!-- screenshot uses https://jec.fyi -->

<span data-ttu-id="f96eb-183">若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1203241"。][CR1203241]</span><span class="sxs-lookup"><span data-stu-id="f96eb-183">To review the history of this feature in the Chromium open-source project, navigate to Issue [1203241][CR1203241].</span></span>


### <a name="support-for-const-redeclarations-in-the-console"></a><span data-ttu-id="f96eb-184">控制台中对 const 重新声明的支持</span><span class="sxs-lookup"><span data-stu-id="f96eb-184">Support for const redeclarations in the Console</span></span>

<span data-ttu-id="f96eb-185">控制台现在支持在单独的 REPL 脚本中重新声明变量 (例如，除了现有和重新声明之外，还支持在控制台) 中运行语句 `const` `let` `class` 。</span><span class="sxs-lookup"><span data-stu-id="f96eb-185">The Console now supports redeclaration of `const` variables across separate REPL scripts (such as when you run a statement in the Console), in addition to the existing `let` and `class` redeclarations.</span></span>  <span data-ttu-id="f96eb-186">此支持允许你对变量进行不同的声明试验 `const` ，而无需刷新页面。</span><span class="sxs-lookup"><span data-stu-id="f96eb-186">This support allows you to experiment with different declarations for `const` variables without refreshing the page.</span></span>  <span data-ttu-id="f96eb-187">以前，如果重新声明绑定，DevTools 会抛出语法 `const` 错误。</span><span class="sxs-lookup"><span data-stu-id="f96eb-187">Previously, DevTools threw a syntax error if you redeclared a `const` binding.</span></span>

<span data-ttu-id="f96eb-188">请参阅下面的示例。</span><span class="sxs-lookup"><span data-stu-id="f96eb-188">Refer to the example below.</span></span> `const` <span data-ttu-id="f96eb-189">redeclaration is supported across separate REPL scripts (refer to variable `a`) .</span><span class="sxs-lookup"><span data-stu-id="f96eb-189">redeclaration is supported across separate REPL scripts (refer to variable `a`).</span></span>  <span data-ttu-id="f96eb-190">请注意，以下方案在设计上不受支持：</span><span class="sxs-lookup"><span data-stu-id="f96eb-190">Note that the following scenarios are not supported, by design:</span></span>

*  `const` <span data-ttu-id="f96eb-191">REPL 脚本中不允许重新声明页面脚本。</span><span class="sxs-lookup"><span data-stu-id="f96eb-191">redeclaration of page scripts is not allowed in REPL scripts.</span></span>
*  `const` <span data-ttu-id="f96eb-192">不允许在同一 REPL 脚本中重新声明， (引用变量 `b`) 。</span><span class="sxs-lookup"><span data-stu-id="f96eb-192">redeclaration within the same REPL script is not allowed (refer to variable `b`).</span></span>

:::image type="complex" source="../../media/2021/05/support-for-const-redeclaration.msft.png" alt-text="控制台中允许重新声明 const 变量" lightbox="../../media/2021/05/support-for-const-redeclaration.msft.png":::
   <span data-ttu-id="f96eb-194">控制台中允许重新声明 const 变量</span><span class="sxs-lookup"><span data-stu-id="f96eb-194">Redeclaring a const variable is allowed in the console</span></span>
:::image-end:::

<span data-ttu-id="f96eb-195">若要了解如何运行单个 REPL 脚本或多行 REPL 脚本，请导航到作为 [JavaScript 环境的](../../../console/console-javascript.md)控制台。</span><span class="sxs-lookup"><span data-stu-id="f96eb-195">To learn how to run a single REPL script or a multi-line REPL script, navigate to [The Console as a JavaScript environment](../../../console/console-javascript.md).</span></span>
    
<span data-ttu-id="f96eb-196">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1076427"。][CR1076427]</span><span class="sxs-lookup"><span data-stu-id="f96eb-196">To review the history of this feature in the Chromium open-source project, navigate to Issue [1076427][CR1076427].</span></span>


### <a name="new-shortcut-to-view-iframe-details"></a><span data-ttu-id="f96eb-197">查看 iframe 详细信息的新快捷方式</span><span class="sxs-lookup"><span data-stu-id="f96eb-197">New shortcut to view iframe details</span></span>

<span data-ttu-id="f96eb-198">若要快速查看详细信息，现在可以右键单击"元素"工具中的元素， `iframe` `iframe` 然后选择"显示**iframe 详细信息"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f96eb-198">To quickly view `iframe` details, you can now right-click an `iframe` element in the **Elements** tool, and then select **Show iframe details**.</span></span>

:::image type="complex" source="../../media/2021/05/show-iframe-details.msft.png" alt-text="iframe 详细信息视图" lightbox="../../media/2021/05/show-iframe-details.msft.png":::
   <span data-ttu-id="f96eb-200">iframe 详细信息视图</span><span class="sxs-lookup"><span data-stu-id="f96eb-200">iframe details view</span></span>
:::image-end:::

<span data-ttu-id="f96eb-201">这将在应用程序工具 `iframe` 中显示有关 **的详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="f96eb-201">This displays the details about the `iframe` in the **Application** tool.</span></span>  <span data-ttu-id="f96eb-202">在 **应用程序工具** 中，可以检查文档详细信息、安全和隔离状态、权限策略等，以调试潜在问题。</span><span class="sxs-lookup"><span data-stu-id="f96eb-202">In the **Application** tool, you can examine document details, security and isolation status, permissions policy, and more, to debug potential issues.</span></span>

:::image type="complex" source="../../media/2021/05/show-iframe-details-application-tool.msft.png" alt-text="应用程序工具中的帧详细信息" lightbox="../../media/2021/05/show-iframe-details-application-tool.msft.png":::
   <span data-ttu-id="f96eb-204">应用程序工具中的 **帧** 详细信息</span><span class="sxs-lookup"><span data-stu-id="f96eb-204">Frame details in the **Application** tool</span></span>
:::image-end:::

<!-- demo page: https://wolfib.github.io/web-demos/ esp https://wolfib.github.io/web-demos/jsIframe.html -->

<span data-ttu-id="f96eb-205">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1192084"。][CR1192084]</span><span class="sxs-lookup"><span data-stu-id="f96eb-205">To review the history of this feature in the Chromium open-source project, navigate to Issue [1192084][CR1192084].</span></span>


### <a name="enhanced-cors-debugging-support"></a><span data-ttu-id="f96eb-206">增强的 CORS 调试支持</span><span class="sxs-lookup"><span data-stu-id="f96eb-206">Enhanced CORS debugging support</span></span>

<span data-ttu-id="f96eb-207">跨源资源共享 (CORS) 错误现在在"问题"选项卡 **中** 显示。 CORS 错误的潜在原因有很多。</span><span class="sxs-lookup"><span data-stu-id="f96eb-207">Cross-origin resource sharing (CORS) errors are now surfaced in the **Issues** tab.  There are various potential causes of CORS errors.</span></span>  <span data-ttu-id="f96eb-208">单击展开每个问题以了解潜在原因和解决方案。</span><span class="sxs-lookup"><span data-stu-id="f96eb-208">Click to expand each issue to understand the potential causes and solutions.</span></span>

:::image type="complex" source="../../media/2021/05/cors-debugging-support.msft.png" alt-text=""问题"选项卡中的 CORS 问题" lightbox="../../media/2021/05/cors-debugging-support.msft.png":::
   <span data-ttu-id="f96eb-210">"问题"选项卡中的 CORS 问题</span><span class="sxs-lookup"><span data-stu-id="f96eb-210">CORS issues in the Issues tab</span></span>
:::image-end:::

<!-- screenshot uses http://cors-errors.glitch.me -->

<span data-ttu-id="f96eb-211">若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1141824"。][CR1141824]</span><span class="sxs-lookup"><span data-stu-id="f96eb-211">To review the history of this feature in the Chromium open-source project, navigate to Issue [1141824][CR1141824].</span></span>


### <a name="renamed-xhr-filter-to-fetchxhr"></a><span data-ttu-id="f96eb-212">将 XHR 筛选器重命名为 Fetch\/XHR</span><span class="sxs-lookup"><span data-stu-id="f96eb-212">Renamed XHR filter to Fetch\/XHR</span></span>

<span data-ttu-id="f96eb-213">在 **网络工具** 中 **，XHR** 筛选器现在重命名为 **Fetch/XHR**。</span><span class="sxs-lookup"><span data-stu-id="f96eb-213">In the **Network** tool, the **XHR** filter is now renamed to **Fetch/XHR**.</span></span> <span data-ttu-id="f96eb-214">此更改使此筛选器包括 和 `XMLHttpRequest` API `Fetch` 网络请求更加清晰。</span><span class="sxs-lookup"><span data-stu-id="f96eb-214">This change makes it clearer that this filter includes both `XMLHttpRequest` and `Fetch` API network requests.</span></span>

:::image type="complex" source="../../media/2021/05/fetch-xhr.msft.png" alt-text="网络工具现在显示 Fetch/XHR 而不是 XHR" lightbox="../../media/2021/05/fetch-xhr.msft.png":::
   <span data-ttu-id="f96eb-216">网络 **工具** 现在显示 **Fetch/XHR** 而不是 **XHR**</span><span class="sxs-lookup"><span data-stu-id="f96eb-216">The **Network** tool now shows **Fetch/XHR** instead of **XHR**</span></span>
:::image-end:::

<span data-ttu-id="f96eb-217">有关详细信息，请导航到：</span><span class="sxs-lookup"><span data-stu-id="f96eb-217">For more information, navigate to:</span></span>
*  [<span data-ttu-id="f96eb-218">XMLHttpRequest 规范</span><span class="sxs-lookup"><span data-stu-id="f96eb-218">XMLHttpRequest spec</span></span>][XhrSpecWhatwgOrg]
*  [<span data-ttu-id="f96eb-219">Fetch spec</span><span class="sxs-lookup"><span data-stu-id="f96eb-219">Fetch spec</span></span>][FetchSpecWhatwgOrg]

<span data-ttu-id="f96eb-220">若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1201398"。][CR1201398]</span><span class="sxs-lookup"><span data-stu-id="f96eb-220">To review the history of this feature in the Chromium open-source project, navigate to Issue [1201398][CR1201398].</span></span>


### <a name="filter-wasm-resource-type-in-the-network-tool"></a><span data-ttu-id="f96eb-221">网络工具中的 Filter Wasm 资源类型</span><span class="sxs-lookup"><span data-stu-id="f96eb-221">Filter Wasm resource type in the Network tool</span></span>

<span data-ttu-id="f96eb-222">在 **"网络** "工具中，现在可以选择新的 **Wasm** 筛选器来筛选 WebAssembly 网络请求。</span><span class="sxs-lookup"><span data-stu-id="f96eb-222">In the **Network** tool, you can now select the new **Wasm** filter to filter the WebAssembly network requests.</span></span>

:::image type="complex" source="../../media/2021/05/wasm-network-requests.msft.png" alt-text="按 Wasm 筛选" lightbox="../../media/2021/05/wasm-network-requests.msft.png":::
   <span data-ttu-id="f96eb-224">按 Wasm 筛选</span><span class="sxs-lookup"><span data-stu-id="f96eb-224">Filter by Wasm</span></span>
:::image-end:::

<!-- screenshot uses http://memory-inspector.glitch.me/demo-wasm.html -->

<span data-ttu-id="f96eb-225">若要在开放源代码项目中查看此功能Chromium历史记录，请导航到"问题[1103638"。][CR1103638]</span><span class="sxs-lookup"><span data-stu-id="f96eb-225">To review the history of this feature in the Chromium open-source project, navigate to Issue [1103638][CR1103638].</span></span>


### <a name="compute-intersections-are-now-included-in-the-performance-tool"></a><span data-ttu-id="f96eb-226">计算交集现在包含在性能工具中</span><span class="sxs-lookup"><span data-stu-id="f96eb-226">Compute Intersections are now included in the Performance tool</span></span>

<span data-ttu-id="f96eb-227">在性能 **工具** 中，DevTools **现在在** 图表上显示计算交集。</span><span class="sxs-lookup"><span data-stu-id="f96eb-227">In the **Performance** tool, DevTools now displays **Compute Intersections** in the flame chart.</span></span> <span data-ttu-id="f96eb-228">这些更改可帮助你识别交集项事件并调试交集器的潜在性能开销。</span><span class="sxs-lookup"><span data-stu-id="f96eb-228">These changes help you identify intersection observers events and debug the potential performance overhead of intersection observers.</span></span>

:::image type="complex" source="../../media/2021/05/compute-intersections-in-perf-tool.msft.png" alt-text="性能工具中的计算交集" lightbox="../../media/2021/05/compute-intersections-in-perf-tool.msft.png":::
   <span data-ttu-id="f96eb-230">性能工具中的 **计算** 交集</span><span class="sxs-lookup"><span data-stu-id="f96eb-230">Compute Intersections in the **Performance** tool</span></span>
:::image-end:::

<!-- screenshot uses https://googlechrome.github.io/samples/intersectionobserver -->

<span data-ttu-id="f96eb-231">若要详细了解交集器，请导航到" [信任"，观察效果更好：Intersection Intersection v2][WebDevIntersectionObserverV2]。</span><span class="sxs-lookup"><span data-stu-id="f96eb-231">For more about intersection observers, navigate to [Trust is good, observation is better: Intersection Observer v2][WebDevIntersectionObserverV2].</span></span>  <span data-ttu-id="f96eb-232">有关使用饼图的信息，请导航到"[分析性能记录"。][DevtoolsEvaluatePerfRefAnalyzeAPerfRecording]</span><span class="sxs-lookup"><span data-stu-id="f96eb-232">For information about using the flame chart, navigate to [Analyze a performance recording][DevtoolsEvaluatePerfRefAnalyzeAPerfRecording].</span></span>  <span data-ttu-id="f96eb-233">若要在开放源代码项目中查看Chromium历史记录，请导航到"问题[1199137"。][CR1199137]</span><span class="sxs-lookup"><span data-stu-id="f96eb-233">To review the history of this feature in the Chromium open-source project, navigate to Issue [1199137][CR1199137].</span></span>


## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="f96eb-234">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="f96eb-234">Download the Microsoft Edge preview channels</span></span>

<span data-ttu-id="f96eb-235">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="f96eb-235">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="f96eb-236">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="f96eb-236">The preview channels give you access to the latest DevTools features.</span></span>


## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="f96eb-237">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="f96eb-237">Getting in touch with Microsoft Edge DevTools team</span></span>

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
> <span data-ttu-id="f96eb-258">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f96eb-258">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>
> <span data-ttu-id="f96eb-259">原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-xx)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="f96eb-259">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-xx) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>

<span data-ttu-id="f96eb-260">[ ![ Creative Commons License][CCby4Image]][CCA4IL] This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span><span class="sxs-lookup"><span data-stu-id="f96eb-260">[![Creative Commons License][CCby4Image]][CCA4IL] This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>

[CCA4IL]: https://creativecommons.org/licenses/by/4.0
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen
