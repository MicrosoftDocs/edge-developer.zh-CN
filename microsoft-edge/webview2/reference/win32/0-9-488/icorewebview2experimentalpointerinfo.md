---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 8c0ed40c61344fe0a3177fd36d5629953f8801d7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885478"
---
# <span data-ttu-id="dcdfa-104">0.9.515-接口 ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="dcdfa-104">0.9.515 - interface ICoreWebView2ExperimentalPointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="dcdfa-105">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-105">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="dcdfa-106">摘要</span><span class="sxs-lookup"><span data-stu-id="dcdfa-106">Summary</span></span>

 <span data-ttu-id="dcdfa-107">成员</span><span class="sxs-lookup"><span data-stu-id="dcdfa-107">Members</span></span>                        | <span data-ttu-id="dcdfa-108">描述</span><span class="sxs-lookup"><span data-stu-id="dcdfa-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dcdfa-109">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-109">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="dcdfa-110">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-110">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-111">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-111">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="dcdfa-112">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-112">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="dcdfa-113">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-113">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="dcdfa-114">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-114">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-115">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-115">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="dcdfa-116">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-116">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-117">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-117">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="dcdfa-118">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-118">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-119">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-119">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="dcdfa-120">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-120">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-121">get_InputData</span><span class="sxs-lookup"><span data-stu-id="dcdfa-121">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="dcdfa-122">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-122">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-123">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="dcdfa-123">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="dcdfa-124">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-124">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-125">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-125">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="dcdfa-126">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-126">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-127">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-127">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="dcdfa-128">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-128">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-129">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-129">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="dcdfa-130">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-130">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-131">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-131">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="dcdfa-132">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-132">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-133">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="dcdfa-133">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="dcdfa-134">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-134">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-135">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="dcdfa-135">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="dcdfa-136">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-136">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-137">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-137">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="dcdfa-138">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-138">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-139">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-139">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="dcdfa-140">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-140">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-141">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-141">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="dcdfa-142">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-142">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-143">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-143">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="dcdfa-144">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-144">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="dcdfa-145">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-145">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="dcdfa-146">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-146">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-147">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-147">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="dcdfa-148">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-148">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-149">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-149">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="dcdfa-150">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-150">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-151">get_Time</span><span class="sxs-lookup"><span data-stu-id="dcdfa-151">get_Time</span></span>](#get_time) | <span data-ttu-id="dcdfa-152">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-152">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-153">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="dcdfa-153">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="dcdfa-154">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-154">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-155">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-155">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="dcdfa-156">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-156">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-157">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-157">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="dcdfa-158">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-158">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-159">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-159">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="dcdfa-160">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-160">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-161">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-161">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="dcdfa-162">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-162">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-163">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-163">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="dcdfa-164">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-164">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-165">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-165">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="dcdfa-166">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-166">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-167">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-167">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="dcdfa-168">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-168">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="dcdfa-169">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-169">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="dcdfa-170">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-170">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-171">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-171">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="dcdfa-172">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-172">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-173">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-173">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="dcdfa-174">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-174">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-175">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-175">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="dcdfa-176">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-176">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-177">put_InputData</span><span class="sxs-lookup"><span data-stu-id="dcdfa-177">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="dcdfa-178">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-178">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-179">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="dcdfa-179">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="dcdfa-180">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-180">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-181">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-181">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="dcdfa-182">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-182">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-183">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-183">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="dcdfa-184">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-184">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-185">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-185">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="dcdfa-186">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-186">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-187">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-187">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="dcdfa-188">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-188">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-189">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="dcdfa-189">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="dcdfa-190">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-190">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-191">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="dcdfa-191">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="dcdfa-192">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-192">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-193">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-193">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="dcdfa-194">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-194">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-195">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-195">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="dcdfa-196">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-196">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-197">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-197">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="dcdfa-198">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-198">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-199">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-199">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="dcdfa-200">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-200">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="dcdfa-201">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-201">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="dcdfa-202">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-202">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-203">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-203">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="dcdfa-204">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-204">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-205">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-205">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="dcdfa-206">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-206">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-207">put_Time</span><span class="sxs-lookup"><span data-stu-id="dcdfa-207">put_Time</span></span>](#put_time) | <span data-ttu-id="dcdfa-208">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-208">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-209">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="dcdfa-209">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="dcdfa-210">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-210">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-211">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-211">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="dcdfa-212">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-212">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-213">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-213">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="dcdfa-214">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-214">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-215">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-215">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="dcdfa-216">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-216">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-217">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-217">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="dcdfa-218">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-218">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="dcdfa-219">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-219">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="dcdfa-220">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-220">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="dcdfa-221">它将获取所有三个字段中的字段，并排除某些 win32 特定的数据类型（如 HWND 和句柄）。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-221">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="dcdfa-222">注意，sourceDevice 已被取出，但我们希望 PointerDeviceRect 和 DisplayRect 涵盖 sourceDevice 的现有使用情形。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-222">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="dcdfa-223">另一个显著的区别是，任何点或 rect 位置都应位于 web 视图物理坐标中。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-223">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="dcdfa-224">即，相对于 web 视图的坐标和未应用的 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-224">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="dcdfa-225">成员</span><span class="sxs-lookup"><span data-stu-id="dcdfa-225">Members</span></span>

