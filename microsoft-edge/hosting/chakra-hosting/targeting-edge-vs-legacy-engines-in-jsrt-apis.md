---
description: 'Learn how to target the different Windows 10 JavaScript engines. '
title: Targeting Microsoft Edge vs. Legacy engines in JsRT APIs
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
# <span data-ttu-id="8ada6-103">Targeting Microsoft Edge vs. Legacy engines in JsRT APIs</span><span class="sxs-lookup"><span data-stu-id="8ada6-103">Targeting Microsoft Edge vs. Legacy engines in JsRT APIs</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="8ada6-104">Windows 10 supports two different JavaScript engines:</span><span class="sxs-lookup"><span data-stu-id="8ada6-104">Windows 10 supports two different JavaScript engines:</span></span>  

*   <span data-ttu-id="8ada6-105">The old Chakra engine (also called the *legacy engine* or jscript9.dll below) that ships with and supports Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="8ada6-105">The old Chakra engine (also called the *legacy engine* or jscript9.dll below) that ships with and supports Internet Explorer 11.</span></span> <span data-ttu-id="8ada6-106">This engine is frozen in time and will remain fundamentally unchanged from Win8.1/IE11 release.</span><span class="sxs-lookup"><span data-stu-id="8ada6-106">This engine is frozen in time and will remain fundamentally unchanged from Win8.1/IE11 release.</span></span>  
*   <span data-ttu-id="8ada6-107">The new Chakra engine (also called the *Edge engine* or chakra.dll below) that ships with and supports the new browser in Windows 10, Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8ada6-107">The new Chakra engine (also called the *Edge engine* or chakra.dll below) that ships with and supports the new browser in Windows 10, Microsoft Edge.</span></span> <span data-ttu-id="8ada6-108">This engine will be continually updated and will support a "living" [Edge](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) engine.</span><span class="sxs-lookup"><span data-stu-id="8ada6-108">This engine will be continually updated and will support a "living" [Edge](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) engine.</span></span> <span data-ttu-id="8ada6-109">A living Microsoft Edge engine implies that unlike the legacy engine, the Microsoft Edge engine would not carry forward any form of versioning script functionality to opt into.</span><span class="sxs-lookup"><span data-stu-id="8ada6-109">A living Microsoft Edge engine implies that unlike the legacy engine, the Microsoft Edge engine would not carry forward any form of versioning script functionality to opt into.</span></span>  

 <span data-ttu-id="8ada6-110">When creating an app using the JavaScript Runtime Hosting (JsRT) API, you can choose to target either the legacy or the Microsoft Edge engine.</span><span class="sxs-lookup"><span data-stu-id="8ada6-110">When creating an app using the JavaScript Runtime Hosting (JsRT) API, you can choose to target either the legacy or the Microsoft Edge engine.</span></span>  

*   <span data-ttu-id="8ada6-111">If you need to emphasize backward compatibility of your existing applications, target the legacy engine.</span><span class="sxs-lookup"><span data-stu-id="8ada6-111">If you need to emphasize backward compatibility of your existing applications, target the legacy engine.</span></span>  
*   <span data-ttu-id="8ada6-112">If you want your app to be forward looking and support new JavaScript features as they are released (for example, ECMAScript 6), target the Microsoft Edge engine.</span><span class="sxs-lookup"><span data-stu-id="8ada6-112">If you want your app to be forward looking and support new JavaScript features as they are released (for example, ECMAScript 6), target the Microsoft Edge engine.</span></span>  

<span data-ttu-id="8ada6-113">This topic includes details that describe how to target the different engines.</span><span class="sxs-lookup"><span data-stu-id="8ada6-113">This topic includes details that describe how to target the different engines.</span></span>  

## <span data-ttu-id="8ada6-114">Target your preferred version</span><span class="sxs-lookup"><span data-stu-id="8ada6-114">Target your preferred version</span></span>  

<span data-ttu-id="8ada6-115">When creating an app, you can select the version of the JsRT that supports either the Microsoft Edge engine or the legacy engine.</span><span class="sxs-lookup"><span data-stu-id="8ada6-115">When creating an app, you can select the version of the JsRT that supports either the Microsoft Edge engine or the legacy engine.</span></span> <span data-ttu-id="8ada6-116">You can choose the JsRT version based on the guidelines above.</span><span class="sxs-lookup"><span data-stu-id="8ada6-116">You can choose the JsRT version based on the guidelines above.</span></span> <span data-ttu-id="8ada6-117">To accommodate these distinctions, the following changes have been made to `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging`.</span><span class="sxs-lookup"><span data-stu-id="8ada6-117">To accommodate these distinctions, the following changes have been made to `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging`.</span></span>  

