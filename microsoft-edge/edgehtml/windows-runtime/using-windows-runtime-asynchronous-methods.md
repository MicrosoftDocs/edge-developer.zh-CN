---
description: 使用 Windows 运行时异步方法
title: 使用 Windows 运行时异步方法
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c7e8ac4690525ee89a06eccf843531c2c7a20324
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398152"
---
# <a name="using-windows-runtime-asynchronous-methods"></a><span data-ttu-id="6c396-103">使用 Windows 运行时异步方法</span><span class="sxs-lookup"><span data-stu-id="6c396-103">Using Windows Runtime asynchronous methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="6c396-104">许多 Windows 运行时方法（尤其是可能需要很长时间才能完成的方法）都是异步方法。</span><span class="sxs-lookup"><span data-stu-id="6c396-104">Many Windows Runtime methods, especially methods that might take a long time to complete, are asynchronous.</span></span>  <span data-ttu-id="6c396-105">这些方法通常返回异步操作或操作 \ (例如 ， ， `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` 或 `Windows.Foundation.IAsyncActionWithProgress` `Windows.Foundation.IAsyncOperationWithProgress` \) 。</span><span class="sxs-lookup"><span data-stu-id="6c396-105">These methods generally return an asynchronous action or operation \(for example, `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, or `Windows.Foundation.IAsyncOperationWithProgress`\).</span></span>  <span data-ttu-id="6c396-106">这些方法在 JavaScript 中由 [CommonJS/Promises/A 模式表示][CommonjsWikiPromises]。</span><span class="sxs-lookup"><span data-stu-id="6c396-106">These methods are represented in JavaScript by the [CommonJS/Promises/A pattern][CommonjsWikiPromises].</span></span>  <span data-ttu-id="6c396-107">即，它们返回一个具有 [then][PreviousVersionsWindowsAppsBr229728]函数的 Promise 对象，如果操作成功，必须提供用于处理结果 `completed` 的函数。</span><span class="sxs-lookup"><span data-stu-id="6c396-107">That is, they return a Promise object that has a [then function][PreviousVersionsWindowsAppsBr229728], for which you must provide a `completed` function that handles the result if the operation succeeds.</span></span>  <span data-ttu-id="6c396-108">如果不想提供错误处理程序，应该使用 [done 函数][PreviousVersionsWindowsAppsHr701079] 而不是 `then` 函数。</span><span class="sxs-lookup"><span data-stu-id="6c396-108">If you don't want to provide an error handler, you should use the [done function][PreviousVersionsWindowsAppsHr701079] instead of the `then` function.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="6c396-109">Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="6c396-109">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <a name="examples-of-asynchronous-methods"></a><span data-ttu-id="6c396-110">异步方法示例</span><span class="sxs-lookup"><span data-stu-id="6c396-110">Examples of asynchronous methods</span></span>  

<span data-ttu-id="6c396-111">在下面的示例中，该 `then` 函数采用一个参数，该参数代表方法的完成 `createResourceAsync` 值。</span><span class="sxs-lookup"><span data-stu-id="6c396-111">In the following example, the `then` function takes a parameter that represents the completed value of the `createResourceAsync` method.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="6c396-112">在这种情况下，如果该方法失败，它将返回错误状态中的承诺， `createResourceAsync` 但不引发异常。</span><span class="sxs-lookup"><span data-stu-id="6c396-112">In this case, if the `createResourceAsync` method fails, it returns a promise in the error state, but does not throw an exception.</span></span>  <span data-ttu-id="6c396-113">可以使用函数处理 `then` 错误，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6c396-113">You can handle an error by using the `then` function as follows.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
              console.log("New item is: " + newItem.id);
          }
          function(err) {
              console.log("Got error: " + err.message);
          });
```  

<span data-ttu-id="6c396-114">如果您不想显式处理错误，但希望它引发异常，您可以改为使用该 `done` 函数。</span><span class="sxs-lookup"><span data-stu-id="6c396-114">If you don't want to handle the error explicitly, but do want it to throw an exception, you can use the `done` function instead.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

<span data-ttu-id="6c396-115">您还可以使用第三个函数显示完成进度。</span><span class="sxs-lookup"><span data-stu-id="6c396-115">You can also display the progress made towards completion by using a third function.</span></span>  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .then(function(newItem) {
               console.log("New item is: " + newItem.id);
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

<span data-ttu-id="6c396-116">有关异步编程的信息，请参阅 [JavaScript 中的异步编程][PreviousVersionsWindowsAppsHh700330]。</span><span class="sxs-lookup"><span data-stu-id="6c396-116">For more information about asynchronous programming, see [Asynchronous Programming in JavaScript][PreviousVersionsWindowsAppsHh700330].</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c396-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c396-117">See also</span></span>  

[<span data-ttu-id="6c396-118">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="6c396-118">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript |Microsoft Docs"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then 方法|Microsoft Docs"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript (HTML) |Microsoft Docs"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done 方法|Microsoft Docs"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "承诺|CommonJS 规范 Wiki"  
