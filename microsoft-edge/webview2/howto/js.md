---
description: 了解如何在 WebView2 应用中的复杂方案中使用 JavaScript
title: 在 WebView2 应用中使用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: da04d1e24b95dfa7ea477bbd228fd46b64727ec3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230934"
---
# <span data-ttu-id="34849-104">在 WebView 中对扩展方案使用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="34849-104">Use JavaScript in WebView for extended scenarios</span></span>  

<span data-ttu-id="34849-105">使用 WebView2 控件中的 JavaScript，可以自定义本机应用以满足你的要求。</span><span class="sxs-lookup"><span data-stu-id="34849-105">Using JavaScript in WebView2 controls allows you to customize native apps to meet your requirements.</span></span>  <span data-ttu-id="34849-106">本文探讨如何在 WebView2 中使用 JavaScript，并回顾如何使用高级 WebView2 特性和功能进行开发。</span><span class="sxs-lookup"><span data-stu-id="34849-106">This article explores how to use JavaScript in WebView2, and reviews how to develop using advanced WebView2 features and functionality.</span></span>  

## <span data-ttu-id="34849-107">开始之前</span><span class="sxs-lookup"><span data-stu-id="34849-107">Before you begin</span></span>  

<span data-ttu-id="34849-108">本文假定您已有一个工作项目。</span><span class="sxs-lookup"><span data-stu-id="34849-108">This article assumes that you already have a working project.</span></span>  <span data-ttu-id="34849-109">如果你没有项目并且想要跟进，请导航到 [WebView2 入门指南][Webview2GettingstartedWpf]。</span><span class="sxs-lookup"><span data-stu-id="34849-109">If you do not have a project and want to follow along, navigate to the [WebView2 Getting Started Guide][Webview2GettingstartedWpf].</span></span>  

## <span data-ttu-id="34849-110">基本 WebView2 函数</span><span class="sxs-lookup"><span data-stu-id="34849-110">Basic WebView2 Functions</span></span>  

<span data-ttu-id="34849-111">使用以下函数开始在 WebView 应用中嵌入 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="34849-111">Use the following functions to begin embedding JavaScript in your WebView app.</span></span>  

| <span data-ttu-id="34849-112">API</span><span class="sxs-lookup"><span data-stu-id="34849-112">API</span></span>  | <span data-ttu-id="34849-113">描述</span><span class="sxs-lookup"><span data-stu-id="34849-113">Description</span></span>  |
|:--- |:--- |  
| [<span data-ttu-id="34849-114">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="34849-114">ExecuteScriptAsync</span></span>][Webview2ReferenceWpfMicrosoftWebExecutescriptasync] | <span data-ttu-id="34849-115">在 WebView 控件中运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="34849-115">Run JavaScript in a WebView control.</span></span> <span data-ttu-id="34849-116">有关详细信息，请导航到"入门"教程。</span><span class="sxs-lookup"><span data-stu-id="34849-116">For more information, navigate to the Getting Started tutorial.</span></span> |
| [<span data-ttu-id="34849-117">OnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="34849-117">OnDocumentCreatedAsync</span></span>][Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated] | <span data-ttu-id="34849-118">创建文档对象模型 \(DOM\) 时运行。</span><span class="sxs-lookup"><span data-stu-id="34849-118">Runs when the Document Object Model \(DOM\) is created.</span></span> |
      
## <span data-ttu-id="34849-119">方案：运行专用脚本文件</span><span class="sxs-lookup"><span data-stu-id="34849-119">Scenario:  Running a dedicated script file</span></span>  

<span data-ttu-id="34849-120">在此部分中，从 WebView2 控件访问专用的 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="34849-120">In this section, access a dedicated JavaScript file from your WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="34849-121">尽管内联编写 JavaScript 对于快速 JavaScript 命令可能非常有效，但会丢失 JavaScript 颜色主题和行格式，这使得在 JavaScript 中编写大量代码Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="34849-121">Although writing JavaScript inline may be efficient for quick JavaScript commands, you lose JavaScript color themes and line formatting that makes it difficult to write large sections of code in Visual Studio.</span></span>  

