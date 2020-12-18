---
description: 替代功能是 Microsoft Edge DevTools 的源工具中的一项功能，允许你将网页资源复制到硬盘驱动器。  刷新网页时，DevTools 不会加载资源，而是将其替换为本地副本。
title: 使用 Microsoft Edge DevTools 使用本地副本替代网页资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 7f273f89708e0948e68cd2c7ba79cefb6d7e167c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230962"
---
# <span data-ttu-id="bd63f-105">使用 Microsoft Edge DevTools 使用本地副本替代网页资源</span><span class="sxs-lookup"><span data-stu-id="bd63f-105">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>  

<span data-ttu-id="bd63f-106">有时，你需要修复网页上无法访问的问题，或者修复涉及缓慢而复杂的生成过程。</span><span class="sxs-lookup"><span data-stu-id="bd63f-106">Sometimes you need to fix a problem on a webpage that you do not have access to or fixes involve a slow and complex build process.</span></span>  <span data-ttu-id="bd63f-107">你可以调试并修复 DevTools 中的所有类型问题。</span><span class="sxs-lookup"><span data-stu-id="bd63f-107">You may debug and fix all kind of problems in DevTools.</span></span> <span data-ttu-id="bd63f-108">但问题是更改不会持续存在。</span><span class="sxs-lookup"><span data-stu-id="bd63f-108">But the problem is the changes do not persist.</span></span>  <span data-ttu-id="bd63f-109">刷新文件后，所有工作都消失。</span><span class="sxs-lookup"><span data-stu-id="bd63f-109">After you refresh the file, all your work is gone.</span></span>  

<span data-ttu-id="bd63f-110">"源 ["工具中的][DevToolsSourcesTool] "覆盖"功能可帮助你解决此问题。</span><span class="sxs-lookup"><span data-stu-id="bd63f-110">The Overrides feature in the [Sources][DevToolsSourcesTool] tool helps you solve this problem.</span></span>  

<span data-ttu-id="bd63f-111">现在，您可以利用当前网页的资源，并在本地存储该资源。</span><span class="sxs-lookup"><span data-stu-id="bd63f-111">You may now take a resource of the current webpage and store it locally.</span></span>  <span data-ttu-id="bd63f-112">刷新网页时，浏览器不会从服务器加载资源。</span><span class="sxs-lookup"><span data-stu-id="bd63f-112">When you refresh the webpage, the browser does not load the resource from the server.</span></span>  <span data-ttu-id="bd63f-113">相反，浏览器会将其替换为你的本地资源副本。</span><span class="sxs-lookup"><span data-stu-id="bd63f-113">Instead the browser replaces it with your local copy of the resource.</span></span>  

## <span data-ttu-id="bd63f-114">将本地文件夹设置为存储替代</span><span class="sxs-lookup"><span data-stu-id="bd63f-114">Setting up your local folder to store Overrides</span></span>  

