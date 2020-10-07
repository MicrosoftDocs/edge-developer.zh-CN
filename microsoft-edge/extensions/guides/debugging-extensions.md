---
description: With F12 Developer Tools, learn how to debug an extension's background script, content scripts, and extension pages.
title: Extensions - Debugging
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, javascript, developer, debug, debugging
ms.custom: seodec18
ms.openlocfilehash: 34488870cb4e4a92a9d57859509ce7d1176cf284
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563301"
---
# <span data-ttu-id="a9bc9-104">Debugging extensions</span><span class="sxs-lookup"><span data-stu-id="a9bc9-104">Debugging extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="a9bc9-105">You can debug your extensions in Microsoft Edge by using F12 Developer Tools.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-105">You can debug your extensions in Microsoft Edge by using F12 Developer Tools.</span></span>

<span data-ttu-id="a9bc9-106">The following video goes through a buggy Microsoft Edge extension, walking though each debugging scenario and fixing it up along the way.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-106">The following video goes through a buggy Microsoft Edge extension, walking though each debugging scenario and fixing it up along the way.</span></span> <span data-ttu-id="a9bc9-107">See the step-by-step instructions below for more info.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-107">See the step-by-step instructions below for more info.</span></span>

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]


> [!NOTE]
> <span data-ttu-id="a9bc9-108">In order to take advantage of extension debugging with F12, you must first turn on developer features in about:flags.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-108">In order to take advantage of extension debugging with F12, you must first turn on developer features in about:flags.</span></span> <span data-ttu-id="a9bc9-109">See [Adding and removing extensions](./adding-and-removing-extensions.md) for details on how to do this.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-109">See [Adding and removing extensions](./adding-and-removing-extensions.md) for details on how to do this.</span></span>


## <span data-ttu-id="a9bc9-110">Background script debugging</span><span class="sxs-lookup"><span data-stu-id="a9bc9-110">Background script debugging</span></span>
<span data-ttu-id="a9bc9-111">To start debugging the background script of your extension:</span><span class="sxs-lookup"><span data-stu-id="a9bc9-111">To start debugging the background script of your extension:</span></span>

1. <span data-ttu-id="a9bc9-112">Click on **More (...)** followed by **Extensions** to go into the extension pane.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-112">Click on **More (...)** followed by **Extensions** to go into the extension pane.</span></span>  
 ![more button](./../media/morebutton.png)
2. <span data-ttu-id="a9bc9-114">Click on the extension that you want to debug.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-114">Click on the extension that you want to debug.</span></span>
3. <span data-ttu-id="a9bc9-115">Click on the **Background page** link to bring up F12 for the background process.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-115">Click on the **Background page** link to bring up F12 for the background process.</span></span>  
 ![selected extension view of options with inspect link](./../media/debug-inspect.png)
4. <span data-ttu-id="a9bc9-117">Select the **Debugger** tab in F12.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-117">Select the **Debugger** tab in F12.</span></span>
5. <span data-ttu-id="a9bc9-118">Navigate to and select your extension's background script.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-118">Navigate to and select your extension's background script.</span></span>
6. <span data-ttu-id="a9bc9-119">Place breakpoints for debugging by clicking to the left of the source code line number.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-119">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![f12 console showing background script with break points](./../media/debug-f12-background.png)
7. <span data-ttu-id="a9bc9-121">Select the **Console** tab and execute the command "`location.reload()`".</span><span class="sxs-lookup"><span data-stu-id="a9bc9-121">Select the **Console** tab and execute the command "`location.reload()`".</span></span> <span data-ttu-id="a9bc9-122">This will re-execute the background script, allowing you to step through your code.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-122">This will re-execute the background script, allowing you to step through your code.</span></span>  
 ![console with location.reload entered](./../media/debug-f12-background-console.png)


## <span data-ttu-id="a9bc9-124">Content script debugging</span><span class="sxs-lookup"><span data-stu-id="a9bc9-124">Content script debugging</span></span>
<span data-ttu-id="a9bc9-125">To start debugging the content script of your extension:</span><span class="sxs-lookup"><span data-stu-id="a9bc9-125">To start debugging the content script of your extension:</span></span>

