---
description: 在 Windows 高对比度模式中使用 DevTools，将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配，以及更多。
title: DevTools (Microsoft Edge 84) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 2752dec8bc7c4eec34ddde05a7dedff7bebef05f
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015487"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="36fa0-104">DevTools (Microsoft Edge 84) 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="36fa0-104">What's new in DevTools (Microsoft Edge 84)</span></span>  

## <span data-ttu-id="36fa0-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="36fa0-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="36fa0-106">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="36fa0-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="36fa0-107">查看它们以尝试 DevTools、Visual Studio 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="36fa0-107">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="36fa0-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="36fa0-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="36fa0-109">在 Windows 高对比度模式下使用 DevTools</span><span class="sxs-lookup"><span data-stu-id="36fa0-109">Use the DevTools in Windows high contrast mode</span></span>

<span data-ttu-id="36fa0-110">Microsoft Edge DevTools 现在在 Windows 处于高对比度模式下显示为高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="36fa0-110">The Microsoft Edge DevTools are now displayed in high contrast mode when Windows is in high contrast mode.</span></span>  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/high-contrast.msft.png":::
   <span data-ttu-id="36fa0-112">高对比度模式下的 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="36fa0-112">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-113">[按照说明在 Windows 中打开 "高对比度" 模式][MicrosoftSupportWindows10HighContrastMode]。</span><span class="sxs-lookup"><span data-stu-id="36fa0-113">[Follow the instructions to turn on high contrast mode in Windows][MicrosoftSupportWindows10HighContrastMode].</span></span>  <span data-ttu-id="36fa0-114">通过按或，在 Microsoft Edge 中打开 DevTools `F12` `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="36fa0-114">Open the DevTools in Microsoft Edge by pressing `F12` or `Ctrl`+`Shift`+`I`.</span></span>  <span data-ttu-id="36fa0-115">DevTools 在 "高对比度" 模式下显示。</span><span class="sxs-lookup"><span data-stu-id="36fa0-115">The DevTools are displayed in high contrast mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="36fa0-116">Microsoft Edge DevTools 目前支持 Windows 上的高对比度模式，但不支持 macOS 上的高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="36fa0-116">The Microsoft Edge DevTools currently support high contrast mode on Windows but not on macOS.</span></span> 

<span data-ttu-id="36fa0-117">Chromium 问题 [#1048378][CR1048378]</span><span class="sxs-lookup"><span data-stu-id="36fa0-117">Chromium issue [#1048378][CR1048378]</span></span>  

### <span data-ttu-id="36fa0-118">将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配</span><span class="sxs-lookup"><span data-stu-id="36fa0-118">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  

<span data-ttu-id="36fa0-119">从你的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team) 和 [Chromium 公共问题跟踪][CRIssuesList]器开始，Microsoft Edge DevTools 团队发现你希望能够在 DevTools 中自定义键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="36fa0-119">From your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) and the [Chromium public issue tracker][CRIssuesList], the Microsoft Edge DevTools team learned that you wanted the ability to customize keyboard shortcuts in the DevTools.</span></span>  <span data-ttu-id="36fa0-120">在 Microsoft Edge 84 中，你现在可以将 DevTools 中的键盘快捷方式与 [Visual Studio 代码][VSCode]匹配，这只是团队在为快捷方式自定义而处理的功能之一。</span><span class="sxs-lookup"><span data-stu-id="36fa0-120">In Microsoft Edge 84, you are now able to match keyboard shortcuts in the DevTools to [Visual Studio Code][VSCode], which is just one of the features the team is working on for shortcut customization.</span></span>  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   <span data-ttu-id="36fa0-122">高对比度模式下的 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="36fa0-122">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-123">若要尝试实验，请按下 "DevTools" `?` 或选择 ![ ][ImageSettingsIcon] DevTools 右上角的 DevTools "设置" 图标来打开 "设置"。</span><span class="sxs-lookup"><span data-stu-id="36fa0-123">To try the experiment, open DevTools Settings by pressing `?` or selecting the ![DevTools Settings icon][ImageSettingsIcon] icon in the top-right corner of the DevTools.</span></span>  <span data-ttu-id="36fa0-124">导航到 " **实验** " 部分，然后选中 \*\*"启用自定义键盘快捷方式设置" 选项卡， (需要重新加载) \*\*。</span><span class="sxs-lookup"><span data-stu-id="36fa0-124">Navigate to the **Experiments** section and check **Enable custom keyboard shortcuts settings tab (requires reload)**.</span></span>  <span data-ttu-id="36fa0-125">现在重新加载 DevTools，再次打开 "设置"，然后导航到 " **快捷方式** " 部分。</span><span class="sxs-lookup"><span data-stu-id="36fa0-125">Now reload the DevTools, open Settings again, and navigate to the **Shortcuts** section.</span></span>  

<span data-ttu-id="36fa0-126">选择 " **)  (DevTools** " 中的 "选择"，然后选择 "**匹配预设的快捷方式**" 下拉列表，然后选择**Visual Studio 代码**</span><span class="sxs-lookup"><span data-stu-id="36fa0-126">Select **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="36fa0-127">DevTools 中的键盘快捷方式现在与 Visual Studio 代码中等效操作的快捷方式相匹配。</span><span class="sxs-lookup"><span data-stu-id="36fa0-127">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in Visual Studio Code.</span></span>  

