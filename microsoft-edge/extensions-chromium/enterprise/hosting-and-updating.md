---
description: 扩展企业文档 for Edge （Chromium）扩展。
title: 托管和更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: eb1f9921d503d25557fc9efb1517537e7a90f4aa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563381"
---
# Web 应用商店托管和更新  

大多数扩展均托管在[Microsoft Edge 预览体验成员 Addons 目录 \ （Microsoft Edge 预览体验计划 Addons \）][MicrosoftStoreExtensions]中，可最好地保护用户免受恶意扩展。  

## 托管  

所有扩展都将作为特殊的 ZIP 文件分配给用户，使用 crx 后缀。  Microsoft Edge Addons 中托管的扩展将作为 .zip 文件上传。 发布过程会自动将 .zip 转换为 crx 文件。  

Microsoft Edge Addons 托管规则有两个例外：  

1.  通过企业策略分配的扩展。  
1.  在开发人员模式下，从本地计算机解压缩扩展目录。  

## 更新  

Microsoft Edge 浏览器会定期检查已安装扩展和更新的新版本，无需用户干预。  

> [!NOTE]
> 将添加计划添加在 Microsoft Edge Addons 上更新扩展的步骤。  

<!-- image links -->

<!-- links -->  

[MicrosoftStoreExtensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "扩展-Microsoft Edge 预览体验计划 Addons"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 可在[此处](https://developer.chrome.com/extensions/hosting)找到原始页面。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
