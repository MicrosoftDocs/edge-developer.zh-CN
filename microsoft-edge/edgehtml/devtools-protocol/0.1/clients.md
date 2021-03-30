---
description: Microsoft Edge DevTools 协议版本 0.1 支持以下工具客户端。
title: 'DevTools 协议版本 0.1 客户端 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb7355524ec6dab5cf0275538c5b0c030891d4a9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232099"
---
# <span data-ttu-id="73149-103">DevTools 协议版本 0.1 客户端 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="73149-103">DevTools Protocol Version 0.1 Clients (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="73149-104">Microsoft Edge DevTools 协议仅适用于 [Windows 10 2018 年 4](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 月更新和 [更高版本的 Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="73149-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="73149-105">**DevTools 协议 0.1** 支持以下工具客户端。</span><span class="sxs-lookup"><span data-stu-id="73149-105">**DevTools Protocol 0.1** supports the following tooling clients.</span></span>

<span data-ttu-id="73149-106">[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)</span><span class="sxs-lookup"><span data-stu-id="73149-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)</span></span>

## <span data-ttu-id="73149-107">Microsoft Edge DevTools 预览版</span><span class="sxs-lookup"><span data-stu-id="73149-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="73149-108">可以使用 Microsoft Store 中的独立 [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 应用远程调试运行 Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) 或更高版本的主机) 。</span><span class="sxs-lookup"><span data-stu-id="73149-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) or later).</span></span>

