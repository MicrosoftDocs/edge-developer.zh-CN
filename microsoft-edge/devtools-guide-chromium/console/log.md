---
description: 了解如何将消息记录到控制台。
title: 开始在控制台中记录消息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: fb428154b00959db1627096819c565dd5dc11346
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439287"
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

# <a name="get-started-with-logging-messages-in-the-console"></a><span data-ttu-id="621e6-104">开始在控制台中记录消息</span><span class="sxs-lookup"><span data-stu-id="621e6-104">Get started with logging messages in the Console</span></span>  

<span data-ttu-id="621e6-105">此交互式教程介绍如何在 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 控制台中记录并筛选消息。</span><span class="sxs-lookup"><span data-stu-id="621e6-105">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="控制台中的消息" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   <span data-ttu-id="621e6-107">控制台中的 **消息**</span><span class="sxs-lookup"><span data-stu-id="621e6-107">Messages in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="621e6-108">本教程旨在按顺序排列。</span><span class="sxs-lookup"><span data-stu-id="621e6-108">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="621e6-109">它假定你了解 Web 开发的基础，例如如何使用 JavaScript 向页面添加交互性。</span><span class="sxs-lookup"><span data-stu-id="621e6-109">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <a name="set-up-the-demo-and-devtools"></a><span data-ttu-id="621e6-110">设置演示和 DevTools</span><span class="sxs-lookup"><span data-stu-id="621e6-110">Set up the demo and DevTools</span></span>  

