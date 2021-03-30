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
# <a name="content-security-policy-csp"></a><span data-ttu-id="15fd1-104">内容安全策略 \(CSP\) </span><span class="sxs-lookup"><span data-stu-id="15fd1-104">Content Security Policy \(CSP\)</span></span>  

<span data-ttu-id="15fd1-105">为了缓解大量潜在的跨站点脚本问题，Microsoft Edge 扩展系统已纳入内容安全策略 [\(CSP\) ][W3CContentSecurityPolicy]的一般概念。</span><span class="sxs-lookup"><span data-stu-id="15fd1-105">In order to mitigate a large class of potential cross-site scripting issues, the Microsoft Edge Extension system has incorporated the general concept of [Content Security Policy \(CSP\)][W3CContentSecurityPolicy].</span></span>  <span data-ttu-id="15fd1-106">这引入了一些相当严格的策略，这些策略使扩展在默认情况下更加安全，并让你能够创建和实施规则，以管理扩展和应用程序可能加载和运行的内容类型。</span><span class="sxs-lookup"><span data-stu-id="15fd1-106">This introduces some fairly strict policies that make Extensions more secure by default, and provides you with the ability to create and enforce rules governing the types of content that may be loaded and run by your Extensions and applications.</span></span>  

<span data-ttu-id="15fd1-107">通常，CSP 用作扩展加载或运行的资源块/允许列表机制。</span><span class="sxs-lookup"><span data-stu-id="15fd1-107">In general, CSP works as a block/allowlisting mechanism for resources loaded or run by your Extensions.</span></span>  <span data-ttu-id="15fd1-108">通过为扩展定义合理的策略，可以仔细考虑扩展所需的资源，并要求浏览器确保这些是扩展有权访问的唯一资源。</span><span class="sxs-lookup"><span data-stu-id="15fd1-108">Defining a reasonable policy for your Extension enables you to carefully consider the resources that your Extension requires, and to ask the browser to ensure that those are the only resources your Extension has access to.</span></span>  <span data-ttu-id="15fd1-109">这些策略在扩展请求的主机权限之上提供安全性;它们是一层额外的保护，而不是替代。</span><span class="sxs-lookup"><span data-stu-id="15fd1-109">The policies provide security over and above the host permissions your Extension requests; they are an additional layer of protection, not a replacement.</span></span>  

<span data-ttu-id="15fd1-110">在 Web 上，此类策略通过 HTTP 标头或元素 `meta` 定义。</span><span class="sxs-lookup"><span data-stu-id="15fd1-110">On the web, such a policy is defined via an HTTP header or `meta` element.</span></span>  <span data-ttu-id="15fd1-111">在 Microsoft Edge 扩展系统中，两者都不是适当的机制。</span><span class="sxs-lookup"><span data-stu-id="15fd1-111">Inside the Microsoft Edge Extension system, neither is an appropriate mechanism.</span></span>  <span data-ttu-id="15fd1-112">相反，扩展策略是使用扩展文件定义的 `manifest.json` ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="15fd1-112">Instead, an Extension policy is defined using the `manifest.json` file for the Extension as follows:</span></span>  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> <span data-ttu-id="15fd1-113">有关 CSP 语法的完整详细信息，请查看内容安全策略规范以及 HTML5Rocks 上的"内容[][HTML5RocksIntroductionContentSecurityPolicy]安全策略简介"一文。 [][W3CContentSecurityPolicy]</span><span class="sxs-lookup"><span data-stu-id="15fd1-113">For full details regarding the CSP syntax, please take a look at the [Content Security Policy specification][W3CContentSecurityPolicy] , and the ["An Introduction to Content Security Policy"][HTML5RocksIntroductionContentSecurityPolicy] article on HTML5Rocks.</span></span>  

## <a name="default-policy-restrictions"></a><span data-ttu-id="15fd1-114">默认策略限制</span><span class="sxs-lookup"><span data-stu-id="15fd1-114">Default Policy Restrictions</span></span>  

