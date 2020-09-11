---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
ms.openlocfilehash: 9321f7912cb1217a3b6a28f322469ea12e5820dc
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010626"
---
# <span data-ttu-id="c4b5f-104">0.9.579-接口 ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="c4b5f-104">0.9.579 - interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="c4b5f-105">调用方实现此接口以接收 AddScriptToExecuteOnDocumentCreated 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="c4b5f-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="c4b5f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c4b5f-106">Summary</span></span>

 <span data-ttu-id="c4b5f-107">成员</span><span class="sxs-lookup"><span data-stu-id="c4b5f-107">Members</span></span>                        | <span data-ttu-id="c4b5f-108">描述</span><span class="sxs-lookup"><span data-stu-id="c4b5f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c4b5f-109">调用</span><span class="sxs-lookup"><span data-stu-id="c4b5f-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c4b5f-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="c4b5f-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="c4b5f-111">成员</span><span class="sxs-lookup"><span data-stu-id="c4b5f-111">Members</span></span>

#### <span data-ttu-id="c4b5f-112">调用</span><span class="sxs-lookup"><span data-stu-id="c4b5f-112">Invoke</span></span> 

<span data-ttu-id="c4b5f-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="c4b5f-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="c4b5f-114">公共 HRESULT [调用](#invoke) (HRESULT ERRORCODE，LPCWSTR id) </span><span class="sxs-lookup"><span data-stu-id="c4b5f-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR id)</span></span>

