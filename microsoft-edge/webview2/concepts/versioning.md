---
description: Microsoft Edge WebView2 使用的版本化模型
title: Microsoft Edge WebView2 的版本控制
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 3ce1f0653a14d92571f1365cbfebc8bb2215ecbe
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010675"
---
# 了解 WebView2 SDK 版本  

WebView2 依赖于 Microsoft Edge 才能正常工作。  每个 WebView2 SDK 都要求安装最低版本的浏览器。  最小版本反映在 SDK 的程序包版本中。  例如，如果使用 `SDK package version 0.9.488` ，则必须使用488或更高版本的内部版本号安装 Microsoft Edge。  浏览器版本也在 WebView2 [发行说明][Releasenotes]中指定。  有关最新版本的 Microsoft Edge 浏览器的详细信息，请导航到 [浏览器频道][DeployedgeChannels]。  

> [!NOTE]
> WebView2 当前处于预览版中。  尽管 Web 视图团队致力于确保浏览器版本和 Sdk 之间的向后兼容性，但不能保证它，因为较新版本的浏览器可能不支持以前的 SDK 版本。  如果浏览器版本和 Sdk 之间存在重大更改，则会在 [发行说明][Releasenotes]中指定这些更改。  

将来，Web 视图团队计划更改 WebView2 应用的分布模型。  有关详细信息，请导航到长 [绿分布模式][DistributionEvergreenMode]。  

## 发布和预发布程序包  

在预览中，发布程序包中包含以下。  

*   [Win32 C/c + + api][ReferenceWin3209622]：在公开时，SDK 中的 api 应保持不变。  

在预览中，预发行程序包包含以下组件。  

*   .NET Api： [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]和 [Core][ReferenceDotnet09628]  
*   实验性 Api。  有关详细信息，请参阅 [实验性 api](#experimental-apis) 部分。  

## 实验性 API  

Web 视图团队正在测试可能表示未来功能的实验 Api。  实验中的 Api 标记为 `experimental` 在 SDK 中。  实验性 Api 可能作为 release 程序包中的完全稳定的 Api 提供。  在发布之前，你应该会认为所有实验性 Api 都有更改。  请使用 [Web 视图反馈][GithubMicrosoftedgeWebviewfeedback]存储库评估实验性 api 并共享反馈。  

> [!CAUTION]
> 避免在生产应用中使用实验性 Api。  

## 匹配 WebView2 运行时版本  

使用特定 SDK 版本编写 WebView2 应用时，应用的用户可能会使用 WebView2 运行时的各种兼容版本运行该应用。  将来，较新的兼容 WebView2 运行时版本包含来自旧版兼容 WebView2 运行时版本的所有非实验性 Api 以及其他新的非实验性 Api。  

*   **Win32 C/c + +** 开发人员在使用 `QueryInterface` 获取新接口时，应检查返回值 `E_NOINTERFACE` ，这可能指示 WebView2 运行时较旧且不支持该特定接口。  
*   **.NET and WinUI** `No such interface supported` 当使用在后续 sdk 中添加的方法、属性和事件时，.net 和 WinUI 开发人员应检查异常，当 WebView2 运行时较旧且不支持这些特定的 api 时，可能会发生这种情况。  

如果 API 不可用，请考虑禁用关联的功能（如有可能），或者向最终用户通知他们需要更新其 WebView2 运行时版本。  

可从 SDK 向 SDK 引入、修改和删除实验性 Api。  当尝试使用在 WebView2 运行时中不可用的实验 API 时，你可能会注意到以前描述的行为。  

## 路线图  

在 WebView2 达到稳定的常规可用状态后，发布程序包包含所有稳定的、受支持的 Win32 C/c + + 和 .NET Api。  预发行程序包包含可能会根据你的反馈和共享见解更改的实验性 Api。  

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[ReferenceDotnet09628]: ../reference/dotnet/0-9-628-reference-webview2.md "参考 (WebView2) |Microsoft 文档"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "参考 (WebView2) |Microsoft 文档"  
[ReferenceWin3209622]: ../reference/win32/0-9-622-reference-webview2.md "参考 (WebView2) |Microsoft 文档"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "参考 (WebView2) |Microsoft 文档"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
