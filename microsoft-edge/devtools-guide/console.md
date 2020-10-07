---
description: Use the Console tool for interactive debugging and ad hoc testing.
title: DevTools - Console
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, console
ms.custom: seodec18
ms.openlocfilehash: f2733cac57ed5f2364747ee64e669fa83aae41f4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563512"
---
# <span data-ttu-id="7a208-104">Console</span><span class="sxs-lookup"><span data-stu-id="7a208-104">Console</span></span>

<span data-ttu-id="7a208-105">The Console developer tool in Microsoft Edge logs information that's associated with a webpage, such as JavaScript, network requests, and security errors.</span><span class="sxs-lookup"><span data-stu-id="7a208-105">The Console developer tool in Microsoft Edge logs information that's associated with a webpage, such as JavaScript, network requests, and security errors.</span></span> <span data-ttu-id="7a208-106">You can use the Console for interactive debugging and ad hoc testing.</span><span class="sxs-lookup"><span data-stu-id="7a208-106">You can use the Console for interactive debugging and ad hoc testing.</span></span> 

<span data-ttu-id="7a208-107">To open the Console tool in Microsoft Edge, press the F12 key to access the developer tool window (or right-click on the page, and then select **Inspect Element**).</span><span class="sxs-lookup"><span data-stu-id="7a208-107">To open the Console tool in Microsoft Edge, press the F12 key to access the developer tool window (or right-click on the page, and then select **Inspect Element**).</span></span> <span data-ttu-id="7a208-108">Then, select the **Console** tab at the top of the window.</span><span class="sxs-lookup"><span data-stu-id="7a208-108">Then, select the **Console** tab at the top of the window.</span></span> 

<span data-ttu-id="7a208-109">You can also use the Console tool to communicate to and from a running webpage.</span><span class="sxs-lookup"><span data-stu-id="7a208-109">You can also use the Console tool to communicate to and from a running webpage.</span></span> <span data-ttu-id="7a208-110">You can use the Console to:</span><span class="sxs-lookup"><span data-stu-id="7a208-110">You can use the Console to:</span></span>

- <span data-ttu-id="7a208-111">Post standard [error and status codes](./console/error-and-status-codes.md) and informational messages as your code runs.</span><span class="sxs-lookup"><span data-stu-id="7a208-111">Post standard [error and status codes](./console/error-and-status-codes.md) and informational messages as your code runs.</span></span>
- <span data-ttu-id="7a208-112">Generate custom debug logs from the [Console API](./console/console-api.md) calls you include in your code.</span><span class="sxs-lookup"><span data-stu-id="7a208-112">Generate custom debug logs from the [Console API](./console/console-api.md) calls you include in your code.</span></span>
- <span data-ttu-id="7a208-113">Provide a [command line](./console/command-line.md) and interactive tree view for inspecting current return values of key variables and functions.</span><span class="sxs-lookup"><span data-stu-id="7a208-113">Provide a [command line](./console/command-line.md) and interactive tree view for inspecting current return values of key variables and functions.</span></span>

## <span data-ttu-id="7a208-114">Parts of the Console</span><span class="sxs-lookup"><span data-stu-id="7a208-114">Parts of the Console</span></span>

<span data-ttu-id="7a208-115">The following image shows the key parts of the Console:</span><span class="sxs-lookup"><span data-stu-id="7a208-115">The following image shows the key parts of the Console:</span></span>

![The Microsoft Edge DevTools console](./media/console.png)

1. <span data-ttu-id="7a208-117">**Errors** / **Warnings** / **Info** / **Logs** buttons: Filter console output by the specified type.</span><span class="sxs-lookup"><span data-stu-id="7a208-117">**Errors** / **Warnings** / **Info** / **Logs** buttons: Filter console output by the specified type.</span></span> <span data-ttu-id="7a208-118">You can multi-select buttons by holding down the **Ctrl** key.</span><span class="sxs-lookup"><span data-stu-id="7a208-118">You can multi-select buttons by holding down the **Ctrl** key.</span></span> <span data-ttu-id="7a208-119">The **All** button clears all filters.</span><span class="sxs-lookup"><span data-stu-id="7a208-119">The **All** button clears all filters.</span></span>

2. <span data-ttu-id="7a208-120">**Clear** button (**Ctrl+L**): The **Clear** button clears the current console display.</span><span class="sxs-lookup"><span data-stu-id="7a208-120">**Clear** button (**Ctrl+L**): The **Clear** button clears the current console display.</span></span>

3. <span data-ttu-id="7a208-121">**Preserve Log** check box: Selecting the **Preserve Log** check box persists your console output across page refreshes and closing and reopening DevTools.</span><span class="sxs-lookup"><span data-stu-id="7a208-121">**Preserve Log** check box: Selecting the **Preserve Log** check box persists your console output across page refreshes and closing and reopening DevTools.</span></span> <span data-ttu-id="7a208-122">The Console history clears only when the tab is closed or you manually clear the Console.</span><span class="sxs-lookup"><span data-stu-id="7a208-122">The Console history clears only when the tab is closed or you manually clear the Console.</span></span>

4. <span data-ttu-id="7a208-123">**Target**: Use the **Target** drop-down menu to switch to a different execution context, such as an `<iframe>` in your page or a running extension.</span><span class="sxs-lookup"><span data-stu-id="7a208-123">**Target**: Use the **Target** drop-down menu to switch to a different execution context, such as an `<iframe>` in your page or a running extension.</span></span> <span data-ttu-id="7a208-124">By default, the top-level frame of your page is selected.</span><span class="sxs-lookup"><span data-stu-id="7a208-124">By default, the top-level frame of your page is selected.</span></span> <span data-ttu-id="7a208-125">Hovering over a selected frame displays a tooltip that shows the full URL for that resource.</span><span class="sxs-lookup"><span data-stu-id="7a208-125">Hovering over a selected frame displays a tooltip that shows the full URL for that resource.</span></span>

