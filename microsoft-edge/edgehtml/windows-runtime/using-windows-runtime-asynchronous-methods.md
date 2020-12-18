---
description: 使用 Windows 运行时异步方法。
title: 使用 Windows 运行时异步方法
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 26ed26e07049a9488aebe5fda92a65550474b51c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232313"
---
# 使用 Windows 运行时异步方法  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

许多 Windows 运行时方法（尤其是可能需要很长时间才能完成的方法）都是异步方法。  这些方法通常返回异步操作或操作 \ (例如 `Windows.Foundation.IAsyncAction` ， ， 或 `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` `Windows.Foundation.IAsyncOperationWithProgress` \) 。  这些方法用 [CommonJS/Promises/A][CommonjsWikiPromises]模式在 JavaScript 中表示。  即，它们返回一个具有 then 函数[][PreviousVersionsWindowsAppsBr229728]的 Promise 对象，如果操作成功，您必须提供用于处理结果 `completed` 的函数。  如果不想提供错误处理程序，应该使用 [done 函数][PreviousVersionsWindowsAppsHr701079] 而不是 `then` 函数。  

> [!IMPORTANT]
> Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。  

## 异步方法示例  

在下面的示例中， `then` 该函数采用一个参数，该参数代表方法的完成 `createResourceAsync` 值。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

在这种情况下，如果该方法失败，它将返回错误状态中的承诺， `createResourceAsync` 但不引发异常。  可以使用函数处理错误 `then` ，如下所示。  

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

如果不希望显式处理错误，但希望它引发异常，可以改为使用该 `done` 函数。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

您还可以使用第三个函数显示完成进度。  

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

有关异步编程详细信息，请参阅 [JavaScript 中的异步编程][PreviousVersionsWindowsAppsHh700330]。  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then 方法 |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript (HTML) 中的异步编程 |Microsoft Docs"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done 方法 |Microsoft Docs"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "承诺 |CommonJS Spec Wiki"  
