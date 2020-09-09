---
description: IE 模式和 Microsoft Edge (Chromium) DevTools
title: Internet Explorer 模式和 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、ie11、internet explorer 11、ie 模式
ms.openlocfilehash: b059cae3ff48a45fe92cbf69e37ad692e329b200
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003959"
---
# <span data-ttu-id="1f314-104">Internet Explorer 模式和 DevTools</span><span class="sxs-lookup"><span data-stu-id="1f314-104">Internet Explorer mode and the DevTools</span></span>  

<span data-ttu-id="1f314-105">本文介绍 Internet Explorer 模式 \ (IE 模式 \ ) 与 Microsoft Edge \ (Chromium \ ) DevTools 集成。</span><span class="sxs-lookup"><span data-stu-id="1f314-105">This article describes how Internet Explorer mode \(IE mode\) integrates with the Microsoft Edge \(Chromium\) DevTools.</span></span>  

## <span data-ttu-id="1f314-106">了解 IE 模式</span><span class="sxs-lookup"><span data-stu-id="1f314-106">Understanding IE mode</span></span>  

<span data-ttu-id="1f314-107">IE 模式允许企业指定仅在 Internet Explorer 11 中工作的网站列表。</span><span class="sxs-lookup"><span data-stu-id="1f314-107">IE mode allows enterprises to specify a list of web sites that only work in Internet Explorer 11.</span></span>  <span data-ttu-id="1f314-108">当您在 Microsoft Edge \ (Chromium \ ) 中导航到这些网站时，Internet Explorer 11 的一个实例在选项卡中运行并呈现网站。 此功能允许企业管理与当前与任何现代 web 浏览器不兼容的技术的兼容性。</span><span class="sxs-lookup"><span data-stu-id="1f314-108">When you navigate to these web sites in Microsoft Edge \(Chromium\), an instance of Internet Explorer 11 runs and renders the site in a tab.  The functionality allows enterprises to manage compatibility with technologies that are currently not compatible with any modern web browsers.</span></span>  <span data-ttu-id="1f314-109">IE 模式中包括对以下技术的支持。</span><span class="sxs-lookup"><span data-stu-id="1f314-109">Support for the following technologies is included in IE mode.</span></span>  

*   <span data-ttu-id="1f314-110">IE 文档模式</span><span class="sxs-lookup"><span data-stu-id="1f314-110">IE document modes</span></span>  
*   <span data-ttu-id="1f314-111">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="1f314-111">ActiveX controls</span></span>  
*   <span data-ttu-id="1f314-112">其他旧版组件</span><span class="sxs-lookup"><span data-stu-id="1f314-112">other legacy components</span></span>  

<span data-ttu-id="1f314-113">在 IE 模式下，呈现过程基于 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="1f314-113">In IE mode, the rendering process is based on Internet Explorer 11.</span></span>  <span data-ttu-id="1f314-114">Microsoft Edge \ (Chromium \ ) 进程管理器处理呈现过程的生存期。</span><span class="sxs-lookup"><span data-stu-id="1f314-114">The Microsoft Edge \(Chromium\) process manager handles the lifetime of the rendering process.</span></span>  <span data-ttu-id="1f314-115">它受限于特定网站 \ (或 app \ ) 的选项卡的生命周期。</span><span class="sxs-lookup"><span data-stu-id="1f314-115">It is constrained to the lifetime of the tab for a specific site \(or app\).</span></span>  <span data-ttu-id="1f314-116">在 IE 模式下呈现选项卡时，特定选项卡的地址栏中将显示一个标记。</span><span class="sxs-lookup"><span data-stu-id="1f314-116">When a tab renders in IE mode, a badge appears in the address bar for the specific tab.</span></span>  

:::image type="complex" source="./media/ie-mode-badge.msft.png" alt-text="地址栏中的 IE 模式标记" lightbox="./media/ie-mode-badge.msft.png":::
   <span data-ttu-id="1f314-118">地址栏中的 IE 模式标记</span><span class="sxs-lookup"><span data-stu-id="1f314-118">IE mode badge in the address bar</span></span>  
:::image-end:::  

<span data-ttu-id="1f314-119">IE 模式目前在 Windows 10 版本的 1903 \ 上可用 (可能2019更新 \ ) ，但即将推出所有受支持的 Windows 平台。</span><span class="sxs-lookup"><span data-stu-id="1f314-119">IE mode is currently available on Windows 10 Version 1903 \(May 2019 Update\), but is coming soon to all supported Windows platforms.</span></span>  

