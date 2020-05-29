---
title: 远程调试 Android 设备入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a9002ca82e6e0dcaf7f174b336e5c640929a561b
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611817"
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




<!--
<style>
.devtools-inline {
  max-height: 1em;
  vertical-align: middle;
}
</style>
-->  
# 远程调试 Android 设备入门   



在 Android 设备上从 Windows 或 macOS 计算机远程调试实时内容。  本教程将指导你如何：  

*   设置 Android 设备以进行远程调试，并从开发计算机中发现它。  
*   从开发计算机检查和调试 Android 设备上的实时内容。  
*   将 Android 设备中的内容说明截屏视频到开发计算机上的 DevTools 实例。  

<!--
> ##### Figure 1  
> Remote Debugging lets you inspect a page running on an Android device from your development machine  
> ![Remote Debugging lets you inspect a page running on an Android device from your development machine][ImageRemoteDebugging]  -->

## 步骤1：发现 Android 设备   

下面的工作流适用于大多数用户。  请参阅[疑难解答： DevTools 未检测到 Android 设备](#troubleshooting-devtools-is-not-detecting-the-android-device)，获取更多帮助。  

1.  打开 Android 上的 "**开发工具选项**" 屏幕。  请参阅[配置设备上的开发人员选项](https://developer.android.com/studio/debug/dev-options.html)。  
1.  选择 "**启用 USB 调试**"。  
1.  在开发计算机上，打开 "Microsoft Edge"。  
1.  [打开 DevTools][DevToolsOpen]。  
1.  在 DevTools 中，选择**主菜单**， `...` 然后选择 "**更多工具**  >  **远程设备**"。  
    
    > ##### 图 1  
    > 通过**主菜单**打开 "**远程设备**" 选项卡  
    > ![通过主菜单打开 "远程设备" 选项卡][ImageOpenRemoteDevices]  

1.  在 DevTools 中，打开 "**设置**" 选项卡。  

1.  请确保 "**发现 USB 设备**" 复选框已启用。  
    
    > ##### 图 2  
    > "**发现 USB 设备**" 复选框已启用  
    > ![已启用 "发现 USB 设备" 复选框][ImageDiscoverUSBDevices]  

1.  使用 USB 电缆将 Android 设备直接连接到开发计算机。  第一次执行此操作时，通常会看到 DevTools 检测到未知设备。  如果你看到一个绿点和**连接**到 Android 设备的模型名称下方的文本，则 DevTools 已成功建立与你的设备的连接。  继续执行[步骤 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)。  
    <!--
    > ##### Figure 4  
    > The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    > ![The Remote Devices tab has successfully detected an unknown device that is pending authorization][ImageUnknownDevice]  -->

1.  如果你的设备显示为 "**未知**"，请在 Android 设备上接受 "**允许 USB 调试**" 权限提示。  

### 疑难解答： DevTools 未检测到 Android 设备   

请确保您的硬件设置正确：  

*   如果您使用的是 USB 集线器，请尝试将 Android 设备直接连接到开发计算机。  
*   尝试在 Android 设备和开发计算机之间拔出 USB 电缆，然后重新插入。  在 Android 和开发计算机屏幕解锁时执行此操作。  
*   请确保您的 USB 电缆正常工作。  你应该能够从开发计算机检查 Android 设备上的文件。  

请确保您的软件设置正确：  

*   如果开发计算机运行的是 Windows，请尝试手动安装 Android 设备的 USB 驱动程序。  请参阅[安装 OEM USB 驱动程序][AndroidUSBDrivers]。  
    
*   某些 Windows 和 Android 设备（特别是 Samsung）的组合需要额外设置。  请参阅 [DevTools 设备插入时不检测设备] [StackOverflowDevicesNotDetected]。  
    
如果您在 Android 设备上看不到 "**允许 USB 调试**" 提示，请尝试：  

*   断开连接并重新连接 USB 电缆的同时，DevTools 将集中在开发计算机上，并且显示 Android 主屏幕。  换句话说，有时当 Android 或开发计算机屏幕锁定时，不会显示提示。
*   更新 Android 设备和开发计算机的显示设置，使其永不进入睡眠状态。  
*   将 Android 的 USB 模式设置为 PTP。  请参阅[Galaxy S4 不显示 "授权 USB 调试" 对话框][StackExchangeGalaxyS4DoesNotShowDialogBox]。  
*   从 Android 设备上的 "**开发工具选项**" 屏幕中选择 "**撤消 USB 调试授权**"，将其重置为新状态。  

如果你发现本部分中未提及的解决方案或 "DevTools 设备" 在插入时未检测到设备 "[StackOverflowDevicesNotDetected]，或者请添加该堆栈溢出问题的答案<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->!  

## 步骤2：从开发计算机调试 Android 设备上的内容   

1.  在 Android 设备上打开 Microsoft Edge。  

1.  在 "**远程设备**" 选项卡中，选择与你的 Android 设备模型名称相匹配的选项卡。  
    在此页的顶部，你可以看到 Android 设备的模型名称，后跟其序列号。  在此下方，你应该看到在设备上运行的 Microsoft Edge 版本，其中版本号位于括号中。  每个打开的 Microsoft Edge 选项卡都将获取其自己的分区。  您可以从此部分与该选项卡进行交互。  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->
    <!--
    > ##### Figure 5  
    > A connected remote device  
    > ![A connected remote device][ImageConnectedRemoteDevice]  -->

1.  在 "**新建选项卡**" 文本框中，输入 URL，然后选择 "**打开**"。  页面将在 Android 设备上的新选项卡中打开。  

1.  选择您刚刚打开的 URL 旁边的 "**检查**"。  将打开一个新的 DevTools 实例。  在 Android 设备上运行的 Microsoft Edge 版本决定了在开发计算机上打开的 DevTools 版本。  
    因此，如果 Android 设备运行的是较旧版本的 Microsoft Edge，则 DevTools 实例可能看起来与你使用的版本有所不同。  

### 更多操作：重新加载、焦点或关闭选项卡   

选择**More Options** `...` 要重新加载、焦点或关闭的选项卡旁边的 "更多选项"。  
<!--
> ##### Figure 6  
> The menu for reloading, focusing, or closing a tab  
> ![The menu for reloading, focusing, or closing a tab][ImageReload]  -->

### 检查元素   

转到 DevTools 实例的 "**元素**" 面板，将鼠标悬停在某个元素上，将其突出显示在 Android 设备的视口中。  

您也可以在 Android 设备屏幕上选择一个元素，以便在 "**元素**" 面板中选择该元素。  在 DevTools 实例上选择 "**选择元素**"，然后在 ![ ][ImageSelectElementIcon] Android 设备屏幕上选择该元素。  

> [!NOTE]
> 选择第一个选项后，"**选择元素**" 已禁用，因此必须在每次使用此功能时重新启用它。  

### 将 Android 屏幕说明截屏视频到开发计算机   

选择 "**切换说明截屏视频** ![ 切换 ][ImageToggleScreencastIcon] " 说明截屏视频可在 DevTools 实例中查看 Android 设备的内容。  

你可以通过多种方式与说明截屏视频交互：  

*   单击被转换为点击，在设备上触发正确的触摸事件。  
*   将计算机上的击键发送到设备。  
*   若要模拟捏出的手势，请 `Shift` 在拖动时按住。  
*   若要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针投掷。

Screencasts 上的一些笔记：  

*   Screencasts 仅显示页面内容。  说明截屏视频的透明部分表示设备接口，如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。  
*   Screencasts 会对帧速率产生负面影响。  在测量滚动或动画时禁用 screencasting，以便更准确地了解页面性能。  
*   如果你的 Android 设备屏幕锁定，你的说明截屏视频的内容将消失。  解锁 Android 设备屏幕以自动恢复说明截屏视频。  





<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!--[ImageRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--remote-debugging.msft.png "old Figure 1:  Remote Debugging lets you inspect a page running on an Android device from your development machine"  -->  
[ImageOpenRemoteDevices]：/microsoft-edge/devtools-guide-chromium/media/remote-debugging-more-tools-remote-devices.msft.png "图1：通过主菜单打开" 远程设备 "选项卡  
[ImageDiscoverUSBDevices]：/microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-tab.msft.png "图2：已启用" 发现 USB 设备 "复选框  
<!--[ImageUnknownDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--unknown-device.msft.png "old Figure 4:  The Remote Devices tab has successfully detected an unknown device that is pending authorization"  -->  
<!--[ImageConnectedRemoteDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--connected-remote-device.msft.png "old Figure 5:  A connected remote device"  -->
<!--[ImageReload]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--reload.msft.png "old Figure 6: The menu for reloading, focusing, or closing a tab"  -->

<!-- links -->  

[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  

[AndroidUSBDrivers]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序 |Android 开发人员"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  
[StackOverflowDevicesNotDetected]： https://stackoverflow.com/questions/21925992 "当插入堆栈内溢时，DevTools 设备不检测设备"  

[StackExchangeGalaxyS4DoesNotShowDialogBox]: https://android.stackexchange.com/questions/101933 "adb-Android 发烧友式堆栈交换"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
