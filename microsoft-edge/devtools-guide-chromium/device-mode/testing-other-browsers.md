---
description: 你的作业不会以确保你的网站在 android 和 Microsoft Edge运行。  即使设备模式能够模拟 iPhone 等一系列其他设备，我们也鼓励你查看由其他浏览器提供的模拟解决方案。
title: 模拟和测试其他浏览器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f2ca56c2e15f578a970e6ceb84b1554bfda53862
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564278"
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
# <a name="emulate-and-test-other-browsers"></a><span data-ttu-id="da194-105">模拟和测试其他浏览器</span><span class="sxs-lookup"><span data-stu-id="da194-105">Emulate and test other browsers</span></span>  

<span data-ttu-id="da194-106">你的作业不会以确保你的网站在 android 和 Microsoft Edge运行。</span><span class="sxs-lookup"><span data-stu-id="da194-106">Your job does not end with ensuring your site runs great across Microsoft Edge and Android.</span></span>  <span data-ttu-id="da194-107">即使设备模式能够模拟 iPhone 等一系列其他设备，我们也鼓励你查看由其他浏览器提供的模拟解决方案。</span><span class="sxs-lookup"><span data-stu-id="da194-107">Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.</span></span>  

### <a name="summary"></a><span data-ttu-id="da194-108">摘要</span><span class="sxs-lookup"><span data-stu-id="da194-108">Summary</span></span>  

*   <span data-ttu-id="da194-109">当你没有特定设备，或者想要对某些内容进行专线检查时，最佳选择是模仿浏览器内的设备。</span><span class="sxs-lookup"><span data-stu-id="da194-109">When you do not have a particular device, or want to do a spot check on something, the best option is to emulate the device right inside your browser.</span></span>  
*   <span data-ttu-id="da194-110">设备仿真器和模拟器使你可以模拟工作站中各种设备上的开发网站。</span><span class="sxs-lookup"><span data-stu-id="da194-110">Device emulators and simulators enable you to mimic your development site on a range of devices from your workstation.</span></span>  
*   <span data-ttu-id="da194-111">基于云的仿真器使你可以跨不同平台自动执行网站单元测试。</span><span class="sxs-lookup"><span data-stu-id="da194-111">Cloud-based emulators enable you to automate unit tests for your site across different platforms.</span></span>  

## <a name="browser-emulators"></a><span data-ttu-id="da194-112">浏览器仿真器</span><span class="sxs-lookup"><span data-stu-id="da194-112">Browser emulators</span></span>  

<span data-ttu-id="da194-113">浏览器仿真器非常适用于测试网站的响应性，但每个模拟器不会模拟 API、CSS 支持和移动浏览器上显示的某些行为的差异。</span><span class="sxs-lookup"><span data-stu-id="da194-113">Browser emulators are great for testing the responsiveness of a site, but each does not emulate differences in API, CSS support, and certain behaviors that is displayed on a mobile browser.</span></span>  <span data-ttu-id="da194-114">在真实设备上运行的浏览器上测试网站，确保一切按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="da194-114">Test your site on browsers running on real devices to be certain everything behaves as expected.</span></span>  

### <a name="firefox-responsive-design-view"></a><span data-ttu-id="da194-115">Firefox 响应式设计视图</span><span class="sxs-lookup"><span data-stu-id="da194-115">Firefox Responsive Design View</span></span>  

<span data-ttu-id="da194-116">Firefox 具有响应 [式][MDNResponsiveDesignMode] 设计视图，该视图鼓励您停止就特定设备进行思考，而是通过拖动边缘来探索设计如何以常见屏幕大小或您自己的大小进行更改。</span><span class="sxs-lookup"><span data-stu-id="da194-116">Firefox has a [responsive design view][MDNResponsiveDesignMode] that encourages you to stop thinking in terms of specific devices and instead explore how your design changes at common screen sizes or your own size by dragging the edges.</span></span>  

### <a name="edgehtml-emulation"></a><span data-ttu-id="da194-117">EdgeHTML 模拟</span><span class="sxs-lookup"><span data-stu-id="da194-117">EdgeHTML emulation</span></span>  

<span data-ttu-id="da194-118">若要模拟Windows Phones，请使用 Microsoft Edge \ (EdgeHTML\) [内置模拟][ArchiveMicrosoftEdgeDevtoolsEmulation]。</span><span class="sxs-lookup"><span data-stu-id="da194-118">To emulate Windows Phones, use the Microsoft Edge \(EdgeHTML\) [built-in emulation][ArchiveMicrosoftEdgeDevtoolsEmulation].</span></span>  

