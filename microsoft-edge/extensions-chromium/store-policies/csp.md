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
# <span data-ttu-id="8fbf2-104">内容安全策略 \ （CSP \）</span><span class="sxs-lookup"><span data-stu-id="8fbf2-104">Content Security Policy \(CSP\)</span></span>  

<span data-ttu-id="8fbf2-105">为了减少可能出现的跨网站脚本问题的大型类，Microsoft Edge 扩展系统合并了[内容安全策略的一般概念 \ （CSP \）][W3CContentSecurityPolicy]。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-105">In order to mitigate a large class of potential cross-site scripting issues, the Microsoft Edge Extension system has incorporated the general concept of [Content Security Policy \(CSP\)][W3CContentSecurityPolicy].</span></span>  <span data-ttu-id="8fbf2-106">这引入了一些相当严格的策略，使扩展在默认情况下更安全，并使你能够创建和强制管理可由你的扩展和应用程序加载和运行的内容类型的规则。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-106">This introduces some fairly strict policies that make Extensions more secure by default, and provides you with the ability to create and enforce rules governing the types of content that may be loaded and run by your Extensions and applications.</span></span>  

<span data-ttu-id="8fbf2-107">通常，CSP 适用于由你的扩展加载或运行的资源的 block/allowlisting 机制。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-107">In general, CSP works as a block/allowlisting mechanism for resources loaded or run by your Extensions.</span></span>  <span data-ttu-id="8fbf2-108">为你的扩展定义合理的策略使你能够仔细考虑你的扩展需要的资源，并要求浏览器确保这些资源是你的扩展有权访问的唯一资源。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-108">Defining a reasonable policy for your Extension enables you to carefully consider the resources that your Extension requires, and to ask the browser to ensure that those are the only resources your Extension has access to.</span></span>  <span data-ttu-id="8fbf2-109">这些策略不仅可提供主机权限，还可提供延长请求的安全性;它们是一种额外的保护层，而不是替代。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-109">These policies provide security over and above the host permissions your Extension requests; they are an additional layer of protection, not a replacement.</span></span>  

<span data-ttu-id="8fbf2-110">在 web 上，此类策略是通过 HTTP 头或元素定义的 `meta` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-110">On the web, such a policy is defined via an HTTP header or `meta` element.</span></span>  <span data-ttu-id="8fbf2-111">在 Microsoft Edge 扩展系统内部，这两种机制都不是一种合适的机制。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-111">Inside the Microsoft Edge Extension system, neither is an appropriate mechanism.</span></span>  <span data-ttu-id="8fbf2-112">相反，扩展策略是通过 `manifest.json` 扩展名的文件定义的，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-112">Instead, an Extension policy is defined via the `manifest.json` file for the Extension as follows:</span></span>  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> <span data-ttu-id="8fbf2-113">有关 CSP 语法的完整详细信息，请参阅[内容安全策略规范][W3CContentSecurityPolicy]和 HTML5Rocks 上的["内容安全策略简介" 一][HTML5RocksIntroductionContentSecurityPolicy]文。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-113">For full details regarding the CSP syntax, please take a look at the [Content Security Policy specification][W3CContentSecurityPolicy] , and the ["An Introduction to Content Security Policy"][HTML5RocksIntroductionContentSecurityPolicy] article on HTML5Rocks.</span></span>  

## <span data-ttu-id="8fbf2-114">默认策略限制</span><span class="sxs-lookup"><span data-stu-id="8fbf2-114">Default Policy Restrictions</span></span>  

<span data-ttu-id="8fbf2-115">未定义 a 的程序包不 `manifest_version` 具有默认内容安全策略。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-115">Packages that do not define a `manifest_version` do not have a default content security policy.</span></span>  <span data-ttu-id="8fbf2-116">选择2的 `manifest_version` 默认内容安全策略是：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-116">Those that select `manifest_version` 2, have a default content security policy of:</span></span>  

