---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 885ad6b161fbde6721e1812735ab50d7e0c3e8d9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885049"
---
# <span data-ttu-id="d26e5-104">0.8.355-接口 IWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d26e5-104">0.8.355 - interface IWebView2AcceleratorKeyPressedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="d26e5-105">AcceleratorKeyPressed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d26e5-105">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="d26e5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d26e5-106">Summary</span></span>

 <span data-ttu-id="d26e5-107">成员</span><span class="sxs-lookup"><span data-stu-id="d26e5-107">Members</span></span>                        | <span data-ttu-id="d26e5-108">描述</span><span class="sxs-lookup"><span data-stu-id="d26e5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d26e5-109">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="d26e5-109">get_KeyEventType</span></span>](#get_keyeventtype) | <span data-ttu-id="d26e5-110">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="d26e5-110">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="d26e5-111">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="d26e5-111">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="d26e5-112">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="d26e5-112">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="d26e5-113">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="d26e5-113">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="d26e5-114">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="d26e5-114">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="d26e5-115">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="d26e5-115">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="d26e5-116">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="d26e5-116">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="d26e5-117">满足</span><span class="sxs-lookup"><span data-stu-id="d26e5-117">Handle</span></span>](#handle) | <span data-ttu-id="d26e5-118">调用此操作将允许浏览器进程继续。</span><span class="sxs-lookup"><span data-stu-id="d26e5-118">Calling this will allow the browser process to continue.</span></span>

## <span data-ttu-id="d26e5-119">成员</span><span class="sxs-lookup"><span data-stu-id="d26e5-119">Members</span></span>

#### <span data-ttu-id="d26e5-120">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="d26e5-120">get_KeyEventType</span></span> 

<span data-ttu-id="d26e5-121">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="d26e5-121">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="d26e5-122">public HRESULT [get_KeyEventType](#get_keyeventtype)（WEBVIEW2_KEY_EVENT_TYPE \* KeyEventType）</span><span class="sxs-lookup"><span data-stu-id="d26e5-122">public HRESULT [get_KeyEventType](#get_keyeventtype)(WEBVIEW2_KEY_EVENT_TYPE \* keyEventType)</span></span>

<span data-ttu-id="d26e5-123">这是 WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN、WEBVIEW2_KEY_EVENT_TYPE_KEY_UP、WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN 或 WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP 之一。</span><span class="sxs-lookup"><span data-stu-id="d26e5-123">This is one of WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN, WEBVIEW2_KEY_EVENT_TYPE_KEY_UP, WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN, or WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP.</span></span>

#### <span data-ttu-id="d26e5-124">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="d26e5-124">get_VirtualKey</span></span> 

<span data-ttu-id="d26e5-125">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="d26e5-125">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="d26e5-126">public HRESULT [get_VirtualKey](#get_virtualkey)（UINT \* VirtualKey）</span><span class="sxs-lookup"><span data-stu-id="d26e5-126">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="d26e5-127">这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。</span><span class="sxs-lookup"><span data-stu-id="d26e5-127">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="d26e5-128">可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。</span><span class="sxs-lookup"><span data-stu-id="d26e5-128">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="d26e5-129">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="d26e5-129">get_KeyEventLParam</span></span> 

<span data-ttu-id="d26e5-130">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="d26e5-130">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="d26e5-131">公共 HRESULT [get_KeyEventLParam](#get_keyeventlparam)（INT \* lParam）</span><span class="sxs-lookup"><span data-stu-id="d26e5-131">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="d26e5-132">请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。</span><span class="sxs-lookup"><span data-stu-id="d26e5-132">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="d26e5-133">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="d26e5-133">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="d26e5-134">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="d26e5-134">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="d26e5-135">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)（WEBVIEW2_PHYSICAL_KEY_STATUS \* PhysicalKeyStatus）</span><span class="sxs-lookup"><span data-stu-id="d26e5-135">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="d26e5-136">满足</span><span class="sxs-lookup"><span data-stu-id="d26e5-136">Handle</span></span> 

<span data-ttu-id="d26e5-137">调用此操作将允许浏览器进程继续。</span><span class="sxs-lookup"><span data-stu-id="d26e5-137">Calling this will allow the browser process to continue.</span></span>

> <span data-ttu-id="d26e5-138">公共 HRESULT[句柄](#handle)（已处理 BOOL）</span><span class="sxs-lookup"><span data-stu-id="d26e5-138">public HRESULT [Handle](#handle)(BOOL handled)</span></span>

<span data-ttu-id="d26e5-139">传递 TRUE 将阻止浏览器对此加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="d26e5-139">Passing TRUE will prevent the browser from performing the default action for this accelerator key.</span></span> <span data-ttu-id="d26e5-140">如果事件处理程序返回时没有调用[句柄（）](#handle)，则它等效于调用句柄（FALSE）。</span><span class="sxs-lookup"><span data-stu-id="d26e5-140">If the event handler returns without calling [Handle()](#handle), it is equivalent to calling Handle(FALSE).</span></span> <span data-ttu-id="d26e5-141">调用[句柄（）](#handle)之后，或事件处理程序返回将不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d26e5-141">Calling [Handle()](#handle) after it has already been called or the event handler has returned will do nothing.</span></span>

