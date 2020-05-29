---
description: 如何在 VS 代码中使用 Microsoft Edge （Chromium）的元素
title: Microsoft Edge 的元素（Chromium）与代码的对比
author: erdraud
ms.author: erdraud
ms.date: 08/08/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、元素
ms.openlocfilehash: 4875a4665fe1561ecf587a050bbd44e116d9ce5e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564540"
---
# <span data-ttu-id="2d1c0-104">Microsoft Edge 与代码扩展的元素</span><span class="sxs-lookup"><span data-stu-id="2d1c0-104">Elements for Microsoft Edge VS Code extension</span></span>

<span data-ttu-id="2d1c0-105">通过添加[Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)与代码扩展的元素，可以从[Visual Studio 代码](https://code.visualstudio.com/)中使用浏览器的元素工具。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-105">By adding the [Elements for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools) VS Code extension, you can use the browser's Elements tool from within [Visual Studio Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="2d1c0-106">通过启动或附加，元素工具将连接到 Microsoft Edge 实例，显示运行时 HTML 结构，并允许你更改布局或修复样式设置问题。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-106">By either launching or attaching, the Elements tool will connect to an instance of Microsoft Edge, display the runtime HTML structure, and allow you to alter the layout or fix styling issues.</span></span>

![工作中的 "边缘" 和 "代码扩展" 元素的 GIF](./media/elements-for-edge.gif)

## <span data-ttu-id="2d1c0-108">从元素扩展启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2d1c0-108">Launching Microsoft Edge From the Elements extension</span></span> 

<span data-ttu-id="2d1c0-109">导航到**活动栏**中的元素。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-109">Navigate to Elements in the **Activity Bar**.</span></span> <span data-ttu-id="2d1c0-110">在显示 "Microsoft Edge 的元素：目标" 的位置旁边有一个加号，将为你的应用打开浏览器。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-110">Next to where it says "Elements for Microsoft Edge: Targets," there is a plus sign that will open the browser for your app.</span></span> <span data-ttu-id="2d1c0-111">如果选择了 "*关于：空白*" 选项，则必须导航到浏览器中的 web 应用，以使其显示在 "元素" 面板中的 VS 代码中。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-111">If you selected the *about:blank* option, you will have to navigate to your web app in the browser for it to appear in the Elements panel in VS Code.</span></span>

## <span data-ttu-id="2d1c0-112">从 "调试" 视图启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2d1c0-112">Launching Microsoft Edge from the Debug view</span></span>

<span data-ttu-id="2d1c0-113">如果你习惯在 Visual Studio 代码中使用 "调试" 视图，则可以从该工具访问元素。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-113">If you are accustomed to using the Debug view in Visual Studio Code, you can access Elements from that tool.</span></span> <span data-ttu-id="2d1c0-114">导航到 "调试" 视图（ `Ctrl`  +  `Shift`  +  `D` 在 Windows 上或 `Command`  +  `Shift`  +  `D` 在 Mac 上）。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-114">Navigate to the Debug view (`Ctrl` + `Shift` + `D` on Windows or `Command` + `Shift` + `D` on Mac).</span></span> 

<span data-ttu-id="2d1c0-115">如果 VS 代码中没有任何配置，请按 `F5` Windows 或 Mac 或单击绿色的 "**播放**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-115">If you do not have any configurations in VS Code, press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="2d1c0-116">在下拉列表中选择 "Edge"。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-116">Select "Edge" in the dropdown.</span></span> <span data-ttu-id="2d1c0-117">现在，你将看到具有以下配置的**启动 json**文件：</span><span class="sxs-lookup"><span data-stu-id="2d1c0-117">You will now see a **launch.json** file with the following configuration:</span></span>

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

<span data-ttu-id="2d1c0-118">既然已加载正确的配置，请按 `F5` Windows 或 Mac 或单击绿色的 "**播放**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-118">Now that you have loaded the correct configuration, either press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="2d1c0-119">你熟悉的 Microsoft Edge 浏览器的元素工具现在将在 VS 代码中启动，使你可以访问浏览器的说明截屏视频并检查页面组件。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-119">The Elements tool you are familiar with from the Microsoft Edge browser will now launch in VS Code, allowing you to access a screencast of your browser and examine the components of your page.</span></span>

## <span data-ttu-id="2d1c0-120">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2d1c0-120">Attaching to Microsoft Edge</span></span>
<span data-ttu-id="2d1c0-121">如果你想要将 VS 代码附加到 Microsoft Edge （Chromium）实例，则必须通过从 teminal 运行以下命令来启动浏览器：</span><span class="sxs-lookup"><span data-stu-id="2d1c0-121">If you'd like to attach VS Code to an instance of Microsoft Edge (Chromium), you must start the browser by running the following command from your teminal:</span></span>

`start msedge --remote-debugging-port=9222`

<span data-ttu-id="2d1c0-122">应用启动后，将以下配置添加到**启动 json**文件：</span><span class="sxs-lookup"><span data-stu-id="2d1c0-122">Once the app has launched, add the configuration below to your **launch.json** file:</span></span>

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

<span data-ttu-id="2d1c0-123">从 "调试器" 下拉菜单中选择 "附加到 Microsoft Edge 并打开元素工具"。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-123">Select "Attach to Microsoft Edge and open the Elements tool" from the Debugger drop-down menu.</span></span> <span data-ttu-id="2d1c0-124">接下来，请按 `F5` Windows 或 Mac 或单击绿色的 "**播放**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-124">Next, either press `F5` on Windows or Mac or click the green **Play** button.</span></span> <span data-ttu-id="2d1c0-125">VS 代码将启动元素工具，使你可以访问浏览器的说明截屏视频、检查 DOM 以及页面上组件的样式。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-125">VS Code will launch the Elements tool, allowing you to access a screencast of your browser, inspect the DOM, and the styling of the components on your page.</span></span>

## <span data-ttu-id="2d1c0-126">反馈</span><span class="sxs-lookup"><span data-stu-id="2d1c0-126">Feedback</span></span>
<span data-ttu-id="2d1c0-127">通过将[问题归档](https://github.com/microsoft/vscode-edge-devtools/issues/new)到此扩展的[GitHub](https://github.com/microsoft/vscode-edge-devtools)存储库来向我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-127">Send us your feedback by [filing an issue](https://github.com/microsoft/vscode-edge-devtools/issues/new) against this extension's [GitHub repo](https://github.com/microsoft/vscode-edge-devtools).</span></span> 

<span data-ttu-id="2d1c0-128">如果您希望帮助我们更好地提高此扩展名，我们将欢迎您的贡献！</span><span class="sxs-lookup"><span data-stu-id="2d1c0-128">If you want to help us make this extension better, we welcome your contributions!</span></span> <span data-ttu-id="2d1c0-129">您可以在[GitHub](https://github.com/microsoft/vscode-edge-devtools)存储库中找到所需的所有内容。</span><span class="sxs-lookup"><span data-stu-id="2d1c0-129">You can find everything you need to get started in [our GitHub repo](https://github.com/microsoft/vscode-edge-devtools).</span></span>