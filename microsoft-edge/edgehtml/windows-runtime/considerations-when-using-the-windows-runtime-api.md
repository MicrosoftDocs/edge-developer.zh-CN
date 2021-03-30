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
# <a name="considerations-when-using-the-windows-runtime-api"></a><span data-ttu-id="283f6-103">使用 Windows 运行时 API 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="283f6-103">Considerations when using the Windows Runtime API</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="283f6-104">在 JavaScript 中，几乎可以使用 Windows 运行时 API 的每一个元素。</span><span class="sxs-lookup"><span data-stu-id="283f6-104">You can use nearly every element of the Windows Runtime API in JavaScript.</span></span>  <span data-ttu-id="283f6-105">但是，应记住 Windows 运行时元素的 JavaScript 表示形式的某些方面。</span><span class="sxs-lookup"><span data-stu-id="283f6-105">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="283f6-106">有关使用 C++、C# 或 Visual Basic 创建 Windows 运行时组件和在 JavaScript 中使用它们的信息，请参阅使用 [C++][WindowsUwpComponentsCreatingCpp] 创建 Windows 运行时组件，以及使用 C# 和 Visual Basic 创建 [Windows][WindowsUwpComponentsCreatingCsharpVb]运行时组件。</span><span class="sxs-lookup"><span data-stu-id="283f6-106">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span></span>  

