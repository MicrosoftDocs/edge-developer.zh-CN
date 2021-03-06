---
description: 如何从 (代码中调试 Microsoft Edge) Chromium (EdgeHTML) Microsoft Edge Visual Studio
title: 从代码 (Microsoft Edge) Chromium Visual Studio
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
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a>Microsoft Edge 调试器Visual Studio代码扩展  

使用 [调试器 for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio 代码扩展，按行调试前端 JavaScript 代码，并直接从 Visual Studio `console.log()` [代码查看语句][VisualstudioCode]！  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="工作中的边缘Visual Studio代码扩展的调试程序" lightbox="./media/debugger-for-edge.gif":::
   工作中的边缘Visual Studio代码扩展的调试程序  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a>启动 Microsoft Edge  

导航到"调试"视图 \ (`Ctrl` + `Shift` + `D` Windows 或 `Command` + `Shift` + `D` macOS\) **中的"调试"视图**。  如果你的"代码"中没有任何Visual Studio，请在 Windows 或 `F5` macOS 上选择，或选择绿色"播放 **"** 按钮。  在 **下拉列表** 中选择"边缘"。  应看到具有以下 `launch.json` 配置的文件。  

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

如果在 Windows 或 macOS 上选择或再次选择绿色"播放"按钮，Visual Studio 代码将启动 `F5` Microsoft Edge \ (EdgeHTML\) 并且你可以直接从 Visual Studio Code 调试在端口上运行**** 的任何 `8080` Web 项目！  

### <a name="microsoft-edge-chromium"></a>Microsoft Edge (Chromium)  

如果要启动 Microsoft Edge \ (Chromium\) ，则新的 Microsoft Edge（而不是 Microsoft Edge \ (EdgeHTML\) ）只需使用要启动的 Microsoft `version` Edge \ (Chromium\) 版本向现有配置添加一个属性，即要启动 \ (或 `dev` `beta` `canary` \) 。  下面的配置将启动 Canary 版本的 Microsoft Edge \ (Chromium\) 。  

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

## <a name="attaching-to-microsoft-edge"></a>附加到 Microsoft Edge  

将Visual Studio代码附加到 Microsoft Edge \ (Chromium\) 。  从终端运行以下命令。  

```shell
start msedge --remote-debugging-port=9222
```  

将下面的配置添加到 `launch.json` 文件。   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

如果现在运行此配置，Visual Studio代码附加到 Microsoft Edge \ (Chromium\) 并开始调试。  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a>与 Microsoft Edge 和代码扩展Visual Studio元素联系    

通过向扩展 [的][GithubMicrosoftVscodeEdgeDebug2NewIssue] [GitHub][GithubMicrosoftVscodeEdgeDebug2] 存储库中提交问题来发送反馈。  请包含调试适配器日志文件，这是为目录中每个运行创建的名称 `%temp%` `vscode-edge-debug2.txt` 。  将此文件拖动到问题注释中，以将其上载到 GitHub。  

为了帮助使 Microsoft Edge 元素Visual Studio代码扩展，欢迎你做出自己的贡献！  在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDebug2] 存储库中查找入门所需的一切。  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]：./media/debugger-for-edge.png"调试器Visual Studio运行中的 Edge Visual Studio代码扩展"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio代码"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新问题 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "适用于 Microsoft Edge |Visual Studio市场"  