```javascript
script-src 'self'; object-src 'self'
```  

<span data-ttu-id="8fbf2-117">此策略通过以下三种方式来限制扩展和应用程序，从而增加安全性：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-117">This policy adds security by limiting Extensions and applications in three ways:</span></span>  

**<span data-ttu-id="8fbf2-118">已禁用 Eval 和相关函数</span><span class="sxs-lookup"><span data-stu-id="8fbf2-118">Eval and related functions are disabled</span></span>**  

<span data-ttu-id="8fbf2-119">如下代码不起作用：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-119">Code like the following does not work:</span></span>  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

<span data-ttu-id="8fbf2-120">按如下方式计算 JavaScript 的字符串是常见的 XSS 攻击媒介。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-120">Evaluating strings of JavaScript like this is a common XSS attack vector.</span></span>  <span data-ttu-id="8fbf2-121">应改为编写如下代码：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-121">Instead, you should write code like:</span></span>

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**<span data-ttu-id="8fbf2-122">内联 JavaScript 不运行</span><span class="sxs-lookup"><span data-stu-id="8fbf2-122">Inline JavaScript are not run</span></span>**  

<span data-ttu-id="8fbf2-123">内联 JavaScript 不会运行。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-123">Inline JavaScript are not run.</span></span>  <span data-ttu-id="8fbf2-124">此限制 bans 内联 `<script>` 块和内联事件处理程序（如） `<button onclick="...">` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-124">This restriction bans both inline `<script>` blocks and inline event handlers, such as `<button onclick="...">`.</span></span>

<span data-ttu-id="8fbf2-125">第一次限制是通过使您不能意外运行由恶意的第三方提供的脚本来擦除跨站点脚本攻击的大型类。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-125">The first restriction wipes out a huge class of cross-site scripting attacks by making it impossible for you to accidentally run the script provided by a malicious third-party.</span></span>  <span data-ttu-id="8fbf2-126">但是，它要求你使用内容和行为之间的完全分离来编写你的代码 \ （你应该无论如何都是如此，对吧？ \）。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-126">It does, however, require you to write your code with a clean separation between content and behavior \(which you should of course do anyway, right?\).</span></span>  <span data-ttu-id="8fbf2-127">示例可能会更清楚。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-127">An example may make this clearer.</span></span>  <span data-ttu-id="8fbf2-128">你可能会尝试编写一个浏览器操作弹出窗口，将其作为单个 `pop-up.html` 容器：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-128">You may try to write a Browser Action pop-up as a single `pop-up.html` containing:</span></span>  

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

<span data-ttu-id="8fbf2-129">必须更改三项内容才能按预期方式执行此操作：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-129">Three things must change in order to make this work the way you expect it to:</span></span>  

