---
description: 了解如何调试 WebView2 控件。
title: 开始调试 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 01cd67897f7041bca0cedcee2cc3242f3ebcc962
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535820"
---
# <a name="get-started-debugging-webview2-apps"></a>开始调试 WebView2 应用  

Microsoft Edge WebView2 控件的目标是将 Web 和本机应用开发功能和工具的最佳组合在一起。  开发 WebView2 应用时，应调试应用。  本文概述了用于调试 WebView2 应用中的 Web 和本机代码的不同工具。  

## [<a name="microsoft-edge-devtools"></a>Microsoft Edge 开发工具](#tab/devtools)  

使用 [Microsoft Edge (Chromium) ][DevtoolsGuideChromiumMain] 开发人员工具调试 WebView2 控件中显示的 Web 内容，方式与为 Microsoft Edge 中显示的其他网页进行调试的方式相同。  若要打开 DevTools，请设置 WebView 控件的焦点，然后使用以下操作之一。  

*   选择 `F12`。  
*   选择 `Ctrl` + `Shift` + `I` 。  
*   打开上下文菜单 \(右键单击\) 并选择 `Inspect` 。  
    
有关详细信息，请导航到["DevTools 概述"。][DevtoolsGuideChromiumMain]  

:::image type="complex" source="./media/f12.png" alt-text="DevTools 调试" lightbox="./media/f12.png":::
   DevTools 调试  
:::image-end:::    

## [<a name="visual-studio"></a>Visual Studio](#tab/visualstudio)  

Visual Studio WebView2 应用中为 Web 和本机代码提供各种调试工具。  在Visual Studio部分中，主要焦点是调试 WebView 控件，但其他调试方法Visual Studio一样可用。  使用以下过程仅调试 Win32 应用或 Office 外接程序中的 Web 和本机代码。  

> [!IMPORTANT]
> 当你在附加了本机调试Visual Studio中调试应用时，选择可能会触发本机 `F12` 调试器，而不是开发人员工具。  Select `Ctrl` + `Shift` + `I` ， or use the context menu \(right-click\) to avoid the situation.  

开始之前，请确保满足以下要求。  

*   若要调试脚本，必须从应用程序内启动Visual Studio。  
*   无法将调试器附加到正在运行的 WebView2 进程。  
*   安装 Visual Studio 2019 版本 16.4 预览版 2 或更高版本。  
    
安装并设置脚本调试器工具Visual Studio。  

1.  完成以下操作以使用 C++ 在桌面开发中安装 **JavaScript** **诊断组件**。  
    1.  在 Windows 资源管理器栏中，键入 `Visual Studio Installer` 。  
    1.  选择 **Visual Studio安装程序** "以打开它。  
    1.  在"Visual Studio安装程序"的已安装版本上，选择"更多 **"按钮，** 然后选择"修改 **"。**  
    1.  In Visual Studio， under **Workloads，** choose the **Desktop Development in C++** setting.  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio修改工作负载屏幕" lightbox="./media/workloads.png":::
            Visual Studio修改工作负载屏幕
        :::image-end:::  
        
    1.  选择 **"单个组件"。**  
    1.  在搜索框中，输入 `JavaScript diagnostics` 。  
    1.  选择 **"JavaScript 诊断"** 设置。  
    1.  选择 **"修改"。** 
        
        :::image type="complex" source="./media/indiv-comp.png" alt-text="Visual Studio"修改单个组件选项卡" lightbox="./media/indiv-comp.png":::
           Visual Studio"修改单个组件"选项卡  
        :::image-end:::  
        
1.  为 WebView2 应用启用脚本调试。  
    1.  在 WebView2 项目中，打开上下文菜单 \(右键单击\) ，然后选择"属性 **"。**  
    1.  在"**配置属性"下**，选择 **"调试"。**  
    1.  在调试**器类型下**，选择 **"JavaScript (WebView2) "。 **  
        
        :::image type="complex" source="./media/enb-js.png" alt-text="Visual Studio调试配置属性" lightbox="./media/enb-js.png":::
           Visual Studio **调试** 配置属性  
        :::image-end:::  
        
