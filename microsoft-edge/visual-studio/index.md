---
description: Microsoft Edge (Chromium) 和 Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs， visual studio， 调试器
ms.openlocfilehash: f3796a040fe6c658211b4009445b5c179ab9b077
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231207"
---
# <span data-ttu-id="fd7e6-104">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd7e6-104">Visual Studio</span></span>

<span data-ttu-id="fd7e6-105">Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) 是 IDE (集成开发) ，可用于编辑、调试、生成和发布 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-105">Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) is an integrated development environment (IDE) that you can use to edit, debug, build, and publish your web applications.</span></span> <span data-ttu-id="fd7e6-106">它是一个功能丰富的程序，可用于 Web 开发的许多方面。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-106">It is a feature-rich program that can be used for many aspects of your web development.</span></span> <span data-ttu-id="fd7e6-107">在大多数 ID 提供的标准编辑器和调试器之上，Visual Studio编译器、代码完成工具、图形设计器以及更多功能，以便于开发过程。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-107">Over and above the standard editor and debugger that most IDEs provide, Visual Studio includes compilers, code completion tools, graphical designers, and many more features to ease your development process.</span></span> <span data-ttu-id="fd7e6-108">如果 [尚未使用](https://visualstudio.microsoft.com/downloads/) Visual Studio，请前往此页面进行下载。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-108">Head to [this page](https://visualstudio.microsoft.com/downloads/) to download Visual Studio if you aren't using it yet.</span></span>

<span data-ttu-id="fd7e6-109">目前，Visual Studio 2019 支持在 Microsoft Edge 中为 ASP\.NET Framework 和 ASP\.NET Core 应用程序调试 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-109">Currently, Visual Studio 2019 supports debugging JavaScript in Microsoft Edge for your ASP\.NET Framework and ASP\.NET Core applications.</span></span> <span data-ttu-id="fd7e6-110">按照以下步骤从 microsoft Edge Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-110">Follow the steps below to debug Microsoft Edge from Visual Studio.</span></span>

## <span data-ttu-id="fd7e6-111">启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fd7e6-111">Launch Microsoft Edge</span></span>
<span data-ttu-id="fd7e6-112">Visual Studio ASP\.NET 和 ASP\.NET Core 应用程序，启动 Web 服务器，启动 Microsoft Edge，并连接 Visual Studio 调试器，只需单击一个按钮即可。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-112">Visual Studio builds your ASP\.NET and ASP\.NET Core application, starts your web server, launches Microsoft Edge, and connects the Visual Studio debugger all at the click of a single button.</span></span> <span data-ttu-id="fd7e6-113">这使你可以直接从 IDE 调试在 Microsoft Edge 中运行的 JavaScript！</span><span class="sxs-lookup"><span data-stu-id="fd7e6-113">This enables you to debug JavaScript running in Microsoft Edge directly from your IDE!</span></span>

### <span data-ttu-id="fd7e6-114">创建新的核心ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="fd7e6-114">Create a new ASP.NET Core web application</span></span>

<span data-ttu-id="fd7e6-115">打开Visual Studio 2019 并选择 **"新建项目"。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-115">Open Visual Studio 2019 and select **Create a new project**.</span></span> <span data-ttu-id="fd7e6-116">下一个屏幕上，选择**ASP\.NET Core Web 应用程序**，然后单击"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-116">On the next screen, select **ASP\.NET Core Web Application** and click **Next**.</span></span>

> ##### <span data-ttu-id="fd7e6-117">图 1</span><span class="sxs-lookup"><span data-stu-id="fd7e6-117">Figure 1</span></span>  
> <span data-ttu-id="fd7e6-118">新建核心 web ASP.NET 新建核心 Web ![ ASP.NET Web 应用程序](./media/create-new-project.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-118">Create a new ASP.NET Core Web Application ![Create a new ASP.NET Core Web Application](./media/create-new-project.png)</span></span>  

<span data-ttu-id="fd7e6-119">提供**新项目的项目**名称，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-119">Provide a **Project name** for your new project and click **Create**.</span></span> <span data-ttu-id="fd7e6-120">对于此示例，选择React.js模板，以演示如何\*\*\*\* 将 React.js 与 ASP.NET Core 应用程序集成，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-120">For the purposes of this example, select **React.js** as the template which shows you how to integrate React.js with an ASP.NET Core application and click **Create**.</span></span>

### <span data-ttu-id="fd7e6-121">从 microsoft Edge Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd7e6-121">Launch Microsoft Edge from Visual Studio</span></span>

<span data-ttu-id="fd7e6-122">创建项目后，打开\*\*ClientApp/src/components/Counter.js。 \*\*</span><span class="sxs-lookup"><span data-stu-id="fd7e6-122">Once your project has been created, open **ClientApp/src/components/Counter.js**.</span></span> <span data-ttu-id="fd7e6-123">现在，通过Visual Studio"播放"按钮和**IIS Express**旁边的下拉列表，告诉用户\*\*\*\* 调试 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-123">Now, tell Visual Studio to debug JavaScript by selecting the dropdown next to the green **Play** button and **IIS Express**.</span></span> 

> ##### <span data-ttu-id="fd7e6-124">图 2</span><span class="sxs-lookup"><span data-stu-id="fd7e6-124">Figure 2</span></span>  
> <span data-ttu-id="fd7e6-125">绿色"播放"按钮和\*\*\*\*\*\*IIS Express\*\*旁边的下拉列表绿色"播放"按钮和 
> ![ IIS Express 旁边的下拉列表](./media/vs-dropdown.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-125">The dropdown next to the green **Play** button and **IIS Express**
![The dropdown next to the green Play button and IIS Express](./media/vs-dropdown.png)</span></span>  

<span data-ttu-id="fd7e6-126">选择 **"脚本调试"，** 然后单击"**启用"。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-126">Select **Script Debugging** and click **Enabled**.</span></span>

> ##### <span data-ttu-id="fd7e6-127">图 3</span><span class="sxs-lookup"><span data-stu-id="fd7e6-127">Figure 3</span></span>  
> <span data-ttu-id="fd7e6-128">在"启用脚本调试Visual Studio ![ 中启用脚本调试Visual Studio](./media/enable-script-debugging.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-128">Enable script debugging in Visual Studio ![Enable script debugging in Visual Studio](./media/enable-script-debugging.png)</span></span>  

<span data-ttu-id="fd7e6-129">在同一下拉列表中，选择 **"Web** 浏览器"，然后单击要启动的 Microsoft Edge Visual Studio频道：Microsoft Edge Canary、Dev 或 Beta。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-129">In the same dropdown, select **Web Browser** and click the preview channel of Microsoft Edge that you want Visual Studio to launch: Microsoft Edge Canary, Dev, or Beta.</span></span> <span data-ttu-id="fd7e6-130">如果尚未安装，请前往 [此页面](https://www.microsoftedgeinsider.com/download) 以安装 Microsoft Edge 预览频道。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-130">If you haven't already, head to [this page](https://www.microsoftedgeinsider.com/download) to install the Microsoft Edge preview channels.</span></span>

> ##### <span data-ttu-id="fd7e6-131">图 4</span><span class="sxs-lookup"><span data-stu-id="fd7e6-131">Figure 4</span></span>  
> <span data-ttu-id="fd7e6-132">选择要启动的 Microsoft Edge Visual Studio 选择要启动的 Microsoft ![ Edge Visual Studio频道](./media/set-web-browser.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-132">Select the preview channel of Microsoft Edge that you want Visual Studio to launch ![Select the preview channel of Microsoft Edge that you want Visual Studio to launch](./media/set-web-browser.png)</span></span>  

> [!NOTE]
> <span data-ttu-id="fd7e6-133">如果选择 Microsoft Edge (EdgeHTML) ，Visual Studio启动它，而不是 Microsoft Edge (Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-133">If you select Microsoft Edge (EdgeHTML), Visual Studio will launch that instead of Microsoft Edge (Chromium).</span></span> <span data-ttu-id="fd7e6-134">安装[Microsoft Edge](https://www.microsoftedgeinsider.com/download)的预览频道并选择它们，或确保计算机上安装的 Microsoft Edge 版本是 Microsoft Edge (Chromium) ，而不是 Microsoft Edge (EdgeHTML) 。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-134">[Install the preview channels of Microsoft Edge](https://www.microsoftedgeinsider.com/download) and select them or ensure that the version of Microsoft Edge installed on your machine is Microsoft Edge (Chromium) and not Microsoft Edge (EdgeHTML).</span></span>

<span data-ttu-id="fd7e6-135">现在，Visual Studio配置正确，请单击绿色 **"播放"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-135">Now that Visual Studio is correctly configured, click the green **Play** button.</span></span> <span data-ttu-id="fd7e6-136">Visual Studio将生成应用程序、启动 Web 服务器、启动 Microsoft Edge，并导航到或任何在launchSettings.js`https://localhost:44362/` \*\* 中指定的端口\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-136">Visual Studio will build your application, start the web server, launch Microsoft Edge, and navigate to `https://localhost:44362/` or whatever port is specified in **launchSettings.json**.</span></span>

> ##### <span data-ttu-id="fd7e6-137">图 5</span><span class="sxs-lookup"><span data-stu-id="fd7e6-137">Figure 5</span></span>  
> <span data-ttu-id="fd7e6-138">从 Microsoft Edge Visual Studio ![ Microsoft Edge 启动的 Microsoft Edge Visual Studio](./media/edge-launch.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-138">Microsoft Edge launched from Visual Studio ![Microsoft Edge launched from Visual Studio](./media/edge-launch.png)</span></span>  

### <span data-ttu-id="fd7e6-139">调试在 Microsoft Edge 中运行的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="fd7e6-139">Debug JavaScript running in Microsoft Edge</span></span>

<span data-ttu-id="fd7e6-140">切换回Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-140">Switch back to Visual Studio.</span></span> <span data-ttu-id="fd7e6-141">In \*\*Counter.js， \*\*set a breakpoint on Line 13 by clicking in theutter next to that line.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-141">In **Counter.js**, set a breakpoint on Line 13 by clicking in the gutter next to that line.</span></span>

> ##### <span data-ttu-id="fd7e6-142">图 6</span><span class="sxs-lookup"><span data-stu-id="fd7e6-142">Figure 6</span></span>
> <span data-ttu-id="fd7e6-143">在 Visual Studio 中设置断点，方法是单击**Counter.js**中第 13 行旁边的装订线Visual Studio单击 Visual Studio 中第 13 行旁边的装订线Counter.js
> ![](./media/set-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-143">Setting a breakpoint in Visual Studio by clicking on the gutter next to Line 13 in **Counter.js**
![Setting a breakpoint in Visual Studio by clicking on the gutter next to Line 13 in Counter.js](./media/set-breakpoint.png)</span></span>  

<span data-ttu-id="fd7e6-144">现在切换回已启动的 Microsoft Edge Visual Studio实例。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-144">Now switch back to the instance of Microsoft Edge that Visual Studio launched.</span></span> <span data-ttu-id="fd7e6-145">在 **页面** 左侧的 NavMenu 中单击"计数器"。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-145">Click on **Counter** in the NavMenu on the left of the page.</span></span> <span data-ttu-id="fd7e6-146">现在单击 **"增量"。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-146">Now click **Increment**.</span></span>

> ##### <span data-ttu-id="fd7e6-147">图 7</span><span class="sxs-lookup"><span data-stu-id="fd7e6-147">Figure 7</span></span>
> <span data-ttu-id="fd7e6-148">核心 Web 应用程序中的ASP.NET核心 Web 应用程序中的"计数器"ASP.NET ![ 页](./media/edge-counter.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-148">The Counter page in our ASP.NET Core web application ![The Counter page in our ASP.NET Core web application](./media/edge-counter.png)</span></span>  

<span data-ttu-id="fd7e6-149">Visual Studio中的 JavaScript 调试器将命中我们在Counter.js\*\* 中设置的断点 \*\*。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-149">The JavaScript debugger in Visual Studio is going to hit the breakpoint we set in **Counter.js**.</span></span> <span data-ttu-id="fd7e6-150">Visual Studio Microsoft Edge 中运行的 JavaScript 已暂停执行，你可以逐行执行脚本。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-150">Visual Studio has now paused execution of the JavaScript running in Microsoft Edge and you can step through the script line-by-line.</span></span>

> ##### <span data-ttu-id="fd7e6-151">图 8</span><span class="sxs-lookup"><span data-stu-id="fd7e6-151">Figure 8</span></span>
> <span data-ttu-id="fd7e6-152">Visual Studio暂停在 Microsoft Edge 中运行的 JavaScript ![ Visual Studio暂停在 Microsoft Edge 中运行的 JavaScript](./media/hit-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-152">Visual Studio pausing JavaScript running in Microsoft Edge ![Visual Studio pausing JavaScript running in Microsoft Edge](./media/hit-breakpoint.png)</span></span>  

<span data-ttu-id="fd7e6-153">此示例只是对 Visual Studio 中可用功能的一个小Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-153">This example was just a minor demonstration of the functionality available in Visual Studio.</span></span> <span data-ttu-id="fd7e6-154">通过阅读文档了解有关 2019 年 Visual Studio可以执行的所有[操作。](/visualstudio/windows/?view=vs-2019&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-154">Learn more about all the things you can do in Visual Studio 2019 by reading [their documentation](/visualstudio/windows/?view=vs-2019&preserve-view=true).</span></span>

## <span data-ttu-id="fd7e6-155">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fd7e6-155">Attach to Microsoft Edge</span></span>
<span data-ttu-id="fd7e6-156">在上一工作流中，Visual Studio启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-156">In the previous workflow, Visual Studio launches Microsoft Edge.</span></span> <span data-ttu-id="fd7e6-157">通过此工作流，你可以将Visual Studio调试器附加到已在运行的 Microsoft Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-157">With this workflow, you will be able to attach the Visual Studio debugger to an already running instance of Microsoft Edge.</span></span> 

<span data-ttu-id="fd7e6-158">首先，确保没有正在运行的 Microsoft Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-158">First, ensure that there are no running instances of Microsoft Edge.</span></span> <span data-ttu-id="fd7e6-159">现在，从终端运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fd7e6-159">Now, from your terminal, run the following command:</span></span>

```console
start msedge –remote-debugging-port=9222
```

<span data-ttu-id="fd7e6-160">从Visual Studio，打开**调试菜单，** 然后选择 **"附加到进程"** 或按 `Ctrl`  +  `Alt`  +  `P` 。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-160">From Visual Studio, open the **Debug** menu and select **Attach to Process** or press `Ctrl` + `Alt` + `P`.</span></span>

> ##### <span data-ttu-id="fd7e6-161">图 9</span><span class="sxs-lookup"><span data-stu-id="fd7e6-161">Figure 9</span></span>
> <span data-ttu-id="fd7e6-162">选择 **"附加到进程** "Visual Studio ![ 选择"附加到进程"**Visual Studio](./media/attach-to-process.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-162">Selecting **Attach to Process** in Visual Studio ![Selecting **Attach to Process** in Visual Studio](./media/attach-to-process.png)</span></span>  

<span data-ttu-id="fd7e6-163">从"**附加到进程"** 对话框中，将**连接**类型设置为\*\*Chrome devtools 协议 websocket， (身份验证) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="fd7e6-163">From the **Attach to Process** dialog, set **Connection type** to **Chrome devtools protocol websocket (no authentication)**.</span></span> <span data-ttu-id="fd7e6-164">在" **连接目标** "文本框中，键入 `http://localhost:9222/` 并按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-164">In the **Connecting target** textbox, type in `http://localhost:9222/` and press `Enter`.</span></span> <span data-ttu-id="fd7e6-165">你应该会看到 Microsoft Edge 中已打开的选项卡列表在"附加到进程"**对话框中列出。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-165">You should see the list of open tabs you have in Microsoft Edge listed out in the **Attach to Process** dialog.</span></span>

> ##### <span data-ttu-id="fd7e6-166">图 10</span><span class="sxs-lookup"><span data-stu-id="fd7e6-166">Figure 10</span></span>
> <span data-ttu-id="fd7e6-167">在 **Visual Studio** 中配置"附加到进程"对话框 ![ Visual Studio](./media/attach-to-process-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-167">Configuring the **Attach to Process** dialog in Visual Studio ![Configuring the Attach to Process dialog in Visual Studio](./media/attach-to-process-dialog.png)</span></span>  

<span data-ttu-id="fd7e6-168">单击 **"选择...**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-168">Click **Select…**</span></span> <span data-ttu-id="fd7e6-169">并检查 \*\*JavaScript (Microsoft Edge – Chromium) \*\*。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-169">and check **JavaScript (Microsoft Edge – Chromium)**.</span></span> <span data-ttu-id="fd7e6-170">可以通过单击"刷新"按钮添加选项卡、导航到新选项卡和关闭选项卡，并查看这些更改反映在"附加到**进程"\*\*\*\*对话框中。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-170">You can add tabs, navigate to new tabs, and close tabs and see those changes reflected in the **Attach to Process** dialog by clicking the **Refresh** button.</span></span> <span data-ttu-id="fd7e6-171">选择要调试的选项卡，然后单击"附加 **"。**</span><span class="sxs-lookup"><span data-stu-id="fd7e6-171">Select the tab you want to debug and click **Attach**.</span></span>

<span data-ttu-id="fd7e6-172">现在Visual Studio调试器连接到 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="fd7e6-172">The Visual Studio debugger is now attached to Microsoft Edge!</span></span> <span data-ttu-id="fd7e6-173">您可以暂停 JavaScript 的执行、设置断点，并直接在 Visual Studio 的"调试 `console.log()` 输出"窗口中查看Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fd7e6-173">You can pause execution of JavaScript, set breakpoints, and see `console.log()` statements directly in the Debug Output window in Visual Studio.</span></span>

## <span data-ttu-id="fd7e6-174">与 Microsoft Visual Studio团队联系</span><span class="sxs-lookup"><span data-stu-id="fd7e6-174">Getting in touch with the Microsoft Visual Studio team</span></span>  

<span data-ttu-id="fd7e6-175">我们期待了解有关如何使用 JavaScript 在 Visual Studio！</span><span class="sxs-lookup"><span data-stu-id="fd7e6-175">We're eager to learn more about how you work with JavaScript in Visual Studio!</span></span>  <span data-ttu-id="fd7e6-176">Please send us feedback by clicking the **Feedback** icon in Visual Studio or by twittering [ @VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text= @VisualStudio+@EdgeDevTools) .</span><span class="sxs-lookup"><span data-stu-id="fd7e6-176">Please send us feedback by clicking the **Feedback** icon in Visual Studio or by tweeting [@VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools).</span></span>  

> ##### <span data-ttu-id="fd7e6-177">图 11</span><span class="sxs-lookup"><span data-stu-id="fd7e6-177">Figure 11</span></span>
> <span data-ttu-id="fd7e6-178">" **反馈** "图标 ![ Visual Studio"反馈"图标Visual Studio](./media/feedback-icon.png)</span><span class="sxs-lookup"><span data-stu-id="fd7e6-178">The **Feedback** icon in Visual Studio ![The Feedback icon in Visual Studio](./media/feedback-icon.png)</span></span>  
