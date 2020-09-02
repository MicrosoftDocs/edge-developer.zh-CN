---
description: Microsoft Edge (Chromium) 和 Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs、visual studio、调试器
ms.openlocfilehash: 3fc2e2c3dc21689d8c378ccbe33e4dff813ea12f
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986190"
---
# <span data-ttu-id="395d0-104">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="395d0-104">Visual Studio</span></span>

<span data-ttu-id="395d0-105">Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) 是 (IDE) 的集成开发环境，可用于编辑、调试、构建和发布 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="395d0-105">Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) is an integrated development environment (IDE) that you can use to edit, debug, build, and publish your web applications.</span></span> <span data-ttu-id="395d0-106">它是一种功能丰富的程序，可用于 web 开发的许多方面。</span><span class="sxs-lookup"><span data-stu-id="395d0-106">It is a feature-rich program that can be used for many aspects of your web development.</span></span> <span data-ttu-id="395d0-107">在大多数 Ide 提供的标准编辑器和调试器上方以及更高的版本中，Visual Studio 包括编译器、代码完成工具、图形设计器以及更多可轻松开发过程的功能。</span><span class="sxs-lookup"><span data-stu-id="395d0-107">Over and above the standard editor and debugger that most IDEs provide, Visual Studio includes compilers, code completion tools, graphical designers, and many more features to ease your development process.</span></span> <span data-ttu-id="395d0-108">转到 [此页面](https://visualstudio.microsoft.com/downloads/) 以下载 Visual Studio （如果尚未使用）。</span><span class="sxs-lookup"><span data-stu-id="395d0-108">Head to [this page](https://visualstudio.microsoft.com/downloads/) to download Visual Studio if you aren't using it yet.</span></span>

<span data-ttu-id="395d0-109">目前，Visual Studio 2019 支持在 Microsoft Edge 中针对你的 ASP\.NET Framework 和 ASP\.NET Core 应用程序调试 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="395d0-109">Currently, Visual Studio 2019 supports debugging JavaScript in Microsoft Edge for your ASP\.NET Framework and ASP\.NET Core applications.</span></span> <span data-ttu-id="395d0-110">请按照以下步骤从 Visual Studio 调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="395d0-110">Follow the steps below to debug Microsoft Edge from Visual Studio.</span></span>

## <span data-ttu-id="395d0-111">启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="395d0-111">Launch Microsoft Edge</span></span>
<span data-ttu-id="395d0-112">Visual Studio 构建你的 ASP\.NET 和 ASP\.NET Core 应用程序，启动你的 web 服务器，启动 Microsoft Edge，并通过单击一个按钮连接 Visual Studio 调试器。</span><span class="sxs-lookup"><span data-stu-id="395d0-112">Visual Studio builds your ASP\.NET and ASP\.NET Core application, starts your web server, launches Microsoft Edge, and connects the Visual Studio debugger all at the click of a single button.</span></span> <span data-ttu-id="395d0-113">这使你可以直接从 IDE 中调试在 Microsoft Edge 中运行的 JavaScript！</span><span class="sxs-lookup"><span data-stu-id="395d0-113">This enables you to debug JavaScript running in Microsoft Edge directly from your IDE!</span></span>

### <span data-ttu-id="395d0-114">创建新的 ASP.NET Core web 应用程序</span><span class="sxs-lookup"><span data-stu-id="395d0-114">Create a new ASP.NET Core web application</span></span>

<span data-ttu-id="395d0-115">打开 Visual Studio 2019，然后选择 " **创建新项目**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-115">Open Visual Studio 2019 and select **Create a new project**.</span></span> <span data-ttu-id="395d0-116">在下一个屏幕上，选择 **ASP\.NET Core Web 应用程序** ，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-116">On the next screen, select **ASP\.NET Core Web Application** and click **Next**.</span></span>

> ##### <span data-ttu-id="395d0-117">图 1</span><span class="sxs-lookup"><span data-stu-id="395d0-117">Figure 1</span></span>  
> <span data-ttu-id="395d0-118">创建新的 ASP.NET Core Web 应用程序 ![ 创建新的 ASP.NET 核心 Web 应用程序](./media/create-new-project.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-118">Create a new ASP.NET Core Web Application ![Create a new ASP.NET Core Web Application](./media/create-new-project.png)</span></span>  

<span data-ttu-id="395d0-119">为新项目提供 **项目名称** ，然后单击 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-119">Provide a **Project name** for your new project and click **Create**.</span></span> <span data-ttu-id="395d0-120">在此示例中，选择 " **React.js** 作为模板，显示如何将 React.js 与 ASP.NET Core 应用程序进行集成，然后单击" **创建**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-120">For the purposes of this example, select **React.js** as the template which shows you how to integrate React.js with an ASP.NET Core application and click **Create**.</span></span>

### <span data-ttu-id="395d0-121">从 Visual Studio 启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="395d0-121">Launch Microsoft Edge from Visual Studio</span></span>

<span data-ttu-id="395d0-122">创建项目后，打开 " **ClientApp/src/组件/Counter.js**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-122">Once your project has been created, open **ClientApp/src/components/Counter.js**.</span></span> <span data-ttu-id="395d0-123">现在，通过选择绿色 " **播放** " 按钮旁边的下拉列表和 " **IIS Express**"，告诉 Visual Studio 调试 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="395d0-123">Now, tell Visual Studio to debug JavaScript by selecting the dropdown next to the green **Play** button and **IIS Express**.</span></span> 

> ##### <span data-ttu-id="395d0-124">图 2</span><span class="sxs-lookup"><span data-stu-id="395d0-124">Figure 2</span></span>  
> <span data-ttu-id="395d0-125">绿色的 "**播放**" 按钮旁边的下拉列表和**iis 表示**" 
> ![ 绿色播放" 按钮旁边的下拉列表和 "iis express"](./media/vs-dropdown.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-125">The dropdown next to the green **Play** button and **IIS Express**
![The dropdown next to the green Play button and IIS Express](./media/vs-dropdown.png)</span></span>  

<span data-ttu-id="395d0-126">选择 " **脚本调试** "，然后单击 " **启用**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-126">Select **Script Debugging** and click **Enabled**.</span></span>

> ##### <span data-ttu-id="395d0-127">图 3</span><span class="sxs-lookup"><span data-stu-id="395d0-127">Figure 3</span></span>  
> <span data-ttu-id="395d0-128">在 visual studio 中启用脚本调试在 ![ Visual studio 中启用脚本调试](./media/enable-script-debugging.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-128">Enable script debugging in Visual Studio ![Enable script debugging in Visual Studio](./media/enable-script-debugging.png)</span></span>  

<span data-ttu-id="395d0-129">在同一个下拉列表中，选择 " **Web 浏览器** "，然后单击要 Visual Studio 启动的 microsoft edge 的预览频道： Microsoft edge "未选定"、"开发" 或 "Beta"。</span><span class="sxs-lookup"><span data-stu-id="395d0-129">In the same dropdown, select **Web Browser** and click the preview channel of Microsoft Edge that you want Visual Studio to launch: Microsoft Edge Canary, Dev, or Beta.</span></span> <span data-ttu-id="395d0-130">如果尚未安装，请转到 [此页面](https://www.microsoftedgeinsider.com/download) 以安装 Microsoft Edge 预览频道。</span><span class="sxs-lookup"><span data-stu-id="395d0-130">If you haven't already, head to [this page](https://www.microsoftedgeinsider.com/download) to install the Microsoft Edge preview channels.</span></span>

> ##### <span data-ttu-id="395d0-131">图 4</span><span class="sxs-lookup"><span data-stu-id="395d0-131">Figure 4</span></span>  
> <span data-ttu-id="395d0-132">选择你希望 Visual Studio 启动的 Microsoft Edge 的预览频道 ![ 选择你希望 Visual studio 启动的 Microsoft edge 的预览频道](./media/set-web-browser.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-132">Select the preview channel of Microsoft Edge that you want Visual Studio to launch ![Select the preview channel of Microsoft Edge that you want Visual Studio to launch](./media/set-web-browser.png)</span></span>  

> [!NOTE]
> <span data-ttu-id="395d0-133">如果选择 "Microsoft Edge (EdgeHTML") ，Visual Studio 将启动，而不是 Microsoft Edge (Chromium ") 。</span><span class="sxs-lookup"><span data-stu-id="395d0-133">If you select Microsoft Edge (EdgeHTML), Visual Studio will launch that instead of Microsoft Edge (Chromium).</span></span> <span data-ttu-id="395d0-134">[安装 Microsoft edge 的预览频道](https://www.microsoftedgeinsider.com/download) ，然后选择它们或确保你的计算机上安装的 microsoft edge 版本是 microsoft Edge (Chromium) ，而不是 microsoft Edge (EdgeHTML) 。</span><span class="sxs-lookup"><span data-stu-id="395d0-134">[Install the preview channels of Microsoft Edge](https://www.microsoftedgeinsider.com/download) and select them or ensure that the version of Microsoft Edge installed on your machine is Microsoft Edge (Chromium) and not Microsoft Edge (EdgeHTML).</span></span>

<span data-ttu-id="395d0-135">现在，已正确配置 Visual Studio，请单击绿色的 " **播放** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="395d0-135">Now that Visual Studio is correctly configured, click the green **Play** button.</span></span> <span data-ttu-id="395d0-136">Visual Studio 将生成你的应用程序、启动 web 服务器、启动 Microsoft Edge，并导航到 `https://localhost:44362/` **launchSettings.js**中指定的任何端口。</span><span class="sxs-lookup"><span data-stu-id="395d0-136">Visual Studio will build your application, start the web server, launch Microsoft Edge, and navigate to `https://localhost:44362/` or whatever port is specified in **launchSettings.json**.</span></span>

> ##### <span data-ttu-id="395d0-137">图 5</span><span class="sxs-lookup"><span data-stu-id="395d0-137">Figure 5</span></span>  
> <span data-ttu-id="395d0-138">从 Visual studio 启动的 Visual Studio microsoft Edge 中启动的 microsoft Edge ![](./media/edge-launch.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-138">Microsoft Edge launched from Visual Studio ![Microsoft Edge launched from Visual Studio](./media/edge-launch.png)</span></span>  

### <span data-ttu-id="395d0-139">调试在 Microsoft Edge 中运行的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="395d0-139">Debug JavaScript running in Microsoft Edge</span></span>

<span data-ttu-id="395d0-140">切换回 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="395d0-140">Switch back to Visual Studio.</span></span> <span data-ttu-id="395d0-141">在 **Counter.js**中，通过单击该行旁边的装订线，在第13行设置一个断点。</span><span class="sxs-lookup"><span data-stu-id="395d0-141">In **Counter.js**, set a breakpoint on Line 13 by clicking in the gutter next to that line.</span></span>

> ##### <span data-ttu-id="395d0-142">图 6</span><span class="sxs-lookup"><span data-stu-id="395d0-142">Figure 6</span></span>
> <span data-ttu-id="395d0-143">通过单击第13行旁边的装订线在 Visual Studio 中设置断点， **Counter.js** 
> ![ 通过单击 Counter.js中第13行旁边的装订线，在 visual studio 中设置断点。](./media/set-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-143">Setting a breakpoint in Visual Studio by clicking on the gutter next to Line 13 in **Counter.js**
![Setting a breakpoint in Visual Studio by clicking on the gutter next to Line 13 in Counter.js](./media/set-breakpoint.png)</span></span>  

<span data-ttu-id="395d0-144">现在切换回启动 Visual Studio 的 Microsoft Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="395d0-144">Now switch back to the instance of Microsoft Edge that Visual Studio launched.</span></span> <span data-ttu-id="395d0-145">单击页面左侧 NavMenu 中的 " **计数器** "。</span><span class="sxs-lookup"><span data-stu-id="395d0-145">Click on **Counter** in the NavMenu on the left of the page.</span></span> <span data-ttu-id="395d0-146">现在单击 " **增量**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-146">Now click **Increment**.</span></span>

> ##### <span data-ttu-id="395d0-147">图 7</span><span class="sxs-lookup"><span data-stu-id="395d0-147">Figure 7</span></span>
> <span data-ttu-id="395d0-148">我们的 ASP.NET Core web 应用程序中的计数器页面 ![ 我们的 ASP.NET core web 应用程序中的计数器页面](./media/edge-counter.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-148">The Counter page in our ASP.NET Core web application ![The Counter page in our ASP.NET Core web application](./media/edge-counter.png)</span></span>  

<span data-ttu-id="395d0-149">Visual Studio 中的 JavaScript 调试器将按下在 **Counter.js**中设置的断点。</span><span class="sxs-lookup"><span data-stu-id="395d0-149">The JavaScript debugger in Visual Studio is going to hit the breakpoint we set in **Counter.js**.</span></span> <span data-ttu-id="395d0-150">Visual Studio 现已暂停执行在 Microsoft Edge 中运行的 JavaScript，你可以逐行执行脚本。</span><span class="sxs-lookup"><span data-stu-id="395d0-150">Visual Studio has now paused execution of the JavaScript running in Microsoft Edge and you can step through the script line-by-line.</span></span>

> ##### <span data-ttu-id="395d0-151">图 8</span><span class="sxs-lookup"><span data-stu-id="395d0-151">Figure 8</span></span>
> <span data-ttu-id="395d0-152">Visual Studio 暂停 Microsoft Edge Visual Studio 中运行的 JavaScript ![ 暂停在 Microsoft edge 中运行的 javascript](./media/hit-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-152">Visual Studio pausing JavaScript running in Microsoft Edge ![Visual Studio pausing JavaScript running in Microsoft Edge](./media/hit-breakpoint.png)</span></span>  

<span data-ttu-id="395d0-153">此示例只是 Visual Studio 中可用功能的次要演示。</span><span class="sxs-lookup"><span data-stu-id="395d0-153">This example was just a minor demonstration of the functionality available in Visual Studio.</span></span> <span data-ttu-id="395d0-154">阅读 [文档](https://docs.microsoft.com/visualstudio/windows/?view=vs-2019)，了解有关 Visual Studio 2019 中可以执行的所有操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="395d0-154">Learn more about all the things you can do in Visual Studio 2019 by reading [their documentation](https://docs.microsoft.com/visualstudio/windows/?view=vs-2019).</span></span>

## <span data-ttu-id="395d0-155">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="395d0-155">Attach to Microsoft Edge</span></span>
<span data-ttu-id="395d0-156">在上一个工作流中，Visual Studio 将启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="395d0-156">In the previous workflow, Visual Studio launches Microsoft Edge.</span></span> <span data-ttu-id="395d0-157">使用此工作流，你将能够将 Visual Studio 调试器附加到已运行的 Microsoft Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="395d0-157">With this workflow, you will be able to attach the Visual Studio debugger to an already running instance of Microsoft Edge.</span></span> 

<span data-ttu-id="395d0-158">首先，请确保没有任何正在运行的 Microsoft Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="395d0-158">First, ensure that there are no running instances of Microsoft Edge.</span></span> <span data-ttu-id="395d0-159">现在，从终端运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="395d0-159">Now, from your terminal, run the following command:</span></span>

```console
start msedge –remote-debugging-port=9222
```

<span data-ttu-id="395d0-160">从 Visual Studio 中，打开 "**调试**" 菜单，然后选择 "**附加到进程**" 或 "按" `Ctrl`  +  `Alt`  +  `P` 。</span><span class="sxs-lookup"><span data-stu-id="395d0-160">From Visual Studio, open the **Debug** menu and select **Attach to Process** or press `Ctrl` + `Alt` + `P`.</span></span>

> ##### <span data-ttu-id="395d0-161">图 9</span><span class="sxs-lookup"><span data-stu-id="395d0-161">Figure 9</span></span>
> <span data-ttu-id="395d0-162">选择 Visual Studio 中的 " **附加到进程** " 在 ![ visual studio 中选择 "* * 附加到进程 * *"](./media/attach-to-process.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-162">Selecting **Attach to Process** in Visual Studio ![Selecting **Attach to Process** in Visual Studio](./media/attach-to-process.png)</span></span>  

<span data-ttu-id="395d0-163">从 " **附加到进程** " 对话框中，将 **连接类型** 设置为 \*\*Chrome devtools 协议 websocket (无身份验证) \*\*。</span><span class="sxs-lookup"><span data-stu-id="395d0-163">From the **Attach to Process** dialog, set **Connection type** to **Chrome devtools protocol websocket (no authentication)**.</span></span> <span data-ttu-id="395d0-164">在 " **连接目标** " 文本框中，键入 "输入" `http://localhost:9222/` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="395d0-164">In the **Connecting target** textbox, type in `http://localhost:9222/` and press `Enter`.</span></span> <span data-ttu-id="395d0-165">你应该会在 " **附加到流程** " 对话框中看到在 Microsoft Edge 中列出的打开选项卡的列表。</span><span class="sxs-lookup"><span data-stu-id="395d0-165">You should see the list of open tabs you have in Microsoft Edge listed out in the **Attach to Process** dialog.</span></span>

> ##### <span data-ttu-id="395d0-166">图 10</span><span class="sxs-lookup"><span data-stu-id="395d0-166">Figure 10</span></span>
> <span data-ttu-id="395d0-167">在 visual Studio 中配置 " **附加到进程** " 对话框 ![ 配置 visual studio 中的 "附加到进程" 对话框](./media/attach-to-process-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-167">Configuring the **Attach to Process** dialog in Visual Studio ![Configuring the Attach to Process dialog in Visual Studio](./media/attach-to-process-dialog.png)</span></span>  

<span data-ttu-id="395d0-168">单击 "**选择 ...** "</span><span class="sxs-lookup"><span data-stu-id="395d0-168">Click **Select…**</span></span> <span data-ttu-id="395d0-169">并检查 \*\*Microsoft Edge (的 JavaScript-Chromium) \*\*。</span><span class="sxs-lookup"><span data-stu-id="395d0-169">and check **JavaScript (Microsoft Edge – Chromium)**.</span></span> <span data-ttu-id="395d0-170">你可以添加选项卡，导航到新选项卡，关闭选项卡，并在 " **附加到进程** " 对话框中单击 " **刷新** " 按钮查看这些更改。</span><span class="sxs-lookup"><span data-stu-id="395d0-170">You can add tabs, navigate to new tabs, and close tabs and see those changes reflected in the **Attach to Process** dialog by clicking the **Refresh** button.</span></span> <span data-ttu-id="395d0-171">选择要调试的选项卡，然后单击 " **附加**"。</span><span class="sxs-lookup"><span data-stu-id="395d0-171">Select the tab you want to debug and click **Attach**.</span></span>

<span data-ttu-id="395d0-172">Visual Studio 调试器现已附加到 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="395d0-172">The Visual Studio debugger is now attached to Microsoft Edge!</span></span> <span data-ttu-id="395d0-173">你可以在 `console.log()` Visual Studio 中的 "调试输出" 窗口中暂停执行 JavaScript、设置断点和查看语句。</span><span class="sxs-lookup"><span data-stu-id="395d0-173">You can pause execution of JavaScript, set breakpoints, and see `console.log()` statements directly in the Debug Output window in Visual Studio.</span></span>

## <span data-ttu-id="395d0-174">与 Microsoft Visual Studio 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="395d0-174">Getting in touch with the Microsoft Visual Studio team</span></span>  

<span data-ttu-id="395d0-175">我们将渴望详细了解如何在 Visual Studio 中使用 JavaScript！</span><span class="sxs-lookup"><span data-stu-id="395d0-175">We're eager to learn more about how you work with JavaScript in Visual Studio!</span></span>  <span data-ttu-id="395d0-176">请通过单击 Visual Studio 中的 **反馈** 图标或发推至 [ @VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text= @VisualStudio + @EdgeDevTools) 来向我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="395d0-176">Please send us feedback by clicking the **Feedback** icon in Visual Studio or by tweeting [@VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools).</span></span>  

> ##### <span data-ttu-id="395d0-177">图 11</span><span class="sxs-lookup"><span data-stu-id="395d0-177">Figure 11</span></span>
> <span data-ttu-id="395d0-178">Visual Studio 中的 **反馈** 图标 ![ visual studio 中的 "反馈" 图标](./media/feedback-icon.png)</span><span class="sxs-lookup"><span data-stu-id="395d0-178">The **Feedback** icon in Visual Studio ![The Feedback icon in Visual Studio](./media/feedback-icon.png)</span></span>  
