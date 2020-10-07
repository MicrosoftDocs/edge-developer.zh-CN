---
title: Considerations when Using the Windows Runtime API
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
# <span data-ttu-id="8320c-102">Considerations when using the Windows Runtime API</span><span class="sxs-lookup"><span data-stu-id="8320c-102">Considerations when using the Windows Runtime API</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="8320c-103">You can use nearly every element of the Windows Runtime API in JavaScript.</span><span class="sxs-lookup"><span data-stu-id="8320c-103">You can use nearly every element of the Windows Runtime API in JavaScript.</span></span>  <span data-ttu-id="8320c-104">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span><span class="sxs-lookup"><span data-stu-id="8320c-104">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="8320c-105">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span><span class="sxs-lookup"><span data-stu-id="8320c-105">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span></span>  

## <span data-ttu-id="8320c-106">Special cases in the JavaScript Representation of Windows Runtime types</span><span class="sxs-lookup"><span data-stu-id="8320c-106">Special cases in the JavaScript Representation of Windows Runtime types</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-107">Strings</span><span class="sxs-lookup"><span data-stu-id="8320c-107">Strings</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-108">An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span><span class="sxs-lookup"><span data-stu-id="8320c-108">An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span></span>  <span data-ttu-id="8320c-109">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span><span class="sxs-lookup"><span data-stu-id="8320c-109">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-110">Interfaces</span><span class="sxs-lookup"><span data-stu-id="8320c-110">Interfaces</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-111">You cannot implement a Windows Runtime interface in JavaScript.</span><span class="sxs-lookup"><span data-stu-id="8320c-111">You cannot implement a Windows Runtime interface in JavaScript.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="8320c-112">Arrays</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-113">Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span><span class="sxs-lookup"><span data-stu-id="8320c-113">Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span></span>  
      *   <span data-ttu-id="8320c-114">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span><span class="sxs-lookup"><span data-stu-id="8320c-114">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span></span>  <span data-ttu-id="8320c-115">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span><span class="sxs-lookup"><span data-stu-id="8320c-115">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span></span>  <span data-ttu-id="8320c-116">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span><span class="sxs-lookup"><span data-stu-id="8320c-116">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-117">Structures</span><span class="sxs-lookup"><span data-stu-id="8320c-117">Structures</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-118">Windows Runtime structures are objects in JavaScript.</span><span class="sxs-lookup"><span data-stu-id="8320c-118">Windows Runtime structures are objects in JavaScript.</span></span>  <span data-ttu-id="8320c-119">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span><span class="sxs-lookup"><span data-stu-id="8320c-119">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span></span>  <span data-ttu-id="8320c-120">Instead, create an object and add the relevant members and their values.</span><span class="sxs-lookup"><span data-stu-id="8320c-120">Instead, create an object and add the relevant members and their values.</span></span>  <span data-ttu-id="8320c-121">The names of the members should be in camel case: `SomeStruct.firstMember`.</span><span class="sxs-lookup"><span data-stu-id="8320c-121">The names of the members should be in camel case: `SomeStruct.firstMember`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-122">Objects</span><span class="sxs-lookup"><span data-stu-id="8320c-122">Objects</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-123">JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span><span class="sxs-lookup"><span data-stu-id="8320c-123">JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span></span>  <span data-ttu-id="8320c-124">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="8320c-124">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-125">Object identity</span><span class="sxs-lookup"><span data-stu-id="8320c-125">Object identity</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-126">In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span><span class="sxs-lookup"><span data-stu-id="8320c-126">In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span></span>  <span data-ttu-id="8320c-127">The JavaScript engine maintains a map of known objects.</span><span class="sxs-lookup"><span data-stu-id="8320c-127">The JavaScript engine maintains a map of known objects.</span></span>  <span data-ttu-id="8320c-128">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span><span class="sxs-lookup"><span data-stu-id="8320c-128">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span></span>  <span data-ttu-id="8320c-129">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span><span class="sxs-lookup"><span data-stu-id="8320c-129">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span></span>  <span data-ttu-id="8320c-130">There are two kinds of exceptions:</span><span class="sxs-lookup"><span data-stu-id="8320c-130">There are two kinds of exceptions:</span></span>  
      
      *   <span data-ttu-id="8320c-131">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="8320c-131">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span></span>  <span data-ttu-id="8320c-132">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span><span class="sxs-lookup"><span data-stu-id="8320c-132">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span></span>  
      *   <span data-ttu-id="8320c-133">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span><span class="sxs-lookup"><span data-stu-id="8320c-133">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span></span>  <span data-ttu-id="8320c-134">Every time a structure or delegate is returned, it gets a new reference.</span><span class="sxs-lookup"><span data-stu-id="8320c-134">Every time a structure or delegate is returned, it gets a new reference.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-135">Name collisions</span><span class="sxs-lookup"><span data-stu-id="8320c-135">Name collisions</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-136">Multiple Windows Runtime interfaces may have members with the same names.</span><span class="sxs-lookup"><span data-stu-id="8320c-136">Multiple Windows Runtime interfaces may have members with the same names.</span></span>  <span data-ttu-id="8320c-137">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span><span class="sxs-lookup"><span data-stu-id="8320c-137">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span></span>  <span data-ttu-id="8320c-138">You can call these members by using the following syntax:</span><span class="sxs-lookup"><span data-stu-id="8320c-138">You can call these members by using the following syntax:</span></span>  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      <span data-ttu-id="8320c-139">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span><span class="sxs-lookup"><span data-stu-id="8320c-139">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span></span>  
      
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
      
      <span data-ttu-id="8320c-140">Here is how you can call the above code in JavaScript.</span><span class="sxs-lookup"><span data-stu-id="8320c-140">Here is how you can call the above code in JavaScript.</span></span>  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` <span data-ttu-id="8320c-141">parameters</span><span class="sxs-lookup"><span data-stu-id="8320c-141">parameters</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-142">If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span><span class="sxs-lookup"><span data-stu-id="8320c-142">If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span></span>  <span data-ttu-id="8320c-143">For example, consider the following Windows Runtime signature in C++.</span><span class="sxs-lookup"><span data-stu-id="8320c-143">For example, consider the following Windows Runtime signature in C++.</span></span>  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      <span data-ttu-id="8320c-144">The JavaScript version of this signature is:</span><span class="sxs-lookup"><span data-stu-id="8320c-144">The JavaScript version of this signature is:</span></span>  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      <span data-ttu-id="8320c-145">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span><span class="sxs-lookup"><span data-stu-id="8320c-145">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="8320c-146">Static members</span><span class="sxs-lookup"><span data-stu-id="8320c-146">Static members</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="8320c-147">The Windows Runtime defines both static members and instance members.</span><span class="sxs-lookup"><span data-stu-id="8320c-147">The Windows Runtime defines both static members and instance members.</span></span>  <span data-ttu-id="8320c-148">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span><span class="sxs-lookup"><span data-stu-id="8320c-148">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span></span>  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
<span data-ttu-id="8320c-149">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span><span class="sxs-lookup"><span data-stu-id="8320c-149">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span></span>  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "JavaScript Representation of Windows Runtime Types | Microsoft Docs"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "Windows Runtime components with C++/CX | Microsoft Docs"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "Windows Runtime components with C# and Visual Basic | Microsoft Docs"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array | MDN"  