---
description: 使用基于标准的 Chakra JavaScript 引擎将脚本功能添加到你的 Windows 应用程序。
title: 托管 JavaScript 运行时
ms.date: 06/18/2020
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 30ec744e-57cc-4ef5-8fe1-d2c27b946548
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
ms.openlocfilehash: 043f7ecd174515ce407d2fc0c2bbe796fa2750a5
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752246"
---
# 托管 JavaScript 运行时  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

JavaScript 运行时（JsRT） Api 为 Windows 操作系统上运行的桌面、Windows 应用商店和服务器端应用程序提供了一种方法，可通过使用 Microsoft Edge 和 Internet Explorer 也使用的基于标准的 Chakra JavaScript 引擎向应用程序添加脚本功能。 这些 Api 可在 Windows 10 和安装了计算机上安装了 Internet Explorer 版本11.0 的任何 Windows 操作系统版本上使用。 有关详细信息，请参阅[参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)。 有关在 Windows 应用商店应用中使用 JsRT 的信息，请参阅[JsRT 和通用 Windows 平台](#Windows)。  

> [!NOTE]
> 本文档假定你对 JavaScript 语言的常规处理非常熟悉。  

## 概念  

了解如何使用 JsRT Api 托管 JavaScript 引擎取决于两个关键概念：运行时和执行上下文。  

*运行时*表示一个完整的 JavaScript 执行环境。 每个创建的运行时都具有其自己的独立垃圾回收堆，并且默认情况下，它自己的实时（JIT）编译器线程和垃圾回收器（GC）线程。 *执行上下文*表示具有其自己的 javascript 全局对象与所有其他执行上下文不同的 javascript 环境。 一个运行时可能包含多个执行上下文，在这种情况下，所有执行上下文都共享与运行时关联的 JIT 编译器和 GC 线程。  

运行时表示单个执行线程。 一次只能有一个运行时在特定线程上处于活动状态，并且运行时一次只能在一个线程上处于活动状态。 运行时是租赁线程，因此线程上当前未处于活动状态的运行时（即未运行任何 JavaScript 代码或对来自主机的任何调用的响应）可用于在其上尚未有活动运行时的任何线程。  

执行上下文绑定到特定运行时并在该运行时中执行代码。 与运行时不同，多个执行上下文可以同时在一个线程上处于活动状态。 因此，主机可以将调用转换为执行上下文，该执行上下文可以回调到主机，并且主机可以将调用转换为不同的执行上下文。  

![多个执行上下文](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting")  

在实践中，除非主机需要在分离的环境中运行代码，否则可以使用单个执行上下文。 同样，除非主机需要同时运行多个代码段，否则一次运行时就足够了。  

## 内存管理  

JavaScript 是一种垃圾回收的语言，因此在使用另一种语言的 JsRT Api 时，必须牢记几个注意事项。  

主要考虑是 JavaScript 垃圾回收器只能查看两个位置中的值的引用：其运行时堆和堆栈。 因此，对存储在其他 JavaScript 值内部或堆栈上的局部变量中的 JavaScript 值的引用始终会由垃圾回收器看到。 但是，在其他位置（如由主机或系统托管的堆）中存储的引用将不会被垃圾回收器看到，并且可能会导致仍在由主机使用的值的提前收集。  

> [!IMPORTANT]
> 某些语言编译器（如 Visual Studio c + + 编译器）可能会尽可能优化离开本地变量。 必须小心，以确保引用 JavaScript 值的局部变量在堆栈上是否应保持这些值处于活动状态。  

如果对 JavaScript 值的引用将存储在对垃圾回收器不可见的位置，则主机必须使用 JsRT Api 手动添加和删除引用。  

## 异常处理  

当脚本执行期间出现 JavaScript 异常时，包含运行时将置于异常状态。 处于异常状态时，无法运行任何代码，并且所有 API 调用都将失败，并出现错误代码， `JsErrorInExceptionState` 直到主机使用 API 检索和清除异常 `JsGetAndClearException` 。 如果主机从 JavaScript 回调返回，但未从异常状态中清除运行时，则当控件传递回 JavaScript 引擎时，将立即重新引发 JavaScript 异常。 这还允许主机回调通过将运行时设置为异常状态，然后从主机回调中返回来 "引发" JavaScript 异常。  

不允许主机通过其自己的内部异常传播到主机回调-任何回调方法都必须在将控制权返回给运行时之前捕获所有主机异常。  

## 运行时资源使用情况  

JsRT Api 公开了多种方法来监视和修改运行时使用资源的方式。 它们通常细分为以下类别：  

*   **线程使用**。 默认情况下，每个运行时将创建专用的 JIT 编译器线程和服务该运行时的专用 GC 线程。 如果使用标志创建运行时 `JsRuntimeAttributeDisableBackgroundWork` ，则 JIT 和 GC 工作将在运行时线程本身上执行，而不是针对每个线程在单独的后台线程上执行。 宿主还可以向调用提供线程服务回调 `JsCreateRuntime` ，从而使主机能够以其认为合适的任何方式计划 JIT 和 GC 工作。
*   **内存使用**。 可通过多种方式监视和修改运行时的内存使用情况。 如果运行时将长时间运行，则主机可以 `JsRuntimeAttributeEnableIdleProcessing` 在创建运行时时指定标志，然后在 `JsIdle` 主机处于空闲状态时进行调用。 这使引擎能够推迟某些内存清理和簿记工作，直到空闲时间。  
    
    主机可以通过调用监视垃圾回收 `JsSetRuntimeBeforeCollectCallback` 。 它还可以通过调用来监视堆所进行的分配 `JsSetRuntimeMemoryAllocationCallback` 。 请注意，仅当运行时堆需要更多要分配的空间时，此 API 才会在每个 JavaScript 分配上回调。 允许内存分配回调拒绝请求，这将触发垃圾回收，如果没有内存可用，则运行时内存不足错误。  
    
    宿主还可以调用 `JsSetRuntimeMemoryLimit` 以设置对运行时可以使用的内存量的限制。 当运行时达到限制时，它将触发垃圾回收，如果没有可用内存，则运行时将引发内存不足错误。  
    
*   **脚本中断和评估**。 主机可以调用 `JsDisableRuntimeExecution` 以终止运行时内的执行。 可随时通过任何线程进行此通话。 由于脚本终止依赖于插入代码中插入的防护点，因此脚本可能不会完全终止，但随后会很快终止。 默认情况下，终止防护点放置在生成的代码中，并且可能不涉及每种情况，如无限循环。 使用标志创建运行时 `JsRuntimeAttributeAllowScriptInterrupt` 会导致运行时插入针对无限循环的其他检查，这通常会降低较小的性能开销。  
    
    如果主机希望禁止 JIT 编译器生成本机代码，则可以指定该 `JsRuntimeAttributeDisableNativeCodeGeneration` 标志。 宿主还可以禁止脚本通过指定标志来动态运行脚本 `JsRuntimeAttributeDisableEval` 。  
    
## 调试和分析  

JsRT Api 支持通过活动脚本技术进行调试和分析。  

从 Windows 10 开始，Chakra JavaScript 引擎支持旧版 Internet Explorer （MSHTML）引擎和新的 Microsoft Edge （EdgeHTML）引擎，并且你可以在 JsRT 中确定目标（有关详细信息，请参阅[面向 Microsoft Edge 与旧引擎](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)）。 在 Visual Studio 中调试脚本的工作方式与旧版引擎和 Microsoft Edge 引擎的工作方式不同。 使用旧版引擎，主机需要提供[IDebugApplication 接口](/scripting/winscript/reference/idebugapplication-interface)指针，该接口指针可从[IProcessDebugManager 接口](/scripting/winscript/reference/iprocessdebugmanager-interface)实例中获取。 对于 Microsoft Edge 引擎， `IDebugApplication` 已弃用，并且 Chakra 引擎通过 Visual Studio 调试器启用本机和脚本调试功能，而无需 `IDebugApplication` 从用户实现。  

若要使执行上下文中的脚本可调试，Chakra 引擎必须切换到使用效率较低的代码执行方法。 因此，调试代码的运行速度通常比不可调试的代码更慢。 因此，使用旧版引擎，主机可以选择从开始在执行上下文中开始调试，方法是将 `IDebugApplication` 指针置于前面 `JsCreateContext` ，或者它可以等到需要调试，然后调用 `JsStartDebugging` 。 使用 Microsoft Edge 引擎后，将 `JsCreateContext` 不再接受 `IDebugApplication` 参数，因此，脚本仅在调用后才可调试 `JsStartDebugging` 。 使用 Visual Studio 进行调试时，必须启用 "脚本" 调试器选项。  

可通过两种方式之一来分析执行上下文中的 JavaScript 代码。 命令行 Visual Studio 探查器（vsperf.exe）可在 Windows 8.1 和更高版本中与/js 开关一起使用，以生成针对应用程序中运行的 JavaScript 代码的报表。 或者，主机可以直接调用 `JsStartProfiling` 并 `JsStopProfiling` 提供用于执行分析的回调。 宿主还可以通过调用来检查垃圾回收的堆的状态 `JsEnumerateHeap` 。 JsRT 中的分析在旧版和 Microsoft Edge 引擎之间以相同的方式工作。 但是，JsRT 分析 api （ `JsStartProfiling` 、 `JsStopProfiling` 、 `JsEnumerateHeap` 和 `JsIsEnumeratingHeap` ）对于通用 Windows 应用不可用。  

<a name="Windows"></a>   

## JsRT 和通用 Windows 平台  

你可以使用 JsRT Api 将脚本功能添加到通用 Windows 应用。 使用 JsRT Api 的通用 Windows 应用将需要面向 Microsoft Edge JSRT Api，后者又面向 Edge Chakra 引擎。 有关详细信息，请参阅确定[Microsoft Edge 与传统引擎的目标](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)。 完整的 JsRT API 可用于通用 Windows 应用，但分析和堆枚举支持（、、 `JsStartProfiling` `JsStopProfiling` `JsEnumerateHeap` 和 `JsIsEnumeratingHeap` 不受支持）除外。  

JsRT 还允许脚本通过 Microsoft Edge JsRT API 公开访问任何[通用 Windows 平台（UWP） api](https://msdn.microsoft.com/library/windows/apps/br211377.aspx) `JsProjectWinRTNamespace` 。 除了在 "经典（Win32） Windows" 应用程序中投影所需的命名空间之外，通用 Windows 应用程序还不需要安装，但需要启用 COM 初始化的委派泵机制，才能 `JsSetProjectionEnqueueCallback` 启用事件和异步 api。 以下 Win32 示例利用异步 UWP Api 创建 http 客户端以从 Uri 获取内容：  

```cpp
typedef struct _jsCall {
    JsProjectionCallback jsCallback;
    JsProjectionCallbackContext jsContext;
    HANDLE event;
} jsCall;

// Set up delegated pumping mechanism; not necessary in UWP applications.
jsCall outstandingCall = {};
CoInitializeEx(nullptr, COINIT_MULTITHREADED);
JsSetProjectionEnqueueCallback([](JsProjectionCallback jsCallback,
JsProjectionCallbackContext jsContext, void *callbackState) {
    jsCall* call = (jsCall*)callbackState;
    call->jsCallback = jsCallback;
    call->jsContext = jsContext;
    SetEvent(call->event);
    },
&outstandingCall);
HANDLE event = CreateEventEx(NULL, NULL, CREATE_EVENT_MANUAL_RESET, EVENT_ALL_ACCESS);
outstandingCall.event = event;

// Project necessary namespaces.
JsProjectWinRTNamespace(L"Windows.Foundation");
JsProjectWinRTNamespace(L"Windows.Web");

// Get content from an Uri.
JsRunScript(L"var uri = new Windows.Foundation.Uri(\"http://somedatasource.com\"); " \
    L"var httpClient = new Windows.Web.Http.HttpClient();" \
    L"httpClient.getStringAsync(uri).done(function (content) { " \
    L"    // do something with the string content " \
    L"}, onError); " \
    L"function onError(reason) { " \
    L"    // error handling " \
    L"}",
    currentSourceContext, L"", &result);

// Wait for async call to come in and then execute; not necessary in UWP applications.
WaitForSingleObjectEx(outstandingCall.event, 10000, FALSE) == WAIT_OBJECT_0;
outstandingCall.jsCallback(outstandingCall.jsContext);
```  

## 另请参阅  

*   [JavaScript 运行时示例应用](https://go.microsoft.com/fwlink/p/?LinkID=306674&clcid=0x409)   
*   [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)   
*   [JavaScript 运行时托管](../javascript-runtime-hosting.md)  
