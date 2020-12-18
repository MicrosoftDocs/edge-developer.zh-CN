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
# DevTools 协议版本 0.1 客户端 (EdgeHTML)   

> [!NOTE]
> Microsoft Edge DevTools 协议仅适用于 [Windows 10 2018 年 4](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 月更新和 [更高版本的 Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。

**DevTools 协议 0.1** 支持以下工具客户端。

[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)

## Microsoft Edge DevTools 预览版

可以使用 Microsoft Store 中的独立 [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 应用远程调试运行 Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) 或更高版本的主机) 。

开发人员Tools 协议的初步版本 0.1 版本提供了核心调试功能，例如设置断点、逐步执行代码和探索堆栈跟踪。 在 Edge DevTools UI 中，这转换为调试器面板[****](../../devtools-guide/debugger.md)中提供的功能，减去 Web 存储、服务工作器、缓存 API 和 IndexedDB (的缓存检查) 。 目前，Microsoft Edge 远程调试仅限于桌面主机，未来版本将支持其他 Windows 10 设备。

下面将了解如何使用 Microsoft Edge DevTools Preview 应用设置远程调试。 DevTools 协议为预览版，需要 [Windows 10 2018](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 年 4 月更新或更高版本的 Windows Insider Preview 版本， (调试) 计算机。 在调试器计算机上 (的边缘 DevTools 预览应用) 将在 Fall Creators Update (版本 1709) 和 Windows Insider Preview 版本上运行。

**在主机上 (调试) 计算机...**

1. 如果你使用 WiFi 网络，请确保该网络**标记为"域**"或"**专用"。** 你可以打开安全中心Windows Defender，单击[****](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)防火墙&**网络**保护并检查你的网络是否列为域*网络或**专用网络*。 

    如果列为"公用**"，请转到"**** 设置网络&  >  **Internet**  >  **Wi-Fi，** 单击网络，将"网络*配置文件*"按钮**切换为"专用"。**

2. 在 *"Windows*设置 **"** 中打开"适用于开发人员 (*搜索，* 然后单击"使用开发人员功能**") ，然后： 

    a. 切换开发人员 **模式**。 这将安装开发人员 *模式* 程序包，为桌面启用远程工具。

    b. 启用[**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (** 通过本地网络连接) 设备**发现 (使**设备对*USB*连接和本地网络连接可见) 。

    c. 打开 **身份验证并** 输入用户名/密码。

    d. 请注意显示 50443 (IP 地址) 端口。

3. 在 Microsoft Edge 中打开你希望从客户端计算机调试的选项卡。

**在客户端 (调试) 计算机...**

1.  从 Microsoft Store 安装和启动独立的 [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) 应用。

2. 打开**远程**面板，然后输入主机 (URL 和端口) 并单击"连接 **"。**

3. **从** 出现的"不受信任的证书"对话框中安装主机 *的* 证书。

4. 提供你为 Device Portal 身份验证指定的用户名/密码。

5. 远程 *面板* 将在主机上加载可调试页面目标的列表。 选择一个开始调试。

6. 使用 **"刷新** "按钮更新和重新加载主机上的远程页面目标列表。 单击 **"断开连接** "按钮返回到" *连接到远程设备* "屏幕并连接到其他主机。

## Microsoft Visual Studio 预览版

使用最新的 [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) 版本 (Visual Studio 15.7 Preview 1 或更高版本) ，可以从任何 ASP.NET 或 .NET Core 项目的 IDE 启动和调试 Microsoft Edge。 DevTools 协议目前处于预览阶段，需要你运行 Windows [Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。

下面将了解如何设置 Microsoft Edge 调试和Visual Studio：

1.  安装并启动 15.7 Visual Studio (Visual Studio 15.7 预览版或更高版本) 。 [****](https://www.visualstudio.com/vs/preview/)

2. 使用 Visual **C#** .NET ASP.NET之一**** 打开现有项目或 .NET Core 项目或新建项目...

3. 在项目解决方案 **资源管理器**中，打开要调试的 JavaScript 文件，并像使用服务器端代码一样在 IDE 中设置断点。

4. 按 `F5` 以启动运行 DevTools Server 的 Microsoft Edge。 当命中一个断点时，你将进入Visual Studio可以进一步检查并逐步执行代码。
