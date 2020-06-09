---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1359e9472455acf2949cc329de4280ad970a3b68
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697306"
---
# <span data-ttu-id="d8633-104">CoreWebView2ScriptDialogOpeningEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="d8633-104">Microsoft.Web.WebView2.Core.CoreWebView2ScriptDialogOpeningEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="d8633-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d8633-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d8633-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d8633-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="d8633-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="d8633-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d8633-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="d8633-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d8633-109">ScriptDialogOpening 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d8633-109">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="d8633-110">摘要</span><span class="sxs-lookup"><span data-stu-id="d8633-110">Summary</span></span>

 <span data-ttu-id="d8633-111">成员</span><span class="sxs-lookup"><span data-stu-id="d8633-111">Members</span></span>                        | <span data-ttu-id="d8633-112">描述</span><span class="sxs-lookup"><span data-stu-id="d8633-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d8633-113">DefaultText</span><span class="sxs-lookup"><span data-stu-id="d8633-113">DefaultText</span></span>](#defaulttext) | <span data-ttu-id="d8633-114">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="d8633-114">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="d8633-115">Kind</span><span class="sxs-lookup"><span data-stu-id="d8633-115">Kind</span></span>](#kind) | <span data-ttu-id="d8633-116">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="d8633-116">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="d8633-117">消息</span><span class="sxs-lookup"><span data-stu-id="d8633-117">Message</span></span>](#message) | <span data-ttu-id="d8633-118">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="d8633-118">The message of the dialog box.</span></span>
[<span data-ttu-id="d8633-119">ResultText</span><span class="sxs-lookup"><span data-stu-id="d8633-119">ResultText</span></span>](#resulttext) | <span data-ttu-id="d8633-120">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="d8633-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="d8633-121">Uri</span><span class="sxs-lookup"><span data-stu-id="d8633-121">Uri</span></span>](#uri) | <span data-ttu-id="d8633-122">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="d8633-122">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="d8633-123">接受</span><span class="sxs-lookup"><span data-stu-id="d8633-123">Accept</span></span>](#accept) | <span data-ttu-id="d8633-124">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="d8633-124">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="d8633-125">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d8633-125">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="d8633-126">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="d8633-126">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="d8633-127">成员</span><span class="sxs-lookup"><span data-stu-id="d8633-127">Members</span></span>

#### <span data-ttu-id="d8633-128">DefaultText</span><span class="sxs-lookup"><span data-stu-id="d8633-128">DefaultText</span></span> 

<span data-ttu-id="d8633-129">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="d8633-129">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="d8633-130">公共字符串[DefaultText](#defaulttext)</span><span class="sxs-lookup"><span data-stu-id="d8633-130">public string [DefaultText](#defaulttext)</span></span>

<span data-ttu-id="d8633-131">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="d8633-131">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="d8633-132">Kind</span><span class="sxs-lookup"><span data-stu-id="d8633-132">Kind</span></span> 

<span data-ttu-id="d8633-133">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="d8633-133">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="d8633-134">公共 CoreWebView2ScriptDialogKind[种类](#kind)</span><span class="sxs-lookup"><span data-stu-id="d8633-134">public CoreWebView2ScriptDialogKind [Kind](#kind)</span></span>

<span data-ttu-id="d8633-135">接受、确认、提示或 beforeunload。</span><span class="sxs-lookup"><span data-stu-id="d8633-135">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="d8633-136">消息</span><span class="sxs-lookup"><span data-stu-id="d8633-136">Message</span></span> 

<span data-ttu-id="d8633-137">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="d8633-137">The message of the dialog box.</span></span>

> <span data-ttu-id="d8633-138">公共字符串[消息](#message)</span><span class="sxs-lookup"><span data-stu-id="d8633-138">public string [Message](#message)</span></span>

<span data-ttu-id="d8633-139">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。</span><span class="sxs-lookup"><span data-stu-id="d8633-139">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="d8633-140">ResultText</span><span class="sxs-lookup"><span data-stu-id="d8633-140">ResultText</span></span> 

<span data-ttu-id="d8633-141">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="d8633-141">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="d8633-142">公共字符串[ResultText](#resulttext)</span><span class="sxs-lookup"><span data-stu-id="d8633-142">public string [ResultText](#resulttext)</span></span>

<span data-ttu-id="d8633-143">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="d8633-143">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="d8633-144">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="d8633-144">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="d8633-145">Uri</span><span class="sxs-lookup"><span data-stu-id="d8633-145">Uri</span></span> 

<span data-ttu-id="d8633-146">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="d8633-146">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="d8633-147">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="d8633-147">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="d8633-148">接受</span><span class="sxs-lookup"><span data-stu-id="d8633-148">Accept</span></span> 

<span data-ttu-id="d8633-149">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="d8633-149">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="d8633-150">公共 void [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="d8633-150">public void [Accept](#accept)()</span></span>

<span data-ttu-id="d8633-151">从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。</span><span class="sxs-lookup"><span data-stu-id="d8633-151">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="d8633-152">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="d8633-152">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="d8633-153">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d8633-153">GetDeferral</span></span> 

<span data-ttu-id="d8633-154">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="d8633-154">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="d8633-155">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="d8633-155">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="d8633-156">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="d8633-156">You can use this to complete the event at a later time.</span></span>

