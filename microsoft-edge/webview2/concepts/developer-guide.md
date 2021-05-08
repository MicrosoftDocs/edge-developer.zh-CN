---
description: 了解在开发 WebView2 应用程序时要使用的开发最佳做法。
title: WebView2 开发的最佳做法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、edge、最佳做法
ms.openlocfilehash: 3982f47e0fe58287582915673d4ba0de0365a55d
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535655"
---
# <a name="webview2-development-best-practices"></a>WebView2 开发的最佳做法  

每个开发团队在构建其应用程序时都遵循不同的做法。 生成 WebView2 应用程序时，建议遵循一些做法。 本文概述了在构建基于生产环境的 WebView2 应用程序时的建议和最佳做法。


## <a name="use-evergreen-webview2-runtime-recommended"></a>使用 Evergreen WebView2 运行时 (推荐)   

虽然固定版本具有严格的兼容性要求的应用用例，但我们通常建议使用 Evergreen WebView2 运行时。  Evergreen WebView2 运行时会自动更新，并包括可用于 WebView2 应用程序的最新功能和安全修补程序。 Evergreen WebView2 运行时还需要减少磁盘上的存储空间。

使用 WebView2 应用程序之前，请确保已安装 Evergreen WebView2 运行时。  有关详细信息，请导航到 [部署 Evergreen WebView2 运行时][Webview2ConceptsDistributionDeployingEvergreenWebview2Runtime]。  

## <a name="run-compatibility-tests-regularly-when-using-the-evergreen-webview2-runtime"></a>使用 Evergreen WebView2 运行时时定期运行兼容性测试

使用 Evergreen WebView2 运行时时，请确保运行常规兼容性测试。 由于运行时自动更新，因此请针对非稳定版本的 Microsoft Edge 测试 WebView2 控件中的 Web 内容，以确保 WebView2 应用程序按预期运行。 本指南类似于我们向 Web 开发人员提供的指导。 有关详细信息，请导航到"[在常青模式下保持兼容"。][Webview2ConceptsDistributionStayCompatibleEvergreenMode]

## <a name="ensure-apis-are-supported-by-the-installed-webview2-runtime"></a>确保安装的 WebView2 运行时支持 API

WebView2 应用程序需要同时在计算机上安装 Webview2 SDK 和 WebView2 运行时来运行。 SDK 和运行时都进行版本控制。 由于 API 不断添加到 WebView2，因此也发布了新版本的运行时以支持新的 API。 需要确保安装在该计算机的 WebView2 运行时支持 WebView2 应用程序使用的 API。 

如果使用 Evergreen WebView2 运行时，则在某些情况下可能不会将运行时更新为使用最新版本。 例如，当用户无法访问 Internet 时，该环境中不会自动更新运行时。 此外，使用某些组策略将暂停 WebView2 更新。 当你将更新推送到 WebView2 应用程序时，应用程序可能会中断，因为它使用的较新的 API 在安装的运行时中不可用。   
 
若要解决此问题，可以在代码调用 API 之前测试 API 在已安装的运行时中的可用性。 此较新功能测试与其他 Web 开发最佳实践类似，这些最佳实践在使用新的 Web API 之前检测支持的功能。 若要测试已安装运行时中的 API 可用性，请使用：
* `queryinterface`C/C++ 中的 。 
* .NET 或 WinUI 中的 try/catch 块。 
    
有关详细信息，请导航到确定 [WebView2 运行时要求][Webview2ConceptsVersioningDetermineWebview2RuntimeRequirement]。  

## <a name="update-the-fixed-version-runtime"></a>更新固定版本运行时  

如果使用固定版本运行时，请确保定期更新运行时，以减少任何潜在的安全风险。 在 Webview2 应用程序中使用第三方内容时，始终认为内容不受信任。  有关详细信息，请导航到"[固定版本分发模式"。][Webview2ConceptsDistributionFixedVersionDistributionMode]  

## <a name="manage-new-versions-of-the-runtime"></a>管理新版本的运行时  

