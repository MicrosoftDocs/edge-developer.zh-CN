---
description: 扩展企业文档，用于 Edge (Chromium) 扩展。
title: 托管和更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: d918aec12e56daf66d13488d360a454d736031e8
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015700"
---
# <span data-ttu-id="74e49-104">Web 应用商店托管和更新</span><span class="sxs-lookup"><span data-stu-id="74e49-104">Web Store Hosting and Updating</span></span>  

<span data-ttu-id="74e49-105">大多数扩展均托管在 [Microsoft Edge 预览体验计划 Addons 目录 \ (Microsoft Edge 预览体验成员 Addons \ ) ][MicrosoftStoreExtensions] 中，以最佳方式保护用户免受恶意扩展。</span><span class="sxs-lookup"><span data-stu-id="74e49-105">Most Extensions are hosted in the [Microsoft Edge Insider Addons catalog \(Microsoft Edge Insider Addons\)][MicrosoftStoreExtensions] to best protect users from malicious Extensions.</span></span>  

## <span data-ttu-id="74e49-106">托管</span><span class="sxs-lookup"><span data-stu-id="74e49-106">Hosting</span></span>  

<span data-ttu-id="74e49-107">所有扩展都将作为特殊的 ZIP 文件分配给用户，使用 crx 后缀。</span><span class="sxs-lookup"><span data-stu-id="74e49-107">All Extensions are distributed to users as a special ZIP file with a .crx suffix.</span></span>  <span data-ttu-id="74e49-108">Microsoft Edge Addons 中托管的扩展将作为 .zip 文件上传。</span><span class="sxs-lookup"><span data-stu-id="74e49-108">Extensions hosted in the Microsoft Edge Addons are uploaded as .zip files.</span></span> <span data-ttu-id="74e49-109">发布过程会自动将 .zip 转换为 crx 文件。</span><span class="sxs-lookup"><span data-stu-id="74e49-109">The publishing process automatically converts the .zip into a .crx file.</span></span>  

<span data-ttu-id="74e49-110">Microsoft Edge Addons 托管规则有两个例外：</span><span class="sxs-lookup"><span data-stu-id="74e49-110">There are two exceptions to the Microsoft Edge Addons hosting rule:</span></span>  

1.  <span data-ttu-id="74e49-111">通过企业策略分配的扩展。</span><span class="sxs-lookup"><span data-stu-id="74e49-111">Extensions that are distributed through the Enterprise policy.</span></span>  
1.  <span data-ttu-id="74e49-112">在开发人员模式下，从本地计算机解压缩扩展目录。</span><span class="sxs-lookup"><span data-stu-id="74e49-112">Unpacked Extension directories from a local machine while in developer mode.</span></span>  

## <span data-ttu-id="74e49-113">更新</span><span class="sxs-lookup"><span data-stu-id="74e49-113">Updating</span></span>  

<span data-ttu-id="74e49-114">Microsoft Edge 浏览器会定期检查已安装扩展和更新的新版本，无需用户干预。</span><span class="sxs-lookup"><span data-stu-id="74e49-114">The Microsoft Edge browser periodically checks for new versions of installed Extensions and updates each without user intervention.</span></span>  

> [!NOTE]
> <span data-ttu-id="74e49-115">将添加计划添加在 Microsoft Edge Addons 上更新扩展的步骤。</span><span class="sxs-lookup"><span data-stu-id="74e49-115">Steps to update an Extension on Microsoft Edge Addons are planned be added.</span></span>  

<!-- image links -->

<!-- links -->  

[MicrosoftStoreExtensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "扩展-Microsoft Edge 预览体验计划 Addons"  

> [!NOTE]
> <span data-ttu-id="74e49-117">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="74e49-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="74e49-118">可在 [此处](https://developer.chrome.com/extensions/hosting)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="74e49-118">The original page is found [here](https://developer.chrome.com/extensions/hosting).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="74e49-120">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="74e49-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
