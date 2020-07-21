---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 7cbf0b051b16e5905e81cfaf59907b337d843e46
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885415"
---
# <span data-ttu-id="09281-104">0.9.515-接口 ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="09281-104">0.9.515 - interface ICoreWebView2AcceleratorKeyPressedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="09281-105">AcceleratorKeyPressed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="09281-105">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="09281-106">摘要</span><span class="sxs-lookup"><span data-stu-id="09281-106">Summary</span></span>

 <span data-ttu-id="09281-107">成员</span><span class="sxs-lookup"><span data-stu-id="09281-107">Members</span></span>                        | <span data-ttu-id="09281-108">描述</span><span class="sxs-lookup"><span data-stu-id="09281-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="09281-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="09281-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="09281-110">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="09281-110">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="09281-111">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="09281-111">get_KeyEventKind</span></span>](#get_keyeventkind) | <span data-ttu-id="09281-112">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="09281-112">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="09281-113">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="09281-113">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="09281-114">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="09281-114">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="09281-115">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="09281-115">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="09281-116">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="09281-116">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="09281-117">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="09281-117">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="09281-118">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="09281-118">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="09281-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="09281-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="09281-120">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="09281-120">Sets the Handled property.</span></span>

## <span data-ttu-id="09281-121">成员</span><span class="sxs-lookup"><span data-stu-id="09281-121">Members</span></span>

#### <span data-ttu-id="09281-122">get_Handled</span><span class="sxs-lookup"><span data-stu-id="09281-122">get_Handled</span></span> 

<span data-ttu-id="09281-123">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="09281-123">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="09281-124">公共 HRESULT [get_Handled](#get_handled)（BOOL \* 已处理）</span><span class="sxs-lookup"><span data-stu-id="09281-124">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

<span data-ttu-id="09281-125">如果已处理的属性设置为 TRUE，则这将阻止 Web 视图对此加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="09281-125">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="09281-126">否则，Web 视图将对加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="09281-126">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="09281-127">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="09281-127">get_KeyEventKind</span></span> 

<span data-ttu-id="09281-128">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="09281-128">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="09281-129">public HRESULT [get_KeyEventKind](#get_keyeventkind)（COREWEBVIEW2_KEY_EVENT_KIND \* KeyEventKind）</span><span class="sxs-lookup"><span data-stu-id="09281-129">public HRESULT [get_KeyEventKind](#get_keyeventkind)(COREWEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span></span>

#### <span data-ttu-id="09281-130">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="09281-130">get_KeyEventLParam</span></span> 

<span data-ttu-id="09281-131">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="09281-131">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="09281-132">公共 HRESULT [get_KeyEventLParam](#get_keyeventlparam)（INT \* lParam）</span><span class="sxs-lookup"><span data-stu-id="09281-132">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="09281-133">请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。</span><span class="sxs-lookup"><span data-stu-id="09281-133">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="09281-134">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="09281-134">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="09281-135">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="09281-135">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="09281-136">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)（COREWEBVIEW2_PHYSICAL_KEY_STATUS \* PhysicalKeyStatus）</span><span class="sxs-lookup"><span data-stu-id="09281-136">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(COREWEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="09281-137">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="09281-137">get_VirtualKey</span></span> 

<span data-ttu-id="09281-138">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="09281-138">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="09281-139">public HRESULT [get_VirtualKey](#get_virtualkey)（UINT \* VirtualKey）</span><span class="sxs-lookup"><span data-stu-id="09281-139">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="09281-140">这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。</span><span class="sxs-lookup"><span data-stu-id="09281-140">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="09281-141">可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。</span><span class="sxs-lookup"><span data-stu-id="09281-141">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="09281-142">put_Handled</span><span class="sxs-lookup"><span data-stu-id="09281-142">put_Handled</span></span> 

<span data-ttu-id="09281-143">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="09281-143">Sets the Handled property.</span></span>

> <span data-ttu-id="09281-144">公共的 HRESULT [put_Handled](#put_handled)（BOOL 已处理）</span><span class="sxs-lookup"><span data-stu-id="09281-144">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