<span data-ttu-id="15fd1-115">未定义内容的包 `manifest_version` 没有默认内容安全策略。</span><span class="sxs-lookup"><span data-stu-id="15fd1-115">Packages that do not define a `manifest_version` do not have a default content security policy.</span></span>  <span data-ttu-id="15fd1-116">选择 `manifest_version` 2 的程序包具有以下默认内容安全策略。</span><span class="sxs-lookup"><span data-stu-id="15fd1-116">Packages that choose `manifest_version` 2, have a the follwoing default content security policy.</span></span>  

```javascript
script-src 'self'; object-src 'self'
```  

<span data-ttu-id="15fd1-117">该策略通过以下三种方式限制扩展和应用程序来增加安全性：</span><span class="sxs-lookup"><span data-stu-id="15fd1-117">The policy adds security by limiting Extensions and applications in three ways:</span></span>  

**<span data-ttu-id="15fd1-118">Eval 和相关函数已禁用</span><span class="sxs-lookup"><span data-stu-id="15fd1-118">Eval and related functions are disabled</span></span>**  

<span data-ttu-id="15fd1-119">如下所示的代码不起作用：</span><span class="sxs-lookup"><span data-stu-id="15fd1-119">Code like the following does not work:</span></span>  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

<span data-ttu-id="15fd1-120">按如下所示评估 JavaScript 字符串是一种常见的 XSS 攻击途径。</span><span class="sxs-lookup"><span data-stu-id="15fd1-120">Evaluating strings of JavaScript like this is a common XSS attack vector.</span></span>  <span data-ttu-id="15fd1-121">相反，应编写类似代码：</span><span class="sxs-lookup"><span data-stu-id="15fd1-121">Instead, you should write code like:</span></span>

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**<span data-ttu-id="15fd1-122">未运行内联 JavaScript</span><span class="sxs-lookup"><span data-stu-id="15fd1-122">Inline JavaScript are not run</span></span>**  

<span data-ttu-id="15fd1-123">不运行内联 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="15fd1-123">Inline JavaScript are not run.</span></span>  <span data-ttu-id="15fd1-124">此限制同时禁止内联 `<script>` 块和内联事件处理程序，如 `<button onclick="...">` 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-124">This restriction bans both inline `<script>` blocks and inline event handlers, such as `<button onclick="...">`.</span></span>

<span data-ttu-id="15fd1-125">第一个限制通过使您无法意外运行恶意第三方提供的脚本来擦除大量跨网站脚本攻击。</span><span class="sxs-lookup"><span data-stu-id="15fd1-125">The first restriction wipes out a huge class of cross-site scripting attacks by making it impossible for you to accidentally run the script provided by a malicious third-party.</span></span>  <span data-ttu-id="15fd1-126">但是，它确实需要你在内容和行为 \(之间以干净分隔方式编写代码，正确吗？\) 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-126">It does, however, require you to write your code with a clean separation between content and behavior \(which you should of course do anyway, right?\).</span></span>  <span data-ttu-id="15fd1-127">示例可以使这一点更加清晰。</span><span class="sxs-lookup"><span data-stu-id="15fd1-127">An example may make this clearer.</span></span>  <span data-ttu-id="15fd1-128">您可以尝试将浏览器操作弹出窗口编写为一个包含 `pop-up.html` ：</span><span class="sxs-lookup"><span data-stu-id="15fd1-128">You may try to write a Browser Action pop-up as a single `pop-up.html` containing:</span></span>  

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

<span data-ttu-id="15fd1-129">若要使此操作按预期方式工作，必须更改三项内容：</span><span class="sxs-lookup"><span data-stu-id="15fd1-129">Three things must change in order to make this work the way you expect it to:</span></span>  