*   <span data-ttu-id="8fbf2-130">`clickHandler`定义必须移到外部 JavaScript 文件 \ （ `popup.js` 可能是一个较好的目标）。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-130">The `clickHandler` definition must be moved into an external JavaScript file \(`popup.js` may be a good target).</span></span>  
*   <span data-ttu-id="8fbf2-131">内联事件处理程序定义必须被重写 `addEventListener` 并提取到中 `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-131">The inline event handler definitions must be rewritten in terms of `addEventListener` and extracted into `popup.js`.</span></span>  
    <span data-ttu-id="8fbf2-132">如果当前正在使用类似代码启动程序，请 `<body onload="main();">` 考虑通过挂钩到 `DOMContentLoaded` 文档事件或窗口事件来替换它 `load` ，具体取决于你的要求。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-132">If you are currently starting your program using code like `<body onload="main();">`, consider replacing it by hooking into the `DOMContentLoaded` event of the document, or the `load` event of the window, depending on your requirements.</span></span>  <span data-ttu-id="8fbf2-133">使用以前的，因为它通常会更快地触发。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-133">Use the former, since it generally triggers more quickly.</span></span>  

*   <span data-ttu-id="8fbf2-134">`setTimeout`必须重写该调用，以避免将字符串转换为 `"awesome(); totallyAwesome()"` 运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-134">The `setTimeout` call must be rewritten to avoid converting the string `"awesome(); totallyAwesome()"` into JavaScript for running.</span></span>  
    <span data-ttu-id="8fbf2-135">这些更改可能类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-135">Those changes may look something like the following:</span></span>  

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

**<span data-ttu-id="8fbf2-136">仅加载本地脚本和对象资源</span><span class="sxs-lookup"><span data-stu-id="8fbf2-136">Only local script and object resources are loaded</span></span>**  

<span data-ttu-id="8fbf2-137">脚本和对象资源只能从扩展包加载，而不能从 web 上加载。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-137">Script and object resources are only able to be loaded from the Extension package, not from the web at large.</span></span>  <span data-ttu-id="8fbf2-138">这可确保你的扩展仅运行你专门批准的代码，防止活动网络攻击者恶意重定向你的资源请求。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-138">This ensures that your Extension only runs the code you specifically approved, preventing an active network attacker from maliciously redirecting your request for a resource.</span></span>  

<span data-ttu-id="8fbf2-139">不必编写依赖于 jQuery \ （或任何其他库 \）从外部 CDN 加载的代码，请考虑在扩展程序包中包含 jQuery 的特定版本。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-139">Instead of writing code that depends on jQuery \(or any other library\) loading from an external CDN, consider including the specific version of jQuery in your Extension package.</span></span>  <span data-ttu-id="8fbf2-140">也就是说，而不是：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-140">That is, instead of:</span></span>  

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

<span data-ttu-id="8fbf2-141">下载文件，将其包含在程序包中，然后编写：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-141">Download the file, include it in your package, and write:</span></span>  

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

## <span data-ttu-id="8fbf2-142">放松默认策略</span><span class="sxs-lookup"><span data-stu-id="8fbf2-142">Relaxing the default policy</span></span>  

**<span data-ttu-id="8fbf2-143">内联脚本</span><span class="sxs-lookup"><span data-stu-id="8fbf2-143">Inline Script</span></span>**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

<span data-ttu-id="8fbf2-144">通过指定策略中的源代码的 base64 编码哈希，可以允许内联脚本。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-144">Inline scripts are able to be allowed by specifying the base64-encoded hash of the source code in the policy.</span></span>  <span data-ttu-id="8fbf2-145">此哈希必须以已使用的哈希算法 \ （sha256、sha384 或 sha512 \）为前缀。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-145">This hash must be prefixed by the used hash algorithm \(sha256, sha384 or sha512\).</span></span>  <span data-ttu-id="8fbf2-146">有关示例，请参阅[<脚本 \ > 元素的哈希用法][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-146">See [Hash usage for \<script\> elements][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage] for an example.</span></span>  

**<span data-ttu-id="8fbf2-147">远程脚本</span><span class="sxs-lookup"><span data-stu-id="8fbf2-147">Remote Script</span></span>**  

<span data-ttu-id="8fbf2-148">如果你需要某些外部 JavaScript 或对象资源，你可以通过 allowlisting 安全来源（应接受脚本）将策略放宽到有限的范围。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-148">If you require some external JavaScript or object resources, you may relax the policy to a limited extent by allowlisting secure origins from which scripts should be accepted.</span></span>  <span data-ttu-id="8fbf2-149">验证使用扩展权限提升权限加载的运行时资源是否与你所需的资源完全一致，并且不会由活动网络攻击者替换。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-149">Verify that runtime resources loaded with with elevated permissions of an Extension are exactly the resources you expect, and are not replaced by an active network attacker.</span></span>  <span data-ttu-id="8fbf2-150">由于[中间人攻击][WikiManMiddleAttacks]在 HTTP 上是简单且不可检测的，因此不接受这些来源。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-150">As [man-in-the-middle attacks][WikiManMiddleAttacks] are both trivial and undetectable over HTTP, those origins are not accepted.</span></span>  

<span data-ttu-id="8fbf2-151">目前，开发人员可以使用以下方案 allowlist 来源：、、 `blob` `filesystem` `https` 和 `extension` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-151">Currently, developers are able to allowlist origins with the following schemes: `blob`, `filesystem`, `https`, and `extension`.</span></span>  <span data-ttu-id="8fbf2-152">必须为和方案显式指定源的主机部分 `https` `extension` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-152">The host part of the origin must explicitly be specified for the `https` and `extension` schemes.</span></span>  <span data-ttu-id="8fbf2-153">不允许使用常规通配符，如 https：、 `https://*` 和 `https://*.com` 不允许; `https://*.example.com` 允许使用子域通配符。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-153">Generic wildcards such as https:, `https://*` and `https://*.com` are not allowed; subdomain wildcards such as `https://*.example.com` are allowed.</span></span>  <span data-ttu-id="8fbf2-154">[公用后缀列表][PublicSuffixList]中的域也被视为常规顶级域。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-154">Domains in the [Public Suffix list][PublicSuffixList] are also viewed as generic top-level domains.</span></span>  <span data-ttu-id="8fbf2-155">若要从这些域加载资源，子域必须明确列出。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-155">To load a resource from these domains, the subdomain must explicitly be listed.</span></span>  <span data-ttu-id="8fbf2-156">例如，无效 `https://*.cloudfront.net` ，但 `https://XXXX.cloudfront.net` `https://*.XXXX.cloudfront.net` 能够 allowlisted。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-156">For example, `https://*.cloudfront.net` is not valid, but `https://XXXX.cloudfront.net` and `https://*.XXXX.cloudfront.net` are able to be allowlisted.</span></span>  

