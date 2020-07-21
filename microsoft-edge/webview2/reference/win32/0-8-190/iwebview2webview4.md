---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebView4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 4e3fdc6283103833526f3c23e12796c78de77261
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884702"
---
# 0.8.355-接口 IWebView2WebView4 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView4
  : public IWebView2WebView3
```

由主 Web 视图对象实现的附加功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[AddRemoteObject](#addremoteobject) | 将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。
[RemoveRemoteObject](#removeremoteobject) | 删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。
[OpenDevToolsWindow](#opendevtoolswindow) | 在 Web 视图中打开当前文档的 DevTools 窗口。
[add_AcceleratorKeyPressed](#add_acceleratorkeypressed) | 为 AcceleratorKeyPressed 事件添加事件处理程序。
[remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed) | 删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。
[WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type) | 触发 AcceleratorKeyPressed 事件的键事件的类型。
[WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status) | 一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。

你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。 有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。

## 成员

#### AddRemoteObject 

将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。

> public HRESULT [AddRemoteObject](#addremoteobject)（LPCWSTR NAME，VARIANT * object）

通过将主机对象作为远程对象代理公开 `window.chrome.webview.remoteObjects.<name>` 。 远程对象代理承诺并将解析为表示主机对象的对象。 如果应用未添加具有名称的对象，则该承诺将被拒绝。 当 JavaScript 代码访问对象的属性或方法时，承诺将返回，它将解析为属性或方法从主机返回的值，或者在出现错误时被拒绝，例如在对象上没有此类属性或参数无效的情况下被拒绝。 例如，当应用程序代码执行以下操作时： 

```cpp
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddRemoteObject(L"host_object", &host);
```

 Web 视图中的 JavaScript 代码将能够按如下方式访问 appObject，然后访问 appObject 的属性和方法： 

```js
let app_object = await window.chrome.webview.remoteObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

 请注意，虽然简单类型、IDispatch 和数组受支持、泛型 IUnknown、VT_DECIMAL 或 VT_RECORD 变体不受支持。 远程 JavaScript 对象（如回调函数）使用实现 IDispatch 的对象表示为 VT_DISPATCH 变体。 可以使用 DISPID 的 DISPID_VALUE 调用 JavaScript 回调方法。 嵌套数组的支持深度为3。 不支持按引用类型的数组。 VT_EMPTY 和 VT_NULL 以 NULL 的形式映射到 JavaScript。 在 JavaScript null 中，未定义映射到 VT_EMPTY。

此外，所有远程对象均公开为 `window.chrome.webview.remoteObjects.sync.<name>` 。 此处的主机对象公开为同步远程对象代理。 这些不承诺且对函数或属性访问的调用会同步阻止正在等待通信的运行脚本，以便主机代码运行。 因此，可能会导致可靠性问题，建议使用上述基于承诺的异步 `window.chrome.webview.remoteObjects.<name>` API。

同步远程对象代理和异步远程对象代理都可以代理同一远程对象。 一个代理所做的远程更改将反映在该远程对象的任何其他代理中，无论其他代理和同步还是异步。

虽然 JavaScript 在对本机代码的同步调用上被阻止，但该本机代码无法回调到 JavaScript。 尝试执行此操作将失败，并 HRESULT_FROM_WIN32 （ERROR_POSSIBLE_DEADLOCK）。

远程对象代理是截取所有属性获取、属性集和方法调用的 JavaScript 代理对象。 作为函数或对象原型一部分的属性或方法在本地运行。 此外，数组中的任何属性或方法 `chrome.webview.remoteObjects.options.forceLocalProperties` 也将在本地运行。 这是默认设置，包括在 JavaScript 中具有含义的可选方法 `toJSON` ，如和 `Symbol.toPrimitive` 。 你可以根据需要向此数组添加更多。

有一种方法 `chrome.webview.remoteObjects.cleanupSome` 可以最大程度地垃圾回收远程对象代理。

远程对象代理还具有以下可在本地运行的方法：

* applyRemote、getRemote、setRemote：对远程对象执行方法调用、属性获取或属性设置。 如果存在冲突的本地方法或属性，则可以使用这些属性显式强制在远程运行某个方法或属性。 例如， `proxy.toString()` 将对代理对象运行本地 toString 方法。 而 `proxy.applyRemote('toString')` `toString` 是在远程代理对象上运行。

* getLocal，setLocal：执行属性 get 或本地设置属性。 可以使用这些方法强制在远程对象代理本身（而不是在它表示的远程对象）上获取或设置属性。 例如， `proxy.unknownProperty` 将获取 `unknownProperty` 从远程代理对象命名的属性。 但 `proxy.getLocal('unknownProperty')` 将获取 `unknownProperty` 代理对象本身的属性值。

