---
description: 了解如何调试 WebView2 控件。
title: 调试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 232104abc360cfa660d567ffb66535213fcb3ae0
ms.sourcegitcommit: a82aa5fc1ada35cd8274490fbff3c0a850785835
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "10888576"
---
# 如何通过 WebView2 进行调试  

Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和开发人员工具的优势。  下页概述了使用 WebView2 控件进行开发时要使用的不同工具。  

## Microsoft Edge 开发工具  

使用[Microsoft edge （Chromium）开发人员工具][DevtoolsMain]来调试在 WebView2 控件中显示的 web 内容，方法与你使用 Microsoft Edge 的方式相同。  若要打开 DevTools，请将焦点置于 "Web 视图" 窗口，然后使用以下任一操作。  

*   选择 `F12` 。  
*   选择 `Ctrl` + `Shift` + `I` 。  
*   打开上下文菜单 \ （右键单击 \），然后选择 `Inspect` 。  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge 开发工具" lightbox="../media/f12.png":::
   Microsoft Edge 开发工具  
:::image-end:::  

> [!IMPORTANT]
> 在附加了本机调试器的 Visual Studio 中调试应用程序时，选择 " `F12` 可能会触发本机调试器，而不是开发工具"。  使用 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ （右键单击 \）以避免这种情况。  

## Visual Studio  

你可以使用 Visual Studio 同时开发应用程序代码和调试脚本。  

请记住以下事项。  

*   Visual Studio 仅支持在从 Visual Studio 内部启动应用时调试脚本。  \ （不支持附加正在运行的进程进行调试。）  
*   不支持目标 Web 视图调试方案。  

使用 Visual Studio 2019 版本16.4 预览版2或更高版本中的脚本调试程序在 Visual Studio 中调试你的脚本。  

设置调试器。  

*   验证安装了**c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。  
    
    1.  导航到 Windows 中的**应用 & 功能**设置。  使用 Windows 任务条搜索它。  
    1.  选择 "**修改**"。  
    1.  验证是否已选中 " **c + +** " 复选框中的**Javascript 诊断**和桌面开发。  
        
        :::image type="complex" source="../media/appsandfeatures.png" alt-text="应用和功能" lightbox="../media/appsandfeatures.png":::
           应用和功能  
        :::image-end:::  
        
*   启用 WebView2 脚本调试。  
    1.  将鼠标悬停在项目上，打开上下文菜单 \ （右键单击 \），然后选择 "**属性**"。  
    1.  在**配置属性**上，选择 "**调试**"。  
    1.  在 "**调试器类型**" 属性中，搜索选项列表，然后选择 " **JavaScript （WebView2）**"。  
        
        :::image type="complex" source="../media/enbjs.png" alt-text="Visual Studio JavaScript 调试器" lightbox="../media/enbjs.png":::
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

你可以使用 Visual Studio 代码调试在 WebView2 控件中运行的脚本。  有关详细信息，请参阅[Microsoft Edge （Chromium） Web 视图应用程序][GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]。  

<!--todo:  add See also heading  -->  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

通过分享你的反馈来帮助构建更丰富的 WebView2 体验。  访问[反馈][GithubMicrosoftedgeWebviewfeedback]存储库以提交功能请求或 bug 报告。  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发工具 |Microsoft 文档"  

[GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge （Chromium） Web 视图应用程序-VS 代码-Microsoft Edge 调试程序 |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
