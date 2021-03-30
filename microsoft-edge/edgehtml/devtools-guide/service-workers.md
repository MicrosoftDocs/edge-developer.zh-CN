---
description: 使用服务工作者面板管理和调试服务工作者
title: DevTools - 调试器 - 服务工作者
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， web development， f12 tools， devtools， debugger， debugging， pwa， service worker， cache api
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 99592f787da8bcf89d2e16231aa3f39047b4fc0b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232484"
---
# <span data-ttu-id="7b7ab-104">服务工作者</span><span class="sxs-lookup"><span data-stu-id="7b7ab-104">Service Workers</span></span>

<span data-ttu-id="7b7ab-105">服务 **工作人员** 面板具有用于管理和调试网站服务工作者的工具，可帮助你：</span><span class="sxs-lookup"><span data-stu-id="7b7ab-105">The **Service Workers** panel has tools for managing and debugging the service workers for your site, to help you:</span></span>

 - <span data-ttu-id="7b7ab-106">获取与您的网站关联的所有服务工作者的概述及其范围和状态的详细信息</span><span class="sxs-lookup"><span data-stu-id="7b7ab-106">Get an overview of all the service workers associated with your site and details of their scope and status</span></span>
 - <span data-ttu-id="7b7ab-107">**更新** 和管理 (**作用域**) 注册服务工作线程</span><span class="sxs-lookup"><span data-stu-id="7b7ab-107">**Update** and manage (**Unregister**) the service worker registration for the given scope</span></span>
 - <span data-ttu-id="7b7ab-108">**推送** 测试通知</span><span class="sxs-lookup"><span data-stu-id="7b7ab-108">**Push** a test notification</span></span>
 - <span data-ttu-id="7b7ab-109">**停止** /**启动**单个服务工作者，并</span><span class="sxs-lookup"><span data-stu-id="7b7ab-109">**Stop**/**Start** individual service workers, and</span></span>
 - <span data-ttu-id="7b7ab-110">**在** 单独的调试器窗口中检查选定的服务工作器</span><span class="sxs-lookup"><span data-stu-id="7b7ab-110">**Inspect** the selected service worker in a separate debugger window</span></span>

!["服务工作者概述"窗格](./media/service_worker.png)

<span data-ttu-id="7b7ab-112">请注意以下有关边缘 DevTools 中的服务工作器调试的信息：</span><span class="sxs-lookup"><span data-stu-id="7b7ab-112">Please note the following about service worker debugging in Edge DevTools:</span></span>

 - <span data-ttu-id="7b7ab-113">调试服务工作者将启动独立于页面工具的 DevTools 的新实例，因为服务工作者可以跨多个选项卡共享。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-113">Debugging a service worker will launch a new instance of the  DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span>
 - <span data-ttu-id="7b7ab-114">由于[**服务**](./elements.md)工作者[](./emulation.md)在后台运行，并且不直接控制应用的前端，因此服务工作器调试器中缺少元素和模拟面板。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-114">The [**Elements**](./elements.md) and [**Emulation**](./emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="7b7ab-115">目前，仅从服务工作者的 DevTools 调试实例报告服务工作者的网络流量，而不是从页面本身的调试器实例中报告。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-115">Currently network traffic for a service worker is only reported from the  DevTools debugging instance for that worker, and not from the debugger instance for the page itself.</span></span>
 - <span data-ttu-id="7b7ab-116">若要模拟 DevTools 中的推送，你需要将推送事件侦听器添加到服务 工作者，以便观察其效果。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-116">To simulate a **Push** from the DevTools, you'll need to add a *push* event listener to your service worker in order to observe its effect.</span></span> <span data-ttu-id="7b7ab-117">下面的示例将在服务工作控制台中打印"从 DevTools 测试推送**消息"。**</span><span class="sxs-lookup"><span data-stu-id="7b7ab-117">The following example will print "Test push message from DevTools" in your service worker **Console**.</span></span>

   ```JavaScript
   self.addEventListener('push', function(event){
       console.log(event.data.text());
   });
   ```

<span data-ttu-id="7b7ab-118">以下是在使用服务工作者时请记住的一些常规问题：</span><span class="sxs-lookup"><span data-stu-id="7b7ab-118">Here are some general things to keep in mind when using service workers:</span></span>

- **<span data-ttu-id="7b7ab-119">仅 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-119">HTTPS-only.</span></span>** <span data-ttu-id="7b7ab-120">服务工作人员将不会在 HTTP 中工作;将需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-120">Service workers will not work in HTTP; you will need to use HTTPS.</span></span> <span data-ttu-id="7b7ab-121">但是，您可以注册服务工作者 `localhost` 以进行测试。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-121">However, you can register service workers on `localhost` for testing purposes.</span></span>

