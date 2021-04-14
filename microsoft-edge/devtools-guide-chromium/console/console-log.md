---
description: 如何在 Microsoft Edge DevTools 控制台中记录消息并运行 JavaScript。
title: 在控制台工具中记录消息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: d48a48de7b261a628ac99f58680deb119268a980
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483356"
---
# <a name="log-messages-in-the-console-tool"></a>在控制台工具中记录消息  

自浏览器开始提供开发人员工具以来， **控制台** 一直很常用。  原因很简单。  

*   在大多数编程课程，你将学习输出某种打印命令，以深入了解发生的情况。  

在 DevTools 之前，你只能使用 `alert()` 或 `document.write()` 语句在浏览器中调试。  

如果要在控制台中记录 **信息**，可以使用多种方法。  查看 API 参考中所有 [可用的方法][DevtoolsConsoleApi]。  以下代码段列出了最重要的方法。  

```javascript
// prints the text to the console as  a log message
console.log('This is a log message')
// prints the text to the console as an informational message
console.info('This is some information') 
// prints the text to the console as an error message
console.error('This is an error')
// prints the text to the console as a warning
console.warn('This is a warning') 
```  

复制并粘贴控制台中的上一个代码**** 段或导航到控制台[消息示例：日志、信息、错误和警告][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml]。  在控制台中尝试任何方法时****，和 方法似乎执行相同的操作，而 和 方法在消息旁边显示图标以及检查消息堆栈跟踪 `log()` `info()` `error()` `warn()` 的方法。 [][WikiStackTrace]  

:::image type="complex" source="../media/console-log-examples.msft.png" alt-text="控制台显示来自不同日志 API 的消息" lightbox="../media/console-log-examples.msft.png":::
   控制台 **显示** 来自不同日志 API 的消息  
:::image-end:::  

但是，对于不同的日志任务，仍建议使用 和 ，因为这样可以在控制台 中 `info()` `log()` 使用类型 [进行筛选][DevtoolsConsoleConsoleFilters]。  

## <a name="different-types-of-logs"></a>不同类型的日志  

你可以向控制台发送任何有效的 JavaScript 或 DOM 引用，而不是日志 **文本**。  控制台 **很** 美观，它确定发送它的类型。  然后，它为你提供可能的最佳表示形式。  复制并粘贴控制台中的以下代码 **段或显示** 结果，导航到控制台 [消息示例：记录不同类型的][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml]。  

```javascript
let x = 2;
// logs the value of x
console.log(x);
// logs the name x and value of x
console.log({x})   
// logs a DOM reference  
console.log(document.querySelector('body'));
// logs an Object
console.log({"type":"life", "meaning": 42});
let w3techs = ['HTML', 'CSS', 'SVG', 'MathML'];
// logs an Array
console.log(w3techs);
```  

每个结果以不同方式显示。  使用三角形切换信息并更详细地分析每个信息。  变量周围的大括号字符是避免出现很多日志消息的一个好技巧，其中仅获取值，但不知道该值 `{}` `x` 源自何处。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types.msft.png" alt-text="在控制台中记录不同类型的变量" lightbox="../media/console-log-types.msft.png":::
         在控制台中记录不同类型的 **变量**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types-expanded.msft.png" alt-text="使用扩展的额外信息在控制台中记录不同类型的变量" lightbox="../media/console-log-types-expanded.msft.png":::
         使用扩展的额外信息在 **控制台中记录** 不同类型的变量  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="format-and-convert-values-with-specifiers"></a>使用说明符设置值的格式和转换值

所有日志方法的一个特殊功能是，您可以在日志消息中使用说明符。  说明符是日志消息的一部分，以百分比符号 \ (\) 字符开始，并允许您以不同格式记录特定值， `%` 甚至转换每个值。  

*   `%s` 日志为字符串
*   `%i` 或 `%d` 日志为 Integers
*   `%f` 日志作为浮点值
*   `%o` 日志作为可展开的 DOM 元素
*   `%O` 日志作为可展开的 JavaScript 对象
*   `%c` 允许您使用 CSS 设置邮件样式

```javascript
// logs "10x console developer"
console.log('%ix %s developer', 10, 'console');
// logs PI => 3.141592653589793
console.log(Math.PI); 
// logs PI as an integer = 3
console.log('%i', Math.PI); 
// logs the webpage body as a DOM node
console.log('%o', document.body); 
// logs the body of the webpage as a JavaScript object with all properties
console.log('%O', document.body); 
// Displays the message as red and big
console.log('%cImportant message follows','color:red;font-size:40px');
```  

第一个示例显示，说明符的替换顺序是字符串后的参数顺序。  若要显示结果，请复制并粘贴控制台中的上一个代码**** 段或导航到控制台[消息示例：使用说明符记录][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml]。  展开日志中的信息以显示 和 之间的巨大 `%o` 差异 `%O` 。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers.msft.png" alt-text="使用说明符记录并转换值" lightbox="../media/console-log-specifiers.msft.png":::
         使用说明符记录并转换值  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers-expanded.msft.png" alt-text="展开结果可显示 %O 之间的差值和 %o说明符 - 正文显示为可展开的 DOM 节点或网页正文上所有 JavaScript 属性的完整列表" lightbox="../media/console-log-specifiers-expanded.msft.png":::
        Expand 结果显示 和 说明符之间的差异 - 正文显示为可展开的 DOM 节点，或显示为网页正文上所有 `%O` `%o` JavaScript 属性的完整列表  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="group-log-messages"></a>组日志消息

