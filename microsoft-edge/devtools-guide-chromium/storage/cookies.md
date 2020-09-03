---
description: 了解如何使用 Microsoft Edge DevTools 查看、编辑和删除页面的 HTTP cookie。
title: 查看、编辑和删除 Microsoft Edge DevTools 中的 Cookie
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: eaaf4663504fc674fd70dc1ca9e0357febb529e0
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993238"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# 查看、编辑和删除 Microsoft Edge DevTools 中的 cookie  

[HTTP cookie][MDNHTTPCookies] 主要用于管理用户会话、存储用户个性化首选项和跟踪用户行为。  Cookie 也是由您在 web 上看到的所有令人讨厌的 "此页面使用 cookies" 同意表单的原因。  以下指南教你如何查看、编辑和删除具有 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]的页面的 HTTP cookie。  

## 打开 "Cookie" 窗格  

1.  [打开 DevTools][DevToolsOpen]。  
1.  选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。  将打开 " **清单** " 窗格。  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest-empty.msft.png":::
       图1：清单窗格  
    :::image-end:::  

1.  在 " **存储** " 下展开 " **cookie**"，然后选择一个原点。  
    
    :::image type="complex" source="../media/storage-application-storage-cookies-selected.msft.png" alt-text=""Cookie" 窗格" lightbox="../media/storage-application-storage-cookies-selected.msft.png":::
       图2： "Cookie" 窗格  
    :::image-end:::  

## 字段  

**Cookies**表包含以下字段。  

*   **名称**。  Cookie 的名称。  
*   **值**。  Cookie 的值。  
*   **域**。  允许接收该 cookie 的主机。  请参阅 [Cookie 范围][MDNHTTPCookiesScope]。  
*   **路径**。  必须存在于请求的 URL 中才能发送页眉的 URL `Cookie` 。  请参阅 [Cookie 范围][MDNHTTPCookiesScope]。  
*   **过期/最大存留期**。  Cookie 的到期日期或最长期限。  请参阅 [永久 cookie][MDNHTTPCookiesPermanent]。  对于 [会话 cookie][MDNHTTPCookiesSession] ，此值始终为 `Session` 。  
*   **大小**。  Cookie 的大小（以字节为单位）。  
*   **HTTP**。  如果为 true，则此字段指示应仅通过 HTTP 使用该 cookie，并且不允许 JavaScript 修改。  请参阅 [HttpOnly cookie][MDNHTTPCookiesSecure]。  
*   **安全**。  如果为 true，则此字段指示该 cookie 必须仅通过安全的 HTTPS 连接发送到服务器。  请参阅 [安全 cookie][MDNHTTPCookiesSecure]。  
*   **SameSite**。  包含 `strict` 或 `lax` 如果 cookie 使用实验性的 [Samesite][MDNHTTPCookiesSamesite] 属性。  
*   **优先级**。  包含 `low` ， `medium` \ (默认 \ ) ，或者 `high` cookie 使用的是已否决的 [cookie 优先级][ChromiumIssue232693] 属性。

## 筛选 cookie  

使用 " **筛选** " 文本框按 **名称** 或 **值**筛选 cookie。  不支持按其他字段进行筛选。  

:::image type="complex" source="../media/storage-application-storage-cookies-filter-id.msft.png" alt-text="筛选出不包含文本 ID 的任何 cookie" lightbox="../media/storage-application-storage-cookies-filter-id.msft.png":::
   图3：筛选出不包含文本的任何 cookie `ID`  
:::image-end:::  

## 编辑 cookie  

" **名称**"、" **值**"、" **域**"、" **路径**" 和 "有效期" **/"最大年龄** " 域可编辑  
双击字段以对其进行编辑。  

:::image type="complex" source="../media/storage-application-storage-cookies-rename.msft.png" alt-text="将 cookie 的名称设置为 DEVTOOLS！" lightbox="../media/storage-application-storage-cookies-rename.msft.png":::
   图4：将 cookie 的名称设置为 `DEVTOOLS!`  
:::image-end:::  

## 删除 Cookie  

选择一个 cookie，然后选择 " **删除**所选 ![ 删除 ][ImageDeleteIcon]  " 以删除特定的 cookie。  

:::image type="complex" source="../media/storage-application-storage-cookies-delete-selected.msft.png" alt-text="删除特定的 cookie" lightbox="../media/storage-application-storage-cookies-delete-selected.msft.png":::
   图5：删除特定的 cookie  
:::image-end:::  

选择 " **清除**全部 ![ 清除" ][ImageClearIcon]  以删除所有 cookie。  

:::image type="complex" source="../media/storage-application-storage-cookies-clear-all.msft.png" alt-text="清除所有 cookie" lightbox="../media/storage-application-storage-cookies-clear-all.msft.png":::
   图6：清除所有 cookie  
:::image-end:::  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  

[ChromiumIssue232693]: https://bugs.chromium.org/p/chromium/issues/detail?id=232693 "Chromium 问题232693：为 Cookies 实施优先级字段 |Chromium Bug"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookie |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP cookie-永久 cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP cookie-SameSite cookie |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie-cookie 范围 |MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP cookie-安全和 HttpOnly cookie |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP cookie-会话 cookie |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
