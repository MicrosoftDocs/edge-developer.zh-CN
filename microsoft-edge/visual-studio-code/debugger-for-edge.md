---
description: '如何从 VS 代码调试 Microsoft Edge (Chromium) 和 Microsoft Edge (EdgeHTML) '
title: '从 VS 代码调试 Microsoft Edge (Chromium) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、调试器
ms.openlocfilehash: 58bcbc927505f4c5a1f493349c3e9475cb75e1be
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695864"
---
# <span data-ttu-id="f2b9b-104">Microsoft Edge 与代码扩展的调试器</span><span class="sxs-lookup"><span data-stu-id="f2b9b-104">Debugger For Microsoft Edge VS Code Extension</span></span>  

<span data-ttu-id="f2b9b-105">借助 [适用于 Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] 和代码扩展的调试器，逐行调试你的前端 JavaScript 代码行并 `console.log()` 直接从 [Visual Studio 代码][VisualstudioCode]中查看语句！</span><span class="sxs-lookup"><span data-stu-id="f2b9b-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] VS Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="适用于工作的调试器与代码扩展":::
   <span data-ttu-id="f2b9b-107">适用于工作的调试器与代码扩展</span><span class="sxs-lookup"><span data-stu-id="f2b9b-107">Debugger for Edge VS Code extension at work</span></span>  
:::image-end:::

<!--![Debugger for Edge VS Code extension at work][ImageGifDebuggerEdge]  -->  

## <span data-ttu-id="f2b9b-108">启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f2b9b-108">Launching Microsoft Edge</span></span>  

<span data-ttu-id="f2b9b-109">在 `Ctrl` + `Shift` + `D` Windows 上或 `Command` + `Shift` + `D` **活动栏**中的 macOS \ ) 导航到 "调试" 视图 \ (。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span></span>  <span data-ttu-id="f2b9b-110">如果 VS 代码中没有任何配置，请按 `F5` Windows 或 macOS 或选择绿色的 " **播放** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-110">If you do not have any configurations in VS Code, press `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="f2b9b-111">在下拉列表中选择 " **边缘** "。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-111">Select **Edge** in the dropdown.</span></span>  <span data-ttu-id="f2b9b-112">你应该会看到 `launch.json` 具有以下配置的文件。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-112">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="f2b9b-113">如果您按 `F5` Windows 或 macOS 或再次选择绿色的 " **播放** " 按钮，则 VS 代码将启动 Microsoft Edge \ (EdgeHTML \ ) ，您可以 `8080` 直接从 VS 代码调试在端口上运行的任何 web 项目！</span><span class="sxs-lookup"><span data-stu-id="f2b9b-113">If you press `F5` on Windows or macOS or select the green **Play** button again, VS Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from VS Code!</span></span>  

### <span data-ttu-id="f2b9b-114">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="f2b9b-114">Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="f2b9b-115">如果你想要启动 Microsoft Edge \ (Chromium \ ) ，Microsoft Edge 的下一版本，而不是 Microsoft Edge \ (EdgeHTML \ ) ，只需将 `version` 属性添加到你的现有配置中，使用 Microsoft edge \ (Chromium \ ) 启动 \ (`dev` 、 `beta` 或 \ ) `canary` 。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-115">If you want to launch Microsoft Edge \(Chromium\), the next version of Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span></span> <span data-ttu-id="f2b9b-116">下面的配置将启动 Chromium 版本的 Microsoft Edge \ (\ ) 。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span></span>  

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

## <span data-ttu-id="f2b9b-117">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f2b9b-117">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="f2b9b-118">将 VS 代码附加到 Microsoft Edge \ (Chromium \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-118">Attach VS Code to Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="f2b9b-119">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-119">From your terminal, run the following command.</span></span>  

```console
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="f2b9b-120">将下面的配置添加到你的 `launch.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-120">Add the configuration below to your `launch.json` file.</span></span>   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

<span data-ttu-id="f2b9b-121">如果现在运行此配置，则 VS 代码附加到 Microsoft Edge \ (Chromium \ ) 并开始调试！</span><span class="sxs-lookup"><span data-stu-id="f2b9b-121">If you now run this configuration, VS Code attaches to Microsoft Edge \(Chromium\) and start debugging!</span></span>  

## <span data-ttu-id="f2b9b-122">与 Microsoft Edge 和代码扩展团队的元素保持联系</span><span class="sxs-lookup"><span data-stu-id="f2b9b-122">Getting in touch with the Elements for Microsoft Edge VS Code extension team</span></span>    

<span data-ttu-id="f2b9b-123">通过在扩展的[GitHub][GithubMicrosoftVscodeEdgeDebug2]存储库中[归档问题][GithubMicrosoftVscodeEdgeDebug2NewIssue]来发送反馈。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  <span data-ttu-id="f2b9b-124">请包含调试适配器日志文件，该文件是在具有名称的目录中的每个运行中创建的 `%temp%` `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span></span>  <span data-ttu-id="f2b9b-125">将此文件拖动到问题注释中，将其上传到 GitHub。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-125">Drag this file into an issue comment to upload it to GitHub.</span></span>  

<span data-ttu-id="f2b9b-126">为了帮助使 Microsoft Edge 与代码扩展的元素更好，您的发布内容是欢迎的！</span><span class="sxs-lookup"><span data-stu-id="f2b9b-126">To help make the Elements for Microsoft Edge VS Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="f2b9b-127">在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDebug2] 存储库中查找所需的所有内容。</span><span class="sxs-lookup"><span data-stu-id="f2b9b-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge VS Code extension in action"  -->  
<span data-ttu-id="f2b9b-128">[ImagePngDebuggerEdge]：/media/debugger-for-edge.png "调试程序中的边缘与代码扩展"</span><span class="sxs-lookup"><span data-stu-id="f2b9b-128">[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "Debugger for Edge VS Code extension in action"</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新问题-microsoft/vscode-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 的调试器 |Visual Studio Marketplace"  
