---
description: Remote debug live content on an Android device from a Windows or macOS computer.
title: Get Started with Remote Debugging Android Devices
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: f1ed7c698f588bb4e438d1b85a0cd0d1aba42647
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993497"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="78d38-104">Get started with remote debugging Android devices</span><span class="sxs-lookup"><span data-stu-id="78d38-104">Get started with remote debugging Android devices</span></span>  

<span data-ttu-id="78d38-105">Remote debug live content on an Android device from your Windows or macOS computer.</span><span class="sxs-lookup"><span data-stu-id="78d38-105">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="78d38-106">The following tutorial page teaches you how to complete the following actions.</span><span class="sxs-lookup"><span data-stu-id="78d38-106">The following tutorial page teaches you how to complete the following actions.</span></span>  

*   <span data-ttu-id="78d38-107">Set up your Android device for remote debugging, and discover it from your development machine.</span><span class="sxs-lookup"><span data-stu-id="78d38-107">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="78d38-108">Inspect and debug live content on your Android device from your development machine.</span><span class="sxs-lookup"><span data-stu-id="78d38-108">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="78d38-109">Screencast content from your Android device onto a DevTools instance on your development machine.</span><span class="sxs-lookup"><span data-stu-id="78d38-109">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> <span data-ttu-id="78d38-110">Remote debugging the Microsoft Edge app on iOS devices is not currently supported.</span><span class="sxs-lookup"><span data-stu-id="78d38-110">Remote debugging the Microsoft Edge app on iOS devices is not currently supported.</span></span>  <span data-ttu-id="78d38-111">The following guide is specifically focused on remote debugging Microsoft Edge on Android devices.</span><span class="sxs-lookup"><span data-stu-id="78d38-111">The following guide is specifically focused on remote debugging Microsoft Edge on Android devices.</span></span>
> <span data-ttu-id="78d38-112">If you have a macOS device, follow the [Brightcove Debugging guide][BrightcoveSupportDebuggingMobileDevices] to remotely debug Microsoft Edge on an iOS device using Safari.</span><span class="sxs-lookup"><span data-stu-id="78d38-112">If you have a macOS device, follow the [Brightcove Debugging guide][BrightcoveSupportDebuggingMobileDevices] to remotely debug Microsoft Edge on an iOS device using Safari.</span></span>  <span data-ttu-id="78d38-113">For more information about the Web Inspector tool in Safari, see [Safari Web Development Tools][AppleDeveloperSafariTools].</span><span class="sxs-lookup"><span data-stu-id="78d38-113">For more information about the Web Inspector tool in Safari, see [Safari Web Development Tools][AppleDeveloperSafariTools].</span></span>  

## <span data-ttu-id="78d38-114">Step 1: Discover your Android device</span><span class="sxs-lookup"><span data-stu-id="78d38-114">Step 1: Discover your Android device</span></span>  

<span data-ttu-id="78d38-115">The workflow below works for most users.</span><span class="sxs-lookup"><span data-stu-id="78d38-115">The workflow below works for most users.</span></span>  <span data-ttu-id="78d38-116">For more help, see the [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) section.</span><span class="sxs-lookup"><span data-stu-id="78d38-116">For more help, see the [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) section.</span></span>  

