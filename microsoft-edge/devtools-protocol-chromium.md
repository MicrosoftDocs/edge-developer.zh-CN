---
description: 更新到 Microsoft Edge DevTools 协议
title: Microsoft Edge DevTools 协议更新
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/11/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: f1936a83f948dd17cc76139b7fd67fc73cd692d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563433"
---
# <span data-ttu-id="dd41b-103">Microsoft Edge （Chromium） DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="dd41b-103">Microsoft Edge (Chromium) DevTools Protocol</span></span>

<span data-ttu-id="dd41b-104">通过 Microsoft Edge 的基础 web 平台中的 shift 至 Chromium， [Microsoft edge （EdgeHTML） DevTools 协议](./devtools-protocol/index.md)将不会收到任何进一步的更新。</span><span class="sxs-lookup"><span data-stu-id="dd41b-104">With the shift in the underlying web platform of Microsoft Edge to Chromium, the [Microsoft Edge (EdgeHTML) DevTools Protocol](./devtools-protocol/index.md) will not be receiving any further updates.</span></span> <span data-ttu-id="dd41b-105">Microsoft Edge （Chromium） DevTools 协议将匹配 Chrome DevTools 协议的 Api。</span><span class="sxs-lookup"><span data-stu-id="dd41b-105">The Microsoft Edge (Chromium) DevTools Protocol will match the APIs of the Chrome DevTools Protocol going forward.</span></span> 

