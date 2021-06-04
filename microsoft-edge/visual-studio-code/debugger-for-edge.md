---
description: 如何从 Microsoft Edge (Chromium) 调试 Microsoft Edge () EdgeHTML Visual Studio Code
title: 从Microsoft Edge (Chromium) 调试Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs code， visual studio code， debugger
ms.openlocfilehash: e36348fc1ef5e30a511e6eda73c7646a85d8717e
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399293"
---
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a>调试器 for Microsoft Edge Visual Studio Code Extension  

使用[调试器 for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code 扩展，按行调试前端 JavaScript 代码，并直接从 `console.log()` Visual Studio Code！ [][VisualstudioCode]  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="适用于工作中的边缘Visual Studio Code扩展的调试程序" lightbox="./media/debugger-for-edge.gif":::
   适用于工作中的边缘Visual Studio Code扩展的调试程序  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a>启动Microsoft Edge  

导航到活动栏中 (`Ctrl` + `Shift` + `D` `Command` + `Shift` + `D` macOS\Windows macOS\) **调试视图**。。  如果设备中没有任何配置，Visual Studio Code或 macOS Windows选择绿色"播放 `F5` "按钮。 ****  在 **下拉列表** 中选择"边缘"。  应看到 `launch.json` 具有以下配置的文件。  

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "edge",
            "request": "launch",
            "name": "Launch Edge against localhost",
            "url": "http://localhost:8080",
            "webRoot": "${workspaceFolder}"
        }
    ]
}
```  

如果在 Windows 或 macOS 上选择或再次选择绿色"播放"按钮，Visual Studio Code 将启动 `F5` Microsoft Edge \(**** EdgeHTML\) 并且你可以调试你直接从 Visual Studio Code 端口运行的任何 Web `8080` 项目！  

### <a name="microsoft-edge-chromium"></a>Microsoft Edge (Chromium)  

如果要启动 Microsoft Edge \(Chromium\) ，则新的 Microsoft Edge（而不是 Microsoft Edge \(EdgeHTML\) ）只需使用要启动的 Microsoft Edge \(Chromium\) 版本向现有配置添加属性，以启动 `version` `dev` \(、或 `beta` `canary` \) 。  下面的配置将启动 Canary 版本的 Microsoft Edge \(Chromium\) 。  

```json
{
    "type": "edge",
    "request": "launch",
    "version": "canary",
    "name": "Launch Edge against localhost",
    "url": "http://localhost:8080",
    "webRoot": "${workspaceFolder}"
}
```  

## <a name="attaching-to-microsoft-edge"></a>附加到Microsoft Edge  

将Visual Studio Code附加到Microsoft Edge \(Chromium\) 。  从终端运行以下命令。  

```shell
start msedge --remote-debugging-port=9222
```  

将下面的配置添加到 `launch.json` 你的文件。   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

如果现在运行此配置，Visual Studio Code连接到 Microsoft Edge \(Chromium\) 并开始调试。  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a>了解适用于 Microsoft Edge Visual Studio Code 团队的元素    

通过向扩展[的 GitHub][GithubMicrosoftVscodeEdgeDebug2NewIssue][提交问题来][GithubMicrosoftVscodeEdgeDebug2]发送反馈。  请包含调试适配器日志文件，这是为目录中每个运行创建 `%temp%` 的名称 `vscode-edge-debug2.txt` 。  将此文件拖动到问题注释中，以将其上载到GitHub。  

为了帮助更好地扩展Microsoft Edge Visual Studio Code元素，欢迎您做出贡献！  在扩展的 GitHub[查找入门][GithubMicrosoftVscodeEdgeDebug2]所需的一切。  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]： ./media/debugger-for-edge.png Debugger for Edge Visual Studio Code extension in action"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新问题 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  
