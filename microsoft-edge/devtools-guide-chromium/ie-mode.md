---
description: IE 模式和 Microsoft Edge （Chromium） DevTools
title: Internet Explorer 模式和 DevTools
author: robpaveza
ms.author: ropaveza
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、ie11、internet explorer 11、ie 模式
ms.openlocfilehash: 18e5f029d277e446857ec48b9cf129149f219256
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564162"
---
# <span data-ttu-id="7b613-104">Internet Explorer 模式和 DevTools</span><span class="sxs-lookup"><span data-stu-id="7b613-104">Internet Explorer mode and the DevTools</span></span>

<span data-ttu-id="7b613-105">本文档介绍 Internet Explorer 模式（IE 模式）如何与 Microsoft Edge （Chromium） DevTools 集成。</span><span class="sxs-lookup"><span data-stu-id="7b613-105">This document describes how Internet Explorer mode (IE mode) integrates with the Microsoft Edge (Chromium) DevTools.</span></span>

## <span data-ttu-id="7b613-106">了解 IE 模式</span><span class="sxs-lookup"><span data-stu-id="7b613-106">Understanding IE mode</span></span>

<span data-ttu-id="7b613-107">IE 模式是一种机制，企业可以使用该机制来指定一组网站，直到现在才在 Internet Explorer 11 中工作。</span><span class="sxs-lookup"><span data-stu-id="7b613-107">IE mode is a mechanism by which enterprises may specify a set of web sites that, until now, only worked in Internet Explorer 11.</span></span> <span data-ttu-id="7b613-108">当在 Microsoft Edge （Chromium）中查看这些网站时，将在选项卡中运行并呈现一个完整的 Internet Explorer 11 实例。这允许企业管理 IE 文档模式、ActiveX 控件以及当前与任何新式 web 浏览器不兼容的其他旧版组件的兼容性。</span><span class="sxs-lookup"><span data-stu-id="7b613-108">When these web sites are viewed in Microsoft Edge (Chromium), a full instance of Internet Explorer 11 is running and rendered within the tab. This allows enterprises to manage compatibility for IE document modes, ActiveX controls, and other legacy components that are currently not compatible with any modern web browsers.</span></span>

<span data-ttu-id="7b613-109">在 IE 模式下，呈现过程完全基于 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="7b613-109">Within IE mode, the rendering process is entirely based in Internet Explorer 11.</span></span> <span data-ttu-id="7b613-110">Microsoft Edge （Chromium）管理器进程管理呈现过程的生存期，但它受限于给定网站或应用程序上的选项卡生存期。</span><span class="sxs-lookup"><span data-stu-id="7b613-110">The Microsoft Edge (Chromium) manager process manages the lifetime of the rendering process, but it is constrained to the tab's lifetime on a given site or application.</span></span> <span data-ttu-id="7b613-111">在 IE 模式下呈现选项卡时，将在给定选项卡的地址栏中显示一个标记：</span><span class="sxs-lookup"><span data-stu-id="7b613-111">When a tab is rendering in IE mode, a badge appears in the address bar for the given tab:</span></span>

![地址栏中的 IE 模式标记](./media/ie-mode-badge.png)

<span data-ttu-id="7b613-113">IE 模式目前适用于 Windows 10 版本1903（可能2019更新），但即将推出所有受支持的 Windows 平台。</span><span class="sxs-lookup"><span data-stu-id="7b613-113">IE mode is currently available on Windows 10 Version 1903 (May 2019 Update) but is coming soon to all supported Windows platforms.</span></span>

## <span data-ttu-id="7b613-114">在 IE 模式下的选项卡上启动 DevTools</span><span class="sxs-lookup"><span data-stu-id="7b613-114">Launching the DevTools on a tab in IE mode</span></span>

<span data-ttu-id="7b613-115">如果您尝试在 IE 模式下查看网站的文档模式，则可以在地址栏中单击锁屏提醒。</span><span class="sxs-lookup"><span data-stu-id="7b613-115">If you are trying to view the document mode of a web site in IE mode, you can click on the badge in the address bar.</span></span>

![通过 IE mode 徽章查看文档模式](./media/ie-mode-badge-doc-mode.png)

<span data-ttu-id="7b613-117">在 IE 模式下的选项卡上，DevTools 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="7b613-117">While on a tab in IE mode, the DevTools will not work.</span></span> <span data-ttu-id="7b613-118">按 `F12` 或 `Ctrl` + `Shift` + `I` 将仅启动 Microsoft Edge （Chromium） DevTools 的空白实例，其中包含以下消息： "开发工具在 Internet Explorer 模式中不可用。</span><span class="sxs-lookup"><span data-stu-id="7b613-118">Pressing `F12` or `Ctrl`+`Shift`+`I` will only launch a blank instance of the Microsoft Edge (Chromium) DevTools with a message that reads: "Developer Tools are not available in Internet Explorer mode.</span></span> <span data-ttu-id="7b613-119">若要调试页面，请在 Internet Explorer 11 中打开它。 "</span><span class="sxs-lookup"><span data-stu-id="7b613-119">To debug the page, open it in Internet Explorer 11."</span></span> <span data-ttu-id="7b613-120">**查看源**将启动记事本，**检查元素**将在 IE 模式下的上下文菜单中不可见。</span><span class="sxs-lookup"><span data-stu-id="7b613-120">**View Source** will launch Notepad and **Inspect Element** will not be visible in the context menu in IE mode.</span></span>

