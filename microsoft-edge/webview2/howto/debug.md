---
description: 了解如何调试 WebView2 控件。
title: 开始调试 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 25a710796b499a78a43045266058029caa890b78
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119106"
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

Visual Studio 在 WebView2 应用程序中提供了用于 web 和本机代码的各种调试工具。  在 Visual Studio 部分中，主要焦点是调试 Web 视图控件，而在 Visual Studio 中调试的其他方法则照常可用。  使用以下过程仅在 Win32 应用程序或 Office 外接程序中调试 web 和本机代码。  

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
        
        :::image type="complex" source="./media/workloads.png" alt-text="DevTools 调试" lightbox="./media/workloads.png":::
            Visual Studio 修改工作负荷屏幕 :::image-end:::  
        
    1.  选择 **单个组件**。  
    1.  在 "搜索" 框中，输入 `JavaScript diagnostics` 。  
    1.  选择 " **JavaScript 诊断** " 设置。  
    1.  选择 " **修改**"。 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="DevTools 调试" lightbox="./media/indivcomp.png":::
           Visual Studio 修改单个组件选项卡  
        :::image-end:::  
        
1.  为 WebView2 应用程序启用脚本调试。  
    1.  在 WebView2 项目中，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **属性**"。  
    1.  在 " **配置" 属性**下，选择 " **调试**"。  
    1.  在 " **调试器类型**" 下，选择 " **JavaScript (WebView2") **。  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="DevTools 调试" lightbox="./media/enbjs.png":::
           Visual Studio **调试** 配置属性  
        :::image-end:::  
        
完成以下操作以调试你的 WebView2 应用程序。  

1.  若要在源代码中设置断点，请将光标悬停在行号的左侧，然后选择设置断点。  JS/TS 调试适配器不执行源路径映射。  您必须打开与您的 WebView2 相关联的完全相同的路径。  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="DevTools 调试" lightbox="./media/breakpoint.png"::: 
       Visual Studio 添加断点  
    :::image-end:::  
    
1.  若要运行调试器，请选择平台的位大小，然后选择 " **本地 Windows 调试器**" 旁边的绿色 "播放" 按钮。  应用程序运行，并且调试器连接到创建的第一个 WebView2 进程。  
    
    :::image type="complex" source="./media/run.png" alt-text="DevTools 调试" lightbox="./media/run.png"::: 
       Visual Studio **本地 Windows 调试器**  
    :::image-end:::  
    
1.  在 **调试控制台**中，查找来自调试器的输出。  
    
    :::image type="complex" source="./media/console.png" alt-text="DevTools 调试" lightbox="./media/console.png"::: 
       Visual Studio **调试控制台**  
    :::image-end:::  
    
## [Visual Studio Code](#tab/visualstudiocode)  

使用 Microsoft Visual Studio 代码调试在 WebView2 控件中运行的脚本。  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

在 Visual Studio 代码中，完成以下操作以调试你的代码。 

1.  你的项目必须具有 `launch.json` 文件。  如果你的项目没有 `launch.json` 文件，请复制以下代码片段并创建一个新 `launch.json` 文件。  
        
    ```json
        "name": "Hello debug world",
        "type": "pwa-msedge",
        "port": 9222, // The port value is optional, and the default value is 9222.
        "request": "launch",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",
        "env": {
            // Customize for your application location if needed
            "Path": "%path%;e:/path/to/your/application/location; "
        },
        "useWebView": true,
    ```  
        
1.  若要在源代码中设置断点，请将鼠标悬停在该行上，然后选择 `F9`
    
    :::image type="complex" source="./media/breakpointvs.png" alt-text="DevTools 调试" lightbox="./media/breakpointvs.png":::
       在 Visual Studio 代码中设置断点  
    :::image-end:::
    
    > [!NOTE]
    > 由于 Visual Studio 代码不执行源映射，因此请确保在 WebView2 使用的同一文件中设置断点。  如果路径不匹配，Visual Studio 代码不会暂停断点处运行的代码。  
    
1.  运行代码。  
    1.  在 " **运行** " 选项卡上，从下拉菜单中选择 "启动配置"。  
    1.  若要开始调试你的应用程序，请选择 "开始调试"，这是 "启动配置" 下拉列表旁边的绿色三角形。  
        
        :::image type="complex" source="./media/runvs.png" alt-text="DevTools 调试" lightbox="./media/runvs.png":::
           Visual Studio 代码运行选项卡  
        :::image-end:::  
        
