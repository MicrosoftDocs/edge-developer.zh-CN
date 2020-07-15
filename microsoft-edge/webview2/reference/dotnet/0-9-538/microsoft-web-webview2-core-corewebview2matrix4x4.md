---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2Matrix4x4 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: bac470b29b08357d27ba77e986f19739acaaa05d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878874"
---
# <span data-ttu-id="fcf2e-104">CoreWebView2Matrix4x4 结构的 WebView2</span><span class="sxs-lookup"><span data-stu-id="fcf2e-104">Microsoft.Web.WebView2.Core.CoreWebView2Matrix4x4 struct</span></span> 

> [!NOTE]
> <span data-ttu-id="fcf2e-105">这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-105">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="fcf2e-106">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="fcf2e-106">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="fcf2e-107">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="fcf2e-107">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="fcf2e-108">此转换用于在调用 CreateCoreWebView2PointerInfoFromPointerId 时计算正确的坐标。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-108">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span>

## <span data-ttu-id="fcf2e-109">摘要</span><span class="sxs-lookup"><span data-stu-id="fcf2e-109">Summary</span></span>

 <span data-ttu-id="fcf2e-110">成员</span><span class="sxs-lookup"><span data-stu-id="fcf2e-110">Members</span></span>                        | <span data-ttu-id="fcf2e-111">描述</span><span class="sxs-lookup"><span data-stu-id="fcf2e-111">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fcf2e-112">_11</span><span class="sxs-lookup"><span data-stu-id="fcf2e-112">_11</span></span>](#_11) | <span data-ttu-id="fcf2e-113">矩阵的第一行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-113">The value in the first row and first column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-114">_12</span><span class="sxs-lookup"><span data-stu-id="fcf2e-114">_12</span></span>](#_12) | <span data-ttu-id="fcf2e-115">矩阵的第一行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-115">The value in the first row and second column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-116">_13</span><span class="sxs-lookup"><span data-stu-id="fcf2e-116">_13</span></span>](#_13) | <span data-ttu-id="fcf2e-117">矩阵的第一行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-117">The value in the first row and third column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-118">_14</span><span class="sxs-lookup"><span data-stu-id="fcf2e-118">_14</span></span>](#_14) | <span data-ttu-id="fcf2e-119">矩阵的第一行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-119">The value in the first row and fourth column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-120">_21</span><span class="sxs-lookup"><span data-stu-id="fcf2e-120">_21</span></span>](#_21) | <span data-ttu-id="fcf2e-121">矩阵的第二行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-121">The value in the second row and first column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-122">_22</span><span class="sxs-lookup"><span data-stu-id="fcf2e-122">_22</span></span>](#_22) | <span data-ttu-id="fcf2e-123">矩阵的第二行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-123">The value in the second row and second column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-124">_23</span><span class="sxs-lookup"><span data-stu-id="fcf2e-124">_23</span></span>](#_23) | <span data-ttu-id="fcf2e-125">矩阵的第二行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-125">The value in the second row and third column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-126">_24</span><span class="sxs-lookup"><span data-stu-id="fcf2e-126">_24</span></span>](#_24) | <span data-ttu-id="fcf2e-127">矩阵的第二行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-127">The value in the second row and fourth column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-128">_31</span><span class="sxs-lookup"><span data-stu-id="fcf2e-128">_31</span></span>](#_31) | <span data-ttu-id="fcf2e-129">矩阵的第三行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-129">The value in the third row and first column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-130">_32</span><span class="sxs-lookup"><span data-stu-id="fcf2e-130">_32</span></span>](#_32) | <span data-ttu-id="fcf2e-131">矩阵的第三行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-131">The value in the third row and second column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-132">_33</span><span class="sxs-lookup"><span data-stu-id="fcf2e-132">_33</span></span>](#_33) | <span data-ttu-id="fcf2e-133">矩阵的第三行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-133">The value in the third row and third column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-134">_34</span><span class="sxs-lookup"><span data-stu-id="fcf2e-134">_34</span></span>](#_34) | <span data-ttu-id="fcf2e-135">矩阵的第三行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-135">The value in the third row and fourth column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-136">_41</span><span class="sxs-lookup"><span data-stu-id="fcf2e-136">_41</span></span>](#_41) | <span data-ttu-id="fcf2e-137">矩阵的第四行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-137">The value in the fourth row and first column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-138">_42</span><span class="sxs-lookup"><span data-stu-id="fcf2e-138">_42</span></span>](#_42) | <span data-ttu-id="fcf2e-139">矩阵的第四行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-139">The value in the fourth row and second column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-140">_43</span><span class="sxs-lookup"><span data-stu-id="fcf2e-140">_43</span></span>](#_43) | <span data-ttu-id="fcf2e-141">矩阵的第四行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-141">The value in the fourth row and third column of the matrix.</span></span>
