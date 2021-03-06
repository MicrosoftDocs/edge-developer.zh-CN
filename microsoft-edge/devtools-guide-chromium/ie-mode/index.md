---
description: IE 模式和 Microsoft Edge (Chromium) DevTools
title: Internet Explorer模式和 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， ie11， Internet explorer 11， ie 模式
ms.openlocfilehash: e65869cd88b449dcde0aec25c77df27f99b78f8d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398600"
---
# <a name="internet-explorer-mode-and-the-devtools"></a><span data-ttu-id="4a829-104">Internet Explorer模式和 DevTools</span><span class="sxs-lookup"><span data-stu-id="4a829-104">Internet Explorer mode and the DevTools</span></span>  

<span data-ttu-id="4a829-105">本文介绍如何Internet Explorer模式 \ (IE 模式\) 与 Microsoft Edge \ (Chromium\) DevTools 集成。</span><span class="sxs-lookup"><span data-stu-id="4a829-105">This article describes how Internet Explorer mode \(IE mode\) integrates with the Microsoft Edge \(Chromium\) DevTools.</span></span>  

## <a name="understanding-ie-mode"></a><span data-ttu-id="4a829-106">了解 IE 模式</span><span class="sxs-lookup"><span data-stu-id="4a829-106">Understanding IE mode</span></span>  

<span data-ttu-id="4a829-107">IE 模式允许企业指定仅在 11 Internet Explorer的网站列表。</span><span class="sxs-lookup"><span data-stu-id="4a829-107">IE mode allows enterprises to specify a list of web sites that only work in Internet Explorer 11.</span></span>  <span data-ttu-id="4a829-108">在 Microsoft Edge \ (Chromium\) 中导航到这些网站时，Internet Explorer 11 的实例将运行并在选项卡中呈现网站。 此功能允许企业管理与当前与任何新式 Web 浏览器不兼容的技术的兼容性。</span><span class="sxs-lookup"><span data-stu-id="4a829-108">When you navigate to these web sites in Microsoft Edge \(Chromium\), an instance of Internet Explorer 11 runs and renders the site in a tab.  The functionality allows enterprises to manage compatibility with technologies that are currently not compatible with any modern web browsers.</span></span>  <span data-ttu-id="4a829-109">IE 模式下包含对以下技术的支持。</span><span class="sxs-lookup"><span data-stu-id="4a829-109">Support for the following technologies is included in IE mode.</span></span>  

*   <span data-ttu-id="4a829-110">IE 文档模式</span><span class="sxs-lookup"><span data-stu-id="4a829-110">IE document modes</span></span>  
*   <span data-ttu-id="4a829-111">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="4a829-111">ActiveX controls</span></span>  
*   <span data-ttu-id="4a829-112">其他旧版组件</span><span class="sxs-lookup"><span data-stu-id="4a829-112">other legacy components</span></span>  

<span data-ttu-id="4a829-113">在 IE 模式下，呈现过程基于 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="4a829-113">In IE mode, the rendering process is based on Internet Explorer 11.</span></span>  <span data-ttu-id="4a829-114">Microsoft Edge \ (Chromium\) 进程管理器处理呈现过程的生存期。</span><span class="sxs-lookup"><span data-stu-id="4a829-114">The Microsoft Edge \(Chromium\) process manager handles the lifetime of the rendering process.</span></span>  <span data-ttu-id="4a829-115">它受特定网站 \ (app\) 选项卡的生存期限制。</span><span class="sxs-lookup"><span data-stu-id="4a829-115">It is constrained to the lifetime of the tab for a specific site \(or app\).</span></span>  <span data-ttu-id="4a829-116">当选项卡以 IE 模式呈现时，特定选项卡的地址栏中会显示锁屏提醒。</span><span class="sxs-lookup"><span data-stu-id="4a829-116">When a tab renders in IE mode, a badge appears in the address bar for the specific tab.</span></span>  

:::image type="complex" source="../media/ie-mode-badge.msft.png" alt-text="地址栏中的 IE 模式锁屏提醒" lightbox="../media/ie-mode-badge.msft.png":::
   <span data-ttu-id="4a829-118">地址栏中的 IE 模式锁屏提醒</span><span class="sxs-lookup"><span data-stu-id="4a829-118">IE mode badge in the address bar</span></span>  
:::image-end:::  

