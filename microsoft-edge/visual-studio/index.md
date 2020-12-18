---
description: Microsoft Edge (Chromium) 和 Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs， visual studio， 调试器
ms.openlocfilehash: f3796a040fe6c658211b4009445b5c179ab9b077
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231207"
---
# Visual Studio

Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) 是 IDE (集成开发) ，可用于编辑、调试、生成和发布 Web 应用程序。 它是一个功能丰富的程序，可用于 Web 开发的许多方面。 在大多数 ID 提供的标准编辑器和调试器之上，Visual Studio编译器、代码完成工具、图形设计器以及更多功能，以便于开发过程。 如果 [尚未使用](https://visualstudio.microsoft.com/downloads/) Visual Studio，请前往此页面进行下载。

目前，Visual Studio 2019 支持在 Microsoft Edge 中为 ASP\.NET Framework 和 ASP\.NET Core 应用程序调试 JavaScript。 按照以下步骤从 microsoft Edge Visual Studio。

## 启动 Microsoft Edge
Visual Studio ASP\.NET 和 ASP\.NET Core 应用程序，启动 Web 服务器，启动 Microsoft Edge，并连接 Visual Studio 调试器，只需单击一个按钮即可。 这使你可以直接从 IDE 调试在 Microsoft Edge 中运行的 JavaScript！

### 创建新的核心ASP.NET Web 应用程序

打开Visual Studio 2019 并选择 **"新建项目"。** 下一个屏幕上，选择**ASP\.NET Core Web 应用程序**，然后单击"下一**步"。**

> ##### 图 1  
> 新建核心 web ASP.NET 新建核心 Web ![ ASP.NET Web 应用程序](./media/create-new-project.png)  

提供**新项目的项目**名称，然后单击"创建 **"。** 对于此示例，选择React.js模板，以演示如何**** 将 React.js 与 ASP.NET Core 应用程序集成，然后单击"创建 **"。**

### 从 microsoft Edge Visual Studio

创建项目后，打开**ClientApp/src/components/Counter.js。 ** 现在，通过Visual Studio"播放"按钮和**IIS Express**旁边的下拉列表，告诉用户**** 调试 JavaScript。 

> ##### 图 2  
> 绿色"播放"按钮和******IIS Express**旁边的下拉列表绿色"播放"按钮和 
> ![ IIS Express 旁边的下拉列表](./media/vs-dropdown.png)  

选择 **"脚本调试"，** 然后单击"**启用"。**

> ##### 图 3  
> 在"启用脚本调试Visual Studio ![ 中启用脚本调试Visual Studio](./media/enable-script-debugging.png)  

在同一下拉列表中，选择 **"Web** 浏览器"，然后单击要启动的 Microsoft Edge Visual Studio频道：Microsoft Edge Canary、Dev 或 Beta。 如果尚未安装，请前往 [此页面](https://www.microsoftedgeinsider.com/download) 以安装 Microsoft Edge 预览频道。

> ##### 图 4  
> 选择要启动的 Microsoft Edge Visual Studio 选择要启动的 Microsoft ![ Edge Visual Studio频道](./media/set-web-browser.png)  

> [!NOTE]
> 如果选择 Microsoft Edge (EdgeHTML) ，Visual Studio启动它，而不是 Microsoft Edge (Chromium) 。 安装[Microsoft Edge](https://www.microsoftedgeinsider.com/download)的预览频道并选择它们，或确保计算机上安装的 Microsoft Edge 版本是 Microsoft Edge (Chromium) ，而不是 Microsoft Edge (EdgeHTML) 。

现在，Visual Studio配置正确，请单击绿色 **"播放"** 按钮。 Visual Studio将生成应用程序、启动 Web 服务器、启动 Microsoft Edge，并导航到或任何在launchSettings.js`https://localhost:44362/` ** 中指定的端口**。

> ##### 图 5  
> 从 Microsoft Edge Visual Studio ![ Microsoft Edge 启动的 Microsoft Edge Visual Studio](./media/edge-launch.png)  

### 调试在 Microsoft Edge 中运行的 JavaScript

切换回Visual Studio。 In **Counter.js， **set a breakpoint on Line 13 by clicking in theutter next to that line.

> ##### 图 6
> 在 Visual Studio 中设置断点，方法是单击**Counter.js**中第 13 行旁边的装订线Visual Studio单击 Visual Studio 中第 13 行旁边的装订线Counter.js
> ![](./media/set-breakpoint.png)  

现在切换回已启动的 Microsoft Edge Visual Studio实例。 在 **页面** 左侧的 NavMenu 中单击"计数器"。 现在单击 **"增量"。**

> ##### 图 7
> 核心 Web 应用程序中的ASP.NET核心 Web 应用程序中的"计数器"ASP.NET ![ 页](./media/edge-counter.png)  

Visual Studio中的 JavaScript 调试器将命中我们在Counter.js** 中设置的断点 **。 Visual Studio Microsoft Edge 中运行的 JavaScript 已暂停执行，你可以逐行执行脚本。

> ##### 图 8
> Visual Studio暂停在 Microsoft Edge 中运行的 JavaScript ![ Visual Studio暂停在 Microsoft Edge 中运行的 JavaScript](./media/hit-breakpoint.png)  

此示例只是对 Visual Studio 中可用功能的一个小Visual Studio。 通过阅读文档了解有关 2019 年 Visual Studio可以执行的所有[操作。](/visualstudio/windows/?view=vs-2019&preserve-view=true)

## 附加到 Microsoft Edge
在上一工作流中，Visual Studio启动 Microsoft Edge。 通过此工作流，你可以将Visual Studio调试器附加到已在运行的 Microsoft Edge 实例。 

首先，确保没有正在运行的 Microsoft Edge 实例。 现在，从终端运行以下命令：

```console
start msedge –remote-debugging-port=9222
```

从Visual Studio，打开**调试菜单，** 然后选择 **"附加到进程"** 或按 `Ctrl`  +  `Alt`  +  `P` 。

> ##### 图 9
> 选择 **"附加到进程** "Visual Studio ![ 选择"附加到进程"**Visual Studio](./media/attach-to-process.png)  

从"**附加到进程"** 对话框中，将**连接**类型设置为**Chrome devtools 协议 websocket， (身份验证) 。 ** 在" **连接目标** "文本框中，键入 `http://localhost:9222/` 并按 `Enter` 。 你应该会看到 Microsoft Edge 中已打开的选项卡列表在"附加到进程"**对话框中列出。**

> ##### 图 10
> 在 **Visual Studio** 中配置"附加到进程"对话框 ![ Visual Studio](./media/attach-to-process-dialog.png)  

单击 **"选择...** 并检查 **JavaScript (Microsoft Edge – Chromium) **。 可以通过单击"刷新"按钮添加选项卡、导航到新选项卡和关闭选项卡，并查看这些更改反映在"附加到**进程"****对话框中。** 选择要调试的选项卡，然后单击"附加 **"。**

现在Visual Studio调试器连接到 Microsoft Edge！ 您可以暂停 JavaScript 的执行、设置断点，并直接在 Visual Studio 的"调试 `console.log()` 输出"窗口中查看Visual Studio。

## 与 Microsoft Visual Studio团队联系  

我们期待了解有关如何使用 JavaScript 在 Visual Studio！  Please send us feedback by clicking the **Feedback** icon in Visual Studio or by twittering [ @VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text= @VisualStudio+@EdgeDevTools) .  

> ##### 图 11
> " **反馈** "图标 ![ Visual Studio"反馈"图标Visual Studio](./media/feedback-icon.png)  
