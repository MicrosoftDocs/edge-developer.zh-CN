---
description: 线程模型
title: 线程模型|WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 9a7ce3d66e53b832d4430afb153e6539d97e5db7
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535606"
---
# <a name="threading-model"></a>线程模型 

:::row:::
   :::column span="1":::
      支持的平台：
   :::column-end:::
   :::column span="2":::
      Win32、Windows Forms、WinUi、WPF
   :::column-end:::
:::row-end:::  

WebView2 控件基于组件对象模型 [ (COM) ][WindowsWin32ComTheComponentObjectModel] 并且必须在单个线程的 Sta (STA [) ][WindowsWin32ComSingleThreadedApartments] 上运行。  

## <a name="thread-safety"></a>线程安全  

必须在 UI 线程上创建 WebView2。  具体来说，是具有消息等待的线程。  所有回调都发生在该线程上，并且必须在该线程上完成对 WebView2 的请求。  从另一个线程使用 WebView2 不安全。  

唯一的例外是 `Content` 属性 `CoreWebView2WebResourceRequest` 。  从 `Content` 后台线程读取属性流。  该流应为敏捷流，或从后台 STA 创建，以防止性能下降至 UI 线程。  

## <a name="re-entrancy"></a>重新entrancy  

包括事件处理程序和完成处理程序的回调将串行运行。  
运行事件处理程序并开始消息循环后，将无法以重新进入的方式运行任何事件处理程序或完成回调。  

## <a name="deferrals"></a>Deferrals  

某些 WebView2 事件读取相关事件参数上设置的值，或在事件处理程序完成后启动一些操作。  如果还需要运行异步操作（如事件处理程序），请对关联事件的事件参数 `GetDeferral` 使用 方法。  返回的对象可确保在请求 的 方法之前不会认为事件 `Deferral` `Complete` `Deferral` 处理程序已完成。  

例如，可以使用 事件在事件处理程序完成时提供 作为子 `NewWindowRequested` `CoreWebView2` 窗口进行连接的 。  但是，如果你需要异步创建 ，请对 请求 `CoreWebView2` `GetDeferral` 方法 `NewWindowRequestedEventArgs` 。  在 上异步创建 和 设置 属性后，使用 方法返回 对象 `CoreWebView2` `NewWindow` 上的 `NewWindowRequestedEventArgs` `Complete` `Deferral` `GetDeferral` 请求。  

## <a name="block-the-ui-thread"></a>阻止 UI 线程  

WebView2 依赖 UI 线程的消息线索来运行事件处理程序回调和异步方法完成回调。  如果使用阻止消息接收的方法（如 或 ），则 WebView2 事件处理程序和异步方法完成处理程序 `Task.Result` `WaitForSingleObject` 不会运行。  例如，以下代码无法完成，因为邮件在等待完成时 `Task.Result` 停止消息 `ExecuteScriptAsync` 等待。  由于邮件的发送被阻止， `ExecuteScriptAsync` 无法完成。   

```csharp
private void Button_Click(object sender, EventArgs e)
{
    string result = webView2Control.CoreWebView2.ExecuteScriptAsync("'test'").Result;
    MessageBox.Show(this, result, "Script Result");
}
```  

使用和 `await` 等异步 `async` `await` 机制，该机制不会阻止消息的显示或 UI 线程。  

```csharp
private async void Button_Click(object sender, EventArgs e)
{
    string result = await webView2Control.CoreWebView2.ExecuteScriptAsync("'test'");
    MessageBox.Show(this, result, "Script Result");
}
```  

## <a name="see-also"></a>另请参阅  

*   若要开始使用 WebView2，请导航到 ["WebView2 入门指南"][Webview2IndexGetStarted] 指南。  
*   有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。  
*   有关 WebView2 API 的更多详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WpfWebview2]。  
*   有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 Microsoft Edge WebView 团队联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGetStarted]: ../index.md#get-started "入门 - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  

[WindowsWin32ComSingleThreadedApartments]: /windows/win32/com/single-threaded-apartments "单线程处理|Microsoft Docs"  
[WindowsWin32ComTheComponentObjectModel]: /windows/win32/com/the-component-object-model "组件对象模型|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
