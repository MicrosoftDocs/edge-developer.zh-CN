---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: f885201ddfb7553a2b9c58a07dd52b7a77c4137a
ms.sourcegitcommit: 0326a4082064e9cdfa602736f3f9ce7d8d294604
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2020
ms.locfileid: "11094927"
---
# <span data-ttu-id="9bd34-104">实验功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-104">Experimental features</span></span>  

<span data-ttu-id="9bd34-105">Microsoft Edge DevTools 提供对仍在开发中的实验功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9bd34-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="9bd34-106">你可以在发布每个功能之前测试和 [提供反馈](#providing-feedback-on-experimental-features) 。</span><span class="sxs-lookup"><span data-stu-id="9bd34-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="9bd34-107">尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。</span><span class="sxs-lookup"><span data-stu-id="9bd34-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="9bd34-108">启用实验功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-108">Turn on experimental features</span></span>  

<span data-ttu-id="9bd34-109">若要在 Microsoft Edge 中打开 " (" 或 "关闭" ) 实验功能，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9bd34-109">To turn on \(or off\) experimental features in Microsoft Edge, use the following steps.</span></span>  

1.  <span data-ttu-id="9bd34-110">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="9bd34-110">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="9bd34-111">选择 `Control` + `Shift` + `I` \ (Windows \ ) 或 `Command` + `Option` + `I` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="9bd34-111">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="9bd34-112">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="9bd34-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="9bd34-113">打开 " [设置][DevToolsCustomizeSettings] " 窗格。</span><span class="sxs-lookup"><span data-stu-id="9bd34-113">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="9bd34-114">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="9bd34-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="9bd34-115">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="9bd34-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="9bd34-116">在 " **设置** " 窗格的左侧，选择 " **实验** " 部分。</span><span class="sxs-lookup"><span data-stu-id="9bd34-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.msft.png":::
       <span data-ttu-id="9bd34-118">DevTools 设置中的实验列表</span><span class="sxs-lookup"><span data-stu-id="9bd34-118">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9bd34-119">在 " **实验** " 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="9bd34-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="9bd34-120">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="9bd34-120">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="9bd34-121">实验性功能将不断更新，并可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="9bd34-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="9bd34-122">若要关闭实验功能，请打开 " **试验** " 页面，然后清除要关闭的实验功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="9bd34-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="9bd34-123">突出显示实验功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-123">Highlighted experimental features</span></span>  