<span data-ttu-id="36fa0-128">例如，在 [Visual Studio 代码][VSCodeShortcuts] 中暂停或继续运行脚本的键盘快捷方式是 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="36fa0-128">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VSCodeShortcuts] is `F5`.</span></span>  <span data-ttu-id="36fa0-129">通过 \*\*DevTools (Default) \*\* 预置，DevTools 中的同一快捷方式， `F8` 但在 **Visual Studio 代码** 中，该快捷方式现在也是如此 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="36fa0-129">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8` but with the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="36fa0-130">此功能目前可在 Microsoft Edge 84 中提供，因此请与团队分享你的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！</span><span class="sxs-lookup"><span data-stu-id="36fa0-130">The feature is currently available in Microsoft Edge 84 as an experiment, so please share your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) with the team!</span></span>  

<span data-ttu-id="36fa0-131">Chromium 问题 [#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="36fa0-131">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="36fa0-132">远程调试 Surface 双核模拟器</span><span class="sxs-lookup"><span data-stu-id="36fa0-132">Remote debug Surface Duo emulators</span></span>  

<span data-ttu-id="36fa0-133">现在，你可以使用[Microsoft Edge DevTools][DevToolsChromiumGuide]的完整功能远程调试[Surface 双核处理器技术][DualScreensAndroidEmulator]中运行的 web 内容。</span><span class="sxs-lookup"><span data-stu-id="36fa0-133">You are now able to remotely debug your web content running in the [Surface Duo emulator][DualScreensAndroidEmulator] using the full power of the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

<span data-ttu-id="36fa0-134">借助 [Surface 双核模拟器][DualScreensAndroidEmulator]，你可以测试 web 内容在新的折叠和双屏幕设备上的呈现方式。</span><span class="sxs-lookup"><span data-stu-id="36fa0-134">With the [Surface Duo emulator][DualScreensAndroidEmulator], you are able to test how your web content renders on a new class of foldable and dual-screen devices.</span></span>  <span data-ttu-id="36fa0-135">仿真器运行 Android 操作系统并提供 [Microsoft Edge Android 应用][AndroidEdge]。</span><span class="sxs-lookup"><span data-stu-id="36fa0-135">The emulator runs the Android operating system and provides the [Microsoft Edge Android app][AndroidEdge].</span></span>  <span data-ttu-id="36fa0-136">在 [Microsoft edge 应用][AndroidEdge] 中加载你的 web 内容，并将其与 [microsoft edge DevTools][DevToolsChromiumGuide]进行调试。</span><span class="sxs-lookup"><span data-stu-id="36fa0-136">Load your web content in the [Microsoft Edge app][AndroidEdge] and debug it with the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="在 Surface 双核模拟器上运行的 Microsoft Edge 应用" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   <span data-ttu-id="36fa0-138">Surface 双核模拟器上的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="36fa0-138">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-139">`edge://inspect` [Microsoft Edge][DesktopEdge]桌面实例中的页面显示**SurfaceDuoEmulator** ，其中列出了在[Surface 双核仿真器][DualScreensAndroidEmulator]上运行的打开的选项卡或[PWAs][PwaIndex] 。</span><span class="sxs-lookup"><span data-stu-id="36fa0-139">The `edge://inspect` page in a desktop instance of [Microsoft Edge][DesktopEdge] shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaIndex] that are running on the [Surface Duo emulator][DualScreensAndroidEmulator].</span></span>  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="Edge://inspect 页面显示在仿真器上运行的 Microsoft Edge 应用中打开的选项卡的列表" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   <span data-ttu-id="36fa0-141">`edge://inspect`页面显示在仿真器上运行的 Microsoft Edge 应用中打开的选项卡的列表</span><span class="sxs-lookup"><span data-stu-id="36fa0-141">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>
:::image-end:::  

<span data-ttu-id="36fa0-142">为要调试的选项卡或 PWA 选择 " **检查** " 将打开 " [Microsoft Edge DevTools][DevToolsChromiumGuide]"。</span><span class="sxs-lookup"><span data-stu-id="36fa0-142">Selecting **inspect** for the tab or PWA that you want to debug opens the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  <span data-ttu-id="36fa0-143">[按照分步指南，在 Surface 双核模拟器上远程调试 web 内容][DevToolsRemoteDebugDuoEmulator]。</span><span class="sxs-lookup"><span data-stu-id="36fa0-143">[Follow the step-by-step guide to remotely debug your web content on the Surface Duo emulator][DevToolsRemoteDebugDuoEmulator].</span></span>  

### <span data-ttu-id="36fa0-144">更轻松地调整 DevTools 抽屉的大小</span><span class="sxs-lookup"><span data-stu-id="36fa0-144">Resize the DevTools drawer more easily</span></span>  

