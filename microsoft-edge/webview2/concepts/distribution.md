---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用程序的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 7db610ff1133b1b5b380372422f1f2f10981e583
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052184"
---
# 使用 WebView2 的应用程序的分发  

分发 WebView2 应用程序时，请确保支持 web 平台-应用启动前存在 [WebView2 运行时](#understanding-the-webview2-runtime) 。  本文介绍开发人员如何安装 WebView2 运行时，并使用 WebView2 应用程序的两种分布模式：长  [绿](#evergreen-distribution-mode) 和 [固定版本](#fixed-version-distribution-mode)。  

## 长绿分布模式  

> [!NOTE]
> 对于大多数开发人员，建议使用长绿分布模式。  

长时间分布模式可确保你的应用充分利用最新功能和安全更新。  它具有下列特征。  

*   基础 web 平台 \ (WebView2 运行时 \ ) 自动更新，而不需要开发人员进行额外的工作。  
*   所有使用长时间分布模式的应用程序都使用长绿 WebView2 运行时的共享副本，该副本节省磁盘空间。  

### 了解 WebView2 运行时  

WebView2 运行时是重新分发的运行时，它充当 WebView2 应用程序的支持 web 平台。  此概念类似于 c + +/.NET 应用的 VC + + 或 .NET 运行时。  在该环境下，将修改运行时 Microsoft Edge \ (Chromium \ ) 二进制文件，这些二进制文件经过微调并针对应用程序进行了测试。  在安装时，运行时不会显示为用户可见的浏览器，例如，用户没有浏览器桌面快捷方式或 "开始" 菜单项。  

对于开发和测试，开发人员可以将运行时或任何非稳定的 Microsoft Edge \ (Chromium \ ) 浏览器频道用于支持的 web 平台。  在生产环境中，开发人员必须确保在应用程序启动之前用户设备上存在运行时。  Microsoft Edge 稳定通道不可用于 WebView2 用法，防止应用在生产环境中依赖浏览器参与。  

开发人员不能在浏览器上取得依赖性，原因如下：  

*   Microsoft Edge \ (Chromium \ ) 不保证在所有用户设备上都存在。  例如，从 Windows Update 断开的设备或不是由 Microsoft 直接管理的设备，而不是由 Microsoft (直接在教育机构的大型企业/市场部 ) 中  允许开发人员分发 WebView2 运行时，可避免将浏览器作为应用的必备项。
*   浏览器和应用具有不同的用例，因此对浏览器的依赖可能会对你的应用产生意外的副作用。  例如，IT 管理员可以针对内部网站兼容性版本控制浏览器。  WebView2 运行时允许应用在浏览器更新处于活动的管理期间保持长绿。  
*   与浏览器相反，运行时是为应用程序方案开发和测试的，在某些情况下，可能会包含在浏览器中尚不可用的 bug 修复。  

长时间 WebView2 运行时计划在 Windows 将来的版本中传送收件箱。  在运行库更广泛地可用之前，建议开发人员将运行时与其生产应用程序一起部署。  

### 部署长绿 WebView2 运行时  

设备上的所有长时间应用仅需要一个安装长绿 WebView2 运行时。  [WebView2 运行时下载页面][Webview2Installer]上提供了许多工具，可帮助开发人员部署长时间运行时，例如：  

*   WebView2 运行时引导程序 \ (即将发布 \ ) 是一个小的 \ (约 2 MB \ ) 安装程序。  此安装程序从与用户的设备体系结构匹配的 Microsoft 服务器下载并安装长时间运行时。  
*   链接以下载引导程序 \ (即将发布 \n ) 是供开发人员以编程方式下载引导程序的链接。
*   WebView2 运行时独立安装程序是可在脱机环境中安装长时间 WebView2 运行时的完整安装程序。  

当前，引导程序和独立安装程序仅支持每台计算机安装，这需要提升。  如果没有提升，则会显示一个 Windows 用户帐户控制提示，要求用户提升权限。  

我们建议采用以下工作流，以确保在启动应用程序之前已安装运行时。  你可以根据你的方案调整工作流。  我们还将在将来提供示例代码。  

#### 仅联机部署  

如果您有仅限联机的部署方案，而最终用户认为有 internet 访问权限，请执行以下步骤：  

*   在应用程序设置过程中，请检查运行时是否已由下列两种情况之一安装：  
    *   检查中是否 `pv (REG_SZ)` 存在 regkey `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}` ，或者  
    *   调用 WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) 并检查 versionInfo 是否为 NULL。  
*   如果未安装运行时，请使用链接以编程方式下载引导程序。  
*   使用 "静默安装" 从提升的进程或命令提示符处调用引导 `MicrosoftEdgeWebview2Setup.exe /silent /install` 程序。  

此工作流可确保仅在需要时安装运行时，不需要打包安装程序或检测用户设备的体系结构，并且可以无提示地安装运行时。  你还可以选择将引导程序与你的应用程序打包，而不是按需以编程方式下载它。  

#### 脱机部署  

如果你有一个脱机部署方案，其中应用部署必须完全脱机工作，请执行以下步骤：  

*   下载 [独立安装程序][Webview2Installer]。  
*   在应用程序安装程序或更新程序中包括安装程序。  
*   在应用程序设置过程中，请检查运行时是否已由下列两种情况之一安装：  
    *   检查中是否 `pv (REG_SZ)` 存在 regkey `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}` ，或者  
    *   调用 WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) 并检查 versionInfo 是否为 NULL。  
*   如果运行时未安装，请从提升的进程或命令提示符处调用独立安装程序，以 `MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install` 进行静默式安装。  

## 固定版本分发模式  

> [!NOTE]
> 固定版本分发模式尚不可用。  

对于受限制的环境，有计划支持固定版本，以前称为 "携带"、"分发" 模式。  固定版本分发模式允许开发人员选择和打包特定版本的 WebView2 运行时。  固定版本分发模式允许你控制你的应用程序使用哪个版本的 WebView2 运行时，以及何时更新用户计算机。  固定版本分发模式不会接收任何自动更新，开发人员应计划自己应用更新。  


<!-- links -->  

[ConceptsVersioning]: ./versioning.md "了解浏览器版本和 WebView2 |Microsoft 文档"  
[ReferenceWin3209622WebviewIdl]: ../reference/win32/0-9-622/webview2-idl.md  "Globals |Microsoft 文档"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序"  
