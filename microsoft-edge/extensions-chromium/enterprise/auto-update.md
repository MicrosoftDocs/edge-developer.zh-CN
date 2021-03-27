---
description: 了解 Microsoft Edge 中扩展的自动更新
title: Microsoft Edge 中的自动更新扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 0f3f140cd3a2a079cd09f4d61e46a420342e15e0
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461498"
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
# <a name="auto-update-extensions-in-microsoft-edge"></a><span data-ttu-id="68383-104">Microsoft Edge 中的自动更新扩展</span><span class="sxs-lookup"><span data-stu-id="68383-104">Auto-update extensions in Microsoft Edge</span></span>  

<span data-ttu-id="68383-105">自动更新扩展与自动更新 Microsoft Edge 有一些相同的优势：</span><span class="sxs-lookup"><span data-stu-id="68383-105">Automatically updating extensions share some of the same benefits as automatically updating Microsoft Edge:</span></span>   

*   <span data-ttu-id="68383-106">合并 Bug 和安全修补程序。</span><span class="sxs-lookup"><span data-stu-id="68383-106">Incorporate bug and security fixes.</span></span>  
*   <span data-ttu-id="68383-107">添加新功能或性能增强功能。</span><span class="sxs-lookup"><span data-stu-id="68383-107">Add new features or performance enhancements.</span></span>  
*   <span data-ttu-id="68383-108">改进用户界面。</span><span class="sxs-lookup"><span data-stu-id="68383-108">Improve the user interface.</span></span>  

<span data-ttu-id="68383-109">以前，当支持基于非存储的扩展时，可以同时更新本机二进制文件和扩展。</span><span class="sxs-lookup"><span data-stu-id="68383-109">Previously when non-store based extensions were supported, it was possible to update the native binaries and the extension at the same time.</span></span>  <span data-ttu-id="68383-110">现在，这些扩展托管在 Microsoft Edge 加载项存储中，并且使用 Microsoft Edge 使用的相同机制进行更新，你无法控制该机制。</span><span class="sxs-lookup"><span data-stu-id="68383-110">Now, those extensions are hosted in the Microsoft Edge Add-ons store and updates are made using the same mechanism that Microsoft Edge uses, which you can't control.</span></span>  <span data-ttu-id="68383-111">在更新依赖本机二进制文件的扩展时，你应该小心。</span><span class="sxs-lookup"><span data-stu-id="68383-111">You should be careful when updating extensions that have a dependency on native binaries.</span></span>  

> [!NOTE]
> <span data-ttu-id="68383-112">本主题不适用于使用合作伙伴中心仪表板 [发布的][MicrosoftPartnerCenter] 扩展。</span><span class="sxs-lookup"><span data-stu-id="68383-112">This topic does not apply to extensions published using the [Partner Center][MicrosoftPartnerCenter] dashboard.</span></span>  <span data-ttu-id="68383-113">可以使用仪表板向用户和 Microsoft Edge 加载项商店发布更新后的版本。</span><span class="sxs-lookup"><span data-stu-id="68383-113">You may use the dashboard to release updated versions to your users and to the Microsoft Edge Add-ons store.</span></span>

## <a name="overview"></a><span data-ttu-id="68383-114">概述</span><span class="sxs-lookup"><span data-stu-id="68383-114">Overview</span></span>  

<span data-ttu-id="68383-115">每隔几个小时，Microsoft Edge 会检查每个安装的扩展或应用是否都有更新 URL。</span><span class="sxs-lookup"><span data-stu-id="68383-115">Every few hours, Microsoft Edge checks whether each installed extension or app has an update URL.</span></span>  <span data-ttu-id="68383-116">扩展可以使用清单中的 字段指定更新 URL，该字段指向执行更新 `update_url` 检查的位置。</span><span class="sxs-lookup"><span data-stu-id="68383-116">Extensions can specify an update URL using the `update_url` field in the manifest, which points to a location to perform an update check.</span></span>  <span data-ttu-id="68383-117">对于每个 `update_url` ，它将发送对更新后的清单 XML 文件的请求。</span><span class="sxs-lookup"><span data-stu-id="68383-117">For each `update_url`, it sends requests for updated manifest XML files.</span></span>  <span data-ttu-id="68383-118">如果更新清单 XML 文件列出了比安装的版本更新的版本，Microsoft Edge 将下载并安装较新版本。</span><span class="sxs-lookup"><span data-stu-id="68383-118">If the update manifest XML file lists a newer version than that installed, Microsoft Edge downloads and installs the newer version.</span></span>  <span data-ttu-id="68383-119">相同的过程适用于手动更新，其中必须使用与当前安装的版本相同的私钥对新 `.crx` 文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="68383-119">The same process works for manual updates, where the new `.crx` file must be signed with the same private key as the currently installed version.</span></span>  

