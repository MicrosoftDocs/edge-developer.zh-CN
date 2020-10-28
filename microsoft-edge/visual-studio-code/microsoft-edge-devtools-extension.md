---
description: '如何使用 Microsoft Edge 的元素 (Chromium Visual Studio 代码中的) '
title: 'Microsoft Edge 的元素 (Chromium 从 Visual Studio 代码中) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、元素
ms.openlocfilehash: 81488c08a76a16b80a415cbd17cd0617df916f54
ms.sourcegitcommit: 1cfcf2c8970a6c2221cfbf09a23d36b08bd60690
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135478"
---
# <span data-ttu-id="1cfde-104">适用于 Visual Studio 代码扩展的 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="1cfde-104">Microsoft Edge DevTools for Visual Studio Code extension</span></span>  

<span data-ttu-id="1cfde-105">用途</span><span class="sxs-lookup"><span data-stu-id="1cfde-105">Use</span></span> <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] --><span data-ttu-id="1cfde-106">此扩展可在 Microsoft Edge DevTools 中访问 [Visual Studio 代码][VisualstudioCode]内部。</span><span class="sxs-lookup"><span data-stu-id="1cfde-106">this extension to access in Microsoft Edge DevTools inside [Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="1cfde-107">你有权访问 Microsoft Edge DevTools 中的 **元素** 和 **网络** 工具。</span><span class="sxs-lookup"><span data-stu-id="1cfde-107">You have access to the **Elements** and **Network** tools in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="1cfde-108">你可以启动或附加到 Microsoft Edge 实例。</span><span class="sxs-lookup"><span data-stu-id="1cfde-108">You may either launch or attach to an instance of Microsoft Edge.</span></span>  <span data-ttu-id="1cfde-109">连接后，你可能会显示运行时 HTML 结构、更改布局、修复样式设置问题以及检查网络流量。</span><span class="sxs-lookup"><span data-stu-id="1cfde-109">After you connect you may display the runtime HTML structure, alter the layout, fix styling issues, and inspect network traffic.</span></span>  

## <span data-ttu-id="1cfde-110">元素工具</span><span class="sxs-lookup"><span data-stu-id="1cfde-110">Elements tool</span></span>  

<span data-ttu-id="1cfde-111">默认情况下，扩展在唯一窗口中启动浏览器实例，并向你提供 Microsoft Edge DevTools 的 **元素** 功能。</span><span class="sxs-lookup"><span data-stu-id="1cfde-111">By default, the extension launches a browser instance in a unique window and gives you the **Elements** functionality of Microsoft Edge DevTools.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="Microsoft Edge DevTools 适用于使用完整浏览器窗口运行的 Visual Studio 代码" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   <span data-ttu-id="1cfde-113">Microsoft Edge DevTools 适用于使用完整浏览器窗口运行的 Visual Studio 代码</span><span class="sxs-lookup"><span data-stu-id="1cfde-113">Microsoft Edge DevTools for Visual Studio Code running with a full browser window</span></span>  
:::image-end:::  

<span data-ttu-id="1cfde-114">在扩展设置中，你可以启用多个功能，如无 **外设模式** 和 **网络**。</span><span class="sxs-lookup"><span data-stu-id="1cfde-114">In the extension settings, you may enable more functionality like **Headless Mode** and **Network**.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="启用 (或禁用扩展设置中) 无外设模式和网络检查" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   <span data-ttu-id="1cfde-116">在扩展设置中启用 \ (或禁用 \ ) 无外设模式和网络检查</span><span class="sxs-lookup"><span data-stu-id="1cfde-116">Enabling \(or disabling\) headless mode and Network inspection in the extension settings</span></span>  
:::image-end:::  

## <span data-ttu-id="1cfde-117">无外设模式</span><span class="sxs-lookup"><span data-stu-id="1cfde-117">Headless Mode</span></span>  

<span data-ttu-id="1cfde-118">在无外设模式下，此扩展不启动要调试的完整浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="1cfde-118">In headless mode, this extension does not launch a full browser instance to debug.</span></span>  <span data-ttu-id="1cfde-119">它在后台运行实例。</span><span class="sxs-lookup"><span data-stu-id="1cfde-119">It runs an instance in the background.</span></span>  <span data-ttu-id="1cfde-120">您可能必须在编辑器内，并与嵌入的浏览器交互。</span><span class="sxs-lookup"><span data-stu-id="1cfde-120">You may have to stay inside the editor and interact with the embedded browser.</span></span>  <span data-ttu-id="1cfde-121">额外的浏览器图标不会显示在任务栏中。</span><span class="sxs-lookup"><span data-stu-id="1cfde-121">An extra browser icon is not be displayed in your task bar.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="Microsoft Edge DevTools 用于使用无外设运行的 Visual Studio 代码" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   <span data-ttu-id="1cfde-123">Microsoft Edge DevTools 用于使用无外设浏览器运行的 Visual Studio 代码</span><span class="sxs-lookup"><span data-stu-id="1cfde-123">Microsoft Edge DevTools for Visual Studio Code running with a headless browser</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="1cfde-124">在 macOS 上，你应将无外设模式启用为你的首选模式。</span><span class="sxs-lookup"><span data-stu-id="1cfde-124">On macOS, you should turn on headless mode as your preferred mode.</span></span>  <span data-ttu-id="1cfde-125">使用无外设模式应解决以下问题：如果窗口不可见，浏览器窗口会报告它 `Not Active` 。</span><span class="sxs-lookup"><span data-stu-id="1cfde-125">Using headless mode should solve an issue where, if the window is not visible, the browser window reports that it is `Not Active`.</span></span>  

## <span data-ttu-id="1cfde-126">网络工具</span><span class="sxs-lookup"><span data-stu-id="1cfde-126">Network tool</span></span>  

<span data-ttu-id="1cfde-127">如果你还想要检查你的应用程序的网络流量，请打开 "设置"，然后打开 " **网络** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1cfde-127">If you also want to inspect the network traffic of your application, open the settings and turn on the **Network** tab.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge DevTools 中用于 Visual Studio 代码的网络检查" lightbox="./media/edge-devtools-for-vscode-network.png":::
    <span data-ttu-id="1cfde-129">Microsoft Edge DevTools 中用于 Visual Studio 代码的网络检查</span><span class="sxs-lookup"><span data-stu-id="1cfde-129">Network inspection in Microsoft Edge DevTools for Visual Studio Code</span></span>  
:::image-end:::  

## <span data-ttu-id="1cfde-130">从扩展启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1cfde-130">Launching Microsoft Edge From the extension</span></span>  

<span data-ttu-id="1cfde-131">导航到 **活动栏**中的 "Microsoft Edge 工具"。</span><span class="sxs-lookup"><span data-stu-id="1cfde-131">Navigate to Microsoft Edge Tools in the **Activity Bar**.</span></span>  <span data-ttu-id="1cfde-132">在它所显示的 **Microsoft Edge 工具：目标** 的位置旁边有一个加号，用于为你的应用打开浏览器。</span><span class="sxs-lookup"><span data-stu-id="1cfde-132">Next to where it says **Microsoft Edge Tools: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="1cfde-133">如果选择 " **关于：空白** " 选项，则必须导航到浏览器中的 web 应用，以使其显示在 Visual Studio 代码的 " **元素** " 面板中。</span><span class="sxs-lookup"><span data-stu-id="1cfde-133">If you choose the **about:blank** option, you must navigate to your web app in the browser for it to appear in the **Elements** panel in Visual Studio Code.</span></span>  

## <span data-ttu-id="1cfde-134">从 "调试" 视图启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1cfde-134">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="1cfde-135">如果你习惯在 Visual Studio 代码中使用 "调试" 视图，请访问 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="1cfde-135">If you are accustomed to using the Debug view in Visual Studio Code, access Microsoft Edge DevTools from it.</span></span>  

1.  <span data-ttu-id="1cfde-136">在 Visual Studio 代码中，导航到 "调试" 视图</span><span class="sxs-lookup"><span data-stu-id="1cfde-136">In Visual Studio Code, navigate to the Debug view</span></span> 
    *   <span data-ttu-id="1cfde-137">在 `Ctrl` + `Shift` + `D` `Command` + `Shift` + `D` macOS \ ) 上选择 "在 Windows/Linux \ (上"。</span><span class="sxs-lookup"><span data-stu-id="1cfde-137">Select `Ctrl`+`Shift`+`D` on Windows/Linux  \(`Command`+`Shift`+`D` on macOS\).</span></span>  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  <span data-ttu-id="1cfde-138">如果 Visual Studio 代码中没有任何配置，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="1cfde-138">If you do not have any configurations in Visual Studio Code, complete one of the following actions.</span></span>  
