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
# <span data-ttu-id="72d9b-104">最新 Windows 10 更新中的 DevTools (EdgeHTML 18)</span><span class="sxs-lookup"><span data-stu-id="72d9b-104">DevTools in the latest Windows 10 update (EdgeHTML 18)</span></span>

<span data-ttu-id="72d9b-105">Microsoft Edge DevTools 的最新更新为 UI 和底层添加了许多便利，包括新的服务工作者和存储专用面板、调试器[\*\*](#service-workers-panel)中的源文件搜索工具，以及[](#source-file-search-tools)用于样式/布局调试和控制台 API 的新边缘[DevTools 协议](#edge-devtools-protocol-updates)域。 [\*\*](#storage-panel)</span><span class="sxs-lookup"><span data-stu-id="72d9b-105">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for [*Service Workers*](#service-workers-panel) and [*Storage*](#storage-panel), source [file search](#source-file-search-tools) tools in the Debugger, and new [Edge DevTools Protocol domains](#edge-devtools-protocol-updates) for style/layout debugging and console APIs.</span></span>

<span data-ttu-id="72d9b-106">以下是 Windows [10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763) 月 ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18) 更新中提供的最新 Microsoft Edge DevTools) 。</span><span class="sxs-lookup"><span data-stu-id="72d9b-106">Here are the latest Microsoft Edge DevTools features available now in the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)).</span></span> <span data-ttu-id="72d9b-107">除此之外，我们还修复了许多辅助功能、可靠性和性能缺陷，以改进基础！</span><span class="sxs-lookup"><span data-stu-id="72d9b-107">In addition to all this, we’ve also fixed a number of accessibility, reliability, and performance bugs to improve fundamentals!</span></span>

## <span data-ttu-id="72d9b-108">DevTools 应用</span><span class="sxs-lookup"><span data-stu-id="72d9b-108">DevTools app</span></span>

<span data-ttu-id="72d9b-109">我们已更新独立 Microsoft [Edge DevTools Preview 应用](./index.md#microsoft-store-app)。</span><span class="sxs-lookup"><span data-stu-id="72d9b-109">We've updated the standalone [Microsoft Edge DevTools Preview app](./index.md#microsoft-store-app).</span></span> <span data-ttu-id="72d9b-110">最新版本包括对调试器中核心功能、用于只读操作 (元素和控制台面板[\*\*\*\*](./debugger.md)[**) 远程**](./console.md)调试[\*\*\*\*](./elements.md)访问权限。</span><span class="sxs-lookup"><span data-stu-id="72d9b-110">The latest release includes remote debugging access to core funtionality in the [**Debugger**](./debugger.md), [**Elements**](./elements.md) (for read-only operations), and [**Console**](./console.md) panels.</span></span>

## <span data-ttu-id="72d9b-111">服务工作人员面板</span><span class="sxs-lookup"><span data-stu-id="72d9b-111">Service Workers panel</span></span>

<span data-ttu-id="72d9b-112">现在，有一个专用的 [**服务**](./service-workers.md) 工作者面板，用于检查、管理和调试网站的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="72d9b-112">There's now a dedicated [**Service Workers**](./service-workers.md) panel for inspecting, managing, and debugging your site's service workers.</span></span> <span data-ttu-id="72d9b-113">这提供了与以前在调试器面板中相同的功能\*\*， (UI！) 。</span><span class="sxs-lookup"><span data-stu-id="72d9b-113">This provides the same functionality as was previously in the *Debugger* panel (now with a less-crowded UI!).</span></span>

![服务工作人员面板](./media/service_worker.png)

## <span data-ttu-id="72d9b-115">存储面板</span><span class="sxs-lookup"><span data-stu-id="72d9b-115">Storage panel</span></span>

<span data-ttu-id="72d9b-116">我们还将调试器中以前 (本地和*Sesion 存储、IndexedDB、Cookie、Cache*) 的所有本地存储检查器移动到其自己的专用存储[**面板**](./storage.md)。 \*\*</span><span class="sxs-lookup"><span data-stu-id="72d9b-116">We've also moved all the local storage inspectors (*Local and Sesion Storage, IndexedDB, Cookies, Cache*) previously in the *Debugger* to their own dedicated [**Storage**](./storage.md) panel.</span></span>

![存储面板](./media/storage_cache.png)

## <span data-ttu-id="72d9b-118">源文件搜索工具</span><span class="sxs-lookup"><span data-stu-id="72d9b-118">Source file search tools</span></span>

<span data-ttu-id="72d9b-119">调试 [**器现在**](./debugger.md) 具有 [源文件搜索](./debugger.md#file-search) 窗格。</span><span class="sxs-lookup"><span data-stu-id="72d9b-119">The [**Debugger**](./debugger.md) now has a [source file search](./debugger.md#file-search) pane.</span></span> <span data-ttu-id="72d9b-120">当你尝试在源\*\* 中查找特定 () ，使用"在文件中查找"命令打开 `Ctrl` + `Shift` + `F` 它。</span><span class="sxs-lookup"><span data-stu-id="72d9b-120">Open it with the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="72d9b-121">工具栏提供不同的搜索选项，包括正则表达式。</span><span class="sxs-lookup"><span data-stu-id="72d9b-121">The toolbar provides different search options, including regular expressions.</span></span> 

![调试器文件搜索](./media/debugger_file_search.png)

<span data-ttu-id="72d9b-123">您还可以使用 Open 文件命令快速打开任何加载\*\* 的源文件 `Ctrl` + `P` () 命令。</span><span class="sxs-lookup"><span data-stu-id="72d9b-123">You can also quickly open any loaded source file with the *Open file* (`Ctrl`+`P`) command.</span></span>

![调试器打开文件](./media/debugger_open_file.png)

## <span data-ttu-id="72d9b-125">Edge DevTools 协议更新</span><span class="sxs-lookup"><span data-stu-id="72d9b-125">Edge DevTools Protocol updates</span></span>

<span data-ttu-id="72d9b-126">版本[0.2](../devtools-protocol/0.2/index.md)的 DevTools 协议提供了样式和布局的新域 (只读) 调试和控制台 API，以及版本[0.1](../devtools-protocol/0.1/index.md)中引入的核心脚本调试功能。</span><span class="sxs-lookup"><span data-stu-id="72d9b-126">[Version 0.2](../devtools-protocol/0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](../devtools-protocol/0.1/index.md).</span></span> <span data-ttu-id="72d9b-127">在 Edge DevTools UI 中，这转换为[**Elements**](../devtools-guide/elements.md) (中提供的功能，以便执行只读操作) 控制台和[**调试器**](../devtools-guide/debugger.md)面板。 [\*\*\*\*](../devtools-guide/console.md)</span><span class="sxs-lookup"><span data-stu-id="72d9b-127">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md) (for read-only operations), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>
