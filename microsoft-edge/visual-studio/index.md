---
description: Microsoft Edge (Chromium) 和 Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/18/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs， visual studio， 调试器
ms.openlocfilehash: 562952ef238c05922e468501706ab75e1976273d
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387270"
---
# <a name="visual-studio"></a><span data-ttu-id="84fc4-104">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-104">Visual Studio</span></span>  

<span data-ttu-id="84fc4-105">Microsoft [Visual Studio][MicrosoftVisualstudioVs] 是一个集成开发环境 \ (IDE\) 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-105">Microsoft [Visual Studio][MicrosoftVisualstudioVs] is an integrated development environment \(IDE\).</span></span>   <span data-ttu-id="84fc4-106">使用它来编辑、调试、生成和发布 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="84fc4-106">Use it to edit, debug, build, and publish your web apps.</span></span>  <span data-ttu-id="84fc4-107">它是一个功能丰富的程序，可用于 Web 开发的许多方面。</span><span class="sxs-lookup"><span data-stu-id="84fc4-107">It is a feature-rich program that may be used for many aspects of your web development.</span></span>  <span data-ttu-id="84fc4-108">在大多数 IDEs 提供的标准编辑器和调试器之上，Visual Studio以下功能以便于开发过程。</span><span class="sxs-lookup"><span data-stu-id="84fc4-108">Over and above the standard editor and debugger that most IDEs provide, Visual Studio includes the following features to ease your development process.</span></span>  

*   <span data-ttu-id="84fc4-109">编译器</span><span class="sxs-lookup"><span data-stu-id="84fc4-109">compilers</span></span>  
*   <span data-ttu-id="84fc4-110">代码完成工具</span><span class="sxs-lookup"><span data-stu-id="84fc4-110">code completion tools</span></span>  
*   <span data-ttu-id="84fc4-111">图形设计器</span><span class="sxs-lookup"><span data-stu-id="84fc4-111">graphical designers</span></span>  
*   <span data-ttu-id="84fc4-112">更多</span><span class="sxs-lookup"><span data-stu-id="84fc4-112">many more</span></span>  
    
<span data-ttu-id="84fc4-113">如果您尚未使用 Visual Studio，请导航到" [下载Visual Studio][MicrosoftVisualstudioDownloads] 下载它。</span><span class="sxs-lookup"><span data-stu-id="84fc4-113">If you are not already using Visual Studio, navigate to [Download Visual Studio][MicrosoftVisualstudioDownloads] to download it.</span></span>  

<span data-ttu-id="84fc4-114">目前，Visual Studio 2019 支持在 Microsoft Edge 中为 ASP.NET Framework 和 ASP.NET Core 应用调试 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="84fc4-114">Currently, Visual Studio 2019 supports debugging JavaScript in Microsoft Edge for your ASP.NET Framework and ASP.NET Core apps.</span></span>  <span data-ttu-id="84fc4-115">完成以下步骤以使用 Visual Studio调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="84fc4-115">Complete the following steps to use Visual Studio to debug Microsoft Edge.</span></span>  

## <a name="launch-microsoft-edge"></a><span data-ttu-id="84fc4-116">启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="84fc4-116">Launch Microsoft Edge</span></span>  

<span data-ttu-id="84fc4-117">Visual Studio单个按钮完成以下工作流。</span><span class="sxs-lookup"><span data-stu-id="84fc4-117">Visual Studio completes the following workflow using a single button.</span></span>  

1.  <span data-ttu-id="84fc4-118">生成你的 ASP.NET ASP.NET 核心应用。</span><span class="sxs-lookup"><span data-stu-id="84fc4-118">Builds your ASP.NET and ASP.NET Core app.</span></span>  
1.  <span data-ttu-id="84fc4-119">启动 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="84fc4-119">Starts your web server.</span></span>  
1.  <span data-ttu-id="84fc4-120">启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="84fc4-120">Launches Microsoft Edge.</span></span>  
1.  <span data-ttu-id="84fc4-121">连接Visual Studio调试器。</span><span class="sxs-lookup"><span data-stu-id="84fc4-121">Connects the Visual Studio debugger.</span></span>  
    
