---
title: JavaScript 版本信息
description: 在 Microsoft Edge、Microsoft Store 应用和 Internet Explorer 中比较 JavaScript 支持
ms.date: 03/05/2020
ms.prod: microsoft-edge
ms.topic: language-reference
author: MSEdgeTeam
ms.author: msedgedevrel
keywords: edge、ie、chakra、jscript、wwa、应用商店应用
ms.custom: seodec18
ms.openlocfilehash: 0edc5769cf80ae9a7ac741c0f478f9ca639d935f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563003"
---
# JavaScript 版本信息  

JavaScript 支持因 Microsoft Edge、Microsoft Store 应用和 Internet Explorer 的不同文档模式而异。 有关 IE 文档代码版本控制的详细信息，请参阅[*定义文档兼容性*](https://go.microsoft.com/fwlink/p/?LinkId=208537)。  

下表总结了跨 Internet Explorer、Microsoft Edge 和 Microsoft Store 应用的 JavaScript 支持。  
  
> [!IMPORTANT]
> 实验功能 \ （从 "*标志*\" 启用）由 "Exp" 表示。 在某些情况下，应用*商店应用*支持在 windows 8 \ （v8 \）和 windows 10 \ （v10 \）应用以及 windows desktop \ （Win \）和 windows phone \ （Phone \）之间有所不同，如所示。  
  
 | 语言元素 | 兼容，Internet Explorer 6 标准，Internet Explorer 7 标准 | Internet Explorer 8 标准 | Internet Explorer 9 标准 | Internet Explorer 10 标准 | Internet Explorer 11 标准 | Microsoft Edge | 应用商店应用 |  
 |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |  
| [__proto \ _ \ _ 属性（对象）](/scripting/javascript/reference/proto-property-object-javascript) | N | N | N | N | Y | Y | v8 （Win）： N <br /> v 8.1 （Win）： Y <br /> v 8.1 （电话）： Y |  
| [$ 1 ... $ 9 属性（RegExp）](/scripting/javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [0n 属性](/scripting/javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [abs 函数](/scripting/javascript/reference/math-abs-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [acos 函数](/scripting/javascript/reference/math-acos-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [acosh 函数](/scripting/javascript/reference/math-acosh-function-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [ActiveXObject 对象](/scripting/javascript/reference/activexobject-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [加法赋值运算符（+ =）](/scripting/javascript/reference/addition-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [加法运算符（+）](/scripting/javascript/reference/addition-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [apply 方法](/scripting/javascript/reference/apply-method-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [arguments 对象](/scripting/javascript/reference/arguments-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [arguments 属性](/scripting/javascript/reference/arguments-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Array 对象](/scripting/javascript/reference/array-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Array。 from 函数（Array）](/scripting/javascript/reference/array-from-function-array-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [IsArray 函数](/scripting/javascript/reference/array-isarray-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [函数数组（数组）](/scripting/javascript/reference/array-of-function-array-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [ArrayBuffer 对象](/scripting/javascript/reference/arraybuffer-object) | N | N | N | Y | Y | Y | Y |  
| [函数](/scripting/javascript/functions-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [asin 函数](/scripting/javascript/reference/math-asin-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Object。 assign 函数（Object）](/scripting/javascript/reference/object-assign-function-object-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [赋值运算符（=）](/scripting/javascript/reference/assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atan 函数](/scripting/javascript/reference/math-atan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atan2 函数](/scripting/javascript/reference/math-atan2-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atEnd 方法](/scripting/javascript/reference/atend-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [bind 方法](/scripting/javascript/reference/bind-method-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [按位与赋值运算符（&=）](/scripting/javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位 AND 运算符（&）](/scripting/javascript/reference/bitwise-and-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位左移位运算符（< \ <）](/scripting/javascript/reference/bitwise-left-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位非运算符（~）](/scripting/javascript/reference/bitwise-not-operator-decrement-tilde-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位 "或" 赋值运算符（&#124;=）](/scripting/javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位 OR 运算符（&#124;）](/scripting/javascript/reference/bitwise-or-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位右移位运算符（>>）](/scripting/javascript/reference/bitwise-right-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位 GMAIL 赋值运算符（^ =）](/scripting/javascript/reference/bitwise-xor-assignment-operator-decrement-hat-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [按位 GMAIL 运算符（^）](/scripting/javascript/reference/bitwise-xor-operator-decrement-hat-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [闪烁方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [bold 方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Boolean 对象](/scripting/javascript/reference/boolean-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [break 语句](/scripting/javascript/reference/break-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [call 方法](/scripting/javascript/reference/call-method-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [被调用方属性](/scripting/javascript/reference/callee-property-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [来电显示属性](/scripting/javascript/reference/caller-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [catch 语句](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ceil 函数](/scripting/javascript/reference/math-ceil-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [charAt 方法](/scripting/javascript/reference/charat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [charCodeAt 方法](/scripting/javascript/reference/charcodeat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [class 语句](/scripting/javascript/reference/class-statement-javascript) | N | N | N | N | N | Exp. | v 8.1： N <br /> v10： Exp。 |  
| [codePointAt 方法（字符串）](/scripting/javascript/reference/codepointat-method-string-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [逗号运算符（，）](/scripting/javascript/reference/comma-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [（单行注释语句）](/scripting/javascript/reference/comment-statements-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [/*..\ */（多行注释语句）](/scripting/javascript/reference/comment-statements-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [比较运算符](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [compile 方法](/scripting/javascript/reference/compile-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [concat 方法（Array）](/scripting/javascript/reference/concat-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [concat 方法（字符串）](/scripting/javascript/reference/concat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [条件编译](/scripting/javascript/advanced/conditional-compilation-javascript) | Y | Y | Y | Y | N | N | N |  
| [条件编译变量](/scripting/javascript/advanced/conditional-compilation-variables-javascript) | Y | Y | Y | Y | N | N | N |  
| [条件（三元）运算符（？:)](/scripting/javascript/reference/conditional-ternary-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [构造函数属性](/scripting/javascript/reference/constructor-property-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [const 语句](/scripting/javascript/reference/const-statement-javascript) | N | N | N | N | Y | Y | v8 （Win）： N <br /> v 8.1 （Win）： Y <br /> v 8.1 （电话）： Y |  
| [continue 语句](/scripting/javascript/reference/continue-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [cos 函数](/scripting/javascript/reference/math-cos-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [create 函数](/scripting/javascript/reference/object-create-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [DataView 对象](/scripting/javascript/reference/dataview-object) | N | N | N | Y | Y | Y | Y |  
| [Date 对象](/scripting/javascript/reference/date-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [调试对象](/scripting/javascript/reference/debug-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [SetNonUserCodeExceptions 属性](/scripting/javascript/reference/debug-setnonusercodeexceptions-property) | N | N | N | Y | Y | Y | Y |  
| [SetNonUserCodeExceptions 属性](/scripting/javascript/reference/debug-setnonusercodeexceptions-property) | N | N | N | Y | Y | Y | Y |  
| [调试器语句](/scripting/javascript/reference/debugger-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [decodeURI 函数](/scripting/javascript/reference/decodeuri-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [DecodeURIComponent 函数](/scripting/javascript/reference/decodeuricomponent-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [减量运算符（--）](/scripting/javascript/reference/increment-and-decrement-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [函数](/scripting/javascript/functions-javascript) | N | N | N | N | N | Exp. | v 8.1： N <br /> v10： Exp。 |  
| [defineProperties 函数](/scripting/javascript/reference/object-defineproperties-function-javascript) | N | X-y | Y | Y | Y | Y | Y |  
| [defineProperty 函数](/scripting/javascript/reference/object-defineproperty-function-javascript) | N | X-y | Y | Y | Y | Y | Y |  
| [删除操作员](/scripting/javascript/reference/delete-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [description 属性](/scripting/javascript/reference/description-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [维度方法](/scripting/javascript/reference/dimensions-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [除法赋值运算符（/=）](/scripting/javascript/reference/division-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [除法运算符（/）](/scripting/javascript/reference/division-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [待办事项 .。。while 语句](/scripting/javascript/reference/do-dot-dot-dot-while-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [E 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [encodeURI 函数](/scripting/javascript/reference/encodeuri-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [encodeURI Component 函数](/scripting/javascript/reference/encodeuricomponent-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [entries 方法（Array）](/scripting/javascript/reference/entries-method-array-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [枚举器对象](/scripting/javascript/reference/enumerator-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [数字常量](/scripting/javascript/reference/number-constants-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [相等运算符（= =）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Error 对象](/scripting/javascript/reference/error-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [stack 属性（错误）](/scripting/javascript/reference/stack-property-error-javascript) | N | N | N | Y | Y | Y | Y |  
| [stackTraceLimit 属性（错误）](/scripting/javascript/reference/stacktracelimit-property-error-javascript) | N | N | N | Y | Y | Y | Y |  
| [escape 函数](/scripting/javascript/reference/escape-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [eval 函数](/scripting/javascript/reference/eval-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [exec 方法](/scripting/javascript/reference/exec-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [每个方法](/scripting/javascript/reference/every-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [exp 函数](/scripting/javascript/reference/math-exp-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fill 方法（数组）](/scripting/javascript/reference/fill-method-array-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [filter 方法](/scripting/javascript/reference/filter-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [finally 语句](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [findIndex 方法（Array）](/scripting/javascript/reference/findindex-method-array-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [固定方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Float32Array 对象](/scripting/javascript/reference/float32array-object) | N | N | N | Y | Y | Y | Y |  
| [Float64Array 对象](/scripting/javascript/reference/float64array-object) | N | N | N | Y | Y | Y | Y |  
| [floor 函数](/scripting/javascript/reference/math-floor-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fontcolor 方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fontsize 方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [for 语句](/scripting/javascript/reference/for-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [forEach 方法](/scripting/javascript/reference/foreach-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [对于 .。。in 语句](/scripting/javascript/reference/for-dot-dot-dot-in-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [对于 .。。语句](/scripting/javascript/reference/for-dot-dot-dot-of-statement-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [冻结函数](/scripting/javascript/reference/object-freeze-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [fromCharCode 函数](/scripting/javascript/reference/string-fromcharcode-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fromCodePoint 函数](/scripting/javascript/reference/string-fromcodepoint-function-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [函数对象](/scripting/javascript/reference/function-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [函数语句](/scripting/javascript/reference/function-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [生成器](/scripting/javascript/advanced/iterators-and-generators-javascript) | N | N | N | N | N | Exp. | v 8.1： N <br /> v10： Exp。 |  
| [getDate 方法](/scripting/javascript/reference/getdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getDay 方法](/scripting/javascript/reference/getday-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getFullYear 方法](/scripting/javascript/reference/getfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getHours 方法](/scripting/javascript/reference/gethours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getItem 方法](/scripting/javascript/reference/getitem-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMilliseconds 方法](/scripting/javascript/reference/getmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMinutes 方法](/scripting/javascript/reference/getminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMonth 方法](/scripting/javascript/reference/getmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [GetObject 函数](/scripting/javascript/reference/getobject-function-javascript) | Y | Y | N | N | N | N | N |  
| [getOwnPropertyDescriptor 函数](/scripting/javascript/reference/object-getownpropertydescriptor-function-javascript) | N | X-y | Y | Y | Y | Y | Y |  
| [getOwnPropertyNames 函数](/scripting/javascript/reference/object-getownpropertynames-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [getPrototypeOf 函数](/scripting/javascript/reference/object-getprototypeof-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [getSeconds 方法](/scripting/javascript/reference/getseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getTime 方法](/scripting/javascript/reference/gettime-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getTimezoneOffset 方法](/scripting/javascript/reference/gettimezoneoffset-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCDate 方法](/scripting/javascript/reference/getutcdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCDay 方法](/scripting/javascript/reference/getutcday-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCFullYear 方法](/scripting/javascript/reference/getutcfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCHours 方法](/scripting/javascript/reference/getutchours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMilliseconds 方法](/scripting/javascript/reference/getutcmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMinutes 方法](/scripting/javascript/reference/getutcminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMonth 方法](/scripting/javascript/reference/getutcmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCSeconds 方法](/scripting/javascript/reference/getutcseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getVarDate 方法](/scripting/javascript/reference/getvardate-method-date-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [getYear 方法](/scripting/javascript/reference/getyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [全局对象](/scripting/javascript/reference/global-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [全局属性](/scripting/javascript/reference/global-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [大于运算符（>）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [大于或等于运算符（>=）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [hasOwnProperty 方法](/scripting/javascript/reference/hasownproperty-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [HTML 标记方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [hypot 函数](/scripting/javascript/reference/math-hypot-function-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [标识运算符（= = =）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [if .。。else 语句](/scripting/javascript/reference/if-dot-dot-dot-else-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ignoreCase 属性](/scripting/javascript/reference/ignorecase-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [imul 函数](/scripting/javascript/reference/math-imul-function-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [In 运算符](/scripting/javascript/reference/in-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [包含方法（字符串）](/scripting/javascript/reference/includes-method-string-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [增量运算符（+ +）](/scripting/javascript/reference/increment-and-decrement-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [index 属性](/scripting/javascript/reference/index-property-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [indexOf 方法（Array）](/scripting/javascript/reference/indexof-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [indexOf 方法（字符串）](/scripting/javascript/reference/indexof-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [不等运算符（！ =）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [无穷大常量](/scripting/javascript/reference/infinity-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [input 属性（$ _）](/scripting/javascript/reference/input-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [instanceof 运算符](/scripting/javascript/reference/instanceof-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Int8Array 对象](/scripting/javascript/reference/int8array-object) | N | N | N | Y | Y | Y | Y |  
| [Int16Array 对象](/scripting/javascript/reference/int16array-object) | N | N | N | Y | Y | Y | Y |  
| [Int32Array 对象](/scripting/javascript/reference/int32array-object) | N | N | N | Y | Y | Y | Y |  
| [国际的排序和对象](/scripting/javascript/reference/intl-collator-object-javascript) | N | N | N | N | Y | Y | v8 （Win）： N <br /> v 8.1 （Win）： Y <br /> v 8.1 （电话）： Y |  
| [国际 DateTimeFormat 对象](/scripting/javascript/reference/intl-datetimeformat-object-javascript) | N | N | N | N | Y | Y | v8： N <br /> v 8.1： Y |  
| [国际 NumberFormat 对象](/scripting/javascript/reference/intl-numberformat-object-javascript) | N | N | N | N | Y | Y | v8： N <br /> v 8.1： Y |  
| [isFinite 函数](/scripting/javascript/reference/isfinite-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isArray 函数](/scripting/javascript/reference/array-isarray-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [IsExtensible 函数](/scripting/javascript/reference/object-isextensible-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [isFrozen 函数](/scripting/javascript/reference/object-isfrozen-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [isInteger 函数](/scripting/javascript/reference/number-isinteger-function-number-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [isNaN 函数](/scripting/javascript/reference/isnan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isNaN 函数（Number）](/scripting/javascript/reference/number-isnan-function-number-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [ISO 日期格式](/scripting/javascript/date-and-time-strings-javascript) | N | N | Y | Y | Y | Y | Y |  
| [IsPrototypeOf 方法](/scripting/javascript/reference/isprototypeof-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isSealed 函数](/scripting/javascript/reference/object-issealed-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [斜体方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [迭代](/scripting/javascript/advanced/iterators-and-generators-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [item 方法](/scripting/javascript/reference/item-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [联接方法](/scripting/javascript/reference/join-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON 对象](/scripting/javascript/reference/json-object-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [键函数](/scripting/javascript/reference/object-keys-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [键方法（数组）](/scripting/javascript/reference/keys-method-array-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [标记语句](/scripting/javascript/reference/labeled-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastIndex 属性](/scripting/javascript/reference/lastindex-property-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastIndexOf 方法（Array）](/scripting/javascript/reference/lastindexof-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [lastIndexOf 方法（字符串）](/scripting/javascript/reference/lastindexof-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastMatch 属性（$&）](/scripting/javascript/reference/lastmatch-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastParen 属性（$ +）](/scripting/javascript/reference/lastparen-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lbound 方法](/scripting/javascript/reference/lbound-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [leftContext 属性（$ '）](/scripting/javascript/reference/leftcontext-property-dollar-grave-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [左移位赋值运算符（<<=）](/scripting/javascript/reference/left-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length 属性（参数）](/scripting/javascript/reference/length-property-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length 属性（数组）](/scripting/javascript/reference/length-property-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length 属性（函数）](/scripting/javascript/reference/length-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length 属性（字符串）](/scripting/javascript/reference/length-property-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [小于运算符（<）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [小于或等于运算符（<=）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [let 语句](/scripting/javascript/reference/let-statement-javascript) | N | N | N | N | Y | Y | v8： N <br /> v 8.1： Y |  
| [link 方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LN2 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LN10 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [localeCompare 方法](/scripting/javascript/reference/localecompare-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [log 函数](/scripting/javascript/reference/math-log-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LOG2E 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LOG10E 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [逻辑 AND 运算符（&&）](/scripting/javascript/reference/logical-and-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [逻辑 NOT 运算符（！）](/scripting/javascript/reference/logical-not-operator-decrement-exclpt-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [逻辑 OR 运算符（&#124;&#124;）](/scripting/javascript/reference/logical-or-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [map 方法](/scripting/javascript/reference/map-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [地图对象](/scripting/javascript/reference/map-object-javascript) | N | N | N | N | Y | Y | v8： N <br /> v 8.1： Y |  
| [match 方法](/scripting/javascript/reference/match-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [数学对象](/scripting/javascript/reference/math-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [max 函数](/scripting/javascript/reference/math-max-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [MAX_VALUE 常量](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [message 属性](/scripting/javascript/reference/message-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [min 函数](/scripting/javascript/reference/math-min-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [MIN_VALUE 常量](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [余数赋值运算符（% =）](/scripting/javascript/reference/modulus-assignment-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [余数运算符（%）](/scripting/javascript/reference/modulus-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [moveFirst 方法](/scripting/javascript/reference/movefirst-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [moveNext 方法](/scripting/javascript/reference/movenext-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [多行属性](/scripting/javascript/reference/multiline-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [乘法赋值运算符（* =）](/scripting/javascript/reference/multiplication-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [乘法运算符（*）](/scripting/javascript/reference/multiplication-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [name 属性](/scripting/javascript/reference/name-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NaN 常量（全局）](/scripting/javascript/reference/nan-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NaN 常量（数字）](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NEGATIVE_INFINITY 常量](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [new 运算符](/scripting/javascript/reference/new-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Nonidentity 运算符（！ = =）](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [now 函数](/scripting/javascript/reference/date-now-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Number 对象](/scripting/javascript/reference/number-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [number 属性](https://developer.mozilla.org/docs/Web/JavaScript/Microsoft_Extensions/Error.number) | Y | Y | Y | Y | Y | Y | Y |  
| [对象对象](/scripting/javascript/reference/object-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [运算符优先级](/scripting/javascript/operator-subtractprecedence-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Date. parse 函数](/scripting/javascript/reference/date-parse-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON。 parse 函数](/scripting/javascript/reference/json-parse-function-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [parseFloat 函数](/scripting/javascript/reference/parsefloat-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [parseInt 函数](/scripting/javascript/reference/parseint-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [PI 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [pop 方法](/scripting/javascript/reference/pop-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [POSITIVE_INFINITY 常量](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [pow 函数](/scripting/javascript/reference/math-pow-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [preventExtensions 函数](/scripting/javascript/reference/object-preventextensions-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [承诺对象](/scripting/javascript/reference/promise-object-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [原型属性](/scripting/javascript/reference/prototype-property-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [propertyIsEnumerable 方法](/scripting/javascript/reference/propertyisenumerable-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [代理对象](/scripting/javascript/reference/proxy-object-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [push 方法](/scripting/javascript/reference/push-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [random 函数](/scripting/javascript/reference/math-random-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [raw 函数](/scripting/javascript/reference/string-raw-function-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [降低方法](/scripting/javascript/reference/reduce-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [reduceRight 方法](/scripting/javascript/reference/reduceright-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [RegExp 对象](/scripting/javascript/reference/regexp-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [正则表达式对象](/scripting/javascript/reference/regular-expression-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [正则表达式语法](https://msdn.microsoft.com/ab0766e1-7037-45ed-aa23-706f58358c0e) | Y | Y | Y | Y | Y | Y | Y |  
| [正则表达式/y 标志](/scripting/javascript/reference/regular-expression-object-javascript) | N | N | N | N | N | Exp. | v 8.1： N <br /> v10： Exp。 |  
| [重复方法（字符串）](/scripting/javascript/reference/repeat-method-string-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [replace 方法](/scripting/javascript/reference/replace-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [函数](/scripting/javascript/functions-javascript) | N | N | N | N | N | N | v 8.1： N <br /> v10： Y |  
| [return 语句](/scripting/javascript/reference/return-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [reverse 方法](/scripting/javascript/reference/reverse-method-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [rightContext 属性（$ '）](/scripting/javascript/reference/rightcontext-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [右移位赋值运算符（>>=）](/scripting/javascript/reference/right-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [round 函数](/scripting/javascript/reference/math-round-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngine 函数](/scripting/javascript/reference/scriptengine-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineBuildVersion 函数](/scripting/javascript/reference/scriptenginebuildversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineMajorVersion 函数](/scripting/javascript/reference/scriptenginemajorversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineMinorVersion 函数](/scripting/javascript/reference/scriptengineminorversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [密封函数](/scripting/javascript/reference/object-seal-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [搜索方法](/scripting/javascript/reference/search-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [设置对象](/scripting/javascript/reference/set-object-javascript) | N | N | N | N | Y | Y | v8： N <br /> v 8.1： Y |  
| [setDate 方法](/scripting/javascript/reference/setdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setFullYear 方法](/scripting/javascript/reference/setfullyear-method-date-javascript) |  | Y | Y | Y | Y | Y | Y |  
| [setHours 方法](/scripting/javascript/reference/sethours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMilliseconds 方法](/scripting/javascript/reference/setmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMinutes 方法](/scripting/javascript/reference/setminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMonth 方法](/scripting/javascript/reference/setmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setSeconds 方法](/scripting/javascript/reference/setseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setTime 方法](/scripting/javascript/reference/settime-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCDate 方法](/scripting/javascript/reference/setutcdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCFullYear 方法](/scripting/javascript/reference/setutcfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCHours 方法](/scripting/javascript/reference/setutchours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMilliseconds 方法](/scripting/javascript/reference/setutcmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMinutes 方法](/scripting/javascript/reference/setutcminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMonth 方法](/scripting/javascript/reference/setutcmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCSeconds 方法](/scripting/javascript/reference/setutcseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setYear 方法](/scripting/javascript/reference/setyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [shift 方法](/scripting/javascript/reference/shift-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [sin 函数](/scripting/javascript/reference/math-sin-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [切片方法（数组）](/scripting/javascript/reference/slice-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [切片方法（字符串）](/scripting/javascript/reference/slice-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [小型方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [某些方法](/scripting/javascript/reference/some-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [sort 方法](/scripting/javascript/reference/sort-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [source 属性](/scripting/javascript/reference/source-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [接合方法](/scripting/javascript/reference/splice-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [split 方法](/scripting/javascript/reference/split-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [函数](/scripting/javascript/functions-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [sqrt 函数](/scripting/javascript/reference/math-sqrt-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [SQRT1_2 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [SQRT2 常量](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [使用严格指令](/scripting/javascript/reference/use-strict-directive) | N | N | N | Y | Y | Y | Y |  
| [删除线方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [字符串对象](/scripting/javascript/reference/string-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON 函数 stringify 函数](/scripting/javascript/reference/json-stringify-function-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [子方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [substr 方法](/scripting/javascript/reference/substr-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [substring 方法](/scripting/javascript/reference/substring-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [减法赋值运算符（-=）](/scripting/javascript/reference/subtraction-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [减法运算符（-）](/scripting/javascript/reference/subtraction-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [sup 方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [switch 语句](/scripting/javascript/reference/switch-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Symbol 对象](/scripting/javascript/reference/symbol-object-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [tan 函数](/scripting/javascript/reference/math-tan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [模板字符串](/scripting/javascript/advanced/template-strings-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [测试方法](/scripting/javascript/reference/test-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [此语句](/scripting/javascript/reference/this-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [throw 语句](/scripting/javascript/reference/throw-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toArray 方法](/scripting/javascript/reference/toarray-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toDateString 方法](/scripting/javascript/reference/todatestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toExponential 方法](/scripting/javascript/reference/toexponential-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toFixed 方法](/scripting/javascript/reference/tofixed-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toGMTString 方法](/scripting/javascript/reference/togmtstring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toISOString 方法](/scripting/javascript/reference/toisostring-method-date-javascript) | N | N | Y | Y | Y | Y | Y |  
| [toJSON 方法](/scripting/javascript/reference/tojson-method-date-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [toLocaleDateString 方法](/scripting/javascript/reference/tolocaledatestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleLowercase 方法](/scripting/javascript/reference/tolocalelowercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleString 方法](/scripting/javascript/reference/tolocalestring-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleTimeString 方法](/scripting/javascript/reference/tolocaletimestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleUppercase 方法](/scripting/javascript/reference/tolocaleuppercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLowerCase 方法](/scripting/javascript/reference/tolowercase-method-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toPrecision 方法](/scripting/javascript/reference/toprecision-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toString 方法](/scripting/javascript/reference/tostring-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toTimeString 方法](/scripting/javascript/reference/totimestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toUpperCase 方法](/scripting/javascript/reference/touppercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toUTCString 方法](/scripting/javascript/reference/toutcstring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [trim 方法](/scripting/javascript/reference/trim-method-string-javascript) | N | N | Y | Y | Y | Y | Y |  
| [try 语句](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [typeof 运算符](/scripting/javascript/reference/typeof-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ubound 方法](/scripting/javascript/reference/ubound-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Uint8Array 对象](/scripting/javascript/reference/uint8array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint16Array 对象](/scripting/javascript/reference/uint16array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint32Array 对象](/scripting/javascript/reference/uint32array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint8ClampedArray 对象](/scripting/javascript/reference/uint8clampedarray-object-javascript) | N | N | N | N | Y | Y | v8：否 <br /> v 8.1 （Win）：是 <br /> v 8.1 （电话）：否 <br /> v10： Y |  
| [一元求反运算符（-）](/scripting/javascript/reference/subtraction-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [未定义常量](/scripting/javascript/reference/undefined-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [unescape 函数](/scripting/javascript/reference/unescape-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Unicode 码位转义符](/scripting/javascript/advanced/special-characters-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [unshift 方法](/scripting/javascript/reference/unshift-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [无符号右移赋值运算符（>>>=）](/scripting/javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [无符号右移运算符（>>>）](/scripting/javascript/reference/unsigned-right-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [使用严格指令](/scripting/javascript/reference/use-strict-directive) | N | N | N | Y | Y | Y | Y |  
| [UTC 函数](/scripting/javascript/reference/date-utc-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [valueOf 方法](/scripting/javascript/reference/valueof-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [values 方法（Array）](/scripting/javascript/reference/values-method-array-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [var 语句](/scripting/javascript/reference/var-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [VBArray 对象](/scripting/javascript/reference/vbarray-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [void 运算符](/scripting/javascript/reference/void-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [WeakMap 对象](/scripting/javascript/reference/weakmap-object-javascript) | N | N | N | N | Y | Y | v8： N <br /> v 8.1： Y |  
| [WeakSet 对象](/scripting/javascript/reference/weakset-object-javascript) | N | N | N | N | N | Y | v 8.1： N <br /> v10： Y |  
| [while 语句](/scripting/javascript/reference/while-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [WinRTError 对象](/scripting/javascript/reference/winrterror-object-javascript) | N | N | N | Y | Y | Y | Y |  
| [with 语句](/scripting/javascript/reference/with-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [write 函数](/scripting/javascript/reference/debug-write-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [writeln 函数](/scripting/javascript/reference/debug-writeln-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
  
 \ * 支持 DOM 对象，但不支持用户定义的对象。  `enumerable` `configurable` 可以指定和属性，但不使用它们。  
