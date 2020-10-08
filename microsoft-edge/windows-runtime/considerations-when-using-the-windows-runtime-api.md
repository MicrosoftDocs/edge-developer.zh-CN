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
# <span data-ttu-id="56d13-102">使用 Windows 运行时 API 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="56d13-102">Considerations when using the Windows Runtime API</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="56d13-103">你可以在 JavaScript 中使用 Windows 运行时 API 的几乎每个元素。</span><span class="sxs-lookup"><span data-stu-id="56d13-103">You can use nearly every element of the Windows Runtime API in JavaScript.</span></span>  <span data-ttu-id="56d13-104">但是，你应该记住 Windows 运行时元素的 JavaScript 表示方面的一些方面。</span><span class="sxs-lookup"><span data-stu-id="56d13-104">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="56d13-105">有关在 c + +、c # 或 Visual Basic 中创建 Windows 运行时组件并在 JavaScript 中使用它们的信息，请参阅使用 [c + + 创建 Windows 运行时组件][WindowsUwpComponentsCreatingCpp] 和使用 [c # 和 Visual Basic 创建 Windows 运行时组件][WindowsUwpComponentsCreatingCsharpVb]。</span><span class="sxs-lookup"><span data-stu-id="56d13-105">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span></span>  

## <span data-ttu-id="56d13-106">Windows 运行时类型的 JavaScript 表示中的特殊情况</span><span class="sxs-lookup"><span data-stu-id="56d13-106">Special cases in the JavaScript Representation of Windows Runtime types</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-107">字符串</span><span class="sxs-lookup"><span data-stu-id="56d13-107">Strings</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-108">未初始化的字符串作为字符串 "undefined" 传递到 Windows 运行时方法，设置为的字符串将 `null` 作为字符串 "null" 传递。</span><span class="sxs-lookup"><span data-stu-id="56d13-108">An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span></span>  <span data-ttu-id="56d13-109">\ (当 a `null` 或 `undefined` value 被强制转换为字符串时，这是 true。 \n ) 将字符串传递到 Windows 运行时方法之前，应将其初始化为空字符串 \ ( "" \ ) 。</span><span class="sxs-lookup"><span data-stu-id="56d13-109">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-110">接口</span><span class="sxs-lookup"><span data-stu-id="56d13-110">Interfaces</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-111">不能在 JavaScript 中实现 Windows 运行时接口。</span><span class="sxs-lookup"><span data-stu-id="56d13-111">You cannot implement a Windows Runtime interface in JavaScript.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-112">数组</span><span class="sxs-lookup"><span data-stu-id="56d13-112">Arrays</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-113">Windows 运行时数组不能调整大小，因此在 JavaScript 中调整数组大小的方法在 Windows 运行时数组中不起作用。</span><span class="sxs-lookup"><span data-stu-id="56d13-113">Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span></span>  
      *   <span data-ttu-id="56d13-114">数组：如果将 JavaScript 数组值传递给 Windows 运行时方法，则会复制该数组。</span><span class="sxs-lookup"><span data-stu-id="56d13-114">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span></span>  <span data-ttu-id="56d13-115">Windows 运行时方法无法修改数组或其成员，并将其返回到你的 JavaScript 应用。</span><span class="sxs-lookup"><span data-stu-id="56d13-115">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span></span>  <span data-ttu-id="56d13-116">但是，你可以使用类型化数组 \ (例如 [Int32Array 对象][MDNInt32array]\ ) ，这些数组不会被复制。</span><span class="sxs-lookup"><span data-stu-id="56d13-116">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-117">结构</span><span class="sxs-lookup"><span data-stu-id="56d13-117">Structures</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-118">Windows 运行时结构是 JavaScript 中的对象。</span><span class="sxs-lookup"><span data-stu-id="56d13-118">Windows Runtime structures are objects in JavaScript.</span></span>  <span data-ttu-id="56d13-119">如果要将 Windows 运行时结构传递到 Windows 运行时方法，请不要使用关键字实例化结构 `new` 。</span><span class="sxs-lookup"><span data-stu-id="56d13-119">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span></span>  <span data-ttu-id="56d13-120">而是创建一个对象并添加相关成员及其值。</span><span class="sxs-lookup"><span data-stu-id="56d13-120">Instead, create an object and add the relevant members and their values.</span></span>  <span data-ttu-id="56d13-121">成员的名称应采用 camel 大小写形式： `SomeStruct.firstMember` 。</span><span class="sxs-lookup"><span data-stu-id="56d13-121">The names of the members should be in camel case: `SomeStruct.firstMember`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-122">对象</span><span class="sxs-lookup"><span data-stu-id="56d13-122">Objects</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-123">JavaScript 对象与托管代码对象 \ (`System.Object` \ ) 不同。</span><span class="sxs-lookup"><span data-stu-id="56d13-123">JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span></span>  <span data-ttu-id="56d13-124">无法将 JavaScript 对象传递到需要的 Windows 运行时方法 `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="56d13-124">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-125">对象标识</span><span class="sxs-lookup"><span data-stu-id="56d13-125">Object identity</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-126">在大多数情况下，在 Windows 运行时和 JavaScript 之间来回传递的对象不会发生变化。</span><span class="sxs-lookup"><span data-stu-id="56d13-126">In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span></span>  <span data-ttu-id="56d13-127">JavaScript 引擎维护已知对象的地图。</span><span class="sxs-lookup"><span data-stu-id="56d13-127">The JavaScript engine maintains a map of known objects.</span></span>  <span data-ttu-id="56d13-128">当从 Windows 运行时返回一个对象时，它将与地图相匹配，如果不存在，则创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="56d13-128">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span></span>  <span data-ttu-id="56d13-129">对于表示由 Windows 运行时方法返回的接口的对象，将遵循相同的过程。</span><span class="sxs-lookup"><span data-stu-id="56d13-129">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span></span>  <span data-ttu-id="56d13-130">有两种类型的异常：</span><span class="sxs-lookup"><span data-stu-id="56d13-130">There are two kinds of exceptions:</span></span>  
      
      *   <span data-ttu-id="56d13-131">从 Windows 运行时调用返回的对象，然后添加新的 \ (expando \ ) 属性，当它们传递回 Windows 运行时，不保留其新属性。</span><span class="sxs-lookup"><span data-stu-id="56d13-131">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span></span>  <span data-ttu-id="56d13-132">但是，当它们返回到 JavaScript 应用时，由于它们与现有对象匹配，因此返回的对象具有 expando 属性。</span><span class="sxs-lookup"><span data-stu-id="56d13-132">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span></span>  
      *   <span data-ttu-id="56d13-133">Windows 运行时中的结构和委托无法标识为与以前使用的结构或委托相同。</span><span class="sxs-lookup"><span data-stu-id="56d13-133">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span></span>  <span data-ttu-id="56d13-134">每次返回结构或委托时，它都会获取一个新引用。</span><span class="sxs-lookup"><span data-stu-id="56d13-134">Every time a structure or delegate is returned, it gets a new reference.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-135">名称冲突</span><span class="sxs-lookup"><span data-stu-id="56d13-135">Name collisions</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-136">多个 Windows 运行时接口可能具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="56d13-136">Multiple Windows Runtime interfaces may have members with the same names.</span></span>  <span data-ttu-id="56d13-137">如果它们合并到单个 JavaScript 对象 (该对象可以是运行时类或接口) 的表示形式，则成员使用完全限定的名称表示。</span><span class="sxs-lookup"><span data-stu-id="56d13-137">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span></span>  <span data-ttu-id="56d13-138">你可以使用以下语法调用这些成员：</span><span class="sxs-lookup"><span data-stu-id="56d13-138">You can call these members by using the following syntax:</span></span>  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      <span data-ttu-id="56d13-139">在以下代码中，两个接口具有 Draw 方法，并且运行时类实现了这两个接口。</span><span class="sxs-lookup"><span data-stu-id="56d13-139">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span></span>  
      
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
      
      <span data-ttu-id="56d13-140">下面介绍如何在 JavaScript 中调用上述代码。</span><span class="sxs-lookup"><span data-stu-id="56d13-140">Here is how you can call the above code in JavaScript.</span></span>  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` <span data-ttu-id="56d13-141">实参</span><span class="sxs-lookup"><span data-stu-id="56d13-141">parameters</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-142">如果 Windows 运行时方法具有多个 `out` 参数，在 JavaScript 中，该方法将 JavaScript 对象作为其返回值，并且该对象具有对应于该 `out` 参数的属性。</span><span class="sxs-lookup"><span data-stu-id="56d13-142">If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span></span>  <span data-ttu-id="56d13-143">例如，请考虑 c + + 中的以下 Windows 运行时签名。</span><span class="sxs-lookup"><span data-stu-id="56d13-143">For example, consider the following Windows Runtime signature in C++.</span></span>  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      <span data-ttu-id="56d13-144">此签名的 JavaScript 版本是：</span><span class="sxs-lookup"><span data-stu-id="56d13-144">The JavaScript version of this signature is:</span></span>  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      <span data-ttu-id="56d13-145">在此示例中， `returnValue` 是具有两个字段的 JavaScript 对象： `first` 和 `second` 。</span><span class="sxs-lookup"><span data-stu-id="56d13-145">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="56d13-146">静态成员</span><span class="sxs-lookup"><span data-stu-id="56d13-146">Static members</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="56d13-147">Windows 运行时同时定义静态成员和实例成员。</span><span class="sxs-lookup"><span data-stu-id="56d13-147">The Windows Runtime defines both static members and instance members.</span></span>  <span data-ttu-id="56d13-148">在 JavaScript 中，静态成员将添加到与 Windows 运行时类或接口关联的对象。</span><span class="sxs-lookup"><span data-stu-id="56d13-148">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span></span>  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
<span data-ttu-id="56d13-149">有关 Windows 运行时基本类型的 JavaScript 表示的详细信息，请参阅 [Windows 运行时类型的 Javascript 表示形式][WindowsRuntimeJavascriptTypes]。</span><span class="sxs-lookup"><span data-stu-id="56d13-149">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span></span>  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows 运行时类型的 JavaScript 表示形式 |Microsoft 文档"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "带有 c + +/CX 的 Windows 运行时组件 |Microsoft 文档"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "带有 c # 和 Visual Basic 的 Windows 运行时组件 |Microsoft 文档"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  