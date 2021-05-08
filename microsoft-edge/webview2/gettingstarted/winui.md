---
description: 适用于 WinUI 应用的 WebView2 入门指南
title: WinUI 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、winui 应用、winui、edge、CoreWebView2、浏览器控件、edge html、入门、入门、.NET
ms.openlocfilehash: 8ecc40a1940bfb656e2dfdc7ab6f57effa90717d
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536337"
---
# <a name="getting-started-with-webview2-in-winui-3-preview"></a><span data-ttu-id="65634-104">WinUI 3 预览版中的 WebView2 (入门) </span><span class="sxs-lookup"><span data-stu-id="65634-104">Getting started with WebView2 in WinUI 3 (Preview)</span></span>  

<span data-ttu-id="65634-105">本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="65634-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="65634-106">你的第一个 WebView2 应用使用 WinUI3。</span><span class="sxs-lookup"><span data-stu-id="65634-106">Your first WebView2 app uses WinUI3.</span></span>  <span data-ttu-id="65634-107">有关各个 API 的信息，请导航到 [API 参考][GithubMicrosoftMicrosoftUiXamlSpecsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="65634-107">For more information on individual APIs, navigate to [API reference][GithubMicrosoftMicrosoftUiXamlSpecsWebview2].</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="65634-108">必备条件</span><span class="sxs-lookup"><span data-stu-id="65634-108">Prerequisites</span></span>  

