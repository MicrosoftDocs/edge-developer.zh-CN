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
# 在 JsRT Api 中确定 Microsoft Edge 与传统引擎的目标  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

Windows 10 支持两种不同的 JavaScript 引擎：  

*   旧的 Chakra 引擎也 (jscript9.dll 随附的 *旧版引擎* 或) ，并支持 Internet Explorer 11。 此引擎已及时冻结，并且将从基本的 Win 8.1/IE11 发布中保持不变。  
*   新的 Chakra 引擎也 (chakra.dll 在 Windows 10 的 Microsoft Edge 中随附和支持新浏览器的 *边缘引擎* 或) 以下。 此引擎将不断更新，并且将支持 "动态" [边缘](https://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) 引擎。 活动的 Microsoft Edge 引擎意味着与旧版引擎不同，Microsoft Edge 引擎不会将任何形式的版本化脚本功能转发到自愿加入。  

 使用 JavaScript 运行时托管 (JsRT) API 创建应用时，你可以选择面向旧版或 Microsoft Edge 引擎。  

*   如果需要强调现有应用程序的向后兼容性，请确定旧版引擎的目标。  
*   如果你希望你的应用在发布时能够继续查找并支持新的 JavaScript 功能 (例如，ECMAScript 6) ，请面向 Microsoft Edge 引擎。  

本主题包含介绍如何面向不同引擎的详细信息。  

## 确定首选版本的目标  

创建应用时，你可以选择支持 Microsoft Edge 引擎或旧版引擎的 JsRT 版本。 您可以根据上述指南选择 JsRT 版本。 为适应这些区别，已对、和进行了以下 `JsCreateRuntime` 更改 `JsCreateContext` `JsStartDebugging` 。  

适用于 `JsCreateRuntime` ：  

*   在面向旧版引擎时， `JsRuntimeVersionEdge` 枚举值已弃用，并且会建议使用该值的消息会 `JsRuntimeVersionInternetExplorer11` 改为使用该值。  
*   当面向 Microsoft Edge 引擎时，将从该函数中省略 version 参数 `JsCreateRuntime` 。  
    
    ```cpp
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);
    ```  
    
 对于 `JsCreateContext` 和 `JsStartDebugging` ：  

*   在面向旧版引擎时，该 `IDebugApplication` 接口用于提供你自己的非远程调试方法。 出于调试目的， `JsCreateContext` `JsStartDebugging` 函数采用 `IDebugApplication` 参数。  
*   在面向 Microsoft Edge 引擎时， `IDebugApplication` 接口已弃用。 Chakra 引擎支持 Visual Studio 调试器的本机和脚本调试功能，无需 `IDebugApplication` 从用户实现。 该接口不再是参数，因此也 `JsCreateContext` 是 `JsStartDebugging` 如此。  

旧版引擎中前面的 Api 的签名如下所示：  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);

JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);
```  

Microsoft Edge 引擎中前面的 Api 的签名如下所示：  

```cpp
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);

JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);

JsErrorCode JsStartDebugging();
```  

## 使用 Visual c + + 编译首选版本  

使用 Visual c + + 时，通过包含 JsRT 标头来导入 JsRT API，并确保链接器输入文件列表中包含 JsRT：  

```cpp
#include <jsrt.h>
```  

![将 jsrt 添加为链接器输入文件](../chakra-hosting/media/js-chakra.png "JS_Chakra_")  

如果你想要面向 Microsoft Edge 引擎二进制文件，你需要先定义宏，然后 `USE_EDGEMODE_JSRT` 再包含 jsrt，而不是通过 jsrt 进行链接，而应链接到 chakrart：  

```cpp
#define USE_EDGEMODE_JSRT
#include <jsrt.h>
```  

![将 chakrart 添加为链接器输入文件](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting_")  

如果你是从新的应用程序开始，你现在可以开始编写针对 JsRT API 的代码。  

## 使用 .NET 为首选版本编译  

如果你使用的是 .NET 和 P/Invoke，则必须更改 JsRT API [DllImport] 声明才能导入 chakra.dll 而不是 jscript9.dll。 此外，将 "定义" 更改 `JsCreateRuntime` 为 "删除参数 `JsRuntimeVersion` " 和 "定义" `JsCreateContext` ，然后 `JsStartDebugging` 删除 `IDebugApplication` 参数。  

对于旧版引擎，请使用以下代码。  

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

对于 Microsoft Edge 引擎，请使用以下代码。  

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
> 如果你通过 LoadLibrary/GetProcAddress) 手动封送函数指针 (例如，请务必不要混合该方法的声明，否则你将 unbalance 该堆栈，这将导致导致应用崩溃等不可预测的行为。 如果在导入代码中执行全局搜索和替换 jscript9.dll 的实例，则会出现相同的问题，因为你将错过 `version` 要删除的参数。  

## 摘要  

在 Windows 10 中，JavaScript 运行时托管 Api 将拆分为两个。 这些 Api 现在支持 "动态" Microsoft Edge 引擎，其语言功能将与 Microsoft Edge 中的 "生活" Microsoft Edge 引擎对齐。 你可以利用桌面或应用商店应用中的这些功能来创建新的、令人兴奋的方法来扩展你的应用程序，并利用现有基本代码中的新式 Web 技术。 但是，由于以前版本之间存在细微差异，因此在面向 Edge 或旧版引擎时，必须注意以下几点。  

*   你的应用只能支持每个进程的 JsRT 的一个版本。  
    
    例如，你无法创建 Microsoft Edge 引擎运行时，然后创建旧版引擎运行时，并希望它们在同一进程中正确运行。 这是不受支持的，可能会导致未记录的行为，例如加载第二个 DLL 失败。  
    
*   当面向 Microsoft Edge 引擎时，你的应用可能会在基础平台自动更新时意外获取新功能。  
    
    例如，旧版运行时的 Internet Explorer 11 模式支持块范围变量声明 `let` ，如和 `const` 。 如果 Microsoft Edge 引擎自动版本控制行为以前是标准的，则已在 Internet Explorer 10 模式下工作的代码在该平台自动升级时可能已开始失败。 在选择要使用的运行时模型时，必须考虑以下事项。 虽然我们认为你应该尽可能地确定 Microsoft Edge 引擎的目标，但你必须小心使用将来可能会无效的 JavaScript 代码结构。  
    
*   Windows 应用商店的 JsRT 仅支持 Microsoft Edge 引擎 ( # A0) 。 尝试链接到 jscript9.dll 中的任何 JsRT API 的应用将无法通过认证。  
*   请务必不要混淆 jscript9.dll 和 chakra.dll 之间的声明，这一点很重要 `JsCreateRuntime` `JsCreateContext` `JsStartDebugging` ，因为它会导致堆栈的 imbalancing。  
    
    使用 C 和 c + + 时，如果你尝试使用错误的声明，则会收到链接器错误，前提是你不执行诸如调用之类的操作 `LoadLibrary` `GetProcAddress` 。 .NET 开发人员可能不会很轻松地发现此问题，因此在使用此功能时，请仔细检查代码。  
    
## 另请参阅  

*   [JavaScript 运行时托管](../javascript-runtime-hosting.md)
 