---
description: Microsoft Edge DevTools 协议版本0.1 的发行说明
title: DevTools 协议版本0.1 发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 3c0648467c20572a525fe257788068966efd193c
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104733"
---
# <span data-ttu-id="a8c7b-103">DevTools 协议版本0.1 发行说明</span><span class="sxs-lookup"><span data-stu-id="a8c7b-103">DevTools Protocol Version 0.1 Release Notes</span></span>

> [!NOTE]
> <span data-ttu-id="a8c7b-104">Microsoft Edge DevTools 协议仅适用于 [windows 10 2018 年4月更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 及更高版本的 [Windows 预览体验计划预览](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="a8c7b-105">Microsoft **Edge DevTools 协议** 版本0.1 提供了在新的独立 [Microsoft edge DevTools 预览版](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用中测试 EdgeHTML 检测和基本远程调试的早期预览。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-105">Version 0.1 of the Microsoft **Edge DevTools Protocol** provides an early preview for testing EdgeHTML instrumentation and basic remote debugging in the new standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app.</span></span> <span data-ttu-id="a8c7b-106">因此，它要求你运行的是 [windows 10 四月2018更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 或更高版本的 [Windows 预览体验计划](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-106">As such, it requires you to be running [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="a8c7b-107">DevTools 协议背后的目标为三折：</span><span class="sxs-lookup"><span data-stu-id="a8c7b-107">The goals behind the DevTools Protocol are three-fold:</span></span>

 - <span data-ttu-id="a8c7b-108">提供用于将 DevTools 应用附加到 Microsoft Edge 的公共 API</span><span class="sxs-lookup"><span data-stu-id="a8c7b-108">Provide a public API for our DevTools app to attach to Microsoft Edge</span></span>
 - <span data-ttu-id="a8c7b-109">将 DevTools 功能的访问权限扩展到外部工具客户端</span><span class="sxs-lookup"><span data-stu-id="a8c7b-109">Expand access of DevTools functionality to external tooling clients</span></span>
 - <span data-ttu-id="a8c7b-110">在运行 Microsoft Edge 的 Windows 10 设备范围内启用远程调试</span><span class="sxs-lookup"><span data-stu-id="a8c7b-110">Enable remote debugging across the range of Windows 10 devices running Microsoft Edge</span></span> 

<span data-ttu-id="a8c7b-111">此预备版本提供核心调试功能，例如设置断点、单步执行代码和浏览堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-111">This preliminary release provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="a8c7b-112">在 Edge DevTools UI 中，这将转换为 " [**调试器**](../../devtools-guide/debugger.md) " 面板中可用的功能，减去 Web 存储、服务工作人员、缓存 API 和 IndexedDB) 的缓存检查 (。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-112">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> 

<span data-ttu-id="a8c7b-113">将在即将推出的版本中添加更多的调试器功能，后跟用于其他 [DevTools](../../devtools-guide.md) 面板的检测。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-113">Further debugger functionality will be added in upcoming releases, followed by the instrumentation powering other [DevTools](../../devtools-guide.md) panels.</span></span>
