---
title: 远程调试 Surface 双核模拟器入门
author: zoherghadyali
ms.author: zoghadya
ms.date: 04/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、远程调试、android、surface 双核
ms.openlocfilehash: af6fa6433b0bc6bba0599e6e9a805235504caadd
ms.sourcegitcommit: 966bfc60040acc794b6ee20eb2084bc8264a4852
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "10621500"
---
# <span data-ttu-id="7c10e-103">远程调试 Surface 双核模拟器入门</span><span class="sxs-lookup"><span data-stu-id="7c10e-103">Get Started with Remote Debugging Surface Duo emulators</span></span>

<span data-ttu-id="7c10e-104">在本文中，你将引导你完成从[Microsoft edge][DesktopEdge]的桌面实例远程调试[Surface 双核][SurfaceDuo]模拟器上的[Microsoft edge 应用][AndroidEdge]中的 web 内容的过程。</span><span class="sxs-lookup"><span data-stu-id="7c10e-104">In this article, you walk through the process of remotely debugging your web content in the [Microsoft Edge app][AndroidEdge] on a [Surface Duo][SurfaceDuo] emulator from a desktop instance of [Microsoft Edge][DesktopEdge].</span></span> <span data-ttu-id="7c10e-105">有关在 Surface 双核设备上进行调试的信息，请参阅我们的 [远程调试 Android 设备][RemoteDebuggingAndroid]指南。</span><span class="sxs-lookup"><span data-stu-id="7c10e-105">For information on debugging on a Surface Duo device, follow our guide for [remote debugging Android devices][RemoteDebuggingAndroid].</span></span>

## <span data-ttu-id="7c10e-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="7c10e-106">Before you Begin</span></span>

<span data-ttu-id="7c10e-107">在运行[Surface 双核处理器技术][DuoEmulator]之前安装[surface 双核 SDK][DuoSdk] 。</span><span class="sxs-lookup"><span data-stu-id="7c10e-107">Install the [Surface Duo SDK][DuoSdk] before running the [Surface Duo emulator][DuoEmulator].</span></span> <span data-ttu-id="7c10e-108">有关详细信息，请参阅 [获取 Surface 双核 SDK][DuoSdkdocs]。</span><span class="sxs-lookup"><span data-stu-id="7c10e-108">For more information, see [Get the Surface Duo SDK][DuoSdkdocs].</span></span>

## <span data-ttu-id="7c10e-109">步骤1：导航到 edge://inspect</span><span class="sxs-lookup"><span data-stu-id="7c10e-109">Step 1: Navigate to edge://inspect</span></span>

<span data-ttu-id="7c10e-110">打开 [Microsoft Edge][DesktopEdge]的桌面实例，然后导航到 `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="7c10e-110">Open a desktop instance of [Microsoft Edge][DesktopEdge], and navigate to `edge://inspect`.</span></span>

