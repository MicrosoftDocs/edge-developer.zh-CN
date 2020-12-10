---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: b2b2e591834f1c75d51ec98523e2752d67a2d354
ms.sourcegitcommit: 6571bcc0b7f1c4c9d6ead65081374bab87cd4469
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203897"
---
# <span data-ttu-id="7e635-104">实验功能</span><span class="sxs-lookup"><span data-stu-id="7e635-104">Experimental features</span></span>  

<span data-ttu-id="7e635-105">Microsoft Edge DevTools 提供对仍在开发中的实验功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7e635-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="7e635-106">你可以在发布每个功能之前测试和 [提供反馈](#providing-feedback-on-experimental-features) 。</span><span class="sxs-lookup"><span data-stu-id="7e635-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="7e635-107">尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。</span><span class="sxs-lookup"><span data-stu-id="7e635-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="7e635-108">启用实验功能</span><span class="sxs-lookup"><span data-stu-id="7e635-108">Turn on experimental features</span></span>  

<span data-ttu-id="7e635-109">若要在 Microsoft Edge 中打开 " (" 或 "关闭" ) 实验功能，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7e635-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="7e635-110">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="7e635-110">[Open DevTools][DevtoolsOpen].</span></span>  
    *   <span data-ttu-id="7e635-111">选择 `Control` + `Shift` + `I` \ (Windows、Linux \ ) 或 `Command` + `Option` + `I` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="7e635-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="7e635-112">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="7e635-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="7e635-113">打开 " [设置][DevToolsCustomizeSettings] " 窗格。</span><span class="sxs-lookup"><span data-stu-id="7e635-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="7e635-114">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="7e635-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="7e635-115">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="7e635-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="7e635-116">在 " **设置** " 窗格的左侧，选择 " **实验** " 部分。</span><span class="sxs-lookup"><span data-stu-id="7e635-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.msft.png":::
       <span data-ttu-id="7e635-118">DevTools**设置**中的实验列表</span><span class="sxs-lookup"><span data-stu-id="7e635-118">List of experiments in DevTools **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="7e635-119">在 " **实验** " 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="7e635-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="7e635-120">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="7e635-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="7e635-121">实验性功能将不断更新，并可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="7e635-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="7e635-122">若要关闭实验功能，请打开 " **试验** " 页面，然后清除要关闭的实验功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="7e635-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="7e635-123">突出显示实验功能</span><span class="sxs-lookup"><span data-stu-id="7e635-123">Highlighted experimental features</span></span>  

