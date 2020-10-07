---
description: Your job does not end with ensuring your site runs great across Microsoft Edge and Android.  Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.
title: Emulate and Test Other Browsers
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 1b76447aa86837abac88bc4727eb7f4ee082342a
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992909"
---
<!-- Copyright Meggin Kearney and Paul Bakaus

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# <span data-ttu-id="4ee99-105">Emulate and test other browsers</span><span class="sxs-lookup"><span data-stu-id="4ee99-105">Emulate and test other browsers</span></span>   




<span data-ttu-id="4ee99-106">Your job does not end with ensuring your site runs great across Microsoft Edge and Android.</span><span class="sxs-lookup"><span data-stu-id="4ee99-106">Your job does not end with ensuring your site runs great across Microsoft Edge and Android.</span></span>  <span data-ttu-id="4ee99-107">Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.</span><span class="sxs-lookup"><span data-stu-id="4ee99-107">Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.</span></span>  

### <span data-ttu-id="4ee99-108">Summary</span><span class="sxs-lookup"><span data-stu-id="4ee99-108">Summary</span></span>  

*   <span data-ttu-id="4ee99-109">When you do not have a particular device, or want to do a spot check on something, the best option is to emulate the device right inside your browser.</span><span class="sxs-lookup"><span data-stu-id="4ee99-109">When you do not have a particular device, or want to do a spot check on something, the best option is to emulate the device right inside your browser.</span></span>  
*   <span data-ttu-id="4ee99-110">Device emulators and simulators enable you to mimic your development site on a range of devices from your workstation.</span><span class="sxs-lookup"><span data-stu-id="4ee99-110">Device emulators and simulators enable you to mimic your development site on a range of devices from your workstation.</span></span>  
*   <span data-ttu-id="4ee99-111">Cloud-based emulators enable you to automate unit tests for your site across different platforms.</span><span class="sxs-lookup"><span data-stu-id="4ee99-111">Cloud-based emulators enable you to automate unit tests for your site across different platforms.</span></span>  

## <span data-ttu-id="4ee99-112">Browser emulators</span><span class="sxs-lookup"><span data-stu-id="4ee99-112">Browser emulators</span></span>  

<span data-ttu-id="4ee99-113">Browser emulators are great for testing the responsiveness of a site, but each does not emulate differences in API, CSS support, and certain behaviors that you see on a mobile browser.</span><span class="sxs-lookup"><span data-stu-id="4ee99-113">Browser emulators are great for testing the responsiveness of a site, but each does not emulate differences in API, CSS support, and certain behaviors that you see on a mobile browser.</span></span>  <span data-ttu-id="4ee99-114">Test your site on browsers running on real devices to be certain everything behaves as expected.</span><span class="sxs-lookup"><span data-stu-id="4ee99-114">Test your site on browsers running on real devices to be certain everything behaves as expected.</span></span>  

### <span data-ttu-id="4ee99-115">Firefox Responsive Design View</span><span class="sxs-lookup"><span data-stu-id="4ee99-115">Firefox Responsive Design View</span></span>  

<span data-ttu-id="4ee99-116">Firefox has a [responsive design view][MDNResponsiveDesignMode] that encourages you to stop thinking in terms of specific devices and instead explore how your design changes at common screen sizes or your own size by dragging the edges.</span><span class="sxs-lookup"><span data-stu-id="4ee99-116">Firefox has a [responsive design view][MDNResponsiveDesignMode] that encourages you to stop thinking in terms of specific devices and instead explore how your design changes at common screen sizes or your own size by dragging the edges.</span></span>  

### <span data-ttu-id="4ee99-117">EdgeHTML emulation</span><span class="sxs-lookup"><span data-stu-id="4ee99-117">EdgeHTML emulation</span></span>  

<span data-ttu-id="4ee99-118">To emulate Windows Phones, use the Microsoft Edge \(EdgeHTML\) [built-in emulation][DevToolsEdgeHtmlEmulation].</span><span class="sxs-lookup"><span data-stu-id="4ee99-118">To emulate Windows Phones, use the Microsoft Edge \(EdgeHTML\) [built-in emulation][DevToolsEdgeHtmlEmulation].</span></span>  

