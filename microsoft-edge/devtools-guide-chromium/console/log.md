---
description: Learn how to log messages to the Console.
title: Get Started With Logging Messages In The Console
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
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





# <span data-ttu-id="3e034-104">Get Started With Logging Messages In The Console</span><span class="sxs-lookup"><span data-stu-id="3e034-104">Get Started With Logging Messages In The Console</span></span>   



<span data-ttu-id="3e034-105">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span><span class="sxs-lookup"><span data-stu-id="3e034-105">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="Messages in the Console" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   <span data-ttu-id="3e034-107">Messages in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-107">Messages in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="3e034-108">This tutorial is intended to be completed in order.</span><span class="sxs-lookup"><span data-stu-id="3e034-108">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="3e034-109">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span><span class="sxs-lookup"><span data-stu-id="3e034-109">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <span data-ttu-id="3e034-110">Set up the demo and DevTools</span><span class="sxs-lookup"><span data-stu-id="3e034-110">Set up the demo and DevTools</span></span>   

<span data-ttu-id="3e034-111">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span><span class="sxs-lookup"><span data-stu-id="3e034-111">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="3e034-112">When you physically follow along, you are more likely to remember the workflows later.</span><span class="sxs-lookup"><span data-stu-id="3e034-112">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="3e034-113">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Log Examples** to open in a new tab.</span><span class="sxs-lookup"><span data-stu-id="3e034-113">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="3e034-114">Console Log Examples</span><span class="sxs-lookup"><span data-stu-id="3e034-114">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="Messages in the Console" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  <span data-ttu-id="3e034-115">Focus the demo and then press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span><span class="sxs-lookup"><span data-stu-id="3e034-115">Focus the demo and then press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="3e034-116">By default DevTools opens to the right of the demo.</span><span class="sxs-lookup"><span data-stu-id="3e034-116">By default DevTools opens to the right of the demo.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="Messages in the Console" lightbox="../media/console-example-devtools-right-console.msft.png":::
             <span data-ttu-id="3e034-118">DevTools opens to the right of the demo</span><span class="sxs-lookup"><span data-stu-id="3e034-118">DevTools opens to the right of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="3e034-119">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span><span class="sxs-lookup"><span data-stu-id="3e034-119">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="Messages in the Console" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             <span data-ttu-id="3e034-121">DevTools docked to the bottom of the demo</span><span class="sxs-lookup"><span data-stu-id="3e034-121">DevTools docked to the bottom of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="3e034-122">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span><span class="sxs-lookup"><span data-stu-id="3e034-122">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="Messages in the Console" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             <span data-ttu-id="3e034-124">Browser in a separate window</span><span class="sxs-lookup"><span data-stu-id="3e034-124">Browser in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="3e034-125">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span><span class="sxs-lookup"><span data-stu-id="3e034-125">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="Messages in the Console" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             <span data-ttu-id="3e034-127">DevTools undocked in a separate window</span><span class="sxs-lookup"><span data-stu-id="3e034-127">DevTools undocked in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="3e034-128">View messages logged from JavaScript</span><span class="sxs-lookup"><span data-stu-id="3e034-128">View messages logged from JavaScript</span></span>   

