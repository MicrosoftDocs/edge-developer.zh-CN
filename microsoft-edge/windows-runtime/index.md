---
description: 使用 Windows 运行时 (WinRT) 从 JavaScript 应用调用本机 Windows Api。
title: '适用于 JavaScript 的 Windows 运行时 (WinRT) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/29/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: Windows 运行时、WinRT、PWA、JavaScript
ms.openlocfilehash: e4b6eab4ecfbd26ccda8ef1c6e51a7a30dfaecfc
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942205"
---
# 适用于 JavaScript 的 Windows 运行时 (WinRT)   

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

[Windows 运行时](/windows/uwp/get-started/universal-application-platform-guide#how-the-universal-windows-platform-relates-to-windows-runtime-apis)\ (或 WinRT \ ) 是为在所有[Windows 10 设备系列](/uwp/extension-sdks/device-families-overview)上运行的[通用 Windows 平台](/windows/uwp/get-started/universal-application-platform-guide)\ (UWP \ ) 应用的本机 api 的集合。  WinRT Api 被投影到多种不同语言，包括 c #、c + +、Visual Basic 和 JavaScript。  

作为 web 开发人员，当你的 web 应用 [作为已安装的 Windows 10 应用程序运行](../progressive-web-apps-edgehtml/windows-features.md#set-up-and-run-your-universal-windows-app) 时，你可能会从 JavaScript 请求这些本机 Windows api， (从该 `wwahost.exe` 进程（而不是浏览器 \ ) ）启动。  此外，作为 Windows 10 应用运行的网站还可以使用 [Microsoft Edge](#webview) web 部件控件来显示远程和本地 web 内容以及用于 blob 和流处理的 [MSApp](#msapp) api 以及其他内容。  

以下是所有 Windows 10 应用均可使用的顶级 WinRT 命名空间区域：  

| WinRT 命名空间 | 描述 |  
|:--- |:--- |  
| [AI](/uwp/api/windows.AI.MachineLearning.Preview) \ (Preview \ )  | 包含支持应用加载计算机学习模型、将数据作为输入绑定并评估结果的类。  |  
| [Windows.applicationmodel.calls](/uwp/api/windows.applicationmodel) | 为应用提供对核心系统功能的访问以及有关应用包的运行时信息，并处理挂起操作。  |  
| [数据](/uwp/api/windows.data.html) | 提供用于处理各种数据格式（包括 HTML、JSON、PDF、文本和 XML）的实用工具类。  |  
| [设备](/uwp/api/windows.devices) | 此命名空间提供对低级别设备提供程序（包括 ADC、GPIO、I2 C、PWM 和 SPI）的访问权限。  |  
| [Foundation](/uwp/api/windows.foundation) | 启用基本 Windows 运行时功能，包括管理异步操作和访问属性存储。  此命名空间还定义了表示统一资源标识符 \ (URI \ ) 、日期和时间、二维度量值和其他基本值的常见值类型。  |  
| [游戏](/uwp/api/windows.gaming.input) |提供对游戏控制器输入、游戏栏、游戏监视和游戏聊天的访问权限。  |  
| [全球化](/uwp/api/windows.globalization) | 提供语言配置文件、地理区域和国际日历的全球化支持。  |  
| [显卡](/uwp/api/windows.graphics) | 提供包含有关如何绘制图形的信息的基本数据类型。  这些数据结构通常用于定义在使用 CompositionVirtualDrawingSurface 类时如何绘制大的图面。  |  
| [管理](/uwp/api/windows.management) | 提供强制从移动设备管理 \ (MDM \ ) 设备到服务器的同步的功能。  此 MDM 同步协议基于开放的移动联盟-设备管理标准。  |  
| [媒体](/uwp/api/windows.media) | 提供用于创建和使用媒体（如照片、音频录制和视频）的类。  |  
| [网络](/uwp/api/windows.networking) | 提供对网络应用使用的主机名和终结点的访问权限。  |  
| [引起](/uwp/api/windows.perception) | 包含用于 perceiving 用户周围环境的类，使应用能够找到与用户周围的图面和全息图相关的设备和原因。  |  
| [安全性](/uwp/api/windows.security.authentication.identity) | 提供用于用户身份验证、凭据管理、加密操作和企业数据保护功能的类。  |  
| [服务](/uwp/api/windows.services.cortana) | 提供对 Cortana、地图、Microsoft Store 和目标 \ (订阅 \ ) 内容的 Microsoft 服务的访问权限。  |  
| [存储](/uwp/api/windows.storage) | 提供用于管理文件、文件夹和应用程序设置的类。  |  
| [系统](/uwp/api/windows.system) | 支持启动应用、获取有关用户的信息和内存分析等系统功能。  |  
| [UI](/uwp/api/windows.ui) | 为应用提供对核心系统功能和有关 UI 的运行时信息的访问。  **注意**：命名空间中的 api 不可 `Windows.UI.Xaml` 用于 JavaScript 应用 \ (，这些应用可能会使用基于 web 标准的等效技术 \ ) 。  |  
| [Web](/uwp/api/windows.web) | 提供有关 web 服务操作导致的错误的信息。  |  

有关用法的更多详细信息，请 [在 JavaScript 中使用 Windows 运行时](./using-the-windows-runtime-in-javascript.md)查看。  若要了解如何将网站作为 Windows 应用运行，请尝试 [定制你的 PWA For windows](../progressive-web-apps/windows-features.md) 教程。  

## WebView  

通过 [Microsoft Edge Web 视图](../webview.md) 控件，你可以在 Windows 10 应用中托管 web 内容。  这类似于使用 `<iframe>` ，但提供了 [更多功能和控制](../hosting/webview.md#webview-versus-iframe) 体验。  

## MSApp  

[MSApp](./reference/msapp.md) global object (\ `window.MSApp` ) 为基于 JavaScript 的 Windows 10 应用提供各种帮助程序函数，例如用于在基于 web 标准和等效 WinRT 对象类型之间进行转换的实用工具。  
