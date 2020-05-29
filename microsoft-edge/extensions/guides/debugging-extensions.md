---
description: 使用 F12 开发人员工具，了解如何调试扩展的后台脚本、内容脚本和扩展页。
title: 扩展-调试
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、javascript、开发人员、调试、调试
ms.custom: seodec18
ms.openlocfilehash: 34488870cb4e4a92a9d57859509ce7d1176cf284
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563301"
---
# <span data-ttu-id="8b77b-104">调试扩展</span><span class="sxs-lookup"><span data-stu-id="8b77b-104">Debugging extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="8b77b-105">你可以使用 F12 开发人员工具在 Microsoft Edge 中调试你的扩展。</span><span class="sxs-lookup"><span data-stu-id="8b77b-105">You can debug your extensions in Microsoft Edge by using F12 Developer Tools.</span></span>

<span data-ttu-id="8b77b-106">下面的视频介绍了一个有问题的 Microsoft Edge 扩展，并浏览每个调试方案并按方式进行修复。</span><span class="sxs-lookup"><span data-stu-id="8b77b-106">The following video goes through a buggy Microsoft Edge extension, walking though each debugging scenario and fixing it up along the way.</span></span> <span data-ttu-id="8b77b-107">有关详细信息，请参阅下面的分步说明。</span><span class="sxs-lookup"><span data-stu-id="8b77b-107">See the step-by-step instructions below for more info.</span></span>

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]


