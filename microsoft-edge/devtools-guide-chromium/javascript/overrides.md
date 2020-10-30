---
description: 覆盖功能是 Microsoft Edge DevTools 的 "源" 工具中的一项功能，可用于将网页资源复制到硬盘。  刷新网页时，DevTools 不会加载该资源，而是将其替换为本地副本。
title: 使用 Microsoft Edge DevTools 替代使用本地副本的网页资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 579ebe92dc50571837e7e3caf8fb7c1a9989bc59
ms.sourcegitcommit: 9dcaf598f3930bcfab9f93ff63463beb98274de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145141"
---
# <span data-ttu-id="e2b25-105">使用 Microsoft Edge DevTools 替代使用本地副本的网页资源</span><span class="sxs-lookup"><span data-stu-id="e2b25-105">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>  

<span data-ttu-id="e2b25-106">有时，您需要修复无法访问的网页上的问题，或者修补程序涉及缓慢而复杂的生成过程。</span><span class="sxs-lookup"><span data-stu-id="e2b25-106">Sometimes you need to fix a problem on a webpage that you do not have access to or fixes involve a slow and complex build process.</span></span>  <span data-ttu-id="e2b25-107">你可以在 DevTools 中调试和修复所有类型的问题。</span><span class="sxs-lookup"><span data-stu-id="e2b25-107">You may debug and fix all kind of problems in DevTools.</span></span> <span data-ttu-id="e2b25-108">但问题是，更改不会保留。</span><span class="sxs-lookup"><span data-stu-id="e2b25-108">But the problem is the changes do not persist.</span></span>  <span data-ttu-id="e2b25-109">刷新文件后，所有工作都将丢失。</span><span class="sxs-lookup"><span data-stu-id="e2b25-109">After you refresh the file, all your work is gone.</span></span>  

<span data-ttu-id="e2b25-110">" [源][DevToolsSourcesTool] " 工具中的 "替代" 功能可帮助你解决此问题。</span><span class="sxs-lookup"><span data-stu-id="e2b25-110">The Overrides feature in the [Sources][DevToolsSourcesTool] tool helps you solve this problem.</span></span>  

<span data-ttu-id="e2b25-111">现在，你可以获取当前网页的资源并将其存储在本地。</span><span class="sxs-lookup"><span data-stu-id="e2b25-111">You may now take a resource of the current webpage and store it locally.</span></span>  <span data-ttu-id="e2b25-112">刷新网页时，浏览器不会从服务器加载资源。</span><span class="sxs-lookup"><span data-stu-id="e2b25-112">When you refresh the webpage, the browser does not load the resource from the server.</span></span>  <span data-ttu-id="e2b25-113">而是让浏览器将其替换为您的资源的本地副本。</span><span class="sxs-lookup"><span data-stu-id="e2b25-113">Instead the browser replaces it with your local copy of the resource.</span></span>  

## <span data-ttu-id="e2b25-114">将本地文件夹设置为存储替代</span><span class="sxs-lookup"><span data-stu-id="e2b25-114">Setting up your local folder to store Overrides</span></span>  

