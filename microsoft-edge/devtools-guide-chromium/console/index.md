---
description: Microsoft Edge DevTools 控制台的主要用途是记录消息并运行 JavaScript。
title: 控制台概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 496caa4d304d9511d4b1c341846f377899ba4597
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399118"
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

# <a name="console-overview"></a><span data-ttu-id="a4408-104">控制台概述</span><span class="sxs-lookup"><span data-stu-id="a4408-104">Console overview</span></span>  

  

<span data-ttu-id="a4408-105">此页面介绍了 Microsoft Edge DevTools 控制台如何更轻松地开发网页。</span><span class="sxs-lookup"><span data-stu-id="a4408-105">This page explains how the Microsoft Edge DevTools Console makes it easier to develop web pages.</span></span>  <span data-ttu-id="a4408-106">控制台**有**两个主要用途：[查看记录的消息](#viewing-logged-messages)和[运行 JavaScript。](#running-javascript)</span><span class="sxs-lookup"><span data-stu-id="a4408-106">The **Console** has 2 main uses: [viewing logged messages](#viewing-logged-messages) and [running JavaScript](#running-javascript).</span></span>  

## <a name="viewing-logged-messages"></a><span data-ttu-id="a4408-107">查看记录的消息</span><span class="sxs-lookup"><span data-stu-id="a4408-107">Viewing logged messages</span></span>  

<span data-ttu-id="a4408-108">Web 开发人员通常会将消息记录到控制台，以确保其 JavaScript 正常工作。</span><span class="sxs-lookup"><span data-stu-id="a4408-108">Web developers often log messages to the Console to make sure that their JavaScript is working as expected.</span></span>  <span data-ttu-id="a4408-109">若要记录消息，请将类似表达式插入 `console.log('Hello, Console!')` JavaScript 中。</span><span class="sxs-lookup"><span data-stu-id="a4408-109">To log a message, you insert an expression like `console.log('Hello, Console!')` into your JavaScript.</span></span>  <span data-ttu-id="a4408-110">当浏览器运行 JavaScript 并处理类似表达式时，浏览器会向控制台记录 **消息**。</span><span class="sxs-lookup"><span data-stu-id="a4408-110">When the browser runs your JavaScript and processes an expression like it, the browser logs the message to the **Console**.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="a4408-111">页面的 HTML 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="a4408-111">The HTML and JavaScript for the page.</span></span>  
      
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
      <span data-ttu-id="a4408-112">下图中 **，控制台显示** 加载页面并等待 3 秒的结果。</span><span class="sxs-lookup"><span data-stu-id="a4408-112">In the following figure, the **Console** displays the results of loading the page and waiting 3 seconds.</span></span>  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="控制台面板" lightbox="../media/console-console-demo.msft.png":::
         <span data-ttu-id="a4408-114">控制台**工具**</span><span class="sxs-lookup"><span data-stu-id="a4408-114">The **Console** tool</span></span>  
      :::image-end:::  
      
      <span data-ttu-id="a4408-115">尝试确定哪些代码行导致浏览器记录消息。</span><span class="sxs-lookup"><span data-stu-id="a4408-115">Try to determine which lines of code caused the browser to log the messages.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="a4408-116">Web 开发人员出于以下 2 个一般原因记录消息。</span><span class="sxs-lookup"><span data-stu-id="a4408-116">Web developers log messages for the following 2 general reasons.</span></span>  

*   <span data-ttu-id="a4408-117">确保代码按正确的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="a4408-117">Making sure that code is running in the right order.</span></span>  
*   <span data-ttu-id="a4408-118">检查某个时刻的变量值。</span><span class="sxs-lookup"><span data-stu-id="a4408-118">Inspecting the values of variables at a certain moment in time.</span></span>  

<span data-ttu-id="a4408-119">若要获得日志记录的动手体验，请导航到"[日志记录消息入门"。][DevtoolsConsoleLoggingMessages]</span><span class="sxs-lookup"><span data-stu-id="a4408-119">To get hands-on experience with logging, navigate to [Get Started With Logging Messages][DevtoolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="a4408-120">若要浏览方法的完整 `console` 列表，请导航到控制台 [API 参考][DevToolsConsoleAPI]。</span><span class="sxs-lookup"><span data-stu-id="a4408-120">To browse the full list of `console` methods, navigate to the [Console API Reference][DevToolsConsoleAPI].</span></span>  <span data-ttu-id="a4408-121">方法之间的主要区别在于所记录数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="a4408-121">The main difference between the methods is how the data being logged is displayed.</span></span>  

## <a name="running-javascript"></a><span data-ttu-id="a4408-122">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="a4408-122">Running JavaScript</span></span>  

<span data-ttu-id="a4408-123">控制台**也是**一个[REPL。][WikiREPLoop]</span><span class="sxs-lookup"><span data-stu-id="a4408-123">The **Console** is also a [REPL][WikiREPLoop].</span></span>  <span data-ttu-id="a4408-124">您可以在控制台中运行 JavaScript **以与** 正在检查的页面进行交互。</span><span class="sxs-lookup"><span data-stu-id="a4408-124">You may run JavaScript in the **Console** to interact with the page being inspected.</span></span>   

:::row:::
   :::column span="":::
      <span data-ttu-id="a4408-125">下图中， **控制台显示在** DevTools 主页旁边。</span><span class="sxs-lookup"><span data-stu-id="a4408-125">In the following figure, the **Console** is shown next to the DevTools homepage.</span></span>  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="DevTools 主页旁边的控制台工具" lightbox="../media/devtools-console-empty.msft.png":::
         <span data-ttu-id="a4408-127">DevTools 主页旁边的控制台工具</span><span class="sxs-lookup"><span data-stu-id="a4408-127">The **Console** tool next to the DevTools homepage</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="a4408-128">在下图中，使用控制台更改页面顶部标题后将显示同 一页。</span><span class="sxs-lookup"><span data-stu-id="a4408-128">In the following figure, the same page is shown after using the **Console** to change the top heading of the page.</span></span>
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="使用控制台更改页面顶部标题" lightbox="../media/devtools-console-h1-changed.msft.png":::
         <span data-ttu-id="a4408-130">使用 **控制台** 更改页面顶部标题</span><span class="sxs-lookup"><span data-stu-id="a4408-130">Use the **Console** to change the top heading of the page</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="a4408-131">从控制台修改页面 **是可能的** ，因为 **控制台** 具有对页面 [窗口][MDNWindow] 的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="a4408-131">Modifying the page from the **Console** is possible because the **Console** has full access to the [window][MDNWindow] of the page.</span></span>  <span data-ttu-id="a4408-132">DevTools 具有一些方便功能，可更轻松地检查页面。</span><span class="sxs-lookup"><span data-stu-id="a4408-132">DevTools has a few convenience functions that make it easier to inspect a page.</span></span>  <span data-ttu-id="a4408-133">例如，假设你的 JavaScript 包含一个称为 `hideModal` .的函数。</span><span class="sxs-lookup"><span data-stu-id="a4408-133">For example, suppose that your JavaScript contains a function called `hideModal`.</span></span>  <span data-ttu-id="a4408-134">运行 `debug(hideModal)` 将暂停下一次运行时代码的第 `hideModal` 一行。</span><span class="sxs-lookup"><span data-stu-id="a4408-134">Running `debug(hideModal)` pauses your code on the first line of `hideModal` the next time that you run it.</span></span>  <span data-ttu-id="a4408-135">有关实用程序函数的完整列表详细信息，请导航到 [控制台实用工具 API 参考][DevtoolsConsoleUtilitiesDebug]。</span><span class="sxs-lookup"><span data-stu-id="a4408-135">For more information about the full list of utility functions, navigate to [Console Utilities API Reference][DevtoolsConsoleUtilitiesDebug].</span></span>  

<span data-ttu-id="a4408-136">运行 JavaScript 时，不需要与页面交互。</span><span class="sxs-lookup"><span data-stu-id="a4408-136">When you run JavaScript you do not have to interact with the page.</span></span>  <span data-ttu-id="a4408-137">您可以使用控制台 **来** 尝试与页面无关的新代码。</span><span class="sxs-lookup"><span data-stu-id="a4408-137">You may use the **Console** to try out new code unrelated to the page.</span></span>  <span data-ttu-id="a4408-138">例如，假设你刚刚了解了内置的 JavaScript 数组映射 [ () ][MDNMap] 方法，并且你想要试验它。</span><span class="sxs-lookup"><span data-stu-id="a4408-138">For example, suppose you just learned about the built-in JavaScript Array [map()][MDNMap] method, and you want to experiment with it.</span></span>  
<span data-ttu-id="a4408-139">**控制台**是试用该函数的一个好位置。</span><span class="sxs-lookup"><span data-stu-id="a4408-139">The **Console** is a good place to try out the function.</span></span>  

<span data-ttu-id="a4408-140">有关在控制台中运行 JavaScript 的更多实践体验 **，请导航**到"运行 JavaScript 入门["。][DevtoolsConsoleRunningJavascript]</span><span class="sxs-lookup"><span data-stu-id="a4408-140">For more hands-on experience with running JavaScript in the **Console**, navigate to [Get Started With Running JavaScript][DevtoolsConsoleRunningJavascript].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="a4408-141">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="a4408-141">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleAPI]: ./api.md "控制台 API 参考|Microsoft Docs"  
[DevtoolsConsoleLoggingMessages]: ./log.md "开始在控制台中记录|Microsoft Docs"  
[DevtoolsConsoleRunningJavascript]: ./javascript.md "开始在控制台中运行 JavaScript |Microsoft Docs"  
[DevtoolsConsoleUtilitiesDebug]: ./utilities.md#debug "debug - 控制台实用工具 API 参考|Microsoft Docs"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map "Array.prototype.map () |MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口|MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval–print 循环 - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="a4408-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a4408-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a4408-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="a4408-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="a4408-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a4408-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