完成以下操作以调试 WebView2 应用。  

1.  若要在源代码中设置断点，请将鼠标悬停在行号的左侧，然后选择设置断点。  JS/TS 调试适配器不执行源路径映射。  必须打开与 WebView2 关联的完全相同的路径。  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studio添加断点" lightbox="./media/breakpoint.png"::: 
       Visual Studio添加断点  
    :::image-end:::  
    
1.  若要运行调试器，请选择平台的位大小，然后选择"本地 Windows 调试器"旁边的绿色播放 **按钮**。  应用运行，调试程序连接到创建的第一个 WebView2 进程。  
    
    :::image type="complex" source="./media/run.png" alt-text="Visual Studio本地 Windows 调试器" lightbox="./media/run.png"::: 
       Visual Studio **本地 Windows 调试器**  
    :::image-end:::  
    
1.  在 **调试控制台中**，查找调试器的输出。  
    
    :::image type="complex" source="./media/console.png" alt-text="Visual Studio调试控制台" lightbox="./media/console.png"::: 
       Visual Studio **调试控制台**  
    :::image-end:::  
    
## [<a name="visual-studio-code"></a>Visual Studio Code](#tab/visualstudiocode)  

使用 Microsoft Visual Studio 代码调试在 WebView2 控件中运行的脚本。  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

在Visual Studio代码"中，完成以下操作以调试代码。 

1.  您的项目需要具有 `launch.json` 文件。  如果您的项目没有文件，请复制以下代码段 `launch.json` 并创建一个新 `launch.json` 文件。  
    
    ```json
        "name": "Hello debug world",
        "type": "pwa-msedge",
        "port": 9222, // The port value is optional, and the default value is 9222.
        "request": "launch",
        "runtimeExecutable": "C:/path/to/your/webview2/app.exe",
        "env": {
            // Customize for your app location if needed
            "Path": "%path%;e:/path/to/your/app/location; "
        },
        "useWebView": true,
        // The following two lines setup source path mapping, where `url` is the start page of your app, and `webRoot` is the top level directory with all your code files.
        "url": "file:///${workspaceFolder}/path/to/your/toplevel/foo.html",
        "webRoot": "${workspaceFolder}/path/to/your/assets"
    ```  
    
    > [!NOTE]
    > Visual Studio代码源路径映射现在需要 URL，因此你的应用现在在启动时会收到命令行参数。  如果需要，可以 `url` 安全地忽略参数。  
    
1.  若要在源代码中设置断点，请将鼠标悬停在行上，然后选择 `F9`
    
    :::image type="complex" source="./media/breakpoint-vs.png" alt-text="断点在代码Visual Studio设置" lightbox="./media/breakpoint-vs.png":::
       断点在代码Visual Studio设置  
    :::image-end:::
    
1.  运行代码。  
    1.  在" **运行** "选项卡上，从下拉菜单中选择启动配置。  
    1.  若要开始调试你的应用，请选择"开始调试"，这是启动配置下拉列表旁边的绿色三角形。  
        
        :::image type="complex" source="./media/run-vs.png" alt-text="Visual Studio代码运行选项卡" lightbox="./media/run-vs.png":::
           Visual Studio代码运行"选项卡  
        :::image-end:::  
        
1.  打开 **调试控制台** 以查看调试输出和错误。  
    
    :::image type="complex" source="./media/results-vs.png" alt-text=" Visual Studio代码调试控制台" lightbox="./media/results-vs.png":::
       Visual Studio代码调试控制台  
    :::image-end:::  
    
**高级设置**：  

