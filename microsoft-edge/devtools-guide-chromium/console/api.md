---
description: 使用控制台 API 将消息写入控制台。
title: 控制台 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: f38a7403cf11fbec5f5833fc0b1ed10207b436de
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398047"
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

# <a name="console-api-reference"></a><span data-ttu-id="2b1d7-104">控制台 API 参考</span><span class="sxs-lookup"><span data-stu-id="2b1d7-104">Console API reference</span></span>  

<span data-ttu-id="2b1d7-105">使用控制台 API 方法从 JavaScript 将消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-105">Use the Console API methods to write messages to the Console from your JavaScript.</span></span>  <span data-ttu-id="2b1d7-106">有关主题的交互式简介，请导航到["开始使用将消息记录到控制台"。][DevtoolsConsoleLog]</span><span class="sxs-lookup"><span data-stu-id="2b1d7-106">For an interactive introduction to the topic, navigate to [Get Started With Logging Messages To The Console][DevtoolsConsoleLog].</span></span>  <span data-ttu-id="2b1d7-107">对于控制台窗格中的方便方法，例如或仅提供这些方法， `debug()` `monitorEvents()` 请导航到[控制台实用工具 API 参考][DevtoolConsoleUtilities]。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2b1d7-107">For the convenience methods like `debug()` or `monitorEvents()` which are only available from the **Console** pane, navigate to [Console Utilities API Reference][DevtoolConsoleUtilities].</span></span>  

---  

## <a name="assert"></a><span data-ttu-id="2b1d7-108">assert</span><span class="sxs-lookup"><span data-stu-id="2b1d7-108">assert</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="2b1d7-109">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-109">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

