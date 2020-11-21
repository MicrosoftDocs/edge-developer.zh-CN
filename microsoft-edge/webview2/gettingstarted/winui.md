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
# WinUI 3 (预览中的 WebView2 入门)   

在本文中，了解如何创建你的第一个 WebView2 应用，以及有关 [Microsoft Edge WebView2 (Preview) ][Webview2Index]的主要功能。  你的第一个 WebView2 应用使用 WinUI3。  有关单个 Api 的详细信息，请导航到 [API 参考][GithubMicrosoftUiXamlSpecsWebview2]。  

## 必备条件  

请确保在继续下一篇文章之前安装以下先决条件列表。  

1.  Windows 10 版本 1803 \ (内部版本 17134 \ ) 或更高版本。  有关详细信息，请导航到 [Windows Update： FAQ][MicrosoftSupport12373]。  
1.  [Microsoft Edge (Chromium) ][MicrosoftedgeinsiderDownload] windows 10、windows 8.1 或 windows 7 上的 "" 通道。  
1.  Visual Studio 2019，版本16.9 预览版。  有关详细信息，请导航到 [WINDOWS UI 库3预览版 3][WindowsAppsWinui3ConfigureYourDevEnvironment]。  
    
    在安装 Visual Studio 时包括以下工作负荷。  
    
    *   .NET 桌面开发 \ (安装程序还会安装 .NET 5 \ )   
    *   通用 Windows 平台开发  
        
    若要构建 c + + 应用，还必须包含以下工作负荷。  
    
    *   带有 c + + 的桌面开发  
    *   C + + (v142 针对通用 Windows 平台工作负荷) 通用 Windows 平台工具可选组件。  有关详细信息，请在右窗格中导航到 "通用 Windows 平台开发" 部分下的 "安装详细信息"。  
        
1.  确保你的系统已为 [nuget.org][NugetHome]启用 NuGet 程序包源。 有关详细信息，请导航到 [常见的 NuGet 配置][NugetConsumePackagesConfiguringNugetBehavior] 和 [Windows 社区工具包][WindowsCommunitytoolkit]。  
1.  下载并安装 [WinUI 3 预览版 3 VSIX 程序包][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]。  安装程序将 WinUI 3 项目模板和包含 WinUI 3 库的 NuGet 包添加到 Visual Studio 2019。  
    
    有关如何将 VSIX 包添加到 Visual Studio 的说明，请导航到 [查找和使用 Visual Studio 扩展][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]。
    
1.  启用 [开发人员模式][WindowsUwpGetStartedEnableYourDeviceForDevelopment] ，以确保你有权访问所有开发人员特定的 Visual Studio 功能。  
    
## 步骤 1-创建项目  

从包含单个主窗口的基本桌面项目开始。  

1.  在 Visual Studio 中，选择 " **创建新项目**"。  
1.  在 "项目" 下拉列表中，分别选择 " **c #**"、" **Windows**" 和 " **WinUI** "。  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="使用 Visual Studio 创建新的 WinUI 项目" lightbox="./media/winui-gettingstarted-selections.png":::
        使用 Visual Studio 创建新的 WinUI 项目
    :::image-end:::  
    
1.  **在桌面) 中选择 "空白应用"、"打包 (WinUI **"，然后选择 "**下一步**"。  
1.  输入项目名称，选择所需的其他选项，然后选择 " **创建**"。  
1.  在 **新的通用 Windows 平台项目**中，选择以下值，然后选择 **"确定"**。  
    *   **目标版本**：  **Windows 10 版本 1903 (内部版本 18362) ** 或更高版本  
    *   **最低版本**：  **Windows 10 版本 1803 (内部版本 17134) **  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="新的通用 Windows 平台项目对话框，其中包含目标版本和最低版本的所选值。" lightbox="./media/winui-gettingstarted-projecttype.png":::
       新的通用 Windows 平台项目对话框，其中包含目标版本和最低版本的所选值。
    :::image-end:::  
    
1.  在 "解决方案资源管理器" 中，生成两个项目。  
    *   **你的项目名称 (桌面) **。  此项目包含你的应用的代码。  **App.xaml.cs** 定义一个 `Application` 表示你的应用实例的类。  **MainWindow.xaml.cs** 定义一个 `MainWindow` 类，该类表示你的应用实例显示的主窗口。  这些类派生自 `Microsoft.UI.Xaml` WinUI 命名空间中的类型。  
    
    *   **项目名称 (程序包) **。  此项目是一个 Windows 应用程序打包项目，该项目配置为将应用构建到 MSIX 程序包中以进行部署。  该项目包含你的应用的程序包清单，并且默认情况下它是你的解决方案的启动项目。  有关详细信息，请导航到 [在 Visual Studio 中设置适用于 MSIX 打包的桌面应用程序][WindowsMsixDesktopToUwpPackagingDotNet] 和 [适用于 Windows 10 的程序包清单架构参考][UwpSchemasAppxpackageUapmanifestRoot]。
    