如果记录许多信息，可以使用 和 方法在控制台 中将日志消息显示为可展开 `group` `groupCollapsed` 和可折叠 **的组**。  可以嵌套和命名组，使数据更易于理解。  

```javascript
console.group("Passengers: Heart of Gold");
console.log('Zaphod');
console.log('Trillian');
console.log('Ford');
console.log('Arthur');
console.log('Marvin');
console.groupCollapsed("Hidden");
console.log('(Frankie & Benjy)');
console.groupEnd("Hidden");
console.groupEnd("Passengers: Heart of Gold");

let technologies = {
  "Standards": ["HTML", "CSS", "SVG", "ECMAScript"],
  "Others": ["jQuery", "Markdown", "Textile", "Sass", "Pug"]
}
for (tech in technologies) {
  console.groupCollapsed(tech);
  technologies[tech].forEach(t => console.log(t));
  console.groupEnd(tech);
}
```  

此外，第二个示例还可以选择生成组名称。  若要显示结果，请复制并粘贴控制台中的上一个代码**** 段或导航到控制台[消息示例：对日志进行分组][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml]。  可以展开和折叠每个部分。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups.msft.png" alt-text="将大量值记录为组" lightbox="../media/console-log-groups.msft.png":::
         将大量值记录为组  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups-expanded.msft.png" alt-text="可以展开和折叠每个组" lightbox="../media/console-log-groups-expanded.msft.png":::
        可以展开和折叠每个组  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="display-complex-data-as-tables"></a>将复杂数据显示为表  

该方法不会将复杂数据记录为可折叠和可展开的对象，而是记录为可以使用不同标题 `console.table()` 进行排序的表。  排序表使用户更容易查看信息。  若要在示例中显示它，请导航到控制台 [消息示例：使用表][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml]。

```javascript
let technologies = {
  "Standards": ["HTML", "CSS", "SVG", "ECMAScript"],
  "Others": ["jQuery", "Markdown", "Textile", "Sass", "Pug"]
}
// log technologies as an object
console.log(technologies);
// display technologies as a table
console.table(technologies);

// get the dimensions of the webpage body
let bodyDimensions = document.body.getBoundingClientRect();
// display dimensions as an object
console.log(bodyDimensions);
// display dimensions as a table
console.table(bodyDimensions);
```  

:::image type="complex" source="../media/console-log-table.msft.png" alt-text="使用 console.table 显示数据，使其更易于阅读" lightbox="../media/console-log-table.msft.png":::
   使用 显示 `console.table` 数据，使其更易于阅读
:::image-end:::  

的输出 `console.table` 不仅具有显示在控制台 中的表 **格式**。    例如，如果将表格复制并粘贴到 Excel、Word 或其他支持表格数据的产品中，则结构保持不变。  

<!--  The output of `console.table` has a table format not only when it displays in the **Console**.  For example, copy and paste a table in Excel, Word, or any other products that support tabular data.  -->  

如果数据具有命名参数，则该方法还允许您为每个属性指定一个列，以 `console.table()` `Array` 作为第二个参数显示。  以下示例显示如何指定一个可读的列数组。  

```javascript
// get all the h1, p and script elements 
let contentElements = document.querySelectorAll(':is(h1,p,script)');
// display the elements as an unfiltered table 
console.table(contentElements)
// display only relevant columns 
console.table(contentElements,['nodeName', 'innerText', 'offsetHeight'])
```  

:::image type="complex" source="../media/console-log-table-filtered.msft.png" alt-text="console.table 显示并提供要显示为第二个参数的属性数组的筛选器信息" lightbox="../media/console-log-table-filtered.msft.png":::
   显示和提供要显示为第二个参数 `console.table` 的属性数组的筛选器信息  
:::image-end:::  

您可能会尝试将日志方法用作调试网页的主要方式，因为日志方法易于使用。  请考虑任何请求 `console.log()` 的结果。  Live 产品不应使用用于调试的任何日志。  它可能会向用户显示内部信息。  控制台中创建的噪音 **非常** 强烈。  当您使用 [断点调试][DevtoolsJavascriptBreakpoints] 或 [Live Expressions][DevtoolsConsoleLiveExpressions]时，您可能会发现您的工作流更有效，并且您获得更好的结果。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  
[DevtoolsConsoleConsoleFilters]: ./console-filters.md "筛选控制台消息|Microsoft Docs"  
[DevtoolsConsoleLiveExpressions]: ./live-expressions.md "使用 Live Expressions 应用程序监视 JavaScript 中的|Microsoft Docs"  

[DevtoolsJavascriptBreakpoints]: ../javascript/breakpoints.md "如何在 Microsoft Edge 开发工具中使用断点暂停代码 | Microsoft Doc"  

[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-examples.html "控制台消息示例：日志、信息、错误和警告|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-types.html "控制台消息示例：记录不同类型的|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-groups.html "控制台消息示例：对日志进行|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-specifiers.html "控制台消息示例：使用说明符记录|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-table.html "控制台消息示例：使用表|GitHub"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "堆栈跟踪|Wikipedia"  
