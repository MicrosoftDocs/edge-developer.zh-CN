---
description: 使用控制台 API 将消息写入到控制台。
title: 控制台 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 684c0a1e42357ceca0a0295859e64447251f191a
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993252"
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

# <span data-ttu-id="a248a-104">控制台 API 参考</span><span class="sxs-lookup"><span data-stu-id="a248a-104">Console API Reference</span></span>  

<span data-ttu-id="a248a-105">使用控制台 API 方法将消息从 JavaScript 写入控制台。</span><span class="sxs-lookup"><span data-stu-id="a248a-105">Use the Console API methods to write messages to the Console from your JavaScript.</span></span>  <span data-ttu-id="a248a-106">有关主题的交互式介绍，请参阅将 [消息记录到控制台的入门][DevtoolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="a248a-106">For an interactive introduction to the topic, see [Get Started With Logging Messages To The Console][DevtoolsConsoleLog].</span></span>  <span data-ttu-id="a248a-107">对于 `debug()` `monitorEvents()` 仅在 " **控制台** " 窗格中可用的便利方法，请参阅 [控制台实用工具 API 参考][DevtoolConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="a248a-107">For the convenience methods like `debug()` or `monitorEvents()` which are only available from the **Console** pane, see [Console Utilities API Reference][DevtoolConsoleUtilities].</span></span>  

---  

## <span data-ttu-id="a248a-108">声明</span><span class="sxs-lookup"><span data-stu-id="a248a-108">assert</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="a248a-109">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-109">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

<span data-ttu-id="a248a-110">当计算结果为时，将 [错误](#error) 写入控制台 `expression` `false` 。</span><span class="sxs-lookup"><span data-stu-id="a248a-110">Writes an [error](#error) to the console when `expression` evaluates to `false`.</span></span>  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="控制台的结果。 assert ( # A1 示例" lightbox="../media/console-demo-assert-button.msft.png":::
   <span data-ttu-id="a248a-112">图1：示例的结果 `console.assert()`</span><span class="sxs-lookup"><span data-stu-id="a248a-112">Figure 1:  The result of the `console.assert()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-113">消除</span><span class="sxs-lookup"><span data-stu-id="a248a-113">clear</span></span>  

```javascript
console.clear()
```

<span data-ttu-id="a248a-114">清除控制台。</span><span class="sxs-lookup"><span data-stu-id="a248a-114">Clears the console.</span></span>  

```javascript
console.clear();  
```  

<span data-ttu-id="a248a-115">如果 " [保留日志][DevtoolsConsoleReferenceLevel] " 已启用， [clear](#clear) 方法将被禁用。</span><span class="sxs-lookup"><span data-stu-id="a248a-115">If [Preserve Log][DevtoolsConsoleReferenceLevel] is enabled, the [clear](#clear) method is disabled.</span></span>  

### <span data-ttu-id="a248a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a248a-116">See also</span></span>  

*   [<span data-ttu-id="a248a-117">清除控制台</span><span class="sxs-lookup"><span data-stu-id="a248a-117">Clear the Console</span></span>][DevtoolsConsoleReferenceClear]  

---  

## <span data-ttu-id="a248a-118">盘点</span><span class="sxs-lookup"><span data-stu-id="a248a-118">count</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="a248a-119">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-119">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-120">写入在同一行和同一行调用 [count](#count) 方法的次数 `label` 。</span><span class="sxs-lookup"><span data-stu-id="a248a-120">Writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="a248a-121">使用 [countReset](#countreset) 方法重置计数。</span><span class="sxs-lookup"><span data-stu-id="a248a-121">Use the [countReset](#countreset) method to reset the count.</span></span>  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="Console 的结果。 count ( # A1 示例" lightbox="../media/console-demo-count-button.msft.png":::
   <span data-ttu-id="a248a-123">图2：示例的结果 `console.count()`</span><span class="sxs-lookup"><span data-stu-id="a248a-123">Figure 2:  The result of the `console.count()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-124">countReset</span><span class="sxs-lookup"><span data-stu-id="a248a-124">countReset</span></span>  

```javascript
console.countReset([label])
```  

<span data-ttu-id="a248a-125">重置计数。</span><span class="sxs-lookup"><span data-stu-id="a248a-125">Resets a count.</span></span>  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## <span data-ttu-id="a248a-126">调试</span><span class="sxs-lookup"><span data-stu-id="a248a-126">debug</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="a248a-127">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-127">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Verbose`

<span data-ttu-id="a248a-128">除了不同日志级别的 [日志](#log) 一样。</span><span class="sxs-lookup"><span data-stu-id="a248a-128">Identical to [log](#log) except different log level.</span></span>  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="控制台的结果。 debug ( # A1 示例" lightbox="../media/console-demo-debug-button.msft.png":::
   <span data-ttu-id="a248a-130">图3：示例的结果 `console.debug()`</span><span class="sxs-lookup"><span data-stu-id="a248a-130">Figure 3:  The result of the `console.debug()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-131">dir</span><span class="sxs-lookup"><span data-stu-id="a248a-131">dir</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="a248a-132">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-132">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-133">打印指定对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="a248a-133">Prints a JSON representation of the specified object.</span></span>  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="Console 的结果 ( # A1 示例" lightbox="../media/console-demo-dir-button.msft.png":::
   <span data-ttu-id="a248a-135">图4：示例的结果 `console.dir()`</span><span class="sxs-lookup"><span data-stu-id="a248a-135">Figure 4:  The result of the `console.dir()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-136">dirxml</span><span class="sxs-lookup"><span data-stu-id="a248a-136">dirxml</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="a248a-137">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-137">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-138">打印的子代的 XML 表示形式 `node` 。</span><span class="sxs-lookup"><span data-stu-id="a248a-138">Prints an XML representation of the descendants of `node`.</span></span>  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="Dirxml 的结果 ( # A1 示例" lightbox="../media/console-demo-dirxml-button.msft.png":::
   <span data-ttu-id="a248a-140">图5：示例的结果 `console.dirxml()`</span><span class="sxs-lookup"><span data-stu-id="a248a-140">Figure 5:  The result of the `console.dirxml()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-141">错误</span><span class="sxs-lookup"><span data-stu-id="a248a-141">error</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="a248a-142">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-142">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<span data-ttu-id="a248a-143">`object`将文件打印到控制台，将其格式设置为错误，并包含堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="a248a-143">Prints the `object` to the Console, formats it as an error, and includes a stack trace.</span></span>  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="控制台的结果。错误 ( # A1 示例" lightbox="../media/console-demo-error-button.msft.png":::
   <span data-ttu-id="a248a-145">图6：示例的结果 `console.error()`</span><span class="sxs-lookup"><span data-stu-id="a248a-145">Figure 6:  The result of the `console.error()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-146">组</span><span class="sxs-lookup"><span data-stu-id="a248a-146">group</span></span>  

```javascript
console.group(label)
```  

<span data-ttu-id="a248a-147">在使用 [groupEnd](#groupend) 方法之前，直观地将邮件分组到一起。</span><span class="sxs-lookup"><span data-stu-id="a248a-147">Visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="a248a-148">使用 [groupCollapsed](#groupcollapsed) 方法可在初始记录到控制台时折叠组。</span><span class="sxs-lookup"><span data-stu-id="a248a-148">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it is initially logged to the Console.</span></span>  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

:::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="控制台的结果。组 ( # A1 示例" lightbox="../media/console-demo-group-button.msft.png":::
   <span data-ttu-id="a248a-150">图7：示例的结果 `console.group()`</span><span class="sxs-lookup"><span data-stu-id="a248a-150">Figure 7:  The result of the `console.group()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-151">groupCollapsed</span><span class="sxs-lookup"><span data-stu-id="a248a-151">groupCollapsed</span></span>  

```javascript
console.groupCollapsed(label)
```  

<span data-ttu-id="a248a-152">除了在将组记录到控制台时，组初始折叠外，还与 [log](#log) 方法相同。</span><span class="sxs-lookup"><span data-stu-id="a248a-152">Same as the [log](#log) method, except the group is initially collapsed when it is logged to the Console.</span></span>  

---  

## <span data-ttu-id="a248a-153">groupEnd</span><span class="sxs-lookup"><span data-stu-id="a248a-153">groupEnd</span></span>  

```javascript
console.groupEnd(label)
```  

<span data-ttu-id="a248a-154">停止直观地对邮件进行分组。</span><span class="sxs-lookup"><span data-stu-id="a248a-154">Stops visually grouping messages.</span></span>  <span data-ttu-id="a248a-155">请参阅 [群组](#group) 方法。</span><span class="sxs-lookup"><span data-stu-id="a248a-155">See the [group](#group) method.</span></span>  

---  

## <span data-ttu-id="a248a-156">“信息”</span><span class="sxs-lookup"><span data-stu-id="a248a-156">info</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="a248a-157">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-157">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-158">与 [log](#log) 方法相同。</span><span class="sxs-lookup"><span data-stu-id="a248a-158">Identical to the [log](#log) method.</span></span>  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="Console.info 的结果 ( # A1 示例" lightbox="../media/console-demo-info-button.msft.png":::
   <span data-ttu-id="a248a-160">图8：示例的结果 `console.info()`</span><span class="sxs-lookup"><span data-stu-id="a248a-160">Figure 8:  The result of the `console.info()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-161">日志</span><span class="sxs-lookup"><span data-stu-id="a248a-161">log</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="a248a-162">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-162">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-163">将消息打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="a248a-163">Prints a message to the Console.</span></span>  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="Console 的结果 ( # A1 示例" lightbox="../media/console-demo-log-button.msft.png":::
   <span data-ttu-id="a248a-165">图9：示例的结果 `console.log()`</span><span class="sxs-lookup"><span data-stu-id="a248a-165">Figure 9:  The result of the `console.log()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-166">表</span><span class="sxs-lookup"><span data-stu-id="a248a-166">table</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="a248a-167">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-167">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-168">将对象数组作为表进行记录。</span><span class="sxs-lookup"><span data-stu-id="a248a-168">Logs an array of objects as a table.</span></span>  

```javascript
console.table([
    {
        first: 'René',
        last: 'Magritte',
    },
    {
        first: 'Chaim',
        last: 'Soutine',
        birthday: '18930113',
    },
    {
        first: 'Henri',
        last: 'Matisse',
    }
]);
```  

:::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="该控制台的结果。表格 ( # A1 示例" lightbox="../media/console-demo-table-button.msft.png":::
   <span data-ttu-id="a248a-170">图10：示例的结果 `console.table()`</span><span class="sxs-lookup"><span data-stu-id="a248a-170">Figure 10:  The result of the `console.table()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-171">time</span><span class="sxs-lookup"><span data-stu-id="a248a-171">time</span></span>  

```javascript
console.time([label])
```  

<span data-ttu-id="a248a-172">启动新的计时器。</span><span class="sxs-lookup"><span data-stu-id="a248a-172">Starts a new timer.</span></span>  <span data-ttu-id="a248a-173">使用 [timeEnd](#timeend) 方法停止计时器并将经过的时间打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="a248a-173">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the Console.</span></span>  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="控制台的结果。时间 ( # A1 示例" lightbox="../media/console-demo-time-button.msft.png":::
   <span data-ttu-id="a248a-175">图11：示例的结果 `console.time()`</span><span class="sxs-lookup"><span data-stu-id="a248a-175">Figure 11:  The result of the `console.time()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-176">timeEnd</span><span class="sxs-lookup"><span data-stu-id="a248a-176">timeEnd</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="a248a-177">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-177">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-178">停止计时器。</span><span class="sxs-lookup"><span data-stu-id="a248a-178">Stops a timer.</span></span>  <span data-ttu-id="a248a-179">请参阅 [time](#time) 方法。</span><span class="sxs-lookup"><span data-stu-id="a248a-179">See the [time](#time) method.</span></span>  

---  

## <span data-ttu-id="a248a-180">轨迹</span><span class="sxs-lookup"><span data-stu-id="a248a-180">trace</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="a248a-181">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-181">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="a248a-182">将堆栈跟踪打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="a248a-182">Prints a stack trace to the Console.</span></span>  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="控制台的结果。跟踪 ( # A1 示例" lightbox="../media/console-demo-trace-button.msft.png":::
   <span data-ttu-id="a248a-184">图12：示例的结果 `console.trace()`</span><span class="sxs-lookup"><span data-stu-id="a248a-184">Figure 12:  The result of the `console.trace()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="a248a-185">出</span><span class="sxs-lookup"><span data-stu-id="a248a-185">warn</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="a248a-186">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="a248a-186">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

<span data-ttu-id="a248a-187">将警告打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="a248a-187">Prints a warning to the Console.</span></span>  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="控制台的结果。警告 ( # A1 示例" lightbox="../media/console-demo-warn-button.msft.png":::
   <span data-ttu-id="a248a-189">图13：示例的结果 `console.warn()`</span><span class="sxs-lookup"><span data-stu-id="a248a-189">Figure 13:  The result of the `console.warn()` example</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "在控制台中记录消息入门"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "清除控制台参考"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "跨页面加载保留消息-控制台参考"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "按日志级别筛选-控制台参考"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"  

> [!NOTE]
> <span data-ttu-id="a248a-196">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a248a-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a248a-197">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/api)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="a248a-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="a248a-199">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a248a-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
