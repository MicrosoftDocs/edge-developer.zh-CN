---
description: 您的工作不能确保您的网站在 Microsoft Edge 和 Android 中运行得非常出色。  即使设备模式能够模拟 Iphone 之类的其他设备，我们也鼓励你查看其他浏览器提供的仿真的解决方案。
title: 模拟和测试其他浏览器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
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





# <span data-ttu-id="e8e0c-105">模拟和测试其他浏览器</span><span class="sxs-lookup"><span data-stu-id="e8e0c-105">Emulate and test other browsers</span></span>   




<span data-ttu-id="e8e0c-106">您的工作不能确保您的网站在 Microsoft Edge 和 Android 中运行得非常出色。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-106">Your job does not end with ensuring your site runs great across Microsoft Edge and Android.</span></span>  <span data-ttu-id="e8e0c-107">即使设备模式能够模拟 Iphone 之类的其他设备，我们也鼓励你查看其他浏览器提供的仿真的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-107">Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.</span></span>  

### <span data-ttu-id="e8e0c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e8e0c-108">Summary</span></span>  

*   <span data-ttu-id="e8e0c-109">如果您没有特定设备，或者想要对某些内容执行专色检查，最佳选择是在浏览器内部直接模拟设备。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-109">When you do not have a particular device, or want to do a spot check on something, the best option is to emulate the device right inside your browser.</span></span>  
*   <span data-ttu-id="e8e0c-110">通过设备模拟器和模拟器，你可以将你的开发网站从工作站上的一系列设备中模拟。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-110">Device emulators and simulators enable you to mimic your development site on a range of devices from your workstation.</span></span>  
*   <span data-ttu-id="e8e0c-111">基于云的模拟器使你能够跨不同平台自动处理你的网站的单元测试。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-111">Cloud-based emulators enable you to automate unit tests for your site across different platforms.</span></span>  

## <span data-ttu-id="e8e0c-112">浏览器模拟器</span><span class="sxs-lookup"><span data-stu-id="e8e0c-112">Browser emulators</span></span>  

<span data-ttu-id="e8e0c-113">浏览器模拟器对于测试网站的响应非常有用，但每个模拟器不会模拟 API、CSS 支持和你在移动浏览器上看到的某些行为的差异。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-113">Browser emulators are great for testing the responsiveness of a site, but each does not emulate differences in API, CSS support, and certain behaviors that you see on a mobile browser.</span></span>  <span data-ttu-id="e8e0c-114">在实际设备上运行的浏览器上测试网站，以确保所有内容均按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-114">Test your site on browsers running on real devices to be certain everything behaves as expected.</span></span>  

### <span data-ttu-id="e8e0c-115">Firefox 响应式设计视图</span><span class="sxs-lookup"><span data-stu-id="e8e0c-115">Firefox Responsive Design View</span></span>  

<span data-ttu-id="e8e0c-116">Firefox 有一个 [响应式设计视图][MDNResponsiveDesignMode] ，它鼓励你在特定设备方面停止思考，而改为通过拖动边缘来了解你的设计是如何在常见的屏幕大小或自己的大小上更改的。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-116">Firefox has a [responsive design view][MDNResponsiveDesignMode] that encourages you to stop thinking in terms of specific devices and instead explore how your design changes at common screen sizes or your own size by dragging the edges.</span></span>  

### <span data-ttu-id="e8e0c-117">EdgeHTML 仿真</span><span class="sxs-lookup"><span data-stu-id="e8e0c-117">EdgeHTML emulation</span></span>  

<span data-ttu-id="e8e0c-118">若要模拟 Windows 手机，请使用 Microsoft Edge \ (EdgeHTML \ ) [内置仿真][DevToolsEdgeHtmlEmulation]。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-118">To emulate Windows Phones, use the Microsoft Edge \(EdgeHTML\) [built-in emulation][DevToolsEdgeHtmlEmulation].</span></span>  

