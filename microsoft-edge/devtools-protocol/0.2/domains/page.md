---
description: 对页面域的引用。 与已检查页面相关的操作和事件属于页面域。
title: Page Domain-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 688cc1fcfce0b81c5eed0c858a4a60b4754c49a4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563400"
---
# <span data-ttu-id="99302-104">页面</span><span class="sxs-lookup"><span data-stu-id="99302-104">Page</span></span>
<span data-ttu-id="99302-105">与已检查页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="99302-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="99302-106">方法</span><span class="sxs-lookup"><span data-stu-id="99302-106">Methods</span></span>**](#methods) | <span data-ttu-id="99302-107">[启用](#enable)、[禁用](#disable)、[导航](#navigate)、 [getFrameTree](#getframetree)</span><span class="sxs-lookup"><span data-stu-id="99302-107">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span></span> |
| [**<span data-ttu-id="99302-108">事件</span><span class="sxs-lookup"><span data-stu-id="99302-108">Events</span></span>**](#events) | <span data-ttu-id="99302-109">[frameAttached](#frameattached)、 [frameDetached](#framedetached)、 [frameNavigated](#framenavigated)、 [loadEventFired](#loadeventfired)、 [domContentEventFired](#domcontenteventfired)</span><span class="sxs-lookup"><span data-stu-id="99302-109">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span></span> |
| [**<span data-ttu-id="99302-110">类型</span><span class="sxs-lookup"><span data-stu-id="99302-110">Types</span></span>**](#types) | <span data-ttu-id="99302-111">[FrameId](#frameid)、 [Frame](#frame)、 [FrameTree](#frametree)</span><span class="sxs-lookup"><span data-stu-id="99302-111">[FrameId](#frameid), [Frame](#frame), [FrameTree](#frametree)</span></span> |
## <span data-ttu-id="99302-112">方法</span><span class="sxs-lookup"><span data-stu-id="99302-112">Methods</span></span>

### <span data-ttu-id="99302-113">“启用”</span><span class="sxs-lookup"><span data-stu-id="99302-113">enable</span></span>
<span data-ttu-id="99302-114">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="99302-114">Enables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="99302-115">“禁用”</span><span class="sxs-lookup"><span data-stu-id="99302-115">disable</span></span>
<span data-ttu-id="99302-116">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="99302-116">Disables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="99302-117">导航</span><span class="sxs-lookup"><span data-stu-id="99302-117">navigate</span></span>
<span data-ttu-id="99302-118">将当前页导航到给定的 URL。</span><span class="sxs-lookup"><span data-stu-id="99302-118">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-119">参数</span><span class="sxs-lookup"><span data-stu-id="99302-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-120">url</span><span class="sxs-lookup"><span data-stu-id="99302-120">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="99302-121">要将页面导航到的 URL。</span><span class="sxs-lookup"><span data-stu-id="99302-121">URL to navigate the page to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-122">frameId</span><span class="sxs-lookup"><span data-stu-id="99302-122">frameId</span></span> <br/> <i><span data-ttu-id="99302-123">可选</span><span class="sxs-lookup"><span data-stu-id="99302-123">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="99302-124">要导航的帧 id。</span><span class="sxs-lookup"><span data-stu-id="99302-124">Frame id to navigate.</span></span> <span data-ttu-id="99302-125">如果未指定，将导航页首页。</span><span class="sxs-lookup"><span data-stu-id="99302-125">If not specified, will navigate the top page.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-126">返回</span><span class="sxs-lookup"><span data-stu-id="99302-126">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-127">frameId</span><span class="sxs-lookup"><span data-stu-id="99302-127">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="99302-128">将导航的帧 id。</span><span class="sxs-lookup"><span data-stu-id="99302-128">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="99302-129">getFrameTree</span><span class="sxs-lookup"><span data-stu-id="99302-129">getFrameTree</span></span>
<span data-ttu-id="99302-130">返回当前的帧树结构。</span><span class="sxs-lookup"><span data-stu-id="99302-130">Returns present frame tree structure.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-131">返回</span><span class="sxs-lookup"><span data-stu-id="99302-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-132">frameTree</span><span class="sxs-lookup"><span data-stu-id="99302-132">frameTree</span></span></td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td><span data-ttu-id="99302-133">显示帧树结构。</span><span class="sxs-lookup"><span data-stu-id="99302-133">Present frame tree structure.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="99302-134">事件</span><span class="sxs-lookup"><span data-stu-id="99302-134">Events</span></span>

### <span data-ttu-id="99302-135">frameAttached</span><span class="sxs-lookup"><span data-stu-id="99302-135">frameAttached</span></span>
<span data-ttu-id="99302-136">当 frame 已附加到其父项时激发。</span><span class="sxs-lookup"><span data-stu-id="99302-136">Fired when frame has been attached to its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-137">参数</span><span class="sxs-lookup"><span data-stu-id="99302-137">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-138">frameId</span><span class="sxs-lookup"><span data-stu-id="99302-138">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="99302-139">已附加的帧的 Id。</span><span class="sxs-lookup"><span data-stu-id="99302-139">Id of the frame that has been attached.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-140">parentFrameId</span><span class="sxs-lookup"><span data-stu-id="99302-140">parentFrameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="99302-141">父框架标识符。</span><span class="sxs-lookup"><span data-stu-id="99302-141">Parent frame identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-142">牌</span><span class="sxs-lookup"><span data-stu-id="99302-142">stack</span></span> <br/> <i><span data-ttu-id="99302-143">可选</span><span class="sxs-lookup"><span data-stu-id="99302-143">optional</span></span></i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td><span data-ttu-id="99302-144">JavaScript 堆栈跟踪（附加了 frame），仅在从脚本启动的帧时进行设置。</span><span class="sxs-lookup"><span data-stu-id="99302-144">JavaScript stack trace of when frame was attached, only set if frame initiated from script.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="99302-145">frameDetached</span><span class="sxs-lookup"><span data-stu-id="99302-145">frameDetached</span></span>
<span data-ttu-id="99302-146">当 frame 已从其父项分离时激发。</span><span class="sxs-lookup"><span data-stu-id="99302-146">Fired when frame has been detached from its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-147">参数</span><span class="sxs-lookup"><span data-stu-id="99302-147">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-148">frameId</span><span class="sxs-lookup"><span data-stu-id="99302-148">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="99302-149">已分离的帧的 Id。</span><span class="sxs-lookup"><span data-stu-id="99302-149">Id of the frame that has been detached.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="99302-150">frameNavigated</span><span class="sxs-lookup"><span data-stu-id="99302-150">frameNavigated</span></span>
<span data-ttu-id="99302-151">在帧导航完成后激发。</span><span class="sxs-lookup"><span data-stu-id="99302-151">Fired once navigation of the frame has completed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-152">参数</span><span class="sxs-lookup"><span data-stu-id="99302-152">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-153">帧</span><span class="sxs-lookup"><span data-stu-id="99302-153">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="99302-154">Frame 对象。</span><span class="sxs-lookup"><span data-stu-id="99302-154">Frame object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="99302-155">loadEventFired</span><span class="sxs-lookup"><span data-stu-id="99302-155">loadEventFired</span></span>
<span data-ttu-id="99302-156">对应于 window onload 事件。</span><span class="sxs-lookup"><span data-stu-id="99302-156">Corresponds to the window.onload event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-157">参数</span><span class="sxs-lookup"><span data-stu-id="99302-157">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-158">icmp</span><span class="sxs-lookup"><span data-stu-id="99302-158">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="99302-159">自 epoch 以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="99302-159">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="99302-160">domContentEventFired</span><span class="sxs-lookup"><span data-stu-id="99302-160">domContentEventFired</span></span>
<span data-ttu-id="99302-161">对应于 onDOMContentLoaded 事件。</span><span class="sxs-lookup"><span data-stu-id="99302-161">Corresponds to the document.onDOMContentLoaded event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-162">参数</span><span class="sxs-lookup"><span data-stu-id="99302-162">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-163">icmp</span><span class="sxs-lookup"><span data-stu-id="99302-163">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="99302-164">自 epoch 以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="99302-164">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="99302-165">类型</span><span class="sxs-lookup"><span data-stu-id="99302-165">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="99302-166">FrameId</span><span class="sxs-lookup"><span data-stu-id="99302-166">FrameId</span></span> `string`

<span data-ttu-id="99302-167">唯一的帧标识符。</span><span class="sxs-lookup"><span data-stu-id="99302-167">Unique frame identifier.</span></span>

</p>

---

### <a name="frame"></a> <span data-ttu-id="99302-168">帧</span><span class="sxs-lookup"><span data-stu-id="99302-168">Frame</span></span> `object`

<span data-ttu-id="99302-169">有关页面上的框架的信息。</span><span class="sxs-lookup"><span data-stu-id="99302-169">Information about the Frame on the Page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-170">属性</span><span class="sxs-lookup"><span data-stu-id="99302-170">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-171">id</span><span class="sxs-lookup"><span data-stu-id="99302-171">id</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="99302-172">Frame 唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="99302-172">Frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-173">parentId</span><span class="sxs-lookup"><span data-stu-id="99302-173">parentId</span></span> <br/> <i><span data-ttu-id="99302-174">可选</span><span class="sxs-lookup"><span data-stu-id="99302-174">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="99302-175">父框架唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="99302-175">Parent frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-176">name</span><span class="sxs-lookup"><span data-stu-id="99302-176">name</span></span> <br/> <i><span data-ttu-id="99302-177">可选</span><span class="sxs-lookup"><span data-stu-id="99302-177">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="99302-178">在标记中指定的帧的名称。</span><span class="sxs-lookup"><span data-stu-id="99302-178">Frame's name as specified in the tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-179">url</span><span class="sxs-lookup"><span data-stu-id="99302-179">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="99302-180">框架文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="99302-180">Frame document's URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-181">securityOrigin</span><span class="sxs-lookup"><span data-stu-id="99302-181">securityOrigin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="99302-182">框架文档的安全来源。</span><span class="sxs-lookup"><span data-stu-id="99302-182">Frame document's security origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-183">mimeType</span><span class="sxs-lookup"><span data-stu-id="99302-183">mimeType</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="99302-184">由浏览器确定的框架文档的 mimeType。</span><span class="sxs-lookup"><span data-stu-id="99302-184">Frame document's mimeType as determined by the browser.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> <span data-ttu-id="99302-185">FrameTree</span><span class="sxs-lookup"><span data-stu-id="99302-185">FrameTree</span></span> `object`

<span data-ttu-id="99302-186">有关帧层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="99302-186">Information about the Frame hierarchy.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="99302-187">属性</span><span class="sxs-lookup"><span data-stu-id="99302-187">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="99302-188">帧</span><span class="sxs-lookup"><span data-stu-id="99302-188">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="99302-189">此树项目的帧信息。</span><span class="sxs-lookup"><span data-stu-id="99302-189">Frame information for this tree item.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="99302-190">childFrames</span><span class="sxs-lookup"><span data-stu-id="99302-190">childFrames</span></span> <br/> <i><span data-ttu-id="99302-191">可选</span><span class="sxs-lookup"><span data-stu-id="99302-191">optional</span></span></i></td>
            <td><a href="#frametree"><code class="flyout">FrameTree[]</code></a></td>
            <td><span data-ttu-id="99302-192">子框架。</span><span class="sxs-lookup"><span data-stu-id="99302-192">Child frames.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
