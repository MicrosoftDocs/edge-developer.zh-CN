---
description: Microsoft Edge (Chromium) 和 Visual Studio 代码
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、调试程序、webhint
ms.openlocfilehash: 0d13c6eb9411f89e3a681176ade0caf8d59d46d8
ms.sourcegitcommit: 02c602379537ab3b9d0a355cea7fcf96fdbd8870
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "11182730"
---
# Visual Studio Code  

[Visual Studio 代码][VisualStudioCodeDocs] 是一种轻量级但功能强大的源代码编辑器。  [Visual Studio 代码][VisualStudioCodeDocs] 适用于 Windows、Linux 和 macOS。  它包括对 JavaScript、TypeScript 和 Node.js 的内置支持，因此它是用于自定义 web 开发人员的一个非常好的工具。  如果尚未使用它，请下载 [Visual Studio 代码][VisualstudioCode]。  

## Extensions  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

若要获取下面突出显示的任何扩展，请导航到 "扩展 \ (在 `Ctrl` + `Shift` + `X` Windows/Linux 上选择" 或 `Command` + `Shift` + `X` "在 Visual Studio 代码中 macOS \ ) 上选择"。  

搜索特定扩展的市场，然后选择 " **安装**"。  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="为 Microsoft Edge Visual Studio 代码扩展安装调试器" lightbox="./media/vscode-debugger-install.png":::
   **为 Microsoft Edge** Visual Studio 代码扩展安装调试器  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="Microsoft Edge Visual Studio 代码扩展的调试器" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         **Microsoft Edge 调试器** Visual Studio 代码扩展  
      :::image-end:::  
      [Microsoft Edge 调试器](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="适用于 Visual Studio 代码 Visual Studio 代码扩展的 Microsoft Edge 工具" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         **适用于 Visual Studio 代码的 Microsoft Edge 工具** Visual Studio 代码扩展  
      :::image-end:::  
      [适用于 Visual Studio 代码的 Microsoft Edge 工具](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio 代码扩展" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         **webhint** Visual Studio 代码扩展  
      :::image-end:::  
      [webhint](#webhint)  
   :::column-end:::
:::row-end:::  

## Microsoft Edge 调试器  

借助 [适用于 Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio 代码扩展的调试器，逐行调试你的前端 JavaScript 代码并 `console.log()` 直接从 [Visual Studio 代码][VisualstudioCode]中查看语句。  
      
使用调试器工具，你可以启动或附加到 Microsoft Edge \ (EdgeHTML \ ) 和 Microsoft Edge \ (Chromium \ ) 。  有关从 Visual Studio 代码和示例配置调试 Microsoft Edge 的演练 `launch.json` ，请导航到 [Microsoft Edge Visual Studio 代码扩展][VisualStudioCodeDebuggerEdge]的 "调试器"。  选择下图以查看操作扩展。  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="操作中的边缘 Visual Studio 代码扩展的调试程序" lightbox="./media/debugger-for-edge.gif":::
   **Microsoft Edge 调试器** 操作中的 Visual Studio 代码扩展  
:::image-end:::  

## 适用于 Visual Studio 代码的 Microsoft Edge 工具

使用 [Microsoft Edge Tools For Visual Studio 代码][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual studio 代码扩展，使用 microsoft edge 浏览器的 " **元素** " 工具在 visual studio 代码中。  将其用于以下操作。  

*   附加到实例或启动 Microsoft Edge 实例。  
*   显示运行时 HTML 结构。  
*   更新布局。  
*   修复样式设置问题。  
    
有关详细信息，请导航到 [Microsoft Edge Tools For Visual Studio Code Visual studio 代码扩展][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="适用于 Visual Studio 代码 Visual Studio 代码扩展的 Microsoft Edge 工具操作" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   **适用于 Visual Studio 代码的 Microsoft Edge 工具** 操作中的 Visual Studio 代码扩展  
:::image-end:::  

## webhint  
      
使用 [webhint][WebhintMain]（一种可自定义的 linting 工具）来改进网站的以下功能。  

*   辅助功能
*   性能
*   跨浏览器兼容性
*   PWA 兼容性
*   安全性

它会检查代码的编码做法和常见错误。 Webhint 最初由 Microsoft Edge 团队开发的 "开放源代码" 项目现在是 [OpenJS Foundation][OpenjsFoundation]的一部分。  Microsoft Edge 团队继续参与社区中的 webhint 和 web 开发人员。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint Visual Studio 代码扩展的屏幕截图" lightbox="./media/webhint-extension.png":::
   **Webhint** Visual Studio 代码扩展的屏幕截图  
:::image-end:::  
      
通过 [为 Visual Studio 代码添加 webhint 扩展][VisualstudioMarketplaceWebhint]，识别并解决你的网站中的问题。  提示检查 HTML、CSS、JavaScript、TypeScript 等。  提示显示为内联下划线，并在 " **问题** " 窗格中进行汇总。  
      
有关详细信息，请导航到 [如何在 Visual Studio 代码中使用 webhint][VisualStudioCodeWebhint]。  

<!--links -->  

[VisualStudioCodeDebuggerEdge]: ./debugger-for-edge.md "Microsoft Edge Visual Studio 代码扩展的调试器 |Microsoft 文档"  
[VisualStudioCodeMicrosoftEdgeDevtoolsExtension]: ./microsoft-edge-devtools-extension.md "适用于 Visual Studio 代码扩展的 Microsoft Edge DevTools |Microsoft 文档"  
[VisualStudioCodeWebhint]: ./webhint.md "Webhint Visual Studio 代码扩展 |Microsoft 文档"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 的调试器 |Visual Studio Marketplace"  
[VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "适用于 Visual Studio 代码的 Microsoft Edge 工具 |Visual Studio Marketplace"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio Marketplace"  

[WebhintMain]:  https://webhint.io "webhint"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
