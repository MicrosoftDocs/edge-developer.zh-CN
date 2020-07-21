---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: cd8f96787d289ab0fe649244ce665445efdbcecf
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884041"
---
# <span data-ttu-id="a034e-104">0.9.430-接口 ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="a034e-104">0.9.430 - interface ICoreWebView2ScriptDialogOpeningEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="a034e-105">ScriptDialogOpening 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a034e-105">Event args for the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="a034e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a034e-106">Summary</span></span>

 <span data-ttu-id="a034e-107">成员</span><span class="sxs-lookup"><span data-stu-id="a034e-107">Members</span></span>                        | <span data-ttu-id="a034e-108">描述</span><span class="sxs-lookup"><span data-stu-id="a034e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a034e-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="a034e-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="a034e-110">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="a034e-110">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="a034e-111">get_Kind</span><span class="sxs-lookup"><span data-stu-id="a034e-111">get_Kind</span></span>](#get_kind) | <span data-ttu-id="a034e-112">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="a034e-112">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="a034e-113">get_Message</span><span class="sxs-lookup"><span data-stu-id="a034e-113">get_Message</span></span>](#get_message) | <span data-ttu-id="a034e-114">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="a034e-114">The message of the dialog box.</span></span>
[<span data-ttu-id="a034e-115">接受</span><span class="sxs-lookup"><span data-stu-id="a034e-115">Accept</span></span>](#accept) | <span data-ttu-id="a034e-116">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="a034e-116">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="a034e-117">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="a034e-117">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="a034e-118">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="a034e-118">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="a034e-119">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="a034e-119">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="a034e-120">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="a034e-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="a034e-121">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="a034e-121">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="a034e-122">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="a034e-122">Set the ResultText property.</span></span>
[<span data-ttu-id="a034e-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="a034e-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="a034e-124">可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="a034e-124">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="a034e-125">成员</span><span class="sxs-lookup"><span data-stu-id="a034e-125">Members</span></span>

#### <span data-ttu-id="a034e-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="a034e-126">get_Uri</span></span> 

<span data-ttu-id="a034e-127">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="a034e-127">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="a034e-128">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="a034e-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="a034e-129">get_Kind</span><span class="sxs-lookup"><span data-stu-id="a034e-129">get_Kind</span></span> 

<span data-ttu-id="a034e-130">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="a034e-130">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="a034e-131">公共 HRESULT [get_Kind](#get_kind)（CORE_WEBVIEW2_SCRIPT_DIALOG_KIND \* 种类）</span><span class="sxs-lookup"><span data-stu-id="a034e-131">public HRESULT [get_Kind](#get_kind)(CORE_WEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

<span data-ttu-id="a034e-132">接受、确认、提示或 beforeunload。</span><span class="sxs-lookup"><span data-stu-id="a034e-132">Accept, confirm, prompt, or beforeunload.</span></span>

#### <span data-ttu-id="a034e-133">get_Message</span><span class="sxs-lookup"><span data-stu-id="a034e-133">get_Message</span></span> 

<span data-ttu-id="a034e-134">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="a034e-134">The message of the dialog box.</span></span>

> <span data-ttu-id="a034e-135">公共 HRESULT [get_Message](#get_message)（LPWSTR \* 消息）</span><span class="sxs-lookup"><span data-stu-id="a034e-135">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="a034e-136">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。</span><span class="sxs-lookup"><span data-stu-id="a034e-136">From JavaScript this is the first parameter passed to alert, confirm, and prompt and is empty for beforeunload.</span></span>

#### <span data-ttu-id="a034e-137">接受</span><span class="sxs-lookup"><span data-stu-id="a034e-137">Accept</span></span> 

<span data-ttu-id="a034e-138">宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="a034e-138">The host may call this to respond with OK to confirm, prompt, and beforeunload dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="a034e-139">public HRESULT [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="a034e-139">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="a034e-140">从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。</span><span class="sxs-lookup"><span data-stu-id="a034e-140">From JavaScript, this means that the confirm and beforeunload function returns true if Accept is called.</span></span> <span data-ttu-id="a034e-141">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="a034e-141">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="a034e-142">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="a034e-142">get_DefaultText</span></span> 

<span data-ttu-id="a034e-143">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="a034e-143">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="a034e-144">公共 HRESULT [get_DefaultText](#get_defaulttext)（LPWSTR \* DefaultText）</span><span class="sxs-lookup"><span data-stu-id="a034e-144">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="a034e-145">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="a034e-145">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="a034e-146">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="a034e-146">get_ResultText</span></span> 

<span data-ttu-id="a034e-147">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="a034e-147">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="a034e-148">公共 HRESULT [get_ResultText](#get_resulttext)（LPWSTR \* ResultText）</span><span class="sxs-lookup"><span data-stu-id="a034e-148">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="a034e-149">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="a034e-149">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="a034e-150">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="a034e-150">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="a034e-151">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="a034e-151">put_ResultText</span></span> 

<span data-ttu-id="a034e-152">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="a034e-152">Set the ResultText property.</span></span>

> <span data-ttu-id="a034e-153">public HRESULT [put_ResultText](#put_resulttext)（LPCWSTR ResultText）</span><span class="sxs-lookup"><span data-stu-id="a034e-153">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

#### <span data-ttu-id="a034e-154">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="a034e-154">GetDeferral</span></span> 

<span data-ttu-id="a034e-155">可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="a034e-155">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="a034e-156">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="a034e-156">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="a034e-157">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="a034e-157">You can use this to complete the event at a later time.</span></span>

