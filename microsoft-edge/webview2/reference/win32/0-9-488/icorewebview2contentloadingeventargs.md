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
ms.openlocfilehash: c720b700257554891f13477f5f3508e331ac6b25
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698202"
---
# <span data-ttu-id="0a9f0-104">interface ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="0a9f0-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="0a9f0-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="0a9f0-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="0a9f0-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="0a9f0-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="0a9f0-107">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0a9f0-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="0a9f0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="0a9f0-108">Summary</span></span>

 <span data-ttu-id="0a9f0-109">成员</span><span class="sxs-lookup"><span data-stu-id="0a9f0-109">Members</span></span>                        | <span data-ttu-id="0a9f0-110">描述</span><span class="sxs-lookup"><span data-stu-id="0a9f0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0a9f0-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="0a9f0-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="0a9f0-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0a9f0-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="0a9f0-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="0a9f0-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="0a9f0-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="0a9f0-114">The ID of the navigation.</span></span>

## <span data-ttu-id="0a9f0-115">成员</span><span class="sxs-lookup"><span data-stu-id="0a9f0-115">Members</span></span>

#### <span data-ttu-id="0a9f0-116">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="0a9f0-116">get_IsErrorPage</span></span> 

<span data-ttu-id="0a9f0-117">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0a9f0-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="0a9f0-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="0a9f0-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="0a9f0-119">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="0a9f0-119">get_NavigationId</span></span> 

<span data-ttu-id="0a9f0-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="0a9f0-120">The ID of the navigation.</span></span>

> <span data-ttu-id="0a9f0-121">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="0a9f0-121">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

