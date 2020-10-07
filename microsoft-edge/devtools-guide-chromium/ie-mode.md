---
description: IE mode and the Microsoft Edge (Chromium) DevTools
title: Internet Explorer mode and the DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, ie11, internet explorer 11, ie mode
ms.openlocfilehash: b059cae3ff48a45fe92cbf69e37ad692e329b200
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003959"
---
# <span data-ttu-id="414c7-104">Internet Explorer mode and the DevTools</span><span class="sxs-lookup"><span data-stu-id="414c7-104">Internet Explorer mode and the DevTools</span></span>  

<span data-ttu-id="414c7-105">This article describes how Internet Explorer mode \(IE mode\) integrates with the Microsoft Edge \(Chromium\) DevTools.</span><span class="sxs-lookup"><span data-stu-id="414c7-105">This article describes how Internet Explorer mode \(IE mode\) integrates with the Microsoft Edge \(Chromium\) DevTools.</span></span>  

## <span data-ttu-id="414c7-106">Understanding IE mode</span><span class="sxs-lookup"><span data-stu-id="414c7-106">Understanding IE mode</span></span>  

<span data-ttu-id="414c7-107">IE mode allows enterprises to specify a list of web sites that only work in Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="414c7-107">IE mode allows enterprises to specify a list of web sites that only work in Internet Explorer 11.</span></span>  <span data-ttu-id="414c7-108">When you navigate to these web sites in Microsoft Edge \(Chromium\), an instance of Internet Explorer 11 runs and renders the site in a tab.  The functionality allows enterprises to manage compatibility with technologies that are currently not compatible with any modern web browsers.</span><span class="sxs-lookup"><span data-stu-id="414c7-108">When you navigate to these web sites in Microsoft Edge \(Chromium\), an instance of Internet Explorer 11 runs and renders the site in a tab.  The functionality allows enterprises to manage compatibility with technologies that are currently not compatible with any modern web browsers.</span></span>  <span data-ttu-id="414c7-109">Support for the following technologies is included in IE mode.</span><span class="sxs-lookup"><span data-stu-id="414c7-109">Support for the following technologies is included in IE mode.</span></span>  

*   <span data-ttu-id="414c7-110">IE document modes</span><span class="sxs-lookup"><span data-stu-id="414c7-110">IE document modes</span></span>  
*   <span data-ttu-id="414c7-111">ActiveX controls</span><span class="sxs-lookup"><span data-stu-id="414c7-111">ActiveX controls</span></span>  
*   <span data-ttu-id="414c7-112">other legacy components</span><span class="sxs-lookup"><span data-stu-id="414c7-112">other legacy components</span></span>  

<span data-ttu-id="414c7-113">In IE mode, the rendering process is based on Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="414c7-113">In IE mode, the rendering process is based on Internet Explorer 11.</span></span>  <span data-ttu-id="414c7-114">The Microsoft Edge \(Chromium\) process manager handles the lifetime of the rendering process.</span><span class="sxs-lookup"><span data-stu-id="414c7-114">The Microsoft Edge \(Chromium\) process manager handles the lifetime of the rendering process.</span></span>  <span data-ttu-id="414c7-115">It is constrained to the lifetime of the tab for a specific site \(or app\).</span><span class="sxs-lookup"><span data-stu-id="414c7-115">It is constrained to the lifetime of the tab for a specific site \(or app\).</span></span>  <span data-ttu-id="414c7-116">When a tab renders in IE mode, a badge appears in the address bar for the specific tab.</span><span class="sxs-lookup"><span data-stu-id="414c7-116">When a tab renders in IE mode, a badge appears in the address bar for the specific tab.</span></span>  

:::image type="complex" source="./media/ie-mode-badge.msft.png" alt-text="IE mode badge in the address bar" lightbox="./media/ie-mode-badge.msft.png":::
   <span data-ttu-id="414c7-118">IE mode badge in the address bar</span><span class="sxs-lookup"><span data-stu-id="414c7-118">IE mode badge in the address bar</span></span>  
:::image-end:::  

