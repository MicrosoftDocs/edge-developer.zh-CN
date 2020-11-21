---
description: WebView2 for WinForms 应用的入门指南
title: WebView2 for WinForms 应用入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、winforms 应用、winforms、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET、windows 窗体
ms.openlocfilehash: f4768c38f293d1931e625136ea7068a61176541e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182386"
---
# <span data-ttu-id="d493e-104">Windows 窗体中的 WebView2 入门</span><span class="sxs-lookup"><span data-stu-id="d493e-104">Getting started with WebView2 in Windows Forms</span></span>

<span data-ttu-id="d493e-105">在本文中，开始创建你的第一个 WebView2 应用并了解 [WebView2](/microsoft-edge/webview2/index)的主要功能。</span><span class="sxs-lookup"><span data-stu-id="d493e-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2](/microsoft-edge/webview2/index).</span></span>  <span data-ttu-id="d493e-106">有关单个 Api 的详细信息，请参阅 [API 参考](/dotnet/api/microsoft.web.webview2.winforms)。</span><span class="sxs-lookup"><span data-stu-id="d493e-106">For more information on individual APIs, see [API reference](/dotnet/api/microsoft.web.webview2.winforms).</span></span>  

## <span data-ttu-id="d493e-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="d493e-107">Prerequisites</span></span>  

<span data-ttu-id="d493e-108">请确保在继续之前安装了以下先决条件列表：</span><span class="sxs-lookup"><span data-stu-id="d493e-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="d493e-109">[WebView2 运行时][Webview2Installer] 或任何 [非稳定 Microsoft Edge () Chromium](https://www.microsoftedgeinsider.com/download) 安装在 windows 10、windows 8.1 或 Windows 7 上的通道。</span><span class="sxs-lookup"><span data-stu-id="d493e-109">[WebView2 Runtime][Webview2Installer] or any [non-stable Microsoft Edge (Chromium) Canary channel](https://www.microsoftedgeinsider.com/download) installed on Windows 10, Windows 8.1, or Windows 7.</span></span> 
* <span data-ttu-id="d493e-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d493e-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="d493e-111">WebView2 当前不支持 .NET 5 和 .NET Core 设计器。</span><span class="sxs-lookup"><span data-stu-id="d493e-111">WebView2 currently does not support the .NET 5 and .NET Core designers.</span></span>

## <span data-ttu-id="d493e-112">步骤 1-创建单个窗口应用程序</span><span class="sxs-lookup"><span data-stu-id="d493e-112">Step 1 - Create a single window application</span></span>

<span data-ttu-id="d493e-113">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="d493e-113">Start with a basic desktop project containing a single main window.</span></span>  

1. <span data-ttu-id="d493e-114">打开 **Visual Studio。**</span><span class="sxs-lookup"><span data-stu-id="d493e-114">Open **Visual Studio.**</span></span>

1. <span data-ttu-id="d493e-115">选择 " **Windows 窗体 .Net Framework 应用** "，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d493e-115">Choose **Windows Forms .NET Framework App** and then choose **Next**.</span></span>

    ![newproject](./media/winforms-newproject.png)

1. <span data-ttu-id="d493e-117">输入 " **项目名称** " 和 " **位置**" 值。</span><span class="sxs-lookup"><span data-stu-id="d493e-117">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="d493e-118">选择 " **.Net Framework 4.6.2** " 或 "更高版本"。</span><span class="sxs-lookup"><span data-stu-id="d493e-118">Select **.NET Framework 4.6.2** or later.</span></span>  

    ![startproject](./media/winforms-startproj.png)

1. <span data-ttu-id="d493e-120">选择 " **创建** " 以创建你的项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-120">Choose **Create** to create your project.</span></span>

## <span data-ttu-id="d493e-121">步骤 2-安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="d493e-121">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="d493e-122">接下来使用 NuGet 将 WebView2 SDK 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-122">Next add the WebView2 SDK to the project using NuGet.</span></span>