> ##### <span data-ttu-id="7c10e-111">图 1</span><span class="sxs-lookup"><span data-stu-id="7c10e-111">Figure 1</span></span>  
> <span data-ttu-id="7c10e-112">`edge://inspect`桌面上的 Microsoft edge 中的页面 ![ 桌面上的 microsoft edge 中的 edge://inspect 页面][ImageEdgeInspect]</span><span class="sxs-lookup"><span data-stu-id="7c10e-112">The `edge://inspect` page in Microsoft Edge on the desktop ![The edge://inspect page in Microsoft Edge on the desktop][ImageEdgeInspect]</span></span>

> [!NOTE]
> <span data-ttu-id="7c10e-113">如果 `edge://inspect` 页面不识别 [Surface 双核模拟器][DuoEmulator]，请重新启动仿真器。</span><span class="sxs-lookup"><span data-stu-id="7c10e-113">If the `edge://inspect` page does not recognize the [Surface Duo emulator][DuoEmulator], restart the emulator.</span></span>

## <span data-ttu-id="7c10e-114">步骤2：启动 Surface 双核仿真器</span><span class="sxs-lookup"><span data-stu-id="7c10e-114">Step 2: Launch the Surface Duo emulator</span></span>

<span data-ttu-id="7c10e-115">启动 [Surface 双核模拟器][DuoEmulator]。</span><span class="sxs-lookup"><span data-stu-id="7c10e-115">Launch the [Surface Duo emulator][DuoEmulator].</span></span> <span data-ttu-id="7c10e-116">请注意，仿真器将显示在仿真器上运行的2个不同的屏幕。</span><span class="sxs-lookup"><span data-stu-id="7c10e-116">Notice that the emulator displays 2 different screens running on the emulator.</span></span>

> ##### <span data-ttu-id="7c10e-117">图 2</span><span class="sxs-lookup"><span data-stu-id="7c10e-117">Figure 2</span></span>
> <span data-ttu-id="7c10e-118">Surface 双核处理器技术（Surface）仿真器 ![][ImageDuoEmulator]</span><span class="sxs-lookup"><span data-stu-id="7c10e-118">The Surface Duo emulator ![The Surface Duo emulator][ImageDuoEmulator]</span></span>  

## <span data-ttu-id="7c10e-119">步骤3：在 Surface 双核模拟器上的 Microsoft Edge 中加载 web 内容</span><span class="sxs-lookup"><span data-stu-id="7c10e-119">Step 3: Load your web content in Microsoft Edge on the Surface Duo emulator</span></span>

<span data-ttu-id="7c10e-120">在任一屏幕上，向上轻扫 [Surface 双核处理器技术][DuoEmulator] 的 "收藏夹" 托盘以显示 "应用" 抽屉。</span><span class="sxs-lookup"><span data-stu-id="7c10e-120">On either screen, swipe up on the Favorites Tray of the [Surface Duo emulator][DuoEmulator] to display the Apps Drawer.</span></span> <span data-ttu-id="7c10e-121">选择 " **边缘** " 以启动 [Microsoft Edge 应用][AndroidEdge]。</span><span class="sxs-lookup"><span data-stu-id="7c10e-121">Choose **Edge** to launch the [Microsoft Edge app][AndroidEdge].</span></span>

> ##### <span data-ttu-id="7c10e-122">图 3</span><span class="sxs-lookup"><span data-stu-id="7c10e-122">Figure 3</span></span>
> <span data-ttu-id="7c10e-123">Surface 双核模拟器上的 Microsoft Edge 应用在 ![ Surface 双核处理器技术上的 Microsoft edge 应用][ImageDuoEmulatorEdge]</span><span class="sxs-lookup"><span data-stu-id="7c10e-123">The Microsoft Edge app on the Surface Duo emulator ![The Microsoft Edge app on the Surface Duo emulator][ImageDuoEmulatorEdge]</span></span>  

<span data-ttu-id="7c10e-124">导航到要在 [Microsoft Edge 应用][AndroidEdge]中调试的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="7c10e-124">Navigate to the website or app that you want to debug in the [Microsoft Edge app][AndroidEdge].</span></span>

## <span data-ttu-id="7c10e-125">步骤4：从 Surface 双核仿真器调试 web 内容</span><span class="sxs-lookup"><span data-stu-id="7c10e-125">Step 4: Debug your web content from the Surface Duo emulator</span></span> 

<span data-ttu-id="7c10e-126">切换回 [Microsoft Edge][DesktopEdge]的桌面实例。</span><span class="sxs-lookup"><span data-stu-id="7c10e-126">Switch back to the desktop instance of [Microsoft Edge][DesktopEdge].</span></span> <span data-ttu-id="7c10e-127">`edge://inspect`页面现在显示**SurfaceDuoEmulator** ，其中列出了在[Surface 双核仿真器][DuoEmulator]上运行的打开的选项卡或[PWAs][PwaDocs] 。</span><span class="sxs-lookup"><span data-stu-id="7c10e-127">The `edge://inspect` page now shows the **SurfaceDuoEmulator** with a list of the open tabs or [PWAs][PwaDocs] that are running on the [Surface Duo emulator][DuoEmulator].</span></span>

> ##### <span data-ttu-id="7c10e-128">图 4</span><span class="sxs-lookup"><span data-stu-id="7c10e-128">Figure 4</span></span>
> <span data-ttu-id="7c10e-129">`edge://inspect`页面显示在仿真器上运行的 Microsoft edge 应用中打开的选项卡列表 ![ edge://inspect 页面显示在仿真器上运行的 microsoft edge 应用中打开的选项卡的列表][ImageEdgeInspectTargets]</span><span class="sxs-lookup"><span data-stu-id="7c10e-129">The `edge://inspect` page displays a list of the open tabs in the Microsoft Edge app running on the emulator ![The edge://inspect page displays a list of the open tabs in the Microsoft Edge app running on the emulator][ImageEdgeInspectTargets]</span></span>  

> [!NOTE]
> <span data-ttu-id="7c10e-130">如果在页面上看**SurfaceDuoEmulator**不到 SurfaceDuoEmulator `edge://inspect` ，请尝试在[Surface 双核模拟器][DuoEmulator]上的[Microsoft Edge 应用][AndroidEdge]中打开或关闭选项卡。</span><span class="sxs-lookup"><span data-stu-id="7c10e-130">If you do not see **SurfaceDuoEmulator** on the `edge://inspect` page, try opening or closing tabs in the [Microsoft Edge app][AndroidEdge] on the [Surface Duo Emulator][DuoEmulator].</span></span> <span data-ttu-id="7c10e-131">有关其他疑难解答步骤，请参阅 [Android 设备][TroubleshootingAndroid]的 "疑难解答" 部分。</span><span class="sxs-lookup"><span data-stu-id="7c10e-131">For additional troubleshooting steps, see the [troubleshooting section for Android devices][TroubleshootingAndroid].</span></span>

<span data-ttu-id="7c10e-132">从运行在模拟器上的打开的选项卡列表中，选择包含要调试的 web 内容的选项卡上的 " **检查** "。</span><span class="sxs-lookup"><span data-stu-id="7c10e-132">From the list of open tabs running on the emulator, choose **inspect** on the tab that has the web content to be debugged.</span></span> <span data-ttu-id="7c10e-133">[Microsoft Edge DevTools][DevToolsDocs]将在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="7c10e-133">The [Microsoft Edge DevTools][DevToolsDocs] will open in a new window.</span></span> <span data-ttu-id="7c10e-134">选择 " **切换说明截屏视频** ![ 切换" 说明截屏视频 ][ImageToggleScreencastIcon] 可在 DevTools 窗口中查看 [Surface 双核模拟器][DuoEmulator] 的 web 内容。</span><span class="sxs-lookup"><span data-stu-id="7c10e-134">Choose **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] to view the web content from your [Surface Duo emulator][DuoEmulator] in the DevTools window.</span></span> <span data-ttu-id="7c10e-135">现在，你可以使用 Microsoft Edge DevTools 来调试 [Surface 双核模拟器][DuoEmulator]上的 web 内容。</span><span class="sxs-lookup"><span data-stu-id="7c10e-135">You are now able to use the Microsoft Edge DevTools to debug your web content on the [Surface Duo emulator][DuoEmulator].</span></span>

