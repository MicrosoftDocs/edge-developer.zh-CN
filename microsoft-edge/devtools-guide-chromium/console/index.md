---
description: Microsoft Edge DevTools 控制台的主要用途是记录消息和运行 JavaScript。
title: 控制台概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 32272c3f76f715566ced66d11346985dc95dd290
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125263"
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

# 控制台概述  

  

此页面介绍 Microsoft Edge DevTools 控制台如何简化网页开发。  该控制台有2个主要用途： [查看记录的消息](#viewing-logged-messages) 和 [运行 JavaScript](#running-javascript)。  

## 查看已记录的消息  

Web 开发人员通常将消息记录到控制台，以确保其 JavaScript 按预期工作。  若要记录消息，请在 JavaScript 中插入类似的表达式 `console.log('Hello, Console!')` 。  当浏览器运行你的 JavaScript 并看到类似这样的表达式时，它会将消息记录到控制台。  

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
      在下图中， **控制台** 显示加载页面并等待3秒钟的结果。  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="控制台面板" lightbox="../media/console-console-demo.msft.png":::
         **控制台**面板  
      :::image-end:::  
      
      尝试确定哪些代码行导致浏览器记录消息。  
   :::column-end:::
:::row-end:::  

Web 开发人员记录以下2个常规原因的消息。  

*   确保代码按正确的顺序运行。  
*   在某一时间点检查变量的值。  

请参阅 [记录消息入门][DevtoolsConsoleLoggingMessages] ，获取有关日志记录的实际操作体验。  请参阅 [控制台 API 参考][DevToolsConsoleAPI] ，浏览完整的方法列表 `console` 。  方法之间的主要区别是显示正在记录的数据的方式。  

## 运行 JavaScript  

该 **控制台** 也是一种 [复制][WikiREPLoop]。  你可以在 **控制台** 中运行 JavaScript 以与被检查的页面交互。   

:::row:::
   :::column span="":::
      在下图中， **控制台** 显示在 DevTools 主页的旁边。  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="控制台面板" lightbox="../media/devtools-console-empty.msft.png":::
         DevTools 主页旁边的 **控制台** 面板  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      在下图中，使用 **控制台** 更改页面的顶部标题后，将显示相同的页面。
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="控制台面板" lightbox="../media/devtools-console-h1-changed.msft.png":::
         使用 **控制台** 更改页面的顶部标题  
      :::image-end:::  
   :::column-end:::
:::row-end:::

由于**控制台**对页面的[窗口][MDNWindow]具有完全访问权限，因此可以从**控制台**修改页面。  DevTools 具有几个便于检查页面的便利功能。  例如，假设你的 JavaScript 包含一个名为 `hideModal` 的函数。  运行 `debug(hideModal)` 时，在 `hideModal` 您下次运行代码时，它会暂停在第一行。  有关实用工具函数的完整列表的详细信息，请导航到 " [控制台实用工具 API 参考][DevtoolsConsoleUtilitiesDebug]"。  

运行 JavaScript 时，不必与页面交互。  你可以使用该 **控制台** 尝试与页面无关的新代码。  例如，假设你刚刚了解内置的 JavaScript 数组 [映射 ( # B1 ][MDNMap] 方法，并且你想要进行试验。  
**控制台**是试用该函数的好地方。  

有关在 **控制台**中运行 javascript 的更多实际体验，请导航到 [开始运行 javascript][DevtoolsConsoleRunningJavascript]。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleAPI]: ./api.md "控制台 API 参考 |Microsoft 文档"  
[DevtoolsConsoleLoggingMessages]: ./log.md "在控制台中记录邮件的入门 |Microsoft 文档"  
[DevtoolsConsoleRunningJavascript]: ./javascript.md "开始在控制台中运行 JavaScript |Microsoft 文档"  
[DevtoolsConsoleUtilitiesDebug]: ./utilities.md#debug "调试-控制台实用工具 API 参考 |Microsoft 文档"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map " ( # A1 | 的数组MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口 |MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "阅读-评估-"打印循环"-维基百科"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