>     *   <span data-ttu-id="1cfde-139">选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="1cfde-139">Select `F5`.</span></span>  
>     *   <span data-ttu-id="1cfde-140">选择 " **播放** \ (绿色 \ ) " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1cfde-140">Choose the **Play** \(green\) button.</span></span>  
> 1.  <span data-ttu-id="1cfde-141">在下拉列表中，选择下拉列表中的 " **边缘** "。</span><span class="sxs-lookup"><span data-stu-id="1cfde-141">In the dropdown, choose **Edge** in the dropdown.</span></span>  
> 1.  <span data-ttu-id="1cfde-142">`launch.json`应显示包含以下配置的文件。</span><span class="sxs-lookup"><span data-stu-id="1cfde-142">A `launch.json` file should be displayed that contains the following configuration.</span></span>  
>     
>     ```json
>     {
>       "version": "0.2.0",
>       "configurations": [
>         {
>           "name": "Launch Microsoft Edge and open the Edge DevTools",
>           "request": "launch",
>           "type": "vscode-edge-devtools.debug",
>           "url": "http://localhost:8080"
>         }
>       ]
>     }
>     ```  
>     
> <span data-ttu-id="1cfde-143">加载正确的配置后，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="1cfde-143">After you load the correct configuration, complete the following action.</span></span>  

