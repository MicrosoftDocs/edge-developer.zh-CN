---
title: DevTools 应用中的 () 功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: aa39e5d7811d4a614e055a8e0479c74278efbefd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942190"
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

# <span data-ttu-id="ed8da-103">DevTools 应用中的 () 功能</span><span class="sxs-lookup"><span data-stu-id="ed8da-103">What's new in DevTools (Microsoft Edge 84)</span></span>  

## <span data-ttu-id="ed8da-104">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="ed8da-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="ed8da-105">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="ed8da-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="ed8da-106">请查看这些公告，尝试使用 DevTools 和 VS 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="ed8da-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="ed8da-107">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="ed8da-108">在 Windows 中，使用 Windows 高对比度模式的 DevTools</span><span class="sxs-lookup"><span data-stu-id="ed8da-108">Use the DevTools in Windows high contrast mode</span></span>

<span data-ttu-id="ed8da-109">当 Windows 处于高对比度模式时，Microsoft Edge 开发工具现在以高对比度模式显示。</span><span class="sxs-lookup"><span data-stu-id="ed8da-109">The Microsoft Edge DevTools are now displayed in high contrast mode when Windows is in high contrast mode.</span></span>  

:::image type="complex" source="../../media/2020/05/high-contrast.msft.png" alt-text="高对比度模式下的 Microsoft Edge 开发工具" lightbox="../../media/2020/05/high-contrast.msft.png":::
   <span data-ttu-id="ed8da-111">高对比度模式下的 Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="ed8da-111">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-112">[按照说明在 Windows 中打开高对比度模式][MicrosoftSupportWindows10HighContrastMode]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-112">[Follow the instructions to turn on high contrast mode in Windows][MicrosoftSupportWindows10HighContrastMode].</span></span>  <span data-ttu-id="ed8da-113">按下或按 Microsoft Edge 打开开发 `F12` 工具 `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="ed8da-113">Open the DevTools in Microsoft Edge by pressing `F12` or `Ctrl`+`Shift`+`I`.</span></span>  <span data-ttu-id="ed8da-114">DevTools 以高对比度模式显示。</span><span class="sxs-lookup"><span data-stu-id="ed8da-114">The DevTools are displayed in high contrast mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="ed8da-115">Microsoft Edge 开发工具当前在 Windows 上支持高对比度模式，但在 macOS 上（而不是在 mac 上）。</span><span class="sxs-lookup"><span data-stu-id="ed8da-115">The Microsoft Edge DevTools currently support high contrast mode on Windows but not on macOS.</span></span> 

<span data-ttu-id="ed8da-116">Chromium [#1048378][CR1048378]</span><span class="sxs-lookup"><span data-stu-id="ed8da-116">Chromium issue [#1048378][CR1048378]</span></span>  

### <span data-ttu-id="ed8da-117">匹配 DevTools 与 VS 代码中的键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="ed8da-117">Match keyboard shortcuts in the DevTools to VS Code</span></span>  

<span data-ttu-id="ed8da-118">借助 [此](#getting-in-touch-with-microsoft-edge-devtools-team) 反馈 [和 Chromium 公共问题跟踪器][CRIssuesList]，Microsoft Edge DevTools 团队了解到了希望能自定义 DevTools 中的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="ed8da-118">From your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) and the [Chromium public issue tracker][CRIssuesList], the Microsoft Edge DevTools team learned that you wanted the ability to customize keyboard shortcuts in the DevTools.</span></span>  <span data-ttu-id="ed8da-119">在 Microsoft Edge 84 中，你现在能够将 DevTools 中的键盘快捷方式与 [VS 代码相匹配，而][VSCode]该代码只是团队正在为支持快捷方式自定义而使用的功能之一。</span><span class="sxs-lookup"><span data-stu-id="ed8da-119">In Microsoft Edge 84, you are now able to match keyboard shortcuts in the DevTools to [VS Code][VSCode], which is just one of the features the team is working on for shortcut customization.</span></span>  

:::image type="complex" source="../../media/2020/05/keyboard-shortcut.msft.png" alt-text="匹配 DevTools 与 VS 代码中的键盘快捷方式" lightbox="../../media/2020/05/keyboard-shortcut.msft.png":::
   <span data-ttu-id="ed8da-121">高对比度模式下的 Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="ed8da-121">The Microsoft Edge DevTools in high contrast mode</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-122">要试用实测，请通过按下或选择 DevTools 右上角的"开发工具设置"图标打开 `?` ![ ][ImageSettingsIcon] DevTools 设置。</span><span class="sxs-lookup"><span data-stu-id="ed8da-122">To try the experiment, open DevTools Settings by pressing `?` or selecting the ![DevTools Settings icon][ImageSettingsIcon] icon in the top-right corner of the DevTools.</span></span>  <span data-ttu-id="ed8da-123">导航到 **"实境"部分，** 检查 \*\*"启用自定义键盘快捷方式设置"选项卡， (需重新加载) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="ed8da-123">Navigate to the **Experiments** section and check **Enable custom keyboard shortcuts settings tab (requires reload)**.</span></span>  <span data-ttu-id="ed8da-124">现在重新加载开发人员工具，再次打开设置，并导航到"快 **捷方式"** 部分。</span><span class="sxs-lookup"><span data-stu-id="ed8da-124">Now reload the DevTools, open Settings again, and navigate to the **Shortcuts** section.</span></span>  

<span data-ttu-id="ed8da-125">从**预设 () 选择 Devtools** **默认模板，\*\*\*\*然后选择Visual Studio代码**。</span><span class="sxs-lookup"><span data-stu-id="ed8da-125">Select **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="ed8da-126">DevTools 中的键盘快捷方式现在与 VS 代码中等效操作的快捷方式匹配。</span><span class="sxs-lookup"><span data-stu-id="ed8da-126">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in VS Code.</span></span>  

<span data-ttu-id="ed8da-127">例如，用于暂停或继续在 VS 代码中运行脚 [本的键盘快捷方式][VSCodeShortcuts] `F5` 为。</span><span class="sxs-lookup"><span data-stu-id="ed8da-127">For example, the keyboard shortcut for pausing or continuing running a script in [VS Code][VSCodeShortcuts] is `F5`.</span></span>  <span data-ttu-id="ed8da-128">借助**DevTools 高级 (者预设**) ，DevTools 中的相同快捷方式 `F8` **是预设 Visual Studio 代码，** 它的快捷方式也是。 `F5`</span><span class="sxs-lookup"><span data-stu-id="ed8da-128">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8` but with the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="ed8da-129">此功能当前在 Microsoft Edge 84 中以实例实例的形式在 Microsoft Edge 中提供，因此请与 [团队分享反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="ed8da-129">The feature is currently available in Microsoft Edge 84 as an experiment, so please share your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team) with the team!</span></span>  