*   <span data-ttu-id="15fd1-130">必须将 `clickHandler` 定义移动到外部 JavaScript 文件 \(`popup.js` 可能是一个不错的) 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-130">The `clickHandler` definition must be moved into an external JavaScript file \(`popup.js` may be a good target).</span></span>  
*   <span data-ttu-id="15fd1-131">必须重写内联事件处理程序定义，并 `addEventListener` 提取到 `popup.js` 中。</span><span class="sxs-lookup"><span data-stu-id="15fd1-131">The inline event handler definitions must be rewritten in terms of `addEventListener` and extracted into `popup.js`.</span></span>  
    <span data-ttu-id="15fd1-132">如果当前使用类似代码启动程序，请考虑通过挂钩到文档事件或窗口事件来替换它， `<body onload="main();">` `DOMContentLoaded` `load` 具体取决于您的要求。</span><span class="sxs-lookup"><span data-stu-id="15fd1-132">If you are currently starting your program using code like `<body onload="main();">`, consider replacing it by hooking into the `DOMContentLoaded` event of the document, or the `load` event of the window, depending on your requirements.</span></span>  <span data-ttu-id="15fd1-133">使用前者，因为它通常更快速地触发。</span><span class="sxs-lookup"><span data-stu-id="15fd1-133">Use the former, since it generally triggers more quickly.</span></span>  

*   <span data-ttu-id="15fd1-134">`setTimeout`必须重写调用以避免将字符串 `"awesome(); totallyAwesome()"` 转换为 JavaScript 以运行。</span><span class="sxs-lookup"><span data-stu-id="15fd1-134">The `setTimeout` call must be rewritten to avoid converting the string `"awesome(); totallyAwesome()"` into JavaScript for running.</span></span>  
    <span data-ttu-id="15fd1-135">这些更改可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="15fd1-135">Those changes may look something like the following:</span></span>  

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

**<span data-ttu-id="15fd1-136">仅加载本地脚本和对象资源</span><span class="sxs-lookup"><span data-stu-id="15fd1-136">Only local script and object resources are loaded</span></span>**  

<span data-ttu-id="15fd1-137">脚本和对象资源只能从扩展包加载，而不是从整个 Web 加载。</span><span class="sxs-lookup"><span data-stu-id="15fd1-137">Script and object resources are only able to be loaded from the Extension package, not from the web at large.</span></span>  <span data-ttu-id="15fd1-138">这将确保您的扩展仅运行您专门批准的代码，从而阻止活动网络攻击者恶意重定向资源请求。</span><span class="sxs-lookup"><span data-stu-id="15fd1-138">This ensures that your Extension only runs the code you specifically approved, preventing an active network attacker from maliciously redirecting your request for a resource.</span></span>  

<span data-ttu-id="15fd1-139">请考虑将 jQuery 的特定版本包括在扩展包中，而不是编写依赖于 jQuery \(或其他任何库\) 从外部 CDN 加载的代码。</span><span class="sxs-lookup"><span data-stu-id="15fd1-139">Instead of writing code that depends on jQuery \(or any other library\) loading from an external CDN, consider including the specific version of jQuery in your Extension package.</span></span>  <span data-ttu-id="15fd1-140">也就是说，而不是：</span><span class="sxs-lookup"><span data-stu-id="15fd1-140">That is, instead of:</span></span>  

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

<span data-ttu-id="15fd1-141">下载文件，将该文件包括在程序包中，然后编写：</span><span class="sxs-lookup"><span data-stu-id="15fd1-141">Download the file, include it in your package, and write:</span></span>  

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

## <a name="relaxing-the-default-policy"></a><span data-ttu-id="15fd1-142">使默认策略更轻松</span><span class="sxs-lookup"><span data-stu-id="15fd1-142">Relaxing the default policy</span></span>  

**<span data-ttu-id="15fd1-143">内联脚本</span><span class="sxs-lookup"><span data-stu-id="15fd1-143">Inline Script</span></span>**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