只要将新版本的 Evergreen WebView2 运行时下载到设备，运行 WebView2 应用程序就会继续使用以前的运行时，直到浏览器进程发布。 此行为允许应用程序连续运行，并阻止删除以前的运行时。 若要使用新版本的运行时，你需要释放对以前的 WebView2 环境对象的所有引用或重新启动应用程序。 下次创建新的 WebView2 环境时，它将使用新版本。

若要在新版本可用时采取措施，例如通知用户重新启动应用程序，可以在代码中使用 [add_NewBrowserVersionAvailable (Win32) ][Webview2ReferenceaddNewBrowserVersionAvailable] 或 [CoreWebView2Environment.NewBrowserVersionAvailable (.NET) ][Webview2ReferenceNewBrowserVersionAvailable] 事件。 如果代码处理重新启动应用程序，请考虑在 WebView2 应用程序退出之前保存用户状态。  

## <a name="manage-the-lifetime-of-the-user-data-folder"></a>管理用户数据文件夹的生命周期 
WebView2 应用创建用户数据文件夹来存储 Cookie、凭据、权限等数据。 创建文件夹后，你的应用负责管理用户数据文件夹的生命周期，包括在卸载应用时清理。  有关详细信息，请导航到"[管理用户数据文件夹"。][Webview2ConceptsUserDataFolder]  

## <a name="follow-recommended-webview2-security-best-practices"></a>遵循建议的 WebView2 安全性最佳做法 
对于任何 WebView2 应用程序，请确保遵循我们建议的 WebView2 安全性最佳做法。  有关详细信息，请导航到 [Best practices for developing secure WebView2 applications][Webview2ConceptsSecurity]。  


<!-- links -->  

[Webview2ConceptsDistributionDeployingEvergreenWebview2Runtime]: ../concepts/distribution.md#deploying-the-evergreen-webview2-runtime "部署 Evergreen WebView2 运行时 - 使用 WebView2 |Microsoft Docs"  
[Webview2ConceptsDistributionFixedVersionDistributionMode]: ../concepts/distribution.md#fixed-version-distribution-mode "固定版本分发模式 - 使用 WebView2 分发|Microsoft Docs"  
[Webview2ConceptsDistributionStayCompatibleEvergreenMode]: ../concepts/distribution.md#stay-compatible-in-evergreen-mode "在常青模式中保持兼容 - 使用 WebView2 模式分配|Microsoft Docs"  
[Webview2ConceptsSecurity]: ../concepts/security.md "开发安全 WebView2 应用程序应用程序的最佳实践|Microsoft Docs"  
[Webview2ConceptsUserDataFolder]: ../concepts/user-data-folder.md "管理用户数据文件夹|Microsoft Docs"  
[Webview2ConceptsVersioningDetermineWebview2RuntimeRequirement]: ../concepts/versioning.md#determine-webview2-runtime-requirement "确定 WebView2 运行时要求 - 了解 WebView2 SDK |Microsoft Docs"  
[Webview2GetStartedWin32]: ../get-started/win32.md "WebView2 |Microsoft Docs"  
[Webview2GetStartedWinforms]: ../get-started/winforms.md "Windows Forms | 中的 WebView2 入门Microsoft Docs"  
[Webview2GetStartedWinui]: ../get-started/winui.md "WinUI 3 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2GetStartedWpf]: ../get-started/wpf.md "WPF | 中的 WebView2 入门Microsoft Docs"  
[Webview2ReferenceaddNewBrowserVersionAvailable]: https://docs.microsoft.com/microsoft-edge/webview2/reference/win32/icorewebview2environment#add_newbrowserversionavailable "add_NewBrowserVersionAvailable |Microsoft Docs"  
[Webview2ReferenceNewBrowserVersionAvailable]: https://docs.microsoft.com/dotnet/api/microsoft.web.webview2.core.corewebview2environment.newbrowserversionavailable "CoreWebView2Environment.NewBrowserVersionAvailable 事件|Microsoft Docs"  