<span data-ttu-id="65634-109">请确保先安装以下先决条件列表，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="65634-109">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="65634-110">[WebView2][Webview2Installer]运行时Microsoft Edge (Chromium) [][MicrosoftedgeinsiderDownload]安装在 Windows 10 版本 1803 \ (版本 17134\) 或更高版本上的非稳定通道。</span><span class="sxs-lookup"><span data-stu-id="65634-110">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on Windows 10 version 1803 \(build 17134\) or later.</span></span>  <span data-ttu-id="65634-111">有关更新Windows 10，请导航到Windows[更新：常见问题解答][MicrosoftSupport12373]。</span><span class="sxs-lookup"><span data-stu-id="65634-111">For more information about Windows 10, navigate to [Windows Update: FAQ][MicrosoftSupport12373].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="65634-112">WebView 团队建议使用 Canary 通道，最低要求版本为 82.0.488.0。</span><span class="sxs-lookup"><span data-stu-id="65634-112">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="65634-113">[Visual Studio][MicrosoftVisualstudioMain] 2019 版本 16.9 预览版。</span><span class="sxs-lookup"><span data-stu-id="65634-113">[Visual Studio][MicrosoftVisualstudioMain] 2019, version 16.9 Preview.</span></span>  <span data-ttu-id="65634-114">有关详细信息，请导航到["Windows UI 库 3 预览版 3"。][WindowsAppsWinui3ConfigureYourDevEnvironment]</span><span class="sxs-lookup"><span data-stu-id="65634-114">For more information, navigate to [Windows UI Library 3 Preview 3][WindowsAppsWinui3ConfigureYourDevEnvironment].</span></span>  
    *   <span data-ttu-id="65634-115">安装客户端时，请包含Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="65634-115">Include the following workloads when you install Visual Studio.</span></span>  
        *   <span data-ttu-id="65634-116">.NET 桌面开发 \ (安装程序还会安装 .NET 5\) </span><span class="sxs-lookup"><span data-stu-id="65634-116">.NET Desktop Development \(the installer also installs .NET 5\)</span></span>  
        *   <span data-ttu-id="65634-117">通用 Windows 平台开发</span><span class="sxs-lookup"><span data-stu-id="65634-117">Universal Windows Platform development</span></span>  
    *   <span data-ttu-id="65634-118">若要生成 C++ 应用，还必须包括以下工作负载。</span><span class="sxs-lookup"><span data-stu-id="65634-118">To build C++ apps, you must also include the following workloads.</span></span>  
        *   <span data-ttu-id="65634-119">使用 C++ 进行桌面开发</span><span class="sxs-lookup"><span data-stu-id="65634-119">Desktop development with C++</span></span>  
        *   <span data-ttu-id="65634-120">通用 (平台工作负载的 C++ \ (v142\) Windows 通用 Windows 平台工具可选组件。</span><span class="sxs-lookup"><span data-stu-id="65634-120">The C++ \(v142\) Universal Windows Platform tools optional component for the Universal Windows Platform workload.</span></span>  <span data-ttu-id="65634-121">有关详细信息，请**导航到右**窗格中"通用 Windows**平台**开发"部分下的"安装详细信息"。</span><span class="sxs-lookup"><span data-stu-id="65634-121">For more information,  navigate to **Installation Details** under the **Universal Windows Platform development** section, on the right pane.</span></span>  
        
## <a name="step-0---visual-studio-settings"></a><span data-ttu-id="65634-122">步骤 0 - Visual Studio设置</span><span class="sxs-lookup"><span data-stu-id="65634-122">Step 0 - Visual Studio settings</span></span>  

1.  <span data-ttu-id="65634-123">确保你的系统已启用NuGet[包源][NugetHome]nuget.org。 有关详细信息，请导航到 Common [NuGet configurations][NugetConsumePackagesConfiguringNugetBehavior] and [Windows Community Toolkit][WindowsCommunitytoolkit]。</span><span class="sxs-lookup"><span data-stu-id="65634-123">Ensure your system has a NuGet package source enabled for [nuget.org][NugetHome].  For more information, navigate to [Common NuGet configurations][NugetConsumePackagesConfiguringNugetBehavior] and [Windows Community Toolkit][WindowsCommunitytoolkit].</span></span>  
1.  <span data-ttu-id="65634-124">下载并安装 [WinUI 3 Preview 3 VSIX 程序包][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]。</span><span class="sxs-lookup"><span data-stu-id="65634-124">Download and install the [WinUI 3 Preview 3 VSIX package][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates].</span></span>  <span data-ttu-id="65634-125">安装程序将 WinUI 3 项目模板和包含 WinUI 3 库的 NuGet 包添加到 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="65634-125">The installer adds both the WinUI 3 project templates and the NuGet package containing the WinUI 3 libraries to Visual Studio 2019.</span></span>  
    
    <span data-ttu-id="65634-126">有关如何将程序包添加到应用 `VSIX` Visual Studio，请导航到查找和使用Visual Studio[扩展。][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]</span><span class="sxs-lookup"><span data-stu-id="65634-126">For instructions on how to add the `VSIX` package to Visual Studio, navigate to [Finding and Using Visual Studio Extensions][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox].</span></span>
    
1.  <span data-ttu-id="65634-127">若要访问开发人员特定的所有Visual Studio功能，请打开开发人员[模式][WindowsUwpGetStartedEnableYourDeviceForDevelopment]。</span><span class="sxs-lookup"><span data-stu-id="65634-127">To access all developer-specific Visual Studio features, turn on [Developer Mode][WindowsUwpGetStartedEnableYourDeviceForDevelopment].</span></span>  
    
## <a name="step-1---create-project"></a><span data-ttu-id="65634-128">步骤 1 - 创建Project</span><span class="sxs-lookup"><span data-stu-id="65634-128">Step 1 - Create Project</span></span>  

<span data-ttu-id="65634-129">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="65634-129">Start with a basic desktop project that contains a single main window.</span></span>  

1.  <span data-ttu-id="65634-130">在Visual Studio中，选择 **"新建项目"。**</span><span class="sxs-lookup"><span data-stu-id="65634-130">In Visual Studio, choose **Create a new project**.</span></span>  
1.  <span data-ttu-id="65634-131">在项目下拉列表中，分别选择**C#、Windows**和\*\*\*\*\*\*WinUI。\*\*</span><span class="sxs-lookup"><span data-stu-id="65634-131">In the project drop-down, choose **C#**, **Windows**, and **WinUI** respectively.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="使用项目创建一个新的 WinUI Visual Studio" lightbox="./media/winui-gettingstarted-selections.png":::
        <span data-ttu-id="65634-133">使用项目创建一个新的 WinUI Visual Studio</span><span class="sxs-lookup"><span data-stu-id="65634-133">Create a new WinUI project using Visual Studio</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="65634-134">Choose \*\*Blank App， Packaged (WinUI in Desktop) \*\*  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="65634-134">Choose **Blank App, Packaged (WinUI in Desktop)** > **Next**.</span></span>  
1.  <span data-ttu-id="65634-135">输入项目名称。</span><span class="sxs-lookup"><span data-stu-id="65634-135">Enter a project name.</span></span>
1.  <span data-ttu-id="65634-136">根据需要选择选项。</span><span class="sxs-lookup"><span data-stu-id="65634-136">Choose options as needed.</span></span>  
1.  <span data-ttu-id="65634-137">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="65634-137">Choose **Create**.</span></span>  
1.  <span data-ttu-id="65634-138">在 **"新建通用Windows平台Project**中，选择以下值，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="65634-138">In **New Universal Windows Platform Project**, choose the following values, and then choose **OK**.</span></span>  
    *   <span data-ttu-id="65634-139">**目标版本\*\*\*\*：Windows 10版本 1903 (版本 18362**) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="65634-139">**Target version**:  **Windows 10, version 1903 (build 18362)** or later</span></span>  
    *   <span data-ttu-id="65634-140">\*\*最低版本\*\*\*\*：Windows 10版本 1803 (版本 17134) \*\*</span><span class="sxs-lookup"><span data-stu-id="65634-140">**Minimum version**:  **Windows 10, version 1803 (build 17134)**</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text=""新建通用Windows平台Project"对话框，包含"目标版本"和"最低版本"的选定值。" lightbox="./media/winui-gettingstarted-projecttype.png":::
       <span data-ttu-id="65634-142">"新建通用Windows平台Project"对话框，包含"目标版本"和"最低版本"的选定值。</span><span class="sxs-lookup"><span data-stu-id="65634-142">The New Universal Windows Platform Project dialog with chosen values for Target version and Minimum version.</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="65634-143">在"解决方案资源管理器"中，将生成两个项目。</span><span class="sxs-lookup"><span data-stu-id="65634-143">In the Solution Explorer, two projects are generated.</span></span>  
    *   <span data-ttu-id="65634-144">\*\*你的项目名称 (桌面) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="65634-144">**Your project name (Desktop)**.</span></span>  <span data-ttu-id="65634-145">桌面项目包含你的应用的代码。</span><span class="sxs-lookup"><span data-stu-id="65634-145">The Desktop project contains the code for your app.</span></span>  <span data-ttu-id="65634-146">`App.xaml.cs`该文件定义一个 `Application` 表示应用实例的类。</span><span class="sxs-lookup"><span data-stu-id="65634-146">The `App.xaml.cs` file defines an `Application` class that represents your app instance.</span></span>  <span data-ttu-id="65634-147">`MainWindow.xaml.cs`该文件定义一个 `MainWindow` 类，该类表示应用实例显示的主窗口。</span><span class="sxs-lookup"><span data-stu-id="65634-147">The `MainWindow.xaml.cs` file defines a `MainWindow` class that represents the main window displayed by your app instance.</span></span>  <span data-ttu-id="65634-148">这些类派生自 `Microsoft.UI.Xaml` WinUI 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="65634-148">The classes derive from types in the `Microsoft.UI.Xaml` namespace of WinUI.</span></span>  
    *   <span data-ttu-id="65634-149">\*\*你的项目名称 (包) \*\*。</span><span class="sxs-lookup"><span data-stu-id="65634-149">**Your project name (Package)**.</span></span>  <span data-ttu-id="65634-150">包项目是一Windows应用程序打包Project，配置为将应用构建到 MSIX 包中进行部署。</span><span class="sxs-lookup"><span data-stu-id="65634-150">The Package project is a Windows Application Packaging Project that is configured to build the app into an MSIX package for deployment.</span></span>  <span data-ttu-id="65634-151">该项目包含应用的程序包清单，并且默认情况下是解决方案的启动项目。</span><span class="sxs-lookup"><span data-stu-id="65634-151">The project contains the package manifest for your app, and is the startup project for your solution by default.</span></span>  <span data-ttu-id="65634-152">有关详细信息，请导航到在 Visual Studio 和程序包清单架构参考中为[MSIX][WindowsMsixDesktopToUwpPackagingDotNet]打包设置桌面[Windows 10。][UwpSchemasAppxpackageUapmanifestRoot]</span><span class="sxs-lookup"><span data-stu-id="65634-152">For more information, navigate to [Set up your desktop application for MSIX packaging in Visual Studio][WindowsMsixDesktopToUwpPackagingDotNet] and [Package manifest schema reference for Windows 10][UwpSchemasAppxpackageUapmanifestRoot].</span></span>  
1.  <span data-ttu-id="65634-153">在"解决方案资源管理器"中，若要显示代码，请打开 `MainWindow.xaml` 文件。</span><span class="sxs-lookup"><span data-stu-id="65634-153">In the Solution Explorer, to display the code, open the `MainWindow.xaml` file.</span></span>  <span data-ttu-id="65634-154">若要运行项目并显示带按钮的窗口，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="65634-154">To run your project and display a window with a button, select `F5`.</span></span>  
    
## <a name="step-2---add-a-webview2-control-to-your-project"></a><span data-ttu-id="65634-155">步骤 2 - 将 WebView2 控件添加到项目中</span><span class="sxs-lookup"><span data-stu-id="65634-155">Step 2 - Add a WebView2 control to your project</span></span>  

<span data-ttu-id="65634-156">将 WebView2 控件添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="65634-156">Add a WebView2 control to your project.</span></span>  

1.  <span data-ttu-id="65634-157">在 `MainWindow.xaml` 文件中，若要添加 WebView2 XAML 命名空间，在 标记内插入以下 `<Window/>` 行。</span><span class="sxs-lookup"><span data-stu-id="65634-157">In the `MainWindow.xaml` file, to add the WebView2 XAML namespace, insert the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    <span data-ttu-id="65634-158">确保 中的 `MainWindow.xaml` 代码类似于以下代码段。</span><span class="sxs-lookup"><span data-stu-id="65634-158">Ensure your code in `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="65634-159">若要添加 WebView2 控件，请将 `<StackPanel>` 标记替换为以下代码段。</span><span class="sxs-lookup"><span data-stu-id="65634-159">To add the WebView2 control, replace the `<StackPanel>` tags with the following code snippet.</span></span>  <span data-ttu-id="65634-160">属性 `Source` 设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="65634-160">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
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
    
1.  <span data-ttu-id="65634-161">在 `MainWindow.xaml.cs` 文件中，注释掉以下行。</span><span class="sxs-lookup"><span data-stu-id="65634-161">In the `MainWindow.xaml.cs` file, comment out the following line.</span></span>
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  <span data-ttu-id="65634-162">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="65634-162">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="65634-163">确保 WebView2 控件显示 [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="65634-163">Ensure your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="WebView2 控件显示 microsoft.com" lightbox="./media/winui-gettingstarted-part3.png":::
       <span data-ttu-id="65634-165">WebView2 控件显示 microsoft.com</span><span class="sxs-lookup"><span data-stu-id="65634-165">WebView2 control displays microsoft.com</span></span>  
    :::image-end:::  
    
## <a name="step-3---add-navigation-controls"></a><span data-ttu-id="65634-166">步骤 3 - 添加导航控件</span><span class="sxs-lookup"><span data-stu-id="65634-166">Step 3 - Add navigation controls</span></span>  

<span data-ttu-id="65634-167">若要允许用户控制 WebView2 控件中显示的网页，请向应用添加地址栏。</span><span class="sxs-lookup"><span data-stu-id="65634-167">To allow users to control the webpage that is displayed in your WebView2 control, add an address bar to your app.</span></span>  

1.  <span data-ttu-id="65634-168">在文件中，将以下代码段复制并粘贴 `MainWindow.xaml` 到包含 `<Grid>` 元素的元素 `WebView2` 中。</span><span class="sxs-lookup"><span data-stu-id="65634-168">In the `MainWindow.xaml` file, copy and paste the following code snippet inside the `<Grid>` element that contains the `WebView2` element.</span></span>  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    <span data-ttu-id="65634-169">确保 `<Grid>` 该文件中的 `MainWindow.xaml` 元素类似于以下代码段。</span><span class="sxs-lookup"><span data-stu-id="65634-169">Ensure your `<Grid>` element in the `MainWindow.xaml` file is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="65634-170">在 文件中，将以下代码段复制到 中，该代码段将 WebView2 控件导航到地址栏中 `MainWindow.xaml.cs` `myButton_Click` 输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="65634-170">In the `MainWindow.xaml.cs` file, copy the following code snippet into `myButton_Click`, which navigates the WebView2 control to the URL entered in the address bar.</span></span>  
    
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
    
    <span data-ttu-id="65634-171">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="65634-171">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="65634-172">在地址栏中输入新 URL，然后选择"转到 **"。**</span><span class="sxs-lookup"><span data-stu-id="65634-172">Enter a new URL in the address bar, and then choose **Go**.</span></span>  <span data-ttu-id="65634-173">例如，输入 `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="65634-173">For example, enter `https://www.bing.com`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="65634-174">确保在地址栏中输入完整 URL。</span><span class="sxs-lookup"><span data-stu-id="65634-174">Ensure you enter complete URLs in the address bar.</span></span>  `ArgumentException` <span data-ttu-id="65634-175">如果 URL 不以 或 为起始，则会引发 `http://` 异常 `https://` 。</span><span class="sxs-lookup"><span data-stu-id="65634-175">exceptions are thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="bing.com" lightbox="./media/winui-gettingstarted-bing.png":::
       <span data-ttu-id="65634-177">bing.com</span><span class="sxs-lookup"><span data-stu-id="65634-177">bing.com</span></span>  
    :::image-end:::  
    
## <a name="step-4---navigation-events"></a><span data-ttu-id="65634-178">步骤 4 - 导航事件</span><span class="sxs-lookup"><span data-stu-id="65634-178">Step 4 - Navigation events</span></span>  

<span data-ttu-id="65634-179">承载 WebView2 控件的应用侦听 WebView2 控件在网页导航过程中引发以下事件。</span><span class="sxs-lookup"><span data-stu-id="65634-179">Apps that host WebView2 controls listen for the following events that are raised by WebView2 controls during webpage navigation.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> <span data-ttu-id="65634-180">如果发生 HTTP 重定向，则一行 `NavigationStarting` 中有多个事件。</span><span class="sxs-lookup"><span data-stu-id="65634-180">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="65634-181">有关详细信息，请导航到["导航事件"。][Webviews2ConceptsNavigationEvents]</span><span class="sxs-lookup"><span data-stu-id="65634-181">For more information, navigate to [Navigation Events][Webviews2ConceptsNavigationEvents].</span></span>  

<span data-ttu-id="65634-182">发生错误时，将引发以下事件，并可能导航到错误网页。</span><span class="sxs-lookup"><span data-stu-id="65634-182">When errors occur, the following events are raised and may navigate to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
<span data-ttu-id="65634-183">作为如何使用事件的示例，请注册用于取消任何非 `NavigationStarting` HTTPS 请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="65634-183">As an example of how to use the events, register a handler for `NavigationStarting` that cancels any non-HTTPS requests.</span></span>  <span data-ttu-id="65634-184">在 `MainWindow.xaml.cs` 中，修改构造函数以注册 `EnsureHttps` ，并添加 `EnsureHttps` 函数，以便与以下代码段匹配。</span><span class="sxs-lookup"><span data-stu-id="65634-184">In `MainWindow.xaml.cs`, modify the constructor to register `EnsureHttps`, and add the `EnsureHttps` function so that it matches the following code snippet.</span></span>  

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

<span data-ttu-id="65634-185">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="65634-185">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="65634-186">确保阻止导航到 HTTP 网站，并且允许 HTTPS 网站导航。</span><span class="sxs-lookup"><span data-stu-id="65634-186">Ensure navigation is blocked to HTTP sites, and allowed for HTTPS sites.</span></span>  

## <a name="step-5---scripting"></a><span data-ttu-id="65634-187">步骤 5 - 脚本</span><span class="sxs-lookup"><span data-stu-id="65634-187">Step 5 - Scripting</span></span>  

<span data-ttu-id="65634-188">你可以在运行时使用主机应用将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="65634-188">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="65634-189">你可以任务 WebView 运行任意 JavaScript 或添加初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="65634-189">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="65634-190">在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。</span><span class="sxs-lookup"><span data-stu-id="65634-190">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="65634-191">注入的 JavaScript 以特定计时运行。</span><span class="sxs-lookup"><span data-stu-id="65634-191">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="65634-192">创建全局对象后运行它。</span><span class="sxs-lookup"><span data-stu-id="65634-192">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="65634-193">在运行 HTML 文档中包含的任何其他脚本之前运行它。</span><span class="sxs-lookup"><span data-stu-id="65634-193">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="65634-194">例如，添加在用户导航到非 HTTPS 网站时发送警报的脚本。</span><span class="sxs-lookup"><span data-stu-id="65634-194">As an example, add scripts that send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="65634-195">修改 `EnsureHttps` 函数以将脚本注入到使用 [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]的 Web 内容中。</span><span class="sxs-lookup"><span data-stu-id="65634-195">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync].</span></span>  

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

