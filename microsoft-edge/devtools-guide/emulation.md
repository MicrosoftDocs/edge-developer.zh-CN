---
description: Use the Emulation panel to test different browser profiles, screen sizes and resolutions, and GPS location coordinates
title: DevTools - Emulation
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, device emulation, responsive design, geolocation, resolution
ms.custom: seodec18
ms.openlocfilehash: d66646600aeaac279acaf622527f829c69f33286
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563503"
---
# <span data-ttu-id="b9c81-104">Emulation</span><span class="sxs-lookup"><span data-stu-id="b9c81-104">Emulation</span></span>

<span data-ttu-id="b9c81-105">The *Emulation* panel helps you to:</span><span class="sxs-lookup"><span data-stu-id="b9c81-105">The *Emulation* panel helps you to:</span></span>
 - <span data-ttu-id="b9c81-106">Simulate various [device profiles](#device), [browsers](#browser-profile), [screen sizes and resolutions](#display)</span><span class="sxs-lookup"><span data-stu-id="b9c81-106">Simulate various [device profiles](#device), [browsers](#browser-profile), [screen sizes and resolutions](#display)</span></span>
 - <span data-ttu-id="b9c81-107">Test different [geolocation settings and coordinates](#geolocation)</span><span class="sxs-lookup"><span data-stu-id="b9c81-107">Test different [geolocation settings and coordinates](#geolocation)</span></span>

![The Microsoft Edge DevTools Emulation panel](./media/emulation.png)

1. <span data-ttu-id="b9c81-109">The **Persist Emulation settings** button will save any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span><span class="sxs-lookup"><span data-stu-id="b9c81-109">The **Persist Emulation settings** button will save any changes you made from the default desktop emulation settings, even when you close and reopen the DevTools.</span></span> 

2. <span data-ttu-id="b9c81-110">The **Reset Emulation settings** button will reset your emulation settings back to the default *Desktop* browser profile and Microsoft Edge user agent string with GPS turned off.</span><span class="sxs-lookup"><span data-stu-id="b9c81-110">The **Reset Emulation settings** button will reset your emulation settings back to the default *Desktop* browser profile and Microsoft Edge user agent string with GPS turned off.</span></span>

3. <span data-ttu-id="b9c81-111">When any of these options are changed from the default, the **Emulation** tab will show an informational alert to indicate that some aspect of your browser's behavior is being emulated.</span><span class="sxs-lookup"><span data-stu-id="b9c81-111">When any of these options are changed from the default, the **Emulation** tab will show an informational alert to indicate that some aspect of your browser's behavior is being emulated.</span></span>

## <span data-ttu-id="b9c81-112">Device</span><span class="sxs-lookup"><span data-stu-id="b9c81-112">Device</span></span>

<span data-ttu-id="b9c81-113">Pick from a preset list of Windows device profiles which  automatically configure the other emulation options or specify your own *Custom* configuation.</span><span class="sxs-lookup"><span data-stu-id="b9c81-113">Pick from a preset list of Windows device profiles which  automatically configure the other emulation options or specify your own *Custom* configuation.</span></span> <span data-ttu-id="b9c81-114">Switch back to *Default* to reset all the emulation tools.</span><span class="sxs-lookup"><span data-stu-id="b9c81-114">Switch back to *Default* to reset all the emulation tools.</span></span>

## <span data-ttu-id="b9c81-115">Mode</span><span class="sxs-lookup"><span data-stu-id="b9c81-115">Mode</span></span>

### <span data-ttu-id="b9c81-116">Browser profile</span><span class="sxs-lookup"><span data-stu-id="b9c81-116">Browser profile</span></span>
<span data-ttu-id="b9c81-117">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to *Windows Phone*.</span><span class="sxs-lookup"><span data-stu-id="b9c81-117">A quick way to simulate your page running on a Windows Phone device is to change the **Browser profile** setting to *Windows Phone*.</span></span>

#### <span data-ttu-id="b9c81-118">User agent string</span><span class="sxs-lookup"><span data-stu-id="b9c81-118">User agent string</span></span>

<span data-ttu-id="b9c81-119">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="b9c81-119">Modifying your user agent string to mimic another browser is a good first step in debugging errors that are only happening in Microsoft Edge.</span></span> 

<span data-ttu-id="b9c81-120">Front end and/or back end scripts sometimes use the user agent string  to detect which browser you're using.</span><span class="sxs-lookup"><span data-stu-id="b9c81-120">Front end and/or back end scripts sometimes use the user agent string  to detect which browser you're using.</span></span> <span data-ttu-id="b9c81-121">And even when you're not using browser detection in your own code, you may be using a third-party JavaScript library or server-side script that does.</span><span class="sxs-lookup"><span data-stu-id="b9c81-121">And even when you're not using browser detection in your own code, you may be using a third-party JavaScript library or server-side script that does.</span></span>

<span data-ttu-id="b9c81-122">The problem with browser detection is that it's often used to scale back or change the features in a webpage based on what the developer writing the script thinks your browser can do, rather than detecting what your browser can actually do using feature detection.</span><span class="sxs-lookup"><span data-stu-id="b9c81-122">The problem with browser detection is that it's often used to scale back or change the features in a webpage based on what the developer writing the script thinks your browser can do, rather than detecting what your browser can actually do using feature detection.</span></span> <span data-ttu-id="b9c81-123">This can cause unexpected behavior, because code targeted at Windows Internet Explorer 8 can run very differently in Microsoft Edge; or a feature your browser is perfectly capable of supporting might be disabled because of an assumption made by the developer.</span><span class="sxs-lookup"><span data-stu-id="b9c81-123">This can cause unexpected behavior, because code targeted at Windows Internet Explorer 8 can run very differently in Microsoft Edge; or a feature your browser is perfectly capable of supporting might be disabled because of an assumption made by the developer.</span></span>

<span data-ttu-id="b9c81-124">If changing your user agent string clears up the problem, browser detection is likely culprit.</span><span class="sxs-lookup"><span data-stu-id="b9c81-124">If changing your user agent string clears up the problem, browser detection is likely culprit.</span></span>

## <span data-ttu-id="b9c81-125">Display</span><span class="sxs-lookup"><span data-stu-id="b9c81-125">Display</span></span>

<span data-ttu-id="b9c81-126">Display emulation lets you preview your site on different screen sizes and resolutions: from conventional desktop monitors to smaller mobile screens or newer high-resolution displays.</span><span class="sxs-lookup"><span data-stu-id="b9c81-126">Display emulation lets you preview your site on different screen sizes and resolutions: from conventional desktop monitors to smaller mobile screens or newer high-resolution displays.</span></span>

<span data-ttu-id="b9c81-127">Emulations are adapted to try and match the physical dimensions of the screens being emulated.</span><span class="sxs-lookup"><span data-stu-id="b9c81-127">Emulations are adapted to try and match the physical dimensions of the screens being emulated.</span></span> <span data-ttu-id="b9c81-128">Emulated pixels might appear compressed or expanded, and emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span><span class="sxs-lookup"><span data-stu-id="b9c81-128">Emulated pixels might appear compressed or expanded, and emulation is not recommended if you need to test pixel-perfect positioning of HTML elements.</span></span> <span data-ttu-id="b9c81-129">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span><span class="sxs-lookup"><span data-stu-id="b9c81-129">Emulation is, however, good for testing responsive designs and identifying larger element positioning issues.</span></span>

### <span data-ttu-id="b9c81-130">Orientation</span><span class="sxs-lookup"><span data-stu-id="b9c81-130">Orientation</span></span>

<span data-ttu-id="b9c81-131">Choose from *Landscape* or *Portrait* mode.</span><span class="sxs-lookup"><span data-stu-id="b9c81-131">Choose from *Landscape* or *Portrait* mode.</span></span>

### <span data-ttu-id="b9c81-132">Resolution</span><span class="sxs-lookup"><span data-stu-id="b9c81-132">Resolution</span></span>

<span data-ttu-id="b9c81-133">Choose from a preset list of popular device resolutions, or specify your own *Custom* config. Resolutions of up to 80 inches and 3820 x 2160 are supported.</span><span class="sxs-lookup"><span data-stu-id="b9c81-133">Choose from a preset list of popular device resolutions, or specify your own *Custom* config. Resolutions of up to 80 inches and 3820 x 2160 are supported.</span></span>

## <span data-ttu-id="b9c81-134">Geolocation</span><span class="sxs-lookup"><span data-stu-id="b9c81-134">Geolocation</span></span>

<span data-ttu-id="b9c81-135">If your site uses the [Geolocation API](https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation) to provide location-based services, you can easily test different GPS coordinates and sensor states from the convenience of your desktop.</span><span class="sxs-lookup"><span data-stu-id="b9c81-135">If your site uses the [Geolocation API](https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation) to provide location-based services, you can easily test different GPS coordinates and sensor states from the convenience of your desktop.</span></span> <span data-ttu-id="b9c81-136">These settings will override any actual GPS coordinates and the sensor state on machines that support geolocation.</span><span class="sxs-lookup"><span data-stu-id="b9c81-136">These settings will override any actual GPS coordinates and the sensor state on machines that support geolocation.</span></span> 

<span data-ttu-id="b9c81-137">As with any usage of personal data on the web, your users will first need to grant your site permission to use their location.</span><span class="sxs-lookup"><span data-stu-id="b9c81-137">As with any usage of personal data on the web, your users will first need to grant your site permission to use their location.</span></span> <span data-ttu-id="b9c81-138">You can test how your site behaves with and without location permissions from the Microsoft Edge *Settings* panel:</span><span class="sxs-lookup"><span data-stu-id="b9c81-138">You can test how your site behaves with and without location permissions from the Microsoft Edge *Settings* panel:</span></span>

<span data-ttu-id="b9c81-139">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span><span class="sxs-lookup"><span data-stu-id="b9c81-139">**...** > **Settings** > **View advanced settings** > **Website permissions** > **Manage**</span></span>

![Manage website permissions from the Microsoft Edge Settings panel](./media/settings_manage_permissions.png)

## <span data-ttu-id="b9c81-141">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="b9c81-141">Shortcuts</span></span>

| <span data-ttu-id="b9c81-142">Action</span><span class="sxs-lookup"><span data-stu-id="b9c81-142">Action</span></span>                   | <span data-ttu-id="b9c81-143">Shortcut</span><span class="sxs-lookup"><span data-stu-id="b9c81-143">Shortcut</span></span>               |
|:-------------------------|:-----------------------|
| <span data-ttu-id="b9c81-144">Reset Emulation settings</span><span class="sxs-lookup"><span data-stu-id="b9c81-144">Reset Emulation settings</span></span> | `CTRL` + `SHIFT` + `L` |
