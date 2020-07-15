---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WinForms WebView2 的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、WebView2、浏览器控件、边缘 html、winforms。 WebView2。
ms.openlocfilehash: 7d707c2a6ecb8127074735f06ba6d4f1f28eea0c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879448"
---
# WinForms 类 WebView2 WebView2 

命名空间： WebView2 \ WinForms \
程序集： Microsoft.Web.WebView2.WinForms.dll

```
class Microsoft.Web.WebView2.WinForms.WebView2
  : public Control
```

用于在 WinForms 中嵌入 WebView2 的控件。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[ContentLoading](#contentloading) | 导航开始到新 URI 并开始呈现该 URI 的内容后，ContentLoading 调度。
[CoreWebView2Ready](#corewebview2ready) | 当控件的[CoreWebView2](#corewebview2)已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。
[NavigationCompleted](#navigationcompleted) | 在顶级文档导航完成后，NavigationCompleted 派单已成功呈现。
[NavigationStarting](#navigationstarting) | 新导航开始前一级文档的 NavigationStarting 调度 WebView2。
[SourceChanged](#sourcechanged) | 源属性更改后的 SourceChanged 调度。
[WebMessageReceived](#webmessagereceived) | WebMessageReceived web 内容向应用主机发送一条消息至应用主机后的调度 `chrome.webview.postMessage` 。
[CoreWebView2](#corewebview2) | 基础 CoreWebView2。
[来源](#source) | Source 属性是 WebView2 的顶级文档的 URI。
[ZoomFactor](#zoomfactor) | Web 视图的缩放系数。
[CanGoBack](#cangoback) | 如果 web 视图可以通过 GoBack 方法导航到导航历史记录中的上一页，则返回 true。
[CanGoForward](#cangoforward) | 如果 web 视图可通过 GoForward 方法导航到导航历史记录中的下一页，则返回 true。
[EnsureCoreWebView2Async](#ensurecorewebview2async) | 显式触发控件的[CoreWebView2](#corewebview2)的初始化。
[ExecuteScriptAsync](#executescriptasync) | 在 WebView2 的顶级文档中执行提供的脚本。
[GoBack](#goback) | 导航到导航历史记录中的上一页。
[GoForward](#goforward) | 导航到导航历史记录中的下一页。
[NavigateToString](#navigatetostring) | 将所提供的 HTML 呈现为 WebView2 的顶层文档。
[重载](#reload) | 重新加载 WebView2 的顶层文档。
[停止](#stop) | 停止 WebView2 中的任何正在进行的导航。
[WebView2](#webview2) | 创建新的 WebView2 WinForms 控件。

## 成员

#### ContentLoading 

导航开始到新 URI 并开始呈现该 URI 的内容后，ContentLoading 调度。

> 公共事件 EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)

这等效于 CoreWebView2 上的 ContentLoading 事件。 有关详细信息，请参阅 CoreWebView2 文档。

#### CoreWebView2Ready 

当控件的[CoreWebView2](#corewebview2)已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。

> 公共事件 EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)

如果你需要在要影响其所有使用情况的 CoreWebView2 上执行一次设置操作（例如，添加事件处理程序、配置设置、安装文档创建脚本、添加主机对象），你应该处理此事件。

此事件不提供任何参数，并且发件人将成为 WebView2 控件，它的 CoreWebView2 属性将在首次有效（即非 null）。

#### NavigationCompleted 

在顶级文档导航完成后，NavigationCompleted 派单已成功呈现。

> 公共事件 EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)

这等效于 CoreWebView2 上的 NavigationCompleted 事件。 有关详细信息，请参阅 CoreWebView2 文档。

#### NavigationStarting 

新导航开始前一级文档的 NavigationStarting 调度 WebView2。

> 公共事件 EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)

这等效于 CoreWebView2 上的 NavigationStarting 事件。 有关详细信息，请参阅 CoreWebView2 文档。

#### SourceChanged 

源属性更改后的 SourceChanged 调度。

> 公共事件 EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)

这可能会在导航期间发生，或者如果页面中的脚本更改了文档的 URI，则可能会发生这种情况。 这等效于 CoreWebView2 上的 SourceChanged 事件。 有关详细信息，请参阅 CoreWebView2 文档。

#### WebMessageReceived 

WebMessageReceived web 内容向应用主机发送一条消息至应用主机后的调度 `chrome.webview.postMessage` 。

> 公共事件 EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)

这等效于 CoreWebView2 上的 WebMessageReceived 事件。 有关详细信息，请参阅 CoreWebView2 文档。

#### CoreWebView2 

基础 CoreWebView2。

> 公共 CoreWebView2 [CoreWebView2](#corewebview2)

使用此属性对 WebView2 内容执行比在 WebView2 上公开的更多操作。 此值为 null，直到初始化。 你可以强制基础 CoreWebView2 通过 InitializeAsync 方法进行初始化。

#### 来源 

Source 属性是 WebView2 的顶级文档的 URI。

> 公共 Uri[源](#source)

设置源等效于调用 CoreWebView2。 如果基础 CoreWebView2 尚未初始化，则此属性为 "关于：空白"。 如果属性设置为非绝对 URI 或 null，则属性保持不变。 有关详细信息，请参阅 CoreWebView2 文档。

#### ZoomFactor 

Web 视图的缩放系数。

> 公共双[ZoomFactor](#zoomfactor)

#### CanGoBack 

如果 web 视图可以通过 GoBack 方法导航到导航历史记录中的上一页，则返回 true。

> 公共 bool [CanGoBack](#cangoback)

这等效于 CoreWebView2 上的 CanGoBack 属性。 如果基础 CoreWebView2 尚未初始化，则此属性为 false。 有关详细信息，请参阅 CoreWebView2 文档。

#### CanGoForward 

如果 web 视图可通过 GoForward 方法导航到导航历史记录中的下一页，则返回 true。

> 公共 bool [CanGoForward](#cangoforward)

这等效于 CoreWebView2 上的 CanGoForward 属性。 如果基础 CoreWebView2 尚未初始化，则此属性为 false。 有关详细信息，请参阅 CoreWebView2 文档。

#### EnsureCoreWebView2Async 

显式触发控件的[CoreWebView2](#corewebview2)的初始化。

> 公共任务[EnsureCoreWebView2Async](#ensurecorewebview2async)（CoreWebView2Environment 环境）

##### 参数
* `environment` 应用于创建 CoreWebView2 的预创建的 CoreWebView2Environment。 创建自己的环境使你可以控制影响 CoreWebView2 初始化方式的多个选项。 如果传递 null （默认值），则将自动创建并使用默认环境。 

##### 返回
表示后台初始化进程的任务。 任务完成后，CoreWebView2 属性将可供使用（即非 null）。 请注意，将在任务完成之前调用控件的[CoreWebView2Ready](#corewebview2ready)事件。 

额外调用此方法将不起作用（忽略任何指定的环境），并返回与第一次调用相同的任务。 通过设置[Source](#source)属性隐式触发初始化后调用此方法将不起作用（忽略任何指定的环境），而只是返回表示已在进行的初始化的任务。 

##### 异常
* `System.InvalidOperationException` 从非 UI 线程调用时引发。

#### ExecuteScriptAsync 

在 WebView2 的顶级文档中执行提供的脚本。

> 公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串脚本）

这等效于 CoreWebView2 上的 ExecuteScriptAsync 方法。 如果基础 CoreWebView2 尚未初始化，此方法将引发 InvalidOperationException。 有关详细信息，请参阅 CoreWebView2.ExecuteScriptAsync 文档。

#### GoBack 

导航到导航历史记录中的上一页。

> 公共 void [GoBack](#goback)（）

这等效于 CoreWebView2 上的 GoBack 方法。 如果基础 CoreWebView2 尚未初始化，此方法将不执行任何操作。 有关详细信息，请参阅 CoreWebView2 文档。

#### GoForward 

导航到导航历史记录中的下一页。

> 公共 void [GoForward](#goforward)（）

这等效于 CoreWebView2 上的 GoForward 方法。 如果基础 CoreWebView2 尚未初始化，此方法将不执行任何操作。 有关详细信息，请参阅 CoreWebView2 文档。

#### NavigateToString 

将所提供的 HTML 呈现为 WebView2 的顶层文档。

> 公共 void [NavigateToString](#navigatetostring)（string htmlContent）

这等效于 CoreWebView2 上的 NavigateToString 方法。 如果基础 CoreWebView2 尚未初始化，此方法将引发 InvalidOperationException。 有关详细信息，请参阅 CoreWebView2 文档。

#### 重载 

重新加载 WebView2 的顶层文档。

> public void [Reload](#reload)（）

这等效于 CoreWebView2 上的 Reload 方法。 如果基础 CoreWebView2 尚未初始化，此方法将引发 InvalidOperationException。 有关详细信息，请参阅 CoreWebView2 文档。

#### 停止 

停止 WebView2 中的任何正在进行的导航。

> public void [Stop](#stop)（）

这等效于 CoreWebView2 上的 Stop 方法。 如果基础 CoreWebView2 尚未初始化，此方法将不执行任何操作。 有关详细信息，请参阅 CoreWebView2 文档。

#### WebView2 

创建新的 WebView2 WinForms 控件。

> 公共[WebView2](#webview2)（）

构造后，CoreWebView2 属性为 null。 调用[EnsureCoreWebView2Async](#ensurecorewebview2async)以初始化基础 CoreWebView2。