<span data-ttu-id="84fc4-122">通过简化的工作流，您可以直接从 IDE 调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="84fc4-122">The simplified workflow allows you to debug JavaScript that run in Microsoft Edge directly from your IDE.</span></span>  

### <a name="create-a-new-aspnet-core-web-app"></a><span data-ttu-id="84fc4-123">创建新的核心 ASP.NET Web 应用</span><span class="sxs-lookup"><span data-stu-id="84fc4-123">Create a new ASP.NET Core web app</span></span>  

<span data-ttu-id="84fc4-124">Open Visual Studio 2019 and choose **Create a new project**.</span><span class="sxs-lookup"><span data-stu-id="84fc4-124">Open Visual Studio 2019 and choose **Create a new project**.</span></span>  <span data-ttu-id="84fc4-125">On the next screen， choose **ASP.NET Core Web app**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="84fc4-125">On the next screen, choose **ASP.NET Core Web app** > **Next**.</span></span>  

:::image type="complex" source="./media/create-new-project.png" alt-text="创建新的核心 ASP.NET Web 应用" lightbox="./media/create-new-project.png":::
   <span data-ttu-id="84fc4-127">创建新的核心 ASP.NET Web 应用</span><span class="sxs-lookup"><span data-stu-id="84fc4-127">Create a new ASP.NET Core Web app</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-128">为新项目**提供**项目名称，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="84fc4-128">Provide a **Project name** for your new project and choose **Create**.</span></span>  <span data-ttu-id="84fc4-129">对于此示例，选择"React.js模板"，\*\*\*\* 然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="84fc4-129">For the purposes of the example, choose **React.js** as the template, and choose **Create**.</span></span>  <span data-ttu-id="84fc4-130">React.js\*\* 模板 \*\* 指定如何将React.js与 ASP.NET Core 应用集成。</span><span class="sxs-lookup"><span data-stu-id="84fc4-130">The **React.js** template specifies how to integrate React.js with an ASP.NET Core app.</span></span>  

### <a name="launch-microsoft-edge-from-visual-studio"></a><span data-ttu-id="84fc4-131">从 Microsoft Edge Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-131">Launch Microsoft Edge from Visual Studio</span></span>  

<span data-ttu-id="84fc4-132">创建项目后，打开 `ClientApp/src/components/Counter.js` 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-132">After you create your project, open `ClientApp/src/components/Counter.js`.</span></span>  <span data-ttu-id="84fc4-133">现在，若要Visual Studio JavaScript，请选择绿色"播放"按钮和\*\*IIS Express\*\*\*\*\*\* 旁边的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="84fc4-133">Now, to use Visual Studio to debug JavaScript, choose the dropdown next to the green **Play** button and **IIS Express**.</span></span>  

:::image type="complex" source="./media/vs-dropdown.png" alt-text="绿色"播放"按钮和 IIS Express 旁边的下拉列表" lightbox="./media/vs-dropdown.png":::
   <span data-ttu-id="84fc4-135">绿色"播放"**按钮和\*\*\*\*IIS Express 旁边的下拉列表**</span><span class="sxs-lookup"><span data-stu-id="84fc4-135">The dropdown next to the green **Play** button and **IIS Express**</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-136">选择 **"启用脚本调试**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="84fc4-136">Choose **Script Debugging** > **Enabled**.</span></span>  

:::image type="complex" source="./media/enable-script-debugging.png" alt-text="在脚本调试中Visual Studio" lightbox="./media/enable-script-debugging.png":::
   <span data-ttu-id="84fc4-138">在脚本调试中Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-138">Turn on script debugging in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-139">在同一个下拉列表中，>\*\*\*\* 想要启动的 Microsoft Visual Studio Edge 预览频道（如 Microsoft Edge Canary、Dev 或 Beta）中的"Web 浏览器"。</span><span class="sxs-lookup"><span data-stu-id="84fc4-139">In the same dropdown, choose **Web Browser** > the preview channel of Microsoft Edge that you want Visual Studio to launch, such as Microsoft Edge Canary, Dev, or Beta.</span></span>  <span data-ttu-id="84fc4-140">如果你尚未使用 Microsoft Edge 预览频道之一，请导航到下载 [Microsoft Edge 预览体验][MicrosoftedgeinsiderDownload] 成员频道以下载一个。</span><span class="sxs-lookup"><span data-stu-id="84fc4-140">If you are not already using one of the Microsoft Edge preview channels, navigate to [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload] to download one.</span></span>  

