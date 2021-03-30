---
description: DevTools 协议版本 0.2 (EdgeHTML) 调试器域参考。 调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐步执行、探索堆栈跟踪等。
title: '调试器域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 00c410812edd4d11e9904a489955e7fd218a7e5d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398173"
---
# <a name="debugger-domain---devtools-protocol-version-02-edgehtml"></a><span data-ttu-id="e6e4f-105">调试器域 - DevTools 协议版本 0.2 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-105">Debugger Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="e6e4f-106">调试器域公开 JavaScript 调试功能。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-106">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="e6e4f-107">它允许设置和删除断点、逐步执行、探索堆栈跟踪等。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| <span data-ttu-id="e6e4f-108">分类</span><span class="sxs-lookup"><span data-stu-id="e6e4f-108">Classification</span></span> | <span data-ttu-id="e6e4f-109">成员</span><span class="sxs-lookup"><span data-stu-id="e6e4f-109">Members</span></span> |  
|:--- |:--- |  
| [**<span data-ttu-id="e6e4f-110">方法</span><span class="sxs-lookup"><span data-stu-id="e6e4f-110">Methods</span></span>**](#methods) | <span data-ttu-id="e6e4f-111">[enable](#enable)， [disable](#disable)， [getPossibleBreakpoints，](#getpossiblebreakpoints) [setBreakpointsActive，](#setbreakpointsactive) [setBreakpointByUrl，](#setbreakpointbyurl) [setBreakpoint，](#setbreakpoint) [removeBreakpoint，](#removebreakpoint) [stepOver，](#stepover) [stepInto，](#stepinto) [stepOut，](#stepout) [pause，](#pause) [resume，](#resume) [getScriptSource，](#getscriptsource) [setPauseOnExceptions，](#setpauseonexceptions) [evaluateOnCallFrame，](#evaluateoncallframe) [setVariableValue，](#setvariablevalue) [setBlackboxPatterns，](#setblackboxpatterns) [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="e6e4f-111">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |  
| [**<span data-ttu-id="e6e4f-112">事件</span><span class="sxs-lookup"><span data-stu-id="e6e4f-112">Events</span></span>**](#events) | <span data-ttu-id="e6e4f-113">[scriptParsed](#scriptparsed)， [breakpointResolved，](#breakpointresolved) [paused，](#paused) [resumed](#resumed)</span><span class="sxs-lookup"><span data-stu-id="e6e4f-113">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |  
| [**<span data-ttu-id="e6e4f-114">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-114">Types</span></span>**](#types) | <span data-ttu-id="e6e4f-115">[BreakpointId](#breakpointid)， [CallFrameId](#callframeid)， [Location](#location)， [BreakLocation](#breaklocation)， [CallFrame](#callframe)， [Scope](#scope)</span><span class="sxs-lookup"><span data-stu-id="e6e4f-115">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |  
| [**<span data-ttu-id="e6e4f-116">依赖关系</span><span class="sxs-lookup"><span data-stu-id="e6e4f-116">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="e6e4f-117">运行时</span><span class="sxs-lookup"><span data-stu-id="e6e4f-117">Runtime</span></span>](./runtime.md) |  

## <a name="methods"></a><span data-ttu-id="e6e4f-118">方法</span><span class="sxs-lookup"><span data-stu-id="e6e4f-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="e6e4f-119">“启用”</span><span class="sxs-lookup"><span data-stu-id="e6e4f-119">enable</span></span>  

<span data-ttu-id="e6e4f-120">为给定页面启用调试程序。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-120">Enables debugger for the given page.</span></span> <span data-ttu-id="e6e4f-121">在接收此命令的结果之前，客户端不应假定调试已启用。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-121">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="e6e4f-122">“禁用”</span><span class="sxs-lookup"><span data-stu-id="e6e4f-122">disable</span></span>  

<span data-ttu-id="e6e4f-123">禁用给定页面的调试器。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-123">Disables debugger for given page.</span></span>  

&nbsp;  

---  

### <a name="getpossiblebreakpoints"></a><span data-ttu-id="e6e4f-124">getPossibleBreakpoints</span><span class="sxs-lookup"><span data-stu-id="e6e4f-124">getPossibleBreakpoints</span></span>  

<span data-ttu-id="e6e4f-125">返回断点的可能位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-125">Returns possible locations for breakpoint.</span></span> <span data-ttu-id="e6e4f-126">start 和 end range 位置中的 scriptId 应相同。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-126">scriptId in start and end range locations should be the same.</span></span>  

| <span data-ttu-id="e6e4f-127">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-127">Parameters</span></span> | <span data-ttu-id="e6e4f-128">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-128">Type</span></span> | <span data-ttu-id="e6e4f-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-129">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-130">start</span><span class="sxs-lookup"><span data-stu-id="e6e4f-130">start</span></span> | [<span data-ttu-id="e6e4f-131">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-131">Location</span></span>](#location) | <span data-ttu-id="e6e4f-132">搜索可能断点位置的范围开始。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-132">Start of range to search possible breakpoint locations in.</span></span> |  
| <span data-ttu-id="e6e4f-133">结束</span><span class="sxs-lookup"><span data-stu-id="e6e4f-133">end</span></span> | [<span data-ttu-id="e6e4f-134">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-134">Location</span></span>](#location) | <span data-ttu-id="e6e4f-135">要搜索 \(中可能断点位置的范围结束，但不包括\) 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-135">End of range to search possible breakpoint locations in \(excluding\).</span></span>  <span data-ttu-id="e6e4f-136">如果未指定，脚本的末尾将用作范围的末尾。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-136">When not specified, end of scripts is used as end of range.</span></span> |  

| <span data-ttu-id="e6e4f-137">返回</span><span class="sxs-lookup"><span data-stu-id="e6e4f-137">Returns</span></span> | <span data-ttu-id="e6e4f-138">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-138">Type</span></span> | <span data-ttu-id="e6e4f-139">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-139">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-140">locations</span><span class="sxs-lookup"><span data-stu-id="e6e4f-140">locations</span></span> | [<span data-ttu-id="e6e4f-141">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="e6e4f-141">BreakLocation</span></span>](#breaklocation) | <span data-ttu-id="e6e4f-142">可能的断点位置的列表。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-142">List of the possible breakpoint locations.</span></span> |  

---  

### <a name="setbreakpointsactive"></a><span data-ttu-id="e6e4f-143">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="e6e4f-143">setBreakpointsActive</span></span>  

<span data-ttu-id="e6e4f-144">激活/停用页面上的所有断点。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-144">Activates / deactivates all breakpoints on the page.</span></span>  

| <span data-ttu-id="e6e4f-145">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-145">Parameters</span></span> | <span data-ttu-id="e6e4f-146">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-146">Type</span></span> | <span data-ttu-id="e6e4f-147">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-147">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-148">active</span><span class="sxs-lookup"><span data-stu-id="e6e4f-148">active</span></span> | `boolean` | <span data-ttu-id="e6e4f-149">断点活动状态的新值。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-149">New value for breakpoints active state.</span></span> | 

---  

### <a name="setbreakpointbyurl"></a><span data-ttu-id="e6e4f-150">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="e6e4f-150">setBreakpointByUrl</span></span>  

<span data-ttu-id="e6e4f-151">设置由 URL 或 URL 正则表达式指定的给定位置的 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-151">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span>  <span data-ttu-id="e6e4f-152">发出此命令后，所有现有分析脚本都将在属性中解析和返回断 `locations` 点。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-152">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in `locations` property.</span></span>  <span data-ttu-id="e6e4f-153">进一步匹配脚本分析将导致 `breakpointResolved` 后续事件发布。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-153">Further matching script parsing will result in subsequent `breakpointResolved` events issued.</span></span>  <span data-ttu-id="e6e4f-154">此逻辑断点在重新加载页面时将生存下来。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-154">This logical breakpoint will survive page reloads.</span></span>  

| <span data-ttu-id="e6e4f-155">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-155">Parameters</span></span> | <span data-ttu-id="e6e4f-156">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-156">Type</span></span> | <span data-ttu-id="e6e4f-157">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-157">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-158">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e6e4f-158">lineNumber</span></span> | `integer` | <span data-ttu-id="e6e4f-159">要设置断点的行号。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-159">Line number to set breakpoint at.</span></span> | 
| <span data-ttu-id="e6e4f-160">url \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-160">url \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-161">要设置断点的资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-161">URL of the resources to set breakpoint on.</span></span> |  
| <span data-ttu-id="e6e4f-162">urlRegex \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-162">urlRegex \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-163">要设置断点的资源 URL 的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-163">Regex pattern for the URLs of the resources to set breakpoints on.</span></span>  <span data-ttu-id="e6e4f-164">或者 `url` `urlRegex` 必须指定。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-164">Either `url` or `urlRegex` must be specified.</span></span> |  
| <span data-ttu-id="e6e4f-165">columnNumber \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-165">columnNumber \(optional\)</span></span> | `integer` | <span data-ttu-id="e6e4f-166">要设置断点的行中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-166">Offset in the line to set breakpoint at.</span></span> |  
| <span data-ttu-id="e6e4f-167">condition \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-167">condition \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-168">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-168">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="e6e4f-169">指定此参数时，如果此表达式计算结果为 true，调试器将仅在断点停止。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-169">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="e6e4f-170">返回</span><span class="sxs-lookup"><span data-stu-id="e6e4f-170">Returns</span></span> | <span data-ttu-id="e6e4f-171">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-171">Type</span></span> | <span data-ttu-id="e6e4f-172">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-172">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-173">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-173">breakpointId</span></span> | [<span data-ttu-id="e6e4f-174">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-174">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="e6e4f-175">创建的断点的 ID，供进一步参考。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-175">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="e6e4f-176">locations</span><span class="sxs-lookup"><span data-stu-id="e6e4f-176">locations</span></span> | [<span data-ttu-id="e6e4f-177">位置[]</span><span class="sxs-lookup"><span data-stu-id="e6e4f-177">Location[]</span></span>](#location) | <span data-ttu-id="e6e4f-178">添加时此断点解析到的位置的列表。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-178">List of the locations this breakpoint resolved into upon addition.</span></span> |  

---  

### <a name="setbreakpoint"></a><span data-ttu-id="e6e4f-179">setBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e6e4f-179">setBreakpoint</span></span>  

<span data-ttu-id="e6e4f-180">设置给定位置的 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-180">Sets JavaScript breakpoint at a given location.</span></span>  

| <span data-ttu-id="e6e4f-181">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-181">Parameters</span></span> | <span data-ttu-id="e6e4f-182">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-182">Type</span></span> | <span data-ttu-id="e6e4f-183">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-183">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-184">location</span><span class="sxs-lookup"><span data-stu-id="e6e4f-184">location</span></span> | [<span data-ttu-id="e6e4f-185">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-185">Location</span></span>](#location) | <span data-ttu-id="e6e4f-186">要设置断点的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-186">Location to set breakpoint in.</span></span> |  
| <span data-ttu-id="e6e4f-187">condition \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-187">condition \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-188">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-188">Expression to use as a breakpoint condition.</span></span>  <span data-ttu-id="e6e4f-189">指定此参数时，如果此表达式计算结果为 true，调试器将仅在断点停止。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-189">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="e6e4f-190">返回</span><span class="sxs-lookup"><span data-stu-id="e6e4f-190">Returns</span></span> | <span data-ttu-id="e6e4f-191">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-191">Type</span></span> | <span data-ttu-id="e6e4f-192">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-192">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-193">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-193">breakpointId</span></span> | [<span data-ttu-id="e6e4f-194">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-194">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="e6e4f-195">创建的断点的 ID，供进一步参考。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-195">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="e6e4f-196">actualLocation</span><span class="sxs-lookup"><span data-stu-id="e6e4f-196">actualLocation</span></span> | [<span data-ttu-id="e6e4f-197">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-197">Location</span></span>](#location) | <span data-ttu-id="e6e4f-198">解析到的断点的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-198">Location this breakpoint resolved into.</span></span> |  

---  

### <a name="removebreakpoint"></a><span data-ttu-id="e6e4f-199">removeBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e6e4f-199">removeBreakpoint</span></span>  

<span data-ttu-id="e6e4f-200">删除 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-200">Removes JavaScript breakpoint.</span></span>  

| <span data-ttu-id="e6e4f-201">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-201">Parameters</span></span> | <span data-ttu-id="e6e4f-202">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-202">Type</span></span> | <span data-ttu-id="e6e4f-203">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-203">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-204">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-204">breakpointId</span></span> | [<span data-ttu-id="e6e4f-205">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-205">BreakpointId</span></span>](#breakpointid) | &nbsp; |  

---  

### <a name="stepover"></a><span data-ttu-id="e6e4f-206">stepOver</span><span class="sxs-lookup"><span data-stu-id="e6e4f-206">stepOver</span></span>  

<span data-ttu-id="e6e4f-207">对语句的步骤。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-207">Steps over the statement.</span></span>  

&nbsp;  

---  

### <a name="stepinto"></a><span data-ttu-id="e6e4f-208">stepInto</span><span class="sxs-lookup"><span data-stu-id="e6e4f-208">stepInto</span></span>  

<span data-ttu-id="e6e4f-209">进入函数调用。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-209">Steps into the function call.</span></span>  

&nbsp;  

---  

### <a name="stepout"></a><span data-ttu-id="e6e4f-210">stepOut</span><span class="sxs-lookup"><span data-stu-id="e6e4f-210">stepOut</span></span>  

<span data-ttu-id="e6e4f-211">退出函数调用。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-211">Steps out of the function call.</span></span>  

&nbsp;  

---  

### <a name="pause"></a><span data-ttu-id="e6e4f-212">pause</span><span class="sxs-lookup"><span data-stu-id="e6e4f-212">pause</span></span>  

<span data-ttu-id="e6e4f-213">停止下一个 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-213">Stops on the next JavaScript statement.</span></span>  

&nbsp;  

---  

### <a name="resume"></a><span data-ttu-id="e6e4f-214">resume</span><span class="sxs-lookup"><span data-stu-id="e6e4f-214">resume</span></span>  

<span data-ttu-id="e6e4f-215">恢复 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-215">Resumes JavaScript execution.</span></span>  

&nbsp;  

---  

### <a name="getscriptsource"></a><span data-ttu-id="e6e4f-216">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="e6e4f-216">getScriptSource</span></span>  

<span data-ttu-id="e6e4f-217">返回具有给定 ID 的脚本的源。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-217">Returns source for the script with given id.</span></span>  

| <span data-ttu-id="e6e4f-218">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-218">Parameters</span></span> | <span data-ttu-id="e6e4f-219">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-219">Type</span></span> | <span data-ttu-id="e6e4f-220">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-220">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-221">scriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-221">scriptId</span></span> | [<span data-ttu-id="e6e4f-222">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-222">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="e6e4f-223">要获取其源的脚本的 ID。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-223">ID of the script to get source for.</span></span> |  

| <span data-ttu-id="e6e4f-224">返回</span><span class="sxs-lookup"><span data-stu-id="e6e4f-224">Returns</span></span> | <span data-ttu-id="e6e4f-225">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-225">Type</span></span> | <span data-ttu-id="e6e4f-226">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-226">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-227">scriptSource</span><span class="sxs-lookup"><span data-stu-id="e6e4f-227">scriptSource</span></span> | `string` | <span data-ttu-id="e6e4f-228">脚本源。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-228">Script source.</span></span> | 

---  

### <a name="setpauseonexceptions"></a><span data-ttu-id="e6e4f-229">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="e6e4f-229">setPauseOnExceptions</span></span>  

<span data-ttu-id="e6e4f-230">定义异常状态上的暂停。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-230">Defines pause on exceptions state.</span></span>  <span data-ttu-id="e6e4f-231">可以设置为在所有异常、未捕获的异常或无异常上停止。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-231">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span>  <span data-ttu-id="e6e4f-232">异常状态的初始暂停为 `none` 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-232">Initial pause on exceptions state is `none`.</span></span>  

| <span data-ttu-id="e6e4f-233">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-233">Parameters</span></span> | <span data-ttu-id="e6e4f-234">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-234">Type</span></span> | <span data-ttu-id="e6e4f-235">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-235">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-236">state</span><span class="sxs-lookup"><span data-stu-id="e6e4f-236">state</span></span> | `string` | <span data-ttu-id="e6e4f-237">暂停异常模式。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-237">Pause on exceptions mode.</span></span>  <span data-ttu-id="e6e4f-238">允许的值：  `none` `uncaught` ， ，</span><span class="sxs-lookup"><span data-stu-id="e6e4f-238">Allowed values:  `none`, `uncaught`,</span></span> `all` |  

---  

### <a name="evaluateoncallframe"></a><span data-ttu-id="e6e4f-239">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="e6e4f-239">evaluateOnCallFrame</span></span>  

<span data-ttu-id="e6e4f-240">计算给定呼叫帧上的表达式。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-240">Evaluates expression on a given call frame.</span></span>  

| <span data-ttu-id="e6e4f-241">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-241">Parameters</span></span> | <span data-ttu-id="e6e4f-242">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-242">Type</span></span> | <span data-ttu-id="e6e4f-243">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-243">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-244">callFrameId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-244">callFrameId</span></span> | [<span data-ttu-id="e6e4f-245">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-245">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="e6e4f-246">要评估的呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-246">Call frame identifier to evaluate on.</span></span> |  
| <span data-ttu-id="e6e4f-247">表达式</span><span class="sxs-lookup"><span data-stu-id="e6e4f-247">expression</span></span> | `string` | <span data-ttu-id="e6e4f-248">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-248">Expression to evaluate.</span></span> | 

| <span data-ttu-id="e6e4f-249">返回</span><span class="sxs-lookup"><span data-stu-id="e6e4f-249">Returns</span></span> | <span data-ttu-id="e6e4f-250">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-250">Type</span></span> | <span data-ttu-id="e6e4f-251">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-251">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-252">result</span><span class="sxs-lookup"><span data-stu-id="e6e4f-252">result</span></span> | [<span data-ttu-id="e6e4f-253">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="e6e4f-253">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="e6e4f-254">评估结果的对象包装。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-254">Object wrapper for the evaluation result.</span></span> |  

---  

### <a name="setvariablevalue"></a><span data-ttu-id="e6e4f-255">setVariableValue</span><span class="sxs-lookup"><span data-stu-id="e6e4f-255">setVariableValue</span></span>  

<span data-ttu-id="e6e4f-256">更改调用框内变量的值。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-256">Changes value of variable in a callframe.</span></span>  <span data-ttu-id="e6e4f-257">不支持基于对象的作用域，必须手动进行可变。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-257">Object-based scopes are not supported and must be mutated manually.</span></span>  

| <span data-ttu-id="e6e4f-258">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-258">Parameters</span></span> | <span data-ttu-id="e6e4f-259">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-259">Type</span></span> | <span data-ttu-id="e6e4f-260">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-260">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-261">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="e6e4f-261">scopeNumber</span></span> | `integer` | <span data-ttu-id="e6e4f-262">范围链中列出的基于 0 的范围数。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-262">0-based number of scope as was listed in scope chain.</span></span>  <span data-ttu-id="e6e4f-263">仅 `local` `closure` 允许 ， `catch` 和范围类型。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-263">Only `local`, `closure`, and `catch` scope types are allowed.</span></span>  <span data-ttu-id="e6e4f-264">可以手动操作其他范围。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-264">Other scopes could be manipulated manually.</span></span> | 
| <span data-ttu-id="e6e4f-265">variableName</span><span class="sxs-lookup"><span data-stu-id="e6e4f-265">variableName</span></span> | `string` | <span data-ttu-id="e6e4f-266">变量名称。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-266">Variable name.</span></span> | 
| <span data-ttu-id="e6e4f-267">newValue</span><span class="sxs-lookup"><span data-stu-id="e6e4f-267">newValue</span></span> | [<span data-ttu-id="e6e4f-268">Runtime.CallArgument</span><span class="sxs-lookup"><span data-stu-id="e6e4f-268">Runtime.CallArgument</span></span>](./runtime.md#callargument) | <span data-ttu-id="e6e4f-269">新变量值。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-269">New variable value.</span></span> |  
| <span data-ttu-id="e6e4f-270">callFrameId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-270">callFrameId</span></span> | [<span data-ttu-id="e6e4f-271">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-271">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="e6e4f-272">包含变量的调用框的 ID。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-272">ID of callframe that holds variable.</span></span> |  

---  

### <a name="setblackboxpatterns"></a><span data-ttu-id="e6e4f-273">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="e6e4f-273">setBlackboxPatterns</span></span>  

<span data-ttu-id="e6e4f-274">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-274">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-275">将以前的黑箱模式替换为传递的黑色框模式。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-275">Replace previous blackbox patterns with passed ones.</span></span>  <span data-ttu-id="e6e4f-276">强制后端在 URL 与其中一种模式匹配的脚本中跳过单步执行/暂停。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-276">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span>  <span data-ttu-id="e6e4f-277">调试器将尝试通过多次执行"分步"来退出黑盒脚本，如果失败，最后会使用"退出"。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-277">The debugger will try to leave blackboxed script by performing 'step in' several times, finally resorting to 'step out' if unsuccessful.</span></span>  


| <span data-ttu-id="e6e4f-278">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-278">Parameters</span></span> | <span data-ttu-id="e6e4f-279">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-279">Type</span></span> | <span data-ttu-id="e6e4f-280">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-280">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-281">模式</span><span class="sxs-lookup"><span data-stu-id="e6e4f-281">patterns</span></span> | `string[]` | <span data-ttu-id="e6e4f-282">将用于检查脚本 URL 的 blackbox 状态正则表达式的数组。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-282">Array of regexps that will be used to check script url for blackbox state.</span></span> | 

---  

### <a name="mssetdebuggerpropertyvalue"></a><span data-ttu-id="e6e4f-283">msSetDebuggerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="e6e4f-283">msSetDebuggerPropertyValue</span></span>  

<span data-ttu-id="e6e4f-284">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-284">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-285">Microsoft：将指定的调试器属性设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-285">Microsoft: Sets the specified debugger property to the specified value.</span></span>  

| <span data-ttu-id="e6e4f-286">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-286">Parameters</span></span> | <span data-ttu-id="e6e4f-287">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-287">Type</span></span> | <span data-ttu-id="e6e4f-288">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-288">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-289">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-289">debuggerPropertyId</span></span> | <span data-ttu-id="e6e4f-290">字符串</span><span class="sxs-lookup"><span data-stu-id="e6e4f-290">string</span></span> | <span data-ttu-id="e6e4f-291">Microsoft：要设置 (`msDebuggerPropertyId` \) \ 属性 ID。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-291">Microsoft:  The property id \(i.e. `msDebuggerPropertyId`\) to set.</span></span> | 
| <span data-ttu-id="e6e4f-292">newValue</span><span class="sxs-lookup"><span data-stu-id="e6e4f-292">newValue</span></span> | `string` | &nbsp; |  

---  

## <a name="events"></a><span data-ttu-id="e6e4f-293">事件</span><span class="sxs-lookup"><span data-stu-id="e6e4f-293">Events</span></span>  

### <a name="scriptparsed"></a><span data-ttu-id="e6e4f-294">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="e6e4f-294">scriptParsed</span></span>  

<span data-ttu-id="e6e4f-295">分析脚本时触发。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-295">Fired when the script is parsed.</span></span> <span data-ttu-id="e6e4f-296">启用调试程序时，还会针对所有已知和未安装脚本触发此事件。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-296">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>  

| <span data-ttu-id="e6e4f-297">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-297">Parameters</span></span> | <span data-ttu-id="e6e4f-298">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-298">Type</span></span> | <span data-ttu-id="e6e4f-299">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-299">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-300">scriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-300">scriptId</span></span> | [<span data-ttu-id="e6e4f-301">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-301">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="e6e4f-302">分析的脚本的标识符。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-302">Identifier of the script parsed.</span></span> |  
| <span data-ttu-id="e6e4f-303">url</span><span class="sxs-lookup"><span data-stu-id="e6e4f-303">url</span></span> | `string` | <span data-ttu-id="e6e4f-304">解析为 \(\) 的脚本的 URL 或) 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-304">URL or name of the script parsed \(if any\).</span></span> | 
| <span data-ttu-id="e6e4f-305">startLine</span><span class="sxs-lookup"><span data-stu-id="e6e4f-305">startLine</span></span> | `integer` | <span data-ttu-id="e6e4f-306">具有给定 URL 的脚本在资源中的行偏移量\(脚本标记\) 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-306">Line offset of the script within the resource with given URL \(for script tags\).</span></span> | 
| <span data-ttu-id="e6e4f-307">startColumn</span><span class="sxs-lookup"><span data-stu-id="e6e4f-307">startColumn</span></span> | `integer` | <span data-ttu-id="e6e4f-308">具有给定 URL 的资源中的脚本的列偏移量。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-308">Column offset of the script within the resource with given URL.</span></span> | 
| <span data-ttu-id="e6e4f-309">endLine</span><span class="sxs-lookup"><span data-stu-id="e6e4f-309">endLine</span></span> | `integer` | <span data-ttu-id="e6e4f-310">脚本的最后一行。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-310">Last line of the script.</span></span> | 
| <span data-ttu-id="e6e4f-311">endColumn</span><span class="sxs-lookup"><span data-stu-id="e6e4f-311">endColumn</span></span> | `integer` | <span data-ttu-id="e6e4f-312">脚本最后一行的长度。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-312">Length of the last line of the script.</span></span> | 
| <span data-ttu-id="e6e4f-313">executionContextId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-313">executionContextId</span></span> | [<span data-ttu-id="e6e4f-314">Runtime.ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-314">Runtime.ExecutionContextId</span></span>](./runtime.md#executioncontextid) | <span data-ttu-id="e6e4f-315">指定脚本创建上下文。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-315">Specifies script creation context.</span></span> |  
| <span data-ttu-id="e6e4f-316">sourceMapURL \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-316">sourceMapURL \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-317">与脚本映射关联的源 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-317">URL of source map associated with script (if any).</span></span> |  
| <span data-ttu-id="e6e4f-318">length \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-318">length \(optional\)</span></span> | `integer` | <span data-ttu-id="e6e4f-319">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-319">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-320">此脚本长度。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-320">This script length.</span></span> |  
| <span data-ttu-id="e6e4f-321">msParentId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-321">msParentId \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-322">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-322">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-323">这是父文档 ID。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-323">This is the parent document ID.</span></span> |  
| <span data-ttu-id="e6e4f-324">msMimeType \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-324">msMimeType \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-325">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-325">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-326">这是 mime 类型。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-326">This is the mime type.</span></span> |  
| <span data-ttu-id="e6e4f-327">msIsDynamicCode \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-327">msIsDynamicCode \(optional\)</span></span> | `boolean` | <span data-ttu-id="e6e4f-328">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-328">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-329">这指示它是否为动态代码。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-329">This indicates whether it is dynamic code.</span></span> |  
| <span data-ttu-id="e6e4f-330">msLongDocumentId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-330">msLongDocumentId \(optional\)</span></span> | `integer` | <span data-ttu-id="e6e4f-331">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-331">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-332">这是长文档 ID。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-332">This is the long document ID.</span></span> |  

---  

### <a name="breakpointresolved"></a><span data-ttu-id="e6e4f-333">breakpointResolved</span><span class="sxs-lookup"><span data-stu-id="e6e4f-333">breakpointResolved</span></span>  

<span data-ttu-id="e6e4f-334">当断点解析为实际脚本和位置时触发。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-334">Fired when breakpoint is resolved to an actual script and location.</span></span>  

| <span data-ttu-id="e6e4f-335">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-335">Parameters</span></span> | <span data-ttu-id="e6e4f-336">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-336">Type</span></span> | <span data-ttu-id="e6e4f-337">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-337">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-338">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-338">breakpointId</span></span> | [<span data-ttu-id="e6e4f-339">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-339">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="e6e4f-340">断点唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-340">Breakpoint unique identifier.</span></span> |  
| <span data-ttu-id="e6e4f-341">location</span><span class="sxs-lookup"><span data-stu-id="e6e4f-341">location</span></span> | [<span data-ttu-id="e6e4f-342">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-342">Location</span></span>](#location) | <span data-ttu-id="e6e4f-343">实际断点位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-343">Actual breakpoint location.</span></span> |  
| <span data-ttu-id="e6e4f-344">msLength \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-344">msLength \(optional\)</span></span> | `integer` | <span data-ttu-id="e6e4f-345">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-345">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-346">Microsoft：代码 \(长度，即断点) 字符数\</span><span class="sxs-lookup"><span data-stu-id="e6e4f-346">Microsoft:  Length of code \(i.e. number of characters\) at the breakpoint location.</span></span> |  

---  

### <a name="paused"></a><span data-ttu-id="e6e4f-347">已暂停</span><span class="sxs-lookup"><span data-stu-id="e6e4f-347">paused</span></span>  

<span data-ttu-id="e6e4f-348">当调试器中断断点或异常时触发。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-348">Fired when the debuggers breaks for a breakpoint or exception.</span></span>  

| <span data-ttu-id="e6e4f-349">参数</span><span class="sxs-lookup"><span data-stu-id="e6e4f-349">Parameters</span></span> | <span data-ttu-id="e6e4f-350">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-350">Type</span></span> | <span data-ttu-id="e6e4f-351">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-351">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-352">callFrames</span><span class="sxs-lookup"><span data-stu-id="e6e4f-352">callFrames</span></span> | [<span data-ttu-id="e6e4f-353">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="e6e4f-353">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="e6e4f-354">调用调试器停止的堆栈。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-354">Call stack the debugger stopped on.</span></span> |  
| <span data-ttu-id="e6e4f-355">reason</span><span class="sxs-lookup"><span data-stu-id="e6e4f-355">reason</span></span> | `string` |  <span data-ttu-id="e6e4f-356">暂停原因。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-356">Pause reason.</span></span>  <span data-ttu-id="e6e4f-357">允许的值  `breakpoint` `step` `exception` ：、、、 `other` 和</span><span class="sxs-lookup"><span data-stu-id="e6e4f-357">Allowed values:  `breakpoint`, `step`, `exception`, `other`, and</span></span> `EventListener` |  
| <span data-ttu-id="e6e4f-358">data \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-358">data \(optional\)</span></span> | `object` | <span data-ttu-id="e6e4f-359">包含特定于中断的辅助属性的对象。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-359">Object containing break-specific auxiliary properties.</span></span> |  
| <span data-ttu-id="e6e4f-360">hitBreakpoints \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-360">hitBreakpoints \(optional\)</span></span> | `string[]` | <span data-ttu-id="e6e4f-361">命中断点 ID</span><span class="sxs-lookup"><span data-stu-id="e6e4f-361">Hit breakpoints IDs</span></span> |  
| <span data-ttu-id="e6e4f-362">asyncStackTrace \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-362">asyncStackTrace \(optional\)</span></span> | `StackTrace` | <span data-ttu-id="e6e4f-363">JavaScript 异步堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-363">JavaScript async stack trace.</span></span> |  

---  

### <a name="resumed"></a><span data-ttu-id="e6e4f-364">恢复</span><span class="sxs-lookup"><span data-stu-id="e6e4f-364">resumed</span></span>  

<span data-ttu-id="e6e4f-365">在调试程序恢复执行时触发。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-365">Fired when the debugger resumes execution.</span></span>  

&nbsp;  

---  

## <a name="types"></a><span data-ttu-id="e6e4f-366">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-366">Types</span></span>  

### <a name="breakpointid-string"></a><span data-ttu-id="e6e4f-367">BreakpointId 字符串</span><span class="sxs-lookup"><span data-stu-id="e6e4f-367">BreakpointId string</span></span>  

<a name="breakpointid"></a>  

<span data-ttu-id="e6e4f-368">断点标识符。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-368">Breakpoint identifier.</span></span>  

&nbsp;  

---  

### <a name="callframeid-string"></a><span data-ttu-id="e6e4f-369">CallFrameId 字符串</span><span class="sxs-lookup"><span data-stu-id="e6e4f-369">CallFrameId string</span></span>  

<a name="callframeid"></a>  

<span data-ttu-id="e6e4f-370">呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-370">Call frame identifier.</span></span>  

&nbsp;  

---  

### <a name="location-object"></a><span data-ttu-id="e6e4f-371">Location 对象</span><span class="sxs-lookup"><span data-stu-id="e6e4f-371">Location object</span></span>  

<a name="location"></a>  

<span data-ttu-id="e6e4f-372">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-372">Location in the source code.</span></span>  

| <span data-ttu-id="e6e4f-373">属性</span><span class="sxs-lookup"><span data-stu-id="e6e4f-373">Properties</span></span> | <span data-ttu-id="e6e4f-374">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-374">Type</span></span> | <span data-ttu-id="e6e4f-375">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-375">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-376">scriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-376">scriptId</span></span> | [<span data-ttu-id="e6e4f-377">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-377">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="e6e4f-378">中报告的脚本标识符 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-378">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="e6e4f-379">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e6e4f-379">lineNumber</span></span> | `integer` | <span data-ttu-id="e6e4f-380">脚本 \(0\) 中的行) 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-380">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="e6e4f-381">columnNumber \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-381">columnNumber \(optional\)</span></span> | `integer` | <span data-ttu-id="e6e4f-382">脚本 \(0\) 中的列号。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-382">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="e6e4f-383">msLength</span><span class="sxs-lookup"><span data-stu-id="e6e4f-383">msLength</span></span> | `integer` | <span data-ttu-id="e6e4f-384">Microsoft：代码 \(，即此调用帧) 字符数\字符数。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-384">Microsoft:  Length of code \(i.e. number of characters\) at this call frame.</span></span> |  

---  

### <a name="breaklocation-object"></a><span data-ttu-id="e6e4f-385">BreakLocation 对象</span><span class="sxs-lookup"><span data-stu-id="e6e4f-385">BreakLocation object</span></span>  

<a name="breaklocation"></a>  

<span data-ttu-id="e6e4f-386">中断源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-386">Break location in the source code.</span></span>  

| <span data-ttu-id="e6e4f-387">属性</span><span class="sxs-lookup"><span data-stu-id="e6e4f-387">Properties</span></span> | <span data-ttu-id="e6e4f-388">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-388">Type</span></span> | <span data-ttu-id="e6e4f-389">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-389">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-390">scriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-390">scriptId</span></span> | [<span data-ttu-id="e6e4f-391">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-391">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="e6e4f-392">报告在 中的脚本标识符 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-392">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="e6e4f-393">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e6e4f-393">lineNumber</span></span> | `integer` | <span data-ttu-id="e6e4f-394">脚本 \(0\) 中的行) 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-394">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="e6e4f-395">columnNumber \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-395">columnNumber \(optional\)</span></span> | `integer` | <span data-ttu-id="e6e4f-396">脚本 \(0\) 中的列号。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-396">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="e6e4f-397">msLength</span><span class="sxs-lookup"><span data-stu-id="e6e4f-397">msLength</span></span> | `integer` | <span data-ttu-id="e6e4f-398">Microsoft：代码 \(，即此调用帧) 字符数\字符数。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-398">Microsoft:  Length of code \(i.e. number of characters\) at this call frame.</span></span> |  
| <span data-ttu-id="e6e4f-399">type \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-399">type \(optional\)</span></span> | `string` | <span data-ttu-id="e6e4f-400">允许的值：debuggerStatement、call、return。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-400">Allowed values: debuggerStatement, call, return.</span></span> |  

---  

### <a name="callframe-object"></a><span data-ttu-id="e6e4f-401">CallFrame 对象</span><span class="sxs-lookup"><span data-stu-id="e6e4f-401">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="e6e4f-402">JavaScript 调用帧。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-402">JavaScript call frame.</span></span> <span data-ttu-id="e6e4f-403">构成调用堆栈的调用帧数组。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-403">Array of call frames form the call stack.</span></span>  

| <span data-ttu-id="e6e4f-404">属性</span><span class="sxs-lookup"><span data-stu-id="e6e4f-404">Properties</span></span> | <span data-ttu-id="e6e4f-405">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-405">Type</span></span> | <span data-ttu-id="e6e4f-406">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-406">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-407">callFrameId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-407">callFrameId</span></span> | [<span data-ttu-id="e6e4f-408">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="e6e4f-408">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="e6e4f-409">呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-409">Call frame identifier.</span></span>  <span data-ttu-id="e6e4f-410">此标识符仅在调试器暂停时有效。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-410">This identifier is only valid while the debugger is paused.</span></span> |  
| <span data-ttu-id="e6e4f-411">functionName</span><span class="sxs-lookup"><span data-stu-id="e6e4f-411">functionName</span></span> | `string` | <span data-ttu-id="e6e4f-412">在此调用帧上调用的 JavaScript 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-412">Name of the JavaScript function called on this call frame.</span></span> |  
| <span data-ttu-id="e6e4f-413">functionLocation \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-413">functionLocation \(optional\)</span></span> | [<span data-ttu-id="e6e4f-414">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-414">Location</span></span>](#location) | <span data-ttu-id="e6e4f-415">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-415">**Experimental**.</span></span>  <span data-ttu-id="e6e4f-416">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-416">Location in the source code.</span></span> |  
| <span data-ttu-id="e6e4f-417">location</span><span class="sxs-lookup"><span data-stu-id="e6e4f-417">location</span></span> | [<span data-ttu-id="e6e4f-418">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-418">Location</span></span>](#location) | <span data-ttu-id="e6e4f-419">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-419">Location in the source code.</span></span> |  
| <span data-ttu-id="e6e4f-420">url</span><span class="sxs-lookup"><span data-stu-id="e6e4f-420">url</span></span> | `string` | <span data-ttu-id="e6e4f-421">JavaScript 脚本名称或 url。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-421">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="e6e4f-422">scopeChain</span><span class="sxs-lookup"><span data-stu-id="e6e4f-422">scopeChain</span></span> | [<span data-ttu-id="e6e4f-423">范围[]</span><span class="sxs-lookup"><span data-stu-id="e6e4f-423">Scope[]</span></span>](#scope) | <span data-ttu-id="e6e4f-424">此呼叫帧的范围链。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-424">Scope chain for this call frame.</span></span> |  
| <span data-ttu-id="e6e4f-425">this</span><span class="sxs-lookup"><span data-stu-id="e6e4f-425">this</span></span> | [<span data-ttu-id="e6e4f-426">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="e6e4f-426">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | `this` <span data-ttu-id="e6e4f-427">对象。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-427">object for this call frame.</span></span> |  
| <span data-ttu-id="e6e4f-428">returnValue \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-428">returnValue \(optional\)</span></span> | [<span data-ttu-id="e6e4f-429">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="e6e4f-429">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="e6e4f-430">如果函数位于返回点，则返回的值。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-430">The value being returned, if the function is at return point.</span></span> |  

---  

### <a name="scope-object"></a><span data-ttu-id="e6e4f-431">Scope 对象</span><span class="sxs-lookup"><span data-stu-id="e6e4f-431">Scope object</span></span>  

<a name="scope"></a>  

<span data-ttu-id="e6e4f-432">范围说明。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-432">Scope description.</span></span>  

| <span data-ttu-id="e6e4f-433">属性</span><span class="sxs-lookup"><span data-stu-id="e6e4f-433">Properties</span></span> | <span data-ttu-id="e6e4f-434">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-434">Type</span></span> | <span data-ttu-id="e6e4f-435">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6e4f-435">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e6e4f-436">类型</span><span class="sxs-lookup"><span data-stu-id="e6e4f-436">type</span></span> | `string` | <span data-ttu-id="e6e4f-437">范围类型。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-437">Scope type.</span></span>  <span data-ttu-id="e6e4f-438">允许的值  `global` `local` `with` ：、、、、、 `closure` `catch` `block` `script` `eval` `module` 和</span><span class="sxs-lookup"><span data-stu-id="e6e4f-438">Allowed values:  `global`, `local`, `with`, `closure`, `catch`, `block`, `script`, `eval`, `module`, and</span></span> `return` |  
| <span data-ttu-id="e6e4f-439">object</span><span class="sxs-lookup"><span data-stu-id="e6e4f-439">object</span></span> | [<span data-ttu-id="e6e4f-440">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="e6e4f-440">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="e6e4f-441">表示范围的对象。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-441">Object representing the scope.</span></span>  <span data-ttu-id="e6e4f-442">对于它表示实际对象和范围;对于其余范围，它是人工临时对象枚举范围变量 `global` `with` 作为其属性。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-442">For `global` and `with` scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span> |  
| <span data-ttu-id="e6e4f-443">name \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-443">name \(optional\)</span></span> | `string` | &nbsp; |  
| <span data-ttu-id="e6e4f-444">startLocation \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-444">startLocation \(optional\)</span></span> | [<span data-ttu-id="e6e4f-445">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-445">Location</span></span>](#location) | <span data-ttu-id="e6e4f-446">范围开始的源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-446">Location in the source code where scope starts.</span></span> |  
| <span data-ttu-id="e6e4f-447">endLocation \(optional\) </span><span class="sxs-lookup"><span data-stu-id="e6e4f-447">endLocation \(optional\)</span></span> | [<span data-ttu-id="e6e4f-448">位置</span><span class="sxs-lookup"><span data-stu-id="e6e4f-448">Location</span></span>](#location) | <span data-ttu-id="e6e4f-449">范围结束的源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e4f-449">Location in the source code where scope ends.</span></span> |  

---  

## <a name="dependencies"></a><span data-ttu-id="e6e4f-450">依赖关系</span><span class="sxs-lookup"><span data-stu-id="e6e4f-450">Dependencies</span></span>  

[<span data-ttu-id="e6e4f-451">运行时</span><span class="sxs-lookup"><span data-stu-id="e6e4f-451">Runtime</span></span>](./runtime.md)  
