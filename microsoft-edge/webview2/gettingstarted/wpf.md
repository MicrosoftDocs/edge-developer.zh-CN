---
description: 适用于 WPF 应用的 WebView2 入门指南
title: 适用于 WPF 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2， webview2， WebView， webview， wpf 应用， wpf， edge， CoreWebView2， 浏览器控件， edge html， 入门， 入门， .NET
ms.openlocfilehash: 1ced88ebd80d663ac2bd25840174d8505729bf32
ms.sourcegitcommit: b51df5036642060525e03cd744b7d35726326abe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "11526078"
---
# <a name="getting-started-with-webview2-in-wpf"></a><span data-ttu-id="fdc7f-104">WPF 中的 WebView2 入门</span><span class="sxs-lookup"><span data-stu-id="fdc7f-104">Getting started with WebView2 in WPF</span></span>

<span data-ttu-id="fdc7f-105">本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="fdc7f-106">有关各个 API 的信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2Wpf]。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-106">For more information on individual APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2Wpf].</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="fdc7f-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="fdc7f-107">Prerequisites</span></span>  

<span data-ttu-id="fdc7f-108">请确保先安装以下先决条件列表，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-108">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="fdc7f-109">[WebView2][Webview2Installer] 运行时或任何 [Microsoft Edge (Chromium) ][MicrosoftedgeinsiderDownload] 安装在受支持的操作系统 \ (当前为 Windows 10、Windows 8.1 和 Windows 7\) 上的非稳定通道。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-109">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
*   <span data-ttu-id="fdc7f-110">[Visual Studio][MicrosoftVisualstudioMain] 2017 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-110">[Visual Studio][MicrosoftVisualstudioMain] 2017 or later.</span></span>  
    
## <a name="step-1---create-a-single-window-app"></a><span data-ttu-id="fdc7f-111">步骤 1 - 创建单窗口应用</span><span class="sxs-lookup"><span data-stu-id="fdc7f-111">Step 1 - Create a single-window app</span></span>  

<span data-ttu-id="fdc7f-112">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-112">Start with a basic desktop project that contains a single main window.</span></span>  

1.  <span data-ttu-id="fdc7f-113">In Visual Studio， choose **WPF .NET Core App** \ (or **WPF .NET Framework App**\) > **Next**.</span><span class="sxs-lookup"><span data-stu-id="fdc7f-113">In Visual Studio, choose **WPF .NET Core App** \(or **WPF .NET Framework App**\) > **Next**.</span></span>  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF 核心":::
             <span data-ttu-id="fdc7f-115">WPF 核心</span><span class="sxs-lookup"><span data-stu-id="fdc7f-115">WPF core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF 框架":::
             <span data-ttu-id="fdc7f-117">WPF 框架</span><span class="sxs-lookup"><span data-stu-id="fdc7f-117">WPF Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="fdc7f-118">输入**项目名称和位置\*\*\*\*的值**。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-118">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="fdc7f-119">选择 **.NET Framework 4.6.2** 或更高版本 \ (或 **.NET Core 3.0** 或更高版本\) 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-119">Choose **.NET Framework 4.6.2** or later \(or **.NET Core 3.0** or later\).</span></span>  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="创建核心":::
                 <span data-ttu-id="fdc7f-121">创建核心</span><span class="sxs-lookup"><span data-stu-id="fdc7f-121">Create core</span></span> :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="创建框架":::
                 <span data-ttu-id="fdc7f-123">创建框架</span><span class="sxs-lookup"><span data-stu-id="fdc7f-123">Create Framework</span></span> :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  <span data-ttu-id="fdc7f-124">若要创建项目，请选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fdc7f-124">To create your project, choose **Create**.</span></span>  
    
## <a name="step-2---install-webview2-sdk"></a><span data-ttu-id="fdc7f-125">步骤 2 - 安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="fdc7f-125">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="fdc7f-126">使用 NuGet 将 WebView2 SDK 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-126">Use NuGet to add the WebView2 SDK to the project.</span></span>  

