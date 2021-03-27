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
# <a name="auto-update-extensions-in-microsoft-edge"></a>Microsoft Edge 中的自动更新扩展  

自动更新扩展与自动更新 Microsoft Edge 有一些相同的优势：   

*   合并 Bug 和安全修补程序。  
*   添加新功能或性能增强功能。  
*   改进用户界面。  

以前，当支持基于非存储的扩展时，可以同时更新本机二进制文件和扩展。  现在，这些扩展托管在 Microsoft Edge 加载项存储中，并且使用 Microsoft Edge 使用的相同机制进行更新，你无法控制该机制。  在更新依赖本机二进制文件的扩展时，你应该小心。  

> [!NOTE]
> 本主题不适用于使用合作伙伴中心仪表板 [发布的][MicrosoftPartnerCenter] 扩展。  可以使用仪表板向用户和 Microsoft Edge 加载项商店发布更新后的版本。

## <a name="overview"></a>概述  

每隔几个小时，Microsoft Edge 会检查每个安装的扩展或应用是否都有更新 URL。  扩展可以使用清单中的 字段指定更新 URL，该字段指向执行更新 `update_url` 检查的位置。  对于每个 `update_url` ，它将发送对更新后的清单 XML 文件的请求。  如果更新清单 XML 文件列出了比安装的版本更新的版本，Microsoft Edge 将下载并安装较新版本。  相同的过程适用于手动更新，其中必须使用与当前安装的版本相同的私钥对新 `.crx` 文件进行签名。  

> [!NOTE]
> 为了维护用户隐私，Microsoft Edge 不会发送任何包含自动更新清单请求的标头，并忽略这些请求响应中的任意 `Cookie` `Set-Cookie` 标头。  

## <a name="update-url"></a>更新 URL  

如果你托管自己的扩展名或应用，则必须将 `update_url` 字段添加到 `manifest.json` 你的文件。  查看以下代码段，查看 的示例 `update_url` 。  

```json
{
  "name": "My extension",
  ... 
  "update_url": "http://contoso.com/mytestextension/updates.xml",
  ... 
}
```  

## <a name="updated-manifest"></a>更新后的清单  

服务器返回的更新清单应为 XML 文档。  查看以下代码段，查看更新后的清单 XML 文件的示例。  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.microsoft.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' />
  </app>
</gupdate>
```  

下表介绍了更新后的清单 XML 文件的属性。  

| 属性 | 详细信息 | 
|:--- |:--- |  
| `appid` | 扩展 ID 是基于公钥的哈希生成的。  若要查找扩展的 ID，请打开 Microsoft Edge 并导航到 `edge://extensions` 。 |  
| `codebase` | 指向文件的 `.crx` URL。 |  
| `version` | 此属性值由 Microsoft Edge 用来确定是否应下载 `.crx` 由 指定的文件 `codebase` 。  它应匹配 `version` 文件文件中 `manifest.json` `.crx` 的值。 |  

更新清单 XML 文件可能包含有关多个扩展的信息，具体方法为包含多个元素。  

## <a name="testing"></a>测试  

默认更新检查频率为几个小时。  若要强制更新，请导航 `edge://extensions` 到"现在 **更新扩展"** 按钮并选择该按钮。  

## <a name="advanced-usage-request-parameters"></a>高级用法：请求参数  

基本自动更新机制与将静态 XML 文件放置到任何 Web 服务器（如 Apache）和更新 XML 文件一样简单，就像发布新版本的扩展一样。  

你可以利用将参数添加到指示扩展 ID 和版本的更新清单请求这一事实。 可以针对所有扩展使用相同的更新 URL，而不是静态 XML 文件。  若要针对所有扩展使用相同的更新 URL，请指向运行动态服务器端代码以测试这些参数的 URL。  

以下示例演示更新 URL 的请求参数的格式 `?x={extension_data}` ：。

本示例中， `{extension_data}` 是一个 URL 编码的字符串，它采用以下格式 `id={id}&v={version}` ：。

例如，以下两个扩展都指向相同的更新 `http://contoso.com/extension_updates.php` URL。  

*  扩展 1 - ID："aaaaaaaaaaaaaaaaa"版本："1.1"
*  分机 2 - ID："bbbbbbbbbb"版本："0.4"


以下是更新每个扩展的请求。  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1
```  

```https
http://contoso.com/extension_updates.php?x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

还可以针对每个唯一更新 URL 在单个请求中列出多个扩展。  以下示例将前面的请求合并为单个请求。  

```https
http://contoso.com/extension_updates.php?x=id%3Daaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa%26v%3D1.1&x=id%3Dbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb%26v%3D0.4
```  

如果发送单个请求，并且使用同一更新 URL 的已安装扩展的数量太长，则更新检查将发出更多 `GET` 请求。  如果 `GET` 请求 URL 大约为 2000 个字符，则请求 URL 太长。  

> [!NOTE]
> 将来，单个 `POST` 请求可能会替换多个 `GET` 请求。  `POST`请求正文中可能包含请求 `POST` 参数。  

## <a name="advanced-usage-minimum-browser-version"></a>高级用法：最低浏览器版本  

随着 Microsoft Edge 扩展系统的新 API 发布，你可以发布仅适用于较新 Microsoft Edge 版本的扩展或应用的更新版本。  当 Microsoft Edge 自动更新时，大多数用户可能需要几天时间才能更新到该新版本。  若要确保特定更新仅适用于当前或高于特定版本的 Microsoft Edge 版本，请在你的更新清单中添加 `prodversionmin` 属性。  在下面的代码段中，属性值 指定应用仅在用户运行 Microsoft Edge 或更高版本时 `prodversionmin` `3.0.193.0` `2.0` `3.0.193.0` 自动更新到版本。  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/docs/apps/autoupdate/)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
