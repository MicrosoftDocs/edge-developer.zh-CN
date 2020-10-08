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

许多 Windows 运行时方法（尤其是可能需要很长时间才能完成的方法）都是异步的。  这些方法通常返回异步操作 \ (例如、、、 `Windows.Foundation.IAsyncAction` `Windows.Foundation.IAsyncOperation` `Windows.Foundation.IAsyncActionWithProgress` 或 `Windows.Foundation.IAsyncOperationWithProgress` \ ) 。  这些方法通过 [CommonJS/承诺/A 模式][CommonjsWikiPromises]在 JavaScript 中表示。  也就是说，它们返回具有 [then 函数][PreviousVersionsWindowsAppsBr229728]的承诺对象，您必须提供一个 `completed` 函数来处理结果（如果操作成功）。  如果不希望提供错误处理程序，则应使用 [done 函数][PreviousVersionsWindowsAppsHr701079] 而不是 `then` 函数。  

> [!IMPORTANT]
> 对于在 Internet Explorer 中运行的应用，Windows 运行时功能不可用。  

## 异步方法示例  

在下面的示例中，该 `then` 函数接受一个表示该方法的已完成值的参数 `createResourceAsync` 。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
    .then(function(newItem) {
        console.log("New item is: " + newItem.id);
            });
```  

在这种情况下，如果该 `createResourceAsync` 方法失败，它将返回错误状态中的承诺，但不会引发异常。  你可以通过使用函数来处理错误，如下所示 `then` 。  

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

如果你不希望显式处理错误，但希望它引发异常，则可以 `done` 改用该函数。  

```javascript
client.createResourceAsync(uri, description, item)
    // Success.
      .done(function(newItem) {
               console.log("New item is: " + newItem.id);
            });
```  

您还可以通过使用第三个函数来显示完成进度。  

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

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript | 中使用 Windows 运行时Microsoft 文档"  

[PreviousVersionsWindowsAppsBr229728]: /previous-versions/windows/apps/br229728(v=win.10) "承诺。然后方法 |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh700330]: /previous-versions/windows/apps/hh700330(v=win.10) "JavaScript 中的异步编程 (HTML) |Microsoft 文档"
[PreviousVersionsWindowsAppsHr701079]: /previous-versions/windows/apps/hh701079(v=win.10) "承诺。完成方法 |Microsoft 文档"  

[CommonjsWikiPromises]: http://wiki.commonjs.org/wiki/Promises "承诺 |CommonJS 规范 Wiki"  