> ##### <span data-ttu-id="7c10e-136">图 5</span><span class="sxs-lookup"><span data-stu-id="7c10e-136">Figure 5</span></span>
> <span data-ttu-id="7c10e-137">使用 Microsoft edge DevTools 在 Surface 双核模拟器上的 Microsoft Edge 应用中 ![ 使用 Microsoft Edge DevTools 调试必应在 Surface 双核模拟器上的 Microsoft edge 应用中调试必应][ImageDevTools]</span><span class="sxs-lookup"><span data-stu-id="7c10e-137">Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator ![Using the Microsoft Edge DevTools to debug Bing in the Microsoft Edge app on the Surface Duo emulator][ImageDevTools]</span></span>  

> [!NOTE]
> <span data-ttu-id="7c10e-138">如果你在仿真器的两个屏幕上跨越 [Microsoft Edge 应用][AndroidEdge] ，说明截屏视频将反映应用的新大小，而不是转轴。</span><span class="sxs-lookup"><span data-stu-id="7c10e-138">If you span the [Microsoft Edge app][AndroidEdge] across both screens in the emulator, the screencast will reflect the new size of the app but not the hinge.</span></span> <span data-ttu-id="7c10e-139">若要了解转轴对 web 内容布局的影响，请使用 [Surface 双核仿真器][DuoEmulator] ，而不是说明截屏视频。</span><span class="sxs-lookup"><span data-stu-id="7c10e-139">To understand how the hinge impacts the layout of your web content, use the [Surface Duo emulator][DuoEmulator] instead of the screencast.</span></span>

