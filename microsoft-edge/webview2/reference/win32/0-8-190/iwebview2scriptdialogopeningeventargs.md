---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 867a8f3656b04a566708fc6fc1a24e80b967c1e2
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652822"
---
# <span data-ttu-id="8743c-104">interface IWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="8743c-104">interface IWebView2ScriptDialogOpeningEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="8743c-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="8743c-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="8743c-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="8743c-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="8743c-107">[IWebView2WebView：： add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening)事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="8743c-107">Event args for the [IWebView2WebView::add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening) event.</span></span>

## <span data-ttu-id="8743c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="8743c-108">Summary</span></span>

 <span data-ttu-id="8743c-109">成员</span><span class="sxs-lookup"><span data-stu-id="8743c-109">Members</span></span>                        | <span data-ttu-id="8743c-110">描述</span><span class="sxs-lookup"><span data-stu-id="8743c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8743c-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8743c-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="8743c-112">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="8743c-112">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="8743c-113">get_Kind</span><span class="sxs-lookup"><span data-stu-id="8743c-113">get_Kind</span></span>](#get_kind) | <span data-ttu-id="8743c-114">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="8743c-114">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="8743c-115">get_Message</span><span class="sxs-lookup"><span data-stu-id="8743c-115">get_Message</span></span>](#get_message) | <span data-ttu-id="8743c-116">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="8743c-116">The message of the dialog box.</span></span>
[<span data-ttu-id="8743c-117">接受</span><span class="sxs-lookup"><span data-stu-id="8743c-117">Accept</span></span>](#accept) | <span data-ttu-id="8743c-118">宿主可以调用此方法来响应 "确定" 以确认和提示对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="8743c-118">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="8743c-119">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="8743c-119">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="8743c-120">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="8743c-120">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="8743c-121">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="8743c-121">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="8743c-122">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="8743c-122">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="8743c-123">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="8743c-123">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="8743c-124">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="8743c-124">Set the ResultText property.</span></span>
[<span data-ttu-id="8743c-125">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8743c-125">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="8743c-126">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="8743c-126">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="8743c-127">成员</span><span class="sxs-lookup"><span data-stu-id="8743c-127">Members</span></span>

#### <span data-ttu-id="8743c-128">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8743c-128">get_Uri</span></span> 

<span data-ttu-id="8743c-129">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="8743c-129">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="8743c-130">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="8743c-130">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="8743c-131">get_Kind</span><span class="sxs-lookup"><span data-stu-id="8743c-131">get_Kind</span></span> 

<span data-ttu-id="8743c-132">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="8743c-132">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="8743c-133">公共 HRESULT [get_Kind](#get_kind)（WEBVIEW2_SCRIPT_DIALOG_KIND \* 种类）</span><span class="sxs-lookup"><span data-stu-id="8743c-133">public HRESULT [get_Kind](#get_kind)(WEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

#### <span data-ttu-id="8743c-134">get_Message</span><span class="sxs-lookup"><span data-stu-id="8743c-134">get_Message</span></span> 

<span data-ttu-id="8743c-135">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="8743c-135">The message of the dialog box.</span></span>

> <span data-ttu-id="8743c-136">公共 HRESULT [get_Message](#get_message)（LPWSTR \* 消息）</span><span class="sxs-lookup"><span data-stu-id="8743c-136">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="8743c-137">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="8743c-137">From JavaScript this is the first parameter passed to alert, confirm, and prompt.</span></span>

#### <span data-ttu-id="8743c-138">接受</span><span class="sxs-lookup"><span data-stu-id="8743c-138">Accept</span></span> 

<span data-ttu-id="8743c-139">宿主可以调用此方法来响应 "确定" 以确认和提示对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="8743c-139">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="8743c-140">public HRESULT [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="8743c-140">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="8743c-141">从 JavaScript 中，这意味着确认函数在调用 Accept 时返回 true。</span><span class="sxs-lookup"><span data-stu-id="8743c-141">From JavaScript this means that the confirm function returns true if Accept is called.</span></span> <span data-ttu-id="8743c-142">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="8743c-142">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="8743c-143">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="8743c-143">get_DefaultText</span></span> 

<span data-ttu-id="8743c-144">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="8743c-144">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="8743c-145">公共 HRESULT [get_DefaultText](#get_defaulttext)（LPWSTR \* DefaultText）</span><span class="sxs-lookup"><span data-stu-id="8743c-145">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="8743c-146">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="8743c-146">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="8743c-147">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="8743c-147">get_ResultText</span></span> 

<span data-ttu-id="8743c-148">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="8743c-148">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="8743c-149">公共 HRESULT [get_ResultText](#get_resulttext)（LPWSTR \* ResultText）</span><span class="sxs-lookup"><span data-stu-id="8743c-149">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="8743c-150">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="8743c-150">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="8743c-151">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="8743c-151">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="8743c-152">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="8743c-152">put_ResultText</span></span> 

<span data-ttu-id="8743c-153">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="8743c-153">Set the ResultText property.</span></span>

> <span data-ttu-id="8743c-154">public HRESULT [put_ResultText](#put_resulttext)（LPCWSTR ResultText）</span><span class="sxs-lookup"><span data-stu-id="8743c-154">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

#### <span data-ttu-id="8743c-155">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8743c-155">GetDeferral</span></span> 

<span data-ttu-id="8743c-156">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="8743c-156">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="8743c-157">公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="8743c-157">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="8743c-158">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="8743c-158">You can use this to complete the event at a later time.</span></span>

