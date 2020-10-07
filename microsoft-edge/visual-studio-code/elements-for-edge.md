---
description: How to use Elements for Microsoft Edge (Chromium) from VS Code
title: Elements for Microsoft Edge (Chromium) from VS Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, vs code, visual studio code, elements
ms.openlocfilehash: ef516d8364c68b550f889bcad0fe762a73ce5f99
ms.sourcegitcommit: 652009c5cea9e75c22b077f0cbcdc0d96bd337ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10694860"
---
# <span data-ttu-id="26261-104">Elements For Microsoft Edge VS Code Extension</span><span class="sxs-lookup"><span data-stu-id="26261-104">Elements For Microsoft Edge VS Code Extension</span></span>  

<span data-ttu-id="26261-105">With the [Elements for Microsoft Edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] VS Code extension, use the Elements tool of the Microsoft Edge browser from within [Visual Studio Code][VisualstudioCode].</span><span class="sxs-lookup"><span data-stu-id="26261-105">With the [Elements for Microsoft Edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] VS Code extension, use the Elements tool of the Microsoft Edge browser from within [Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="26261-106">By either launching or attaching, the Elements tool connects to an instance of Microsoft Edge, displays the runtime HTML structure, and allows you to alter the layout or fix styling issues.</span><span class="sxs-lookup"><span data-stu-id="26261-106">By either launching or attaching, the Elements tool connects to an instance of Microsoft Edge, displays the runtime HTML structure, and allows you to alter the layout or fix styling issues.</span></span>  

:::image type="complex" source="./media/elements-for-edge.gif" alt-text="Elements for Edge VS Code extension at work":::
   <span data-ttu-id="26261-108">Elements for Edge VS Code extension at work</span><span class="sxs-lookup"><span data-stu-id="26261-108">Elements for Edge VS Code extension at work</span></span>  
:::image-end:::

<!--![Elements for Edge VS Code extension at work][ImageGifElementsEdge]  -->  

## <span data-ttu-id="26261-109">Launching Microsoft Edge From the Elements extension</span><span class="sxs-lookup"><span data-stu-id="26261-109">Launching Microsoft Edge From the Elements extension</span></span>  

<span data-ttu-id="26261-110">Navigate to Elements in the **Activity Bar**.</span><span class="sxs-lookup"><span data-stu-id="26261-110">Navigate to Elements in the **Activity Bar**.</span></span>  <span data-ttu-id="26261-111">Next to where it says **Elements for Microsoft Edge: Targets,** there is a plus sign that opens the browser for your app.</span><span class="sxs-lookup"><span data-stu-id="26261-111">Next to where it says **Elements for Microsoft Edge: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="26261-112">If you selected the **about:blank** option, you must navigate to your web app in the browser for it to appear in the Elements panel in VS Code.</span><span class="sxs-lookup"><span data-stu-id="26261-112">If you selected the **about:blank** option, you must navigate to your web app in the browser for it to appear in the Elements panel in VS Code.</span></span>  

## <span data-ttu-id="26261-113">Launching Microsoft Edge from the Debug view</span><span class="sxs-lookup"><span data-stu-id="26261-113">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="26261-114">If you are accustomed to using the Debug view in Visual Studio Code, access Elements from that tool.</span><span class="sxs-lookup"><span data-stu-id="26261-114">If you are accustomed to using the Debug view in Visual Studio Code, access Elements from that tool.</span></span>  <span data-ttu-id="26261-115">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\).</span><span class="sxs-lookup"><span data-stu-id="26261-115">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\).</span></span>  

<span data-ttu-id="26261-116">If you do not have any configurations in VS Code, press `F5` on Windows or macOS or select the green **Play** button.</span><span class="sxs-lookup"><span data-stu-id="26261-116">If you do not have any configurations in VS Code, press `F5` on Windows or macOS or select the green **Play** button.</span></span> <span data-ttu-id="26261-117">Select **Edge** in the dropdown.</span><span class="sxs-lookup"><span data-stu-id="26261-117">Select **Edge** in the dropdown.</span></span> <span data-ttu-id="26261-118">You should see a `launch.json` file with the following configuration.</span><span class="sxs-lookup"><span data-stu-id="26261-118">You should see a `launch.json` file with the following configuration.</span></span>  

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            
            "name": "Launch Microsoft Edge and open the Elements tool",
            "request": "launch",
            "type": "vscode-edge-devtools.debug",
            "url": "http://localhost:3000"
        
        }
    ]
}
```  

<span data-ttu-id="26261-119">Now that you have loaded the correct configuration, either press `F5` on Windows or macOS or select the green **Play** button.</span><span class="sxs-lookup"><span data-stu-id="26261-119">Now that you have loaded the correct configuration, either press `F5` on Windows or macOS or select the green **Play** button.</span></span> <span data-ttu-id="26261-120">The Elements tool, that is familiar to you, from the Microsoft Edge browser launches in VS Code, allowing you to access a screencast of your browser and examine the components of your page.</span><span class="sxs-lookup"><span data-stu-id="26261-120">The Elements tool, that is familiar to you, from the Microsoft Edge browser launches in VS Code, allowing you to access a screencast of your browser and examine the components of your page.</span></span>  

## <span data-ttu-id="26261-121">Attaching to Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="26261-121">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="26261-122">To attach VS Code to an instance of Microsoft Edge\(Chromium\), you must start the browser by running the following command from your terminal.</span><span class="sxs-lookup"><span data-stu-id="26261-122">To attach VS Code to an instance of Microsoft Edge\(Chromium\), you must start the browser by running the following command from your terminal.</span></span>  

`start msedge --remote-debugging-port=9222`  

<span data-ttu-id="26261-123">Once the app has launched, add the configuration below to your **launch.json** file:</span><span class="sxs-lookup"><span data-stu-id="26261-123">Once the app has launched, add the configuration below to your **launch.json** file:</span></span>  

```json
{
    "type": "vscode-edge-devtools.debug",
    "request": "attach",
    "name": "Attach to Microsoft Edge and open the Elements tool",
    "url": "http://localhost:3000/",
    "webRoot": "${workspaceFolder}/out",
    "port": 9222
}
```  

<span data-ttu-id="26261-124">Select **Attach to Microsoft Edge and open the Elements tool** from the Debugger drop-down menu.</span><span class="sxs-lookup"><span data-stu-id="26261-124">Select **Attach to Microsoft Edge and open the Elements tool** from the Debugger drop-down menu.</span></span>  <span data-ttu-id="26261-125">Next, either press `F5` on Windows or macOS or select the green **Play** button.</span><span class="sxs-lookup"><span data-stu-id="26261-125">Next, either press `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="26261-126">VS Code launches the Elements tool, allowing you to access a screencast of your browser, inspect the DOM, and the styling of the components on your page.</span><span class="sxs-lookup"><span data-stu-id="26261-126">VS Code launches the Elements tool, allowing you to access a screencast of your browser, inspect the DOM, and the styling of the components on your page.</span></span>  