<span data-ttu-id="dd41b-106">你可以通过参阅[Chrome DevTools 协议查看器](https://chromedevtools.github.io/devtools-protocol/tot/)找到有关这些域和方法的文档。</span><span class="sxs-lookup"><span data-stu-id="dd41b-106">You can find documentation on those domains and methods by referring to the [Chrome DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/tot/).</span></span>

> [!NOTE]
> <span data-ttu-id="dd41b-107">Microsoft edge （ `ms` Chromium） DevTools 协议不再支持[microsoft Edge （EdgeHTML） DevTools 协议](./devtools-protocol/index.md)中带前缀的任何方法。</span><span class="sxs-lookup"><span data-stu-id="dd41b-107">Any methods that were prefixed with `ms` in the [Microsoft Edge (EdgeHTML) DevTools Protocol](./devtools-protocol/index.md) are no longer supported in the Microsoft Edge (Chromium) DevTools Protocol.</span></span>

## <span data-ttu-id="dd41b-108">使用 DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="dd41b-108">Using the DevTools Protocol</span></span>

<span data-ttu-id="dd41b-109">下面介绍了如何将自定义工具客户端附加到 Microsoft Edge 中的 DevTools 服务器（Chromium）。</span><span class="sxs-lookup"><span data-stu-id="dd41b-109">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge (Chromium).</span></span>

1. <span data-ttu-id="dd41b-110">确保 Microsoft Edge （Chromium）的所有实例均已关闭。</span><span class="sxs-lookup"><span data-stu-id="dd41b-110">Ensure all instances of Microsoft Edge (Chromium) are closed.</span></span>

2. <span data-ttu-id="dd41b-111">通过远程调试端口启动 Microsoft Edge （Chromium）：</span><span class="sxs-lookup"><span data-stu-id="dd41b-111">Launch Microsoft Edge (Chromium) with the remote debugging port:</span></span>

    ```
    msedge.exe --remote-debugging-port=9222
    ```

3. <span data-ttu-id="dd41b-112">或者，如果需要，可以使用不同的用户配置文件启动另一个边缘实例：</span><span class="sxs-lookup"><span data-stu-id="dd41b-112">Optionally, you can start a separate instance of Edge using a distinct user profile if desired:</span></span>

    ```
    msedge.exe --user-data-dir=<some directory>
    ```

4. <span data-ttu-id="dd41b-113">接下来，使用 HTTP `list` 终结点获取可附加的页面目标的列表：</span><span class="sxs-lookup"><span data-stu-id="dd41b-113">Next, use the HTTP `list` endpoint to get a list of attachable page targets:</span></span>

    ```
    http://localhost:9222/json/list
    ```

5. <span data-ttu-id="dd41b-114">最后，连接到 `webSocketDebuggerUrl` 所需的目标并发出命令/通过 DevTools web 套接字服务器订阅事件消息。</span><span class="sxs-lookup"><span data-stu-id="dd41b-114">Finally, connect to the `webSocketDebuggerUrl` of the desired target and issue commands/subscribe to event messages through the DevTools web socket server.</span></span>

## <span data-ttu-id="dd41b-115">DevTools 协议 HTTP 终结点</span><span class="sxs-lookup"><span data-stu-id="dd41b-115">DevTools Protocol HTTP Endpoints</span></span>

<span data-ttu-id="dd41b-116">Microsoft Edge （Chromium） DevTools 协议支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="dd41b-116">The Microsoft Edge (Chromium) DevTools Protocol supports the following HTTP endpoints.</span></span>

## <span data-ttu-id="dd41b-117">/json/version</span><span class="sxs-lookup"><span data-stu-id="dd41b-117">/json/version</span></span>
<span data-ttu-id="dd41b-118">提供有关主机计算机的浏览器以及它支持的 DevTools 协议版本的信息。</span><span class="sxs-lookup"><span data-stu-id="dd41b-118">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="dd41b-119">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-119">Parameters</span></span>**

*<span data-ttu-id="dd41b-120">无</span><span class="sxs-lookup"><span data-stu-id="dd41b-120">None</span></span>*

**<span data-ttu-id="dd41b-121">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-121">Return object</span></span>**

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

## <span data-ttu-id="dd41b-122">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="dd41b-122">/json/protocol</span></span>

<span data-ttu-id="dd41b-123">提供序列化为 JSON 的整个协议 API 图面。</span><span class="sxs-lookup"><span data-stu-id="dd41b-123">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="dd41b-124">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-124">Parameters</span></span>**

*<span data-ttu-id="dd41b-125">无</span><span class="sxs-lookup"><span data-stu-id="dd41b-125">None</span></span>*

**<span data-ttu-id="dd41b-126">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-126">Return object</span></span>**

<span data-ttu-id="dd41b-127">JSON 对象，表示当前版本的协议的可用 API 图面。</span><span class="sxs-lookup"><span data-stu-id="dd41b-127">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="dd41b-128">/json/list</span><span class="sxs-lookup"><span data-stu-id="dd41b-128">/json/list</span></span>

<span data-ttu-id="dd41b-129">提供用于调试的页面目标的候选列表。</span><span class="sxs-lookup"><span data-stu-id="dd41b-129">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="dd41b-130">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-130">Parameters</span></span>**

*<span data-ttu-id="dd41b-131">无</span><span class="sxs-lookup"><span data-stu-id="dd41b-131">None</span></span>*

**<span data-ttu-id="dd41b-132">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-132">Return object</span></span>**

```json
[{
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, … ]
```

## <span data-ttu-id="dd41b-133">/json/close</span><span class="sxs-lookup"><span data-stu-id="dd41b-133">/json/close</span></span>

<span data-ttu-id="dd41b-134">关闭目标进程（例如，在 Microsoft Edge 中（Chromium），关闭页面选项卡。）</span><span class="sxs-lookup"><span data-stu-id="dd41b-134">Closes down the target process (e.g., in Microsoft Edge (Chromium), closes the page tab.)</span></span>

**<span data-ttu-id="dd41b-135">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-135">Parameters</span></span>**

<span data-ttu-id="dd41b-136">目标 ID</span><span class="sxs-lookup"><span data-stu-id="dd41b-136">Target ID</span></span> 

**<span data-ttu-id="dd41b-137">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-137">Return object</span></span>**

```
String(“Target is closing”)
```

## <span data-ttu-id="dd41b-138">Microsoft Edge 远程工具（Beta 版）</span><span class="sxs-lookup"><span data-stu-id="dd41b-138">Remote Tools for Microsoft Edge (Beta)</span></span>

<span data-ttu-id="dd41b-139">现在，你可以从[Microsoft Store](https://www.microsoft.com/store/apps/windows)安装[Microsoft Edge 远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) 。</span><span class="sxs-lookup"><span data-stu-id="dd41b-139">You are now able to install the [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) from the [Microsoft Store](https://www.microsoft.com/store/apps/windows).</span></span> <span data-ttu-id="dd41b-140">此应用使你能够从你的开发计算机远程调试运行在 Windows 10 设备上的 Microsoft Edge （Chromium）。</span><span class="sxs-lookup"><span data-stu-id="dd41b-140">This app enables you to remotely debug Microsoft Edge (Chromium) running on a Windows 10 device from your development machine.</span></span>

<span data-ttu-id="dd41b-141">若要了解如何设置 Windows 10 设备并从开发计算机连接到该设备，请查看[本教程](./devtools-guide-chromium/remote-debugging/windows.md)。</span><span class="sxs-lookup"><span data-stu-id="dd41b-141">To learn how to set up your Windows 10 device and connect to it from your development machine, check out [this tutorial](./devtools-guide-chromium/remote-debugging/windows.md).</span></span>

<span data-ttu-id="dd41b-142">[适用于 Microsoft edge 的远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)将相同的 microsoft Edge （Chromium） DevTools 协议用作[DevTools](./devtools-guide-chromium.md) ，以与运行在你想要调试的 Windows 10 设备上的 microsoft edge 通信。</span><span class="sxs-lookup"><span data-stu-id="dd41b-142">The [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) uses the same Microsoft Edge (Chromium) DevTools Protocol as the [DevTools](./devtools-guide-chromium.md) to communicate with Microsoft Edge running on the Windows 10 device you want to debug.</span></span> <span data-ttu-id="dd41b-143">`/msedge/`在每次调用该协议之前，此应用只需预先操作和进程 ID （ `pid` ）。</span><span class="sxs-lookup"><span data-stu-id="dd41b-143">This app just prepends `/msedge/` and a process ID (`pid`) before each call to the protocol.</span></span> <span data-ttu-id="dd41b-144">它支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="dd41b-144">It supports the following HTTP endpoints.</span></span>

### <span data-ttu-id="dd41b-145">/msedge/json/list</span><span class="sxs-lookup"><span data-stu-id="dd41b-145">/msedge/json/list</span></span>

<span data-ttu-id="dd41b-146">`msedge.exe`在 Windows 10 设备上提供用于调试的所有进程（包括[PWAs](./progressive-web-apps-chromium/index.md)和所有 Microsoft Edge 实例中的所有选项卡）的候选列表。</span><span class="sxs-lookup"><span data-stu-id="dd41b-146">Provides a candidate list of all `msedge.exe` processes (including [PWAs](./progressive-web-apps-chromium/index.md) and all tabs in all instances of Microsoft Edge) on the Windows 10 device for debugging.</span></span>

**<span data-ttu-id="dd41b-147">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-147">Parameters</span></span>**

*<span data-ttu-id="dd41b-148">无</span><span class="sxs-lookup"><span data-stu-id="dd41b-148">None</span></span>*

**<span data-ttu-id="dd41b-149">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-149">Return object</span></span>**

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
}, … ]
```

### <span data-ttu-id="dd41b-150">/msedge/</span><span class="sxs-lookup"><span data-stu-id="dd41b-150">/msedge/</span></span>

<span data-ttu-id="dd41b-151">在功能上等效于[/msedge/json/list](#msedgejsonlist)。</span><span class="sxs-lookup"><span data-stu-id="dd41b-151">Functionally equivalent to [/msedge/json/list](#msedgejsonlist).</span></span> 

### <span data-ttu-id="dd41b-152">/msedge/[pid]/json/list</span><span class="sxs-lookup"><span data-stu-id="dd41b-152">/msedge/[pid]/json/list</span></span>

<span data-ttu-id="dd41b-153">为 Microsoft Edge 实例提供与提供的用于调试匹配的目标的候选列表 `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="dd41b-153">Provides a candidate list of page targets for the Microsoft Edge instance that matches the provided `[pid]` for debugging.</span></span>

