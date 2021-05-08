---
description: 适用于 WPF 应用的 WebView2 入门指南
title: 适用于 WPF 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、wpf 应用、wpf、edge、CoreWebView2、浏览器控件、edge html、入门、入门、.NET
ms.openlocfilehash: e7ddb3977d34e8150a10354e638226bcf96d610d
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535854"
---
# <a name="get-started-with-webview2-in-wpf"></a>WPF 中的 WebView2 入门

本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。  有关各个 API 的信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2Wpf]。  

## <a name="prerequisites"></a>必备条件  

请确保先安装以下先决条件列表，然后再继续。  

*   [WebView2][Webview2Installer]运行时Microsoft Edge (Chromium) [][MicrosoftedgeinsiderDownload]安装在受支持的操作系统 \ (上的任意非稳定通道Windows 10、Windows 8.1和 Windows 7\) 。  
*   [Visual Studio][MicrosoftVisualstudioMain] 2017 或更高版本。  
    
## <a name="step-1---create-a-single-window-app"></a>步骤 1 - 创建单窗口应用  

从包含单个主窗口的基本桌面项目开始。  

1.  In Visual Studio， choose **WPF .NET Core App** \ (or **WPF .NET Framework App**\) > **Next**.  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-getting-started-wpf-core.png" alt-text="WPF 核心":::
             WPF 核心 :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-getting-started-wpf-fw.png" alt-text="WPF 框架":::
             WPF 框架 :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  输入 name 和**location Project****的值**。  选择 **.NET Framework 4.6.2**或更高版本 \ (**或 .NET Core 3.0**或更高版本\) 。  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-getting-started-create-core.png" alt-text="创建核心":::
             创建核心 :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-getting-started-create-fw.png" alt-text="创建框架":::
             创建框架 :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  若要创建项目，请选择"创建 **"。**  
    
## <a name="step-2---install-webview2-sdk"></a>步骤 2 - 安装 WebView2 SDK  

使用 NuGet 将 WebView2 SDK 添加到项目中。  

1.  将鼠标悬停在项目上，打开上下文菜单 \ (右键单击\) ，然后选择"管理NuGet**包..."。**  
    
    :::image type="complex" source="./media/wpf-getting-started-mng-nuget.png" alt-text="管理 NuGet 程序包" lightbox="./media/wpf-getting-started-mng-nuget.png":::
       管理 NuGet 程序包
    :::image-end:::
    
1.  在搜索栏中，键入"> `Microsoft.Web.WebView2` **选择"Microsoft.Web.WebView2"。**  
    
    :::image type="complex" source="./media/install-nuget.png" alt-text="NuGet" lightbox="./media/install-nuget.png":::
       NuGet  
    :::image-end:::
    
    准备好开始使用 WebView2 API 开发应用。  若要生成并运行项目，请选择 `F5` 。  正在运行的项目显示一个空窗口。  
    
    :::image type="complex" source="./media/winforms-empty-app.png" alt-text="空应用" lightbox="./media/winforms-empty-app.png":::
       空应用  
    :::image-end:::  
    
## <a name="step-3---create-a-single-webview"></a>步骤 3 - 创建单个 WebView 

接下来，将 WebView 添加到你的应用。  

1.  在 `MainWindow.xaml` 文件中，若要添加 WebView2 XAML 命名空间，在 标记内插入以下 `<Window/>` 行。  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    确保 中的代码 `MainWindow.xaml` 类似于以下代码段。  
    
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
    
1.  若要添加 WebView2 控件，请将 `<Grid>` 标记替换为以下代码段。  属性 `Source` 设置 WebView2 控件中显示的初始 URI。  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  若要生成并运行项目，请选择 `F5`  "确保 WebView2 控件显示 [https://www.microsoft.com][|::ref1::|Main] "。  
    
    :::image type="complex" source="./media/wpf-getting-started-microsoft.png" alt-text="Microsoft.com":::
       Microsoft.com
    :::image-end:::  
    
## <a name="step-4---navigation"></a>步骤 4 - 导航  

添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的能力。

1.  在 文件中，通过复制并粘贴包含 WebView 的 中的以下代码段 `MainWindow.xaml` `<DockPanel>` 来添加地址栏。  
    
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
    
    确保 `<DockPanel>` 文件的 `MainWindow.xaml` 部分与以下代码段匹配。  
    
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
    
1.  在Visual Studio中，若要添加命名空间，请将 `MainWindow.xaml.cs` `CoreWebView2` 以下代码段插入顶部。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  在文件中，复制以下代码段以创建 方法，该方法将 WebView 导航到地址栏中 `MainWindow.xaml.cs` `ButtonGo_Click` 输入的 URL。  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    若要生成并运行项目，请选择 `F5` 。  在地址栏中键入新 URL，然后选择"**转到"。**  例如，键入 `https://www.bing.com`。  确保 WebView2 控件导航到 URL。  
    
    > [!NOTE]
    > 确保在地址栏中输入完整 URL。  如果 `ArgumentException` URL 不以 或 为起始，则 `http://` 会引发 `https://` 。  
    
    :::image type="complex" source="./media/wpf-getting-started-bing.png" alt-text="必应":::
       bing.com
    :::image-end:::
    
## <a name="step-5---navigation-events"></a>步骤 5 - 导航事件  

