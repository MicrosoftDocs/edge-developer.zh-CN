---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 132ccab0f9f378eedd8c83a7404c350161556f2e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182393"
---
# 了解 WebView2 SDK 版本

WebView2 SDK 的新版本以与 Microsoft Edge (Chromium ) 浏览器相同的常规节奏提供，每六周大约每六周。  

## 发布和预发布程序包  

WebView2 NuGet 程序包包含发布和预发布程序包。  

发布程序包向前兼容，包含 [Win32 C/c + + api][ReferenceWin32]。  此 SDK 中的 Api 完全受支持。  

预发布程序包是发布程序包的一个超集，下面列出了其他组件。  

*   .NET Api： [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]和 [Core][DotnetMicrosoftWebWebview2CoreNamespace]  
*   实验性 Api：有关详细信息，请导航到 [实验性 api](#experimental-apis) 部分。  

### 路线图  

发布包包含所有稳定的、受支持的 Win32 C/c + + Api。  将来，发布版程序包将包含所有稳定的、受支持的 .NET Api （当它们正式可用时）。  预发布程序包包含可能会根据你的反馈进行更改的实验性 Api。 

## 实验性 API  

Web 视图团队正在查找未来版本中可能包含的实验性 Api 的反馈。  实验中的 Api 标记为 `experimental` 在 SDK 中。  你可以使用 [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。  

> [!CAUTION]
> 可从 SDK 向 SDK 引入、修改和删除实验性 Api。  避免在生产应用中使用实验性 Api。  

> [!NOTE]
> 在已安装版本的 WebView2 运行时中，实验性 Api 可能不可用。  

## 匹配 WebView2 运行时版本  
WebView2 应用程序要求用户安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2]。 WebView2 运行时将自动更新到最新的可用版本。 在某些情况下，用户可能需要停止自动 WebView2 运行时更新，这可能会导致应用程序兼容性问题。

如果 WebView2 运行时更新已停止，请确保你了解你的应用程序所需的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 的最低版本。 请考虑以下两个项目：  

1. SDK 的最低要求版本可在 WebView2 [发行说明][Releasenotes] 中的 **最低 WebView2 运行时版本**下找到。 例如，对于 SDK 版本[1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222)，你必须安装[WebView2 运行时][MicrosoftDeveloperEdgeWebview2]或具有**86.0.616.0**或更高版本号的[非稳定 Microsoft Edge 通道][MicrosoftedgeinsiderDownload]。 只有当 web 平台中存在重大更改时，SDK 所需的最低版本才会更改。

2. 支持应用中使用的接口和 Api 所需的 NuGet 程序包所需的最低版本。 新的接口和 Api 会定期添加到 WebView2。 在 SDK 中捆绑的 Api 和接口将需要不同版本的 WebView2 运行时，因为它们在不同的时间添加到了 SDK。  所需的 WebView2 运行时版本与第一次引入 API 的 SDK 版本的内部版本号（第三个数字）相匹配。 例如，SDK 版本 [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222) 中添加的新 API 或接口将需要 WebView2 运行时版本：86.0。**622**。 在后续 SDK 版本中添加的 API 或接口需要具有与 SDK 相同版本号的 WebView2 运行时。 你可以确定 WebView2 运行时版本是否支持 [以编程方式](#determine-webview2-runtime-requirement)支持接口或 API。

> [!IMPORTANT]
> 开发长时间 [WebView2 应用程序](distribution.md#evergreen-distribution-mode)时，请定期针对最新版本的 WebView2 运行时和非稳定的 Microsoft Edge 浏览器测试应用程序。  由于 web 平台不断发展，因此定期测试是确保应用程序按预期执行的最佳方式。  

### 确定 WebView2 运行时要求

请考虑以下项目，具体取决于您使用的是哪个 SDK： 

*   **Win32 C/c + +**。  使用 `QueryInterface` 获取新接口时，请检查返回值 `E_NOINTERFACE` 。  此值可能指示 WebView2 运行时是以前的版本，并且不支持该接口。 导航到 WebView2API 示例以查看其工作原理的 [示例](https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622) 。
*   **.Net 和 WinUI**。  `No such interface supported`在使用已添加到最新 sdk 的方法、属性和事件时，检查异常。  如果 WebView2 运行时是早期版本，并且不支持这些 Api，则可能会发生此异常。  

如果 API 不可用，请考虑删除关联的功能，或通知用户他们需要更新其 WebView2 运行时的版本。  



 

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->  

[Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 命名空间 | WebView2 命名空间 |Microsoft 文档"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 c + + 参考 |Microsoft 文档"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 开发人员"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  
