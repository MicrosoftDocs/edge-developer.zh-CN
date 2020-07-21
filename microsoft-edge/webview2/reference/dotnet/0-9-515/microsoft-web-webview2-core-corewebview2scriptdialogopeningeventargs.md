---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 4e7cd20b982d829be6d304eea1f3f60759cc503f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884853"
---
# <span data-ttu-id="2bc1b-104">0.9.515-WebView2 的 CoreWebView2ScriptDialogOpeningEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="2bc1b-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="2bc1b-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="2bc1b-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="2bc1b-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="2bc1b-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="2bc1b-107">ScriptDialogOpening 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="2bc1b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="2bc1b-108">Summary</span></span>

 <span data-ttu-id="2bc1b-109">成员</span><span class="sxs-lookup"><span data-stu-id="2bc1b-109">Members</span></span>                        | <span data-ttu-id="2bc1b-110">描述</span><span class="sxs-lookup"><span data-stu-id="2bc1b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2bc1b-111">DefaultText</span><span class="sxs-lookup"><span data-stu-id="2bc1b-111">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="2bc1b-112">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-112">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="2bc1b-113">Kind</span><span class="sxs-lookup"><span data-stu-id="2bc1b-113">Kind</span></span>](#kind) | <span data-ttu-id="2bc1b-114">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="2bc1b-115">消息</span><span class="sxs-lookup"><span data-stu-id="2bc1b-115">Message</span></span>](#message) | <span data-ttu-id="2bc1b-116">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-116">The message of the dialog box.</span></span>
[<span data-ttu-id="2bc1b-117">ResultText</span><span class="sxs-lookup"><span data-stu-id="2bc1b-117">ResultText</span></span>](#resulttext) | <span data-ttu-id="2bc1b-118">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-118">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="2bc1b-119">Uri</span><span class="sxs-lookup"><span data-stu-id="2bc1b-119">Uri</span></span>](#uri) | <span data-ttu-id="2bc1b-120">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-120">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="2bc1b-121">接受</span><span class="sxs-lookup"><span data-stu-id="2bc1b-121">Accept</span></span>](#accept) | <span data-ttu-id="2bc1b-122">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-122">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="2bc1b-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2bc1b-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="2bc1b-124">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-124">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="2bc1b-125">成员</span><span class="sxs-lookup"><span data-stu-id="2bc1b-125">Members</span></span>

#### <span data-ttu-id="2bc1b-126">DefaultText</span><span class="sxs-lookup"><span data-stu-id="2bc1b-126">DefaultText</span></span> 

<span data-ttu-id="2bc1b-127">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-127">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="2bc1b-128">公共字符串[DefaultText](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="2bc1b-128">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="2bc1b-129">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-129">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="2bc1b-130">Kind</span><span class="sxs-lookup"><span data-stu-id="2bc1b-130">Kind</span></span> 

<span data-ttu-id="2bc1b-131">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-131">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="2bc1b-132">公共 CoreWebView2ScriptDialogKind[种类](#kind)</span><span class="sxs-lookup"><span data-stu-id="2bc1b-132">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="2bc1b-133">接受、确认、提示或 beforeunload。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-133">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="2bc1b-134">消息</span><span class="sxs-lookup"><span data-stu-id="2bc1b-134">Message</span></span> 

<span data-ttu-id="2bc1b-135">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-135">The message of the dialog box.</span></span>

> <span data-ttu-id="2bc1b-136">公共字符串[消息](#message)</span><span class="sxs-lookup"><span data-stu-id="2bc1b-136">public string [Message](#message)</span></span>

<span data-ttu-id="2bc1b-137">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-137">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="2bc1b-138">ResultText</span><span class="sxs-lookup"><span data-stu-id="2bc1b-138">ResultText</span></span> 

<span data-ttu-id="2bc1b-139">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-139">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="2bc1b-140">公共字符串[ResultText](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="2bc1b-140">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="2bc1b-141">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-141">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="2bc1b-142">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-142">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="2bc1b-143">Uri</span><span class="sxs-lookup"><span data-stu-id="2bc1b-143">Uri</span></span> 

<span data-ttu-id="2bc1b-144">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-144">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="2bc1b-145">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="2bc1b-145">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="2bc1b-146">接受</span><span class="sxs-lookup"><span data-stu-id="2bc1b-146">Accept</span></span> 

<span data-ttu-id="2bc1b-147">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-147">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="2bc1b-148">公共 void [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="2bc1b-148">public void [Accept](#accept)()</span></span>

<span data-ttu-id="2bc1b-149">从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-149">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="2bc1b-150">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-150">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="2bc1b-151">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2bc1b-151">GetDeferral</span></span> 

<span data-ttu-id="2bc1b-152">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-152">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="2bc1b-153">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="2bc1b-153">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="2bc1b-154">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="2bc1b-154">You can use this to complete the event at a later time.</span></span>

