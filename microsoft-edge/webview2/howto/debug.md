---
description: 了解如何调试 WebView2 控件。
title: 调试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/10/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 6b2cc65e5cb368c29efec2eb3638f0c1772000d9
ms.sourcegitcommit: 4bc904c5d54347185f275bd76441975be471c320
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926475"
---
# 如何通过 WebView2 进行调试  

Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和开发人员工具的优势。  下页概述了使用 WebView2 控件进行开发时要使用的不同工具。  

## Microsoft Edge 开发工具  

使用[Microsoft edge (Chromium) 开发人员工具][DevtoolsGuideChromiumMain]来调试在 WebView2 控件中显示的 web 内容，方法与使用 Microsoft Edge 相同。  若要打开 DevTools，请将焦点置于 "Web 视图" 窗口，然后使用以下任一操作。  
*   选择 `F12` 。  
*   选择 `Ctrl` + `Shift` + `I` 。  
*   打开上下文菜单 \ (右键单击 \ ) > 选择 `Inspect` 。  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge 开发工具" lightbox="../media/f12.png":::
   Microsoft Edge 开发工具  
:::image-end:::  

> [!NOTE]
> 当在 Visual Studio 中调试应用程序时，如果附加了本机调试器，则按下 `F12` 可能会触发本机调试器，而不是开发人员工具。  按下 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ (右键单击 \ ) 以避免这种情况。  

> [!NOTE]
> `--auto-open-devtools-for-tabs`首次创建 Web 视图时，可以使用命令行参数打开新的 DevTools 窗口。  <!--See `CreateCoreWebView2Controller` documentation for how to provide additional command-line arguments to the browser process.  See `LoaderOverride` registry key to examine different builds of WebView2 without modifying your application in the `CreateCoreWebView2Controller` documentation.  -->  

## Visual Studio  

使用 Visual Studio 2019 版本16.4 预览版2或更高版本中的脚本调试程序在 Visual Studio 中调试你的脚本。  验证安装了**c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 诊断":::
   Visual Studio JavaScript 诊断  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

若要启用 WebView2 脚本调试，请打开上下文菜单 \ (右键单击项目上的 \ ) > 选择 "**属性**"。  

*   在**配置属性**上，选择 "**调试**"。  
*   在 "**调试器类型**" 属性中，从选项列表中选择 " **JavaScript (WebView2") ** 。 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript 调试器":::
   Visual Studio JavaScript 调试器  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

你已准备好进行调试。  

若要进行调试，请完成以下操作。  

1.  设置断点  
    *   打开脚本文件，并将断点设置为所需位置。  
        
        > [!NOTE]
        > JS/TS 调试适配器不执行源路径映射。您必须打开与您的 WebView2 相关联的完全相同的路径。  
        
1.  运行代码  
    *   选择适当的构建风格和运行时环境，然后启动本地 windows 调试器。  
1.  查看调试控制台  
    *   在创建第一个 webview2 后，你的应用程序运行和调试程序将连接。将显示任何挂起的调试输出。  
        
        > [!NOTE]
        > 此调试方法当前仅限于 Win32 应用程序和 Office 外接程序。  
        
## Visual Studio Code  

你可以使用 Visual Studio 代码调试在 WebView2 控件中运行的脚本。  有关详细信息，请参阅[Microsoft Edge (Chromium) Web 视图应用程序][GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]。  

<!--todo:  add See also heading  -->  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!--## Debugging  

Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`. You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView. See CreateCoreWebView2Controller documentation for how to provide additional command line arguments to the browser process. Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateCoreWebView2Controller documentation.  -->  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发人员工具"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) Web 视图应用程序-VS 代码-Microsoft Edge 的调试器-microsoft/vscode-debug2 |GitHub"  
