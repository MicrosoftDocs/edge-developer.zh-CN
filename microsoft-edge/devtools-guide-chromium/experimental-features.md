---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/25/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: a5793b6f4b67add313958ad4b8cee01cb7b09dbf
ms.sourcegitcommit: 7e3644e6b1d568ab795168e421c013814efa0073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996157"
---
# <span data-ttu-id="02670-104">实验功能</span><span class="sxs-lookup"><span data-stu-id="02670-104">Experimental features</span></span>  

<span data-ttu-id="02670-105">你可以使用 Microsoft Edge DevTools 中仍处于开发阶段的实验功能来测试和 [提供反馈](#providing-feedback-on-experimental-features) ，然后再广泛发布。</span><span class="sxs-lookup"><span data-stu-id="02670-105">You may use the experimental features that are still under development in the Microsoft Edge DevTools to test and [provide feedback](#providing-feedback-on-experimental-features) before each is released broadly.</span></span>  

<span data-ttu-id="02670-106">尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。</span><span class="sxs-lookup"><span data-stu-id="02670-106">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="02670-107">启用实验功能</span><span class="sxs-lookup"><span data-stu-id="02670-107">Turn on experimental features</span></span>  

<span data-ttu-id="02670-108">使用以下步骤打开 Microsoft Edge 中的 " (" 或 "关闭" ) 实验功能。</span><span class="sxs-lookup"><span data-stu-id="02670-108">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="02670-109">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="02670-109">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="02670-110">选择 `Control` + `Shift` + `I` \ (Windows \ ) 或 `Command` + `Option` + `I` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="02670-110">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="02670-111">有关详细信息，请参阅 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="02670-111">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="02670-112">打开 " [设置][DevToolsCustomizeSettings] " 窗格。</span><span class="sxs-lookup"><span data-stu-id="02670-112">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="02670-113">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="02670-113">Select `Shift`+`?`.</span></span>  <span data-ttu-id="02670-114">有关详细信息，请参阅 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="02670-114">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="02670-115">在 " **设置** " 窗格的左侧，选择 " **实验** " 部分。</span><span class="sxs-lookup"><span data-stu-id="02670-115">On the left side of the **Settings** pane, select the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.png":::
       <span data-ttu-id="02670-117">DevTools 设置中的实验列表</span><span class="sxs-lookup"><span data-stu-id="02670-117">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="02670-118">在 " **实验** " 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="02670-118">On the **Experiments** page, scroll through the list of all available experimental features and select the checkbox next to each features that you want to test.</span></span>  
1.  <span data-ttu-id="02670-119">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="02670-119">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="02670-120">实验性功能将不断更新，并可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="02670-120">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="02670-121">若要关闭实验功能，请打开 " **试验** " 页面，然后清除要关闭的实验功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="02670-121">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="02670-122">突出显示实验功能</span><span class="sxs-lookup"><span data-stu-id="02670-122">Highlighted experimental features</span></span>  

