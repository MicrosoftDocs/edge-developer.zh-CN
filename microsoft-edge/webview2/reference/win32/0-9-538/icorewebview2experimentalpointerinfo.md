---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalPointerInfo
ms.openlocfilehash: 6a5727fbcae24f7fd65c6c4a7a49b1a0b4746eb3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883709"
---
# <span data-ttu-id="fb484-104">interface ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="fb484-104">interface ICoreWebView2ExperimentalPointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="fb484-105">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="fb484-105">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="fb484-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fb484-106">Summary</span></span>

 <span data-ttu-id="fb484-107">成员</span><span class="sxs-lookup"><span data-stu-id="fb484-107">Members</span></span>                        | <span data-ttu-id="fb484-108">描述</span><span class="sxs-lookup"><span data-stu-id="fb484-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fb484-109">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="fb484-109">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="fb484-110">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-110">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="fb484-111">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="fb484-111">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="fb484-112">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-112">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="fb484-113">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="fb484-113">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="fb484-114">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="fb484-114">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="fb484-115">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-115">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="fb484-116">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-116">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="fb484-117">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-117">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="fb484-118">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-118">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="fb484-119">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="fb484-119">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="fb484-120">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-120">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="fb484-121">get_InputData</span><span class="sxs-lookup"><span data-stu-id="fb484-121">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="fb484-122">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="fb484-122">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="fb484-123">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="fb484-123">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="fb484-124">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="fb484-124">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="fb484-125">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-125">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="fb484-126">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-126">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="fb484-127">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="fb484-127">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="fb484-128">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-128">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="fb484-129">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-129">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="fb484-130">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-130">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="fb484-131">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="fb484-131">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="fb484-132">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="fb484-132">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="fb484-133">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="fb484-133">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="fb484-134">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="fb484-134">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="fb484-135">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="fb484-135">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="fb484-136">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="fb484-136">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="fb484-137">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="fb484-137">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="fb484-138">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-138">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="fb484-139">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-139">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="fb484-140">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-140">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="fb484-141">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-141">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="fb484-142">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-142">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="fb484-143">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="fb484-143">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="fb484-144">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-144">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="fb484-145">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-145">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="fb484-146">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-146">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="fb484-147">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="fb484-147">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="fb484-148">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="fb484-148">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="fb484-149">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="fb484-149">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="fb484-150">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-150">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="fb484-151">get_Time</span><span class="sxs-lookup"><span data-stu-id="fb484-151">get_Time</span></span>](#get_time) | <span data-ttu-id="fb484-152">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="fb484-152">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="fb484-153">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="fb484-153">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="fb484-154">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="fb484-154">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="fb484-155">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-155">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="fb484-156">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-156">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="fb484-157">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-157">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="fb484-158">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-158">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="fb484-159">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="fb484-159">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="fb484-160">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-160">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="fb484-161">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="fb484-161">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="fb484-162">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="fb484-162">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="fb484-163">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-163">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="fb484-164">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-164">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="fb484-165">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="fb484-165">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="fb484-166">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-166">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="fb484-167">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="fb484-167">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="fb484-168">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-168">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="fb484-169">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="fb484-169">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="fb484-170">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="fb484-170">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="fb484-171">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-171">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="fb484-172">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-172">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="fb484-173">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-173">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="fb484-174">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-174">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="fb484-175">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="fb484-175">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="fb484-176">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-176">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="fb484-177">put_InputData</span><span class="sxs-lookup"><span data-stu-id="fb484-177">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="fb484-178">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="fb484-178">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="fb484-179">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="fb484-179">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="fb484-180">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="fb484-180">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="fb484-181">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-181">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="fb484-182">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-182">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="fb484-183">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="fb484-183">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="fb484-184">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-184">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="fb484-185">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-185">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="fb484-186">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-186">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="fb484-187">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="fb484-187">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="fb484-188">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="fb484-188">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="fb484-189">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="fb484-189">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="fb484-190">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="fb484-190">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="fb484-191">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="fb484-191">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="fb484-192">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="fb484-192">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="fb484-193">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="fb484-193">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="fb484-194">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-194">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="fb484-195">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-195">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="fb484-196">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-196">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="fb484-197">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-197">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="fb484-198">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-198">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="fb484-199">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="fb484-199">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="fb484-200">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-200">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="fb484-201">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-201">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="fb484-202">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-202">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="fb484-203">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="fb484-203">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="fb484-204">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="fb484-204">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="fb484-205">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="fb484-205">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="fb484-206">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-206">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="fb484-207">put_Time</span><span class="sxs-lookup"><span data-stu-id="fb484-207">put_Time</span></span>](#put_time) | <span data-ttu-id="fb484-208">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="fb484-208">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="fb484-209">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="fb484-209">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="fb484-210">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="fb484-210">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="fb484-211">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-211">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="fb484-212">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-212">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="fb484-213">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-213">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="fb484-214">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-214">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="fb484-215">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="fb484-215">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="fb484-216">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-216">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="fb484-217">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="fb484-217">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="fb484-218">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="fb484-218">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="fb484-219">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-219">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="fb484-220">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-220">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="fb484-221">它将获取所有三个字段中的字段，并排除某些 win32 特定的数据类型（如 HWND 和句柄）。</span><span class="sxs-lookup"><span data-stu-id="fb484-221">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="fb484-222">注意，sourceDevice 已被取出，但我们希望 PointerDeviceRect 和 DisplayRect 涵盖 sourceDevice 的现有使用情形。</span><span class="sxs-lookup"><span data-stu-id="fb484-222">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="fb484-223">另一个显著的区别是，任何点或 rect 位置都应位于 web 视图物理坐标中。</span><span class="sxs-lookup"><span data-stu-id="fb484-223">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="fb484-224">即，相对于 web 视图的坐标和未应用的 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="fb484-224">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="fb484-225">成员</span><span class="sxs-lookup"><span data-stu-id="fb484-225">Members</span></span>

