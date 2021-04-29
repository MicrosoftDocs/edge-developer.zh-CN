---
description: 使用 Microsoft Edge WebView2 控件在 Win32、.NET 和 UWP 应用中托管 Web 内容
title: Microsoft Edge WebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、edge html、Windows Forms、WinForms、WPF、.NET、WinUI、Project 一线
ms.openlocfilehash: ec22edbc838f57c2f9c591a0f48298d61dce484c
ms.sourcegitcommit: b51df5036642060525e03cd744b7d35726326abe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "11526071"
---
# <a name="introduction-to-microsoft-edge-webview2"></a>Microsoft Edge WebView2 简介  

Microsoft Edge WebView2 控件使你能够将 Web 技术 \ (HTML、CSS 和 JavaScript\) 嵌入本机应用中。  WebView2 控件使用 [Microsoft Edge (Chromium ][MicrosoftedgeinsiderMain]) 作为呈现引擎，以在本机应用中显示 Web 内容。  使用 WebView2，你可以将 Web 代码嵌入本机应用的不同部分。  在单个 WebView 实例中生成所有本机应用。  若要了解如何开始生成 WebView2 应用，请导航到"[入门"。](#getting-started)  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="什么是 WebView？" lightbox="./media/WebView2/whatwebview.png":::
   什么是 WebView？  
:::image-end:::  

## <a name="hybrid-app-approach"></a>混合应用方法  

开发人员通常必须在生成 Web 应用还是生成本机应用之间做出决定。  该决策将决定范围与电源之间的选择。  Web 应用可广泛覆盖。  作为 Web 开发人员，您可以跨不同平台重用大部分代码。  若要访问本机平台的所有功能，请使用本机应用。  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web 本机" lightbox="./media/WebView2/webnative.png":::
   Web 本机  
:::image-end:::  

混合应用使开发人员能够享受两全其美。  混合应用开发人员受益于以下优势。  

*   Web 平台的优势和强度。  
*   本机平台的功能和完整功能。  
    
## <a name="webview2-benefits"></a>WebView2 优势   

<!--  
:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="WebView reasons" lightbox="./media/WebView2/webviewreasons.png":::
   WebView reasons  
:::image-end:::  
-->  

:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-web-ecosystem-skillset.msft.png":::  
      **Web 生态系统 \&技能集**  
      利用 Web 生态系统内存在的整个 Web 平台、库、工具和人才。  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-rapid-innovation.msft.png":::  
      **快速创新**  
      Web 开发允许更快地部署和迭代。  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-windows-7-8-10-support.msft.png":::  
      **Windows 7、8 和 10 支持**  
      支持跨 Windows 7、Windows 8 和 Windows 10 实现一致的用户体验。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-native-capabilities.msft.png":::  
      **本机功能**  
      访问完整的本机 API 集。  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-code-sharing.msft.png":::  
      **代码共享**  
      向代码库添加 Web 代码可增强跨多个平台的重用。  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-microsoft-support.msft.png":::  
      **Microsoft 支持**  
      当 WebView2 在通用版本 \ (GA\) 发布时，Microsoft 提供支持并添加新功能) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-evergreen.msft.png":::  
      **常青分布**  
      依靠具有常规平台更新和安全修补程序的最新版本的 Chromium。  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-fixed.msft.png":::  
      **已修复**  
      \ (即将推出\) 选择将 Chromium 位打包到应用中。  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-incremental-adoption.msft.png":::  
      **增量采用**  
      将 Web 组件分片添加到应用。  
   :::column-end:::
:::row-end:::  

## <a name="getting-started"></a>入门  

若要使用 WebView2 控件生成和测试应用，你需要 <!--both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and  -->安装的[WebView2 SDK。][NugetPackagesMicrosoftWebWebView2]  选择下列选项之一开始。  

*   [Win32 C/C++ 入门][Webview2GettingstartedWin32]  
*   [WPF 入门][Webview2GettingstartedWpf]  
*   [WinForms 入门][Webview2GettingstartedWinforms]  
*   [WinUI3 入门][Webview2GettingstartedWinui]  

[WebView2 示例][GithubMicrosoftedgeWebview2samples]存储库包含演示所有 WebView2 SDK 功能和 API 使用模式的示例。  随着更多功能添加到 WebView2 SDK 中，示例应用将更新。  

## <a name="supported-platforms"></a>支持的平台  

通用 \ (GA\) 或预览版可在以下编程环境中使用。  

*   Win32 C/C++ \ (GA\)   
*   .NET Framework 4.5 或更高版本  
*   .NET Core 3.1 或更高版本  
*   .NET 5  
*   [WinUI 3.0][UwpToolkitsWinui3] \ (Preview\)   

您可以在以下版本的 Windows 中运行 WebView2 应用。  

*   Windows 10  
*   Windows 8.1  
*   Windows 7 \*\*  
*   Windows Server 2019  
*   Windows Server 2016  
*   WindowsServer 2012  
*   Windows Server 2012 R2  
*   Windows Server 2008 R2 \*\*  

> [!IMPORTANT]
> \*\* Windows 7 和 Windows Server 2008 R2 的 WebView2 支持与 Microsoft Edge 具有相同的支持周期。  有关详细信息，请导航到 [Microsoft Edge 支持的操作系统][DeployedgeMicrosoftEdgeSupportedOS]。  

## <a name="next-steps"></a>后续步骤  

若要详细了解如何生成和部署 WebView2 应用，请查看概念文档和帮助指南。  

#### <a name="concepts"></a>概念  

*   [了解 WebView2 SDK 版本][Webview2ConceptsVersioning]  
*   [使用 WebView2 分发应用][Webview2ConceptsDistribution]  
*   [开发安全 WebView2 应用的最佳方案][Webview2ConceptsSecurity]  
*   [在 WebView2 应用中管理用户数据文件夹][Webview2ConceptsUserdatafolder]  
 
#### <a name="how-to-guides"></a>How-To指南  

*   [如何使用 WebView2 调试][Webview2HowtoDebug]  
*   [使用 Microsoft Edge 驱动程序自动执行和测试 WebView2][Webview2HowtoWebdriver]  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 Microsoft Edge WebView 团队联系  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 应用程序分配|Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "开发安全的 WebView2 应用和 web |Microsoft Docs"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "管理用户数据文件夹|Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "了解 WebView2 SDK |Microsoft Docs"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 应用程序|Microsoft Docs"  
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows 窗体应用中的 WebView2 入门 (预览) |Microsoft Docs"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WinUI3 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2HowtoDebug]: ./howto/debug.md "如何使用 WebView2 |Microsoft Docs"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "使用 Microsoft Edge 驱动程序工具自动执行和测试 WebView2 |Microsoft Docs"  
[Webview2Releasenotes]: ./releasenotes.md "WebView2 SDK |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI Library 3 Preview 2 (2020 年 7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge 支持的操作系统|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 |NuGet 库"  