<span data-ttu-id="36fa0-145">在 Microsoft Edge 83 或更早版本中，你只能通过将 [DevTools 抽屉][DevToolsDrawer] 悬停在抽屉的工具栏内来调整其大小。</span><span class="sxs-lookup"><span data-stu-id="36fa0-145">In Microsoft Edge 83 or earlier, you were only able to resize the [DevTools Drawer][DevToolsDrawer] by hovering inside the Drawer's toolbar.</span></span>  <span data-ttu-id="36fa0-146">抽屉的行为与 DevTools 中的窗格的其他调整控件的行为不同，您将鼠标悬停在窗格边框上以调整其大小。</span><span class="sxs-lookup"><span data-stu-id="36fa0-146">The Drawer behaved differently than the other resize controls for panes in the DevTools where you hover over the border of the pane to resize it.</span></span>  <span data-ttu-id="36fa0-147">选择下图以查看如何在版本83或更早版本的 Microsoft Edge 中调整抽屉的大小。</span><span class="sxs-lookup"><span data-stu-id="36fa0-147">Select the following image to see how resizing the Drawer worked in version 83 or earlier of Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="在 Microsoft Edge 83 中调整 DevTools 抽屉的大小" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   <span data-ttu-id="36fa0-149">在 Microsoft Edge 83 中调整 DevTools 抽屉的大小</span><span class="sxs-lookup"><span data-stu-id="36fa0-149">Resizing the DevTools Drawer in Microsoft Edge 83</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="36fa0-150">从 Microsoft Edge 84 开始，您现在可以通过将抽屉悬停在抽屉的边框上来调整抽屉的大小。</span><span class="sxs-lookup"><span data-stu-id="36fa0-150">Starting with Microsoft Edge 84, you are now able to resize the Drawer by hovering over the border of the Drawer.</span></span>  <span data-ttu-id="36fa0-151">此更改将 DevTools 抽屉大小的行为与 DevTools 中的其他窗格调整大小的方式对齐。</span><span class="sxs-lookup"><span data-stu-id="36fa0-151">This change aligns the behavior resizing the DevTools Drawer with the way you resize other panes in the DevTools.</span></span>  <span data-ttu-id="36fa0-152">选择以下图像以查看 Microsoft Edge 84 中的 "操作调整大小"。</span><span class="sxs-lookup"><span data-stu-id="36fa0-152">Select the following image to see resizing in action in Microsoft Edge 84.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="在 Microsoft Edge 84 中调整 DevTools 抽屉的大小" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   <span data-ttu-id="36fa0-154">在 Microsoft Edge 84 中调整 DevTools 抽屉的大小</span><span class="sxs-lookup"><span data-stu-id="36fa0-154">Resizing the DevTools Drawer in Microsoft Edge 84</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="36fa0-155">Chromium 问题 [#1076112][CR1076112]</span><span class="sxs-lookup"><span data-stu-id="36fa0-155">Chromium issue [#1076112][CR1076112]</span></span>  

### <span data-ttu-id="36fa0-156">Screencasting 导航按钮显示焦点</span><span class="sxs-lookup"><span data-stu-id="36fa0-156">Screencasting navigation buttons display focus</span></span>  

<span data-ttu-id="36fa0-157">当远程调试 [Android 设备][DevToolsRemoteDebugAndroid]、 [Windows 10 设备][DevToolsRemoteDebugWindows]或 [Surface 双核模拟器][DevToolsRemoteDebugDuoEmulator]时，可以使用 ![ DevTools 左上角的 "切换说明截屏视频" 图标切换 screencasting ][ImageScreencastingIcon] 。</span><span class="sxs-lookup"><span data-stu-id="36fa0-157">When remote debugging an [Android device][DevToolsRemoteDebugAndroid], a [Windows 10 device][DevToolsRemoteDebugWindows], or a [Surface Duo emulator][DevToolsRemoteDebugDuoEmulator], you are able to toggle screencasting with the ![Toggle Screencast][ImageScreencastingIcon] icon in the top-left corner of the DevTools.</span></span>  <span data-ttu-id="36fa0-158">如果启用了 screencasting，你可以从 DevTools 窗口中的远程设备上的 Microsoft Edge 中导航选项卡。</span><span class="sxs-lookup"><span data-stu-id="36fa0-158">With screencasting enabled, you are able to navigate the tab in Microsoft Edge on the remote device from the DevTools window.</span></span>  <span data-ttu-id="36fa0-159">在 Microsoft Edge 84 中，这些导航按钮现在也可通过键盘访问。</span><span class="sxs-lookup"><span data-stu-id="36fa0-159">In Microsoft Edge 84, these navigation buttons are now also keyboard accessible.</span></span>  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="按 screencasted URL 栏中的 Shift + Tab 将焦点显示在 "刷新" 按钮上" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   <span data-ttu-id="36fa0-161">按 `Shift` + `Tab` screencasted URL 栏中的说明将焦点放在 "**刷新**" 按钮上</span><span class="sxs-lookup"><span data-stu-id="36fa0-161">Pressing `Shift`+`Tab` from the screencasted URL bar shows focus on the **Refresh** button</span></span>
:::image-end:::  