<span data-ttu-id="8ada6-118">For `JsCreateRuntime`:</span><span class="sxs-lookup"><span data-stu-id="8ada6-118">For `JsCreateRuntime`:</span></span>  

*   <span data-ttu-id="8ada6-119">When targeting the legacy engine, the `JsRuntimeVersionEdge` enumeration value is deprecated, and a message will suggest using the `JsRuntimeVersionInternetExplorer11` value instead.</span><span class="sxs-lookup"><span data-stu-id="8ada6-119">When targeting the legacy engine, the `JsRuntimeVersionEdge` enumeration value is deprecated, and a message will suggest using the `JsRuntimeVersionInternetExplorer11` value instead.</span></span>  
*   <span data-ttu-id="8ada6-120">When targeting the Microsoft Edge engine, the version parameter is omitted from the `JsCreateRuntime` function.</span><span class="sxs-lookup"><span data-stu-id="8ada6-120">When targeting the Microsoft Edge engine, the version parameter is omitted from the `JsCreateRuntime` function.</span></span>  
    
    ```cpp
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);
    ```  
    
 <span data-ttu-id="8ada6-121">For `JsCreateContext` and `JsStartDebugging`:</span><span class="sxs-lookup"><span data-stu-id="8ada6-121">For `JsCreateContext` and `JsStartDebugging`:</span></span>  

*   <span data-ttu-id="8ada6-122">When targeting the legacy engine, the `IDebugApplication` interface is used to supply your own non-remote debugging methods.</span><span class="sxs-lookup"><span data-stu-id="8ada6-122">When targeting the legacy engine, the `IDebugApplication` interface is used to supply your own non-remote debugging methods.</span></span> <span data-ttu-id="8ada6-123">For debugging purposes, `JsCreateContext` and `JsStartDebugging` functions take `IDebugApplication` as parameter.</span><span class="sxs-lookup"><span data-stu-id="8ada6-123">For debugging purposes, `JsCreateContext` and `JsStartDebugging` functions take `IDebugApplication` as parameter.</span></span>  
*   <span data-ttu-id="8ada6-124">When targeting the Microsoft Edge engine, the `IDebugApplication` interface is deprecated.</span><span class="sxs-lookup"><span data-stu-id="8ada6-124">When targeting the Microsoft Edge engine, the `IDebugApplication` interface is deprecated.</span></span> <span data-ttu-id="8ada6-125">The Chakra engine enables native and script debugging capability with Visual Studio debugger without requiring an implementation of `IDebugApplication` from user.</span><span class="sxs-lookup"><span data-stu-id="8ada6-125">The Chakra engine enables native and script debugging capability with Visual Studio debugger without requiring an implementation of `IDebugApplication` from user.</span></span> <span data-ttu-id="8ada6-126">The interface is no longer a parameter for `JsCreateContext` and `JsStartDebugging` as a result.</span><span class="sxs-lookup"><span data-stu-id="8ada6-126">The interface is no longer a parameter for `JsCreateContext` and `JsStartDebugging` as a result.</span></span>  

<span data-ttu-id="8ada6-127">The signatures for the preceding APIs in the legacy engine are as follows:</span><span class="sxs-lookup"><span data-stu-id="8ada6-127">The signatures for the preceding APIs in the legacy engine are as follows:</span></span>  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);

JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);
```  

<span data-ttu-id="8ada6-128">The signatures for the preceding APIs in the Microsoft Edge engine are as follows:</span><span class="sxs-lookup"><span data-stu-id="8ada6-128">The signatures for the preceding APIs in the Microsoft Edge engine are as follows:</span></span>  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);

JsErrorCode JsStartDebugging();
```  

## <span data-ttu-id="8ada6-129">Compile for your preferred version using Visual C++</span><span class="sxs-lookup"><span data-stu-id="8ada6-129">Compile for your preferred version using Visual C++</span></span>  

<span data-ttu-id="8ada6-130">When using Visual C++, import the JsRT API by including the jsrt.h header, and ensure that jsrt.lib is included in your linker input files list:</span><span class="sxs-lookup"><span data-stu-id="8ada6-130">When using Visual C++, import the JsRT API by including the jsrt.h header, and ensure that jsrt.lib is included in your linker input files list:</span></span>  

```cpp
#include <jsrt.h>
```  

![Adding jsrt.lib as a linker input file](../chakra-hosting/media/js-chakra.png "JS_Chakra_")  

<span data-ttu-id="8ada6-132">If you want to target the Microsoft Edge engine binaries, you need to define the macro `USE_EDGEMODE_JSRT` before including jsrt.h, and instead of linking against jsrt.lib, you should link against chakrart.lib:</span><span class="sxs-lookup"><span data-stu-id="8ada6-132">If you want to target the Microsoft Edge engine binaries, you need to define the macro `USE_EDGEMODE_JSRT` before including jsrt.h, and instead of linking against jsrt.lib, you should link against chakrart.lib:</span></span>  

