---
description: WebView2 for WinUI 应用的入门指南
title: WebView2 for WinUI 应用入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、winui 应用、winui、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET
ms.openlocfilehash: a1ccffe332f71ee9d53ff267e8cca6bdbda81703
ms.sourcegitcommit: 02c602379537ab3b9d0a355cea7fcf96fdbd8870
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "11182719"
---
# <span data-ttu-id="91914-104">WinUI 3 (预览中的 WebView2 入门) </span><span class="sxs-lookup"><span data-stu-id="91914-104">Getting started with WebView2 in WinUI 3 (Preview)</span></span>  

<span data-ttu-id="91914-105">在本文中，了解如何创建你的第一个 WebView2 应用，以及有关 [Microsoft Edge WebView2 (Preview) ][Webview2Index]的主要功能。</span><span class="sxs-lookup"><span data-stu-id="91914-105">In this article, learn how to create your first WebView2 app and about the main features of [Introduction to Microsoft Edge WebView2 (Preview)][Webview2Index].</span></span>  <span data-ttu-id="91914-106">你的第一个 WebView2 应用使用 WinUI3。</span><span class="sxs-lookup"><span data-stu-id="91914-106">Your first WebView2 app uses WinUI3.</span></span>  <span data-ttu-id="91914-107">有关单个 Api 的详细信息，请导航到 [API 参考][GithubMicrosoftUiXamlSpecsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="91914-107">For more information on individual APIs, navigate to [API reference][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

## <span data-ttu-id="91914-108">必备条件</span><span class="sxs-lookup"><span data-stu-id="91914-108">Prerequisites</span></span>  

<span data-ttu-id="91914-109">请确保在继续下一篇文章之前安装以下先决条件列表。</span><span class="sxs-lookup"><span data-stu-id="91914-109">Ensure you install the following list of pre-requisites before proceeding with the following article.</span></span>  

1.  <span data-ttu-id="91914-110">Windows 10 版本 1803 \ (内部版本 17134 \ ) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="91914-110">Windows 10 version 1803 \(build 17134\) or later.</span></span>  <span data-ttu-id="91914-111">有关详细信息，请导航到 [Windows Update： FAQ][MicrosoftSupport12373]。</span><span class="sxs-lookup"><span data-stu-id="91914-111">For more information, navigate to [Windows Update: FAQ][MicrosoftSupport12373].</span></span>  
1.  <span data-ttu-id="91914-112">[Microsoft Edge (Chromium) ][MicrosoftedgeinsiderDownload] windows 10、windows 8.1 或 windows 7 上的 "" 通道。</span><span class="sxs-lookup"><span data-stu-id="91914-112">[Microsoft Edge (Chromium) Canary channel][MicrosoftedgeinsiderDownload] on Windows 10, Windows 8.1, or Windows 7.</span></span>  
1.  <span data-ttu-id="91914-113">Visual Studio 2019，版本16.9 预览版。</span><span class="sxs-lookup"><span data-stu-id="91914-113">Visual Studio 2019, version 16.9 Preview.</span></span>  <span data-ttu-id="91914-114">有关详细信息，请导航到 [WINDOWS UI 库3预览版 3][WindowsAppsWinui3ConfigureYourDevEnvironment]。</span><span class="sxs-lookup"><span data-stu-id="91914-114">For more information, navigate to [Windows UI Library 3 Preview 3][WindowsAppsWinui3ConfigureYourDevEnvironment].</span></span>  
    
    <span data-ttu-id="91914-115">在安装 Visual Studio 时包括以下工作负荷。</span><span class="sxs-lookup"><span data-stu-id="91914-115">Include the following workloads when you install Visual Studio.</span></span>  
    
    *   <span data-ttu-id="91914-116">.NET 桌面开发 \ (安装程序还会安装 .NET 5 \ ) </span><span class="sxs-lookup"><span data-stu-id="91914-116">.NET Desktop Development \(the installer also installs .NET 5\)</span></span>  
    *   <span data-ttu-id="91914-117">通用 Windows 平台开发</span><span class="sxs-lookup"><span data-stu-id="91914-117">Universal Windows Platform development</span></span>  
        
    <span data-ttu-id="91914-118">若要构建 c + + 应用，还必须包含以下工作负荷。</span><span class="sxs-lookup"><span data-stu-id="91914-118">To build C++ apps, you must also include the following workloads.</span></span>  
    
    *   <span data-ttu-id="91914-119">带有 c + + 的桌面开发</span><span class="sxs-lookup"><span data-stu-id="91914-119">Desktop development with C++</span></span>  
    *   <span data-ttu-id="91914-120">C + + (v142 针对通用 Windows 平台工作负荷) 通用 Windows 平台工具可选组件。</span><span class="sxs-lookup"><span data-stu-id="91914-120">The C++ (v142) Universal Windows Platform tools optional component for the Universal Windows Platform workload.</span></span>  <span data-ttu-id="91914-121">有关详细信息，请在右窗格中导航到 "通用 Windows 平台开发" 部分下的 "安装详细信息"。</span><span class="sxs-lookup"><span data-stu-id="91914-121">For more information,  navigate to Installation Details under the Universal Windows Platform development section, on the right pane.</span></span>  
        
1.  <span data-ttu-id="91914-122">确保你的系统已为 [nuget.org][NugetHome]启用 NuGet 程序包源。 有关详细信息，请导航到 [常见的 NuGet 配置][NugetConsumePackagesConfiguringNugetBehavior] 和 [Windows 社区工具包][WindowsCommunitytoolkit]。</span><span class="sxs-lookup"><span data-stu-id="91914-122">Make sure your system has a NuGet package source enabled for [nuget.org][NugetHome].  For more information, navigate to [Common NuGet configurations][NugetConsumePackagesConfiguringNugetBehavior] and [Windows Community Toolkit][WindowsCommunitytoolkit].</span></span>  
1.  <span data-ttu-id="91914-123">下载并安装 [WinUI 3 预览版 3 VSIX 程序包][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]。</span><span class="sxs-lookup"><span data-stu-id="91914-123">Download and install the [WinUI 3 Preview 3 VSIX package][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates].</span></span>  <span data-ttu-id="91914-124">安装程序将 WinUI 3 项目模板和包含 WinUI 3 库的 NuGet 包添加到 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="91914-124">The installer adds both the WinUI 3 project templates and the NuGet package containing the WinUI 3 libraries to Visual Studio 2019.</span></span>  
    
    <span data-ttu-id="91914-125">有关如何将 VSIX 包添加到 Visual Studio 的说明，请导航到 [查找和使用 Visual Studio 扩展][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]。</span><span class="sxs-lookup"><span data-stu-id="91914-125">For instructions on how to add the VSIX package to Visual Studio, navigate to [Finding and Using Visual Studio Extensions][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox].</span></span>
    
1.  <span data-ttu-id="91914-126">启用 [开发人员模式][WindowsUwpGetStartedEnableYourDeviceForDevelopment] ，以确保你有权访问所有开发人员特定的 Visual Studio 功能。</span><span class="sxs-lookup"><span data-stu-id="91914-126">Enable [Developer Mode][WindowsUwpGetStartedEnableYourDeviceForDevelopment] to ensure you have access to all developer-specific Visual Studio features.</span></span>  
    
## <span data-ttu-id="91914-127">步骤 1-创建项目</span><span class="sxs-lookup"><span data-stu-id="91914-127">Step 1 - Create Project</span></span>  

<span data-ttu-id="91914-128">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="91914-128">Start with a basic desktop project containing a single main window.</span></span>  

1.  <span data-ttu-id="91914-129">在 Visual Studio 中，选择 " **创建新项目**"。</span><span class="sxs-lookup"><span data-stu-id="91914-129">In Visual Studio, choose **Create a new project**.</span></span>  
1.  <span data-ttu-id="91914-130">在 "项目" 下拉列表中，分别选择 " **c #**"、" **Windows**" 和 " **WinUI** "。</span><span class="sxs-lookup"><span data-stu-id="91914-130">In the project drop-down, choose **C#**, **Windows**, and **WinUI** respectively.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="使用 Visual Studio 创建新的 WinUI 项目" lightbox="./media/winui-gettingstarted-selections.png":::
        <span data-ttu-id="91914-132">使用 Visual Studio 创建新的 WinUI 项目</span><span class="sxs-lookup"><span data-stu-id="91914-132">Create a new WinUI project using Visual Studio</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="91914-133">**在桌面) 中选择 "空白应用"、"打包 (WinUI **"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="91914-133">Choose **Blank App, Packaged (WinUI in Desktop)**, and then choose **Next**.</span></span>  
1.  <span data-ttu-id="91914-134">输入项目名称，选择所需的其他选项，然后选择 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="91914-134">Enter a project name, choose other options as needed, and then choose **Create**.</span></span>  
1.  <span data-ttu-id="91914-135">在 **新的通用 Windows 平台项目**中，选择以下值，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="91914-135">In **New Universal Windows Platform Project**, choose the following values, and then choose **OK**.</span></span>  
    *   <span data-ttu-id="91914-136">**目标版本**：  \*\*Windows 10 版本 1903 (内部版本 18362) \*\* 或更高版本</span><span class="sxs-lookup"><span data-stu-id="91914-136">**Target version**:  **Windows 10, version 1903 (build 18362)** or later</span></span>  
    *   <span data-ttu-id="91914-137">**最低版本**：  \*\*Windows 10 版本 1803 (内部版本 17134) \*\*</span><span class="sxs-lookup"><span data-stu-id="91914-137">**Minimum version**:  **Windows 10, version 1803 (build 17134)**</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="新的通用 Windows 平台项目对话框，其中包含目标版本和最低版本的所选值。" lightbox="./media/winui-gettingstarted-projecttype.png":::
       <span data-ttu-id="91914-139">新的通用 Windows 平台项目对话框，其中包含目标版本和最低版本的所选值。</span><span class="sxs-lookup"><span data-stu-id="91914-139">The New Universal Windows Platform Project dialog with chosen values for Target version and Minimum version.</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="91914-140">在 "解决方案资源管理器" 中，生成两个项目。</span><span class="sxs-lookup"><span data-stu-id="91914-140">In the Solution Explorer, two projects are generated.</span></span>  
    *   <span data-ttu-id="91914-141">\*\*你的项目名称 (桌面) \*\*。</span><span class="sxs-lookup"><span data-stu-id="91914-141">**Your project name (Desktop)**.</span></span>  <span data-ttu-id="91914-142">此项目包含你的应用的代码。</span><span class="sxs-lookup"><span data-stu-id="91914-142">This project contains the code for your app.</span></span>  <span data-ttu-id="91914-143">**App.xaml.cs** 定义一个 `Application` 表示你的应用实例的类。</span><span class="sxs-lookup"><span data-stu-id="91914-143">**App.xaml.cs** defines an `Application` class that represents your app instance.</span></span>  <span data-ttu-id="91914-144">**MainWindow.xaml.cs** 定义一个 `MainWindow` 类，该类表示你的应用实例显示的主窗口。</span><span class="sxs-lookup"><span data-stu-id="91914-144">**MainWindow.xaml.cs** defines a `MainWindow` class that represents the main window displayed by your app instance.</span></span>  <span data-ttu-id="91914-145">这些类派生自 `Microsoft.UI.Xaml` WinUI 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="91914-145">These classes derive from types in the `Microsoft.UI.Xaml` namespace of WinUI.</span></span>  
    
    *   <span data-ttu-id="91914-146">\*\*项目名称 (程序包) \*\*。</span><span class="sxs-lookup"><span data-stu-id="91914-146">**Your project name (Package)**.</span></span>  <span data-ttu-id="91914-147">此项目是一个 Windows 应用程序打包项目，该项目配置为将应用构建到 MSIX 程序包中以进行部署。</span><span class="sxs-lookup"><span data-stu-id="91914-147">This project is a Windows Application Packaging Project that is configured to build the app into an MSIX package for deployment.</span></span>  <span data-ttu-id="91914-148">该项目包含你的应用的程序包清单，并且默认情况下它是你的解决方案的启动项目。</span><span class="sxs-lookup"><span data-stu-id="91914-148">The project contains the package manifest for your app, and it is the startup project for your solution by default.</span></span>  <span data-ttu-id="91914-149">有关详细信息，请导航到 [在 Visual Studio 中设置适用于 MSIX 打包的桌面应用程序][WindowsMsixDesktopToUwpPackagingDotNet] 和 [适用于 Windows 10 的程序包清单架构参考][UwpSchemasAppxpackageUapmanifestRoot]。</span><span class="sxs-lookup"><span data-stu-id="91914-149">For more information, navigate to [Set up your desktop application for MSIX packaging in Visual Studio][WindowsMsixDesktopToUwpPackagingDotNet] and [Package manifest schema reference for Windows 10][UwpSchemasAppxpackageUapmanifestRoot].</span></span>
    
1.  <span data-ttu-id="91914-150">在 "解决方案资源管理器" 中，若要显示代码，请打开 " `MainWindow.xaml` 文件"。</span><span class="sxs-lookup"><span data-stu-id="91914-150">In the Solution Explorer, to display the code, open `MainWindow.xaml` file.</span></span>  <span data-ttu-id="91914-151">选择 `F5` 以运行你的项目，并显示一个带有按钮的窗口。</span><span class="sxs-lookup"><span data-stu-id="91914-151">Select `F5` to run your project and show a window with a button.</span></span>  
    
## <span data-ttu-id="91914-152">步骤 2-将 WebView2 控件添加到你的项目</span><span class="sxs-lookup"><span data-stu-id="91914-152">Step 2 - Add a WebView2 control to your project</span></span>  

<span data-ttu-id="91914-153">接下来，将 WebView2 控件添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="91914-153">Next add a WebView2 control to your project.</span></span>  

1.  <span data-ttu-id="91914-154">打开 `MainWindow.xaml`。</span><span class="sxs-lookup"><span data-stu-id="91914-154">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="91914-155">通过在标记内插入以下行来添加 WebView2 XAML 命名空间 `<Window/>` 。</span><span class="sxs-lookup"><span data-stu-id="91914-155">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    <span data-ttu-id="91914-156">确认中的代码 `MainWindow.xaml` 与以下代码片段类似。</span><span class="sxs-lookup"><span data-stu-id="91914-156">Confirm that your code in `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="91914-157">若要添加 WebView2 控件，请将 `<StackPanel>` 标记替换为以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="91914-157">To add the WebView2 control, replace the `<StackPanel>` tags with the following code snippet.</span></span>  <span data-ttu-id="91914-158">该 `Source` 属性设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="91914-158">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
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
    
1.  <span data-ttu-id="91914-159">打开 `MainWindow.xaml.cs` 并注释掉以下行。</span><span class="sxs-lookup"><span data-stu-id="91914-159">Open `MainWindow.xaml.cs` and comment out the following line.</span></span>
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  <span data-ttu-id="91914-160">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="91914-160">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="91914-161">确认你的 WebView2 控件是否显示 [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="91914-161">Confirm that your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="显示 microsoft.com 网站的 WebView2 控件" lightbox="./media/winui-gettingstarted-part3.png":::
       <span data-ttu-id="91914-163">显示 microsoft.com 网站的 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="91914-163">A WebView2 control displaying the microsoft.com site.</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="91914-164">步骤 3-添加导航控件</span><span class="sxs-lookup"><span data-stu-id="91914-164">Step 3 - Add navigation controls</span></span>  

<span data-ttu-id="91914-165">通过向应用添加地址栏，允许用户控制 WebView2 控件中显示的网页。</span><span class="sxs-lookup"><span data-stu-id="91914-165">Allow users to control the web page that is displayed in your WebView2 control by adding an address bar to your app.</span></span>  

1.  <span data-ttu-id="91914-166">在中 `MainWindow.xaml` ，将以下代码片段复制并粘贴到 `Grid` 包含该元素的元素内 `WebView2` 。</span><span class="sxs-lookup"><span data-stu-id="91914-166">In `MainWindow.xaml`, copy and paste the following code snippet inside the `Grid` element that contains the `WebView2` element.</span></span>  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    <span data-ttu-id="91914-167">确认你 `Grid` 的元素 `MainWindow.xaml` 类似于以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="91914-167">Confirm that your `Grid` element of `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="91914-168">在中 `MainWindow.xaml.cs` ，将以下代码片段复制到，该代码片段将 `myButton_Click` WebView2 控件导航到在地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="91914-168">In `MainWindow.xaml.cs`, copy the following code snippet to `myButton_Click`, which navigates the WebView2 control to the URL entered in the address bar.</span></span>  
    
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
    
    <span data-ttu-id="91914-169">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="91914-169">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="91914-170">在地址栏中输入新的 URL，然后选择 " **转到**"。</span><span class="sxs-lookup"><span data-stu-id="91914-170">Enter a new URL in the address bar, and then choose **Go**.</span></span>  <span data-ttu-id="91914-171">例如，enter `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="91914-171">For example, enter `https://www.bing.com`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="91914-172">确保在地址栏中使用完整的 Url。</span><span class="sxs-lookup"><span data-stu-id="91914-172">Ensure you use complete URLs in the address bar.</span></span>  `ArgumentException` <span data-ttu-id="91914-173">如果 URL 不以 or 开头，将引发异常 `http://` `https://` 。</span><span class="sxs-lookup"><span data-stu-id="91914-173">exceptions are thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="Bing.com" lightbox="./media/winui-gettingstarted-bing.png":::
       <span data-ttu-id="91914-175">Bing.com</span><span class="sxs-lookup"><span data-stu-id="91914-175">Bing.com</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="91914-176">步骤 4-导航事件</span><span class="sxs-lookup"><span data-stu-id="91914-176">Step 4 - Navigation events</span></span>  

<span data-ttu-id="91914-177">承载 WebView2 控件的应用程序侦听网页导航期间 WebView2 控件引发的以下事件。</span><span class="sxs-lookup"><span data-stu-id="91914-177">Applications that host WebView2 controls listen for the following events that are raised by WebView2 controls during web page navigation.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> <span data-ttu-id="91914-178">HTTP 重定向引发多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="91914-178">HTTP redirects raise multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="91914-179">有关详细信息，请导航到 [导航事件][Webviews2ConceptsNavigationEvents]。</span><span class="sxs-lookup"><span data-stu-id="91914-179">For more information, navigate to [Navigation Events][Webviews2ConceptsNavigationEvents].</span></span>  

<span data-ttu-id="91914-180">发生错误时，将引发以下事件，并且可能会导航到错误页面。</span><span class="sxs-lookup"><span data-stu-id="91914-180">When errors occur, the following events are raised and may navigate to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
<span data-ttu-id="91914-181">作为如何使用事件的示例，注册该程序的处理程序将 `NavigationStarting` 取消任何不使用 HTTPS 的请求。</span><span class="sxs-lookup"><span data-stu-id="91914-181">As an example of how to use the events, register a handler for `NavigationStarting` that cancels any request that does not use HTTPS.</span></span>  <span data-ttu-id="91914-182">在中 `MainWindow.xaml.cs` ，修改要注册的构造函数 `EnsureHttps` ，并添加 `EnsureHttps` 函数以使其与以下代码片段匹配。</span><span class="sxs-lookup"><span data-stu-id="91914-182">In `MainWindow.xaml.cs`, modify the constructor to register `EnsureHttps`, and add the `EnsureHttps` function so that it matches the following code snippet.</span></span>  

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

<span data-ttu-id="91914-183">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="91914-183">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="91914-184">确认对 HTTP 站点的导航已被阻止，并且对于 HTTPS 站点是允许的。</span><span class="sxs-lookup"><span data-stu-id="91914-184">Confirm that navigation is blocked to HTTP sites, and allowed for HTTPS sites.</span></span>  

## <span data-ttu-id="91914-185">步骤 5-脚本</span><span class="sxs-lookup"><span data-stu-id="91914-185">Step 5 - Scripting</span></span>  

<span data-ttu-id="91914-186">宿主应用程序可能会在运行时将 JavaScript 代码注入 WebView2 控件中。</span><span class="sxs-lookup"><span data-stu-id="91914-186">Host applications may inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="91914-187">插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="91914-187">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="91914-188">插入的 JavaScript 在特定计时中运行。</span><span class="sxs-lookup"><span data-stu-id="91914-188">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="91914-189">在创建全局对象后运行它。</span><span class="sxs-lookup"><span data-stu-id="91914-189">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="91914-190">在运行 HTML 文档中包含的任何其他脚本之前运行它。</span><span class="sxs-lookup"><span data-stu-id="91914-190">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="91914-191">例如，当用户导航到非 HTTPS 网站时，添加脚本会发送警报。</span><span class="sxs-lookup"><span data-stu-id="91914-191">As an example, add scripts send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="91914-192">修改该 `EnsureHttps` 函数以将脚本插入到使用 [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]的 web 内容中。</span><span class="sxs-lookup"><span data-stu-id="91914-192">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync].</span></span>  

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