<span data-ttu-id="3e034-129">Most messages that you see in the Console come from the web developers who wrote the JavaScript of the page.</span><span class="sxs-lookup"><span data-stu-id="3e034-129">Most messages that you see in the Console come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="3e034-130">The goal of this section is to introduce you to the different message types that you are likely to see in the Console, and explain how you may log each message type yourself from your own JavaScript.</span><span class="sxs-lookup"><span data-stu-id="3e034-130">The goal of this section is to introduce you to the different message types that you are likely to see in the Console, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="3e034-131">Click the **Log Info** button in the demo.</span><span class="sxs-lookup"><span data-stu-id="3e034-131">Click the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="3e034-132">gets logged to the Console.</span><span class="sxs-lookup"><span data-stu-id="3e034-132">gets logged to the Console.</span></span>
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="Messages in the Console" lightbox="../media/console-log-info.msft.png":::
       <span data-ttu-id="3e034-134">The **Console** after clicking **Log Info**</span><span class="sxs-lookup"><span data-stu-id="3e034-134">The **Console** after clicking **Log Info**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-135">Next to the `Hello, Console!` message in the Console click **log.js:2**.</span><span class="sxs-lookup"><span data-stu-id="3e034-135">Next to the `Hello, Console!` message in the Console click **log.js:2**.</span></span>  <span data-ttu-id="3e034-136">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span><span class="sxs-lookup"><span data-stu-id="3e034-136">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="3e034-137">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span><span class="sxs-lookup"><span data-stu-id="3e034-137">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="Messages in the Console" lightbox="../media/console-sources-logjs.msft.png":::
       <span data-ttu-id="3e034-139">DevTools opens the **Sources** panel after you click</span><span class="sxs-lookup"><span data-stu-id="3e034-139">DevTools opens the **Sources** panel after you click</span></span> `log.js:2`  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-140">Navigate back to the **Console** using any of the following workflows:</span><span class="sxs-lookup"><span data-stu-id="3e034-140">Navigate back to the **Console** using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="3e034-141">Click the **Console** tab.</span><span class="sxs-lookup"><span data-stu-id="3e034-141">Click the **Console** tab.</span></span>  
    *   <span data-ttu-id="3e034-142">Press `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) until the Console panel is in focus.</span><span class="sxs-lookup"><span data-stu-id="3e034-142">Press `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) until the Console panel is in focus.</span></span>  
    *   <span data-ttu-id="3e034-143">[Open the Command Menu][DevToolsCommandMenu], start typing `Console`, select the **Show Console Panel** command, and then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="3e034-143">[Open the Command Menu][DevToolsCommandMenu], start typing `Console`, select the **Show Console Panel** command, and then press `Enter`.</span></span>  
    
1.  <span data-ttu-id="3e034-144">Click the **Log Warning** button in the demo.</span><span class="sxs-lookup"><span data-stu-id="3e034-144">Click the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="3e034-145">gets logged to the Console.</span><span class="sxs-lookup"><span data-stu-id="3e034-145">gets logged to the Console.</span></span>  <span data-ttu-id="3e034-146">Messages formatted like this are warnings.</span><span class="sxs-lookup"><span data-stu-id="3e034-146">Messages formatted like this are warnings.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="Messages in the Console" lightbox="../media/console-log-warning.msft.png":::
       <span data-ttu-id="3e034-148">The **Console** after you click **Log Warning**</span><span class="sxs-lookup"><span data-stu-id="3e034-148">The **Console** after you click **Log Warning**</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="3e034-149">If you want to see the code that caused a message to get logged a certain way, click on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span><span class="sxs-lookup"><span data-stu-id="3e034-149">If you want to see the code that caused a message to get logged a certain way, click on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="3e034-150">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon in front of `Abandon Hope All Ye Who Enter`.</span><span class="sxs-lookup"><span data-stu-id="3e034-150">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="3e034-151">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span><span class="sxs-lookup"><span data-stu-id="3e034-151">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="Messages in the Console" lightbox="../media/console-log-warning-expanded.msft.png":::
       <span data-ttu-id="3e034-153">A stack trace</span><span class="sxs-lookup"><span data-stu-id="3e034-153">A stack trace</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="3e034-154">The stack trace is telling you that a function named `logWarning` was called, which in turn called a function named `quoteDante`.</span><span class="sxs-lookup"><span data-stu-id="3e034-154">The stack trace is telling you that a function named `logWarning` was called, which in turn called a function named `quoteDante`.</span></span>  <span data-ttu-id="3e034-155">In other words, the call that happened first is at the bottom of the stack trace.</span><span class="sxs-lookup"><span data-stu-id="3e034-155">In other words, the call that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="3e034-156">You may log stack traces at any time by calling `console.trace()`.</span><span class="sxs-lookup"><span data-stu-id="3e034-156">You may log stack traces at any time by calling `console.trace()`.</span></span>  

