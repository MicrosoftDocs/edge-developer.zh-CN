---
title: Windows 运行时日期时间和时间跨度表示形式
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: d3e138493b80face1238118a99c03f6015a6a8ef
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564574"
---
# Windows 运行时日期时间和时间跨度表示形式  

日期和时间的 JavaScript 表示形式与 Windows 运行时版本不同。  Windows 运行时[日期时间][UwpWindowsFoundationDatetime]结构在 javascript 中表示为具有与数据匹配的后备应用商店的[日期][MDNDate] `DateTime` \ （并与 JavaScript \ 的范围和精度不同 `Date` ）。  如果你修改此自定义 `Date` 对象，它将变为标准 JavaScript `Date` 并丢失精度。  JavaScript `Date` 值可以传递到 Windows 运行时， `DateTime` 并将进行范围检查，这可能会导致封送处理异常。  

 Windows 运行时[TimeSpan][UwpWindowsFoundationTimespan]结构将转换为毫秒并作为 JavaScript 编号返回。  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "在 JavaScript 中使用 Windows 运行时"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 结构"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan 结构"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日期 |MDN"  
