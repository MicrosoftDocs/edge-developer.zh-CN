---
description: '了解如何面向不同的 Windows 10 JavaScript 引擎。 '
title: 在 JsRT Api 中确定 Microsoft Edge 与传统引擎的目标
ms.date: 06/18/2020
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: cbc7df6c-0bc9-48f5-b9ad-b9ed31c42f92
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
ms.openlocfilehash: 99a3143dd5f995332524a99e5c6c5019b955fea8
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752225"
---
# <span data-ttu-id="d7704-103">在 JsRT Api 中确定 Microsoft Edge 与传统引擎的目标</span><span class="sxs-lookup"><span data-stu-id="d7704-103">Targeting Microsoft Edge vs. Legacy engines in JsRT APIs</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="d7704-104">Windows 10 支持两种不同的 JavaScript 引擎：</span><span class="sxs-lookup"><span data-stu-id="d7704-104">Windows 10 supports two different JavaScript engines:</span></span>  

*   <span data-ttu-id="d7704-105">旧的 Chakra 引擎（也称为*旧版引擎*或以下 jscript9.dll）随附并支持 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="d7704-105">The old Chakra engine (also called the *legacy engine* or jscript9.dll below) that ships with and supports Internet Explorer 11.</span></span> <span data-ttu-id="d7704-106">此引擎已及时冻结，并且将从基本的 Win 8.1/IE11 发布中保持不变。</span><span class="sxs-lookup"><span data-stu-id="d7704-106">This engine is frozen in time and will remain fundamentally unchanged from Win8.1/IE11 release.</span></span>  
*   <span data-ttu-id="d7704-107">新的 Chakra 引擎（也称为*Edge 引擎*或以下 chakra.dll）在 Windows 10、Microsoft Edge 中随附并支持新浏览器。</span><span class="sxs-lookup"><span data-stu-id="d7704-107">The new Chakra engine (also called the *Edge engine* or chakra.dll below) that ships with and supports the new browser in Windows 10, Microsoft Edge.</span></span> <span data-ttu-id="d7704-108">此引擎将不断更新，并且将支持 "动态"[边缘](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx)引擎。</span><span class="sxs-lookup"><span data-stu-id="d7704-108">This engine will be continually updated and will support a "living" [Edge](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) engine.</span></span> <span data-ttu-id="d7704-109">活动的 Microsoft Edge 引擎意味着与旧版引擎不同，Microsoft Edge 引擎不会将任何形式的版本化脚本功能转发到自愿加入。</span><span class="sxs-lookup"><span data-stu-id="d7704-109">A living Microsoft Edge engine implies that unlike the legacy engine, the Microsoft Edge engine would not carry forward any form of versioning script functionality to opt into.</span></span>  

 <span data-ttu-id="d7704-110">使用 JavaScript 运行时托管（JsRT） API 创建应用时，你可以选择面向旧版或 Microsoft Edge 引擎。</span><span class="sxs-lookup"><span data-stu-id="d7704-110">When creating an app using the JavaScript Runtime Hosting (JsRT) API, you can choose to target either the legacy or the Microsoft Edge engine.</span></span>  

*   <span data-ttu-id="d7704-111">如果需要强调现有应用程序的向后兼容性，请确定旧版引擎的目标。</span><span class="sxs-lookup"><span data-stu-id="d7704-111">If you need to emphasize backward compatibility of your existing applications, target the legacy engine.</span></span>  
*   <span data-ttu-id="d7704-112">如果你希望你的应用在发布（如 ECMAScript 6）发布时能够继续查找并支持新的 JavaScript 功能，请确定 Microsoft Edge 引擎的目标。</span><span class="sxs-lookup"><span data-stu-id="d7704-112">If you want your app to be forward looking and support new JavaScript features as they are released (for example, ECMAScript 6), target the Microsoft Edge engine.</span></span>  

<span data-ttu-id="d7704-113">本主题包含介绍如何面向不同引擎的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d7704-113">This topic includes details that describe how to target the different engines.</span></span>  

## <span data-ttu-id="d7704-114">确定首选版本的目标</span><span class="sxs-lookup"><span data-stu-id="d7704-114">Target your preferred version</span></span>  

