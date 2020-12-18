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
# <span data-ttu-id="c5e58-103">Windows Runtime DateTime 和 TimeSpan 表示形式</span><span class="sxs-lookup"><span data-stu-id="c5e58-103">Windows Runtime DateTime and TimeSpan representations</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="c5e58-104">日期和时间的 JavaScript 表示形式与 Windows 运行时版本不同。</span><span class="sxs-lookup"><span data-stu-id="c5e58-104">The JavaScript representation of dates and times is different from the Windows Runtime version.</span></span>  <span data-ttu-id="c5e58-105">Windows 运行时 [DateTime][UwpWindowsFoundationDatetime] 结构在 JavaScript 中表示为 [具有][MDNDate] 与数据 \ (匹配的备份存储的日期，其范围和精度与 `DateTime` JavaScript `Date` \) 不同。</span><span class="sxs-lookup"><span data-stu-id="c5e58-105">The Windows Runtime [DateTime][UwpWindowsFoundationDatetime] structure is represented in JavaScript as a [Date][MDNDate] that has a backing store that matches the `DateTime` data \(and has a different range and precision from the JavaScript `Date`\).</span></span>  <span data-ttu-id="c5e58-106">如果修改此自定义 `Date` 对象，它将变为标准 JavaScript `Date` 并失去精度。</span><span class="sxs-lookup"><span data-stu-id="c5e58-106">If you modify this custom `Date` object, it becomes a standard JavaScript `Date` and loses precision.</span></span>  <span data-ttu-id="c5e58-107">JavaScript 值可以传递到 Windows 运行时，并且将被范围检查，这可能会导致 `Date` `DateTime` 封送异常。</span><span class="sxs-lookup"><span data-stu-id="c5e58-107">JavaScript `Date` values can be passed to a Windows Runtime `DateTime` and will be range-checked, which might result in marshaling exceptions.</span></span>  

 <span data-ttu-id="c5e58-108">Windows 运行时 [TimeSpan][UwpWindowsFoundationTimespan] 结构将转换为毫秒，并作为 JavaScript 数字返回。</span><span class="sxs-lookup"><span data-stu-id="c5e58-108">The Windows Runtime [TimeSpan][UwpWindowsFoundationTimespan] structure is converted to milliseconds and returned as a JavaScript number.</span></span>  

## <span data-ttu-id="c5e58-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5e58-109">See also</span></span>  

[<span data-ttu-id="c5e58-110">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="c5e58-110">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  

[UwpWindowsFoundationDatetime]: /uwp/api/Windows.Foundation.DateTime "DateTime 结构 |Microsoft Docs"  
[UwpWindowsFoundationTimespan]: /uwp/api/windows.foundation.timespan "TimeSpan 结构 |Microsoft Docs"  

[MDNDate]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date "日期 |MDN"  
