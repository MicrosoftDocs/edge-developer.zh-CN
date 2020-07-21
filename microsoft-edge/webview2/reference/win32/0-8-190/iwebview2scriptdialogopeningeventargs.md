---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: de8c8cc2c6c6f857a2889ad167061d2834c30c02
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885791"
---
# <span data-ttu-id="6a74c-104">0.8.355-接口 IWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="6a74c-104">0.8.355 - interface IWebView2ScriptDialogOpeningEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

<span data-ttu-id="6a74c-105">[IWebView2WebView：： add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening)事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6a74c-105">Event args for the [IWebView2WebView::add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening) event.</span></span>

## <span data-ttu-id="6a74c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="6a74c-106">Summary</span></span>

 <span data-ttu-id="6a74c-107">成员</span><span class="sxs-lookup"><span data-stu-id="6a74c-107">Members</span></span>                        | <span data-ttu-id="6a74c-108">描述</span><span class="sxs-lookup"><span data-stu-id="6a74c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6a74c-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="6a74c-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="6a74c-110">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="6a74c-110">The URI of the page that requested the dialog box.</span></span>
[<span data-ttu-id="6a74c-111">get_Kind</span><span class="sxs-lookup"><span data-stu-id="6a74c-111">get_Kind</span></span>](#get_kind) | <span data-ttu-id="6a74c-112">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="6a74c-112">The kind of JavaScript dialog box.</span></span>
[<span data-ttu-id="6a74c-113">get_Message</span><span class="sxs-lookup"><span data-stu-id="6a74c-113">get_Message</span></span>](#get_message) | <span data-ttu-id="6a74c-114">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="6a74c-114">The message of the dialog box.</span></span>
[<span data-ttu-id="6a74c-115">接受</span><span class="sxs-lookup"><span data-stu-id="6a74c-115">Accept</span></span>](#accept) | <span data-ttu-id="6a74c-116">宿主可以调用此方法来响应 "确定" 以确认和提示对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="6a74c-116">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>
[<span data-ttu-id="6a74c-117">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="6a74c-117">get_DefaultText</span></span>](#get_defaulttext) | <span data-ttu-id="6a74c-118">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="6a74c-118">The second parameter passed to the JavaScript prompt dialog.</span></span>
[<span data-ttu-id="6a74c-119">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="6a74c-119">get_ResultText</span></span>](#get_resulttext) | <span data-ttu-id="6a74c-120">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="6a74c-120">The return value from the JavaScript prompt function if Accept is called.</span></span>
[<span data-ttu-id="6a74c-121">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="6a74c-121">put_ResultText</span></span>](#put_resulttext) | <span data-ttu-id="6a74c-122">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="6a74c-122">Set the ResultText property.</span></span>
[<span data-ttu-id="6a74c-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6a74c-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="6a74c-124">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="6a74c-124">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="6a74c-125">成员</span><span class="sxs-lookup"><span data-stu-id="6a74c-125">Members</span></span>

#### <span data-ttu-id="6a74c-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="6a74c-126">get_Uri</span></span> 

<span data-ttu-id="6a74c-127">请求对话框的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="6a74c-127">The URI of the page that requested the dialog box.</span></span>

> <span data-ttu-id="6a74c-128">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="6a74c-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="6a74c-129">get_Kind</span><span class="sxs-lookup"><span data-stu-id="6a74c-129">get_Kind</span></span> 

<span data-ttu-id="6a74c-130">"JavaScript 类型" 对话框。</span><span class="sxs-lookup"><span data-stu-id="6a74c-130">The kind of JavaScript dialog box.</span></span>

> <span data-ttu-id="6a74c-131">公共 HRESULT [get_Kind](#get_kind)（WEBVIEW2_SCRIPT_DIALOG_KIND \* 种类）</span><span class="sxs-lookup"><span data-stu-id="6a74c-131">public HRESULT [get_Kind](#get_kind)(WEBVIEW2_SCRIPT_DIALOG_KIND \* kind)</span></span>

#### <span data-ttu-id="6a74c-132">get_Message</span><span class="sxs-lookup"><span data-stu-id="6a74c-132">get_Message</span></span> 

<span data-ttu-id="6a74c-133">对话框的消息。</span><span class="sxs-lookup"><span data-stu-id="6a74c-133">The message of the dialog box.</span></span>

> <span data-ttu-id="6a74c-134">公共 HRESULT [get_Message](#get_message)（LPWSTR \* 消息）</span><span class="sxs-lookup"><span data-stu-id="6a74c-134">public HRESULT [get_Message](#get_message)(LPWSTR \* message)</span></span>

<span data-ttu-id="6a74c-135">从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="6a74c-135">From JavaScript this is the first parameter passed to alert, confirm, and prompt.</span></span>

#### <span data-ttu-id="6a74c-136">接受</span><span class="sxs-lookup"><span data-stu-id="6a74c-136">Accept</span></span> 

<span data-ttu-id="6a74c-137">宿主可以调用此方法来响应 "确定" 以确认和提示对话框，或者不调用此方法来指示 "取消"。</span><span class="sxs-lookup"><span data-stu-id="6a74c-137">The host may call this to respond with OK to confirm and prompt dialogs or not call this method to indicate cancel.</span></span>

> <span data-ttu-id="6a74c-138">public HRESULT [Accept](#accept)（）</span><span class="sxs-lookup"><span data-stu-id="6a74c-138">public HRESULT [Accept](#accept)()</span></span>

<span data-ttu-id="6a74c-139">从 JavaScript 中，这意味着确认函数在调用 Accept 时返回 true。</span><span class="sxs-lookup"><span data-stu-id="6a74c-139">From JavaScript this means that the confirm function returns true if Accept is called.</span></span> <span data-ttu-id="6a74c-140">对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="6a74c-140">And for the prompt function it returns the value of ResultText if Accept is called and returns false otherwise.</span></span>

#### <span data-ttu-id="6a74c-141">get_DefaultText</span><span class="sxs-lookup"><span data-stu-id="6a74c-141">get_DefaultText</span></span> 

<span data-ttu-id="6a74c-142">第二个参数传递到 JavaScript 提示对话框。</span><span class="sxs-lookup"><span data-stu-id="6a74c-142">The second parameter passed to the JavaScript prompt dialog.</span></span>

> <span data-ttu-id="6a74c-143">公共 HRESULT [get_DefaultText](#get_defaulttext)（LPWSTR \* DefaultText）</span><span class="sxs-lookup"><span data-stu-id="6a74c-143">public HRESULT [get_DefaultText](#get_defaulttext)(LPWSTR \* defaultText)</span></span>

<span data-ttu-id="6a74c-144">这是提示 JavaScript 函数的结果所使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="6a74c-144">This is the default value to use for the result of the prompt JavaScript function.</span></span>

#### <span data-ttu-id="6a74c-145">get_ResultText</span><span class="sxs-lookup"><span data-stu-id="6a74c-145">get_ResultText</span></span> 

<span data-ttu-id="6a74c-146">如果调用 Accept，则返回 JavaScript 提示函数的值。</span><span class="sxs-lookup"><span data-stu-id="6a74c-146">The return value from the JavaScript prompt function if Accept is called.</span></span>

> <span data-ttu-id="6a74c-147">公共 HRESULT [get_ResultText](#get_resulttext)（LPWSTR \* ResultText）</span><span class="sxs-lookup"><span data-stu-id="6a74c-147">public HRESULT [get_ResultText](#get_resulttext)(LPWSTR \* resultText)</span></span>

<span data-ttu-id="6a74c-148">对于除提示之外的对话框类型，忽略此操作。</span><span class="sxs-lookup"><span data-stu-id="6a74c-148">This is ignored for dialog kinds other than prompt.</span></span> <span data-ttu-id="6a74c-149">如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。</span><span class="sxs-lookup"><span data-stu-id="6a74c-149">If Accept is not called this value is ignored and false is returned from prompt.</span></span>

#### <span data-ttu-id="6a74c-150">put_ResultText</span><span class="sxs-lookup"><span data-stu-id="6a74c-150">put_ResultText</span></span> 

<span data-ttu-id="6a74c-151">设置 ResultText 属性。</span><span class="sxs-lookup"><span data-stu-id="6a74c-151">Set the ResultText property.</span></span>

> <span data-ttu-id="6a74c-152">public HRESULT [put_ResultText](#put_resulttext)（LPCWSTR ResultText）</span><span class="sxs-lookup"><span data-stu-id="6a74c-152">public HRESULT [put_ResultText](#put_resulttext)(LPCWSTR resultText)</span></span>

#### <span data-ttu-id="6a74c-153">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6a74c-153">GetDeferral</span></span> 

<span data-ttu-id="6a74c-154">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="6a74c-154">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="6a74c-155">公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="6a74c-155">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="6a74c-156">稍后可使用此操作完成事件。</span><span class="sxs-lookup"><span data-stu-id="6a74c-156">You can use this to complete the event at a later time.</span></span>

