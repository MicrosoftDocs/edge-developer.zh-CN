---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 实验
ms.openlocfilehash: fbdeeb08599285a9cfa6edd467282cfbabbadd74
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232377"
---
# <span data-ttu-id="462b6-104">实验功能</span><span class="sxs-lookup"><span data-stu-id="462b6-104">Experimental features</span></span>  

<span data-ttu-id="462b6-105">Microsoft Edge DevTools 提供对仍处于开发中的实验性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="462b6-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="462b6-106">您可以在发布每个 [功能之前](#providing-feedback-on-experimental-features) 进行测试并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="462b6-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="462b6-107">虽然实验功能在 Microsoft Edge 的所有频道中均可用，但您可以使用 Microsoft Edge Canary 渠道获取最新的实验功能。</span><span class="sxs-lookup"><span data-stu-id="462b6-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="462b6-108">打开实验性功能</span><span class="sxs-lookup"><span data-stu-id="462b6-108">Turn on experimental features</span></span>  

<span data-ttu-id="462b6-109">若要在 Microsoft Edge 中 (\) 或关闭\) 实验功能，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="462b6-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="462b6-110">[打开 DevTools。][DevtoolsOpenMain]</span><span class="sxs-lookup"><span data-stu-id="462b6-110">[Open DevTools][DevtoolsOpenMain].</span></span>  
    *   <span data-ttu-id="462b6-111">选择 `Control` + `Shift` + `I` \ (Windows、Linux\) `Command` + `Option` + `I` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="462b6-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="462b6-112">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="462b6-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="462b6-113">打开 ["设置"][DevToolsCustomizeSettings] 窗格。</span><span class="sxs-lookup"><span data-stu-id="462b6-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="462b6-114">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="462b6-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="462b6-115">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="462b6-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="462b6-116">在"设置"窗格的 **左侧，选择** " **实验"** 部分。</span><span class="sxs-lookup"><span data-stu-id="462b6-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="../media/experiments-devtools.msft.png":::
       <span data-ttu-id="462b6-118">DevTools 设置中的实验 **列表**</span><span class="sxs-lookup"><span data-stu-id="462b6-118">List of experiments in DevTools **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="462b6-119">在 **"实验** "页上，滚动浏览所有可用实验功能的列表，并选中要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="462b6-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="462b6-120">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="462b6-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="462b6-121">实验性功能会不断更新，并且可能会导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="462b6-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="462b6-122">若要关闭实验功能，请打开"实验 **"页并** 清除要关闭的实验功能复选框。</span><span class="sxs-lookup"><span data-stu-id="462b6-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="462b6-123">突出显示的实验功能</span><span class="sxs-lookup"><span data-stu-id="462b6-123">Highlighted experimental features</span></span>  