1.  <span data-ttu-id="78d38-117">Open the **Developer Options** screen on your Android.</span><span class="sxs-lookup"><span data-stu-id="78d38-117">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="78d38-118">For more information, see [Configure On-Device Developer Options][AndroidDeveloperStudioDevOptions].</span><span class="sxs-lookup"><span data-stu-id="78d38-118">For more information, see [Configure On-Device Developer Options][AndroidDeveloperStudioDevOptions].</span></span>  
1.  <span data-ttu-id="78d38-119">Select **Enable USB Debugging**.</span><span class="sxs-lookup"><span data-stu-id="78d38-119">Select **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="78d38-120">On your development machine, open Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="78d38-120">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="78d38-121">Navigate to the `edge://inspect` page in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="78d38-121">Navigate to the `edge://inspect` page in Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       <span data-ttu-id="78d38-123">Figure 1.</span><span class="sxs-lookup"><span data-stu-id="78d38-123">Figure 1.</span></span>  <span data-ttu-id="78d38-124">The `edge://inspect` page in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="78d38-124">The `edge://inspect` page in Microsoft Edge</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="78d38-125">Connect your Android device directly to your development machine using a USB cable.</span><span class="sxs-lookup"><span data-stu-id="78d38-125">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="78d38-126">The first time you try to connect, you usually see prompt about DevTools detecting an unknown device.</span><span class="sxs-lookup"><span data-stu-id="78d38-126">The first time you try to connect, you usually see prompt about DevTools detecting an unknown device.</span></span>  <span data-ttu-id="78d38-127">Accept the **Allow USB Debugging** permission prompt on your Android device.</span><span class="sxs-lookup"><span data-stu-id="78d38-127">Accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       <span data-ttu-id="78d38-129">Figure 2.</span><span class="sxs-lookup"><span data-stu-id="78d38-129">Figure 2.</span></span>  <span data-ttu-id="78d38-130">The **Allow USB Debugging** permission prompt on an Android device</span><span class="sxs-lookup"><span data-stu-id="78d38-130">The **Allow USB Debugging** permission prompt on an Android device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="78d38-131">If you see the model name of your Android device, then Microsoft Edge has successfully established the connection to your device.</span><span class="sxs-lookup"><span data-stu-id="78d38-131">If you see the model name of your Android device, then Microsoft Edge has successfully established the connection to your device.</span></span>  <span data-ttu-id="78d38-132">Continue to the [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) section.</span><span class="sxs-lookup"><span data-stu-id="78d38-132">Continue to the [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) section.</span></span>  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <span data-ttu-id="78d38-133">Troubleshooting: DevTools is not detecting the Android device</span><span class="sxs-lookup"><span data-stu-id="78d38-133">Troubleshooting: DevTools is not detecting the Android device</span></span>  

<span data-ttu-id="78d38-134">Use the following tips to help you troubleshoot the correct settings for your hardware.</span><span class="sxs-lookup"><span data-stu-id="78d38-134">Use the following tips to help you troubleshoot the correct settings for your hardware.</span></span>  

*   <span data-ttu-id="78d38-135">If you are using a USB hub, try connecting your Android device directly to your development machine.</span><span class="sxs-lookup"><span data-stu-id="78d38-135">If you are using a USB hub, try connecting your Android device directly to your development machine.</span></span>  
*   <span data-ttu-id="78d38-136">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span><span class="sxs-lookup"><span data-stu-id="78d38-136">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span></span>  <span data-ttu-id="78d38-137">Complete the task while your Android and development machine screens are unlocked.</span><span class="sxs-lookup"><span data-stu-id="78d38-137">Complete the task while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="78d38-138">Make sure that your USB cable works.</span><span class="sxs-lookup"><span data-stu-id="78d38-138">Make sure that your USB cable works.</span></span>  <span data-ttu-id="78d38-139">You should be able to inspect files on your Android device from your development machine.</span><span class="sxs-lookup"><span data-stu-id="78d38-139">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="78d38-140">Use the following tips to help you verify that your software is set up correctly.</span><span class="sxs-lookup"><span data-stu-id="78d38-140">Use the following tips to help you verify that your software is set up correctly.</span></span>  

*   <span data-ttu-id="78d38-141">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span><span class="sxs-lookup"><span data-stu-id="78d38-141">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="78d38-142">For more information, see [Install OEM USB Drivers][AndroidDeveloperToolsOemUsb].</span><span class="sxs-lookup"><span data-stu-id="78d38-142">For more information, see [Install OEM USB Drivers][AndroidDeveloperToolsOemUsb].</span></span>  
*   <span data-ttu-id="78d38-143">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span><span class="sxs-lookup"><span data-stu-id="78d38-143">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span></span>  <span data-ttu-id="78d38-144">For more information, see [DevTools Devices does not detect device when plugged in][Stackoverflow21925992].</span><span class="sxs-lookup"><span data-stu-id="78d38-144">For more information, see [DevTools Devices does not detect device when plugged in][Stackoverflow21925992].</span></span>  

<span data-ttu-id="78d38-145">Use the following tips to help you troubleshoot not seeing the **Allow USB Debugging** prompt on your Android device.</span><span class="sxs-lookup"><span data-stu-id="78d38-145">Use the following tips to help you troubleshoot not seeing the **Allow USB Debugging** prompt on your Android device.</span></span>  

