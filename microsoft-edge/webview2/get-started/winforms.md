---
description: 适用于 WinForms 应用的 WebView2 入门指南
title: WinForms 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、winforms 应用、winforms、edge、CoreWebView2、浏览器控件、edge html、入门、入门、.NET、windows 窗体
ms.openlocfilehash: 704e5732ddcff02e56f49bec37a5d1ad5f11c2b5
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535878"
---
# <a name="get-started-with-webview2-in-windows-forms"></a>在表单中开始使用 WebView2 Windows表单

本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。  有关各个 API 的信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2Winforms]。  

## <a name="prerequisites"></a>必备条件  

请确保先安装以下先决条件列表，然后再继续。  

*   [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]运行时Microsoft Edge (Chromium) [][MicrosoftedgeinsiderDownload]安装在受支持的操作系统 \ (上的任意非稳定通道Windows 10、Windows 8.1和 Windows 7\) 。  
    
    > [!NOTE]
    > WebView 团队建议使用 Canary 通道，最低要求版本为 82.0.488.0。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2017 或更高版本。  
    
> [!NOTE]
> WebView2 当前不支持 .NET 5 和 .NET Core 设计器。  

## <a name="step-1---create-a-single-window-app"></a>步骤 1 - 创建单窗口应用

从包含单个主窗口的基本桌面项目开始。  

1.  In Visual Studio， choose **Windows Forms .NET Framework App**  >  **Next**.
    
    :::image type="complex" source="./media/winforms-new-project.png" alt-text="新建项目" lightbox="./media/winforms-new-project.png":::
       新建项目  
    :::image-end:::
    
1.  输入 name 和**location Project****的值**。  选择 **.NET Framework 4.6.2**或更高版本。  
    
    :::image type="complex" source="./media/winforms-start-proj.png" alt-text="启动项目" lightbox="./media/winforms-start-proj.png":::
       启动项目  
    :::image-end:::
    
1.  若要创建项目，请选择"创建 **"。**
    
## <a name="step-2---install-webview2-sdk"></a>步骤 2 - 安装 WebView2 SDK

使用 NuGet 将 WebView2 SDK 添加到项目中。  

1.  将鼠标悬停在项目上，打开上下文菜单 \ (右键单击\) ，然后选择"管理NuGet**包..."。**  
    
    :::image type="complex" source="./media/wpf-getting-started-mng-nuget.png" alt-text="管理 NuGet 包":::
       管理 NuGet 包
    :::image-end:::
    
1.  在搜索栏中，键入"> `Microsoft.Web.WebView2` **选择"Microsoft.Web.WebView2"。**  
    
    :::image type="complex" source="./media/install-nuget.png" alt-text="NuGet" lightbox="./media/install-nuget.png":::
       NuGet  
    :::image-end:::
    
    开始使用 WebView2 API 开发应用。  若要生成并运行项目，请选择 `F5` 。  正在运行的项目显示一个空窗口。  
    
    :::image type="complex" source="./media/winforms-empty-app.png" alt-text="空应用" lightbox="./media/winforms-empty-app.png":::
       空应用  
    :::image-end:::
    
## <a name="step-3---create-a-single-webview"></a>步骤 3 - 创建单个 WebView  

将 WebView 添加到你的应用。  

1.  打开 **"Windows设计器"。**  
1.  在工具箱**中搜索 WebView2。** ****  
    
    > [!NOTE]
    > 如果使用的是 Visual Studio 2017，则**默认情况下 WebView2**可能不会显示在工具箱**中**。  若要启用此行为，请选择"**工具**  >  **""** 选项  >  ****>"**自动填充工具箱**"设置设置为 `True` 。  
    
    将**WebView2 控件**拖放到 Windows Forms App。
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="显示 WebView2 的工具箱":::
       显示 WebView2 的工具箱  
    :::image-end:::  
    
1.  将 `(Name)` 属性设置为 `webView`。
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 控件的属性":::
       WebView2 控件的属性
    :::image-end:::
    