1. <span data-ttu-id="a9bc9-126">Launch F12 by either navigating to the **More (...)** button and selecting **"F12 Developer Tools"** or by pressing F12 on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-126">Launch F12 by either navigating to the **More (...)** button and selecting **"F12 Developer Tools"** or by pressing F12 on your keyboard.</span></span>
2. <span data-ttu-id="a9bc9-127">Navigate to and select your extension's content script.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-127">Navigate to and select your extension's content script.</span></span> <span data-ttu-id="a9bc9-128">Content scripts for extensions currently running will be depicted by a different folder for each extension.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-128">Content scripts for extensions currently running will be depicted by a different folder for each extension.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a9bc9-129">Only running content scripts will appear.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-129">Only running content scripts will appear.</span></span>

3. <span data-ttu-id="a9bc9-130">Place breakpoints for debugging by clicking to the left of the source code line number.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-130">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![f12 with content script being debugged](./../media/debug-content-f12.png)
4. <span data-ttu-id="a9bc9-132">Refresh the browser tab to begin stepping though your code.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-132">Refresh the browser tab to begin stepping though your code.</span></span>




## <span data-ttu-id="a9bc9-133">Extension page debugging</span><span class="sxs-lookup"><span data-stu-id="a9bc9-133">Extension page debugging</span></span>

<span data-ttu-id="a9bc9-134">There are two methods that can be used for accessing the source code of your extension page for debugging.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-134">There are two methods that can be used for accessing the source code of your extension page for debugging.</span></span> <span data-ttu-id="a9bc9-135">One method applies to a variety of pages while the other only works for popup pages.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-135">One method applies to a variety of pages while the other only works for popup pages.</span></span>

### <span data-ttu-id="a9bc9-136">Debugging any extension page</span><span class="sxs-lookup"><span data-stu-id="a9bc9-136">Debugging any extension page</span></span>
<span data-ttu-id="a9bc9-137">The following method works for all extension pages like the options page and popups:</span><span class="sxs-lookup"><span data-stu-id="a9bc9-137">The following method works for all extension pages like the options page and popups:</span></span>


1. <span data-ttu-id="a9bc9-138">Right-click on the background of your page.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-138">Right-click on the background of your page.</span></span>
2. <span data-ttu-id="a9bc9-139">Select **"View source"**.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-139">Select **"View source"**.</span></span>

   ![popup debugging with f12](./../media/debug-popup-select.png)

3. <span data-ttu-id="a9bc9-141">Once F12 opens, place breakpoints within the file you want to debug.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-141">Once F12 opens, place breakpoints within the file you want to debug.</span></span>

   ![popup debugging with f12](./../media/debug-popup-f12.png)
4. <span data-ttu-id="a9bc9-143">Select the **Console** tab and execute the command `location.reload()`.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-143">Select the **Console** tab and execute the command `location.reload()`.</span></span> <span data-ttu-id="a9bc9-144">This will re-execute the page script, allowing you to step through your code.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-144">This will re-execute the page script, allowing you to step through your code.</span></span>  

   ![console with location.reload entered](./../media/debug-f12-background-console.png)

### <span data-ttu-id="a9bc9-146">Debugging a popup extension page</span><span class="sxs-lookup"><span data-stu-id="a9bc9-146">Debugging a popup extension page</span></span>
<span data-ttu-id="a9bc9-147">While the method for debugging extension pages also applies to popup extension pages, the following steps outline another way to debug your popup:</span><span class="sxs-lookup"><span data-stu-id="a9bc9-147">While the method for debugging extension pages also applies to popup extension pages, the following steps outline another way to debug your popup:</span></span>

1. <span data-ttu-id="a9bc9-148">Right-click your extension's icon.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-148">Right-click your extension's icon.</span></span>
2. <span data-ttu-id="a9bc9-149">Select **"Inspect popup"**.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-149">Select **"Inspect popup"**.</span></span>

   ![popup debug inspect](./../media/debug-popup-inspect.png)
3. <span data-ttu-id="a9bc9-151">Follow steps 3 and 4 above for placing breakpoints and reloading the popup.</span><span class="sxs-lookup"><span data-stu-id="a9bc9-151">Follow steps 3 and 4 above for placing breakpoints and reloading the popup.</span></span>