<span data-ttu-id="8fbf2-157">为了便于开发，通过 HTTP 从本地计算机上的服务器加载的资源可以 allowlisted。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-157">For development ease, resources loaded over HTTP from servers on your local machine are able to be allowlisted.</span></span>  <span data-ttu-id="8fbf2-158">你可以在或的任何端口上 allowlist 脚本和对象 `http://127.0.0.1` 源 `http://localhost` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-158">You may allowlist script and object sources on any port of either `http://127.0.0.1` or `http://localhost`.</span></span>  

> [!NOTE]
> <span data-ttu-id="8fbf2-159">对通过 HTTP 加载的资源的限制仅适用于直接运行的资源。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-159">The restriction against resources loaded over HTTP applies only to those resources which are directly run.</span></span>  <span data-ttu-id="8fbf2-160">例如，您仍然可以免费连接到您喜欢的任何来源的 XMLHTTPRequest 连接;默认策略不会 `connect-src` 以任何方式限制或任何其他 CSP 指令。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-160">You are still free, for example, to make XMLHTTPRequest connections to any origin you like; the default policy does not restrict `connect-src` or any of the other CSP directives in any way.</span></span>  

<span data-ttu-id="8fbf2-161">允许通过 HTTPS 从 example.com 加载脚本资源的松散策略定义可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-161">A relaxed policy definition which allows script resources to be loaded from example.com over HTTPS may look like:</span></span>  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> <span data-ttu-id="8fbf2-162">`script-src`和 `object-src` 均由策略定义。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-162">Both `script-src` and `object-src` are defined by the policy.</span></span>  <span data-ttu-id="8fbf2-163">Microsoft Edge 不接受不将每个值限制为 \ （至少 \） "" 的策略 `self` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-163">Microsoft Edge does not accept a policy that does not limit each of these values to \(at least\) '`self`'.</span></span>  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**<span data-ttu-id="8fbf2-164">评估的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="8fbf2-164">Evaluated JavaScript</span></span>**  

<span data-ttu-id="8fbf2-165">策略 `eval()` 和相关函数（如、 `setTimeout(String)` `setInterval(String)` 和）可以 `new Function(String)` 通过添加 `unsafe-eval` 到你的策略来放松：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-165">The policy against `eval()` and related functions like `setTimeout(String)`, `setInterval(String)`, and `new Function(String)` are able to be relaxed by adding `unsafe-eval` to your policy:</span></span>  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