<span data-ttu-id="15fd1-144">通过指定策略中源代码的 base64 编码哈希，可以允许内联脚本。</span><span class="sxs-lookup"><span data-stu-id="15fd1-144">Inline scripts are able to be allowed by specifying the base64-encoded hash of the source code in the policy.</span></span>  <span data-ttu-id="15fd1-145">此哈希必须以使用的哈希算法 \(sha256、sha384 或 sha512\) 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-145">This hash must be prefixed by the used hash algorithm \(sha256, sha384 or sha512\).</span></span>  <span data-ttu-id="15fd1-146">例如，导航到 [元素的哈希 \<script\> 用法][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]。</span><span class="sxs-lookup"><span data-stu-id="15fd1-146">For an example, navigate to [Hash usage for \<script\> elements][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage].</span></span>  

**<span data-ttu-id="15fd1-147">远程脚本</span><span class="sxs-lookup"><span data-stu-id="15fd1-147">Remote Script</span></span>**  

<span data-ttu-id="15fd1-148">如果您需要一些外部 JavaScript 或对象资源，则可能会允许列出应接受脚本的安全来源，从而在一定程度上放松策略。</span><span class="sxs-lookup"><span data-stu-id="15fd1-148">If you require some external JavaScript or object resources, you may relax the policy to a limited extent by allowlisting secure origins from which scripts should be accepted.</span></span>  <span data-ttu-id="15fd1-149">验证使用提升的扩展权限加载的运行时资源是否正是您期望的资源，并且不会替换为活动网络攻击者。</span><span class="sxs-lookup"><span data-stu-id="15fd1-149">Verify that runtime resources loaded with with elevated permissions of an Extension are exactly the resources you expect, and are not replaced by an active network attacker.</span></span>  <span data-ttu-id="15fd1-150">由于 [中间人攻击][WikiManMiddleAttacks] 在 HTTP 上既简单又无法检测，因此不接受这些来源。</span><span class="sxs-lookup"><span data-stu-id="15fd1-150">As [man-in-the-middle attacks][WikiManMiddleAttacks] are both trivial and undetectable over HTTP, those origins are not accepted.</span></span>  

<span data-ttu-id="15fd1-151">目前，开发人员能够允许具有以下方案列出源：、、 `blob` `filesystem` `https` 和 `extension` 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-151">Currently, developers are able to allowlist origins with the following schemes: `blob`, `filesystem`, `https`, and `extension`.</span></span>  <span data-ttu-id="15fd1-152">必须为和方案显式指定源的 `https` 主机 `extension` 部分。</span><span class="sxs-lookup"><span data-stu-id="15fd1-152">The host part of the origin must explicitly be specified for the `https` and `extension` schemes.</span></span>  <span data-ttu-id="15fd1-153">不允许使用诸如 https：等常规通配符;允许使用子域通配符（ `https://*` `https://*.com` `https://*.example.com` 如此类）。</span><span class="sxs-lookup"><span data-stu-id="15fd1-153">Generic wildcards such as https:, `https://*` and `https://*.com` are not allowed; subdomain wildcards such as `https://*.example.com` are allowed.</span></span>  <span data-ttu-id="15fd1-154">公共后缀 [列表中的域][PublicSuffixList] 也被视为通用顶级域。</span><span class="sxs-lookup"><span data-stu-id="15fd1-154">Domains in the [Public Suffix list][PublicSuffixList] are also viewed as generic top-level domains.</span></span>  <span data-ttu-id="15fd1-155">若要从这些域加载资源，必须显式列出子域。</span><span class="sxs-lookup"><span data-stu-id="15fd1-155">To load a resource from these domains, the subdomain must explicitly be listed.</span></span>  <span data-ttu-id="15fd1-156">例如 `https://*.cloudfront.net` ，无效，但 `https://XXXX.cloudfront.net` `https://*.XXXX.cloudfront.net` 能够 `allowlisted` 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-156">For example, `https://*.cloudfront.net` is not valid, but `https://XXXX.cloudfront.net` and `https://*.XXXX.cloudfront.net` are able to be `allowlisted`.</span></span>  

<span data-ttu-id="15fd1-157">为了便于开发，通过 HTTP 从本地计算机上服务器加载的资源可以 `allowlisted` 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-157">For development ease, resources loaded over HTTP from servers on your local machine are able to be `allowlisted`.</span></span>  <span data-ttu-id="15fd1-158">您可以允许列表脚本和对象源在任何端口的任一 `http://127.0.0.1` 或 `http://localhost` 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-158">You may allowlist script and object sources on any port of either `http://127.0.0.1` or `http://localhost`.</span></span>  