<span data-ttu-id="65634-196">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="65634-196">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="65634-197">确保应用在导航到任何非 HTTPS 网站时显示警报。</span><span class="sxs-lookup"><span data-stu-id="65634-197">Ensure your app displays an alert when you navigate to any non-HTTPS websites.</span></span>  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="WebView2 控件显示警报对话框" lightbox="./media/winui-gettingstarted-script.png":::
   <span data-ttu-id="65634-199">WebView2 控件显示警报对话框</span><span class="sxs-lookup"><span data-stu-id="65634-199">WebView2 control displays an alert dialog</span></span>
:::image-end:::  

<span data-ttu-id="65634-200">恭喜！你生成了第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="65634-200">Congratulations, you built your first WebView2 app.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="65634-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="65634-201">Next steps</span></span>  

<span data-ttu-id="65634-202">若要继续了解有关 WebView2 的更多内容，请导航到以下资源。</span><span class="sxs-lookup"><span data-stu-id="65634-202">To continue learning more about WebView2, navigate to the following resources.</span></span>  

*   <span data-ttu-id="65634-203">若要了解有关生成 WebView2 应用程序的信息，请导航到 [WebView2 开发最佳做法][WV2BestPractices]。</span><span class="sxs-lookup"><span data-stu-id="65634-203">To learn more about building WebView2 applications, navigate to [WebView2 development best practices][WV2BestPractices].</span></span>  
*   <span data-ttu-id="65634-204">有关 WebView2 功能的综合示例，请导航到 [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain]。</span><span class="sxs-lookup"><span data-stu-id="65634-204">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain].</span></span>  
*   <span data-ttu-id="65634-205">有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]</span><span class="sxs-lookup"><span data-stu-id="65634-205">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="65634-206">WinRT CoreWebView2 对象在发布 WebView2 API 时可能不可用。</span><span class="sxs-lookup"><span data-stu-id="65634-206">The WinRT CoreWebView2 object may not be available with the release of the WebView2 API.</span></span>  <span data-ttu-id="65634-207">若要了解哪些 API 可用于 WebView2 控件，请导航到 [WebView2 Spec，][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] 了解可用的 API 列表。</span><span class="sxs-lookup"><span data-stu-id="65634-207">To understand which APIs are available to WebView2 controls, navigate to [WebView2 Spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] for a list of the APIs that are available.</span></span>  
    
