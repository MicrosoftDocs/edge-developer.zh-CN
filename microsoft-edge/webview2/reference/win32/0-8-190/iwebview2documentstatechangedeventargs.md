---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 342716da2cded9c903f1edd13fb3400c779a9b39
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653046"
---
# <span data-ttu-id="b2c48-104">interface IWebView2DocumentStateChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="b2c48-104">interface IWebView2DocumentStateChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="b2c48-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="b2c48-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="b2c48-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="b2c48-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2DocumentStateChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="b2c48-107">DocumentStateChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="b2c48-107">Event args for the DocumentStateChanged event.</span></span>

## <span data-ttu-id="b2c48-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b2c48-108">Summary</span></span>

 <span data-ttu-id="b2c48-109">成员</span><span class="sxs-lookup"><span data-stu-id="b2c48-109">Members</span></span>                        | <span data-ttu-id="b2c48-110">描述</span><span class="sxs-lookup"><span data-stu-id="b2c48-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b2c48-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="b2c48-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="b2c48-112">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="b2c48-112">True if the page being navigated to is a new document.</span></span>
[<span data-ttu-id="b2c48-113">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="b2c48-113">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="b2c48-114">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="b2c48-114">True if the loaded content is an error page.</span></span>

## <span data-ttu-id="b2c48-115">成员</span><span class="sxs-lookup"><span data-stu-id="b2c48-115">Members</span></span>

#### <span data-ttu-id="b2c48-116">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="b2c48-116">get_IsNewDocument</span></span> 

<span data-ttu-id="b2c48-117">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="b2c48-117">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="b2c48-118">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="b2c48-118">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

#### <span data-ttu-id="b2c48-119">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="b2c48-119">get_IsErrorPage</span></span> 

<span data-ttu-id="b2c48-120">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="b2c48-120">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="b2c48-121">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="b2c48-121">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

