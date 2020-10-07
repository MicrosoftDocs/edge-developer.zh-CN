---
description: Content Security Policy for Edge (Chromium) Extensions.
title: Content Security Policy (CSP)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, extensions development, browser extensions, addons, partner center, developer
ms.openlocfilehash: f3769639465d048c42ad0705f74598fbd1db8a20
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015714"
---
# <span data-ttu-id="87bc0-104">Content Security Policy \(CSP\)</span><span class="sxs-lookup"><span data-stu-id="87bc0-104">Content Security Policy \(CSP\)</span></span>  

<span data-ttu-id="87bc0-105">In order to mitigate a large class of potential cross-site scripting issues, the Microsoft Edge Extension system has incorporated the general concept of [Content Security Policy \(CSP\)][W3CContentSecurityPolicy].</span><span class="sxs-lookup"><span data-stu-id="87bc0-105">In order to mitigate a large class of potential cross-site scripting issues, the Microsoft Edge Extension system has incorporated the general concept of [Content Security Policy \(CSP\)][W3CContentSecurityPolicy].</span></span>  <span data-ttu-id="87bc0-106">This introduces some fairly strict policies that make Extensions more secure by default, and provides you with the ability to create and enforce rules governing the types of content that may be loaded and run by your Extensions and applications.</span><span class="sxs-lookup"><span data-stu-id="87bc0-106">This introduces some fairly strict policies that make Extensions more secure by default, and provides you with the ability to create and enforce rules governing the types of content that may be loaded and run by your Extensions and applications.</span></span>  

<span data-ttu-id="87bc0-107">In general, CSP works as a block/allowlisting mechanism for resources loaded or run by your Extensions.</span><span class="sxs-lookup"><span data-stu-id="87bc0-107">In general, CSP works as a block/allowlisting mechanism for resources loaded or run by your Extensions.</span></span>  <span data-ttu-id="87bc0-108">Defining a reasonable policy for your Extension enables you to carefully consider the resources that your Extension requires, and to ask the browser to ensure that those are the only resources your Extension has access to.</span><span class="sxs-lookup"><span data-stu-id="87bc0-108">Defining a reasonable policy for your Extension enables you to carefully consider the resources that your Extension requires, and to ask the browser to ensure that those are the only resources your Extension has access to.</span></span>  <span data-ttu-id="87bc0-109">These policies provide security over and above the host permissions your Extension requests; they are an additional layer of protection, not a replacement.</span><span class="sxs-lookup"><span data-stu-id="87bc0-109">These policies provide security over and above the host permissions your Extension requests; they are an additional layer of protection, not a replacement.</span></span>  

<span data-ttu-id="87bc0-110">On the web, such a policy is defined via an HTTP header or `meta` element.</span><span class="sxs-lookup"><span data-stu-id="87bc0-110">On the web, such a policy is defined via an HTTP header or `meta` element.</span></span>  <span data-ttu-id="87bc0-111">Inside the Microsoft Edge Extension system, neither is an appropriate mechanism.</span><span class="sxs-lookup"><span data-stu-id="87bc0-111">Inside the Microsoft Edge Extension system, neither is an appropriate mechanism.</span></span>  <span data-ttu-id="87bc0-112">Instead, an Extension policy is defined via the `manifest.json` file for the Extension as follows:</span><span class="sxs-lookup"><span data-stu-id="87bc0-112">Instead, an Extension policy is defined via the `manifest.json` file for the Extension as follows:</span></span>  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> <span data-ttu-id="87bc0-113">For full details regarding the CSP syntax, please take a look at the [Content Security Policy specification][W3CContentSecurityPolicy] , and the ["An Introduction to Content Security Policy"][HTML5RocksIntroductionContentSecurityPolicy] article on HTML5Rocks.</span><span class="sxs-lookup"><span data-stu-id="87bc0-113">For full details regarding the CSP syntax, please take a look at the [Content Security Policy specification][W3CContentSecurityPolicy] , and the ["An Introduction to Content Security Policy"][HTML5RocksIntroductionContentSecurityPolicy] article on HTML5Rocks.</span></span>  

