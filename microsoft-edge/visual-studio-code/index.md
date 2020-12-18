---
description: Microsoft Edge (Chromium) 和 Visual Studio Code
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， web development， f12 tools， devtools， vs code， visual studio code， debugger， webhint
ms.openlocfilehash: 1aa5b66043e87ebb0f1b848dcd60e2553b378f36
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230689"
---
# Visual Studio 代码概述  

[Visual Studio代码][VisualStudioCodeDocs] 是一个轻型但功能强大的源代码编辑器。  [Visual Studio适用于][VisualStudioCodeDocs] Windows、Linux 和 macOS。  它包括对 JavaScript、TypeScript 和 Node.js 的内置支持，因此它是 Web 开发人员在自定义之前的重要工具。  如果尚未使用它，请下载Visual Studio [代码][VisualstudioCode]。  

## Extensions  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

若要获取下面突出显示的任何扩展，请导航到"扩展"\ (在 `Ctrl` + `Shift` + `X` Windows/Linux 或 `Command` + `Shift` + `X` macOS\) "Visual Studio选择。  

在 Marketplace 中搜索特定扩展，然后选择"**安装"。**  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="安装适用于 Microsoft Edge 的调试器Visual Studio代码扩展" lightbox="./media/vscode-debugger-install.png":::
   安装 **适用于 Microsoft Edge 的调试** 器Visual Studio代码扩展  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="适用于 Microsoft Edge Visual Studio代码扩展的调试程序" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         **适用于 Microsoft Edge 的调试器** Visual Studio代码扩展  
      :::image-end:::  
      [适用于 Microsoft Edge 的调试器](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         **Microsoft Edge Tools for Visual Studio Code** Visual Studio代码扩展  
      :::image-end:::  
      [Microsoft Edge Tools for Visual Studio Code](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio代码扩展" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         **webhint** Visual Studio代码扩展  
      :::image-end:::  
      [webhint](#webhint)  
   :::column-end:::
:::row-end:::  

## 适用于 Microsoft Edge 的调试器  

使用 [调试器 for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio 代码扩展，分行调试前端 JavaScript 代码，并直接从 Visual Studio `console.log()` [代码查看语句][VisualstudioCode]。  
      
使用调试器工具，你可以启动或连接到 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 。  有关从代码和示例配置Visual Studio Microsoft Edge 的演练，请导航到调试器 For Microsoft Edge Visual Studio `launch.json` [代码扩展][VisualStudioCodeDebuggerEdge]。  选择下图以查看扩展的可操作性。  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="运行中的边缘Visual Studio代码扩展的调试程序" lightbox="./media/debugger-for-edge.gif":::
   **适用于 Microsoft Edge 的调试器** Visual Studio代码扩展操作  
:::image-end:::  

## Microsoft Edge Tools for Visual Studio Code

借助[Microsoft Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio扩展，请使用 Microsoft **** Edge 浏览器的 Elements 工具，Visual Studio代码。  用于以下操作。  

*   附加到实例或启动 Microsoft Edge 的实例。  
*   显示运行时 HTML 结构。  
*   更新布局。  
*   修复样式设置问题。  
    
有关详细信息，请导航到 [Microsoft Edge Tools for Visual Studio Code Visual Studio 扩展][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension in action" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   **Microsoft Edge Tools for Visual Studio Code** Visual Studio代码扩展操作  
:::image-end:::  

## webhint  
      
使用 [Webhint（][WebhintMain]一个可自定义的 linting 工具）可改进网站的以下功能。  

*   辅助功能
*   性能
*   跨浏览器兼容性
*   PWA 兼容性
*   安全性

它会检查代码的编码实践和常见错误。 最初由 Microsoft Edge 团队开发的 Webhint 开放源代码项目现在是 [OpenJS Foundation][OpenjsFoundation]的一部分。  Microsoft Edge 团队将继续与社区中的 Web 开发人员一起为 WebHint 做贡献。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint Visual Studio代码扩展的屏幕截图" lightbox="./media/webhint-extension.png":::
   **Webhint 代码扩展**Visual Studio屏幕截图  
:::image-end:::  
      
通过添加 Webhint 扩展以识别并修复网站中 [的问题Visual Studio代码][VisualstudioMarketplaceWebhint]。  提示检查 HTML、CSS、JavaScript、TypeScript 等。  提示显示为内联下划线，并汇总在"问题 **"** 窗格中。  
      
有关详细信息，请导航到 [如何使用 Webhint 在Visual Studio代码][VisualStudioCodeWebhint]。  

<!--links -->  

[VisualStudioCodeDebuggerEdge]: ./debugger-for-edge.md "适用于 Microsoft Edge 的调试Visual Studio代码扩展 |Microsoft Docs"  
[VisualStudioCodeMicrosoftEdgeDevtoolsExtension]: ./microsoft-edge-devtools-extension.md "Microsoft Edge DevTools for Visual Studio Code extension |Microsoft Docs"  
[VisualStudioCodeWebhint]: ./webhint.md "Webhint Visual Studio代码扩展 |Microsoft Docs"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio代码"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "适用于 Microsoft Edge 的调试器 |Visual Studio市场"  
[VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio市场"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio市场"  

[WebhintMain]:  https://webhint.io "webhint"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
