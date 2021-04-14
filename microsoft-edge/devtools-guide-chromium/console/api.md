---
description: 使用控制台 API 将消息写入控制台。
title: 控制台 API 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 54b89e25501449a1e5119afa812a0535fbc6ffbb
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483252"
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
# <a name="console-api-reference"></a><span data-ttu-id="24361-104">控制台 API 参考</span><span class="sxs-lookup"><span data-stu-id="24361-104">Console API reference</span></span>  

<span data-ttu-id="24361-105">当你 **在** DevTools 中完成多个任务时，控制台工具非常有用。</span><span class="sxs-lookup"><span data-stu-id="24361-105">The **Console** tool is helpful when you complete multiple tasks in the DevTools.</span></span>  <span data-ttu-id="24361-106">API 可以包括在脚本中。</span><span class="sxs-lookup"><span data-stu-id="24361-106">APIs are available to include in your scripts.</span></span> <span data-ttu-id="24361-107">便利方法仅在控制台工具 **（** 如 和 方法） `debug()` `monitorEvents()` 中可用。</span><span class="sxs-lookup"><span data-stu-id="24361-107">Convenience methods are only available for use in the **Console** tool, such as the `debug()` and `monitorEvents()` methods.</span></span>  <span data-ttu-id="24361-108">有关控制台入门的信息，请导航到\*\*\*\* 开始将消息记录[到控制台][DevtoolsConsoleConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="24361-108">For more information on getting started with the **Console**, navigate to [Get started with logging messages to the Console][DevtoolsConsoleConsoleLog].</span></span>  <span data-ttu-id="24361-109">有关控制台中便利方法详细信息 **，** 请导航到"[控制台实用程序 API 参考"。][DevtoolConsoleUtilities]</span><span class="sxs-lookup"><span data-stu-id="24361-109">For more information on the convenience methods in the **Console**, navigate to [Console Utilities API Reference][DevtoolConsoleUtilities].</span></span>  

---  

## <a name="assert"></a><span data-ttu-id="24361-110">assert</span><span class="sxs-lookup"><span data-stu-id="24361-110">assert</span></span>  