<span data-ttu-id="e8e0c-119">使用 [IE 11 仿真][Ie11DevToolsEmulation] 模拟你的页面在较早版本的 Internet Explorer 中的外观。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-119">Use [IE 11 Emulation][Ie11DevToolsEmulation] to simulate how your page may look in older versions of Internet Explorer.</span></span>  

## <span data-ttu-id="e8e0c-120">设备模拟器和模拟器</span><span class="sxs-lookup"><span data-stu-id="e8e0c-120">Device emulators and simulators</span></span>  

<span data-ttu-id="e8e0c-121">设备模拟器和模拟器不仅模拟浏览器环境，还模拟整个设备。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-121">Device simulators and emulators simulate not just the browser environment but the entire device.</span></span>  <span data-ttu-id="e8e0c-122">每个测试都有助于测试需要操作系统集成的项目，例如用虚拟键盘的表单输入。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-122">Each are useful to test things that require OS integration, for example form input with virtual keyboards.</span></span>  

### <span data-ttu-id="e8e0c-123">Android 模拟器</span><span class="sxs-lookup"><span data-stu-id="e8e0c-123">Android emulator</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="e8e0c-124">目前，无法在 Android 模拟器上安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-124">At the moment, there is no way to install Microsoft Edge on an Android emulator.</span></span>  <span data-ttu-id="e8e0c-125">但是，你可以使用 Android 浏览器、Chromium 内容外壳和适用于 Android 的 Firefox，我们将在本指南的后面部分进行查看。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-125">However, you may use the Android Browser, the Chromium Content Shell, and Firefox for Android which we review later in this guide.</span></span>  <span data-ttu-id="e8e0c-126">Chromium 内容 Shell 以 Microsoft Edge 的形式运行同一 Chromium 呈现引擎，但不会出现任何浏览器特定功能。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-126">Chromium Content Shell runs the same Chromium rendering engine as Microsoft Edge, but comes without any of the browser specific features.</span></span>  

<span data-ttu-id="e8e0c-127">Android 模拟器随附了 Android SDK，您需要在 [Android Studio][AndroidStudioDownload]中下载该 SDK。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-127">The Android emulator comes with the Android SDK which you need to download as part of [Android Studio][AndroidStudioDownload].</span></span>  <span data-ttu-id="e8e0c-128">然后按照说明 [设置虚拟设备][AndroidStudioCreateManageVirtualDevices] 并 [启动模拟器][AndroidStudioRunAppsAndroidEmulator]。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-128">Then follow the instructions to [set up a virtual device][AndroidStudioCreateManageVirtualDevices] and [start the emulator][AndroidStudioRunAppsAndroidEmulator].</span></span>  
<span data-ttu-id="e8e0c-129">启动仿真器后，单击浏览器图标，然后在 Android 旧版的常用浏览器中测试您的网站。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-129">Once your emulator is booted, click on the Browser icon, and test your site on the old Stock Browser for Android.</span></span>  

#### <span data-ttu-id="e8e0c-130">Android 上的 Chromium 内容 shell</span><span class="sxs-lookup"><span data-stu-id="e8e0c-130">Chromium content shell on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Android Emulator Content Shell" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

<span data-ttu-id="e8e0c-131">若要安装 Android 的 Chromium 内容 Shell，请保持仿真器运行并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-131">To install the Chromium Content Shell for Android, leave your emulator running and run the following command.</span></span>  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

<span data-ttu-id="e8e0c-132">现在，你可以通过 Chromium 内容 Shell 测试你的网站。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-132">Now you are able to test your site with the Chromium Content Shell.</span></span>  

#### <span data-ttu-id="e8e0c-133">Android 上的 Firefox</span><span class="sxs-lookup"><span data-stu-id="e8e0c-133">Firefox on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Firefox Icon on Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="e8e0c-134">与 Chromium 内容外壳程序类似，你可以获取将 Firefox 安装到模拟器的 APK。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-134">Similar to the Chromium Content Shell, you are able to get an APK to install Firefox onto the emulator.</span></span>  

