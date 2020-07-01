---
title: 在控制台中记录消息入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 4c930caf60af2b5e276e003378546e147c249548
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843962"
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





# <span data-ttu-id="b142c-103">在控制台中记录消息入门</span><span class="sxs-lookup"><span data-stu-id="b142c-103">Get Started With Logging Messages In The Console</span></span>   



<span data-ttu-id="b142c-104">此交互式教程介绍如何在[Microsoft Edge DevTools][MicrosoftEdgeDevTools]控制台中记录和筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="b142c-104">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

> ##### <span data-ttu-id="b142c-105">图 1</span><span class="sxs-lookup"><span data-stu-id="b142c-105">Figure 1</span></span>  
> <span data-ttu-id="b142c-106">控制台中的消息</span><span class="sxs-lookup"><span data-stu-id="b142c-106">Messages in the Console</span></span>  
> ![控制台中的消息][ImageLogExample]  

<span data-ttu-id="b142c-108">本教程旨在按顺序完成。</span><span class="sxs-lookup"><span data-stu-id="b142c-108">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="b142c-109">它假定你了解 web 开发的基础知识，例如如何使用 JavaScript 向页面添加交互。</span><span class="sxs-lookup"><span data-stu-id="b142c-109">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <span data-ttu-id="b142c-110">设置演示和 DevTools</span><span class="sxs-lookup"><span data-stu-id="b142c-110">Set up the demo and DevTools</span></span>   

<span data-ttu-id="b142c-111">本教程旨在使您能够打开演示并自行尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="b142c-111">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="b142c-112">当您进行物理跟踪时，更有可能会在以后记忆工作流。</span><span class="sxs-lookup"><span data-stu-id="b142c-112">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="b142c-113">保留 `Control` \ （Windows \）或 `Command` \ （macOS \），然后单击 "**控制台日志示例**" 以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="b142c-113">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="b142c-114">控制台日志示例</span><span class="sxs-lookup"><span data-stu-id="b142c-114">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!-- > [!TIP]
    > Move the demo to a separate window.  
    > 
    > > ##### old Figure 2  
    > > The tutorial on the left, and the demo on the right  
    > > ![The tutorial on the left, and the demo on the right][ImageLogSetUp1]  -->
    