<span data-ttu-id="d7704-115">创建应用时，你可以选择支持 Microsoft Edge 引擎或旧版引擎的 JsRT 版本。</span><span class="sxs-lookup"><span data-stu-id="d7704-115">When creating an app, you can select the version of the JsRT that supports either the Microsoft Edge engine or the legacy engine.</span></span> <span data-ttu-id="d7704-116">您可以根据上述指南选择 JsRT 版本。</span><span class="sxs-lookup"><span data-stu-id="d7704-116">You can choose the JsRT version based on the guidelines above.</span></span> <span data-ttu-id="d7704-117">为适应这些区别，已对、和进行了以下 `JsCreateRuntime` 更改 `JsCreateContext` `JsStartDebugging` 。</span><span class="sxs-lookup"><span data-stu-id="d7704-117">To accommodate these distinctions, the following changes have been made to `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging`.</span></span>  

<span data-ttu-id="d7704-118">适用于 `JsCreateRuntime` ：</span><span class="sxs-lookup"><span data-stu-id="d7704-118">For `JsCreateRuntime`:</span></span>  

*   <span data-ttu-id="d7704-119">在面向旧版引擎时， `JsRuntimeVersionEdge` 枚举值已弃用，并且会建议使用该值的消息会 `JsRuntimeVersionInternetExplorer11` 改为使用该值。</span><span class="sxs-lookup"><span data-stu-id="d7704-119">When targeting the legacy engine, the `JsRuntimeVersionEdge` enumeration value is deprecated, and a message will suggest using the `JsRuntimeVersionInternetExplorer11` value instead.</span></span>  
*   <span data-ttu-id="d7704-120">当面向 Microsoft Edge 引擎时，将从该函数中省略 version 参数 `JsCreateRuntime` 。</span><span class="sxs-lookup"><span data-stu-id="d7704-120">When targeting the Microsoft Edge engine, the version parameter is omitted from the `JsCreateRuntime` function.</span></span>  
    
    ```cpp
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);
    ```  
    
 <span data-ttu-id="d7704-121">对于 `JsCreateContext` 和 `JsStartDebugging` ：</span><span class="sxs-lookup"><span data-stu-id="d7704-121">For `JsCreateContext` and `JsStartDebugging`:</span></span>  

*   <span data-ttu-id="d7704-122">在面向旧版引擎时，该 `IDebugApplication` 接口用于提供你自己的非远程调试方法。</span><span class="sxs-lookup"><span data-stu-id="d7704-122">When targeting the legacy engine, the `IDebugApplication` interface is used to supply your own non-remote debugging methods.</span></span> <span data-ttu-id="d7704-123">出于调试目的， `JsCreateContext` `JsStartDebugging` 函数采用 `IDebugApplication` 参数。</span><span class="sxs-lookup"><span data-stu-id="d7704-123">For debugging purposes, `JsCreateContext` and `JsStartDebugging` functions take `IDebugApplication` as parameter.</span></span>  
*   <span data-ttu-id="d7704-124">在面向 Microsoft Edge 引擎时， `IDebugApplication` 接口已弃用。</span><span class="sxs-lookup"><span data-stu-id="d7704-124">When targeting the Microsoft Edge engine, the `IDebugApplication` interface is deprecated.</span></span> <span data-ttu-id="d7704-125">Chakra 引擎支持 Visual Studio 调试器的本机和脚本调试功能，无需 `IDebugApplication` 从用户实现。</span><span class="sxs-lookup"><span data-stu-id="d7704-125">The Chakra engine enables native and script debugging capability with Visual Studio debugger without requiring an implementation of `IDebugApplication` from user.</span></span> <span data-ttu-id="d7704-126">该接口不再是参数，因此也 `JsCreateContext` 是 `JsStartDebugging` 如此。</span><span class="sxs-lookup"><span data-stu-id="d7704-126">The interface is no longer a parameter for `JsCreateContext` and `JsStartDebugging` as a result.</span></span>  