<span data-ttu-id="2b1d7-110">计算 [结果](#error) 为 时，将错误 `expression` 写入控制台 `false` 。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-110">Writes an [error](#error) to the console when `expression` evaluates to `false`.</span></span>  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="console.assert 示例 () 结果" lightbox="../media/console-demo-assert-button.msft.png":::
   <span data-ttu-id="2b1d7-112">图 1：示例 `console.assert()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-112">Figure 1:  The result of the `console.assert()` example</span></span>  
:::image-end:::  

---  

## <a name="clear"></a><span data-ttu-id="2b1d7-113">clear</span><span class="sxs-lookup"><span data-stu-id="2b1d7-113">clear</span></span>  

```javascript
console.clear()
```

<span data-ttu-id="2b1d7-114">清除控制台。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-114">Clears the console.</span></span>  

```javascript
console.clear();  
```  

<span data-ttu-id="2b1d7-115">如果 [启用"][DevtoolsConsoleReferenceLevel] 保留日志"， [则禁用清除](#clear) 方法。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-115">If [Preserve Log][DevtoolsConsoleReferenceLevel] is enabled, the [clear](#clear) method is disabled.</span></span>  

### <a name="see-also"></a><span data-ttu-id="2b1d7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b1d7-116">See also</span></span>  

*   [<span data-ttu-id="2b1d7-117">清除控制台</span><span class="sxs-lookup"><span data-stu-id="2b1d7-117">Clear the Console</span></span>][DevtoolsConsoleReferenceClear]  

---  

## <a name="count"></a><span data-ttu-id="2b1d7-118">count</span><span class="sxs-lookup"><span data-stu-id="2b1d7-118">count</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="2b1d7-119">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-119">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-120">写入在同一行和同一行上调用 [count](#count) 方法次数 `label` 。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-120">Writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="2b1d7-121">使用 [countReset](#countreset) 方法重置计数。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-121">Use the [countReset](#countreset) method to reset the count.</span></span>  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="console.count 示例 () 结果" lightbox="../media/console-demo-count-button.msft.png":::
   <span data-ttu-id="2b1d7-123">图 2：示例 `console.count()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-123">Figure 2:  The result of the `console.count()` example</span></span>  
:::image-end:::  

---  

## <a name="countreset"></a><span data-ttu-id="2b1d7-124">countReset</span><span class="sxs-lookup"><span data-stu-id="2b1d7-124">countReset</span></span>  

```javascript
console.countReset([label])
```  

<span data-ttu-id="2b1d7-125">重置计数。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-125">Resets a count.</span></span>  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## <a name="debug"></a><span data-ttu-id="2b1d7-126">调试</span><span class="sxs-lookup"><span data-stu-id="2b1d7-126">debug</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="2b1d7-127">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-127">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Verbose`

<span data-ttu-id="2b1d7-128">与日志 [相同，](#log) 不同日志级别除外。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-128">Identical to [log](#log) except different log level.</span></span>  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="console.debug 示例 () 结果" lightbox="../media/console-demo-debug-button.msft.png":::
   <span data-ttu-id="2b1d7-130">图 3：示例 `console.debug()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-130">Figure 3:  The result of the `console.debug()` example</span></span>  
:::image-end:::  

---  

## <a name="dir"></a><span data-ttu-id="2b1d7-131">dir</span><span class="sxs-lookup"><span data-stu-id="2b1d7-131">dir</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="2b1d7-132">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-132">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-133">打印指定对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-133">Prints a JSON representation of the specified object.</span></span>  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="console.dir 示例 () 结果" lightbox="../media/console-demo-dir-button.msft.png":::
   <span data-ttu-id="2b1d7-135">图 4：示例 `console.dir()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-135">Figure 4:  The result of the `console.dir()` example</span></span>  
:::image-end:::  

---  

## <a name="dirxml"></a><span data-ttu-id="2b1d7-136">dirxml</span><span class="sxs-lookup"><span data-stu-id="2b1d7-136">dirxml</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="2b1d7-137">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-137">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-138">打印的后代的 XML 表示形式 `node` 。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-138">Prints an XML representation of the descendants of `node`.</span></span>  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="console.dirxml 示例 () 结果" lightbox="../media/console-demo-dirxml-button.msft.png":::
   <span data-ttu-id="2b1d7-140">图 5：示例 `console.dirxml()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-140">Figure 5:  The result of the `console.dirxml()` example</span></span>  
:::image-end:::  

---  

## <a name="error"></a><span data-ttu-id="2b1d7-141">错误</span><span class="sxs-lookup"><span data-stu-id="2b1d7-141">error</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="2b1d7-142">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-142">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<span data-ttu-id="2b1d7-143">将输出 `object` 到控制台，将它格式化为错误，并包括堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-143">Prints the `object` to the Console, formats it as an error, and includes a stack trace.</span></span>  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="console.error 示例 () 结果" lightbox="../media/console-demo-error-button.msft.png":::
   <span data-ttu-id="2b1d7-145">图 6：示例 `console.error()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-145">Figure 6:  The result of the `console.error()` example</span></span>  
:::image-end:::  

---  

## <a name="group"></a><span data-ttu-id="2b1d7-146">组</span><span class="sxs-lookup"><span data-stu-id="2b1d7-146">group</span></span>  

```javascript
console.group(label)
```  

<span data-ttu-id="2b1d7-147">直观地将邮件分组在一起，直到 [使用 groupEnd](#groupend) 方法。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-147">Visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="2b1d7-148">使用 [groupCollapsed](#groupcollapsed) 方法在组最初记录到控制台时折叠该组。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-148">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it is initially logged to the Console.</span></span>  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

:::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="console.group 示例 () 结果" lightbox="../media/console-demo-group-button.msft.png":::
   <span data-ttu-id="2b1d7-150">图 7：示例 `console.group()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-150">Figure 7:  The result of the `console.group()` example</span></span>  
:::image-end:::  

---  

## <a name="groupcollapsed"></a><span data-ttu-id="2b1d7-151">groupCollapsed</span><span class="sxs-lookup"><span data-stu-id="2b1d7-151">groupCollapsed</span></span>  

```javascript
console.groupCollapsed(label)
```  

<span data-ttu-id="2b1d7-152">与日志 [方法相同](#log) ，但组在记录到控制台时最初折叠。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-152">Same as the [log](#log) method, except the group is initially collapsed when it is logged to the Console.</span></span>  

---  

## <a name="groupend"></a><span data-ttu-id="2b1d7-153">groupEnd</span><span class="sxs-lookup"><span data-stu-id="2b1d7-153">groupEnd</span></span>  

```javascript
console.groupEnd(label)
```  

<span data-ttu-id="2b1d7-154">停止以可视方式对邮件进行分组。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-154">Stops visually grouping messages.</span></span>  <span data-ttu-id="2b1d7-155">导航到 [组](#group) 方法。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-155">Navigate to the [group](#group) method.</span></span>  

---  

## <a name="info"></a><span data-ttu-id="2b1d7-156">“信息”</span><span class="sxs-lookup"><span data-stu-id="2b1d7-156">info</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="2b1d7-157">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-157">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-158">与日志 [方法](#log) 相同。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-158">Identical to the [log](#log) method.</span></span>  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="示例console.info () 结果" lightbox="../media/console-demo-info-button.msft.png":::
   <span data-ttu-id="2b1d7-160">图 8：示例 `console.info()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-160">Figure 8:  The result of the `console.info()` example</span></span>  
:::image-end:::  

---  

## <a name="log"></a><span data-ttu-id="2b1d7-161">日志</span><span class="sxs-lookup"><span data-stu-id="2b1d7-161">log</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="2b1d7-162">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-162">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-163">将消息打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-163">Prints a message to the Console.</span></span>  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="console.log 示例 () 结果" lightbox="../media/console-demo-log-button.msft.png":::
   <span data-ttu-id="2b1d7-165">图 9：示例 `console.log()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-165">Figure 9:  The result of the `console.log()` example</span></span>  
:::image-end:::  

---  

## <a name="table"></a><span data-ttu-id="2b1d7-166">table</span><span class="sxs-lookup"><span data-stu-id="2b1d7-166">table</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="2b1d7-167">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-167">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-168">将对象数组记录为表。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-168">Logs an array of objects as a table.</span></span>  

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

:::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="console.table 示例 () 结果" lightbox="../media/console-demo-table-button.msft.png":::
   <span data-ttu-id="2b1d7-170">图 10：示例 `console.table()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-170">Figure 10:  The result of the `console.table()` example</span></span>  
:::image-end:::  

---  

## <a name="time"></a><span data-ttu-id="2b1d7-171">time</span><span class="sxs-lookup"><span data-stu-id="2b1d7-171">time</span></span>  

```javascript
console.time([label])
```  

<span data-ttu-id="2b1d7-172">启动新计时器。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-172">Starts a new timer.</span></span>  <span data-ttu-id="2b1d7-173">使用 [timeEnd](#timeend) 方法停止计时器，将已用时间打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-173">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the Console.</span></span>  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="console.time 示例 () 结果" lightbox="../media/console-demo-time-button.msft.png":::
   <span data-ttu-id="2b1d7-175">图 11：示例 `console.time()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-175">Figure 11:  The result of the `console.time()` example</span></span>  
:::image-end:::  

---  

## <a name="timeend"></a><span data-ttu-id="2b1d7-176">timeEnd</span><span class="sxs-lookup"><span data-stu-id="2b1d7-176">timeEnd</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="2b1d7-177">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-177">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-178">停止计时器。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-178">Stops a timer.</span></span>  <span data-ttu-id="2b1d7-179">导航到 [时间](#time) 方法。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-179">Navigate to the [time](#time) method.</span></span>  

---  

## <a name="trace"></a><span data-ttu-id="2b1d7-180">trace</span><span class="sxs-lookup"><span data-stu-id="2b1d7-180">trace</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="2b1d7-181">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-181">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="2b1d7-182">将堆栈跟踪打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-182">Prints a stack trace to the Console.</span></span>  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="console.trace 示例 () 结果" lightbox="../media/console-demo-trace-button.msft.png":::
   <span data-ttu-id="2b1d7-184">图 12：示例 `console.trace()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-184">Figure 12:  The result of the `console.trace()` example</span></span>  
:::image-end:::  

---  

## <a name="warn"></a><span data-ttu-id="2b1d7-185">warn</span><span class="sxs-lookup"><span data-stu-id="2b1d7-185">warn</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="2b1d7-186">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="2b1d7-186">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

<span data-ttu-id="2b1d7-187">向控制台打印警告。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-187">Prints a warning to the Console.</span></span>  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="console.warn 示例 () 结果" lightbox="../media/console-demo-warn-button.msft.png":::
   <span data-ttu-id="2b1d7-189">图 13：示例 `console.warn()` 的结果</span><span class="sxs-lookup"><span data-stu-id="2b1d7-189">Figure 13:  The result of the `console.warn()` example</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="2b1d7-190">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="2b1d7-190">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "开始在控制台中记录消息"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "清除控制台 - 控制台参考"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "跨页面加载保留消息 - 控制台参考"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "按日志级别筛选 - 控制台参考"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"  

> [!NOTE]
> <span data-ttu-id="2b1d7-197">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-197">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2b1d7-198">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/api)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-198">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2b1d7-200">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2b1d7-200">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
