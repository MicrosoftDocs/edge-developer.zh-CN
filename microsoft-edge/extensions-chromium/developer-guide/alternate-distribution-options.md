---
description: 了解如何使用不使用已验证存储的备用方法分发扩展
title: 分发扩展的备用方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 3b2c72e13488632e2fadea2a7e8eb95888f67170
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343148"
---
# <span data-ttu-id="54b1d-104">备用扩展分发方法</span><span class="sxs-lookup"><span data-stu-id="54b1d-104">Alternate extension distribution methods</span></span>  

<span data-ttu-id="54b1d-105">通常，扩展通过 Microsoft Edge 加载项存储分发。</span><span class="sxs-lookup"><span data-stu-id="54b1d-105">Generally, extensions are distributed through the Microsoft Edge Add-ons store.</span></span> <span data-ttu-id="54b1d-106">在某些情况下，开发人员可能需要使用备用方法分发扩展。</span><span class="sxs-lookup"><span data-stu-id="54b1d-106">There are some scenarios where developers may need to distribute extensions using alternate methods.</span></span> <span data-ttu-id="54b1d-107">例如：</span><span class="sxs-lookup"><span data-stu-id="54b1d-107">For example:</span></span>

1.  <span data-ttu-id="54b1d-108">扩展与其他软件相关联，并且应该与捆绑软件的其余部分一起安装。</span><span class="sxs-lookup"><span data-stu-id="54b1d-108">The extension is associated with other software, and it should be installed together with the rest of the bundled software.</span></span>   
1.  <span data-ttu-id="54b1d-109">网络管理员希望在整个组织中分发扩展。</span><span class="sxs-lookup"><span data-stu-id="54b1d-109">Network administrators want to distribute an extension throughout their organization.</span></span>   

<span data-ttu-id="54b1d-110">未从边缘加载项存储加载的扩展称为外部安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="54b1d-110">Extensions that are not loaded from the Edge Add-ons store are referred to as externally installed extensions.</span></span> <span data-ttu-id="54b1d-111">以下列表提供了分发外部安装的扩展的备用方法。</span><span class="sxs-lookup"><span data-stu-id="54b1d-111">The following list provides alternate methods of distributing externally installed extensions.</span></span> 

*   <span data-ttu-id="54b1d-112">使用 Windows 注册表 (Windows) 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-112">Use the Windows registry (Windows only).</span></span>  
*   <span data-ttu-id="54b1d-113">将首选项 JSON 文件 (macOS 和 Linux) 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-113">Use a preferences JSON file (macOS and Linux).</span></span>  
    
## <span data-ttu-id="54b1d-114">开始之前</span><span class="sxs-lookup"><span data-stu-id="54b1d-114">Before you begin</span></span>  

<span data-ttu-id="54b1d-115">请确保在 Microsoft Edge 加载项存储中发布扩展名，或打包文件，并确保它 `.crx` 已成功安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="54b1d-115">Ensure that you publish your extension in the Microsoft Edge Add-ons store, or package a `.crx` file and ensure that it installs successfully on your computer.</span></span>  <span data-ttu-id="54b1d-116">如果使用 安装 `.crx` 文件， `update_URL` 请确保可以导航到该 URL 的扩展名。</span><span class="sxs-lookup"><span data-stu-id="54b1d-116">If you install the `.crx` file using the `update_URL`, ensure you can navigate to your extension at that URL.</span></span>  

<span data-ttu-id="54b1d-117">此外，请确保你拥有以下信息。</span><span class="sxs-lookup"><span data-stu-id="54b1d-117">Also, ensure that you have the following information.</span></span>    

1.  <span data-ttu-id="54b1d-118">文件的文件 `.crx` 路径或扩展 `update_URL` 名。</span><span class="sxs-lookup"><span data-stu-id="54b1d-118">The file path of the `.crx` file, or the `update_URL` of your extension.</span></span>
1.  <span data-ttu-id="54b1d-119">扩展的版本。</span><span class="sxs-lookup"><span data-stu-id="54b1d-119">The version of your extension.</span></span>  <span data-ttu-id="54b1d-120">版本信息可在清单文件中提供，或在加载打包的扩展后在 Microsoft Edge `edge://extensions` 中提供。</span><span class="sxs-lookup"><span data-stu-id="54b1d-120">The version information is available in your manifest file, or in Microsoft Edge at `edge://extensions` after you load the packed extension.</span></span>   
1.  <span data-ttu-id="54b1d-121">扩展的 ID。</span><span class="sxs-lookup"><span data-stu-id="54b1d-121">The ID of your extension.</span></span>  <span data-ttu-id="54b1d-122">在加载打包的扩展后，Microsoft Edge 中会提供 `edge://extensions` ID 信息。</span><span class="sxs-lookup"><span data-stu-id="54b1d-122">The ID information is available in Microsoft Edge at `edge://extensions` after you load the packed extension.</span></span>  

