---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalPointerInfo
ms.openlocfilehash: bc35ebaf3f1b5acf12a1d379336cd006f962390e
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011766"
---
# <span data-ttu-id="aa47d-104">interface ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="aa47d-104">interface ICoreWebView2ExperimentalPointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="aa47d-105">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="aa47d-105">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="aa47d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="aa47d-106">Summary</span></span>

 <span data-ttu-id="aa47d-107">成员</span><span class="sxs-lookup"><span data-stu-id="aa47d-107">Members</span></span>                        | <span data-ttu-id="aa47d-108">描述</span><span class="sxs-lookup"><span data-stu-id="aa47d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aa47d-109">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-109">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="aa47d-110">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-110">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="aa47d-111">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-111">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="aa47d-112">获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-112">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="aa47d-113">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="aa47d-113">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="aa47d-114">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="aa47d-114">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="aa47d-115">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-115">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="aa47d-116">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-116">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-117">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-117">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="aa47d-118">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-118">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="aa47d-119">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-119">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="aa47d-120">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-120">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="aa47d-121">get_InputData</span><span class="sxs-lookup"><span data-stu-id="aa47d-121">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="aa47d-122">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="aa47d-122">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="aa47d-123">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="aa47d-123">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="aa47d-124">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="aa47d-124">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="aa47d-125">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-125">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="aa47d-126">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-126">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="aa47d-127">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-127">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="aa47d-128">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-128">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="aa47d-129">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-129">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="aa47d-130">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-130">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="aa47d-131">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="aa47d-131">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="aa47d-132">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-132">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-133">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="aa47d-133">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="aa47d-134">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="aa47d-134">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="aa47d-135">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="aa47d-135">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="aa47d-136">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="aa47d-136">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="aa47d-137">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-137">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="aa47d-138">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-138">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="aa47d-139">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-139">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="aa47d-140">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-140">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-141">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-141">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="aa47d-142">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-142">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="aa47d-143">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-143">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="aa47d-144">获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-144">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="aa47d-145">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-145">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="aa47d-146">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-146">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="aa47d-147">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="aa47d-147">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="aa47d-148">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="aa47d-148">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="aa47d-149">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-149">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="aa47d-150">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-150">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="aa47d-151">get_Time</span><span class="sxs-lookup"><span data-stu-id="aa47d-151">get_Time</span></span>](#get_time) | <span data-ttu-id="aa47d-152">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="aa47d-152">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="aa47d-153">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="aa47d-153">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="aa47d-154">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="aa47d-154">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="aa47d-155">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-155">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="aa47d-156">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-156">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="aa47d-157">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-157">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="aa47d-158">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-158">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="aa47d-159">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-159">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="aa47d-160">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-160">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="aa47d-161">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="aa47d-161">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="aa47d-162">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-162">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-163">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-163">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="aa47d-164">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-164">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="aa47d-165">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-165">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="aa47d-166">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-166">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="aa47d-167">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-167">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="aa47d-168">按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-168">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="aa47d-169">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="aa47d-169">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="aa47d-170">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="aa47d-170">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="aa47d-171">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-171">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="aa47d-172">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-172">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-173">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-173">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="aa47d-174">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-174">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="aa47d-175">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-175">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="aa47d-176">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-176">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="aa47d-177">put_InputData</span><span class="sxs-lookup"><span data-stu-id="aa47d-177">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="aa47d-178">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="aa47d-178">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="aa47d-179">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="aa47d-179">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="aa47d-180">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="aa47d-180">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="aa47d-181">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-181">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="aa47d-182">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-182">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="aa47d-183">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-183">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="aa47d-184">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-184">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="aa47d-185">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-185">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="aa47d-186">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-186">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="aa47d-187">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="aa47d-187">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="aa47d-188">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-188">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-189">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="aa47d-189">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="aa47d-190">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="aa47d-190">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="aa47d-191">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="aa47d-191">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="aa47d-192">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="aa47d-192">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="aa47d-193">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-193">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="aa47d-194">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-194">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="aa47d-195">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-195">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="aa47d-196">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-196">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-197">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-197">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="aa47d-198">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-198">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="aa47d-199">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-199">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="aa47d-200">按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-200">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="aa47d-201">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-201">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="aa47d-202">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-202">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="aa47d-203">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="aa47d-203">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="aa47d-204">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="aa47d-204">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="aa47d-205">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-205">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="aa47d-206">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-206">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="aa47d-207">put_Time</span><span class="sxs-lookup"><span data-stu-id="aa47d-207">put_Time</span></span>](#put_time) | <span data-ttu-id="aa47d-208">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="aa47d-208">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="aa47d-209">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="aa47d-209">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="aa47d-210">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="aa47d-210">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="aa47d-211">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-211">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="aa47d-212">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-212">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="aa47d-213">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-213">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="aa47d-214">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-214">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="aa47d-215">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-215">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="aa47d-216">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-216">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="aa47d-217">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="aa47d-217">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="aa47d-218">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-218">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="aa47d-219">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-219">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="aa47d-220">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-220">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="aa47d-221">它将获取所有三个字段中的字段，并排除某些 win32 特定的数据类型（如 HWND 和句柄）。</span><span class="sxs-lookup"><span data-stu-id="aa47d-221">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="aa47d-222">注意，sourceDevice 已被取出，但我们希望 PointerDeviceRect 和 DisplayRect 涵盖 sourceDevice 的现有使用情形。</span><span class="sxs-lookup"><span data-stu-id="aa47d-222">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="aa47d-223">另一个显著的区别是，任何点或 rect 位置都应位于 web 视图物理坐标中。</span><span class="sxs-lookup"><span data-stu-id="aa47d-223">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="aa47d-224">即，相对于 web 视图的坐标和未应用的 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="aa47d-224">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="aa47d-225">成员</span><span class="sxs-lookup"><span data-stu-id="aa47d-225">Members</span></span>

#### <span data-ttu-id="aa47d-226">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-226">get_ButtonChangeKind</span></span> 

<span data-ttu-id="aa47d-227">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-227">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="aa47d-228">公共 HRESULT [get_ButtonChangeKind](#get_buttonchangekind) (INT32 \* ButtonChangeKind) </span><span class="sxs-lookup"><span data-stu-id="aa47d-228">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="aa47d-229">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-229">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="aa47d-230">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-230">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-231">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-231">get_DisplayRect</span></span> 

<span data-ttu-id="aa47d-232">获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-232">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="aa47d-233">公共 HRESULT [get_DisplayRect](#get_displayrect) (RECT \* DisplayRect) </span><span class="sxs-lookup"><span data-stu-id="aa47d-233">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="aa47d-234">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="aa47d-234">get_FrameId</span></span> 

<span data-ttu-id="aa47d-235">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="aa47d-235">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="aa47d-236">公共 HRESULT [get_FrameId](#get_frameid) (UINT32 \* FrameId) </span><span class="sxs-lookup"><span data-stu-id="aa47d-236">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="aa47d-237">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-237">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-238">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-238">get_HimetricLocation</span></span> 

<span data-ttu-id="aa47d-239">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-239">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-240">公共 HRESULT [get_HimetricLocation](#get_himetriclocation) (POINT \* HimetricLocation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-240">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="aa47d-241">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-241">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-242">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-242">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="aa47d-243">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-243">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="aa47d-244">公共 HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw) (POINT \* HimetricLocationRaw) </span><span class="sxs-lookup"><span data-stu-id="aa47d-244">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="aa47d-245">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-245">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-246">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-246">get_HistoryCount</span></span> 

<span data-ttu-id="aa47d-247">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-247">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="aa47d-248">公共 HRESULT [get_HistoryCount](#get_historycount) (UINT32 \* HistoryCount) </span><span class="sxs-lookup"><span data-stu-id="aa47d-248">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="aa47d-249">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-249">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-250">get_InputData</span><span class="sxs-lookup"><span data-stu-id="aa47d-250">get_InputData</span></span> 

<span data-ttu-id="aa47d-251">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="aa47d-251">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="aa47d-252">公共 HRESULT [get_InputData](#get_inputdata) (INT32 \* InputData) </span><span class="sxs-lookup"><span data-stu-id="aa47d-252">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="aa47d-253">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-253">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-254">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="aa47d-254">get_KeyStates</span></span> 

<span data-ttu-id="aa47d-255">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="aa47d-255">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="aa47d-256">公共 HRESULT [get_KeyStates](#get_keystates) (DWORD \* KeyStates) </span><span class="sxs-lookup"><span data-stu-id="aa47d-256">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="aa47d-257">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-257">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-258">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-258">get_PenFlags</span></span> 

<span data-ttu-id="aa47d-259">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-259">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="aa47d-260">公共 HRESULT [get_PenFlags](#get_penflags) (UINT32 \* PenFlags) </span><span class="sxs-lookup"><span data-stu-id="aa47d-260">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="aa47d-261">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-261">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="aa47d-262">这些值由 Windows SDK 中的 PEN_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-262">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-263">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-263">get_PenMask</span></span> 

<span data-ttu-id="aa47d-264">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-264">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="aa47d-265">公共 HRESULT [get_PenMask](#get_penmask) (UINT32 \* PenMask) </span><span class="sxs-lookup"><span data-stu-id="aa47d-265">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="aa47d-266">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-266">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="aa47d-267">这些值由 Windows SDK 中的 PEN_MASK 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-267">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-268">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-268">get_PenPressure</span></span> 

<span data-ttu-id="aa47d-269">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-269">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="aa47d-270">公共 HRESULT [get_PenPressure](#get_penpressure) (UINT32 \* PenPressure) </span><span class="sxs-lookup"><span data-stu-id="aa47d-270">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="aa47d-271">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-271">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-272">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="aa47d-272">get_PenRotation</span></span> 

<span data-ttu-id="aa47d-273">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-273">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-274">公共 HRESULT [get_PenRotation](#get_penrotation) (UINT32 \* PenRotation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-274">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="aa47d-275">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-275">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-276">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="aa47d-276">get_PenTiltX</span></span> 

<span data-ttu-id="aa47d-277">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="aa47d-277">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="aa47d-278">公共 HRESULT [get_PenTiltX](#get_pentiltx) (INT32 \* PenTiltX) </span><span class="sxs-lookup"><span data-stu-id="aa47d-278">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="aa47d-279">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-279">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-280">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="aa47d-280">get_PenTiltY</span></span> 

<span data-ttu-id="aa47d-281">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="aa47d-281">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="aa47d-282">公共 HRESULT [get_PenTiltY](#get_pentilty) (INT32 \* PenTiltY) </span><span class="sxs-lookup"><span data-stu-id="aa47d-282">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="aa47d-283">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-283">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-284">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-284">get_PerformanceCount</span></span> 

<span data-ttu-id="aa47d-285">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-285">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="aa47d-286">公共 HRESULT [get_PerformanceCount](#get_performancecount) (UINT64 \* PerformanceCount) </span><span class="sxs-lookup"><span data-stu-id="aa47d-286">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="aa47d-287">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-287">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-288">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-288">get_PixelLocation</span></span> 

<span data-ttu-id="aa47d-289">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-289">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-290">公共 HRESULT [get_PixelLocation](#get_pixellocation) (POINT \* PixelLocation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-290">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="aa47d-291">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-291">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-292">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-292">get_PixelLocationRaw</span></span> 

<span data-ttu-id="aa47d-293">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-293">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="aa47d-294">公共 HRESULT [get_PixelLocationRaw](#get_pixellocationraw) (POINT \* PixelLocationRaw) </span><span class="sxs-lookup"><span data-stu-id="aa47d-294">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="aa47d-295">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-295">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-296">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-296">get_PointerDeviceRect</span></span> 

<span data-ttu-id="aa47d-297">获取在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-297">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="aa47d-298">公共 HRESULT [get_PointerDeviceRect](#get_pointerdevicerect) (RECT \* PointerDeviceRect) </span><span class="sxs-lookup"><span data-stu-id="aa47d-298">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="aa47d-299">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-299">get_PointerFlags</span></span> 

<span data-ttu-id="aa47d-300">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-300">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="aa47d-301">公共 HRESULT [get_PointerFlags](#get_pointerflags) (UINT32 \* PointerFlags) </span><span class="sxs-lookup"><span data-stu-id="aa47d-301">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="aa47d-302">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-302">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="aa47d-303">这些值由 Windows SDK 中的 POINTER_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-303">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-304">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="aa47d-304">get_PointerId</span></span> 

<span data-ttu-id="aa47d-305">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="aa47d-305">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="aa47d-306">公共 HRESULT [get_PointerId](#get_pointerid) (UINT32 \* PointerId) </span><span class="sxs-lookup"><span data-stu-id="aa47d-306">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="aa47d-307">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-307">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-308">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-308">get_PointerKind</span></span> 

<span data-ttu-id="aa47d-309">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-309">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="aa47d-310">公共 HRESULT [get_PointerKind](#get_pointerkind) (DWORD \* PointerKind) </span><span class="sxs-lookup"><span data-stu-id="aa47d-310">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="aa47d-311">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-311">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="aa47d-312">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-312">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="aa47d-313">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="aa47d-313">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="aa47d-314">get_Time</span><span class="sxs-lookup"><span data-stu-id="aa47d-314">get_Time</span></span> 

<span data-ttu-id="aa47d-315">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="aa47d-315">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="aa47d-316">公共 HRESULT [get_Time](#get_time) (DWORD \* 时间) </span><span class="sxs-lookup"><span data-stu-id="aa47d-316">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="aa47d-317">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-317">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-318">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="aa47d-318">get_TouchContact</span></span> 

<span data-ttu-id="aa47d-319">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="aa47d-319">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="aa47d-320">公共 HRESULT [get_TouchContact](#get_touchcontact) (RECT \* TouchContact) </span><span class="sxs-lookup"><span data-stu-id="aa47d-320">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="aa47d-321">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-321">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-322">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-322">get_TouchContactRaw</span></span> 

<span data-ttu-id="aa47d-323">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-323">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="aa47d-324">公共 HRESULT [get_TouchContactRaw](#get_touchcontactraw) (RECT \* TouchContactRaw) </span><span class="sxs-lookup"><span data-stu-id="aa47d-324">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="aa47d-325">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-325">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-326">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-326">get_TouchFlags</span></span> 

<span data-ttu-id="aa47d-327">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-327">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="aa47d-328">公共 HRESULT [get_TouchFlags](#get_touchflags) (UINT32 \* TouchFlags) </span><span class="sxs-lookup"><span data-stu-id="aa47d-328">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="aa47d-329">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-329">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="aa47d-330">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-330">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-331">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-331">get_TouchMask</span></span> 

<span data-ttu-id="aa47d-332">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-332">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="aa47d-333">公共 HRESULT [get_TouchMask](#get_touchmask) (UINT32 \* TouchMask) </span><span class="sxs-lookup"><span data-stu-id="aa47d-333">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="aa47d-334">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-334">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="aa47d-335">这些值由 Windows SDK 中的 TOUCH_MASK 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-335">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-336">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="aa47d-336">get_TouchOrientation</span></span> 

<span data-ttu-id="aa47d-337">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-337">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-338">公共 HRESULT [get_TouchOrientation](#get_touchorientation) (UINT32 \* TouchOrientation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-338">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="aa47d-339">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的方向属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-339">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-340">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-340">get_TouchPressure</span></span> 

<span data-ttu-id="aa47d-341">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-341">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="aa47d-342">公共 HRESULT [get_TouchPressure](#get_touchpressure) (UINT32 \* TouchPressure) </span><span class="sxs-lookup"><span data-stu-id="aa47d-342">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="aa47d-343">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-343">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-344">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-344">put_ButtonChangeKind</span></span> 

<span data-ttu-id="aa47d-345">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-345">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="aa47d-346">公共 HRESULT [put_ButtonChangeKind](#put_buttonchangekind) (INT32 ButtonChangeKind) </span><span class="sxs-lookup"><span data-stu-id="aa47d-346">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="aa47d-347">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-347">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="aa47d-348">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-348">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-349">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-349">put_DisplayRect</span></span> 

<span data-ttu-id="aa47d-350">按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-350">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="aa47d-351">公共 HRESULT [put_DisplayRect](#put_displayrect) (RECT DisplayRect) </span><span class="sxs-lookup"><span data-stu-id="aa47d-351">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="aa47d-352">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="aa47d-352">put_FrameId</span></span> 

<span data-ttu-id="aa47d-353">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="aa47d-353">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="aa47d-354">公共 HRESULT [put_FrameId](#put_frameid) (UINT32 FrameId) </span><span class="sxs-lookup"><span data-stu-id="aa47d-354">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="aa47d-355">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-355">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-356">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-356">put_HimetricLocation</span></span> 

<span data-ttu-id="aa47d-357">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-357">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-358">公共 HRESULT [put_HimetricLocation](#put_himetriclocation) (POINT HimetricLocation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-358">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="aa47d-359">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-359">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-360">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-360">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="aa47d-361">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-361">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="aa47d-362">公共 HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw) (POINT HimetricLocationRaw) </span><span class="sxs-lookup"><span data-stu-id="aa47d-362">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="aa47d-363">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-363">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-364">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-364">put_HistoryCount</span></span> 

<span data-ttu-id="aa47d-365">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-365">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="aa47d-366">公共 HRESULT [put_HistoryCount](#put_historycount) (UINT32 HistoryCount) </span><span class="sxs-lookup"><span data-stu-id="aa47d-366">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="aa47d-367">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-367">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-368">put_InputData</span><span class="sxs-lookup"><span data-stu-id="aa47d-368">put_InputData</span></span> 

<span data-ttu-id="aa47d-369">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="aa47d-369">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="aa47d-370">公共 HRESULT [put_InputData](#put_inputdata) (INT32 InputData) </span><span class="sxs-lookup"><span data-stu-id="aa47d-370">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="aa47d-371">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-371">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-372">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="aa47d-372">put_KeyStates</span></span> 

<span data-ttu-id="aa47d-373">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="aa47d-373">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="aa47d-374">公共 HRESULT [put_KeyStates](#put_keystates) (DWORD KeyStates) </span><span class="sxs-lookup"><span data-stu-id="aa47d-374">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="aa47d-375">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-375">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-376">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-376">put_PenFlags</span></span> 

<span data-ttu-id="aa47d-377">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-377">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="aa47d-378">公共 HRESULT [put_PenFlags](#put_penflags) (UINT32 PenFlags) </span><span class="sxs-lookup"><span data-stu-id="aa47d-378">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="aa47d-379">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-379">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="aa47d-380">这些值由 Windows SDK 中的 PEN_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-380">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-381">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-381">put_PenMask</span></span> 

<span data-ttu-id="aa47d-382">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-382">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="aa47d-383">公共 HRESULT [put_PenMask](#put_penmask) (UINT32 PenMask) </span><span class="sxs-lookup"><span data-stu-id="aa47d-383">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="aa47d-384">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-384">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="aa47d-385">这些值由 Windows SDK 中的 PEN_MASK 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-385">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-386">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-386">put_PenPressure</span></span> 

<span data-ttu-id="aa47d-387">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-387">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="aa47d-388">公共 HRESULT [put_PenPressure](#put_penpressure) (UINT32 PenPressure) </span><span class="sxs-lookup"><span data-stu-id="aa47d-388">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="aa47d-389">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-389">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-390">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="aa47d-390">put_PenRotation</span></span> 

<span data-ttu-id="aa47d-391">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-391">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-392">公共 HRESULT [put_PenRotation](#put_penrotation) (UINT32 PenRotation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-392">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="aa47d-393">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-393">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-394">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="aa47d-394">put_PenTiltX</span></span> 

<span data-ttu-id="aa47d-395">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="aa47d-395">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="aa47d-396">公共 HRESULT [put_PenTiltX](#put_pentiltx) (INT32 PenTiltX) </span><span class="sxs-lookup"><span data-stu-id="aa47d-396">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="aa47d-397">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-397">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-398">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="aa47d-398">put_PenTiltY</span></span> 

<span data-ttu-id="aa47d-399">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="aa47d-399">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="aa47d-400">公共 HRESULT [put_PenTiltY](#put_pentilty) (INT32 PenTiltY) </span><span class="sxs-lookup"><span data-stu-id="aa47d-400">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="aa47d-401">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-401">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-402">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="aa47d-402">put_PerformanceCount</span></span> 

<span data-ttu-id="aa47d-403">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="aa47d-403">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="aa47d-404">公共 HRESULT [put_PerformanceCount](#put_performancecount) (UINT64 PerformanceCount) </span><span class="sxs-lookup"><span data-stu-id="aa47d-404">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="aa47d-405">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-405">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-406">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="aa47d-406">put_PixelLocation</span></span> 

<span data-ttu-id="aa47d-407">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-407">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-408">公共 HRESULT [put_PixelLocation](#put_pixellocation) (POINT PixelLocation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-408">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="aa47d-409">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-409">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-410">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-410">put_PixelLocationRaw</span></span> 

<span data-ttu-id="aa47d-411">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-411">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="aa47d-412">公共 HRESULT [put_PixelLocationRaw](#put_pixellocationraw) (POINT PixelLocationRaw) </span><span class="sxs-lookup"><span data-stu-id="aa47d-412">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="aa47d-413">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-413">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-414">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="aa47d-414">put_PointerDeviceRect</span></span> 

<span data-ttu-id="aa47d-415">按照 Windows SDK (winuser) 中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="aa47d-415">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="aa47d-416">公共 HRESULT [put_PointerDeviceRect](#put_pointerdevicerect) (RECT PointerDeviceRect) </span><span class="sxs-lookup"><span data-stu-id="aa47d-416">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="aa47d-417">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-417">put_PointerFlags</span></span> 

<span data-ttu-id="aa47d-418">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-418">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="aa47d-419">公共 HRESULT [put_PointerFlags](#put_pointerflags) (UINT32 PointerFlags) </span><span class="sxs-lookup"><span data-stu-id="aa47d-419">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="aa47d-420">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-420">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="aa47d-421">这些值由 Windows SDK 中的 POINTER_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-421">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-422">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="aa47d-422">put_PointerId</span></span> 

<span data-ttu-id="aa47d-423">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="aa47d-423">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="aa47d-424">公共 HRESULT [put_PointerId](#put_pointerid) (UINT32 PointerId) </span><span class="sxs-lookup"><span data-stu-id="aa47d-424">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="aa47d-425">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-425">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-426">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="aa47d-426">put_PointerKind</span></span> 

<span data-ttu-id="aa47d-427">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="aa47d-427">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="aa47d-428">公共 HRESULT [put_PointerKind](#put_pointerkind) (DWORD PointerKind) </span><span class="sxs-lookup"><span data-stu-id="aa47d-428">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="aa47d-429">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-429">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="aa47d-430">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-430">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="aa47d-431">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="aa47d-431">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="aa47d-432">put_Time</span><span class="sxs-lookup"><span data-stu-id="aa47d-432">put_Time</span></span> 

<span data-ttu-id="aa47d-433">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="aa47d-433">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="aa47d-434"> (DWORD 时间的公共 HRESULT [put_Time](#put_time)) </span><span class="sxs-lookup"><span data-stu-id="aa47d-434">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="aa47d-435">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-435">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-436">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="aa47d-436">put_TouchContact</span></span> 

<span data-ttu-id="aa47d-437">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="aa47d-437">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="aa47d-438">公共 HRESULT [put_TouchContact](#put_touchcontact) (RECT TouchContact) </span><span class="sxs-lookup"><span data-stu-id="aa47d-438">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="aa47d-439">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-439">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-440">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="aa47d-440">put_TouchContactRaw</span></span> 

<span data-ttu-id="aa47d-441">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="aa47d-441">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="aa47d-442">公共 HRESULT [put_TouchContactRaw](#put_touchcontactraw) (RECT TouchContactRaw) </span><span class="sxs-lookup"><span data-stu-id="aa47d-442">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="aa47d-443">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-443">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-444">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="aa47d-444">put_TouchFlags</span></span> 

<span data-ttu-id="aa47d-445">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="aa47d-445">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="aa47d-446">公共 HRESULT [put_TouchFlags](#put_touchflags) (UINT32 TouchFlags) </span><span class="sxs-lookup"><span data-stu-id="aa47d-446">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="aa47d-447">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-447">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="aa47d-448">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-448">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-449">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="aa47d-449">put_TouchMask</span></span> 

<span data-ttu-id="aa47d-450">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="aa47d-450">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="aa47d-451">公共 HRESULT [put_TouchMask](#put_touchmask) (UINT32 TouchMask) </span><span class="sxs-lookup"><span data-stu-id="aa47d-451">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="aa47d-452">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-452">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="aa47d-453">这些值由 Windows SDK 中的 TOUCH_MASK 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="aa47d-453">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-454">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="aa47d-454">put_TouchOrientation</span></span> 

<span data-ttu-id="aa47d-455">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="aa47d-455">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="aa47d-456">公共 HRESULT [put_TouchOrientation](#put_touchorientation) (UINT32 TouchOrientation) </span><span class="sxs-lookup"><span data-stu-id="aa47d-456">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="aa47d-457">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的方向属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-457">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="aa47d-458">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="aa47d-458">put_TouchPressure</span></span> 

<span data-ttu-id="aa47d-459">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="aa47d-459">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="aa47d-460">公共 HRESULT [put_TouchPressure](#put_touchpressure) (UINT32 TouchPressure) </span><span class="sxs-lookup"><span data-stu-id="aa47d-460">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="aa47d-461">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="aa47d-461">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

