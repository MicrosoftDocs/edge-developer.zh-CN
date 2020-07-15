---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a0372e9319a3dd260092b8bc96c693976b7f1fec
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880316"
---
# <span data-ttu-id="b980f-104">0.9.515-接口 ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="b980f-104">0.9.515 - interface ICoreWebView2ScriptDialogOpeningEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="b980f-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="b980f-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="b980f-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="b980f-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="b980f-107">ScriptDialogOpening 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="b980f-107">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="b980f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b980f-108">Summary</span></span>

 <span data-ttu-id="b980f-109">成员</span><span class="sxs-lookup"><span data-stu-id="b980f-109">Members</span></span>                        | <span data-ttu-id="b980f-110">描述</span><span class="sxs-lookup"><span data-stu-id="b980f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b980f-111">接受</span><span class="sxs-lookup"><span data-stu-id="b980f-111">Accept</span></span>](#accept) | <span data-ttu-id="b980f-112">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="b980f-112">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="b980f-113">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="b980f-113">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="b980f-114">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="b980f-114">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="b980f-115">get_Kind</span><span class="sxs-lookup"><span data-stu-id="b980f-115">get_Kind</span></span>](#get_kind) | <span data-ttu-id="b980f-116">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="b980f-116">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="b980f-117">get_Message</span><span class="sxs-lookup"><span data-stu-id="b980f-117">get_Message</span></span>](#get_message) | <span data-ttu-id="b980f-118">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="b980f-118">The message of the dialog box.</span></span>
[<span data-ttu-id="b980f-119">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="b980f-119">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="b980f-120">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="b980f-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="b980f-121">get_Uri</span><span class="sxs-lookup"><span data-stu-id="b980f-121">get_Uri</span></span>](#get_uri) | <span data-ttu-id="b980f-122">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="b980f-122">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="b980f-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="b980f-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="b980f-124">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="b980f-124">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="b980f-125">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="b980f-125">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="b980f-126">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="b980f-126">Set the ResultText property.</span></span>

## <span data-ttu-id="b980f-127">成员</span><span class="sxs-lookup"><span data-stu-id="b980f-127">Members</span></span>

#### <span data-ttu-id="b980f-128">接受</span><span class="sxs-lookup"><span data-stu-id="b980f-128">Accept</span></span> 

<span data-ttu-id="b980f-129">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="b980f-129">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="b980f-130">public HRESULT [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="b980f-130">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="b980f-131">从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。</span><span class="sxs-lookup"><span data-stu-id="b980f-131">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="b980f-132">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="b980f-132">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="b980f-133">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="b980f-133">get_DefaultText</span></span> 

<span data-ttu-id="b980f-134">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="b980f-134">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="b980f-135">公共 HRESULT [get_DefaultText](#get_defaulttext)（LPWSTR \* DefaultText）</span><span class="sxs-lookup"><span data-stu-id="b980f-135">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="b980f-136">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="b980f-136">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="b980f-137">get_Kind</span><span class="sxs-lookup"><span data-stu-id="b980f-137">get_Kind</span></span> 

<span data-ttu-id="b980f-138">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="b980f-138">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="b980f-139">公共 HRESULT [get_Kind](#get_kind)（COREWEBVIEW2_SCRIPT_DIALOG_KIND \* 种类）</span><span class="sxs-lookup"><span data-stu-id="b980f-139">public HRESULT [get_Kind](#get_kind)(COREWEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

<span data-ttu-id="b980f-140">接受、确认、提示或 beforeunload。</span><span class="sxs-lookup"><span data-stu-id="b980f-140">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="b980f-141">get_Message</span><span class="sxs-lookup"><span data-stu-id="b980f-141">get_Message</span></span> 

<span data-ttu-id="b980f-142">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="b980f-142">The message of the dialog box.</span></span>

> <span data-ttu-id="b980f-143">公共 HRESULT [get_Message](#get_message)（LPWSTR \* 消息）</span><span class="sxs-lookup"><span data-stu-id="b980f-143">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="b980f-144">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。</span><span class="sxs-lookup"><span data-stu-id="b980f-144">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="b980f-145">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="b980f-145">get_ResultText</span></span> 

<span data-ttu-id="b980f-146">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="b980f-146">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="b980f-147">公共 HRESULT [get_ResultText](#get_resulttext)（LPWSTR \* ResultText）</span><span class="sxs-lookup"><span data-stu-id="b980f-147">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="b980f-148">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="b980f-148">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="b980f-149">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="b980f-149">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="b980f-150">get_Uri</span><span class="sxs-lookup"><span data-stu-id="b980f-150">get_Uri</span></span> 

<span data-ttu-id="b980f-151">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="b980f-151">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="b980f-152">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="b980f-152">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="b980f-153">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="b980f-153">GetDeferral</span></span> 

<span data-ttu-id="b980f-154">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="b980f-154">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="b980f-155">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="b980f-155">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="b980f-156">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="b980f-156">You can use this to complete the event at a later time.</span></span>

#### <span data-ttu-id="b980f-157">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="b980f-157">put_ResultText</span></span> 

<span data-ttu-id="b980f-158">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="b980f-158">Set the ResultText property.</span></span>

> <span data-ttu-id="b980f-159">public HRESULT [put_ResultText](#put_resulttext)（LPCWSTR ResultText）</span><span class="sxs-lookup"><span data-stu-id="b980f-159">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

