---
description: 查看2018年10月更新中的 Microsoft Edge DevTools 中的新增功能
title: Microsoft Edge DevTools 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、edgehtml 18
ms.custom: RS5, seodec18
ms.openlocfilehash: 604419f4c77ccaaf2dfd3179273be803cde86fc8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563440"
---
# 最新 Windows 10 更新（EdgeHTML 18）中的 DevTools

对 Microsoft Edge DevTools 的最新更新向 UI 添加了许多 conveniences，包括[*服务工作人员*](#service-workers-panel)和[*存储*](#storage-panel)的新专用面板、调试程序中的源代码[文件搜索](#source-file-search-tools)工具以及样式/布局调试和控制台 Api 的新的[边缘 DevTools 协议域](#edge-devtools-protocol-updates)。

下面是[Windows 10 年10月2018更新](/windows/uwp/whats-new/windows-10-build-17763)（[EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)）现已推出的最新 Microsoft Edge DevTools 功能。 此外，我们还修复了许多辅助功能、可靠性和性能 bug 来改进基础知识！

## DevTools 应用

我们已更新了独立的[Microsoft Edge DevTools 预览版应用](../devtools-guide.md#microsoft-store-app)。 最新版本包括在[**调试程序**](./debugger.md)中对核心 funtionality 的远程调试访问、[**元素**](./elements.md)（适用于只读操作）和[**控制台**](./console.md)面板。

## 服务工作者面板

现在有一个专用的[**服务工作者**](./service-workers.md)面板，用于检查、管理和调试您的网站的服务工作人员。 这提供的功能与以前在*调试程序*面板中的功能相同（现在使用较拥挤的 UI！）。

![服务工作者面板](./media/service_worker.png)

## 存储面板

我们还将以前在*调试程序*中的所有本地存储检查器（*本地和 Sesion 存储、IndexedDB、cookie、缓存*）移动到其自己的 "专用[**存储**](./storage.md)" 面板。

![存储面板](./media/storage_cache.png)

## 源文件搜索工具

[**调试器**](./debugger.md)现在有一个[源文件搜索](./debugger.md#file-search)窗格。 如果你要*Find in files* `Ctrl` + `Shift` + `F` 在源中查找特定的代码字符串，请使用 "在文件中查找" 命令（）将其打开。 工具栏提供了不同的搜索选项，包括正则表达式。 

![调试器文件搜索](./media/debugger_file_search.png)

您还可以通过 "*打开文件*" （ `Ctrl` + ）命令快速打开任何加载的源文件 `P` 。

![调试器打开文件](./media/debugger_open_file.png)

## Edge DevTools 协议更新

除了[版本 0.1](../devtools-protocol/0.1/index.md)中引入的核心脚本调试功能之外，DevTools 协议的[版本 0.2](../devtools-protocol/0.2/index.md)还提供了新域用于样式和布局（只读）调试和控制台 api。 在 Edge DevTools UI 中，这将转换为[**元素**](../devtools-guide/elements.md)中可用的功能（适用于只读操作）、[**控制台**](../devtools-guide/console.md)和[**调试器**](../devtools-guide/debugger.md)面板。