*   <span data-ttu-id="78d38-146">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span><span class="sxs-lookup"><span data-stu-id="78d38-146">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="78d38-147">You may not see the prompt if your Android or development machine screens are locked.</span><span class="sxs-lookup"><span data-stu-id="78d38-147">You may not see the prompt if your Android or development machine screens are locked.</span></span>  

*   <span data-ttu-id="78d38-148">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span><span class="sxs-lookup"><span data-stu-id="78d38-148">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span></span>  
*   <span data-ttu-id="78d38-149">Setting the USB mode for Android to PTP.</span><span class="sxs-lookup"><span data-stu-id="78d38-149">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="78d38-150">For more information, see [Galaxy S4 does not show Authorize USB debugging dialog box][StackexchangeAndroid101933].</span><span class="sxs-lookup"><span data-stu-id="78d38-150">For more information, see [Galaxy S4 does not show Authorize USB debugging dialog box][StackexchangeAndroid101933].</span></span>  
*   <span data-ttu-id="78d38-151">Select **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span><span class="sxs-lookup"><span data-stu-id="78d38-151">Select **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="78d38-152">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][Stackoverflow21925992] on Stack Overflow, please add your solution to the Stack Overflow question</span><span class="sxs-lookup"><span data-stu-id="78d38-152">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][Stackoverflow21925992] on Stack Overflow, please add your solution to the Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="78d38-153">!</span><span class="sxs-lookup"><span data-stu-id="78d38-153">!</span></span>  

## <span data-ttu-id="78d38-154">Step 2: Debug content on your Android device from your development machine</span><span class="sxs-lookup"><span data-stu-id="78d38-154">Step 2: Debug content on your Android device from your development machine</span></span>  

1.  <span data-ttu-id="78d38-155">Open Microsoft Edge on your Android device.</span><span class="sxs-lookup"><span data-stu-id="78d38-155">Open Microsoft Edge on your Android device.</span></span>  
1.  <span data-ttu-id="78d38-156">From the `edge://inspect` page, you see the model name of your Android device, followed by the device serial number.</span><span class="sxs-lookup"><span data-stu-id="78d38-156">From the `edge://inspect` page, you see the model name of your Android device, followed by the device serial number.</span></span>  <span data-ttu-id="78d38-157">Below that, you should see the version of Microsoft Edge running on the device, with the version number in parentheses.</span><span class="sxs-lookup"><span data-stu-id="78d38-157">Below that, you should see the version of Microsoft Edge running on the device, with the version number in parentheses.</span></span>  <span data-ttu-id="78d38-158">Each open Microsoft Edge tab gets a unique section.</span><span class="sxs-lookup"><span data-stu-id="78d38-158">Each open Microsoft Edge tab gets a unique section.</span></span>  <span data-ttu-id="78d38-159">You may interact with that tab from a section.</span><span class="sxs-lookup"><span data-stu-id="78d38-159">You may interact with that tab from a section.</span></span>  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       <span data-ttu-id="78d38-161">Figure 3.</span><span class="sxs-lookup"><span data-stu-id="78d38-161">Figure 3.</span></span>  <span data-ttu-id="78d38-162">A connected remote device</span><span class="sxs-lookup"><span data-stu-id="78d38-162">A connected remote device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="78d38-163">In the **Open tab with url** text box, enter a URL and then select **Open**.</span><span class="sxs-lookup"><span data-stu-id="78d38-163">In the **Open tab with url** text box, enter a URL and then select **Open**.</span></span>  <span data-ttu-id="78d38-164">The page opens in a new tab on your Android device.</span><span class="sxs-lookup"><span data-stu-id="78d38-164">The page opens in a new tab on your Android device.</span></span>  
1.  <span data-ttu-id="78d38-165">Select **inspect** next to the URL that you just opened.</span><span class="sxs-lookup"><span data-stu-id="78d38-165">Select **inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="78d38-166">A new DevTools instance opens.</span><span class="sxs-lookup"><span data-stu-id="78d38-166">A new DevTools instance opens.</span></span>  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <span data-ttu-id="78d38-167">More actions: focus, reload, or close a tab</span><span class="sxs-lookup"><span data-stu-id="78d38-167">More actions: focus, reload, or close a tab</span></span>  

