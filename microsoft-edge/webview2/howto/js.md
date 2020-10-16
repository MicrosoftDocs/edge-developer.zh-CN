---
description: 了解如何在 WebView2 应用中的复杂方案中使用 JavaScript
title: 在 WebView2 应用中使用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/15/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 0fd4e33b7cfc16dcd19a850147b6efbca8922a8e
ms.sourcegitcommit: 442de63da52d00c6dc27fa08ccdb736534127566
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120066"
---
# <span data-ttu-id="ce69a-104">在 Web 视图中将 JavaScript 用于扩展方案</span><span class="sxs-lookup"><span data-stu-id="ce69a-104">Use JavaScript in WebView for extended scenarios</span></span>  

<span data-ttu-id="ce69a-105">通过在 WebView2 控件中使用 JavaScript，你可以自定义本机应用以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="ce69a-105">Using JavaScript in WebView2 controls allows you to customize native apps to meet your requirements.</span></span>  <span data-ttu-id="ce69a-106">本文介绍如何在 WebView2 中使用 JavaScript，并介绍如何使用高级 WebView2 功能和功能进行开发。</span><span class="sxs-lookup"><span data-stu-id="ce69a-106">This article explores how to use JavaScript in WebView2, and reviews how to develop using advanced WebView2 features and functionality.</span></span>  

## <span data-ttu-id="ce69a-107">开始之前</span><span class="sxs-lookup"><span data-stu-id="ce69a-107">Before you begin</span></span>  

<span data-ttu-id="ce69a-108">本文假定你已有一个正在工作的项目。</span><span class="sxs-lookup"><span data-stu-id="ce69a-108">This article assumes that you already have a working project.</span></span>  <span data-ttu-id="ce69a-109">如果您没有项目并想要跟踪，请导航到 [WebView2 入门指南][Webview2GettingstartedWpf]。</span><span class="sxs-lookup"><span data-stu-id="ce69a-109">If you do not have a project and want to follow along, navigate to the [WebView2 Getting Started Guide][Webview2GettingstartedWpf].</span></span>  

## <span data-ttu-id="ce69a-110">基本 WebView2 函数</span><span class="sxs-lookup"><span data-stu-id="ce69a-110">Basic WebView2 Functions</span></span>  

<span data-ttu-id="ce69a-111">使用以下函数开始在 Web 视图应用中嵌入 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="ce69a-111">Use the following functions to begin embedding JavaScript in your WebView app.</span></span>  

| <span data-ttu-id="ce69a-112">API</span><span class="sxs-lookup"><span data-stu-id="ce69a-112">API</span></span>  | <span data-ttu-id="ce69a-113">描述</span><span class="sxs-lookup"><span data-stu-id="ce69a-113">Description</span></span>  |
|:--- |:--- |  
| [<span data-ttu-id="ce69a-114">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="ce69a-114">ExecuteScriptAsync</span></span>][Webview2ReferenceWpfMicrosoftWebExecutescriptasync] | <span data-ttu-id="ce69a-115">在 Web 视图控件中运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="ce69a-115">Run JavaScript in a WebView control.</span></span> <span data-ttu-id="ce69a-116">有关详细信息，请导航到入门教程。</span><span class="sxs-lookup"><span data-stu-id="ce69a-116">For more information, navigate to the Getting Started tutorial.</span></span> |
| [<span data-ttu-id="ce69a-117">OnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="ce69a-117">OnDocumentCreatedAsync</span></span>][Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated] | <span data-ttu-id="ce69a-118">在创建文档对象模型 \ (DOM \ ) 时运行。</span><span class="sxs-lookup"><span data-stu-id="ce69a-118">Runs when the Document Object Model \(DOM\) is created.</span></span> |
      
## <span data-ttu-id="ce69a-119">方案：运行专用脚本文件</span><span class="sxs-lookup"><span data-stu-id="ce69a-119">Scenario:  Running a dedicated script file</span></span>  

<span data-ttu-id="ce69a-120">在此部分中，从 WebView2 控件访问专用的 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="ce69a-120">In this section, access a dedicated JavaScript file from your WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="ce69a-121">虽然嵌入式 JavaScript 的编写对于快速的 JavaScript 命令而言可能很有效，但你将丢失 JavaScript 颜色主题和行格式，这使在 Visual Studio 中编写大型代码段很困难。</span><span class="sxs-lookup"><span data-stu-id="ce69a-121">Although writing JavaScript inline may be efficient for quick JavaScript commands, you lose JavaScript color themes and line formatting that makes it difficult to write large sections of code in Visual Studio.</span></span>  