#### <span data-ttu-id="dcdfa-226">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-226">get_ButtonChangeKind</span></span> 

<span data-ttu-id="dcdfa-227">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-227">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-228">公共 HRESULT [get_ButtonChangeKind](#get_buttonchangekind)（INT32 \* ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-228">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="dcdfa-229">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-229">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="dcdfa-230">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-230">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-231">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-231">get_DisplayRect</span></span> 

<span data-ttu-id="dcdfa-232">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-232">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="dcdfa-233">public HRESULT [get_DisplayRect](#get_displayrect)（RECT \* DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-233">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="dcdfa-234">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-234">get_FrameId</span></span> 

<span data-ttu-id="dcdfa-235">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-235">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-236">公共 HRESULT [get_FrameId](#get_frameid)（UINT32 \* FrameId）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-236">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="dcdfa-237">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-237">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-238">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-238">get_HimetricLocation</span></span> 

<span data-ttu-id="dcdfa-239">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-239">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-240">public HRESULT [get_HimetricLocation](#get_himetriclocation)（POINT \* HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-240">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="dcdfa-241">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-241">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-242">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-242">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="dcdfa-243">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-243">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-244">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)（POINT \* HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-244">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="dcdfa-245">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-245">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-246">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-246">get_HistoryCount</span></span> 

<span data-ttu-id="dcdfa-247">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-247">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-248">公共 HRESULT [get_HistoryCount](#get_historycount)（UINT32 \* HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-248">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="dcdfa-249">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-249">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-250">get_InputData</span><span class="sxs-lookup"><span data-stu-id="dcdfa-250">get_InputData</span></span> 

<span data-ttu-id="dcdfa-251">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-251">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-252">公共 HRESULT [get_InputData](#get_inputdata)（INT32 \* InputData）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-252">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="dcdfa-253">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-253">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-254">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="dcdfa-254">get_KeyStates</span></span> 

<span data-ttu-id="dcdfa-255">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-255">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-256">公共 HRESULT [get_KeyStates](#get_keystates)（DWORD \* KeyStates）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-256">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="dcdfa-257">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-257">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-258">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-258">get_PenFlags</span></span> 

<span data-ttu-id="dcdfa-259">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-259">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-260">公共 HRESULT [get_PenFlags](#get_penflags)（UINT32 \* PenFlags）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-260">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="dcdfa-261">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-261">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="dcdfa-262">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-262">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-263">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-263">get_PenMask</span></span> 

<span data-ttu-id="dcdfa-264">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-264">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-265">公共 HRESULT [get_PenMask](#get_penmask)（UINT32 \* PenMask）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-265">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="dcdfa-266">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-266">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="dcdfa-267">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-267">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-268">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-268">get_PenPressure</span></span> 

<span data-ttu-id="dcdfa-269">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-269">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-270">公共 HRESULT [get_PenPressure](#get_penpressure)（UINT32 \* PenPressure）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-270">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="dcdfa-271">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-271">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-272">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-272">get_PenRotation</span></span> 

<span data-ttu-id="dcdfa-273">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-273">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-274">公共 HRESULT [get_PenRotation](#get_penrotation)（UINT32 \* PenRotation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-274">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="dcdfa-275">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-275">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-276">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="dcdfa-276">get_PenTiltX</span></span> 

<span data-ttu-id="dcdfa-277">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-277">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-278">公共 HRESULT [get_PenTiltX](#get_pentiltx)（INT32 \* PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-278">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="dcdfa-279">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-279">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-280">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="dcdfa-280">get_PenTiltY</span></span> 

<span data-ttu-id="dcdfa-281">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-281">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-282">公共 HRESULT [get_PenTiltY](#get_pentilty)（INT32 \* PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-282">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="dcdfa-283">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-283">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-284">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-284">get_PerformanceCount</span></span> 

<span data-ttu-id="dcdfa-285">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-285">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-286">公共 HRESULT [get_PerformanceCount](#get_performancecount)（UINT64 \* PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-286">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="dcdfa-287">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-287">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-288">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-288">get_PixelLocation</span></span> 

<span data-ttu-id="dcdfa-289">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-289">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-290">public HRESULT [get_PixelLocation](#get_pixellocation)（POINT \* PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-290">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="dcdfa-291">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-291">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-292">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-292">get_PixelLocationRaw</span></span> 

<span data-ttu-id="dcdfa-293">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-293">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-294">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)（POINT \* PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-294">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="dcdfa-295">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-295">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-296">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-296">get_PointerDeviceRect</span></span> 

<span data-ttu-id="dcdfa-297">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-297">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="dcdfa-298">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)（RECT \* PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-298">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="dcdfa-299">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-299">get_PointerFlags</span></span> 

<span data-ttu-id="dcdfa-300">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-300">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-301">公共 HRESULT [get_PointerFlags](#get_pointerflags)（UINT32 \* PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-301">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="dcdfa-302">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-302">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="dcdfa-303">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-303">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-304">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-304">get_PointerId</span></span> 

<span data-ttu-id="dcdfa-305">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-305">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-306">公共 HRESULT [get_PointerId](#get_pointerid)（UINT32 \* PointerId）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-306">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="dcdfa-307">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-307">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-308">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-308">get_PointerKind</span></span> 

<span data-ttu-id="dcdfa-309">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-309">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-310">公共 HRESULT [get_PointerKind](#get_pointerkind)（DWORD \* PointerKind）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-310">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="dcdfa-311">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-311">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="dcdfa-312">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-312">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="dcdfa-313">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-313">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="dcdfa-314">get_Time</span><span class="sxs-lookup"><span data-stu-id="dcdfa-314">get_Time</span></span> 

<span data-ttu-id="dcdfa-315">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-315">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-316">公共 HRESULT [get_Time](#get_time)（DWORD \* 时间）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-316">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="dcdfa-317">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-317">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-318">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="dcdfa-318">get_TouchContact</span></span> 

<span data-ttu-id="dcdfa-319">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-319">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-320">public HRESULT [get_TouchContact](#get_touchcontact)（RECT \* TouchContact）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-320">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="dcdfa-321">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-321">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-322">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-322">get_TouchContactRaw</span></span> 

<span data-ttu-id="dcdfa-323">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-323">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-324">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)（RECT \* TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-324">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="dcdfa-325">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-325">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-326">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-326">get_TouchFlags</span></span> 

<span data-ttu-id="dcdfa-327">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-327">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-328">公共 HRESULT [get_TouchFlags](#get_touchflags)（UINT32 \* TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-328">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="dcdfa-329">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-329">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="dcdfa-330">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-330">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-331">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-331">get_TouchMask</span></span> 

<span data-ttu-id="dcdfa-332">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-332">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-333">公共 HRESULT [get_TouchMask](#get_touchmask)（UINT32 \* TouchMask）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-333">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="dcdfa-334">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-334">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="dcdfa-335">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-335">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-336">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-336">get_TouchOrientation</span></span> 

<span data-ttu-id="dcdfa-337">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-337">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-338">公共 HRESULT [get_TouchOrientation](#get_touchorientation)（UINT32 \* TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-338">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="dcdfa-339">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-339">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-340">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-340">get_TouchPressure</span></span> 

<span data-ttu-id="dcdfa-341">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-341">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-342">公共 HRESULT [get_TouchPressure](#get_touchpressure)（UINT32 \* TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-342">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="dcdfa-343">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-343">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-344">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-344">put_ButtonChangeKind</span></span> 

<span data-ttu-id="dcdfa-345">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-345">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-346">公共 HRESULT [put_ButtonChangeKind](#put_buttonchangekind)（INT32 ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-346">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="dcdfa-347">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-347">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="dcdfa-348">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-348">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-349">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-349">put_DisplayRect</span></span> 

<span data-ttu-id="dcdfa-350">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-350">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="dcdfa-351">public HRESULT [put_DisplayRect](#put_displayrect)（RECT DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-351">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="dcdfa-352">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-352">put_FrameId</span></span> 

<span data-ttu-id="dcdfa-353">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-353">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-354">公共 HRESULT [put_FrameId](#put_frameid)（UINT32 FrameId）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-354">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="dcdfa-355">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-355">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-356">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-356">put_HimetricLocation</span></span> 

<span data-ttu-id="dcdfa-357">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-357">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-358">public HRESULT [put_HimetricLocation](#put_himetriclocation)（POINT HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-358">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="dcdfa-359">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-359">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-360">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-360">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="dcdfa-361">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-361">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-362">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)（POINT HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-362">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="dcdfa-363">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-363">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-364">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-364">put_HistoryCount</span></span> 

<span data-ttu-id="dcdfa-365">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-365">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-366">公共 HRESULT [put_HistoryCount](#put_historycount)（UINT32 HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-366">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="dcdfa-367">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-367">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-368">put_InputData</span><span class="sxs-lookup"><span data-stu-id="dcdfa-368">put_InputData</span></span> 

<span data-ttu-id="dcdfa-369">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-369">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-370">公共 HRESULT [put_InputData](#put_inputdata)（INT32 InputData）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-370">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="dcdfa-371">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-371">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-372">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="dcdfa-372">put_KeyStates</span></span> 

<span data-ttu-id="dcdfa-373">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-373">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-374">公共 HRESULT [put_KeyStates](#put_keystates)（DWORD KeyStates）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-374">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="dcdfa-375">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-375">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-376">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-376">put_PenFlags</span></span> 

<span data-ttu-id="dcdfa-377">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-377">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-378">公共 HRESULT [put_PenFlags](#put_penflags)（UINT32 PenFlags）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-378">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="dcdfa-379">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-379">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="dcdfa-380">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-380">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-381">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-381">put_PenMask</span></span> 

<span data-ttu-id="dcdfa-382">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-382">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-383">公共 HRESULT [put_PenMask](#put_penmask)（UINT32 PenMask）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-383">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="dcdfa-384">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-384">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="dcdfa-385">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-385">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-386">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-386">put_PenPressure</span></span> 

<span data-ttu-id="dcdfa-387">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-387">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-388">公共 HRESULT [put_PenPressure](#put_penpressure)（UINT32 PenPressure）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-388">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="dcdfa-389">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-389">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-390">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-390">put_PenRotation</span></span> 

<span data-ttu-id="dcdfa-391">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-391">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-392">公共 HRESULT [put_PenRotation](#put_penrotation)（UINT32 PenRotation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-392">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="dcdfa-393">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-393">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-394">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="dcdfa-394">put_PenTiltX</span></span> 

<span data-ttu-id="dcdfa-395">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-395">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-396">公共 HRESULT [put_PenTiltX](#put_pentiltx)（INT32 PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-396">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="dcdfa-397">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-397">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-398">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="dcdfa-398">put_PenTiltY</span></span> 

<span data-ttu-id="dcdfa-399">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-399">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-400">公共 HRESULT [put_PenTiltY](#put_pentilty)（INT32 PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-400">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="dcdfa-401">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-401">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-402">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="dcdfa-402">put_PerformanceCount</span></span> 

<span data-ttu-id="dcdfa-403">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-403">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-404">公共 HRESULT [put_PerformanceCount](#put_performancecount)（UINT64 PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-404">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="dcdfa-405">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-405">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-406">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-406">put_PixelLocation</span></span> 

<span data-ttu-id="dcdfa-407">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-407">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-408">public HRESULT [put_PixelLocation](#put_pixellocation)（POINT PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-408">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="dcdfa-409">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-409">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-410">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-410">put_PixelLocationRaw</span></span> 

<span data-ttu-id="dcdfa-411">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-411">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-412">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)（POINT PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-412">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="dcdfa-413">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-413">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-414">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="dcdfa-414">put_PointerDeviceRect</span></span> 

<span data-ttu-id="dcdfa-415">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-415">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="dcdfa-416">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)（RECT PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-416">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="dcdfa-417">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-417">put_PointerFlags</span></span> 

<span data-ttu-id="dcdfa-418">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-418">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-419">公共 HRESULT [put_PointerFlags](#put_pointerflags)（UINT32 PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-419">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="dcdfa-420">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-420">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="dcdfa-421">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-421">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-422">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="dcdfa-422">put_PointerId</span></span> 

<span data-ttu-id="dcdfa-423">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-423">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-424">公共 HRESULT [put_PointerId](#put_pointerid)（UINT32 PointerId）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-424">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="dcdfa-425">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-425">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-426">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="dcdfa-426">put_PointerKind</span></span> 

<span data-ttu-id="dcdfa-427">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-427">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-428">公共 HRESULT [put_PointerKind](#put_pointerkind)（DWORD PointerKind）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-428">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="dcdfa-429">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-429">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="dcdfa-430">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-430">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="dcdfa-431">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-431">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="dcdfa-432">put_Time</span><span class="sxs-lookup"><span data-stu-id="dcdfa-432">put_Time</span></span> 

<span data-ttu-id="dcdfa-433">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-433">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-434">公共 HRESULT [put_Time](#put_time)（DWORD 时间）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-434">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="dcdfa-435">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-435">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-436">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="dcdfa-436">put_TouchContact</span></span> 

<span data-ttu-id="dcdfa-437">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-437">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-438">public HRESULT [put_TouchContact](#put_touchcontact)（RECT TouchContact）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-438">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="dcdfa-439">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-439">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-440">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="dcdfa-440">put_TouchContactRaw</span></span> 

<span data-ttu-id="dcdfa-441">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-441">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-442">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)（RECT TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-442">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="dcdfa-443">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-443">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-444">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="dcdfa-444">put_TouchFlags</span></span> 

<span data-ttu-id="dcdfa-445">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-445">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-446">公共 HRESULT [put_TouchFlags](#put_touchflags)（UINT32 TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-446">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="dcdfa-447">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-447">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="dcdfa-448">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-448">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-449">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="dcdfa-449">put_TouchMask</span></span> 

<span data-ttu-id="dcdfa-450">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-450">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-451">公共 HRESULT [put_TouchMask](#put_touchmask)（UINT32 TouchMask）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-451">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="dcdfa-452">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-452">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="dcdfa-453">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-453">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-454">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="dcdfa-454">put_TouchOrientation</span></span> 

<span data-ttu-id="dcdfa-455">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-455">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-456">公共 HRESULT [put_TouchOrientation](#put_touchorientation)（UINT32 TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-456">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="dcdfa-457">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-457">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="dcdfa-458">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-458">put_TouchPressure</span></span> 

<span data-ttu-id="dcdfa-459">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-459">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="dcdfa-460">公共 HRESULT [put_TouchPressure](#put_touchpressure)（UINT32 TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="dcdfa-460">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="dcdfa-461">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="dcdfa-461">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