<span data-ttu-id="da194-119">使用 [IE 11 仿真][Ie11DevToolsEmulation] 模拟页面在早期版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="da194-119">Use [IE 11 Emulation][Ie11DevToolsEmulation] to simulate how your page may look in older versions of Internet Explorer.</span></span>  

## <a name="device-emulators-and-simulators"></a><span data-ttu-id="da194-120">设备仿真器与模拟器</span><span class="sxs-lookup"><span data-stu-id="da194-120">Device emulators and simulators</span></span>  

<span data-ttu-id="da194-121">设备模拟器和仿真器不仅模拟浏览器环境，还模拟整个设备。</span><span class="sxs-lookup"><span data-stu-id="da194-121">Device simulators and emulators simulate not just the browser environment but the entire device.</span></span>  <span data-ttu-id="da194-122">每个功能都可用于测试需要操作系统集成（例如，使用虚拟键盘的表单输入）的项。</span><span class="sxs-lookup"><span data-stu-id="da194-122">Each are useful to test things that require OS integration, for example form input with virtual keyboards.</span></span>  

### <a name="android-emulator"></a><span data-ttu-id="da194-123">Android 仿真器</span><span class="sxs-lookup"><span data-stu-id="da194-123">Android emulator</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="da194-124">目前，无法将 Microsoft Edge Android 仿真器上。</span><span class="sxs-lookup"><span data-stu-id="da194-124">At the moment, there is no way to install Microsoft Edge on an Android emulator.</span></span>  <span data-ttu-id="da194-125">但是，您可以使用 Android 浏览器、Chromium Shell 和 Firefox for Android，我们将在本指南的稍后部分介绍这些内容。</span><span class="sxs-lookup"><span data-stu-id="da194-125">However, you may use the Android Browser, the Chromium Content Shell, and Firefox for Android which we review later in this guide.</span></span>  <span data-ttu-id="da194-126">Chromium内容命令行管理程序Chromium呈现引擎Microsoft Edge，但不带任何特定于浏览器的功能。</span><span class="sxs-lookup"><span data-stu-id="da194-126">Chromium Content Shell runs the same Chromium rendering engine as Microsoft Edge, but comes without any of the browser specific features.</span></span>  

<span data-ttu-id="da194-127">Android 仿真器附带 Android SDK，你需要下载为 Android [Studio][AndroidStudioDownload]的一部分。</span><span class="sxs-lookup"><span data-stu-id="da194-127">The Android emulator comes with the Android SDK which you need to download as part of [Android Studio][AndroidStudioDownload].</span></span>  <span data-ttu-id="da194-128">然后按照说明[设置虚拟设备并][AndroidStudioCreateManageVirtualDevices][启动仿真器][AndroidStudioRunAppsAndroidEmulator]。</span><span class="sxs-lookup"><span data-stu-id="da194-128">Then follow the instructions to [set up a virtual device][AndroidStudioCreateManageVirtualDevices] and [start the emulator][AndroidStudioRunAppsAndroidEmulator].</span></span>  
<span data-ttu-id="da194-129">启动仿真器后，选择浏览器图标，在适用于 Android 的旧股票浏览器上测试你的网站。</span><span class="sxs-lookup"><span data-stu-id="da194-129">Once your emulator is booted, choose on the Browser icon, and test your site on the old Stock Browser for Android.</span></span>  

#### <a name="chromium-content-shell-on-android"></a><span data-ttu-id="da194-130">Chromium Android 上的内容 shell</span><span class="sxs-lookup"><span data-stu-id="da194-130">Chromium content shell on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Android Emulator Content Shell" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

<span data-ttu-id="da194-131">若要安装适用于 Android Chromium命令行管理程序，请保持仿真器运行并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="da194-131">To install the Chromium Content Shell for Android, leave your emulator running and run the following command.</span></span>  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

<span data-ttu-id="da194-132">现在，您可以使用内容命令行管理程序测试Chromium网站。</span><span class="sxs-lookup"><span data-stu-id="da194-132">Now you are able to test your site with the Chromium Content Shell.</span></span>  

#### <a name="firefox-on-android"></a><span data-ttu-id="da194-133">Android 上的 Firefox</span><span class="sxs-lookup"><span data-stu-id="da194-133">Firefox on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Firefox Icon on Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="da194-134">与内容Chromium类似，您可以获取 APK 以将 Firefox 安装到仿真器上。</span><span class="sxs-lookup"><span data-stu-id="da194-134">Similar to the Chromium Content Shell, you are able to get an APK to install Firefox onto the emulator.</span></span>  

