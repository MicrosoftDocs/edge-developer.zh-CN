---
description: 用于 Microsoft Edge WebView2 的版本模型
title: 了解 WebView2 SDK 版本
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b292f59e264293a958eb619d04b751203cb517ac
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461176"
---
# <a name="understand-webview2-sdk-versions"></a>了解 WebView2 SDK 版本  

新版本的 WebView2 SDK 的发布常规节奏与 Microsoft Edge \ (Chromium\) 浏览器相同，大约每六周发布一次。  

## <a name="release-and-prerelease-package"></a>发布和预发布包  

WebView2 NuGet 程序包包含发布和预发布包。  

发布 **包与** 向前兼容，并包含以下组件。  

*   [Win32 C/C++ API][ReferenceWin32]
*   .NET [API：WPF、WinForms][DotnetMicrosoftWebWebview2WpfNamespace]和[Core][DotnetMicrosoftWebWebview2CoreNamespace]。 [][DotnetMicrosoftWebWebview2WinformsNamespace]  
    
SDK 中的 API 完全受支持。  

**预发布包是**包含实验性 API 的发布包[的超集](#experimental-apis)。  避免使用预发布 SDK 生成生产应用。  

### <a name="roadmap"></a>路线图  

该发行版包含所有稳定且受支持的 Win32 C/C++ 和 .NET API。  预发布包包含实验性 API，这些 API 可能会根据你的反馈发生变化。  

## <a name="experimental-apis"></a>实验性 API  

WebView 团队正在寻求有关将来版本中可能包含的实验性 API 的反馈。  实验性 API 在 `experimental` SDK 中标记为 。  若要帮助你评估实验性 API 并分享你的反馈，请导航到 [WebView 反馈存储库][GithubMicrosoftedgeWebviewfeedback]。  

> [!CAUTION]
> 实验性 API 可以在 SDK 中引入、修改和删除。  避免在生产应用中使用实验性 API。  

> [!NOTE]
> 实验性 API 可能在你的已安装版本的 WebView2 运行时中不可用。  

## <a name="matching-webview2-runtime-versions"></a>匹配的 WebView2 运行时版本  
WebView2 应用要求用户安装 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2]。  WebView2 运行时自动更新到最新版本。  在某些情况下，用户可能需要停止自动 WebView2 运行时更新，这可能会导致应用兼容性问题。  

如果 WebView2 运行时更新已停止，请确保了解应用所需的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 的最低版本。  请考虑以下两项：  

1.  若要成功加载 webview2 实例，需要 SDK 的最低版本，可以在要加载的最低 Microsoft [][Webview2Releasenotes] Edge 版本下的 WebView2**发行说明找到**。  SDK 需要加载的最低版本仅在 Web 平台发生重大变化时更改。  例如，对于 SDK [版本 1.0.622.22，][Webview2Releasenotes1062222]必须安装具有内部版本号或更新版本的 [WebView2 运行时][MicrosoftDeveloperEdgeWebview2] 或非稳定 [Microsoft Edge][MicrosoftedgeinsiderDownload] 通道 `86.0.616.0` 。   
1.  支持应用中的接口和 API 所需的 NuGet 程序包的最低必需版本位于完全 API 兼容性下的 WebView2 [][Webview2Releasenotes]**发行说明中**。  新接口和 API 会定期添加到 WebView2。  捆绑在 SDK 中的 API 和接口需要不同版本的 WebView2 运行时，因为 API 和接口会在不同的时间添加到 SDK 中。  所需的 WebView2 运行时版本与首次引入 API 的 SDK 版本的内部版本号（即第三个数字）匹配。  例如，在 SDK 版本 [1.0.622.22][Webview2Releasenotes1062222] 中添加的新 API 或接口需要 WebView2 运行时版本 `86.0.622.0` 或更高版本。  在稍后的 SDK 版本中添加的 API 或接口需要与 SDK 版本号相同的 WebView2 运行时。  若要帮助你确定 WebView2 运行时版本是否支持接口或 API，请导航到确定 [WebView2 运行时要求](#determine-webview2-runtime-requirement)。  
    
> [!IMPORTANT]
> 开发 [Evergreen WebView2][Webview2ConceptsDistributionEvergreenDistributionMode]应用时，定期针对最新版本的 WebView2 运行时和非稳定 Microsoft Edge 渠道测试你的应用。  由于 Web 平台在不断演变，因此定期测试是确保应用按预期运行的最佳方法。  

### <a name="determine-webview2-runtime-requirement"></a>确定 WebView2 运行时要求  

根据你使用哪个 SDK，请考虑以下项：  

*   **Win32 C/C++**。  使用 `QueryInterface` 获取新接口时，请验证 的返回值 `E_NOINTERFACE` 。  值可能指示 WebView2 运行时是早期版本，并且不支持该接口。  有关其工作方式的示例，请导航到第 [622 行 - AppWindow.cpp][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]。  
*   **.NET 和 WinUI**。  在使用已添加到最新 SDK 的方法、属性和事件时检查 `No such interface supported` 异常。  当 WebView2 运行时是早期版本，并且不支持 API 时，可能会发生异常。  
    
如果 API 不可用，请考虑删除关联的功能，或通知用户需要更新 WebView2 运行时。  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "常青分发模式 - 使用 WebView2 分配|Microsoft Docs"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK |Microsoft Docs"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22 - WebView2 SDK |Microsoft Docs"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述|Microsoft Docs"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 命名空间|Microsoft Docs"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 命名空间|Microsoft Docs"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 命名空间|Microsoft Docs"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ 参考|Microsoft Docs"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 开发人员"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "第 622 行 - AppWindow.cpp - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  
