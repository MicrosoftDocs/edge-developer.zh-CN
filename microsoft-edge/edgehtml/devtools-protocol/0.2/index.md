---
description: Microsoft Edge DevTools 协议版本 0.2 的发行说明
title: Microsoft Edge DevTools 协议版本 0.2 发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 61d8f5b00dca3505594ca41db6c80c5ba4157092
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232072"
---
# DevTools 协议版本 0.2 发行说明

> [!NOTE]
> Microsoft Edge DevTools 协议的版本 0.2 仅适用于 [Windows 10 2018 年 10 月](/windows/uwp/whats-new/windows-10-build-17763) 更新和更高版本的 Windows Insider [Preview](https://insider.windows.com/getting-started/) 版本。

Microsoft **Edge DevTools 协议** 的版本 0.2 提供了一个预览，用于测试新的独立 Microsoft Edge [DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用中的边缘HTML 检测和基本远程调试。 因此，需要你运行 [Windows 10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763) 月更新或更高版本 [的 Windows Insider Preview](https://insider.windows.com/getting-started/) 版本。

DevTools 协议背后的目标有三重：

 - 为要附加到 Microsoft Edge 的 DevTools 应用提供公共 API
 - 扩展对外部工具客户端的 DevTools 功能的访问
 - 在运行 Microsoft Edge 的 Windows 10 设备范围内启用远程调试 

除版本 0.1 中引入的核心脚本调试功能外，DevTools 协议版本 0.2 还包括样式和布局的新域 (只读) 调试和控制台 API。 在 Edge DevTools UI 中，这转换为元素、控制台[****](../../devtools-guide/elements.md)和调试[****](../../devtools-guide/console.md)器面板[**中提供**](../../devtools-guide/debugger.md)的功能。
