---
description: Edge 和 Chromium (扩展) 安全策略。
title: '内容安全策略 (CSP) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 8307482e780b4d631edffd976cca7ba724e2ad40
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397515"
---
# <a name="content-security-policy-csp"></a>内容安全策略 \(CSP\)   

为了缓解大量的潜在跨站点脚本问题，Microsoft Edge 扩展系统合并了内容安全策略 [\(CSP\) 的一般概念 ][W3CContentSecurityPolicy]。  这引入了一些相当严格的策略，这些策略使扩展在默认情况下更加安全，并让你能够创建和实施规则，以管理扩展和应用程序可能加载和运行的内容类型。  

通常，CSP 用作扩展加载或运行的资源的阻止/允许列表机制。  通过为扩展定义合理的策略，你可以仔细考虑扩展所需的资源，并要求浏览器确保这些是你的扩展有权访问的唯一资源。  这些策略提供高于扩展请求的主机权限的安全性;它们是一层额外的保护，而不是替代。  

在 Web 上，此类策略通过 HTTP 标头或元素 `meta` 定义。  在 Microsoft Edge 扩展系统中，两者都不是适当的机制。  而是使用扩展的文件定义扩展策略 `manifest.json` ，如下所示：  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> 有关 CSP 语法的完整详细信息，请参阅内容安全策略规范和 HTML5Rocks 上的"内容[][HTML5RocksIntroductionContentSecurityPolicy]安全策略简介"文章。 [][W3CContentSecurityPolicy]  

## <a name="default-policy-restrictions"></a>默认策略限制  

未定义 的包 `manifest_version` 没有默认内容安全策略。  选择 `manifest_version` 2 的程序包具有以下默认内容安全策略。  

```javascript
script-src 'self'; object-src 'self'
```  

该策略通过以下三种方式限制扩展和应用程序来增加安全性：  

**Eval 和相关函数已禁用**  

类似下面的代码不起作用：  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

像这样评估 JavaScript 字符串是一种常见的 XSS 攻击矢量。  相反，您应编写如下所示的代码：

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**内联 JavaScript 未运行**  

内联 JavaScript 不运行。  此限制同时禁止内联 `<script>` 块和内联事件处理程序（如 `<button onclick="...">` ）。

第一个限制通过使您无法意外运行恶意第三方提供的脚本来擦除大量跨站点脚本攻击。  但是，它确实需要你在内容和行为 \(编写代码，您当然应该这样做，正确) 。  例如，可以更清楚地说明这一点。  您可以尝试将浏览器操作弹出窗口编写为单个 `pop-up.html` 包含：  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script>
            function awesome() {
                // do something awesome!
            }
            
            function totallyAwesome() {
                // do something TOTALLY awesome!
            }
            
            function clickHandler(element) {
                setTimeout("awesome(); totallyAwesome()", 1000);
            }
            
            function main() {
                // Initialization work goes here.
            }
        </script>
    </head>
    <body onload="main();">
        <button onclick="clickHandler(this)">
            Click for awesomeness!
        </button>
    </body>
</html>
```  

为了使此操作按预期方式工作，必须更改以下三项：  

*   必须将 `clickHandler` 定义移动到外部 JavaScript 文件 \(`popup.js` 可能是一个很好的目标) 。  
*   内联事件处理程序定义必须重写为 ，并 `addEventListener` 提取到 `popup.js` 中。  
    如果当前正在使用类似 的代码启动程序，请考虑通过挂钩到文档的事件或窗口的事件来替换它， `<body onload="main();">` `DOMContentLoaded` `load` 具体取决于你的要求。  使用前者，因为它通常更快速地触发。  

*   `setTimeout`必须重写调用以避免将字符串 `"awesome(); totallyAwesome()"` 转换为 JavaScript 以运行。  
    这些更改可能如下所示：  

```javascript
function awesome() {
    // Do something awesome!
}

function totallyAwesome() {
    // do something TOTALLY awesome!
}

function awesomeTask() {
    awesome();
    totallyAwesome();
}

function clickHandler(e) {
    setTimeout(awesomeTask, 1000);
}

function main() {
    // Initialization work goes here.
}

// Add event listeners once the DOM has fully loaded by listening for the
// `DOMContentLoaded` event on the document, and adding your listeners to
// specific elements when it triggers.
document.addEventListener('DOMContentLoaded', function () {
    document.querySelector('button').addEventListener('click', clickHandler);
    main();
});
```  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script src="popup.js"></script>
    </head>
    <body>
        <button>Click for awesomeness!</button>
    </body>
</html>
```  

**仅加载本地脚本和对象资源**  

脚本和对象资源只能从扩展包加载，而不是从大型 Web 加载。  这将确保你的扩展仅运行你专门批准的代码，防止活动网络攻击者恶意重定向你的资源请求。  

请考虑将 jQuery 的特定版本包括在扩展包中，而不是编写依赖于 jQuery \(或任何其他库\) 从外部 CDN 加载的代码。  即，而不是：  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
    </head>
    <body>
        <button>Click for awesomeness!</button>
    </body>
</html>
```  

下载文件，将文件包括在程序包中，然后编写：  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script src="jquery.min.js"></script>
    </head>
    <body>
        <button>Click for awesomeness!</button>
    </body>
</html>
```  

## <a name="relaxing-the-default-policy"></a>支持默认策略  

**内联脚本**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

