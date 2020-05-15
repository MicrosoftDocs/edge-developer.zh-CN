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
ms.openlocfilehash: 5b15d6205306e558d1d8709cceed8b7a68a77bce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653007"
---
# <span data-ttu-id="b4286-104">interface IWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="b4286-104">interface IWebView2AcceleratorKeyPressedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="b4286-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="b4286-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="b4286-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="b4286-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="b4286-107">AcceleratorKeyPressed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="b4286-107">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="b4286-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b4286-108">Summary</span></span>

 <span data-ttu-id="b4286-109">成员</span><span class="sxs-lookup"><span data-stu-id="b4286-109">Members</span></span>                        | <span data-ttu-id="b4286-110">描述</span><span class="sxs-lookup"><span data-stu-id="b4286-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b4286-111">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="b4286-111">get_KeyEventType</span></span>](#get_keyeventtype) | <span data-ttu-id="b4286-112">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="b4286-112">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="b4286-113">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="b4286-113">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="b4286-114">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="b4286-114">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="b4286-115">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="b4286-115">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="b4286-116">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="b4286-116">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="b4286-117">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="b4286-117">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="b4286-118">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="b4286-118">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="b4286-119">满足</span><span class="sxs-lookup"><span data-stu-id="b4286-119">Handle</span></span>](#handle) | <span data-ttu-id="b4286-120">调用此操作将允许浏览器进程继续。</span><span class="sxs-lookup"><span data-stu-id="b4286-120">Calling this will allow the browser process to continue.</span></span>

## <span data-ttu-id="b4286-121">成员</span><span class="sxs-lookup"><span data-stu-id="b4286-121">Members</span></span>

#### <span data-ttu-id="b4286-122">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="b4286-122">get_KeyEventType</span></span> 

<span data-ttu-id="b4286-123">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="b4286-123">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="b4286-124">public HRESULT [get_KeyEventType](#get_keyeventtype)（WEBVIEW2_KEY_EVENT_TYPE \* KeyEventType）</span><span class="sxs-lookup"><span data-stu-id="b4286-124">public HRESULT [get_KeyEventType](#get_keyeventtype)(WEBVIEW2_KEY_EVENT_TYPE \* keyEventType)</span></span>

<span data-ttu-id="b4286-125">这是 WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN、WEBVIEW2_KEY_EVENT_TYPE_KEY_UP、WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN 或 WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP 之一。</span><span class="sxs-lookup"><span data-stu-id="b4286-125">This is one of WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN, WEBVIEW2_KEY_EVENT_TYPE_KEY_UP, WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN, or WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP.</span></span>

#### <span data-ttu-id="b4286-126">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="b4286-126">get_VirtualKey</span></span> 

<span data-ttu-id="b4286-127">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="b4286-127">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="b4286-128">public HRESULT [get_VirtualKey](#get_virtualkey)（UINT \* VirtualKey）</span><span class="sxs-lookup"><span data-stu-id="b4286-128">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="b4286-129">这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。</span><span class="sxs-lookup"><span data-stu-id="b4286-129">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="b4286-130">可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。</span><span class="sxs-lookup"><span data-stu-id="b4286-130">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="b4286-131">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="b4286-131">get_KeyEventLParam</span></span> 

<span data-ttu-id="b4286-132">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="b4286-132">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="b4286-133">公共 HRESULT [get_KeyEventLParam](#get_keyeventlparam)（INT \* lParam）</span><span class="sxs-lookup"><span data-stu-id="b4286-133">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="b4286-134">请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。</span><span class="sxs-lookup"><span data-stu-id="b4286-134">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="b4286-135">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="b4286-135">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="b4286-136">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="b4286-136">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="b4286-137">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)（WEBVIEW2_PHYSICAL_KEY_STATUS \* PhysicalKeyStatus）</span><span class="sxs-lookup"><span data-stu-id="b4286-137">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="b4286-138">满足</span><span class="sxs-lookup"><span data-stu-id="b4286-138">Handle</span></span> 

<span data-ttu-id="b4286-139">调用此操作将允许浏览器进程继续。</span><span class="sxs-lookup"><span data-stu-id="b4286-139">Calling this will allow the browser process to continue.</span></span>

> <span data-ttu-id="b4286-140">公共 HRESULT[句柄](#handle)（已处理 BOOL）</span><span class="sxs-lookup"><span data-stu-id="b4286-140">public HRESULT [Handle](#handle)(BOOL handled)</span></span>

<span data-ttu-id="b4286-141">传递 TRUE 将阻止浏览器对此加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="b4286-141">Passing TRUE will prevent the browser from performing the default action for this accelerator key.</span></span> <span data-ttu-id="b4286-142">如果事件处理程序返回时没有调用[句柄（）](#handle)，则它等效于调用句柄（FALSE）。</span><span class="sxs-lookup"><span data-stu-id="b4286-142">If the event handler returns without calling [Handle()](#handle), it is equivalent to calling Handle(FALSE).</span></span> <span data-ttu-id="b4286-143">调用[句柄（）](#handle)之后，或事件处理程序返回将不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b4286-143">Calling [Handle()](#handle) after it has already been called or the event handler has returned will do nothing.</span></span>