:::image type="complex" source="./media/set-web-browser.png" alt-text="选择要启动的 Microsoft Edge Visual Studio频道" lightbox="./media/set-web-browser.png":::
   <span data-ttu-id="84fc4-142">选择要启动的 Microsoft Edge Visual Studio频道</span><span class="sxs-lookup"><span data-stu-id="84fc4-142">Choose the preview channel of Microsoft Edge that you want Visual Studio to launch</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="84fc4-143">如果选择 Microsoft Edge \ (EdgeHTML\) ，Visual Studio启动它，而不是 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-143">If you choose Microsoft Edge \(EdgeHTML\), Visual Studio launches it instead of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="84fc4-144">安装[Microsoft Edge][MicrosoftedgeinsiderDownload]的预览频道之一，或确保计算机上安装的 Microsoft Edge 版本是 Microsoft Edge \ (Chromium\) 而不是 Microsoft Edge \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-144">[Install the one of the preview channels of Microsoft Edge][MicrosoftedgeinsiderDownload] or ensure that the version of Microsoft Edge installed on your machine is Microsoft Edge \(Chromium\) and not Microsoft Edge \(EdgeHTML\).</span></span>  

<span data-ttu-id="84fc4-145">现在，Visual Studio配置正确，选择绿色 **"播放"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="84fc4-145">Now that Visual Studio is correctly configured, choose the green **Play** button.</span></span>  <span data-ttu-id="84fc4-146">Visual Studio生成应用、启动 Web 服务器、启动 Microsoft Edge，然后导航到 或在 中 `https://localhost:44362/` 指定的任何端口 `launchSettings.json` 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-146">Visual Studio builds your app, start the web server, launch Microsoft Edge, and navigate to `https://localhost:44362/` or whatever port is specified in `launchSettings.json`.</span></span>  

:::image type="complex" source="./media/edge-launch.png" alt-text="Microsoft Edge 从 Visual Studio" lightbox="./media/edge-launch.png":::
   <span data-ttu-id="84fc4-148">Microsoft Edge 从 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-148">Microsoft Edge launches from Visual Studio</span></span>  
:::image-end:::  

### <a name="debug-javascript-running-in-microsoft-edge"></a><span data-ttu-id="84fc4-149">调试在 Microsoft Edge 中运行的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="84fc4-149">Debug JavaScript running in Microsoft Edge</span></span>  

<span data-ttu-id="84fc4-150">切换回Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="84fc4-150">Switch back to Visual Studio.</span></span>  <span data-ttu-id="84fc4-151">在 `Counter.js` 中，若要设置第 13 行上的断点，请选择该行旁边的装订线。</span><span class="sxs-lookup"><span data-stu-id="84fc4-151">In `Counter.js`, to set a breakpoint on Line 13, choose the gutter next to the line.</span></span>  

:::image type="complex" source="./media/set-breakpoint.png" alt-text="Choose the gutter next to Line 13 in Counter.js to set a breakpoint in Visual Studio" lightbox="./media/set-breakpoint.png":::
   <span data-ttu-id="84fc4-153">选择第 13 行旁边的装订线以 `Counter.js` 在 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-153">Choose the gutter next to Line 13 in `Counter.js` to set a breakpoint in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-154">现在切换回已启动的 Microsoft Edge Visual Studio实例。</span><span class="sxs-lookup"><span data-stu-id="84fc4-154">Now switch back to the instance of Microsoft Edge that Visual Studio launched.</span></span>  <span data-ttu-id="84fc4-155">在 **网页** 左侧的 NavMenu 中的"计数器"上选择。</span><span class="sxs-lookup"><span data-stu-id="84fc4-155">Choose on **Counter** in the NavMenu on the left of the webpage.</span></span>  <span data-ttu-id="84fc4-156">现在，选择 **"增量"。**</span><span class="sxs-lookup"><span data-stu-id="84fc4-156">Now choose **Increment**.</span></span>  

