---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2Matrix4x4 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: e8048bd51d717904ce2d220eb63db8de5d155885
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011631"
---
# <span data-ttu-id="e504e-104">CoreWebView2Matrix4x4 结构的 WebView2</span><span class="sxs-lookup"><span data-stu-id="e504e-104">Microsoft.Web.WebView2.Core.CoreWebView2Matrix4x4 struct</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="e504e-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="e504e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e504e-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e504e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e504e-107">此转换用于在调用 CreateCoreWebView2PointerInfoFromPointerId 时计算正确的坐标。</span><span class="sxs-lookup"><span data-stu-id="e504e-107">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span>

## <span data-ttu-id="e504e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e504e-108">Summary</span></span>

 <span data-ttu-id="e504e-109">成员</span><span class="sxs-lookup"><span data-stu-id="e504e-109">Members</span></span>                        | <span data-ttu-id="e504e-110">描述</span><span class="sxs-lookup"><span data-stu-id="e504e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e504e-111">_11</span><span class="sxs-lookup"><span data-stu-id="e504e-111">_11</span></span>](#_11) | <span data-ttu-id="e504e-112">矩阵的第一行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-112">The value in the first row and first column of the matrix.</span></span>
[<span data-ttu-id="e504e-113">_12</span><span class="sxs-lookup"><span data-stu-id="e504e-113">_12</span></span>](#_12) | <span data-ttu-id="e504e-114">矩阵的第一行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-114">The value in the first row and second column of the matrix.</span></span>
[<span data-ttu-id="e504e-115">_13</span><span class="sxs-lookup"><span data-stu-id="e504e-115">_13</span></span>](#_13) | <span data-ttu-id="e504e-116">矩阵的第一行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-116">The value in the first row and third column of the matrix.</span></span>
[<span data-ttu-id="e504e-117">_14</span><span class="sxs-lookup"><span data-stu-id="e504e-117">_14</span></span>](#_14) | <span data-ttu-id="e504e-118">矩阵的第一行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-118">The value in the first row and fourth column of the matrix.</span></span>
[<span data-ttu-id="e504e-119">_21</span><span class="sxs-lookup"><span data-stu-id="e504e-119">_21</span></span>](#_21) | <span data-ttu-id="e504e-120">矩阵的第二行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-120">The value in the second row and first column of the matrix.</span></span>
[<span data-ttu-id="e504e-121">_22</span><span class="sxs-lookup"><span data-stu-id="e504e-121">_22</span></span>](#_22) | <span data-ttu-id="e504e-122">矩阵的第二行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-122">The value in the second row and second column of the matrix.</span></span>
[<span data-ttu-id="e504e-123">_23</span><span class="sxs-lookup"><span data-stu-id="e504e-123">_23</span></span>](#_23) | <span data-ttu-id="e504e-124">矩阵的第二行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-124">The value in the second row and third column of the matrix.</span></span>
[<span data-ttu-id="e504e-125">_24</span><span class="sxs-lookup"><span data-stu-id="e504e-125">_24</span></span>](#_24) | <span data-ttu-id="e504e-126">矩阵的第二行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-126">The value in the second row and fourth column of the matrix.</span></span>
[<span data-ttu-id="e504e-127">_31</span><span class="sxs-lookup"><span data-stu-id="e504e-127">_31</span></span>](#_31) | <span data-ttu-id="e504e-128">矩阵的第三行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-128">The value in the third row and first column of the matrix.</span></span>
[<span data-ttu-id="e504e-129">_32</span><span class="sxs-lookup"><span data-stu-id="e504e-129">_32</span></span>](#_32) | <span data-ttu-id="e504e-130">矩阵的第三行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-130">The value in the third row and second column of the matrix.</span></span>
[<span data-ttu-id="e504e-131">_33</span><span class="sxs-lookup"><span data-stu-id="e504e-131">_33</span></span>](#_33) | <span data-ttu-id="e504e-132">矩阵的第三行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-132">The value in the third row and third column of the matrix.</span></span>
[<span data-ttu-id="e504e-133">_34</span><span class="sxs-lookup"><span data-stu-id="e504e-133">_34</span></span>](#_34) | <span data-ttu-id="e504e-134">矩阵的第三行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-134">The value in the third row and fourth column of the matrix.</span></span>
[<span data-ttu-id="e504e-135">_41</span><span class="sxs-lookup"><span data-stu-id="e504e-135">_41</span></span>](#_41) | <span data-ttu-id="e504e-136">矩阵的第四行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-136">The value in the fourth row and first column of the matrix.</span></span>
[<span data-ttu-id="e504e-137">_42</span><span class="sxs-lookup"><span data-stu-id="e504e-137">_42</span></span>](#_42) | <span data-ttu-id="e504e-138">矩阵的第四行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-138">The value in the fourth row and second column of the matrix.</span></span>
[<span data-ttu-id="e504e-139">_43</span><span class="sxs-lookup"><span data-stu-id="e504e-139">_43</span></span>](#_43) | <span data-ttu-id="e504e-140">矩阵的第四行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-140">The value in the fourth row and third column of the matrix.</span></span>
[<span data-ttu-id="e504e-141">_44</span><span class="sxs-lookup"><span data-stu-id="e504e-141">_44</span></span>](#_44) | <span data-ttu-id="e504e-142">矩阵的第四行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-142">The value in the fourth row and fourth column of the matrix.</span></span>

<span data-ttu-id="e504e-143">这等效于 D2D1_MATRIX_4X4_F。</span><span class="sxs-lookup"><span data-stu-id="e504e-143">This is equivalent to a D2D1_MATRIX_4X4_F.</span></span>

## <span data-ttu-id="e504e-144">成员</span><span class="sxs-lookup"><span data-stu-id="e504e-144">Members</span></span>

#### <span data-ttu-id="e504e-145">_11</span><span class="sxs-lookup"><span data-stu-id="e504e-145">_11</span></span> 

<span data-ttu-id="e504e-146">矩阵的第一行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-146">The value in the first row and first column of the matrix.</span></span>

> <span data-ttu-id="e504e-147">公共单 [_11](#_11)</span><span class="sxs-lookup"><span data-stu-id="e504e-147">public Single [_11](#_11)</span></span>

#### <span data-ttu-id="e504e-148">_12</span><span class="sxs-lookup"><span data-stu-id="e504e-148">_12</span></span> 

<span data-ttu-id="e504e-149">矩阵的第一行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-149">The value in the first row and second column of the matrix.</span></span>

> <span data-ttu-id="e504e-150">公共单 [_12](#_12)</span><span class="sxs-lookup"><span data-stu-id="e504e-150">public Single [_12](#_12)</span></span>

#### <span data-ttu-id="e504e-151">_13</span><span class="sxs-lookup"><span data-stu-id="e504e-151">_13</span></span> 

<span data-ttu-id="e504e-152">矩阵的第一行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-152">The value in the first row and third column of the matrix.</span></span>

> <span data-ttu-id="e504e-153">公共单 [_13](#_13)</span><span class="sxs-lookup"><span data-stu-id="e504e-153">public Single [_13](#_13)</span></span>

#### <span data-ttu-id="e504e-154">_14</span><span class="sxs-lookup"><span data-stu-id="e504e-154">_14</span></span> 

<span data-ttu-id="e504e-155">矩阵的第一行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-155">The value in the first row and fourth column of the matrix.</span></span>

> <span data-ttu-id="e504e-156">公共单 [_14](#_14)</span><span class="sxs-lookup"><span data-stu-id="e504e-156">public Single [_14](#_14)</span></span>

#### <span data-ttu-id="e504e-157">_21</span><span class="sxs-lookup"><span data-stu-id="e504e-157">_21</span></span> 

<span data-ttu-id="e504e-158">矩阵的第二行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-158">The value in the second row and first column of the matrix.</span></span>

> <span data-ttu-id="e504e-159">公共单 [_21](#_21)</span><span class="sxs-lookup"><span data-stu-id="e504e-159">public Single [_21](#_21)</span></span>

#### <span data-ttu-id="e504e-160">_22</span><span class="sxs-lookup"><span data-stu-id="e504e-160">_22</span></span> 

<span data-ttu-id="e504e-161">矩阵的第二行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-161">The value in the second row and second column of the matrix.</span></span>

> <span data-ttu-id="e504e-162">公共单 [_22](#_22)</span><span class="sxs-lookup"><span data-stu-id="e504e-162">public Single [_22](#_22)</span></span>

#### <span data-ttu-id="e504e-163">_23</span><span class="sxs-lookup"><span data-stu-id="e504e-163">_23</span></span> 

<span data-ttu-id="e504e-164">矩阵的第二行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-164">The value in the second row and third column of the matrix.</span></span>

> <span data-ttu-id="e504e-165">公共单 [_23](#_23)</span><span class="sxs-lookup"><span data-stu-id="e504e-165">public Single [_23](#_23)</span></span>

#### <span data-ttu-id="e504e-166">_24</span><span class="sxs-lookup"><span data-stu-id="e504e-166">_24</span></span> 

<span data-ttu-id="e504e-167">矩阵的第二行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-167">The value in the second row and fourth column of the matrix.</span></span>

> <span data-ttu-id="e504e-168">公共单 [_24](#_24)</span><span class="sxs-lookup"><span data-stu-id="e504e-168">public Single [_24](#_24)</span></span>

#### <span data-ttu-id="e504e-169">_31</span><span class="sxs-lookup"><span data-stu-id="e504e-169">_31</span></span> 

<span data-ttu-id="e504e-170">矩阵的第三行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-170">The value in the third row and first column of the matrix.</span></span>

> <span data-ttu-id="e504e-171">公共单 [_31](#_31)</span><span class="sxs-lookup"><span data-stu-id="e504e-171">public Single [_31](#_31)</span></span>

#### <span data-ttu-id="e504e-172">_32</span><span class="sxs-lookup"><span data-stu-id="e504e-172">_32</span></span> 

<span data-ttu-id="e504e-173">矩阵的第三行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-173">The value in the third row and second column of the matrix.</span></span>

> <span data-ttu-id="e504e-174">公共单 [_32](#_32)</span><span class="sxs-lookup"><span data-stu-id="e504e-174">public Single [_32](#_32)</span></span>

#### <span data-ttu-id="e504e-175">_33</span><span class="sxs-lookup"><span data-stu-id="e504e-175">_33</span></span> 

<span data-ttu-id="e504e-176">矩阵的第三行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-176">The value in the third row and third column of the matrix.</span></span>

> <span data-ttu-id="e504e-177">公共单 [_33](#_33)</span><span class="sxs-lookup"><span data-stu-id="e504e-177">public Single [_33](#_33)</span></span>

#### <span data-ttu-id="e504e-178">_34</span><span class="sxs-lookup"><span data-stu-id="e504e-178">_34</span></span> 

<span data-ttu-id="e504e-179">矩阵的第三行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-179">The value in the third row and fourth column of the matrix.</span></span>

> <span data-ttu-id="e504e-180">公共单 [_34](#_34)</span><span class="sxs-lookup"><span data-stu-id="e504e-180">public Single [_34](#_34)</span></span>

#### <span data-ttu-id="e504e-181">_41</span><span class="sxs-lookup"><span data-stu-id="e504e-181">_41</span></span> 

<span data-ttu-id="e504e-182">矩阵的第四行和第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-182">The value in the fourth row and first column of the matrix.</span></span>

> <span data-ttu-id="e504e-183">公共单 [_41](#_41)</span><span class="sxs-lookup"><span data-stu-id="e504e-183">public Single [_41](#_41)</span></span>

#### <span data-ttu-id="e504e-184">_42</span><span class="sxs-lookup"><span data-stu-id="e504e-184">_42</span></span> 

<span data-ttu-id="e504e-185">矩阵的第四行和第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-185">The value in the fourth row and second column of the matrix.</span></span>

> <span data-ttu-id="e504e-186">公共单 [_42](#_42)</span><span class="sxs-lookup"><span data-stu-id="e504e-186">public Single [_42](#_42)</span></span>

#### <span data-ttu-id="e504e-187">_43</span><span class="sxs-lookup"><span data-stu-id="e504e-187">_43</span></span> 

<span data-ttu-id="e504e-188">矩阵的第四行和第三列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-188">The value in the fourth row and third column of the matrix.</span></span>

> <span data-ttu-id="e504e-189">公共单 [_43](#_43)</span><span class="sxs-lookup"><span data-stu-id="e504e-189">public Single [_43](#_43)</span></span>

#### <span data-ttu-id="e504e-190">_44</span><span class="sxs-lookup"><span data-stu-id="e504e-190">_44</span></span> 

<span data-ttu-id="e504e-191">矩阵的第四行和第四列中的值。</span><span class="sxs-lookup"><span data-stu-id="e504e-191">The value in the fourth row and fourth column of the matrix.</span></span>

> <span data-ttu-id="e504e-192">公共单 [_44](#_44)</span><span class="sxs-lookup"><span data-stu-id="e504e-192">public Single [_44](#_44)</span></span>

