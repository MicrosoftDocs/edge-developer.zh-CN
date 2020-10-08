---
description: 通过经验证的应用商店以外的机制分配扩展的过程
title: 分发扩展的备用方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: e28a84fd75ad1ac0be2000a22c26371ca73d0293
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015693"
---
# <span data-ttu-id="6800f-104">分发扩展的备用方法</span><span class="sxs-lookup"><span data-stu-id="6800f-104">Alternate Method of Distributing Extension</span></span>  

<span data-ttu-id="6800f-105">如果你是要为其他软件的安装过程的一部分分发扩展的开发人员，或者是希望在其整个组织中分发扩展的网络管理员，Microsoft Edge 支持以下扩展安装方法：</span><span class="sxs-lookup"><span data-stu-id="6800f-105">If you are a developer who wants to distribute an Extension as part of the installation process for other software, or a network admin that want to distribute an Extension throughout their organization, Microsoft Edge supports the following Extension installation methods:</span></span>  

*   **<span data-ttu-id="6800f-106">仅使用 Windows 注册表 \ (Windows ) </span><span class="sxs-lookup"><span data-stu-id="6800f-106">Using the Windows registry \(Windows only\)</span></span>**  

<span data-ttu-id="6800f-107">Microsoft Edge 支持安装托管的扩展 `update_URL` 。</span><span class="sxs-lookup"><span data-stu-id="6800f-107">Microsoft Edge supports installing an Extension hosted at an `update_URL`.</span></span>  <span data-ttu-id="6800f-108">在 Windows 上， `update_URL` 必须指向 Microsoft Edge Addons catalog \ (Microsoft Edge Addons \ ) 必须在其中托管扩展的位置。</span><span class="sxs-lookup"><span data-stu-id="6800f-108">On Windows, the `update_URL` must point to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\) where the Extension must be hosted.</span></span>  

> [!NOTE]
> <span data-ttu-id="6800f-109">通过 macOS 的首选项 json 文件进行扩展的外部安装</span><span class="sxs-lookup"><span data-stu-id="6800f-109">External installation of Extension via a preferences json file for macOS</span></span> <!--and Linux--> <span data-ttu-id="6800f-110">尚不支持。</span><span class="sxs-lookup"><span data-stu-id="6800f-110">are not supported yet.</span></span>  <span data-ttu-id="6800f-111">此功能支持将很快推出。</span><span class="sxs-lookup"><span data-stu-id="6800f-111">This feature support will soon be available.</span></span>

## <span data-ttu-id="6800f-112">使用 Windows 注册表</span><span class="sxs-lookup"><span data-stu-id="6800f-112">Using the Windows registry</span></span>  

<span data-ttu-id="6800f-113">首先，在 Microsoft Edge Addons 中发布扩展，或将 crx 文件打包，并确保它成功安装。</span><span class="sxs-lookup"><span data-stu-id="6800f-113">First, publish the Extension in the Microsoft Edge Addons, or package a .crx file and make sure that it installs successfully.</span></span>  

<span data-ttu-id="6800f-114">通过 windows 中的注册表安装扩展的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="6800f-114">The steps to install Extension via registry in windows are:</span></span>  

*   <span data-ttu-id="6800f-115">在注册表中查找或创建以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="6800f-115">Find or create the following key in the registry:</span></span>  
    *   <span data-ttu-id="6800f-116">32位 Windows：</span><span class="sxs-lookup"><span data-stu-id="6800f-116">32-bit Windows:</span></span>  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`  
    *   <span data-ttu-id="6800f-117">64位 Windows：</span><span class="sxs-lookup"><span data-stu-id="6800f-117">64-bit Windows:</span></span>  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`  
*   <span data-ttu-id="6800f-118">创建一个新的键 \ (文件夹 \ ) ，使用与扩展名 \ 的 ID 相同的扩展名 \ (例如， `aaaaaaaaaabbbbbbbbbbcccccccccc` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="6800f-118">Create a new key \(folder\) under the Extensions key with the same name as the ID of your Extension \(for example, `aaaaaaaaaabbbbbbbbbbcccccccccc`\).</span></span>  
*   <span data-ttu-id="6800f-119">在你的扩展键中，创建一个属性， `update_url` 并将其设置为值： `https://edge.microsoft.com/extensionwebstorebase/v1/crx` ，\ (这一点指向 Microsoft Edge Addons \ ) 中的扩展 crx。</span><span class="sxs-lookup"><span data-stu-id="6800f-119">In your Extension key, create a property, `update_url`, and set it to the value: `https://edge.microsoft.com/extensionwebstorebase/v1/crx`,  \(this points to the crx of your extension in the Microsoft Edge Addons\).</span></span> <span data-ttu-id="6800f-120">如果想要从 Chrome Web Store 安装扩展，请提供 Chrome Web Store 更新 URL `https://clients2.google.com/service/update2/crx` 。</span><span class="sxs-lookup"><span data-stu-id="6800f-120">If you want to install an extension from the Chrome Web Store, please provide the Chrome Web Store update URL, `https://clients2.google.com/service/update2/crx`.</span></span>  
    
    ```javascript
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
*   <span data-ttu-id="6800f-121">启动浏览器并转到 `edge://extensions` ; 你应该看到列出的扩展名。</span><span class="sxs-lookup"><span data-stu-id="6800f-121">Launch the browser and go to `edge://extensions`; you should see the extension listed.</span></span>  

## <span data-ttu-id="6800f-122">更新和卸载</span><span class="sxs-lookup"><span data-stu-id="6800f-122">Updating and uninstalling</span></span>  

<span data-ttu-id="6800f-123">每次浏览器启动时，Microsoft Edge 将扫描注册表中的元数据条目，并对已安装的外部扩展进行任何必要的更改。</span><span class="sxs-lookup"><span data-stu-id="6800f-123">Microsoft Edge scans the metadata entries in the registry each time the browser starts, and makes any necessary changes to the installed external extensions.</span></span>  

<span data-ttu-id="6800f-124">若要将扩展更新到新版本，请更新文件，然后更新注册表中的版本。</span><span class="sxs-lookup"><span data-stu-id="6800f-124">To update your extension to a new version, update the file, and then update the version in the registry.</span></span>  

<span data-ttu-id="6800f-125">若要卸载扩展 \ (例如，如果软件已卸载 \ ) ，请从注册表中删除您的首选项文件 \ (`aaaaaaaaaabbbbbbbbbbcccccccccc.json` \ ) 或元数据。</span><span class="sxs-lookup"><span data-stu-id="6800f-125">To uninstall your extension \(for example, if your software is uninstalled\), remove your preference file \(`aaaaaaaaaabbbbbbbbbbcccccccccc.json`\) or the metadata from the registry.</span></span>  

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="6800f-126">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6800f-126">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6800f-127">可在 [此处](https://developer.chrome.com/apps/external_extensions)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="6800f-127">The original page is found [here](https://developer.chrome.com/apps/external_extensions).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6800f-129">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6800f-129">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
