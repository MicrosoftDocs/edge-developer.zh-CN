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
ms.openlocfilehash: 6ebed9e61bf7eda60e6e16b7a417306baa5d07bf
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652805"
---
# <span data-ttu-id="444da-104">interface IWebView2WebView4</span><span class="sxs-lookup"><span data-stu-id="444da-104">interface IWebView2WebView4</span></span> 

> [!NOTE]
> <span data-ttu-id="444da-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="444da-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="444da-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="444da-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView4
  : public IWebView2WebView3
```

<span data-ttu-id="444da-107">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="444da-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="444da-108">摘要</span><span class="sxs-lookup"><span data-stu-id="444da-108">Summary</span></span>

 <span data-ttu-id="444da-109">成员</span><span class="sxs-lookup"><span data-stu-id="444da-109">Members</span></span>                        | <span data-ttu-id="444da-110">描述</span><span class="sxs-lookup"><span data-stu-id="444da-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="444da-111">AddRemoteObject</span><span class="sxs-lookup"><span data-stu-id="444da-111">AddRemoteObject</span></span>](#addremoteobject) | <span data-ttu-id="444da-112">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="444da-112">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="444da-113">RemoveRemoteObject</span><span class="sxs-lookup"><span data-stu-id="444da-113">RemoveRemoteObject</span></span>](#removeremoteobject) | <span data-ttu-id="444da-114">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="444da-114">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="444da-115">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="444da-115">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="444da-116">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="444da-116">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="444da-117">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="444da-117">add_AcceleratorKeyPressed</span></span>](#add_acceleratorkeypressed) | <span data-ttu-id="444da-118">为 AcceleratorKeyPressed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="444da-118">Add an event handler for the AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="444da-119">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="444da-119">remove_AcceleratorKeyPressed</span></span>](#remove_acceleratorkeypressed) | <span data-ttu-id="444da-120">删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="444da-120">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>
[<span data-ttu-id="444da-121">WEBVIEW2_KEY_EVENT_TYPE</span><span class="sxs-lookup"><span data-stu-id="444da-121">WEBVIEW2_KEY_EVENT_TYPE</span></span>](#webview2_key_event_type) | <span data-ttu-id="444da-122">触发 AcceleratorKeyPressed 事件的键事件的类型。</span><span class="sxs-lookup"><span data-stu-id="444da-122">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="444da-123">WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="444da-123">WEBVIEW2_PHYSICAL_KEY_STATUS</span></span>](#webview2_physical_key_status) | <span data-ttu-id="444da-124">一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。</span><span class="sxs-lookup"><span data-stu-id="444da-124">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

<span data-ttu-id="444da-125">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="444da-125">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="444da-126">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="444da-126">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="444da-127">成员</span><span class="sxs-lookup"><span data-stu-id="444da-127">Members</span></span>

#### <span data-ttu-id="444da-128">AddRemoteObject</span><span class="sxs-lookup"><span data-stu-id="444da-128">AddRemoteObject</span></span> 

<span data-ttu-id="444da-129">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="444da-129">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="444da-130">public HRESULT [AddRemoteObject](#addremoteobject)（LPCWSTR NAME，VARIANT \* object）</span><span class="sxs-lookup"><span data-stu-id="444da-130">public HRESULT [AddRemoteObject](#addremoteobject)(LPCWSTR name,VARIANT \* object)</span></span>

<span data-ttu-id="444da-131">通过将主机对象作为远程对象代理公开 `window.chrome.webview.remoteObjects.<name>` 。</span><span class="sxs-lookup"><span data-stu-id="444da-131">Host objects are exposed as remote object proxies via `window.chrome.webview.remoteObjects.<name>`.</span></span> <span data-ttu-id="444da-132">远程对象代理承诺并将解析为表示主机对象的对象。</span><span class="sxs-lookup"><span data-stu-id="444da-132">Remote object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="444da-133">如果应用未添加具有名称的对象，则该承诺将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="444da-133">The promise is rejected if the app has not added an object with the name.</span></span> <span data-ttu-id="444da-134">当 JavaScript 代码访问对象的属性或方法时，承诺将返回，它将解析为属性或方法从主机返回的值，或者在出现错误时被拒绝，例如在对象上没有此类属性或参数无效的情况下被拒绝。</span><span class="sxs-lookup"><span data-stu-id="444da-134">When JavaScript code access a property or method of the object, a promise is return, which will resolve to the value returned from the host for the property or method, or rejected in case of error such as there is no such property or method on the object or parameters are invalid.</span></span> <span data-ttu-id="444da-135">例如，当应用程序代码执行以下操作时：</span><span class="sxs-lookup"><span data-stu-id="444da-135">For example, when the application code does the following:</span></span> 

```cpp
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddRemoteObject(L"host_object", &host);
```

 <span data-ttu-id="444da-136">Web 视图中的 JavaScript 代码将能够按如下方式访问 appObject，然后访问 appObject 的属性和方法：</span><span class="sxs-lookup"><span data-stu-id="444da-136">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject:</span></span> 

```js
let app_object = await window.chrome.webview.remoteObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

 <span data-ttu-id="444da-137">请注意，虽然简单类型、IDispatch 和数组受支持、泛型 IUnknown、VT_DECIMAL 或 VT_RECORD 变体不受支持。</span><span class="sxs-lookup"><span data-stu-id="444da-137">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="444da-138">远程 JavaScript 对象（如回调函数）使用实现 IDispatch 的对象表示为 VT_DISPATCH 变体。</span><span class="sxs-lookup"><span data-stu-id="444da-138">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="444da-139">可以使用 DISPID 的 DISPID_VALUE 调用 JavaScript 回调方法。</span><span class="sxs-lookup"><span data-stu-id="444da-139">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="444da-140">嵌套数组的支持深度为3。</span><span class="sxs-lookup"><span data-stu-id="444da-140">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="444da-141">不支持按引用类型的数组。</span><span class="sxs-lookup"><span data-stu-id="444da-141">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="444da-142">VT_EMPTY 和 VT_NULL 以 NULL 的形式映射到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="444da-142">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="444da-143">在 JavaScript null 中，未定义映射到 VT_EMPTY。</span><span class="sxs-lookup"><span data-stu-id="444da-143">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="444da-144">此外，所有远程对象均公开为 `window.chrome.webview.remoteObjects.sync.<name>` 。</span><span class="sxs-lookup"><span data-stu-id="444da-144">Additionally, all remote objects are exposed as `window.chrome.webview.remoteObjects.sync.<name>`.</span></span> <span data-ttu-id="444da-145">此处的主机对象公开为同步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="444da-145">Here the host objects are exposed as synchronous remote object proxies.</span></span> <span data-ttu-id="444da-146">这些不承诺且对函数或属性访问的调用会同步阻止正在等待通信的运行脚本，以便主机代码运行。</span><span class="sxs-lookup"><span data-stu-id="444da-146">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="444da-147">因此，可能会导致可靠性问题，建议使用上述基于承诺的异步 `window.chrome.webview.remoteObjects.<name>` API。</span><span class="sxs-lookup"><span data-stu-id="444da-147">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.remoteObjects.<name>` API described above.</span></span>

<span data-ttu-id="444da-148">同步远程对象代理和异步远程对象代理都可以代理同一远程对象。</span><span class="sxs-lookup"><span data-stu-id="444da-148">Synchronous remote object proxies and asynchronous remote object proxies can both proxy the same remote object.</span></span> <span data-ttu-id="444da-149">一个代理所做的远程更改将反映在该远程对象的任何其他代理中，无论其他代理和同步还是异步。</span><span class="sxs-lookup"><span data-stu-id="444da-149">Remote changes made by one proxy will be reflected in any other proxy of that same remote object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="444da-150">虽然 JavaScript 在对本机代码的同步调用上被阻止，但该本机代码无法回调到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="444da-150">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="444da-151">尝试执行此操作将失败，并 HRESULT_FROM_WIN32 （ERROR_POSSIBLE_DEADLOCK）。</span><span class="sxs-lookup"><span data-stu-id="444da-151">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="444da-152">远程对象代理是截取所有属性获取、属性集和方法调用的 JavaScript 代理对象。</span><span class="sxs-lookup"><span data-stu-id="444da-152">Remote object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="444da-153">作为函数或对象原型一部分的属性或方法在本地运行。</span><span class="sxs-lookup"><span data-stu-id="444da-153">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="444da-154">此外，数组中的任何属性或方法 `chrome.webview.remoteObjects.options.forceLocalProperties` 也将在本地运行。</span><span class="sxs-lookup"><span data-stu-id="444da-154">Additionally any property or method in the array `chrome.webview.remoteObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="444da-155">这是默认设置，包括在 JavaScript 中具有含义的可选方法 `toJSON` ，如和 `Symbol.toPrimitive` 。</span><span class="sxs-lookup"><span data-stu-id="444da-155">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="444da-156">你可以根据需要向此数组添加更多。</span><span class="sxs-lookup"><span data-stu-id="444da-156">You can add more to this array as required.</span></span>