> [!NOTE]
> <span data-ttu-id="68383-120">为了维护用户隐私，Microsoft Edge 不会发送任何包含自动更新清单请求的标头，并忽略这些请求响应中的任意 `Cookie` `Set-Cookie` 标头。</span><span class="sxs-lookup"><span data-stu-id="68383-120">In order to maintain user privacy, Microsoft Edge does not send any `Cookie` headers with auto-update manifest requests, and ignores any `Set-Cookie` headers in the responses to those requests.</span></span>  

## <a name="update-url"></a><span data-ttu-id="68383-121">更新 URL</span><span class="sxs-lookup"><span data-stu-id="68383-121">Update URL</span></span>  

<span data-ttu-id="68383-122">如果你托管自己的扩展名或应用，则必须将 `update_url` 字段添加到 `manifest.json` 你的文件。</span><span class="sxs-lookup"><span data-stu-id="68383-122">If you host your own extension or app, you must add the `update_url` field to your `manifest.json` file.</span></span>  <span data-ttu-id="68383-123">查看以下代码段，查看 的示例 `update_url` 。</span><span class="sxs-lookup"><span data-stu-id="68383-123">Review the following code snippet for an example of the `update_url`.</span></span>  

```json
{
  "name": "My extension",
  ... 
  "update_url": "http://contoso.com/mytestextension/updates.xml",
  ... 
}
```  

## <a name="updated-manifest"></a><span data-ttu-id="68383-124">更新后的清单</span><span class="sxs-lookup"><span data-stu-id="68383-124">Updated manifest</span></span>  

<span data-ttu-id="68383-125">服务器返回的更新清单应为 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="68383-125">The updated manifest returned by the server should be an XML document.</span></span>  <span data-ttu-id="68383-126">查看以下代码段，查看更新后的清单 XML 文件的示例。</span><span class="sxs-lookup"><span data-stu-id="68383-126">Review the following code snippet for an example of the updated manifest XML file.</span></span>  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.microsoft.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' />
  </app>
</gupdate>
```  

<span data-ttu-id="68383-127">下表介绍了更新后的清单 XML 文件的属性。</span><span class="sxs-lookup"><span data-stu-id="68383-127">The following table describes attributes of the updated manifest XML file.</span></span>  

| <span data-ttu-id="68383-128">属性</span><span class="sxs-lookup"><span data-stu-id="68383-128">Attribute</span></span> | <span data-ttu-id="68383-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="68383-129">Details</span></span> | 
|:--- |:--- |  
| `appid` | <span data-ttu-id="68383-130">扩展 ID 是基于公钥的哈希生成的。</span><span class="sxs-lookup"><span data-stu-id="68383-130">The extension ID is generated based on a hash of the public key.</span></span>  <span data-ttu-id="68383-131">若要查找扩展的 ID，请打开 Microsoft Edge 并导航到 `edge://extensions` 。</span><span class="sxs-lookup"><span data-stu-id="68383-131">To find the ID of an extension, open Microsoft Edge and navigate to `edge://extensions`.</span></span> |  
| `codebase` | <span data-ttu-id="68383-132">指向文件的 `.crx` URL。</span><span class="sxs-lookup"><span data-stu-id="68383-132">A URL to the `.crx` file.</span></span> |  
| `version` | <span data-ttu-id="68383-133">此属性值由 Microsoft Edge 用来确定是否应下载 `.crx` 由 指定的文件 `codebase` 。</span><span class="sxs-lookup"><span data-stu-id="68383-133">This attribute value is used by Microsoft Edge to determine whether it should download the `.crx` file specified by `codebase`.</span></span>  <span data-ttu-id="68383-134">它应匹配 `version` 文件文件中 `manifest.json` `.crx` 的值。</span><span class="sxs-lookup"><span data-stu-id="68383-134">It should match the value of `version` in the `manifest.json` file of the `.crx` file.</span></span> |  