<span data-ttu-id="da194-135">[下载正确的 .apk 文件][MozillaFirefoxDownload]。</span><span class="sxs-lookup"><span data-stu-id="da194-135">[Download the correct .apk file][MozillaFirefoxDownload].</span></span>  

<span data-ttu-id="da194-136">若要将文件安装到打开的仿真器或连接的 Android 设备上，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="da194-136">To install the file onto an open emulator or connected Android device, run the following command.</span></span>  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <a name="ios-simulator"></a><span data-ttu-id="da194-137">iOS 模拟器</span><span class="sxs-lookup"><span data-stu-id="da194-137">iOS simulator</span></span>  

<span data-ttu-id="da194-138">适用于 Mac OS X 的 iOS 模拟器附带 Xcode，从 [应用商店安装][MacAppStoreXcode]。</span><span class="sxs-lookup"><span data-stu-id="da194-138">The iOS simulator for Mac OS X comes with Xcode, which you [install from the App Store][MacAppStoreXcode].</span></span>  

<span data-ttu-id="da194-139">完成后，了解如何通过 Apple 开发人员文档使用 [模拟器][AppleSimulatorHelp]。</span><span class="sxs-lookup"><span data-stu-id="da194-139">When you are done, learn how to work with the simulator through [Apple Developer documentation][AppleSimulatorHelp].</span></span>  

> [!NOTE]
> <span data-ttu-id="da194-140">若要避免每次想要使用 iOS 模拟器时都打开 Xcode，请将其打开，将鼠标悬停在扩展坞中的 iOS 模拟器图标上，打开上下文菜单 \ (右键单击\) ，然后选择"保持在扩展坞中 **"。**</span><span class="sxs-lookup"><span data-stu-id="da194-140">To avoid having to open Xcode every time you want to use the iOS Simulator, open it, hover on the iOS Simulator icon in your dock, open the contextual menu \(right-click\), and choose **Keep in Dock**.</span></span>  <span data-ttu-id="da194-141">现在只要需要图标即可。</span><span class="sxs-lookup"><span data-stu-id="da194-141">Now just choose the icon whenever you need it.</span></span>  

###  <a name="microsoft-edge-edgehtml"></a><span data-ttu-id="da194-142">Microsoft Edge (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="da194-142">Microsoft Edge (EdgeHTML)</span></span>  

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="新式 IE VM" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   <span data-ttu-id="da194-144">新式 IE VM</span><span class="sxs-lookup"><span data-stu-id="da194-144">Modern IE VM</span></span>  
:::image-end:::  

<span data-ttu-id="da194-145">Microsoft Edge \ (EdgeHTML\) Virtual Machines \ (VM\) 可使你通过 VirtualBox \ (或 VMWare\) 访问计算机上不同版本的 EdgeHTML 和 IE。</span><span class="sxs-lookup"><span data-stu-id="da194-145">Microsoft Edge \(EdgeHTML\) Virtual Machines \(VMs\) enable you to access different versions of EdgeHTML and IE on your computer via VirtualBox \(or VMWare\).</span></span>  <span data-ttu-id="da194-146">在 [下载页面上选择虚拟机][MicrosoftDeveloperEdgeVms]。</span><span class="sxs-lookup"><span data-stu-id="da194-146">Choose a [virtual machine on the download page][MicrosoftDeveloperEdgeVms].</span></span>  

## <a name="cloud-based-emulators-and-simulators"></a><span data-ttu-id="da194-147">基于云的模拟器和模拟器</span><span class="sxs-lookup"><span data-stu-id="da194-147">Cloud-based emulators and simulators</span></span>  

<span data-ttu-id="da194-148">如果你无法使用仿真器，并且无法访问真实设备，则基于云的仿真器是下一个最佳选择。</span><span class="sxs-lookup"><span data-stu-id="da194-148">If you are not able to use the emulators and do not have access to real devices, then cloud-based emulators are the next best thing.</span></span>  <span data-ttu-id="da194-149">与实际设备和本地仿真器不同，基于云的模拟器的一大优点是，可以跨不同平台自动执行网站单元测试。</span><span class="sxs-lookup"><span data-stu-id="da194-149">A big advantage of cloud-based emulators over real devices and local emulators is that you are able to automate unit tests for your site across different platforms.</span></span>  

