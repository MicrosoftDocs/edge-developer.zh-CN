---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 95fa97268fb5695aebf5c1414752cf12cf1da57b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881142"
---
# <span data-ttu-id="f0360-104">0.9.430-接口 ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="f0360-104">0.9.430 - interface ICoreWebView2ContentLoadingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="f0360-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="f0360-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="f0360-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="f0360-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="f0360-107">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f0360-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="f0360-108">摘要</span><span class="sxs-lookup"><span data-stu-id="f0360-108">Summary</span></span>

 <span data-ttu-id="f0360-109">成员</span><span class="sxs-lookup"><span data-stu-id="f0360-109">Members</span></span>                        | <span data-ttu-id="f0360-110">描述</span><span class="sxs-lookup"><span data-stu-id="f0360-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f0360-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f0360-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="f0360-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f0360-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="f0360-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="f0360-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="f0360-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="f0360-114">The ID of the navigation.</span></span>

## <span data-ttu-id="f0360-115">成员</span><span class="sxs-lookup"><span data-stu-id="f0360-115">Members</span></span>

#### <span data-ttu-id="f0360-116">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f0360-116">get_IsErrorPage</span></span> 

<span data-ttu-id="f0360-117">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f0360-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="f0360-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="f0360-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="f0360-119">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="f0360-119">get_NavigationId</span></span> 

<span data-ttu-id="f0360-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="f0360-120">The ID of the navigation.</span></span>

> <span data-ttu-id="f0360-121">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="f0360-121">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

