---
description: 替代功能是 Microsoft Edge DevTools 的"源"工具中的一项功能，允许你将网页资源复制到硬盘驱动器。  刷新网页时，DevTools 不会加载资源，而是将其替换为本地副本。
title: 使用 Microsoft Edge DevTools 使用本地副本替代网页资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 66c0686c166163f1640384d096288af0b530f135
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519434"
---
# <a name="override-webpage-resources-with-local-copies-using-microsoft-edge-devtools"></a><span data-ttu-id="faefb-105">使用 Microsoft Edge DevTools 使用本地副本替代网页资源</span><span class="sxs-lookup"><span data-stu-id="faefb-105">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>  

<span data-ttu-id="faefb-106">有时你需要尝试一些可能的网页修补程序，但你无法访问源文件，或者更改页面需要一个缓慢而复杂的生成过程。</span><span class="sxs-lookup"><span data-stu-id="faefb-106">Sometimes you need to try out some possible fixes for a webpage, but you don't have access to the source files, or changing the page requires a slow and complex build process.</span></span>  <span data-ttu-id="faefb-107">你可以调试和修复 DevTools 中的所有类型问题。</span><span class="sxs-lookup"><span data-stu-id="faefb-107">You may debug and fix all kind of problems in DevTools.</span></span>  <span data-ttu-id="faefb-108">但更改不会保留;刷新本地文件后，所有工作都消失。</span><span class="sxs-lookup"><span data-stu-id="faefb-108">But the changes do not persist; after you refresh the local file, all your work is gone.</span></span>  <span data-ttu-id="faefb-109">源 [工具中的替代][DevToolsSourcesTool] 功能可帮助你解决此问题。</span><span class="sxs-lookup"><span data-stu-id="faefb-109">The Overrides feature in the [Sources][DevToolsSourcesTool] tool helps you solve this problem.</span></span>  

<span data-ttu-id="faefb-110">现在，您可以利用当前网页的资源，并在本地存储该资源。</span><span class="sxs-lookup"><span data-stu-id="faefb-110">You may now take a resource of the current webpage and store it locally.</span></span>  <span data-ttu-id="faefb-111">刷新网页时，浏览器不会从服务器加载资源。</span><span class="sxs-lookup"><span data-stu-id="faefb-111">When you refresh the webpage, the browser does not load the resource from the server.</span></span>  <span data-ttu-id="faefb-112">相反，浏览器会将其替换为你的本地资源副本。</span><span class="sxs-lookup"><span data-stu-id="faefb-112">Instead the browser replaces it with your local copy of the resource.</span></span>  

## <a name="setting-up-your-local-folder-to-store-overrides"></a><span data-ttu-id="faefb-113">将本地文件夹设置为存储替代</span><span class="sxs-lookup"><span data-stu-id="faefb-113">Setting up your local folder to store Overrides</span></span>  

