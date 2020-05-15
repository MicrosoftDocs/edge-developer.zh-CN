---
description: 将 Win32 应用中的 web 内容托管到 Microsoft Edge Web 部件2控件中
title: Microsoft Edge WebView2 for Win32、WPF 和 WinForms 的发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 14030d3dde8c4e68c0790073dc38e5c856e2a091
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653200"
---
# WebView2 SDK 的发行说明  

[WEBVIEW2 SDK][WebView2NuGetGallery]的发行说明。  

## 0.9.515-预发布

[NuGet 程序包][WebView2NuGetGallery0.9.515-prerelease]|最低 Microsoft Edge 版本84.0.515.0。

**更新 NuGet 程序包后重新编译你的应用。**

* **公告：** WebView2 现在支持 .NET Framework 4.6.2 或更高版本上的 Windows 窗体和 WPF 以及**预发布程序包**中的 .net Core 3.0 或更高版本
* 签出[wpf 入门指南](./gettingstarted/wpf.md)，了解如何开始生成 wpf 应用程序和针对 Wpf 特定 Api 的[wpf 参考](./reference/wpf/0-9-515-reference-webview2.md)
* 签出[Windows 窗体入门指南](./gettingstarted/winforms.md)，开始构建 windows 窗体应用程序和 windows 窗体特定 Api 的[Windows 窗体参考](./reference/winforms/0-9-515-reference-webview2.md)
* 签出 CoreWebView2 Api 的[.Net 参考](./reference/dotnet/0-9-515-reference-webview2.md)
* **已知问题：** 我们知道此预发布中的一些问题，我们将在将来的版本中解决这些问题
  * **DPI 感知：** WPF 的 WebView2 当前不能识别 DPI。 在高 DPI 监视器上初始化 WebView2 时，存在一个已知问题，即 "Web 视图" 首次初始化为窗口的一小部分，直到调整窗口大小。
  * **WPF 设计器：** 此版本目前不支持 WPF 设计器。 通过在文本编辑器中直接修改相应的 XAML，将 WebView2 控件放置在你的应用中

## 0.9.488

[NuGet 程序包][WebView2NuGetGallery0.9.488]|最低 Microsoft Edge 版本84.0.488.0。

**更新 NuGet 程序包后重新编译你的应用。**

