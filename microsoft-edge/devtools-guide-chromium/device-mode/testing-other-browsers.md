---
description: 你的作业不会以确保你的站点在 Microsoft Edge 和 Android 中运行出色结束。  即使设备模式能够模拟 iPhone 等一系列其他设备，我们也鼓励你查看其他浏览器提供的模拟解决方案。
title: 模拟和测试其他浏览器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 6b1239db373bd13d798ac90ac47a10878d07cdcb
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398684"
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

# <a name="emulate-and-test-other-browsers"></a>模拟和测试其他浏览器  

你的作业不会以确保你的站点在 Microsoft Edge 和 Android 中运行出色结束。  即使设备模式能够模拟 iPhone 等一系列其他设备，我们也鼓励你查看其他浏览器提供的模拟解决方案。  

### <a name="summary"></a>摘要  

*   当你没有特定设备，或者想要对某些内容执行专线检查时，最佳选择是在你的浏览器内模拟该设备。  
*   设备仿真器和模拟器使你可以模拟工作站中的一系列设备上的开发网站。  
*   基于云的仿真器使你可以跨不同平台自动执行网站单元测试。  

## <a name="browser-emulators"></a>浏览器仿真器  

浏览器仿真器非常适用于测试网站的响应性，但每个仿真器不会模拟 API、CSS 支持和移动浏览器上显示的某些行为的差异。  在真实设备上运行的浏览器上测试网站，确保一切按预期方式运行。  

### <a name="firefox-responsive-design-view"></a>Firefox 响应式设计视图  

Firefox 具有[][MDNResponsiveDesignMode]响应式设计视图，鼓励你停止考虑特定设备，而是通过拖动边缘来探索设计在常见屏幕大小或你自己的大小下如何更改。  

### <a name="edgehtml-emulation"></a>EdgeHTML 仿真  

若要模拟 Windows 手机，请使用 Microsoft Edge \ (EdgeHTML\) [内置的模拟][DevToolsEdgeHtmlEmulation]。  

使用 [IE 11 模拟][Ie11DevToolsEmulation] 模拟页面在早期版本的 Internet Explorer。  

## <a name="device-emulators-and-simulators"></a>设备仿真器和模拟器  

设备模拟器和仿真器不仅模拟浏览器环境，还模拟整个设备。  每个项都可用于测试需要操作系统集成（例如，使用虚拟键盘的表单输入）的项。  

### <a name="android-emulator"></a>Android 仿真器  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

目前，无法将 Microsoft Edge 安装在 Android 仿真器上。  但是，您可以使用 Android 浏览器、Chromium 内容 Shell 和 Firefox for Android，我们将在本指南稍后介绍这些内容。  Chromium 内容 Shell 与 Microsoft Edge 运行相同的 Chromium 呈现引擎，但不带任何特定于浏览器的功能。  

Android 仿真器附带需要下载的 Android SDK 作为 [Android Studio][AndroidStudioDownload]的一部分。  然后按照说明[设置虚拟设备并][AndroidStudioCreateManageVirtualDevices][启动仿真器][AndroidStudioRunAppsAndroidEmulator]。  
启动仿真器后，选择浏览器图标，在适用于 Android 的旧股票浏览器上测试您的网站。  

#### <a name="chromium-content-shell-on-android"></a>Android 上的 Chromium 内容 shell  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Android Emulator Content Shell" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

若要安装适用于 Android 的 Chromium 内容 Shell，请保持仿真器运行并运行以下命令。  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

现在，您可以使用 Chromium 内容命令行管理程序测试您的网站。  

#### <a name="firefox-on-android"></a>Android 上的 Firefox  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Firefox Icon on Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

与 Chromium 内容 Shell 类似，你可以获取 APK 以将 Firefox 安装到仿真器上。  

[下载正确的 .apk 文件][MozillaFirefoxDownload]。  

若要将该文件安装到打开的仿真器或连接的 Android 设备上，请运行以下命令。  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <a name="ios-simulator"></a>iOS 模拟器  

