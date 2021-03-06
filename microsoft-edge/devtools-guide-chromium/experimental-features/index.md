---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 实验
ms.openlocfilehash: b366cfeccafe874bc9e76d3b66659122c5d07c69
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398677"
---
# <a name="experimental-features"></a><span data-ttu-id="55380-104">实验功能</span><span class="sxs-lookup"><span data-stu-id="55380-104">Experimental features</span></span>  

<span data-ttu-id="55380-105">Microsoft Edge DevTools 提供对仍处于开发中的实验性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="55380-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="55380-106">您可以在发布每个 [功能之前](#providing-feedback-on-experimental-features) 进行测试并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="55380-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="55380-107">虽然实验功能在 Microsoft Edge 的所有频道中都可用，但你可能会使用 Microsoft Edge Canary 渠道获取最新的实验功能。</span><span class="sxs-lookup"><span data-stu-id="55380-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="55380-108">打开实验性功能</span><span class="sxs-lookup"><span data-stu-id="55380-108">Turn on experimental features</span></span>  

<span data-ttu-id="55380-109">若要在 Microsoft Edge 中打开 \ (或关闭\) 实验功能，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="55380-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="55380-110">[打开 DevTools。][DevtoolsOpenMain]</span><span class="sxs-lookup"><span data-stu-id="55380-110">[Open DevTools][DevtoolsOpenMain].</span></span>  
    *   <span data-ttu-id="55380-111">选择 `Control` + `Shift` + `I` \ (Windows、Linux\) `Command` + `Option` + `I` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="55380-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="55380-112">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="55380-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="55380-113">打开 ["设置"][DevToolsCustomizeIndexSettings] 窗格。</span><span class="sxs-lookup"><span data-stu-id="55380-113">Open the [Settings][DevToolsCustomizeIndexSettings] pane.</span></span>  
    *   <span data-ttu-id="55380-114">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="55380-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="55380-115">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="55380-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="55380-116">在"设置"窗格 **的** 左侧，选择" **实验"** 部分。</span><span class="sxs-lookup"><span data-stu-id="55380-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text=""设置"中的"实验"页" lightbox="../media/experiments-devtools.msft.png":::
       <span data-ttu-id="55380-118">" **设置"** 中的"实验" **页**</span><span class="sxs-lookup"><span data-stu-id="55380-118">The **Experiments** page in **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="55380-119">在 **"实验** "页上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="55380-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="55380-120">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="55380-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="55380-121">实验性功能会不断更新，并可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="55380-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="55380-122">若要关闭实验功能，请打开"实验\*\*\*\*"页并清除要关闭的实验功能复选框。</span><span class="sxs-lookup"><span data-stu-id="55380-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <a name="highlighted-experimental-features"></a><span data-ttu-id="55380-123">突出显示的实验功能</span><span class="sxs-lookup"><span data-stu-id="55380-123">Highlighted experimental features</span></span>  