<span data-ttu-id="621e6-111">本教程旨在让你能够打开演示并自己尝试所有工作流。</span><span class="sxs-lookup"><span data-stu-id="621e6-111">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="621e6-112">当您实际遵循此流程时，您以后更有可能会记住工作流。</span><span class="sxs-lookup"><span data-stu-id="621e6-112">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="621e6-113">按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) \*\*\*\* 并选择"控制台日志示例"以在新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="621e6-113">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="621e6-114">控制台日志示例</span><span class="sxs-lookup"><span data-stu-id="621e6-114">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  <span data-ttu-id="621e6-115">关注演示，然后选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="621e6-115">Focus the demo and then select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="621e6-116">默认情况下，DevTools 将在演示的右侧打开。</span><span class="sxs-lookup"><span data-stu-id="621e6-116">By default DevTools opens to the right of the demo.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="DevTools 将在演示右侧打开" lightbox="../media/console-example-devtools-right-console.msft.png":::
             <span data-ttu-id="621e6-118">DevTools 将在演示右侧打开</span><span class="sxs-lookup"><span data-stu-id="621e6-118">DevTools opens to the right of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="621e6-119">[窗口底部的扩展坞 DevTools。][DevToolsCustomizePlacement]</span><span class="sxs-lookup"><span data-stu-id="621e6-119">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="DevTools 固定到演示底部" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             <span data-ttu-id="621e6-121">DevTools 固定到演示底部</span><span class="sxs-lookup"><span data-stu-id="621e6-121">DevTools docked to the bottom of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="621e6-122">[将 DevTools 撤消到单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="621e6-122">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             <span data-ttu-id="621e6-124">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="621e6-124">Browser in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="621e6-125">[将 DevTools 撤消到单独的窗口中][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="621e6-125">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="在单独的窗口中取消停靠的 DevTools" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             <span data-ttu-id="621e6-127">在单独的窗口中取消停靠的 DevTools</span><span class="sxs-lookup"><span data-stu-id="621e6-127">DevTools undocked in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="view-messages-logged-from-javascript"></a><span data-ttu-id="621e6-128">查看从 JavaScript 记录的消息</span><span class="sxs-lookup"><span data-stu-id="621e6-128">View messages logged from JavaScript</span></span>  

<span data-ttu-id="621e6-129">控制台中显示的大多数消息来自编写页面\*\*\*\* JavaScript 的 Web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="621e6-129">Most messages that are displayed in the **Console** come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="621e6-130">本节的目的是介绍您可能在控制台中查看的不同邮件类型，并说明如何从自己的 JavaScript 自行记录\*\*\*\* 每封邮件类型。</span><span class="sxs-lookup"><span data-stu-id="621e6-130">The goal of this section is to introduce you to the different message types that you are likely to review in the **Console**, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="621e6-131">在演示 **中选择** "日志信息"按钮。</span><span class="sxs-lookup"><span data-stu-id="621e6-131">Choose the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="621e6-132">记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="621e6-132">gets logged to the Console.</span></span>
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="选择"日志信息"后的控制台" lightbox="../media/console-log-info.msft.png":::
       <span data-ttu-id="621e6-134">选择 **"** 日志信息 **"后的控制台**</span><span class="sxs-lookup"><span data-stu-id="621e6-134">The **Console** after you choose **Log Info**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-135">在控制台中 `Hello, Console!` 的消息旁边，选择 **"log.js：2"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-135">Next to the `Hello, Console!` message in the Console choose **log.js:2**.</span></span>  <span data-ttu-id="621e6-136">"源"面板将打开并突出显示导致消息记录到控制台的代码行。</span><span class="sxs-lookup"><span data-stu-id="621e6-136">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="621e6-137">当页面的 JavaScript 运行 时，会记录该消息 `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="621e6-137">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="选择"源"工具后，DevTools 将打开log.js：2" lightbox="../media/console-sources-logjs.msft.png":::
       <span data-ttu-id="621e6-139">选择后，DevTools **将** 打开"源"工具</span><span class="sxs-lookup"><span data-stu-id="621e6-139">DevTools opens the **Sources** tool after you choose</span></span> `log.js:2`  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-140">使用下列任何 **工作流** 导航回控制台：</span><span class="sxs-lookup"><span data-stu-id="621e6-140">Navigate back to the **Console** using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="621e6-141">选择 **控制台** 工具。</span><span class="sxs-lookup"><span data-stu-id="621e6-141">Choose the **Console** tool.</span></span>  
    *   <span data-ttu-id="621e6-142">选择 `Control` + `[` \ (Windows、Linux\) 或 `Command` + `[` \ (macOS\) 直到控制台工具成为焦点。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="621e6-142">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) until the **Console** tool is in focus.</span></span>  
    *   <span data-ttu-id="621e6-143">[打开命令菜单，][DevToolsCommandMenu]键入 `Console` ，选择显示 **控制台面板** 命令，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="621e6-143">[Open the Command Menu][DevToolsCommandMenu], type `Console`, choose the **Show Console Panel** command, and then select `Enter`.</span></span>  
    
1.  <span data-ttu-id="621e6-144">在演示 **中选择** "日志警告"按钮。</span><span class="sxs-lookup"><span data-stu-id="621e6-144">Choose the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="621e6-145">记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="621e6-145">gets logged to the **Console**.</span></span>  <span data-ttu-id="621e6-146">如下所示的邮件是警告。</span><span class="sxs-lookup"><span data-stu-id="621e6-146">Messages formatted like this are warnings.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="选择"日志警告"后的控制台" lightbox="../media/console-log-warning.msft.png":::
       <span data-ttu-id="621e6-148">选择 **"** 日志警告"后的 **控制台**</span><span class="sxs-lookup"><span data-stu-id="621e6-148">The **Console** after you choose **Log Warning**</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="621e6-149">如果要显示导致以特定方式记录消息的代码，请选择脚本 \ (如 \) 以查看导致邮件格式化的代码 `log.js:12` 。</span><span class="sxs-lookup"><span data-stu-id="621e6-149">If you want to display the code that caused a message to get logged a certain way, choose on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="621e6-150">选择前面的 **展开** \ (展开 ![ ](../media/expand-icon.msft.png) \) 图标 `Abandon Hope All Ye Who Enter` 。</span><span class="sxs-lookup"><span data-stu-id="621e6-150">Choose the **Expand** \(![Expand](../media/expand-icon.msft.png)\) icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="621e6-151">DevTools 显示 [调用][WikiStackTrace] 前导的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="621e6-151">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="堆栈跟踪" lightbox="../media/console-log-warning-expanded.msft.png":::
       <span data-ttu-id="621e6-153">堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="621e6-153">A stack trace</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="621e6-154">堆栈跟踪会告知你，名为 `logWarning` 的函数运行，而该函数又运行名为 的函数 `quoteDante` 。</span><span class="sxs-lookup"><span data-stu-id="621e6-154">The stack trace is telling you that a function named `logWarning` is run, which in turn runs a function named `quoteDante`.</span></span>  <span data-ttu-id="621e6-155">换句话说，首先发生的请求位于堆栈跟踪的底部。</span><span class="sxs-lookup"><span data-stu-id="621e6-155">In other words, the request that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="621e6-156">你随时可能通过运行 记录堆栈跟踪 `console.trace()` 。</span><span class="sxs-lookup"><span data-stu-id="621e6-156">You may log stack traces at any time by running `console.trace()`.</span></span>  

1.  <span data-ttu-id="621e6-157">选择 **"日志错误"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-157">Choose **Log Error**.</span></span>  <span data-ttu-id="621e6-158">将记录以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="621e6-158">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="错误消息" lightbox="../media/console-log-error.msft.png":::
       <span data-ttu-id="621e6-160">错误消息</span><span class="sxs-lookup"><span data-stu-id="621e6-160">An error message</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-161">选择 **"日志表"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-161">Choose **Log Table**.</span></span>  <span data-ttu-id="621e6-162">有关艺术家的表将被记录到**控制台。**</span><span class="sxs-lookup"><span data-stu-id="621e6-162">A table about famous artists gets logged to the **Console**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="621e6-163">仅为 `birthday` 一行填充该列。</span><span class="sxs-lookup"><span data-stu-id="621e6-163">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="621e6-164">查看代码以确定原因。</span><span class="sxs-lookup"><span data-stu-id="621e6-164">Review the code to determine why that is.</span></span>
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="控制台中的表" lightbox="../media/console-log-table.msft.png":::
       <span data-ttu-id="621e6-166">控制台中的 **表**</span><span class="sxs-lookup"><span data-stu-id="621e6-166">A table in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-167">选择 **"日志组"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-167">Choose **Log Group**.</span></span>  <span data-ttu-id="621e6-168">4 个动物、反犯罪团体的名称在标签下 `Adolescent Irradiated Espionage Tortoises` 分组。</span><span class="sxs-lookup"><span data-stu-id="621e6-168">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="控制台中的一组消息" lightbox="../media/console-log-group.msft.png":::
       <span data-ttu-id="621e6-170">控制台中的一组 **消息**</span><span class="sxs-lookup"><span data-stu-id="621e6-170">A group of messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-171">选择 **"日志自定义"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-171">Choose **Log Custom**.</span></span>  <span data-ttu-id="621e6-172">将红色边框和蓝色背景的消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="621e6-172">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="控制台中具有自定义格式的消息" lightbox="../media/console-log-custom.msft.png":::
       <span data-ttu-id="621e6-174">控制台中具有自定义格式 **的消息**</span><span class="sxs-lookup"><span data-stu-id="621e6-174">A message with custom formatting in the **Console**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="621e6-175">此处的主要理念是，当您希望从 JavaScript 将消息记录到控制台时，请使用其中一 `console` 种方法。</span><span class="sxs-lookup"><span data-stu-id="621e6-175">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="621e6-176">每个方法对邮件的格式都不同。</span><span class="sxs-lookup"><span data-stu-id="621e6-176">Each method formats messages differently.</span></span>  

<span data-ttu-id="621e6-177">除了本节中演示的方法外，还有更多方法。</span><span class="sxs-lookup"><span data-stu-id="621e6-177">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="621e6-178">本教程介绍如何浏览其余方法。</span><span class="sxs-lookup"><span data-stu-id="621e6-178">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <a name="view-messages-logged-by-the-browser"></a><span data-ttu-id="621e6-179">查看浏览器记录的消息</span><span class="sxs-lookup"><span data-stu-id="621e6-179">View messages logged by the browser</span></span>  

<span data-ttu-id="621e6-180">浏览器将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="621e6-180">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="621e6-181">当页面出现问题时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="621e6-181">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="621e6-182">选择 **"原因 404"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-182">Choose **Cause 404**.</span></span>  <span data-ttu-id="621e6-183">浏览器记录网络错误的 HTTP 状态代码， `404` 因为页面的 JavaScript 尝试获取不存在的文件。</span><span class="sxs-lookup"><span data-stu-id="621e6-183">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="控制台中出现 404 错误" lightbox="../media/console-cause-404.msft.png":::
       <span data-ttu-id="621e6-185">控制台 `404` 中的 **错误**</span><span class="sxs-lookup"><span data-stu-id="621e6-185">A `404` error in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-186">选择 **"原因错误"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-186">Choose **Cause Error**.</span></span>  <span data-ttu-id="621e6-187">浏览器未记录，因为 JavaScript 尝试更新不存在的 `TypeError` DOM 节点。</span><span class="sxs-lookup"><span data-stu-id="621e6-187">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="控制台中的 TypeError" lightbox="../media/console-cause-error.msft.png":::
       <span data-ttu-id="621e6-189">控制台 `TypeError` 中的\*\*\*\* A</span><span class="sxs-lookup"><span data-stu-id="621e6-189">A `TypeError` in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-190">选择" **日志级别** "下拉列表并启用" **详细"** 选项（如果已禁用）。</span><span class="sxs-lookup"><span data-stu-id="621e6-190">Choose the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="621e6-191">您可以在下一节中了解有关筛选功能的内容。</span><span class="sxs-lookup"><span data-stu-id="621e6-191">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="621e6-192">需要这样做以确保所记录的下一条消息可见。</span><span class="sxs-lookup"><span data-stu-id="621e6-192">You need to do this to make sure that the next message you log is visible.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="621e6-193">如果"默认级别"下拉列表处于禁用状态，可能需要关闭 **控制台** 边栏。</span><span class="sxs-lookup"><span data-stu-id="621e6-193">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span></span>  <span data-ttu-id="621e6-194">按下面的消息源筛选，了解有关控制台边 **栏** 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="621e6-194">Filter by Message Source below for more information about the **Console** Sidebar.</span></span>
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="启用详细日志级别" lightbox="../media/console-cause-error-log-levels.msft.png":::
       <span data-ttu-id="621e6-196">启用详细日志级别</span><span class="sxs-lookup"><span data-stu-id="621e6-196">Enabling the Verbose log level</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-197">选择 **"原因冲突"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-197">Choose **Cause Violation**.</span></span>  <span data-ttu-id="621e6-198">页面在几秒钟后将无响应，然后浏览器将消息记录 `[Violation] 'click' handler took 3000ms` 到控制台。</span><span class="sxs-lookup"><span data-stu-id="621e6-198">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="621e6-199">确切的持续时间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="621e6-199">The exact duration may vary.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="控制台中的冲突" lightbox="../media/console-cause-violation.msft.png":::
       <span data-ttu-id="621e6-201">控制台中的 **冲突**</span><span class="sxs-lookup"><span data-stu-id="621e6-201">A violation in the **Console**</span></span>  
    :::image-end:::  
    
## <a name="filter-messages"></a><span data-ttu-id="621e6-202">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="621e6-202">Filter messages</span></span>  

<span data-ttu-id="621e6-203">在某些网页上，你查看 **控制台** 时收到大量消息。</span><span class="sxs-lookup"><span data-stu-id="621e6-203">On some webpages you review the **Console** get flooded with messages.</span></span>  <span data-ttu-id="621e6-204">DevTools 提供了许多不同的方法来筛选出与当前任务不相关的消息。</span><span class="sxs-lookup"><span data-stu-id="621e6-204">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <a name="filter-by-log-level"></a><span data-ttu-id="621e6-205">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="621e6-205">Filter by log level</span></span>  

<span data-ttu-id="621e6-206">每个 `console` 方法都分配有严重性级别 `Verbose` `Info` ：、、或 `Warning` `Error` 。</span><span class="sxs-lookup"><span data-stu-id="621e6-206">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="621e6-207">例如， `console.log()` 是 `Info` -level 邮件， `console.error()` 而 是 `Error` -level 邮件。</span><span class="sxs-lookup"><span data-stu-id="621e6-207">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="621e6-208">选择"**日志级别**"下拉列表并禁用 **"错误"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-208">Choose the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="621e6-209">当一个级别旁边不再有选中标记时，该级别将被禁用。</span><span class="sxs-lookup"><span data-stu-id="621e6-209">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="621e6-210">`Error`-level 消息将消失。</span><span class="sxs-lookup"><span data-stu-id="621e6-210">The `Error`-level messages disappear.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="在控制台中禁用错误级别的消息" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       <span data-ttu-id="621e6-212">在控制台中禁用错误级别 **的消息**</span><span class="sxs-lookup"><span data-stu-id="621e6-212">Disable Error-level messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-213">再次**选择"日志**级别"下拉列表，然后重新启用 **"错误"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-213">Choose the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="621e6-214">`Error`-level 消息将重新出现。</span><span class="sxs-lookup"><span data-stu-id="621e6-214">The `Error`-level messages reappear.</span></span>  

### <a name="filter-by-text"></a><span data-ttu-id="621e6-215">按文本筛选</span><span class="sxs-lookup"><span data-stu-id="621e6-215">Filter by text</span></span>  

<span data-ttu-id="621e6-216">当只想查看包含确切字符串的邮件时，在"筛选器"文本框中 **键入该字符串** 。</span><span class="sxs-lookup"><span data-stu-id="621e6-216">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="621e6-217">键入 `Dave` 到“**筛选器**”文本框。</span><span class="sxs-lookup"><span data-stu-id="621e6-217">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="621e6-218">所有不包含字符串的邮件 `Dave` 都隐藏。</span><span class="sxs-lookup"><span data-stu-id="621e6-218">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="621e6-219">还可以查看 `Adolescent Irradiated Espionage Tortoises` 标签。</span><span class="sxs-lookup"><span data-stu-id="621e6-219">You may also review the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="621e6-220">这是一个错误。</span><span class="sxs-lookup"><span data-stu-id="621e6-220">That is a bug.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="筛选掉不包含 Dave 的任何邮件" lightbox="../media/console-all-messages-text-filter.msft.png":::
       <span data-ttu-id="621e6-222">筛选掉任何不包含的邮件</span><span class="sxs-lookup"><span data-stu-id="621e6-222">Filter out any message that does not include</span></span> `Dave`  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-223">从 `Dave` " **筛选器"文本框** 中删除。</span><span class="sxs-lookup"><span data-stu-id="621e6-223">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="621e6-224">所有邮件都重新出现。</span><span class="sxs-lookup"><span data-stu-id="621e6-224">All the messages reappear.</span></span>  

### <a name="filter-by-regular-expression"></a><span data-ttu-id="621e6-225">按正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="621e6-225">Filter by regular expression</span></span>  

<span data-ttu-id="621e6-226">当您想要显示包含文本模式（而不是特定字符串）的所有邮件时，请使用 [正则表达式][MDNRegularExpressions]。</span><span class="sxs-lookup"><span data-stu-id="621e6-226">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="621e6-227">键入 `/^[AH]/` 到“**筛选器**”文本框。</span><span class="sxs-lookup"><span data-stu-id="621e6-227">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="621e6-228">在 [RegExr 中][|::ref1::|Main] 键入模式，以说明它正在执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="621e6-228">Type the pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="筛选出任何与模式不匹配的邮件" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       <span data-ttu-id="621e6-230">筛选出与模式不匹配的任何邮件</span><span class="sxs-lookup"><span data-stu-id="621e6-230">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-231">从 `/^[AH]/` " **筛选器"文本框** 中删除。</span><span class="sxs-lookup"><span data-stu-id="621e6-231">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="621e6-232">所有邮件再次可见。</span><span class="sxs-lookup"><span data-stu-id="621e6-232">All messages are visible again.</span></span>  

### <a name="filter-by-message-source"></a><span data-ttu-id="621e6-233">按邮件源筛选</span><span class="sxs-lookup"><span data-stu-id="621e6-233">Filter by message source</span></span>  

<span data-ttu-id="621e6-234">如果只想查看来自特定 URL 的邮件，请使用 **边栏**。</span><span class="sxs-lookup"><span data-stu-id="621e6-234">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="621e6-235">Choose **Show Console Sidebar** \ (![ Show Console Sidebar ](../media/show-console-sidebar-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="621e6-235">Choose **Show Console Sidebar** \(![Show Console Sidebar](../media/show-console-sidebar-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="边栏" lightbox="../media/console-sidebar-all-messages.msft.png":::
       <span data-ttu-id="621e6-237">边栏</span><span class="sxs-lookup"><span data-stu-id="621e6-237">The Sidebar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-238">选择" **展开** \ (![ 展开 ](../media/expand-icon.msft.png) \) "图标旁边的"邮件数"。</span><span class="sxs-lookup"><span data-stu-id="621e6-238">Choose the **Expand** \(![Expand](../media/expand-icon.msft.png)\) icon next to the number of messages.</span></span>  <span data-ttu-id="621e6-239">在下图中，邮件数指示为 **"13 邮件"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-239">In the following figure, the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="621e6-240">**边栏**显示导致记录消息的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="621e6-240">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="621e6-241">例如， `log.js` 导致 11 条消息。</span><span class="sxs-lookup"><span data-stu-id="621e6-241">For example, `log.js` caused 11 messages.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="在边栏中查看消息源" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       <span data-ttu-id="621e6-243">在边栏中查看消息源</span><span class="sxs-lookup"><span data-stu-id="621e6-243">Viewing the source of messages in the Sidebar</span></span>  
    :::image-end:::  
    
### <a name="filter-by-user-messages"></a><span data-ttu-id="621e6-244">按用户消息筛选</span><span class="sxs-lookup"><span data-stu-id="621e6-244">Filter by user messages</span></span>  

<span data-ttu-id="621e6-245">之前，当你选择"日志 **信息**"时，名为 `console.log('Hello, Console!')` 的脚本用于将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="621e6-245">Earlier, when you choose **Log Info**, a script named `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="621e6-246">从 JavaScript 中记录的消息（如下所示）称为 **用户消息**。</span><span class="sxs-lookup"><span data-stu-id="621e6-246">Messages logged from JavaScript like this are named **user messages**.</span></span>  <span data-ttu-id="621e6-247">相反，当你选择 **"原因 404"** 时，浏览器会记录一条 -level 消息，指出未找到请求 `Error` 的资源。</span><span class="sxs-lookup"><span data-stu-id="621e6-247">In contrast, when you choose **Cause 404**, the browser logs an `Error`-level message stating that the requested resource is not found.</span></span>  <span data-ttu-id="621e6-248">类似这样的邮件被视为 **浏览器消息**。</span><span class="sxs-lookup"><span data-stu-id="621e6-248">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="621e6-249">使用 **边栏筛选** 掉浏览器消息，并只显示用户消息。</span><span class="sxs-lookup"><span data-stu-id="621e6-249">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="621e6-250">选择 **"9 个用户消息"。**</span><span class="sxs-lookup"><span data-stu-id="621e6-250">Choose **9 User Messages**.</span></span>  <span data-ttu-id="621e6-251">浏览器消息处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="621e6-251">The browser messages are hidden.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="筛选掉浏览器消息" lightbox="../media/console-sidebar-user-messages.msft.png":::
       <span data-ttu-id="621e6-253">筛选掉浏览器消息</span><span class="sxs-lookup"><span data-stu-id="621e6-253">Filtering out browser messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="621e6-254">选择 **"13 邮件"** 可再次显示所有邮件。</span><span class="sxs-lookup"><span data-stu-id="621e6-254">Choose **13 Messages** to show all messages again.</span></span>  

## <a name="use-the-console-alongside-any-other-tools"></a><span data-ttu-id="621e6-255">将控制台与任何其他工具一同使用</span><span class="sxs-lookup"><span data-stu-id="621e6-255">Use the Console alongside any other tools</span></span>  

<span data-ttu-id="621e6-256">如果要编辑样式，但需要快速检查控制台日志中的某内容，请使用"箱"。</span><span class="sxs-lookup"><span data-stu-id="621e6-256">If you are editing styles, but you need to quickly check the Console log for something, Use the Drawer.</span></span>  

1.  <span data-ttu-id="621e6-257">选择" **元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="621e6-257">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="621e6-258">选择 `Escape`。</span><span class="sxs-lookup"><span data-stu-id="621e6-258">Select `Escape`.</span></span>  <span data-ttu-id="621e6-259">将 **打开** "箱" **中的控制台** 工具。</span><span class="sxs-lookup"><span data-stu-id="621e6-259">The **Console** tool in the **Drawer** opens.</span></span>  <span data-ttu-id="621e6-260">它拥有你在整个教程中一直使用的控制台面板的所有功能。</span><span class="sxs-lookup"><span data-stu-id="621e6-260">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text=""箱"中的控制台工具" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         <span data-ttu-id="621e6-262">" **箱** "中的控制台 **工具**</span><span class="sxs-lookup"><span data-stu-id="621e6-262">The **Console** tool in the **Drawer**</span></span>  
    :::image-end:::  
    
## <a name="see-also"></a><span data-ttu-id="621e6-263">另请参阅</span><span class="sxs-lookup"><span data-stu-id="621e6-263">See also</span></span>  

*   <span data-ttu-id="621e6-264">若要浏览更多与控制台**UI**相关的功能和工作流，请导航到"控制台[参考"。][DevToolsConsoleApi]</span><span class="sxs-lookup"><span data-stu-id="621e6-264">To explore more features and workflows related to the **Console** UI,navigate to [Console Reference][DevToolsConsoleApi].</span></span>  
*   <span data-ttu-id="621e6-265">若要了解有关查看从 JavaScript 记录的消息中演示的所有方法，并浏览本文未涵盖的其他方法，请导航到"控制台 API 参考 `console` [](#view-messages-logged-from-javascript) `console` ["。][DevToolsConsoleReference]</span><span class="sxs-lookup"><span data-stu-id="621e6-265">To learn more about all of the `console` methods demonstrated in [View messages logged from JavaScript](#view-messages-logged-from-javascript) and explore the other `console` methods not covered in this article, navigate to [Console API Reference][DevToolsConsoleReference].</span></span>  
<!--*   Navigate to [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  
     
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="621e6-266">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="621e6-266">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具|Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单菜单运行|Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考|Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "控制台参考|Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "记录消息记录|小故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式|MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "堆栈跟踪 - Wikipedia"  
> [!NOTE]
> <span data-ttu-id="621e6-276">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="621e6-276">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="621e6-277">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="621e6-277">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="621e6-279">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="621e6-279">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
