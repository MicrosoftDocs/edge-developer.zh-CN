---
description: Microsoft Edge （Chromium）和 Visual Studio 代码
title: Visual Studio Code
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/12/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、调试程序、webhint
ms.openlocfilehash: 94148864edbd43adbe2dc9f3d0c2fa0c1f7f0b43
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564539"
---
# <span data-ttu-id="03773-104">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="03773-104">Visual Studio Code</span></span>

<span data-ttu-id="03773-105">[Visual Studio 代码](https://code.visualstudio.com/Docs)是一个轻量级但功能强大的源代码编辑器，可在桌面上运行，并且适用于 Windows、MacOS 和 Linux。</span><span class="sxs-lookup"><span data-stu-id="03773-105">[Visual Studio Code](https://code.visualstudio.com/Docs) is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux.</span></span> <span data-ttu-id="03773-106">它附带了针对 JavaScript、TypeScript 和 node.js 的内置支持，因此它是适用于现成的 web 开发人员的绝佳工具！</span><span class="sxs-lookup"><span data-stu-id="03773-106">It comes with built-in support for JavaScript, TypeScript and Node.js so it's a great tool for web developers right out of the box!</span></span> <span data-ttu-id="03773-107">转到[此页面](https://code.visualstudio.com/)以下载 Visual Studio 代码（如果尚未使用）。</span><span class="sxs-lookup"><span data-stu-id="03773-107">Head to [this page](https://code.visualstudio.com/) to download Visual Studio Code if you aren't using it yet.</span></span>

## <span data-ttu-id="03773-108">Extensions</span><span class="sxs-lookup"><span data-stu-id="03773-108">Extensions</span></span>

<!-- We want to put something like the tiles for extensions VS Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page. I think it's a web page. I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->

<span data-ttu-id="03773-109">若要获取下面突出显示的任何扩展，请导航到 VS 代码中的 "扩展" （ `Ctrl`  +  `Shift`  +  `X` 在 Windows 或 `Command`  +  `Shift`  +  `X` Mac 上）。</span><span class="sxs-lookup"><span data-stu-id="03773-109">To acquire any of the extensions highlighted below, navigate to Extensions (`Ctrl` + `Shift` + `X` on Windows or `Command` + `Shift` + `X` on Mac) in VS Code.</span></span>

<span data-ttu-id="03773-110">在市场中搜索特定的扩展，然后选择 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="03773-110">Search the Marketplace for the specific extension and select **Install**.</span></span>

![为 Microsoft Edge 和代码扩展安装调试器](./media/vscode-debugger-install.png)

## <span data-ttu-id="03773-112">Microsoft Edge 调试器</span><span class="sxs-lookup"><span data-stu-id="03773-112">Debugger for Microsoft Edge</span></span>

<span data-ttu-id="03773-113">`console.log()`使用[适用于 Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)和代码扩展的调试器直接在[Visual Studio 代码](https://code.visualstudio.com/)中使用 "逐行" 和 "显示语句" 调试你的前端 JavaScript 代码行！</span><span class="sxs-lookup"><span data-stu-id="03773-113">Debug your front-end JavaScript code line by line and display `console.log()` statements directly in [Visual Studio Code](https://code.visualstudio.com/) using the the [Debugger for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension!</span></span>

<span data-ttu-id="03773-114">使用[适用于 Microsoft edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS 代码扩展的调试器启动或附加到 microsoft Edge （EdgeHTML）和 microsoft Edge （Chromium）。</span><span class="sxs-lookup"><span data-stu-id="03773-114">Use the [Debugger for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension to launch or attach to both Microsoft Edge (EdgeHTML) and Microsoft Edge (Chromium).</span></span> <span data-ttu-id="03773-115">有关从 VS 代码调试 Microsoft Edge 和样例**启动**配置的演练，请查看[此页面](./debugger-for-edge.md)。</span><span class="sxs-lookup"><span data-stu-id="03773-115">Check out [this page](./debugger-for-edge.md) for a walkthrough of debugging Microsoft Edge from VS Code and sample **launch.json** configurations.</span></span>

![适用于操作中的边缘与代码扩展的调试器的 GIF！](./media/debugger-for-edge.gif)

## <span data-ttu-id="03773-117">Microsoft Edge 元素</span><span class="sxs-lookup"><span data-stu-id="03773-117">Elements for Microsoft Edge</span></span>

<span data-ttu-id="03773-118">通过添加[Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)与代码扩展的元素，可以从 Visual Studio 代码中使用浏览器的元素工具。</span><span class="sxs-lookup"><span data-stu-id="03773-118">By adding the [Elements for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools) VS Code extension, you can use the browser's Elements tool from within Visual Studio Code.</span></span> <span data-ttu-id="03773-119">通过启动或附加，元素工具将连接到 Microsoft Edge 实例，显示运行时 HTML 结构，并允许你更改布局或修复样式设置问题。</span><span class="sxs-lookup"><span data-stu-id="03773-119">By either launching or attaching, the Elements tool will connect to an instance of Microsoft Edge, display the runtime HTML structure, and allow you to alter the layout or fix styling issues.</span></span>

<span data-ttu-id="03773-120">有关详细信息，请查看[此页面](./elements-for-edge.md)。</span><span class="sxs-lookup"><span data-stu-id="03773-120">For more information, check out [this page](./elements-for-edge.md).</span></span>

![操作中的边缘与代码扩展的元素的 GIF！](./media/elements-for-edge.gif)

## <span data-ttu-id="03773-122">webhint</span><span class="sxs-lookup"><span data-stu-id="03773-122">webhint</span></span>

<span data-ttu-id="03773-123">使用[webhint](https://webhint.io)（一种可自定义的 linting 工具）来改进你的网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。</span><span class="sxs-lookup"><span data-stu-id="03773-123">Use [webhint](https://webhint.io), a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span> <span data-ttu-id="03773-124">它会检查代码的最佳做法和常见错误。</span><span class="sxs-lookup"><span data-stu-id="03773-124">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="03773-125">此开放源代码项目（最初由 Microsoft Edge 团队开发）现在是[OpenJS 基础](https://openjsf.org/)的一部分。</span><span class="sxs-lookup"><span data-stu-id="03773-125">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation](https://openjsf.org/).</span></span> <span data-ttu-id="03773-126">Microsoft Edge 团队继续参与社区中的 webhint 和 web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="03773-126">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>

![Webhint 与代码扩展的屏幕截图](./media/webhint-extension.png)

<span data-ttu-id="03773-128">通过添加[VS 代码的 webhint 扩展名](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint)，识别并修复 HTML、CSS、JavaScript、TypeScript 等中的问题。</span><span class="sxs-lookup"><span data-stu-id="03773-128">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint).</span></span> <span data-ttu-id="03773-129">提示显示为内联下划线，并在 "问题" 窗格中进行汇总。</span><span class="sxs-lookup"><span data-stu-id="03773-129">Hints appear as inline underlines and are summarized in the Problems pane.</span></span>

<span data-ttu-id="03773-130">有关详细信息，请参阅[如何在 Visual Studio 代码中使用 webhint](./webhint.md)。</span><span class="sxs-lookup"><span data-stu-id="03773-130">For more information, see [How to use webhint in Visual Studio Code](./webhint.md).</span></span>
