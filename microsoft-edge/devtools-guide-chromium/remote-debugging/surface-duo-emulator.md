---
title: Get Started with Remote Debugging Surface Duo emulators
author: zoherghadyali
ms.author: zoghadya
ms.date: 04/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, remote debugging, android, surface duo
ms.openlocfilehash: af6fa6433b0bc6bba0599e6e9a805235504caadd
ms.sourcegitcommit: 966bfc60040acc794b6ee20eb2084bc8264a4852
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "10621500"
---
# <span data-ttu-id="e748d-103">Get Started with Remote Debugging Surface Duo emulators</span><span class="sxs-lookup"><span data-stu-id="e748d-103">Get Started with Remote Debugging Surface Duo emulators</span></span>

<span data-ttu-id="e748d-104">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][AndroidEdge] on a [Surface Duo][SurfaceDuo] emulator from a desktop instance of [Microsoft Edge][DesktopEdge].</span><span class="sxs-lookup"><span data-stu-id="e748d-104">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][AndroidEdge] on a [Surface Duo][SurfaceDuo] emulator from a desktop instance of [Microsoft Edge][DesktopEdge].</span></span> <span data-ttu-id="e748d-105">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][RemoteDebuggingAndroid].</span><span class="sxs-lookup"><span data-stu-id="e748d-105">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][RemoteDebuggingAndroid].</span></span>

## <span data-ttu-id="e748d-106">Before you Begin</span><span class="sxs-lookup"><span data-stu-id="e748d-106">Before you Begin</span></span>

<span data-ttu-id="e748d-107">Install the [Surface Duo SDK][DuoSdk] before running the [Surface Duo emulator][DuoEmulator].</span><span class="sxs-lookup"><span data-stu-id="e748d-107">Install the [Surface Duo SDK][DuoSdk] before running the [Surface Duo emulator][DuoEmulator].</span></span> <span data-ttu-id="e748d-108">For more information, see [Get the Surface Duo SDK][DuoSdkdocs].</span><span class="sxs-lookup"><span data-stu-id="e748d-108">For more information, see [Get the Surface Duo SDK][DuoSdkdocs].</span></span>

## <span data-ttu-id="e748d-109">Step 1: Navigate to edge://inspect</span><span class="sxs-lookup"><span data-stu-id="e748d-109">Step 1: Navigate to edge://inspect</span></span>

<span data-ttu-id="e748d-110">Open a desktop instance of [Microsoft Edge][DesktopEdge], and navigate to `edge://inspect`.</span><span class="sxs-lookup"><span data-stu-id="e748d-110">Open a desktop instance of [Microsoft Edge][DesktopEdge], and navigate to `edge://inspect`.</span></span>

> ##### <span data-ttu-id="e748d-111">Figure 1</span><span class="sxs-lookup"><span data-stu-id="e748d-111">Figure 1</span></span>  
> <span data-ttu-id="e748d-112">The `edge://inspect` page in Microsoft Edge on the desktop ![The edge://inspect page in Microsoft Edge on the desktop][ImageEdgeInspect]</span><span class="sxs-lookup"><span data-stu-id="e748d-112">The `edge://inspect` page in Microsoft Edge on the desktop ![The edge://inspect page in Microsoft Edge on the desktop][ImageEdgeInspect]</span></span>

> [!NOTE]
> <span data-ttu-id="e748d-113">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DuoEmulator], restart the emulator.</span><span class="sxs-lookup"><span data-stu-id="e748d-113">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DuoEmulator], restart the emulator.</span></span>

## <span data-ttu-id="e748d-114">Step 2: Launch the Surface Duo emulator</span><span class="sxs-lookup"><span data-stu-id="e748d-114">Step 2: Launch the Surface Duo emulator</span></span>

<span data-ttu-id="e748d-115">Launch the [Surface Duo emulator][DuoEmulator].</span><span class="sxs-lookup"><span data-stu-id="e748d-115">Launch the [Surface Duo emulator][DuoEmulator].</span></span> <span data-ttu-id="e748d-116">Notice that the emulator displays 2 different screens running on the emulator.</span><span class="sxs-lookup"><span data-stu-id="e748d-116">Notice that the emulator displays 2 different screens running on the emulator.</span></span>

