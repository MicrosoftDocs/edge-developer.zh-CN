---
title: 远程调试 Surface 双核模拟器入门
author: zoherghadyali
ms.author: zoghadya
ms.date: 04/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、远程调试、android、surface 双核
ms.openlocfilehash: af6fa6433b0bc6bba0599e6e9a805235504caadd
ms.sourcegitcommit: 966bfc60040acc794b6ee20eb2084bc8264a4852
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "10621500"
---
# 远程调试 Surface 双核模拟器入门

在本文中，你将引导你完成从[Microsoft edge][DesktopEdge]的桌面实例远程调试[Surface 双核][SurfaceDuo]模拟器上的[Microsoft edge 应用][AndroidEdge]中的 web 内容的过程。 有关在 Surface 双核设备上进行调试的信息，请参阅我们的 [远程调试 Android 设备][RemoteDebuggingAndroid]指南。

## 开始之前

在运行[Surface 双核处理器技术][DuoEmulator]之前安装[surface 双核 SDK][DuoSdk] 。 有关详细信息，请参阅 [获取 Surface 双核 SDK][DuoSdkdocs]。

## 步骤1：导航到 edge://inspect

打开 [Microsoft Edge][DesktopEdge]的桌面实例，然后导航到 `edge://inspect` 。

> ##### 图 1  
> `edge://inspect`桌面上的 Microsoft edge 中的页面 ![ 桌面上的 microsoft edge 中的 edge://inspect 页面][ImageEdgeInspect]

> [!NOTE]
> 如果 `edge://inspect` 页面不识别 [Surface 双核模拟器][DuoEmulator]，请重新启动仿真器。

## 步骤2：启动 Surface 双核仿真器

启动 [Surface 双核模拟器][DuoEmulator]。 请注意，仿真器将显示在仿真器上运行的2个不同的屏幕。

> ##### 图 2
> Surface 双核处理器技术（Surface）仿真器 ![][ImageDuoEmulator]  

## 步骤3：在 Surface 双核模拟器上的 Microsoft Edge 中加载 web 内容

在任一屏幕上，向上轻扫 [Surface 双核处理器技术][DuoEmulator] 的 "收藏夹" 托盘以显示 "应用" 抽屉。 选择 " **边缘** " 以启动 [Microsoft Edge 应用][AndroidEdge]。

> ##### 图 3
> Surface 双核模拟器上的 Microsoft Edge 应用在 ![ Surface 双核处理器技术上的 Microsoft edge 应用][ImageDuoEmulatorEdge]  

导航到要在 [Microsoft Edge 应用][AndroidEdge]中调试的网站或应用。

## 步骤4：从 Surface 双核仿真器调试 web 内容 

切换回 [Microsoft Edge][DesktopEdge]的桌面实例。 `edge://inspect`页面现在显示**SurfaceDuoEmulator** ，其中列出了在[Surface 双核仿真器][DuoEmulator]上运行的打开的选项卡或[PWAs][PwaDocs] 。

> ##### 图 4
> `edge://inspect`页面显示在仿真器上运行的 Microsoft edge 应用中打开的选项卡列表 ![ edge://inspect 页面显示在仿真器上运行的 microsoft edge 应用中打开的选项卡的列表][ImageEdgeInspectTargets]  

> [!NOTE]
> 如果在页面上看**SurfaceDuoEmulator**不到 SurfaceDuoEmulator `edge://inspect` ，请尝试在[Surface 双核模拟器][DuoEmulator]上的[Microsoft Edge 应用][AndroidEdge]中打开或关闭选项卡。 有关其他疑难解答步骤，请参阅 [Android 设备][TroubleshootingAndroid]的 "疑难解答" 部分。

从运行在模拟器上的打开的选项卡列表中，选择包含要调试的 web 内容的选项卡上的 " **检查** "。 [Microsoft Edge DevTools][DevToolsDocs]将在新窗口中打开。 选择 " **切换说明截屏视频** ![ 切换" 说明截屏视频 ][ImageToggleScreencastIcon] 可在 DevTools 窗口中查看 [Surface 双核模拟器][DuoEmulator] 的 web 内容。 现在，你可以使用 Microsoft Edge DevTools 来调试 [Surface 双核模拟器][DuoEmulator]上的 web 内容。

> ##### 图 5
> 使用 Microsoft edge DevTools 在 Surface 双核模拟器上的 Microsoft Edge 应用中 ![ 使用 Microsoft Edge DevTools 调试必应在 Surface 双核模拟器上的 Microsoft edge 应用中调试必应][ImageDevTools]  

> [!NOTE]
> 如果你在仿真器的两个屏幕上跨越 [Microsoft Edge 应用][AndroidEdge] ，说明截屏视频将反映应用的新大小，而不是转轴。 若要了解转轴对 web 内容布局的影响，请使用 [Surface 双核仿真器][DuoEmulator] ，而不是说明截屏视频。

## 其他资源

Web 是新的可折叠和双屏幕设备的平台，因为你可以一次性编写 HTML、CSS 和 JavaScript，使其在单屏幕、双屏幕和可折叠的设备上更加美观。 有关详细信息，请参阅这些其他资源，开始为这些新设备构建 web 内容。

- [有关在双屏幕设备上创建应用的文档][DualScreenDocs]
- [Microsoft Edge web 平台 explainer 用于在可折叠和双屏幕设备上构建 web 体验的新 Api][WebPlatformExplainer]
- [Microsoft 365 开发人员日会议录制：如何为网站和 web 应用构建双屏幕体验][DeveloperDay]

<!-- image links -->  
[ImageEdgeInspect]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page.msft.png "图1：桌面上的 Microsoft Edge 中的 edge://inspect 页面"
[ImageDuoEmulator]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator.msft.png "图2： Surface 双核仿真器"
[ImageDuoEmulatorEdge]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator-edge.msft.png "图3： Surface 双核模拟器上的 Microsoft Edge 应用"
[ImageEdgeInspectTargets]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png "图4： edge://inspect 页面显示在仿真器上运行的 Microsoft Edge 应用中打开的选项卡的列表"
[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png
[ImageDevTools]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-devtools.msft.png "图5：使用 Microsoft Edge DevTools 在 Surface 双核模拟器上的 Microsoft Edge 应用中调试 Bing"

<!-- links -->  
[RemoteDebuggingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "远程调试 Android 设备入门"
[PwaDocs]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用"
[DevToolsDocs]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"
[TroubleshootingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index#troubleshooting-devtools-is-not-detecting-the-android-device "疑难解答： DevTools 未检测到 Android 设备"

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android 应用"
[SurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "介绍 Surface 双核"
[DesktopEdge]: https://www.microsoft.com/edge/ "新的 Microsoft Edge 简介"
[DuoEmulator]: https://docs.microsoft.com/dual-screen/android/use-emulator "使用 Surface 双核仿真器"
[DuoSdk]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface 双核处理器技术 SDK 预览版本"
[DuoSdkDocs]: https://docs.microsoft.com/dual-screen/android/get-duo-sdk "获取 Surface 双核 SDK"
[DualScreenDocs]: https://docs.microsoft.com/dual-screen/ "为双屏幕设备创建应用"
[WebPlatformExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "针对折叠设备上的启发式体验的 Web 平台基元"
[DeveloperDay]: https://youtu.be/DXrZWsqXPVc "如何为网站和 web 应用构建双屏幕体验"