#### <span data-ttu-id="fb484-226">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="fb484-226">get_ButtonChangeKind</span></span> 

<span data-ttu-id="fb484-227">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-227">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="fb484-228">公共 HRESULT [get_ButtonChangeKind](#get_buttonchangekind)（INT32 \* ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="fb484-228">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="fb484-229">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-229">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="fb484-230">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-230">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-231">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="fb484-231">get_DisplayRect</span></span> 

<span data-ttu-id="fb484-232">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-232">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="fb484-233">public HRESULT [get_DisplayRect](#get_displayrect)（RECT \* DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="fb484-233">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="fb484-234">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="fb484-234">get_FrameId</span></span> 

<span data-ttu-id="fb484-235">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="fb484-235">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="fb484-236">公共 HRESULT [get_FrameId](#get_frameid)（UINT32 \* FrameId）</span><span class="sxs-lookup"><span data-stu-id="fb484-236">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="fb484-237">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-237">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-238">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-238">get_HimetricLocation</span></span> 

<span data-ttu-id="fb484-239">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-239">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="fb484-240">public HRESULT [get_HimetricLocation](#get_himetriclocation)（POINT \* HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="fb484-240">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="fb484-241">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-241">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-242">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-242">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="fb484-243">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-243">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="fb484-244">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)（POINT \* HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="fb484-244">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="fb484-245">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-245">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-246">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="fb484-246">get_HistoryCount</span></span> 

<span data-ttu-id="fb484-247">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-247">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="fb484-248">公共 HRESULT [get_HistoryCount](#get_historycount)（UINT32 \* HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="fb484-248">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="fb484-249">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-249">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-250">get_InputData</span><span class="sxs-lookup"><span data-stu-id="fb484-250">get_InputData</span></span> 

<span data-ttu-id="fb484-251">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="fb484-251">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="fb484-252">公共 HRESULT [get_InputData](#get_inputdata)（INT32 \* InputData）</span><span class="sxs-lookup"><span data-stu-id="fb484-252">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="fb484-253">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-253">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-254">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="fb484-254">get_KeyStates</span></span> 

<span data-ttu-id="fb484-255">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="fb484-255">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="fb484-256">公共 HRESULT [get_KeyStates](#get_keystates)（DWORD \* KeyStates）</span><span class="sxs-lookup"><span data-stu-id="fb484-256">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="fb484-257">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-257">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-258">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-258">get_PenFlags</span></span> 

<span data-ttu-id="fb484-259">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-259">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="fb484-260">公共 HRESULT [get_PenFlags](#get_penflags)（UINT32 \* PenFlags）</span><span class="sxs-lookup"><span data-stu-id="fb484-260">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="fb484-261">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-261">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="fb484-262">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-262">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-263">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="fb484-263">get_PenMask</span></span> 

<span data-ttu-id="fb484-264">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-264">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="fb484-265">公共 HRESULT [get_PenMask](#get_penmask)（UINT32 \* PenMask）</span><span class="sxs-lookup"><span data-stu-id="fb484-265">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="fb484-266">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-266">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="fb484-267">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-267">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-268">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-268">get_PenPressure</span></span> 

<span data-ttu-id="fb484-269">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-269">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="fb484-270">公共 HRESULT [get_PenPressure](#get_penpressure)（UINT32 \* PenPressure）</span><span class="sxs-lookup"><span data-stu-id="fb484-270">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="fb484-271">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-271">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-272">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="fb484-272">get_PenRotation</span></span> 

<span data-ttu-id="fb484-273">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="fb484-273">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="fb484-274">公共 HRESULT [get_PenRotation](#get_penrotation)（UINT32 \* PenRotation）</span><span class="sxs-lookup"><span data-stu-id="fb484-274">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="fb484-275">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-275">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-276">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="fb484-276">get_PenTiltX</span></span> 

<span data-ttu-id="fb484-277">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="fb484-277">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="fb484-278">公共 HRESULT [get_PenTiltX](#get_pentiltx)（INT32 \* PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="fb484-278">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="fb484-279">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-279">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-280">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="fb484-280">get_PenTiltY</span></span> 

<span data-ttu-id="fb484-281">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="fb484-281">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="fb484-282">公共 HRESULT [get_PenTiltY](#get_pentilty)（INT32 \* PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="fb484-282">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="fb484-283">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-283">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-284">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="fb484-284">get_PerformanceCount</span></span> 

<span data-ttu-id="fb484-285">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-285">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="fb484-286">公共 HRESULT [get_PerformanceCount](#get_performancecount)（UINT64 \* PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="fb484-286">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="fb484-287">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-287">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-288">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-288">get_PixelLocation</span></span> 

<span data-ttu-id="fb484-289">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-289">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="fb484-290">public HRESULT [get_PixelLocation](#get_pixellocation)（POINT \* PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="fb484-290">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="fb484-291">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-291">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-292">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-292">get_PixelLocationRaw</span></span> 

<span data-ttu-id="fb484-293">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-293">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="fb484-294">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)（POINT \* PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="fb484-294">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="fb484-295">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-295">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-296">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="fb484-296">get_PointerDeviceRect</span></span> 

<span data-ttu-id="fb484-297">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-297">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="fb484-298">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)（RECT \* PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="fb484-298">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="fb484-299">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-299">get_PointerFlags</span></span> 

<span data-ttu-id="fb484-300">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-300">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="fb484-301">公共 HRESULT [get_PointerFlags](#get_pointerflags)（UINT32 \* PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="fb484-301">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="fb484-302">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-302">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="fb484-303">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-303">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-304">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="fb484-304">get_PointerId</span></span> 

<span data-ttu-id="fb484-305">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="fb484-305">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="fb484-306">公共 HRESULT [get_PointerId](#get_pointerid)（UINT32 \* PointerId）</span><span class="sxs-lookup"><span data-stu-id="fb484-306">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="fb484-307">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-307">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-308">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="fb484-308">get_PointerKind</span></span> 

<span data-ttu-id="fb484-309">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-309">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="fb484-310">公共 HRESULT [get_PointerKind](#get_pointerkind)（DWORD \* PointerKind）</span><span class="sxs-lookup"><span data-stu-id="fb484-310">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="fb484-311">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-311">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="fb484-312">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-312">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="fb484-313">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="fb484-313">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="fb484-314">get_Time</span><span class="sxs-lookup"><span data-stu-id="fb484-314">get_Time</span></span> 

<span data-ttu-id="fb484-315">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="fb484-315">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="fb484-316">公共 HRESULT [get_Time](#get_time)（DWORD \* 时间）</span><span class="sxs-lookup"><span data-stu-id="fb484-316">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="fb484-317">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-317">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-318">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="fb484-318">get_TouchContact</span></span> 

<span data-ttu-id="fb484-319">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="fb484-319">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="fb484-320">public HRESULT [get_TouchContact](#get_touchcontact)（RECT \* TouchContact）</span><span class="sxs-lookup"><span data-stu-id="fb484-320">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="fb484-321">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-321">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-322">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-322">get_TouchContactRaw</span></span> 

<span data-ttu-id="fb484-323">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-323">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="fb484-324">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)（RECT \* TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="fb484-324">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="fb484-325">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-325">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-326">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-326">get_TouchFlags</span></span> 

<span data-ttu-id="fb484-327">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-327">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="fb484-328">公共 HRESULT [get_TouchFlags](#get_touchflags)（UINT32 \* TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="fb484-328">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="fb484-329">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-329">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="fb484-330">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-330">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-331">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="fb484-331">get_TouchMask</span></span> 

<span data-ttu-id="fb484-332">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-332">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="fb484-333">公共 HRESULT [get_TouchMask](#get_touchmask)（UINT32 \* TouchMask）</span><span class="sxs-lookup"><span data-stu-id="fb484-333">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="fb484-334">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-334">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="fb484-335">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-335">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-336">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="fb484-336">get_TouchOrientation</span></span> 

<span data-ttu-id="fb484-337">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="fb484-337">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="fb484-338">公共 HRESULT [get_TouchOrientation](#get_touchorientation)（UINT32 \* TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="fb484-338">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="fb484-339">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-339">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-340">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-340">get_TouchPressure</span></span> 

<span data-ttu-id="fb484-341">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-341">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="fb484-342">公共 HRESULT [get_TouchPressure](#get_touchpressure)（UINT32 \* TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="fb484-342">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="fb484-343">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-343">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-344">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="fb484-344">put_ButtonChangeKind</span></span> 

<span data-ttu-id="fb484-345">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-345">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="fb484-346">公共 HRESULT [put_ButtonChangeKind](#put_buttonchangekind)（INT32 ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="fb484-346">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="fb484-347">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-347">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="fb484-348">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-348">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-349">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="fb484-349">put_DisplayRect</span></span> 

<span data-ttu-id="fb484-350">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-350">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="fb484-351">public HRESULT [put_DisplayRect](#put_displayrect)（RECT DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="fb484-351">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="fb484-352">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="fb484-352">put_FrameId</span></span> 

<span data-ttu-id="fb484-353">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="fb484-353">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="fb484-354">公共 HRESULT [put_FrameId](#put_frameid)（UINT32 FrameId）</span><span class="sxs-lookup"><span data-stu-id="fb484-354">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="fb484-355">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-355">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-356">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-356">put_HimetricLocation</span></span> 

<span data-ttu-id="fb484-357">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-357">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="fb484-358">public HRESULT [put_HimetricLocation](#put_himetriclocation)（POINT HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="fb484-358">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="fb484-359">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-359">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-360">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-360">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="fb484-361">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-361">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="fb484-362">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)（POINT HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="fb484-362">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="fb484-363">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-363">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-364">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="fb484-364">put_HistoryCount</span></span> 

<span data-ttu-id="fb484-365">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-365">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="fb484-366">公共 HRESULT [put_HistoryCount](#put_historycount)（UINT32 HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="fb484-366">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="fb484-367">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-367">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-368">put_InputData</span><span class="sxs-lookup"><span data-stu-id="fb484-368">put_InputData</span></span> 

<span data-ttu-id="fb484-369">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="fb484-369">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="fb484-370">公共 HRESULT [put_InputData](#put_inputdata)（INT32 InputData）</span><span class="sxs-lookup"><span data-stu-id="fb484-370">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="fb484-371">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-371">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-372">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="fb484-372">put_KeyStates</span></span> 

<span data-ttu-id="fb484-373">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="fb484-373">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="fb484-374">公共 HRESULT [put_KeyStates](#put_keystates)（DWORD KeyStates）</span><span class="sxs-lookup"><span data-stu-id="fb484-374">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="fb484-375">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-375">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-376">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-376">put_PenFlags</span></span> 

<span data-ttu-id="fb484-377">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-377">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="fb484-378">公共 HRESULT [put_PenFlags](#put_penflags)（UINT32 PenFlags）</span><span class="sxs-lookup"><span data-stu-id="fb484-378">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="fb484-379">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-379">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="fb484-380">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-380">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-381">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="fb484-381">put_PenMask</span></span> 

<span data-ttu-id="fb484-382">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-382">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="fb484-383">公共 HRESULT [put_PenMask](#put_penmask)（UINT32 PenMask）</span><span class="sxs-lookup"><span data-stu-id="fb484-383">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="fb484-384">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-384">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="fb484-385">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-385">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-386">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-386">put_PenPressure</span></span> 

<span data-ttu-id="fb484-387">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-387">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="fb484-388">公共 HRESULT [put_PenPressure](#put_penpressure)（UINT32 PenPressure）</span><span class="sxs-lookup"><span data-stu-id="fb484-388">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="fb484-389">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-389">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-390">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="fb484-390">put_PenRotation</span></span> 

<span data-ttu-id="fb484-391">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="fb484-391">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="fb484-392">公共 HRESULT [put_PenRotation](#put_penrotation)（UINT32 PenRotation）</span><span class="sxs-lookup"><span data-stu-id="fb484-392">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="fb484-393">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-393">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-394">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="fb484-394">put_PenTiltX</span></span> 

<span data-ttu-id="fb484-395">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="fb484-395">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="fb484-396">公共 HRESULT [put_PenTiltX](#put_pentiltx)（INT32 PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="fb484-396">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="fb484-397">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-397">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-398">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="fb484-398">put_PenTiltY</span></span> 

<span data-ttu-id="fb484-399">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="fb484-399">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="fb484-400">公共 HRESULT [put_PenTiltY](#put_pentilty)（INT32 PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="fb484-400">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="fb484-401">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-401">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-402">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="fb484-402">put_PerformanceCount</span></span> 

<span data-ttu-id="fb484-403">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="fb484-403">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="fb484-404">公共 HRESULT [put_PerformanceCount](#put_performancecount)（UINT64 PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="fb484-404">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="fb484-405">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-405">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-406">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="fb484-406">put_PixelLocation</span></span> 

<span data-ttu-id="fb484-407">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="fb484-407">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="fb484-408">public HRESULT [put_PixelLocation](#put_pixellocation)（POINT PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="fb484-408">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="fb484-409">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-409">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-410">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-410">put_PixelLocationRaw</span></span> 

<span data-ttu-id="fb484-411">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-411">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="fb484-412">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)（POINT PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="fb484-412">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="fb484-413">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-413">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-414">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="fb484-414">put_PointerDeviceRect</span></span> 

<span data-ttu-id="fb484-415">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="fb484-415">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="fb484-416">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)（RECT PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="fb484-416">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="fb484-417">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-417">put_PointerFlags</span></span> 

<span data-ttu-id="fb484-418">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-418">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="fb484-419">公共 HRESULT [put_PointerFlags](#put_pointerflags)（UINT32 PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="fb484-419">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="fb484-420">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-420">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="fb484-421">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-421">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-422">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="fb484-422">put_PointerId</span></span> 

<span data-ttu-id="fb484-423">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="fb484-423">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="fb484-424">公共 HRESULT [put_PointerId](#put_pointerid)（UINT32 PointerId）</span><span class="sxs-lookup"><span data-stu-id="fb484-424">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="fb484-425">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-425">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-426">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="fb484-426">put_PointerKind</span></span> 

<span data-ttu-id="fb484-427">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="fb484-427">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="fb484-428">公共 HRESULT [put_PointerKind](#put_pointerkind)（DWORD PointerKind）</span><span class="sxs-lookup"><span data-stu-id="fb484-428">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="fb484-429">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-429">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="fb484-430">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-430">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="fb484-431">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="fb484-431">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="fb484-432">put_Time</span><span class="sxs-lookup"><span data-stu-id="fb484-432">put_Time</span></span> 

<span data-ttu-id="fb484-433">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="fb484-433">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="fb484-434">公共 HRESULT [put_Time](#put_time)（DWORD 时间）</span><span class="sxs-lookup"><span data-stu-id="fb484-434">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="fb484-435">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-435">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-436">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="fb484-436">put_TouchContact</span></span> 

<span data-ttu-id="fb484-437">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="fb484-437">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="fb484-438">public HRESULT [put_TouchContact](#put_touchcontact)（RECT TouchContact）</span><span class="sxs-lookup"><span data-stu-id="fb484-438">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="fb484-439">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-439">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-440">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="fb484-440">put_TouchContactRaw</span></span> 

<span data-ttu-id="fb484-441">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="fb484-441">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="fb484-442">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)（RECT TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="fb484-442">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="fb484-443">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-443">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-444">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="fb484-444">put_TouchFlags</span></span> 

<span data-ttu-id="fb484-445">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="fb484-445">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="fb484-446">公共 HRESULT [put_TouchFlags](#put_touchflags)（UINT32 TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="fb484-446">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="fb484-447">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-447">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="fb484-448">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-448">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-449">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="fb484-449">put_TouchMask</span></span> 

<span data-ttu-id="fb484-450">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="fb484-450">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="fb484-451">公共 HRESULT [put_TouchMask](#put_touchmask)（UINT32 TouchMask）</span><span class="sxs-lookup"><span data-stu-id="fb484-451">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="fb484-452">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-452">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="fb484-453">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="fb484-453">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-454">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="fb484-454">put_TouchOrientation</span></span> 

<span data-ttu-id="fb484-455">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="fb484-455">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="fb484-456">公共 HRESULT [put_TouchOrientation](#put_touchorientation)（UINT32 TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="fb484-456">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="fb484-457">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-457">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="fb484-458">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="fb484-458">put_TouchPressure</span></span> 

<span data-ttu-id="fb484-459">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="fb484-459">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="fb484-460">公共 HRESULT [put_TouchPressure](#put_touchpressure)（UINT32 TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="fb484-460">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="fb484-461">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="fb484-461">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

