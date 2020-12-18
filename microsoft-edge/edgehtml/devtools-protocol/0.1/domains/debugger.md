---
description: DevTools 协议版本 0.1 (调试) EdgeHTML 协议参考。 调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐步执行、探索堆栈跟踪等。
title: '调试器域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/16/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5160e6e69ec76f8c584f1bdb969464d805c7afa7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232474"
---
# <span data-ttu-id="2c6d7-105">调试器域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="2c6d7-105">Debugger Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  
  
<span data-ttu-id="2c6d7-106">调试器域公开 JavaScript 调试功能。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-106">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="2c6d7-107">它允许设置和删除断点、逐步执行、探索堆栈跟踪等。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="2c6d7-108">方法</span><span class="sxs-lookup"><span data-stu-id="2c6d7-108">Methods</span></span>**](#methods) | <span data-ttu-id="2c6d7-109">[enable](#enable)， [disable](#disable)， [getPossibleBreakpoints，](#getpossiblebreakpoints) [setBreakpointsActive，](#setbreakpointsactive) [setBreakpointByUrl，](#setbreakpointbyurl) [setBreakpoint，](#setbreakpoint) [removeBreakpoint，](#removebreakpoint) [stepOver，](#stepover) [stepInto，](#stepinto) [stepOut，](#stepout) [pause，](#pause) [resume，](#resume) [getScriptSource，](#getscriptsource) [setPauseOnExceptions，](#setpauseonexceptions) [evaluateOnCallFrame，](#evaluateoncallframe) [setVariableValue](#setvariablevalue)， [setBlackboxPatterns，](#setblackboxpatterns) [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="2c6d7-109">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |
| [**<span data-ttu-id="2c6d7-110">事件</span><span class="sxs-lookup"><span data-stu-id="2c6d7-110">Events</span></span>**](#events) | <span data-ttu-id="2c6d7-111">[scriptParsed](#scriptparsed)， [breakpointResolved，](#breakpointresolved) [paused，](#paused) [resumed](#resumed)</span><span class="sxs-lookup"><span data-stu-id="2c6d7-111">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |
| [**<span data-ttu-id="2c6d7-112">类型</span><span class="sxs-lookup"><span data-stu-id="2c6d7-112">Types</span></span>**](#types) | <span data-ttu-id="2c6d7-113">[BreakpointId](#breakpointid)， [CallFrameId](#callframeid)， [Location](#location)， [BreakLocation](#breaklocation)， [CallFrame](#callframe)， [Scope](#scope)</span><span class="sxs-lookup"><span data-stu-id="2c6d7-113">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |
| [**<span data-ttu-id="2c6d7-114">依赖关系</span><span class="sxs-lookup"><span data-stu-id="2c6d7-114">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="2c6d7-115">运行时</span><span class="sxs-lookup"><span data-stu-id="2c6d7-115">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="2c6d7-116">方法</span><span class="sxs-lookup"><span data-stu-id="2c6d7-116">Methods</span></span>

### <span data-ttu-id="2c6d7-117">“启用”</span><span class="sxs-lookup"><span data-stu-id="2c6d7-117">enable</span></span>
<span data-ttu-id="2c6d7-118">为给定页面启用调试程序。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-118">Enables debugger for the given page.</span></span> <span data-ttu-id="2c6d7-119">在接收到此命令的结果之前，客户端不应假定已启用调试。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-119">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>


---

### <span data-ttu-id="2c6d7-120">“禁用”</span><span class="sxs-lookup"><span data-stu-id="2c6d7-120">disable</span></span>
<span data-ttu-id="2c6d7-121">禁用给定页面的调试程序。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-121">Disables debugger for given page.</span></span>


---

### <span data-ttu-id="2c6d7-122">getPossibleBreakpoints</span><span class="sxs-lookup"><span data-stu-id="2c6d7-122">getPossibleBreakpoints</span></span>
<span data-ttu-id="2c6d7-123">返回断点可能的位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-123">Returns possible locations for breakpoint.</span></span> <span data-ttu-id="2c6d7-124">start 和 end range 位置中的 scriptId 应相同。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-124">scriptId in start and end range locations should be the same.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-125">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-125">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-126">start</span><span class="sxs-lookup"><span data-stu-id="2c6d7-126">start</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-127">要搜索可能的断点位置的范围开始。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-127">Start of range to search possible breakpoint locations in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-128">结束</span><span class="sxs-lookup"><span data-stu-id="2c6d7-128">end</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-129">要搜索可能断点位置的范围结束， (排除) 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-129">End of range to search possible breakpoint locations in (excluding).</span></span> <span data-ttu-id="2c6d7-130">如果未指定，脚本的末尾将用作范围的末尾。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-130">When not specified, end of scripts is used as end of range.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-131">返回</span><span class="sxs-lookup"><span data-stu-id="2c6d7-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-132">locations</span><span class="sxs-lookup"><span data-stu-id="2c6d7-132">locations</span></span></td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td><span data-ttu-id="2c6d7-133">可能的断点位置的列表。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-133">List of the possible breakpoint locations.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-134">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="2c6d7-134">setBreakpointsActive</span></span>
<span data-ttu-id="2c6d7-135">激活/停用页面上的所有断点。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-135">Activates / deactivates all breakpoints on the page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-136">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-136">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-137">active</span><span class="sxs-lookup"><span data-stu-id="2c6d7-137">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2c6d7-138">断点活动状态的新值。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-138">New value for breakpoints active state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-139">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="2c6d7-139">setBreakpointByUrl</span></span>
<span data-ttu-id="2c6d7-140">设置由 URL 或 URL 正则表达式指定的给定位置的 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-140">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span> <span data-ttu-id="2c6d7-141">发出此命令后，所有现有已分析脚本都将解析断点，并返回属性 <code>locations</code> 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-141">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in <code>locations</code> property.</span></span> <span data-ttu-id="2c6d7-142">进一步匹配脚本分析将生成 <code>breakpointResolved</code> 后续事件。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-142">Further matching script parsing will result in subsequent <code>breakpointResolved</code> events issued.</span></span> <span data-ttu-id="2c6d7-143">此逻辑断点在重新加载页面时将生存下来。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-143">This logical breakpoint will survive page reloads.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-144">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-144">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-145">lineNumber</span><span class="sxs-lookup"><span data-stu-id="2c6d7-145">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-146">要设置断点的行号。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-146">Line number to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-147">url</span><span class="sxs-lookup"><span data-stu-id="2c6d7-147">url</span></span> <br/> <i><span data-ttu-id="2c6d7-148">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-148">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-149">要设置断点的资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-149">URL of the resources to set breakpoint on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-150">urlRegex</span><span class="sxs-lookup"><span data-stu-id="2c6d7-150">urlRegex</span></span> <br/> <i><span data-ttu-id="2c6d7-151">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-151">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-152">要设置断点的资源 URL 的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-152">Regex pattern for the URLs of the resources to set breakpoints on.</span></span> <span data-ttu-id="2c6d7-153">指定 <code>url</code> 或 <code>urlRegex</code> 必须指定。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-153">Either <code>url</code> or <code>urlRegex</code> must be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-154">columnNumber</span><span class="sxs-lookup"><span data-stu-id="2c6d7-154">columnNumber</span></span> <br/> <i><span data-ttu-id="2c6d7-155">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-155">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-156">要设置断点的行中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-156">Offset in the line to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-157">condition</span><span class="sxs-lookup"><span data-stu-id="2c6d7-157">condition</span></span> <br/> <i><span data-ttu-id="2c6d7-158">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-158">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-159">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-159">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="2c6d7-160">指定此表达式时，如果此表达式计算结果为 true，调试器将仅在断点停止。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-160">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-161">返回</span><span class="sxs-lookup"><span data-stu-id="2c6d7-161">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-162">breakpointId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-162">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="2c6d7-163">创建的断点的 ID，供进一步参考。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-163">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-164">locations</span><span class="sxs-lookup"><span data-stu-id="2c6d7-164">locations</span></span></td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td><span data-ttu-id="2c6d7-165">添加时此断点解析到的位置列表。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-165">List of the locations this breakpoint resolved into upon addition.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-166">setBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2c6d7-166">setBreakpoint</span></span>
<span data-ttu-id="2c6d7-167">设置给定位置的 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-167">Sets JavaScript breakpoint at a given location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-168">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-168">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-169">location</span><span class="sxs-lookup"><span data-stu-id="2c6d7-169">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-170">要设置断点的位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-170">Location to set breakpoint in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-171">condition</span><span class="sxs-lookup"><span data-stu-id="2c6d7-171">condition</span></span> <br/> <i><span data-ttu-id="2c6d7-172">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-172">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-173">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-173">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="2c6d7-174">指定此表达式时，如果此表达式计算结果为 true，调试器将仅在断点停止。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-174">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-175">返回</span><span class="sxs-lookup"><span data-stu-id="2c6d7-175">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-176">breakpointId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-176">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="2c6d7-177">创建的断点的 ID，供进一步参考。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-177">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-178">actualLocation</span><span class="sxs-lookup"><span data-stu-id="2c6d7-178">actualLocation</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-179">此断点解析到的位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-179">Location this breakpoint resolved into.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-180">removeBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2c6d7-180">removeBreakpoint</span></span>
<span data-ttu-id="2c6d7-181">删除 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-181">Removes JavaScript breakpoint.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-182">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-182">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-183">breakpointId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-183">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-184">stepOver</span><span class="sxs-lookup"><span data-stu-id="2c6d7-184">stepOver</span></span>
<span data-ttu-id="2c6d7-185">对语句的步骤。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-185">Steps over the statement.</span></span>


---

### <span data-ttu-id="2c6d7-186">stepInto</span><span class="sxs-lookup"><span data-stu-id="2c6d7-186">stepInto</span></span>
<span data-ttu-id="2c6d7-187">进入函数调用。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-187">Steps into the function call.</span></span>


---

### <span data-ttu-id="2c6d7-188">stepOut</span><span class="sxs-lookup"><span data-stu-id="2c6d7-188">stepOut</span></span>
<span data-ttu-id="2c6d7-189">退出函数调用。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-189">Steps out of the function call.</span></span>


---

### <span data-ttu-id="2c6d7-190">pause</span><span class="sxs-lookup"><span data-stu-id="2c6d7-190">pause</span></span>
<span data-ttu-id="2c6d7-191">停止下一个 JavaScript 语句。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-191">Stops on the next JavaScript statement.</span></span>


---

### <span data-ttu-id="2c6d7-192">resume</span><span class="sxs-lookup"><span data-stu-id="2c6d7-192">resume</span></span>
<span data-ttu-id="2c6d7-193">恢复 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-193">Resumes JavaScript execution.</span></span>


---

### <span data-ttu-id="2c6d7-194">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="2c6d7-194">getScriptSource</span></span>
<span data-ttu-id="2c6d7-195">返回具有给定 ID 的脚本的源。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-195">Returns source for the script with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-196">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-196">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-197">scriptId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-197">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="2c6d7-198">要获取其源的脚本的 ID。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-198">Id of the script to get source for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-199">返回</span><span class="sxs-lookup"><span data-stu-id="2c6d7-199">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-200">scriptSource</span><span class="sxs-lookup"><span data-stu-id="2c6d7-200">scriptSource</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-201">脚本源。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-201">Script source.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-202">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="2c6d7-202">setPauseOnExceptions</span></span>
<span data-ttu-id="2c6d7-203">定义异常状态上的暂停。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-203">Defines pause on exceptions state.</span></span> <span data-ttu-id="2c6d7-204">可以设置为在所有异常、未捕获的异常或无异常上停止。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-204">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span> <span data-ttu-id="2c6d7-205">异常状态的初始暂停为 <code>none</code> 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-205">Initial pause on exceptions state is <code>none</code>.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-206">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-207">state</span><span class="sxs-lookup"><span data-stu-id="2c6d7-207">state</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="2c6d7-208">允许的值：无、未捕获、全部</span><span class="sxs-lookup"><span data-stu-id="2c6d7-208">Allowed values: none, uncaught, all</span></span></i></td>
            <td><span data-ttu-id="2c6d7-209">暂停异常模式。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-209">Pause on exceptions mode.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-210">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="2c6d7-210">evaluateOnCallFrame</span></span>
<span data-ttu-id="2c6d7-211">计算给定呼叫帧上的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-211">Evaluates expression on a given call frame.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-212">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-212">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-213">callFrameId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-213">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="2c6d7-214">要评估的呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-214">Call frame identifier to evaluate on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-215">表达式</span><span class="sxs-lookup"><span data-stu-id="2c6d7-215">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-216">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-216">Expression to evaluate.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-217">返回</span><span class="sxs-lookup"><span data-stu-id="2c6d7-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-218">result</span><span class="sxs-lookup"><span data-stu-id="2c6d7-218">result</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="2c6d7-219">评估结果的对象包装。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-219">Object wrapper for the evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-220">setVariableValue</span><span class="sxs-lookup"><span data-stu-id="2c6d7-220">setVariableValue</span></span>
<span data-ttu-id="2c6d7-221">更改调用框中的变量值。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-221">Changes value of variable in a callframe.</span></span> <span data-ttu-id="2c6d7-222">不支持基于对象的作用域，必须手动进行可变。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-222">Object-based scopes are not supported and must be mutated manually.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-223">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-223">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-224">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="2c6d7-224">scopeNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-225">范围链中列出的基于 0 的范围数。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-225">0-based number of scope as was listed in scope chain.</span></span> <span data-ttu-id="2c6d7-226">仅允许使用"local"、"closure"和"catch"范围类型。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-226">Only 'local', 'closure' and 'catch' scope types are allowed.</span></span> <span data-ttu-id="2c6d7-227">可以手动操作其他范围。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-227">Other scopes could be manipulated manually.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-228">variableName</span><span class="sxs-lookup"><span data-stu-id="2c6d7-228">variableName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-229">变量名称。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-229">Variable name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-230">newValue</span><span class="sxs-lookup"><span data-stu-id="2c6d7-230">newValue</span></span></td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td><span data-ttu-id="2c6d7-231">新变量值。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-231">New variable value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-232">callFrameId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-232">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="2c6d7-233">保留变量的 callframe 的 ID。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-233">Id of callframe that holds variable.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-234">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="2c6d7-234">setBlackboxPatterns</span></span>
<span><b><span data-ttu-id="2c6d7-235">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-235">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-236">将以前的黑盒模式替换为传递的黑色框模式。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-236">Replace previous blackbox patterns with passed ones.</span></span> <span data-ttu-id="2c6d7-237">使用与其中一种模式匹配的 URL 强制后端跳过脚本中的单步执行/暂停。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-237">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span> <span data-ttu-id="2c6d7-238">调试器将尝试通过多次执行"分步"来退出黑盒脚本，如果失败，最后会采取"退出"措施。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-238">The debugger will try to leave blackboxed script by performing 'step in' several times, finally resorting to 'step out' if unsuccessful.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-239">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-240">模式</span><span class="sxs-lookup"><span data-stu-id="2c6d7-240">patterns</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="2c6d7-241">将用于检查脚本 URL 的黑盒状态正则表达式的数组。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-241">Array of regexps that will be used to check script url for blackbox state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-242">msSetDebuggerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="2c6d7-242">msSetDebuggerPropertyValue</span></span>
<span><b><span data-ttu-id="2c6d7-243">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-243">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-244">Microsoft：将指定的调试器属性设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-244">Microsoft: Sets the specified debugger property to the specified value.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-245">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-245">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-246">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-246">debuggerPropertyId</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-247">Microsoft：属性 id (即 msDebuggerPropertyId) 设置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-247">Microsoft: The property id (i.e. msDebuggerPropertyId) to set.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-248">newValue</span><span class="sxs-lookup"><span data-stu-id="2c6d7-248">newValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="2c6d7-249">事件</span><span class="sxs-lookup"><span data-stu-id="2c6d7-249">Events</span></span>

### <span data-ttu-id="2c6d7-250">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="2c6d7-250">scriptParsed</span></span>
<span data-ttu-id="2c6d7-251">分析脚本时触发。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-251">Fired when the script is parsed.</span></span> <span data-ttu-id="2c6d7-252">启用调试器时，还会针对所有已知和未添加的脚本触发此事件。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-252">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-253">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-253">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-254">scriptId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-254">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="2c6d7-255">已分析的脚本的标识符。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-255">Identifier of the script parsed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-256">url</span><span class="sxs-lookup"><span data-stu-id="2c6d7-256">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-257">已分析脚本的 URL 或 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-257">URL or name of the script parsed (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-258">startLine</span><span class="sxs-lookup"><span data-stu-id="2c6d7-258">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-259">具有给定 URL 的资源中的脚本的行偏移量 (用于脚本标记) 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-259">Line offset of the script within the resource with given URL (for script tags).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-260">startColumn</span><span class="sxs-lookup"><span data-stu-id="2c6d7-260">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-261">具有给定 URL 的资源中的脚本的列偏移量。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-261">Column offset of the script within the resource with given URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-262">endLine</span><span class="sxs-lookup"><span data-stu-id="2c6d7-262">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-263">脚本的最后一行。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-263">Last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-264">endColumn</span><span class="sxs-lookup"><span data-stu-id="2c6d7-264">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-265">脚本最后一行的长度。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-265">Length of the last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-266">executionContextId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-266">executionContextId</span></span></td>
            <td><a href="runtime.md#executioncontextid"><code class="flyout">Runtime.ExecutionContextId</code></a></td>
            <td><span data-ttu-id="2c6d7-267">指定脚本创建上下文。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-267">Specifies script creation context.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-268">sourceMapURL</span><span class="sxs-lookup"><span data-stu-id="2c6d7-268">sourceMapURL</span></span> <br/> <i><span data-ttu-id="2c6d7-269">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-269">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-270">与脚本映射关联的源 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-270">URL of source map associated with script (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-271">length</span><span class="sxs-lookup"><span data-stu-id="2c6d7-271">length</span></span> <br/> <i><span data-ttu-id="2c6d7-272">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-272">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="2c6d7-273">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-273">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-274">此脚本长度。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-274">This script length.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-275">msParentId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-275">msParentId</span></span> <br/> <i><span data-ttu-id="2c6d7-276">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-276">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="2c6d7-277">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-277">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-278">这是父文档 ID。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-278">This is the parent document ID.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-279">msMimeType</span><span class="sxs-lookup"><span data-stu-id="2c6d7-279">msMimeType</span></span> <br/> <i><span data-ttu-id="2c6d7-280">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-280">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="2c6d7-281">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-281">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-282">这是 mime 类型。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-282">This is the mime type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-283">msIsDynamicCode</span><span class="sxs-lookup"><span data-stu-id="2c6d7-283">msIsDynamicCode</span></span> <br/> <i><span data-ttu-id="2c6d7-284">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-284">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="2c6d7-285">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-285">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-286">这指示它是否为动态代码。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-286">This indicates whether it is dynamic code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-287">msLongDocumentId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-287">msLongDocumentId</span></span> <br/> <i><span data-ttu-id="2c6d7-288">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-288">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="2c6d7-289">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-289">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-290">这是长文档 ID。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-290">This is the long document ID.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-291">breakpointResolved</span><span class="sxs-lookup"><span data-stu-id="2c6d7-291">breakpointResolved</span></span>
<span data-ttu-id="2c6d7-292">当断点解析为实际脚本和位置时触发。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-292">Fired when breakpoint is resolved to an actual script and location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-293">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-293">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-294">breakpointId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-294">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="2c6d7-295">断点唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-295">Breakpoint unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-296">location</span><span class="sxs-lookup"><span data-stu-id="2c6d7-296">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-297">实际断点位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-297">Actual breakpoint location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-298">msLength</span><span class="sxs-lookup"><span data-stu-id="2c6d7-298">msLength</span></span> <br/> <i><span data-ttu-id="2c6d7-299">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-299">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="2c6d7-300">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-300">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-301">Microsoft：代码长度 (即断点) 的字符数。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-301">Microsoft: Length of code (i.e. number of characters) at the breakpoint location.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-302">已暂停</span><span class="sxs-lookup"><span data-stu-id="2c6d7-302">paused</span></span>
<span data-ttu-id="2c6d7-303">当调试器中断断点或异常时触发。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-303">Fired when the debuggers breaks for a breakpoint or exception.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-304">参数</span><span class="sxs-lookup"><span data-stu-id="2c6d7-304">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-305">callFrames</span><span class="sxs-lookup"><span data-stu-id="2c6d7-305">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="2c6d7-306">调用调试器停止的堆栈。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-306">Call stack the debugger stopped on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-307">reason</span><span class="sxs-lookup"><span data-stu-id="2c6d7-307">reason</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="2c6d7-308">允许的值：断点、步骤、异常、其他</span><span class="sxs-lookup"><span data-stu-id="2c6d7-308">Allowed values: breakpoint, step, exception, other</span></span></i></td>
            <td><span data-ttu-id="2c6d7-309">暂停原因。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-309">Pause reason.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-310">数据</span><span class="sxs-lookup"><span data-stu-id="2c6d7-310">data</span></span> <br/> <i><span data-ttu-id="2c6d7-311">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-311">optional</span></span></i></td>
            <td><code class="flyout">object</code></td>
            <td><span data-ttu-id="2c6d7-312">包含特定于中断的辅助属性的对象。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-312">Object containing break-specific auxiliary properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-313">hitBreakpoints</span><span class="sxs-lookup"><span data-stu-id="2c6d7-313">hitBreakpoints</span></span> <br/> <i><span data-ttu-id="2c6d7-314">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-314">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="2c6d7-315">命中断点 ID</span><span class="sxs-lookup"><span data-stu-id="2c6d7-315">Hit breakpoints IDs</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2c6d7-316">恢复</span><span class="sxs-lookup"><span data-stu-id="2c6d7-316">resumed</span></span>
<span data-ttu-id="2c6d7-317">在调试程序恢复执行时触发。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-317">Fired when the debugger resumes execution.</span></span>


---

## <span data-ttu-id="2c6d7-318">类型</span><span class="sxs-lookup"><span data-stu-id="2c6d7-318">Types</span></span>

### <a name="breakpointid"></a> <span data-ttu-id="2c6d7-319">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-319">BreakpointId</span></span> `string`

<span data-ttu-id="2c6d7-320">断点标识符。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-320">Breakpoint identifier.</span></span>


---

### <a name="callframeid"></a> <span data-ttu-id="2c6d7-321">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-321">CallFrameId</span></span> `string`

<span data-ttu-id="2c6d7-322">呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-322">Call frame identifier.</span></span>


---

### <a name="location"></a> <span data-ttu-id="2c6d7-323">位置</span><span class="sxs-lookup"><span data-stu-id="2c6d7-323">Location</span></span> `object`

<span data-ttu-id="2c6d7-324">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-324">Location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-325">属性</span><span class="sxs-lookup"><span data-stu-id="2c6d7-325">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-326">scriptId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-326">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="2c6d7-327">报告在中的脚本标识符 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-327">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-328">lineNumber</span><span class="sxs-lookup"><span data-stu-id="2c6d7-328">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-329">脚本中的行号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-329">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-330">columnNumber</span><span class="sxs-lookup"><span data-stu-id="2c6d7-330">columnNumber</span></span> <br/> <i><span data-ttu-id="2c6d7-331">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-331">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-332">脚本中的列号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-332">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-333">msLength</span><span class="sxs-lookup"><span data-stu-id="2c6d7-333">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-334">Microsoft：代码长度 (即此调用) 的字符数。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-334">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="breaklocation"></a> <span data-ttu-id="2c6d7-335">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="2c6d7-335">BreakLocation</span></span> `object`

<span data-ttu-id="2c6d7-336">中断源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-336">Break location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-337">属性</span><span class="sxs-lookup"><span data-stu-id="2c6d7-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-338">scriptId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-338">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="2c6d7-339">报告在中的脚本标识符 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-339">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-340">lineNumber</span><span class="sxs-lookup"><span data-stu-id="2c6d7-340">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-341">脚本中的行号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-341">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-342">columnNumber</span><span class="sxs-lookup"><span data-stu-id="2c6d7-342">columnNumber</span></span> <br/> <i><span data-ttu-id="2c6d7-343">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-343">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-344">脚本中的列号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-344">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-345">msLength</span><span class="sxs-lookup"><span data-stu-id="2c6d7-345">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2c6d7-346">Microsoft：代码长度 (即此调用) 的字符数。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-346">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-347">类型</span><span class="sxs-lookup"><span data-stu-id="2c6d7-347">type</span></span> <br/> <i><span data-ttu-id="2c6d7-348">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-348">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-349">允许的值：debuggerStatement、call、return。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-349">Allowed values: debuggerStatement, call, return.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="callframe"></a> <span data-ttu-id="2c6d7-350">CallFrame</span><span class="sxs-lookup"><span data-stu-id="2c6d7-350">CallFrame</span></span> `object`

<span data-ttu-id="2c6d7-351">JavaScript 调用框架。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-351">JavaScript call frame.</span></span> <span data-ttu-id="2c6d7-352">调用堆栈中的呼叫帧数组。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-352">Array of call frames form the call stack.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-353">属性</span><span class="sxs-lookup"><span data-stu-id="2c6d7-353">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-354">callFrameId</span><span class="sxs-lookup"><span data-stu-id="2c6d7-354">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="2c6d7-355">呼叫帧标识符。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-355">Call frame identifier.</span></span> <span data-ttu-id="2c6d7-356">此标识符仅在调试器暂停时有效。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-356">This identifier is only valid while the debugger is paused.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-357">functionName</span><span class="sxs-lookup"><span data-stu-id="2c6d7-357">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-358">在此调用帧上调用的 JavaScript 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-358">Name of the JavaScript function called on this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-359">functionLocation</span><span class="sxs-lookup"><span data-stu-id="2c6d7-359">functionLocation</span></span> <br/> <i><span data-ttu-id="2c6d7-360">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-360">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b><span data-ttu-id="2c6d7-361">实验。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-361">Experimental.</span></span> </b></span><span data-ttu-id="2c6d7-362">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-362">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-363">location</span><span class="sxs-lookup"><span data-stu-id="2c6d7-363">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-364">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-364">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-365">url</span><span class="sxs-lookup"><span data-stu-id="2c6d7-365">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2c6d7-366">JavaScript 脚本名称或 URL。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-366">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-367">scopeChain</span><span class="sxs-lookup"><span data-stu-id="2c6d7-367">scopeChain</span></span></td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td><span data-ttu-id="2c6d7-368">此呼叫帧的范围链。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-368">Scope chain for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-369">this</span><span class="sxs-lookup"><span data-stu-id="2c6d7-369">this</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> <span data-ttu-id="2c6d7-370">对象。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-370">object for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-371">returnValue</span><span class="sxs-lookup"><span data-stu-id="2c6d7-371">returnValue</span></span> <br/> <i><span data-ttu-id="2c6d7-372">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-372">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="2c6d7-373">如果函数在返回点，则返回的值。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-373">The value being returned, if the function is at return point.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="scope"></a> <span data-ttu-id="2c6d7-374">范围</span><span class="sxs-lookup"><span data-stu-id="2c6d7-374">Scope</span></span> `object`

<span data-ttu-id="2c6d7-375">范围说明。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-375">Scope description.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2c6d7-376">属性</span><span class="sxs-lookup"><span data-stu-id="2c6d7-376">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2c6d7-377">类型</span><span class="sxs-lookup"><span data-stu-id="2c6d7-377">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="2c6d7-378">允许的值：global、local、with、closure、catch、block、script、eval、module</span><span class="sxs-lookup"><span data-stu-id="2c6d7-378">Allowed values: global, local, with, closure, catch, block, script, eval, module</span></span></i></td>
            <td><span data-ttu-id="2c6d7-379">范围类型。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-379">Scope type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-380">object</span><span class="sxs-lookup"><span data-stu-id="2c6d7-380">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="2c6d7-381">表示范围的对象。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-381">Object representing the scope.</span></span> <span data-ttu-id="2c6d7-382">对于和范围，它表示实际对象;对于其余范围，它是人工瞬态对象，用于枚举范围变量 <code>global</code> <code>with</code> 作为其属性。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-382">For <code>global</code> and <code>with</code> scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-383">name</span><span class="sxs-lookup"><span data-stu-id="2c6d7-383">name</span></span> <br/> <i><span data-ttu-id="2c6d7-384">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-384">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-385">startLocation</span><span class="sxs-lookup"><span data-stu-id="2c6d7-385">startLocation</span></span> <br/> <i><span data-ttu-id="2c6d7-386">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-386">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-387">范围开始的源代码中的位置</span><span class="sxs-lookup"><span data-stu-id="2c6d7-387">Location in the source code where scope starts</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2c6d7-388">endLocation</span><span class="sxs-lookup"><span data-stu-id="2c6d7-388">endLocation</span></span> <br/> <i><span data-ttu-id="2c6d7-389">可选</span><span class="sxs-lookup"><span data-stu-id="2c6d7-389">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="2c6d7-390">范围结束的源代码中的位置</span><span class="sxs-lookup"><span data-stu-id="2c6d7-390">Location in the source code where scope ends</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="2c6d7-391">依赖关系</span><span class="sxs-lookup"><span data-stu-id="2c6d7-391">Dependencies</span></span>

[<span data-ttu-id="2c6d7-392">运行时</span><span class="sxs-lookup"><span data-stu-id="2c6d7-392">Runtime</span></span>](runtime.md)