<span data-ttu-id="4ee99-119">Use [IE 11 Emulation][Ie11DevToolsEmulation] to simulate how your page may look in older versions of Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4ee99-119">Use [IE 11 Emulation][Ie11DevToolsEmulation] to simulate how your page may look in older versions of Internet Explorer.</span></span>  

## <span data-ttu-id="4ee99-120">Device emulators and simulators</span><span class="sxs-lookup"><span data-stu-id="4ee99-120">Device emulators and simulators</span></span>  

<span data-ttu-id="4ee99-121">Device simulators and emulators simulate not just the browser environment but the entire device.</span><span class="sxs-lookup"><span data-stu-id="4ee99-121">Device simulators and emulators simulate not just the browser environment but the entire device.</span></span>  <span data-ttu-id="4ee99-122">Each are useful to test things that require OS integration, for example form input with virtual keyboards.</span><span class="sxs-lookup"><span data-stu-id="4ee99-122">Each are useful to test things that require OS integration, for example form input with virtual keyboards.</span></span>  

### <span data-ttu-id="4ee99-123">Android emulator</span><span class="sxs-lookup"><span data-stu-id="4ee99-123">Android emulator</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="4ee99-124">At the moment, there is no way to install Microsoft Edge on an Android emulator.</span><span class="sxs-lookup"><span data-stu-id="4ee99-124">At the moment, there is no way to install Microsoft Edge on an Android emulator.</span></span>  <span data-ttu-id="4ee99-125">However, you may use the Android Browser, the Chromium Content Shell, and Firefox for Android which we review later in this guide.</span><span class="sxs-lookup"><span data-stu-id="4ee99-125">However, you may use the Android Browser, the Chromium Content Shell, and Firefox for Android which we review later in this guide.</span></span>  <span data-ttu-id="4ee99-126">Chromium Content Shell runs the same Chromium rendering engine as Microsoft Edge, but comes without any of the browser specific features.</span><span class="sxs-lookup"><span data-stu-id="4ee99-126">Chromium Content Shell runs the same Chromium rendering engine as Microsoft Edge, but comes without any of the browser specific features.</span></span>  

<span data-ttu-id="4ee99-127">The Android emulator comes with the Android SDK which you need to download as part of [Android Studio][AndroidStudioDownload].</span><span class="sxs-lookup"><span data-stu-id="4ee99-127">The Android emulator comes with the Android SDK which you need to download as part of [Android Studio][AndroidStudioDownload].</span></span>  <span data-ttu-id="4ee99-128">Then follow the instructions to [set up a virtual device][AndroidStudioCreateManageVirtualDevices] and [start the emulator][AndroidStudioRunAppsAndroidEmulator].</span><span class="sxs-lookup"><span data-stu-id="4ee99-128">Then follow the instructions to [set up a virtual device][AndroidStudioCreateManageVirtualDevices] and [start the emulator][AndroidStudioRunAppsAndroidEmulator].</span></span>  
<span data-ttu-id="4ee99-129">Once your emulator is booted, click on the Browser icon, and test your site on the old Stock Browser for Android.</span><span class="sxs-lookup"><span data-stu-id="4ee99-129">Once your emulator is booted, click on the Browser icon, and test your site on the old Stock Browser for Android.</span></span>  

#### <span data-ttu-id="4ee99-130">Chromium content shell on Android</span><span class="sxs-lookup"><span data-stu-id="4ee99-130">Chromium content shell on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

<span data-ttu-id="4ee99-131">To install the Chromium Content Shell for Android, leave your emulator running and run the following command.</span><span class="sxs-lookup"><span data-stu-id="4ee99-131">To install the Chromium Content Shell for Android, leave your emulator running and run the following command.</span></span>  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

<span data-ttu-id="4ee99-132">Now you are able to test your site with the Chromium Content Shell.</span><span class="sxs-lookup"><span data-stu-id="4ee99-132">Now you are able to test your site with the Chromium Content Shell.</span></span>  

#### <span data-ttu-id="4ee99-133">Firefox on Android</span><span class="sxs-lookup"><span data-stu-id="4ee99-133">Firefox on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="4ee99-134">Similar to the Chromium Content Shell, you are able to get an APK to install Firefox onto the emulator.</span><span class="sxs-lookup"><span data-stu-id="4ee99-134">Similar to the Chromium Content Shell, you are able to get an APK to install Firefox onto the emulator.</span></span>  

