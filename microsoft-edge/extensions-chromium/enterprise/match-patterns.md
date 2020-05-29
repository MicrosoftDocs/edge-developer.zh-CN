---
description: 适用于 Edge （Chromium）扩展的企业策略文档。
title: 匹配模式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 16f54fcdc127822e89e050c367a681d886b0c8d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563378"
---
# <span data-ttu-id="8a5f1-104">匹配模式</span><span class="sxs-lookup"><span data-stu-id="8a5f1-104">Match Patterns</span></span>

<span data-ttu-id="8a5f1-105">主机权限和内容脚本匹配基于由匹配模式定义的一组 Url。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-105">Host permissions and content script matching are based on a set of URLs defined by match patterns.</span></span>  <span data-ttu-id="8a5f1-106">匹配模式实质上是以允许的方案（、、、或）开头的 URL， `http` `https` `file` `ftp` 其中可以包含 " `*` " 个字符。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-106">A match pattern is essentially a URL that begins with a permitted scheme (`http`, `https`, `file`, or `ftp`, and that can contain '`*`' characters.</span></span>  <span data-ttu-id="8a5f1-107">特殊模式 `<all_urls>` 匹配以允许的方案开头的任何 URL。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-107">The special pattern `<all_urls>` matches any URL that starts with a permitted scheme.</span></span>  <span data-ttu-id="8a5f1-108">每个匹配模式都有3个部分：</span><span class="sxs-lookup"><span data-stu-id="8a5f1-108">Each match pattern has 3 parts:</span></span>  

*   <span data-ttu-id="8a5f1-109">_方案_（例如 `http` 或或） `file`</span><span class="sxs-lookup"><span data-stu-id="8a5f1-109">_scheme_ — for example, `http` or `file` or</span></span> `*`  

> [!NOTE]
> <span data-ttu-id="8a5f1-110">对 `file` url 的访问不是自动的。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-110">Access to `file` URLs is not automatic.</span></span>  <span data-ttu-id="8a5f1-111">用户必须访问 "扩展管理" 页面，并选择为 `file` 请求它的每个扩展进行访问。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-111">The user must visit the Extensions management page and opt in to `file` access for each Extension that requests it.</span></span>  

*   `_host_` <span data-ttu-id="8a5f1-112">-例如， `www.google.com` 或 `*.google.com` `*` ; 如果方案为文件，则没有主机部件。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-112">— for example, `www.google.com` or `*.google.com` or `*`; if the scheme is file, there is no host part.</span></span>  
*   `_path_` <span data-ttu-id="8a5f1-113">-例如、、 `/*` `/foo*` 或 `/foo/bar` 。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-113">— for example, `/*`, `/foo*`, or `/foo/bar`.</span></span>  <span data-ttu-id="8a5f1-114">该路径必须存在于主机权限中，但始终被视为 `/*` 。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-114">The path must be present in a host permission, but is always treated as `/*`.</span></span>  

<span data-ttu-id="8a5f1-115">基本语法：</span><span class="sxs-lookup"><span data-stu-id="8a5f1-115">The basic syntax:</span></span>  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

<span data-ttu-id="8a5f1-116">的含义 `*` 取决于它是属于 "方案"、"主机" 还是 "路径" 部分。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-116">The meaning of `*` depends on whether it is in the scheme, host, or path part.</span></span>  <span data-ttu-id="8a5f1-117">如果方案为 `*` ，则它将匹配 `http` 或 `https` ，而不 `file` `ftp` 是或。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-117">If the scheme is `*`, then it matches either `http` or `https`, and not `file`, or `ftp`.</span></span>  <span data-ttu-id="8a5f1-118">如果主机刚刚如此 `*` ，则它匹配任何主机。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-118">If the host is just `*`, then it matches any host.</span></span> <span data-ttu-id="8a5f1-119">如果主机是 `*.hostname` ，则它与指定的主机或任何子域相匹配。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-119">If the host is `*.hostname`, then it matches the specified host or any of the subdomains.</span></span>  <span data-ttu-id="8a5f1-120">在 "路径" 部分中，每个 `*` 字符均匹配0个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-120">In the path section, each `*` matches 0 or more characters.</span></span>  <span data-ttu-id="8a5f1-121">下表显示了一些有效的模式。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-121">The following table shows some valid patterns.</span></span>  

| <span data-ttu-id="8a5f1-122">模式</span><span class="sxs-lookup"><span data-stu-id="8a5f1-122">Pattern</span></span> | <span data-ttu-id="8a5f1-123">用途</span><span class="sxs-lookup"><span data-stu-id="8a5f1-123">What it does</span></span> | <span data-ttu-id="8a5f1-124">匹配 Url 的示例</span><span class="sxs-lookup"><span data-stu-id="8a5f1-124">Examples of matching URLs</span></span> |  
|:--- |:--- |:--- |  
| `http://*/*` | <span data-ttu-id="8a5f1-125">匹配任何使用 http 方案的 URL</span><span class="sxs-lookup"><span data-stu-id="8a5f1-125">Matches any URL that uses the http scheme</span></span> | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | <span data-ttu-id="8a5f1-126">匹配任何主机上任何使用 http 方案的 URL，只要路径开头为</span><span class="sxs-lookup"><span data-stu-id="8a5f1-126">Matches any URL that uses the http scheme, on any host, as long as the path starts with</span></span> `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | <span data-ttu-id="8a5f1-127">与任何使用 https 方案的 URL 均位于 `google.com` 主机 \ （如 `www.google.com` 、 `docs.google.com` 或 `google.com` \）上，只要路径的开头 `/foo` 和结尾为</span><span class="sxs-lookup"><span data-stu-id="8a5f1-127">Matches any URL that uses the https scheme, is on a `google.com` host \(such as `www.google.com`, `docs.google.com`, or `google.com`\), as long as the path starts with `/foo` and ends with</span></span> `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | <span data-ttu-id="8a5f1-128">匹配指定的 URL</span><span class="sxs-lookup"><span data-stu-id="8a5f1-128">Matches the specified URL</span></span> | `http://example.org/foo/bar.html` |  
|`file:///foo*` | <span data-ttu-id="8a5f1-129">匹配路径以下列路径开头的任何本地文件</span><span class="sxs-lookup"><span data-stu-id="8a5f1-129">Matches any local file whose path starts with</span></span> `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | <span data-ttu-id="8a5f1-130">匹配任何使用该 `http` 方案且位于主机上的 URL</span><span class="sxs-lookup"><span data-stu-id="8a5f1-130">Matches any URL that uses the `http` scheme and is on the host</span></span> `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | <span data-ttu-id="8a5f1-131">匹配以或开头的任何 `http://mail.google.com` URL `https://mail.google.com` 。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-131">Matches any URL that starts with `http://mail.google.com` or `https://mail.google.com`.</span></span> | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | <span data-ttu-id="8a5f1-132">匹配任何使用允许的方案的 URL。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-132">Matches any URL that uses a permitted scheme.</span></span> <span data-ttu-id="8a5f1-133">\ （有关允许的方案列表，请参阅本部分的开头部分。）</span><span class="sxs-lookup"><span data-stu-id="8a5f1-133">\(See the beginning of this section for the list of permitted schemes.\)</span></span> | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

<span data-ttu-id="8a5f1-134">下面是一些 `_invalid_` 模式匹配的示例：</span><span class="sxs-lookup"><span data-stu-id="8a5f1-134">Here are some examples of `_invalid_` pattern matches:</span></span>

| <span data-ttu-id="8a5f1-135">错误模式</span><span class="sxs-lookup"><span data-stu-id="8a5f1-135">Bad pattern</span></span> | <span data-ttu-id="8a5f1-136">为什么不正确</span><span class="sxs-lookup"><span data-stu-id="8a5f1-136">Why it is bad</span></span> |  
|:--- |:--- |  
| `http://www.foo.com` | <span data-ttu-id="8a5f1-137">否</span><span class="sxs-lookup"><span data-stu-id="8a5f1-137">No</span></span> `_path_` |  
| `http://*foo/bar` | <span data-ttu-id="8a5f1-138">主机中的 "" `*` 只能后跟 " `.` " 或 " `/` "</span><span class="sxs-lookup"><span data-stu-id="8a5f1-138">'`*`' in the host can be followed only by a '`.`' or '`/`'</span></span> |  
| `http://foo.*.bar/baz` | <span data-ttu-id="8a5f1-139">如果 " `*` " 在中 `_host_` ，则必须是第一个字符</span><span class="sxs-lookup"><span data-stu-id="8a5f1-139">If '`*`' is in the `_host_`, it must be the first character</span></span> |  
| `http:/bar` | <span data-ttu-id="8a5f1-140">缺少 `_scheme_` 分隔符 \ （' `/` ' 应为 " `//` " \ "）</span><span class="sxs-lookup"><span data-stu-id="8a5f1-140">Missing `_scheme_` separator \('`/`' should be "`//`"\)</span></span> |  
| `foo://*` | <span data-ttu-id="8a5f1-141">无效</span><span class="sxs-lookup"><span data-stu-id="8a5f1-141">Invalid</span></span> `_scheme_` |  

<span data-ttu-id="8a5f1-142">某些方案在所有上下文中都不受支持。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-142">Some schemes are not supported in all contexts.</span></span>

> [!NOTE]
> <span data-ttu-id="8a5f1-143">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-143">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8a5f1-144">可在[此处](https://developer.chrome.com/extensions/match_patterns/)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-144">The original page is found [here](https://developer.chrome.com/extensions/match_patterns/).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="8a5f1-146">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8a5f1-146">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
