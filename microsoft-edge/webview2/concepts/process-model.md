---
description: 进程模型
title: 过程模型|WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 95d0c53219114c47a781317ab4b2ee2028fc586f
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535613"
---
# <a name="process-model"></a>进程模型  

:::row:::
   :::column span="1":::
      支持的平台：
   :::column-end:::
   :::column span="2":::
      Win32、Windows Forms、WinUi、WPF
   :::column-end:::
:::row-end:::  

WebView2 使用与 Microsoft Edge 浏览器相同的进程模型。  有关浏览器进程模型详细信息，请导航到"浏览器体系结构[- 内部查看新式 Web 浏览器"。][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]  

一个浏览器进程与呈现器进程和其他实用程序进程关联，如本文中所述。  此外，如果指定了 WebView2，主机应用请求进程将使用 WebView2。  

:::image type="complex" source="../media/process-model-1.png" alt-text="进程 1" lightbox="../media/process-model-1.png":::
   进程 1  
:::image-end:::    

浏览器进程仅与一个用户数据文件夹相关联。  请求进程可以指定多个用户数据文件夹。  指定多个用户数据文件夹的请求进程与相同数量的浏览器进程关联。  
例如，请求访问两个用户数据文件夹的请求进程使用两个浏览器进程。  

:::image type="complex" source="../media/process-model-2.png" alt-text="过程 2" lightbox="../media/process-model-2.png":::
   过程 2  
:::image-end:::    

浏览器进程与多个呈现器进程关联。  WebView 2 实例创建一个浏览器进程来为框架提供服务。  浏览器进程可能与多个帧关联。  浏览器进程可能与 WebView2 的不同实例相关联。  呈现进程数因以下条件而异。  

*   在浏览器中使用网站隔离功能。  
*   在关联的 WebView2 实例中呈现的已断开连接源的数量。  
    
网站隔离浏览器功能在上一内容中进行了介绍。 
<!--todo:  which previous content?  -->  

`CoreWebView2Environment`表示用户数据文件夹和浏览器进程。  不直接对应于任何一组进程，因为 WebView2 使用各种呈现器进程，具体取决于前面所述的 `CoreWebView2` 网站隔离。  

若要对浏览器和呈现器进程中的崩溃和挂起做出反应，请使用 `ProcessFailed` 的 事件 `CoreWebView2` 。  

若要安全关闭关联的浏览器和呈现器进程，请使用 的 `Close` `CoreWebView2Controller` 方法。  

若要从 WebView2 实例的 **DevTools** 窗口打开浏览器任务管理器窗口，请完成以下操作。  

*   选择 `Shift`+`Escape`。  
*   将鼠标悬停在 DevTools 窗口标题栏上，打开上下文菜单 \ (右键单击\) ，然后选择 `Browser task manager` 。  
    
将显示与 WebView2 的浏览器进程关联的所有进程，包括关联目的。  

## <a name="see-also"></a>另请参阅  

*   若要开始使用 WebView2，请导航到 [WebView2 入门指南][Webview2IndexGetStarted] 。  
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

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "浏览器体系结构 - 内部查看新式 Web 浏览器 (第 1 部分) "  
