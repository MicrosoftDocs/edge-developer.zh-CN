---
description: The process of distributing extension by mechanism other than verified stores
title: Alternate Method of Distributing Extension
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, extensions development, browser extensions, addons, partner center, developer
ms.openlocfilehash: e28a84fd75ad1ac0be2000a22c26371ca73d0293
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015693"
---
# <span data-ttu-id="1de8e-104">Alternate Method of Distributing Extension</span><span class="sxs-lookup"><span data-stu-id="1de8e-104">Alternate Method of Distributing Extension</span></span>  

<span data-ttu-id="1de8e-105">If you are a developer who wants to distribute an Extension as part of the installation process for other software, or a network admin that want to distribute an Extension throughout their organization, Microsoft Edge supports the following Extension installation methods:</span><span class="sxs-lookup"><span data-stu-id="1de8e-105">If you are a developer who wants to distribute an Extension as part of the installation process for other software, or a network admin that want to distribute an Extension throughout their organization, Microsoft Edge supports the following Extension installation methods:</span></span>  

*   **<span data-ttu-id="1de8e-106">Using the Windows registry \(Windows only\)</span><span class="sxs-lookup"><span data-stu-id="1de8e-106">Using the Windows registry \(Windows only\)</span></span>**  

<span data-ttu-id="1de8e-107">Microsoft Edge supports installing an Extension hosted at an `update_URL`.</span><span class="sxs-lookup"><span data-stu-id="1de8e-107">Microsoft Edge supports installing an Extension hosted at an `update_URL`.</span></span>  <span data-ttu-id="1de8e-108">On Windows, the `update_URL` must point to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\) where the Extension must be hosted.</span><span class="sxs-lookup"><span data-stu-id="1de8e-108">On Windows, the `update_URL` must point to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\) where the Extension must be hosted.</span></span>  

> [!NOTE]
> <span data-ttu-id="1de8e-109">External installation of Extension via a preferences json file for macOS</span><span class="sxs-lookup"><span data-stu-id="1de8e-109">External installation of Extension via a preferences json file for macOS</span></span> <!--and Linux--> <span data-ttu-id="1de8e-110">are not supported yet.</span><span class="sxs-lookup"><span data-stu-id="1de8e-110">are not supported yet.</span></span>  <span data-ttu-id="1de8e-111">This feature support will soon be available.</span><span class="sxs-lookup"><span data-stu-id="1de8e-111">This feature support will soon be available.</span></span>

## <span data-ttu-id="1de8e-112">Using the Windows registry</span><span class="sxs-lookup"><span data-stu-id="1de8e-112">Using the Windows registry</span></span>  

<span data-ttu-id="1de8e-113">First, publish the Extension in the Microsoft Edge Addons, or package a .crx file and make sure that it installs successfully.</span><span class="sxs-lookup"><span data-stu-id="1de8e-113">First, publish the Extension in the Microsoft Edge Addons, or package a .crx file and make sure that it installs successfully.</span></span>  

<span data-ttu-id="1de8e-114">The steps to install Extension via registry in windows are:</span><span class="sxs-lookup"><span data-stu-id="1de8e-114">The steps to install Extension via registry in windows are:</span></span>  

*   <span data-ttu-id="1de8e-115">Find or create the following key in the registry:</span><span class="sxs-lookup"><span data-stu-id="1de8e-115">Find or create the following key in the registry:</span></span>  
    *   <span data-ttu-id="1de8e-116">32-bit Windows:</span><span class="sxs-lookup"><span data-stu-id="1de8e-116">32-bit Windows:</span></span>  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`  
    *   <span data-ttu-id="1de8e-117">64-bit Windows:</span><span class="sxs-lookup"><span data-stu-id="1de8e-117">64-bit Windows:</span></span>  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`  
*   <span data-ttu-id="1de8e-118">Create a new key \(folder\) under the Extensions key with the same name as the ID of your Extension \(for example, `aaaaaaaaaabbbbbbbbbbcccccccccc`\).</span><span class="sxs-lookup"><span data-stu-id="1de8e-118">Create a new key \(folder\) under the Extensions key with the same name as the ID of your Extension \(for example, `aaaaaaaaaabbbbbbbbbbcccccccccc`\).</span></span>  
*   <span data-ttu-id="1de8e-119">In your Extension key, create a property, `update_url`, and set it to the value: `https://edge.microsoft.com/extensionwebstorebase/v1/crx`,  \(this points to the crx of your extension in the Microsoft Edge Addons\).</span><span class="sxs-lookup"><span data-stu-id="1de8e-119">In your Extension key, create a property, `update_url`, and set it to the value: `https://edge.microsoft.com/extensionwebstorebase/v1/crx`,  \(this points to the crx of your extension in the Microsoft Edge Addons\).</span></span> <span data-ttu-id="1de8e-120">If you want to install an extension from the Chrome Web Store, please provide the Chrome Web Store update URL, `https://clients2.google.com/service/update2/crx`.</span><span class="sxs-lookup"><span data-stu-id="1de8e-120">If you want to install an extension from the Chrome Web Store, please provide the Chrome Web Store update URL, `https://clients2.google.com/service/update2/crx`.</span></span>  
    
    ```javascript
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
*   <span data-ttu-id="1de8e-121">Launch the browser and go to `edge://extensions`; you should see the extension listed.</span><span class="sxs-lookup"><span data-stu-id="1de8e-121">Launch the browser and go to `edge://extensions`; you should see the extension listed.</span></span>  

## <span data-ttu-id="1de8e-122">Updating and uninstalling</span><span class="sxs-lookup"><span data-stu-id="1de8e-122">Updating and uninstalling</span></span>  

<span data-ttu-id="1de8e-123">Microsoft Edge scans the metadata entries in the registry each time the browser starts, and makes any necessary changes to the installed external extensions.</span><span class="sxs-lookup"><span data-stu-id="1de8e-123">Microsoft Edge scans the metadata entries in the registry each time the browser starts, and makes any necessary changes to the installed external extensions.</span></span>  

<span data-ttu-id="1de8e-124">To update your extension to a new version, update the file, and then update the version in the registry.</span><span class="sxs-lookup"><span data-stu-id="1de8e-124">To update your extension to a new version, update the file, and then update the version in the registry.</span></span>  

<span data-ttu-id="1de8e-125">To uninstall your extension \(for example, if your software is uninstalled\), remove your preference file \(`aaaaaaaaaabbbbbbbbbbcccccccccc.json`\) or the metadata from the registry.</span><span class="sxs-lookup"><span data-stu-id="1de8e-125">To uninstall your extension \(for example, if your software is uninstalled\), remove your preference file \(`aaaaaaaaaabbbbbbbbbbcccccccccc.json`\) or the metadata from the registry.</span></span>  

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="1de8e-126">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1de8e-126">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1de8e-127">The original page is found [here](https://developer.chrome.com/apps/external_extensions).</span><span class="sxs-lookup"><span data-stu-id="1de8e-127">The original page is found [here](https://developer.chrome.com/apps/external_extensions).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="1de8e-129">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1de8e-129">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
