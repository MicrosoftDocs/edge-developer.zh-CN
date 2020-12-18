---
description: 使用 Windows 运行时 (WinRT) 从 JavaScript 应用调用本机 Windows API。
title: 适用于 JavaScript (WinRT) Windows 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: Windows 运行时、WinRT、PWA、JavaScript
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3bd67f052d0a836c754f7b58d0625e09ae8781cd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232745"
---
# 适用于 JavaScript (WinRT) Windows 运行时  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

[Windows 运行时](/windows/uwp/get-started/universal-application-platform-guide#how-the-universal-windows-platform-relates-to-windows-runtime-apis)\ (或简单的 WinRT\) 是支持跨所有[Windows 10](/uwp/extension-sdks/device-families-overview)设备系列运行的通用[Windows 平台](/windows/uwp/get-started/universal-application-platform-guide)\ (UWP\) 应用的本机 API 的集合。  WinRT API 被计划为许多不同的语言，包括 C#、C++、Visual Basic和 JavaScript。  

作为 Web 开发人员，当 Web 应用作为从进程启动的已安装 [Windows 10](../progressive-web-apps/windows-features.md#set-up-and-run-your-universal-windows-app) 应用 \ (而不是浏览器\) 运行时，你可以从 JavaScript 请求这些本机 Windows `wwahost.exe` API。  此外，作为 Windows 10 应用运行的网站可能还使用 [Microsoft Edge Webview](#webview) 控件显示远程和本地 Web 内容以及 [MSApp](#msapp) API，用于 blob 和流处理等。  

下面是可用于所有 Windows 10 应用的顶级 WinRT 命名空间区域：  

| WinRT 命名空间 | 描述 |  
|:--- |:--- |  
| [AI](/uwp/api/windows.AI.MachineLearning.Preview) \ (Preview\)  | 包含使应用能够加载机器学习模型、将数据绑定为输入并评估结果的类。  |  
| [ApplicationModel](/uwp/api/windows.applicationmodel) | 为应用提供对核心系统功能和有关应用包的运行时信息的访问权限，并处理暂停操作。  |  
| [数据](/uwp/api/windows.data.html) | 提供实用程序类，用于处理各种数据格式，包括 HTML、JSON、PDF、文本和 XML。  |  
| [设备](/uwp/api/windows.devices) | 此命名空间提供对低级别设备提供程序的访问，包括 ADC、GPIO、I2 C、PWM 和 SPI。  |  
| [Foundation](/uwp/api/windows.foundation) | 启用基本的 Windows 运行时功能，包括管理异步操作和访问属性存储。  此命名空间还定义表示统一资源标识符 \ (URI\) 、日期和时间、二维度量和其他基本值的常见值类型。  |  
| [游戏](/uwp/api/windows.gaming.input) |提供对游戏控制器输入、游戏栏、游戏监视和游戏聊天的访问权限。  |  
| [全球化](/uwp/api/windows.globalization) | 为语言配置文件、地理区域和国际日历提供全球化支持。  |  
| [显卡](/uwp/api/windows.graphics) | 提供包含有关绘制图形的信息的基本数据类型。  这些数据结构通常用于定义在使用 CompositionVirtualDrawingSurface 类时绘制的图面大小。  |  
| [管理](/uwp/api/windows.management) | 提供强制从移动设备管理 \ (MDM\) 设备同步到服务器的功能。  此 MDM 同步协议基于开放移动联盟 - 设备管理标准。  |  
| [Media](/uwp/api/windows.media) | 提供用于创建和用于媒体（如照片、音频录制和视频）的类。  |  
| [网络](/uwp/api/windows.networking) | 提供对网络应用使用的主机名和终结点的访问。  |  
| [感知](/uwp/api/windows.perception) | 包含用于感知用户周围环境的类，使应用可以相对于用户周围的表面和全息影像查找设备的位置和原因。  |  
| [安全性](/uwp/api/windows.security.authentication.identity) | 提供用于用户身份验证、凭据管理、加密操作和企业数据保护功能的类。  |  
| [服务](/uwp/api/windows.services.cortana) | 提供对 Cortana、地图、Microsoft Store 和目标 \ (订阅\) 的访问权限。  |  
| [存储](/uwp/api/windows.storage) | 提供用于管理文件、文件夹和应用程序设置的类。  |  
| [系统](/uwp/api/windows.system) | 启用系统功能，例如启动应用、获取有关用户的信息以及内存分析。  |  
| [UI](/uwp/api/windows.ui) | 向应用提供对核心系统功能和 UI 的运行时信息的访问权限。  **注意**：命名空间中的 API 不适用于 JavaScript 应用 \ (它可能会使用等效的基于 Web 标准的 `Windows.UI.Xaml` 技术\) 。  |  
| [Web](/uwp/api/windows.web) | 提供有关 Web 服务操作导致的错误的信息。  |  

有关使用情况的更多详细信息，请查看使用 [JavaScript 中的 Windows 运行时](./using-the-windows-runtime-in-javascript.md)。  若要了解如何将网站作为 Windows 应用运行，请尝试"定制 [适用于 Windows 的 PWA"](../progressive-web-apps/windows-features.md) 教程。  

## WebView  

[Microsoft Edge WebView](../hosting/webview/index.md)控件使你能够在 Windows 10 应用中托管 Web 内容。  这类似于使用 `<iframe>` ，但提供了更多的功能 [和控制](../hosting/webview/index.md#webview-versus-iframe) 体验。  

## MSApp  

[MSApp](./reference/msapp.md)全局对象 \ (\) 为基于 JavaScript 的 Windows 10 应用提供排序的帮助程序函数，例如用于基于 Web 标准的和等效的 WinRT 对象类型之间转换的 `window.MSApp` 实用程序。  
