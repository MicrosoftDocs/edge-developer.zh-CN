---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/21/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: 6b3e1c06d6b8ed79054c28df483fcca93e5751d6
ms.sourcegitcommit: 19ef1422733ef1fd051d2b4f0263ce191e8d67bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902852"
---
# <span data-ttu-id="c174a-104">实验功能</span><span class="sxs-lookup"><span data-stu-id="c174a-104">Experimental features</span></span>  

<span data-ttu-id="c174a-105">你可以使用 Microsoft Edge DevTools 中仍处于开发阶段的实验功能来测试和[提供反馈](#providing-feedback-on-experimental-features)，然后再广泛发布。</span><span class="sxs-lookup"><span data-stu-id="c174a-105">You may use the experimental features that are still under development in the Microsoft Edge DevTools to test and [provide feedback](#providing-feedback-on-experimental-features) before each is released broadly.</span></span>  

<span data-ttu-id="c174a-106">尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。</span><span class="sxs-lookup"><span data-stu-id="c174a-106">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="c174a-107">启用实验功能</span><span class="sxs-lookup"><span data-stu-id="c174a-107">Turn on experimental features</span></span>  

<span data-ttu-id="c174a-108">使用以下步骤打开 Microsoft Edge 中的 "\" （或 "关闭 \"）实验功能。</span><span class="sxs-lookup"><span data-stu-id="c174a-108">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="c174a-109">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="c174a-109">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="c174a-110">选择 `Control` + `Shift` + `I` \ （Windows \）或 `Command` + `Option` + `I` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="c174a-110">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="c174a-111">有关详细信息，请参阅[Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="c174a-111">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="c174a-112">打开 "[设置][DevToolsCustomizeSettings]" 窗格。</span><span class="sxs-lookup"><span data-stu-id="c174a-112">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="c174a-113">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="c174a-113">Select `Shift`+`?`.</span></span>  <span data-ttu-id="c174a-114">有关详细信息，请参阅[Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="c174a-114">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="c174a-115">在 "**设置**" 窗格的左侧，选择 "**实验**" 部分。</span><span class="sxs-lookup"><span data-stu-id="c174a-115">On the left side of the **Settings** pane, select the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.png":::
       <span data-ttu-id="c174a-117">DevTools 设置中的实验列表</span><span class="sxs-lookup"><span data-stu-id="c174a-117">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c174a-118">在 "**实验**" 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="c174a-118">On the **Experiments** page, scroll through the list of all available experimental features and select the checkbox next to each features that you want to test.</span></span>  
1.  <span data-ttu-id="c174a-119">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="c174a-119">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="c174a-120">实验性功能将不断更新，并可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="c174a-120">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="c174a-121">若要关闭实验功能，请打开 "**试验**" 页面，然后清除要关闭的实验功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="c174a-121">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="c174a-122">突出显示实验功能</span><span class="sxs-lookup"><span data-stu-id="c174a-122">Highlighted experimental features</span></span>  

<span data-ttu-id="c174a-123">以下部分介绍 Microsoft Edge 中可用的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="c174a-123">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="c174a-124">实验性功能</span><span class="sxs-lookup"><span data-stu-id="c174a-124">Experimental feature</span></span> | <span data-ttu-id="c174a-125">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="c174a-125">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="c174a-126">启用自定义键盘快捷方式设置选项卡</span><span class="sxs-lookup"><span data-stu-id="c174a-126">Enable custom keyboard shortcuts settings tab</span></span>](#enable-custom-keyboard-shortcuts-settings-tab) | <span data-ttu-id="c174a-127">84或更高版本</span><span class="sxs-lookup"><span data-stu-id="c174a-127">84 or later</span></span> |
| [<span data-ttu-id="c174a-128">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="c174a-128">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="c174a-129">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="c174a-129">85 or later</span></span> |  
| [<span data-ttu-id="c174a-130">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="c174a-130">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="c174a-131">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="c174a-131">85 or later</span></span> |  
| [<span data-ttu-id="c174a-132">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="c174a-132">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="c174a-133">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="c174a-133">85 or later</span></span> | 
| [<span data-ttu-id="c174a-134">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="c174a-134">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="c174a-135">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="c174a-135">85 or later</span></span> |

### <span data-ttu-id="c174a-136">启用自定义键盘快捷方式设置选项卡</span><span class="sxs-lookup"><span data-stu-id="c174a-136">Enable custom keyboard shortcuts settings tab</span></span>

<span data-ttu-id="c174a-137">在[DevTools 设置][DevToolsCustomizeSettings]中提供新的**快捷方式**页面，在 DevTools 中启用匹配的[键盘快捷方式][DevToolsShortcuts][与代码][VisualstudioCode]。</span><span class="sxs-lookup"><span data-stu-id="c174a-137">Provides a new **Shortcuts** page in [DevTools Settings][DevToolsCustomizeSettings] that enables matching [keyboard shortcuts][DevToolsShortcuts] in the DevTools to [VS Code][VisualstudioCode].</span></span>  

<span data-ttu-id="c174a-138">启用实验后，请使用 select 再次打开[DevTools 设置][DevToolsCustomizeSettings] `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="c174a-138">Once you have enabled the experiment, open [DevTools Settings][DevToolsCustomizeSettings] again using select `Shift`+`?`.</span></span>  <span data-ttu-id="c174a-139">导航到 "新建**快捷方式**" 页面。</span><span class="sxs-lookup"><span data-stu-id="c174a-139">Navigate to the new **Shortcuts** page.</span></span>  <span data-ttu-id="c174a-140">**从 "预设**" 下拉列表中选择 " **DevTools" （默认）** ，然后选择 " **Visual Studio 代码**"。</span><span class="sxs-lookup"><span data-stu-id="c174a-140">Select **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="c174a-141">DevTools 中的键盘快捷方式现在与与 VS 代码中的等效操作的快捷方式相匹配。</span><span class="sxs-lookup"><span data-stu-id="c174a-141">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in VS Code.</span></span>  

:::image type="complex" source="./media/experiments-keyboard-shortcut.png" alt-text="将 DevTools 中的键盘快捷方式与 VS 代码相匹配" lightbox="./media/experiments-keyboard-shortcut.png":::
   <span data-ttu-id="c174a-143">将 DevTools 中的键盘快捷方式与 VS 代码相匹配</span><span class="sxs-lookup"><span data-stu-id="c174a-143">Match keyboard shortcuts in the DevTools to VS Code</span></span>
:::image-end:::  

<span data-ttu-id="c174a-144">例如，在 Windows 上，在[VS 代码][VisualstudioCodeShortcutsKeyboardWindows]中暂停或继续运行脚本的键盘快捷方式是 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c174a-144">For example, on Windows the keyboard shortcut for pausing or continuing running a script in [VS Code][VisualstudioCodeShortcutsKeyboardWindows] is `F5`.</span></span>  <span data-ttu-id="c174a-145">通过**DevTools （默认）** 预设，DevTools 中的相同快捷方式 `F8` 。</span><span class="sxs-lookup"><span data-stu-id="c174a-145">With the **DevTools (Default)** preset, the same shortcut in the DevTools is `F8`.</span></span>  <span data-ttu-id="c174a-146">通过**Visual Studio 代码**预置，快捷方式也是 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c174a-146">With the **Visual Studio Code** preset, the shortcut is also `F5`.</span></span>  

### <span data-ttu-id="c174a-147">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="c174a-147">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="c174a-148">在调试具有 CSS 网格布局的网站时，改善页面上的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="c174a-148">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="c174a-149">你可以在 DevTools 设置中进一步自定义覆盖。</span><span class="sxs-lookup"><span data-stu-id="c174a-149">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS 网格调试功能" lightbox="./media/experiments-grid.png":::
   <span data-ttu-id="c174a-151">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="c174a-151">CSS grid debugging feature</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="c174a-152">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="c174a-152">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="c174a-153">通常，**元素**和**网络**之类的工具只能在 DevTools 的 main \ （top \）面板中打开。</span><span class="sxs-lookup"><span data-stu-id="c174a-153">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="c174a-154">同样， **3D 视图**和**问题**之类的工具可能仅在 DevTools 的抽屉 \ （底部 \）面板中打开。</span><span class="sxs-lookup"><span data-stu-id="c174a-154">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="c174a-155">选择实验后，你可以通过将工具悬停在选项卡上，打开上下文菜单 \ （右键单击 \），然后选择 "移到**页首**" 或 "**移至底部**"，在顶部和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="c174a-155">When you choose the experiment, you may move tools between the top and bottom panels by hovering on the tab, opening the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="c174a-156">此实验允许你自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="c174a-156">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="c174a-157">若要显示或隐藏底部面板，请选择 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="c174a-157">To show or hide the bottom panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="在面板之间移动选项卡" lightbox="./media/experiments-move-panels.png":::
   <span data-ttu-id="c174a-159">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="c174a-159">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="c174a-160">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="c174a-160">Enable webhint</span></span>  

<span data-ttu-id="c174a-161">[webhint][WebhintMain]是一种开放源工具，可提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWAs 和其他常见 web 开发问题的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="c174a-161">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="c174a-162">[Webhint][WebhintMain]实验将 webhint 反馈引入 "[问题][DevtoolsIssues]" 面板中的 DevTools。</span><span class="sxs-lookup"><span data-stu-id="c174a-162">The [webhint][WebhintMain] experiment brings the webhint feedback into DevTools in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="c174a-163">你可以选择该问题以查看有关如何解决该问题的文档和你的网站上受影响的资源列表。</span><span class="sxs-lookup"><span data-stu-id="c174a-163">You may select the issue to see documentation on how to fix the issue and a list of the affected resources on your website.</span></span>  <span data-ttu-id="c174a-164">选择资源链接以打开 DevTools 中的相关**网络**、**源**或**元素**窗格。</span><span class="sxs-lookup"><span data-stu-id="c174a-164">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="./media/experiments-webhint.png":::
   <span data-ttu-id="c174a-166">"问题" 面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="c174a-166">webhint feedback in the Issues panel</span></span>  
:::image-end:::      

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="c174a-167">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="c174a-167">Enable Network Console</span></span>

<span data-ttu-id="c174a-168">**网络控制台**是通过 HTTP 建立综合网络请求的实验的工作标题。</span><span class="sxs-lookup"><span data-stu-id="c174a-168">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="c174a-169">你可以使用**网络控制台**实验来发送 web API 请求。</span><span class="sxs-lookup"><span data-stu-id="c174a-169">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="c174a-170">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="c174a-170">After enabling the experiment, ensure you restart the DevTools.</span></span> <span data-ttu-id="c174a-171">要使用网络控制台，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c174a-171">To use the Network Console:</span></span>
1.  <span data-ttu-id="c174a-172">打开 "**网络**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="c174a-172">Open the **Network** pane.</span></span>
1.  <span data-ttu-id="c174a-173">查找要更改和重新发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="c174a-173">Find the network request that you want to change and resend.</span></span>
1.  <span data-ttu-id="c174a-174">打开上下文菜单 \ （右键单击 \），然后选择 "**编辑并重播**"。</span><span class="sxs-lookup"><span data-stu-id="c174a-174">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span> 
1.  <span data-ttu-id="c174a-175">当**网络控制台**打开时，请编辑网络请求信息。</span><span class="sxs-lookup"><span data-stu-id="c174a-175">When the **Network Console** opens, edit the network request information.</span></span>
1.  <span data-ttu-id="c174a-176">选择 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="c174a-176">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.png" alt-text="控制台抽屉中的网络控制台" lightbox="./media/network-network-console.png":::
<span data-ttu-id="c174a-178">控制台抽屉中的网络控制台</span><span class="sxs-lookup"><span data-stu-id="c174a-178">Network Console in the Console drawer</span></span>
:::image-end::: 

<!--Available in Microsoft Edge version 85 and later.  --> 

## <span data-ttu-id="c174a-179">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="c174a-179">Previous experimental features</span></span>  

*   <span data-ttu-id="c174a-180">[3D 视图][Devtools3dViewIndex]现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="c174a-180">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  

## <span data-ttu-id="c174a-181">提供有关实验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="c174a-181">Providing feedback on experimental features</span></span>  

<span data-ttu-id="c174a-182">提供有关 Microsoft Edge DevTools 实验的反馈或与 DevTools 相关的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="c174a-182">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="c174a-183">使用 DevTools 中的反馈图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="c174a-183">Send your feedback using the Feedback icon in the DevTools</span></span>  
*   <span data-ttu-id="c174a-184">Tweet [@EdgeDevTools][TwitterEdgedevtools]</span><span class="sxs-lookup"><span data-stu-id="c174a-184">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/devtools-feedback.png" alt-text="Microsoft Edge DevTools 中的反馈图标" lightbox="./media/devtools-feedback.png":::
   <span data-ttu-id="c174a-186">Microsoft Edge DevTools 中的反馈图标</span><span class="sxs-lookup"><span data-stu-id="c174a-186">Feedback icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D 视图 |Microsoft 文档"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualstudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "适用于 Windows 的 Visual Studio 代码键盘快捷方式 |Visual Studio 代码"  

[WebhintMain]: https://webhint.io "webhint" 