**<span data-ttu-id="dd41b-154">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-154">Parameters</span></span>**

*<span data-ttu-id="dd41b-155">无</span><span class="sxs-lookup"><span data-stu-id="dd41b-155">None</span></span>*

**<span data-ttu-id="dd41b-156">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-156">Return object</span></span>**

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
}, … ]
```

### <span data-ttu-id="dd41b-157">/msedge/[pid]/json/version</span><span class="sxs-lookup"><span data-stu-id="dd41b-157">/msedge/[pid]/json/version</span></span>

<span data-ttu-id="dd41b-158">提供与所提供的 `[pid]` 和其支持的 DevTools 协议版本相匹配的 Microsoft Edge 实例的相关信息。</span><span class="sxs-lookup"><span data-stu-id="dd41b-158">Provides information about the Microsoft Edge instance that matches the provided `[pid]` and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="dd41b-159">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-159">Parameters</span></span>**

*<span data-ttu-id="dd41b-160">无</span><span class="sxs-lookup"><span data-stu-id="dd41b-160">None</span></span>*

**<span data-ttu-id="dd41b-161">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-161">Return object</span></span>**

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

### <span data-ttu-id="dd41b-162">/msedge/[pid]/json/protocol/</span><span class="sxs-lookup"><span data-stu-id="dd41b-162">/msedge/[pid]/json/protocol/</span></span>

<span data-ttu-id="dd41b-163">为与所提供的 Microsoft Edge 实例匹配的 Microsoft Edge 实例提供完整的协议 API 图面序列化为 JSON `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="dd41b-163">Provides the entire protocol API surface serialized as JSON for the Microsoft Edge instance that matches the provided `[pid]`.</span></span>

**<span data-ttu-id="dd41b-164">参数</span><span class="sxs-lookup"><span data-stu-id="dd41b-164">Parameters</span></span>**

*<span data-ttu-id="dd41b-165">无</span><span class="sxs-lookup"><span data-stu-id="dd41b-165">None</span></span>*

**<span data-ttu-id="dd41b-166">返回对象</span><span class="sxs-lookup"><span data-stu-id="dd41b-166">Return object</span></span>**

<span data-ttu-id="dd41b-167">JSON 对象，表示与所提供的 Microsoft Edge 实例匹配的 Microsoft Edge 实例所使用的协议版本的可用 API 图面 `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="dd41b-167">JSON object which represents the available API surface for the version of the protocol that the Microsoft Edge instance that matches the provided `[pid]` is using.</span></span>
