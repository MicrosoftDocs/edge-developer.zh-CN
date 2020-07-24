---
description: 在 Windows 窗体应用中将 web 内容与 Microsoft Edge Web 视图2控件一起托管
title: 适用于 Windows 表单应用的 Microsoft Edge Web 视图2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、winforms 应用、winforms、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET、windows 窗体
ms.openlocfilehash: 634fbd74a94ea990bc3eb9c150760522a5c13ce1
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895523"
---
# Windows 窗体应用中的 WebView2 入门（预览版）  

在本文中，开始创建你的第一个 WebView2 应用，并了解[WebView2 （预览版）](/microsoft-edge/hosting/webview2/index)的主要功能。  有关单个 Api 的详细信息，请参阅[API 参考](../reference/dotnet/0-9-515-reference-webview2.md)。  

## 必备条件  

请确保在继续之前安装了以下先决条件列表：  

* 安装在 Windows 10、Windows 8.1 或 Windows 7 上的[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download)的未安装频道。 
* [Visual Studio](https://visualstudio.microsoft.com) 2017 或更高版本。

> [!NOTE]
> WebView2 当前不支持 .NET Core 3.0 的[设计器（预览版）](https://visualstudio.microsoft.com/vs/preview)。

## 步骤 1-创建单个窗口应用程序

从包含单个主窗口的基本桌面项目开始。  

1. 打开**Visual Studio。**

1. 选择 " **Windows 窗体 .Net Framework 应用**"，然后选择 "**下一步**"。

    ![newproject](./media/winforms-newproject.png)

1. 输入 "**项目名称**" 和 "**位置**" 值。  选择 " **.Net Framework 4.6.2** " 或 "更高版本"。  

    ![startproject](./media/winforms-startproj.png)

1. 选择 "**创建**" 以创建你的项目。

## 步骤 2-安装 WebView2 SDK

接下来，将 WebView2 SDK 添加到项目。  对于预览，使用 Nuget 安装 WebView2 SDK。  

1. 打开项目上的上下文菜单 \ （右键单击 \），然后选择 "**管理 NuGet 程序包 ...**"。  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       Nuget.exe :::image-end:::

1. `Microsoft.Web.WebView2`在搜索栏中输入。  从搜索结果中选择 " **WebView2** "。  

    > [!IMPORTANT]
    > 确保选中 "**包括预**发布"，选择 "**版本**" 中的预发布程序包，然后选择 "**安装**"。  

    ![nuget.exe](./media/installnuget.png)

全部设置为使用 WebView2 API 开始开发应用程序。  选择 `F5` 以生成并运行项目。  正在运行的项目显示一个空窗口。  

![emptyApp](./media/winforms-emptyApp.png)

## 步骤 3-创建单个 Web 视图  

接下来，将 Web 视图添加到你的应用程序。  

1. 打开**Windows 窗体设计器**。  
1. 在**工具箱**中搜索**WebView2** 。 将**WebView2**控件拖放到 Windows Forms 应用中

    ![>](./media/winforms-toolbox.png)

1. 将 `Name` 属性更改为 `webView`。

    ![>](./media/winforms-properties.png)

1. 该 `Source` 属性设置 WebView2 控件中显示的初始 URI。 将 Source 属性设置为 <https://www.microsoft.com>

    ![>](./media/winforms-source.png)

选择 `F5` 生成并运行项目。  确认你的 WebView2 控件是否显示 [https://www.microsoft.com](https://www.microsoft.com) 。

![hellowebview](./media/winforms-hellowebview.png)

> [!NOTE]
> 如果您使用的是高 DPI 监视器，则可能需要为[高 dpi 支持配置 Windows 窗体应用](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support)。

## 步骤 4-处理窗口调整大小事件

将更多控件从工具箱添加到 Windows 窗体，然后相应地处理窗口大小调整事件。

1. 在**Windows 窗体设计器**中打开**工具箱**
1. 将**TextBox**拖放到 Windows Forms 应用中。 **TextBox** `addressBar` 在 "**属性" 选项卡**中命名文本框。
1. 将**按钮**拖放到 Windows 窗体应用中。 将**按钮**中的文本更改为 `Go!` 并在**Button** `goButton` "**属性" 选项卡**中命名该按钮。

    应用在设计器中的外观应如下所示：
    
    ![设计器](./media/winforms-designer.png)

1. 在**Form1.cs**定义 `Form_Resize` 以在调整应用窗口大小时保持控件的位置。

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);
}

private void Form_Resize(object sender, EventArgs e)
{
    webView.Size = this.ClientSize - new System.Drawing.Size(webView.Location);
    goButton.Left = this.ClientSize.Width - goButton.Width;
    addressBar.Width = goButton.Left - addressBar.Left;
}
```

选择 `F5` 生成并运行项目。  确认应用显示类似于以下屏幕截图。

![应用](./media/winforms-app.png)

## 步骤 5-导航

添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的功能。

1. 在 `Form1.cs` "添加命名空间" 中，将 `CoreWebView2` 以下代码片段插入到顶部 `Form1.cs` 。  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1. 在**Windows 窗体设计器**中，双击 `Go!` 要在其中创建方法的按钮 `goButton_Click` `Form1.cs` 。 在函数内复制并粘贴以下代码段。 现在，该 `goButton_Click` 函数将 Web 视图导航到在地址栏中输入的 URL。

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

选择 `F5` 生成并运行项目。  在地址栏中输入新的 URL，然后单击 "**转到**"。  例如，enter `https://www.bing.com` 。  确认 WebView2 控件导航到 URL。  

> [!NOTE]
> 确保在地址栏中输入完整的 URL。 `ArgumentException`如果 URL 不以 or 开头的 URL，则会引发 `http://` `https://`

![bing](./media/winforms-bing.png)

## 步骤 6-导航事件  

托管 WebView2 控件的应用程序将侦听在导航到网页期间由 WebView2 控件引发的以下事件。  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

有关详细信息，请参阅[导航事件](../concepts/navigation-events.md)。  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   导航事件
:::image-end:::

当发生错误时，将引发以下事件，并可能依赖于导航到错误页面。  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

当存在 HTTP 重定向时，有多个 `NavigationStarting` 事件。  

若要演示如何使用这些事件，请首先注册 `NavigationStarting` 一个用于取消任何不使用 HTTPS 的请求的处理程序。  

在中 `Form1.cs` ，修改构造函数，如下所示，并添加 `EnsureHttps` 函数。  

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);

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

