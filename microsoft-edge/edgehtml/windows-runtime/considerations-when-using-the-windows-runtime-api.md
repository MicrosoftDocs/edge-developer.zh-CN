---
description: 使用 Windows 运行时 API 时的注意事项
title: 使用 Windows 运行时 API 时的注意事项
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: 8
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 170374fd109802bff0aa0fc93cea6c8d50c9d7c7
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399342"
---
# <a name="considerations-when-using-the-windows-runtime-api"></a>使用 Windows 运行时 API 时的注意事项  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

在 JavaScript 中，几乎可以使用 Windows 运行时 API 的每一个元素。  但是，应记住 Windows 运行时元素的 JavaScript 表示形式的某些方面。  

> [!IMPORTANT]
> 有关使用 C++、C# 或 Visual Basic 创建 Windows 运行时组件和在 JavaScript 中使用它们的信息，请参阅使用 [C++][WindowsUwpComponentsCreatingCpp] 创建 Windows 运行时组件，以及使用 C# 和 Visual Basic 创建 [Windows][WindowsUwpComponentsCreatingCsharpVb]运行时组件。  

## <a name="special-cases-in-the-javascript-representation-of-windows-runtime-types"></a>Windows 运行时类型的 JavaScript 表示形式中的特殊情况  

:::row:::
   :::column span="1":::
      字符串  
   :::column-end:::
   :::column span="3":::
      未初始化的字符串作为字符串"undefined"传递给 Windows 运行时方法，设置为字符串 `null` "null"的字符串传递。  \ (只要将一个或一个值强制转换为字符串，就会发生此情况。\) 在将字符串传递到 Windows 运行时方法之前，应先初始化它作为空字符串 `null` `undefined` \ (""\) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      接口  
   :::column-end:::
   :::column span="3":::
      无法在 JavaScript 中实现 Windows 运行时接口。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      数组  
   :::column-end:::
   :::column span="3":::
      Windows 运行时数组不可调整大小，因此在 JavaScript 中调整数组大小的方法对 Windows 运行时数组不起作用。  
      *   数组：如果将 JavaScript 数组值传递给 Windows 运行时方法，则复制该数组。  Windows 运行时方法无法修改数组或其成员，无法将数组返回到 JavaScript 应用。  但是，可以使用键入的数组 \ (例如 [，Int32Array 对象][MDNInt32array]\) ，这些数组不会复制。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      结构  
   :::column-end:::
   :::column span="3":::
      Windows 运行时结构是 JavaScript 中的对象。  如果要将 Windows 运行时结构传递给 Windows 运行时方法，请不要使用关键字实例化 `new` 该结构。  相反，请创建一个对象并添加相关成员及其值。  成员的名称应为 camel 大小写： `SomeStruct.firstMember` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      对象  
   :::column-end:::
   :::column span="3":::
      JavaScript 对象与托管代码对象 \ (`System.Object` \) 。  不能将 JavaScript 对象传递给需要 a 的 Windows 运行时方法 `System.Object` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      对象标识  
   :::column-end:::
   :::column span="3":::
      在大多数情况下，在 Windows 运行时和 JavaScript 之间来回传递的对象不会更改。  JavaScript 引擎维护已知对象的映射。  当从 Windows 运行时返回对象时，它将与映射匹配，如果该对象不存在，则创建一个新对象。  对于表示由 Windows 运行时方法返回的接口的对象，将执行相同的过程。  有两种类型的例外：  
      
      *   从 Windows 运行时调用返回，然后添加了新的 \ (expando\) 属性的对象在传递回 Windows 运行时时不会保留其新属性。  但是，当它们返回到 JavaScript 应用时，由于它们与现有对象匹配，因此返回的对象确实具有 expando 属性。  
      *   无法将 Windows 运行时中的结构和委托标识为与以前使用的结构或委托相同。  每次返回结构或委托时，都会获得一个新引用。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      名称冲突  
   :::column-end:::
   :::column span="3":::
      多个 Windows 运行时接口可能具有相同的名称的成员。  如果它们组合在单个 JavaScript 对象 (它可以表示运行时类或接口) ，则成员用完全限定的名称表示。  可以使用以下语法调用这些成员：  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      在下面的代码中，两个接口具有一个 Draw 方法，一个运行时类实现这两个接口。  
      
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
      
      下面是在 JavaScript 中调用上述代码的方法。  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` 参数  
   :::column-end:::
   :::column span="3":::
      如果 Windows 运行时方法具有多个参数，则该方法在 JavaScript 中具有 JavaScript 对象作为其返回值，并且该对象具有与参数对应的 `out` `out` 属性。  例如，请考虑以下 C++ 中的 Windows 运行时签名。  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      此签名的 JavaScript 版本为：  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      本示例中， `returnValue` 是一个 JavaScript 对象，该对象具有两个字段： `first` 和 `second` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      静态成员  
   :::column-end:::
   :::column span="3":::
      Windows 运行时定义静态成员和实例成员。  在 JavaScript 中，静态成员将添加到与 Windows 运行时类或接口关联的对象。  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
有关 Windows 运行时基本类型的 JavaScript 表示形式详细信息，请参阅 Windows 运行时类型的 [JavaScript 表示形式][WindowsRuntimeJavascriptTypes]。  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows 运行时类型的 JavaScript 表示|Microsoft Docs"  

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "Windows 运行时组件与 C++/CX |Microsoft Docs"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "Windows 运行时组件C#Visual Basic |Microsoft Docs"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  