<span data-ttu-id="ce69a-122">若要解决此问题，请使用你的代码创建一个单独的 JavaScript 文件，然后使用参数传递对该文件的引用 `ExecuteScriptAsync` 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-122">To solve the problem, create a separate JavaScript file with your code, and then pass a reference to that file using the `ExecuteScriptAsync` parameters.</span></span>  

1.  <span data-ttu-id="ce69a-123">`.js`在项目中创建一个文件，然后添加要运行的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="ce69a-123">Create a `.js` file in your project, and add the JavaScript code that you want to run.</span></span>  <span data-ttu-id="ce69a-124">例如，创建一个名为 `script.js` 的文件。</span><span class="sxs-lookup"><span data-stu-id="ce69a-124">For example, create a file called `script.js`.</span></span>  
1.  <span data-ttu-id="ce69a-125">将 JavaScript 文件转换为传递到的字符串 `ExecuteScriptAsync` 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-125">Convert the JavaScript file to a string that is passed to `ExecuteScriptAsync`.</span></span>  
    1.  <span data-ttu-id="ce69a-126">若要将 JavaScript 文件转换为字符串，请复制以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="ce69a-126">To convert your JavaScript file into a string, copy the following code snippet.</span></span>  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  <span data-ttu-id="ce69a-127">将代码粘贴到 `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-127">Paste the code into `MainWindow.xaml.cs`.</span></span>  
1.  <span data-ttu-id="ce69a-128">使用传递文本变量 `ExecuteScriptAsync` 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-128">Pass your text variable using `ExecuteScriptAsync`.</span></span>  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## <span data-ttu-id="ce69a-129">方案：删除拖放功能</span><span class="sxs-lookup"><span data-stu-id="ce69a-129">Scenario:  Remove drag-and-drop functionality</span></span>  

<span data-ttu-id="ce69a-130">在此部分中，使用 JavaScript 从 WebView2 控件中删除拖放功能。</span><span class="sxs-lookup"><span data-stu-id="ce69a-130">In this section, use JavaScript to remove the drag-and-drop functionality from your WebView2 control.</span></span>  

<span data-ttu-id="ce69a-131">首先，浏览当前的拖放功能。</span><span class="sxs-lookup"><span data-stu-id="ce69a-131">To begin, explore the current drag-and-drop functionality.</span></span>  

1.  <span data-ttu-id="ce69a-132">创建一个 `.txt` 文件，以便进行拖放。</span><span class="sxs-lookup"><span data-stu-id="ce69a-132">Create a `.txt` file in order to drag-and-drop.</span></span>  <span data-ttu-id="ce69a-133">例如，创建一个名为的文件 `contoso.txt` 并向其中添加文本。</span><span class="sxs-lookup"><span data-stu-id="ce69a-133">For example, create a file named `contoso.txt` and add text to it.</span></span>  
1.  <span data-ttu-id="ce69a-134">运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="ce69a-134">Run your project.</span></span>  
1.  <span data-ttu-id="ce69a-135">将文件拖放 `contoso.txt` 到 Web 视图控件上。</span><span class="sxs-lookup"><span data-stu-id="ce69a-135">Drag-and-drop the `contoso.txt` file onto the WebView control.</span></span>  <span data-ttu-id="ce69a-136">将打开一个新窗口，这是你的示例项目中的代码的结果。</span><span class="sxs-lookup"><span data-stu-id="ce69a-136">A new window opens, which is the result of the code in your sample project.</span></span>  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="拖放 contoso.txt 的结果" lightbox="./media/dragtext.png":::
       <span data-ttu-id="ce69a-138">拖放 contoso.txt 的结果</span><span class="sxs-lookup"><span data-stu-id="ce69a-138">Result of dragging and dropping contoso.txt</span></span>  
    :::image-end:::  

<span data-ttu-id="ce69a-139">现在，添加代码以从 WebView2 控件中删除拖放功能。</span><span class="sxs-lookup"><span data-stu-id="ce69a-139">Now, add code to remove the drag-and-drop functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="ce69a-140">将以下代码段复制并粘贴到 `InitializeAsync()` 其中 `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-140">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  <span data-ttu-id="ce69a-141">运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="ce69a-141">Run your project.</span></span>  
1.  <span data-ttu-id="ce69a-142">尝试拖放 `contoso.txt` 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-142">Try to drag-and-drop `contoso.txt`.</span></span>  <span data-ttu-id="ce69a-143">确认您不能拖放。</span><span class="sxs-lookup"><span data-stu-id="ce69a-143">Confirm that you are not able to drag-and-drop.</span></span>  

