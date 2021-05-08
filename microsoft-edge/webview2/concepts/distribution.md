---
description: 使用 WebView2 发布应用时Microsoft Edge选项
title: WebView2 Microsoft Edge分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 97ede968e066c572bb1b22e10ed7e758e38e3ca4
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535697"
---
# <a name="distribution-of-apps-using-webview2"></a>使用 WebView2 分发应用  

分发 WebView2 应用时，请确保在应用启动前存在支持 Web 平台 [WebView2][Webview2Installer]运行时。  本文介绍了如何 \ (开发人员\) 安装 WebView2 运行时，以及如何对 WebView2 应用使用两种分发模式[：Evergreen](#evergreen-distribution-mode)和 Fixed [Version。](#fixed-version-distribution-mode)  

## <a name="evergreen-distribution-mode"></a>常青分发模式  

> [!NOTE]
> 建议大多数开发人员使用常青分发模式。  

常青分发模式可确保你的应用充分利用最新的功能和安全更新。  它具有以下特征。  

*   基础 Web 平台 \ (WebView2 运行时\) 自动更新，无需额外工作。  
*   所有使用 Evergreen 分发模式的应用都使用 Evergreen WebView2 运行时的共享副本，从而节省磁盘空间。  
    
### <a name="understanding-the-webview2-runtime"></a>了解 WebView2 运行时  

WebView2 运行时是一个可再发行运行时，并用作 WebView2 应用的支持 Web 平台。  此概念类似于 Visual C++/.NET 应用的 .NET 运行时。  运行时包含经过修改Microsoft Edge \ (Chromium\) 已针对应用进行优化和测试的二进制文件。  运行时在安装时不会显示为用户可见的浏览器。  例如，用户没有浏览器桌面快捷方式或"开始"菜单条目。  

在开发和测试期间，你可以将任一平台用作支持 Web 平台。  

*   WebView2 运行时  
*   任何预览体验成员 \ (非稳定\) Microsoft Edge \ (Chromium\) 浏览器通道  
    
在生产环境中，在应用启动之前，必须确保运行时存在于用户设备上。  Microsoft Edge Stable 渠道不可用于 WebView2。  该决定可防止应用在生产中依赖浏览器。

请勿依赖浏览器，因为：  

*   Microsoft Edge \ (Chromium\) 不一定存在于所有用户设备上。  例如，与 Windows Update 断开连接或不由 Microsoft 直接管理的设备 \ (大部分 Enterprise 和 EDU 市场\) 可能没有浏览器。  允许分发 WebView2 运行时可以避免依赖浏览器作为应用的先决条件。  
*   浏览器和应用具有不同的用例，因此依赖浏览器可能会对应用产生意外的负面影响。  例如，IT 管理员可以对浏览器进行版本控制，以确保内部网站兼容性。  WebView2 运行时允许应用在主动管理浏览器更新时保持常青。  
*   与浏览器相反，运行时针对应用方案进行开发和测试，并且在某些情况下可能包括浏览器中尚未提供的 Bug 修复。  
    
今后，Evergreen WebView2 运行时计划提供未来版本Windows。  将运行时与生产应用一起部署，直到运行时更普遍可用。  

### <a name="deploying-the-evergreen-webview2-runtime"></a>部署 Evergreen WebView2 运行时  

设备上的所有 Evergreen 应用只需安装一次 Evergreen WebView2 运行时。  WebView2 运行时下载页上提供了 [许多工具][Webview2Installer]。  以下工具可帮助你部署常青运行时。  

*   WebView2 运行时引导程序是一个小的 \ (大约 2 MB\) 安装程序。  WebView2 运行时引导程序从与用户设备体系结构匹配的 Microsoft 服务器下载并安装 Evergreen Runtime。  
*   使用链接以编程方式下载引导程序。  
*   WebView2 运行时独立安装程序是在脱机环境中安装 Evergreen WebView2 运行时的完整安装程序。  
    
目前，引导程序和独立安装程序仅支持每台计算机安装，这需要提升。  如果安装程序在未提升权限的情况下运行，系统将提示用户提升权限。  

使用以下工作流来确保在应用启动之前已安装运行时。  可以根据方案调整工作流。  示例代码在示例 [存储库中提供][GitHubMicrosoftedgeWebView2samplesWebview2Deployment]。  

#### <a name="online-only-deployment"></a>仅联机部署  

如果你有假定用户具有 Internet 访问权限的仅联机部署方案，请完成以下步骤。  

1.  在应用设置期间，请确保已安装运行时。  若要进行验证，请完成以下操作之一。  
    *   检查 `pv (REG_SZ)` 注册表项是否存在且不是 `null` 或为空。  在  `pv (REG_SZ)` 下列位置查找。  
        
        在 64 位Windows  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        在 32 位Windows  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。  
1.  如果未安装运行时，请使用链接以编程方式下载引导程序。  
1.  通过静默安装从提升的进程或命令提示符调用 `MicrosoftEdgeWebview2Setup.exe /silent /install` 引导程序。  
    
以前的工作流具有以下优点。  

*   仅在需要或不需要打包安装程序时安装运行时。  
*   引导程序自动检测设备体系结构并安装匹配的运行时。  
*   以静默方式安装运行时。  
    
还可以选择将引导程序打包到你的应用中，而不是以编程方式按需下载它。  

#### <a name="offline-deployment"></a>脱机部署  

如果你有应用部署必须完全脱机工作的脱机部署方案，请完成以下步骤。  

1.  下载 [独立安装程序][Webview2Installer]。  
1.  在应用安装程序或更新程序中包括安装程序。  
1.  在应用设置期间，请确保已安装运行时。  若要进行验证，请完成以下操作之一。  
    *   检查 `pv (REG_SZ)` 注册表项是否存在且不是 `null` 或为空。  在  `pv (REG_SZ)` 下列位置查找。  
        
        在 64 位Windows  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        在 32 位Windows  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。  
1.  如果未安装运行时，请运行独立安装程序。  如果要运行无提示安装，请从提升的进程运行安装程序，或者复制并运行以下命令。  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### <a name="stay-compatible-in-evergreen-mode"></a>在常青模式下保持兼容  

Web 在不断演变。  Evergreen WebView2 运行时保持最新状态，以提供最新功能和安全修补程序。  若要确保应用与 Web 保持兼容，应设置测试基础结构。  

非稳定 Microsoft Edge渠道 \ (Beta/Dev/Canary\) 可快速了解 WebView2 运行时即将出现的内容。  就像开发 web 应用程序Microsoft Edge一样，你应该定期测试 WebView2 应用。  针对其中一个非稳定渠道测试 WebView2 应用，并更新应用或报告问题 [（如果][GithubMicrosoftedgeWebviewfeedback] 出现问题）。 通常推荐使用 Dev 和 Beta 渠道。  若要帮助你确定哪个频道正确，请导航到"Microsoft Edge[概述"。][DeployEdgeMicrosoftEdgeChannels]  你可以[下载测试环境中][DownloadNonstableEdge]Microsoft Edge不稳定的渠道，并使用或环境变量来指示测试 `regkey` 应用的通道首选项。  有关详细信息，请导航到 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]。  您还可以使用 [WebDriver 自动][HowToWebdriver] 执行 WebView2 测试。

