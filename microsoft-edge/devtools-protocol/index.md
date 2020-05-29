---
description: 使用 Microsoft Edge DevTools 协议检查和调试 Microsoft Edge （EdgeHTML）浏览器。
title: Microsoft Edge DevTools 协议
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 8bef24c98dae284f2111f6a16fca4a6f27c89dc4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563391"
---
# <span data-ttu-id="15a1f-103">Microsoft Edge （EdgeHTML） DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="15a1f-103">Microsoft Edge (EdgeHTML) DevTools Protocol</span></span>

> [!NOTE]
> <span data-ttu-id="15a1f-104">Microsoft Edge （EdgeHTML） DevTools 协议仅适用于[2018 年4月更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)和更高版本的 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="15a1f-104">The Microsoft Edge (EdgeHTML) DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later builds.</span></span>

<span data-ttu-id="15a1f-105">开发人员工具可以使用**Microsoft edge （EdgeHTML） DevTools 协议**检查和调试 Microsoft Edge （EdgeHTML）浏览器。</span><span class="sxs-lookup"><span data-stu-id="15a1f-105">Developer tools can use the **Microsoft Edge (EdgeHTML) DevTools Protocol** to inspect and debug the Microsoft Edge (EdgeHTML) browser.</span></span> <span data-ttu-id="15a1f-106">它提供了一组方法和事件，这些方法和事件组织到 EdgeHTML 引擎规范的不同[域](0.2/domains/index.md)中。</span><span class="sxs-lookup"><span data-stu-id="15a1f-106">It provides a set of methods and events that are organized into different [Domains](0.2/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="15a1f-107">工具客户可以通过与由 Microsoft Edge （EdgeHTML）或 Windows Device Portal 托管的*DevTools 服务器*交换的 JSON web 套接字消息来调用这些方法并监视这些事件。</span><span class="sxs-lookup"><span data-stu-id="15a1f-107">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge (EdgeHTML) or the Windows Device Portal.</span></span> <span data-ttu-id="15a1f-108">Microsoft Edge （EdgeHTML） DevTools 使用此协议，从[Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)提供的独立 DevTools 客户端开始[远程调试](0.2/clients.md#microsoft-edge-devtools-preview)运行 microsoft Edge （EdgeHTML）的主机。</span><span class="sxs-lookup"><span data-stu-id="15a1f-108">Microsoft Edge (EdgeHTML) DevTools uses this protocol to enable [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge (EdgeHTML) from the standalone DevTools client available from the [Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj).</span></span>

<span data-ttu-id="15a1f-109">Microsoft Edge （EdgeHTML） DevTools 协议设计为与 Chrome DevTools 协议密切对齐（请参阅[W3C WICG For DevTools 协议](https://github.com/WICG/devtools-protocol/)），尽管此版本中有已知的互操作性差距。</span><span class="sxs-lookup"><span data-stu-id="15a1f-109">The Microsoft Edge (EdgeHTML) DevTools Protocol is designed to align closely with the Chrome DevTools Protocol (see the [W3C WICG for DevTools Protocols](https://github.com/WICG/devtools-protocol/)), though there are known interoperability gaps in this release.</span></span>

## <span data-ttu-id="15a1f-110">使用协议</span><span class="sxs-lookup"><span data-stu-id="15a1f-110">Using the protocol</span></span>

<span data-ttu-id="15a1f-111">下面介绍了如何将自定义工具客户端附加到 Microsoft Edge 中的 DevTools 服务器（EdgeHTML）。</span><span class="sxs-lookup"><span data-stu-id="15a1f-111">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge (EdgeHTML).</span></span> <span data-ttu-id="15a1f-112">如果您使用的是 Microsoft Edge DevTools 作为客户，请参阅[远程调试](0.2/clients.md#microsoft-edge-devtools-preview)说明。</span><span class="sxs-lookup"><span data-stu-id="15a1f-112">See the [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) instructions if you're using Microsoft Edge DevTools as your client.</span></span>

1. <span data-ttu-id="15a1f-113">在远程调试端口打开的情况下启动 Microsoft Edge （EdgeHTML），指定要打开的 URL。</span><span class="sxs-lookup"><span data-stu-id="15a1f-113">Launch Microsoft Edge (EdgeHTML) with the remote debugging port open, specifying the URL you wish to open.</span></span> <span data-ttu-id="15a1f-114">例如：</span><span class="sxs-lookup"><span data-stu-id="15a1f-114">For example:</span></span>

    ```
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    <span data-ttu-id="15a1f-115">如果 Edge 已启动，则 URL 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="15a1f-115">If Edge is already launched, the URL parameter is optional.</span></span> <span data-ttu-id="15a1f-116">浏览器地址栏旁边将显示一个按钮，指示**开发人员工具服务器**已启动：</span><span class="sxs-lookup"><span data-stu-id="15a1f-116">A button will appear next to the browser address bar to indicate the **Developer tools server** has started:</span></span>

    ![开发人员工具服务器](media/developer-tools-server.png) 

2. <span data-ttu-id="15a1f-118">使用此[HTTP 终结点](0.2/http.md)获取可附加的页面目标的列表：</span><span class="sxs-lookup"><span data-stu-id="15a1f-118">Use this [HTTP endpoint](0.2/http.md) to get a list of attachable page targets:</span></span>

    ```
    http://localhost:9222/json/list
    ```

3. <span data-ttu-id="15a1f-119">连接到所需页面的列出， `webSocketDebuggerUrl` 通过 devtools 套接字服务器发出更多[协议命令](0.2/domains/index.md)并接收事件消息。</span><span class="sxs-lookup"><span data-stu-id="15a1f-119">Connect to the listed `webSocketDebuggerUrl` of the desired page to issue further [protocol commands](0.2/domains/index.md) and receive event messages through the devtools socket server.</span></span>

## <span data-ttu-id="15a1f-120">状态和反馈</span><span class="sxs-lookup"><span data-stu-id="15a1f-120">Status and feedback</span></span>

<span data-ttu-id="15a1f-121">除了[版本 0.1](0.1/index.md)中引入的核心脚本调试功能之外，DevTools 协议的[版本 0.2](0.2/index.md)还提供了新域用于样式和布局（只读）调试和控制台 api。</span><span class="sxs-lookup"><span data-stu-id="15a1f-121">[Version 0.2](0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](0.1/index.md).</span></span> <span data-ttu-id="15a1f-122">在 Microsoft Edge DevTools UI 中，这将转换为[**元素**](../devtools-guide/elements.md)、[**控制台**](../devtools-guide/console.md)和[**调试器**](../devtools-guide/debugger.md)面板中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="15a1f-122">In the Microsoft Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>

<span data-ttu-id="15a1f-123">感谢你试用 Edge DevTools 协议！</span><span class="sxs-lookup"><span data-stu-id="15a1f-123">Thanks for trying the Edge DevTools Protocol!</span></span> <span data-ttu-id="15a1f-124">我们乐意在以下网址听到您的反馈意见：</span><span class="sxs-lookup"><span data-stu-id="15a1f-124">We'd love to hear your feedback at:</span></span>

 - <span data-ttu-id="15a1f-125">[**Microsoft Edge 开发人员 UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475)： DevTools 功能创意和请求</span><span class="sxs-lookup"><span data-stu-id="15a1f-125">[**Microsoft Edge Developer UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475): DevTools feature ideas and requests</span></span>

 - <span data-ttu-id="15a1f-126">[**EdgeHTML 问题跟踪**](https://developer.microsoft.com/microsoft-edge/platform/issues/)器：协议、DevTools 和 EdgeHTML 平台错误和问题</span><span class="sxs-lookup"><span data-stu-id="15a1f-126">[**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): Protocol, DevTools, and EdgeHTML platform bugs and issues</span></span>

 - <span data-ttu-id="15a1f-127">[**Microsoft Edge DevTools 反馈中心**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344)：通过 "反馈中心" 应用的协议和 DevTools 问题和建议</span><span class="sxs-lookup"><span data-stu-id="15a1f-127">[**Microsoft Edge DevTools Feedback Hub**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): Protocol and DevTools problems and suggestions through the Feedback Hub app</span></span>

## <span data-ttu-id="15a1f-128">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="15a1f-128">FAQ</span></span>

#### <span data-ttu-id="15a1f-129">多个客户端是否可以连接到同一 DevTools 服务器？</span><span class="sxs-lookup"><span data-stu-id="15a1f-129">Can multiple clients connect to the same DevTools Server?</span></span>
<span data-ttu-id="15a1f-130">否，客户端在调试时不会同时进行。</span><span class="sxs-lookup"><span data-stu-id="15a1f-130">No, not simultaneously when the clients are debugging.</span></span> <span data-ttu-id="15a1f-131">最后一个要连接的客户端将启动以前的客户端。</span><span class="sxs-lookup"><span data-stu-id="15a1f-131">The last client to connect will kick off the previous one.</span></span> <span data-ttu-id="15a1f-132">将来，当支持其他工具时，这些工具可能支持同时进行的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="15a1f-132">In the future when additional tools are supported, those will likely support simultaneous client connections.</span></span>

#### <span data-ttu-id="15a1f-133">是否必须将9222用作 DevTools 服务器端口？</span><span class="sxs-lookup"><span data-stu-id="15a1f-133">Do I have to use 9222 as the DevTools Server port?</span></span>
<span data-ttu-id="15a1f-134">否。</span><span class="sxs-lookup"><span data-stu-id="15a1f-134">No.</span></span> <span data-ttu-id="15a1f-135">你可以指定任何端口，但确保选择一个尚未使用的端口。</span><span class="sxs-lookup"><span data-stu-id="15a1f-135">You can specify any port, though be sure to pick one that isn't already in use.</span></span> <span data-ttu-id="15a1f-136">约定使用端口9222进行远程调试。</span><span class="sxs-lookup"><span data-stu-id="15a1f-136">Port 9222 for remote debugging is used by convention.</span></span>

#### <span data-ttu-id="15a1f-137">如何将自定义工具客户端连接到运行 DevTools 服务器的 Microsoft Edge （EdgeHTML）？</span><span class="sxs-lookup"><span data-stu-id="15a1f-137">How do I connect my custom tooling client to Microsoft Edge (EdgeHTML) running the DevTools Server?</span></span>
<span data-ttu-id="15a1f-138">有关附加到在本地计算机上运行的 Microsoft Edge （EdgeHTML）的协议说明，请参阅[*使用上述协议*](#using-the-protocol)说明。</span><span class="sxs-lookup"><span data-stu-id="15a1f-138">See [*Using the protocol*](#using-the-protocol) instructions above for attaching to Microsoft Edge (EdgeHTML) running on the local machine.</span></span> <span data-ttu-id="15a1f-139">如果你希望支持远程调试，你将需要设计用户工作流，以便在客户端上安装主机的 SSL 证书，例如安装对话框是[Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)使用。</span><span class="sxs-lookup"><span data-stu-id="15a1f-139">If you're looking to support remote debugging, you'll need to devise a user workflow for installing the host machine's SSL certificate on the client, for example with an install dialog as [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) uses.</span></span>

#### <span data-ttu-id="15a1f-140">如果我是使用 Edge DevTools 进行远程调试，是否需要使用 *--DevTools 服务器端口*命令行开关启动主浏览器进程？</span><span class="sxs-lookup"><span data-stu-id="15a1f-140">If I'm remote debugging using Edge DevTools, do I need to start the host browser process with *--devtools-server-port* cmd line switch?</span></span> 
<span data-ttu-id="15a1f-141">否。</span><span class="sxs-lookup"><span data-stu-id="15a1f-141">No.</span></span> <span data-ttu-id="15a1f-142">如果你正在[使用 Microsoft Edge DevTools Preview 设置远程调试](./0.2/clients.md#microsoft-edge-devtools-preview)，则 `--devtools-server-port` 命令行开关不是开始边缘所必需的。</span><span class="sxs-lookup"><span data-stu-id="15a1f-142">If you're setting up [remote debugging using Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview), the `--devtools-server-port` command line switch is not necessary for starting Edge.</span></span> <span data-ttu-id="15a1f-143">在这种情况下，Windows *Device Portal*将代表浏览器托管 DevTools 服务器。</span><span class="sxs-lookup"><span data-stu-id="15a1f-143">In this case, Windows *Device Portal* is hosting the DevTools Server on behalf of the browser.</span></span>

#### <span data-ttu-id="15a1f-144">是否可以使用 Edge DevTools 协议远程调试 WWAHost 或 web 视图过程？</span><span class="sxs-lookup"><span data-stu-id="15a1f-144">Can I use the Edge DevTools Protocol to remotely debug a WWAHost.exe or webview process?</span></span>
<span data-ttu-id="15a1f-145">Edge DevTools 协议当前仅支持浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="15a1f-145">The Edge DevTools Protocol currently supports only browser tabs.</span></span> <span data-ttu-id="15a1f-146">不支持 WWAHost 和 web 视图进程。</span><span class="sxs-lookup"><span data-stu-id="15a1f-146">WWAHost.exe and webview processes are not supported.</span></span>
