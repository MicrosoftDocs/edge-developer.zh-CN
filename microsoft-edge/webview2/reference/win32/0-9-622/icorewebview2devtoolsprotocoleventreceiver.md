---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2DevToolsProtocolEventReceiver
ms.openlocfilehash: 6b3d6170d84f5e968121f90e1eebe5daf532f03d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011624"
---
# <span data-ttu-id="7c2b5-104">interface ICoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="7c2b5-104">interface ICoreWebView2DevToolsProtocolEventReceiver</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceiver
  : public IUnknown
```

<span data-ttu-id="7c2b5-105">将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-105">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="7c2b5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="7c2b5-106">Summary</span></span>

 <span data-ttu-id="7c2b5-107">成员</span><span class="sxs-lookup"><span data-stu-id="7c2b5-107">Members</span></span>                        | <span data-ttu-id="7c2b5-108">描述</span><span class="sxs-lookup"><span data-stu-id="7c2b5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7c2b5-109">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="7c2b5-109">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="7c2b5-110">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-110">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="7c2b5-111">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="7c2b5-111">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="7c2b5-112">删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-112">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

<span data-ttu-id="7c2b5-113">通过 GetDevToolsProtocolEventReceiver 从 Web 视图对象中获取。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="7c2b5-114">成员</span><span class="sxs-lookup"><span data-stu-id="7c2b5-114">Members</span></span>

#### <span data-ttu-id="7c2b5-115">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="7c2b5-115">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="7c2b5-116">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="7c2b5-117">公共 HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived) ([ICoreWebView2DevToolsProtocolEventReceivedEventHandler](icorewebview2devtoolsprotocoleventreceivedeventhandler.md) \* 处理程序、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="7c2b5-117">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)([ICoreWebView2DevToolsProtocolEventReceivedEventHandler](icorewebview2devtoolsprotocoleventreceivedeventhandler.md) \* handler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="7c2b5-118">每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="7c2b5-119">将调用一个事件参数对象，该对象包含将 DevTools 协议事件的参数对象作为 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-119">Invoke will be called with an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        wil::com_ptr<ICoreWebView2DevToolsProtocolEventReceiver> receiver;
        CHECK_FAILURE(
            m_webView->GetDevToolsProtocolEventReceiver(eventName.c_str(), &receiver));

        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(receiver->remove_DevToolsProtocolEventReceived(
                preexistingToken->second));
        }

        CHECK_FAILURE(receiver->add_DevToolsProtocolEventReceived(
            Callback<ICoreWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](
                    ICoreWebView2* sender,
                    ICoreWebView2DevToolsProtocolEventReceivedEventArgs* args) -> HRESULT {
                    wil::unique_cotaskmem_string parameterObjectAsJson;
                    CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
                    MessageBox(
                        nullptr, parameterObjectAsJson.get(),
                        (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
                    return S_OK;
                })
                .Get(),
            &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="7c2b5-120">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="7c2b5-120">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="7c2b5-121">删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-121">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="7c2b5-122">公共 HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="7c2b5-122">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(EventRegistrationToken token)</span></span>

