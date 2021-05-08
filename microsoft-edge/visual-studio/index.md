---
description: Microsoft Edge (Chromium) 和 Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/18/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs， visual studio， 调试器
ms.openlocfilehash: 562952ef238c05922e468501706ab75e1976273d
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387270"
---
# <a name="visual-studio"></a>Visual Studio  

Microsoft [Visual Studio][MicrosoftVisualstudioVs] 是一个集成开发环境 \ (IDE\) 。   使用它来编辑、调试、生成和发布 Web 应用。  它是一个功能丰富的程序，可用于 Web 开发的许多方面。  在大多数 IDEs 提供的标准编辑器和调试器之上，Visual Studio以下功能以便于开发过程。  

*   编译器  
*   代码完成工具  
*   图形设计器  
*   更多  
    
如果您尚未使用 Visual Studio，请导航到" [下载Visual Studio][MicrosoftVisualstudioDownloads] 下载它。  

目前，Visual Studio 2019 支持在 Microsoft Edge 中为 ASP.NET Framework 和 ASP.NET Core 应用调试 JavaScript。  完成以下步骤以使用 Visual Studio调试 Microsoft Edge。  

## <a name="launch-microsoft-edge"></a>启动 Microsoft Edge  

Visual Studio单个按钮完成以下工作流。  

1.  生成你的 ASP.NET ASP.NET 核心应用。  
1.  启动 Web 服务器。  
1.  启动 Microsoft Edge。  
1.  连接Visual Studio调试器。  
    
通过简化的工作流，您可以直接从 IDE 调试在 Microsoft Edge 中运行的 JavaScript。  

### <a name="create-a-new-aspnet-core-web-app"></a>创建新的核心 ASP.NET Web 应用  

Open Visual Studio 2019 and choose **Create a new project**.  On the next screen， choose **ASP.NET Core Web app**  >  **Next**.  

:::image type="complex" source="./media/create-new-project.png" alt-text="创建新的核心 ASP.NET Web 应用" lightbox="./media/create-new-project.png":::
   创建新的核心 ASP.NET Web 应用  
:::image-end:::  

为新项目**提供**项目名称，然后选择"创建 **"。**  对于此示例，选择"React.js模板"，**** 然后选择"创建 **"。**  React.js** 模板 ** 指定如何将React.js与 ASP.NET Core 应用集成。  

### <a name="launch-microsoft-edge-from-visual-studio"></a>从 Microsoft Edge Visual Studio  

创建项目后，打开 `ClientApp/src/components/Counter.js` 。  现在，若要Visual Studio JavaScript，请选择绿色"播放"按钮和**IIS Express****** 旁边的下拉列表。  

:::image type="complex" source="./media/vs-dropdown.png" alt-text="绿色"播放"按钮和 IIS Express 旁边的下拉列表" lightbox="./media/vs-dropdown.png":::
   绿色"播放"**按钮和****IIS Express 旁边的下拉列表**  
:::image-end:::  

选择 **"启用脚本调试**  >  **"。**  

:::image type="complex" source="./media/enable-script-debugging.png" alt-text="在脚本调试中Visual Studio" lightbox="./media/enable-script-debugging.png":::
   在脚本调试中Visual Studio  
:::image-end:::  

在同一个下拉列表中，>**** 想要启动的 Microsoft Visual Studio Edge 预览频道（如 Microsoft Edge Canary、Dev 或 Beta）中的"Web 浏览器"。  如果你尚未使用 Microsoft Edge 预览频道之一，请导航到下载 [Microsoft Edge 预览体验][MicrosoftedgeinsiderDownload] 成员频道以下载一个。  

:::image type="complex" source="./media/set-web-browser.png" alt-text="选择要启动的 Microsoft Edge Visual Studio频道" lightbox="./media/set-web-browser.png":::
   选择要启动的 Microsoft Edge Visual Studio频道  
:::image-end:::  

> [!NOTE]
> 如果选择 Microsoft Edge \ (EdgeHTML\) ，Visual Studio启动它，而不是 Microsoft Edge \ (Chromium\) 。  安装[Microsoft Edge][MicrosoftedgeinsiderDownload]的预览频道之一，或确保计算机上安装的 Microsoft Edge 版本是 Microsoft Edge \ (Chromium\) 而不是 Microsoft Edge \ (EdgeHTML\) 。  

现在，Visual Studio配置正确，选择绿色 **"播放"** 按钮。  Visual Studio生成应用、启动 Web 服务器、启动 Microsoft Edge，然后导航到 或在 中 `https://localhost:44362/` 指定的任何端口 `launchSettings.json` 。  

:::image type="complex" source="./media/edge-launch.png" alt-text="Microsoft Edge 从 Visual Studio" lightbox="./media/edge-launch.png":::
   Microsoft Edge 从 Visual Studio  
:::image-end:::  

