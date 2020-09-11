---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2SourceChangedEventArgs
ms.openlocfilehash: b9350db7d59c0369bfb16d10e30a23ef3f6bffa5
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010451"
---
# <span data-ttu-id="a401e-104">0.9.579-接口 ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="a401e-104">0.9.579 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="a401e-105">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a401e-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="a401e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a401e-106">Summary</span></span>

 <span data-ttu-id="a401e-107">成员</span><span class="sxs-lookup"><span data-stu-id="a401e-107">Members</span></span>                        | <span data-ttu-id="a401e-108">描述</span><span class="sxs-lookup"><span data-stu-id="a401e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a401e-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="a401e-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="a401e-110">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a401e-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="a401e-111">成员</span><span class="sxs-lookup"><span data-stu-id="a401e-111">Members</span></span>

#### <span data-ttu-id="a401e-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="a401e-112">get_IsNewDocument</span></span> 

<span data-ttu-id="a401e-113">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a401e-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="a401e-114">公共 HRESULT [get_IsNewDocument](#get_isnewdocument) (BOOL \* IsNewDocument) </span><span class="sxs-lookup"><span data-stu-id="a401e-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