1. <span data-ttu-id="d493e-123">打开项目上的上下文菜单 \ (右键单击 "\ ) "，然后选择 " **管理 NuGet 程序包 ...**"。</span><span class="sxs-lookup"><span data-stu-id="d493e-123">Open the context menu on the project \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="管理 NuGet 程序包":::
       <span data-ttu-id="d493e-125">管理 NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="d493e-125">Manage NuGet Packages</span></span> :::image-end:::

1. <span data-ttu-id="d493e-126">`Microsoft.Web.WebView2`在搜索栏中输入。</span><span class="sxs-lookup"><span data-stu-id="d493e-126">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="d493e-127">从搜索结果中选择 " **WebView2** "。</span><span class="sxs-lookup"><span data-stu-id="d493e-127">Choose **Microsoft.Web.WebView2** from the search results.</span></span>  

    ![nuget.exe](./media/installnuget.png)

<span data-ttu-id="d493e-129">全部设置为开始使用 WebView2 API 开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="d493e-129">You're all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="d493e-130">选择 `F5` 以生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-130">Select `F5` to build and run the project.</span></span>  <span data-ttu-id="d493e-131">正在运行的项目显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="d493e-131">The running project displays an empty window.</span></span>  

![emptyApp](./media/winforms-emptyApp.png)

## <span data-ttu-id="d493e-133">步骤 3-创建单个 Web 视图</span><span class="sxs-lookup"><span data-stu-id="d493e-133">Step 3 - Create a single WebView</span></span>  

<span data-ttu-id="d493e-134">接下来，将 Web 视图添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d493e-134">Next add a WebView to your application.</span></span>  

1. <span data-ttu-id="d493e-135">打开 **Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="d493e-135">Open the **Windows Forms Designer**.</span></span>  
1. <span data-ttu-id="d493e-136">在**工具箱**中搜索**WebView2** 。</span><span class="sxs-lookup"><span data-stu-id="d493e-136">Search for **WebView2** in the **Toolbox**.</span></span> <span data-ttu-id="d493e-137">将 **WebView2** 控件拖放到 Windows Forms 应用中。</span><span class="sxs-lookup"><span data-stu-id="d493e-137">Drag and drop the **WebView2** control into the Windows Forms App.</span></span>
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="显示 WebView2 的工具箱":::
       <span data-ttu-id="d493e-139">显示 WebView2 的工具箱</span><span class="sxs-lookup"><span data-stu-id="d493e-139">Toolbox displaying WebView2</span></span> :::image-end:::  

1. <span data-ttu-id="d493e-140">将 `Name` 属性更改为 `webView`。</span><span class="sxs-lookup"><span data-stu-id="d493e-140">Change the `Name` property to `webView`.</span></span>
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 控件的属性":::
       <span data-ttu-id="d493e-142">WebView2 控件的属性</span><span class="sxs-lookup"><span data-stu-id="d493e-142">Properties of the WebView2 control</span></span> :::image-end:::

1. <span data-ttu-id="d493e-143">该 `Source` 属性设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="d493e-143">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span> <span data-ttu-id="d493e-144">将 Source 属性设置为</span><span class="sxs-lookup"><span data-stu-id="d493e-144">Set the Source property to</span></span> <https://www.microsoft.com>
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 控件的 Source 属性":::
       <span data-ttu-id="d493e-146">WebView2 控件的 Source 属性</span><span class="sxs-lookup"><span data-stu-id="d493e-146">The Source property of the WebView2 control</span></span> :::image-end:::

<span data-ttu-id="d493e-147">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-147">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d493e-148">确认你的 WebView2 控件是否显示 [https://www.microsoft.com](https://www.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="d493e-148">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>

![hellowebview](./media/winforms-hellowebview.png)

> [!NOTE]
> <span data-ttu-id="d493e-150">如果您使用的是高 DPI 监视器，则可能需要为 [高 dpi 支持配置 Windows 窗体应用](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support)。</span><span class="sxs-lookup"><span data-stu-id="d493e-150">If you are working on a high DPI monitor, you may have to [configure your Windows Forms app for high DPI support](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support).</span></span>

## <span data-ttu-id="d493e-151">步骤 4-处理窗口调整大小事件</span><span class="sxs-lookup"><span data-stu-id="d493e-151">Step 4 - Handle Window Resize Events</span></span>

<span data-ttu-id="d493e-152">将更多控件从工具箱添加到 Windows 窗体，然后相应地处理窗口大小调整事件。</span><span class="sxs-lookup"><span data-stu-id="d493e-152">Add a few more controls to your Windows Forms from the toolbox, and then handle window resize events appropriately.</span></span>

1. <span data-ttu-id="d493e-153">在**Windows 窗体设计器**中，打开 **"工具箱**"</span><span class="sxs-lookup"><span data-stu-id="d493e-153">In the **Windows Forms Designer**, open the **Toolbox**</span></span>
1. <span data-ttu-id="d493e-154">将 **TextBox** 拖放到 Windows Forms 应用中。</span><span class="sxs-lookup"><span data-stu-id="d493e-154">Drag and Drop a **TextBox** into the Windows Forms App.</span></span> <span data-ttu-id="d493e-155">**TextBox** `addressBar` 在 "**属性" 选项卡**中命名文本框。</span><span class="sxs-lookup"><span data-stu-id="d493e-155">Name the **TextBox** `addressBar` in the **Properties Tab**.</span></span>
1. <span data-ttu-id="d493e-156">将 **按钮** 拖放到 Windows 窗体应用中。</span><span class="sxs-lookup"><span data-stu-id="d493e-156">Drag and Drop a **Button** into the Windows Forms App.</span></span> <span data-ttu-id="d493e-157">将**按钮**中的文本更改为 `Go!` 并在**Button** `goButton` "**属性" 选项卡**中命名该按钮。</span><span class="sxs-lookup"><span data-stu-id="d493e-157">Change the text in the **Button** to `Go!` and name the **Button** `goButton` in the **Properties Tab**.</span></span>

    <span data-ttu-id="d493e-158">应用在设计器中的外观应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d493e-158">The app should look like the following image in the designer.</span></span>
    
    ![设计器](./media/winforms-designer.png)

1. <span data-ttu-id="d493e-160">在 **Form1.cs** 定义 `Form_Resize` 以在调整应用窗口大小时保持控件的位置。</span><span class="sxs-lookup"><span data-stu-id="d493e-160">In **Form1.cs** define `Form_Resize` to keep the controls in place when the App Window is resized.</span></span>

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);
}