<span data-ttu-id="4a829-119">IE 模式目前可用于 Windows 10 版本 1903 \ (2019 年 5 月更新\) ，但即将推出到所有受支持的 Windows 平台。</span><span class="sxs-lookup"><span data-stu-id="4a829-119">IE mode is currently available on Windows 10 Version 1903 \(May 2019 Update\), but is coming soon to all supported Windows platforms.</span></span>  

## <a name="launching-the-devtools-on-a-tab-in-ie-mode"></a><span data-ttu-id="4a829-120">在 IE 模式下的选项卡上启动 DevTools</span><span class="sxs-lookup"><span data-stu-id="4a829-120">Launching the DevTools on a tab in IE mode</span></span>  

<span data-ttu-id="4a829-121">如果尝试在 IE 模式下查看网站的文档模式，请选择地址栏中的锁屏提醒。</span><span class="sxs-lookup"><span data-stu-id="4a829-121">If you are trying to view the document mode of a web site in IE mode, choose the badge in the address bar.</span></span>  

:::image type="complex" source="../media/ie-mode-badge-doc-mode.msft.png" alt-text="使用 IE 模式锁屏提醒查看文档模式" lightbox="../media/ie-mode-badge-doc-mode.msft.png":::
   <span data-ttu-id="4a829-123">使用 IE 模式锁屏提醒查看文档模式</span><span class="sxs-lookup"><span data-stu-id="4a829-123">View document mode using IE mode badge</span></span>  
:::image-end:::  

<span data-ttu-id="4a829-124">如果选项卡使用的是 IE 模式，DevTools 将不起作用，并且会出现以下情况。</span><span class="sxs-lookup"><span data-stu-id="4a829-124">If a tab is using IE mode, the DevTools do not work and the following conditions occur.</span></span>

*   <span data-ttu-id="4a829-125">如果选择或 `F12` 选择，将启动 `Ctrl` + `Shift` + `I` Microsoft Edge \ (Chromium\) DevTools 的空白实例将显示以下消息。</span><span class="sxs-lookup"><span data-stu-id="4a829-125">If you select `F12` or select `Ctrl`+`Shift`+`I`, a blank instance of the Microsoft Edge \(Chromium\) DevTools is launched displays the following message.</span></span>  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   <span data-ttu-id="4a829-126">如果打开上下文菜单 \ (右键单击\) 并选择 **"** 查看源"，将启动记事本。</span><span class="sxs-lookup"><span data-stu-id="4a829-126">If you open a contextual menu \(right-click\) and choose **View Source**, Notepad is launched.</span></span>  
*   <span data-ttu-id="4a829-127">如果打开上下文菜单 \ (右键单击\) ， **则 Inspect 元素** 不可见。</span><span class="sxs-lookup"><span data-stu-id="4a829-127">If you open a contextual menu \(right-click\), the **Inspect Element** is not visible.</span></span>  