<span data-ttu-id="e8e0c-135">[下载正确的 apk 文件][MozillaFirefoxDownload]。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-135">[Download the correct .apk file][MozillaFirefoxDownload].</span></span>  

<span data-ttu-id="e8e0c-136">若要将文件安装到打开的模拟器或连接的 Android 设备上，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-136">To install the file onto an open emulator or connected Android device, run the following command.</span></span>  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <span data-ttu-id="e8e0c-137">iOS 模拟器</span><span class="sxs-lookup"><span data-stu-id="e8e0c-137">iOS simulator</span></span>  

<span data-ttu-id="e8e0c-138">适用于 Mac OS X 的 iOS 模拟器附带了 Xcode，可 [从 App Store 进行安装][MacAppStoreXcode]。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-138">The iOS simulator for Mac OS X comes with Xcode, which you [install from the App Store][MacAppStoreXcode].</span></span>  

<span data-ttu-id="e8e0c-139">完成后，了解如何通过 [Apple 开发人员文档][AppleSimulatorHelp]处理模拟器。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-139">When you are done, learn how to work with the simulator through [Apple Developer documentation][AppleSimulatorHelp].</span></span>  

> [!NOTE]
> <span data-ttu-id="e8e0c-140">若要避免每次希望使用 iOS 模拟器时都打开 Xcode，请将其打开，然后右键单击您的 dock 中的 iOS 模拟器图标，然后选择 " **保留在 dock 中**"。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-140">To avoid having to open Xcode every time you want to use the iOS Simulator, open it, then right-click the iOS Simulator icon in your dock and select **Keep in Dock**.</span></span>  <span data-ttu-id="e8e0c-141">现在只需在需要时单击此图标。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-141">Now just click this icon whenever you need it.</span></span>  

###  <span data-ttu-id="e8e0c-142">Microsoft Edge (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="e8e0c-142">Microsoft Edge (EdgeHTML)</span></span>  

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="新式 IE VM" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   <span data-ttu-id="e8e0c-144">新式 IE VM</span><span class="sxs-lookup"><span data-stu-id="e8e0c-144">Modern IE VM</span></span>  
:::image-end:::  

<span data-ttu-id="e8e0c-145">Microsoft Edge \ (EdgeHTML \ ) 虚拟机 \ (Vm \ ) 使你可以通过 VirtualBox \ (或 VMWare ) 访问计算机上的不同版本的 EdgeHTML 和 IE。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-145">Microsoft Edge \(EdgeHTML\) Virtual Machines \(VMs\) enable you to access different versions of EdgeHTML and IE on your computer via VirtualBox \(or VMWare\).</span></span>  <span data-ttu-id="e8e0c-146">选择 ["下载" 页面上的虚拟机][MicrosoftDeveloperEdgeVms]。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-146">Choose a [virtual machine on the download page][MicrosoftDeveloperEdgeVms].</span></span>  

## <span data-ttu-id="e8e0c-147">基于云的模拟器和模拟器</span><span class="sxs-lookup"><span data-stu-id="e8e0c-147">Cloud-based emulators and simulators</span></span>  

<span data-ttu-id="e8e0c-148">如果无法使用仿真程序，并且无法访问实际设备，则基于云的模拟器是下一种最佳做法。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-148">If you are not able to use the emulators and do not have access to real devices, then cloud-based emulators are the next best thing.</span></span>  <span data-ttu-id="e8e0c-149">在真实设备和本地模拟器上使用基于云的模拟器的一个显著优势是，你可以跨不同平台自动处理你的网站的单元测试。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-149">A big advantage of cloud-based emulators over real devices and local emulators is that you are able to automate unit tests for your site across different platforms.</span></span>  

