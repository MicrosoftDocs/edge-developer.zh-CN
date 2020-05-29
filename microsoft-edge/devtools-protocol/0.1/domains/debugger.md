---
description: 对调试器域的引用。 调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。
title: 调试器域-DevTools 协议版本0。1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 6c5d668f943a731e5ba86ed5aa2294007a432ce6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563427"
---
# <span data-ttu-id="4155f-105">调试器</span><span class="sxs-lookup"><span data-stu-id="4155f-105">Debugger</span></span>
<span data-ttu-id="4155f-106">调试器域公开 JavaScript 调试功能。</span><span class="sxs-lookup"><span data-stu-id="4155f-106">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="4155f-107">它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。</span><span class="sxs-lookup"><span data-stu-id="4155f-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="4155f-108">方法</span><span class="sxs-lookup"><span data-stu-id="4155f-108">Methods</span></span>**](#methods) | <span data-ttu-id="4155f-109">[enable](#enable)、 [disable](#disable)、 [getPossibleBreakpoints](#getpossiblebreakpoints)、 [setBreakpointsActive](#setbreakpointsactive)、 [setBreakpointByUrl](#setbreakpointbyurl)、 [setBreakpoint](#setbreakpoint)、 [removeBreakpoint](#removebreakpoint)、[跨距](#stepover)、 [stepInto](#stepinto)、 [stepOut](#stepout)、[暂停](#pause)、[恢复](#resume)、 [getScriptSource、setPauseOnExceptions](#getscriptsource)、 [evaluateOnCallFrame](#evaluateoncallframe)、 [setVariableValue](#setvariablevalue)、 [setBlackboxPatterns](#setblackboxpatterns)、msSetDebuggerPropertyValue、、、 [、、](#mssetdebuggerpropertyvalue) 、 [setPauseOnExceptions](#setpauseonexceptions)</span><span class="sxs-lookup"><span data-stu-id="4155f-109">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |
| [**<span data-ttu-id="4155f-110">事件</span><span class="sxs-lookup"><span data-stu-id="4155f-110">Events</span></span>**](#events) | <span data-ttu-id="4155f-111">[scriptParsed](#scriptparsed)、 [breakpointResolved](#breakpointresolved)、已[暂停](#paused)、已[恢复](#resumed)</span><span class="sxs-lookup"><span data-stu-id="4155f-111">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |
| [**<span data-ttu-id="4155f-112">类型</span><span class="sxs-lookup"><span data-stu-id="4155f-112">Types</span></span>**](#types) | <span data-ttu-id="4155f-113">[BreakpointId](#breakpointid)、 [CallFrameId](#callframeid)、 [Location](#location)、 [BreakLocation](#breaklocation)、 [CallFrame](#callframe)、 [Scope](#scope)</span><span class="sxs-lookup"><span data-stu-id="4155f-113">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |
| [**<span data-ttu-id="4155f-114">依赖关系</span><span class="sxs-lookup"><span data-stu-id="4155f-114">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="4155f-115">运行时</span><span class="sxs-lookup"><span data-stu-id="4155f-115">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="4155f-116">方法</span><span class="sxs-lookup"><span data-stu-id="4155f-116">Methods</span></span>

### <span data-ttu-id="4155f-117">“启用”</span><span class="sxs-lookup"><span data-stu-id="4155f-117">enable</span></span>
<span data-ttu-id="4155f-118">为给定页面启用调试器。</span><span class="sxs-lookup"><span data-stu-id="4155f-118">Enables debugger for the given page.</span></span> <span data-ttu-id="4155f-119">客户端不应假设已启用调试，直到接收到此命令的结果。</span><span class="sxs-lookup"><span data-stu-id="4155f-119">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>


---

### <span data-ttu-id="4155f-120">“禁用”</span><span class="sxs-lookup"><span data-stu-id="4155f-120">disable</span></span>
<span data-ttu-id="4155f-121">为给定页禁用调试器。</span><span class="sxs-lookup"><span data-stu-id="4155f-121">Disables debugger for given page.</span></span>


---

### <span data-ttu-id="4155f-122">getPossibleBreakpoints</span><span class="sxs-lookup"><span data-stu-id="4155f-122">getPossibleBreakpoints</span></span>
<span data-ttu-id="4155f-123">返回断点的可能位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-123">Returns possible locations for breakpoint.</span></span> <span data-ttu-id="4155f-124">开始和结束区域位置中的 scriptId 应相同。</span><span class="sxs-lookup"><span data-stu-id="4155f-124">scriptId in start and end range locations should be the same.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-125">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-125">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-126">start</span><span class="sxs-lookup"><span data-stu-id="4155f-126">start</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-127">在中搜索可能的断点位置的起始范围。</span><span class="sxs-lookup"><span data-stu-id="4155f-127">Start of range to search possible breakpoint locations in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-128">结束</span><span class="sxs-lookup"><span data-stu-id="4155f-128">end</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-129">在（不包括）中搜索可能的断点位置的结尾。</span><span class="sxs-lookup"><span data-stu-id="4155f-129">End of range to search possible breakpoint locations in (excluding).</span></span> <span data-ttu-id="4155f-130">当未指定时，脚本的结尾将用作区域的结尾。</span><span class="sxs-lookup"><span data-stu-id="4155f-130">When not specified, end of scripts is used as end of range.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-131">返回</span><span class="sxs-lookup"><span data-stu-id="4155f-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-132">各个</span><span class="sxs-lookup"><span data-stu-id="4155f-132">locations</span></span></td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td><span data-ttu-id="4155f-133">可能的断点位置的列表。</span><span class="sxs-lookup"><span data-stu-id="4155f-133">List of the possible breakpoint locations.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-134">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="4155f-134">setBreakpointsActive</span></span>
<span data-ttu-id="4155f-135">激活/停用页面上的所有断点。</span><span class="sxs-lookup"><span data-stu-id="4155f-135">Activates / deactivates all breakpoints on the page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-136">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-136">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-137">active</span><span class="sxs-lookup"><span data-stu-id="4155f-137">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="4155f-138">断点活动状态的新值。</span><span class="sxs-lookup"><span data-stu-id="4155f-138">New value for breakpoints active state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-139">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="4155f-139">setBreakpointByUrl</span></span>
<span data-ttu-id="4155f-140">在通过 URL 或 URL regex 指定的给定位置设置 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="4155f-140">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span> <span data-ttu-id="4155f-141">发出此命令后，所有现有的已分析脚本都将在属性中解析和返回断点 <code>locations</code> 。</span><span class="sxs-lookup"><span data-stu-id="4155f-141">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in <code>locations</code> property.</span></span> <span data-ttu-id="4155f-142">进一步匹配的脚本分析将导致后续 <code>breakpointResolved</code> 事件被发布。</span><span class="sxs-lookup"><span data-stu-id="4155f-142">Further matching script parsing will result in subsequent <code>breakpointResolved</code> events issued.</span></span> <span data-ttu-id="4155f-143">此逻辑断点将在页面重新加载后继续。</span><span class="sxs-lookup"><span data-stu-id="4155f-143">This logical breakpoint will survive page reloads.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-144">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-144">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-145">lineNumber</span><span class="sxs-lookup"><span data-stu-id="4155f-145">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-146">用于设置断点的行号。</span><span class="sxs-lookup"><span data-stu-id="4155f-146">Line number to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-147">url</span><span class="sxs-lookup"><span data-stu-id="4155f-147">url</span></span> <br/> <i><span data-ttu-id="4155f-148">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-148">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-149">要在其上设置断点的资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="4155f-149">URL of the resources to set breakpoint on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-150">urlRegex</span><span class="sxs-lookup"><span data-stu-id="4155f-150">urlRegex</span></span> <br/> <i><span data-ttu-id="4155f-151">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-151">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-152">要在其上设置断点的资源的 Url 的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="4155f-152">Regex pattern for the URLs of the resources to set breakpoints on.</span></span> <span data-ttu-id="4155f-153"><code>url</code>或者 <code>urlRegex</code> 必须指定。</span><span class="sxs-lookup"><span data-stu-id="4155f-153">Either <code>url</code> or <code>urlRegex</code> must be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-154">columnNumber</span><span class="sxs-lookup"><span data-stu-id="4155f-154">columnNumber</span></span> <br/> <i><span data-ttu-id="4155f-155">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-155">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-156">行中的偏移量，用于设置断点。</span><span class="sxs-lookup"><span data-stu-id="4155f-156">Offset in the line to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-157">符合</span><span class="sxs-lookup"><span data-stu-id="4155f-157">condition</span></span> <br/> <i><span data-ttu-id="4155f-158">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-158">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-159">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="4155f-159">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="4155f-160">如果指定，只有当此表达式的计算结果为 true 时，调试器才会在断点处停止。</span><span class="sxs-lookup"><span data-stu-id="4155f-160">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-161">返回</span><span class="sxs-lookup"><span data-stu-id="4155f-161">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-162">breakpointId</span><span class="sxs-lookup"><span data-stu-id="4155f-162">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="4155f-163">用于进一步引用的已创建断点的 Id。</span><span class="sxs-lookup"><span data-stu-id="4155f-163">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-164">各个</span><span class="sxs-lookup"><span data-stu-id="4155f-164">locations</span></span></td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td><span data-ttu-id="4155f-165">添加此断点时，此断点的解决位置的列表。</span><span class="sxs-lookup"><span data-stu-id="4155f-165">List of the locations this breakpoint resolved into upon addition.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-166">setBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4155f-166">setBreakpoint</span></span>
<span data-ttu-id="4155f-167">在给定位置设置 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="4155f-167">Sets JavaScript breakpoint at a given location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-168">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-168">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-169">location</span><span class="sxs-lookup"><span data-stu-id="4155f-169">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-170">在其中设置断点的位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-170">Location to set breakpoint in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-171">符合</span><span class="sxs-lookup"><span data-stu-id="4155f-171">condition</span></span> <br/> <i><span data-ttu-id="4155f-172">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-172">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-173">用作断点条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="4155f-173">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="4155f-174">如果指定，只有当此表达式的计算结果为 true 时，调试器才会在断点处停止。</span><span class="sxs-lookup"><span data-stu-id="4155f-174">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-175">返回</span><span class="sxs-lookup"><span data-stu-id="4155f-175">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-176">breakpointId</span><span class="sxs-lookup"><span data-stu-id="4155f-176">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="4155f-177">用于进一步引用的已创建断点的 Id。</span><span class="sxs-lookup"><span data-stu-id="4155f-177">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-178">actualLocation</span><span class="sxs-lookup"><span data-stu-id="4155f-178">actualLocation</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-179">解决此断点的位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-179">Location this breakpoint resolved into.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-180">removeBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4155f-180">removeBreakpoint</span></span>
<span data-ttu-id="4155f-181">删除 JavaScript 断点。</span><span class="sxs-lookup"><span data-stu-id="4155f-181">Removes JavaScript breakpoint.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-182">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-182">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-183">breakpointId</span><span class="sxs-lookup"><span data-stu-id="4155f-183">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-184">配合</span><span class="sxs-lookup"><span data-stu-id="4155f-184">stepOver</span></span>
<span data-ttu-id="4155f-185">对语句执行步骤。</span><span class="sxs-lookup"><span data-stu-id="4155f-185">Steps over the statement.</span></span>


---

### <span data-ttu-id="4155f-186">stepInto</span><span class="sxs-lookup"><span data-stu-id="4155f-186">stepInto</span></span>
<span data-ttu-id="4155f-187">执行函数调用中的步骤。</span><span class="sxs-lookup"><span data-stu-id="4155f-187">Steps into the function call.</span></span>


---

### <span data-ttu-id="4155f-188">stepOut</span><span class="sxs-lookup"><span data-stu-id="4155f-188">stepOut</span></span>
<span data-ttu-id="4155f-189">执行函数调用之外的步骤。</span><span class="sxs-lookup"><span data-stu-id="4155f-189">Steps out of the function call.</span></span>


---

### <span data-ttu-id="4155f-190">pause</span><span class="sxs-lookup"><span data-stu-id="4155f-190">pause</span></span>
<span data-ttu-id="4155f-191">在下一个 JavaScript 语句停止。</span><span class="sxs-lookup"><span data-stu-id="4155f-191">Stops on the next JavaScript statement.</span></span>


---

### <span data-ttu-id="4155f-192">resume</span><span class="sxs-lookup"><span data-stu-id="4155f-192">resume</span></span>
<span data-ttu-id="4155f-193">继续执行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="4155f-193">Resumes JavaScript execution.</span></span>


---

### <span data-ttu-id="4155f-194">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="4155f-194">getScriptSource</span></span>
<span data-ttu-id="4155f-195">返回具有给定 id 的脚本的源。</span><span class="sxs-lookup"><span data-stu-id="4155f-195">Returns source for the script with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-196">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-196">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-197">scriptId</span><span class="sxs-lookup"><span data-stu-id="4155f-197">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="4155f-198">要获取其源的脚本的 Id。</span><span class="sxs-lookup"><span data-stu-id="4155f-198">Id of the script to get source for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-199">返回</span><span class="sxs-lookup"><span data-stu-id="4155f-199">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-200">scriptSource</span><span class="sxs-lookup"><span data-stu-id="4155f-200">scriptSource</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-201">脚本源。</span><span class="sxs-lookup"><span data-stu-id="4155f-201">Script source.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-202">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="4155f-202">setPauseOnExceptions</span></span>
<span data-ttu-id="4155f-203">定义 "在异常状态时暂停" 状态。</span><span class="sxs-lookup"><span data-stu-id="4155f-203">Defines pause on exceptions state.</span></span> <span data-ttu-id="4155f-204">可以设置为在所有异常、未捕获的异常或无异常的情况下停止。</span><span class="sxs-lookup"><span data-stu-id="4155f-204">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span> <span data-ttu-id="4155f-205">异常状态的初始暂停为 <code>none</code> 。</span><span class="sxs-lookup"><span data-stu-id="4155f-205">Initial pause on exceptions state is <code>none</code>.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-206">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-207">状态</span><span class="sxs-lookup"><span data-stu-id="4155f-207">state</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="4155f-208">允许的值：无、未捕获、全部</span><span class="sxs-lookup"><span data-stu-id="4155f-208">Allowed values: none, uncaught, all</span></span></i></td>
            <td><span data-ttu-id="4155f-209">"在例外模式暂停"。</span><span class="sxs-lookup"><span data-stu-id="4155f-209">Pause on exceptions mode.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-210">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="4155f-210">evaluateOnCallFrame</span></span>
<span data-ttu-id="4155f-211">计算给定调用帧上的表达式。</span><span class="sxs-lookup"><span data-stu-id="4155f-211">Evaluates expression on a given call frame.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-212">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-212">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-213">callFrameId</span><span class="sxs-lookup"><span data-stu-id="4155f-213">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="4155f-214">要计算的调用帧标识符。</span><span class="sxs-lookup"><span data-stu-id="4155f-214">Call frame identifier to evaluate on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-215">表达</span><span class="sxs-lookup"><span data-stu-id="4155f-215">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-216">要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="4155f-216">Expression to evaluate.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-217">返回</span><span class="sxs-lookup"><span data-stu-id="4155f-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-218">结果</span><span class="sxs-lookup"><span data-stu-id="4155f-218">result</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="4155f-219">计算结果的对象包装器。</span><span class="sxs-lookup"><span data-stu-id="4155f-219">Object wrapper for the evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-220">setVariableValue</span><span class="sxs-lookup"><span data-stu-id="4155f-220">setVariableValue</span></span>
<span data-ttu-id="4155f-221">更改 callframe 中的变量值。</span><span class="sxs-lookup"><span data-stu-id="4155f-221">Changes value of variable in a callframe.</span></span> <span data-ttu-id="4155f-222">基于对象的作用域不受支持，必须手动进行。</span><span class="sxs-lookup"><span data-stu-id="4155f-222">Object-based scopes are not supported and must be mutated manually.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-223">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-223">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-224">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="4155f-224">scopeNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-225">作用域链中列出了从0开始的范围数。</span><span class="sxs-lookup"><span data-stu-id="4155f-225">0-based number of scope as was listed in scope chain.</span></span> <span data-ttu-id="4155f-226">仅允许 "local"、"闭" 和 "catch" 作用域类型。</span><span class="sxs-lookup"><span data-stu-id="4155f-226">Only 'local', 'closure' and 'catch' scope types are allowed.</span></span> <span data-ttu-id="4155f-227">其他作用域可以手动操作。</span><span class="sxs-lookup"><span data-stu-id="4155f-227">Other scopes could be manipulated manually.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-228">variableName</span><span class="sxs-lookup"><span data-stu-id="4155f-228">variableName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-229">变量名称。</span><span class="sxs-lookup"><span data-stu-id="4155f-229">Variable name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-230">newValue</span><span class="sxs-lookup"><span data-stu-id="4155f-230">newValue</span></span></td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td><span data-ttu-id="4155f-231">新的变量值。</span><span class="sxs-lookup"><span data-stu-id="4155f-231">New variable value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-232">callFrameId</span><span class="sxs-lookup"><span data-stu-id="4155f-232">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="4155f-233">保存变量的 callframe 的 Id。</span><span class="sxs-lookup"><span data-stu-id="4155f-233">Id of callframe that holds variable.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-234">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="4155f-234">setBlackboxPatterns</span></span>
<span><b><span data-ttu-id="4155f-235">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-235">Experimental.</span></span> </b></span><span data-ttu-id="4155f-236">将以前的 blackbox 模式替换为已传递的模式。</span><span class="sxs-lookup"><span data-stu-id="4155f-236">Replace previous blackbox patterns with passed ones.</span></span> <span data-ttu-id="4155f-237">强制后端通过与其中一个模式匹配的 url 跳过在脚本中的步进/暂停。</span><span class="sxs-lookup"><span data-stu-id="4155f-237">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span> <span data-ttu-id="4155f-238">调试程序将尝试通过多次执行 "step in" 来退出 blackboxed 脚本，最后，如果不成功，则使用 "跳出"。</span><span class="sxs-lookup"><span data-stu-id="4155f-238">The debugger will try to leave blackboxed script by performing 'step in' several times, finally resorting to 'step out' if unsuccessful.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-239">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-240">模式</span><span class="sxs-lookup"><span data-stu-id="4155f-240">patterns</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="4155f-241">将用于检查 blackbox 状态的脚本 url 的 regexps 数组。</span><span class="sxs-lookup"><span data-stu-id="4155f-241">Array of regexps that will be used to check script url for blackbox state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-242">msSetDebuggerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="4155f-242">msSetDebuggerPropertyValue</span></span>
<span><b><span data-ttu-id="4155f-243">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-243">Experimental.</span></span> </b></span><span data-ttu-id="4155f-244">Microsoft：将指定的调试器属性设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="4155f-244">Microsoft: Sets the specified debugger property to the specified value.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-245">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-245">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-246">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="4155f-246">debuggerPropertyId</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-247">Microsoft：要设置的属性 id （如 msDebuggerPropertyId）。</span><span class="sxs-lookup"><span data-stu-id="4155f-247">Microsoft: The property id (i.e. msDebuggerPropertyId) to set.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-248">newValue</span><span class="sxs-lookup"><span data-stu-id="4155f-248">newValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="4155f-249">事件</span><span class="sxs-lookup"><span data-stu-id="4155f-249">Events</span></span>

### <span data-ttu-id="4155f-250">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="4155f-250">scriptParsed</span></span>
<span data-ttu-id="4155f-251">在分析脚本时激发。</span><span class="sxs-lookup"><span data-stu-id="4155f-251">Fired when the script is parsed.</span></span> <span data-ttu-id="4155f-252">启用调试程序时，还会针对所有已知和 uncollected 脚本触发此事件。</span><span class="sxs-lookup"><span data-stu-id="4155f-252">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-253">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-253">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-254">scriptId</span><span class="sxs-lookup"><span data-stu-id="4155f-254">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="4155f-255">已分析的脚本的标识符。</span><span class="sxs-lookup"><span data-stu-id="4155f-255">Identifier of the script parsed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-256">url</span><span class="sxs-lookup"><span data-stu-id="4155f-256">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-257">已分析的脚本的 URL 或名称（如果有）。</span><span class="sxs-lookup"><span data-stu-id="4155f-257">URL or name of the script parsed (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-258">startLine</span><span class="sxs-lookup"><span data-stu-id="4155f-258">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-259">具有给定 URL （对于脚本标记）的资源中的脚本的行偏移量。</span><span class="sxs-lookup"><span data-stu-id="4155f-259">Line offset of the script within the resource with given URL (for script tags).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-260">startColumn</span><span class="sxs-lookup"><span data-stu-id="4155f-260">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-261">具有给定 URL 的资源内的脚本的列偏移量。</span><span class="sxs-lookup"><span data-stu-id="4155f-261">Column offset of the script within the resource with given URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-262">endLine</span><span class="sxs-lookup"><span data-stu-id="4155f-262">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-263">脚本的最后一行。</span><span class="sxs-lookup"><span data-stu-id="4155f-263">Last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-264">endColumn</span><span class="sxs-lookup"><span data-stu-id="4155f-264">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-265">脚本最后一行的长度。</span><span class="sxs-lookup"><span data-stu-id="4155f-265">Length of the last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-266">executionContextId</span><span class="sxs-lookup"><span data-stu-id="4155f-266">executionContextId</span></span></td>
            <td><a href="runtime.md#executioncontextid"><code class="flyout">Runtime.ExecutionContextId</code></a></td>
            <td><span data-ttu-id="4155f-267">指定脚本创建上下文。</span><span class="sxs-lookup"><span data-stu-id="4155f-267">Specifies script creation context.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-268">sourceMapURL</span><span class="sxs-lookup"><span data-stu-id="4155f-268">sourceMapURL</span></span> <br/> <i><span data-ttu-id="4155f-269">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-269">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-270">与脚本关联的源映射的 URL （如果有）。</span><span class="sxs-lookup"><span data-stu-id="4155f-270">URL of source map associated with script (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-271">时长</span><span class="sxs-lookup"><span data-stu-id="4155f-271">length</span></span> <br/> <i><span data-ttu-id="4155f-272">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-272">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="4155f-273">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-273">Experimental.</span></span> </b></span><span data-ttu-id="4155f-274">此脚本长度。</span><span class="sxs-lookup"><span data-stu-id="4155f-274">This script length.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-275">msParentId</span><span class="sxs-lookup"><span data-stu-id="4155f-275">msParentId</span></span> <br/> <i><span data-ttu-id="4155f-276">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-276">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="4155f-277">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-277">Experimental.</span></span> </b></span><span data-ttu-id="4155f-278">这是父文档 ID。</span><span class="sxs-lookup"><span data-stu-id="4155f-278">This is the parent document ID.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-279">msMimeType</span><span class="sxs-lookup"><span data-stu-id="4155f-279">msMimeType</span></span> <br/> <i><span data-ttu-id="4155f-280">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-280">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="4155f-281">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-281">Experimental.</span></span> </b></span><span data-ttu-id="4155f-282">这是 mime 类型。</span><span class="sxs-lookup"><span data-stu-id="4155f-282">This is the mime type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-283">msIsDynamicCode</span><span class="sxs-lookup"><span data-stu-id="4155f-283">msIsDynamicCode</span></span> <br/> <i><span data-ttu-id="4155f-284">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-284">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="4155f-285">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-285">Experimental.</span></span> </b></span><span data-ttu-id="4155f-286">这指示它是否是动态代码。</span><span class="sxs-lookup"><span data-stu-id="4155f-286">This indicates whether it is dynamic code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-287">msLongDocumentId</span><span class="sxs-lookup"><span data-stu-id="4155f-287">msLongDocumentId</span></span> <br/> <i><span data-ttu-id="4155f-288">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-288">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="4155f-289">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-289">Experimental.</span></span> </b></span><span data-ttu-id="4155f-290">这是长文档 ID。</span><span class="sxs-lookup"><span data-stu-id="4155f-290">This is the long document ID.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-291">breakpointResolved</span><span class="sxs-lookup"><span data-stu-id="4155f-291">breakpointResolved</span></span>
<span data-ttu-id="4155f-292">将断点解析为实际脚本和位置时激发。</span><span class="sxs-lookup"><span data-stu-id="4155f-292">Fired when breakpoint is resolved to an actual script and location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-293">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-293">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-294">breakpointId</span><span class="sxs-lookup"><span data-stu-id="4155f-294">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="4155f-295">断点唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4155f-295">Breakpoint unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-296">location</span><span class="sxs-lookup"><span data-stu-id="4155f-296">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-297">实际断点位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-297">Actual breakpoint location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-298">msLength</span><span class="sxs-lookup"><span data-stu-id="4155f-298">msLength</span></span> <br/> <i><span data-ttu-id="4155f-299">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-299">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="4155f-300">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-300">Experimental.</span></span> </b></span><span data-ttu-id="4155f-301">Microsoft：断点位置处的代码长度（即字符数）。</span><span class="sxs-lookup"><span data-stu-id="4155f-301">Microsoft: Length of code (i.e. number of characters) at the breakpoint location.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-302">已暂停</span><span class="sxs-lookup"><span data-stu-id="4155f-302">paused</span></span>
<span data-ttu-id="4155f-303">当调试程序中断断点或异常时引发。</span><span class="sxs-lookup"><span data-stu-id="4155f-303">Fired when the debuggers breaks for a breakpoint or exception.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-304">参数</span><span class="sxs-lookup"><span data-stu-id="4155f-304">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-305">callFrames</span><span class="sxs-lookup"><span data-stu-id="4155f-305">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="4155f-306">调试器在其上停止的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="4155f-306">Call stack the debugger stopped on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-307">reason</span><span class="sxs-lookup"><span data-stu-id="4155f-307">reason</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="4155f-308">允许的值：断点、步骤、异常、其他</span><span class="sxs-lookup"><span data-stu-id="4155f-308">Allowed values: breakpoint, step, exception, other</span></span></i></td>
            <td><span data-ttu-id="4155f-309">暂停原因。</span><span class="sxs-lookup"><span data-stu-id="4155f-309">Pause reason.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-310">数据</span><span class="sxs-lookup"><span data-stu-id="4155f-310">data</span></span> <br/> <i><span data-ttu-id="4155f-311">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-311">optional</span></span></i></td>
            <td><code class="flyout">object</code></td>
            <td><span data-ttu-id="4155f-312">包含特定于断点的辅助属性的对象。</span><span class="sxs-lookup"><span data-stu-id="4155f-312">Object containing break-specific auxiliary properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-313">hitBreakpoints</span><span class="sxs-lookup"><span data-stu-id="4155f-313">hitBreakpoints</span></span> <br/> <i><span data-ttu-id="4155f-314">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-314">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="4155f-315">命中断点 Id</span><span class="sxs-lookup"><span data-stu-id="4155f-315">Hit breakpoints IDs</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="4155f-316">稍后</span><span class="sxs-lookup"><span data-stu-id="4155f-316">resumed</span></span>
<span data-ttu-id="4155f-317">调试器恢复执行时激发。</span><span class="sxs-lookup"><span data-stu-id="4155f-317">Fired when the debugger resumes execution.</span></span>


---

## <span data-ttu-id="4155f-318">类型</span><span class="sxs-lookup"><span data-stu-id="4155f-318">Types</span></span>

### <a name="breakpointid"></a> <span data-ttu-id="4155f-319">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="4155f-319">BreakpointId</span></span> `string`

<span data-ttu-id="4155f-320">断点标识符。</span><span class="sxs-lookup"><span data-stu-id="4155f-320">Breakpoint identifier.</span></span>


---

### <a name="callframeid"></a> <span data-ttu-id="4155f-321">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="4155f-321">CallFrameId</span></span> `string`

<span data-ttu-id="4155f-322">通话帧标识符。</span><span class="sxs-lookup"><span data-stu-id="4155f-322">Call frame identifier.</span></span>


---

### <a name="location"></a> <span data-ttu-id="4155f-323">位置</span><span class="sxs-lookup"><span data-stu-id="4155f-323">Location</span></span> `object`

<span data-ttu-id="4155f-324">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-324">Location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-325">属性</span><span class="sxs-lookup"><span data-stu-id="4155f-325">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-326">scriptId</span><span class="sxs-lookup"><span data-stu-id="4155f-326">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="4155f-327">中报告的脚本标识符 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="4155f-327">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-328">lineNumber</span><span class="sxs-lookup"><span data-stu-id="4155f-328">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-329">脚本中的行号（从0开始）。</span><span class="sxs-lookup"><span data-stu-id="4155f-329">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-330">columnNumber</span><span class="sxs-lookup"><span data-stu-id="4155f-330">columnNumber</span></span> <br/> <i><span data-ttu-id="4155f-331">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-331">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-332">脚本中的列号（基于0）。</span><span class="sxs-lookup"><span data-stu-id="4155f-332">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-333">msLength</span><span class="sxs-lookup"><span data-stu-id="4155f-333">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-334">Microsoft：此调用帧上的代码长度（例如字符数）。</span><span class="sxs-lookup"><span data-stu-id="4155f-334">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="breaklocation"></a> <span data-ttu-id="4155f-335">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="4155f-335">BreakLocation</span></span> `object`

<span data-ttu-id="4155f-336">在源代码中中断位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-336">Break location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-337">属性</span><span class="sxs-lookup"><span data-stu-id="4155f-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-338">scriptId</span><span class="sxs-lookup"><span data-stu-id="4155f-338">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="4155f-339">中报告的脚本标识符 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="4155f-339">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-340">lineNumber</span><span class="sxs-lookup"><span data-stu-id="4155f-340">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-341">脚本中的行号（从0开始）。</span><span class="sxs-lookup"><span data-stu-id="4155f-341">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-342">columnNumber</span><span class="sxs-lookup"><span data-stu-id="4155f-342">columnNumber</span></span> <br/> <i><span data-ttu-id="4155f-343">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-343">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-344">脚本中的列号（基于0）。</span><span class="sxs-lookup"><span data-stu-id="4155f-344">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-345">msLength</span><span class="sxs-lookup"><span data-stu-id="4155f-345">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="4155f-346">Microsoft：此调用帧上的代码长度（例如字符数）。</span><span class="sxs-lookup"><span data-stu-id="4155f-346">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-347">类型</span><span class="sxs-lookup"><span data-stu-id="4155f-347">type</span></span> <br/> <i><span data-ttu-id="4155f-348">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-348">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-349">允许的值： debuggerStatement、call、return。</span><span class="sxs-lookup"><span data-stu-id="4155f-349">Allowed values: debuggerStatement, call, return.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="callframe"></a> <span data-ttu-id="4155f-350">CallFrame</span><span class="sxs-lookup"><span data-stu-id="4155f-350">CallFrame</span></span> `object`

<span data-ttu-id="4155f-351">JavaScript 调用帧。</span><span class="sxs-lookup"><span data-stu-id="4155f-351">JavaScript call frame.</span></span> <span data-ttu-id="4155f-352">调用帧的数组构成了调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="4155f-352">Array of call frames form the call stack.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-353">属性</span><span class="sxs-lookup"><span data-stu-id="4155f-353">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-354">callFrameId</span><span class="sxs-lookup"><span data-stu-id="4155f-354">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="4155f-355">通话帧标识符。</span><span class="sxs-lookup"><span data-stu-id="4155f-355">Call frame identifier.</span></span> <span data-ttu-id="4155f-356">此标识符仅在调试器暂停时才有效。</span><span class="sxs-lookup"><span data-stu-id="4155f-356">This identifier is only valid while the debugger is paused.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-357">functionName</span><span class="sxs-lookup"><span data-stu-id="4155f-357">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-358">在此调用帧上调用的 JavaScript 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="4155f-358">Name of the JavaScript function called on this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-359">functionLocation</span><span class="sxs-lookup"><span data-stu-id="4155f-359">functionLocation</span></span> <br/> <i><span data-ttu-id="4155f-360">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-360">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b><span data-ttu-id="4155f-361">实验.</span><span class="sxs-lookup"><span data-stu-id="4155f-361">Experimental.</span></span> </b></span><span data-ttu-id="4155f-362">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-362">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-363">location</span><span class="sxs-lookup"><span data-stu-id="4155f-363">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-364">源代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="4155f-364">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-365">url</span><span class="sxs-lookup"><span data-stu-id="4155f-365">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="4155f-366">JavaScript 脚本名称或 url。</span><span class="sxs-lookup"><span data-stu-id="4155f-366">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-367">scopeChain</span><span class="sxs-lookup"><span data-stu-id="4155f-367">scopeChain</span></span></td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td><span data-ttu-id="4155f-368">此通话帧的作用域链。</span><span class="sxs-lookup"><span data-stu-id="4155f-368">Scope chain for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-369">此</span><span class="sxs-lookup"><span data-stu-id="4155f-369">this</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> <span data-ttu-id="4155f-370">此调用帧的对象。</span><span class="sxs-lookup"><span data-stu-id="4155f-370">object for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-371">returnValue</span><span class="sxs-lookup"><span data-stu-id="4155f-371">returnValue</span></span> <br/> <i><span data-ttu-id="4155f-372">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-372">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="4155f-373">如果函数位于返回点，则返回值。</span><span class="sxs-lookup"><span data-stu-id="4155f-373">The value being returned, if the function is at return point.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="scope"></a> <span data-ttu-id="4155f-374">范围</span><span class="sxs-lookup"><span data-stu-id="4155f-374">Scope</span></span> `object`

<span data-ttu-id="4155f-375">范围说明。</span><span class="sxs-lookup"><span data-stu-id="4155f-375">Scope description.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="4155f-376">属性</span><span class="sxs-lookup"><span data-stu-id="4155f-376">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="4155f-377">类型</span><span class="sxs-lookup"><span data-stu-id="4155f-377">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="4155f-378">允许的值：全局、本地、使用、关闭、捕获、阻止、脚本、评估、模块</span><span class="sxs-lookup"><span data-stu-id="4155f-378">Allowed values: global, local, with, closure, catch, block, script, eval, module</span></span></i></td>
            <td><span data-ttu-id="4155f-379">范围类型。</span><span class="sxs-lookup"><span data-stu-id="4155f-379">Scope type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-380">object</span><span class="sxs-lookup"><span data-stu-id="4155f-380">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="4155f-381">表示范围的对象。</span><span class="sxs-lookup"><span data-stu-id="4155f-381">Object representing the scope.</span></span> <span data-ttu-id="4155f-382">对于 <code>global</code> 和 <code>with</code> 作用域它表示实际对象; 对于作用域的其余部分，它是将 scope 变量枚举为其属性的人工瞬时对象。</span><span class="sxs-lookup"><span data-stu-id="4155f-382">For <code>global</code> and <code>with</code> scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-383">name</span><span class="sxs-lookup"><span data-stu-id="4155f-383">name</span></span> <br/> <i><span data-ttu-id="4155f-384">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-384">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-385">startLocation</span><span class="sxs-lookup"><span data-stu-id="4155f-385">startLocation</span></span> <br/> <i><span data-ttu-id="4155f-386">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-386">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-387">作用域在源代码中的起始位置</span><span class="sxs-lookup"><span data-stu-id="4155f-387">Location in the source code where scope starts</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="4155f-388">endLocation</span><span class="sxs-lookup"><span data-stu-id="4155f-388">endLocation</span></span> <br/> <i><span data-ttu-id="4155f-389">可选</span><span class="sxs-lookup"><span data-stu-id="4155f-389">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="4155f-390">范围结束的源代码中的位置</span><span class="sxs-lookup"><span data-stu-id="4155f-390">Location in the source code where scope ends</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="4155f-391">依赖关系</span><span class="sxs-lookup"><span data-stu-id="4155f-391">Dependencies</span></span>

[<span data-ttu-id="4155f-392">运行时</span><span class="sxs-lookup"><span data-stu-id="4155f-392">Runtime</span></span>](runtime.md)