<span data-ttu-id="d7704-127">旧版引擎中前面的 Api 的签名如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7704-127">The signatures for the preceding APIs in the legacy engine are as follows:</span></span>  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);

JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);
```  

<span data-ttu-id="d7704-128">Microsoft Edge 引擎中前面的 Api 的签名如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7704-128">The signatures for the preceding APIs in the Microsoft Edge engine are as follows:</span></span>  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);

JsErrorCode JsStartDebugging();
```  

## <span data-ttu-id="d7704-129">使用 Visual c + + 编译首选版本</span><span class="sxs-lookup"><span data-stu-id="d7704-129">Compile for your preferred version using Visual C++</span></span>  

<span data-ttu-id="d7704-130">使用 Visual c + + 时，通过包含 JsRT 标头来导入 JsRT API，并确保链接器输入文件列表中包含 JsRT：</span><span class="sxs-lookup"><span data-stu-id="d7704-130">When using Visual C++, import the JsRT API by including the jsrt.h header, and ensure that jsrt.lib is included in your linker input files list:</span></span>  

```cpp
#include <jsrt.h>
```  

![将 jsrt 添加为链接器输入文件](../chakra-hosting/media/js-chakra.png "JS_Chakra_")  

<span data-ttu-id="d7704-132">如果你想要面向 Microsoft Edge 引擎二进制文件，你需要先定义宏，然后 `USE_EDGEMODE_JSRT` 再包含 jsrt，而不是通过 jsrt 进行链接，而应链接到 chakrart：</span><span class="sxs-lookup"><span data-stu-id="d7704-132">If you want to target the Microsoft Edge engine binaries, you need to define the macro `USE_EDGEMODE_JSRT` before including jsrt.h, and instead of linking against jsrt.lib, you should link against chakrart.lib:</span></span>  

```cpp
#define USE_EDGEMODE_JSRT
#include <jsrt.h>
```  