[<span data-ttu-id="fcf2e-142">_44</span><span class="sxs-lookup"><span data-stu-id="fcf2e-142">_44</span></span>](#_44) | <span data-ttu-id="fcf2e-143">矩阵的第四行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-143">The value in the fourth row and fourth column of the matrix.</span></span>

<span data-ttu-id="fcf2e-144">这等效于 D2D1_MATRIX_4X4_F。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-144">This is equivalent to a D2D1_MATRIX_4X4_F.</span></span>

## <span data-ttu-id="fcf2e-145">成员</span><span class="sxs-lookup"><span data-stu-id="fcf2e-145">Members</span></span>

#### <span data-ttu-id="fcf2e-146">_11</span><span class="sxs-lookup"><span data-stu-id="fcf2e-146">_11</span></span> 

<span data-ttu-id="fcf2e-147">矩阵的第一行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-147">The value in the first row and first column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-148">公共单[_11](#_11)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-148">public Single [_11](#_11)</span></span>

#### <span data-ttu-id="fcf2e-149">_12</span><span class="sxs-lookup"><span data-stu-id="fcf2e-149">_12</span></span> 

<span data-ttu-id="fcf2e-150">矩阵的第一行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-150">The value in the first row and second column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-151">公共单[_12](#_12)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-151">public Single [_12](#_12)</span></span>

#### <span data-ttu-id="fcf2e-152">_13</span><span class="sxs-lookup"><span data-stu-id="fcf2e-152">_13</span></span> 

<span data-ttu-id="fcf2e-153">矩阵的第一行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-153">The value in the first row and third column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-154">公共单[_13](#_13)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-154">public Single [_13](#_13)</span></span>

#### <span data-ttu-id="fcf2e-155">_14</span><span class="sxs-lookup"><span data-stu-id="fcf2e-155">_14</span></span> 

<span data-ttu-id="fcf2e-156">矩阵的第一行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-156">The value in the first row and fourth column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-157">公共单[_14](#_14)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-157">public Single [_14](#_14)</span></span>

#### <span data-ttu-id="fcf2e-158">_21</span><span class="sxs-lookup"><span data-stu-id="fcf2e-158">_21</span></span> 

<span data-ttu-id="fcf2e-159">矩阵的第二行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-159">The value in the second row and first column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-160">公共单[_21](#_21)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-160">public Single [_21](#_21)</span></span>

#### <span data-ttu-id="fcf2e-161">_22</span><span class="sxs-lookup"><span data-stu-id="fcf2e-161">_22</span></span> 

<span data-ttu-id="fcf2e-162">矩阵的第二行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-162">The value in the second row and second column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-163">公共单[_22](#_22)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-163">public Single [_22](#_22)</span></span>

#### <span data-ttu-id="fcf2e-164">_23</span><span class="sxs-lookup"><span data-stu-id="fcf2e-164">_23</span></span> 

<span data-ttu-id="fcf2e-165">矩阵的第二行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-165">The value in the second row and third column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-166">公共单[_23](#_23)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-166">public Single [_23](#_23)</span></span>

#### <span data-ttu-id="fcf2e-167">_24</span><span class="sxs-lookup"><span data-stu-id="fcf2e-167">_24</span></span> 

<span data-ttu-id="fcf2e-168">矩阵的第二行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-168">The value in the second row and fourth column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-169">公共单[_24](#_24)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-169">public Single [_24](#_24)</span></span>

#### <span data-ttu-id="fcf2e-170">_31</span><span class="sxs-lookup"><span data-stu-id="fcf2e-170">_31</span></span> 

<span data-ttu-id="fcf2e-171">矩阵的第三行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-171">The value in the third row and first column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-172">公共单[_31](#_31)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-172">public Single [_31](#_31)</span></span>

#### <span data-ttu-id="fcf2e-173">_32</span><span class="sxs-lookup"><span data-stu-id="fcf2e-173">_32</span></span> 

<span data-ttu-id="fcf2e-174">矩阵的第三行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-174">The value in the third row and second column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-175">公共单[_32](#_32)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-175">public Single [_32](#_32)</span></span>

#### <span data-ttu-id="fcf2e-176">_33</span><span class="sxs-lookup"><span data-stu-id="fcf2e-176">_33</span></span> 

<span data-ttu-id="fcf2e-177">矩阵的第三行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-177">The value in the third row and third column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-178">公共单[_33](#_33)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-178">public Single [_33](#_33)</span></span>

#### <span data-ttu-id="fcf2e-179">_34</span><span class="sxs-lookup"><span data-stu-id="fcf2e-179">_34</span></span> 

<span data-ttu-id="fcf2e-180">矩阵的第三行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-180">The value in the third row and fourth column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-181">公共单[_34](#_34)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-181">public Single [_34](#_34)</span></span>

#### <span data-ttu-id="fcf2e-182">_41</span><span class="sxs-lookup"><span data-stu-id="fcf2e-182">_41</span></span> 

<span data-ttu-id="fcf2e-183">矩阵的第四行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-183">The value in the fourth row and first column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-184">公共单[_41](#_41)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-184">public Single [_41](#_41)</span></span>

#### <span data-ttu-id="fcf2e-185">_42</span><span class="sxs-lookup"><span data-stu-id="fcf2e-185">_42</span></span> 

<span data-ttu-id="fcf2e-186">矩阵的第四行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-186">The value in the fourth row and second column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-187">公共单[_42](#_42)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-187">public Single [_42](#_42)</span></span>

#### <span data-ttu-id="fcf2e-188">_43</span><span class="sxs-lookup"><span data-stu-id="fcf2e-188">_43</span></span> 

<span data-ttu-id="fcf2e-189">矩阵的第四行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-189">The value in the fourth row and third column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-190">公共单[_43](#_43)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-190">public Single [_43](#_43)</span></span>

#### <span data-ttu-id="fcf2e-191">_44</span><span class="sxs-lookup"><span data-stu-id="fcf2e-191">_44</span></span> 

<span data-ttu-id="fcf2e-192">矩阵的第四行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="fcf2e-192">The value in the fourth row and fourth column of the matrix.</span></span>

> <span data-ttu-id="fcf2e-193">公共单[_44](#_44)</span><span class="sxs-lookup"><span data-stu-id="fcf2e-193">public Single [_44](#_44)</span></span>

