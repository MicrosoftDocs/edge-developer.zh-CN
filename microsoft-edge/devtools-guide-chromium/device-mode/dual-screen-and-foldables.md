---
description: 使用 Microsoft Edge 中的虚拟设备增强双屏幕和可折叠设备的网站。
title: 在 DevTools 中模拟双屏幕和可折叠Microsoft Edge设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 模拟， 设备， 模拟， 移动， 双屏， 可折叠， Surface Duo， Samsung 用户折叠
ms.openlocfilehash: c3bd3296afa86d9d2c90c164bc3e9088bc043c3c
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564341"
---
# <a name="emulate-dual-screen-and-foldable-devices-in-microsoft-edge-devtools"></a><span data-ttu-id="450d2-104">在 DevTools 中模拟双屏幕和可折叠Microsoft Edge设备</span><span class="sxs-lookup"><span data-stu-id="450d2-104">Emulate dual-screen and foldable devices in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="450d2-105">在 Microsoft Edge版本 89 或更高版本中，你可以模拟以下双屏幕和可折叠设备。</span><span class="sxs-lookup"><span data-stu-id="450d2-105">In Microsoft Edge version 89 or later, you may emulate the following dual-screen and foldable devices.</span></span>  

*   [<span data-ttu-id="450d2-106">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="450d2-106">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="450d2-107">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="450d2-107">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  
    
<span data-ttu-id="450d2-108">模拟设备，并切换以下状态。</span><span class="sxs-lookup"><span data-stu-id="450d2-108">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="450d2-109">单屏或折叠状态</span><span class="sxs-lookup"><span data-stu-id="450d2-109">Single-screen or folded posture</span></span>  
*   <span data-ttu-id="450d2-110">双屏或展开状态</span><span class="sxs-lookup"><span data-stu-id="450d2-110">Dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="450d2-111">打开实验性[Web 平台 API，](#turn-on-experimental-apis)并使用[CSS 媒体][DualScreenDocsCssMedia]屏幕跨区功能以及[JavaScript getWindowSegments API][DualScreenDocsJSAPI]为双屏幕和可折叠设备增强您的网站 \ (或 app\) 。</span><span class="sxs-lookup"><span data-stu-id="450d2-111">[Turn on experimental Web Platform APIs](#turn-on-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="模拟 Surface Duo Microsoft Edge" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="450d2-113">模拟 Surface Duo Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="450d2-113">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

## <a name="turn-on-experimental-apis"></a><span data-ttu-id="450d2-114">打开实验性 API</span><span class="sxs-lookup"><span data-stu-id="450d2-114">Turn on experimental APIs</span></span>  

<span data-ttu-id="450d2-115">若要使用[CSS 媒体屏幕跨区][DualScreenDocsCssMedia]功能以及[JavaScript getWindowSegments API，][DualScreenDocsJSAPI]请打开 `Experimental Web Platform features` Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="450d2-115">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="450d2-116">完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="450d2-116">Complete the following steps.</span></span>  

1.  <span data-ttu-id="450d2-117">导航到 `edge://flags`。</span><span class="sxs-lookup"><span data-stu-id="450d2-117">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="450d2-118">在"**搜索标志**"文本框中，输入 `Experimental Web Platform features` ，选择"**实验性 Web 平台功能**"标志，将"**已禁用"更改为\*\*\*\*"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="450d2-118">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="450d2-119">重启 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="450d2-119">Restart Microsoft Edge.</span></span>  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="打开"实验性 Web 平台功能"标志" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="450d2-121">打开" **实验性 Web 平台功能"** 标志</span><span class="sxs-lookup"><span data-stu-id="450d2-121">Turn on the **Experimental Web Platform features** flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="450d2-122">如果使用[CSS][DualScreenDocsCssMedia]媒体查询或[JavaScript Windows Segment][DualScreenDocsJSAPI]枚举 API 增强 Surface Duo 的网站或应用，还必须在 Surface [Duo][SurfaceDevicesDuo]设备上的 Android [Microsoft Edge][GooglePlayMicrosoftEdge]应用中打开实验**性 Web**平台功能[][SurfaceDevicesDuo]标志。</span><span class="sxs-lookup"><span data-stu-id="450d2-122">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also turn on the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="450d2-123">如果在桌面[Microsoft Edge][MicrosoftEdge]中打开实验性**Web**平台功能标志，并且在[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用中关闭，则桌面 Microsoft Edge 的 Surface Duo 模拟器中的网站或应用的行为与[Surface Duo][SurfaceDevicesDuo]上的[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用不匹配。</span><span class="sxs-lookup"><span data-stu-id="450d2-123">If the **Experimental Web Platform features** flag is turned on in [desktop Microsoft Edge][MicrosoftEdge] and turned off in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="450d2-124">确保 Android 和桌面设备之间的标志Microsoft Edge，以在桌面设备上成功使用 Surface Duo [Microsoft Edge。][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="450d2-124">Ensure that the flags match across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

## <a name="test-on-foldable-and-dual-screen-devices"></a><span data-ttu-id="450d2-125">在可折叠和双屏设备上测试</span><span class="sxs-lookup"><span data-stu-id="450d2-125">Test on foldable and dual-screen devices</span></span>  

<span data-ttu-id="450d2-126">当你在 Microsoft Edge 中模拟双屏状态[中的 Surface Duo][SurfaceDevicesDuo]时，两个屏幕之间的空间\ (\) 将绘制在你的网站或应用上。</span><span class="sxs-lookup"><span data-stu-id="450d2-126">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="450d2-127">模拟显示与你的网站 \ (或 app\) 在 Surface Duo 上运行的[Microsoft Edge Android][GooglePlayMicrosoftEdge]应用中[的呈现方式相匹配][SurfaceDevicesDuo]。</span><span class="sxs-lookup"><span data-stu-id="450d2-127">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] while running on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="450d2-128">你可能必须更新你的网站 \ (或 app\) ，以更好地显示整个网站。</span><span class="sxs-lookup"><span data-stu-id="450d2-128">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="450d2-129">若要详细了解如何调整你的网站 \ (或 app\) 以适应变化，请导航到如何与接您 [一起操作][DualScreenIntroductionHowWorkSeam]。</span><span class="sxs-lookup"><span data-stu-id="450d2-129">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam].</span></span>  