*   <span data-ttu-id="da194-150">[BrowserStack (商业) ][|::ref1::|] 是最容易用于手动测试。</span><span class="sxs-lookup"><span data-stu-id="da194-150">[BrowserStack (commercial)][|::ref1::|] is the easiest to use for manual testing.</span></span>  <span data-ttu-id="da194-151">选择操作系统，选择浏览器版本和设备类型，选择要浏览的 URL，然后它会调节可与你交互的托管虚拟机。</span><span class="sxs-lookup"><span data-stu-id="da194-151">You select an operating system, select your browser version and device type, select a URL to browse, and it spins up a hosted virtual machine with which you may interact.</span></span>  <span data-ttu-id="da194-152">还可以在同一个屏幕中运行多个仿真器，从而可以同时跨多个设备测试应用的外观。</span><span class="sxs-lookup"><span data-stu-id="da194-152">You are able to also run multiple emulators in the same screen, enabling you to test the look and feel of your app across multiple devices at the same time.</span></span>  
*   <span data-ttu-id="da194-153">[使用 Commercial (Labs) ][SauceLabs] 可以在仿真器内运行单元测试，这可能非常有用，可用于编写通过网站的流脚本，并随后在各种设备上观看有关此内容的视频录制。</span><span class="sxs-lookup"><span data-stu-id="da194-153">[SauceLabs (commercial)][SauceLabs] enables you to run unit tests inside of an emulator, which may be really useful for scripting a flow through your site and watching the video recording of this afterwards on various devices.</span></span>  <span data-ttu-id="da194-154">您还可以对网站执行手动测试。</span><span class="sxs-lookup"><span data-stu-id="da194-154">You are also able to do manual testing with your site.</span></span>  
*   <span data-ttu-id="da194-155">[商业 (设备) ][AppExperience] 不使用仿真器，而是使用你可以远程控制的真实设备。</span><span class="sxs-lookup"><span data-stu-id="da194-155">[Device Anywhere (commercial)][AppExperience] does not use emulators but real devices which you are able to control remotely.</span></span>  <span data-ttu-id="da194-156">如果你需要在特定设备上重现问题，并且可能未使用之前指南中的任一选项显示 Bug，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="da194-156">This is very useful in the event where you need to reproduce a problem on a specific device and may not display the bug using any of the options in the previous guides.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="da194-157">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="da194-157">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[ArchiveMicrosoftEdgeDevtoolsEmulation]: /archive/microsoft-edge/legacy/developer/devtools-guide/emulation "模拟|Microsoft Docs"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "模拟浏览器、屏幕大小和 GPS 位置|Microsoft Docs"  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "下载虚拟机"  

[AndroidStudioCreateManageVirtualDevices]: https://developer.android.com/tools/devices/managing-avds.html "创建和管理虚拟设备|Android 开发人员"  
[AndroidStudioDownload]:  https://developer.android.com/sdk/installing/studio.html "下载 Android Studio 和 SDK |Android 开发人员"  
[AndroidStudioRunAppsAndroidEmulator]: https://developer.android.com/tools/devices/emulator.html "在 Android 仿真器设备上|Android 开发人员"  

[AppExperience]: https://www.sigos.com/app-experience/ "应用体验"  
[AppleSimulatorHelp]: https://help.apple.com/simulator/mac/current "模拟器帮助 - 当前|Apple"  
[BrowserStack]: https://www.browserstack.com/automate "BrowserStack"  
[MacAppStoreXcode]: https://itunes.apple.com/app/xcode/id497799835 "Mac 应用商店上的 Xcode"  
[MDNResponsiveDesignMode]: https://developer.mozilla.org/docs/Tools/Responsive_Design_View "响应式设计|MDN"  
[MozillaFirefoxDownload]: https://www.mozilla.org/firefox/all/#product-android-beta "下载 Firefox 浏览器"  
[SauceLabs]: https://saucelabs.com "一些实验室"  

> [!NOTE]
> <span data-ttu-id="da194-171">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="da194-171">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="da194-172">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers)由[Meggin Kearney][MegginKearney] \ (Tech Writer\) 和[Paul Bakaus][PaulBakaus] \ (Open Web Developer Advocate 在 Google |工具、性能、动画、UX\) 。</span><span class="sxs-lookup"><span data-stu-id="da194-172">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google | Tools, Performance, Animation, UX\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="da194-174">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="da194-174">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors#paul-bakaus  
