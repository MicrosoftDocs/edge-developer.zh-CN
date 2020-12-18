---
description: Microsoft Edge DevTools 协议版本 0.1 发行说明
title: DevTools 协议版本 0.1 发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 60e92cb3afa9b10b15c8ebdd520c0061fbb3b366
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232467"
---
# DevTools 协议版本 0.1 发行说明

> [!NOTE]
> Microsoft Edge DevTools 协议仅适用于 [Windows 10 2018 年 4](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 月更新和 [更高版本的 Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。

Microsoft **Edge DevTools 协议** 版本 0.1 提供早期预览版，用于测试新的独立 [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用中的边缘HTML 检测和基本远程调试。 因此，需要你运行 [Windows 10 2018 年 4](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 月更新或更高版本 [的 Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。

DevTools 协议背后的目标有三重：

 - 为要附加到 Microsoft Edge 的 DevTools 应用提供公共 API
 - 扩展对外部工具客户端的 DevTools 功能的访问
 - 在运行 Microsoft Edge 的 Windows 10 设备范围内启用远程调试 

此初步版本提供了核心调试功能，例如设置断点、逐步执行代码和探索堆栈跟踪。 在 Edge DevTools UI 中，这转换为调试器面板[****](../../devtools-guide/debugger.md)中提供的功能，减去 Web 存储、服务工作器、缓存 API 和 IndexedDB (的缓存检查) 。 

将在即将发布的版本中添加进一步调试器功能，后跟为其他 [DevTools](../index.md) 面板提供电源的检测。
