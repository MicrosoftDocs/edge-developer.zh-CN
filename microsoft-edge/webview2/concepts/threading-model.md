---
description: 线程模型
title: 线程模型
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 61e3b7fc8d25e2a1ce9c60fb84f5f39ba43f281b
ms.sourcegitcommit: efdc6369c48942bfa39e45c713300ed70f0e3655
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "11013735"
---
# 线程模型 

WebView2 控件基于 [组件对象模型 (COM) ](https://docs.microsoft.com/windows/win32/com/the-component-object-model) ，并且必须在 [单线程单元 (STA) ](https://docs.microsoft.com/windows/win32/com/single-threaded-apartments) 线程上运行。

## 线程安全  

WebView2 必须在 UI 线程上创建。  专门使用消息泵的线程。  所有回调都在该线程上发生，并且对 WebView2 的请求必须在该线程上完成。  使用来自另一个线程的 WebView2 是不安全的。  

唯一的例外是针对的 `Content` 属性 `CoreWebView2WebResourceRequest` 。  `Content`从后台线程读取属性流。  流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。  

## 重  

回调包括事件处理程序和完成处理程序按顺序运行。  如果你有一个事件处理程序正在运行并开始消息循环，则任何其他事件处理程序或完成回调都无法以重入方式开始运行。  

## 延迟  

某些 WebView2 事件会读取其事件参数上设置的值，或在事件处理程序完成后执行某些操作。  如果你还需要运行异步操作（如事件处理程序），你可以 `GetDeferral` 对关联事件的事件参数使用该方法。  返回的延迟对象可确保事件处理程序在请求的方法之前不会被视为已完成 `Complete` `Deferral` 。  

例如，你可以使用 `NewWindowRequested` 事件来提供在 `CoreWebView2` 事件处理程序完成时作为子窗口连接的。  但是，如果需要异步创建 `CoreWebView2` ，请 `GetDeferral` 在上请求该方法 `NewWindowRequestedEventArgs` 。  在上异步创建 `CoreWebView2` 并设置 `NewWindow` 属性后 `NewWindowRequestedEventArgs` ， `Complete` `Deferral` 使用方法返回对对象的请求 `GetDeferral` 。  

<!-- links -->  