<span data-ttu-id="7e635-124">以下部分介绍 Microsoft Edge 中可用的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="7e635-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="7e635-125">实验性功能</span><span class="sxs-lookup"><span data-stu-id="7e635-125">Experimental feature</span></span> | <span data-ttu-id="7e635-126">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="7e635-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="7e635-127">仿真：支持双重屏幕模式</span><span class="sxs-lookup"><span data-stu-id="7e635-127">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="7e635-128">84或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-128">84 or later</span></span> |  
| [<span data-ttu-id="7e635-129">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="7e635-129">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="7e635-130">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-130">85 or later</span></span> |  
| [<span data-ttu-id="7e635-131">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="7e635-131">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="7e635-132">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-132">85 or later</span></span> |  
| [<span data-ttu-id="7e635-133">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="7e635-133">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="7e635-134">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-134">85 or later</span></span> |  
| [<span data-ttu-id="7e635-135">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="7e635-135">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="7e635-136">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-136">85 or later</span></span> |  
| [<span data-ttu-id="7e635-137">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="7e635-137">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="7e635-138">86或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-138">86 or later</span></span> |  
| [<span data-ttu-id="7e635-139">启用键盘快捷方式编辑器</span><span class="sxs-lookup"><span data-stu-id="7e635-139">Enable keyboard shortcut editor</span></span>](#enable-keyboard-shortcut-editor) | <span data-ttu-id="7e635-140">87或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-140">87 or later</span></span> |  
| [<span data-ttu-id="7e635-141">在3D 视图中打开复合图层</span><span class="sxs-lookup"><span data-stu-id="7e635-141">Turn on Composited Layers in 3D View</span></span>](#turn-on-composited-layers-in-3d-view) | <span data-ttu-id="7e635-142">87或更高版本</span><span class="sxs-lookup"><span data-stu-id="7e635-142">87 or later</span></span> |  

### <span data-ttu-id="7e635-143">仿真：支持双重屏幕模式</span><span class="sxs-lookup"><span data-stu-id="7e635-143">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="7e635-144">提供用于模拟 Microsoft Edge 中的两个新的双屏幕和可折叠设备的附加功能。</span><span class="sxs-lookup"><span data-stu-id="7e635-144">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="7e635-145">Surface 双核</span><span class="sxs-lookup"><span data-stu-id="7e635-145">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="7e635-146">Samsung Galaxy 折页</span><span class="sxs-lookup"><span data-stu-id="7e635-146">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  
    
<span data-ttu-id="7e635-147">模拟设备并在以下姿势之间切换。</span><span class="sxs-lookup"><span data-stu-id="7e635-147">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="7e635-148">单屏幕或折叠的状况</span><span class="sxs-lookup"><span data-stu-id="7e635-148">single-screen or folded posture</span></span>  
*   <span data-ttu-id="7e635-149">双屏幕或展开的状况</span><span class="sxs-lookup"><span data-stu-id="7e635-149">dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="7e635-150">[启用实验性 Web 平台 api](#enable-experimental-apis) 并使用 [CSS 媒体屏幕生成功能][DualScreenDocsCssMedia] 和 [JavaScript getWindowSegments API][DualScreenDocsJSAPI] 来增强您的网站 \ (或适用于双屏幕和可折叠设备的应用 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="7e635-150">[Enable experimental Web Platform APIs](#enable-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="./media/experiments-surface-duo-emulation.msft.png" alt-text="在 Microsoft Edge 中模拟 Surface 双核" lightbox="./media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="7e635-152">在 Microsoft Edge 中模拟 Surface 双核</span><span class="sxs-lookup"><span data-stu-id="7e635-152">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="7e635-153">启用实验性 Api</span><span class="sxs-lookup"><span data-stu-id="7e635-153">Enable experimental APIs</span></span>  

<span data-ttu-id="7e635-154">若要使用 [CSS 媒体屏幕生成功能][DualScreenDocsCssMedia] 和 [JavaScript getWindowSegments API][DualScreenDocsJSAPI]，请打开 `Experimental Web Platform features` Microsoft Edge 中的标志。</span><span class="sxs-lookup"><span data-stu-id="7e635-154">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="7e635-155">完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7e635-155">Complete the following steps.</span></span>  

1.  <span data-ttu-id="7e635-156">导航到 `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="7e635-156">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="7e635-157">在 " **搜索标志** " 文本框中，输入 `Experimental Web Platform features` ，选择实验性的 **Web 平台功能** 标志，将 " **已禁用** " 更改为 " **已启用**"。</span><span class="sxs-lookup"><span data-stu-id="7e635-157">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="7e635-158">重启 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="7e635-158">Restart Microsoft Edge.</span></span>  
    
:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="启用实验性 Web 平台功能标志" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="7e635-160">启用实验性 Web 平台功能标志</span><span class="sxs-lookup"><span data-stu-id="7e635-160">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="7e635-161">如果你使用[CSS 媒体查询][DualScreenDocsCssMedia]或[JavaScript WINDOWS Segment 枚举 API][DualScreenDocsJSAPI]来增强你的网站或适用于[surface 双核][SurfaceDevicesDuo]的应用，你还必须在[Surface 双核][SurfaceDevicesDuo]设备上启用[Android Microsoft Edge 应用][GooglePlayMicrosoftEdge]中的**实验性 Web 平台功能**标志。</span><span class="sxs-lookup"><span data-stu-id="7e635-161">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="7e635-162">如果在[桌面 Microsoft edge][MicrosoftEdge]中启用了实验性的**Web 平台功能**标志，并且在[Android microsoft edge 应用][GooglePlayMicrosoftEdge]中禁用了该标志，则桌面 microsoft edge 中的 Surface 双核模拟器中的网站或应用的行为与[Surface 双核][SurfaceDevicesDuo]上的[Android Microsoft edge 应用][GooglePlayMicrosoftEdge]不匹配。</span><span class="sxs-lookup"><span data-stu-id="7e635-162">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="7e635-163">确保标志在 Android 和桌面 Microsoft Edge 中匹配，以便在 [桌面 Microsoft edge][MicrosoftEdge]中成功使用 Surface 双核模拟器。</span><span class="sxs-lookup"><span data-stu-id="7e635-163">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="7e635-164">在折叠和双屏幕设备上进行测试</span><span class="sxs-lookup"><span data-stu-id="7e635-164">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="7e635-165">当您在 Microsoft Edge 的双屏幕状态下模拟 [Surface 双核][SurfaceDevicesDuo] 时，接缝 \ (在您的网站或应用上绘制的两个屏幕 ) 之间的空间。</span><span class="sxs-lookup"><span data-stu-id="7e635-165">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="7e635-166">仿真显示与在[Surface 双核][SurfaceDevicesDuo]上运行的[Microsoft Edge Android 应用][GooglePlayMicrosoftEdge]中呈现的你的网站 \ (或应用 \ ) 的方式相匹配。</span><span class="sxs-lookup"><span data-stu-id="7e635-166">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] running on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="7e635-167">您可能需要更新您的网站 \ (或应用 \ ) ，以便更好地沿接缝显示。</span><span class="sxs-lookup"><span data-stu-id="7e635-167">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="7e635-168">有关将您的网站 \ (或 app \ ) 调整到接缝的详细信息，请导航到 " [如何处理接缝][DualScreenIntroductionHowWorkSeam]"。</span><span class="sxs-lookup"><span data-stu-id="7e635-168">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam].</span></span>  

<span data-ttu-id="7e635-169">[设备工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport]具有其他功能，可帮助你在多个姿势和方向中测试你的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="7e635-169">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="7e635-170">选择 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "，将视区旋转为横向方向。</span><span class="sxs-lookup"><span data-stu-id="7e635-170">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="7e635-171">将该功能与 **span** \ (![ span ][ImageSpanIcon] \ ) 组合在单个屏幕或折叠的姿势或已展开的屏幕或已展开的之间切换。</span><span class="sxs-lookup"><span data-stu-id="7e635-171">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="7e635-172">同时，这些功能支持在所有四种可能的姿势和方向中测试你的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="7e635-172">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="双屏幕和折叠设备的姿势和方向的矩阵" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="7e635-174">双屏幕和折叠设备的姿势和方向的矩阵</span><span class="sxs-lookup"><span data-stu-id="7e635-174">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="7e635-175"> (ExperimentalApis \ ) 图标中的 **实验 Web 平台功能** \ " ![ ][ImageExperimentalApisIcon] 显示实验性 **web 平台功能** 标志的状态。</span><span class="sxs-lookup"><span data-stu-id="7e635-175">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="7e635-176">如果标志处于打开状态，则会突出显示该图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-176">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="7e635-177">如果该标志已关闭，则不会突出显示该图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-177">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="7e635-178">若要打开 " (" 或 "关闭" ) 标志，请导航到 `edge://flags` "标志" 并切换。</span><span class="sxs-lookup"><span data-stu-id="7e635-178">To turn on \(or off\) the flag, navigate to `edge://flags` and toggle the flag.</span></span>  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

<span data-ttu-id="7e635-179">下面是可帮助你增强网站的其他资源 (或适用于双屏幕设备的应用 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="7e635-179">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices.</span></span>  

*   <span data-ttu-id="7e635-180">有关在双屏幕设备上进行 web 开发的详细信息，请导航到 [双屏幕 web 体验][DualScreenWebIndex]。</span><span class="sxs-lookup"><span data-stu-id="7e635-180">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="7e635-181">安装 [Surface 双核模拟器][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="7e635-181">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="7e635-182">它与 Microsoft Edge 中的仿真器不同，模拟运行 Android 的 Surface 双核，并与 [Android Studio][AndroidDeveloperStudio]集成。</span><span class="sxs-lookup"><span data-stu-id="7e635-182">It is different from the emulator in Microsoft Edge, emulates the Surface Duo running Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="7e635-183">有关详细信息，请导航到 [获取 Surface 双核 SDK][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="7e635-183">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  
    
> [!NOTE]
> <span data-ttu-id="7e635-184">以下是当前已知问题的列表。</span><span class="sxs-lookup"><span data-stu-id="7e635-184">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="7e635-185">当使用 [Microsoft 远程桌面客户端][RemoteDesktopClientDocs] 连接到远程电脑并模拟 [Surface 双核][SurfaceDevicesDuo] 或 [Samsung Galaxy 折页][SamsungMobileGalaxyFold]时，指针可能会晃动或断断续续。</span><span class="sxs-lookup"><span data-stu-id="7e635-185">When using a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="7e635-186">如果遇到问题，请 [发送反馈](#providing-feedback-on-experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="7e635-186">If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).</span></span>  

### <span data-ttu-id="7e635-187">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="7e635-187">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="7e635-188">此实验功能提供了许多新的可视化效果，可帮助你调试 CSS 网格布局。</span><span class="sxs-lookup"><span data-stu-id="7e635-188">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="7e635-189">若要预览最新实验功能，请 [启用此实验](#turn-on-experimental-features) 并重新加载 DevTools。</span><span class="sxs-lookup"><span data-stu-id="7e635-189">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="7e635-190">此体验默认情况下在 Microsoft Edge 版本87或更高版本中打开。</span><span class="sxs-lookup"><span data-stu-id="7e635-190">This experiment is on by default in Microsoft Edge version 87 or later.</span></span>  

#### <span data-ttu-id="7e635-191">利用 "检查" 工具查看悬停的网格重叠</span><span class="sxs-lookup"><span data-stu-id="7e635-191">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="7e635-192">" **检查** " 工具提供了一种通过鼠标悬停在网站中来标识和可视化 CSS 网格布局的快速方法。</span><span class="sxs-lookup"><span data-stu-id="7e635-192">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="7e635-193">选择 DevTools 左上角的 " **检查** \ (![ 检查 ](./media/inspect-icon.msft.png) \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-193">Choose the **Inspect** \(![Inspect](./media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="7e635-194">然后，将鼠标悬停在正在调试的网站上的网格元素上。</span><span class="sxs-lookup"><span data-stu-id="7e635-194">Then, hover over a Grid element on the website you are debugging.</span></span>  <span data-ttu-id="7e635-195">大纲显示在网格周围，阴影指示网格间隙的位置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="7e635-195">Outlines are displayed around the grid, and shading indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="./media/grid-inspect.msft.png" alt-text="通过 "检查" 工具查看网格" lightbox="./media/grid-inspect.msft.png":::
   <span data-ttu-id="7e635-197">通过 "检查" 工具查看网格</span><span class="sxs-lookup"><span data-stu-id="7e635-197">Viewing grids with the Inspect tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="7e635-198">查看永久网格覆盖</span><span class="sxs-lookup"><span data-stu-id="7e635-198">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="7e635-199">在 Microsoft Edge 版本86或更高版本中，实验性 CSS 网格功能还提供了启用持久网格覆盖的选项。</span><span class="sxs-lookup"><span data-stu-id="7e635-199">In Microsoft Edge version 86 or later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="7e635-200">永久性覆盖提供多项好处。</span><span class="sxs-lookup"><span data-stu-id="7e635-200">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="7e635-201">滚动、移动鼠标和使用 DevTools 的其他功能时，永久叠加在页面上保持可见。</span><span class="sxs-lookup"><span data-stu-id="7e635-201">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="7e635-202">可以同时启用多个永久覆盖，从而允许同时查看多个网格布局。</span><span class="sxs-lookup"><span data-stu-id="7e635-202">Multiple persistent overlays can be enabled at the same time, allowing you to review several grid layouts at once.</span></span>  
*   <span data-ttu-id="7e635-203">永久覆盖提供许多配置选项，如在网格区域中隐藏或显示名称、网格间隙、轨道大小等。</span><span class="sxs-lookup"><span data-stu-id="7e635-203">Persistent overlays offer many configuration options, such as hiding or showing names in the grid area, grid gaps, track sizes, and so on.</span></span>  
    
<span data-ttu-id="7e635-204">切换永久网格覆盖的两种方式。</span><span class="sxs-lookup"><span data-stu-id="7e635-204">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="7e635-205">选择 "**元素**" 工具的 DOM 树中显示的任何网格元素旁边的 "**网格**" 椭圆图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-205">Choose the **Grid** oval icon next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="./media/grid-adorner.msft.png" alt-text=""元素" 工具中的 "网格椭圆" 图标" lightbox="./media/grid-adorner.msft.png":::
       <span data-ttu-id="7e635-207">" **元素** " 工具中的 "网格椭圆" 图标</span><span class="sxs-lookup"><span data-stu-id="7e635-207">Grid oval icon in **Elements** tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="7e635-208">打开位于 "元素" 工具中的新 **版式** 面板，然后选择要突出显示的每个网格元素旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="7e635-208">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="./media/grid-layout-zoom.msft.png" alt-text="DevTools 中的版式面板" lightbox="./media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="7e635-210">DevTools 中的**版式**面板</span><span class="sxs-lookup"><span data-stu-id="7e635-210">**Layout** panel in DevTools</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="7e635-211">配置永久重叠</span><span class="sxs-lookup"><span data-stu-id="7e635-211">Configuring persistent overlays</span></span>  

<span data-ttu-id="7e635-212">在 Microsoft Edge 版本86或更高版本中，新的 **版式** 面板位于 " **元素** " 工具中和 " **样式** " 和 " **计算** " 选项卡旁边。</span><span class="sxs-lookup"><span data-stu-id="7e635-212">In Microsoft Edge version 86 or later, the new **Layout** panel is located in the **Elements** tool alongside the **Styles** and **Computed** tabs.</span></span>  <span data-ttu-id="7e635-213">" **布局** " 面板图面为永久叠加的配置选项。</span><span class="sxs-lookup"><span data-stu-id="7e635-213">The **Layout** panel surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="./media/experiments-grid.msft.png":::
   <span data-ttu-id="7e635-215">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="7e635-215">CSS grid debugging feature</span></span>  
:::image-end:::  

### <span data-ttu-id="7e635-216">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="7e635-216">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="7e635-217">通常，诸如 **元素** 和 **网络** 之类的工具可能仅在位于 DevTools 顶部的主面板中打开。</span><span class="sxs-lookup"><span data-stu-id="7e635-217">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="7e635-218">通常仅在位于 DevTools 底部的**抽屉**面板中打开的**3D 视图**和**问题**等工具。</span><span class="sxs-lookup"><span data-stu-id="7e635-218">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="7e635-219">选择实验后，您可以在顶部面板和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="7e635-219">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="7e635-220">若要移动工具，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **移到页首** " 或 " **移至底部**"。</span><span class="sxs-lookup"><span data-stu-id="7e635-220">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="7e635-221">此实验允许你自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="7e635-221">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="7e635-222">若要显示或隐藏 **抽屉** 面板，请选择 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="7e635-222">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="在面板之间移动选项卡" lightbox="./media/experiments-move-panels.msft.png":::
   <span data-ttu-id="7e635-224">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="7e635-224">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="7e635-225">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="7e635-225">Enable webhint</span></span>  

<span data-ttu-id="7e635-226">[webhint][WebhintMain] 是一种开放源工具，可提供网站和本地网页的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="7e635-226">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="7e635-227">[Webhint][WebhintMain]提供的反馈类型。</span><span class="sxs-lookup"><span data-stu-id="7e635-227">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="7e635-228">辅助功能</span><span class="sxs-lookup"><span data-stu-id="7e635-228">accessibility</span></span>  
*   <span data-ttu-id="7e635-229">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="7e635-229">cross-browser compatibility</span></span>  
*   <span data-ttu-id="7e635-230">安全性</span><span class="sxs-lookup"><span data-stu-id="7e635-230">security</span></span>  
*   <span data-ttu-id="7e635-231">性能</span><span class="sxs-lookup"><span data-stu-id="7e635-231">performance</span></span>  
*   <span data-ttu-id="7e635-232"> (PWAs) 的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="7e635-232">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="7e635-233">其他常见 web 开发问题</span><span class="sxs-lookup"><span data-stu-id="7e635-233">other common web development issues</span></span>  
    
<span data-ttu-id="7e635-234">[Webhint][WebhintMain]实验将在 "[问题][DevtoolsIssues]" 面板中显示 webhint 反馈。</span><span class="sxs-lookup"><span data-stu-id="7e635-234">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="7e635-235">选择一个问题以显示解决方案文档和您的网站上受影响的资源列表。</span><span class="sxs-lookup"><span data-stu-id="7e635-235">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="7e635-236">选择资源链接以打开 DevTools 中的相关 **网络**、 **源**或 **元素** 窗格。</span><span class="sxs-lookup"><span data-stu-id="7e635-236">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="./media/experiments-webhint.msft.png":::
   <span data-ttu-id="7e635-238">" **问题** " 面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="7e635-238">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="7e635-239">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="7e635-239">Enable Network Console</span></span>  

<span data-ttu-id="7e635-240">**网络控制台** 是通过 HTTP 建立综合网络请求的实验的工作标题。</span><span class="sxs-lookup"><span data-stu-id="7e635-240">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="7e635-241">你可以使用 **网络控制台** 实验来发送 web API 请求。</span><span class="sxs-lookup"><span data-stu-id="7e635-241">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="7e635-242">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="7e635-242">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="7e635-243">若要使用 **网络控制台**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7e635-243">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="7e635-244">打开 " **网络** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="7e635-244">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="7e635-245">查找要更改和重新发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="7e635-245">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="7e635-246">打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **编辑并重播**"。</span><span class="sxs-lookup"><span data-stu-id="7e635-246">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="7e635-247">当 **网络控制台** 打开时，请编辑网络请求信息。</span><span class="sxs-lookup"><span data-stu-id="7e635-247">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="7e635-248">选择 " **发送**"。</span><span class="sxs-lookup"><span data-stu-id="7e635-248">Choose **Send**.</span></span>  
    
:::image type="complex" source="./media/network-network-console.msft.png" alt-text="控制台抽屉中的网络控制台" lightbox="./media/network-network-console.msft.png":::
   <span data-ttu-id="7e635-250">**控制台**抽屉中的**网络控制台**</span><span class="sxs-lookup"><span data-stu-id="7e635-250">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="7e635-251">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="7e635-251">Source Order Viewer</span></span>  

<span data-ttu-id="7e635-252">**源顺序查看器** 是显示页面源中的元素顺序的实验。</span><span class="sxs-lookup"><span data-stu-id="7e635-252">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="7e635-253">屏幕显示顺序可能与源的顺序不同，迷惑屏幕阅读器和键盘用户。</span><span class="sxs-lookup"><span data-stu-id="7e635-253">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="7e635-254">使用 **源顺序查看器** 实验查找屏幕显示顺序和源顺序之间的差异。</span><span class="sxs-lookup"><span data-stu-id="7e635-254">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="7e635-255">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="7e635-255">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="7e635-256">若要使用 " **源顺序查看器**"，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7e635-256">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="7e635-257">打开 " **元素** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="7e635-257">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="7e635-258">打开抽屉 \ (底部 \ ) 面板中的 " **辅助功能** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="7e635-258">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="7e635-259">在 " **源顺序查看器** " 部分下，选择 " **显示源顺序** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="7e635-259">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="7e635-260">突出显示任何 HTML 元素以显示页面源中顺序的覆盖图。</span><span class="sxs-lookup"><span data-stu-id="7e635-260">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  
    
:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text=""辅助功能" 窗格中的 "源顺序查看器"" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="7e635-262">"**辅助功能**" 窗格中的 "**源顺序查看器**"</span><span class="sxs-lookup"><span data-stu-id="7e635-262">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <span data-ttu-id="7e635-263">启用键盘快捷方式编辑器</span><span class="sxs-lookup"><span data-stu-id="7e635-263">Enable keyboard shortcut editor</span></span>

<span data-ttu-id="7e635-264">启用 " **启用键盘快捷方式编辑器** " 实验后，您现在可以自定义 DevTools 中任何操作的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7e635-264">With the **Enable keyboard shortcut editor** experiment turned on, you are now able to customize keyboard shortcuts for any action in the DevTools.</span></span>  <span data-ttu-id="7e635-265">若要自定义特定操作的键盘快捷方式，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7e635-265">To customize the keyboard shortcut for a specific action, complete the following steps.</span></span>  

1.  <span data-ttu-id="7e635-266">[打开 DevTools][DevtoolsOpenMain]。</span><span class="sxs-lookup"><span data-stu-id="7e635-266">[Open DevTools][DevtoolsOpenMain].</span></span>  
1.  <span data-ttu-id="7e635-267">打开 " [设置][DevToolsCustomizeSettings]"。</span><span class="sxs-lookup"><span data-stu-id="7e635-267">Open [Settings][DevToolsCustomizeSettings].</span></span>
    *   <span data-ttu-id="7e635-268">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="7e635-268">Select `Shift`+`?`.</span></span>  
1.  <span data-ttu-id="7e635-269">导航到 " **快捷方式** " 页面。</span><span class="sxs-lookup"><span data-stu-id="7e635-269">Navigate to the **Shortcuts** page.</span></span>  
1.  <span data-ttu-id="7e635-270">选择要自定义的操作。</span><span class="sxs-lookup"><span data-stu-id="7e635-270">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="7e635-271">选择 " **编辑** \ (![ EditKeyboardShortcut ][ImageEditKeyboardShortcutIcon] \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-271">Choose the **Edit** \(![EditKeyboardShortcut][ImageEditKeyboardShortcutIcon]\) icon.</span></span>  
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="从 "设置" 中的 "快捷方式" 页面选择要自定义的操作" lightbox="./media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       <span data-ttu-id="7e635-273">从 "[设置][DevToolsCustomizeSettings]" 中的 "**快捷方式**" 页面选择要自定义的操作</span><span class="sxs-lookup"><span data-stu-id="7e635-273">Choose the action to customize from the **Shortcuts** page in [Settings][DevToolsCustomizeSettings]</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="7e635-274">在键盘上，选择要绑定到操作的键。</span><span class="sxs-lookup"><span data-stu-id="7e635-274">On the keyboard, select the keys you want to bind to the action.</span></span>
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="选择要分配给操作的键" lightbox="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="7e635-276">选择要分配给操作的键</span><span class="sxs-lookup"><span data-stu-id="7e635-276">Select the keys you want to assign to the action</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="7e635-277">若要保存新的键盘快捷方式，请选择 "选中标记 \ (</span><span class="sxs-lookup"><span data-stu-id="7e635-277">To save your new keyboard shortcut, choose the checkmark \(</span></span>![CheckmarkKeyboardShortcut][ImageCheckmarkKeyboardShortcutIcon]<span data-ttu-id="7e635-279">\ ) 图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-279">\) icon.</span></span>
    
    :::image type="complex" source="./media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="选择复选标记图标以保存新的键盘快捷方式" lightbox="./media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="7e635-281">选择复选标记图标以保存新的键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="7e635-281">Choose the checkmark icon to save your new keyboard shortcut</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="7e635-282">选择新的键盘快捷方式以触发 DevTools 中的操作。</span><span class="sxs-lookup"><span data-stu-id="7e635-282">Select your new keyboard shortcut to trigger the action in the DevTools.</span></span>  
    
<span data-ttu-id="7e635-283">在 " **快捷方式** " 页面上， **自定义键盘快捷方式** \ (![ CustomKeyboardShortcut ][ImageCustomKeyboardShortcutIcon] \ ) 图标显示已自定义的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7e635-283">On the **Shortcuts** page, the **Custom Keyboard Shortcut** \(![CustomKeyboardShortcut][ImageCustomKeyboardShortcutIcon]\) icon displays keyboard shortcuts that you have customized.</span></span>  <span data-ttu-id="7e635-284">若要重置所有快捷方式，请选择 " **还原默认快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="7e635-284">To reset all shortcuts, choose **Restore default shortcuts**.</span></span>  

<span data-ttu-id="7e635-285">在编辑操作的键盘快捷方式时，若要放弃所做的更改，请选择 "X (![ XKeyboardShortcut ][ImageXKeyboardShortcutIcon] \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-285">When you are editing the keyboard shortcuts for an action, to discard your changes, choose the X \(![XKeyboardShortcut][ImageXKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="7e635-286">若要删除特定操作的快捷方式，请选择 " **删除快捷方式** \ (![ DeleteKeyboardShortcut ][ImageDeleteKeyboardShortcutIcon] \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="7e635-286">To remove shortcuts for a specific action, choose the **Delete shortcut** \(![DeleteKeyboardShortcut][ImageDeleteKeyboardShortcutIcon]\) icon.</span></span>  <span data-ttu-id="7e635-287">若要为操作添加多个快捷方式，请选择 " **添加快捷方式**"。</span><span class="sxs-lookup"><span data-stu-id="7e635-287">To add multiple shortcuts for an action, choose **Add a shortcut**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e635-288">如果键盘快捷方式当前已分配给另一个操作，您将无法保存它以执行新操作。</span><span class="sxs-lookup"><span data-stu-id="7e635-288">If a keyboard shortcut is currently assigned to another action, you are not able to save it for a new action.</span></span>  <span data-ttu-id="7e635-289">必须先删除上一个操作的键盘快捷方式，然后再将其添加到新操作。</span><span class="sxs-lookup"><span data-stu-id="7e635-289">You must first delete the keyboard shortcut for the previous action and then add it to the new action.</span></span>  

<!--Available in Microsoft Edge version 87 and later.  -->

### <span data-ttu-id="7e635-290">在3D 视图中打开复合图层</span><span class="sxs-lookup"><span data-stu-id="7e635-290">Turn on Composited Layers in 3D View</span></span>

<span data-ttu-id="7e635-291">现在，你可以在 z 索引和文档对象模型 \ (DOM \ ) 中可视化层。</span><span class="sxs-lookup"><span data-stu-id="7e635-291">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="7e635-292">此功能可帮助你在不切换上下文的情况下进行调试。</span><span class="sxs-lookup"><span data-stu-id="7e635-292">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="7e635-293">您发现减少上下文切换是一个主要难点。</span><span class="sxs-lookup"><span data-stu-id="7e635-293">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="7e635-294">你编写的代码对你的 web 应用的影响并非总是很清楚。</span><span class="sxs-lookup"><span data-stu-id="7e635-294">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="7e635-295">为了获得全面的可视化调试体验，现在组合了3D 视图和复合图层。</span><span class="sxs-lookup"><span data-stu-id="7e635-295">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  <span data-ttu-id="7e635-296">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="7e635-296">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="7e635-297">若要使用 **合成图层**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7e635-297">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="7e635-298">在抽屉上，选择 " **3D 视图** " 工具。</span><span class="sxs-lookup"><span data-stu-id="7e635-298">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="7e635-299">打开 " **复合图层** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="7e635-299">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="7e635-300">将显示应用的所有已绘制的图层。</span><span class="sxs-lookup"><span data-stu-id="7e635-300">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="7e635-301">在你自己的 web 应用中试用此功能。</span><span class="sxs-lookup"><span data-stu-id="7e635-301">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="./media/experiments-layers.msft.png" alt-text=""复合图层" 窗格" lightbox="./media/experiments-layers.msft.png":::
   <span data-ttu-id="7e635-303">"**复合图层**" 窗格</span><span class="sxs-lookup"><span data-stu-id="7e635-303">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

## <span data-ttu-id="7e635-304">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="7e635-304">Previous experimental features</span></span>  

*   <span data-ttu-id="7e635-305">[3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="7e635-305">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="7e635-306">[自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在在 Microsoft Edge 版本86或更高版本中可用且默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="7e635-306">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  

## <span data-ttu-id="7e635-307">提供有关实验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="7e635-307">Providing feedback on experimental features</span></span>  

<span data-ttu-id="7e635-308">提供有关 Microsoft Edge DevTools 实验的反馈或与 DevTools 相关的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="7e635-308">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="7e635-309">使用 DevTools 中的 " **发送反馈** " 图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="7e635-309">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="7e635-310">向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文</span><span class="sxs-lookup"><span data-stu-id="7e635-310">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的 "发送反馈" 图标" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="7e635-312">Microsoft Edge DevTools 中的 " **发送反馈** " 图标</span><span class="sxs-lookup"><span data-stu-id="7e635-312">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageRotateIcon]: ./media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ./media/span-dark-icon.msft.png  
[ImageExperimentalApisIcon]: ./media/experimental-apis-dark-icon.msft.png  
[ImageEditKeyboardShortcutIcon]: ./media/edit-keyboard-shortcut-icon.msft.png  
[ImageCheckmarkKeyboardShortcutIcon]: ./media/checkmark-keyboard-shortcut-icon.msft.png  
[ImageCustomKeyboardShortcutIcon]: ./media/custom-keyboard-shortcut-icon.msft.png  
[ImageDeleteKeyboardShortcutIcon]: ./media/delete-keyboard-shortcut-icon.msft.png  
[ImageXKeyboardShortcutIcon]: ./media/discard-changes-keyboard-shortcut-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D 视图 |Microsoft 文档"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ./device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 |Microsoft Edge"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpenMain]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏幕 web 体验 |Microsoft 文档"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface 双核仿真器 |Microsoft 文档"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用双屏幕设备的接缝简介 |Microsoft 文档"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface 双核仿真器 |Microsoft 文档"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "适用于双屏幕检测的 CSS 媒体屏幕扩展功能 |Microsoft 文档"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft 文档"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端 |Microsoft 文档"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface 双核 |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy 折页 |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
