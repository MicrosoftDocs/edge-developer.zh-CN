---
description: 从 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。
title: 远程调试 Android 设备入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 61fad793ca03dbef68a5f769dbfd25e780fd9930
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398257"
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

# <a name="get-started-with-remote-debugging-android-devices"></a>远程调试 Android 设备入门  

从 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。  以下教程页面将指导你如何完成以下操作。  

*   设置 Android 设备进行远程调试，然后从开发计算机中发现它。  
*   从开发计算机检查和调试 Android 设备上的实时内容。  
*   将 Android 设备中的内容屏蔽到开发计算机上 DevTools 实例。  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> 目前不支持在 iOS 设备上远程调试 Microsoft Edge 应用。  以下指南专门侧重于在 Android 设备上远程调试 Microsoft Edge。
> 如果你有 macOS 设备，请按照 [Brightcove 调试][BrightcoveSupportDebuggingMobileDevices] 指南使用 Safari 在 iOS 设备上远程调试 Microsoft Edge。  有关 Safari 中的 Web 检查器工具详细信息，请导航到 [Safari Web 开发工具][AppleDeveloperSafariTools]。  

## <a name="step-1-discover-your-android-device"></a>步骤 1：发现 Android 设备  

下面的工作流适用于大多数用户。  若要获得更多帮助，请导航到 ["疑难解答：DevTools](#troubleshooting-devtools-is-not-detecting-the-android-device) 未检测 Android 设备"部分。  

1.  在 Android **上** 打开"开发人员选项"屏幕。  有关详细信息，请导航到["配置设备上的开发人员选项"。][AndroidDeveloperStudioDevOptions]  
1.  选择 **"启用 USB 调试"。**  
1.  在开发计算机上，打开 Microsoft Edge。  
1.  导航到 `edge://inspect` Microsoft Edge 中的页面。  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge edge://inspect页面" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       图 1.  `edge://inspect`Microsoft Edge 中的页面  
    :::image-end:::  
    
1.  使用 USB 电缆将 Android 设备直接连接到开发计算机。  首次尝试连接时，应显示有关 DevTools 检测未知设备的提示。  接受 **Android 设备上的"允许 USB** 调试"权限提示。  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android 设备上的"允许 USB 调试"权限提示" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       图 2.  Android **设备上的"允许 USB** 调试"权限提示  
    :::image-end:::  
    
1.  如果显示 Android 设备的型号名称，则 Microsoft Edge 已成功建立与设备的连接。  继续步骤 [2](#step-2-debug-content-on-your-android-device-from-your-development-machine) 部分。  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <a name="troubleshooting-devtools-is-not-detecting-the-android-device"></a>疑难解答：DevTools 未检测到 Android 设备  

使用以下提示可帮助你解决硬件的正确设置问题。  

*   如果你使用的是 USB 集线器，请尝试将 Android 设备直接连接到开发计算机。  
*   请尝试拔下 Android 设备和开发计算机之间的 USB 电缆，然后重新插入 USB 电缆。  解锁 Android 屏幕和开发计算机屏幕时完成任务。  
*   确保 USB 电缆正常工作。  你应该能够从开发计算机检查 Android 设备上的文件。  

使用以下提示可帮助你验证软件是否正确设置。  

*   如果你的开发计算机正在运行 Windows，请尝试手动为 Android 设备安装 USB 驱动程序。  有关详细信息，请导航到["安装 OEM USB 驱动程序"。][AndroidDeveloperToolsOemUsb]  
*   Windows 和 Android 设备的一些组合 \ (特别是 Samsung\) 需要额外的设置。  有关详细信息，请导航到 [DevTools 设备在插入时检测设备][Stackoverflow21925992]。  

如果你的 Android 设备上未显示"允许 **USB** 调试"提示，请使用以下提示来帮助你排除故障。  

*   断开 USB 电缆的连接，然后重新连接 U 盘，同时 DevTools 专注于开发计算机，并且 Android 主屏幕显示。  
    
    > [!NOTE]
    > 如果 Android 或开发计算机屏幕已锁定，则显示提示。  

*   更新 Android 设备和开发计算机显示设置，以便每个设备从不进入睡眠状态。  
*   将 Android 的 USB 模式设置为 PTP。  有关详细信息，请导航到 ["开发公司 S4"不会显示"授权 USB 调试"对话框][StackexchangeAndroid101933]。  
*   Choose **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.  

如果发现此页或 [DevTools 设备][Stackoverflow21925992] 未在 Stack Overflow 上插入时检测到设备的解决方案，请将你的解决方案添加到 Stack Overflow 问题<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->.  

## <a name="step-2-debug-content-on-your-android-device-from-your-development-machine"></a>步骤 2：从开发计算机调试 Android 设备上的内容  

1.  在 Android 设备上打开 Microsoft Edge。  
1.  导航到 ，将显示 Android 设备的型号名称，后 `edge://inspect` 跟设备序列号。  在下面，应显示设备上运行的 Microsoft Edge 版本，括号中显示版本号。  每个打开的 Microsoft Edge 选项卡获取一个唯一部分。  You may interact with that tab from a section.  <!--If there are any apps using WebView, a section for each of those apps should be displayed, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="连接的远程设备" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       图 3.  连接的远程设备  
    :::image-end:::  
    
1.  在**包含 URL 文本框的"打开**"选项卡中，输入 URL，然后选择"**打开"。**  该页面将在 Android 设备上的新选项卡中打开。  
1.  选择 **刚** 打开的 URL 旁边的"检查"。  将打开一个新的 DevTools 实例。  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <a name="more-actions-focus-refresh-or-close-a-tab"></a>更多操作：焦点、刷新或关闭选项卡  

选择**焦点选项卡****、重新加载****或关闭**要对焦、刷新或关闭的选项卡旁边的选项卡。  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="用于焦点、刷新或关闭选项卡的按钮" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   图 4.  用于焦点、刷新或关闭选项卡的按钮  
:::image-end:::  

### <a name="inspect-elements"></a>检查元素  

导航到**** DevTools 实例的元素工具，将鼠标悬停在某个元素上以在 Android 设备的视口中突出显示它。  

还可以在 Android 设备屏幕上选择一个元素，以在"元素"工具 **中选择** 它。  在**** ![ DevTools (选择元素 \) 图标，然后选择 ][ImageSelectElementIcon] Android 设备屏幕上的元素。  

> [!NOTE]
> **Select 元素** 在首次选择后被禁用，因此每次想要使用该功能时都必须重新启用它。  

### <a name="screencast-your-android-screen-to-your-development-machine"></a>将 Android 屏幕屏蔽到开发计算机  

Choose **Toggle Screencast** \ (![ Toggle Screencast \) icon to view the content of your Android device in your ][ImageToggleScreencastIcon] DevTools instance.  

你能够通过以下方式与屏幕视频进行交互。  

*   选择将转换为点击，在设备上触发正确的触摸事件。  
*   将计算机上键击发送到设备。  
*   若要模拟收缩手势，请按住 `Shift` 拖动。  
*   若要滚动，请使用跟踪板或鼠标滚轮，或与鼠标指针一起跳。

> [!NOTE]
> 使用以下提示帮助你进行屏幕广播。  
> 
> *   屏幕视频仅显示页面内容。  屏幕视频的透明部分表示设备接口，如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。  
> *   屏幕视频会对帧速率产生负面影响。  在测量滚动或动画时禁用屏幕视频，以获得页面性能的更准确图片。  
> *   如果你的 Android 设备屏幕锁定，屏幕视频的内容将消失。  解锁 Android 设备屏幕以自动恢复屏幕视频。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "配置设备上的开发人员选项|Android 开发人员"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序|Android 开发人员"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 开发工具|Apple 开发人员"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "在移动设备上调试|Brightcove 支持"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb - Android Enthusiast Stack Exchange"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "DevTools 设备在插入时不检测设备 - Stack Overflow"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