## <span data-ttu-id="7c10e-140">其他资源</span><span class="sxs-lookup"><span data-stu-id="7c10e-140">Additional Resources</span></span>

<span data-ttu-id="7c10e-141">Web 是新的可折叠和双屏幕设备的平台，因为你可以一次性编写 HTML、CSS 和 JavaScript，使其在单屏幕、双屏幕和可折叠的设备上更加美观。</span><span class="sxs-lookup"><span data-stu-id="7c10e-141">The web is a great platform for the new class of foldable and dual-screen devices because you can write your HTML, CSS, and JavaScript once and have it look great across single-screen, dual-screen, and foldable devices.</span></span> <span data-ttu-id="7c10e-142">有关详细信息，请参阅这些其他资源，开始为这些新设备构建 web 内容。</span><span class="sxs-lookup"><span data-stu-id="7c10e-142">For more information, see these additional resources to get started building web content for these new devices.</span></span>

- [<span data-ttu-id="7c10e-143">有关在双屏幕设备上创建应用的文档</span><span class="sxs-lookup"><span data-stu-id="7c10e-143">Documentation for creating apps on dual-screen devices</span></span>][DualScreenDocs]
- [<span data-ttu-id="7c10e-144">Microsoft Edge web 平台 explainer 用于在可折叠和双屏幕设备上构建 web 体验的新 Api</span><span class="sxs-lookup"><span data-stu-id="7c10e-144">The Microsoft Edge web platform explainer for new APIs to build web experiences on foldable and dual-screen devices</span></span>][WebPlatformExplainer]
- [<span data-ttu-id="7c10e-145">Microsoft 365 开发人员日会议录制：如何为网站和 web 应用构建双屏幕体验</span><span class="sxs-lookup"><span data-stu-id="7c10e-145">Recording of Microsoft 365 Developer Day session: How to build dual-screen experiences for websites and web apps</span></span>][DeveloperDay]

<!-- image links -->  
[ImageEdgeInspect]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page.msft.png "图1：桌面上的 Microsoft Edge 中的 edge://inspect 页面"
[ImageDuoEmulator]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator.msft.png "图2： Surface 双核仿真器"
[ImageDuoEmulatorEdge]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator-edge.msft.png "图3： Surface 双核模拟器上的 Microsoft Edge 应用"
[ImageEdgeInspectTargets]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png "图4： edge://inspect 页面显示在仿真器上运行的 Microsoft Edge 应用中打开的选项卡的列表"
[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png
[ImageDevTools]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-devtools.msft.png "图5：使用 Microsoft Edge DevTools 在 Surface 双核模拟器上的 Microsoft Edge 应用中调试 Bing"

<!-- links -->  
[RemoteDebuggingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "远程调试 Android 设备入门"
[PwaDocs]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用"
[DevToolsDocs]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"
[TroubleshootingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index#troubleshooting-devtools-is-not-detecting-the-android-device "疑难解答： DevTools 未检测到 Android 设备"

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android 应用"
[SurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "介绍 Surface 双核"
[DesktopEdge]: https://www.microsoft.com/edge/ "新的 Microsoft Edge 简介"
[DuoEmulator]: https://docs.microsoft.com/dual-screen/android/use-emulator "使用 Surface 双核仿真器"
[DuoSdk]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface 双核处理器技术 SDK 预览版本"
[DuoSdkDocs]: https://docs.microsoft.com/dual-screen/android/get-duo-sdk "获取 Surface 双核 SDK"
[DualScreenDocs]: https://docs.microsoft.com/dual-screen/ "为双屏幕设备创建应用"
[WebPlatformExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "针对折叠设备上的启发式体验的 Web 平台基元"
[DeveloperDay]: https://youtu.be/DXrZWsqXPVc "如何为网站和 web 应用构建双屏幕体验"
