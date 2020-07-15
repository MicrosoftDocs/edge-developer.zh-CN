---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2ScriptDialogOpeningEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: cbff39e9393026f51471bdfb3189600e2d7bf109
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879693"
---
# <span data-ttu-id="87c4e-104">CoreWebView2ScriptDialogOpeningEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="87c4e-104">Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

<span data-ttu-id="87c4e-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="87c4e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="87c4e-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="87c4e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="87c4e-107">ScriptDialogOpening 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="87c4e-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="87c4e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="87c4e-108">Summary</span></span>

 <span data-ttu-id="87c4e-109">成员</span><span class="sxs-lookup"><span data-stu-id="87c4e-109">Members</span></span>                        | <span data-ttu-id="87c4e-110">描述</span><span class="sxs-lookup"><span data-stu-id="87c4e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="87c4e-111">DefaultText</span><span class="sxs-lookup"><span data-stu-id="87c4e-111">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="87c4e-112">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="87c4e-112">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="87c4e-113">Kind</span><span class="sxs-lookup"><span data-stu-id="87c4e-113">Kind</span></span>](#kind) | <span data-ttu-id="87c4e-114">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="87c4e-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="87c4e-115">消息</span><span class="sxs-lookup"><span data-stu-id="87c4e-115">Message</span></span>](#message) | <span data-ttu-id="87c4e-116">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="87c4e-116">The message of the dialog box.</span></span>
[<span data-ttu-id="87c4e-117">ResultText</span><span class="sxs-lookup"><span data-stu-id="87c4e-117">ResultText</span></span>](#resulttext) | <span data-ttu-id="87c4e-118">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="87c4e-118">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="87c4e-119">Uri</span><span class="sxs-lookup"><span data-stu-id="87c4e-119">Uri</span></span>](#uri) | <span data-ttu-id="87c4e-120">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="87c4e-120">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="87c4e-121">接受</span><span class="sxs-lookup"><span data-stu-id="87c4e-121">Accept</span></span>](#accept) | <span data-ttu-id="87c4e-122">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="87c4e-122">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="87c4e-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="87c4e-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="87c4e-124">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="87c4e-124">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="87c4e-125">成员</span><span class="sxs-lookup"><span data-stu-id="87c4e-125">Members</span></span>

#### <span data-ttu-id="87c4e-126">DefaultText</span><span class="sxs-lookup"><span data-stu-id="87c4e-126">DefaultText</span></span> 

<span data-ttu-id="87c4e-127">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="87c4e-127">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="87c4e-128">公共字符串[DefaultText](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="87c4e-128">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="87c4e-129">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="87c4e-129">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="87c4e-130">Kind</span><span class="sxs-lookup"><span data-stu-id="87c4e-130">Kind</span></span> 

<span data-ttu-id="87c4e-131">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="87c4e-131">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="87c4e-132">公共 CoreWebView2ScriptDialogKind[种类](#kind)</span><span class="sxs-lookup"><span data-stu-id="87c4e-132">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="87c4e-133">接受、确认、提示或 beforeunload。</span><span class="sxs-lookup"><span data-stu-id="87c4e-133">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="87c4e-134">消息</span><span class="sxs-lookup"><span data-stu-id="87c4e-134">Message</span></span> 

<span data-ttu-id="87c4e-135">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="87c4e-135">The message of the dialog box.</span></span>

> <span data-ttu-id="87c4e-136">公共字符串[消息](#message)</span><span class="sxs-lookup"><span data-stu-id="87c4e-136">public string [Message](#message)</span></span>

<span data-ttu-id="87c4e-137">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。</span><span class="sxs-lookup"><span data-stu-id="87c4e-137">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="87c4e-138">ResultText</span><span class="sxs-lookup"><span data-stu-id="87c4e-138">ResultText</span></span> 

<span data-ttu-id="87c4e-139">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="87c4e-139">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="87c4e-140">公共字符串[ResultText](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="87c4e-140">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="87c4e-141">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="87c4e-141">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="87c4e-142">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="87c4e-142">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="87c4e-143">Uri</span><span class="sxs-lookup"><span data-stu-id="87c4e-143">Uri</span></span> 

<span data-ttu-id="87c4e-144">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="87c4e-144">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="87c4e-145">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="87c4e-145">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="87c4e-146">接受</span><span class="sxs-lookup"><span data-stu-id="87c4e-146">Accept</span></span> 

<span data-ttu-id="87c4e-147">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="87c4e-147">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="87c4e-148">公共 void [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="87c4e-148">public void [Accept](#accept)()</span></span>

<span data-ttu-id="87c4e-149">从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。</span><span class="sxs-lookup"><span data-stu-id="87c4e-149">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="87c4e-150">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="87c4e-150">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="87c4e-151">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="87c4e-151">GetDeferral</span></span> 

<span data-ttu-id="87c4e-152">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="87c4e-152">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="87c4e-153">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="87c4e-153">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="87c4e-154">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="87c4e-154">You can use this to complete the event at a later time.</span></span>

