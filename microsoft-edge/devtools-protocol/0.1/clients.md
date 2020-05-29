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
# DevTools 协议客户端

> [!NOTE]
> Microsoft Edge DevTools 协议仅适用于[windows 10 2018 年4月更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)及更高版本的[Windows 预览体验计划预览](https://insider.windows.com/en-us/getting-started/)版本。

**DevTools 协议 0.1**支持以下工具客户端。

[ ![ Microsoft Edge DevTools 预览版](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ microsoft Visual Studio 15.7 preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)

## Microsoft Edge DevTools 预览

你可以使用独立的[**Microsoft Edge DevTools 预览版**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)microsoft Store 中的 Windows 10 应用来远程调试运行 microsoft Edge 的主机设备（[EdgeHTML 17](../../dev-guide.md)或更高版本）。

此 DevTools 协议的预发布版本0.1 提供了核心调试功能，例如设置断点、单步执行代码和浏览堆栈跟踪。 在 Edge DevTools UI 中，这将转换为[**调试器**](../../devtools-guide/debugger.md)面板中可用的功能，减去缓存检查（对于 Web 存储、服务工作人员、缓存 API 和 IndexedDB）。 当前 Microsoft Edge 远程调试限制为桌面主机，并且支持未来版本中的其他 Windows 10 设备。

下面介绍如何设置 Microsoft Edge DevTools Preview 应用的远程调试。 DevTools 协议在预览版中，并且需要[windows 10 四月2018更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)或主机（debugee）计算机上的 Windows 预览体验计划内部版本。 Edge DevTools Preview 应用（在调试程序计算机上使用）将在秋季创意者更新（版本1709）和 Windows 预览体验计划预览版（版本）上运行。

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

## Microsoft Visual Studio 预览版

使用最新的[**Visual Studio 预览版**](https://www.visualstudio.com/vs/preview/)（visual Studio 15.7 preview 1 或更高版本），你可以在任何 ASP.NET 或 .net Core 项目上从 IDE 启动和调试 Microsoft Edge。 DevTools 协议当前处于预览版中，需要你运行[Windows 预览体验计划预览版](https://insider.windows.com/en-us/getting-started/)。

下面介绍如何设置 Visual Studio 的 Microsoft Edge 调试：

1.  安装和启动最新的[**Visual Studio 预览版**](https://www.visualstudio.com/vs/preview/)（visual Studio 15.7 preview 1 或更高版本）。

2. 打开现有的 ASP.NET 或 .NET Core project 或**创建新项目 ...** 使用其中一个**Visual c #** .net 模板。

3. 在 project**解决方案资源管理器**中，打开要调试的 JavaScript 文件，并在 IDE 中设置断点，就像处理服务器端代码一样。

4. 按 `F5` 启动运行 DevTools 服务器的 Microsoft Edge。 命中断点时，将中断到 Visual Studio 中，并可进一步检查代码并逐句通过代码。