> ##### <span data-ttu-id="e748d-117">Figure 2</span><span class="sxs-lookup"><span data-stu-id="e748d-117">Figure 2</span></span>
> <span data-ttu-id="e748d-118">The Surface Duo emulator ![The Surface Duo emulator][ImageDuoEmulator]</span><span class="sxs-lookup"><span data-stu-id="e748d-118">The Surface Duo emulator ![The Surface Duo emulator][ImageDuoEmulator]</span></span>  

## <span data-ttu-id="e748d-119">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span><span class="sxs-lookup"><span data-stu-id="e748d-119">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span></span>

<span data-ttu-id="e748d-120">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DuoEmulator] to display the Apps Drawer.</span><span class="sxs-lookup"><span data-stu-id="e748d-120">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DuoEmulator] to display the Apps Drawer.</span></span> <span data-ttu-id="e748d-121">Choose **Edge** to launch the [Microsoft Edge app][AndroidEdge].</span><span class="sxs-lookup"><span data-stu-id="e748d-121">Choose **Edge** to launch the [Microsoft Edge app][AndroidEdge].</span></span>

> ##### <span data-ttu-id="e748d-122">Figure 3</span><span class="sxs-lookup"><span data-stu-id="e748d-122">Figure 3</span></span>
> <span data-ttu-id="e748d-123">The Microsoft Edge app on the Surface Duo emulator ![The Microsoft Edge app on the Surface Duo emulator][ImageDuoEmulatorEdge]</span><span class="sxs-lookup"><span data-stu-id="e748d-123">The Microsoft Edge app on the Surface Duo emulator ![The Microsoft Edge app on the Surface Duo emulator][ImageDuoEmulatorEdge]</span></span>  

<span data-ttu-id="e748d-124">Navigate to the website or app that you want to debug in the [Microsoft Edge app][AndroidEdge].</span><span class="sxs-lookup"><span data-stu-id="e748d-124">Navigate to the website or app that you want to debug in the [Microsoft Edge app][AndroidEdge].</span></span>

## <span data-ttu-id="e748d-125">Step 4: Debug your web content from the Surface Duo emulator</span><span class="sxs-lookup"><span data-stu-id="e748d-125">Step 4: Debug your web content from the Surface Duo emulator</span></span> 

<span data-ttu-id="e748d-126">Switch back to the desktop instance of [Microsoft Edge][DesktopEdge].</span><span class="sxs-lookup"><span data-stu-id="e748d-126">Switch back to the desktop instance of [Microsoft Edge][DesktopEdge].</span></span> <span data-ttu-id="e748d-127">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaDocs] that are running on the [Surface Duo emulator][DuoEmulator].</span><span class="sxs-lookup"><span data-stu-id="e748d-127">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaDocs] that are running on the [Surface Duo emulator][DuoEmulator].</span></span>

> ##### <span data-ttu-id="e748d-128">Figure 4</span><span class="sxs-lookup"><span data-stu-id="e748d-128">Figure 4</span></span>
> <span data-ttu-id="e748d-129">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator ![The edge://inspect page displays a list of the open tabs in the Microsoft Edge app running on the emulator][ImageEdgeInspectTargets]</span><span class="sxs-lookup"><span data-stu-id="e748d-129">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator ![The edge://inspect page displays a list of the open tabs in the Microsoft Edge app running on the emulator][ImageEdgeInspectTargets]</span></span>  

> [!NOTE]
> <span data-ttu-id="e748d-130">If you do not see **SurfaceDuoEmulator** on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][AndroidEdge] on the [Surface Duo Emulator][DuoEmulator].</span><span class="sxs-lookup"><span data-stu-id="e748d-130">If you do not see **SurfaceDuoEmulator** on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][AndroidEdge] on the [Surface Duo Emulator][DuoEmulator].</span></span> <span data-ttu-id="e748d-131">For additional troubleshooting steps, see the [troubleshooting section for Android devices][TroubleshootingAndroid].</span><span class="sxs-lookup"><span data-stu-id="e748d-131">For additional troubleshooting steps, see the [troubleshooting section for Android devices][TroubleshootingAndroid].</span></span>

<span data-ttu-id="e748d-132">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span><span class="sxs-lookup"><span data-stu-id="e748d-132">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span></span> <span data-ttu-id="e748d-133">The [Microsoft Edge DevTools][DevToolsDocs] will open in a new window.</span><span class="sxs-lookup"><span data-stu-id="e748d-133">The [Microsoft Edge DevTools][DevToolsDocs] will open in a new window.</span></span> <span data-ttu-id="e748d-134">Choose **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] to view the web content from your [Surface Duo emulator][DuoEmulator] in the DevTools window.</span><span class="sxs-lookup"><span data-stu-id="e748d-134">Choose **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] to view the web content from your [Surface Duo emulator][DuoEmulator] in the DevTools window.</span></span> <span data-ttu-id="e748d-135">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DuoEmulator].</span><span class="sxs-lookup"><span data-stu-id="e748d-135">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DuoEmulator].</span></span>

