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

# <a name="console-overview"></a>控制台概述  

  

此页面介绍了 Microsoft Edge DevTools 控制台如何更轻松地开发网页。  控制台**有**两个主要用途：[查看记录的消息](#viewing-logged-messages)和[运行 JavaScript。](#running-javascript)  

## <a name="viewing-logged-messages"></a>查看记录的消息  

Web 开发人员通常会将消息记录到控制台，以确保其 JavaScript 正常工作。  若要记录消息，请将类似表达式插入 `console.log('Hello, Console!')` JavaScript 中。  当浏览器运行 JavaScript 并处理类似表达式时，浏览器会向控制台记录 **消息**。  

:::row:::
   :::column span="":::
      页面的 HTML 和 JavaScript。  
      
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
      下图中 **，控制台显示** 加载页面并等待 3 秒的结果。  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="控制台面板" lightbox="../media/console-console-demo.msft.png":::
         控制台**工具**  
      :::image-end:::  
      
      尝试确定哪些代码行导致浏览器记录消息。  
   :::column-end:::
:::row-end:::  

Web 开发人员出于以下 2 个一般原因记录消息。  

*   确保代码按正确的顺序运行。  
*   检查某个时刻的变量值。  

若要获得日志记录的动手体验，请导航到"[日志记录消息入门"。][DevtoolsConsoleLoggingMessages]  若要浏览方法的完整 `console` 列表，请导航到控制台 [API 参考][DevToolsConsoleAPI]。  方法之间的主要区别在于所记录数据的显示方式。  

## <a name="running-javascript"></a>运行 JavaScript  

控制台**也是**一个[REPL。][WikiREPLoop]  您可以在控制台中运行 JavaScript **以与** 正在检查的页面进行交互。   

:::row:::
   :::column span="":::
      下图中， **控制台显示在** DevTools 主页旁边。  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="DevTools 主页旁边的控制台工具" lightbox="../media/devtools-console-empty.msft.png":::
         DevTools 主页旁边的控制台工具****  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      在下图中，使用控制台更改页面顶部标题后将显示同**** 一页。
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="使用控制台更改页面顶部标题" lightbox="../media/devtools-console-h1-changed.msft.png":::
         使用 **控制台** 更改页面顶部标题  
      :::image-end:::  
   :::column-end:::
:::row-end:::

从控制台修改页面 **是可能的** ，因为 **控制台** 具有对页面 [窗口][MDNWindow] 的完全访问权限。  DevTools 具有一些方便功能，可更轻松地检查页面。  例如，假设你的 JavaScript 包含一个称为 `hideModal` .的函数。  运行 `debug(hideModal)` 将暂停下一次运行时代码的第 `hideModal` 一行。  有关实用程序函数的完整列表详细信息，请导航到 [控制台实用工具 API 参考][DevtoolsConsoleUtilitiesDebug]。  

运行 JavaScript 时，不需要与页面交互。  您可以使用控制台 **来** 尝试与页面无关的新代码。  例如，假设你刚刚了解了内置的 JavaScript 数组映射 [ () ][MDNMap] 方法，并且你想要试验它。  
**控制台**是试用该函数的一个好位置。  

有关在控制台中运行 JavaScript 的更多实践体验 **，请导航**到"运行 JavaScript 入门["。][DevtoolsConsoleRunningJavascript]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
