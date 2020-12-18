---
description: 远程调试 Surface Duo 仿真器入门。
title: 远程调试 Surface Duo 仿真器入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 远程调试， android， surface duo
ms.openlocfilehash: f44c85c468de3bdd7727695e3f33269584966231
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230629"
---
# 远程调试 Surface Duo 仿真器入门  

本文将介绍从 Microsoft Edge 桌面实例在[Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo]仿真器上的[Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx]应用中远程调试 Web[内容的过程][MicrosoftEdge]。  有关在 Surface Duo 设备上调试的信息，请按照我们的远程 [调试 Android 设备的指南操作][DevtoolsRemoteDebuggingMain]。  

## 开始之前

在运行[Surface Duo 仿真][MicrosoftDownload100847]器之前安装 Surface [Duo SDK。][DualScreenAndroidUseEmulator]  有关详细信息，请参阅获取[Surface Duo SDK。][DualScreenAndroidGetDuoSdk]  

## 步骤 1：导航到edge://inspect  

打开 Microsoft Edge 的 [桌面实例][MicrosoftEdge]，然后导航到 `edge://inspect` 。  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="桌面edge://inspect Microsoft Edge 中的"页面"" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   `edge://inspect`桌面版 Microsoft Edge 中的页面  
:::image-end:::

> [!NOTE]
> 如果 `edge://inspect` 页面无法识别 Surface [Duo 仿真器][DualScreenAndroidUseEmulator]，请重新启动仿真器。  

## 步骤 2：启动 Surface Duo 仿真器  

启动 [Surface Duo 模拟器][DualScreenAndroidUseEmulator]。  请注意，仿真器显示 2 个在仿真器上运行的不同屏幕。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Duo 仿真器" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   Surface Duo 仿真器  
:::image-end:::  

## 步骤 3：在 Surface Duo 仿真器上的 Microsoft Edge 中加载 Web 内容  

在任一屏幕上，在 [Surface Duo][DualScreenAndroidUseEmulator] 模拟器的收藏夹托盘上向上轻扫以显示"应用箱"。  选择 **"边缘** "以 [启动 Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Duo 模拟器上的 Microsoft Edge 应用" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   Surface Duo 模拟器上的 Microsoft Edge 应用  
:::image-end:::  

导航到你想要在 Microsoft Edge 应用中调试 [的网站或应用][GooglePlayStoreAppsComMicrosoftEmmx]。  

## 步骤 4：从 Surface Duo 仿真器调试 Web 内容  

切换回 Microsoft Edge 的 [桌面实例][MicrosoftEdge]。  该 `edge://inspect` 页面现在显示**SurfaceD一个或多个**在[Surface Duo][DualScreenAndroidUseEmulator]仿真器上运行的打开的选项卡或[PWA][ProgressiveWebAppsIndex]的列表。  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text="the edge://inspect page displays a list of the open tabs in the Microsoft Edge app running on the emulator" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   该 `edge://inspect` 页面在模拟器上运行的 Microsoft Edge 应用中显示打开的选项卡列表  
:::image-end:::  

> [!NOTE]
> 如果你未在页面上**看到 SurfaceDuoEmulator，** 请尝试在 Surface Duo 模拟器上的 Microsoft Edge 应用中打开 `edge://inspect` [或关闭选项卡][DualScreenAndroidUseEmulator]。 [][GooglePlayStoreAppsComMicrosoftEmmx]  有关其他疑难解答步骤，请参阅 Android 设备的疑难 [解答部分][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。  

从模拟器上运行的打开的选项卡列表中，在包含要**** 调试的 Web 内容的选项卡上选择"检查"。  Microsoft [Edge DevTools][DevtoolsIndex] 将在新窗口中打开。  Choose **Toggle Screencast** \ (![ Toggle Screencast ][ImageToggleScreencastIcon] \) to view the web content from your [Surface Duo emulator][DualScreenAndroidUseEmulator] in the DevTools window.  你现在可以使用 Microsoft Edge DevTools 调试 Surface Duo 模拟器 [上的 Web 内容][DualScreenAndroidUseEmulator]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="使用 Microsoft Edge DevTools 在 Surface Duo 仿真器上的 Microsoft Edge 应用中调试必应" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   使用 Microsoft Edge DevTools 在 Surface Duo 仿真器上的 Microsoft Edge 应用中调试必应  
:::image-end:::  

> [!NOTE]
> 如果在仿真器中的 [两][GooglePlayStoreAppsComMicrosoftEmmx] 个屏幕中跨 Microsoft Edge 应用，屏幕广播将反映应用的新大小，但无法反映屏幕大小。  若要了解云层如何影响 Web 内容的布局，请使用 [Surface Duo][DualScreenAndroidUseEmulator] 仿真器，而不是屏幕广播。  

## 其他资源  

对于新的可折叠和双屏幕设备类，Web 是一个很好的平台，因为您可以编写 HTML、CSS 和 JavaScript 一次，并且可以在单屏、双屏幕和可折叠设备上显示出色的外观。  有关详细信息，请参阅这些其他资源，开始为这些新设备生成 Web 内容。  

*   [有关在双屏设备上创建应用的文档][DualScreenIndex]  
*   [在可折叠和双屏幕设备上构建 Web 体验的新 API 的 Microsoft Edge Web 平台解释器][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [录制 Microsoft 365 开发人员日会话：如何为网站和 Web 应用构建双屏体验][YoutubeDxrzwsqxpvc]  

<!-- image links -->  

[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows 上的渐进式 Web 应用 |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "远程调试 Android 设备入门 |Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "疑难解答：DevTools 无法检测 Android 设备 - 远程调试 Android 设备入门 |Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "为双屏设备创建应用 |Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface D一仿真器 |Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo SDK |Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "引入新的 Microsoft Edge"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo |Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "下载 Surface Duo SDK 预览版 |Microsoft 下载中心"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge：Web 浏览器 |GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "可折叠设备上启发式体验的 Web 平台基元 - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "如何为网站和 Web 应用构建双屏幕体验 |YouTube"  