## <span data-ttu-id="87bc0-114">Default Policy Restrictions</span><span class="sxs-lookup"><span data-stu-id="87bc0-114">Default Policy Restrictions</span></span>  

<span data-ttu-id="87bc0-115">Packages that do not define a `manifest_version` do not have a default content security policy.</span><span class="sxs-lookup"><span data-stu-id="87bc0-115">Packages that do not define a `manifest_version` do not have a default content security policy.</span></span>  <span data-ttu-id="87bc0-116">Those that select `manifest_version` 2, have a default content security policy of:</span><span class="sxs-lookup"><span data-stu-id="87bc0-116">Those that select `manifest_version` 2, have a default content security policy of:</span></span>  

```javascript
script-src 'self'; object-src 'self'
```  

<span data-ttu-id="87bc0-117">This policy adds security by limiting Extensions and applications in three ways:</span><span class="sxs-lookup"><span data-stu-id="87bc0-117">This policy adds security by limiting Extensions and applications in three ways:</span></span>  

**<span data-ttu-id="87bc0-118">Eval and related functions are disabled</span><span class="sxs-lookup"><span data-stu-id="87bc0-118">Eval and related functions are disabled</span></span>**  

<span data-ttu-id="87bc0-119">Code like the following does not work:</span><span class="sxs-lookup"><span data-stu-id="87bc0-119">Code like the following does not work:</span></span>  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

<span data-ttu-id="87bc0-120">Evaluating strings of JavaScript like this is a common XSS attack vector.</span><span class="sxs-lookup"><span data-stu-id="87bc0-120">Evaluating strings of JavaScript like this is a common XSS attack vector.</span></span>  <span data-ttu-id="87bc0-121">Instead, you should write code like:</span><span class="sxs-lookup"><span data-stu-id="87bc0-121">Instead, you should write code like:</span></span>

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**<span data-ttu-id="87bc0-122">Inline JavaScript are not run</span><span class="sxs-lookup"><span data-stu-id="87bc0-122">Inline JavaScript are not run</span></span>**  

<span data-ttu-id="87bc0-123">Inline JavaScript are not run.</span><span class="sxs-lookup"><span data-stu-id="87bc0-123">Inline JavaScript are not run.</span></span>  <span data-ttu-id="87bc0-124">This restriction bans both inline `<script>` blocks and inline event handlers, such as `<button onclick="...">`.</span><span class="sxs-lookup"><span data-stu-id="87bc0-124">This restriction bans both inline `<script>` blocks and inline event handlers, such as `<button onclick="...">`.</span></span>

<span data-ttu-id="87bc0-125">The first restriction wipes out a huge class of cross-site scripting attacks by making it impossible for you to accidentally run the script provided by a malicious third-party.</span><span class="sxs-lookup"><span data-stu-id="87bc0-125">The first restriction wipes out a huge class of cross-site scripting attacks by making it impossible for you to accidentally run the script provided by a malicious third-party.</span></span>  <span data-ttu-id="87bc0-126">It does, however, require you to write your code with a clean separation between content and behavior \(which you should of course do anyway, right?\).</span><span class="sxs-lookup"><span data-stu-id="87bc0-126">It does, however, require you to write your code with a clean separation between content and behavior \(which you should of course do anyway, right?\).</span></span>  <span data-ttu-id="87bc0-127">An example may make this clearer.</span><span class="sxs-lookup"><span data-stu-id="87bc0-127">An example may make this clearer.</span></span>  <span data-ttu-id="87bc0-128">You may try to write a Browser Action pop-up as a single `pop-up.html` containing:</span><span class="sxs-lookup"><span data-stu-id="87bc0-128">You may try to write a Browser Action pop-up as a single `pop-up.html` containing:</span></span>  

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

<span data-ttu-id="87bc0-129">Three things must change in order to make this work the way you expect it to:</span><span class="sxs-lookup"><span data-stu-id="87bc0-129">Three things must change in order to make this work the way you expect it to:</span></span>  

