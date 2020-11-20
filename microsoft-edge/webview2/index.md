---
description: 通过 Microsoft Edge WebView2 控件在 Win32、.NET、UWP 应用程序中托管 web 内容
title: Microsoft Edge WebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、Windows 窗体、WinForms、WPF、.NET、WinUI、Project 留尼汪岛
ms.openlocfilehash: 9e5cc3a26f07a11c9fd5c21d62ecafc3ed5103f4
ms.sourcegitcommit: c619168deea44cdec8ebc80ef9ddf1d91d5f726d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "11182181"
---
# Microsoft Edge WebView2 简介  

Microsoft Edge WebView2 控件使你能够在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript \ ) 。  WebView2 控件使用 [Microsoft Edge () Chromium ][MicrosoftedgeinsiderMain] 作为呈现引擎在本机应用程序中显示 web 内容。  使用 WebView2，你可以将 web 代码嵌入本机应用程序的不同部分，或在单个 Web 视图中构建整个本机应用程序。  有关如何开始生成 WebView2 应用程序的信息，请导航到 " [开始](#getting-started)"。  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="什么是 Web 视图" lightbox="./media/WebView2/whatwebview.png":::
   什么是 Web 视图  
:::image-end:::  

## 混合应用程序方法  

开发人员通常必须决定生成 web 应用程序还是本机应用程序。  决策在接触和接通电源之间的平衡。  Web 应用程序允许广泛访问。  作为 Web 开发人员，你可以在所有不同平台上重复使用大多数代码（如果不是所有代码）。  但是，本机应用程序利用整个本机平台的功能。  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native" lightbox="./media/WebView2/webnative.png":::
   Web native  
:::image-end:::  

混合应用程序使开发人员能够享受这两个领域的最佳体验。  混合应用程序开发人员受益于 web 平台的 ubiquity 和强项，以及本机平台的强大功能和完整功能。  

## WebView2 优惠  

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="Web 视图原因" lightbox="./media/WebView2/webviewreasons.png":::
   Web 视图原因  
:::image-end:::  

:::row:::
   :::column span="1":::
      **Web 生态系统 \ & skillset**  
      利用 web 生态系统中存在的整个 web 平台、库、工具和人才。  
   :::column-end:::
   :::column span="1":::
      **快速创新**  
      Web 开发允许更快的部署和迭代。  
   :::column-end:::
   :::column span="1":::
      **Windows 7、8、10支持**  
      在 Windows 7、8和10上支持一致的用户体验。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **本机功能**  
      访问完整的本机 Api 集。  
   :::column-end:::
   :::column span="1":::
      **代码共享**  
      将 web 代码添加到你的基本代码，可在多个平台之间更好地重复使用。  
   :::column-end:::
   :::column span="1":::
      **Microsoft 支持**  
      Microsoft 在 WebView2 发布为 GA 时提供支持和添加新功能请求。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **长绿分布**  
      通过常规的平台更新和安全修补程序依赖最新版本的 Chromium。  
   :::column-end:::
   :::column span="1":::
      已**修复**的 \ (即将推出 \ )   
      选择将 Chromium 位打包在你的应用程序中。  
   :::column-end:::
   :::column span="1":::
      **增量采纳**  
      将 web 组件逐个添加到应用程序。  
   :::column-end:::
:::row-end:::  

## 即刻体验  

若要使用 WebView2 控件生成和测试你的应用程序，你需要同时安装 [Microsoft Edge (Chromium) ][MicrosoftedgeinsiderDownload] 和 [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] 。  选择以下选项之一开始使用。  

*   [Win32 C/c + + 入门][Webview2GettingstartedWin32]  
*   [WPF 入门][Webview2GettingstartedWpf]  
*   [WinForms 入门][Webview2GettingstartedWinforms]  
*   [WinUI3 入门][Webview2GettingstartedWinui]  

[WebView2 示例][GithubMicrosoftedgeWebview2samples]存储库包含演示所有 WebView2 SDK 功能和 API 使用模式的示例。  随着将更多功能添加到 WebView2 SDK，示例应用程序将更新。  

## 支持的平台  

常规可用性 \ (GA \ ) 或预览版版本在以下编程环境中可用。  

*   Win32 C/c + + \ (GA \ )   
*   .NET Framework 4.6.2 或更高版本 \ (Preview \ )   
*   .NET Core 3.0 或更高版本 \ (Preview \ )   
*   [WinUI 3.0][UwpToolkitsWinui3] \ (Preview \ )   

你可以在以下版本的 Windows 上运行 WebView2 应用程序。  

*   Windows 10  
*   Windows 8.1  
*   Windows 7 \ * \ *  
*   Windows Server 2019  
*   Windows Server 2016  
*   WindowsServer 2012  
*   Windows Server 2012 R2  
*   Windows Server 2008 R2 \ * \ *  

> [!IMPORTANT]
> \ * \ * WebView2 支持 Windows 7 和 Windows Server 2008 R2 与 Microsoft Edge 具有相同的支持周期。  有关详细信息，请导航到 [Microsoft Edge 支持的操作系统][DeployedgeMicrosoftEdgeSupportedOS]。  

## 后续步骤  

有关如何构建和部署 WebView2 应用程序的详细信息，请参阅概念文档和操作方法指南。  

#### 概念  

*   [了解 WebView2 SDK 版本][Webview2ConceptsVersioning]
*   [使用 WebView2 的应用程序的分发][Webview2ConceptsDistribution]  
*   [开发安全 WebView2 应用程序的最佳做法][Webview2ConceptsSecurity]
*   [管理 WebView2 应用程序中的用户数据文件夹][Webview2ConceptsUserdatafolder]
 
#### How-To 指南  

*   [如何通过 WebView2 进行调试][Webview2HowtoDebug]  
*   [通过 Microsoft Edge 驱动程序自动化和测试 WebView2][Webview2HowtoWebdriver]  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 | 的应用程序的分发Microsoft 文档"  
[Webview2ConceptsSecurity]: ./concepts/security.md "开发安全 WebView2 应用程序的最佳做法 |Microsoft 文档"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "管理用户数据文件夹 |Microsoft 文档"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "了解 WebView2 SDK 版本 |Microsoft 文档"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 | 入门 |Microsoft 文档"  
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms 应用中的 WebView2 入门 (预览版) |Microsoft 文档"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WebView2 中的 "开始" WinUI3 () 预览 "|Microsoft 文档"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF 中的 WebView2 入门 (预览版) |Microsoft 文档"  
[Webview2HowtoDebug]: ./howto/debug.md "如何通过 WebView2 | 进行调试Microsoft 文档"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "通过 Microsoft Edge 驱动程序自动化和测试 WebView2 |Microsoft 文档"  
[Webview2Releasenotes]: ./releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI 库3预览版 2 (2020 年7月) |Microsoft 文档"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge 支持的操作系统 |Microsoft 文档"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub" 

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "WebView2 |NuGet 库"  
