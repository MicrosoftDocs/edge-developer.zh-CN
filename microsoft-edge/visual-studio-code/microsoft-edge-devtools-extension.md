---
description: 如何使用 Microsoft Edge 元素 (代码中) Chromium Visual Studio
title: Microsoft Edge 元素 (代码中) Chromium Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs code， visual studio code， 元素
ms.openlocfilehash: 83bac187fa2a9b1766a52f3f2cd176f171846e02
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398453"
---
# <a name="microsoft-edge-devtools-for-visual-studio-code-extension"></a><span data-ttu-id="b5757-104">Microsoft Edge DevTools for Visual Studio Code extension</span><span class="sxs-lookup"><span data-stu-id="b5757-104">Microsoft Edge DevTools for Visual Studio Code extension</span></span>  

<span data-ttu-id="b5757-105">用途</span><span class="sxs-lookup"><span data-stu-id="b5757-105">Use</span></span> <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] --><span data-ttu-id="b5757-106">此扩展以在 Microsoft Edge DevTools 中访问 Microsoft Visual Studio [Code。][VisualstudioCode]</span><span class="sxs-lookup"><span data-stu-id="b5757-106">this extension to access in Microsoft Edge DevTools inside [Microsoft Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="b5757-107">你有权访问 Microsoft  Edge DevTools**中的元素**和网络工具。</span><span class="sxs-lookup"><span data-stu-id="b5757-107">You have access to the **Elements** and **Network** tools in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="b5757-108">可以启动或附加到 Microsoft Edge 的实例。</span><span class="sxs-lookup"><span data-stu-id="b5757-108">You may either launch or attach to an instance of Microsoft Edge.</span></span>  <span data-ttu-id="b5757-109">连接后，可以显示运行时 HTML 结构、更改布局、修复样式设置问题以及检查网络流量。</span><span class="sxs-lookup"><span data-stu-id="b5757-109">After you connect you may display the runtime HTML structure, alter the layout, fix styling issues, and inspect network traffic.</span></span>  

## <a name="elements-tool"></a><span data-ttu-id="b5757-110">元素工具</span><span class="sxs-lookup"><span data-stu-id="b5757-110">Elements tool</span></span>  

<span data-ttu-id="b5757-111">默认情况下，扩展将在唯一窗口中启动浏览器实例，并为你提供 Microsoft Edge  DevTools 的元素功能。</span><span class="sxs-lookup"><span data-stu-id="b5757-111">By default, the extension launches a browser instance in a unique window and gives you the **Elements** functionality of Microsoft Edge DevTools.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="Microsoft Edge DevTools for Visual Studio在完整浏览器窗口中运行的代码" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   <span data-ttu-id="b5757-113">Microsoft Edge DevTools for Visual Studio在完整浏览器窗口中运行的代码</span><span class="sxs-lookup"><span data-stu-id="b5757-113">Microsoft Edge DevTools for Visual Studio Code running with a full browser window</span></span>  
:::image-end:::  

<span data-ttu-id="b5757-114">在扩展设置中，你可以启用更多功能，如无**头模式和网络**。 </span><span class="sxs-lookup"><span data-stu-id="b5757-114">In the extension settings, you may enable more functionality like **Headless Mode** and **Network**.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="在 (设置中启用) 无头模式和网络检查" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   <span data-ttu-id="b5757-116">启用 \(或禁用\) 扩展设置中的无头模式和网络检查</span><span class="sxs-lookup"><span data-stu-id="b5757-116">Enabling \(or disabling\) headless mode and Network inspection in the extension settings</span></span>  
:::image-end:::  

## <a name="headless-mode"></a><span data-ttu-id="b5757-117">无头模式</span><span class="sxs-lookup"><span data-stu-id="b5757-117">Headless Mode</span></span>  

<span data-ttu-id="b5757-118">在无头模式下，此扩展不会启动完整的浏览器实例进行调试。</span><span class="sxs-lookup"><span data-stu-id="b5757-118">In headless mode, this extension does not launch a full browser instance to debug.</span></span>  <span data-ttu-id="b5757-119">它在后台运行实例。</span><span class="sxs-lookup"><span data-stu-id="b5757-119">It runs an instance in the background.</span></span>  <span data-ttu-id="b5757-120">你可能必须留在编辑器内并与嵌入的浏览器交互。</span><span class="sxs-lookup"><span data-stu-id="b5757-120">You may have to stay inside the editor and interact with the embedded browser.</span></span>  <span data-ttu-id="b5757-121">任务栏中不显示额外的浏览器图标。</span><span class="sxs-lookup"><span data-stu-id="b5757-121">An extra browser icon is not be displayed in your task bar.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="用于无Visual Studio运行的代码的 Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   <span data-ttu-id="b5757-123">用于无Visual Studio运行的代码的 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="b5757-123">Microsoft Edge DevTools for Visual Studio Code running with a headless browser</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b5757-124">在 macOS 上，应打开无头模式作为首选模式。</span><span class="sxs-lookup"><span data-stu-id="b5757-124">On macOS, you should turn on headless mode as your preferred mode.</span></span>  <span data-ttu-id="b5757-125">使用无头模式应解决一个问题，如果窗口不可见，浏览器窗口将报告它 `Not Active` 。</span><span class="sxs-lookup"><span data-stu-id="b5757-125">Using headless mode should solve an issue where, if the window is not visible, the browser window reports that it is `Not Active`.</span></span>  

## <a name="network-tool"></a><span data-ttu-id="b5757-126">网络工具</span><span class="sxs-lookup"><span data-stu-id="b5757-126">Network tool</span></span>  

<span data-ttu-id="b5757-127">如果还要检查应用程序的网络流量，请打开设置并打开"网络 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5757-127">If you also want to inspect the network traffic of your application, open the settings and turn on the **Network** tab.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge DevTools for Visual Studio 中的网络检查" lightbox="./media/edge-devtools-for-vscode-network.png":::
    <span data-ttu-id="b5757-129">Microsoft Edge DevTools for Visual Studio 中的网络检查</span><span class="sxs-lookup"><span data-stu-id="b5757-129">Network inspection in Microsoft Edge DevTools for Visual Studio Code</span></span>  
:::image-end:::  

## <a name="launching-microsoft-edge-from-the-extension"></a><span data-ttu-id="b5757-130">从扩展启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b5757-130">Launching Microsoft Edge From the extension</span></span>  

<span data-ttu-id="b5757-131">导航到活动栏中的 Microsoft Edge **工具**。</span><span class="sxs-lookup"><span data-stu-id="b5757-131">Navigate to Microsoft Edge Tools in the **Activity Bar**.</span></span>  <span data-ttu-id="b5757-132">旁边显示 **"Microsoft Edge 工具： 目标"，** 旁边有一个为你的应用打开浏览器的加号。</span><span class="sxs-lookup"><span data-stu-id="b5757-132">Next to where it says **Microsoft Edge Tools: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="b5757-133">如果选择 **"about：blank"** 选项，则必须在浏览器中导航到 Web 应用，以在"代码"中的" 元素"Visual Studio中显示。</span><span class="sxs-lookup"><span data-stu-id="b5757-133">If you choose the **about:blank** option, you must navigate to your web app in the browser for it to appear in the **Elements** panel in Visual Studio Code.</span></span>  

## <a name="launching-microsoft-edge-from-the-debug-view"></a><span data-ttu-id="b5757-134">从调试视图启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b5757-134">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="b5757-135">如果你习惯在代码中使用调试Visual Studio，请从它访问 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="b5757-135">If you are accustomed to using the Debug view in Visual Studio Code, access Microsoft Edge DevTools from it.</span></span>  

1.  <span data-ttu-id="b5757-136">在Visual Studio中，导航到"调试"视图</span><span class="sxs-lookup"><span data-stu-id="b5757-136">In Visual Studio Code, navigate to the Debug view</span></span> 
    *   <span data-ttu-id="b5757-137">在 `Ctrl` + `Shift` + `D` windows/Linux \(`Command` + `Shift` + `D` macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="b5757-137">Select `Ctrl`+`Shift`+`D` on Windows/Linux  \(`Command`+`Shift`+`D` on macOS\).</span></span>  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  <span data-ttu-id="b5757-138">如果代码中没有任何配置Visual Studio，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="b5757-138">If you do not have any configurations in Visual Studio Code, complete one of the following actions.</span></span>  
>     *   <span data-ttu-id="b5757-139">选择 `F5`。</span><span class="sxs-lookup"><span data-stu-id="b5757-139">Select `F5`.</span></span>  
>     *   <span data-ttu-id="b5757-140">选择 **"播放** \(绿色\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="b5757-140">Choose the **Play** \(green\) button.</span></span>  
> 1.  <span data-ttu-id="b5757-141">在下拉列表中，选择 **下拉列表** 中的"边缘"。</span><span class="sxs-lookup"><span data-stu-id="b5757-141">In the dropdown, choose **Edge** in the dropdown.</span></span>  
> 1.  <span data-ttu-id="b5757-142">应 `launch.json` 显示包含以下配置的文件。</span><span class="sxs-lookup"><span data-stu-id="b5757-142">A `launch.json` file should be displayed that contains the following configuration.</span></span>  
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
> <span data-ttu-id="b5757-143">加载正确的配置后，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="b5757-143">After you load the correct configuration, complete the following action.</span></span>  

1.  <span data-ttu-id="b5757-144">若要 **从代码Visual Studio** 元素工具，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="b5757-144">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="b5757-145">选择 `F5`。</span><span class="sxs-lookup"><span data-stu-id="b5757-145">Select `F5`.</span></span>  
    *   <span data-ttu-id="b5757-146">选择 **"播放** \(绿色\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="b5757-146">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="b5757-147">现在，您可以执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="b5757-147">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="b5757-148">访问浏览器的屏幕视频。</span><span class="sxs-lookup"><span data-stu-id="b5757-148">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="b5757-149">检查页面上组件的 DOM 和样式。</span><span class="sxs-lookup"><span data-stu-id="b5757-149">Inspect the DOM and the styling of the components on your page.</span></span>  

## <a name="attaching-to-microsoft-edge"></a><span data-ttu-id="b5757-150">附加到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b5757-150">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="b5757-151">若要打开浏览器并将该实例附加到Visual Studio代码，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b5757-151">To open a browser and attach the instance to Visual Studio Code, complete the following steps.</span></span> 

1.  <span data-ttu-id="b5757-152">若要打开 Microsoft Edge \(Chromium\) 的实例，请复制并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b5757-152">To open an instance of Microsoft Edge \(Chromium\), copy and run the following command.</span></span>  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="b5757-153">实例启动后，将以下代码段复制并粘贴到 `launch.json` 文件中。</span><span class="sxs-lookup"><span data-stu-id="b5757-153">After the instance launches, copy and paste the following code snippet into your `launch.json` file.</span></span>  
    
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
    
1.  <span data-ttu-id="b5757-154">在Visual Studio中，打开 **调试** 器下拉菜单，然后选择"附加到 **Microsoft Edge"，然后打开开发人员工具**。</span><span class="sxs-lookup"><span data-stu-id="b5757-154">In Visual Studio Code, open the **Debugger** drop-down menu and choose **Attach to Microsoft Edge and open the developer tools**.</span></span>  
1.  <span data-ttu-id="b5757-155">若要 **从代码Visual Studio** 元素工具，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="b5757-155">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="b5757-156">选择 `F5`。</span><span class="sxs-lookup"><span data-stu-id="b5757-156">Select `F5`.</span></span>  
    *   <span data-ttu-id="b5757-157">选择 **"播放** \(绿色\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="b5757-157">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="b5757-158">现在，您可以执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="b5757-158">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="b5757-159">访问浏览器的屏幕视频。</span><span class="sxs-lookup"><span data-stu-id="b5757-159">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="b5757-160">检查页面上组件的 DOM 和样式。</span><span class="sxs-lookup"><span data-stu-id="b5757-160">Inspect the DOM and the styling of the components on your page.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-for-visual-studio-code-extension-team"></a><span data-ttu-id="b5757-161">联系 Microsoft Edge 开发人员工具Visual Studio代码扩展团队</span><span class="sxs-lookup"><span data-stu-id="b5757-161">Getting in touch with the Microsoft Edge DevTools for Visual Studio Code extension team</span></span>  

<span data-ttu-id="b5757-162">通过针对扩展 [的][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] [GitHub 存储库][GithubMicrosoftVscodeEdgeDevtools] 提交问题来发送反馈。</span><span class="sxs-lookup"><span data-stu-id="b5757-162">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="b5757-163">如果你想要帮助创建</span><span class="sxs-lookup"><span data-stu-id="b5757-163">If you want to help make</span></span> <!--the Microsoft Edge DevTools for Visual Studio Code --><span data-ttu-id="b5757-164">此扩展效果更好，欢迎你做出贡献。</span><span class="sxs-lookup"><span data-stu-id="b5757-164">this extension better, your contributions are welcome.</span></span>  <span data-ttu-id="b5757-165">在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDevtools] 存储库中查找入门所需的一切。</span><span class="sxs-lookup"><span data-stu-id="b5757-165">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio代码"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题 - microsoft/vscode-edge-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code"  
