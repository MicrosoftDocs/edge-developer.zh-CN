---
description: 适用于 WinUI 应用的 WebView2 入门指南
title: WinUI 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、winui 应用、winui、edge、CoreWebView2、浏览器控件、edge html、入门、入门、.NET
ms.openlocfilehash: ad78c5e65af507031ddd510f4b21782fe00ae465
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535846"
---
# <a name="get-started-with-webview2-in-winui-3-preview"></a>WinUI 3 预览版中的 WebView2 (入门)   

本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。  你的第一个 WebView2 应用使用 WinUI3。  有关各个 API 的信息，请导航到 [API 参考][GithubMicrosoftMicrosoftUiXamlSpecsWebview2]。  

## <a name="prerequisites"></a>必备条件  

请确保先安装以下先决条件列表，然后再继续。  

*   [WebView2][Webview2Installer]运行时Microsoft Edge (Chromium) [][MicrosoftedgeinsiderDownload]安装在 Windows 10 版本 1803 \ (版本 17134\) 或更高版本上的非稳定通道。  有关更新Windows 10，请导航到Windows[更新：常见问题解答][MicrosoftSupport12373]。  
    
    > [!NOTE]
    > WebView 团队建议使用 Canary 通道，最低要求版本为 82.0.488.0。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2019 版本 16.9 预览版。  有关详细信息，请导航到["Windows UI 库 3 预览版 3"。][WindowsAppsWinui3ConfigureYourDevEnvironment]  
    *   安装客户端时，请包含Visual Studio。  
        *   .NET 桌面开发 \ (安装程序还会安装 .NET 5\)   
        *   通用 Windows 平台开发  
    *   若要生成 C++ 应用，还必须包括以下工作负载。  
        *   使用 C++ 进行桌面开发  
        *   通用 (平台工作负载的 C++ \ (v142\) Windows 通用 Windows 平台工具可选组件。  有关详细信息，请**导航到右**窗格中"通用 Windows**平台**开发"部分下的"安装详细信息"。  
        
## <a name="step-0---visual-studio-settings"></a>步骤 0 - Visual Studio设置  

1.  确保你的系统已启用NuGet[包源][NugetHome]nuget.org。 有关详细信息，请导航到 Common [NuGet configurations][NugetConsumePackagesConfiguringNugetBehavior] and [Windows Community Toolkit][WindowsCommunitytoolkit]。  
1.  下载并安装 [WinUI 3 Preview 3 VSIX 程序包][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]。  安装程序将 WinUI 3 项目模板和包含 WinUI 3 库的 NuGet 包添加到 Visual Studio 2019。  
    
    有关如何将程序包添加到应用 `VSIX` Visual Studio，请导航到查找和使用Visual Studio[扩展。][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]
    
1.  若要访问开发人员特定的所有Visual Studio功能，请打开开发人员[模式][WindowsUwpGetStartedEnableYourDeviceForDevelopment]。  
    
## <a name="step-1---create-project"></a>步骤 1 - 创建Project  

从包含单个主窗口的基本桌面项目开始。  

1.  在Visual Studio中，选择 **"新建项目"。**  
1.  在项目下拉列表中，分别选择**C#、Windows**和******WinUI。**  
    
    :::image type="complex" source="./media/winui-getting-started-selections.png" alt-text="使用项目创建一个新的 WinUI Visual Studio" lightbox="./media/winui-getting-started-selections.png":::
        使用项目创建一个新的 WinUI Visual Studio
    :::image-end:::  
    
1.  Choose **Blank App， Packaged (WinUI in Desktop) **  >  **Next**.  
1.  输入项目名称。
1.  根据需要选择选项。  
1.  选择“**创建**”。  
1.  在 **"新建通用Windows平台Project**中，选择以下值，然后选择"确定 **"。**  
    *   **目标版本****：Windows 10版本 1903 (版本 18362**) 或更高版本  
    *   **最低版本****：Windows 10版本 1803 (版本 17134) **  
        
    :::image type="complex" source="./media/winui-getting-started-project-type.png" alt-text=""新建通用Windows平台Project"对话框，包含"目标版本"和"最低版本"的选定值。" lightbox="./media/winui-getting-started-project-type.png":::
       "新建通用Windows平台Project"对话框，包含"目标版本"和"最低版本"的选定值。
    :::image-end:::  
    
1.  在"解决方案资源管理器"中，将生成两个项目。  
    *   **你的项目名称 (桌面) 。 **  桌面项目包含你的应用的代码。  `App.xaml.cs`该文件定义一个 `Application` 表示应用实例的类。  `MainWindow.xaml.cs`该文件定义一个 `MainWindow` 类，该类表示应用实例显示的主窗口。  这些类派生自 `Microsoft.UI.Xaml` WinUI 命名空间中的类型。  
    *   **你的项目名称 (包) **。  包项目是一Windows应用程序打包Project，配置为将应用构建到 MSIX 包中进行部署。  该项目包含应用的程序包清单，并且默认情况下是解决方案的启动项目。  有关详细信息，请导航到在 Visual Studio 和程序包清单架构参考中为[MSIX][WindowsMsixDesktopToUwpPackagingDotNet]打包设置桌面[Windows 10。][UwpSchemasAppxpackageUapmanifestRoot]  
1.  在"解决方案资源管理器"中，若要显示代码，请打开 `MainWindow.xaml` 文件。  若要运行项目并显示带按钮的窗口，请选择 `F5` 。  
    
## <a name="step-2---add-a-webview2-control-to-your-project"></a>步骤 2 - 将 WebView2 控件添加到项目中  

将 WebView2 控件添加到项目中。  

1.  在 `MainWindow.xaml` 文件中，若要添加 WebView2 XAML 命名空间，在 标记内插入以下 `<Window/>` 行。  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    确保 中的 `MainWindow.xaml` 代码类似于以下代码段。  
    
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
    
1.  若要添加 WebView2 控件，请将 `<StackPanel>` 标记替换为以下代码段。  属性 `Source` 设置 WebView2 控件中显示的初始 URI。  
    
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
    
1.  在 `MainWindow.xaml.cs` 文件中，注释掉以下行。
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  若要生成并运行项目，请选择 `F5` 。  确保 WebView2 控件显示 [https://www.microsoft.com][|::ref1::|Main] 。  
    
    :::image type="complex" source="./media/winui-getting-started-part-3.png" alt-text="WebView2 控件显示 microsoft.com" lightbox="./media/winui-getting-started-part-3.png":::
       WebView2 控件显示 microsoft.com  
    :::image-end:::  
    
## <a name="step-3---add-navigation-controls"></a>步骤 3 - 添加导航控件  

若要允许用户控制 WebView2 控件中显示的网页，请向应用添加地址栏。  

1.  在文件中，将以下代码段复制并粘贴 `MainWindow.xaml` 到包含 `<Grid>` 元素的元素 `WebView2` 中。  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    确保 `<Grid>` 该文件中的 `MainWindow.xaml` 元素类似于以下代码段。  
    
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
    
1.  在 文件中，将以下代码段复制到 中，该代码段将 WebView2 控件导航到地址栏中 `MainWindow.xaml.cs` `myButton_Click` 输入的 URL。  
    
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
    
    若要生成并运行项目，请选择 `F5` 。  在地址栏中输入新 URL，然后选择"转到 **"。**  例如，输入 `https://www.bing.com` 。  
    
    > [!NOTE]
    > 确保在地址栏中输入完整 URL。  `ArgumentException` 如果 URL 不以 或 为起始，则会引发 `http://` 异常 `https://` 。  
    
    :::image type="complex" source="./media/winui-getting-started-bing.png" alt-text="bing.com" lightbox="./media/winui-getting-started-bing.png":::
       bing.com  
    :::image-end:::  
    
## <a name="step-4---navigation-events"></a>步骤 4 - 导航事件  

承载 WebView2 控件的应用侦听 WebView2 控件在网页导航过程中引发以下事件。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  
    
> [!NOTE]
> 如果发生 HTTP 重定向，则一行 `NavigationStarting` 中有多个事件。  

有关详细信息，请导航到["导航事件"。][Webviews2ConceptsNavigationEvents]  

发生错误时，将引发以下事件，并可能导航到错误网页。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
    
作为如何使用事件的示例，请注册用于取消任何非 `NavigationStarting` HTTPS 请求的处理程序。  在 `MainWindow.xaml.cs` 中，修改构造函数以注册 `EnsureHttps` ，并添加 `EnsureHttps` 函数，以便与以下代码段匹配。  

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

若要生成并运行项目，请选择 `F5` 。  确保阻止导航到 HTTP 网站，并且允许 HTTPS 网站导航。  

## <a name="step-5---scripting"></a>步骤 5 - 脚本  

你可以在运行时使用主机应用将 JavaScript 代码注入 WebView2 控件。  你可以任务 WebView 运行任意 JavaScript 或添加初始化脚本。  在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。  注入的 JavaScript 以特定计时运行。  

*   创建全局对象后运行它。  
*   在运行 HTML 文档中包含的任何其他脚本之前运行它。  
    
例如，添加在用户导航到非 HTTPS 网站时发送警报的脚本。  修改 `EnsureHttps` 函数以将脚本注入到使用 [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]的 Web 内容中。  

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

若要生成并运行项目，请选择 `F5` 。  确保应用在导航到任何非 HTTPS 网站时显示警报。  

:::image type="complex" source="./media/winui-getting-started-script.png" alt-text="WebView2 控件显示警报对话框" lightbox="./media/winui-getting-started-script.png":::
   WebView2 控件显示警报对话框
:::image-end:::  

恭喜！你生成了第一个 WebView2 应用。  

## <a name="next-steps"></a>后续步骤  

若要继续了解有关 WebView2 的更多内容，请导航到以下资源。  

*   若要了解有关生成 WebView2 应用程序的信息，请导航到 [WebView2 开发最佳做法][WV2BestPractices]。  
*   有关 WebView2 功能的综合示例，请导航到 [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain]。  
*   有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]  
    
    > [!NOTE]
    > WinRT CoreWebView2 对象在发布 WebView2 API 时可能不可用。  若要了解哪些 API 可用于 WebView2 控件，请导航到 [WebView2 Spec，][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] 了解可用的 API 列表。  
    
*   有关 WebView2 API 的详细信息，请导航到 [WebView2 spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2]。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 WebView 团队Microsoft Edge联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

若要发送特定于 WinUI 的功能请求或 Bug，请导航到"问题[- microsoft/microsoft-ui-xaml"，][GithubMicrosoftMicrosoftUiXamlIssues]然后选择"**新问题"。**  

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
