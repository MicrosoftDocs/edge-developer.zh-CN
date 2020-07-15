---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: e7a512201c1ef7917a54b93dbd06587294e76f78
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881177"
---
# <span data-ttu-id="5d938-104">0.9.430-接口 ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="5d938-104">0.9.430 - interface ICoreWebView2AcceleratorKeyPressedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="5d938-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="5d938-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="5d938-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="5d938-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="5d938-107">AcceleratorKeyPressed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5d938-107">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="5d938-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5d938-108">Summary</span></span>

 <span data-ttu-id="5d938-109">成员</span><span class="sxs-lookup"><span data-stu-id="5d938-109">Members</span></span>                        | <span data-ttu-id="5d938-110">描述</span><span class="sxs-lookup"><span data-stu-id="5d938-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5d938-111">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="5d938-111">get_KeyEventKind</span></span>](#get_keyeventkind) | <span data-ttu-id="5d938-112">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="5d938-112">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="5d938-113">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="5d938-113">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="5d938-114">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="5d938-114">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="5d938-115">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="5d938-115">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="5d938-116">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="5d938-116">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="5d938-117">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="5d938-117">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="5d938-118">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="5d938-118">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="5d938-119">get_Handled</span><span class="sxs-lookup"><span data-stu-id="5d938-119">get_Handled</span></span>](#get_handled) | <span data-ttu-id="5d938-120">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="5d938-120">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="5d938-121">put_Handled</span><span class="sxs-lookup"><span data-stu-id="5d938-121">put_Handled</span></span>](#put_handled) | <span data-ttu-id="5d938-122">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="5d938-122">Sets the Handled property.</span></span>

## <span data-ttu-id="5d938-123">成员</span><span class="sxs-lookup"><span data-stu-id="5d938-123">Members</span></span>

#### <span data-ttu-id="5d938-124">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="5d938-124">get_KeyEventKind</span></span> 

<span data-ttu-id="5d938-125">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="5d938-125">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="5d938-126">public HRESULT [get_KeyEventKind](#get_keyeventkind)（CORE_WEBVIEW2_KEY_EVENT_KIND \* KeyEventKind）</span><span class="sxs-lookup"><span data-stu-id="5d938-126">public HRESULT [get_KeyEventKind](#get_keyeventkind)(CORE_WEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span></span>

#### <span data-ttu-id="5d938-127">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="5d938-127">get_VirtualKey</span></span> 

<span data-ttu-id="5d938-128">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="5d938-128">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="5d938-129">public HRESULT [get_VirtualKey](#get_virtualkey)（UINT \* VirtualKey）</span><span class="sxs-lookup"><span data-stu-id="5d938-129">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="5d938-130">这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。</span><span class="sxs-lookup"><span data-stu-id="5d938-130">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="5d938-131">可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。</span><span class="sxs-lookup"><span data-stu-id="5d938-131">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="5d938-132">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="5d938-132">get_KeyEventLParam</span></span> 

<span data-ttu-id="5d938-133">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="5d938-133">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="5d938-134">公共 HRESULT [get_KeyEventLParam](#get_keyeventlparam)（INT \* lParam）</span><span class="sxs-lookup"><span data-stu-id="5d938-134">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="5d938-135">请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。</span><span class="sxs-lookup"><span data-stu-id="5d938-135">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="5d938-136">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="5d938-136">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="5d938-137">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="5d938-137">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="5d938-138">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)（CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* PhysicalKeyStatus）</span><span class="sxs-lookup"><span data-stu-id="5d938-138">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="5d938-139">get_Handled</span><span class="sxs-lookup"><span data-stu-id="5d938-139">get_Handled</span></span> 

<span data-ttu-id="5d938-140">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="5d938-140">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="5d938-141">公共 HRESULT [get_Handled](#get_handled)（BOOL \* 已处理）</span><span class="sxs-lookup"><span data-stu-id="5d938-141">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

<span data-ttu-id="5d938-142">如果已处理的属性设置为 TRUE，则这将阻止 Web 视图对此加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="5d938-142">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="5d938-143">否则，Web 视图将对加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="5d938-143">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="5d938-144">put_Handled</span><span class="sxs-lookup"><span data-stu-id="5d938-144">put_Handled</span></span> 

<span data-ttu-id="5d938-145">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="5d938-145">Sets the Handled property.</span></span>

> <span data-ttu-id="5d938-146">公共的 HRESULT [put_Handled](#put_handled)（BOOL 已处理）</span><span class="sxs-lookup"><span data-stu-id="5d938-146">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

