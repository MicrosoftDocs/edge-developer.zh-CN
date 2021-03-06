---
description: 使用 F12 开发人员工具，了解如何调试扩展的后台脚本、内容脚本和扩展页。
title: 调试|扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， javascript， 开发人员， 调试， 调试
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a23c7558080cca7671cdfc9790705a8d8c9ed705
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399363"
---
# <a name="debugging-extensions"></a><span data-ttu-id="79dbf-104">调试扩展</span><span class="sxs-lookup"><span data-stu-id="79dbf-104">Debugging extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="79dbf-105">可以使用 F12 开发人员工具在 Microsoft Edge 中调试扩展。</span><span class="sxs-lookup"><span data-stu-id="79dbf-105">You can debug your extensions in Microsoft Edge by using F12 Developer Tools.</span></span>  

<span data-ttu-id="79dbf-106">以下视频演示了一个缺陷的 Microsoft Edge 扩展，浏览每个调试方案并一直进行修复。</span><span class="sxs-lookup"><span data-stu-id="79dbf-106">The following video goes through a buggy Microsoft Edge extension, walking though each debugging scenario and fixing it up along the way.</span></span>  <span data-ttu-id="79dbf-107">有关详细信息，请参阅下面的分步说明。</span><span class="sxs-lookup"><span data-stu-id="79dbf-107">See the step-by-step instructions below for more info.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]  

> [!NOTE]
> <span data-ttu-id="79dbf-108">为了利用 F12 的扩展调试，必须先打开 about：flags 中的开发人员功能。</span><span class="sxs-lookup"><span data-stu-id="79dbf-108">In order to take advantage of extension debugging with F12, you must first turn on developer features in about:flags.</span></span>  <span data-ttu-id="79dbf-109">请参阅 ["添加和删除扩展"，](./adding-and-removing-extensions.md) 详细了解如何这样做。</span><span class="sxs-lookup"><span data-stu-id="79dbf-109">See [Adding and removing extensions](./adding-and-removing-extensions.md) for details on how to do this.</span></span>  

## <a name="background-script-debugging"></a><span data-ttu-id="79dbf-110">后台脚本调试</span><span class="sxs-lookup"><span data-stu-id="79dbf-110">Background script debugging</span></span>  

<span data-ttu-id="79dbf-111">若要开始调试扩展的后台脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79dbf-111">To start debugging the background script of your extension:</span></span>  

1.  <span data-ttu-id="79dbf-112">单击 **"更多 (...) \*\*\*\*后跟"扩展**"转到扩展窗格。</span><span class="sxs-lookup"><span data-stu-id="79dbf-112">Click on **More (...)** followed by **Extensions** to go into the extension pane.</span></span>  
    
    ![“更多”按钮](../media/morebutton.png)  
    
1.  <span data-ttu-id="79dbf-114">单击要调试的扩展。</span><span class="sxs-lookup"><span data-stu-id="79dbf-114">Click on the extension that you want to debug.</span></span>  
1.  <span data-ttu-id="79dbf-115">单击" **后台"页面** 链接，为后台进程显示 F12。</span><span class="sxs-lookup"><span data-stu-id="79dbf-115">Click on the **Background page** link to bring up F12 for the background process.</span></span>  
    
    ![具有检查链接的选项的选定扩展视图](../media/debug-inspect.png)  
    
1.  <span data-ttu-id="79dbf-117">选择 **F12 中的** "调试器"选项卡。</span><span class="sxs-lookup"><span data-stu-id="79dbf-117">Select the **Debugger** tab in F12.</span></span>  
1.  <span data-ttu-id="79dbf-118">导航到扩展的后台脚本并选择该脚本。</span><span class="sxs-lookup"><span data-stu-id="79dbf-118">Navigate to and select your extension's background script.</span></span>  
1.  <span data-ttu-id="79dbf-119">单击源代码行号的左侧，放置用于调试的断点。</span><span class="sxs-lookup"><span data-stu-id="79dbf-119">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
    
    ![显示具有断点的背景脚本的 f12 控制台](../media/debug-f12-background.png)  
    
1.  <span data-ttu-id="79dbf-121">选择 **"控制台"** 选项卡并执行 `location.reload()` 命令。</span><span class="sxs-lookup"><span data-stu-id="79dbf-121">Select the **Console** tab and execute the `location.reload()` command.</span></span>  <span data-ttu-id="79dbf-122">这将重新执行后台脚本，从而允许您逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="79dbf-122">This will re-execute the background script, allowing you to step through your code.</span></span>  
    
    ![输入了 location.reload 的控制台](../media/debug-f12-background-console.png)  
    
## <a name="content-script-debugging"></a><span data-ttu-id="79dbf-124">内容脚本调试</span><span class="sxs-lookup"><span data-stu-id="79dbf-124">Content script debugging</span></span>  

<span data-ttu-id="79dbf-125">若要开始调试扩展的内容脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79dbf-125">To start debugging the content script of your extension:</span></span>  

