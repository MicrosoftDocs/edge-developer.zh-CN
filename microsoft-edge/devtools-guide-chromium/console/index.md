---
description: The main uses of the Microsoft Edge DevTools Console are logging messages and running JavaScript.
title: Console Overview
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 0cdce953b22d22f9a2bf8048a6eff89388aa6e2e
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993154"
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





# <span data-ttu-id="fb899-104">Console Overview</span><span class="sxs-lookup"><span data-stu-id="fb899-104">Console Overview</span></span>   

  

<span data-ttu-id="fb899-105">This page explains how the Microsoft Edge DevTools Console makes it easier to develop web pages.</span><span class="sxs-lookup"><span data-stu-id="fb899-105">This page explains how the Microsoft Edge DevTools Console makes it easier to develop web pages.</span></span>  <span data-ttu-id="fb899-106">The Console has 2 main uses: [viewing logged messages](#viewing-logged-messages) and [running JavaScript](#running-javascript).</span><span class="sxs-lookup"><span data-stu-id="fb899-106">The Console has 2 main uses: [viewing logged messages](#viewing-logged-messages) and [running JavaScript](#running-javascript).</span></span>  

## <span data-ttu-id="fb899-107">Viewing logged messages</span><span class="sxs-lookup"><span data-stu-id="fb899-107">Viewing logged messages</span></span>   

<span data-ttu-id="fb899-108">Web developers often log messages to the Console to make sure that their JavaScript is working as expected.</span><span class="sxs-lookup"><span data-stu-id="fb899-108">Web developers often log messages to the Console to make sure that their JavaScript is working as expected.</span></span>  <span data-ttu-id="fb899-109">To log a message, you insert an expression like `console.log('Hello, Console!')` into your JavaScript.</span><span class="sxs-lookup"><span data-stu-id="fb899-109">To log a message, you insert an expression like `console.log('Hello, Console!')` into your JavaScript.</span></span>  <span data-ttu-id="fb899-110">When the browser runs your JavaScript and sees an expression like that, it logs the message to the Console.</span><span class="sxs-lookup"><span data-stu-id="fb899-110">When the browser runs your JavaScript and sees an expression like that, it logs the message to the Console.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="fb899-111">The HTML and JavaScript for the page.</span><span class="sxs-lookup"><span data-stu-id="fb899-111">The HTML and JavaScript for the page.</span></span>  
      
      ```html
      <!doctype html>
      <html>
          <head>
              <title>Console Demo</title>
          </head>
          <body>
              <h1>Hello, World!</h1>
              <script>
                  console.log('Loading!');
                  const h1 = document.querySelector('h1');
                  console.log(h1.textContent);
                  console.assert(document.querySelector('h2'), 'h2 not found!');
                  const artists = [
                      { first: 'René', last: 'Magritte' },
                      { first: 'Chaim', last: 'Soutine' },
                      { first: 'Henri', last: 'Matisse' }
                  ];
                  console.table(artists);
                  setTimeout(() => {
                      h1.textContent = 'Hello, Console!';
                      console.log(h1.textContent);
                  }, 3000);
              </script>
          </body>
      </html>
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="fb899-112">In the following figure, the **Console** displays the results of loading the page and waiting 3 seconds.</span><span class="sxs-lookup"><span data-stu-id="fb899-112">In the following figure, the **Console** displays the results of loading the page and waiting 3 seconds.</span></span>  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="The Console panel" lightbox="../media/console-console-demo.msft.png":::
         <span data-ttu-id="fb899-114">The **Console** panel</span><span class="sxs-lookup"><span data-stu-id="fb899-114">The **Console** panel</span></span>  
      :::image-end:::  
      
      <span data-ttu-id="fb899-115">Try to determine which lines of code caused the browser to log the messages.</span><span class="sxs-lookup"><span data-stu-id="fb899-115">Try to determine which lines of code caused the browser to log the messages.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="fb899-116">Web developers log messages for the following 2 general reasons.</span><span class="sxs-lookup"><span data-stu-id="fb899-116">Web developers log messages for the following 2 general reasons.</span></span>  

*   <span data-ttu-id="fb899-117">Making sure that code is running in the right order.</span><span class="sxs-lookup"><span data-stu-id="fb899-117">Making sure that code is running in the right order.</span></span>  
*   <span data-ttu-id="fb899-118">Inspecting the values of variables at a certain moment in time.</span><span class="sxs-lookup"><span data-stu-id="fb899-118">Inspecting the values of variables at a certain moment in time.</span></span>  

<span data-ttu-id="fb899-119">See [Get Started With Logging Messages][DevtoolsConsoleLoggingMessages] to get hands-on experience with logging.</span><span class="sxs-lookup"><span data-stu-id="fb899-119">See [Get Started With Logging Messages][DevtoolsConsoleLoggingMessages] to get hands-on experience with logging.</span></span>  <span data-ttu-id="fb899-120">See the [Console API Reference][DevToolsConsoleAPI] to browse the full list of `console` methods.</span><span class="sxs-lookup"><span data-stu-id="fb899-120">See the [Console API Reference][DevToolsConsoleAPI] to browse the full list of `console` methods.</span></span>  <span data-ttu-id="fb899-121">The main difference between the methods is how the data being logged is displayed.</span><span class="sxs-lookup"><span data-stu-id="fb899-121">The main difference between the methods is how the data being logged is displayed.</span></span>  

## <span data-ttu-id="fb899-122">Running JavaScript</span><span class="sxs-lookup"><span data-stu-id="fb899-122">Running JavaScript</span></span>   

<span data-ttu-id="fb899-123">The **Console** is also a [REPL][WikiREPLoop].</span><span class="sxs-lookup"><span data-stu-id="fb899-123">The **Console** is also a [REPL][WikiREPLoop].</span></span>  <span data-ttu-id="fb899-124">You may run JavaScript in the **Console** to interact with the page being inspected.</span><span class="sxs-lookup"><span data-stu-id="fb899-124">You may run JavaScript in the **Console** to interact with the page being inspected.</span></span>   

:::row:::
   :::column span="":::
      <span data-ttu-id="fb899-125">In the following figure, the **Console** is shown next to the DevTools homepage.</span><span class="sxs-lookup"><span data-stu-id="fb899-125">In the following figure, the **Console** is shown next to the DevTools homepage.</span></span>  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="The Console panel" lightbox="../media/devtools-console-empty.msft.png":::
         <span data-ttu-id="fb899-127">The **Console** panel next to the DevTools homepage</span><span class="sxs-lookup"><span data-stu-id="fb899-127">The **Console** panel next to the DevTools homepage</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="fb899-128">In the following figure, the same page is shown after using the **Console** to change the top heading of the page.</span><span class="sxs-lookup"><span data-stu-id="fb899-128">In the following figure, the same page is shown after using the **Console** to change the top heading of the page.</span></span>
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="The Console panel" lightbox="../media/devtools-console-h1-changed.msft.png":::
         <span data-ttu-id="fb899-130">Use the **Console** to change the top heading of the page</span><span class="sxs-lookup"><span data-stu-id="fb899-130">Use the **Console** to change the top heading of the page</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="fb899-131">Modifying the page from the **Console** is possible because the **Console** has full access to the [window][MDNWindow] of the page.</span><span class="sxs-lookup"><span data-stu-id="fb899-131">Modifying the page from the **Console** is possible because the **Console** has full access to the [window][MDNWindow] of the page.</span></span>  <span data-ttu-id="fb899-132">DevTools has a few convenience functions that make it easier to inspect a page.</span><span class="sxs-lookup"><span data-stu-id="fb899-132">DevTools has a few convenience functions that make it easier to inspect a page.</span></span>  <span data-ttu-id="fb899-133">For example, suppose that your JavaScript contains a function called `hideModal`.</span><span class="sxs-lookup"><span data-stu-id="fb899-133">For example, suppose that your JavaScript contains a function called `hideModal`.</span></span>  <span data-ttu-id="fb899-134">Running `debug(hideModal)` pauses your code on the first line of `hideModal` the next time that you run it.</span><span class="sxs-lookup"><span data-stu-id="fb899-134">Running `debug(hideModal)` pauses your code on the first line of `hideModal` the next time that you run it.</span></span>  <span data-ttu-id="fb899-135">For more information about the full list of utility functions, see [Console Utilities API Reference][DevtoolsConsoleUtilitiesDebug].</span><span class="sxs-lookup"><span data-stu-id="fb899-135">For more information about the full list of utility functions, see [Console Utilities API Reference][DevtoolsConsoleUtilitiesDebug].</span></span>  

<span data-ttu-id="fb899-136">When you run JavaScript you do not have to interact with the page.</span><span class="sxs-lookup"><span data-stu-id="fb899-136">When you run JavaScript you do not have to interact with the page.</span></span>  <span data-ttu-id="fb899-137">You may use the **Console** to try out new code unrelated to the page.</span><span class="sxs-lookup"><span data-stu-id="fb899-137">You may use the **Console** to try out new code unrelated to the page.</span></span>  <span data-ttu-id="fb899-138">For example, suppose you just learned about the built-in JavaScript Array [map()][MDNMap] method, and you want to experiment with it.</span><span class="sxs-lookup"><span data-stu-id="fb899-138">For example, suppose you just learned about the built-in JavaScript Array [map()][MDNMap] method, and you want to experiment with it.</span></span>  
<span data-ttu-id="fb899-139">The **Console** is a good place to try out the function.</span><span class="sxs-lookup"><span data-stu-id="fb899-139">The **Console** is a good place to try out the function.</span></span>  

<span data-ttu-id="fb899-140">For more hands-on experience with running JavaScript in the **Console**, see [Get Started With Running JavaScript][DevtoolsConsoleRunningJavascript].</span><span class="sxs-lookup"><span data-stu-id="fb899-140">For more hands-on experience with running JavaScript in the **Console**, see [Get Started With Running JavaScript][DevtoolsConsoleRunningJavascript].</span></span>  

   

  

<!-- links -->  

[DevToolsConsoleAPI]: ./api.md "Console API Reference | Microsoft Docs"  
[DevtoolsConsoleLoggingMessages]: ./log.md "Get Started With Logging Messages In The Console | Microsoft Docs"  
[DevtoolsConsoleRunningJavascript]: ./javascript.md "Get Started With Running JavaScript In The Console | Microsoft Docs"  
[DevtoolsConsoleUtilitiesDebug]: ./utilities.md#debug "debug - Console Utilities API Reference | Microsoft Docs"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map "Array.prototype.map() | MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "Window | MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read–eval–print loop - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="fb899-148">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="fb899-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fb899-149">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="fb899-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="fb899-151">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="fb899-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
