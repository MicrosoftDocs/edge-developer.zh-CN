---
description: 从 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。
title: Android 设备远程调试入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: 2beab5bf6d4b58dc93d883f5114e168213053e84
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439563"
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

# <a name="get-started-with-remote-debugging-android-devices"></a>Android 设备远程调试入门  

从你的 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。  下面的教程页面指导你如何完成以下操作。  

*   设置 Android 设备进行远程调试，然后从开发计算机中发现。  
*   在开发设备上检查和调试 Android 设备上的实时内容。  
*   将 Android 设备中的内容截屏到开发计算机上的开发工具实例上。  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> 当前不支持在 iOS 设备上远程调试 Microsoft Edge 应用程序。   以下指南专门针对 Android 设备上的 Microsoft Edge 进行远程调试。
> 如果使用的是 macOS 设备，请按照 [Brightcove 调试指南][BrightcoveSupportDebuggingMobileDevices]使用 Safari 在 iOS 设备上远程调试 Microsoft Edge。  有关 Safari 中的 Web 检查器工具的更多信息，请导航至 [Safari Web 开发工具][AppleDeveloperSafariTools]。  

## <a name="step-1-discover-your-android-device"></a>步骤 1：发现 Android 设备  

下面的工作流适用于大多数用户。  有关更多帮助信息，请导航至[疑难解答：DevTools 未检测 Android 设备](#troubleshooting-devtools-is-not-detecting-the-android-device)一节。  

1.  打开 Android 上的“**开发人员选项**”屏幕。  有关更多信息，请导航至[配置设备上开发人员选项][AndroidDeveloperStudioDevOptions]。  
1.  选择“**启用 USB 调试**”。  
1.  在开发计算机上，打开 Microsoft Edge。  
1.  导航到 Microsoft Edge 中的 `edge://inspect` 页面。  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge 中的 edge://inspect 页面" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       图 1.  Microsoft Edge 中的 `edge://inspect` 页面  
    :::image-end:::  
    
1.  使用 USB 电缆将 Android 设备直接连接到开发计算机。  首次尝试连接时，将显示有关开发工具检测未知设备的提示。  在 Android 设备上接受“**允许 USB 调试**”权限提示。  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android 设备上的“允许 USB 调试”权限提示" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       图 2.  Android 设备上的“**允许 USB 调试**”权限提示  
    :::image-end:::  
    
1.  如果显示 Android 设备的型号名称，则 Microsoft Edge 已成功与设备建立连接。  继续[第 2 步](#step-2-debug-content-on-your-android-device-from-your-development-machine)部分。  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <a name="troubleshooting-devtools-is-not-detecting-the-android-device"></a>疑难解答：DevTools 未检测 Android 设备  

使用以下提示可帮助你对硬件的正确设置进行故障排除。  

*   如果使用 USB 集线器，尝试将 Android 设备直接连接到开发计算机。  
*   尝试拔下 Android 设备与开发机器之间的 USB 电缆，然后重新插入 USB 电缆。  解锁 Android 和开发计算机屏幕时完成任务。  
*   确保 USB 电缆正常工作。  应该能够在开发计算机上检查 Android 设备上的文件。  

使用以下提示可帮助你验证软件是否正确设置。  

*   如果你的开发计算机运行的是 Windows，请尝试手动为 Android 设备安装 USB 驱动程序。  有关详细信息，请导航到[安装 OEM USB 驱动程序][AndroidDeveloperToolsOemUsb]。  
*   Windows 和 Android 设备\(尤其是 Samsung \)的某些组合需要其他设置。  有关详细信息，请导航到[插入时开发工具设备无法检测到设备。][Stackoverflow21925992]  

如果 Android 设备上未显示“**允许 USB 调试**”提示，请使用以下提示来帮助你排除故障。  

*   开发工具专注于开发计算机并且显示 Android 主屏幕时，断开 USB 电缆连接，然后重新连接。  
    
    > [!NOTE]
    > 如果 Android 或开发计算机屏幕已锁定，则显示提示。  

*   更新 Android 设备和开发机的显示设置，以使每台设备都不会进入睡眠状态。  
*   将 Android 的 USB 模式设置为 PTP。  有关更多信息，请导航至 [Galaxy S4 不显示“授权 USB 调试”对话框][StackexchangeAndroid101933]。  
*   从 Android 设备上的“**开发人员选项**”屏幕上选择“**撤销 USB 调试授权**”，以将其重置为新状态。  

如果找到未在本页面或堆栈溢出的[插入时开发工具设备无法检测到设备][Stackoverflow21925992]上提及的解决方案，请将解决方案添加到堆栈溢出问题<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->.  

## <a name="step-2-debug-content-on-your-android-device-from-your-development-machine"></a>步骤 2：从开发计算机调试 Android 设备上的内容  

1.  在 Android 设备上打开 Microsoft Edge。  
1.  导航到 `edge://inspect` ，将显示 Android 设备的型号名称，后跟设备序列号。  在下面，应显示设备上运行的 Microsoft Edge 版本，括号中会显示版本号。  每个打开的 Microsoft Edge 选项卡获取一个唯一部分。  可以从一个部分中与该选项卡进行交互。  <!--If there are any apps using WebView, a section for each of those apps should be displayed, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="连接的远程设备" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       图 3.  连接的远程设备  
    :::image-end:::  
    
1.  在“**使用 URL 打开选项卡 **“文本框中，输入 URL 并选择“**打开**”。  该页面将在 Android 设备上的新选项卡中打开。  
1.  选择刚打开 URL 旁边的“**检查**”。  新的开发工具实例打开。  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <a name="more-actions-focus-refresh-or-close-a-tab"></a>更多操作：聚焦、刷新或关闭选项卡  

在要聚焦、刷新或关闭的选项卡旁边，选择“**聚焦选项卡**”、“**重新加载**”或“**关闭**”。  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="用于聚焦、刷新或关闭选项卡的按钮" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   图 4.  用于聚焦、刷新或关闭选项卡的按钮  
:::image-end:::  

### <a name="inspect-elements"></a>检查元素  

导航到开发工具实例的“**元素**”工具，然后将鼠标悬停在某个元素上以在 Android 设备的视口中突出显示。  

还可以在 Android 设备屏幕上选择一个元素，然后在“**元素 **”工具中将其选中。  选择开发工具实例中“**选择元素**” \(![选择元素](../media/select-element-icon.msft.png)\)图标，然后在 Android 设备屏幕上选择元素。  

> [!NOTE]
> 第一次选择后将禁用“** 选择元素**”，因此每次使用功能时都必须重新启用。  

### <a name="screencast-your-android-screen-to-your-development-machine"></a>将 Android 屏幕截屏到开发计算机  

选择“**切换截屏视频**” \(![切换截屏视频](../media/toggle-screencast-icon.msft.png)\) 图标可在开发工具实例中查看 Android 设备的内容。  

可以通过以下方式与截屏视频进行交互。  

*   选择将转换为点击，在设备上触发适当的触摸事件。  
*   计算机上的击键会发送到设备。  
*   若要模拟收缩手势，拖动时按住 `Shift`。  
*   如果要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针拖动。

> [!NOTE]
> 使用以下提示来帮助你进行截屏。  
> 
> *   截屏视频仅显示页面内容。  截屏视频的透明部分表示设备界面，例如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。  
> *   截屏视频会对帧速率产生负面影响。  在测量滚动或动画时禁用截屏视频，以更准确地了解页面性能。  
> *   如果 Android 设备屏幕锁定，截屏视频的内容将消失。  解锁 Android 设备屏幕以自动恢复截屏视频。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "配置设备上开发人员选项 | Android 开发人员"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序 | Android 开发人员"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 开发工具| Apple 开发人员"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "在移动设备上调试 | Brightcove 支持"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb - Android Enthusiast Stack Exchange"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "插入时开发工具设备无法检测到设备 - 堆栈溢出"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
