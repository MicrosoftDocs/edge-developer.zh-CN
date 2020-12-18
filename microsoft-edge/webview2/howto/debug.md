---
description: 了解如何调试 WebView2 控件。
title: 开始调试 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 4f94fe880f66f8aeb387d2db4a8bfaab20699466
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230696"
---
# <span data-ttu-id="5bd62-104">开始调试 WebView2 应用程序</span><span class="sxs-lookup"><span data-stu-id="5bd62-104">Get started debugging WebView2 applications</span></span>  

<span data-ttu-id="5bd62-105">Microsoft Edge WebView2 控件的目标是将 Web 和本机应用程序开发功能和工具的最佳组合在一起。</span><span class="sxs-lookup"><span data-stu-id="5bd62-105">The goal of the Microsoft Edge WebView2 control is to combine the best of both the web and native application development features and tools.</span></span>  <span data-ttu-id="5bd62-106">开发 WebView2 应用程序时，应调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bd62-106">When you develop your WebView2 application, you should debug your application.</span></span>  <span data-ttu-id="5bd62-107">本文概述了用于调试 Web 和 WebView2 应用程序中的本机代码的不同工具。</span><span class="sxs-lookup"><span data-stu-id="5bd62-107">This article outlines the different tools to use to debug both your web and native code in your WebView2 application.</span></span>  

## [<span data-ttu-id="5bd62-108">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="5bd62-108">Microsoft Edge DevTools</span></span>](#tab/devtools)  

<span data-ttu-id="5bd62-109">使用 [Microsoft Edge (Chromium) 开发人员][DevtoolsGuideChromiumMain] 工具调试 WebView2 控件中显示的 Web 内容，方法与调试 Microsoft Edge 中显示的其他网页的方式相同。</span><span class="sxs-lookup"><span data-stu-id="5bd62-109">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you may debug for another webpage displayed in Microsoft Edge.</span></span>  <span data-ttu-id="5bd62-110">若要打开 DevTools，请设置 WebView 控件的焦点，然后使用以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="5bd62-110">To open the DevTools, set focus on the WebView control and then use one of the following actions.</span></span>  

*   <span data-ttu-id="5bd62-111">选择 `F12`。</span><span class="sxs-lookup"><span data-stu-id="5bd62-111">Select `F12`.</span></span>  
*   <span data-ttu-id="5bd62-112">选择 `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="5bd62-112">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="5bd62-113">打开上下文菜单 \ (右键单击\) 并选择 `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="5bd62-113">Open the context menu \(right-click\) and choose `Inspect`.</span></span>  
    