选择 `F5` 生成并运行项目。 确认在导航到 HTTP 站点时，Web 视图保持不变。 但是，Web 视图将导航到 HTTPS 站点。

## 步骤 7-脚本  

在运行时，你可以使用主机应用程序将 JavaScript 代码注入 WebView2 控件。  插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。  插入的 JavaScript 将在创建全局对象后以及 HTML 文档中包含的任何其他脚本运行之前运行。  

导航到非 HTTPS 网站时，可以使用脚本来提醒用户。  修改该 `EnsureHttps` 函数，以便它使用[ExecuteScriptAsync]()方法将脚本插入 web 内容。  

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

选择 `F5` 生成并运行项目。  确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。  

![https](./media/winforms-https.png)

## 步骤 8-主机和 web 内容之间的通信  

宿主和 web 内容可以按如下方式进行通信 `postMessage` ：  

* WebView2 控件中的 Web 内容可能会使用将消息发布到主机 `window.chrome.webview.postMessage` 。  主机使用主机上已注册的任何内容处理消息 `WebMessageReceived` 。  
* 使用 or 将消息发布到 WebView2 控件中的 web `CoreWebView2.PostWebMessageAsString` 内容 `CoreWebView2.PostWebMessageAsJSON` 。  这些消息由添加到的处理程序捕获 `window.chrome.webview.addEventListener` 。  

此通信机制允许 web 内容使用本机功能将消息传递到主机。  

在你的项目中，当 WebView2 控件导航到 URL 时，它将在地址栏中显示 URL，并向 WebView2 控件中显示的 URL 的用户发出警报。  

1. 在**Form1.cs**中，更新你的构造函数并创建 `InitializeAsync` 函数，如以下代码片段所示。  `InitializeAsync`函数会等待[EnsureCoreWebView2Async]() ，因为它的初始化 `CoreWebView2` 是异步的。  

    ```csharp
    public Form1()
    {
        InitializeComponent();
        this.Resize += new System.EventHandler(this.Form_Resize);
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }

    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  

1. 初始化**CoreWebView2**后，注册一个事件处理程序以响应 `WebMessageReceived` 。  在 " `Form1.cs` 更新" `InitializeAsync` 和 " `UpdateAddressBar` 使用以下代码片段添加" 中。  

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

1. 为了让 web 视图发送和响应 web 消息，在 `CoreWebView2` 初始化后，主机会将 web 内容中的脚本插入到：  

    1. 使用将 URL 发送给主机 `postMessage` 。
    1. 注册一个事件处理程序以打印从主机发送的消息。  

在中 `Form1.cs` ，更新， `InitializeAsync` 如以下代码片段所示。  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

选择 `F5` 生成并运行应用。  确认地址栏显示在 Web 视图中显示的网站的 URL。 此外，当你成功导航到新 URL 时，Web 视图会警告 Web 视图中显示的 URL 的用户。  

![finalapp](./media/winforms-finalapp.png)

恭喜，你已构建了你的第一个 WebView2 应用！  

## 后续步骤 

* 签出[WebView2Samples](https://github.com/MicrosoftEdge/WebView2Samples)存储库，获取 WebView2's 功能的全面示例
* 签出[api 参考](../reference/winforms/0-9-515/microsoft-web-webview2-winforms-webview2.md)了解有关我们的 api 的更多详细信息
* 签出[WebView2 资源](../index.md#next-steps)列表以了解有关 WebView2 的详细信息


## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

通过分享你的反馈来帮助构建更丰富的 WebView2 体验！  访问 Microsoft Edge Web 视图[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告或搜索已知问题。  