1.  <span data-ttu-id="e2b25-115">在 " **源** " 工具中，找到左侧的几个部分。</span><span class="sxs-lookup"><span data-stu-id="e2b25-115">In the **Sources** tool, find several sections on the left-hand side.</span></span>  <span data-ttu-id="e2b25-116">如果 " **覆盖** " 选项未显示，请选择</span><span class="sxs-lookup"><span data-stu-id="e2b25-116">If the **Overrides** option is not displayed, choose the</span></span> <code>&#x0226B;</code><!--`≫`--> <span data-ttu-id="e2b25-117">转到此处的图标。</span><span class="sxs-lookup"><span data-stu-id="e2b25-117">icon to get there.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="空间不足，无法显示覆盖选项的 "源" 工具" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             <span data-ttu-id="e2b25-119">空间不足，无法显示覆盖选项的 "**源**" 工具</span><span class="sxs-lookup"><span data-stu-id="e2b25-119">**Sources** tool with not enough space to show the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="选择 "覆盖" 选项" lightbox="../media/javascript-overrides-menu.msft.png":::
             <span data-ttu-id="e2b25-121">选择 "覆盖" 选项</span><span class="sxs-lookup"><span data-stu-id="e2b25-121">Choose the overrides option</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="e2b25-122">选择 " **覆盖** " 选项后，必须选择本地计算机上的文件夹来存储要替换的资源文件。</span><span class="sxs-lookup"><span data-stu-id="e2b25-122">After you choose the **Overrides** option, you must choose a folder on your local computer to store the resource files that you want to replace.</span></span>  <span data-ttu-id="e2b25-123">选择 " **+ 选择替代文件夹** " 以搜索文件夹。</span><span class="sxs-lookup"><span data-stu-id="e2b25-123">Choose the **+ Select folder for overrides** to search for a folder.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="选择要用于替代的文件夹" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       <span data-ttu-id="e2b25-125">选择要用于替代的文件夹</span><span class="sxs-lookup"><span data-stu-id="e2b25-125">Choose a folder to use for overrides</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e2b25-126">DevTools 警告你必须具有对文件夹的完全访问权限，并且不应显示任何敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e2b25-126">DevTools warns you that must have full access to the folder and that you should not reveal any sensitive information.</span></span>  <span data-ttu-id="e2b25-127">在警告栏上，选择 " **允许** " 以授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="e2b25-127">On the warning bar, choose **Allow** to grant access.</span></span>  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="向文件夹授予 DevTools 访问权限" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       <span data-ttu-id="e2b25-129">向文件夹授予 DevTools 访问权限</span><span class="sxs-lookup"><span data-stu-id="e2b25-129">Grant DevTools access to folder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e2b25-130">在 " **替代** " 窗格中，应在 "替换文件夹" 旁边显示一个复选框 `Enable Local Overrides` 。</span><span class="sxs-lookup"><span data-stu-id="e2b25-130">In the **Overrides** pane, a checkbox should be displayed next to `Enable Local Overrides` and your overrides folder.</span></span>  <span data-ttu-id="e2b25-131">图标旁边将显示一个图标，允许您删除本地替代设置。</span><span class="sxs-lookup"><span data-stu-id="e2b25-131">An icon is displayed next to it that allows you to delete your local overrides settings.</span></span>  <span data-ttu-id="e2b25-132">您现在已完成对文件夹的设置，并准备将实时资源替换为本地资源。</span><span class="sxs-lookup"><span data-stu-id="e2b25-132">You are now done setting up your folder and ready to replace live resources with local ones.</span></span>
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="已成功设置覆盖文件夹" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       <span data-ttu-id="e2b25-134">已成功设置覆盖文件夹</span><span class="sxs-lookup"><span data-stu-id="e2b25-134">Successful set up of an overrides folder</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="e2b25-135">将文件添加到替代文件夹</span><span class="sxs-lookup"><span data-stu-id="e2b25-135">Adding files to your Overrides folder</span></span>  
  
<span data-ttu-id="e2b25-136">若要将文件添加到替代文件夹，请打开 " **元素** " 工具并检查网页。</span><span class="sxs-lookup"><span data-stu-id="e2b25-136">To add files to your overrides folder, open the **Elements** tool and inspect the webpage.</span></span>  <span data-ttu-id="e2b25-137">若要编辑，请在 " **样式** " 检查器中选择 CSS 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e2b25-137">To edit, choose the name of the CSS file in the **Styles** inspector.</span></span>  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="在 "样式" 检查器中选择文件" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   <span data-ttu-id="e2b25-139">在 " **样式** " 检查器中选择文件</span><span class="sxs-lookup"><span data-stu-id="e2b25-139">Choose a file in the **Styles** inspector</span></span>  
:::image-end:::  

<span data-ttu-id="e2b25-140">在 " **源代码** 编辑器" 上，将鼠标悬停在所选文件的文件名上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **另存为替代**"。</span><span class="sxs-lookup"><span data-stu-id="e2b25-140">On the **Sources** editor, hover on the file name of your chosen file, open the contextual menu \(right-click\), and choose **Save for overrides**.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="在源代码编辑器中，添加要覆盖的文件的名称" lightbox="../media/javascript-overrides-file-name.msft.png":::
   <span data-ttu-id="e2b25-142">在 **源代码** 编辑器中，添加要覆盖的文件的名称</span><span class="sxs-lookup"><span data-stu-id="e2b25-142">In the **Sources** editor, add the name of the file to overrides</span></span>  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="在上下文菜单上，选择 "另存为替代"" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   <span data-ttu-id="e2b25-144">在上下文菜单上，选择 "**另存为替代**"</span><span class="sxs-lookup"><span data-stu-id="e2b25-144">On the context menu, choose **Save for overrides**</span></span>  
:::image-end:::  

