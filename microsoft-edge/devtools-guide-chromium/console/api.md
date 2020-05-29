---
title: 控制台 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: e54bae7c7c61584ccd39568f1bb54312cc2082c0
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601752"
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





# <span data-ttu-id="64ba5-103">控制台 API 参考</span><span class="sxs-lookup"><span data-stu-id="64ba5-103">Console API Reference</span></span>   

  

<span data-ttu-id="64ba5-104">使用控制台 API 方法将消息从 JavaScript 写入控制台。</span><span class="sxs-lookup"><span data-stu-id="64ba5-104">Use the Console API methods to write messages to the Console from your JavaScript.</span></span>  <span data-ttu-id="64ba5-105">有关主题的交互式介绍，请参阅将[消息记录到控制台的入门][DevtoolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="64ba5-105">See [Get Started With Logging Messages To The Console][DevtoolsConsoleLog] for an interactive introduction to the topic.</span></span>  <span data-ttu-id="64ba5-106">如果你要查找的便利方法（如或仅在控制台上可用），请参阅[控制台实用工具 API 参考] [DevtoolConsoleUtilities] `debug()` `monitorEvents()` 。</span><span class="sxs-lookup"><span data-stu-id="64ba5-106">See [Console Utilities API Reference] [DevtoolConsoleUtilities] if you are looking for the convenience methods like `debug()` or `monitorEvents()` which are only available from the Console.</span></span>  

## <span data-ttu-id="64ba5-107">声明</span><span class="sxs-lookup"><span data-stu-id="64ba5-107">assert</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="64ba5-108">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-108">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

<span data-ttu-id="64ba5-109">当计算结果为时，将[错误](#error)写入控制台 `expression` `false` 。</span><span class="sxs-lookup"><span data-stu-id="64ba5-109">Writes an [error](#error) to the console when `expression` evaluates to `false`.</span></span>  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

> ##### <span data-ttu-id="64ba5-110">图 1</span><span class="sxs-lookup"><span data-stu-id="64ba5-110">Figure 1</span></span>  
> <span data-ttu-id="64ba5-111">示例的结果 `console.assert()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-111">The result of the `console.assert()` example</span></span>  
> ![Console 的结果（）示例][ImageAssert]  

## <span data-ttu-id="64ba5-113">消除</span><span class="sxs-lookup"><span data-stu-id="64ba5-113">clear</span></span>  

```javascript
console.clear()
```

<span data-ttu-id="64ba5-114">清除控制台。</span><span class="sxs-lookup"><span data-stu-id="64ba5-114">Clears the console.</span></span>  

```javascript
console.clear();  
```  

<span data-ttu-id="64ba5-115">如果 "[保留日志][DevtoolsConsoleReferenceLevel]" 已启用， [clear](#clear)方法将被禁用。</span><span class="sxs-lookup"><span data-stu-id="64ba5-115">If [Preserve Log][DevtoolsConsoleReferenceLevel] is enabled, the [clear](#clear) method is disabled.</span></span>  

<span data-ttu-id="64ba5-116">另请参阅：[清除控制台][DevtoolsConsoleReferenceClear]</span><span class="sxs-lookup"><span data-stu-id="64ba5-116">See also: [Clear the Console][DevtoolsConsoleReferenceClear]</span></span>  

## <span data-ttu-id="64ba5-117">盘点</span><span class="sxs-lookup"><span data-stu-id="64ba5-117">count</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="64ba5-118">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-118">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-119">写入在同一行和同一行调用[count](#count)方法的次数 `label` 。</span><span class="sxs-lookup"><span data-stu-id="64ba5-119">Writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="64ba5-120">使用[countReset](#countreset)方法重置计数。</span><span class="sxs-lookup"><span data-stu-id="64ba5-120">Use the [countReset](#countreset) method to reset the count.</span></span>  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

> ##### <span data-ttu-id="64ba5-121">图 2</span><span class="sxs-lookup"><span data-stu-id="64ba5-121">Figure 2</span></span>  
> <span data-ttu-id="64ba5-122">示例的结果 `console.count()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-122">The result of the `console.count()` example</span></span>  
> ![Console 的结果（）示例][ImageCount]  

## <span data-ttu-id="64ba5-124">countReset</span><span class="sxs-lookup"><span data-stu-id="64ba5-124">countReset</span></span>  

```javascript
console.countReset([label])
```  

<span data-ttu-id="64ba5-125">重置计数。</span><span class="sxs-lookup"><span data-stu-id="64ba5-125">Resets a count.</span></span>  

```javascript
console.countReset();
console.countReset('coffee');
```  

## <span data-ttu-id="64ba5-126">调试</span><span class="sxs-lookup"><span data-stu-id="64ba5-126">debug</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="64ba5-127">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-127">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-128">与[log](#log)方法相同。</span><span class="sxs-lookup"><span data-stu-id="64ba5-128">Identical to the [log](#log) method.</span></span>  

```javascript
console.debug('debug');  
```  

> ##### <span data-ttu-id="64ba5-129">图 3</span><span class="sxs-lookup"><span data-stu-id="64ba5-129">Figure 3</span></span>  
> <span data-ttu-id="64ba5-130">示例的结果 `console.debug()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-130">The result of the `console.debug()` example</span></span>  
> ![Console 的结果（）示例][ImageDebug]  

## <span data-ttu-id="64ba5-132">dir</span><span class="sxs-lookup"><span data-stu-id="64ba5-132">dir</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="64ba5-133">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-133">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-134">打印指定对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="64ba5-134">Prints a JSON representation of the specified object.</span></span>  

```javascript
console.dir(document.head);
```  

> ##### <span data-ttu-id="64ba5-135">图 4</span><span class="sxs-lookup"><span data-stu-id="64ba5-135">Figure 4</span></span>  
> <span data-ttu-id="64ba5-136">示例的结果 `console.dir()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-136">The result of the `console.dir()` example</span></span>  
> ![Console （）示例的结果][ImageDir]  

## <span data-ttu-id="64ba5-138">dirxml</span><span class="sxs-lookup"><span data-stu-id="64ba5-138">dirxml</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="64ba5-139">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-139">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-140">打印的子代的 XML 表示形式 `node` 。</span><span class="sxs-lookup"><span data-stu-id="64ba5-140">Prints an XML representation of the descendants of `node`.</span></span>  

```javascript
console.dirxml(document);
```  

> ##### <span data-ttu-id="64ba5-141">图 5</span><span class="sxs-lookup"><span data-stu-id="64ba5-141">Figure 5</span></span>  
> <span data-ttu-id="64ba5-142">示例的结果 `console.dirxml()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-142">The result of the `console.dirxml()` example</span></span>  
> ![Dirxml （）示例的结果][ImageDirXml]  

## <span data-ttu-id="64ba5-144">错误</span><span class="sxs-lookup"><span data-stu-id="64ba5-144">error</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="64ba5-145">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-145">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<span data-ttu-id="64ba5-146">`object`将文件打印到控制台，将其格式设置为错误，并包含堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="64ba5-146">Prints the `object` to the Console, formats it as an error, and includes a stack trace.</span></span>  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

> ##### <span data-ttu-id="64ba5-147">图 6</span><span class="sxs-lookup"><span data-stu-id="64ba5-147">Figure 6</span></span>  
> <span data-ttu-id="64ba5-148">示例的结果 `console.error()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-148">The result of the `console.error()` example</span></span>  
> ![控制台的结果。错误（）示例][ImageError]  

## <span data-ttu-id="64ba5-150">组</span><span class="sxs-lookup"><span data-stu-id="64ba5-150">group</span></span>  

```javascript
console.group(label)
```  

<span data-ttu-id="64ba5-151">在使用[groupEnd](#groupend)方法之前，直观地将邮件分组到一起。</span><span class="sxs-lookup"><span data-stu-id="64ba5-151">Visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="64ba5-152">使用[groupCollapsed](#groupcollapsed)方法可在初始记录到控制台时折叠组。</span><span class="sxs-lookup"><span data-stu-id="64ba5-152">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it is initially logged to the Console.</span></span>  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

> ##### <span data-ttu-id="64ba5-153">图 7</span><span class="sxs-lookup"><span data-stu-id="64ba5-153">Figure 7</span></span>  
> <span data-ttu-id="64ba5-154">示例的结果 `console.group()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-154">The result of the `console.group()` example</span></span>  
> ![Console 的结果。 group （）示例][ImageGroup]  

## <span data-ttu-id="64ba5-156">groupCollapsed</span><span class="sxs-lookup"><span data-stu-id="64ba5-156">groupCollapsed</span></span>  

```javascript
console.groupCollapsed(label)
```  

<span data-ttu-id="64ba5-157">除了在将组记录到控制台时，组初始折叠外，还与[log](#log)方法相同。</span><span class="sxs-lookup"><span data-stu-id="64ba5-157">Same as the [log](#log) method, except the group is initially collapsed when it is logged to the Console.</span></span>  

## <span data-ttu-id="64ba5-158">groupEnd</span><span class="sxs-lookup"><span data-stu-id="64ba5-158">groupEnd</span></span>  

```javascript
console.groupEnd(label)
```  

<span data-ttu-id="64ba5-159">停止直观地对邮件进行分组。</span><span class="sxs-lookup"><span data-stu-id="64ba5-159">Stops visually grouping messages.</span></span>  <span data-ttu-id="64ba5-160">请参阅[群组](#group)方法。</span><span class="sxs-lookup"><span data-stu-id="64ba5-160">See the [group](#group) method.</span></span>  

## <span data-ttu-id="64ba5-161">“信息”</span><span class="sxs-lookup"><span data-stu-id="64ba5-161">info</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="64ba5-162">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-162">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-163">与[log](#log)方法相同。</span><span class="sxs-lookup"><span data-stu-id="64ba5-163">Identical to the [log](#log) method.</span></span>  

```javascript
console.info('info');
```  

> ##### <span data-ttu-id="64ba5-164">图 8</span><span class="sxs-lookup"><span data-stu-id="64ba5-164">Figure 8</span></span>  
> <span data-ttu-id="64ba5-165">示例的结果 `console.info()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-165">The result of the `console.info()` example</span></span>  
> ![Console.info （）示例的结果][ImageInfo]  

## <span data-ttu-id="64ba5-167">日志</span><span class="sxs-lookup"><span data-stu-id="64ba5-167">log</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="64ba5-168">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-168">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-169">将消息打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="64ba5-169">Prints a message to the Console.</span></span>  

```javascript
console.log('log');
```  

> ##### <span data-ttu-id="64ba5-170">图 9</span><span class="sxs-lookup"><span data-stu-id="64ba5-170">Figure 9</span></span>  
> <span data-ttu-id="64ba5-171">示例的结果 `console.log()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-171">The result of the `console.log()` example</span></span>  
> ![Console 的结果（）示例][ImageLog]  

## <span data-ttu-id="64ba5-173">表</span><span class="sxs-lookup"><span data-stu-id="64ba5-173">table</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="64ba5-174">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-174">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-175">将对象数组作为表进行记录。</span><span class="sxs-lookup"><span data-stu-id="64ba5-175">Logs an array of objects as a table.</span></span>  

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

> ##### <span data-ttu-id="64ba5-176">图 10</span><span class="sxs-lookup"><span data-stu-id="64ba5-176">Figure 10</span></span>  
> <span data-ttu-id="64ba5-177">示例的结果 `console.table()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-177">The result of the `console.table()` example</span></span>  
> ![Console 的结果（）示例][ImageTable]  

## <span data-ttu-id="64ba5-179">time</span><span class="sxs-lookup"><span data-stu-id="64ba5-179">time</span></span>  

```javascript
console.time([label])
```  

<span data-ttu-id="64ba5-180">启动新的计时器。</span><span class="sxs-lookup"><span data-stu-id="64ba5-180">Starts a new timer.</span></span>  <span data-ttu-id="64ba5-181">使用[timeEnd](#timeend)方法停止计时器并将经过的时间打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="64ba5-181">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the Console.</span></span>  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

> ##### <span data-ttu-id="64ba5-182">图 11</span><span class="sxs-lookup"><span data-stu-id="64ba5-182">Figure 11</span></span>  
> <span data-ttu-id="64ba5-183">示例的结果 `console.time()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-183">The result of the `console.time()` example</span></span>  
> ![Console 的结果。 time （）示例][ImageTime]  

## <span data-ttu-id="64ba5-185">timeEnd</span><span class="sxs-lookup"><span data-stu-id="64ba5-185">timeEnd</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="64ba5-186">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-186">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-187">停止计时器。</span><span class="sxs-lookup"><span data-stu-id="64ba5-187">Stops a timer.</span></span>  <span data-ttu-id="64ba5-188">请参阅[time](#time)方法。</span><span class="sxs-lookup"><span data-stu-id="64ba5-188">See the [time](#time) method.</span></span>  

## <span data-ttu-id="64ba5-189">轨迹</span><span class="sxs-lookup"><span data-stu-id="64ba5-189">trace</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="64ba5-190">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-190">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="64ba5-191">将堆栈跟踪打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="64ba5-191">Prints a stack trace to the Console.</span></span>  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

> ##### <span data-ttu-id="64ba5-192">图 12</span><span class="sxs-lookup"><span data-stu-id="64ba5-192">Figure 12</span></span>  
> <span data-ttu-id="64ba5-193">示例的结果 `console.trace()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-193">The result of the `console.trace()` example</span></span>  
> ![Console 的结果（）示例][ImageTrace]  

## <span data-ttu-id="64ba5-195">出</span><span class="sxs-lookup"><span data-stu-id="64ba5-195">warn</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="64ba5-196">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="64ba5-196">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

<span data-ttu-id="64ba5-197">将警告打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="64ba5-197">Prints a warning to the Console.</span></span>  

```javascript
console.warn('warn');
```  

> ##### <span data-ttu-id="64ba5-198">图 13</span><span class="sxs-lookup"><span data-stu-id="64ba5-198">Figure 13</span></span>  
> <span data-ttu-id="64ba5-199">示例的结果 `console.warn()`</span><span class="sxs-lookup"><span data-stu-id="64ba5-199">The result of the `console.warn()` example</span></span>  
> ![控制台的结果。警告（）示例][ImageWarn]  

   

  

<!-- image links -->  

[ImageAssert]: /microsoft-edge/devtools-guide-chromium/media/console-demo-assert-button.msft.png "图1： console 的结果（）示例"  
[ImageCount]: /microsoft-edge/devtools-guide-chromium/media/console-demo-count-button.msft.png "图2： console 的结果（）示例"  
[ImageDebug]: /microsoft-edge/devtools-guide-chromium/media/console-demo-debug-button.msft.png "图3： console 的结果（）示例"  
[ImageDir]: /microsoft-edge/devtools-guide-chromium/media/console-demo-dir-button.msft.png "图4： dir （）示例的结果"  
[ImageDirXml]: /microsoft-edge/devtools-guide-chromium/media/console-demo-dirxml-button.msft.png "图5： dirxml （）示例的结果"  
[ImageError]: /microsoft-edge/devtools-guide-chromium/media/console-demo-error-button.msft.png "图6：控制台的结果。错误（）示例"  
[ImageGroup]: /microsoft-edge/devtools-guide-chromium/media/console-demo-group-button.msft.png "图7： console 的结果。 group （）示例"  
[ImageInfo]: /microsoft-edge/devtools-guide-chromium/media/console-demo-info-button.msft.png "图8： console.info （）示例的结果"  
[ImageLog]: /microsoft-edge/devtools-guide-chromium/media/console-demo-log-button.msft.png "图9： console 的结果（）示例"  
[ImageTable]: /microsoft-edge/devtools-guide-chromium/media/console-demo-table-button.msft.png "图10： console 的结果（）示例"  
[ImageTime]: /microsoft-edge/devtools-guide-chromium/media/console-demo-time-button.msft.png "图11：控制台的结果。 time （）示例"  
[ImageTrace]: /microsoft-edge/devtools-guide-chromium/media/console-demo-trace-button.msft.png "图12： console 的结果（）示例"  
[ImageWarn]: /microsoft-edge/devtools-guide-chromium/media/console-demo-warn-button.msft.png "图13：控制台的结果。警告（）示例"  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "在控制台中记录消息入门"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "清除控制台参考"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "跨页面加载保留消息-控制台参考"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "按日志级别筛选-控制台参考"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  

> [!NOTE]
> <span data-ttu-id="64ba5-220">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="64ba5-220">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="64ba5-221">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/api)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="64ba5-221">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="64ba5-223">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="64ba5-223">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
