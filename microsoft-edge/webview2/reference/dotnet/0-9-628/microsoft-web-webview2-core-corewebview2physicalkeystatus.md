---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2PhysicalKeyStatus 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: adecd3b23369935b1dc5729e894eaf1c295a06d3
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011668"
---
# <span data-ttu-id="f5b59-104">CoreWebView2PhysicalKeyStatus 结构的 WebView2</span><span class="sxs-lookup"><span data-stu-id="f5b59-104">Microsoft.Web.WebView2.Core.CoreWebView2PhysicalKeyStatus struct</span></span> 

<span data-ttu-id="f5b59-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="f5b59-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f5b59-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="f5b59-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f5b59-107">一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。</span><span class="sxs-lookup"><span data-stu-id="f5b59-107">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

## <span data-ttu-id="f5b59-108">摘要</span><span class="sxs-lookup"><span data-stu-id="f5b59-108">Summary</span></span>

 <span data-ttu-id="f5b59-109">成员</span><span class="sxs-lookup"><span data-stu-id="f5b59-109">Members</span></span>                        | <span data-ttu-id="f5b59-110">描述</span><span class="sxs-lookup"><span data-stu-id="f5b59-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f5b59-111">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="f5b59-111">IsExtendedKey</span></span>](#isextendedkey) | <span data-ttu-id="f5b59-112">指示该键是否为扩展键。</span><span class="sxs-lookup"><span data-stu-id="f5b59-112">Indicates whether the key is an extended key.</span></span>
[<span data-ttu-id="f5b59-113">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="f5b59-113">IsKeyReleased</span></span>](#iskeyreleased) | <span data-ttu-id="f5b59-114">切换状态。</span><span class="sxs-lookup"><span data-stu-id="f5b59-114">The transition state.</span></span>
[<span data-ttu-id="f5b59-115">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="f5b59-115">IsMenuKeyDown</span></span>](#ismenukeydown) | <span data-ttu-id="f5b59-116">上下文代码。</span><span class="sxs-lookup"><span data-stu-id="f5b59-116">The context code.</span></span>
[<span data-ttu-id="f5b59-117">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="f5b59-117">RepeatCount</span></span>](#repeatcount) | <span data-ttu-id="f5b59-118">当前消息的重复次数。</span><span class="sxs-lookup"><span data-stu-id="f5b59-118">The repeat count for the current message.</span></span>
[<span data-ttu-id="f5b59-119">ScanCode</span><span class="sxs-lookup"><span data-stu-id="f5b59-119">ScanCode</span></span>](#scancode) | <span data-ttu-id="f5b59-120">扫描代码。</span><span class="sxs-lookup"><span data-stu-id="f5b59-120">The scan code.</span></span>
[<span data-ttu-id="f5b59-121">WasKeyDown</span><span class="sxs-lookup"><span data-stu-id="f5b59-121">WasKeyDown</span></span>](#waskeydown) | <span data-ttu-id="f5b59-122">以前的键状态。</span><span class="sxs-lookup"><span data-stu-id="f5b59-122">The previous key state.</span></span>

<span data-ttu-id="f5b59-123">有关详细信息，请参阅 WM_KEYDOWN 的文档 [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。</span><span class="sxs-lookup"><span data-stu-id="f5b59-123">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown).</span></span>

## <span data-ttu-id="f5b59-124">成员</span><span class="sxs-lookup"><span data-stu-id="f5b59-124">Members</span></span>

#### <span data-ttu-id="f5b59-125">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="f5b59-125">IsExtendedKey</span></span> 

<span data-ttu-id="f5b59-126">指示该键是否为扩展键。</span><span class="sxs-lookup"><span data-stu-id="f5b59-126">Indicates whether the key is an extended key.</span></span>

> <span data-ttu-id="f5b59-127">公共 int [IsExtendedKey](#isextendedkey)</span><span class="sxs-lookup"><span data-stu-id="f5b59-127">public int [IsExtendedKey](#isextendedkey)</span></span>

#### <span data-ttu-id="f5b59-128">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="f5b59-128">IsKeyReleased</span></span> 

<span data-ttu-id="f5b59-129">切换状态。</span><span class="sxs-lookup"><span data-stu-id="f5b59-129">The transition state.</span></span>

> <span data-ttu-id="f5b59-130">公共 int [IsKeyReleased](#iskeyreleased)</span><span class="sxs-lookup"><span data-stu-id="f5b59-130">public int [IsKeyReleased](#iskeyreleased)</span></span>

#### <span data-ttu-id="f5b59-131">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="f5b59-131">IsMenuKeyDown</span></span> 

<span data-ttu-id="f5b59-132">上下文代码。</span><span class="sxs-lookup"><span data-stu-id="f5b59-132">The context code.</span></span>

> <span data-ttu-id="f5b59-133">公共 int [IsMenuKeyDown](#ismenukeydown)</span><span class="sxs-lookup"><span data-stu-id="f5b59-133">public int [IsMenuKeyDown](#ismenukeydown)</span></span>

#### <span data-ttu-id="f5b59-134">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="f5b59-134">RepeatCount</span></span> 

<span data-ttu-id="f5b59-135">当前消息的重复次数。</span><span class="sxs-lookup"><span data-stu-id="f5b59-135">The repeat count for the current message.</span></span>

> <span data-ttu-id="f5b59-136">公共 uint [RepeatCount](#repeatcount)</span><span class="sxs-lookup"><span data-stu-id="f5b59-136">public uint [RepeatCount](#repeatcount)</span></span>

#### <span data-ttu-id="f5b59-137">ScanCode</span><span class="sxs-lookup"><span data-stu-id="f5b59-137">ScanCode</span></span> 

<span data-ttu-id="f5b59-138">扫描代码。</span><span class="sxs-lookup"><span data-stu-id="f5b59-138">The scan code.</span></span>

> <span data-ttu-id="f5b59-139">公共 uint [ScanCode](#scancode)</span><span class="sxs-lookup"><span data-stu-id="f5b59-139">public uint [ScanCode](#scancode)</span></span>

#### <span data-ttu-id="f5b59-140">WasKeyDown</span><span class="sxs-lookup"><span data-stu-id="f5b59-140">WasKeyDown</span></span> 

<span data-ttu-id="f5b59-141">以前的键状态。</span><span class="sxs-lookup"><span data-stu-id="f5b59-141">The previous key state.</span></span>

> <span data-ttu-id="f5b59-142">公共 int [WasKeyDown](#waskeydown)</span><span class="sxs-lookup"><span data-stu-id="f5b59-142">public int [WasKeyDown](#waskeydown)</span></span>
