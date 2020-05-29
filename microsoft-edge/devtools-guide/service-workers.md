---
description: 使用 "服务工作人员" 面板管理和调试你的服务工作人员
title: DevTools-调试程序-服务工作人员
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、调试器、调试、pwa、服务工作人员、缓存 api
ms.custom: seodec18
ms.openlocfilehash: 8e1fa62358657a47ce40d0742f95a76f2586d0c8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563458"
---
# <span data-ttu-id="35682-104">服务工作人员</span><span class="sxs-lookup"><span data-stu-id="35682-104">Service Workers</span></span>

<span data-ttu-id="35682-105">"**服务工作者**" 面板具有用于管理和调试网站的服务工作人员的工具，可帮助你：</span><span class="sxs-lookup"><span data-stu-id="35682-105">The **Service Workers** panel has tools for managing and debugging the service workers for your site, to help you:</span></span>

 - <span data-ttu-id="35682-106">大致了解与您的网站相关联的所有服务工作者及其范围和状态的详细信息</span><span class="sxs-lookup"><span data-stu-id="35682-106">Get an overview of all the service workers associated with your site and details of their scope and status</span></span>
 - <span data-ttu-id="35682-107">**更新**和管理（**注销**）给定范围的服务工作人员注册</span><span class="sxs-lookup"><span data-stu-id="35682-107">**Update** and manage (**Unregister**) the service worker registration for the given scope</span></span>
 - <span data-ttu-id="35682-108">**推送**测试通知</span><span class="sxs-lookup"><span data-stu-id="35682-108">**Push** a test notification</span></span>
 - <span data-ttu-id="35682-109">**停止** /**启动**单个服务工作人员，然后</span><span class="sxs-lookup"><span data-stu-id="35682-109">**Stop**/**Start** individual service workers, and</span></span>
 - <span data-ttu-id="35682-110">在单独的调试器窗口中**检查**所选服务工作人员</span><span class="sxs-lookup"><span data-stu-id="35682-110">**Inspect** the selected service worker in a separate debugger window</span></span>

![服务工作人员概述窗格](./media/service_worker.png)