* 同步：异步远程对象代理公开同步方法，该方法可为同一远程对象返回同步远程对象代理的承诺。 例如， `chrome.webview.remoteObjects.sample.methodCall()` 返回一个异步远程对象代理。 你可以改用此 `sync` 方法获取同步远程对象代理： `const syncProxy = await chrome.webview.remoteObjects.sample.methodCall().sync()`

* 异步：同步远程对象代理公开一个 async 方法，该方法会阻止并返回同一远程对象的异步远程对象代理。 例如， `chrome.webview.remoteObjects.sync.sample.methodCall()` 返回同步远程对象代理。 `async`在此块上调用该方法，然后返回同一远程对象的异步远程对象代理： `const asyncProxy = chrome.webview.remoteObjects.sync.sample.methodCall().async()`

* 然后：异步远程对象代理具有 then 方法。 这使它们能够可等待。 `then` 将返回使用远程对象的表示形式解析的承诺。 如果代理表示 JavaScript 文本，则会在本地返回一个副本。 如果代理表示一个函数，则返回非可等待代理。 如果代理表示的 JavaScript 对象混合了文本属性和函数属性，则会将某些属性作为远程对象代理返回该对象的副本。

所有其他属性和方法调用（除了上述远程对象代理方法、forceLocalProperties 列表和函数和对象原型上的属性）都是远程运行的。 异步远程对象代理返回表示异步完成调用该方法或获取属性的异步完成的承诺。 在远程操作完成后，承诺将解决该操作的结果值。 同步远程对象代理的工作方式类似，但阻止了 JavaScript 执行并等待远程操作完成。

在异步远程对象代理上设置属性的工作方式略有不同。 Set 将立即返回，返回值为将设置的值。 这是 JavaScript 代理对象的要求。 如果需要异步等待属性设置为 "完成"，请使用 setRemote 方法，该方法将返回上述承诺。 同步对象属性 set 属性在设置该属性之前同步地阻止。

例如，假设你有一个具有以下接口的 COM 对象

```idl
    [uuid(3a14c9c0-bc3e-453f-a314-4ce4a0ec81d8), object, local]
    interface IRemoteObjectSample : IUnknown
    {
        // Demonstrate basic method call with some parameters and a return value.
        HRESULT MethodWithParametersAndReturnValue([in] BSTR stringParameter, [in] INT integerParameter, [out, retval] BSTR* stringResult);

        // Demonstrate getting and setting a property.
        [propget] HRESULT Property([out, retval] BSTR* stringResult);
        [propput] HRESULT Property([in] BSTR stringValue);

        // Demonstrate native calling back into JavaScript.
        HRESULT CallCallbackAsynchronously([in] IDispatch* callbackParameter);
    };
```

 我们可以将此接口的实例添加到我们的 JavaScript 中 `AddRemoteObject` 。 在这种情况下，我们将其命名 `sample` 为：

```cpp
            VARIANT remoteObjectAsVariant = {};
            m_remoteObject.query_to<IDispatch>(&remoteObjectAsVariant.pdispVal);
            remoteObjectAsVariant.vt = VT_DISPATCH;

            // We can call AddRemoteObject multiple times in a row without
            // calling RemoveRemoteObject first. This will replace the previous object
            // with the new object. In our case this is the same object and everything
            // is fine.
            CHECK_FAILURE(m_webView->AddRemoteObject(L"sample", &remoteObjectAsVariant));
            remoteObjectAsVariant.pdispVal->Release();
```

 然后，在 HTML 文档中，我们可以通过以下方式使用该 COM 对象 `chrome.webview.remoteObjects.sample` ：

```js
        document.getElementById("getPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = await chrome.webview.remoteObjects.sample.property;
            document.getElementById("getPropertyAsyncOutput").textContent = propertyValue;
        });

        document.getElementById("getPropertySyncButton").addEventListener("click", () => {
            const propertyValue = chrome.webview.remoteObjects.sync.sample.property;
            document.getElementById("getPropertySyncOutput").textContent = propertyValue;
        });

        document.getElementById("setPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyAsyncInput").value;
            // The following line will work but it will return immediately before the property value has actually been set.
            // If you need to set the property and wait for the property to change value, use the setRemote function.
            chrome.webview.remoteObjects.sample.property = propertyValue;
            document.getElementById("setPropertyAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertyExplicitAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyExplicitAsyncInput").value;
            // If you care about waiting until the property has actually changed value use the setRemote function.
            await chrome.webview.remoteObjects.sample.setRemote("property", propertyValue);
            document.getElementById("setPropertyExplicitAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertySyncButton").addEventListener("click", () => {
            const propertyValue = document.getElementById("setPropertySyncInput").value;
            chrome.webview.remoteObjects.sync.sample.property = propertyValue;
            document.getElementById("setPropertySyncOutput").textContent = "Set";
        });

        document.getElementById("invokeMethodAsyncButton").addEventListener("click", async () => {
            const paramValue1 = document.getElementById("invokeMethodAsyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodAsyncParam2").value);
            const resultValue = await chrome.webview.remoteObjects.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodAsyncOutput").textContent = resultValue;
        });

        document.getElementById("invokeMethodSyncButton").addEventListener("click", () => {
            const paramValue1 = document.getElementById("invokeMethodSyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodSyncParam2").value);
            const resultValue = chrome.webview.remoteObjects.sync.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodSyncOutput").textContent = resultValue;
        });

        let callbackCount = 0;
        document.getElementById("invokeCallbackButton").addEventListener("click", async () => {
            chrome.webview.remoteObjects.sample.CallCallbackAsynchronously(() => {
                document.getElementById("invokeCallbackOutput").textContent = "Native object called the callback " + (++callbackCount) + " time(s).";
            });
        });
```

