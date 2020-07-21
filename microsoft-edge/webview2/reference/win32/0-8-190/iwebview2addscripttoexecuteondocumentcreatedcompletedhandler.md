---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 464192c119ddb7dd59ee7cb5981f172eb44dbb78
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885014"
---
# <span data-ttu-id="a112d-104">0.8.355-接口 IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a112d-104">0.8.355 - interface IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a112d-105">调用方实现此接口以接收 AddScriptToExecuteOnDocumentCreated 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="a112d-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="a112d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a112d-106">Summary</span></span>

 <span data-ttu-id="a112d-107">成员</span><span class="sxs-lookup"><span data-stu-id="a112d-107">Members</span></span>                        | <span data-ttu-id="a112d-108">描述</span><span class="sxs-lookup"><span data-stu-id="a112d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a112d-109">调用</span><span class="sxs-lookup"><span data-stu-id="a112d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a112d-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="a112d-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="a112d-111">成员</span><span class="sxs-lookup"><span data-stu-id="a112d-111">Members</span></span>

#### <span data-ttu-id="a112d-112">调用</span><span class="sxs-lookup"><span data-stu-id="a112d-112">Invoke</span></span> 

<span data-ttu-id="a112d-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="a112d-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a112d-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE、LPCWSTR id）</span><span class="sxs-lookup"><span data-stu-id="a112d-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR id)</span></span>

