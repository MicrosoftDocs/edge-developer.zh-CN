---
description: 使用 Microsoft Edge DevTools 协议检查和调试 Microsoft Edge (EdgeHTML) 浏览器。
title: Microsoft Edge DevTools 协议
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2ba81e51d3f9abd2aa2011993532566885ce553f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232456"
---
# <span data-ttu-id="c96b2-103">Microsoft Edge (EdgeHTML) DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="c96b2-103">Microsoft Edge (EdgeHTML) DevTools Protocol</span></span>

> [!NOTE]
> <span data-ttu-id="c96b2-104">Microsoft Edge (EdgeHTML) DevTools 协议仅适用于 [Windows 10 2018](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 年 4 月更新和更高版本。</span><span class="sxs-lookup"><span data-stu-id="c96b2-104">The Microsoft Edge (EdgeHTML) DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later builds.</span></span>

<span data-ttu-id="c96b2-105">开发人员工具可以使用 **Microsoft Edge (EdgeHTML) DevTools** 协议检查和调试 Microsoft Edge (EdgeHTML) 浏览器。</span><span class="sxs-lookup"><span data-stu-id="c96b2-105">Developer tools can use the **Microsoft Edge (EdgeHTML) DevTools Protocol** to inspect and debug the Microsoft Edge (EdgeHTML) browser.</span></span> <span data-ttu-id="c96b2-106">它提供了一组组织到 EdgeHTML 引擎检测的不同 [域中](0.2/domains/index.md) 的方法和事件。</span><span class="sxs-lookup"><span data-stu-id="c96b2-106">It provides a set of methods and events that are organized into different [Domains](0.2/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="c96b2-107">工具客户端可以调用这些方法，并通过与由 Microsoft Edge (EdgeHTML) 或 Windows Device Portal 托管的 *DevTools Server* 交换的 JSON Web 套接字消息来监视这些事件。</span><span class="sxs-lookup"><span data-stu-id="c96b2-107">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge (EdgeHTML) or the Windows Device Portal.</span></span> <span data-ttu-id="c96b2-108">Microsoft Edge (EdgeHTML) DevTools 使用此协议启用从[](0.2/clients.md#microsoft-edge-devtools-preview)Microsoft Store 提供的独立 DevTools 客户端远程调试运行 Microsoft Edge (EdgeHTML) 的[主机](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)。</span><span class="sxs-lookup"><span data-stu-id="c96b2-108">Microsoft Edge (EdgeHTML) DevTools uses this protocol to enable [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge (EdgeHTML) from the standalone DevTools client available from the [Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj).</span></span>

<span data-ttu-id="c96b2-109">Microsoft Edge (EdgeHTML) DevTools 协议旨在与 Chrome DevTools 协议 (请参阅 [适用于 DevTools 协议的 W3C WICG](https://github.com/WICG/devtools-protocol/)) ，尽管此版本存在已知的互操作性差异。</span><span class="sxs-lookup"><span data-stu-id="c96b2-109">The Microsoft Edge (EdgeHTML) DevTools Protocol is designed to align closely with the Chrome DevTools Protocol (see the [W3C WICG for DevTools Protocols](https://github.com/WICG/devtools-protocol/)), though there are known interoperability gaps in this release.</span></span>

## <span data-ttu-id="c96b2-110">使用协议</span><span class="sxs-lookup"><span data-stu-id="c96b2-110">Using the protocol</span></span>

<span data-ttu-id="c96b2-111">下面将了解如何将自定义工具客户端附加到 Microsoft Edge 中的 DevTools Server (EdgeHTML) 。</span><span class="sxs-lookup"><span data-stu-id="c96b2-111">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge (EdgeHTML).</span></span> <span data-ttu-id="c96b2-112">如果使用 [Microsoft](0.2/clients.md#microsoft-edge-devtools-preview) Edge DevTools 作为客户端，请参阅远程调试说明。</span><span class="sxs-lookup"><span data-stu-id="c96b2-112">See the [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) instructions if you're using Microsoft Edge DevTools as your client.</span></span>

1. <span data-ttu-id="c96b2-113">启动 Microsoft Edge (EdgeHTML) 远程调试端口处于打开状态，并指定要打开的 URL。</span><span class="sxs-lookup"><span data-stu-id="c96b2-113">Launch Microsoft Edge (EdgeHTML) with the remote debugging port open, specifying the URL you wish to open.</span></span> <span data-ttu-id="c96b2-114">例如：</span><span class="sxs-lookup"><span data-stu-id="c96b2-114">For example:</span></span>

    ```shell
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    <span data-ttu-id="c96b2-115">如果边缘已启动，URL 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="c96b2-115">If Edge is already launched, the URL parameter is optional.</span></span> <span data-ttu-id="c96b2-116">浏览器地址栏旁边将显示一个按钮，以指示 **开发人员工具服务器** 已启动：</span><span class="sxs-lookup"><span data-stu-id="c96b2-116">A button will appear next to the browser address bar to indicate the **Developer tools server** has started:</span></span>

    ![开发人员工具服务器](media/developer-tools-server.png) 

2. <span data-ttu-id="c96b2-118">使用此 [HTTP 终结点](0.2/http.md) 获取可附加页面目标的列表：</span><span class="sxs-lookup"><span data-stu-id="c96b2-118">Use this [HTTP endpoint](0.2/http.md) to get a list of attachable page targets:</span></span>

    ```http
    http://localhost:9222/json/list
    ```

3. <span data-ttu-id="c96b2-119">连接到所需页面的列表，以 `webSocketDebuggerUrl` 发出进一步 [的协议命令](0.2/domains/index.md) 并通过 devtools 套接字服务器接收事件消息。</span><span class="sxs-lookup"><span data-stu-id="c96b2-119">Connect to the listed `webSocketDebuggerUrl` of the desired page to issue further [protocol commands](0.2/domains/index.md) and receive event messages through the devtools socket server.</span></span>

## <span data-ttu-id="c96b2-120">状态和反馈</span><span class="sxs-lookup"><span data-stu-id="c96b2-120">Status and feedback</span></span>

<span data-ttu-id="c96b2-121">除[版本 0.1](0.2/index.md)中引入的核心脚本调试功能外，DevTools 协议版本[0.2](0.1/index.md)还提供了样式和布局的新域 (只读) 调试和控制台 API。</span><span class="sxs-lookup"><span data-stu-id="c96b2-121">[Version 0.2](0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](0.1/index.md).</span></span> <span data-ttu-id="c96b2-122">在 Microsoft Edge DevTools UI 中，这转换为元素、[\*\*\*\*](../devtools-guide/elements.md)控制台和[\*\*\*\*](../devtools-guide/console.md)调试器面板[**中提供**](../devtools-guide/debugger.md)的功能。</span><span class="sxs-lookup"><span data-stu-id="c96b2-122">In the Microsoft Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>

<span data-ttu-id="c96b2-123">感谢尝试 Edge DevTools 协议！</span><span class="sxs-lookup"><span data-stu-id="c96b2-123">Thanks for trying the Edge DevTools Protocol!</span></span> <span data-ttu-id="c96b2-124">我们喜欢在：</span><span class="sxs-lookup"><span data-stu-id="c96b2-124">We'd love to hear your feedback at:</span></span>

 - <span data-ttu-id="c96b2-125">[**Microsoft Edge 开发人员 UserVoice：DevTools**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475)功能想法和请求</span><span class="sxs-lookup"><span data-stu-id="c96b2-125">[**Microsoft Edge Developer UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475): DevTools feature ideas and requests</span></span>

 - <span data-ttu-id="c96b2-126">[**EdgeHTML 问题跟踪程序**](https://developer.microsoft.com/microsoft-edge/platform/issues/)：协议、DevTools 和 EdgeHTML 平台 Bug 和问题</span><span class="sxs-lookup"><span data-stu-id="c96b2-126">[**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): Protocol, DevTools, and EdgeHTML platform bugs and issues</span></span>

 - <span data-ttu-id="c96b2-127">[**Microsoft Edge DevTools 反馈中心**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344)：通过反馈中心应用的协议和 DevTools 问题和建议</span><span class="sxs-lookup"><span data-stu-id="c96b2-127">[**Microsoft Edge DevTools Feedback Hub**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): Protocol and DevTools problems and suggestions through the Feedback Hub app</span></span>

## <span data-ttu-id="c96b2-128">常见问题</span><span class="sxs-lookup"><span data-stu-id="c96b2-128">FAQ</span></span>

#### <span data-ttu-id="c96b2-129">多个客户端能否连接到同一个 DevTools 服务器？</span><span class="sxs-lookup"><span data-stu-id="c96b2-129">Can multiple clients connect to the same DevTools Server?</span></span>
<span data-ttu-id="c96b2-130">否，在客户端调试时不能同时进行。</span><span class="sxs-lookup"><span data-stu-id="c96b2-130">No, not simultaneously when the clients are debugging.</span></span> <span data-ttu-id="c96b2-131">最后一个要连接的客户端将启动上一个客户端。</span><span class="sxs-lookup"><span data-stu-id="c96b2-131">The last client to connect will kick off the previous one.</span></span> <span data-ttu-id="c96b2-132">在将来支持其他工具时，这些工具可能支持同时进行客户端连接。</span><span class="sxs-lookup"><span data-stu-id="c96b2-132">In the future when additional tools are supported, those will likely support simultaneous client connections.</span></span>

#### <span data-ttu-id="c96b2-133">我是否必须使用 9222 作为 DevTools 服务器端口？</span><span class="sxs-lookup"><span data-stu-id="c96b2-133">Do I have to use 9222 as the DevTools Server port?</span></span>
<span data-ttu-id="c96b2-134">否。</span><span class="sxs-lookup"><span data-stu-id="c96b2-134">No.</span></span> <span data-ttu-id="c96b2-135">您可以指定任何端口，但请务必选取尚未使用的端口。</span><span class="sxs-lookup"><span data-stu-id="c96b2-135">You can specify any port, though be sure to pick one that isn't already in use.</span></span> <span data-ttu-id="c96b2-136">用于远程调试的端口 9222 按惯例使用。</span><span class="sxs-lookup"><span data-stu-id="c96b2-136">Port 9222 for remote debugging is used by convention.</span></span>

#### <span data-ttu-id="c96b2-137">如何将我的自定义工具客户端连接到运行 DevTools (EdgeHTML) Microsoft Edge？</span><span class="sxs-lookup"><span data-stu-id="c96b2-137">How do I connect my custom tooling client to Microsoft Edge (EdgeHTML) running the DevTools Server?</span></span>
<span data-ttu-id="c96b2-138">请参阅 [*使用上述协议*](#using-the-protocol) 说明连接到本地计算机上 (运行的 EdgeHTML) Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c96b2-138">See [*Using the protocol*](#using-the-protocol) instructions above for attaching to Microsoft Edge (EdgeHTML) running on the local machine.</span></span> <span data-ttu-id="c96b2-139">如果你希望支持远程调试，则需要设计一个用户工作流，以在客户端上安装主机的 SSL 证书，例如，在 [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) 使用安装对话框时。</span><span class="sxs-lookup"><span data-stu-id="c96b2-139">If you're looking to support remote debugging, you'll need to devise a user workflow for installing the host machine's SSL certificate on the client, for example with an install dialog as [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) uses.</span></span>

#### <span data-ttu-id="c96b2-140">如果我使用 Edge DevTools 进行远程调试，是否需要使用 *--devtools-server-port* cmd 线路交换机启动主机浏览器进程？</span><span class="sxs-lookup"><span data-stu-id="c96b2-140">If I'm remote debugging using Edge DevTools, do I need to start the host browser process with *--devtools-server-port* cmd line switch?</span></span> 
<span data-ttu-id="c96b2-141">否。</span><span class="sxs-lookup"><span data-stu-id="c96b2-141">No.</span></span> <span data-ttu-id="c96b2-142">如果使用 Microsoft Edge [DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)设置远程调试，则启动 Edge 时不需要 `--devtools-server-port` 命令行开关。</span><span class="sxs-lookup"><span data-stu-id="c96b2-142">If you're setting up [remote debugging using Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview), the `--devtools-server-port` command line switch is not necessary for starting Edge.</span></span> <span data-ttu-id="c96b2-143">在这种情况下，Windows *Device Portal* 代表浏览器托管 DevTools Server。</span><span class="sxs-lookup"><span data-stu-id="c96b2-143">In this case, Windows *Device Portal* is hosting the DevTools Server on behalf of the browser.</span></span>

#### <span data-ttu-id="c96b2-144">我能否使用边缘开发人员工具协议远程调试WWAHost.exe或 Webview 进程？</span><span class="sxs-lookup"><span data-stu-id="c96b2-144">Can I use the Edge DevTools Protocol to remotely debug a WWAHost.exe or webview process?</span></span>
<span data-ttu-id="c96b2-145">边缘 DevTools 协议当前仅支持浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="c96b2-145">The Edge DevTools Protocol currently supports only browser tabs.</span></span> <span data-ttu-id="c96b2-146">WWAHost.exe webview 进程不受支持。</span><span class="sxs-lookup"><span data-stu-id="c96b2-146">WWAHost.exe and webview processes are not supported.</span></span>
