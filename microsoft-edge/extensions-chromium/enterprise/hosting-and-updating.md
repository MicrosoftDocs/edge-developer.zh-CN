---
description: 在企业中托管和发布扩展Microsoft Edge (Chromium) 。
title: 发布和更新加载项Microsoft Edge加载项存储中的扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 2249462b0a2dac86efa4b775171e2a3229a34431
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461218"
---
# <a name="publish-and-update-extensions-in-the-microsoft-edge-add-ons-store"></a>发布和更新加载项Microsoft Edge加载项存储中的扩展  

大多数扩展都发布到Microsoft Edge[加载项][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]存储，以保护用户免受恶意扩展的攻击。  

## <a name="publish-options-for-extensions"></a>发布扩展选项  

所有扩展名都作为一个特殊的存档 \(`.zip` \) 文件作为后缀分发给 `.crx` 用户。  发布到加载项Microsoft Edge扩展作为文件 `.zip` 上载。  发布过程会自动将文件 `.zip` 转换为 `.crx` 文件。  

以下两种方案不需要你在加载项应用商店中Microsoft Edge扩展。  

*   使用策略分配Enterprise扩展。  
*   在本地计算机上使用解压缩的扩展目录Microsoft Edge开发人员模式时。  

## <a name="updates-to-extensions"></a>扩展的更新

浏览器Microsoft Edge检查安装的扩展的新版本。 安装更新时无需用户干预。  


<!-- image links -->

<!-- links -->  

[MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "扩展 - Microsoft Edge预览体验成员加载项|Microsoft"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/extensions/hosting)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
