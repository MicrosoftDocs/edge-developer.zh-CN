---
title: 在控制台中记录消息入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: c2cf868e6daaf9dd45c7acc90a71c2154261b9c3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982616"
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





# <span data-ttu-id="d6f63-103">在控制台中记录消息入门</span><span class="sxs-lookup"><span data-stu-id="d6f63-103">Get Started With Logging Messages In The Console</span></span>   



<span data-ttu-id="d6f63-104">此交互式教程介绍如何在 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 控制台中记录和筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="d6f63-104">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="控制台中的消息" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   <span data-ttu-id="d6f63-106">**控制台**中的消息</span><span class="sxs-lookup"><span data-stu-id="d6f63-106">Messages in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="d6f63-107">本教程旨在按顺序完成。</span><span class="sxs-lookup"><span data-stu-id="d6f63-107">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="d6f63-108">它假定你了解 web 开发的基础知识，例如如何使用 JavaScript 向页面添加交互。</span><span class="sxs-lookup"><span data-stu-id="d6f63-108">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <span data-ttu-id="d6f63-109">设置演示和 DevTools</span><span class="sxs-lookup"><span data-stu-id="d6f63-109">Set up the demo and DevTools</span></span>   

<span data-ttu-id="d6f63-110">本教程旨在使您能够打开演示并自行尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="d6f63-110">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="d6f63-111">当您进行物理跟踪时，更有可能会在以后记忆工作流。</span><span class="sxs-lookup"><span data-stu-id="d6f63-111">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="d6f63-112">保留 `Control` \ (Windows \ ) 或 `Command` \ (macOS \ ) ，然后单击 " **控制台日志示例** " 以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="d6f63-112">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="d6f63-113">控制台日志示例</span><span class="sxs-lookup"><span data-stu-id="d6f63-113">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  <span data-ttu-id="d6f63-114">聚焦演示，然后按 `Control` + `Shift` + `J` (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="d6f63-114">Focus the demo and then press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="d6f63-115">默认情况下，DevTools 将在演示右侧打开。</span><span class="sxs-lookup"><span data-stu-id="d6f63-115">By default DevTools opens to the right of the demo.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="DevTools 将在演示右侧打开" lightbox="../media/console-example-devtools-right-console.msft.png":::
             <span data-ttu-id="d6f63-117">DevTools 将在演示右侧打开</span><span class="sxs-lookup"><span data-stu-id="d6f63-117">DevTools opens to the right of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="d6f63-118">[将 DevTools 停靠在窗口底部][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="d6f63-118">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="DevTools 停靠在演示底部" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             <span data-ttu-id="d6f63-120">DevTools 停靠在演示底部</span><span class="sxs-lookup"><span data-stu-id="d6f63-120">DevTools docked to the bottom of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="d6f63-121">[将 DevTools 取消停靠到一个单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="d6f63-121">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             <span data-ttu-id="d6f63-123">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="d6f63-123">Browser in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="d6f63-124">[将 DevTools 取消停靠到一个单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="d6f63-124">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="DevTools 在单独窗口中取消停靠" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             <span data-ttu-id="d6f63-126">DevTools 在单独窗口中取消停靠</span><span class="sxs-lookup"><span data-stu-id="d6f63-126">DevTools undocked in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="d6f63-127">查看从 JavaScript 记录的消息</span><span class="sxs-lookup"><span data-stu-id="d6f63-127">View messages logged from JavaScript</span></span>   

<span data-ttu-id="d6f63-128">您在控制台中看到的大多数消息来自于编写页面 JavaScript 的 web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="d6f63-128">Most messages that you see in the Console come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="d6f63-129">本部分的目标是介绍你可能会在控制台中看到的不同消息类型，并介绍如何从你自己的 JavaScript 中自己记录每种消息类型。</span><span class="sxs-lookup"><span data-stu-id="d6f63-129">The goal of this section is to introduce you to the different message types that you are likely to see in the Console, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="d6f63-130">单击演示中的 " **日志信息** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="d6f63-130">Click the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="d6f63-131">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f63-131">gets logged to the Console.</span></span>
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="单击 "日志信息" 后的控制台" lightbox="../media/console-log-info.msft.png":::
       <span data-ttu-id="d6f63-133">单击 "**日志信息**" 后的**控制台**</span><span class="sxs-lookup"><span data-stu-id="d6f63-133">The **Console** after clicking **Log Info**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-134">`Hello, Console!`在控制台中的邮件旁边，单击 " **log.js： 2**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-134">Next to the `Hello, Console!` message in the Console click **log.js:2**.</span></span>  <span data-ttu-id="d6f63-135">"源" 面板将打开并突出显示导致消息登录到控制台的代码行。</span><span class="sxs-lookup"><span data-stu-id="d6f63-135">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="d6f63-136">当页面的 JavaScript 运行时，将记录此消息 `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-136">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="单击 "log.js" 后，DevTools 将打开 "源" 面板：2" lightbox="../media/console-sources-logjs.msft.png":::
       <span data-ttu-id="d6f63-138">单击后，DevTools 将打开 " **源** " 面板</span><span class="sxs-lookup"><span data-stu-id="d6f63-138">DevTools opens the **Sources** panel after you click</span></span> `log.js:2`  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-139">使用以下任一工作流向后导航到 **控制台** ：</span><span class="sxs-lookup"><span data-stu-id="d6f63-139">Navigate back to the **Console** using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="d6f63-140">单击 " **控制台** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d6f63-140">Click the **Console** tab.</span></span>  
    *   <span data-ttu-id="d6f63-141">按 `Control` + `[` \ (Windows \ ) 或 `Command` + `[` \ (macOS \ ) 直到控制台面板处于焦点。</span><span class="sxs-lookup"><span data-stu-id="d6f63-141">Press `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) until the Console panel is in focus.</span></span>  
    *   <span data-ttu-id="d6f63-142">[打开 "命令" 菜单][DevToolsCommandMenu]，开始键入 `Console` ，选择 " **显示控制台面板** " 命令，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-142">[Open the Command Menu][DevToolsCommandMenu], start typing `Console`, select the **Show Console Panel** command, and then press `Enter`.</span></span>  
    
1.  <span data-ttu-id="d6f63-143">单击演示中的 " **日志警告** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="d6f63-143">Click the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="d6f63-144">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f63-144">gets logged to the Console.</span></span>  <span data-ttu-id="d6f63-145">此类消息的格式是警告。</span><span class="sxs-lookup"><span data-stu-id="d6f63-145">Messages formatted like this are warnings.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="单击 "日志警告" 后的控制台" lightbox="../media/console-log-warning.msft.png":::
       <span data-ttu-id="d6f63-147">单击 "**日志警告**" 后的**控制台**</span><span class="sxs-lookup"><span data-stu-id="d6f63-147">The **Console** after you click **Log Warning**</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="d6f63-148">如果想要查看导致邮件以特定方式记录的代码，请单击脚本 \ (，例如 `log.js:12` \ ) 查看导致邮件格式的代码。</span><span class="sxs-lookup"><span data-stu-id="d6f63-148">If you want to see the code that caused a message to get logged a certain way, click on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="d6f63-149">单击 " **展开** " (![ 展开 ][ImageExpandIcon] "在" 前面的 \ ) 图标 `Abandon Hope All Ye Who Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-149">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="d6f63-150">DevTools 显示调用的 [堆栈跟踪][WikiStackTrace] 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-150">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="堆栈跟踪" lightbox="../media/console-log-warning-expanded.msft.png":::
       <span data-ttu-id="d6f63-152">堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="d6f63-152">A stack trace</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="d6f63-153">堆栈跟踪告诉你调用了名为的函数 `logWarning` ，而该函数又称为一个名为的函数 `quoteDante` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-153">The stack trace is telling you that a function named `logWarning` was called, which in turn called a function named `quoteDante`.</span></span>  <span data-ttu-id="d6f63-154">换句话说，首先发生的调用位于堆栈跟踪的底部。</span><span class="sxs-lookup"><span data-stu-id="d6f63-154">In other words, the call that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="d6f63-155">你可以随时通过调用来记录堆栈跟踪 `console.trace()` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-155">You may log stack traces at any time by calling `console.trace()`.</span></span>  

1.  <span data-ttu-id="d6f63-156">单击 " **日志错误**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-156">Click **Log Error**.</span></span>  <span data-ttu-id="d6f63-157">已记录以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="d6f63-157">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="一条错误消息" lightbox="../media/console-log-error.msft.png":::
       <span data-ttu-id="d6f63-159">一条错误消息</span><span class="sxs-lookup"><span data-stu-id="d6f63-159">An error message</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-160">单击 " **日志表**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-160">Click **Log Table**.</span></span>  <span data-ttu-id="d6f63-161">将有关著名音乐家的表格记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f63-161">A table about famous artists gets logged to the Console.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="d6f63-162">`birthday`列仅填充一行。</span><span class="sxs-lookup"><span data-stu-id="d6f63-162">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="d6f63-163">查看代码以确定该代码的原因。</span><span class="sxs-lookup"><span data-stu-id="d6f63-163">Review the code to determine why that is.</span></span>
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="控制台中的表" lightbox="../media/console-log-table.msft.png":::
       <span data-ttu-id="d6f63-165">**控制台**中的表</span><span class="sxs-lookup"><span data-stu-id="d6f63-165">A table in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-166">单击 " **日志组**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-166">Click **Log Group**.</span></span>  <span data-ttu-id="d6f63-167">4个著名的犯罪 turtles 的名称在标签下分组 `Adolescent Irradiated Espionage Tortoises` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-167">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="控制台中的一组消息" lightbox="../media/console-log-group.msft.png":::
       <span data-ttu-id="d6f63-169">**控制台**中的一组消息</span><span class="sxs-lookup"><span data-stu-id="d6f63-169">A group of messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-170">单击 " **日志自定义**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-170">Click **Log Custom**.</span></span>  <span data-ttu-id="d6f63-171">带有红色边框和蓝色背景的消息将记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f63-171">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="在控制台中自定义格式的邮件" lightbox="../media/console-log-custom.msft.png":::
       <span data-ttu-id="d6f63-173">在**控制台**中自定义格式的邮件</span><span class="sxs-lookup"><span data-stu-id="d6f63-173">A message with custom formatting in the **Console**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="d6f63-174">此处的主要概念是，当你希望从 JavaScript 将消息记录到控制台时，请使用其中一种 `console` 方法。</span><span class="sxs-lookup"><span data-stu-id="d6f63-174">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="d6f63-175">每种方法设置邮件的格式都不同。</span><span class="sxs-lookup"><span data-stu-id="d6f63-175">Each method formats messages differently.</span></span>  

<span data-ttu-id="d6f63-176">此部分中介绍的方法甚至更多。</span><span class="sxs-lookup"><span data-stu-id="d6f63-176">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="d6f63-177">本教程介绍如何浏览方法的其余部分。</span><span class="sxs-lookup"><span data-stu-id="d6f63-177">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <span data-ttu-id="d6f63-178">查看浏览器记录的消息</span><span class="sxs-lookup"><span data-stu-id="d6f63-178">View messages logged by the browser</span></span>   

<span data-ttu-id="d6f63-179">浏览器也将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f63-179">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="d6f63-180">当页面出现问题时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d6f63-180">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="d6f63-181">单击 " **原因 404**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-181">Click **Cause 404**.</span></span>  <span data-ttu-id="d6f63-182">浏览器记录网络错误的 HTTP 状态代码， `404` 因为该页的 JavaScript 尝试提取不存在的文件。</span><span class="sxs-lookup"><span data-stu-id="d6f63-182">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="控制台中的404错误" lightbox="../media/console-cause-404.msft.png":::
       <span data-ttu-id="d6f63-184">`404`**控制台**中的错误</span><span class="sxs-lookup"><span data-stu-id="d6f63-184">A `404` error in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-185">单击 " **导致错误**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-185">Click **Cause Error**.</span></span>  <span data-ttu-id="d6f63-186">`TypeError`由于 JavaScript 尝试更新不存在的 DOM 节点，因此浏览器将记录未捕获。</span><span class="sxs-lookup"><span data-stu-id="d6f63-186">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="控制台中的 TypeError" lightbox="../media/console-cause-error.msft.png":::
       <span data-ttu-id="d6f63-188">A `TypeError` 在**控制台**中</span><span class="sxs-lookup"><span data-stu-id="d6f63-188">A `TypeError` in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-189">单击 " **日志级别** " 下拉列表，并启用 " **详细** " 选项（如果已禁用）。</span><span class="sxs-lookup"><span data-stu-id="d6f63-189">Click the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="d6f63-190">在下一节中了解有关筛选的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d6f63-190">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="d6f63-191">您需要执行此操作，以确保您记录的下一条消息是可见的。</span><span class="sxs-lookup"><span data-stu-id="d6f63-191">You need to do this to make sure that the next message you log is visible.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="d6f63-192">如果 "默认级别" 下拉列表处于禁用状态，您可能需要关闭 **控制台** 边栏。</span><span class="sxs-lookup"><span data-stu-id="d6f63-192">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span></span>  <span data-ttu-id="d6f63-193">有关 **控制台** 边栏的详细信息，请按以下消息源进行筛选。</span><span class="sxs-lookup"><span data-stu-id="d6f63-193">Filter by Message Source below for more information about the **Console** Sidebar.</span></span>
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="启用详细日志级别" lightbox="../media/console-cause-error-log-levels.msft.png":::
       <span data-ttu-id="d6f63-195">启用详细日志级别</span><span class="sxs-lookup"><span data-stu-id="d6f63-195">Enabling the Verbose log level</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-196">单击 " **导致冲突**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-196">Click **Cause Violation**.</span></span>  <span data-ttu-id="d6f63-197">该页面将在几秒钟后停止响应，然后浏览器将消息记录 `[Violation] 'click' handler took 3000ms` 到控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f63-197">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="d6f63-198">确切持续时间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="d6f63-198">The exact duration may vary.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="控制台中的冲突" lightbox="../media/console-cause-violation.msft.png":::
       <span data-ttu-id="d6f63-200">**控制台**中的冲突</span><span class="sxs-lookup"><span data-stu-id="d6f63-200">A violation in the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="d6f63-201">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="d6f63-201">Filter messages</span></span>   

<span data-ttu-id="d6f63-202">在某些页面上，你会看到该控制台会使消息淹没。</span><span class="sxs-lookup"><span data-stu-id="d6f63-202">On some pages you see the Console get flooded with messages.</span></span>  <span data-ttu-id="d6f63-203">DevTools 提供了多种不同的方法来筛选出与手边的任务无关的邮件。</span><span class="sxs-lookup"><span data-stu-id="d6f63-203">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <span data-ttu-id="d6f63-204">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="d6f63-204">Filter by log level</span></span>   

<span data-ttu-id="d6f63-205">每个 `console` 方法都分配了一个严重性级别： `Verbose` 、、 `Info` `Warning` 或 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-205">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="d6f63-206">例如， `console.log()` 是一种 `Info` 级别的消息，而 `console.error()` 是一种 `Error` 级别的消息。</span><span class="sxs-lookup"><span data-stu-id="d6f63-206">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="d6f63-207">单击 " **日志级别** " 下拉列表并禁用 **错误**。</span><span class="sxs-lookup"><span data-stu-id="d6f63-207">Click the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="d6f63-208">如果该级别旁边不再有选中标记，则该级别将被禁用。</span><span class="sxs-lookup"><span data-stu-id="d6f63-208">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="d6f63-209">`Error`级别消息消失。</span><span class="sxs-lookup"><span data-stu-id="d6f63-209">The `Error`-level messages disappear.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="在控制台中禁用错误级别消息" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       <span data-ttu-id="d6f63-211">在**控制台**中禁用错误级别消息</span><span class="sxs-lookup"><span data-stu-id="d6f63-211">Disabling Error-level messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-212">再次单击 " **日志级别** " 下拉列表，然后重新启用 **错误**。</span><span class="sxs-lookup"><span data-stu-id="d6f63-212">Click the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="d6f63-213">`Error`级邮件再次出现。</span><span class="sxs-lookup"><span data-stu-id="d6f63-213">The `Error`-level messages reappear.</span></span>  

### <span data-ttu-id="d6f63-214">按文本进行筛选</span><span class="sxs-lookup"><span data-stu-id="d6f63-214">Filter by text</span></span>   

<span data-ttu-id="d6f63-215">如果只希望查看包含确切字符串的邮件，请将该字符串键入到 " **筛选器** " 文本框中。</span><span class="sxs-lookup"><span data-stu-id="d6f63-215">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="d6f63-216">在 `Dave` " **筛选器** " 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="d6f63-216">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="d6f63-217">不包含该字符串的所有消息 `Dave` 均被隐藏。</span><span class="sxs-lookup"><span data-stu-id="d6f63-217">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="d6f63-218">您可能还会看到 `Adolescent Irradiated Espionage Tortoises` 标签。</span><span class="sxs-lookup"><span data-stu-id="d6f63-218">You might also see the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="d6f63-219">这是一个 bug。</span><span class="sxs-lookup"><span data-stu-id="d6f63-219">That is a bug.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="筛选出不包含 Dave 的任何消息" lightbox="../media/console-all-messages-text-filter.msft.png":::
       <span data-ttu-id="d6f63-221">筛选出不包含的任何邮件</span><span class="sxs-lookup"><span data-stu-id="d6f63-221">Filtering out any message that does not include</span></span> `Dave`  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-222">`Dave`从 "**筛选器**" 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="d6f63-222">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="d6f63-223">所有邮件再次出现。</span><span class="sxs-lookup"><span data-stu-id="d6f63-223">All the messages reappear.</span></span>  

### <span data-ttu-id="d6f63-224">按正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="d6f63-224">Filter by regular expression</span></span>   

<span data-ttu-id="d6f63-225">当你想要显示包含文本模式的所有消息（而不是特定字符串）时，请使用 [正则表达式][MDNRegularExpressions]。</span><span class="sxs-lookup"><span data-stu-id="d6f63-225">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="d6f63-226">在 `/^[AH]/` " **筛选器** " 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="d6f63-226">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="d6f63-227">在 [RegExr][|::ref1::|Main] 中键入此模式，获取对其执行操作的说明。</span><span class="sxs-lookup"><span data-stu-id="d6f63-227">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="筛选出与模式不匹配的任何消息" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       <span data-ttu-id="d6f63-229">筛选出与模式不匹配的任何邮件</span><span class="sxs-lookup"><span data-stu-id="d6f63-229">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-230">`/^[AH]/`从 "**筛选器**" 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="d6f63-230">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="d6f63-231">所有邮件都将再次显示。</span><span class="sxs-lookup"><span data-stu-id="d6f63-231">All messages are visible again.</span></span>  

### <span data-ttu-id="d6f63-232">按消息源筛选</span><span class="sxs-lookup"><span data-stu-id="d6f63-232">Filter by message source</span></span>   

<span data-ttu-id="d6f63-233">如果只希望查看来自特定 URL 的邮件，请使用 **边栏**。</span><span class="sxs-lookup"><span data-stu-id="d6f63-233">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="d6f63-234">单击 " **显示控制台边栏** \ (![ 显示控制台边栏 ][ImageShowConsoleSidebarIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="d6f63-234">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\).</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="边栏" lightbox="../media/console-sidebar-all-messages.msft.png":::
       <span data-ttu-id="d6f63-236">边栏</span><span class="sxs-lookup"><span data-stu-id="d6f63-236">The Sidebar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-237">单击邮件数旁边的 " **展开** \ (![ 展开 ][ImageExpandIcon] \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="d6f63-237">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon next to the number of messages.</span></span>  <span data-ttu-id="d6f63-238">在下图中，邮件数显示为 **13 条消息**。</span><span class="sxs-lookup"><span data-stu-id="d6f63-238">In the following figure, the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="d6f63-239">**边栏**显示导致记录消息的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="d6f63-239">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="d6f63-240">例如， `log.js` 导致了11条消息。</span><span class="sxs-lookup"><span data-stu-id="d6f63-240">For example, `log.js` caused 11 messages.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="查看边栏中的邮件源" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       <span data-ttu-id="d6f63-242">查看边栏中的邮件源</span><span class="sxs-lookup"><span data-stu-id="d6f63-242">Viewing the source of messages in the Sidebar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="d6f63-243">按用户消息筛选</span><span class="sxs-lookup"><span data-stu-id="d6f63-243">Filter by user messages</span></span>   

<span data-ttu-id="d6f63-244">较早版本中，当您单击 " **日志信息**" 时，将调用一个脚本，以便 `console.log('Hello, Console!')` 将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f63-244">Earlier, when you clicked **Log Info**, a script called `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="d6f63-245">从属于此类的 JavaScript 记录的消息称为 " **用户消息**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-245">Messages logged from JavaScript like this are called **user messages**.</span></span>  <span data-ttu-id="d6f63-246">相比之下，当你单击 " **原因 404**" 时，浏览器记录了一个 `Error` 级别消息，指出找不到所请求的资源。</span><span class="sxs-lookup"><span data-stu-id="d6f63-246">In contrast, when you clicked **Cause 404**, the browser logged an `Error`-level message stating that the requested resource could not be found.</span></span>  <span data-ttu-id="d6f63-247">类似消息被视为 **浏览器消息**。</span><span class="sxs-lookup"><span data-stu-id="d6f63-247">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="d6f63-248">使用 **边栏** 筛选出浏览器消息，并仅显示用户消息。</span><span class="sxs-lookup"><span data-stu-id="d6f63-248">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="d6f63-249">单击 " **9 个用户消息**"。</span><span class="sxs-lookup"><span data-stu-id="d6f63-249">Click **9 User Messages**.</span></span>  <span data-ttu-id="d6f63-250">浏览器消息处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="d6f63-250">The browser messages are hidden.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="筛选出浏览器消息" lightbox="../media/console-sidebar-user-messages.msft.png":::
       <span data-ttu-id="d6f63-252">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="d6f63-252">Filtering out browser messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6f63-253">单击 **13 条消息** ，再次显示所有消息。</span><span class="sxs-lookup"><span data-stu-id="d6f63-253">Click **13 Messages** to show all messages again.</span></span>  

## <span data-ttu-id="d6f63-254">将控制台与任何其他面板一起使用</span><span class="sxs-lookup"><span data-stu-id="d6f63-254">Use the Console alongside any other panel</span></span>   

<span data-ttu-id="d6f63-255">如果正在编辑样式，但需要快速检查控制台日志是否有什么内容？</span><span class="sxs-lookup"><span data-stu-id="d6f63-255">What if you are editing styles, but you need to quickly check the Console log for something?</span></span> <span data-ttu-id="d6f63-256">使用抽屉。</span><span class="sxs-lookup"><span data-stu-id="d6f63-256">Use the Drawer.</span></span>  

1.  <span data-ttu-id="d6f63-257">单击 " **元素** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d6f63-257">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="d6f63-258">按 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="d6f63-258">Press `Escape`.</span></span>  <span data-ttu-id="d6f63-259">将打开 **抽屉** 的 "控制台" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d6f63-259">The Console tab of the **Drawer** opens.</span></span>  <span data-ttu-id="d6f63-260">它具有您在整个教程中使用的控制台面板的所有功能。</span><span class="sxs-lookup"><span data-stu-id="d6f63-260">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="抽屉中的 "控制台" 选项卡" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         <span data-ttu-id="d6f63-262">**抽屉**中的 "**控制台**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="d6f63-262">The **Console** tab in the **Drawer**</span></span>  
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
> <span data-ttu-id="d6f63-272">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d6f63-272">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d6f63-273">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="d6f63-273">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="d6f63-275">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d6f63-275">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
