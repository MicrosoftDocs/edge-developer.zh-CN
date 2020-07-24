---
description: 在 WinUI 应用中将 web 内容与 Microsoft Edge Web 视图2控件一起托管
title: 适用于 WinUI 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、winui 应用、winui、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET
ms.openlocfilehash: 9960a4411e69f0232ae2d202a61a9beb01c0a631
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895509"
---
# <span data-ttu-id="71673-104">WinUI3 中的 WebView2 入门（预览版）</span><span class="sxs-lookup"><span data-stu-id="71673-104">Getting started with WebView2 in WinUI3 (Preview)</span></span>  

<span data-ttu-id="71673-105">在本文中，开始使用 WinUI3 创建你的第一个 WebView2 应用，并了解[Microsoft Edge WebView2 （预览版）简介][Webview2Index]的主要功能。</span><span class="sxs-lookup"><span data-stu-id="71673-105">In this article, get started creating your first WebView2 app with WinUI3 and learn about the main features of [Introduction to Microsoft Edge WebView2 (Preview)][Webview2Index].</span></span>  <span data-ttu-id="71673-106">有关单个 Api 的详细信息，请参阅[API 参考][GithubMicrosoftUiXamlSpecsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="71673-106">For more information on individual APIs, see [API reference][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

## <span data-ttu-id="71673-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="71673-107">Prerequisites</span></span>  

<span data-ttu-id="71673-108">请确保在继续下一篇文章之前安装以下先决条件列表。</span><span class="sxs-lookup"><span data-stu-id="71673-108">Ensure you install the following list of pre-requisites before proceeding with the following article.</span></span>  

*   <span data-ttu-id="71673-109">Windows 10 版本 1803 \ （内部版本17134）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="71673-109">Windows 10 version 1803 \(build 17134\) or later.</span></span>  <span data-ttu-id="71673-110">有关详细信息，请参阅[Windows Update： FAQ][MicrosoftSupport12373]。</span><span class="sxs-lookup"><span data-stu-id="71673-110">For more information, see [Windows Update: FAQ][MicrosoftSupport12373].</span></span>  
*   <span data-ttu-id="71673-111">Windows 10、Windows 8.1 或 Windows 7 上的[Microsoft Edge （Chromium）][MicrosoftedgeinsiderDownload]未带的频道。</span><span class="sxs-lookup"><span data-stu-id="71673-111">[Microsoft Edge (Chromium) Canary channel][MicrosoftedgeinsiderDownload] on Windows 10, Windows 8.1, or Windows 7.</span></span>  
*   <span data-ttu-id="71673-112">Visual Studio 2019，版本16.7 预览版1。</span><span class="sxs-lookup"><span data-stu-id="71673-112">Visual Studio 2019, version 16.7 Preview 1.</span></span>  <span data-ttu-id="71673-113">有关详细信息，请参阅[WINDOWS UI 库3预览2（2020年7月）][WindowsAppsWinui3ConfigureYourDevEnvironment]。</span><span class="sxs-lookup"><span data-stu-id="71673-113">For more information, see [Windows UI Library 3 Preview 2 (July 2020)][WindowsAppsWinui3ConfigureYourDevEnvironment].</span></span>  
*   <span data-ttu-id="71673-114">.NET 5 预览版4的[x64][WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]和[x86][WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]版本。</span><span class="sxs-lookup"><span data-stu-id="71673-114">Both the [x64][WindowsDotnetcliBlobCoreSdk50100Preview4202681X86] and [x86][WindowsDotnetcliBlobCoreSdk50100Preview4202681X64] versions of .NET 5 Preview 4.</span></span>  
*   <span data-ttu-id="71673-115">Visual Studio 2019 的[WinUI 3 项目模板][VisualstudioMarketplaceWinUiprojecttemplates]扩展。</span><span class="sxs-lookup"><span data-stu-id="71673-115">[WinUI 3 Project Templates][VisualstudioMarketplaceWinUiprojecttemplates] extension for Visual Studio 2019.</span></span>  
<span data-ttu-id="71673-116">确保[启用开发人员模式][WindowsUwpGetStartedEnableYourDeviceForDevelopment]以确保你有权访问所有 Visual Studio 功能。</span><span class="sxs-lookup"><span data-stu-id="71673-116">Ensure you [Enable Developer Mode][WindowsUwpGetStartedEnableYourDeviceForDevelopment] to ensure you have access to all Visual Studio features.</span></span>  

## <span data-ttu-id="71673-117">步骤 1-创建项目</span><span class="sxs-lookup"><span data-stu-id="71673-117">Step 1 - Create Project</span></span>  

<span data-ttu-id="71673-118">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="71673-118">Start with a basic desktop project containing a single main window.</span></span>  

1.  <span data-ttu-id="71673-119">在 Visual Studio 中，选择 "**创建新项目**"。</span><span class="sxs-lookup"><span data-stu-id="71673-119">In Visual Studio, select **Create a new project**.</span></span>  
1.  <span data-ttu-id="71673-120">在 "项目" 下拉列表中，分别选择 " **c #**"、" **Windows**" 和 " **WinUI** "。</span><span class="sxs-lookup"><span data-stu-id="71673-120">In the project drop-down, select **C#**, **Windows**, and **WinUI** respectively.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="适用于 WinUI 的 Visual studio 项目创建对话框" lightbox="./media/winui-gettingstarted-selections.png":::
       <span data-ttu-id="71673-122">适用于 WinUI 的 Visual studio 项目创建对话框</span><span class="sxs-lookup"><span data-stu-id="71673-122">Visual studio project creation dialog for WinUI</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="71673-123">选择 **"空白应用"、"打包（桌面中的 WinUI）**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="71673-123">Choose **Blank App, Packaged (WinUI in Desktop)**, and then choose **Next**.</span></span>  
1.  <span data-ttu-id="71673-124">输入项目名称，选择所需的其他选项，然后选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="71673-124">Enter a project name, choose other options as needed, and then select **Create**.</span></span>  
1.  <span data-ttu-id="71673-125">在**新的通用 Windows 平台项目**中，选择以下值，然后选择 **"确定"**：</span><span class="sxs-lookup"><span data-stu-id="71673-125">In **New Universal Windows Platform Project**, select the following values, and then choose **OK**:</span></span>  
    *   <span data-ttu-id="71673-126">目标版本： **Windows 10、版本1903（内部版本18362）** 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="71673-126">Target version: **Windows 10, version 1903 (build 18362)** or later.</span></span>  
    *   <span data-ttu-id="71673-127">最低版本： **Windows 10 版本1803（内部版本17134）**。</span><span class="sxs-lookup"><span data-stu-id="71673-127">Minimum version: **Windows 10, version 1803 (build 17134)**.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="新的通用 Windows 平台项目对话框，其中包含目标版本和最低版本的选定值。" lightbox="./media/winui-gettingstarted-projecttype.png":::
       <span data-ttu-id="71673-129">新的通用 Windows 平台项目对话框，其中包含目标版本和最低版本的选定值。</span><span class="sxs-lookup"><span data-stu-id="71673-129">The New Universal Windows Platform Project dialog with selected values for Target version and Minimum version.</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="71673-130">在 "解决方案资源管理器" 中，生成两个项目。</span><span class="sxs-lookup"><span data-stu-id="71673-130">In the Solution Explorer, two projects are generated.</span></span>  
    *   <span data-ttu-id="71673-131">**项目名称（桌面）**。</span><span class="sxs-lookup"><span data-stu-id="71673-131">**Your project name(Desktop)**.</span></span> <span data-ttu-id="71673-132">此项目包含你的应用的代码。</span><span class="sxs-lookup"><span data-stu-id="71673-132">This project contains the code for your app.</span></span>  <span data-ttu-id="71673-133">**App.xaml.cs**定义一个 `Application` 表示你的应用实例的类。</span><span class="sxs-lookup"><span data-stu-id="71673-133">**App.xaml.cs** defines an`Application`class that represents your app instance.</span></span> <span data-ttu-id="71673-134">**MainWindow.xaml.cs**定义一个 `MainWindow` 类，该类表示你的应用实例显示的主窗口。</span><span class="sxs-lookup"><span data-stu-id="71673-134">**MainWindow.xaml.cs** defines a`MainWindow`class that represents the main window displayed by your app instance.</span></span>  <span data-ttu-id="71673-135">这些类派生自 `Microsoft.UI.Xaml` WinUI 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="71673-135">These classes derive from types in the`Microsoft.UI.Xaml`namespace of WinUI.</span></span>  
    
    *   <span data-ttu-id="71673-136">**你的项目名称（程序包）**。</span><span class="sxs-lookup"><span data-stu-id="71673-136">**Your project name(Package)**.</span></span>  <span data-ttu-id="71673-137">此项目是 aWindows 应用程序打包 Projectthat 配置为将应用构建到 MSIX 程序包中以进行部署。</span><span class="sxs-lookup"><span data-stu-id="71673-137">This project is aWindows Application Packaging Projectthat is configured to build the app into an MSIX package for deployment.</span></span>  <span data-ttu-id="71673-138">该项目包含 thepackage manifestfor 你的应用，并且默认情况下它是你的解决方案的启动项目。</span><span class="sxs-lookup"><span data-stu-id="71673-138">The project contains thepackage manifestfor your app, and it is the startup project for your solution by default.</span></span> <span data-ttu-id="71673-139">有关详细信息，请参阅[在 Visual Studio 中设置用于 MSIX 打包的桌面应用程序][WindowsMsixDesktopToUwpPackagingDotNet]和[适用于 Windows 10 的程序包清单架构参考][UwpSchemasAppxpackageUapmanifestRoot]。</span><span class="sxs-lookup"><span data-stu-id="71673-139">For more information, see [Set up your desktop application for MSIX packaging in Visual Studio][WindowsMsixDesktopToUwpPackagingDotNet] and [Package manifest schema reference for Windows 10][UwpSchemasAppxpackageUapmanifestRoot].</span></span>
    
1.  <span data-ttu-id="71673-140">在 "解决方案资源管理器" 中，打开**MainWindow**以显示代码。</span><span class="sxs-lookup"><span data-stu-id="71673-140">In the Solution Explorer, open **MainWindow.xaml** to display the code.</span></span>  <span data-ttu-id="71673-141">选择 `F5` 以运行你的项目，并显示一个带有按钮的窗口。</span><span class="sxs-lookup"><span data-stu-id="71673-141">Select `F5` to run your project and show a window with a button.</span></span>  
    
## <span data-ttu-id="71673-142">步骤 2-将 WebView2 控件添加到你的项目</span><span class="sxs-lookup"><span data-stu-id="71673-142">Step 2 - Add a WebView2 control to your project</span></span>  

<span data-ttu-id="71673-143">接下来，将 WebView2 控件添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="71673-143">Next add a WebView2 control to your project.</span></span>  

1.  <span data-ttu-id="71673-144">打开 `MainWindow.xaml`。</span><span class="sxs-lookup"><span data-stu-id="71673-144">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="71673-145">通过在标记内插入以下行来添加 WebView2 XAML 命名空间 `<Window/>` 。</span><span class="sxs-lookup"><span data-stu-id="71673-145">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    <span data-ttu-id="71673-146">确认中的代码 `MainWindow.xaml` 与以下代码片段类似。</span><span class="sxs-lookup"><span data-stu-id="71673-146">Confirm that your code in `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
    ```xml
    <Window
          x:Class="WinUI_Sample.MainWindow"
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:local="using:WinUI_Sample"
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
          mc:Ignorable="d"
          xmlns:controls="using:Microsoft.UI.Xaml.Controls"
          >
        
          <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" VerticalAlignment="Center">
            <Button x:Name="myButton" Click="myButton_Click">Click Me</Button>
          </StackPanel>
    
    </Window>
    ```  
    
1.  <span data-ttu-id="71673-147">若要添加 WebView2 控件，请将 `<StackPanel>` 标记替换为以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="71673-147">To add the WebView2 control, replace the `<StackPanel>` tags with the following code snippet.</span></span>  <span data-ttu-id="71673-148">该 `Source` 属性设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="71673-148">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
    ```xml  
    <Grid>

        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
            <ColumnDefinition Width="Auto" />
        </Grid.ColumnDefinitions>
        
        <controls:WebView2 x:Name="MyWebView"  Grid.Row="1" Grid.ColumnSpan="2" 
            Source="https://www.microsoft.com" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" />
    
    </Grid>
    ```  
    
1.  <span data-ttu-id="71673-149">打开 `MainWindow.xaml.cs` 并注释掉以下行。</span><span class="sxs-lookup"><span data-stu-id="71673-149">Open `MainWindow.xaml.cs` and comment out the following line.</span></span>
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  <span data-ttu-id="71673-150">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="71673-150">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="71673-151">确认你的 WebView2 控件是否显示 [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="71673-151">Confirm that your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="显示 microsoft.com 网站的 WebView2 控件" lightbox="./media/winui-gettingstarted-part3.png":::
       <span data-ttu-id="71673-153">显示 microsoft.com 网站的 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="71673-153">A WebView2 control displaying the microsoft.com site.</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="71673-154">步骤 3-添加导航控件</span><span class="sxs-lookup"><span data-stu-id="71673-154">Step 3 - Add navigation controls</span></span>  

<span data-ttu-id="71673-155">通过向应用添加地址栏，允许用户控制 WebView2 控件中显示的网页。</span><span class="sxs-lookup"><span data-stu-id="71673-155">Allow users to control the web page that is displayed in your WebView2 control by adding an address bar to your app.</span></span> 

1.  <span data-ttu-id="71673-156">在**MainWindow**中，将以下代码段复制并粘贴到包含该 `Grid` 元素的元素内 `WebView2` 。</span><span class="sxs-lookup"><span data-stu-id="71673-156">In **MainWindow.xaml**, copy and paste the following code snippet inside the `Grid` element that contains the `WebView2` element.</span></span>  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    <span data-ttu-id="71673-157">确认你 `Grid` 的元素 `MainWindow.xaml` 类似于以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="71673-157">Confirm that your `Grid` element of `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
    ```xml
    <Grid>
    
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
            <ColumnDefinition Width="Auto" />
        </Grid.ColumnDefinitions>
    
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
        
        <WebView2 x:Name="MyWebView"  Grid.Row="1" Grid.ColumnSpan="2" 
            Source="https://www.microsoft.com" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" />
    
    </Grid>
    ```  
    
1.  <span data-ttu-id="71673-158">在**MainWindow.xaml.cs**中，将以下代码片段复制到，该代码片段会将 `myButton_Click` WebView2 控件导航到在地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="71673-158">In **MainWindow.xaml.cs**, copy the following code snippet to `myButton_Click`, which navigates the WebView2 control to the URL entered in the address bar.</span></span>  
    
    ```csharp
    private void myButton_Click(object sender, RoutedEventArgs e)
    {
        try
        {
            Uri targetUri = new Uri(addressBar.Text);
            MyWebView.Source = targetUri;
        }
        catch (FormatException ex)
        {
            // Incorrect address entered.
        }
    }
    ```  
    
    <span data-ttu-id="71673-159">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="71673-159">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="71673-160">在地址栏中输入新的 URL，然后选择 "**转到**"。</span><span class="sxs-lookup"><span data-stu-id="71673-160">Enter a new URL in the address bar, and then select **Go**.</span></span>  <span data-ttu-id="71673-161">例如，enter `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="71673-161">For example, enter `https://www.bing.com`.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="71673-162">确保在地址栏中使用完整的 Url。</span><span class="sxs-lookup"><span data-stu-id="71673-162">Ensure you use complete URLs in the address bar.</span></span> `ArgumentException` <span data-ttu-id="71673-163">如果 URL 不以 or 开头，将引发异常 `http://` `https://` 。</span><span class="sxs-lookup"><span data-stu-id="71673-163">exceptions are thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="Bing.com" lightbox="./media/winui-gettingstarted-bing.png":::
       <span data-ttu-id="71673-165">Bing.com</span><span class="sxs-lookup"><span data-stu-id="71673-165">Bing.com</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="71673-166">步骤 4-导航事件</span><span class="sxs-lookup"><span data-stu-id="71673-166">Step 4 - Navigation events</span></span>  

<span data-ttu-id="71673-167">承载 WebView2 控件的应用程序侦听网页导航期间 WebView2 控件引发的以下事件。</span><span class="sxs-lookup"><span data-stu-id="71673-167">Applications that host WebView2 controls listen for the following events that are raised by WebView2 controls during web page navigation.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  
> [!NOTE]
> <span data-ttu-id="71673-168">HTTP 重定向引发多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="71673-168">HTTP redirects raise multiple `NavigationStarting` events.</span></span>  
<span data-ttu-id="71673-169">有关详细信息，请参阅[导航事件][Webviews2ConceptsNavigationEvents]。</span><span class="sxs-lookup"><span data-stu-id="71673-169">For more information, see [Navigation Events][Webviews2ConceptsNavigationEvents].</span></span>  

<span data-ttu-id="71673-170">发生错误时，将引发以下事件，并且可能会导航到错误页面。</span><span class="sxs-lookup"><span data-stu-id="71673-170">When errors occur, the following events are raised and may navigate to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
    

<span data-ttu-id="71673-171">作为如何使用事件的示例，注册该程序的处理程序将 `NavigationStarting` 取消任何不使用 HTTPS 的请求。</span><span class="sxs-lookup"><span data-stu-id="71673-171">As an example of how to use the events, register a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span> <span data-ttu-id="71673-172">在中 `MainWindow.xaml.cs` ，修改要注册的构造函数 `EnsureHttps` ，并添加 `EnsureHttps` 函数以使其与以下代码片段匹配。</span><span class="sxs-lookup"><span data-stu-id="71673-172">In `MainWindow.xaml.cs`, modify the constructor to register `EnsureHttps`, and add the `EnsureHttps` function so that it matches the following code snippet.</span></span>  


```csharp
public MainWindow()
{
    InitializeComponent();
    MyWebView.NavigationStarting += EnsureHttps;
}

private void EnsureHttps(WebView2 sender, WebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        args.Cancel = true;
    }
    else
    {
        addressBar.Text = uri;
    }
}
```  

<span data-ttu-id="71673-173">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="71673-173">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="71673-174">确认对 HTTP 站点的导航已被阻止，并且对于 HTTPS 站点是允许的。</span><span class="sxs-lookup"><span data-stu-id="71673-174">Confirm that navigation is blocked to HTTP sites, and allowed for HTTPS sites.</span></span>  

## <span data-ttu-id="71673-175">步骤 5-脚本</span><span class="sxs-lookup"><span data-stu-id="71673-175">Step 5 - Scripting</span></span>  

<span data-ttu-id="71673-176">宿主应用程序可能会在运行时将 JavaScript 代码注入 WebView2 控件中。</span><span class="sxs-lookup"><span data-stu-id="71673-176">Host applications may inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="71673-177">插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="71673-177">The injected JavaScript applies to all new top level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="71673-178">插入的 JavaScript 将在创建全局对象后以及 HTML 文档中包含的任何其他脚本运行之前运行。</span><span class="sxs-lookup"><span data-stu-id="71673-178">The injected JavaScript is run after creation of the global object, and before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="71673-179">例如，当用户导航到非 HTTPS 网站时，添加脚本会发送警报。</span><span class="sxs-lookup"><span data-stu-id="71673-179">As an example, add scripts send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="71673-180">修改该 `EnsureHttps` 函数以使用[ExecuteScriptAsync][Webviews2ReferenceWpf09515MicrosoftWebExecutescriptasync]将脚本注入 web 内容。</span><span class="sxs-lookup"><span data-stu-id="71673-180">Modify the `EnsureHttps` function to inject a script into the web content using [ExecuteScriptAsync][Webviews2ReferenceWpf09515MicrosoftWebExecutescriptasync].</span></span>  

```csharp
private void EnsureHttps(WebView2 sender, WebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        MyWebView.ExecuteScriptAsync($"alert('{uri} is not safe, try an https link')");
        args.Cancel = true;
    }
    else
    {
        addressBar.Text = uri;
    }
}
```  

<span data-ttu-id="71673-181">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="71673-181">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="71673-182">确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。</span><span class="sxs-lookup"><span data-stu-id="71673-182">Confirm that your application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="显示警报对话框的 WebView2 控件" lightbox="./media/winui-gettingstarted-script.png":::
   <span data-ttu-id="71673-184">显示警报对话框的 WebView2 控件</span><span class="sxs-lookup"><span data-stu-id="71673-184">WebView2 control showing an alert dialog</span></span>
:::image-end:::  

<span data-ttu-id="71673-185">恭喜，你已构建了你的第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="71673-185">Congratulations, you built your first WebView2 app.</span></span>  

## <span data-ttu-id="71673-186">后续步骤</span><span class="sxs-lookup"><span data-stu-id="71673-186">Next Steps</span></span>  

<span data-ttu-id="71673-187">我们的团队当前正在构建更多 WebView2 Api。</span><span class="sxs-lookup"><span data-stu-id="71673-187">Our team is currently building more WebView2 APIs.</span></span>  <span data-ttu-id="71673-188">有关 WebView2 Api 的当前状态的详细信息，请参阅[WebView2 规范][GithubMicrosoftUiXamlSpecsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="71673-188">For more information on the current state of WebView2 APIs, see the [WebView2 spec][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

> [!NOTE]
> <span data-ttu-id="71673-189">在 WebView2 Api 提供时，WinRT CoreWebView2 对象可能不可用。</span><span class="sxs-lookup"><span data-stu-id="71673-189">The WinRT CoreWebView2 object may not be available at the time the WebView2 APIs ship.</span></span> <span data-ttu-id="71673-190">若要了解哪些 Api 可用于 WebView2 控件，请参阅[WebView2 规范][GithubMicrosoftUiXamlSpecsWebview2]以获取可用 api 的列表。</span><span class="sxs-lookup"><span data-stu-id="71673-190">To understand which APIs are available to WebView2 controls, see [WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] for a list of the APIs that are available.</span></span> 

<span data-ttu-id="71673-191">有关 WebView2 功能的详细信息，请参阅[WebView2 概念和操作方法指南][Webview2IndexNextSteps]以及[WebView2 示例][GithubMicrosoftedgeWebview2samplesMain]存储库。</span><span class="sxs-lookup"><span data-stu-id="71673-191">For more information about WebView2 capabilities, see [WebView2 Concepts and How-To guides][Webview2IndexNextSteps], and the [WebView2 samples repo][GithubMicrosoftedgeWebview2samplesMain].</span></span>  

## <span data-ttu-id="71673-192">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="71673-192">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="71673-193">通过分享你的反馈来帮助构建更丰富的 WebView2 体验。</span><span class="sxs-lookup"><span data-stu-id="71673-193">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="71673-194">访问 Microsoft Edge Web 视图[反馈][GithubMicrosoftedgeWebviewfeedback]存储库以提交功能请求或 bug 报告，或搜索已知问题。</span><span class="sxs-lookup"><span data-stu-id="71673-194">Visit the Microsoft Edge WebView [feedback repo][GithubMicrosoftedgeWebviewfeedback] to submit feature requests or bug reports, or to search for known issues.</span></span>  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 简介（预览版） |Microsoft 文档"  
[Webview2IndexNextSteps]: ../index.md#next-steps "后续步骤-介绍 Microsoft Edge WebView2 （预览版） |Microsoft 文档"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件 |Microsoft 文档"  
[Webviews2ReferenceWpf09515MicrosoftWebExecutescriptasync]: ../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync "ExecuteScriptAsync-WebView2 | WebView2 类 |Microsoft 文档"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "适用于 Windows 10 的程序包清单架构参考 |Microsoft 文档"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "配置你的开发环境-Windows UI 库3.0 预览版1（五月2020） |Microsoft 文档"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "在 Visual Studio 中设置用于 MSIX 打包的桌面应用程序 |Microsoft 文档"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "启用设备进行开发 |Microsoft 文档"  

[GithubMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 规范-microsoft/microsoft-xaml-规格 |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Word"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows 更新：常见问题"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "下载 dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe "dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceWinUiprojecttemplates]: https://marketplace.visualstudio.com/items?itemName=Microsoft-WinUI.WinUIProjectTemplates "WinUI 3 项目模板"  
