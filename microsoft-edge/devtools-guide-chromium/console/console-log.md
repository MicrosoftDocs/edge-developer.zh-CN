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
# <a name="log-messages-in-the-console-tool"></a><span data-ttu-id="9dc37-104">在控制台工具中记录消息</span><span class="sxs-lookup"><span data-stu-id="9dc37-104">Log messages in the Console tool</span></span>  

<span data-ttu-id="9dc37-105">自浏览器开始提供开发人员工具以来， **控制台** 一直很常用。</span><span class="sxs-lookup"><span data-stu-id="9dc37-105">Ever since browsers started to offer developer tools, the **Console** is a favorite.</span></span>  <span data-ttu-id="9dc37-106">原因很简单。</span><span class="sxs-lookup"><span data-stu-id="9dc37-106">The reason is simple.</span></span>  

*   <span data-ttu-id="9dc37-107">在大多数编程课程，你将学习输出某种打印命令，以深入了解发生的情况。</span><span class="sxs-lookup"><span data-stu-id="9dc37-107">In most programming courses, you learn to output some kind of print command to gain insights about what happens.</span></span>  

<span data-ttu-id="9dc37-108">在 DevTools 之前，你只能使用 `alert()` 或 `document.write()` 语句在浏览器中调试。</span><span class="sxs-lookup"><span data-stu-id="9dc37-108">Before the DevTools, you were limited to an `alert()` or `document.write()` statement to debug in the browser.</span></span>  

