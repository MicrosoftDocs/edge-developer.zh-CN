---
description: 如何在 VS 代码中使用 Microsoft Edge （Chromium）的元素
title: Microsoft Edge 的元素（Chromium）与代码的对比
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、元素
ms.openlocfilehash: ef516d8364c68b550f889bcad0fe762a73ce5f99
ms.sourcegitcommit: 652009c5cea9e75c22b077f0cbcdc0d96bd337ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10694860"
---
# <span data-ttu-id="86a0a-104">Microsoft Edge 与代码扩展的元素</span><span class="sxs-lookup"><span data-stu-id="86a0a-104">Elements For Microsoft Edge VS Code Extension</span></span>  

<span data-ttu-id="86a0a-105">使用[Microsoft edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium]和代码扩展的元素，在[Visual Studio 代码][VisualstudioCode]中使用 microsoft edge 浏览器的 "元素" 工具。</span><span class="sxs-lookup"><span data-stu-id="86a0a-105">With the [Elements for Microsoft Edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] VS Code extension, use the Elements tool of the Microsoft Edge browser from within [Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="86a0a-106">通过启动或附加，元素工具连接到 Microsoft Edge 实例，显示运行时 HTML 结构，并允许你更改布局或修复样式设置问题。</span><span class="sxs-lookup"><span data-stu-id="86a0a-106">By either launching or attaching, the Elements tool connects to an instance of Microsoft Edge, displays the runtime HTML structure, and allows you to alter the layout or fix styling issues.</span></span>  

:::image type="complex" source="./media/elements-for-edge.gif" alt-text="工作中的边缘与代码扩展的元素":::
   <span data-ttu-id="86a0a-108">工作中的边缘与代码扩展的元素</span><span class="sxs-lookup"><span data-stu-id="86a0a-108">Elements for Edge VS Code extension at work</span></span>  
:::image-end:::

<!--![Elements for Edge VS Code extension at work][ImageGifElementsEdge]  -->  

## <span data-ttu-id="86a0a-109">从元素扩展启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="86a0a-109">Launching Microsoft Edge From the Elements extension</span></span>  

<span data-ttu-id="86a0a-110">导航到**活动栏**中的元素。</span><span class="sxs-lookup"><span data-stu-id="86a0a-110">Navigate to Elements in the **Activity Bar**.</span></span>  <span data-ttu-id="86a0a-111">在它所示的**Microsoft Edge 元素的**位置旁边，有一个加号，可为你的应用打开浏览器。</span><span class="sxs-lookup"><span data-stu-id="86a0a-111">Next to where it says **Elements for Microsoft Edge: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="86a0a-112">如果选择了 "**关于：空白**" 选项，则必须导航到浏览器中的 web 应用，以使其显示在 "元素" 面板中的 VS 代码中。</span><span class="sxs-lookup"><span data-stu-id="86a0a-112">If you selected the **about:blank** option, you must navigate to your web app in the browser for it to appear in the Elements panel in VS Code.</span></span>  

## <span data-ttu-id="86a0a-113">从 "调试" 视图启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="86a0a-113">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="86a0a-114">如果你习惯在 Visual Studio 代码中使用 "调试" 视图，请访问该工具中的元素。</span><span class="sxs-lookup"><span data-stu-id="86a0a-114">If you are accustomed to using the Debug view in Visual Studio Code, access Elements from that tool.</span></span>  <span data-ttu-id="86a0a-115">导航到 "调试" 视图 \ （ `Ctrl` + `Shift` + `D` 在 Windows 上或 `Command` + `Shift` + `D` 在 macOS \ 上）。</span><span class="sxs-lookup"><span data-stu-id="86a0a-115">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\).</span></span>  

<span data-ttu-id="86a0a-116">如果 VS 代码中没有任何配置，请按 `F5` Windows 或 macOS 或选择绿色的 "**播放**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="86a0a-116">If you do not have any configurations in VS Code, press `F5` on Windows or macOS or select the green **Play** button.</span></span> <span data-ttu-id="86a0a-117">在下拉列表中选择 "**边缘**"。</span><span class="sxs-lookup"><span data-stu-id="86a0a-117">Select **Edge** in the dropdown.</span></span> <span data-ttu-id="86a0a-118">你应该会看到 `launch.json` 具有以下配置的文件。</span><span class="sxs-lookup"><span data-stu-id="86a0a-118">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="86a0a-119">加载正确的配置后，请按 `F5` Windows 或 macOS 或选择绿色的 "**播放**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="86a0a-119">Now that you have loaded the correct configuration, either press `F5` on Windows or macOS or select the green **Play** button.</span></span> <span data-ttu-id="86a0a-120">从 Microsoft Edge 浏览器启动的 VS 代码中，你熟悉的元素工具使你能够访问浏览器的说明截屏视频，并检查页面组件。</span><span class="sxs-lookup"><span data-stu-id="86a0a-120">The Elements tool, that is familiar to you, from the Microsoft Edge browser launches in VS Code, allowing you to access a screencast of your browser and examine the components of your page.</span></span>  

## <span data-ttu-id="86a0a-121">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="86a0a-121">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="86a0a-122">若要将 VS 代码附加到 Microsoft Edge \ （Chromium \）的实例，必须通过从你的终端运行以下命令来启动浏览器。</span><span class="sxs-lookup"><span data-stu-id="86a0a-122">To attach VS Code to an instance of Microsoft Edge\(Chromium\), you must start the browser by running the following command from your terminal.</span></span>  

`start msedge --remote-debugging-port=9222`  

<span data-ttu-id="86a0a-123">应用启动后，将以下配置添加到**启动 json**文件：</span><span class="sxs-lookup"><span data-stu-id="86a0a-123">Once the app has launched, add the configuration below to your **launch.json** file:</span></span>  

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

<span data-ttu-id="86a0a-124">选择 "**附加到 Microsoft Edge"，然后**从 "调试器" 下拉菜单中打开 "元素" 工具。</span><span class="sxs-lookup"><span data-stu-id="86a0a-124">Select **Attach to Microsoft Edge and open the Elements tool** from the Debugger drop-down menu.</span></span>  <span data-ttu-id="86a0a-125">接下来，按 " `F5` Windows" 或 "macOS" 或选择 "绿色**播放**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="86a0a-125">Next, either press `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="86a0a-126">VS 代码启动 "元素" 工具，使你可以访问浏览器的说明截屏视频、检查 DOM 以及页面上组件的样式。</span><span class="sxs-lookup"><span data-stu-id="86a0a-126">VS Code launches the Elements tool, allowing you to access a screencast of your browser, inspect the DOM, and the styling of the components on your page.</span></span>  

## <span data-ttu-id="86a0a-127">与 Microsoft Edge 和代码扩展团队的元素保持联系</span><span class="sxs-lookup"><span data-stu-id="86a0a-127">Getting in touch with the Elements for Microsoft Edge VS Code extension team</span></span>  

<span data-ttu-id="86a0a-128">通过针对扩展的[GitHub][GithubMicrosoftVscodeEdgeDevtools]存储库将[问题归档][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]来发送反馈。</span><span class="sxs-lookup"><span data-stu-id="86a0a-128">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="86a0a-129">如果你希望帮助使 Microsoft Edge 与代码扩展的元素更好，你的发布是欢迎的！</span><span class="sxs-lookup"><span data-stu-id="86a0a-129">If you want to help make the Elements for Microsoft Edge VS Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="86a0a-130">在扩展的[GitHub][GithubMicrosoftVscodeEdgeDevtools]存储库中查找您需要的所有内容。</span><span class="sxs-lookup"><span data-stu-id="86a0a-130">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<!-- image links -->  

<!--[ImageGifElementsEdge]: ./media/elements-for-edge.gif "Elements for Edge VS Code extension in action"  -->  
<span data-ttu-id="86a0a-131">[ImagePngElementsEdge]：./media/elements-for-edge.png "在操作中对边缘与代码扩展的元素"</span><span class="sxs-lookup"><span data-stu-id="86a0a-131">[ImagePngElementsEdge]: ./media/elements-for-edge.png "Elements for Edge VS Code extension in action"</span></span>  

<!--links -->  

[VscodeElementsEdge]: ./elements-for-edge.md "Microsoft Edge 与代码扩展的元素 |Microsoft 文档"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题-microsoft/vscode-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge 元素（Chromium） |Visual Studio Marketplace"  
