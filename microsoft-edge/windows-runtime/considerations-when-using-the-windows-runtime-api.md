---
title: 使用 Windows 运行时 API 时的注意事项
ms.custom: ''
ms.date: 04/01/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: 8
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 95b082e27c4f247b841a9540e13bd49bd4c8bd67
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564593"
---
# 使用 Windows 运行时 API 时的注意事项  

你可以在 JavaScript 中使用 Windows 运行时 API 的几乎每个元素。  但是，你应该记住 Windows 运行时元素的 JavaScript 表示方面的一些方面。  

> [!IMPORTANT]
> 有关在 c + +、c # 或 Visual Basic 中创建 Windows 运行时组件并在 JavaScript 中使用它们的信息，请参阅使用[c + + 创建 Windows 运行时组件][WindowsUwpComponentsCreatingCpp]和使用[c # 和 Visual Basic 创建 Windows 运行时组件][WindowsUwpComponentsCreatingCsharpVb]。  

## Windows 运行时类型的 JavaScript 表示中的特殊情况  

*   字符串：将未初始化的字符串作为字符串 "undefined" 传递到 Windows 运行时方法，并且将字符串设置为 `null` 作为字符串 "null" 传递。  \ （在将 `null` `undefined` 字符串传递到 Windows 运行时方法之前，此值为 true，应将字符串初始化为空字符串 \ （"" \）。  
*   接口：不能在 JavaScript 中实现 Windows 运行时接口。  
*   数组： Windows 运行时数组不能调整大小，因此在 JavaScript 中调整数组大小的方法在 Windows 运行时数组上不起作用。  
*   数组：如果将 JavaScript 数组值传递给 Windows 运行时方法，则会复制该数组。  Windows 运行时方法无法修改数组或其成员，并将其返回到你的 JavaScript 应用。  但是，你可以使用类型化数组 \ （例如， [Int32Array Object][MDNInt32array]\），这些数组不会被复制。  
*   结构： Windows 运行时结构是 JavaScript 中的对象。  如果要将 Windows 运行时结构传递到 Windows 运行时方法，请不要使用关键字实例化结构 `new` 。  而是创建一个对象并添加相关成员及其值。  成员的名称应采用 camel 大小写形式： `SomeStruct.firstMember` 。  
*   对象： JavaScript 对象与托管代码对象（ `System.Object` \）不同。  无法将 JavaScript 对象传递到需要的 Windows 运行时方法 `System.Object` 。  
*   对象标识：在大多数情况下，在 Windows 运行时和 JavaScript 之间来回传递的对象不会发生变化。  JavaScript 引擎维护已知对象的地图。  当从 Windows 运行时返回一个对象时，它将与地图相匹配，如果不存在，则创建一个新对象。  对于表示由 Windows 运行时方法返回的接口的对象，将遵循相同的过程。  有两种类型的异常：  

    *   从 Windows 运行时调用返回的对象，然后添加新的 \ （expando \）属性，当它们传递回 Windows 运行时，不保留其新属性。  但是，当它们返回到 JavaScript 应用时，由于它们与现有对象匹配，因此返回的对象具有 expando 属性。  
    *   Windows 运行时中的结构和委托无法标识为与以前使用的结构或委托相同。  每次返回结构或委托时，它都会获取一个新引用。  

*   名称冲突：多个 Windows 运行时接口可能具有相同名称的成员。  如果它们合并在单个 JavaScript 对象（可以是运行时类或接口的表示形式）中，则成员使用完全限定的名称表示。  你可以使用以下语法调用这些成员：  
    
    ```cpp
    Class["MemberName"](parameter)
    ```  
    
    在以下代码中，两个接口具有 Draw 方法，并且运行时类实现了这两个接口。  
    
    ```cpp
    namespace CollisionExample {
        interface InterfaceA
        {
            HRESULT Draw([in] Int32 a);
        }
        interface InterfaceB
        {
            HRESULT Draw([in] HString a);
        }
        runtimeclass ExampleObject {
          interface InterfaceA
          interface InterfaceB
        }
    }
    ```  
    
    下面介绍如何在 JavaScript 中调用上述代码。  
    
    ```javascript
    var example = new ExampleObject();
    example["CollisionExample.InterfaceA.draw"](12);
    example["CollisionExample.InterfaceB.draw"]("hello");
    ```  
    
*   `Out` 参数：如果 Windows 运行时方法具有多个 `out` 参数，在 JavaScript 中，该方法将 JavaScript 对象作为其返回值，并且该对象具有对应于该 `out` 参数的属性。  例如，请考虑 c + + 中的以下 Windows 运行时签名。  
    
    ```cpp
    void ExampleMethod(
      [OutAttribute] char^ first,
      [OutAttribute] char^ second
    )
    ```  
    
    此签名的 JavaScript 版本是：  
    
    ```javascript
    var returnValue = exampleMethod();
    ```  
    
    在此示例中， `returnValue` 是具有两个字段的 JavaScript 对象： `first` 和 `second` 。  
    
*   静态成员： Windows 运行时同时定义静态成员和实例成员。  在 JavaScript 中，静态成员将添加到与 Windows 运行时类或接口关联的对象。  
    
    ```javascript
    // Static method.
    var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
    // Instance method.
    var reading = accel.getCurrentReading();
    ```  
    
有关 Windows 运行时基本类型的 JavaScript 表示的详细信息，请参阅[Windows 运行时类型的 Javascript 表示形式][WindowsRuntimeJavascriptTypes]。  

<!-- image links -->  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: /microsoft-edge/windows-runtime/javascript-representation-of-windows-runtime-types "Windows 运行时类型的 JavaScript 表示形式"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "带有 c + +/CX 的 Windows 运行时组件"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "带有 c # 和 Visual Basic 的 Windows 运行时组件"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  