*   <span data-ttu-id="e8e0c-150">[BrowserStack (商业) ][|::ref1::|] 最容易用于手动测试。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-150">[BrowserStack (commercial)][|::ref1::|] is the easiest to use for manual testing.</span></span>  <span data-ttu-id="e8e0c-151">选择操作系统，选择你的浏览器版本和设备类型，选择要浏览的 URL，它会旋转托管的虚拟机，你可以与其进行交互。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-151">You select an operating system, select your browser version and device type, select a URL to browse, and it spins up a hosted virtual machine with which you may interact.</span></span>  <span data-ttu-id="e8e0c-152">你还可以在同一屏幕中运行多个模拟器，从而使你能够在多个设备上同时测试你的应用的外观。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-152">You are able to also run multiple emulators in the same screen, enabling you to test the look and feel of your app across multiple devices at the same time.</span></span>  
*   <span data-ttu-id="e8e0c-153">[SauceLabs (商业) ][SauceLabs] 使你能够在仿真器内运行单元测试，这对于通过您的网站编写流并随后在各种设备上观看视频录制的内容非常有用。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-153">[SauceLabs (commercial)][SauceLabs] enables you to run unit tests inside of an emulator, which may be really useful for scripting a flow through your site and watching the video recording of this afterwards on various devices.</span></span>  <span data-ttu-id="e8e0c-154">您还可以通过您的网站进行手动测试。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-154">You are also able to do manual testing with your site.</span></span>  
*   <span data-ttu-id="e8e0c-155">[ (商业) 的任意位置的设备 ][AppExperience] 不使用模拟器，而是您能够远程控制的实时设备。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-155">[Device Anywhere (commercial)][AppExperience] does not use emulators but real devices which you are able to control remotely.</span></span>  <span data-ttu-id="e8e0c-156">这在你需要在特定设备上重现问题且无法使用上述指南中的任何选项查看 bug 的情况下非常有用。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-156">This is very useful in the event where you need to reproduce a problem on a specific device and are not able to see the bug using any of the options in the previous guides.</span></span>  

<!--  
 


-->  

<!-- links -->  

[DevToolsEdgeHtmlEmulation]: /microsoft-edge/devtools-guide/emulation "DevTools (EdgeHTML) 仿真 |Microsoft 文档"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "模拟浏览器、屏幕大小和 GPS 位置 |Microsoft 文档"  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "下载虚拟机"  

[AndroidStudioCreateManageVirtualDevices]: https://developer.android.com/tools/devices/managing-avds.html "创建和管理虚拟设备 |Android 开发人员"  
[AndroidStudioDownload]:  https://developer.android.com/sdk/installing/studio.html "下载 Android Studio 和 SDK 工具 |Android 开发人员"  
[AndroidStudioRunAppsAndroidEmulator]: https://developer.android.com/tools/devices/emulator.html "在 Android 模拟器上运行应用 |Android 开发人员"  

[AppExperience]: https://www.sigos.com/app-experience/ "应用体验"  
[AppleSimulatorHelp]: https://help.apple.com/simulator/mac/current "模拟器帮助-当前 |Apple"  
[BrowserStack]: https://www.browserstack.com/automate "BrowserStack"  
[MacAppStoreXcode]: https://itunes.apple.com/app/xcode/id497799835 "Mac 应用商店上的 Xcode"  
[MDNResponsiveDesignMode]: https://developer.mozilla.org/docs/Tools/Responsive_Design_View "响应式设计模式 |MDN"  
[MozillaFirefoxDownload]: https://www.mozilla.org/firefox/all/#product-android-beta "下载 Firefox 浏览器"  
[SauceLabs]: https://saucelabs.com "Sauce Labs"  

> [!NOTE]
> <span data-ttu-id="e8e0c-170">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e8e0c-171">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) 找到，并由 [Meggin Kearney][MegginKearney] (技术 ) 作者 \ (在 Google | 上打开 Web 开发人员的 [Bakaus][PaulBakaus] 。工具、性能、动画、UX \ ) 。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google | Tools, Performance, Animation, UX\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e8e0c-173">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e8e0c-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