1.  <span data-ttu-id="faefb-114">导航到 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="faefb-114">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="faefb-115">在左侧 **导航器** (窗格中，) " **替代"** 选项卡。 如果未 **显示"覆盖** "选项卡，请选择</span><span class="sxs-lookup"><span data-stu-id="faefb-115">In the **Navigator** pane (on the left), choose the **Overrides** tab.  If the **Overrides** tab is not displayed, choose the</span></span> <code>&#x0226B;</code><!--`≫`--> <span data-ttu-id="faefb-116">图标。</span><span class="sxs-lookup"><span data-stu-id="faefb-116">icon.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="空间不足以显示替代选项的源工具" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             <span data-ttu-id="faefb-118">**空间** 不足以显示替代选项的源工具</span><span class="sxs-lookup"><span data-stu-id="faefb-118">**Sources** tool with not enough space to show the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="选择替代选项" lightbox="../media/javascript-overrides-menu.msft.png":::
             <span data-ttu-id="faefb-120">选择替代选项</span><span class="sxs-lookup"><span data-stu-id="faefb-120">Choose the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="faefb-121">在本地计算机上选择一个文件夹，以存储要替换的资源文件。</span><span class="sxs-lookup"><span data-stu-id="faefb-121">Choose a folder on your local computer to store the resource files that you want to replace.</span></span>  
     *   <span data-ttu-id="faefb-122">若要搜索文件夹，请选择" **+ 选择文件夹"进行替代**。</span><span class="sxs-lookup"><span data-stu-id="faefb-122">To search for a folder, choose **+ Select folder for overrides**.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="选择要用于替代的文件夹" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       <span data-ttu-id="faefb-124">选择要用于替代的文件夹</span><span class="sxs-lookup"><span data-stu-id="faefb-124">Choose a folder to use for overrides</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="faefb-125">DevTools 警告你必须具有对文件夹的完全访问权限，并且不应显示任何敏感信息。</span><span class="sxs-lookup"><span data-stu-id="faefb-125">DevTools warns you that must have full access to the folder and that you should not reveal any sensitive information.</span></span>  <span data-ttu-id="faefb-126">在警告栏上，选择 **"允许** "以授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="faefb-126">On the warning bar, choose **Allow** to grant access.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="授予 DevTools 对文件夹的访问权限" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       <span data-ttu-id="faefb-128">授予 DevTools 对文件夹的访问权限</span><span class="sxs-lookup"><span data-stu-id="faefb-128">Grant DevTools access to folder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="faefb-129">在 **"覆盖"** 选项卡中，"启用本地覆盖"旁边 **会显示一个复选框**。</span><span class="sxs-lookup"><span data-stu-id="faefb-129">In the **Overrides** tab, a checkbox is shown next to **Enable Local Overrides**.</span></span>  <span data-ttu-id="faefb-130">"启用本地覆盖 **"右侧\*\*\*\*是"清除**配置"图标，可用于删除本地覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="faefb-130">To the right of **Enable Local Overrides** is a **Clear configuration** icon that allows you to delete your local overrides settings.</span></span>  <span data-ttu-id="faefb-131">现在，你已完成文件夹设置，并已准备好将实时资源替换为本地资源。</span><span class="sxs-lookup"><span data-stu-id="faefb-131">You are now done setting up your folder and are ready to replace live resources with local ones.</span></span>
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="成功设置替代文件夹" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       <span data-ttu-id="faefb-133">成功设置替代文件夹</span><span class="sxs-lookup"><span data-stu-id="faefb-133">Successful setup of an overrides folder</span></span>  
    :::image-end:::  
    
## <a name="adding-files-to-your-overrides-folder"></a><span data-ttu-id="faefb-134">将文件添加到 Overrides 文件夹</span><span class="sxs-lookup"><span data-stu-id="faefb-134">Adding files to your Overrides folder</span></span>  
  
<span data-ttu-id="faefb-135">若要将文件添加到替代文件夹，请打开 **"元素** "工具并检查网页。</span><span class="sxs-lookup"><span data-stu-id="faefb-135">To add files to your overrides folder, open the **Elements** tool and inspect the webpage.</span></span>  <span data-ttu-id="faefb-136">若要编辑，请选择样式检查器中的 CSS **文件** 的名称。</span><span class="sxs-lookup"><span data-stu-id="faefb-136">To edit, choose the name of the CSS file in the **Styles** inspector.</span></span>  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="在样式检查器中选择文件" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   <span data-ttu-id="faefb-138">在样式检查器 **中选择** 文件</span><span class="sxs-lookup"><span data-stu-id="faefb-138">Choose a file in the **Styles** inspector</span></span>  
:::image-end:::  

<span data-ttu-id="faefb-139">在"**源**"编辑器上，将鼠标悬停在所选文件的文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"保存**以替代"。**</span><span class="sxs-lookup"><span data-stu-id="faefb-139">On the **Sources** editor, hover on the file name of your chosen file, open the contextual menu \(right-click\), and choose **Save for overrides**.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="在"源"编辑器中，将文件的名称添加到替代" lightbox="../media/javascript-overrides-file-name.msft.png":::
   <span data-ttu-id="faefb-141">在 **"源** "编辑器中，将文件的名称添加到替代</span><span class="sxs-lookup"><span data-stu-id="faefb-141">In the **Sources** editor, add the name of the file to overrides</span></span>  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="在上下文菜单上，选择"保存替代"" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   <span data-ttu-id="faefb-143">在上下文菜单上，选择 **"保存替代"**</span><span class="sxs-lookup"><span data-stu-id="faefb-143">On the context menu, choose **Save for overrides**</span></span>  
:::image-end:::  

