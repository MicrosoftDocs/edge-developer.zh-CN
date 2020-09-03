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

# 控制台 API 参考  

使用控制台 API 方法将消息从 JavaScript 写入控制台。  有关主题的交互式介绍，请参阅将 [消息记录到控制台的入门][DevtoolsConsoleLog]。  对于 `debug()` `monitorEvents()` 仅在 " **控制台** " 窗格中可用的便利方法，请参阅 [控制台实用工具 API 参考][DevtoolConsoleUtilities]。  

---  

## 声明  

```javascript
console.assert(expression, object)
```

[日志级别][DevtoolsConsoleReferencePersist]： `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

当计算结果为时，将 [错误](#error) 写入控制台 `expression` `false` 。  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="控制台的结果。 assert ( # A1 示例" lightbox="../media/console-demo-assert-button.msft.png":::
   图1：示例的结果 `console.assert()`  
:::image-end:::  

---  

## 消除  

```javascript
console.clear()
```

清除控制台。  

```javascript
console.clear();  
```  

如果 " [保留日志][DevtoolsConsoleReferenceLevel] " 已启用， [clear](#clear) 方法将被禁用。  

### 另请参阅  

*   [清除控制台][DevtoolsConsoleReferenceClear]  

---  

## 盘点  

```javascript
console.count([label])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

写入在同一行和同一行调用 [count](#count) 方法的次数 `label` 。  使用 [countReset](#countreset) 方法重置计数。  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="Console 的结果。 count ( # A1 示例" lightbox="../media/console-demo-count-button.msft.png":::
   图2：示例的结果 `console.count()`  
:::image-end:::  

---  

## countReset  

```javascript
console.countReset([label])
```  

重置计数。  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## 调试  

```javascript
console.debug(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Verbose`

除了不同日志级别的 [日志](#log) 一样。  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="控制台的结果。 debug ( # A1 示例" lightbox="../media/console-demo-debug-button.msft.png":::
   图3：示例的结果 `console.debug()`  
:::image-end:::  

---  

## dir  

```javascript
console.dir(object)
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

打印指定对象的 JSON 表示形式。  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="Console 的结果 ( # A1 示例" lightbox="../media/console-demo-dir-button.msft.png":::
   图4：示例的结果 `console.dir()`  
:::image-end:::  

---  

## dirxml  

```javascript
console.dirxml(node)
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

打印的子代的 XML 表示形式 `node` 。  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="Dirxml 的结果 ( # A1 示例" lightbox="../media/console-demo-dirxml-button.msft.png":::
   图5：示例的结果 `console.dirxml()`  
:::image-end:::  

---  

## 错误  

```javascript
console.error(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Error`  

`object`将文件打印到控制台，将其格式设置为错误，并包含堆栈跟踪。  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="控制台的结果。错误 ( # A1 示例" lightbox="../media/console-demo-error-button.msft.png":::
   图6：示例的结果 `console.error()`  
:::image-end:::  

---  

## 组  

```javascript
console.group(label)
```  

在使用 [groupEnd](#groupend) 方法之前，直观地将邮件分组到一起。  使用 [groupCollapsed](#groupcollapsed) 方法可在初始记录到控制台时折叠组。  

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
   图7：示例的结果 `console.group()`  
:::image-end:::  

---  

## groupCollapsed  

```javascript
console.groupCollapsed(label)
```  

除了在将组记录到控制台时，组初始折叠外，还与 [log](#log) 方法相同。  

---  

## groupEnd  

```javascript
console.groupEnd(label)
```  

停止直观地对邮件进行分组。  请参阅 [群组](#group) 方法。  

---  

## “信息”  

```javascript
console.info(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

与 [log](#log) 方法相同。  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="Console.info 的结果 ( # A1 示例" lightbox="../media/console-demo-info-button.msft.png":::
   图8：示例的结果 `console.info()`  
:::image-end:::  

---  

## 日志  

```javascript
console.log(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

将消息打印到控制台。  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="Console 的结果 ( # A1 示例" lightbox="../media/console-demo-log-button.msft.png":::
   图9：示例的结果 `console.log()`  
:::image-end:::  

---  

## 表  

```javascript
console.table(array)
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

将对象数组作为表进行记录。  

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
   图10：示例的结果 `console.table()`  
:::image-end:::  

---  

## time  

```javascript
console.time([label])
```  

启动新的计时器。  使用 [timeEnd](#timeend) 方法停止计时器并将经过的时间打印到控制台。  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="控制台的结果。时间 ( # A1 示例" lightbox="../media/console-demo-time-button.msft.png":::
   图11：示例的结果 `console.time()`  
:::image-end:::  

---  

## timeEnd  

```javascript
console.timeEnd([label])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

停止计时器。  请参阅 [time](#time) 方法。  

---  

## 轨迹  

```javascript
console.trace()
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

将堆栈跟踪打印到控制台。  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="控制台的结果。跟踪 ( # A1 示例" lightbox="../media/console-demo-trace-button.msft.png":::
   图12：示例的结果 `console.trace()`  
:::image-end:::  

---  

## 出  

```javascript
console.warn(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Warning`  

将警告打印到控制台。  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="控制台的结果。警告 ( # A1 示例" lightbox="../media/console-demo-warn-button.msft.png":::
   图13：示例的结果 `console.warn()`  
:::image-end:::  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "在控制台中记录消息入门"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "清除控制台参考"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "跨页面加载保留消息-控制台参考"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "按日志级别筛选-控制台参考"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/api)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
