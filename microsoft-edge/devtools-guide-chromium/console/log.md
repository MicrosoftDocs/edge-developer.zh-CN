---
description: 了解如何将消息记录到控制台。
title: 开始在控制台中记录消息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 2f91f1847bf5469e8106edc21553172fc06db9ee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231109"
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

# <span data-ttu-id="2290c-104">开始在控制台中记录消息</span><span class="sxs-lookup"><span data-stu-id="2290c-104">Get Started With Logging Messages In The Console</span></span>  

<span data-ttu-id="2290c-105">此交互式教程介绍如何在 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 控制台中记录并筛选消息。</span><span class="sxs-lookup"><span data-stu-id="2290c-105">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="控制台中的邮件" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   <span data-ttu-id="2290c-107">控制台中的 **邮件**</span><span class="sxs-lookup"><span data-stu-id="2290c-107">Messages in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="2290c-108">本教程旨在按顺序排列。</span><span class="sxs-lookup"><span data-stu-id="2290c-108">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="2290c-109">它假定你了解 Web 开发的基础，例如如何使用 JavaScript 向页面添加交互性。</span><span class="sxs-lookup"><span data-stu-id="2290c-109">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <span data-ttu-id="2290c-110">设置演示和 DevTools</span><span class="sxs-lookup"><span data-stu-id="2290c-110">Set up the demo and DevTools</span></span>  