1.  <span data-ttu-id="bd63f-115">在 **"源** "工具中，在左侧找到多个部分。</span><span class="sxs-lookup"><span data-stu-id="bd63f-115">In the **Sources** tool, find several sections on the left-hand side.</span></span>  <span data-ttu-id="bd63f-116">如果未 **显示"替代"** 选项，请选择</span><span class="sxs-lookup"><span data-stu-id="bd63f-116">If the **Overrides** option is not displayed, choose the</span></span> <code>&#x0226B;</code><!--`≫`--> <span data-ttu-id="bd63f-117">图标到达那里。</span><span class="sxs-lookup"><span data-stu-id="bd63f-117">icon to get there.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="显示替代选项的空间不足的源工具" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             <span data-ttu-id="bd63f-119">**显示** 替代选项的空间不足的源工具</span><span class="sxs-lookup"><span data-stu-id="bd63f-119">**Sources** tool with not enough space to show the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="选择替代选项" lightbox="../media/javascript-overrides-menu.msft.png":::
             <span data-ttu-id="bd63f-121">选择替代选项</span><span class="sxs-lookup"><span data-stu-id="bd63f-121">Choose the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="bd63f-122">选择" **覆盖"选项** 后，您必须在本地计算机上选择一个文件夹来存储要替换的资源文件。</span><span class="sxs-lookup"><span data-stu-id="bd63f-122">After you choose the **Overrides** option, you must choose a folder on your local computer to store the resource files that you want to replace.</span></span>  <span data-ttu-id="bd63f-123">为 **替代选择 + Select 文件夹** 以搜索文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd63f-123">Choose the **+ Select folder for overrides** to search for a folder.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="选择要用于替代的文件夹" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       <span data-ttu-id="bd63f-125">选择要用于替代的文件夹</span><span class="sxs-lookup"><span data-stu-id="bd63f-125">Choose a folder to use for overrides</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="bd63f-126">DevTools 警告您必须具有对文件夹的完全访问权限，并且不应显示任何敏感信息。</span><span class="sxs-lookup"><span data-stu-id="bd63f-126">DevTools warns you that must have full access to the folder and that you should not reveal any sensitive information.</span></span>  <span data-ttu-id="bd63f-127">在警告栏上，选择 **"允许** 授予访问权限"。</span><span class="sxs-lookup"><span data-stu-id="bd63f-127">On the warning bar, choose **Allow** to grant access.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="授予 DevTools 对文件夹的访问权限" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       <span data-ttu-id="bd63f-129">授予 DevTools 文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="bd63f-129">Grant DevTools access to folder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="bd63f-130">在 **"覆盖"** 窗格中，应在替代文件夹旁边显示一个 `Enable Local Overrides` 复选框。</span><span class="sxs-lookup"><span data-stu-id="bd63f-130">In the **Overrides** pane, a checkbox should be displayed next to `Enable Local Overrides` and your overrides folder.</span></span>  <span data-ttu-id="bd63f-131">旁边会显示一个图标，允许你删除本地覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="bd63f-131">An icon is displayed next to it that allows you to delete your local overrides settings.</span></span>  <span data-ttu-id="bd63f-132">现在，你已完成文件夹设置并准备好将实时资源替换为本地资源。</span><span class="sxs-lookup"><span data-stu-id="bd63f-132">You are now done setting up your folder and ready to replace live resources with local ones.</span></span>
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="成功设置替代文件夹" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       <span data-ttu-id="bd63f-134">成功设置替代文件夹</span><span class="sxs-lookup"><span data-stu-id="bd63f-134">Successful set up of an overrides folder</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="bd63f-135">将文件添加到 Overrides 文件夹</span><span class="sxs-lookup"><span data-stu-id="bd63f-135">Adding files to your Overrides folder</span></span>  
  
<span data-ttu-id="bd63f-136">若要将文件添加到替代文件夹，请打开 **Elements** 工具并检查网页。</span><span class="sxs-lookup"><span data-stu-id="bd63f-136">To add files to your overrides folder, open the **Elements** tool and inspect the webpage.</span></span>  <span data-ttu-id="bd63f-137">若要编辑，请选择样式检查器中的 CSS **文件** 的名称。</span><span class="sxs-lookup"><span data-stu-id="bd63f-137">To edit, choose the name of the CSS file in the **Styles** inspector.</span></span>  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="在样式检查器中选择文件" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   <span data-ttu-id="bd63f-139">在样式检查器 **中选择** 文件</span><span class="sxs-lookup"><span data-stu-id="bd63f-139">Choose a file in the **Styles** inspector</span></span>  
:::image-end:::  

<span data-ttu-id="bd63f-140">在源**编辑器**上，将鼠标悬停在所选文件的文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"保存**替代"。**</span><span class="sxs-lookup"><span data-stu-id="bd63f-140">On the **Sources** editor, hover on the file name of your chosen file, open the contextual menu \(right-click\), and choose **Save for overrides**.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="在"源"编辑器中，添加要覆盖的文件的名称" lightbox="../media/javascript-overrides-file-name.msft.png":::
   <span data-ttu-id="bd63f-142">在 **"源** "编辑器中，添加要覆盖的文件的名称</span><span class="sxs-lookup"><span data-stu-id="bd63f-142">In the **Sources** editor, add the name of the file to overrides</span></span>  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="在上下文菜单上，选择"保存替代"" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   <span data-ttu-id="bd63f-144">在上下文菜单上，选择 **"保存替代"**</span><span class="sxs-lookup"><span data-stu-id="bd63f-144">On the context menu, choose **Save for overrides**</span></span>  
:::image-end:::  