> [!NOTE] 
> <span data-ttu-id="54b1d-123">以下示例用作 `1.0` 版本和 `aaaaaaaaaabbbbbbbbbbcccccccccc` ID。</span><span class="sxs-lookup"><span data-stu-id="54b1d-123">The following examples use `1.0` as the version, and `aaaaaaaaaabbbbbbbbbbcccccccccc` for the ID.</span></span>  

## <span data-ttu-id="54b1d-124">使用 Windows 注册表 (Windows 注册表) </span><span class="sxs-lookup"><span data-stu-id="54b1d-124">Use the Windows registry (Windows only)</span></span>  

<span data-ttu-id="54b1d-125">若要使用 Windows 注册表分发扩展，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="54b1d-125">To distribute your extension using the Windows registry, perform the following steps.</span></span>

1.  <span data-ttu-id="54b1d-126">在注册表中查找或创建以下项：</span><span class="sxs-lookup"><span data-stu-id="54b1d-126">Find or create the following key in the registry:</span></span>  
    *   <span data-ttu-id="54b1d-127">32 位 Windows：  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions` .</span><span class="sxs-lookup"><span data-stu-id="54b1d-127">32-bit Windows:  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`.</span></span>  
    *   <span data-ttu-id="54b1d-128">64 位 Windows：  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions` .</span><span class="sxs-lookup"><span data-stu-id="54b1d-128">64-bit Windows:  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`.</span></span>  
1.  <span data-ttu-id="54b1d-129">在扩展名下新建一个密钥或\*\*\*\* 文件夹，其名称与扩展的 ID 相同。</span><span class="sxs-lookup"><span data-stu-id="54b1d-129">Create a new key, or folder, under **Extensions** with the same name as the ID of your extension.</span></span> <span data-ttu-id="54b1d-130">例如，使用名称创建键 `aaaaaaaaaabbbbbbbbbbcccccccccc` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-130">For example, create the key with the name `aaaaaaaaaabbbbbbbbbbcccccccccc`.</span></span>  
1.  <span data-ttu-id="54b1d-131">在 **Extensions** 键中，创建 `update_url` 属性，将值设置为 `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-131">In the **Extensions** key, create the `update_url` property, and set the value to `https://edge.microsoft.com/extensionwebstorebase/v1/crx`.</span></span>  <span data-ttu-id="54b1d-132">该属性指向 Microsoft Edge 加载项存储 `update_url` `.crx` 中扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="54b1d-132">The `update_url` property points to the `.crx` file of your extension in the Microsoft Edge Add-ons store.</span></span>  

    ```json
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="54b1d-133">如果要从 Chrome Web 应用商店安装扩展，将值 `update_url` 设置为 `https://clients2.google.com/service/update2/crx` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-133">If you want to install an extension from the Chrome Web Store, set the value of `update_url` to `https://clients2.google.com/service/update2/crx`.</span></span>  
  
1.  <span data-ttu-id="54b1d-134">通过导航到验证你的扩展是否列在 Microsoft Edge 中 `edge://extensions` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-134">Verify that your extension is listed in Microsoft Edge by navigating to `edge://extensions`.</span></span>  

## <span data-ttu-id="54b1d-135">将首选项 JSON 文件 (macOS 和 Linux) </span><span class="sxs-lookup"><span data-stu-id="54b1d-135">Use a preferences JSON file (macOS and Linux)</span></span>  

<span data-ttu-id="54b1d-136">若要使用首选项 JSON 文件分发扩展名，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="54b1d-136">To distribute your extension using a preferences JSON file, perform the following steps.</span></span>

