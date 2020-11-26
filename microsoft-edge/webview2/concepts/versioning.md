---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 54d62de00a89a3c433fd77e9ec20945adbfc19c3
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "11191608"
---
# 了解 WebView2 SDK 版本  

WebView2 SDK 的新版本以与 Microsoft Edge (Chromium ) 浏览器相同的常规节奏提供，每六周大约每六周。  

## 发布和预发布程序包  

WebView2 NuGet 程序包包含发布和预发布程序包。  

**发布程序包**向前兼容，包含以下组件。  

*   [Win32 C/c + + Api][ReferenceWin32]
*   .NET Api：  [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]和 [Core][DotnetMicrosoftWebWebview2CoreNamespace]。  
    
SDK 中的 Api 完全受支持。  

**预发布程序包**是发布程序包的一个包含实验性[api](#experimental-apis)的超集。  

### 路线图  

发布包包含所有稳定、受支持的 Win32 C/c + + 和 .NET Api。  预发布程序包包含可能会根据你的反馈进行更改的实验性 Api。  

## 实验性 API  

Web 视图团队正在查找未来版本中可能包含的实验性 Api 的反馈。  实验中的 Api 标记为 `experimental` 在 SDK 中。  若要帮助你评估实验性 Api 并共享你的反馈，请导航到 " [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]" 存储库。  

> [!CAUTION]
> 可从 SDK 向 SDK 引入、修改和删除实验性 Api。  避免在生产应用中使用实验性 Api。  

> [!NOTE]
> 在已安装版本的 WebView2 运行时中，实验性 Api 可能不可用。  

## 匹配 WebView2 运行时版本  
WebView2 应用需要用户安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2]。  WebView2 运行时将自动更新到最新版本的可用版本。  在某些情况下，用户可能希望停止自动 WebView2 运行时更新，这可能会导致应用兼容性问题。  

如果停止 WebView2 运行时更新，请确保你了解你的应用所需的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 的最低版本。  请考虑以下两个项目：  

1.  SDK 的最低要求版本在 WebView2 [发行说明][Webview2Releasenotes] 中的 " **最低 WebView2 运行时版本**" 下找到。  例如，对于 SDK 版本 [1.0.622.22][Webview2Releasenotes1062222]，你必须使用内部版本号或更高版本安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 或 [非稳定 Microsoft Edge 通道][MicrosoftedgeinsiderDownload] `86.0.616.0` 。  只有当 web 平台中发生重大更改时，SDK 所需的最低版本才会发生更改。  
1.  支持你在应用中使用的接口和 Api 所需的最低版本的 NuGet 程序包。  新的接口和 Api 会定期添加到 WebView2。  在 SDK 中捆绑的 Api 和接口需要不同版本的 WebView2 运行时，因为 Api 和接口在不同的时间添加到了 SDK。  所需的 WebView2 运行时版本与第一次引入 API 的 SDK 版本的内部版本号（第三个数字）相匹配。  例如，在 SDK 版本 [1.0.622.22][Webview2Releasenotes1062222] 中添加的新 API 或接口需要 WebView2 运行时版本：  `86.0.622.0`  在更高版本的 SDK 版本中添加的 api 或接口需要具有与 SDK 相同的版本号的 WebView2 运行时。  为了帮助你确定 WebView2 运行时版本是否支持接口或 API，请导航以 [确定 WebView2 运行时要求](#determine-webview2-runtime-requirement)。  
    
> [!IMPORTANT]
> 开发长时间 [WebView2 应用][Webview2ConceptsDistributionEvergreenDistributionMode]时，请定期针对最新版本的 WebView2 运行时和非稳定的 Microsoft Edge 浏览器测试你的应用。  由于 web 平台不断发展，因此定期测试是确保你的应用按预期执行的最佳方式。  

### 确定 WebView2 运行时要求  

请考虑以下项目，具体取决于您使用的是哪个 SDK：  

*   **Win32 C/c + +**。  使用 `QueryInterface` 获取新接口时，请验证返回值 `E_NOINTERFACE` 。  该值可能指示 WebView2 运行时是以前的版本，并且不支持该接口。  有关其工作原理的示例，请导航到 " [行 622-AppWindow][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]"。  
*   **.Net 和 WinUI**。  `No such interface supported`在使用已添加到最新 sdk 的方法、属性和事件时，检查异常。  当 WebView2 运行时是早期版本且不支持 Api 时，可能会发生异常。  
    
如果 API 不可用，请考虑删除关联的功能，或通知用户需要 WebView2 运行时的更新。  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用分发Microsoft 文档"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22-WebView2 SDK 的发行说明 |Microsoft 文档"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 命名空间 |Microsoft 文档"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 命名空间 | WebView2 命名空间 |Microsoft 文档"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 c + + 参考 |Microsoft 文档"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 开发人员"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "Line 622-AppWindow-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  