<span data-ttu-id="24361-111">此方法在计算[结果为](#error)**时将**错误 `expression` 写入控制台 `false` 。</span><span class="sxs-lookup"><span data-stu-id="24361-111">This method writes an [error](#error) to the **Console** when `expression` evaluates to `false`.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-112">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-112">JavaScript syntax</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="24361-113">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-113">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

### <a name="javascript-example"></a><span data-ttu-id="24361-114">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-114">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-115">输入</span><span class="sxs-lookup"><span data-stu-id="24361-115">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      const x = 5;
      const y = 3;
      const reason = 'x is expected to be less than y';
      console.assert(x < y, {x, y, reason});
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-116">输出</span><span class="sxs-lookup"><span data-stu-id="24361-116">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="console.assert 示例 () 结果" lightbox="../media/console-demo-assert-button.msft.png":::
         <span data-ttu-id="24361-118">示例 `console.assert()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-118">The result of the `console.assert()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="clear"></a><span data-ttu-id="24361-119">clear</span><span class="sxs-lookup"><span data-stu-id="24361-119">clear</span></span>  

<span data-ttu-id="24361-120">此方法 **清除控制台**。</span><span class="sxs-lookup"><span data-stu-id="24361-120">This method clears the **Console**.</span></span>  

<span data-ttu-id="24361-121">如果 [打开][DevtoolsConsoleReferenceFilter] "保留日志"，则 [清除](#clear) 方法将关闭。</span><span class="sxs-lookup"><span data-stu-id="24361-121">If [Preserve Log][DevtoolsConsoleReferenceFilter] is turned on, the [clear](#clear) method is turned off.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-122">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-122">JavaScript syntax</span></span>  

```javascript
console.clear()
```

### <a name="javascript-example"></a><span data-ttu-id="24361-123">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-123">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-124">输入</span><span class="sxs-lookup"><span data-stu-id="24361-124">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.clear();  
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-125">输出</span><span class="sxs-lookup"><span data-stu-id="24361-125">Output</span></span>
   :::column-end:::
   :::column span="3":::
      
   :::column-end:::
:::row-end:::  

### <a name="see-also"></a><span data-ttu-id="24361-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24361-126">See also</span></span>  

*   [<span data-ttu-id="24361-127">清除控制台</span><span class="sxs-lookup"><span data-stu-id="24361-127">Clear the Console</span></span>][DevtoolsConsoleReferenceClear]  

---  

## <a name="count"></a><span data-ttu-id="24361-128">count</span><span class="sxs-lookup"><span data-stu-id="24361-128">count</span></span>  

<span data-ttu-id="24361-129">此方法写入在同一行和使用相同的 调用 [count](#count) 方法次数 `label` 。</span><span class="sxs-lookup"><span data-stu-id="24361-129">This method writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="24361-130">使用 [countReset](#countreset) 方法可重置计数。</span><span class="sxs-lookup"><span data-stu-id="24361-130">Use the [countReset](#countreset) method to reset the count.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-131">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-131">JavaScript syntax</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="24361-132">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-132">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="24361-133">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-133">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-134">输入</span><span class="sxs-lookup"><span data-stu-id="24361-134">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.count();
      console.count('coffee');
      console.count();
      console.count();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-135">输出</span><span class="sxs-lookup"><span data-stu-id="24361-135">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="console.count 示例 () 结果" lightbox="../media/console-demo-count-button.msft.png":::
         <span data-ttu-id="24361-137">示例 `console.count()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-137">The result of the `console.count()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="countreset"></a><span data-ttu-id="24361-138">countReset</span><span class="sxs-lookup"><span data-stu-id="24361-138">countReset</span></span>  

<span data-ttu-id="24361-139">此方法重置计数。</span><span class="sxs-lookup"><span data-stu-id="24361-139">This method resets a count.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-140">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-140">JavaScript syntax</span></span>  

```javascript
console.countReset([label])
```  

### <a name="javascript-example"></a><span data-ttu-id="24361-141">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-141">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-142">输入</span><span class="sxs-lookup"><span data-stu-id="24361-142">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.countReset();
      console.countReset('coffee');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-143">输出</span><span class="sxs-lookup"><span data-stu-id="24361-143">Output</span></span>
   :::column-end:::
   :::column span="3":::
      
   :::column-end:::
:::row-end:::  

---  

## <a name="debug"></a><span data-ttu-id="24361-144">调试</span><span class="sxs-lookup"><span data-stu-id="24361-144">debug</span></span>  

<span data-ttu-id="24361-145">此方法与日志方法 [相同](#log) ，不同日志级别除外。</span><span class="sxs-lookup"><span data-stu-id="24361-145">This method is identical to the [log](#log) method, except different log level.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-146">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-146">JavaScript syntax</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="24361-147">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-147">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Verbose`  

### <a name="javascript-example"></a><span data-ttu-id="24361-148">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-148">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-149">输入</span><span class="sxs-lookup"><span data-stu-id="24361-149">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.debug('debug');  
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-150">输出</span><span class="sxs-lookup"><span data-stu-id="24361-150">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="console.debug 示例 () 结果" lightbox="../media/console-demo-debug-button.msft.png":::
         <span data-ttu-id="24361-152">示例 `console.debug()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-152">The result of the `console.debug()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="dir"></a><span data-ttu-id="24361-153">dir</span><span class="sxs-lookup"><span data-stu-id="24361-153">dir</span></span>  

<span data-ttu-id="24361-154">此方法打印指定对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="24361-154">This method prints a JSON representation of the specified object.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-155">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-155">JavaScript syntax</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="24361-156">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-156">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="24361-157">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-157">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-158">输入</span><span class="sxs-lookup"><span data-stu-id="24361-158">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.dir(document.head);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-159">输出</span><span class="sxs-lookup"><span data-stu-id="24361-159">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="console.dir 示例 () 结果" lightbox="../media/console-demo-dir-button.msft.png":::
         <span data-ttu-id="24361-161">示例 `console.dir()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-161">The result of the `console.dir()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="dirxml"></a><span data-ttu-id="24361-162">dirxml</span><span class="sxs-lookup"><span data-stu-id="24361-162">dirxml</span></span>  

<span data-ttu-id="24361-163">此方法打印 后代的 XML 表示形式 `node` 。</span><span class="sxs-lookup"><span data-stu-id="24361-163">This method prints an XML representation of the descendants of `node`.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-164">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-164">JavaScript syntax</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="24361-165">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-165">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="24361-166">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-166">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-167">输入</span><span class="sxs-lookup"><span data-stu-id="24361-167">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.dirxml(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-168">输出</span><span class="sxs-lookup"><span data-stu-id="24361-168">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="console.dirxml 示例 () 结果" lightbox="../media/console-demo-dirxml-button.msft.png":::
         <span data-ttu-id="24361-170">示例 `console.dirxml()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-170">The result of the `console.dirxml()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="error"></a><span data-ttu-id="24361-171">错误</span><span class="sxs-lookup"><span data-stu-id="24361-171">error</span></span>  

<span data-ttu-id="24361-172">此方法将 打印 `object` 到 **控制台**，将格式设置为错误，并包括堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="24361-172">This method prints the `object` to the **Console**, formats it as an error, and includes a stack trace.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-173">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-173">JavaScript syntax</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="24361-174">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-174">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

### <a name="javascript-example"></a><span data-ttu-id="24361-175">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-175">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-176">输入</span><span class="sxs-lookup"><span data-stu-id="24361-176">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-177">输出</span><span class="sxs-lookup"><span data-stu-id="24361-177">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="console.error 示例 () 结果" lightbox="../media/console-demo-error-button.msft.png":::
         <span data-ttu-id="24361-179">示例 `console.error()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-179">The result of the `console.error()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="group"></a><span data-ttu-id="24361-180">组</span><span class="sxs-lookup"><span data-stu-id="24361-180">group</span></span>  

<span data-ttu-id="24361-181">此方法直观地将邮件分组在一起，直到 [使用 groupEnd](#groupend) 方法。</span><span class="sxs-lookup"><span data-stu-id="24361-181">This method visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="24361-182">使用 [groupCollapsed](#groupcollapsed) 方法可折叠最初记录到控制台的 **组**。</span><span class="sxs-lookup"><span data-stu-id="24361-182">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it initially logs to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-183">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-183">JavaScript syntax</span></span>  

```javascript
console.group(label)
```  

### <a name="javascript-example"></a><span data-ttu-id="24361-184">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-184">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-185">输入</span><span class="sxs-lookup"><span data-stu-id="24361-185">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      const label = 'Adolescent Irradiated Espionage Tortoises';
      console.group(label);
      console.info('Leo');
      console.info('Mike');
      console.info('Don');
      console.info('Raph');
      console.groupEnd(label);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-186">输出</span><span class="sxs-lookup"><span data-stu-id="24361-186">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="console.group 示例 () 结果" lightbox="../media/console-demo-group-button.msft.png":::
         <span data-ttu-id="24361-188">示例 `console.group()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-188">The result of the `console.group()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="groupcollapsed"></a><span data-ttu-id="24361-189">groupCollapsed</span><span class="sxs-lookup"><span data-stu-id="24361-189">groupCollapsed</span></span>  

<span data-ttu-id="24361-190">此方法与日志[方法相同，](#log)但组最初在记录到控制台**时折叠。**</span><span class="sxs-lookup"><span data-stu-id="24361-190">This method is identical to the [log](#log) method, except the group is initially collapsed when it logs to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-191">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-191">JavaScript syntax</span></span>  

```javascript
console.groupCollapsed(label)
```  

---  

## <a name="groupend"></a><span data-ttu-id="24361-192">groupEnd</span><span class="sxs-lookup"><span data-stu-id="24361-192">groupEnd</span></span>  

<span data-ttu-id="24361-193">此方法停止对邮件进行视觉分组。</span><span class="sxs-lookup"><span data-stu-id="24361-193">This method stops visually grouping messages.</span></span>  <span data-ttu-id="24361-194">导航到 [group](#group) 方法。</span><span class="sxs-lookup"><span data-stu-id="24361-194">Navigate to the [group](#group) method.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-195">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-195">JavaScript syntax</span></span>  

```javascript
console.groupEnd(label)
```  

---  

## <a name="info"></a><span data-ttu-id="24361-196">信息</span><span class="sxs-lookup"><span data-stu-id="24361-196">info</span></span>  

<span data-ttu-id="24361-197">此方法与 log 方法[相同。](#log)</span><span class="sxs-lookup"><span data-stu-id="24361-197">This method is identical to the [log](#log) method.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-198">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-198">JavaScript syntax</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="24361-199">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-199">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="24361-200">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-200">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-201">输入</span><span class="sxs-lookup"><span data-stu-id="24361-201">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.info('info');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-202">输出</span><span class="sxs-lookup"><span data-stu-id="24361-202">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="示例 console.info () 结果" lightbox="../media/console-demo-info-button.msft.png":::
         <span data-ttu-id="24361-204">示例 `console.info()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-204">The result of the `console.info()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="log"></a><span data-ttu-id="24361-205">日志</span><span class="sxs-lookup"><span data-stu-id="24361-205">log</span></span>  

<span data-ttu-id="24361-206">此方法将一条消息打印到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="24361-206">This method prints a message to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-207">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-207">JavaScript syntax</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="24361-208">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-208">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="24361-209">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-209">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-210">输入</span><span class="sxs-lookup"><span data-stu-id="24361-210">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.log('log');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-211">输出</span><span class="sxs-lookup"><span data-stu-id="24361-211">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="console.log 示例 () 结果" lightbox="../media/console-demo-log-button.msft.png":::
         <span data-ttu-id="24361-213">示例 `console.log()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-213">The result of the `console.log()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a><span data-ttu-id="24361-214">table</span><span class="sxs-lookup"><span data-stu-id="24361-214">table</span></span>  

<span data-ttu-id="24361-215">此方法将对象数组记录为表。</span><span class="sxs-lookup"><span data-stu-id="24361-215">This method logs an array of objects as a table.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-216">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-216">JavaScript syntax</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="24361-217">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-217">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="24361-218">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-218">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-219">输入</span><span class="sxs-lookup"><span data-stu-id="24361-219">Input</span></span>  
   :::column-end:::
   :::column span="3":::
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
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-220">输出</span><span class="sxs-lookup"><span data-stu-id="24361-220">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="console.table 示例 () 结果" lightbox="../media/console-demo-table-button.msft.png":::
         <span data-ttu-id="24361-222">示例 `console.table()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-222">The result of the `console.table()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="time"></a><span data-ttu-id="24361-223">time</span><span class="sxs-lookup"><span data-stu-id="24361-223">time</span></span>  

<span data-ttu-id="24361-224">此方法启动一个新的计时器。</span><span class="sxs-lookup"><span data-stu-id="24361-224">This method starts a new timer.</span></span>  <span data-ttu-id="24361-225">使用 [timeEnd](#timeend) 方法停止计时器，将已用时间打印到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="24361-225">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-226">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-226">JavaScript syntax</span></span>  

```javascript
console.time([label])
```  

### <a name="javascript-example"></a><span data-ttu-id="24361-227">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-227">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-228">输入</span><span class="sxs-lookup"><span data-stu-id="24361-228">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.time();
      for (var i = 0; i < 100000; i++) {
          let square = i ** 2;
      }
      console.timeEnd();
      ```
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-229">输出</span><span class="sxs-lookup"><span data-stu-id="24361-229">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="console.time 示例 () 结果" lightbox="../media/console-demo-time-button.msft.png":::
         <span data-ttu-id="24361-231">示例 `console.time()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-231">The result of the `console.time()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="timeend"></a><span data-ttu-id="24361-232">timeEnd</span><span class="sxs-lookup"><span data-stu-id="24361-232">timeEnd</span></span>  

<span data-ttu-id="24361-233">此方法将停止计时器。</span><span class="sxs-lookup"><span data-stu-id="24361-233">This method stops a timer.</span></span>  <span data-ttu-id="24361-234">有关详细信息，请导航到 [time](#time) 方法。</span><span class="sxs-lookup"><span data-stu-id="24361-234">For more information, navigate to the [time](#time) method.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-235">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-235">JavaScript syntax</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="24361-236">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-236">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

---  

## <a name="trace"></a><span data-ttu-id="24361-237">trace</span><span class="sxs-lookup"><span data-stu-id="24361-237">trace</span></span>  

<span data-ttu-id="24361-238">此方法将堆栈跟踪打印到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="24361-238">This method prints a stack trace to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-239">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-239">JavaScript syntax</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="24361-240">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-240">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="24361-241">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-241">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-242">输入</span><span class="sxs-lookup"><span data-stu-id="24361-242">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      const first = () => { second(); };
      const second = () => { third(); };
      const third = () => { fourth(); };
      const fourth = () => { console.trace(); };
      first();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-243">输出</span><span class="sxs-lookup"><span data-stu-id="24361-243">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="console.trace 示例 () 结果" lightbox="../media/console-demo-trace-button.msft.png":::
         <span data-ttu-id="24361-245">示例 `console.trace()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-245">The result of the `console.trace()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="warn"></a><span data-ttu-id="24361-246">warn</span><span class="sxs-lookup"><span data-stu-id="24361-246">warn</span></span>  

<span data-ttu-id="24361-247">此方法将警告输出到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="24361-247">This method prints a warning to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="24361-248">JavaScript 语法</span><span class="sxs-lookup"><span data-stu-id="24361-248">JavaScript syntax</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="24361-249">[日志级别][DevtoolsConsoleReferencePersist]：</span><span class="sxs-lookup"><span data-stu-id="24361-249">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

### <a name="javascript-example"></a><span data-ttu-id="24361-250">JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="24361-250">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-251">输入</span><span class="sxs-lookup"><span data-stu-id="24361-251">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.warn('warn');
      ```
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="24361-252">输出</span><span class="sxs-lookup"><span data-stu-id="24361-252">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="console.warn 示例 () 结果" lightbox="../media/console-demo-warn-button.msft.png":::
         <span data-ttu-id="24361-254">示例 `console.warn()` 结果</span><span class="sxs-lookup"><span data-stu-id="24361-254">The result of the `console.warn()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="24361-255">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="24361-255">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleLog]: ./console-log.md "控制台工具控制台中的|Microsoft Docs"  
[DevtoolConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考|Microsoft Docs"  
[DevtoolsConsoleReferenceClear]: ./reference.md#clear-the-console "清除控制台 - 控制台|Microsoft Docs"  
[DevtoolsConsoleReferenceFilter]: ./reference.md#filter-by-log-level "按日志级别筛选 - 控制台参考 | Microsoft Docs"  
[DevtoolsConsoleReferencePersist]: ./reference.md#persist-messages-across-page-loads "跨页面加载保留消息 - 控制台参考|Microsoft Docs"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具概述 | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="24361-262">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="24361-262">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="24361-263">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/api)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="24361-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="24361-265">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="24361-265">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