> [!NOTE]
> <span data-ttu-id="8b77b-108">为了利用对 F12 的扩展调试，您必须首先打开关于：标志的开发人员功能。</span><span class="sxs-lookup"><span data-stu-id="8b77b-108">In order to take advantage of extension debugging with F12, you must first turn on developer features in about:flags.</span></span> <span data-ttu-id="8b77b-109">有关如何执行此操作的详细信息，请参阅[添加和删除扩展](./adding-and-removing-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="8b77b-109">See [Adding and removing extensions](./adding-and-removing-extensions.md) for details on how to do this.</span></span>


## <span data-ttu-id="8b77b-110">后台脚本调试</span><span class="sxs-lookup"><span data-stu-id="8b77b-110">Background script debugging</span></span>
<span data-ttu-id="8b77b-111">若要开始调试你的扩展的后台脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b77b-111">To start debugging the background script of your extension:</span></span>

1. <span data-ttu-id="8b77b-112">单击 "**更多" （...）** ，然后单击 "**扩展**" 以转到 "扩展" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="8b77b-112">Click on **More (...)** followed by **Extensions** to go into the extension pane.</span></span>  
 !["更多" 按钮](./../media/morebutton.png)
2. <span data-ttu-id="8b77b-114">单击要调试的扩展。</span><span class="sxs-lookup"><span data-stu-id="8b77b-114">Click on the extension that you want to debug.</span></span>
3. <span data-ttu-id="8b77b-115">单击 "**背景页**" 链接以弹出后台进程的 F12。</span><span class="sxs-lookup"><span data-stu-id="8b77b-115">Click on the **Background page** link to bring up F12 for the background process.</span></span>  
 !["检查链接" 选项的选定扩展视图](./../media/debug-inspect.png)
4. <span data-ttu-id="8b77b-117">选择 F12 中的 "**调试器**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8b77b-117">Select the **Debugger** tab in F12.</span></span>
5. <span data-ttu-id="8b77b-118">导航到并选择您的扩展的后台脚本。</span><span class="sxs-lookup"><span data-stu-id="8b77b-118">Navigate to and select your extension's background script.</span></span>
6. <span data-ttu-id="8b77b-119">通过单击源代码行号的左侧，放置用于调试的断点。</span><span class="sxs-lookup"><span data-stu-id="8b77b-119">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![显示带中断点的后台脚本的 f12 控制台](./../media/debug-f12-background.png)
7. <span data-ttu-id="8b77b-121">选择 "**控制台**" 选项卡，然后执行命令 " `location.reload()` "。</span><span class="sxs-lookup"><span data-stu-id="8b77b-121">Select the **Console** tab and execute the command "`location.reload()`".</span></span> <span data-ttu-id="8b77b-122">这将重新执行后台脚本，使你可以逐句通过代码。</span><span class="sxs-lookup"><span data-stu-id="8b77b-122">This will re-execute the background script, allowing you to step through your code.</span></span>  
 ![带有位置的控制台。已输入重新加载](./../media/debug-f12-background-console.png)


## <span data-ttu-id="8b77b-124">内容脚本调试</span><span class="sxs-lookup"><span data-stu-id="8b77b-124">Content script debugging</span></span>
<span data-ttu-id="8b77b-125">要开始调试您的扩展的内容脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b77b-125">To start debugging the content script of your extension:</span></span>

1. <span data-ttu-id="8b77b-126">通过导航到 "**其他（...）** " 按钮并选择 **"f12 开发工具"** ，或按键盘上的 F12，启动 F12。</span><span class="sxs-lookup"><span data-stu-id="8b77b-126">Launch F12 by either navigating to the **More (...)** button and selecting **"F12 Developer Tools"** or by pressing F12 on your keyboard.</span></span>
2. <span data-ttu-id="8b77b-127">导航到您的扩展内容脚本，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="8b77b-127">Navigate to and select your extension's content script.</span></span> <span data-ttu-id="8b77b-128">当前正在运行的扩展的内容脚本将由每个扩展名的不同文件夹进行描绘。</span><span class="sxs-lookup"><span data-stu-id="8b77b-128">Content scripts for extensions currently running will be depicted by a different folder for each extension.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b77b-129">将仅显示运行的内容脚本。</span><span class="sxs-lookup"><span data-stu-id="8b77b-129">Only running content scripts will appear.</span></span>

3. <span data-ttu-id="8b77b-130">通过单击源代码行号的左侧，放置用于调试的断点。</span><span class="sxs-lookup"><span data-stu-id="8b77b-130">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![正在调试的内容脚本的 f12](./../media/debug-content-f12.png)
4. <span data-ttu-id="8b77b-132">刷新浏览器选项卡，通过代码开始单步执行。</span><span class="sxs-lookup"><span data-stu-id="8b77b-132">Refresh the browser tab to begin stepping though your code.</span></span>




## <span data-ttu-id="8b77b-133">扩展页面调试</span><span class="sxs-lookup"><span data-stu-id="8b77b-133">Extension page debugging</span></span>

<span data-ttu-id="8b77b-134">可使用两种方法来访问用于调试的扩展页面的源代码。</span><span class="sxs-lookup"><span data-stu-id="8b77b-134">There are two methods that can be used for accessing the source code of your extension page for debugging.</span></span> <span data-ttu-id="8b77b-135">一种方法适用于各种页面，而另一种方法仅适用于弹出式页面。</span><span class="sxs-lookup"><span data-stu-id="8b77b-135">One method applies to a variety of pages while the other only works for popup pages.</span></span>

### <span data-ttu-id="8b77b-136">调试任何扩展页</span><span class="sxs-lookup"><span data-stu-id="8b77b-136">Debugging any extension page</span></span>
<span data-ttu-id="8b77b-137">以下方法适用于所有扩展名页面，例如 "选项" 页面和弹出窗口：</span><span class="sxs-lookup"><span data-stu-id="8b77b-137">The following method works for all extension pages like the options page and popups:</span></span>


1. <span data-ttu-id="8b77b-138">右键单击您的页面的背景。</span><span class="sxs-lookup"><span data-stu-id="8b77b-138">Right-click on the background of your page.</span></span>
2. <span data-ttu-id="8b77b-139">选择 **"查看源"**。</span><span class="sxs-lookup"><span data-stu-id="8b77b-139">Select **"View source"**.</span></span>

   ![带 f12 的弹出调试](./../media/debug-popup-select.png)

3. <span data-ttu-id="8b77b-141">打开 F12 后，在要调试的文件中放置断点。</span><span class="sxs-lookup"><span data-stu-id="8b77b-141">Once F12 opens, place breakpoints within the file you want to debug.</span></span>

   ![带 f12 的弹出调试](./../media/debug-popup-f12.png)
4. <span data-ttu-id="8b77b-143">选择 "**控制台**" 选项卡，然后执行命令 `location.reload()` 。</span><span class="sxs-lookup"><span data-stu-id="8b77b-143">Select the **Console** tab and execute the command `location.reload()`.</span></span> <span data-ttu-id="8b77b-144">这将重新执行页面脚本，使你可以逐句通过代码。</span><span class="sxs-lookup"><span data-stu-id="8b77b-144">This will re-execute the page script, allowing you to step through your code.</span></span>  

   ![带有位置的控制台。已输入重新加载](./../media/debug-f12-background-console.png)

### <span data-ttu-id="8b77b-146">调试弹出窗口扩展页</span><span class="sxs-lookup"><span data-stu-id="8b77b-146">Debugging a popup extension page</span></span>
<span data-ttu-id="8b77b-147">虽然调试扩展页的方法也适用于弹出窗口扩展页面，但以下步骤概括了调试弹出窗口的另一种方法：</span><span class="sxs-lookup"><span data-stu-id="8b77b-147">While the method for debugging extension pages also applies to popup extension pages, the following steps outline another way to debug your popup:</span></span>

1. <span data-ttu-id="8b77b-148">右键单击您的扩展名图标。</span><span class="sxs-lookup"><span data-stu-id="8b77b-148">Right-click your extension's icon.</span></span>
2. <span data-ttu-id="8b77b-149">选择 **"检查弹出窗口"**。</span><span class="sxs-lookup"><span data-stu-id="8b77b-149">Select **"Inspect popup"**.</span></span>

   ![弹出调试检查](./../media/debug-popup-inspect.png)
3. <span data-ttu-id="8b77b-151">按照上面的步骤3和4操作，放置断点并重新加载弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="8b77b-151">Follow steps 3 and 4 above for placing breakpoints and reloading the popup.</span></span>
