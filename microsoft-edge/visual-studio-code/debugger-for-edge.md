---
description: How to debug Microsoft Edge (Chromium) and Microsoft Edge (EdgeHTML) from VS Code
title: Debug Microsoft Edge (Chromium) from VS Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, vs code, visual studio code, debugger
ms.openlocfilehash: 58bcbc927505f4c5a1f493349c3e9475cb75e1be
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695864"
---
# <span data-ttu-id="30059-104">Debugger For Microsoft Edge VS Code Extension</span><span class="sxs-lookup"><span data-stu-id="30059-104">Debugger For Microsoft Edge VS Code Extension</span></span>  

<span data-ttu-id="30059-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] VS Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span><span class="sxs-lookup"><span data-stu-id="30059-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] VS Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="Debugger for Edge VS Code extension at work":::
   <span data-ttu-id="30059-107">Debugger for Edge VS Code extension at work</span><span class="sxs-lookup"><span data-stu-id="30059-107">Debugger for Edge VS Code extension at work</span></span>  
:::image-end:::

<!--![Debugger for Edge VS Code extension at work][ImageGifDebuggerEdge]  -->  

## <span data-ttu-id="30059-108">Launching Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="30059-108">Launching Microsoft Edge</span></span>  

<span data-ttu-id="30059-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span><span class="sxs-lookup"><span data-stu-id="30059-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span></span>  <span data-ttu-id="30059-110">If you do not have any configurations in VS Code, press `F5` on Windows or macOS or select the green **Play** button.</span><span class="sxs-lookup"><span data-stu-id="30059-110">If you do not have any configurations in VS Code, press `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="30059-111">Select **Edge** in the dropdown.</span><span class="sxs-lookup"><span data-stu-id="30059-111">Select **Edge** in the dropdown.</span></span>  <span data-ttu-id="30059-112">You should see a `launch.json` file with the following configuration.</span><span class="sxs-lookup"><span data-stu-id="30059-112">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="30059-113">If you press `F5` on Windows or macOS or select the green **Play** button again, VS Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from VS Code!</span><span class="sxs-lookup"><span data-stu-id="30059-113">If you press `F5` on Windows or macOS or select the green **Play** button again, VS Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from VS Code!</span></span>  

### <span data-ttu-id="30059-114">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="30059-114">Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="30059-115">If you want to launch Microsoft Edge \(Chromium\), the next version of Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span><span class="sxs-lookup"><span data-stu-id="30059-115">If you want to launch Microsoft Edge \(Chromium\), the next version of Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span></span> <span data-ttu-id="30059-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span><span class="sxs-lookup"><span data-stu-id="30059-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span></span>  

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

## <span data-ttu-id="30059-117">Attaching to Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="30059-117">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="30059-118">Attach VS Code to Microsoft Edge \(Chromium\).</span><span class="sxs-lookup"><span data-stu-id="30059-118">Attach VS Code to Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="30059-119">From your terminal, run the following command.</span><span class="sxs-lookup"><span data-stu-id="30059-119">From your terminal, run the following command.</span></span>  

```console
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="30059-120">Add the configuration below to your `launch.json` file.</span><span class="sxs-lookup"><span data-stu-id="30059-120">Add the configuration below to your `launch.json` file.</span></span>   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

<span data-ttu-id="30059-121">If you now run this configuration, VS Code attaches to Microsoft Edge \(Chromium\) and start debugging!</span><span class="sxs-lookup"><span data-stu-id="30059-121">If you now run this configuration, VS Code attaches to Microsoft Edge \(Chromium\) and start debugging!</span></span>  

## <span data-ttu-id="30059-122">Getting in touch with the Elements for Microsoft Edge VS Code extension team</span><span class="sxs-lookup"><span data-stu-id="30059-122">Getting in touch with the Elements for Microsoft Edge VS Code extension team</span></span>    

<span data-ttu-id="30059-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span><span class="sxs-lookup"><span data-stu-id="30059-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  <span data-ttu-id="30059-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span><span class="sxs-lookup"><span data-stu-id="30059-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span></span>  <span data-ttu-id="30059-125">Drag this file into an issue comment to upload it to GitHub.</span><span class="sxs-lookup"><span data-stu-id="30059-125">Drag this file into an issue comment to upload it to GitHub.</span></span>  

<span data-ttu-id="30059-126">To help make the Elements for Microsoft Edge VS Code extension better, your contributions are welcome!</span><span class="sxs-lookup"><span data-stu-id="30059-126">To help make the Elements for Microsoft Edge VS Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="30059-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span><span class="sxs-lookup"><span data-stu-id="30059-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge VS Code extension in action"  -->  
[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "Debugger for Edge VS Code extension in action"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "Documentation | Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 | GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "New Issue - microsoft/vscode-edge-debug2 | GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Debugger for Microsoft Edge | Visual Studio Marketplace"  