private void Form_Resize(object sender, EventArgs e)
{
    webView.Size = this.ClientSize - new System.Drawing.Size(webView.Location);
    goButton.Left = this.ClientSize.Width - goButton.Width;
    addressBar.Width = goButton.Left - addressBar.Left;
}
```

<span data-ttu-id="d493e-161">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-161">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d493e-162">确认应用显示类似于以下屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="d493e-162">Confirm that the app displays similar to the following screenshot.</span></span>

![应用](./media/winforms-app.png)

## <span data-ttu-id="d493e-164">步骤 5-导航</span><span class="sxs-lookup"><span data-stu-id="d493e-164">Step 5 - Navigation</span></span>

<span data-ttu-id="d493e-165">添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的功能。</span><span class="sxs-lookup"><span data-stu-id="d493e-165">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1. <span data-ttu-id="d493e-166">在 `Form1.cs` "添加命名空间" 中，将 `CoreWebView2` 以下代码片段插入到顶部 `Form1.cs` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-166">In `Form1.cs` add the `CoreWebView2` namespace by inserting the following code snippet at the top of `Form1.cs`.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1. <span data-ttu-id="d493e-167">在 **Windows 窗体设计器**中，双击 `Go!` 要在其中创建方法的按钮 `goButton_Click` `Form1.cs` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-167">In the **Windows Forms Designer**, double-click on the `Go!` button to create the `goButton_Click` method in `Form1.cs`.</span></span> <span data-ttu-id="d493e-168">在函数内复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="d493e-168">Copy and paste the following snippet inside the function.</span></span> <span data-ttu-id="d493e-169">现在，该 `goButton_Click` 函数将 Web 视图导航到在地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="d493e-169">Now, the `goButton_Click` function navigates the WebView to the URL entered in the address bar.</span></span>

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="d493e-170">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-170">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d493e-171">在地址栏中输入新的 URL，然后选择 " **转到**"。</span><span class="sxs-lookup"><span data-stu-id="d493e-171">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="d493e-172">例如，enter `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-172">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="d493e-173">确认 WebView2 控件导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="d493e-173">Confirm that the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="d493e-174">确保在地址栏中输入完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="d493e-174">Ensure a complete URL is entered in the address bar.</span></span> <span data-ttu-id="d493e-175">`ArgumentException`如果 URL 不以 or 开头的 URL，则会引发 `http://`</span><span class="sxs-lookup"><span data-stu-id="d493e-175">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

![bing](./media/winforms-bing.png)

## <span data-ttu-id="d493e-177">步骤 6-导航事件</span><span class="sxs-lookup"><span data-stu-id="d493e-177">Step 6 - Navigation events</span></span>  

<span data-ttu-id="d493e-178">在网页导航期间，WebView2 控件引发事件。</span><span class="sxs-lookup"><span data-stu-id="d493e-178">During webpage navigation, the WebView2 control raises events.</span></span> <span data-ttu-id="d493e-179">托管 WebView2 控件的应用程序将侦听以下事件。</span><span class="sxs-lookup"><span data-stu-id="d493e-179">The application that hosts WebView2 controls listens for the following events.</span></span>  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