1.  <span data-ttu-id="3e034-157">Click **Log Error**.</span><span class="sxs-lookup"><span data-stu-id="3e034-157">Click **Log Error**.</span></span>  <span data-ttu-id="3e034-158">The following error message gets logged:</span><span class="sxs-lookup"><span data-stu-id="3e034-158">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="Messages in the Console" lightbox="../media/console-log-error.msft.png":::
       <span data-ttu-id="3e034-160">An error message</span><span class="sxs-lookup"><span data-stu-id="3e034-160">An error message</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-161">Click **Log Table**.</span><span class="sxs-lookup"><span data-stu-id="3e034-161">Click **Log Table**.</span></span>  <span data-ttu-id="3e034-162">A table about famous artists gets logged to the Console.</span><span class="sxs-lookup"><span data-stu-id="3e034-162">A table about famous artists gets logged to the Console.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3e034-163">The `birthday` column is only populated for one row.</span><span class="sxs-lookup"><span data-stu-id="3e034-163">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="3e034-164">Review the code to determine why that is.</span><span class="sxs-lookup"><span data-stu-id="3e034-164">Review the code to determine why that is.</span></span>
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="Messages in the Console" lightbox="../media/console-log-table.msft.png":::
       <span data-ttu-id="3e034-166">A table in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-166">A table in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-167">Click **Log Group**.</span><span class="sxs-lookup"><span data-stu-id="3e034-167">Click **Log Group**.</span></span>  <span data-ttu-id="3e034-168">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span><span class="sxs-lookup"><span data-stu-id="3e034-168">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="Messages in the Console" lightbox="../media/console-log-group.msft.png":::
       <span data-ttu-id="3e034-170">A group of messages in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-170">A group of messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-171">Click **Log Custom**.</span><span class="sxs-lookup"><span data-stu-id="3e034-171">Click **Log Custom**.</span></span>  <span data-ttu-id="3e034-172">A message with a red border and blue background gets logged to the Console.</span><span class="sxs-lookup"><span data-stu-id="3e034-172">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="Messages in the Console" lightbox="../media/console-log-custom.msft.png":::
       <span data-ttu-id="3e034-174">A message with custom formatting in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-174">A message with custom formatting in the **Console**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="3e034-175">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span><span class="sxs-lookup"><span data-stu-id="3e034-175">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="3e034-176">Each method formats messages differently.</span><span class="sxs-lookup"><span data-stu-id="3e034-176">Each method formats messages differently.</span></span>  

<span data-ttu-id="3e034-177">There are even more methods than what has been demonstrated in this section.</span><span class="sxs-lookup"><span data-stu-id="3e034-177">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="3e034-178">This tutorial shows you how to explore the rest of the methods.</span><span class="sxs-lookup"><span data-stu-id="3e034-178">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <span data-ttu-id="3e034-179">View messages logged by the browser</span><span class="sxs-lookup"><span data-stu-id="3e034-179">View messages logged by the browser</span></span>   