:::image type="complex" source="./media/edge-counter.png" alt-text="核心 Web 应用中 ASP.NET 计数器页面" lightbox="./media/edge-counter.png":::
   <span data-ttu-id="84fc4-158">核心 Web 应用中 ASP.NET 计数器页面</span><span class="sxs-lookup"><span data-stu-id="84fc4-158">The Counter page in our ASP.NET Core web app</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-159">中 JavaScript 调试Visual Studio命中你在 中设置的断点 `Counter.js` 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-159">The JavaScript debugger in Visual Studio hits the breakpoint you set in `Counter.js`.</span></span>  <span data-ttu-id="84fc4-160">Visual Studio现在暂停在 Microsoft Edge 中运行的 JavaScript 的运行时，你可以逐行执行脚本。</span><span class="sxs-lookup"><span data-stu-id="84fc4-160">Visual Studio now pauses the runtime of the JavaScript running in Microsoft Edge and you may step through the script line-by-line.</span></span>  

:::image type="complex" source="./media/hit-breakpoint.png" alt-text="Visual Studio Microsoft Edge 中运行的 JavaScript" lightbox="./media/hit-breakpoint.png":::
   <span data-ttu-id="84fc4-162">Visual Studio Microsoft Edge 中运行的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="84fc4-162">Visual Studio pauses JavaScript running in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-163">该示例只是对 Visual Studio 中提供的功能的一Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="84fc4-163">The example was just a minor demonstration of the functionality available in Visual Studio.</span></span>  <span data-ttu-id="84fc4-164">有关 Visual Studio 2019 中功能Visual Studio [文档][VisualStudioWindowsIndex]。</span><span class="sxs-lookup"><span data-stu-id="84fc4-164">For more information about the functionality in Visual Studio 2019, navigate to [Visual Studio documentation][VisualStudioWindowsIndex].</span></span>  

## <a name="attach-to-microsoft-edge"></a><span data-ttu-id="84fc4-165">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="84fc4-165">Attach to Microsoft Edge</span></span>  

<span data-ttu-id="84fc4-166">以前，必须启动 Microsoft Edge Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="84fc4-166">Previously, you had to launch Microsoft Edge from Visual Studio.</span></span>  <span data-ttu-id="84fc4-167">现在，可以将调试器Visual Studio Microsoft Edge 的一个已在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="84fc4-167">Now, you are able to attach the Visual Studio debugger to an already running instance of Microsoft Edge.</span></span>  

<span data-ttu-id="84fc4-168">首先，确保没有正在运行的 Microsoft Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="84fc4-168">First, ensure that there are no running instances of Microsoft Edge.</span></span>  <span data-ttu-id="84fc4-169">现在，从命令行运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="84fc4-169">Now, from your command line, run the following command.</span></span>  

```console
start msedge –remote-debugging-port=9222
```  

<span data-ttu-id="84fc4-170">从Visual Studio，**打开"调试**"菜单并选择 **"附加到进程"或**选择 `Ctrl` + `Alt` + `P` 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-170">From Visual Studio, open the **Debug** menu and choose **Attach to Process** or select `Ctrl`+`Alt`+`P`.</span></span>  

:::image type="complex" source="./media/attach-to-process.png" alt-text="选择"附加到进程"Visual Studio" lightbox="./media/attach-to-process.png":::
   <span data-ttu-id="84fc4-172">选择 **"附加到进程** "Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-172">Choose **Attach to Process** in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-173">从附加到**进程对话框中**，将**连接**类型设置为\*\*Chrome devtools 协议 websocket (无身份验证) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="84fc4-173">From the **Attach to Process** dialog, set **Connection type** to **Chrome devtools protocol websocket (no authentication)**.</span></span>  <span data-ttu-id="84fc4-174">在" **连接目标** "文本框中，键入 `http://localhost:9222/` 并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="84fc4-174">In the **Connecting target** textbox, type `http://localhost:9222/` and select `Enter`.</span></span>  <span data-ttu-id="84fc4-175">查看"附加到进程"对话框中列出的 Microsoft Edge 中已打开的 **选项卡** 列表。</span><span class="sxs-lookup"><span data-stu-id="84fc4-175">Review the list of open tabs you have in Microsoft Edge listed out in the **Attach to Process** dialog.</span></span>  