![将 chakrart 添加为链接器输入文件](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting_")  

<span data-ttu-id="d7704-134">如果你是从新的应用程序开始，你现在可以开始编写针对 JsRT API 的代码。</span><span class="sxs-lookup"><span data-stu-id="d7704-134">If you're starting with a new application, you are now ready to start writing code against the JsRT API.</span></span>  

## <span data-ttu-id="d7704-135">使用 .NET 为首选版本编译</span><span class="sxs-lookup"><span data-stu-id="d7704-135">Compile for your preferred version using .NET</span></span>  

<span data-ttu-id="d7704-136">如果你使用的是 .NET 和 P/Invoke，则必须更改 JsRT API [DllImport] 声明才能导入 chakra.dll 而不是 jscript9.dll。</span><span class="sxs-lookup"><span data-stu-id="d7704-136">If you're using .NET and P/Invoke, you must change your JsRT API [DllImport] declarations to import chakra.dll instead of jscript9.dll.</span></span> <span data-ttu-id="d7704-137">此外，将 "定义" 更改 `JsCreateRuntime` 为 "删除参数 `JsRuntimeVersion` " 和 "定义" `JsCreateContext` ，然后 `JsStartDebugging` 删除 `IDebugApplication` 参数。</span><span class="sxs-lookup"><span data-stu-id="d7704-137">In addition, change the definition of `JsCreateRuntime` to remove the `JsRuntimeVersion` parameter and the definition of `JsCreateContext` and `JsStartDebugging` to remove the `IDebugApplication` parameter.</span></span>  

<span data-ttu-id="d7704-138">对于旧版引擎，请使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="d7704-138">For the legacy engine, use the following code.</span></span>  

```csharp
[DllImport("jscript9.dll")]
public static extern JsErrorCode JsCreateRuntime(
    JsRuntimeAttributes attributes,
    JsRuntimeVersion version,
    JsThreadServiceCallback callback,
    out JsRuntimeSafeHandle runtime
);

[DllImport("jscript9.dll")]
public static extern JsErrorCode JsCreateContext(
    JsRuntimeSafeHandle runtime,
    IDebugApplication debugApplication,
    out JsContextRef newContext
);   

[DllImport("jscript9.dll")]
public static extern JsErrorCode JsStartDebugging(
    IDebugApplication debugApplication,
);
```  

<span data-ttu-id="d7704-139">对于 Microsoft Edge 引擎，请使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="d7704-139">For the Microsoft Edge engine, use the following code.</span></span>  

```csharp
[DllImport("chakra.dll")]
public static extern JsErrorCode JsCreateRuntime(
    JsRuntimeAttributes attributes,
    JsThreadServiceCallback callback,
    out JsRuntimeSafeHandle runtime
);  

[DllImport("chakra.dll")]
public static extern JsErrorCode JsCreateContext(
    JsRuntimeSafeHandle runtime,
    out JsContextRef newContext
);

[DllImport("chakra.dll")]
public static extern JsErrorCode JsStartDebugging();
```  

> [!CAUTION]
> <span data-ttu-id="d7704-140">如果你手动封送处理函数指针（如通过 LoadLibrary/GetProcAddress），则不要混合使用该方法的声明，否则你将 unbalance 该堆栈，这将导致导致应用崩溃等不可预测的行为。</span><span class="sxs-lookup"><span data-stu-id="d7704-140">If you are manually marshaling the function pointer (such as via LoadLibrary/GetProcAddress), it is critical that you do not mix the declarations of the method, or else you will unbalance the stack, which will result in unpredictable behavior such as causing your app to crash.</span></span> <span data-ttu-id="d7704-141">如果在导入代码中执行全局搜索和替换 jscript9.dll 的实例，则会出现相同的问题，因为你将错过 `version` 要删除的参数。</span><span class="sxs-lookup"><span data-stu-id="d7704-141">The same problem will occur if you perform a global search-and-replace of instances of jscript9.dll in your import code, because you'll miss the `version` parameter being dropped.</span></span>  

## <span data-ttu-id="d7704-142">摘要</span><span class="sxs-lookup"><span data-stu-id="d7704-142">Summary</span></span>  

<span data-ttu-id="d7704-143">在 Windows 10 中，JavaScript 运行时托管 Api 将拆分为两个。</span><span class="sxs-lookup"><span data-stu-id="d7704-143">In Windows 10, the JavaScript Runtime Hosting APIs are splitting into two.</span></span> <span data-ttu-id="d7704-144">这些 Api 现在支持 "动态" Microsoft Edge 引擎，其语言功能将与 Microsoft Edge 中的 "生活" Microsoft Edge 引擎对齐。</span><span class="sxs-lookup"><span data-stu-id="d7704-144">These APIs now support a "living" Microsoft Edge engine, whose language capabilities will be aligned with the "living" Microsoft Edge engine in the Microsoft Edge.</span></span> <span data-ttu-id="d7704-145">你可以利用桌面或应用商店应用中的这些功能来创建新的、令人兴奋的方法来扩展你的应用程序，并利用现有基本代码中的新式 Web 技术。</span><span class="sxs-lookup"><span data-stu-id="d7704-145">You can leverage these capabilities from your desktop or Store apps to create new and exciting ways to extend your application and to leverage modern Web skills in your existing code base.</span></span> <span data-ttu-id="d7704-146">但是，由于以前版本之间存在细微差异，因此在面向 Edge 或旧版引擎时，必须注意以下几点。</span><span class="sxs-lookup"><span data-stu-id="d7704-146">However, because there are subtle differences between previous versions, you must be aware of the following points when targeting the Edge or legacy engine.</span></span>  

*   <span data-ttu-id="d7704-147">你的应用只能支持每个进程的 JsRT 的一个版本。</span><span class="sxs-lookup"><span data-stu-id="d7704-147">Your app can support only one version of JsRT per process.</span></span>  
    
    <span data-ttu-id="d7704-148">例如，你无法创建 Microsoft Edge 引擎运行时，然后创建旧版引擎运行时，并希望它们在同一进程中正确运行。</span><span class="sxs-lookup"><span data-stu-id="d7704-148">For example, you can't create a Microsoft Edge engine runtime and then a legacy engine runtime and expect them to run correctly in the same process.</span></span> <span data-ttu-id="d7704-149">这是不受支持的，可能会导致未记录的行为，例如加载第二个 DLL 失败。</span><span class="sxs-lookup"><span data-stu-id="d7704-149">This is unsupported and may result in undocumented behavior, such as failure to load the second DLL.</span></span>  
    
*   <span data-ttu-id="d7704-150">当面向 Microsoft Edge 引擎时，你的应用可能会在基础平台自动更新时意外获取新功能。</span><span class="sxs-lookup"><span data-stu-id="d7704-150">When targeting the Microsoft Edge engine, your app may unexpectedly acquire new features when the underlying platform is automatically updated.</span></span>  
    
    <span data-ttu-id="d7704-151">例如，旧版运行时的 Internet Explorer 11 模式支持块范围变量声明 `let` ，如和 `const` 。</span><span class="sxs-lookup"><span data-stu-id="d7704-151">For example, the Internet Explorer 11 mode of the legacy runtime supports block-scoping variable declarations such as `let` and `const`.</span></span> <span data-ttu-id="d7704-152">如果 Microsoft Edge 引擎自动版本控制行为以前是标准的，则已在 Internet Explorer 10 模式下工作的代码在该平台自动升级时可能已开始失败。</span><span class="sxs-lookup"><span data-stu-id="d7704-152">If the Microsoft Edge engine automatic versioning behavior had been the standard previously, code that had worked in Internet Explorer 10 mode, which did not have block-scoping rules, may have started failing when the platform had automatically upgraded.</span></span> <span data-ttu-id="d7704-153">在选择要使用的运行时模型时，必须考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="d7704-153">This must be a consideration when choosing which runtime model to use.</span></span> <span data-ttu-id="d7704-154">虽然我们认为你应该尽可能地确定 Microsoft Edge 引擎的目标，但你必须小心使用将来可能会无效的 JavaScript 代码结构。</span><span class="sxs-lookup"><span data-stu-id="d7704-154">While we believe you should target the Microsoft Edge engine whenever possible, you must be careful about using JavaScript code structures that may become invalid in the future.</span></span>  
    
*   <span data-ttu-id="d7704-155">适用于 Windows 应用商店的 JsRT 仅支持 Microsoft Edge 引擎（chakra.dll）。</span><span class="sxs-lookup"><span data-stu-id="d7704-155">JsRT for the Windows Store only supports the Microsoft Edge engine (chakra.dll).</span></span> <span data-ttu-id="d7704-156">尝试链接到 jscript9.dll 中的任何 JsRT API 的应用将无法通过认证。</span><span class="sxs-lookup"><span data-stu-id="d7704-156">Apps attempting to link against any JsRT API in jscript9.dll will fail certification.</span></span>  
*   <span data-ttu-id="d7704-157">请务必不要混淆 jscript9.dll 和 chakra.dll 之间的声明，这一点很重要 `JsCreateRuntime` `JsCreateContext` `JsStartDebugging` ，因为它会导致堆栈的 imbalancing。</span><span class="sxs-lookup"><span data-stu-id="d7704-157">It is critical that you do not confuse the declaration of `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging` between jscript9.dll and chakra.dll, because it will result in imbalancing the stack.</span></span>  
    
    <span data-ttu-id="d7704-158">使用 C 和 c + + 时，如果你尝试使用错误的声明，则会收到链接器错误，前提是你不执行诸如调用之类的操作 `LoadLibrary` `GetProcAddress` 。</span><span class="sxs-lookup"><span data-stu-id="d7704-158">When using C and C++, you will receive a linker error if you try to use the wrong declaration, as long as you're not doing something like calling `LoadLibrary` and then `GetProcAddress`.</span></span> <span data-ttu-id="d7704-159">.NET 开发人员可能不会很轻松地发现此问题，因此在使用此功能时，请仔细检查代码。</span><span class="sxs-lookup"><span data-stu-id="d7704-159">.NET developers may not find this problem as easily, so double-check your code when using this feature.</span></span>  
    
## <span data-ttu-id="d7704-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7704-160">See also</span></span>  

*   [<span data-ttu-id="d7704-161">JavaScript 运行时托管</span><span class="sxs-lookup"><span data-stu-id="d7704-161">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)
 