<span data-ttu-id="91914-193">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="91914-193">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="91914-194">确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。</span><span class="sxs-lookup"><span data-stu-id="91914-194">Confirm that your application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="显示警报对话框的 WebView2 控件" lightbox="./media/winui-gettingstarted-script.png":::
   <span data-ttu-id="91914-196">显示警报对话框的 WebView2 控件</span><span class="sxs-lookup"><span data-stu-id="91914-196">WebView2 control showing an alert dialog</span></span>
:::image-end:::  

<span data-ttu-id="91914-197">恭喜，你已构建了你的第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="91914-197">Congratulations, you built your first WebView2 app.</span></span>  

## <span data-ttu-id="91914-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="91914-198">Next Steps</span></span>  

<span data-ttu-id="91914-199">我们的团队当前正在构建更多 WebView2 Api。</span><span class="sxs-lookup"><span data-stu-id="91914-199">Our team is currently building more WebView2 APIs.</span></span>  <span data-ttu-id="91914-200">有关 WebView2 Api 的当前状态的详细信息，请导航到 [WebView2 规范][GithubMicrosoftUiXamlSpecsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="91914-200">For more information on the current state of WebView2 APIs, navigate to the [WebView2 spec][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

> [!NOTE]
> <span data-ttu-id="91914-201">在 WebView2 Api 提供时，WinRT CoreWebView2 对象可能不可用。</span><span class="sxs-lookup"><span data-stu-id="91914-201">The WinRT CoreWebView2 object may not be available at the time the WebView2 APIs ship.</span></span>  <span data-ttu-id="91914-202">若要了解哪些 Api 可用于 WebView2 控件，请导航到 [WebView2 规范][GithubMicrosoftUiXamlSpecsWebview2] ，获取可用 api 的列表。</span><span class="sxs-lookup"><span data-stu-id="91914-202">To understand which APIs are available to WebView2 controls, navigate to [WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] for a list of the APIs that are available.</span></span>  

<span data-ttu-id="91914-203">有关 WebView2 功能的详细信息，请导航到 [WebView2 概念和 How-To 指南][Webview2IndexNextSteps] 和 [WebView2 示例][GithubMicrosoftedgeWebview2samplesMain]存储库。</span><span class="sxs-lookup"><span data-stu-id="91914-203">For more information about WebView2 capabilities, navigate to [WebView2 Concepts and How-To guides][Webview2IndexNextSteps] and the [WebView2 samples repo][GithubMicrosoftedgeWebview2samplesMain].</span></span>  

## <span data-ttu-id="91914-204">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="91914-204">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  
[Webview2IndexNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件 |Microsoft 文档"  
[Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法 (WebView2) |Microsoft 文档"  

[NugetConsumePackagesConfiguringNugetBehavior]: /nuget/consume-packages/configuring-nuget-behavior "常见 NuGet 配置 |Microsoft 文档"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "适用于 Windows 10 的程序包清单架构参考 |Microsoft 文档"  

[VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]: /visualstudio/ide/finding-and-using-visual-studio-extensions#install-without-using-the-manage-extensions-dialog-box "不使用 "管理扩展" 对话框进行安装-管理 Visual Studio 的扩展 |Microsoft 文档"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "配置你的开发环境-Windows UI 库3.0 预览版 1 (2020) |Microsoft 文档"  
[WindowsCommunitytoolkit]: /windows/communitytoolkit "Windows 社区工具包文档 |Microsoft 文档"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "在 Visual Studio 中设置用于 MSIX 打包的桌面应用程序 |Microsoft 文档"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "启用设备进行开发 |Microsoft 文档"  

[GithubMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 规范-microsoft/microsoft-xaml-规格 |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Word"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows 更新：常见问题"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[NugetHome]: https://nuget.org "开始 |NuGet 库"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "下载 dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe " dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]: https://marketplace.visualstudio.com/items?itemName=Microsoft-WinUI.WinUIProjectTemplates "WinUI 3 项目模板 |Visual Studio Marketplace"  