<span data-ttu-id="bd63f-145">该文件存储在替代文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bd63f-145">The file is stored in your overrides folder.</span></span>  <span data-ttu-id="bd63f-146">验证 DevTools 是否创建使用具有正确目录结构的文件 URL 命名的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd63f-146">Verify that DevTools create a folder that is named using the URL of the file with the correct directory structure.</span></span>  <span data-ttu-id="bd63f-147">文件存储在内部。</span><span class="sxs-lookup"><span data-stu-id="bd63f-147">The file is stored inside.</span></span>  <span data-ttu-id="bd63f-148">编辑器中的文件名现在还显示一个紫色点，指示文件是本地文件，而不是活动文件。</span><span class="sxs-lookup"><span data-stu-id="bd63f-148">The file name in the editor now also shows a purple dot that indicates that the file is local and not a live one.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="成功将文件存储在替代文件夹中" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   <span data-ttu-id="bd63f-150">成功将文件存储在替代文件夹中</span><span class="sxs-lookup"><span data-stu-id="bd63f-150">Successfully stored the file in your overrides folder</span></span>  
:::image-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="bd63f-151">在下面的示例中，现在可以更改网页的样式。</span><span class="sxs-lookup"><span data-stu-id="bd63f-151">In the following example, you may now change the styles of the webpage.</span></span>  <span data-ttu-id="bd63f-152">若要在文件周围添加红色边框，在 **样式** 编辑器上复制以下样式，并将其添加到 body 元素中。</span><span class="sxs-lookup"><span data-stu-id="bd63f-152">To add a red border around the file, on the **Styles** editor, copy the following style, and add it to the body element.</span></span>  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="bd63f-153">该文件会自动保存在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="bd63f-153">The file is automatically saved on your computer.</span></span>  <span data-ttu-id="bd63f-154">如果刷新该文件，将显示边框，并且不会丢失任何工作。</span><span class="sxs-lookup"><span data-stu-id="bd63f-154">If you refresh the file, the border is displayed and none of your work is lost.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="通过编辑替代文件夹中的文件永久更改网页样式" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         <span data-ttu-id="bd63f-156">通过编辑替代文件夹中的文件永久更改网页样式</span><span class="sxs-lookup"><span data-stu-id="bd63f-156">Change webpage styles persistently by editing a file in your overrides folder</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="bd63f-157">在"**源**"工具的"\*\*\*\* 页面"部分，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击\) ，并将其添加到重写。</span><span class="sxs-lookup"><span data-stu-id="bd63f-157">On the **Sources** tool, in the **Page** section, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="bd63f-158">同样，覆盖文件夹中已有的文件在图标上有一个紫色点。</span><span class="sxs-lookup"><span data-stu-id="bd63f-158">Again, files that are already in your overrides folder have a purple dot on the icon.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="从源工具中选择文件进行替代" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         <span data-ttu-id="bd63f-160">从源工具 **中选择** 文件进行替代</span><span class="sxs-lookup"><span data-stu-id="bd63f-160">Choose a file from the **Sources** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="bd63f-161">或者，在网络工具\*\*\*\* 上，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击\) ，并将其添加到覆盖。</span><span class="sxs-lookup"><span data-stu-id="bd63f-161">Alternatively, on the **Network** tool, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="bd63f-162">当替代生效时，位于您的计算机上而不是来自实时网页的文件。</span><span class="sxs-lookup"><span data-stu-id="bd63f-162">When overrides are in effect, files that are located on your computer and not from the live webpage.</span></span>  <span data-ttu-id="bd63f-163">当替代生效时，在 **网络** 工具上，找到文件名旁边的警告图标。</span><span class="sxs-lookup"><span data-stu-id="bd63f-163">When overrides are in effect, on the **Network** tool, locate a warning icon next to the file name.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="从网络工具中选择文件进行替代" lightbox="../media/javascript-overrides-network.msft.png":::
         <span data-ttu-id="bd63f-165">从网络工具 **中选择** 文件进行替代</span><span class="sxs-lookup"><span data-stu-id="bd63f-165">Choose a file from the **Network** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="bd63f-166">覆盖的双向交互</span><span class="sxs-lookup"><span data-stu-id="bd63f-166">Two-way interaction of overrides</span></span>  

<span data-ttu-id="bd63f-167">使用 DevTools 的 **源** 工具提供的编辑器或要更改文件的任何编辑器。</span><span class="sxs-lookup"><span data-stu-id="bd63f-167">Use the editor provided with the **Sources** tool of DevTools or any editor you want to change the files.</span></span>  <span data-ttu-id="bd63f-168">更改将同步访问替代文件夹中文件的所有产品。</span><span class="sxs-lookup"><span data-stu-id="bd63f-168">Changes are synced across all the products that access the files in the overrides folder.</span></span>  

## <span data-ttu-id="bd63f-169">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="bd63f-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "源工具概述 |Microsoft Docs"  
