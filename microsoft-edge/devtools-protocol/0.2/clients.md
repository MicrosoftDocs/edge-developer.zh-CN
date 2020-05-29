---
description: Microsoft Edge DevTools 协议版本0.2 支持以下工具客户端。
title: Microsoft Edge DevTools 协议版本0.2 客户端
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 657d594b85c47cc1d5c80b8f2ac3ecc4bd4e4502
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563414"
---
# <span data-ttu-id="b97e8-103">DevTools 协议客户端</span><span class="sxs-lookup"><span data-stu-id="b97e8-103">DevTools Protocol Clients</span></span>

> [!NOTE]
> <span data-ttu-id="b97e8-104">Microsoft Edge DevTools 协议的版本0.2 仅适用于[windows 10 10 月2018更新](/windows/uwp/whats-new/windows-10-build-17763)及更高版本的[Windows 预览体验计划预览版](https://insider.windows.com/en-us/getting-started/)。</span><span class="sxs-lookup"><span data-stu-id="b97e8-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>  

<span data-ttu-id="b97e8-105">**DevTools 协议 0.2**支持以下工具客户端。</span><span class="sxs-lookup"><span data-stu-id="b97e8-105">**DevTools Protocol 0.2** supports the following tooling clients.</span></span>

<span data-ttu-id="b97e8-106">[ ![ Microsoft Edge DevTools 预览](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ visual studio 代码](../media/visual-studio-code.png)](#visual-studio-code) [ ![ Microsoft Visual studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="b97e8-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) [![Microsoft Visual Studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span></span>

## <span data-ttu-id="b97e8-107">Microsoft Edge DevTools 预览</span><span class="sxs-lookup"><span data-stu-id="b97e8-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="b97e8-108">你可以使用独立的[**Microsoft Edge DevTools 预览版**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)microsoft Store 中的 Windows 10 应用来远程调试运行 microsoft Edge 的主机设备（[EdgeHTML 17](../../dev-guide.md)或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="b97e8-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide.md) or later).</span></span>

<span data-ttu-id="b97e8-109">除了版本0.1 中引入的核心脚本调试功能之外，DevTools 协议的版本0.2 还提供了用于样式和布局调试和控制台 Api 的新域。</span><span class="sxs-lookup"><span data-stu-id="b97e8-109">Version 0.2 of the DevTools Protocol provides new domains for style and layout debugging and console APIs, in addition to the core script debugging functionality introduced in Version 0.1.</span></span> <span data-ttu-id="b97e8-110">在 Edge DevTools UI 中，这将转换为[**元素**](../../devtools-guide/elements.md)、[**控制台**](../../devtools-guide/console.md)和[**调试器**](../../devtools-guide/debugger.md)面板中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="b97e8-110">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../../devtools-guide/elements.md), [**Console**](../../devtools-guide/console.md) and [**Debugger**](../../devtools-guide/debugger.md) panels.</span></span> <span data-ttu-id="b97e8-111">当前 Microsoft Edge 远程调试限制为桌面主机，并且支持未来版本中的其他 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="b97e8-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="b97e8-112">下面介绍如何设置 Microsoft Edge DevTools Preview 应用的远程调试。</span><span class="sxs-lookup"><span data-stu-id="b97e8-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="b97e8-113">DevTools 协议版本0.2 要求在主机（debugee）计算机上安装[windows 10 2018 10 月更新](/windows/uwp/whats-new/windows-10-build-17763)或更高版本的 Windows 预览体验计划版本。</span><span class="sxs-lookup"><span data-stu-id="b97e8-113">The DevTools Protocol version 0.2 requires [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="b97e8-114">Edge DevTools Preview 应用（在调试程序计算机上使用）将在 Windows 10 版本16299（Windows 10 秋季创意者更新、10/2017）或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="b97e8-114">The Edge DevTools Preview app (used on the debugger machine) will run on Windows 10 version 16299 (Windows 10 Fall Creators Update, 10/2017) or higher.</span></span>

**<span data-ttu-id="b97e8-115">在主机（debugee）计算机上 .。。</span><span class="sxs-lookup"><span data-stu-id="b97e8-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="b97e8-116">如果您使用的是 WiFi 网络，请确保网络已标记为 "**域**" 或 "**专用**"。</span><span class="sxs-lookup"><span data-stu-id="b97e8-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="b97e8-117">你可以通过以下方法验证此情况：打开[**Windows Defender 安全中心**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)应用，单击 "**防火墙 & 网络保护**"，然后检查您的网络是否列为*域网络*或*专用网络*。</span><span class="sxs-lookup"><span data-stu-id="b97e8-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="b97e8-118">如果它列为*Public*，请转到 "**设置**  >  **网络 & Internet**  >  **wi-fi**"，单击您的网络，然后将 "*网络配置文件*" 按钮切换到 "**专用**"。</span><span class="sxs-lookup"><span data-stu-id="b97e8-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="b97e8-119">在 Windows*设置*中打开**For 开发人员**控制面板（搜索*开发人员*，单击 "*使用开发人员功能*"），然后：</span><span class="sxs-lookup"><span data-stu-id="b97e8-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="b97e8-120">a.</span><span class="sxs-lookup"><span data-stu-id="b97e8-120">a.</span></span> <span data-ttu-id="b97e8-121">在**开发人员模式下**切换。</span><span class="sxs-lookup"><span data-stu-id="b97e8-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="b97e8-122">这将安装*开发人员模式*程序包，从而启用桌面远程工具。</span><span class="sxs-lookup"><span data-stu-id="b97e8-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="b97e8-123">b.</span><span class="sxs-lookup"><span data-stu-id="b97e8-123">b.</span></span> <span data-ttu-id="b97e8-124">启用[**Device Portal**](/windows/uwp/debug-test-perf/device-portal) （*通过局域网连接启用远程诊断*）和**设备发现**（*使你的设备对 USB 连接和本地网络可见*）。</span><span class="sxs-lookup"><span data-stu-id="b97e8-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="b97e8-125">c.</span><span class="sxs-lookup"><span data-stu-id="b97e8-125">c.</span></span> <span data-ttu-id="b97e8-126">启用**身份验证**并提供用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="b97e8-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="b97e8-127">d.</span><span class="sxs-lookup"><span data-stu-id="b97e8-127">d.</span></span> <span data-ttu-id="b97e8-128">注意显示的计算机 IP 地址和连接端口（50443）。</span><span class="sxs-lookup"><span data-stu-id="b97e8-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="b97e8-129">在 Microsoft Edge 中打开要从客户端计算机调试的选项卡。</span><span class="sxs-lookup"><span data-stu-id="b97e8-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="b97e8-130">在客户端（调试器）计算机上 .。。</span><span class="sxs-lookup"><span data-stu-id="b97e8-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="b97e8-131">从 Microsoft Store 安装并启动独立的[Microsoft Edge DevTools 预览版](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)应用。</span><span class="sxs-lookup"><span data-stu-id="b97e8-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="b97e8-132">打开**远程**面板，输入主机的网络位置（URL 和端口），然后单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="b97e8-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="b97e8-133">从出现的 "*不受信任的证书*" 对话框**安装**主机的证书。</span><span class="sxs-lookup"><span data-stu-id="b97e8-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="b97e8-134">提供为 Device Portal 身份验证指定的用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="b97e8-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="b97e8-135">*远程*面板将在主机上加载可调试页面目标的列表。</span><span class="sxs-lookup"><span data-stu-id="b97e8-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="b97e8-136">选择一个以开始调试。</span><span class="sxs-lookup"><span data-stu-id="b97e8-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="b97e8-137">使用 "**刷新**" 按钮更新和重新加载主机上的远程页面目标列表。</span><span class="sxs-lookup"><span data-stu-id="b97e8-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="b97e8-138">单击 "**断开**连接" 按钮以返回到 "*连接到远程设备*" 屏幕并附加到其他主机。</span><span class="sxs-lookup"><span data-stu-id="b97e8-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="b97e8-139">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b97e8-139">Visual Studio Code</span></span>

<span data-ttu-id="b97e8-140">通过[调试程序进行边缘](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)与代码扩展，你可以在 Visual Studio 代码中直接在 Microsoft Edge 中调试运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="b97e8-140">With the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension, you can debug script running in Microsoft Edge directly in Visual Studio Code.</span></span> <span data-ttu-id="b97e8-141">扩展要求你从 localhost 提供你的 web 应用程序，你可以从命令行或[任务](https://code.visualstudio.com/docs/editor/tasks)开始。</span><span class="sxs-lookup"><span data-stu-id="b97e8-141">The extension requires you to be serving your web application from localhost, which you can start from either command-line or a [Task](https://code.visualstudio.com/docs/editor/tasks).</span></span>

<span data-ttu-id="b97e8-142">首先，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b97e8-142">To get started:</span></span>

1. <span data-ttu-id="b97e8-143">安装[调试器以实现边缘](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)与代码扩展。</span><span class="sxs-lookup"><span data-stu-id="b97e8-143">Install the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension.</span></span>

2. <span data-ttu-id="b97e8-144">重启与编码，打开包含要调试的项目的文件夹，然后在代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="b97e8-144">Restart VS Code, open the folder containing the project you wish to debug and set breakpoints in your code.</span></span>

3. <span data-ttu-id="b97e8-145">配置 localhost[启动任务](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)以打开项目的所需页面： "**调试**  >  **添加配置 ...**"。例如：</span><span class="sxs-lookup"><span data-stu-id="b97e8-145">Configure a localhost [launch task](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations) to open the desired page of your project: **Debug** > **Add Configuration...**. For example:</span></span>

    ```json
    {
        "version": "0.2.0",
        "configurations": [

            {
                "name": "Launch localhost",
                "type": "edge",
                "request": "launch",
                "url": "http://localhost/mypage.html",
                "webRoot": "${workspaceFolder}/wwwroot"
            }
        ]
    }
    ```

    <span data-ttu-id="b97e8-146">[*使用调试器*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger)时有更多的启动配置设置。</span><span class="sxs-lookup"><span data-stu-id="b97e8-146">[*Using the debugger*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) has more on launch configuration settings.</span></span> 

4. <span data-ttu-id="b97e8-147">在 localhost 上启动服务器，然后按 "**开始调试**" （播放）按钮或 `F5` 启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b97e8-147">Start your server on localhost and press the **Start Debugging** (play) button or `F5` to launch Microsoft Edge.</span></span> <span data-ttu-id="b97e8-148">命中断点时，将中断到 VS 代码，并可进一步检查代码并逐句通过代码。</span><span class="sxs-lookup"><span data-stu-id="b97e8-148">When a breakpoint is hit, you'll break into VS Code and can further inspect and step through code from there.</span></span>

<span data-ttu-id="b97e8-149">有关详细信息，请查看[适用于 Microsoft Edge 文档的 VS 代码调试器](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--)。</span><span class="sxs-lookup"><span data-stu-id="b97e8-149">For more, check out the [VS Code - Debugger for Microsoft Edge](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) documentation.</span></span>

## <span data-ttu-id="b97e8-150">Microsoft Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b97e8-150">Microsoft Visual Studio</span></span>

<span data-ttu-id="b97e8-151">使用在[Windows 10 2018 10 月更新](/windows/uwp/whats-new/windows-10-build-17763)中运行的最新[**visual Studio**](https://www.visualstudio.com)版本（visual studio 15.8 或更高版本），你可以在任何 ASP.NET 或 .net CORE 项目上从 IDE 启动和调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b97e8-151">Using the latest [**Visual Studio**](https://www.visualstudio.com) version (Visual Studio 15.8 or later) running on [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span>

<span data-ttu-id="b97e8-152">下面介绍如何设置 Visual Studio 的 Microsoft Edge 调试：</span><span class="sxs-lookup"><span data-stu-id="b97e8-152">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="b97e8-153">安装和启动最新的[**Visual studio**](https://www.visualstudio.com/) （visual studio 15.8 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="b97e8-153">Install and launch the latest [**Visual Studio**](https://www.visualstudio.com/) (Visual Studio 15.8 or later).</span></span>

2. <span data-ttu-id="b97e8-154">打开现有的 ASP.NET 或 .NET Core project 或**创建新项目 ...** 使用其中一个**Visual c #** .net 模板。</span><span class="sxs-lookup"><span data-stu-id="b97e8-154">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="b97e8-155">在 project**解决方案资源管理器**中，打开要调试的 JavaScript 文件，并在 IDE 中设置断点，就像处理服务器端代码一样。</span><span class="sxs-lookup"><span data-stu-id="b97e8-155">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="b97e8-156">按 `F5` 启动运行 DevTools 服务器的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b97e8-156">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="b97e8-157">命中断点时，将中断到 Visual Studio 中，并可进一步检查代码并逐句通过代码。</span><span class="sxs-lookup"><span data-stu-id="b97e8-157">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