5. <span data-ttu-id="7a208-126">**Show Console** / **Hide Console** button (**Ctrl**+ **&grave;** ): In addition to the Console panel, you can use the console from the bottom of any other DevTools panel by pressing the **Show Console** / **Hide Console** button.</span><span class="sxs-lookup"><span data-stu-id="7a208-126">**Show Console** / **Hide Console** button (**Ctrl**+ **&grave;** ): In addition to the Console panel, you can use the console from the bottom of any other DevTools panel by pressing the **Show Console** / **Hide Console** button.</span></span> <span data-ttu-id="7a208-127">The button has no effect when DevTools is open to the Console panel.</span><span class="sxs-lookup"><span data-stu-id="7a208-127">The button has no effect when DevTools is open to the Console panel.</span></span>
 
6. <span data-ttu-id="7a208-128">**Filter logs** (**Ctrl+F**) : You can also filter logs by using a specific text string in the search box.</span><span class="sxs-lookup"><span data-stu-id="7a208-128">**Filter logs** (**Ctrl+F**) : You can also filter logs by using a specific text string in the search box.</span></span>

7. <span data-ttu-id="7a208-129">**Debugger**: Select any blue source link to open the DevTools Debugger to that particular line of code for further inspection.</span><span class="sxs-lookup"><span data-stu-id="7a208-129">**Debugger**: Select any blue source link to open the DevTools Debugger to that particular line of code for further inspection.</span></span>

## <span data-ttu-id="7a208-130">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="7a208-130">Shortcuts</span></span>

<span data-ttu-id="7a208-131">Action</span><span class="sxs-lookup"><span data-stu-id="7a208-131">Action</span></span>                                            | <span data-ttu-id="7a208-132">Shortcut</span><span class="sxs-lookup"><span data-stu-id="7a208-132">Shortcut</span></span>               
:-------------------------------------------------| :----------------------
<span data-ttu-id="7a208-133">Launch DevTools with Console in focus</span><span class="sxs-lookup"><span data-stu-id="7a208-133">Launch DevTools with Console in focus</span></span>             | <span data-ttu-id="7a208-134">**Ctrl** + **Shift** + **J**</span><span class="sxs-lookup"><span data-stu-id="7a208-134">**Ctrl** + **Shift** + **J**</span></span> 
<span data-ttu-id="7a208-135">Switch to the Console</span><span class="sxs-lookup"><span data-stu-id="7a208-135">Switch to the Console</span></span>                                 | <span data-ttu-id="7a208-136">**Ctrl** + **2**</span><span class="sxs-lookup"><span data-stu-id="7a208-136">**Ctrl** + **2**</span></span>           
<span data-ttu-id="7a208-137">Show/hide the Console from another DevTools tab</span><span class="sxs-lookup"><span data-stu-id="7a208-137">Show/hide the Console from another DevTools tab</span></span>       | <span data-ttu-id="7a208-138">**Ctrl** + **&grave;** (back tick)</span><span class="sxs-lookup"><span data-stu-id="7a208-138">**Ctrl** + **&grave;** (back tick)</span></span>  
<span data-ttu-id="7a208-139">Execute (single-line command)</span><span class="sxs-lookup"><span data-stu-id="7a208-139">Execute (single-line command)</span></span>                     | **<span data-ttu-id="7a208-140">Enter</span><span class="sxs-lookup"><span data-stu-id="7a208-140">Enter</span></span>**                
<span data-ttu-id="7a208-141">Line break without executing (multi-line command)</span><span class="sxs-lookup"><span data-stu-id="7a208-141">Line break without executing (multi-line command)</span></span> | <span data-ttu-id="7a208-142">**Shift** + **Enter** or **Ctrl** + **Enter**</span><span class="sxs-lookup"><span data-stu-id="7a208-142">**Shift** + **Enter** or **Ctrl** + **Enter**</span></span>      
<span data-ttu-id="7a208-143">Clear the Console of all messages</span><span class="sxs-lookup"><span data-stu-id="7a208-143">Clear the Console of all messages</span></span>                 | <span data-ttu-id="7a208-144">**Ctrl** + **L**</span><span class="sxs-lookup"><span data-stu-id="7a208-144">**Ctrl** + **L**</span></span>           
<span data-ttu-id="7a208-145">Filter logs (set focus to search box)</span><span class="sxs-lookup"><span data-stu-id="7a208-145">Filter logs (set focus to search box)</span></span>             | <span data-ttu-id="7a208-146">**Ctrl** + **F**</span><span class="sxs-lookup"><span data-stu-id="7a208-146">**Ctrl** + **F**</span></span>           
<span data-ttu-id="7a208-147">Accept auto-completion suggestion (when in focus)</span><span class="sxs-lookup"><span data-stu-id="7a208-147">Accept auto-completion suggestion (when in focus)</span></span> | <span data-ttu-id="7a208-148">**Enter** or **Tab**</span><span class="sxs-lookup"><span data-stu-id="7a208-148">**Enter** or **Tab**</span></span>       
<span data-ttu-id="7a208-149">Previous/next auto-completion suggestion</span><span class="sxs-lookup"><span data-stu-id="7a208-149">Previous/next auto-completion suggestion</span></span>          | <span data-ttu-id="7a208-150">**Up arrow key**/**Down arrow key**</span><span class="sxs-lookup"><span data-stu-id="7a208-150">**Up arrow key**/**Down arrow key**</span></span>   


