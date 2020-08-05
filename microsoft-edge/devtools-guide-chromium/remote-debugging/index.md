---
title: 远程调试 Android 设备入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c77633c4844f0e576b7dff6574000a78c8c083da
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708534"
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

# 远程调试 Android 设备入门  

在 Android 设备上从 Windows 或 macOS 计算机远程调试实时内容。  以下教程页面教你如何完成以下操作。  

*   设置 Android 设备以进行远程调试，并从开发计算机中发现它。  
*   从开发计算机检查和调试 Android 设备上的实时内容。  
*   将 Android 设备中的内容说明截屏视频到开发计算机上的 DevTools 实例。  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> 远程调试目前不支持 iOS 设备上的 Microsoft Edge 应用。  以下指南专门针对 Android 设备上的远程调试 Microsoft Edge。
> 如果你有 macOS 设备，请按照[Brightcove 调试指南][BrightcoveSupportDebuggingMobileDevices]操作，以使用 Safari 在 iOS 设备上远程调试 Microsoft Edge。  有关 Safari 中的 Web 检查器工具的详细信息，请参阅[Safari Web 开发工具][AppleDeveloperSafariTools]。  

## 步骤1：发现 Android 设备  

下面的工作流适用于大多数用户。  有关更多帮助，请参阅[疑难解答： DevTools 未检测到 Android 设备](#troubleshooting-devtools-is-not-detecting-the-android-device)部分。  

1.  打开 Android 上的 "**开发工具选项**" 屏幕。  有关详细信息，请参阅[配置设备上的开发人员选项][AndroidDeveloperStudioDevOptions]。  
1.  选择 "**启用 USB 调试**"。  
1.  在开发计算机上，打开 "Microsoft Edge"。  
1.  导航到 `edge://inspect` Microsoft Edge 中的页面。  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge 中的 edge://inspect 页面" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       图 1.  `edge://inspect`Microsoft Edge 中的页面  
    :::image-end:::  
    
1.  使用 USB 电缆将 Android 设备直接连接到开发计算机。  第一次尝试连接时，通常会看到有关检测未知设备的 DevTools 的提示。  接受 Android 设备上的 "**允许 USB 调试**" 权限提示。  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android 设备上的 允许 USB 调试 权限提示" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       图 2.  Android 设备上的 "**允许 USB 调试**" 权限提示  
    :::image-end:::  
    
1.  如果你看到 Android 设备的模型名称，则 Microsoft Edge 已成功建立与你的设备的连接。  转到 "[步骤 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) " 部分。  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### 疑难解答： DevTools 未检测到 Android 设备  

使用以下提示来帮助你解决硬件的正确设置。  

*   如果您使用的是 USB 集线器，请尝试将 Android 设备直接连接到开发计算机。  
*   尝试在 Android 设备和开发计算机之间拔出 USB 电缆，然后重新插入 USB 电缆。  在 Android 和开发计算机屏幕解除锁定时完成任务。  
*   请确保您的 USB 电缆正常工作。  你应该能够从开发计算机检查 Android 设备上的文件。  

使用以下提示来帮助验证软件是否设置正确。  

*   如果开发计算机运行的是 Windows，请尝试手动安装 Android 设备的 USB 驱动程序。  有关详细信息，请参阅[安装 OEM USB 驱动程序][AndroidDeveloperToolsOemUsb]。  
*   某些 Windows 和 Android 设备的组合 \ （特别是 Samsung \）需要其他设置。  有关详细信息，请参阅[DevTools 设备在接通电源时不检测设备][Stackoverflow21925992]。  

使用以下提示可帮助你解决在 Android 设备上不能看到 "**允许 USB 调试**" 提示。  

*   断开连接并重新连接 USB 电缆的同时，DevTools 将集中在开发计算机上，并且显示 Android 主屏幕。  
    
    > [!NOTE]
    > 如果您的 Android 或开发计算机屏幕被锁定，您可能看不到提示。  

*   更新 Android 设备和开发计算机的显示设置，以便每个设备都不会进入睡眠状态。  
*   将 Android 的 USB 模式设置为 PTP。  有关详细信息，请参阅[Galaxy S4 不显示 "授权 USB 调试" 对话框][StackexchangeAndroid101933]。  
*   从 Android 设备上的 "**开发工具选项**" 屏幕中选择 "**撤消 USB 调试授权**"，将其重置为新状态。  

如果您发现此页面或 DevTools 设备上未提及的解决方案在堆栈溢出[时未检测到设备][Stackoverflow21925992]，请将您的解决方案添加到堆栈溢出问题<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->!  

## 步骤2：从开发计算机调试 Android 设备上的内容  

1.  在 Android 设备上打开 Microsoft Edge。  
1.  在 `edge://inspect` 页面中，你将看到 Android 设备的型号名称，后跟设备序列号。  在此下方，你应该看到在设备上运行的 Microsoft Edge 版本，其中版本号位于括号中。  每个打开的 Microsoft Edge 选项卡都将获取一个唯一的分区。  你可以从分区与该选项卡进行交互。  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="已连接的远程设备" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       图 3.  已连接的远程设备  
    :::image-end:::  
    
1.  在 "**打开包含 url 的选项卡**" 框中，输入 url，然后选择 "**打开**"。  页面将在 Android 设备上的新选项卡中打开。  
1.  选择您刚刚打开的 URL 旁边的 "**检查**"。  将打开一个新的 DevTools 实例。  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### 更多操作：焦点、重新加载或关闭选项卡  

选择要关注、重新加载或关闭的选项卡旁边的 "**焦点" 选项卡**、"**重新加载**" 或 "**关闭**"。  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="用于聚焦、重新加载或关闭选项卡的按钮" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   图 4.  用于聚焦、重新加载或关闭选项卡的按钮  
:::image-end:::  

### 检查元素  

转到 DevTools 实例的 "**元素**" 面板，将鼠标悬停在某个元素上，将其突出显示在 Android 设备的视口中。  

您也可以在 Android 设备屏幕上选择一个元素，以便在 "**元素**" 面板中选择该元素。  选择**Select Element** ![ DevTools 实例上的 "选择元素" ][ImageSelectElementIcon] 图标，然后在 Android 设备屏幕上选择该元素。  

> [!NOTE]
> 选择第一个选项后，"**选择元素**" 已禁用，因此必须在每次使用该功能时重新启用它。  

### 将 Android 屏幕说明截屏视频到开发计算机  

选择 "**切换说明截屏视频** ![ 切换 ][ImageToggleScreencastIcon] " 说明截屏视频图标可在 DevTools 实例中查看 Android 设备的内容。  

你可以通过以下方式与说明截屏视频交互。  

*   单击被转换为点击，在设备上触发正确的触摸事件。  
*   将计算机上的击键发送到设备。  
*   若要模拟捏出的手势，请 `Shift` 在拖动时按住。  
*   若要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针投掷。

> [!NOTE]
> 使用以下提示可帮助您说明截屏视频。  
> 
> *   Screencasts 仅显示页面内容。  说明截屏视频的透明部分表示设备接口，如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。  
> *   Screencasts 会对帧速率产生负面影响。  在测量滚动或动画时禁用 screencasting，以便更准确地了解页面性能。  
> *   如果你的 Android 设备屏幕锁定，你的说明截屏视频的内容将消失。  解锁 Android 设备屏幕以自动恢复说明截屏视频。  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "配置设备上的开发人员选项 |Android 开发人员"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序 |Android 开发人员"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 开发工具 |Apple 开发人员"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "在移动设备上调试 |Brightcove 支持"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb-Android 发烧友式堆栈交换"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "插入堆栈内溢时，DevTools 设备不检测设备"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
