---
title: 使用 Windows 运行时 API 时的注意事项
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: 6b460fe514927590382613b7454a69c89a5a5f8b
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942215"
---
# 使用 Windows 运行时 API 时的注意事项  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

几常以 JavaScript 方式使用 Windows 运行时 API 的每个元素。  但是，你应记住 Windows 运行时元素的 JavaScript 表示形式的某些方面。  

> [!IMPORTANT]
> 有关通过 C++、C# 或 Visual Basic 创建 Windows 运行时组件并使用 JavaScript 编写它们的信息，请参阅" [使用 C++][WindowsUwpComponentsCreatingCpp] 创建 Windows 运行时组件" [并使用 C#][WindowsUwpComponentsCreatingCsharpVb]和 Visual Basic 创建 Windows 运行时组件。  

## Windows 运行时类型的 JavaScript 表示形式的特殊情况  

:::row:::
   :::column span="1":::
      字符串  
   :::column-end:::
   :::column span="3":::
      未初始化的字符串作为字符串"undefined"传递到 Windows 运行时方法，并将一个字符串设置为 `null` 字符串"null"。  \ (只要将一个或 `null` `undefined` 值相对于 string.\) 在将字符串传递给 Windows 运行时方法之前，应该将其初始化为空字符串 \ ("\) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      接口  
   :::column-end:::
   :::column span="3":::
      你无法使用 JavaScript 实现 Windows 运行时接口。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      数组  
   :::column-end:::
   :::column span="3":::
      Windows 运行时数组不可调整大小，因此在 JavaScript 中重设数组大小的方法对 Windows 运行时数组无效。  
      *   数组：如果你将一个 JavaScript 数组值传递给 Windows 运行时方法，则复制该数组。  Windows 运行时方法无法修改数组或其成员并将其返回 JavaScript 应用。  但是，你可以使用类型化数组 \ (例如 [，Int32Array 对象][MDNInt32array]\) ，而不复制。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      结构  
   :::column-end:::
   :::column span="3":::
      Windows 运行时结构为 JavaScript 中的对象。  如果你希望将一个 Windows 运行时结构传递给 Windows 运行时方法，请不要使用关键字实例 `new` 化结构。  请改为创建一个对象并添加相关成员及其值。  成员的名称应当为 camel 用 `SomeStruct.firstMember` 例：  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      对象  
   :::column-end:::
   :::column span="3":::
      JavaScript 对象与托管代码对象 \ (`System.Object` \) 不同。  你无法将 JavaScript 对象传递给需要的 Windows 运行时方法 `System.Object` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      对象标识  
   :::column-end:::
   :::column span="3":::
      在大多数情况下，在 Windows 运行时和 JavaScript 之间来回传递的对象不会改变。  JavaScript 引文维护已知对象的地图。  从 Windows 运行时返回某个对象时，该对象与地图匹配，如果其不存在一个新对象。  对于表示由 Windows 运行时方法返回的接口的对象，将遵循相同的过程。  有两种类型的异常：  
      
      *   从 Windows 运行时调用返回的对象，然后添加了新的 \ (expando\) 属性时，当这些对象传递回 Windows 运行时时不会保留这些新属性。  但是，当这些控件返回给 JavaScript 应用时，由于它们与现有对象匹配，所以返回的对象将具有扩展属性。  
      *   Windows 运行时中的结构和委代被标识为与以前使用的结构或代理相同。  每次返回结构或代理人时，它都会获得一个新的引用。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      名称合作  
   :::column-end:::
   :::column span="3":::
      多个 Windows 运行时接口可能拥有具有相同名称的成员。  如果它们组合在一个 JavaScript 对象 (中可以表示运行时类或接口) 则成员将以完全限定的名称表示。  您可以使用以下语法调用这些成员：  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      在以下代码中，两个接口都有一个 Draw 方法，而且运行时类实现这两个接口。  
      
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
      
      下面介绍了如何使用 JavaScript 调用上述代码。  
      
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
      如果 Windows 运行时方法有多个 `out` 参数，则在 JavaScript 中，该方法将 JavaScript 对象作为它的返回值，该对象具有与该参数对应 `out` 的属性。  例如，请考虑以下使用 C++ 的 Windows 运行时签名。  
      
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
      
      在此示例中 `returnValue` ，有两个字段且有一个 JavaScript `first` 对象 `second` ：  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      静态成员  
   :::column-end:::
   :::column span="3":::
      Windows 运行时定义静态成员和实例成员。  在 JavaScript 中，静态成员将被添加到与 Windows 运行时类或接口关联的对象中。  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
有关 Windows 运行时基本类型的 JavaScript 表示的详细信息，请参阅 [Windows 运行时类型的 JavaScript 表示形式][WindowsRuntimeJavascriptTypes]。  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows 运行时类型的 JavaScript 表示 |Microsoft 文档"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "使用 C++/CX | 的 Windows 运行时组件Microsoft 文档"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "使用 C# 和应用 | 的 Windows 运行时组Visual Basic |Microsoft 文档"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  