> ##### <span data-ttu-id="e748d-136">Figure 5</span><span class="sxs-lookup"><span data-stu-id="e748d-136">Figure 5</span></span>
> <span data-ttu-id="e748d-137">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator ![Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator][ImageDevTools]</span><span class="sxs-lookup"><span data-stu-id="e748d-137">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator ![Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator][ImageDevTools]</span></span>  

> [!NOTE]
> <span data-ttu-id="e748d-138">If you span the [Microsoft Edge app][AndroidEdge] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span><span class="sxs-lookup"><span data-stu-id="e748d-138">If you span the [Microsoft Edge app][AndroidEdge] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span></span> <span data-ttu-id="e748d-139">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DuoEmulator] instead of the screencast.</span><span class="sxs-lookup"><span data-stu-id="e748d-139">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DuoEmulator] instead of the screencast.</span></span>

## <span data-ttu-id="e748d-140">Additional Resources</span><span class="sxs-lookup"><span data-stu-id="e748d-140">Additional Resources</span></span>

<span data-ttu-id="e748d-141">The web is a great platform for the new class of foldable and dual-screen devices because you can write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span><span class="sxs-lookup"><span data-stu-id="e748d-141">The web is a great platform for the new class of foldable and dual-screen devices because you can write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span></span> <span data-ttu-id="e748d-142">For more information, see these additional resources to get started building web content for these new devices.</span><span class="sxs-lookup"><span data-stu-id="e748d-142">For more information, see these additional resources to get started building web content for these new devices.</span></span>

- [<span data-ttu-id="e748d-143">Documentation for creating apps on dual-screen devices</span><span class="sxs-lookup"><span data-stu-id="e748d-143">Documentation for creating apps on dual-screen devices</span></span>][DualScreenDocs]
- [<span data-ttu-id="e748d-144">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span><span class="sxs-lookup"><span data-stu-id="e748d-144">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span></span>][WebPlatformExplainer]
- [<span data-ttu-id="e748d-145">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span><span class="sxs-lookup"><span data-stu-id="e748d-145">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span></span>][DeveloperDay]

<!-- image links -->  
[ImageEdgeInspect]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page.msft.png "Figure 1: The edge://inspect page in Microsoft Edge on the desktop"
[ImageDuoEmulator]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator.msft.png "Figure 2: The Surface Duo emulator"
[ImageDuoEmulatorEdge]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator-edge.msft.png "Figure 3: The Microsoft Edge app on the Surface Duo emulator"
[ImageEdgeInspectTargets]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png "Figure 4: The edge://inspect page displays a list of the open tabs in the Microsoft Edge app running on the emulator"
[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png
[ImageDevTools]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-devtools.msft.png "Figure 5: Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator"

<!-- links -->  
[RemoteDebuggingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Get Started with Remote Debugging Android Devices"
[PwaDocs]: /microsoft-edge/progressive-web-apps-chromium/index "Progressive Web Apps on Windows"
[DevToolsDocs]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) Developer Tools"
[TroubleshootingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index#troubleshooting-devtools-is-not-detecting-the-android-device "Troubleshooting: DevTools is not detecting the Android device"

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android app"
[SurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "Introducing Surface Duo"
[DesktopEdge]: https://www.microsoft.com/edge/ "Introducing the new Microsoft Edge"
[DuoEmulator]: https://docs.microsoft.com/dual-screen/android/use-emulator "Use the Surface DUo emulator"
[DuoSdk]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface Duo SDK Preview Release"
[DuoSdkDocs]: https://docs.microsoft.com/dual-screen/android/get-duo-sdk "Get the Surface Duo SDK"
[DualScreenDocs]: https://docs.microsoft.com/dual-screen/ "Create apps for dual-screen devices"
[WebPlatformExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "Web Platform Primitives for Enlightened Experiences on Foldable Devices"
[DeveloperDay]: https://youtu.be/DXrZWsqXPVc "How to build dual-screen experiences for the website and web apps"
