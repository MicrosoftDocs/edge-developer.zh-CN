---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: abe167548b7e604bd60c792660ea5b52dec9b848
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697299"
---
# <span data-ttu-id="5687a-104">CoreWebView2ContentLoadingEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="5687a-104">Microsoft.Web.WebView2.Core.CoreWebView2ContentLoadingEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="5687a-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="5687a-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="5687a-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="5687a-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="5687a-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="5687a-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5687a-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="5687a-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5687a-109">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5687a-109">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="5687a-110">摘要</span><span class="sxs-lookup"><span data-stu-id="5687a-110">Summary</span></span>

 <span data-ttu-id="5687a-111">成员</span><span class="sxs-lookup"><span data-stu-id="5687a-111">Members</span></span>                        | <span data-ttu-id="5687a-112">描述</span><span class="sxs-lookup"><span data-stu-id="5687a-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5687a-113">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="5687a-113">IsErrorPage</span></span>](#iserrorpage) | <span data-ttu-id="5687a-114">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="5687a-114">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="5687a-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="5687a-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="5687a-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="5687a-116">The ID of the navigation.</span></span>

## <span data-ttu-id="5687a-117">成员</span><span class="sxs-lookup"><span data-stu-id="5687a-117">Members</span></span>

#### <span data-ttu-id="5687a-118">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="5687a-118">IsErrorPage</span></span> 

<span data-ttu-id="5687a-119">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="5687a-119">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="5687a-120">公共 bool [IsErrorPage](#iserrorpage)</span><span class="sxs-lookup"><span data-stu-id="5687a-120">public bool [IsErrorPage](#iserrorpage)</span></span>

#### <span data-ttu-id="5687a-121">NavigationId</span><span class="sxs-lookup"><span data-stu-id="5687a-121">NavigationId</span></span> 

<span data-ttu-id="5687a-122">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="5687a-122">The ID of the navigation.</span></span>

> <span data-ttu-id="5687a-123">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="5687a-123">public ulong [NavigationId](#navigationid)</span></span>

