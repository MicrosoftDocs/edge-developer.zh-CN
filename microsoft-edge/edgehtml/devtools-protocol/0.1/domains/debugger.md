---
description: DevTools 协议版本 0.1 (EdgeHTML) 调试器域参考。  调试器域公开 JavaScript 调试功能。  它允许设置和删除断点、逐步执行、探索堆栈跟踪等。
title: '调试器域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d63408e23fd8912cf617bfefae2b991387b45a38
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397676"
---
# <a name="debugger-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="3999c-105">调试器域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="3999c-105">Debugger Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  
  
<span data-ttu-id="3999c-106">调试器域公开 JavaScript 调试功能。</span><span class="sxs-lookup"><span data-stu-id="3999c-106">Debugger domain exposes JavaScript debugging capabilities.</span></span>  <span data-ttu-id="3999c-107">它允许设置和删除断点、逐步执行、探索堆栈跟踪等。</span><span class="sxs-lookup"><span data-stu-id="3999c-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| <span data-ttu-id="3999c-108">分类</span><span class="sxs-lookup"><span data-stu-id="3999c-108">Classification</span></span> | <span data-ttu-id="3999c-109">成员</span><span class="sxs-lookup"><span data-stu-id="3999c-109">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="3999c-110">方法</span><span class="sxs-lookup"><span data-stu-id="3999c-110">Methods</span></span>](#methods) | <span data-ttu-id="3999c-111">[enable](#enable)， [disable](#disable)， [getPossibleBreakpoints，](#getpossiblebreakpoints) [setBreakpointsActive，](#setbreakpointsactive) [setBreakpointByUrl，](#setbreakpointbyurl) [setBreakpoint，](#setbreakpoint) [removeBreakpoint，](#removebreakpoint) [stepOver，](#stepover) [stepInto，](#stepinto) [stepOut，](#stepout) [pause，](#pause) [resume，](#resume) [getScriptSource，](#getscriptsource) [setPauseOnExceptions，](#setpauseonexceptions) [evaluateOnCallFrame，](#evaluateoncallframe) [setVariableValue，](#setvariablevalue) [setBlackboxPatterns，](#setblackboxpatterns) [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="3999c-111">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |  
| [<span data-ttu-id="3999c-112">事件</span><span class="sxs-lookup"><span data-stu-id="3999c-112">Events</span></span>](#events) | <span data-ttu-id="3999c-113">[scriptParsed](#scriptparsed)， [breakpointResolved，](#breakpointresolved) [paused，](#paused) [resumed](#resumed)</span><span class="sxs-lookup"><span data-stu-id="3999c-113">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |  
| [<span data-ttu-id="3999c-114">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-114">Types</span></span>](#types) | <span data-ttu-id="3999c-115">[BreakpointId](#breakpointid)， [CallFrameId](#callframeid)， [Location](#location)， [BreakLocation](#breaklocation)， [CallFrame](#callframe)， [Scope](#scope)</span><span class="sxs-lookup"><span data-stu-id="3999c-115">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |  
| [<span data-ttu-id="3999c-116">依赖关系</span><span class="sxs-lookup"><span data-stu-id="3999c-116">Dependencies</span></span>](#dependencies) | [<span data-ttu-id="3999c-117">运行时</span><span class="sxs-lookup"><span data-stu-id="3999c-117">Runtime</span></span>](./runtime.md) |  

## <a name="methods"></a><span data-ttu-id="3999c-118">方法</span><span class="sxs-lookup"><span data-stu-id="3999c-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="3999c-119">“启用”</span><span class="sxs-lookup"><span data-stu-id="3999c-119">enable</span></span>  

<span data-ttu-id="3999c-120">为给定页面启用调试程序。</span><span class="sxs-lookup"><span data-stu-id="3999c-120">Enables debugger for the given page.</span></span>  <span data-ttu-id="3999c-121">在接收此命令的结果之前，客户端不应假定调试已启用。</span><span class="sxs-lookup"><span data-stu-id="3999c-121">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="3999c-122">“禁用”</span><span class="sxs-lookup"><span data-stu-id="3999c-122">disable</span></span>  

<span data-ttu-id="3999c-123">禁用给定页面的调试程序。</span><span class="sxs-lookup"><span data-stu-id="3999c-123">Disables debugger for given page.</span></span>  

&nbsp;  

---  

### <a name="getpossiblebreakpoints"></a><span data-ttu-id="3999c-124">getPossibleBreakpoints</span><span class="sxs-lookup"><span data-stu-id="3999c-124">getPossibleBreakpoints</span></span>  

<span data-ttu-id="3999c-125">返回断点的可能位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-125">Returns possible locations for breakpoint.</span></span>  <span data-ttu-id="3999c-126">start 和 end range 位置中的 scriptId 应相同。</span><span class="sxs-lookup"><span data-stu-id="3999c-126">scriptId in start and end range locations should be the same.</span></span>  

| <span data-ttu-id="3999c-127">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-127">Parameters</span></span> | <span data-ttu-id="3999c-128">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-128">Type</span></span> | <span data-ttu-id="3999c-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-129">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-130">start</span><span class="sxs-lookup"><span data-stu-id="3999c-130">start</span></span> | [<span data-ttu-id="3999c-131">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-131">Location</span></span>](#location) | <span data-ttu-id="3999c-132">搜索可能断点位置的范围开始。</span><span class="sxs-lookup"><span data-stu-id="3999c-132">Start of range to search possible breakpoint locations in.</span></span> |  
| <span data-ttu-id="3999c-133">结束</span><span class="sxs-lookup"><span data-stu-id="3999c-133">end</span></span> | [<span data-ttu-id="3999c-134">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-134">Location</span></span>](#location) | <span data-ttu-id="3999c-135">要搜索 \ (中可能断点位置的范围结束，但不包括\) 。</span><span class="sxs-lookup"><span data-stu-id="3999c-135">End of range to search possible breakpoint locations in \(excluding\).</span></span>  <span data-ttu-id="3999c-136">如果未指定，脚本的末尾将用作范围的末尾。</span><span class="sxs-lookup"><span data-stu-id="3999c-136">When not specified, end of scripts is used as end of range.</span></span> |  

| <span data-ttu-id="3999c-137">返回</span><span class="sxs-lookup"><span data-stu-id="3999c-137">Returns</span></span> | <span data-ttu-id="3999c-138">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-138">Type</span></span> | <span data-ttu-id="3999c-139">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-139">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-140">locations</span><span class="sxs-lookup"><span data-stu-id="3999c-140">locations</span></span> | [<span data-ttu-id="3999c-141">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="3999c-141">BreakLocation</span></span>](#breaklocation) | <span data-ttu-id="3999c-142">可能的断点位置的列表。</span><span class="sxs-lookup"><span data-stu-id="3999c-142">List of the possible breakpoint locations.</span></span> |  

---  

### <a name="setbreakpointsactive"></a><span data-ttu-id="3999c-143">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="3999c-143">setBreakpointsActive</span></span>  

<span data-ttu-id="3999c-144">激活/停用页面上的所有断点。</span><span class="sxs-lookup"><span data-stu-id="3999c-144">Activates / deactivates all breakpoints on the page.</span></span>  

| <span data-ttu-id="3999c-145">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-145">Parameters</span></span> | <span data-ttu-id="3999c-146">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-146">Type</span></span> | <span data-ttu-id="3999c-147">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-147">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-148">active</span><span class="sxs-lookup"><span data-stu-id="3999c-148">active</span></span> | `boolean` | <span data-ttu-id="3999c-149">断点活动状态的新值。</span><span class="sxs-lookup"><span data-stu-id="3999c-149">New value for breakpoints active state.</span></span> |  

---  

### <a name="setbreakpointbyurl"></a><span data-ttu-id="3999c-150">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="3999c-150">setBreakpointByUrl</span></span>  

<span data-ttu-id="3999c-151">设置由 URL 或 URL 正则表达式指定的给定位置的 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="3999c-151">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span>  <span data-ttu-id="3999c-152">发出此命令后，所有现有分析脚本都将在属性中解析和返回断 `locations` 点。</span><span class="sxs-lookup"><span data-stu-id="3999c-152">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in `locations` property.</span></span>  <span data-ttu-id="3999c-153">进一步匹配脚本分析将导致 `breakpointResolved` 后续事件发布。</span><span class="sxs-lookup"><span data-stu-id="3999c-153">Further matching script parsing will result in subsequent `breakpointResolved` events issued.</span></span>  <span data-ttu-id="3999c-154">此逻辑断点在重新加载页面时将生存下来。</span><span class="sxs-lookup"><span data-stu-id="3999c-154">This logical breakpoint will survive page reloads.</span></span>  

| <span data-ttu-id="3999c-155">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-155">Parameters</span></span> | <span data-ttu-id="3999c-156">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-156">Type</span></span> | <span data-ttu-id="3999c-157">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-157">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-158">lineNumber</span><span class="sxs-lookup"><span data-stu-id="3999c-158">lineNumber</span></span> | `integer` | <span data-ttu-id="3999c-159">要设置断点的行号。</span><span class="sxs-lookup"><span data-stu-id="3999c-159">Line number to set breakpoint at.</span></span> |  
| <span data-ttu-id="3999c-160">url \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-160">url  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-161">要设置断点的资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="3999c-161">URL of the resources to set breakpoint on.</span></span> |  
| <span data-ttu-id="3999c-162">urlRegex \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-162">urlRegex  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-163">要设置断点的资源 URL 的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="3999c-163">Regex pattern for the URLs of the resources to set breakpoints on.</span></span>  <span data-ttu-id="3999c-164">或者 `url` `urlRegex` 必须指定。</span><span class="sxs-lookup"><span data-stu-id="3999c-164">Either `url` or `urlRegex` must be specified.</span></span> |  
| <span data-ttu-id="3999c-165">columnNumber \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-165">columnNumber  \(optional\)</span></span> | `integer` | <span data-ttu-id="3999c-166">要设置断点的行中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="3999c-166">Offset in the line to set breakpoint at.</span></span> |  
| <span data-ttu-id="3999c-167">condition \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-167">condition  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-168">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="3999c-168">Expression to use as a breakpoint condition.</span></span>  <span data-ttu-id="3999c-169">指定此参数时，如果此表达式计算结果为 true，调试器将仅在断点停止。</span><span class="sxs-lookup"><span data-stu-id="3999c-169">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="3999c-170">返回</span><span class="sxs-lookup"><span data-stu-id="3999c-170">Returns</span></span> | <span data-ttu-id="3999c-171">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-171">Type</span></span> | <span data-ttu-id="3999c-172">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-172">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-173">breakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-173">breakpointId</span></span> | [<span data-ttu-id="3999c-174">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-174">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="3999c-175">创建的断点的 ID，供进一步参考。</span><span class="sxs-lookup"><span data-stu-id="3999c-175">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="3999c-176">locations</span><span class="sxs-lookup"><span data-stu-id="3999c-176">locations</span></span> | [<span data-ttu-id="3999c-177">位置[]</span><span class="sxs-lookup"><span data-stu-id="3999c-177">Location[]</span></span>](#location) | <span data-ttu-id="3999c-178">添加时此断点解析到的位置的列表。</span><span class="sxs-lookup"><span data-stu-id="3999c-178">List of the locations this breakpoint resolved into upon addition.</span></span> |  

---  

### <a name="setbreakpoint"></a><span data-ttu-id="3999c-179">setBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3999c-179">setBreakpoint</span></span>  

<span data-ttu-id="3999c-180">设置给定位置的 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="3999c-180">Sets JavaScript breakpoint at a given location.</span></span>  

| <span data-ttu-id="3999c-181">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-181">Parameters</span></span> | <span data-ttu-id="3999c-182">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-182">Type</span></span> | <span data-ttu-id="3999c-183">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-183">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-184">location</span><span class="sxs-lookup"><span data-stu-id="3999c-184">location</span></span> | [<span data-ttu-id="3999c-185">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-185">Location</span></span>](#location) | <span data-ttu-id="3999c-186">要设置断点的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-186">Location to set breakpoint in.</span></span> |  
| <span data-ttu-id="3999c-187">condition \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-187">condition  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-188">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="3999c-188">Expression to use as a breakpoint condition.</span></span>  <span data-ttu-id="3999c-189">指定此参数时，如果此表达式计算结果为 true，调试器将仅在断点停止。</span><span class="sxs-lookup"><span data-stu-id="3999c-189">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="3999c-190">返回</span><span class="sxs-lookup"><span data-stu-id="3999c-190">Returns</span></span> | <span data-ttu-id="3999c-191">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-191">Type</span></span> | <span data-ttu-id="3999c-192">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-192">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-193">breakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-193">breakpointId</span></span> | [<span data-ttu-id="3999c-194">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-194">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="3999c-195">创建的断点的 ID，供进一步参考。</span><span class="sxs-lookup"><span data-stu-id="3999c-195">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="3999c-196">actualLocation</span><span class="sxs-lookup"><span data-stu-id="3999c-196">actualLocation</span></span> | [<span data-ttu-id="3999c-197">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-197">Location</span></span>](#location) | <span data-ttu-id="3999c-198">解析到的断点的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-198">Location this breakpoint resolved into.</span></span> |  

---  

### <a name="removebreakpoint"></a><span data-ttu-id="3999c-199">removeBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3999c-199">removeBreakpoint</span></span>  

<span data-ttu-id="3999c-200">删除 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="3999c-200">Removes JavaScript breakpoint.</span></span>  

| <span data-ttu-id="3999c-201">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-201">Parameters</span></span> | <span data-ttu-id="3999c-202">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-202">Type</span></span> | <span data-ttu-id="3999c-203">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-203">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-204">breakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-204">breakpointId</span></span> | [<span data-ttu-id="3999c-205">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-205">BreakpointId</span></span>](#breakpointid) | &nbsp; |  

---  

### <a name="stepover"></a><span data-ttu-id="3999c-206">stepOver</span><span class="sxs-lookup"><span data-stu-id="3999c-206">stepOver</span></span>  

<span data-ttu-id="3999c-207">对语句的步骤。</span><span class="sxs-lookup"><span data-stu-id="3999c-207">Steps over the statement.</span></span>  

&nbsp;  

---  

### <a name="stepinto"></a><span data-ttu-id="3999c-208">stepInto</span><span class="sxs-lookup"><span data-stu-id="3999c-208">stepInto</span></span>  

<span data-ttu-id="3999c-209">进入函数调用。</span><span class="sxs-lookup"><span data-stu-id="3999c-209">Steps into the function call.</span></span>  

&nbsp;  

---  

### <a name="stepout"></a><span data-ttu-id="3999c-210">stepOut</span><span class="sxs-lookup"><span data-stu-id="3999c-210">stepOut</span></span>  

<span data-ttu-id="3999c-211">退出函数调用。</span><span class="sxs-lookup"><span data-stu-id="3999c-211">Steps out of the function call.</span></span>  

&nbsp;  

---  

### <a name="pause"></a><span data-ttu-id="3999c-212">pause</span><span class="sxs-lookup"><span data-stu-id="3999c-212">pause</span></span>  

<span data-ttu-id="3999c-213">停止下一个 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="3999c-213">Stops on the next JavaScript statement.</span></span>  

&nbsp;  

---  

### <a name="resume"></a><span data-ttu-id="3999c-214">resume</span><span class="sxs-lookup"><span data-stu-id="3999c-214">resume</span></span>  

<span data-ttu-id="3999c-215">恢复 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="3999c-215">Resumes JavaScript execution.</span></span>  

&nbsp;  

---  

### <a name="getscriptsource"></a><span data-ttu-id="3999c-216">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="3999c-216">getScriptSource</span></span>  

<span data-ttu-id="3999c-217">返回具有给定 ID 的脚本的源。</span><span class="sxs-lookup"><span data-stu-id="3999c-217">Returns source for the script with given ID.</span></span>  

| <span data-ttu-id="3999c-218">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-218">Parameters</span></span> | <span data-ttu-id="3999c-219">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-219">Type</span></span> | <span data-ttu-id="3999c-220">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-220">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-221">scriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-221">scriptId</span></span> | [<span data-ttu-id="3999c-222">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-222">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="3999c-223">要获取其源的脚本的 ID。</span><span class="sxs-lookup"><span data-stu-id="3999c-223">ID of the script to get source for.</span></span> |  
| <span data-ttu-id="3999c-224">返回</span><span class="sxs-lookup"><span data-stu-id="3999c-224">Returns</span></span> | <span data-ttu-id="3999c-225">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-225">Type</span></span> | <span data-ttu-id="3999c-226">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-226">Details</span></span> |  
|<span data-ttu-id="3999c-227">:---</span><span class="sxs-lookup"><span data-stu-id="3999c-227">:---</span></span> |<span data-ttu-id="3999c-228">:---</span><span class="sxs-lookup"><span data-stu-id="3999c-228">:---</span></span> |<span data-ttu-id="3999c-229">:---</span><span class="sxs-lookup"><span data-stu-id="3999c-229">:---</span></span> |  
| <span data-ttu-id="3999c-230">scriptSource</span><span class="sxs-lookup"><span data-stu-id="3999c-230">scriptSource</span></span> | `string` | <span data-ttu-id="3999c-231">脚本源。</span><span class="sxs-lookup"><span data-stu-id="3999c-231">Script source.</span></span> |  

---  

### <a name="setpauseonexceptions"></a><span data-ttu-id="3999c-232">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="3999c-232">setPauseOnExceptions</span></span>  

<span data-ttu-id="3999c-233">定义异常状态上的暂停。</span><span class="sxs-lookup"><span data-stu-id="3999c-233">Defines pause on exceptions state.</span></span>  <span data-ttu-id="3999c-234">可以设置为在所有异常、未捕获的异常或无异常上停止。</span><span class="sxs-lookup"><span data-stu-id="3999c-234">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span>  <span data-ttu-id="3999c-235">异常状态的初始暂停为 `none` 。</span><span class="sxs-lookup"><span data-stu-id="3999c-235">Initial pause on exceptions state is `none`.</span></span>  

| <span data-ttu-id="3999c-236">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-236">Parameters</span></span> | <span data-ttu-id="3999c-237">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-237">Type</span></span> | <span data-ttu-id="3999c-238">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-238">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-239">state</span><span class="sxs-lookup"><span data-stu-id="3999c-239">state</span></span> | `string` | <span data-ttu-id="3999c-240">暂停异常模式。</span><span class="sxs-lookup"><span data-stu-id="3999c-240">Pause on exceptions mode.</span></span>  <span data-ttu-id="3999c-241">允许的值  `none` ：、 `uncaught` 和</span><span class="sxs-lookup"><span data-stu-id="3999c-241">Allowed values:  `none`, `uncaught`, and</span></span> `all` |  

---  

### <a name="evaluateoncallframe"></a><span data-ttu-id="3999c-242">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="3999c-242">evaluateOnCallFrame</span></span>  

<span data-ttu-id="3999c-243">计算给定呼叫帧上的表达式。</span><span class="sxs-lookup"><span data-stu-id="3999c-243">Evaluates expression on a given call frame.</span></span>  

| <span data-ttu-id="3999c-244">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-244">Parameters</span></span> | <span data-ttu-id="3999c-245">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-245">Type</span></span> | <span data-ttu-id="3999c-246">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-246">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-247">callFrameId</span><span class="sxs-lookup"><span data-stu-id="3999c-247">callFrameId</span></span> | [<span data-ttu-id="3999c-248">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="3999c-248">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="3999c-249">要评估的呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="3999c-249">Call frame identifier to evaluate on.</span></span> |  
| <span data-ttu-id="3999c-250">表达式</span><span class="sxs-lookup"><span data-stu-id="3999c-250">expression</span></span> | `string` | <span data-ttu-id="3999c-251">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="3999c-251">Expression to evaluate.</span></span> |  
| <span data-ttu-id="3999c-252">返回</span><span class="sxs-lookup"><span data-stu-id="3999c-252">Returns</span></span> | <span data-ttu-id="3999c-253">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-253">Type</span></span> | <span data-ttu-id="3999c-254">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-254">Details</span></span> |  
|<span data-ttu-id="3999c-255">:---</span><span class="sxs-lookup"><span data-stu-id="3999c-255">:---</span></span> |<span data-ttu-id="3999c-256">:---</span><span class="sxs-lookup"><span data-stu-id="3999c-256">:---</span></span> |<span data-ttu-id="3999c-257">:---</span><span class="sxs-lookup"><span data-stu-id="3999c-257">:---</span></span> |  
| <span data-ttu-id="3999c-258">result</span><span class="sxs-lookup"><span data-stu-id="3999c-258">result</span></span> | [<span data-ttu-id="3999c-259">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="3999c-259">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="3999c-260">评估结果的对象包装。</span><span class="sxs-lookup"><span data-stu-id="3999c-260">Object wrapper for the evaluation result.</span></span> |  

---  

### <a name="setvariablevalue"></a><span data-ttu-id="3999c-261">setVariableValue</span><span class="sxs-lookup"><span data-stu-id="3999c-261">setVariableValue</span></span>  

<span data-ttu-id="3999c-262">更改调用框内变量的值。</span><span class="sxs-lookup"><span data-stu-id="3999c-262">Changes value of variable in a callframe.</span></span>  <span data-ttu-id="3999c-263">不支持基于对象的作用域，必须手动进行可变。</span><span class="sxs-lookup"><span data-stu-id="3999c-263">Object-based scopes are not supported and must be mutated manually.</span></span>  

| <span data-ttu-id="3999c-264">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-264">Parameters</span></span> | <span data-ttu-id="3999c-265">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-265">Type</span></span> | <span data-ttu-id="3999c-266">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-266">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-267">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="3999c-267">scopeNumber</span></span> | `integer` | <span data-ttu-id="3999c-268">范围链中列出的基于 0 的范围数。</span><span class="sxs-lookup"><span data-stu-id="3999c-268">0-based number of scope as was listed in scope chain.</span></span>  <span data-ttu-id="3999c-269">仅 `local` `closure` 允许 ， `catch` 和范围类型。</span><span class="sxs-lookup"><span data-stu-id="3999c-269">Only `local`, `closure`, and `catch` scope types are allowed.</span></span>  <span data-ttu-id="3999c-270">可以手动操作其他范围。</span><span class="sxs-lookup"><span data-stu-id="3999c-270">Other scopes could be manipulated manually.</span></span> |  
| <span data-ttu-id="3999c-271">variableName</span><span class="sxs-lookup"><span data-stu-id="3999c-271">variableName</span></span> | `string` | <span data-ttu-id="3999c-272">变量名称。</span><span class="sxs-lookup"><span data-stu-id="3999c-272">Variable name.</span></span> |  
| <span data-ttu-id="3999c-273">newValue</span><span class="sxs-lookup"><span data-stu-id="3999c-273">newValue</span></span> | [<span data-ttu-id="3999c-274">Runtime.CallArgument</span><span class="sxs-lookup"><span data-stu-id="3999c-274">Runtime.CallArgument</span></span>](./runtime.md#callargument) | <span data-ttu-id="3999c-275">新变量值。</span><span class="sxs-lookup"><span data-stu-id="3999c-275">New variable value.</span></span> |  
| <span data-ttu-id="3999c-276">callFrameId</span><span class="sxs-lookup"><span data-stu-id="3999c-276">callFrameId</span></span> | [<span data-ttu-id="3999c-277">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="3999c-277">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="3999c-278">包含变量的调用框的 ID。</span><span class="sxs-lookup"><span data-stu-id="3999c-278">ID of callframe that holds variable.</span></span> |  

---  

### <a name="setblackboxpatterns"></a><span data-ttu-id="3999c-279">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="3999c-279">setBlackboxPatterns</span></span>  

<span data-ttu-id="3999c-280">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-280">**Experimental**.</span></span>  <span data-ttu-id="3999c-281">将以前的黑箱模式替换为传递的黑色框模式。</span><span class="sxs-lookup"><span data-stu-id="3999c-281">Replace previous blackbox patterns with passed ones.</span></span>  <span data-ttu-id="3999c-282">强制后端在 URL 与其中一种模式匹配的脚本中跳过单步执行/暂停。</span><span class="sxs-lookup"><span data-stu-id="3999c-282">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span>  <span data-ttu-id="3999c-283">调试程序将尝试通过执行多次来保留黑盒脚本，如果失败 `step in` ，最后 `step out` 将采用此脚本。</span><span class="sxs-lookup"><span data-stu-id="3999c-283">The debugger will try to leave blackboxed script by performing `step in` several times, finally resorting to `step out` if unsuccessful.</span></span>  

| <span data-ttu-id="3999c-284">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-284">Parameters</span></span> | <span data-ttu-id="3999c-285">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-285">Type</span></span> | <span data-ttu-id="3999c-286">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-286">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-287">模式</span><span class="sxs-lookup"><span data-stu-id="3999c-287">patterns</span></span> | `string[]` | <span data-ttu-id="3999c-288">将用于检查脚本 URL 的 blackbox 状态正则表达式的数组。</span><span class="sxs-lookup"><span data-stu-id="3999c-288">Array of regexps that will be used to check script url for blackbox state.</span></span> |  

---  

### <a name="mssetdebuggerpropertyvalue"></a><span data-ttu-id="3999c-289">msSetDebuggerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="3999c-289">msSetDebuggerPropertyValue</span></span>  

<span data-ttu-id="3999c-290">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-290">**Experimental**.</span></span>  <span data-ttu-id="3999c-291">Microsoft：将指定的调试器属性设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="3999c-291">Microsoft:  Sets the specified debugger property to the specified value.</span></span>  

| <span data-ttu-id="3999c-292">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-292">Parameters</span></span> | <span data-ttu-id="3999c-293">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-293">Type</span></span> | <span data-ttu-id="3999c-294">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-294">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-295">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="3999c-295">debuggerPropertyId</span></span> | `string` | <span data-ttu-id="3999c-296">Microsoft：属性 ID \ (即 msDebuggerPropertyId\) 设置。</span><span class="sxs-lookup"><span data-stu-id="3999c-296">Microsoft: The property ID \(i.e. msDebuggerPropertyId\) to set.</span></span> |  
| <span data-ttu-id="3999c-297">newValue</span><span class="sxs-lookup"><span data-stu-id="3999c-297">newValue</span></span> | `string` | &nbsp; |  

---  

## <a name="events"></a><span data-ttu-id="3999c-298">事件</span><span class="sxs-lookup"><span data-stu-id="3999c-298">Events</span></span>  

### <a name="scriptparsed"></a><span data-ttu-id="3999c-299">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="3999c-299">scriptParsed</span></span>  

<span data-ttu-id="3999c-300">分析脚本时触发。</span><span class="sxs-lookup"><span data-stu-id="3999c-300">Fired when the script is parsed.</span></span>  <span data-ttu-id="3999c-301">启用调试程序时，还会针对所有已知和未创建脚本触发此事件。</span><span class="sxs-lookup"><span data-stu-id="3999c-301">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>  

| <span data-ttu-id="3999c-302">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-302">Parameters</span></span> | <span data-ttu-id="3999c-303">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-303">Type</span></span> | <span data-ttu-id="3999c-304">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-304">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-305">scriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-305">scriptId</span></span> | [<span data-ttu-id="3999c-306">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-306">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="3999c-307">分析的脚本的标识符。</span><span class="sxs-lookup"><span data-stu-id="3999c-307">Identifier of the script parsed.</span></span> |  
| <span data-ttu-id="3999c-308">url</span><span class="sxs-lookup"><span data-stu-id="3999c-308">url</span></span> | `string` | <span data-ttu-id="3999c-309">解析为 \ (\) 的脚本的 URL 或) 。</span><span class="sxs-lookup"><span data-stu-id="3999c-309">URL or name of the script parsed \(if any\).</span></span> |  
| <span data-ttu-id="3999c-310">startLine</span><span class="sxs-lookup"><span data-stu-id="3999c-310">startLine</span></span> | `integer` | <span data-ttu-id="3999c-311">具有给定 URL 的脚本在资源中的行偏移量\ (脚本标记\) 。</span><span class="sxs-lookup"><span data-stu-id="3999c-311">Line offset of the script within the resource with given URL \(for script tags\).</span></span> |  
| <span data-ttu-id="3999c-312">startColumn</span><span class="sxs-lookup"><span data-stu-id="3999c-312">startColumn</span></span> | `integer` | <span data-ttu-id="3999c-313">具有给定 URL 的资源中的脚本的列偏移量。</span><span class="sxs-lookup"><span data-stu-id="3999c-313">Column offset of the script within the resource with given URL.</span></span> |  
| <span data-ttu-id="3999c-314">endLine</span><span class="sxs-lookup"><span data-stu-id="3999c-314">endLine</span></span> | `integer` | <span data-ttu-id="3999c-315">脚本的最后一行。</span><span class="sxs-lookup"><span data-stu-id="3999c-315">Last line of the script.</span></span> |  
| <span data-ttu-id="3999c-316">endColumn</span><span class="sxs-lookup"><span data-stu-id="3999c-316">endColumn</span></span> | `integer` | <span data-ttu-id="3999c-317">脚本最后一行的长度。</span><span class="sxs-lookup"><span data-stu-id="3999c-317">Length of the last line of the script.</span></span> |  
| <span data-ttu-id="3999c-318">executionContextId</span><span class="sxs-lookup"><span data-stu-id="3999c-318">executionContextId</span></span> | [<span data-ttu-id="3999c-319">Runtime.ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="3999c-319">Runtime.ExecutionContextId</span></span>](./runtime.md#executioncontextid) | <span data-ttu-id="3999c-320">指定脚本创建上下文。</span><span class="sxs-lookup"><span data-stu-id="3999c-320">Specifies script creation context.</span></span> |  
| <span data-ttu-id="3999c-321">sourceMapURL \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-321">sourceMapURL  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-322">与脚本映射关联的源 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="3999c-322">URL of source map associated with script (if any).</span></span> |  
| <span data-ttu-id="3999c-323">length \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-323">length  \(optional\)</span></span> | `integer` | <span data-ttu-id="3999c-324">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-324">**Experimental**.</span></span>  <span data-ttu-id="3999c-325">此脚本长度。</span><span class="sxs-lookup"><span data-stu-id="3999c-325">This script length.</span></span> |  
| <span data-ttu-id="3999c-326">msParentId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-326">msParentId  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-327">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-327">**Experimental**.</span></span>  <span data-ttu-id="3999c-328">这是父文档 ID。</span><span class="sxs-lookup"><span data-stu-id="3999c-328">This is the parent document ID.</span></span> |  
| <span data-ttu-id="3999c-329">msMimeType \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-329">msMimeType  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-330">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-330">**Experimental**.</span></span>  <span data-ttu-id="3999c-331">这是 mime 类型。</span><span class="sxs-lookup"><span data-stu-id="3999c-331">This is the mime type.</span></span> |  
| <span data-ttu-id="3999c-332">msIsDynamicCode \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-332">msIsDynamicCode  \(optional\)</span></span> | `boolean` | <span data-ttu-id="3999c-333">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-333">**Experimental**.</span></span>  <span data-ttu-id="3999c-334">这指示它是否为动态代码。</span><span class="sxs-lookup"><span data-stu-id="3999c-334">This indicates whether it is dynamic code.</span></span> |  
| <span data-ttu-id="3999c-335">msLongDocumentId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-335">msLongDocumentId  \(optional\)</span></span> | `integer` | <span data-ttu-id="3999c-336">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-336">**Experimental**.</span></span>  <span data-ttu-id="3999c-337">这是长文档 ID。</span><span class="sxs-lookup"><span data-stu-id="3999c-337">This is the long document ID.</span></span> |  

---  

### <a name="breakpointresolved"></a><span data-ttu-id="3999c-338">breakpointResolved</span><span class="sxs-lookup"><span data-stu-id="3999c-338">breakpointResolved</span></span>  

<span data-ttu-id="3999c-339">当断点解析为实际脚本和位置时触发。</span><span class="sxs-lookup"><span data-stu-id="3999c-339">Fired when breakpoint is resolved to an actual script and location.</span></span>  

| <span data-ttu-id="3999c-340">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-340">Parameters</span></span> | <span data-ttu-id="3999c-341">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-341">Type</span></span> | <span data-ttu-id="3999c-342">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-342">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-343">breakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-343">breakpointId</span></span> | [<span data-ttu-id="3999c-344">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="3999c-344">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="3999c-345">断点唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3999c-345">Breakpoint unique identifier.</span></span> |  
| <span data-ttu-id="3999c-346">location</span><span class="sxs-lookup"><span data-stu-id="3999c-346">location</span></span> | [<span data-ttu-id="3999c-347">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-347">Location</span></span>](#location) | <span data-ttu-id="3999c-348">实际断点位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-348">Actual breakpoint location.</span></span> |  
| <span data-ttu-id="3999c-349">msLength \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-349">msLength  \(optional\)</span></span> | `integer` | <span data-ttu-id="3999c-350">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-350">**Experimental**.</span></span>  <span data-ttu-id="3999c-351">Microsoft：代码 \ (长度，即断点) 字符数\</span><span class="sxs-lookup"><span data-stu-id="3999c-351">Microsoft:  Length of code \(i.e. number of characters\) at the breakpoint location.</span></span> |  

---  

### <a name="paused"></a><span data-ttu-id="3999c-352">已暂停</span><span class="sxs-lookup"><span data-stu-id="3999c-352">paused</span></span>  

<span data-ttu-id="3999c-353">当调试器中断断点或异常时触发。</span><span class="sxs-lookup"><span data-stu-id="3999c-353">Fired when the debuggers breaks for a breakpoint or exception.</span></span>  

| <span data-ttu-id="3999c-354">参数</span><span class="sxs-lookup"><span data-stu-id="3999c-354">Parameters</span></span> | <span data-ttu-id="3999c-355">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-355">Type</span></span> | <span data-ttu-id="3999c-356">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-356">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-357">callFrames</span><span class="sxs-lookup"><span data-stu-id="3999c-357">callFrames</span></span> | [<span data-ttu-id="3999c-358">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="3999c-358">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="3999c-359">调用调试器停止的堆栈。</span><span class="sxs-lookup"><span data-stu-id="3999c-359">Call stack the debugger stopped on.</span></span> |  
| <span data-ttu-id="3999c-360">reason</span><span class="sxs-lookup"><span data-stu-id="3999c-360">reason</span></span> | `string` | <span data-ttu-id="3999c-361">暂停原因。</span><span class="sxs-lookup"><span data-stu-id="3999c-361">Pause reason.</span></span>  <span data-ttu-id="3999c-362">允许的值  `breakpoint` `step` `exception` ：、、和</span><span class="sxs-lookup"><span data-stu-id="3999c-362">Allowed values:  `breakpoint`, `step`, `exception`, and</span></span> `other` |  
| <span data-ttu-id="3999c-363">data \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-363">data  \(optional\)</span></span> | `object` | <span data-ttu-id="3999c-364">包含特定于中断的辅助属性的对象。</span><span class="sxs-lookup"><span data-stu-id="3999c-364">Object containing break-specific auxiliary properties.</span></span> |  
| <span data-ttu-id="3999c-365">hitBreakpoints \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-365">hitBreakpoints  \(optional\)</span></span> | `string[]` | <span data-ttu-id="3999c-366">命中断点 ID</span><span class="sxs-lookup"><span data-stu-id="3999c-366">Hit breakpoints IDs</span></span> |  

---  

### <a name="resumed"></a><span data-ttu-id="3999c-367">恢复</span><span class="sxs-lookup"><span data-stu-id="3999c-367">resumed</span></span>  

<span data-ttu-id="3999c-368">在调试程序恢复执行时触发。</span><span class="sxs-lookup"><span data-stu-id="3999c-368">Fired when the debugger resumes execution.</span></span>  

&nbsp;  

---  

## <a name="types"></a><span data-ttu-id="3999c-369">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-369">Types</span></span>  

### <a name="breakpointid-string"></a><span data-ttu-id="3999c-370">BreakpointId 字符串</span><span class="sxs-lookup"><span data-stu-id="3999c-370">BreakpointId string</span></span>  

<a name="breakpointid"></a>  

<span data-ttu-id="3999c-371">断点标识符。</span><span class="sxs-lookup"><span data-stu-id="3999c-371">Breakpoint identifier.</span></span>  

&nbsp;  

---  

### <a name="callframeid-string"></a><span data-ttu-id="3999c-372">CallFrameId 字符串</span><span class="sxs-lookup"><span data-stu-id="3999c-372">CallFrameId string</span></span>  

<a name="callframeid"></a>  

<span data-ttu-id="3999c-373">呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="3999c-373">Call frame identifier.</span></span>  

&nbsp;  

---  

### <a name="location-object"></a><span data-ttu-id="3999c-374">Location 对象</span><span class="sxs-lookup"><span data-stu-id="3999c-374">Location object</span></span>  

<a name="location"></a>  

<span data-ttu-id="3999c-375">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-375">Location in the source code.</span></span>  

| <span data-ttu-id="3999c-376">属性</span><span class="sxs-lookup"><span data-stu-id="3999c-376">Properties</span></span> | <span data-ttu-id="3999c-377">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-377">Type</span></span> | <span data-ttu-id="3999c-378">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-378">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-379">scriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-379">scriptId</span></span> | [<span data-ttu-id="3999c-380">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-380">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="3999c-381">报告在 中的脚本标识符 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="3999c-381">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="3999c-382">lineNumber</span><span class="sxs-lookup"><span data-stu-id="3999c-382">lineNumber</span></span> | `integer` | <span data-ttu-id="3999c-383">脚本 \ (0\) 中的行) 。</span><span class="sxs-lookup"><span data-stu-id="3999c-383">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="3999c-384">columnNumber \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-384">columnNumber  \(optional\)</span></span> | `integer` | <span data-ttu-id="3999c-385">脚本 \ (0\) 中的列号。</span><span class="sxs-lookup"><span data-stu-id="3999c-385">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="3999c-386">msLength</span><span class="sxs-lookup"><span data-stu-id="3999c-386">msLength</span></span> | `integer` | <span data-ttu-id="3999c-387">Microsoft：代码 \ (，即在此调用帧) 字符数\字符数。</span><span class="sxs-lookup"><span data-stu-id="3999c-387">Microsoft: Length of code \(i.e. number of characters\) at this call frame.</span></span> |  

---  

### <a name="breaklocation-object"></a><span data-ttu-id="3999c-388">BreakLocation 对象</span><span class="sxs-lookup"><span data-stu-id="3999c-388">BreakLocation object</span></span>  

<a name="breaklocation"></a>  

<span data-ttu-id="3999c-389">中断源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-389">Break location in the source code.</span></span>  

| <span data-ttu-id="3999c-390">属性</span><span class="sxs-lookup"><span data-stu-id="3999c-390">Properties</span></span> | <span data-ttu-id="3999c-391">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-391">Type</span></span> | <span data-ttu-id="3999c-392">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-392">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-393">scriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-393">scriptId</span></span> | [<span data-ttu-id="3999c-394">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="3999c-394">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="3999c-395">中报告的脚本标识符 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="3999c-395">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="3999c-396">lineNumber</span><span class="sxs-lookup"><span data-stu-id="3999c-396">lineNumber</span></span> | `integer` | <span data-ttu-id="3999c-397">脚本 \ (0\) 中的行) 。</span><span class="sxs-lookup"><span data-stu-id="3999c-397">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="3999c-398">columnNumber \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-398">columnNumber  \(optional\)</span></span> | `integer` | <span data-ttu-id="3999c-399">脚本 \ (0\) 中的列号。</span><span class="sxs-lookup"><span data-stu-id="3999c-399">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="3999c-400">msLength</span><span class="sxs-lookup"><span data-stu-id="3999c-400">msLength</span></span> | `integer` | <span data-ttu-id="3999c-401">Microsoft：代码 \ (，即在此调用帧) 字符数\字符数。</span><span class="sxs-lookup"><span data-stu-id="3999c-401">Microsoft:  Length of code \(i.e. number of characters\) at this call frame.</span></span> |  
| <span data-ttu-id="3999c-402">type \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-402">type  \(optional\)</span></span> | `string` | <span data-ttu-id="3999c-403">允许的值  `debuggerStatement` ：、 `call` 和</span><span class="sxs-lookup"><span data-stu-id="3999c-403">Allowed values:  `debuggerStatement`, `call`, and</span></span> `return` |  

---  

### <a name="callframe-object"></a><span data-ttu-id="3999c-404">CallFrame 对象</span><span class="sxs-lookup"><span data-stu-id="3999c-404">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="3999c-405">JavaScript 调用帧。</span><span class="sxs-lookup"><span data-stu-id="3999c-405">JavaScript call frame.</span></span>  <span data-ttu-id="3999c-406">构成调用堆栈的调用帧数组。</span><span class="sxs-lookup"><span data-stu-id="3999c-406">Array of call frames form the call stack.</span></span>  

| <span data-ttu-id="3999c-407">属性</span><span class="sxs-lookup"><span data-stu-id="3999c-407">Properties</span></span> | <span data-ttu-id="3999c-408">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-408">Type</span></span> | <span data-ttu-id="3999c-409">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-409">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-410">callFrameId</span><span class="sxs-lookup"><span data-stu-id="3999c-410">callFrameId</span></span> | [<span data-ttu-id="3999c-411">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="3999c-411">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="3999c-412">呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="3999c-412">Call frame identifier.</span></span>  <span data-ttu-id="3999c-413">此标识符仅在调试器暂停时有效。</span><span class="sxs-lookup"><span data-stu-id="3999c-413">This identifier is only valid while the debugger is paused.</span></span> |  
| <span data-ttu-id="3999c-414">functionName</span><span class="sxs-lookup"><span data-stu-id="3999c-414">functionName</span></span> | `string` | <span data-ttu-id="3999c-415">在此调用帧上调用的 JavaScript 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="3999c-415">Name of the JavaScript function called on this call frame.</span></span> |  
| <span data-ttu-id="3999c-416">functionLocation \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-416">functionLocation  \(optional\)</span></span> | [<span data-ttu-id="3999c-417">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-417">Location</span></span>](#location) | <span data-ttu-id="3999c-418">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="3999c-418">**Experimental**.</span></span>  <span data-ttu-id="3999c-419">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-419">Location in the source code.</span></span> |  
| <span data-ttu-id="3999c-420">location</span><span class="sxs-lookup"><span data-stu-id="3999c-420">location</span></span> | [<span data-ttu-id="3999c-421">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-421">Location</span></span>](#location) | <span data-ttu-id="3999c-422">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-422">Location in the source code.</span></span> |  
| <span data-ttu-id="3999c-423">url</span><span class="sxs-lookup"><span data-stu-id="3999c-423">url</span></span> | `string` | <span data-ttu-id="3999c-424">JavaScript 脚本名称或 url。</span><span class="sxs-lookup"><span data-stu-id="3999c-424">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="3999c-425">scopeChain</span><span class="sxs-lookup"><span data-stu-id="3999c-425">scopeChain</span></span> | [<span data-ttu-id="3999c-426">范围[]</span><span class="sxs-lookup"><span data-stu-id="3999c-426">Scope[]</span></span>](#scope) | <span data-ttu-id="3999c-427">此呼叫帧的范围链。</span><span class="sxs-lookup"><span data-stu-id="3999c-427">Scope chain for this call frame.</span></span> |  
| <span data-ttu-id="3999c-428">this</span><span class="sxs-lookup"><span data-stu-id="3999c-428">this</span></span> | [<span data-ttu-id="3999c-429">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="3999c-429">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | `this` <span data-ttu-id="3999c-430">对象。</span><span class="sxs-lookup"><span data-stu-id="3999c-430">object for this call frame.</span></span> |  
| <span data-ttu-id="3999c-431">returnValue \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-431">returnValue  \(optional\)</span></span> | [<span data-ttu-id="3999c-432">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="3999c-432">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="3999c-433">如果函数位于返回点，则返回的值。</span><span class="sxs-lookup"><span data-stu-id="3999c-433">The value being returned, if the function is at return point.</span></span> |  

---  

### <a name="scope-object"></a><span data-ttu-id="3999c-434">Scope 对象</span><span class="sxs-lookup"><span data-stu-id="3999c-434">Scope object</span></span>  

<a name="scope"></a>  

<span data-ttu-id="3999c-435">范围说明。</span><span class="sxs-lookup"><span data-stu-id="3999c-435">Scope description.</span></span>  

| <span data-ttu-id="3999c-436">属性</span><span class="sxs-lookup"><span data-stu-id="3999c-436">Properties</span></span> | <span data-ttu-id="3999c-437">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-437">Type</span></span> | <span data-ttu-id="3999c-438">详细信息</span><span class="sxs-lookup"><span data-stu-id="3999c-438">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="3999c-439">类型</span><span class="sxs-lookup"><span data-stu-id="3999c-439">type</span></span> | `string` | <span data-ttu-id="3999c-440">范围类型。</span><span class="sxs-lookup"><span data-stu-id="3999c-440">Scope type.</span></span>  <span data-ttu-id="3999c-441">允许的值  `global` `local` `with` ：、、、、、 `closure` `catch` `block` `script` `eval` 和</span><span class="sxs-lookup"><span data-stu-id="3999c-441">Allowed values:  `global`, `local`, `with`, `closure`, `catch`, `block`, `script`, `eval`, and</span></span> `module` |  
| <span data-ttu-id="3999c-442">object</span><span class="sxs-lookup"><span data-stu-id="3999c-442">object</span></span> | [<span data-ttu-id="3999c-443">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="3999c-443">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="3999c-444">表示范围的对象。</span><span class="sxs-lookup"><span data-stu-id="3999c-444">Object representing the scope.</span></span>  <span data-ttu-id="3999c-445">对于和范围，它表示实际对象;对于其余范围，它是人工临时对象枚举范围变量 `global` `with` 作为其属性。</span><span class="sxs-lookup"><span data-stu-id="3999c-445">For `global` and `with` scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span> |  
| <span data-ttu-id="3999c-446">name \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-446">name  \(optional\)</span></span> | `string` | &nbsp; |  
| <span data-ttu-id="3999c-447">startLocation \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-447">startLocation  \(optional\)</span></span> | [<span data-ttu-id="3999c-448">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-448">Location</span></span>](#location) | <span data-ttu-id="3999c-449">范围开始的源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-449">Location in the source code where scope starts.</span></span> |  
| <span data-ttu-id="3999c-450">endLocation \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="3999c-450">endLocation  \(optional\)</span></span> | [<span data-ttu-id="3999c-451">位置</span><span class="sxs-lookup"><span data-stu-id="3999c-451">Location</span></span>](#location) | <span data-ttu-id="3999c-452">范围结束的源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="3999c-452">Location in the source code where scope ends.</span></span> |  

---  

## <a name="dependencies"></a><span data-ttu-id="3999c-453">依赖关系</span><span class="sxs-lookup"><span data-stu-id="3999c-453">Dependencies</span></span>  

[<span data-ttu-id="3999c-454">运行时</span><span class="sxs-lookup"><span data-stu-id="3999c-454">Runtime</span></span>](./runtime.md)  
