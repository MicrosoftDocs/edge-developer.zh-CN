---
title: Windows 运行时类型的 JavaScript 表示形式
ms.custom: ''
ms.date: 04/01/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Runtime types [JavaScript]
- JavaScript, Windows Runtime types
ms.assetid: f4851802-8b40-4afa-ba6c-8a162a9a43cc
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b76c28d3448b8be6fbef1fd7e23b07b2eff8d087
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564588"
---
# Windows 运行时类型的 JavaScript 表示形式  

下表介绍了 JavaScript 表示 Windows 运行时类型的方式。  

> [!IMPORTANT]
> 对于在 Internet Explorer 中运行的应用，Windows 运行时功能不可用。  

## JavaScript 中的 Windows 运行时类型  

| Windows 运行时类型 | JavaScript 表示 | 描述 |  
|:--- |:--- |:--- |  
| `UInt8` | `Number` | Windows 运行时 `Uint8` 是一个无符号的8位整数，表示为 JavaScript 编号。  JavaScript 值首先转换为 JavaScript 编号，然后 `ToUint32` 遵循该流程。  如果 JavaScript number 值超出 Uint8 的范围，则结果将应用模数 2 ^ 8。 |  
| `Int32` | `Number` | Windows 运行时 `Int32` 是一个已签名的32位整数，表示为 JavaScript 编号。  JavaScript 值首先转换为 JavaScript 编号，然后 `ToInt32` 遵循该流程。  如果 JavaScript number 值位于 a 范围之外 `Int32` ，结果将应用模数 2 ^ 16。 |  
| `Int64` | `Number` | Windows 运行时 `Int64` 是有符号的64位整数，表示为标准数字（如果它位于范围 \ [-2 ^ 53、2 ^ 53 \] 内）。  如果它超出此范围，则表示为一个数字值，其中包含一个自定义后备存储，该存储保留整数数据的完整64位。  对这些自定义 Int64 数字值的所有数学运算均会将该值转换为从 \ [-2 ^ 53，2 ^ 53 \] 范围内的标准数字。  如果该值超出此范围，则引发类型错误。  此转换过程的例外是、、 `==` `===` `SameValue` 和 `RelationalComparison` 操作，它们在传递两个表示的64位值时基于完整的64位比较参数。  如果任一参数是标准 JavaScript 编号，这些操作还会在比较之前将参数转换为 JavaScript 编号。  如果它是 Int64 值本身，则会直接分配 JavaScript 值;否则，对值应用转换的结果 `ToInteger` 将传递到 Windows 运行时。  如果类型强制失败，则会返回异常。 |  
| `Uint64` | `Number` | Windows 运行时 `Uint64` 是一个无符号的64位整数，表示为标准数字（如果它位于范围 \ [0，2 ^ 53 \] 内）。  如果它超出此范围，则表示为具有自定义后备存储的数字，该存储保留无符号整数数据的完整64位。  对这些自定义 Uint64 值的所有数学运算均会将该值转换为从 \ [0，2 ^ 53 \] 范围内的标准数字。  如果该值超出此范围，则引发类型错误。  此转换过程的例外是、、 `==` `===` `SameValue` 和 `RelationalComparison` 操作，它们在传递 2 64 位值时基于完整的64位比较参数。  如果任一参数是标准 JavaScript 编号，这些操作还会在比较之前将参数转换为 JavaScript 编号。  如果它是 Uint64 值本身，则会直接分配 JavaScript 值;否则， `ToInteger` 对值应用转换的结果，然后将模数 2 ^ 52 传递到 Windows 运行时。  如果类型转换失败，则会返回异常。 |  
| `Single` | `Number` | Windows 运行时 `Single` 是32位浮点数，表示为 JavaScript 编号，方法是将最接近的双精度值拖到单精度值中。  JavaScript 值转换为 JavaScript 编号，然后进行范围检查，以确保该值可以用单精度32位 IEEE 754 浮点数字表示。  如果转换或范围检查失败，则会返回封送处理错误。 |  
| `Double` | `Number` | Windows 运行时 `Double` 是64位浮点数字。  `ToNumber` 用于将 Windows 运行时转换 `Double` 为 JavaScript 编号。  如果转换失败，则会返回封送处理错误。 |  
| `Boolean` | `Boolean` | Windows 运行时 `Boolean` 是8位值，其中0是零， `false` 而任何非零的值都是 `true` 以 JavaScript 的形式表示 `Boolean` 。  JavaScript 值首先被转换为 JavaScript `Boolean` `ToBoolean` 。  这意味着，声明为的 Windows 运行时函数 `void func(BOOL);` 可以在 JavaScript 中写入 `obj.func("test");` 。  通过传递的参数调用 Windows 运行时函数 `BOOL` `TRUE` 。  如果转换失败，则会返回封送处理错误。 |  
| `Char16` | `String` | Windows 运行时 `Char16` 是一个16位 Unicode 字符，表示为包含单个字符的 JavaScript 字符串。  JavaScript 值转换为 JavaScript 字符串 `ToString` ，然后进行检查，以确保字符串仅为一个字符长度。  然后将单个字符作为 `Char16` 值传递。  如果转换或长度检查失败，则会返回封送处理错误。 |  
| `String` | `String` | Windows 运行时 `String` 是对象的不可变序列 `Char16` 。  字符串表示为 JavaScript `String` 对象。  对于和空字符串，Windows 运行时字符串不具有不同的值 `null` \ （"" \）。  `null` 和空字符串值转换为 JavaScript 空字符串。  注意：当 JavaScript `null` 传递到需要字符串的 Windows 运行时参数时，它将生成字符串值 "null"，而不是 `null` 空字符串 \ （"" \ "）。  传递到 Windows 运行时的字符串应始终实例化为空字符串。 |  
| `Enumeration` | `Object` | Windows 运行时 `Enumeration` 是具有关联的命名常量集的32位整数 \ （有符号 \）。  在 JavaScript 中，枚举表示为一个对象，其中包含每个已命名值的只读字段。  枚举值转换为和的之前定义的 JavaScript 数字 `Int32` `UInt32` 。  当 JavaScript 值转换为 Windows 运行时枚举时，将按上文所述对其进行转换、截断和范围检查。  但是，不对照枚举中指定的已定义命名值检查结果值。 |  
| `Structure` | `Object` | Windows 运行时 `Structure` 是已命名的数据字段的异类集合。  在 JavaScript 中，结构表示为一个 JavaScript 对象，该对象包含结构中每个字段的命名属性。  如果转换任何结构值失败，则会返回封送处理错误。  在 Windows 运行时结构中不具有等效项的 JavaScript 对象中的字段将被忽略。  注意：无法在具有关键字的 JavaScript 中实例化 Windows 运行时结构 `new` 。 |  
| `Array` | `Array` | 将 Windows 运行时 `Array` 转换为 JavaScript 数组。  但是，Windows 运行时数组不能调整大小，因此某些 JavaScript 数组操作是不可能的。  `[[Class]]`已转换数组的 internal 属性未设置为 "array"，因为 ECMAScript 5 规范不允许这样做。  这意味着该 `Array.isArray(v)` 返回 `false` 。  JavaScript 值转换为 Windows 运行时数组，如下所示：如果值为 `null` 或 `undefined` ，则将其转换为本机 `null` 。  如果其内部 `[[Class]]` 属性为 "Array"，则将其复制到本机数组，并传递对此数组的引用。  如果它是转换后的数组（如前面所述），则传递基础本机数组。  注意：将 JavaScript 数组值传递到 Windows 运行时方法会导致该数组的完整副本。 |  
| 委派 \ （函数回调 \） | `Function` | Windows 运行时委托是对单个方法的引用。  Windows 运行时委托在 JavaScript 中表示为 JavaScript `Function` ，确保在正确的线程上调用。  调用时 `Function` ，参数将转换为等效的 Windows 运行时参数类型。  如果 JavaScript 参数比委托 `in` 参数少，则代理人调用失败。  如果存在的 JavaScript 参数比 `in` 委托中的参数多，则忽略额外的 javascript 参数。  调用委托后， `out` 参数将转换为 JavaScript 类型并返回。  如果将本机 JavaScript 函数对象转换为 Windows 运行时委托，则会将其包装在对应类型的 Windows 运行时委托中。  调用委托时， `in` 参数将转换为 JavaScript 类型。  调用委托后，返回值转换为 `out` 委托的参数。 |  
| 接口 | `Object` | 接口和接口组不直接在 JavaScript 中表示为对象。  但是，接口表示为 Windows 运行时方法的参数和返回类型。  Windows 运行时接口实例按如下方式进行转换：<br /> <br /> 1. 如果存在有效的运行时类，则将该对象表示为该类的实例。<br /> 2. 如果没有有效的运行时类，则将对象表示为一个未命名的运行时类的实例，该实例仅实现该实例已知要实现的接口以及它所需的接口。<br /> <br /> 将对 JavaScript 值进行测试以确定它是否为运行时类或接口的实例。  如果是，并且原始 Windows 运行时值实现了该接口，则会将该对象传递到 Windows 运行时。 |  
| 运行时类 | `Object` | Windows 运行时中的对象可以是实现一个或多个接口的运行时类的实例。  Windows 运行时对象在 JavaScript 中表示为对象。  在类的所有已实现接口上定义的方法、属性和事件的联合均表示 JavaScript 对象原型中的命名属性。  JavaScript 使用者可以直接访问该类的任何成员。  Windows 运行时对象具有一个原型，其中包含运行时类的所有已实现接口中的所有成员。 |  
  
## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "在 JavaScript 中使用 Windows 运行时"  