1.  在 "解决方案资源管理器" 中，若要显示代码，请打开 " `MainWindow.xaml` 文件"。  选择 `F5` 以运行你的项目，并显示一个带有按钮的窗口。  
    
## 步骤 2-将 WebView2 控件添加到你的项目  

接下来，将 WebView2 控件添加到你的项目。  

1.  打开 `MainWindow.xaml`。  通过在标记内插入以下行来添加 WebView2 XAML 命名空间 `<Window/>` 。  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    确认中的代码 `MainWindow.xaml` 与以下代码片段类似。  
    
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
    
1.  若要添加 WebView2 控件，请将 `<StackPanel>` 标记替换为以下代码片段。  该 `Source` 属性设置 WebView2 控件中显示的初始 URI。  
    
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
    
1.  打开 `MainWindow.xaml.cs` 并注释掉以下行。
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  选择 `F5` 生成并运行项目。  确认你的 WebView2 控件是否显示 [https://www.microsoft.com][|::ref1::|Main] 。  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="显示 microsoft.com 网站的 WebView2 控件" lightbox="./media/winui-gettingstarted-part3.png":::
       显示 microsoft.com 网站的 WebView2 控件。  
    :::image-end:::  
    
## 步骤 3-添加导航控件  

通过向应用添加地址栏，允许用户控制 WebView2 控件中显示的网页。  

1.  在中 `MainWindow.xaml` ，将以下代码片段复制并粘贴到 `Grid` 包含该元素的元素内 `WebView2` 。  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    确认你 `Grid` 的元素 `MainWindow.xaml` 类似于以下代码片段。  
    
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
    
1.  在中 `MainWindow.xaml.cs` ，将以下代码片段复制到，该代码片段将 `myButton_Click` WebView2 控件导航到在地址栏中输入的 URL。  
    
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
    
    选择 `F5` 生成并运行项目。  在地址栏中输入新的 URL，然后选择 " **转到**"。  例如，enter `https://www.bing.com` 。  
    
    > [!NOTE]
    > 确保在地址栏中使用完整的 Url。  `ArgumentException` 如果 URL 不以 or 开头，将引发异常 `http://` `https://` 。  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="Bing.com" lightbox="./media/winui-gettingstarted-bing.png":::
       Bing.com  
    :::image-end:::  
    
## 步骤 4-导航事件  

承载 WebView2 控件的应用程序侦听网页导航期间 WebView2 控件引发的以下事件。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> HTTP 重定向引发多个 `NavigationStarting` 事件。  

有关详细信息，请导航到 [导航事件][Webviews2ConceptsNavigationEvents]。  

发生错误时，将引发以下事件，并且可能会导航到错误页面。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
作为如何使用事件的示例，注册该程序的处理程序将 `NavigationStarting` 取消任何不使用 HTTPS 的请求。  在中 `MainWindow.xaml.cs` ，修改要注册的构造函数 `EnsureHttps` ，并添加 `EnsureHttps` 函数以使其与以下代码片段匹配。  

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

选择 `F5` 生成并运行项目。  确认对 HTTP 站点的导航已被阻止，并且对于 HTTPS 站点是允许的。  

## 步骤 5-脚本  

宿主应用程序可能会在运行时将 JavaScript 代码注入 WebView2 控件中。  插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。  插入的 JavaScript 在特定计时中运行。  

*   在创建全局对象后运行它。  
*   在运行 HTML 文档中包含的任何其他脚本之前运行它。  

例如，当用户导航到非 HTTPS 网站时，添加脚本会发送警报。  修改该 `EnsureHttps` 函数以将脚本插入到使用 [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]的 web 内容中。  

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

选择 `F5` 生成并运行项目。  确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="显示警报对话框的 WebView2 控件" lightbox="./media/winui-gettingstarted-script.png":::
   显示警报对话框的 WebView2 控件
:::image-end:::  

恭喜，你已构建了你的第一个 WebView2 应用。  

## 后续步骤  

我们的团队当前正在构建更多 WebView2 Api。  有关 WebView2 Api 的当前状态的详细信息，请导航到 [WebView2 规范][GithubMicrosoftUiXamlSpecsWebview2]。  

> [!NOTE]
> 在 WebView2 Api 提供时，WinRT CoreWebView2 对象可能不可用。  若要了解哪些 Api 可用于 WebView2 控件，请导航到 [WebView2 规范][GithubMicrosoftUiXamlSpecsWebview2] ，获取可用 api 的列表。  

有关 WebView2 功能的详细信息，请导航到 [WebView2 概念和 How-To 指南][Webview2IndexNextSteps] 和 [WebView2 示例][GithubMicrosoftedgeWebview2samplesMain]存储库。  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

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
