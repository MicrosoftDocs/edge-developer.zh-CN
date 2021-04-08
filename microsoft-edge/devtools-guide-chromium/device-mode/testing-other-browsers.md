---
description: 你的作业不会以确保你的站点在 Microsoft Edge 和 Android 中运行出色结束。  即使设备模式能够模拟 iPhone 等一系列其他设备，我们也鼓励你查看由其他浏览器提供的模拟解决方案。
title: 模拟和测试其他浏览器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 22153a54df7c5b92236a745be8e3bbac9a52d247
ms.sourcegitcommit: fa8bedfc83fbd1c4ce7bda8c69586c4f24007beb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "11481364"
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

你的作业不会以确保你的站点在 Microsoft Edge 和 Android 中运行出色结束。  即使设备模式能够模拟 iPhone 等一系列其他设备，我们也鼓励你查看由其他浏览器提供的模拟解决方案。  

### <a name="summary"></a>摘要  

*   当你没有特定设备，或者想要对某些内容进行专线检查时，最佳选择是模仿浏览器内的设备。  
*   设备仿真器和模拟器使你可以模拟工作站中各种设备上的开发网站。  
*   基于云的仿真器使你可以跨不同平台自动执行网站单元测试。  

## <a name="browser-emulators"></a>浏览器仿真器  

浏览器仿真器非常适用于测试网站的响应性，但每个模拟器不会模拟 API、CSS 支持和移动浏览器上显示的某些行为的差异。  在真实设备上运行的浏览器上测试网站，确保一切按预期方式运行。  

### <a name="firefox-responsive-design-view"></a>Firefox 响应式设计视图  

Firefox 具有响应 [式][MDNResponsiveDesignMode] 设计视图，该视图鼓励您停止就特定设备进行思考，而是通过拖动边缘来探索设计如何以常见屏幕大小或您自己的大小进行更改。  

### <a name="edgehtml-emulation"></a>EdgeHTML 模拟  

若要模拟 Windows Phones，请使用 Microsoft Edge \ (EdgeHTML\) [内置模拟][ArchiveMicrosoftEdgeDevtoolsEmulation]。  

使用 [IE 11 仿真][Ie11DevToolsEmulation] 模拟页面在早期版本的 Internet Explorer。  

## <a name="device-emulators-and-simulators"></a>设备仿真器与模拟器  

设备模拟器和仿真器不仅模拟浏览器环境，还模拟整个设备。  每个功能都可用于测试需要操作系统集成（例如，使用虚拟键盘的表单输入）的项。  

### <a name="android-emulator"></a>Android 仿真器  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

目前，无法将 Microsoft Edge 安装在 Android 仿真器上。  但是，您可以使用 Android 浏览器、Chromium 内容 Shell 和 Firefox for Android，我们将在本指南的稍后部分介绍这些内容。  Chromium 内容 Shell 运行与 Microsoft Edge 相同的 Chromium 呈现引擎，但不带任何特定于浏览器的功能。  

Android 仿真器附带 Android SDK，你需要下载为 Android [Studio][AndroidStudioDownload]的一部分。  然后按照说明[设置虚拟设备并][AndroidStudioCreateManageVirtualDevices][启动仿真器][AndroidStudioRunAppsAndroidEmulator]。  
启动仿真器后，选择浏览器图标，在适用于 Android 的旧股票浏览器上测试你的网站。  

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

现在，您可以使用 Chromium 内容 Shell 测试您的网站。  

#### <a name="firefox-on-android"></a>Android 上的 Firefox  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Firefox Icon on Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

与 Chromium 内容 Shell 类似，您可以获取 APK 以将 Firefox 安装到仿真器上。  

[下载正确的 .apk 文件][MozillaFirefoxDownload]。  

若要将文件安装到打开的仿真器或连接的 Android 设备上，请运行以下命令。  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <a name="ios-simulator"></a>iOS 模拟器  

适用于 Mac OS X 的 iOS 模拟器附带 Xcode，从 [应用商店安装][MacAppStoreXcode]。  

完成后，了解如何通过 Apple 开发人员文档使用 [模拟器][AppleSimulatorHelp]。  

> [!NOTE]
> 若要避免每次想要使用 iOS 模拟器时都打开 Xcode，请将其打开，将鼠标悬停在扩展坞中的 iOS 模拟器图标上，打开上下文菜单 \ (右键单击\) ，然后选择"保持在扩展坞中 **"。**  现在只要需要图标即可。  

###  <a name="microsoft-edge-edgehtml"></a>Microsoft Edge (EdgeHTML)   

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="新式 IE VM" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   新式 IE VM  
:::image-end:::  

Microsoft Edge \ (EdgeHTML\) Virtual Machines \ (VM\) 使您能够通过 VirtualBox \ (或 VMWare\) 访问计算机上不同版本的 EdgeHTML 和 IE。  在 [下载页面上选择虚拟机][MicrosoftDeveloperEdgeVms]。  

## <a name="cloud-based-emulators-and-simulators"></a>基于云的模拟器和模拟器  

如果你无法使用仿真器，并且无法访问真实设备，则基于云的仿真器是下一个最佳选择。  与实际设备和本地仿真器不同，基于云的模拟器的一大优点是，可以跨不同平台自动执行网站单元测试。  

*   [BrowserStack (商业) ][|::ref1::|] 是最容易用于手动测试。  选择操作系统，选择浏览器版本和设备类型，选择要浏览的 URL，然后它会调节可与你交互的托管虚拟机。  还可以在同一个屏幕中运行多个仿真器，从而可以同时跨多个设备测试应用的外观。  
*   [使用 Commercial (Labs) ][SauceLabs] 可以在仿真器内运行单元测试，这可能非常有用，可用于编写通过网站的流脚本，并随后在各种设备上观看有关此内容的视频录制。  您还可以对网站执行手动测试。  
*   [商业 (设备) ][AppExperience] 不使用仿真器，而是使用你可以远程控制的真实设备。  如果你需要在特定设备上重现问题，并且可能未使用之前指南中的任一选项显示 Bug，这将非常有用。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>与 Microsoft Edge 开发人员工具团队联系  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers)由[Meggin Kearney][MegginKearney] \ (Tech Writer\) 和[Paul Bakaus][PaulBakaus] \ (Open Web Developer Advocate 在 Google |工具、性能、动画、UX\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