<span data-ttu-id="e2b25-145">文件存储在 "替代" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e2b25-145">The file is stored in your overrides folder.</span></span>  <span data-ttu-id="e2b25-146">验证 DevTools 使用具有正确目录结构的文件的 URL 创建一个名为的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e2b25-146">Verify that DevTools create a folder that is named using the URL of the file with the correct directory structure.</span></span>  <span data-ttu-id="e2b25-147">文件存储在其中。</span><span class="sxs-lookup"><span data-stu-id="e2b25-147">The file is stored inside.</span></span>  <span data-ttu-id="e2b25-148">编辑器中的文件名现在还显示一个紫色圆点，表示该文件是本地的，而不是实时的。</span><span class="sxs-lookup"><span data-stu-id="e2b25-148">The file name in the editor now also shows a purple dot that indicates that the file is local and not a live one.</span></span>  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="已成功将文件存储在 "替代" 文件夹中" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   <span data-ttu-id="e2b25-150">已成功将文件存储在 "替代" 文件夹中</span><span class="sxs-lookup"><span data-stu-id="e2b25-150">Successfully stored the file in your overrides folder</span></span>  
:::image-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="e2b25-151">在以下示例中，你现在可以更改网页的样式。</span><span class="sxs-lookup"><span data-stu-id="e2b25-151">In the following example, you may now change the styles of the webpage.</span></span>  <span data-ttu-id="e2b25-152">若要在文件周围添加红色边框，请在 " **样式** 编辑器" 中复制以下样式，并将其添加到 body 元素。</span><span class="sxs-lookup"><span data-stu-id="e2b25-152">To add a red border around the file, on the **Styles** editor, copy the following style, and add it to the body element.</span></span>  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e2b25-153">文件将自动保存在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="e2b25-153">The file is automatically saved on your computer.</span></span>  <span data-ttu-id="e2b25-154">如果刷新文件，将显示边框，并且不会丢失任何工作。</span><span class="sxs-lookup"><span data-stu-id="e2b25-154">If you refresh the file, the border is displayed and none of your work is lost.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="通过编辑 "覆盖" 文件夹中的文件，永久更改网页样式" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         <span data-ttu-id="e2b25-156">通过编辑 "覆盖" 文件夹中的文件，永久更改网页样式</span><span class="sxs-lookup"><span data-stu-id="e2b25-156">Change webpage styles persistently by editing a file in your overrides folder</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      <span data-ttu-id="e2b25-157">在 " **源** " 工具的 " **页面** " 部分中，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击 "\ ) "，然后将其添加到 "覆盖"。</span><span class="sxs-lookup"><span data-stu-id="e2b25-157">On the **Sources** tool, in the **Page** section, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="e2b25-158">同样，"覆盖" 文件夹中已有的文件在图标上有一个紫色圆点。</span><span class="sxs-lookup"><span data-stu-id="e2b25-158">Again, files that are already in your overrides folder have a purple dot on the icon.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="从 "源" 工具中选择用于替代的文件" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         <span data-ttu-id="e2b25-160">从 " **源** " 工具中选择用于替代的文件</span><span class="sxs-lookup"><span data-stu-id="e2b25-160">Choose a file from the **Sources** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e2b25-161">或者，在 " **网络** " 工具上，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击 "\ ) "，然后将其添加到 "覆盖"。</span><span class="sxs-lookup"><span data-stu-id="e2b25-161">Alternatively, on the **Network** tool, hover on any file, open the contextual menu \(right-click\), and add it to overrides.</span></span>  <span data-ttu-id="e2b25-162">当重写生效时，位于计算机上而不是从 live 网页中的文件。</span><span class="sxs-lookup"><span data-stu-id="e2b25-162">When overrides are in effect, files that are located on your computer and not from the live webpage.</span></span>  <span data-ttu-id="e2b25-163">当覆盖生效时，请在 " **网络** " 工具上，找到文件名旁边的警告图标。</span><span class="sxs-lookup"><span data-stu-id="e2b25-163">When overrides are in effect, on the **Network** tool, locate a warning icon next to the file name.</span></span>  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="从网络工具中选择一个文件进行替代" lightbox="../media/javascript-overrides-network.msft.png":::
         <span data-ttu-id="e2b25-165">从 **网络** 工具中选择一个文件进行替代</span><span class="sxs-lookup"><span data-stu-id="e2b25-165">Choose a file from the **Network** tool for overrides</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="e2b25-166">替代的双向交互</span><span class="sxs-lookup"><span data-stu-id="e2b25-166">Two-way interaction of overrides</span></span>  

<span data-ttu-id="e2b25-167">使用 DevTools 的 " **源** " 工具提供的编辑器或要更改文件的任何编辑器。</span><span class="sxs-lookup"><span data-stu-id="e2b25-167">Use the editor provided with the **Sources** tool of DevTools or any editor you want to change the files.</span></span>  <span data-ttu-id="e2b25-168">更改将在所有可访问 "覆盖" 文件夹中的文件的产品之间同步。</span><span class="sxs-lookup"><span data-stu-id="e2b25-168">Changes are synced across all the products that access the files in the overrides folder.</span></span>  

## <span data-ttu-id="e2b25-169">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="e2b25-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources.md "源工具概述 |Microsoft 文档"  