1.  属性 `Source` 设置 WebView2 控件中显示的初始 URI。  将 `Source` 属性设置为 `https://www.microsoft.com`。  
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 控件的 Source 属性":::
       WebView2 控件的 **Source** 属性
    :::image-end:::  

若要生成并运行项目，请选择 `F5` 。  确保 WebView2 控件显示 [https://www.microsoft.com][|::ref1::|Main] 。

:::image type="complex" source="./media/winforms-hello-webview.png" alt-text="hello webview" lightbox="./media/winforms-hello-webview.png":::
   hello webview  
:::image-end:::    

> [!NOTE]
> 如果正在处理高 DPI 监视器，可能需要将 Windows [Forms 应用配置为高 DPI 支持][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]。  

## <a name="step-4---handle-window-resize-events"></a>步骤 4 - 处理窗口大小事件  

从工具箱向窗体中添加Windows控件，然后适当地处理窗口大小事件。  

1.  在 **"Windows设计器"中**，打开"工具箱 **"。**  
1.  将**TextBox 拖放**到 Windows Forms 应用程序中。  将 **"属性"选项卡中的 TextBox** `addressBar` **命名**。  
1.  将**按钮拖放到**Windows Forms 应用程序中。  将"按钮"中的**文本** `Go!` 更改为 ，并**** 命名"属性"选项卡 `goButton` **中的"按钮"。**  
    
    应用应如设计器中的下图所示。  
    
    :::image type="complex" source="./media/winforms-designer.png" alt-text="WinForms 设计器" lightbox="./media/winforms-designer.png":::
       WinForms 设计器  
    :::image-end:::  

1.  在 `Form1.cs` 文件中，定义 `Form_Resize` 以在调整应用窗口大小时保持控件就位。
    
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

若要生成并运行项目，请选择 `F5` 。  确保应用显示类似于以下屏幕截图。

:::image type="complex" source="./media/winforms-app.png" alt-text="应用" lightbox="./media/winforms-app.png":::
   应用  
:::image-end:::  

## <a name="step-5---navigation"></a>步骤 5 - 导航

添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的能力。  

1.  选择 `F5` 以生成并运行项目。  确认应用显示类似于以下屏幕截图。  
    
    :::image type="complex" source="./media/winforms-app.png" alt-text="WinForms 应用" lightbox="./media/winforms-app.png":::
       WinForms 应用  
    :::image-end:::  
    
1.  在 `Form1.cs` 文件中，若要添加 `CoreWebView2` 命名空间，请将以下代码段插入顶部。  
1.  在 `Form1.cs` 添加 `CoreWebView2` 命名空间时，在 的顶部插入以下代码段 `Form1.cs` 。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  在 **"Windows设计器**"中，双击按钮 `Go!` 以 `goButton_Click` 在文件中创建 `Form1.cs` 方法。  复制以下代码段并将其粘贴到 函数中。  现在， `goButton_Click` 函数将 WebView 导航到地址栏中输入的 URL。
    
    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
若要生成并运行项目，请选择 `F5` 。  在地址栏中输入新 URL，然后选择"转到 **"。**  例如，输入 `https://www.bing.com` 。  确保 WebView2 控件导航到 URL。  

> [!NOTE]
> 确保在地址栏中输入完整 URL。  如果 `ArgumentException` URL 不以 或 为起始，则 `http://` 会引发 。 `https://`

:::image type="complex" source="./media/winforms-bing.png" alt-text="bing.com" lightbox="./media/winforms-bing.png":::
   bing.com  
:::image-end:::  

## <a name="step-6---navigation-events"></a>步骤 6 - 导航事件  

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

若要演示如何使用事件，请首先注册一个处理程序，以取消不使用 `NavigationStarting` HTTPS 的任何请求。  

在 `Form1.cs` 文件中，更新构造函数以匹配以下代码段并添加 `EnsureHttps` 函数。  

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

在构造函数中 `EnsureHttps` ，注册为 WebView2 控件上事件 `NavigationStarting` 的事件处理程序。  

若要生成并运行项目，请选择 `F5` 。  确保导航到 HTTP 网站时，WebView 保持不变。  但是，WebView 将导航到 HTTPS 网站。

## <a name="step-7---scripting"></a>步骤 7 - 脚本  

你可以在运行时使用主机应用将 JavaScript 代码注入 WebView2 控件。  你可以任务 WebView 运行任意 JavaScript 或添加初始化脚本。  在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。  注入的 JavaScript 以特定计时运行。  

*   创建全局对象后运行它。  
*   在运行 HTML 文档中包含的任何其他脚本之前运行它。  
    
例如，添加在用户导航到非 HTTPS 网站时发送警报的脚本。  修改 `EnsureHttps` 函数以将脚本注入到使用 [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync] 方法的 Web 内容中。  

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

:::image type="complex" source="./media/winforms-https.png" alt-text="https" lightbox="./media/winforms-https.png":::
   https  
:::image-end:::  

## <a name="step-8---communication-between-host-and-web-content"></a>步骤 8 - 主机和 Web 内容之间的通信  

主机和 Web 内容可能 `postMessage` 用于相互通信，如下所示：  

*   WebView2 控件中的 Web 内容可能 `window.chrome.webview.postMessage` 用于向主机发布消息。  主机使用主机上注册的任何消息 `WebMessageReceived` 处理邮件。  
*   使用 或 将消息张贴到 WebView2 控件中的 `CoreWebView2.PostWebMessageAsString` Web 内容 `CoreWebView2.PostWebMessageAsJSON` 。  添加到 的处理程序会捕获这些消息 `window.chrome.webview.addEventListener` 。  
    
通信机制使用本机功能将来自 Web 内容的消息传递给主机。  

在项目中，当 WebView2 控件导航到 URL 时，它会在地址栏中显示 URL，并通知用户 WebView2 控件中显示的 URL。  

1.  在 `Form1.cs` 文件中，更新构造函数并创建 `InitializeAsync` 一个函数以匹配以下代码段。  函数 `InitializeAsync` awaits [EnsureCoreWebView2Async，][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] 因为 的初始化 `CoreWebView2` 是异步的。  
    
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
    
1.  初始化 `CoreWebView2` 后，注册事件处理程序以响应 `WebMessageReceived` 。  在 `Form1.cs` 文件中， `InitializeAsync` 使用下面的代码 `UpdateAddressBar` 段更新和添加。  
    
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
    
1.  为了使 WebView 能够发送和响应 Web 消息，在初始化后，主机将 Web 内容中的脚本注入 `CoreWebView2` 到：  
    1.  使用 将 URL 发送到主机 `postMessage` 。
    1.  注册事件处理程序以打印从主机发送的消息。  
        
在 `Form1.cs` 文件中，进行更新 `InitializeAsync` 以匹配以下代码段。  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

若要生成并运行应用，请选择 `F5` 。  现在，地址栏在 WebView2 控件中显示 URI。  此外，当你成功导航到新 URL 时，WebView 会向用户通知 WebView 中显示的 URL。  

:::image type="complex" source="./media/winforms-final-app.png" alt-text="最终应用" lightbox="./media/winforms-final-app.png":::
   最终应用  
:::image-end:::  

恭喜！你生成了第一个 WebView2 应用。  

## <a name="next-steps"></a>后续步骤  

若要继续了解有关 WebView2 的更多内容，请导航到以下资源。  

*   若要了解有关生成 WebView2 应用程序的信息，请导航到 [WebView2 开发最佳做法][WV2BestPractices]。  
*   有关 WebView2 功能的综合示例，请导航到 [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain]。  
*   有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]  
*   有关 WebView2 API 的详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WinformsWebview2]。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 WebView 团队Microsoft Edge联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 开发最佳实践|Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 类|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async (CoreWebView2Environment) 方法|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.winforms.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法|Microsoft Docs"  

[DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]: /dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support "Configuring your Windows Forms app for high DPI support - Windows Forms |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 |Microsoft Edge开发人员"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  