> [!NOTE]
> <span data-ttu-id="15fd1-159">对通过 HTTP 加载的资源的限制仅适用于直接运行的资源。</span><span class="sxs-lookup"><span data-stu-id="15fd1-159">The restriction against resources loaded over HTTP applies only to those resources which are directly run.</span></span>  <span data-ttu-id="15fd1-160">例如，您仍可以自由连接到您喜欢的任何源;默认策略不会以任何方式限制 `XMLHTTPRequest` `connect-src` 或其他任何 CSP 指令。</span><span class="sxs-lookup"><span data-stu-id="15fd1-160">You are still free, for example, to make `XMLHTTPRequest` connections to any origin you like; the default policy does not restrict `connect-src` or any of the other CSP directives in any way.</span></span>  

<span data-ttu-id="15fd1-161">允许通过 HTTPS 加载脚本资源的宽松策略定义可能 `example.com` 如下所示：</span><span class="sxs-lookup"><span data-stu-id="15fd1-161">A relaxed policy definition which allows script resources to be loaded from `example.com` over HTTPS may look like:</span></span>  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> <span data-ttu-id="15fd1-162">两 `script-src` `object-src` 者均由策略定义。</span><span class="sxs-lookup"><span data-stu-id="15fd1-162">Both `script-src` and `object-src` are defined by the policy.</span></span>  <span data-ttu-id="15fd1-163">Microsoft Edge 不接受不将每个值限制为 \(\) ' `self` 的策略。</span><span class="sxs-lookup"><span data-stu-id="15fd1-163">Microsoft Edge does not accept a policy that does not limit each of these values to \(at least\) '`self`'.</span></span>  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**<span data-ttu-id="15fd1-164">评估的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="15fd1-164">Evaluated JavaScript</span></span>**  

<span data-ttu-id="15fd1-165">针对策略和相关函数（如 ， ）并能够通过向策略添加 `eval()` `setTimeout(String)` `setInterval(String)` `new Function(String)` 来 `unsafe-eval` 轻松：</span><span class="sxs-lookup"><span data-stu-id="15fd1-165">The policy against `eval()` and related functions like `setTimeout(String)`, `setInterval(String)`, and `new Function(String)` are able to be relaxed by adding `unsafe-eval` to your policy:</span></span>  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

<span data-ttu-id="15fd1-166">但是，应避免制定策略。</span><span class="sxs-lookup"><span data-stu-id="15fd1-166">However, you should avoid relaxing policies.</span></span>  <span data-ttu-id="15fd1-167">这些函数是主要 XSS 攻击途径。</span><span class="sxs-lookup"><span data-stu-id="15fd1-167">The functions are notorious XSS attack vectors.</span></span>  

## <a name="tightening-the-default-policy"></a><span data-ttu-id="15fd1-168">强化默认策略</span><span class="sxs-lookup"><span data-stu-id="15fd1-168">Tightening the default policy</span></span>  

<span data-ttu-id="15fd1-169">当然，你可以将此策略严格到扩展允许的任何程度，以便以便利为代价提高安全性。</span><span class="sxs-lookup"><span data-stu-id="15fd1-169">You may, of course, tighten this policy to whatever extent your Extension allows in order to increase security at the expense of convenience.</span></span>  <span data-ttu-id="15fd1-170">若要指定你的扩展只能从关联的扩展包加载任何类型的 \(图像等\) 资源，例如，策略可能 `default-src 'self'` 适合。</span><span class="sxs-lookup"><span data-stu-id="15fd1-170">To specify that your Extension are able to only load resources of any type \(images, and so on\) from the associated Extension package, for example, a policy of `default-src 'self'` may be appropriate.</span></span>  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## <a name="content-scripts"></a><span data-ttu-id="15fd1-171">内容脚本</span><span class="sxs-lookup"><span data-stu-id="15fd1-171">Content Scripts</span></span>  

