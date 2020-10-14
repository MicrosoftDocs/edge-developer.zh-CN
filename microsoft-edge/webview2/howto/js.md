---
description: 了解如何在 WebView2 应用中的复杂方案中使用 JavaScript
title: 在 WebView2 应用中使用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/12/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 5312cf6209e81a1bbcfa33f324e9b8e7ef099cec
ms.sourcegitcommit: aec8d3482465dfb9a4f5f61c5eded1ff6f66d71d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117694"
---
# 在 Web 视图中将 JavaScript 用于扩展方案  

通过在 WebView2 控件中使用 JavaScript，你可以自定义本机应用以满足你的需求。  本文介绍如何在 WebView2 中使用 JavaScript，并介绍如何使用高级 WebView2 功能和功能进行开发。  

## 开始之前  

本文假定你已有一个正在工作的项目。  如果您没有项目并想要跟踪，请导航到 [WebView2 入门指南][Webview2GettingstartedWpf]。  

## 基本 WebView2 函数  

使用以下函数开始在 Web 视图应用中嵌入 JavaScript。  

| API  | 描述  |
|:--- |:--- |  
| [ExecuteScriptAsync][Webview2ReferenceWpf09515MicrosoftWebExecutescriptasync] | 在 Web 视图控件中运行 JavaScript。 有关详细信息，请导航到入门教程。 |
| [OnDocumentCreatedAsync][Webview2ReferenceWin3209538Icorewebview2Addscripttoexecuteondocumentcreated] | 在创建文档对象模型 \ (DOM \ ) 时运行。 |
      
## 方案：运行专用脚本文件  

在此部分中，从 WebView2 控件访问专用的 JavaScript 文件。  

> [!NOTE]
> 虽然嵌入式 JavaScript 的编写对于快速的 JavaScript 命令而言可能很有效，但你将丢失 JavaScript 颜色主题和行格式，这使在 Visual Studio 中编写大型代码段很困难。  

若要解决此问题，请使用你的代码创建一个单独的 JavaScript 文件，然后使用参数传递对该文件的引用 `ExecuteScriptAsync` 。  

1.  `.js`在项目中创建一个文件，然后添加要运行的 JavaScript 代码。  例如，创建一个名为 `script.js` 的文件。  
1.  将 JavaScript 文件转换为传递到的字符串 `ExecuteScriptAsync` 。  
    1.  若要将 JavaScript 文件转换为字符串，请复制以下代码片段。  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  将代码粘贴到 `MainWindow.xaml.cs` 。  
1.  使用传递文本变量 `ExecuteScriptAsync` 。  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## 方案：删除拖放功能  

在此部分中，使用 JavaScript 从 WebView2 控件中删除拖放功能。  

首先，浏览当前的拖放功能。  

1.  创建一个 `.txt` 文件，以便进行拖放。  例如，创建一个名为的文件 `contoso.txt` 并向其中添加文本。  
1.  运行你的项目。  
1.  将文件拖放 `contoso.txt` 到 Web 视图控件上。  将打开一个新窗口，这是你的示例项目中的代码的结果。  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="拖放 contoso.txt 的结果" lightbox="./media/dragtext.png":::
       拖放 contoso.txt 的结果  
    :::image-end:::  

现在，添加代码以从 WebView2 控件中删除拖放功能。  

1.  将以下代码段复制并粘贴到 `InitializeAsync()` 其中 `MainWindow.xaml.cs` 。   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  运行你的项目。  
1.  尝试拖放 `contoso.txt` 。  确认您不能拖放。  

## 方案：删除上下文菜单  

在此部分中，从 WebView2 控件中删除默认上下文菜单。  

首先，浏览当前上下文菜单功能。  

1.  运行你的项目。  
1.  将鼠标悬停在 WebView2 控件上的任意位置并打开上下文菜单 \ (右键单击 \ ) 。  上下文菜单显示默认选项。  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="拖放 contoso.txt 的结果" lightbox="./media/contextmenu.png":::
       显示默认选项的上下文菜单  
    :::image-end:::  
    
现在添加代码以从 WebView2 控件中删除上下文菜单功能。  

1.  将以下代码段复制并粘贴到 `InitializeAsync()` 其中 `MainWindow.xaml.cs` 。    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  再次运行代码。  确认无法打开上下文菜单 \ (右键单击 \ ) 。  
   
## 另请参阅  

*   有关如何开始使用 WebView2 的详细信息，请导航到 [WebView2 入门指南][Webview2MainGettingStarted]。  
*   有关 WebView2 功能的完整示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。  
*   有关 WebView2 Api 的详细信息，请导航到 [API 参考][Webview2ApiReference]。  
*   有关 WebView2 的详细信息，请导航到 " [WebView2 资源][Webview2MainNextSteps]"。  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  


[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft 文档"  
[Webview2GettingstartedWpf]: ../gettingstarted/wpf.md "WPF 中的 WebView2 入门 (预览版) |Microsoft 文档"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门-Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  
[Webview2MainNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webview2ReferenceWin3209538Icorewebview2Addscripttoexecuteondocumentcreated]: ../reference/win32/0-9-538/icorewebview2.md#addscripttoexecuteondocumentcreated "AddScriptToExecuteOnDocumentCreated-0.9.579-interface ICoreWebView2 |Microsoft 文档"  
[Webview2ReferenceWpf09515MicrosoftWebExecutescriptasync]: ../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync "ExecuteScriptAsync-WebView2 | WebView2 类 |Microsoft 文档"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  