1.  <span data-ttu-id="54b1d-137">使用 Linux 时，请确保扩展文件在将安装扩展的计算机 `.crx` 中可用。</span><span class="sxs-lookup"><span data-stu-id="54b1d-137">When using Linux, ensure your `.crx` extension file is available on the machine that the extension will be installed on.</span></span> <span data-ttu-id="54b1d-138">将扩展文件复制到本地目录，或使用计算机可访问的网络 `.crx` 共享。</span><span class="sxs-lookup"><span data-stu-id="54b1d-138">Copy the `.crx` extension file to a local directory, or use a  network share that is reachable from the machine.</span></span> 
1.  <span data-ttu-id="54b1d-139">创建一个 JSON 文件，该文件的名称对应于扩展名的 ID。</span><span class="sxs-lookup"><span data-stu-id="54b1d-139">Create a JSON file where the name of the file corresponds to the ID of your extension.</span></span> <span data-ttu-id="54b1d-140">例如，创建具有文件名的 JSON 文件 `aaaaaaaaaabbbbbbbbbbcccccccccc.json` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-140">For example, create a JSON file with the file name `aaaaaaaaaabbbbbbbbbbcccccccccc.json`.</span></span>  
1.  <span data-ttu-id="54b1d-141">根据您的操作系统，将 JSON 文件保存到以下文件夹之一。</span><span class="sxs-lookup"><span data-stu-id="54b1d-141">Depending on your operating system, save the JSON file to one of the following folders.</span></span>   
    *   **<span data-ttu-id="54b1d-142">macOS</span><span class="sxs-lookup"><span data-stu-id="54b1d-142">macOS</span></span>**  
        *   <span data-ttu-id="54b1d-143">特定于用户：</span><span class="sxs-lookup"><span data-stu-id="54b1d-143">User specific:</span></span> `~USERNAME/Library/Application Support/Microsoft Edge/External Extensions/`  
        *   <span data-ttu-id="54b1d-144">所有用户：</span><span class="sxs-lookup"><span data-stu-id="54b1d-144">All users:</span></span> `/Library/Application Support/Microsoft/Edge/External Extensions/`  
        
        <span data-ttu-id="54b1d-145">若要防止未经授权的用户为所有用户安装扩展，请确保扩展文件是只读的。</span><span class="sxs-lookup"><span data-stu-id="54b1d-145">To prevent unauthorized users from installing extensions for all users, ensure your extension file is read only.</span></span> <span data-ttu-id="54b1d-146">此外，请确保满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="54b1d-146">Additionally, ensure that the following conditions are met:</span></span>
        
        *   <span data-ttu-id="54b1d-147">路径中的每个目录归用户根所有。</span><span class="sxs-lookup"><span data-stu-id="54b1d-147">Every directory in the path is owned by the user root.</span></span>  
        *   <span data-ttu-id="54b1d-148">路径中的每个目录都分配给或 `admin` `wheel` 组。</span><span class="sxs-lookup"><span data-stu-id="54b1d-148">Every directory in the path is assigned to the `admin` or `wheel` group.</span></span>  
        *   <span data-ttu-id="54b1d-149">路径中的每个目录都不可写入。</span><span class="sxs-lookup"><span data-stu-id="54b1d-149">Every directory in the path isn't world writable.</span></span>  
        *   <span data-ttu-id="54b1d-150">路径还必须没有符号链接。</span><span class="sxs-lookup"><span data-stu-id="54b1d-150">The path must also be free of symbolic links.</span></span>  
        
    *   **<span data-ttu-id="54b1d-151">Linux</span><span class="sxs-lookup"><span data-stu-id="54b1d-151">Linux</span></span>**  
        *   <span data-ttu-id="54b1d-152">特定于用户：</span><span class="sxs-lookup"><span data-stu-id="54b1d-152">User specific:</span></span> `~/.config/microsoft-edge/External Extensions/`  
        *   <span data-ttu-id="54b1d-153">所有用户：</span><span class="sxs-lookup"><span data-stu-id="54b1d-153">All users:</span></span> `/usr/share/microsoft-edge/extensions/`  