<span data-ttu-id="3e034-180">The browser logs messages to the Console, too.</span><span class="sxs-lookup"><span data-stu-id="3e034-180">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="3e034-181">This usually happens when there is a problem with the page.</span><span class="sxs-lookup"><span data-stu-id="3e034-181">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="3e034-182">Click **Cause 404**.</span><span class="sxs-lookup"><span data-stu-id="3e034-182">Click **Cause 404**.</span></span>  <span data-ttu-id="3e034-183">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span><span class="sxs-lookup"><span data-stu-id="3e034-183">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="Messages in the Console" lightbox="../media/console-cause-404.msft.png":::
       <span data-ttu-id="3e034-185">A `404` error in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-185">A `404` error in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-186">Click **Cause Error**.</span><span class="sxs-lookup"><span data-stu-id="3e034-186">Click **Cause Error**.</span></span>  <span data-ttu-id="3e034-187">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span><span class="sxs-lookup"><span data-stu-id="3e034-187">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="Messages in the Console" lightbox="../media/console-cause-error.msft.png":::
       <span data-ttu-id="3e034-189">A `TypeError` in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-189">A `TypeError` in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-190">Click the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span><span class="sxs-lookup"><span data-stu-id="3e034-190">Click the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="3e034-191">You learn more about filtering in the next section.</span><span class="sxs-lookup"><span data-stu-id="3e034-191">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="3e034-192">You need to do this to make sure that the next message you log is visible.</span><span class="sxs-lookup"><span data-stu-id="3e034-192">You need to do this to make sure that the next message you log is visible.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3e034-193">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span><span class="sxs-lookup"><span data-stu-id="3e034-193">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span></span>  <span data-ttu-id="3e034-194">Filter by Message Source below for more information about the **Console** Sidebar.</span><span class="sxs-lookup"><span data-stu-id="3e034-194">Filter by Message Source below for more information about the **Console** Sidebar.</span></span>
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="Messages in the Console" lightbox="../media/console-cause-error-log-levels.msft.png":::
       <span data-ttu-id="3e034-196">Enabling the Verbose log level</span><span class="sxs-lookup"><span data-stu-id="3e034-196">Enabling the Verbose log level</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-197">Click **Cause Violation**.</span><span class="sxs-lookup"><span data-stu-id="3e034-197">Click **Cause Violation**.</span></span>  <span data-ttu-id="3e034-198">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span><span class="sxs-lookup"><span data-stu-id="3e034-198">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="3e034-199">The exact duration may vary.</span><span class="sxs-lookup"><span data-stu-id="3e034-199">The exact duration may vary.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="Messages in the Console" lightbox="../media/console-cause-violation.msft.png":::
       <span data-ttu-id="3e034-201">A violation in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-201">A violation in the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3e034-202">Filter messages</span><span class="sxs-lookup"><span data-stu-id="3e034-202">Filter messages</span></span>   

<span data-ttu-id="3e034-203">On some pages you see the Console get flooded with messages.</span><span class="sxs-lookup"><span data-stu-id="3e034-203">On some pages you see the Console get flooded with messages.</span></span>  <span data-ttu-id="3e034-204">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span><span class="sxs-lookup"><span data-stu-id="3e034-204">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <span data-ttu-id="3e034-205">Filter by log level</span><span class="sxs-lookup"><span data-stu-id="3e034-205">Filter by log level</span></span>   

<span data-ttu-id="3e034-206">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span><span class="sxs-lookup"><span data-stu-id="3e034-206">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="3e034-207">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span><span class="sxs-lookup"><span data-stu-id="3e034-207">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="3e034-208">Click the **Log Levels** dropdown and disable **Errors**.</span><span class="sxs-lookup"><span data-stu-id="3e034-208">Click the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="3e034-209">A level is disabled when there is no longer a checkmark next to it.</span><span class="sxs-lookup"><span data-stu-id="3e034-209">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="3e034-210">The `Error`-level messages disappear.</span><span class="sxs-lookup"><span data-stu-id="3e034-210">The `Error`-level messages disappear.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="Messages in the Console" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       <span data-ttu-id="3e034-212">Disabling Error-level messages in the **Console**</span><span class="sxs-lookup"><span data-stu-id="3e034-212">Disabling Error-level messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-213">Click the **Log Levels** dropdown again and re-enable **Errors**.</span><span class="sxs-lookup"><span data-stu-id="3e034-213">Click the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="3e034-214">The `Error`-level messages reappear.</span><span class="sxs-lookup"><span data-stu-id="3e034-214">The `Error`-level messages reappear.</span></span>  

### <span data-ttu-id="3e034-215">Filter by text</span><span class="sxs-lookup"><span data-stu-id="3e034-215">Filter by text</span></span>   