<span data-ttu-id="2290c-111">本教程旨在让你能够打开演示并自己尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="2290c-111">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="2290c-112">当您实际跟进时，您以后更有可能会记住工作流。</span><span class="sxs-lookup"><span data-stu-id="2290c-112">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="2290c-113">按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，\*\*\*\* 然后选择控制台日志示例以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="2290c-113">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="2290c-114">控制台日志示例</span><span class="sxs-lookup"><span data-stu-id="2290c-114">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  <span data-ttu-id="2290c-115">关注演示，然后选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="2290c-115">Focus the demo and then select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="2290c-116">默认情况下，DevTools 将在演示右侧打开。</span><span class="sxs-lookup"><span data-stu-id="2290c-116">By default DevTools opens to the right of the demo.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="DevTools 将在演示右侧打开" lightbox="../media/console-example-devtools-right-console.msft.png":::
             <span data-ttu-id="2290c-118">DevTools 将在演示右侧打开</span><span class="sxs-lookup"><span data-stu-id="2290c-118">DevTools opens to the right of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="2290c-119">[窗口底部的扩展坞 DevTools。][DevToolsCustomizePlacement]</span><span class="sxs-lookup"><span data-stu-id="2290c-119">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="停靠在演示底部的 DevTools" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             <span data-ttu-id="2290c-121">停靠在演示底部的 DevTools</span><span class="sxs-lookup"><span data-stu-id="2290c-121">DevTools docked to the bottom of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="2290c-122">[将 DevTools 撤消到单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="2290c-122">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             <span data-ttu-id="2290c-124">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="2290c-124">Browser in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="2290c-125">[将 DevTools 撤消到单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="2290c-125">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="DevTools 在单独的窗口中取消停靠" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             <span data-ttu-id="2290c-127">DevTools 在单独的窗口中取消停靠</span><span class="sxs-lookup"><span data-stu-id="2290c-127">DevTools undocked in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="2290c-128">查看从 JavaScript 记录的消息</span><span class="sxs-lookup"><span data-stu-id="2290c-128">View messages logged from JavaScript</span></span>  

<span data-ttu-id="2290c-129">控制台中显示的大多数消息来自编写页面\*\*\*\* JavaScript 的 Web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="2290c-129">Most messages that are displayed in the **Console** come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="2290c-130">本节的目标是向你介绍你可能在控制台中查看的不同邮件类型，并说明如何从自己的 JavaScript 自行\*\*\*\* 记录每封邮件类型。</span><span class="sxs-lookup"><span data-stu-id="2290c-130">The goal of this section is to introduce you to the different message types that you are likely to review in the **Console**, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="2290c-131">在 **演示中选择** "日志信息"按钮。</span><span class="sxs-lookup"><span data-stu-id="2290c-131">Choose the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="2290c-132">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="2290c-132">gets logged to the Console.</span></span>
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="选择日志信息后的控制台" lightbox="../media/console-log-info.msft.png":::
       <span data-ttu-id="2290c-134">选择 **日志** 信息后的 **控制台**</span><span class="sxs-lookup"><span data-stu-id="2290c-134">The **Console** after you choose **Log Info**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-135">在控制台 `Hello, Console!` 中的消息旁边，选择**log.js：2。**</span><span class="sxs-lookup"><span data-stu-id="2290c-135">Next to the `Hello, Console!` message in the Console choose **log.js:2**.</span></span>  <span data-ttu-id="2290c-136">"源"面板将打开，并突出显示导致消息记录到控制台的代码行。</span><span class="sxs-lookup"><span data-stu-id="2290c-136">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="2290c-137">当页面的 JavaScript 运行时，已记录消息 `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="2290c-137">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="选择"源"面板后，DevTools 将打开log.js：2" lightbox="../media/console-sources-logjs.msft.png":::
       <span data-ttu-id="2290c-139">选择后，DevTools **将打开** "源"面板</span><span class="sxs-lookup"><span data-stu-id="2290c-139">DevTools opens the **Sources** panel after you choose</span></span> `log.js:2`  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-140">使用下列 **任一工作流** 导航回控制台：</span><span class="sxs-lookup"><span data-stu-id="2290c-140">Navigate back to the **Console** using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="2290c-141">选择" **控制台"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2290c-141">Choose the **Console** tab.</span></span>  
    *   <span data-ttu-id="2290c-142">选择 `Control` + `[` \ (Windows、Linux\) 或 `Command` + `[` \ (macOS\) ，\*\*\*\* 直到控制台面板聚焦。</span><span class="sxs-lookup"><span data-stu-id="2290c-142">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) until the **Console** panel is in focus.</span></span>  
    *   <span data-ttu-id="2290c-143">[打开命令菜单][DevToolsCommandMenu]，键入 `Console` ，选择显示 **控制台面板** 命令，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="2290c-143">[Open the Command Menu][DevToolsCommandMenu], type `Console`, choose the **Show Console Panel** command, and then select `Enter`.</span></span>  
    
1.  <span data-ttu-id="2290c-144">在演示 **中选择** "日志警告"按钮。</span><span class="sxs-lookup"><span data-stu-id="2290c-144">Choose the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="2290c-145">记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="2290c-145">gets logged to the **Console**.</span></span>  <span data-ttu-id="2290c-146">如下所示的邮件是警告。</span><span class="sxs-lookup"><span data-stu-id="2290c-146">Messages formatted like this are warnings.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="选择日志警告后的控制台" lightbox="../media/console-log-warning.msft.png":::
       <span data-ttu-id="2290c-148">选择 **日志** 警告后的 **控制台**</span><span class="sxs-lookup"><span data-stu-id="2290c-148">The **Console** after you choose **Log Warning**</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="2290c-149">如果要显示导致邮件以特定方式记录的代码，请选择脚本 \ (例如 \) 以查看导致邮件格式化的代码。 `log.js:12`</span><span class="sxs-lookup"><span data-stu-id="2290c-149">If you want to display the code that caused a message to get logged a certain way, choose on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="2290c-150">选择 **前面的"展开** (![ ][ImageExpandIcon] 展开\) 图标 `Abandon Hope All Ye Who Enter` 。</span><span class="sxs-lookup"><span data-stu-id="2290c-150">Choose the **Expand** \(![Expand][ImageExpandIcon]\) icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="2290c-151">DevTools [显示调用][WikiStackTrace] 前导的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="2290c-151">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="堆栈跟踪" lightbox="../media/console-log-warning-expanded.msft.png":::
       <span data-ttu-id="2290c-153">堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="2290c-153">A stack trace</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="2290c-154">堆栈跟踪会告知您，已运行命名的函数 `logWarning` ，而该函数又运行名为函数 `quoteDante` 。</span><span class="sxs-lookup"><span data-stu-id="2290c-154">The stack trace is telling you that a function named `logWarning` is run, which in turn runs a function named `quoteDante`.</span></span>  <span data-ttu-id="2290c-155">换句话说，首先发生的请求位于堆栈跟踪的底部。</span><span class="sxs-lookup"><span data-stu-id="2290c-155">In other words, the request that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="2290c-156">你随时可能通过运行来记录堆栈跟踪 `console.trace()` 。</span><span class="sxs-lookup"><span data-stu-id="2290c-156">You may log stack traces at any time by running `console.trace()`.</span></span>  

1.  <span data-ttu-id="2290c-157">选择 **"日志错误"。**</span><span class="sxs-lookup"><span data-stu-id="2290c-157">Choose **Log Error**.</span></span>  <span data-ttu-id="2290c-158">将记录以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2290c-158">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="错误消息" lightbox="../media/console-log-error.msft.png":::
       <span data-ttu-id="2290c-160">错误消息</span><span class="sxs-lookup"><span data-stu-id="2290c-160">An error message</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-161">选择 **"日志表"。**</span><span class="sxs-lookup"><span data-stu-id="2290c-161">Choose **Log Table**.</span></span>  <span data-ttu-id="2290c-162">有关艺术家的表被记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="2290c-162">A table about famous artists gets logged to the **Console**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2290c-163">该 `birthday` 列只填充一行。</span><span class="sxs-lookup"><span data-stu-id="2290c-163">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="2290c-164">查看代码以确定原因。</span><span class="sxs-lookup"><span data-stu-id="2290c-164">Review the code to determine why that is.</span></span>
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="控制台中的表" lightbox="../media/console-log-table.msft.png":::
       <span data-ttu-id="2290c-166">控制台中的 **表**</span><span class="sxs-lookup"><span data-stu-id="2290c-166">A table in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-167">选择 **日志组**。</span><span class="sxs-lookup"><span data-stu-id="2290c-167">Choose **Log Group**.</span></span>  <span data-ttu-id="2290c-168">4 个动物、反犯罪者的名称将分组在标签 `Adolescent Irradiated Espionage Tortoises` 下。</span><span class="sxs-lookup"><span data-stu-id="2290c-168">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="控制台中的一组消息" lightbox="../media/console-log-group.msft.png":::
       <span data-ttu-id="2290c-170">控制台中的一组 **消息**</span><span class="sxs-lookup"><span data-stu-id="2290c-170">A group of messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-171">选择 **"日志自定义"。**</span><span class="sxs-lookup"><span data-stu-id="2290c-171">Choose **Log Custom**.</span></span>  <span data-ttu-id="2290c-172">红色边框和蓝色背景的消息将记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="2290c-172">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="控制台中具有自定义格式的邮件" lightbox="../media/console-log-custom.msft.png":::
       <span data-ttu-id="2290c-174">控制台中具有自定义格式 **的邮件**</span><span class="sxs-lookup"><span data-stu-id="2290c-174">A message with custom formatting in the **Console**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="2290c-175">此处的主要想法是，当你希望从 JavaScript 将消息记录到控制台时，可使用其中一 `console` 种方法。</span><span class="sxs-lookup"><span data-stu-id="2290c-175">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="2290c-176">每种方法对邮件的格式不同。</span><span class="sxs-lookup"><span data-stu-id="2290c-176">Each method formats messages differently.</span></span>  

<span data-ttu-id="2290c-177">方法比本节中演示的方法更多。</span><span class="sxs-lookup"><span data-stu-id="2290c-177">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="2290c-178">本教程介绍如何浏览其余方法。</span><span class="sxs-lookup"><span data-stu-id="2290c-178">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <span data-ttu-id="2290c-179">查看浏览器记录的消息</span><span class="sxs-lookup"><span data-stu-id="2290c-179">View messages logged by the browser</span></span>  

<span data-ttu-id="2290c-180">浏览器将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="2290c-180">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="2290c-181">当页面出现问题时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="2290c-181">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="2290c-182">选择 **原因 404**。</span><span class="sxs-lookup"><span data-stu-id="2290c-182">Choose **Cause 404**.</span></span>  <span data-ttu-id="2290c-183">浏览器记录网络错误的 HTTP 状态代码 `404` ，因为页面的 JavaScript 尝试获取不存在的文件。</span><span class="sxs-lookup"><span data-stu-id="2290c-183">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="控制台中的 404 错误" lightbox="../media/console-cause-404.msft.png":::
       <span data-ttu-id="2290c-185">控制台 `404` 中的 **错误**</span><span class="sxs-lookup"><span data-stu-id="2290c-185">A `404` error in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-186">选择 **"原因错误"。**</span><span class="sxs-lookup"><span data-stu-id="2290c-186">Choose **Cause Error**.</span></span>  <span data-ttu-id="2290c-187">浏览器将记录未记录， `TypeError` 因为 JavaScript 正在尝试更新不存在的 DOM 节点。</span><span class="sxs-lookup"><span data-stu-id="2290c-187">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="控制台中的 TypeError" lightbox="../media/console-cause-error.msft.png":::
       <span data-ttu-id="2290c-189">控制台 `TypeError` 中的\*\*\*\* A</span><span class="sxs-lookup"><span data-stu-id="2290c-189">A `TypeError` in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-190">Choose the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span><span class="sxs-lookup"><span data-stu-id="2290c-190">Choose the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="2290c-191">你将在下一节中了解有关筛选功能的内容。</span><span class="sxs-lookup"><span data-stu-id="2290c-191">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="2290c-192">需要这样做以确保记录的下一条消息可见。</span><span class="sxs-lookup"><span data-stu-id="2290c-192">You need to do this to make sure that the next message you log is visible.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2290c-193">如果"默认级别"下拉列表处于禁用状态，您可能需要关闭 **控制台** 边栏。</span><span class="sxs-lookup"><span data-stu-id="2290c-193">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span></span>  <span data-ttu-id="2290c-194">按下面的消息源进行筛选，了解有关控制台边 **栏** 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2290c-194">Filter by Message Source below for more information about the **Console** Sidebar.</span></span>
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="启用详细日志级别" lightbox="../media/console-cause-error-log-levels.msft.png":::
       <span data-ttu-id="2290c-196">启用详细日志级别</span><span class="sxs-lookup"><span data-stu-id="2290c-196">Enabling the Verbose log level</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-197">选择 **"原因冲突"。**</span><span class="sxs-lookup"><span data-stu-id="2290c-197">Choose **Cause Violation**.</span></span>  <span data-ttu-id="2290c-198">页面在几秒钟后将无响应，然后浏览器将消息记录 `[Violation] 'click' handler took 3000ms` 到控制台。</span><span class="sxs-lookup"><span data-stu-id="2290c-198">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="2290c-199">确切的持续时间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="2290c-199">The exact duration may vary.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="控制台中的冲突" lightbox="../media/console-cause-violation.msft.png":::
       <span data-ttu-id="2290c-201">控制台中的 **冲突**</span><span class="sxs-lookup"><span data-stu-id="2290c-201">A violation in the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="2290c-202">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="2290c-202">Filter messages</span></span>  

<span data-ttu-id="2290c-203">在某些网页上，你查看 **控制台** 时收到大量消息。</span><span class="sxs-lookup"><span data-stu-id="2290c-203">On some webpages you review the **Console** get flooded with messages.</span></span>  <span data-ttu-id="2290c-204">DevTools 提供了许多不同的方法来筛选出与当前任务不相关的邮件。</span><span class="sxs-lookup"><span data-stu-id="2290c-204">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <span data-ttu-id="2290c-205">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="2290c-205">Filter by log level</span></span>  

<span data-ttu-id="2290c-206">每个 `console` 方法都分配有一个严重性级别：、、 `Verbose` `Info` `Warning` 或 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="2290c-206">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="2290c-207">例如， `console.log()` 是 `Info` -level 消息， `console.error()` 而 `Error` -level 消息。</span><span class="sxs-lookup"><span data-stu-id="2290c-207">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="2290c-208">选择 **"日志级别**"下拉列表并禁用 **"错误"。**</span><span class="sxs-lookup"><span data-stu-id="2290c-208">Choose the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="2290c-209">当一个级别旁边不再有选中标记时，该级别将被禁用。</span><span class="sxs-lookup"><span data-stu-id="2290c-209">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="2290c-210">`Error`-level 消息将消失。</span><span class="sxs-lookup"><span data-stu-id="2290c-210">The `Error`-level messages disappear.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="在控制台中禁用错误级别消息" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       <span data-ttu-id="2290c-212">在控制台中禁用错误级别 **消息**</span><span class="sxs-lookup"><span data-stu-id="2290c-212">Disable Error-level messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-213">再次**选择"日志**级别"下拉列表，然后重新启用 **"错误"。**</span><span class="sxs-lookup"><span data-stu-id="2290c-213">Choose the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="2290c-214">`Error`-level 消息将重新出现。</span><span class="sxs-lookup"><span data-stu-id="2290c-214">The `Error`-level messages reappear.</span></span>  

### <span data-ttu-id="2290c-215">按文本筛选</span><span class="sxs-lookup"><span data-stu-id="2290c-215">Filter by text</span></span>  

<span data-ttu-id="2290c-216">当只想查看包含确切字符串的邮件时，在"筛选器"文本框中 **键入该字符串** 。</span><span class="sxs-lookup"><span data-stu-id="2290c-216">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="2290c-217">键入 `Dave` 到“**筛选器**”文本框。</span><span class="sxs-lookup"><span data-stu-id="2290c-217">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="2290c-218">不包含字符串的所有邮件 `Dave` 都处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="2290c-218">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="2290c-219">还可以查看 `Adolescent Irradiated Espionage Tortoises` 标签。</span><span class="sxs-lookup"><span data-stu-id="2290c-219">You may also review the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="2290c-220">这是一个 bug。</span><span class="sxs-lookup"><span data-stu-id="2290c-220">That is a bug.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="筛选掉不包含 Dave 的任何邮件" lightbox="../media/console-all-messages-text-filter.msft.png":::
       <span data-ttu-id="2290c-222">筛选掉任何不包含的邮件</span><span class="sxs-lookup"><span data-stu-id="2290c-222">Filter out any message that does not include</span></span> `Dave`  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-223">从 `Dave` " **筛选器"** 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="2290c-223">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="2290c-224">将重新显示所有消息。</span><span class="sxs-lookup"><span data-stu-id="2290c-224">All the messages reappear.</span></span>  

### <span data-ttu-id="2290c-225">按正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="2290c-225">Filter by regular expression</span></span>  

<span data-ttu-id="2290c-226">当您想要显示包含文本模式（而不是特定字符串）的所有邮件时，请使用 [正则表达式][MDNRegularExpressions]。</span><span class="sxs-lookup"><span data-stu-id="2290c-226">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="2290c-227">键入 `/^[AH]/` 到“**筛选器**”文本框。</span><span class="sxs-lookup"><span data-stu-id="2290c-227">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="2290c-228">在 [RegExr 中键入此模式][|::ref1::|Main] ，以说明它正在做什么。</span><span class="sxs-lookup"><span data-stu-id="2290c-228">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="筛选出与模式不匹配的任何邮件" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       <span data-ttu-id="2290c-230">筛选出与模式不匹配的任何邮件</span><span class="sxs-lookup"><span data-stu-id="2290c-230">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-231">从 `/^[AH]/` " **筛选器"** 文本框中删除。</span><span class="sxs-lookup"><span data-stu-id="2290c-231">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="2290c-232">所有邮件再次可见。</span><span class="sxs-lookup"><span data-stu-id="2290c-232">All messages are visible again.</span></span>  

### <span data-ttu-id="2290c-233">按邮件源筛选</span><span class="sxs-lookup"><span data-stu-id="2290c-233">Filter by message source</span></span>  

<span data-ttu-id="2290c-234">当你只想查看来自特定 URL 的消息时，请使用 **边栏**。</span><span class="sxs-lookup"><span data-stu-id="2290c-234">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="2290c-235">Choose **Show Console Sidebar** \ (![ Show Console Sidebar ][ImageShowConsoleSidebarIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="2290c-235">Choose **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\).</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="边栏" lightbox="../media/console-sidebar-all-messages.msft.png":::
       <span data-ttu-id="2290c-237">边栏</span><span class="sxs-lookup"><span data-stu-id="2290c-237">The Sidebar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-238">Choose the **Expand** \ (![ Expand ][ImageExpandIcon] \) icon next to the number of messages.</span><span class="sxs-lookup"><span data-stu-id="2290c-238">Choose the **Expand** \(![Expand][ImageExpandIcon]\) icon next to the number of messages.</span></span>  <span data-ttu-id="2290c-239">在下图中，邮件数指示为 **13 个邮件**。</span><span class="sxs-lookup"><span data-stu-id="2290c-239">In the following figure, the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="2290c-240">**边栏**显示导致记录消息的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="2290c-240">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="2290c-241">例如， `log.js` 导致 11 条消息。</span><span class="sxs-lookup"><span data-stu-id="2290c-241">For example, `log.js` caused 11 messages.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="查看边栏中的消息源" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       <span data-ttu-id="2290c-243">在边栏中查看消息源</span><span class="sxs-lookup"><span data-stu-id="2290c-243">Viewing the source of messages in the Sidebar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="2290c-244">按用户邮件筛选</span><span class="sxs-lookup"><span data-stu-id="2290c-244">Filter by user messages</span></span>  

<span data-ttu-id="2290c-245">之前，选择"日志 **信息**"时，会指定一个脚本，用于 `console.log('Hello, Console!')` 将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="2290c-245">Earlier, when you choose **Log Info**, a script named `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="2290c-246">从 JavaScript 中记录的消息（如下所示）称为 **用户消息**。</span><span class="sxs-lookup"><span data-stu-id="2290c-246">Messages logged from JavaScript like this are named **user messages**.</span></span>  <span data-ttu-id="2290c-247">相比之下，当你选择 **"原因 404"** 时，浏览器会记录一条 -level 消息，指出找不到请求 `Error` 的资源。</span><span class="sxs-lookup"><span data-stu-id="2290c-247">In contrast, when you choose **Cause 404**, the browser logs an `Error`-level message stating that the requested resource could not be found.</span></span>  <span data-ttu-id="2290c-248">类似消息被视为浏览器 **消息**。</span><span class="sxs-lookup"><span data-stu-id="2290c-248">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="2290c-249">使用 **边栏筛选** 掉浏览器消息，并只显示用户消息。</span><span class="sxs-lookup"><span data-stu-id="2290c-249">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="2290c-250">选择 **9 个用户消息**。</span><span class="sxs-lookup"><span data-stu-id="2290c-250">Choose **9 User Messages**.</span></span>  <span data-ttu-id="2290c-251">浏览器消息处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="2290c-251">The browser messages are hidden.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="筛选掉浏览器消息" lightbox="../media/console-sidebar-user-messages.msft.png":::
       <span data-ttu-id="2290c-253">筛选掉浏览器消息</span><span class="sxs-lookup"><span data-stu-id="2290c-253">Filtering out browser messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2290c-254">选择 **"13 条消息** "可再次显示所有邮件。</span><span class="sxs-lookup"><span data-stu-id="2290c-254">Choose **13 Messages** to show all messages again.</span></span>  

## <span data-ttu-id="2290c-255">将控制台与任何其他面板一同使用</span><span class="sxs-lookup"><span data-stu-id="2290c-255">Use the Console alongside any other panel</span></span>  

<span data-ttu-id="2290c-256">如果要编辑样式，但需要快速检查控制台日志中的某内容，该做什么？</span><span class="sxs-lookup"><span data-stu-id="2290c-256">What if you are editing styles, but you need to quickly check the Console log for something?</span></span>  <span data-ttu-id="2290c-257">使用"箱"。</span><span class="sxs-lookup"><span data-stu-id="2290c-257">Use the Drawer.</span></span>  

1.  <span data-ttu-id="2290c-258">选择" **元素"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2290c-258">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="2290c-259">选择 `Escape`。</span><span class="sxs-lookup"><span data-stu-id="2290c-259">Select `Escape`.</span></span>  <span data-ttu-id="2290c-260">将 **打开** "箱" **的"控制台"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2290c-260">The **Console** tab of the **Drawer** opens.</span></span>  <span data-ttu-id="2290c-261">它拥有你在整个教程中一直使用的控制台面板的所有功能。</span><span class="sxs-lookup"><span data-stu-id="2290c-261">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text=""箱"中的"控制台"选项卡" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         <span data-ttu-id="2290c-263">" **箱"** 中的"控制台" **选项卡**</span><span class="sxs-lookup"><span data-stu-id="2290c-263">The **Console** tab in the **Drawer**</span></span>  
    :::image-end:::  
    
<!--## Next steps  -->

<!--
*   Navigate to [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   Navigate to [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   Navigate to [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

## <span data-ttu-id="2290c-264">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="2290c-264">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具 |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考 |Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "控制台参考 |Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "日志记录消息入门 |小故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "堆栈跟踪 - Wikipedia"  
> [!NOTE]
> <span data-ttu-id="2290c-274">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2290c-274">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2290c-275">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="2290c-275">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2290c-277">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2290c-277">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
