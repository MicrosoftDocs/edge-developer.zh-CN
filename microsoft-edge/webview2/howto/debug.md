---
description: 了解如何调试 WebView2 控件。
title: 开始调试 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/13/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 15171147b847b1d41cd603efed1b8ee42185dc29
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010696"
---
# 开始调试 WebView2 应用程序  

Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和工具的优势。  开发 WebView2 应用程序时，应调试你的应用程序。  本文概述了用于在 WebView2 应用程序中调试 web 和本机代码的不同工具。  

## [Microsoft Edge 开发工具](#tab/devtools)  

使用 [Microsoft edge (Chromium) 开发人员工具][DevtoolsGuideChromiumMain] 来调试在 WebView2 控件中显示的 web 内容，其方式与你对 Microsoft Edge 中显示的其他网页的调试方式相同。  若要打开 DevTools，请将焦点置于 "Web 视图" 控件上，然后使用下列操作之一。  

*   选择 `F12` 。  
*   选择 `Ctrl` + `Shift` + `I` 。  
*   打开上下文菜单 \ (右键单击 \ ) 并选择 `Inspect` 。  

有关详细信息，请参阅 [DevTools 概述][DevtoolsGuideChromiumMain]。  

:::image type="complex" source="./media/f12.png" alt-text="DevTools 调试" lightbox="./media/f12.png":::
   DevTools 调试  
:::image-end:::  

## [Visual Studio](#tab/visualstudio)  

Visual Studio 在 WebView2 应用程序中提供了用于 web 和本机代码的各种调试工具。  在 Visual Studio 部分中，主要关注的是调试 Web 视图控件，但在 Visual Studio 中调试的其他方法通常是可用的。  使用以下过程仅在 Win32 应用程序或 Office 外接程序中调试 web 和本机代码。  

> [!IMPORTANT]
> 在附加了本机调试器的 Visual Studio 中调试应用程序时，选择 " `F12` 可能会触发本机调试器，而不是开发工具"。  选择 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ (右键单击 \ ) 以避免这种情况。  

开始之前，请确保满足以下要求。  

*   若要调试脚本，应用必须从 Visual Studio 内部启动。  
*   不能将调试程序附加到正在运行的 WebView2 进程。  
*   安装 Visual Studio 2019 版本16.4 预览版2或更高版本。  

在 Visual Studio 中安装和设置脚本调试程序工具。  

1.  完成以下操作以在**桌面开发中用 c + +** 安装**JavaScript 诊断**组件。  

    1. 在 Windows 资源管理器栏中，键入 `Visual Studio Installer` 。  
    1. 选择 " **Visual Studio 安装程序** " 将其打开。  
    1. 在 Visual Studio 安装程序的已安装版本上，选择 " **更多** " 按钮，然后选择 " **修改**"。  
    1. 在 Visual Studio 中的 " **工作量**" 下，选择 " **在 c + + 中的桌面开发** " 设置。  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio 修改工作负荷屏幕" lightbox="./media/workloads.png":::
            Visual Studio 修改工作负荷屏幕 :::image-end:::  
        
    1.  选择 **单个组件**。  
    1.  在 "搜索" 框中，输入 `JavaScript diagnostics` 。  
    1.  选择 " **JavaScript 诊断** " 设置。  
    1.  选择 " **修改**"。 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studio 修改单个组件选项卡" lightbox="./media/indivcomp.png":::
           Visual Studio 修改单个组件选项卡  
        :::image-end:::  
        
1.  为 WebView2 应用程序启用脚本调试。  
    1.  在 WebView2 项目中，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **属性**"。  
    1.  在 " **配置" 属性**下，选择 " **调试**"。  
    1.  在 " **调试器类型**" 下，选择 " **JavaScript (WebView2") **。  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studio 调试配置属性" lightbox="./media/enbjs.png":::
           Visual Studio **调试** 配置属性  
        :::image-end:::  
        
完成以下操作以调试你的 WebView2 应用程序。  

1.  若要在源代码中设置断点，请将光标悬停在行号的左侧，然后选择设置断点。  JS/TS 调试适配器不执行源路径映射。  您必须打开与您的 WebView2 相关联的完全相同的路径。  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studio 添加断点" lightbox="./media/breakpoint.png"::: 
       Visual Studio 添加断点  
    :::image-end:::  
    
1.  若要运行调试器，请选择平台的位大小，然后选择 " **本地 Windows 调试器**" 旁边的绿色 "播放" 按钮。  应用程序运行，并且调试器连接到创建的第一个 WebView2 进程。  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio 本地 Windows 调试器" lightbox="./media/run.png"::: 
       Visual Studio **本地 Windows 调试器**  
    :::image-end:::  
    
1.  在 **调试控制台**中，查找来自调试器的输出。  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio 调试控制台" lightbox="./media/console.png"::: 
       Visual Studio **调试控制台**  
    :::image-end:::  
    
* * *  

## 另请参阅  

*   若要开始使用 WebView2，请参阅 [WebView2 入门指南][Webview2MainGettingStarted]。  
*   有关 WebView2 功能的完整示例，请参阅 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。
*   有关 WebView2 Api 的更多详细信息，请参阅 [API 参考][Webview2ApiReference]。
*   有关 WebView2 的详细信息，请参阅 [WebView2 资源][Webview2MainNextSteps]。

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发人员工具"  

[Webview2ReferenceDotnet09628MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: ../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environmentoptions.md#additionalbrowserarguments "AdditionalBrowserArguments-0.9.515-WebView2 for CoreWebView2EnvironmentOptions 类 |Microsoft 文档"  
[Webview2ReferenceWin3209622Webview2IdlParameters]: ../reference/win32/0-9-622/webview2-idl.md#createcorewebview2environment  "CreateCoreWebView2Environment-Globals |Microsoft 文档"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft 文档"  
[Webview2MainNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门-Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能-适用于 Visual Studio 代码的 JavaScript 调试程序-microsoft/vscode-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) Web 视图应用程序-Visual Studio 代码-Microsoft Edge 的调试器-microsoft/vscode-debug2 |GitHub"  
