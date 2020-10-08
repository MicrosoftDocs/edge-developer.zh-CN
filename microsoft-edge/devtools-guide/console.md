---
description: 使用 "控制台" 工具进行交互式调试和临时测试。
title: DevTools-Console
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、console
ms.custom: seodec18
ms.openlocfilehash: f2733cac57ed5f2364747ee64e669fa83aae41f4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563512"
---
# <span data-ttu-id="a46c0-104">控制台</span><span class="sxs-lookup"><span data-stu-id="a46c0-104">Console</span></span>

<span data-ttu-id="a46c0-105">Microsoft Edge 中的控制台开发人员工具可记录与网页相关联的信息，例如 JavaScript、网络请求和安全错误。</span><span class="sxs-lookup"><span data-stu-id="a46c0-105">The Console developer tool in Microsoft Edge logs information that's associated with a webpage, such as JavaScript, network requests, and security errors.</span></span> <span data-ttu-id="a46c0-106">你可以使用该控制台进行交互式调试和临时测试。</span><span class="sxs-lookup"><span data-stu-id="a46c0-106">You can use the Console for interactive debugging and ad hoc testing.</span></span> 

<span data-ttu-id="a46c0-107">若要打开 Microsoft Edge 中的控制台工具，请按 F12 键访问开发工具窗口 (或右键单击页面，然后选择 " **检查元素** ") 。</span><span class="sxs-lookup"><span data-stu-id="a46c0-107">To open the Console tool in Microsoft Edge, press the F12 key to access the developer tool window (or right-click on the page, and then select **Inspect Element**).</span></span> <span data-ttu-id="a46c0-108">然后，选择窗口顶部的 " **控制台** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a46c0-108">Then, select the **Console** tab at the top of the window.</span></span> 

<span data-ttu-id="a46c0-109">您也可以使用 "控制台" 工具与正在运行的网页进行通信。</span><span class="sxs-lookup"><span data-stu-id="a46c0-109">You can also use the Console tool to communicate to and from a running webpage.</span></span> <span data-ttu-id="a46c0-110">您可以使用该控制台执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a46c0-110">You can use the Console to:</span></span>

- <span data-ttu-id="a46c0-111">在代码运行时发布标准 [错误和状态代码](./console/error-and-status-codes.md) 以及信息性消息。</span><span class="sxs-lookup"><span data-stu-id="a46c0-111">Post standard [error and status codes](./console/error-and-status-codes.md) and informational messages as your code runs.</span></span>
- <span data-ttu-id="a46c0-112">从你的代码中包含的 [控制台 API](./console/console-api.md) 调用生成自定义调试日志。</span><span class="sxs-lookup"><span data-stu-id="a46c0-112">Generate custom debug logs from the [Console API](./console/console-api.md) calls you include in your code.</span></span>
- <span data-ttu-id="a46c0-113">提供用于检查关键变量和函数的当前返回值的 [命令行](./console/command-line.md) 和交互式树视图。</span><span class="sxs-lookup"><span data-stu-id="a46c0-113">Provide a [command line](./console/command-line.md) and interactive tree view for inspecting current return values of key variables and functions.</span></span>

## <span data-ttu-id="a46c0-114">控制台的部件</span><span class="sxs-lookup"><span data-stu-id="a46c0-114">Parts of the Console</span></span>

<span data-ttu-id="a46c0-115">下图显示了控制台的关键部分：</span><span class="sxs-lookup"><span data-stu-id="a46c0-115">The following image shows the key parts of the Console:</span></span>

![Microsoft Edge DevTools 控制台](./media/console.png)

1. <span data-ttu-id="a46c0-117">**错误**  / **警告**  / **信息**  / **日志**按钮：按指定类型筛选控制台输出。</span><span class="sxs-lookup"><span data-stu-id="a46c0-117">**Errors** / **Warnings** / **Info** / **Logs** buttons: Filter console output by the specified type.</span></span> <span data-ttu-id="a46c0-118">您可以通过按住 **Ctrl** 键来选择多个按钮。</span><span class="sxs-lookup"><span data-stu-id="a46c0-118">You can multi-select buttons by holding down the **Ctrl** key.</span></span> <span data-ttu-id="a46c0-119">" **全部** " 按钮将清除所有筛选器。</span><span class="sxs-lookup"><span data-stu-id="a46c0-119">The **All** button clears all filters.</span></span>