- **<span data-ttu-id="7b7ab-122">不允许 DOM 访问。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-122">No DOM access allowed.</span></span>** <span data-ttu-id="7b7ab-123">与 Web 工作者一样，你无法访问页面的对象模型。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-123">As with web workers, you don't get access to the page's object model.</span></span> <span data-ttu-id="7b7ab-124">这意味着，如果需要更改有关页面的内容，则需要从服务工作者使用到页面，以便可以处理页面 [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) 的 DOM 更改。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-124">This means that if you need to change something about the page, you'll need to use [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) from the service worker to the page so that you can handle it DOM changes from the page.</span></span>

- **<span data-ttu-id="7b7ab-125">独立于页面执行。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-125">Executes separate from page.</span></span>** <span data-ttu-id="7b7ab-126">由于这些脚本不绑定到页面的生命周期，因此了解它们不与页面共享同一上下文很重要。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-126">Because these scripts are not tied to the lifetime of a page, it's important to understand that they do not share the same context as the page.</span></span> <span data-ttu-id="7b7ab-127">除了无法像前面 (一样访问 DOM) ，他们无法访问页面上可用的相同变量。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-127">Aside from not having access to the DOM (as stated earlier), they won't have access to the same variables available on the page.</span></span>

- **<span data-ttu-id="7b7ab-128">替代 *应用程序缓存*。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-128">Overrides *App Cache*.</span></span>** <span data-ttu-id="7b7ab-129">使用服务工作者时，将忽略应用缓存。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-129">App Cache will be ignored when service workers are in use.</span></span> <span data-ttu-id="7b7ab-130">服务工作线程 API 旨在通过向 Web 开发人员提供更精细的控制来完全取代应用程序缓存。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-130">The Service Worker API is intended to entirely supplant App Cache  by giving more granular control to the web developer.</span></span>

  - **<span data-ttu-id="7b7ab-131">脚本不能位于 CDN 上。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-131">Script can't be on CDN.</span></span>** <span data-ttu-id="7b7ab-132">服务工作者的 JavaScript 文件无法托管在 CDN (CDN) 上，它必须与页面位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-132">The JavaScript file for the service worker can't be hosted on a Content Distribution Network (CDN), it must be on the same domain as the page.</span></span> <span data-ttu-id="7b7ab-133">但是，如果需要，可以从 CDN 导入脚本。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-133">However, if you like, you can import scripts from your CDN.</span></span>

- **<span data-ttu-id="7b7ab-134">可以随时终止。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-134">Can be terminated any time.</span></span>** <span data-ttu-id="7b7ab-135">服务工作人员应短期工作，其生存时间与事件关联。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-135">Service workers are meant to be short-lived and their lifetime is tied to events.</span></span> <span data-ttu-id="7b7ab-136">特别是，服务工作者有一个时间限制，必须完成其事件处理程序的执行。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-136">In particular, service workers have a time limit in which they must finish executing their event handlers.</span></span> <span data-ttu-id="7b7ab-137">在其他情况下，浏览器或操作系统可能会选择终止影响电池、CPU 或内存消耗的服务工作者。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-137">In other cases, the browser or the operating system may choose to terminate a service worker that impacts the battery, CPU, or memory consumption.</span></span> <span data-ttu-id="7b7ab-138">在任一情况下，如果对正在处理的后续事件使用不同的服务工作实例，则避免依赖服务工作线程脚本中的全局变量。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-138">In either case, avoid relying on global variables in the service worker script in case a different service worker instance is used on a subsequent event that's being handled.</span></span>

- **<span data-ttu-id="7b7ab-139">仅允许异步请求。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-139">Only asynchronous requests allowed.</span></span>** <span data-ttu-id="7b7ab-140">此处不允许同步 XHR！</span><span class="sxs-lookup"><span data-stu-id="7b7ab-140">Synchronous XHR is not allowed here!</span></span> <span data-ttu-id="7b7ab-141">这两者都不是 localStorage，因此最好使用 IndexedDB 和前面介绍的新缓存 API。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-141">Neither is localStorage, so it's best to make use of IndexedDB and the new Caches API described earlier.</span></span>

- **<span data-ttu-id="7b7ab-142">服务工作线程范围为 1：1。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-142">Service worker to scope is 1:1.</span></span>** <span data-ttu-id="7b7ab-143">每个作用域只能有一个服务工作线程。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-143">You'll only be able to have one service worker per scope.</span></span> <span data-ttu-id="7b7ab-144">这意味着，如果您尝试为已具有服务工作器的范围注册其他服务工作器，则将会更新该服务工作线程。</span><span class="sxs-lookup"><span data-stu-id="7b7ab-144">That means if you try to register a different service worker for a scope that already has a service worker, that service worker will be updated.</span></span>
