---
description: 在 WPF 应用中将 web 内容与 Microsoft Edge Web 视图2控件一起托管
title: 适用于 WPF 应用的 Microsoft Edge Web 视图2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、wpf 应用、wpf、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET
ms.openlocfilehash: 01d92322a85e38dab3c502e8dd76729fef8400b1
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652912"
---
# <span data-ttu-id="2f358-104">WPF 中的 WebView2 入门（预览版）</span><span class="sxs-lookup"><span data-stu-id="2f358-104">Getting Started with WebView2 in WPF (Preview)</span></span>  

<span data-ttu-id="2f358-105">在本文中，开始创建你的第一个 WebView2 应用，并了解[WebView2 （预览版）](/microsoft-edge/hosting/webview2/index)的主要功能。</span><span class="sxs-lookup"><span data-stu-id="2f358-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2 (preview)](/microsoft-edge/hosting/webview2/index).</span></span>  <span data-ttu-id="2f358-106">有关单个 Api 的详细信息，请参阅[API 参考](../reference/dotnet/0-9-515-reference-webview2.md)。</span><span class="sxs-lookup"><span data-stu-id="2f358-106">For more information on individual APIs, see [API reference](../reference/dotnet/0-9-515-reference-webview2.md).</span></span>  

## <span data-ttu-id="2f358-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="2f358-107">Prerequisites</span></span>  

