---
description: Microsoft Edge DevTools 协议版本0.1 的发行说明
title: DevTools 协议版本0.1 发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 29dc8f1b0ba67cb2b3155cb2135d488609e9bff9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563415"
---
# DevTools 协议版本0.1 发行说明

> [!NOTE]
> Microsoft Edge DevTools 协议仅适用于[windows 10 2018 年4月更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)及更高版本的[Windows 预览体验计划预览](https://insider.windows.com/en-us/getting-started/)版本。

Microsoft **Edge DevTools 协议**版本0.1 提供了在新的独立[Microsoft edge DevTools 预览版](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)应用中测试 EdgeHTML 检测和基本远程调试的早期预览。 因此，它要求你运行的是[windows 10 四月2018更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)或更高版本的[Windows 预览体验计划](https://insider.windows.com/en-us/getting-started/)版本。

DevTools 协议背后的目标为三折：

 - 提供用于将 DevTools 应用附加到 Microsoft Edge 的公共 API
 - 将 DevTools 功能的访问权限扩展到外部工具客户端
 - 在运行 Micrsoft Edge 的 Windows 10 设备范围内启用远程调试 

此预备版本提供核心调试功能，例如设置断点、单步执行代码和浏览堆栈跟踪。 在 Edge DevTools UI 中，这将转换为[**调试器**](../../devtools-guide/debugger.md)面板中可用的功能，减去缓存检查（对于 Web 存储、服务工作人员、缓存 API 和 IndexedDB）。 

将在即将推出的版本中添加更多的调试器功能，后跟用于其他[DevTools](../../devtools-guide.md)面板的检测。