*   <span data-ttu-id="87bc0-130">The `clickHandler` definition must be moved into an external JavaScript file \(`popup.js` may be a good target).</span><span class="sxs-lookup"><span data-stu-id="87bc0-130">The `clickHandler` definition must be moved into an external JavaScript file \(`popup.js` may be a good target).</span></span>  
*   <span data-ttu-id="87bc0-131">The inline event handler definitions must be rewritten in terms of `addEventListener` and extracted into `popup.js`.</span><span class="sxs-lookup"><span data-stu-id="87bc0-131">The inline event handler definitions must be rewritten in terms of `addEventListener` and extracted into `popup.js`.</span></span>  
    <span data-ttu-id="87bc0-132">If you are currently starting your program using code like `<body onload="main();">`, consider replacing it by hooking into the `DOMContentLoaded` event of the document, or the `load` event of the window, depending on your requirements.</span><span class="sxs-lookup"><span data-stu-id="87bc0-132">If you are currently starting your program using code like `<body onload="main();">`, consider replacing it by hooking into the `DOMContentLoaded` event of the document, or the `load` event of the window, depending on your requirements.</span></span>  <span data-ttu-id="87bc0-133">Use the former, since it generally triggers more quickly.</span><span class="sxs-lookup"><span data-stu-id="87bc0-133">Use the former, since it generally triggers more quickly.</span></span>  

*   <span data-ttu-id="87bc0-134">The `setTimeout` call must be rewritten to avoid converting the string `"awesome(); totallyAwesome()"` into JavaScript for running.</span><span class="sxs-lookup"><span data-stu-id="87bc0-134">The `setTimeout` call must be rewritten to avoid converting the string `"awesome(); totallyAwesome()"` into JavaScript for running.</span></span>  
    <span data-ttu-id="87bc0-135">Those changes may look something like the following:</span><span class="sxs-lookup"><span data-stu-id="87bc0-135">Those changes may look something like the following:</span></span>  

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

**<span data-ttu-id="87bc0-136">Only local script and object resources are loaded</span><span class="sxs-lookup"><span data-stu-id="87bc0-136">Only local script and object resources are loaded</span></span>**  

<span data-ttu-id="87bc0-137">Script and object resources are only able to be loaded from the Extension package, not from the web at large.</span><span class="sxs-lookup"><span data-stu-id="87bc0-137">Script and object resources are only able to be loaded from the Extension package, not from the web at large.</span></span>  <span data-ttu-id="87bc0-138">This ensures that your Extension only runs the code you specifically approved, preventing an active network attacker from maliciously redirecting your request for a resource.</span><span class="sxs-lookup"><span data-stu-id="87bc0-138">This ensures that your Extension only runs the code you specifically approved, preventing an active network attacker from maliciously redirecting your request for a resource.</span></span>  

<span data-ttu-id="87bc0-139">Instead of writing code that depends on jQuery \(or any other library\) loading from an external CDN, consider including the specific version of jQuery in your Extension package.</span><span class="sxs-lookup"><span data-stu-id="87bc0-139">Instead of writing code that depends on jQuery \(or any other library\) loading from an external CDN, consider including the specific version of jQuery in your Extension package.</span></span>  <span data-ttu-id="87bc0-140">That is, instead of:</span><span class="sxs-lookup"><span data-stu-id="87bc0-140">That is, instead of:</span></span>  

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

<span data-ttu-id="87bc0-141">Download the file, include it in your package, and write:</span><span class="sxs-lookup"><span data-stu-id="87bc0-141">Download the file, include it in your package, and write:</span></span>  

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

## <span data-ttu-id="87bc0-142">Relaxing the default policy</span><span class="sxs-lookup"><span data-stu-id="87bc0-142">Relaxing the default policy</span></span>  

**<span data-ttu-id="87bc0-143">Inline Script</span><span class="sxs-lookup"><span data-stu-id="87bc0-143">Inline Script</span></span>**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