<span data-ttu-id="faefb-144">该文件存储在替代文件夹中。</span><span class="sxs-lookup"><span data-stu-id="faefb-144">The file is stored in your overrides folder.</span></span>  <span data-ttu-id="faefb-145">验证 DevTools 是否使用具有正确目录结构的文件的 URL 创建名为 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="faefb-145">Verify that DevTools create a folder that is named using the URL of the file with the correct directory structure.</span></span>  <span data-ttu-id="faefb-146">文件存储在内部。</span><span class="sxs-lookup"><span data-stu-id="faefb-146">The file is stored inside.</span></span>  <span data-ttu-id="faefb-147">编辑器中的文件名现在还显示一个紫色点，指示文件是本地文件，而不是实时文件。</span><span class="sxs-lookup"><span data-stu-id="faefb-147">The file name in the editor now also shows a purple dot that indicates that the file is local and not a live one.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="已成功将文件存储在替代文件夹中" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   <span data-ttu-id="faefb-149">已成功将文件存储在替代文件夹中</span><span class="sxs-lookup"><span data-stu-id="faefb-149">Successfully stored the file in your overrides folder</span></span>  
:::image-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="faefb-150">在下面的示例中，现在可以更改网页的样式。</span><span class="sxs-lookup"><span data-stu-id="faefb-150">In the following example, you may now change the styles of the webpage.</span></span>  <span data-ttu-id="faefb-151">若要在文件周围添加红色边框，在 **"** 样式"编辑器上复制以下样式，并将其添加到 body 元素中。</span><span class="sxs-lookup"><span data-stu-id="faefb-151">To add a red border around the file, on the **Styles** editor, copy the following style, and add it to the body element.</span></span>  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="faefb-152">该文件将自动保存在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="faefb-152">The file is automatically saved on your computer.</span></span>  <span data-ttu-id="faefb-153">如果刷新文件，将显示边框，并且不会丢失任何工作。</span><span class="sxs-lookup"><span data-stu-id="faefb-153">If you refresh the file, the border is displayed and none of your work is lost.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="通过编辑替代文件夹中的文件来永久更改网页样式" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         <span data-ttu-id="faefb-155">通过编辑替代文件夹中的文件来永久更改网页样式</span><span class="sxs-lookup"><span data-stu-id="faefb-155">Change webpage styles persistently by editing a file in your overrides folder</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="faefb-156">在" **源** "工具的" **页面** "部分，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击\) ，并将其添加到覆盖。</span><span class="sxs-lookup"><span data-stu-id="faefb-156">On the **Sources** tool, in the **Page** section, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="faefb-157">同样，已位于替代文件夹中的文件在图标上还有一个紫色点。</span><span class="sxs-lookup"><span data-stu-id="faefb-157">Again, files that are already in your overrides folder have a purple dot on the icon.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="从"源"工具中选择文件进行替代" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         <span data-ttu-id="faefb-159">从"源"工具 **中选择** 文件进行替代</span><span class="sxs-lookup"><span data-stu-id="faefb-159">Choose a file from the **Sources** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="faefb-160">或者，在 **"** 网络"工具上，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击\) ，并将其添加到覆盖。</span><span class="sxs-lookup"><span data-stu-id="faefb-160">Alternatively, on the **Network** tool, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="faefb-161">当替代生效时，位于您的计算机而不是实时网页中的文件。</span><span class="sxs-lookup"><span data-stu-id="faefb-161">When overrides are in effect, files that are located on your computer and not from the live webpage.</span></span>  <span data-ttu-id="faefb-162">当替代生效时，在 **"** 网络"工具上，找到文件名旁边的警告图标。</span><span class="sxs-lookup"><span data-stu-id="faefb-162">When overrides are in effect, on the **Network** tool, locate a warning icon next to the file name.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="从网络工具中选择文件进行替代" lightbox="../media/javascript-overrides-network.msft.png":::
         <span data-ttu-id="faefb-164">从网络工具 **中选择** 文件进行替代</span><span class="sxs-lookup"><span data-stu-id="faefb-164">Choose a file from the **Network** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="two-way-interaction-of-overrides"></a><span data-ttu-id="faefb-165">覆盖的双向交互</span><span class="sxs-lookup"><span data-stu-id="faefb-165">Two-way interaction of overrides</span></span>  

<span data-ttu-id="faefb-166">使用 DevTools 的 **"** 源"工具提供的编辑器或要更改文件的任何编辑器。</span><span class="sxs-lookup"><span data-stu-id="faefb-166">Use the editor provided with the **Sources** tool of DevTools or any editor you want to change the files.</span></span>  <span data-ttu-id="faefb-167">更改将跨访问覆盖文件夹中文件的所有产品进行同步。</span><span class="sxs-lookup"><span data-stu-id="faefb-167">Changes are synced across all the products that access the files in the overrides folder.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="faefb-168">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="faefb-168">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "源工具概述 | Microsoft Docs"  
