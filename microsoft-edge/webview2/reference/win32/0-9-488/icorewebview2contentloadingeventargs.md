---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a5dd8dc0b504faad7c02669ae464ca1ef75c88af
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880778"
---
# <span data-ttu-id="78f1b-104">0.9.515-接口 ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="78f1b-104">0.9.515 - interface ICoreWebView2ContentLoadingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="78f1b-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="78f1b-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="78f1b-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="78f1b-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="78f1b-107">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="78f1b-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="78f1b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="78f1b-108">Summary</span></span>

 <span data-ttu-id="78f1b-109">成员</span><span class="sxs-lookup"><span data-stu-id="78f1b-109">Members</span></span>                        | <span data-ttu-id="78f1b-110">描述</span><span class="sxs-lookup"><span data-stu-id="78f1b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="78f1b-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="78f1b-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="78f1b-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="78f1b-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="78f1b-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="78f1b-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="78f1b-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="78f1b-114">The ID of the navigation.</span></span>

## <span data-ttu-id="78f1b-115">成员</span><span class="sxs-lookup"><span data-stu-id="78f1b-115">Members</span></span>

#### <span data-ttu-id="78f1b-116">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="78f1b-116">get_IsErrorPage</span></span> 

<span data-ttu-id="78f1b-117">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="78f1b-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="78f1b-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="78f1b-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="78f1b-119">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="78f1b-119">get_NavigationId</span></span> 

<span data-ttu-id="78f1b-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="78f1b-120">The ID of the navigation.</span></span>

> <span data-ttu-id="78f1b-121">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="78f1b-121">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