*   <span data-ttu-id="65634-208">有关 WebView2 API 的详细信息，请导航到 [WebView2 spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="65634-208">For detailed information about the WebView2 API, navigate to [WebView2 spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2].</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="65634-209">与 WebView 团队Microsoft Edge联系</span><span class="sxs-lookup"><span data-stu-id="65634-209">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<span data-ttu-id="65634-210">若要发送特定于 WinUI 的功能请求或 Bug，请导航到"问题[- microsoft/microsoft-ui-xaml"，][GithubMicrosoftMicrosoftUiXamlIssues]然后选择"**新问题"。**</span><span class="sxs-lookup"><span data-stu-id="65634-210">To send your WinUI-specific feature requests or bugs, navigate to [Issues - microsoft/microsoft-ui-xaml][GithubMicrosoftMicrosoftUiXamlIssues] and choose **New issue**.</span></span>  

<!-- links -->  
[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 开发最佳实践|Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: ../index.md "WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件|Microsoft Docs"  
[Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExeMicrosoft.Web.WebView2.Wpf () 方法 (cuteScriptAsync) |Microsoft Docs"  

[NugetConsumePackagesConfiguringNugetBehavior]: /nuget/consume-packages/configuring-nuget-behavior "常见NuGet配置|Microsoft Docs"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "程序包清单架构参考Windows 10 |Microsoft Docs"  

[VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]: /visualstudio/ide/finding-and-using-visual-studio-extensions#install-without-using-the-manage-extensions-dialog-box "无需使用&quot;管理扩展&quot;对话框安装 - 管理 Visual Studio |Microsoft Docs"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "配置开发环境 - Windows 2020 年 5 月 (UI 库 3.0 预览 1) |Microsoft Docs"  
[WindowsCommunitytoolkit]: /windows/communitytoolkit "Windows Community Toolkit文档|Microsoft Docs"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "将桌面应用程序设置为 MSIX 打包Visual Studio |Microsoft Docs"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "启用设备进行开发|Microsoft Docs"  

[GithubMicrosoftMicrosoftUiXamlIssues]: https://github.com/microsoft/microsoft-ui-xaml/issues "问题 - microsoft/microsoft-ui-xaml |GitHub"  
[GithubMicrosoftMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 规范 - microsoft/microsoft-ui-xaml-specs |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows更新：常见问题解答"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[NugetHome]: https://nuget.org "家庭|NuGet库"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "下载dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe " dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]: https://marketplace.visualstudio.com/items?itemName=Microsoft-WinUI.WinUIProjectTemplates "WinUI 3 Project模板|Visual StudioMarketplace"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序" 