<span data-ttu-id="55380-124">以下各节介绍了 Microsoft Edge 中可用的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="55380-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="55380-125">实验性功能</span><span class="sxs-lookup"><span data-stu-id="55380-125">Experimental feature</span></span> | <span data-ttu-id="55380-126">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="55380-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="55380-127">启用 Webhint</span><span class="sxs-lookup"><span data-stu-id="55380-127">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="55380-128">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-128">85 or later</span></span> |  
| [<span data-ttu-id="55380-129">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="55380-129">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="55380-130">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-130">85 or later</span></span> |  
| [<span data-ttu-id="55380-131">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="55380-131">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="55380-132">86 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-132">86 or later</span></span> |  
| [<span data-ttu-id="55380-133">启用键盘快捷方式编辑器</span><span class="sxs-lookup"><span data-stu-id="55380-133">Enable keyboard shortcut editor</span></span>](#enable-keyboard-shortcut-editor) | <span data-ttu-id="55380-134">87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-134">87 or later</span></span> |  
| [<span data-ttu-id="55380-135">在 3D 视图中启用复合层</span><span class="sxs-lookup"><span data-stu-id="55380-135">Enable Composited Layers in 3D View</span></span>](#enable-composited-layers-in-3d-view) | <span data-ttu-id="55380-136">87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-136">87 or later</span></span> |  
| [<span data-ttu-id="55380-137">在"样式"窗格中启用新的字体编辑器工具</span><span class="sxs-lookup"><span data-stu-id="55380-137">Enable new Font Editor tool within the Styles pane</span></span>](#enable-new-font-editor-tool-within-the-styles-pane) | <span data-ttu-id="55380-138">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-138">89 or later</span></span> |  
| [<span data-ttu-id="55380-139">启用新的 CSS Flexbox 调试功能</span><span class="sxs-lookup"><span data-stu-id="55380-139">Enable new CSS Flexbox debugging features</span></span>](#enable-new-css-flexbox-debugging-features) | <span data-ttu-id="55380-140">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-140">89 or later</span></span> |  
| [<span data-ttu-id="55380-141">启用 + 按钮选项卡菜单以打开更多工具</span><span class="sxs-lookup"><span data-stu-id="55380-141">Enable + button tab menus to open more tools</span></span>](#enable--button-tab-menus-to-open-more-tools) | <span data-ttu-id="55380-142">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-142">89 or later</span></span> |  
| [<span data-ttu-id="55380-143">启用欢迎选项卡</span><span class="sxs-lookup"><span data-stu-id="55380-143">Enable Welcome tab</span></span>](#enable-welcome-tool) | <span data-ttu-id="55380-144">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="55380-144">89 or later</span></span> |  

### <a name="enable-new-css-grid-debugging-features"></a><span data-ttu-id="55380-145">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="55380-145">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="55380-146">此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS 网格布局。</span><span class="sxs-lookup"><span data-stu-id="55380-146">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="55380-147">若要预览最新的实验功能，请 [启用此实验](#turn-on-experimental-features) 并重新加载 DevTools。</span><span class="sxs-lookup"><span data-stu-id="55380-147">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="55380-148">此实验在 Microsoft Edge 版本 87 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="55380-148">This experiment is on by default in Microsoft Edge version 87 or later.</span></span>  

#### <a name="viewing-on-hover-grid-overlays-with-the-inspect-tool"></a><span data-ttu-id="55380-149">使用"检查"工具查看悬停网格覆盖</span><span class="sxs-lookup"><span data-stu-id="55380-149">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="55380-150">检查 **工具** 提供了一种通过将鼠标悬停在网站中的 CSS 网格布局来标识和可视化这些布局的快速方法。</span><span class="sxs-lookup"><span data-stu-id="55380-150">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="55380-151">Choose the **Inspect** \ (![ Inspect ](../media/inspect-icon.msft.png) \) icon in the top-left corner of DevTools.</span><span class="sxs-lookup"><span data-stu-id="55380-151">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="55380-152">然后，将鼠标 `Grid` 悬停在正在调试的网页上的某个元素上。</span><span class="sxs-lookup"><span data-stu-id="55380-152">Then, hover on a `Grid` element on the webpage you are debugging.</span></span>  <span data-ttu-id="55380-153">大纲显示在网格周围，并且对齐指示网格间隙的位置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="55380-153">Outlines are displayed around the grid, and hatching indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="../media/grid-inspect.msft.png" alt-text="使用检查工具查看网格" lightbox="../media/grid-inspect.msft.png":::
   <span data-ttu-id="55380-155">使用检查工具 **查看** 网格</span><span class="sxs-lookup"><span data-stu-id="55380-155">Viewing grids with the **Inspect** tool</span></span>  
:::image-end:::  

#### <a name="viewing-persistent-grid-overlays"></a><span data-ttu-id="55380-156">查看持久网格覆盖</span><span class="sxs-lookup"><span data-stu-id="55380-156">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="55380-157">在 Microsoft Edge 版本 86 或更高版本中，实验性 CSS 网格功能还提供了启用持久网格覆盖的选项。</span><span class="sxs-lookup"><span data-stu-id="55380-157">In Microsoft Edge version 86 or later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="55380-158">持久覆盖具有多个优势。</span><span class="sxs-lookup"><span data-stu-id="55380-158">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="55380-159">滚动、移动鼠标并使用 DevTools 的其他功能时，持久覆盖在页面上仍然可见。</span><span class="sxs-lookup"><span data-stu-id="55380-159">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="55380-160">可以同时打开多个永久性覆盖，从而允许您一次查看多个网格布局。</span><span class="sxs-lookup"><span data-stu-id="55380-160">Multiple persistent overlays may be turned on at the same time, allowing you to review several grid layouts at once.</span></span>  
*   <span data-ttu-id="55380-161">持久覆盖提供了许多配置选项，例如隐藏或显示网格区域中的名称、网格间隙、轨大小等。</span><span class="sxs-lookup"><span data-stu-id="55380-161">Persistent overlays offer many configuration options, such as hiding or showing names in the grid area, grid gaps, track sizes, and so on.</span></span>  
    
<span data-ttu-id="55380-162">切换持久网格覆盖的两种方法。</span><span class="sxs-lookup"><span data-stu-id="55380-162">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="55380-163">选择 **"元素"** 工具的 DOM 树中显示的任何 Grid 元素旁边的" **网格"椭圆** 图标。</span><span class="sxs-lookup"><span data-stu-id="55380-163">Choose the **Grid** oval icon next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="../media/grid-adorner.msft.png" alt-text="元素工具中的网格椭圆图标" lightbox="../media/grid-adorner.msft.png":::
       <span data-ttu-id="55380-165">元素工具中的 **网格** 椭圆图标</span><span class="sxs-lookup"><span data-stu-id="55380-165">Grid oval icon in **Elements** tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="55380-166">打开位于 **"元素** "工具中的新布局面板，然后选择要突出显示的每个 Grid 元素旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="55380-166">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="../media/grid-layout-zoom.msft.png" alt-text="DevTools 中的布局面板" lightbox="../media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="55380-168">\*\*\*\* DevTools 中的布局面板</span><span class="sxs-lookup"><span data-stu-id="55380-168">**Layout** panel in DevTools</span></span>  
    :::image-end:::  
    
#### <a name="configuring-persistent-overlays"></a><span data-ttu-id="55380-169">配置永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="55380-169">Configuring persistent overlays</span></span>  

<span data-ttu-id="55380-170">在 Microsoft Edge 版本 86\*\*\*\* 或更高版本中，新的布局面板位于 **"** 元素"工具中以及"**样式**"和"**计算"** 面板中。</span><span class="sxs-lookup"><span data-stu-id="55380-170">In Microsoft Edge version 86 or later, the new **Layout** panel is located in the **Elements** tool alongside the **Styles** and **Computed** panels.</span></span>  <span data-ttu-id="55380-171">布局 **面板** 显示持久覆盖的配置选项。</span><span class="sxs-lookup"><span data-stu-id="55380-171">The **Layout** panel surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="../media/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../media/experiments-grid.msft.png":::
   <span data-ttu-id="55380-173">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="55380-173">CSS grid debugging feature</span></span>  
:::image-end:::  

### <a name="enable-support-to-move-tabs-between-panels"></a><span data-ttu-id="55380-174">支持在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="55380-174">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="55380-175">通常，**元素和网络等**工具只能在位于\*\*\*\* DevTools 顶部的主面板中打开。</span><span class="sxs-lookup"><span data-stu-id="55380-175">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="55380-176">工具（**如 3D 视图**和问题）通常仅在位于\*\*\*\* DevTools 底部的"箱"面板中打开。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="55380-176">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="55380-177">选择实验后，您可以在顶部和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="55380-177">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="55380-178">若要移动工具，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击\) ，然后选择"移动到顶部"或"\*\*\*\* 移动到**底部"。**</span><span class="sxs-lookup"><span data-stu-id="55380-178">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="55380-179">此实验允许你自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="55380-179">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="55380-180">若要显示或隐藏 **"箱"面板** ，请选择 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="55380-180">To display or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="../media/experiments-move-panels.msft.png" alt-text="在面板之间移动工具" lightbox="../media/experiments-move-panels.msft.png":::
   <span data-ttu-id="55380-182">在面板之间移动工具</span><span class="sxs-lookup"><span data-stu-id="55380-182">Moving tools between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-webhint"></a><span data-ttu-id="55380-183">启用 Webhint</span><span class="sxs-lookup"><span data-stu-id="55380-183">Enable webhint</span></span>  

<span data-ttu-id="55380-184">[webhint][WebhintMain] 是一个开源工具，可为网站和本地网页提供实时反馈。</span><span class="sxs-lookup"><span data-stu-id="55380-184">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="55380-185">Webhint 提供 [的反馈类型][WebhintMain]。</span><span class="sxs-lookup"><span data-stu-id="55380-185">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="55380-186">辅助功能</span><span class="sxs-lookup"><span data-stu-id="55380-186">accessibility</span></span>  
*   <span data-ttu-id="55380-187">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="55380-187">cross-browser compatibility</span></span>  
*   <span data-ttu-id="55380-188">安全性</span><span class="sxs-lookup"><span data-stu-id="55380-188">security</span></span>  
*   <span data-ttu-id="55380-189">性能</span><span class="sxs-lookup"><span data-stu-id="55380-189">performance</span></span>  
*   <span data-ttu-id="55380-190">渐进式 Web 应用 (PWA) </span><span class="sxs-lookup"><span data-stu-id="55380-190">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="55380-191">其他常见的 Web 开发问题</span><span class="sxs-lookup"><span data-stu-id="55380-191">other common web development issues</span></span>  
    
<span data-ttu-id="55380-192">[Webhint 实验][WebhintMain]在"问题"面板中显示[Webhint][DevtoolsIssues]反馈。</span><span class="sxs-lookup"><span data-stu-id="55380-192">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="55380-193">选择一个问题，在网站上显示解决方案文档和受影响的资源列表。</span><span class="sxs-lookup"><span data-stu-id="55380-193">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="55380-194">选择资源链接以在 DevTools**中**打开\*\*\*\* 相关的"**网络**、源"或"元素"窗格。</span><span class="sxs-lookup"><span data-stu-id="55380-194">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../media/experiments-webhint.msft.png":::
   <span data-ttu-id="55380-196">问题面板中的 **webhint** 反馈</span><span class="sxs-lookup"><span data-stu-id="55380-196">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-network-console"></a><span data-ttu-id="55380-197">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="55380-197">Enable Network Console</span></span>  

<span data-ttu-id="55380-198">**网络控制台** 是实验的工作主题，它通过 HTTP 提出综合网络请求。</span><span class="sxs-lookup"><span data-stu-id="55380-198">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="55380-199">可以使用网络 **控制台** 实验发送 Web API 请求。</span><span class="sxs-lookup"><span data-stu-id="55380-199">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="55380-200">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="55380-200">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="55380-201">若要使用 **网络控制台**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="55380-201">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="55380-202">打开 **"网络"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="55380-202">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="55380-203">查找要更改和重新发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="55380-203">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="55380-204">打开上下文菜单 \ (右键单击\) ，然后选择"编辑和**重播"。**</span><span class="sxs-lookup"><span data-stu-id="55380-204">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="55380-205">当 **网络控制台打开** 时，编辑网络请求信息。</span><span class="sxs-lookup"><span data-stu-id="55380-205">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="55380-206">选择 **"发送"。**</span><span class="sxs-lookup"><span data-stu-id="55380-206">Choose **Send**.</span></span>  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="控制台箱中的网络控制台" lightbox="../media/network-network-console.msft.png":::
   <span data-ttu-id="55380-208">**控制台箱\*\*\*\*中的网络**控制台</span><span class="sxs-lookup"><span data-stu-id="55380-208">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="source-order-viewer"></a><span data-ttu-id="55380-209">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="55380-209">Source Order Viewer</span></span>  

<span data-ttu-id="55380-210">**源订单查看器** 是显示网页源中元素顺序的实验。</span><span class="sxs-lookup"><span data-stu-id="55380-210">**Source Order Viewer** is an experiment that displays the order of elements in the webpage source.</span></span>  <span data-ttu-id="55380-211">屏幕显示顺序可能与源的顺序不同，这会使屏幕阅读器和键盘用户混淆。</span><span class="sxs-lookup"><span data-stu-id="55380-211">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="55380-212">使用 **源顺序查看器** 实验可查找屏幕显示顺序和源顺序之间的差异。</span><span class="sxs-lookup"><span data-stu-id="55380-212">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="55380-213">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="55380-213">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="55380-214">若要使用 **源订单查看器**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="55380-214">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="55380-215">打开 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="55380-215">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="55380-216">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span><span class="sxs-lookup"><span data-stu-id="55380-216">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="55380-217">在" **源订单查看器** "部分下，选中 **"显示源订单"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="55380-217">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="55380-218">突出显示任何 HTML 元素以显示网页源中订单的覆盖层。</span><span class="sxs-lookup"><span data-stu-id="55380-218">Highlight any HTML element to display an overlay that the order in the webpage source.</span></span>  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="辅助功能窗格中的源订单查看器" lightbox="../media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="55380-220">**辅助功能窗格中\*\*\*\*的源订单查看器**</span><span class="sxs-lookup"><span data-stu-id="55380-220">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <a name="enable-keyboard-shortcut-editor"></a><span data-ttu-id="55380-221">启用键盘快捷方式编辑器</span><span class="sxs-lookup"><span data-stu-id="55380-221">Enable keyboard shortcut editor</span></span>

<span data-ttu-id="55380-222">打开 **"启用键盘快捷方式编辑器** "实验后，你可以为 DevTools 中的任何操作自定义键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="55380-222">With the **Enable keyboard shortcut editor** experiment turned on, you may customize keyboard shortcuts for any action in the DevTools.</span></span>  <span data-ttu-id="55380-223">若要自定义特定操作键盘快捷方式，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="55380-223">To customize the keyboard shortcut for a specific action, complete the following steps.</span></span>  

1.  <span data-ttu-id="55380-224">[打开 DevTools。][DevtoolsOpenMain]</span><span class="sxs-lookup"><span data-stu-id="55380-224">[Open DevTools][DevtoolsOpenMain].</span></span>  
1.  <span data-ttu-id="55380-225">打开["设置"。][DevToolsCustomizeIndexSettings]</span><span class="sxs-lookup"><span data-stu-id="55380-225">Open [Settings][DevToolsCustomizeIndexSettings].</span></span>  
    *   <span data-ttu-id="55380-226">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="55380-226">Select `Shift`+`?`.</span></span>  
1.  <span data-ttu-id="55380-227">导航到 **"快捷方式"** 页。</span><span class="sxs-lookup"><span data-stu-id="55380-227">Navigate to the **Shortcuts** page.</span></span>  
1.  <span data-ttu-id="55380-228">选择要自定义的操作。</span><span class="sxs-lookup"><span data-stu-id="55380-228">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="55380-229">Choose the **Edit** \ (![ EditKeyboardShortcut ](../media/edit-keyboard-shortcut-icon.msft.png) \) icon.</span><span class="sxs-lookup"><span data-stu-id="55380-229">Choose the **Edit** \(![EditKeyboardShortcut](../media/edit-keyboard-shortcut-icon.msft.png)\) icon.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="从"设置"中的"快捷方式"页选择要自定义的操作" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       <span data-ttu-id="55380-231">从"设置"中的"快捷方式 **"页选择要** 自定义 [的操作][DevToolsCustomizeIndexSettings]</span><span class="sxs-lookup"><span data-stu-id="55380-231">Choose the action to customize from the **Shortcuts** page in [Settings][DevToolsCustomizeIndexSettings]</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="55380-232">在键盘上，选择要绑定到该操作的键。</span><span class="sxs-lookup"><span data-stu-id="55380-232">On the keyboard, select the keys to bind to the action.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="选择要分配给该操作的键" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="55380-234">选择要分配给该操作的键</span><span class="sxs-lookup"><span data-stu-id="55380-234">Choose the keys you want to assign to the action</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="55380-235">若要保存新的键盘快捷方式，请选择选中标记 \ (</span><span class="sxs-lookup"><span data-stu-id="55380-235">To save your new keyboard shortcut, choose the checkmark \(</span></span>![CheckmarkKeyboardShortcut](../media/checkmark-keyboard-shortcut-icon.msft.png)<span data-ttu-id="55380-237">\) 图标。</span><span class="sxs-lookup"><span data-stu-id="55380-237">\) icon.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="选择选中标记图标以保存新的键盘快捷方式" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="55380-239">选择选中标记图标以保存新的键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="55380-239">Choose the checkmark icon to save your new keyboard shortcut</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="55380-240">选择新的键盘快捷方式以触发 DevTools 中的操作。</span><span class="sxs-lookup"><span data-stu-id="55380-240">Select your new keyboard shortcut to trigger the action in the DevTools.</span></span>  
    
<span data-ttu-id="55380-241">在 **"快捷方式"** 页上 **，自定义键盘** 快捷方式 \ (![ CustomKeyboardShortcut ](../media/custom-keyboard-shortcut-icon.msft.png) \) 图标显示自定义的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="55380-241">On the **Shortcuts** page, the **Custom Keyboard Shortcut** \(![CustomKeyboardShortcut](../media/custom-keyboard-shortcut-icon.msft.png)\) icon displays keyboard shortcuts you customized.</span></span>  <span data-ttu-id="55380-242">若要重置所有快捷方式，请选择"**还原默认快捷方式"。**</span><span class="sxs-lookup"><span data-stu-id="55380-242">To reset all shortcuts, choose **Restore default shortcuts**.</span></span>  

<span data-ttu-id="55380-243">若要在编辑操作键盘快捷方式时放弃所做的更改，请选择 X \ (![ XKeyboardShortcut ](../media/discard-changes-keyboard-shortcut-icon.msft.png) \) 图标。</span><span class="sxs-lookup"><span data-stu-id="55380-243">To discard your changes while you edit the keyboard shortcuts for an action, choose the X \(![XKeyboardShortcut](../media/discard-changes-keyboard-shortcut-icon.msft.png)\) icon.</span></span>  <span data-ttu-id="55380-244">若要删除特定操作快捷方式，请选择"删除"快捷方式 **\ (** ![ DeleteKeyboardShortcut ](../media/delete-keyboard-shortcut-icon.msft.png) \) 图标。</span><span class="sxs-lookup"><span data-stu-id="55380-244">To remove shortcuts for a specific action, choose the **Delete shortcut** \(![DeleteKeyboardShortcut](../media/delete-keyboard-shortcut-icon.msft.png)\) icon.</span></span>  <span data-ttu-id="55380-245">若要为操作添加多个快捷方式，请选择"**添加快捷方式"。**</span><span class="sxs-lookup"><span data-stu-id="55380-245">To add multiple shortcuts for an action, choose **Add a shortcut**.</span></span>  

> [!NOTE]
> <span data-ttu-id="55380-246">如果键盘快捷方式当前已分配给另一个操作，则不能将其保存以用于新操作。</span><span class="sxs-lookup"><span data-stu-id="55380-246">If a keyboard shortcut is currently assigned to another action, you may not save it for a new action.</span></span>  <span data-ttu-id="55380-247">必须先删除上一个操作的键盘快捷方式，然后将其添加到新操作。</span><span class="sxs-lookup"><span data-stu-id="55380-247">You must first delete the keyboard shortcut for the previous action and then add it to the new action.</span></span>  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-composited-layers-in-3d-view"></a><span data-ttu-id="55380-248">在 3D 视图中启用复合层</span><span class="sxs-lookup"><span data-stu-id="55380-248">Enable Composited Layers in 3D View</span></span>  

<span data-ttu-id="55380-249">现在，您可以可视化 Z 索引和文档对象模型 \ (DOM\) 。</span><span class="sxs-lookup"><span data-stu-id="55380-249">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="55380-250">此功能可帮助您在不经常切换上下文的情况下进行调试。</span><span class="sxs-lookup"><span data-stu-id="55380-250">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="55380-251">您确定减少上下文切换是一个主要的难点。</span><span class="sxs-lookup"><span data-stu-id="55380-251">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="55380-252">您编写的代码对 Web 应用有何影响并不总是明确的。</span><span class="sxs-lookup"><span data-stu-id="55380-252">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="55380-253">为获得全面的视觉调试体验， 已将3D 视图和复合层组合到一起。</span><span class="sxs-lookup"><span data-stu-id="55380-253">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  

<span data-ttu-id="55380-254">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="55380-254">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="55380-255">若要使用 **复合层**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="55380-255">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="55380-256">在"3D 视图"工具 **上，选择"3D 视图"** 工具。</span><span class="sxs-lookup"><span data-stu-id="55380-256">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="55380-257">打开 **"复合层"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="55380-257">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="55380-258">将显示应用的所有绘制层。</span><span class="sxs-lookup"><span data-stu-id="55380-258">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="55380-259">使用你自己的 Web 应用试用此功能。</span><span class="sxs-lookup"><span data-stu-id="55380-259">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="55380-261">**复合层** 窗格</span><span class="sxs-lookup"><span data-stu-id="55380-261">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-new-font-editor-tool-within-the-styles-pane"></a><span data-ttu-id="55380-262">在"样式"窗格中启用新的字体编辑器工具</span><span class="sxs-lookup"><span data-stu-id="55380-262">Enable new Font Editor tool within the Styles pane</span></span>  

<span data-ttu-id="55380-263">现在可以使用新的可视 [字体编辑器][DevtoolsInspectStylesEditFonts] 编辑字体。</span><span class="sxs-lookup"><span data-stu-id="55380-263">You may now use the new visual [Font Editor][DevtoolsInspectStylesEditFonts] to edit fonts.</span></span>  <span data-ttu-id="55380-264">使用它定义字体和字体特征。</span><span class="sxs-lookup"><span data-stu-id="55380-264">Use it define fonts and font characteristics.</span></span>  <span data-ttu-id="55380-265">可视 **字体编辑器** 可帮助您完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="55380-265">The visual **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="55380-266">在不同字体属性的单位之间切换</span><span class="sxs-lookup"><span data-stu-id="55380-266">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="55380-267">在不同字体属性的关键字之间切换</span><span class="sxs-lookup"><span data-stu-id="55380-267">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="55380-268">转换单位</span><span class="sxs-lookup"><span data-stu-id="55380-268">Convert units</span></span>  
*   <span data-ttu-id="55380-269">生成准确的 CSS 代码</span><span class="sxs-lookup"><span data-stu-id="55380-269">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="55380-270">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="55380-270">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="55380-271">若要使用新的可视 **字体编辑器**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="55380-271">To use the new visual **Font Editor**, complete the following steps.</span></span>  

1.  <span data-ttu-id="55380-272">打开 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="55380-272">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="55380-273">打开 **"样式"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="55380-273">Open the **Styles** pane.</span></span>  
1.  <span data-ttu-id="55380-274">选择 **字体编辑器** 图标。</span><span class="sxs-lookup"><span data-stu-id="55380-274">Choose the **Font Editor** icon.</span></span>  
    
<span data-ttu-id="55380-275">有关新的可视字体编辑器的详细信息，\*\*\*\* 请导航到 DevTools 的"样式"窗格中的"编辑[CSS 字体样式和设置"。][DevtoolsInspectStylesEditFonts]</span><span class="sxs-lookup"><span data-stu-id="55380-275">For more information about the new visual **Font Editor**, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="突出显示可视字体编辑器窗格" lightbox="../media/font-editor-open.msft.png":::
   <span data-ttu-id="55380-277">突出显示 **可视字体编辑器** 窗格</span><span class="sxs-lookup"><span data-stu-id="55380-277">The visual **Font Editor** pane is highlighted</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-new-css-flexbox-debugging-features"></a><span data-ttu-id="55380-278">启用新的 CSS Flexbox 调试功能</span><span class="sxs-lookup"><span data-stu-id="55380-278">Enable new CSS Flexbox debugging features</span></span>  

<span data-ttu-id="55380-279">此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS 弹性框布局。</span><span class="sxs-lookup"><span data-stu-id="55380-279">This experimental feature provides many new visualizations to help you debug CSS Flexbox layouts.</span></span>  <span data-ttu-id="55380-280">若要预览最新的实验功能，请 [打开此实验](#turn-on-experimental-features) 并重新加载 DevTools。</span><span class="sxs-lookup"><span data-stu-id="55380-280">To preview the latest experimental features, [turn on this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a><span data-ttu-id="55380-281">使用检查工具在 Flexbox 布局上显示永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="55380-281">Display persistent overlays on Flexbox layouts with the Inspect tool</span></span>  

<span data-ttu-id="55380-282">检查 **工具** 提供了一种通过将鼠标悬停在网站中的 CSS 弹性框布局来识别并可视化它们的快速方法。</span><span class="sxs-lookup"><span data-stu-id="55380-282">The **Inspect** tool provides a quick way to identify and visualize CSS Flexbox layouts in a website by hovering on them with the mouse.</span></span>  <span data-ttu-id="55380-283">Choose the **Inspect** \ (![ Inspect ](../media/inspect-icon.msft.png) \) icon in the top-left corner of DevTools.</span><span class="sxs-lookup"><span data-stu-id="55380-283">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="55380-284">然后，在调试网站时，将鼠标悬停在弹性容器上，以在弹性容器周围显示轮廓。</span><span class="sxs-lookup"><span data-stu-id="55380-284">Then, while debugging the website, hover on a flex container to display outlines around the flex container.</span></span>  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="使用检查工具显示 Flexbox 容器" lightbox="../media/flexbox-hover.msft.png":::
   <span data-ttu-id="55380-286">使用检查工具显示 Flexbox**容器**</span><span class="sxs-lookup"><span data-stu-id="55380-286">Display Flexbox containers with the **Inspect** tool</span></span>  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a><span data-ttu-id="55380-287">在 Flexbox 布局上显示永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="55380-287">Display persistent overlays on Flexbox layouts</span></span>  

<span data-ttu-id="55380-288">在 Microsoft Edge 版本 89 或更高版本中，实验性 CSS Flexbox 功能还提供了在 Flexbox 布局上打开永久性覆盖的选项。</span><span class="sxs-lookup"><span data-stu-id="55380-288">In Microsoft Edge version 89 or later, the experimental CSS Flexbox feature also offers the option to turn on persistent overlays on Flexbox layouts.</span></span>  <span data-ttu-id="55380-289">持久覆盖具有以下优点。</span><span class="sxs-lookup"><span data-stu-id="55380-289">Persistent overlays provide the following benefits.</span></span>  

*   <span data-ttu-id="55380-290">滚动、移动鼠标和使用 DevTools 的其他功能时，永久性覆盖在网页上仍然可见。</span><span class="sxs-lookup"><span data-stu-id="55380-290">Persistent overlays remain visible on the webpage as you scroll, move your mouse, and use other features of the DevTools.</span></span>
*   <span data-ttu-id="55380-291">可以同时使用多个永久性覆盖，以便一次查看多个 Flexbox 布局。</span><span class="sxs-lookup"><span data-stu-id="55380-291">Multiple persistent overlays may be used at the same time, to allow you to review several Flexbox layouts at once.</span></span>  
*   <span data-ttu-id="55380-292">持久覆盖提供颜色配置选项。</span><span class="sxs-lookup"><span data-stu-id="55380-292">Persistent overlays offer color configuration options.</span></span>  
    
<span data-ttu-id="55380-293">若要在 Flexbox 布局上切换永久性覆盖，请使用下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="55380-293">To toggle persistent overlays on Flexbox layout, use one of following actions.</span></span>  

*   <span data-ttu-id="55380-294">选择 **"元素"** 工具的 DOM 树中显示的任意 Flexbox 容器旁边的 Flexbox **椭圆图标** 。</span><span class="sxs-lookup"><span data-stu-id="55380-294">Choose the **Flexbox** oval icon next to any Flexbox container displayed in the DOM tree of the **Elements** tool.</span></span>  
*   <span data-ttu-id="55380-295">打开位于 **"元素**"工具中的新布局\*\*\*\* 面板，然后选择要突出显示的每个 Flexbox 容器旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="55380-295">Open the new **Layout** panel located in the **Elements** tool, and choose the checkbox next to each Flexbox container you want to highlight.</span></span>  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools 中的弹性图标和布局面板" lightbox="../media/flexbox-overlay.msft.png":::
   <span data-ttu-id="55380-297">DevTools 中的弹性图标和布局面板\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="55380-297">Flex icons and **Layout** panel in DevTools</span></span>  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a><span data-ttu-id="55380-298">配置永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="55380-298">Configure persistent overlays</span></span>  

<span data-ttu-id="55380-299">若要为 CSS 网格或 Flexbox 布局配置永久覆盖的选项，请使用"布局 **"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="55380-299">To configure options for persistent overlays for CSS grids or Flexbox layouts, use the **Layout** pane.</span></span>  <span data-ttu-id="55380-300">"**布局**"窗格位于"样式"\*\*\*\* 和"计算"窗格\*\*\*\* 旁边的"元素 **"工具**中。</span><span class="sxs-lookup"><span data-stu-id="55380-300">The **Layout** pane is located in the **Elements** tool next to the **Styles** and **Computed** panes.</span></span>  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="布局面板" lightbox="../media/flexbox-layout.msft.png":::
   <span data-ttu-id="55380-302">布局面板</span><span class="sxs-lookup"><span data-stu-id="55380-302">Layout panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable--button-tab-menus-to-open-more-tools"></a><span data-ttu-id="55380-303">启用 + 按钮选项卡菜单以打开更多工具</span><span class="sxs-lookup"><span data-stu-id="55380-303">Enable + button tab menus to open more tools</span></span>  

<span data-ttu-id="55380-304">现在，可以使用新的"更多工具"\ (\*\*\*\* `+` \) 图标打开更多工具。</span><span class="sxs-lookup"><span data-stu-id="55380-304">You may now open more tools using the new **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="55380-305">打开"启用 **+"** 按钮选项卡菜单以打开更多工具实验并重新加载 DevTools 后，在 DevTools 顶部的选项卡组右侧显示加号 `+` \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="55380-305">After you turn on the **Enable + button tab menus to open more tools** experiment and reload DevTools, a plus sign \(`+`\) displays to the right of the tab group at the top of the DevTools.</span></span>  <span data-ttu-id="55380-306">若要显示可添加到选项卡栏的其他工具的列表，请选择新的"更多工具"\ (\*\*\*\* `+` \) 图标。</span><span class="sxs-lookup"><span data-stu-id="55380-306">To display a list of other tools that you may add to the tab bar, choose the new **More Tools** \(`+`\) icon.</span></span>  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="顶部窗格中的更多工具" lightbox="../media/experiments-more-tools-button.msft.png":::
   <span data-ttu-id="55380-308">**顶部窗格中** 的更多工具</span><span class="sxs-lookup"><span data-stu-id="55380-308">**More Tools** in the top pane</span></span>
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-welcome-tool"></a><span data-ttu-id="55380-309">启用欢迎工具</span><span class="sxs-lookup"><span data-stu-id="55380-309">Enable Welcome tool</span></span>

<span data-ttu-id="55380-310">此实验将" **新增功能"** 工具替换为新的 **欢迎** 工具。</span><span class="sxs-lookup"><span data-stu-id="55380-310">This experiment replaces the **What's New** tool with the new **Welcome** tool.</span></span>  <span data-ttu-id="55380-311">它显示以下内容的刷新设计。</span><span class="sxs-lookup"><span data-stu-id="55380-311">It displays a refreshed design for the following content.</span></span>  

*   <span data-ttu-id="55380-312">指向开发人员文档的链接</span><span class="sxs-lookup"><span data-stu-id="55380-312">Links to developer docs</span></span>  
*   <span data-ttu-id="55380-313">最新功能</span><span class="sxs-lookup"><span data-stu-id="55380-313">the latest features</span></span>  
*   <span data-ttu-id="55380-314">发行说明</span><span class="sxs-lookup"><span data-stu-id="55380-314">release notes</span></span>  
*   <span data-ttu-id="55380-315">联系 Microsoft Edge DevTools 团队的选项</span><span class="sxs-lookup"><span data-stu-id="55380-315">Option to contact the Microsoft Edge DevTools team</span></span>  
    
<span data-ttu-id="55380-316">每次 **更新** 到 Microsoft Edge 后，欢迎工具都会自动打开。</span><span class="sxs-lookup"><span data-stu-id="55380-316">The **Welcome** tool opens automatically after each update to Microsoft Edge.</span></span>  <span data-ttu-id="55380-317">若要防止每次更新后显示\*\*\*\* 欢迎工具，请清除"欢迎"工具标题下\*\*\*\* 每个更新后"打开"选项卡**旁边的**复选框。</span><span class="sxs-lookup"><span data-stu-id="55380-317">To prevent the display of the **Welcome** tool after each update, clear the checkbox next to **Open tab after each update** under the **Welcome** tool title.</span></span>  

<span data-ttu-id="55380-318">如果你更喜欢原始**的**新增功能工具，请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"并删除"  >  \*\*\*\* 启用欢迎"**选项卡旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="55380-318">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="欢迎工具" lightbox="../media/experiments-welcome.msft.png":::
   <span data-ttu-id="55380-320">**欢迎** 工具</span><span class="sxs-lookup"><span data-stu-id="55380-320">**Welcome** tool</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a><span data-ttu-id="55380-321">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="55380-321">Previous experimental features</span></span>  

*   <span data-ttu-id="55380-322">[3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本 83 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="55380-322">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="55380-323">[在 Microsoft][DevtoolsMoveTabs] Edge 版本 85 或更高版本中，现已启用支持以在面板之间移动选项卡，默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="55380-323">[Turn on support to move tabs between panels][DevtoolsMoveTabs] is now available and turned on by default in Microsoft Edge version 85 or later.</span></span>  
*   <span data-ttu-id="55380-324">[自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在可用，在 Microsoft Edge 版本 86 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="55380-324">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  
*   <span data-ttu-id="55380-325">[模拟：支持双屏模式][DevtoolsDeviceModeDualScreenAndFoldables] 现在可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="55380-325">[Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="55380-326">[在][DevtoolsCssGrid] Microsoft Edge 版本 89 或更高版本中，现已提供并默认打开新的 CSS 网格调试功能。</span><span class="sxs-lookup"><span data-stu-id="55380-326">[Turn on new CSS grid debugging features][DevtoolsCssGrid] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
    
## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="55380-327">提供有关实验性功能的反馈</span><span class="sxs-lookup"><span data-stu-id="55380-327">Providing feedback on experimental features</span></span>  

<span data-ttu-id="55380-328">提供有关 Microsoft Edge DevTools 实验或与 DevTools 相关的任何其他内容的反馈。</span><span class="sxs-lookup"><span data-stu-id="55380-328">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="55380-329">使用 DevTools 中的 **"发送反馈** "图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="55380-329">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="55380-330">向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文</span><span class="sxs-lookup"><span data-stu-id="55380-330">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="55380-332">Microsoft Edge DevTools 中的“**发送反馈**”图标</span><span class="sxs-lookup"><span data-stu-id="55380-332">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D 视图 | Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsMoveTabs]: ../customize/index.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools |Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "在 DevTools | 的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsIssues]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏幕 Web 体验|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用接点 - 双屏设备简介|Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "用于双屏幕检测的 CSS 媒体屏幕|Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "百分百折|Samsung"  
[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "在 Microsoft Edge DevTools |Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
