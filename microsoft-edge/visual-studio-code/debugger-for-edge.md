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
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a><span data-ttu-id="19508-104">调试器 for Microsoft Edge Visual Studio Code Extension</span><span class="sxs-lookup"><span data-stu-id="19508-104">Debugger For Microsoft Edge Visual Studio Code Extension</span></span>  

<span data-ttu-id="19508-105">使用[调试器 for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code 扩展，按行调试前端 JavaScript 代码，并直接从 `console.log()` Visual Studio Code！ [][VisualstudioCode]</span><span class="sxs-lookup"><span data-stu-id="19508-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="适用于工作中的边缘Visual Studio Code扩展的调试程序" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="19508-107">适用于工作中的边缘Visual Studio Code扩展的调试程序</span><span class="sxs-lookup"><span data-stu-id="19508-107">Debugger for Edge Visual Studio Code extension at work</span></span>  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a><span data-ttu-id="19508-108">启动Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="19508-108">Launching Microsoft Edge</span></span>  

<span data-ttu-id="19508-109">导航到活动栏中 (`Ctrl` + `Shift` + `D` `Command` + `Shift` + `D` macOS\Windows macOS\) **调试视图**。。</span><span class="sxs-lookup"><span data-stu-id="19508-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span></span>  <span data-ttu-id="19508-110">如果设备中没有任何配置，Visual Studio Code或 macOS Windows选择绿色"播放 `F5` "按钮。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="19508-110">If you do not have any configurations in Visual Studio Code, select `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="19508-111">在 **下拉列表** 中选择"边缘"。</span><span class="sxs-lookup"><span data-stu-id="19508-111">Select **Edge** in the dropdown.</span></span>  <span data-ttu-id="19508-112">应看到 `launch.json` 具有以下配置的文件。</span><span class="sxs-lookup"><span data-stu-id="19508-112">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="19508-113">如果在 Windows 或 macOS 上选择或再次选择绿色"播放"按钮，Visual Studio Code 将启动 `F5` Microsoft Edge \ (\*\*\*\* EdgeHTML\) 并且你可以调试你直接从 Visual Studio Code 端口运行的任何 Web `8080` 项目！</span><span class="sxs-lookup"><span data-stu-id="19508-113">If you select `F5` on Windows or macOS or select the green **Play** button again, Visual Studio Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from Visual Studio Code!</span></span>  

### <a name="microsoft-edge-chromium"></a><span data-ttu-id="19508-114">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="19508-114">Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="19508-115">如果要启动 Microsoft Edge \ (Chromium\) ，则新的 Microsoft Edge（而不是 Microsoft Edge \ (EdgeHTML\) ）只需使用要启动的 Microsoft Edge \ (Chromium\) 版本向现有配置添加属性，以启动 `version` `dev` \ (、或 `beta` `canary` \) 。</span><span class="sxs-lookup"><span data-stu-id="19508-115">If you want to launch Microsoft Edge \(Chromium\), the new Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span></span>  <span data-ttu-id="19508-116">下面的配置将启动 Canary 版本的 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="19508-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span></span>  

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

## <a name="attaching-to-microsoft-edge"></a><span data-ttu-id="19508-117">附加到Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="19508-117">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="19508-118">将Visual Studio Code附加到Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="19508-118">Attach Visual Studio Code to Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="19508-119">从终端运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="19508-119">From your terminal, run the following command.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="19508-120">将下面的配置添加到 `launch.json` 你的文件。</span><span class="sxs-lookup"><span data-stu-id="19508-120">Add the configuration below to your `launch.json` file.</span></span>   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

<span data-ttu-id="19508-121">如果现在运行此配置，Visual Studio Code连接到 Microsoft Edge \ (Chromium\) 并开始调试。</span><span class="sxs-lookup"><span data-stu-id="19508-121">If you now run this configuration, Visual Studio Code attaches to Microsoft Edge \(Chromium\) and start debugging.</span></span>  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a><span data-ttu-id="19508-122">了解适用于 Microsoft Edge Visual Studio Code 团队的元素</span><span class="sxs-lookup"><span data-stu-id="19508-122">Getting in touch with the Elements for Microsoft Edge Visual Studio Code extension team</span></span>    

<span data-ttu-id="19508-123">通过向扩展[的 GitHub][GithubMicrosoftVscodeEdgeDebug2NewIssue][提交问题来][GithubMicrosoftVscodeEdgeDebug2]发送反馈。</span><span class="sxs-lookup"><span data-stu-id="19508-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  <span data-ttu-id="19508-124">请包含调试适配器日志文件，这是为目录中每个运行创建 `%temp%` 的名称 `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="19508-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span></span>  <span data-ttu-id="19508-125">将此文件拖动到问题注释中，以将其上载到GitHub。</span><span class="sxs-lookup"><span data-stu-id="19508-125">Drag this file into an issue comment to upload it to GitHub.</span></span>  

<span data-ttu-id="19508-126">为了帮助更好地扩展Microsoft Edge Visual Studio Code元素，欢迎您做出贡献！</span><span class="sxs-lookup"><span data-stu-id="19508-126">To help make the Elements for Microsoft Edge Visual Studio Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="19508-127">在扩展的 GitHub[查找入门][GithubMicrosoftVscodeEdgeDebug2]所需的一切。</span><span class="sxs-lookup"><span data-stu-id="19508-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
<span data-ttu-id="19508-128">[ImagePngDebuggerEdge]： ./media/debugger-for-edge.png Debugger for Edge Visual Studio Code extension in action"</span><span class="sxs-lookup"><span data-stu-id="19508-128">[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "Debugger for Edge Visual Studio Code extension in action"</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新问题 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  