1.  <span data-ttu-id="1cfde-144">若要从 Visual Studio 代码启动 **元素** 工具，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="1cfde-144">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="1cfde-145">选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="1cfde-145">Select `F5`.</span></span>  
    *   <span data-ttu-id="1cfde-146">选择 " **播放** \ (绿色 \ ) " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1cfde-146">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="1cfde-147">现在，你可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="1cfde-147">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="1cfde-148">访问浏览器的说明截屏视频。</span><span class="sxs-lookup"><span data-stu-id="1cfde-148">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="1cfde-149">检查页面上组件的 DOM 和样式。</span><span class="sxs-lookup"><span data-stu-id="1cfde-149">Inspect the DOM and the styling of the components on your page.</span></span>  

## <span data-ttu-id="1cfde-150">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1cfde-150">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="1cfde-151">若要打开浏览器并将实例附加到 Visual Studio 代码，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1cfde-151">To open a browser and attach the instance to Visual Studio Code, complete the following steps.</span></span> 

1.  <span data-ttu-id="1cfde-152">若要打开 Microsoft Edge \ (Chromium \ ) 的实例，请复制并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1cfde-152">To open an instance of Microsoft Edge \(Chromium\), copy and run the following command.</span></span>  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="1cfde-153">实例启动后，将以下代码片段复制并粘贴到您的 `launch.json` 文件中。</span><span class="sxs-lookup"><span data-stu-id="1cfde-153">After the instance launches, copy and paste the following code snippet into your `launch.json` file.</span></span>  
    
    ```json
    {
        "type": "vscode-edge-devtools.debug",
        "request": "attach",
        "name": "Attach to Microsoft Edge and open the developer tools",
        "url": "http://localhost:3000/",
        "webRoot": "${workspaceFolder}/out",
        "port": 9222
    }
    ```  
    
1.  <span data-ttu-id="1cfde-154">在 Visual Studio 代码中，打开 " **调试器** " 下拉菜单，然后选择 **"附加到 Microsoft Edge" 并打开 "开发工具工具"**。</span><span class="sxs-lookup"><span data-stu-id="1cfde-154">In Visual Studio Code, open the **Debugger** drop-down menu and choose **Attach to Microsoft Edge and open the developer tools**.</span></span>  
1.  <span data-ttu-id="1cfde-155">若要从 Visual Studio 代码启动 **元素** 工具，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="1cfde-155">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="1cfde-156">选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="1cfde-156">Select `F5`.</span></span>  
    *   <span data-ttu-id="1cfde-157">选择 " **播放** \ (绿色 \ ) " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1cfde-157">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="1cfde-158">现在，你可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="1cfde-158">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="1cfde-159">访问浏览器的说明截屏视频。</span><span class="sxs-lookup"><span data-stu-id="1cfde-159">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="1cfde-160">检查页面上组件的 DOM 和样式。</span><span class="sxs-lookup"><span data-stu-id="1cfde-160">Inspect the DOM and the styling of the components on your page.</span></span>  
    
## <span data-ttu-id="1cfde-161">与 Microsoft Edge DevTools for Visual Studio 代码扩展团队取得联系</span><span class="sxs-lookup"><span data-stu-id="1cfde-161">Getting in touch with the Microsoft Edge DevTools for Visual Studio Code extension team</span></span>  

<span data-ttu-id="1cfde-162">通过针对扩展的[GitHub][GithubMicrosoftVscodeEdgeDevtools]存储库将[问题归档][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]来发送反馈。</span><span class="sxs-lookup"><span data-stu-id="1cfde-162">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="1cfde-163">如果您希望帮助实现</span><span class="sxs-lookup"><span data-stu-id="1cfde-163">If you want to help make</span></span> <!--the Microsoft Edge DevTools for Visual Studio Code --><span data-ttu-id="1cfde-164">此扩展更好，您的发布内容是欢迎。</span><span class="sxs-lookup"><span data-stu-id="1cfde-164">this extension better, your contributions are welcome.</span></span>  <span data-ttu-id="1cfde-165">在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDevtools] 存储库中查找您需要的所有内容。</span><span class="sxs-lookup"><span data-stu-id="1cfde-165">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题-microsoft/vscode-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "适用于 VS 代码的 Microsoft Edge 工具"  