1.  <span data-ttu-id="54b1d-154">根据您的方案，将相应的代码复制到 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="54b1d-154">Depending on your scenario, copy the appropriate code that follows to your JSON file.</span></span> 
    *   <span data-ttu-id="54b1d-155">仅适用于 Linux。</span><span class="sxs-lookup"><span data-stu-id="54b1d-155">Applies to Linux only.</span></span> <span data-ttu-id="54b1d-156">如果从文件安装，则使用 和 指定位置和 `external_crx` 版本 `external_version` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-156">If you install from a file, specify the location and version using `external_crx` and `external_version`.</span></span>  
            
        ```json
        {
            "external_crx": "/home/share/extension.crx",
            "external_version": "1.0"
        }
        ```  

    *   <span data-ttu-id="54b1d-157">适用于 macOS 和 Linux。</span><span class="sxs-lookup"><span data-stu-id="54b1d-157">Applies to macOS and Linux.</span></span> <span data-ttu-id="54b1d-158">如果从安装位置 `update_URL` 安装，则使用 指定更新 `external_update_url` URL。</span><span class="sxs-lookup"><span data-stu-id="54b1d-158">If you install from an `update_URL`, specify the update URL using `external_update_url`.</span></span> 
        
        <span data-ttu-id="54b1d-159">仅在 Linux 上从本地文件安装时，将以下代码 `.crx` 复制到 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="54b1d-159">Copy the following code to your JSON file when installing from local `.crx` files on Linux only.</span></span>  
    
        ```json
        {
            "external_update_url": "http://myhost.com/mytestextension/updates.xml"
        }
        ```  
 
    *  <span data-ttu-id="54b1d-160">从 macOS 和 Linux 上的 Microsoft Edge 加载项存储安装时，将以下代码复制到 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="54b1d-160">Copy the following code to your JSON file when installing from the Microsoft Edge Add-ons store on macOS and Linux.</span></span>
    
        ```json
        {
            "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
        }
        ```  
    
1.  <span data-ttu-id="54b1d-161">若要安装特定区域设置扩展，使用 列出受支持的区域设置 `supported_locale` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-161">To install extensions for specific locales, list the supported locales using `supported_locale`.</span></span>  <span data-ttu-id="54b1d-162">还可以指定父区域设置，为使用该父级的所有语言区域设置安装扩展。</span><span class="sxs-lookup"><span data-stu-id="54b1d-162">You may also specify parent locales to install your extension for all language locales that use that parent.</span></span> <span data-ttu-id="54b1d-163">例如，使用父区域设置时，扩展会针对所有英语区域设置（如 `en` `en-US` ， `en-GB` 等）进行安装。</span><span class="sxs-lookup"><span data-stu-id="54b1d-163">For example, when using the parent locale `en`, your extension installs for all English locales, such as `en-US`, `en-GB`, and so on.</span></span>  <span data-ttu-id="54b1d-164">当用户在浏览器中更改其区域设置时，将卸载外部安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="54b1d-164">When users change their locale in their browser, externally installed extensions are uninstalled.</span></span>  <span data-ttu-id="54b1d-165">若要安装任何区域设置扩展，请不要使用 `supported_locales` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-165">To install your extension for any locale, do not use `supported_locales`.</span></span>  

    ```json
    {
        "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx",
        "supported_locales": [ "en", "fr", "de" ]
    }
    ```  

1.  <span data-ttu-id="54b1d-166">通过导航到验证你的扩展是否安装在 Microsoft Edge 中 `edge://extensions` 。</span><span class="sxs-lookup"><span data-stu-id="54b1d-166">Verify that your extension is installed in Microsoft Edge by navigating to `edge://extensions`.</span></span>  

## <span data-ttu-id="54b1d-167">更新和卸载外部安装的扩展</span><span class="sxs-lookup"><span data-stu-id="54b1d-167">Update and uninstall externally installed extensions</span></span>

<span data-ttu-id="54b1d-168">每次浏览器启动时，Microsoft Edge 会扫描注册表中的元数据条目，并更改外部安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="54b1d-168">Microsoft Edge scans the metadata entries in the registry each time the browser starts, and makes any changes to the externally installed extensions.</span></span>  

<span data-ttu-id="54b1d-169">若要将扩展更新到新版本，请更新清单文件中的版本，然后在注册表中更新版本。</span><span class="sxs-lookup"><span data-stu-id="54b1d-169">To update your extension to a new version, update the version in the manifest file, and then update the version in the registry.</span></span>  

<span data-ttu-id="54b1d-170">您可能需要卸载外部安装的扩展，这些扩展作为以前安装在计算机上的软件捆绑包的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="54b1d-170">You may need to uninstall externally installed extensions, which were installed as part of a bundle of software that was previously installed on the machine.</span></span>  <span data-ttu-id="54b1d-171">若要卸载扩展，请删除首选项 JSON 文件或从注册表中删除项。</span><span class="sxs-lookup"><span data-stu-id="54b1d-171">To uninstall your extension, remove your preferences JSON file or remove the key from the registry.</span></span>   

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="54b1d-172">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="54b1d-172">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  <span data-ttu-id="54b1d-173">原始页面位于 [此处](https://developer.chrome.com/apps/external_extensions)。</span><span class="sxs-lookup"><span data-stu-id="54b1d-173">The original page is found [here](https://developer.chrome.com/apps/external_extensions).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="54b1d-175">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="54b1d-175">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
