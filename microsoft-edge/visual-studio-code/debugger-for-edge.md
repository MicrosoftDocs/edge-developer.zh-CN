---
description: 如何从 VS 代码调试 Microsoft Edge （Chromium）和 Microsoft Edge （EdgeHTML）
title: 从 VS 代码调试 Microsoft Edge （Chromium）
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/10/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、调试器
ms.openlocfilehash: 7d8d2f87500b3e81866b49de32db91c0a525baf2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564536"
---
# Microsoft Edge 与代码扩展的调试器

借助[适用于 Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)和代码扩展的调试器，你可以逐行调试你的前端 JavaScript 代码行并 `console.log()` 直接从[Visual Studio 代码](https://code.visualstudio.com/)中查看所有语句！

![适用于工作中的边缘与代码扩展的调试器的 GIF](./media/debugger-for-edge.gif)

## 启动 Microsoft Edge

导航到活动栏中的 "调试" 视图（ `Ctrl`  +  `Shift`  +  `D` 在 Windows 或 `Command`  +  `Shift`  +  `D` Mac 上）。 **Activity Bar** 如果 VS 代码中没有任何配置，请按 `F5` Windows 或 Mac 或单击绿色的 "**播放**" 按钮。 在下拉列表中选择 "Edge"。 现在，你将看到具有以下配置的**启动 json**文件：

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

如果你现在按 `F5` Windows 或 Mac 或再次单击绿色的 "**播放**" 按钮，则 VS 代码将启动 Microsoft Edge （EdgeHTML），你将能够从 VS 代码直接调试你在端口**8080**上运行的任何 web 项目！

### Microsoft Edge (Chromium)

如果你想要启动 Microsoft Edge （Chromium），则下一版本的 Microsoft Edge，而不是 Microsoft Edge （EdgeHTML），只需 `version` 使用要启动的 Microsoft edge （ `dev` 、 `beta` 或）版本将属性添加到你的现有配置 `canary` 。 以下配置将启动 Microsoft Edge 的 Chromium 版本（）：

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

## 附加到 Microsoft Edge

你还可以将 VS 代码附加到 Microsoft Edge （Chromium）。 在终端中，运行以下命令：

`start msedge --remote-debugging-port=9222`

将以下配置添加到**启动 json**文件：

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```

如果现在运行此配置，则 VS 代码将附加到 Microsoft Edge （Chromium），并且你可以开始调试！

## 反馈

通过将[问题归档](https://github.com/Microsoft/vscode-edge-debug2/issues/new)到此扩展的[GitHub](https://github.com/Microsoft/vscode-edge-debug2)存储库来向我们发送反馈。 请包含调试适配器日志文件，该文件是在% temp% 目录中为每个运行创建的名称 `vscode-edge-debug2.txt` 。 你可以将此文件拖动到问题注释中，将其上传到 GitHub。

如果您希望帮助我们更好地提高此扩展名，我们将欢迎您的贡献！ 您可以在[GitHub](https://github.com/Microsoft/vscode-edge-debug2)存储库中找到所需的所有内容。