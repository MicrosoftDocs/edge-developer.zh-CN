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
ms.openlocfilehash: ad51afee97d3cc3e913ecdd73c4f0c2a99c70564
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895536"
---
# <span data-ttu-id="759fa-104">线程模型</span><span class="sxs-lookup"><span data-stu-id="759fa-104">Threading model</span></span>  

## <span data-ttu-id="759fa-105">线程安全</span><span class="sxs-lookup"><span data-stu-id="759fa-105">Thread safety</span></span>  

<span data-ttu-id="759fa-106">WebView2 必须在 UI 线程上创建。</span><span class="sxs-lookup"><span data-stu-id="759fa-106">The WebView2 must be created on a UI thread.</span></span>  <span data-ttu-id="759fa-107">专门使用消息泵的线程。</span><span class="sxs-lookup"><span data-stu-id="759fa-107">Specifically a thread with a message pump.</span></span>  <span data-ttu-id="759fa-108">所有回调都在该线程上发生，并且对 WebView2 的请求必须在该线程上完成。</span><span class="sxs-lookup"><span data-stu-id="759fa-108">All callbacks occur on that thread and requests into the WebView2 must be done on that thread.</span></span>  <span data-ttu-id="759fa-109">使用来自另一个线程的 WebView2 是不安全的。</span><span class="sxs-lookup"><span data-stu-id="759fa-109">It is not safe to use the WebView2 from another thread.</span></span>  

<span data-ttu-id="759fa-110">唯一的例外是针对的 `Content` 属性 `CoreWebView2WebResourceRequest` 。</span><span class="sxs-lookup"><span data-stu-id="759fa-110">The only exception is for the `Content` property of `CoreWebView2WebResourceRequest`.</span></span>  <span data-ttu-id="759fa-111">`Content`从后台线程读取属性流。</span><span class="sxs-lookup"><span data-stu-id="759fa-111">The `Content` property stream is read from a background thread.</span></span>  <span data-ttu-id="759fa-112">流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。</span><span class="sxs-lookup"><span data-stu-id="759fa-112">The stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span>  

## <span data-ttu-id="759fa-113">重</span><span class="sxs-lookup"><span data-stu-id="759fa-113">Reentrancy</span></span>  

<span data-ttu-id="759fa-114">回调包括事件处理程序和完成处理程序按顺序运行。</span><span class="sxs-lookup"><span data-stu-id="759fa-114">Callbacks including event handlers and completion handlers run serially.</span></span>  <span data-ttu-id="759fa-115">如果你有一个事件处理程序正在运行并开始消息循环，则任何其他事件处理程序或完成回调都无法以重入方式开始运行。</span><span class="sxs-lookup"><span data-stu-id="759fa-115">If you have an event handler running and begin a message loop, no other event handlers or completion callbacks are able to begin running in a reentrant manner.</span></span>  

## <span data-ttu-id="759fa-116">延迟</span><span class="sxs-lookup"><span data-stu-id="759fa-116">Deferrals</span></span>  

<span data-ttu-id="759fa-117">某些 WebView2 事件会读取其事件参数上设置的值，或在事件处理程序完成后执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="759fa-117">Some WebView2 events read values set on their event args or perform some action after the event handler completes.</span></span>  <span data-ttu-id="759fa-118">如果你还需要运行异步操作（如事件处理程序），你可以 `GetDeferral` 对关联事件的事件参数使用该方法。</span><span class="sxs-lookup"><span data-stu-id="759fa-118">If you also need to run an asynchronous operation such an event handler, you may use the `GetDeferral` method on the event args of the associated events.</span></span>  <span data-ttu-id="759fa-119">返回的延迟对象可确保事件处理程序在请求的方法之前不会被视为已完成 `Complete` `Deferral` 。</span><span class="sxs-lookup"><span data-stu-id="759fa-119">The returned Deferral object ensures the event handler is not considered complete until the `Complete` method of the `Deferral` is requested.</span></span>  

<span data-ttu-id="759fa-120">例如，你可以使用 `NewWindowRequested` 事件来提供在 `CoreWebView2` 事件处理程序完成时作为子窗口连接的。</span><span class="sxs-lookup"><span data-stu-id="759fa-120">For instance, you may use the `NewWindowRequested` event to provide a `CoreWebView2` to connect as a child window when the event handler completes.</span></span>  <span data-ttu-id="759fa-121">但是，如果需要异步创建 `CoreWebView2` ，请 `GetDeferral` 在上请求该方法 `NewWindowRequestedEventArgs` 。</span><span class="sxs-lookup"><span data-stu-id="759fa-121">But if you need to asynchronously create the `CoreWebView2`, request the `GetDeferral` method on the `NewWindowRequestedEventArgs`.</span></span>  <span data-ttu-id="759fa-122">在上异步创建 `CoreWebView2` 并设置 `NewWindow` 属性后 `NewWindowRequestedEventArgs` ， `Complete` `Deferral` 使用方法返回对对象的请求 `GetDeferral` 。</span><span class="sxs-lookup"><span data-stu-id="759fa-122">After you have asynchronously created the `CoreWebView2` and set the `NewWindow` property on the `NewWindowRequestedEventArgs`, request `Complete` on the `Deferral` object be returned using the `GetDeferral` method.</span></span>  

<!-- links -->  