<span data-ttu-id="ed8da-130">Chromium [问题#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="ed8da-130">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="ed8da-131">远程调试 Surface Duo 模拟器</span><span class="sxs-lookup"><span data-stu-id="ed8da-131">Remote debug Surface Duo emulators</span></span>  

<span data-ttu-id="ed8da-132">你现在可以使用[Microsoft Edge DevTools][DevToolsChromiumGuide]的完整功能远程调试[在 Surface Duo][DualScreensAndroidEmulator]仿真器中运行的 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="ed8da-132">You are now able to remotely debug your web content running in the [Surface Duo emulator][DualScreensAndroidEmulator] using the full power of the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

<span data-ttu-id="ed8da-133">通过 [Surface Duo 模拟器，][DualScreensAndroidEmulator]你能够测试 Web 内容在一个可折人化和全新屏幕设备中的呈现方式。</span><span class="sxs-lookup"><span data-stu-id="ed8da-133">With the [Surface Duo emulator][DualScreensAndroidEmulator], you are able to test how your web content renders on a new class of foldable and dual-screen devices.</span></span>  <span data-ttu-id="ed8da-134">该模拟器运行 Android 操作系统并提供 [Microsoft Edge Android 应用][AndroidEdge]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-134">The emulator runs the Android operating system and provides the [Microsoft Edge Android app][AndroidEdge].</span></span>  <span data-ttu-id="ed8da-135">在 Microsoft Edge 应用中加 [载你的 Web][AndroidEdge] 内容，并使用 [Microsoft Edge DevTools 对其进行调试][DevToolsChromiumGuide]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-135">Load your web content in the [Microsoft Edge app][AndroidEdge] and debug it with the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  

:::image type="complex" source="../../media/2020/05/surface-duo-emulator.msft.png" alt-text="在 Surface Duo 仿真器上运行的 Microsoft Edge 应用" lightbox="../../media/2020/05/surface-duo-emulator.msft.png":::
   <span data-ttu-id="ed8da-137">Surface Duo 模拟器上的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="ed8da-137">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-138">`edge://inspect` [Microsoft Edge][DesktopEdge]桌面实例中的页面显示**SurfaceDuoEmulator，** 其中包含[在 Surface Duo][DualScreensAndroidEmulator]仿真器上运行的打开选项卡或[PWA][PwaIndex]列表。</span><span class="sxs-lookup"><span data-stu-id="ed8da-138">The `edge://inspect` page in a desktop instance of [Microsoft Edge][DesktopEdge] shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaIndex] that are running on the [Surface Duo emulator][DualScreensAndroidEmulator].</span></span>  

:::image type="complex" source="../../media/2020/05/edge-inspect.msft.png" alt-text="该edge://inspect页面显示在仿真器上运行的 Microsoft Edge 应用中打开的选项卡的列表" lightbox="../../media/2020/05/edge-inspect.msft.png":::
   <span data-ttu-id="ed8da-140">`edge://inspect`该页面显示仿真器上运行的 Microsoft Edge 应用中打开的选项卡列表</span><span class="sxs-lookup"><span data-stu-id="ed8da-140">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>
:::image-end:::  

<span data-ttu-id="ed8da-141">为**想要调试的**选项卡或 PWA 选择检查，打开[Microsoft Edge DevTools。][DevToolsChromiumGuide]</span><span class="sxs-lookup"><span data-stu-id="ed8da-141">Selecting **inspect** for the tab or PWA that you want to debug opens the [Microsoft Edge DevTools][DevToolsChromiumGuide].</span></span>  <span data-ttu-id="ed8da-142">[按照循环指南远程调试 Surface Duo 模拟器上的 Web 内容][DevToolsRemoteDebugDuoEmulator]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-142">[Follow the step-by-step guide to remotely debug your web content on the Surface Duo emulator][DevToolsRemoteDebugDuoEmulator].</span></span>  

### <span data-ttu-id="ed8da-143">更轻松地调整 DevTools 绘制器的大小</span><span class="sxs-lookup"><span data-stu-id="ed8da-143">Resize the DevTools drawer more easily</span></span>  

<span data-ttu-id="ed8da-144">在 Microsoft Edge 83 或更早版本中，你只能通过将鼠标悬停在 Drawer 工具栏内部来调整 [DevTools][DevToolsDrawer] Drawer 的大小。</span><span class="sxs-lookup"><span data-stu-id="ed8da-144">In Microsoft Edge 83 or earlier, you were only able to resize the [DevTools Drawer][DevToolsDrawer] by hovering inside the Drawer's toolbar.</span></span>  <span data-ttu-id="ed8da-145">绘图器的行为与使用适用于窗格的其他调整大小控件不同，将鼠标悬停在窗格的边框上方以调整其大小。</span><span class="sxs-lookup"><span data-stu-id="ed8da-145">The Drawer behaved differently than the other resize controls for panes in the DevTools where you hover over the border of the pane to resize it.</span></span>  <span data-ttu-id="ed8da-146">选择下图，查看调整绘图器在 83 版或早期版本 Microsoft Edge 中如何工作。</span><span class="sxs-lookup"><span data-stu-id="ed8da-146">Select the following image to see how resizing the Drawer worked in version 83 or earlier of Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-83.msft.png" alt-text="在 Microsoft Edge 83 中调整 DevTools 绘图器的大小" lightbox="../../media/2020/05/drawer-83.msft.gif":::
   <span data-ttu-id="ed8da-148">在 Microsoft Edge 83 中调整 DevTools 绘图器的大小</span><span class="sxs-lookup"><span data-stu-id="ed8da-148">Resizing the DevTools Drawer in Microsoft Edge 83</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="ed8da-149">从 Microsoft Edge 84 开始，你现在可以通过将鼠标悬停在绘图器边框上方来调整绘图器的大小。</span><span class="sxs-lookup"><span data-stu-id="ed8da-149">Starting with Microsoft Edge 84, you are now able to resize the Drawer by hovering over the border of the Drawer.</span></span>  <span data-ttu-id="ed8da-150">此更改将使用在 DevTools 中调整其他窗格大小的方式对齐 DevTools Drawer 的大小调整行为。</span><span class="sxs-lookup"><span data-stu-id="ed8da-150">This change aligns the behavior resizing the DevTools Drawer with the way you resize other panes in the DevTools.</span></span>  <span data-ttu-id="ed8da-151">选择下图，在 Microsoft Edge 84 中查看操作的大小调整。</span><span class="sxs-lookup"><span data-stu-id="ed8da-151">Select the following image to see resizing in action in Microsoft Edge 84.</span></span>  

:::image type="complex" source="../../media/2020/05/drawer-84.msft.png" alt-text="在 Microsoft Edge 84 中调整 DevTools 绘图器的大小" lightbox="../../media/2020/05/drawer-84.msft.gif":::
   <span data-ttu-id="ed8da-153">在 Microsoft Edge 84 中调整 DevTools 绘图器的大小</span><span class="sxs-lookup"><span data-stu-id="ed8da-153">Resizing the DevTools Drawer in Microsoft Edge 84</span></span>
:::image-end:::  

<!--todo:  create png that represents the gif information  -->  

<span data-ttu-id="ed8da-154">Chromium [问题#1076112][CR1076112]</span><span class="sxs-lookup"><span data-stu-id="ed8da-154">Chromium issue [#1076112][CR1076112]</span></span>  

### <span data-ttu-id="ed8da-155">屏幕播中导航按钮显示焦点</span><span class="sxs-lookup"><span data-stu-id="ed8da-155">Screencasting navigation buttons display focus</span></span>  

<span data-ttu-id="ed8da-156">远程调试[Android 设备][DevToolsRemoteDebugAndroid][、Windows 10 设备][DevToolsRemoteDebugWindows]或 Surface [Duo 模拟器时][DevToolsRemoteDebugDuoEmulator]，你可以使用 ![ DevTools 左上角的切换屏幕图标切换屏幕 ][ImageScreencastingIcon] 。</span><span class="sxs-lookup"><span data-stu-id="ed8da-156">When remote debugging an [Android device][DevToolsRemoteDebugAndroid], a [Windows 10 device][DevToolsRemoteDebugWindows], or a [Surface Duo emulator][DevToolsRemoteDebugDuoEmulator], you are able to toggle screencasting with the ![Toggle Screencast][ImageScreencastingIcon] icon in the top-left corner of the DevTools.</span></span>  <span data-ttu-id="ed8da-157">启用屏幕功能后，你可以从"开发工具"窗口在远程设备上的 Microsoft Edge 中导航选项卡。</span><span class="sxs-lookup"><span data-stu-id="ed8da-157">With screencasting enabled, you are able to navigate the tab in Microsoft Edge on the remote device from the DevTools window.</span></span>  <span data-ttu-id="ed8da-158">在 Microsoft Edge 84 中，这些导航按钮现在也是可访问的键盘。</span><span class="sxs-lookup"><span data-stu-id="ed8da-158">In Microsoft Edge 84, these navigation buttons are now also keyboard accessible.</span></span>  

:::image type="complex" source="../../media/2020/05/screencasting-nav.msft.png" alt-text="从屏幕粘贴的 URL 栏按 Shift+Tab 可将焦点置于"刷新"按钮上" lightbox="../../media/2020/05/screencasting-nav.msft.png":::
   <span data-ttu-id="ed8da-160">从 `Shift` + `Tab` 屏幕上按下的 URL 栏可焦点**位于"刷新"按钮**上</span><span class="sxs-lookup"><span data-stu-id="ed8da-160">Pressing `Shift`+`Tab` from the screencasted URL bar shows focus on the **Refresh** button</span></span>
:::image-end:::  

<span data-ttu-id="ed8da-161">Chromium [问题#1081486][CR1081486]</span><span class="sxs-lookup"><span data-stu-id="ed8da-161">Chromium issue [#1081486][CR1081486]</span></span>  

### <span data-ttu-id="ed8da-162">现可访问"网络"面板详细信息窗格</span><span class="sxs-lookup"><span data-stu-id="ed8da-162">Network panel Details pane is now accessible</span></span>  

<span data-ttu-id="ed8da-163">在 Microsoft Edge 84 中[，"网络"][DevToolsNetworkDetails]面板中的"详细信息"窗格现在在你打开网络日志中的资源时获取**Network**[焦点][DevToolsNetworkLog]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-163">In Microsoft Edge 84, the [Details pane][DevToolsNetworkDetails] in the **Network** panel now takes focus when you open it for a resource in the [Network Log][DevToolsNetworkLog].</span></span>  <span data-ttu-id="ed8da-164">此更改允许屏幕阅读器读出"详细信息"窗格的内容并 **与其进行** 交互。</span><span class="sxs-lookup"><span data-stu-id="ed8da-164">This change allows screen readers to read out and interact with the content of the **Details** pane.</span></span>  

:::image type="complex" source="../../media/2020/05/network-details.msft.png" alt-text="打开时"网络"面板中的"详细信息"窗格获取焦点" lightbox="../../media/2020/05/network-details.msft.png":::
   <span data-ttu-id="ed8da-166">打开 **时"** 网络"面 **板中的** "详细信息"窗格获取焦点</span><span class="sxs-lookup"><span data-stu-id="ed8da-166">The **Details** pane in the **Network** panel takes focus when opened</span></span>
:::image-end:::  

<span data-ttu-id="ed8da-167">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="ed8da-167">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="ed8da-168">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="ed8da-168">Announcements from the Chromium project</span></span>  

<span data-ttu-id="ed8da-169">以下部分公布给开源 Chromium 项目的 Microsoft Edge 84 中可用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="ed8da-169">The following sections announce additional features available in Microsoft Edge 84 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="ed8da-170">使用 DevTools Drawer 中新问题工具解决网站问题</span><span class="sxs-lookup"><span data-stu-id="ed8da-170">Fix site issues with the new Issues tool in the DevTools Drawer</span></span>

<span data-ttu-id="ed8da-171">DevTools **绘图** 器中的新"问题"工具构建以帮助减少主机通知模拟和 **待筛选邮件**。</span><span class="sxs-lookup"><span data-stu-id="ed8da-171">The new **Issues** tool in the DevTools Drawer was built to help reduce the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="ed8da-172">当前， **主机是** 网站开发人员、库、框架和 Microsoft Edge 的中心位置，用于记录消息、警告和错误。</span><span class="sxs-lookup"><span data-stu-id="ed8da-172">Currently, the **Console** is the central place for website developers, libraries, frameworks, and Microsoft Edge to log messages, warnings, and errors.</span></span>  <span data-ttu-id="ed8da-173">**问题**工具聚合以一种结构化、聚合和可操作的方式从浏览器中显示警告，链接指向 Microsoft Edge DevTools 中受影响资源的链接，并提供有关如何修复问题的指南。</span><span class="sxs-lookup"><span data-stu-id="ed8da-173">The **Issues** tool aggregates warnings from the browser in a structured, aggregated, and actionable way, links to affected resources within Microsoft Edge DevTools, and provides guidance on how to fix the issues.</span></span>  <span data-ttu-id="ed8da-174">随时间推移，在 Microsoft Edge 环境（而不是主机）中应该会看到更多**Issues**更多相关警告，这应**Console**有助于减少主机中的**杂乱**。</span><span class="sxs-lookup"><span data-stu-id="ed8da-174">Over time, you should see more and more warnings in Microsoft Edge surfacing in the **Issues** tool rather than the **Console**, which should help reduce the clutter in the **Console**.</span></span>  

<span data-ttu-id="ed8da-175">若要开始使用，请参阅 ["查找并修复 Microsoft Edge DevTools 问题"工具的问题][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-175">To get started, see [Find And Fix Problems With The Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2020/05/issues.msft.png" alt-text="DevTools Drawer 中的"问题"工具" lightbox="../../media/2020/05/issues.msft.png":::
   <span data-ttu-id="ed8da-177">DevTools Drawer 中的"问题"工具**Issues**</span><span class="sxs-lookup"><span data-stu-id="ed8da-177">The **Issues** tool in the DevTools Drawer</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-178">Chromium [#1068116][CR1068116]</span><span class="sxs-lookup"><span data-stu-id="ed8da-178">Chromium issue [#1068116][CR1068116]</span></span>  

### <span data-ttu-id="ed8da-179">查看"检查模式"工具提示中的辅助功能信息</span><span class="sxs-lookup"><span data-stu-id="ed8da-179">View accessibility information in the Inspect Mode tooltip</span></span>  

<span data-ttu-id="ed8da-180">" **检查模式"** 工具提示现在指示该元素名称和角色是否为 [可行][WebhintHintsAxeNameRoleValue] 且可 [使用键盘焦点][WebhintHintsAxeKeyboard]。</span><span class="sxs-lookup"><span data-stu-id="ed8da-180">The **Inspect Mode** tooltip now indicates whether the element has an accessible [name and role][WebhintHintsAxeNameRoleValue] and is [keyboard-focusable][WebhintHintsAxeKeyboard].</span></span>  

<!--todo:  add link inspect mode tooltip (WebdevCls) when section is live  -->  
<!--todo:  add link name and role (WebdevLabelsText) when section is live  -->  
<!--todo:  add link keyboard-focusable (WebdevControlFocus) when section is live  -->  

:::image type="complex" source="../../media/2020/05/a11y.msft.png" alt-text="包含辅助功能信息的"检查模式"工具提示" lightbox="../../media/2020/05/a11y.msft.png":::
  <span data-ttu-id="ed8da-182">包含 **辅助功能信息的** "检查模式"工具提示</span><span class="sxs-lookup"><span data-stu-id="ed8da-182">The **Inspect Mode** tooltip with accessibility information</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-183">Chromium [问题#1040025][CR1040025]</span><span class="sxs-lookup"><span data-stu-id="ed8da-183">Chromium issue [#1040025][CR1040025]</span></span>  

### <span data-ttu-id="ed8da-184">性能面板更新</span><span class="sxs-lookup"><span data-stu-id="ed8da-184">Performance panel updates</span></span>  

#### <span data-ttu-id="ed8da-185">查看页脚中的"总阻止时间"信息</span><span class="sxs-lookup"><span data-stu-id="ed8da-185">View Total Blocking Time information in the footer</span></span>  

<span data-ttu-id="ed8da-186">记录加载性能之后 **，"性能"** 面板现显示了页脚中的 (TBT\) 信息的总阻止时间 \和"数据"。</span><span class="sxs-lookup"><span data-stu-id="ed8da-186">After recording your load performance, the **Performance** panel now shows Total Blocking Time \(TBT\) information in the footer.</span></span>  <span data-ttu-id="ed8da-187">TBT 是一个加载性能指标，有助于量量一个页面为可用时长。</span><span class="sxs-lookup"><span data-stu-id="ed8da-187">TBT is a load performance metric that helps quantify how long a page takes to become usable.</span></span>  <span data-ttu-id="ed8da-188">它实就是测量页面显示的时长是不动 (因为内容呈现到屏幕\) ;但实际上并不可用，因为 JavaScript 会阻止主线程，因此页面不对用户输入做出响应。</span><span class="sxs-lookup"><span data-stu-id="ed8da-188">It essentially measures how long a page appears to be usable \(because the content is rendered to the screen\); but is not actually usable, because JavaScript is blocking the main thread and therefore the page does not respond to user input.</span></span>  <span data-ttu-id="ed8da-189">TBT 是表示第一次输入延迟大同小计的主要指标。</span><span class="sxs-lookup"><span data-stu-id="ed8da-189">TBT is the main metric for approximating First Input Delay.</span></span>  

<!--todo:  add link Total Blocking Time (TBT) (WebdevTbt) when section is live  -->  
<!--todo:  add link lab metric (WebdevMeasureSpeedLabField) when section is live  -->  
<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  

<span data-ttu-id="ed8da-190">要获取"总阻止时间"信息，请不要**Refresh Page**使用刷新页面刷新 ![ 页面图标 ][ImageRefreshPageIcon] 工作流记录页面加载性能。</span><span class="sxs-lookup"><span data-stu-id="ed8da-190">To get Total Blocking Time information, do not use the **Refresh Page** ![Refresh page icon][ImageRefreshPageIcon] workflow for recording page load performance.</span></span>  

<span data-ttu-id="ed8da-191">反之，选择 **"录** ![ 制记录 ][ImageRecordIcon] "图标，手动重新加载页面，等待页面加载，然后停止录制。</span><span class="sxs-lookup"><span data-stu-id="ed8da-191">Instead, select **Record** ![Record icon][ImageRecordIcon], manually reload the page, wait for the page to load, and then stop recording.</span></span>  

<span data-ttu-id="ed8da-192">如果看到 `Total Blocking Time: Unavailable` ，Microsoft Edge DevTools 无法从 Microsoft Edge 中的内部分析数据获得所需信息。</span><span class="sxs-lookup"><span data-stu-id="ed8da-192">If you see `Total Blocking Time: Unavailable`, Microsoft Edge DevTools did not get the required information from the internal profiling data in Microsoft Edge.</span></span>  

:::image type="complex" source="../../media/2020/05/tbt.msft.png" alt-text=""性能"面板录制页脚脚中的总阻止时间信息" lightbox="../../media/2020/05/tbt.msft.png":::
   <span data-ttu-id="ed8da-194">"性能"面板录制页脚脚 **中的总阻止** 时间信息</span><span class="sxs-lookup"><span data-stu-id="ed8da-194">Total Blocking Time information in the footer of a **Performance** panel recording</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-195">Chromium [问题#1054381][CR1054381]</span><span class="sxs-lookup"><span data-stu-id="ed8da-195">Chromium issue [#1054381][CR1054381]</span></span>  

#### <span data-ttu-id="ed8da-196">新体验部分中的布局 Shift 事件</span><span class="sxs-lookup"><span data-stu-id="ed8da-196">Layout Shift events in the new Experience section</span></span>  

<span data-ttu-id="ed8da-197">"性能 **"面** 板的 **"** 新体验"部分可帮助你检测布局改班。</span><span class="sxs-lookup"><span data-stu-id="ed8da-197">The new **Experience** section of the **Performance** panel helps you detect layout shifts.</span></span>  <span data-ttu-id="ed8da-198">累计布局 Shift \ (CLS\) 是一种指标，可帮助你量避，使你衡量不必要的可视化性。</span><span class="sxs-lookup"><span data-stu-id="ed8da-198">Cumulative Layout Shift \(CLS\) is a metric that helps you quantify unwanted visual instability.</span></span>

<!--todo:  add link Core Web Vitals (WebdevCoreWebVitals) when section is live  -->  
<!--todo:  add link layout shifts (WebdevCls) when section is live  -->  

<span data-ttu-id="ed8da-199">选择 **布局 Shift** 事件以查看摘要窗格中布局排 **班的详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="ed8da-199">Select the **Layout Shift** event to see the details of the layout shift in the **Summary** pane.</span></span>  <span data-ttu-id="ed8da-200">将鼠标悬**停在"移动到"\*\*\*\*字段和"移动到**"字段上，可视化布局发生的位置。</span><span class="sxs-lookup"><span data-stu-id="ed8da-200">Hover over the **Moved from** and **Moved to** fields to visualize where the layout shift occurred.</span></span>  

:::image type="complex" source="../../media/2020/05/cls.msft.png" alt-text="布局移班的详细信息" lightbox="../../media/2020/05/cls.msft.png":::
   <span data-ttu-id="ed8da-202">布局移班的详细信息</span><span class="sxs-lookup"><span data-stu-id="ed8da-202">The details of a layout shift</span></span>  
:::image-end:::  

### <span data-ttu-id="ed8da-203">在主机中更加准确的承诺术语</span><span class="sxs-lookup"><span data-stu-id="ed8da-203">More accurate promise terminology in the Console</span></span>  

<span data-ttu-id="ed8da-204">在记录时 `Promise` ， **主机未正确** 提供的 `PromiseStatus` 值设置为 `resolved` 。</span><span class="sxs-lookup"><span data-stu-id="ed8da-204">When logging a `Promise`, the **Console** incorrectly provided `PromiseStatus` value set to `resolved`.</span></span>  

:::image type="complex" source="../../media/2020/05/resolved.msft.png" alt-text="使用旧已解决术语的主机示例" lightbox="../../media/2020/05/resolved.msft.png":::
   <span data-ttu-id="ed8da-206">使用旧 **术语的** 主 `resolved` 机示例</span><span class="sxs-lookup"><span data-stu-id="ed8da-206">An example of the **Console** using the old `resolved` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-207">主 **机现在使用** 该术语 `fulfilled` ，该术语与规范 `Promise` 对齐。</span><span class="sxs-lookup"><span data-stu-id="ed8da-207">The **Console** now uses the term `fulfilled`, which aligns with the `Promise` specification.</span></span>  <span data-ttu-id="ed8da-208">有关规范的详细信息 `Promise` ，请参阅[GitHub 上的"州和 Fates"。](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md)</span><span class="sxs-lookup"><span data-stu-id="ed8da-208">For more information about the `Promise` specification, see [States and Fates on GitHub](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md).</span></span>  

:::image type="complex" source="../../media/2020/05/fulfilled.msft.png" alt-text="使用新的实施术语的主机示例" lightbox="../../media/2020/05/fulfilled.msft.png":::
  <span data-ttu-id="ed8da-210">使用新 **术语的** 主 `fulfilled` 机示例</span><span class="sxs-lookup"><span data-stu-id="ed8da-210">An example of the **Console** using the new `fulfilled` terminology</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-211">V8 问题 [#6751][CRV86751]</span><span class="sxs-lookup"><span data-stu-id="ed8da-211">V8 issue [#6751][CRV86751]</span></span>  

### <span data-ttu-id="ed8da-212">"样式"窗格将更新</span><span class="sxs-lookup"><span data-stu-id="ed8da-212">Styles pane updates</span></span>  

#### <span data-ttu-id="ed8da-213">对还原关键字的支持</span><span class="sxs-lookup"><span data-stu-id="ed8da-213">Support for the revert keyword</span></span>  

<span data-ttu-id="ed8da-214">"样式"窗格的 **自动完成** UI 现在检测 [到"还][MDNRevert] 原 CSS"关键字，它将属性的级集值还原到应用到元素样式设置的上一个值。</span><span class="sxs-lookup"><span data-stu-id="ed8da-214">The autocomplete UI of the **Styles** pane now detects the [revert][MDNRevert] CSS keyword, which reverts the cascaded value of a property to the previous value applied to the styling of the element.</span></span>  

:::image type="complex" source="../../media/2020/05/revert.msft.png" alt-text="设置属性值进行还原" lightbox="../../media/2020/05/revert.msft.png":::
  <span data-ttu-id="ed8da-216">设置属性值进行还原</span><span class="sxs-lookup"><span data-stu-id="ed8da-216">Setting the value of a property to revert</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-217">Chromium [#1075437][CR1075437]</span><span class="sxs-lookup"><span data-stu-id="ed8da-217">Chromium issue [#1075437][CR1075437]</span></span>  

#### <span data-ttu-id="ed8da-218">图像预览</span><span class="sxs-lookup"><span data-stu-id="ed8da-218">Image previews</span></span>  

<span data-ttu-id="ed8da-219">将鼠标悬 `background-image` 停在 **"样式"窗格中的** 某个值上，可在工具提示中查看图像预览。</span><span class="sxs-lookup"><span data-stu-id="ed8da-219">Hover over a `background-image` value in the **Styles** pane to see a preview of the image in a tooltip.</span></span>  

:::image type="complex" source="../../media/2020/05/image-preview.msft.png" alt-text="将鼠标指悬停在背景图像值上" lightbox="../../media/2020/05/image-preview.msft.png":::
  <span data-ttu-id="ed8da-221">将鼠标悬停在 `background-image` 某个值上</span><span class="sxs-lookup"><span data-stu-id="ed8da-221">Hovering over a `background-image` value</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-222">Chromium [问题#1040019][CR1040019]</span><span class="sxs-lookup"><span data-stu-id="ed8da-222">Chromium issue [#1040019][CR1040019]</span></span>  

#### <span data-ttu-id="ed8da-223">"颜色选取器"现在使用空格分隔的函数颜色表示</span><span class="sxs-lookup"><span data-stu-id="ed8da-223">Color Picker now uses space-separated functional color notation</span></span>  

<span data-ttu-id="ed8da-224">[CSS Color Module Level 指定][CSSWGDraftsColor4Changes3] 颜色函数（例如 `rgb()` ）应支持空格分隔的参数。</span><span class="sxs-lookup"><span data-stu-id="ed8da-224">[CSS Color Module Level 4][CSSWGDraftsColor4Changes3] specifies that color functions, such as `rgb()`, should support space-separated arguments.</span></span>  <span data-ttu-id="ed8da-225">例如，`rgb(0, 0, 0)` 与 `rbg(0 0 0)` 等效。</span><span class="sxs-lookup"><span data-stu-id="ed8da-225">For example, `rgb(0, 0, 0)` is equivalent to `rbg(0 0 0)`.</span></span>  

<span data-ttu-id="ed8da-226">当你通过按住[并选择值][DevtoolsCssReferenceColorPicker]在"样式"窗格中选择颜色表示的颜色或在"颜色表示**Styles** `Shift` "之间 `background-color` 交替时，应看到空格分隔的参数语法。</span><span class="sxs-lookup"><span data-stu-id="ed8da-226">When you choose colors with the [Color Picker][DevtoolsCssReferenceColorPicker] or alternate between color representations in the **Styles** pane by holding `Shift` and selecting the `background-color` value, you should see the space-separated argument syntax.</span></span>  

:::image type="complex" source="../../media/2020/05/color.msft.png" alt-text="在"样式"窗格中使用空格分隔的参数" lightbox="../../media/2020/05/color.msft.png":::
  <span data-ttu-id="ed8da-228">在"样式"窗格中使用空格 **分隔** 的参数</span><span class="sxs-lookup"><span data-stu-id="ed8da-228">Using space-separated arguments in the **Styles** pane</span></span>  
:::image-end:::  

<span data-ttu-id="ed8da-229">您还应会在计算窗格和"检查模式"工具提示**Computed\*\*\*\*中看到**语法。</span><span class="sxs-lookup"><span data-stu-id="ed8da-229">You should also see the syntax in the **Computed** pane and the **Inspect Mode** tooltip.</span></span>  

<span data-ttu-id="ed8da-230">Microsoft Edge 开发工具正在使用新的语法，因为即将使用的 CSS 功能（如 [颜色 () ） ][CSSWGDraftsColor4Property] 不支持已弃用的逗号分隔参数语法。</span><span class="sxs-lookup"><span data-stu-id="ed8da-230">Microsoft Edge DevTools is using the new syntax because upcoming CSS features such as [color()][CSSWGDraftsColor4Property] do not support the deprecated comma-separated argument syntax.</span></span>  

<span data-ttu-id="ed8da-231">大多数浏览器中已支持使用空间分隔的参数语法一段时间。</span><span class="sxs-lookup"><span data-stu-id="ed8da-231">The space-separated argument syntax has been supported in most browsers for a while.</span></span>  <span data-ttu-id="ed8da-232">有关详细信息，请参阅" [我可以使用：空间分隔的函数颜色表示方式"？][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span><span class="sxs-lookup"><span data-stu-id="ed8da-232">For more information, see [Can I use: Space-separated functional color notations?][CaniuseMDNSpaceSeparatedFunctionalColorNotations]</span></span>  

<span data-ttu-id="ed8da-233">Chromium [#1072952][CR1072952]</span><span class="sxs-lookup"><span data-stu-id="ed8da-233">Chromium issue [#1072952][CR1072952]</span></span>  

### <span data-ttu-id="ed8da-234">"元素"面板中的"属性"窗格的弃用</span><span class="sxs-lookup"><span data-stu-id="ed8da-234">Deprecation of the Properties pane in the Elements panel</span></span>  

<span data-ttu-id="ed8da-235">**"元素"** 面**板中的"** 属性"窗格被弃用。</span><span class="sxs-lookup"><span data-stu-id="ed8da-235">The **Properties** pane in the **Elements** panel is deprecated.</span></span>  <span data-ttu-id="ed8da-236">请 `console.dir($0)` 改 **为在主机中** 运行。</span><span class="sxs-lookup"><span data-stu-id="ed8da-236">Run `console.dir($0)` in the **Console** instead.</span></span>  

:::image type="complex" source="../../media/2020/05/properties.msft.png" alt-text="弃用的属性窗格" lightbox="../../media/2020/05/properties.msft.png":::
   <span data-ttu-id="ed8da-238">弃用的 **属性** 窗格</span><span class="sxs-lookup"><span data-stu-id="ed8da-238">The deprecated **Properties** pane</span></span>  
:::image-end:::  

#### <span data-ttu-id="ed8da-239">参考</span><span class="sxs-lookup"><span data-stu-id="ed8da-239">References</span></span>  

*   [<span data-ttu-id="ed8da-240">console.dir () </span><span class="sxs-lookup"><span data-stu-id="ed8da-240">console.dir()</span></span>][DevtoolsConsoleApiDir]  
*   [<span data-ttu-id="ed8da-241">$0</span><span class="sxs-lookup"><span data-stu-id="ed8da-241">$0</span></span>][DevtoolsConsoleUtilitiesDom]  

### <span data-ttu-id="ed8da-242">清单窗格中的应用快捷方式支持</span><span class="sxs-lookup"><span data-stu-id="ed8da-242">App shortcuts support in the Manifest pane</span></span>  

<span data-ttu-id="ed8da-243">应用快捷方式可帮助用户在 Web 应用中快速启动常规任务或推荐的任务。</span><span class="sxs-lookup"><span data-stu-id="ed8da-243">App shortcuts help users quickly start common or recommended tasks within a web app.</span></span>  <span data-ttu-id="ed8da-244">仅对于用户桌面或移动设备上安装的渐进 [式 Web 应用][PwaIndex] ，将显示应用快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="ed8da-244">The app shortcuts menu is shown only for [Progressive Web Apps][PwaIndex] that are installed on the user's desktop or mobile device.</span></span>  

<!--For more information, see [Get things done quickly with app shortcuts][WebdevAppShortcuts].  -->  

<!--todo:  add link Get things done quickly with app shortcuts (WebdevAppShortcuts) when section is live -->  

:::image type="complex" source="../../media/2020/05/app-shortcuts.msft.png" alt-text="清单窗格中的应用快捷方式" lightbox="../../media/2020/05/app-shortcuts.msft.png":::
  <span data-ttu-id="ed8da-246">清单窗格 **中的应用快捷** 方式</span><span class="sxs-lookup"><span data-stu-id="ed8da-246">App shortcuts in the **Manifest** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="ed8da-247">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="ed8da-247">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="ed8da-248">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="ed8da-248">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="ed8da-249">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="ed8da-249">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="ed8da-250">与 Microsoft Edge 开发工具团队联系</span><span class="sxs-lookup"><span data-stu-id="ed8da-250">Getting in touch with Microsoft Edge Devtools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "开发工具"设置"图标"
[ImageScreencastingIcon]: /microsoft-edge/devtools-guide-chromium/remote-debugging/images/toggle-screencast-icon.msft.png ""DevTools 切换屏幕"图标"
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png ""DevTools 性能"面板"刷新页面"图标"
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png ""DevTools 性能"面板记录图标"

<!-- links -->  

[DualScreensAndroidEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 模拟器 |Microsoft 文档"

[DevtoolsConsoleApiDir]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - 主机 API 参考 |Microsoft 文档"  
[DevtoolsConsoleUtilitiesDom]: /microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象 - 主机实用工具 API 参考 |Microsoft 文档"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "使用"颜色选取器"更改颜色 - CSS 引用 |Microsoft 文档"  
[DevToolsDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "绘图 - 自定义概述 |Microsoft 文档"  
[DevToolsChromiumGuide]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft 文档"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并解决 Microsoft Edge DevTools 问题选项卡 |Microsoft 文档"  
[DevToolsRemoteDebugAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "远程调试 Android 设备入门 |Microsoft 文档"  
[DevToolsRemoteDebugDuoEmulator]: /microsoft-edge/devtools-guide-chromium/remote-debugging/surface-duo-emulator "远程调试 Surface Duo 模拟器入门 |Microsoft 文档"  
[DevToolsRemoteDebugWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备 | 入门 |Microsoft 文档"  
[DevToolsNetworkDetails]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "检查资源 |Microsoft 文档"  
[DevToolsNetworkLog]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动 |Microsoft 文档"  
[PwaIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的进度 Web 应用 |Microsoft 文档"  
<!--[DevtoolsWhatsNew201901Inspect]: /microsoft-edge/devtools-guide-chromium/whats-new/2019/01/devtools#inspect "Detailed tooltips in Inspect Mode - What's New In DevTools (Edge 73) | Microsoft Docs"  -->  

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android 应用"

[CaniuseMDNSpaceSeparatedFunctionalColorNotations]: https://caniuse.com/#feat=mdn-css_types_color_space_separated_functional_notation "分隔空间分隔的函数颜色表示符 - MDN |我可以使用"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"  
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG |Chromium bug"  
[CR1040019]: https://crbug.com/1040019 "DevTools：在"样式"窗格中轻松预览图像和背景图像 |Chromium bug"  
[CR1040025]: https://crbug.com/1040025 "DevTools：在元素弹出窗口中显示基本 a11 信息 |Chromium bug"  
[CR1048378]: https://crbug.com/1048378 "对高对比度模式的 DevTools UI 支持 |Chromium bug"  
[CR1054381]: https://crbug.com/1054381 "CR 1054381 |Chromium bug"  
[CR1068116]: https://crbug.com/1068116 ""发货问题"面板 |Chromium bug"  
[CR1072952]: https://crbug.com/1072952 "开发工具：颜色选取器应该会创建现代 CSS 颜色语法 |Chromium bug"  
[CR1075437]: https://crbug.com/1075437 "DevTools：添加对 CSS 'revert' 关键字/值的支持 |Chromium bug"  
[CR1076112]: https://crbug.com/1076112 "开发工具个性化 - 绘图器调整器大小"  
[CR1081486]: https://crbug.com/1081486 "屏幕模式下的导航按钮中不可看到键盘焦点 |Chromium bug"  
[CRV86751]: https://bugs.chromium.org/p/v8/issues/detail?id=6751 "PromiseStatus 应"fulfilled"，而不是"resolved"|V8 bug"  

[CSSWGDraftsColor4Changes3]: https://drafts.csswg.org/css-color#changes-from-3 ""颜色 3"的更改 - CSS 颜色模块级别 4 |工作组编辑器草稿的 W3C CSS 工作"  
[CSSWGDraftsColor4Property]: https://drafts.csswg.org/css-color#the-color-property "3. 前景颜色：'color' - CSS Color Module Level 4 |工作组编辑器草稿的 W3C CSS 工作"  

[DesktopEdge]: https://www.microsoft.com/edge/ "新版 Microsoft Edge 简要"  

[GithubDomenicPromiseUnwrappingStatesFates]: https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md "状态和图案 - domenic/promises-unwrapping |GitHub"  

[MDNRevert]: https://developer.mozilla.org/docs/Web/CSS/revert "还原 |MDN"  
[MDNRevertBrowserCompatibility]: https://developer.mozilla.org/docs/Web/CSS/revert#Browser_compatibility "浏览器兼容性 |MDN"  

[VSCode]: https://code.visualstudio.com/ "Visual Studio代码"  
[VSCodeShortcuts]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Windows 的代码键盘快捷方式"  

[WebhintHintsAxeKeyboard]: https://webhint.io/docs/user-guide/hints/hint-axe/keyboard/ "Axe： 键盘 |WebHint"  
[WebhintHintsAxeNameRoleValue]: https://webhint.io/docs/user-guide/hints/hint-axe/name-role-value/ "Axe：名称角色值 |WebHint"  

[MicrosoftSupportWindows10HighContrastMode]: https://support.microsoft.com/help/4026951/windows-10-turn-high-contrast-mode-on-or-off "在 Windows 中打开或关闭高对比度模式|Windows 支持"  

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
> <span data-ttu-id="ed8da-299">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ed8da-299">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ed8da-300">原始页面位于[此处](https://developers.google.com/web/updates/2020/05/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ed8da-300">The original page is found [here](https://developers.google.com/web/updates/2020/05/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ed8da-302">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ed8da-302">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