2. <span data-ttu-id="a46c0-120">"**清除**" 按钮 (**Ctrl + L**) ： "**清除**" 按钮将清除当前的控制台显示。</span><span class="sxs-lookup"><span data-stu-id="a46c0-120">**Clear** button (**Ctrl+L**): The **Clear** button clears the current console display.</span></span>

3. <span data-ttu-id="a46c0-121">"**保留日志**" 复选框：选中 "**保留日志**" 复选框将在页面刷新和关闭并重新打开 DevTools 时保持您的控制台输出。</span><span class="sxs-lookup"><span data-stu-id="a46c0-121">**Preserve Log** check box: Selecting the **Preserve Log** check box persists your console output across page refreshes and closing and reopening DevTools.</span></span> <span data-ttu-id="a46c0-122">仅当关闭选项卡或手动清除控制台时，才会清除控制台历史记录。</span><span class="sxs-lookup"><span data-stu-id="a46c0-122">The Console history clears only when the tab is closed or you manually clear the Console.</span></span>

4. <span data-ttu-id="a46c0-123">**目标**：使用 " **目标** " 下拉菜单切换到其他执行上下文，例如 `<iframe>` 页面中的页面或运行的扩展。</span><span class="sxs-lookup"><span data-stu-id="a46c0-123">**Target**: Use the **Target** drop-down menu to switch to a different execution context, such as an `<iframe>` in your page or a running extension.</span></span> <span data-ttu-id="a46c0-124">默认情况下，您的页面的顶级框架处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="a46c0-124">By default, the top-level frame of your page is selected.</span></span> <span data-ttu-id="a46c0-125">将鼠标悬停在所选的框架上将显示一个工具提示，显示该资源的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="a46c0-125">Hovering over a selected frame displays a tooltip that shows the full URL for that resource.</span></span>

5. <span data-ttu-id="a46c0-126">**显示控制台**  / **隐藏 "控制台**" 按钮 (**Ctrl** +  **&grave;** ) ：除了 "控制台" 面板之外，还可以通过按 "**显示控制台**  /  **隐藏控制台**" 按钮，使用其他 DevTools 面板底部的控制台。</span><span class="sxs-lookup"><span data-stu-id="a46c0-126">**Show Console** / **Hide Console** button (**Ctrl**+ **&grave;** ): In addition to the Console panel, you can use the console from the bottom of any other DevTools panel by pressing the **Show Console** / **Hide Console** button.</span></span> <span data-ttu-id="a46c0-127">在将 DevTools 打开到控制台面板时，该按钮不起作用。</span><span class="sxs-lookup"><span data-stu-id="a46c0-127">The button has no effect when DevTools is open to the Console panel.</span></span>
 
6. <span data-ttu-id="a46c0-128"> (**Ctrl + F**) **筛选日志**：还可以使用搜索框中的特定文本字符串筛选日志。</span><span class="sxs-lookup"><span data-stu-id="a46c0-128">**Filter logs** (**Ctrl+F**) : You can also filter logs by using a specific text string in the search box.</span></span>

7. <span data-ttu-id="a46c0-129">**调试器**：选择任何蓝色源链接以打开该特定代码行的 DevTools 调试程序进行进一步检查。</span><span class="sxs-lookup"><span data-stu-id="a46c0-129">**Debugger**: Select any blue source link to open the DevTools Debugger to that particular line of code for further inspection.</span></span>

## <span data-ttu-id="a46c0-130">快捷方式</span><span class="sxs-lookup"><span data-stu-id="a46c0-130">Shortcuts</span></span>

