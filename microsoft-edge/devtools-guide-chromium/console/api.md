---
title: 控制台 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/09/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 19545759ede4252f2e7ba21329d482f4eb96f0c6
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708462"
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

# <span data-ttu-id="7b7ba-103">控制台 API 参考</span><span class="sxs-lookup"><span data-stu-id="7b7ba-103">Console API Reference</span></span>  

<span data-ttu-id="7b7ba-104">使用控制台 API 方法将消息从 JavaScript 写入控制台。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-104">Use the Console API methods to write messages to the Console from your JavaScript.</span></span>  <span data-ttu-id="7b7ba-105">有关主题的交互式介绍，请参阅将[消息记录到控制台的入门][DevtoolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-105">For an interactive introduction to the topic, see [Get Started With Logging Messages To The Console][DevtoolsConsoleLog].</span></span>  <span data-ttu-id="7b7ba-106">对于 `debug()` `monitorEvents()` 仅在 "**控制台**" 窗格中可用的便利方法，请参阅[控制台实用工具 API 参考][DevtoolConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-106">For the convenience methods like `debug()` or `monitorEvents()` which are only available from the **Console** pane, see [Console Utilities API Reference][DevtoolConsoleUtilities].</span></span>  

---  

## <span data-ttu-id="7b7ba-107">声明</span><span class="sxs-lookup"><span data-stu-id="7b7ba-107">assert</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="7b7ba-108">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-108">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

<span data-ttu-id="7b7ba-109">当计算结果为时，将[错误](#error)写入控制台 `expression` `false` 。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-109">Writes an [error](#error) to the console when `expression` evaluates to `false`.</span></span>  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="Console 的结果（）示例" lightbox="../media/console-demo-assert-button.msft.png":::
   <span data-ttu-id="7b7ba-111">图1：示例的结果 `console.assert()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-111">Figure 1:  The result of the `console.assert()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-112">消除</span><span class="sxs-lookup"><span data-stu-id="7b7ba-112">clear</span></span>  

```javascript
console.clear()
```

<span data-ttu-id="7b7ba-113">清除控制台。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-113">Clears the console.</span></span>  

```javascript
console.clear();  
```  

<span data-ttu-id="7b7ba-114">如果 "[保留日志][DevtoolsConsoleReferenceLevel]" 已启用， [clear](#clear)方法将被禁用。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-114">If [Preserve Log][DevtoolsConsoleReferenceLevel] is enabled, the [clear](#clear) method is disabled.</span></span>  

### <span data-ttu-id="7b7ba-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b7ba-115">See also</span></span>  

*   [<span data-ttu-id="7b7ba-116">清除控制台</span><span class="sxs-lookup"><span data-stu-id="7b7ba-116">Clear the Console</span></span>][DevtoolsConsoleReferenceClear]  

---  

## <span data-ttu-id="7b7ba-117">盘点</span><span class="sxs-lookup"><span data-stu-id="7b7ba-117">count</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="7b7ba-118">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-118">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-119">写入在同一行和同一行调用[count](#count)方法的次数 `label` 。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-119">Writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="7b7ba-120">使用[countReset](#countreset)方法重置计数。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-120">Use the [countReset](#countreset) method to reset the count.</span></span>  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="Console 的结果（）示例" lightbox="../media/console-demo-count-button.msft.png":::
   <span data-ttu-id="7b7ba-122">图2：示例的结果 `console.count()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-122">Figure 2:  The result of the `console.count()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-123">countReset</span><span class="sxs-lookup"><span data-stu-id="7b7ba-123">countReset</span></span>  

```javascript
console.countReset([label])
```  

<span data-ttu-id="7b7ba-124">重置计数。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-124">Resets a count.</span></span>  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## <span data-ttu-id="7b7ba-125">调试</span><span class="sxs-lookup"><span data-stu-id="7b7ba-125">debug</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="7b7ba-126">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-126">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Verbose`

<span data-ttu-id="7b7ba-127">除了不同日志级别的[日志](#log)一样。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-127">Identical to [log](#log) except different log level.</span></span>  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="Console 的结果（）示例" lightbox="../media/console-demo-debug-button.msft.png":::
   <span data-ttu-id="7b7ba-129">图3：示例的结果 `console.debug()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-129">Figure 3:  The result of the `console.debug()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-130">dir</span><span class="sxs-lookup"><span data-stu-id="7b7ba-130">dir</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="7b7ba-131">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-131">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-132">打印指定对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-132">Prints a JSON representation of the specified object.</span></span>  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="Console （）示例的结果" lightbox="../media/console-demo-dir-button.msft.png":::
   <span data-ttu-id="7b7ba-134">图4：示例的结果 `console.dir()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-134">Figure 4:  The result of the `console.dir()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-135">dirxml</span><span class="sxs-lookup"><span data-stu-id="7b7ba-135">dirxml</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="7b7ba-136">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-136">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-137">打印的子代的 XML 表示形式 `node` 。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-137">Prints an XML representation of the descendants of `node`.</span></span>  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="Dirxml （）示例的结果" lightbox="../media/console-demo-dirxml-button.msft.png":::
   <span data-ttu-id="7b7ba-139">图5：示例的结果 `console.dirxml()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-139">Figure 5:  The result of the `console.dirxml()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-140">错误</span><span class="sxs-lookup"><span data-stu-id="7b7ba-140">error</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="7b7ba-141">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-141">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<span data-ttu-id="7b7ba-142">`object`将文件打印到控制台，将其格式设置为错误，并包含堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-142">Prints the `object` to the Console, formats it as an error, and includes a stack trace.</span></span>  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="控制台的结果。错误（）示例" lightbox="../media/console-demo-error-button.msft.png":::
   <span data-ttu-id="7b7ba-144">图6：示例的结果 `console.error()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-144">Figure 6:  The result of the `console.error()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-145">组</span><span class="sxs-lookup"><span data-stu-id="7b7ba-145">group</span></span>  

```javascript
console.group(label)
```  

<span data-ttu-id="7b7ba-146">在使用[groupEnd](#groupend)方法之前，直观地将邮件分组到一起。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-146">Visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="7b7ba-147">使用[groupCollapsed](#groupcollapsed)方法可在初始记录到控制台时折叠组。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-147">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it is initially logged to the Console.</span></span>  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

:::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="Console 的结果。 group （）示例" lightbox="../media/console-demo-group-button.msft.png":::
   <span data-ttu-id="7b7ba-149">图7：示例的结果 `console.group()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-149">Figure 7:  The result of the `console.group()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-150">groupCollapsed</span><span class="sxs-lookup"><span data-stu-id="7b7ba-150">groupCollapsed</span></span>  

```javascript
console.groupCollapsed(label)
```  

<span data-ttu-id="7b7ba-151">除了在将组记录到控制台时，组初始折叠外，还与[log](#log)方法相同。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-151">Same as the [log](#log) method, except the group is initially collapsed when it is logged to the Console.</span></span>  

---  

## <span data-ttu-id="7b7ba-152">groupEnd</span><span class="sxs-lookup"><span data-stu-id="7b7ba-152">groupEnd</span></span>  

```javascript
console.groupEnd(label)
```  

<span data-ttu-id="7b7ba-153">停止直观地对邮件进行分组。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-153">Stops visually grouping messages.</span></span>  <span data-ttu-id="7b7ba-154">请参阅[群组](#group)方法。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-154">See the [group](#group) method.</span></span>  

---  

## <span data-ttu-id="7b7ba-155">“信息”</span><span class="sxs-lookup"><span data-stu-id="7b7ba-155">info</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="7b7ba-156">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-156">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-157">与[log](#log)方法相同。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-157">Identical to the [log](#log) method.</span></span>  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="Console.info （）示例的结果" lightbox="../media/console-demo-info-button.msft.png":::
   <span data-ttu-id="7b7ba-159">图8：示例的结果 `console.info()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-159">Figure 8:  The result of the `console.info()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-160">日志</span><span class="sxs-lookup"><span data-stu-id="7b7ba-160">log</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="7b7ba-161">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-161">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-162">将消息打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-162">Prints a message to the Console.</span></span>  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="Console 的结果（）示例" lightbox="../media/console-demo-log-button.msft.png":::
   <span data-ttu-id="7b7ba-164">图9：示例的结果 `console.log()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-164">Figure 9:  The result of the `console.log()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-165">表</span><span class="sxs-lookup"><span data-stu-id="7b7ba-165">table</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="7b7ba-166">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-166">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-167">将对象数组作为表进行记录。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-167">Logs an array of objects as a table.</span></span>  

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

:::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="Console 的结果（）示例" lightbox="../media/console-demo-table-button.msft.png":::
   <span data-ttu-id="7b7ba-169">图10：示例的结果 `console.table()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-169">Figure 10:  The result of the `console.table()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-170">time</span><span class="sxs-lookup"><span data-stu-id="7b7ba-170">time</span></span>  

```javascript
console.time([label])
```  

<span data-ttu-id="7b7ba-171">启动新的计时器。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-171">Starts a new timer.</span></span>  <span data-ttu-id="7b7ba-172">使用[timeEnd](#timeend)方法停止计时器并将经过的时间打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-172">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the Console.</span></span>  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="Console 的结果。 time （）示例" lightbox="../media/console-demo-time-button.msft.png":::
   <span data-ttu-id="7b7ba-174">图11：示例的结果 `console.time()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-174">Figure 11:  The result of the `console.time()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-175">timeEnd</span><span class="sxs-lookup"><span data-stu-id="7b7ba-175">timeEnd</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="7b7ba-176">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-176">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-177">停止计时器。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-177">Stops a timer.</span></span>  <span data-ttu-id="7b7ba-178">请参阅[time](#time)方法。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-178">See the [time](#time) method.</span></span>  

---  

## <span data-ttu-id="7b7ba-179">轨迹</span><span class="sxs-lookup"><span data-stu-id="7b7ba-179">trace</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="7b7ba-180">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-180">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="7b7ba-181">将堆栈跟踪打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-181">Prints a stack trace to the Console.</span></span>  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="Console 的结果（）示例" lightbox="../media/console-demo-trace-button.msft.png":::
   <span data-ttu-id="7b7ba-183">图12：示例的结果 `console.trace()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-183">Figure 12:  The result of the `console.trace()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="7b7ba-184">出</span><span class="sxs-lookup"><span data-stu-id="7b7ba-184">warn</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="7b7ba-185">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="7b7ba-185">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

<span data-ttu-id="7b7ba-186">将警告打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-186">Prints a warning to the Console.</span></span>  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="控制台的结果。警告（）示例" lightbox="../media/console-demo-warn-button.msft.png":::
   <span data-ttu-id="7b7ba-188">图13：示例的结果 `console.warn()`</span><span class="sxs-lookup"><span data-stu-id="7b7ba-188">Figure 13:  The result of the `console.warn()` example</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "在控制台中记录消息入门"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "清除控制台参考"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "跨页面加载保留消息-控制台参考"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "按日志级别筛选-控制台参考"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  

> [!NOTE]
> <span data-ttu-id="7b7ba-195">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-195">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7b7ba-196">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/api)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-196">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="7b7ba-198">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="7b7ba-198">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