<span data-ttu-id="87bc0-144">Inline scripts are able to be allowed by specifying the base64-encoded hash of the source code in the policy.</span><span class="sxs-lookup"><span data-stu-id="87bc0-144">Inline scripts are able to be allowed by specifying the base64-encoded hash of the source code in the policy.</span></span>  <span data-ttu-id="87bc0-145">This hash must be prefixed by the used hash algorithm \(sha256, sha384 or sha512\).</span><span class="sxs-lookup"><span data-stu-id="87bc0-145">This hash must be prefixed by the used hash algorithm \(sha256, sha384 or sha512\).</span></span>  <span data-ttu-id="87bc0-146">See [Hash usage for \<script\> elements][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage] for an example.</span><span class="sxs-lookup"><span data-stu-id="87bc0-146">See [Hash usage for \<script\> elements][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage] for an example.</span></span>  

**<span data-ttu-id="87bc0-147">Remote Script</span><span class="sxs-lookup"><span data-stu-id="87bc0-147">Remote Script</span></span>**  

<span data-ttu-id="87bc0-148">If you require some external JavaScript or object resources, you may relax the policy to a limited extent by allowlisting secure origins from which scripts should be accepted.</span><span class="sxs-lookup"><span data-stu-id="87bc0-148">If you require some external JavaScript or object resources, you may relax the policy to a limited extent by allowlisting secure origins from which scripts should be accepted.</span></span>  <span data-ttu-id="87bc0-149">Verify that runtime resources loaded with with elevated permissions of an Extension are exactly the resources you expect, and are not replaced by an active network attacker.</span><span class="sxs-lookup"><span data-stu-id="87bc0-149">Verify that runtime resources loaded with with elevated permissions of an Extension are exactly the resources you expect, and are not replaced by an active network attacker.</span></span>  <span data-ttu-id="87bc0-150">As [man-in-the-middle attacks][WikiManMiddleAttacks] are both trivial and undetectable over HTTP, those origins are not accepted.</span><span class="sxs-lookup"><span data-stu-id="87bc0-150">As [man-in-the-middle attacks][WikiManMiddleAttacks] are both trivial and undetectable over HTTP, those origins are not accepted.</span></span>  

<span data-ttu-id="87bc0-151">Currently, developers are able to allowlist origins with the following schemes: `blob`, `filesystem`, `https`, and `extension`.</span><span class="sxs-lookup"><span data-stu-id="87bc0-151">Currently, developers are able to allowlist origins with the following schemes: `blob`, `filesystem`, `https`, and `extension`.</span></span>  <span data-ttu-id="87bc0-152">The host part of the origin must explicitly be specified for the `https` and `extension` schemes.</span><span class="sxs-lookup"><span data-stu-id="87bc0-152">The host part of the origin must explicitly be specified for the `https` and `extension` schemes.</span></span>  <span data-ttu-id="87bc0-153">Generic wildcards such as https:, `https://*` and `https://*.com` are not allowed; subdomain wildcards such as `https://*.example.com` are allowed.</span><span class="sxs-lookup"><span data-stu-id="87bc0-153">Generic wildcards such as https:, `https://*` and `https://*.com` are not allowed; subdomain wildcards such as `https://*.example.com` are allowed.</span></span>  <span data-ttu-id="87bc0-154">Domains in the [Public Suffix list][PublicSuffixList] are also viewed as generic top-level domains.</span><span class="sxs-lookup"><span data-stu-id="87bc0-154">Domains in the [Public Suffix list][PublicSuffixList] are also viewed as generic top-level domains.</span></span>  <span data-ttu-id="87bc0-155">To load a resource from these domains, the subdomain must explicitly be listed.</span><span class="sxs-lookup"><span data-stu-id="87bc0-155">To load a resource from these domains, the subdomain must explicitly be listed.</span></span>  <span data-ttu-id="87bc0-156">For example, `https://*.cloudfront.net` is not valid, but `https://XXXX.cloudfront.net` and `https://*.XXXX.cloudfront.net` are able to be allowlisted.</span><span class="sxs-lookup"><span data-stu-id="87bc0-156">For example, `https://*.cloudfront.net` is not valid, but `https://XXXX.cloudfront.net` and `https://*.XXXX.cloudfront.net` are able to be allowlisted.</span></span>  