<span data-ttu-id="414c7-119">IE mode is currently available on Windows 10 Version 1903 \(May 2019 Update\), but is coming soon to all supported Windows platforms.</span><span class="sxs-lookup"><span data-stu-id="414c7-119">IE mode is currently available on Windows 10 Version 1903 \(May 2019 Update\), but is coming soon to all supported Windows platforms.</span></span>  

## <span data-ttu-id="414c7-120">Launching the DevTools on a tab in IE mode</span><span class="sxs-lookup"><span data-stu-id="414c7-120">Launching the DevTools on a tab in IE mode</span></span>  

<span data-ttu-id="414c7-121">If you are trying to view the document mode of a web site in IE mode, choose the badge in the address bar.</span><span class="sxs-lookup"><span data-stu-id="414c7-121">If you are trying to view the document mode of a web site in IE mode, choose the badge in the address bar.</span></span>  

:::image type="complex" source="./media/ie-mode-badge-doc-mode.msft.png" alt-text="IE mode badge in the address bar" lightbox="./media/ie-mode-badge-doc-mode.msft.png":::
   <span data-ttu-id="414c7-123">View document mode using IE mode badge</span><span class="sxs-lookup"><span data-stu-id="414c7-123">View document mode using IE mode badge</span></span>  
:::image-end:::  

<span data-ttu-id="414c7-124">If a tab is using IE mode, the DevTools do not work and the following conditions occur.</span><span class="sxs-lookup"><span data-stu-id="414c7-124">If a tab is using IE mode, the DevTools do not work and the following conditions occur.</span></span>

*   <span data-ttu-id="414c7-125">If you select `F12` or select `Ctrl`+`Shift`+`I`, a blank instance of the Microsoft Edge \(Chromium\) DevTools is launched displays the following message.</span><span class="sxs-lookup"><span data-stu-id="414c7-125">If you select `F12` or select `Ctrl`+`Shift`+`I`, a blank instance of the Microsoft Edge \(Chromium\) DevTools is launched displays the following message.</span></span>  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   <span data-ttu-id="414c7-126">If you open a contextual menu \(right-click\) and choose **View Source**, Notepad is launched.</span><span class="sxs-lookup"><span data-stu-id="414c7-126">If you open a contextual menu \(right-click\) and choose **View Source**, Notepad is launched.</span></span>  
*   <span data-ttu-id="414c7-127">If you open a contextual menu \(right-click\), the **Inspect Element** is not visible.</span><span class="sxs-lookup"><span data-stu-id="414c7-127">If you open a contextual menu \(right-click\), the **Inspect Element** is not visible.</span></span>  

