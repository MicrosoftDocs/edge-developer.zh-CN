---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: c6bb99078b5574ba89c0d66b49e2c63cd6888d28
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653084"
---
# <span data-ttu-id="7984d-104">interface ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="7984d-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="7984d-105">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7984d-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="7984d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="7984d-106">Summary</span></span>

 <span data-ttu-id="7984d-107">成员</span><span class="sxs-lookup"><span data-stu-id="7984d-107">Members</span></span>                        | <span data-ttu-id="7984d-108">描述</span><span class="sxs-lookup"><span data-stu-id="7984d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7984d-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="7984d-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="7984d-110">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="7984d-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="7984d-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="7984d-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="7984d-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="7984d-112">The ID of the navigation.</span></span>

## <span data-ttu-id="7984d-113">成员</span><span class="sxs-lookup"><span data-stu-id="7984d-113">Members</span></span>

#### <span data-ttu-id="7984d-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="7984d-114">get_IsErrorPage</span></span> 

<span data-ttu-id="7984d-115">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="7984d-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="7984d-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="7984d-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="7984d-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="7984d-117">get_NavigationId</span></span> 

<span data-ttu-id="7984d-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="7984d-118">The ID of the navigation.</span></span>

> <span data-ttu-id="7984d-119">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="7984d-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

