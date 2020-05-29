---
title: 控制台概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6062afb929a5d763c095d4915a2960993bc5ab4c
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601782"
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

  

此页面介绍 Microsoft Edge DevTools 控制台如何简化网页开发。  该控制台有2个主要用途：[查看记录的消息](#viewing-logged-messages)和[运行 JavaScript](#running-javascript)。  

## 查看已记录的消息   

Web 开发人员通常将消息记录到控制台，以确保其 JavaScript 按预期工作。  若要记录消息，请在 JavaScript 中插入类似的表达式 `console.log('Hello, Console!')` 。  当浏览器运行你的 JavaScript 并看到类似这样的表达式时，它会将消息记录到控制台。  例如，假设你正在编写页面的 HTML 和 JavaScript：  

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
        {
          first: 'René',
          last: 'Magritte'
        },
        {
          first: 'Chaim',
          last: 'Soutine'
        },
        {
          first: 'Henri',
          last: 'Matisse'
        }
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

[图 1](#figure-1)显示了加载页面并等待3秒钟后控制台的外观。  尝试确定哪些代码行导致浏览器记录消息。  

> ##### 图 1  
> 控制台面板  
> ![控制台面板][ImageConsole]  

Web 开发人员记录以下两个常规原因的消息：  

*   确保代码按正确的顺序运行。  
*   在某一时间点检查变量的值。  

请参阅[记录消息入门][DevtoolsConsoleLoggingMessages]，获取有关日志记录的实际操作体验。  请参阅[控制台 API 参考][DevToolsConsoleAPI]，浏览完整的方法列表 `console` 。  方法之间的主要区别是显示正在记录的数据的方式。  

## 运行 JavaScript   

该控制台也是一种[复制][WikiREPLoop]。  你可以在控制台中运行 JavaScript 以与被检查的页面交互。  例如，[图 2](#figure-2)显示了 DevTools 主页旁边的控制台，[图 3](#figure-3)显示了使用控制台更改页面顶部标题后的同一页面。  

> ##### 图 2  
> DevTools 主页旁边的控制台面板  
> ![DevTools 主页旁边的控制台面板][ImageConsoleOverview]  

> ##### 图 3  
> 使用控制台更改页面的顶部标题  
> ![使用控制台更改页面的顶部标题][ImageConsoleChangeTitle]  

由于控制台对页面的[窗口][MDNWindow]具有完全访问权限，因此可以从控制台修改页面。  DevTools 具有几个便于检查页面的便利功能。  例如，假设你的 JavaScript 包含一个名为 `hideModal` 的函数。  运行 `debug(hideModal)` 时，在 `hideModal` 您下次运行代码时，它会暂停在第一行。  有关实用工具函数的完整列表，请参阅[控制台实用工具 API 参考][DevtoolsConsoleUtilitiesDebug]。  

运行 JavaScript 时，不必与页面交互。  你可以使用该控制台尝试与页面无关的新代码。  例如，假设你刚刚了解内置的 JavaScript 数组[映射（）][MDNMap]方法，并且你想要对其进行试验。  
**控制台**是试用该函数的好地方。  

请参阅[开始运行 javascript][ImageConsoleChangeTitle]以获取有关在控制台中运行 javascript 的实际体验。  

   

  

<!-- image links -->  

[ImageConsole]: /microsoft-edge/devtools-guide-chromium/media/console-console-demo.msft.png "图1：控制台面板"  
[ImageConsoleChangeTitle]: /microsoft-edge/devtools-guide-chromium/media/devtools-console-h1-changed.msft.png "图3：使用控制台更改页面的顶部标题"  
[ImageConsoleOverview]: /microsoft-edge/devtools-guide-chromium/media/devtools-console-empty.msft.png "图2： DevTools 主页旁边的控制台面板"  

<!-- links -->  

[DevToolsConsoleAPI]: /microsoft-edge/devtools-guide-chromium/console/api "控制台 API 参考"  
[DevtoolsConsoleLoggingMessages]: /microsoft-edge/devtools-guide-chromium/console/log "在控制台中记录消息入门"  
[DevtoolsConsoleRunningJavascript]: /microsoft-edge/devtools-guide-chromium/console/javascript "开始在控制台中运行 JavaScript"  
[DevtoolsConsoleUtilitiesDebug]: /microsoft-edge/devtools-guide-chromium/console/utilities#debug "调试-控制台实用工具 API 参考"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map "数组 .map （） |MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "窗口 |MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "阅读-评估-"打印循环"-维基百科"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
