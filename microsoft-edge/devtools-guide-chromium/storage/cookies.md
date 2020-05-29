---
title: 查看、编辑和删除 Microsoft Edge DevTools 中的 Cookie
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 084c4116cd4c9c5e70b2fe341257fa68ba2c8ae7
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612066"
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





# 查看、编辑和删除 Microsoft Edge DevTools 中的 Cookie   

  

[HTTP cookie][MDNHTTPCookies]主要用于管理用户会话、存储用户个性化首选项和跟踪用户行为。  它们也是导致所有这些令人讨厌的 "此页面使用 cookie" 同意表单的原因。  本指南教你如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]查看、编辑和删除页面上的 HTTP cookie。  

## 打开 "Cookie" 窗格   

1.  [打开 DevTools][DevToolsOpen]。  
1.  选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。  将打开 "**清单**" 窗格。  
    
    > ##### 图 1  
    > 清单窗格  
    > ![清单窗格][ImageManifest]  

1.  在 "**存储**" 下展开 " **cookie**"，然后选择一个原点。  
    
    > ##### 图 2  
    > "Cookie" 窗格  
    > !["Cookie" 窗格][ImageCookies]  

## 字段   

**Cookies**表包含以下字段：  

*   **名称**。  Cookie 的名称。  
*   **值**。  Cookie 的值。  
*   **域**。  允许接收该 cookie 的主机。  请参阅[Cookie 范围][MDNHTTPCookiesScope]。  
*   **路径**。  必须存在于请求的 URL 中才能发送页眉的 URL `Cookie` 。  请参阅[Cookie 范围][MDNHTTPCookiesScope]。  
*   **过期/最大存留期**。  Cookie 的到期日期或最长期限。  请参阅[永久 cookie][MDNHTTPCookiesPermanent]。  对于[会话 cookie][MDNHTTPCookiesSession] ，此值始终为 `Session` 。  
*   **大小**。  Cookie 的大小（以字节为单位）。  
*   **HTTP**。  如果为 true，则此字段指示应仅通过 HTTP 使用该 cookie，并且不允许 JavaScript 修改。  请参阅[HttpOnly cookie][MDNHTTPCookiesSecure]。  
*   **安全**。  如果为 true，则此字段指示该 cookie 必须仅通过安全的 HTTPS 连接发送到服务器。  请参阅[安全 cookie][MDNHTTPCookiesSecure]。  
*   **SameSite**。  包含 `strict` 或 `lax` 如果 cookie 使用实验性的[Samesite][MDNHTTPCookiesSamesite]属性。  

## 筛选 cookie   

使用 "**筛选**" 文本框按**名称**或**值**筛选 cookie。  不支持按其他字段进行筛选。  

> ##### 图 3  
> 筛选出不包含文本的任何 cookie `ID`  
> ![筛选出不包含文本 ID 的任何 cookie][ImageCookiesFilter]  

## 编辑 cookie   

"**名称**"、"**值**"、"**域**"、"**路径**" 和 "有效期" **/"最大年龄**" 域可编辑  
双击字段以对其进行编辑。  

> ##### 图 4  
> 将 cookie 的名称设置为 `DEVTOOLS!`  
> ![将 cookie 的名称设置为 DEVTOOLS！][ImageEditCookie]  

## 删除 Cookie   

选择一个 cookie，然后单击 "**删除**所选 ![ 删除项" ][ImageDeleteIcon] 以删除该 cookie。  

> ##### 图 5  
> 删除特定的 cookie  
> ![删除特定的 cookie][ImageDeleteCookie]  

选择 "**清除**全部 ![ 清除" ][ImageClearIcon] 以删除所有 cookie。  

> ##### 图 6  
> 清除所有 cookie  
> ![清除所有 cookie][ImageClearAllCookies]  

<!--    -->  

  

<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest-empty.msft.png "图1：清单窗格"  
[ImageCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-selected.msft.png "图2： "Cookie" 窗格"  
[ImageCookiesFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-filter-id.msft.png "图3：筛选出不包含文本 ID 的任何 cookie"  
[ImageEditCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-rename.msft.png "图4：将 cookie 的名称设置为 DEVTOOLS！"  
[ImageDeleteCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-delete-selected.msft.png "图5：删除特定的 cookie"  
[ImageClearAllCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-clear-all.msft.png "图6：清除所有 cookie"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP cookie |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP cookie-永久 cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP cookie-SameSite cookie |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie-cookie 范围 |MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP cookie-安全和 HttpOnly cookie |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP cookie-会话 cookie |MDN"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