<span data-ttu-id="414c7-128">The reason that a number of the tools within the DevTools \(like the **Network** and **Performance** tools\) do not work is the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span><span class="sxs-lookup"><span data-stu-id="414c7-128">The reason that a number of the tools within the DevTools \(like the **Network** and **Performance** tools\) do not work is the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span>  <span data-ttu-id="414c7-129">To provide feedback, navigate to [Getting in touch with the Microsoft Edge DevTools team](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span><span class="sxs-lookup"><span data-stu-id="414c7-129">To provide feedback, navigate to [Getting in touch with the Microsoft Edge DevTools team](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

:::image type="complex" source="./media/ie-mode-devtools.msft.png" alt-text="IE mode badge in the address bar" lightbox="./media/ie-mode-devtools.msft.png":::
   <span data-ttu-id="414c7-131">DevTools launched in IE mode</span><span class="sxs-lookup"><span data-stu-id="414c7-131">DevTools launched in IE mode</span></span>  
:::image-end:::  

<span data-ttu-id="414c7-132">To test your Internet Explorer 11-based website \(or app\) in Internet Explorer 11 and IE mode, perform the following steps.</span><span class="sxs-lookup"><span data-stu-id="414c7-132">To test your Internet Explorer 11-based website \(or app\) in Internet Explorer 11 and IE mode, perform the following steps.</span></span>  

1.  <span data-ttu-id="414c7-133">Open Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="414c7-133">Open Internet Explorer 11.</span></span>  
    *   <span data-ttu-id="414c7-134">On Windows 10, locate the shortcut for Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="414c7-134">On Windows 10, locate the shortcut for Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="414c7-135">**Start Menu** > **Windows Accessories** > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="414c7-135">**Start Menu** > **Windows Accessories** > **Internet Explorer 11**.</span></span>  
    *   <span data-ttu-id="414c7-136">On Windows 7, locate Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="414c7-136">On Windows 7, locate Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="414c7-137">**Start Menu** > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="414c7-137">**Start Menu** > **Internet Explorer 11**.</span></span>  
1.  <span data-ttu-id="414c7-138">In Internet Explorer 11, open the same webpage.</span><span class="sxs-lookup"><span data-stu-id="414c7-138">In Internet Explorer 11, open the same webpage.</span></span>  
1.  <span data-ttu-id="414c7-139">Launch the Internet Explorer DevTools.</span><span class="sxs-lookup"><span data-stu-id="414c7-139">Launch the Internet Explorer DevTools.</span></span>  
    *   <span data-ttu-id="414c7-140">Select `F12`.</span><span class="sxs-lookup"><span data-stu-id="414c7-140">Select `F12`.</span></span>  
    *   <span data-ttu-id="414c7-141">Hover anywhere, open a contextual menu \(right-click\), and choose **Inspect element**.</span><span class="sxs-lookup"><span data-stu-id="414c7-141">Hover anywhere, open a contextual menu \(right-click\), and choose **Inspect element**.</span></span>  <span data-ttu-id="414c7-142">For more information about how to use those tools, navigate to [Using the F12 developer tools][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326].</span><span class="sxs-lookup"><span data-stu-id="414c7-142">For more information about how to use those tools, navigate to [Using the F12 developer tools][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326].</span></span>  

## <span data-ttu-id="414c7-143">Remote debugging and IE mode</span><span class="sxs-lookup"><span data-stu-id="414c7-143">Remote debugging and IE mode</span></span>  

<span data-ttu-id="414c7-144">Launch Microsoft Edge \(Chromium\) with remote debugging turned on from the command-line interface.</span><span class="sxs-lookup"><span data-stu-id="414c7-144">Launch Microsoft Edge \(Chromium\) with remote debugging turned on from the command-line interface.</span></span>  <span data-ttu-id="414c7-145">Visual Studio, Visual Studio Code, and other development tools typically run a command to launch Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="414c7-145">Visual Studio, Visual Studio Code, and other development tools typically run a command to launch Microsoft Edge.</span></span>  <span data-ttu-id="414c7-146">The following command launches Microsoft Edge with the remote debugging port set to `9222`.</span><span class="sxs-lookup"><span data-stu-id="414c7-146">The following command launches Microsoft Edge with the remote debugging port set to `9222`.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="414c7-147">After you launch Microsoft Edge \(Chromium\) using a command-line argument, IE mode is unavailable.</span><span class="sxs-lookup"><span data-stu-id="414c7-147">After you launch Microsoft Edge \(Chromium\) using a command-line argument, IE mode is unavailable.</span></span>  <span data-ttu-id="414c7-148">You may still navigate to websites \(or apps\) that would otherwise display in IE mode.</span><span class="sxs-lookup"><span data-stu-id="414c7-148">You may still navigate to websites \(or apps\) that would otherwise display in IE mode.</span></span> <span data-ttu-id="414c7-149">The website \(or app\) content renders using Chromium, not Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="414c7-149">The website \(or app\) content renders using Chromium, not Internet Explorer 11.</span></span>  <span data-ttu-id="414c7-150">Expect the parts of the pages that rely on IE11, such as ActiveX controls, to not render correctly.</span><span class="sxs-lookup"><span data-stu-id="414c7-150">Expect the parts of the pages that rely on IE11, such as ActiveX controls, to not render correctly.</span></span>  <span data-ttu-id="414c7-151">The IE mode badge does not appear in the address bar.</span><span class="sxs-lookup"><span data-stu-id="414c7-151">The IE mode badge does not appear in the address bar.</span></span>  

<span data-ttu-id="414c7-152">IE mode remains unavailable until you completely close and restart Microsoft Edge \(Chromium\).</span><span class="sxs-lookup"><span data-stu-id="414c7-152">IE mode remains unavailable until you completely close and restart Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="414c7-153">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="414c7-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "Using the F12 developer tools | Microsoft Docs"  