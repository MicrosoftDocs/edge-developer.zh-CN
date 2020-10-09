---
description: Microsoft Edge DevTools 协议版本0.2 的发行说明
title: Microsoft Edge DevTools 协议版本0.2 发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: c4959d2905f95c2bcf98cb78ad67bb88ecfec959
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104740"
---
# DevTools 协议版本0.2 发行说明

> [!NOTE]
> Microsoft Edge DevTools 协议的版本0.2 仅适用于 [windows 10 10 月2018更新](/windows/uwp/whats-new/windows-10-build-17763) 及更高版本的 [Windows 预览体验计划预览版](https://insider.windows.com/getting-started/) 。

Microsoft **Edge DevTools 协议** 版本0.2 在新的独立 [Microsoft edge DevTools 预览版](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用中提供了用于测试 EdgeHTML 检测和基本远程调试的预览。 因此，它需要你运行 [2018 年10月更新](/windows/uwp/whats-new/windows-10-build-17763) 或 [Windows 预览体验计划预览版](https://insider.windows.com/getting-started/) 的更高版本。

DevTools 协议背后的目标为三折：

 - 提供用于将 DevTools 应用附加到 Microsoft Edge 的公共 API
 - 将 DevTools 功能的访问权限扩展到外部工具客户端
 - 在运行 Microsoft Edge 的 Windows 10 设备范围内启用远程调试 

DevTools 协议的版本0.2 包括 (只读) 调试和控制台 Api 以及版本0.1 中引入的核心脚本调试功能的样式和布局的新域。 在 Edge DevTools UI 中，这将转换为 [**元素**](../../devtools-guide/elements.md)、 [**控制台**](../../devtools-guide/console.md) 和 [**调试器**](../../devtools-guide/debugger.md)  面板中可用的功能。