<span data-ttu-id="d493e-180">有关详细信息，请参阅 [导航事件](../concepts/navigation-events.md)。</span><span class="sxs-lookup"><span data-stu-id="d493e-180">For more information, see [Navigation Events](../concepts/navigation-events.md).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   <span data-ttu-id="d493e-182">导航事件</span><span class="sxs-lookup"><span data-stu-id="d493e-182">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="d493e-183">当发生错误时，将引发以下事件，并可能依赖于导航到错误页面。</span><span class="sxs-lookup"><span data-stu-id="d493e-183">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

<span data-ttu-id="d493e-184">当存在 HTTP 重定向时，有多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="d493e-184">When there's an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="d493e-185">若要演示如何使用这些事件，请首先注册 `NavigationStarting` 一个用于取消任何不使用 HTTPS 的请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="d493e-185">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span>  

<span data-ttu-id="d493e-186">在中 `Form1.cs` ，修改构造函数，如下所示，并添加 `EnsureHttps` 函数。</span><span class="sxs-lookup"><span data-stu-id="d493e-186">In `Form1.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);

    webView.NavigationStarting += EnsureHttps;
}

void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        args.Cancel = true;
    }
}
```

<span data-ttu-id="d493e-187">在构造函数中，EnsureHttps 将注册为 WebView2 控件上事件的事件处理程序 `NavigationStarting` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-187">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="d493e-188">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-188">Select `F5` to build and run your project.</span></span> <span data-ttu-id="d493e-189">确认在导航到 HTTP 站点时，Web 视图保持不变。</span><span class="sxs-lookup"><span data-stu-id="d493e-189">Confirm that when navigating to an HTTP site, the WebView remains unchanged.</span></span> <span data-ttu-id="d493e-190">但是，Web 视图将导航到 HTTPS 站点。</span><span class="sxs-lookup"><span data-stu-id="d493e-190">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="d493e-191">步骤 7-脚本</span><span class="sxs-lookup"><span data-stu-id="d493e-191">Step 7 - Scripting</span></span>  

<span data-ttu-id="d493e-192">在运行时，你可以使用主机应用程序将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="d493e-192">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="d493e-193">插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="d493e-193">The injected JavaScript applies to all new top-level documents and any child frames, until the JavaScript is removed.</span></span>  <span data-ttu-id="d493e-194">插入的 JavaScript 在创建全局对象之后以及 HTML 文档中包含的任何脚本之前运行。</span><span class="sxs-lookup"><span data-stu-id="d493e-194">The injected JavaScript is run after creation of the global object, and before any scripts included in the HTML document.</span></span>  

<span data-ttu-id="d493e-195">导航到非 HTTPS 网站时，可以使用脚本来提醒用户。</span><span class="sxs-lookup"><span data-stu-id="d493e-195">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="d493e-196">修改该 `EnsureHttps` 函数，以便它使用 [ExecuteScriptAsync]() 方法将脚本插入 web 内容。</span><span class="sxs-lookup"><span data-stu-id="d493e-196">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync]() method.</span></span>  

```csharp
void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        webView.CoreWebView2.ExecuteScriptAsync($"alert('{uri} is not safe, try an https link')");
        args.Cancel = true;
    }
}
```  

<span data-ttu-id="d493e-197">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="d493e-197">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d493e-198">确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。</span><span class="sxs-lookup"><span data-stu-id="d493e-198">Confirm that the application displays an alert when you navigate to a site that doesn't use HTTPS.</span></span>  

![https](./media/winforms-https.png)

## <span data-ttu-id="d493e-200">步骤 8-主机和 web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="d493e-200">Step 8 - Communication between host and web content</span></span>  

<span data-ttu-id="d493e-201">宿主和 web 内容可以按如下方式进行通信 `postMessage` ：</span><span class="sxs-lookup"><span data-stu-id="d493e-201">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