<span data-ttu-id="68383-135">更新清单 XML 文件可能包含有关多个扩展的信息，具体方法为包含多个元素。</span><span class="sxs-lookup"><span data-stu-id="68383-135">The update manifest XML file may contain information about multiple extensions by including multiple elements.</span></span>  

## <a name="testing"></a><span data-ttu-id="68383-136">测试</span><span class="sxs-lookup"><span data-stu-id="68383-136">Testing</span></span>  

<span data-ttu-id="68383-137">默认更新检查频率为几个小时。</span><span class="sxs-lookup"><span data-stu-id="68383-137">The default update check frequency is several hours.</span></span>  <span data-ttu-id="68383-138">若要强制更新，请导航 `edge://extensions` 到"现在 **更新扩展"** 按钮并选择该按钮。</span><span class="sxs-lookup"><span data-stu-id="68383-138">To force an update, navigate to `edge://extensions` and choose the **Update extensions now** button.</span></span>  

## <a name="advanced-usage-request-parameters"></a><span data-ttu-id="68383-139">高级用法：请求参数</span><span class="sxs-lookup"><span data-stu-id="68383-139">Advanced usage: request parameters</span></span>  

<span data-ttu-id="68383-140">基本自动更新机制与将静态 XML 文件放置到任何 Web 服务器（如 Apache）和更新 XML 文件一样简单，就像发布新版本的扩展一样。</span><span class="sxs-lookup"><span data-stu-id="68383-140">The basic auto-update mechanism is as easy as dropping a static XML file onto any web server such as Apache, and updating the XML file as you release new versions of your extensions.</span></span>  

<span data-ttu-id="68383-141">你可以利用将参数添加到指示扩展 ID 和版本的更新清单请求这一事实。</span><span class="sxs-lookup"><span data-stu-id="68383-141">You may take advantage of the fact that parameters are added to the update manifest request that indicate the extension ID and version.</span></span> <span data-ttu-id="68383-142">可以针对所有扩展使用相同的更新 URL，而不是静态 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="68383-142">You can use the same update URL for all your extensions instead of a static XML file.</span></span>  <span data-ttu-id="68383-143">若要针对所有扩展使用相同的更新 URL，请指向运行动态服务器端代码以测试这些参数的 URL。</span><span class="sxs-lookup"><span data-stu-id="68383-143">To use the same update URL for all your extensions, point to a URL that runs dynamic server-side code to test these parameters.</span></span>  

<span data-ttu-id="68383-144">以下示例演示更新 URL 的请求参数的格式 `?x={extension_data}` ：。</span><span class="sxs-lookup"><span data-stu-id="68383-144">The following example demonstrates the format of the request parameters of update URL: `?x={extension_data}`.</span></span>

<span data-ttu-id="68383-145">本示例中， `{extension_data}` 是一个 URL 编码的字符串，它采用以下格式 `id={id}&v={version}` ：。</span><span class="sxs-lookup"><span data-stu-id="68383-145">In this example, `{extension_data}` is a URL-encoded string that uses the following format: `id={id}&v={version}`.</span></span>

<span data-ttu-id="68383-146">例如，以下两个扩展都指向相同的更新 `http://contoso.com/extension_updates.php` URL。</span><span class="sxs-lookup"><span data-stu-id="68383-146">For example, the following two extensions both point to the same update URL `http://contoso.com/extension_updates.php`.</span></span>  

*  <span data-ttu-id="68383-147">扩展 1 - ID："aaaaaaaaaaaaaaaaa"版本："1.1"</span><span class="sxs-lookup"><span data-stu-id="68383-147">Extension 1 - ID: "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa" Version: "1.1"</span></span>
*  <span data-ttu-id="68383-148">分机 2 - ID："bbbbbbbbbb"版本："0.4"</span><span class="sxs-lookup"><span data-stu-id="68383-148">Extension 2 - ID: "bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb" Version: "0.4"</span></span>


