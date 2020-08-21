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
# <span data-ttu-id="db272-102">使用 Windows 运行时 API 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="db272-102">Considerations when using the Windows Runtime API</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="db272-103">几常以 JavaScript 方式使用 Windows 运行时 API 的每个元素。</span><span class="sxs-lookup"><span data-stu-id="db272-103">You can use nearly every element of the Windows Runtime API in JavaScript.</span></span>  <span data-ttu-id="db272-104">但是，你应记住 Windows 运行时元素的 JavaScript 表示形式的某些方面。</span><span class="sxs-lookup"><span data-stu-id="db272-104">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="db272-105">有关通过 C++、C# 或 Visual Basic 创建 Windows 运行时组件并使用 JavaScript 编写它们的信息，请参阅" [使用 C++][WindowsUwpComponentsCreatingCpp] 创建 Windows 运行时组件" [并使用 C#][WindowsUwpComponentsCreatingCsharpVb]和 Visual Basic 创建 Windows 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="db272-105">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span></span>  

## <span data-ttu-id="db272-106">Windows 运行时类型的 JavaScript 表示形式的特殊情况</span><span class="sxs-lookup"><span data-stu-id="db272-106">Special cases in the JavaScript Representation of Windows Runtime types</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-107">字符串</span><span class="sxs-lookup"><span data-stu-id="db272-107">Strings</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-108">未初始化的字符串作为字符串"undefined"传递到 Windows 运行时方法，并将一个字符串设置为 `null` 字符串"null"。</span><span class="sxs-lookup"><span data-stu-id="db272-108">An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span></span>  <span data-ttu-id="db272-109">\ (只要将一个或 `null` `undefined` 值相对于 string.\) 在将字符串传递给 Windows 运行时方法之前，应该将其初始化为空字符串 \ ("\) 。</span><span class="sxs-lookup"><span data-stu-id="db272-109">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-110">接口</span><span class="sxs-lookup"><span data-stu-id="db272-110">Interfaces</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-111">你无法使用 JavaScript 实现 Windows 运行时接口。</span><span class="sxs-lookup"><span data-stu-id="db272-111">You cannot implement a Windows Runtime interface in JavaScript.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-112">数组</span><span class="sxs-lookup"><span data-stu-id="db272-112">Arrays</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-113">Windows 运行时数组不可调整大小，因此在 JavaScript 中重设数组大小的方法对 Windows 运行时数组无效。</span><span class="sxs-lookup"><span data-stu-id="db272-113">Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span></span>  
      *   <span data-ttu-id="db272-114">数组：如果你将一个 JavaScript 数组值传递给 Windows 运行时方法，则复制该数组。</span><span class="sxs-lookup"><span data-stu-id="db272-114">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span></span>  <span data-ttu-id="db272-115">Windows 运行时方法无法修改数组或其成员并将其返回 JavaScript 应用。</span><span class="sxs-lookup"><span data-stu-id="db272-115">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span></span>  <span data-ttu-id="db272-116">但是，你可以使用类型化数组 \ (例如 [，Int32Array 对象][MDNInt32array]\) ，而不复制。</span><span class="sxs-lookup"><span data-stu-id="db272-116">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-117">结构</span><span class="sxs-lookup"><span data-stu-id="db272-117">Structures</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-118">Windows 运行时结构为 JavaScript 中的对象。</span><span class="sxs-lookup"><span data-stu-id="db272-118">Windows Runtime structures are objects in JavaScript.</span></span>  <span data-ttu-id="db272-119">如果你希望将一个 Windows 运行时结构传递给 Windows 运行时方法，请不要使用关键字实例 `new` 化结构。</span><span class="sxs-lookup"><span data-stu-id="db272-119">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span></span>  <span data-ttu-id="db272-120">请改为创建一个对象并添加相关成员及其值。</span><span class="sxs-lookup"><span data-stu-id="db272-120">Instead, create an object and add the relevant members and their values.</span></span>  <span data-ttu-id="db272-121">成员的名称应当为 camel 用 `SomeStruct.firstMember` 例：</span><span class="sxs-lookup"><span data-stu-id="db272-121">The names of the members should be in camel case: `SomeStruct.firstMember`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-122">对象</span><span class="sxs-lookup"><span data-stu-id="db272-122">Objects</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-123">JavaScript 对象与托管代码对象 \ (`System.Object` \) 不同。</span><span class="sxs-lookup"><span data-stu-id="db272-123">JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span></span>  <span data-ttu-id="db272-124">你无法将 JavaScript 对象传递给需要的 Windows 运行时方法 `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="db272-124">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-125">对象标识</span><span class="sxs-lookup"><span data-stu-id="db272-125">Object identity</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-126">在大多数情况下，在 Windows 运行时和 JavaScript 之间来回传递的对象不会改变。</span><span class="sxs-lookup"><span data-stu-id="db272-126">In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span></span>  <span data-ttu-id="db272-127">JavaScript 引文维护已知对象的地图。</span><span class="sxs-lookup"><span data-stu-id="db272-127">The JavaScript engine maintains a map of known objects.</span></span>  <span data-ttu-id="db272-128">从 Windows 运行时返回某个对象时，该对象与地图匹配，如果其不存在一个新对象。</span><span class="sxs-lookup"><span data-stu-id="db272-128">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span></span>  <span data-ttu-id="db272-129">对于表示由 Windows 运行时方法返回的接口的对象，将遵循相同的过程。</span><span class="sxs-lookup"><span data-stu-id="db272-129">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span></span>  <span data-ttu-id="db272-130">有两种类型的异常：</span><span class="sxs-lookup"><span data-stu-id="db272-130">There are two kinds of exceptions:</span></span>  
      
      *   <span data-ttu-id="db272-131">从 Windows 运行时调用返回的对象，然后添加了新的 \ (expando\) 属性时，当这些对象传递回 Windows 运行时时不会保留这些新属性。</span><span class="sxs-lookup"><span data-stu-id="db272-131">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span></span>  <span data-ttu-id="db272-132">但是，当这些控件返回给 JavaScript 应用时，由于它们与现有对象匹配，所以返回的对象将具有扩展属性。</span><span class="sxs-lookup"><span data-stu-id="db272-132">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span></span>  
      *   <span data-ttu-id="db272-133">Windows 运行时中的结构和委代被标识为与以前使用的结构或代理相同。</span><span class="sxs-lookup"><span data-stu-id="db272-133">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span></span>  <span data-ttu-id="db272-134">每次返回结构或代理人时，它都会获得一个新的引用。</span><span class="sxs-lookup"><span data-stu-id="db272-134">Every time a structure or delegate is returned, it gets a new reference.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-135">名称合作</span><span class="sxs-lookup"><span data-stu-id="db272-135">Name collisions</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-136">多个 Windows 运行时接口可能拥有具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="db272-136">Multiple Windows Runtime interfaces may have members with the same names.</span></span>  <span data-ttu-id="db272-137">如果它们组合在一个 JavaScript 对象 (中可以表示运行时类或接口) 则成员将以完全限定的名称表示。</span><span class="sxs-lookup"><span data-stu-id="db272-137">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span></span>  <span data-ttu-id="db272-138">您可以使用以下语法调用这些成员：</span><span class="sxs-lookup"><span data-stu-id="db272-138">You can call these members by using the following syntax:</span></span>  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      <span data-ttu-id="db272-139">在以下代码中，两个接口都有一个 Draw 方法，而且运行时类实现这两个接口。</span><span class="sxs-lookup"><span data-stu-id="db272-139">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span></span>  
      
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
      
      <span data-ttu-id="db272-140">下面介绍了如何使用 JavaScript 调用上述代码。</span><span class="sxs-lookup"><span data-stu-id="db272-140">Here is how you can call the above code in JavaScript.</span></span>  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` <span data-ttu-id="db272-141">参数</span><span class="sxs-lookup"><span data-stu-id="db272-141">parameters</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-142">如果 Windows 运行时方法有多个 `out` 参数，则在 JavaScript 中，该方法将 JavaScript 对象作为它的返回值，该对象具有与该参数对应 `out` 的属性。</span><span class="sxs-lookup"><span data-stu-id="db272-142">If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span></span>  <span data-ttu-id="db272-143">例如，请考虑以下使用 C++ 的 Windows 运行时签名。</span><span class="sxs-lookup"><span data-stu-id="db272-143">For example, consider the following Windows Runtime signature in C++.</span></span>  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      <span data-ttu-id="db272-144">此签名的 JavaScript 版本为：</span><span class="sxs-lookup"><span data-stu-id="db272-144">The JavaScript version of this signature is:</span></span>  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      <span data-ttu-id="db272-145">在此示例中 `returnValue` ，有两个字段且有一个 JavaScript `first` 对象 `second` ：</span><span class="sxs-lookup"><span data-stu-id="db272-145">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db272-146">静态成员</span><span class="sxs-lookup"><span data-stu-id="db272-146">Static members</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="db272-147">Windows 运行时定义静态成员和实例成员。</span><span class="sxs-lookup"><span data-stu-id="db272-147">The Windows Runtime defines both static members and instance members.</span></span>  <span data-ttu-id="db272-148">在 JavaScript 中，静态成员将被添加到与 Windows 运行时类或接口关联的对象中。</span><span class="sxs-lookup"><span data-stu-id="db272-148">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span></span>  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
<span data-ttu-id="db272-149">有关 Windows 运行时基本类型的 JavaScript 表示的详细信息，请参阅 [Windows 运行时类型的 JavaScript 表示形式][WindowsRuntimeJavascriptTypes]。</span><span class="sxs-lookup"><span data-stu-id="db272-149">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span></span>  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows 运行时类型的 JavaScript 表示 |Microsoft 文档"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "使用 C++/CX | 的 Windows 运行时组件Microsoft 文档"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "使用 C# 和应用 | 的 Windows 运行时组Visual Basic |Microsoft 文档"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  