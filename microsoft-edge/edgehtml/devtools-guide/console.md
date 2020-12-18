---
description: 使用控制台工具进行交互式调试和临时测试。
title: DevTools - 控制台
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 控制台
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 472aafa9e6c6fd98ea952804f0e92ed0b774f59c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232284"
---
# <span data-ttu-id="b14f5-104">控制台</span><span class="sxs-lookup"><span data-stu-id="b14f5-104">Console</span></span>

<span data-ttu-id="b14f5-105">Microsoft Edge 中的控制台开发人员工具记录与网页关联的信息，例如 JavaScript、网络请求和安全错误。</span><span class="sxs-lookup"><span data-stu-id="b14f5-105">The Console developer tool in Microsoft Edge logs information that's associated with a webpage, such as JavaScript, network requests, and security errors.</span></span> <span data-ttu-id="b14f5-106">可以使用控制台进行交互式调试和临时测试。</span><span class="sxs-lookup"><span data-stu-id="b14f5-106">You can use the Console for interactive debugging and ad hoc testing.</span></span> 

<span data-ttu-id="b14f5-107">若要在 Microsoft Edge 中打开控制台工具，请按 F12 键以访问开发人员工具窗口 (或右键单击页面，然后选择"检查元素") 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b14f5-107">To open the Console tool in Microsoft Edge, press the F12 key to access the developer tool window (or right-click on the page, and then select **Inspect Element**).</span></span> <span data-ttu-id="b14f5-108">然后，选择 **窗口** 顶部的"控制台"选项卡。</span><span class="sxs-lookup"><span data-stu-id="b14f5-108">Then, select the **Console** tab at the top of the window.</span></span> 

<span data-ttu-id="b14f5-109">您还可以使用控制台工具与正在运行的网页进行通信和从该网页进行通信。</span><span class="sxs-lookup"><span data-stu-id="b14f5-109">You can also use the Console tool to communicate to and from a running webpage.</span></span> <span data-ttu-id="b14f5-110">可以使用控制台：</span><span class="sxs-lookup"><span data-stu-id="b14f5-110">You can use the Console to:</span></span>

- <span data-ttu-id="b14f5-111">在 [代码运行时](./console/error-and-status-codes.md) 发布标准错误和状态代码和信息性消息。</span><span class="sxs-lookup"><span data-stu-id="b14f5-111">Post standard [error and status codes](./console/error-and-status-codes.md) and informational messages as your code runs.</span></span>
- <span data-ttu-id="b14f5-112">通过包括在代码中的控制台 [API](./console/console-api.md) 调用生成自定义调试日志。</span><span class="sxs-lookup"><span data-stu-id="b14f5-112">Generate custom debug logs from the [Console API](./console/console-api.md) calls you include in your code.</span></span>
- <span data-ttu-id="b14f5-113">提供 [用于检查关键](./console/command-line.md) 变量和函数的当前返回值的命令行和交互式树视图。</span><span class="sxs-lookup"><span data-stu-id="b14f5-113">Provide a [command line](./console/command-line.md) and interactive tree view for inspecting current return values of key variables and functions.</span></span>

## <span data-ttu-id="b14f5-114">控制台的各个部分</span><span class="sxs-lookup"><span data-stu-id="b14f5-114">Parts of the Console</span></span>

<span data-ttu-id="b14f5-115">下图显示了控制台的关键部分：</span><span class="sxs-lookup"><span data-stu-id="b14f5-115">The following image shows the key parts of the Console:</span></span>

![Microsoft Edge DevTools 控制台](./media/console.png)

1. <span data-ttu-id="b14f5-117">**错误**  / **警告**  / **信息**  / **日志**按钮：按指定类型筛选控制台输出。</span><span class="sxs-lookup"><span data-stu-id="b14f5-117">**Errors** / **Warnings** / **Info** / **Logs** buttons: Filter console output by the specified type.</span></span> <span data-ttu-id="b14f5-118">按住 Ctrl 键可以多**选按钮。**</span><span class="sxs-lookup"><span data-stu-id="b14f5-118">You can multi-select buttons by holding down the **Ctrl** key.</span></span> <span data-ttu-id="b14f5-119">" **所有** "按钮清除所有筛选器。</span><span class="sxs-lookup"><span data-stu-id="b14f5-119">The **All** button clears all filters.</span></span>