1.  <span data-ttu-id="fdc7f-127">将鼠标悬停在项目上，打开上下文菜单 \ (右键单击\) ，然后选择管理**NuGet 程序包...。**</span><span class="sxs-lookup"><span data-stu-id="fdc7f-127">Hover on the projecty, open the contextual menu \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="管理 NuGet 程序包":::
       <span data-ttu-id="fdc7f-129">管理 NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="fdc7f-129">Manage NuGet packages</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="fdc7f-130">在搜索栏中，键入"> `Microsoft.Web.WebView2` **选择"Microsoft.Web.WebView2"。**</span><span class="sxs-lookup"><span data-stu-id="fdc7f-130">In the search bar, type `Microsoft.Web.WebView2` > choose **Microsoft.Web.WebView2**.</span></span>  
   
    :::image type="complex" source="./media/installnuget.png" alt-text="NuGet" lightbox="./media/installnuget.png":::
       <span data-ttu-id="fdc7f-132">NuGet</span><span class="sxs-lookup"><span data-stu-id="fdc7f-132">NuGet</span></span>  
    :::image-end:::
    
    <span data-ttu-id="fdc7f-133">准备好开始使用 WebView2 API 开发应用。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-133">Ready to start developing apps using the WebView2 API.</span></span>  <span data-ttu-id="fdc7f-134">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-134">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="fdc7f-135">正在运行的项目显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-135">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/winforms-emptyapp.png" alt-text="空应用" lightbox="./media/winforms-emptyapp.png":::
       <span data-ttu-id="fdc7f-137">空应用</span><span class="sxs-lookup"><span data-stu-id="fdc7f-137">Empty app</span></span>  
    :::image-end:::  
    
## <a name="step-3---create-a-single-webview"></a><span data-ttu-id="fdc7f-138">步骤 3 - 创建单个 WebView</span><span class="sxs-lookup"><span data-stu-id="fdc7f-138">Step 3 - Create a single WebView</span></span> 

<span data-ttu-id="fdc7f-139">接下来，将 WebView 添加到你的应用。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-139">Next add a WebView to your app.</span></span>  