<span data-ttu-id="444da-157">有一种方法 `chrome.webview.remoteObjects.cleanupSome` 可以最大程度地垃圾回收远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="444da-157">There's a method `chrome.webview.remoteObjects.cleanupSome` that will best effort garbage collect remote object proxies.</span></span>

<span data-ttu-id="444da-158">远程对象代理还具有以下可在本地运行的方法：</span><span class="sxs-lookup"><span data-stu-id="444da-158">Remote object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="444da-159">applyRemote、getRemote、setRemote：对远程对象执行方法调用、属性获取或属性设置。</span><span class="sxs-lookup"><span data-stu-id="444da-159">applyRemote, getRemote, setRemote: Perform a method invocation, property get, or property set on the remote object.</span></span> <span data-ttu-id="444da-160">如果存在冲突的本地方法或属性，则可以使用这些属性显式强制在远程运行某个方法或属性。</span><span class="sxs-lookup"><span data-stu-id="444da-160">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="444da-161">例如， `proxy.toString()` 将对代理对象运行本地 toString 方法。</span><span class="sxs-lookup"><span data-stu-id="444da-161">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="444da-162">而 `proxy.applyRemote('toString')` `toString` 是在远程代理对象上运行。</span><span class="sxs-lookup"><span data-stu-id="444da-162">But `proxy.applyRemote('toString')` runs `toString` on the remote proxied object instead.</span></span>

