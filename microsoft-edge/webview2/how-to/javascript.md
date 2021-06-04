---
description: 了解如何在 WebView2 应用中的复杂方案中使用 JavaScript
title: 在 WebView2 应用中使用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8db5c4a5b3709c144240fe88e6f8480445c1659f
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535822"
---
# <a name="use-javascript-in-webview-for-extended-scenarios"></a>在 WebView 中对扩展方案使用 JavaScript  

使用 WebView2 控件中的 JavaScript，可以自定义本机应用以满足你的要求。  本文探讨如何在 WebView2 中使用 JavaScript，并回顾如何使用高级 WebView2 特性和功能进行开发。  

## <a name="before-you-begin"></a>开始之前  

本文假定您已有一个工作项目。  如果你没有项目，并且想要继续操作，请导航到 [WebView2 入门指南][Webview2GetStartedWpf]。  

## <a name="basic-webview2-functions"></a>基本 WebView2 函数  

使用以下函数开始在 WebView 应用中嵌入 JavaScript。  

| API  | 说明  |
|:--- |:--- |  
| [ExecuteScriptAsync][Webview2ReferenceWpfMicrosoftWebExecutescriptasync] | 在 WebView 控件中运行 JavaScript。 有关详细信息，请导航到入门教程。 |
| [OnDocumentCreatedAsync][Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated] | 创建文档对象模型 \(DOM\) 时运行。 |
      
## <a name="scenario--running-a-dedicated-script-file"></a>方案：运行专用脚本文件  

在此部分中，从 WebView2 控件访问专用的 JavaScript 文件。  

> [!NOTE]
> 虽然内联编写 JavaScript 对于快速 JavaScript 命令可能非常高效，但会丢失 JavaScript 颜色主题和行格式，这使得在 JavaScript 中编写大量代码Visual Studio。  

若要解决此问题，请用代码创建单独的 JavaScript 文件，然后使用 参数传递对该文件 `ExecuteScriptAsync` 的引用。  

1.  在 `.js` 项目中创建文件，并添加要运行的 JavaScript 代码。  例如，创建一个称为 的文件 `script.js` 。  
1.  将 JavaScript 文件转换为传递给 的字符串 `ExecuteScriptAsync` 。  
    1.  若要将 JavaScript 文件转换为字符串，请复制以下代码段。  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  将代码粘贴到 `MainWindow.xaml.cs` 中。  
1.  使用 传递文本变量 `ExecuteScriptAsync` 。  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  
    
## <a name="scenario--remove-drag-and-drop-functionality"></a>方案：删除拖放功能  

在此部分中，使用 JavaScript 从 WebView2 控件中删除拖放功能。  

首先，探索当前的拖放功能。  

1.  创建 `.txt` 文件以拖放。  例如，创建一个名为 的文件 `contoso.txt` ，并添加文本。  
1.  运行项目。  
1.  将文件拖放到 `contoso.txt` WebView 控件上。  将打开一个新窗口，这是示例项目中代码的结果。  
    
    :::image type="complex" source="./media/drag-text.png" alt-text="拖放操作的结果contoso.txt" lightbox="./media/drag-text.png":::
       拖放操作的结果contoso.txt  
    :::image-end:::  
    
现在，添加代码以从 WebView2 控件中删除拖放功能。  

1.  将以下代码段复制并粘贴到 `InitializeAsync()` 中 `MainWindow.xaml.cs` 。   
    
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
    
1.  运行项目。  
1.  尝试拖放 `contoso.txt` 。  确认无法拖放。  
    
## <a name="scenario--removing-the-context-menu"></a>方案：删除上下文菜单  

在此部分中，从 WebView2 控件中删除默认上下文菜单。  

首先，探索当前上下文菜单功能。  

1.  运行项目。  
1.  将鼠标悬停在 WebView2 控件上的任意位置，然后打开上下文菜单 \(右键单击\) 。  上下文菜单显示默认选项。  
    
    :::image type="complex" source="./media/context-menu.png" alt-text="显示默认选项的上下文菜单" lightbox="./media/context-menu.png":::
       显示默认选项的上下文菜单  
    :::image-end:::  
    
现在，添加代码以从 WebView2 控件中删除上下文菜单功能。  

1.  将以下代码段复制并粘贴到 `InitializeAsync()` 中 `MainWindow.xaml.cs` 。    
    
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  
    
1.  再次运行代码。  确认无法打开上下文菜单 \(右键单击\) 。  
    
## <a name="see-also"></a>另请参阅  

*   若要开始使用 WebView2，请导航到["WebView2 入门指南"。][Webview2MainGetStarted]  
*   有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。  
*   有关 WebView2 API 的详细信息，请导航到 [API 参考][Webview2ApiReference]。  
*   有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2MainNextSteps]  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 Microsoft Edge WebView 团队联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考|Microsoft Docs"  
[Webview2GetStartedWpf]: ../get-started/wpf.md "WPF 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2MainGetStarted]: ../index.md#get-started "入门 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated]: /microsoft-edge/webview2/reference/win32/icorewebview2#addscripttoexecuteondocumentcreated "AddScriptToExecuteOnDocumentCreated - 0.9.579 - 接口 ICoreWebView2 |Microsoft Docs"  

[Webview2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExeMicrosoft.Web.WebView2.Wpf () 方法 (cuteScriptAsync) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
