---
description: 对页面域的引用。 与已检查页面相关的操作和事件属于页面域。
title: Page 域-DevTools 协议版本0.2 （EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 864515eefbcb809e280f2ab1d81015018272c398
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882840"
---
# <span data-ttu-id="42be5-104">Page 域-DevTools 协议版本0.2 （EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="42be5-104">Page Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="42be5-105">与已检查页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="42be5-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="42be5-106">方法</span><span class="sxs-lookup"><span data-stu-id="42be5-106">Methods</span></span>**](#methods) | <span data-ttu-id="42be5-107">[启用](#enable)、[禁用](#disable)、[导航](#navigate)、 [getFrameTree](#getframetree)</span><span class="sxs-lookup"><span data-stu-id="42be5-107">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span></span> |
| [**<span data-ttu-id="42be5-108">事件</span><span class="sxs-lookup"><span data-stu-id="42be5-108">Events</span></span>**](#events) | <span data-ttu-id="42be5-109">[frameAttached](#frameattached)、 [frameDetached](#framedetached)、 [frameNavigated](#framenavigated)、 [loadEventFired](#loadeventfired)、 [domContentEventFired](#domcontenteventfired)</span><span class="sxs-lookup"><span data-stu-id="42be5-109">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span></span> |
| [**<span data-ttu-id="42be5-110">类型</span><span class="sxs-lookup"><span data-stu-id="42be5-110">Types</span></span>**](#types) | <span data-ttu-id="42be5-111">[FrameId](#frameid)、 [Frame](#frame)、 [FrameTree](#frametree)</span><span class="sxs-lookup"><span data-stu-id="42be5-111">[FrameId](#frameid), [Frame](#frame), [FrameTree](#frametree)</span></span> |
## <span data-ttu-id="42be5-112">方法</span><span class="sxs-lookup"><span data-stu-id="42be5-112">Methods</span></span>

### <span data-ttu-id="42be5-113">“启用”</span><span class="sxs-lookup"><span data-stu-id="42be5-113">enable</span></span>
<span data-ttu-id="42be5-114">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="42be5-114">Enables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="42be5-115">“禁用”</span><span class="sxs-lookup"><span data-stu-id="42be5-115">disable</span></span>
<span data-ttu-id="42be5-116">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="42be5-116">Disables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="42be5-117">导航</span><span class="sxs-lookup"><span data-stu-id="42be5-117">navigate</span></span>
<span data-ttu-id="42be5-118">将当前页导航到给定的 URL。</span><span class="sxs-lookup"><span data-stu-id="42be5-118">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-119">参数</span><span class="sxs-lookup"><span data-stu-id="42be5-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-120">url</span><span class="sxs-lookup"><span data-stu-id="42be5-120">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="42be5-121">要将页面导航到的 URL。</span><span class="sxs-lookup"><span data-stu-id="42be5-121">URL to navigate the page to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-122">frameId</span><span class="sxs-lookup"><span data-stu-id="42be5-122">frameId</span></span> <br/> <i><span data-ttu-id="42be5-123">可选</span><span class="sxs-lookup"><span data-stu-id="42be5-123">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="42be5-124">要导航的帧 id。</span><span class="sxs-lookup"><span data-stu-id="42be5-124">Frame id to navigate.</span></span> <span data-ttu-id="42be5-125">如果未指定，将导航页首页。</span><span class="sxs-lookup"><span data-stu-id="42be5-125">If not specified, will navigate the top page.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-126">返回</span><span class="sxs-lookup"><span data-stu-id="42be5-126">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-127">frameId</span><span class="sxs-lookup"><span data-stu-id="42be5-127">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="42be5-128">将导航的帧 id。</span><span class="sxs-lookup"><span data-stu-id="42be5-128">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="42be5-129">getFrameTree</span><span class="sxs-lookup"><span data-stu-id="42be5-129">getFrameTree</span></span>
<span data-ttu-id="42be5-130">返回当前的帧树结构。</span><span class="sxs-lookup"><span data-stu-id="42be5-130">Returns present frame tree structure.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-131">返回</span><span class="sxs-lookup"><span data-stu-id="42be5-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-132">frameTree</span><span class="sxs-lookup"><span data-stu-id="42be5-132">frameTree</span></span></td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td><span data-ttu-id="42be5-133">显示帧树结构。</span><span class="sxs-lookup"><span data-stu-id="42be5-133">Present frame tree structure.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="42be5-134">事件</span><span class="sxs-lookup"><span data-stu-id="42be5-134">Events</span></span>

### <span data-ttu-id="42be5-135">frameAttached</span><span class="sxs-lookup"><span data-stu-id="42be5-135">frameAttached</span></span>
<span data-ttu-id="42be5-136">当 frame 已附加到其父项时激发。</span><span class="sxs-lookup"><span data-stu-id="42be5-136">Fired when frame has been attached to its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-137">参数</span><span class="sxs-lookup"><span data-stu-id="42be5-137">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-138">frameId</span><span class="sxs-lookup"><span data-stu-id="42be5-138">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="42be5-139">已附加的帧的 Id。</span><span class="sxs-lookup"><span data-stu-id="42be5-139">Id of the frame that has been attached.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-140">parentFrameId</span><span class="sxs-lookup"><span data-stu-id="42be5-140">parentFrameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="42be5-141">父框架标识符。</span><span class="sxs-lookup"><span data-stu-id="42be5-141">Parent frame identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-142">牌</span><span class="sxs-lookup"><span data-stu-id="42be5-142">stack</span></span> <br/> <i><span data-ttu-id="42be5-143">可选</span><span class="sxs-lookup"><span data-stu-id="42be5-143">optional</span></span></i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td><span data-ttu-id="42be5-144">JavaScript 堆栈跟踪（附加了 frame），仅在从脚本启动的帧时进行设置。</span><span class="sxs-lookup"><span data-stu-id="42be5-144">JavaScript stack trace of when frame was attached, only set if frame initiated from script.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="42be5-145">frameDetached</span><span class="sxs-lookup"><span data-stu-id="42be5-145">frameDetached</span></span>
<span data-ttu-id="42be5-146">当 frame 已从其父项分离时激发。</span><span class="sxs-lookup"><span data-stu-id="42be5-146">Fired when frame has been detached from its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-147">参数</span><span class="sxs-lookup"><span data-stu-id="42be5-147">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-148">frameId</span><span class="sxs-lookup"><span data-stu-id="42be5-148">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="42be5-149">已分离的帧的 Id。</span><span class="sxs-lookup"><span data-stu-id="42be5-149">Id of the frame that has been detached.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="42be5-150">frameNavigated</span><span class="sxs-lookup"><span data-stu-id="42be5-150">frameNavigated</span></span>
<span data-ttu-id="42be5-151">在帧导航完成后激发。</span><span class="sxs-lookup"><span data-stu-id="42be5-151">Fired once navigation of the frame has completed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-152">参数</span><span class="sxs-lookup"><span data-stu-id="42be5-152">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-153">帧</span><span class="sxs-lookup"><span data-stu-id="42be5-153">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="42be5-154">Frame 对象。</span><span class="sxs-lookup"><span data-stu-id="42be5-154">Frame object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="42be5-155">loadEventFired</span><span class="sxs-lookup"><span data-stu-id="42be5-155">loadEventFired</span></span>
<span data-ttu-id="42be5-156">对应于 window onload 事件。</span><span class="sxs-lookup"><span data-stu-id="42be5-156">Corresponds to the window.onload event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-157">参数</span><span class="sxs-lookup"><span data-stu-id="42be5-157">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-158">icmp</span><span class="sxs-lookup"><span data-stu-id="42be5-158">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="42be5-159">自 epoch 以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="42be5-159">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="42be5-160">domContentEventFired</span><span class="sxs-lookup"><span data-stu-id="42be5-160">domContentEventFired</span></span>
<span data-ttu-id="42be5-161">对应于 onDOMContentLoaded 事件。</span><span class="sxs-lookup"><span data-stu-id="42be5-161">Corresponds to the document.onDOMContentLoaded event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-162">参数</span><span class="sxs-lookup"><span data-stu-id="42be5-162">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-163">icmp</span><span class="sxs-lookup"><span data-stu-id="42be5-163">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="42be5-164">自 epoch 以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="42be5-164">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="42be5-165">类型</span><span class="sxs-lookup"><span data-stu-id="42be5-165">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="42be5-166">FrameId</span><span class="sxs-lookup"><span data-stu-id="42be5-166">FrameId</span></span> `string`

<span data-ttu-id="42be5-167">唯一的帧标识符。</span><span class="sxs-lookup"><span data-stu-id="42be5-167">Unique frame identifier.</span></span>

</p>

---

### <a name="frame"></a> <span data-ttu-id="42be5-168">帧</span><span class="sxs-lookup"><span data-stu-id="42be5-168">Frame</span></span> `object`

<span data-ttu-id="42be5-169">有关页面上的框架的信息。</span><span class="sxs-lookup"><span data-stu-id="42be5-169">Information about the Frame on the Page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-170">属性</span><span class="sxs-lookup"><span data-stu-id="42be5-170">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-171">id</span><span class="sxs-lookup"><span data-stu-id="42be5-171">id</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="42be5-172">Frame 唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="42be5-172">Frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-173">parentId</span><span class="sxs-lookup"><span data-stu-id="42be5-173">parentId</span></span> <br/> <i><span data-ttu-id="42be5-174">可选</span><span class="sxs-lookup"><span data-stu-id="42be5-174">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="42be5-175">父框架唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="42be5-175">Parent frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-176">name</span><span class="sxs-lookup"><span data-stu-id="42be5-176">name</span></span> <br/> <i><span data-ttu-id="42be5-177">可选</span><span class="sxs-lookup"><span data-stu-id="42be5-177">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="42be5-178">在标记中指定的帧的名称。</span><span class="sxs-lookup"><span data-stu-id="42be5-178">Frame's name as specified in the tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-179">url</span><span class="sxs-lookup"><span data-stu-id="42be5-179">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="42be5-180">框架文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="42be5-180">Frame document's URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-181">securityOrigin</span><span class="sxs-lookup"><span data-stu-id="42be5-181">securityOrigin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="42be5-182">框架文档的安全来源。</span><span class="sxs-lookup"><span data-stu-id="42be5-182">Frame document's security origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-183">mimeType</span><span class="sxs-lookup"><span data-stu-id="42be5-183">mimeType</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="42be5-184">由浏览器确定的框架文档的 mimeType。</span><span class="sxs-lookup"><span data-stu-id="42be5-184">Frame document's mimeType as determined by the browser.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> <span data-ttu-id="42be5-185">FrameTree</span><span class="sxs-lookup"><span data-stu-id="42be5-185">FrameTree</span></span> `object`

<span data-ttu-id="42be5-186">有关帧层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="42be5-186">Information about the Frame hierarchy.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="42be5-187">属性</span><span class="sxs-lookup"><span data-stu-id="42be5-187">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="42be5-188">帧</span><span class="sxs-lookup"><span data-stu-id="42be5-188">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="42be5-189">此树项目的帧信息。</span><span class="sxs-lookup"><span data-stu-id="42be5-189">Frame information for this tree item.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="42be5-190">childFrames</span><span class="sxs-lookup"><span data-stu-id="42be5-190">childFrames</span></span> <br/> <i><span data-ttu-id="42be5-191">可选</span><span class="sxs-lookup"><span data-stu-id="42be5-191">optional</span></span></i></td>
            <td><a href="#frametree"><code class="flyout">FrameTree[]</code></a></td>
            <td><span data-ttu-id="42be5-192">子框架。</span><span class="sxs-lookup"><span data-stu-id="42be5-192">Child frames.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
