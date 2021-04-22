---
description: 在 Windows 高对比度模式下使用 DevTools、匹配 DevTools 中的键盘快捷方式以Visual Studio代码等。
title: 'Microsoft Edge 84 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 01d41fe5400dde427a0ac73870ace0e1211f429a
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514387"
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
# <a name="whats-new-in-devtools-microsoft-edge-84"></a><span data-ttu-id="f3944-104">Microsoft Edge 84 (DevTools 中的新增) </span><span class="sxs-lookup"><span data-stu-id="f3944-104">What's new in DevTools (Microsoft Edge 84)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f3944-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="f3944-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="f3944-106">以下各节列出了你可能错过的 Microsoft Edge DevTools 团队中的通知。</span><span class="sxs-lookup"><span data-stu-id="f3944-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="f3944-107">请查看公告以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="f3944-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="f3944-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="f3944-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="use-the-devtools-in-windows-high-contrast-mode"></a><span data-ttu-id="f3944-109">在 Windows 高对比度模式下使用 DevTools</span><span class="sxs-lookup"><span data-stu-id="f3944-109">Use the DevTools in Windows high contrast mode</span></span>

<span data-ttu-id="f3944-110">当 Windows 处于高对比度模式时，Microsoft Edge DevTools 现在以高对比度模式显示。</span><span class="sxs-lookup"><span data-stu-id="f3944-110">The Microsoft Edge DevTools are now displayed in high contrast mode when Windows is in high contrast mode.</span></span>  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="高对比度模式下的 Microsoft Edge DevTools" lightbox="../../media/2020/05/high-contrast.msft.png":::
   <span data-ttu-id="f3944-112">高对比度模式下的 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="f3944-112">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-113">[按照说明在 Windows 中打开高对比度模式][MicrosoftSupportWindows10HighContrastMode]。</span><span class="sxs-lookup"><span data-stu-id="f3944-113">[Follow the instructions to turn on high contrast mode in Windows][MicrosoftSupportWindows10HighContrastMode].</span></span>  <span data-ttu-id="f3944-114">若要在 Microsoft Edge 中打开 DevTools，请选择 `F12` 或 `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="f3944-114">To open the DevTools in Microsoft Edge, select `F12` or `Ctrl`+`Shift`+`I`.</span></span>  <span data-ttu-id="f3944-115">DevTools 以高对比度模式显示。</span><span class="sxs-lookup"><span data-stu-id="f3944-115">The DevTools are displayed in high contrast mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="f3944-116">Microsoft Edge DevTools 当前在 Windows 上支持高对比度模式，但在 macOS 上不支持。</span><span class="sxs-lookup"><span data-stu-id="f3944-116">The Microsoft Edge DevTools currently support high contrast mode on Windows but not on macOS.</span></span>  

