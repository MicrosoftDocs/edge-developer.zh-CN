---
description: See what's new in the Microsoft Edge DevTools in the Windows 10 October 2018 Update
title: What's new in the Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, edgehtml 18
ms.custom: RS5, seodec18
ms.openlocfilehash: 604419f4c77ccaaf2dfd3179273be803cde86fc8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563440"
---
# <span data-ttu-id="2b427-104">DevTools in the latest Windows 10 update (EdgeHTML 18)</span><span class="sxs-lookup"><span data-stu-id="2b427-104">DevTools in the latest Windows 10 update (EdgeHTML 18)</span></span>

<span data-ttu-id="2b427-105">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for [*Service Workers*](#service-workers-panel) and [*Storage*](#storage-panel), source [file search](#source-file-search-tools) tools in the Debugger, and new [Edge DevTools Protocol domains](#edge-devtools-protocol-updates) for style/layout debugging and console APIs.</span><span class="sxs-lookup"><span data-stu-id="2b427-105">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for [*Service Workers*](#service-workers-panel) and [*Storage*](#storage-panel), source [file search](#source-file-search-tools) tools in the Debugger, and new [Edge DevTools Protocol domains](#edge-devtools-protocol-updates) for style/layout debugging and console APIs.</span></span>

<span data-ttu-id="2b427-106">Here are the latest Microsoft Edge DevTools features available now in the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)).</span><span class="sxs-lookup"><span data-stu-id="2b427-106">Here are the latest Microsoft Edge DevTools features available now in the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)).</span></span> <span data-ttu-id="2b427-107">In addition to all this, we’ve also fixed a number of accessibility, reliability, and performance bugs to improve fundamentals!</span><span class="sxs-lookup"><span data-stu-id="2b427-107">In addition to all this, we’ve also fixed a number of accessibility, reliability, and performance bugs to improve fundamentals!</span></span>

## <span data-ttu-id="2b427-108">DevTools app</span><span class="sxs-lookup"><span data-stu-id="2b427-108">DevTools app</span></span>

<span data-ttu-id="2b427-109">We've updated the standalone [Microsoft Edge DevTools Preview app](../devtools-guide.md#microsoft-store-app).</span><span class="sxs-lookup"><span data-stu-id="2b427-109">We've updated the standalone [Microsoft Edge DevTools Preview app](../devtools-guide.md#microsoft-store-app).</span></span> <span data-ttu-id="2b427-110">The latest release includes remote debugging access to core funtionality in the [**Debugger**](./debugger.md), [**Elements**](./elements.md) (for read-only operations), and [**Console**](./console.md) panels.</span><span class="sxs-lookup"><span data-stu-id="2b427-110">The latest release includes remote debugging access to core funtionality in the [**Debugger**](./debugger.md), [**Elements**](./elements.md) (for read-only operations), and [**Console**](./console.md) panels.</span></span>

## <span data-ttu-id="2b427-111">Service Workers panel</span><span class="sxs-lookup"><span data-stu-id="2b427-111">Service Workers panel</span></span>

<span data-ttu-id="2b427-112">There's now a dedicated [**Service Workers**](./service-workers.md) panel for inspecting, managing, and debugging your site's service workers.</span><span class="sxs-lookup"><span data-stu-id="2b427-112">There's now a dedicated [**Service Workers**](./service-workers.md) panel for inspecting, managing, and debugging your site's service workers.</span></span> <span data-ttu-id="2b427-113">This provides the same functionality as was previously in the *Debugger* panel (now with a less-crowded UI!).</span><span class="sxs-lookup"><span data-stu-id="2b427-113">This provides the same functionality as was previously in the *Debugger* panel (now with a less-crowded UI!).</span></span>

![Service Workers panel](./media/service_worker.png)

## <span data-ttu-id="2b427-115">Storage panel</span><span class="sxs-lookup"><span data-stu-id="2b427-115">Storage panel</span></span>

<span data-ttu-id="2b427-116">We've also moved all the local storage inspectors (*Local and Sesion Storage, IndexedDB, Cookies, Cache*) previously in the *Debugger* to their own dedicated [**Storage**](./storage.md) panel.</span><span class="sxs-lookup"><span data-stu-id="2b427-116">We've also moved all the local storage inspectors (*Local and Sesion Storage, IndexedDB, Cookies, Cache*) previously in the *Debugger* to their own dedicated [**Storage**](./storage.md) panel.</span></span>

![Storage panel](./media/storage_cache.png)

## <span data-ttu-id="2b427-118">Source file search tools</span><span class="sxs-lookup"><span data-stu-id="2b427-118">Source file search tools</span></span>

<span data-ttu-id="2b427-119">The [**Debugger**](./debugger.md) now has a [source file search](./debugger.md#file-search) pane.</span><span class="sxs-lookup"><span data-stu-id="2b427-119">The [**Debugger**](./debugger.md) now has a [source file search](./debugger.md#file-search) pane.</span></span> <span data-ttu-id="2b427-120">Open it with the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span><span class="sxs-lookup"><span data-stu-id="2b427-120">Open it with the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="2b427-121">The toolbar provides different search options, including regular expressions.</span><span class="sxs-lookup"><span data-stu-id="2b427-121">The toolbar provides different search options, including regular expressions.</span></span> 

![Debugger file search](./media/debugger_file_search.png)

<span data-ttu-id="2b427-123">You can also quickly open any loaded source file with the *Open file* (`Ctrl`+`P`) command.</span><span class="sxs-lookup"><span data-stu-id="2b427-123">You can also quickly open any loaded source file with the *Open file* (`Ctrl`+`P`) command.</span></span>

![Debugger open file](./media/debugger_open_file.png)

## <span data-ttu-id="2b427-125">Edge DevTools Protocol updates</span><span class="sxs-lookup"><span data-stu-id="2b427-125">Edge DevTools Protocol updates</span></span>

<span data-ttu-id="2b427-126">[Version 0.2](../devtools-protocol/0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](../devtools-protocol/0.1/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b427-126">[Version 0.2](../devtools-protocol/0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](../devtools-protocol/0.1/index.md).</span></span> <span data-ttu-id="2b427-127">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md) (for read-only operations), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span><span class="sxs-lookup"><span data-stu-id="2b427-127">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md) (for read-only operations), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>
