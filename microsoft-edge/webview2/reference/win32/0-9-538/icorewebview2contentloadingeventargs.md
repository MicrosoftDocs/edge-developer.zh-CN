---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 8acec97ec6060cd53adc3821f6a51db2048935fb
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698487"
---
# <span data-ttu-id="8298c-104">interface ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="8298c-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="8298c-105">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="8298c-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="8298c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="8298c-106">Summary</span></span>

 <span data-ttu-id="8298c-107">成员</span><span class="sxs-lookup"><span data-stu-id="8298c-107">Members</span></span>                        | <span data-ttu-id="8298c-108">描述</span><span class="sxs-lookup"><span data-stu-id="8298c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8298c-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="8298c-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="8298c-110">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="8298c-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="8298c-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="8298c-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="8298c-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="8298c-112">The ID of the navigation.</span></span>

## <span data-ttu-id="8298c-113">成员</span><span class="sxs-lookup"><span data-stu-id="8298c-113">Members</span></span>

#### <span data-ttu-id="8298c-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="8298c-114">get_IsErrorPage</span></span> 

<span data-ttu-id="8298c-115">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="8298c-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="8298c-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="8298c-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="8298c-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="8298c-117">get_NavigationId</span></span> 

<span data-ttu-id="8298c-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="8298c-118">The ID of the navigation.</span></span>

> <span data-ttu-id="8298c-119">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="8298c-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