适用于 Mac OS X 的 iOS 模拟器附带 Xcode，你可以[从应用商店安装 Xcode。][MacAppStoreXcode]  

完成后，了解如何通过 Apple 开发人员文档使用 [模拟器][AppleSimulatorHelp]。  

> [!NOTE]
> 若要避免每次想要使用 iOS 模拟器时都打开 Xcode，请打开它，将鼠标悬停在扩展坞中的 iOS 模拟器图标上，打开上下文菜单 \ (右键单击\) ，然后选择"保持为扩展坞 **"。**  现在只需在需要图标时选择它。  

###  <a name="microsoft-edge-edgehtml"></a>Microsoft Edge (EdgeHTML)   

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="新式 IE VM" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   新式 IE VM  
:::image-end:::  

Microsoft Edge \ (EdgeHTML\) 虚拟机 \ (VM\) 使您能够通过 VirtualBox \ (或 VMWare\) 访问计算机上不同版本的 EdgeHTML 和 IE。  在 [下载页面上选择虚拟机][MicrosoftDeveloperEdgeVms]。  

## <a name="cloud-based-emulators-and-simulators"></a>基于云的模拟器和模拟器  

如果你无法使用仿真器，并且无法访问真实的设备，则基于云的仿真器是下一个最佳选择。  与实际设备和本地仿真器不同，基于云的模拟器的一大优点是，你可以跨不同平台为网站自动执行单元测试。  

*   [BrowserStack (商业) ][|::ref1::|] 最易于用于手动测试。  选择操作系统，选择浏览器版本和设备类型，选择要浏览的 URL，然后它会旋转可与你交互的托管虚拟机。  还可以在同一个屏幕中运行多个仿真器，从而同时跨多个设备测试应用的外观。  
*   [利用 (Commercial) ， ][SauceLabs] 可以在仿真器内运行单元测试，这可能对编写网站流脚本并观看以后在各种设备上录制此内容的视频非常有用。  您还可以对网站执行手动测试。  
*   [商业 (设备) ][AppExperience] 不使用仿真器，而是能够远程控制的真实设备。  如果你需要在特定设备上重现问题，并且可能未使用之前指南中的任一选项显示 Bug，这将非常有用。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsEdgeHtmlEmulation]: /microsoft-edge/devtools-guide/emulation "DevTools (EdgeHTML) - 模拟|Microsoft Docs"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "模拟浏览器、屏幕大小和 GPS 位置|Microsoft Docs"  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "下载虚拟机"  

[AndroidStudioCreateManageVirtualDevices]: https://developer.android.com/tools/devices/managing-avds.html "创建和管理虚拟设备|Android 开发人员"  
[AndroidStudioDownload]:  https://developer.android.com/sdk/installing/studio.html "下载 Android Studio 和 SDK |Android 开发人员"  
[AndroidStudioRunAppsAndroidEmulator]: https://developer.android.com/tools/devices/emulator.html "在 Android 仿真器设备上|Android 开发人员"  

[AppExperience]: https://www.sigos.com/app-experience/ "应用体验"  
[AppleSimulatorHelp]: https://help.apple.com/simulator/mac/current "模拟器帮助 - 当前|Apple"  
[BrowserStack]: https://www.browserstack.com/automate "BrowserStack"  
[MacAppStoreXcode]: https://itunes.apple.com/app/xcode/id497799835 "Mac 应用商店上的 Xcode"  
[MDNResponsiveDesignMode]: https://developer.mozilla.org/docs/Tools/Responsive_Design_View "响应式设计模式|MDN"  
[MozillaFirefoxDownload]: https://www.mozilla.org/firefox/all/#product-android-beta "下载 Firefox 浏览器"  
[SauceLabs]: https://saucelabs.com "一些实验室"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers)由 Google (的[Meggin Kearney][MegginKearney] \ (Tech Writer\) 和[Paul Bakaus][PaulBakaus] \ (Open Web Developer Advocate 创作|工具、性能、动画、UX\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