* <span data-ttu-id="444da-163">getLocal，setLocal：执行属性 get 或本地设置属性。</span><span class="sxs-lookup"><span data-stu-id="444da-163">getLocal, setLocal: Perform property get, or property set locally.</span></span> <span data-ttu-id="444da-164">可以使用这些方法强制在远程对象代理本身（而不是在它表示的远程对象）上获取或设置属性。</span><span class="sxs-lookup"><span data-stu-id="444da-164">You can use these methods to force getting or setting a property on the remote object proxy itself rather than on the remote object it represents.</span></span> <span data-ttu-id="444da-165">例如， `proxy.unknownProperty` 将获取 `unknownProperty` 从远程代理对象命名的属性。</span><span class="sxs-lookup"><span data-stu-id="444da-165">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the remote proxied object.</span></span> <span data-ttu-id="444da-166">但 `proxy.getLocal('unknownProperty')` 将获取 `unknownProperty` 代理对象本身的属性值。</span><span class="sxs-lookup"><span data-stu-id="444da-166">But `proxy.getLocal('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="444da-167">同步：异步远程对象代理公开同步方法，该方法可为同一远程对象返回同步远程对象代理的承诺。</span><span class="sxs-lookup"><span data-stu-id="444da-167">sync: Asynchronous remote object proxies expose a sync method which returns a promise for a synchronous remote object proxy for the same remote object.</span></span> <span data-ttu-id="444da-168">例如， `chrome.webview.remoteObjects.sample.methodCall()` 返回一个异步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="444da-168">For example, `chrome.webview.remoteObjects.sample.methodCall()` returns an asynchronous remote object proxy.</span></span> <span data-ttu-id="444da-169">你可以改用此 `sync` 方法获取同步远程对象代理：</span><span class="sxs-lookup"><span data-stu-id="444da-169">You can use the `sync` method to obtain a synchronous remote object proxy instead:</span></span> `const syncProxy = await chrome.webview.remoteObjects.sample.methodCall().sync()`

* <span data-ttu-id="444da-170">异步：同步远程对象代理公开一个 async 方法，该方法会阻止并返回同一远程对象的异步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="444da-170">async: Synchronous remote object proxies expose an async method which blocks and returns an asynchronous remote object proxy for the same remote object.</span></span> <span data-ttu-id="444da-171">例如， `chrome.webview.remoteObjects.sync.sample.methodCall()` 返回同步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="444da-171">For example, `chrome.webview.remoteObjects.sync.sample.methodCall()` returns a synchronous remote object proxy.</span></span> <span data-ttu-id="444da-172">`async`在此块上调用该方法，然后返回同一远程对象的异步远程对象代理：</span><span class="sxs-lookup"><span data-stu-id="444da-172">Calling the `async` method on this blocks and then returns an asynchronous remote object proxy for the same remote object:</span></span> `const asyncProxy = chrome.webview.remoteObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="444da-173">然后：异步远程对象代理具有 then 方法。</span><span class="sxs-lookup"><span data-stu-id="444da-173">then: Asynchronous remote object proxies have a then method.</span></span> <span data-ttu-id="444da-174">这使它们能够可等待。</span><span class="sxs-lookup"><span data-stu-id="444da-174">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="444da-175">将返回使用远程对象的表示形式解析的承诺。</span><span class="sxs-lookup"><span data-stu-id="444da-175">will return a promise that resolves with a representation of the remote object.</span></span> <span data-ttu-id="444da-176">如果代理表示 JavaScript 文本，则会在本地返回一个副本。</span><span class="sxs-lookup"><span data-stu-id="444da-176">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="444da-177">如果代理表示一个函数，则返回非可等待代理。</span><span class="sxs-lookup"><span data-stu-id="444da-177">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="444da-178">如果代理表示的 JavaScript 对象混合了文本属性和函数属性，则会将某些属性作为远程对象代理返回该对象的副本。</span><span class="sxs-lookup"><span data-stu-id="444da-178">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as remote object proxies.</span></span>

