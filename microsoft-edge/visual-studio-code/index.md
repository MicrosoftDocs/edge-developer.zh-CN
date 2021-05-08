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
# <span data-ttu-id="49a4a-104">Visual Studio 代码概述</span><span class="sxs-lookup"><span data-stu-id="49a4a-104">Visual Studio Code overview</span></span>  

<span data-ttu-id="49a4a-105">[Visual Studio Code][VisualStudioCodeDocs]是一个轻型但功能强大的源代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="49a4a-105">[Visual Studio Code][VisualStudioCodeDocs] is a lightweight, but powerful source code editor.</span></span>  <span data-ttu-id="49a4a-106">[Visual Studio Code][VisualStudioCodeDocs]适用于 Windows、Linux 和 macOS。</span><span class="sxs-lookup"><span data-stu-id="49a4a-106">[Visual Studio Code][VisualStudioCodeDocs] is available for Windows, Linux, and macOS.</span></span>  <span data-ttu-id="49a4a-107">它包括对 JavaScript、TypeScript 和 Node.js 的内置支持，因此在自定义之前，它是 Web 开发人员的一个很好的工具。</span><span class="sxs-lookup"><span data-stu-id="49a4a-107">It includes built-in support for JavaScript, TypeScript, and Node.js, so it is a great tool for web developers before you customize it.</span></span>  <span data-ttu-id="49a4a-108">如果尚未使用它，[请下载][VisualstudioCode]Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="49a4a-108">If you are not using it yet, download [Visual Studio Code][VisualstudioCode].</span></span>  

## <span data-ttu-id="49a4a-109">Extensions</span><span class="sxs-lookup"><span data-stu-id="49a4a-109">Extensions</span></span>  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

