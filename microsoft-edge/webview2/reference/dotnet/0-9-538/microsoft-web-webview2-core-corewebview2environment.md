---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 3af7c02f51a203e434c92bac5219dc4db58f406b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698427"
---
# CoreWebView2Environment 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

这表示 WebView2 环境。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[BrowserVersionString](#browserversionstring) | 当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。
[NewBrowserVersionAvailable](#newbrowserversionavailable) | 当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。
[CompareBrowserVersions](#comparebrowserversions) | 正确比较浏览器版本以确定哪个版本较旧、更旧或相同。
[CreateAsync](#createasync) | 使用安装的边缘版本创建长绿 WebView2 环境。
[CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync) | 异步创建用于可视化托管的新 Web 视图。
[CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync) | 异步创建新的 Web 视图。
[CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo) | 创建一个空 CoreWebView2ExperimentalPointerInfo。
[CreateWebResourceResponse](#createwebresourceresponse) | 创建新的 web 资源响应对象。
[GetAvailableBrowserVersionString](#getavailablebrowserversionstring) | 获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。
[GetProviderForHwnd](#getproviderforhwnd) | 返回与给定 HWND 对应的 CoreWebView2CompositionController 的 UI 自动化提供程序。

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

#### CompareBrowserVersions 

正确比较浏览器版本以确定哪个版本较旧、更旧或相同。

> 公共静态 int [CompareBrowserVersions](#comparebrowserversions)（string version1，string version2）

返回-1、0或1，具体取决于 version1 是否小于、等于或大于 version2。

##### 参数
* `version1` 要比较的版本字符串之一。 

* `version2` 要比较的其他版本字符串。

#### CreateAsync 

使用安装的边缘版本创建长绿 WebView2 环境。

> 公共静态异步任务< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [CreateAsync](#createasync)（string browserExecutableFolder、string userDataFolder、CoreWebView2EnvironmentOptions 选项）

##### 参数
* `browserExecutableFolder` 包含嵌入边缘的文件夹的相对路径。 

* `userDataFolder` 可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。 

* `options` 用于创建 WebView2 环境的选项。

#### CreateCoreWebView2CompositionControllerAsync 

> [!NOTE]
> 这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。

异步创建用于可视化托管的新 Web 视图。

> 公共异步任务< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md)  >  [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)（IntPtr ParentWindow）

parentWindow 是应用将连接 Web 视图的可视化树的 HWND。 这将是应用将接收指向 Web 视图的指针/鼠标输入的 HWND （并且将需要使用 SendMouseInput/SendPointerInput 转发）。 如果应用将 Web 视图可视化树移动到另一个窗口下方，则需要设置 CoreWebView2CompositionController 以更新可视化树的新父 HWND。

在创建的 CoreWebView2CompositionController 上设置 RootVisualTarget 属性，以提供视觉对象以托管浏览器的可视化树。

建议为进程或应用程序窗口设置应用程序用户模型 ID。 如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。

#### CreateCoreWebView2ControllerAsync 

异步创建新的 Web 视图。

> 公共异步任务< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)（IntPtr ParentWindow）

parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。 在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。 由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。

建议为进程或应用程序窗口设置应用程序用户模型 ID。 如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。

#### CreateCoreWebView2PointerInfo 

> [!NOTE]
> 这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。

创建一个空 CoreWebView2ExperimentalPointerInfo。

> 公共[CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)（）

在调用 SendPointerInput 之前，需要用所有相关信息填充返回的 CoreWebView2ExperimentalPointerInfo。

#### CreateWebResourceResponse 

创建新的 web 资源响应对象。

> 公共 HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)（流内容、int StatusCode、string ReasonPhrase、string 头）

标头是由换行符分隔的原始响应标题字符串。 也可以使用空的标头字符串创建此对象，然后使用 CoreWebView2HttpResponseHeaders 来逐行构造标题。 有关其他参数的信息，请参阅 CoreWebView2WebResourceResponse。

#### GetAvailableBrowserVersionString 

获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。

> 公共静态字符串[GetAvailableBrowserVersionString](#getavailablebrowserversionstring)（string browserExecutableFolder）

##### 参数
* `browserExecutableFolder` 包含嵌入边缘的文件夹的相对路径。

#### GetProviderForHwnd 

> [!NOTE]
> 这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。

返回与给定 HWND 对应的 CoreWebView2CompositionController 的 UI 自动化提供程序。

> 公共对象[GetProviderForHwnd](#getproviderforhwnd)（IntPtr hwnd）

