---
description: 了解如何使用 Microsoft Edge WebView2 Chromium DevTools 协议 NuGet 程序包在 WebView2 应用中使用 Chrome DevTools 协议
title: 在 WebView2 中使用 Chrome DevTools 协议
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Chrome DevTools 协议
ms.openlocfilehash: 0f7a2dd4bb3b1621e854cd4c0c5410e64d3c03ff
ms.sourcegitcommit: 0ef5bb3933cde8a466f2931b824f07b4995cfe5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "11409306"
---
# <a name="use-chromium-devtools-protocol-in-webview2"></a>在 WebView2 中使用 Chromium DevTools 协议  

[Chromium DevTools 协议][GitHubChromedevtoolsDevtoolsProtocol]提供用于检测、检查、调试和配置文件基于 Chromium 的浏览器的 API。  Chromium DevTools 协议是 Microsoft Edge \ (Chromium\) DevTools 的基础。  对 WebView2 平台中未实现的功能使用 Chromium DevTools 协议。  有关 Chromium DevTools 协议功能的信息，请导航到 [Chromium DevTools 协议][GitHubChromedevtoolsDevtoolsProtocol]。  

> [!CAUTION]
> Microsoft Edge WebView2 团队不维护或支持 Chromium DevTools 协议。  Chromium DevTools 协议由开源 Chromium 项目维护。  
> 
> 若要发送有关未来 WebView2 平台功能的建议，请导航到 ["WebView 反馈][GithubMicrosoftedgeWebview2feedback] "并提交问题。  

若要在 WebView2 中使用 Chromium DevTools 协议 API，请使用以下任一操作。  

*   安装并使用 [Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview) ][NugettestIntPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet 程序包 \ (.NET\) 。  
*   运行下列方法之一。  
    *   [.NET：CallDevToolsProtocolAsync][DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString] [、GetDevToolsProtocolEventReceiver][DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]  
    *   Win32  [C/C++：CallDevToolsProtocolMethod][Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod] [、ICoreWebView2DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]  
    
## <a name="use-devtoolsprotocolhelper-preview"></a>使用 DevToolsProtocolHelper (Preview) 

> [!NOTE]
> [Microsoft.Web.WebView2.DevToolsProtocolExtension][NugettestIntPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet 程序包目前处于技术预览阶段。  在预览版中，请勿在生产应用中使用程序包。

[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview) ][NugettestIntPackagesMicrosoftWebWebView2DevToolsprotocolextension] 是 WebView2 团队创建的 NuGet 包，可轻松访问 Chromium DevTools 协议功能。  以下示例介绍如何在 WebView2 控件的 Chromium DevTools 协议中使用地理位置功能。  你可以遵循类似的模式来使用其他 Chromium DevTools 协议功能。  

## <a name="step-1-create-a-webpage-to-find-your-geolocation"></a>步骤 1：创建网页以查找地理位置  

若要创建 `HTML file` 以查找地理位置，请完成以下操作。  

1.  打开Visual Studio代码 \ (或你选择的 IDE\) 。  
1.  创建新 `.html` 文件。  
1.  将以下代码段复制并粘贴到新 `.html` 文件中。  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <title>Geolocation Finder</title>
    </head>
    <body>
        <button id="display">Display Location</button>
        <div id="message"></div>
    </body>
    
    <script>
        const btn = document.getElementById('display');
        // Find the user location.
        btn.addEventListener('click', function () {
            navigator.geolocation.getCurrentPosition(onSuccess, onError);
        });
        
        // Update message to display the latitude and longitude coordinates.
        function onSuccess(position) {
            const {latitude, longitude} = position.coords;
            message.textContent = `Your location: (${latitude},${longitude})`;
        }
        
        function onError() {
            message.textContent = `Operation Failed`;
        }
    </script>
    </html>
    ```  
    
1.  使用 `.html` 文件名 保存文件 `geolocation.html` 。  
1.  打开 Microsoft Edge。  
1.  打开 `geolocation.html` 文件。  
1.  若要显示纬度和经度坐标，请选择"显示 **位置"** 按钮。  若要验证和比较地理位置，请将坐标复制并粘贴到 中 [https://www.bing.com/maps][BingMaps] 。  
    
    :::image type="complex" source="./media/geolocater-browser.png" alt-text="在 Microsoft Edge 中显示用户的地理位置坐标" lightbox="./media/geolocater-browser.png":::
       在 Microsoft Edge 中显示用户的地理位置坐标  
    :::image-end:::  
    
## <a name="step-2-display-geolocationhtml-in-a-webview2"></a>步骤 2：geolocation.htmWebView2 中显示 geolocation.html  

1.  若要创建 WebView2 应用，请使用以下入门指南或 WebView2 示例之一。  
    *   [Windows 窗体中的 WebView2 入门][Webview2GettingstartedWinforms]  
    *   [WPF 中的 WebView2 入门][Webview2GettingstartedWpf]  
    *   [WebView2 示例][GithubMicrosoftedgeWebview2samples]  
        
1.  将 WebView2 控件的初始导航设置为 `geolocation.html` 。  
    
    ```csharp
    webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    ```  
    
1.  确保 `geolocation.html` 文件显示在 WebView2 控件应用中。  
    
    :::image type="complex" source="./media/initial-geolocate.png" alt-text="在 WebView2 geolocater.htm应用中显示 geolocater.html 文件" lightbox="./media/initial-geolocate.png":::
       在 `geolocation.html` WebView2 控件应用中显示文件  
    :::image-end:::  
    
## <a name="step-3-install-the-devtoolsprotocolhelper-nuget-package"></a>步骤 3：安装 DevToolsProtocolHelper NuGet 程序包  

使用 NuGet 下载 `Microsoft.Web.WebView2.DevToolsProtocolExtension` 。  若要安装程序包，请完成以下操作。  

1.  选择 **"项目**  >  **管理 NuGet 程序包浏览**  >  **"。**  
1.  键入 `Microsoft.Web.WebView2.DevToolsProtocolExtension` 并选择 **"Microsoft.Web.WebView2.DevToolsProtocolExtension**  >  **安装"。**   
    
:::image type="complex" source="./media/cdpnuget.png" alt-text="确保 Microsoft.Web.WebView2.DevToolsProtocolExtension 显示在 NuGet Visual Studio中程序包管理器" lightbox="./media/cdpnuget.png":::
   确保 **Microsoft.Web.WebView2.DevToolsProtocolExtension** 显示在 NuGet Visual Studio中程序包管理器  
:::image-end:::  

## <a name="step-4-use-devtools-protocol-helper"></a>步骤 4：使用 DevTools 协议帮助程序  

1.  将 `DevToolsProtocolExtension` 命名空间添加到项目中。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    using Microsoft.Web.WebView2.Core.DevToolsProtocolExtension;
    ```  
    
1.  实例化 `DevToolsProtocolHelper` 对象并导航到 `geolocation.html` 。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webView.CoreWebView2.GetDevToolsProtocolHelper(); 
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    }
    ```  
    
1.  运行 [setGeoLocationOverrideAsync][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride] 方法。  有关详细信息，请导航到 [setGeolocationOverride][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webview.CoreWebView2.GetDevToolsProtocolHelper();
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
        
        // Latitude and longitude for Paris, France.
        double latitude = 48.857024082572565;  
        double longitude = 2.3161581601457386;  
        double accuracy = 1;
        await helper.Emulation.setGeolocationOverrideAsync(latitude, longitude, accuracy);
        
    }
    ```  
    