* **公告：** 从即将推出的 Microsoft Edge 版本83开始，长时间浏览器将不再面向稳定的浏览器通道。 相反，它将针对另一组二进制文件（即品牌[Microsoft Edge WebView2 运行时](./index.md#microsoft-edge-webview2-runtime)），它可以通过当前正在开发的安装程序进行链安装。 [应用分布](./index.md#app-distribution)中的更多详细信息。
* **公告：** 前进后，我们将发布两个程序包：一个预发布程序包，其中包含实验性 Api （供你试用）和具有稳定 Api 的稳定发布程序包（你可以依赖）。 签出[Microsoft Edge WEBVIEW2 SDK](./index.md#microsoft-edge-webview2-sdk)以了解差异。
* **重大更改：** 为了确保我们的 API 与 Windows API 命名约定相一致，我们已更新以下接口的名称：
  * CORE_WEBVIEW2_ * 前缀现在 COREWEBVIEW2_ *。
  * [GetCoreWebView2BrowserVersionInfo](reference/win32/0-9-430/webview2-idl.md#getcorewebview2browserversioninfo)现已[GetAvailableCoreWebView2BrowserVersionString](reference/win32/0-9-488/webview2-idl.md#getavailablecorewebview2browserversionstring)
  * [get_BrowserVersionInfo](reference/win32/0-9-430/icorewebview2environment.md#get_browserversioninfo)现在[get_BrowserVersionString](reference/win32/0-9-488/icorewebview2environment.md#get_browserversionstring)
  * [AddRemoteObject](reference/win32/0-9-430/icorewebview2.md#addremoteobject)现已[AddHostObjectToScript](reference/win32/0-9-488/icorewebview2.md#addhostobjecttoscript)
  * [RemoveRemoteObject](reference/win32/0-9-430/icorewebview2.md#removeremoteobject)现已[RemoveHostObjectFromScript](reference/win32/0-9-488/icorewebview2.md#removehostobjectfromscript)
  * remoteObjects 现在是 chrome. web hostObjects
* **重大更改：** AddRemoteObject JS 代理方法也已重命名。
  * getLocal 现已 getLocalProperty
  * setLocal 现在 setLocalProperty
  * getRemote 现已 getHostProperty
  * setRemote 现已 setHostProperty
  * applyRemote 现已 applyHostFunction
* **重大更改：** [CreateCoreWebView2EnvironmentWithDetails](reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithdetails)现在已弃用，并且已替换为[CreateCoreWebView2EnvironmentWithOptions](reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithoptions)。  
* 已添加[FrameNavigationCompleted](reference/win32/0-9-488/icorewebview2.md#add_framenavigationcompleted)事件。 现在，当 iframe 完成导航时，将引发一个事件，并返回导航和导航 id 的成功。
* 已添加[ICoreWebView2EnvironmentOptions](reference/win32/0-9-488/ICoreWebView2EnvironmentOptions.md)接口，可用于确定应用程序面向的 WebView2 运行时的版本。
* 已添加[IsBuiltInErrorPageEnabled](reference/win32/0-9-488/ICoreWebView2Settings.md#get_isbuiltinerrorpageenabled)设置。 现在，你可以选择启用或禁用内置错误页面，以便导航失败和呈现进程失败。
* 更新了远程对象注入以支持 .NET IDispatch 实现。 （[#113](https://github.com/MicrosoftEdge/WebViewFeedback/issues/113)）
* 更新了[webview.newwindowrequested](reference/win32/0-9-488/icorewebview2.md#add_newwindowrequested)事件以处理上下文菜单中的请求。 （[#108](https://github.com/MicrosoftEdge/WebViewFeedback/issues/108)）
* 发布了我们的第一个单独的预发布程序包，您可以在其中访问可视化托管 Api。 我们已更新[WebView2APISample](https://github.com/MicrosoftEdge/WebView2Samples)以包含这些新实验性 api。
  * 添加了[ICoreWebView2ExperimentalCompositionController](reference/win32/0-9-488/ICoreWebView2ExperimentalCompositionController.md)接口，用于连接到合成树并提供用于 web 视图的输入。
  * 添加了包含 POINTER_INFO 中的所有信息的[ICoreWebView2ExperimentalPointerInfo](reference/win32/0-9-488/ICoreWebView2ExperimentalPointerInfo.md) 。 它将被传递到 SendPointerInput 以将指针输入插入 Web 视图中。
  * 添加了[ICoreWebView2ExperimentalCursorChangedEventHandler](reference/win32/0-9-488/ICoreWebView2ExperimentalCursorChangedEventHandler.md) ，它将指示应用何时应更改 web 视图上的鼠标光标。 当鼠标位于 Web 视图中的文本框上方时，光标将从箭头更改为选择器。 CompositionController 上的 cursor 属性告诉应用在 Web 视图中，鼠标光标的当前用途。

## 0.9.430

[NuGet 程序包][WebView2NuGetGallery0.9.430]|最低 Microsoft Edge 版本82.0.430.0。

**更新 NuGet 程序包后重新编译你的应用。**

此 SDK 是我们的官方 Win32 c + + Beta 版本，其中包含了我们收到的多个功能请求。 我们尝试限制发布数和重大更改，但在我们接近我们的常规可用性时，我们使用的是 Beta 版本，以便在一次中转中合并多项重大重大更改。

* **重大更改：** 在我们接近最终版本时，我们将把前缀*IWebView2WebView*重命名为*ICoreWebView2* ，以确保我们的 API 与 Windows api 命名约定相一致。 此外，为了让 UI 框架能够使用我们的 SDK 可扩展，我们已将 ICoreWebView2 分为[ICoreWebView2](reference/win32/0-9-430/icorewebview2.md)和[ICoreWebView2Host](reference/win32/0-9-430/icorewebview2host.md)。 ICoreWebView2Host 支持调整大小、显示和隐藏、重点以及与窗口化和合成相关的其他功能。 ICoreWebView2 支持所有其他 WebView2 功能。 若要了解有关合并这些更改的详细信息，请在我们的[WebView2APISample](https://github.com/MicrosoftEdge/WebView2Samples)项目中签出[拉取请求](https://github.com/MicrosoftEdge/WebView2Samples/pull/17)。
* **重大更改：** 将[DocumentStateChanged](reference/win32/0-8-190/iwebview2webview.md#add_documentstatechanged)拆分为三个组件： [SourceChanged](reference/win32/0-9-430/icorewebview2.md#add_sourcechanged)、 [ContentLoading](reference/win32/0-9-430/icorewebview2.md#add_contentloading)和[HistoryChanged](reference/win32/0-9-430/icorewebview2.md#add_historychanged)。 现在，当源 URL 更改时，将引发 SourceChanged 事件。 更改历史记录状态时，将引发 HistoryChanged 事件。 加载新文档时，ContentLoading 事件将在初始脚本之前激发。
* 添加了对 ARM64 体系结构的支持
* 添加了适用于触摸屏设备的软输入面板（SIP）支持
* 添加了对 `Windows Server 2008 R2` 、 `Windows Server 2012/2012 R2` 和的支持 `Windows Server 2016`
* 添加了允许状态栏在窗口模式下关注窗口的[NotifyParentWindowPositionChanged](reference/win32/0-9-430/icorewebview2host.md#notifyparentwindowpositionchanged) 。 这还需要在无窗口模式下实现，以便辅助功能正常工作。
* 添加了[AreRemoteObjectsAllowed](reference/win32/0-9-430/icorewebview2settings.md#get_areremoteobjectsallowed)设置以全局控制是否可由任何远程对象访问页面。 默认情况下，启用 AreRemoteObjectsAllowed，这意味着由[AddRemoteObject](reference/win32/0-9-430/icorewebview2.md#addremoteobject)添加的远程对象可从页面访问。 禁用 AreRemoteObjectsAllowed 时，将无法从页面访问对象。 将在下一个导航事件中应用更改。
* 添加了[IsZoomControlEnabled](reference/win32/0-9-430/icorewebview2settings.md#get_iszoomcontrolenabled)设置以防止用户使用 `ctrl`  +  `+` / `-` 或 `ctrl` + 鼠标滚轮影响 web 视图的缩放。 如果禁用此设置，则仍可通过[put_ZoomFactor](reference/win32/0-9-430/icorewebview2host.md#put_zoomfactor)设置缩放。  
* 将 ZoomFactor 更改为仅应用于当前 Web 视图。 对当前 Web 视图的缩放更改不会影响发生在原始站点上的其他 WebViews。 有关详细信息，请参阅[get_ZoomFactor](reference/win32/0-9-430/icorewebview2host.md#get_zoomfactor) 。
* 用于 Web 视图的 Hid ZoomView UI。 （[#95](https://github.com/MicrosoftEdge/WebViewFeedback/issues/95)）
* 已添加[SetBoundsAndZoomFactor](reference/win32/0-9-430/icorewebview2host.md#setboundsandzoomfactor)。 现在，你可以同时设置 Web 视图的缩放系数和边界。
* 已添加[WindowCloseRequested](reference/win32/0-9-430/icorewebview2.md#add_windowcloserequested)事件。 有关详细信息，请参阅[add_WindowCloseRequested](reference/win32/0-9-430/icorewebview2.md#add_windowcloserequested) 。 （[#119](https://github.com/MicrosoftEdge/WebViewFeedback/issues/119)）
* 添加了对 javascript 对话框事件的 beforeunload 对话框类型和已添加[CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD](reference/win32/0-9-430/icorewebview2.md#core_webview2_script_dialog_kind)枚举项的支持。
* 将[GetHeaders](reference/win32/0-9-430/icorewebview2httprequestheaders.md#getheaders)添加到 HttpRequestHeaders， [GetHeader](reference/win32/0-9-430/icorewebview2httpresponseheaders.md#getheader)到 HttpResponseHeaders，并将[get_HasCurrentHeader](reference/win32/0-9-430/icorewebview2httpheaderscollectioniterator.md#get_hascurrentheader)属性添加到 HttpHeadersCollectionIterator。
* **重大更改：** 已修改 DevToolsProtocolEventReceived 行为。 现在，你可以为特定的 DevTools 协议事件创建[DevToolsProtocolEventReceiver](reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md) ，并使用[add_DevToolsProtocolEventReceived](reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md#add_devtoolsprotocoleventreceived)remove_DevToolsProtocolEventReceived 订阅/取消订阅此类事件 / [remove_DevToolsProtocolEventReceived](reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md#remove_devtoolsprotocoleventreceived)。
* **重大更改：** 已将 WebMessageReceivedEventArgs " [get_WebMessageAsString](reference/win32/0-8-190/iwebview2webmessagereceivedeventargs.md#get_webmessageasstring)属性更改为[TryGetWebMessageAsString](reference/win32/0-9-430/icorewebview2webmessagereceivedeventargs.md#trygetwebmessageasstring)方法。
* **重大更改：** 已将 AcceleratorKeyPressedEventArgs " [Handle](reference/win32/0-8-190/iwebview2acceleratorkeypressedeventargs.md#handle)方法更改为[get_Handled](reference/win32/0-9-430/icorewebview2acceleratorkeypressedeventargs.md#get_handled)属性。

## 0.8.355

[NuGet 程序包][WebView2NuGetGallery0.8.355]|最低 Microsoft Edge 版本80.0.355.0。

**更新 NuGet 程序包后重新编译你的应用。**

* 发布 WebView2API 示例-我们的 SDK 的综合指南。 请[在此处](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample)查看！
* 添加了除英语之外的所有语言的 IME 支持。 （[#30](https://github.com/MicrosoftEdge/WebViewFeedback/issues/30)）
* 更新了 WebResourceRequested 事件的 API 图面以响应 bug 报告。  同时指定筛选器和创建事件现在已被否决。  若要创建 web 资源请求的事件，请使用[add_WebResourceRequested](reference/win32/0-8-190/iwebview2webview5.md#add_webresourcerequested)添加事件和[AddWebResourceRequestedFilter](reference/win32/0-8-190/iwebview2webview5.md#addwebresourcerequestedfilter)以添加筛选器。  [RemoveWebResourceRequestedFilter](reference/win32/0-8-190/iwebview2webview5.md#removewebresourcerequestedfilter)将删除筛选器。  （[#36](https://github.com/MicrosoftEdge/WebViewFeedback/issues/36)）（[#74](https://github.com/MicrosoftEdge/WebViewFeedback/issues/74)）  
* **重大更改：** 已修改的全屏行为。 弃用的[IsFullScreenAllowed](reference/win32/0-8-190/IWebView2Settings.md#get_isfullscreenallowed_deprecated)。  现在，默认情况下，如果 Web 视图（如视频）内的某个元素设置为全屏，它将填充 Web 视图的边界。  使用[ContainsFullScreenElementChanged](reference/win32/0-8-190/IWebView2ContainsFullScreenElementChangedEventHandler.md#interface-iwebview2containsfullscreenelementchangedeventhandler)事件和[get_ContainsFullScreenElement](reference/win32/0-8-190/iwebview2webview5.md#get_containsfullscreenelement)指定如果元素要进入全屏模式，应用应如何调整 web 视图的大小。  

## 0.8.314

[NuGet 程序包][WebView2NuGetGallery0.8.314]|最低 Microsoft Edge 版本80.0.314.0。

**更新 NuGet 程序包后重新编译你的应用。**

* 添加了对 Windows 7、Windows 8/8.1 的支持。
* 已添加 Visual Studio 和 Visual Studio 代码调试支持 WebView2。 现在，你可以在 WebView2 中从 IDE 调试你的脚本。 单击[此处](/microsoft-edge/hosting/webview2#debugging-webview2)了解更多详细信息。  
* 已添加 `Native Object Injection` ，允许在 WebView2 内运行的脚本从应用程序的 Win32 组件传递 IDispatch 对象，并访问 idispatch 对象的属性。  有关详细信息，请参阅[AddRemoteObject](reference/win32/0-8-190/iwebview2webview4.md#addremoteobject) 。  （[#17](https://github.com/MicrosoftEdge/WebViewFeedback/issues/17)）。  
* 已添加 `AcceleratorKeyPressed` 事件。  有关详细信息，请参阅[add_AcceleratorKeyPressed](reference/win32/0-8-190/iwebview2webview4.md#add_acceleratorkeypressed) 。  （[#57](https://github.com/MicrosoftEdge/WebViewFeedback/issues/57)）。  
* 已禁用 `Context Menus` 。  有关详细信息，请参阅[put_AreDefaultContextMenusEnabled](reference/win32/0-8-190/iwebview2settings2.md#put_aredefaultcontextmenusenabled) （[#57](https://github.com/MicrosoftEdge/WebViewFeedback/issues/57)）。  
* 已更新 `DPI Awareness` 。 现在，Web 视图的 DPI 感知将与宿主应用程序的 DPI 感知一致。 注意，如果另一个混合应用程序是使用与原始 Web 视图不同的 DPI 感知启动的，则当用户数据目录相同（[#1](https://github.com/MicrosoftEdge/WebViewFeedback/issues/1)）时，将不会启动新的 web 视图。
* 已更新 `Notification Change Behavior` ，WebView2 将自动拒绝由 Web 视图中托管的 web 内容提示的通知权限请求。

## 0.8.270  

[NuGet 程序包][WebView2NuGetGallery0.8.270]|最低 Microsoft Edge 版本78.0.270.0。  

**更新 NuGet 程序包后重新编译你的应用。**

* 添加了 `DocumentTitleChanged` 指示文档标题更改 \ （[\ #27][MicrosoftEdgeWebViewFeedbackIssue27]\）的事件。  
* 已添加 `GetWebView2BrowserVersionInfo` API \ （[\ #18][MicrosoftEdgeWebViewFeedbackIssue18]\）。  
* 已添加 `NewWindowRequested` 事件。  
* `CreateWebView2EnvironmentWithDetails`要删除的已更新函数 `releaseChannelPreference` 。  有关详细信息，请参阅[CreateWebView2EnvironmentWithDetails][WebViewsGlobalsCreateWebView2EnvironmentWithDetails]函数。  注册表和环境变量替代仍受支持。  除非被覆盖，否则使用默认通道首选项。  
    在通道搜索过程中，我们将跳过与 WebView2 SDK 不兼容的任何旧版频道版本。  
    我们选择更稳定的频道，以确保最一致的最终用户行为。  在使用最新的 "最新" 的新版本进行测试时，应创建一个脚本以 `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` `1` 在启动应用之前将环境变量设置为。  
* `CreateWebView2EnvironmentWithDetails`在未指定时用于选择的逻辑的更新函数 `userDataFolder` 。  有关详细信息，请参阅[CreateWebView2EnvironmentWithDetails][WebViewsGlobalsCreateWebView2EnvironmentWithDetails]函数。  如果你以前使用的是默认 `userDataFolder` 位置，则当你切换到新的 SDK 时，默认值 `userDataFolder` 将重置（设置为主机代码目录中的新位置），并且你的状态也会重置。  
    如果主机进程没有写入指定目录的权限，则 `CreateWebView2EnvironmentWithDetails` 可能失败。  你可以将旧用户数据目录中的数据复制到新目录。  

## 0.8.230  

[NuGet 程序包][WebView2NuGetGallery0.8.230]|最低 Microsoft Edge 版本77.0.230.0。  

**更新 NuGet 程序包后重新编译你的应用。**

* 添加了 `Stop` 用于停止所有导航和挂起资源提取的 API \ （[\ #28][MicrosoftEdgeWebViewFeedbackIssue28]\）。  
* 已将 .tlb 文件添加到 Nuget 程序包 \ （[\ #22][MicrosoftEdgeWebViewFeedbackIssue22]\）。  
* 已将 .NET 项目添加到 NuGet 程序包中的安装程序列表 \ （[\ #32][MicrosoftEdgeWebViewFeedbackIssue32]\）。  

## 0.8.190  

[NuGet 程序包][WebView2NuGetGallery0.8.190]|最低 Microsoft Edge 版本77.0.190.0。  

**更新 NuGet 程序包后重新编译你的应用。**

* 添加 `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` 到控件，以便用户可以打开 DevTools \ （[\ #16][MicrosoftEdgeWebViewFeedbackIssue16]\）。  
* 添加 `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` 到控件（如果显示状态栏） \ （[\ #19][MicrosoftEdgeWebViewFeedbackIssue19]\）。  
* 添加， `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` 用于在导航历史记录中后退和前进。  
* 添加 `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` 了用于在 web 视图中查看和修改 http 标头的 HTTP 标头类型（）。  
* 在64位计算机上添加了32位 Web 视图支持 \ （[\ #13][MicrosoftEdgeWebViewFeedbackIssue13]\）。  
* 已将 Web 视图 IDL 添加到 SDK \ （[\ #14][MicrosoftEdgeWebViewFeedbackIssue14]\）。  
* 添加了支持 IID\_\ * 接口 id 对象的 lib \ （[\ #12][MicrosoftEdgeWebViewFeedbackIssue12]\）。  
* 已将 DLL 文件的包含路径、链接和自动复制添加到 SDK 中的 NuGet 目标文件。  
* 已启用 `window.open` 脚本中的请求。  

## 0.8.149  

[NuGet 程序包][WebView2NuGetGallery0.8.149]|最低 Microsoft Edge 版本76.0.149.0。  

初始开发人员预览版。  

<!-- image links -->

<!-- Links -->
[MicrosoftEdgeWebViewFeedbackIssue12]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback 问题12的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue13]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback 问题13的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue14]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback 问题14的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue16]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 问题16的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue18]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback 问题18的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue19]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback 问题19的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue22]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback 问题22的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue27]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback 问题27的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue28]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback 问题28的反馈存储库"  
[MicrosoftEdgeWebViewFeedbackIssue32]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback 问题32的反馈存储库"  

[WebView2NuGetGallery]: https://aka.ms/webviewnuget "NuGet 库 |WebView2"  
[WebView2NuGetGallery0.8.149]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet 库 |WebView2 v 0.8.149"  
[WebView2NuGetGallery0.8.190]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet 库 |WebView2 v 0.8.190"  
[WebView2NuGetGallery0.8.230]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet 库 |WebView2 v 0.8.230"  
[WebView2NuGetGallery0.8.270]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet 库 |WebView2 v 0.8.270"  
[WebView2NuGetGallery0.8.314]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet 库 |WebView2 v 0.8.314"  
[WebView2NuGetGallery0.8.355]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet 库 |WebView2 v 0.8.355"  
[WebView2NuGetGallery0.9.430]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet 库 |WebView2 v 0.9.430"
[WebView2NuGetGallery0.9.488]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet 库 |WebView2 v 0.9.488"
[WebView2NuGetGallery0.9.515-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet 库 |WebView2 v 0.9.515 预发布"

[WebViewsGlobalsCreateWebView2EnvironmentWithDetails]: reference/win32/0-8-190/webview2-idl.md#createwebview2environmentwithdetails "Web 视图 Globals-CreateWebView2EnvironmentWithDetails 函数"  