<span data-ttu-id="9bd34-124">以下部分介绍 Microsoft Edge 中可用的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="9bd34-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="9bd34-125">实验性功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-125">Experimental feature</span></span> | <span data-ttu-id="9bd34-126">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="9bd34-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="9bd34-127">仿真：支持双重屏幕模式</span><span class="sxs-lookup"><span data-stu-id="9bd34-127">Emulation: Support dual screen mode</span></span>](#emulation-support-dual-screen-mode) | <span data-ttu-id="9bd34-128">84或更高版本</span><span class="sxs-lookup"><span data-stu-id="9bd34-128">84 or later</span></span> |  
| [<span data-ttu-id="9bd34-129">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-129">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="9bd34-130">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="9bd34-130">85 or later</span></span> |  
| [<span data-ttu-id="9bd34-131">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="9bd34-131">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="9bd34-132">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="9bd34-132">85 or later</span></span> |  
| [<span data-ttu-id="9bd34-133">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="9bd34-133">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="9bd34-134">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="9bd34-134">85 or later</span></span> |  
| [<span data-ttu-id="9bd34-135">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="9bd34-135">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="9bd34-136">85或更高版本</span><span class="sxs-lookup"><span data-stu-id="9bd34-136">85 or later</span></span> |  
| [<span data-ttu-id="9bd34-137">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="9bd34-137">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="9bd34-138">86或更高版本</span><span class="sxs-lookup"><span data-stu-id="9bd34-138">86 or later</span></span> |  

### <span data-ttu-id="9bd34-139">仿真：支持双重屏幕模式</span><span class="sxs-lookup"><span data-stu-id="9bd34-139">Emulation: Support dual screen mode</span></span>  

<span data-ttu-id="9bd34-140">提供用于模拟 Microsoft Edge 中的两个新的双屏幕和可折叠设备的附加功能。</span><span class="sxs-lookup"><span data-stu-id="9bd34-140">Provides additional features for emulating two new dual-screen and foldable devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="9bd34-141">Surface 双核</span><span class="sxs-lookup"><span data-stu-id="9bd34-141">Surface Duo</span></span>][SurfaceDevicesDuo]  
*   [<span data-ttu-id="9bd34-142">Samsung Galaxy 折页</span><span class="sxs-lookup"><span data-stu-id="9bd34-142">Samsung Galaxy Fold</span></span>][SamsungMobileGalaxyFold]  

<span data-ttu-id="9bd34-143">模拟设备并在以下姿势之间切换。</span><span class="sxs-lookup"><span data-stu-id="9bd34-143">Emulate the devices and toggle between the following postures.</span></span>  

*   <span data-ttu-id="9bd34-144">单屏幕或折叠的状况</span><span class="sxs-lookup"><span data-stu-id="9bd34-144">single-screen or folded posture</span></span>  
*   <span data-ttu-id="9bd34-145">双屏幕或展开的状况</span><span class="sxs-lookup"><span data-stu-id="9bd34-145">dual-screen or unfolded posture</span></span>  
    
<span data-ttu-id="9bd34-146">[启用实验性 Web 平台 api](#enable-experimental-apis) 并使用 [CSS 媒体屏幕生成功能][DualScreenDocsCssMedia] 和 [JavaScript getWindowSegments API][DualScreenDocsJSAPI] 来增强您的网站 \ (或适用于双屏幕和可折叠设备的应用 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="9bd34-146">[Enable experimental Web Platform APIs](#enable-experimental-apis) and use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI] to enhance your website \(or app\) for dual-screen and foldable devices.</span></span>  

:::image type="complex" source="./media/experiments-surface-duo-emulation.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-surface-duo-emulation.msft.png":::  
   <span data-ttu-id="9bd34-148">在 Microsoft Edge 中模拟 Surface 双核</span><span class="sxs-lookup"><span data-stu-id="9bd34-148">Emulate Surface Duo in Microsoft Edge</span></span>  
:::image-end:::  

#### <span data-ttu-id="9bd34-149">启用实验性 Api</span><span class="sxs-lookup"><span data-stu-id="9bd34-149">Enable experimental APIs</span></span>  

<span data-ttu-id="9bd34-150">若要使用 [CSS 媒体屏幕生成功能][DualScreenDocsCssMedia] 和 [JavaScript getWindowSegments API][DualScreenDocsJSAPI]，请打开 `Experimental Web Platform features` Microsoft Edge 中的标志。</span><span class="sxs-lookup"><span data-stu-id="9bd34-150">To use the [CSS media screen-spanning feature][DualScreenDocsCssMedia] and [JavaScript getWindowSegments API][DualScreenDocsJSAPI], turn on the `Experimental Web Platform features` flag in Microsoft Edge.</span></span>  <span data-ttu-id="9bd34-151">完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9bd34-151">Complete the following steps.</span></span>  

1.  <span data-ttu-id="9bd34-152">导航到 `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="9bd34-152">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="9bd34-153">在 " **搜索标志** " 文本框中，输入 `Experimental Web Platform features` ，选择实验性的 **Web 平台功能** 标志，将 " **已禁用** " 更改为 " **已启用**"。</span><span class="sxs-lookup"><span data-stu-id="9bd34-153">In the **Search flags** textbox, enter `Experimental Web Platform features`, choose the **Experimental Web Platform features** flag, and change **Disabled** to **Enabled**.</span></span>  
1.  <span data-ttu-id="9bd34-154">重启 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="9bd34-154">Restart Microsoft Edge.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   <span data-ttu-id="9bd34-156">启用实验性 Web 平台功能标志</span><span class="sxs-lookup"><span data-stu-id="9bd34-156">Enable the Experimental Web Platform features flag</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="9bd34-157">如果你使用[CSS 媒体查询][DualScreenDocsCssMedia]或[JavaScript WINDOWS Segment 枚举 API][DualScreenDocsJSAPI]来增强你的网站或适用于[surface 双核][SurfaceDevicesDuo]的应用，你还必须在[Surface 双核][SurfaceDevicesDuo]设备上启用[Android Microsoft Edge 应用][GooglePlayMicrosoftEdge]中的**实验性 Web 平台功能**标志。</span><span class="sxs-lookup"><span data-stu-id="9bd34-157">If you are using [CSS media queries][DualScreenDocsCssMedia] or the [JavaScript Windows Segment Enumeration API][DualScreenDocsJSAPI] to enhance your website or app for the [Surface Duo][SurfaceDevicesDuo], you must also enable the **Experimental Web Platform features** flag in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on your [Surface Duo][SurfaceDevicesDuo] device.</span></span>  
> 
> <span data-ttu-id="9bd34-158">如果在[桌面 Microsoft edge][MicrosoftEdge]中启用了实验性的**Web 平台功能**标志，并且在[Android microsoft edge 应用][GooglePlayMicrosoftEdge]中禁用了该标志，则桌面 microsoft edge 中的 Surface 双核模拟器中的网站或应用的行为与[Surface 双核][SurfaceDevicesDuo]上的[Android Microsoft edge 应用][GooglePlayMicrosoftEdge]不匹配。</span><span class="sxs-lookup"><span data-stu-id="9bd34-158">If the **Experimental Web Platform features** flag is enabled in [desktop Microsoft Edge][MicrosoftEdge] and disabled in the [Android Microsoft Edge app][GooglePlayMicrosoftEdge], the behavior of your website or app in the Surface Duo emulator in desktop Microsoft Edge does not match with the [Android Microsoft Edge app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="9bd34-159">确保标志在 Android 和桌面 Microsoft Edge 中匹配，以便在 [桌面 Microsoft edge][MicrosoftEdge]中成功使用 Surface 双核模拟器。</span><span class="sxs-lookup"><span data-stu-id="9bd34-159">Ensure that the flags are matching across Android and desktop Microsoft Edge to successfully use the Surface Duo emulator in [desktop Microsoft Edge][MicrosoftEdge].</span></span>  

#### <span data-ttu-id="9bd34-160">在折叠和双屏幕设备上进行测试</span><span class="sxs-lookup"><span data-stu-id="9bd34-160">Testing on foldable and dual-screen devices</span></span>  

<span data-ttu-id="9bd34-161">当您在 Microsoft Edge 的双屏幕状态下模拟 [Surface 双核][SurfaceDevicesDuo] 时，接缝 \ (在您的网站或应用上绘制的两个屏幕 ) 之间的空间。</span><span class="sxs-lookup"><span data-stu-id="9bd34-161">When you emulate the [Surface Duo][SurfaceDevicesDuo] in a dual-screen posture in Microsoft Edge, the seam \(the space between the two screens\) is drawn over your website or app.</span></span>  

<span data-ttu-id="9bd34-162">仿真显示与你的网站 \ (或应用 \ ) 在[Surface 双核][SurfaceDevicesDuo]上的[Microsoft Edge Android 应用][GooglePlayMicrosoftEdge]中呈现的方式相匹配。</span><span class="sxs-lookup"><span data-stu-id="9bd34-162">The emulated display matches the way your website \(or app\) renders in the [Microsoft Edge Android app][GooglePlayMicrosoftEdge] on [Surface Duo][SurfaceDevicesDuo].</span></span>  <span data-ttu-id="9bd34-163">您可能需要更新您的网站 \ (或应用 \ ) ，以便更好地沿接缝显示。</span><span class="sxs-lookup"><span data-stu-id="9bd34-163">You may have to update your website \(or app\) to display better along the seam.</span></span>  <span data-ttu-id="9bd34-164">有关将您的网站 \ (或 app \ ) 调整到接缝的详细信息，请导航到如何使用 Surface 双核文档中 [的接缝][DualScreenIntroductionHowWorkSeam] 。</span><span class="sxs-lookup"><span data-stu-id="9bd34-164">For more information about adapting your website \(or app\) to the seam, navigate to [How to work with the seam][DualScreenIntroductionHowWorkSeam] in the Surface Duo documentation.</span></span>  

<span data-ttu-id="9bd34-165">[设备工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport]具有其他功能，可帮助你在多个姿势和方向中测试你的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="9bd34-165">The [Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport] has additional features to help you test your website or app in multiple postures and orientations.</span></span>  <span data-ttu-id="9bd34-166">选择 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "，将视区旋转为横向方向。</span><span class="sxs-lookup"><span data-stu-id="9bd34-166">Choose **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span> <span data-ttu-id="9bd34-167">将该功能与 **span** \ (![ span ][ImageSpanIcon] \ ) 组合在单个屏幕或折叠的姿势或已展开的屏幕或已展开的之间切换。</span><span class="sxs-lookup"><span data-stu-id="9bd34-167">Combine the feature with **Span** \(![Span][ImageSpanIcon]\) to toggle between single-screen or folded and dual-screen or unfolded postures.</span></span>  <span data-ttu-id="9bd34-168">同时，这些功能支持在所有四种可能的姿势和方向中测试你的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="9bd34-168">Together, the features enable testing your website or app in all four possible postures and orientations.</span></span>  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   <span data-ttu-id="9bd34-170">双屏幕和折叠设备的姿势和方向的矩阵</span><span class="sxs-lookup"><span data-stu-id="9bd34-170">Matrix of postures and orientations for dual-screen and foldable devices</span></span>  
:::image-end:::  

<span data-ttu-id="9bd34-171"> (ExperimentalApis \ ) 图标中的 **实验 Web 平台功能** \ " ![ ][ImageExperimentalApisIcon] 显示实验性 **web 平台功能** 标志的状态。</span><span class="sxs-lookup"><span data-stu-id="9bd34-171">The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="9bd34-172">如果标志处于打开状态，则会突出显示该图标。</span><span class="sxs-lookup"><span data-stu-id="9bd34-172">If the flag is turned on, the icon is highlighted.</span></span>  <span data-ttu-id="9bd34-173">如果该标志已关闭，则不会突出显示该图标。</span><span class="sxs-lookup"><span data-stu-id="9bd34-173">If the flag is turned off, the icon is not highlighted.</span></span>  <span data-ttu-id="9bd34-174">若要打开 " (" 或 "关闭" ) 标志，请导航到 `edge://flags` "标志" 并切换。</span><span class="sxs-lookup"><span data-stu-id="9bd34-174">To turn on \(or off\) the flag, navigate to `edge://flags` and toggle the flag.</span></span>  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

<span data-ttu-id="9bd34-175">下面是可帮助你增强网站的其他资源 (或适用于双屏幕设备的应用 \ ) ：</span><span class="sxs-lookup"><span data-stu-id="9bd34-175">Here are additional resources that may help you enhance your website \(or app\) for dual-screen devices:</span></span>
*   <span data-ttu-id="9bd34-176">有关在双屏幕设备上进行 web 开发的详细信息，请导航到 [双屏幕 web 体验][DualScreenWebIndex]。</span><span class="sxs-lookup"><span data-stu-id="9bd34-176">For more information about web development on dual-screen devices, navigate to [Dual-screen web experiences][DualScreenWebIndex].</span></span>  
*   <span data-ttu-id="9bd34-177">安装 [Surface 双核模拟器][DualScreenAndroidUseEmulator]。</span><span class="sxs-lookup"><span data-stu-id="9bd34-177">Install the [Surface Duo emulator][DualScreenAndroidUseEmulator].</span></span>  <span data-ttu-id="9bd34-178">它与 Microsoft Edge 中的仿真器不同，模拟运行 Android 的 Surface 双核，并与 [Android Studio][AndroidDeveloperStudio]集成。</span><span class="sxs-lookup"><span data-stu-id="9bd34-178">It is different from the emulator in Microsoft Edge, emulates the Surface Duo running Android, and integrates with [Android Studio][AndroidDeveloperStudio].</span></span>  <span data-ttu-id="9bd34-179">有关详细信息，请导航到 [获取 Surface 双核 SDK][DualScreenAndroidGetDuoSdk]。</span><span class="sxs-lookup"><span data-stu-id="9bd34-179">For more information, navigate to [Get the Surface Duo SDK][DualScreenAndroidGetDuoSdk].</span></span>  

> [!NOTE]
> <span data-ttu-id="9bd34-180">以下是当前已知问题的列表。</span><span class="sxs-lookup"><span data-stu-id="9bd34-180">The following is a list of current known issues.</span></span>  
> 
> *   <span data-ttu-id="9bd34-181">当使用 [Microsoft 远程桌面客户端][RemoteDesktopClientDocs] 连接到远程电脑并模拟 [Surface 双核][SurfaceDevicesDuo] 或 [Samsung Galaxy 折页][SamsungMobileGalaxyFold]时，指针可能会晃动或断断续续。</span><span class="sxs-lookup"><span data-stu-id="9bd34-181">When using a [Microsoft Remote Desktop client][RemoteDesktopClientDocs] to connect to a remote PC and emulate the [Surface Duo][SurfaceDevicesDuo] or [Samsung Galaxy Fold][SamsungMobileGalaxyFold], the pointer may shake or stutter.</span></span>  <span data-ttu-id="9bd34-182">如果遇到问题，请 [发送反馈](#providing-feedback-on-experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="9bd34-182">If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).</span></span>  

### <span data-ttu-id="9bd34-183">启用新的 CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-183">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="9bd34-184">此实验功能提供了许多新的可视化效果，可帮助你调试 CSS 网格布局。</span><span class="sxs-lookup"><span data-stu-id="9bd34-184">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="9bd34-185">若要预览最新实验功能，请 [启用此实验](#turn-on-experimental-features) 并重新加载 DevTools。</span><span class="sxs-lookup"><span data-stu-id="9bd34-185">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="9bd34-186">默认情况下，此实验在 Edge 87 和更高版本中处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="9bd34-186">This experiment is on by default in Edge 87 and later.</span></span>  

#### <span data-ttu-id="9bd34-187">利用 "检查" 工具查看悬停的网格重叠</span><span class="sxs-lookup"><span data-stu-id="9bd34-187">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="9bd34-188">" **检查** " 工具提供了一种通过鼠标悬停在网站中来标识和可视化 CSS 网格布局的快速方法。</span><span class="sxs-lookup"><span data-stu-id="9bd34-188">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="9bd34-189">选择 DevTools 左上角的 " **检查** \ (![ 检查 ](./media/inspect-icon.msft.png) \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="9bd34-189">Choose the **Inspect** \(![Inspect](./media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="9bd34-190">然后，将鼠标悬停在正在调试的网站上的网格元素上。</span><span class="sxs-lookup"><span data-stu-id="9bd34-190">Then, hover over a Grid element on the website you are debugging.</span></span>  <span data-ttu-id="9bd34-191">大纲显示在网格周围，阴影指示网格间隙的位置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="9bd34-191">Outlines are displayed around the grid, and shading indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="./media/grid-inspect.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/grid-inspect.msft.png":::
   <span data-ttu-id="9bd34-193">通过 "检查" 工具查看网格</span><span class="sxs-lookup"><span data-stu-id="9bd34-193">Viewing grids with the Inspect tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="9bd34-194">查看永久网格覆盖</span><span class="sxs-lookup"><span data-stu-id="9bd34-194">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="9bd34-195">在 Edge 86 和更高版本中，实验性 CSS 网格功能还提供了启用持久网格覆盖的选项。</span><span class="sxs-lookup"><span data-stu-id="9bd34-195">In Edge 86 and later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="9bd34-196">永久性覆盖提供多项好处。</span><span class="sxs-lookup"><span data-stu-id="9bd34-196">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="9bd34-197">滚动、移动鼠标和使用 DevTools 的其他功能时，永久叠加在页面上保持可见。</span><span class="sxs-lookup"><span data-stu-id="9bd34-197">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="9bd34-198">可以同时启用多个永久覆盖，从而使你可以同时查看大量的网格布局。</span><span class="sxs-lookup"><span data-stu-id="9bd34-198">Multiple persistent overlays can be enabled at the same time, allowing you to review numerous grid layouts at once.</span></span>  
*   <span data-ttu-id="9bd34-199">永久覆盖提供许多配置选项，如隐藏或显示网格区名称、网格间隙、轨道大小等。</span><span class="sxs-lookup"><span data-stu-id="9bd34-199">Persistent overlays offer many configuration options, such as hiding or showing grid area names, grid gaps, track sizes, and more.</span></span>  

<span data-ttu-id="9bd34-200">切换永久网格覆盖的两种方式。</span><span class="sxs-lookup"><span data-stu-id="9bd34-200">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="9bd34-201">选择 "**元素**" 工具的 DOM 树中显示的任何网格元素旁边的**网格**菱形。</span><span class="sxs-lookup"><span data-stu-id="9bd34-201">Choose the **Grid** lozenge next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="./media/grid-adorner.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/grid-adorner.msft.png":::
       <span data-ttu-id="9bd34-203">元素工具中的网格菱形</span><span class="sxs-lookup"><span data-stu-id="9bd34-203">Grid lozenge in Elements tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="9bd34-204">打开位于 "元素" 工具中的新 **版式** 面板，然后选择要突出显示的每个网格元素旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="9bd34-204">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="./media/grid-layout-zoom.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="9bd34-206">布局面板</span><span class="sxs-lookup"><span data-stu-id="9bd34-206">Layout panel</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="9bd34-207">配置永久重叠</span><span class="sxs-lookup"><span data-stu-id="9bd34-207">Configuring persistent overlays</span></span>  

<span data-ttu-id="9bd34-208">新的 **版式** 面板，位于 " **元素** " 工具中，位于边缘86和更高版本中的 " **样式** " 和 " **计算** " 选项卡上，曲面配置选项用于永久叠加。</span><span class="sxs-lookup"><span data-stu-id="9bd34-208">The new **Layout** panel, located in the **Elements** tool alongside the **Styles** and **Computed** tabs in Edge 86 and later, surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-grid.msft.png":::
   <span data-ttu-id="9bd34-210">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-210">CSS grid debugging feature</span></span>  
:::image-end:::  

### <span data-ttu-id="9bd34-211">启用支持以在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="9bd34-211">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="9bd34-212">通常，诸如 **元素** 和 **网络** 之类的工具可能仅在位于 DevTools 顶部的主面板中打开。</span><span class="sxs-lookup"><span data-stu-id="9bd34-212">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="9bd34-213">通常仅在位于 DevTools 底部的**抽屉**面板中打开的**3D 视图**和**问题**等工具。</span><span class="sxs-lookup"><span data-stu-id="9bd34-213">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="9bd34-214">选择实验后，您可以在顶部面板和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="9bd34-214">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="9bd34-215">若要移动工具，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **移到页首** " 或 " **移至底部**"。</span><span class="sxs-lookup"><span data-stu-id="9bd34-215">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="9bd34-216">此实验允许你自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="9bd34-216">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="9bd34-217">若要显示或隐藏 **抽屉** 面板，请选择 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="9bd34-217">To show or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-move-panels.msft.png":::
   <span data-ttu-id="9bd34-219">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="9bd34-219">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="9bd34-220">启用 webhint</span><span class="sxs-lookup"><span data-stu-id="9bd34-220">Enable webhint</span></span>  

<span data-ttu-id="9bd34-221">[webhint][WebhintMain] 是一种开放源工具，可提供网站和本地网页的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="9bd34-221">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local web pages.</span></span>  <span data-ttu-id="9bd34-222">[Webhint][WebhintMain]提供的反馈类型。</span><span class="sxs-lookup"><span data-stu-id="9bd34-222">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="9bd34-223">辅助功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-223">accessibility</span></span>  
*   <span data-ttu-id="9bd34-224">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="9bd34-224">cross-browser compatibility</span></span>  
*   <span data-ttu-id="9bd34-225">安全性</span><span class="sxs-lookup"><span data-stu-id="9bd34-225">security</span></span>  
*   <span data-ttu-id="9bd34-226">性能</span><span class="sxs-lookup"><span data-stu-id="9bd34-226">performance</span></span>  
*   <span data-ttu-id="9bd34-227">PWA</span><span class="sxs-lookup"><span data-stu-id="9bd34-227">PWAs</span></span>  
*   <span data-ttu-id="9bd34-228">其他常见 web 开发问题</span><span class="sxs-lookup"><span data-stu-id="9bd34-228">other common web development issues</span></span>  

<span data-ttu-id="9bd34-229">[Webhint][WebhintMain]实验将在 "[问题][DevtoolsIssues]" 面板中显示 webhint 反馈。</span><span class="sxs-lookup"><span data-stu-id="9bd34-229">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="9bd34-230">选择一个问题以显示解决方案文档和您的网站上受影响的资源列表。</span><span class="sxs-lookup"><span data-stu-id="9bd34-230">Select an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="9bd34-231">选择资源链接以打开 DevTools 中的相关 **网络**、 **源**或 **元素** 窗格。</span><span class="sxs-lookup"><span data-stu-id="9bd34-231">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-webhint.msft.png":::
   <span data-ttu-id="9bd34-233">" **问题** " 面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="9bd34-233">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="9bd34-234">启用网络控制台</span><span class="sxs-lookup"><span data-stu-id="9bd34-234">Enable Network Console</span></span>  

<span data-ttu-id="9bd34-235">**网络控制台** 是通过 HTTP 建立综合网络请求的实验的工作标题。</span><span class="sxs-lookup"><span data-stu-id="9bd34-235">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="9bd34-236">你可以使用 **网络控制台** 实验来发送 web API 请求。</span><span class="sxs-lookup"><span data-stu-id="9bd34-236">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="9bd34-237">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="9bd34-237">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="9bd34-238">若要使用 **网络控制台**，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9bd34-238">To use the **Network Console**, use the following steps.</span></span>  

1.  <span data-ttu-id="9bd34-239">打开 " **网络** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="9bd34-239">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="9bd34-240">查找要更改和重新发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="9bd34-240">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="9bd34-241">打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **编辑并重播**"。</span><span class="sxs-lookup"><span data-stu-id="9bd34-241">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="9bd34-242">当 **网络控制台** 打开时，请编辑网络请求信息。</span><span class="sxs-lookup"><span data-stu-id="9bd34-242">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="9bd34-243">选择 " **发送**"。</span><span class="sxs-lookup"><span data-stu-id="9bd34-243">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/network-network-console.msft.png":::
   <span data-ttu-id="9bd34-245">**控制台**抽屉中的**网络控制台**</span><span class="sxs-lookup"><span data-stu-id="9bd34-245">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="9bd34-246">源订单查看器</span><span class="sxs-lookup"><span data-stu-id="9bd34-246">Source Order Viewer</span></span>  

<span data-ttu-id="9bd34-247">**源顺序查看器** 是显示页面源中的元素顺序的实验。</span><span class="sxs-lookup"><span data-stu-id="9bd34-247">**Source Order Viewer** is an experiment that displays the order of elements in the page source.</span></span>  <span data-ttu-id="9bd34-248">屏幕显示顺序可能与源的顺序不同，迷惑屏幕阅读器和键盘用户。</span><span class="sxs-lookup"><span data-stu-id="9bd34-248">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="9bd34-249">使用 **源顺序查看器** 实验查找屏幕显示顺序和源顺序之间的差异。</span><span class="sxs-lookup"><span data-stu-id="9bd34-249">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="9bd34-250">启用实验后，确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="9bd34-250">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="9bd34-251">若要使用 " **源顺序查看器**"，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9bd34-251">To use **Source Order Viewer**, use the following steps.</span></span>  

1.  <span data-ttu-id="9bd34-252">打开 " **元素** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="9bd34-252">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="9bd34-253">打开抽屉 \ (底部 \ ) 面板中的 " **辅助功能** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="9bd34-253">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="9bd34-254">在 " **源顺序查看器** " 部分中，选中 " **显示源顺序** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="9bd34-254">Under the **Source Order Viewer** section, select the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="9bd34-255">突出显示任何 HTML 元素以显示页面源中顺序的覆盖图。</span><span class="sxs-lookup"><span data-stu-id="9bd34-255">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="9bd34-257">"**辅助功能**" 窗格中的 "**源顺序查看器**"</span><span class="sxs-lookup"><span data-stu-id="9bd34-257">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## <span data-ttu-id="9bd34-258">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="9bd34-258">Previous experimental features</span></span>  

*   <span data-ttu-id="9bd34-259">[3D 视图][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="9bd34-259">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="9bd34-260">[自定义键盘快捷方式][DevtoolsCustomKeyboardShortcuts] 现在在 Microsoft Edge 版本86或更高版本中可用且默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="9bd34-260">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  

## <span data-ttu-id="9bd34-261">提供有关实验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="9bd34-261">Providing feedback on experimental features</span></span>  

<span data-ttu-id="9bd34-262">提供有关 Microsoft Edge DevTools 实验的反馈或与 DevTools 相关的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="9bd34-262">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="9bd34-263">使用 DevTools 中的 " **发送反馈** " 图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="9bd34-263">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="9bd34-264">向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文</span><span class="sxs-lookup"><span data-stu-id="9bd34-264">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="9bd34-266">Microsoft Edge DevTools 中的 " **发送反馈** " 图标</span><span class="sxs-lookup"><span data-stu-id="9bd34-266">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageRotateIcon]: ./media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ./media/span-dark-icon.msft.png  
[ImageExperimentalApisIcon]: ./media/experimental-apis-dark-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D 视图 |Microsoft 文档"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ./device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 |Microsoft Edge"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"

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