<span data-ttu-id="73149-109">开发人员Tools 协议的初步版本 0.1 版本提供了核心调试功能，例如设置断点、逐步执行代码和探索堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="73149-109">This preliminary Version 0.1 release of the DevTools Protocol provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="73149-110">在 Edge DevTools UI 中，这转换为调试器面板[](../../devtools-guide/debugger.md)中提供的功能，减去 Web 存储、服务工作器、缓存 API 和 IndexedDB (的缓存检查) 。</span><span class="sxs-lookup"><span data-stu-id="73149-110">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> <span data-ttu-id="73149-111">目前，Microsoft Edge 远程调试仅限于桌面主机，未来版本将支持其他 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="73149-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="73149-112">下面将了解如何使用 Microsoft Edge DevTools Preview 应用设置远程调试。</span><span class="sxs-lookup"><span data-stu-id="73149-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="73149-113">DevTools 协议为预览版，需要 [Windows 10 2018](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 年 4 月更新或更高版本的 Windows Insider Preview 版本， (调试) 计算机。</span><span class="sxs-lookup"><span data-stu-id="73149-113">The DevTools Protocol is in preview and requires [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="73149-114">在调试器计算机上 (的边缘 DevTools 预览应用) 将在 Fall Creators Update (版本 1709) 和 Windows Insider Preview 版本上运行。</span><span class="sxs-lookup"><span data-stu-id="73149-114">The Edge DevTools Preview app (used on the debugger machine) will run on Fall Creators Update (version 1709) and Windows Insider Preview builds.</span></span>

**<span data-ttu-id="73149-115">在主机上 (调试) 计算机...</span><span class="sxs-lookup"><span data-stu-id="73149-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="73149-116">如果你使用 WiFi 网络，请确保该网络**标记为"域**"或"**专用"。**</span><span class="sxs-lookup"><span data-stu-id="73149-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="73149-117">你可以打开安全中心Windows Defender，单击[](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)防火墙&**网络**保护并检查你的网络是否列为域*网络或专用网络*。</span><span class="sxs-lookup"><span data-stu-id="73149-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="73149-118">如果列为"公用**"，请转到" 设置网络&  >  **Internet**  >  **Wi-Fi，** 单击网络，将"网络*配置文件*"按钮**切换为"专用"。</span><span class="sxs-lookup"><span data-stu-id="73149-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="73149-119">在 *"Windows*设置 **"** 中打开"适用于开发人员 (*搜索，* 然后单击"使用开发人员功能") ，然后：</span><span class="sxs-lookup"><span data-stu-id="73149-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="73149-120">a.</span><span class="sxs-lookup"><span data-stu-id="73149-120">a.</span></span> <span data-ttu-id="73149-121">切换开发人员 **模式**。</span><span class="sxs-lookup"><span data-stu-id="73149-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="73149-122">这将安装开发人员 *模式* 程序包，为桌面启用远程工具。</span><span class="sxs-lookup"><span data-stu-id="73149-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="73149-123">b.</span><span class="sxs-lookup"><span data-stu-id="73149-123">b.</span></span> <span data-ttu-id="73149-124">启用[**Device Portal**](/windows/uwp/debug-test-perf/device-portal) ( 通过本地网络连接) 设备**发现 (使**设备对*USB*连接和本地网络连接可见) 。</span><span class="sxs-lookup"><span data-stu-id="73149-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="73149-125">c.</span><span class="sxs-lookup"><span data-stu-id="73149-125">c.</span></span> <span data-ttu-id="73149-126">打开 **身份验证并** 输入用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="73149-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="73149-127">d.</span><span class="sxs-lookup"><span data-stu-id="73149-127">d.</span></span> <span data-ttu-id="73149-128">请注意显示 50443 (IP 地址) 端口。</span><span class="sxs-lookup"><span data-stu-id="73149-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="73149-129">在 Microsoft Edge 中打开你希望从客户端计算机调试的选项卡。</span><span class="sxs-lookup"><span data-stu-id="73149-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="73149-130">在客户端 (调试) 计算机...</span><span class="sxs-lookup"><span data-stu-id="73149-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="73149-131">从 Microsoft Store 安装和启动独立的 [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用。</span><span class="sxs-lookup"><span data-stu-id="73149-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="73149-132">打开**远程**面板，然后输入主机 (URL 和端口) 并单击"连接 **"。**</span><span class="sxs-lookup"><span data-stu-id="73149-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="73149-133">**从** 出现的"不受信任的证书"对话框中安装主机 *的* 证书。</span><span class="sxs-lookup"><span data-stu-id="73149-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="73149-134">提供你为 Device Portal 身份验证指定的用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="73149-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="73149-135">远程 *面板* 将在主机上加载可调试页面目标的列表。</span><span class="sxs-lookup"><span data-stu-id="73149-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="73149-136">选择一个开始调试。</span><span class="sxs-lookup"><span data-stu-id="73149-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="73149-137">使用 **"刷新** "按钮更新和重新加载主机上的远程页面目标列表。</span><span class="sxs-lookup"><span data-stu-id="73149-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="73149-138">单击 **"断开连接** "按钮返回到" *连接到远程设备* "屏幕并连接到其他主机。</span><span class="sxs-lookup"><span data-stu-id="73149-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="73149-139">Microsoft Visual Studio 预览版</span><span class="sxs-lookup"><span data-stu-id="73149-139">Microsoft Visual Studio Preview</span></span>

<span data-ttu-id="73149-140">使用最新的 [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) 版本 (Visual Studio 15.7 Preview 1 或更高版本) ，可以从任何 ASP.NET 或 .NET Core 项目的 IDE 启动和调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="73149-140">Using the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span> <span data-ttu-id="73149-141">DevTools 协议目前处于预览阶段，需要你运行 Windows [Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="73149-141">The DevTools Protocol is currently in preview and requires you to be running a [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="73149-142">下面将了解如何设置 Microsoft Edge 调试和Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="73149-142">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="73149-143">安装并启动 15.7 Visual Studio (Visual Studio 15.7 预览版或更高版本) 。 [](https://www.visualstudio.com/vs/preview/)</span><span class="sxs-lookup"><span data-stu-id="73149-143">Install and launch the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later).</span></span>

2. <span data-ttu-id="73149-144">使用 Visual **C#** .NET ASP.NET之一 打开现有项目或 .NET Core 项目或新建项目...</span><span class="sxs-lookup"><span data-stu-id="73149-144">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="73149-145">在项目解决方案 **资源管理器**中，打开要调试的 JavaScript 文件，并像使用服务器端代码一样在 IDE 中设置断点。</span><span class="sxs-lookup"><span data-stu-id="73149-145">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="73149-146">按 `F5` 以启动运行 DevTools Server 的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="73149-146">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="73149-147">当命中一个断点时，你将进入Visual Studio可以进一步检查并逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="73149-147">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