* <span data-ttu-id="d493e-202">WebView2 控件中的 Web 内容可能会使用将消息发布到主机 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-202">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="d493e-203">主机使用主机上已注册的任何内容处理消息 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-203">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
* <span data-ttu-id="d493e-204">使用 or 将消息发布到 WebView2 控件中的 web `CoreWebView2.PostWebMessageAsString` 内容 `CoreWebView2.PostWebMessageAsJSON` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-204">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="d493e-205">这些消息由添加到的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-205">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="d493e-206">此通信机制允许 web 内容使用本机功能将消息传递到主机。</span><span class="sxs-lookup"><span data-stu-id="d493e-206">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="d493e-207">在你的项目中，当 WebView2 控件导航到 URL 时，它将在地址栏中显示 URL，并向 WebView2 控件中显示的 URL 的用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="d493e-207">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1. <span data-ttu-id="d493e-208">在 **Form1.cs**中，更新你的构造函数并创建 `InitializeAsync` 函数，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="d493e-208">In **Form1.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="d493e-209">`InitializeAsync`函数会等待[EnsureCoreWebView2Async]() ，因为它的初始化 `CoreWebView2` 是异步的。</span><span class="sxs-lookup"><span data-stu-id="d493e-209">The `InitializeAsync` function awaits [EnsureCoreWebView2Async]() because the initialization of `CoreWebView2` is asynchronous.</span></span>  

    ```csharp
    public Form1()
    {
        InitializeComponent();
        this.Resize += new System.EventHandler(this.Form_Resize);
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }

    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  

1. <span data-ttu-id="d493e-210">初始化 **CoreWebView2** 后，注册一个事件处理程序以响应 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-210">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="d493e-211">在中 `Form1.cs` ， `InitializeAsync` `UpdateAddressBar` 使用以下代码段进行更新和添加。</span><span class="sxs-lookup"><span data-stu-id="d493e-211">In `Form1.cs`, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
    }

    void UpdateAddressBar(object sender, CoreWebView2WebMessageReceivedEventArgs args)
    {
        String uri = args.TryGetWebMessageAsString();
        addressBar.Text = uri;
        webView.CoreWebView2.PostWebMessageAsString(uri);
    }
    ```  

1. <span data-ttu-id="d493e-212">为了让 web 视图发送和响应 web 消息，在 `CoreWebView2` 初始化后，主机会将 web 内容中的脚本插入到：</span><span class="sxs-lookup"><span data-stu-id="d493e-212">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host injects a script in the web content to:</span></span>  

    1. <span data-ttu-id="d493e-213">使用将 URL 发送给主机 `postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="d493e-213">Send the URL to the host using `postMessage`.</span></span>
    1. <span data-ttu-id="d493e-214">注册一个事件处理程序以打印从主机发送的消息。</span><span class="sxs-lookup"><span data-stu-id="d493e-214">Register an event handler to print a message sent from the host.</span></span>  

<span data-ttu-id="d493e-215">在中 `Form1.cs` ，更新， `InitializeAsync` 如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="d493e-215">In `Form1.cs`, update `InitializeAsync` as shown in the following code snippet.</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="d493e-216">选择 `F5` 生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="d493e-216">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="d493e-217">确认地址栏显示在 Web 视图中显示的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="d493e-217">Confirm that the address bar displays the URL of the site displayed in the WebView.</span></span> <span data-ttu-id="d493e-218">此外，当你成功导航到新 URL 时，Web 视图会警告 Web 视图中显示的 URL 的用户。</span><span class="sxs-lookup"><span data-stu-id="d493e-218">Also, when you successfully navigate to a new URL, the WebView alerts the user of the URL displayed in the WebView.</span></span>  

![finalapp](./media/winforms-finalapp.png)

<span data-ttu-id="d493e-220">恭喜，你已构建了你的第一个 WebView2 应用！</span><span class="sxs-lookup"><span data-stu-id="d493e-220">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="d493e-221">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d493e-221">Next steps</span></span> 

<span data-ttu-id="d493e-222">若要继续了解有关 WebView2 的详细信息，请导航到以下资源。</span><span class="sxs-lookup"><span data-stu-id="d493e-222">To continue learning more about WebView2, navigate to the following resources.</span></span>

* <span data-ttu-id="d493e-223">[WebView2Samples](https://github.com/MicrosoftEdge/WebView2Samples)存储库有一个全面的 WebView2's 功能示例。</span><span class="sxs-lookup"><span data-stu-id="d493e-223">The [WebView2Samples repo](https://github.com/MicrosoftEdge/WebView2Samples) has a comprehensive example of WebView2's capabilities.</span></span>
* <span data-ttu-id="d493e-224">有关我们的 Api 的更多详细信息，请 [参阅 API 参考](/dotnet/api/microsoft.web.webview2.winforms.webview2) 。</span><span class="sxs-lookup"><span data-stu-id="d493e-224">The [API reference](/dotnet/api/microsoft.web.webview2.winforms.webview2) for more detailed information about our APIs.</span></span>
* <span data-ttu-id="d493e-225">[WebView2 资源](../index.md#next-steps)。</span><span class="sxs-lookup"><span data-stu-id="d493e-225">[WebView2 Resources](../index.md#next-steps).</span></span>


## <span data-ttu-id="d493e-226">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="d493e-226">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  


<!-- links -->  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序" 