#### RemoveRemoteObject 

删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。

> 公共 HRESULT [RemoveRemoteObject](#removeremoteobject)（LPCWSTR name）

当新的访问尝试将被拒绝时，如果 Web 视图中的 JavaScript 代码已获得该对象，则 JavaScript 代码将继续具有对该对象的访问权限。 为已删除或从未添加的名称调用此方法将失败。

#### OpenDevToolsWindow 

在 Web 视图中打开当前文档的 DevTools 窗口。

> 公共 HRESULT [OpenDevToolsWindow](#opendevtoolswindow)（）

如果在 DevTools 窗口已打开时调用，则不执行任何操作

#### add_AcceleratorKeyPressed 

为 AcceleratorKeyPressed 事件添加事件处理程序。

> public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)（[IWebView2AcceleratorKeyPressedEventHandler](IWebView2AcceleratorKeyPressedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。 如果某个键出现以下情况之一，则将其视为一个加速器：

1. 按 Ctrl 或 Alt 当前正在保持，或者

1. 按下的键不会映射到字符。 一些特定的键永远不会被视为加速器，如 Shift。 转义键始终被视为加速键。

通过按住键导致的 Autorepeated 键事件也会引发此事件。 你可以通过检查事件参数 "KeyEventLParam" 或 "PhysicalKeyStatus" 来筛选这些问题。

在窗口模式下，此事件处理程序是同步调用的。 在事件参数或事件处理程序返回之前调用句柄（）之前，浏览器进程将被阻止，并且传出进程间 COM 调用将失败，并显示 RPC_E_CANTCALLOUT_ININPUTSYNCCALL。 但是，所有 WebView2 API 方法都有效。

在无窗口模式下，异步调用事件处理程序。 在调用事件处理程序返回或句柄（）时，将不会访问浏览器，但浏览器进程本身将不会被阻止，并且传出 COM 调用将正常工作。

建议你先调用句柄（TRUE），然后才能知道你希望处理加速键。

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_webView->add_AcceleratorKeyPressed(
        Callback<IWebView2AcceleratorKeyPressedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2AcceleratorKeyPressedEventArgs* args)
                -> HRESULT {
                WEBVIEW2_KEY_EVENT_TYPE type;
                CHECK_FAILURE(args->get_KeyEventType(&type));
                // We only care about key down events.
                if (type == WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN ||
                    type == WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN)
                {
                    UINT key;
                    CHECK_FAILURE(args->get_VirtualKey(&key));
                    // Check if the key is one we want to handle.
                    if (std::function<void()> action =
                            m_appWindow->GetAcceleratorKeyFunction(key))
                    {
                        // Keep the browser from handling this key, whether it's autorepeated or
                        // not.
                        CHECK_FAILURE(args->Handle(TRUE));

                        // Filter out autorepeated keys.
                        WEBVIEW2_PHYSICAL_KEY_STATUS status;
                        CHECK_FAILURE(args->get_PhysicalKeyStatus(&status));
                        if (!status.WasKeyDown)
                        {
                            // Perform the action asynchronously to avoid blocking the
                            // browser process's event queue.
                            m_appWindow->RunAsync(action);
                        }
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_acceleratorKeyPressedToken));
```

#### remove_AcceleratorKeyPressed 

删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。

> public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)（EventRegistrationToken 标记）

#### WEBVIEW2_KEY_EVENT_TYPE 

触发 AcceleratorKeyPressed 事件的键事件的类型。

> 枚举[WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN            | 对应于窗口消息 WM_KEYDOWN。
WEBVIEW2_KEY_EVENT_TYPE_KEY_UP            | 对应于窗口消息 WM_KEYUP。
WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN            | 对应于窗口消息 WM_SYSKEYDOWN。
WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP            | 对应于窗口消息 WM_SYSKEYUP。

#### WEBVIEW2_PHYSICAL_KEY_STATUS 

一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。

> typedef [WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status)

有关详细信息，请参阅 WM_KEYDOWN 的文档[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)