2. <span data-ttu-id="b14f5-120">**Ctrl+L** (\*\*\*\* 清除按钮) ："清除"按钮可清除\*\*\*\* 当前控制台的显示。</span><span class="sxs-lookup"><span data-stu-id="b14f5-120">**Clear** button (**Ctrl+L**): The **Clear** button clears the current console display.</span></span>

3. <span data-ttu-id="b14f5-121">**"保留**日志"复选框：选中\*\*\*\*"保留日志"复选框可跨页面刷新、关闭和重新打开 DevTools 保留控制台输出。</span><span class="sxs-lookup"><span data-stu-id="b14f5-121">**Preserve Log** check box: Selecting the **Preserve Log** check box persists your console output across page refreshes and closing and reopening DevTools.</span></span> <span data-ttu-id="b14f5-122">控制台历史记录仅在关闭选项卡或手动清除控制台时清除。</span><span class="sxs-lookup"><span data-stu-id="b14f5-122">The Console history clears only when the tab is closed or you manually clear the Console.</span></span>

4. <span data-ttu-id="b14f5-123">**目标**：使用 **"** 目标"下拉菜单切换到其他执行上下文，如页面中的上下文或 `<iframe>` 正在运行的扩展。</span><span class="sxs-lookup"><span data-stu-id="b14f5-123">**Target**: Use the **Target** drop-down menu to switch to a different execution context, such as an `<iframe>` in your page or a running extension.</span></span> <span data-ttu-id="b14f5-124">默认情况下，选择页面的顶级框架。</span><span class="sxs-lookup"><span data-stu-id="b14f5-124">By default, the top-level frame of your page is selected.</span></span> <span data-ttu-id="b14f5-125">将鼠标悬停在选定框架上将显示一个工具提示，用于显示该资源的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="b14f5-125">Hovering over a selected frame displays a tooltip that shows the full URL for that resource.</span></span>

5. <span data-ttu-id="b14f5-126">**显示控制台**  / **按** **Ctrl** (隐藏控制台) ：除了控制台面板之外，还可以按"显示控制台隐藏控制台"按钮，从任何其他 +  **&grave;** DevTools\*\*\*\*  /  \*\*\*\* 面板的底部使用控制台。</span><span class="sxs-lookup"><span data-stu-id="b14f5-126">**Show Console** / **Hide Console** button (**Ctrl**+ **&grave;** ): In addition to the Console panel, you can use the console from the bottom of any other DevTools panel by pressing the **Show Console** / **Hide Console** button.</span></span> <span data-ttu-id="b14f5-127">当 DevTools 打开到控制台面板时，该按钮不起作用。</span><span class="sxs-lookup"><span data-stu-id="b14f5-127">The button has no effect when DevTools is open to the Console panel.</span></span>
 
6. <span data-ttu-id="b14f5-128">**筛选日志** (**Ctrl+F**) ：您还可以使用搜索框中的特定文本字符串筛选日志。</span><span class="sxs-lookup"><span data-stu-id="b14f5-128">**Filter logs** (**Ctrl+F**) : You can also filter logs by using a specific text string in the search box.</span></span>

7. <span data-ttu-id="b14f5-129">**调试器**：选择任何蓝色源链接，将 DevTools 调试器打开到该特定代码行，以便进一步检查。</span><span class="sxs-lookup"><span data-stu-id="b14f5-129">**Debugger**: Select any blue source link to open the DevTools Debugger to that particular line of code for further inspection.</span></span>

## <span data-ttu-id="b14f5-130">快捷方式</span><span class="sxs-lookup"><span data-stu-id="b14f5-130">Shortcuts</span></span>