<span data-ttu-id="87bc0-157">For development ease, resources loaded over HTTP from servers on your local machine are able to be allowlisted.</span><span class="sxs-lookup"><span data-stu-id="87bc0-157">For development ease, resources loaded over HTTP from servers on your local machine are able to be allowlisted.</span></span>  <span data-ttu-id="87bc0-158">You may allowlist script and object sources on any port of either `http://127.0.0.1` or `http://localhost`.</span><span class="sxs-lookup"><span data-stu-id="87bc0-158">You may allowlist script and object sources on any port of either `http://127.0.0.1` or `http://localhost`.</span></span>  

> [!NOTE]
> <span data-ttu-id="87bc0-159">The restriction against resources loaded over HTTP applies only to those resources which are directly run.</span><span class="sxs-lookup"><span data-stu-id="87bc0-159">The restriction against resources loaded over HTTP applies only to those resources which are directly run.</span></span>  <span data-ttu-id="87bc0-160">You are still free, for example, to make XMLHTTPRequest connections to any origin you like; the default policy does not restrict `connect-src` or any of the other CSP directives in any way.</span><span class="sxs-lookup"><span data-stu-id="87bc0-160">You are still free, for example, to make XMLHTTPRequest connections to any origin you like; the default policy does not restrict `connect-src` or any of the other CSP directives in any way.</span></span>  

<span data-ttu-id="87bc0-161">A relaxed policy definition which allows script resources to be loaded from example.com over HTTPS may look like:</span><span class="sxs-lookup"><span data-stu-id="87bc0-161">A relaxed policy definition which allows script resources to be loaded from example.com over HTTPS may look like:</span></span>  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> <span data-ttu-id="87bc0-162">Both `script-src` and `object-src` are defined by the policy.</span><span class="sxs-lookup"><span data-stu-id="87bc0-162">Both `script-src` and `object-src` are defined by the policy.</span></span>  <span data-ttu-id="87bc0-163">Microsoft Edge does not accept a policy that does not limit each of these values to \(at least\) '`self`'.</span><span class="sxs-lookup"><span data-stu-id="87bc0-163">Microsoft Edge does not accept a policy that does not limit each of these values to \(at least\) '`self`'.</span></span>  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**<span data-ttu-id="87bc0-164">Evaluated JavaScript</span><span class="sxs-lookup"><span data-stu-id="87bc0-164">Evaluated JavaScript</span></span>**  

<span data-ttu-id="87bc0-165">The policy against `eval()` and related functions like `setTimeout(String)`, `setInterval(String)`, and `new Function(String)` are able to be relaxed by adding `unsafe-eval` to your policy:</span><span class="sxs-lookup"><span data-stu-id="87bc0-165">The policy against `eval()` and related functions like `setTimeout(String)`, `setInterval(String)`, and `new Function(String)` are able to be relaxed by adding `unsafe-eval` to your policy:</span></span>  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

<span data-ttu-id="87bc0-166">However, we strongly recommend against doing this.</span><span class="sxs-lookup"><span data-stu-id="87bc0-166">However, we strongly recommend against doing this.</span></span>  <span data-ttu-id="87bc0-167">These functions are notorious XSS attack vectors.</span><span class="sxs-lookup"><span data-stu-id="87bc0-167">These functions are notorious XSS attack vectors.</span></span>  

## <span data-ttu-id="87bc0-168">Tightening the default policy</span><span class="sxs-lookup"><span data-stu-id="87bc0-168">Tightening the default policy</span></span>  

<span data-ttu-id="87bc0-169">You may, of course, tighten this policy to whatever extent your Extension allows in order to increase security at the expense of convenience.</span><span class="sxs-lookup"><span data-stu-id="87bc0-169">You may, of course, tighten this policy to whatever extent your Extension allows in order to increase security at the expense of convenience.</span></span>  <span data-ttu-id="87bc0-170">To specify that your Extension are able to only load resources of any type \(images, and so on\) from the associated Extension package, for example, a policy of `default-src 'self'` may be appropriate.</span><span class="sxs-lookup"><span data-stu-id="87bc0-170">To specify that your Extension are able to only load resources of any type \(images, and so on\) from the associated Extension package, for example, a policy of `default-src 'self'` may be appropriate.</span></span>  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## <span data-ttu-id="87bc0-171">Content Scripts</span><span class="sxs-lookup"><span data-stu-id="87bc0-171">Content Scripts</span></span>  