<span data-ttu-id="7b613-121">这是因为在 IE 模式下，DevTools 中的多个组件（如网络和性能工具）将中断，而在 IE 模式下从 Chromium 切换到 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="7b613-121">This is because a number of components in the DevTools (like the Network and Performance tools) would break when the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span> <span data-ttu-id="7b613-122">若要向我们提供反馈，请单击 `:)` 图标。</span><span class="sxs-lookup"><span data-stu-id="7b613-122">To give us feedback, click the `:)` icon.</span></span>

![在 IE 模式下启动的 DevTools](./media/ie-mode-devtools.png)

<span data-ttu-id="7b613-124">如果你要开发或维护基于 Internet Explorer 11 的网站或应用程序，我们建议导航到 Internet Explorer 11 中的同一页面。</span><span class="sxs-lookup"><span data-stu-id="7b613-124">If you are developing or maintaining an Internet Explorer 11-based web site or application, we recommend navigating to the same page in Internet Explorer 11.</span></span> <span data-ttu-id="7b613-125">在 Windows 10 上，你可以在 "Windows 附件" 下的 "开始" 菜单中找到 Internet Explorer 11 的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7b613-125">On Windows 10, you can find the shortcut for Internet Explorer 11 on the Start Menu underneath Windows Accessories.</span></span> <span data-ttu-id="7b613-126">在 Windows 7 上，你可以在主 "开始" 菜单上找到 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="7b613-126">On Windows 7, you can find Internet Explorer 11 on the main Start Menu.</span></span> <span data-ttu-id="7b613-127">然后，你可以通过在 `F12` 上下文菜单中按下或单击 "**检查元素**" 来启动 Internet Explorer DevTools。</span><span class="sxs-lookup"><span data-stu-id="7b613-127">You can then launch the Internet Explorer DevTools by pressing `F12` or clicking **Inspect element** in the context menu.</span></span> <span data-ttu-id="7b613-128">若要了解有关如何使用这些工具的详细信息，请单击[此处](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85))。</span><span class="sxs-lookup"><span data-stu-id="7b613-128">To learn more about how to use those tools, click [here](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85)).</span></span>

## <span data-ttu-id="7b613-129">远程调试和 IE 模式</span><span class="sxs-lookup"><span data-stu-id="7b613-129">Remote debugging and IE mode</span></span>

<span data-ttu-id="7b613-130">你可以启动启用了远程调试的 Microsoft Edge （Chromium），它通常是从命令行中的工具（如 Visual Studio 或代码启动边缘）：</span><span class="sxs-lookup"><span data-stu-id="7b613-130">You can launch Microsoft Edge (Chromium) with remote debugging enabled, which is typically how tools like Visual Studio or VS Code launch Edge, from the command line:</span></span>

`start msedge --remote-debugging-port=9222`

<span data-ttu-id="7b613-131">使用此命令行参数启动 Microsoft Edge （Chromium）时，IE 模式将不可用。</span><span class="sxs-lookup"><span data-stu-id="7b613-131">When Microsoft Edge (Chromium) is launched with this command line argument, IE mode will be unavailable.</span></span> <span data-ttu-id="7b613-132">你仍可以导航到将以其他方式在 IE 模式下显示的网站或应用程序，但内容将通过 Chromium （而不是 Internet Explorer 11）呈现。</span><span class="sxs-lookup"><span data-stu-id="7b613-132">You can still navigate to web sites or applications that would otherwise be in IE mode but the content will render via Chromium, not Internet Explorer 11.</span></span> <span data-ttu-id="7b613-133">你可以预见，依赖 IE11 的这些页面部分（如 ActiveX 控件）将无法正确呈现。</span><span class="sxs-lookup"><span data-stu-id="7b613-133">You can expect that the parts of those pages that rely on IE11, like ActiveX controls, will not render correctly.</span></span> <span data-ttu-id="7b613-134">"IE 模式标记" 将不再显示在地址栏中。</span><span class="sxs-lookup"><span data-stu-id="7b613-134">The IE mode badge will no longer appear in the address bar.</span></span>

<span data-ttu-id="7b613-135">在完全关闭 Microsoft Edge （Chromium）之前，IE 模式将一直不可用。</span><span class="sxs-lookup"><span data-stu-id="7b613-135">IE mode will remain unavailable until you completely close Microsoft Edge (Chromium).</span></span>