## <span data-ttu-id="26261-127">Getting in touch with the Elements for Microsoft Edge VS Code extension team</span><span class="sxs-lookup"><span data-stu-id="26261-127">Getting in touch with the Elements for Microsoft Edge VS Code extension team</span></span>  

<span data-ttu-id="26261-128">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span><span class="sxs-lookup"><span data-stu-id="26261-128">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="26261-129">If you want to help make the Elements for Microsoft Edge VS Code extension better, your contributions are welcome!</span><span class="sxs-lookup"><span data-stu-id="26261-129">If you want to help make the Elements for Microsoft Edge VS Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="26261-130">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span><span class="sxs-lookup"><span data-stu-id="26261-130">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<!-- image links -->  

<!--[ImageGifElementsEdge]: ./media/elements-for-edge.gif "Elements for Edge VS Code extension in action"  -->  
[ImagePngElementsEdge]: ./media/elements-for-edge.png "Elements for Edge VS Code extension in action"  

<!--links -->  

[VscodeElementsEdge]: ./elements-for-edge.md "Elements For Microsoft Edge VS Code Extension | Microsoft Docs"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "Documentation | Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "New Issue - microsoft/vscode-edge-devtools | GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Elements for Microsoft Edge (Chromium) | Visual Studio Marketplace"  