## <span data-ttu-id="1f314-120">在 IE 模式下的选项卡上启动 DevTools</span><span class="sxs-lookup"><span data-stu-id="1f314-120">Launching the DevTools on a tab in IE mode</span></span>  

<span data-ttu-id="1f314-121">如果您尝试在 IE 模式下查看网站的文档模式，请选择地址栏中的锁屏提醒。</span><span class="sxs-lookup"><span data-stu-id="1f314-121">If you are trying to view the document mode of a web site in IE mode, choose the badge in the address bar.</span></span>  

:::image type="complex" source="./media/ie-mode-badge-doc-mode.msft.png" alt-text="使用 IE 模式锁屏提醒查看文档模式" lightbox="./media/ie-mode-badge-doc-mode.msft.png":::
   <span data-ttu-id="1f314-123">使用 IE 模式锁屏提醒查看文档模式</span><span class="sxs-lookup"><span data-stu-id="1f314-123">View document mode using IE mode badge</span></span>  
:::image-end:::  

<span data-ttu-id="1f314-124">如果选项卡使用的是 IE 模式，则 DevTools 不起作用，并且会出现以下情况。</span><span class="sxs-lookup"><span data-stu-id="1f314-124">If a tab is using IE mode, the DevTools do not work and the following conditions occur.</span></span>

*   <span data-ttu-id="1f314-125">如果您选择 `F12` 或选择 `Ctrl` + `Shift` + `I` ""，则会启动 Microsoft Edge \ (Chromium \ ) DevTools 的空实例，并显示以下消息。</span><span class="sxs-lookup"><span data-stu-id="1f314-125">If you select `F12` or select `Ctrl`+`Shift`+`I`, a blank instance of the Microsoft Edge \(Chromium\) DevTools is launched displays the following message.</span></span>  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   <span data-ttu-id="1f314-126">如果打开上下文菜单 \ (右键单击 \ ) 并选择 " **查看源**"，将启动 "记事本"。</span><span class="sxs-lookup"><span data-stu-id="1f314-126">If you open a contextual menu \(right-click\) and choose **View Source**, Notepad is launched.</span></span>  
*   <span data-ttu-id="1f314-127">如果打开上下文菜单 \ (右键单击 \ ) ，将看不到 " **检查" 元素** 。</span><span class="sxs-lookup"><span data-stu-id="1f314-127">If you open a contextual menu \(right-click\), the **Inspect Element** is not visible.</span></span>  

