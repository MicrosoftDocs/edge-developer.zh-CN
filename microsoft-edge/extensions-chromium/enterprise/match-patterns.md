---
description: Edge 和 Chromium (扩展) 策略文档。
title: 匹配模式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: fcb87b62cac063c7663f575fa3d992b187408c28
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461246"
---
<!-- Copyright A. W. Fuchs

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="match-patterns"></a><span data-ttu-id="0761b-104">匹配模式</span><span class="sxs-lookup"><span data-stu-id="0761b-104">Match Patterns</span></span>

<span data-ttu-id="0761b-105">主机权限和内容脚本匹配基于匹配模式定义的一组 URL。</span><span class="sxs-lookup"><span data-stu-id="0761b-105">Host permissions and content script matching are based on a set of URLs defined by match patterns.</span></span>  <span data-ttu-id="0761b-106">匹配模式实质上是一个 URL，它以允许的方案开头， (、、或 `http` ，并且可以包含 ' ' `https` `file` `ftp` `*` 字符。</span><span class="sxs-lookup"><span data-stu-id="0761b-106">A match pattern is essentially a URL that begins with a permitted scheme (`http`, `https`, `file`, or `ftp`, and that can contain '`*`' characters.</span></span>  <span data-ttu-id="0761b-107">特殊模式 `<all_urls>` 与以允许方案开头的任何 URL 匹配。</span><span class="sxs-lookup"><span data-stu-id="0761b-107">The special pattern `<all_urls>` matches any URL that starts with a permitted scheme.</span></span>  <span data-ttu-id="0761b-108">每个匹配模式有 3 个部分：</span><span class="sxs-lookup"><span data-stu-id="0761b-108">Each match pattern has 3 parts:</span></span>  

*   <span data-ttu-id="0761b-109">_方案_ — 例如 `http` ， `file` 或 或</span><span class="sxs-lookup"><span data-stu-id="0761b-109">_scheme_ — for example, `http` or `file` or</span></span> `*`  

> [!NOTE]
> <span data-ttu-id="0761b-110">对 `file` URL 的访问不是自动的。</span><span class="sxs-lookup"><span data-stu-id="0761b-110">Access to `file` URLs is not automatic.</span></span>  <span data-ttu-id="0761b-111">用户必须访问"扩展管理"页，并针对请求它的 `file` 每个扩展选择访问。</span><span class="sxs-lookup"><span data-stu-id="0761b-111">The user must visit the Extensions management page and opt in to `file` access for each Extension that requests it.</span></span>  

*   `_host_` <span data-ttu-id="0761b-112">— 例如， `www.google.com` `*.google.com` 或 `*` ;如果方案是文件，则没有主机部件。</span><span class="sxs-lookup"><span data-stu-id="0761b-112">— for example, `www.google.com` or `*.google.com` or `*`; if the scheme is file, there is no host part.</span></span>  
*   `_path_` <span data-ttu-id="0761b-113">例如， `/*` 、 `/foo*` 或 `/foo/bar` 。</span><span class="sxs-lookup"><span data-stu-id="0761b-113">— for example, `/*`, `/foo*`, or `/foo/bar`.</span></span>  <span data-ttu-id="0761b-114">路径必须存在于主机权限中，但始终被视为 `/*` 。</span><span class="sxs-lookup"><span data-stu-id="0761b-114">The path must be present in a host permission, but is always treated as `/*`.</span></span>  

<span data-ttu-id="0761b-115">基本语法：</span><span class="sxs-lookup"><span data-stu-id="0761b-115">The basic syntax:</span></span>  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

<span data-ttu-id="0761b-116">的含义 `*` 取决于它是位于方案、主机还是路径部分。</span><span class="sxs-lookup"><span data-stu-id="0761b-116">The meaning of `*` depends on whether it is in the scheme, host, or path part.</span></span>  <span data-ttu-id="0761b-117">如果方案为 `*` ，则它匹配 `http` 或 `https` ，而不是 `file` 或 `ftp` 。</span><span class="sxs-lookup"><span data-stu-id="0761b-117">If the scheme is `*`, then it matches either `http` or `https`, and not `file`, or `ftp`.</span></span>  <span data-ttu-id="0761b-118">如果主机只是 `*` ，它将匹配任何主机。</span><span class="sxs-lookup"><span data-stu-id="0761b-118">If the host is just `*`, then it matches any host.</span></span> <span data-ttu-id="0761b-119">如果主机为 `*.hostname` ，则其与指定的主机或任何子域匹配。</span><span class="sxs-lookup"><span data-stu-id="0761b-119">If the host is `*.hostname`, then it matches the specified host or any of the subdomains.</span></span>  <span data-ttu-id="0761b-120">在路径部分中，每个 `*` 匹配都匹配 0 个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="0761b-120">In the path section, each `*` matches 0 or more characters.</span></span>  <span data-ttu-id="0761b-121">下表显示了一些有效的模式。</span><span class="sxs-lookup"><span data-stu-id="0761b-121">The following table shows some valid patterns.</span></span>  

| <span data-ttu-id="0761b-122">模式</span><span class="sxs-lookup"><span data-stu-id="0761b-122">Pattern</span></span> | <span data-ttu-id="0761b-123">它有什么功能</span><span class="sxs-lookup"><span data-stu-id="0761b-123">What it does</span></span> | <span data-ttu-id="0761b-124">匹配 URL 的示例</span><span class="sxs-lookup"><span data-stu-id="0761b-124">Examples of matching URLs</span></span> |  
|:--- |:--- |:--- |  
| `http://*/*` | <span data-ttu-id="0761b-125">匹配使用 http 方案的任何 URL</span><span class="sxs-lookup"><span data-stu-id="0761b-125">Matches any URL that uses the http scheme</span></span> | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | <span data-ttu-id="0761b-126">匹配在任何主机上使用 http 方案的任何 URL，只要路径以</span><span class="sxs-lookup"><span data-stu-id="0761b-126">Matches any URL that uses the http scheme, on any host, as long as the path starts with</span></span> `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | <span data-ttu-id="0761b-127">匹配使用 https 方案的任何 URL，位于主机 \(如 、 或 `google.com` `www.google.com` `docs.google.com` `google.com` \) 上，只要路径以 开头和 `/foo` 结尾</span><span class="sxs-lookup"><span data-stu-id="0761b-127">Matches any URL that uses the https scheme, is on a `google.com` host \(such as `www.google.com`, `docs.google.com`, or `google.com`\), as long as the path starts with `/foo` and ends with</span></span> `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | <span data-ttu-id="0761b-128">匹配指定的 URL</span><span class="sxs-lookup"><span data-stu-id="0761b-128">Matches the specified URL</span></span> | `http://example.org/foo/bar.html` |  
|`file:///foo*` | <span data-ttu-id="0761b-129">匹配其路径以 开头的任何本地文件</span><span class="sxs-lookup"><span data-stu-id="0761b-129">Matches any local file whose path starts with</span></span> `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | <span data-ttu-id="0761b-130">匹配使用方案且位于 `http` 主机上的任何 URL</span><span class="sxs-lookup"><span data-stu-id="0761b-130">Matches any URL that uses the `http` scheme and is on the host</span></span> `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | <span data-ttu-id="0761b-131">匹配以 或 开头的任何 `http://mail.google.com` `https://mail.google.com` URL。</span><span class="sxs-lookup"><span data-stu-id="0761b-131">Matches any URL that starts with `http://mail.google.com` or `https://mail.google.com`.</span></span> | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | <span data-ttu-id="0761b-132">匹配使用允许方案的任何 URL。</span><span class="sxs-lookup"><span data-stu-id="0761b-132">Matches any URL that uses a permitted scheme.</span></span> <span data-ttu-id="0761b-133">\(请参阅本部分的开头，查看允许的方案列表。\) </span><span class="sxs-lookup"><span data-stu-id="0761b-133">\(See the beginning of this section for the list of permitted schemes.\)</span></span> | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

<span data-ttu-id="0761b-134">下面是模式匹配的 `_invalid_` 一些示例：</span><span class="sxs-lookup"><span data-stu-id="0761b-134">Here are some examples of `_invalid_` pattern matches:</span></span>

| <span data-ttu-id="0761b-135">错误模式</span><span class="sxs-lookup"><span data-stu-id="0761b-135">Bad pattern</span></span> | <span data-ttu-id="0761b-136">错误的原因</span><span class="sxs-lookup"><span data-stu-id="0761b-136">Why it is bad</span></span> |  
|:--- |:--- |  
| `http://www.foo.com` | <span data-ttu-id="0761b-137">否</span><span class="sxs-lookup"><span data-stu-id="0761b-137">No</span></span> `_path_` |  
| `http://*foo/bar` | <span data-ttu-id="0761b-138">' `*` ' in the host can be followed only by a ' ' or ' `.` `/` '</span><span class="sxs-lookup"><span data-stu-id="0761b-138">'`*`' in the host can be followed only by a '`.`' or '`/`'</span></span> |  
| `http://foo.*.bar/baz` | <span data-ttu-id="0761b-139">如果 ' `*` ' 位于 `_host_` 中，则它必须是第一个字符</span><span class="sxs-lookup"><span data-stu-id="0761b-139">If '`*`' is in the `_host_`, it must be the first character</span></span> |  
| `http:/bar` | <span data-ttu-id="0761b-140">缺少 `_scheme_` 分隔符 \(' `/` ' 应为 `//` "\) </span><span class="sxs-lookup"><span data-stu-id="0761b-140">Missing `_scheme_` separator \('`/`' should be "`//`"\)</span></span> |  
| `foo://*` | <span data-ttu-id="0761b-141">无效</span><span class="sxs-lookup"><span data-stu-id="0761b-141">Invalid</span></span> `_scheme_` |  

<span data-ttu-id="0761b-142">某些方案并非在所有上下文中都受支持。</span><span class="sxs-lookup"><span data-stu-id="0761b-142">Some schemes are not supported in all contexts.</span></span>

> [!NOTE]
> <span data-ttu-id="0761b-143">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0761b-143">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0761b-144">原始页面位于 [此处](https://developer.chrome.com/extensions/match_patterns)。</span><span class="sxs-lookup"><span data-stu-id="0761b-144">The original page is found [here](https://developer.chrome.com/extensions/match_patterns).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0761b-146">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0761b-146">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
