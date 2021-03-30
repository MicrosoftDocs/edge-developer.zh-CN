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
# <span data-ttu-id="a4e51-103">DevTools 协议版本 0.1 发行说明</span><span class="sxs-lookup"><span data-stu-id="a4e51-103">DevTools Protocol Version 0.1 Release Notes</span></span>

> [!NOTE]
> <span data-ttu-id="a4e51-104">Microsoft Edge DevTools 协议仅适用于 [Windows 10 2018 年 4](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 月更新和 [更高版本的 Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="a4e51-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="a4e51-105">Microsoft **Edge DevTools 协议** 版本 0.1 提供早期预览版，用于测试新的独立 [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用中的边缘HTML 检测和基本远程调试。</span><span class="sxs-lookup"><span data-stu-id="a4e51-105">Version 0.1 of the Microsoft **Edge DevTools Protocol** provides an early preview for testing EdgeHTML instrumentation and basic remote debugging in the new standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app.</span></span> <span data-ttu-id="a4e51-106">因此，需要你运行 [Windows 10 2018 年 4](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 月更新或更高版本 [的 Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="a4e51-106">As such, it requires you to be running [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="a4e51-107">DevTools 协议背后的目标有三重：</span><span class="sxs-lookup"><span data-stu-id="a4e51-107">The goals behind the DevTools Protocol are three-fold:</span></span>

 - <span data-ttu-id="a4e51-108">为要附加到 Microsoft Edge 的 DevTools 应用提供公共 API</span><span class="sxs-lookup"><span data-stu-id="a4e51-108">Provide a public API for our DevTools app to attach to Microsoft Edge</span></span>
 - <span data-ttu-id="a4e51-109">扩展对外部工具客户端的 DevTools 功能的访问</span><span class="sxs-lookup"><span data-stu-id="a4e51-109">Expand access of DevTools functionality to external tooling clients</span></span>
 - <span data-ttu-id="a4e51-110">在运行 Microsoft Edge 的 Windows 10 设备范围内启用远程调试</span><span class="sxs-lookup"><span data-stu-id="a4e51-110">Enable remote debugging across the range of Windows 10 devices running Microsoft Edge</span></span> 

<span data-ttu-id="a4e51-111">此初步版本提供了核心调试功能，例如设置断点、逐步执行代码和探索堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="a4e51-111">This preliminary release provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="a4e51-112">在 Edge DevTools UI 中，这转换为调试器面板[](../../devtools-guide/debugger.md)中提供的功能，减去 Web 存储、服务工作器、缓存 API 和 IndexedDB (的缓存检查) 。</span><span class="sxs-lookup"><span data-stu-id="a4e51-112">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> 

<span data-ttu-id="a4e51-113">将在即将发布的版本中添加进一步调试器功能，后跟为其他 [DevTools](../index.md) 面板提供电源的检测。</span><span class="sxs-lookup"><span data-stu-id="a4e51-113">Further debugger functionality will be added in upcoming releases, followed by the instrumentation powering other [DevTools](../index.md) panels.</span></span>
