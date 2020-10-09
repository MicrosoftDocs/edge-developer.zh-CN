---
description: 使用仿真面板测试不同浏览器配置文件、屏幕大小和分辨率以及 GPS 位置坐标
title: DevTools-模拟
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，设备仿真，响应式设计，地理位置，分辨率
ms.custom: seodec18
ms.openlocfilehash: 6eaa8d79cfd64473dcc52beff5659b39054e2a48
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104845"
---
# <span data-ttu-id="b75a4-104">枚举</span><span class="sxs-lookup"><span data-stu-id="b75a4-104">Emulation</span></span>  

> [!NOTE]
> <span data-ttu-id="b75a4-105">新版 Microsoft Edge 是使用 Chromium 构建的，并从版本 75 开始。</span><span class="sxs-lookup"><span data-stu-id="b75a4-105">The new Microsoft Edge is built using Chromium, and starts at version 75.</span></span>  <span data-ttu-id="b75a4-106">有关详细信息，请 [下载新的 Microsoft edge][MicrosoftNewEdge]，然后尝试新的 [Microsoft edge (Chromium) 开发人员工具][DevtoolsGuideChromium]。</span><span class="sxs-lookup"><span data-stu-id="b75a4-106">For more information, [download the new Microsoft Edge][MicrosoftNewEdge], and try out the new [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromium].</span></span>  
> 
> <span data-ttu-id="b75a4-107">若要模拟新 DevTools 中的不同设备、浏览器、屏幕大小和分辨率，请导航到 " [在 Microsoft Edge 中模拟移动设备 \" (Chromium \ ) DevTools][DevtoolsGuideChromiumDeviceMode]"。</span><span class="sxs-lookup"><span data-stu-id="b75a4-107">To emulate different devices, browsers, screen sizes, and resolutions in the new DevTools, navigate to [Emulate Mobile Devices in Microsoft Edge \(Chromium\) DevTools][DevtoolsGuideChromiumDeviceMode].</span></span>  

<span data-ttu-id="b75a4-108">**仿真**面板有助于执行下列活动。</span><span class="sxs-lookup"><span data-stu-id="b75a4-108">The **Emulation** panel helps with the following activities.</span></span>    

