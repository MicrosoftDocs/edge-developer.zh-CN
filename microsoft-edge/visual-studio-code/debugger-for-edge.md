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
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a><span data-ttu-id="89705-104">Microsoft Edge 调试器Visual Studio代码扩展</span><span class="sxs-lookup"><span data-stu-id="89705-104">Debugger For Microsoft Edge Visual Studio Code Extension</span></span>  

<span data-ttu-id="89705-105">使用 [调试器 for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio 代码扩展，按行调试前端 JavaScript 代码，并直接从 Visual Studio `console.log()` [代码查看语句][VisualstudioCode]！</span><span class="sxs-lookup"><span data-stu-id="89705-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="工作中的边缘Visual Studio代码扩展的调试程序" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="89705-107">工作中的边缘Visual Studio代码扩展的调试程序</span><span class="sxs-lookup"><span data-stu-id="89705-107">Debugger for Edge Visual Studio Code extension at work</span></span>  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a><span data-ttu-id="89705-108">启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="89705-108">Launching Microsoft Edge</span></span>  

<span data-ttu-id="89705-109">导航到"调试"视图 \(`Ctrl` + `Shift` + `D` Windows 或 `Command` + `Shift` + `D` macOS\) **中的"调试"视图**。</span><span class="sxs-lookup"><span data-stu-id="89705-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span></span>  <span data-ttu-id="89705-110">如果你的"代码"中没有任何Visual Studio，请在 Windows 或 `F5` macOS 上选择，或选择绿色"播放 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="89705-110">If you do not have any configurations in Visual Studio Code, select `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="89705-111">在 **下拉列表** 中选择"边缘"。</span><span class="sxs-lookup"><span data-stu-id="89705-111">Select **Edge** in the dropdown.</span></span>  <span data-ttu-id="89705-112">应看到具有以下 `launch.json` 配置的文件。</span><span class="sxs-lookup"><span data-stu-id="89705-112">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="89705-113">如果在 Windows 或 macOS 上选择或再次选择绿色"播放"按钮，Visual Studio 代码将启动 `F5` Microsoft Edge \(EdgeHTML\) 并且你可以直接从 Visual Studio Code 调试在端口上运行 的任何 `8080` Web 项目！</span><span class="sxs-lookup"><span data-stu-id="89705-113">If you select `F5` on Windows or macOS or select the green **Play** button again, Visual Studio Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from Visual Studio Code!</span></span>  

### <a name="microsoft-edge-chromium"></a><span data-ttu-id="89705-114">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="89705-114">Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="89705-115">如果要启动 Microsoft Edge \(Chromium\) ，则新的 Microsoft Edge（而不是 Microsoft Edge \(EdgeHTML\) ）只需使用要启动的 Microsoft `version` Edge \(Chromium\) 版本向现有配置添加一个属性，即要启动 \(或 `dev` `beta` `canary` \) 。</span><span class="sxs-lookup"><span data-stu-id="89705-115">If you want to launch Microsoft Edge \(Chromium\), the new Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span></span>  <span data-ttu-id="89705-116">下面的配置将启动 Canary 版本的 Microsoft Edge \(Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="89705-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span></span>  

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

## <a name="attaching-to-microsoft-edge"></a><span data-ttu-id="89705-117">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="89705-117">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="89705-118">将Visual Studio代码附加到 Microsoft Edge \(Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="89705-118">Attach Visual Studio Code to Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="89705-119">从终端运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="89705-119">From your terminal, run the following command.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="89705-120">将下面的配置添加到 `launch.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="89705-120">Add the configuration below to your `launch.json` file.</span></span>   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

<span data-ttu-id="89705-121">如果现在运行此配置，Visual Studio代码附加到 Microsoft Edge \(Chromium\) 并开始调试。</span><span class="sxs-lookup"><span data-stu-id="89705-121">If you now run this configuration, Visual Studio Code attaches to Microsoft Edge \(Chromium\) and start debugging.</span></span>  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a><span data-ttu-id="89705-122">与 Microsoft Edge 和代码扩展Visual Studio元素联系</span><span class="sxs-lookup"><span data-stu-id="89705-122">Getting in touch with the Elements for Microsoft Edge Visual Studio Code extension team</span></span>    

<span data-ttu-id="89705-123">通过向扩展 [的][GithubMicrosoftVscodeEdgeDebug2NewIssue] [GitHub][GithubMicrosoftVscodeEdgeDebug2] 存储库中提交问题来发送反馈。</span><span class="sxs-lookup"><span data-stu-id="89705-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  <span data-ttu-id="89705-124">请包含调试适配器日志文件，这是为目录中每个运行创建的名称 `%temp%` `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="89705-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span></span>  <span data-ttu-id="89705-125">将此文件拖动到问题注释中，以将其上载到 GitHub。</span><span class="sxs-lookup"><span data-stu-id="89705-125">Drag this file into an issue comment to upload it to GitHub.</span></span>  

<span data-ttu-id="89705-126">为了帮助使 Microsoft Edge 元素Visual Studio代码扩展，欢迎你做出自己的贡献！</span><span class="sxs-lookup"><span data-stu-id="89705-126">To help make the Elements for Microsoft Edge Visual Studio Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="89705-127">在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDebug2] 存储库中查找入门所需的一切。</span><span class="sxs-lookup"><span data-stu-id="89705-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
<span data-ttu-id="89705-128">[ImagePngDebuggerEdge]：./media/debugger-for-edge.png"调试器Visual Studio运行中的 Edge Visual Studio代码扩展"</span><span class="sxs-lookup"><span data-stu-id="89705-128">[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "Debugger for Edge Visual Studio Code extension in action"</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio代码"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新问题 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "适用于 Microsoft Edge |Visual Studio市场"  