## <a name="fixed-version-distribution-mode"></a>固定版本分发模式   

对于具有严格兼容性要求的限制环境，请考虑使用固定版本分发模式。  使用固定版本分发模式选择并打包特定版本的 WebView2 运行时。  你可以为你的应用指定运行时更新的时间。  固定版本分发模式不会接收任何自动更新。 计划更新你的应用和运行时。  

> [!NOTE] 
> 固定版本分发模式以前称为自带发布。  

若要使用固定版本模式，请完成以下操作

1.  [下载][Webview2Installer] 固定版本程序包。 
1.  使用命令行或 WinRAR 等 `expand {path to the package} -F:* {path to the destination folder}` 工具解压缩包。 避免通过文件资源管理器解压缩，因为它可能无法生成正确的文件夹结构。  
1.  在项目中包括解压缩的固定版本二进制文件。  
1.  指示创建 WebView2 环境时固定版本二进制文件的路径。  
    *   对于 Win32 C/C++，可以使用 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 函数创建环境。  使用 `browserExecutableFolder` 参数指示包含 的文件夹的路径 `msedgewebview2.exe` 。  
    *   对于 .NET，您可以执行以下任一选项来指定环境。  
        
        > [!NOTE]
        > 必须指定环境，WebView2 `Source` 属性才能生效。  
        
        *   在 `CreationProperties` [][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / WebView2 (设置 \) WPF[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) 属性。  使用 `BrowserExecutableFolder` `CoreWebView2CreationProperties` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) 类中的成员指示固定版本二进制文件的路径。  
        *   使用 `EnsureCoreWebView2Async` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / [WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) 指定环境。  使用 `browserExecutableFolder` [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] 中的 参数指示固定版本二进制文件的路径。  
1.  将固定版本二进制文件打包并随你的应用一起提供。  根据情况更新二进制文件。  
    
### <a name="known-issues-for-fixed-version"></a>固定版本的已知问题  

与 Evergreen 运行时相比，固定版本没有安装过程，[这会导致][MicrosoftPlayReady]Microsoft PlayReady的情况下无法工作。  可以通过完成以下操作来缓解此问题。  

1.  找到在用户设备上部署固定版本程序包的路径，如以下位置。
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  在用户设备上运行以下命令。

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  PlayReady 现在应在用户的设备上运行。  在" **固定** 版本"文件夹 **的"** 安全"选项卡中，它应包括 和 `ALL APPLICATION PACKAGES` 的权限 `ALL RESTRICTED APPLICATION PACKAGES` 。  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady 的权限" lightbox="../media/play-ready-permission.png":::
        PlayReady 的权限  
    :::image-end:::  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "了解浏览器版本和 WebView2 |Microsoft Docs"  
[HowToWebdriver]: ../how-to/webdriver.md "使用驱动程序测试工具自动Microsoft Edge WebView2 |Microsoft Docs"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Docs"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - 全局|Microsoft Docs"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "频道Microsoft Edge概述|Microsoft Docs"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "CreateAsync - Microsoft.Web.WebView2.Core.CoreWebView2Environment 类|Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async -Microsoft.Web.WebView2.Wpf.WebView2 类|Microsoft Docs"  
[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async - Microsoft.Web.WebView2.WinForms.WebView2 类|Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties - Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties 类|Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 类|Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "CreationProperties - Microsoft.Web.WebView2.Wpf.WebView2 类|Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "Microsoft.Web.WebView2.WinForms.WebView2 类|Microsoft Docs"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序|Microsoft 开发人员"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈|GitHub"  

[GitHubMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 部署 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
