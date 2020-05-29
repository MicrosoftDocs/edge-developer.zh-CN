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
# DevTools 协议客户端

> [!NOTE]
> Microsoft Edge DevTools 协议的版本0.2 仅适用于[windows 10 10 月2018更新](/windows/uwp/whats-new/windows-10-build-17763)及更高版本的[Windows 预览体验计划预览版](https://insider.windows.com/en-us/getting-started/)。  

**DevTools 协议 0.2**支持以下工具客户端。

[ ![ Microsoft Edge DevTools 预览](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ visual studio 代码](../media/visual-studio-code.png)](#visual-studio-code) [ ![ Microsoft Visual studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)

## Microsoft Edge DevTools 预览

你可以使用独立的[**Microsoft Edge DevTools 预览版**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)microsoft Store 中的 Windows 10 应用来远程调试运行 microsoft Edge 的主机设备（[EdgeHTML 17](../../dev-guide.md)或更高版本）。

除了版本0.1 中引入的核心脚本调试功能之外，DevTools 协议的版本0.2 还提供了用于样式和布局调试和控制台 Api 的新域。 在 Edge DevTools UI 中，这将转换为[**元素**](../../devtools-guide/elements.md)、[**控制台**](../../devtools-guide/console.md)和[**调试器**](../../devtools-guide/debugger.md)面板中可用的功能。 当前 Microsoft Edge 远程调试限制为桌面主机，并且支持未来版本中的其他 Windows 10 设备。

下面介绍如何设置 Microsoft Edge DevTools Preview 应用的远程调试。 DevTools 协议版本0.2 要求在主机（debugee）计算机上安装[windows 10 2018 10 月更新](/windows/uwp/whats-new/windows-10-build-17763)或更高版本的 Windows 预览体验计划版本。 Edge DevTools Preview 应用（在调试程序计算机上使用）将在 Windows 10 版本16299（Windows 10 秋季创意者更新、10/2017）或更高版本上运行。

**在主机（debugee）计算机上 .。。**

1. 如果您使用的是 WiFi 网络，请确保网络已标记为 "**域**" 或 "**专用**"。 你可以通过以下方法验证此情况：打开[**Windows Defender 安全中心**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)应用，单击 "**防火墙 & 网络保护**"，然后检查您的网络是否列为*域网络*或*专用网络*。 

    如果它列为*Public*，请转到 "**设置**  >  **网络 & Internet**  >  **wi-fi**"，单击您的网络，然后将 "*网络配置文件*" 按钮切换到 "**专用**"。

2. 在 Windows*设置*中打开**For 开发人员**控制面板（搜索*开发人员*，单击 "*使用开发人员功能*"），然后： 

    a. 在**开发人员模式下**切换。 这将安装*开发人员模式*程序包，从而启用桌面远程工具。

    b. 启用[**Device Portal**](/windows/uwp/debug-test-perf/device-portal) （*通过局域网连接启用远程诊断*）和**设备发现**（*使你的设备对 USB 连接和本地网络可见*）。

    c. 启用**身份验证**并提供用户名/密码。

    d. 注意显示的计算机 IP 地址和连接端口（50443）。

3. 在 Microsoft Edge 中打开要从客户端计算机调试的选项卡。

**在客户端（调试器）计算机上 .。。**

1.  从 Microsoft Store 安装并启动独立的[Microsoft Edge DevTools 预览版](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)应用。

2. 打开**远程**面板，输入主机的网络位置（URL 和端口），然后单击 "**连接**"。

3. 从出现的 "*不受信任的证书*" 对话框**安装**主机的证书。

4. 提供为 Device Portal 身份验证指定的用户名/密码。

5. *远程*面板将在主机上加载可调试页面目标的列表。 选择一个以开始调试。

6. 使用 "**刷新**" 按钮更新和重新加载主机上的远程页面目标列表。 单击 "**断开**连接" 按钮以返回到 "*连接到远程设备*" 屏幕并附加到其他主机。

## Visual Studio Code

通过[调试程序进行边缘](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)与代码扩展，你可以在 Visual Studio 代码中直接在 Microsoft Edge 中调试运行的脚本。 扩展要求你从 localhost 提供你的 web 应用程序，你可以从命令行或[任务](https://code.visualstudio.com/docs/editor/tasks)开始。

首先，请执行以下操作：

1. 安装[调试器以实现边缘](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)与代码扩展。

2. 重启与编码，打开包含要调试的项目的文件夹，然后在代码中设置断点。

3. 配置 localhost[启动任务](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)以打开项目的所需页面： "**调试**  >  **添加配置 ...**"。例如：

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

    [*使用调试器*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger)时有更多的启动配置设置。 

4. 在 localhost 上启动服务器，然后按 "**开始调试**" （播放）按钮或 `F5` 启动 Microsoft Edge。 命中断点时，将中断到 VS 代码，并可进一步检查代码并逐句通过代码。

有关详细信息，请查看[适用于 Microsoft Edge 文档的 VS 代码调试器](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--)。

## Microsoft Visual Studio

使用在[Windows 10 2018 10 月更新](/windows/uwp/whats-new/windows-10-build-17763)中运行的最新[**visual Studio**](https://www.visualstudio.com)版本（visual studio 15.8 或更高版本），你可以在任何 ASP.NET 或 .net CORE 项目上从 IDE 启动和调试 Microsoft Edge。

下面介绍如何设置 Visual Studio 的 Microsoft Edge 调试：

1.  安装和启动最新的[**Visual studio**](https://www.visualstudio.com/) （visual studio 15.8 或更高版本）。

2. 打开现有的 ASP.NET 或 .NET Core project 或**创建新项目 ...** 使用其中一个**Visual c #** .net 模板。

3. 在 project**解决方案资源管理器**中，打开要调试的 JavaScript 文件，并在 IDE 中设置断点，就像处理服务器端代码一样。

4. 按 `F5` 启动运行 DevTools 服务器的 Microsoft Edge。 命中断点时，将中断到 Visual Studio 中，并可进一步检查代码并逐句通过代码。
