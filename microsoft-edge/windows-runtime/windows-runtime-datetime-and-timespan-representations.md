---
title: Windows Runtime DateTime 和 TimeSpan 表示形式
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime dates and times
- TimeSpan [JavaScript]
- DateTime [JavaScript]
ms.assetid: 9743e9ac-9054-463e-8264-427183e4905f
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1c51bba74bb7e5182eb25342badcae848eeba339
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942052"
---
# Windows Runtime DateTime 和 TimeSpan 表示形式  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

日期和时间的 JavaScript 表示形式与 Windows 运行时版本不同。  Windows 运行时 [日期时间][UwpWindowsFoundationDatetime] 结构在 javascript 中表示为一个日期，该 [日期][MDNDate] 具有与数据 \ (匹配的后备存储 `DateTime` ，并且从 JavaScript \ ) 具有不同的范围和精度 `Date` 。  如果你修改此自定义 `Date` 对象，它将变为标准 JavaScript `Date` 并丢失精度。  JavaScript `Date` 值可以传递到 Windows 运行时， `DateTime` 并将进行范围检查，这可能会导致封送处理异常。  

 Windows 运行时 [TimeSpan][UwpWindowsFoundationTimespan] 结构将转换为毫秒并作为 JavaScript 编号返回。  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript | 中使用 Windows 运行时Microsoft 文档"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 结构 |Microsoft 文档"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan 结构 |Microsoft 文档"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日期 |MDN"  
