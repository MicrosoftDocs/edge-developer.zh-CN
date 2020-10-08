---
description: Microsoft Edge (Chromium) 和 Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs、visual studio、调试器
ms.openlocfilehash: 3fc2e2c3dc21689d8c378ccbe33e4dff813ea12f
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986190"
---
# Visual Studio

Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) 是 (IDE) 的集成开发环境，可用于编辑、调试、构建和发布 web 应用程序。 它是一种功能丰富的程序，可用于 web 开发的许多方面。 在大多数 Ide 提供的标准编辑器和调试器上方以及更高的版本中，Visual Studio 包括编译器、代码完成工具、图形设计器以及更多可轻松开发过程的功能。 转到 [此页面](https://visualstudio.microsoft.com/downloads/) 以下载 Visual Studio （如果尚未使用）。

目前，Visual Studio 2019 支持在 Microsoft Edge 中针对你的 ASP\.NET Framework 和 ASP\.NET Core 应用程序调试 JavaScript。 请按照以下步骤从 Visual Studio 调试 Microsoft Edge。

## 启动 Microsoft Edge
Visual Studio 构建你的 ASP\.NET 和 ASP\.NET Core 应用程序，启动你的 web 服务器，启动 Microsoft Edge，并通过单击一个按钮连接 Visual Studio 调试器。 这使你可以直接从 IDE 中调试在 Microsoft Edge 中运行的 JavaScript！

### 创建新的 ASP.NET Core web 应用程序

打开 Visual Studio 2019，然后选择 " **创建新项目**"。 在下一个屏幕上，选择 **ASP\.NET Core Web 应用程序** ，然后单击 " **下一步**"。

> ##### 图 1  
> 创建新的 ASP.NET Core Web 应用程序 ![ 创建新的 ASP.NET 核心 Web 应用程序](./media/create-new-project.png)  

为新项目提供 **项目名称** ，然后单击 " **创建**"。 在此示例中，选择 " **React.js** 作为模板，显示如何将 React.js 与 ASP.NET Core 应用程序进行集成，然后单击" **创建**"。

### 从 Visual Studio 启动 Microsoft Edge

创建项目后，打开 " **ClientApp/src/组件/Counter.js**"。 现在，通过选择绿色 " **播放** " 按钮旁边的下拉列表和 " **IIS Express**"，告诉 Visual Studio 调试 JavaScript。 

> ##### 图 2  
> 绿色的 "**播放**" 按钮旁边的下拉列表和**iis 表示**" 
> ![ 绿色播放" 按钮旁边的下拉列表和 "iis express"](./media/vs-dropdown.png)  

选择 " **脚本调试** "，然后单击 " **启用**"。

> ##### 图 3  
> 在 visual studio 中启用脚本调试在 ![ Visual studio 中启用脚本调试](./media/enable-script-debugging.png)  

在同一个下拉列表中，选择 " **Web 浏览器** "，然后单击要 Visual Studio 启动的 microsoft edge 的预览频道： Microsoft edge "未选定"、"开发" 或 "Beta"。 如果尚未安装，请转到 [此页面](https://www.microsoftedgeinsider.com/download) 以安装 Microsoft Edge 预览频道。

> ##### 图 4  
> 选择你希望 Visual Studio 启动的 Microsoft Edge 的预览频道 ![ 选择你希望 Visual studio 启动的 Microsoft edge 的预览频道](./media/set-web-browser.png)  

> [!NOTE]
> 如果选择 "Microsoft Edge (EdgeHTML") ，Visual Studio 将启动，而不是 Microsoft Edge (Chromium ") 。 [安装 Microsoft edge 的预览频道](https://www.microsoftedgeinsider.com/download) ，然后选择它们或确保你的计算机上安装的 microsoft edge 版本是 microsoft Edge (Chromium) ，而不是 microsoft Edge (EdgeHTML) 。

现在，已正确配置 Visual Studio，请单击绿色的 " **播放** " 按钮。 Visual Studio 将生成你的应用程序、启动 web 服务器、启动 Microsoft Edge，并导航到 `https://localhost:44362/` **launchSettings.js**中指定的任何端口。

> ##### 图 5  
> 从 Visual studio 启动的 Visual Studio microsoft Edge 中启动的 microsoft Edge ![](./media/edge-launch.png)  

### 调试在 Microsoft Edge 中运行的 JavaScript

切换回 Visual Studio。 在 **Counter.js**中，通过单击该行旁边的装订线，在第13行设置一个断点。

> ##### 图 6
> 通过单击第13行旁边的装订线在 Visual Studio 中设置断点， **Counter.js** 
> ![ 通过单击 Counter.js中第13行旁边的装订线，在 visual studio 中设置断点。](./media/set-breakpoint.png)  

现在切换回启动 Visual Studio 的 Microsoft Edge 实例。 单击页面左侧 NavMenu 中的 " **计数器** "。 现在单击 " **增量**"。

> ##### 图 7
> 我们的 ASP.NET Core web 应用程序中的计数器页面 ![ 我们的 ASP.NET core web 应用程序中的计数器页面](./media/edge-counter.png)  

Visual Studio 中的 JavaScript 调试器将按下在 **Counter.js**中设置的断点。 Visual Studio 现已暂停执行在 Microsoft Edge 中运行的 JavaScript，你可以逐行执行脚本。

> ##### 图 8
> Visual Studio 暂停 Microsoft Edge Visual Studio 中运行的 JavaScript ![ 暂停在 Microsoft edge 中运行的 javascript](./media/hit-breakpoint.png)  

此示例只是 Visual Studio 中可用功能的次要演示。 阅读 [文档](https://docs.microsoft.com/visualstudio/windows/?view=vs-2019)，了解有关 Visual Studio 2019 中可以执行的所有操作的详细信息。

## 附加到 Microsoft Edge
在上一个工作流中，Visual Studio 将启动 Microsoft Edge。 使用此工作流，你将能够将 Visual Studio 调试器附加到已运行的 Microsoft Edge 实例。 

首先，请确保没有任何正在运行的 Microsoft Edge 实例。 现在，从终端运行以下命令：

```console
start msedge –remote-debugging-port=9222
```

从 Visual Studio 中，打开 "**调试**" 菜单，然后选择 "**附加到进程**" 或 "按" `Ctrl`  +  `Alt`  +  `P` 。

> ##### 图 9
> 选择 Visual Studio 中的 " **附加到进程** " 在 ![ visual studio 中选择 "* * 附加到进程 * *"](./media/attach-to-process.png)  

从 " **附加到进程** " 对话框中，将 **连接类型** 设置为 **Chrome devtools 协议 websocket (无身份验证) **。 在 " **连接目标** " 文本框中，键入 "输入" `http://localhost:9222/` ，然后按 `Enter` 。 你应该会在 " **附加到流程** " 对话框中看到在 Microsoft Edge 中列出的打开选项卡的列表。

> ##### 图 10
> 在 visual Studio 中配置 " **附加到进程** " 对话框 ![ 配置 visual studio 中的 "附加到进程" 对话框](./media/attach-to-process-dialog.png)  

单击 "**选择 ...** " 并检查 **Microsoft Edge (的 JavaScript-Chromium) **。 你可以添加选项卡，导航到新选项卡，关闭选项卡，并在 " **附加到进程** " 对话框中单击 " **刷新** " 按钮查看这些更改。 选择要调试的选项卡，然后单击 " **附加**"。

Visual Studio 调试器现已附加到 Microsoft Edge！ 你可以在 `console.log()` Visual Studio 中的 "调试输出" 窗口中暂停执行 JavaScript、设置断点和查看语句。

## 与 Microsoft Visual Studio 团队取得联系  

我们将渴望详细了解如何在 Visual Studio 中使用 JavaScript！  请通过单击 Visual Studio 中的 **反馈** 图标或发推至 [ @VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text= @VisualStudio + @EdgeDevTools) 来向我们发送反馈。  

> ##### 图 11
> Visual Studio 中的 **反馈** 图标 ![ visual studio 中的 "反馈" 图标](./media/feedback-icon.png)  
