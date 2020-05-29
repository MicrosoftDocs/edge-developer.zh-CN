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
# CSS
此域公开 CSS 读/写操作。 所有 CSS 对象（样式表、规则和样式）在 `id` 相关对象的后续操作中都有相关联的已使用。 每个对象类型都有一个特定的 `id` 结构，它们在不同类型的对象之间不能互换。 可以使用 `get*ForNode()` 调用（接受 DOM 节点 id）加载 CSS 对象。 客户端还可以通过事件跟踪样式表 `styleSheetAdded` / `styleSheetRemoved` ，随后使用这些方法加载所需的样式表内容 `getStyleSheet[Text]()` 。

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)、 [disable](#disable)、 [getInlineStylesForNode](#getinlinestylesfornode)、 [getMatchedStylesForNode](#getmatchedstylesfornode)、 [getPlatformFontsForNode](#getplatformfontsfornode)、 [getComputedStyleForNode](#getcomputedstylefornode) |
| [**事件**](#events) | [styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved) |
| [**类型**](#types) | [StyleSheetId](#stylesheetid)、 [PseudoElementMatches](#pseudoelementmatches)、 [InheritedStyleEntry](#inheritedstyleentry)、 [RuleMatch](#rulematch)、 [Value](#value)、 [SelectorList](#selectorlist)、 [CSSRule](#cssrule)、 [SourceRange](#sourcerange)、 [ShorthandEntry](#shorthandentry)、 [CSSStyle](#cssstyle)、 [CSSProperty](#cssproperty)、 [CSSMedia](#cssmedia)、 [MediaQuery](#mediaquery)、 [MediaQueryExpression、PlatformFontUsage](#mediaqueryexpression) [、CSSKeyframesRule](#platformfontusage) [、CSSKeyframeRule](#csskeyframesrule) [、CSSComputedStyleProperty](#csskeyframerule) [、CSSStyleSheetHeader](#csscomputedstyleproperty)、、 [、、](#cssstylesheetheader) 、、 |
| [**依赖关系**](#dependencies) | [DOM](dom.md) |
## 方法

### “启用”
为给定页面启用 CSS 代理。 客户端不应假定已启用了 CSS 代理，直到收到此命令的结果。

</p>

---

### “禁用”
禁用给定页面的 CSS 代理。

</p>

---

### getInlineStylesForNode
返回由标识的 DOM 节点的内联定义的样式（显式在 "style" 属性中，并隐式地使用 DOM 属性） `nodeId` 。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>可选</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>指定的 DOM 节点的内联样式。</td>
        </tr>
        <tr>
            <td>attributesStyle <br /> <i>可选</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性定义的元素样式（例如，"width = 20 height = 100%"）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getMatchedStylesForNode
返回由标识的 DOM 节点请求的样式 `nodeId` 。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>可选</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>指定的 DOM 节点的内联样式。</td>
        </tr>
        <tr>
            <td>attributesStyle <br /> <i>可选</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性定义的元素样式（例如，"width = 20 height = 100%"）。</td>
        </tr>
        <tr>
            <td>matchedCSSRules <br /> <i>可选</i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>与此节点匹配的 CSS 规则，来自所有适用的样式表。</td>
        </tr>
        <tr>
            <td>pseudoElements <br /> <i>可选</i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td>此节点的伪样式匹配。</td>
        </tr>
        <tr>
            <td>接手 <br /> <i>可选</i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td>继承的样式链（从 "即时节点父节点" 到 "DOM 树根"）。</td>
        </tr>
        <tr>
            <td>cssKeyframesRules <br /> <i>可选</i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td>与此节点匹配的 CSS keyframed 动画的列表。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getPlatformFontsForNode
请求有关平台字体的信息，用于在给定的节点中呈现子 TextNodes。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>字体</td>
            <td><a href="#platformfontusage"><code class="flyout">PlatformFontUsage[]</code></a></td>
            <td>每个使用的平台字体的使用统计信息。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getComputedStyleForNode
返回由标识的 DOM 节点的计算样式 `nodeId` 。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>computedStyle</td>
            <td><a href="#csscomputedstyleproperty"><code class="flyout">CSSComputedStyleProperty[]</code></a></td>
            <td>指定的 DOM 节点的计算样式。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 事件

### styleSheetAdded
每当添加活动文档样式表时引发。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>标题</td>
            <td><a href="#cssstylesheetheader"><code class="flyout">CSSStyleSheetHeader</code></a></td>
            <td>添加了样式表 metainfo。</td>
        </tr>
    </tbody>
</table>
</p>

---

### styleSheetChanged
当样式表因客户端操作而更改时激发。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId</td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### styleSheetRemoved
每当删除活动文档样式表时引发。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId</td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>已删除的样式表的标识符。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 类型

### <a name="stylesheetid"></a> StyleSheetId `string`



</p>

---

### <a name="pseudoelementmatches"></a> PseudoElementMatches `object`

单个虚拟样式的 CSS 规则集合。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>pseudoType</td>
            <td><a href="dom.md#pseudotype"><code class="flyout">DOM.PseudoType</code></a></td>
            <td>伪元素类型。</td>
        </tr>
        <tr>
            <td>接近</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>匹配适用于伪样式的 CSS 规则。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> InheritedStyleEntry `object`

来自上级节点的继承 CSS 规则集合。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>可选</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>上级节点在样式继承链中的内联样式（如果有）。</td>
        </tr>
        <tr>
            <td>matchedCSSRules</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>与样式继承链中的上级节点匹配的 CSS 规则的匹配项。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="rulematch"></a> RuleMatch `object`

匹配 CSS 规则的数据。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>规则</td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td>匹配中的 CSS 规则。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> Value `object`

简单选择器的数据（在选择器列表中以逗号分隔）。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>文本</td>
            <td><code class="flyout">string</code></td>
            <td>值文本。</td>
        </tr>
        <tr>
            <td>范围 <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>基础资源中的值范围（如果可用）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="selectorlist"></a> SelectorList `object`

选择器列表数据。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>选择器</td>
            <td><a href="#value"><code class="flyout">Value[]</code></a></td>
            <td>列表中的选定器。</td>
        </tr>
        <tr>
            <td>文本</td>
            <td><code class="flyout">string</code></td>
            <td>规则选择器文本。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssrule"></a> CSSRule `object`

CSS 规则表示形式。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId <br /> <i>可选</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>此规则来自的 css 样式表标识符（用户代理样式表和用户指定的样式表规则不存在）。</td>
        </tr>
        <tr>
            <td>selectorList <br /> <i>可选</i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td>规则选择器数据。</td>
        </tr>
        <tr>
            <td>原 <br /> <i>可选</i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>父样式表的来源。</td>
        </tr>
        <tr>
            <td>style</td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>关联的样式声明。</td>
        </tr>
        <tr>
            <td>媒体 <br /> <i>可选</i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td>媒体列表数组（适用于涉及媒体查询的规则）。 该数组枚举从最内层的媒体查询开始，然后向外进行枚举。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> SourceRange `object`

资源内的文本范围。 所有数字都是从零开始的。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">integer</code></td>
            <td>范围起始行。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>范围（包含）的起始列。</td>
        </tr>
        <tr>
            <td>endLine</td>
            <td><code class="flyout">integer</code></td>
            <td>区域结束行</td>
        </tr>
        <tr>
            <td>endColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>区域的结束列（独占）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="shorthandentry"></a> ShorthandEntry `object`



<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>速记名称。</td>
        </tr>
        <tr>
            <td>值</td>
            <td><code class="flyout">string</code></td>
            <td>简写值。</td>
        </tr>
        <tr>
            <td>必要 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>属性是否具有 "！重要" 批注（表示 `false` 缺少）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstyle"></a> CSSStyle `object`

CSS 样式表示形式。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId <br /> <i>可选</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>此规则来自的 css 样式表标识符（用户代理样式表和用户指定的样式表规则不存在）。</td>
        </tr>
        <tr>
            <td>cssProperties</td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td>样式中的 CSS 属性。</td>
        </tr>
        <tr>
            <td>shorthandEntries</td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td>在样式中找到的所有 shorthands 的计算值。</td>
        </tr>
        <tr>
            <td>cssText <br /> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>样式声明文本（如果可用）。</td>
        </tr>
        <tr>
            <td>范围 <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>封闭样式表中的样式声明范围（如果可用）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssproperty"></a> CSSProperty `object`

CSS 属性声明数据。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>属性名称。</td>
        </tr>
        <tr>
            <td>值</td>
            <td><code class="flyout">string</code></td>
            <td>属性值。</td>
        </tr>
        <tr>
            <td>必要 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>属性是否具有 "！重要" 批注（表示 `false` 缺少）。</td>
        </tr>
        <tr>
            <td>暗示 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>属性是否为隐式的（表示 `false` 缺少）。</td>
        </tr>
        <tr>
            <td>文本 <br /> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>样式中指定的完整属性文本。</td>
        </tr>
        <tr>
            <td>parsedOk <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>浏览器是否理解该属性（暗示 `true` 缺少）。</td>
        </tr>
        <tr>
            <td>禁用 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>用户是否已禁用该属性（仅针对基于源的属性提供）。</td>
        </tr>
        <tr>
            <td>范围 <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>封闭样式声明中的整个属性范围（如果可用）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssmedia"></a> CSSMedia `object`

CSS 媒体规则描述符。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>文本</td>
            <td><code class="flyout">string</code></td>
            <td>媒体查询文本。</td>
        </tr>
        <tr>
            <td>从源</td>
            <td><code class="flyout">string</code> <br /> <i>允许的值： mediaRule、importRule、linkedSheet、inlineSheet</i></td>
            <td>媒体查询的源如果由 @media 规则指定的 "mediaRule"，则为 "importRule" （如果由 @import 规则指定），"linkedSheet" 如果由规则指定，则为 "" （如果在链接样式表的 LINK 标记中由 "media" 属性指定），"inlineSheet" （如果由内联样式表的 STYLE 标记中的 "media" 属性指定）</td>
        </tr>
        <tr>
            <td>sourceURL <br /> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>包含媒体查询说明的文档的 URL。</td>
        </tr>
        <tr>
            <td>范围 <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>封闭样式表中的关联规则（@media 或 @import）标题区域（如果有）。</td>
        </tr>
        <tr>
            <td>styleSheetId <br /> <i>可选</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>包含此对象（如果存在）的样式表的标识符。</td>
        </tr>
        <tr>
            <td>mediaList <br /> <i>可选</i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td>媒体查询的数组。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaquery"></a> MediaQuery `object`

媒体查询描述符。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>表达式</td>
            <td><a href="#mediaqueryexpression"><code class="flyout">MediaQueryExpression[]</code></a></td>
            <td>媒体查询表达式的数组。</td>
        </tr>
        <tr>
            <td>active</td>
            <td><code class="flyout">boolean</code></td>
            <td>是否满足媒体查询条件。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaqueryexpression"></a> MediaQueryExpression `object`

媒体查询表达式描述符。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>值</td>
            <td><code class="flyout">number</code></td>
            <td>媒体查询表达式值。</td>
        </tr>
        <tr>
            <td>插件</td>
            <td><code class="flyout">string</code></td>
            <td>媒体查询表达式单元。</td>
        </tr>
        <tr>
            <td>功能</td>
            <td><code class="flyout">string</code></td>
            <td>媒体查询表达式功能。</td>
        </tr>
        <tr>
            <td>valueRange <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>封闭样式表中的值文本的关联范围（如果可用）。</td>
        </tr>
        <tr>
            <td>computedLength <br /> <i>可选</i></td>
            <td><code class="flyout">number</code></td>
            <td>媒体查询表达式的计算长度（如果适用）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> PlatformFontUsage `object`

与给定字体一起呈现的标志符号量的相关信息。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>familyName</td>
            <td><code class="flyout">string</code></td>
            <td>按平台报告的字体系列名称。</td>
        </tr>
        <tr>
            <td>isCustomFont</td>
            <td><code class="flyout">boolean</code></td>
            <td>指示是否在本地下载或解析字体。</td>
        </tr>
        <tr>
            <td>glyphCount</td>
            <td><code class="flyout">number</code></td>
            <td>用此字体呈现的标志符号的数量。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframesrule"></a> CSSKeyframesRule `object`

CSS 关键帧规则表示。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>animationName</td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td>动画名称。</td>
        </tr>
        <tr>
            <td>关键帧</td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td>关键帧的列表。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframerule"></a> CSSKeyframeRule `object`

CSS 关键帧规则表示形式。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId <br /> <i>可选</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>此规则来自的 css 样式表标识符（用户代理样式表和用户指定的样式表规则不存在）。</td>
        </tr>
        <tr>
            <td>原</td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>父样式表的来源。</td>
        </tr>
        <tr>
            <td>keyText</td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td>关联的键文本。</td>
        </tr>
        <tr>
            <td>style</td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>关联的样式声明。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csscomputedstyleproperty"></a> CSSComputedStyleProperty `object`



<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>计算样式属性名称。</td>
        </tr>
        <tr>
            <td>值</td>
            <td><code class="flyout">string</code></td>
            <td>计算样式属性值。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstylesheetheader"></a> CSSStyleSheetHeader `object`

CSS 样式表 metainformation。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId</td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>样式表标识符。</td>
        </tr>
        <tr>
            <td>sourceURL</td>
            <td><code class="flyout">string</code></td>
            <td>样式表资源 URL。</td>
        </tr>
        <tr>
            <td>禁用</td>
            <td><code class="flyout">boolean</code></td>
            <td>表示是否已禁用样式表。</td>
        </tr>
        <tr>
            <td>isInline</td>
            <td><code class="flyout">boolean</code></td>
            <td>是否为分析器的样式标记创建了此样式表。 此标志未设置为 "文档"。已写入样式标记。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">number</code></td>
            <td>资源样式表内的行偏移量（基于零）。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">number</code></td>
            <td>资源中样式表的列偏移量（基于零）。</td>
        </tr>
        <tr>
            <td>时长</td>
            <td><code class="flyout">number</code></td>
            <td>内容的大小（以字符为字符）。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依赖关系

[DOM](dom.md)