<span data-ttu-id="2f358-108">请确保在继续之前安装了以下先决条件列表：</span><span class="sxs-lookup"><span data-stu-id="2f358-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="2f358-109">安装在 Windows 10、Windows 8.1 或 Windows 7 上的[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download/) 。</span><span class="sxs-lookup"><span data-stu-id="2f358-109">[Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/) installed on Windows 10, Windows 8.1, or Windows 7.</span></span>  <span data-ttu-id="2f358-110">Microsoft Edge Web 视图团队建议使用 "未带" 通道。</span><span class="sxs-lookup"><span data-stu-id="2f358-110">The Microsoft Edge WebView team recommends using the Canary channel.</span></span>  
* <span data-ttu-id="2f358-111">[Visual Studio](https://visualstudio.microsoft.com/) 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2f358-111">[Visual Studio](https://visualstudio.microsoft.com/) 2015 or later.</span></span>  

## <span data-ttu-id="2f358-112">步骤 1-创建单个窗口应用程序</span><span class="sxs-lookup"><span data-stu-id="2f358-112">Step 1 - Create a single window application</span></span>

<span data-ttu-id="2f358-113">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="2f358-113">Start with a basic desktop project containing a single main window.</span></span>  

1. <span data-ttu-id="2f358-114">打开**Visual Studio。**</span><span class="sxs-lookup"><span data-stu-id="2f358-114">Open **Visual Studio.**</span></span>
2. <span data-ttu-id="2f358-115">选择 " **wpf .Net Core app** " 或 " **Wpf .net Framework 应用**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2f358-115">Choose **WPF .NET Core App** or **WPF .NET Framework App**, and then choose **Next**.</span></span>  

    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF 核心":::
             <span data-ttu-id="2f358-117">WPF 核心</span><span class="sxs-lookup"><span data-stu-id="2f358-117">WPF core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF 框架":::
             <span data-ttu-id="2f358-119">WPF 框架</span><span class="sxs-lookup"><span data-stu-id="2f358-119">WPF Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::

3. <span data-ttu-id="2f358-120">输入 "**项目名称**" 和 "**位置**" 值。</span><span class="sxs-lookup"><span data-stu-id="2f358-120">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="2f358-121">选择 ".NET Framework 4.6.2 或更高版本" 或 ".NET Core 3.0 或更高版本"。</span><span class="sxs-lookup"><span data-stu-id="2f358-121">Select .NET Framework 4.6.2 or later, or .NET Core 3.0 or later.</span></span>  

:::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="创建核心":::
             <span data-ttu-id="2f358-123">创建核心</span><span class="sxs-lookup"><span data-stu-id="2f358-123">Create core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="创建框架":::
             <span data-ttu-id="2f358-125">创建框架</span><span class="sxs-lookup"><span data-stu-id="2f358-125">Create Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::

4. <span data-ttu-id="2f358-126">选择 "**创建**" 以创建你的项目。</span><span class="sxs-lookup"><span data-stu-id="2f358-126">Choose **Create** to create your project.</span></span>  

## <span data-ttu-id="2f358-127">步骤 2-安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="2f358-127">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="2f358-128">接下来，将 WebView2 SDK 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="2f358-128">Next add the WebView2 SDK to the project.</span></span>  <span data-ttu-id="2f358-129">对于预览，使用 Nuget 安装 WebView2 SDK。</span><span class="sxs-lookup"><span data-stu-id="2f358-129">For the preview, install the WebView2 SDK using Nuget.</span></span>  

1. <span data-ttu-id="2f358-130">打开项目上的上下文菜单 \ （右键单击 \），然后选择 "**管理 NuGet 程序包 ...**"。</span><span class="sxs-lookup"><span data-stu-id="2f358-130">Open the context menu on the project \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       <span data-ttu-id="2f358-132">Nuget.exe</span><span class="sxs-lookup"><span data-stu-id="2f358-132">Nuget</span></span> :::image-end:::

2. <span data-ttu-id="2f358-133">`Microsoft.Web.WebView2`在搜索栏中输入。</span><span class="sxs-lookup"><span data-stu-id="2f358-133">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="2f358-134">从搜索结果中选择 " **WebView2** "。</span><span class="sxs-lookup"><span data-stu-id="2f358-134">Choose **Microsoft.Web.WebView2** from the search results.</span></span>  <span data-ttu-id="2f358-135">将 "程序包版本" 设置为 "**预发布**"，然后选择 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="2f358-135">Set the package version to **pre-release**, and then choose **Install**.</span></span>  

     ![nuget.exe](./media/installnuget.PNG)

<span data-ttu-id="2f358-137">全部设置为使用 WebView2 API 开始开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f358-137">You are all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="2f358-138">按 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="2f358-138">Press `F5` to build and run the project.</span></span>  <span data-ttu-id="2f358-139">正在运行的项目显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="2f358-139">The running project displays an empty window.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="空应用":::
   <span data-ttu-id="2f358-141">空应用</span><span class="sxs-lookup"><span data-stu-id="2f358-141">Empty app</span></span>
:::image-end:::

## <span data-ttu-id="2f358-142">步骤 3-在 MainWindow 中创建单个 Web 视图</span><span class="sxs-lookup"><span data-stu-id="2f358-142">Step 3 - Create a single WebView in MainWindow.xaml</span></span>  

<span data-ttu-id="2f358-143">接下来，将 Web 视图添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f358-143">Next add a WebView to your application.</span></span>  

1. <span data-ttu-id="2f358-144">打开 `MainWindow.xaml`。</span><span class="sxs-lookup"><span data-stu-id="2f358-144">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="2f358-145">通过在标记内插入以下行来添加 WebView2 XAML 命名空间 `<Window/>` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-145">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  

    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  

    <span data-ttu-id="2f358-146">确认代码 `MainWindow.xaml` 看起来类似于以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="2f358-146">Confirm that the code in `MainWindow.xaml` looks like the following code snippet.</span></span>  

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
        />
        <Grid>

                </Grid>
    </Window>
    ```  

2. <span data-ttu-id="2f358-147">通过 `<Grid>` 使用以下代码片段替换标记来添加 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="2f358-147">Add the WebView2 control by replacing the `<Grid>` tags, with the following code snippet.</span></span>  <span data-ttu-id="2f358-148">该 `Source` 属性设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="2f358-148">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  

    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  

3. <span data-ttu-id="2f358-149">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="2f358-149">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="2f358-150">确认你的 WebView2 控件是否显示 [https://www.microsoft.com](https://www.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="2f358-150">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       <span data-ttu-id="2f358-152">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2f358-152">Microsoft.com</span></span> :::image-end:::

## <span data-ttu-id="2f358-153">步骤 4-导航</span><span class="sxs-lookup"><span data-stu-id="2f358-153">Step 4 - Navigation</span></span>  

<span data-ttu-id="2f358-154">添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的功能。</span><span class="sxs-lookup"><span data-stu-id="2f358-154">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1. <span data-ttu-id="2f358-155">在**MainWindow**中，通过在包含 web 视图的 DockPanel 中复制和粘贴以下代码片段来添加地址栏。</span><span class="sxs-lookup"><span data-stu-id="2f358-155">In **MainWindow.xaml**, add an address bar by copying and pasting the following code snippet inside the DockPanel that contains the WebView.</span></span>  

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

<span data-ttu-id="2f358-156">确认该 `DockPanel` 部分 `MainWindow.xaml` 看起来类似于以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="2f358-156">Confirm that the `DockPanel` section of `MainWindow.xaml` looks like the following code snippet.</span></span>  

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

2. <span data-ttu-id="2f358-157">`MainWindow.xaml.cs`在 Visual Studio 中打开。</span><span class="sxs-lookup"><span data-stu-id="2f358-157">Open `MainWindow.xaml.cs` in Visual Studio.</span></span>  <span data-ttu-id="2f358-158">`CoreWebView2`通过在的顶部插入以下代码片段来添加命名空间 `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-158">Add the `CoreWebView2` namespace by inserting the following code snippet at the top of `MainWindow.xaml.cs`.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

3. <span data-ttu-id="2f358-159">在**MainWindow.xaml.cs**中，复制以下代码片段以创建 `ButtonGo_Click` 方法，该方法将 web 视图导航到在地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="2f358-159">In **MainWindow.xaml.cs**, copy the following code snippet to create the `ButtonGo_Click` method, which navigates the WebView to the URL entered in the address bar.</span></span>  

    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="2f358-160">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="2f358-160">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="2f358-161">在地址栏中输入新的 URL，然后单击 "**转到**"。</span><span class="sxs-lookup"><span data-stu-id="2f358-161">Enter a new URL in the address bar, and click **Go**.</span></span>  <span data-ttu-id="2f358-162">例如，enter `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-162">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="2f358-163">确认 WebView2 控件导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="2f358-163">Confirm that the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="2f358-164">请确保在地址栏中输入完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="2f358-164">Make sure a complete URL is entered in the address bar.</span></span> <span data-ttu-id="2f358-165">`ArgumentException`如果 URL 不以 or 开头的 URL，则会引发 `http://`</span><span class="sxs-lookup"><span data-stu-id="2f358-165">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

:::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="必应":::
   <span data-ttu-id="2f358-167">必应</span><span class="sxs-lookup"><span data-stu-id="2f358-167">Bing</span></span>
:::image-end:::

## <span data-ttu-id="2f358-168">步骤 5-导航事件</span><span class="sxs-lookup"><span data-stu-id="2f358-168">Step 5 - Navigation events</span></span>  

<span data-ttu-id="2f358-169">托管 WebView2 控件的应用程序将侦听在导航到网页期间由 WebView2 控件引发的以下事件。</span><span class="sxs-lookup"><span data-stu-id="2f358-169">The application that hosts WebView2 controls listens to the following events that are raised by the WebView2 control during navigation to web pages.</span></span>  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

<span data-ttu-id="2f358-170">有关详细信息，请参阅[导航事件](../reference/win32/0-9-488/icorewebview2.md#navigation-events)。</span><span class="sxs-lookup"><span data-stu-id="2f358-170">For more information, see [Navigation Events](../reference/win32/0-9-488/icorewebview2.md#navigation-events).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   <span data-ttu-id="2f358-172">导航事件</span><span class="sxs-lookup"><span data-stu-id="2f358-172">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="2f358-173">当发生错误时，将引发以下事件，并可能依赖于导航到错误页面。</span><span class="sxs-lookup"><span data-stu-id="2f358-173">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

<span data-ttu-id="2f358-174">当存在 HTTP 重定向时，有多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="2f358-174">When there is an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="2f358-175">若要演示如何使用这些事件，请首先注册 `NavigationStarting` 一个用于取消任何不使用 HTTPS 的请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="2f358-175">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that do not use HTTPS.</span></span>  

<span data-ttu-id="2f358-176">在中 `MainWindow.xaml.cs` ，修改构造函数，如下所示，并添加 `EnsureHttps` 函数。</span><span class="sxs-lookup"><span data-stu-id="2f358-176">In `MainWindow.xaml.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="2f358-177">在构造函数中，EnsureHttps 将注册为 WebView2 控件上事件的事件处理程序 `NavigationStarting` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-177">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="2f358-178">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="2f358-178">Press `F5` to build and run your project.</span></span> <span data-ttu-id="2f358-179">确认在导航到 HTTP 站点时，Web 视图**保持不变**。</span><span class="sxs-lookup"><span data-stu-id="2f358-179">Confirm that when navigating to an HTTP site, the WebView **remains unchanged**.</span></span> <span data-ttu-id="2f358-180">但是，Web 视图将导航到 HTTPS 站点。</span><span class="sxs-lookup"><span data-stu-id="2f358-180">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="2f358-181">步骤 6-脚本</span><span class="sxs-lookup"><span data-stu-id="2f358-181">Step 6 - Scripting</span></span>  

<span data-ttu-id="2f358-182">在运行时，你可以使用主机应用程序将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="2f358-182">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="2f358-183">插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="2f358-183">The injected JavaScript applies to all new top level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="2f358-184">插入的 JavaScript 将在创建全局对象后以及 HTML 文档中包含的任何其他脚本运行之前运行。</span><span class="sxs-lookup"><span data-stu-id="2f358-184">The injected JavaScript is run after creation of the global object, and before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="2f358-185">导航到非 HTTPS 网站时，可以使用脚本来提醒用户。</span><span class="sxs-lookup"><span data-stu-id="2f358-185">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="2f358-186">修改该 `EnsureHttps` 函数，以便它使用[ExecuteScriptAsync](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync)方法将脚本插入 web 内容。</span><span class="sxs-lookup"><span data-stu-id="2f358-186">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync) method.</span></span>  

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

<span data-ttu-id="2f358-187">按 `F5` 生成并运行你的项目。</span><span class="sxs-lookup"><span data-stu-id="2f358-187">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="2f358-188">确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。</span><span class="sxs-lookup"><span data-stu-id="2f358-188">Confirm that the application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   <span data-ttu-id="2f358-190">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2f358-190">HTTPS</span></span>
:::image-end:::

## <span data-ttu-id="2f358-191">步骤 7-主机和 web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="2f358-191">Step 7 - Communication between host and web content</span></span>  

<span data-ttu-id="2f358-192">宿主和 web 内容可以按如下方式进行通信 `postMessage` ：</span><span class="sxs-lookup"><span data-stu-id="2f358-192">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

* <span data-ttu-id="2f358-193">WebView2 控件中的 Web 内容可能会使用将消息发布到主机 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-193">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="2f358-194">主机使用主机上已注册的任何内容处理消息 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-194">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
* <span data-ttu-id="2f358-195">使用 or 将消息发布到 WebView2 控件中的 web `CoreWebView2.PostWebMessageAsString` 内容 `CoreWebView2.PostWebMessageAsJSON` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-195">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="2f358-196">这些消息由添加到的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-196">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="2f358-197">此通信机制允许 web 内容使用本机功能将消息传递到主机。</span><span class="sxs-lookup"><span data-stu-id="2f358-197">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="2f358-198">在你的项目中，当 WebView2 控件导航到 URL 时，它将在地址栏中显示 URL，并向 WebView2 控件中显示的 URL 的用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="2f358-198">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1. <span data-ttu-id="2f358-199">在**MainWindow.xaml.cs**中，更新你的构造函数并创建 `InitializeAsync` 函数，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="2f358-199">In **MainWindow.xaml.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="2f358-200">`InitializeAsync`函数会等待[EnsureCoreWebView2Async](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#ensurecorewebview2async) ，因为它的初始化 `CoreWebView2` 是异步的。</span><span class="sxs-lookup"><span data-stu-id="2f358-200">The `InitializeAsync` function awaits [EnsureCoreWebView2Async](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#ensurecorewebview2async) because the initialization of `CoreWebView2` is asynchronous.</span></span>  

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

2. <span data-ttu-id="2f358-201">初始化**CoreWebView2**后，注册一个事件处理程序以响应 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="2f358-201">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="2f358-202">在**MainWindow.xaml.cs**更新中 `InitializeAsync` ，并 `UpdateAddressBar` 使用以下代码片段添加。</span><span class="sxs-lookup"><span data-stu-id="2f358-202">In **MainWindow.xaml.cs** update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

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

3. <span data-ttu-id="2f358-203">为了让 web 视图发送和响应 web 消息，在 `CoreWebView2` 初始化后，主机：</span><span class="sxs-lookup"><span data-stu-id="2f358-203">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host:</span></span>  

    1. <span data-ttu-id="2f358-204">将脚本插入到 web 内容中，该内容注册处理程序以打印来自主机的消息。</span><span class="sxs-lookup"><span data-stu-id="2f358-204">Injects a script to the web content that registers a handler to print message from the host.</span></span>  
    2. <span data-ttu-id="2f358-205">将脚本插入到将 URL 发布到主机的 web 内容中。</span><span class="sxs-lookup"><span data-stu-id="2f358-205">Injects a script to the web content that posts the URL to the host.</span></span>  

<span data-ttu-id="2f358-206">在中 `MainWindow.xaml.cs` ，按 `InitializeAsync` 如下方式更新：</span><span class="sxs-lookup"><span data-stu-id="2f358-206">In `MainWindow.xaml.cs`, update `InitializeAsync` as follows:</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="2f358-207">按 `F5` 生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="2f358-207">Press `F5` to build and run the app.</span></span>  <span data-ttu-id="2f358-208">现在，地址栏在 Web 视图中显示 URI，当你成功导航到新的 URI 时，Web 视图会警告 Web 视图中显示的 URI 的用户。</span><span class="sxs-lookup"><span data-stu-id="2f358-208">Now the address bar displays the URI in the WebView and when you successfully navigate to a new URI, the WebView alerts the user of the URI displayed in the WebView.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="addressBar":::
   <span data-ttu-id="2f358-210">addressBar</span><span class="sxs-lookup"><span data-stu-id="2f358-210">addressBar</span></span>
:::image-end:::

<span data-ttu-id="2f358-211">恭喜，你已构建了你的第一个 WebView2 应用！</span><span class="sxs-lookup"><span data-stu-id="2f358-211">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="2f358-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2f358-212">Next Steps</span></span>  

<span data-ttu-id="2f358-213">本演练中不包含大量 WebView2 功能。</span><span class="sxs-lookup"><span data-stu-id="2f358-213">There are plenty of WebView2 functionalities that are not covered in this walkthrough.</span></span>  

<span data-ttu-id="2f358-214">若要了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="2f358-214">To learn more:</span></span>  

* <span data-ttu-id="2f358-215">请浏览[api 参考](../reference/dotnet/0-9-515-reference-webview2.md)，了解有关每个 API 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f358-215">Please explore [API reference](../reference/dotnet/0-9-515-reference-webview2.md) for detailed information about each API.</span></span>  

## <span data-ttu-id="2f358-216">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="2f358-216">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="2f358-217">通过分享你的反馈来帮助构建更丰富的 WebView2 体验！</span><span class="sxs-lookup"><span data-stu-id="2f358-217">Help build a richer WebView2 experience by sharing your feedback!</span></span>  <span data-ttu-id="2f358-218">访问 Microsoft Edge Web 视图[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告或搜索已知问题。</span><span class="sxs-lookup"><span data-stu-id="2f358-218">Visit the Microsoft Edge WebView [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports or search for known issues.</span></span>  
