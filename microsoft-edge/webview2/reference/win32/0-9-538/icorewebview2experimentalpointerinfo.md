---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalPointerInfo
ms.openlocfilehash: db966ad087e22bc6b8d3865c416f8feba15e434a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011397"
---
# 0.9.579-接口 ICoreWebView2ExperimentalPointerInfo 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_ButtonChangeKind](#get_buttonchangekind) | 获取指针事件的 ButtonChangeKind。
[get_DisplayRect](#get_displayrect) | 获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。
[get_FrameId](#get_frameid) | 获取指针事件的 FrameID。
[get_HimetricLocation](#get_himetriclocation) | 获取指针事件的 HimetricLocation。
[get_HimetricLocationRaw](#get_himetriclocationraw) | 获取指针事件的 HimetricLocationRaw。
[get_HistoryCount](#get_historycount) | 获取指针事件的 HistoryCount。
[get_InputData](#get_inputdata) | 获取指针事件的 InputData。
[get_KeyStates](#get_keystates) | 获取指针事件的 KeyStates。
[get_PenFlags](#get_penflags) | 获取指针事件的 PenFlags。
[get_PenMask](#get_penmask) | 获取指针事件的 PenMask。
[get_PenPressure](#get_penpressure) | 获取指针事件的 PenPressure。
[get_PenRotation](#get_penrotation) | 获取指针事件的 PenRotation。
[get_PenTiltX](#get_pentiltx) | 获取指针事件的 PenTiltX。
[get_PenTiltY](#get_pentilty) | 获取指针事件的 PenTiltY。
[get_PerformanceCount](#get_performancecount) | 获取指针事件的 PerformanceCount。
[get_PixelLocation](#get_pixellocation) | 获取指针事件的 PixelLocation。
[get_PixelLocationRaw](#get_pixellocationraw) | 获取指针事件的 PixelLocationRaw。
[get_PointerDeviceRect](#get_pointerdevicerect) | 获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。
[get_PointerFlags](#get_pointerflags) | 获取指针事件的 PointerFlags。
[get_PointerId](#get_pointerid) | 获取指针事件的 PointerId。
[get_PointerKind](#get_pointerkind) | 获取指针事件的 PointerKind。
[get_Time](#get_time) | 获取指针事件的时间。
[get_TouchContact](#get_touchcontact) | 获取指针事件的 TouchContact。
[get_TouchContactRaw](#get_touchcontactraw) | 获取指针事件的 TouchContactRaw。
[get_TouchFlags](#get_touchflags) | 获取指针事件的 TouchFlags。
[get_TouchMask](#get_touchmask) | 获取指针事件的 TouchMask。
[get_TouchOrientation](#get_touchorientation) | 获取指针事件的 TouchOrientation。
[get_TouchPressure](#get_touchpressure) | 获取指针事件的 TouchPressure。
[put_ButtonChangeKind](#put_buttonchangekind) | 设置指针事件的 ButtonChangeKind。
[put_DisplayRect](#put_displayrect) | 按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。
[put_FrameId](#put_frameid) | 设置指针事件的 FrameID。
[put_HimetricLocation](#put_himetriclocation) | 设置指针事件的 HimetricLocation。
[put_HimetricLocationRaw](#put_himetriclocationraw) | 设置指针事件的 HimetricLocationRaw。
[put_HistoryCount](#put_historycount) | 设置指针事件的 HistoryCount。
[put_InputData](#put_inputdata) | 设置指针事件的 InputData。
[put_KeyStates](#put_keystates) | 设置指针事件的 KeyStates。
[put_PenFlags](#put_penflags) | 设置指针事件的 PenFlags。
[put_PenMask](#put_penmask) | 设置指针事件的 PenMask。
[put_PenPressure](#put_penpressure) | 设置指针事件的 PenPressure。
[put_PenRotation](#put_penrotation) | 设置指针事件的 PenRotation。
[put_PenTiltX](#put_pentiltx) | 设置指针事件的 PenTiltX。
[put_PenTiltY](#put_pentilty) | 设置指针事件的 PenTiltY。
[put_PerformanceCount](#put_performancecount) | 设置指针事件的 PerformanceCount。
[put_PixelLocation](#put_pixellocation) | 设置指针事件的 PixelLocation。
[put_PixelLocationRaw](#put_pixellocationraw) | 设置指针事件的 PixelLocationRaw。
[put_PointerDeviceRect](#put_pointerdevicerect) | 按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。
[put_PointerFlags](#put_pointerflags) | 设置指针事件的 PointerFlags。
[put_PointerId](#put_pointerid) | 设置指针事件的 PointerId。
[put_PointerKind](#put_pointerkind) | 设置指针事件的 PointerKind。
[put_Time](#put_time) | 设置指针事件的时间。
[put_TouchContact](#put_touchcontact) | 设置指针事件的 TouchContact。
[put_TouchContactRaw](#put_touchcontactraw) | 设置指针事件的 TouchContactRaw。
[put_TouchFlags](#put_touchflags) | 设置指针事件的 TouchFlags。
[put_TouchMask](#put_touchmask) | 设置指针事件的 TouchMask。
[put_TouchOrientation](#put_touchorientation) | 设置指针事件的 TouchOrientation。
[put_TouchPressure](#put_touchpressure) | 设置指针事件的 TouchPressure。

它将获取所有三个字段中的字段，并排除某些 win32 特定的数据类型（如 HWND 和句柄）。 注意，sourceDevice 已被取出，但我们希望 PointerDeviceRect 和 DisplayRect 涵盖 sourceDevice 的现有使用情形。 另一个显著的区别是，任何点或 rect 位置都应位于 web 视图物理坐标中。 即，相对于 web 视图的坐标和未应用的 DPI 缩放。

## 成员

#### get_ButtonChangeKind 

获取指针事件的 ButtonChangeKind。

> 公共 HRESULT [get_ButtonChangeKind](#get_buttonchangekind) (INT32 * ButtonChangeKind) 

这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。 这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举 (winuser) 定义。

#### get_DisplayRect 

获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。

> 公共 HRESULT [get_DisplayRect](#get_displayrect) (RECT * DisplayRect) 

#### get_FrameId 

获取指针事件的 FrameID。

> 公共 HRESULT [get_FrameId](#get_frameid) (UINT32 * FrameId) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 frameId 属性。

#### get_HimetricLocation 

获取指针事件的 HimetricLocation。

> 公共 HRESULT [get_HimetricLocation](#get_himetriclocation) (POINT * HimetricLocation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。

#### get_HimetricLocationRaw 

获取指针事件的 HimetricLocationRaw。

> 公共 HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw) (POINT * HimetricLocationRaw) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。

#### get_HistoryCount 

获取指针事件的 HistoryCount。

> 公共 HRESULT [get_HistoryCount](#get_historycount) (UINT32 * HistoryCount) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 historyCount 属性。

#### get_InputData 

获取指针事件的 InputData。

> 公共 HRESULT [get_InputData](#get_inputdata) (INT32 * InputData) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 InputData 属性。

#### get_KeyStates 

获取指针事件的 KeyStates。

> 公共 HRESULT [get_KeyStates](#get_keystates) (DWORD * KeyStates) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwKeyStates 属性。

#### get_PenFlags 

获取指针事件的 PenFlags。

> 公共 HRESULT [get_PenFlags](#get_penflags) (UINT32 * PenFlags) 

这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。 这些值由 Windows SDK 中的 PEN_FLAGS 常量 (winuser) 定义。

#### get_PenMask 

获取指针事件的 PenMask。

> 公共 HRESULT [get_PenMask](#get_penmask) (UINT32 * PenMask) 

这对应于 POINTER_PEN_INFO 结构的 penMask 属性。 这些值由 Windows SDK 中的 PEN_MASK 常量 (winuser) 定义。

#### get_PenPressure 

获取指针事件的 PenPressure。

> 公共 HRESULT [get_PenPressure](#get_penpressure) (UINT32 * PenPressure) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的压力属性。

#### get_PenRotation 

获取指针事件的 PenRotation。

> 公共 HRESULT [get_PenRotation](#get_penrotation) (UINT32 * PenRotation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的旋转属性。

#### get_PenTiltX 

获取指针事件的 PenTiltX。

> 公共 HRESULT [get_PenTiltX](#get_pentiltx) (INT32 * PenTiltX) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。

#### get_PenTiltY 

获取指针事件的 PenTiltY。

> 公共 HRESULT [get_PenTiltY](#get_pentilty) (INT32 * PenTiltY) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。

#### get_PerformanceCount 

获取指针事件的 PerformanceCount。

> 公共 HRESULT [get_PerformanceCount](#get_performancecount) (UINT64 * PerformanceCount) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 PerformanceCount 属性。

#### get_PixelLocation 

获取指针事件的 PixelLocation。

> 公共 HRESULT [get_PixelLocation](#get_pixellocation) (POINT * PixelLocation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。

#### get_PixelLocationRaw 

获取指针事件的 PixelLocationRaw。

> 公共 HRESULT [get_PixelLocationRaw](#get_pixellocationraw) (POINT * PixelLocationRaw) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。

#### get_PointerDeviceRect 

获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。

> 公共 HRESULT [get_PointerDeviceRect](#get_pointerdevicerect) (RECT * PointerDeviceRect) 

#### get_PointerFlags 

获取指针事件的 PointerFlags。

> 公共 HRESULT [get_PointerFlags](#get_pointerflags) (UINT32 * PointerFlags) 

这对应于 POINTER_INFO 结构的 pointerFlags 属性。 这些值由 Windows SDK 中的 POINTER_FLAGS 常量 (winuser) 定义。

#### get_PointerId 

获取指针事件的 PointerId。

> 公共 HRESULT [get_PointerId](#get_pointerid) (UINT32 * PointerId) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 pointerId 属性。

#### get_PointerKind 

获取指针事件的 PointerKind。

> 公共 HRESULT [get_PointerKind](#get_pointerkind) (DWORD * PointerKind) 

这对应于 POINTER_INFO 结构的 pointerKind 属性。 这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举 (winuser) 定义。 支持 PT_PEN 和 PT_TOUCH。

#### get_Time 

获取指针事件的时间。

> 公共 HRESULT [get_Time](#get_time) (DWORD * 时间) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwTime 属性。

#### get_TouchContact 

获取指针事件的 TouchContact。

> 公共 HRESULT [get_TouchContact](#get_touchcontact) (RECT * TouchContact) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。

#### get_TouchContactRaw 

获取指针事件的 TouchContactRaw。

> 公共 HRESULT [get_TouchContactRaw](#get_touchcontactraw) (RECT * TouchContactRaw) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。

#### get_TouchFlags 

获取指针事件的 TouchFlags。

> 公共 HRESULT [get_TouchFlags](#get_touchflags) (UINT32 * TouchFlags) 

这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。 这些值由 Windows SDK 中的 TOUCH_FLAGS 常量 (winuser) 定义。

#### get_TouchMask 

获取指针事件的 TouchMask。

> 公共 HRESULT [get_TouchMask](#get_touchmask) (UINT32 * TouchMask) 

这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。 这些值由 Windows SDK 中的 TOUCH_MASK 常量 (winuser) 定义。

#### get_TouchOrientation 

获取指针事件的 TouchOrientation。

> 公共 HRESULT [get_TouchOrientation](#get_touchorientation) (UINT32 * TouchOrientation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的方向属性。

#### get_TouchPressure 

获取指针事件的 TouchPressure。

> 公共 HRESULT [get_TouchPressure](#get_touchpressure) (UINT32 * TouchPressure) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的压力属性。

#### put_ButtonChangeKind 

设置指针事件的 ButtonChangeKind。

> 公共 HRESULT [put_ButtonChangeKind](#put_buttonchangekind) (INT32 ButtonChangeKind) 

这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。 这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举 (winuser) 定义。

#### put_DisplayRect 

按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。

> 公共 HRESULT [put_DisplayRect](#put_displayrect) (RECT DisplayRect) 

#### put_FrameId 

设置指针事件的 FrameID。

> 公共 HRESULT [put_FrameId](#put_frameid) (UINT32 FrameId) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 frameId 属性。

#### put_HimetricLocation 

设置指针事件的 HimetricLocation。

> 公共 HRESULT [put_HimetricLocation](#put_himetriclocation) (POINT HimetricLocation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。

#### put_HimetricLocationRaw 

设置指针事件的 HimetricLocationRaw。

> 公共 HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw) (POINT HimetricLocationRaw) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。

#### put_HistoryCount 

设置指针事件的 HistoryCount。

> 公共 HRESULT [put_HistoryCount](#put_historycount) (UINT32 HistoryCount) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 historyCount 属性。

#### put_InputData 

设置指针事件的 InputData。

> 公共 HRESULT [put_InputData](#put_inputdata) (INT32 InputData) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 InputData 属性。

#### put_KeyStates 

设置指针事件的 KeyStates。

> 公共 HRESULT [put_KeyStates](#put_keystates) (DWORD KeyStates) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwKeyStates 属性。

#### put_PenFlags 

设置指针事件的 PenFlags。

> 公共 HRESULT [put_PenFlags](#put_penflags) (UINT32 PenFlags) 

这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。 这些值由 Windows SDK 中的 PEN_FLAGS 常量 (winuser) 定义。

#### put_PenMask 

设置指针事件的 PenMask。

> 公共 HRESULT [put_PenMask](#put_penmask) (UINT32 PenMask) 

这对应于 POINTER_PEN_INFO 结构的 penMask 属性。 这些值由 Windows SDK 中的 PEN_MASK 常量 (winuser) 定义。

#### put_PenPressure 

设置指针事件的 PenPressure。

> 公共 HRESULT [put_PenPressure](#put_penpressure) (UINT32 PenPressure) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的压力属性。

#### put_PenRotation 

设置指针事件的 PenRotation。

> 公共 HRESULT [put_PenRotation](#put_penrotation) (UINT32 PenRotation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的旋转属性。

#### put_PenTiltX 

设置指针事件的 PenTiltX。

> 公共 HRESULT [put_PenTiltX](#put_pentiltx) (INT32 PenTiltX) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。

#### put_PenTiltY 

设置指针事件的 PenTiltY。

> 公共 HRESULT [put_PenTiltY](#put_pentilty) (INT32 PenTiltY) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。

#### put_PerformanceCount 

设置指针事件的 PerformanceCount。

> 公共 HRESULT [put_PerformanceCount](#put_performancecount) (UINT64 PerformanceCount) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 PerformanceCount 属性。

#### put_PixelLocation 

设置指针事件的 PixelLocation。

> 公共 HRESULT [put_PixelLocation](#put_pixellocation) (POINT PixelLocation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。

#### put_PixelLocationRaw 

设置指针事件的 PixelLocationRaw。

> 公共 HRESULT [put_PixelLocationRaw](#put_pixellocationraw) (POINT PixelLocationRaw) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。

#### put_PointerDeviceRect 

按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。

> 公共 HRESULT [put_PointerDeviceRect](#put_pointerdevicerect) (RECT PointerDeviceRect) 

#### put_PointerFlags 

设置指针事件的 PointerFlags。

> 公共 HRESULT [put_PointerFlags](#put_pointerflags) (UINT32 PointerFlags) 

这对应于 POINTER_INFO 结构的 pointerFlags 属性。 这些值由 Windows SDK 中的 POINTER_FLAGS 常量 (winuser) 定义。

#### put_PointerId 

设置指针事件的 PointerId。

> 公共 HRESULT [put_PointerId](#put_pointerid) (UINT32 PointerId) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 pointerId 属性。

#### put_PointerKind 

设置指针事件的 PointerKind。

> 公共 HRESULT [put_PointerKind](#put_pointerkind) (DWORD PointerKind) 

这对应于 POINTER_INFO 结构的 pointerKind 属性。 这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举 (winuser) 定义。 支持 PT_PEN 和 PT_TOUCH。

#### put_Time 

设置指针事件的时间。

>  (DWORD 时间的公共 HRESULT [put_Time](#put_time)) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwTime 属性。

#### put_TouchContact 

设置指针事件的 TouchContact。

> 公共 HRESULT [put_TouchContact](#put_touchcontact) (RECT TouchContact) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。

#### put_TouchContactRaw 

设置指针事件的 TouchContactRaw。

> 公共 HRESULT [put_TouchContactRaw](#put_touchcontactraw) (RECT TouchContactRaw) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。

#### put_TouchFlags 

设置指针事件的 TouchFlags。

> 公共 HRESULT [put_TouchFlags](#put_touchflags) (UINT32 TouchFlags) 

这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。 这些值由 Windows SDK 中的 TOUCH_FLAGS 常量 (winuser) 定义。

#### put_TouchMask 

设置指针事件的 TouchMask。

> 公共 HRESULT [put_TouchMask](#put_touchmask) (UINT32 TouchMask) 

这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。 这些值由 Windows SDK 中的 TOUCH_MASK 常量 (winuser) 定义。

#### put_TouchOrientation 

设置指针事件的 TouchOrientation。

> 公共 HRESULT [put_TouchOrientation](#put_touchorientation) (UINT32 TouchOrientation) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的方向属性。

#### put_TouchPressure 

设置指针事件的 TouchPressure。

> 公共 HRESULT [put_TouchPressure](#put_touchpressure) (UINT32 TouchPressure) 

这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的压力属性。