## <a name="special-cases-in-the-javascript-representation-of-windows-runtime-types"></a><span data-ttu-id="283f6-107">Windows 运行时类型的 JavaScript 表示形式中的特殊情况</span><span class="sxs-lookup"><span data-stu-id="283f6-107">Special cases in the JavaScript Representation of Windows Runtime types</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-108">字符串</span><span class="sxs-lookup"><span data-stu-id="283f6-108">Strings</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-109">未初始化的字符串作为字符串"undefined"传递给 Windows 运行时方法，设置为字符串 `null` "null"的字符串传递。</span><span class="sxs-lookup"><span data-stu-id="283f6-109">An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span></span>  <span data-ttu-id="283f6-110">\(只要将一个或一个值强制转换为字符串，就会发生此情况。\) 在将字符串传递到 Windows 运行时方法之前，应先初始化它作为空字符串 `null` `undefined` \(""\) 。</span><span class="sxs-lookup"><span data-stu-id="283f6-110">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-111">接口</span><span class="sxs-lookup"><span data-stu-id="283f6-111">Interfaces</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-112">无法在 JavaScript 中实现 Windows 运行时接口。</span><span class="sxs-lookup"><span data-stu-id="283f6-112">You cannot implement a Windows Runtime interface in JavaScript.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-113">数组</span><span class="sxs-lookup"><span data-stu-id="283f6-113">Arrays</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-114">Windows 运行时数组不可调整大小，因此在 JavaScript 中调整数组大小的方法对 Windows 运行时数组不起作用。</span><span class="sxs-lookup"><span data-stu-id="283f6-114">Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span></span>  
      *   <span data-ttu-id="283f6-115">数组：如果将 JavaScript 数组值传递给 Windows 运行时方法，则复制该数组。</span><span class="sxs-lookup"><span data-stu-id="283f6-115">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span></span>  <span data-ttu-id="283f6-116">Windows 运行时方法无法修改数组或其成员，无法将数组返回到 JavaScript 应用。</span><span class="sxs-lookup"><span data-stu-id="283f6-116">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span></span>  <span data-ttu-id="283f6-117">但是，可以使用键入的数组 \(例如 [，Int32Array 对象][MDNInt32array]\) ，这些数组不会复制。</span><span class="sxs-lookup"><span data-stu-id="283f6-117">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-118">结构</span><span class="sxs-lookup"><span data-stu-id="283f6-118">Structures</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-119">Windows 运行时结构是 JavaScript 中的对象。</span><span class="sxs-lookup"><span data-stu-id="283f6-119">Windows Runtime structures are objects in JavaScript.</span></span>  <span data-ttu-id="283f6-120">如果要将 Windows 运行时结构传递给 Windows 运行时方法，请不要使用关键字实例化 `new` 该结构。</span><span class="sxs-lookup"><span data-stu-id="283f6-120">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span></span>  <span data-ttu-id="283f6-121">相反，请创建一个对象并添加相关成员及其值。</span><span class="sxs-lookup"><span data-stu-id="283f6-121">Instead, create an object and add the relevant members and their values.</span></span>  <span data-ttu-id="283f6-122">成员的名称应为 camel 大小写： `SomeStruct.firstMember` 。</span><span class="sxs-lookup"><span data-stu-id="283f6-122">The names of the members should be in camel case: `SomeStruct.firstMember`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-123">对象</span><span class="sxs-lookup"><span data-stu-id="283f6-123">Objects</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-124">JavaScript 对象与托管代码对象 \(`System.Object` \) 。</span><span class="sxs-lookup"><span data-stu-id="283f6-124">JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span></span>  <span data-ttu-id="283f6-125">不能将 JavaScript 对象传递给需要 a 的 Windows 运行时方法 `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="283f6-125">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-126">对象标识</span><span class="sxs-lookup"><span data-stu-id="283f6-126">Object identity</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-127">在大多数情况下，在 Windows 运行时和 JavaScript 之间来回传递的对象不会更改。</span><span class="sxs-lookup"><span data-stu-id="283f6-127">In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span></span>  <span data-ttu-id="283f6-128">JavaScript 引擎维护已知对象的映射。</span><span class="sxs-lookup"><span data-stu-id="283f6-128">The JavaScript engine maintains a map of known objects.</span></span>  <span data-ttu-id="283f6-129">当从 Windows 运行时返回对象时，它将与映射匹配，如果该对象不存在，则创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="283f6-129">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span></span>  <span data-ttu-id="283f6-130">对于表示由 Windows 运行时方法返回的接口的对象，将执行相同的过程。</span><span class="sxs-lookup"><span data-stu-id="283f6-130">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span></span>  <span data-ttu-id="283f6-131">有两种类型的例外：</span><span class="sxs-lookup"><span data-stu-id="283f6-131">There are two kinds of exceptions:</span></span>  
      
      *   <span data-ttu-id="283f6-132">从 Windows 运行时调用返回，然后添加了新的 \(expando\) 属性的对象在传递回 Windows 运行时时不会保留其新属性。</span><span class="sxs-lookup"><span data-stu-id="283f6-132">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span></span>  <span data-ttu-id="283f6-133">但是，当它们返回到 JavaScript 应用时，由于它们与现有对象匹配，因此返回的对象确实具有 expando 属性。</span><span class="sxs-lookup"><span data-stu-id="283f6-133">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span></span>  
      *   <span data-ttu-id="283f6-134">无法将 Windows 运行时中的结构和委托标识为与以前使用的结构或委托相同。</span><span class="sxs-lookup"><span data-stu-id="283f6-134">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span></span>  <span data-ttu-id="283f6-135">每次返回结构或委托时，都会获得一个新引用。</span><span class="sxs-lookup"><span data-stu-id="283f6-135">Every time a structure or delegate is returned, it gets a new reference.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-136">名称冲突</span><span class="sxs-lookup"><span data-stu-id="283f6-136">Name collisions</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-137">多个 Windows 运行时接口可能具有相同的名称的成员。</span><span class="sxs-lookup"><span data-stu-id="283f6-137">Multiple Windows Runtime interfaces may have members with the same names.</span></span>  <span data-ttu-id="283f6-138">如果它们组合在单个 JavaScript 对象 (它可以表示运行时类或接口) ，则成员用完全限定的名称表示。</span><span class="sxs-lookup"><span data-stu-id="283f6-138">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span></span>  <span data-ttu-id="283f6-139">可以使用以下语法调用这些成员：</span><span class="sxs-lookup"><span data-stu-id="283f6-139">You can call these members by using the following syntax:</span></span>  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      <span data-ttu-id="283f6-140">在下面的代码中，两个接口具有一个 Draw 方法，一个运行时类实现这两个接口。</span><span class="sxs-lookup"><span data-stu-id="283f6-140">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span></span>  
      
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
      
      <span data-ttu-id="283f6-141">下面是在 JavaScript 中调用上述代码的方法。</span><span class="sxs-lookup"><span data-stu-id="283f6-141">Here is how you can call the above code in JavaScript.</span></span>  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` <span data-ttu-id="283f6-142">参数</span><span class="sxs-lookup"><span data-stu-id="283f6-142">parameters</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-143">如果 Windows 运行时方法具有多个参数，则该方法在 JavaScript 中具有 JavaScript 对象作为其返回值，并且该对象具有与参数对应的 `out` `out` 属性。</span><span class="sxs-lookup"><span data-stu-id="283f6-143">If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span></span>  <span data-ttu-id="283f6-144">例如，请考虑以下 C++ 中的 Windows 运行时签名。</span><span class="sxs-lookup"><span data-stu-id="283f6-144">For example, consider the following Windows Runtime signature in C++.</span></span>  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      <span data-ttu-id="283f6-145">此签名的 JavaScript 版本为：</span><span class="sxs-lookup"><span data-stu-id="283f6-145">The JavaScript version of this signature is:</span></span>  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      <span data-ttu-id="283f6-146">本示例中， `returnValue` 是一个 JavaScript 对象，该对象具有两个字段： `first` 和 `second` 。</span><span class="sxs-lookup"><span data-stu-id="283f6-146">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="283f6-147">静态成员</span><span class="sxs-lookup"><span data-stu-id="283f6-147">Static members</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="283f6-148">Windows 运行时定义静态成员和实例成员。</span><span class="sxs-lookup"><span data-stu-id="283f6-148">The Windows Runtime defines both static members and instance members.</span></span>  <span data-ttu-id="283f6-149">在 JavaScript 中，静态成员将添加到与 Windows 运行时类或接口关联的对象。</span><span class="sxs-lookup"><span data-stu-id="283f6-149">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span></span>  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
<span data-ttu-id="283f6-150">有关 Windows 运行时基本类型的 JavaScript 表示形式详细信息，请参阅 Windows 运行时类型的 [JavaScript 表示形式][WindowsRuntimeJavascriptTypes]。</span><span class="sxs-lookup"><span data-stu-id="283f6-150">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span></span>  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows 运行时类型的 JavaScript 表示|Microsoft Docs"  

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "Windows 运行时组件与 C++/CX |Microsoft Docs"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "Windows 运行时组件C#Visual Basic |Microsoft Docs"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  
