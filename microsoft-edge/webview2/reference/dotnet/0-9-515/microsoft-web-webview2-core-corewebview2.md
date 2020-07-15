---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: f17621b1ea387855e060eaebe0cd096f2bacaf50
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879371"
---
# 0.9.515-WebView2 的 CoreWebView2 类 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[BrowserProcessId](#browserprocessid) | 托管 Web 视图的浏览器进程的进程 id。
[CanGoBack](#cangoback) | 如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。
[CanGoForward](#cangoforward) | 如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。
[ContainsFullScreenElement](#containsfullscreenelement) | 指示 Web 视图是否包含全屏 HTML 元素。
[ContainsFullScreenElementChanged](#containsfullscreenelementchanged) | ContainsFullScreenElement 属性更改时通知。
[ContentLoading](#contentloading) | ContentLoading 在加载任何内容之前激发，包括使用 AddScriptToExecuteOnDocumentCreated ContentLoading 添加的脚本在同一页面导航（如通过片段导航或历史记录）发生时不会触发。
[DocumentTitle](#documenttitle) | 当前顶级文档的标题。
[DocumentTitleChanged](#documenttitlechanged) | 当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。
[FrameNavigationCompleted](#framenavigationcompleted) | 当子框架已完全加载（已激发了 FrameNavigationCompleted）或加载时出错，已停止加载时，将引发事件。
[FrameNavigationStarting](#framenavigationstarting) | 当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。
[HistoryChanged](#historychanged) | 历史记录更改侦听顶级文档的导航历史记录更改。
[NavigationCompleted](#navigationcompleted) | 当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。
[NavigationStarting](#navigationstarting) | 当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。
[Webview.newwindowrequested](#newwindowrequested) | 在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。
[Webview.permissionrequested](#permissionrequested) | 在 Web 视图中的内容请求访问某些权限资源的权限时引发。
[ProcessFailed](#processfailed) | 当 Web 视图进程意外终止或停止响应时激发。
[ScriptDialogOpening](#scriptdialogopening) | 将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。
[“设置”](#settings) | CoreWebView2Settings 对象包含适用于运行的的各种可修改设置
[来源](#source) | 当前顶级文档的 URI。
[SourceChanged](#sourcechanged) | Source 属性更改时将触发 SourceChanged。
[WebMessageReceived](#webmessagereceived) | 当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。
[WebResourceRequested](#webresourcerequested) | 在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。
[WindowCloseRequested](#windowcloserequested) | 在 Web 视图中请求关闭窗口的内容（如在窗口后）关闭窗口时激发。调用 close。
[AddHostObjectToScript](#addhostobjecttoscript) | 将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。
[AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync) | 将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。
[AddWebResourceRequestedFilter](#addwebresourcerequestedfilter) | 将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。
[CallDevToolsProtocolMethodAsync](#calldevtoolsprotocolmethodasync) | 调用异步 DevToolsProtocol 方法。
[CapturePreviewAsync](#capturepreviewasync) | 捕获 Web 视图显示的图像。
[ExecuteScriptAsync](#executescriptasync) | 从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。
[GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver) | 获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。
[GoBack](#goback) | 将 Web 视图导航到导航历史记录中的上一页。
[GoForward](#goforward) | 将 Web 视图导航到导航历史记录中的下一页。
[导航](#navigate) | 导致将顶级文档导航到指定的 URI。
[NavigateToString](#navigatetostring) | 启动作为新文档的源 HTML 的 htmlContent 导航。
[OpenDevToolsWindow](#opendevtoolswindow) | 在 Web 视图中打开当前文档的 DevTools 窗口。
[PostWebMessageAsJson](#postwebmessageasjson) | 将指定的 webMessage 发布到此 Web 视图中的顶级文档。
[PostWebMessageAsString](#postwebmessageasstring) | 这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。
[重载](#reload) | 重新加载当前页面。
[RemoveHostObjectFromScript](#removehostobjectfromscript) | 删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。
[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated) | 删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。
[RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter) | 删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。
[停止](#stop) | 停止所有导航和挂起的资源提取。

## 成员

#### BrowserProcessId 

托管 Web 视图的浏览器进程的进程 id。

> 公共 uint [BrowserProcessId](#browserprocessid)

#### CanGoBack 

如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。

> 公共 bool [CanGoBack](#cangoback)

如果 CanGoBack 更改值，将引发 HistoryChanged 事件。

#### CanGoForward 

如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。

> 公共 bool [CanGoForward](#cangoforward)

如果 CanGoForward 更改值，将引发 HistoryChanged 事件。

#### ContainsFullScreenElement 

指示 Web 视图是否包含全屏 HTML 元素。

> 公共 bool [ContainsFullScreenElement](#containsfullscreenelement)

#### ContainsFullScreenElementChanged 

ContainsFullScreenElement 属性更改时通知。

> 公共事件 EventHandler< 对象 > [ContainsFullScreenElementChanged](#containsfullscreenelementchanged)

这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。 例如，当视频元素请求进入全屏时，此事件非常有用。 然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。

#### ContentLoading 

ContentLoading 在加载任何内容之前激发，包括使用 AddScriptToExecuteOnDocumentCreated ContentLoading 添加的脚本在同一页面导航（如通过片段导航或历史记录）发生时不会触发。

> 公共事件 EventHandler< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)  >  [ContentLoading](#contentloading)

这将遵循 NavigationStarting 和 SourceChanged 事件，并在 HistoryChanged 和 NavigationCompleted 事件之前。

#### DocumentTitle 

当前顶级文档的标题。

> 公共字符串[DocumentTitle](#documenttitle)

如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。

#### DocumentTitleChanged 

当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。

> 公共事件 EventHandler< 对象 > [DocumentTitleChanged](#documenttitlechanged)

#### FrameNavigationCompleted 

当子框架已完全加载（已激发了 FrameNavigationCompleted）或加载时出错，已停止加载时，将引发事件。

> 公共事件 EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [FrameNavigationCompleted](#framenavigationcompleted)

#### FrameNavigationStarting 

当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。

> 公共事件 EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [FrameNavigationStarting](#framenavigationstarting)

这也会引发重定向。

#### HistoryChanged 

历史记录更改侦听顶级文档的导航历史记录更改。

> 公共事件 EventHandler< 对象 > [HistoryChanged](#historychanged)

使用历史记录更改检查 CanGoBack/CanGoForward 值是否已更改。 使用 GoBack/GoForward 时也会触发 HistoryChanged。 HistoryChanged 在 SourceChanged 和 ContentLoading 后激发。 为 HistoryChanged 事件添加事件处理程序。

#### NavigationCompleted 

当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。

> 公共事件 EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [NavigationCompleted](#navigationcompleted)

#### NavigationStarting 

当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。

> 公共事件 EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [NavigationStarting](#navigationstarting)

这也会引发重定向。

#### Webview.newwindowrequested 

在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。

> 公共事件 EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)  >  [webview.newwindowrequested](#newwindowrequested)

应用可以传递将被视为打开的窗口的目标 web 视图。

#### Webview.permissionrequested 

在 Web 视图中的内容请求访问某些权限资源的权限时引发。

> 公共事件 EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)  >  [webview.permissionrequested](#permissionrequested)

#### ProcessFailed 

当 Web 视图进程意外终止或停止响应时激发。

> 公共事件 EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md)  >  [ProcessFailed](#processfailed)

#### ScriptDialogOpening 

将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。

> 公共事件 EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)  >  [ScriptDialogOpening](#scriptdialogopening)

仅当 AreDefaultScriptDialogsEnabled 属性设置为 false 时，此事件才会触发 CoreWebView2Settings。 ScriptDialogOpening 事件可用于取消对话框或使用自定义对话框替换默认对话框。

#### “设置” 

CoreWebView2Settings 对象包含适用于运行的的各种可修改设置

> 公共[CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md) [设置](#settings)

#### 来源 

当前顶级文档的 URI。

> 公共字符串[源](#source)

在某些情况下（例如导航到不同的网站或片段导航），此值可能会更改 SourceChanged 事件的一部分。 它对于其他类型的导航（如页面重新加载或 pushState 与当前页面具有相同的 URL）保持不变。

#### SourceChanged 

Source 属性更改时将触发 SourceChanged。

> 公共事件 EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)  >  [SourceChanged](#sourcechanged)

导航到其他网站或片段导航时，将引发 SourceChanged。 对于其他类型的导航（如页面重新加载或 pushState，其 URL 与当前页面相同），不会引发此类导航。 SourceChanged 将在 ContentLoading 之前激发，以便导航到新文档。 为 SourceChanged 事件添加事件处理程序。

#### WebMessageReceived 

当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。

> 公共事件 EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)  >  [WebMessageReceived](#webmessagereceived)

PostMessage 函数是 `void postMessage(object)` 对象是 JSON 转换支持的任何对象。 当调用 postMessage 时，将使用转换为 JSON 字符串的 postMessage 对象参数来调用 CoreWebView2WebMessageReceivedEventHandler 集。

#### WebResourceRequested 

在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。

> 公共事件 EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)  >  [WebResourceRequested](#webresourcerequested)

必须至少添加一个筛选器，才能触发该事件。

#### WindowCloseRequested 

在 Web 视图中请求关闭窗口的内容（如在窗口后）关闭窗口时激发。调用 close。

> 公共事件 EventHandler< 对象 > [WindowCloseRequested](#windowcloserequested)

如果应用程序有意义，则应用应关闭 Web 视图和相关应用窗口。

#### AddHostObjectToScript 

将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。

> 公共 void [AddHostObjectToScript](#addhostobjecttoscript)（字符串名称、对象 rawObject）

主机对象通过来公开为主机对象代理 `window.chrome.webview.hostObjects.{name}` 。 主机对象代理承诺并将解析为表示主机对象的对象。 Web 视图中的 JavaScript 代码将能够按如下方式访问 appObject，然后访问 appObject 的属性和方法： 
```
let app_object = await window.chrome.webview.hostObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```
 请注意，虽然简单类型、IDispatch 和数组受支持、泛型 IUnknown、VT_DECIMAL 或 VT_RECORD 变体不受支持。 远程 JavaScript 对象（如回调函数）使用实现 IDispatch 的对象表示为 VT_DISPATCH 变体。 可以使用 DISPID 的 DISPID_VALUE 调用 JavaScript 回调方法。 嵌套数组的支持深度为3。 不支持按引用类型的数组。 VT_EMPTY 和 VT_NULL 以 NULL 的形式映射到 JavaScript。 在 JavaScript null 中，未定义映射到 VT_EMPTY。

此外，所有主机对象都公开为 `window.chrome.webview.hostObjects.sync.{name}` 。 此处，主机对象作为同步主机对象代理公开。 这些不承诺且对函数或属性访问的调用会同步阻止正在等待通信的运行脚本，以便主机代码运行。 因此，可能会导致可靠性问题，建议使用上述基于承诺的异步 `window.chrome.webview.hostObjects.{name}` API。

同步主机对象代理和异步主机对象代理都可以代理相同的主机对象。 一个代理所做的远程更改将反映在同一主机对象的任何其他代理中，无论其他代理和同步还是异步。

虽然 JavaScript 在对本机代码的同步调用上被阻止，但该本机代码无法回调到 JavaScript。 尝试执行此操作将失败，并 HRESULT_FROM_WIN32 （ERROR_POSSIBLE_DEADLOCK）。

主机对象代理是截取所有属性获取、属性集和方法调用的 JavaScript 代理对象。 作为函数或对象原型一部分的属性或方法在本地运行。 此外，数组中的任何属性或方法 `chrome.webview.hostObjects.options.forceLocalProperties` 也将在本地运行。 这是默认设置，包括在 JavaScript 中具有含义的可选方法 `toJSON` ，如和 `Symbol.toPrimitive` 。 你可以根据需要向此数组添加更多。

有一种方法 `chrome.webview.hostObjects.cleanupSome` 可以最大努力垃圾回收主机对象代理。

宿主对象代理还具有以下可在本地运行的方法：

* applyHostFunction、getHostProperty、setHostProperty：对主机对象执行方法调用、属性获取或属性设置。 如果存在冲突的本地方法或属性，则可以使用这些属性显式强制在远程运行某个方法或属性。 例如， `proxy.toString()` 将对代理对象运行本地 toString 方法。 而 `proxy.applyHostFunction('toString')` `toString` 是在主机代理对象上运行。

* getLocalProperty、setLocalProperty：执行属性 get 或本地设置属性。 你可以使用这些方法强制获取或设置主机对象代理本身的属性，而不是它所表示的主机对象上的属性。 例如， `proxy.unknownProperty` 将获取 `unknownProperty` 从 host 代理对象命名的属性。 但 `proxy.getLocalProperty('unknownProperty')` 将获取 `unknownProperty` 代理对象本身的属性值。

* 同步：异步主机对象代理公开同步方法，该方法可为同一主机对象的同步主机对象代理返回承诺。 例如， `chrome.webview.hostObjects.sample.methodCall()` 返回一个异步主机对象代理。 可以 `sync` 改为使用该方法获取同步主机对象代理： `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* 异步：同步主机对象代理公开一个 async 方法，该方法会阻止并返回同一主机对象的异步主机对象代理。 例如， `chrome.webview.hostObjects.sync.sample.methodCall()` 返回同步主机对象代理。 `async`在此块上调用该方法，然后返回同一 host 对象的异步主机对象代理： `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* 然后：异步主机对象代理具有 then 方法。 这使它们能够可等待。 `then` 将返回通过主机对象的表示形式解析的承诺。 如果代理表示 JavaScript 文本，则会在本地返回一个副本。 如果代理表示一个函数，则返回非可等待代理。 如果代理表示的 JavaScript 对象混合了文本属性和函数属性，则会将某些属性作为主机对象代理返回该对象的副本。

所有其他属性和方法调用（除了上述远程对象代理方法、forceLocalProperties 列表和函数和对象原型上的属性）都是远程运行的。 异步主机对象代理返回表示异步完成远程调用该方法或获取属性的一种承诺。 在远程操作完成后，承诺将解决该操作的结果值。 同步主机对象代理的工作方式类似，但阻止了 JavaScript 执行，并等待远程操作完成。

在异步主机对象代理上设置属性的工作方式略有不同。 Set 将立即返回，返回值为将设置的值。 这是 JavaScript 代理对象的要求。 如果需要异步等待属性设置为 "完成"，请使用 setHostProperty 方法，该方法将返回上述承诺。 同步对象属性 set 属性在设置该属性之前同步地阻止。

#### AddScriptToExecuteOnDocumentCreatedAsync 

将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。

> 公共异步任务< 字符串 > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)（字符串 javaScript）

插入的脚本将应用于所有未来的顶级文档和子框架导航，直到使用 RemoveScriptToExecuteOnDocumentCreated 删除。 这是异步应用的，你必须等待完成处理程序运行，然后才能确保脚本已准备好在将来的导航上执行。

请注意，如果 HTML 文档通过[沙盒](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)属性或[内容安全策略 HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)进行了某种类型的沙盒，则会影响在此处运行脚本。 例如，如果未设置 "allow-modals" 关键字，则将忽略对该函数的调用 `alert` 。

#### AddWebResourceRequestedFilter 

将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。

> 公共 void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)（string Uri，CoreWebView2WebResourceContext ResourceContext）

URI 参数可以是通配符字符串（""：零或更多，'？ '：正好是一）。 nullptr 等效于 L ""。 有关资源上下文筛选器的说明，请参阅 CoreWebView2WebResourceContext enum。

#### CallDevToolsProtocolMethodAsync 

调用异步 DevToolsProtocol 方法。

> 公共异步任务< 字符串 > [CallDevToolsProtocolMethodAsync](#calldevtoolsprotocolmethodasync)（String 方法名称、字符串 parametersAsJson）

有关可用方法的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。 "方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。 ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。 当方法异步完成时，将调用处理程序的 Invoke 方法。 将使用方法的返回对象作为 JSON 字符串调用调用。

#### CapturePreviewAsync 

捕获 Web 视图显示的图像。

> 公共异步任务[CapturePreviewAsync](#capturepreviewasync)（CoreWebView2CapturePreviewImageFormat ImageFormat，Stream imageStream）

指定具有 imageFormat 参数的图像的格式。 生成的图像二进制数据将写入所提供的 imageStream 参数。 当 CapturePreview 完成写入流时，将调用所提供的处理程序参数上的 Invoke 方法。

#### ExecuteScriptAsync 

从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。

> 公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串 javaScript）

这将异步执行，并且在完成后，如果 ExecuteScriptCompletedHandler 参数中提供了处理程序，则将通过评估所提供的 JavaScript 的结果调用其 Invoke 方法。 结果值是一个 JSON 编码的字符串。 如果结果未定义、包含引用循环或者其他无法编码到 JSON，则将以字符串 "null" 形式返回 JSON null 值。 请注意，没有显式返回值的函数将返回 undefined。 如果执行的脚本引发了未处理的异常，则结果也为 "null"。 此方法是异步应用的。 如果在导航过程中 NavigationStarting 事件后调用该方法，则会在加载新文档时在新文档中执行该脚本，同时引发 ContentLoading。 即使 IsScriptEnabled 设置为 FALSE，ExecuteScript 仍可正常工作。

#### GetDevToolsProtocolEventReceiver 

获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。

> 公共 CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)（string 事件）

有关可用方法的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。 "方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。 ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。 当方法异步完成时，将调用处理程序的 Invoke 方法。 将使用方法的返回对象作为 JSON 字符串调用调用。

#### GoBack 

将 Web 视图导航到导航历史记录中的上一页。

> 公共 void [GoBack](#goback)（）

#### GoForward 

将 Web 视图导航到导航历史记录中的下一页。

> 公共 void [GoForward](#goforward)（）

#### 导航 

导致将顶级文档导航到指定的 URI。

> 公共 void[导航](#navigate)（字符串 uri）

有关详细信息，请参阅导航事件。 请注意，这将启动导航，并且相应的 NavigationStarting 事件将在此导航调用完成后的某个时间触发。

#### NavigateToString 

启动作为新文档的源 HTML 的 htmlContent 导航。

> 公共 void [NavigateToString](#navigatetostring)（string htmlContent）

HtmlContent 参数不能大于 2 MB 的字符。 新页面的来源将显示为 "空白"。

#### OpenDevToolsWindow 

在 Web 视图中打开当前文档的 DevTools 窗口。

> 公共 void [OpenDevToolsWindow](#opendevtoolswindow)（）

如果在 DevTools 窗口已打开时调用，则不执行任何操作。

#### PostWebMessageAsJson 

将指定的 webMessage 发布到此 Web 视图中的顶级文档。

> 公共 void [PostWebMessageAsJson](#postwebmessageasjson)（string webMessageAsJson）

将激发顶级文档的 "chrome" 消息事件。 该文档中的 JavaScript 可以通过以下方式订阅和取消订阅该事件：

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

事件参数是的实例 `MessageEvent` 。 CoreWebView2Settings IsWebMessageEnabled 设置必须为 true，否则此方法将失败，并 E_INVALIDARG。 事件参数的数据属性是将其作为 JSON 字符串分析到 JavaScript 对象中的 webMessage 字符串参数。 事件 arg 的 source 属性是对该对象的引用 `window.chrome.webview` 。 有关从 web 视图中的 HTML 文档发送邮件到主机的信息，请参阅 SetWebMessageReceivedEventHandler。 此消息将异步发送。 如果在将邮件发布到页面之前发生导航，则不会发送邮件。

#### PostWebMessageAsString 

这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。

> 公共 void [PostWebMessageAsString](#postwebmessageasstring)（string webMessageAsString）

此行为与 PostWebMessageAsJson 完全相同，但 `window.chrome.webview` 消息事件参数的 data 属性将是与 webMessageAsString 具有相同值的字符串。 如果想要通过简单的字符串而不是 JSON 对象进行通信，请使用此操作，而不是 PostWebMessageAsJson。

#### 重载 

重新加载当前页面。

> public void [Reload](#reload)（）

这类似于导航到当前顶级文档的 URI，包括触发和遵从 HTTP 缓存中任何条目的所有导航事件。 但是，将不会修改后退/前进历史记录。

#### RemoveHostObjectFromScript 

删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。

> 公共 void [RemoveHostObjectFromScript](#removehostobjectfromscript)（字符串名称）

当新的访问尝试将被拒绝时，如果 Web 视图中的 JavaScript 代码已获得该对象，则 JavaScript 代码将继续具有对该对象的访问权限。 为已删除或从未添加的名称调用此方法将失败。

#### RemoveScriptToExecuteOnDocumentCreated 

删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。

> 公共 void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)（字符串 id）

#### RemoveWebResourceRequestedFilter 

删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。

> 公共 void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)（string Uri， [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) ResourceContext）

如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。 返回从未添加的筛选器 E_INVALIDARG。

#### 停止 

停止所有导航和挂起的资源提取。

> public void [Stop](#stop)（）

不会停止脚本。

