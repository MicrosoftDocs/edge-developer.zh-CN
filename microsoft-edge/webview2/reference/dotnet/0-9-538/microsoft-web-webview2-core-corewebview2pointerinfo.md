---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2PointerInfo 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 8a5e5f4188b5115e1c6b836f80aad69c4bf2da7e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878755"
---
# CoreWebView2PointerInfo 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[ButtonChangeKind](#buttonchangekind) | 指针事件的 ButtonChangeKind。
[DisplayRect](#displayrect) | 在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。
[FrameId](#frameid) | 指针事件的 FrameID。
[HimetricLocation](#himetriclocation) | 指针事件的 HimetricLocation。
[HimetricLocationRaw](#himetriclocationraw) | 指针事件的 HimetricLocationRaw。
[HistoryCount](#historycount) | 指针事件的 HistoryCount。
[InputData](#inputdata) | 指针事件的 InputData。
[KeyStates](#keystates) | 指针事件的 KeyStates。
[PenFlags](#penflags) | 指针事件的 PenFlags。
[PenMask](#penmask) | 指针事件的 PenMask。
[PenPressure](#penpressure) | 指针事件的 PenPressure。
[PenRotation](#penrotation) | 指针事件的 PenRotation。
[PenTiltX](#pentiltx) | 指针事件的 PenTiltX。
[PenTiltY](#pentilty) | 指针事件的 PenTiltY。
[PerformanceCount](#performancecount) | 指针事件的 PerformanceCount。
[PixelLocation](#pixellocation) | 指针事件的 PixelLocation。
[PixelLocationRaw](#pixellocationraw) | 指针事件的 PixelLocationRaw。
[PointerDeviceRect](#pointerdevicerect) | 在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。
[PointerFlags](#pointerflags) | 指针事件的 PointerFlags。
[PointerId](#pointerid) | 指针事件的 PointerId。
[PointerKind](#pointerkind) | 指针事件的 PointerKind。
[时间](#time) | 指针事件的时间。
[TouchContact](#touchcontact) | 指针事件的 TouchContact。
[TouchContactRaw](#touchcontactraw) | 指针事件的 TouchContactRaw。
[TouchFlags](#touchflags) | 指针事件的 TouchFlags。
[TouchMask](#touchmask) | 指针事件的 TouchMask。
[TouchOrientation](#touchorientation) | 指针事件的 TouchOrientation。
[TouchPressure](#touchpressure) | 指针事件的 TouchPressure。

## 成员

#### ButtonChangeKind 

指针事件的 ButtonChangeKind。

> 公共 int [ButtonChangeKind](#buttonchangekind)

这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。 这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。

#### DisplayRect 

在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。

> 公共矩形[DisplayRect](#displayrect)

#### FrameId 

指针事件的 FrameID。

> 公共 uint [FrameId](#frameid)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。

#### HimetricLocation 

指针事件的 HimetricLocation。

> 公共点[HimetricLocation](#himetriclocation)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。

#### HimetricLocationRaw 

指针事件的 HimetricLocationRaw。

> 公共点[HimetricLocationRaw](#himetriclocationraw)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。

#### HistoryCount 

指针事件的 HistoryCount。

> 公共 uint [HistoryCount](#historycount)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。

#### InputData 

指针事件的 InputData。

> 公共 int [InputData](#inputdata)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。

#### KeyStates 

指针事件的 KeyStates。

> 公共 uint [KeyStates](#keystates)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。

#### PenFlags 

指针事件的 PenFlags。

> 公共 uint [PenFlags](#penflags)

这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。 这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。

#### PenMask 

指针事件的 PenMask。

> 公共 uint [PenMask](#penmask)

这对应于 POINTER_PEN_INFO 结构的 penMask 属性。 这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。

#### PenPressure 

指针事件的 PenPressure。

> 公共 uint [PenPressure](#penpressure)

这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。

#### PenRotation 

指针事件的 PenRotation。

> 公共 uint [PenRotation](#penrotation)

这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。

#### PenTiltX 

指针事件的 PenTiltX。

> 公共 int [PenTiltX](#pentiltx)

这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。

#### PenTiltY 

指针事件的 PenTiltY。

> 公共 int [PenTiltY](#pentilty)

这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。

#### PerformanceCount 

指针事件的 PerformanceCount。

> 公共 ulong [PerformanceCount](#performancecount)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。

#### PixelLocation 

指针事件的 PixelLocation。

> 公共点[PixelLocation](#pixellocation)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。

#### PixelLocationRaw 

指针事件的 PixelLocationRaw。

> 公共点[PixelLocationRaw](#pixellocationraw)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。

#### PointerDeviceRect 

在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。

> 公共矩形[PointerDeviceRect](#pointerdevicerect)

#### PointerFlags 

指针事件的 PointerFlags。

> 公共 uint [PointerFlags](#pointerflags)

这对应于 POINTER_INFO 结构的 pointerFlags 属性。 这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。

#### PointerId 

指针事件的 PointerId。

> 公共 uint [PointerId](#pointerid)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。

#### PointerKind 

指针事件的 PointerKind。

> 公共 uint [PointerKind](#pointerkind)

这对应于 POINTER_INFO 结构的 pointerKind 属性。 这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。 支持 PT_PEN 和 PT_TOUCH。

#### 时间 

指针事件的时间。

> 公共 uint[时间](#time)

这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。

#### TouchContact 

指针事件的 TouchContact。

> 公共矩形[TouchContact](#touchcontact)

这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。

#### TouchContactRaw 

指针事件的 TouchContactRaw。

> 公共矩形[TouchContactRaw](#touchcontactraw)

这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。

#### TouchFlags 

指针事件的 TouchFlags。

> 公共 uint [TouchFlags](#touchflags)

这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。 这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。

#### TouchMask 

指针事件的 TouchMask。

> 公共 uint [TouchMask](#touchmask)

这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。 这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。

#### TouchOrientation 

指针事件的 TouchOrientation。

> 公共 uint [TouchOrientation](#touchorientation)

这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。

#### TouchPressure 

指针事件的 TouchPressure。

> 公共 uint [TouchPressure](#touchpressure)

这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。