<span data-ttu-id="450d2-130">设备 [工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport] 具有其他功能，可帮助你以多种状态和方向测试网站或应用。</span><span class="sxs-lookup"><span data-stu-id="450d2-130">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="450d2-131">Choose **Rotate** \ (![ Rotate ](../media/rotate-dark-icon.msft.png) \) to rotate the viewport to landscape orientation.</span><span class="sxs-lookup"><span data-stu-id="450d2-131">Choose **Rotate** \(![Rotate](../media/rotate-dark-icon.msft.png)\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="450d2-132">将该功能与 **Span** \ (Span \) 结合使用，可在单屏或折叠、双屏或展开状态 ![ ](../media/span-dark-icon.msft.png) 之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="450d2-132">Combine the feature with **Span** \(![Span](../media/span-dark-icon.msft.png)\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="450d2-133">这些功能共同允许你在所有四种可能状态和方向中测试网站或应用。</span><span class="sxs-lookup"><span data-stu-id="450d2-133">Together, the features allow you to test your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="双屏幕和可折叠设备的状态和方向矩阵" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="450d2-135">双屏幕和可折叠设备的状态和方向矩阵</span><span class="sxs-lookup"><span data-stu-id="450d2-135">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="450d2-136">实验 **性 Web 平台功能** \ (![ ExperimentalApis ](../media/experimental-apis-dark-icon.msft.png) \) 图标显示"实验 **性 Web 平台功能"标志** 的状态。</span><span class="sxs-lookup"><span data-stu-id="450d2-136">The **Experimental Web Platform features** \(![ExperimentalApis](../media/experimental-apis-dark-icon.msft.png)\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="450d2-137">如果此标志已打开，则突出显示该图标。</span><span class="sxs-lookup"><span data-stu-id="450d2-137">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="450d2-138">如果关闭标志，则不突出显示图标。</span><span class="sxs-lookup"><span data-stu-id="450d2-138">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="450d2-139">若要打开 \ (或 off\) 标志，请选择图标或导航到 并 `edge://flags` 切换标志。</span><span class="sxs-lookup"><span data-stu-id="450d2-139">To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.</span></span>  

> [!NOTE]
> <span data-ttu-id="450d2-140">以下是当前已知问题的列表。</span><span class="sxs-lookup"><span data-stu-id="450d2-140">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="450d2-141">当你使用[Microsoft 远程桌面][RemoteDesktopClientDocs]客户端连接到远程电脑并模拟 Surface [Duo][SurfaceDevicesDuo]或[Samsung 用户折叠][SamsungMobileGalaxyFold]时，指针可能会抖动或抖动。</span><span class="sxs-lookup"><span data-stu-id="450d2-141">When you use a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="450d2-142">如果遇到问题，请 [发送反馈](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="450d2-142">If you run into the issue, [send feedback](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="450d2-143">其他资源</span><span class="sxs-lookup"><span data-stu-id="450d2-143">Additional Resources</span></span>  

<span data-ttu-id="450d2-144">下面是可帮助您增强双屏设备的网站 \ (或 app\) 的其他资源。</span><span class="sxs-lookup"><span data-stu-id="450d2-144">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices.</span></span>  

*   <span data-ttu-id="450d2-145">有关在双屏设备上进行 Web 开发的信息，请导航到 [双屏幕 Web 体验][DualScreenWebIndex]。</span><span class="sxs-lookup"><span data-stu-id="450d2-145">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="450d2-146">安装 [Surface Duo 仿真器][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="450d2-146">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="450d2-147">Surface Duo 仿真器不同于 Microsoft Edge 中的仿真器，运行 Android，并且与[Android Studio 集成][AndroidDeveloperStudio]。</span><span class="sxs-lookup"><span data-stu-id="450d2-147">The Surface Duo emulator is different from the emulator in Microsoft Edge, runs Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="450d2-148">有关详细信息，请导航到[获取 Surface Duo SDK][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="450d2-148">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="450d2-149">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="450d2-149">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 | Microsoft Edge"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏 Web 体验|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo 模拟器|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何处理接缝 - 双屏幕设备简介| Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 模拟器|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "用于双屏幕检测的 CSS 媒体屏幕跨越功能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript AP | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/global/galaxy/galaxy-fold "百合|三星"  