<span data-ttu-id="02670-123">以下部分介绍 Microsoft Edge 中可用的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="02670-123">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="02670-124">实验性功能</span><span class="sxs-lookup"><span data-stu-id="02670-124">Experimental feature</span></span> | <span data-ttu-id="02670-125">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="02670-125">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="02670-126">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="02670-126">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="02670-127">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="02670-127">85 or later</span></span> |  
| [<span data-ttu-id="02670-128">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="02670-128">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="02670-129">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="02670-129">85 or later</span></span> |  
| [<span data-ttu-id="02670-130">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="02670-130">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="02670-131">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="02670-131">85 or later</span></span> |  
| [<span data-ttu-id="02670-132">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="02670-132">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="02670-133">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="02670-133">85 or later</span></span> |  
| [<span data-ttu-id="02670-134">启用源订单查看器</span><span class="sxs-lookup"><span data-stu-id="02670-134">Enable Source Order Viewer</span></span>](#enable-source-order-viewer) | <span data-ttu-id="02670-135">86或更高版本</span><span class="sxs-lookup"><span data-stu-id="02670-135">86 or later</span></span> |  

### <span data-ttu-id="02670-136">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="02670-136">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="02670-137">在调试具有 CSS 网格布局的网站时，改善页面上的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="02670-137">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="02670-138">你可以在 DevTools 设置中进一步自定义覆盖。</span><span class="sxs-lookup"><span data-stu-id="02670-138">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS 网格调试功能" lightbox="./media/experiments-grid.png":::
   <span data-ttu-id="02670-140">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="02670-140">CSS grid debugging feature</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="02670-141">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="02670-141">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="02670-142">通常， **元素** 和 **网络** 之类的工具可能仅在 DevTools 的 main \ (top \ ) 面板中打开。</span><span class="sxs-lookup"><span data-stu-id="02670-142">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="02670-143">同样， **3D 视图** 和 **问题** 之类的工具可能仅在 DevTools 的 "抽屉" (底部 \ ) 面板中打开。</span><span class="sxs-lookup"><span data-stu-id="02670-143">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="02670-144">选择实验后，你可以通过在选项卡上悬停在选项卡上，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **移到页首** " 或 " **移至底部**"，在顶部面板和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="02670-144">When you choose the experiment, you may move tools between the top and bottom panels by hovering on the tab, opening the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="02670-145">此实验允许你自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="02670-145">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="02670-146">若要显示或隐藏底部面板，请选择 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="02670-146">To show or hide the bottom panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="在面板之间移动选项卡" lightbox="./media/experiments-move-panels.png":::
   <span data-ttu-id="02670-148">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="02670-148">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="02670-149">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="02670-149">Enable webhint</span></span>  

<span data-ttu-id="02670-150">[webhint][WebhintMain] 是一种开放源工具，可提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWAs 和其他常见 web 开发问题的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="02670-150">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="02670-151">[Webhint][WebhintMain]实验将 webhint 反馈引入 "[问题][DevtoolsIssues]" 面板中的 DevTools。</span><span class="sxs-lookup"><span data-stu-id="02670-151">The [webhint][WebhintMain] experiment brings the webhint feedback into DevTools in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="02670-152">你可以选择该问题以查看有关如何解决该问题的文档和你的网站上受影响的资源列表。</span><span class="sxs-lookup"><span data-stu-id="02670-152">You may select the issue to see documentation on how to fix the issue and a list of the affected resources on your website.</span></span>  <span data-ttu-id="02670-153">选择资源链接以打开 DevTools 中的相关 **网络**、 **源**或 **元素** 窗格。</span><span class="sxs-lookup"><span data-stu-id="02670-153">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="./media/experiments-webhint.png":::
   <span data-ttu-id="02670-155">" **问题** " 面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="02670-155">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="02670-156">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="02670-156">Enable Network Console</span></span>  

<span data-ttu-id="02670-157">**网络控制台** 是通过 HTTP 建立综合网络请求的实验的工作标题。</span><span class="sxs-lookup"><span data-stu-id="02670-157">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="02670-158">你可以使用 **网络控制台** 实验来发送 web API 请求。</span><span class="sxs-lookup"><span data-stu-id="02670-158">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="02670-159">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="02670-159">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="02670-160">要使用网络控制台，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02670-160">To use the Network Console:</span></span>  

1.  <span data-ttu-id="02670-161">打开 " **网络** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="02670-161">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="02670-162">查找要更改和重新发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="02670-162">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="02670-163">打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **编辑并重播**"。</span><span class="sxs-lookup"><span data-stu-id="02670-163">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="02670-164">当 **网络控制台** 打开时，请编辑网络请求信息。</span><span class="sxs-lookup"><span data-stu-id="02670-164">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="02670-165">选择 " **发送**"。</span><span class="sxs-lookup"><span data-stu-id="02670-165">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.png" alt-text="控制台抽屉中的网络控制台" lightbox="./media/network-network-console.png":::
   <span data-ttu-id="02670-167">**控制台**抽屉中的**网络控制台**</span><span class="sxs-lookup"><span data-stu-id="02670-167">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  --> 

### <span data-ttu-id="02670-168">启用源订单查看器</span><span class="sxs-lookup"><span data-stu-id="02670-168">Enable Source Order Viewer</span></span>  

<span data-ttu-id="02670-169">**源顺序查看器** 是实验的工作标题，用于在页面源中显示元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="02670-169">**Source Order Viewer** is the working title of an experiment to display the order of elements in the page source.</span></span>  <span data-ttu-id="02670-170">你可以使用 **源顺序查看器** 实验查找页面中的辅助功能问题，因为显示顺序在屏幕上可能与源的顺序不同，迷惑屏幕阅读器用户。</span><span class="sxs-lookup"><span data-stu-id="02670-170">You may use the **Source Order Viewer** experiment to find accessibility issues in your pages since the display order on-screen may differ from the order of the source, which confuses screen reader users.</span></span>  

<span data-ttu-id="02670-171">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="02670-171">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="02670-172">要使用源订单查看器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02670-172">To use Source Order Viewer:</span></span>  

1.  <span data-ttu-id="02670-173">打开 " **元素** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="02670-173">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="02670-174">打开抽屉 \ (底部 \ ) 面板中的 " **辅助功能** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="02670-174">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="02670-175">在 " **源顺序查看器** " 部分中，选中 " **显示源顺序** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="02670-175">Under the **Source Order Viewer** section, select the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="02670-176">突出显示任何 HTML 元素以显示页面源中顺序的覆盖图。</span><span class="sxs-lookup"><span data-stu-id="02670-176">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text=""辅助功能" 窗格中的 "源顺序查看器"" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="02670-178">"**辅助功能**" 窗格中的 "**源顺序查看器**"</span><span class="sxs-lookup"><span data-stu-id="02670-178">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## <span data-ttu-id="02670-179">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="02670-179">Previous experimental features</span></span>  

*   <span data-ttu-id="02670-180">[3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="02670-180">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="02670-181">[自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在在 Microsoft Edge 版本86或更高版本中可用且默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="02670-181">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>
## <span data-ttu-id="02670-182">提供有关实验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="02670-182">Providing feedback on experimental features</span></span>  

<span data-ttu-id="02670-183">提供有关 Microsoft Edge DevTools 实验的反馈或与 DevTools 相关的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="02670-183">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="02670-184">使用 DevTools 中的 " **发送反馈** " 图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="02670-184">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="02670-185">向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文</span><span class="sxs-lookup"><span data-stu-id="02670-185">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>   

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的 "发送反馈" 图标" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="02670-187">Microsoft Edge DevTools 中的 " **发送反馈** " 图标</span><span class="sxs-lookup"><span data-stu-id="02670-187">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D 视图 |Microsoft 文档"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint" 