<span data-ttu-id="b14f5-131">操作</span><span class="sxs-lookup"><span data-stu-id="b14f5-131">Action</span></span>                                            | <span data-ttu-id="b14f5-132">快捷方式</span><span class="sxs-lookup"><span data-stu-id="b14f5-132">Shortcut</span></span>               
:-------------------------------------------------| :----------------------
<span data-ttu-id="b14f5-133">在焦点上启动具有控制台的 DevTools</span><span class="sxs-lookup"><span data-stu-id="b14f5-133">Launch DevTools with Console in focus</span></span>             | <span data-ttu-id="b14f5-134">**Ctrl**  + **Shift**  + **J**</span><span class="sxs-lookup"><span data-stu-id="b14f5-134">**Ctrl** + **Shift** + **J**</span></span> 
<span data-ttu-id="b14f5-135">切换到控制台</span><span class="sxs-lookup"><span data-stu-id="b14f5-135">Switch to the Console</span></span>                                 | <span data-ttu-id="b14f5-136">**Ctrl**  + **2**</span><span class="sxs-lookup"><span data-stu-id="b14f5-136">**Ctrl** + **2**</span></span>           
<span data-ttu-id="b14f5-137">从另一个"开发工具"选项卡显示/隐藏控制台</span><span class="sxs-lookup"><span data-stu-id="b14f5-137">Show/hide the Console from another DevTools tab</span></span>       | <span data-ttu-id="b14f5-138">**Ctrl**  +  **&grave;** (刻度线) </span><span class="sxs-lookup"><span data-stu-id="b14f5-138">**Ctrl** + **&grave;** (back tick)</span></span>  
<span data-ttu-id="b14f5-139">执行 (命令行命令) </span><span class="sxs-lookup"><span data-stu-id="b14f5-139">Execute (single-line command)</span></span>                     | **<span data-ttu-id="b14f5-140">Enter</span><span class="sxs-lookup"><span data-stu-id="b14f5-140">Enter</span></span>**                
<span data-ttu-id="b14f5-141">无需执行多行 (换行符) </span><span class="sxs-lookup"><span data-stu-id="b14f5-141">Line break without executing (multi-line command)</span></span> | <span data-ttu-id="b14f5-142">**Shift**  + **Enter**或**Ctrl**  +  **Enter**</span><span class="sxs-lookup"><span data-stu-id="b14f5-142">**Shift** + **Enter** or **Ctrl** + **Enter**</span></span>      
<span data-ttu-id="b14f5-143">清除所有邮件的控制台</span><span class="sxs-lookup"><span data-stu-id="b14f5-143">Clear the Console of all messages</span></span>                 | <span data-ttu-id="b14f5-144">**Ctrl**  + **L**</span><span class="sxs-lookup"><span data-stu-id="b14f5-144">**Ctrl** + **L**</span></span>           
<span data-ttu-id="b14f5-145">筛选器日志 (将焦点设置为搜索框) </span><span class="sxs-lookup"><span data-stu-id="b14f5-145">Filter logs (set focus to search box)</span></span>             | <span data-ttu-id="b14f5-146">**Ctrl**  + **F**</span><span class="sxs-lookup"><span data-stu-id="b14f5-146">**Ctrl** + **F**</span></span>           
<span data-ttu-id="b14f5-147">当焦点在焦点 (接受自动完成) </span><span class="sxs-lookup"><span data-stu-id="b14f5-147">Accept auto-completion suggestion (when in focus)</span></span> | <span data-ttu-id="b14f5-148">**Enter** 或 **Tab**</span><span class="sxs-lookup"><span data-stu-id="b14f5-148">**Enter** or **Tab**</span></span>       
<span data-ttu-id="b14f5-149">上一个/下一个自动完成建议</span><span class="sxs-lookup"><span data-stu-id="b14f5-149">Previous/next auto-completion suggestion</span></span>          | <span data-ttu-id="b14f5-150">**向上箭头键** /**向下箭头键**</span><span class="sxs-lookup"><span data-stu-id="b14f5-150">**Up arrow key**/**Down arrow key**</span></span>   