### <a name="debug-javascript-running-in-microsoft-edge"></a>调试在 Microsoft Edge 中运行的 JavaScript  

切换回Visual Studio。  在 `Counter.js` 中，若要设置第 13 行上的断点，请选择该行旁边的装订线。  

:::image type="complex" source="./media/set-breakpoint.png" alt-text="Choose the gutter next to Line 13 in Counter.js to set a breakpoint in Visual Studio" lightbox="./media/set-breakpoint.png":::
   选择第 13 行旁边的装订线以 `Counter.js` 在 Visual Studio  
:::image-end:::  

现在切换回已启动的 Microsoft Edge Visual Studio实例。  在 **网页** 左侧的 NavMenu 中的"计数器"上选择。  现在，选择 **"增量"。**  

:::image type="complex" source="./media/edge-counter.png" alt-text="核心 Web 应用中 ASP.NET 计数器页面" lightbox="./media/edge-counter.png":::
   核心 Web 应用中 ASP.NET 计数器页面  
:::image-end:::  

中 JavaScript 调试Visual Studio命中你在 中设置的断点 `Counter.js` 。  Visual Studio现在暂停在 Microsoft Edge 中运行的 JavaScript 的运行时，你可以逐行执行脚本。  

:::image type="complex" source="./media/hit-breakpoint.png" alt-text="Visual Studio Microsoft Edge 中运行的 JavaScript" lightbox="./media/hit-breakpoint.png":::
   Visual Studio Microsoft Edge 中运行的 JavaScript  
:::image-end:::  

该示例只是对 Visual Studio 中提供的功能的一Visual Studio。  有关 Visual Studio 2019 中功能Visual Studio [文档][VisualStudioWindowsIndex]。  

## <a name="attach-to-microsoft-edge"></a>附加到 Microsoft Edge  

以前，必须启动 Microsoft Edge Visual Studio。  现在，可以将调试器Visual Studio Microsoft Edge 的一个已在运行的实例。  

首先，确保没有正在运行的 Microsoft Edge 实例。  现在，从命令行运行以下命令。  

```console
start msedge –remote-debugging-port=9222
```  

从Visual Studio，**打开"调试**"菜单并选择 **"附加到进程"或**选择 `Ctrl` + `Alt` + `P` 。  

:::image type="complex" source="./media/attach-to-process.png" alt-text="选择"附加到进程"Visual Studio" lightbox="./media/attach-to-process.png":::
   选择 **"附加到进程** "Visual Studio  
:::image-end:::  

从附加到**进程对话框中**，将**连接**类型设置为**Chrome devtools 协议 websocket (无身份验证) 。 **  在" **连接目标** "文本框中，键入 `http://localhost:9222/` 并选择 `Enter` 。  查看"附加到进程"对话框中列出的 Microsoft Edge 中已打开的 **选项卡** 列表。  

:::image type="complex" source="./media/attach-to-process-dialog.png" alt-text="配置"附加到进程"对话框Visual Studio" lightbox="./media/attach-to-process-dialog.png":::
   Configure the **Attach to Process** dialog in Visual Studio  
:::image-end:::  

选择 **选择...** > **Microsoft Edge 中的 JavaScript (Chromium) " 旁边的复选框 **。  若要添加选项卡、导航到新选项卡、关闭选项卡并显示"附加到进程"对话框中反映的更改****，请选择"**刷新"** 按钮。  选择要调试的选项卡，然后选择"附加 **"。**  

现在Visual Studio调试器已连接到 Microsoft Edge。  您可以暂停 JavaScript 的运行，直接在 Visual Studio 的"调试 `console.log()` 输出"窗口中设置断点并查看Visual Studio。  

## <a name="getting-in-touch-with-the-microsoft-visual-studio-team"></a>与 Microsoft Visual Studio联系  

Microsoft Visual Studio 和 Microsoft Edge 团队希望详细了解如何在 Visual Studio 中使用 JavaScript。  若要发送反馈，请选择"发送反馈 **"图标Visual Studio**推文[@VisualStudio@EdgeDevTools。][TwitterIntentTweetViualstudioEdgdevtools]  

:::image type="complex" source="./media/feedback-icon.png" alt-text=""发送反馈"图标Visual Studio" lightbox="./media/feedback-icon.png":::
   " **发送反馈** "图标Visual Studio  
:::image-end:::  

<!-- links -->  

[VisualStudioWindowsIndex]: /visualstudio/windows/index "Visual Studio文档|Microsoft Docs"  

[MicrosoftVisualstudioDownloads]: https://visualstudio.microsoft.com/downloads "下载Visual Studio"  
[MicrosoftVisualstudioVs]: https://visualstudio.microsoft.com/vs "Visual Studio IDE"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[TwitterIntentTweetViualstudioEdgdevtools]: https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools "推文@VisualStudio和@EdgeDevTools |Twitter"  
