---
description: 更新到 Microsoft Edge DevTools 协议
title: Microsoft Edge DevTools 协议更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 15b13e2b93d1dbd013a82ea52b643071fa5b6f7e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232504"
---
# <span data-ttu-id="c962b-103">Microsoft Edge (Chromium) DevTools 协议概述</span><span class="sxs-lookup"><span data-stu-id="c962b-103">Microsoft Edge (Chromium) DevTools Protocol overview</span></span>  

<span data-ttu-id="c962b-104">随着 Microsoft Edge 的基础 Web 平台向 Chromium 的转移 [，Microsoft Edge (EdgeHTML) DevTools 协议将不会](../edgehtml/devtools-protocol/index.md) 接收任何进一步的更新。</span><span class="sxs-lookup"><span data-stu-id="c962b-104">With the shift in the underlying web platform of Microsoft Edge to Chromium, the [Microsoft Edge (EdgeHTML) DevTools Protocol](../edgehtml/devtools-protocol/index.md) will not be receiving any further updates.</span></span>  <span data-ttu-id="c962b-105">Microsoft Edge \ (Chromium\) DevTools 协议将匹配 Chrome DevTools 协议的 API。</span><span class="sxs-lookup"><span data-stu-id="c962b-105">The Microsoft Edge \(Chromium\) DevTools Protocol will match the APIs of the Chrome DevTools Protocol going forward.</span></span>  

