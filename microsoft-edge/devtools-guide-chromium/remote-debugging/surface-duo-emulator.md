---
description: 远程调试 Surface Duo 仿真程序入门。
title: 远程调试 Surface Duo 仿真程序入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发工具, 远程调试, android, surface duo
ms.openlocfilehash: 61f903a5b929b7ee7b924938cf6ddc21a9783ca7
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439324"
---
# <a name="get-started-with-remote-debugging-surface-duo-emulators"></a><span data-ttu-id="febb6-104">远程调试 Surface Duo 仿真程序入门</span><span class="sxs-lookup"><span data-stu-id="febb6-104">Get started with Remote Debugging Surface Duo emulators</span></span>  

<span data-ttu-id="febb6-105">本文将介绍从 [Microsoft Edge][MicrosoftEdge] 的桌面版实例远程调试 [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo] 仿真程序上 [Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]的 web 内容。</span><span class="sxs-lookup"><span data-stu-id="febb6-105">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on a [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo] emulator from a desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="febb6-106">有关在 Surface Duo 设备上进行调试的信息，请遵循[远程调试 Android 设备][DevtoolsRemoteDebuggingMain]的指南。</span><span class="sxs-lookup"><span data-stu-id="febb6-106">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][DevtoolsRemoteDebuggingMain].</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="febb6-107">开始之前</span><span class="sxs-lookup"><span data-stu-id="febb6-107">Before you Begin</span></span>

<span data-ttu-id="febb6-108">运行[Surface Duo 仿真程序][DualScreenAndroidUseEmulator]前，先安装 [Surface Duo SDK][MicrosoftDownload100847]。</span><span class="sxs-lookup"><span data-stu-id="febb6-108">Install the [Surface Duo SDK][MicrosoftDownload100847] before running the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="febb6-109">有关详细信息，请导航到[获取 Surface Duo SDK][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="febb6-109">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

## <a name="step-1-navigate-to-edgeinspect"></a><span data-ttu-id="febb6-110">步骤 1：导航到 edge://inspect</span><span class="sxs-lookup"><span data-stu-id="febb6-110">Step 1: Navigate to edge://inspect</span></span>  

<span data-ttu-id="febb6-111">打开 [Microsoft Edge][MicrosoftEdge] 的桌面实例，然后导航到 `edge://inspect`。</span><span class="sxs-lookup"><span data-stu-id="febb6-111">Open a desktop instance of [Microsoft Edge][MicrosoftEdge], and navigate to `edge://inspect`.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="桌面上 Microsoft Edge 中的 edge://inspect 页面" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   <span data-ttu-id="febb6-113">桌面上的 Microsoft Edge `edge://inspect` 页面</span><span class="sxs-lookup"><span data-stu-id="febb6-113">The `edge://inspect` page in Microsoft Edge on the desktop</span></span>  
:::image-end:::

> [!NOTE]
> <span data-ttu-id="febb6-114">如果 `edge://inspect` 页面无法识别 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]，请重新启动仿真程序。</span><span class="sxs-lookup"><span data-stu-id="febb6-114">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DualScreenAndroidUseEmulator], restart the emulator.</span></span>  

## <a name="step-2-launch-the-surface-duo-emulator"></a><span data-ttu-id="febb6-115">步骤 2：启动 Surface Duo 仿真程序</span><span class="sxs-lookup"><span data-stu-id="febb6-115">Step 2: Launch the Surface Duo emulator</span></span>  

<span data-ttu-id="febb6-116">启动 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="febb6-116">Launch the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="febb6-117">请注意，仿真程序显示 2 个在仿真程序上运行的不同屏幕。</span><span class="sxs-lookup"><span data-stu-id="febb6-117">Notice that the emulator displays 2 different screens running on the emulator.</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Duo 仿真程序" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   <span data-ttu-id="febb6-119">Surface Duo 仿真程序</span><span class="sxs-lookup"><span data-stu-id="febb6-119">The Surface Duo emulator</span></span>  
:::image-end:::  

## <a name="step-3-load-your-web-content-in-microsoft-edge-on-the-surface-duo-emulator"></a><span data-ttu-id="febb6-120">步骤 3：在 Surface Duo 仿真程序上将 web 内容载入 Microsoft Edge </span><span class="sxs-lookup"><span data-stu-id="febb6-120">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span></span>  

<span data-ttu-id="febb6-121">在任一屏幕上，将 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]的“收藏夹托盘”上向上轻扫，以显示“应用抽屉”。</span><span class="sxs-lookup"><span data-stu-id="febb6-121">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DualScreenAndroidUseEmulator] to display the Apps Drawer.</span></span>  <span data-ttu-id="febb6-122">选择 **Edge** 以启动 [Microsoft Edge 应用程序][GooglePlayStoreAppsComMicrosoftEmmx]。</span><span class="sxs-lookup"><span data-stu-id="febb6-122">Choose **Edge** to launch the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Duo 仿真程序上的 Microsoft Edge 应用" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   <span data-ttu-id="febb6-124">Surface Duo 仿真程序上的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="febb6-124">The Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

<span data-ttu-id="febb6-125">导航到想要在 [Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]中调试的网站或 应用。</span><span class="sxs-lookup"><span data-stu-id="febb6-125">Navigate to the website or app that you want to debug in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx].</span></span>  

## <a name="step-4-debug-your-web-content-from-the-surface-duo-emulator"></a><span data-ttu-id="febb6-126">步骤 4：从 Surface Duo 仿真程序调试 Web 内容</span><span class="sxs-lookup"><span data-stu-id="febb6-126">Step 4: Debug your web content from the Surface Duo emulator</span></span>  

