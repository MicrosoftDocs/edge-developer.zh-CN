---
description: 如何使用元素从Microsoft Edge (Chromium) Visual Studio Code
title: 用于Microsoft Edge (Chromium) 元素Visual Studio Code
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
# <a name="microsoft-edge-devtools-for-visual-studio-code-extension"></a><span data-ttu-id="fcefc-104">Microsoft Edge用于开发人员扩展Visual Studio Code工具</span><span class="sxs-lookup"><span data-stu-id="fcefc-104">Microsoft Edge DevTools for Visual Studio Code extension</span></span>  

<span data-ttu-id="fcefc-105">用途</span><span class="sxs-lookup"><span data-stu-id="fcefc-105">Use</span></span> <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] --><span data-ttu-id="fcefc-106">此扩展用于访问 Microsoft Edge Code[内 Microsoft Visual Studio DevTools。][VisualstudioCode]</span><span class="sxs-lookup"><span data-stu-id="fcefc-106">this extension to access in Microsoft Edge DevTools inside [Microsoft Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="fcefc-107">你有权访问开发人员**工具\*\*\*\*中的元素**Microsoft Edge工具。</span><span class="sxs-lookup"><span data-stu-id="fcefc-107">You have access to the **Elements** and **Network** tools in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="fcefc-108">可以启动或附加到应用程序实例Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="fcefc-108">You may either launch or attach to an instance of Microsoft Edge.</span></span>  <span data-ttu-id="fcefc-109">连接后，你可能会显示运行时 HTML 结构、更改布局、修复样式设置问题并检查网络流量。</span><span class="sxs-lookup"><span data-stu-id="fcefc-109">After you connect you may display the runtime HTML structure, alter the layout, fix styling issues, and inspect network traffic.</span></span>  

## <a name="elements-tool"></a><span data-ttu-id="fcefc-110">元素工具</span><span class="sxs-lookup"><span data-stu-id="fcefc-110">Elements tool</span></span>  

<span data-ttu-id="fcefc-111">默认情况下，扩展将在唯一窗口中启动浏览器实例，并为你提供 DevTools \*\*\*\* Microsoft Edge功能。</span><span class="sxs-lookup"><span data-stu-id="fcefc-111">By default, the extension launches a browser instance in a unique window and gives you the **Elements** functionality of Microsoft Edge DevTools.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="Microsoft Edge用于运行Visual Studio Code浏览器窗口运行的 DevTools" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   <span data-ttu-id="fcefc-113">Microsoft Edge用于运行Visual Studio Code浏览器窗口运行的 DevTools</span><span class="sxs-lookup"><span data-stu-id="fcefc-113">Microsoft Edge DevTools for Visual Studio Code running with a full browser window</span></span>  
:::image-end:::  

<span data-ttu-id="fcefc-114">在扩展设置中，你可以启用更多功能，如无**头模式和网络**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fcefc-114">In the extension settings, you may enable more functionality like **Headless Mode** and **Network**.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="在 (设置中启用) 无头模式和网络检查" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   <span data-ttu-id="fcefc-116">在扩展 (启用 \) 或禁用\无头模式和网络检查</span><span class="sxs-lookup"><span data-stu-id="fcefc-116">Enabling \(or disabling\) headless mode and Network inspection in the extension settings</span></span>  
:::image-end:::  

## <a name="headless-mode"></a><span data-ttu-id="fcefc-117">无头模式</span><span class="sxs-lookup"><span data-stu-id="fcefc-117">Headless Mode</span></span>  

<span data-ttu-id="fcefc-118">在无头模式下，此扩展不会启动完整的浏览器实例进行调试。</span><span class="sxs-lookup"><span data-stu-id="fcefc-118">In headless mode, this extension does not launch a full browser instance to debug.</span></span>  <span data-ttu-id="fcefc-119">它在后台运行实例。</span><span class="sxs-lookup"><span data-stu-id="fcefc-119">It runs an instance in the background.</span></span>  <span data-ttu-id="fcefc-120">你可能必须停留在编辑器内并与嵌入的浏览器交互。</span><span class="sxs-lookup"><span data-stu-id="fcefc-120">You may have to stay inside the editor and interact with the embedded browser.</span></span>  <span data-ttu-id="fcefc-121">任务栏中不会显示额外的浏览器图标。</span><span class="sxs-lookup"><span data-stu-id="fcefc-121">An extra browser icon is not be displayed in your task bar.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="Microsoft Edge用于无Visual Studio Code运行的 DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   <span data-ttu-id="fcefc-123">Microsoft Edge用于使用无Visual Studio Code浏览器运行的 DevTools</span><span class="sxs-lookup"><span data-stu-id="fcefc-123">Microsoft Edge DevTools for Visual Studio Code running with a headless browser</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="fcefc-124">在 macOS 上，应打开无头模式作为首选模式。</span><span class="sxs-lookup"><span data-stu-id="fcefc-124">On macOS, you should turn on headless mode as your preferred mode.</span></span>  <span data-ttu-id="fcefc-125">使用无头模式应该可以解决一个问题，即如果窗口不可见，浏览器窗口将报告它是 `Not Active` 。</span><span class="sxs-lookup"><span data-stu-id="fcefc-125">Using headless mode should solve an issue where, if the window is not visible, the browser window reports that it is `Not Active`.</span></span>  

## <a name="network-tool"></a><span data-ttu-id="fcefc-126">网络工具</span><span class="sxs-lookup"><span data-stu-id="fcefc-126">Network tool</span></span>  

<span data-ttu-id="fcefc-127">如果还要检查应用程序的网络流量，请打开设置并打开"网络 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fcefc-127">If you also want to inspect the network traffic of your application, open the settings and turn on the **Network** tab.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge开发人员工具中的网络Visual Studio Code" lightbox="./media/edge-devtools-for-vscode-network.png":::
    <span data-ttu-id="fcefc-129">Microsoft Edge开发人员工具中的网络Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fcefc-129">Network inspection in Microsoft Edge DevTools for Visual Studio Code</span></span>  
:::image-end:::  

## <a name="launching-microsoft-edge-from-the-extension"></a><span data-ttu-id="fcefc-130">从Microsoft Edge启动</span><span class="sxs-lookup"><span data-stu-id="fcefc-130">Launching Microsoft Edge From the extension</span></span>  

<span data-ttu-id="fcefc-131">导航到Microsoft Edge栏中的"工具 **"。**</span><span class="sxs-lookup"><span data-stu-id="fcefc-131">Navigate to Microsoft Edge Tools in the **Activity Bar**.</span></span>  <span data-ttu-id="fcefc-132">旁边显示 **"Microsoft Edge：** 目标"，旁边有一个加号，用于打开应用的浏览器。</span><span class="sxs-lookup"><span data-stu-id="fcefc-132">Next to where it says **Microsoft Edge Tools: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="fcefc-133">如果选择 **"about：blank"** 选项，则必须在浏览器中导航到 Web 应用，这样它将显示在 Visual Studio Code 中的\*\*\*\*"元素"面板中。</span><span class="sxs-lookup"><span data-stu-id="fcefc-133">If you choose the **about:blank** option, you must navigate to your web app in the browser for it to appear in the **Elements** panel in Visual Studio Code.</span></span>  

## <a name="launching-microsoft-edge-from-the-debug-view"></a><span data-ttu-id="fcefc-134">从Microsoft Edge视图启动应用程序</span><span class="sxs-lookup"><span data-stu-id="fcefc-134">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="fcefc-135">如果你习惯使用调试视图中的调试Visual Studio Code，请Microsoft Edge访问 DevTools。</span><span class="sxs-lookup"><span data-stu-id="fcefc-135">If you are accustomed to using the Debug view in Visual Studio Code, access Microsoft Edge DevTools from it.</span></span>  

1.  <span data-ttu-id="fcefc-136">在Visual Studio Code中，导航到"调试"视图</span><span class="sxs-lookup"><span data-stu-id="fcefc-136">In Visual Studio Code, navigate to the Debug view</span></span> 
    *   <span data-ttu-id="fcefc-137">在 `Ctrl` + `Shift` + `D` macOS\Windows 上的 `Command` + `Shift` + `D` (/Linux \) 上选择。</span><span class="sxs-lookup"><span data-stu-id="fcefc-137">Select `Ctrl`+`Shift`+`D` on Windows/Linux  \(`Command`+`Shift`+`D` on macOS\).</span></span>  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  <span data-ttu-id="fcefc-138">如果配置中没有任何Visual Studio Code，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="fcefc-138">If you do not have any configurations in Visual Studio Code, complete one of the following actions.</span></span>  
>     *   <span data-ttu-id="fcefc-139">选择 `F5`。</span><span class="sxs-lookup"><span data-stu-id="fcefc-139">Select `F5`.</span></span>  
>     *   <span data-ttu-id="fcefc-140">选择" **播放** \ (绿色\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="fcefc-140">Choose the **Play** \(green\) button.</span></span>  
> 1.  <span data-ttu-id="fcefc-141">在下拉列表中 **，选择下拉列表** 中的"边缘"。</span><span class="sxs-lookup"><span data-stu-id="fcefc-141">In the dropdown, choose **Edge** in the dropdown.</span></span>  
> 1.  <span data-ttu-id="fcefc-142">`launch.json`应显示包含以下配置的文件。</span><span class="sxs-lookup"><span data-stu-id="fcefc-142">A `launch.json` file should be displayed that contains the following configuration.</span></span>  
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
> <span data-ttu-id="fcefc-143">加载正确配置后，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="fcefc-143">After you load the correct configuration, complete the following action.</span></span>  

1.  <span data-ttu-id="fcefc-144">若要从"**元素"Visual Studio Code，** 请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="fcefc-144">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="fcefc-145">选择 `F5`。</span><span class="sxs-lookup"><span data-stu-id="fcefc-145">Select `F5`.</span></span>  
    *   <span data-ttu-id="fcefc-146">选择" **播放** \ (绿色\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="fcefc-146">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="fcefc-147">现在，您可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="fcefc-147">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="fcefc-148">访问浏览器的屏幕视频。</span><span class="sxs-lookup"><span data-stu-id="fcefc-148">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="fcefc-149">检查页面上组件的 DOM 和样式。</span><span class="sxs-lookup"><span data-stu-id="fcefc-149">Inspect the DOM and the styling of the components on your page.</span></span>  

## <a name="attaching-to-microsoft-edge"></a><span data-ttu-id="fcefc-150">附加到Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fcefc-150">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="fcefc-151">若要打开浏览器并将实例附加到Visual Studio Code，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="fcefc-151">To open a browser and attach the instance to Visual Studio Code, complete the following steps.</span></span> 

1.  <span data-ttu-id="fcefc-152">若要打开 \Microsoft Edge \ (Chromium\) 的实例，请复制并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fcefc-152">To open an instance of Microsoft Edge \(Chromium\), copy and run the following command.</span></span>  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="fcefc-153">实例启动后，将以下代码段复制并粘贴到 `launch.json` 文件中。</span><span class="sxs-lookup"><span data-stu-id="fcefc-153">After the instance launches, copy and paste the following code snippet into your `launch.json` file.</span></span>  
    
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
    
1.  <span data-ttu-id="fcefc-154">In Visual Studio Code， open the **Debugger** drop-down menu and choose **Attach to Microsoft Edge and open the developer tools**.</span><span class="sxs-lookup"><span data-stu-id="fcefc-154">In Visual Studio Code, open the **Debugger** drop-down menu and choose **Attach to Microsoft Edge and open the developer tools**.</span></span>  
1.  <span data-ttu-id="fcefc-155">若要从"**元素"Visual Studio Code，** 请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="fcefc-155">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="fcefc-156">选择 `F5`。</span><span class="sxs-lookup"><span data-stu-id="fcefc-156">Select `F5`.</span></span>  
    *   <span data-ttu-id="fcefc-157">选择" **播放** \ (绿色\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="fcefc-157">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="fcefc-158">现在，您可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="fcefc-158">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="fcefc-159">访问浏览器的屏幕视频。</span><span class="sxs-lookup"><span data-stu-id="fcefc-159">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="fcefc-160">检查页面上组件的 DOM 和样式。</span><span class="sxs-lookup"><span data-stu-id="fcefc-160">Inspect the DOM and the styling of the components on your page.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-for-visual-studio-code-extension-team"></a><span data-ttu-id="fcefc-161">与开发人员扩展Microsoft Edge开发人员工具Visual Studio Code联系</span><span class="sxs-lookup"><span data-stu-id="fcefc-161">Getting in touch with the Microsoft Edge DevTools for Visual Studio Code extension team</span></span>  

<span data-ttu-id="fcefc-162">通过针对扩展[的][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]GitHub[提交问题来][GithubMicrosoftVscodeEdgeDevtools]发送反馈。</span><span class="sxs-lookup"><span data-stu-id="fcefc-162">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="fcefc-163">如果你需要帮助</span><span class="sxs-lookup"><span data-stu-id="fcefc-163">If you want to help make</span></span> <!--the Microsoft Edge DevTools for Visual Studio Code --><span data-ttu-id="fcefc-164">此扩展更好，欢迎您做出贡献。</span><span class="sxs-lookup"><span data-stu-id="fcefc-164">this extension better, your contributions are welcome.</span></span>  <span data-ttu-id="fcefc-165">在扩展的 GitHub[查找入门][GithubMicrosoftVscodeEdgeDevtools]所需的一切。</span><span class="sxs-lookup"><span data-stu-id="fcefc-165">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题 - microsoft/vscode-edge-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge工具Visual Studio Code"  
