---
description: 使用 Microsoft Edge 中的虚拟设备增强用于双屏幕和可折叠设备的网站。
title: 模拟 Microsoft Edge DevTools 中的双屏幕和可折叠设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web development， f12 tools， devtools， emulation， device， simulation， mobile， dual-screen， foldable， Surface Duo， SamsungSamsungy Fold
ms.openlocfilehash: bc91c0b7c917d82f169dc7d47e047a587d505353
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313153"
---
# 模拟 Microsoft Edge DevTools 中的双屏幕和可折叠设备  

在 Microsoft Edge 版本 89 或更高版本中，你可以模拟以下双屏幕和可折叠设备。  

*   [Surface Duo][SurfaceDevicesDuo]  
*   [三星百合][SamsungMobileGalaxyFold]  
    
模拟设备，并切换以下状态。  

*   单屏或折叠状态  
*   双屏或展开状态  
    
打开实验性 Web 平台[API，](#turn-on-experimental-apis)并使用[CSS 媒体][DualScreenDocsCssMedia]屏幕跨越功能以及[JavaScript getWindowSegments API][DualScreenDocsJSAPI]增强双屏幕和可折叠设备的网站 \ (或 app\) 。  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="模拟 Microsoft Edge 中的 Surface Duo" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   模拟 Microsoft Edge 中的 Surface Duo  
:::image-end:::  

## 打开实验性 API  

若要使用 [CSS 媒体屏幕跨越][DualScreenDocsCssMedia] 功能以及 [JavaScript getWindowSegments API，][DualScreenDocsJSAPI]请打开 `Experimental Web Platform features` Microsoft Edge 中的标志。  完成以下步骤。  

1.  导航到 `edge://flags` 。  
1.  在**搜索标志**文本框中，输入、选择实验 Web 平台功能标志，并更改为 `Experimental Web Platform features` **"已禁用"。** **** ****  
1.  重启 Microsoft Edge。  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="打开实验性 Web 平台功能标志" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   打开实验 **性 Web 平台功能** 标志  
:::image-end:::  

> [!NOTE]
> 如果你使用[CSS][DualScreenDocsCssMedia]媒体查询或[JavaScript Windows 段枚举 API][DualScreenDocsJSAPI]增强[Surface Duo][SurfaceDevicesDuo]的网站或应用，则还必须在[Surface Duo][SurfaceDevicesDuo]设备上的[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用中打开实验**性 Web**平台功能标志。  
> 
> 如果在桌面[Microsoft Edge][MicrosoftEdge]中打开实验性**Web**平台功能标志，并且在[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用中关闭，则桌面版 Microsoft Edge 的 Surface Duo 模拟器中的网站或应用的行为与[Surface Duo][SurfaceDevicesDuo]上的[Android Microsoft Edge][GooglePlayMicrosoftEdge]应用不匹配。  确保标志在 Android 和桌面版 Microsoft Edge 之间匹配，以在桌面 [版 Microsoft Edge][MicrosoftEdge]中成功使用 Surface Duo 仿真器。  

## 在可折叠和双屏幕设备上测试  

当你在 Microsoft Edge 中模拟双屏幕状态中的 [Surface Duo][SurfaceDevicesDuo] 时，两个屏幕之间的 (\) 将绘制在网站或应用上。  

模拟的显示与你的网站 \ (或 app\) 在 Surface Duo 上运行时在 [Microsoft Edge Android][GooglePlayMicrosoftEdge] 应用中 [呈现的方式相匹配][SurfaceDevicesDuo]。  你可能需要更新网站 \ (app\) ，以更好地显示网站。  若要详细了解如何调整您的网站 \ (或 app\) 以适应变化，请导航到"如何使用[此目录"。][DualScreenIntroductionHowWorkSeam]  

设备 [工具栏][DevtoolsDeviceModeIndexSimulateMobileViewport] 具有其他功能，可帮助你以多种状态和方向测试网站或应用。  Choose **Rotate** \ (![ Rotate ](../media/rotate-dark-icon.msft.png) \) to rotate the viewport to landscape orientation. 将此功能与 **Span** \ (Span \) 相结合，以在单屏或折叠、双屏或展开状态 ![ ](../media/span-dark-icon.msft.png) 之间进行切换。  这些功能共同允许你以所有四种可能状态和方向测试网站或应用。  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="双屏和可折叠设备的状态和方向矩阵" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   双屏和可折叠设备的状态和方向矩阵  
:::image-end:::  

实验 **性 Web 平台功能** \ (![ ExperimentalApis ](../media/experimental-apis-dark-icon.msft.png) \) 图标显示实验性 **Web 平台功能标志** 的状态。  如果标志已打开，则突出显示图标。  如果关闭标志，则不突出显示图标。  若要打开 \ (或关闭\) ，请选择图标或导航到并 `edge://flags` 切换标志。  

> [!NOTE]
> 以下是当前已知问题的列表。  
> 
> *   当你使用 [Microsoft 远程桌面客户端][RemoteDesktopClientDocs] 连接到远程电脑并模拟 [Surface Duo 或][SurfaceDevicesDuo] [Samsung 一][SamsungMobileGalaxyFold]起折叠时，指针可能会抖动或抖动。  如果遇到问题，请 [发送反馈](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

## 其他资源  

下面是可帮助您增强双屏幕设备的网站 \ (或 app\) 的其他资源。  

*   有关在双屏设备上进行 Web 开发的信息，请导航到 [双屏幕 Web 体验][DualScreenWebIndex]。  
*   安装 [Surface Duo 仿真器][DualScreenAndroidUseEmulator]。  Surface Duo 仿真器不同于 Microsoft Edge 中的仿真器，运行 Android，并且与 [Android Studio 集成][AndroidDeveloperStudio]。  有关详细信息，请导航到["获取 Surface Duo SDK"。][DualScreenAndroidGetDuoSdk]  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools |Microsoft Edge"  

[DualScreenWebIndex]: /dual-screen/web/index "双屏幕 Web 体验|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "获取 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏幕设备简介|Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "使用 Surface Duo 仿真器|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "用于双屏检测方法的 CSS 媒体屏幕|Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "远程桌面客户端|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "百年百|Samsung"  