<span data-ttu-id="febb6-127">切换回 [Microsoft Edge][MicrosoftEdge] 的桌面实例。</span><span class="sxs-lookup"><span data-stu-id="febb6-127">Switch back to the desktop instance of [Microsoft Edge][MicrosoftEdge].</span></span>  <span data-ttu-id="febb6-128">现在，`edge://inspect` 页面显示 **SurfaceDuoEmulator**以及在 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]上运行的打开的选项卡或 [PWAs][ProgressiveWebAppsIndex]列表。</span><span class="sxs-lookup"><span data-stu-id="febb6-128">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][ProgressiveWebAppsIndex] that are running on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text="edge://inspect 页面在模拟器上运行的 Microsoft Edge 应用程序中显示打开选项卡的列表" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   <span data-ttu-id="febb6-130">`edge://inspect` 页面在模拟器上运行的 Microsoft Edge 应用程序中显示打开选项卡的列表</span><span class="sxs-lookup"><span data-stu-id="febb6-130">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="febb6-131">如果在 `edge://inspect` 页上未显示 **SurfaceDuoEmulator**，请尝试在 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]上的 [Microsoft Edge应用程序][GooglePlayStoreAppsComMicrosoftEmmx]中打开或关闭选项卡。</span><span class="sxs-lookup"><span data-stu-id="febb6-131">If **SurfaceDuoEmulator** is not displayed on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] on the [Surface Duo Emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="febb6-132">有关其他疑难解答步骤，请导航到 [Android 设备的疑难解答部分][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。</span><span class="sxs-lookup"><span data-stu-id="febb6-132">For additional troubleshooting steps, navigate to [troubleshooting section for Android devices][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice].</span></span>  

<span data-ttu-id="febb6-133">从模拟器上运行的打开的选项卡列表中，在具有要调试的 Web 内容的选项卡上选择“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="febb6-133">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span></span>  <span data-ttu-id="febb6-134">[Microsoft Edge 开发工具][DevtoolsIndex]将在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="febb6-134">The [Microsoft Edge DevTools][DevtoolsIndex] will open in a new window.</span></span>  <span data-ttu-id="febb6-135">选择“**切换截屏视频**” \(![切换截屏视频t](../media/toggle-screencast-icon.msft.png)\)，从开发工具窗口中的 [ Surface Duo 仿真程序][DualScreenAndroidUseEmulator]查看 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="febb6-135">Choose **Toggle Screencast** \(![Toggle Screencast](../media/toggle-screencast-icon.msft.png)\) to view the web content from your [Surface Duo emulator][DualScreenAndroidUseEmulator] in the DevTools window.</span></span>  <span data-ttu-id="febb6-136">现在可以使用 Microsoft Edge 开发工具在 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]上调试 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="febb6-136">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="使用 Microsoft Edge 开发工具在 Surface Duo 仿真程序的 Microsoft Edge 应用程序中调试 Bing" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   <span data-ttu-id="febb6-138">使用 Microsoft Edge 开发工具在 Surface Duo 仿真程序的 Microsoft Edge 应用程序中调试 Bing</span><span class="sxs-lookup"><span data-stu-id="febb6-138">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="febb6-139">如果 [Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]在仿真程序中跨两个屏幕，截屏视频将反映应用程序的新尺寸，而不是铰链。</span><span class="sxs-lookup"><span data-stu-id="febb6-139">If you span the [Microsoft Edge app][GooglePlayStoreAppsComMicrosoftEmmx] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span></span>  <span data-ttu-id="febb6-140">若要了解网站如何影响 Web 内容的布局，请使用 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator] ，而不是截屏视频。</span><span class="sxs-lookup"><span data-stu-id="febb6-140">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DualScreenAndroidUseEmulator] instead of the screencast.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="febb6-141">其他资源</span><span class="sxs-lookup"><span data-stu-id="febb6-141">Additional Resources</span></span>  

<span data-ttu-id="febb6-142">对于新的可折叠和双屏幕设备类，Web 是一个很好的平台，因为可以编写 HTML、CSS 和 JavaScript 一次，并且可以在单屏、双屏和可折叠设备上显示出色的外观。</span><span class="sxs-lookup"><span data-stu-id="febb6-142">The web is a great platform for the new class of foldable and dual-screen devices because you may write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span></span>  <span data-ttu-id="febb6-143">有关更多信息，请导航至以下其他资源，以开始为这些新设备构建 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="febb6-143">For more information, navigate to the following additional resources to get started building web content for these new devices.</span></span>  

*   [<span data-ttu-id="febb6-144">有关在双屏设备上创建应用的文档</span><span class="sxs-lookup"><span data-stu-id="febb6-144">Documentation for creating apps on dual-screen devices</span></span>][DualScreenIndex]  
*   [<span data-ttu-id="febb6-145">Microsoft Edge Web 平台介绍在可折叠和双屏设备上构建 Web 体验的新 API</span><span class="sxs-lookup"><span data-stu-id="febb6-145">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span></span>][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [<span data-ttu-id="febb6-146">Microsoft 365 开发人员日会话录制：如何为网站和 Web 应用构建双屏体验</span><span class="sxs-lookup"><span data-stu-id="febb6-146">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span></span>][YoutubeDxrzwsqxpvc]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="febb6-147">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="febb6-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发工具 | Microsoft 文档"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows 应用上的渐进式 Web |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "Android 设备远程调试入门 | Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "疑难解答：开发工具未检测 Android 设备 - Android 设备远程调试入门 | Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "为双屏设备创建应用 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 仿真程序 | Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo SDK | Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "推出新的 Microsoft Edge"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新 Surface Duo | Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "下载 Surface Duo SDK 预览版 | Microsoft 下载中心"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge: Web Browser | GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "可折叠设备启发式体验的 Web 平台基元 - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "如何为网站和 Web 应用构建双屏体验 | YouTube"  