<span data-ttu-id="4ee99-135">[Download the correct .apk file][MozillaFirefoxDownload].</span><span class="sxs-lookup"><span data-stu-id="4ee99-135">[Download the correct .apk file][MozillaFirefoxDownload].</span></span>  

<span data-ttu-id="4ee99-136">To install the file onto an open emulator or connected Android device, run the following command.</span><span class="sxs-lookup"><span data-stu-id="4ee99-136">To install the file onto an open emulator or connected Android device, run the following command.</span></span>  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <span data-ttu-id="4ee99-137">iOS simulator</span><span class="sxs-lookup"><span data-stu-id="4ee99-137">iOS simulator</span></span>  

<span data-ttu-id="4ee99-138">The iOS simulator for Mac OS X comes with Xcode, which you [install from the App Store][MacAppStoreXcode].</span><span class="sxs-lookup"><span data-stu-id="4ee99-138">The iOS simulator for Mac OS X comes with Xcode, which you [install from the App Store][MacAppStoreXcode].</span></span>  

<span data-ttu-id="4ee99-139">When you are done, learn how to work with the simulator through [Apple Developer documentation][AppleSimulatorHelp].</span><span class="sxs-lookup"><span data-stu-id="4ee99-139">When you are done, learn how to work with the simulator through [Apple Developer documentation][AppleSimulatorHelp].</span></span>  

> [!NOTE]
> <span data-ttu-id="4ee99-140">To avoid having to open Xcode every time you want to use the iOS Simulator, open it, then right-click the iOS Simulator icon in your dock and select **Keep in Dock**.</span><span class="sxs-lookup"><span data-stu-id="4ee99-140">To avoid having to open Xcode every time you want to use the iOS Simulator, open it, then right-click the iOS Simulator icon in your dock and select **Keep in Dock**.</span></span>  <span data-ttu-id="4ee99-141">Now just click this icon whenever you need it.</span><span class="sxs-lookup"><span data-stu-id="4ee99-141">Now just click this icon whenever you need it.</span></span>  

###  <span data-ttu-id="4ee99-142">Microsoft Edge (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="4ee99-142">Microsoft Edge (EdgeHTML)</span></span>  

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   <span data-ttu-id="4ee99-144">Modern IE VM</span><span class="sxs-lookup"><span data-stu-id="4ee99-144">Modern IE VM</span></span>  
:::image-end:::  

<span data-ttu-id="4ee99-145">Microsoft Edge \(EdgeHTML\) Virtual Machines \(VMs\) enable you to access different versions of EdgeHTML and IE on your computer via VirtualBox \(or VMWare\).</span><span class="sxs-lookup"><span data-stu-id="4ee99-145">Microsoft Edge \(EdgeHTML\) Virtual Machines \(VMs\) enable you to access different versions of EdgeHTML and IE on your computer via VirtualBox \(or VMWare\).</span></span>  <span data-ttu-id="4ee99-146">Choose a [virtual machine on the download page][MicrosoftDeveloperEdgeVms].</span><span class="sxs-lookup"><span data-stu-id="4ee99-146">Choose a [virtual machine on the download page][MicrosoftDeveloperEdgeVms].</span></span>  

## <span data-ttu-id="4ee99-147">Cloud-based emulators and simulators</span><span class="sxs-lookup"><span data-stu-id="4ee99-147">Cloud-based emulators and simulators</span></span>  

<span data-ttu-id="4ee99-148">If you are not able to use the emulators and do not have access to real devices, then cloud-based emulators are the next best thing.</span><span class="sxs-lookup"><span data-stu-id="4ee99-148">If you are not able to use the emulators and do not have access to real devices, then cloud-based emulators are the next best thing.</span></span>  <span data-ttu-id="4ee99-149">A big advantage of cloud-based emulators over real devices and local emulators is that you are able to automate unit tests for your site across different platforms.</span><span class="sxs-lookup"><span data-stu-id="4ee99-149">A big advantage of cloud-based emulators over real devices and local emulators is that you are able to automate unit tests for your site across different platforms.</span></span>  