<span data-ttu-id="15fd1-172">正在讨论的策略适用于扩展的后台页面和事件页面。</span><span class="sxs-lookup"><span data-stu-id="15fd1-172">The policy being discussing applies to the background pages and event pages of the Extension.</span></span>  <span data-ttu-id="15fd1-173">内容脚本如何应用于扩展的内容脚本更为复杂。</span><span class="sxs-lookup"><span data-stu-id="15fd1-173">How the content scripts apply to the content scripts of the Extension is more complicated.</span></span>  

<span data-ttu-id="15fd1-174">内容脚本通常不受扩展 CSP 的遵守。</span><span class="sxs-lookup"><span data-stu-id="15fd1-174">Content scripts are generally not subject to the CSP of the Extension.</span></span>  <span data-ttu-id="15fd1-175">由于内容脚本不是 HTML，因此主要影响是即使扩展 CSP 未指定，它们也可能使用，尽管 `eval` `unsafe-eval` 不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="15fd1-175">Since content scripts are not HTML, the main impact of this is that they may use `eval` even if the CSP of the Extension does not specify `unsafe-eval`, although this is not recommended.</span></span>  <span data-ttu-id="15fd1-176">此外，页面的 CSP 不适用于内容脚本。</span><span class="sxs-lookup"><span data-stu-id="15fd1-176">Additionally, the CSP of the page does not apply to content scripts.</span></span>  <span data-ttu-id="15fd1-177">更复杂的是内容脚本创建并放入所运行页面 `<script>` 的 DOM 中的标记。</span><span class="sxs-lookup"><span data-stu-id="15fd1-177">More complicated are `<script>` tags that content scripts create and put into the DOM of the page they are running on.</span></span>  <span data-ttu-id="15fd1-178">这些脚本将作为 DOM 注入脚本进行引用。</span><span class="sxs-lookup"><span data-stu-id="15fd1-178">These are referenced as DOM injected scripts going forward.</span></span>  

<span data-ttu-id="15fd1-179">注入页面后立即运行的 DOM 注入脚本将如预期运行。</span><span class="sxs-lookup"><span data-stu-id="15fd1-179">DOM injected scripts that run immediately upon injection into the page runs as you may expect.</span></span>  <span data-ttu-id="15fd1-180">假设一个包含以下代码的内容脚本是一个简单示例：</span><span class="sxs-lookup"><span data-stu-id="15fd1-180">Imagine a content script with the following code as a simple example:</span></span>  

```javascript
document.write("<script>alert(1);</script>");
 ```  

<span data-ttu-id="15fd1-181">此内容脚本会立即 `alert` 在 `document.write()` .</span><span class="sxs-lookup"><span data-stu-id="15fd1-181">This content script causes an `alert` immediately upon the `document.write()`.</span></span>  <span data-ttu-id="15fd1-182">请注意，无论页面可以指定何种策略，都会运行此代码。</span><span class="sxs-lookup"><span data-stu-id="15fd1-182">Note that this runs regardless of the policy a page may specify.</span></span>
<span data-ttu-id="15fd1-183">但是，行为在 DOM 注入脚本内部以及任何在注入时不立即运行的脚本中都变得更加复杂。</span><span class="sxs-lookup"><span data-stu-id="15fd1-183">However, the behavior becomes more complicated both inside that DOM injected script and for any script that does not immediately run upon injection.</span></span>  <span data-ttu-id="15fd1-184">假设你的扩展在提供指定关联的云解决方案提供商的页面上运行 `script-src 'self'` 。</span><span class="sxs-lookup"><span data-stu-id="15fd1-184">Imagine that your Extension is running on a page that provides an associated CSP that specifies `script-src 'self'`.</span></span>  <span data-ttu-id="15fd1-185">现在，假设内容脚本运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="15fd1-185">Now imagine the content script runs the following code:</span></span>  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

