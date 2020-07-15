---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2PhysicalKeyStatus
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: da7069fb4dad164720bb697a250a216a0bd452ad
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881198"
---
# <span data-ttu-id="70eb0-104">0.9.515-WebView2 的 CoreWebView2PhysicalKeyStatus 结构</span><span class="sxs-lookup"><span data-stu-id="70eb0-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2PhysicalKeyStatus struct</span></span> 

> [!NOTE]
> <span data-ttu-id="70eb0-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="70eb0-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="70eb0-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="70eb0-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="70eb0-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="70eb0-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="70eb0-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="70eb0-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="70eb0-109">一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。</span><span class="sxs-lookup"><span data-stu-id="70eb0-109">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

## <span data-ttu-id="70eb0-110">摘要</span><span class="sxs-lookup"><span data-stu-id="70eb0-110">Summary</span></span>

 <span data-ttu-id="70eb0-111">成员</span><span class="sxs-lookup"><span data-stu-id="70eb0-111">Members</span></span>                        | <span data-ttu-id="70eb0-112">描述</span><span class="sxs-lookup"><span data-stu-id="70eb0-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="70eb0-113">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="70eb0-113">IsExtendedKey</span></span>](#isextendedkey) | <span data-ttu-id="70eb0-114">指示该键是否为扩展键。</span><span class="sxs-lookup"><span data-stu-id="70eb0-114">Indicates whether the key is an extended key.</span></span>
[<span data-ttu-id="70eb0-115">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="70eb0-115">IsKeyReleased</span></span>](#iskeyreleased) | <span data-ttu-id="70eb0-116">切换状态。</span><span class="sxs-lookup"><span data-stu-id="70eb0-116">The transition state.</span></span>
[<span data-ttu-id="70eb0-117">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="70eb0-117">IsMenuKeyDown</span></span>](#ismenukeydown) | <span data-ttu-id="70eb0-118">上下文代码。</span><span class="sxs-lookup"><span data-stu-id="70eb0-118">The context code.</span></span>
[<span data-ttu-id="70eb0-119">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="70eb0-119">RepeatCount</span></span>](#repeatcount) | <span data-ttu-id="70eb0-120">当前消息的重复次数。</span><span class="sxs-lookup"><span data-stu-id="70eb0-120">The repeat count for the current message.</span></span>
[<span data-ttu-id="70eb0-121">ScanCode</span><span class="sxs-lookup"><span data-stu-id="70eb0-121">ScanCode</span></span>](#scancode) | <span data-ttu-id="70eb0-122">扫描代码。</span><span class="sxs-lookup"><span data-stu-id="70eb0-122">The scan code.</span></span>
[<span data-ttu-id="70eb0-123">WasKeyDown</span><span class="sxs-lookup"><span data-stu-id="70eb0-123">WasKeyDown</span></span>](#waskeydown) | <span data-ttu-id="70eb0-124">以前的键状态。</span><span class="sxs-lookup"><span data-stu-id="70eb0-124">The previous key state.</span></span>

<span data-ttu-id="70eb0-125">有关详细信息，请参阅 WM_KEYDOWN 的文档 [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。</span><span class="sxs-lookup"><span data-stu-id="70eb0-125">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown).</span></span>

## <span data-ttu-id="70eb0-126">成员</span><span class="sxs-lookup"><span data-stu-id="70eb0-126">Members</span></span>

#### <span data-ttu-id="70eb0-127">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="70eb0-127">IsExtendedKey</span></span> 

<span data-ttu-id="70eb0-128">指示该键是否为扩展键。</span><span class="sxs-lookup"><span data-stu-id="70eb0-128">Indicates whether the key is an extended key.</span></span>

> <span data-ttu-id="70eb0-129">公共 int [IsExtendedKey](#isextendedkey)</span><span class="sxs-lookup"><span data-stu-id="70eb0-129">public int [IsExtendedKey](#isextendedkey)</span></span>

#### <span data-ttu-id="70eb0-130">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="70eb0-130">IsKeyReleased</span></span> 

<span data-ttu-id="70eb0-131">切换状态。</span><span class="sxs-lookup"><span data-stu-id="70eb0-131">The transition state.</span></span>

> <span data-ttu-id="70eb0-132">公共 int [IsKeyReleased](#iskeyreleased)</span><span class="sxs-lookup"><span data-stu-id="70eb0-132">public int [IsKeyReleased](#iskeyreleased)</span></span>

#### <span data-ttu-id="70eb0-133">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="70eb0-133">IsMenuKeyDown</span></span> 

<span data-ttu-id="70eb0-134">上下文代码。</span><span class="sxs-lookup"><span data-stu-id="70eb0-134">The context code.</span></span>

> <span data-ttu-id="70eb0-135">公共 int [IsMenuKeyDown](#ismenukeydown)</span><span class="sxs-lookup"><span data-stu-id="70eb0-135">public int [IsMenuKeyDown](#ismenukeydown)</span></span>

#### <span data-ttu-id="70eb0-136">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="70eb0-136">RepeatCount</span></span> 

<span data-ttu-id="70eb0-137">当前消息的重复次数。</span><span class="sxs-lookup"><span data-stu-id="70eb0-137">The repeat count for the current message.</span></span>

> <span data-ttu-id="70eb0-138">公共 uint [RepeatCount](#repeatcount)</span><span class="sxs-lookup"><span data-stu-id="70eb0-138">public uint [RepeatCount](#repeatcount)</span></span>

#### <span data-ttu-id="70eb0-139">ScanCode</span><span class="sxs-lookup"><span data-stu-id="70eb0-139">ScanCode</span></span> 

<span data-ttu-id="70eb0-140">扫描代码。</span><span class="sxs-lookup"><span data-stu-id="70eb0-140">The scan code.</span></span>

> <span data-ttu-id="70eb0-141">公共 uint [ScanCode](#scancode)</span><span class="sxs-lookup"><span data-stu-id="70eb0-141">public uint [ScanCode](#scancode)</span></span>

#### <span data-ttu-id="70eb0-142">WasKeyDown</span><span class="sxs-lookup"><span data-stu-id="70eb0-142">WasKeyDown</span></span> 

<span data-ttu-id="70eb0-143">以前的键状态。</span><span class="sxs-lookup"><span data-stu-id="70eb0-143">The previous key state.</span></span>

> <span data-ttu-id="70eb0-144">公共 int [WasKeyDown](#waskeydown)</span><span class="sxs-lookup"><span data-stu-id="70eb0-144">public int [WasKeyDown](#waskeydown)</span></span>

