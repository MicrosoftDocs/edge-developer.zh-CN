---
description: 远程调试 Surface Duo 仿真器入门。
title: 远程调试 Surface Duo 仿真器入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 远程调试， android， surface duo
ms.openlocfilehash: a9696e63528a674d349b78fbdec2a1b804f61c49
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398012"
---
# <a name="get-started-with-remote-debugging-surface-duo-emulators"></a><span data-ttu-id="41713-104">远程调试 Surface Duo 仿真器入门</span><span class="sxs-lookup"><span data-stu-id="41713-104">Get started with Remote Debugging Surface Duo emulators</span></span>  

<span data-ttu-id="41713-105">本文将介绍从 Microsoft Edge 桌面实例在[Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo]仿真器上的[Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx]应用中远程调试[Web 内容的过程][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="41713-105">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on a [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo] emulator from a desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="41713-106">有关在 Surface Duo 设备上进行调试的信息，请按照我们的远程 [调试 Android 设备的指南操作][DevtoolsRemoteDebuggingMain]。</span><span class="sxs-lookup"><span data-stu-id="41713-106">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][DevtoolsRemoteDebuggingMain].</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="41713-107">开始之前</span><span class="sxs-lookup"><span data-stu-id="41713-107">Before you Begin</span></span>

<span data-ttu-id="41713-108">在运行[Surface Duo 仿真器][MicrosoftDownload100847]之前安装[Surface Duo SDK。][DualScreenAndroidUseEmulator]</span><span class="sxs-lookup"><span data-stu-id="41713-108">Install the [Surface Duo SDK][MicrosoftDownload100847] before running the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="41713-109">有关详细信息，请导航到["获取 Surface Duo SDK"。][DualScreenAndroidGetDuoSdk]</span><span class="sxs-lookup"><span data-stu-id="41713-109">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

## <a name="step-1-navigate-to-edgeinspect"></a><span data-ttu-id="41713-110">步骤 1：导航到edge://inspect</span><span class="sxs-lookup"><span data-stu-id="41713-110">Step 1: Navigate to edge://inspect</span></span>  

<span data-ttu-id="41713-111">打开 Microsoft Edge 的 [桌面实例][MicrosoftEdge]，然后导航到 `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="41713-111">Open a desktop instance of [Microsoft Edge][MicrosoftEdge], and navigate to `edge://inspect`.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="桌面edge://inspect Microsoft Edge 中的"edge://inspect"页面" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   <span data-ttu-id="41713-113">`edge://inspect`桌面版 Microsoft Edge 中的页面</span><span class="sxs-lookup"><span data-stu-id="41713-113">The `edge://inspect` page in Microsoft Edge on the desktop</span></span>  
:::image-end:::

> [!NOTE]
> <span data-ttu-id="41713-114">如果 `edge://inspect` 页面无法识别 Surface [Duo 仿真器][DualScreenAndroidUseEmulator]，请重新启动该仿真器。</span><span class="sxs-lookup"><span data-stu-id="41713-114">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DualScreenAndroidUseEmulator], restart the emulator.</span></span>  

## <a name="step-2-launch-the-surface-duo-emulator"></a><span data-ttu-id="41713-115">步骤 2：启动 Surface Duo 仿真器</span><span class="sxs-lookup"><span data-stu-id="41713-115">Step 2: Launch the Surface Duo emulator</span></span>  

<span data-ttu-id="41713-116">启动 [Surface Duo 仿真器][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="41713-116">Launch the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="41713-117">请注意，仿真器显示 2 个在仿真器上运行的不同屏幕。</span><span class="sxs-lookup"><span data-stu-id="41713-117">Notice that the emulator displays 2 different screens running on the emulator.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Duo 仿真器" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   <span data-ttu-id="41713-119">Surface Duo 仿真器</span><span class="sxs-lookup"><span data-stu-id="41713-119">The Surface Duo emulator</span></span>  
:::image-end:::  

## <a name="step-3-load-your-web-content-in-microsoft-edge-on-the-surface-duo-emulator"></a><span data-ttu-id="41713-120">步骤 3：在 Surface Duo 仿真器上的 Microsoft Edge 中加载 Web 内容</span><span class="sxs-lookup"><span data-stu-id="41713-120">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span></span>  

<span data-ttu-id="41713-121">在任一屏幕上，向上轻扫 [Surface Duo][DualScreenAndroidUseEmulator] 仿真器收藏夹托盘以显示应用箱。</span><span class="sxs-lookup"><span data-stu-id="41713-121">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DualScreenAndroidUseEmulator] to display the Apps Drawer.</span></span>  <span data-ttu-id="41713-122">选择 **"边缘** "以 [启动 Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]。</span><span class="sxs-lookup"><span data-stu-id="41713-122">Choose **Edge** to launch the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Duo 模拟器上的 Microsoft Edge 应用" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   <span data-ttu-id="41713-124">Surface Duo 模拟器上的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="41713-124">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="41713-125">导航到你想要在 Microsoft Edge 应用中调试 [的网站或应用][GooglePlayStoreAppsComMicrosoftEmmx]。</span><span class="sxs-lookup"><span data-stu-id="41713-125">Navigate to the website or app that you want to debug in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

## <a name="step-4-debug-your-web-content-from-the-surface-duo-emulator"></a><span data-ttu-id="41713-126">步骤 4：从 Surface Duo 仿真器调试 Web 内容</span><span class="sxs-lookup"><span data-stu-id="41713-126">Step 4: Debug your web content from the Surface Duo emulator</span></span>  