1.  <span data-ttu-id="fdc7f-140">在 `MainWindow.xaml` 文件中，若要添加 WebView2 XAML 命名空间，在 标记内插入以下 `<Window/>` 行。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-140">In the `MainWindow.xaml` file, to add the WebView2 XAML namespace, insert the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    <span data-ttu-id="fdc7f-141">确保 中的代码 `MainWindow.xaml` 类似于以下代码段。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-141">Ensure the code in `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="fdc7f-142">若要添加 WebView2 控件，请将 `<Grid>` 标记替换为以下代码段。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-142">To add the WebView2 control, replace the `<Grid>` tags with the following code snippet.</span></span>  <span data-ttu-id="fdc7f-143">属性 `Source` 设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-143">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  <span data-ttu-id="fdc7f-144">若要生成并运行项目，请选择 `F5`  "确保 WebView2 控件显示 [https://www.microsoft.com][|::ref1::|Main] "。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-144">To build and run the project, select `F5`  Ensure your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       <span data-ttu-id="fdc7f-146">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fdc7f-146">Microsoft.com</span></span>
    :::image-end:::  
    
## <a name="step-4---navigation"></a><span data-ttu-id="fdc7f-147">步骤 4 - 导航</span><span class="sxs-lookup"><span data-stu-id="fdc7f-147">Step 4 - Navigation</span></span>  

<span data-ttu-id="fdc7f-148">添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的能力。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-148">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1.  <span data-ttu-id="fdc7f-149">在 文件中，通过复制并粘贴包含 WebView 的 中的以下代码段 `MainWindow.xaml` `<DockPanel>` 来添加地址栏。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-149">In the `MainWindow.xaml` file, add an address bar by copying and pasting the following code snippet inside the `<DockPanel>` that contains the WebView.</span></span>  
    
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
    
    <span data-ttu-id="fdc7f-150">确保 `<DockPanel>` 文件的 `MainWindow.xaml` 部分与以下代码段匹配。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-150">Ensure the `<DockPanel>` section of the `MainWindow.xaml` file matches the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="fdc7f-151">在Visual Studio中，若要 `MainWindow.xaml.cs` 添加命名空间，请将 `CoreWebView2` 以下代码段插入顶部。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-151">In Visual Studio, in the `MainWindow.xaml.cs` file, to add the `CoreWebView2` namespace, insert the following code snippet at the top.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  <span data-ttu-id="fdc7f-152">在文件中，复制以下代码段以创建 方法，该方法将 WebView 导航到地址栏中 `MainWindow.xaml.cs` `ButtonGo_Click` 输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-152">In the `MainWindow.xaml.cs`file, copy the following code snippet to create the `ButtonGo_Click` method, which navigates the WebView to the URL entered in the address bar.</span></span>  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    <span data-ttu-id="fdc7f-153">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-153">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="fdc7f-154">在地址栏中键入新 URL，然后选择"**转到"。**</span><span class="sxs-lookup"><span data-stu-id="fdc7f-154">Type a new URL in the address bar and choose **Go**.</span></span>  <span data-ttu-id="fdc7f-155">例如，键入 `https://www.bing.com`。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-155">For example, type `https://www.bing.com`.</span></span>  <span data-ttu-id="fdc7f-156">确保 WebView2 控件导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-156">Ensure the WebView2 control navigates to the URL.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="fdc7f-157">确保在地址栏中输入完整 URL。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-157">Make sure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="fdc7f-158">如果 `ArgumentException` URL 不以 或 为起始，则 `http://` 会引发 `https://` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-158">An `ArgumentException` is thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="必应":::
       <span data-ttu-id="fdc7f-160">bing.com</span><span class="sxs-lookup"><span data-stu-id="fdc7f-160">bing.com</span></span>
    :::image-end:::
    
## <a name="step-5---navigation-events"></a><span data-ttu-id="fdc7f-161">步骤 5 - 导航事件</span><span class="sxs-lookup"><span data-stu-id="fdc7f-161">Step 5 - Navigation events</span></span>  

<span data-ttu-id="fdc7f-162">在网页导航期间，WebView2 控件将引发事件。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-162">During webpage navigation, the WebView2 control raises events.</span></span>  <span data-ttu-id="fdc7f-163">承载 WebView2 控件的应用侦听以下事件。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-163">The app that hosts WebView2 controls listens for the following events.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

