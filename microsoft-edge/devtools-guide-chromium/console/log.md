---
description: 了解如何将消息记录到控制台。
title: 在控制台中记录消息入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3a2562eeb25bcee7c8b5195f6f2297613e37f2d6
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993147"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# <span data-ttu-id="d59d6-104">在控制台中记录消息入门</span><span class="sxs-lookup"><span data-stu-id="d59d6-104">Get Started With Logging Messages In The Console</span></span>   



<span data-ttu-id="d59d6-105">此交互式教程介绍如何在 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 控制台中记录和筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="d59d6-105">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="控制台中的消息" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   <span data-ttu-id="d59d6-107">**控制台**中的消息</span><span class="sxs-lookup"><span data-stu-id="d59d6-107">Messages in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="d59d6-108">本教程旨在按顺序完成。</span><span class="sxs-lookup"><span data-stu-id="d59d6-108">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="d59d6-109">它假定你了解 web 开发的基础知识，例如如何使用 JavaScript 向页面添加交互。</span><span class="sxs-lookup"><span data-stu-id="d59d6-109">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <span data-ttu-id="d59d6-110">设置演示和 DevTools</span><span class="sxs-lookup"><span data-stu-id="d59d6-110">Set up the demo and DevTools</span></span>   

<span data-ttu-id="d59d6-111">本教程旨在使您能够打开演示并自行尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="d59d6-111">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="d59d6-112">当您进行物理跟踪时，更有可能会在以后记忆工作流。</span><span class="sxs-lookup"><span data-stu-id="d59d6-112">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="d59d6-113">保留 `Control` \ (Windows \ ) 或 `Command` \ (macOS \ ) ，然后单击 " **控制台日志示例** " 以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="d59d6-113">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="d59d6-114">控制台日志示例</span><span class="sxs-lookup"><span data-stu-id="d59d6-114">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="控制台中的消息" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  <span data-ttu-id="d59d6-115">聚焦演示，然后按 `Control` + `Shift` + `J` (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="d59d6-115">Focus the demo and then press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="d59d6-116">默认情况下，DevTools 将在演示右侧打开。</span><span class="sxs-lookup"><span data-stu-id="d59d6-116">By default DevTools opens to the right of the demo.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="控制台中的消息" lightbox="../media/console-example-devtools-right-console.msft.png":::
             <span data-ttu-id="d59d6-118">DevTools 将在演示右侧打开</span><span class="sxs-lookup"><span data-stu-id="d59d6-118">DevTools opens to the right of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="d59d6-119">[将 DevTools 停靠在窗口底部][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="d59d6-119">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="控制台中的消息" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             <span data-ttu-id="d59d6-121">DevTools 停靠在演示底部</span><span class="sxs-lookup"><span data-stu-id="d59d6-121">DevTools docked to the bottom of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="d59d6-122">[将 DevTools 取消停靠到一个单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="d59d6-122">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="控制台中的消息" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             <span data-ttu-id="d59d6-124">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="d59d6-124">Browser in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="d59d6-125">[将 DevTools 取消停靠到一个单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="d59d6-125">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="控制台中的消息" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             <span data-ttu-id="d59d6-127">DevTools 在单独窗口中取消停靠</span><span class="sxs-lookup"><span data-stu-id="d59d6-127">DevTools undocked in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="d59d6-128">查看从 JavaScript 记录的消息</span><span class="sxs-lookup"><span data-stu-id="d59d6-128">View messages logged from JavaScript</span></span>   

<span data-ttu-id="d59d6-129">您在控制台中看到的大多数消息来自于编写页面 JavaScript 的 web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="d59d6-129">Most messages that you see in the Console come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="d59d6-130">本部分的目标是介绍你可能会在控制台中看到的不同消息类型，并介绍如何从你自己的 JavaScript 中自己记录每种消息类型。</span><span class="sxs-lookup"><span data-stu-id="d59d6-130">The goal of this section is to introduce you to the different message types that you are likely to see in the Console, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="d59d6-131">单击演示中的 " **日志信息** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="d59d6-131">Click the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="d59d6-132">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d59d6-132">gets logged to the Console.</span></span>
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="控制台中的消息" lightbox="../media/console-log-info.msft.png":::
       <span data-ttu-id="d59d6-134">单击 "**日志信息**" 后的**控制台**</span><span class="sxs-lookup"><span data-stu-id="d59d6-134">The **Console** after clicking **Log Info**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-135">`Hello, Console!`在控制台中的邮件旁边，单击 " **log.js： 2**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-135">Next to the `Hello, Console!` message in the Console click **log.js:2**.</span></span>  <span data-ttu-id="d59d6-136">"源" 面板将打开并突出显示导致消息登录到控制台的代码行。</span><span class="sxs-lookup"><span data-stu-id="d59d6-136">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="d59d6-137">当页面的 JavaScript 运行时，将记录此消息 `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-137">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="控制台中的消息" lightbox="../media/console-sources-logjs.msft.png":::
       <span data-ttu-id="d59d6-139">单击后，DevTools 将打开 " **源** " 面板</span><span class="sxs-lookup"><span data-stu-id="d59d6-139">DevTools opens the **Sources** panel after you click</span></span> `log.js:2`  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-140">使用以下任一工作流向后导航到 **控制台** ：</span><span class="sxs-lookup"><span data-stu-id="d59d6-140">Navigate back to the **Console** using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="d59d6-141">单击 " **控制台** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d59d6-141">Click the **Console** tab.</span></span>  
    *   <span data-ttu-id="d59d6-142">按 `Control` + `[` \ (Windows \ ) 或 `Command` + `[` \ (macOS \ ) 直到控制台面板处于焦点。</span><span class="sxs-lookup"><span data-stu-id="d59d6-142">Press `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) until the Console panel is in focus.</span></span>  
    *   <span data-ttu-id="d59d6-143">[打开 "命令" 菜单][DevToolsCommandMenu]，开始键入 `Console` ，选择 " **显示控制台面板** " 命令，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-143">[Open the Command Menu][DevToolsCommandMenu], start typing `Console`, select the **Show Console Panel** command, and then press `Enter`.</span></span>  
    
1.  <span data-ttu-id="d59d6-144">单击演示中的 " **日志警告** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="d59d6-144">Click the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="d59d6-145">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d59d6-145">gets logged to the Console.</span></span>  <span data-ttu-id="d59d6-146">此类消息的格式是警告。</span><span class="sxs-lookup"><span data-stu-id="d59d6-146">Messages formatted like this are warnings.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="控制台中的消息" lightbox="../media/console-log-warning.msft.png":::
       <span data-ttu-id="d59d6-148">单击 "**日志警告**" 后的**控制台**</span><span class="sxs-lookup"><span data-stu-id="d59d6-148">The **Console** after you click **Log Warning**</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="d59d6-149">如果想要查看导致邮件以特定方式记录的代码，请单击脚本 \ (，例如 `log.js:12` \ ) 查看导致邮件格式的代码。</span><span class="sxs-lookup"><span data-stu-id="d59d6-149">If you want to see the code that caused a message to get logged a certain way, click on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="d59d6-150">单击 " **展开** " (![ 展开 ][ImageExpandIcon] "在" 前面的 \ ) 图标 `Abandon Hope All Ye Who Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-150">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="d59d6-151">DevTools 显示调用的 [堆栈跟踪][WikiStackTrace] 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-151">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="控制台中的消息" lightbox="../media/console-log-warning-expanded.msft.png":::
       <span data-ttu-id="d59d6-153">堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="d59d6-153">A stack trace</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="d59d6-154">堆栈跟踪告诉你调用了名为的函数 `logWarning` ，而该函数又称为一个名为的函数 `quoteDante` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-154">The stack trace is telling you that a function named `logWarning` was called, which in turn called a function named `quoteDante`.</span></span>  <span data-ttu-id="d59d6-155">换句话说，首先发生的调用位于堆栈跟踪的底部。</span><span class="sxs-lookup"><span data-stu-id="d59d6-155">In other words, the call that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="d59d6-156">你可以随时通过调用来记录堆栈跟踪 `console.trace()` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-156">You may log stack traces at any time by calling `console.trace()`.</span></span>  

1.  <span data-ttu-id="d59d6-157">单击 " **日志错误**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-157">Click **Log Error**.</span></span>  <span data-ttu-id="d59d6-158">已记录以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="d59d6-158">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="控制台中的消息" lightbox="../media/console-log-error.msft.png":::
       <span data-ttu-id="d59d6-160">一条错误消息</span><span class="sxs-lookup"><span data-stu-id="d59d6-160">An error message</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-161">单击 " **日志表**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-161">Click **Log Table**.</span></span>  <span data-ttu-id="d59d6-162">将有关著名音乐家的表格记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d59d6-162">A table about famous artists gets logged to the Console.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="d59d6-163">`birthday`列仅填充一行。</span><span class="sxs-lookup"><span data-stu-id="d59d6-163">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="d59d6-164">查看代码以确定该代码的原因。</span><span class="sxs-lookup"><span data-stu-id="d59d6-164">Review the code to determine why that is.</span></span>
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="控制台中的消息" lightbox="../media/console-log-table.msft.png":::
       <span data-ttu-id="d59d6-166">**控制台**中的表</span><span class="sxs-lookup"><span data-stu-id="d59d6-166">A table in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-167">单击 " **日志组**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-167">Click **Log Group**.</span></span>  <span data-ttu-id="d59d6-168">4个著名的犯罪 turtles 的名称在标签下分组 `Adolescent Irradiated Espionage Tortoises` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-168">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="控制台中的消息" lightbox="../media/console-log-group.msft.png":::
       <span data-ttu-id="d59d6-170">**控制台**中的一组消息</span><span class="sxs-lookup"><span data-stu-id="d59d6-170">A group of messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-171">单击 " **日志自定义**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-171">Click **Log Custom**.</span></span>  <span data-ttu-id="d59d6-172">带有红色边框和蓝色背景的消息将记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d59d6-172">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="控制台中的消息" lightbox="../media/console-log-custom.msft.png":::
       <span data-ttu-id="d59d6-174">在**控制台**中自定义格式的邮件</span><span class="sxs-lookup"><span data-stu-id="d59d6-174">A message with custom formatting in the **Console**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="d59d6-175">此处的主要概念是，当你希望从 JavaScript 将消息记录到控制台时，请使用其中一种 `console` 方法。</span><span class="sxs-lookup"><span data-stu-id="d59d6-175">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="d59d6-176">每种方法设置邮件的格式都不同。</span><span class="sxs-lookup"><span data-stu-id="d59d6-176">Each method formats messages differently.</span></span>  

<span data-ttu-id="d59d6-177">此部分中介绍的方法甚至更多。</span><span class="sxs-lookup"><span data-stu-id="d59d6-177">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="d59d6-178">本教程介绍如何浏览方法的其余部分。</span><span class="sxs-lookup"><span data-stu-id="d59d6-178">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <span data-ttu-id="d59d6-179">查看浏览器记录的消息</span><span class="sxs-lookup"><span data-stu-id="d59d6-179">View messages logged by the browser</span></span>   

<span data-ttu-id="d59d6-180">浏览器也将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d59d6-180">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="d59d6-181">当页面出现问题时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d59d6-181">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="d59d6-182">单击 " **原因 404**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-182">Click **Cause 404**.</span></span>  <span data-ttu-id="d59d6-183">浏览器记录网络错误的 HTTP 状态代码， `404` 因为该页的 JavaScript 尝试提取不存在的文件。</span><span class="sxs-lookup"><span data-stu-id="d59d6-183">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="控制台中的消息" lightbox="../media/console-cause-404.msft.png":::
       <span data-ttu-id="d59d6-185">`404`**控制台**中的错误</span><span class="sxs-lookup"><span data-stu-id="d59d6-185">A `404` error in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-186">单击 " **导致错误**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-186">Click **Cause Error**.</span></span>  <span data-ttu-id="d59d6-187">`TypeError`由于 JavaScript 尝试更新不存在的 DOM 节点，因此浏览器将记录未捕获。</span><span class="sxs-lookup"><span data-stu-id="d59d6-187">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="控制台中的消息" lightbox="../media/console-cause-error.msft.png":::
       <span data-ttu-id="d59d6-189">A `TypeError` 在**控制台**中</span><span class="sxs-lookup"><span data-stu-id="d59d6-189">A `TypeError` in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-190">单击 " **日志级别** " 下拉列表，并启用 " **详细** " 选项（如果已禁用）。</span><span class="sxs-lookup"><span data-stu-id="d59d6-190">Click the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="d59d6-191">在下一节中了解有关筛选的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d59d6-191">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="d59d6-192">您需要执行此操作，以确保您记录的下一条消息是可见的。</span><span class="sxs-lookup"><span data-stu-id="d59d6-192">You need to do this to make sure that the next message you log is visible.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="d59d6-193">如果 "默认级别" 下拉列表处于禁用状态，您可能需要关闭 **控制台** 边栏。</span><span class="sxs-lookup"><span data-stu-id="d59d6-193">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span></span>  <span data-ttu-id="d59d6-194">有关 **控制台** 边栏的详细信息，请按以下消息源进行筛选。</span><span class="sxs-lookup"><span data-stu-id="d59d6-194">Filter by Message Source below for more information about the **Console** Sidebar.</span></span>
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="控制台中的消息" lightbox="../media/console-cause-error-log-levels.msft.png":::
       <span data-ttu-id="d59d6-196">启用详细日志级别</span><span class="sxs-lookup"><span data-stu-id="d59d6-196">Enabling the Verbose log level</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-197">单击 " **导致冲突**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-197">Click **Cause Violation**.</span></span>  <span data-ttu-id="d59d6-198">该页面将在几秒钟后停止响应，然后浏览器将消息记录 `[Violation] 'click' handler took 3000ms` 到控制台。</span><span class="sxs-lookup"><span data-stu-id="d59d6-198">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="d59d6-199">确切持续时间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="d59d6-199">The exact duration may vary.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="控制台中的消息" lightbox="../media/console-cause-violation.msft.png":::
       <span data-ttu-id="d59d6-201">**控制台**中的冲突</span><span class="sxs-lookup"><span data-stu-id="d59d6-201">A violation in the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="d59d6-202">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="d59d6-202">Filter messages</span></span>   

<span data-ttu-id="d59d6-203">在某些页面上，你会看到该控制台会使消息淹没。</span><span class="sxs-lookup"><span data-stu-id="d59d6-203">On some pages you see the Console get flooded with messages.</span></span>  <span data-ttu-id="d59d6-204">DevTools 提供了多种不同的方法来筛选出与手边的任务无关的邮件。</span><span class="sxs-lookup"><span data-stu-id="d59d6-204">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <span data-ttu-id="d59d6-205">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="d59d6-205">Filter by log level</span></span>   

<span data-ttu-id="d59d6-206">每个 `console` 方法都分配了一个严重性级别： `Verbose` 、、 `Info` `Warning` 或 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-206">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="d59d6-207">例如， `console.log()` 是一种 `Info` 级别的消息，而 `console.error()` 是一种 `Error` 级别的消息。</span><span class="sxs-lookup"><span data-stu-id="d59d6-207">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="d59d6-208">单击 " **日志级别** " 下拉列表并禁用 **错误**。</span><span class="sxs-lookup"><span data-stu-id="d59d6-208">Click the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="d59d6-209">如果该级别旁边不再有选中标记，则该级别将被禁用。</span><span class="sxs-lookup"><span data-stu-id="d59d6-209">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="d59d6-210">`Error`级别消息消失。</span><span class="sxs-lookup"><span data-stu-id="d59d6-210">The `Error`-level messages disappear.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="控制台中的消息" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       <span data-ttu-id="d59d6-212">在**控制台**中禁用错误级别消息</span><span class="sxs-lookup"><span data-stu-id="d59d6-212">Disabling Error-level messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-213">再次单击 " **日志级别** " 下拉列表，然后重新启用 **错误**。</span><span class="sxs-lookup"><span data-stu-id="d59d6-213">Click the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="d59d6-214">`Error`级邮件再次出现。</span><span class="sxs-lookup"><span data-stu-id="d59d6-214">The `Error`-level messages reappear.</span></span>  

### <span data-ttu-id="d59d6-215">按文本进行筛选</span><span class="sxs-lookup"><span data-stu-id="d59d6-215">Filter by text</span></span>   

<span data-ttu-id="d59d6-216">如果只希望查看包含确切字符串的邮件，请将该字符串键入到 " **筛选器** " 文本框中。</span><span class="sxs-lookup"><span data-stu-id="d59d6-216">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="d59d6-217">在 `Dave` " **筛选器** " 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="d59d6-217">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="d59d6-218">不包含该字符串的所有消息 `Dave` 均被隐藏。</span><span class="sxs-lookup"><span data-stu-id="d59d6-218">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="d59d6-219">您可能还会看到 `Adolescent Irradiated Espionage Tortoises` 标签。</span><span class="sxs-lookup"><span data-stu-id="d59d6-219">You might also see the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="d59d6-220">这是一个 bug。</span><span class="sxs-lookup"><span data-stu-id="d59d6-220">That is a bug.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="控制台中的消息" lightbox="../media/console-all-messages-text-filter.msft.png":::
       <span data-ttu-id="d59d6-222">筛选出不包含的任何邮件</span><span class="sxs-lookup"><span data-stu-id="d59d6-222">Filtering out any message that does not include</span></span> `Dave`  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-223">`Dave`从 "**筛选器**" 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="d59d6-223">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="d59d6-224">所有邮件再次出现。</span><span class="sxs-lookup"><span data-stu-id="d59d6-224">All the messages reappear.</span></span>  

### <span data-ttu-id="d59d6-225">按正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="d59d6-225">Filter by regular expression</span></span>   

<span data-ttu-id="d59d6-226">当你想要显示包含文本模式的所有消息（而不是特定字符串）时，请使用 [正则表达式][MDNRegularExpressions]。</span><span class="sxs-lookup"><span data-stu-id="d59d6-226">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="d59d6-227">在 `/^[AH]/` " **筛选器** " 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="d59d6-227">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="d59d6-228">在 [RegExr][|::ref1::|Main] 中键入此模式，获取对其执行操作的说明。</span><span class="sxs-lookup"><span data-stu-id="d59d6-228">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="控制台中的消息" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       <span data-ttu-id="d59d6-230">筛选出与模式不匹配的任何邮件</span><span class="sxs-lookup"><span data-stu-id="d59d6-230">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-231">`/^[AH]/`从 "**筛选器**" 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="d59d6-231">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="d59d6-232">所有邮件都将再次显示。</span><span class="sxs-lookup"><span data-stu-id="d59d6-232">All messages are visible again.</span></span>  

### <span data-ttu-id="d59d6-233">按消息源筛选</span><span class="sxs-lookup"><span data-stu-id="d59d6-233">Filter by message source</span></span>   

<span data-ttu-id="d59d6-234">如果只希望查看来自特定 URL 的邮件，请使用 **边栏**。</span><span class="sxs-lookup"><span data-stu-id="d59d6-234">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="d59d6-235">单击 " **显示控制台边栏** \ (![ 显示控制台边栏 ][ImageShowConsoleSidebarIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="d59d6-235">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\).</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="控制台中的消息" lightbox="../media/console-sidebar-all-messages.msft.png":::
       <span data-ttu-id="d59d6-237">边栏</span><span class="sxs-lookup"><span data-stu-id="d59d6-237">The Sidebar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-238">单击邮件数旁边的 " **展开** \ (![ 展开 ][ImageExpandIcon] \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="d59d6-238">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon next to the number of messages.</span></span>  <span data-ttu-id="d59d6-239">在下图中，邮件数显示为 **13 条消息**。</span><span class="sxs-lookup"><span data-stu-id="d59d6-239">In the following figure, the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="d59d6-240">**边栏**显示导致记录消息的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="d59d6-240">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="d59d6-241">例如， `log.js` 导致了11条消息。</span><span class="sxs-lookup"><span data-stu-id="d59d6-241">For example, `log.js` caused 11 messages.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="控制台中的消息" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       <span data-ttu-id="d59d6-243">查看边栏中的邮件源</span><span class="sxs-lookup"><span data-stu-id="d59d6-243">Viewing the source of messages in the Sidebar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="d59d6-244">按用户消息筛选</span><span class="sxs-lookup"><span data-stu-id="d59d6-244">Filter by user messages</span></span>   

<span data-ttu-id="d59d6-245">较早版本中，当您单击 " **日志信息**" 时，将调用一个脚本，以便 `console.log('Hello, Console!')` 将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d59d6-245">Earlier, when you clicked **Log Info**, a script called `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="d59d6-246">从属于此类的 JavaScript 记录的消息称为 " **用户消息**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-246">Messages logged from JavaScript like this are called **user messages**.</span></span>  <span data-ttu-id="d59d6-247">相比之下，当你单击 " **原因 404**" 时，浏览器记录了一个 `Error` 级别消息，指出找不到所请求的资源。</span><span class="sxs-lookup"><span data-stu-id="d59d6-247">In contrast, when you clicked **Cause 404**, the browser logged an `Error`-level message stating that the requested resource could not be found.</span></span>  <span data-ttu-id="d59d6-248">类似消息被视为 **浏览器消息**。</span><span class="sxs-lookup"><span data-stu-id="d59d6-248">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="d59d6-249">使用 **边栏** 筛选出浏览器消息，并仅显示用户消息。</span><span class="sxs-lookup"><span data-stu-id="d59d6-249">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="d59d6-250">单击 " **9 个用户消息**"。</span><span class="sxs-lookup"><span data-stu-id="d59d6-250">Click **9 User Messages**.</span></span>  <span data-ttu-id="d59d6-251">浏览器消息处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="d59d6-251">The browser messages are hidden.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="控制台中的消息" lightbox="../media/console-sidebar-user-messages.msft.png":::
       <span data-ttu-id="d59d6-253">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="d59d6-253">Filtering out browser messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d59d6-254">单击 **13 条消息** ，再次显示所有消息。</span><span class="sxs-lookup"><span data-stu-id="d59d6-254">Click **13 Messages** to show all messages again.</span></span>  

## <span data-ttu-id="d59d6-255">将控制台与任何其他面板一起使用</span><span class="sxs-lookup"><span data-stu-id="d59d6-255">Use the Console alongside any other panel</span></span>   

<span data-ttu-id="d59d6-256">如果正在编辑样式，但需要快速检查控制台日志是否有什么内容？</span><span class="sxs-lookup"><span data-stu-id="d59d6-256">What if you are editing styles, but you need to quickly check the Console log for something?</span></span> <span data-ttu-id="d59d6-257">使用抽屉。</span><span class="sxs-lookup"><span data-stu-id="d59d6-257">Use the Drawer.</span></span>  

1.  <span data-ttu-id="d59d6-258">单击 " **元素** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d59d6-258">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="d59d6-259">按 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="d59d6-259">Press `Escape`.</span></span>  <span data-ttu-id="d59d6-260">将打开 **抽屉** 的 "控制台" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d59d6-260">The Console tab of the **Drawer** opens.</span></span>  <span data-ttu-id="d59d6-261">它具有您在整个教程中使用的控制台面板的所有功能。</span><span class="sxs-lookup"><span data-stu-id="d59d6-261">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="控制台中的消息" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         <span data-ttu-id="d59d6-263">**抽屉**中的 "**控制台**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="d59d6-263">The **Console** tab in the **Drawer**</span></span>  
    :::image-end:::  
    
<!--## Next steps  -->

<!--
*   See [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   See [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   See [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

<!--
 


-->  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \ (Chromium \ ) 开发工具 |Microsoft 文档"  
[DevToolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 位置 |Microsoft 文档"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考 |Microsoft 文档"  
[DevToolsConsoleReference]: ./reference.md "控制台参考 |Microsoft 文档"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "记录消息入门 |故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "堆栈跟踪-维基百科"  


> [!NOTE]
> <span data-ttu-id="d59d6-273">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d59d6-273">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d59d6-274">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="d59d6-274">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="d59d6-276">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d59d6-276">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
