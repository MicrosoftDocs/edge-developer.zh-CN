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
# <span data-ttu-id="ccdd4-102">使用 Windows 运行时异步方法</span><span class="sxs-lookup"><span data-stu-id="ccdd4-102">Using Windows Runtime asynchronous methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="ccdd4-103">许多 Windows 运行时方法（尤其是可能需要很长时间才能完成的方法）都是异步的。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-103">Many Windows Runtime methods, especially methods that might take a long time to complete, are asynchronous.</span></span>  <span data-ttu-id="ccdd4-104">这些方法通常返回异步操作 \ (例如、、、 `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` 或 `Windows.Foundation.IAsyncOperationWithProgress` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-104">These methods generally return an asynchronous action or operation \(for example, `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, or `Windows.Foundation.IAsyncOperationWithProgress`\).</span></span>  <span data-ttu-id="ccdd4-105">这些方法通过 [CommonJS/承诺/A 模式][CommonjsWikiPromises]在 JavaScript 中表示。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-105">These methods are represented in JavaScript by the [CommonJS/Promises/A pattern][CommonjsWikiPromises].</span></span>  <span data-ttu-id="ccdd4-106">也就是说，它们返回具有 [then 函数][PreviousVersionsWindowsAppsBr229728]的承诺对象，您必须提供一个 `completed` 函数来处理结果（如果操作成功）。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-106">That is, they return a Promise object that has a [then function][PreviousVersionsWindowsAppsBr229728], for which you must provide a `completed` function that handles the result if the operation succeeds.</span></span>  <span data-ttu-id="ccdd4-107">如果不希望提供错误处理程序，则应使用 [done 函数][PreviousVersionsWindowsAppsHr701079] 而不是 `then` 函数。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-107">If you don't want to provide an error handler, you should use the [done function][PreviousVersionsWindowsAppsHr701079] instead of the `then` function.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ccdd4-108">对于在 Internet Explorer 中运行的应用，Windows 运行时功能不可用。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-108">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="ccdd4-109">异步方法示例</span><span class="sxs-lookup"><span data-stu-id="ccdd4-109">Examples of asynchronous methods</span></span>  

<span data-ttu-id="ccdd4-110">在下面的示例中，该 `then` 函数接受一个表示该方法的已完成值的参数 `createResourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-110">In the following example, the `then` function takes a parameter that represents the completed value of the `createResourceAsync` method.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="ccdd4-111">在这种情况下，如果该 `createResourceAsync` 方法失败，它将返回错误状态中的承诺，但不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-111">In this case, if the `createResourceAsync` method fails, it returns a promise in the error state, but does not throw an exception.</span></span>  <span data-ttu-id="ccdd4-112">你可以通过使用函数来处理错误，如下所示 `then` 。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-112">You can handle an error by using the `then` function as follows.</span></span>  

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

<span data-ttu-id="ccdd4-113">如果你不希望显式处理错误，但希望它引发异常，则可以 `done` 改用该函数。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-113">If you don't want to handle the error explicitly, but do want it to throw an exception, you can use the `done` function instead.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="ccdd4-114">您还可以通过使用第三个函数来显示完成进度。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-114">You can also display the progress made towards completion by using a third function.</span></span>  

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

<span data-ttu-id="ccdd4-115">有关异步编程的详细信息，请参阅 [JavaScript 中的异步编程][PreviousVersionsWindowsAppsHh700330]。</span><span class="sxs-lookup"><span data-stu-id="ccdd4-115">For more information about asynchronous programming, see [Asynchronous Programming in JavaScript][PreviousVersionsWindowsAppsHh700330].</span></span>  

## <span data-ttu-id="ccdd4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccdd4-116">See also</span></span>  

[<span data-ttu-id="ccdd4-117">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="ccdd4-117">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript | 中使用 Windows 运行时Microsoft 文档"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "承诺。然后方法 |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript 中的异步编程 (HTML) |Microsoft 文档"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "承诺。完成方法 |Microsoft 文档"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "承诺 |CommonJS 规范 Wiki"  
