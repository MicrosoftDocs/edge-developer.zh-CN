---
description: 适用于 WPF 应用的 WebView2 入门指南
title: WPF 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、wpf 应用、wpf、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET
ms.openlocfilehash: 8a18d12f30872ce3dd373e40ce8c7a4f0c4edad9
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119113"
---
# <span data-ttu-id="1b35e-104">WPF 中的 WebView2 入门 (预览) </span><span class="sxs-lookup"><span data-stu-id="1b35e-104">Getting started with WebView2 in WPF (Preview)</span></span>

<span data-ttu-id="1b35e-105">在本文中，开始创建你的第一个 WebView2 应用并了解 [WebView2 (preview) ](../index.md)的主要功能。</span><span class="sxs-lookup"><span data-stu-id="1b35e-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2 (preview)](../index.md).</span></span>  <span data-ttu-id="1b35e-106">有关单个 Api 的详细信息，请参阅 [API 参考](/dotnet/api/microsoft.web.webview2.wpf)。</span><span class="sxs-lookup"><span data-stu-id="1b35e-106">For more information on individual APIs, see [API reference](/dotnet/api/microsoft.web.webview2.wpf).</span></span>  

## <span data-ttu-id="1b35e-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="1b35e-107">Prerequisites</span></span>  

<span data-ttu-id="1b35e-108">请确保在继续之前安装了以下先决条件列表：</span><span class="sxs-lookup"><span data-stu-id="1b35e-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="1b35e-109">[Microsoft Edge (Chromium](https://www.microsoftedgeinsider.com/download) 在 windows 10、windows 8.1 或 windows 7 上安装了) 的未放大频道。</span><span class="sxs-lookup"><span data-stu-id="1b35e-109">[Microsoft Edge (Chromium) Canary channel](https://www.microsoftedgeinsider.com/download) installed on Windows 10, Windows 8.1, or Windows 7.</span></span>  
* <span data-ttu-id="1b35e-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1b35e-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 or later.</span></span>  

## <span data-ttu-id="1b35e-111">步骤 1-创建单个窗口应用程序</span><span class="sxs-lookup"><span data-stu-id="1b35e-111">Step 1 - Create a single window application</span></span>  

<span data-ttu-id="1b35e-112">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="1b35e-112">Start with a basic desktop project containing a single main window.</span></span>  

1.  <span data-ttu-id="1b35e-113">打开 **Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="1b35e-113">Open **Visual Studio**.</span></span>  
1.  <span data-ttu-id="1b35e-114">选择 " **wpf .Net Core app** " 或 " **Wpf .net Framework 应用**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1b35e-114">Select **WPF .NET Core App** or **WPF .NET Framework App**, and then select **Next**.</span></span>  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF 核心":::
             <span data-ttu-id="1b35e-116">WPF 核心</span><span class="sxs-lookup"><span data-stu-id="1b35e-116">WPF core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF 核心":::
             <span data-ttu-id="1b35e-118">WPF 框架</span><span class="sxs-lookup"><span data-stu-id="1b35e-118">WPF Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="1b35e-119">输入 " **项目名称** " 和 " **位置**" 值。</span><span class="sxs-lookup"><span data-stu-id="1b35e-119">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="1b35e-120">选择 ".NET Framework 4.6.2 或更高版本" 或 ".NET Core 3.0 或更高版本"。</span><span class="sxs-lookup"><span data-stu-id="1b35e-120">Select .NET Framework 4.6.2 or later, or .NET Core 3.0 or later.</span></span>  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="WPF 核心":::
                 <span data-ttu-id="1b35e-122">创建核心</span><span class="sxs-lookup"><span data-stu-id="1b35e-122">Create core</span></span> :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="WPF 核心":::
                 <span data-ttu-id="1b35e-124">创建框架</span><span class="sxs-lookup"><span data-stu-id="1b35e-124">Create Framework</span></span> :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  <span data-ttu-id="1b35e-125">选择 " **创建** " 以创建项目。</span><span class="sxs-lookup"><span data-stu-id="1b35e-125">Select **Create** to create your project.</span></span>  
    