<span data-ttu-id="49a4a-110">若要获取下面突出显示的任何扩展，请在 Windows/Linux 或 Visual Studio Code 中的 `Ctrl` + `Shift` + `X` `Command` + `Shift` + macOS\) 上导航到扩展 `X` \ (选择。</span><span class="sxs-lookup"><span data-stu-id="49a4a-110">To acquire any of the extensions highlighted below, navigate to Extensions \(select `Ctrl`+`Shift`+`X` on Windows/Linux or `Command`+`Shift`+`X` on macOS\) in Visual Studio Code.</span></span>  

<span data-ttu-id="49a4a-111">在 Marketplace 中搜索特定扩展，然后选择"安装 **"。**</span><span class="sxs-lookup"><span data-stu-id="49a4a-111">Search the Marketplace for the specific extension and choose **Install**.</span></span>  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="安装调试器Microsoft Edge Visual Studio Code扩展" lightbox="./media/vscode-debugger-install.png":::
   <span data-ttu-id="49a4a-113">安装**调试器Microsoft Edge Visual Studio Code**扩展</span><span class="sxs-lookup"><span data-stu-id="49a4a-113">Install the **Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="调试程序Microsoft Edge Visual Studio Code扩展" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         <span data-ttu-id="49a4a-115">**调试程序Microsoft Edge Visual Studio Code**扩展</span><span class="sxs-lookup"><span data-stu-id="49a4a-115">**Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="49a4a-116">调试程序Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49a4a-116">Debugger for Microsoft Edge</span></span>](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Microsoft Edge扩展Visual Studio Code Visual Studio Code工具" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         <span data-ttu-id="49a4a-118">**Microsoft Edge工具Visual Studio Code Visual Studio Code**扩展</span><span class="sxs-lookup"><span data-stu-id="49a4a-118">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="49a4a-119">Microsoft Edge工具Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="49a4a-119">Microsoft Edge Tools for Visual Studio Code</span></span>](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio Code扩展" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         <span data-ttu-id="49a4a-121">**webhint** Visual Studio Code扩展</span><span class="sxs-lookup"><span data-stu-id="49a4a-121">**webhint** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="49a4a-122">webhint</span><span class="sxs-lookup"><span data-stu-id="49a4a-122">webhint</span></span>](#webhint)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="49a4a-123">调试程序Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49a4a-123">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="49a4a-124">使用[调试器 for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code 扩展，可以分行调试前端 JavaScript 代码，并直接从 Visual Studio Code `console.log()` [查看语句][VisualstudioCode]。</span><span class="sxs-lookup"><span data-stu-id="49a4a-124">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line-by-line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode].</span></span>  
      
<span data-ttu-id="49a4a-125">使用调试器工具，你可以启动或附加到 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="49a4a-125">Using the Debugger tool, you may launch or attach to both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="49a4a-126">有关从配置和示例配置Microsoft Edge调试Visual Studio Code演练，请导航到调试 `launch.json` 器 For Microsoft Edge Visual Studio Code [Extension][VisualStudioCodeDebuggerEdge]。</span><span class="sxs-lookup"><span data-stu-id="49a4a-126">For a walkthrough of debugging Microsoft Edge from Visual Studio Code and sample `launch.json` configurations, navigate to [Debugger For Microsoft Edge Visual Studio Code Extension][VisualStudioCodeDebuggerEdge].</span></span>  <span data-ttu-id="49a4a-127">选择以下图像以查看扩展的操作。</span><span class="sxs-lookup"><span data-stu-id="49a4a-127">Choose the following image to see the extension in action.</span></span>  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="适用于 Edge Visual Studio Code的调试器在操作中" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="49a4a-129">**调试器Microsoft Edge Visual Studio Code**扩展</span><span class="sxs-lookup"><span data-stu-id="49a4a-129">**Debugger for Microsoft Edge** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="49a4a-130">Microsoft Edge工具Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="49a4a-130">Microsoft Edge Tools for Visual Studio Code</span></span>

<span data-ttu-id="49a4a-131">使用[Microsoft Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio Code 扩展，请使用 Microsoft Edge\*\*\*\* 浏览器的 Elements Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="49a4a-131">With the [Microsoft Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio Code extension, use the **Elements** tool of the Microsoft Edge browser within Visual Studio Code.</span></span>  <span data-ttu-id="49a4a-132">用于以下操作。</span><span class="sxs-lookup"><span data-stu-id="49a4a-132">Use it for the following actions.</span></span>  

*   <span data-ttu-id="49a4a-133">附加到实例或启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="49a4a-133">Attach to an instance or launch an instance of Microsoft Edge.</span></span>  
*   <span data-ttu-id="49a4a-134">显示运行时 HTML 结构。</span><span class="sxs-lookup"><span data-stu-id="49a4a-134">Display the runtime HTML structure.</span></span>  
*   <span data-ttu-id="49a4a-135">更新布局。</span><span class="sxs-lookup"><span data-stu-id="49a4a-135">Update the layout.</span></span>  
*   <span data-ttu-id="49a4a-136">修复样式设置问题。</span><span class="sxs-lookup"><span data-stu-id="49a4a-136">Fix styling issues.</span></span>  
    
<span data-ttu-id="49a4a-137">有关详细信息，请导航到 Microsoft Edge [Tools for Visual Studio Code Visual Studio Code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]。</span><span class="sxs-lookup"><span data-stu-id="49a4a-137">For more information, navigate to [Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension].</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Microsoft Edge适用于Visual Studio Code Visual Studio Code扩展的工具" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   <span data-ttu-id="49a4a-139">**Microsoft Edge工具Visual Studio Code Visual Studio Code**扩展</span><span class="sxs-lookup"><span data-stu-id="49a4a-139">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="49a4a-140">webhint</span><span class="sxs-lookup"><span data-stu-id="49a4a-140">webhint</span></span>  
      
<span data-ttu-id="49a4a-141">使用 [Webhint（][WebhintMain]一个可自定义的 Lint 工具）可改进网站的以下功能。</span><span class="sxs-lookup"><span data-stu-id="49a4a-141">Use [webhint][WebhintMain], a customizable linting tool, to improve the following functionality of your site.</span></span>  

*   <span data-ttu-id="49a4a-142">辅助功能</span><span class="sxs-lookup"><span data-stu-id="49a4a-142">Accessibility</span></span>
*   <span data-ttu-id="49a4a-143">性能</span><span class="sxs-lookup"><span data-stu-id="49a4a-143">Performance</span></span>
*   <span data-ttu-id="49a4a-144">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="49a4a-144">Cross-browser compatibility</span></span>
*   <span data-ttu-id="49a4a-145">PWA兼容性</span><span class="sxs-lookup"><span data-stu-id="49a4a-145">PWA compatibility</span></span>
*   <span data-ttu-id="49a4a-146">安全性</span><span class="sxs-lookup"><span data-stu-id="49a4a-146">Security</span></span>

<span data-ttu-id="49a4a-147">它会检查代码的编码实践和常见错误。</span><span class="sxs-lookup"><span data-stu-id="49a4a-147">It checks your code for coding practices and common errors.</span></span> <span data-ttu-id="49a4a-148">Webhint 开放源代码项目（最初由 Microsoft Edge 开发）现在是[OpenJS Foundation 的一部分][OpenjsFoundation]。</span><span class="sxs-lookup"><span data-stu-id="49a4a-148">The webhint open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="49a4a-149">该Microsoft Edge团队将继续与社区中的 Web 开发人员一起为 webhint 做贡献。</span><span class="sxs-lookup"><span data-stu-id="49a4a-149">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint 扩展Visual Studio Code屏幕截图" lightbox="./media/webhint-extension.png":::
   <span data-ttu-id="49a4a-151">**Webhint 扩展Visual Studio Code**屏幕截图</span><span class="sxs-lookup"><span data-stu-id="49a4a-151">Screenshot of **webhint** Visual Studio Code extension</span></span>  
:::image-end:::  
      
<span data-ttu-id="49a4a-152">通过添加[webhint][VisualstudioMarketplaceWebhint]扩展以识别并修复网站中Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="49a4a-152">Identify and fix problems in your website by adding the [webhint extension for Visual Studio Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="49a4a-153">提示检查 HTML、CSS、JavaScript、TypeScript 等。</span><span class="sxs-lookup"><span data-stu-id="49a4a-153">Hints examine HTML, CSS, JavaScript, TypeScript, and more.</span></span>  <span data-ttu-id="49a4a-154">提示显示为内联下划线，并汇总在"问题 **"** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="49a4a-154">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  
      
<span data-ttu-id="49a4a-155">有关详细信息，请导航到"如何使用[webhint Visual Studio Code"。][VisualStudioCodeWebhint]</span><span class="sxs-lookup"><span data-stu-id="49a4a-155">For more information, navigate to [How to use webhint in Visual Studio Code][VisualStudioCodeWebhint].</span></span>  

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
