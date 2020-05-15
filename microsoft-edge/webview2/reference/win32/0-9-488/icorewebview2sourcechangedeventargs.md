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
ms.openlocfilehash: 6d4c5e7893f9be78baca25e8976ca889ef9826c0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653149"
---
# <span data-ttu-id="f47e5-104">interface ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="f47e5-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="f47e5-105">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f47e5-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="f47e5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f47e5-106">Summary</span></span>

 <span data-ttu-id="f47e5-107">成员</span><span class="sxs-lookup"><span data-stu-id="f47e5-107">Members</span></span>                        | <span data-ttu-id="f47e5-108">描述</span><span class="sxs-lookup"><span data-stu-id="f47e5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f47e5-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="f47e5-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="f47e5-110">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f47e5-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="f47e5-111">成员</span><span class="sxs-lookup"><span data-stu-id="f47e5-111">Members</span></span>

#### <span data-ttu-id="f47e5-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="f47e5-112">get_IsNewDocument</span></span> 

<span data-ttu-id="f47e5-113">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f47e5-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="f47e5-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="f47e5-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

