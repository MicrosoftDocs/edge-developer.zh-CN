---
title: Windows 运行时类型 JavaScript 表示形式
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: 0ee55b5dd5071b0f0b31656ae164e9801e98d6ac
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942049"
---
# Windows 运行时类型 JavaScript 表示形式  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

下表描述了 JavaScript 表示 Windows 运行时类型的方式。  

> [!IMPORTANT]
> Windows 运行时功能不适用于在运行时运行Internet Explorer。  

## JavaScript 中的 Windows 运行时类型  

| Windows 运行时类型 | JavaScript 表示 | 描述 |  
|:--- |:--- |:--- |  
| `UInt8` | `Number` | Windows 运行时 `Uint8` 是无符号的 8 位整数，以 JavaScript 编号表示。  首先将 JavaScript 值转换为 JavaScript 编号，然后该 `ToUint32` 过程随后转换。  如果 JavaScript 数值超出 Uint8 范围，则结果将应用模块 2^8。  |  
| `Int32` | `Number` | Windows 运行时 `Int32` 是一个有符号的 32 位整数，表示为 JavaScript 编号。  首先将 JavaScript 值转换为 JavaScript 编号，然后该 `ToInt32` 过程随后转换。  如果 JavaScript 数字值超出项目范围， `Int32` 则结果将应用模块 2^16。  |  
| `Int64` | `Number` | Windows 运行时 `Int64` 是一个有符号的 64 位整数，如果位于范围内的 \[2^53， 2^53\]，则用作标准数字表示。  如果它位于此范围之外，则此值表示为具有自定义支持存储的数字值，该值维护整数数据的整数 64 位。  对这些自定义 Int64 数字值的所有数学运算都会导致值转换为区域 \[-2^53， 2^53\]中的标准数字。  如果值在此范围之外，将引发类型错误。  此转换过程的例外是，在传递两个表示 64 位值时，根据 `==` `===` `SameValue` 完整的 64 位对参数进行比 `RelationalComparison` 较。  如果任一参数是标准 JavaScript 编号，则在比较之前，这些操作还会将该参数转换为 JavaScript 号。  如果 JavaScript 值为 Int64 值本身，则直接分配它;否则，将转换应用于 `ToInteger` 值的结果传递给 Windows 运行时。  如果类型转换失败，则返回异常。  |  
| `Uint64` | `Number` | Windows 运行时 `Uint64` 是无符号的 64 位整数;如果位于范围内的 \[0， 2^53\]，则用标准数字表示。  如果它位于此范围之外，则此值表示为具有自定义备份存储的数字，该序列具有不签类整数数据的全部 64 位。  对这些自定义 Uint64 值的所有数学运算都会导致值转换为区域 \[0， 2^53\]中的标准数字。  如果值在此范围之外，将引发类型错误。  此转换过程的例外是，在传递两个 64 位值时，将基于完整 `==` `===` 的 64 位对参数 `SameValue` `RelationalComparison` 进行比较。  如果任一参数是标准 JavaScript 编号，则在比较之前，这些操作还会将该参数转换为 JavaScript 号。  如果 JavaScript 值为 Uint64 值本身，则直接分配它;否则，将转换应用于该值的结果 `ToInteger` （后跟模块 2^52）会传递到 Windows 运行时。  如果类型转换失败，则返回异常。  |  
| `Single` | `Number` | Windows 运行时是一个 32 位浮点数，由于将最接近的双精度值选取到单精度值，表示 `Single` 为 JavaScript 编号。  JavaScript 值转换为 JavaScript 号，然后进行检查的范围，以确保该值可在单精度 32 位 IEEE 754 浮点数中表示。  如果转换或范围检查失败，则返回边距错误。  |  
| `Double` | `Number` | Windows 运行时 `Double` 是一个 64 位浮点数。  `ToNumber` 用于将 Windows 运行时转换为 `Double` JavaScript 号码。  如果转换失败，则返回边距错误。  |  
| `Boolean` | `Boolean` | Windows 运行时 `Boolean` 是 8 位值，其中 0 和 `false` 零以外的任何值都 `true` 表示为 JavaScript。 `Boolean`  首先将 JavaScript 值转换为 `Boolean` `ToBoolean` JavaScript。  这意味着声明为可以使用 JavaScript 编写的 Windows `void func(BOOL);` 运行时函数 `obj.func("test");` 。  使用作为传递形式传递 `BOOL` 的参数调用 Windows 运行时 `TRUE` 函数。  如果转换失败，则返回边距错误。  |  
| `Char16` | `String` | Windows 运行时 `Char16` 是 16 位 Unicode 字符，表示为 JavaScript 字符串，该字符包含单个字符。  JavaScript 值将转换为 JavaScript 字符串 `ToString` ，然后进行检查，以确保该字符串长度仅一个字符。  然后将单个字符作为 `Char16` 值传递。  如果转换或长度检查失败，则返回一个边距错误。  |  
| `String` | `String` | Windows `String` 运行时是一个不可拟的对象 `Char16` 序列。  字符串表示为 JavaScript `String` 对象。  Windows 运行时字符串对于空字符串 `null` \ ("\) 。  `null` 和空字符串值将转换为 JavaScript 空字符串。  **注意**：当 JavaScript 传递到需要字符串的 Windows 运行时参数时，会得到字符串 `null` 值"null"，而不是将会创建空 `null` 字符串 \ ("\) 。  传递到 Windows 运行时的字符串应始终将其实例化为空字符串。  |  
| `Enumeration` | `Object` | Windows 运行时 `Enumeration` 是一个具有关联的命名常量的 32 ) 位整数 \ (有符号或未签名\控件。  在 JavaScript 中，枚举表示为一个对象，该对象包含每个命名值的只读字段。  枚举值将按前面定义和转换为 JavaScript 数字 `Int32` `UInt32` 。  当 JavaScript 值转换为 Windows 运行时枚举时，会将其转换、运行并按之前所述选中的范围。  但是，不会对枚举中指定的已定义命名值进行查看结果值。  |  
| `Structure` | `Object` | Windows 运行时 `Structure` 是命名数据字段的异类集合。  在 JavaScript 中，结构表示为一个 JavaScript 对象，该对象包含在结构中为每个字段包含一个命名属性。  如果任何结构值的转换失败，则返回一个重叠错误。  将忽略 JavaScript 对象中没有等效项的字段。  **注意**：Windows 运行时结构无法在包含关键字的 JavaScript 中 `new` 实例化。  |  
| `Array` | `Array` | Windows 运行时 `Array` 会转换为 JavaScript 数组。  但是，Windows 运行时数组不可调整大小，因此不可使用某些 JavaScript 数组操作。  转换数组 `[[Class]]` 的内部属性不设置为"数组"，因为 ECMAScript 5 规范不允许此属性。  这意味着 `Array.isArray(v)` 返回。 `false`  JavaScript 值转换为 Windows 运行时数组，如下所示：如果值 `null` 或 `undefined` ，它将转换为本机 `null` 。  如果内部属性 `[[Class]]` 是"数组"，则将其复制到本机数组并传递对此数组的引用。  如果是一个转换数组，如前所述，将传递基础本机数组。  **注意**：将 JavaScript 数组值传递到 Windows 运行时方法会导致数组的完整副本。  |  
| 委有 \ (回调\)  | `Function` | Windows 运行时委理是对单个方法的引用。  Windows 运行时委委注册以 JavaScript 形式表示，以适当的会话 `Function` 调用。  调用 `Function` 后，参数将转换为等效的 Windows 运行时参数类型。  如果的 JavaScript 参数少于代理 `in` 参数，则委代调用将失败。  如果有多于委g中的参数数量的 JavaScript 参数，则将忽略额外的 `in` JavaScript 参数。  在调用委Ggeg 后， `out` 参数将转换为 JavaScript 类型并返回。  如果一个本机 JavaScript 函数对象转换为 Windows 运行时委委注册，它将包在对应类型的 Windows 运行时委委集中。  调用委Ggeg 时， `in` 参数将转换为 JavaScript 类型。  在调用委Gate 之后，返回值将转换 `out` 为委g的参数。  |  
| 接口 | `Object` | 界面和接口组并不以对象的形式直接表示在 JavaScript 中。  但是，接口表示为参数，并返回 Windows 运行时方法的返回类型。  Windows 运行时接口实例如下转换：<br /> <br /> 1. 如果有效运行时类，则该对象将表示为该类的实例。<br /> 2. 如果没有有效的运行时类，则将该对象表示为一个未命名运行时类的实例，该类实际实现该实例所知该实例所知称为实现的接口及其所需的接口。<br /> <br /> 对 JavaScript 值进行测试，确定它是运行时类还是接口的一个实例。  如果是，而原始的 Windows 运行时值实现接口，则会将该对象传递给 Windows 运行时。  |  
| 运行时类 | `Object` | Windows 运行时中的对象可以是实现一个或多个接口的运行时类的实例。  Windows 运行时对象以 JavaScript 表示为对象。  在所有类的实现接口上定义的方法、属性和事件的联合表示 JavaScript 对象的原型中的命名属性。  JavaScript 消费者可以直接访问类的任何成员。  Windows 运行时对象具有一个原型，该原型包含来自运行时类上所有实现接口的所有成员。  |  
  
## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft 文档"  