<span data-ttu-id="78d38-168">Select **focus tab**, **reload**, or **close** next to the tab that you want to focus, reload, or close.</span><span class="sxs-lookup"><span data-stu-id="78d38-168">Select **focus tab**, **reload**, or **close** next to the tab that you want to focus, reload, or close.</span></span>  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   <span data-ttu-id="78d38-170">Figure 4.</span><span class="sxs-lookup"><span data-stu-id="78d38-170">Figure 4.</span></span>  <span data-ttu-id="78d38-171">The buttons for focusing, reloading, or closing a tab</span><span class="sxs-lookup"><span data-stu-id="78d38-171">The buttons for focusing, reloading, or closing a tab</span></span>  
:::image-end:::  

### <span data-ttu-id="78d38-172">Inspect elements</span><span class="sxs-lookup"><span data-stu-id="78d38-172">Inspect elements</span></span>  

<span data-ttu-id="78d38-173">Go to the **Elements** panel of your DevTools instance, and hover over an element to highlight it in the viewport of your Android device.</span><span class="sxs-lookup"><span data-stu-id="78d38-173">Go to the **Elements** panel of your DevTools instance, and hover over an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="78d38-174">You may also select an element on your Android device screen to select it in the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="78d38-174">You may also select an element on your Android device screen to select it in the **Elements** panel.</span></span>  <span data-ttu-id="78d38-175">Select **Select Element** ![Select Element][ImageSelectElementIcon] icon on your DevTools instance, and then select the element on your Android device screen.</span><span class="sxs-lookup"><span data-stu-id="78d38-175">Select **Select Element** ![Select Element][ImageSelectElementIcon] icon on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="78d38-176">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span><span class="sxs-lookup"><span data-stu-id="78d38-176">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span></span>  

### <span data-ttu-id="78d38-177">Screencast your Android screen to your development machine</span><span class="sxs-lookup"><span data-stu-id="78d38-177">Screencast your Android screen to your development machine</span></span>  

<span data-ttu-id="78d38-178">Select **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] icon to view the content of your Android device in your DevTools instance.</span><span class="sxs-lookup"><span data-stu-id="78d38-178">Select **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] icon to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="78d38-179">You are able to interact with the screencast in the following ways.</span><span class="sxs-lookup"><span data-stu-id="78d38-179">You are able to interact with the screencast in the following ways.</span></span>  

*   <span data-ttu-id="78d38-180">Clicks are translated into taps, firing proper touch events on the device.</span><span class="sxs-lookup"><span data-stu-id="78d38-180">Clicks are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="78d38-181">Keystrokes on your computer are sent to the device.</span><span class="sxs-lookup"><span data-stu-id="78d38-181">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="78d38-182">To simulate a pinch gesture, hold `Shift` while dragging.</span><span class="sxs-lookup"><span data-stu-id="78d38-182">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="78d38-183">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span><span class="sxs-lookup"><span data-stu-id="78d38-183">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="78d38-184">Use the following tips to help you screencast.</span><span class="sxs-lookup"><span data-stu-id="78d38-184">Use the following tips to help you screencast.</span></span>  
> 
> *   <span data-ttu-id="78d38-185">Screencasts only display page content.</span><span class="sxs-lookup"><span data-stu-id="78d38-185">Screencasts only display page content.</span></span>  <span data-ttu-id="78d38-186">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span><span class="sxs-lookup"><span data-stu-id="78d38-186">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
> *   <span data-ttu-id="78d38-187">Screencasts negatively affect frame rates.</span><span class="sxs-lookup"><span data-stu-id="78d38-187">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="78d38-188">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span><span class="sxs-lookup"><span data-stu-id="78d38-188">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
> *   <span data-ttu-id="78d38-189">If your Android device screen locks, the content of your screencast disappears.</span><span class="sxs-lookup"><span data-stu-id="78d38-189">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="78d38-190">Unlock your Android device screen to automatically resume the screencast.</span><span class="sxs-lookup"><span data-stu-id="78d38-190">Unlock your Android device screen to automatically resume the screencast.</span></span>  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "Configure on-device developer options | Android Developer"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "Install OEM USB drivers | Android Developers"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web Development Tools | Apple Developer"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "Debugging on Mobile Devices | Brightcove Support"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb - Android Enthusiast Stack Exchange"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "DevTools Devices does not detect device when plugged in - Stack Overflow"  

> [!NOTE]
> <span data-ttu-id="78d38-197">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="78d38-197">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="78d38-198">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="78d38-198">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="78d38-200">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="78d38-200">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
