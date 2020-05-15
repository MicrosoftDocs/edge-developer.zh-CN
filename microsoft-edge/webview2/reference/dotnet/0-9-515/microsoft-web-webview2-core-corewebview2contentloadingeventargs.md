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
ms.openlocfilehash: a63f20a49ff0816e0a8edee0b5b6898a82017334
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653126"
---
# <span data-ttu-id="53fef-104">CoreWebView2ContentLoadingEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="53fef-104">Microsoft.Web.WebView2.Core.CoreWebView2ContentLoadingEventArgs class</span></span> 

<span data-ttu-id="53fef-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="53fef-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="53fef-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="53fef-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="53fef-107">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="53fef-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="53fef-108">摘要</span><span class="sxs-lookup"><span data-stu-id="53fef-108">Summary</span></span>

 <span data-ttu-id="53fef-109">成员</span><span class="sxs-lookup"><span data-stu-id="53fef-109">Members</span></span>                        | <span data-ttu-id="53fef-110">描述</span><span class="sxs-lookup"><span data-stu-id="53fef-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="53fef-111">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="53fef-111">IsErrorPage</span></span>](#iserrorpage) | <span data-ttu-id="53fef-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="53fef-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="53fef-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="53fef-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="53fef-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="53fef-114">The ID of the navigation.</span></span>

## <span data-ttu-id="53fef-115">成员</span><span class="sxs-lookup"><span data-stu-id="53fef-115">Members</span></span>

#### <span data-ttu-id="53fef-116">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="53fef-116">IsErrorPage</span></span> 

<span data-ttu-id="53fef-117">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="53fef-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="53fef-118">公共 bool [IsErrorPage](#iserrorpage)</span><span class="sxs-lookup"><span data-stu-id="53fef-118">public bool [IsErrorPage](#iserrorpage)</span></span>

#### <span data-ttu-id="53fef-119">NavigationId</span><span class="sxs-lookup"><span data-stu-id="53fef-119">NavigationId</span></span> 

<span data-ttu-id="53fef-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="53fef-120">The ID of the navigation.</span></span>

> <span data-ttu-id="53fef-121">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="53fef-121">public ulong [NavigationId](#navigationid)</span></span>