<span data-ttu-id="34849-122">若要解决此问题，请用代码创建一个单独的 JavaScript 文件，然后使用参数传递对该文件 `ExecuteScriptAsync` 的引用。</span><span class="sxs-lookup"><span data-stu-id="34849-122">To solve the problem, create a separate JavaScript file with your code, and then pass a reference to that file using the `ExecuteScriptAsync` parameters.</span></span>  

1.  <span data-ttu-id="34849-123">在 `.js` 项目中创建文件，并添加要运行的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="34849-123">Create a `.js` file in your project, and add the JavaScript code that you want to run.</span></span>  <span data-ttu-id="34849-124">例如，创建一个称为 `script.js` .</span><span class="sxs-lookup"><span data-stu-id="34849-124">For example, create a file called `script.js`.</span></span>  
1.  <span data-ttu-id="34849-125">将 JavaScript 文件转换为传递给的字符串 `ExecuteScriptAsync` 。</span><span class="sxs-lookup"><span data-stu-id="34849-125">Convert the JavaScript file to a string that is passed to `ExecuteScriptAsync`.</span></span>  
    1.  <span data-ttu-id="34849-126">若要将 JavaScript 文件转换为字符串，请复制以下代码段。</span><span class="sxs-lookup"><span data-stu-id="34849-126">To convert your JavaScript file into a string, copy the following code snippet.</span></span>  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  <span data-ttu-id="34849-127">将代码粘贴到 `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="34849-127">Paste the code into `MainWindow.xaml.cs`.</span></span>  
1.  <span data-ttu-id="34849-128">使用 传递文本变量 `ExecuteScriptAsync` 。</span><span class="sxs-lookup"><span data-stu-id="34849-128">Pass your text variable using `ExecuteScriptAsync`.</span></span>  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## <span data-ttu-id="34849-129">方案：删除拖放功能</span><span class="sxs-lookup"><span data-stu-id="34849-129">Scenario:  Remove drag-and-drop functionality</span></span>  

<span data-ttu-id="34849-130">在此部分中，使用 JavaScript 从 WebView2 控件中删除拖放功能。</span><span class="sxs-lookup"><span data-stu-id="34849-130">In this section, use JavaScript to remove the drag-and-drop functionality from your WebView2 control.</span></span>  

<span data-ttu-id="34849-131">首先，浏览当前的拖放功能。</span><span class="sxs-lookup"><span data-stu-id="34849-131">To begin, explore the current drag-and-drop functionality.</span></span>  

1.  <span data-ttu-id="34849-132">创建 `.txt` 文件以便拖放。</span><span class="sxs-lookup"><span data-stu-id="34849-132">Create a `.txt` file in order to drag-and-drop.</span></span>  <span data-ttu-id="34849-133">例如，创建一个名为的文件 `contoso.txt` ，然后向该文件中添加文本。</span><span class="sxs-lookup"><span data-stu-id="34849-133">For example, create a file named `contoso.txt` and add text to it.</span></span>  
1.  <span data-ttu-id="34849-134">运行项目。</span><span class="sxs-lookup"><span data-stu-id="34849-134">Run your project.</span></span>  
1.  <span data-ttu-id="34849-135">将文件拖放 `contoso.txt` 到 WebView 控件上。</span><span class="sxs-lookup"><span data-stu-id="34849-135">Drag-and-drop the `contoso.txt` file onto the WebView control.</span></span>  <span data-ttu-id="34849-136">将打开一个新窗口，这是示例项目中代码的结果。</span><span class="sxs-lookup"><span data-stu-id="34849-136">A new window opens, which is the result of the code in your sample project.</span></span>  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="拖放操作的结果contoso.txt" lightbox="./media/dragtext.png":::
       <span data-ttu-id="34849-138">拖放操作的结果contoso.txt</span><span class="sxs-lookup"><span data-stu-id="34849-138">Result of dragging and dropping contoso.txt</span></span>  
    :::image-end:::  

<span data-ttu-id="34849-139">现在，添加代码以从 WebView2 控件中删除拖放功能。</span><span class="sxs-lookup"><span data-stu-id="34849-139">Now, add code to remove the drag-and-drop functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="34849-140">将以下代码段复制并粘贴到 `InitializeAsync()` `MainWindow.xaml.cs` 中。</span><span class="sxs-lookup"><span data-stu-id="34849-140">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  <span data-ttu-id="34849-141">运行项目。</span><span class="sxs-lookup"><span data-stu-id="34849-141">Run your project.</span></span>  
1.  <span data-ttu-id="34849-142">尝试拖放 `contoso.txt` 。</span><span class="sxs-lookup"><span data-stu-id="34849-142">Try to drag-and-drop `contoso.txt`.</span></span>  <span data-ttu-id="34849-143">确认无法拖放。</span><span class="sxs-lookup"><span data-stu-id="34849-143">Confirm that you are not able to drag-and-drop.</span></span>  

## <span data-ttu-id="34849-144">方案：删除上下文菜单</span><span class="sxs-lookup"><span data-stu-id="34849-144">Scenario:  Removing the Context Menu</span></span>  

<span data-ttu-id="34849-145">在此部分中，从 WebView2 控件中删除默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="34849-145">In this section, remove the default context menu from your WebView2 control.</span></span>  

<span data-ttu-id="34849-146">首先，浏览当前上下文菜单功能。</span><span class="sxs-lookup"><span data-stu-id="34849-146">To begin, explore the current contextual menu functionality.</span></span>  

1.  <span data-ttu-id="34849-147">运行项目。</span><span class="sxs-lookup"><span data-stu-id="34849-147">Run your project.</span></span>  
1.  <span data-ttu-id="34849-148">将鼠标悬停在 WebView2 控件上的任意位置，然后打开上下文菜单 \(右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="34849-148">Hover anywhere on the WebView2 control and open the context menu \(right-click\).</span></span>  <span data-ttu-id="34849-149">上下文菜单显示默认选项。</span><span class="sxs-lookup"><span data-stu-id="34849-149">The context menu displays the default choices.</span></span>  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="显示默认选项的上下文菜单" lightbox="./media/contextmenu.png":::
       <span data-ttu-id="34849-151">显示默认选项的上下文菜单</span><span class="sxs-lookup"><span data-stu-id="34849-151">The context menu showing the default choices</span></span>  
    :::image-end:::  
    
<span data-ttu-id="34849-152">现在添加代码以从 WebView2 控件中删除上下文菜单功能。</span><span class="sxs-lookup"><span data-stu-id="34849-152">Now add code to remove the contextual menu functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="34849-153">将以下代码段复制并粘贴到 `InitializeAsync()` `MainWindow.xaml.cs` 中。</span><span class="sxs-lookup"><span data-stu-id="34849-153">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  <span data-ttu-id="34849-154">再次运行代码。</span><span class="sxs-lookup"><span data-stu-id="34849-154">Run the code again.</span></span>  <span data-ttu-id="34849-155">确认无法打开上下文菜单 \(右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="34849-155">Confirm that you're not able to open a context menu \(right-click\).</span></span>  
   
## <span data-ttu-id="34849-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34849-156">See also</span></span>  

*   <span data-ttu-id="34849-157">有关使用 WebView2 入门的信息，请导航到 [WebView2 入门指南][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="34849-157">For more information on getting started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="34849-158">有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。</span><span class="sxs-lookup"><span data-stu-id="34849-158">For a comprehensive example of WebView2 capabilities, navigate to the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>  
*   <span data-ttu-id="34849-159">有关 WebView2 API 的详细信息，请导航到 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="34849-159">For detailed information on WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>  
*   <span data-ttu-id="34849-160">有关 WebView2 的信息，请导航到 [WebView2 资源][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="34849-160">For more information on WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>  

## <span data-ttu-id="34849-161">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="34849-161">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  


[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft Docs"  
[Webview2GettingstartedWpf]: ../gettingstarted/wpf.md "WPF (预览版中的 WebView2) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  
[Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated]: /microsoft-edge/webview2/reference/win32/icorewebview2#addscripttoexecuteondocumentcreated "AddScriptToExecuteOnDocumentCreated - 0.9.579 - 接口 ICoreWebView2 |Microsoft Docs"  
[Webview2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法 (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