<span data-ttu-id="8fbf2-166">但是，我们强烈建议您执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-166">However, we strongly recommend against doing this.</span></span>  <span data-ttu-id="8fbf2-167">这些函数是 notorious XSS 攻击媒介。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-167">These functions are notorious XSS attack vectors.</span></span>  

## <span data-ttu-id="8fbf2-168">加强默认策略</span><span class="sxs-lookup"><span data-stu-id="8fbf2-168">Tightening the default policy</span></span>  

<span data-ttu-id="8fbf2-169">当然，你可以将此政策提升到扩展所允许的任何程度，以便在方便的时候提高安全性。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-169">You may, of course, tighten this policy to whatever extent your Extension allows in order to increase security at the expense of convenience.</span></span>  <span data-ttu-id="8fbf2-170">若要指定你的扩展只能从关联的扩展包加载任何类型 \ （图像等）的资源，例如 `default-src 'self'` 可能适用的策略。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-170">To specify that your Extension are able to only load resources of any type \(images, and so on\) from the associated Extension package, for example, a policy of `default-src 'self'` may be appropriate.</span></span>  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## <span data-ttu-id="8fbf2-171">内容脚本</span><span class="sxs-lookup"><span data-stu-id="8fbf2-171">Content Scripts</span></span>  

<span data-ttu-id="8fbf2-172">正在讨论的策略适用于扩展的背景页和事件页面。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-172">The policy being discussing applies to the background pages and event pages of the Extension.</span></span>  <span data-ttu-id="8fbf2-173">内容脚本对扩展内容脚本的应用方式更复杂。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-173">How the content scripts apply to the content scripts of the Extension is more complicated.</span></span>  

<span data-ttu-id="8fbf2-174">内容脚本通常不受扩展的 CSP 制约。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-174">Content scripts are generally not subject to the CSP of the Extension.</span></span>  <span data-ttu-id="8fbf2-175">由于内容脚本并非 HTML，因此这种情况的主要影响是即使扩展的 CSP 不指定，它们也可能会使用 `eval` `unsafe-eval` ，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-175">Since content scripts are not HTML, the main impact of this is that they may use `eval` even if the CSP of the Extension does not specify `unsafe-eval`, although this is not recommended.</span></span>  <span data-ttu-id="8fbf2-176">此外，页面的 CSP 不适用于内容脚本。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-176">Additionally, the CSP of the page does not apply to content scripts.</span></span>  <span data-ttu-id="8fbf2-177">更复杂的是 `<script>` 内容脚本创建并放置在其运行的页面的 DOM 中的标记。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-177">More complicated are `<script>` tags that content scripts create and put into the DOM of the page they are running on.</span></span>  <span data-ttu-id="8fbf2-178">这些脚本将作为即将转发的 DOM 插入脚本进行引用。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-178">These are referenced as DOM injected scripts going forward.</span></span>  

<span data-ttu-id="8fbf2-179">在插入到页面后立即运行的 DOM 插入的脚本将按预期的方式运行。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-179">DOM injected scripts that run immediately upon injection into the page runs as you may expect.</span></span>  <span data-ttu-id="8fbf2-180">想象一个内容脚本，其中包含以下代码作为一个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-180">Imagine a content script with the following code as a simple example:</span></span>  

```javascript
document.write("<script>alert(1);</script>");
 ```  

