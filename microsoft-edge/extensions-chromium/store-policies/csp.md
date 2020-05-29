---
description: 边缘（Chromium）扩展的内容安全策略。
title: 内容安全策略（CSP）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 52d6d0afb38401250183788726013d521a269f06
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563339"
---
# 内容安全策略 \ （CSP \）  

为了减少可能出现的跨网站脚本问题的大型类，Microsoft Edge 扩展系统合并了[内容安全策略的一般概念 \ （CSP \）][W3CContentSecurityPolicy]。  这引入了一些相当严格的策略，使扩展在默认情况下更安全，并使你能够创建和强制管理可由你的扩展和应用程序加载和运行的内容类型的规则。  

通常，CSP 适用于由你的扩展加载或运行的资源的 block/allowlisting 机制。  为你的扩展定义合理的策略使你能够仔细考虑你的扩展需要的资源，并要求浏览器确保这些资源是你的扩展有权访问的唯一资源。  这些策略不仅可提供主机权限，还可提供延长请求的安全性;它们是一种额外的保护层，而不是替代。  

在 web 上，此类策略是通过 HTTP 头或元素定义的 `meta` 。  在 Microsoft Edge 扩展系统内部，这两种机制都不是一种合适的机制。  相反，扩展策略是通过 `manifest.json` 扩展名的文件定义的，如下所示：  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> 有关 CSP 语法的完整详细信息，请参阅[内容安全策略规范][W3CContentSecurityPolicy]和 HTML5Rocks 上的["内容安全策略简介" 一][HTML5RocksIntroductionContentSecurityPolicy]文。  

## 默认策略限制  

未定义 a 的程序包不 `manifest_version` 具有默认内容安全策略。  选择2的 `manifest_version` 默认内容安全策略是：  

```javascript
script-src 'self'; object-src 'self'
```  

此策略通过以下三种方式来限制扩展和应用程序，从而增加安全性：  

**已禁用 Eval 和相关函数**  

如下代码不起作用：  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

按如下方式计算 JavaScript 的字符串是常见的 XSS 攻击媒介。  应改为编写如下代码：

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**内联 JavaScript 不运行**  

内联 JavaScript 不会运行。  此限制 bans 内联 `<script>` 块和内联事件处理程序（如） `<button onclick="...">` 。

第一次限制是通过使您不能意外运行由恶意的第三方提供的脚本来擦除跨站点脚本攻击的大型类。  但是，它要求你使用内容和行为之间的完全分离来编写你的代码 \ （你应该无论如何都是如此，对吧？ \）。  示例可能会更清楚。  你可能会尝试编写一个浏览器操作弹出窗口，将其作为单个 `pop-up.html` 容器：  

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

必须更改三项内容才能按预期方式执行此操作：  

*   `clickHandler`定义必须移到外部 JavaScript 文件 \ （ `popup.js` 可能是一个较好的目标）。  
*   内联事件处理程序定义必须被重写 `addEventListener` 并提取到中 `popup.js` 。  
    如果当前正在使用类似代码启动程序，请 `<body onload="main();">` 考虑通过挂钩到 `DOMContentLoaded` 文档事件或窗口事件来替换它 `load` ，具体取决于你的要求。  使用以前的，因为它通常会更快地触发。  

*   `setTimeout`必须重写该调用，以避免将字符串转换为 `"awesome(); totallyAwesome()"` 运行的 JavaScript。  
    这些更改可能类似于以下内容：  

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

脚本和对象资源只能从扩展包加载，而不能从 web 上加载。  这可确保你的扩展仅运行你专门批准的代码，防止活动网络攻击者恶意重定向你的资源请求。  

不必编写依赖于 jQuery \ （或任何其他库 \）从外部 CDN 加载的代码，请考虑在扩展程序包中包含 jQuery 的特定版本。  也就是说，而不是：  

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

下载文件，将其包含在程序包中，然后编写：  

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

## 放松默认策略  

**内联脚本**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

通过指定策略中的源代码的 base64 编码哈希，可以允许内联脚本。  此哈希必须以已使用的哈希算法 \ （sha256、sha384 或 sha512 \）为前缀。  有关示例，请参阅[<脚本 \ > 元素的哈希用法][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]。  

**远程脚本**  

如果你需要某些外部 JavaScript 或对象资源，你可以通过 allowlisting 安全来源（应接受脚本）将策略放宽到有限的范围。  验证使用扩展权限提升权限加载的运行时资源是否与你所需的资源完全一致，并且不会由活动网络攻击者替换。  由于[中间人攻击][WikiManMiddleAttacks]在 HTTP 上是简单且不可检测的，因此不接受这些来源。  