1.  打开 **调试控制台** 以查看调试输出和错误。  
    
    :::image type="complex" source="./media/resultsvs.png" alt-text="DevTools 调试" lightbox="./media/resultsvs.png":::
       Visual Studio 代码调试控制台  
    :::image-end:::  
    
**高级设置**：  

*   定向的 Web 视图调试。 

    在某些 WebView2 应用程序中，你可以使用多个 WebView2 控件。 若要在此情况下选择要调试的 WebView2 控件，您可以使用目标 WebView2 调试 
    
    打开 `launch.json` 并完成以下操作以使用目标 Web 视图调试。  
    
    1.  确认 `useWebview` 参数已设置为 `true` 。  
    1.  添加 `urlFilter` 参数。  当 WebView2 控件导航到 URL 时， `urlFilter` 参数值用于比较 URL 中出现的字符串。  
    
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    调试应用程序时，可能需要从呈现过程的开头逐句通过代码。 如果你在网站上呈现网页，并且你无权访问源代码，则可以使用该 `?=value`  选项，因为网页忽略无法识别的参数。   
    
    > [!IMPORTANT]
    > 在 URL 中找到第一个匹配后，调试器停止。  不能同时调试两个 WebView2 控件，因为 CDP 端口由所有 WebView2 控件共享，并且使用单个端口号。  
    
*   调试正在运行的进程  
    
    你可能需要附加调试程序才能运行 WebView2 进程。 若要执行此操作，请在中将 `launch.json` `request` 参数更新为 `attach` 。
        
    ```json
        "name": "Hello debugging world",
        "type": "pwa-msedge",
        "port": 9222, 
        "request": "attach",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
        "env": {
            "Path": "%path%;e:/path/to/your/build/location; "  
        },
        "useWebView": true
    ```  
        
    你的 WebView2 控件必须打开 CDP 端口才能允许调试 WebView2 控件。  必须生成代码，以确保在启动调试程序之前，只有一个 WebView2 控件具有 Chrome) 端口 (的 "CDP" 开发人员协议。  
    
*   调试跟踪选项  
    
    将 `trace` 参数添加到 launch.json 以启用调试跟踪。  
    
    1.  添加 `trace` 参数。  
        
 
        
        :::row:::
           :::column span="":::
              ```json
                "name": "Hello debugging world",
                "type": "pwa-msedge",
                "port": 9222, 
                "request": "attach",
                "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
                "env": {
                "Path": "%path%;e:/path/to/your/build/location; "  
                },
                "useWebView": true
                ,"trace": true  // Turn on  debug tracing, and save the output to a log file.
              ```  
              
              :::image type="complex" source="./media/tracelog.png" alt-text="DevTools 调试" lightbox="./media/tracelog.png":::
                 将调试输出保存到日志文件  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text="DevTools 调试" lightbox="./media/verbose.png":::
                 启用了详细跟踪的 Visual Studio 代码调试输出  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   调试 Office 加载项。
    
    如果你正在调试 Office 加载项，请在单独的 Visual Studio 代码实例中打开加载项源代码。  在 WebView2 应用程序中打开 launch.js，然后添加以下代码片段以将调试程序附加到 Office 外接程序。
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   调试器疑难解答  
    
    使用调试程序时可能会遇到以下情况。  

    *   调试器不会在断点处停止，并且你拥有调试输出。  若要解决此问题，请确认带有断点的文件是由 WebView2 控件使用的同一文件。  调试器不执行源路径映射。  
    *   无法附加到正在运行的进程，并且收到超时错误。  若要解决此问题，请确认 WebView2 控件已打开 CDP 端口。  确保  `additionalBrowserArguments`  注册表中的值正确，或者选项正确。  有关详细信息，请参阅 [additionalBrowserArguments for 新][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] 和 [additionalBrowserArguments for Win32][Webview2ReferenceWin32Webview2IdlParameters]。  
    
* * *  


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

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions AdditionalBrowserArguments 属性 (WebView2) |Microsoft 文档"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment-Globals |Microsoft 文档"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft 文档"  
[Webview2MainNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门-Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能-适用于 Visual Studio 代码的 JavaScript 调试程序-microsoft/vscode-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) Web 视图应用程序-Visual Studio 代码-Microsoft Edge 的调试器-microsoft/vscode-debug2 |GitHub"  