<span data-ttu-id="35682-112">请注意以下有关 Edge DevTools 中的服务工作者调试的信息：</span><span class="sxs-lookup"><span data-stu-id="35682-112">Please note the following about service worker debugging in Edge DevTools:</span></span>

 - <span data-ttu-id="35682-113">调试服务工作人员将启动与页面工具分开的 DevTools 的新实例，因为服务工作人员可以在多个选项卡之间共享。</span><span class="sxs-lookup"><span data-stu-id="35682-113">Debugging a service worker will launch a new instance of the  DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span>
 - <span data-ttu-id="35682-114">如果服务工作者在后台运行，并且不直接控制应用的前端，则服务工作器调试器中不存在[**元素**](./elements.md)和[**仿真**](./emulation.md)面板。</span><span class="sxs-lookup"><span data-stu-id="35682-114">The [**Elements**](./elements.md) and [**Emulation**](./emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="35682-115">当前服务工作器的网络流量仅从该工作人员的 DevTools 调试实例报告，而不是从页面本身的调试器实例中报告。</span><span class="sxs-lookup"><span data-stu-id="35682-115">Currently network traffic for a service worker is only reported from the  DevTools debugging instance for that worker, and not from the debugger instance for the page itself.</span></span>
 - <span data-ttu-id="35682-116">若要从 DevTools 模拟**推送**，需要将*push*事件侦听器添加到服务工作人员，以便观察其效果。</span><span class="sxs-lookup"><span data-stu-id="35682-116">To simulate a **Push** from the DevTools, you'll need to add a *push* event listener to your service worker in order to observe its effect.</span></span> <span data-ttu-id="35682-117">以下示例将在服务工作器**控制台**中打印 "从 DevTools 测试推送消息"。</span><span class="sxs-lookup"><span data-stu-id="35682-117">The following example will print "Test push message from DevTools" in your service worker **Console**.</span></span>

   ```JavaScript
   self.addEventListener('push', function(event){
       console.log(event.data.text());
   });
   ```

<span data-ttu-id="35682-118">下面是使用服务工作人员时需要牢记的一些一般事项：</span><span class="sxs-lookup"><span data-stu-id="35682-118">Here are some general things to keep in mind when using service workers:</span></span>

- **<span data-ttu-id="35682-119">仅限 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="35682-119">HTTPS-only.</span></span>** <span data-ttu-id="35682-120">服务工作人员将无法在 HTTP 中使用;您将需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="35682-120">Service workers will not work in HTTP; you will need to use HTTPS.</span></span> <span data-ttu-id="35682-121">但是，你可以出于测试目的注册服务工作人员 `localhost` 。</span><span class="sxs-lookup"><span data-stu-id="35682-121">However, you can register service workers on `localhost` for testing purposes.</span></span>

- **<span data-ttu-id="35682-122">不允许 DOM 访问。</span><span class="sxs-lookup"><span data-stu-id="35682-122">No DOM access allowed.</span></span>** <span data-ttu-id="35682-123">与 web 工作人员一样，您不能访问页面的对象模型。</span><span class="sxs-lookup"><span data-stu-id="35682-123">As with web workers, you don't get access to the page's object model.</span></span> <span data-ttu-id="35682-124">这意味着，如果你需要更改有关页面的某些内容，你将需要 [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) 从服务工作人员到页面的使用，以便你可以从页面处理 DOM 更改。</span><span class="sxs-lookup"><span data-stu-id="35682-124">This means that if you need to change something about the page, you'll need to use [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) from the service worker to the page so that you can handle it DOM changes from the page.</span></span>

- **<span data-ttu-id="35682-125">独立于页面执行。</span><span class="sxs-lookup"><span data-stu-id="35682-125">Executes separate from page.</span></span>** <span data-ttu-id="35682-126">由于这些脚本不依赖于页面的生存期，因此请务必了解它们不会与页面共享相同的上下文。</span><span class="sxs-lookup"><span data-stu-id="35682-126">Because these scripts are not tied to the lifetime of a page, it's important to understand that they do not share the same context as the page.</span></span> <span data-ttu-id="35682-127">除了没有对 DOM 的访问权限（如上文所述）之外，它们将无法访问页面上提供的相同变量。</span><span class="sxs-lookup"><span data-stu-id="35682-127">Aside from not having access to the DOM (as stated earlier), they won't have access to the same variables available on the page.</span></span>

- **<span data-ttu-id="35682-128">替代*应用缓存*。</span><span class="sxs-lookup"><span data-stu-id="35682-128">Overrides *App Cache*.</span></span>** <span data-ttu-id="35682-129">服务工作人员正在使用时，将忽略应用缓存。</span><span class="sxs-lookup"><span data-stu-id="35682-129">App Cache will be ignored when service workers are in use.</span></span> <span data-ttu-id="35682-130">服务工作者 API 旨在通过向 web 开发人员提供更精细的控制来完全 supplant 应用缓存。</span><span class="sxs-lookup"><span data-stu-id="35682-130">The Service Worker API is intended to entirely supplant App Cache  by giving more granular control to the web developer.</span></span>

  - **<span data-ttu-id="35682-131">脚本不能在 CDN 上显示。</span><span class="sxs-lookup"><span data-stu-id="35682-131">Script can't be on CDN.</span></span>** <span data-ttu-id="35682-132">服务工作人员的 JavaScript 文件不能托管在内容分发网络（CDN）上，它必须与页面位于同一域。</span><span class="sxs-lookup"><span data-stu-id="35682-132">The JavaScript file for the service worker can't be hosted on a Content Distribution Network (CDN), it must be on the same domain as the page.</span></span> <span data-ttu-id="35682-133">但是，如果你愿意，可以从 CDN 导入脚本。</span><span class="sxs-lookup"><span data-stu-id="35682-133">However, if you like, you can import scripts from your CDN.</span></span>

- **<span data-ttu-id="35682-134">随时可以终止。</span><span class="sxs-lookup"><span data-stu-id="35682-134">Can be terminated any time.</span></span>** <span data-ttu-id="35682-135">服务工作者的生命周期很短，其生命周期绑定到事件。</span><span class="sxs-lookup"><span data-stu-id="35682-135">Service workers are meant to be short-lived and their lifetime is tied to events.</span></span> <span data-ttu-id="35682-136">特别是，服务工作人员有一个时间限制，它们必须完成其事件处理程序的执行。</span><span class="sxs-lookup"><span data-stu-id="35682-136">In particular, service workers have a time limit in which they must finish executing their event handlers.</span></span> <span data-ttu-id="35682-137">在其他情况下，浏览器或操作系统可能会选择终止影响电池、CPU 或内存消耗的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="35682-137">In other cases, the browser or the operating system may choose to terminate a service worker that impacts the battery, CPU, or memory consumption.</span></span> <span data-ttu-id="35682-138">在任何一种情况下，请避免在服务工作脚本中依赖全局变量，以防在正在处理的后续事件中使用不同的服务工作者实例。</span><span class="sxs-lookup"><span data-stu-id="35682-138">In either case, avoid relying on global variables in the service worker script in case a different service worker instance is used on a subsequent event that's being handled.</span></span>

- **<span data-ttu-id="35682-139">仅允许异步请求。</span><span class="sxs-lookup"><span data-stu-id="35682-139">Only asynchronous requests allowed.</span></span>** <span data-ttu-id="35682-140">此处不允许使用同步 XHR！</span><span class="sxs-lookup"><span data-stu-id="35682-140">Synchronous XHR is not allowed here!</span></span> <span data-ttu-id="35682-141">不 localStorage，因此最好使用 IndexedDB 和前面介绍的新缓存 API。</span><span class="sxs-lookup"><span data-stu-id="35682-141">Neither is localStorage, so it's best to make use of IndexedDB and the new Caches API described earlier.</span></span>

- **<span data-ttu-id="35682-142">作用域的服务工作人员为1:1。</span><span class="sxs-lookup"><span data-stu-id="35682-142">Service worker to scope is 1:1.</span></span>** <span data-ttu-id="35682-143">每个作用域只能有一个服务工作者。</span><span class="sxs-lookup"><span data-stu-id="35682-143">You'll only be able to have one service worker per scope.</span></span> <span data-ttu-id="35682-144">这意味着，如果你尝试为已具有服务工作人员的作用域注册不同的服务工作人员，该服务工作人员将更新。</span><span class="sxs-lookup"><span data-stu-id="35682-144">That means if you try to register a different service worker for a scope that already has a service worker, that service worker will be updated.</span></span>
