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
# CSS

此域公开 CSS 读/写操作。 样式表 (规则的所有 CSS 对象) 在相关对象的后续操作中使用的 `id` 关联。 每个对象类型都有一个特定的结构，并且这些结构在不同类型的对象之间 `id` 不可互换。 CSS 对象可以使用接受 DOM 节点 id `get*ForNode()` (的调用加载) 。 客户端还可以通过事件跟踪样式表，然后使用方法加载所需的 `styleSheetAdded` / `styleSheetRemoved` 样式表 `getStyleSheet[Text]()` 内容。

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)， [disable](#disable)， [getInlineStylesForNode](#getinlinestylesfornode)， [getMatchedStylesForNode](#getmatchedstylesfornode)， [getPlatformFontsForNode](#getplatformfontsfornode)， [getComputedStyleForNode](#getcomputedstylefornode) |
| [**事件**](#events) | [styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved) |
| [**类型**](#types) | [](#stylesheetid)StyleSheetId、PseudoElementMatches、InheritedStyleEntry、RuleMatch、Value、SelectorList、CSSRule、SourceRange、ShorthandEntry、CSSStyle、CSSProperty、CSSMedia、MediaQuery、MediaQueryExpression、PlatformFontUsage、CSSKeyframesRule、CSSKeyframeRule、CSSComputedStyleProperty、CSSStyleSheetHeader [](#pseudoelementmatches) [](#inheritedstyleentry) [](#rulematch) [](#value) [](#selectorlist) [](#cssrule) [](#sourcerange) [](#shorthandentry) [](#cssstyle) [](#cssproperty) [](#cssmedia) [](#mediaquery) [](#mediaqueryexpression) [](#platformfontusage) [](#csskeyframesrule) [](#csskeyframerule) [](#csscomputedstyleproperty) [](#cssstylesheetheader) |
| [**依赖关系**](#dependencies) | [DOM](dom.md) |
## 方法

### “启用”
为给定页面启用 CSS 代理。 客户端不应假定 CSS 代理已启用，直到收到此命令的结果。

</p>

---

### “禁用”
禁用给定页面的 CSS 代理。

</p>

---

### getInlineStylesForNode
返回在"style" (中显式定义的内联样式，并隐式使用 DOM 属性) 标识的 DOM 节点 `nodeId` 。

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
            <td>nodeId</td>
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
            <td>指定 DOM 节点的内联样式。</td>
        </tr>
        <tr>
            <td>attributesStyle <br /> <i>可选</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性定义的元素样式 (例如，由"width=20 height=100%") 。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getMatchedStylesForNode
返回由 标识的 DOM 节点的请求样式 `nodeId` 。

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
            <td>nodeId</td>
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
            <td>指定 DOM 节点的内联样式。</td>
        </tr>
        <tr>
            <td>attributesStyle <br /> <i>可选</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性定义的元素样式 (例如，由"width=20 height=100%") 。</td>
        </tr>
        <tr>
            <td>matchedCSSRules <br /> <i>可选</i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>匹配此节点的 CSS 规则，来自所有适用的样式表。</td>
        </tr>
        <tr>
            <td>pseudoElements <br /> <i>可选</i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td>此节点的伪样式匹配。</td>
        </tr>
        <tr>
            <td>继承 <br /> <i>可选</i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td>继承的样式链 (从直接节点父元素一直继承到 DOM 树根) 。</td>
        </tr>
        <tr>
            <td>cssKeyframesRules <br /> <i>可选</i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td>匹配此节点的 CSS 关键帧动画列表。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getPlatformFontsForNode
请求有关我们在给定节点中呈现子 TextNodes 的平台字体的信息。

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
            <td>nodeId</td>
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
            <td>每个已使用平台字体的使用情况统计信息。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getComputedStyleForNode
返回由 标识的 DOM 节点的计算样式 `nodeId` 。

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
            <td>nodeId</td>
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
            <td>指定 DOM 节点的计算样式。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 事件

### styleSheetAdded
每当添加活动文档样式表时触发。

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
每当样式表因客户端操作而更改时触发。

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
每当删除活动文档样式表时触发。

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
            <td>已删除样式表的标识符。</td>
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

单个伪样式的 CSS 规则集合。

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
            <td>匹配</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>适用于伪样式的 CSS 规则的匹配项。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> InheritedStyleEntry `object`

继承的来自上级节点的 CSS 规则集合。

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
            <td>上级节点的内联样式（如果有）在样式继承链中。</td>
        </tr>
        <tr>
            <td>matchedCSSRules</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>与样式继承链中的上级节点匹配的 CSS 规则匹配。</td>
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
            <td>rule</td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td>匹配中的 CSS 规则。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> 值 `object`

简单选择器 (在选择器列表中用逗号) 。

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
            <td>基础资源资源中的值 (（如果) ）。</td>
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
            <td>列表中的选择器。</td>
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
            <td>此规则 (用户代理样式表和用户指定的样式表规则) css 样式表标识符。</td>
        </tr>
        <tr>
            <td>selectorList <br /> <i>可选</i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td>规则选择器数据。</td>
        </tr>
        <tr>
            <td>origin <br /> <i>可选</i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>父样式表的原点。</td>
        </tr>
        <tr>
            <td>style</td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>关联的样式声明。</td>
        </tr>
        <tr>
            <td>媒体 <br /> <i>可选</i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td>媒体列表数组 (涉及媒体查询的) 。 该数组枚举从最里层开始向外延伸的媒体查询。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> SourceRange `object`

资源中的文本范围。 所有数字都从零开始。

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
            <td>范围的起始行。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>区域起始列 (包含) 。</td>
        </tr>
        <tr>
            <td>endLine</td>
            <td><code class="flyout">integer</code></td>
            <td>范围的结束行</td>
        </tr>
        <tr>
            <td>endColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>区域结束列 (独占) 。</td>
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
            <td>速记值。</td>
        </tr>
        <tr>
            <td>重要 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果属性不存在，则 `false` ("！important") 。</td>
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
            <td>此规则 (用户代理样式表和用户指定的样式表规则) css 样式表标识符。</td>
        </tr>
        <tr>
            <td>cssProperties</td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td>样式中的 CSS 属性。</td>
        </tr>
        <tr>
            <td>shorthandEntries</td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td>在样式中发现的所有速记的计算值。</td>
        </tr>
        <tr>
            <td>cssText <br /> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>样式声明文本 (（如果) ）。</td>
        </tr>
        <tr>
            <td>范围 <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>包含样式表样式表的样式声明 (（如果) ）。</td>
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
            <td>重要 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果属性不存在，则 `false` ("！important") 。</td>
        </tr>
        <tr>
            <td>隐式 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果不存在此属性， (`false` 是否隐式) 。</td>
        </tr>
        <tr>
            <td>文本 <br /> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>样式中指定的全属性文本。</td>
        </tr>
        <tr>
            <td>parsedOk <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>浏览器是否理解该属性 (是否表示 `true` 不存在) 。</td>
        </tr>
        <tr>
            <td>已禁用 <br /> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>用户是否禁用此属性 (基于源的属性是否) 。</td>
        </tr>
        <tr>
            <td>范围 <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>括在样式声明中的整个属性 (（如果) ）。</td>
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
            <td>source</td>
            <td><code class="flyout">string</code> <br /> <i>允许的值：mediaRule、importRule、linkedSheet、inlineSheet</i></td>
            <td>媒体查询的源："mediaRule"（如果由 @media 规则指定，如果由 @import 规则指定，则"importRule";如果由链接样式表的 LINK 标记中的"media"属性指定，则"linkedSheet";如果由内联样式表的 STYLE 标记中的"media"属性指定，则指定"inlineSheet"。</td>
        </tr>
        <tr>
            <td>sourceURL <br /> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>包含媒体查询说明的文档的 URL。</td>
        </tr>
        <tr>
            <td>范围 <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>关联的规则 (@media 或 @import) 标题范围包含在样式表 (中（如果) ）。</td>
        </tr>
        <tr>
            <td>styleSheetId <br /> <i>可选</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>包含此对象的样式表的标识符 (（如果存在) ）。</td>
        </tr>
        <tr>
            <td>mediaList <br /> <i>可选</i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td>媒体查询数组。</td>
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
            <td>unit</td>
            <td><code class="flyout">string</code></td>
            <td>媒体查询表达式单位。</td>
        </tr>
        <tr>
            <td>功能</td>
            <td><code class="flyout">string</code></td>
            <td>媒体查询表达式功能。</td>
        </tr>
        <tr>
            <td>valueRange <br /> <i>可选</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>括起样式表内值文本的关联区域 (（如果) ）。</td>
        </tr>
        <tr>
            <td>computedLength <br /> <i>可选</i></td>
            <td><code class="flyout">number</code></td>
            <td>如果适用，则计算媒体 (表达式) 。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> PlatformFontUsage `object`

有关使用给定字体呈现的字形数量的信息。

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
            <td>平台报告的字体系列名称。</td>
        </tr>
        <tr>
            <td>isCustomFont</td>
            <td><code class="flyout">boolean</code></td>
            <td>指示字体是在本地下载还是解析。</td>
        </tr>
        <tr>
            <td>glyphCount</td>
            <td><code class="flyout">number</code></td>
            <td>用此字体呈现的字形数量。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframesrule"></a> CSSKeyframesRule `object`

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
            <td>animationName</td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td>动画名称。</td>
        </tr>
        <tr>
            <td>关键帧</td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td>关键帧列表。</td>
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
            <td>此规则 (用户代理样式表和用户指定的样式表规则) css 样式表标识符。</td>
        </tr>
        <tr>
            <td>origin</td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>父样式表的原点。</td>
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
            <td>已禁用</td>
            <td><code class="flyout">boolean</code></td>
            <td>表示是否禁用样式表。</td>
        </tr>
        <tr>
            <td>isInline</td>
            <td><code class="flyout">boolean</code></td>
            <td>此样式表是否由分析程序为 STYLE 标记创建。 未为 document.written STYLE 标记设置此标志。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">number</code></td>
            <td>资源中的样式表的行偏移量 (从零开始) 。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">number</code></td>
            <td>资源中的样式表的列偏移量 (从零开始) 。</td>
        </tr>
        <tr>
            <td>length</td>
            <td><code class="flyout">number</code></td>
            <td>内容的大小以 (字符表示) 。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依赖关系

[DOM](dom.md)