1.  运行应用。  
1.  若要显示法国巴黎的坐标，请选择" **显示位置"** 按钮。  
    
    :::image type="complex" source="./media/finallocation-cdp.png" alt-text="在具有巴黎坐标的 WebView2 控件中显示 .html 文件" lightbox="./media/finallocation-cdp.png":::
       在 `.html` WebView2 控件中显示文件以及巴黎的坐标  
    :::image-end:::  
    
## <a name="file-a-chromium-devtools-protocol-bug"></a>提交 Chromium DevTools 协议 Bug  

WebView2 团队没有 Chromium DevTools 协议。  

> [!IMPORTANT]
> 将反馈和 Bug 直接提交到 Chromium 问题存储库。  

若要提交 Chromium DevTools 协议 bug 或问题，请完成以下操作。  

1.  提交 [Bug 报告][ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]。  
1.  导航到 ["WebView 反馈"][GithubMicrosoftedgeWebview2feedback] 并打开新问题。  
    
## <a name="see-also"></a>另请参阅  

*   [WebView2 示例][GithubMicrosoftedgeWebview2samples]  
    
 <!-- links -->  

[Webview2GettingstartedWinforms]: /microsoft-edge/webview2/gettingstarted/winforms "Windows Forms | 中的 WebView2 入门Microsoft Docs"  
[Webview2GettingstartedWpf]: /microsoft-edge/webview2/gettingstarted/wpf "WPF | 中的 WebView2 入门Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2.getdevtoolsprotocoleventreceiver?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2.GetDevToolsProtocolEventReceiver (String) 方法 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString]: /dotnet/api/microsoft.web.webview2.core.corewebview2.calldevtoolsprotocolmethodasync?view=webview2-dotnet-1.0.774.44&preserve-view=true#Microsoft_Web_WebView2_Core_CoreWebView2_CallDevToolsProtocolMethodAsync_System_String_System_String_ "CoreWebView2.CallDevToolsProtocolMethodAsync (String， String) 方法 |Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-1.0.774.44&preserve-view=true#calldevtoolsprotocolmethod "CallDevToolsProtocolMethod - 接口 ICoreWebView2 |Microsoft Docs"  
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-1.0.774.44&preserve-view=true "interface ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  

[BingMaps]: https://www.bing.com/maps "必应地图"  

[GitHubChromedevtoolsDevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools 协议|GitHub"  
[GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]: https://chromedevtools.github.io/devtools-protocol/tot/Emulation/#method-setGeolocationOverride "Emulation.setGeolocationOverride - Chrome DevTools 协议|GitHub"  

[GithubMicrosoftedgeWebview2feedback]: https://github.com/MicrosoftEdge/WebView2Feedback "WebView 反馈|GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例|GitHub"  

[ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]: https://bugs.chromium.org/p/chromium/issues/entry?components=Platform%3EDevTools%3EPlatform "错误报告|Chromium Bug"  

[NugettestIntPackagesMicrosoftWebWebView2DevToolsprotocolextension]: https://int.nugettest.org/packages/Microsoft.Web.WebView2.DevToolsProtocolExtension "Microsoft.Web.WebView2.DevToolsProtocolExtension |NuGet QA 库"  