内联脚本能够通过在策略中指定源代码的 base64 编码哈希来允许。  此哈希必须以使用的哈希算法 \(sha256、sha384 或 sha512\) 作为前缀。  例如，导航到元素 [的哈希 \<script\> 用法][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]。  

**远程脚本**  

如果您需要一些外部 JavaScript 或对象资源，则可能会通过允许列出应接受脚本的安全源来限制策略。  验证使用扩展的提升权限加载的运行时资源是否正是您期望的资源，并且不会替换为活动网络攻击者。  由于 [中间人攻击][WikiManMiddleAttacks] 在 HTTP 上是无关紧要的和无法检测到的，因此不接受这些来源。  

目前，开发人员可以允许具有以下方案列出源 `blob` `filesystem` ：、、 `https` 和 `extension` 。  必须为 和 方案显式指定源的主机 `https` `extension` 部分。  不允许使用泛型通配符（如 https：和 ）;允许使用诸如 `https://*` `https://*.com` 这样的子 `https://*.example.com` 域通配符。  公共后缀 [列表中的域][PublicSuffixList] 也被视为常规顶级域。  若要从这些域加载资源，必须明确列出子域。  例如， `https://*.cloudfront.net` 是 无效，但 `https://XXXX.cloudfront.net` 和 `https://*.XXXX.cloudfront.net` 可以 `allowlisted` 。  

为了便于开发，从本地计算机上服务器加载的 HTTP 资源可以 `allowlisted` 。  可以允许在 或 的任何端口上列出脚本和 `http://127.0.0.1` 对象源 `http://localhost` 。  

> [!NOTE]
> 对通过 HTTP 加载的资源的限制仅适用于直接运行的资源。  例如，你仍然可以自由地连接到任何你喜欢的源;默认策略不会以任何方式限制 `XMLHTTPRequest` `connect-src` 或其他任何云解决方案提供商指令。  

允许通过 HTTPS 加载脚本资源的宽松策略定义可能 `example.com` 如下所示：  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> 和 `script-src` `object-src` 都由策略定义。  Microsoft Edge 不接受不将其中每个值限制为 \(\) ' `self` "的策略。  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**评估的 JavaScript**  

针对 的策略和相关函数（如 、 和 ）能够通过向策略 `eval()` `setTimeout(String)` `setInterval(String)` `new Function(String)` 添加来 `unsafe-eval` 轻松：  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

但是，应避免使用策略。  这些函数是一些 XSS 攻击矢量。  

## <a name="tightening-the-default-policy"></a>使用默认策略  

当然，你可以将此策略严格到扩展允许的任何程度，以便以便利为代价提高安全性。  若要指定你的扩展只能从关联的扩展包加载任何类型的 \(图像等\) 资源，例如，策略 可能合适 `default-src 'self'` 。  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## <a name="content-scripts"></a>内容脚本  

正在讨论的策略适用于扩展的背景页和事件页面。  内容脚本如何应用于扩展的内容脚本更加复杂。  

内容脚本通常不受扩展 CSP 的管理。  由于内容脚本不是 HTML，因此主要影响是，即使扩展 CSP 未指定 ，它们也可能使用 ，尽管 `eval` `unsafe-eval` 不建议这样做。  此外，页面的 CSP 不适用于内容脚本。  更复杂的是 `<script>` 内容脚本创建并放入其运行的页面的 DOM 中的标记。  这些脚本将作为 DOM 注入脚本进行引用。  

注入页面后立即运行的 DOM 注入脚本将如预期运行。  假设一个包含以下代码的内容脚本就是一个简单的示例：  

```javascript
document.write("<script>alert(1);</script>");
 ```  

此内容脚本会立即 `alert` 在 上引发 `document.write()` 。  请注意，无论页面可以指定何种策略，这都会运行。
但是，行为会变得更加复杂，既包括该 DOM 注入脚本，也针对任何在注入时未立即运行的脚本。  假设你的扩展在提供指定 的关联 CSP 的页面上运行 `script-src 'self'` 。  现在假设内容脚本运行以下代码：  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

如果用户选择该按钮， `onclick` 脚本将不会运行。  这是因为脚本未立即运行，在未将事件发生视为内容脚本的一部分之前不会解释代码，因此页面 \(而非 Extension\) 的 CSP 将限制行为。 `click`  由于该 CSP 不指定 `unsafe-inline` ，内联事件处理程序将被阻止。  
在这种情况下实现所需行为的正确方法可能是将处理程序添加为内容脚本中的函数， `onclick` 如下所示：  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

如果内容脚本运行以下内容，也会出现另一个类似问题：  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

在这种情况下，脚本将运行并显示警报。  但是，请看一下这种情况：  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

在初始脚本运行时，将阻止对 `eval` 的调用。  也就是说，虽然允许初始脚本运行时，但脚本内的行为由页面的 CSP 进行控制。  
因此，根据你在扩展中编写 DOM 注入脚本的方法，对页面 CSP 的更改可能会影响扩展的行为。  由于内容脚本不受页面 CSP 的影响，因此，这是将尽可能多的扩展行为放入内容脚本（而不是 DOM 注入脚本）中的原因。  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "内容安全策略策略简介|HTML5 百年"  
[PublicSuffixList]: https://publicsuffix.org/list "查看公共后缀列表"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\<script\> 元素的哈希用法 - 内容安全策略级别 2 |W3C"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "内容安全策略级别 3 |W3C"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "中间人攻击|Wikipedia"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/extensions/contentSecurityPolicy)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
