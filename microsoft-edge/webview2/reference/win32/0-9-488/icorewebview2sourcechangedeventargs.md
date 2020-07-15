---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 9ea8f860d637c5d9e49e68917d167380c0418b87
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877369"
---
# <span data-ttu-id="3a178-104">0.9.515-接口 ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="3a178-104">0.9.515 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="3a178-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="3a178-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="3a178-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="3a178-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="3a178-107">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3a178-107">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="3a178-108">摘要</span><span class="sxs-lookup"><span data-stu-id="3a178-108">Summary</span></span>

 <span data-ttu-id="3a178-109">成员</span><span class="sxs-lookup"><span data-stu-id="3a178-109">Members</span></span>                        | <span data-ttu-id="3a178-110">描述</span><span class="sxs-lookup"><span data-stu-id="3a178-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3a178-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="3a178-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="3a178-112">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="3a178-112">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="3a178-113">成员</span><span class="sxs-lookup"><span data-stu-id="3a178-113">Members</span></span>

#### <span data-ttu-id="3a178-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="3a178-114">get_IsNewDocument</span></span> 

<span data-ttu-id="3a178-115">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="3a178-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="3a178-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="3a178-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

