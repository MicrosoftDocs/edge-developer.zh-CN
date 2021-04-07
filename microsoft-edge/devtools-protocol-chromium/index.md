---
description: 更新到 Microsoft Edge DevTools 协议
title: Microsoft Edge DevTools 协议更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: de7d6c39c09ba321f21b34e6e461ec030f09f6ad
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480158"
---
# <a name="microsoft-edge-chromium-devtools-protocol-overview"></a><span data-ttu-id="465e2-103">Microsoft Edge (Chromium) DevTools 协议概述</span><span class="sxs-lookup"><span data-stu-id="465e2-103">Microsoft Edge (Chromium) DevTools Protocol overview</span></span>  

<span data-ttu-id="465e2-104">随着 Microsoft Edge 的基础 Web 平台向 Chromium 的转移 [，Microsoft Edge (EdgeHTML) DevTools 协议](/archive/microsoft-edge/legacy/developer/devtools-protocol/index) 将不会接收任何进一步的更新。</span><span class="sxs-lookup"><span data-stu-id="465e2-104">With the shift in the underlying web platform of Microsoft Edge to Chromium, the [Microsoft Edge (EdgeHTML) DevTools Protocol](/archive/microsoft-edge/legacy/developer/devtools-protocol/index) will not be receiving any further updates.</span></span>  <span data-ttu-id="465e2-105">Microsoft Edge \ (Chromium\) DevTools 协议将匹配 Chrome DevTools 协议的 API。</span><span class="sxs-lookup"><span data-stu-id="465e2-105">The Microsoft Edge \(Chromium\) DevTools Protocol will match the APIs of the Chrome DevTools Protocol going forward.</span></span>  

