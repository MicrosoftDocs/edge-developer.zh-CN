---
description: 在 WPF 应用中将 web 内容与 Microsoft Edge Web 视图2控件一起托管
title: 适用于 WPF 应用的 Microsoft Edge Web 视图2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/11/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、wpf 应用、wpf、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET
ms.openlocfilehash: 30736106906abe818ccec32e2935798d12ced0be
ms.sourcegitcommit: 4f8613ed7a33e3cbf822b6315d427af14774cd68
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2020
ms.locfileid: "10709892"
---
# WPF 中的 WebView2 入门（预览版）  

在本文中，开始创建你的第一个 WebView2 应用，并了解[WebView2 （预览版）](../index.md)的主要功能。  有关单个 Api 的详细信息，请参阅[API 参考](../reference/dotnet/0-9-515-reference-webview2.md)。  

## 必备条件  

请确保在继续之前安装了以下先决条件列表：  

* 安装在 Windows 10、Windows 8.1 或 Windows 7 上的[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download)的未安装频道。  
* [Visual Studio](https://visualstudio.microsoft.com/) 2017 或更高版本。  

## 步骤 1-创建单个窗口应用程序  

从包含单个主窗口的基本桌面项目开始。  

1.  打开**Visual Studio**。  
1.  选择 " **wpf .Net Core app** " 或 " **Wpf .net Framework 应用**"，然后选择 "**下一步**"。  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF 核心":::
             WPF 核心 :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF 框架":::
             WPF 框架 :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  输入 "**项目名称**" 和 "**位置**" 值。  选择 ".NET Framework 4.6.2 或更高版本" 或 ".NET Core 3.0 或更高版本"。  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="创建核心":::
                 创建核心 :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="创建框架":::
                 创建框架 :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  选择 "**创建**" 以创建项目。  
    
## 步骤 2-安装 WebView2 SDK  

接下来，将 WebView2 SDK 添加到项目。  对于预览，使用 Nuget 安装 WebView2 SDK。  

1.  打开项目上的上下文菜单 \ （右键单击 \），然后选择 "**管理 NuGet 程序包 ...**"。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       Nuget.exe
    :::image-end:::
    
1.  `Microsoft.Web.WebView2`在搜索栏中输入。  从搜索结果中选择 " **WebView2** "。  将 "程序包版本" 设置为 "**预发布**"，然后选择 "**安装**"。  
    
     ![nuget.exe](./media/installnuget.PNG)
    
    全部设置为使用 WebView2 API 开始开发应用程序。  按 `F5` 生成并运行项目。  正在运行的项目显示一个空窗口。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="空应用":::
       空应用
    :::image-end:::  
    
## 步骤 3-在 MainWindow 中创建单个 Web 视图  

接下来，将 Web 视图添加到你的应用程序。  

1.  打开 `MainWindow.xaml`。  通过在标记内插入以下行来添加 WebView2 XAML 命名空间 `<Window/>` 。  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    确认代码 `MainWindow.xaml` 看起来类似于以下代码片段。  
    
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
    
1.  通过 `<Grid>` 使用以下代码片段替换标记来添加 WebView2 控件。  该 `Source` 属性设置 WebView2 控件中显示的初始 URI。  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  按 `F5` 生成并运行你的项目。  确认你的 WebView2 控件是否显示 [https://www.microsoft.com](https://www.microsoft.com) 。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       Microsoft.com
    :::image-end:::  
    
## 步骤 4-导航  

添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的功能。

1.  在**MainWindow**中，通过在包含 web 视图的 DockPanel 中复制和粘贴以下代码片段来添加地址栏。  
    
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
    
    确认该 `DockPanel` 部分 `MainWindow.xaml` 看起来类似于以下代码片段。  
    
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
    
1.  `MainWindow.xaml.cs`在 Visual Studio 中打开。  `CoreWebView2`通过在的顶部插入以下代码片段来添加命名空间 `MainWindow.xaml.cs` 。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  在**MainWindow.xaml.cs**中，复制以下代码片段以创建 `ButtonGo_Click` 方法，该方法将 web 视图导航到在地址栏中输入的 URL。  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    按 `F5` 生成并运行你的项目。  在地址栏中输入新的 URL，然后选择 "**转到**"。  例如，enter `https://www.bing.com` 。  确认 WebView2 控件导航到 URL。  
    
    > [!NOTE]
    > 请确保在地址栏中输入完整的 URL。  `ArgumentException`如果 URL 不以 or 开头，则会引发 `http://` a `https://` 。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="必应":::
       必应
    :::image-end:::
    
## 步骤 5-导航事件  

托管 WebView2 控件的应用程序将侦听在导航到网页期间由 WebView2 控件引发的以下事件。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

有关详细信息，请参阅[导航事件](../reference/win32/0-9-488/icorewebview2.md#navigation-events)。  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   导航事件
:::image-end:::  

当发生错误时，将引发以下事件，并可能依赖于导航到错误页面。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

当存在 HTTP 重定向时，有多个 `NavigationStarting` 事件。  

若要演示如何使用这些事件，请首先注册 `NavigationStarting` 一个用于取消任何不使用 HTTPS 的请求的处理程序。  

在中 `MainWindow.xaml.cs` ，修改构造函数，如下所示，并添加 `EnsureHttps` 函数。  

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

在构造函数中，EnsureHttps 将注册为 WebView2 控件上事件的事件处理程序 `NavigationStarting` 。  

按 `F5` 生成并运行你的项目。  确认在导航到 HTTP 站点时，Web 视图**保持不变**。  但是，Web 视图导航到 HTTPS 站点。  

## 步骤 6-脚本  

在运行时，你可以使用主机应用程序将 JavaScript 代码注入 WebView2 控件。  插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。  插入的 JavaScript 将在创建全局对象后以及 HTML 文档中包含的任何其他脚本运行之前运行。  

导航到非 HTTPS 网站时，可以使用脚本来提醒用户。  修改该 `EnsureHttps` 函数，以便它使用[ExecuteScriptAsync](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync)方法将脚本插入 web 内容。  

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

按 `F5` 生成并运行你的项目。  确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   HTTPS
:::image-end:::  

## 步骤 7-主机和 web 内容之间的通信  

宿主和 web 内容可以按如下方式进行通信 `postMessage` ：  

*   WebView2 控件中的 Web 内容可能会使用将消息发布到主机 `window.chrome.webview.postMessage` 。  主机使用主机上已注册的任何内容处理消息 `WebMessageReceived` 。  
*   使用 or 将消息发布到 WebView2 控件中的 web `CoreWebView2.PostWebMessageAsString` 内容 `CoreWebView2.PostWebMessageAsJSON` 。  这些消息由添加到的处理程序捕获 `window.chrome.webview.addEventListener` 。  

此通信机制允许 web 内容使用本机功能将消息传递到主机。  

在你的项目中，当 WebView2 控件导航到 URL 时，它将在地址栏中显示 URL，并向 WebView2 控件中显示的 URL 的用户发出警报。  

1.  在**MainWindow.xaml.cs**中，更新你的构造函数并创建 `InitializeAsync` 函数，如以下代码片段所示。  `InitializeAsync`函数会等待[EnsureCoreWebView2Async](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#ensurecorewebview2async) ，因为它的初始化 `CoreWebView2` 是异步的。  
    
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
    
1.  初始化**CoreWebView2**后，注册一个事件处理程序以响应 `WebMessageReceived` 。  在**MainWindow.xaml.cs**更新中 `InitializeAsync` ，并 `UpdateAddressBar` 使用以下代码片段添加。  
    
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
    
1.  为了让 web 视图发送和响应 web 消息，在 `CoreWebView2` 初始化后，主机：  
    
    1.  将脚本插入到 web 内容中，该内容注册处理程序以打印来自主机的消息。  
    1.  将脚本插入到将 URL 发布到主机的 web 内容中。  
    
    在中 `MainWindow.xaml.cs` ，按 `InitializeAsync` 如下方式更新：  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    按 `F5` 生成并运行应用。  现在，地址栏在 Web 视图中显示 URI，当你成功导航到新的 URI 时，Web 视图会警告 Web 视图中显示的 URI 的用户。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="addressBar":::
       addressBar
    :::image-end:::

恭喜，你已构建了你的第一个 WebView2 应用！  

## 后续步骤  

*   有关 WebView2 功能的完整示例，请参阅 GitHub 上的[WebView2Samples](https://github.com/MicrosoftEdge/WebView2Samples)存储库。  
*   有关 WebView2 Api 的更多详细信息，请参阅[API 参考](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md)。  
*   有关 WebView2 的详细信息，请参阅[WebView2 资源](../index.md#next-steps)。  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

通过分享你的反馈来帮助构建更丰富的 WebView2 体验！  访问 Microsoft Edge Web 视图[反馈](https://github.com/MicrosoftEdge/WebViewFeedback)存储库以提交功能请求或 bug 报告或搜索已知问题。  
