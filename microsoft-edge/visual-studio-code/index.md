---
description: Microsoft Edge (Chromium) 和 Visual Studio Code
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs code， visual studio code， 调试程序， webhint
ms.openlocfilehash: 1aa5b66043e87ebb0f1b848dcd60e2553b378f36
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230689"
---
# Visual Studio 代码概述  

[Visual Studio Code][VisualStudioCodeDocs]是一个轻型但功能强大的源代码编辑器。  [Visual Studio Code][VisualStudioCodeDocs]适用于 Windows、Linux 和 macOS。  它包括对 JavaScript、TypeScript 和 Node.js 的内置支持，因此在自定义之前，它是 Web 开发人员的一个很好的工具。  如果尚未使用它，[请下载][VisualstudioCode]Visual Studio Code。  

## Extensions  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

若要获取下面突出显示的任何扩展，请在 Windows/Linux 或 Visual Studio Code 中的 `Ctrl` + `Shift` + `X` `Command` + `Shift` + macOS\) 上导航到扩展 `X` \(选择。  

在 Marketplace 中搜索特定扩展，然后选择"安装 **"。**  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="安装调试器Microsoft Edge Visual Studio Code扩展" lightbox="./media/vscode-debugger-install.png":::
   安装**调试器Microsoft Edge Visual Studio Code**扩展  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="调试程序Microsoft Edge Visual Studio Code扩展" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         **调试程序Microsoft Edge Visual Studio Code**扩展  
      :::image-end:::  
      [调试程序Microsoft Edge](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Microsoft Edge扩展Visual Studio Code Visual Studio Code工具" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         **Microsoft Edge工具Visual Studio Code Visual Studio Code**扩展  
      :::image-end:::  
      [Microsoft Edge工具Visual Studio Code](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio Code扩展" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         **webhint** Visual Studio Code扩展  
      :::image-end:::  
      [webhint](#webhint)  
   :::column-end:::
:::row-end:::  

## 调试程序Microsoft Edge  

使用[调试器 for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code 扩展，可以分行调试前端 JavaScript 代码，并直接从 Visual Studio Code `console.log()` [查看语句][VisualstudioCode]。  
      
使用调试器工具，你可以启动或附加到 Microsoft Edge \(EdgeHTML\) 和 Microsoft Edge \(Chromium\) 。  有关从配置和示例配置Microsoft Edge调试Visual Studio Code演练，请导航到调试 `launch.json` 器 For Microsoft Edge Visual Studio Code [Extension][VisualStudioCodeDebuggerEdge]。  选择以下图像以查看扩展的操作。  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="适用于 Edge Visual Studio Code的调试器在操作中" lightbox="./media/debugger-for-edge.gif":::
   **调试器Microsoft Edge Visual Studio Code**扩展  
:::image-end:::  

## Microsoft Edge工具Visual Studio Code

使用[Microsoft Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio Code 扩展，请使用 Microsoft Edge**** 浏览器的 Elements Visual Studio Code。  用于以下操作。  

*   附加到实例或启动 Microsoft Edge。  
*   显示运行时 HTML 结构。  
*   更新布局。  
*   修复样式设置问题。  
    
有关详细信息，请导航到 Microsoft Edge [Tools for Visual Studio Code Visual Studio Code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Microsoft Edge适用于Visual Studio Code Visual Studio Code扩展的工具" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   **Microsoft Edge工具Visual Studio Code Visual Studio Code**扩展  
:::image-end:::  

## webhint  
      
使用 [Webhint（][WebhintMain]一个可自定义的 Lint 工具）可改进网站的以下功能。  

*   辅助功能
*   性能
*   跨浏览器兼容性
*   PWA兼容性
*   安全性

它会检查代码的编码实践和常见错误。 Webhint 开放源代码项目（最初由 Microsoft Edge 开发）现在是[OpenJS Foundation 的一部分][OpenjsFoundation]。  该Microsoft Edge团队将继续与社区中的 Web 开发人员一起为 webhint 做贡献。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint 扩展Visual Studio Code屏幕截图" lightbox="./media/webhint-extension.png":::
   **Webhint 扩展Visual Studio Code**屏幕截图  
:::image-end:::  
      
通过添加[webhint][VisualstudioMarketplaceWebhint]扩展以识别并修复网站中Visual Studio Code。  提示检查 HTML、CSS、JavaScript、TypeScript 等。  提示显示为内联下划线，并汇总在"问题 **"** 窗格中。  
      
有关详细信息，请导航到"如何使用[webhint Visual Studio Code"。][VisualStudioCodeWebhint]  

<!--links -->  

[VisualStudioCodeDebuggerEdge]: ./debugger-for-edge.md "调试程序Microsoft Edge Visual Studio Code扩展|Microsoft Docs"  
[VisualStudioCodeMicrosoftEdgeDevtoolsExtension]: ./microsoft-edge-devtools-extension.md "Microsoft Edge开发工具Visual Studio Code扩展|Microsoft Docs"  
[VisualStudioCodeWebhint]: ./webhint.md "Webhint Visual Studio Code Extension |Microsoft Docs"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio Code"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "调试程序Microsoft Edge |Visual StudioMarketplace"  
[VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual StudioMarketplace"  

[WebhintMain]:  https://webhint.io "webhint"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