<span data-ttu-id="1f314-128">DevTools (中类似于 **网络** 和 **性能** 工具的许多工具 \ ) 不起作用是呈现引擎在 IE 模式下从 Chromium 切换到 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="1f314-128">The reason that a number of the tools within the DevTools \(like the **Network** and **Performance** tools\) do not work is the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span>  <span data-ttu-id="1f314-129">若要提供反馈，请导航到 [与 Microsoft Edge DevTools 团队取得联系](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="1f314-129">To provide feedback, navigate to [Getting in touch with the Microsoft Edge DevTools team](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

:::image type="complex" source="./media/ie-mode-devtools.msft.png" alt-text="在 IE 模式下启动的 DevTools" lightbox="./media/ie-mode-devtools.msft.png":::
   <span data-ttu-id="1f314-131">在 IE 模式下启动的 DevTools</span><span class="sxs-lookup"><span data-stu-id="1f314-131">DevTools launched in IE mode</span></span>  
:::image-end:::  

<span data-ttu-id="1f314-132">要在 Internet Explorer 11 和 IE 模式下测试您的基于 Internet Explorer 11 的网站 \ (或应用 \ ) ，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1f314-132">To test your Internet Explorer 11-based website \(or app\) in Internet Explorer 11 and IE mode, perform the following steps.</span></span>  

1.  <span data-ttu-id="1f314-133">打开 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="1f314-133">Open Internet Explorer 11.</span></span>  
    *   <span data-ttu-id="1f314-134">在 Windows 10 上，找到 Internet Explorer 11 的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="1f314-134">On Windows 10, locate the shortcut for Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="1f314-135">**开始菜单**  > **Windows 附件**  > **Internet Explorer 11**。</span><span class="sxs-lookup"><span data-stu-id="1f314-135">**Start Menu** > **Windows Accessories** > **Internet Explorer 11**.</span></span>  
    *   <span data-ttu-id="1f314-136">在 Windows 7 上，找到 "Internet Explorer 11"。</span><span class="sxs-lookup"><span data-stu-id="1f314-136">On Windows 7, locate Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="1f314-137">**开始菜单**  > **Internet Explorer 11**。</span><span class="sxs-lookup"><span data-stu-id="1f314-137">**Start Menu** > **Internet Explorer 11**.</span></span>  
1.  <span data-ttu-id="1f314-138">在 Internet Explorer 11 中，打开相同的网页。</span><span class="sxs-lookup"><span data-stu-id="1f314-138">In Internet Explorer 11, open the same webpage.</span></span>  
1.  <span data-ttu-id="1f314-139">启动 Internet Explorer DevTools。</span><span class="sxs-lookup"><span data-stu-id="1f314-139">Launch the Internet Explorer DevTools.</span></span>  
    *   <span data-ttu-id="1f314-140">选择 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="1f314-140">Select `F12`.</span></span>  
    *   <span data-ttu-id="1f314-141">将鼠标悬停在任意位置，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **检查元素**"。</span><span class="sxs-lookup"><span data-stu-id="1f314-141">Hover anywhere, open a contextual menu \(right-click\), and choose **Inspect element**.</span></span>  <span data-ttu-id="1f314-142">有关如何使用这些工具的详细信息，请导航到 [使用 F12 开发人员工具][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]。</span><span class="sxs-lookup"><span data-stu-id="1f314-142">For more information about how to use those tools, navigate to [Using the F12 developer tools][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326].</span></span>  

## <span data-ttu-id="1f314-143">远程调试和 IE 模式</span><span class="sxs-lookup"><span data-stu-id="1f314-143">Remote debugging and IE mode</span></span>  

<span data-ttu-id="1f314-144">启动 Microsoft Edge \ (Chromium \ ) 从命令行界面打开远程调试。</span><span class="sxs-lookup"><span data-stu-id="1f314-144">Launch Microsoft Edge \(Chromium\) with remote debugging turned on from the command-line interface.</span></span>  <span data-ttu-id="1f314-145">Visual Studio、Visual Studio 代码和其他开发工具通常运行命令来启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="1f314-145">Visual Studio, Visual Studio Code, and other development tools typically run a command to launch Microsoft Edge.</span></span>  <span data-ttu-id="1f314-146">以下命令将启动设置为的远程调试端口的 Microsoft Edge `9222` 。</span><span class="sxs-lookup"><span data-stu-id="1f314-146">The following command launches Microsoft Edge with the remote debugging port set to `9222`.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="1f314-147">启动 Microsoft Edge \ (Chromium \ ) 使用命令行参数时，IE 模式不可用。</span><span class="sxs-lookup"><span data-stu-id="1f314-147">After you launch Microsoft Edge \(Chromium\) using a command-line argument, IE mode is unavailable.</span></span>  <span data-ttu-id="1f314-148">您仍然可以导航到 "网站 \ (" 或 "应用 \ ) "，否则将在 IE 模式下显示这些应用。</span><span class="sxs-lookup"><span data-stu-id="1f314-148">You may still navigate to websites \(or apps\) that would otherwise display in IE mode.</span></span> <span data-ttu-id="1f314-149">网站 \ (或应用 \ ) 内容使用 Chromium （而不是 Internet Explorer 11）呈现。</span><span class="sxs-lookup"><span data-stu-id="1f314-149">The website \(or app\) content renders using Chromium, not Internet Explorer 11.</span></span>  <span data-ttu-id="1f314-150">希望页面中依赖 IE11 的部分（如 ActiveX 控件）无法正确呈现。</span><span class="sxs-lookup"><span data-stu-id="1f314-150">Expect the parts of the pages that rely on IE11, such as ActiveX controls, to not render correctly.</span></span>  <span data-ttu-id="1f314-151">IE 模式标记不会显示在地址栏中。</span><span class="sxs-lookup"><span data-stu-id="1f314-151">The IE mode badge does not appear in the address bar.</span></span>  

<span data-ttu-id="1f314-152">在完全关闭并重新启动 Microsoft Edge \ (Chromium \ ) 之前，IE 模式保持不可用。</span><span class="sxs-lookup"><span data-stu-id="1f314-152">IE mode remains unavailable until you completely close and restart Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="1f314-153">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="1f314-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "使用 F12 开发人员工具 |Microsoft 文档"  