## <span data-ttu-id="1b35e-126">步骤 2-安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="1b35e-126">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="1b35e-127">接下来，将 WebView2 SDK 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="1b35e-127">Next add the WebView2 SDK to the project.</span></span>  <span data-ttu-id="1b35e-128">对于预览，使用 Nuget 安装 WebView2 SDK。</span><span class="sxs-lookup"><span data-stu-id="1b35e-128">For the preview, install the WebView2 SDK using Nuget.</span></span>  

1.  <span data-ttu-id="1b35e-129">打开项目上的上下文菜单 \ (右键单击 "\ ) "，然后选择 " **管理 NuGet 程序包 ...**"。</span><span class="sxs-lookup"><span data-stu-id="1b35e-129">Open the context menu on the project \(right-click\), and select **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="WPF 核心":::
       <span data-ttu-id="1b35e-131">Nuget.exe</span><span class="sxs-lookup"><span data-stu-id="1b35e-131">Nuget</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="1b35e-132">`Microsoft.Web.WebView2`在搜索栏中输入。</span><span class="sxs-lookup"><span data-stu-id="1b35e-132">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="1b35e-133">从搜索结果中选择 " **WebView2** "。</span><span class="sxs-lookup"><span data-stu-id="1b35e-133">Select **Microsoft.Web.WebView2** from the search results.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="1b35e-134">确保选中 " **包括预**发布"，选择 " **版本**" 中的预发布程序包，然后选择 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="1b35e-134">Ensure you check **Include prerelease**, select a prerelease package in **Version**, and then choose **Install**.</span></span>  
  
     ![nuget.exe](./media/installnuget.PNG)
    
    <span data-ttu-id="1b35e-136">全部设置为使用 WebView2 API 开始开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b35e-136">You are all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="1b35e-137">选择 `F5` 以生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="1b35e-137">Select `F5` to build and run the project.</span></span>  <span data-ttu-id="1b35e-138">正在运行的项目显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="1b35e-138">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="WPF 核心":::
       <span data-ttu-id="1b35e-140">空应用</span><span class="sxs-lookup"><span data-stu-id="1b35e-140">Empty app</span></span>
    :::image-end:::  
    
## <span data-ttu-id="1b35e-141">步骤 3-在 MainWindow 中创建单个 Web 视图</span><span class="sxs-lookup"><span data-stu-id="1b35e-141">Step 3 - Create a single WebView in MainWindow.xaml</span></span>  

<span data-ttu-id="1b35e-142">接下来，将 Web 视图添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b35e-142">Next add a WebView to your application.</span></span>  

1.  <span data-ttu-id="1b35e-143">打开 `MainWindow.xaml`。</span><span class="sxs-lookup"><span data-stu-id="1b35e-143">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="1b35e-144">通过在标记内插入以下行来添加 WebView2 XAML 命名空间 `<Window/>` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-144">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    <span data-ttu-id="1b35e-145">确认代码 `MainWindow.xaml` 看起来类似于以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="1b35e-145">Confirm that the code in `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
    ```xml
    <Window x:Class="WPF_Getting_Started.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:local="clr-namespace:{YOUR PROJECT NAME}"
            xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
            mc:Ignorable="d"
            Title="MainWindow"
            Height="450"
            Width="800"
    >
        <Grid>
        
        </Grid>
    </Window>
    ```  
    
1.  <span data-ttu-id="1b35e-146">通过 `<Grid>` 使用以下代码片段替换标记来添加 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="1b35e-146">Add the WebView2 control by replacing the `<Grid>` tags, with the following code snippet.</span></span>  <span data-ttu-id="1b35e-147">该 `Source` 属性设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="1b35e-147">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  <span data-ttu-id="1b35e-148">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="1b35e-148">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="1b35e-149">确认你的 WebView2 控件是否显示 [https://www.microsoft.com](https://www.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-149">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="WPF 核心":::
       <span data-ttu-id="1b35e-151">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1b35e-151">Microsoft.com</span></span>
    :::image-end:::  
    
## <span data-ttu-id="1b35e-152">步骤 4-导航</span><span class="sxs-lookup"><span data-stu-id="1b35e-152">Step 4 - Navigation</span></span>  

<span data-ttu-id="1b35e-153">添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的功能。</span><span class="sxs-lookup"><span data-stu-id="1b35e-153">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1.  <span data-ttu-id="1b35e-154">在 **MainWindow**中，通过在包含 web 视图的 DockPanel 中复制和粘贴以下代码片段来添加地址栏。</span><span class="sxs-lookup"><span data-stu-id="1b35e-154">In **MainWindow.xaml**, add an address bar by copying and pasting the following code snippet inside the DockPanel that contains the WebView.</span></span>  
    
    ```xml
    <DockPanel DockPanel.Dock="Top">
        <Button x:Name="ButtonGo"
                DockPanel.Dock="Right"
                Click="ButtonGo_Click"
                Content="Go"
        />
        <TextBox Name="addressBar"/>
    </DockPanel>
    ```  
    
    <span data-ttu-id="1b35e-155">确认该 `DockPanel` 部分 `MainWindow.xaml` 看起来类似于以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="1b35e-155">Confirm that the `DockPanel` section of `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
    ```xml
    <DockPanel>
        <DockPanel DockPanel.Dock="Top">
            <Button x:Name="ButtonGo" DockPanel.Dock="Right" Click="ButtonGo_Click" Content="Go"/>
            <TextBox Name = "addressBar"/>
        </DockPanel>
        <wv2:WebView2 Name = "webView"
                      Source = "https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  <span data-ttu-id="1b35e-156">`MainWindow.xaml.cs`在 Visual Studio 中打开。</span><span class="sxs-lookup"><span data-stu-id="1b35e-156">Open `MainWindow.xaml.cs` in Visual Studio.</span></span>  <span data-ttu-id="1b35e-157">`CoreWebView2`通过在的顶部插入以下代码片段来添加命名空间 `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-157">Add the `CoreWebView2` namespace by inserting the following code snippet at the top of `MainWindow.xaml.cs`.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  <span data-ttu-id="1b35e-158">在 **MainWindow.xaml.cs**中，复制以下代码片段以创建 `ButtonGo_Click` 方法，该方法将 web 视图导航到在地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="1b35e-158">In **MainWindow.xaml.cs**, copy the following code snippet to create the `ButtonGo_Click` method, which navigates the WebView to the URL entered in the address bar.</span></span>  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    <span data-ttu-id="1b35e-159">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="1b35e-159">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="1b35e-160">在地址栏中输入新的 URL，然后选择 " **转到**"。</span><span class="sxs-lookup"><span data-stu-id="1b35e-160">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="1b35e-161">例如，enter `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-161">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="1b35e-162">确认 WebView2 控件导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="1b35e-162">Confirm that the WebView2 control navigates to the URL.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1b35e-163">请确保在地址栏中输入完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="1b35e-163">Make sure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="1b35e-164">`ArgumentException`如果 URL 不以 or 开头，则会引发 `http://` a `https://` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-164">An `ArgumentException` is thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="WPF 核心":::
       <span data-ttu-id="1b35e-166">必应</span><span class="sxs-lookup"><span data-stu-id="1b35e-166">Bing</span></span>
    :::image-end:::
    
## <span data-ttu-id="1b35e-167">步骤 5-导航事件</span><span class="sxs-lookup"><span data-stu-id="1b35e-167">Step 5 - Navigation events</span></span>  

<span data-ttu-id="1b35e-168">托管 WebView2 控件的应用程序将侦听在导航到网页期间由 WebView2 控件引发的以下事件。</span><span class="sxs-lookup"><span data-stu-id="1b35e-168">The application that hosts WebView2 controls listens to the following events that are raised by the WebView2 control during navigation to web pages.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

<span data-ttu-id="1b35e-169">有关详细信息，请参阅 [导航事件](../concepts/navigation-events.md)。</span><span class="sxs-lookup"><span data-stu-id="1b35e-169">For more information, see [Navigation Events](../concepts/navigation-events.md).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="WPF 核心":::
   <span data-ttu-id="1b35e-171">导航事件</span><span class="sxs-lookup"><span data-stu-id="1b35e-171">Navigation events</span></span>
:::image-end:::  

<span data-ttu-id="1b35e-172">当发生错误时，将引发以下事件，并可能依赖于导航到错误页面。</span><span class="sxs-lookup"><span data-stu-id="1b35e-172">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

<span data-ttu-id="1b35e-173">当存在 HTTP 重定向时，有多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="1b35e-173">When there is an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="1b35e-174">若要演示如何使用这些事件，请首先注册 `NavigationStarting` 一个用于取消任何不使用 HTTPS 的请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="1b35e-174">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that do not use HTTPS.</span></span>  

<span data-ttu-id="1b35e-175">在中 `MainWindow.xaml.cs` ，修改构造函数，如下所示，并添加 `EnsureHttps` 函数。</span><span class="sxs-lookup"><span data-stu-id="1b35e-175">In `MainWindow.xaml.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

```csharp
public MainWindow()
{
    InitializeComponent();
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

<span data-ttu-id="1b35e-176">在构造函数中，EnsureHttps 将注册为 WebView2 控件上事件的事件处理程序 `NavigationStarting` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-176">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="1b35e-177">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="1b35e-177">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="1b35e-178">确认在导航到 HTTP 站点时，Web 视图 **保持不变**。</span><span class="sxs-lookup"><span data-stu-id="1b35e-178">Confirm that when navigating to an HTTP site, the WebView **remains unchanged**.</span></span>  <span data-ttu-id="1b35e-179">但是，Web 视图导航到 HTTPS 站点。</span><span class="sxs-lookup"><span data-stu-id="1b35e-179">However, the WebView navigates to HTTPS sites.</span></span>  

## <span data-ttu-id="1b35e-180">步骤 6-脚本</span><span class="sxs-lookup"><span data-stu-id="1b35e-180">Step 6 - Scripting</span></span>  

<span data-ttu-id="1b35e-181">在运行时，你可以使用主机应用程序将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="1b35e-181">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="1b35e-182">插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="1b35e-182">The injected JavaScript applies to all new top level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="1b35e-183">插入的 JavaScript 将在创建全局对象后以及 HTML 文档中包含的任何其他脚本运行之前运行。</span><span class="sxs-lookup"><span data-stu-id="1b35e-183">The injected JavaScript is run after creation of the global object, and before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="1b35e-184">导航到非 HTTPS 网站时，可以使用脚本来提醒用户。</span><span class="sxs-lookup"><span data-stu-id="1b35e-184">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="1b35e-185">修改该 `EnsureHttps` 函数，以便它使用 [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync) 方法将脚本插入 web 内容。</span><span class="sxs-lookup"><span data-stu-id="1b35e-185">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync) method.</span></span>  

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

<span data-ttu-id="1b35e-186">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="1b35e-186">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="1b35e-187">确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。</span><span class="sxs-lookup"><span data-stu-id="1b35e-187">Confirm that the application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="WPF 核心":::
   <span data-ttu-id="1b35e-189">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1b35e-189">HTTPS</span></span>
:::image-end:::  

## <span data-ttu-id="1b35e-190">步骤 7-主机和 web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="1b35e-190">Step 7 - Communication between host and web content</span></span>  

<span data-ttu-id="1b35e-191">宿主和 web 内容可以按如下方式进行通信 `postMessage` ：</span><span class="sxs-lookup"><span data-stu-id="1b35e-191">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

*   <span data-ttu-id="1b35e-192">WebView2 控件中的 Web 内容可能会使用将消息发布到主机 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-192">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="1b35e-193">主机使用主机上已注册的任何内容处理消息 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-193">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="1b35e-194">使用 or 将消息发布到 WebView2 控件中的 web `CoreWebView2.PostWebMessageAsString` 内容 `CoreWebView2.PostWebMessageAsJSON` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-194">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="1b35e-195">这些消息由添加到的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-195">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="1b35e-196">此通信机制允许 web 内容使用本机功能将消息传递到主机。</span><span class="sxs-lookup"><span data-stu-id="1b35e-196">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="1b35e-197">在你的项目中，当 WebView2 控件导航到 URL 时，它将在地址栏中显示 URL，并向 WebView2 控件中显示的 URL 的用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="1b35e-197">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="1b35e-198">在 **MainWindow.xaml.cs**中，更新你的构造函数并创建 `InitializeAsync` 函数，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="1b35e-198">In **MainWindow.xaml.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="1b35e-199">`InitializeAsync`函数会等待[EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) ，因为它的初始化 `CoreWebView2` 是异步的。</span><span class="sxs-lookup"><span data-stu-id="1b35e-199">The `InitializeAsync` function awaits [EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) because the initialization of `CoreWebView2` is asynchronous.</span></span>  
    
    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }
    
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  
    
1.  <span data-ttu-id="1b35e-200">初始化 **CoreWebView2** 后，注册一个事件处理程序以响应 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="1b35e-200">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="1b35e-201">在 **MainWindow.xaml.cs** 更新中 `InitializeAsync` ，并 `UpdateAddressBar` 使用以下代码片段添加。</span><span class="sxs-lookup"><span data-stu-id="1b35e-201">In **MainWindow.xaml.cs** update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="1b35e-202">为了让 web 视图发送和响应 web 消息，在 `CoreWebView2` 初始化后，主机：</span><span class="sxs-lookup"><span data-stu-id="1b35e-202">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host:</span></span>  
    
    1.  <span data-ttu-id="1b35e-203">将脚本插入到 web 内容中，该内容注册处理程序以打印来自主机的消息。</span><span class="sxs-lookup"><span data-stu-id="1b35e-203">Injects a script to the web content that registers a handler to print message from the host.</span></span>  
    1.  <span data-ttu-id="1b35e-204">将脚本插入到将 URL 发布到主机的 web 内容中。</span><span class="sxs-lookup"><span data-stu-id="1b35e-204">Injects a script to the web content that posts the URL to the host.</span></span>  
    
    <span data-ttu-id="1b35e-205">在中 `MainWindow.xaml.cs` ，按 `InitializeAsync` 如下方式更新：</span><span class="sxs-lookup"><span data-stu-id="1b35e-205">In `MainWindow.xaml.cs`, update `InitializeAsync` as follows:</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    <span data-ttu-id="1b35e-206">按 `F5` 生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="1b35e-206">Press `F5` to build and run the app.</span></span>  <span data-ttu-id="1b35e-207">现在，地址栏在 Web 视图中显示 URI，当你成功导航到新的 URI 时，Web 视图会警告 Web 视图中显示的 URI 的用户。</span><span class="sxs-lookup"><span data-stu-id="1b35e-207">Now the address bar displays the URI in the WebView and when you successfully navigate to a new URI, the WebView alerts the user of the URI displayed in the WebView.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="WPF 核心":::
       <span data-ttu-id="1b35e-209">addressBar</span><span class="sxs-lookup"><span data-stu-id="1b35e-209">addressBar</span></span>
    :::image-end:::

<span data-ttu-id="1b35e-210">恭喜，你已构建了你的第一个 WebView2 应用！</span><span class="sxs-lookup"><span data-stu-id="1b35e-210">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="1b35e-211">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1b35e-211">Next steps</span></span>  

*   <span data-ttu-id="1b35e-212">有关 WebView2 功能的完整示例，请参阅 GitHub 上的 [WebView2Samples](https://github.com/MicrosoftEdge/WebView2Samples) 存储库。</span><span class="sxs-lookup"><span data-stu-id="1b35e-212">For a comprehensive example of WebView2 capabilities, see [WebView2Samples repo](https://github.com/MicrosoftEdge/WebView2Samples) on GitHub.</span></span>  
*   <span data-ttu-id="1b35e-213">有关 WebView2 Api 的更多详细信息，请参阅 [API 参考](/dotnet/api/microsoft.web.webview2.wpf.webview2)。</span><span class="sxs-lookup"><span data-stu-id="1b35e-213">For more detailed information about WebView2 APIs, see [API reference](/dotnet/api/microsoft.web.webview2.wpf.webview2).</span></span>  
*   <span data-ttu-id="1b35e-214">有关 WebView2 的详细信息，请参阅 [WebView2 资源](../index.md#next-steps)。</span><span class="sxs-lookup"><span data-stu-id="1b35e-214">For more information about  WebView2, see [WebView2 Resources](../index.md#next-steps).</span></span>  

## <span data-ttu-id="1b35e-215">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="1b35e-215">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  
