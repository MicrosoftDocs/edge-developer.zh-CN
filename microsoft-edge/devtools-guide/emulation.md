---
description: 使用仿真面板测试不同浏览器配置文件、屏幕大小和分辨率以及 GPS 位置坐标
title: DevTools-模拟
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，设备仿真，响应式设计，地理位置，分辨率
ms.custom: seodec18
ms.openlocfilehash: d66646600aeaac279acaf622527f829c69f33286
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563503"
---
# <span data-ttu-id="f693a-104">枚举</span><span class="sxs-lookup"><span data-stu-id="f693a-104">Emulation</span></span>

<span data-ttu-id="f693a-105">*仿真*面板可帮助你：</span><span class="sxs-lookup"><span data-stu-id="f693a-105">The *Emulation* panel helps you to:</span></span>
 - <span data-ttu-id="f693a-106">模拟各种 [设备配置文件](#device)、 [浏览器](#browser-profile)、 [屏幕大小和分辨率](#display)</span><span class="sxs-lookup"><span data-stu-id="f693a-106">Simulate various [device profiles](#device), [browsers](#browser-profile), [screen sizes and resolutions](#display)</span></span>
 - <span data-ttu-id="f693a-107">测试不同 [的地理位置设置和坐标](#geolocation)</span><span class="sxs-lookup"><span data-stu-id="f693a-107">Test different [geolocation settings and coordinates](#geolocation)</span></span>

![Microsoft Edge DevTools 仿真面板](./media/emulation.png)

1. <span data-ttu-id="f693a-109">即使在关闭并重新打开 DevTools 时，" **始终仿真设置** " 按钮也会保存你从默认桌面仿真设置所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="f693a-109">The **Persist Emulation settings** button will save any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span></span> 

2. <span data-ttu-id="f693a-110">" **重置仿真设置** " 按钮会将你的仿真设置重置为默认 *桌面* 浏览器配置文件，并将 Microsoft Edge 用户代理字符串重置为 "GPS 关闭"。</span><span class="sxs-lookup"><span data-stu-id="f693a-110">The **Reset Emulation settings** button will reset your emulation settings back to the default *Desktop* browser profile and Microsoft Edge user agent string with GPS turned off.</span></span>

3. <span data-ttu-id="f693a-111">如果这些选项中的任何一个更改为默认值，则 " **模拟** " 选项卡将显示信息性警报，指示浏览器行为的某些方面已被模拟。</span><span class="sxs-lookup"><span data-stu-id="f693a-111">When any of these options are changed from the default, the **Emulation** tab will show an informational alert to indicate that some aspect of your browser's behavior is being emulated.</span></span>

## <span data-ttu-id="f693a-112">设备</span><span class="sxs-lookup"><span data-stu-id="f693a-112">Device</span></span>

<span data-ttu-id="f693a-113">从自动配置其他仿真选项或指定你自己的 *自定义* Configuation 的 Windows 设备配置文件的预设列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="f693a-113">Pick from a preset list of Windows device profiles which  automatically configure the other emulation options or specify your own *Custom* configuation.</span></span> <span data-ttu-id="f693a-114">切换回 *默认* 设置以重置所有模拟工具。</span><span class="sxs-lookup"><span data-stu-id="f693a-114">Switch back to *Default* to reset all the emulation tools.</span></span>

## <span data-ttu-id="f693a-115">模式</span><span class="sxs-lookup"><span data-stu-id="f693a-115">Mode</span></span>

### <span data-ttu-id="f693a-116">浏览器配置文件</span><span class="sxs-lookup"><span data-stu-id="f693a-116">Browser profile</span></span>
<span data-ttu-id="f693a-117">模拟在 Windows Phone 设备上运行的页面的快速方法是将 **浏览器配置文件** 设置更改为 *windows phone*。</span><span class="sxs-lookup"><span data-stu-id="f693a-117">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to *Windows Phone*.</span></span>

#### <span data-ttu-id="f693a-118">用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="f693a-118">User agent string</span></span>

<span data-ttu-id="f693a-119">在调试仅在 Microsoft Edge 中发生的错误时，修改您的用户代理字符串以模仿另一个浏览器是一个很好的第一步。</span><span class="sxs-lookup"><span data-stu-id="f693a-119">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span></span> 

<span data-ttu-id="f693a-120">前端和/或后端脚本有时使用用户代理字符串检测你正在使用的浏览器。</span><span class="sxs-lookup"><span data-stu-id="f693a-120">Front end and/or back end scripts sometimes use the user agent string  to detect which browser you're using.</span></span> <span data-ttu-id="f693a-121">即使在您自己的代码中不使用浏览器检测，您也可以使用第三方 JavaScript 库或服务器端脚本执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f693a-121">And even when you're not using browser detection in your own code, you may be using a third-party JavaScript library or server-side script that does.</span></span>

<span data-ttu-id="f693a-122">浏览器检测的问题是，它通常用于根据你的浏览器编写脚本所认为的开发人员可以执行的操作来缩放或更改网页中的功能，而不是检测你的浏览器可以使用功能检测实际执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f693a-122">The problem with browser detection is that it's often used to scale back or change the features in a webpage based on what the developer writing the script thinks your browser can do, rather than detecting what your browser can actually do using feature detection.</span></span> <span data-ttu-id="f693a-123">这可能会导致意外行为，因为面向 Windows Internet Explorer 8 的代码在 Microsoft Edge 中的运行方式非常不同;或者，你的浏览器完全支持支持的功能可能会因开发人员的假设而被禁用。</span><span class="sxs-lookup"><span data-stu-id="f693a-123">This can cause unexpected behavior, because code targeted at Windows Internet Explorer 8 can run very differently in Microsoft Edge; or a feature your browser is perfectly capable of supporting might be disabled because of an assumption made by the developer.</span></span>

<span data-ttu-id="f693a-124">如果更改用户代理字符串后出现问题，则可能是浏览器检测原因。</span><span class="sxs-lookup"><span data-stu-id="f693a-124">If changing your user agent string clears up the problem, browser detection is likely culprit.</span></span>

## <span data-ttu-id="f693a-125">显示</span><span class="sxs-lookup"><span data-stu-id="f693a-125">Display</span></span>

<span data-ttu-id="f693a-126">"显示仿真" 使你能够以不同的屏幕大小和分辨率预览你的网站：从常规桌面监视器到较小的移动屏幕或较新的高分辨率显示。</span><span class="sxs-lookup"><span data-stu-id="f693a-126">Display emulation lets you preview your site on different screen sizes and resolutions: from conventional desktop monitors to smaller mobile screens or newer high-resolution displays.</span></span>

<span data-ttu-id="f693a-127">模拟适用于尝试匹配正在仿真的屏幕的物理尺寸。</span><span class="sxs-lookup"><span data-stu-id="f693a-127">Emulations are adapted to try and match the physical dimensions of the screens being emulated.</span></span> <span data-ttu-id="f693a-128">模拟像素可能会显示为压缩或扩展，如果需要测试 HTML 元素的像素完全位置，则建议不要使用模拟。</span><span class="sxs-lookup"><span data-stu-id="f693a-128">Emulated pixels might appear compressed or expanded, and emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span></span> <span data-ttu-id="f693a-129">但是，模拟适用于测试响应式设计和确定更大的元素定位问题。</span><span class="sxs-lookup"><span data-stu-id="f693a-129">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span></span>

### <span data-ttu-id="f693a-130">Orientation</span><span class="sxs-lookup"><span data-stu-id="f693a-130">Orientation</span></span>

<span data-ttu-id="f693a-131">从 " *横向* " 或 " *纵向* " 模式中进行选择。</span><span class="sxs-lookup"><span data-stu-id="f693a-131">Choose from *Landscape* or *Portrait* mode.</span></span>

### <span data-ttu-id="f693a-132">分辨率</span><span class="sxs-lookup"><span data-stu-id="f693a-132">Resolution</span></span>

<span data-ttu-id="f693a-133">从常用设备分辨率的预设列表中选择，或指定您自己的 *自定义* 配置。支持最高80英寸和 3820 x 2160 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="f693a-133">Choose from a preset list of popular device resolutions, or specify your own *Custom* config. Resolutions of up to 80 inches and 3820 x 2160 are supported.</span></span>

## <span data-ttu-id="f693a-134">地理位置</span><span class="sxs-lookup"><span data-stu-id="f693a-134">Geolocation</span></span>

<span data-ttu-id="f693a-135">如果您的网站使用 [地理位置 API](https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation) 提供基于位置的服务，您可以轻松地从桌面的便利测试不同的 GPS 坐标和传感器状态。</span><span class="sxs-lookup"><span data-stu-id="f693a-135">If your site uses the [Geolocation API](https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation) to provide location-based services, you can easily test different GPS coordinates and sensor states from the convenience of your desktop.</span></span> <span data-ttu-id="f693a-136">这些设置将覆盖支持地理位置的计算机上的任何实际 GPS 坐标和传感器状态。</span><span class="sxs-lookup"><span data-stu-id="f693a-136">These settings will override any actual GPS coordinates and the sensor state on machines that support geolocation.</span></span> 

<span data-ttu-id="f693a-137">与 web 上的个人数据的任何使用一样，你的用户首先需要授予你的网站使用其位置的权限。</span><span class="sxs-lookup"><span data-stu-id="f693a-137">As with any usage of personal data on the web, your users will first need to grant your site permission to use their location.</span></span> <span data-ttu-id="f693a-138">你可以通过 Microsoft Edge *设置* 面板测试网站的行为和不包含位置权限：</span><span class="sxs-lookup"><span data-stu-id="f693a-138">You can test how your site behaves with and without location permissions from the Microsoft Edge *Settings* panel:</span></span>

<span data-ttu-id="f693a-139">**...** > **设置**  > **查看高级设置**  > **网站权限**  > **管理**</span><span class="sxs-lookup"><span data-stu-id="f693a-139">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span></span>

![从 Microsoft Edge 设置面板管理网站权限](./media/settings_manage_permissions.png)

## <span data-ttu-id="f693a-141">快捷方式</span><span class="sxs-lookup"><span data-stu-id="f693a-141">Shortcuts</span></span>

| <span data-ttu-id="f693a-142">操作</span><span class="sxs-lookup"><span data-stu-id="f693a-142">Action</span></span>                   | <span data-ttu-id="f693a-143">快捷方式</span><span class="sxs-lookup"><span data-stu-id="f693a-143">Shortcut</span></span>               |
|:-------------------------|:-----------------------|
| <span data-ttu-id="f693a-144">重置仿真设置</span><span class="sxs-lookup"><span data-stu-id="f693a-144">Reset Emulation settings</span></span> | `CTRL` + `SHIFT` + `L` |