*   <span data-ttu-id="b75a4-109">模拟各种 [设备配置文件](#device)、 [浏览器](#browser-profile)以及 [屏幕大小和分辨率](#display)</span><span class="sxs-lookup"><span data-stu-id="b75a4-109">Simulate various [device profiles](#device), [browsers](#browser-profile), and [screen sizes and resolutions](#display)</span></span>  
*   <span data-ttu-id="b75a4-110">测试不同 [的地理位置设置和坐标](#geolocation)</span><span class="sxs-lookup"><span data-stu-id="b75a4-110">Test different [geolocation settings and coordinates](#geolocation)</span></span>  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools 仿真面板" lightbox="./media/emulation.png":::
   <span data-ttu-id="b75a4-112">Microsoft Edge DevTools **仿真** 面板</span><span class="sxs-lookup"><span data-stu-id="b75a4-112">The Microsoft Edge DevTools **Emulation** panel</span></span>  
:::image-end:::  

1.  <span data-ttu-id="b75a4-113">" **始终仿真设置** " 按钮可保存从默认桌面仿真设置所做的任何更改，即使在关闭并重新打开 DevTools 时也是如此。</span><span class="sxs-lookup"><span data-stu-id="b75a4-113">The **Persist Emulation settings** button saves any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span></span>  

1.  <span data-ttu-id="b75a4-114">" **重置仿真设置** " 按钮将你的仿真设置重置为默认桌面浏览器配置文件，并将 Microsoft Edge 用户代理字符串重置为 "GPS 关闭"。</span><span class="sxs-lookup"><span data-stu-id="b75a4-114">The **Reset Emulation settings** button resets your emulation settings back to the default Desktop browser profile and Microsoft Edge user agent string with GPS turned off.</span></span>  

1.  <span data-ttu-id="b75a4-115">如果这些选项中的任何一个更改为默认值，则 " **模拟** " 选项卡将显示信息性警报，指示浏览器行为的某些方面正在被模拟。</span><span class="sxs-lookup"><span data-stu-id="b75a4-115">When any of these options are changed from the default, the **Emulation** tab displays an informational alert to indicate that some aspect of the behavior of your browser is being emulated.</span></span>  

## <span data-ttu-id="b75a4-116">设备</span><span class="sxs-lookup"><span data-stu-id="b75a4-116">Device</span></span>  

<span data-ttu-id="b75a4-117">从自动配置其他仿真选项或指定你自己的 **自定义** 配置的 Windows 设备配置文件的预设列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="b75a4-117">Pick from a preset list of Windows device profiles that automatically configure the other emulation options or specify your own **Custom** configuration.</span></span>  <span data-ttu-id="b75a4-118">切换回 **默认** 设置以重置所有模拟工具。</span><span class="sxs-lookup"><span data-stu-id="b75a4-118">Switch back to **Default** to reset all the emulation tools.</span></span>  

## <span data-ttu-id="b75a4-119">模式</span><span class="sxs-lookup"><span data-stu-id="b75a4-119">Mode</span></span>  

### <span data-ttu-id="b75a4-120">浏览器配置文件</span><span class="sxs-lookup"><span data-stu-id="b75a4-120">Browser profile</span></span>  

<span data-ttu-id="b75a4-121">模拟在 Windows Phone 设备上运行的页面的快速方法是将 **浏览器配置文件** 设置更改为 **windows phone**。</span><span class="sxs-lookup"><span data-stu-id="b75a4-121">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to **Windows Phone**.</span></span>  

#### <span data-ttu-id="b75a4-122">用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="b75a4-122">User agent string</span></span>  

<span data-ttu-id="b75a4-123">在调试仅在 Microsoft Edge 中发生的错误时，修改您的用户代理字符串以模仿另一个浏览器是一个很好的第一步。</span><span class="sxs-lookup"><span data-stu-id="b75a4-123">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span></span>  

<span data-ttu-id="b75a4-124">脚本使用用户代理字符串检测所使用的浏览器。</span><span class="sxs-lookup"><span data-stu-id="b75a4-124">Scripts use the user agent string to detect which browser is used.</span></span>  <span data-ttu-id="b75a4-125">脚本可能是前端、后端或前端和后端。</span><span class="sxs-lookup"><span data-stu-id="b75a4-125">Script may be front-end, back-end, or front-end and back-end.</span></span>  <span data-ttu-id="b75a4-126">尽管你的代码不使用浏览器检测，你的代码可以从第三方 JavaScript 库或服务器端脚本继承它。</span><span class="sxs-lookup"><span data-stu-id="b75a4-126">Although your code does not use browser detection, your code may inherit it from a third-party JavaScript library or server-side script.</span></span>  

<span data-ttu-id="b75a4-127">浏览器检测的问题是，你可以使用有关浏览器功能的假设在你的网页中缩放-回退 (或更改 \ ) 功能。</span><span class="sxs-lookup"><span data-stu-id="b75a4-127">The problem with browser detection is that you may scale-back \(or change\) features in your webpage using assumptions about browser capabilities.</span></span> <span data-ttu-id="b75a4-128">相反，你应该考虑使用功能检测来检测浏览器的功能。</span><span class="sxs-lookup"><span data-stu-id="b75a4-128">Instead, you should consider using feature detection to detect the capabilities of your browser.</span></span>  <span data-ttu-id="b75a4-129">出现意外行为可能是由于下列情况之一。</span><span class="sxs-lookup"><span data-stu-id="b75a4-129">Unexpected behavior may occur because of one of the following situations.</span></span>  

*   <span data-ttu-id="b75a4-130">在 Windows Internet Explorer 8 上定向的代码可能在 Microsoft Edge 中以不同的方式运行。</span><span class="sxs-lookup"><span data-stu-id="b75a4-130">Code targeted at Windows Internet Explorer 8 may run differently in Microsoft Edge.</span></span>  
*   <span data-ttu-id="b75a4-131">由于开发人员的假定，您的浏览器应支持的功能已被禁用。</span><span class="sxs-lookup"><span data-stu-id="b75a4-131">A feature that your browser should support is disabled, because of an assumption made by the developer.</span></span>  

<span data-ttu-id="b75a4-132">如果更改用户代理字符串后出现问题，则可能是浏览器检测原因。</span><span class="sxs-lookup"><span data-stu-id="b75a4-132">If changing your user agent string clears up the problem, browser detection is likely culprit.</span></span>  

## <span data-ttu-id="b75a4-133">显示</span><span class="sxs-lookup"><span data-stu-id="b75a4-133">Display</span></span>  

<span data-ttu-id="b75a4-134">显示仿真以在不同的屏幕大小和分辨率下预览你的网站。</span><span class="sxs-lookup"><span data-stu-id="b75a4-134">Display emulation to preview your site on different screen sizes and resolutions.</span></span>  

*   <span data-ttu-id="b75a4-135">常规桌面监视器</span><span class="sxs-lookup"><span data-stu-id="b75a4-135">conventional desktop monitors</span></span>  
*   <span data-ttu-id="b75a4-136">较小的移动屏幕</span><span class="sxs-lookup"><span data-stu-id="b75a4-136">smaller mobile screens</span></span>  
*   <span data-ttu-id="b75a4-137">较新的高分辨率显示</span><span class="sxs-lookup"><span data-stu-id="b75a4-137">newer high-resolution displays</span></span>  

<span data-ttu-id="b75a4-138">模拟适用于尝试匹配正在仿真的屏幕的物理维度。</span><span class="sxs-lookup"><span data-stu-id="b75a4-138">Emulations are adapted to try to match the physical dimensions of the screens being emulated.</span></span>  <span data-ttu-id="b75a4-139">模拟像素可能会显示为压缩或扩展。</span><span class="sxs-lookup"><span data-stu-id="b75a4-139">Emulated pixels may appear compressed or expanded.</span></span> <span data-ttu-id="b75a4-140">如果需要测试 HTML 元素的像素完全位置，则建议不要使用模拟。</span><span class="sxs-lookup"><span data-stu-id="b75a4-140">Emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span></span>  <span data-ttu-id="b75a4-141">但是，模拟适用于测试响应式设计和确定更大的元素定位问题。</span><span class="sxs-lookup"><span data-stu-id="b75a4-141">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span></span>  

### <span data-ttu-id="b75a4-142">Orientation</span><span class="sxs-lookup"><span data-stu-id="b75a4-142">Orientation</span></span>  

<span data-ttu-id="b75a4-143">从 " **横向** " 或 " **纵向** " 模式中进行选择。</span><span class="sxs-lookup"><span data-stu-id="b75a4-143">Choose from **Landscape** or **Portrait** mode.</span></span>  

### <span data-ttu-id="b75a4-144">分辨率</span><span class="sxs-lookup"><span data-stu-id="b75a4-144">Resolution</span></span>  

<span data-ttu-id="b75a4-145">从常用设备分辨率的预设列表中选择，或指定您自己的 **自定义** 配置。 支持最高80英寸和 3820 x 2160 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="b75a4-145">Choose from a preset list of popular device resolutions, or specify your own **Custom** config.  Resolutions of up to 80 inches and 3820 x 2160 are supported.</span></span>  

## <span data-ttu-id="b75a4-146">地理位置</span><span class="sxs-lookup"><span data-stu-id="b75a4-146">Geolocation</span></span>  

<span data-ttu-id="b75a4-147">如果你的网站使用 [地理位置 API][MdnGeolocationUsing] 提供基于位置的服务，则你的桌面的便利将提供以下活动。</span><span class="sxs-lookup"><span data-stu-id="b75a4-147">If your website uses the [Geolocation API][MdnGeolocationUsing] to provide location-based services, the following activities are available from the convenience of your desktop.</span></span>  

*   <span data-ttu-id="b75a4-148">轻松测试不同的 GPS 坐标</span><span class="sxs-lookup"><span data-stu-id="b75a4-148">easily test different GPS coordinates</span></span>  
*   <span data-ttu-id="b75a4-149">轻松测试不同的传感器状态</span><span class="sxs-lookup"><span data-stu-id="b75a4-149">easily test different sensor states</span></span>  

<span data-ttu-id="b75a4-150">这些设置将覆盖支持地理位置的设备上的任何实际 GPS 坐标和传感器状态。</span><span class="sxs-lookup"><span data-stu-id="b75a4-150">The settings override any actual GPS coordinates and the sensor state on devices that support geolocation.</span></span>  

<span data-ttu-id="b75a4-151">在使用设备位置之前，您的网站必须请求并向用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="b75a4-151">Your website must request and be granted permission from a user before using the device location.</span></span>  <span data-ttu-id="b75a4-152">通过 "Microsoft Edge **设置** " 面板测试网站的行为和不带位置权限。</span><span class="sxs-lookup"><span data-stu-id="b75a4-152">Test how your site behaves with and without location permissions from the Microsoft Edge **Settings** panel.</span></span>  

<span data-ttu-id="b75a4-153">**...** > **设置**  > **查看高级设置**  > **网站权限**  > **管理**</span><span class="sxs-lookup"><span data-stu-id="b75a4-153">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span></span>  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="Microsoft Edge DevTools 仿真面板" lightbox="./media/settings_manage_permissions.png":::
   <span data-ttu-id="b75a4-155">从 Microsoft Edge **设置** 面板管理网站权限</span><span class="sxs-lookup"><span data-stu-id="b75a4-155">Manage website permissions from the Microsoft Edge **Settings** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="b75a4-156">快捷方式</span><span class="sxs-lookup"><span data-stu-id="b75a4-156">Shortcuts</span></span>

| <span data-ttu-id="b75a4-157">操作</span><span class="sxs-lookup"><span data-stu-id="b75a4-157">Action</span></span>  | <span data-ttu-id="b75a4-158">快捷方式</span><span class="sxs-lookup"><span data-stu-id="b75a4-158">Shortcut</span></span>  |  
|:--- |:--- |  
| <span data-ttu-id="b75a4-159">重置仿真设置</span><span class="sxs-lookup"><span data-stu-id="b75a4-159">Reset Emulation settings</span></span> | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "地理位置 API |MDN"  