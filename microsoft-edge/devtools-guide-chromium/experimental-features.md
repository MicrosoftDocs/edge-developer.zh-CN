---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验性功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: 731a289f555870eeff9cdc160965b59925b70c4d
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843935"
---
# <span data-ttu-id="0423c-104">实验性功能</span><span class="sxs-lookup"><span data-stu-id="0423c-104">Experimental features</span></span>  

<span data-ttu-id="0423c-105">你可以使用 Microsoft Edge DevTools 中仍处于开发阶段的实验功能来测试和[提供反馈](#providing-feedback-on-experimental-features)，然后再广泛发布。</span><span class="sxs-lookup"><span data-stu-id="0423c-105">You may use the experimental features that are still under development in the Microsoft Edge DevTools to test and [provide feedback](#providing-feedback-on-experimental-features) before each is released broadly.</span></span>  

<span data-ttu-id="0423c-106">尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。</span><span class="sxs-lookup"><span data-stu-id="0423c-106">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="0423c-107">启用实验功能</span><span class="sxs-lookup"><span data-stu-id="0423c-107">Turn on experimental features</span></span>  

<span data-ttu-id="0423c-108">使用以下步骤打开 Microsoft Edge 中的 "\" （或 "关闭 \"）实验功能。</span><span class="sxs-lookup"><span data-stu-id="0423c-108">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="0423c-109">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="0423c-109">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="0423c-110">按 `Control` + `Shift` + `I` \ （Windows \）或 `Command` + `Option` + `I` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="0423c-110">Press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="0423c-111">有关详细信息，请参阅[Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="0423c-111">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="0423c-112">打开 "**设置**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="0423c-112">Open the **Settings** pane.</span></span>  
    *   <span data-ttu-id="0423c-113">按 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="0423c-113">Press `Shift`+`?`.</span></span>  <span data-ttu-id="0423c-114">有关详细信息，请参阅[Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="0423c-114">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="0423c-115">在 "**设置**" 窗格的左侧，选择 "**实验**" 部分。</span><span class="sxs-lookup"><span data-stu-id="0423c-115">On the left side of the **Settings** pane, select the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.png":::
       <span data-ttu-id="0423c-117">DevTools 设置中的实验列表</span><span class="sxs-lookup"><span data-stu-id="0423c-117">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0423c-118">在 "**实验**" 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="0423c-118">On the **Experiments** page, scroll through the list of all available experimental features and select the checkbox next to each features that you want to test.</span></span>  
1.  <span data-ttu-id="0423c-119">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="0423c-119">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="0423c-120">实验性功能将不断更新，并可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="0423c-120">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="0423c-121">若要关闭实验功能，请打开 "**试验**" 页面，然后清除要关闭的实验功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="0423c-121">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="0423c-122">突出显示实验功能</span><span class="sxs-lookup"><span data-stu-id="0423c-122">Highlighted experimental features</span></span>  

<span data-ttu-id="0423c-123">以下部分介绍 Microsoft Edge 中可用的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="0423c-123">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="0423c-124">实验性功能</span><span class="sxs-lookup"><span data-stu-id="0423c-124">Experimental feature</span></span> | <span data-ttu-id="0423c-125">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="0423c-125">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="0423c-126">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="0423c-126">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="0423c-127">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="0423c-127">85 or later</span></span> |  
| [<span data-ttu-id="0423c-128">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="0423c-128">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="0423c-129">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="0423c-129">85 or later</span></span> |  
| [<span data-ttu-id="0423c-130">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="0423c-130">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="0423c-131">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="0423c-131">85 or later</span></span> |  

### <span data-ttu-id="0423c-132">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="0423c-132">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="0423c-133">在调试具有 CSS 网格布局的网站时，改善页面上的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="0423c-133">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="0423c-134">你可以在 DevTools 设置中进一步自定义覆盖。</span><span class="sxs-lookup"><span data-stu-id="0423c-134">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS 网格调试功能" lightbox="./media/experiments-grid.png":::
   <span data-ttu-id="0423c-136">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="0423c-136">CSS grid debugging feature</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="0423c-137">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="0423c-137">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="0423c-138">通常，**元素**和**网络**之类的工具只能在 DevTools 的 main \ （top \）面板中打开。</span><span class="sxs-lookup"><span data-stu-id="0423c-138">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="0423c-139">同样， **3D 视图**和**问题**之类的工具可能仅在 DevTools 的抽屉 \ （底部 \）面板中打开。</span><span class="sxs-lookup"><span data-stu-id="0423c-139">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="0423c-140">选择此实验后，你可以通过在选项卡上悬停，打开上下文菜单 \ （右键单击 \），然后选择 "**移到页首**" 或 "**移至底部**"，在顶部面板和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="0423c-140">When this experiment is selected, you may move tools between the top and bottom panels by hovering on the tab, opening the contextual menu \(right-click\), and selecting **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="0423c-141">此实验允许你自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="0423c-141">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="0423c-142">若要显示或隐藏底部面板，请按 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="0423c-142">To show or hide the bottom panel, press `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="在面板之间移动选项卡" lightbox="./media/experiments-move-panels.png":::
   <span data-ttu-id="0423c-144">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="0423c-144">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="0423c-145">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="0423c-145">Enable webhint</span></span>  

<span data-ttu-id="0423c-146">[webhint][WebhintMain]是一种开放源工具，可提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWAs 和其他常见 web 开发问题的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="0423c-146">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="0423c-147">此实验将 webhint 反馈带入 "[问题][DevtoolsIssues]" 面板中的 DevTools。</span><span class="sxs-lookup"><span data-stu-id="0423c-147">This experiment brings the webhint feedback into DevTools in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="0423c-148">你可以选择该问题以查看有关如何解决该问题的文档和你的网站上受影响的资源列表。</span><span class="sxs-lookup"><span data-stu-id="0423c-148">You may select the issue to see documentation on how to fix the issue and a list of the affected resources on your website.</span></span>  <span data-ttu-id="0423c-149">选择资源链接以打开 DevTools 中的相关**网络**、**源**或**元素**窗格。</span><span class="sxs-lookup"><span data-stu-id="0423c-149">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="./media/experiments-webhint.png":::
   <span data-ttu-id="0423c-151">"问题" 面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="0423c-151">webhint feedback in the Issues panel</span></span>  
:::image-end:::      

<!--Available in Microsoft Edge version 85 and later.  -->  

## <span data-ttu-id="0423c-152">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="0423c-152">Previous experimental features</span></span>  

*   <span data-ttu-id="0423c-153">[3D 视图][Devtools3DView]现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="0423c-153">[3D View][Devtools3DView] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  

## <span data-ttu-id="0423c-154">提供有关实验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="0423c-154">Providing feedback on experimental features</span></span>  

<span data-ttu-id="0423c-155">若要提供有关 Microsoft Edge DevTools 实验的反馈或与 DevTools 相关的任何其他内容，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0423c-155">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools:</span></span>  

*   <span data-ttu-id="0423c-156">使用 DevTools 中的反馈图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="0423c-156">Send your feedback using the Feedback icon in the DevTools</span></span>  
*   <span data-ttu-id="0423c-157">Tweet [@EdgeDevTools][TwitterEdgedevtools]</span><span class="sxs-lookup"><span data-stu-id="0423c-157">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/devtools-feedback.png" alt-text="Microsoft Edge DevTools 中的反馈图标" lightbox="./media/devtools-feedback.png":::
   <span data-ttu-id="0423c-159">Microsoft Edge DevTools 中的反馈图标</span><span class="sxs-lookup"><span data-stu-id="0423c-159">Feedback icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[Devtools3DView]: ./3D-view.md "3D 视图 |Microsoft 文档"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式-Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint" 