<span data-ttu-id="c962b-106">可以通过引用 [Chrome DevTools](https://chromedevtools.github.io/devtools-protocol/tot/)协议查看器找到有关这些域和方法的文档。</span><span class="sxs-lookup"><span data-stu-id="c962b-106">You can find documentation on those domains and methods by referring to the [Chrome DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/tot/).</span></span>  

> [!NOTE]
> <span data-ttu-id="c962b-107">`ms` [Microsoft Edge \ (EdgeHTML) DevTools](../edgehtml/devtools-protocol/index.md)协议中前缀的任何方法在 Microsoft Edge \ (Chromium\) DevTools 协议中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="c962b-107">Any methods that were prefixed with `ms` in the [Microsoft Edge (EdgeHTML) DevTools Protocol](../edgehtml/devtools-protocol/index.md) are no longer supported in the Microsoft Edge \(Chromium\) DevTools Protocol.</span></span>  

## <span data-ttu-id="c962b-108">使用 DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="c962b-108">Using the DevTools Protocol</span></span>  

<span data-ttu-id="c962b-109">下面将了解如何将自定义工具客户端附加到 Microsoft Edge \ (Chromium\) 中的 DevTools Server。</span><span class="sxs-lookup"><span data-stu-id="c962b-109">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge \(Chromium\).</span></span>  

1.  <span data-ttu-id="c962b-110">确保关闭 Microsoft Edge \ (Chromium\) 实例。</span><span class="sxs-lookup"><span data-stu-id="c962b-110">Ensure all instances of Microsoft Edge \(Chromium\) are closed.</span></span>  
1.  <span data-ttu-id="c962b-111">使用远程调试 (启动 Microsoft Edge \) Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="c962b-111">Launch Microsoft Edge \(Chromium\) with the remote debugging port:.</span></span> 
    
    ```shell
    msedge.exe --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="c962b-112">或者，如果需要，可以使用不同的用户配置文件启动单独的 Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="c962b-112">Optionally, you can start a separate instance of Edge using a distinct user profile if desired.</span></span>  
    
    ```shell
    msedge.exe --user-data-dir=<some directory>
    ```  
    
1.  <span data-ttu-id="c962b-113">接下来，使用 HTTP `list` 终结点获取可附加页面目标的列表。</span><span class="sxs-lookup"><span data-stu-id="c962b-113">Next, use the HTTP `list` endpoint to get a list of attachable page targets.</span></span>  
    
    ```http
    http://localhost:9222/json/list
    ```  
    
1.  <span data-ttu-id="c962b-114">最后，通过 DevTools Web 套接字服务器连接到所需目标并发出命令 `webSocketDebuggerUrl` /订阅事件消息。</span><span class="sxs-lookup"><span data-stu-id="c962b-114">Finally, connect to the `webSocketDebuggerUrl` of the desired target and issue commands/subscribe to event messages through the DevTools web socket server.</span></span>  

## <span data-ttu-id="c962b-115">DevTools 协议 HTTP 终结点</span><span class="sxs-lookup"><span data-stu-id="c962b-115">DevTools Protocol HTTP Endpoints</span></span>  

<span data-ttu-id="c962b-116">Microsoft Edge \ (Chromium\) DevTools 协议支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="c962b-116">The Microsoft Edge \(Chromium\) DevTools Protocol supports the following HTTP endpoints.</span></span>  

## <span data-ttu-id="c962b-117">/json/version</span><span class="sxs-lookup"><span data-stu-id="c962b-117">/json/version</span></span>  

<span data-ttu-id="c962b-118">提供有关主机浏览器及其支持的 DevTools 协议版本的信息。</span><span class="sxs-lookup"><span data-stu-id="c962b-118">Provides information on the browser of the host machine and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="c962b-119">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-119">Parameters</span></span>**  

**<span data-ttu-id="c962b-120">无</span><span class="sxs-lookup"><span data-stu-id="c962b-120">None</span></span>**  

**<span data-ttu-id="c962b-121">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-121">Return object</span></span>**  

```json
{
   "Browser": "Edg/75.0.115.0",
   "Protocol-Version": "1.3",
   "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.115.0",
   "V8-Version": "7.5.98",
   "WebKit-Version": "537.36 (@68a98f73c7d0f766fb5a013ea7f8dbb41089bc1b)",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/browser/a9d0e8cf-476a-4a89-bba9-0fc27ce691cd"
}
```  

## <span data-ttu-id="c962b-122">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="c962b-122">/json/protocol</span></span>  

<span data-ttu-id="c962b-123">提供序列化为 JSON 的整个协议 API 图面。</span><span class="sxs-lookup"><span data-stu-id="c962b-123">Provides the entire protocol API surface serialized as JSON.</span></span>  

**<span data-ttu-id="c962b-124">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-124">Parameters</span></span>**  

**<span data-ttu-id="c962b-125">无</span><span class="sxs-lookup"><span data-stu-id="c962b-125">None</span></span>**  

**<span data-ttu-id="c962b-126">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-126">Return object</span></span>**  

<span data-ttu-id="c962b-127">JSON 对象，该对象表示协议当前版本的可用 API 图面。</span><span class="sxs-lookup"><span data-stu-id="c962b-127">JSON object which represents the available API surface for current version of the protocol.</span></span>  

## <span data-ttu-id="c962b-128">/json/list</span><span class="sxs-lookup"><span data-stu-id="c962b-128">/json/list</span></span>  

<span data-ttu-id="c962b-129">提供用于调试的页面目标的候选列表。</span><span class="sxs-lookup"><span data-stu-id="c962b-129">Provides a candidate list of page targets for debugging.</span></span>  

**<span data-ttu-id="c962b-130">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-130">Parameters</span></span>**  

**<span data-ttu-id="c962b-131">无</span><span class="sxs-lookup"><span data-stu-id="c962b-131">None</span></span>**  

**<span data-ttu-id="c962b-132">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-132">Return object</span></span>**  

```json
[{
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, ...  ]
```  

## <span data-ttu-id="c962b-133">/json/close</span><span class="sxs-lookup"><span data-stu-id="c962b-133">/json/close</span></span>  

<span data-ttu-id="c962b-134">关闭目标进程 \ (例如，在 Microsoft Edge \ (Chromium\) 中，关闭页面选项卡\) 。</span><span class="sxs-lookup"><span data-stu-id="c962b-134">Closes down the target process \(for example, in Microsoft Edge \(Chromium\), closes the page tab\).</span></span>  

**<span data-ttu-id="c962b-135">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-135">Parameters</span></span>**  

<span data-ttu-id="c962b-136">目标 ID</span><span class="sxs-lookup"><span data-stu-id="c962b-136">Target ID</span></span>  

**<span data-ttu-id="c962b-137">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-137">Return object</span></span>**  

```
String(“Target is closing”)
```  

## <span data-ttu-id="c962b-138">Microsoft Edge 适用的远程工具 (Beta)</span><span class="sxs-lookup"><span data-stu-id="c962b-138">Remote Tools for Microsoft Edge (Beta)</span></span>  

<span data-ttu-id="c962b-139">现在，你可以从 Microsoft [Store ](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) 安装适用于 Microsoft Edge (Beta) [的远程工具](https://www.microsoft.com/store/apps/windows)。</span><span class="sxs-lookup"><span data-stu-id="c962b-139">You are now able to install the [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) from the [Microsoft Store](https://www.microsoft.com/store/apps/windows).</span></span>  <span data-ttu-id="c962b-140">此应用使你能够远程调试在开发 (Windows 10) 上运行的 Microsoft Edge 和 Chromium。</span><span class="sxs-lookup"><span data-stu-id="c962b-140">This app enables you to remotely debug Microsoft Edge (Chromium) running on a Windows 10 device from your development machine.</span></span>  

<span data-ttu-id="c962b-141">若要了解如何设置 Windows 10 设备，以及如何从开发计算机连接到该设备，请导航到"远程调试 [Windows 10](../devtools-guide-chromium/remote-debugging/windows.md)设备入门"。</span><span class="sxs-lookup"><span data-stu-id="c962b-141">To learn how to set up your Windows 10 device and connect to it from your development machine, navigate to [Get Started with Remote Debugging Windows 10 Devices](../devtools-guide-chromium/remote-debugging/windows.md).</span></span>  

<span data-ttu-id="c962b-142">适用于 [Microsoft Edge (Beta) ](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) 的远程工具使用与 [DevTools](../devtools-guide-chromium/index.md) 相同的 Microsoft Edge (Chromium) DevTools 协议，与在你要调试的 Windows 10 设备上运行的 Microsoft Edge 进行通信。</span><span class="sxs-lookup"><span data-stu-id="c962b-142">The [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) uses the same Microsoft Edge (Chromium) DevTools Protocol as the [DevTools](../devtools-guide-chromium/index.md) to communicate with Microsoft Edge running on the Windows 10 device you want to debug.</span></span>  <span data-ttu-id="c962b-143">每次调用协议之前，此应用程序 () `/msedge/` `pid` 进程 ID。</span><span class="sxs-lookup"><span data-stu-id="c962b-143">This app just prepends `/msedge/` and a process ID (`pid`) before each call to the protocol.</span></span>  <span data-ttu-id="c962b-144">它支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="c962b-144">It supports the following HTTP endpoints.</span></span>  

### <span data-ttu-id="c962b-145">/msedge/json/list</span><span class="sxs-lookup"><span data-stu-id="c962b-145">/msedge/json/list</span></span>  

<span data-ttu-id="c962b-146">提供所有进程 \ (候选列表，包括 `msedge.exe` [PBA](../progressive-web-apps-chromium/index.md) 和 Windows 10 设备上所有 Microsoft Edge\) 实例的所有选项卡进行调试。</span><span class="sxs-lookup"><span data-stu-id="c962b-146">Provides a candidate list of all `msedge.exe` processes \(including [PWAs](../progressive-web-apps-chromium/index.md) and all tabs in all instances of Microsoft Edge\) on the Windows 10 device for debugging.</span></span>  

**<span data-ttu-id="c962b-147">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-147">Parameters</span></span>**  

**<span data-ttu-id="c962b-148">无</span><span class="sxs-lookup"><span data-stu-id="c962b-148">None</span></span>**  

**<span data-ttu-id="c962b-149">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-149">Return object</span></span>**  

```json
[{
   "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "browserProcessId": 7264
}, ...  ]
```  

### <span data-ttu-id="c962b-150">/msedge/</span><span class="sxs-lookup"><span data-stu-id="c962b-150">/msedge/</span></span>  

<span data-ttu-id="c962b-151">在功能上等同于 [/msedge/json/list](#msedgejsonlist)。</span><span class="sxs-lookup"><span data-stu-id="c962b-151">Functionally equivalent to [/msedge/json/list](#msedgejsonlist).</span></span>  

### <span data-ttu-id="c962b-152">/msedge/[pid]/json/list</span><span class="sxs-lookup"><span data-stu-id="c962b-152">/msedge/[pid]/json/list</span></span>  

<span data-ttu-id="c962b-153">提供与提供的调试匹配的 Microsoft Edge 实例的候选页面 `[pid]` 目标列表。</span><span class="sxs-lookup"><span data-stu-id="c962b-153">Provides a candidate list of page targets for the Microsoft Edge instance that matches the provided `[pid]` for debugging.</span></span>  

**<span data-ttu-id="c962b-154">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-154">Parameters</span></span>**  

**<span data-ttu-id="c962b-155">无</span><span class="sxs-lookup"><span data-stu-id="c962b-155">None</span></span>**  

**<span data-ttu-id="c962b-156">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-156">Return object</span></span>**  

```json
[{
    "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB"
}, ...  ]
```  

### <span data-ttu-id="c962b-157">/msedge/[pid]/json/version</span><span class="sxs-lookup"><span data-stu-id="c962b-157">/msedge/[pid]/json/version</span></span>  

<span data-ttu-id="c962b-158">提供有关与提供的 Microsoft Edge 实例及其支持的 `[pid]` DevTools 协议版本匹配的信息。</span><span class="sxs-lookup"><span data-stu-id="c962b-158">Provides information about the Microsoft Edge instance that matches the provided `[pid]` and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="c962b-159">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-159">Parameters</span></span>**  

**<span data-ttu-id="c962b-160">无</span><span class="sxs-lookup"><span data-stu-id="c962b-160">None</span></span>**  

**<span data-ttu-id="c962b-161">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-161">Return object</span></span>**  

```json
{
    "Browser": "Edg/82.0.452.0",
    "Protocol-Version": "1.3",
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/82.0.4080.0 Safari/537.36 Edg/82.0.452.0",
    "V8-Version": "8.2.263",
    "WebKit-Version": "537.36 (@fe0232051787ca94ac8edfc0084c3488b7d9bdb2)",
    "webSocketDebuggerUrl": "172.17.75.195:80/msedge/7264/devtools/browser/7a67c8c4-138b-48e3-bfe0-cb7af34d559a"
}
```  

### <span data-ttu-id="c962b-162">/msedge/[pid]/json/protocol/</span><span class="sxs-lookup"><span data-stu-id="c962b-162">/msedge/[pid]/json/protocol/</span></span>  

<span data-ttu-id="c962b-163">为与提供的 Microsoft Edge 实例匹配，提供序列化为 JSON 的整个协议 API 图面 `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="c962b-163">Provides the entire protocol API surface serialized as JSON for the Microsoft Edge instance that matches the provided `[pid]`.</span></span>  

**<span data-ttu-id="c962b-164">参数</span><span class="sxs-lookup"><span data-stu-id="c962b-164">Parameters</span></span>**  

**<span data-ttu-id="c962b-165">无</span><span class="sxs-lookup"><span data-stu-id="c962b-165">None</span></span>**  

**<span data-ttu-id="c962b-166">Return 对象</span><span class="sxs-lookup"><span data-stu-id="c962b-166">Return object</span></span>**  

<span data-ttu-id="c962b-167">JSON 对象，表示与提供的 Microsoft Edge 实例使用的协议版本可用的 API `[pid]` 图面。</span><span class="sxs-lookup"><span data-stu-id="c962b-167">JSON object which represents the available API surface for the version of the protocol that the Microsoft Edge instance that matches the provided `[pid]` is using.</span></span>  
