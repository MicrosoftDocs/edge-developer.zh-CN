---
description: Enterprise policy documentation for Edge (Chromium) Extensions.
title: Match Patterns
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, extensions development, browser extensions, addons, partner center, developer
ms.openlocfilehash: 59427769a010ca774833a809d3025e7594634202
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015658"
---
# <span data-ttu-id="ae725-104">Match Patterns</span><span class="sxs-lookup"><span data-stu-id="ae725-104">Match Patterns</span></span>

<span data-ttu-id="ae725-105">Host permissions and content script matching are based on a set of URLs defined by match patterns.</span><span class="sxs-lookup"><span data-stu-id="ae725-105">Host permissions and content script matching are based on a set of URLs defined by match patterns.</span></span>  <span data-ttu-id="ae725-106">A match pattern is essentially a URL that begins with a permitted scheme (`http`, `https`, `file`, or `ftp`, and that can contain '`*`' characters.</span><span class="sxs-lookup"><span data-stu-id="ae725-106">A match pattern is essentially a URL that begins with a permitted scheme (`http`, `https`, `file`, or `ftp`, and that can contain '`*`' characters.</span></span>  <span data-ttu-id="ae725-107">The special pattern `<all_urls>` matches any URL that starts with a permitted scheme.</span><span class="sxs-lookup"><span data-stu-id="ae725-107">The special pattern `<all_urls>` matches any URL that starts with a permitted scheme.</span></span>  <span data-ttu-id="ae725-108">Each match pattern has 3 parts:</span><span class="sxs-lookup"><span data-stu-id="ae725-108">Each match pattern has 3 parts:</span></span>  

*   <span data-ttu-id="ae725-109">_scheme_ — for example, `http` or `file` or</span><span class="sxs-lookup"><span data-stu-id="ae725-109">_scheme_ — for example, `http` or `file` or</span></span> `*`  

> [!NOTE]
> <span data-ttu-id="ae725-110">Access to `file` URLs is not automatic.</span><span class="sxs-lookup"><span data-stu-id="ae725-110">Access to `file` URLs is not automatic.</span></span>  <span data-ttu-id="ae725-111">The user must visit the Extensions management page and opt in to `file` access for each Extension that requests it.</span><span class="sxs-lookup"><span data-stu-id="ae725-111">The user must visit the Extensions management page and opt in to `file` access for each Extension that requests it.</span></span>  

*   `_host_` <span data-ttu-id="ae725-112">— for example, `www.google.com` or `*.google.com` or `*`; if the scheme is file, there is no host part.</span><span class="sxs-lookup"><span data-stu-id="ae725-112">— for example, `www.google.com` or `*.google.com` or `*`; if the scheme is file, there is no host part.</span></span>  
*   `_path_` <span data-ttu-id="ae725-113">— for example, `/*`, `/foo*`, or `/foo/bar`.</span><span class="sxs-lookup"><span data-stu-id="ae725-113">— for example, `/*`, `/foo*`, or `/foo/bar`.</span></span>  <span data-ttu-id="ae725-114">The path must be present in a host permission, but is always treated as `/*`.</span><span class="sxs-lookup"><span data-stu-id="ae725-114">The path must be present in a host permission, but is always treated as `/*`.</span></span>  

<span data-ttu-id="ae725-115">The basic syntax:</span><span class="sxs-lookup"><span data-stu-id="ae725-115">The basic syntax:</span></span>  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

<span data-ttu-id="ae725-116">The meaning of `*` depends on whether it is in the scheme, host, or path part.</span><span class="sxs-lookup"><span data-stu-id="ae725-116">The meaning of `*` depends on whether it is in the scheme, host, or path part.</span></span>  <span data-ttu-id="ae725-117">If the scheme is `*`, then it matches either `http` or `https`, and not `file`, or `ftp`.</span><span class="sxs-lookup"><span data-stu-id="ae725-117">If the scheme is `*`, then it matches either `http` or `https`, and not `file`, or `ftp`.</span></span>  <span data-ttu-id="ae725-118">If the host is just `*`, then it matches any host.</span><span class="sxs-lookup"><span data-stu-id="ae725-118">If the host is just `*`, then it matches any host.</span></span> <span data-ttu-id="ae725-119">If the host is `*.hostname`, then it matches the specified host or any of the subdomains.</span><span class="sxs-lookup"><span data-stu-id="ae725-119">If the host is `*.hostname`, then it matches the specified host or any of the subdomains.</span></span>  <span data-ttu-id="ae725-120">In the path section, each `*` matches 0 or more characters.</span><span class="sxs-lookup"><span data-stu-id="ae725-120">In the path section, each `*` matches 0 or more characters.</span></span>  <span data-ttu-id="ae725-121">The following table shows some valid patterns.</span><span class="sxs-lookup"><span data-stu-id="ae725-121">The following table shows some valid patterns.</span></span>  

| <span data-ttu-id="ae725-122">Pattern</span><span class="sxs-lookup"><span data-stu-id="ae725-122">Pattern</span></span> | <span data-ttu-id="ae725-123">What it does</span><span class="sxs-lookup"><span data-stu-id="ae725-123">What it does</span></span> | <span data-ttu-id="ae725-124">Examples of matching URLs</span><span class="sxs-lookup"><span data-stu-id="ae725-124">Examples of matching URLs</span></span> |  
|:--- |:--- |:--- |  
| `http://*/*` | <span data-ttu-id="ae725-125">Matches any URL that uses the http scheme</span><span class="sxs-lookup"><span data-stu-id="ae725-125">Matches any URL that uses the http scheme</span></span> | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | <span data-ttu-id="ae725-126">Matches any URL that uses the http scheme, on any host, as long as the path starts with</span><span class="sxs-lookup"><span data-stu-id="ae725-126">Matches any URL that uses the http scheme, on any host, as long as the path starts with</span></span> `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | <span data-ttu-id="ae725-127">Matches any URL that uses the https scheme, is on a `google.com` host \(such as `www.google.com`, `docs.google.com`, or `google.com`\), as long as the path starts with `/foo` and ends with</span><span class="sxs-lookup"><span data-stu-id="ae725-127">Matches any URL that uses the https scheme, is on a `google.com` host \(such as `www.google.com`, `docs.google.com`, or `google.com`\), as long as the path starts with `/foo` and ends with</span></span> `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | <span data-ttu-id="ae725-128">Matches the specified URL</span><span class="sxs-lookup"><span data-stu-id="ae725-128">Matches the specified URL</span></span> | `http://example.org/foo/bar.html` |  
|`file:///foo*` | <span data-ttu-id="ae725-129">Matches any local file whose path starts with</span><span class="sxs-lookup"><span data-stu-id="ae725-129">Matches any local file whose path starts with</span></span> `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | <span data-ttu-id="ae725-130">Matches any URL that uses the `http` scheme and is on the host</span><span class="sxs-lookup"><span data-stu-id="ae725-130">Matches any URL that uses the `http` scheme and is on the host</span></span> `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | <span data-ttu-id="ae725-131">Matches any URL that starts with `http://mail.google.com` or `https://mail.google.com`.</span><span class="sxs-lookup"><span data-stu-id="ae725-131">Matches any URL that starts with `http://mail.google.com` or `https://mail.google.com`.</span></span> | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | <span data-ttu-id="ae725-132">Matches any URL that uses a permitted scheme.</span><span class="sxs-lookup"><span data-stu-id="ae725-132">Matches any URL that uses a permitted scheme.</span></span> <span data-ttu-id="ae725-133">\(See the beginning of this section for the list of permitted schemes.\)</span><span class="sxs-lookup"><span data-stu-id="ae725-133">\(See the beginning of this section for the list of permitted schemes.\)</span></span> | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

<span data-ttu-id="ae725-134">Here are some examples of `_invalid_` pattern matches:</span><span class="sxs-lookup"><span data-stu-id="ae725-134">Here are some examples of `_invalid_` pattern matches:</span></span>

| <span data-ttu-id="ae725-135">Bad pattern</span><span class="sxs-lookup"><span data-stu-id="ae725-135">Bad pattern</span></span> | <span data-ttu-id="ae725-136">Why it is bad</span><span class="sxs-lookup"><span data-stu-id="ae725-136">Why it is bad</span></span> |  
|:--- |:--- |  
| `http://www.foo.com` | <span data-ttu-id="ae725-137">No</span><span class="sxs-lookup"><span data-stu-id="ae725-137">No</span></span> `_path_` |  
| `http://*foo/bar` | <span data-ttu-id="ae725-138">'`*`' in the host can be followed only by a '`.`' or '`/`'</span><span class="sxs-lookup"><span data-stu-id="ae725-138">'`*`' in the host can be followed only by a '`.`' or '`/`'</span></span> |  
| `http://foo.*.bar/baz` | <span data-ttu-id="ae725-139">If '`*`' is in the `_host_`, it must be the first character</span><span class="sxs-lookup"><span data-stu-id="ae725-139">If '`*`' is in the `_host_`, it must be the first character</span></span> |  
| `http:/bar` | <span data-ttu-id="ae725-140">Missing `_scheme_` separator \('`/`' should be "`//`"\)</span><span class="sxs-lookup"><span data-stu-id="ae725-140">Missing `_scheme_` separator \('`/`' should be "`//`"\)</span></span> |  
| `foo://*` | <span data-ttu-id="ae725-141">Invalid</span><span class="sxs-lookup"><span data-stu-id="ae725-141">Invalid</span></span> `_scheme_` |  

<span data-ttu-id="ae725-142">Some schemes are not supported in all contexts.</span><span class="sxs-lookup"><span data-stu-id="ae725-142">Some schemes are not supported in all contexts.</span></span>

> [!NOTE]
> <span data-ttu-id="ae725-143">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ae725-143">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ae725-144">The original page is found [here](https://developer.chrome.com/extensions/match_patterns/).</span><span class="sxs-lookup"><span data-stu-id="ae725-144">The original page is found [here](https://developer.chrome.com/extensions/match_patterns/).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ae725-146">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ae725-146">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
