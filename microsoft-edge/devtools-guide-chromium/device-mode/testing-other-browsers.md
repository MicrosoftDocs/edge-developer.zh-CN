---
title: 模拟和测试其他浏览器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 65ad10ff89d3e4c27abc97cea0eb18b15853dd2e
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607311"
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





# <span data-ttu-id="56e07-103">模拟和测试其他浏览器</span><span class="sxs-lookup"><span data-stu-id="56e07-103">Emulate and Test Other Browsers</span></span>   




<span data-ttu-id="56e07-104">您的工作不能确保您的网站在 Microsoft Edge 和 Android 中运行得非常出色。</span><span class="sxs-lookup"><span data-stu-id="56e07-104">Your job does not end with ensuring your site runs great across Microsoft Edge and Android.</span></span>  <span data-ttu-id="56e07-105">即使设备模式能够模拟 Iphone 之类的其他设备，我们也鼓励你查看其他浏览器提供的仿真的解决方案。</span><span class="sxs-lookup"><span data-stu-id="56e07-105">Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.</span></span>  

### <span data-ttu-id="56e07-106">摘要</span><span class="sxs-lookup"><span data-stu-id="56e07-106">Summary</span></span>  

*   <span data-ttu-id="56e07-107">如果您没有特定设备，或者想要对某些内容执行专色检查，最佳选择是在浏览器内部直接模拟设备。</span><span class="sxs-lookup"><span data-stu-id="56e07-107">When you do not have a particular device, or want to do a spot check on something, the best option is to emulate the device right inside your browser.</span></span>  
*   <span data-ttu-id="56e07-108">通过设备模拟器和模拟器，你可以将你的开发网站从工作站上的一系列设备中模拟。</span><span class="sxs-lookup"><span data-stu-id="56e07-108">Device emulators and simulators enable you to mimic your development site on a range of devices from your workstation.</span></span>  
*   <span data-ttu-id="56e07-109">基于云的模拟器使你能够跨不同平台自动处理你的网站的单元测试。</span><span class="sxs-lookup"><span data-stu-id="56e07-109">Cloud-based emulators enable you to automate unit tests for your site across different platforms.</span></span>  

## <span data-ttu-id="56e07-110">浏览器模拟器</span><span class="sxs-lookup"><span data-stu-id="56e07-110">Browser emulators</span></span>  

<span data-ttu-id="56e07-111">浏览器模拟器对于测试网站的响应非常有用，但每个模拟器不会模拟 API、CSS 支持和你在移动浏览器上看到的某些行为的差异。</span><span class="sxs-lookup"><span data-stu-id="56e07-111">Browser emulators are great for testing the responsiveness of a site, but each does not emulate differences in API, CSS support, and certain behaviors that you see on a mobile browser.</span></span>  <span data-ttu-id="56e07-112">在实际设备上运行的浏览器上测试网站，以确保所有内容均按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="56e07-112">Test your site on browsers running on real devices to be certain everything behaves as expected.</span></span>  

### <span data-ttu-id="56e07-113">Firefox 响应式设计视图</span><span class="sxs-lookup"><span data-stu-id="56e07-113">Firefox Responsive Design View</span></span>  

<span data-ttu-id="56e07-114">Firefox 有一个[响应式设计视图][MDNResponsiveDesignMode]，它鼓励你在特定设备方面停止思考，而改为通过拖动边缘来了解你的设计是如何在常见的屏幕大小或自己的大小上更改的。</span><span class="sxs-lookup"><span data-stu-id="56e07-114">Firefox has a [responsive design view][MDNResponsiveDesignMode] that encourages you to stop thinking in terms of specific devices and instead explore how your design changes at common screen sizes or your own size by dragging the edges.</span></span>  

### <span data-ttu-id="56e07-115">EdgeHTML 仿真</span><span class="sxs-lookup"><span data-stu-id="56e07-115">EdgeHTML Emulation</span></span>  

<span data-ttu-id="56e07-116">若要模拟 Windows 手机，请使用 Microsoft Edge \ （EdgeHTML \）[内置仿真][DevToolsEdgeHtmlEmulation]。</span><span class="sxs-lookup"><span data-stu-id="56e07-116">To emulate Windows Phones, use the Microsoft Edge \(EdgeHTML\) [built-in emulation][DevToolsEdgeHtmlEmulation].</span></span>  

<span data-ttu-id="56e07-117">使用[IE 11 仿真][Ie11DevToolsEmulation]模拟你的页面在较早版本的 Internet Explorer 中的外观。</span><span class="sxs-lookup"><span data-stu-id="56e07-117">Use [IE 11 Emulation][Ie11DevToolsEmulation] to simulate how your page may look in older versions of Internet Explorer.</span></span>  

