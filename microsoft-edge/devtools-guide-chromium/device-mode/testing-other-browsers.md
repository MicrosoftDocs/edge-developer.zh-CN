---
title: 模拟和测试其他浏览器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: d5eb33ea4cd1224930e91898d2c711310202cfc0
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984976"
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





# 模拟和测试其他浏览器   




您的工作不能确保您的网站在 Microsoft Edge 和 Android 中运行得非常出色。  即使设备模式能够模拟 Iphone 之类的其他设备，我们也鼓励你查看其他浏览器提供的仿真的解决方案。  

### 摘要  

*   如果您没有特定设备，或者想要对某些内容执行专色检查，最佳选择是在浏览器内部直接模拟设备。  
*   通过设备模拟器和模拟器，你可以将你的开发网站从工作站上的一系列设备中模拟。  
*   基于云的模拟器使你能够跨不同平台自动处理你的网站的单元测试。  

## 浏览器模拟器  

浏览器模拟器对于测试网站的响应非常有用，但每个模拟器不会模拟 API、CSS 支持和你在移动浏览器上看到的某些行为的差异。  在实际设备上运行的浏览器上测试网站，以确保所有内容均按预期方式工作。  

### Firefox 响应式设计视图  

Firefox 有一个 [响应式设计视图][MDNResponsiveDesignMode] ，它鼓励你在特定设备方面停止思考，而改为通过拖动边缘来了解你的设计是如何在常见的屏幕大小或自己的大小上更改的。  

### EdgeHTML 仿真  

若要模拟 Windows 手机，请使用 Microsoft Edge \ (EdgeHTML \ ) [内置仿真][DevToolsEdgeHtmlEmulation]。  

使用 [IE 11 仿真][Ie11DevToolsEmulation] 模拟你的页面在较早版本的 Internet Explorer 中的外观。  

## 设备模拟器和模拟器  

设备模拟器和模拟器不仅模拟浏览器环境，还模拟整个设备。  每个测试都有助于测试需要操作系统集成的项目，例如用虚拟键盘的表单输入。  

### Android 模拟器  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

目前，无法在 Android 模拟器上安装 Microsoft Edge。  但是，你可以使用 Android 浏览器、Chromium 内容外壳和适用于 Android 的 Firefox，我们将在本指南的后面部分进行查看。  Chromium 内容 Shell 以 Microsoft Edge 的形式运行同一 Chromium 呈现引擎，但不会出现任何浏览器特定功能。  

Android 模拟器随附了 Android SDK，您需要在 [Android Studio][AndroidStudioDownload]中下载该 SDK。  然后按照说明 [设置虚拟设备][AndroidStudioCreateManageVirtualDevices] 并 [启动模拟器][AndroidStudioRunAppsAndroidEmulator]。  
启动仿真器后，单击浏览器图标，然后在 Android 旧版的常用浏览器中测试您的网站。  

#### Android 上的 Chromium 内容 shell  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Android Emulator Content Shell" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

若要安装 Android 的 Chromium 内容 Shell，请保持仿真器运行并运行以下命令。  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

现在，你可以通过 Chromium 内容 Shell 测试你的网站。  

#### Android 上的 Firefox  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Firefox Icon on Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

与 Chromium 内容外壳程序类似，你可以获取将 Firefox 安装到模拟器的 APK。  

[下载正确的 apk 文件][MozillaFirefoxDownload]。  

若要将文件安装到打开的模拟器或连接的 Android 设备上，请运行以下命令。  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### iOS 模拟器  

适用于 Mac OS X 的 iOS 模拟器附带了 Xcode，可 [从 App Store 进行安装][MacAppStoreXcode]。  

完成后，了解如何通过 [Apple 开发人员文档][AppleSimulatorHelp]处理模拟器。  

> [!NOTE]
> 若要避免每次希望使用 iOS 模拟器时都打开 Xcode，请将其打开，然后右键单击您的 dock 中的 iOS 模拟器图标，然后选择 " **保留在 dock 中**"。  现在只需在需要时单击此图标。  

###  Microsoft Edge (EdgeHTML)   

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="新式 IE VM" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   新式 IE VM  
:::image-end:::  

Microsoft Edge \ (EdgeHTML \ ) 虚拟机 \ (Vm \ ) 使你可以通过 VirtualBox \ (或 VMWare ) 访问计算机上的不同版本的 EdgeHTML 和 IE。  选择 ["下载" 页面上的虚拟机][MicrosoftDeveloperEdgeVms]。  

## 基于云的模拟器和模拟器  

如果无法使用仿真程序，并且无法访问实际设备，则基于云的模拟器是下一种最佳做法。  在真实设备和本地模拟器上使用基于云的模拟器的一个显著优势是，你可以跨不同平台自动处理你的网站的单元测试。  

*   [BrowserStack (商业) ][|::ref1::|] 最容易用于手动测试。  选择操作系统，选择你的浏览器版本和设备类型，选择要浏览的 URL，它会旋转托管的虚拟机，你可以与其进行交互。  你还可以在同一屏幕中运行多个模拟器，从而使你能够在多个设备上同时测试你的应用的外观。  
*   [SauceLabs (商业) ][SauceLabs] 使你能够在仿真器内运行单元测试，这对于通过您的网站编写流并随后在各种设备上观看视频录制的内容非常有用。  您还可以通过您的网站进行手动测试。  
*   [ (商业) 的任意位置的设备 ][AppExperience] 不使用模拟器，而是您能够远程控制的实时设备。  这在你需要在特定设备上重现问题且无法使用上述指南中的任何选项查看 bug 的情况下非常有用。  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) 找到，并由 [Meggin Kearney][MegginKearney] (技术 ) 作者 \ (在 Google | 上打开 Web 开发人员的 [Bakaus][PaulBakaus] 。工具、性能、动画、UX \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
