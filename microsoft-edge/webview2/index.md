---
description: 将 Win32 应用中的 web 内容托管到 Microsoft Edge Web 部件2控件中
title: Microsoft Edge WebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、Windows Forms、WinForms、WPF、.NET
ms.openlocfilehash: 1b140d9f644c7a864cac4966bb4cfdd400feeb0d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697740"
---
# Microsoft Edge WebView2 简介（预览版）  

Microsoft Edge WebView2 控件使你能够在本机应用程序中嵌入 web 技术 \ （HTML、CSS 和 JavaScript \）。  WebView2 控件使用[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com)作为呈现引擎，以在本机应用程序中显示 web 内容。  使用 WebView2，你可以将 web 代码嵌入本机应用程序的不同部分，或在单个 Web 视图中构建整个本机应用程序。  有关如何开始构建 WebView2 应用程序的信息，请参阅[入门](./index.md#getting-started)。  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="什么是 Web 视图":::
   什么是 Web 视图  
:::image-end:::  

> [!NOTE]
> WebView2 Preview 适用于早期原型和收集反馈，以帮助对 API 进行整形。  Microsoft Edge Web 图团队不建议在生产应用中使用预览，因为可能会[发生重大更改](./releasenotes.md)。  

## 混合应用程序方法  

开发人员通常必须在构建 web 应用程序或本机应用程序之间进行选择。  决策在接触和接通电源之间的平衡。  Web 应用程序允许广泛访问。  作为 Web 开发人员，你可以在所有不同平台上重复使用大多数代码（如果不是所有代码）。  但是，本机应用程序利用整个本机平台的功能。  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native":::
   Web native  
:::image-end:::  

混合应用程序使开发人员能够享受这两个领域的最佳体验。  混合应用程序开发人员受益于 web 平台的 ubiquity 和强项，以及本机平台的强大功能和完整功能。  

## WebView2 优惠   

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="Web 视图原因":::
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
      **固定**\ （即将推出 \）  
      选择将 Chromium 位打包在你的应用程序中。  
   :::column-end:::
   :::column span="1":::
      **增量采纳**  
      将 web 组件逐个添加到应用程序。  
   :::column-end:::
:::row-end:::

## 即刻体验  

若要使用 WebView2 控件生成和测试你的应用程序，你需要安装[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download)和[WebView2 SDK](https://aka.ms/webviewnuget) 。  选择以下选项之一开始使用。  

*   [Win32 C/c + + 入门](./gettingstarted/win32.md)  
*   [WPF 入门](./gettingstarted/wpf.md)  
*   [WinForms 入门](./gettingstarted/winforms.md)  

[WebView2 示例](https://github.com/MicrosoftEdge/WebView2Samples)存储库包含演示所有 WebView2 sdk 功能和 API 使用模式的示例。 随着将更多功能添加到 WebView2 SDK，示例应用程序将更新。   

## 支持的平台  

开发人员预览版在以下编程环境中可用。  

*   Win32 C/c + +  
*   .NET Framework 4.6.2 或更高版本  
*   .NET Core 3.0 或更高版本  
*   [WinUI 3。0](/uwp/toolkits/winui3/)  

你可以在以下版本的 Windows 上运行 WebView2 应用程序。  

*   Windows 10  
*   Windows 8.1  
*   Windows 8  
*   Windows7  
*   Windows Server 2016  
*   WindowsServer 2012  
*   Windows Server 2012R2  
*   Windows Server 2008 R2  

## 后续步骤  

有关如何构建和部署 WebView2 应用程序的更多详细信息，请参阅概念文档和操作方法指南。  

#### 概念  

*   [WebView2 SDK 和 Microsoft Edge 版本控制](./concepts/versioning.md)
*   [分发 WebView2 应用程序](./concepts/distribution.md)  
 
#### 操作方法指南  

*   [通过 DevTools 和 Visual Studio 脚本调试调试 WebView2](./howto/debug.md)  
*   [通过 Microsoft EdgeDriver 自动化和调试 WebView2](./howto/webdriver.md)  

<!--todo: add how-tos when available  -->  

## 与 WebView2 团队取得联系  

通过分享你的反馈来帮助构建更丰富的 WebView2 体验。  访问 "Web 视图[反馈](https://aka.ms/webviewfeedback)" 存储库以提交功能请求或 bug 报告。  它也是搜索已知问题的好地方。  

> [!NOTE]
> 在开发人员预览版期间，Microsoft Edge Web 图团队还会收集数据，以帮助构建更好的 Web 视图。  用户可以通过导航到 `edge://settings/privacy` Microsoft Edge 浏览器并关闭浏览器数据收集来关闭 Web 视图数据收集。  