<span data-ttu-id="9dc37-109">如果要在控制台中记录 **信息**，可以使用多种方法。</span><span class="sxs-lookup"><span data-stu-id="9dc37-109">If you want to log information in the **Console**, lots of methods are available to you.</span></span>  <span data-ttu-id="9dc37-110">查看 API 参考中所有 [可用的方法][DevtoolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="9dc37-110">Review all of available methods in the [API reference][DevtoolsConsoleApi].</span></span>  <span data-ttu-id="9dc37-111">以下代码段列出了最重要的方法。</span><span class="sxs-lookup"><span data-stu-id="9dc37-111">The following code snippet lists the most important methods.</span></span>  

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

<span data-ttu-id="9dc37-112">复制并粘贴控制台中的上一个代码\*\*\*\* 段或导航到控制台[消息示例：日志、信息、错误和警告][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml]。</span><span class="sxs-lookup"><span data-stu-id="9dc37-112">Copy and paste the previous code snippet in the **Console** or navigate to [Console messages examples: log, info, error, and warn][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml].</span></span>  <span data-ttu-id="9dc37-113">在控制台中尝试任何方法时\*\*\*\*，和 方法似乎执行相同的操作，而 和 方法在消息旁边显示图标以及检查消息堆栈跟踪 `log()` `info()` `error()` `warn()` 的方法。 [][WikiStackTrace]</span><span class="sxs-lookup"><span data-stu-id="9dc37-113">When you try any method in the **Console**, the `log()` and `info()` methods seem to do the same thing, while the `error()` and `warn()` methods display an icon next to the message and a way to inspect the [stack trace][WikiStackTrace] of the message.</span></span>  

:::image type="complex" source="../media/console-log-examples.msft.png" alt-text="控制台显示来自不同日志 API 的消息" lightbox="../media/console-log-examples.msft.png":::
   <span data-ttu-id="9dc37-115">控制台 **显示** 来自不同日志 API 的消息</span><span class="sxs-lookup"><span data-stu-id="9dc37-115">The **Console** displays the messages from different log APIs</span></span>  
:::image-end:::  

<span data-ttu-id="9dc37-116">但是，对于不同的日志任务，仍建议使用 和 ，因为这样可以在控制台 中 `info()` `log()` 使用类型 [进行筛选][DevtoolsConsoleConsoleFilters]。</span><span class="sxs-lookup"><span data-stu-id="9dc37-116">It is, however, still a good idea to use `info()` and `log()` for different log tasks as that allows you to [filter using type in the Console][DevtoolsConsoleConsoleFilters].</span></span>  

## <a name="different-types-of-logs"></a><span data-ttu-id="9dc37-117">不同类型的日志</span><span class="sxs-lookup"><span data-stu-id="9dc37-117">Different types of logs</span></span>  

<span data-ttu-id="9dc37-118">你可以向控制台发送任何有效的 JavaScript 或 DOM 引用，而不是日志 **文本**。</span><span class="sxs-lookup"><span data-stu-id="9dc37-118">Instead of log text you may send any valid JavaScript or DOM references to the **Console**.</span></span>  <span data-ttu-id="9dc37-119">控制台 **很** 美观，它确定发送它的类型。</span><span class="sxs-lookup"><span data-stu-id="9dc37-119">The **Console** is elegant and it determines the type that you send it.</span></span>  <span data-ttu-id="9dc37-120">然后，它为你提供可能的最佳表示形式。</span><span class="sxs-lookup"><span data-stu-id="9dc37-120">It then gives you the best possible representation.</span></span>  <span data-ttu-id="9dc37-121">复制并粘贴控制台中的以下代码 **段或显示** 结果，导航到控制台 [消息示例：记录不同类型的][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml]。</span><span class="sxs-lookup"><span data-stu-id="9dc37-121">Copy and paste the following code snippet in the **Console** or to display the results, navigate to [Console messages examples: logging different types][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml].</span></span>  

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

<span data-ttu-id="9dc37-122">每个结果以不同方式显示。</span><span class="sxs-lookup"><span data-stu-id="9dc37-122">Each result is displayed in a different way.</span></span>  <span data-ttu-id="9dc37-123">使用三角形切换信息并更详细地分析每个信息。</span><span class="sxs-lookup"><span data-stu-id="9dc37-123">Use the triangles to toggle the information and analyze each one in more detail.</span></span>  <span data-ttu-id="9dc37-124">变量周围的大括号字符是避免出现很多日志消息的一个好技巧，其中仅获取值，但不知道该值 `{}` `x` 源自何处。</span><span class="sxs-lookup"><span data-stu-id="9dc37-124">The curly brace characters `{}` around the `x` variable are a nice little trick to avoid lots of log messages where you only get a value but you don't know where it originated.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types.msft.png" alt-text="在控制台中记录不同类型的变量" lightbox="../media/console-log-types.msft.png":::
         <span data-ttu-id="9dc37-126">在控制台中记录不同类型的 **变量**</span><span class="sxs-lookup"><span data-stu-id="9dc37-126">Log variables of different types in the **Console**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types-expanded.msft.png" alt-text="使用扩展的额外信息在控制台中记录不同类型的变量" lightbox="../media/console-log-types-expanded.msft.png":::
         <span data-ttu-id="9dc37-128">使用扩展的额外信息在 **控制台中记录** 不同类型的变量</span><span class="sxs-lookup"><span data-stu-id="9dc37-128">Log variables of different types in the **Console** with expanded extra information</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="format-and-convert-values-with-specifiers"></a><span data-ttu-id="9dc37-129">使用说明符设置值的格式和转换值</span><span class="sxs-lookup"><span data-stu-id="9dc37-129">Format and convert values with specifiers</span></span>

<span data-ttu-id="9dc37-130">所有日志方法的一个特殊功能是，您可以在日志消息中使用说明符。</span><span class="sxs-lookup"><span data-stu-id="9dc37-130">A special feature of all the log methods is that you may use specifiers in your log message.</span></span>  <span data-ttu-id="9dc37-131">说明符是日志消息的一部分，以百分比符号 \ (\) 字符开始，并允许您以不同格式记录特定值， `%` 甚至转换每个值。</span><span class="sxs-lookup"><span data-stu-id="9dc37-131">Specifiers are part of a log message and start with a percentage sign \(`%`\) character and allow you to log certain values in different formats and even convert each.</span></span>  

*   `%s` <span data-ttu-id="9dc37-132">日志为字符串</span><span class="sxs-lookup"><span data-stu-id="9dc37-132">logs as Strings</span></span>
*   `%i` <span data-ttu-id="9dc37-133">或 `%d` 日志为 Integers</span><span class="sxs-lookup"><span data-stu-id="9dc37-133">or `%d` logs as Integers</span></span>
*   `%f` <span data-ttu-id="9dc37-134">日志作为浮点值</span><span class="sxs-lookup"><span data-stu-id="9dc37-134">logs as a floating-point value</span></span>
*   `%o` <span data-ttu-id="9dc37-135">日志作为可展开的 DOM 元素</span><span class="sxs-lookup"><span data-stu-id="9dc37-135">logs as an expandable DOM element</span></span>
*   `%O` <span data-ttu-id="9dc37-136">日志作为可展开的 JavaScript 对象</span><span class="sxs-lookup"><span data-stu-id="9dc37-136">logs as an expandable JavaScript object</span></span>
*   `%c` <span data-ttu-id="9dc37-137">允许您使用 CSS 设置邮件样式</span><span class="sxs-lookup"><span data-stu-id="9dc37-137">allows you to style you message with CSS</span></span>

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

<span data-ttu-id="9dc37-138">第一个示例显示，说明符的替换顺序是字符串后的参数顺序。</span><span class="sxs-lookup"><span data-stu-id="9dc37-138">The first example displays that the order of replacement of specifiers is the parameter order following the string.</span></span>  <span data-ttu-id="9dc37-139">若要显示结果，请复制并粘贴控制台中的上一个代码\*\*\*\* 段或导航到控制台[消息示例：使用说明符记录][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml]。</span><span class="sxs-lookup"><span data-stu-id="9dc37-139">To display the results, copy and paste the previous code snippet in the **Console** or navigate to [Console messages examples: Logging with specifiers][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml].</span></span>  <span data-ttu-id="9dc37-140">展开日志中的信息以显示 和 之间的巨大 `%o` 差异 `%O` 。</span><span class="sxs-lookup"><span data-stu-id="9dc37-140">Expand the information in the log to display the huge difference between `%o` and `%O`.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers.msft.png" alt-text="使用说明符记录并转换值" lightbox="../media/console-log-specifiers.msft.png":::
         <span data-ttu-id="9dc37-142">使用说明符记录并转换值</span><span class="sxs-lookup"><span data-stu-id="9dc37-142">Use specifiers to log and convert values</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers-expanded.msft.png" alt-text="展开结果可显示 %O 之间的差值和 %o说明符 - 正文显示为可展开的 DOM 节点或网页正文上所有 JavaScript 属性的完整列表" lightbox="../media/console-log-specifiers-expanded.msft.png":::
        <span data-ttu-id="9dc37-144">Expand 结果显示 和 说明符之间的差异 - 正文显示为可展开的 DOM 节点，或显示为网页正文上所有 `%O` `%o` JavaScript 属性的完整列表</span><span class="sxs-lookup"><span data-stu-id="9dc37-144">Expand the results displays the difference between the `%O` and `%o` specifier - the body is either displayed as an expandable DOM node or as a full list of all JavaScript properties on the webpage body</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="group-log-messages"></a><span data-ttu-id="9dc37-145">组日志消息</span><span class="sxs-lookup"><span data-stu-id="9dc37-145">Group log messages</span></span>

<span data-ttu-id="9dc37-146">如果记录许多信息，可以使用 和 方法在控制台 中将日志消息显示为可展开 `group` `groupCollapsed` 和可折叠 **的组**。</span><span class="sxs-lookup"><span data-stu-id="9dc37-146">If you log much information, you may use the `group` and `groupCollapsed` methods to display log messages as expandable and collapsible groups in the **Console**.</span></span>  <span data-ttu-id="9dc37-147">可以嵌套和命名组，使数据更易于理解。</span><span class="sxs-lookup"><span data-stu-id="9dc37-147">Groups may be nested and named to make the data much easier to understand.</span></span>  

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

<span data-ttu-id="9dc37-148">此外，第二个示例还可以选择生成组名称。</span><span class="sxs-lookup"><span data-stu-id="9dc37-148">Also in the second example, the group names may be optionally generated.</span></span>  <span data-ttu-id="9dc37-149">若要显示结果，请复制并粘贴控制台中的上一个代码\*\*\*\* 段或导航到控制台[消息示例：对日志进行分组][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml]。</span><span class="sxs-lookup"><span data-stu-id="9dc37-149">To display the results, copy and paste the previous code snippet in the **Console** or navigate to [Console messages examples: grouping logs][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml].</span></span>  <span data-ttu-id="9dc37-150">可以展开和折叠每个部分。</span><span class="sxs-lookup"><span data-stu-id="9dc37-150">You may expand and collapse each of the sections.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups.msft.png" alt-text="将大量值记录为组" lightbox="../media/console-log-groups.msft.png":::
         <span data-ttu-id="9dc37-152">将大量值记录为组</span><span class="sxs-lookup"><span data-stu-id="9dc37-152">Log lots of values as groups</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups-expanded.msft.png" alt-text="可以展开和折叠每个组" lightbox="../media/console-log-groups-expanded.msft.png":::
        <span data-ttu-id="9dc37-154">可以展开和折叠每个组</span><span class="sxs-lookup"><span data-stu-id="9dc37-154">Each group may be expanded and collapsed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="display-complex-data-as-tables"></a><span data-ttu-id="9dc37-155">将复杂数据显示为表</span><span class="sxs-lookup"><span data-stu-id="9dc37-155">Display complex data as tables</span></span>  

<span data-ttu-id="9dc37-156">该方法不会将复杂数据记录为可折叠和可展开的对象，而是记录为可以使用不同标题 `console.table()` 进行排序的表。</span><span class="sxs-lookup"><span data-stu-id="9dc37-156">The `console.table()` method logs complex data not as a collapsible and expandable object, but as a table that you may sort using different headers.</span></span>  <span data-ttu-id="9dc37-157">排序表使用户更容易查看信息。</span><span class="sxs-lookup"><span data-stu-id="9dc37-157">A sorted table makes it much easier for people to review the information.</span></span>  <span data-ttu-id="9dc37-158">若要在示例中显示它，请导航到控制台 [消息示例：使用表][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml]。</span><span class="sxs-lookup"><span data-stu-id="9dc37-158">To display it in an example, navigate to [Console messages examples: Using table][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml].</span></span>

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
   <span data-ttu-id="9dc37-160">使用 显示 `console.table` 数据，使其更易于阅读</span><span class="sxs-lookup"><span data-stu-id="9dc37-160">Display data with `console.table` to make it much easier to read</span></span>
:::image-end:::  

<span data-ttu-id="9dc37-161">的输出 `console.table` 不仅具有显示在控制台 中的表 **格式**。</span><span class="sxs-lookup"><span data-stu-id="9dc37-161">The output of `console.table` has a table format not only when it displays in the **Console**.</span></span>    <span data-ttu-id="9dc37-162">例如，如果将表格复制并粘贴到 Excel、Word 或其他支持表格数据的产品中，则结构保持不变。</span><span class="sxs-lookup"><span data-stu-id="9dc37-162">For example, if you copy and paste a table into Excel, Word, or any other product that supports tabular data, the structure remains intact.</span></span>  

<!--  The output of `console.table` has a table format not only when it displays in the **Console**.  For example, copy and paste a table in Excel, Word, or any other products that support tabular data.  -->  

<span data-ttu-id="9dc37-163">如果数据具有命名参数，则该方法还允许您为每个属性指定一个列，以 `console.table()` `Array` 作为第二个参数显示。</span><span class="sxs-lookup"><span data-stu-id="9dc37-163">If the data has named parameters, the `console.table()` method also allows you to specify an `Array` of columns for each property to display as a second parameter.</span></span>  <span data-ttu-id="9dc37-164">以下示例显示如何指定一个可读的列数组。</span><span class="sxs-lookup"><span data-stu-id="9dc37-164">The following example displays how to specify an array of columns that is more readable.</span></span>  

```javascript
// get all the h1, p and script elements 
let contentElements = document.querySelectorAll(':is(h1,p,script)');
// display the elements as an unfiltered table 
console.table(contentElements)
// display only relevant columns 
console.table(contentElements,['nodeName', 'innerText', 'offsetHeight'])
```  

:::image type="complex" source="../media/console-log-table-filtered.msft.png" alt-text="console.table 显示并提供要显示为第二个参数的属性数组的筛选器信息" lightbox="../media/console-log-table-filtered.msft.png":::
   <span data-ttu-id="9dc37-166">显示和提供要显示为第二个参数 `console.table` 的属性数组的筛选器信息</span><span class="sxs-lookup"><span data-stu-id="9dc37-166">Filter information that `console.table` displays and provide an array of properties to display as a second parameter</span></span>  
:::image-end:::  

<span data-ttu-id="9dc37-167">您可能会尝试将日志方法用作调试网页的主要方式，因为日志方法易于使用。</span><span class="sxs-lookup"><span data-stu-id="9dc37-167">You may be tempted to use the log methods as your main means to debug webpages, because log methods are simple to use.</span></span>  <span data-ttu-id="9dc37-168">请考虑任何请求 `console.log()` 的结果。</span><span class="sxs-lookup"><span data-stu-id="9dc37-168">Consider the result of any `console.log()` request.</span></span>  <span data-ttu-id="9dc37-169">Live 产品不应使用用于调试的任何日志。</span><span class="sxs-lookup"><span data-stu-id="9dc37-169">Live products shouldn't use any log that was used to debug.</span></span>  <span data-ttu-id="9dc37-170">它可能会向用户显示内部信息。</span><span class="sxs-lookup"><span data-stu-id="9dc37-170">It may reveal inside information to people.</span></span>  <span data-ttu-id="9dc37-171">控制台中创建的噪音 **非常** 强烈。</span><span class="sxs-lookup"><span data-stu-id="9dc37-171">And the noise created in the **Console** is overwhelming.</span></span>  <span data-ttu-id="9dc37-172">当您使用 [断点调试][DevtoolsJavascriptBreakpoints] 或 [Live Expressions][DevtoolsConsoleLiveExpressions]时，您可能会发现您的工作流更有效，并且您获得更好的结果。</span><span class="sxs-lookup"><span data-stu-id="9dc37-172">When you use [Breakpoint Debugging][DevtoolsJavascriptBreakpoints] or [Live Expressions][DevtoolsConsoleLiveExpressions], you may find that your workflows are more effective and you get better results.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9dc37-173">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="9dc37-173">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