1.  <span data-ttu-id="b142c-115">聚焦演示，然后按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="b142c-115">Focus the demo and then press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="b142c-116">默认情况下，DevTools 将在演示右侧打开。</span><span class="sxs-lookup"><span data-stu-id="b142c-116">By default DevTools opens to the right of the demo.</span></span>  
    
    > ##### <span data-ttu-id="b142c-117">图 2</span><span class="sxs-lookup"><span data-stu-id="b142c-117">Figure 2</span></span>  
    > <span data-ttu-id="b142c-118">DevTools 将在演示右侧打开</span><span class="sxs-lookup"><span data-stu-id="b142c-118">DevTools opens to the right of the demo</span></span>  
    > <span data-ttu-id="b142c-119">![DevTools 将在演示右侧打开][ImageDevToolsRight]</span><span class="sxs-lookup"><span data-stu-id="b142c-119">![DevTools opens to the right of the demo][ImageDevToolsRight]</span></span>  
    
    > [!TIP]
    > <span data-ttu-id="b142c-120">[将 DevTools 停靠在窗口底部或将其移到一个单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="b142c-120">[Dock DevTools to the bottom of the window or undock it into a separate window][DevToolsCustomizePlacement].</span></span>  
    
    > ##### <span data-ttu-id="b142c-121">图 3</span><span class="sxs-lookup"><span data-stu-id="b142c-121">Figure 3</span></span>  
    > <span data-ttu-id="b142c-122">DevTools 停靠在演示底部</span><span class="sxs-lookup"><span data-stu-id="b142c-122">DevTools docked to the bottom of the demo</span></span>  
    > <span data-ttu-id="b142c-123">![DevTools 固定在演示底部][ImageDevToolsBottom]</span><span class="sxs-lookup"><span data-stu-id="b142c-123">![DevTools docked to the bottom of the demo][ImageDevToolsBottom]</span></span>  
    
    > ##### <span data-ttu-id="b142c-124">图 4</span><span class="sxs-lookup"><span data-stu-id="b142c-124">Figure 4</span></span>  
    > <span data-ttu-id="b142c-125">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="b142c-125">Browser in a separate window</span></span>  
    > <span data-ttu-id="b142c-126">![浏览器在单独窗口中][ImageDevToolsSeparateBrowse]</span><span class="sxs-lookup"><span data-stu-id="b142c-126">![Browser in a separate window][ImageDevToolsSeparateBrowse]</span></span>  
    
    > ##### <span data-ttu-id="b142c-127">图 5</span><span class="sxs-lookup"><span data-stu-id="b142c-127">Figure 5</span></span>  
    > <span data-ttu-id="b142c-128">DevTools 在单独窗口中取消停靠</span><span class="sxs-lookup"><span data-stu-id="b142c-128">DevTools undocked in a separate window</span></span>  
    > <span data-ttu-id="b142c-129">![DevTools 在单独窗口中取消停靠][ImageDevToolsSeparateDevTools]</span><span class="sxs-lookup"><span data-stu-id="b142c-129">![DevTools undocked in a separate window][ImageDevToolsSeparateDevTools]</span></span>  
    
## <span data-ttu-id="b142c-130">查看从 JavaScript 记录的消息</span><span class="sxs-lookup"><span data-stu-id="b142c-130">View messages logged from JavaScript</span></span>   

<span data-ttu-id="b142c-131">您在控制台中看到的大多数消息来自于编写页面 JavaScript 的 web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="b142c-131">Most messages that you see in the Console come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="b142c-132">本部分的目标是介绍你可能会在控制台中看到的不同消息类型，并介绍如何从你自己的 JavaScript 中自己记录每种消息类型。</span><span class="sxs-lookup"><span data-stu-id="b142c-132">The goal of this section is to introduce you to the different message types that you are likely to see in the Console, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="b142c-133">单击演示中的 "**日志信息**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b142c-133">Click the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="b142c-134">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="b142c-134">gets logged to the Console.</span></span>
    
    > ##### <span data-ttu-id="b142c-135">图 6</span><span class="sxs-lookup"><span data-stu-id="b142c-135">Figure 6</span></span>  
    > <span data-ttu-id="b142c-136">单击 "**日志信息**" 后的控制台</span><span class="sxs-lookup"><span data-stu-id="b142c-136">The Console after clicking **Log Info**</span></span>  
    > <span data-ttu-id="b142c-137">![单击 "日志信息" 后的控制台][ImageLogInfo]</span><span class="sxs-lookup"><span data-stu-id="b142c-137">![The Console after clicking Log Info][ImageLogInfo]</span></span>  
    
1.  <span data-ttu-id="b142c-138">`Hello, Console!`在控制台中的邮件旁边，单击 " **log.js： 2**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-138">Next to the `Hello, Console!` message in the Console click **log.js:2**.</span></span>  <span data-ttu-id="b142c-139">"源" 面板将打开并突出显示导致消息登录到控制台的代码行。</span><span class="sxs-lookup"><span data-stu-id="b142c-139">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="b142c-140">当页面的 JavaScript 运行时，将记录此消息 `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-140">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    > ##### <span data-ttu-id="b142c-141">图 7</span><span class="sxs-lookup"><span data-stu-id="b142c-141">Figure 7</span></span>  
    > <span data-ttu-id="b142c-142">单击 "log.js" 后，DevTools 将打开 "源" 面板 **： 2**</span><span class="sxs-lookup"><span data-stu-id="b142c-142">DevTools opens the Sources panel after you click **log.js:2**</span></span>  
    > <span data-ttu-id="b142c-143">![DevTools 在你单击 "log.js： 2] 后打开" 源 "面板[ImageSourceLog]</span><span class="sxs-lookup"><span data-stu-id="b142c-143">![DevTools opens the Sources panel after you click log.js:2][ImageSourceLog]</span></span>  
    
1.  <span data-ttu-id="b142c-144">使用以下任一工作流向后导航到控制台：</span><span class="sxs-lookup"><span data-stu-id="b142c-144">Navigate back to the Console using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="b142c-145">单击 "**控制台**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b142c-145">Click the **Console** tab.</span></span>  
    *   <span data-ttu-id="b142c-146">按 `Control` + `[` \ （Windows \）或 `Command` + `[` \ （macOS \），直到控制台面板处于焦点。</span><span class="sxs-lookup"><span data-stu-id="b142c-146">Press `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) until the Console panel is in focus.</span></span>  
    *   <span data-ttu-id="b142c-147">[打开 "命令" 菜单][DevToolsCommandMenu]，开始键入 `Console` ，选择 "**显示控制台面板**" 命令，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-147">[Open the Command Menu][DevToolsCommandMenu], start typing `Console`, select the **Show Console Panel** command, and then press `Enter`.</span></span>  
    
1.  <span data-ttu-id="b142c-148">单击演示中的 "**日志警告**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b142c-148">Click the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="b142c-149">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="b142c-149">gets logged to the Console.</span></span>  <span data-ttu-id="b142c-150">此类消息的格式是警告。</span><span class="sxs-lookup"><span data-stu-id="b142c-150">Messages formatted like this are warnings.</span></span>  
    
    > ##### <span data-ttu-id="b142c-151">图 8</span><span class="sxs-lookup"><span data-stu-id="b142c-151">Figure 8</span></span>  
    > <span data-ttu-id="b142c-152">单击 "**日志警告**" 后的控制台</span><span class="sxs-lookup"><span data-stu-id="b142c-152">The Console after clicking **Log Warning**</span></span>  
    > <span data-ttu-id="b142c-153">![单击 "日志警告" 后的控制台][ImageConsoleLogWarning]</span><span class="sxs-lookup"><span data-stu-id="b142c-153">![The Console after clicking Log Warning][ImageConsoleLogWarning]</span></span>  
    
    > [!TIP]
    > <span data-ttu-id="b142c-154">如果想要查看导致邮件以特定方式记录的代码，请单击脚本 \ （如 `log.js:12` \）以查看导致邮件格式的代码。</span><span class="sxs-lookup"><span data-stu-id="b142c-154">If you want to see the code that caused a message to get logged a certain way, click on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="b142c-155">单击**Expand** ![ 前面的展开展开 ][ImageExpandIcon] 图标 `Abandon Hope All Ye Who Enter` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-155">Click the **Expand** ![Expand][ImageExpandIcon] icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="b142c-156">DevTools 显示调用的[堆栈跟踪][WikiStackTrace]。</span><span class="sxs-lookup"><span data-stu-id="b142c-156">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    > ##### <span data-ttu-id="b142c-157">图 9</span><span class="sxs-lookup"><span data-stu-id="b142c-157">Figure 9</span></span>  
    > <span data-ttu-id="b142c-158">堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="b142c-158">A stack trace</span></span>  
    > <span data-ttu-id="b142c-159">![堆栈跟踪][ImageStackTrace]</span><span class="sxs-lookup"><span data-stu-id="b142c-159">![A stack trace][ImageStackTrace]</span></span>  
    
    <span data-ttu-id="b142c-160">堆栈跟踪告诉你调用了名为的函数 `logWarning` ，而该函数又称为一个名为的函数 `quoteDante` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-160">The stack trace is telling you that a function named `logWarning` was called, which in turn called a function named `quoteDante`.</span></span>  <span data-ttu-id="b142c-161">换句话说，首先发生的调用位于堆栈跟踪的底部。</span><span class="sxs-lookup"><span data-stu-id="b142c-161">In other words, the call that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="b142c-162">你可以随时通过调用来记录堆栈跟踪 `console.trace()` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-162">You may log stack traces at any time by calling `console.trace()`.</span></span>  

1.  <span data-ttu-id="b142c-163">单击 "**日志错误**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-163">Click **Log Error**.</span></span>  <span data-ttu-id="b142c-164">已记录以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="b142c-164">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    > ##### <span data-ttu-id="b142c-165">图 10</span><span class="sxs-lookup"><span data-stu-id="b142c-165">Figure 10</span></span>  
    > <span data-ttu-id="b142c-166">一条错误消息</span><span class="sxs-lookup"><span data-stu-id="b142c-166">An error message</span></span>  
    > <span data-ttu-id="b142c-167">![一条错误消息][ImageLogError]</span><span class="sxs-lookup"><span data-stu-id="b142c-167">![An error message][ImageLogError]</span></span>  
    
1.  <span data-ttu-id="b142c-168">单击 "**日志表**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-168">Click **Log Table**.</span></span>  <span data-ttu-id="b142c-169">将有关著名音乐家的表格记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="b142c-169">A table about famous artists gets logged to the Console.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b142c-170">`birthday`列仅填充一行。</span><span class="sxs-lookup"><span data-stu-id="b142c-170">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="b142c-171">检查代码，找出原因。</span><span class="sxs-lookup"><span data-stu-id="b142c-171">Check the code to figure out why that is.</span></span>
    
    > ##### <span data-ttu-id="b142c-172">图 11</span><span class="sxs-lookup"><span data-stu-id="b142c-172">Figure 11</span></span>  
    > <span data-ttu-id="b142c-173">控制台中的表</span><span class="sxs-lookup"><span data-stu-id="b142c-173">A table in the Console</span></span>  
    > <span data-ttu-id="b142c-174">![控制台中的表][ImageConsoleTable]</span><span class="sxs-lookup"><span data-stu-id="b142c-174">![A table in the Console][ImageConsoleTable]</span></span>  
    
1.  <span data-ttu-id="b142c-175">单击 "**日志组**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-175">Click **Log Group**.</span></span>  <span data-ttu-id="b142c-176">4个著名的犯罪 turtles 的名称在标签下分组 `Adolescent Irradiated Espionage Tortoises` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-176">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    > ##### <span data-ttu-id="b142c-177">图 12</span><span class="sxs-lookup"><span data-stu-id="b142c-177">Figure 12</span></span>  
    > <span data-ttu-id="b142c-178">控制台中的一组消息</span><span class="sxs-lookup"><span data-stu-id="b142c-178">A group of messages in the Console</span></span>  
    > <span data-ttu-id="b142c-179">![控制台中的一组消息][ImageConsoleLogGroup]</span><span class="sxs-lookup"><span data-stu-id="b142c-179">![A group of messages in the Console][ImageConsoleLogGroup]</span></span>  
    
1.  <span data-ttu-id="b142c-180">单击 "**日志自定义**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-180">Click **Log Custom**.</span></span>  <span data-ttu-id="b142c-181">带有红色边框和蓝色背景的消息将记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="b142c-181">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    > ##### <span data-ttu-id="b142c-182">图 13</span><span class="sxs-lookup"><span data-stu-id="b142c-182">Figure 13</span></span>  
    > <span data-ttu-id="b142c-183">在控制台中自定义格式的邮件</span><span class="sxs-lookup"><span data-stu-id="b142c-183">A message with custom formatting in the Console</span></span>  
    > <span data-ttu-id="b142c-184">![在控制台中有自定义格式的邮件][ImageConsoleLogCustomFormatting]</span><span class="sxs-lookup"><span data-stu-id="b142c-184">![A message with custom formatting in the Console][ImageConsoleLogCustomFormatting]</span></span>  
    
<span data-ttu-id="b142c-185">此处的主要概念是，当你希望从 JavaScript 将消息记录到控制台时，请使用其中一种 `console` 方法。</span><span class="sxs-lookup"><span data-stu-id="b142c-185">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="b142c-186">每种方法设置邮件的格式都不同。</span><span class="sxs-lookup"><span data-stu-id="b142c-186">Each method formats messages differently.</span></span>  

<span data-ttu-id="b142c-187">此部分中介绍的方法甚至更多。</span><span class="sxs-lookup"><span data-stu-id="b142c-187">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="b142c-188">本教程介绍如何浏览方法的其余部分。</span><span class="sxs-lookup"><span data-stu-id="b142c-188">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <span data-ttu-id="b142c-189">查看浏览器记录的消息</span><span class="sxs-lookup"><span data-stu-id="b142c-189">View messages logged by the browser</span></span>   

<span data-ttu-id="b142c-190">浏览器也将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="b142c-190">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="b142c-191">当页面出现问题时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b142c-191">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="b142c-192">单击 "**原因 404**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-192">Click **Cause 404**.</span></span>  <span data-ttu-id="b142c-193">`404`由于页面的 JavaScript 尝试提取不存在的文件，因此浏览器会记录网络错误。</span><span class="sxs-lookup"><span data-stu-id="b142c-193">The browser logs a `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    > ##### <span data-ttu-id="b142c-194">图 14</span><span class="sxs-lookup"><span data-stu-id="b142c-194">Figure 14</span></span>  
    > <span data-ttu-id="b142c-195">控制台中的404错误</span><span class="sxs-lookup"><span data-stu-id="b142c-195">A 404 error in the Console</span></span>  
    > <span data-ttu-id="b142c-196">![在控制台中出现404错误][ImageConsoleLogError]</span><span class="sxs-lookup"><span data-stu-id="b142c-196">![A 404 error in the Console][ImageConsoleLogError]</span></span>  
    
1.  <span data-ttu-id="b142c-197">单击 "**导致错误**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-197">Click **Cause Error**.</span></span>  <span data-ttu-id="b142c-198">`TypeError`由于 JavaScript 尝试更新不存在的 DOM 节点，因此浏览器将记录未捕获。</span><span class="sxs-lookup"><span data-stu-id="b142c-198">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    > ##### <span data-ttu-id="b142c-199">图 15</span><span class="sxs-lookup"><span data-stu-id="b142c-199">Figure 15</span></span>  
    > <span data-ttu-id="b142c-200">控制台中的 TypeError</span><span class="sxs-lookup"><span data-stu-id="b142c-200">A TypeError in the Console</span></span>  
    > <span data-ttu-id="b142c-201">![控制台中的 TypeError][ImageConsoleLogTypeError]</span><span class="sxs-lookup"><span data-stu-id="b142c-201">![A TypeError in the Console][ImageConsoleLogTypeError]</span></span>  
    
1.  <span data-ttu-id="b142c-202">单击 "**日志级别**" 下拉列表，并启用 "**详细**" 选项（如果已禁用）。</span><span class="sxs-lookup"><span data-stu-id="b142c-202">Click the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="b142c-203">在下一节中了解有关筛选的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b142c-203">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="b142c-204">您需要执行此操作，以确保您记录的下一条消息是可见的。</span><span class="sxs-lookup"><span data-stu-id="b142c-204">You need to do this to make sure that the next message you log is visible.</span></span>  
    <span data-ttu-id="b142c-205">**注意：** 如果 "默认级别" 下拉列表处于禁用状态，您可能需要关闭控制台边栏。</span><span class="sxs-lookup"><span data-stu-id="b142c-205">**Note:** If the Default Levels dropdown is disabled, you may need to close the Console Sidebar.</span></span> <span data-ttu-id="b142c-206">有关控制台边栏的详细信息，请按以下消息源进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b142c-206">Filter by Message Source below for more information about the Console Sidebar.</span></span>
    
    > ##### <span data-ttu-id="b142c-207">图 16</span><span class="sxs-lookup"><span data-stu-id="b142c-207">Figure 16</span></span>  
    > <span data-ttu-id="b142c-208">启用**详细**日志级别</span><span class="sxs-lookup"><span data-stu-id="b142c-208">Enabling the **Verbose** log level</span></span>  
    > <span data-ttu-id="b142c-209">![启用详细日志级别][ImageVerboseLogLevel]</span><span class="sxs-lookup"><span data-stu-id="b142c-209">![Enabling the Verbose log level][ImageVerboseLogLevel]</span></span>  
    
1.  <span data-ttu-id="b142c-210">单击 "**导致冲突**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-210">Click **Cause Violation**.</span></span>  <span data-ttu-id="b142c-211">该页面将在几秒钟后停止响应，然后浏览器将消息记录 `[Violation] 'click' handler took 3000ms` 到控制台。</span><span class="sxs-lookup"><span data-stu-id="b142c-211">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="b142c-212">确切持续时间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="b142c-212">The exact duration may vary.</span></span>  
    
    > ##### <span data-ttu-id="b142c-213">图 17</span><span class="sxs-lookup"><span data-stu-id="b142c-213">Figure 17</span></span>  
    > <span data-ttu-id="b142c-214">控制台中的冲突</span><span class="sxs-lookup"><span data-stu-id="b142c-214">A violation in the Console</span></span>  
    > <span data-ttu-id="b142c-215">![在控制台中的冲突][ImageConsoleLogViolation]</span><span class="sxs-lookup"><span data-stu-id="b142c-215">![A violation in the Console][ImageConsoleLogViolation]</span></span>  
    
## <span data-ttu-id="b142c-216">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="b142c-216">Filter messages</span></span>   

<span data-ttu-id="b142c-217">在某些页面上，你会看到该控制台会使消息淹没。</span><span class="sxs-lookup"><span data-stu-id="b142c-217">On some pages you see the Console get flooded with messages.</span></span>  <span data-ttu-id="b142c-218">DevTools 提供了多种不同的方法来筛选出与手边的任务无关的邮件。</span><span class="sxs-lookup"><span data-stu-id="b142c-218">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <span data-ttu-id="b142c-219">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="b142c-219">Filter by log level</span></span>   

<span data-ttu-id="b142c-220">每个 `console` 方法都分配了一个严重性级别： `Verbose` 、、 `Info` `Warning` 或 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-220">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="b142c-221">例如， `console.log()` 是一种 `Info` 级别的消息，而 `console.error()` 是一种 `Error` 级别的消息。</span><span class="sxs-lookup"><span data-stu-id="b142c-221">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="b142c-222">单击 "**日志级别**" 下拉列表并禁用**错误**。</span><span class="sxs-lookup"><span data-stu-id="b142c-222">Click the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="b142c-223">如果该级别旁边不再有选中标记，则该级别将被禁用。</span><span class="sxs-lookup"><span data-stu-id="b142c-223">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="b142c-224">`Error`级别消息消失。</span><span class="sxs-lookup"><span data-stu-id="b142c-224">The `Error`-level messages disappear.</span></span>  
    
    > ##### <span data-ttu-id="b142c-225">图18</span><span class="sxs-lookup"><span data-stu-id="b142c-225">Figure 18</span></span>  
    > <span data-ttu-id="b142c-226">`Error`在控制台中禁用级别消息</span><span class="sxs-lookup"><span data-stu-id="b142c-226">Disabling `Error`-level messages in the Console</span></span>  
    > <span data-ttu-id="b142c-227">![在控制台中禁用错误级别消息][ImageConsoleDisablingLogError]</span><span class="sxs-lookup"><span data-stu-id="b142c-227">![Disabling Error-level messages in the Console][ImageConsoleDisablingLogError]</span></span>  
    
1.  <span data-ttu-id="b142c-228">再次单击 "**日志级别**" 下拉列表，然后重新启用**错误**。</span><span class="sxs-lookup"><span data-stu-id="b142c-228">Click the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="b142c-229">`Error`级邮件再次出现。</span><span class="sxs-lookup"><span data-stu-id="b142c-229">The `Error`-level messages reappear.</span></span>  

### <span data-ttu-id="b142c-230">按文本进行筛选</span><span class="sxs-lookup"><span data-stu-id="b142c-230">Filter by text</span></span>   

<span data-ttu-id="b142c-231">如果只希望查看包含确切字符串的邮件，请将该字符串键入到 "**筛选器**" 文本框中。</span><span class="sxs-lookup"><span data-stu-id="b142c-231">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="b142c-232">在 `Dave` "**筛选器**" 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="b142c-232">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="b142c-233">不包含该字符串的所有消息 `Dave` 均被隐藏。</span><span class="sxs-lookup"><span data-stu-id="b142c-233">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="b142c-234">您可能还会看到 `Adolescent Irradiated Espionage Tortoises` 标签。</span><span class="sxs-lookup"><span data-stu-id="b142c-234">You might also see the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="b142c-235">这是一个 bug。</span><span class="sxs-lookup"><span data-stu-id="b142c-235">That is a bug.</span></span>  
    
    > ##### <span data-ttu-id="b142c-236">图19</span><span class="sxs-lookup"><span data-stu-id="b142c-236">Figure 19</span></span>  
    > <span data-ttu-id="b142c-237">筛选出不包含的任何邮件</span><span class="sxs-lookup"><span data-stu-id="b142c-237">Filtering out any message that does not include</span></span> `Dave`  
    > <span data-ttu-id="b142c-238">![筛选掉不包含 Dave 的任何消息][ImageLogTextFiltering]</span><span class="sxs-lookup"><span data-stu-id="b142c-238">![Filtering out any message that does not include Dave][ImageLogTextFiltering]</span></span>  
    
1.  <span data-ttu-id="b142c-239">`Dave`从 "**筛选器**" 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="b142c-239">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="b142c-240">所有邮件再次出现。</span><span class="sxs-lookup"><span data-stu-id="b142c-240">All the messages reappear.</span></span>  

### <span data-ttu-id="b142c-241">按正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="b142c-241">Filter by regular expression</span></span>   

<span data-ttu-id="b142c-242">当你想要显示包含文本模式的所有消息（而不是特定字符串）时，请使用[正则表达式][MDNRegularExpressions]。</span><span class="sxs-lookup"><span data-stu-id="b142c-242">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="b142c-243">在 `/^[AH]/` "**筛选器**" 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="b142c-243">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="b142c-244">在[RegExr][|::ref1::|Main]中键入此模式，获取对其执行操作的说明。</span><span class="sxs-lookup"><span data-stu-id="b142c-244">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    > ##### <span data-ttu-id="b142c-245">图20</span><span class="sxs-lookup"><span data-stu-id="b142c-245">Figure 20</span></span>  
    > <span data-ttu-id="b142c-246">筛选出与模式不匹配的任何邮件</span><span class="sxs-lookup"><span data-stu-id="b142c-246">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    > <span data-ttu-id="b142c-247">![筛选出与模式不匹配的任何消息][ImageLogRegExFiltering]</span><span class="sxs-lookup"><span data-stu-id="b142c-247">![Filtering out any message that does not match a pattern][ImageLogRegExFiltering]</span></span>  
    
1.  <span data-ttu-id="b142c-248">`/^[AH]/`从 "**筛选器**" 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="b142c-248">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="b142c-249">所有邮件都将再次显示。</span><span class="sxs-lookup"><span data-stu-id="b142c-249">All messages are visible again.</span></span>  

### <span data-ttu-id="b142c-250">按消息源筛选</span><span class="sxs-lookup"><span data-stu-id="b142c-250">Filter by message source</span></span>   

<span data-ttu-id="b142c-251">如果只希望查看来自特定 URL 的邮件，请使用**边栏**。</span><span class="sxs-lookup"><span data-stu-id="b142c-251">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="b142c-252">单击 "**显示控制台边栏** ![ 显示控制台边栏" ][ImageShowConsoleSidebarIcon] 。</span><span class="sxs-lookup"><span data-stu-id="b142c-252">Click **Show Console Sidebar** ![Show Console Sidebar][ImageShowConsoleSidebarIcon].</span></span>  
    
    > ##### <span data-ttu-id="b142c-253">图21</span><span class="sxs-lookup"><span data-stu-id="b142c-253">Figure 21</span></span>  
    > <span data-ttu-id="b142c-254">边栏</span><span class="sxs-lookup"><span data-stu-id="b142c-254">The Sidebar</span></span>  
    > <span data-ttu-id="b142c-255">![提要栏][ImageConsoleSidebar]</span><span class="sxs-lookup"><span data-stu-id="b142c-255">![The Sidebar][ImageConsoleSidebar]</span></span>  
    
1.  <span data-ttu-id="b142c-256">单击**Expand** ![ ][ImageExpandIcon] 邮件数旁边的展开展开图标。</span><span class="sxs-lookup"><span data-stu-id="b142c-256">Click the **Expand** ![Expand][ImageExpandIcon] icon next to the number of messages.</span></span>  <span data-ttu-id="b142c-257">在[图 21](#figure-21)中，邮件数显示为**13 条消息**。</span><span class="sxs-lookup"><span data-stu-id="b142c-257">In [Figure 21](#figure-21), the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="b142c-258">**边栏**显示导致记录消息的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="b142c-258">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="b142c-259">例如， `log.js` 导致了11条消息。</span><span class="sxs-lookup"><span data-stu-id="b142c-259">For example, `log.js` caused 11 messages.</span></span>  
    
    > ##### <span data-ttu-id="b142c-260">图22</span><span class="sxs-lookup"><span data-stu-id="b142c-260">Figure 22</span></span>  
    > <span data-ttu-id="b142c-261">查看边栏中的邮件源</span><span class="sxs-lookup"><span data-stu-id="b142c-261">Viewing the source of messages in the Sidebar</span></span>  
    > <span data-ttu-id="b142c-262">![查看边栏中的邮件源][ImageConsoleSidebarLogSource]</span><span class="sxs-lookup"><span data-stu-id="b142c-262">![Viewing the source of messages in the Sidebar][ImageConsoleSidebarLogSource]</span></span>  
    
### <span data-ttu-id="b142c-263">按用户消息筛选</span><span class="sxs-lookup"><span data-stu-id="b142c-263">Filter by user messages</span></span>   

<span data-ttu-id="b142c-264">较早版本中，当您单击 "**日志信息**" 时，将调用一个脚本，以便 `console.log('Hello, Console!')` 将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="b142c-264">Earlier, when you clicked **Log Info**, a script called `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="b142c-265">从属于此类的 JavaScript 记录的消息称为 "**用户消息**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-265">Messages logged from JavaScript like this are called **user messages**.</span></span>  <span data-ttu-id="b142c-266">相比之下，当你单击 "**原因 404**" 时，浏览器记录了一个 `Error` 级别消息，指出找不到所请求的资源。</span><span class="sxs-lookup"><span data-stu-id="b142c-266">In contrast, when you clicked **Cause 404**, the browser logged an `Error`-level message stating that the requested resource could not be found.</span></span>  <span data-ttu-id="b142c-267">类似消息被视为**浏览器消息**。</span><span class="sxs-lookup"><span data-stu-id="b142c-267">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="b142c-268">使用**边栏**筛选出浏览器消息，并仅显示用户消息。</span><span class="sxs-lookup"><span data-stu-id="b142c-268">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="b142c-269">单击 " **9 个用户消息**"。</span><span class="sxs-lookup"><span data-stu-id="b142c-269">Click **9 User Messages**.</span></span>  <span data-ttu-id="b142c-270">浏览器消息处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="b142c-270">The browser messages are hidden.</span></span>  
    
    > ##### <span data-ttu-id="b142c-271">图23</span><span class="sxs-lookup"><span data-stu-id="b142c-271">Figure 23</span></span>  
    > <span data-ttu-id="b142c-272">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="b142c-272">Filtering out browser messages</span></span>  
    > <span data-ttu-id="b142c-273">![筛选出浏览器消息][ImageConsoleLogBrowserFiltering]</span><span class="sxs-lookup"><span data-stu-id="b142c-273">![Filtering out browser messages][ImageConsoleLogBrowserFiltering]</span></span>  
    
1.  <span data-ttu-id="b142c-274">单击**13 条消息**，再次显示所有消息。</span><span class="sxs-lookup"><span data-stu-id="b142c-274">Click **13 Messages** to show all messages again.</span></span>  

## <span data-ttu-id="b142c-275">将控制台与任何其他面板一起使用</span><span class="sxs-lookup"><span data-stu-id="b142c-275">Use the Console alongside any other panel</span></span>   

<span data-ttu-id="b142c-276">如果正在编辑样式，但需要快速检查控制台日志是否有什么内容？</span><span class="sxs-lookup"><span data-stu-id="b142c-276">What if you are editing styles, but you need to quickly check the Console log for something?</span></span> <span data-ttu-id="b142c-277">使用抽屉。</span><span class="sxs-lookup"><span data-stu-id="b142c-277">Use the Drawer.</span></span>  

1.  <span data-ttu-id="b142c-278">单击 "**元素**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b142c-278">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="b142c-279">按 `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="b142c-279">Press `Escape`.</span></span>  <span data-ttu-id="b142c-280">将打开**抽屉**的 "控制台" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b142c-280">The Console tab of the **Drawer** opens.</span></span>  <span data-ttu-id="b142c-281">它具有您在整个教程中使用的控制台面板的所有功能。</span><span class="sxs-lookup"><span data-stu-id="b142c-281">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    > ##### <span data-ttu-id="b142c-282">图24</span><span class="sxs-lookup"><span data-stu-id="b142c-282">Figure 24</span></span>  
    > <span data-ttu-id="b142c-283">抽屉中的 "控制台" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b142c-283">The Console tab in the Drawer</span></span>  
    > <span data-ttu-id="b142c-284">![抽屉中的 "控制台" 选项卡][ImageDrawerConsole]</span><span class="sxs-lookup"><span data-stu-id="b142c-284">![The Console tab in the Drawer][ImageDrawerConsole]</span></span>  
    
<!--## Next steps  -->

<!--
*   See [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   See [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   See [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

 



<!-- image links -->  

[ImageExpandIcon]: /microsoft-edge/devtools-guide-chromium/media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: /microsoft-edge/devtools-guide-chromium/media/show-console-sidebar-icon.msft.png  

[ImageLogExample]: /microsoft-edge/devtools-guide-chromium/media/console-ars-technica-console-onload.msft.png "图1：控制台中的邮件"  
<!--[ImageLogSetUp1]: /microsoft-edge/devtools-guide-chromium/media/log-set-up-1.msft.png "old Figure 2: The tutorial on the left, and the demo on the right"  -->  
<span data-ttu-id="b142c-286">[ImageDevToolsRight]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-right-console.msft.png "图2： DevTools 将在演示的右侧打开"</span><span class="sxs-lookup"><span data-stu-id="b142c-286">[ImageDevToolsRight]: /microsoft-edge/devtools-guide-chromium/media/console-example-devtools-right-console.msft.png "Figure 2: DevTools opens to the right of the demo"</span></span>  
<span data-ttu-id="b142c-287">[ImageDevToolsBottom]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-bottom-console.msft.png "图3： DevTools 停靠到演示的底部"</span><span class="sxs-lookup"><span data-stu-id="b142c-287">[ImageDevToolsBottom]: /microsoft-edge/devtools-guide-chromium/media/console-example-devtools-bottom-console.msft.png "Figure 3: DevTools docked to the bottom of the demo"</span></span>  
<span data-ttu-id="b142c-288">[ImageDevToolsSeparateBrowse]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-browse.msft.png "图4：浏览器在单独的窗口中"</span><span class="sxs-lookup"><span data-stu-id="b142c-288">[ImageDevToolsSeparateBrowse]: /microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-browse.msft.png "Figure 4: Browser in a separate window"</span></span>  
<span data-ttu-id="b142c-289">[ImageDevToolsSeparateDevTools]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-devtools.msft.png "图5：在单独的窗口中取消停靠 DevTools"</span><span class="sxs-lookup"><span data-stu-id="b142c-289">[ImageDevToolsSeparateDevTools]: /microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-devtools.msft.png "Figure 5: DevTools undocked in a separate window"</span></span>  
<span data-ttu-id="b142c-290">[ImageLogInfo]：/microsoft-edge/devtools-guide-chromium/media/console-log-info.msft.png "图6：单击" 日志信息 "后的控制台"</span><span class="sxs-lookup"><span data-stu-id="b142c-290">[ImageLogInfo]: /microsoft-edge/devtools-guide-chromium/media/console-log-info.msft.png "Figure 6: The Console after clicking Log Info"</span></span>  
<span data-ttu-id="b142c-291">[ImageSourceLog]：/microsoft-edge/devtools-guide-chromium/media/console-sources-logjs.msft.png "图7：单击" log.js： 2 "后 DevTools 打开" 源 "面板。</span><span class="sxs-lookup"><span data-stu-id="b142c-291">[ImageSourceLog]: /microsoft-edge/devtools-guide-chromium/media/console-sources-logjs.msft.png "Figure 7: DevTools opens the Sources panel after you click log.js:2"</span></span>  
<span data-ttu-id="b142c-292">[ImageConsoleLogWarning]：/microsoft-edge/devtools-guide-chromium/media/console-log-warning.msft.png "图8：单击" 日志警告 "后的控制台"</span><span class="sxs-lookup"><span data-stu-id="b142c-292">[ImageConsoleLogWarning]: /microsoft-edge/devtools-guide-chromium/media/console-log-warning.msft.png "Figure 8: The Console after clicking Log Warning"</span></span>  
<span data-ttu-id="b142c-293">[ImageStackTrace]：/microsoft-edge/devtools-guide-chromium/media/console-log-warning-expanded.msft.png "图9：堆栈跟踪"</span><span class="sxs-lookup"><span data-stu-id="b142c-293">[ImageStackTrace]: /microsoft-edge/devtools-guide-chromium/media/console-log-warning-expanded.msft.png "Figure 9: A stack trace"</span></span>  
<span data-ttu-id="b142c-294">[ImageLogError]：/microsoft-edge/devtools-guide-chromium/media/console-log-error.msft.png "图10：错误消息"</span><span class="sxs-lookup"><span data-stu-id="b142c-294">[ImageLogError]: /microsoft-edge/devtools-guide-chromium/media/console-log-error.msft.png "Figure 10: An error message"</span></span>  
<span data-ttu-id="b142c-295">[ImageConsoleTable]：/microsoft-edge/devtools-guide-chromium/media/console-log-table.msft.png "图11：控制台中的表格"</span><span class="sxs-lookup"><span data-stu-id="b142c-295">[ImageConsoleTable]: /microsoft-edge/devtools-guide-chromium/media/console-log-table.msft.png "Figure 11: A table in the Console"</span></span>  
<span data-ttu-id="b142c-296">[ImageConsoleLogGroup]：/microsoft-edge/devtools-guide-chromium/media/console-log-group.msft.png "图12：一组在控制台中的邮件"</span><span class="sxs-lookup"><span data-stu-id="b142c-296">[ImageConsoleLogGroup]: /microsoft-edge/devtools-guide-chromium/media/console-log-group.msft.png "Figure 12: A group of messages in the Console"</span></span>  
<span data-ttu-id="b142c-297">[ImageConsoleLogCustomFormatting]：/microsoft-edge/devtools-guide-chromium/media/console-log-custom.msft.png "图13：在控制台中有自定义格式的邮件"</span><span class="sxs-lookup"><span data-stu-id="b142c-297">[ImageConsoleLogCustomFormatting]: /microsoft-edge/devtools-guide-chromium/media/console-log-custom.msft.png "Figure 13: A message with custom formatting in the Console"</span></span>  
<span data-ttu-id="b142c-298">[ImageConsoleLogError]：/microsoft-edge/devtools-guide-chromium/media/console-cause-404.msft.png "图14：控制台中的404错误"</span><span class="sxs-lookup"><span data-stu-id="b142c-298">[ImageConsoleLogError]: /microsoft-edge/devtools-guide-chromium/media/console-cause-404.msft.png "Figure 14: A 404 error in the Console"</span></span>  
<span data-ttu-id="b142c-299">[ImageConsoleLogTypeError]：/microsoft-edge/devtools-guide-chromium/media/console-cause-error.msft.png "图15：控制台中的 TypeError"</span><span class="sxs-lookup"><span data-stu-id="b142c-299">[ImageConsoleLogTypeError]: /microsoft-edge/devtools-guide-chromium/media/console-cause-error.msft.png "Figure 15: A TypeError in the Console"</span></span>  
<span data-ttu-id="b142c-300">[ImageVerboseLogLevel]：/microsoft-edge/devtools-guide-chromium/media/console-cause-error-log-levels.msft.png "图16：启用详细日志级别"</span><span class="sxs-lookup"><span data-stu-id="b142c-300">[ImageVerboseLogLevel]: /microsoft-edge/devtools-guide-chromium/media/console-cause-error-log-levels.msft.png "Figure 16: Enabling the Verbose log level"</span></span>  
<span data-ttu-id="b142c-301">[ImageConsoleLogViolation]：/microsoft-edge/devtools-guide-chromium/media/console-cause-violation.msft.png "图17：控制台中的冲突"</span><span class="sxs-lookup"><span data-stu-id="b142c-301">[ImageConsoleLogViolation]: /microsoft-edge/devtools-guide-chromium/media/console-cause-violation.msft.png "Figure 17: A violation in the Console"</span></span>  
<span data-ttu-id="b142c-302">[ImageConsoleDisablingLogError]：/microsoft-edge/devtools-guide-chromium/media/console-cause-violation-log-levels.msft.png "图18：在控制台中禁用错误级别消息"</span><span class="sxs-lookup"><span data-stu-id="b142c-302">[ImageConsoleDisablingLogError]: /microsoft-edge/devtools-guide-chromium/media/console-cause-violation-log-levels.msft.png "Figure 18: Disabling Error-level messages in the Console"</span></span>  
<span data-ttu-id="b142c-303">[ImageLogTextFiltering]：/microsoft-edge/devtools-guide-chromium/media/console-all-messages-text-filter.msft.png "图19：筛选出不包含 Dave 的任何邮件"</span><span class="sxs-lookup"><span data-stu-id="b142c-303">[ImageLogTextFiltering]: /microsoft-edge/devtools-guide-chromium/media/console-all-messages-text-filter.msft.png "Figure 19: Filtering out any message that does not include Dave"</span></span>  
<span data-ttu-id="b142c-304">[ImageLogRegExFiltering]：/microsoft-edge/devtools-guide-chromium/media/console-all-messages-regex-filter.msft.png "图20：筛选出与模式不匹配的任何邮件"</span><span class="sxs-lookup"><span data-stu-id="b142c-304">[ImageLogRegExFiltering]: /microsoft-edge/devtools-guide-chromium/media/console-all-messages-regex-filter.msft.png "Figure 20: Filtering out any message that does not match a pattern"</span></span>  
<span data-ttu-id="b142c-305">[ImageConsoleSidebar]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-all-messages.msft.png "图21：边栏"</span><span class="sxs-lookup"><span data-stu-id="b142c-305">[ImageConsoleSidebar]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-all-messages.msft.png "Figure 21: The Sidebar"</span></span>  
<span data-ttu-id="b142c-306">[ImageConsoleSidebarLogSource]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-expanded-all-messages.msft.png "图22：查看边栏中邮件的来源"</span><span class="sxs-lookup"><span data-stu-id="b142c-306">[ImageConsoleSidebarLogSource]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-expanded-all-messages.msft.png "Figure 22: Viewing the source of messages in the Sidebar"</span></span>  
<span data-ttu-id="b142c-307">[ImageConsoleLogBrowserFiltering]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-user-messages.msft.png "图23：筛选出浏览器消息"</span><span class="sxs-lookup"><span data-stu-id="b142c-307">[ImageConsoleLogBrowserFiltering]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-user-messages.msft.png "Figure 23: Filtering out browser messages"</span></span>  
<span data-ttu-id="b142c-308">[ImageDrawerConsole]：/microsoft-edge/devtools-guide-chromium/media/console-elements-drawer-console-sidebar-all-messages.msft.png "图24：抽屉中的控制台" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b142c-308">[ImageDrawerConsole]: /microsoft-edge/devtools-guide-chromium/media/console-elements-drawer-console-sidebar-all-messages.msft.png "Figure 24: The Console tab in the Drawer"</span></span>  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge \ （Chromium \）开发人员工具"  
[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  
[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "控制台 API 参考"  
[DevToolsConsoleReference]: /microsoft-edge/devtools-guide-chromium/console/reference "控制台参考"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "记录消息入门 |故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "堆栈跟踪-维基百科"  


> [!NOTE]
> <span data-ttu-id="b142c-318">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b142c-318">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b142c-319">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="b142c-319">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="b142c-321">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b142c-321">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