1.  <span data-ttu-id="79dbf-126">通过导航到"更多\*\* (...) **按钮并选择 F12 开发人员工具或按键盘来启动**F12。\*\* `F12`</span><span class="sxs-lookup"><span data-stu-id="79dbf-126">Launch F12 by either navigating to the **More (...)** button and selecting **F12 Developer Tools** or by pressing `F12` on your keyboard.</span></span>  
1.  <span data-ttu-id="79dbf-127">导航到并选择扩展的内容脚本。</span><span class="sxs-lookup"><span data-stu-id="79dbf-127">Navigate to and select your extension's content script.</span></span>  <span data-ttu-id="79dbf-128">当前运行的扩展的内容脚本将用每个扩展的不同文件夹描述。</span><span class="sxs-lookup"><span data-stu-id="79dbf-128">Content scripts for extensions currently running will be depicted by a different folder for each extension.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="79dbf-129">只显示运行的内容脚本。</span><span class="sxs-lookup"><span data-stu-id="79dbf-129">Only running content scripts will appear.</span></span>  
    
1.  <span data-ttu-id="79dbf-130">单击源代码行号的左侧，放置用于调试的断点。</span><span class="sxs-lookup"><span data-stu-id="79dbf-130">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
    
    ![正在调试内容脚本的 f12](../media/debug-content-f12.png)  
    
1.  <span data-ttu-id="79dbf-132">刷新浏览器选项卡以开始逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="79dbf-132">Refresh the browser tab to begin stepping though your code.</span></span>  
    
## <a name="extension-page-debugging"></a><span data-ttu-id="79dbf-133">扩展页调试</span><span class="sxs-lookup"><span data-stu-id="79dbf-133">Extension page debugging</span></span>  

<span data-ttu-id="79dbf-134">有两种方法可用于访问扩展页的源代码进行调试。</span><span class="sxs-lookup"><span data-stu-id="79dbf-134">There are two methods that can be used for accessing the source code of your extension page for debugging.</span></span>  <span data-ttu-id="79dbf-135">一种方法适用于各种页面，另一种方法仅适用于弹出页。</span><span class="sxs-lookup"><span data-stu-id="79dbf-135">One method applies to a variety of pages while the other only works for popup pages.</span></span>  

### <a name="debugging-any-extension-page"></a><span data-ttu-id="79dbf-136">调试任何扩展页</span><span class="sxs-lookup"><span data-stu-id="79dbf-136">Debugging any extension page</span></span>  

<span data-ttu-id="79dbf-137">以下方法适用于选项页和弹出窗口等所有扩展页面：</span><span class="sxs-lookup"><span data-stu-id="79dbf-137">The following method works for all extension pages like the options page and popups:</span></span>  

1.  <span data-ttu-id="79dbf-138">右键单击页面背景。</span><span class="sxs-lookup"><span data-stu-id="79dbf-138">Right-click on the background of your page.</span></span>  
1.  <span data-ttu-id="79dbf-139">选择 **"查看源"。**</span><span class="sxs-lookup"><span data-stu-id="79dbf-139">Select **View source**.</span></span>  
    
    ![使用 f12 打开弹出窗口调试](../media/debug-popup-select.png)  
    
1.  <span data-ttu-id="79dbf-141">F12 打开后，在要调试的文件中放置断点。</span><span class="sxs-lookup"><span data-stu-id="79dbf-141">Once F12 opens, place breakpoints within the file you want to debug.</span></span>  
    
    ![使用 f12 进行弹出式调试](../media/debug-popup-f12.png)  
    
1.  <span data-ttu-id="79dbf-143">选择 **控制台** 选项卡并执行命令 `location.reload()` 。</span><span class="sxs-lookup"><span data-stu-id="79dbf-143">Select the **Console** tab and execute the command `location.reload()`.</span></span>  <span data-ttu-id="79dbf-144">这将重新执行页面脚本，从而允许您逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="79dbf-144">This will re-execute the page script, allowing you to step through your code.</span></span>  
    
    ![输入了 location.reload 的控制台](../media/debug-f12-background-console.png)  
    
### <a name="debugging-a-popup-extension-page"></a><span data-ttu-id="79dbf-146">调试弹出窗口扩展页</span><span class="sxs-lookup"><span data-stu-id="79dbf-146">Debugging a popup extension page</span></span>  

<span data-ttu-id="79dbf-147">尽管调试扩展页的方法也适用于弹出扩展页，但以下步骤概述了调试弹出窗口的另一种方法：</span><span class="sxs-lookup"><span data-stu-id="79dbf-147">While the method for debugging extension pages also applies to popup extension pages, the following steps outline another way to debug your popup:</span></span>  

1.  <span data-ttu-id="79dbf-148">右键单击扩展的图标。</span><span class="sxs-lookup"><span data-stu-id="79dbf-148">Right-click your extension's icon.</span></span>  
1.  <span data-ttu-id="79dbf-149">选择 **"检查"弹出窗口**。</span><span class="sxs-lookup"><span data-stu-id="79dbf-149">Select **Inspect popup**.</span></span>  
    
    ![弹出窗口调试检查](../media/debug-popup-inspect.png)  
    
1.  <span data-ttu-id="79dbf-151">按照上述步骤 3 和 4 放置断点并重新加载弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="79dbf-151">Follow steps 3 and 4 above for placing breakpoints and reloading the popup.</span></span>  
    