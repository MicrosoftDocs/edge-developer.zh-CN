---
description: 在企业中托管和发布 Microsoft Edge (Chromium) 。
title: 在 Microsoft Edge 加载项存储中发布和更新扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 91fdd5c2f625890653085e8999da3e513b072348
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327685"
---
# 在 Microsoft Edge 加载项存储中发布和更新扩展  

大多数扩展都发布到 Microsoft [Edge 加载项][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions] 存储，以保护用户免受恶意扩展的攻击。  

## 发布扩展选项  

所有扩展作为带有后缀的特殊存档 \ (`.zip` \) 分发给 `.crx` 用户。  发布到 Microsoft Edge 加载项存储的扩展作为文件 `.zip` 上载。  发布过程会自动将文件 `.zip` 转换为 `.crx` 文件。  

以下两种方案不要求您在 Microsoft Edge 加载项存储中发布扩展。  

*   使用企业策略分发的扩展。  
*   当 Microsoft Edge 处于开发人员模式时，在本地计算机上使用未打包的扩展目录。  

## 扩展的更新

Microsoft Edge 浏览器会定期检查已安装扩展的新版本，并更新每个扩展，而无需用户干预。  

<!-- links -->  

[MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "扩展 - Microsoft Edge 预览体验成员|Microsoft"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/extensions/hosting)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
