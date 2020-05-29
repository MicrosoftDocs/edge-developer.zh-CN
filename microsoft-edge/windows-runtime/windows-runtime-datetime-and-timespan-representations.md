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
# <span data-ttu-id="654d9-102">Windows 运行时日期时间和时间跨度表示形式</span><span class="sxs-lookup"><span data-stu-id="654d9-102">Windows Runtime DateTime and TimeSpan Representations</span></span>  

<span data-ttu-id="654d9-103">日期和时间的 JavaScript 表示形式与 Windows 运行时版本不同。</span><span class="sxs-lookup"><span data-stu-id="654d9-103">The JavaScript representation of dates and times is different from the Windows Runtime version.</span></span>  <span data-ttu-id="654d9-104">Windows 运行时[日期时间][UwpWindowsFoundationDatetime]结构在 javascript 中表示为具有与数据匹配的后备应用商店的[日期][MDNDate] `DateTime` \ （并与 JavaScript \ 的范围和精度不同 `Date` ）。</span><span class="sxs-lookup"><span data-stu-id="654d9-104">The Windows Runtime [DateTime][UwpWindowsFoundationDatetime] structure is represented in JavaScript as a [Date][MDNDate] that has a backing store that matches the `DateTime` data \(and has a different range and precision from the JavaScript `Date`\).</span></span>  <span data-ttu-id="654d9-105">如果你修改此自定义 `Date` 对象，它将变为标准 JavaScript `Date` 并丢失精度。</span><span class="sxs-lookup"><span data-stu-id="654d9-105">If you modify this custom `Date` object, it becomes a standard JavaScript `Date` and loses precision.</span></span>  <span data-ttu-id="654d9-106">JavaScript `Date` 值可以传递到 Windows 运行时， `DateTime` 并将进行范围检查，这可能会导致封送处理异常。</span><span class="sxs-lookup"><span data-stu-id="654d9-106">JavaScript `Date` values can be passed to a Windows Runtime `DateTime` and will be range-checked, which might result in marshaling exceptions.</span></span>  

 <span data-ttu-id="654d9-107">Windows 运行时[TimeSpan][UwpWindowsFoundationTimespan]结构将转换为毫秒并作为 JavaScript 编号返回。</span><span class="sxs-lookup"><span data-stu-id="654d9-107">The Windows Runtime [TimeSpan][UwpWindowsFoundationTimespan] structure is converted to milliseconds and returned as a JavaScript number.</span></span>  

## <span data-ttu-id="654d9-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="654d9-108">See Also</span></span>  

[<span data-ttu-id="654d9-109">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="654d9-109">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "在 JavaScript 中使用 Windows 运行时"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 结构"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan 结构"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日期 |MDN"  
