---
description: 了解自动更新到 Microsoft Edge
title: 自动更新 Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: d9901f9c39dabfab111eb7e0c34a3e267a317110
ms.sourcegitcommit: 59d8043e37b89da814f63bc85daf84e0e7167eab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2021
ms.locfileid: "11586386"
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
# <a name="automatically-update-extensions-in-microsoft-edge"></a>自动更新 Microsoft Edge  

将扩展设置为自动更新时，扩展将在设置为自动更新Microsoft Edge共享以下优势。  

*   合并 Bug 和安全修补程序。  
*   添加新功能或性能增强功能。  
*   改进用户界面。  

以前支持基于非存储的扩展。  此外，你同时更新了本机二进制文件和扩展。  

现在，Microsoft Edge加载项存储托管扩展，并且使用与加载项相同的机制更新Microsoft Edge。  你无法控制更新机制。  更新依赖本机二进制文件的扩展时请谨慎。  

> [!NOTE]
> 本文不适用于使用合作伙伴中心仪表板[发布的扩展。][MicrosoftPartnerDashboardMicrosoftedgePublicLoginRefDd]  可以使用仪表板向用户和加载项商店Microsoft Edge更新的版本。  有关详细信息，请导航到 [更新或删除扩展][ExtensionsPublishUpdateExtension]。  

## <a name="overview"></a>概述  

每隔几个小时，Microsoft Edge检查每个安装的扩展或应用是否都有更新 URL。  若要为扩展指定更新 URL，请使用 `update_url` 清单中的 字段。  清单 `update_url` 中的字段指向完成更新检查的位置。  对于每个 `update_url` ，它将发送对更新后的清单 XML 文件的请求。  如果更新清单 XML 文件列出了比安装的版本更新的版本，Microsoft Edge下载并安装较新版本。  相同的过程适用于手动更新，其中必须使用与当前安装的版本相同的私钥对新 `.crx` 文件进行签名。  

> [!NOTE]
> 为了维护用户隐私，Microsoft Edge发送任何包含自动更新清单请求的标头，并忽略这些请求响应中的任意 `Cookie` `Set-Cookie` 标头。  

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
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
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
| `version` | 此属性值由 Microsoft Edge确定是否应下载 `.crx` 由 指定的文件 `codebase` 。  它应匹配 `version` 文件文件中 `manifest.json` `.crx` 的值。 |  

更新清单 XML 文件可能包含有关多个扩展的信息，具体方法为包含多个元素。  

## <a name="testing"></a>测试  

默认更新检查频率为几个小时。  若要强制更新，请导航 `edge://extensions` 到"现在 **更新扩展"** 按钮并选择该按钮。  

## <a name="advanced-usage-request-parameters"></a>高级用法：请求参数  

基本机制很简单。  若要自动更新扩展，请完成以下操作。  

1.  Upload Web 服务器上创建静态 XML 文件，如 Apache。  
1.  在发布新版本的扩展时更新 XML 文件。  
    
利用添加到更新清单请求中的某些参数指示扩展和 这一 `ID` 事实 `version` 。  可以针对所有 `update URL` 扩展使用相同方法，而不是静态 XML 文件。  若要在所有扩展中使用相同的方法，请指向运行动态服务器端代码以 `update URL` 测试参数的 URL。  

以下示例演示更新 URL 的请求参数的格式。  

```url
?x={extension_data}
```  

本示例中， `{extension_data}` 是一个 URL 编码的字符串，它采用以下格式。  

```url
id={id}&v={version}
```  

例如，以下两个扩展都指向相同的更新 `http://contoso.com/extension_updates.php` URL。  

*   扩展名 1  
    *   ID： `aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa`  
    *   更新 URL： `http://contoso.com/extension_updates.php`
    *   版本： `1.1`  
*   扩展名 2  
    *   ID： `bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb`  
    *   更新 URL： `http://contoso.com/extension_updates.php`
    *   版本： `0.4`  


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

随着适用于 Microsoft Edge 扩展系统的新 API 发布，你可以发布仅适用于较新版本的扩展或应用的Microsoft Edge版本。  当Microsoft Edge自动更新时，大多数用户可能需要几天时间才能更新到该新版本。  若要确保特定更新仅适用于Microsoft Edge版本或高于特定版本的更新版本，请在你的更新清单中添加 `prodversionmin` 属性。  在下面的代码段中，属性值 指定仅在用户运行版本或更新版本时，Microsoft Edge `prodversionmin` `3.0.193.0` `2.0` `3.0.193.0` 更新。  

```xml
<?xml version='1.0' encoding='UTF-8'?>
<gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'>
  <app appid='aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa'>
    <updatecheck codebase='http://contoso.com/mytestextension/mte_v2.crx' version='2.0' prodversionmin='3.0.193.0' />
  </app>
</gupdate>
```  

<!-- links -->  

[ExtensionsPublishUpdateExtension]: ../publish/update-extension.md "更新或删除扩展|Microsoft Docs"  

[MicrosoftPartnerDashboardMicrosoftedgePublicLoginRefDd]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/docs/apps/autoupdate)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
