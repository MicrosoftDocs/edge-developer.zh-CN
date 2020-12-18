---
description: 查看 Windows 10 2018 年 10 月更新中的 Microsoft Edge DevTools 中的新增功能
title: Microsoft Edge DevTools 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， edgehtml 18
ms.custom: RS5, seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2f1d3c6fe5bf061186d5c6593a115a8b6794c0dd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232483"
---
# 最新 Windows 10 更新中的 DevTools (EdgeHTML 18)

Microsoft Edge DevTools 的最新更新为 UI 和底层添加了许多便利，包括新的服务工作者和存储专用面板、调试器[**](#service-workers-panel)中的源文件搜索工具，以及[](#source-file-search-tools)用于样式/布局调试和控制台 API 的新边缘[DevTools 协议](#edge-devtools-protocol-updates)域。 [**](#storage-panel)

以下是 Windows [10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763) 月 ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18) 更新中提供的最新 Microsoft Edge DevTools) 。 除此之外，我们还修复了许多辅助功能、可靠性和性能缺陷，以改进基础！

## DevTools 应用

我们已更新独立 Microsoft [Edge DevTools Preview 应用](./index.md#microsoft-store-app)。 最新版本包括对调试器中核心功能、用于只读操作 (元素和控制台面板[****](./debugger.md)[**) 远程**](./console.md)调试[****](./elements.md)访问权限。

## 服务工作人员面板

现在，有一个专用的 [**服务**](./service-workers.md) 工作者面板，用于检查、管理和调试网站的服务工作人员。 这提供了与以前在调试器面板中相同的功能**， (UI！) 。

![服务工作人员面板](./media/service_worker.png)

## 存储面板

我们还将调试器中以前 (本地和*Sesion 存储、IndexedDB、Cookie、Cache*) 的所有本地存储检查器移动到其自己的专用存储[**面板**](./storage.md)。 **

![存储面板](./media/storage_cache.png)

## 源文件搜索工具

调试 [**器现在**](./debugger.md) 具有 [源文件搜索](./debugger.md#file-search) 窗格。 当你尝试在源** 中查找特定 () ，使用"在文件中查找"命令打开 `Ctrl` + `Shift` + `F` 它。 工具栏提供不同的搜索选项，包括正则表达式。 

![调试器文件搜索](./media/debugger_file_search.png)

您还可以使用 Open 文件命令快速打开任何加载** 的源文件 `Ctrl` + `P` () 命令。

![调试器打开文件](./media/debugger_open_file.png)

## Edge DevTools 协议更新

版本[0.2](../devtools-protocol/0.2/index.md)的 DevTools 协议提供了样式和布局的新域 (只读) 调试和控制台 API，以及版本[0.1](../devtools-protocol/0.1/index.md)中引入的核心脚本调试功能。 在 Edge DevTools UI 中，这转换为[**Elements**](../devtools-guide/elements.md) (中提供的功能，以便执行只读操作) 控制台和[**调试器**](../devtools-guide/debugger.md)面板。 [****](../devtools-guide/console.md)
