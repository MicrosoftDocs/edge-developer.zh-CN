---
description: 使用 WebView2 控件在 Win32、.NET 和 UWP 应用中Microsoft Edge Web 内容
title: Microsoft EdgeWebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、edge html、Windows Forms、WinForms、WPF、.NET、WinUI、Project
ms.openlocfilehash: 9c1aa073294fc649223da19c44850dc4335f6c00
ms.sourcegitcommit: 7f7922dbb6af87ecac1378d18359125770c5b8e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536823"
---
# <a name="introduction-to-microsoft-edge-webview2"></a>WebView2 Microsoft Edge简介  

WebView2 Microsoft Edge WebView2 控件允许你将 Web 技术 \ (HTML、CSS 和 JavaScript\) 嵌入本机应用中。  WebView2 控件使用[Microsoft Edge (Chromium) ][MicrosoftedgeinsiderMain]作为呈现引擎，以在本机应用中显示 Web 内容。  使用 WebView2，你可以将 Web 代码嵌入本机应用的不同部分。  在单个 WebView 实例中生成所有本机应用。  若要了解如何开始生成 WebView2 应用，请导航到["入门"。](#get-started)  

:::image type="complex" source="./media/WebView2/what-webview.png" alt-text="什么是 WebView？" lightbox="./media/WebView2/what-webview.png":::
   什么是 WebView？  
:::image-end:::    

## <a name="hybrid-app-approach"></a>混合应用方法  

开发人员通常必须在生成 Web 应用还是生成本机应用之间做出决定。  该决策将决定范围与电源之间的选择。  Web 应用可广泛覆盖。  作为 Web 开发人员，您可以跨不同平台重用大部分代码。  若要访问本机平台的所有功能，请使用本机应用。  

:::image type="complex" source="./media/WebView2/web-native.png" alt-text="Web 本机" lightbox="./media/WebView2/web-native.png":::
   Web 本机  
:::image-end:::    

混合应用使开发人员能够享受两全其美。  混合应用开发人员受益于以下优势。  

*   Web 平台的优势和强度。  
*   本机平台的功能和完整功能。  
    
## <a name="webview2-benefits"></a>WebView2 优势   

:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-web-ecosystem-skillset-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-rapid-innovation-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-windows-7-8-10-support-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="web-ecosystem--skillset"></a>Web 生态系统&技能集  
   :::column-end:::
   :::column span="1":::
      ### <a name="rapid-innovation"></a>快速创新  
   :::column-end:::
   :::column span="1":::
      ### <a name="windows-7-8-and-10-support"></a>Windows 7、8 和 10 支持  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      利用 Web 生态系统内存在的整个 Web 平台、库、工具和人才。  
   :::column-end:::
   :::column span="1":::
      Web 开发允许更快地部署和迭代。  
   :::column-end:::
   :::column span="1":::
      支持跨 Windows 7、Windows 8 和 Windows 10。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-native-capabilities-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-code-sharing-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-microsoft-support-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="native-capabilities"></a>本机功能  
   :::column-end:::
   :::column span="1":::
      ### <a name="code-sharing"></a>代码共享  
   :::column-end:::
   :::column span="1":::
      ### <a name="microsoft-support"></a>Microsoft 支持  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      访问完整的本机 API 集。  
   :::column-end:::
   :::column span="1":::
      向代码库添加 Web 代码可增强跨多个平台的重用。  
   :::column-end:::
   :::column span="1":::
      当 WebView2 在通用版本 \ (GA\) 发布时，Microsoft 提供支持并添加新功能) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-evergreen-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-fixed-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-incremental-adoption-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="evergreen-distribution"></a>常青分布  
   :::column-end:::
   :::column span="1":::
      ### <a name="fixed"></a>已修复  
   :::column-end:::
   :::column span="1":::
      ### <a name="incremental-adoption"></a>增量采用  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      依赖最新版 Chromium定期平台更新和安全修补程序。  
   :::column-end:::
   :::column span="1":::
      \ (即将推出\) 选择在应用中打包Chromium位。  
   :::column-end:::
   :::column span="1":::
      将 Web 组件分片添加到应用。  
   :::column-end:::