<span data-ttu-id="5bd62-114">有关详细信息，请参阅 [DevTools 概述][DevtoolsGuideChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="5bd62-114">For more information, see [DevTools overview][DevtoolsGuideChromiumMain].</span></span>  

:::image type="complex" source="./media/f12.png" alt-text="DevTools 调试" lightbox="./media/f12.png":::
   <span data-ttu-id="5bd62-116">DevTools 调试</span><span class="sxs-lookup"><span data-stu-id="5bd62-116">DevTools debugging</span></span>  
:::image-end:::  

## [<span data-ttu-id="5bd62-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5bd62-117">Visual Studio</span></span>](#tab/visualstudio)  

<span data-ttu-id="5bd62-118">Visual Studio WebView2 应用程序中为 Web 和本机代码提供各种调试工具。</span><span class="sxs-lookup"><span data-stu-id="5bd62-118">Visual Studio provides various debugging tools for web and native code in WebView2 applications.</span></span>  <span data-ttu-id="5bd62-119">在Visual Studio部分中，主要焦点是调试 WebView 控件，但其他调试方法Visual Studio一样可用。</span><span class="sxs-lookup"><span data-stu-id="5bd62-119">In the Visual Studio section, the primary focus is debugging WebView controls, however the other methods of debugging in Visual Studio are available as usual.</span></span>  <span data-ttu-id="5bd62-120">使用以下过程仅调试 Win32 应用程序或 Office 外接程序中的 Web 和本机代码。</span><span class="sxs-lookup"><span data-stu-id="5bd62-120">Use the following process to debug web and native code in Win32 applications or Office Add-ins only.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="5bd62-121">在附加了本机调试Visual Studio中调试应用程序时，选择可能会触发本机 `F12` 调试程序，而不是开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="5bd62-121">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="5bd62-122">Select `Ctrl` + `Shift` + `I` ， or use the context menu \ (right-click\) to avoid the situation.</span><span class="sxs-lookup"><span data-stu-id="5bd62-122">Select `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

<span data-ttu-id="5bd62-123">开始之前，请确保满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="5bd62-123">Before you begin, ensure the following requirements are met.</span></span>  

*   <span data-ttu-id="5bd62-124">若要调试脚本，必须在应用程序内启动Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="5bd62-124">To debug scripts, the app must be launched from within Visual Studio.</span></span>  
*   <span data-ttu-id="5bd62-125">无法将调试器附加到正在运行的 WebView2 进程。</span><span class="sxs-lookup"><span data-stu-id="5bd62-125">You cannot attach a debugger to a running WebView2 process.</span></span>  
*   <span data-ttu-id="5bd62-126">安装 Visual Studio 2019 版本 16.4 Preview 2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5bd62-126">Install Visual Studio 2019 version 16.4 Preview 2 or later.</span></span>  
    
<span data-ttu-id="5bd62-127">安装和设置脚本调试器工具Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="5bd62-127">Install and set up the script debugger tools in Visual Studio.</span></span>  

1.  <span data-ttu-id="5bd62-128">完成以下操作以使用 C++ 在桌面开发中安装 **JavaScript** **诊断组件**。</span><span class="sxs-lookup"><span data-stu-id="5bd62-128">Complete the following actions to install the **JavaScript diagnostics** component in **Desktop development with C++**.</span></span>  
    
    1.  <span data-ttu-id="5bd62-129">在 Windows 资源管理器栏中，键入 `Visual Studio Installer` 。</span><span class="sxs-lookup"><span data-stu-id="5bd62-129">In the Windows Explorer bar, type `Visual Studio Installer`.</span></span>  
    1.  <span data-ttu-id="5bd62-130">选择 **Visual Studio安装程序** 打开它。</span><span class="sxs-lookup"><span data-stu-id="5bd62-130">Choose **Visual Studio Installer** to open it.</span></span>  
    1.  <span data-ttu-id="5bd62-131">在Visual Studio安装程序中，在已安装的版本上，选择"更多 **"按钮，** 然后选择"修改 **"。**</span><span class="sxs-lookup"><span data-stu-id="5bd62-131">In the Visual Studio Installer, on the installed version, choose the **More** button, and then choose **Modify**.</span></span>  
    1.  <span data-ttu-id="5bd62-132">In Visual Studio， under **Workloads，** choose the **Desktop Development in C++** setting.</span><span class="sxs-lookup"><span data-stu-id="5bd62-132">In Visual Studio, under **Workloads**, choose the **Desktop Development in C++** setting.</span></span>  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio修改工作负载屏幕" lightbox="./media/workloads.png":::
            <span data-ttu-id="5bd62-134">Visual Studio修改工作负载屏幕</span><span class="sxs-lookup"><span data-stu-id="5bd62-134">Visual Studio Modifying Workloads Screen</span></span>
        :::image-end:::  
        
    1.  <span data-ttu-id="5bd62-135">选择 **单个组件**。</span><span class="sxs-lookup"><span data-stu-id="5bd62-135">Choose **Individual components**.</span></span>  
    1.  <span data-ttu-id="5bd62-136">在搜索框中，输入 `JavaScript diagnostics` 。</span><span class="sxs-lookup"><span data-stu-id="5bd62-136">In the search box, enter `JavaScript diagnostics`.</span></span>  
    1.  <span data-ttu-id="5bd62-137">选择 **JavaScript 诊断** 设置。</span><span class="sxs-lookup"><span data-stu-id="5bd62-137">Choose the **JavaScript diagnostics** setting.</span></span>  
    1.  <span data-ttu-id="5bd62-138">选择 **"修改"。**</span><span class="sxs-lookup"><span data-stu-id="5bd62-138">Choose **Modify**.</span></span> 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studio"修改单个组件"选项卡" lightbox="./media/indivcomp.png":::
           <span data-ttu-id="5bd62-140">Visual Studio"修改单个组件"选项卡</span><span class="sxs-lookup"><span data-stu-id="5bd62-140">Visual Studio Modifying Individual Components Tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="5bd62-141">为 WebView2 应用程序启用脚本调试。</span><span class="sxs-lookup"><span data-stu-id="5bd62-141">Enable script debugging for WebView2 applications.</span></span>  
    1.  <span data-ttu-id="5bd62-142">在 WebView2 项目中，打开上下文菜单 \ (右键单击\) ，然后选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="5bd62-142">In your WebView2 project, open the context menu \(right-click\), and choose **Properties**.</span></span>  
    1.  <span data-ttu-id="5bd62-143">在"**配置属性"下**，选择 **"调试"。**</span><span class="sxs-lookup"><span data-stu-id="5bd62-143">Under the **Configuration Properties**, choose **Debugging**.</span></span>  
    1.  <span data-ttu-id="5bd62-144">在**调试器类型下**，选择\*\*JavaScript (WebView2) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="5bd62-144">Under the **Debugger Type**, choose **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studio调试配置属性" lightbox="./media/enbjs.png":::
           <span data-ttu-id="5bd62-146">Visual Studio **调试** 配置属性</span><span class="sxs-lookup"><span data-stu-id="5bd62-146">Visual Studio **Debugging** Configuration Property</span></span>  
        :::image-end:::  
        
<span data-ttu-id="5bd62-147">完成以下操作以调试 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bd62-147">Complete the following actions to debug your WebView2 application.</span></span>  

1.  <span data-ttu-id="5bd62-148">若要在源代码中设置断点，请将鼠标悬停在行号左侧，然后选择设置断点。</span><span class="sxs-lookup"><span data-stu-id="5bd62-148">To set a breakpoint in your source code, hover to the left of the line number, and choose to set a breakpoint.</span></span>  <span data-ttu-id="5bd62-149">JS/TS 调试适配器不执行源路径映射。</span><span class="sxs-lookup"><span data-stu-id="5bd62-149">The JS/TS debug adapter does not perform source path mapping.</span></span>  <span data-ttu-id="5bd62-150">必须打开与 WebView2 关联的完全相同的路径。</span><span class="sxs-lookup"><span data-stu-id="5bd62-150">You must open the exact same path associated with your WebView2.</span></span>  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studio断点" lightbox="./media/breakpoint.png"::: 
       <span data-ttu-id="5bd62-152">Visual Studio断点</span><span class="sxs-lookup"><span data-stu-id="5bd62-152">Visual Studio add breakpoint</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5bd62-153">若要运行调试器，请选择平台的位大小，然后选择本地 Windows 调试器旁边的绿色播放 **按钮**。</span><span class="sxs-lookup"><span data-stu-id="5bd62-153">To run the debugger, choose the bit size of the platform, and then choose the green play button next to **Local Windows Debugger**.</span></span>  <span data-ttu-id="5bd62-154">应用程序运行，调试程序连接到创建的第一个 WebView2 进程。</span><span class="sxs-lookup"><span data-stu-id="5bd62-154">The application runs and the debugger connects to the first WebView2 process that is created.</span></span>  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio Windows 调试器" lightbox="./media/run.png"::: 
       <span data-ttu-id="5bd62-156">Visual Studio Windows **调试器**</span><span class="sxs-lookup"><span data-stu-id="5bd62-156">Visual Studio **Local Windows Debugger**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5bd62-157">在 **调试控制台中**，从调试器中查找输出。</span><span class="sxs-lookup"><span data-stu-id="5bd62-157">In the **Debug Console**, find the output from the debugger.</span></span>  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio调试控制台" lightbox="./media/console.png"::: 
       <span data-ttu-id="5bd62-159">Visual Studio **调试控制台**</span><span class="sxs-lookup"><span data-stu-id="5bd62-159">Visual Studio **Debug Console**</span></span>  
    :::image-end:::  
    
## [<span data-ttu-id="5bd62-160">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5bd62-160">Visual Studio Code</span></span>](#tab/visualstudiocode)  

<span data-ttu-id="5bd62-161">使用 Microsoft Visual Studio 代码调试在 WebView2 控件中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="5bd62-161">Use Microsoft Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

<span data-ttu-id="5bd62-162">在Visual Studio代码中，完成以下操作以调试代码。</span><span class="sxs-lookup"><span data-stu-id="5bd62-162">In Visual Studio Code, complete the following actions to debug your code.</span></span> 

1.  <span data-ttu-id="5bd62-163">您的项目需要具有 `launch.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="5bd62-163">Your project is required to have a `launch.json` file.</span></span>  <span data-ttu-id="5bd62-164">如果项目没有文件，请复制以下 `launch.json` 代码段并创建新 `launch.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="5bd62-164">If your project doesn't have a `launch.json` file, copy the following code snippet and create a new `launch.json` file.</span></span>  
    
    ```json
        "name": "Hello debug world",
        "type": "pwa-msedge",
        "port": 9222, // The port value is optional, and the default value is 9222.
        "request": "launch",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",
        "env": {
            // Customize for your application location if needed
            "Path": "%path%;e:/path/to/your/application/location; "
        },
        "useWebView": true,
    ```  
    
1.  <span data-ttu-id="5bd62-165">若要在源代码中设置断点，请将鼠标悬停在该行上，然后选择</span><span class="sxs-lookup"><span data-stu-id="5bd62-165">To set a breakpoint in your source code, hover on the line, and select</span></span> `F9`
    
    :::image type="complex" source="./media/breakpointvs.png" alt-text="断点在代码Visual Studio设置" lightbox="./media/breakpointvs.png":::
       <span data-ttu-id="5bd62-167">断点在代码Visual Studio设置</span><span class="sxs-lookup"><span data-stu-id="5bd62-167">Breakpoint is set in Visual Studio Code</span></span>  
    :::image-end:::
    
    > [!NOTE]
    > <span data-ttu-id="5bd62-168">由于Visual Studio代码不执行源映射，因此请确保在 WebView2 使用的同一文件中设置断点。</span><span class="sxs-lookup"><span data-stu-id="5bd62-168">Because Visual Studio Code does not perform source mapping, ensure you set breakpoints in the same file that WebView2 uses.</span></span>  <span data-ttu-id="5bd62-169">如果路径不匹配，则Visual Studio代码不会在断点暂停正在运行的代码。</span><span class="sxs-lookup"><span data-stu-id="5bd62-169">If the paths do not match, Visual Studio Code does not pause the running code at the breakpoint.</span></span>  
    
1.  <span data-ttu-id="5bd62-170">运行代码。</span><span class="sxs-lookup"><span data-stu-id="5bd62-170">Run the code.</span></span>  
    1.  <span data-ttu-id="5bd62-171">在 **"运行** "选项卡上，从下拉菜单中选择启动配置。</span><span class="sxs-lookup"><span data-stu-id="5bd62-171">On the **Run** tab, choose the launch configuration from the dropdown menu.</span></span>  
    1.  <span data-ttu-id="5bd62-172">若要开始调试应用程序，请选择"开始调试"，这是启动配置下拉列表旁边的绿色三角形。</span><span class="sxs-lookup"><span data-stu-id="5bd62-172">To start debugging your application, choose Start Debugging, which is the green triangle next to the launch configuration drop down.</span></span>  
        
        :::image type="complex" source="./media/runvs.png" alt-text=" Visual Studio"代码运行"选项卡" lightbox="./media/runvs.png":::
           <span data-ttu-id="5bd62-174">Visual Studio"代码运行"选项卡</span><span class="sxs-lookup"><span data-stu-id="5bd62-174">Visual Studio Code Run tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="5bd62-175">打开 **调试控制台** 以查看调试输出和错误。</span><span class="sxs-lookup"><span data-stu-id="5bd62-175">Open **Debug Console** to view the debug output and errors.</span></span>  
    
    :::image type="complex" source="./media/resultsvs.png" alt-text=" Visual Studio代码调试控制台" lightbox="./media/resultsvs.png":::
       <span data-ttu-id="5bd62-177">Visual Studio代码调试控制台</span><span class="sxs-lookup"><span data-stu-id="5bd62-177">Visual Studio Code Debug Console</span></span>  
    :::image-end:::  
    
<span data-ttu-id="5bd62-178">**高级设置**：</span><span class="sxs-lookup"><span data-stu-id="5bd62-178">**Advanced Settings**:</span></span>  

*   <span data-ttu-id="5bd62-179">目标 Web 视图调试。</span><span class="sxs-lookup"><span data-stu-id="5bd62-179">Targeted Webview debugging.</span></span> 
    
    <span data-ttu-id="5bd62-180">在某些 WebView2 应用程序中，可以使用多个 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="5bd62-180">In some WebView2 applications, you may use more than one WebView2 control.</span></span> <span data-ttu-id="5bd62-181">若要选取 WebView2 控件以在这种情况下进行调试，可以使用目标 Webview2 调试</span><span class="sxs-lookup"><span data-stu-id="5bd62-181">To pick the WebView2 control to debug in this situation you can use targeted webview2 debugging</span></span> 
    
    <span data-ttu-id="5bd62-182">打开 `launch.json` 并完成以下操作以使用目标 Webview 调试。</span><span class="sxs-lookup"><span data-stu-id="5bd62-182">Open `launch.json` and complete the following actions to use targeted Webview debugging.</span></span>  
    
    1.  <span data-ttu-id="5bd62-183">确认参数 `useWebview` 设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="5bd62-183">Confirm that the `useWebview` parameter is set to `true`.</span></span>  
    1.  <span data-ttu-id="5bd62-184">添加 `urlFilter` 参数。</span><span class="sxs-lookup"><span data-stu-id="5bd62-184">Add the `urlFilter` parameter.</span></span>  <span data-ttu-id="5bd62-185">当 WebView2 控件导航到 URL 时，参数值用于 `urlFilter` 比较 URL 中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="5bd62-185">When the WebView2 control navigates to a URL, the `urlFilter` parameter value is used to compare strings that appear in the URL.</span></span>  
    
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    <span data-ttu-id="5bd62-186">调试应用程序时，可能需要从呈现过程开始逐步调试代码。</span><span class="sxs-lookup"><span data-stu-id="5bd62-186">When debugging your application, you may need to step through the code from the beginning of the rendering process.</span></span> <span data-ttu-id="5bd62-187">如果您在网站上呈现网页，但无法访问源代码，您可以使用该选项，因为网页将忽略无法 `?=value`  识别的参数。</span><span class="sxs-lookup"><span data-stu-id="5bd62-187">If you are rendering webpages on sites and you don't have access to the source code, you can use the `?=value` option, because webpages ignore unrecognized parameters.</span></span>   
    
    > [!IMPORTANT]
    > <span data-ttu-id="5bd62-188">在 URL 中发现第一个匹配项后，调试器将停止。</span><span class="sxs-lookup"><span data-stu-id="5bd62-188">After the first match is found in the URL, the debugger stops.</span></span>  <span data-ttu-id="5bd62-189">无法同时调试两个 WebView2 控件，因为 CDP 端口由所有 WebView2 控件共享，并且使用单个端口号。</span><span class="sxs-lookup"><span data-stu-id="5bd62-189">You cannot debug two WebView2 controls at the same time because the CDP port is shared by all WebView2 controls, and uses a single port number.</span></span>  
    
*   <span data-ttu-id="5bd62-190">调试正在运行的进程</span><span class="sxs-lookup"><span data-stu-id="5bd62-190">Debug running processes</span></span>  
    
    <span data-ttu-id="5bd62-191">你可能需要将调试器附加到运行 WebView2 进程。</span><span class="sxs-lookup"><span data-stu-id="5bd62-191">You may need to attach the debugger to running WebView2 processes.</span></span> <span data-ttu-id="5bd62-192">为此，在 `launch.json` 中，将 `request` 参数更新为 `attach` 。</span><span class="sxs-lookup"><span data-stu-id="5bd62-192">To do that, in `launch.json`, update the `request` parameter to `attach`.</span></span>
    
    ```json
        "name": "Hello debugging world",
        "type": "pwa-msedge",
        "port": 9222, 
        "request": "attach",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
        "env": {
            "Path": "%path%;e:/path/to/your/build/location; "  
        },
        "useWebView": true
    ```  
    
    <span data-ttu-id="5bd62-193">WebView2 控件必须打开 CDP 端口以允许调试 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="5bd62-193">Your WebView2 control must open the CDP port to allow debugging of the WebView2 control.</span></span>  <span data-ttu-id="5bd62-194">必须生成代码，以确保在启动调试程序之前，只有一个 WebView2 控件在 CDP (打开) 的 Chrome 开发人员协议。</span><span class="sxs-lookup"><span data-stu-id="5bd62-194">Your code must be built to ensure that only one WebView2 control has a Chrome Developer Protocol (CDP) port open, before starting the debugger.</span></span>  
    
*   <span data-ttu-id="5bd62-195">调试跟踪选项</span><span class="sxs-lookup"><span data-stu-id="5bd62-195">Debug tracing options</span></span>  
    
    <span data-ttu-id="5bd62-196">将参数 `trace` 添加到launch.js启用调试跟踪。</span><span class="sxs-lookup"><span data-stu-id="5bd62-196">Add the `trace` parameter to launch.json to enable debug tracing.</span></span>  
    
    1.  <span data-ttu-id="5bd62-197">添加 `trace` 参数。</span><span class="sxs-lookup"><span data-stu-id="5bd62-197">Add `trace` parameter.</span></span>  
        
        :::row:::
           :::column span="":::
              ```json
                "name": "Hello debugging world",
                "type": "pwa-msedge",
                "port": 9222, 
                "request": "attach",
                "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
                "env": {
                "Path": "%path%;e:/path/to/your/build/location; "  
                },
                "useWebView": true
                ,"trace": true  // Turn on  debug tracing, and save the output to a log file.
              ```  
              
              :::image type="complex" source="./media/tracelog.png" alt-text=" 将调试输出保存到日志文件。" lightbox="./media/tracelog.png":::
                 <span data-ttu-id="5bd62-199">将调试输出保存到日志文件</span><span class="sxs-lookup"><span data-stu-id="5bd62-199">Save debug output to a log file</span></span>  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 详细输出" lightbox="./media/verbose.png":::
                 <span data-ttu-id="5bd62-201">Visual Studio启用详细跟踪的"代码调试输出"</span><span class="sxs-lookup"><span data-stu-id="5bd62-201">Visual Studio Code Debug Output with verbose tracing turned on</span></span>  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   <span data-ttu-id="5bd62-202">调试 Office 加载项。</span><span class="sxs-lookup"><span data-stu-id="5bd62-202">Debug Office Add-ins.</span></span>
    
    <span data-ttu-id="5bd62-203">如果要调试 Office 外接程序，请打开外接程序源代码中的单独实例的 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="5bd62-203">If you're debugging Office Add-ins, open the add-in source code in a separate instance of Visual Studio Code.</span></span>  <span data-ttu-id="5bd62-204">在 launch.js2 应用程序中打开"打开"菜单，并添加以下代码段以将调试器附加到 Office 加载项。</span><span class="sxs-lookup"><span data-stu-id="5bd62-204">Open launch.json in your WebView2 application and add the following code snippet to attach the debugger to the Office add-in.</span></span>
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   <span data-ttu-id="5bd62-205">调试程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="5bd62-205">Troubleshooting the debugger</span></span>  
    
    <span data-ttu-id="5bd62-206">使用调试器时，可能会遇到以下情况。</span><span class="sxs-lookup"><span data-stu-id="5bd62-206">You may encounter the following scenarios when using the debugger.</span></span>  
    
    *   <span data-ttu-id="5bd62-207">调试器不会在断点处停止，并且你有调试输出。</span><span class="sxs-lookup"><span data-stu-id="5bd62-207">The debugger doesn't stop at the breakpoint, and you have debug output.</span></span>  <span data-ttu-id="5bd62-208">若要解决此问题，请确认断点为文件与 WebView2 控件所使用的文件相同。</span><span class="sxs-lookup"><span data-stu-id="5bd62-208">To solve the issue, confirm that the file with the breakpoint is the same file that's used by the WebView2 control.</span></span>  <span data-ttu-id="5bd62-209">调试程序不执行源路径映射。</span><span class="sxs-lookup"><span data-stu-id="5bd62-209">The debugger doesn't perform source path mapping.</span></span>  
    *   <span data-ttu-id="5bd62-210">无法附加到正在运行的进程，并收到超时错误。</span><span class="sxs-lookup"><span data-stu-id="5bd62-210">You can't attach to a running process, and you get a timeout error.</span></span>  <span data-ttu-id="5bd62-211">若要解决此问题，请确认 WebView2 控件打开了 CDP 端口。</span><span class="sxs-lookup"><span data-stu-id="5bd62-211">To solve the issue, confirm that the WebView2 control opened the CDP port.</span></span>  <span data-ttu-id="5bd62-212">请确保  `additionalBrowserArguments`  注册表中的值正确，或者选项正确。</span><span class="sxs-lookup"><span data-stu-id="5bd62-212">Ensure your `additionalBrowserArguments` value in the registry is correct, or the options are correct.</span></span>  <span data-ttu-id="5bd62-213">有关详细信息，请参阅[dotnet 的其他BrowserArguments][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]和[适用于 Win32 的其他BrowserArguments。][Webview2ReferenceWin32Webview2IdlParameters]</span><span class="sxs-lookup"><span data-stu-id="5bd62-213">For more information, see [additionalBrowserArguments for dotnet][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] and [additionalBrowserArguments for Win32][Webview2ReferenceWin32Webview2IdlParameters].</span></span>  
    
* * *  

## <span data-ttu-id="5bd62-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bd62-214">See also</span></span>  

*   <span data-ttu-id="5bd62-215">若要开始使用 WebView2，请参阅 [WebView2 入门指南][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="5bd62-215">To get started using WebView2, see [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="5bd62-216">有关 WebView2 功能的综合示例，请参阅 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。</span><span class="sxs-lookup"><span data-stu-id="5bd62-216">For a comprehensive example of WebView2 capabilities, see the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>
*   <span data-ttu-id="5bd62-217">有关 WebView2 API 的更多详细信息，请参阅 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="5bd62-217">For more detailed information about WebView2 APIs, see [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="5bd62-218">有关 WebView2 的信息，请参阅 [WebView2 资源][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="5bd62-218">For more information about WebView2, see [WebView2 Resources][Webview2MainNextSteps].</span></span>
    
## <span data-ttu-id="5bd62-219">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="5bd62-219">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions.AdditionalBrowserArguments (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment - Globals |Microsoft Docs"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能- JavaScript 调试器Visual Studio代码 - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView 应用程序 - Visual Studio 代码 - 适用于 Microsoft Edge 的调试器 - microsoft/vscode-edge-debug2 |GitHub"  