<span data-ttu-id="444da-179">所有其他属性和方法调用（除了上述远程对象代理方法、forceLocalProperties 列表和函数和对象原型上的属性）都是远程运行的。</span><span class="sxs-lookup"><span data-stu-id="444da-179">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="444da-180">异步远程对象代理返回表示异步完成调用该方法或获取属性的异步完成的承诺。</span><span class="sxs-lookup"><span data-stu-id="444da-180">Asynchronous remote object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="444da-181">在远程操作完成后，承诺将解决该操作的结果值。</span><span class="sxs-lookup"><span data-stu-id="444da-181">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="444da-182">同步远程对象代理的工作方式类似，但阻止了 JavaScript 执行并等待远程操作完成。</span><span class="sxs-lookup"><span data-stu-id="444da-182">Synchronous remote object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="444da-183">在异步远程对象代理上设置属性的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="444da-183">Setting a property on an asynchronous remote object proxy works slightly differently.</span></span> <span data-ttu-id="444da-184">Set 将立即返回，返回值为将设置的值。</span><span class="sxs-lookup"><span data-stu-id="444da-184">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="444da-185">这是 JavaScript 代理对象的要求。</span><span class="sxs-lookup"><span data-stu-id="444da-185">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="444da-186">如果需要异步等待属性设置为 "完成"，请使用 setRemote 方法，该方法将返回上述承诺。</span><span class="sxs-lookup"><span data-stu-id="444da-186">If you need to asynchronously wait for the property set to complete, use the setRemote method which returns a promise as described above.</span></span> <span data-ttu-id="444da-187">同步对象属性 set 属性在设置该属性之前同步地阻止。</span><span class="sxs-lookup"><span data-stu-id="444da-187">Synchronous object property set property synchronously blocks until the property is set.</span></span>

