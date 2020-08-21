---
description: 使用 Windows 运行时 (WinRT) 给 JavaScript 应用调用本机 Windows API。
title: '适用于 JavaScript 的 Windows (WinRT) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/29/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: Windows 运行时，WinRT、PWA、JavaScript
ms.openlocfilehash: e4b6eab4ecfbd26ccda8ef1c6e51a7a30dfaecfc
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942205"
---
# 适用于 JavaScript 的 Windows (WinRT)   

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

[Windows 运行时](/windows/uwp/get-started/universal-application-platform-guide#how-the-universal-windows-platform-relates-to-windows-runtime-apis)\ (或仅限 WinRT\) 是为运行所有 Windows 10 设备系列的通用[Windows 平](/windows/uwp/get-started/universal-application-platform-guide)台 \ (UWP\) 应用提供的本机 API[集合](/uwp/extension-sdks/device-families-overview)。  WinRT API 将使用多种不同的语言投影，包括 C#、C++、Visual Basic和 JavaScript。  

作为 Web 开发人员，当你的 Web 应用以已安装 [的 Windows 10](../progressive-web-apps-edgehtml/windows-features.md#set-up-and-run-your-universal-windows-app) 应用 \ (启动时（而不是浏览器\) ）运行时，你可以通过 JavaScript 请求这些本机 Windows `wwahost.exe` API。  此外，作为 Windows 10 应用运行的网站还可以使用 [Microsoft Edge WebView](#webview) 控件，在其他事项中显示远程和本地 [Web 内容和本地 Web](#msapp) 内容和 MSApp API。  

以下是可供所有 Windows 10 应用使用的顶级 WinRT 命名空间：  

| WinRT Namespace | 描述 |  
|:--- |:--- |  
| [AI](/uwp/api/windows.AI.MachineLearning.Preview) \ (Preview\)  | 包含使应用能够加载机器学习模型、将数据绑定为输入、计算结果的类。  |  
| [ApplicationModel](/uwp/api/windows.applicationmodel) | 提供应用来访问有关应用包的关键系统功能和运行时信息，并处理挂起操作。  |  
| [数据](/uwp/api/windows.data.html) | 提供使用各种数据格式（包括 HTML、JSON、PDF、PDF 和 XML）的实用工具类。  |  
| [设备](/uwp/api/windows.devices) | 此命名空间提供对低级别设备提供程序的访问权限，包括 ADC、GPIO、I2 C、PWM 和 SPI。  |  
| [Foundation](/uwp/api/windows.foundation) | 启用基本 Windows 运行时功能，包括管理异步操作和访问属性存储。  此命名空间还定义表示统一资源标识符 \ (URI\) 、日期和时间、2D 度量值以及其他基本值的常见值类型。  |  
| [游戏](/uwp/api/windows.gaming.input) |提供对游戏控制器输入、游戏栏、游戏监视和游戏聊天的访问权限。  |  
| [全球化](/uwp/api/windows.globalization) | 提供对语言配置文件、地理区域和国际日历的全球化支持。  |  
| [显卡](/uwp/api/windows.graphics) | 提供包含有关如何绘制图形的信息的基本数据类型。  这些数据结构通常用于定义在使用 CompositionVirtualDrawingSurface 类时绘制的大图面。  |  
| [管理](/uwp/api/windows.management) | 提供强制从移动设备管理 \ (MDM\) 到服务器的同步的功能。  此 MDM 同步协议基于开放的移动设备管理标准。  |  
| [媒体](/uwp/api/windows.media) | 提供类，用于创建和使用媒体，如照片、录音和视频。  |  
| [网络](/uwp/api/windows.networking) | 提供对网络应用所使用的主机名和终结点的访问。  |  
| [感受](/uwp/api/windows.perception) | 包含使用适合用户环境的类，允许应用定位到相对于用户的表面和全息影像的设备。  |  
| [安全性](/uwp/api/windows.security.authentication.identity) | 为用户身份验证、凭据管理、加密操作和企业数据保护功能提供类。  |  
| [服务](/uwp/api/windows.services.cortana) | 提供对适用于 Cortana、地图、Microsoft Store 和定向 \ (\) 内容的 Microsoft 服务的访问。  |  
| [存储](/uwp/api/windows.storage) | 提供类来管理文件、文件夹和应用程序设置。  |  
| [系统](/uwp/api/windows.system) | 启用系统功能，如启动应用、获取有关用户的信息和内存分析。  |  
| [UI](/uwp/api/windows.ui) | 提供应用来访问有关 UI 的关键系统功能和运行时信息。  **注意**：命名空间 `Windows.UI.Xaml` 中的 API 不可用于 JavaScript 应用 \ (，后者可能使用等效的基于 Web 标准的技术\) 。  |  
| [Web](/uwp/api/windows.web) | 提供有关来自 Web 服务操作导致的错误的信息。  |  

有关使用情况的详细信息，请查明使用 [JavaScript 中的 Windows 运行时](./using-the-windows-runtime-in-javascript.md)。  要了解如何以 Windows 应用身定制网站，请试 [用 PWA 教](../progressive-web-apps/windows-features.md) 程。  

## WebView  

Microsoft [Edge WebView](../webview.md) 控件可用于在 Windows 10 应用中托管 Web 内容。  这类似于使用体验， `<iframe>` 但提供了更多功能 [和对体验的](../hosting/webview.md#webview-versus-iframe) 控制。  

## MSApp  

[MSApp](./reference/msapp.md)全局对象 \ (`window.MSApp` \) 提供适用于基于 JavaScript 的 Windows 10 应用的分类帮助程序函数，例如在基于 Web 标准的和等效 WinRT 对象类型之间进行转换的实用工具。  
