---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 8aa715990b24c8364abae39b5c7abd2f148dc2c5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880834"
---
# <span data-ttu-id="ead1d-104">0.9.515-接口 ICoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="ead1d-104">0.9.515 - interface ICoreWebView2DevToolsProtocolEventReceiver</span></span> 

> [!NOTE]
> <span data-ttu-id="ead1d-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="ead1d-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="ead1d-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="ead1d-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DevToolsProtocolEventReceiver
  : public IUnknown
```

<span data-ttu-id="ead1d-107">将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。</span><span class="sxs-lookup"><span data-stu-id="ead1d-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="ead1d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="ead1d-108">Summary</span></span>

 <span data-ttu-id="ead1d-109">成员</span><span class="sxs-lookup"><span data-stu-id="ead1d-109">Members</span></span>                        | <span data-ttu-id="ead1d-110">描述</span><span class="sxs-lookup"><span data-stu-id="ead1d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ead1d-111">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="ead1d-111">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="ead1d-112">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="ead1d-112">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="ead1d-113">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="ead1d-113">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="ead1d-114">删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ead1d-114">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

<span data-ttu-id="ead1d-115">通过 GetDevToolsProtocolEventReceiver 从 Web 视图对象中获取。</span><span class="sxs-lookup"><span data-stu-id="ead1d-115">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="ead1d-116">成员</span><span class="sxs-lookup"><span data-stu-id="ead1d-116">Members</span></span>

#### <span data-ttu-id="ead1d-117">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="ead1d-117">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="ead1d-118">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="ead1d-118">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="ead1d-119">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)（[ICoreWebView2DevToolsProtocolEventReceivedEventHandler](icorewebview2devtoolsprotocoleventreceivedeventhandler.md) \* 处理程序，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="ead1d-119">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)([ICoreWebView2DevToolsProtocolEventReceivedEventHandler](icorewebview2devtoolsprotocoleventreceivedeventhandler.md) \* handler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="ead1d-120">每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="ead1d-120">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="ead1d-121">将使用包含 DevTools 协议事件参数对象的事件参数对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="ead1d-121">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

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

#### <span data-ttu-id="ead1d-122">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="ead1d-122">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="ead1d-123">删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ead1d-123">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="ead1d-124">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="ead1d-124">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(EventRegistrationToken token)</span></span>

