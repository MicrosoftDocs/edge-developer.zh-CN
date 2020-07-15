---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b7071a312ce1fa3ca006a6805a1f712a51d0dab0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879112"
---
# <span data-ttu-id="e7ce2-104">0.9.515-WebView2 的 CoreWebView2ScriptDialogOpeningEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="e7ce2-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="e7ce2-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="e7ce2-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="e7ce2-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="e7ce2-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e7ce2-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e7ce2-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e7ce2-109">ScriptDialogOpening 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-109">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="e7ce2-110">摘要</span><span class="sxs-lookup"><span data-stu-id="e7ce2-110">Summary</span></span>

 <span data-ttu-id="e7ce2-111">成员</span><span class="sxs-lookup"><span data-stu-id="e7ce2-111">Members</span></span>                        | <span data-ttu-id="e7ce2-112">描述</span><span class="sxs-lookup"><span data-stu-id="e7ce2-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e7ce2-113">DefaultText</span><span class="sxs-lookup"><span data-stu-id="e7ce2-113">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="e7ce2-114">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-114">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="e7ce2-115">Kind</span><span class="sxs-lookup"><span data-stu-id="e7ce2-115">Kind</span></span>](#kind) | <span data-ttu-id="e7ce2-116">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-116">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="e7ce2-117">消息</span><span class="sxs-lookup"><span data-stu-id="e7ce2-117">Message</span></span>](#message) | <span data-ttu-id="e7ce2-118">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-118">The message of the dialog box.</span></span>
[<span data-ttu-id="e7ce2-119">ResultText</span><span class="sxs-lookup"><span data-stu-id="e7ce2-119">ResultText</span></span>](#resulttext) | <span data-ttu-id="e7ce2-120">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="e7ce2-121">Uri</span><span class="sxs-lookup"><span data-stu-id="e7ce2-121">Uri</span></span>](#uri) | <span data-ttu-id="e7ce2-122">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-122">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="e7ce2-123">接受</span><span class="sxs-lookup"><span data-stu-id="e7ce2-123">Accept</span></span>](#accept) | <span data-ttu-id="e7ce2-124">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-124">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="e7ce2-125">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="e7ce2-125">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="e7ce2-126">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-126">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="e7ce2-127">成员</span><span class="sxs-lookup"><span data-stu-id="e7ce2-127">Members</span></span>

#### <span data-ttu-id="e7ce2-128">DefaultText</span><span class="sxs-lookup"><span data-stu-id="e7ce2-128">DefaultText</span></span> 

<span data-ttu-id="e7ce2-129">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-129">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="e7ce2-130">公共字符串[DefaultText](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="e7ce2-130">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="e7ce2-131">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-131">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="e7ce2-132">Kind</span><span class="sxs-lookup"><span data-stu-id="e7ce2-132">Kind</span></span> 

<span data-ttu-id="e7ce2-133">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-133">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="e7ce2-134">公共 CoreWebView2ScriptDialogKind[种类](#kind)</span><span class="sxs-lookup"><span data-stu-id="e7ce2-134">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="e7ce2-135">接受、确认、提示或 beforeunload。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-135">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="e7ce2-136">消息</span><span class="sxs-lookup"><span data-stu-id="e7ce2-136">Message</span></span> 

<span data-ttu-id="e7ce2-137">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-137">The message of the dialog box.</span></span>

> <span data-ttu-id="e7ce2-138">公共字符串[消息](#message)</span><span class="sxs-lookup"><span data-stu-id="e7ce2-138">public string [Message](#message)</span></span>

<span data-ttu-id="e7ce2-139">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-139">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="e7ce2-140">ResultText</span><span class="sxs-lookup"><span data-stu-id="e7ce2-140">ResultText</span></span> 

<span data-ttu-id="e7ce2-141">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-141">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="e7ce2-142">公共字符串[ResultText](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="e7ce2-142">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="e7ce2-143">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-143">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="e7ce2-144">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-144">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="e7ce2-145">Uri</span><span class="sxs-lookup"><span data-stu-id="e7ce2-145">Uri</span></span> 

<span data-ttu-id="e7ce2-146">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-146">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="e7ce2-147">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="e7ce2-147">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="e7ce2-148">接受</span><span class="sxs-lookup"><span data-stu-id="e7ce2-148">Accept</span></span> 

<span data-ttu-id="e7ce2-149">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-149">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="e7ce2-150">公共 void [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="e7ce2-150">public void [Accept](#accept)()</span></span>

<span data-ttu-id="e7ce2-151">从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-151">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="e7ce2-152">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-152">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="e7ce2-153">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="e7ce2-153">GetDeferral</span></span> 

<span data-ttu-id="e7ce2-154">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-154">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="e7ce2-155">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="e7ce2-155">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="e7ce2-156">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="e7ce2-156">You can use this to complete the event at a later time.</span></span>

