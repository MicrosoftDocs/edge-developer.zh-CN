---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: e8563bdd77972945a1e4b81662071d07d1efeb02
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698444"
---
# <span data-ttu-id="9d3fa-104">CoreWebView2Matrix4x4 结构的 WebView2</span><span class="sxs-lookup"><span data-stu-id="9d3fa-104">Microsoft.Web.WebView2.Core.CoreWebView2Matrix4x4 struct</span></span> 

> [!NOTE]
> <span data-ttu-id="9d3fa-105">这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-105">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="9d3fa-106">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="9d3fa-106">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9d3fa-107">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="9d3fa-107">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="9d3fa-108">此转换用于在调用 CreateCoreWebView2PointerInfoFromPointerId 时计算正确的坐标。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-108">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span>

## <span data-ttu-id="9d3fa-109">摘要</span><span class="sxs-lookup"><span data-stu-id="9d3fa-109">Summary</span></span>

 <span data-ttu-id="9d3fa-110">成员</span><span class="sxs-lookup"><span data-stu-id="9d3fa-110">Members</span></span>                        | <span data-ttu-id="9d3fa-111">描述</span><span class="sxs-lookup"><span data-stu-id="9d3fa-111">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9d3fa-112">_11</span><span class="sxs-lookup"><span data-stu-id="9d3fa-112">_11</span></span>](#_11) | <span data-ttu-id="9d3fa-113">矩阵的第一行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-113">The value in the first row and first column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-114">_12</span><span class="sxs-lookup"><span data-stu-id="9d3fa-114">_12</span></span>](#_12) | <span data-ttu-id="9d3fa-115">矩阵的第一行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-115">The value in the first row and second column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-116">_13</span><span class="sxs-lookup"><span data-stu-id="9d3fa-116">_13</span></span>](#_13) | <span data-ttu-id="9d3fa-117">矩阵的第一行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-117">The value in the first row and third column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-118">_14</span><span class="sxs-lookup"><span data-stu-id="9d3fa-118">_14</span></span>](#_14) | <span data-ttu-id="9d3fa-119">矩阵的第一行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-119">The value in the first row and fourth column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-120">_21</span><span class="sxs-lookup"><span data-stu-id="9d3fa-120">_21</span></span>](#_21) | <span data-ttu-id="9d3fa-121">矩阵的第二行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-121">The value in the second row and first column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-122">_22</span><span class="sxs-lookup"><span data-stu-id="9d3fa-122">_22</span></span>](#_22) | <span data-ttu-id="9d3fa-123">矩阵的第二行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-123">The value in the second row and second column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-124">_23</span><span class="sxs-lookup"><span data-stu-id="9d3fa-124">_23</span></span>](#_23) | <span data-ttu-id="9d3fa-125">矩阵的第二行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-125">The value in the second row and third column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-126">_24</span><span class="sxs-lookup"><span data-stu-id="9d3fa-126">_24</span></span>](#_24) | <span data-ttu-id="9d3fa-127">矩阵的第二行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-127">The value in the second row and fourth column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-128">_31</span><span class="sxs-lookup"><span data-stu-id="9d3fa-128">_31</span></span>](#_31) | <span data-ttu-id="9d3fa-129">矩阵的第三行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-129">The value in the third row and first column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-130">_32</span><span class="sxs-lookup"><span data-stu-id="9d3fa-130">_32</span></span>](#_32) | <span data-ttu-id="9d3fa-131">矩阵的第三行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-131">The value in the third row and second column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-132">_33</span><span class="sxs-lookup"><span data-stu-id="9d3fa-132">_33</span></span>](#_33) | <span data-ttu-id="9d3fa-133">矩阵的第三行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-133">The value in the third row and third column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-134">_34</span><span class="sxs-lookup"><span data-stu-id="9d3fa-134">_34</span></span>](#_34) | <span data-ttu-id="9d3fa-135">矩阵的第三行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-135">The value in the third row and fourth column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-136">_41</span><span class="sxs-lookup"><span data-stu-id="9d3fa-136">_41</span></span>](#_41) | <span data-ttu-id="9d3fa-137">矩阵的第四行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-137">The value in the fourth row and first column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-138">_42</span><span class="sxs-lookup"><span data-stu-id="9d3fa-138">_42</span></span>](#_42) | <span data-ttu-id="9d3fa-139">矩阵的第四行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-139">The value in the fourth row and second column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-140">_43</span><span class="sxs-lookup"><span data-stu-id="9d3fa-140">_43</span></span>](#_43) | <span data-ttu-id="9d3fa-141">矩阵的第四行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-141">The value in the fourth row and third column of the matrix.</span></span>