<span data-ttu-id="3e034-216">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span><span class="sxs-lookup"><span data-stu-id="3e034-216">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="3e034-217">Type `Dave` into the **Filter** text box.</span><span class="sxs-lookup"><span data-stu-id="3e034-217">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="3e034-218">All messages that do not include the string `Dave` are hidden.</span><span class="sxs-lookup"><span data-stu-id="3e034-218">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="3e034-219">You might also see the `Adolescent Irradiated Espionage Tortoises` label.</span><span class="sxs-lookup"><span data-stu-id="3e034-219">You might also see the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="3e034-220">That is a bug.</span><span class="sxs-lookup"><span data-stu-id="3e034-220">That is a bug.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="Messages in the Console" lightbox="../media/console-all-messages-text-filter.msft.png":::
       <span data-ttu-id="3e034-222">Filtering out any message that does not include</span><span class="sxs-lookup"><span data-stu-id="3e034-222">Filtering out any message that does not include</span></span> `Dave`  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-223">Delete `Dave` from the **Filter** text box.</span><span class="sxs-lookup"><span data-stu-id="3e034-223">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="3e034-224">All the messages reappear.</span><span class="sxs-lookup"><span data-stu-id="3e034-224">All the messages reappear.</span></span>  

### <span data-ttu-id="3e034-225">Filter by regular expression</span><span class="sxs-lookup"><span data-stu-id="3e034-225">Filter by regular expression</span></span>   

<span data-ttu-id="3e034-226">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span><span class="sxs-lookup"><span data-stu-id="3e034-226">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="3e034-227">Type `/^[AH]/` into the **Filter** text box.</span><span class="sxs-lookup"><span data-stu-id="3e034-227">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="3e034-228">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span><span class="sxs-lookup"><span data-stu-id="3e034-228">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="Messages in the Console" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       <span data-ttu-id="3e034-230">Filtering out any message that does not match the pattern</span><span class="sxs-lookup"><span data-stu-id="3e034-230">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-231">Delete `/^[AH]/` from the **Filter** text box.</span><span class="sxs-lookup"><span data-stu-id="3e034-231">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="3e034-232">All messages are visible again.</span><span class="sxs-lookup"><span data-stu-id="3e034-232">All messages are visible again.</span></span>  

### <span data-ttu-id="3e034-233">Filter by message source</span><span class="sxs-lookup"><span data-stu-id="3e034-233">Filter by message source</span></span>   

<span data-ttu-id="3e034-234">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span><span class="sxs-lookup"><span data-stu-id="3e034-234">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="3e034-235">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\).</span><span class="sxs-lookup"><span data-stu-id="3e034-235">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\).</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="Messages in the Console" lightbox="../media/console-sidebar-all-messages.msft.png":::
       <span data-ttu-id="3e034-237">The Sidebar</span><span class="sxs-lookup"><span data-stu-id="3e034-237">The Sidebar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-238">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon next to the number of messages.</span><span class="sxs-lookup"><span data-stu-id="3e034-238">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon next to the number of messages.</span></span>  <span data-ttu-id="3e034-239">In the following figure, the number of messages is indicated as **13 Messages**.</span><span class="sxs-lookup"><span data-stu-id="3e034-239">In the following figure, the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="3e034-240">The **Sidebar** shows a list of URLs that caused messages to be logged.</span><span class="sxs-lookup"><span data-stu-id="3e034-240">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="3e034-241">For example, `log.js` caused 11 messages.</span><span class="sxs-lookup"><span data-stu-id="3e034-241">For example, `log.js` caused 11 messages.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="Messages in the Console" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       <span data-ttu-id="3e034-243">Viewing the source of messages in the Sidebar</span><span class="sxs-lookup"><span data-stu-id="3e034-243">Viewing the source of messages in the Sidebar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="3e034-244">Filter by user messages</span><span class="sxs-lookup"><span data-stu-id="3e034-244">Filter by user messages</span></span>   

