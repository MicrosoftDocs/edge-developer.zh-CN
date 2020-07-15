---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8a9f1b1e44353796c6d3b57d3f4c6f3d4997aad5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880197"
---
# <span data-ttu-id="6b111-104">0.9.430-接口 ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="6b111-104">0.9.430 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="6b111-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="6b111-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="6b111-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="6b111-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="6b111-107">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6b111-107">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="6b111-108">摘要</span><span class="sxs-lookup"><span data-stu-id="6b111-108">Summary</span></span>

 <span data-ttu-id="6b111-109">成员</span><span class="sxs-lookup"><span data-stu-id="6b111-109">Members</span></span>                        | <span data-ttu-id="6b111-110">描述</span><span class="sxs-lookup"><span data-stu-id="6b111-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6b111-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="6b111-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="6b111-112">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6b111-112">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="6b111-113">成员</span><span class="sxs-lookup"><span data-stu-id="6b111-113">Members</span></span>

#### <span data-ttu-id="6b111-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="6b111-114">get_IsNewDocument</span></span> 

<span data-ttu-id="6b111-115">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6b111-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="6b111-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="6b111-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