:::image type="complex" source="./media/attach-to-process-dialog.png" alt-text="配置"附加到进程"对话框Visual Studio" lightbox="./media/attach-to-process-dialog.png":::
   <span data-ttu-id="84fc4-177">Configure the **Attach to Process** dialog in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-177">Configure the **Attach to Process** dialog in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="84fc4-178">选择 **选择...** > \*\*Microsoft Edge 中的 JavaScript (Chromium) " 旁边的复选框 \*\*。</span><span class="sxs-lookup"><span data-stu-id="84fc4-178">Choose **Select...** > the checkbox next to **JavaScript (Microsoft Edge – Chromium)**.</span></span>  <span data-ttu-id="84fc4-179">若要添加选项卡、导航到新选项卡、关闭选项卡并显示"附加到进程"对话框中反映的更改\*\*\*\*，请选择"**刷新"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="84fc4-179">To add tabs, navigate to new tabs, and close tabs and display the changes reflected in the **Attach to Process** dialog, choose the **Refresh** button.</span></span>  <span data-ttu-id="84fc4-180">选择要调试的选项卡，然后选择"附加 **"。**</span><span class="sxs-lookup"><span data-stu-id="84fc4-180">Choose the tab you want to debug and choose **Attach**.</span></span>  

<span data-ttu-id="84fc4-181">现在Visual Studio调试器已连接到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="84fc4-181">The Visual Studio debugger is now attached to Microsoft Edge.</span></span>  <span data-ttu-id="84fc4-182">您可以暂停 JavaScript 的运行，直接在 Visual Studio 的"调试 `console.log()` 输出"窗口中设置断点并查看Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="84fc4-182">You may pause the running of JavaScript, set breakpoints, and review `console.log()` statements directly in the Debug Output window in Visual Studio.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-visual-studio-team"></a><span data-ttu-id="84fc4-183">与 Microsoft Visual Studio联系</span><span class="sxs-lookup"><span data-stu-id="84fc4-183">Getting in touch with the Microsoft Visual Studio team</span></span>  

<span data-ttu-id="84fc4-184">Microsoft Visual Studio 和 Microsoft Edge 团队希望详细了解如何在 Visual Studio 中使用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="84fc4-184">The Microsoft Visual Studio and Microsoft Edge teams wants to learn more about how you work with JavaScript in Visual Studio.</span></span>  <span data-ttu-id="84fc4-185">若要发送反馈，请选择"发送反馈 **"图标Visual Studio**推文[@VisualStudio@EdgeDevTools。][TwitterIntentTweetViualstudioEdgdevtools]</span><span class="sxs-lookup"><span data-stu-id="84fc4-185">To send your feedback, choose the **Send Feedback** icon in Visual Studio or tweet [@VisualStudio and @EdgeDevTools][TwitterIntentTweetViualstudioEdgdevtools].</span></span>  

:::image type="complex" source="./media/feedback-icon.png" alt-text=""发送反馈"图标Visual Studio" lightbox="./media/feedback-icon.png":::
   <span data-ttu-id="84fc4-187">" **发送反馈** "图标Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84fc4-187">The **Send Feedback** icon in Visual Studio</span></span>  
:::image-end:::  

<!-- links -->  

[VisualStudioWindowsIndex]: /visualstudio/windows/index "Visual Studio文档|Microsoft Docs"  

[MicrosoftVisualstudioDownloads]: https://visualstudio.microsoft.com/downloads "下载Visual Studio"  
[MicrosoftVisualstudioVs]: https://visualstudio.microsoft.com/vs "Visual Studio IDE"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[TwitterIntentTweetViualstudioEdgdevtools]: https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools "推文@VisualStudio和@EdgeDevTools |Twitter"  
