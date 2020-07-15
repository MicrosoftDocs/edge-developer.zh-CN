---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 899adcb7cfa171e8c1f6cb9693092e36f2e41a5f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877761"
---
# <span data-ttu-id="60756-104">0.9.515-WebView2 的 CoreWebView2ContentLoadingEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="60756-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2ContentLoadingEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="60756-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="60756-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="60756-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="60756-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="60756-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="60756-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="60756-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="60756-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="60756-109">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="60756-109">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="60756-110">摘要</span><span class="sxs-lookup"><span data-stu-id="60756-110">Summary</span></span>

 <span data-ttu-id="60756-111">成员</span><span class="sxs-lookup"><span data-stu-id="60756-111">Members</span></span>                        | <span data-ttu-id="60756-112">描述</span><span class="sxs-lookup"><span data-stu-id="60756-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="60756-113">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="60756-113">IsErrorPage</span></span>](#iserrorpage) | <span data-ttu-id="60756-114">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="60756-114">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="60756-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="60756-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="60756-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="60756-116">The ID of the navigation.</span></span>

## <span data-ttu-id="60756-117">成员</span><span class="sxs-lookup"><span data-stu-id="60756-117">Members</span></span>

#### <span data-ttu-id="60756-118">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="60756-118">IsErrorPage</span></span> 

<span data-ttu-id="60756-119">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="60756-119">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="60756-120">公共 bool [IsErrorPage](#iserrorpage)</span><span class="sxs-lookup"><span data-stu-id="60756-120">public bool [IsErrorPage](#iserrorpage)</span></span>

#### <span data-ttu-id="60756-121">NavigationId</span><span class="sxs-lookup"><span data-stu-id="60756-121">NavigationId</span></span> 

<span data-ttu-id="60756-122">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="60756-122">The ID of the navigation.</span></span>

> <span data-ttu-id="60756-123">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="60756-123">public ulong [NavigationId](#navigationid)</span></span>

