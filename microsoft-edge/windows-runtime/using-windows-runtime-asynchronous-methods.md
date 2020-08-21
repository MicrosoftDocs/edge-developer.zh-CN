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
# 使用 Windows 运行时异步方法  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

许多 Windows 运行时方法（特别是可能需要较长时间才能完成的方法）都是异步的。  这些方法通常会返回异步操作或操作 \ (，例如 `Windows.Foundation.IAsyncAction` ，， `Windows.Foundation.IAsyncOperation` 或 `Windows.Foundation.IAsyncActionWithProgress` `Windows.Foundation.IAsyncOperationWithProgress` \) 。  以 JavaScript 格式表示 [的公共游戏/Promises/A 模式表示这些方法][CommonjsWikiPromises]。  即，它们返回的 Promise 对象具有 [then 函数][PreviousVersionsWindowsAppsBr229728]，为该对象必须提供一个在操作成功后处理结果 `completed` 的函数。  如果不希望提供错误处理程序，则应使用 [done 函数][PreviousVersionsWindowsAppsHr701079] 而不是 `then` 函数。  

> [!IMPORTANT]
> Windows 运行时功能不适用于在运行时运行Internet Explorer。  

## 异步方法示例  

在下面的示例中 `then` ，该函数采用表示该方法的完整值的 `createResourceAsync` 参数。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

在此情况下，如果 `createResourceAsync` 该方法失败，它会在错误状态下返回一个承诺，但不引发异常。  可以按照如下方式使用 `then` 该函数来处理错误。  

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

如果不希望显式处理错误，但希望它引发异常，则可以改用 `done` 函数。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

你还可以通过使用第三个函数，显示为完成的进度。  

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

有关异步编程的详细信息，请参阅 [JavaScript 中的异步编程][PreviousVersionsWindowsAppsHh700330]。  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft 文档"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "Promise.then method |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "使用 JavaScript 异步编写的 (HTML) |Microsoft 文档"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "Promise.done 方法 |Microsoft 文档"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "Promises |CommonJS Spec Wiki"  