<span data-ttu-id="444da-188">例如，假设你有一个具有以下接口的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="444da-188">For example, suppose you have a COM object with the following interface</span></span>

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

 <span data-ttu-id="444da-189">我们可以将此接口的实例添加到我们的 JavaScript 中 `AddRemoteObject` 。</span><span class="sxs-lookup"><span data-stu-id="444da-189">We can add an instance of this interface into our JavaScript with `AddRemoteObject`.</span></span> <span data-ttu-id="444da-190">在这种情况下，我们将其命名 `sample` 为：</span><span class="sxs-lookup"><span data-stu-id="444da-190">In this case we name it `sample`:</span></span>

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

 <span data-ttu-id="444da-191">然后，在 HTML 文档中，我们可以通过以下方式使用该 COM 对象 `chrome.webview.remoteObjects.sample` ：</span><span class="sxs-lookup"><span data-stu-id="444da-191">Then in the HTML document we can use this COM object via `chrome.webview.remoteObjects.sample`:</span></span>

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

#### <span data-ttu-id="444da-192">RemoveRemoteObject</span><span class="sxs-lookup"><span data-stu-id="444da-192">RemoveRemoteObject</span></span> 

<span data-ttu-id="444da-193">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="444da-193">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="444da-194">公共 HRESULT [RemoveRemoteObject](#removeremoteobject)（LPCWSTR name）</span><span class="sxs-lookup"><span data-stu-id="444da-194">public HRESULT [RemoveRemoteObject](#removeremoteobject)(LPCWSTR name)</span></span>

<span data-ttu-id="444da-195">当新的访问尝试将被拒绝时，如果 Web 视图中的 JavaScript 代码已获得该对象，则 JavaScript 代码将继续具有对该对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="444da-195">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="444da-196">为已删除或从未添加的名称调用此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="444da-196">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="444da-197">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="444da-197">OpenDevToolsWindow</span></span> 

<span data-ttu-id="444da-198">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="444da-198">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="444da-199">公共 HRESULT [OpenDevToolsWindow](#opendevtoolswindow)（）</span><span class="sxs-lookup"><span data-stu-id="444da-199">public HRESULT [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="444da-200">如果在 DevTools 窗口已打开时调用，则不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="444da-200">Does nothing if called when the DevTools window is already open</span></span>

#### <span data-ttu-id="444da-201">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="444da-201">add_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="444da-202">为 AcceleratorKeyPressed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="444da-202">Add an event handler for the AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="444da-203">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)（[IWebView2AcceleratorKeyPressedEventHandler](IWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="444da-203">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([IWebView2AcceleratorKeyPressedEventHandler](IWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="444da-204">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="444da-204">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="444da-205">如果某个键出现以下情况之一，则将其视为一个加速器：</span><span class="sxs-lookup"><span data-stu-id="444da-205">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="444da-206">按 Ctrl 或 Alt 当前正在保持，或者</span><span class="sxs-lookup"><span data-stu-id="444da-206">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="444da-207">按下的键不会映射到字符。</span><span class="sxs-lookup"><span data-stu-id="444da-207">the pressed key does not map to a character.</span></span> <span data-ttu-id="444da-208">一些特定的键永远不会被视为加速器，如 Shift。</span><span class="sxs-lookup"><span data-stu-id="444da-208">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="444da-209">转义键始终被视为加速键。</span><span class="sxs-lookup"><span data-stu-id="444da-209">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="444da-210">通过按住键导致的 Autorepeated 键事件也会引发此事件。</span><span class="sxs-lookup"><span data-stu-id="444da-210">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="444da-211">你可以通过检查事件参数 "KeyEventLParam" 或 "PhysicalKeyStatus" 来筛选这些问题。</span><span class="sxs-lookup"><span data-stu-id="444da-211">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="444da-212">在窗口模式下，此事件处理程序是同步调用的。</span><span class="sxs-lookup"><span data-stu-id="444da-212">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="444da-213">在事件参数或事件处理程序返回之前调用句柄（）之前，浏览器进程将被阻止，并且传出进程间 COM 调用将失败，并显示 RPC_E_CANTCALLOUT_ININPUTSYNCCALL。</span><span class="sxs-lookup"><span data-stu-id="444da-213">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="444da-214">但是，所有 WebView2 API 方法都有效。</span><span class="sxs-lookup"><span data-stu-id="444da-214">All WebView2 API methods will work, however.</span></span>

<span data-ttu-id="444da-215">在无窗口模式下，异步调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="444da-215">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="444da-216">在调用事件处理程序返回或句柄（）时，将不会访问浏览器，但浏览器进程本身将不会被阻止，并且传出 COM 调用将正常工作。</span><span class="sxs-lookup"><span data-stu-id="444da-216">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="444da-217">建议你先调用句柄（TRUE），然后才能知道你希望处理加速键。</span><span class="sxs-lookup"><span data-stu-id="444da-217">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

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

#### <span data-ttu-id="444da-218">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="444da-218">remove_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="444da-219">删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="444da-219">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>

> <span data-ttu-id="444da-220">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="444da-220">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="444da-221">WEBVIEW2_KEY_EVENT_TYPE</span><span class="sxs-lookup"><span data-stu-id="444da-221">WEBVIEW2_KEY_EVENT_TYPE</span></span> 

<span data-ttu-id="444da-222">触发 AcceleratorKeyPressed 事件的键事件的类型。</span><span class="sxs-lookup"><span data-stu-id="444da-222">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="444da-223">枚举[WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type)</span><span class="sxs-lookup"><span data-stu-id="444da-223">enum [WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type)</span></span>

 <span data-ttu-id="444da-224">值</span><span class="sxs-lookup"><span data-stu-id="444da-224">Values</span></span>                         | <span data-ttu-id="444da-225">描述</span><span class="sxs-lookup"><span data-stu-id="444da-225">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="444da-226">WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="444da-226">WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN</span></span>            | <span data-ttu-id="444da-227">对应于窗口消息 WM_KEYDOWN。</span><span class="sxs-lookup"><span data-stu-id="444da-227">Correspond to window message WM_KEYDOWN.</span></span>
<span data-ttu-id="444da-228">WEBVIEW2_KEY_EVENT_TYPE_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="444da-228">WEBVIEW2_KEY_EVENT_TYPE_KEY_UP</span></span>            | <span data-ttu-id="444da-229">对应于窗口消息 WM_KEYUP。</span><span class="sxs-lookup"><span data-stu-id="444da-229">Correspond to window message WM_KEYUP.</span></span>
<span data-ttu-id="444da-230">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="444da-230">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN</span></span>            | <span data-ttu-id="444da-231">对应于窗口消息 WM_SYSKEYDOWN。</span><span class="sxs-lookup"><span data-stu-id="444da-231">Correspond to window message WM_SYSKEYDOWN.</span></span>
<span data-ttu-id="444da-232">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="444da-232">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP</span></span>            | <span data-ttu-id="444da-233">对应于窗口消息 WM_SYSKEYUP。</span><span class="sxs-lookup"><span data-stu-id="444da-233">Correspond to window message WM_SYSKEYUP.</span></span>

#### <span data-ttu-id="444da-234">WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="444da-234">WEBVIEW2_PHYSICAL_KEY_STATUS</span></span> 

<span data-ttu-id="444da-235">一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。</span><span class="sxs-lookup"><span data-stu-id="444da-235">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

> <span data-ttu-id="444da-236">typedef [WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status)</span><span class="sxs-lookup"><span data-stu-id="444da-236">typedef [WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status)</span></span>

<span data-ttu-id="444da-237">有关详细信息，请参阅 WM_KEYDOWN 的文档[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span><span class="sxs-lookup"><span data-stu-id="444da-237">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span></span>

