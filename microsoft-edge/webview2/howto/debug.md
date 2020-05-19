---
description: 了解如何调试 WebView2 控件。
title: 调试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 386bc237257be0ade8c48bc1c737b0151a882719
ms.sourcegitcommit: 5bdffe91a6594f77eeffa4e864fda90a02784771
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "10659684"
---
# 如何在与 WebView2 控件一起开发时进行调试  

Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和开发人员工具的优势。  本文概述了使用 WebView2 控件进行开发时要使用的不同工具。  

## Microsoft Edge 开发工具  

使用[Microsoft edge （Chromium）开发人员工具](/microsoft-edge/devtools-guide-chromium)来调试在 WebView2 控件中显示的 web 内容，方法与你使用 Microsoft Edge 的方式相同。  若要打开 DevTools，请将焦点置于 "Web 视图" 窗口，然后使用以下任一选项。  
*   选择 `F12` 。  
*   选择 `Ctrl` + `Shift` + `I` 。  
*   打开上下文菜单 \ （右键单击 \） > 选择 `Inspect` 。  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge 开发工具":::
   Microsoft Edge 开发工具  
:::image-end:::  

> [!NOTE]
> 在附加了本机调试器的 Visual Studio 中调试应用程序时，选择 " `F12` 可能会触发本机调试器，而不是开发工具"。  使用 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ （右键单击 \）以避免这种情况。  

## Visual Studio  

使用 Visual Studio 2019 版本16.4 预览版2或更高版本中的脚本调试程序在 Visual Studio 中调试你的脚本。  验证安装了**c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 诊断":::
   Visual Studio JavaScript 诊断  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

若要启用 WebView2 脚本调试，请打开项目上的上下文菜单 \ （右键单击 \） > 选择 "**属性**"。  在**配置属性**上，选择 "**调试**"。  在 "**调试器类型**" 属性中，从选项列表中选择 " **JavaScript （WebView2）** "。 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript 调试器":::
   Visual Studio JavaScript 调试器  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

## Visual Studio Code  

你可以使用 Visual Studio 代码调试在 WebView2 控件中运行的脚本。  有关详细信息，请参阅[Microsoft Edge （Chromium） Web 视图应用程序](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications)。  

<!--todo:  add See also heading  -->  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

通过分享你的反馈来帮助构建更丰富的 WebView2 体验。  访问[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告。  
