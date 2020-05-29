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
# <span data-ttu-id="8f8b5-104">Microsoft Edge 与代码扩展的调试器</span><span class="sxs-lookup"><span data-stu-id="8f8b5-104">Debugger for Microsoft Edge VS Code extension</span></span>

<span data-ttu-id="8f8b5-105">借助[适用于 Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)和代码扩展的调试器，你可以逐行调试你的前端 JavaScript 代码行并 `console.log()` 直接从[Visual Studio 代码](https://code.visualstudio.com/)中查看所有语句！</span><span class="sxs-lookup"><span data-stu-id="8f8b5-105">With the [Debugger for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension, you can debug your front-end JavaScript code line by line and see `console.log()` statements all directly from [Visual Studio Code](https://code.visualstudio.com/)!</span></span>

![适用于工作中的边缘与代码扩展的调试器的 GIF](./media/debugger-for-edge.gif)

## <span data-ttu-id="8f8b5-107">启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8f8b5-107">Launching Microsoft Edge</span></span>

<span data-ttu-id="8f8b5-108">导航到活动栏中的 "调试" 视图（ `Ctrl`  +  `Shift`  +  `D` 在 Windows 或 `Command`  +  `Shift`  +  `D` Mac 上）。 **Activity Bar**</span><span class="sxs-lookup"><span data-stu-id="8f8b5-108">Navigate to the Debug view (`Ctrl` + `Shift` + `D` on Windows or `Command` + `Shift` + `D` on Mac) in the **Activity Bar**.</span></span> <span data-ttu-id="8f8b5-109">如果 VS 代码中没有任何配置，请按 `F5` Windows 或 Mac 或单击绿色的 "**播放**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-109">If you do not have any configurations in VS Code, press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="8f8b5-110">在下拉列表中选择 "Edge"。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-110">Select "Edge" in the dropdown.</span></span> <span data-ttu-id="8f8b5-111">现在，你将看到具有以下配置的**启动 json**文件：</span><span class="sxs-lookup"><span data-stu-id="8f8b5-111">You will now see a **launch.json** file with the following configuration:</span></span>

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

<span data-ttu-id="8f8b5-112">如果你现在按 `F5` Windows 或 Mac 或再次单击绿色的 "**播放**" 按钮，则 VS 代码将启动 Microsoft Edge （EdgeHTML），你将能够从 VS 代码直接调试你在端口**8080**上运行的任何 web 项目！</span><span class="sxs-lookup"><span data-stu-id="8f8b5-112">If you now press `F5` on Windows or Mac or click the green **Play** button again, VS Code will launch Microsoft Edge (EdgeHTML) and you will be able to debug any web project you have running on port **8080** directly from VS Code!</span></span>

### <span data-ttu-id="8f8b5-113">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="8f8b5-113">Microsoft Edge (Chromium)</span></span>

<span data-ttu-id="8f8b5-114">如果你想要启动 Microsoft Edge （Chromium），则下一版本的 Microsoft Edge，而不是 Microsoft Edge （EdgeHTML），只需 `version` 使用要启动的 Microsoft edge （ `dev` 、 `beta` 或）版本将属性添加到你的现有配置 `canary` 。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-114">If you want to launch Microsoft Edge (Chromium), the next version of Microsoft Edge, instead of Microsoft Edge (EdgeHTML), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge (Chromium) you want to launch (`dev`, `beta`, or `canary`).</span></span> <span data-ttu-id="8f8b5-115">以下配置将启动 Microsoft Edge 的 Chromium 版本（）：</span><span class="sxs-lookup"><span data-stu-id="8f8b5-115">The configuration below will launch the Canary version of Microsoft Edge (Chromium):</span></span>

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

## <span data-ttu-id="8f8b5-116">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8f8b5-116">Attaching to Microsoft Edge</span></span>

<span data-ttu-id="8f8b5-117">你还可以将 VS 代码附加到 Microsoft Edge （Chromium）。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-117">You can also attach VS Code to Microsoft Edge (Chromium).</span></span> <span data-ttu-id="8f8b5-118">在终端中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8f8b5-118">From your terminal, run the following command:</span></span>

`start msedge --remote-debugging-port=9222`

<span data-ttu-id="8f8b5-119">将以下配置添加到**启动 json**文件：</span><span class="sxs-lookup"><span data-stu-id="8f8b5-119">Add the configuration below to your **launch.json** file:</span></span>

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```

<span data-ttu-id="8f8b5-120">如果现在运行此配置，则 VS 代码将附加到 Microsoft Edge （Chromium），并且你可以开始调试！</span><span class="sxs-lookup"><span data-stu-id="8f8b5-120">If you now run this configuration, VS Code will attach to Microsoft Edge (Chromium) and you can start debugging!</span></span>

## <span data-ttu-id="8f8b5-121">反馈</span><span class="sxs-lookup"><span data-stu-id="8f8b5-121">Feedback</span></span>

<span data-ttu-id="8f8b5-122">通过将[问题归档](https://github.com/Microsoft/vscode-edge-debug2/issues/new)到此扩展的[GitHub](https://github.com/Microsoft/vscode-edge-debug2)存储库来向我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-122">Send us your feedback by [filing an issue](https://github.com/Microsoft/vscode-edge-debug2/issues/new) against this extension's [GitHub repo](https://github.com/Microsoft/vscode-edge-debug2).</span></span> <span data-ttu-id="8f8b5-123">请包含调试适配器日志文件，该文件是在% temp% 目录中为每个运行创建的名称 `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-123">Please include the debug adapter log file, which is created for each run in the %temp% directory with the name `vscode-edge-debug2.txt`.</span></span> <span data-ttu-id="8f8b5-124">你可以将此文件拖动到问题注释中，将其上传到 GitHub。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-124">You can drag this file into an issue comment to upload it to GitHub.</span></span>

<span data-ttu-id="8f8b5-125">如果您希望帮助我们更好地提高此扩展名，我们将欢迎您的贡献！</span><span class="sxs-lookup"><span data-stu-id="8f8b5-125">If you want to help us make this extension better, we welcome your contributions!</span></span> <span data-ttu-id="8f8b5-126">您可以在[GitHub](https://github.com/Microsoft/vscode-edge-debug2)存储库中找到所需的所有内容。</span><span class="sxs-lookup"><span data-stu-id="8f8b5-126">You can find everything you need to get started in [our GitHub repo](https://github.com/Microsoft/vscode-edge-debug2).</span></span>