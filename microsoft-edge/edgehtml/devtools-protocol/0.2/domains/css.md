---
description: CSS 域的引用。 此域公开 CSS 读/写操作。 样式表 (规则的所有 CSS 对象) 在相关对象的后续操作中使用的 `id` 关联。 每个对象类型都有一个特定的结构，并且这些结构在不同类型的对象之间 `id` 不可互换。 CSS 对象可以使用接受 DOM 节点 id `get*ForNode()` 的 (加载) 。 客户端还可以通过事件跟踪样式表，然后使用这些方法加载所需的 `styleSheetAdded` / `styleSheetRemoved` 样式表 `getStyleSheet[Text]()` 内容。
title: CSS 域 - DevTools 协议版本 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cf5efdef09b7e2d9041cd8536faaff8fb99a7f71
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232464"
---
# <span data-ttu-id="7159a-108">CSS</span><span class="sxs-lookup"><span data-stu-id="7159a-108">CSS</span></span>

<span data-ttu-id="7159a-109">此域公开 CSS 读/写操作。</span><span class="sxs-lookup"><span data-stu-id="7159a-109">This domain exposes CSS read/write operations.</span></span> <span data-ttu-id="7159a-110">样式表 (规则的所有 CSS 对象) 在相关对象的后续操作中使用的 `id` 关联。</span><span class="sxs-lookup"><span data-stu-id="7159a-110">All CSS objects (stylesheets, rules, and styles) have an associated `id` used in subsequent operations on the related object.</span></span> <span data-ttu-id="7159a-111">每个对象类型都有一个特定的结构，并且这些结构在不同类型的对象之间 `id` 不可互换。</span><span class="sxs-lookup"><span data-stu-id="7159a-111">Each object type has a specific `id` structure, and those are not interchangeable between objects of different kinds.</span></span> <span data-ttu-id="7159a-112">CSS 对象可以使用接受 DOM 节点 id `get*ForNode()` (的调用加载) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-112">CSS objects can be loaded using the `get*ForNode()` calls (which accept a DOM node id).</span></span> <span data-ttu-id="7159a-113">客户端还可以通过事件跟踪样式表，然后使用方法加载所需的 `styleSheetAdded` / `styleSheetRemoved` 样式表 `getStyleSheet[Text]()` 内容。</span><span class="sxs-lookup"><span data-stu-id="7159a-113">A client can also keep track of stylesheets via the `styleSheetAdded`/`styleSheetRemoved` events and subsequently load the required stylesheet contents using the `getStyleSheet[Text]()` methods.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="7159a-114">方法</span><span class="sxs-lookup"><span data-stu-id="7159a-114">Methods</span></span>**](#methods) | <span data-ttu-id="7159a-115">[enable](#enable)， [disable](#disable)， [getInlineStylesForNode](#getinlinestylesfornode)， [getMatchedStylesForNode](#getmatchedstylesfornode)， [getPlatformFontsForNode](#getplatformfontsfornode)， [getComputedStyleForNode](#getcomputedstylefornode)</span><span class="sxs-lookup"><span data-stu-id="7159a-115">[enable](#enable), [disable](#disable), [getInlineStylesForNode](#getinlinestylesfornode), [getMatchedStylesForNode](#getmatchedstylesfornode), [getPlatformFontsForNode](#getplatformfontsfornode), [getComputedStyleForNode](#getcomputedstylefornode)</span></span> |
| [**<span data-ttu-id="7159a-116">事件</span><span class="sxs-lookup"><span data-stu-id="7159a-116">Events</span></span>**](#events) | <span data-ttu-id="7159a-117">[styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved)</span><span class="sxs-lookup"><span data-stu-id="7159a-117">[styleSheetAdded](#stylesheetadded), [styleSheetChanged](#stylesheetchanged), [styleSheetRemoved](#stylesheetremoved)</span></span> |
| [**<span data-ttu-id="7159a-118">类型</span><span class="sxs-lookup"><span data-stu-id="7159a-118">Types</span></span>**](#types) | <span data-ttu-id="7159a-119">[](#stylesheetid)StyleSheetId、PseudoElementMatches、InheritedStyleEntry、RuleMatch、Value、SelectorList、CSSRule、SourceRange、ShorthandEntry、CSSStyle、CSSProperty、CSSMedia、MediaQuery、MediaQueryExpression、PlatformFontUsage、CSSKeyframesRule、CSSKeyframeRule、CSSComputedStyleProperty、CSSStyleSheetHeader [](#pseudoelementmatches) [](#inheritedstyleentry) [](#rulematch) [](#value) [](#selectorlist) [](#cssrule) [](#sourcerange) [](#shorthandentry) [](#cssstyle) [](#cssproperty) [](#cssmedia) [](#mediaquery) [](#mediaqueryexpression) [](#platformfontusage) [](#csskeyframesrule) [](#csskeyframerule) [](#csscomputedstyleproperty) [](#cssstylesheetheader)</span><span class="sxs-lookup"><span data-stu-id="7159a-119">[StyleSheetId](#stylesheetid), [PseudoElementMatches](#pseudoelementmatches), [InheritedStyleEntry](#inheritedstyleentry), [RuleMatch](#rulematch), [Value](#value), [SelectorList](#selectorlist), [CSSRule](#cssrule), [SourceRange](#sourcerange), [ShorthandEntry](#shorthandentry), [CSSStyle](#cssstyle), [CSSProperty](#cssproperty), [CSSMedia](#cssmedia), [MediaQuery](#mediaquery), [MediaQueryExpression](#mediaqueryexpression), [PlatformFontUsage](#platformfontusage), [CSSKeyframesRule](#csskeyframesrule), [CSSKeyframeRule](#csskeyframerule), [CSSComputedStyleProperty](#csscomputedstyleproperty), [CSSStyleSheetHeader](#cssstylesheetheader)</span></span> |
| [**<span data-ttu-id="7159a-120">依赖关系</span><span class="sxs-lookup"><span data-stu-id="7159a-120">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="7159a-121">DOM</span><span class="sxs-lookup"><span data-stu-id="7159a-121">DOM</span></span>](dom.md) |
## <span data-ttu-id="7159a-122">方法</span><span class="sxs-lookup"><span data-stu-id="7159a-122">Methods</span></span>

### <span data-ttu-id="7159a-123">“启用”</span><span class="sxs-lookup"><span data-stu-id="7159a-123">enable</span></span>
<span data-ttu-id="7159a-124">为给定页面启用 CSS 代理。</span><span class="sxs-lookup"><span data-stu-id="7159a-124">Enables the CSS agent for the given page.</span></span> <span data-ttu-id="7159a-125">客户端不应假定 CSS 代理已启用，直到收到此命令的结果。</span><span class="sxs-lookup"><span data-stu-id="7159a-125">Clients should not assume that the CSS agent has been enabled until the result of this command is received.</span></span>

</p>

---

### <span data-ttu-id="7159a-126">“禁用”</span><span class="sxs-lookup"><span data-stu-id="7159a-126">disable</span></span>
<span data-ttu-id="7159a-127">禁用给定页面的 CSS 代理。</span><span class="sxs-lookup"><span data-stu-id="7159a-127">Disables the CSS agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="7159a-128">getInlineStylesForNode</span><span class="sxs-lookup"><span data-stu-id="7159a-128">getInlineStylesForNode</span></span>
<span data-ttu-id="7159a-129">返回在"style" (中显式定义的内联样式，并隐式使用 DOM 属性) 标识的 DOM 节点 `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="7159a-129">Returns the styles defined inline (explicitly in the "style" attribute and implicitly, using DOM attributes) for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-130">参数</span><span class="sxs-lookup"><span data-stu-id="7159a-130">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-131">nodeId</span><span class="sxs-lookup"><span data-stu-id="7159a-131">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-132">返回</span><span class="sxs-lookup"><span data-stu-id="7159a-132">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-133">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="7159a-133">inlineStyle</span></span> <br /> <i><span data-ttu-id="7159a-134">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-134">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="7159a-135">指定 DOM 节点的内联样式。</span><span class="sxs-lookup"><span data-stu-id="7159a-135">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-136">attributesStyle</span><span class="sxs-lookup"><span data-stu-id="7159a-136">attributesStyle</span></span> <br /> <i><span data-ttu-id="7159a-137">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-137">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="7159a-138">属性定义的元素样式 (例如，由"width=20 height=100%") 。</span><span class="sxs-lookup"><span data-stu-id="7159a-138">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="7159a-139">getMatchedStylesForNode</span><span class="sxs-lookup"><span data-stu-id="7159a-139">getMatchedStylesForNode</span></span>
<span data-ttu-id="7159a-140">返回由 标识的 DOM 节点的请求样式 `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="7159a-140">Returns requested styles for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-141">参数</span><span class="sxs-lookup"><span data-stu-id="7159a-141">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-142">nodeId</span><span class="sxs-lookup"><span data-stu-id="7159a-142">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-143">返回</span><span class="sxs-lookup"><span data-stu-id="7159a-143">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-144">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="7159a-144">inlineStyle</span></span> <br /> <i><span data-ttu-id="7159a-145">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-145">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="7159a-146">指定 DOM 节点的内联样式。</span><span class="sxs-lookup"><span data-stu-id="7159a-146">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-147">attributesStyle</span><span class="sxs-lookup"><span data-stu-id="7159a-147">attributesStyle</span></span> <br /> <i><span data-ttu-id="7159a-148">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-148">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="7159a-149">属性定义的元素样式 (例如，由"width=20 height=100%") 。</span><span class="sxs-lookup"><span data-stu-id="7159a-149">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-150">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="7159a-150">matchedCSSRules</span></span> <br /> <i><span data-ttu-id="7159a-151">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-151">optional</span></span></i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="7159a-152">匹配此节点的 CSS 规则，来自所有适用的样式表。</span><span class="sxs-lookup"><span data-stu-id="7159a-152">CSS rules matching this node, from all applicable stylesheets.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-153">pseudoElements</span><span class="sxs-lookup"><span data-stu-id="7159a-153">pseudoElements</span></span> <br /> <i><span data-ttu-id="7159a-154">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-154">optional</span></span></i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td><span data-ttu-id="7159a-155">此节点的伪样式匹配。</span><span class="sxs-lookup"><span data-stu-id="7159a-155">Pseudo style matches for this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-156">继承</span><span class="sxs-lookup"><span data-stu-id="7159a-156">inherited</span></span> <br /> <i><span data-ttu-id="7159a-157">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-157">optional</span></span></i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td><span data-ttu-id="7159a-158">继承的样式链 (从直接节点父元素一直继承到 DOM 树根) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-158">A chain of inherited styles (from the immediate node parent up to the DOM tree root).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-159">cssKeyframesRules</span><span class="sxs-lookup"><span data-stu-id="7159a-159">cssKeyframesRules</span></span> <br /> <i><span data-ttu-id="7159a-160">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-160">optional</span></span></i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td><span data-ttu-id="7159a-161">匹配此节点的 CSS 关键帧动画列表。</span><span class="sxs-lookup"><span data-stu-id="7159a-161">A list of CSS keyframed animations matching this node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="7159a-162">getPlatformFontsForNode</span><span class="sxs-lookup"><span data-stu-id="7159a-162">getPlatformFontsForNode</span></span>
<span data-ttu-id="7159a-163">请求有关我们在给定节点中呈现子 TextNodes 的平台字体的信息。</span><span class="sxs-lookup"><span data-stu-id="7159a-163">Requests information about platform fonts which we used to render child TextNodes in the given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-164">参数</span><span class="sxs-lookup"><span data-stu-id="7159a-164">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-165">nodeId</span><span class="sxs-lookup"><span data-stu-id="7159a-165">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-166">返回</span><span class="sxs-lookup"><span data-stu-id="7159a-166">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-167">字体</span><span class="sxs-lookup"><span data-stu-id="7159a-167">fonts</span></span></td>
            <td><a href="#platformfontusage"><code class="flyout">PlatformFontUsage[]</code></a></td>
            <td><span data-ttu-id="7159a-168">每个已使用平台字体的使用情况统计信息。</span><span class="sxs-lookup"><span data-stu-id="7159a-168">Usage statistics for every employed platform font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="7159a-169">getComputedStyleForNode</span><span class="sxs-lookup"><span data-stu-id="7159a-169">getComputedStyleForNode</span></span>
<span data-ttu-id="7159a-170">返回由 标识的 DOM 节点的计算样式 `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="7159a-170">Returns the computed style for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-171">参数</span><span class="sxs-lookup"><span data-stu-id="7159a-171">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-172">nodeId</span><span class="sxs-lookup"><span data-stu-id="7159a-172">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-173">返回</span><span class="sxs-lookup"><span data-stu-id="7159a-173">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-174">computedStyle</span><span class="sxs-lookup"><span data-stu-id="7159a-174">computedStyle</span></span></td>
            <td><a href="#csscomputedstyleproperty"><code class="flyout">CSSComputedStyleProperty[]</code></a></td>
            <td><span data-ttu-id="7159a-175">指定 DOM 节点的计算样式。</span><span class="sxs-lookup"><span data-stu-id="7159a-175">Computed style for the specified DOM node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="7159a-176">事件</span><span class="sxs-lookup"><span data-stu-id="7159a-176">Events</span></span>

### <span data-ttu-id="7159a-177">styleSheetAdded</span><span class="sxs-lookup"><span data-stu-id="7159a-177">styleSheetAdded</span></span>
<span data-ttu-id="7159a-178">每当添加活动文档样式表时触发。</span><span class="sxs-lookup"><span data-stu-id="7159a-178">Fired whenever an active document stylesheet is added.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-179">参数</span><span class="sxs-lookup"><span data-stu-id="7159a-179">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-180">标题</span><span class="sxs-lookup"><span data-stu-id="7159a-180">header</span></span></td>
            <td><a href="#cssstylesheetheader"><code class="flyout">CSSStyleSheetHeader</code></a></td>
            <td><span data-ttu-id="7159a-181">添加了样式表 metainfo。</span><span class="sxs-lookup"><span data-stu-id="7159a-181">Added stylesheet metainfo.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="7159a-182">styleSheetChanged</span><span class="sxs-lookup"><span data-stu-id="7159a-182">styleSheetChanged</span></span>
<span data-ttu-id="7159a-183">每当样式表因客户端操作而更改时触发。</span><span class="sxs-lookup"><span data-stu-id="7159a-183">Fired whenever a stylesheet is changed as a result of the client operation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-184">参数</span><span class="sxs-lookup"><span data-stu-id="7159a-184">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-185">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-185">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="7159a-186">styleSheetRemoved</span><span class="sxs-lookup"><span data-stu-id="7159a-186">styleSheetRemoved</span></span>
<span data-ttu-id="7159a-187">每当删除活动文档样式表时触发。</span><span class="sxs-lookup"><span data-stu-id="7159a-187">Fired whenever an active document stylesheet is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-188">参数</span><span class="sxs-lookup"><span data-stu-id="7159a-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-189">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-189">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="7159a-190">已删除样式表的标识符。</span><span class="sxs-lookup"><span data-stu-id="7159a-190">Identifier of the removed stylesheet.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="7159a-191">类型</span><span class="sxs-lookup"><span data-stu-id="7159a-191">Types</span></span>

### <a name="stylesheetid"></a> <span data-ttu-id="7159a-192">StyleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-192">StyleSheetId</span></span> `string`



</p>

---

### <a name="pseudoelementmatches"></a> <span data-ttu-id="7159a-193">PseudoElementMatches</span><span class="sxs-lookup"><span data-stu-id="7159a-193">PseudoElementMatches</span></span> `object`

<span data-ttu-id="7159a-194">单个伪样式的 CSS 规则集合。</span><span class="sxs-lookup"><span data-stu-id="7159a-194">CSS rule collection for a single pseudo style.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-195">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-195">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-196">pseudoType</span><span class="sxs-lookup"><span data-stu-id="7159a-196">pseudoType</span></span></td>
            <td><a href="dom.md#pseudotype"><code class="flyout">DOM.PseudoType</code></a></td>
            <td><span data-ttu-id="7159a-197">伪元素类型。</span><span class="sxs-lookup"><span data-stu-id="7159a-197">Pseudo element type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-198">匹配</span><span class="sxs-lookup"><span data-stu-id="7159a-198">matches</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="7159a-199">适用于伪样式的 CSS 规则的匹配项。</span><span class="sxs-lookup"><span data-stu-id="7159a-199">Matches of CSS rules applicable to the pseudo style.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> <span data-ttu-id="7159a-200">InheritedStyleEntry</span><span class="sxs-lookup"><span data-stu-id="7159a-200">InheritedStyleEntry</span></span> `object`

<span data-ttu-id="7159a-201">继承的来自上级节点的 CSS 规则集合。</span><span class="sxs-lookup"><span data-stu-id="7159a-201">Inherited CSS rule collection from ancestor node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-202">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-202">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-203">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="7159a-203">inlineStyle</span></span> <br /> <i><span data-ttu-id="7159a-204">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-204">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="7159a-205">上级节点的内联样式（如果有）在样式继承链中。</span><span class="sxs-lookup"><span data-stu-id="7159a-205">The ancestor node's inline style, if any, in the style inheritance chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-206">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="7159a-206">matchedCSSRules</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="7159a-207">与样式继承链中的上级节点匹配的 CSS 规则匹配。</span><span class="sxs-lookup"><span data-stu-id="7159a-207">Matches of CSS rules matching the ancestor node in the style inheritance chain.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="rulematch"></a> <span data-ttu-id="7159a-208">RuleMatch</span><span class="sxs-lookup"><span data-stu-id="7159a-208">RuleMatch</span></span> `object`

<span data-ttu-id="7159a-209">匹配 CSS 规则的数据。</span><span class="sxs-lookup"><span data-stu-id="7159a-209">Match data for a CSS rule.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-210">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-210">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-211">rule</span><span class="sxs-lookup"><span data-stu-id="7159a-211">rule</span></span></td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td><span data-ttu-id="7159a-212">匹配中的 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="7159a-212">CSS rule in the match.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> <span data-ttu-id="7159a-213">值</span><span class="sxs-lookup"><span data-stu-id="7159a-213">Value</span></span> `object`

<span data-ttu-id="7159a-214">简单选择器 (在选择器列表中用逗号) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-214">Data for a simple selector (these are delimited by commas in a selector list).</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-215">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-215">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-216">文本</span><span class="sxs-lookup"><span data-stu-id="7159a-216">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-217">值文本。</span><span class="sxs-lookup"><span data-stu-id="7159a-217">Value text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-218">范围</span><span class="sxs-lookup"><span data-stu-id="7159a-218">range</span></span> <br /> <i><span data-ttu-id="7159a-219">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-219">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="7159a-220">基础资源资源中的值 (（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="7159a-220">Value range in the underlying resource (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="selectorlist"></a> <span data-ttu-id="7159a-221">SelectorList</span><span class="sxs-lookup"><span data-stu-id="7159a-221">SelectorList</span></span> `object`

<span data-ttu-id="7159a-222">选择器列表数据。</span><span class="sxs-lookup"><span data-stu-id="7159a-222">Selector list data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-223">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-223">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-224">选择器</span><span class="sxs-lookup"><span data-stu-id="7159a-224">selectors</span></span></td>
            <td><a href="#value"><code class="flyout">Value[]</code></a></td>
            <td><span data-ttu-id="7159a-225">列表中的选择器。</span><span class="sxs-lookup"><span data-stu-id="7159a-225">Selectors in the list.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-226">文本</span><span class="sxs-lookup"><span data-stu-id="7159a-226">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-227">规则选择器文本。</span><span class="sxs-lookup"><span data-stu-id="7159a-227">Rule selector text.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssrule"></a> <span data-ttu-id="7159a-228">CSSRule</span><span class="sxs-lookup"><span data-stu-id="7159a-228">CSSRule</span></span> `object`

<span data-ttu-id="7159a-229">CSS 规则表示形式。</span><span class="sxs-lookup"><span data-stu-id="7159a-229">CSS rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-230">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-230">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-231">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-231">styleSheetId</span></span> <br /> <i><span data-ttu-id="7159a-232">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-232">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="7159a-233">此规则 (用户代理样式表和用户指定的样式表规则) css 样式表标识符。</span><span class="sxs-lookup"><span data-stu-id="7159a-233">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-234">selectorList</span><span class="sxs-lookup"><span data-stu-id="7159a-234">selectorList</span></span> <br /> <i><span data-ttu-id="7159a-235">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-235">optional</span></span></i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td><span data-ttu-id="7159a-236">规则选择器数据。</span><span class="sxs-lookup"><span data-stu-id="7159a-236">Rule selector data.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-237">origin</span><span class="sxs-lookup"><span data-stu-id="7159a-237">origin</span></span> <br /> <i><span data-ttu-id="7159a-238">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-238">optional</span></span></i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="7159a-239">父样式表的原点。</span><span class="sxs-lookup"><span data-stu-id="7159a-239">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-240">style</span><span class="sxs-lookup"><span data-stu-id="7159a-240">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="7159a-241">关联的样式声明。</span><span class="sxs-lookup"><span data-stu-id="7159a-241">Associated style declaration.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-242">媒体</span><span class="sxs-lookup"><span data-stu-id="7159a-242">media</span></span> <br /> <i><span data-ttu-id="7159a-243">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-243">optional</span></span></i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td><span data-ttu-id="7159a-244">媒体列表数组 (涉及媒体查询的) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-244">Media list array (for rules involving media queries).</span></span> <span data-ttu-id="7159a-245">该数组枚举从最里层开始向外延伸的媒体查询。</span><span class="sxs-lookup"><span data-stu-id="7159a-245">The array enumerates media queries starting with the innermost one, going outwards.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> <span data-ttu-id="7159a-246">SourceRange</span><span class="sxs-lookup"><span data-stu-id="7159a-246">SourceRange</span></span> `object`

<span data-ttu-id="7159a-247">资源中的文本范围。</span><span class="sxs-lookup"><span data-stu-id="7159a-247">Text range within a resource.</span></span> <span data-ttu-id="7159a-248">所有数字都从零开始。</span><span class="sxs-lookup"><span data-stu-id="7159a-248">All numbers are zero-based.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-249">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-249">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-250">startLine</span><span class="sxs-lookup"><span data-stu-id="7159a-250">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="7159a-251">范围的起始行。</span><span class="sxs-lookup"><span data-stu-id="7159a-251">Start line of range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-252">startColumn</span><span class="sxs-lookup"><span data-stu-id="7159a-252">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="7159a-253">区域起始列 (包含) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-253">Start column of range (inclusive).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-254">endLine</span><span class="sxs-lookup"><span data-stu-id="7159a-254">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="7159a-255">范围的结束行</span><span class="sxs-lookup"><span data-stu-id="7159a-255">End line of range</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-256">endColumn</span><span class="sxs-lookup"><span data-stu-id="7159a-256">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="7159a-257">区域结束列 (独占) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-257">End column of range (exclusive).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="shorthandentry"></a> <span data-ttu-id="7159a-258">ShorthandEntry</span><span class="sxs-lookup"><span data-stu-id="7159a-258">ShorthandEntry</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-259">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-259">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-260">name</span><span class="sxs-lookup"><span data-stu-id="7159a-260">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-261">速记名称。</span><span class="sxs-lookup"><span data-stu-id="7159a-261">Shorthand name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-262">值</span><span class="sxs-lookup"><span data-stu-id="7159a-262">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-263">速记值。</span><span class="sxs-lookup"><span data-stu-id="7159a-263">Shorthand value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-264">重要</span><span class="sxs-lookup"><span data-stu-id="7159a-264">important</span></span> <br /> <i><span data-ttu-id="7159a-265">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-265">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-266">如果属性不存在，则 `false` ("！important") 。</span><span class="sxs-lookup"><span data-stu-id="7159a-266">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstyle"></a> <span data-ttu-id="7159a-267">CSSStyle</span><span class="sxs-lookup"><span data-stu-id="7159a-267">CSSStyle</span></span> `object`

<span data-ttu-id="7159a-268">CSS 样式表示形式。</span><span class="sxs-lookup"><span data-stu-id="7159a-268">CSS style representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-269">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-269">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-270">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-270">styleSheetId</span></span> <br /> <i><span data-ttu-id="7159a-271">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-271">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="7159a-272">此规则 (用户代理样式表和用户指定的样式表规则) css 样式表标识符。</span><span class="sxs-lookup"><span data-stu-id="7159a-272">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-273">cssProperties</span><span class="sxs-lookup"><span data-stu-id="7159a-273">cssProperties</span></span></td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td><span data-ttu-id="7159a-274">样式中的 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="7159a-274">CSS properties in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-275">shorthandEntries</span><span class="sxs-lookup"><span data-stu-id="7159a-275">shorthandEntries</span></span></td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td><span data-ttu-id="7159a-276">在样式中发现的所有速记的计算值。</span><span class="sxs-lookup"><span data-stu-id="7159a-276">Computed values for all shorthands found in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-277">cssText</span><span class="sxs-lookup"><span data-stu-id="7159a-277">cssText</span></span> <br /> <i><span data-ttu-id="7159a-278">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-278">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-279">样式声明文本 (（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="7159a-279">Style declaration text (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-280">范围</span><span class="sxs-lookup"><span data-stu-id="7159a-280">range</span></span> <br /> <i><span data-ttu-id="7159a-281">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-281">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="7159a-282">包含样式表样式表的样式声明 (（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="7159a-282">Style declaration range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssproperty"></a> <span data-ttu-id="7159a-283">CSSProperty</span><span class="sxs-lookup"><span data-stu-id="7159a-283">CSSProperty</span></span> `object`

<span data-ttu-id="7159a-284">CSS 属性声明数据。</span><span class="sxs-lookup"><span data-stu-id="7159a-284">CSS property declaration data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-285">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-285">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-286">name</span><span class="sxs-lookup"><span data-stu-id="7159a-286">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-287">属性名称。</span><span class="sxs-lookup"><span data-stu-id="7159a-287">The property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-288">值</span><span class="sxs-lookup"><span data-stu-id="7159a-288">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-289">属性值。</span><span class="sxs-lookup"><span data-stu-id="7159a-289">The property value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-290">重要</span><span class="sxs-lookup"><span data-stu-id="7159a-290">important</span></span> <br /> <i><span data-ttu-id="7159a-291">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-291">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-292">如果属性不存在，则 `false` ("！important") 。</span><span class="sxs-lookup"><span data-stu-id="7159a-292">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-293">隐式</span><span class="sxs-lookup"><span data-stu-id="7159a-293">implicit</span></span> <br /> <i><span data-ttu-id="7159a-294">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-294">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-295">如果不存在此属性， (`false` 是否隐式) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-295">Whether the property is implicit (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-296">文本</span><span class="sxs-lookup"><span data-stu-id="7159a-296">text</span></span> <br /> <i><span data-ttu-id="7159a-297">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-297">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-298">样式中指定的全属性文本。</span><span class="sxs-lookup"><span data-stu-id="7159a-298">The full property text as specified in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-299">parsedOk</span><span class="sxs-lookup"><span data-stu-id="7159a-299">parsedOk</span></span> <br /> <i><span data-ttu-id="7159a-300">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-300">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-301">浏览器是否理解该属性 (是否表示 `true` 不存在) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-301">Whether the property is understood by the browser (implies `true` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-302">已禁用</span><span class="sxs-lookup"><span data-stu-id="7159a-302">disabled</span></span> <br /> <i><span data-ttu-id="7159a-303">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-303">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-304">用户是否禁用此属性 (基于源的属性是否) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-304">Whether the property is disabled by the user (present for source-based properties only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-305">范围</span><span class="sxs-lookup"><span data-stu-id="7159a-305">range</span></span> <br /> <i><span data-ttu-id="7159a-306">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-306">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="7159a-307">括在样式声明中的整个属性 (（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="7159a-307">The entire property range in the enclosing style declaration (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssmedia"></a> <span data-ttu-id="7159a-308">CSSMedia</span><span class="sxs-lookup"><span data-stu-id="7159a-308">CSSMedia</span></span> `object`

<span data-ttu-id="7159a-309">CSS 媒体规则描述符。</span><span class="sxs-lookup"><span data-stu-id="7159a-309">CSS media rule descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-310">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-310">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-311">文本</span><span class="sxs-lookup"><span data-stu-id="7159a-311">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-312">媒体查询文本。</span><span class="sxs-lookup"><span data-stu-id="7159a-312">Media query text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-313">source</span><span class="sxs-lookup"><span data-stu-id="7159a-313">source</span></span></td>
            <td><code class="flyout">string</code> <br /> <i><span data-ttu-id="7159a-314">允许的值：mediaRule、importRule、linkedSheet、inlineSheet</span><span class="sxs-lookup"><span data-stu-id="7159a-314">Allowed values: mediaRule, importRule, linkedSheet, inlineSheet</span></span></i></td>
            <td><span data-ttu-id="7159a-315">媒体查询的源："mediaRule"（如果由 @media 规则指定，如果由 @import 规则指定，则"importRule";如果由链接样式表的 LINK 标记中的"media"属性指定，则"linkedSheet";如果由内联样式表的 STYLE 标记中的"media"属性指定，则指定"inlineSheet"。</span><span class="sxs-lookup"><span data-stu-id="7159a-315">Source of the media query: "mediaRule" if specified by a @media rule, "importRule" if specified by an @import rule, "linkedSheet" if specified by a "media" attribute in a linked stylesheet's LINK tag, "inlineSheet" if specified by a "media" attribute in an inline stylesheet's STYLE tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-316">sourceURL</span><span class="sxs-lookup"><span data-stu-id="7159a-316">sourceURL</span></span> <br /> <i><span data-ttu-id="7159a-317">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-317">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-318">包含媒体查询说明的文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="7159a-318">URL of the document containing the media query description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-319">范围</span><span class="sxs-lookup"><span data-stu-id="7159a-319">range</span></span> <br /> <i><span data-ttu-id="7159a-320">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-320">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="7159a-321">关联的规则 (@media 或 @import) 标题范围包含在样式表 (中（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="7159a-321">The associated rule (@media or @import) header range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-322">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-322">styleSheetId</span></span> <br /> <i><span data-ttu-id="7159a-323">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-323">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="7159a-324">包含此对象的样式表的标识符 (（如果存在) ）。</span><span class="sxs-lookup"><span data-stu-id="7159a-324">Identifier of the stylesheet containing this object (if exists).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-325">mediaList</span><span class="sxs-lookup"><span data-stu-id="7159a-325">mediaList</span></span> <br /> <i><span data-ttu-id="7159a-326">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-326">optional</span></span></i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td><span data-ttu-id="7159a-327">媒体查询数组。</span><span class="sxs-lookup"><span data-stu-id="7159a-327">Array of media queries.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaquery"></a> <span data-ttu-id="7159a-328">MediaQuery</span><span class="sxs-lookup"><span data-stu-id="7159a-328">MediaQuery</span></span> `object`

<span data-ttu-id="7159a-329">媒体查询描述符。</span><span class="sxs-lookup"><span data-stu-id="7159a-329">Media query descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-330">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-330">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-331">表达式</span><span class="sxs-lookup"><span data-stu-id="7159a-331">expressions</span></span></td>
            <td><a href="#mediaqueryexpression"><code class="flyout">MediaQueryExpression[]</code></a></td>
            <td><span data-ttu-id="7159a-332">媒体查询表达式的数组。</span><span class="sxs-lookup"><span data-stu-id="7159a-332">Array of media query expressions.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-333">active</span><span class="sxs-lookup"><span data-stu-id="7159a-333">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-334">是否满足媒体查询条件。</span><span class="sxs-lookup"><span data-stu-id="7159a-334">Whether the media query condition is satisfied.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaqueryexpression"></a> <span data-ttu-id="7159a-335">MediaQueryExpression</span><span class="sxs-lookup"><span data-stu-id="7159a-335">MediaQueryExpression</span></span> `object`

<span data-ttu-id="7159a-336">媒体查询表达式描述符。</span><span class="sxs-lookup"><span data-stu-id="7159a-336">Media query expression descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-337">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-338">值</span><span class="sxs-lookup"><span data-stu-id="7159a-338">value</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="7159a-339">媒体查询表达式值。</span><span class="sxs-lookup"><span data-stu-id="7159a-339">Media query expression value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-340">unit</span><span class="sxs-lookup"><span data-stu-id="7159a-340">unit</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-341">媒体查询表达式单位。</span><span class="sxs-lookup"><span data-stu-id="7159a-341">Media query expression units.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-342">功能</span><span class="sxs-lookup"><span data-stu-id="7159a-342">feature</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-343">媒体查询表达式功能。</span><span class="sxs-lookup"><span data-stu-id="7159a-343">Media query expression feature.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-344">valueRange</span><span class="sxs-lookup"><span data-stu-id="7159a-344">valueRange</span></span> <br /> <i><span data-ttu-id="7159a-345">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-345">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="7159a-346">括起样式表内值文本的关联区域 (（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="7159a-346">The associated range of the value text in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-347">computedLength</span><span class="sxs-lookup"><span data-stu-id="7159a-347">computedLength</span></span> <br /> <i><span data-ttu-id="7159a-348">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-348">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="7159a-349">如果适用，则计算媒体 (表达式) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-349">Computed length of media query expression (if applicable).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> <span data-ttu-id="7159a-350">PlatformFontUsage</span><span class="sxs-lookup"><span data-stu-id="7159a-350">PlatformFontUsage</span></span> `object`

<span data-ttu-id="7159a-351">有关使用给定字体呈现的字形数量的信息。</span><span class="sxs-lookup"><span data-stu-id="7159a-351">Information about amount of glyphs that were rendered with given font.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-352">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-352">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-353">familyName</span><span class="sxs-lookup"><span data-stu-id="7159a-353">familyName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-354">平台报告的字体系列名称。</span><span class="sxs-lookup"><span data-stu-id="7159a-354">Font's family name reported by platform.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-355">isCustomFont</span><span class="sxs-lookup"><span data-stu-id="7159a-355">isCustomFont</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-356">指示字体是在本地下载还是解析。</span><span class="sxs-lookup"><span data-stu-id="7159a-356">Indicates if the font was downloaded or resolved locally.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-357">glyphCount</span><span class="sxs-lookup"><span data-stu-id="7159a-357">glyphCount</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="7159a-358">用此字体呈现的字形数量。</span><span class="sxs-lookup"><span data-stu-id="7159a-358">Amount of glyphs that were rendered with this font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframesrule"></a> <span data-ttu-id="7159a-359">CSSKeyframesRule</span><span class="sxs-lookup"><span data-stu-id="7159a-359">CSSKeyframesRule</span></span> `object`

<span data-ttu-id="7159a-360">CSS 关键帧规则表示形式。</span><span class="sxs-lookup"><span data-stu-id="7159a-360">CSS keyframes rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-361">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-361">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-362">animationName</span><span class="sxs-lookup"><span data-stu-id="7159a-362">animationName</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="7159a-363">动画名称。</span><span class="sxs-lookup"><span data-stu-id="7159a-363">Animation name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-364">关键帧</span><span class="sxs-lookup"><span data-stu-id="7159a-364">keyframes</span></span></td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td><span data-ttu-id="7159a-365">关键帧列表。</span><span class="sxs-lookup"><span data-stu-id="7159a-365">List of keyframes.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframerule"></a> <span data-ttu-id="7159a-366">CSSKeyframeRule</span><span class="sxs-lookup"><span data-stu-id="7159a-366">CSSKeyframeRule</span></span> `object`

<span data-ttu-id="7159a-367">CSS 关键帧规则表示形式。</span><span class="sxs-lookup"><span data-stu-id="7159a-367">CSS keyframe rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-368">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-369">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-369">styleSheetId</span></span> <br /> <i><span data-ttu-id="7159a-370">可选</span><span class="sxs-lookup"><span data-stu-id="7159a-370">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="7159a-371">此规则 (用户代理样式表和用户指定的样式表规则) css 样式表标识符。</span><span class="sxs-lookup"><span data-stu-id="7159a-371">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-372">origin</span><span class="sxs-lookup"><span data-stu-id="7159a-372">origin</span></span></td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="7159a-373">父样式表的原点。</span><span class="sxs-lookup"><span data-stu-id="7159a-373">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-374">keyText</span><span class="sxs-lookup"><span data-stu-id="7159a-374">keyText</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="7159a-375">关联的键文本。</span><span class="sxs-lookup"><span data-stu-id="7159a-375">Associated key text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-376">style</span><span class="sxs-lookup"><span data-stu-id="7159a-376">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="7159a-377">关联的样式声明。</span><span class="sxs-lookup"><span data-stu-id="7159a-377">Associated style declaration.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csscomputedstyleproperty"></a> <span data-ttu-id="7159a-378">CSSComputedStyleProperty</span><span class="sxs-lookup"><span data-stu-id="7159a-378">CSSComputedStyleProperty</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-379">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-379">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-380">name</span><span class="sxs-lookup"><span data-stu-id="7159a-380">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-381">计算样式属性名称。</span><span class="sxs-lookup"><span data-stu-id="7159a-381">Computed style property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-382">值</span><span class="sxs-lookup"><span data-stu-id="7159a-382">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-383">计算样式属性值。</span><span class="sxs-lookup"><span data-stu-id="7159a-383">Computed style property value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstylesheetheader"></a> <span data-ttu-id="7159a-384">CSSStyleSheetHeader</span><span class="sxs-lookup"><span data-stu-id="7159a-384">CSSStyleSheetHeader</span></span> `object`

<span data-ttu-id="7159a-385">CSS 样式表 metainformation。</span><span class="sxs-lookup"><span data-stu-id="7159a-385">CSS stylesheet metainformation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="7159a-386">属性</span><span class="sxs-lookup"><span data-stu-id="7159a-386">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="7159a-387">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="7159a-387">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="7159a-388">样式表标识符。</span><span class="sxs-lookup"><span data-stu-id="7159a-388">The stylesheet identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-389">sourceURL</span><span class="sxs-lookup"><span data-stu-id="7159a-389">sourceURL</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="7159a-390">样式表资源 URL。</span><span class="sxs-lookup"><span data-stu-id="7159a-390">Stylesheet resource URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-391">已禁用</span><span class="sxs-lookup"><span data-stu-id="7159a-391">disabled</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-392">表示是否禁用样式表。</span><span class="sxs-lookup"><span data-stu-id="7159a-392">Denotes whether the stylesheet is disabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-393">isInline</span><span class="sxs-lookup"><span data-stu-id="7159a-393">isInline</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="7159a-394">此样式表是否由分析程序为 STYLE 标记创建。</span><span class="sxs-lookup"><span data-stu-id="7159a-394">Whether this stylesheet is created for STYLE tag by parser.</span></span> <span data-ttu-id="7159a-395">未为 document.written STYLE 标记设置此标志。</span><span class="sxs-lookup"><span data-stu-id="7159a-395">This flag is not set for document.written STYLE tags.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-396">startLine</span><span class="sxs-lookup"><span data-stu-id="7159a-396">startLine</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="7159a-397">资源中的样式表的行偏移量 (从零开始) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-397">Line offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-398">startColumn</span><span class="sxs-lookup"><span data-stu-id="7159a-398">startColumn</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="7159a-399">资源中的样式表的列偏移量 (从零开始) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-399">Column offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="7159a-400">length</span><span class="sxs-lookup"><span data-stu-id="7159a-400">length</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="7159a-401">内容的大小以 (字符表示) 。</span><span class="sxs-lookup"><span data-stu-id="7159a-401">Size of the content (in characters).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="7159a-402">依赖关系</span><span class="sxs-lookup"><span data-stu-id="7159a-402">Dependencies</span></span>

[<span data-ttu-id="7159a-403">DOM</span><span class="sxs-lookup"><span data-stu-id="7159a-403">DOM</span></span>](dom.md)