<span data-ttu-id="87bc0-172">The policy being discussing applies to the background pages and event pages of the Extension.</span><span class="sxs-lookup"><span data-stu-id="87bc0-172">The policy being discussing applies to the background pages and event pages of the Extension.</span></span>  <span data-ttu-id="87bc0-173">How the content scripts apply to the content scripts of the Extension is more complicated.</span><span class="sxs-lookup"><span data-stu-id="87bc0-173">How the content scripts apply to the content scripts of the Extension is more complicated.</span></span>  

<span data-ttu-id="87bc0-174">Content scripts are generally not subject to the CSP of the Extension.</span><span class="sxs-lookup"><span data-stu-id="87bc0-174">Content scripts are generally not subject to the CSP of the Extension.</span></span>  <span data-ttu-id="87bc0-175">Since content scripts are not HTML, the main impact of this is that they may use `eval` even if the CSP of the Extension does not specify `unsafe-eval`, although this is not recommended.</span><span class="sxs-lookup"><span data-stu-id="87bc0-175">Since content scripts are not HTML, the main impact of this is that they may use `eval` even if the CSP of the Extension does not specify `unsafe-eval`, although this is not recommended.</span></span>  <span data-ttu-id="87bc0-176">Additionally, the CSP of the page does not apply to content scripts.</span><span class="sxs-lookup"><span data-stu-id="87bc0-176">Additionally, the CSP of the page does not apply to content scripts.</span></span>  <span data-ttu-id="87bc0-177">More complicated are `<script>` tags that content scripts create and put into the DOM of the page they are running on.</span><span class="sxs-lookup"><span data-stu-id="87bc0-177">More complicated are `<script>` tags that content scripts create and put into the DOM of the page they are running on.</span></span>  <span data-ttu-id="87bc0-178">These are referenced as DOM injected scripts going forward.</span><span class="sxs-lookup"><span data-stu-id="87bc0-178">These are referenced as DOM injected scripts going forward.</span></span>  

<span data-ttu-id="87bc0-179">DOM injected scripts that run immediately upon injection into the page runs as you may expect.</span><span class="sxs-lookup"><span data-stu-id="87bc0-179">DOM injected scripts that run immediately upon injection into the page runs as you may expect.</span></span>  <span data-ttu-id="87bc0-180">Imagine a content script with the following code as a simple example:</span><span class="sxs-lookup"><span data-stu-id="87bc0-180">Imagine a content script with the following code as a simple example:</span></span>  

```javascript
document.write("<script>alert(1);</script>");
 ```  

<span data-ttu-id="87bc0-181">This content script causes an `alert` immediately upon the `document.write()`.</span><span class="sxs-lookup"><span data-stu-id="87bc0-181">This content script causes an `alert` immediately upon the `document.write()`.</span></span>  <span data-ttu-id="87bc0-182">Note that this runs regardless of the policy a page may specify.</span><span class="sxs-lookup"><span data-stu-id="87bc0-182">Note that this runs regardless of the policy a page may specify.</span></span>
<span data-ttu-id="87bc0-183">However, the behavior becomes more complicated both inside that DOM injected script and for any script that does not immediately run upon injection.</span><span class="sxs-lookup"><span data-stu-id="87bc0-183">However, the behavior becomes more complicated both inside that DOM injected script and for any script that does not immediately run upon injection.</span></span>  <span data-ttu-id="87bc0-184">Imagine that your Extension is running on a page that provides an associated CSP that specifies `script-src 'self'`.</span><span class="sxs-lookup"><span data-stu-id="87bc0-184">Imagine that your Extension is running on a page that provides an associated CSP that specifies `script-src 'self'`.</span></span>  <span data-ttu-id="87bc0-185">Now imagine the content script runs the following code:</span><span class="sxs-lookup"><span data-stu-id="87bc0-185">Now imagine the content script runs the following code:</span></span>  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