<span data-ttu-id="4a829-128">DevTools \ (中的许多工具（如**网络**和性能工具\) ）不起作用的原因是呈现\*\*\*\* 引擎在 IE 模式下从 Chromium 切换到 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="4a829-128">The reason that a number of the tools within the DevTools \(like the **Network** and **Performance** tools\) do not work is the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span>  <span data-ttu-id="4a829-129">若要提供反馈，请导航到 [与 Microsoft Edge DevTools](#getting-in-touch-with-the-microsoft-edge-devtools-team)团队联系。</span><span class="sxs-lookup"><span data-stu-id="4a829-129">To provide feedback, navigate to [Getting in touch with the Microsoft Edge DevTools team](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

:::image type="complex" source="../media/ie-mode-devtools.msft.png" alt-text="在 IE 模式下启动的 DevTools" lightbox="../media/ie-mode-devtools.msft.png":::
   <span data-ttu-id="4a829-131">在 IE 模式下启动的 DevTools</span><span class="sxs-lookup"><span data-stu-id="4a829-131">DevTools launched in IE mode</span></span>  
:::image-end:::  

<span data-ttu-id="4a829-132">若要在 Internet Explorer 11 和 IE 模式下测试基于 Internet Explorer 11 的网站 \ (或 app\) ，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a829-132">To test your Internet Explorer 11-based website \(or app\) in Internet Explorer 11 and IE mode, perform the following steps.</span></span>  

1.  <span data-ttu-id="4a829-133">打开Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="4a829-133">Open Internet Explorer 11.</span></span>  
    *   <span data-ttu-id="4a829-134">在 Windows 10 上，找到 Internet Explorer 11 的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="4a829-134">On Windows 10, locate the shortcut for Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="4a829-135">**"开始"菜单**  > **Windows 附件**  > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="4a829-135">**Start Menu** > **Windows Accessories** > **Internet Explorer 11**.</span></span>  
    *   <span data-ttu-id="4a829-136">在 Windows 7 上，找到 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="4a829-136">On Windows 7, locate Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="4a829-137">**"开始"菜单**  > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="4a829-137">**Start Menu** > **Internet Explorer 11**.</span></span>  
1.  <span data-ttu-id="4a829-138">在 Internet Explorer 11 中，打开同一网页。</span><span class="sxs-lookup"><span data-stu-id="4a829-138">In Internet Explorer 11, open the same webpage.</span></span>  
1.  <span data-ttu-id="4a829-139">启动 Internet Explorer DevTools。</span><span class="sxs-lookup"><span data-stu-id="4a829-139">Launch the Internet Explorer DevTools.</span></span>  
    *   <span data-ttu-id="4a829-140">选择 `F12`。</span><span class="sxs-lookup"><span data-stu-id="4a829-140">Select `F12`.</span></span>  
    *   <span data-ttu-id="4a829-141">将鼠标悬停在任意位置，打开上下文菜单 \ (右键单击\) ，然后选择 **"检查"元素**。</span><span class="sxs-lookup"><span data-stu-id="4a829-141">Hover anywhere, open a contextual menu \(right-click\), and choose **Inspect element**.</span></span>  <span data-ttu-id="4a829-142">若要详细了解如何使用这些工具，请导航到["使用 F12 开发人员工具"。][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]</span><span class="sxs-lookup"><span data-stu-id="4a829-142">For more information about how to use those tools, navigate to [Using the F12 developer tools][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326].</span></span>  

## <a name="remote-debugging-and-ie-mode"></a><span data-ttu-id="4a829-143">远程调试和 IE 模式</span><span class="sxs-lookup"><span data-stu-id="4a829-143">Remote debugging and IE mode</span></span>  

<span data-ttu-id="4a829-144">启动 Microsoft Edge \ (Chromium\) ，同时从命令行界面打开远程调试。</span><span class="sxs-lookup"><span data-stu-id="4a829-144">Launch Microsoft Edge \(Chromium\) with remote debugging turned on from the command-line interface.</span></span>  <span data-ttu-id="4a829-145">Microsoft Visual Studio、Microsoft Visual Studio Code 和其他开发工具通常会运行命令来启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="4a829-145">Microsoft Visual Studio, Microsoft Visual Studio Code, and other development tools typically run a command to launch Microsoft Edge.</span></span>  <span data-ttu-id="4a829-146">以下命令启动 Microsoft Edge，远程调试端口设置为 `9222` 。</span><span class="sxs-lookup"><span data-stu-id="4a829-146">The following command launches Microsoft Edge with the remote debugging port set to `9222`.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="4a829-147">使用命令行参数启动 Microsoft Edge \ (Chromium\) 后，IE 模式将不可用。</span><span class="sxs-lookup"><span data-stu-id="4a829-147">After you launch Microsoft Edge \(Chromium\) using a command-line argument, IE mode is unavailable.</span></span>  <span data-ttu-id="4a829-148">你仍可以导航到以 iE 模式 (或应用) 或应用\应用。</span><span class="sxs-lookup"><span data-stu-id="4a829-148">You may still navigate to websites \(or apps\) that are otherwise displayed in IE mode.</span></span>  <span data-ttu-id="4a829-149">网站 \ (或 app\) 内容使用 Chromium 而不是 Internet Explorer 11 呈现。</span><span class="sxs-lookup"><span data-stu-id="4a829-149">The website \(or app\) content renders using Chromium, not Internet Explorer 11.</span></span>  <span data-ttu-id="4a829-150">预计依赖 IE11 的网页部分（如ActiveX控件）无法正确呈现。</span><span class="sxs-lookup"><span data-stu-id="4a829-150">Expect the parts of the webpages that rely on IE11, such as ActiveX controls, to not render correctly.</span></span>  <span data-ttu-id="4a829-151">IE 模式锁屏提醒不会显示在地址栏中。</span><span class="sxs-lookup"><span data-stu-id="4a829-151">The IE mode badge does not appear in the address bar.</span></span>  

<span data-ttu-id="4a829-152">IE 模式仍然不可用，直到你完全关闭并重新启动 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="4a829-152">IE mode remains unavailable until you completely close and restart Microsoft Edge \(Chromium\).</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4a829-153">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="4a829-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "使用 F12 开发人员工具|Microsoft Docs"  
