---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: c3ba6ac3a2478861abb7b26e726a9cbd606b0eb9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652975"
---
# <span data-ttu-id="a13aa-104">interface ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="a13aa-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="a13aa-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a13aa-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="a13aa-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a13aa-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="a13aa-107">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a13aa-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="a13aa-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a13aa-108">Summary</span></span>

 <span data-ttu-id="a13aa-109">成员</span><span class="sxs-lookup"><span data-stu-id="a13aa-109">Members</span></span>                        | <span data-ttu-id="a13aa-110">描述</span><span class="sxs-lookup"><span data-stu-id="a13aa-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a13aa-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="a13aa-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="a13aa-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a13aa-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="a13aa-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="a13aa-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="a13aa-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a13aa-114">The ID of the navigation.</span></span>

## <span data-ttu-id="a13aa-115">成员</span><span class="sxs-lookup"><span data-stu-id="a13aa-115">Members</span></span>

#### <span data-ttu-id="a13aa-116">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="a13aa-116">get_IsErrorPage</span></span> 

<span data-ttu-id="a13aa-117">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a13aa-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="a13aa-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="a13aa-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="a13aa-119">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="a13aa-119">get_NavigationId</span></span> 

<span data-ttu-id="a13aa-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a13aa-120">The ID of the navigation.</span></span>

> <span data-ttu-id="a13aa-121">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="a13aa-121">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