<span data-ttu-id="87bc0-186">If a user clicks on that button, the `onclick` script does not run.</span><span class="sxs-lookup"><span data-stu-id="87bc0-186">If a user clicks on that button, the `onclick` script does not run.</span></span>  <span data-ttu-id="87bc0-187">This is because the script did not immediately run and code is not interpreted until the click event occurs is not considered part of the content script, so the CSP of the page \(not of the Extension\) restricts the behavior.</span><span class="sxs-lookup"><span data-stu-id="87bc0-187">This is because the script did not immediately run and code is not interpreted until the click event occurs is not considered part of the content script, so the CSP of the page \(not of the Extension\) restricts the behavior.</span></span>  <span data-ttu-id="87bc0-188">And since that CSP does not specify `unsafe-inline`, the inline event handler is blocked.</span><span class="sxs-lookup"><span data-stu-id="87bc0-188">And since that CSP does not specify `unsafe-inline`, the inline event handler is blocked.</span></span>  
<span data-ttu-id="87bc0-189">The correct way to implement the desired behavior in this case may be to add the `onclick` handler as a function from the content script as follows:</span><span class="sxs-lookup"><span data-stu-id="87bc0-189">The correct way to implement the desired behavior in this case may be to add the `onclick` handler as a function from the content script as follows:</span></span>  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

<span data-ttu-id="87bc0-190">Another similar issue arises if the content script runs the following:</span><span class="sxs-lookup"><span data-stu-id="87bc0-190">Another similar issue arises if the content script runs the following:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="87bc0-191">In this case, the script runs and the alert displays.</span><span class="sxs-lookup"><span data-stu-id="87bc0-191">In this case, the script runs and the alert displays.</span></span>  <span data-ttu-id="87bc0-192">However, take this case:</span><span class="sxs-lookup"><span data-stu-id="87bc0-192">However, take this case:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="87bc0-193">While the initial script runs, the call to `eval` is blocked.</span><span class="sxs-lookup"><span data-stu-id="87bc0-193">While the initial script runs, the call to `eval` is blocked.</span></span>  <span data-ttu-id="87bc0-194">That is, while the initial script runtime is allowed, the behavior within the script is regulated by the CSP of the page.</span><span class="sxs-lookup"><span data-stu-id="87bc0-194">That is, while the initial script runtime is allowed, the behavior within the script is regulated by the CSP of the page.</span></span>  
<span data-ttu-id="87bc0-195">Thus, depending on how you write DOM injected scripts in your Extension, changes to the CSP of the page may affect the behavior of your Extension.</span><span class="sxs-lookup"><span data-stu-id="87bc0-195">Thus, depending on how you write DOM injected scripts in your Extension, changes to the CSP of the page may affect the behavior of your Extension.</span></span>  <span data-ttu-id="87bc0-196">Since content scripts are not affected by the CSP of the page, this a great reason to put as much behavior as possible of your Extension into the content script rather than DOM injected scripts.</span><span class="sxs-lookup"><span data-stu-id="87bc0-196">Since content scripts are not affected by the CSP of the page, this a great reason to put as much behavior as possible of your Extension into the content script rather than DOM injected scripts.</span></span>  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "An Introduction to Content Security Policy - HTML5 Rocks"  
[PublicSuffixList]: https://publicsuffix.org/list "VIEW THE PUBLIC SUFFIX LIST"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "Hash usage for \<script\> elements - Content Security Policy Level 2"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "Content Security Policy Level 3"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "Man-in-the-middle attack - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="87bc0-202">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="87bc0-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="87bc0-203">The original page is found [here](https://developer.chrome.com/extensions/contentSecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="87bc0-203">The original page is found [here](https://developer.chrome.com/extensions/contentSecurityPolicy).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="87bc0-205">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="87bc0-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
