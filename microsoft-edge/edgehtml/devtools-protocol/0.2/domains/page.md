---
description: DevTools 协议版本 0.2 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2f1849a2e2aa2f53cef9dff5d03ac991d368a6f3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232083"
---
# <span data-ttu-id="937bf-104">页面域 - DevTools 协议版本 0.2 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="937bf-104">Page Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="937bf-105">与检查的页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="937bf-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="937bf-106">方法</span><span class="sxs-lookup"><span data-stu-id="937bf-106">Methods</span></span>**](#methods) | <span data-ttu-id="937bf-107">[启用](#enable)， [禁用](#disable)， [导航](#navigate)， [getFrameTree](#getframetree)</span><span class="sxs-lookup"><span data-stu-id="937bf-107">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span></span> |
| [**<span data-ttu-id="937bf-108">事件</span><span class="sxs-lookup"><span data-stu-id="937bf-108">Events</span></span>**](#events) | <span data-ttu-id="937bf-109">[frameAttached](#frameattached)， [frameDetached](#framedetached)， [frameNavigated](#framenavigated)， [loadEventFired](#loadeventfired)， [domContentEventFired](#domcontenteventfired)</span><span class="sxs-lookup"><span data-stu-id="937bf-109">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span></span> |
| [**<span data-ttu-id="937bf-110">类型</span><span class="sxs-lookup"><span data-stu-id="937bf-110">Types</span></span>**](#types) | <span data-ttu-id="937bf-111">[FrameId](#frameid)， [Frame](#frame)， [FrameTree](#frametree)</span><span class="sxs-lookup"><span data-stu-id="937bf-111">[FrameId](#frameid), [Frame](#frame), [FrameTree](#frametree)</span></span> |
## <span data-ttu-id="937bf-112">方法</span><span class="sxs-lookup"><span data-stu-id="937bf-112">Methods</span></span>

### <span data-ttu-id="937bf-113">“启用”</span><span class="sxs-lookup"><span data-stu-id="937bf-113">enable</span></span>
<span data-ttu-id="937bf-114">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="937bf-114">Enables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="937bf-115">“禁用”</span><span class="sxs-lookup"><span data-stu-id="937bf-115">disable</span></span>
<span data-ttu-id="937bf-116">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="937bf-116">Disables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="937bf-117">导航</span><span class="sxs-lookup"><span data-stu-id="937bf-117">navigate</span></span>
<span data-ttu-id="937bf-118">将当前页面导航到给定 URL。</span><span class="sxs-lookup"><span data-stu-id="937bf-118">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-119">参数</span><span class="sxs-lookup"><span data-stu-id="937bf-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-120">url</span><span class="sxs-lookup"><span data-stu-id="937bf-120">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="937bf-121">导航到页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="937bf-121">URL to navigate the page to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-122">frameId</span><span class="sxs-lookup"><span data-stu-id="937bf-122">frameId</span></span> <br/> <i><span data-ttu-id="937bf-123">可选</span><span class="sxs-lookup"><span data-stu-id="937bf-123">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="937bf-124">要导航的框架 ID。</span><span class="sxs-lookup"><span data-stu-id="937bf-124">Frame id to navigate.</span></span> <span data-ttu-id="937bf-125">如果未指定，将导航到顶部页面。</span><span class="sxs-lookup"><span data-stu-id="937bf-125">If not specified, will navigate the top page.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-126">返回</span><span class="sxs-lookup"><span data-stu-id="937bf-126">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-127">frameId</span><span class="sxs-lookup"><span data-stu-id="937bf-127">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="937bf-128">将导航的框架 ID。</span><span class="sxs-lookup"><span data-stu-id="937bf-128">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="937bf-129">getFrameTree</span><span class="sxs-lookup"><span data-stu-id="937bf-129">getFrameTree</span></span>
<span data-ttu-id="937bf-130">返回当前框架树结构。</span><span class="sxs-lookup"><span data-stu-id="937bf-130">Returns present frame tree structure.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-131">返回</span><span class="sxs-lookup"><span data-stu-id="937bf-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-132">frameTree</span><span class="sxs-lookup"><span data-stu-id="937bf-132">frameTree</span></span></td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td><span data-ttu-id="937bf-133">显示框架树结构。</span><span class="sxs-lookup"><span data-stu-id="937bf-133">Present frame tree structure.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="937bf-134">事件</span><span class="sxs-lookup"><span data-stu-id="937bf-134">Events</span></span>

### <span data-ttu-id="937bf-135">frameAttached</span><span class="sxs-lookup"><span data-stu-id="937bf-135">frameAttached</span></span>
<span data-ttu-id="937bf-136">当框架已连接到其父级时触发。</span><span class="sxs-lookup"><span data-stu-id="937bf-136">Fired when frame has been attached to its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-137">参数</span><span class="sxs-lookup"><span data-stu-id="937bf-137">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-138">frameId</span><span class="sxs-lookup"><span data-stu-id="937bf-138">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="937bf-139">已附加的帧的 ID。</span><span class="sxs-lookup"><span data-stu-id="937bf-139">Id of the frame that has been attached.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-140">parentFrameId</span><span class="sxs-lookup"><span data-stu-id="937bf-140">parentFrameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="937bf-141">父框架标识符。</span><span class="sxs-lookup"><span data-stu-id="937bf-141">Parent frame identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-142">stack</span><span class="sxs-lookup"><span data-stu-id="937bf-142">stack</span></span> <br/> <i><span data-ttu-id="937bf-143">可选</span><span class="sxs-lookup"><span data-stu-id="937bf-143">optional</span></span></i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td><span data-ttu-id="937bf-144">框架的附加时间 JavaScript 堆栈跟踪，仅在框架从脚本启动时设置。</span><span class="sxs-lookup"><span data-stu-id="937bf-144">JavaScript stack trace of when frame was attached, only set if frame initiated from script.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="937bf-145">frameDetached</span><span class="sxs-lookup"><span data-stu-id="937bf-145">frameDetached</span></span>
<span data-ttu-id="937bf-146">当框架与父级分离时触发。</span><span class="sxs-lookup"><span data-stu-id="937bf-146">Fired when frame has been detached from its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-147">参数</span><span class="sxs-lookup"><span data-stu-id="937bf-147">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-148">frameId</span><span class="sxs-lookup"><span data-stu-id="937bf-148">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="937bf-149">已分离的帧的 ID。</span><span class="sxs-lookup"><span data-stu-id="937bf-149">Id of the frame that has been detached.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="937bf-150">frameNavigated</span><span class="sxs-lookup"><span data-stu-id="937bf-150">frameNavigated</span></span>
<span data-ttu-id="937bf-151">帧导航完成后触发。</span><span class="sxs-lookup"><span data-stu-id="937bf-151">Fired once navigation of the frame has completed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-152">参数</span><span class="sxs-lookup"><span data-stu-id="937bf-152">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-153">frame</span><span class="sxs-lookup"><span data-stu-id="937bf-153">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="937bf-154">Frame 对象。</span><span class="sxs-lookup"><span data-stu-id="937bf-154">Frame object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="937bf-155">loadEventFired</span><span class="sxs-lookup"><span data-stu-id="937bf-155">loadEventFired</span></span>
<span data-ttu-id="937bf-156">对应于 window.onload 事件。</span><span class="sxs-lookup"><span data-stu-id="937bf-156">Corresponds to the window.onload event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-157">参数</span><span class="sxs-lookup"><span data-stu-id="937bf-157">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-158">timestamp</span><span class="sxs-lookup"><span data-stu-id="937bf-158">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="937bf-159">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="937bf-159">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="937bf-160">domContentEventFired</span><span class="sxs-lookup"><span data-stu-id="937bf-160">domContentEventFired</span></span>
<span data-ttu-id="937bf-161">对应于 document.onDOMContentLoaded 事件。</span><span class="sxs-lookup"><span data-stu-id="937bf-161">Corresponds to the document.onDOMContentLoaded event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-162">参数</span><span class="sxs-lookup"><span data-stu-id="937bf-162">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-163">timestamp</span><span class="sxs-lookup"><span data-stu-id="937bf-163">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="937bf-164">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="937bf-164">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="937bf-165">类型</span><span class="sxs-lookup"><span data-stu-id="937bf-165">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="937bf-166">FrameId</span><span class="sxs-lookup"><span data-stu-id="937bf-166">FrameId</span></span> `string`

<span data-ttu-id="937bf-167">唯一帧标识符。</span><span class="sxs-lookup"><span data-stu-id="937bf-167">Unique frame identifier.</span></span>

</p>

---

### <a name="frame"></a> <span data-ttu-id="937bf-168">帧</span><span class="sxs-lookup"><span data-stu-id="937bf-168">Frame</span></span> `object`

<span data-ttu-id="937bf-169">有关页面上框架的信息。</span><span class="sxs-lookup"><span data-stu-id="937bf-169">Information about the Frame on the Page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-170">属性</span><span class="sxs-lookup"><span data-stu-id="937bf-170">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-171">id</span><span class="sxs-lookup"><span data-stu-id="937bf-171">id</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="937bf-172">帧唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="937bf-172">Frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-173">parentId</span><span class="sxs-lookup"><span data-stu-id="937bf-173">parentId</span></span> <br/> <i><span data-ttu-id="937bf-174">可选</span><span class="sxs-lookup"><span data-stu-id="937bf-174">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="937bf-175">父框架唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="937bf-175">Parent frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-176">name</span><span class="sxs-lookup"><span data-stu-id="937bf-176">name</span></span> <br/> <i><span data-ttu-id="937bf-177">可选</span><span class="sxs-lookup"><span data-stu-id="937bf-177">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="937bf-178">标记中指定的框架名称。</span><span class="sxs-lookup"><span data-stu-id="937bf-178">Frame's name as specified in the tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-179">url</span><span class="sxs-lookup"><span data-stu-id="937bf-179">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="937bf-180">框架文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="937bf-180">Frame document's URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-181">securityOrigin</span><span class="sxs-lookup"><span data-stu-id="937bf-181">securityOrigin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="937bf-182">框架文档的安全来源。</span><span class="sxs-lookup"><span data-stu-id="937bf-182">Frame document's security origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-183">mimeType</span><span class="sxs-lookup"><span data-stu-id="937bf-183">mimeType</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="937bf-184">框架文档的 mimeType，由浏览器确定。</span><span class="sxs-lookup"><span data-stu-id="937bf-184">Frame document's mimeType as determined by the browser.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> <span data-ttu-id="937bf-185">FrameTree</span><span class="sxs-lookup"><span data-stu-id="937bf-185">FrameTree</span></span> `object`

<span data-ttu-id="937bf-186">有关 Frame 层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="937bf-186">Information about the Frame hierarchy.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="937bf-187">属性</span><span class="sxs-lookup"><span data-stu-id="937bf-187">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="937bf-188">frame</span><span class="sxs-lookup"><span data-stu-id="937bf-188">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="937bf-189">此树项的框架信息。</span><span class="sxs-lookup"><span data-stu-id="937bf-189">Frame information for this tree item.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="937bf-190">childFrames</span><span class="sxs-lookup"><span data-stu-id="937bf-190">childFrames</span></span> <br/> <i><span data-ttu-id="937bf-191">可选</span><span class="sxs-lookup"><span data-stu-id="937bf-191">optional</span></span></i></td>
            <td><a href="#frametree"><code class="flyout">FrameTree[]</code></a></td>
            <td><span data-ttu-id="937bf-192">子框架。</span><span class="sxs-lookup"><span data-stu-id="937bf-192">Child frames.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
