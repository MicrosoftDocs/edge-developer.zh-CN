---
description: 使用模拟面板测试不同的浏览器配置文件、屏幕大小和分辨率以及 GPS 位置坐标
title: DevTools - 模拟
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 设备仿真， 响应式设计， 地理位置， 分辨率
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: af740472f22a8b322c03cb672a3da909ef195fac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232259"
---
# <span data-ttu-id="95c66-104">枚举</span><span class="sxs-lookup"><span data-stu-id="95c66-104">Emulation</span></span>  

> [!NOTE]
> <span data-ttu-id="95c66-105">新版 Microsoft Edge 是使用 Chromium 构建的，并从版本 75 开始。</span><span class="sxs-lookup"><span data-stu-id="95c66-105">The new Microsoft Edge is built using Chromium, and starts at version 75.</span></span>  <span data-ttu-id="95c66-106">有关详细信息，请 [下载新的 Microsoft Edge，][MicrosoftNewEdge]并尝试使用新的 Microsoft Edge ([Chromium) 开发人员工具][DevtoolsGuideChromium]。</span><span class="sxs-lookup"><span data-stu-id="95c66-106">For more information, [download the new Microsoft Edge][MicrosoftNewEdge], and try out the new [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromium].</span></span>  
> 
> <span data-ttu-id="95c66-107">若要模拟新 DevTools 中的不同设备、浏览器、屏幕大小和分辨率，请导航到 Microsoft [Edge \(Chromium\) DevTools 中的"模拟移动设备"。][DevtoolsGuideChromiumDeviceMode]</span><span class="sxs-lookup"><span data-stu-id="95c66-107">To emulate different devices, browsers, screen sizes, and resolutions in the new DevTools, navigate to [Emulate Mobile Devices in Microsoft Edge \(Chromium\) DevTools][DevtoolsGuideChromiumDeviceMode].</span></span>  

<span data-ttu-id="95c66-108">**模拟面板**可帮助执行下列活动。</span><span class="sxs-lookup"><span data-stu-id="95c66-108">The **Emulation** panel helps with the following activities.</span></span>    