## <span data-ttu-id="56e07-118">设备模拟器和模拟器</span><span class="sxs-lookup"><span data-stu-id="56e07-118">Device emulators and simulators</span></span>  

<span data-ttu-id="56e07-119">设备模拟器和模拟器不仅模拟浏览器环境，还模拟整个设备。</span><span class="sxs-lookup"><span data-stu-id="56e07-119">Device simulators and emulators simulate not just the browser environment but the entire device.</span></span>  <span data-ttu-id="56e07-120">每个测试都有助于测试需要操作系统集成的项目，例如用虚拟键盘的表单输入。</span><span class="sxs-lookup"><span data-stu-id="56e07-120">Each are useful to test things that require OS integration, for example form input with virtual keyboards.</span></span>  

### <span data-ttu-id="56e07-121">Android 模拟器</span><span class="sxs-lookup"><span data-stu-id="56e07-121">Android Emulator</span></span>  

<!--
> ##### Figure old 1  
> Stock Browser in Android Emulator  
> ![Stock Browser in Android Emulator][ImageAndroidEmulatorStockBrowser]  
-->

<span data-ttu-id="56e07-122">目前，无法在 Android 模拟器上安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="56e07-122">At the moment, there is no way to install Microsoft Edge on an Android emulator.</span></span>  <span data-ttu-id="56e07-123">但是，你可以使用 Android 浏览器、Chromium 内容外壳和适用于 Android 的 Firefox，我们将在本指南的后面部分进行查看。</span><span class="sxs-lookup"><span data-stu-id="56e07-123">However, you may use the Android Browser, the Chromium Content Shell, and Firefox for Android which we review later in this guide.</span></span>  <span data-ttu-id="56e07-124">Chromium 内容 Shell 以 Microsoft Edge 的形式运行同一 Chromium 呈现引擎，但不会出现任何浏览器特定功能。</span><span class="sxs-lookup"><span data-stu-id="56e07-124">Chromium Content Shell runs the same Chromium rendering engine as Microsoft Edge, but comes without any of the browser specific features.</span></span>  

<span data-ttu-id="56e07-125">Android 模拟器随附了 Android SDK，您需要在[Android Studio][AndroidStudioDownload]中下载该 SDK。</span><span class="sxs-lookup"><span data-stu-id="56e07-125">The Android emulator comes with the Android SDK which you need to download as part of [Android Studio][AndroidStudioDownload].</span></span>  <span data-ttu-id="56e07-126">然后按照说明[设置虚拟设备][AndroidStudioCreateManageVirtualDevices]并[启动模拟器][AndroidStudioRunAppsAndroidEmulator]。</span><span class="sxs-lookup"><span data-stu-id="56e07-126">Then follow the instructions to [set up a virtual device][AndroidStudioCreateManageVirtualDevices] and [start the emulator][AndroidStudioRunAppsAndroidEmulator].</span></span>  
<span data-ttu-id="56e07-127">启动仿真器后，单击浏览器图标，然后在 Android 旧版的常用浏览器中测试您的网站。</span><span class="sxs-lookup"><span data-stu-id="56e07-127">Once your emulator is booted, click on the Browser icon, and test your site on the old Stock Browser for Android.</span></span>  

#### <span data-ttu-id="56e07-128">Android 上的 Chromium 内容 Shell</span><span class="sxs-lookup"><span data-stu-id="56e07-128">Chromium Content Shell on Android</span></span>  

<!--
> ##### Figure old 2  
> Android Emulator Content Shell  
> ![Android Emulator Content Shell][ImageAndroidEmulatorContentShell]  
-->

<span data-ttu-id="56e07-129">若要安装 Android 的 Chromium 内容 Shell，请让你的模拟器在命令提示符处运行并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="56e07-129">To install the Chromium Content Shell for Android, leave your emulator running and run the following commands at a command prompt:</span></span>  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

<span data-ttu-id="56e07-130">现在，你可以通过 Chromium 内容 Shell 测试你的网站。</span><span class="sxs-lookup"><span data-stu-id="56e07-130">Now you are able to test your site with the Chromium Content Shell.</span></span>  

#### <span data-ttu-id="56e07-131">Android 上的 Firefox</span><span class="sxs-lookup"><span data-stu-id="56e07-131">Firefox on Android</span></span>  

<!--
> ##### Figure old 3  
> Firefox Icon on Android Emulator  
> ![Firefox Icon on Android Emulator][ImageAndroidEmulatorFirefoxBrowser]  
-->