<span data-ttu-id="36fa0-162">Chromium 问题 [#1081486][CR1081486]</span><span class="sxs-lookup"><span data-stu-id="36fa0-162">Chromium issue [#1081486][CR1081486]</span></span>  

### <span data-ttu-id="36fa0-163">现在可以访问网络面板的详细信息窗格</span><span class="sxs-lookup"><span data-stu-id="36fa0-163">Network panel Details pane is now accessible</span></span>  

<span data-ttu-id="36fa0-164">在 Microsoft Edge 84 中，当您为[网络日志][DevToolsNetworkLog]中的资源打开 "**网络**" 面板中的 "[详细信息" 窗格][DevToolsNetworkDetails]时，它们现在将获得焦点。</span><span class="sxs-lookup"><span data-stu-id="36fa0-164">In Microsoft Edge 84, the [Details pane][DevToolsNetworkDetails] in the **Network** panel now takes focus when you open it for a resource in the [Network Log][DevToolsNetworkLog].</span></span>  <span data-ttu-id="36fa0-165">此更改允许屏幕阅读器读出 " **详细信息** " 窗格的内容并与之交互。</span><span class="sxs-lookup"><span data-stu-id="36fa0-165">This change allows screen readers to read out and interact with the content of the **Details** pane.</span></span>  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text=""网络" 面板中的 "详细信息" 窗格在打开时获得焦点" lightbox="../../media/2020/05/network-details.msft.png":::
   <span data-ttu-id="36fa0-167">"**网络**" 面板中的 "**详细信息**" 窗格在打开时获得焦点</span><span class="sxs-lookup"><span data-stu-id="36fa0-167">The **Details** pane in the **Network** panel takes focus when opened</span></span>
:::image-end:::  

<span data-ttu-id="36fa0-168">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="36fa0-168">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="36fa0-169">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="36fa0-169">Announcements from the Chromium project</span></span>  

<span data-ttu-id="36fa0-170">以下各节宣布了在 Microsoft Edge 84 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。</span><span class="sxs-lookup"><span data-stu-id="36fa0-170">The following sections announce additional features available in Microsoft Edge 84 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="36fa0-171">通过 DevTools 抽屉中的新问题工具修复网站问题</span><span class="sxs-lookup"><span data-stu-id="36fa0-171">Fix site issues with the new Issues tool in the DevTools Drawer</span></span>

<span data-ttu-id="36fa0-172">DevTools 抽屉中的 "新建 **问题** " 工具可帮助减少 **控制台**的通知 fatigue 和混乱。</span><span class="sxs-lookup"><span data-stu-id="36fa0-172">The new **Issues** tool in the DevTools Drawer was built to help reduce the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="36fa0-173">当前，该 **控制台** 是网站开发人员、库、框架和 Microsoft Edge 的中心位置，用于记录消息、警告和错误。</span><span class="sxs-lookup"><span data-stu-id="36fa0-173">Currently, the **Console** is the central place for website developers, libraries, frameworks, and Microsoft Edge to log messages, warnings, and errors.</span></span>  <span data-ttu-id="36fa0-174">" **问题** " 工具将来自浏览器的警告聚合到 Microsoft Edge DevTools 中受影响的资源的链接，并提供有关如何解决这些问题的指南。</span><span class="sxs-lookup"><span data-stu-id="36fa0-174">The **Issues** tool aggregates warnings from the browser in a structured, aggregated, and actionable way, links to affected resources within Microsoft Edge DevTools, and provides guidance on how to fix the issues.</span></span>  <span data-ttu-id="36fa0-175">随着时间的推移，你应在 " **问题** " 工具（而不是 **控制台**）的 Microsoft Edge 呈现形式中看到更多警告，这有助于减少在 **控制台**中的混乱。</span><span class="sxs-lookup"><span data-stu-id="36fa0-175">Over time, you should see more and more warnings in Microsoft Edge surfacing in the **Issues** tool rather than the **Console**, which should help reduce the clutter in the **Console**.</span></span>  