*   <span data-ttu-id="95c66-109">模拟[各种设备配置文件](#device)[、浏览器](#browser-profile)[和屏幕大小和分辨率](#display)</span><span class="sxs-lookup"><span data-stu-id="95c66-109">Simulate various [device profiles](#device), [browsers](#browser-profile), and [screen sizes and resolutions](#display)</span></span>  
*   <span data-ttu-id="95c66-110">测试 [不同的地理位置设置和坐标](#geolocation)</span><span class="sxs-lookup"><span data-stu-id="95c66-110">Test different [geolocation settings and coordinates](#geolocation)</span></span>  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools 模拟面板" lightbox="./media/emulation.png":::
   <span data-ttu-id="95c66-112">Microsoft Edge DevTools **模拟** 面板</span><span class="sxs-lookup"><span data-stu-id="95c66-112">The Microsoft Edge DevTools **Emulation** panel</span></span>  
:::image-end:::  

1.  <span data-ttu-id="95c66-113">即使 **关闭并重新打开** DevTools，"持久模拟设置"按钮也保存了从默认桌面模拟设置进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="95c66-113">The **Persist Emulation settings** button saves any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span></span>  

1.  <span data-ttu-id="95c66-114">" **重置仿真设置"** 按钮将仿真设置重置回默认的桌面浏览器配置文件，并关闭 GPS 的 Microsoft Edge 用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="95c66-114">The **Reset Emulation settings** button resets your emulation settings back to the default Desktop browser profile and Microsoft Edge user agent string with GPS turned off.</span></span>  

1.  <span data-ttu-id="95c66-115">当这些选项中的任一选项从默认值更改时，" **模拟** "选项卡将显示信息性警报，以指示正在模拟浏览器行为的一些方面。</span><span class="sxs-lookup"><span data-stu-id="95c66-115">When any of these options are changed from the default, the **Emulation** tab displays an informational alert to indicate that some aspect of the behavior of your browser is being emulated.</span></span>  

## <span data-ttu-id="95c66-116">设备</span><span class="sxs-lookup"><span data-stu-id="95c66-116">Device</span></span>  

<span data-ttu-id="95c66-117">从可自动配置其他模拟选项或指定你自己的自定义配置的 Windows 设备配置文件的预设 **列表中进行选择** 。</span><span class="sxs-lookup"><span data-stu-id="95c66-117">Pick from a preset list of Windows device profiles that automatically configure the other emulation options or specify your own **Custom** configuration.</span></span>  <span data-ttu-id="95c66-118">切换回 **"默认值** "以重置所有模拟工具。</span><span class="sxs-lookup"><span data-stu-id="95c66-118">Switch back to **Default** to reset all the emulation tools.</span></span>  

## <span data-ttu-id="95c66-119">模式</span><span class="sxs-lookup"><span data-stu-id="95c66-119">Mode</span></span>  

### <span data-ttu-id="95c66-120">浏览器配置文件</span><span class="sxs-lookup"><span data-stu-id="95c66-120">Browser profile</span></span>  

<span data-ttu-id="95c66-121">模拟在 Windows Phone 设备上运行的页面的快速方法就是将**浏览器配置文件**设置更改为 Windows **Phone。**</span><span class="sxs-lookup"><span data-stu-id="95c66-121">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to **Windows Phone**.</span></span>  

#### <span data-ttu-id="95c66-122">用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="95c66-122">User agent string</span></span>  

<span data-ttu-id="95c66-123">修改用户代理字符串以模仿其他浏览器是调试仅发生在 Microsoft Edge 中的错误的良好第一步。</span><span class="sxs-lookup"><span data-stu-id="95c66-123">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span></span>  

<span data-ttu-id="95c66-124">脚本使用用户代理字符串检测所使用的浏览器。</span><span class="sxs-lookup"><span data-stu-id="95c66-124">Scripts use the user agent string to detect which browser is used.</span></span>  <span data-ttu-id="95c66-125">脚本可能是前端、后端或前端和后端。</span><span class="sxs-lookup"><span data-stu-id="95c66-125">Script may be front-end, back-end, or front-end and back-end.</span></span>  <span data-ttu-id="95c66-126">尽管代码不使用浏览器检测，但代码可能会从第三方 JavaScript 库或服务器端脚本继承它。</span><span class="sxs-lookup"><span data-stu-id="95c66-126">Although your code does not use browser detection, your code may inherit it from a third-party JavaScript library or server-side script.</span></span>  

<span data-ttu-id="95c66-127">浏览器检测的问题是，您可以使用有关浏览器功能的假设 (或更改\) 网页中的功能。</span><span class="sxs-lookup"><span data-stu-id="95c66-127">The problem with browser detection is that you may scale-back \(or change\) features in your webpage using assumptions about browser capabilities.</span></span> <span data-ttu-id="95c66-128">相反，应考虑使用功能检测来检测浏览器的功能。</span><span class="sxs-lookup"><span data-stu-id="95c66-128">Instead, you should consider using feature detection to detect the capabilities of your browser.</span></span>  <span data-ttu-id="95c66-129">由于下列情况之一，可能会发生意外行为。</span><span class="sxs-lookup"><span data-stu-id="95c66-129">Unexpected behavior may occur because of one of the following situations.</span></span>  

*   <span data-ttu-id="95c66-130">面向 Windows Internet Explorer 8的代码可能在 Microsoft Edge 中以不同方式运行。</span><span class="sxs-lookup"><span data-stu-id="95c66-130">Code targeted at Windows Internet Explorer 8 may run differently in Microsoft Edge.</span></span>  
*   <span data-ttu-id="95c66-131">浏览器应支持的功能已禁用，因为开发人员做出假设。</span><span class="sxs-lookup"><span data-stu-id="95c66-131">A feature that your browser should support is disabled, because of an assumption made by the developer.</span></span>  

<span data-ttu-id="95c66-132">如果更改用户代理字符串可清除该问题，则浏览器检测可能是原因。</span><span class="sxs-lookup"><span data-stu-id="95c66-132">If changing your user agent string clears up the problem, browser detection is likely culprit.</span></span>  

## <span data-ttu-id="95c66-133">显示</span><span class="sxs-lookup"><span data-stu-id="95c66-133">Display</span></span>  

<span data-ttu-id="95c66-134">显示模拟以在不同的屏幕大小和分辨率上预览网站。</span><span class="sxs-lookup"><span data-stu-id="95c66-134">Display emulation to preview your site on different screen sizes and resolutions.</span></span>  

*   <span data-ttu-id="95c66-135">传统桌面监视器</span><span class="sxs-lookup"><span data-stu-id="95c66-135">conventional desktop monitors</span></span>  
*   <span data-ttu-id="95c66-136">较小的移动屏幕</span><span class="sxs-lookup"><span data-stu-id="95c66-136">smaller mobile screens</span></span>  
*   <span data-ttu-id="95c66-137">较新的高分辨率显示器</span><span class="sxs-lookup"><span data-stu-id="95c66-137">newer high-resolution displays</span></span>  

<span data-ttu-id="95c66-138">调整模拟以尝试匹配要模拟的屏幕的物理尺寸。</span><span class="sxs-lookup"><span data-stu-id="95c66-138">Emulations are adapted to try to match the physical dimensions of the screens being emulated.</span></span>  <span data-ttu-id="95c66-139">模拟像素可能显示为压缩或展开。</span><span class="sxs-lookup"><span data-stu-id="95c66-139">Emulated pixels may appear compressed or expanded.</span></span> <span data-ttu-id="95c66-140">如果你需要测试 HTML 元素的像素完美位置，则不建议进行模拟。</span><span class="sxs-lookup"><span data-stu-id="95c66-140">Emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span></span>  <span data-ttu-id="95c66-141">但是，仿真适用于测试响应式设计和识别较大的元素定位问题。</span><span class="sxs-lookup"><span data-stu-id="95c66-141">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span></span>  

### <span data-ttu-id="95c66-142">Orientation</span><span class="sxs-lookup"><span data-stu-id="95c66-142">Orientation</span></span>  

<span data-ttu-id="95c66-143">从横向**或纵向模式**选择。</span><span class="sxs-lookup"><span data-stu-id="95c66-143">Choose from **Landscape** or **Portrait** mode.</span></span>  

### <span data-ttu-id="95c66-144">分辨率</span><span class="sxs-lookup"><span data-stu-id="95c66-144">Resolution</span></span>  

<span data-ttu-id="95c66-145">从常用设备分辨率的预设列表中进行选择，或指定你自己的 **自定义** 配置。 支持高达 80 英寸和 3820 x 2160 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="95c66-145">Choose from a preset list of popular device resolutions, or specify your own **Custom** config.  Resolutions of up to 80 inches and 3820 x 2160 are supported.</span></span>  

## <span data-ttu-id="95c66-146">地理位置</span><span class="sxs-lookup"><span data-stu-id="95c66-146">Geolocation</span></span>  

<span data-ttu-id="95c66-147">如果您的网站使用地理位置 [API][MdnGeolocationUsing] 提供基于位置的服务，则为了方便使用桌面，可进行以下活动。</span><span class="sxs-lookup"><span data-stu-id="95c66-147">If your website uses the [Geolocation API][MdnGeolocationUsing] to provide location-based services, the following activities are available from the convenience of your desktop.</span></span>  

*   <span data-ttu-id="95c66-148">轻松测试不同的 GPS 坐标</span><span class="sxs-lookup"><span data-stu-id="95c66-148">easily test different GPS coordinates</span></span>  
*   <span data-ttu-id="95c66-149">轻松测试不同的传感器状态</span><span class="sxs-lookup"><span data-stu-id="95c66-149">easily test different sensor states</span></span>  

<span data-ttu-id="95c66-150">这些设置会覆盖支持地理位置的设备上的任何实际 GPS 坐标和传感器状态。</span><span class="sxs-lookup"><span data-stu-id="95c66-150">The settings override any actual GPS coordinates and the sensor state on devices that support geolocation.</span></span>  

<span data-ttu-id="95c66-151">使用设备位置之前，您的网站必须请求并授予用户权限。</span><span class="sxs-lookup"><span data-stu-id="95c66-151">Your website must request and be granted permission from a user before using the device location.</span></span>  <span data-ttu-id="95c66-152">测试站点的行为方式，以及 Microsoft Edge 设置面板中的位置权限和 **位置** 权限。</span><span class="sxs-lookup"><span data-stu-id="95c66-152">Test how your site behaves with and without location permissions from the Microsoft Edge **Settings** panel.</span></span>  

<span data-ttu-id="95c66-153">**...** > **设置**  > **查看高级设置**  > **网站权限**  > **管理**</span><span class="sxs-lookup"><span data-stu-id="95c66-153">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span></span>  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="从 Microsoft Edge 设置面板管理网站权限" lightbox="./media/settings_manage_permissions.png":::
   <span data-ttu-id="95c66-155">从 Microsoft Edge 设置面板管理 **网站** 权限</span><span class="sxs-lookup"><span data-stu-id="95c66-155">Manage website permissions from the Microsoft Edge **Settings** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="95c66-156">快捷方式</span><span class="sxs-lookup"><span data-stu-id="95c66-156">Shortcuts</span></span>

| <span data-ttu-id="95c66-157">操作</span><span class="sxs-lookup"><span data-stu-id="95c66-157">Action</span></span>  | <span data-ttu-id="95c66-158">快捷方式</span><span class="sxs-lookup"><span data-stu-id="95c66-158">Shortcut</span></span>  |  
|:--- |:--- |  
| <span data-ttu-id="95c66-159">重置模拟设置</span><span class="sxs-lookup"><span data-stu-id="95c66-159">Reset Emulation settings</span></span> | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "地理位置 API |MDN"  
