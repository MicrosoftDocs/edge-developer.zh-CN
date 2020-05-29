---
description: Microsoft Edge DevTools 协议版本0.1 支持以下工具客户端。
title: DevTools 协议版本0.1 客户端
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: a537102bab7b5d914fd721aeca8bed57817e9216
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563437"
---
# <span data-ttu-id="b2b82-103">DevTools 协议客户端</span><span class="sxs-lookup"><span data-stu-id="b2b82-103">DevTools Protocol Clients</span></span>

> [!NOTE]
> <span data-ttu-id="b2b82-104">Microsoft Edge DevTools 协议仅适用于[windows 10 2018 年4月更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)及更高版本的[Windows 预览体验计划预览](https://insider.windows.com/en-us/getting-started/)版本。</span><span class="sxs-lookup"><span data-stu-id="b2b82-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="b2b82-105">**DevTools 协议 0.1**支持以下工具客户端。</span><span class="sxs-lookup"><span data-stu-id="b2b82-105">**DevTools Protocol 0.1** supports the following tooling clients.</span></span>

<span data-ttu-id="b2b82-106">[ ![ Microsoft Edge DevTools 预览版](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ microsoft Visual Studio 15.7 preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)</span><span class="sxs-lookup"><span data-stu-id="b2b82-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)</span></span>

## <span data-ttu-id="b2b82-107">Microsoft Edge DevTools 预览</span><span class="sxs-lookup"><span data-stu-id="b2b82-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="b2b82-108">你可以使用独立的[**Microsoft Edge DevTools 预览版**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)microsoft Store 中的 Windows 10 应用来远程调试运行 microsoft Edge 的主机设备（[EdgeHTML 17](../../dev-guide.md)或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="b2b82-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide.md) or later).</span></span>

<span data-ttu-id="b2b82-109">此 DevTools 协议的预发布版本0.1 提供了核心调试功能，例如设置断点、单步执行代码和浏览堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="b2b82-109">This preliminary Version 0.1 release of the DevTools Protocol provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="b2b82-110">在 Edge DevTools UI 中，这将转换为[**调试器**](../../devtools-guide/debugger.md)面板中可用的功能，减去缓存检查（对于 Web 存储、服务工作人员、缓存 API 和 IndexedDB）。</span><span class="sxs-lookup"><span data-stu-id="b2b82-110">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> <span data-ttu-id="b2b82-111">当前 Microsoft Edge 远程调试限制为桌面主机，并且支持未来版本中的其他 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="b2b82-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="b2b82-112">下面介绍如何设置 Microsoft Edge DevTools Preview 应用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="b2b82-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="b2b82-113">DevTools 协议在预览版中，并且需要[windows 10 四月2018更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)或主机（debugee）计算机上的 Windows 预览体验计划内部版本。</span><span class="sxs-lookup"><span data-stu-id="b2b82-113">The DevTools Protocol is in preview and requires [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="b2b82-114">Edge DevTools Preview 应用（在调试程序计算机上使用）将在秋季创意者更新（版本1709）和 Windows 预览体验计划预览版（版本）上运行。</span><span class="sxs-lookup"><span data-stu-id="b2b82-114">The Edge DevTools Preview app (used on the debugger machine) will run on Fall Creators Update (version 1709) and Windows Insider Preview builds.</span></span>

**<span data-ttu-id="b2b82-115">在主机（debugee）计算机上 .。。</span><span class="sxs-lookup"><span data-stu-id="b2b82-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="b2b82-116">如果您使用的是 WiFi 网络，请确保网络已标记为 "**域**" 或 "**专用**"。</span><span class="sxs-lookup"><span data-stu-id="b2b82-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="b2b82-117">你可以通过以下方法验证此情况：打开[**Windows Defender 安全中心**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)应用，单击 "**防火墙 & 网络保护**"，然后检查您的网络是否列为*域网络*或*专用网络*。</span><span class="sxs-lookup"><span data-stu-id="b2b82-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="b2b82-118">如果它列为*Public*，请转到 "**设置**  >  **网络 & Internet**  >  **wi-fi**"，单击您的网络，然后将 "*网络配置文件*" 按钮切换到 "**专用**"。</span><span class="sxs-lookup"><span data-stu-id="b2b82-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="b2b82-119">在 Windows*设置*中打开**For 开发人员**控制面板（搜索*开发人员*，单击 "*使用开发人员功能*"），然后：</span><span class="sxs-lookup"><span data-stu-id="b2b82-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="b2b82-120">a.</span><span class="sxs-lookup"><span data-stu-id="b2b82-120">a.</span></span> <span data-ttu-id="b2b82-121">在**开发人员模式下**切换。</span><span class="sxs-lookup"><span data-stu-id="b2b82-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="b2b82-122">这将安装*开发人员模式*程序包，从而启用桌面远程工具。</span><span class="sxs-lookup"><span data-stu-id="b2b82-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="b2b82-123">b.</span><span class="sxs-lookup"><span data-stu-id="b2b82-123">b.</span></span> <span data-ttu-id="b2b82-124">启用[**Device Portal**](/windows/uwp/debug-test-perf/device-portal) （*通过局域网连接启用远程诊断*）和**设备发现**（*使你的设备对 USB 连接和本地网络可见*）。</span><span class="sxs-lookup"><span data-stu-id="b2b82-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="b2b82-125">c.</span><span class="sxs-lookup"><span data-stu-id="b2b82-125">c.</span></span> <span data-ttu-id="b2b82-126">启用**身份验证**并提供用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="b2b82-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="b2b82-127">d.</span><span class="sxs-lookup"><span data-stu-id="b2b82-127">d.</span></span> <span data-ttu-id="b2b82-128">注意显示的计算机 IP 地址和连接端口（50443）。</span><span class="sxs-lookup"><span data-stu-id="b2b82-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="b2b82-129">在 Microsoft Edge 中打开要从客户端计算机调试的选项卡。</span><span class="sxs-lookup"><span data-stu-id="b2b82-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="b2b82-130">在客户端（调试器）计算机上 .。。</span><span class="sxs-lookup"><span data-stu-id="b2b82-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="b2b82-131">从 Microsoft Store 安装并启动独立的[Microsoft Edge DevTools 预览版](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)应用。</span><span class="sxs-lookup"><span data-stu-id="b2b82-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="b2b82-132">打开**远程**面板，输入主机的网络位置（URL 和端口），然后单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="b2b82-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="b2b82-133">从出现的 "*不受信任的证书*" 对话框**安装**主机的证书。</span><span class="sxs-lookup"><span data-stu-id="b2b82-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="b2b82-134">提供为 Device Portal 身份验证指定的用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="b2b82-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="b2b82-135">*远程*面板将在主机上加载可调试页面目标的列表。</span><span class="sxs-lookup"><span data-stu-id="b2b82-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="b2b82-136">选择一个以开始调试。</span><span class="sxs-lookup"><span data-stu-id="b2b82-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="b2b82-137">使用 "**刷新**" 按钮更新和重新加载主机上的远程页面目标列表。</span><span class="sxs-lookup"><span data-stu-id="b2b82-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="b2b82-138">单击 "**断开**连接" 按钮以返回到 "*连接到远程设备*" 屏幕并附加到其他主机。</span><span class="sxs-lookup"><span data-stu-id="b2b82-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="b2b82-139">Microsoft Visual Studio 预览版</span><span class="sxs-lookup"><span data-stu-id="b2b82-139">Microsoft Visual Studio Preview</span></span>

<span data-ttu-id="b2b82-140">使用最新的[**Visual Studio 预览版**](https://www.visualstudio.com/vs/preview/)（visual Studio 15.7 preview 1 或更高版本），你可以在任何 ASP.NET 或 .net Core 项目上从 IDE 启动和调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b2b82-140">Using the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span> <span data-ttu-id="b2b82-141">DevTools 协议当前处于预览版中，需要你运行[Windows 预览体验计划预览版](https://insider.windows.com/en-us/getting-started/)。</span><span class="sxs-lookup"><span data-stu-id="b2b82-141">The DevTools Protocol is currently in preview and requires you to be running a [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="b2b82-142">下面介绍如何设置 Visual Studio 的 Microsoft Edge 调试：</span><span class="sxs-lookup"><span data-stu-id="b2b82-142">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="b2b82-143">安装和启动最新的[**Visual Studio 预览版**](https://www.visualstudio.com/vs/preview/)（visual Studio 15.7 preview 1 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="b2b82-143">Install and launch the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later).</span></span>

2. <span data-ttu-id="b2b82-144">打开现有的 ASP.NET 或 .NET Core project 或**创建新项目 ...** 使用其中一个**Visual c #** .net 模板。</span><span class="sxs-lookup"><span data-stu-id="b2b82-144">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="b2b82-145">在 project**解决方案资源管理器**中，打开要调试的 JavaScript 文件，并在 IDE 中设置断点，就像处理服务器端代码一样。</span><span class="sxs-lookup"><span data-stu-id="b2b82-145">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="b2b82-146">按 `F5` 启动运行 DevTools 服务器的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b2b82-146">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="b2b82-147">命中断点时，将中断到 Visual Studio 中，并可进一步检查代码并逐句通过代码。</span><span class="sxs-lookup"><span data-stu-id="b2b82-147">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