<span data-ttu-id="41713-127">切换回 Microsoft Edge 的 [桌面实例][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="41713-127">Switch back to the desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="41713-128">该 `edge://inspect` 页面现在显示**SurfaceDwnEmulator，** 其中列出了在 Surface Duo 仿真器上运行的打开的选项卡或[PWA。][DualScreenAndroidUseEmulator] [][ProgressiveWebAppsIndex]</span><span class="sxs-lookup"><span data-stu-id="41713-128">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][ProgressiveWebAppsIndex] that are running on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text=""edge://inspect"页显示运行在仿真器上的 Microsoft Edge 应用中打开的选项卡的列表" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   <span data-ttu-id="41713-130">该 `edge://inspect` 页面在模拟器上运行的 Microsoft Edge 应用中显示打开的选项卡的列表</span><span class="sxs-lookup"><span data-stu-id="41713-130">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="41713-131">如果**SurfaceDatorEmulator**未显示在页面上，请尝试在 Surface Duo 模拟器上的 Microsoft Edge 应用中打开或 `edge://inspect` [关闭选项卡][DualScreenAndroidUseEmulator]。 [][GooglePlayStoreAppsComMicrosoftEmmx]</span><span class="sxs-lookup"><span data-stu-id="41713-131">If **SurfaceDuoEmulator** is not displayed on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on the [Surface Duo Emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="41713-132">有关其他疑难解答步骤，请导航到 [Android 设备的疑难解答部分][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。</span><span class="sxs-lookup"><span data-stu-id="41713-132">For additional troubleshooting steps, navigate to [troubleshooting section for Android devices][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice].</span></span>  

<span data-ttu-id="41713-133">从模拟器上运行的打开选项卡列表中，在包含要调试\*\*\*\* 的 Web 内容的选项卡上选择"检查"。</span><span class="sxs-lookup"><span data-stu-id="41713-133">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span></span>  <span data-ttu-id="41713-134">[Microsoft Edge DevTools][DevtoolsIndex]将在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="41713-134">The [Microsoft Edge DevTools][DevtoolsIndex] will open in a new window.</span></span>  <span data-ttu-id="41713-135">Choose **Toggle Screencast** \ (![ Toggle Screencast ][ImageToggleScreencastIcon] \) to view the web content from your [Surface Duo emulator][DualScreenAndroidUseEmulator] in the DevTools window.</span><span class="sxs-lookup"><span data-stu-id="41713-135">Choose **Toggle Screencast** \(![Toggle Screencast][ImageToggleScreencastIcon]\) to view the web content from your [Surface Duo emulator][DualScreenAndroidUseEmulator] in the DevTools window.</span></span>  <span data-ttu-id="41713-136">你现在可以使用 Microsoft Edge DevTools 调试 [Surface Duo][DualScreenAndroidUseEmulator]仿真器上的 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="41713-136">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="使用 Microsoft Edge DevTools 在 Surface Duo 仿真器上的 Microsoft Edge 应用中调试必应" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   <span data-ttu-id="41713-138">使用 Microsoft Edge DevTools 在 Surface Duo 仿真器上的 Microsoft Edge 应用中调试必应</span><span class="sxs-lookup"><span data-stu-id="41713-138">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="41713-139">如果你将 [Microsoft Edge 应用跨][GooglePlayStoreAppsComMicrosoftEmmx] 模拟器中的两个屏幕，屏幕视频将反映应用的新大小，但不会反映屏幕大小。</span><span class="sxs-lookup"><span data-stu-id="41713-139">If you span the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span></span>  <span data-ttu-id="41713-140">若要了解云台如何影响 Web 内容的布局，请使用 [Surface Duo 仿真][DualScreenAndroidUseEmulator] 器，而不是屏幕视频。</span><span class="sxs-lookup"><span data-stu-id="41713-140">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DualScreenAndroidUseEmulator] instead of the screencast.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="41713-141">其他资源</span><span class="sxs-lookup"><span data-stu-id="41713-141">Additional Resources</span></span>  

<span data-ttu-id="41713-142">对于可折叠和双屏设备的新类，Web 是一个很好的平台，因为你可以编写 HTML、CSS 和 JavaScript 一次，并且让它在单屏、双屏和可折叠设备中外观都非常好。</span><span class="sxs-lookup"><span data-stu-id="41713-142">The web is a great platform for the new class of foldable and dual-screen devices because you may write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span></span>  <span data-ttu-id="41713-143">有关详细信息，请导航到以下其他资源，开始为这些新设备生成 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="41713-143">For more information, navigate to the following additional resources to get started building web content for these new devices.</span></span>  

*   [<span data-ttu-id="41713-144">有关在双屏设备上创建应用的文档</span><span class="sxs-lookup"><span data-stu-id="41713-144">Documentation for creating apps on dual-screen devices</span></span>][DualScreenIndex]  
*   [<span data-ttu-id="41713-145">在可折叠和双屏幕设备上构建 Web 体验的新 API 的 Microsoft Edge Web 平台说明器</span><span class="sxs-lookup"><span data-stu-id="41713-145">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span></span>][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [<span data-ttu-id="41713-146">录制 Microsoft 365 开发人员日会话：如何为网站和 Web 应用构建双屏体验</span><span class="sxs-lookup"><span data-stu-id="41713-146">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span></span>][YoutubeDxrzwsqxpvc]  

<!-- image links -->  

[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows 应用上的渐进式 Web |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "开始远程调试 Android 设备|Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "疑难解答：DevTools 未检测 Android 设备 - 开始远程调试 Android 设备|Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "为两屏设备创建|Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface D一仿真器|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo SDK |Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新 Microsoft Edge 的介绍"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo |Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "下载 Surface Duo SDK 预览版|Microsoft 下载中心"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge：Web 浏览器|GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "可折叠设备的启发式体验的 Web 平台基元 - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "如何为网站和 Web 应用生成双屏幕|YouTube"  