```cpp
#define USE_EDGEMODE_JSRT
#include <jsrt.h>
```  

![Adding chakrart.lib as a linker input file](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting_")  

<span data-ttu-id="8ada6-134">If you're starting with a new application, you are now ready to start writing code against the JsRT API.</span><span class="sxs-lookup"><span data-stu-id="8ada6-134">If you're starting with a new application, you are now ready to start writing code against the JsRT API.</span></span>  

## <span data-ttu-id="8ada6-135">Compile for your preferred version using .NET</span><span class="sxs-lookup"><span data-stu-id="8ada6-135">Compile for your preferred version using .NET</span></span>  

<span data-ttu-id="8ada6-136">If you're using .NET and P/Invoke, you must change your JsRT API [DllImport] declarations to import chakra.dll instead of jscript9.dll.</span><span class="sxs-lookup"><span data-stu-id="8ada6-136">If you're using .NET and P/Invoke, you must change your JsRT API [DllImport] declarations to import chakra.dll instead of jscript9.dll.</span></span> <span data-ttu-id="8ada6-137">In addition, change the definition of `JsCreateRuntime` to remove the `JsRuntimeVersion` parameter and the definition of `JsCreateContext` and `JsStartDebugging` to remove the `IDebugApplication` parameter.</span><span class="sxs-lookup"><span data-stu-id="8ada6-137">In addition, change the definition of `JsCreateRuntime` to remove the `JsRuntimeVersion` parameter and the definition of `JsCreateContext` and `JsStartDebugging` to remove the `IDebugApplication` parameter.</span></span>  

<span data-ttu-id="8ada6-138">For the legacy engine, use the following code.</span><span class="sxs-lookup"><span data-stu-id="8ada6-138">For the legacy engine, use the following code.</span></span>  

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

<span data-ttu-id="8ada6-139">For the Microsoft Edge engine, use the following code.</span><span class="sxs-lookup"><span data-stu-id="8ada6-139">For the Microsoft Edge engine, use the following code.</span></span>  

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
> <span data-ttu-id="8ada6-140">If you are manually marshaling the function pointer (such as via LoadLibrary/GetProcAddress), it is critical that you do not mix the declarations of the method, or else you will unbalance the stack, which will result in unpredictable behavior such as causing your app to crash.</span><span class="sxs-lookup"><span data-stu-id="8ada6-140">If you are manually marshaling the function pointer (such as via LoadLibrary/GetProcAddress), it is critical that you do not mix the declarations of the method, or else you will unbalance the stack, which will result in unpredictable behavior such as causing your app to crash.</span></span> <span data-ttu-id="8ada6-141">The same problem will occur if you perform a global search-and-replace of instances of jscript9.dll in your import code, because you'll miss the `version` parameter being dropped.</span><span class="sxs-lookup"><span data-stu-id="8ada6-141">The same problem will occur if you perform a global search-and-replace of instances of jscript9.dll in your import code, because you'll miss the `version` parameter being dropped.</span></span>  

## <span data-ttu-id="8ada6-142">Summary</span><span class="sxs-lookup"><span data-stu-id="8ada6-142">Summary</span></span>  

<span data-ttu-id="8ada6-143">In Windows 10, the JavaScript Runtime Hosting APIs are splitting into two.</span><span class="sxs-lookup"><span data-stu-id="8ada6-143">In Windows 10, the JavaScript Runtime Hosting APIs are splitting into two.</span></span> <span data-ttu-id="8ada6-144">These APIs now support a "living" Microsoft Edge engine, whose language capabilities will be aligned with the "living" Microsoft Edge engine in the Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8ada6-144">These APIs now support a "living" Microsoft Edge engine, whose language capabilities will be aligned with the "living" Microsoft Edge engine in the Microsoft Edge.</span></span> <span data-ttu-id="8ada6-145">You can leverage these capabilities from your desktop or Store apps to create new and exciting ways to extend your application and to leverage modern Web skills in your existing code base.</span><span class="sxs-lookup"><span data-stu-id="8ada6-145">You can leverage these capabilities from your desktop or Store apps to create new and exciting ways to extend your application and to leverage modern Web skills in your existing code base.</span></span> <span data-ttu-id="8ada6-146">However, because there are subtle differences between previous versions, you must be aware of the following points when targeting the Edge or legacy engine.</span><span class="sxs-lookup"><span data-stu-id="8ada6-146">However, because there are subtle differences between previous versions, you must be aware of the following points when targeting the Edge or legacy engine.</span></span>  

*   <span data-ttu-id="8ada6-147">Your app can support only one version of JsRT per process.</span><span class="sxs-lookup"><span data-stu-id="8ada6-147">Your app can support only one version of JsRT per process.</span></span>  
    
    <span data-ttu-id="8ada6-148">For example, you can't create a Microsoft Edge engine runtime and then a legacy engine runtime and expect them to run correctly in the same process.</span><span class="sxs-lookup"><span data-stu-id="8ada6-148">For example, you can't create a Microsoft Edge engine runtime and then a legacy engine runtime and expect them to run correctly in the same process.</span></span> <span data-ttu-id="8ada6-149">This is unsupported and may result in undocumented behavior, such as failure to load the second DLL.</span><span class="sxs-lookup"><span data-stu-id="8ada6-149">This is unsupported and may result in undocumented behavior, such as failure to load the second DLL.</span></span>  
    
*   <span data-ttu-id="8ada6-150">When targeting the Microsoft Edge engine, your app may unexpectedly acquire new features when the underlying platform is automatically updated.</span><span class="sxs-lookup"><span data-stu-id="8ada6-150">When targeting the Microsoft Edge engine, your app may unexpectedly acquire new features when the underlying platform is automatically updated.</span></span>  
    
    <span data-ttu-id="8ada6-151">For example, the Internet Explorer 11 mode of the legacy runtime supports block-scoping variable declarations such as `let` and `const`.</span><span class="sxs-lookup"><span data-stu-id="8ada6-151">For example, the Internet Explorer 11 mode of the legacy runtime supports block-scoping variable declarations such as `let` and `const`.</span></span> <span data-ttu-id="8ada6-152">If the Microsoft Edge engine automatic versioning behavior had been the standard previously, code that had worked in Internet Explorer 10 mode, which did not have block-scoping rules, may have started failing when the platform had automatically upgraded.</span><span class="sxs-lookup"><span data-stu-id="8ada6-152">If the Microsoft Edge engine automatic versioning behavior had been the standard previously, code that had worked in Internet Explorer 10 mode, which did not have block-scoping rules, may have started failing when the platform had automatically upgraded.</span></span> <span data-ttu-id="8ada6-153">This must be a consideration when choosing which runtime model to use.</span><span class="sxs-lookup"><span data-stu-id="8ada6-153">This must be a consideration when choosing which runtime model to use.</span></span> <span data-ttu-id="8ada6-154">While we believe you should target the Microsoft Edge engine whenever possible, you must be careful about using JavaScript code structures that may become invalid in the future.</span><span class="sxs-lookup"><span data-stu-id="8ada6-154">While we believe you should target the Microsoft Edge engine whenever possible, you must be careful about using JavaScript code structures that may become invalid in the future.</span></span>  
    
*   <span data-ttu-id="8ada6-155">JsRT for the Windows Store only supports the Microsoft Edge engine (chakra.dll).</span><span class="sxs-lookup"><span data-stu-id="8ada6-155">JsRT for the Windows Store only supports the Microsoft Edge engine (chakra.dll).</span></span> <span data-ttu-id="8ada6-156">Apps attempting to link against any JsRT API in jscript9.dll will fail certification.</span><span class="sxs-lookup"><span data-stu-id="8ada6-156">Apps attempting to link against any JsRT API in jscript9.dll will fail certification.</span></span>  
*   <span data-ttu-id="8ada6-157">It is critical that you do not confuse the declaration of `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging` between jscript9.dll and chakra.dll, because it will result in imbalancing the stack.</span><span class="sxs-lookup"><span data-stu-id="8ada6-157">It is critical that you do not confuse the declaration of `JsCreateRuntime`, `JsCreateContext`, and `JsStartDebugging` between jscript9.dll and chakra.dll, because it will result in imbalancing the stack.</span></span>  
    
    <span data-ttu-id="8ada6-158">When using C and C++, you will receive a linker error if you try to use the wrong declaration, as long as you're not doing something like calling `LoadLibrary` and then `GetProcAddress`.</span><span class="sxs-lookup"><span data-stu-id="8ada6-158">When using C and C++, you will receive a linker error if you try to use the wrong declaration, as long as you're not doing something like calling `LoadLibrary` and then `GetProcAddress`.</span></span> <span data-ttu-id="8ada6-159">.NET developers may not find this problem as easily, so double-check your code when using this feature.</span><span class="sxs-lookup"><span data-stu-id="8ada6-159">.NET developers may not find this problem as easily, so double-check your code when using this feature.</span></span>  
    
## <span data-ttu-id="8ada6-160">See also</span><span class="sxs-lookup"><span data-stu-id="8ada6-160">See also</span></span>  

*   [<span data-ttu-id="8ada6-161">JavaScript Runtime Hosting</span><span class="sxs-lookup"><span data-stu-id="8ada6-161">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)
 