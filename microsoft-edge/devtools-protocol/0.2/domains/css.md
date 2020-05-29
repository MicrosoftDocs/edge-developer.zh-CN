---
description: 对 CSS 域的引用。 此域公开 CSS 读/写操作。 所有 CSS 对象（样式表、规则和样式）在 `id` 相关对象的后续操作中都有相关联的已使用。 每个对象类型都有一个特定的 `id` 结构，它们在不同类型的对象之间不能互换。 可以使用 `get*ForNode()` 调用（接受 DOM 节点 id）加载 CSS 对象。 客户端还可以通过事件跟踪样式表 `styleSheetAdded` / `styleSheetRemoved` ，随后使用这些方法加载所需的样式表内容 `getStyleSheet[Text]()` 。
title: CSS 域-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 939eda0ae2f5228657d35899ab75b39493eff917
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563411"
---
# <span data-ttu-id="b1ac8-108">CSS</span><span class="sxs-lookup"><span data-stu-id="b1ac8-108">CSS</span></span>
<span data-ttu-id="b1ac8-109">此域公开 CSS 读/写操作。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-109">This domain exposes CSS read/write operations.</span></span> <span data-ttu-id="b1ac8-110">所有 CSS 对象（样式表、规则和样式）在 `id` 相关对象的后续操作中都有相关联的已使用。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-110">All CSS objects (stylesheets, rules, and styles) have an associated `id` used in subsequent operations on the related object.</span></span> <span data-ttu-id="b1ac8-111">每个对象类型都有一个特定的 `id` 结构，它们在不同类型的对象之间不能互换。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-111">Each object type has a specific `id` structure, and those are not interchangeable between objects of different kinds.</span></span> <span data-ttu-id="b1ac8-112">可以使用 `get*ForNode()` 调用（接受 DOM 节点 id）加载 CSS 对象。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-112">CSS objects can be loaded using the `get*ForNode()` calls (which accept a DOM node id).</span></span> <span data-ttu-id="b1ac8-113">客户端还可以通过事件跟踪样式表 `styleSheetAdded` / `styleSheetRemoved` ，随后使用这些方法加载所需的样式表内容 `getStyleSheet[Text]()` 。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-113">A client can also keep track of stylesheets via the `styleSheetAdded`/`styleSheetRemoved` events and subsequently load the required stylesheet contents using the `getStyleSheet[Text]()` methods.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="b1ac8-114">方法</span><span class="sxs-lookup"><span data-stu-id="b1ac8-114">Methods</span></span>**](#methods) | <span data-ttu-id="b1ac8-115">[enable](#enable)、 [disable](#disable)、 [getInlineStylesForNode](#getinlinestylesfornode)、 [getMatchedStylesForNode](#getmatchedstylesfornode)、 [getPlatformFontsForNode](#getplatformfontsfornode)、 [getComputedStyleForNode](#getcomputedstylefornode)</span><span class="sxs-lookup"><span data-stu-id="b1ac8-115">[enable](#enable), [disable](#disable), [getInlineStylesForNode](#getinlinestylesfornode), [getMatchedStylesForNode](#getmatchedstylesfornode), [getPlatformFontsForNode](#getplatformfontsfornode), [getComputedStyleForNode](#getcomputedstylefornode)</span></span> |
| [**<span data-ttu-id="b1ac8-116">事件</span><span class="sxs-lookup"><span data-stu-id="b1ac8-116">Events</span></span>**](#events) | <span data-ttu-id="b1ac8-117">[styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved)</span><span class="sxs-lookup"><span data-stu-id="b1ac8-117">[styleSheetAdded](#stylesheetadded), [styleSheetChanged](#stylesheetchanged), [styleSheetRemoved](#stylesheetremoved)</span></span> |
| [**<span data-ttu-id="b1ac8-118">类型</span><span class="sxs-lookup"><span data-stu-id="b1ac8-118">Types</span></span>**](#types) | <span data-ttu-id="b1ac8-119">[StyleSheetId](#stylesheetid)、 [PseudoElementMatches](#pseudoelementmatches)、 [InheritedStyleEntry](#inheritedstyleentry)、 [RuleMatch](#rulematch)、 [Value](#value)、 [SelectorList](#selectorlist)、 [CSSRule](#cssrule)、 [SourceRange](#sourcerange)、 [ShorthandEntry](#shorthandentry)、 [CSSStyle](#cssstyle)、 [CSSProperty](#cssproperty)、 [CSSMedia](#cssmedia)、 [MediaQuery](#mediaquery)、 [MediaQueryExpression、PlatformFontUsage](#mediaqueryexpression) [、CSSKeyframesRule](#platformfontusage) [、CSSKeyframeRule](#csskeyframesrule) [、CSSComputedStyleProperty](#csskeyframerule) [、CSSStyleSheetHeader](#csscomputedstyleproperty)、、 [、、](#cssstylesheetheader) 、、</span><span class="sxs-lookup"><span data-stu-id="b1ac8-119">[StyleSheetId](#stylesheetid), [PseudoElementMatches](#pseudoelementmatches), [InheritedStyleEntry](#inheritedstyleentry), [RuleMatch](#rulematch), [Value](#value), [SelectorList](#selectorlist), [CSSRule](#cssrule), [SourceRange](#sourcerange), [ShorthandEntry](#shorthandentry), [CSSStyle](#cssstyle), [CSSProperty](#cssproperty), [CSSMedia](#cssmedia), [MediaQuery](#mediaquery), [MediaQueryExpression](#mediaqueryexpression), [PlatformFontUsage](#platformfontusage), [CSSKeyframesRule](#csskeyframesrule), [CSSKeyframeRule](#csskeyframerule), [CSSComputedStyleProperty](#csscomputedstyleproperty), [CSSStyleSheetHeader](#cssstylesheetheader)</span></span> |
| [**<span data-ttu-id="b1ac8-120">依赖关系</span><span class="sxs-lookup"><span data-stu-id="b1ac8-120">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="b1ac8-121">DOM</span><span class="sxs-lookup"><span data-stu-id="b1ac8-121">DOM</span></span>](dom.md) |
## <span data-ttu-id="b1ac8-122">方法</span><span class="sxs-lookup"><span data-stu-id="b1ac8-122">Methods</span></span>

### <span data-ttu-id="b1ac8-123">“启用”</span><span class="sxs-lookup"><span data-stu-id="b1ac8-123">enable</span></span>
<span data-ttu-id="b1ac8-124">为给定页面启用 CSS 代理。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-124">Enables the CSS agent for the given page.</span></span> <span data-ttu-id="b1ac8-125">客户端不应假定已启用了 CSS 代理，直到收到此命令的结果。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-125">Clients should not assume that the CSS agent has been enabled until the result of this command is received.</span></span>

</p>

---

### <span data-ttu-id="b1ac8-126">“禁用”</span><span class="sxs-lookup"><span data-stu-id="b1ac8-126">disable</span></span>
<span data-ttu-id="b1ac8-127">禁用给定页面的 CSS 代理。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-127">Disables the CSS agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="b1ac8-128">getInlineStylesForNode</span><span class="sxs-lookup"><span data-stu-id="b1ac8-128">getInlineStylesForNode</span></span>
<span data-ttu-id="b1ac8-129">返回由标识的 DOM 节点的内联定义的样式（显式在 "style" 属性中，并隐式地使用 DOM 属性） `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-129">Returns the styles defined inline (explicitly in the "style" attribute and implicitly, using DOM attributes) for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-130">参数</span><span class="sxs-lookup"><span data-stu-id="b1ac8-130">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-131">a</span><span class="sxs-lookup"><span data-stu-id="b1ac8-131">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-132">返回</span><span class="sxs-lookup"><span data-stu-id="b1ac8-132">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-133">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="b1ac8-133">inlineStyle</span></span> <br /> <i><span data-ttu-id="b1ac8-134">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-134">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="b1ac8-135">指定的 DOM 节点的内联样式。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-135">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-136">attributesStyle</span><span class="sxs-lookup"><span data-stu-id="b1ac8-136">attributesStyle</span></span> <br /> <i><span data-ttu-id="b1ac8-137">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-137">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="b1ac8-138">属性定义的元素样式（例如，"width = 20 height = 100%"）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-138">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="b1ac8-139">getMatchedStylesForNode</span><span class="sxs-lookup"><span data-stu-id="b1ac8-139">getMatchedStylesForNode</span></span>
<span data-ttu-id="b1ac8-140">返回由标识的 DOM 节点请求的样式 `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-140">Returns requested styles for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-141">参数</span><span class="sxs-lookup"><span data-stu-id="b1ac8-141">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-142">a</span><span class="sxs-lookup"><span data-stu-id="b1ac8-142">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-143">返回</span><span class="sxs-lookup"><span data-stu-id="b1ac8-143">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-144">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="b1ac8-144">inlineStyle</span></span> <br /> <i><span data-ttu-id="b1ac8-145">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-145">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="b1ac8-146">指定的 DOM 节点的内联样式。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-146">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-147">attributesStyle</span><span class="sxs-lookup"><span data-stu-id="b1ac8-147">attributesStyle</span></span> <br /> <i><span data-ttu-id="b1ac8-148">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-148">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="b1ac8-149">属性定义的元素样式（例如，"width = 20 height = 100%"）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-149">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-150">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="b1ac8-150">matchedCSSRules</span></span> <br /> <i><span data-ttu-id="b1ac8-151">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-151">optional</span></span></i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="b1ac8-152">与此节点匹配的 CSS 规则，来自所有适用的样式表。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-152">CSS rules matching this node, from all applicable stylesheets.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-153">pseudoElements</span><span class="sxs-lookup"><span data-stu-id="b1ac8-153">pseudoElements</span></span> <br /> <i><span data-ttu-id="b1ac8-154">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-154">optional</span></span></i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td><span data-ttu-id="b1ac8-155">此节点的伪样式匹配。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-155">Pseudo style matches for this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-156">接手</span><span class="sxs-lookup"><span data-stu-id="b1ac8-156">inherited</span></span> <br /> <i><span data-ttu-id="b1ac8-157">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-157">optional</span></span></i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td><span data-ttu-id="b1ac8-158">继承的样式链（从 "即时节点父节点" 到 "DOM 树根"）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-158">A chain of inherited styles (from the immediate node parent up to the DOM tree root).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-159">cssKeyframesRules</span><span class="sxs-lookup"><span data-stu-id="b1ac8-159">cssKeyframesRules</span></span> <br /> <i><span data-ttu-id="b1ac8-160">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-160">optional</span></span></i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td><span data-ttu-id="b1ac8-161">与此节点匹配的 CSS keyframed 动画的列表。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-161">A list of CSS keyframed animations matching this node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="b1ac8-162">getPlatformFontsForNode</span><span class="sxs-lookup"><span data-stu-id="b1ac8-162">getPlatformFontsForNode</span></span>
<span data-ttu-id="b1ac8-163">请求有关平台字体的信息，用于在给定的节点中呈现子 TextNodes。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-163">Requests information about platform fonts which we used to render child TextNodes in the given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-164">参数</span><span class="sxs-lookup"><span data-stu-id="b1ac8-164">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-165">a</span><span class="sxs-lookup"><span data-stu-id="b1ac8-165">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-166">返回</span><span class="sxs-lookup"><span data-stu-id="b1ac8-166">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-167">字体</span><span class="sxs-lookup"><span data-stu-id="b1ac8-167">fonts</span></span></td>
            <td><a href="#platformfontusage"><code class="flyout">PlatformFontUsage[]</code></a></td>
            <td><span data-ttu-id="b1ac8-168">每个使用的平台字体的使用统计信息。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-168">Usage statistics for every employed platform font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="b1ac8-169">getComputedStyleForNode</span><span class="sxs-lookup"><span data-stu-id="b1ac8-169">getComputedStyleForNode</span></span>
<span data-ttu-id="b1ac8-170">返回由标识的 DOM 节点的计算样式 `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-170">Returns the computed style for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-171">参数</span><span class="sxs-lookup"><span data-stu-id="b1ac8-171">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-172">a</span><span class="sxs-lookup"><span data-stu-id="b1ac8-172">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-173">返回</span><span class="sxs-lookup"><span data-stu-id="b1ac8-173">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-174">computedStyle</span><span class="sxs-lookup"><span data-stu-id="b1ac8-174">computedStyle</span></span></td>
            <td><a href="#csscomputedstyleproperty"><code class="flyout">CSSComputedStyleProperty[]</code></a></td>
            <td><span data-ttu-id="b1ac8-175">指定的 DOM 节点的计算样式。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-175">Computed style for the specified DOM node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="b1ac8-176">事件</span><span class="sxs-lookup"><span data-stu-id="b1ac8-176">Events</span></span>

### <span data-ttu-id="b1ac8-177">styleSheetAdded</span><span class="sxs-lookup"><span data-stu-id="b1ac8-177">styleSheetAdded</span></span>
<span data-ttu-id="b1ac8-178">每当添加活动文档样式表时引发。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-178">Fired whenever an active document stylesheet is added.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-179">参数</span><span class="sxs-lookup"><span data-stu-id="b1ac8-179">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-180">标题</span><span class="sxs-lookup"><span data-stu-id="b1ac8-180">header</span></span></td>
            <td><a href="#cssstylesheetheader"><code class="flyout">CSSStyleSheetHeader</code></a></td>
            <td><span data-ttu-id="b1ac8-181">添加了样式表 metainfo。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-181">Added stylesheet metainfo.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="b1ac8-182">styleSheetChanged</span><span class="sxs-lookup"><span data-stu-id="b1ac8-182">styleSheetChanged</span></span>
<span data-ttu-id="b1ac8-183">当样式表因客户端操作而更改时激发。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-183">Fired whenever a stylesheet is changed as a result of the client operation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-184">参数</span><span class="sxs-lookup"><span data-stu-id="b1ac8-184">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-185">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-185">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="b1ac8-186">styleSheetRemoved</span><span class="sxs-lookup"><span data-stu-id="b1ac8-186">styleSheetRemoved</span></span>
<span data-ttu-id="b1ac8-187">每当删除活动文档样式表时引发。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-187">Fired whenever an active document stylesheet is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-188">参数</span><span class="sxs-lookup"><span data-stu-id="b1ac8-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-189">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-189">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="b1ac8-190">已删除的样式表的标识符。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-190">Identifier of the removed stylesheet.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="b1ac8-191">类型</span><span class="sxs-lookup"><span data-stu-id="b1ac8-191">Types</span></span>

### <a name="stylesheetid"></a> <span data-ttu-id="b1ac8-192">StyleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-192">StyleSheetId</span></span> `string`



</p>

---

### <a name="pseudoelementmatches"></a> <span data-ttu-id="b1ac8-193">PseudoElementMatches</span><span class="sxs-lookup"><span data-stu-id="b1ac8-193">PseudoElementMatches</span></span> `object`

<span data-ttu-id="b1ac8-194">单个虚拟样式的 CSS 规则集合。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-194">CSS rule collection for a single pseudo style.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-195">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-195">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-196">pseudoType</span><span class="sxs-lookup"><span data-stu-id="b1ac8-196">pseudoType</span></span></td>
            <td><a href="dom.md#pseudotype"><code class="flyout">DOM.PseudoType</code></a></td>
            <td><span data-ttu-id="b1ac8-197">伪元素类型。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-197">Pseudo element type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-198">接近</span><span class="sxs-lookup"><span data-stu-id="b1ac8-198">matches</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="b1ac8-199">匹配适用于伪样式的 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-199">Matches of CSS rules applicable to the pseudo style.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> <span data-ttu-id="b1ac8-200">InheritedStyleEntry</span><span class="sxs-lookup"><span data-stu-id="b1ac8-200">InheritedStyleEntry</span></span> `object`

<span data-ttu-id="b1ac8-201">来自上级节点的继承 CSS 规则集合。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-201">Inherited CSS rule collection from ancestor node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-202">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-202">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-203">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="b1ac8-203">inlineStyle</span></span> <br /> <i><span data-ttu-id="b1ac8-204">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-204">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="b1ac8-205">上级节点在样式继承链中的内联样式（如果有）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-205">The ancestor node's inline style, if any, in the style inheritance chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-206">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="b1ac8-206">matchedCSSRules</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="b1ac8-207">与样式继承链中的上级节点匹配的 CSS 规则的匹配项。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-207">Matches of CSS rules matching the ancestor node in the style inheritance chain.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="rulematch"></a> <span data-ttu-id="b1ac8-208">RuleMatch</span><span class="sxs-lookup"><span data-stu-id="b1ac8-208">RuleMatch</span></span> `object`

<span data-ttu-id="b1ac8-209">匹配 CSS 规则的数据。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-209">Match data for a CSS rule.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-210">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-210">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-211">规则</span><span class="sxs-lookup"><span data-stu-id="b1ac8-211">rule</span></span></td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td><span data-ttu-id="b1ac8-212">匹配中的 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-212">CSS rule in the match.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> <span data-ttu-id="b1ac8-213">Value</span><span class="sxs-lookup"><span data-stu-id="b1ac8-213">Value</span></span> `object`

<span data-ttu-id="b1ac8-214">简单选择器的数据（在选择器列表中以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-214">Data for a simple selector (these are delimited by commas in a selector list).</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-215">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-215">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-216">文本</span><span class="sxs-lookup"><span data-stu-id="b1ac8-216">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-217">值文本。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-217">Value text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-218">范围</span><span class="sxs-lookup"><span data-stu-id="b1ac8-218">range</span></span> <br /> <i><span data-ttu-id="b1ac8-219">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-219">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="b1ac8-220">基础资源中的值范围（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-220">Value range in the underlying resource (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="selectorlist"></a> <span data-ttu-id="b1ac8-221">SelectorList</span><span class="sxs-lookup"><span data-stu-id="b1ac8-221">SelectorList</span></span> `object`

<span data-ttu-id="b1ac8-222">选择器列表数据。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-222">Selector list data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-223">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-223">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-224">选择器</span><span class="sxs-lookup"><span data-stu-id="b1ac8-224">selectors</span></span></td>
            <td><a href="#value"><code class="flyout">Value[]</code></a></td>
            <td><span data-ttu-id="b1ac8-225">列表中的选定器。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-225">Selectors in the list.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-226">文本</span><span class="sxs-lookup"><span data-stu-id="b1ac8-226">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-227">规则选择器文本。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-227">Rule selector text.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssrule"></a> <span data-ttu-id="b1ac8-228">CSSRule</span><span class="sxs-lookup"><span data-stu-id="b1ac8-228">CSSRule</span></span> `object`

<span data-ttu-id="b1ac8-229">CSS 规则表示形式。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-229">CSS rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-230">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-230">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-231">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-231">styleSheetId</span></span> <br /> <i><span data-ttu-id="b1ac8-232">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-232">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="b1ac8-233">此规则来自的 css 样式表标识符（用户代理样式表和用户指定的样式表规则不存在）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-233">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-234">selectorList</span><span class="sxs-lookup"><span data-stu-id="b1ac8-234">selectorList</span></span> <br /> <i><span data-ttu-id="b1ac8-235">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-235">optional</span></span></i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td><span data-ttu-id="b1ac8-236">规则选择器数据。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-236">Rule selector data.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-237">原</span><span class="sxs-lookup"><span data-stu-id="b1ac8-237">origin</span></span> <br /> <i><span data-ttu-id="b1ac8-238">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-238">optional</span></span></i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="b1ac8-239">父样式表的来源。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-239">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-240">style</span><span class="sxs-lookup"><span data-stu-id="b1ac8-240">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="b1ac8-241">关联的样式声明。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-241">Associated style declaration.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-242">媒体</span><span class="sxs-lookup"><span data-stu-id="b1ac8-242">media</span></span> <br /> <i><span data-ttu-id="b1ac8-243">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-243">optional</span></span></i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td><span data-ttu-id="b1ac8-244">媒体列表数组（适用于涉及媒体查询的规则）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-244">Media list array (for rules involving media queries).</span></span> <span data-ttu-id="b1ac8-245">该数组枚举从最内层的媒体查询开始，然后向外进行枚举。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-245">The array enumerates media queries starting with the innermost one, going outwards.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> <span data-ttu-id="b1ac8-246">SourceRange</span><span class="sxs-lookup"><span data-stu-id="b1ac8-246">SourceRange</span></span> `object`

<span data-ttu-id="b1ac8-247">资源内的文本范围。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-247">Text range within a resource.</span></span> <span data-ttu-id="b1ac8-248">所有数字都是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-248">All numbers are zero-based.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-249">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-249">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-250">startLine</span><span class="sxs-lookup"><span data-stu-id="b1ac8-250">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b1ac8-251">范围起始行。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-251">Start line of range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-252">startColumn</span><span class="sxs-lookup"><span data-stu-id="b1ac8-252">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b1ac8-253">范围（包含）的起始列。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-253">Start column of range (inclusive).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-254">endLine</span><span class="sxs-lookup"><span data-stu-id="b1ac8-254">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b1ac8-255">区域结束行</span><span class="sxs-lookup"><span data-stu-id="b1ac8-255">End line of range</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-256">endColumn</span><span class="sxs-lookup"><span data-stu-id="b1ac8-256">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b1ac8-257">区域的结束列（独占）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-257">End column of range (exclusive).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="shorthandentry"></a> <span data-ttu-id="b1ac8-258">ShorthandEntry</span><span class="sxs-lookup"><span data-stu-id="b1ac8-258">ShorthandEntry</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-259">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-259">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-260">name</span><span class="sxs-lookup"><span data-stu-id="b1ac8-260">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-261">速记名称。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-261">Shorthand name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-262">值</span><span class="sxs-lookup"><span data-stu-id="b1ac8-262">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-263">简写值。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-263">Shorthand value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-264">必要</span><span class="sxs-lookup"><span data-stu-id="b1ac8-264">important</span></span> <br /> <i><span data-ttu-id="b1ac8-265">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-265">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-266">属性是否具有 "！重要" 批注（表示 `false` 缺少）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-266">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstyle"></a> <span data-ttu-id="b1ac8-267">CSSStyle</span><span class="sxs-lookup"><span data-stu-id="b1ac8-267">CSSStyle</span></span> `object`

<span data-ttu-id="b1ac8-268">CSS 样式表示形式。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-268">CSS style representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-269">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-269">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-270">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-270">styleSheetId</span></span> <br /> <i><span data-ttu-id="b1ac8-271">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-271">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="b1ac8-272">此规则来自的 css 样式表标识符（用户代理样式表和用户指定的样式表规则不存在）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-272">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-273">cssProperties</span><span class="sxs-lookup"><span data-stu-id="b1ac8-273">cssProperties</span></span></td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td><span data-ttu-id="b1ac8-274">样式中的 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-274">CSS properties in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-275">shorthandEntries</span><span class="sxs-lookup"><span data-stu-id="b1ac8-275">shorthandEntries</span></span></td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td><span data-ttu-id="b1ac8-276">在样式中找到的所有 shorthands 的计算值。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-276">Computed values for all shorthands found in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-277">cssText</span><span class="sxs-lookup"><span data-stu-id="b1ac8-277">cssText</span></span> <br /> <i><span data-ttu-id="b1ac8-278">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-278">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-279">样式声明文本（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-279">Style declaration text (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-280">范围</span><span class="sxs-lookup"><span data-stu-id="b1ac8-280">range</span></span> <br /> <i><span data-ttu-id="b1ac8-281">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-281">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="b1ac8-282">封闭样式表中的样式声明范围（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-282">Style declaration range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssproperty"></a> <span data-ttu-id="b1ac8-283">CSSProperty</span><span class="sxs-lookup"><span data-stu-id="b1ac8-283">CSSProperty</span></span> `object`

<span data-ttu-id="b1ac8-284">CSS 属性声明数据。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-284">CSS property declaration data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-285">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-285">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-286">name</span><span class="sxs-lookup"><span data-stu-id="b1ac8-286">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-287">属性名称。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-287">The property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-288">值</span><span class="sxs-lookup"><span data-stu-id="b1ac8-288">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-289">属性值。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-289">The property value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-290">必要</span><span class="sxs-lookup"><span data-stu-id="b1ac8-290">important</span></span> <br /> <i><span data-ttu-id="b1ac8-291">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-291">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-292">属性是否具有 "！重要" 批注（表示 `false` 缺少）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-292">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-293">暗示</span><span class="sxs-lookup"><span data-stu-id="b1ac8-293">implicit</span></span> <br /> <i><span data-ttu-id="b1ac8-294">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-294">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-295">属性是否为隐式的（表示 `false` 缺少）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-295">Whether the property is implicit (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-296">文本</span><span class="sxs-lookup"><span data-stu-id="b1ac8-296">text</span></span> <br /> <i><span data-ttu-id="b1ac8-297">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-297">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-298">样式中指定的完整属性文本。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-298">The full property text as specified in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-299">parsedOk</span><span class="sxs-lookup"><span data-stu-id="b1ac8-299">parsedOk</span></span> <br /> <i><span data-ttu-id="b1ac8-300">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-300">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-301">浏览器是否理解该属性（暗示 `true` 缺少）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-301">Whether the property is understood by the browser (implies `true` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-302">禁用</span><span class="sxs-lookup"><span data-stu-id="b1ac8-302">disabled</span></span> <br /> <i><span data-ttu-id="b1ac8-303">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-303">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-304">用户是否已禁用该属性（仅针对基于源的属性提供）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-304">Whether the property is disabled by the user (present for source-based properties only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-305">范围</span><span class="sxs-lookup"><span data-stu-id="b1ac8-305">range</span></span> <br /> <i><span data-ttu-id="b1ac8-306">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-306">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="b1ac8-307">封闭样式声明中的整个属性范围（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-307">The entire property range in the enclosing style declaration (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssmedia"></a> <span data-ttu-id="b1ac8-308">CSSMedia</span><span class="sxs-lookup"><span data-stu-id="b1ac8-308">CSSMedia</span></span> `object`

<span data-ttu-id="b1ac8-309">CSS 媒体规则描述符。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-309">CSS media rule descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-310">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-310">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-311">文本</span><span class="sxs-lookup"><span data-stu-id="b1ac8-311">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-312">媒体查询文本。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-312">Media query text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-313">从源</span><span class="sxs-lookup"><span data-stu-id="b1ac8-313">source</span></span></td>
            <td><code class="flyout">string</code> <br /> <i><span data-ttu-id="b1ac8-314">允许的值： mediaRule、importRule、linkedSheet、inlineSheet</span><span class="sxs-lookup"><span data-stu-id="b1ac8-314">Allowed values: mediaRule, importRule, linkedSheet, inlineSheet</span></span></i></td>
            <td><span data-ttu-id="b1ac8-315">媒体查询的源如果由 @media 规则指定的 "mediaRule"，则为 "importRule" （如果由 @import 规则指定），"linkedSheet" 如果由规则指定，则为 "" （如果在链接样式表的 LINK 标记中由 "media" 属性指定），"inlineSheet" （如果由内联样式表的 STYLE 标记中的 "media" 属性指定）</span><span class="sxs-lookup"><span data-stu-id="b1ac8-315">Source of the media query: "mediaRule" if specified by a @media rule, "importRule" if specified by an @import rule, "linkedSheet" if specified by a "media" attribute in a linked stylesheet's LINK tag, "inlineSheet" if specified by a "media" attribute in an inline stylesheet's STYLE tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-316">sourceURL</span><span class="sxs-lookup"><span data-stu-id="b1ac8-316">sourceURL</span></span> <br /> <i><span data-ttu-id="b1ac8-317">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-317">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-318">包含媒体查询说明的文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-318">URL of the document containing the media query description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-319">范围</span><span class="sxs-lookup"><span data-stu-id="b1ac8-319">range</span></span> <br /> <i><span data-ttu-id="b1ac8-320">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-320">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="b1ac8-321">封闭样式表中的关联规则（@media 或 @import）标题区域（如果有）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-321">The associated rule (@media or @import) header range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-322">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-322">styleSheetId</span></span> <br /> <i><span data-ttu-id="b1ac8-323">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-323">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="b1ac8-324">包含此对象（如果存在）的样式表的标识符。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-324">Identifier of the stylesheet containing this object (if exists).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-325">mediaList</span><span class="sxs-lookup"><span data-stu-id="b1ac8-325">mediaList</span></span> <br /> <i><span data-ttu-id="b1ac8-326">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-326">optional</span></span></i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td><span data-ttu-id="b1ac8-327">媒体查询的数组。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-327">Array of media queries.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaquery"></a> <span data-ttu-id="b1ac8-328">MediaQuery</span><span class="sxs-lookup"><span data-stu-id="b1ac8-328">MediaQuery</span></span> `object`

<span data-ttu-id="b1ac8-329">媒体查询描述符。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-329">Media query descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-330">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-330">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-331">表达式</span><span class="sxs-lookup"><span data-stu-id="b1ac8-331">expressions</span></span></td>
            <td><a href="#mediaqueryexpression"><code class="flyout">MediaQueryExpression[]</code></a></td>
            <td><span data-ttu-id="b1ac8-332">媒体查询表达式的数组。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-332">Array of media query expressions.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-333">active</span><span class="sxs-lookup"><span data-stu-id="b1ac8-333">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-334">是否满足媒体查询条件。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-334">Whether the media query condition is satisfied.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaqueryexpression"></a> <span data-ttu-id="b1ac8-335">MediaQueryExpression</span><span class="sxs-lookup"><span data-stu-id="b1ac8-335">MediaQueryExpression</span></span> `object`

<span data-ttu-id="b1ac8-336">媒体查询表达式描述符。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-336">Media query expression descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-337">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-338">值</span><span class="sxs-lookup"><span data-stu-id="b1ac8-338">value</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="b1ac8-339">媒体查询表达式值。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-339">Media query expression value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-340">插件</span><span class="sxs-lookup"><span data-stu-id="b1ac8-340">unit</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-341">媒体查询表达式单元。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-341">Media query expression units.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-342">功能</span><span class="sxs-lookup"><span data-stu-id="b1ac8-342">feature</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-343">媒体查询表达式功能。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-343">Media query expression feature.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-344">valueRange</span><span class="sxs-lookup"><span data-stu-id="b1ac8-344">valueRange</span></span> <br /> <i><span data-ttu-id="b1ac8-345">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-345">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="b1ac8-346">封闭样式表中的值文本的关联范围（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-346">The associated range of the value text in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-347">computedLength</span><span class="sxs-lookup"><span data-stu-id="b1ac8-347">computedLength</span></span> <br /> <i><span data-ttu-id="b1ac8-348">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-348">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="b1ac8-349">媒体查询表达式的计算长度（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-349">Computed length of media query expression (if applicable).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> <span data-ttu-id="b1ac8-350">PlatformFontUsage</span><span class="sxs-lookup"><span data-stu-id="b1ac8-350">PlatformFontUsage</span></span> `object`

<span data-ttu-id="b1ac8-351">与给定字体一起呈现的标志符号量的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-351">Information about amount of glyphs that were rendered with given font.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-352">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-352">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-353">familyName</span><span class="sxs-lookup"><span data-stu-id="b1ac8-353">familyName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-354">按平台报告的字体系列名称。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-354">Font's family name reported by platform.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-355">isCustomFont</span><span class="sxs-lookup"><span data-stu-id="b1ac8-355">isCustomFont</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-356">指示是否在本地下载或解析字体。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-356">Indicates if the font was downloaded or resolved locally.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-357">glyphCount</span><span class="sxs-lookup"><span data-stu-id="b1ac8-357">glyphCount</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="b1ac8-358">用此字体呈现的标志符号的数量。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-358">Amount of glyphs that were rendered with this font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframesrule"></a> <span data-ttu-id="b1ac8-359">CSSKeyframesRule</span><span class="sxs-lookup"><span data-stu-id="b1ac8-359">CSSKeyframesRule</span></span> `object`

<span data-ttu-id="b1ac8-360">CSS 关键帧规则表示。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-360">CSS keyframes rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-361">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-361">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-362">animationName</span><span class="sxs-lookup"><span data-stu-id="b1ac8-362">animationName</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="b1ac8-363">动画名称。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-363">Animation name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-364">关键帧</span><span class="sxs-lookup"><span data-stu-id="b1ac8-364">keyframes</span></span></td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td><span data-ttu-id="b1ac8-365">关键帧的列表。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-365">List of keyframes.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframerule"></a> <span data-ttu-id="b1ac8-366">CSSKeyframeRule</span><span class="sxs-lookup"><span data-stu-id="b1ac8-366">CSSKeyframeRule</span></span> `object`

<span data-ttu-id="b1ac8-367">CSS 关键帧规则表示形式。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-367">CSS keyframe rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-368">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-369">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-369">styleSheetId</span></span> <br /> <i><span data-ttu-id="b1ac8-370">可选</span><span class="sxs-lookup"><span data-stu-id="b1ac8-370">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="b1ac8-371">此规则来自的 css 样式表标识符（用户代理样式表和用户指定的样式表规则不存在）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-371">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-372">原</span><span class="sxs-lookup"><span data-stu-id="b1ac8-372">origin</span></span></td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="b1ac8-373">父样式表的来源。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-373">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-374">keyText</span><span class="sxs-lookup"><span data-stu-id="b1ac8-374">keyText</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="b1ac8-375">关联的键文本。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-375">Associated key text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-376">style</span><span class="sxs-lookup"><span data-stu-id="b1ac8-376">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="b1ac8-377">关联的样式声明。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-377">Associated style declaration.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csscomputedstyleproperty"></a> <span data-ttu-id="b1ac8-378">CSSComputedStyleProperty</span><span class="sxs-lookup"><span data-stu-id="b1ac8-378">CSSComputedStyleProperty</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-379">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-379">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-380">name</span><span class="sxs-lookup"><span data-stu-id="b1ac8-380">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-381">计算样式属性名称。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-381">Computed style property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-382">值</span><span class="sxs-lookup"><span data-stu-id="b1ac8-382">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-383">计算样式属性值。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-383">Computed style property value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstylesheetheader"></a> <span data-ttu-id="b1ac8-384">CSSStyleSheetHeader</span><span class="sxs-lookup"><span data-stu-id="b1ac8-384">CSSStyleSheetHeader</span></span> `object`

<span data-ttu-id="b1ac8-385">CSS 样式表 metainformation。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-385">CSS stylesheet metainformation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b1ac8-386">属性</span><span class="sxs-lookup"><span data-stu-id="b1ac8-386">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b1ac8-387">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="b1ac8-387">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="b1ac8-388">样式表标识符。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-388">The stylesheet identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-389">sourceURL</span><span class="sxs-lookup"><span data-stu-id="b1ac8-389">sourceURL</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b1ac8-390">样式表资源 URL。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-390">Stylesheet resource URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-391">禁用</span><span class="sxs-lookup"><span data-stu-id="b1ac8-391">disabled</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-392">表示是否已禁用样式表。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-392">Denotes whether the stylesheet is disabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-393">isInline</span><span class="sxs-lookup"><span data-stu-id="b1ac8-393">isInline</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b1ac8-394">是否为分析器的样式标记创建了此样式表。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-394">Whether this stylesheet is created for STYLE tag by parser.</span></span> <span data-ttu-id="b1ac8-395">此标志未设置为 "文档"。已写入样式标记。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-395">This flag is not set for document.written STYLE tags.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-396">startLine</span><span class="sxs-lookup"><span data-stu-id="b1ac8-396">startLine</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="b1ac8-397">资源样式表内的行偏移量（基于零）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-397">Line offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-398">startColumn</span><span class="sxs-lookup"><span data-stu-id="b1ac8-398">startColumn</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="b1ac8-399">资源中样式表的列偏移量（基于零）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-399">Column offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b1ac8-400">时长</span><span class="sxs-lookup"><span data-stu-id="b1ac8-400">length</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="b1ac8-401">内容的大小（以字符为字符）。</span><span class="sxs-lookup"><span data-stu-id="b1ac8-401">Size of the content (in characters).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="b1ac8-402">依赖关系</span><span class="sxs-lookup"><span data-stu-id="b1ac8-402">Dependencies</span></span>

[<span data-ttu-id="b1ac8-403">DOM</span><span class="sxs-lookup"><span data-stu-id="b1ac8-403">DOM</span></span>](dom.md)