目前，开发人员可以使用以下方案 allowlist 来源：、、 `blob` `filesystem` `https` 和 `extension` 。  必须为和方案显式指定源的主机部分 `https` `extension` 。  不允许使用常规通配符，如 https：、 `https://*` 和 `https://*.com` 不允许; `https://*.example.com` 允许使用子域通配符。  [公用后缀列表][PublicSuffixList]中的域也被视为常规顶级域。  若要从这些域加载资源，子域必须明确列出。  例如，无效 `https://*.cloudfront.net` ，但 `https://XXXX.cloudfront.net` `https://*.XXXX.cloudfront.net` 能够 allowlisted。  

为了便于开发，通过 HTTP 从本地计算机上的服务器加载的资源可以 allowlisted。  你可以在或的任何端口上 allowlist 脚本和对象 `http://127.0.0.1` 源 `http://localhost` 。  

> [!NOTE]
> 对通过 HTTP 加载的资源的限制仅适用于直接运行的资源。  例如，您仍然可以免费连接到您喜欢的任何来源的 XMLHTTPRequest 连接;默认策略不会 `connect-src` 以任何方式限制或任何其他 CSP 指令。  

允许通过 HTTPS 从 example.com 加载脚本资源的松散策略定义可能如下所示：  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> `script-src`和 `object-src` 均由策略定义。  Microsoft Edge 不接受不将每个值限制为 \ （至少 \） "" 的策略 `self` 。  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**评估的 JavaScript**  

策略 `eval()` 和相关函数（如、 `setTimeout(String)` `setInterval(String)` 和）可以 `new Function(String)` 通过添加 `unsafe-eval` 到你的策略来放松：  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

但是，我们强烈建议您执行此操作。  这些函数是 notorious XSS 攻击媒介。  

## 加强默认策略  

当然，你可以将此政策提升到扩展所允许的任何程度，以便在方便的时候提高安全性。  若要指定你的扩展只能从关联的扩展包加载任何类型 \ （图像等）的资源，例如 `default-src 'self'` 可能适用的策略。  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## 内容脚本  

正在讨论的策略适用于扩展的背景页和事件页面。  内容脚本对扩展内容脚本的应用方式更复杂。  

内容脚本通常不受扩展的 CSP 制约。  由于内容脚本并非 HTML，因此这种情况的主要影响是即使扩展的 CSP 不指定，它们也可能会使用 `eval` `unsafe-eval` ，但不建议这样做。  此外，页面的 CSP 不适用于内容脚本。  更复杂的是 `<script>` 内容脚本创建并放置在其运行的页面的 DOM 中的标记。  这些脚本将作为即将转发的 DOM 插入脚本进行引用。  

在插入到页面后立即运行的 DOM 插入的脚本将按预期的方式运行。  想象一个内容脚本，其中包含以下代码作为一个简单的示例：  

```javascript
document.write("<script>alert(1);</script>");
 ```  

此内容脚本立即导致 `alert` `document.write()` 。  请注意，无论页面可能指定的策略如何，都会运行此操作。
但是，该行为将在该 DOM 插入脚本和任何不会在注入时立即运行的脚本中变得更复杂。  假设你的扩展正在页面上运行，该页面提供指定的关联 CSP `script-src 'self'` 。  现在，假设内容脚本运行以下代码：  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

如果用户单击该按钮， `onclick` 脚本将不会运行。  这是因为脚本不会立即运行，并且不会将代码解释为内容脚本的一部分，因此不会将代码视为内容脚本的一部分，因此页面的 CSP （不是扩展名 \）会限制行为。  由于该 CSP 不指定，因此 `unsafe-inline` 内联事件处理程序被阻止。  
在这种情况下，实现所需行为的正确方法可能是 `onclick` 通过内容脚本中的函数添加处理程序，如下所示：  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

如果内容脚本运行以下内容，则会出现另一个类似问题：  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

在这种情况下，脚本将运行，并显示警报。  但是，请考虑以下情况：  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

运行初始脚本时，将 `eval` 阻止呼叫。  也就是说，在允许初始脚本运行时，脚本内的行为由页面的 CSP 管制。  
因此，根据你在扩展中编写 DOM 插入的脚本的方式，对页面的 CSP 所做的更改可能会影响你的扩展的行为。  由于页面的 CSP 不会影响内容脚本，因此这是将尽可能多的扩展放入内容脚本（而不是 DOM 插入的脚本）的重要理由。  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "内容安全策略简介-HTML5 Rocks"  
[PublicSuffixList]: https://publicsuffix.org/list "查看公用后缀列表"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\ <脚本 \ > 元素-内容安全策略级别2的哈希使用情况"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "内容安全策略级别3"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "中间人攻击-维基百科"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 可在[此处](https://developer.chrome.com/extensions/contentSecurityPolicy)找到原始页面。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