<span data-ttu-id="68383-149">以下是更新每个扩展的请求。</span><span class="sxs-lookup"><span data-stu-id="68383-149">The following are the requests to update each extension.</span></span>  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1
```  

```https
http://contoso.com/extension_updates.php?x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

<span data-ttu-id="68383-150">还可以针对每个唯一更新 URL 在单个请求中列出多个扩展。</span><span class="sxs-lookup"><span data-stu-id="68383-150">You may also list multiple extensions in a single request for each unique update URL.</span></span>  <span data-ttu-id="68383-151">以下示例将前面的请求合并为单个请求。</span><span class="sxs-lookup"><span data-stu-id="68383-151">The following example merges the previous requests into a single request.</span></span>  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1&x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

<span data-ttu-id="68383-152">如果发送单个请求，并且使用同一更新 URL 的已安装扩展的数量太长，则更新检查将发出更多 `GET` 请求。</span><span class="sxs-lookup"><span data-stu-id="68383-152">If you send a single request and the number of installed extensions that use the same update URL is too long, the update check issues more `GET` requests.</span></span>  <span data-ttu-id="68383-153">如果 `GET` 请求 URL 大约为 2000 个字符，则请求 URL 太长。</span><span class="sxs-lookup"><span data-stu-id="68383-153">A `GET` request URL is too long if it is approximately 2000 characters.</span></span>  

> [!NOTE]
> <span data-ttu-id="68383-154">将来，单个 `POST` 请求可能会替换多个 `GET` 请求。</span><span class="sxs-lookup"><span data-stu-id="68383-154">In the future, a single `POST` request may replace multiple `GET` requests.</span></span>  <span data-ttu-id="68383-155">`POST`请求正文中可能包含请求 `POST` 参数。</span><span class="sxs-lookup"><span data-stu-id="68383-155">The `POST` request may contain the request parameters in the `POST` body.</span></span>  

## <a name="advanced-usage-minimum-browser-version"></a><span data-ttu-id="68383-156">高级用法：最低浏览器版本</span><span class="sxs-lookup"><span data-stu-id="68383-156">Advanced usage: minimum browser version</span></span>  

<span data-ttu-id="68383-157">随着 Microsoft Edge 扩展系统的新 API 发布，你可以发布仅适用于较新 Microsoft Edge 版本的扩展或应用的更新版本。</span><span class="sxs-lookup"><span data-stu-id="68383-157">As new APIs release for the Microsoft Edge extensions system, you may release an updated version of your extension or app that only works with newer Microsoft Edge versions.</span></span>  <span data-ttu-id="68383-158">当 Microsoft Edge 自动更新时，大多数用户可能需要几天时间才能更新到该新版本。</span><span class="sxs-lookup"><span data-stu-id="68383-158">When Microsoft Edge is auto-updated, it may take a few days before most of your users update to that new release.</span></span>  <span data-ttu-id="68383-159">若要确保特定更新仅适用于当前或高于特定版本的 Microsoft Edge 版本，请在你的更新清单中添加 `prodversionmin` 属性。</span><span class="sxs-lookup"><span data-stu-id="68383-159">To ensure that a specific update applies only to Microsoft Edge versions that are current or newer than a specific version, add the `prodversionmin` attribute in your update manifest.</span></span>  <span data-ttu-id="68383-160">在下面的代码段中，属性值 指定应用仅在用户运行 Microsoft Edge 或更高版本时 `prodversionmin` `3.0.193.0` `2.0` `3.0.193.0` 自动更新到版本。</span><span class="sxs-lookup"><span data-stu-id="68383-160">In the following code snippet, the `prodversionmin` attribute value of `3.0.193.0` specifies that your app auto-updates to version `2.0` only when the user is running Microsoft Edge `3.0.193.0` or newer.</span></span>  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' prodversionmin='3.0.193.0' />
  </app>
</gupdate>
```  

<!-- links -->  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  

> [!NOTE]
> <span data-ttu-id="68383-162">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="68383-162">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="68383-163">原始页面位于 [此处](https://developer.chrome.com/docs/apps/autoupdate/)。</span><span class="sxs-lookup"><span data-stu-id="68383-163">The original page is found [here](https://developer.chrome.com/docs/apps/autoupdate/).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="68383-165">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="68383-165">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
