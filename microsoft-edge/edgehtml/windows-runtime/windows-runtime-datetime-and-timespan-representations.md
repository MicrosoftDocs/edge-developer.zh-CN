---
description: Windows Runtime DateTime 和 TimeSpan 表示形式
title: Windows Runtime DateTime 和 TimeSpan 表示形式
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime dates and times
- TimeSpan [JavaScript]
- DateTime [JavaScript]
ms.assetid: 9743e9ac-9054-463e-8264-427183e4905f
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1ee3d601e727601aba03f2ff7efa532171b8f815
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232312"
---
# Windows Runtime DateTime 和 TimeSpan 表示形式  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

日期和时间的 JavaScript 表示形式与 Windows 运行时版本不同。  Windows 运行时 [DateTime][UwpWindowsFoundationDatetime] 结构在 JavaScript 中表示为 [具有][MDNDate] 与数据 \ (匹配的备份存储的日期，其范围和精度与 `DateTime` JavaScript `Date` \) 不同。  如果修改此自定义 `Date` 对象，它将变为标准 JavaScript `Date` 并失去精度。  JavaScript 值可以传递到 Windows 运行时，并且将被范围检查，这可能会导致 `Date` `DateTime` 封送异常。  

 Windows 运行时 [TimeSpan][UwpWindowsFoundationTimespan] 结构将转换为毫秒，并作为 JavaScript 数字返回。  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 结构 |Microsoft Docs"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan 结构 |Microsoft Docs"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日期 |MDN"  