*   <span data-ttu-id="4ee99-150">[BrowserStack (commercial)][|::ref1::|] is the easiest to use for manual testing.</span><span class="sxs-lookup"><span data-stu-id="4ee99-150">[BrowserStack (commercial)][|::ref1::|] is the easiest to use for manual testing.</span></span>  <span data-ttu-id="4ee99-151">You select an operating system, select your browser version and device type, select a URL to browse, and it spins up a hosted virtual machine with which you may interact.</span><span class="sxs-lookup"><span data-stu-id="4ee99-151">You select an operating system, select your browser version and device type, select a URL to browse, and it spins up a hosted virtual machine with which you may interact.</span></span>  <span data-ttu-id="4ee99-152">You are able to also run multiple emulators in the same screen, enabling you to test the look and feel of your app across multiple devices at the same time.</span><span class="sxs-lookup"><span data-stu-id="4ee99-152">You are able to also run multiple emulators in the same screen, enabling you to test the look and feel of your app across multiple devices at the same time.</span></span>  
*   <span data-ttu-id="4ee99-153">[SauceLabs (commercial)][SauceLabs] enables you to run unit tests inside of an emulator, which may be really useful for scripting a flow through your site and watching the video recording of this afterwards on various devices.</span><span class="sxs-lookup"><span data-stu-id="4ee99-153">[SauceLabs (commercial)][SauceLabs] enables you to run unit tests inside of an emulator, which may be really useful for scripting a flow through your site and watching the video recording of this afterwards on various devices.</span></span>  <span data-ttu-id="4ee99-154">You are also able to do manual testing with your site.</span><span class="sxs-lookup"><span data-stu-id="4ee99-154">You are also able to do manual testing with your site.</span></span>  
*   <span data-ttu-id="4ee99-155">[Device Anywhere (commercial)][AppExperience] does not use emulators but real devices which you are able to control remotely.</span><span class="sxs-lookup"><span data-stu-id="4ee99-155">[Device Anywhere (commercial)][AppExperience] does not use emulators but real devices which you are able to control remotely.</span></span>  <span data-ttu-id="4ee99-156">This is very useful in the event where you need to reproduce a problem on a specific device and are not able to see the bug using any of the options in the previous guides.</span><span class="sxs-lookup"><span data-stu-id="4ee99-156">This is very useful in the event where you need to reproduce a problem on a specific device and are not able to see the bug using any of the options in the previous guides.</span></span>  

<!--  
 


-->  

<!-- links -->  

[DevToolsEdgeHtmlEmulation]: /microsoft-edge/devtools-guide/emulation "DevTools (EdgeHTML) - Emulation | Microsoft Docs"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "Emulate browsers, screen sizes, and GPS locations | Microsoft Docs"  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "Download virtual machines"  

[AndroidStudioCreateManageVirtualDevices]: https://developer.android.com/tools/devices/managing-avds.html "Create and manage virtual devices | Android Developers"  
[AndroidStudioDownload]:  https://developer.android.com/sdk/installing/studio.html "Download Android Studio and SDK tools | Android Developers"  
[AndroidStudioRunAppsAndroidEmulator]: https://developer.android.com/tools/devices/emulator.html "Run apps on the Android Emulator | Android Developers"  

[AppExperience]: https://www.sigos.com/app-experience/ "App Experience"  
[AppleSimulatorHelp]: https://help.apple.com/simulator/mac/current "Simulator Help - current | Apple"  
[BrowserStack]: https://www.browserstack.com/automate "BrowserStack"  
[MacAppStoreXcode]: https://itunes.apple.com/app/xcode/id497799835 "Xcode on the Mac App Store"  
[MDNResponsiveDesignMode]: https://developer.mozilla.org/docs/Tools/Responsive_Design_View "Responsive Design Mode | MDN"  
[MozillaFirefoxDownload]: https://www.mozilla.org/firefox/all/#product-android-beta "Download the Firefox Browser"  
[SauceLabs]: https://saucelabs.com "Sauce Labs"  

> [!NOTE]
> <span data-ttu-id="4ee99-170">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="4ee99-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4ee99-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google | Tools, Performance, Animation, UX\).</span><span class="sxs-lookup"><span data-stu-id="4ee99-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google | Tools, Performance, Animation, UX\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="4ee99-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span><span class="sxs-lookup"><span data-stu-id="4ee99-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