<span data-ttu-id="fdc7f-164">有关详细信息，请导航到["导航事件"。][Webview2ConceptsNavigationEvents]</span><span class="sxs-lookup"><span data-stu-id="fdc7f-164">For more information, navigate to [Navigation Events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   <span data-ttu-id="fdc7f-166">导航事件</span><span class="sxs-lookup"><span data-stu-id="fdc7f-166">Navigation events</span></span>
:::image-end:::  

<span data-ttu-id="fdc7f-167">发生错误时，将引发以下事件，并可能依赖于导航到错误网页。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-167">When an error occurs, the following events are raised and may depend on navigation to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

> [!NOTE]
> <span data-ttu-id="fdc7f-168">如果发生 HTTP 重定向，则一行 `NavigationStarting` 中有多个事件。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-168">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="fdc7f-169">若要演示如何使用事件，请注册用于取消任何非 `NavigationStarting` HTTPS 请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-169">To demonstrate how to use the events, register a handler for `NavigationStarting` that cancels any non-HTTPS requests.</span></span>  

<span data-ttu-id="fdc7f-170">在 `MainWindow.xaml.cs` 文件中，修改构造函数以匹配以下代码段并添加 `EnsureHttps` 函数。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-170">In the `MainWindow.xaml.cs` file, modify the constructor to match the following code snippet and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="fdc7f-171">在构造函数中 `EnsureHttps` ，注册为 WebView2 控件上事件 `NavigationStarting` 的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-171">In the constructor, `EnsureHttps` is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="fdc7f-172">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-172">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="fdc7f-173">确保导航到 HTTP 网站时，WebView 保持不变。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-173">Ensure when navigating to an HTTP site, the WebView remains unchanged.</span></span>  <span data-ttu-id="fdc7f-174">但是，WebView 导航到 HTTPS 网站。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-174">However, the WebView navigates to HTTPS sites.</span></span>  

## <a name="step-6---scripting"></a><span data-ttu-id="fdc7f-175">步骤 6 - 脚本</span><span class="sxs-lookup"><span data-stu-id="fdc7f-175">Step 6 - Scripting</span></span>  

<span data-ttu-id="fdc7f-176">你可以在运行时使用主机应用将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-176">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="fdc7f-177">你可以任务 WebView 运行任意 JavaScript 或添加初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-177">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="fdc7f-178">在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-178">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="fdc7f-179">注入的 JavaScript 以特定计时运行。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-179">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="fdc7f-180">创建全局对象后运行它。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-180">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="fdc7f-181">在运行 HTML 文档中包含的任何其他脚本之前运行它。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-181">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="fdc7f-182">例如，添加在用户导航到非 HTTPS 网站时发送警报的脚本。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-182">As an example, add scripts that send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="fdc7f-183">修改 `EnsureHttps` 函数以将脚本注入到使用 [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync) 方法的 Web 内容中。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-183">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync) method.</span></span>  

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

<span data-ttu-id="fdc7f-184">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-184">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="fdc7f-185">当你导航到不使用 HTTPS 的网站时，请确保应用显示一个警报。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-185">Ensure the app displays an alert when you navigate to a website that doesn't use HTTPS.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   <span data-ttu-id="fdc7f-187">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fdc7f-187">HTTPS</span></span>
:::image-end:::  

## <a name="step-7---communication-between-host-and-web-content"></a><span data-ttu-id="fdc7f-188">步骤 7 - 主机和 Web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="fdc7f-188">Step 7 - Communication between host and web content</span></span>  