<span data-ttu-id="56e07-132">与 Chromium 内容外壳程序类似，你可以获取将 Firefox 安装到模拟器的 APK。</span><span class="sxs-lookup"><span data-stu-id="56e07-132">Similar to the Chromium Content Shell, you are able to get an APK to install Firefox onto the emulator.</span></span>  

<span data-ttu-id="56e07-133">[下载正确的 apk 文件][MozillaFirefoxDownload]。</span><span class="sxs-lookup"><span data-stu-id="56e07-133">[Download the correct .apk file][MozillaFirefoxDownload].</span></span>  

<span data-ttu-id="56e07-134">在此处，你可以使用以下命令将文件安装到开放模拟器或连接的 Android 设备上：</span><span class="sxs-lookup"><span data-stu-id="56e07-134">From here, you are able to install the file onto an open emulator or connected Android device with the following command:</span></span>  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <span data-ttu-id="56e07-135">iOS 模拟器</span><span class="sxs-lookup"><span data-stu-id="56e07-135">iOS Simulator</span></span>  

<span data-ttu-id="56e07-136">适用于 Mac OS X 的 iOS 模拟器附带了 Xcode，可[从 App Store 进行安装][MacAppStoreXcode]。</span><span class="sxs-lookup"><span data-stu-id="56e07-136">The iOS simulator for Mac OS X comes with Xcode, which you [install from the App Store][MacAppStoreXcode].</span></span>  

<span data-ttu-id="56e07-137">完成后，了解如何通过[Apple 开发人员文档][AppleSimulatorHelp]处理模拟器。</span><span class="sxs-lookup"><span data-stu-id="56e07-137">When you are done, learn how to work with the simulator through [Apple Developer documentation][AppleSimulatorHelp].</span></span>  

> [!NOTE]
> <span data-ttu-id="56e07-138">若要避免每次希望使用 iOS 模拟器时都打开 Xcode，请将其打开，然后右键单击您的 dock 中的 iOS 模拟器图标，然后选择 "**保留在 dock 中**"。</span><span class="sxs-lookup"><span data-stu-id="56e07-138">To avoid having to open Xcode every time you want to use the iOS Simulator, open it, then right-click the iOS Simulator icon in your dock and select **Keep in Dock**.</span></span>  <span data-ttu-id="56e07-139">现在只需在需要时单击此图标。</span><span class="sxs-lookup"><span data-stu-id="56e07-139">Now just click this icon whenever you need it.</span></span>  

###  <span data-ttu-id="56e07-140">Microsoft Edge （EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="56e07-140">Microsoft Edge (EdgeHTML)</span></span>  

> ##### <span data-ttu-id="56e07-141">图 1</span><span class="sxs-lookup"><span data-stu-id="56e07-141">Figure 1</span></span>  
> <span data-ttu-id="56e07-142">新式 IE VM</span><span class="sxs-lookup"><span data-stu-id="56e07-142">Modern IE VM</span></span>  
> <span data-ttu-id="56e07-143">![新式 IE VM][ImageVMModernIe]</span><span class="sxs-lookup"><span data-stu-id="56e07-143">![Modern IE VM][ImageVMModernIe]</span></span>  

<span data-ttu-id="56e07-144">Microsoft Edge \ （EdgeHTML \）虚拟机 \ （Vm \）允许你通过 VirtualBox \ （或 VMWare \）访问你的计算机上的不同版本的 EdgeHTML 和 IE。</span><span class="sxs-lookup"><span data-stu-id="56e07-144">Microsoft Edge \(EdgeHTML\) Virtual Machines \(VMs\) enable you to access different versions of EdgeHTML and IE on your computer via VirtualBox \(or VMWare\).</span></span>  <span data-ttu-id="56e07-145">选择["下载" 页面上的虚拟机][MicrosoftDeveloperEdgeVms]。</span><span class="sxs-lookup"><span data-stu-id="56e07-145">Choose a [virtual machine on the download page][MicrosoftDeveloperEdgeVms].</span></span>  

## <span data-ttu-id="56e07-146">基于云的模拟器和模拟器</span><span class="sxs-lookup"><span data-stu-id="56e07-146">Cloud-based emulators and simulators</span></span>  

<span data-ttu-id="56e07-147">如果无法使用仿真程序，并且无法访问实际设备，则基于云的模拟器是下一种最佳做法。</span><span class="sxs-lookup"><span data-stu-id="56e07-147">If you are not able to use the emulators and do not have access to real devices, then cloud-based emulators are the next best thing.</span></span>  <span data-ttu-id="56e07-148">在真实设备和本地模拟器上使用基于云的模拟器的一个显著优势是，你可以跨不同平台自动处理你的网站的单元测试。</span><span class="sxs-lookup"><span data-stu-id="56e07-148">A big advantage of cloud-based emulators over real devices and local emulators is that you are able to automate unit tests for your site across different platforms.</span></span>  

