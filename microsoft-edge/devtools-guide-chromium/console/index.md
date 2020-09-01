---
title: 控制台概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 45e2eb9d66fa284b1326e7554b6897a1e1747561
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982278"
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





# <span data-ttu-id="38fa1-103">控制台概述</span><span class="sxs-lookup"><span data-stu-id="38fa1-103">Console Overview</span></span>   

  

<span data-ttu-id="38fa1-104">此页面介绍 Microsoft Edge DevTools 控制台如何简化网页开发。</span><span class="sxs-lookup"><span data-stu-id="38fa1-104">This page explains how the Microsoft Edge DevTools Console makes it easier to develop web pages.</span></span>  <span data-ttu-id="38fa1-105">该控制台有2个主要用途： [查看记录的消息](#viewing-logged-messages) 和 [运行 JavaScript](#running-javascript)。</span><span class="sxs-lookup"><span data-stu-id="38fa1-105">The Console has 2 main uses: [viewing logged messages](#viewing-logged-messages) and [running JavaScript](#running-javascript).</span></span>  

## <span data-ttu-id="38fa1-106">查看已记录的消息</span><span class="sxs-lookup"><span data-stu-id="38fa1-106">Viewing logged messages</span></span>   

<span data-ttu-id="38fa1-107">Web 开发人员通常将消息记录到控制台，以确保其 JavaScript 按预期工作。</span><span class="sxs-lookup"><span data-stu-id="38fa1-107">Web developers often log messages to the Console to make sure that their JavaScript is working as expected.</span></span>  <span data-ttu-id="38fa1-108">若要记录消息，请在 JavaScript 中插入类似的表达式 `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="38fa1-108">To log a message, you insert an expression like `console.log('Hello, Console!')` into your JavaScript.</span></span>  <span data-ttu-id="38fa1-109">当浏览器运行你的 JavaScript 并看到类似这样的表达式时，它会将消息记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="38fa1-109">When the browser runs your JavaScript and sees an expression like that, it logs the message to the Console.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="38fa1-110">页面的 HTML 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="38fa1-110">The HTML and JavaScript for the page.</span></span>  
      
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
      <span data-ttu-id="38fa1-111">在下图中， **控制台** 显示加载页面并等待3秒钟的结果。</span><span class="sxs-lookup"><span data-stu-id="38fa1-111">In the following figure, the **Console** displays the results of loading the page and waiting 3 seconds.</span></span>  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="控制台面板" lightbox="../media/console-console-demo.msft.png":::
         <span data-ttu-id="38fa1-113">**控制台**面板</span><span class="sxs-lookup"><span data-stu-id="38fa1-113">The **Console** panel</span></span>  
      :::image-end:::  
      
      <span data-ttu-id="38fa1-114">尝试确定哪些代码行导致浏览器记录消息。</span><span class="sxs-lookup"><span data-stu-id="38fa1-114">Try to determine which lines of code caused the browser to log the messages.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="38fa1-115">Web 开发人员记录以下2个常规原因的消息。</span><span class="sxs-lookup"><span data-stu-id="38fa1-115">Web developers log messages for the following 2 general reasons.</span></span>  

*   <span data-ttu-id="38fa1-116">确保代码按正确的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="38fa1-116">Making sure that code is running in the right order.</span></span>  
*   <span data-ttu-id="38fa1-117">在某一时间点检查变量的值。</span><span class="sxs-lookup"><span data-stu-id="38fa1-117">Inspecting the values of variables at a certain moment in time.</span></span>  

<span data-ttu-id="38fa1-118">请参阅 [记录消息入门][DevtoolsConsoleLoggingMessages] ，获取有关日志记录的实际操作体验。</span><span class="sxs-lookup"><span data-stu-id="38fa1-118">See [Get Started With Logging Messages][DevtoolsConsoleLoggingMessages] to get hands-on experience with logging.</span></span>  <span data-ttu-id="38fa1-119">请参阅 [控制台 API 参考][DevToolsConsoleAPI] ，浏览完整的方法列表 `console` 。</span><span class="sxs-lookup"><span data-stu-id="38fa1-119">See the [Console API Reference][DevToolsConsoleAPI] to browse the full list of `console` methods.</span></span>  <span data-ttu-id="38fa1-120">方法之间的主要区别是显示正在记录的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="38fa1-120">The main difference between the methods is how the data being logged is displayed.</span></span>  

## <span data-ttu-id="38fa1-121">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="38fa1-121">Running JavaScript</span></span>   

<span data-ttu-id="38fa1-122">该 **控制台** 也是一种 [复制][WikiREPLoop]。</span><span class="sxs-lookup"><span data-stu-id="38fa1-122">The **Console** is also a [REPL][WikiREPLoop].</span></span>  <span data-ttu-id="38fa1-123">你可以在 **控制台** 中运行 JavaScript 以与被检查的页面交互。</span><span class="sxs-lookup"><span data-stu-id="38fa1-123">You may run JavaScript in the **Console** to interact with the page being inspected.</span></span>   

:::row:::
   :::column span="":::
      <span data-ttu-id="38fa1-124">在下图中， **控制台** 显示在 DevTools 主页的旁边。</span><span class="sxs-lookup"><span data-stu-id="38fa1-124">In the following figure, the **Console** is shown next to the DevTools homepage.</span></span>  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="DevTools 主页旁边的控制台面板" lightbox="../media/devtools-console-empty.msft.png":::
         <span data-ttu-id="38fa1-126">DevTools 主页旁边的 **控制台** 面板</span><span class="sxs-lookup"><span data-stu-id="38fa1-126">The **Console** panel next to the DevTools homepage</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="38fa1-127">在下图中，使用 **控制台** 更改页面的顶部标题后，将显示相同的页面。</span><span class="sxs-lookup"><span data-stu-id="38fa1-127">In the following figure, the same page is shown after using the **Console** to change the top heading of the page.</span></span>
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="使用控制台更改页面的顶部标题" lightbox="../media/devtools-console-h1-changed.msft.png":::
         <span data-ttu-id="38fa1-129">使用 **控制台** 更改页面的顶部标题</span><span class="sxs-lookup"><span data-stu-id="38fa1-129">Use the **Console** to change the top heading of the page</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="38fa1-130">由于**控制台**对页面的[窗口][MDNWindow]具有完全访问权限，因此可以从**控制台**修改页面。</span><span class="sxs-lookup"><span data-stu-id="38fa1-130">Modifying the page from the **Console** is possible because the **Console** has full access to the [window][MDNWindow] of the page.</span></span>  <span data-ttu-id="38fa1-131">DevTools 具有几个便于检查页面的便利功能。</span><span class="sxs-lookup"><span data-stu-id="38fa1-131">DevTools has a few convenience functions that make it easier to inspect a page.</span></span>  <span data-ttu-id="38fa1-132">例如，假设你的 JavaScript 包含一个名为 `hideModal` 的函数。</span><span class="sxs-lookup"><span data-stu-id="38fa1-132">For example, suppose that your JavaScript contains a function called `hideModal`.</span></span>  <span data-ttu-id="38fa1-133">运行 `debug(hideModal)` 时，在 `hideModal` 您下次运行代码时，它会暂停在第一行。</span><span class="sxs-lookup"><span data-stu-id="38fa1-133">Running `debug(hideModal)` pauses your code on the first line of `hideModal` the next time that you run it.</span></span>  <span data-ttu-id="38fa1-134">有关实用工具函数的完整列表的详细信息，请参阅 [控制台实用工具 API 参考][DevtoolsConsoleUtilitiesDebug]。</span><span class="sxs-lookup"><span data-stu-id="38fa1-134">For more information about the full list of utility functions, see [Console Utilities API Reference][DevtoolsConsoleUtilitiesDebug].</span></span>  

<span data-ttu-id="38fa1-135">运行 JavaScript 时，不必与页面交互。</span><span class="sxs-lookup"><span data-stu-id="38fa1-135">When you run JavaScript you do not have to interact with the page.</span></span>  <span data-ttu-id="38fa1-136">你可以使用该 **控制台** 尝试与页面无关的新代码。</span><span class="sxs-lookup"><span data-stu-id="38fa1-136">You may use the **Console** to try out new code unrelated to the page.</span></span>  <span data-ttu-id="38fa1-137">例如，假设你刚刚了解内置的 JavaScript 数组 [映射 ( # B1 ][MDNMap] 方法，并且你想要进行试验。</span><span class="sxs-lookup"><span data-stu-id="38fa1-137">For example, suppose you just learned about the built-in JavaScript Array [map()][MDNMap] method, and you want to experiment with it.</span></span>  
<span data-ttu-id="38fa1-138">**控制台**是试用该函数的好地方。</span><span class="sxs-lookup"><span data-stu-id="38fa1-138">The **Console** is a good place to try out the function.</span></span>  

<span data-ttu-id="38fa1-139">有关在 **控制台**中运行 javascript 的更多实际体验，请参阅 [运行 javascript 入门][DevtoolsConsoleRunningJavascript]。</span><span class="sxs-lookup"><span data-stu-id="38fa1-139">For more hands-on experience with running JavaScript in the **Console**, see [Get Started With Running JavaScript][DevtoolsConsoleRunningJavascript].</span></span>  

   

  

<!-- links -->  

[DevToolsConsoleAPI]: ./api.md "控制台 API 参考 |Microsoft 文档"  
[DevtoolsConsoleLoggingMessages]: ./log.md "在控制台中记录邮件的入门 |Microsoft 文档"  
[DevtoolsConsoleRunningJavascript]: ./javascript.md "开始在控制台中运行 JavaScript |Microsoft 文档"  
[DevtoolsConsoleUtilitiesDebug]: ./utilities.md#debug "调试-控制台实用工具 API 参考 |Microsoft 文档"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map " ( # A1 | 的数组MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口 |MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "阅读-评估-"打印循环"-维基百科"  

> [!NOTE]
> <span data-ttu-id="38fa1-147">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="38fa1-147">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="38fa1-148">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="38fa1-148">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="38fa1-150">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="38fa1-150">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