在网页导航期间，WebView2 控件将引发事件。  承载 WebView2 控件的应用侦听以下事件。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  
    
有关详细信息，请导航到["导航事件"。][Webview2ConceptsNavigationEvents]  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   导航事件
:::image-end:::  

发生错误时，将引发以下事件，并可能依赖于导航到错误网页。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
    
> [!NOTE]
> 如果发生 HTTP 重定向，则一行 `NavigationStarting` 中有多个事件。  

若要演示如何使用事件，请注册用于取消任何非 `NavigationStarting` HTTPS 请求的处理程序。  

在 `MainWindow.xaml.cs` 文件中，修改构造函数以匹配以下代码段并添加 `EnsureHttps` 函数。  

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

在构造函数中 `EnsureHttps` ，注册为 WebView2 控件上事件 `NavigationStarting` 的事件处理程序。  

若要生成并运行项目，请选择 `F5` 。  确保导航到 HTTP 网站时，WebView 保持不变。  但是，WebView 导航到 HTTPS 网站。  

## <a name="step-6---scripting"></a>步骤 6 - 脚本  

你可以在运行时使用主机应用将 JavaScript 代码注入 WebView2 控件。  你可以任务 WebView 运行任意 JavaScript 或添加初始化脚本。  在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。  注入的 JavaScript 以特定计时运行。  

*   创建全局对象后运行它。  
*   在运行 HTML 文档中包含的任何其他脚本之前运行它。  
    
例如，添加在用户导航到非 HTTPS 网站时发送警报的脚本。  修改 `EnsureHttps` 函数以将脚本注入到使用 [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync) 方法的 Web 内容中。  

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

若要生成并运行项目，请选择 `F5` 。  当你导航到不使用 HTTPS 的网站时，请确保应用显示一个警报。  

:::image type="complex" source="./media/wpf-getting-started-https.png" alt-text="HTTPS":::
   HTTPS
:::image-end:::  

## <a name="step-7---communication-between-host-and-web-content"></a>步骤 7 - 主机和 Web 内容之间的通信  

主机和 Web 内容可能通过以下方式使用 进行通信 `postMessage` 。  

*   WebView2 控件中的 Web 内容可能会使用 向主机发布消息 `window.chrome.webview.postMessage` 。  主机使用主机上注册的任何消息 `WebMessageReceived` 处理邮件。  
*   使用 或 将消息张贴到 WebView2 控件中的 `CoreWebView2.PostWebMessageAsString` Web 内容 `CoreWebView2.PostWebMessageAsJSON` 。  消息被添加到 的处理程序捕获 `window.chrome.webview.addEventListener` 。  
    
通信机制使用本机功能将来自 Web 内容的消息传递给主机。  

在项目中，当 WebView2 控件导航到 URL 时，它会在地址栏中显示 URL，并通知用户 WebView2 控件中显示的 URL。  

1.  在 `MainWindow.xaml.cs` 文件中，更新构造函数并创建 `InitializeAsync` 一个函数以匹配以下代码段。  函数 `InitializeAsync` awaits [EnsureCoreWebView2Async，](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) 因为 的初始化 `CoreWebView2` 是异步的。  
    
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
    
1.  初始化 **CoreWebView2** 后，注册事件处理程序以响应 `WebMessageReceived` 。  在 `MainWindow.xaml.cs` 中 `InitializeAsync` ，使用下面的 `UpdateAddressBar` 代码段更新和添加。  
    
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
    
1.  为了使 WebView 能够发送和响应 Web 消息，在初始化后，主机 `CoreWebView2` ：  
    1.  将脚本注入 Web 内容，用于注册处理程序以从主机打印消息。  
    1.  将脚本注入到将 URL 张贴到主机的 Web 内容。  
        
    在 `MainWindow.xaml.cs` 文件中，进行更新 `InitializeAsync` 以匹配以下代码段。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    若要生成并运行应用，请选择 `F5` 。  现在，地址栏在 WebView2 控件中显示 URI。  当您成功导航到新的 URI 时，WebView2 控件会向 WebView2 控件中显示的 URI 的用户发出警报。  
    
    :::image type="complex" source="./media/wpf-getting-started-searchbar.png" alt-text="addressBar":::
       addressBar
    :::image-end:::
    
恭喜！你生成了第一个 WebView2 应用。  

## <a name="next-steps"></a>后续步骤  

若要继续了解有关 WebView2 的更多内容，请导航到以下资源。  

*   若要了解有关生成 WebView2 应用程序的信息，请导航到 [WebView2 开发最佳做法][WV2BestPractices]。  
*   有关 WebView2 功能的综合示例，请导航到[webView2Samples][GithubMicrosoftedgeWebview2samplesMain]存储库GitHub。  
*   有关 WebView2 API 的更多详细信息，请导航到 [API 参考](/dotnet/api/microsoft.web.webview2.wpf.webview2)。  
*   有关 WebView2 的信息，请导航到["WebView2 资源"。](../index.md#next-steps)  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 WebView 团队Microsoft Edge联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  
 
[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 开发最佳实践|Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async (CoreWebView2Environment) 方法|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 |Microsoft Edge开发人员"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualStudioMain]: https://visualstudio.microsoft.com "Microsoft Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序" 