<span data-ttu-id="f3944-117">Chromium [问题#1048378][CR1048378]</span><span class="sxs-lookup"><span data-stu-id="f3944-117">Chromium issue [#1048378][CR1048378]</span></span>  

### <a name="match-keyboard-shortcuts-in-the-devtools-to-visual-studio-code"></a><span data-ttu-id="f3944-118">将 DevTools 中的键盘快捷方式与代码Visual Studio匹配</span><span class="sxs-lookup"><span data-stu-id="f3944-118">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  

<span data-ttu-id="f3944-119">从 [你的反馈](#getting-in-touch-with-microsoft-edge-devtools-team) 和 [Chromium][CRIssuesList]公共问题跟踪器中，Microsoft Edge DevTools 团队了解到你需要在 DevTools 中自定义键盘快捷方式的能力。</span><span class="sxs-lookup"><span data-stu-id="f3944-119">From your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) and the [Chromium public issue tracker][CRIssuesList], the Microsoft Edge DevTools team learned that you wanted the ability to customize keyboard shortcuts in the DevTools.</span></span>  <span data-ttu-id="f3944-120">在 Microsoft Edge 84 中，你现在能够将 DevTools 中的键盘快捷方式与 [Visual Studio Code][VisualStudioCode]匹配，这只是团队正致力于进行快捷方式自定义的功能之一。</span><span class="sxs-lookup"><span data-stu-id="f3944-120">In Microsoft Edge 84, you are now able to match keyboard shortcuts in the DevTools to [Visual Studio Code][VisualStudioCode], which is just one of the features the team is working on for shortcut customization.</span></span>  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="将 DevTools 中的键盘快捷方式与代码Visual Studio匹配" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   <span data-ttu-id="f3944-122">高对比度模式下的 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="f3944-122">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-123">若要试用实验，请打开 DevTools 设置，方法为选择或选择 `?` ![ DevTools 工具右上角的"DevTools 设置" ][ImageSettingsIcon] 图标图标。</span><span class="sxs-lookup"><span data-stu-id="f3944-123">To try the experiment, open DevTools Settings by selecting `?` or choosing the ![DevTools Settings icon][ImageSettingsIcon] icon in the top-right corner of the DevTools.</span></span>  <span data-ttu-id="f3944-124">导航到**实验部分**，并选中\*\*启用自定义键盘快捷方式设置选项卡 (重新加载) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="f3944-124">Navigate to the **Experiments** section and check **Enable custom keyboard shortcuts settings tab (requires reload)**.</span></span>  <span data-ttu-id="f3944-125">现在重新加载 DevTools，再次打开"设置"，然后导航到 **"快捷方式"** 部分。</span><span class="sxs-lookup"><span data-stu-id="f3944-125">Now reload the DevTools, open Settings again, and navigate to the **Shortcuts** section.</span></span>  

<span data-ttu-id="f3944-126">在 **"从预设 (快捷方式) 选择"DevTools**) \*\*\*\* 默认选项"，然后选择"Visual Studio**代码"。**</span><span class="sxs-lookup"><span data-stu-id="f3944-126">Choose **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="f3944-127">DevTools 中的键盘快捷方式现在与代码中等效操作Visual Studio匹配。</span><span class="sxs-lookup"><span data-stu-id="f3944-127">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in Visual Studio Code.</span></span>  

<span data-ttu-id="f3944-128">例如，用于暂停或继续运行代码中的脚本的键盘快捷方式 [Visual Studio为][VisualStudioCodeShortcuts] `F5` 。</span><span class="sxs-lookup"><span data-stu-id="f3944-128">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualStudioCodeShortcuts] is `F5`.</span></span>  <span data-ttu-id="f3944-129">使用\*\*DevTools (Default) \*\*预设，DevTools 中的同一快捷方式是，但具有 Visual Studio Code 预设， `F8` 该快捷方式现在也是\*\*\*\* `F5` 。</span><span class="sxs-lookup"><span data-stu-id="f3944-129">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8` but with the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="f3944-130">此功能目前作为实验在 Microsoft Edge 84 中提供，因此请与 [团队](#getting-in-touch-with-microsoft-edge-devtools-team) 分享你的反馈！</span><span class="sxs-lookup"><span data-stu-id="f3944-130">The feature is currently available in Microsoft Edge 84 as an experiment, so please share your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) with the team!</span></span>  

<span data-ttu-id="f3944-131">Chromium [问题#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="f3944-131">Chromium issue [#174309][CR174309]</span></span>  

### <a name="remote-debug-surface-duo-emulators"></a><span data-ttu-id="f3944-132">远程调试 Surface Duo 仿真器</span><span class="sxs-lookup"><span data-stu-id="f3944-132">Remote debug Surface Duo emulators</span></span>  

<span data-ttu-id="f3944-133">你现在可以使用[Microsoft Edge DevTools][DevToolsChromiumGuide]的全部功能远程调试[在 Surface Duo][DualScreensAndroidEmulator]模拟器中运行的 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="f3944-133">You are now able to remotely debug your web content running in the [Surface Duo emulator][DualScreensAndroidEmulator] using the full power of the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

<span data-ttu-id="f3944-134">使用 [Surface Duo 仿真][DualScreensAndroidEmulator]器，你可以测试 Web 内容在可折叠和双屏幕设备的新类上呈现方式。</span><span class="sxs-lookup"><span data-stu-id="f3944-134">With the [Surface Duo emulator][DualScreensAndroidEmulator], you are able to test how your web content renders on a new class of foldable and dual-screen devices.</span></span>  <span data-ttu-id="f3944-135">仿真器运行 Android 操作系统并提供 [Microsoft Edge Android 应用][AndroidEdge]。</span><span class="sxs-lookup"><span data-stu-id="f3944-135">The emulator runs the Android operating system and provides the [Microsoft Edge Android app][AndroidEdge].</span></span>  <span data-ttu-id="f3944-136">在 Microsoft Edge 应用中加载 Web [内容，][AndroidEdge] 然后使用 [Microsoft Edge DevTools 调试它][DevToolsChromiumGuide]。</span><span class="sxs-lookup"><span data-stu-id="f3944-136">Load your web content in the [Microsoft Edge app][AndroidEdge] and debug it with the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="在 Surface Duo 仿真器上运行的 Microsoft Edge 应用" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   <span data-ttu-id="f3944-138">Surface Duo 仿真程序上的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="f3944-138">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-139">Microsoft Edge 桌面实例中的页面显示 `edge://inspect` **SurfaceD一个Emulator，** 其中列出了在 Surface Duo 仿真器上运行的已打开选项卡或[][DesktopEdge][PWA。][PwaIndex] [][DualScreensAndroidEmulator]</span><span class="sxs-lookup"><span data-stu-id="f3944-139">The `edge://inspect` page in a desktop instance of [Microsoft Edge][DesktopEdge] shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaIndex] that are running on the [Surface Duo emulator][DualScreensAndroidEmulator].</span></span>  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="edge://inspect 页面在模拟器上运行的 Microsoft Edge 应用程序中显示打开选项卡的列表" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   <span data-ttu-id="f3944-141">`edge://inspect` 页面在模拟器上运行的 Microsoft Edge 应用程序中显示打开选项卡的列表</span><span class="sxs-lookup"><span data-stu-id="f3944-141">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>
:::image-end:::  