[<span data-ttu-id="9d3fa-142">_44</span><span class="sxs-lookup"><span data-stu-id="9d3fa-142">_44</span></span>](#_44) | <span data-ttu-id="9d3fa-143">矩阵的第四行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-143">The value in the fourth row and fourth column of the matrix.</span></span>

<span data-ttu-id="9d3fa-144">这等效于 D2D1_MATRIX_4X4_F。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-144">This is equivalent to a D2D1_MATRIX_4X4_F.</span></span>

## <span data-ttu-id="9d3fa-145">成员</span><span class="sxs-lookup"><span data-stu-id="9d3fa-145">Members</span></span>

#### <span data-ttu-id="9d3fa-146">_11</span><span class="sxs-lookup"><span data-stu-id="9d3fa-146">_11</span></span> 

<span data-ttu-id="9d3fa-147">矩阵的第一行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-147">The value in the first row and first column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-148">公共单[_11](#_11)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-148">public Single [_11](#_11)</span></span>

#### <span data-ttu-id="9d3fa-149">_12</span><span class="sxs-lookup"><span data-stu-id="9d3fa-149">_12</span></span> 

<span data-ttu-id="9d3fa-150">矩阵的第一行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-150">The value in the first row and second column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-151">公共单[_12](#_12)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-151">public Single [_12](#_12)</span></span>

#### <span data-ttu-id="9d3fa-152">_13</span><span class="sxs-lookup"><span data-stu-id="9d3fa-152">_13</span></span> 

<span data-ttu-id="9d3fa-153">矩阵的第一行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-153">The value in the first row and third column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-154">公共单[_13](#_13)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-154">public Single [_13](#_13)</span></span>

#### <span data-ttu-id="9d3fa-155">_14</span><span class="sxs-lookup"><span data-stu-id="9d3fa-155">_14</span></span> 

<span data-ttu-id="9d3fa-156">矩阵的第一行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-156">The value in the first row and fourth column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-157">公共单[_14](#_14)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-157">public Single [_14](#_14)</span></span>

#### <span data-ttu-id="9d3fa-158">_21</span><span class="sxs-lookup"><span data-stu-id="9d3fa-158">_21</span></span> 

<span data-ttu-id="9d3fa-159">矩阵的第二行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-159">The value in the second row and first column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-160">公共单[_21](#_21)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-160">public Single [_21](#_21)</span></span>

#### <span data-ttu-id="9d3fa-161">_22</span><span class="sxs-lookup"><span data-stu-id="9d3fa-161">_22</span></span> 

<span data-ttu-id="9d3fa-162">矩阵的第二行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-162">The value in the second row and second column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-163">公共单[_22](#_22)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-163">public Single [_22](#_22)</span></span>

#### <span data-ttu-id="9d3fa-164">_23</span><span class="sxs-lookup"><span data-stu-id="9d3fa-164">_23</span></span> 

<span data-ttu-id="9d3fa-165">矩阵的第二行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-165">The value in the second row and third column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-166">公共单[_23](#_23)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-166">public Single [_23](#_23)</span></span>

#### <span data-ttu-id="9d3fa-167">_24</span><span class="sxs-lookup"><span data-stu-id="9d3fa-167">_24</span></span> 

<span data-ttu-id="9d3fa-168">矩阵的第二行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-168">The value in the second row and fourth column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-169">公共单[_24](#_24)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-169">public Single [_24](#_24)</span></span>

#### <span data-ttu-id="9d3fa-170">_31</span><span class="sxs-lookup"><span data-stu-id="9d3fa-170">_31</span></span> 

<span data-ttu-id="9d3fa-171">矩阵的第三行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-171">The value in the third row and first column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-172">公共单[_31](#_31)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-172">public Single [_31](#_31)</span></span>

#### <span data-ttu-id="9d3fa-173">_32</span><span class="sxs-lookup"><span data-stu-id="9d3fa-173">_32</span></span> 

<span data-ttu-id="9d3fa-174">矩阵的第三行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-174">The value in the third row and second column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-175">公共单[_32](#_32)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-175">public Single [_32](#_32)</span></span>

#### <span data-ttu-id="9d3fa-176">_33</span><span class="sxs-lookup"><span data-stu-id="9d3fa-176">_33</span></span> 

<span data-ttu-id="9d3fa-177">矩阵的第三行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-177">The value in the third row and third column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-178">公共单[_33](#_33)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-178">public Single [_33](#_33)</span></span>

#### <span data-ttu-id="9d3fa-179">_34</span><span class="sxs-lookup"><span data-stu-id="9d3fa-179">_34</span></span> 

<span data-ttu-id="9d3fa-180">矩阵的第三行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-180">The value in the third row and fourth column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-181">公共单[_34](#_34)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-181">public Single [_34](#_34)</span></span>

#### <span data-ttu-id="9d3fa-182">_41</span><span class="sxs-lookup"><span data-stu-id="9d3fa-182">_41</span></span> 

<span data-ttu-id="9d3fa-183">矩阵的第四行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-183">The value in the fourth row and first column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-184">公共单[_41](#_41)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-184">public Single [_41](#_41)</span></span>

#### <span data-ttu-id="9d3fa-185">_42</span><span class="sxs-lookup"><span data-stu-id="9d3fa-185">_42</span></span> 

<span data-ttu-id="9d3fa-186">矩阵的第四行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-186">The value in the fourth row and second column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-187">公共单[_42](#_42)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-187">public Single [_42](#_42)</span></span>

#### <span data-ttu-id="9d3fa-188">_43</span><span class="sxs-lookup"><span data-stu-id="9d3fa-188">_43</span></span> 

<span data-ttu-id="9d3fa-189">矩阵的第四行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-189">The value in the fourth row and third column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-190">公共单[_43](#_43)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-190">public Single [_43](#_43)</span></span>

#### <span data-ttu-id="9d3fa-191">_44</span><span class="sxs-lookup"><span data-stu-id="9d3fa-191">_44</span></span> 

<span data-ttu-id="9d3fa-192">矩阵的第四行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="9d3fa-192">The value in the fourth row and fourth column of the matrix.</span></span>

> <span data-ttu-id="9d3fa-193">公共单[_44](#_44)</span><span class="sxs-lookup"><span data-stu-id="9d3fa-193">public Single [_44](#_44)</span></span>

