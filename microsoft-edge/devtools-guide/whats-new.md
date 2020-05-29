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
# <span data-ttu-id="b0e06-104">最新 Windows 10 更新（EdgeHTML 18）中的 DevTools</span><span class="sxs-lookup"><span data-stu-id="b0e06-104">DevTools in the latest Windows 10 update (EdgeHTML 18)</span></span>

<span data-ttu-id="b0e06-105">对 Microsoft Edge DevTools 的最新更新向 UI 添加了许多 conveniences，包括[*服务工作人员*](#service-workers-panel)和[*存储*](#storage-panel)的新专用面板、调试程序中的源代码[文件搜索](#source-file-search-tools)工具以及样式/布局调试和控制台 Api 的新的[边缘 DevTools 协议域](#edge-devtools-protocol-updates)。</span><span class="sxs-lookup"><span data-stu-id="b0e06-105">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for [*Service Workers*](#service-workers-panel) and [*Storage*](#storage-panel), source [file search](#source-file-search-tools) tools in the Debugger, and new [Edge DevTools Protocol domains](#edge-devtools-protocol-updates) for style/layout debugging and console APIs.</span></span>

<span data-ttu-id="b0e06-106">下面是[Windows 10 年10月2018更新](/windows/uwp/whats-new/windows-10-build-17763)（[EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)）现已推出的最新 Microsoft Edge DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="b0e06-106">Here are the latest Microsoft Edge DevTools features available now in the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)).</span></span> <span data-ttu-id="b0e06-107">此外，我们还修复了许多辅助功能、可靠性和性能 bug 来改进基础知识！</span><span class="sxs-lookup"><span data-stu-id="b0e06-107">In addition to all this, we’ve also fixed a number of accessibility, reliability, and performance bugs to improve fundamentals!</span></span>

## <span data-ttu-id="b0e06-108">DevTools 应用</span><span class="sxs-lookup"><span data-stu-id="b0e06-108">DevTools app</span></span>

<span data-ttu-id="b0e06-109">我们已更新了独立的[Microsoft Edge DevTools 预览版应用](../devtools-guide.md#microsoft-store-app)。</span><span class="sxs-lookup"><span data-stu-id="b0e06-109">We've updated the standalone [Microsoft Edge DevTools Preview app](../devtools-guide.md#microsoft-store-app).</span></span> <span data-ttu-id="b0e06-110">最新版本包括在[**调试程序**](./debugger.md)中对核心 funtionality 的远程调试访问、[**元素**](./elements.md)（适用于只读操作）和[**控制台**](./console.md)面板。</span><span class="sxs-lookup"><span data-stu-id="b0e06-110">The latest release includes remote debugging access to core funtionality in the [**Debugger**](./debugger.md), [**Elements**](./elements.md) (for read-only operations), and [**Console**](./console.md) panels.</span></span>

## <span data-ttu-id="b0e06-111">服务工作者面板</span><span class="sxs-lookup"><span data-stu-id="b0e06-111">Service Workers panel</span></span>

<span data-ttu-id="b0e06-112">现在有一个专用的[**服务工作者**](./service-workers.md)面板，用于检查、管理和调试您的网站的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="b0e06-112">There's now a dedicated [**Service Workers**](./service-workers.md) panel for inspecting, managing, and debugging your site's service workers.</span></span> <span data-ttu-id="b0e06-113">这提供的功能与以前在*调试程序*面板中的功能相同（现在使用较拥挤的 UI！）。</span><span class="sxs-lookup"><span data-stu-id="b0e06-113">This provides the same functionality as was previously in the *Debugger* panel (now with a less-crowded UI!).</span></span>

![服务工作者面板](./media/service_worker.png)

## <span data-ttu-id="b0e06-115">存储面板</span><span class="sxs-lookup"><span data-stu-id="b0e06-115">Storage panel</span></span>

<span data-ttu-id="b0e06-116">我们还将以前在*调试程序*中的所有本地存储检查器（*本地和 Sesion 存储、IndexedDB、cookie、缓存*）移动到其自己的 "专用[**存储**](./storage.md)" 面板。</span><span class="sxs-lookup"><span data-stu-id="b0e06-116">We've also moved all the local storage inspectors (*Local and Sesion Storage, IndexedDB, Cookies, Cache*) previously in the *Debugger* to their own dedicated [**Storage**](./storage.md) panel.</span></span>

![存储面板](./media/storage_cache.png)

## <span data-ttu-id="b0e06-118">源文件搜索工具</span><span class="sxs-lookup"><span data-stu-id="b0e06-118">Source file search tools</span></span>

<span data-ttu-id="b0e06-119">[**调试器**](./debugger.md)现在有一个[源文件搜索](./debugger.md#file-search)窗格。</span><span class="sxs-lookup"><span data-stu-id="b0e06-119">The [**Debugger**](./debugger.md) now has a [source file search](./debugger.md#file-search) pane.</span></span> <span data-ttu-id="b0e06-120">如果你要*Find in files* `Ctrl` + `Shift` + `F` 在源中查找特定的代码字符串，请使用 "在文件中查找" 命令（）将其打开。</span><span class="sxs-lookup"><span data-stu-id="b0e06-120">Open it with the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="b0e06-121">工具栏提供了不同的搜索选项，包括正则表达式。</span><span class="sxs-lookup"><span data-stu-id="b0e06-121">The toolbar provides different search options, including regular expressions.</span></span> 

![调试器文件搜索](./media/debugger_file_search.png)

<span data-ttu-id="b0e06-123">您还可以通过 "*打开文件*" （ `Ctrl` + ）命令快速打开任何加载的源文件 `P` 。</span><span class="sxs-lookup"><span data-stu-id="b0e06-123">You can also quickly open any loaded source file with the *Open file* (`Ctrl`+`P`) command.</span></span>

![调试器打开文件](./media/debugger_open_file.png)

## <span data-ttu-id="b0e06-125">Edge DevTools 协议更新</span><span class="sxs-lookup"><span data-stu-id="b0e06-125">Edge DevTools Protocol updates</span></span>

<span data-ttu-id="b0e06-126">除了[版本 0.1](../devtools-protocol/0.1/index.md)中引入的核心脚本调试功能之外，DevTools 协议的[版本 0.2](../devtools-protocol/0.2/index.md)还提供了新域用于样式和布局（只读）调试和控制台 api。</span><span class="sxs-lookup"><span data-stu-id="b0e06-126">[Version 0.2](../devtools-protocol/0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](../devtools-protocol/0.1/index.md).</span></span> <span data-ttu-id="b0e06-127">在 Edge DevTools UI 中，这将转换为[**元素**](../devtools-guide/elements.md)中可用的功能（适用于只读操作）、[**控制台**](../devtools-guide/console.md)和[**调试器**](../devtools-guide/debugger.md)面板。</span><span class="sxs-lookup"><span data-stu-id="b0e06-127">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md) (for read-only operations), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>