<span data-ttu-id="f3944-142">选择要**调试**的选项卡或 PWA 的"检查"以打开[Microsoft Edge DevTools。][DevToolsChromiumGuide]</span><span class="sxs-lookup"><span data-stu-id="f3944-142">Choose **inspect** for the tab or PWA that you want to debug to open the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  <span data-ttu-id="f3944-143">[按照分步指南在 Surface Duo][DevToolsRemoteDebugDuoEmulator]仿真器上远程调试 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="f3944-143">[Follow the step-by-step guide to remotely debug your web content on the Surface Duo emulator][DevToolsRemoteDebugDuoEmulator].</span></span>  

### <a name="resize-the-devtools-drawer-more-easily"></a><span data-ttu-id="f3944-144">更轻松地调整 DevTools 箱的大小</span><span class="sxs-lookup"><span data-stu-id="f3944-144">Resize the DevTools drawer more easily</span></span>  

<span data-ttu-id="f3944-145">在 Microsoft Edge 83 或更早版本中，你仅能通过将鼠标悬停在"箱"工具栏内来调整 [DevTools"][DevToolsDrawer] 箱"的大小。</span><span class="sxs-lookup"><span data-stu-id="f3944-145">In Microsoft Edge 83 or earlier, you were only able to resize the [DevTools Drawer][DevToolsDrawer] by hovering inside the toolbar of the Drawer.</span></span>  <span data-ttu-id="f3944-146">The Drawer behavely different than the other resize controls for panes in the DevTools where you hover on the border of the pane to resize it.</span><span class="sxs-lookup"><span data-stu-id="f3944-146">The Drawer behaved differently than the other resize controls for panes in the DevTools where you hover on the border of the pane to resize it.</span></span>  <span data-ttu-id="f3944-147">选择下图可显示调整"箱"大小在 Microsoft Edge 版本 83 或更早版本中的运行方式。</span><span class="sxs-lookup"><span data-stu-id="f3944-147">Choose the following image to display how resizing the Drawer worked in version 83 or earlier of Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="调整 Microsoft Edge 83 中的 DevTools 箱大小" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   <span data-ttu-id="f3944-149">调整 Microsoft Edge 83 中的 DevTools 箱大小</span><span class="sxs-lookup"><span data-stu-id="f3944-149">Resizing the DevTools Drawer in Microsoft Edge 83</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="f3944-150">从 Microsoft Edge 84 开始，现在通过将鼠标悬停在"箱"边框上，可以调整"箱"的大小。</span><span class="sxs-lookup"><span data-stu-id="f3944-150">Starting with Microsoft Edge 84, you are now able to resize the Drawer by hovering over the border of the Drawer.</span></span>  <span data-ttu-id="f3944-151">此更改将调整 DevTools 箱大小的行为与调整 DevTools 中其他窗格的大小的方式保持一致。</span><span class="sxs-lookup"><span data-stu-id="f3944-151">This change aligns the behavior resizing the DevTools Drawer with the way you resize other panes in the DevTools.</span></span>  <span data-ttu-id="f3944-152">选择以下图像，在 Microsoft Edge 84 中显示操作中的调整大小。</span><span class="sxs-lookup"><span data-stu-id="f3944-152">Choose the following image to display resizing in action in Microsoft Edge 84.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="调整 Microsoft Edge 84 中的 DevTools 箱大小" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   <span data-ttu-id="f3944-154">调整 Microsoft Edge 84 中的 DevTools 箱大小</span><span class="sxs-lookup"><span data-stu-id="f3944-154">Resizing the DevTools Drawer in Microsoft Edge 84</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="f3944-155">Chromium [问题#1076112][CR1076112]</span><span class="sxs-lookup"><span data-stu-id="f3944-155">Chromium issue [#1076112][CR1076112]</span></span>  

### <a name="screencasting-navigation-buttons-display-focus"></a><span data-ttu-id="f3944-156">屏幕广播导航按钮显示焦点</span><span class="sxs-lookup"><span data-stu-id="f3944-156">Screencasting navigation buttons display focus</span></span>  

<span data-ttu-id="f3944-157">远程调试 [Android][DevToolsRemoteDebugAndroid]设备 [、Windows 10][DevToolsRemoteDebugWindows]设备或 Surface [Duo][DevToolsRemoteDebugDuoEmulator]仿真器时，可以使用 ![ DevTools 左上角的切换屏幕视频图标切换屏幕视频 ][ImageScreencastingIcon] 。</span><span class="sxs-lookup"><span data-stu-id="f3944-157">When remote debugging an [Android device][DevToolsRemoteDebugAndroid], a [Windows 10 device][DevToolsRemoteDebugWindows], or a [Surface Duo emulator][DevToolsRemoteDebugDuoEmulator], you are able to toggle screencasting with the ![Toggle Screencast][ImageScreencastingIcon] icon in the top-left corner of the DevTools.</span></span>  <span data-ttu-id="f3944-158">启用屏幕广播后，你可以从 DevTools 窗口在远程设备上导航 Microsoft Edge 中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="f3944-158">With screencasting enabled, you are able to navigate the tab in Microsoft Edge on the remote device from the DevTools window.</span></span>  <span data-ttu-id="f3944-159">在 Microsoft Edge 84 中，这些导航按钮现在也可供键盘访问。</span><span class="sxs-lookup"><span data-stu-id="f3944-159">In Microsoft Edge 84, these navigation buttons are now also keyboard accessible.</span></span>  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="Select Shift+Tab from the screencasted URL bar shows focus on the Refresh button" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   <span data-ttu-id="f3944-161">Select `Shift` + `Tab` from the screencasted URL bar shows focus on the **Refresh** button</span><span class="sxs-lookup"><span data-stu-id="f3944-161">Select `Shift`+`Tab` from the screencasted URL bar shows focus on the **Refresh** button</span></span>
:::image-end:::  

<span data-ttu-id="f3944-162">Chromium [问题#1081486][CR1081486]</span><span class="sxs-lookup"><span data-stu-id="f3944-162">Chromium issue [#1081486][CR1081486]</span></span>  

### <a name="network-panel-details-pane-is-now-accessible"></a><span data-ttu-id="f3944-163">网络面板 现在可访问详细信息窗格</span><span class="sxs-lookup"><span data-stu-id="f3944-163">Network panel Details pane is now accessible</span></span>  

<span data-ttu-id="f3944-164">在 Microsoft Edge 84 中，\*\*\*\* 当您在网络日志中为资源打开网络工具中的"详细信息"窗格时，它[现在将具有焦点][DevToolsNetworkLog]。 [][DevToolsNetworkDetails]</span><span class="sxs-lookup"><span data-stu-id="f3944-164">In Microsoft Edge 84, the [Details pane][DevToolsNetworkDetails] in the **Network** tool now takes focus when you open it for a resource in the [Network Log][DevToolsNetworkLog].</span></span>  <span data-ttu-id="f3944-165">此更改允许屏幕阅读器读出"详细信息"窗格的内容并 **与之** 交互。</span><span class="sxs-lookup"><span data-stu-id="f3944-165">This change allows screen readers to read out and interact with the content of the **Details** pane.</span></span>  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text=""网络"面板中的"详细信息"窗格在打开时将焦点" lightbox="../../media/2020/05/network-details.msft.png":::
   <span data-ttu-id="f3944-167">" **网络** "工具中的" **详细信息** "窗格在打开时将焦点</span><span class="sxs-lookup"><span data-stu-id="f3944-167">The **Details** pane in the **Network** tool takes focus when opened</span></span>
:::image-end:::  

<span data-ttu-id="f3944-168">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="f3944-168">Chromium issue [#963183][CR963183]</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="f3944-169">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="f3944-169">Announcements from the Chromium project</span></span>  

<span data-ttu-id="f3944-170">以下各节宣布 Microsoft Edge 84 中提供的其他功能已参与开放源代码 Chromium 项目。</span><span class="sxs-lookup"><span data-stu-id="f3944-170">The following sections announce additional features available in Microsoft Edge 84 that were contributed to the open source Chromium project.</span></span>  

### <a name="fix-site-issues-with-the-new-issues-tool-in-the-devtools-drawer"></a><span data-ttu-id="f3944-171">修复开发人员工具箱中新问题工具的网站问题</span><span class="sxs-lookup"><span data-stu-id="f3944-171">Fix site issues with the new Issues tool in the DevTools Drawer</span></span>

<span data-ttu-id="f3944-172">DevTools"箱"中新增的"问题"工具是为了帮助减少控制台的通知疲劳和**混乱。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f3944-172">The new **Issues** tool in the DevTools Drawer was built to help reduce the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="f3944-173">目前， **控制台** 是网站开发人员、库、框架和 Microsoft Edge 记录消息、警告和错误的中心位置。</span><span class="sxs-lookup"><span data-stu-id="f3944-173">Currently, the **Console** is the central place for website developers, libraries, frameworks, and Microsoft Edge to log messages, warnings, and errors.</span></span>  <span data-ttu-id="f3944-174">" **问题** "工具以结构化、聚合且可操作的方式聚合来自浏览器的警告、指向 Microsoft Edge DevTools 中受影响的资源的链接，并提供有关如何修复问题的指南。</span><span class="sxs-lookup"><span data-stu-id="f3944-174">The **Issues** tool aggregates warnings from the browser in a structured, aggregated, and actionable way, links to affected resources within Microsoft Edge DevTools, and provides guidance on how to fix the issues.</span></span>  <span data-ttu-id="f3944-175">随着时间的推移，问题工具（而不是控制台）中的 Microsoft Edge 中\*\*\*\* 会显示越来越多的警告，\*\*\*\* 这有助于减少控制台中的混乱 **。**</span><span class="sxs-lookup"><span data-stu-id="f3944-175">Over time, more and more warnings are surfaced in Microsoft Edge in the **Issues** tool rather than the **Console**, which should help reduce the clutter in the **Console**.</span></span>  

<span data-ttu-id="f3944-176">To get started， navigate to [Find and Fix Problems with the Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span><span class="sxs-lookup"><span data-stu-id="f3944-176">To get started, navigate to [Find And Fix Problems With The Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools"箱"中的"问题"工具" lightbox="../../media/2020/05/issues.msft.png":::
   <span data-ttu-id="f3944-178">DevTools"箱"中的"问题"工具\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f3944-178">The **Issues** tool in the DevTools Drawer</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-179">Chromium [问题#1068116][CR1068116]</span><span class="sxs-lookup"><span data-stu-id="f3944-179">Chromium issue [#1068116][CR1068116]</span></span>  

### <a name="view-accessibility-information-in-the-inspect-mode-tooltip"></a><span data-ttu-id="f3944-180">在检查模式工具提示中查看辅助功能信息</span><span class="sxs-lookup"><span data-stu-id="f3944-180">View accessibility information in the Inspect Mode tooltip</span></span>  

<span data-ttu-id="f3944-181">检查**模式**工具提示现在指示元素是否具有辅助名称和角色，并且[是键盘可聚焦的][WebhintHintsAxeKeyboard]。 [][WebhintHintsAxeNameRoleValue]</span><span class="sxs-lookup"><span data-stu-id="f3944-181">The **Inspect Mode** tooltip now indicates whether the element has an accessible [name and role][WebhintHintsAxeNameRoleValue] and is [keyboard-focusable][WebhintHintsAxeKeyboard].</span></span>  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="包含辅助功能信息的检查模式工具提示" lightbox="../../media/2020/05/a11y.msft.png":::
  <span data-ttu-id="f3944-183">包含 **辅助功能** 信息的检查模式工具提示</span><span class="sxs-lookup"><span data-stu-id="f3944-183">The **Inspect Mode** tooltip with accessibility information</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-184">Chromium [问题#1040025][CR1040025]</span><span class="sxs-lookup"><span data-stu-id="f3944-184">Chromium issue [#1040025][CR1040025]</span></span>  

### <a name="performance-panel-updates"></a><span data-ttu-id="f3944-185">性能面板更新</span><span class="sxs-lookup"><span data-stu-id="f3944-185">Performance panel updates</span></span>  

#### <a name="view-total-blocking-time-information-in-the-footer"></a><span data-ttu-id="f3944-186">查看页脚中的总阻止时间信息</span><span class="sxs-lookup"><span data-stu-id="f3944-186">View Total Blocking Time information in the footer</span></span>  

<span data-ttu-id="f3944-187">记录负载性能后，"性能\*\*\*\*"面板现在在页脚中 (总阻止时间 \) TBT\) 信息。</span><span class="sxs-lookup"><span data-stu-id="f3944-187">After recording your load performance, the **Performance** panel now shows Total Blocking Time \(TBT\) information in the footer.</span></span>  <span data-ttu-id="f3944-188">TBT 是一种负载性能指标，有助于量化页面使用所花的时间。</span><span class="sxs-lookup"><span data-stu-id="f3944-188">TBT is a load performance metric that helps quantify how long a page takes to become usable.</span></span>  <span data-ttu-id="f3944-189">它实质上测量页面显示为可用 \ (，因为内容呈现到屏幕\) ;但实际上并不可用，因为 JavaScript 会阻止主线程，因此页面不会响应用户输入。</span><span class="sxs-lookup"><span data-stu-id="f3944-189">It essentially measures how long a page appears to be usable \(because the content is rendered to the screen\); but is not actually usable, because JavaScript is blocking the main thread and therefore the page does not respond to user input.</span></span>  <span data-ttu-id="f3944-190">TBT 是估计第一次输入延迟的主要指标。</span><span class="sxs-lookup"><span data-stu-id="f3944-190">TBT is the main metric for approximating First Input Delay.</span></span>  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

<span data-ttu-id="f3944-191">若要获取总阻止时间信息，请不要使用"刷新 **页面**刷新"页面 ![ 图标工作流 ][ImageRefreshPageIcon] 来记录页面加载性能。</span><span class="sxs-lookup"><span data-stu-id="f3944-191">To get Total Blocking Time information, do not use the **Refresh Page** ![Refresh page icon][ImageRefreshPageIcon] workflow for recording page load performance.</span></span>  

<span data-ttu-id="f3944-192">相反，选择 **"录制** ![ "图标， ][ImageRecordIcon] 手动重新加载页面，等待页面加载，然后停止录制。</span><span class="sxs-lookup"><span data-stu-id="f3944-192">Instead, select **Record** ![Record icon][ImageRecordIcon], manually reload the page, wait for the page to load, and then stop recording.</span></span>  

<span data-ttu-id="f3944-193">如果 `Total Blocking Time: Unavailable` 显示，Microsoft Edge DevTools 不会从 Microsoft Edge 中的内部分析数据获取所需信息。</span><span class="sxs-lookup"><span data-stu-id="f3944-193">If `Total Blocking Time: Unavailable` is displayed, Microsoft Edge DevTools did not get the required information from the internal profiling data in Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text="性能面板记录的页脚中的总阻止时间信息" lightbox="../../media/2020/05/tbt.msft.png":::
   <span data-ttu-id="f3944-195">性能面板记录的页脚中的总 **阻止时间** 信息</span><span class="sxs-lookup"><span data-stu-id="f3944-195">Total Blocking Time information in the footer of a **Performance** panel recording</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-196">Chromium [问题#1054381][CR1054381]</span><span class="sxs-lookup"><span data-stu-id="f3944-196">Chromium issue [#1054381][CR1054381]</span></span>  

#### <a name="layout-shift-events-in-the-new-experience-section"></a><span data-ttu-id="f3944-197">新"体验"部分中的布局 Shift 事件</span><span class="sxs-lookup"><span data-stu-id="f3944-197">Layout Shift events in the new Experience section</span></span>  

<span data-ttu-id="f3944-198">"**性能"\*\*\*\*面板的新"** 体验"部分可帮助你检测布局移动。</span><span class="sxs-lookup"><span data-stu-id="f3944-198">The new **Experience** section of the **Performance** panel helps you detect layout shifts.</span></span>  <span data-ttu-id="f3944-199">累积布局班次 \ (CLS\) 是一个指标，可帮助你量化不需要的视觉不稳定。</span><span class="sxs-lookup"><span data-stu-id="f3944-199">Cumulative Layout Shift \(CLS\) is a metric that helps you quantify unwanted visual instability.</span></span>

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

<span data-ttu-id="f3944-200">选择 **"布局班次** "事件以显示"摘要"窗格中布局 **班次的详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="f3944-200">Choose the **Layout Shift** event to display the details of the layout shift in the **Summary** pane.</span></span>  <span data-ttu-id="f3944-201">将鼠标悬停在 **"移动位置** "和"移动到 **"字段上** ，可直观地显示发生布局切换的位置。</span><span class="sxs-lookup"><span data-stu-id="f3944-201">Hover on the **Moved from** and **Moved to** fields to visualize where the layout shift occurred.</span></span>  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="布局转换的详细信息" lightbox="../../media/2020/05/cls.msft.png":::
   <span data-ttu-id="f3944-203">布局转换的详细信息</span><span class="sxs-lookup"><span data-stu-id="f3944-203">The details of a layout shift</span></span>  
:::image-end:::  

### <a name="more-accurate-promise-terminology-in-the-console"></a><span data-ttu-id="f3944-204">控制台中更准确的承诺术语</span><span class="sxs-lookup"><span data-stu-id="f3944-204">More accurate promise terminology in the Console</span></span>  

<span data-ttu-id="f3944-205">记录 时 `Promise` ， **控制台** 错误地提供了设置为 `PromiseStatus` 的值 `resolved` 。</span><span class="sxs-lookup"><span data-stu-id="f3944-205">When logging a `Promise`, the **Console** incorrectly provided `PromiseStatus` value set to `resolved`.</span></span>  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="使用旧的已解析术语的控制台示例" lightbox="../../media/2020/05/resolved.msft.png":::
   <span data-ttu-id="f3944-207">使用旧 **术语** 的控制台 `resolved` 示例</span><span class="sxs-lookup"><span data-stu-id="f3944-207">An example of the **Console** using the old `resolved` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-208">控制台 **现在** 使用术语 `fulfilled` ，该术语与规范 `Promise` 一致。</span><span class="sxs-lookup"><span data-stu-id="f3944-208">The **Console** now uses the term `fulfilled`, which aligns with the `Promise` specification.</span></span>  <span data-ttu-id="f3944-209">有关规范详细信息，请导航到 GitHub 上的"状态"和 `Promise` ["状态"。](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)</span><span class="sxs-lookup"><span data-stu-id="f3944-209">For more information about the `Promise` specification, navigate to [States and Fates on GitHub](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md).</span></span>  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="使用新的已实现术语的控制台示例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  <span data-ttu-id="f3944-211">使用新 **术语** 的控制台 `fulfilled` 示例</span><span class="sxs-lookup"><span data-stu-id="f3944-211">An example of the **Console** using the new `fulfilled` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-212">V8 [问题#6751][CRV86751]</span><span class="sxs-lookup"><span data-stu-id="f3944-212">V8 issue [#6751][CRV86751]</span></span>  

### <a name="styles-pane-updates"></a><span data-ttu-id="f3944-213">样式窗格更新</span><span class="sxs-lookup"><span data-stu-id="f3944-213">Styles pane updates</span></span>  

#### <a name="support-for-the-revert-keyword"></a><span data-ttu-id="f3944-214">支持 revert 关键字</span><span class="sxs-lookup"><span data-stu-id="f3944-214">Support for the revert keyword</span></span>  

<span data-ttu-id="f3944-215">"样式"窗格的自动完成\*\*\*\* UI 现在检测到[revert][MDNRevert] CSS 关键字，该关键字将属性的级联值还原为之前应用于元素样式的值。</span><span class="sxs-lookup"><span data-stu-id="f3944-215">The autocomplete UI of the **Styles** pane now detects the [revert][MDNRevert] CSS keyword, which reverts the cascaded value of a property to the previous value applied to the styling of the element.</span></span>  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="设置要还原的属性的值" lightbox="../../media/2020/05/revert.msft.png":::
  <span data-ttu-id="f3944-217">设置要还原的属性的值</span><span class="sxs-lookup"><span data-stu-id="f3944-217">Setting the value of a property to revert</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-218">Chromium [问题#1075437][CR1075437]</span><span class="sxs-lookup"><span data-stu-id="f3944-218">Chromium issue [#1075437][CR1075437]</span></span>  

#### <a name="image-previews"></a><span data-ttu-id="f3944-219">图像预览</span><span class="sxs-lookup"><span data-stu-id="f3944-219">Image previews</span></span>  

<span data-ttu-id="f3944-220">将鼠标 `background-image` 悬停在 **"** 样式"窗格中的值上，以在工具提示中显示图像预览。</span><span class="sxs-lookup"><span data-stu-id="f3944-220">Hover on a `background-image` value in the **Styles** pane to display a preview of the image in a tooltip.</span></span>  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="将鼠标悬停在背景图像值上" lightbox="../../media/2020/05/image-preview.msft.png":::
  <span data-ttu-id="f3944-222">将鼠标悬停在 `background-image` 值上方</span><span class="sxs-lookup"><span data-stu-id="f3944-222">Hovering over a `background-image` value</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-223">Chromium [问题#1040019][CR1040019]</span><span class="sxs-lookup"><span data-stu-id="f3944-223">Chromium issue [#1040019][CR1040019]</span></span>  

#### <a name="color-picker-now-uses-space-separated-functional-color-notation"></a><span data-ttu-id="f3944-224">颜色选取器现在使用空格分隔的功能颜色表示法</span><span class="sxs-lookup"><span data-stu-id="f3944-224">Color Picker now uses space-separated functional color notation</span></span>  

<span data-ttu-id="f3944-225">[CSS 颜色模块级别 4][CSSWGDraftsColor4Changes3] 指定颜色函数（如 ）应 `rgb()` 支持空格分隔参数。</span><span class="sxs-lookup"><span data-stu-id="f3944-225">[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] specifies that color functions, such as `rgb()`, should support space-separated arguments.</span></span>  <span data-ttu-id="f3944-226">例如，`rgb(0, 0, 0)` 与 `rbg(0 0 0)` 等效。</span><span class="sxs-lookup"><span data-stu-id="f3944-226">For example, `rgb(0, 0, 0)` is equivalent to `rbg(0 0 0)`.</span></span>  

<span data-ttu-id="f3944-227">当你通过选择值来选择[][DevtoolsCssReferenceColorPicker]颜色选取器或在"样式"窗格中的颜色表示形式\*\*\*\* 之间交替选择颜色时，将显示空格分隔 `Shift` `background-color` 的参数语法。</span><span class="sxs-lookup"><span data-stu-id="f3944-227">When you choose colors with the [Color Picker][DevtoolsCssReferenceColorPicker] or alternate between color representations in the **Styles** pane by holding `Shift` and selecting the `background-color` value, the space-separated argument syntax is displayed.</span></span>  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="在"样式"窗格中使用空格分隔的参数" lightbox="../../media/2020/05/color.msft.png":::
  <span data-ttu-id="f3944-229">在"样式"窗格中使用 **空格分隔** 的参数</span><span class="sxs-lookup"><span data-stu-id="f3944-229">Using space-separated arguments in the **Styles** pane</span></span>  
:::image-end:::  

<span data-ttu-id="f3944-230">还应在"计算"窗格和"检查**模式\*\*\*\*"工具提示**中显示语法。</span><span class="sxs-lookup"><span data-stu-id="f3944-230">You should also display the syntax in the **Computed** pane and the **Inspect Mode** tooltip.</span></span>  

<span data-ttu-id="f3944-231">Microsoft Edge DevTools 正在使用新语法，因为即将推出的 CSS[][CSSWGDraftsColor4Property]功能（如颜色 () 不支持已弃用逗号分隔的参数语法。</span><span class="sxs-lookup"><span data-stu-id="f3944-231">Microsoft Edge DevTools is using the new syntax because upcoming CSS features such as [color()][CSSWGDraftsColor4Property] do not support the deprecated comma-separated argument syntax.</span></span>  

<span data-ttu-id="f3944-232">一段时间以来，大多数浏览器都支持空格分隔的参数语法。</span><span class="sxs-lookup"><span data-stu-id="f3944-232">The space-separated argument syntax has been supported in most browsers for a while.</span></span>  <span data-ttu-id="f3944-233">有关详细信息，请导航到" [我可以使用：用空格分隔的功能颜色表示法"？][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span><span class="sxs-lookup"><span data-stu-id="f3944-233">For more information, navigate to [Can I use: Space-separated functional color notations?][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span></span>  

<span data-ttu-id="f3944-234">Chromium [问题#1072952][CR1072952]</span><span class="sxs-lookup"><span data-stu-id="f3944-234">Chromium issue [#1072952][CR1072952]</span></span>  

### <a name="deprecation-of-the-properties-pane-in-the-elements-panel"></a><span data-ttu-id="f3944-235">在"元素"面板中弃用"属性"窗格</span><span class="sxs-lookup"><span data-stu-id="f3944-235">Deprecation of the Properties pane in the Elements panel</span></span>  

<span data-ttu-id="f3944-236">Elements \*\*\*\* 工具中的"**属性**"窗格已弃用。</span><span class="sxs-lookup"><span data-stu-id="f3944-236">The **Properties** pane in the **Elements** tool is deprecated.</span></span>  <span data-ttu-id="f3944-237">改为 `console.dir($0)` 在 **控制台** 中运行。</span><span class="sxs-lookup"><span data-stu-id="f3944-237">Run `console.dir($0)` in the **Console** instead.</span></span>  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="已弃用的属性窗格" lightbox="../../media/2020/05/properties.msft.png":::
   <span data-ttu-id="f3944-239">已弃**用的属性窗格**</span><span class="sxs-lookup"><span data-stu-id="f3944-239">The deprecated **Properties** pane</span></span>  
:::image-end:::  

#### <a name="references"></a><span data-ttu-id="f3944-240">参考</span><span class="sxs-lookup"><span data-stu-id="f3944-240">References</span></span>  

*   [<span data-ttu-id="f3944-241">console.dir () </span><span class="sxs-lookup"><span data-stu-id="f3944-241">console.dir()</span></span>][DevtoolsConsoleApiDir]  
*   [<span data-ttu-id="f3944-242">$0</span><span class="sxs-lookup"><span data-stu-id="f3944-242">$0</span></span>][DevtoolsConsoleUtilitiesDom]  

### <a name="app-shortcuts-support-in-the-manifest-pane"></a><span data-ttu-id="f3944-243">清单窗格中的应用程序快捷方式支持</span><span class="sxs-lookup"><span data-stu-id="f3944-243">App shortcuts support in the Manifest pane</span></span>  

<span data-ttu-id="f3944-244">应用快捷方式可帮助用户在 Web 应用中快速启动常见任务或推荐任务。</span><span class="sxs-lookup"><span data-stu-id="f3944-244">App shortcuts help users quickly start common or recommended tasks within a web app.</span></span>  <span data-ttu-id="f3944-245">应用快捷方式菜单只针对安装在用户的桌面或移动设备上的渐进式 [Web][PwaIndex] 应用显示。</span><span class="sxs-lookup"><span data-stu-id="f3944-245">The app shortcuts menu is shown only for [Progressive Web Apps][PwaIndex] that are installed on the user's desktop or mobile device.</span></span>  

<!--For more information, navigate to [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text=""清单"窗格中的应用快捷方式" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  <span data-ttu-id="f3944-247">"清单"窗格中 **的应用** 快捷方式</span><span class="sxs-lookup"><span data-stu-id="f3944-247">App shortcuts in the **Manifest** pane</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="f3944-248">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="f3944-248">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="f3944-249">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="f3944-249">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="f3944-250">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="f3944-250">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="f3944-251">与 Microsoft Edge Devtools 团队联系</span><span class="sxs-lookup"><span data-stu-id="f3944-251">Getting in touch with Microsoft Edge Devtools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/settings-icon.msft.png  
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/toggle-screencast-icon.msft.png  
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/refresh-page-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/media/record-icon.msft.png  

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 模拟器|Microsoft Docs"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - 控制台 API 参考|Microsoft Docs"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象 - 控制台实用程序 API |Microsoft Docs"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "使用颜色选取器更改颜色 - CSS |Microsoft Docs"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "箱 - 自定义|Microsoft Docs"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并修复 Microsoft Edge&quot;开发工具问题&quot;选项卡|Microsoft Docs"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "远程调试 Android 设备|Microsoft Docs"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "远程调试 Surface Duo 仿真器|Microsoft Docs"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备|Microsoft Docs"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "检查资源配置的详细信息|Microsoft Docs"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动|Microsoft Docs"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 应用上的渐进式 Web |Microsoft Docs"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android 应用"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "空格分隔的功能颜色表示法 - MDN |我可以使用"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定|Chromium Bug"  
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG |Chromium Bug"  
[CR1040019]: https://crbug.com/1040019 "DevTools：在样式窗格中轻松预览图像和背景|Chromium Bug"  
[CR1040025]: https://crbug.com/1040025 "DevTools：在元素弹出窗口中显示基本的 a11y |Chromium Bug"  
[CR1048378]: https://crbug.com/1048378 "针对高对比度模式模式的 DevTools UI |Chromium Bug"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium Bug"  
[CR1068116]: https://crbug.com/1068116 "发货问题面板|Chromium Bug"  
[CR1072952]: https://crbug.com/1072952 "DevTools：颜色选取器应生成新式 CSS 颜色语法|Chromium Bug"  
[CR1075437]: https://crbug.com/1075437 "DevTools：添加对 CSS&quot;revert&quot;关键字/值|Chromium Bug"  
[CR1076112]: https://crbug.com/1076112 "Devtools 个性化设置 - 箱大小调整器"  
[CR1081486]: https://crbug.com/1081486 "对于屏幕广播模式下的导航按钮，键盘焦点不可见|Chromium Bug"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus 应为&quot;已实现&quot;，而不是&quot;已解决&quot;|V8 bug"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 "从颜色 3 - CSS 颜色模块级别 4 更改|W3C CSS 工作组编辑器草稿"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. 前景色：&quot;颜色&quot;- CSS 颜色模块级别 4 |W3C CSS 工作组编辑器草稿"  

[DesktopEdge]: https://www.microsoft.com/edge/ "推出新的 Microsoft Edge"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "状态和状态 - 空位/承诺-取消|GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "还原|MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "浏览器兼容性|MDN"  

[VisualStudioCode]: https://code.visualstudio.com/ "Visual Studio 代码"  
[VisualStudioCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Windows 的键盘快捷方式"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "轴：键盘|WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "轴：将角色值|WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "在 Windows 应用商店中打开或关闭高对比度|Windows 支持"  

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
> <span data-ttu-id="f3944-296">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f3944-296">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f3944-297">原始页面位于[此处](https://developer.chrome.com/blog/new-in-devtools-84)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f3944-297">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-84) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f3944-299">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f3944-299">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
