---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/27/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a0030e1a2a77d65963bd8333f2071485ab2fe308
ms.sourcegitcommit: 83efa259be89cc773a82751242495a0a919d54cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "10687795"
---
# WebView2 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

用于在 WPF 应用程序中嵌入 web 内容的控件。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[ContentLoading](#contentloading) | CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。
[CoreWebView2Ready](#corewebview2ready) | 当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。
[NavigationCompleted](#navigationcompleted) | CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。
[NavigationStarting](#navigationstarting) | CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。
[SourceChanged](#sourcechanged) | CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。
[WebMessageReceived](#webmessagereceived) | CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。
[CanGoBack](#cangoback) | 如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。
[CanGoForward](#cangoforward) | 如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。
[CoreWebView2](#corewebview2) | 访问基础 Core CoreWebView2 COM API 的完整功能。
[CreationProperties](#creationproperties) | 获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。
[来源](#source) | Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。
[EnsureCoreWebView2Async](#ensurecorewebview2async) | 显式触发控件的 CoreWebView2 的初始化。
[ExecuteScriptAsync](#executescriptasync) | 通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。
[GoBack](#goback) | 将 Web 视图导航到导航历史记录中的上一页。
[GoForward](#goforward) | 将 Web 视图导航到导航历史记录中的下一页。
[NavigateToString](#navigatetostring) | 启动作为新文档的源 HTML 的 htmlContent 导航。
[重载](#reload) | 重新加载当前页。
[停止](#stop) | 停止所有导航和挂起的资源读取。
[WebView2](#webview2) | 创建 WebView2 控件的新实例。

此控件实际上是围绕 WebView2 COM API 的包装，你可以在此处找到文档： [https://aka.ms/webview2](https://aka.ms/webview2) 通过访问 CoreWebView2 属性，可以直接访问基础 ICoreWebView2 接口及其所有功能。 某些最常用的 COM 功能也可以通过控件上的包装方法/属性/事件直接访问。

在创建时，该控件的 CoreWebView2 属性将为 null。 这是因为创建 CoreWebView2 是一个昂贵的操作，它涉及启动 Edge 浏览器进程之类的操作。 有两种方法可导致创建 CoreWebView2：1）调用 EnsureCoreWebView2Async 方法。 这称为显式初始化。 2）设置 Source 属性（例如，可以通过标记执行此操作）。 这称为隐式初始化。 这两个选项都将开始在后台初始化，并返回到呼叫方，而无需等待它完成。 若要指定有关初始化过程的选项，请将你自己的 CoreWebView2Environment 传递给 EnsureCoreWebView2Async，或在初始化之前设置控件的 CreationProperties 属性。

初始化完成后（无论其触发方式如何），将按如下顺序发生以下情况：1）将调用控件的 CoreWebView2Ready 事件。 如果你需要在其使用之前对 CoreWebView2 执行一次设置操作，则应在该事件的处理程序中执行此操作。 2）如果 Uri 已设置为 Source 属性，则控件将开始在后台导航到该属性（即，这些步骤将在不等待导航结束的情况下继续）。 3）从 EnsureCoreWebView2Async 返回的任务将完成。

有关初始化过程中涉及的任何方法/属性/事件的更多详细信息，请参阅其特定文档。

由于该控件的 CoreWebView2 是一个非常重量级的对象（有可能负责多个正在运行的进程和 mb 的磁盘空间），因此该控件实现 IDisposable 以提供用于释放它的显式方法。 调用 Dispose 将释放 CoreWebView2 及其基础资源（除其他 WebViews 还在使用的其他资源之外），并将 CoreWebView2 重置为 null。 在 Dispose 调用后，CoreWebView2 无法重新初始化，并且尝试使用需要它的功能将引发 ObjectDisposedException。

请注意，此控件扩展了 HwndHost，以便嵌入实时位于 WPF 生态系统之外的窗口。 这对控件的输入和输出行为以及它从 UIElement 和 FrameworkElement 中 "继承" 的功能有一定的影响。 有关详细信息，请参阅 HwndHost 和 WPF/Win32 互操作文档：

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## 成员

#### ContentLoading 

CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。

> 公共事件 EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)

此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。 此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。

#### CoreWebView2Ready 

当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。

> 公共事件 EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)

如果你需要在要影响其所有使用情况的 CoreWebView2 上执行一次设置操作（例如，添加事件处理程序、配置设置、安装文档创建脚本、添加主机对象），你应该处理此事件。 有关初始化概述，请参阅 WebView2 类文档。

此事件不提供任何参数，并且发件人将成为 WebView2 控件，它的 CoreWebView2 属性将在首次有效（即非 null）。

#### NavigationCompleted 

CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。

> 公共事件 EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)

此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。 此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。

#### NavigationStarting 

CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。

> 公共事件 EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)

此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。 此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。

#### SourceChanged 

CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。

> 公共事件 EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)

此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。 此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。

#### WebMessageReceived 

CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。

> 公共事件 EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)

此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。 此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。

#### CanGoBack 

如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。

> 公共 bool [CanGoBack](#cangoback)

CoreWebView2 的 CanGoBack 属性的 CoreWebView2 包装器。 如果 CoreWebView2 尚未初始化，则返回 false。

#### CanGoForward 

如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。

> 公共 bool [CanGoForward](#cangoforward)

CoreWebView2 的 CanGoForward 属性的 CoreWebView2 包装器。 如果 CoreWebView2 尚未初始化，则返回 false。

#### CoreWebView2 

访问基础 Core CoreWebView2 COM API 的完整功能。

> 公共 CoreWebView2 [CoreWebView2](#corewebview2)

返回 null，直到初始化完成。 有关初始化概述，请参阅 WebView2 类文档。

##### 异常
* `InvalidOperationException` 如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。 有关详细信息，请参阅 DispatcherObject VerifyAccess。

* `ObjectDisposedException` 如果已在该控件上调用 Dispose，则引发该异常。

#### CreationProperties 

获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。

> 公共 CoreWebView2CreationProperties [CreationProperties](#creationproperties)

在已开始控件的 CoreWebView2 初始化后，设置此属性将不起作用（将保留旧值）。 有关初始化概述，请参阅 WebView2 类文档。

#### 来源 

Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。

> 公共 Uri[源](#source)

一般说来，获取此属性等效于获取 CoreWebView2 的 CoreWebView2 属性，并且设置此属性等效于在 CoreWebView2 上调用 CoreWebView2 方法。 在 CoreWebView2 初始化之前获取此属性将检索已设置为其的最后一个 Uri。 在 CoreWebView2 初始化之前设置此属性将导致在后台启动初始化（如果尚未进行），之后，WebView2 将导航到指定的 Uri。 有关初始化概述，请参阅 WebView2 类文档。

##### 异常
* `ObjectDisposedException` 如果已在该控件上调用 Dispose，则引发该异常。

#### EnsureCoreWebView2Async 

显式触发控件的 CoreWebView2 的初始化。

> 公共任务[EnsureCoreWebView2Async](#ensurecorewebview2async)（CoreWebView2Environment 环境）

有关初始化概述，请参阅 WebView2 类文档。

##### 参数
* `environment` 应用于创建 CoreWebView2 的预创建的 CoreWebView2Environment。 创建自己的环境使你可以控制影响 CoreWebView2 初始化方式的多个选项。 如果你将环境传递到此方法，则它将覆盖 CreationProperties 属性上指定的任何设置。 如果传递 null （默认值），并且未将任何值设置为 CreationProperties，则将自动创建和使用默认环境。 

##### 返回
表示后台初始化进程的任务。 任务完成后，CoreWebView2 属性将可供使用（即非 null）。 请注意，将在任务完成之前调用控件的 CoreWebView2Ready 事件。 

额外调用此方法将不起作用（忽略任何指定的环境），并返回与第一次调用相同的任务。 通过设置 Source 属性隐式触发初始化后调用此方法将不起作用（忽略任何指定的环境），而只是返回表示已在进行的初始化的任务。 请注意，即使此方法是异步的并返回任务，它仍必须在 UI 线程上调用，如大多数 UI 控件的大多数公共功能。 

##### 异常
* `InvalidOperationException` 如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。 有关详细信息，请参阅 DispatcherObject VerifyAccess。

* `ObjectDisposedException` 如果已在该控件上调用 Dispose，则引发该异常。

#### ExecuteScriptAsync 

通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。

> 公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串 javaScript）

等同于在 CoreWebView2 上调用 CoreWebView2 ExecuteScriptAsync

##### 异常
* `InvalidOperationException` 如果 CoreWebView2 尚未初始化，则抛出。

* `InvalidOperationException` 如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。 有关详细信息，请参阅 DispatcherObject VerifyAccess。

* `ObjectDisposedException` 如果已在该控件上调用 Dispose，则引发该异常。

#### GoBack 

将 Web 视图导航到导航历史记录中的上一页。

> 公共 void [GoBack](#goback)（）

如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoBack，否则不执行任何操作。

##### 异常
* `InvalidOperationException` 如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。 有关详细信息，请参阅 DispatcherObject VerifyAccess。

* `ObjectDisposedException` 如果已在该控件上调用 Dispose，则引发该异常。

#### GoForward 

将 Web 视图导航到导航历史记录中的下一页。

> 公共 void [GoForward](#goforward)（）

如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoForward，否则不执行任何操作。

##### 异常
* `InvalidOperationException` 如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。 有关详细信息，请参阅 DispatcherObject VerifyAccess。

* `ObjectDisposedException` 如果已在该控件上调用 Dispose，则引发该异常。

#### NavigateToString 

启动作为新文档的源 HTML 的 htmlContent 导航。

> 公共 void [NavigateToString](#navigatetostring)（string htmlContent）

等同于在 CoreWebView2 上调用 CoreWebView2 NavigateToString

##### 异常
* `InvalidOperationException` 如果 CoreWebView2 尚未初始化，则抛出。

<exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。  有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。

#### 重载 

重新加载当前页。

> public void [Reload](#reload)（）

等效于在 CoreWebView2 上调用 CoreWebView2

##### 异常
* `InvalidOperationException` 如果 CoreWebView2 尚未初始化，则抛出。

<exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。  有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。

#### 停止 

停止所有导航和挂起的资源读取。

> public void [Stop](#stop)（）

等同于调用 CoreWebView2。在 CoreWebView2 上停止

##### 异常
* `InvalidOperationException` 如果 CoreWebView2 尚未初始化，则抛出。

<exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。  有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。

#### WebView2 

创建 WebView2 控件的新实例。

> 公共[WebView2](#webview2)（）

请注意，在初始化之前，控件的 CoreWebView2 将为 null。 有关初始化概述，请参阅 WebView2 类文档。

