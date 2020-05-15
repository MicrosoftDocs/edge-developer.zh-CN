---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 45c0a26fa424f87e692b243b43e7a3b189a2acd8
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653221"
---
# <span data-ttu-id="0efb3-104">interface ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="0efb3-104">interface ICoreWebView2ScriptDialogOpeningEventArgs</span></span> 

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="0efb3-105">ScriptDialogOpening 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0efb3-105">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="0efb3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0efb3-106">Summary</span></span>

 <span data-ttu-id="0efb3-107">成员</span><span class="sxs-lookup"><span data-stu-id="0efb3-107">Members</span></span>                        | <span data-ttu-id="0efb3-108">描述</span><span class="sxs-lookup"><span data-stu-id="0efb3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0efb3-109">接受</span><span class="sxs-lookup"><span data-stu-id="0efb3-109">Accept</span></span>](#accept) | <span data-ttu-id="0efb3-110">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="0efb3-110">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="0efb3-111">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="0efb3-111">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="0efb3-112">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="0efb3-112">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="0efb3-113">get_Kind</span><span class="sxs-lookup"><span data-stu-id="0efb3-113">get_Kind</span></span>](#get_kind) | <span data-ttu-id="0efb3-114">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="0efb3-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="0efb3-115">get_Message</span><span class="sxs-lookup"><span data-stu-id="0efb3-115">get_Message</span></span>](#get_message) | <span data-ttu-id="0efb3-116">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="0efb3-116">The message of the dialog box.</span></span>
[<span data-ttu-id="0efb3-117">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="0efb3-117">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="0efb3-118">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="0efb3-118">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="0efb3-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0efb3-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="0efb3-120">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="0efb3-120">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="0efb3-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="0efb3-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="0efb3-122">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="0efb3-122">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="0efb3-123">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="0efb3-123">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="0efb3-124">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="0efb3-124">Set the ResultText property.</span></span>

## <span data-ttu-id="0efb3-125">成员</span><span class="sxs-lookup"><span data-stu-id="0efb3-125">Members</span></span>

#### <span data-ttu-id="0efb3-126">接受</span><span class="sxs-lookup"><span data-stu-id="0efb3-126">Accept</span></span> 

<span data-ttu-id="0efb3-127">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="0efb3-127">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="0efb3-128">public HRESULT [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="0efb3-128">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="0efb3-129">从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。</span><span class="sxs-lookup"><span data-stu-id="0efb3-129">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="0efb3-130">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="0efb3-130">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="0efb3-131">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="0efb3-131">get_DefaultText</span></span> 

<span data-ttu-id="0efb3-132">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="0efb3-132">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="0efb3-133">公共 HRESULT [get_DefaultText](#get_defaulttext)（LPWSTR \* DefaultText）</span><span class="sxs-lookup"><span data-stu-id="0efb3-133">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="0efb3-134">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="0efb3-134">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="0efb3-135">get_Kind</span><span class="sxs-lookup"><span data-stu-id="0efb3-135">get_Kind</span></span> 

<span data-ttu-id="0efb3-136">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="0efb3-136">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="0efb3-137">公共 HRESULT [get_Kind](#get_kind)（COREWEBVIEW2_SCRIPT_DIALOG_KIND \* 种类）</span><span class="sxs-lookup"><span data-stu-id="0efb3-137">public HRESULT [get_Kind](#get_kind)(COREWEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

<span data-ttu-id="0efb3-138">接受、确认、提示或 beforeunload。</span><span class="sxs-lookup"><span data-stu-id="0efb3-138">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="0efb3-139">get_Message</span><span class="sxs-lookup"><span data-stu-id="0efb3-139">get_Message</span></span> 

<span data-ttu-id="0efb3-140">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="0efb3-140">The message of the dialog box.</span></span>

> <span data-ttu-id="0efb3-141">公共 HRESULT [get_Message](#get_message)（LPWSTR \* 消息）</span><span class="sxs-lookup"><span data-stu-id="0efb3-141">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="0efb3-142">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。</span><span class="sxs-lookup"><span data-stu-id="0efb3-142">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="0efb3-143">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="0efb3-143">get_ResultText</span></span> 

<span data-ttu-id="0efb3-144">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="0efb3-144">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="0efb3-145">公共 HRESULT [get_ResultText](#get_resulttext)（LPWSTR \* ResultText）</span><span class="sxs-lookup"><span data-stu-id="0efb3-145">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="0efb3-146">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="0efb3-146">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="0efb3-147">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="0efb3-147">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="0efb3-148">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0efb3-148">get_Uri</span></span> 

<span data-ttu-id="0efb3-149">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="0efb3-149">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="0efb3-150">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="0efb3-150">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="0efb3-151">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="0efb3-151">GetDeferral</span></span> 

<span data-ttu-id="0efb3-152">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="0efb3-152">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="0efb3-153">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="0efb3-153">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="0efb3-154">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="0efb3-154">You can use this to complete the event at a later time.</span></span>

#### <span data-ttu-id="0efb3-155">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="0efb3-155">put_ResultText</span></span> 

<span data-ttu-id="0efb3-156">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="0efb3-156">Set the ResultText property.</span></span>

> <span data-ttu-id="0efb3-157">public HRESULT [put_ResultText](#put_resulttext)（LPCWSTR ResultText）</span><span class="sxs-lookup"><span data-stu-id="0efb3-157">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