<span data-ttu-id="8fbf2-181">此内容脚本立即导致 `alert` `document.write()` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-181">This content script causes an `alert` immediately upon the `document.write()`.</span></span>  <span data-ttu-id="8fbf2-182">请注意，无论页面可能指定的策略如何，都会运行此操作。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-182">Note that this runs regardless of the policy a page may specify.</span></span>
<span data-ttu-id="8fbf2-183">但是，该行为将在该 DOM 插入脚本和任何不会在注入时立即运行的脚本中变得更复杂。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-183">However, the behavior becomes more complicated both inside that DOM injected script and for any script that does not immediately run upon injection.</span></span>  <span data-ttu-id="8fbf2-184">假设你的扩展正在页面上运行，该页面提供指定的关联 CSP `script-src 'self'` 。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-184">Imagine that your Extension is running on a page that provides an associated CSP that specifies `script-src 'self'`.</span></span>  <span data-ttu-id="8fbf2-185">现在，假设内容脚本运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-185">Now imagine the content script runs the following code:</span></span>  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

<span data-ttu-id="8fbf2-186">如果用户单击该按钮， `onclick` 脚本将不会运行。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-186">If a user clicks on that button, the `onclick` script does not run.</span></span>  <span data-ttu-id="8fbf2-187">这是因为脚本不会立即运行，并且不会将代码解释为内容脚本的一部分，因此不会将代码视为内容脚本的一部分，因此页面的 CSP （不是扩展名 \）会限制行为。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-187">This is because the script did not immediately run and code is not interpreted until the click event occurs is not considered part of the content script, so the CSP of the page \(not of the Extension\) restricts the behavior.</span></span>  <span data-ttu-id="8fbf2-188">由于该 CSP 不指定，因此 `unsafe-inline` 内联事件处理程序被阻止。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-188">And since that CSP does not specify `unsafe-inline`, the inline event handler is blocked.</span></span>  
<span data-ttu-id="8fbf2-189">在这种情况下，实现所需行为的正确方法可能是 `onclick` 通过内容脚本中的函数添加处理程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-189">The correct way to implement the desired behavior in this case may be to add the `onclick` handler as a function from the content script as follows:</span></span>  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

<span data-ttu-id="8fbf2-190">如果内容脚本运行以下内容，则会出现另一个类似问题：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-190">Another similar issue arises if the content script runs the following:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="8fbf2-191">在这种情况下，脚本将运行，并显示警报。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-191">In this case, the script runs and the alert displays.</span></span>  <span data-ttu-id="8fbf2-192">但是，请考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="8fbf2-192">However, take this case:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="8fbf2-193">运行初始脚本时，将 `eval` 阻止呼叫。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-193">While the initial script runs, the call to `eval` is blocked.</span></span>  <span data-ttu-id="8fbf2-194">也就是说，在允许初始脚本运行时，脚本内的行为由页面的 CSP 管制。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-194">That is, while the initial script runtime is allowed, the behavior within the script is regulated by the CSP of the page.</span></span>  
<span data-ttu-id="8fbf2-195">因此，根据你在扩展中编写 DOM 插入的脚本的方式，对页面的 CSP 所做的更改可能会影响你的扩展的行为。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-195">Thus, depending on how you write DOM injected scripts in your Extension, changes to the CSP of the page may affect the behavior of your Extension.</span></span>  <span data-ttu-id="8fbf2-196">由于页面的 CSP 不会影响内容脚本，因此这是将尽可能多的扩展放入内容脚本（而不是 DOM 插入的脚本）的重要理由。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-196">Since content scripts are not affected by the CSP of the page, this a great reason to put as much behavior as possible of your Extension into the content script rather than DOM injected scripts.</span></span>  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "内容安全策略简介-HTML5 Rocks"  
[PublicSuffixList]: https://publicsuffix.org/list "查看公用后缀列表"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\ <脚本 \ > 元素-内容安全策略级别2的哈希使用情况"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "内容安全策略级别3"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "中间人攻击-维基百科"  

> [!NOTE]
> <span data-ttu-id="8fbf2-202">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8fbf2-203">可在[此处](https://developer.chrome.com/extensions/contentSecurityPolicy)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-203">The original page is found [here](https://developer.chrome.com/extensions/contentSecurityPolicy).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="8fbf2-205">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8fbf2-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