<span data-ttu-id="465e2-106">可以通过引用 [Chrome DevTools](https://chromedevtools.github.io/devtools-protocol/tot)协议查看器来查找有关这些域和方法的文档。</span><span class="sxs-lookup"><span data-stu-id="465e2-106">You can find documentation on those domains and methods by referring to the [Chrome DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/tot).</span></span>  

> [!NOTE]
> <span data-ttu-id="465e2-107">`ms`Microsoft Edge \ (Chromium\) [DevTools 协议不再支持在 Microsoft Edge (EdgeHTML) DevTools](/archive/microsoft-edge/legacy/developer/devtools-protocol/index)协议中作为前缀的任何方法。</span><span class="sxs-lookup"><span data-stu-id="465e2-107">Any methods that were prefixed with `ms` in the [Microsoft Edge (EdgeHTML) DevTools Protocol](/archive/microsoft-edge/legacy/developer/devtools-protocol/index) are no longer supported in the Microsoft Edge \(Chromium\) DevTools Protocol.</span></span>  

## <a name="using-the-devtools-protocol"></a><span data-ttu-id="465e2-108">使用 DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="465e2-108">Using the DevTools Protocol</span></span>  

<span data-ttu-id="465e2-109">下面将了解如何将自定义工具客户端附加到 Microsoft Edge \ (Chromium\) 中的 DevTools 服务器。</span><span class="sxs-lookup"><span data-stu-id="465e2-109">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge \(Chromium\).</span></span>  

1.  <span data-ttu-id="465e2-110">确保关闭 Microsoft Edge \ (Chromium\) 实例。</span><span class="sxs-lookup"><span data-stu-id="465e2-110">Ensure all instances of Microsoft Edge \(Chromium\) are closed.</span></span>  
1.  <span data-ttu-id="465e2-111">使用远程调试 (启动 Microsoft Edge \) Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="465e2-111">Launch Microsoft Edge \(Chromium\) with the remote debugging port:.</span></span> 
    
    ```shell
    msedge.exe --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="465e2-112">（可选）如果需要，可以使用不同的用户配置文件启动单独的 Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="465e2-112">Optionally, you can start a separate instance of Edge using a distinct user profile if desired.</span></span>  
    
    ```shell
    msedge.exe --user-data-dir=<some directory>
    ```  
    
1.  <span data-ttu-id="465e2-113">接下来，使用 HTTP `list` 终结点获取可附加页面目标的列表。</span><span class="sxs-lookup"><span data-stu-id="465e2-113">Next, use the HTTP `list` endpoint to get a list of attachable page targets.</span></span>  
    
    ```http
    http://localhost:9222/json/list
    ```  
    
1.  <span data-ttu-id="465e2-114">最后，通过 DevTools Web 套接字服务器连接到所需目标的 并发出命令 `webSocketDebuggerUrl` /订阅事件消息。</span><span class="sxs-lookup"><span data-stu-id="465e2-114">Finally, connect to the `webSocketDebuggerUrl` of the desired target and issue commands/subscribe to event messages through the DevTools web socket server.</span></span>  

## <a name="devtools-protocol-http-endpoints"></a><span data-ttu-id="465e2-115">DevTools 协议 HTTP 终结点</span><span class="sxs-lookup"><span data-stu-id="465e2-115">DevTools Protocol HTTP Endpoints</span></span>  

<span data-ttu-id="465e2-116">Microsoft Edge \ (Chromium\) DevTools 协议支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="465e2-116">The Microsoft Edge \(Chromium\) DevTools Protocol supports the following HTTP endpoints.</span></span>  

## <a name="jsonversion"></a><span data-ttu-id="465e2-117">/json/version</span><span class="sxs-lookup"><span data-stu-id="465e2-117">/json/version</span></span>  

<span data-ttu-id="465e2-118">提供有关主机的浏览器及其支持的 DevTools 协议的哪个版本的信息。</span><span class="sxs-lookup"><span data-stu-id="465e2-118">Provides information on the browser of the host machine and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="465e2-119">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-119">Parameters</span></span>**  

**<span data-ttu-id="465e2-120">无</span><span class="sxs-lookup"><span data-stu-id="465e2-120">None</span></span>**  

**<span data-ttu-id="465e2-121">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-121">Return object</span></span>**  

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

## <a name="jsonprotocol"></a><span data-ttu-id="465e2-122">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="465e2-122">/json/protocol</span></span>  

<span data-ttu-id="465e2-123">提供序列化为 JSON 的整个协议 API 图面。</span><span class="sxs-lookup"><span data-stu-id="465e2-123">Provides the entire protocol API surface serialized as JSON.</span></span>  

**<span data-ttu-id="465e2-124">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-124">Parameters</span></span>**  

**<span data-ttu-id="465e2-125">无</span><span class="sxs-lookup"><span data-stu-id="465e2-125">None</span></span>**  

**<span data-ttu-id="465e2-126">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-126">Return object</span></span>**  

<span data-ttu-id="465e2-127">表示协议当前版本的可用 API 图面的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="465e2-127">JSON object which represents the available API surface for current version of the protocol.</span></span>  

## <a name="jsonlist"></a><span data-ttu-id="465e2-128">/json/list</span><span class="sxs-lookup"><span data-stu-id="465e2-128">/json/list</span></span>  

<span data-ttu-id="465e2-129">提供用于调试的页面目标的候选列表。</span><span class="sxs-lookup"><span data-stu-id="465e2-129">Provides a candidate list of page targets for debugging.</span></span>  

**<span data-ttu-id="465e2-130">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-130">Parameters</span></span>**  

**<span data-ttu-id="465e2-131">无</span><span class="sxs-lookup"><span data-stu-id="465e2-131">None</span></span>**  

**<span data-ttu-id="465e2-132">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-132">Return object</span></span>**  

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

## <a name="jsonclose"></a><span data-ttu-id="465e2-133">/json/close</span><span class="sxs-lookup"><span data-stu-id="465e2-133">/json/close</span></span>  

<span data-ttu-id="465e2-134">关闭目标进程 \ (例如，在 Microsoft Edge \ (Chromium\) 中，关闭页面选项卡\) 。</span><span class="sxs-lookup"><span data-stu-id="465e2-134">Closes down the target process \(for example, in Microsoft Edge \(Chromium\), closes the page tab\).</span></span>  

**<span data-ttu-id="465e2-135">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-135">Parameters</span></span>**  

<span data-ttu-id="465e2-136">目标 ID</span><span class="sxs-lookup"><span data-stu-id="465e2-136">Target ID</span></span>  

**<span data-ttu-id="465e2-137">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-137">Return object</span></span>**  

```
String(“Target is closing”)
```  

## <a name="remote-tools-for-microsoft-edge-beta"></a><span data-ttu-id="465e2-138">Microsoft Edge 适用的远程工具 (Beta)</span><span class="sxs-lookup"><span data-stu-id="465e2-138">Remote Tools for Microsoft Edge (Beta)</span></span>  

<span data-ttu-id="465e2-139">现在，你可以从 Microsoft Store 安装[适用于 Microsoft Edge (Beta) ](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)[远程工具](https://www.microsoft.com/store/apps/windows)。</span><span class="sxs-lookup"><span data-stu-id="465e2-139">You are now able to install the [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) from the [Microsoft Store](https://www.microsoft.com/store/apps/windows).</span></span>  <span data-ttu-id="465e2-140">此应用使你能够远程调试在开发 (Windows 10) 上运行的 Microsoft Edge 和 Chromium。</span><span class="sxs-lookup"><span data-stu-id="465e2-140">This app enables you to remotely debug Microsoft Edge (Chromium) running on a Windows 10 device from your development machine.</span></span>  

<span data-ttu-id="465e2-141">若要了解如何设置 Windows 10 设备，以及如何从开发计算机连接到该设备，请导航到远程调试 [Windows 10](../devtools-guide-chromium/remote-debugging/windows.md)设备入门。</span><span class="sxs-lookup"><span data-stu-id="465e2-141">To learn how to set up your Windows 10 device and connect to it from your development machine, navigate to [Get Started with Remote Debugging Windows 10 Devices](../devtools-guide-chromium/remote-debugging/windows.md).</span></span>  

<span data-ttu-id="465e2-142">适用于 [Microsoft Edge (Beta) ](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) 的远程工具使用与 [DevTools](../devtools-guide-chromium/index.md) 相同的 Microsoft Edge (Chromium) DevTools 协议与在你要调试的 Windows 10 设备上运行的 Microsoft Edge 进行通信。</span><span class="sxs-lookup"><span data-stu-id="465e2-142">The [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) uses the same Microsoft Edge (Chromium) DevTools Protocol as the [DevTools](../devtools-guide-chromium/index.md) to communicate with Microsoft Edge running on the Windows 10 device you want to debug.</span></span>  <span data-ttu-id="465e2-143">每次调用协议之前，此应用程序只是预先 () `/msedge/` `pid` 进程 ID。</span><span class="sxs-lookup"><span data-stu-id="465e2-143">This app just prepends `/msedge/` and a process ID (`pid`) before each call to the protocol.</span></span>  <span data-ttu-id="465e2-144">它支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="465e2-144">It supports the following HTTP endpoints.</span></span>  

### <a name="msedgejsonlist"></a><span data-ttu-id="465e2-145">/msedge/json/list</span><span class="sxs-lookup"><span data-stu-id="465e2-145">/msedge/json/list</span></span>  

<span data-ttu-id="465e2-146">提供所有进程 \ (的候选列表，包括 `msedge.exe` [PBA](../progressive-web-apps-chromium/index.md) 和 Windows 10 设备上 Microsoft Edge\) 的所有实例的所有选项卡进行调试。</span><span class="sxs-lookup"><span data-stu-id="465e2-146">Provides a candidate list of all `msedge.exe` processes \(including [PWAs](../progressive-web-apps-chromium/index.md) and all tabs in all instances of Microsoft Edge\) on the Windows 10 device for debugging.</span></span>  

**<span data-ttu-id="465e2-147">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-147">Parameters</span></span>**  

**<span data-ttu-id="465e2-148">无</span><span class="sxs-lookup"><span data-stu-id="465e2-148">None</span></span>**  

**<span data-ttu-id="465e2-149">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-149">Return object</span></span>**  

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

### <a name="msedge"></a><span data-ttu-id="465e2-150">/msedge/</span><span class="sxs-lookup"><span data-stu-id="465e2-150">/msedge/</span></span>  

<span data-ttu-id="465e2-151">在功能上等同于 [/msedge/json/list](#msedgejsonlist)。</span><span class="sxs-lookup"><span data-stu-id="465e2-151">Functionally equivalent to [/msedge/json/list](#msedgejsonlist).</span></span>  

### <a name="msedgepidjsonlist"></a><span data-ttu-id="465e2-152">/msedge/[pid]/json/list</span><span class="sxs-lookup"><span data-stu-id="465e2-152">/msedge/[pid]/json/list</span></span>  

<span data-ttu-id="465e2-153">提供与提供的调试匹配的 Microsoft Edge 实例的候选页面 `[pid]` 目标列表。</span><span class="sxs-lookup"><span data-stu-id="465e2-153">Provides a candidate list of page targets for the Microsoft Edge instance that matches the provided `[pid]` for debugging.</span></span>  

**<span data-ttu-id="465e2-154">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-154">Parameters</span></span>**  

**<span data-ttu-id="465e2-155">无</span><span class="sxs-lookup"><span data-stu-id="465e2-155">None</span></span>**  

**<span data-ttu-id="465e2-156">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-156">Return object</span></span>**  

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

### <a name="msedgepidjsonversion"></a><span data-ttu-id="465e2-157">/msedge/[pid]/json/version</span><span class="sxs-lookup"><span data-stu-id="465e2-157">/msedge/[pid]/json/version</span></span>  

<span data-ttu-id="465e2-158">提供有关与提供的 Microsoft Edge 实例以及它支持的 `[pid]` DevTools 协议版本匹配的信息。</span><span class="sxs-lookup"><span data-stu-id="465e2-158">Provides information about the Microsoft Edge instance that matches the provided `[pid]` and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="465e2-159">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-159">Parameters</span></span>**  

**<span data-ttu-id="465e2-160">无</span><span class="sxs-lookup"><span data-stu-id="465e2-160">None</span></span>**  

**<span data-ttu-id="465e2-161">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-161">Return object</span></span>**  

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

### <a name="msedgepidjsonprotocol"></a><span data-ttu-id="465e2-162">/msedge/[pid]/json/protocol/</span><span class="sxs-lookup"><span data-stu-id="465e2-162">/msedge/[pid]/json/protocol/</span></span>  

<span data-ttu-id="465e2-163">为与提供的 匹配 Microsoft Edge 实例提供序列化为 JSON 的整个协议 API 图面 `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="465e2-163">Provides the entire protocol API surface serialized as JSON for the Microsoft Edge instance that matches the provided `[pid]`.</span></span>  

**<span data-ttu-id="465e2-164">参数</span><span class="sxs-lookup"><span data-stu-id="465e2-164">Parameters</span></span>**  

**<span data-ttu-id="465e2-165">无</span><span class="sxs-lookup"><span data-stu-id="465e2-165">None</span></span>**  

**<span data-ttu-id="465e2-166">Return 对象</span><span class="sxs-lookup"><span data-stu-id="465e2-166">Return object</span></span>**  

<span data-ttu-id="465e2-167">JSON 对象，表示 Microsoft Edge 实例使用的协议版本的可用 API `[pid]` 图面。</span><span class="sxs-lookup"><span data-stu-id="465e2-167">JSON object which represents the available API surface for the version of the protocol that the Microsoft Edge instance that matches the provided `[pid]` is using.</span></span>  