*   目标 Web 视图调试。 
    
    在某些 WebView2 应用中，可以使用多个 WebView2 控件。 若要选取 WebView2 控件以在这种情况下进行调试，可以使用目标 Webview2 调试 
    
    打开 `launch.json` 并完成以下操作以使用目标 Webview 调试。  
    
    1.  确认参数 `useWebview` 设置为 `true` 。  
    1.  添加 `urlFilter` 参数。  当 WebView2 控件导航到 URL 时，参数值用于比较 URL `urlFilter` 中出现的字符串。  
        
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    调试应用时，可能需要从呈现过程开始逐步执行代码。 如果您在网站上呈现网页，但无法访问源代码，可以使用 选项，因为网页将忽略无法 `?=value`  识别的参数。   
    
    > [!IMPORTANT]
    > 在 URL 中发现第一个匹配项后，调试程序将停止。  无法同时调试两个 WebView2 控件，因为 CDP 端口由所有 WebView2 控件共享，并且使用单个端口号。  
    
*   调试正在运行的进程  
    
    你可能需要将调试器附加到运行 WebView2 进程。 为此，在 `launch.json` 中，将 `request` 参数更新为 `attach` 。
    
    ```json
        "name": "Hello debugging world",
        "type": "pwa-msedge",
        "port": 9222, 
        "request": "attach",
        "runtimeExecutable": "C:/path/to/your/webview2/app.exe",  
        "env": {
            "Path": "%path%;e:/path/to/your/build/location; "  
        },
        "useWebView": true
    ```  
    
    WebView2 控件必须打开 CDP 端口以允许调试 WebView2 控件。  必须生成代码，以确保在启动调试程序之前，只有一个 WebView2 控件在 CDP (打开 Chrome 开发人员) 协议。  
    
*   调试跟踪选项  
    
    将 参数 `trace` 添加到 launch.js启用调试跟踪。  
    
    1.  添加 `trace` 参数。  
        
        :::row:::
           :::column span="":::
              ```json
                "name": "Hello debugging world",
                "type": "pwa-msedge",
                "port": 9222, 
                "request": "attach",
                "runtimeExecutable": "C:/path/to/your/webview2/app.exe",  
                "env": {
                "Path": "%path%;e:/path/to/your/build/location; "  
                },
                "useWebView": true
                ,"trace": true  // Turn on  debug tracing, and save the output to a log file.
              ```  
              
              :::image type="complex" source="./media/trace-log.png" alt-text=" 将调试输出保存到日志文件。" lightbox="./media/trace-log.png":::
                 将调试输出保存到日志文件  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 详细输出" lightbox="./media/verbose.png":::
                 Visual Studio启用详细跟踪功能的代码调试输出  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   调试 Office 加载项。  
    
    如果要调试 Office 加载项，请打开代码的单独实例中的Visual Studio代码。  在 launch.js2 应用中打开"打开"菜单，并添加以下代码段以将调试器附加到 Office 加载项。
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   调试器疑难解答  
    
    使用调试器时可能会遇到以下情形。  
    
    *   调试程序不会在断点停止，并且你有调试输出。  若要解决此问题，请确认断点为的文件与 WebView2 控件所使用的文件相同。  调试程序不执行源路径映射。  
    *   无法附加到正在运行的进程，并且收到超时错误。  若要解决此问题，请确认 WebView2 控件打开了 CDP 端口。  请确保  `additionalBrowserArguments`  注册表中的值正确，或者选项正确。  有关详细信息，请导航到[dotnet 的 additionalBrowserArguments][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]和[Win32 的 additionalBrowserArguments。][Webview2ReferenceWin32Webview2IdlParameters]  
        
* * *  

## <a name="see-also"></a>另请参阅  

*   若要开始使用 WebView2，请导航到["WebView2 入门指南"。][Webview2MainGetStarted]  
*   有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。
*   有关 WebView2 API 的更多详细信息，请导航到 [API 参考][Webview2ApiReference]。
*   有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2MainNextSteps]
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 Microsoft Edge WebView 团队联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions.AdditionalBrowserArguments 属性 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment - 全局|Microsoft Docs"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考|Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  
[Webview2MainGetStarted]: ../index.md#get-started "入门 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