<span data-ttu-id="462b6-124">以下各节介绍 Microsoft Edge 中提供的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="462b6-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="462b6-125">实验功能</span><span class="sxs-lookup"><span data-stu-id="462b6-125">Experimental feature</span></span> | <span data-ttu-id="462b6-126">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="462b6-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="462b6-127">模拟：支持双屏幕模式</span><span class="sxs-lookup"><span data-stu-id="462b6-127">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="462b6-128">84 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-128">84 or later</span></span> |  
| [<span data-ttu-id="462b6-129">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="462b6-129">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="462b6-130">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-130">85 or later</span></span> |  
| [<span data-ttu-id="462b6-131">支持在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="462b6-131">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="462b6-132">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-132">85 or later</span></span> |  
| [<span data-ttu-id="462b6-133">启用 Webhint</span><span class="sxs-lookup"><span data-stu-id="462b6-133">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="462b6-134">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-134">85 or later</span></span> |  
| [<span data-ttu-id="462b6-135">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="462b6-135">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="462b6-136">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-136">85 or later</span></span> |  
| [<span data-ttu-id="462b6-137">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="462b6-137">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="462b6-138">86 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-138">86 or later</span></span> |  
| [<span data-ttu-id="462b6-139">启用键盘快捷方式编辑器</span><span class="sxs-lookup"><span data-stu-id="462b6-139">Enable keyboard shortcut editor</span></span>](#enable-keyboard-shortcut-editor) | <span data-ttu-id="462b6-140">87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-140">87 or later</span></span> |  
| [<span data-ttu-id="462b6-141">在 3D 视图中打开复合层</span><span class="sxs-lookup"><span data-stu-id="462b6-141">Turn on Composited Layers in 3D View</span></span>](#turn-on-composited-layers-in-3d-view) | <span data-ttu-id="462b6-142">87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="462b6-142">87 or later</span></span> |  

### <span data-ttu-id="462b6-143">模拟：支持双屏幕模式</span><span class="sxs-lookup"><span data-stu-id="462b6-143">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="462b6-144">提供在 Microsoft Edge 中模拟两个新的双屏幕和可折叠设备的其他功能。</span><span class="sxs-lookup"><span data-stu-id="462b6-144">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="462b6-145">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="462b6-145">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="462b6-146">三星百合</span><span class="sxs-lookup"><span data-stu-id="462b6-146">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  
    
<span data-ttu-id="462b6-147">模拟设备，并切换以下状态。</span><span class="sxs-lookup"><span data-stu-id="462b6-147">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="462b6-148">单屏或折叠状态</span><span class="sxs-lookup"><span data-stu-id="462b6-148">Single-screen or folded posture</span></span>  
*   <span data-ttu-id="462b6-149">双屏或展开状态</span><span class="sxs-lookup"><span data-stu-id="462b6-149">Dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="462b6-150">启用实验性 Web 平台[API，](#enable-experimental-apis)并使用[CSS 媒体][DualScreenDocsCssMedia]屏幕跨越功能以及[JavaScript getWindowSegments API][DualScreenDocsJSAPI]增强适用于双屏幕和可折叠设备的网站 \ (或 app\) 。</span><span class="sxs-lookup"><span data-stu-id="462b6-150">[Enable experimental Web Platform APIs](#enable-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="在 Microsoft Edge 中模拟 Surface Duo" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="462b6-152">在 Microsoft Edge 中模拟 Surface Duo</span><span class="sxs-lookup"><span data-stu-id="462b6-152">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="462b6-153">启用实验性 API</span><span class="sxs-lookup"><span data-stu-id="462b6-153">Enable experimental APIs</span></span>  

<span data-ttu-id="462b6-154">若要使用 [CSS 媒体屏幕跨越][DualScreenDocsCssMedia] 功能以及 [JavaScript getWindowSegments API，][DualScreenDocsJSAPI]请打开 `Experimental Web Platform features` Microsoft Edge 中的标志。</span><span class="sxs-lookup"><span data-stu-id="462b6-154">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="462b6-155">完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="462b6-155">Complete the following steps.</span></span>  

1.  <span data-ttu-id="462b6-156">导航到 `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="462b6-156">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="462b6-157">在**搜索标志**文本框中，输入、选择实验 Web 平台功能标志，并更改为 `Experimental Web Platform features` **"已禁用"。** \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="462b6-157">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="462b6-158">重启 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="462b6-158">Restart Microsoft Edge.</span></span>  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="启用实验性 Web 平台功能标志" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="462b6-160">启用实验性 Web 平台功能标志</span><span class="sxs-lookup"><span data-stu-id="462b6-160">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="462b6-161">如果你使用[CSS][DualScreenDocsCssMedia]媒体查询或[JavaScript Windows 段枚举 API][DualScreenDocsJSAPI]增强[Surface Duo][SurfaceDevicesDuo]的网站或应用，则还必须在[Surface Duo][SurfaceDevicesDuo]设备上的[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用中启用实验性**Web**平台功能标志。</span><span class="sxs-lookup"><span data-stu-id="462b6-161">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="462b6-162">如果在桌面[Microsoft Edge][MicrosoftEdge]中启用实验性**Web**平台功能标志，并且在 Android [Microsoft Edge][GooglePlayMicrosoftEdge]应用中禁用，则桌面 Microsoft Edge 的 Surface Duo 仿真器中的网站或应用的行为与[Surface Duo][SurfaceDevicesDuo]上的[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用不匹配。</span><span class="sxs-lookup"><span data-stu-id="462b6-162">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="462b6-163">确保标志在 Android 和桌面版 Microsoft Edge 之间匹配，以在桌面版 Microsoft Edge 中成功使用 Surface Duo [仿真器][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="462b6-163">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="462b6-164">在可折叠和双屏幕设备上进行测试</span><span class="sxs-lookup"><span data-stu-id="462b6-164">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="462b6-165">当你在 Microsoft Edge 中模拟双屏幕状态中的 [Surface Duo][SurfaceDevicesDuo] 时，两个屏幕之间的 (\) 将绘制在网站或应用上。</span><span class="sxs-lookup"><span data-stu-id="462b6-165">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="462b6-166">模拟显示与您的网站 \ (或 app\) 在 Surface Duo 上运行的 Microsoft [Edge Android][GooglePlayMicrosoftEdge] 应用中的呈现 [方式相匹配][SurfaceDevicesDuo]。</span><span class="sxs-lookup"><span data-stu-id="462b6-166">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] running on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="462b6-167">你可能需要更新网站 \ (app\) ，以更好地显示网站。</span><span class="sxs-lookup"><span data-stu-id="462b6-167">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="462b6-168">若要详细了解如何调整您的网站 \ (或 app\) 以适应变化，请导航到"如何使用[此目录"。][DualScreenIntroductionHowWorkSeam]</span><span class="sxs-lookup"><span data-stu-id="462b6-168">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam].</span></span>  

<span data-ttu-id="462b6-169">设备 [工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport] 具有其他功能，可帮助你以多种状态和方向测试网站或应用。</span><span class="sxs-lookup"><span data-stu-id="462b6-169">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="462b6-170">Choose **Rotate** \ (![ Rotate ][ImageRotateIcon] \) to rotate the viewport to landscape orientation.</span><span class="sxs-lookup"><span data-stu-id="462b6-170">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="462b6-171">将此功能与 **Span** \ (Span \) 相结合，以在单屏或折叠、双屏或展开状态 ![ ][ImageSpanIcon] 之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="462b6-171">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="462b6-172">这些功能共同支持在所有四种可能状态和方向中测试网站或应用。</span><span class="sxs-lookup"><span data-stu-id="462b6-172">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="双屏幕和可折叠设备状态和方向的矩阵" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="462b6-174">双屏和可折叠设备的状态和方向矩阵</span><span class="sxs-lookup"><span data-stu-id="462b6-174">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="462b6-175">实验 **性 Web 平台功能** \ (![ ExperimentalApis ][ImageExperimentalApisIcon] \) 图标显示实验性 **Web 平台功能标志** 的状态。</span><span class="sxs-lookup"><span data-stu-id="462b6-175">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="462b6-176">如果标志已打开，则突出显示图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-176">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="462b6-177">如果关闭标志，则不突出显示图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-177">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="462b6-178">若要打开 \ (或关闭\) ，请导航到该标志 `edge://flags` 并切换该标志。</span><span class="sxs-lookup"><span data-stu-id="462b6-178">To turn on \(or off\) the flag, navigate to `edge://flags` and toggle the flag.</span></span>  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

<span data-ttu-id="462b6-179">下面是可帮助您增强双屏幕设备的网站 \ (或 app\) 的其他资源。</span><span class="sxs-lookup"><span data-stu-id="462b6-179">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices.</span></span>  

*   <span data-ttu-id="462b6-180">有关在双屏设备上进行 Web 开发的信息，请导航到 [双屏幕 Web 体验][DualScreenWebIndex]。</span><span class="sxs-lookup"><span data-stu-id="462b6-180">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="462b6-181">安装 [Surface Duo 仿真器][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="462b6-181">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="462b6-182">它不同于 Microsoft Edge 中的仿真器，模拟运行 Android 的 Surface Duo，并且与 [Android Studio 集成][AndroidDeveloperStudio]。</span><span class="sxs-lookup"><span data-stu-id="462b6-182">It is different from the emulator in Microsoft Edge, emulates the Surface Duo running Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="462b6-183">有关详细信息，请导航到["获取 Surface Duo SDK"。][DualScreenAndroidGetDuoSdk]</span><span class="sxs-lookup"><span data-stu-id="462b6-183">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  
    
> [!NOTE]
> <span data-ttu-id="462b6-184">以下是当前已知问题的列表。</span><span class="sxs-lookup"><span data-stu-id="462b6-184">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="462b6-185">当使用 [Microsoft 远程桌面客户端][RemoteDesktopClientDocs] 连接到远程电脑并模拟 Surface [Duo][SurfaceDevicesDuo] 或 [Samsung 一][SamsungMobileGalaxyFold]起折叠时，指针可能会抖动或抖动。</span><span class="sxs-lookup"><span data-stu-id="462b6-185">When using a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="462b6-186">如果遇到问题，请 [发送反馈](#providing-feedback-on-experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="462b6-186">If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).</span></span>  

### <span data-ttu-id="462b6-187">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="462b6-187">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="462b6-188">此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS 网格布局。</span><span class="sxs-lookup"><span data-stu-id="462b6-188">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="462b6-189">若要预览最新的实验功能，请 [启用此实验](#turn-on-experimental-features) 并重新加载 DevTools。</span><span class="sxs-lookup"><span data-stu-id="462b6-189">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="462b6-190">此实验在 Microsoft Edge 版本 87 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="462b6-190">This experiment is on by default in Microsoft Edge version 87 or later.</span></span>  

#### <span data-ttu-id="462b6-191">使用"检查"工具查看悬停网格覆盖</span><span class="sxs-lookup"><span data-stu-id="462b6-191">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="462b6-192">检查 **工具** 提供了一种快速方法，通过将鼠标悬停在网站中的 CSS 网格布局上来识别并可视化这些布局。</span><span class="sxs-lookup"><span data-stu-id="462b6-192">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="462b6-193">选择\*\*\*\* ![ DevTools (左上角的"检查) 检查 \) ][ImageInspectIcon] 图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-193">Choose the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="462b6-194">然后，将鼠标悬停在要调试的网站上 Grid 元素上。</span><span class="sxs-lookup"><span data-stu-id="462b6-194">Then, hover over a Grid element on the website you are debugging.</span></span>  <span data-ttu-id="462b6-195">边框显示在网格周围，底纹指示网格间隙的位置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="462b6-195">Outlines are displayed around the grid, and shading indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="../media/grid-inspect.msft.png" alt-text="使用"检查"工具查看网格" lightbox="../media/grid-inspect.msft.png":::
   <span data-ttu-id="462b6-197">使用"检查"工具 **查看** 网格</span><span class="sxs-lookup"><span data-stu-id="462b6-197">Viewing grids with the **Inspect** tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="462b6-198">查看持久网格覆盖</span><span class="sxs-lookup"><span data-stu-id="462b6-198">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="462b6-199">在 Microsoft Edge 版本 86 或更高版本中，实验 CSS 网格功能还提供了启用持久网格覆盖的选项。</span><span class="sxs-lookup"><span data-stu-id="462b6-199">In Microsoft Edge version 86 or later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="462b6-200">持久覆盖具有多个优势。</span><span class="sxs-lookup"><span data-stu-id="462b6-200">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="462b6-201">滚动、移动鼠标并使用 DevTools 的其他功能时，永久性覆盖在页面上仍然可见。</span><span class="sxs-lookup"><span data-stu-id="462b6-201">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="462b6-202">可以同时启用多个永久性覆盖，从而允许您一次查看多个网格布局。</span><span class="sxs-lookup"><span data-stu-id="462b6-202">Multiple persistent overlays can be enabled at the same time, allowing you to review several grid layouts at once.</span></span>  
*   <span data-ttu-id="462b6-203">永久性覆盖提供了许多配置选项，例如隐藏或显示网格区域中的名称、网格间隙、跟踪大小等。</span><span class="sxs-lookup"><span data-stu-id="462b6-203">Persistent overlays offer many configuration options, such as hiding or showing names in the grid area, grid gaps, track sizes, and so on.</span></span>  
    
<span data-ttu-id="462b6-204">切换持久网格覆盖的两种方法。</span><span class="sxs-lookup"><span data-stu-id="462b6-204">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="462b6-205">选择 **"元素"** 工具的 DOM 树中显示的任何 Grid 元素旁边的" **网格"椭圆** 图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-205">Choose the **Grid** oval icon next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="../media/grid-adorner.msft.png" alt-text="元素工具中的网格椭圆图标" lightbox="../media/grid-adorner.msft.png":::
       <span data-ttu-id="462b6-207">元素工具中的 **网格** 椭圆图标</span><span class="sxs-lookup"><span data-stu-id="462b6-207">Grid oval icon in **Elements** tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="462b6-208">打开位于 **"元素** "工具中的新布局面板，并选中要突出显示的每个 Grid 元素旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="462b6-208">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="../media/grid-layout-zoom.msft.png" alt-text="DevTools 中的布局面板" lightbox="../media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="462b6-210">\*\*\*\* DevTools 中的布局面板</span><span class="sxs-lookup"><span data-stu-id="462b6-210">**Layout** panel in DevTools</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="462b6-211">配置永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="462b6-211">Configuring persistent overlays</span></span>  

<span data-ttu-id="462b6-212">在 Microsoft Edge 版本 86\*\*\*\* 或更高版本中，新的布局面板位于 **"** 元素"工具\*\*\*\* 中的"样式"和"**计算"选项卡**旁边。</span><span class="sxs-lookup"><span data-stu-id="462b6-212">In Microsoft Edge version 86 or later, the new **Layout** panel is located in the **Elements** tool alongside the **Styles** and **Computed** tabs.</span></span>  <span data-ttu-id="462b6-213">布局 **面板** 显示持久覆盖的配置选项。</span><span class="sxs-lookup"><span data-stu-id="462b6-213">The **Layout** panel surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="../media/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../media/experiments-grid.msft.png":::
   <span data-ttu-id="462b6-215">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="462b6-215">CSS grid debugging feature</span></span>  
:::image-end:::  

### <span data-ttu-id="462b6-216">支持在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="462b6-216">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="462b6-217">通常，元素和网络等工具\*\*\*\* 只能在位于\*\*\*\* DevTools 顶部的主面板中打开。</span><span class="sxs-lookup"><span data-stu-id="462b6-217">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="462b6-218">工具（**如 3D 视图**和问题）通常仅在位于\*\*\*\* DevTools 底部的"箱"面板中打开。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="462b6-218">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="462b6-219">选择实验后，您可以在顶部和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="462b6-219">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="462b6-220">若要移动工具，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击\) ，然后选择"移动到顶部"或"\*\*\*\* 移动到**底部"。**</span><span class="sxs-lookup"><span data-stu-id="462b6-220">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="462b6-221">此实验允许你自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="462b6-221">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="462b6-222">若要显示或隐藏 **"箱"** 面板，请选择 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="462b6-222">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="../media/experiments-move-panels.msft.png" alt-text="在面板之间移动选项卡" lightbox="../media/experiments-move-panels.msft.png":::
   <span data-ttu-id="462b6-224">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="462b6-224">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="462b6-225">启用 Webhint</span><span class="sxs-lookup"><span data-stu-id="462b6-225">Enable webhint</span></span>  

<span data-ttu-id="462b6-226">[webhint][WebhintMain] 是一个开源工具，可为网站和本地网页提供实时反馈。</span><span class="sxs-lookup"><span data-stu-id="462b6-226">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="462b6-227">Webhint 提供 [的反馈类型][WebhintMain]。</span><span class="sxs-lookup"><span data-stu-id="462b6-227">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="462b6-228">辅助功能</span><span class="sxs-lookup"><span data-stu-id="462b6-228">accessibility</span></span>  
*   <span data-ttu-id="462b6-229">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="462b6-229">cross-browser compatibility</span></span>  
*   <span data-ttu-id="462b6-230">安全性</span><span class="sxs-lookup"><span data-stu-id="462b6-230">security</span></span>  
*   <span data-ttu-id="462b6-231">性能</span><span class="sxs-lookup"><span data-stu-id="462b6-231">performance</span></span>  
*   <span data-ttu-id="462b6-232">渐进式 Web (PBA) </span><span class="sxs-lookup"><span data-stu-id="462b6-232">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="462b6-233">其他常见的 Web 开发问题</span><span class="sxs-lookup"><span data-stu-id="462b6-233">other common web development issues</span></span>  
    
<span data-ttu-id="462b6-234">[Webhint 实验][WebhintMain]在"问题"面板中显示[Webhint][DevtoolsIssues]反馈。</span><span class="sxs-lookup"><span data-stu-id="462b6-234">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="462b6-235">选择一个问题，在网站上显示解决方案文档和受影响资源列表。</span><span class="sxs-lookup"><span data-stu-id="462b6-235">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="462b6-236">选择资源链接以在 DevTools\*\*\*\*\*\*中**打开**相关的"\*\* 网络、源"或"元素"窗格。</span><span class="sxs-lookup"><span data-stu-id="462b6-236">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../media/experiments-webhint.msft.png":::
   <span data-ttu-id="462b6-238">问题面板中的 webhint**反馈**</span><span class="sxs-lookup"><span data-stu-id="462b6-238">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="462b6-239">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="462b6-239">Enable Network Console</span></span>  

<span data-ttu-id="462b6-240">**网络控制台** 是通过 HTTP 进行综合网络请求的实验的工作主题。</span><span class="sxs-lookup"><span data-stu-id="462b6-240">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="462b6-241">可以使用网络 **控制台** 实验发送 Web API 请求。</span><span class="sxs-lookup"><span data-stu-id="462b6-241">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="462b6-242">启用实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="462b6-242">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="462b6-243">若要使用 **网络控制台**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="462b6-243">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="462b6-244">打开 **"网络"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="462b6-244">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="462b6-245">查找要更改和重新发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="462b6-245">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="462b6-246">打开上下文菜单 \ (右键单击\) ，然后选择"编辑**和重播"。**</span><span class="sxs-lookup"><span data-stu-id="462b6-246">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="462b6-247">当网络 **控制台打开** 时，编辑网络请求信息。</span><span class="sxs-lookup"><span data-stu-id="462b6-247">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="462b6-248">选择 **"发送"。**</span><span class="sxs-lookup"><span data-stu-id="462b6-248">Choose **Send**.</span></span>  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="控制台箱中的网络控制台" lightbox="../media/network-network-console.msft.png":::
   <span data-ttu-id="462b6-250">**控制台箱\*\*\*\*中的网络控制台**</span><span class="sxs-lookup"><span data-stu-id="462b6-250">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="462b6-251">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="462b6-251">Source Order Viewer</span></span>  

<span data-ttu-id="462b6-252">**源顺序查看器** 是显示页面源中元素顺序的实验。</span><span class="sxs-lookup"><span data-stu-id="462b6-252">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="462b6-253">屏幕显示顺序可能与源的顺序不同，这会使屏幕阅读器和键盘用户混淆。</span><span class="sxs-lookup"><span data-stu-id="462b6-253">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="462b6-254">使用 **源订单查看器** 实验可查找屏幕显示顺序和源顺序之间的差异。</span><span class="sxs-lookup"><span data-stu-id="462b6-254">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="462b6-255">启用实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="462b6-255">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="462b6-256">若要使用 **源订单查看器**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="462b6-256">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="462b6-257">打开 **"元素"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="462b6-257">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="462b6-258">打开 **"下角** "\ (面板中的"辅助功能) 窗格。</span><span class="sxs-lookup"><span data-stu-id="462b6-258">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="462b6-259">在" **源订单查看器"** 部分下，选中" **显示源订单"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="462b6-259">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="462b6-260">突出显示任何 HTML 元素以显示页面源中顺序的覆盖。</span><span class="sxs-lookup"><span data-stu-id="462b6-260">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="辅助功能窗格中的源订单查看器" lightbox="../media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="462b6-262">**辅助功能窗格中**的**源订单查看器**</span><span class="sxs-lookup"><span data-stu-id="462b6-262">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <span data-ttu-id="462b6-263">启用键盘快捷方式编辑器</span><span class="sxs-lookup"><span data-stu-id="462b6-263">Enable keyboard shortcut editor</span></span>

<span data-ttu-id="462b6-264">打开 **"启用键盘** 快捷方式编辑器"实验后，你现在可以自定义 DevTools 中任何动作的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="462b6-264">With the **Enable keyboard shortcut editor** experiment turned on, you are now able to customize keyboard shortcuts for any action in the DevTools.</span></span>  <span data-ttu-id="462b6-265">若要为特定操作自定义键盘快捷方式，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="462b6-265">To customize the keyboard shortcut for a specific action, complete the following steps.</span></span>  

1.  <span data-ttu-id="462b6-266">[打开 DevTools。][DevtoolsOpenMain]</span><span class="sxs-lookup"><span data-stu-id="462b6-266">[Open DevTools][DevtoolsOpenMain].</span></span>  
1.  <span data-ttu-id="462b6-267">打开["设置"。][DevToolsCustomizeSettings]</span><span class="sxs-lookup"><span data-stu-id="462b6-267">Open [Settings][DevToolsCustomizeSettings].</span></span>
    *   <span data-ttu-id="462b6-268">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="462b6-268">Select `Shift`+`?`.</span></span>  
1.  <span data-ttu-id="462b6-269">导航到 **"快捷方式"** 页。</span><span class="sxs-lookup"><span data-stu-id="462b6-269">Navigate to the **Shortcuts** page.</span></span>  
1.  <span data-ttu-id="462b6-270">选择要自定义的操作。</span><span class="sxs-lookup"><span data-stu-id="462b6-270">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="462b6-271">选择 **编辑** \ (![ EditKeyboardShortcut ][ImageEditKeyboardShortcutIcon] \) 图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-271">Choose the **Edit** \(![EditKeyboardShortcut][ImageEditKeyboardShortcutIcon]\) icon.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="从"设置"中的"快捷方式"页选择要自定义的操作" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       <span data-ttu-id="462b6-273">从"设置"中的"快捷方式 **"** 页选择要自定义 [的操作][DevToolsCustomizeSettings]</span><span class="sxs-lookup"><span data-stu-id="462b6-273">Choose the action to customize from the **Shortcuts** page in [Settings][DevToolsCustomizeSettings]</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="462b6-274">在键盘上，选择要绑定到该操作的键。</span><span class="sxs-lookup"><span data-stu-id="462b6-274">On the keyboard, select the keys you want to bind to the action.</span></span>
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="选择要分配给该操作的键" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="462b6-276">选择要分配给该操作的键</span><span class="sxs-lookup"><span data-stu-id="462b6-276">Select the keys you want to assign to the action</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="462b6-277">若要保存新的键盘快捷方式，请选择选中标记 \ (</span><span class="sxs-lookup"><span data-stu-id="462b6-277">To save your new keyboard shortcut, choose the checkmark \(</span></span>![CheckmarkKeyboardShortcut][ImageCheckmarkKeyboardShortcutIcon]<span data-ttu-id="462b6-279">\) 图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-279">\) icon.</span></span>
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="选择选中标记图标以保存新的键盘快捷方式" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="462b6-281">选择选中标记图标以保存新的键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="462b6-281">Choose the checkmark icon to save your new keyboard shortcut</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="462b6-282">选择新的键盘快捷方式以在 DevTools 中触发该操作。</span><span class="sxs-lookup"><span data-stu-id="462b6-282">Select your new keyboard shortcut to trigger the action in the DevTools.</span></span>  
    
<span data-ttu-id="462b6-283">在 **"快捷方式"** 页上，自定义键盘快捷方式 **\ (** ![ CustomKeyboardShortcut ][ImageCustomKeyboardShortcutIcon] \) 图标显示已自定义的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="462b6-283">On the **Shortcuts** page, the **Custom Keyboard Shortcut** \(![CustomKeyboardShortcut][ImageCustomKeyboardShortcutIcon]\) icon displays keyboard shortcuts that you have customized.</span></span>  <span data-ttu-id="462b6-284">若要重置所有快捷方式，请选择"**还原默认快捷方式"。**</span><span class="sxs-lookup"><span data-stu-id="462b6-284">To reset all shortcuts, choose **Restore default shortcuts**.</span></span>  

<span data-ttu-id="462b6-285">编辑操作键盘快捷方式时，若要放弃所做的更改，请选择 X \ (![ XKeyboardShortcut ][ImageXKeyboardShortcutIcon] \) 图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-285">When you are editing the keyboard shortcuts for an action, to discard your changes, choose the X \(![XKeyboardShortcut][ImageXKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="462b6-286">若要删除特定操作快捷方式，请选择"删除"快捷方式 **\ (** ![ DeleteKeyboardShortcut ][ImageDeleteKeyboardShortcutIcon] \) 图标。</span><span class="sxs-lookup"><span data-stu-id="462b6-286">To remove shortcuts for a specific action, choose the **Delete shortcut** \(![DeleteKeyboardShortcut][ImageDeleteKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="462b6-287">若要为操作添加多个快捷方式，请选择"**添加快捷方式"。**</span><span class="sxs-lookup"><span data-stu-id="462b6-287">To add multiple shortcuts for an action, choose **Add a shortcut**.</span></span>

> [!NOTE]
> <span data-ttu-id="462b6-288">如果键盘快捷方式当前已分配给另一个操作，则不能将其保存以用于新操作。</span><span class="sxs-lookup"><span data-stu-id="462b6-288">If a keyboard shortcut is currently assigned to another action, you are not able to save it for a new action.</span></span>  <span data-ttu-id="462b6-289">必须先删除上一个操作键盘快捷方式，然后将其添加到新操作。</span><span class="sxs-lookup"><span data-stu-id="462b6-289">You must first delete the keyboard shortcut for the previous action and then add it to the new action.</span></span>  

<!--Available in Microsoft Edge version 87 and later.  -->

### <span data-ttu-id="462b6-290">在 3D 视图中打开复合层</span><span class="sxs-lookup"><span data-stu-id="462b6-290">Turn on Composited Layers in 3D View</span></span>

<span data-ttu-id="462b6-291">现在，您可以可视化 Z 索引和文档对象模型 \ (DOM\) 。</span><span class="sxs-lookup"><span data-stu-id="462b6-291">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="462b6-292">此功能可帮助您在不经常切换上下文的情况下进行调试。</span><span class="sxs-lookup"><span data-stu-id="462b6-292">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="462b6-293">您确定减少上下文切换是一个主要的难点。</span><span class="sxs-lookup"><span data-stu-id="462b6-293">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="462b6-294">您编写的代码对 Web 应用有何影响并不总是很明显。</span><span class="sxs-lookup"><span data-stu-id="462b6-294">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="462b6-295">为获得全面的视觉调试体验， 已将3D 视图和复合层组合到一起。</span><span class="sxs-lookup"><span data-stu-id="462b6-295">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  <span data-ttu-id="462b6-296">启用实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="462b6-296">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="462b6-297">若要使用 **复合层**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="462b6-297">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="462b6-298">在箱中，选择 **3D 视图** 工具。</span><span class="sxs-lookup"><span data-stu-id="462b6-298">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="462b6-299">打开 **"复合层"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="462b6-299">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="462b6-300">将显示应用的所有绘制图层。</span><span class="sxs-lookup"><span data-stu-id="462b6-300">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="462b6-301">使用你自己的 Web 应用试用此功能。</span><span class="sxs-lookup"><span data-stu-id="462b6-301">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="462b6-303">**复合层** 窗格</span><span class="sxs-lookup"><span data-stu-id="462b6-303">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

## <span data-ttu-id="462b6-304">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="462b6-304">Previous experimental features</span></span>  

*   <span data-ttu-id="462b6-305">[3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本 83 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="462b6-305">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="462b6-306">[自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在可用，在 Microsoft Edge 版本 86 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="462b6-306">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  

## <span data-ttu-id="462b6-307">提供有关实验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="462b6-307">Providing feedback on experimental features</span></span>  

<span data-ttu-id="462b6-308">提供有关 Microsoft Edge DevTools 实验或与 DevTools 相关的任何其他内容的反馈。</span><span class="sxs-lookup"><span data-stu-id="462b6-308">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="462b6-309">使用 DevTools 中的 **"发送反馈** "图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="462b6-309">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="462b6-310">向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文</span><span class="sxs-lookup"><span data-stu-id="462b6-310">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="462b6-312">Microsoft Edge DevTools 中的“**发送反馈**”图标</span><span class="sxs-lookup"><span data-stu-id="462b6-312">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageCheckmarkKeyboardShortcutIcon]: ../media/checkmark-keyboard-shortcut-icon.msft.png  
[ImageCustomKeyboardShortcutIcon]: ../media/custom-keyboard-shortcut-icon.msft.png  
[ImageDeleteKeyboardShortcutIcon]: ../media/delete-keyboard-shortcut-icon.msft.png  
[ImageEditKeyboardShortcutIcon]: ../media/edit-keyboard-shortcut-icon.msft.png  
[ImageExperimentalApisIcon]: ../media/experimental-apis-dark-icon.msft.png  
[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ../media/span-dark-icon.msft.png  
[ImageXKeyboardShortcutIcon]: ../media/discard-changes-keyboard-shortcut-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D 视图 | Microsoft Docs"  
[DevToolsCustomizeSettings]: ../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools |Microsoft Edge"  
[DevtoolsIssues]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏幕 Web 体验|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏幕设备简介|Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "用于双屏检测方法的 CSS 媒体屏幕|Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "百年百|Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