## <span data-ttu-id="ce69a-144">方案：删除上下文菜单</span><span class="sxs-lookup"><span data-stu-id="ce69a-144">Scenario:  Removing the Context Menu</span></span>  

<span data-ttu-id="ce69a-145">在此部分中，从 WebView2 控件中删除默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="ce69a-145">In this section, remove the default context menu from your WebView2 control.</span></span>  

<span data-ttu-id="ce69a-146">首先，浏览当前上下文菜单功能。</span><span class="sxs-lookup"><span data-stu-id="ce69a-146">To begin, explore the current contextual menu functionality.</span></span>  

1.  <span data-ttu-id="ce69a-147">运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="ce69a-147">Run your project.</span></span>  
1.  <span data-ttu-id="ce69a-148">将鼠标悬停在 WebView2 控件上的任意位置并打开上下文菜单 \ (右键单击 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-148">Hover anywhere on the WebView2 control and open the context menu \(right-click\).</span></span>  <span data-ttu-id="ce69a-149">上下文菜单显示默认选项。</span><span class="sxs-lookup"><span data-stu-id="ce69a-149">The context menu displays the default choices.</span></span>  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="拖放 contoso.txt 的结果" lightbox="./media/contextmenu.png":::
       <span data-ttu-id="ce69a-151">显示默认选项的上下文菜单</span><span class="sxs-lookup"><span data-stu-id="ce69a-151">The context menu showing the default choices</span></span>  
    :::image-end:::  
    
<span data-ttu-id="ce69a-152">现在添加代码以从 WebView2 控件中删除上下文菜单功能。</span><span class="sxs-lookup"><span data-stu-id="ce69a-152">Now add code to remove the contextual menu functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="ce69a-153">将以下代码段复制并粘贴到 `InitializeAsync()` 其中 `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-153">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  <span data-ttu-id="ce69a-154">再次运行代码。</span><span class="sxs-lookup"><span data-stu-id="ce69a-154">Run the code again.</span></span>  <span data-ttu-id="ce69a-155">确认无法打开上下文菜单 \ (右键单击 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="ce69a-155">Confirm that you're not able to open a context menu \(right-click\).</span></span>  
   
## <span data-ttu-id="ce69a-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce69a-156">See also</span></span>  

*   <span data-ttu-id="ce69a-157">有关如何开始使用 WebView2 的详细信息，请导航到 [WebView2 入门指南][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="ce69a-157">For more information on getting started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="ce69a-158">有关 WebView2 功能的完整示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。</span><span class="sxs-lookup"><span data-stu-id="ce69a-158">For a comprehensive example of WebView2 capabilities, navigate to the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>  
*   <span data-ttu-id="ce69a-159">有关 WebView2 Api 的详细信息，请导航到 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="ce69a-159">For detailed information on WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>  
*   <span data-ttu-id="ce69a-160">有关 WebView2 的详细信息，请导航到 " [WebView2 资源][Webview2MainNextSteps]"。</span><span class="sxs-lookup"><span data-stu-id="ce69a-160">For more information on WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>  

## <span data-ttu-id="ce69a-161">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="ce69a-161">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  


[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft 文档"  
[Webview2GettingstartedWpf]: ../gettingstarted/wpf.md "WPF 中的 WebView2 入门 (预览版) |Microsoft 文档"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门-Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  
[Webview2MainNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated]: /microsoft-edge/webview2/reference/win32/icorewebview2#addscripttoexecuteondocumentcreated "AddScriptToExecuteOnDocumentCreated-0.9.579-interface ICoreWebView2 |Microsoft 文档"  
[Webview2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法 (WebView2) |Microsoft 文档"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  
