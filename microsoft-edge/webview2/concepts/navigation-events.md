---
description: 导航
title: 导航|WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: d133bfb99808d0e036c4b46be9ef82039aee49eb
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535704"
---
# <a name="navigation-events"></a>导航事件  

:::row:::
   :::column span="1":::
      支持的平台：
   :::column-end:::
   :::column span="2":::
      Win32、Windows Forms、WinUi、WPF
   :::column-end:::
:::row-end:::  

导航事件在 WebView2 实例中显示的内容发生特定异步操作时运行。  例如，当 WebView2 用户导航到新网站时，本机内容会使用 事件侦听 `NavigationStarting` 更改。  导航操作完成后，运行 `NavigationCompleted` 。  有关导航事件的良好示例，请导航到 [WebView2 入门指南][Webview2IndexGetStarted]。  

<!--todo:  Move the relevant information out of the get started guide to better focus the content and leave the most concise elements in the get started guide.  -->   

导航事件的正常顺序为 `NavigationStarting` `SourceChanged` 、、、 `ContentLoading` `HistoryChanged` 和 `NavigationCompleted` 。  以下事件描述每次导航期间 WebView2 的状态。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 导航事件" lightbox="../media/navigation-graph.png":::
         Microsoft Edge WebView2 导航事件  
      :::image-end:::  
      
      > [!NOTE]
      > 该图表示导航事件，这些事件 `NavigationId` 在各自的 event 参数上具有相同的属性。  
   :::column-end:::
   :::column span="2":::
      | Sequence | 事件名称 | 详细信息 |  
      |:--- |:--- |:--- |  
      | 1 | `NavigationStarting`  |  WebView2 开始导航，导航结果为网络请求。  在事件期间，主机可能会禁止该请求。  |  
      | 2 | `SourceChanged`  |  WebView2 的源将更改到新的 URL。  该事件可能由不会导致网络请求（如片段导航）的导航操作导致。  |  
      | 3 | `ContentLoading`  |  WebView 开始加载新页面的内容。  |  
      | 4 | `HistoryChanged`  |  导航导致 WebView2 的历史记录更新。  |  
      | 5 | `NavigationCompleted`  |  WebView2 完成新页面上的内容加载。  |  
   :::column-end:::
:::row-end:::

使用导航 ID \ (`NavigationId` event\) 跟踪每个新文档的导航事件。  每次 `NavigationId` 成功导航到新文档时，WebView 事件都会更改。  

 具有不同事件实例的 `NavigationId` 导航事件可能会重叠。  例如，启动导航事件时，必须等待相关 `NavigationStarting` 事件。  如果随后启动另一个导航，则应该会看到第一个导航的事件，后跟第二个导航的事件，然后是第一个导航的事件，然后是第二个导航的所有其他相应导航事件。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`  
 
 在错误情况下，根据导航是否继续导航到错误页面，可能（也可能没有 `ContentLoading` ）事件。  
 
 如果 HTTP 重定向发生，则一行中有多个事件，其中更高版本的事件参数设置了属性，但是 `NavigationStarting` `IsRedirect` `NavigationId` 该事件保持不变。  
 
 相同的文档导航事件（如导航到片段）不会导致事件， `NavigationStarting` 并且不会增加 `NavigationId` 事件。  

若要监视或取消 WebView2 实例中的子框架内的导航事件，请使用 和 事件，这些事件与等效的非 `FrameNavigationStarting` `FrameNavigationCompleted` 帧对应事件类似。  

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

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