<span data-ttu-id="15fd1-186">如果用户选择该按钮， `onclick` 则脚本不会运行。</span><span class="sxs-lookup"><span data-stu-id="15fd1-186">If a user chooses that button, the `onclick` script does not run.</span></span>  <span data-ttu-id="15fd1-187">这是因为脚本未立即运行，并且代码在未被视为内容脚本的一部分之前不会解释，因此页面 `click` \(而不是 Extension\) 的 CSP 将限制行为。</span><span class="sxs-lookup"><span data-stu-id="15fd1-187">This is because the script did not immediately run and code is not interpreted until the `click` event occurs is not considered part of the content script, so the CSP of the page \(not of the Extension\) restricts the behavior.</span></span>  <span data-ttu-id="15fd1-188">由于该 CSP 未指定， `unsafe-inline` 内联事件处理程序将被阻止。</span><span class="sxs-lookup"><span data-stu-id="15fd1-188">And since that CSP does not specify `unsafe-inline`, the inline event handler is blocked.</span></span>  
<span data-ttu-id="15fd1-189">在这种情况下实现所需行为的正确方法可能是将处理程序添加为内容脚本中的函数， `onclick` 如下所示：</span><span class="sxs-lookup"><span data-stu-id="15fd1-189">The correct way to implement the desired behavior in this case may be to add the `onclick` handler as a function from the content script as follows:</span></span>  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

<span data-ttu-id="15fd1-190">如果内容脚本运行以下内容，也会出现另一个类似问题：</span><span class="sxs-lookup"><span data-stu-id="15fd1-190">Another similar issue arises if the content script runs the following:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="15fd1-191">在这种情况下，脚本将运行并显示警报。</span><span class="sxs-lookup"><span data-stu-id="15fd1-191">In this case, the script runs and the alert displays.</span></span>  <span data-ttu-id="15fd1-192">但是，请看一下这种情况：</span><span class="sxs-lookup"><span data-stu-id="15fd1-192">However, take this case:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="15fd1-193">初始脚本运行时，将阻止 `eval` 对的调用。</span><span class="sxs-lookup"><span data-stu-id="15fd1-193">While the initial script runs, the call to `eval` is blocked.</span></span>  <span data-ttu-id="15fd1-194">也就是说，虽然允许初始脚本运行时，但脚本内的行为由页面的 CSP 进行控制。</span><span class="sxs-lookup"><span data-stu-id="15fd1-194">That is, while the initial script runtime is allowed, the behavior within the script is regulated by the CSP of the page.</span></span>  
<span data-ttu-id="15fd1-195">因此，根据在扩展中编写 DOM 注入脚本的方法，对页面 CSP 的更改可能会影响扩展的行为。</span><span class="sxs-lookup"><span data-stu-id="15fd1-195">Thus, depending on how you write DOM injected scripts in your Extension, changes to the CSP of the page may affect the behavior of your Extension.</span></span>  <span data-ttu-id="15fd1-196">由于内容脚本不受页面 CSP 的影响，因此，这是将扩展尽可能多的行为放入内容脚本（而不是 DOM 注入脚本）的一个重要原因。</span><span class="sxs-lookup"><span data-stu-id="15fd1-196">Since content scripts are not affected by the CSP of the page, this a great reason to put as much behavior as possible of your Extension into the content script rather than DOM injected scripts.</span></span>  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "内容安全策略策略|HTML5 元素"  
[PublicSuffixList]: https://publicsuffix.org/list "查看公共后缀列表"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\<script\> 元素的哈希用法 - 内容安全策略级别 2 |W3C"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "内容安全策略级别 3 |W3C"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "中间人攻击|Wikipedia"  

> [!NOTE]
> <span data-ttu-id="15fd1-202">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="15fd1-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="15fd1-203">原始页面位于 [此处](https://developer.chrome.com/extensions/contentSecurityPolicy)。</span><span class="sxs-lookup"><span data-stu-id="15fd1-203">The original page is found [here](https://developer.chrome.com/extensions/contentSecurityPolicy).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="15fd1-205">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="15fd1-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