<span data-ttu-id="fdc7f-189">主机和 Web 内容可能通过以下方式使用 进行通信 `postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-189">The host and web content may communicate in the following ways using `postMessage`.</span></span>  

*   <span data-ttu-id="fdc7f-190">WebView2 控件中的 Web 内容可能会使用 向主机发布消息 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-190">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="fdc7f-191">主机使用主机上注册的任何消息 `WebMessageReceived` 处理邮件。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-191">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="fdc7f-192">使用 或 将消息张贴到 WebView2 控件中的 `CoreWebView2.PostWebMessageAsString` Web 内容 `CoreWebView2.PostWebMessageAsJSON` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-192">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="fdc7f-193">消息被添加到 的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-193">The messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="fdc7f-194">通信机制使用本机功能将来自 Web 内容的消息传递给主机。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-194">The communication mechanism passes messages from web content to the host using native capabilities.</span></span>  

<span data-ttu-id="fdc7f-195">在项目中，当 WebView2 控件导航到 URL 时，它会在地址栏中显示 URL，并通知用户 WebView2 控件中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-195">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="fdc7f-196">在 `MainWindow.xaml.cs` 文件中，更新构造函数并创建 `InitializeAsync` 一个函数以匹配以下代码段。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-196">In the `MainWindow.xaml.cs` file, update your constructor and create an `InitializeAsync` function to match the following code snippet.</span></span>  <span data-ttu-id="fdc7f-197">函数 `InitializeAsync` awaits [EnsureCoreWebView2Async，](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) 因为 的初始化 `CoreWebView2` 是异步的。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-197">The `InitializeAsync` function awaits [EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) because the initialization of `CoreWebView2` is asynchronous.</span></span>  
    
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
    
1.  <span data-ttu-id="fdc7f-198">初始化 **CoreWebView2** 后，注册事件处理程序以响应 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-198">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="fdc7f-199">在 `MainWindow.xaml.cs` 中 `InitializeAsync` ，使用下面的 `UpdateAddressBar` 代码段更新和添加。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-199">In `MainWindow.xaml.cs`, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="fdc7f-200">为了使 WebView 能够发送和响应 Web 消息，在初始化后，主机 `CoreWebView2` ：</span><span class="sxs-lookup"><span data-stu-id="fdc7f-200">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host:</span></span>  
    1.  <span data-ttu-id="fdc7f-201">将脚本注入 Web 内容，用于注册处理程序以从主机打印消息。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-201">Injects a script to the web content that registers a handler to print message from the host.</span></span>  
    1.  <span data-ttu-id="fdc7f-202">将脚本注入到将 URL 张贴到主机的 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-202">Injects a script to the web content that posts the URL to the host.</span></span>  
        
    <span data-ttu-id="fdc7f-203">在 `MainWindow.xaml.cs` 文件中，进行更新 `InitializeAsync` 以匹配以下代码段。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-203">In the `MainWindow.xaml.cs` file, update `InitializeAsync` to match the following code snippet.</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    <span data-ttu-id="fdc7f-204">若要生成并运行应用，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-204">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="fdc7f-205">现在，地址栏在 WebView2 控件中显示 URI。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-205">Now, the address bar displays the URI in the WebView2 control.</span></span>  <span data-ttu-id="fdc7f-206">当您成功导航到新的 URI 时，WebView2 控件会向 WebView2 控件中显示的 URI 的用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-206">When you successfully navigate to a new URI, the WebView2 control alerts the user of the URI that's displayed in the WebView2 control.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="addressBar":::
       <span data-ttu-id="fdc7f-208">addressBar</span><span class="sxs-lookup"><span data-stu-id="fdc7f-208">addressBar</span></span>
    :::image-end:::

<span data-ttu-id="fdc7f-209">恭喜！你生成了第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-209">Congratulations, you built your first WebView2 app.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="fdc7f-210">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fdc7f-210">Next steps</span></span>  

<span data-ttu-id="fdc7f-211">若要继续了解有关 WebView2 的更多内容，请导航到以下资源。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-211">To continue learning more about WebView2, navigate to the following resources.</span></span>  

*   <span data-ttu-id="fdc7f-212">若要了解有关生成 WebView2 应用程序的信息，请导航到 [WebView2 开发最佳做法][WV2BestPractices]。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-212">To learn more about building WebView2 applications, navigate to [WebView2 development best practices][WV2BestPractices].</span></span>  
*   <span data-ttu-id="fdc7f-213">有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain] 存储库。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-213">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samplesMain] on GitHub.</span></span>  
*   <span data-ttu-id="fdc7f-214">有关 WebView2 API 的更多详细信息，请导航到 [API 参考](/dotnet/api/microsoft.web.webview2.wpf.webview2)。</span><span class="sxs-lookup"><span data-stu-id="fdc7f-214">For more detailed information about WebView2 API, navigate to [API reference](/dotnet/api/microsoft.web.webview2.wpf.webview2).</span></span>  
*   <span data-ttu-id="fdc7f-215">有关 WebView2 的信息，请导航到["WebView2 资源"。](../index.md#next-steps)</span><span class="sxs-lookup"><span data-stu-id="fdc7f-215">For more information about  WebView2, navigate to [WebView2 Resources](../index.md#next-steps).</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="fdc7f-216">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="fdc7f-216">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  
 
[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 开发最佳实践|Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async (CoreWebView2Environment) 方法|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 |Microsoft Edge 开发人员"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualStudioMain]: https://visualstudio.microsoft.com "Microsoft Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序" 