<span data-ttu-id="36fa0-176">若要开始使用，请参阅 [查找并修复 Microsoft Edge DevTools 问题工具的相关问题][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="36fa0-176">To get started, see [Find And Fix Problems With The Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools 抽屉中的 "问题" 工具" lightbox="../../media/2020/05/issues.msft.png":::
   <span data-ttu-id="36fa0-178">DevTools 抽屉中的 " **问题** " 工具</span><span class="sxs-lookup"><span data-stu-id="36fa0-178">The **Issues** tool in the DevTools Drawer</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-179">Chromium 问题 [#1068116][CR1068116]</span><span class="sxs-lookup"><span data-stu-id="36fa0-179">Chromium issue [#1068116][CR1068116]</span></span>  

### <span data-ttu-id="36fa0-180">查看 "检查模式" 工具提示中的辅助功能信息</span><span class="sxs-lookup"><span data-stu-id="36fa0-180">View accessibility information in the Inspect Mode tooltip</span></span>  

<span data-ttu-id="36fa0-181">" **检查模式** 工具提示" 现在指示元素是否具有可访问的 [名称和角色][WebhintHintsAxeNameRoleValue] 且可通过 [键盘获得焦点][WebhintHintsAxeKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="36fa0-181">The **Inspect Mode** tooltip now indicates whether the element has an accessible [name and role][WebhintHintsAxeNameRoleValue] and is [keyboard-focusable][WebhintHintsAxeKeyboard].</span></span>  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="带有辅助功能信息的 "检查模式" 工具提示" lightbox="../../media/2020/05/a11y.msft.png":::
  <span data-ttu-id="36fa0-183">带有辅助功能信息的 " **检查模式** " 工具提示</span><span class="sxs-lookup"><span data-stu-id="36fa0-183">The **Inspect Mode** tooltip with accessibility information</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-184">Chromium 问题 [#1040025][CR1040025]</span><span class="sxs-lookup"><span data-stu-id="36fa0-184">Chromium issue [#1040025][CR1040025]</span></span>  

### <span data-ttu-id="36fa0-185">性能面板更新</span><span class="sxs-lookup"><span data-stu-id="36fa0-185">Performance panel updates</span></span>  

#### <span data-ttu-id="36fa0-186">查看页脚中的总阻塞时间信息</span><span class="sxs-lookup"><span data-stu-id="36fa0-186">View Total Blocking Time information in the footer</span></span>  

<span data-ttu-id="36fa0-187">记录加载性能后， **性能** 面板现在显示总阻塞时间 \ (TBT \ ) 页脚中的信息。</span><span class="sxs-lookup"><span data-stu-id="36fa0-187">After recording your load performance, the **Performance** panel now shows Total Blocking Time \(TBT\) information in the footer.</span></span>  <span data-ttu-id="36fa0-188">TBT 是一种加载性能指标，可帮助量化页面变得可用的时间。</span><span class="sxs-lookup"><span data-stu-id="36fa0-188">TBT is a load performance metric that helps quantify how long a page takes to become usable.</span></span>  <span data-ttu-id="36fa0-189">它实质衡量页面的显示时间，因为内容呈现到屏幕 ) ，因此它的使用时间为 (;但实际上并不是可用的，因为 JavaScript 阻止主线程，因此页面不响应用户输入。</span><span class="sxs-lookup"><span data-stu-id="36fa0-189">It essentially measures how long a page appears to be usable \(because the content is rendered to the screen\); but is not actually usable, because JavaScript is blocking the main thread and therefore the page does not respond to user input.</span></span>  <span data-ttu-id="36fa0-190">TBT 是 approximating 第一个输入延迟的主要指标。</span><span class="sxs-lookup"><span data-stu-id="36fa0-190">TBT is the main metric for approximating First Input Delay.</span></span>  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

<span data-ttu-id="36fa0-191">若要获取总阻塞时间信息，请不要使用**Refresh Page** ![ 用于录制页面加载性能的刷新页面刷新页面图标 ][ImageRefreshPageIcon] 工作流。</span><span class="sxs-lookup"><span data-stu-id="36fa0-191">To get Total Blocking Time information, do not use the **Refresh Page** ![Refresh page icon][ImageRefreshPageIcon] workflow for recording page load performance.</span></span>  

<span data-ttu-id="36fa0-192">而是选择 " **录制** ![ 录制 ][ImageRecordIcon] " 图标，手动重新加载页面，等待页面加载，然后停止录制。</span><span class="sxs-lookup"><span data-stu-id="36fa0-192">Instead, select **Record** ![Record icon][ImageRecordIcon], manually reload the page, wait for the page to load, and then stop recording.</span></span>  

<span data-ttu-id="36fa0-193">如果你看到 `Total Blocking Time: Unavailable` ，Microsoft Edge DevTools 不会从 Microsoft edge 中的内部分析数据获取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="36fa0-193">If you see `Total Blocking Time: Unavailable`, Microsoft Edge DevTools did not get the required information from the internal profiling data in Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="性能面板录制的页脚中的总阻塞时间信息" lightbox="../../media/2020/05/tbt.msft.png":::
   <span data-ttu-id="36fa0-195">**性能**面板录制的页脚中的总阻塞时间信息</span><span class="sxs-lookup"><span data-stu-id="36fa0-195">Total Blocking Time information in the footer of a **Performance** panel recording</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-196">Chromium 问题 [#1054381][CR1054381]</span><span class="sxs-lookup"><span data-stu-id="36fa0-196">Chromium issue [#1054381][CR1054381]</span></span>  

#### <span data-ttu-id="36fa0-197">"新体验" 部分中的布局切换事件</span><span class="sxs-lookup"><span data-stu-id="36fa0-197">Layout Shift events in the new Experience section</span></span>  

<span data-ttu-id="36fa0-198">"**性能**" 面板的 "新**体验**" 部分可帮助你检测布局切换。</span><span class="sxs-lookup"><span data-stu-id="36fa0-198">The new **Experience** section of the **Performance** panel helps you detect layout shifts.</span></span>  <span data-ttu-id="36fa0-199">累积布局切换 \ (CLS \ ) 是有助于量化不需要的视觉不稳定性的指标。</span><span class="sxs-lookup"><span data-stu-id="36fa0-199">Cumulative Layout Shift \(CLS\) is a metric that helps you quantify unwanted visual instability.</span></span>

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

<span data-ttu-id="36fa0-200">选择 " **布局移动** " 事件可在 " **摘要** " 窗格中查看布局切换的详细信息。</span><span class="sxs-lookup"><span data-stu-id="36fa0-200">Select the **Layout Shift** event to see the details of the layout shift in the **Summary** pane.</span></span>  <span data-ttu-id="36fa0-201">将鼠标悬停在 " **移动的源** " 和 " **移动到** " 字段上，以直观显示发生布局变化的位置。</span><span class="sxs-lookup"><span data-stu-id="36fa0-201">Hover over the **Moved from** and **Moved to** fields to visualize where the layout shift occurred.</span></span>  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="布局切换的详细信息" lightbox="../../media/2020/05/cls.msft.png":::
   <span data-ttu-id="36fa0-203">布局切换的详细信息</span><span class="sxs-lookup"><span data-stu-id="36fa0-203">The details of a layout shift</span></span>  
:::image-end:::  

### <span data-ttu-id="36fa0-204">在控制台中获得更准确的承诺术语</span><span class="sxs-lookup"><span data-stu-id="36fa0-204">More accurate promise terminology in the Console</span></span>  

<span data-ttu-id="36fa0-205">当日志记录时 `Promise` ， **控制台** 不正确地 `PromiseStatus` 将值设置为 `resolved` 。</span><span class="sxs-lookup"><span data-stu-id="36fa0-205">When logging a `Promise`, the **Console** incorrectly provided `PromiseStatus` value set to `resolved`.</span></span>  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="使用旧的已解决术语的控制台示例" lightbox="../../media/2020/05/resolved.msft.png":::
   <span data-ttu-id="36fa0-207">使用旧术语的**控制台**示例 `resolved`</span><span class="sxs-lookup"><span data-stu-id="36fa0-207">An example of the **Console** using the old `resolved` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-208">现在，该 **控制台** 使用 `fulfilled` 与规范对齐的术语 `Promise` 。</span><span class="sxs-lookup"><span data-stu-id="36fa0-208">The **Console** now uses the term `fulfilled`, which aligns with the `Promise` specification.</span></span>  <span data-ttu-id="36fa0-209">有关规范的详细信息 `Promise` ，请参阅 [GitHub 上的状态和 Fates](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)。</span><span class="sxs-lookup"><span data-stu-id="36fa0-209">For more information about the `Promise` specification, see [States and Fates on GitHub](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md).</span></span>  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="使用新的已完成术语的控制台示例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  <span data-ttu-id="36fa0-211">使用新术语的**控制台**示例 `fulfilled`</span><span class="sxs-lookup"><span data-stu-id="36fa0-211">An example of the **Console** using the new `fulfilled` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-212">V8 问题 [#6751][CRV86751]</span><span class="sxs-lookup"><span data-stu-id="36fa0-212">V8 issue [#6751][CRV86751]</span></span>  

### <span data-ttu-id="36fa0-213">"样式" 窗格更新</span><span class="sxs-lookup"><span data-stu-id="36fa0-213">Styles pane updates</span></span>  

#### <span data-ttu-id="36fa0-214">对 revert 关键字的支持</span><span class="sxs-lookup"><span data-stu-id="36fa0-214">Support for the revert keyword</span></span>  

<span data-ttu-id="36fa0-215">" **样式** " 窗格的 "自动完成" UI 现在检测到 " [还原][MDNRevert] CSS" 关键字，该关键字可将属性的级联值还原为应用于该元素的样式的上一个值。</span><span class="sxs-lookup"><span data-stu-id="36fa0-215">The autocomplete UI of the **Styles** pane now detects the [revert][MDNRevert] CSS keyword, which reverts the cascaded value of a property to the previous value applied to the styling of the element.</span></span>  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="将属性的值设置为 "还原"" lightbox="../../media/2020/05/revert.msft.png":::
  <span data-ttu-id="36fa0-217">将属性的值设置为 "还原"</span><span class="sxs-lookup"><span data-stu-id="36fa0-217">Setting the value of a property to revert</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-218">Chromium 问题 [#1075437][CR1075437]</span><span class="sxs-lookup"><span data-stu-id="36fa0-218">Chromium issue [#1075437][CR1075437]</span></span>  

#### <span data-ttu-id="36fa0-219">图像预览</span><span class="sxs-lookup"><span data-stu-id="36fa0-219">Image previews</span></span>  

<span data-ttu-id="36fa0-220">将鼠标悬停 `background-image` 在 " **样式** " 窗格中的某个值上，可在工具提示中查看图像的预览。</span><span class="sxs-lookup"><span data-stu-id="36fa0-220">Hover over a `background-image` value in the **Styles** pane to see a preview of the image in a tooltip.</span></span>  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="将鼠标悬停在背景图像值上" lightbox="../../media/2020/05/image-preview.msft.png":::
  <span data-ttu-id="36fa0-222">将鼠标悬停在某个 `background-image` 值上</span><span class="sxs-lookup"><span data-stu-id="36fa0-222">Hovering over a `background-image` value</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-223">Chromium 问题 [#1040019][CR1040019]</span><span class="sxs-lookup"><span data-stu-id="36fa0-223">Chromium issue [#1040019][CR1040019]</span></span>  

#### <span data-ttu-id="36fa0-224">颜色选取器现在使用空格分隔的功能颜色表示法</span><span class="sxs-lookup"><span data-stu-id="36fa0-224">Color Picker now uses space-separated functional color notation</span></span>  

<span data-ttu-id="36fa0-225">[CSS 颜色模块级别 4][CSSWGDraftsColor4Changes3] 指定颜色函数（例如 `rgb()` ）应支持以空格分隔的参数。</span><span class="sxs-lookup"><span data-stu-id="36fa0-225">[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] specifies that color functions, such as `rgb()`, should support space-separated arguments.</span></span>  <span data-ttu-id="36fa0-226">例如，`rgb(0, 0, 0)` 与 `rbg(0 0 0)` 等效。</span><span class="sxs-lookup"><span data-stu-id="36fa0-226">For example, `rgb(0, 0, 0)` is equivalent to `rbg(0 0 0)`.</span></span>  

<span data-ttu-id="36fa0-227">使用 [颜色选取器][DevtoolsCssReferenceColorPicker] 选择颜色或在 "样式" 窗格中通过按住并选择值在 " **样式** " 窗格中交替颜色表示时 `Shift` `background-color` ，应看到以空格分隔的参数语法。</span><span class="sxs-lookup"><span data-stu-id="36fa0-227">When you choose colors with the [Color Picker][DevtoolsCssReferenceColorPicker] or alternate between color representations in the **Styles** pane by holding `Shift` and selecting the `background-color` value, you should see the space-separated argument syntax.</span></span>  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="在 "样式" 窗格中使用空格分隔的参数" lightbox="../../media/2020/05/color.msft.png":::
  <span data-ttu-id="36fa0-229">在 " **样式** " 窗格中使用空格分隔的参数</span><span class="sxs-lookup"><span data-stu-id="36fa0-229">Using space-separated arguments in the **Styles** pane</span></span>  
:::image-end:::  

<span data-ttu-id="36fa0-230">还应在 " **计算** " 窗格和 " **检查模式** 工具提示" 中查看语法。</span><span class="sxs-lookup"><span data-stu-id="36fa0-230">You should also see the syntax in the **Computed** pane and the **Inspect Mode** tooltip.</span></span>  

<span data-ttu-id="36fa0-231">Microsoft Edge DevTools 使用新语法，因为即将出现的 CSS 功能（如 [color ( # B1 ][CSSWGDraftsColor4Property] ）不支持弃用的逗号分隔参数语法。</span><span class="sxs-lookup"><span data-stu-id="36fa0-231">Microsoft Edge DevTools is using the new syntax because upcoming CSS features such as [color()][CSSWGDraftsColor4Property] do not support the deprecated comma-separated argument syntax.</span></span>  

<span data-ttu-id="36fa0-232">在大多数浏览器中，一段时间内支持空格分隔的参数语法。</span><span class="sxs-lookup"><span data-stu-id="36fa0-232">The space-separated argument syntax has been supported in most browsers for a while.</span></span>  <span data-ttu-id="36fa0-233">有关详细信息，请参阅 [我是否可以使用：以空格分隔的功能颜色表示法？][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span><span class="sxs-lookup"><span data-stu-id="36fa0-233">For more information, see [Can I use: Space-separated functional color notations?][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span></span>  

<span data-ttu-id="36fa0-234">Chromium 问题 [#1072952][CR1072952]</span><span class="sxs-lookup"><span data-stu-id="36fa0-234">Chromium issue [#1072952][CR1072952]</span></span>  

### <span data-ttu-id="36fa0-235">"元素" 面板中的 "属性" 窗格的弃用</span><span class="sxs-lookup"><span data-stu-id="36fa0-235">Deprecation of the Properties pane in the Elements panel</span></span>  

<span data-ttu-id="36fa0-236">"**元素**" 面板中的 "**属性**" 窗格已弃用。</span><span class="sxs-lookup"><span data-stu-id="36fa0-236">The **Properties** pane in the **Elements** panel is deprecated.</span></span>  <span data-ttu-id="36fa0-237">`console.dir($0)`改为在**控制台**中运行。</span><span class="sxs-lookup"><span data-stu-id="36fa0-237">Run `console.dir($0)` in the **Console** instead.</span></span>  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text=""已弃用的属性" 窗格" lightbox="../../media/2020/05/properties.msft.png":::
   <span data-ttu-id="36fa0-239">"已弃用的 **属性** " 窗格</span><span class="sxs-lookup"><span data-stu-id="36fa0-239">The deprecated **Properties** pane</span></span>  
:::image-end:::  

#### <span data-ttu-id="36fa0-240">参考</span><span class="sxs-lookup"><span data-stu-id="36fa0-240">References</span></span>  

*   [<span data-ttu-id="36fa0-241"> ( # A1 的 console</span><span class="sxs-lookup"><span data-stu-id="36fa0-241">console.dir()</span></span>][DevtoolsConsoleApiDir]  
*   [<span data-ttu-id="36fa0-242">$0</span><span class="sxs-lookup"><span data-stu-id="36fa0-242">$0</span></span>][DevtoolsConsoleUtilitiesDom]  

### <span data-ttu-id="36fa0-243">清单窗格中的应用快捷方式支持</span><span class="sxs-lookup"><span data-stu-id="36fa0-243">App shortcuts support in the Manifest pane</span></span>  

<span data-ttu-id="36fa0-244">应用快捷方式可帮助用户在 web 应用中快速启动常见或建议的任务。</span><span class="sxs-lookup"><span data-stu-id="36fa0-244">App shortcuts help users quickly start common or recommended tasks within a web app.</span></span>  <span data-ttu-id="36fa0-245">仅为在用户的桌面或移动设备上安装的 [渐进 Web 应用][PwaIndex] 显示 "应用快捷方式" 菜单。</span><span class="sxs-lookup"><span data-stu-id="36fa0-245">The app shortcuts menu is shown only for [Progressive Web Apps][PwaIndex] that are installed on the user's desktop or mobile device.</span></span>  

<!--For more information, see [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="清单窗格中的应用快捷方式" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  <span data-ttu-id="36fa0-247">**清单**窗格中的应用快捷方式</span><span class="sxs-lookup"><span data-stu-id="36fa0-247">App shortcuts in the **Manifest** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="36fa0-248">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="36fa0-248">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="36fa0-249">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="36fa0-249">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="36fa0-250">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="36fa0-250">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="36fa0-251">与 Microsoft Edge Devtools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="36fa0-251">Getting in touch with Microsoft Edge Devtools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/settings-icon.msft.png  
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/toggle-screencast-icon.msft.png  
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/refresh-page-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/record-icon.msft.png  

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "使用 Surface 双核仿真器 |Microsoft 文档"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir-控制台 API 参考 |Microsoft 文档"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象-控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "用颜色选取器更改颜色-CSS 参考 |Microsoft 文档"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义概述 |Microsoft 文档"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并修复 Microsoft Edge DevTools 问题选项卡 |Microsoft 文档"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "开始使用 "远程调试 Android 设备" |Microsoft 文档"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "远程调试 Surface 双核模拟器入门 |Microsoft 文档"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备入门 |Microsoft 文档"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "检查资源的详细信息 |Microsoft 文档"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动 |Microsoft 文档"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用 |Microsoft 文档"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android 应用"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "以空格分隔的功能颜色表示法-MDN |我是否可以使用"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"  
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG 标准 |Chromium bug"  
[CR1040019]: https://crbug.com/1040019 "DevTools：在 "样式" 窗格中轻松预览图像和背景图像 |Chromium bug"  
[CR1040025]: https://crbug.com/1040025 "DevTools：显示元素 popover | 中的基本 a11y 信息Chromium bug"  
[CR1048378]: https://crbug.com/1048378 "高对比度模式下的 DevTools UI 支持 |Chromium bug"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium bug"  
[CR1068116]: https://crbug.com/1068116 "发货问题面板 |Chromium bug"  
[CR1072952]: https://crbug.com/1072952 "DevTools：拾色器应生成新式 CSS 颜色语法 |Chromium bug"  
[CR1075437]: https://crbug.com/1075437 "DevTools：添加对 CSS "revert" 关键字/值的支持 |Chromium bug"  
[CR1076112]: https://crbug.com/1076112 "Devtools 个性化设置-抽屉调整人"  
[CR1081486]: https://crbug.com/1081486 "说明截屏视频模式中的导航按钮不可见的键盘焦点 |Chromium bug"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus 应为 "已完成"，而不是 "已解决" |V8 bug"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "从颜色 3-CSS 颜色模块级别4开始的更改 |W3C CSS 工作组编辑器草稿"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. 前景颜色： "Color"-CSS 颜色模块级别 4 |W3C CSS 工作组编辑器草稿"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新的 Microsoft Edge 简介"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "州和 Fates-domenic/承诺-解包 |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "还原 |MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "浏览器兼容性 |MDN"  

[VSCode]: https://code.visualstudio.com/ "Visual Studio 代码"  
[VSCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "适用于 Windows 的 Visual Studio 代码键盘快捷方式"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "Axe：键盘 |WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "Axe： Name Role Value |WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "在 Windows | 中打开或关闭高对比度模式Windows 支持"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"  

<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebdevCoreWebVitals]: https://alphabet-dev/vitals#core-web-vitals "Core Web Vitals | alphabet-dev"  -->  

> [!NOTE]
> <span data-ttu-id="36fa0-296">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="36fa0-296">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="36fa0-297">原始页面位于[此处](https://developers.google.com/web/updates/2020/05/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="36fa0-297">The original page is found [here](https://developers.google.com/web/updates/2020/05/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="36fa0-299">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="36fa0-299">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
