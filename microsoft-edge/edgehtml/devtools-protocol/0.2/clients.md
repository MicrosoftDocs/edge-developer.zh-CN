---
description: Microsoft Edge DevTools 协议版本 0.2 支持以下工具客户端。
title: 'Microsoft Edge DevTools 协议版本 0.2 客户端 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b471ff5a4051411fc205a269d811524c38acac72
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232087"
---
# <span data-ttu-id="618c3-103">Microsoft Edge DevTools 协议版本 0.2 客户端 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="618c3-103">Microsoft Edge DevTools Protocol Version 0.2 Clients (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="618c3-104">Microsoft Edge DevTools 协议的版本 0.2 仅适用于 [Windows 10 2018 年 10 月](/windows/uwp/whats-new/windows-10-build-17763) 更新和更高版本的 Windows Insider [Preview](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="618c3-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>  

<span data-ttu-id="618c3-105">**DevTools 协议 0.2** 支持以下工具客户端。</span><span class="sxs-lookup"><span data-stu-id="618c3-105">**DevTools Protocol 0.2** supports the following tooling clients.</span></span>

<span data-ttu-id="618c3-106">[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) Microsoft Visual Studio [ ![ 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="618c3-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) [![Microsoft Visual Studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span></span>

## <span data-ttu-id="618c3-107">Microsoft Edge DevTools 预览版</span><span class="sxs-lookup"><span data-stu-id="618c3-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="618c3-108">可以使用 Microsoft Store 中的独立 [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 应用远程调试运行 Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) 或更高版本的主机) 。</span><span class="sxs-lookup"><span data-stu-id="618c3-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) or later).</span></span>

<span data-ttu-id="618c3-109">除了版本 0.1 中引入的核心脚本调试功能外，DevTools 协议的版本 0.2 还提供了用于样式和布局调试以及控制台 API 的新域。</span><span class="sxs-lookup"><span data-stu-id="618c3-109">Version 0.2 of the DevTools Protocol provides new domains for style and layout debugging and console APIs, in addition to the core script debugging functionality introduced in Version 0.1.</span></span> <span data-ttu-id="618c3-110">在 Edge DevTools UI 中，这转换为元素、控制台[\*\*\*\*](../../devtools-guide/elements.md)和调试[\*\*\*\*](../../devtools-guide/console.md)器面板[**中提供**](../../devtools-guide/debugger.md)的功能。</span><span class="sxs-lookup"><span data-stu-id="618c3-110">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../../devtools-guide/elements.md), [**Console**](../../devtools-guide/console.md) and [**Debugger**](../../devtools-guide/debugger.md) panels.</span></span> <span data-ttu-id="618c3-111">目前，Microsoft Edge 远程调试仅限于桌面主机，未来版本将支持其他 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="618c3-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="618c3-112">下面将了解如何使用 Microsoft Edge DevTools Preview 应用设置远程调试。</span><span class="sxs-lookup"><span data-stu-id="618c3-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="618c3-113">DevTools 协议版本 0.2 需要 [Windows 10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763) 月更新或主机上调试 (预览版的更高版本) 版本。</span><span class="sxs-lookup"><span data-stu-id="618c3-113">The DevTools Protocol version 0.2 requires [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="618c3-114">在调试器计算机上 (的边缘 DevTools 预览应用) 将在 Windows 10 版本 16299 (Windows 10 Fall Creators Update，10/2017) 或更高版本运行。</span><span class="sxs-lookup"><span data-stu-id="618c3-114">The Edge DevTools Preview app (used on the debugger machine) will run on Windows 10 version 16299 (Windows 10 Fall Creators Update, 10/2017) or higher.</span></span>

**<span data-ttu-id="618c3-115">在主机上 (调试) 计算机...</span><span class="sxs-lookup"><span data-stu-id="618c3-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="618c3-116">如果你使用 WiFi 网络，请确保该网络**标记为"域**"或"**专用"。**</span><span class="sxs-lookup"><span data-stu-id="618c3-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="618c3-117">你可以打开安全中心Windows Defender，单击[\*\*\*\*](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)防火墙&**网络**保护并检查你的网络是否列为域*网络或\*\*专用网络*。</span><span class="sxs-lookup"><span data-stu-id="618c3-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="618c3-118">如果列为"公用\**"，请转到"\*\*\*\* 设置网络&  >  **Internet**  >  **Wi-Fi，** 单击网络，将"网络*配置文件\*"按钮切换为 **"专用"。**</span><span class="sxs-lookup"><span data-stu-id="618c3-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="618c3-119">在 *"Windows*设置\*\*\*\*"\*\* 中打开开发人员控制面板 (*搜索，* 然后单击"使用开发人员功能") ，然后：</span><span class="sxs-lookup"><span data-stu-id="618c3-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="618c3-120">a.</span><span class="sxs-lookup"><span data-stu-id="618c3-120">a.</span></span> <span data-ttu-id="618c3-121">切换开发人员 **模式**。</span><span class="sxs-lookup"><span data-stu-id="618c3-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="618c3-122">这将安装开发人员 *模式* 程序包，为桌面启用远程工具。</span><span class="sxs-lookup"><span data-stu-id="618c3-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="618c3-123">b.</span><span class="sxs-lookup"><span data-stu-id="618c3-123">b.</span></span> <span data-ttu-id="618c3-124">启用 Device [**Portal**](/windows/uwp/debug-test-perf/device-portal) (\*\* 通过本地网络连接) 设备发现 (使设备对*USB*连接\*\*\*\* 和本地网络连接可见) 。</span><span class="sxs-lookup"><span data-stu-id="618c3-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="618c3-125">c.</span><span class="sxs-lookup"><span data-stu-id="618c3-125">c.</span></span> <span data-ttu-id="618c3-126">打开 **身份验证并** 输入用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="618c3-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="618c3-127">d.</span><span class="sxs-lookup"><span data-stu-id="618c3-127">d.</span></span> <span data-ttu-id="618c3-128">请注意显示 50443 (IP 地址) 端口。</span><span class="sxs-lookup"><span data-stu-id="618c3-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="618c3-129">在 Microsoft Edge 中打开你希望从客户端计算机调试的选项卡。</span><span class="sxs-lookup"><span data-stu-id="618c3-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="618c3-130">在客户端 (调试) 计算机...</span><span class="sxs-lookup"><span data-stu-id="618c3-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="618c3-131">从 Microsoft Store 安装和启动独立的 [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用。</span><span class="sxs-lookup"><span data-stu-id="618c3-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="618c3-132">打开**远程**面板，然后输入主机 (URL 和端口) 并单击"连接 **"。**</span><span class="sxs-lookup"><span data-stu-id="618c3-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="618c3-133">**从** 出现的"不受信任的证书"对话框中安装主机 *的* 证书。</span><span class="sxs-lookup"><span data-stu-id="618c3-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="618c3-134">提供你为 Device Portal 身份验证指定的用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="618c3-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="618c3-135">远程 *面板* 将在主机上加载可调试页面目标的列表。</span><span class="sxs-lookup"><span data-stu-id="618c3-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="618c3-136">选择一个开始调试。</span><span class="sxs-lookup"><span data-stu-id="618c3-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="618c3-137">使用 **"刷新** "按钮更新和重新加载主机上的远程页面目标列表。</span><span class="sxs-lookup"><span data-stu-id="618c3-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="618c3-138">单击 **"断开连接** "按钮返回到" *连接到远程设备* "屏幕并连接到其他主机。</span><span class="sxs-lookup"><span data-stu-id="618c3-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="618c3-139">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="618c3-139">Visual Studio Code</span></span>

<span data-ttu-id="618c3-140">借助适用于 Edge VS 代码 [扩展的](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) 调试器，可以直接在 Microsoft Edge 中调试Visual Studio代码。</span><span class="sxs-lookup"><span data-stu-id="618c3-140">With the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension, you can debug script running in Microsoft Edge directly in Visual Studio Code.</span></span> <span data-ttu-id="618c3-141">扩展需要您从 localhost 提供 Web 应用程序，可以从命令行或 [Task](https://code.visualstudio.com/docs/editor/tasks)开始。</span><span class="sxs-lookup"><span data-stu-id="618c3-141">The extension requires you to be serving your web application from localhost, which you can start from either command-line or a [Task](https://code.visualstudio.com/docs/editor/tasks).</span></span>

<span data-ttu-id="618c3-142">首先，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="618c3-142">To get started:</span></span>

1. <span data-ttu-id="618c3-143">安装适用于边缘 VS [代码扩展的](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) 调试器。</span><span class="sxs-lookup"><span data-stu-id="618c3-143">Install the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension.</span></span>

2. <span data-ttu-id="618c3-144">重新启动 VS Code，打开包含要调试的项目的文件夹，然后在你的代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="618c3-144">Restart VS Code, open the folder containing the project you wish to debug and set breakpoints in your code.</span></span>

3. <span data-ttu-id="618c3-145">配置 localhost[启动任务](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)以打开项目所需的页面：**调试**  >  **添加配置...** 例如：</span><span class="sxs-lookup"><span data-stu-id="618c3-145">Configure a localhost [launch task](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations) to open the desired page of your project: **Debug** > **Add Configuration...**. For example:</span></span>

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

    <span data-ttu-id="618c3-146">[*使用调试器*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) 对启动配置设置具有更多功能。</span><span class="sxs-lookup"><span data-stu-id="618c3-146">[*Using the debugger*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) has more on launch configuration settings.</span></span> 

4. <span data-ttu-id="618c3-147">在 localhost 上启动服务器，\*\*\*\* 然后按"开始调试 (") 按钮或启动 Microsoft `F5` Edge。</span><span class="sxs-lookup"><span data-stu-id="618c3-147">Start your server on localhost and press the **Start Debugging** (play) button or `F5` to launch Microsoft Edge.</span></span> <span data-ttu-id="618c3-148">当命中断点时，你将进入 VS Code，并可以进一步检查并逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="618c3-148">When a breakpoint is hit, you'll break into VS Code and can further inspect and step through code from there.</span></span>

<span data-ttu-id="618c3-149">有关详细信息，请查看 [适用于 Microsoft Edge 的 VS 代码 - 调试](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) 器文档。</span><span class="sxs-lookup"><span data-stu-id="618c3-149">For more, check out the [VS Code - Debugger for Microsoft Edge](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) documentation.</span></span>

## <span data-ttu-id="618c3-150">Microsoft Visual Studio</span><span class="sxs-lookup"><span data-stu-id="618c3-150">Microsoft Visual Studio</span></span>

<span data-ttu-id="618c3-151">使用在 [**Windows**](https://www.visualstudio.com) [10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763)月更新上运行的最新 Visual Studio 版本 (Visual Studio 15.8 或更高版本) ，可以从任何 ASP.NET 或 .NET Core 项目上的 IDE 启动和调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="618c3-151">Using the latest [**Visual Studio**](https://www.visualstudio.com) version (Visual Studio 15.8 or later) running on [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span>

<span data-ttu-id="618c3-152">下面将了解如何设置 Microsoft Edge 调试和Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="618c3-152">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="618c3-153">安装并启动 15.8 [**Visual Studio (Visual Studio**](https://www.visualstudio.com/) 15.8 或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="618c3-153">Install and launch the latest [**Visual Studio**](https://www.visualstudio.com/) (Visual Studio 15.8 or later).</span></span>

2. <span data-ttu-id="618c3-154">使用 Visual **C#** .NET ASP.NET之一\*\*\*\* 打开现有项目或 .NET Core 项目或新建项目...</span><span class="sxs-lookup"><span data-stu-id="618c3-154">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="618c3-155">在项目解决方案 **资源管理器**中，打开要调试的 JavaScript 文件，并像使用服务器端代码一样在 IDE 中设置断点。</span><span class="sxs-lookup"><span data-stu-id="618c3-155">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="618c3-156">按 `F5` 以启动运行 DevTools Server 的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="618c3-156">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="618c3-157">当命中一个断点时，你将进入Visual Studio可以进一步检查并逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="618c3-157">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