*   <span data-ttu-id="56e07-149">[BrowserStack （商业版）][|::ref1::|]最易于用于手动测试。</span><span class="sxs-lookup"><span data-stu-id="56e07-149">[BrowserStack (commercial)][|::ref1::|] is the easiest to use for manual testing.</span></span>  <span data-ttu-id="56e07-150">选择操作系统，选择你的浏览器版本和设备类型，选择要浏览的 URL，它会旋转托管的虚拟机，你可以与其进行交互。</span><span class="sxs-lookup"><span data-stu-id="56e07-150">You select an operating system, select your browser version and device type, select a URL to browse, and it spins up a hosted virtual machine with which you may interact.</span></span>  <span data-ttu-id="56e07-151">你还可以在同一屏幕中运行多个模拟器，从而使你能够在多个设备上同时测试你的应用的外观。</span><span class="sxs-lookup"><span data-stu-id="56e07-151">You are able to also run multiple emulators in the same screen, enabling you to test the look and feel of your app across multiple devices at the same time.</span></span>  
*   <span data-ttu-id="56e07-152">[SauceLabs （商业版）][SauceLabs]使你能够在仿真器内运行单元测试，这对于通过您的网站编写流并随后在各种设备上观看视频录制的内容可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="56e07-152">[SauceLabs (commercial)][SauceLabs] enables you to run unit tests inside of an emulator, which may be really useful for scripting a flow through your site and watching the video recording of this afterwards on various devices.</span></span>  <span data-ttu-id="56e07-153">您还可以通过您的网站进行手动测试。</span><span class="sxs-lookup"><span data-stu-id="56e07-153">You are also able to do manual testing with your site.</span></span>  
*   <span data-ttu-id="56e07-154">[任何地方的设备（商业版）][AppExperience]不使用模拟器，而是您能够远程控制的实时设备。</span><span class="sxs-lookup"><span data-stu-id="56e07-154">[Device Anywhere (commercial)][AppExperience] does not use emulators but real devices which you are able to control remotely.</span></span>  <span data-ttu-id="56e07-155">这在你需要在特定设备上重现问题且无法使用上述指南中的任何选项查看 bug 的情况下非常有用。</span><span class="sxs-lookup"><span data-stu-id="56e07-155">This is very useful in the event where you need to reproduce a problem on a specific device and are not able to see the bug using any of the options in the previous guides.</span></span>  

 



<!-- image links -->  

<!--[ImageAndroidEmulatorStockBrowser]: /microsoft-edge/devtools-guide-chromium/media/device-mode-android-emulator-stock-browser.msft.png "Figure old 1: Stock Browser in Android Emulator"  -->  
<!--[ImageAndroidEmulatorContentShell]: /microsoft-edge/devtools-guide-chromium/media/device-mode-android-avd-contentshell.msft.png "Figure old 2: Android Emulator Content Shell"  -->  
<!--[ImageAndroidEmulatorFirefoxBrowser]: /microsoft-edge/devtools-guide-chromium/media/device-mode-ff-on-android-emulator.msft.png "Figure old 3: Firefox Icon on Android Emulator"  -->  
<span data-ttu-id="56e07-156">[ImageVMModernIe]：/microsoft-edge/devtools-guide-chromium/media/device-mode-modern-ie-vm.msft.png "图1：新式 IE VM"</span><span class="sxs-lookup"><span data-stu-id="56e07-156">[ImageVMModernIe]: /microsoft-edge/devtools-guide-chromium/media/device-mode-modern-ie-vm.msft.png "Figure 1: Modern IE VM"</span></span>  

<!-- links -->  

[DevToolsEdgeHtmlEmulation]: /microsoft-edge/devtools-guide/emulation "DevTools （EdgeHTML）-模拟"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "模拟浏览器、屏幕大小和 GPS 位置"  

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
> <span data-ttu-id="56e07-170">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="56e07-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="56e07-171">原始页面可在[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers)找到，并由[Meggin Kearney][MegginKearney] \ （技术作者）和[Paul Bakaus][PaulBakaus] \ （在 Google | 上打开 Web 开发人员提供商）。工具、性能、动画、UX \）。</span><span class="sxs-lookup"><span data-stu-id="56e07-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google | Tools, Performance, Animation, UX\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="56e07-173">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="56e07-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
