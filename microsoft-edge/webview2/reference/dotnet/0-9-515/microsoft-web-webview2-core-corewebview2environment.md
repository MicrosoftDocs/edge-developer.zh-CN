---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 986b1dc2870375243a0ee664262216105edd95a8
ms.sourcegitcommit: 3f8c8a5643e416b0851254833f9771192883ec45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699498"
---
# CoreWebView2Environment 类的 WebView2 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

这表示 WebView2 环境。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[BrowserVersionString](#browserversionstring) | 当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。
[NewBrowserVersionAvailable](#newbrowserversionavailable) | 当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。
[CreateAsync](#createasync) | 使用安装的边缘版本创建长绿 WebView2 环境。
[CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync) | 异步创建新的 Web 视图。
[CreateWebResourceResponse](#createwebresourceresponse) | 创建新的 web 资源响应对象。

在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。 在不同的环境中使用它不保证兼容，并且可能会失败。

## 成员

#### BrowserVersionString 

当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。

> 公共字符串[BrowserVersionString](#browserversionstring)

这与 GetAvailableCoreWebView2BrowserVersionString API 的格式相匹配。 信道名称为 "beta"、"dev" 和 "未设备"。

#### NewBrowserVersionAvailable 

当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。

> 公共事件 EventHandler< 对象 > [NewBrowserVersionAvailable](#newbrowserversionavailable)

若要使用较新版本的浏览器，必须创建新的环境和 Web 视图。 将仅针对从其运行代码的同一边缘通道中的新版本引发此事件。 当不运行安装的边缘时，将不会触发任何事件。

由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的环境和 WebViews。 或者只提示用户重新启动应用。

#### CreateAsync 

使用安装的边缘版本创建长绿 WebView2 环境。

> 公共静态异步任务< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [CreateAsync](#createasync)（string browserExecutableFolder、string userDataFolder、CoreWebView2EnvironmentOptions 选项）

##### 参数
* `browserExecutableFolder` 包含嵌入边缘的文件夹的相对路径。 

* `userDataFolder` 可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。 

* `options` 用于创建 WebView2 环境的选项。

#### CreateCoreWebView2ControllerAsync 

异步创建新的 Web 视图。

> 公共异步任务< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)（IntPtr ParentWindow）

parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。 在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。 由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。

建议为进程或应用程序窗口设置应用程序用户模型 ID。 如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。

#### CreateWebResourceResponse 

创建新的 web 资源响应对象。

> 公共 HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)（流内容、int StatusCode、string ReasonPhrase、string 头）

标头是由换行符分隔的原始响应标题字符串。 也可以使用空的标头字符串创建此对象，然后使用 CoreWebView2HttpResponseHeaders 来逐行构造标题。 有关其他参数的信息，请参阅 CoreWebView2WebResourceResponse。

