---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2DocumentStateChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 75741c1ba1d835d1c26c7d1db0845071216e0705
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886120"
---
# <span data-ttu-id="33b1d-104">0.8.355-接口 IWebView2DocumentStateChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="33b1d-104">0.8.355 - interface IWebView2DocumentStateChangedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DocumentStateChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="33b1d-105">DocumentStateChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="33b1d-105">Event args for the DocumentStateChanged event.</span></span>

## <span data-ttu-id="33b1d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="33b1d-106">Summary</span></span>

 <span data-ttu-id="33b1d-107">成员</span><span class="sxs-lookup"><span data-stu-id="33b1d-107">Members</span></span>                        | <span data-ttu-id="33b1d-108">描述</span><span class="sxs-lookup"><span data-stu-id="33b1d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="33b1d-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="33b1d-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="33b1d-110">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="33b1d-110">True if the page being navigated to is a new document.</span></span>
[<span data-ttu-id="33b1d-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="33b1d-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="33b1d-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="33b1d-112">True if the loaded content is an error page.</span></span>

## <span data-ttu-id="33b1d-113">成员</span><span class="sxs-lookup"><span data-stu-id="33b1d-113">Members</span></span>

#### <span data-ttu-id="33b1d-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="33b1d-114">get_IsNewDocument</span></span> 

<span data-ttu-id="33b1d-115">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="33b1d-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="33b1d-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="33b1d-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

#### <span data-ttu-id="33b1d-117">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="33b1d-117">get_IsErrorPage</span></span> 

<span data-ttu-id="33b1d-118">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="33b1d-118">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="33b1d-119">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="33b1d-119">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

