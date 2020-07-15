---
description: 了解如何开发安全的 WebView2 应用程序
title: 开发安全 WebView2 应用程序的最佳做法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、安全性
ms.openlocfilehash: 998bcf056e6350efc66880a9ad520f6d969af2f1
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879142"
---
# 开发安全 WebView2 应用程序的最佳做法

[WebView2 控件](https://docs.microsoft.com/microsoft-edge/webview2/)允许开发人员在其本机应用程序中托管 web 内容。 如果使用不当，托管 web 内容提供了多种优点，例如使用基于 web 的 UI、访问 web 平台的功能、共享代码跨平台等。 若要避免托管 web 内容可能引发的漏洞，请确保设计 WebView2 应用程序以密切监视 web 内容和主机应用程序之间的交互。 

1. 将所有 web 内容视为不安全
    - 在使用 web 消息和宿主对象参数之前对其进行验证，因为 web 消息和参数可能不正确（无意或恶意），并导致应用意外运行。
    - 始终检查 WebView2 内运行的文档的来源并评估内容的可信度。 

2. 设计特定的 web 消息和宿主对象交互，而不是使用泛型代理。

3. 通过修改[ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) （Win32）或[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) （.net）来限制 web 内容功能，如下所示：
    - `AreHostObjectsAllowed` `false` 如果不希望 web 内容访问主机对象，则设置为。
    - `IsWebMessageEnabled` `false` 如果不希望 web 内容发布 web 消息到本机应用程序，请设置为。 
    - `IsScriptEnabled` `false` 如果不希望 web 内容运行脚本（例如，显示静态 html 内容时），则设置为。
    - `AreDefaultScriptDialogsEnabled` `false` 如果不希望显示 web 内容或对话框，则设置为 `alert` `prompt` 。

4. 使用 `NavigationStarting` 和 `FrameNavigationStarting` 事件根据新页面的来源更新设置，如下所示：
    1. 若要防止你的应用程序导航到特定页面，请使用这些事件进行检查，然后阻止页面或框架导航。 
    2. 导航到新页面时，你可能需要按照上述说明调整[ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) （Win32）或[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) （.net） ' 上的属性值。

5. 导航到新文档时，请使用 `ContentLoading` 事件删除使用的已公开主机对象 `RemoveHostObjectFromScript` 。 