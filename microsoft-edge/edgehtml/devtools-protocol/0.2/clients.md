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
# Microsoft Edge DevTools 协议版本 0.2 客户端 (EdgeHTML)   

> [!NOTE]
> Microsoft Edge DevTools 协议的版本 0.2 仅适用于 [Windows 10 2018 年 10 月](/windows/uwp/whats-new/windows-10-build-17763) 更新和更高版本的 Windows Insider [Preview](https://insider.windows.com/en-us/getting-started/) 版本。  

**DevTools 协议 0.2** 支持以下工具客户端。

[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) Microsoft Visual Studio [ ![ 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)

## Microsoft Edge DevTools 预览版

可以使用 Microsoft Store 中的独立 [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 应用远程调试运行 Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) 或更高版本的主机) 。

除了版本 0.1 中引入的核心脚本调试功能外，DevTools 协议的版本 0.2 还提供了用于样式和布局调试以及控制台 API 的新域。 在 Edge DevTools UI 中，这转换为元素、控制台[****](../../devtools-guide/elements.md)和调试[****](../../devtools-guide/console.md)器面板[**中提供**](../../devtools-guide/debugger.md)的功能。 目前，Microsoft Edge 远程调试仅限于桌面主机，未来版本将支持其他 Windows 10 设备。

下面将了解如何使用 Microsoft Edge DevTools Preview 应用设置远程调试。 DevTools 协议版本 0.2 需要 [Windows 10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763) 月更新或主机上调试 (预览版的更高版本) 版本。 在调试器计算机上 (的边缘 DevTools 预览应用) 将在 Windows 10 版本 16299 (Windows 10 Fall Creators Update，10/2017) 或更高版本运行。

**在主机上 (调试) 计算机...**

1. 如果你使用 WiFi 网络，请确保该网络**标记为"域**"或"**专用"。** 你可以打开安全中心Windows Defender，单击[****](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)防火墙&**网络**保护并检查你的网络是否列为域*网络或**专用网络*。 

    如果列为"公用**"，请转到"**** 设置网络&  >  **Internet**  >  **Wi-Fi，** 单击网络，将"网络*配置文件*"按钮切换为 **"专用"。**

2. 在 *"Windows*设置****"** 中打开开发人员控制面板 (*搜索，* 然后单击"使用开发人员功能") ，然后： 

    a. 切换开发人员 **模式**。 这将安装开发人员 *模式* 程序包，为桌面启用远程工具。

    b. 启用 Device [**Portal**](/windows/uwp/debug-test-perf/device-portal) (** 通过本地网络连接) 设备发现 (使设备对*USB*连接**** 和本地网络连接可见) 。

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

## Visual Studio Code

借助适用于 Edge VS 代码 [扩展的](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) 调试器，可以直接在 Microsoft Edge 中调试Visual Studio代码。 扩展需要您从 localhost 提供 Web 应用程序，可以从命令行或 [Task](https://code.visualstudio.com/docs/editor/tasks)开始。

首先，请执行以下操作：

1. 安装适用于边缘 VS [代码扩展的](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) 调试器。

2. 重新启动 VS Code，打开包含要调试的项目的文件夹，然后在你的代码中设置断点。

3. 配置 localhost[启动任务](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)以打开项目所需的页面：**调试**  >  **添加配置...** 例如：

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

    [*使用调试器*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) 对启动配置设置具有更多功能。 

4. 在 localhost 上启动服务器，**** 然后按"开始调试 (") 按钮或启动 Microsoft `F5` Edge。 当命中断点时，你将进入 VS Code，并可以进一步检查并逐步执行代码。

有关详细信息，请查看 [适用于 Microsoft Edge 的 VS 代码 - 调试](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) 器文档。

## Microsoft Visual Studio

使用在 [**Windows**](https://www.visualstudio.com) [10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763)月更新上运行的最新 Visual Studio 版本 (Visual Studio 15.8 或更高版本) ，可以从任何 ASP.NET 或 .NET Core 项目上的 IDE 启动和调试 Microsoft Edge。

下面将了解如何设置 Microsoft Edge 调试和Visual Studio：

1.  安装并启动 15.8 [**Visual Studio (Visual Studio**](https://www.visualstudio.com/) 15.8 或更高版本) 。

2. 使用 Visual **C#** .NET ASP.NET之一**** 打开现有项目或 .NET Core 项目或新建项目...

3. 在项目解决方案 **资源管理器**中，打开要调试的 JavaScript 文件，并像使用服务器端代码一样在 IDE 中设置断点。

4. 按 `F5` 以启动运行 DevTools Server 的 Microsoft Edge。 当命中一个断点时，你将进入Visual Studio可以进一步检查并逐步执行代码。
