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
# <span data-ttu-id="66059-103">DevTools 协议版本0.2 发行说明</span><span class="sxs-lookup"><span data-stu-id="66059-103">DevTools Protocol Version 0.2 Release Notes</span></span>

> [!NOTE]
> <span data-ttu-id="66059-104">Microsoft Edge DevTools 协议的版本0.2 仅适用于 [windows 10 10 月2018更新](/windows/uwp/whats-new/windows-10-build-17763) 及更高版本的 [Windows 预览体验计划预览版](https://insider.windows.com/getting-started/) 。</span><span class="sxs-lookup"><span data-stu-id="66059-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) and later [Windows Insider Preview](https://insider.windows.com/getting-started/) builds.</span></span>

<span data-ttu-id="66059-105">Microsoft **Edge DevTools 协议** 版本0.2 在新的独立 [Microsoft edge DevTools 预览版](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用中提供了用于测试 EdgeHTML 检测和基本远程调试的预览。</span><span class="sxs-lookup"><span data-stu-id="66059-105">Version 0.2 of the Microsoft **Edge DevTools Protocol** provides a preview for testing EdgeHTML instrumentation and basic remote debugging in the new standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app.</span></span> <span data-ttu-id="66059-106">因此，它需要你运行 [2018 年10月更新](/windows/uwp/whats-new/windows-10-build-17763) 或 [Windows 预览体验计划预览版](https://insider.windows.com/getting-started/) 的更高版本。</span><span class="sxs-lookup"><span data-stu-id="66059-106">As such, it requires you to be running the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) or a later [Windows Insider Preview](https://insider.windows.com/getting-started/) build.</span></span>

<span data-ttu-id="66059-107">DevTools 协议背后的目标为三折：</span><span class="sxs-lookup"><span data-stu-id="66059-107">The goals behind the DevTools Protocol are three-fold:</span></span>

 - <span data-ttu-id="66059-108">提供用于将 DevTools 应用附加到 Microsoft Edge 的公共 API</span><span class="sxs-lookup"><span data-stu-id="66059-108">Provide a public API for our DevTools app to attach to Microsoft Edge</span></span>
 - <span data-ttu-id="66059-109">将 DevTools 功能的访问权限扩展到外部工具客户端</span><span class="sxs-lookup"><span data-stu-id="66059-109">Expand access of DevTools functionality to external tooling clients</span></span>
 - <span data-ttu-id="66059-110">在运行 Microsoft Edge 的 Windows 10 设备范围内启用远程调试</span><span class="sxs-lookup"><span data-stu-id="66059-110">Enable remote debugging across the range of Windows 10 devices running Microsoft Edge</span></span> 

<span data-ttu-id="66059-111">DevTools 协议的版本0.2 包括 (只读) 调试和控制台 Api 以及版本0.1 中引入的核心脚本调试功能的样式和布局的新域。</span><span class="sxs-lookup"><span data-stu-id="66059-111">Version 0.2 of the DevTools Protocol includes new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in Version 0.1.</span></span> <span data-ttu-id="66059-112">在 Edge DevTools UI 中，这将转换为 [**元素**](../../devtools-guide/elements.md)、 [**控制台**](../../devtools-guide/console.md) 和 [**调试器**](../../devtools-guide/debugger.md)  面板中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="66059-112">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../../devtools-guide/elements.md), [**Console**](../../devtools-guide/console.md) and [**Debugger**](../../devtools-guide/debugger.md)  panels.</span></span>