<span data-ttu-id="3e034-245">Earlier, when you clicked **Log Info**, a script called `console.log('Hello, Console!')` in order to log the message to the Console.</span><span class="sxs-lookup"><span data-stu-id="3e034-245">Earlier, when you clicked **Log Info**, a script called `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="3e034-246">Messages logged from JavaScript like this are called **user messages**.</span><span class="sxs-lookup"><span data-stu-id="3e034-246">Messages logged from JavaScript like this are called **user messages**.</span></span>  <span data-ttu-id="3e034-247">In contrast, when you clicked **Cause 404**, the browser logged an `Error`-level message stating that the requested resource could not be found.</span><span class="sxs-lookup"><span data-stu-id="3e034-247">In contrast, when you clicked **Cause 404**, the browser logged an `Error`-level message stating that the requested resource could not be found.</span></span>  <span data-ttu-id="3e034-248">Messages like that are considered **browser messages**.</span><span class="sxs-lookup"><span data-stu-id="3e034-248">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="3e034-249">Use the **Sidebar** to filter out browser messages and only show user messages.</span><span class="sxs-lookup"><span data-stu-id="3e034-249">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="3e034-250">Click **9 User Messages**.</span><span class="sxs-lookup"><span data-stu-id="3e034-250">Click **9 User Messages**.</span></span>  <span data-ttu-id="3e034-251">The browser messages are hidden.</span><span class="sxs-lookup"><span data-stu-id="3e034-251">The browser messages are hidden.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="Messages in the Console" lightbox="../media/console-sidebar-user-messages.msft.png":::
       <span data-ttu-id="3e034-253">Filtering out browser messages</span><span class="sxs-lookup"><span data-stu-id="3e034-253">Filtering out browser messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3e034-254">Click **13 Messages** to show all messages again.</span><span class="sxs-lookup"><span data-stu-id="3e034-254">Click **13 Messages** to show all messages again.</span></span>  

## <span data-ttu-id="3e034-255">Use the Console alongside any other panel</span><span class="sxs-lookup"><span data-stu-id="3e034-255">Use the Console alongside any other panel</span></span>   

<span data-ttu-id="3e034-256">What if you are editing styles, but you need to quickly check the Console log for something?</span><span class="sxs-lookup"><span data-stu-id="3e034-256">What if you are editing styles, but you need to quickly check the Console log for something?</span></span> <span data-ttu-id="3e034-257">Use the Drawer.</span><span class="sxs-lookup"><span data-stu-id="3e034-257">Use the Drawer.</span></span>  

1.  <span data-ttu-id="3e034-258">Click the **Elements** tab.</span><span class="sxs-lookup"><span data-stu-id="3e034-258">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="3e034-259">Press `Escape`.</span><span class="sxs-lookup"><span data-stu-id="3e034-259">Press `Escape`.</span></span>  <span data-ttu-id="3e034-260">The Console tab of the **Drawer** opens.</span><span class="sxs-lookup"><span data-stu-id="3e034-260">The Console tab of the **Drawer** opens.</span></span>  <span data-ttu-id="3e034-261">It has all of the features of the Console panel that you have been using throughout this tutorial.</span><span class="sxs-lookup"><span data-stu-id="3e034-261">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="Messages in the Console" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         <span data-ttu-id="3e034-263">The **Console** tab in the **Drawer**</span><span class="sxs-lookup"><span data-stu-id="3e034-263">The **Console** tab in the **Drawer**</span></span>  
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

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \(Chromium\) developer tools | Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "Run commands with the Microsoft Edge DevTools Command menu | Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "Change Microsoft Edge DevTools placement | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "Console API reference | Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "Console reference | Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "Get Started With Logging Messages | Glitch"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "Regular Expressions | MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "Stack trace - Wikipedia"  


> [!NOTE]
> <span data-ttu-id="3e034-273">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3e034-273">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3e034-274">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="3e034-274">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3e034-276">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span><span class="sxs-lookup"><span data-stu-id="3e034-276">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
