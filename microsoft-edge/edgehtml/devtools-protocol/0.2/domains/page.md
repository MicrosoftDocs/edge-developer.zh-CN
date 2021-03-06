---
description: DevTools 协议版本 0.2 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d969dd100164ace61445a4618174cfa943dcfd2b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398845"
---
# <a name="page-domain---devtools-protocol-version-02-edgehtml"></a><span data-ttu-id="b4a33-104">页面域 - DevTools 协议版本 0.2 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="b4a33-104">Page Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="b4a33-105">与检查的页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="b4a33-105">Actions and events related to the inspected page belong to the page domain.</span></span>  

| <span data-ttu-id="b4a33-106">分类</span><span class="sxs-lookup"><span data-stu-id="b4a33-106">Classification</span></span> | <span data-ttu-id="b4a33-107">成员</span><span class="sxs-lookup"><span data-stu-id="b4a33-107">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="b4a33-108">方法</span><span class="sxs-lookup"><span data-stu-id="b4a33-108">Methods</span></span>](#methods) | <span data-ttu-id="b4a33-109">[enable](#enable)， [disable](#disable)， [navigate](#navigate)， [getFrameTree](#getframetree)</span><span class="sxs-lookup"><span data-stu-id="b4a33-109">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span></span> |  
| [<span data-ttu-id="b4a33-110">事件</span><span class="sxs-lookup"><span data-stu-id="b4a33-110">Events</span></span>](#events) | <span data-ttu-id="b4a33-111">[frameAttached](#frameattached)， [frameDetached](#framedetached)， [frameNavigated](#framenavigated)， [loadEventFired](#loadeventfired)， [domContentEventFired](#domcontenteventfired)</span><span class="sxs-lookup"><span data-stu-id="b4a33-111">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span></span> |  
| [<span data-ttu-id="b4a33-112">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-112">Types</span></span>](#types) | <span data-ttu-id="b4a33-113">[FrameId](#frameid)、 [Frame](#frame)、 [FrameTree](#frametree)</span><span class="sxs-lookup"><span data-stu-id="b4a33-113">[FrameId](#frameid), [Frame](#frame), [FrameTree](#frametree)</span></span> |  

## <a name="methods"></a><span data-ttu-id="b4a33-114">方法</span><span class="sxs-lookup"><span data-stu-id="b4a33-114">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="b4a33-115">“启用”</span><span class="sxs-lookup"><span data-stu-id="b4a33-115">enable</span></span>  

<span data-ttu-id="b4a33-116">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="b4a33-116">Enables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="b4a33-117">“禁用”</span><span class="sxs-lookup"><span data-stu-id="b4a33-117">disable</span></span>  

<span data-ttu-id="b4a33-118">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="b4a33-118">Disables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="navigate"></a><span data-ttu-id="b4a33-119">导航</span><span class="sxs-lookup"><span data-stu-id="b4a33-119">navigate</span></span>  

<span data-ttu-id="b4a33-120">将当前页面导航到给定 URL。</span><span class="sxs-lookup"><span data-stu-id="b4a33-120">Navigates current page to the given URL.</span></span>  

| <span data-ttu-id="b4a33-121">参数</span><span class="sxs-lookup"><span data-stu-id="b4a33-121">Parameters</span></span> | <span data-ttu-id="b4a33-122">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-122">Type</span></span> | <span data-ttu-id="b4a33-123">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-123">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-124">url</span><span class="sxs-lookup"><span data-stu-id="b4a33-124">url</span></span> | `string` | <span data-ttu-id="b4a33-125">导航到页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="b4a33-125">URL to navigate the page to.</span></span> |  
| <span data-ttu-id="b4a33-126">frameId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="b4a33-126">frameId \(optional\)</span></span> | [<span data-ttu-id="b4a33-127">FrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-127">FrameId</span></span>](#frameid) | <span data-ttu-id="b4a33-128">要导航的框架 ID。</span><span class="sxs-lookup"><span data-stu-id="b4a33-128">Frame id to navigate.</span></span>  <span data-ttu-id="b4a33-129">如果未指定，将导航顶部页面。</span><span class="sxs-lookup"><span data-stu-id="b4a33-129">If not specified, will navigate the top page.</span></span> |  

| <span data-ttu-id="b4a33-130">返回</span><span class="sxs-lookup"><span data-stu-id="b4a33-130">Returns</span></span> | <span data-ttu-id="b4a33-131">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-131">Type</span></span> | <span data-ttu-id="b4a33-132">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-132">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-133">frameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-133">frameId</span></span> | [<span data-ttu-id="b4a33-134">FrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-134">FrameId</span></span>](#frameid) | <span data-ttu-id="b4a33-135">将导航的帧 ID。</span><span class="sxs-lookup"><span data-stu-id="b4a33-135">Frame id that will be navigated.</span></span> |  

---  

### <a name="getframetree"></a><span data-ttu-id="b4a33-136">getFrameTree</span><span class="sxs-lookup"><span data-stu-id="b4a33-136">getFrameTree</span></span>  

<span data-ttu-id="b4a33-137">返回当前框架树结构。</span><span class="sxs-lookup"><span data-stu-id="b4a33-137">Returns present frame tree structure.</span></span>  

| <span data-ttu-id="b4a33-138">返回</span><span class="sxs-lookup"><span data-stu-id="b4a33-138">Returns</span></span> | <span data-ttu-id="b4a33-139">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-139">Type</span></span> | <span data-ttu-id="b4a33-140">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-140">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-141">frameTree</span><span class="sxs-lookup"><span data-stu-id="b4a33-141">frameTree</span></span> | [<span data-ttu-id="b4a33-142">FrameTree</span><span class="sxs-lookup"><span data-stu-id="b4a33-142">FrameTree</span></span>](#frametree) | <span data-ttu-id="b4a33-143">显示框架树结构。</span><span class="sxs-lookup"><span data-stu-id="b4a33-143">Present frame tree structure.</span></span> |  

---  

## <a name="events"></a><span data-ttu-id="b4a33-144">事件</span><span class="sxs-lookup"><span data-stu-id="b4a33-144">Events</span></span>  

### <a name="frameattached"></a><span data-ttu-id="b4a33-145">frameAttached</span><span class="sxs-lookup"><span data-stu-id="b4a33-145">frameAttached</span></span>  

<span data-ttu-id="b4a33-146">当框架已连接到其父级时触发。</span><span class="sxs-lookup"><span data-stu-id="b4a33-146">Fired when frame has been attached to its parent.</span></span>  

| <span data-ttu-id="b4a33-147">参数</span><span class="sxs-lookup"><span data-stu-id="b4a33-147">Parameters</span></span> | <span data-ttu-id="b4a33-148">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-148">Type</span></span> | <span data-ttu-id="b4a33-149">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-149">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-150">frameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-150">frameId</span></span> | [<span data-ttu-id="b4a33-151">FrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-151">FrameId</span></span>](#frameid) | <span data-ttu-id="b4a33-152">已附加的帧的 ID。</span><span class="sxs-lookup"><span data-stu-id="b4a33-152">Id of the frame that has been attached.</span></span> |  
| <span data-ttu-id="b4a33-153">parentFrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-153">parentFrameId</span></span> | [<span data-ttu-id="b4a33-154">FrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-154">FrameId</span></span>](#frameid) | <span data-ttu-id="b4a33-155">父帧标识符。</span><span class="sxs-lookup"><span data-stu-id="b4a33-155">Parent frame identifier.</span></span> |  
| <span data-ttu-id="b4a33-156">stack \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="b4a33-156">stack \(optional\)</span></span> | [<span data-ttu-id="b4a33-157">Runtime.StackTrace</span><span class="sxs-lookup"><span data-stu-id="b4a33-157">Runtime.StackTrace</span></span>](./runtime.md#stacktrace) | <span data-ttu-id="b4a33-158">框架的附加时间 JavaScript 堆栈跟踪，仅在框架从脚本启动时设置。</span><span class="sxs-lookup"><span data-stu-id="b4a33-158">JavaScript stack trace of when frame was attached, only set if frame initiated from script.</span></span> |  

---  

### <a name="framedetached"></a><span data-ttu-id="b4a33-159">frameDetached</span><span class="sxs-lookup"><span data-stu-id="b4a33-159">frameDetached</span></span>  

<span data-ttu-id="b4a33-160">当框架与父级分离时触发。</span><span class="sxs-lookup"><span data-stu-id="b4a33-160">Fired when frame has been detached from its parent.</span></span>  

| <span data-ttu-id="b4a33-161">参数</span><span class="sxs-lookup"><span data-stu-id="b4a33-161">Parameters</span></span> | <span data-ttu-id="b4a33-162">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-162">Type</span></span> | <span data-ttu-id="b4a33-163">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-163">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-164">frameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-164">frameId</span></span> | [<span data-ttu-id="b4a33-165">FrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-165">FrameId</span></span>](#frameid) | <span data-ttu-id="b4a33-166">已分离的帧的 ID。</span><span class="sxs-lookup"><span data-stu-id="b4a33-166">ID of the frame that has been detached.</span></span> |  

---  

### <a name="framenavigated"></a><span data-ttu-id="b4a33-167">frameNavigated</span><span class="sxs-lookup"><span data-stu-id="b4a33-167">frameNavigated</span></span>  

<span data-ttu-id="b4a33-168">帧导航完成后触发。</span><span class="sxs-lookup"><span data-stu-id="b4a33-168">Fired once navigation of the frame has completed.</span></span>  

| <span data-ttu-id="b4a33-169">参数</span><span class="sxs-lookup"><span data-stu-id="b4a33-169">Parameters</span></span> | <span data-ttu-id="b4a33-170">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-170">Type</span></span> | <span data-ttu-id="b4a33-171">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-171">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-172">frame</span><span class="sxs-lookup"><span data-stu-id="b4a33-172">frame</span></span> | [<span data-ttu-id="b4a33-173">帧</span><span class="sxs-lookup"><span data-stu-id="b4a33-173">Frame</span></span>](#frame) | <span data-ttu-id="b4a33-174">Frame 对象。</span><span class="sxs-lookup"><span data-stu-id="b4a33-174">Frame object.</span></span> |  

---  

### <a name="loadeventfired"></a><span data-ttu-id="b4a33-175">loadEventFired</span><span class="sxs-lookup"><span data-stu-id="b4a33-175">loadEventFired</span></span>  

<span data-ttu-id="b4a33-176">对应于 `window.onload` 事件。</span><span class="sxs-lookup"><span data-stu-id="b4a33-176">Corresponds to the `window.onload` event.</span></span>  

| <span data-ttu-id="b4a33-177">参数</span><span class="sxs-lookup"><span data-stu-id="b4a33-177">Parameters</span></span> | <span data-ttu-id="b4a33-178">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-178">Type</span></span> | <span data-ttu-id="b4a33-179">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-179">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-180">timestamp</span><span class="sxs-lookup"><span data-stu-id="b4a33-180">timestamp</span></span> | `number` | <span data-ttu-id="b4a33-181">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="b4a33-181">Number of milliseconds since epoch.</span></span> |  

---  

### <a name="domcontenteventfired"></a><span data-ttu-id="b4a33-182">domContentEventFired</span><span class="sxs-lookup"><span data-stu-id="b4a33-182">domContentEventFired</span></span>  

<span data-ttu-id="b4a33-183">对应于 `document.onDOMContentLoaded` 事件。</span><span class="sxs-lookup"><span data-stu-id="b4a33-183">Corresponds to the `document.onDOMContentLoaded` event.</span></span>  

| <span data-ttu-id="b4a33-184">参数</span><span class="sxs-lookup"><span data-stu-id="b4a33-184">Parameters</span></span> | <span data-ttu-id="b4a33-185">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-185">Type</span></span> | <span data-ttu-id="b4a33-186">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-186">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-187">timestamp</span><span class="sxs-lookup"><span data-stu-id="b4a33-187">timestamp</span></span> | `number` | <span data-ttu-id="b4a33-188">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="b4a33-188">Number of milliseconds since epoch.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="b4a33-189">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-189">Types</span></span>  

### <a name="frameid-string"></a><span data-ttu-id="b4a33-190">FrameId 字符串</span><span class="sxs-lookup"><span data-stu-id="b4a33-190">FrameId string</span></span>  

<a name="frameid"></a>  

<span data-ttu-id="b4a33-191">唯一的帧标识符。</span><span class="sxs-lookup"><span data-stu-id="b4a33-191">Unique frame identifier.</span></span>  

&nbsp;  

---  

### <a name="frame-object"></a><span data-ttu-id="b4a33-192">Frame 对象</span><span class="sxs-lookup"><span data-stu-id="b4a33-192">Frame object</span></span>  

<a name="frame"></a>  

<span data-ttu-id="b4a33-193">有关页面上框架的信息。</span><span class="sxs-lookup"><span data-stu-id="b4a33-193">Information about the Frame on the Page.</span></span>  

| <span data-ttu-id="b4a33-194">属性</span><span class="sxs-lookup"><span data-stu-id="b4a33-194">Properties</span></span> | <span data-ttu-id="b4a33-195">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-195">Type</span></span> | <span data-ttu-id="b4a33-196">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-196">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-197">id</span><span class="sxs-lookup"><span data-stu-id="b4a33-197">id</span></span> | [<span data-ttu-id="b4a33-198">FrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-198">FrameId</span></span>](#frameid) | <span data-ttu-id="b4a33-199">帧唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b4a33-199">Frame unique identifier.</span></span> |  
| <span data-ttu-id="b4a33-200">parentId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="b4a33-200">parentId \(optional\)</span></span> | [<span data-ttu-id="b4a33-201">FrameId</span><span class="sxs-lookup"><span data-stu-id="b4a33-201">FrameId</span></span>](#frameid) | <span data-ttu-id="b4a33-202">父帧唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b4a33-202">Parent frame unique identifier.</span></span> |  
| <span data-ttu-id="b4a33-203">name \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="b4a33-203">name \(optional\)</span></span> | `string` | <span data-ttu-id="b4a33-204">标记中指定的框架名称。</span><span class="sxs-lookup"><span data-stu-id="b4a33-204">Frame's name as specified in the tag.</span></span> |  
| <span data-ttu-id="b4a33-205">url</span><span class="sxs-lookup"><span data-stu-id="b4a33-205">url</span></span> | `string` | <span data-ttu-id="b4a33-206">框架文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="b4a33-206">Frame document's URL.</span></span> |  
| <span data-ttu-id="b4a33-207">securityOrigin</span><span class="sxs-lookup"><span data-stu-id="b4a33-207">securityOrigin</span></span> | `string` | <span data-ttu-id="b4a33-208">框架文档的安全来源。</span><span class="sxs-lookup"><span data-stu-id="b4a33-208">Frame document's security origin.</span></span> |  
| <span data-ttu-id="b4a33-209">mimeType</span><span class="sxs-lookup"><span data-stu-id="b4a33-209">mimeType</span></span> | `string` | <span data-ttu-id="b4a33-210">框架文档的 mimeType，由浏览器确定。</span><span class="sxs-lookup"><span data-stu-id="b4a33-210">Frame document's mimeType as determined by the browser.</span></span> |  

---  

### <a name="frametree-object"></a><span data-ttu-id="b4a33-211">FrameTree 对象</span><span class="sxs-lookup"><span data-stu-id="b4a33-211">FrameTree object</span></span>  

<a name="frametree"></a>  

<span data-ttu-id="b4a33-212">有关 Frame 层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="b4a33-212">Information about the Frame hierarchy.</span></span>  

| <span data-ttu-id="b4a33-213">属性</span><span class="sxs-lookup"><span data-stu-id="b4a33-213">Properties</span></span> | <span data-ttu-id="b4a33-214">类型</span><span class="sxs-lookup"><span data-stu-id="b4a33-214">Type</span></span> | <span data-ttu-id="b4a33-215">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a33-215">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b4a33-216">frame</span><span class="sxs-lookup"><span data-stu-id="b4a33-216">frame</span></span> | [<span data-ttu-id="b4a33-217">帧</span><span class="sxs-lookup"><span data-stu-id="b4a33-217">Frame</span></span>](#frame) | <span data-ttu-id="b4a33-218">此树项的框架信息。</span><span class="sxs-lookup"><span data-stu-id="b4a33-218">Frame information for this tree item.</span></span> |  
| <span data-ttu-id="b4a33-219">childFrames \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="b4a33-219">childFrames \(optional\)</span></span> | [<span data-ttu-id="b4a33-220">FrameTree[]</span><span class="sxs-lookup"><span data-stu-id="b4a33-220">FrameTree[]</span></span>](#frametree) | <span data-ttu-id="b4a33-221">子框架。</span><span class="sxs-lookup"><span data-stu-id="b4a33-221">Child frames.</span></span> |  

---  
