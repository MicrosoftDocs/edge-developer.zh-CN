---
description: Microsoft Edge (Chromium) 和 Visual Studio 代码
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、调试程序、webhint
ms.openlocfilehash: e178612d9db8ce3223bb5158c4557675d3314e15
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695875"
---
# Visual Studio Code  

[Visual Studio 代码][VisualStudioCodeDocs] 是一种轻量级但功能强大的源代码编辑器，可在桌面上运行，并且适用于 Windows、MacOS 和 Linux。  它附带了针对 JavaScript、TypeScript 和 Node.js 的内置支持，因此它是适用于现成的 web 开发人员的绝佳工具！  如果尚未使用它，请下载 [Visual Studio 代码][VisualstudioCode]。  

## Extensions  

<!--Todo: We want to put something like the tiles for extensions VS Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

若要获取下面突出显示的任何扩展，请导航到 Windows 上的 "扩展 \ (`Ctrl` + `Shift` + `X` " 或 `Command` + `Shift` + `X` "在 VS 代码中 macOS \ ) "。  

在市场中搜索特定的扩展，然后选择 " **安装**"。  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="为 Microsoft Edge 和代码扩展安装调试器":::
   为 Microsoft Edge 和代码扩展安装调试器  
:::image-end:::  

:::row:::
   :::column span="1":::
      ### Microsoft Edge 调试器  

      通过 [适用于 Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] 与代码扩展的调试器，通过逐行调试你的前端 JavaScript 代码并 `console.log()` 直接从 [Visual Studio 代码][VisualstudioCode]中查看语句！  
      
      使用调试器工具，你可以启动或附加到 Microsoft Edge \ (EdgeHTML \ ) 和 Microsoft Edge \ (Chromium \ ) 。  有关从 VS 代码和示例配置调试 Microsoft Edge 的演练 `launch.json` ，请参阅 [调试器 For MICROSOFT Edge VS 代码扩展][VscodeDebuggerEdge]。  选择下图以查看操作扩展。  

      :::image type="content" source="./media/debugger-for-edge.png" alt-text="为 Microsoft Edge 和代码扩展安装调试器" lightbox="./media/debugger-for-edge.gif":::  
   :::column-end:::
   :::column span="1":::
      ### Microsoft Edge 元素  
      
      使用 [Microsoft edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] 和代码扩展的元素，在 Visual Studio 代码中使用 microsoft edge 浏览器的 "元素" 工具。  通过启动或附加，元素工具连接到 Microsoft Edge 实例，显示运行时 HTML 结构，并允许你更改布局或修复样式设置问题。  
      
      有关详细信息，请参阅 [Microsoft EDGE 和代码扩展的元素][VscodeElementsEdge]。  选择下图以查看操作扩展。  
      
      :::image type="content" source="./media/elements-for-edge.png" alt-text="为 Microsoft Edge 和代码扩展安装调试器" lightbox="./media/elements-for-edge.gif":::  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      ### webhint
      
      使用 [webhint][WebhintMain]（一种可自定义的 linting 工具）来改进你的网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。  它会检查代码的最佳做法和常见错误。 Webhint 最初由 Microsoft Edge 团队开发的 "开放源代码" 项目现在是 [OpenJS Foundation][OpenjsFoundation]的一部分。  Microsoft Edge 团队继续参与社区中的 webhint 和 web 开发人员。  <!--Select the following image to see the extension in action.  -->  
      
      :::image type="content" source="./media/webhint-extension.png" alt-text="为 Microsoft Edge 和代码扩展安装调试器" lightbox="./media/webhint-extension.png":::  
      
      通过添加 [VS 代码的 webhint 扩展名][VisualstudioMarketplaceWebhint]，识别并修复 HTML、CSS、JavaScript、TypeScript 等中的问题。  提示显示为内联下划线，并在 " **问题** " 窗格中进行汇总。  
      
      有关详细信息，请参阅 [如何在 Visual Studio 代码中使用 webhint][VscodeWebhint]。  
   :::column-end:::
   :::column span="1":::
      <!--Empty to retain grid  -->  
   :::column-end:::
:::row-end:::

<!-- image links -->  

<!--links -->  

[VscodeDebuggerEdge]: ./debugger-for-edge.md "Microsoft Edge 调试程序与代码扩展 |Microsoft 文档"  
[VscodeElementsEdge]: ./elements-for-edge.md "Microsoft Edge 与代码扩展的元素 |Microsoft 文档"  
[VscodeWebhint]: ./webhint.md "Webhint 与代码扩展 |Microsoft 文档"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 的调试器 |Visual Studio Marketplace"  
[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge 的元素 (Chromium) |Visual Studio Marketplace"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio Marketplace"  

[WebhintMain]:  https://webhint.io "webhint"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