<span data-ttu-id="a46c0-131">操作</span><span class="sxs-lookup"><span data-stu-id="a46c0-131">Action</span></span>                                            | <span data-ttu-id="a46c0-132">快捷方式</span><span class="sxs-lookup"><span data-stu-id="a46c0-132">Shortcut</span></span>               
:-------------------------------------------------| :----------------------
<span data-ttu-id="a46c0-133">在关注的控制台中启动 DevTools</span><span class="sxs-lookup"><span data-stu-id="a46c0-133">Launch DevTools with Console in focus</span></span>             | <span data-ttu-id="a46c0-134">**Ctrl**  + **班次**  + **J**</span><span class="sxs-lookup"><span data-stu-id="a46c0-134">**Ctrl** + **Shift** + **J**</span></span> 
<span data-ttu-id="a46c0-135">切换到控制台</span><span class="sxs-lookup"><span data-stu-id="a46c0-135">Switch to the Console</span></span>                                 | <span data-ttu-id="a46c0-136">**Ctrl**  + **2**</span><span class="sxs-lookup"><span data-stu-id="a46c0-136">**Ctrl** + **2**</span></span>           
<span data-ttu-id="a46c0-137">从另一个 DevTools 选项卡中显示/隐藏控制台</span><span class="sxs-lookup"><span data-stu-id="a46c0-137">Show/hide the Console from another DevTools tab</span></span>       | <span data-ttu-id="a46c0-138">**Ctrl**  +  Ctrl **&grave;** ("后退" 滴答) </span><span class="sxs-lookup"><span data-stu-id="a46c0-138">**Ctrl** + **&grave;** (back tick)</span></span>  
<span data-ttu-id="a46c0-139">"执行 (单行" 命令) </span><span class="sxs-lookup"><span data-stu-id="a46c0-139">Execute (single-line command)</span></span>                     | **<span data-ttu-id="a46c0-140">Enter</span><span class="sxs-lookup"><span data-stu-id="a46c0-140">Enter</span></span>**                
<span data-ttu-id="a46c0-141">不执行 (多行命令的换行符) </span><span class="sxs-lookup"><span data-stu-id="a46c0-141">Line break without executing (multi-line command)</span></span> | <span data-ttu-id="a46c0-142">**班次**  + **Enter**或**Ctrl**  +  **enter**</span><span class="sxs-lookup"><span data-stu-id="a46c0-142">**Shift** + **Enter** or **Ctrl** + **Enter**</span></span>      
<span data-ttu-id="a46c0-143">清除所有邮件的控制台</span><span class="sxs-lookup"><span data-stu-id="a46c0-143">Clear the Console of all messages</span></span>                 | <span data-ttu-id="a46c0-144">**Ctrl**  + **L**</span><span class="sxs-lookup"><span data-stu-id="a46c0-144">**Ctrl** + **L**</span></span>           
<span data-ttu-id="a46c0-145">筛选日志 (将焦点设置到 "搜索" 框) </span><span class="sxs-lookup"><span data-stu-id="a46c0-145">Filter logs (set focus to search box)</span></span>             | <span data-ttu-id="a46c0-146">**Ctrl**  + **F**</span><span class="sxs-lookup"><span data-stu-id="a46c0-146">**Ctrl** + **F**</span></span>           
<span data-ttu-id="a46c0-147">在焦点) 时接受自动完成建议 (</span><span class="sxs-lookup"><span data-stu-id="a46c0-147">Accept auto-completion suggestion (when in focus)</span></span> | <span data-ttu-id="a46c0-148">**Enter** 或 **Tab**</span><span class="sxs-lookup"><span data-stu-id="a46c0-148">**Enter** or **Tab**</span></span>       
<span data-ttu-id="a46c0-149">上一个/下一个自动完成建议</span><span class="sxs-lookup"><span data-stu-id="a46c0-149">Previous/next auto-completion suggestion</span></span>          | <span data-ttu-id="a46c0-150">**向上键** /**向下键**</span><span class="sxs-lookup"><span data-stu-id="a46c0-150">**Up arrow key**/**Down arrow key**</span></span>   


