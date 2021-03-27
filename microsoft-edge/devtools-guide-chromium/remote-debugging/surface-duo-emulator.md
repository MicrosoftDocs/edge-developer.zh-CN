---
description: 远程调试 Surface Duo 仿真程序入门。
title: 远程调试 Surface Duo 仿真程序入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发工具, 远程调试, android, surface duo
ms.openlocfilehash: 61f903a5b929b7ee7b924938cf6ddc21a9783ca7
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439324"
---
# <a name="get-started-with-remote-debugging-surface-duo-emulators"></a>远程调试 Surface Duo 仿真程序入门  

本文将介绍从 [Microsoft Edge][MicrosoftEdge] 的桌面版实例远程调试 [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo] 仿真程序上 [Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]的 web 内容。  有关在 Surface Duo 设备上进行调试的信息，请遵循[远程调试 Android 设备][DevtoolsRemoteDebuggingMain]的指南。  

## <a name="before-you-begin"></a>开始之前

运行[Surface Duo 仿真程序][DualScreenAndroidUseEmulator]前，先安装 [Surface Duo SDK][MicrosoftDownload100847]。  有关详细信息，请导航到[获取 Surface Duo SDK][DualScreenAndroidGetDuoSdk]。  

## <a name="step-1-navigate-to-edgeinspect"></a>步骤 1：导航到 edge://inspect  

打开 [Microsoft Edge][MicrosoftEdge] 的桌面实例，然后导航到 `edge://inspect`。  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="桌面上 Microsoft Edge 中的 edge://inspect 页面" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   桌面上的 Microsoft Edge `edge://inspect` 页面  
:::image-end:::

> [!NOTE]
> 如果 `edge://inspect` 页面无法识别 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]，请重新启动仿真程序。  

## <a name="step-2-launch-the-surface-duo-emulator"></a>步骤 2：启动 Surface Duo 仿真程序  

启动 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]。  请注意，仿真程序显示 2 个在仿真程序上运行的不同屏幕。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Duo 仿真程序" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   Surface Duo 仿真程序  
:::image-end:::  

## <a name="step-3-load-your-web-content-in-microsoft-edge-on-the-surface-duo-emulator"></a>步骤 3：在 Surface Duo 仿真程序上将 web 内容载入 Microsoft Edge   

在任一屏幕上，将 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]的“收藏夹托盘”上向上轻扫，以显示“应用抽屉”。  选择 **Edge** 以启动 [Microsoft Edge 应用程序][GooglePlayStoreAppsComMicrosoftEmmx]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Duo 仿真程序上的 Microsoft Edge 应用" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   Surface Duo 仿真程序上的 Microsoft Edge 应用  
:::image-end:::  

导航到想要在 [Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]中调试的网站或 应用。  

## <a name="step-4-debug-your-web-content-from-the-surface-duo-emulator"></a>步骤 4：从 Surface Duo 仿真程序调试 Web 内容  

切换回 [Microsoft Edge][MicrosoftEdge] 的桌面实例。  现在，`edge://inspect` 页面显示 **SurfaceDuoEmulator**以及在 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]上运行的打开的选项卡或 [PWAs][ProgressiveWebAppsIndex]列表。  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text="edge://inspect 页面在模拟器上运行的 Microsoft Edge 应用程序中显示打开选项卡的列表" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   `edge://inspect` 页面在模拟器上运行的 Microsoft Edge 应用程序中显示打开选项卡的列表  
:::image-end:::  

> [!NOTE]
> 如果在 `edge://inspect` 页上未显示 **SurfaceDuoEmulator**，请尝试在 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]上的 [Microsoft Edge应用程序][GooglePlayStoreAppsComMicrosoftEmmx]中打开或关闭选项卡。  有关其他疑难解答步骤，请导航到 [Android 设备的疑难解答部分][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。  

从模拟器上运行的打开的选项卡列表中，在具有要调试的 Web 内容的选项卡上选择“**检查**”。  [Microsoft Edge 开发工具][DevtoolsIndex]将在新窗口中打开。  选择“**切换截屏视频**” \(![切换截屏视频t](../media/toggle-screencast-icon.msft.png)\)，从开发工具窗口中的 [ Surface Duo 仿真程序][DualScreenAndroidUseEmulator]查看 Web 内容。  现在可以使用 Microsoft Edge 开发工具在 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator]上调试 Web 内容。  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="使用 Microsoft Edge 开发工具在 Surface Duo 仿真程序的 Microsoft Edge 应用程序中调试 Bing" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   使用 Microsoft Edge 开发工具在 Surface Duo 仿真程序的 Microsoft Edge 应用程序中调试 Bing  
:::image-end:::  

> [!NOTE]
> 如果 [Microsoft Edge 应用][GooglePlayStoreAppsComMicrosoftEmmx]在仿真程序中跨两个屏幕，截屏视频将反映应用程序的新尺寸，而不是铰链。  若要了解网站如何影响 Web 内容的布局，请使用 [Surface Duo 仿真程序][DualScreenAndroidUseEmulator] ，而不是截屏视频。  

## <a name="additional-resources"></a>其他资源  

对于新的可折叠和双屏幕设备类，Web 是一个很好的平台，因为可以编写 HTML、CSS 和 JavaScript 一次，并且可以在单屏、双屏和可折叠设备上显示出色的外观。  有关更多信息，请导航至以下其他资源，以开始为这些新设备构建 Web 内容。  

*   [有关在双屏设备上创建应用的文档][DualScreenIndex]  
*   [Microsoft Edge Web 平台介绍在可折叠和双屏设备上构建 Web 体验的新 API][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [Microsoft 365 开发人员日会话录制：如何为网站和 Web 应用构建双屏体验][YoutubeDxrzwsqxpvc]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发工具 | Microsoft 文档"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows 应用上的渐进式 Web |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "Android 设备远程调试入门 | Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "疑难解答：开发工具未检测 Android 设备 - Android 设备远程调试入门 | Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "为双屏设备创建应用 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 仿真程序 | Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo SDK | Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "推出新的 Microsoft Edge"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新 Surface Duo | Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "下载 Surface Duo SDK 预览版 | Microsoft 下载中心"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge: Web Browser | GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "可折叠设备启发式体验的 Web 平台基元 - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "如何为网站和 Web 应用构建双屏体验 | YouTube"  
