---
title: 使用 Windows 运行时异步方法
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d9d59fb8b97e34feb002de1477dbe38709bde713
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942075"
---
# <span data-ttu-id="684c8-102">使用 Windows 运行时异步方法</span><span class="sxs-lookup"><span data-stu-id="684c8-102">Using Windows Runtime asynchronous methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="684c8-103">许多 Windows 运行时方法（特别是可能需要较长时间才能完成的方法）都是异步的。</span><span class="sxs-lookup"><span data-stu-id="684c8-103">Many Windows Runtime methods, especially methods that might take a long time to complete, are asynchronous.</span></span>  <span data-ttu-id="684c8-104">这些方法通常会返回异步操作或操作 \ (，例如 `Windows.Foundation.IAsyncAction` ，， `Windows.Foundation.IAsyncOperation` 或 `Windows.Foundation.IAsyncActionWithProgress` `Windows.Foundation.IAsyncOperationWithProgress` \) 。</span><span class="sxs-lookup"><span data-stu-id="684c8-104">These methods generally return an asynchronous action or operation \(for example, `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, or `Windows.Foundation.IAsyncOperationWithProgress`\).</span></span>  <span data-ttu-id="684c8-105">以 JavaScript 格式表示 [的公共游戏/Promises/A 模式表示这些方法][CommonjsWikiPromises]。</span><span class="sxs-lookup"><span data-stu-id="684c8-105">These methods are represented in JavaScript by the [CommonJS/Promises/A pattern][CommonjsWikiPromises].</span></span>  <span data-ttu-id="684c8-106">即，它们返回的 Promise 对象具有 [then 函数][PreviousVersionsWindowsAppsBr229728]，为该对象必须提供一个在操作成功后处理结果 `completed` 的函数。</span><span class="sxs-lookup"><span data-stu-id="684c8-106">That is, they return a Promise object that has a [then function][PreviousVersionsWindowsAppsBr229728], for which you must provide a `completed` function that handles the result if the operation succeeds.</span></span>  <span data-ttu-id="684c8-107">如果不希望提供错误处理程序，则应使用 [done 函数][PreviousVersionsWindowsAppsHr701079] 而不是 `then` 函数。</span><span class="sxs-lookup"><span data-stu-id="684c8-107">If you don't want to provide an error handler, you should use the [done function][PreviousVersionsWindowsAppsHr701079] instead of the `then` function.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="684c8-108">Windows 运行时功能不适用于在运行时运行Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="684c8-108">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="684c8-109">异步方法示例</span><span class="sxs-lookup"><span data-stu-id="684c8-109">Examples of asynchronous methods</span></span>  

<span data-ttu-id="684c8-110">在下面的示例中 `then` ，该函数采用表示该方法的完整值的 `createResourceAsync` 参数。</span><span class="sxs-lookup"><span data-stu-id="684c8-110">In the following example, the `then` function takes a parameter that represents the completed value of the `createResourceAsync` method.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="684c8-111">在此情况下，如果 `createResourceAsync` 该方法失败，它会在错误状态下返回一个承诺，但不引发异常。</span><span class="sxs-lookup"><span data-stu-id="684c8-111">In this case, if the `createResourceAsync` method fails, it returns a promise in the error state, but does not throw an exception.</span></span>  <span data-ttu-id="684c8-112">可以按照如下方式使用 `then` 该函数来处理错误。</span><span class="sxs-lookup"><span data-stu-id="684c8-112">You can handle an error by using the `then` function as follows.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
              console.log("New item is: " + newItem.id);
          }
          function(err) {
              console.log("Got error: " + err.message);
          });
```  

<span data-ttu-id="684c8-113">如果不希望显式处理错误，但希望它引发异常，则可以改用 `done` 函数。</span><span class="sxs-lookup"><span data-stu-id="684c8-113">If you don't want to handle the error explicitly, but do want it to throw an exception, you can use the `done` function instead.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="684c8-114">你还可以通过使用第三个函数，显示为完成的进度。</span><span class="sxs-lookup"><span data-stu-id="684c8-114">You can also display the progress made towards completion by using a third function.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .then(function(newItem) {
               console.log("New item is: " + newItem.id);
            },
    // Error.
            function(error) {
               alert("Failed to create a resource.");
            },
    // Progress.
            function(progress, resultSoFar) {
               setProgressBar(progress);
            });
```  

<span data-ttu-id="684c8-115">有关异步编程的详细信息，请参阅 [JavaScript 中的异步编程][PreviousVersionsWindowsAppsHh700330]。</span><span class="sxs-lookup"><span data-stu-id="684c8-115">For more information about asynchronous programming, see [Asynchronous Programming in JavaScript][PreviousVersionsWindowsAppsHh700330].</span></span>  

## <span data-ttu-id="684c8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="684c8-116">See also</span></span>  

[<span data-ttu-id="684c8-117">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="684c8-117">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft 文档"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then method |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "使用 JavaScript 异步编写的 (HTML) |Microsoft 文档"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done 方法 |Microsoft 文档"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "Promises |CommonJS Spec Wiki"  
