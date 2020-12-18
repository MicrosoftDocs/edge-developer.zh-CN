---
description: Windows 运行时类型的 JavaScript 表示形式。
title: Windows 运行时类型 JavaScript 表示形式
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- Windows Runtime types [JavaScript]
- JavaScript, Windows Runtime types
ms.assetid: f4851802-8b40-4afa-ba6c-8a162a9a43cc
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1fd6c8831b2c98cea5794866a0f8830d8f557723
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232743"
---
# Windows 运行时类型 JavaScript 表示形式  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

下表介绍了 JavaScript 表示 Windows 运行时类型的方式。  

> [!IMPORTANT]
> Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。  

## JavaScript 中的 Windows 运行时类型  

| Windows 运行时类型 | JavaScript 表示形式 | 描述 |  
|:--- |:--- |:--- |  
| `UInt8` | `Number` | Windows 运行时 `Uint8` 是一个无符号 8 位整数，表示为 JavaScript 数字。  JavaScript 值首先转换为 JavaScript 数字，然后 `ToUint32` 执行此过程。  如果 JavaScript 数字值超出 Uint8 的范围，则结果将应用模数 2^8。  |  
| `Int32` | `Number` | Windows 运行时 `Int32` 是一个 32 位有符号整数，表示为 JavaScript 数字。  JavaScript 值首先转换为 JavaScript 数字，然后 `ToInt32` 执行此过程。  如果 JavaScript 数字值超出一个范围，则结果将应用 `Int32` 模数 2^16。  |  
| `Int64` | `Number` | Windows 运行时是一个有符号的 64 位整数，如果其位于 `Int64` \[-2^53， 2^53\] 范围内，则表示为标准数字。  如果超出此范围，则它表示为一个数字值，该数字具有用于维护完整 64 位整数数据的自定义备份存储。  这些自定义 Int64 数字值的所有数学运算都会导致值转换为 \[-2^53， 2^53\] 范围中的标准数字。  如果值超出此范围，则引发类型错误。  此转换过程的例外情况是 ， 和操作，它们根据传递的两个表示的 64 位值时基于完整的 `==` `===` 64 位来 `SameValue` `RelationalComparison` 比较参数。  如果任一参数是标准 JavaScript 编号，则这些操作还会在比较之前将参数转换为 JavaScript 数字。  如果是 Int64 值本身，则直接分配 JavaScript 值;否则，对值应用 `ToInteger` 转换的结果将传递给 Windows 运行时。  如果类型强制失败，则返回异常。  |  
| `Uint64` | `Number` | Windows 运行时是一个无符号 64 位整数，如果位于 `Uint64` \[0， 2^53\] 范围内，则表示为标准数字。  如果超出此范围，则它表示为一个数字，该数字具有一个自定义备份存储，该存储可维护完整的 64 位无符号整数数据。  这些自定义 Uint64 值的所有数学运算都会导致值转换为 \[0， 2^53\] 范围中的标准数字。  如果值超出此范围，则引发类型错误。  此转换过程的例外情况是 ， 和操作，它们根据传递两个 64 位值时的完整 `==` `===` 64 位来 `SameValue` `RelationalComparison` 比较参数。  如果任一参数是标准 JavaScript 编号，则这些操作还会在比较之前将参数转换为 JavaScript 数字。  如果是 Uint64 值本身，则直接分配 JavaScript 值;否则，对值应用转换的结果，然后采用 `ToInteger` modulo 2^52，将传递到 Windows 运行时。  如果类型转换失败，则返回异常。  |  
| `Single` | `Number` | Windows 运行时是一个 32 位浮点数，通过选取最接近单精度值的双精度值来表示为 `Single` JavaScript 数字。  JavaScript 值将转换为 JavaScript 数字，然后检查范围以确保该值可以使用单精度 32 位 IEEE 754 浮点数表示。  如果转换或区域检查失败，则返回封送错误。  |  
| `Double` | `Number` | Windows 运行时 `Double` 是 64 位浮点数。  `ToNumber` 用于将 Windows 运行时 `Double` 转换为 JavaScript 号码。  如果转换失败，则返回封送错误。  |  
| `Boolean` | `Boolean` | Windows 运行时是一个 8 位值，其中零为，除零值外的任何值都表示 `Boolean` `false` 为 `true` `Boolean` JavaScript。  JavaScript 值首先被转换为 `Boolean` `ToBoolean` JavaScript。  这意味着声明为的 Windows 运行时函数可以在 JavaScript 中编写 `void func(BOOL);` 为 `obj.func("test");` 。  调用 Windows 运行时函数时， `BOOL` 参数传递为 `TRUE` 。  如果转换失败，则返回封送错误。  |  
| `Char16` | `String` | Windows 运行时 `Char16` 是一个 16 位 Unicode 字符，表示为包含单个字符的 JavaScript 字符串。  JavaScript 值将转换为 JavaScript 字符串，然后进行检查以确保该字符串只有一 `ToString` 个字符长。  然后，将单个字符作为值 `Char16` 传递。  如果转换或长度检查失败，则返回封送错误。  |  
| `String` | `String` | Windows 运行时 `String` 是对象的不可变 `Char16` 序列。  字符串表示为 JavaScript `String` 对象。  Windows 运行时字符串没有不同的值和空 `null` 字符串 \ (""\) 。  `null` 空字符串值转换为 JavaScript 空字符串。  **注意**：当 JavaScript 传递给需要字符串的 Windows 运行时参数时，它将生成字符串值 `null` "null"，而不是空字符串 `null` \ (""\) 。  传递给 Windows 运行时的字符串应始终实例化为空字符串。  |  
| `Enumeration` | `Object` | Windows 运行时 `Enumeration` 是一个 32 位整数 \ (有符号或无符号\) ，具有一组关联的命名常量。  在 JavaScript 中，枚举表示为包含每个命名值的只读字段的对象。  枚举值将转换为 JavaScript 数字，如前面为 `Int32` 和 所定义 `UInt32` 。  当 JavaScript 值转换为 Windows 运行时枚举时，它将被转换、截断并检查范围，如前面所述。  但是，不会针对枚举中指定的已定义命名值检查生成的值。  |  
| `Structure` | `Object` | Windows 运行时 `Structure` 是命名数据字段的异类集合。  在 JavaScript 中，结构表示为 JavaScript 对象，该对象包含结构中每个字段的命名属性。  如果任何结构值的转换失败，则返回封送错误。  在 Windows 运行时结构中没有等效项的 JavaScript 对象中的字段将被忽略。  **注意**：无法在 JavaScript 中使用关键字实例化 Windows 运行时 `new` 结构。  |  
| `Array` | `Array` | Windows 运行时 `Array` 将转换为 JavaScript 数组。  但是，Windows 运行时数组不可调整大小，因此无法执行某些 JavaScript 数组操作。  转换 `[[Class]]` 后的数组的内部属性未设置为"Array"，因为 ECMAScript 5 规范不允许这样做。  这意味着返回 `Array.isArray(v)` `false` 。  JavaScript 值转换为 Windows 运行时数组，如下所示：如果值是 `null` 或，则转换为 `undefined` 本机。 `null`  如果内部 `[[Class]]` 属性为"Array"，则它将复制到本机数组，并传递对此数组的引用。  如果它是一个已转换的数组（如前面所述，则传递基础本机数组）。  **注意**：将 JavaScript 数组值传递给 Windows 运行时方法将导致数组的完整副本。  |  
| Delegate \ (function callback\)  | `Function` | Windows 运行时委托是对单个方法的引用。  Windows 运行时委托在 JavaScript 中表示为 JavaScript，它保证在正确的 `Function` 线程上调用。  调用 `Function` 时，参数将转换为等效的 Windows 运行时参数类型。  如果 JavaScript 参数少于委派参数 `in` ，则委派调用将失败。  如果 JavaScript 参数数多于委托中的参数数，则 `in` 忽略额外的 JavaScript 参数。  调用委托后， `out` 参数将转换为 JavaScript 类型并返回。  如果将本机 JavaScript 函数对象转换为 Windows 运行时委托，它将包装在相应类型的 Windows 运行时委托中。  调用委托时， `in` 参数将转换为 JavaScript 类型。  调用委托后，返回值将转换为委托 `out` 的参数。  |  
| 接口 | `Object` | 接口和接口组在 JavaScript 中不直接表示为对象。  但是，接口表示为参数并返回 Windows 运行时方法的类型。  Windows 运行时接口实例的转换方式如下：<br /> <br /> 1. 如果存在有效的运行时类，则以该类的实例表示该对象。<br /> 2. 如果没有有效的运行时类，将对象表示为未命名运行时类的实例，该类完全实现该实例已知的要实现接口及其所需接口。<br /> <br /> 测试 JavaScript 值以确定它是运行时类的实例还是接口。  如果是，并且原始 Windows 运行时值实现接口，则对象将传递到 Windows 运行时。  |  
| 运行时类 | `Object` | Windows 运行时中的对象可以是实现一个或多个接口的运行时类的实例。  Windows 运行时对象在 JavaScript 中表示为对象。  在类的所有实现接口上定义的方法、属性和事件联合表示 JavaScript 对象原型中的命名属性。  JavaScript 使用者可以直接访问该类的任何成员。  Windows 运行时对象具有一个原型，其中包含运行时类的所有实现接口中的所有成员。  |  
  
## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  