:::row-end:::  

## <a name="get-started"></a>入门  

若要使用 WebView2 控件生成和测试应用，你需要 <!--both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and  -->安装的[WebView2 SDK。][NugetPackagesMicrosoftWebWebView2]  选择下列选项之一开始。  

*   [入门 Win32 C/C++][Webview2GetStartedWin32]  
*   [入门 WPF][Webview2GetStartedWpf]  
*   [入门 WinForms][Webview2GetStartedWinforms]  
*   [入门 WinUI3][Webview2GetStartedWinui]  
    
[WebView2 示例][GithubMicrosoftedgeWebview2samples]存储库包含演示所有 WebView2 SDK 功能和 API 使用模式的示例。  随着更多功能添加到 WebView2 SDK 中，示例应用将更新。  

## <a name="supported-platforms"></a>支持的平台  

通用 \ (GA\) 或预览版可在以下编程环境中使用。  

*   Win32 C/C++ \ (GA\)   
*   .NET Framework 4.5 或更高版本  
*   .NET Core 3.1 或更高版本  
*   .NET 5  
*   [WinUI 3.0][UwpToolkitsWinui3] \ (Preview\)   
    
你可以运行以下版本的 WebView2 Windows。  

*   Windows 10  
*   Windows 8.1  
*   Windows 7 \*\*  
*   Windows Server 2019  
*   Windows Server 2016  
*   WindowsServer 2012  
*   Windows Server 2012 R2  
*   WindowsServer 2008 R2 \*\*  
    
> [!IMPORTANT]
> \*\* 对 Windows 7 和 Windows Server 2008 R2 的 WebView2 支持与 Microsoft Edge。  有关详细信息，请导航到Microsoft Edge[支持的操作系统。][DeployedgeMicrosoftEdgeSupportedOS]  

## <a name="next-steps"></a>后续步骤  

若要详细了解如何生成和部署 WebView2 应用，请查看概念文档和帮助指南。  

### <a name="concepts"></a>概念  

*   [了解 WebView2 SDK 版本][Webview2ConceptsVersioning]  
*   [使用 WebView2 分发应用][Webview2ConceptsDistribution]  
*   [开发安全 WebView2 应用的最佳方案][Webview2ConceptsSecurity]  
*   [在 WebView2 应用中管理用户数据文件夹][Webview2ConceptsUserDataFolder]  
 
### <a name="how-to-guides"></a>How-To指南  

*   [如何使用 WebView2 调试][Webview2HowToDebug]  
*   [使用驱动程序自动化和测试 WebView2 Microsoft Edge驱动程序][Webview2HowToWebdriver]  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 WebView 团队Microsoft Edge联系  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 应用程序分配|Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "开发安全的 WebView2 应用和 web |Microsoft Docs"  
[Webview2ConceptsUserDataFolder]: ./concepts/user-data-folder.md "管理用户数据文件夹|Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "了解 WebView2 SDK |Microsoft Docs"  
[Webview2GetStartedWin32]: ./get-started/win32.md "WebView2 |Microsoft Docs"  
[Webview2GetStartedWinforms]: ./get-started/winforms.md "Windows Forms 应用中的 WebView2 (预览) |Microsoft Docs"  
[Webview2GetStartedWinui]: ./get-started/winui.md "WinUI3 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2GetStartedWpf]: ./get-started/wpf.md "WPF 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2HowToDebug]: ./how-to/debug.md "如何使用 WebView2 |Microsoft Docs"  
[Webview2HowToWebdriver]: ./how-to/webdriver.md "使用驱动程序测试工具自动Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2ReleaseNotes]: ./release-notes.md "WebView2 SDK |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "WindowsUI Library 3 Preview 2 (2020 年 7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge支持的操作系统|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge预览体验成员"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载Microsoft Edge预览体验成员"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 |NuGet库"  
