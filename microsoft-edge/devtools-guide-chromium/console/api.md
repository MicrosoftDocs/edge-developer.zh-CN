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

# <a name="console-api-reference"></a>控制台 API 参考  

使用控制台 API 方法从 JavaScript 将消息写入控制台。  有关主题的交互式简介，请导航到["开始使用将消息记录到控制台"。][DevtoolsConsoleLog]  对于控制台窗格中的方便方法，例如或仅提供这些方法， `debug()` `monitorEvents()` 请导航到[控制台实用工具 API 参考][DevtoolConsoleUtilities]。 ****  

---  

## <a name="assert"></a>assert  

```javascript
console.assert(expression, object)
```

[日志级别][DevtoolsConsoleReferencePersist]： `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

计算 [结果](#error) 为 时，将错误 `expression` 写入控制台 `false` 。  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="console.assert 示例 () 结果" lightbox="../media/console-demo-assert-button.msft.png":::
   图 1：示例 `console.assert()` 的结果  
:::image-end:::  

---  

## <a name="clear"></a>clear  

```javascript
console.clear()
```

清除控制台。  

```javascript
console.clear();  
```  

如果 [启用"][DevtoolsConsoleReferenceLevel] 保留日志"， [则禁用清除](#clear) 方法。  

### <a name="see-also"></a>另请参阅  

*   [清除控制台][DevtoolsConsoleReferenceClear]  

---  

## <a name="count"></a>count  

```javascript
console.count([label])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

写入在同一行和同一行上调用 [count](#count) 方法次数 `label` 。  使用 [countReset](#countreset) 方法重置计数。  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="console.count 示例 () 结果" lightbox="../media/console-demo-count-button.msft.png":::
   图 2：示例 `console.count()` 的结果  
:::image-end:::  

---  

## <a name="countreset"></a>countReset  

```javascript
console.countReset([label])
```  

重置计数。  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## <a name="debug"></a>调试  

```javascript
console.debug(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Verbose`

与日志 [相同，](#log) 不同日志级别除外。  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="console.debug 示例 () 结果" lightbox="../media/console-demo-debug-button.msft.png":::
   图 3：示例 `console.debug()` 的结果  
:::image-end:::  

---  

## <a name="dir"></a>dir  

```javascript
console.dir(object)
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

打印指定对象的 JSON 表示形式。  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="console.dir 示例 () 结果" lightbox="../media/console-demo-dir-button.msft.png":::
   图 4：示例 `console.dir()` 的结果  
:::image-end:::  

---  

## <a name="dirxml"></a>dirxml  

```javascript
console.dirxml(node)
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

打印的后代的 XML 表示形式 `node` 。  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="console.dirxml 示例 () 结果" lightbox="../media/console-demo-dirxml-button.msft.png":::
   图 5：示例 `console.dirxml()` 的结果  
:::image-end:::  

---  

## <a name="error"></a>错误  

```javascript
console.error(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Error`  

将输出 `object` 到控制台，将它格式化为错误，并包括堆栈跟踪。  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="console.error 示例 () 结果" lightbox="../media/console-demo-error-button.msft.png":::
   图 6：示例 `console.error()` 的结果  
:::image-end:::  

---  

## <a name="group"></a>组  

```javascript
console.group(label)
```  

直观地将邮件分组在一起，直到 [使用 groupEnd](#groupend) 方法。  使用 [groupCollapsed](#groupcollapsed) 方法在组最初记录到控制台时折叠该组。  

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
   图 7：示例 `console.group()` 的结果  
:::image-end:::  

---  

## <a name="groupcollapsed"></a>groupCollapsed  

```javascript
console.groupCollapsed(label)
```  

与日志 [方法相同](#log) ，但组在记录到控制台时最初折叠。  

---  

## <a name="groupend"></a>groupEnd  

```javascript
console.groupEnd(label)
```  

停止以可视方式对邮件进行分组。  导航到 [组](#group) 方法。  

---  

## <a name="info"></a>“信息”  

```javascript
console.info(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

与日志 [方法](#log) 相同。  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="示例console.info () 结果" lightbox="../media/console-demo-info-button.msft.png":::
   图 8：示例 `console.info()` 的结果  
:::image-end:::  

---  

## <a name="log"></a>日志  

```javascript
console.log(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

将消息打印到控制台。  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="console.log 示例 () 结果" lightbox="../media/console-demo-log-button.msft.png":::
   图 9：示例 `console.log()` 的结果  
:::image-end:::  

---  

## <a name="table"></a>table  

```javascript
console.table(array)
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

将对象数组记录为表。  

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
   图 10：示例 `console.table()` 的结果  
:::image-end:::  

---  

## <a name="time"></a>time  

```javascript
console.time([label])
```  

启动新计时器。  使用 [timeEnd](#timeend) 方法停止计时器，将已用时间打印到控制台。  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="console.time 示例 () 结果" lightbox="../media/console-demo-time-button.msft.png":::
   图 11：示例 `console.time()` 的结果  
:::image-end:::  

---  

## <a name="timeend"></a>timeEnd  

```javascript
console.timeEnd([label])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Info`  

停止计时器。  导航到 [时间](#time) 方法。  

---  

## <a name="trace"></a>trace  

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

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="console.trace 示例 () 结果" lightbox="../media/console-demo-trace-button.msft.png":::
   图 12：示例 `console.trace()` 的结果  
:::image-end:::  

---  

## <a name="warn"></a>warn  

```javascript
console.warn(object [, object, ...])
```  

[日志级别][DevtoolsConsoleReferencePersist]： `Warning`  

向控制台打印警告。  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="console.warn 示例 () 结果" lightbox="../media/console-demo-warn-button.msft.png":::
   图 13：示例 `console.warn()` 的结果  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "开始在控制台中记录消息"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "清除控制台 - 控制台参考"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "跨页面加载保留消息 - 控制台参考"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "按日志级别筛选 - 控制台参考"  

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
