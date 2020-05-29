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
# Visual Studio Code

[Visual Studio 代码](https://code.visualstudio.com/Docs)是一个轻量级但功能强大的源代码编辑器，可在桌面上运行，并且适用于 Windows、MacOS 和 Linux。 它附带了针对 JavaScript、TypeScript 和 node.js 的内置支持，因此它是适用于现成的 web 开发人员的绝佳工具！ 转到[此页面](https://code.visualstudio.com/)以下载 Visual Studio 代码（如果尚未使用）。

## Extensions

<!-- We want to put something like the tiles for extensions VS Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page. I think it's a web page. I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->

若要获取下面突出显示的任何扩展，请导航到 VS 代码中的 "扩展" （ `Ctrl`  +  `Shift`  +  `X` 在 Windows 或 `Command`  +  `Shift`  +  `X` Mac 上）。

在市场中搜索特定的扩展，然后选择 "**安装**"。

![为 Microsoft Edge 和代码扩展安装调试器](./media/vscode-debugger-install.png)

## Microsoft Edge 调试器

`console.log()`使用[适用于 Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)和代码扩展的调试器直接在[Visual Studio 代码](https://code.visualstudio.com/)中使用 "逐行" 和 "显示语句" 调试你的前端 JavaScript 代码行！

使用[适用于 Microsoft edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS 代码扩展的调试器启动或附加到 microsoft Edge （EdgeHTML）和 microsoft Edge （Chromium）。 有关从 VS 代码调试 Microsoft Edge 和样例**启动**配置的演练，请查看[此页面](./debugger-for-edge.md)。

![适用于操作中的边缘与代码扩展的调试器的 GIF！](./media/debugger-for-edge.gif)

## Microsoft Edge 元素

通过添加[Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)与代码扩展的元素，可以从 Visual Studio 代码中使用浏览器的元素工具。 通过启动或附加，元素工具将连接到 Microsoft Edge 实例，显示运行时 HTML 结构，并允许你更改布局或修复样式设置问题。

有关详细信息，请查看[此页面](./elements-for-edge.md)。

![操作中的边缘与代码扩展的元素的 GIF！](./media/elements-for-edge.gif)

## webhint

使用[webhint](https://webhint.io)（一种可自定义的 linting 工具）来改进你的网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。 它会检查代码的最佳做法和常见错误。 此开放源代码项目（最初由 Microsoft Edge 团队开发）现在是[OpenJS 基础](https://openjsf.org/)的一部分。 Microsoft Edge 团队继续参与社区中的 webhint 和 web 开发人员。

![Webhint 与代码扩展的屏幕截图](./media/webhint-extension.png)

通过添加[VS 代码的 webhint 扩展名](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint)，识别并修复 HTML、CSS、JavaScript、TypeScript 等中的问题。 提示显示为内联下划线，并在 "问题" 窗格中进行汇总。

有关详细信息，请参阅[如何在 Visual Studio 代码中使用 webhint](./webhint.md)。
