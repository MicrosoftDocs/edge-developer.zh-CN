---
description: 了解如何开发安全的 WebView2 应用程序
title: 开发安全 WebView2 应用程序的最佳做法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、安全性
ms.openlocfilehash: f30163954f1906f71afa520b87d58c7647a5250a
ms.sourcegitcommit: b3555043e9d5aefa5a9e36ba4d73934d41559f49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894303"
---
# 开发安全 WebView2 应用程序的最佳做法  

[WebView2 控件][Webview2Main]允许开发人员在本机应用程序中托管 web 内容。 如果使用不当，托管 web 内容提供了多种优点，例如使用基于 web 的 UI、访问 web 平台的功能、共享代码跨平台等。  若要避免托管 web 内容可能引发的漏洞，请确保设计 WebView2 应用程序以密切监视 web 内容和主机应用程序之间的交互。  

1.  将所有 web 内容视为不安全。  
    *   在使用之前验证 web 消息和主机对象参数，因为 web 消息和参数可能格式不正确 \ （无意或恶意 \），并导致应用意外运行。
    *   始终检查 WebView2 内运行的文档的来源并评估内容的可信度。  
1.  设计特定的 web 消息和宿主对象交互，而不是使用泛型代理。  
1.  通过修改[ICoreWebView2Settings （Win32）][Webview2ReferenceWin3209538Icorewebview2settings]或[CoreWebView2Settings （.net）][Webview2ReferenceWin3209538MicrosoftWebWebview2CoreCorewebview2settings]设置以下选项以限制 web 内容功能。  
    *   `AreHostObjectsAllowed` `false` 如果不希望 web 内容访问主机对象，则设置为。  
    *   `IsWebMessageEnabled` `false` 如果不希望 web 内容将 web 消息发布到本机应用程序，则设置为。  
    *   `IsScriptEnabled` `false` 如果您不希望 web 内容运行脚本，请执行 "设置为" （例如，显示静态 html 内容 \）。  
    *   `AreDefaultScriptDialogsEnabled` `false` 如果不希望显示 web 内容或对话框，则设置为 `alert` `prompt` 。  
1.  在以下步骤中，使用 `NavigationStarting` 和 `FrameNavigationStarting` 事件根据新页面的来源更新设置。  
    1.  若要防止你的应用程序导航到特定页面，请使用事件进行检查，然后阻止页面或框架导航。  
    1.  导航到新页面时，你可能需要按照前面所述调整[ICoreWebView2Settings （Win32）][Webview2ReferenceWin3209538Icorewebview2settings]或[CoreWebView2Settings （.net）][Webview2ReferenceWin3209538MicrosoftWebWebview2CoreCorewebview2settings]的属性值。  
1.  导航到新文档时，请使用 `ContentLoading` 事件删除使用的已公开主机对象 `RemoveHostObjectFromScript` 。  

<!--## Security

Always check the Source property of the WebView before using `ExecuteScript`, `PostWebMessageAsJson`, `PostWebMessageAsString`, or any other method to send information into the WebView. The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation. Similarly, be very careful with `AddScriptToExecuteOnDocumentCreated`. All future `navigations` run the same script and if it provides access to information intended only for a certain origin, any HTML document may have access.

When examining the result of an `ExecuteScript` method call, a `WebMessageReceived` event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.

When constructing a message to send into a WebView, prefer using `PostWebMessageAsJson` and construct the JSON string parameter using a JSON library. This avoids any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script. -->  

<!-- links -->  

[Webview2Main]: ../index.md "Microsoft Edge WebView2 简介（预览版） |Microsoft 文档"  

[Webview2ReferenceWin3209538Icorewebview2settings]: ../reference/win32/0-9-538/icorewebview2settings.md "interface ICoreWebView2Settings |Microsoft 文档"  

[Webview2ReferenceWin3209538MicrosoftWebWebview2CoreCorewebview2settings]: ../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md "CoreWebView2Settings 类 | WebView2 类 |Microsoft 文档"  
