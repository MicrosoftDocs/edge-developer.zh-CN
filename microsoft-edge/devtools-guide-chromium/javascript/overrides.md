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
# 使用 Microsoft Edge DevTools 使用本地副本替代网页资源  

有时，你需要修复网页上无法访问的问题，或者修复涉及缓慢而复杂的生成过程。  你可以调试并修复 DevTools 中的所有类型问题。 但问题是更改不会持续存在。  刷新文件后，所有工作都消失。  

"源 ["工具中的][DevToolsSourcesTool] "覆盖"功能可帮助你解决此问题。  

现在，您可以利用当前网页的资源，并在本地存储该资源。  刷新网页时，浏览器不会从服务器加载资源。  相反，浏览器会将其替换为你的本地资源副本。  

## 将本地文件夹设置为存储替代  

1.  在 **"源** "工具中，在左侧找到多个部分。  如果未 **显示"替代"** 选项，请选择 <code>&#x0226B;</code><!--`≫`--> 图标到达那里。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="显示替代选项的空间不足的源工具" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             **显示** 替代选项的空间不足的源工具  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="选择替代选项" lightbox="../media/javascript-overrides-menu.msft.png":::
             选择替代选项  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择" **覆盖"选项** 后，您必须在本地计算机上选择一个文件夹来存储要替换的资源文件。  为 **替代选择 + Select 文件夹** 以搜索文件夹。  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="选择要用于替代的文件夹" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       选择要用于替代的文件夹  
    :::image-end:::  
    
1.  DevTools 警告您必须具有对文件夹的完全访问权限，并且不应显示任何敏感信息。  在警告栏上，选择 **"允许** 授予访问权限"。  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="授予 DevTools 对文件夹的访问权限" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       授予 DevTools 文件夹访问权限  
    :::image-end:::  
    
1.  在 **"覆盖"** 窗格中，应在替代文件夹旁边显示一个 `Enable Local Overrides` 复选框。  旁边会显示一个图标，允许你删除本地覆盖设置。  现在，你已完成文件夹设置并准备好将实时资源替换为本地资源。
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="成功设置替代文件夹" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       成功设置替代文件夹  
    :::image-end:::  
    
## 将文件添加到 Overrides 文件夹  
  
若要将文件添加到替代文件夹，请打开 **Elements** 工具并检查网页。  若要编辑，请选择样式检查器中的 CSS **文件** 的名称。  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="在样式检查器中选择文件" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   在样式检查器 **中选择** 文件  
:::image-end:::  

在源**编辑器**上，将鼠标悬停在所选文件的文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"保存**替代"。**  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="在源编辑器中，添加要覆盖的文件的名称" lightbox="../media/javascript-overrides-file-name.msft.png":::
   在 **"源** "编辑器中，添加要覆盖的文件的名称  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="在上下文菜单上，选择保存替代" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   在上下文菜单上，选择 **"保存替代"**  
:::image-end:::  

该文件存储在替代文件夹中。  验证 DevTools 是否创建使用具有正确目录结构的文件 URL 命名的文件夹。  文件存储在内部。  编辑器中的文件名现在还显示一个紫色点，指示文件是本地文件，而不是活动文件。  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="成功将文件存储在替代文件夹中" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   成功将文件存储在替代文件夹中  
:::image-end:::  

:::row:::
   :::column span="":::
      在下面的示例中，现在可以更改网页的样式。  若要在文件周围添加红色边框，在 **样式** 编辑器上复制以下样式，并将其添加到 body 元素中。  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      该文件会自动保存在您的计算机上。  如果刷新该文件，将显示边框，并且不会丢失任何工作。  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="通过编辑替代文件夹中的文件永久更改网页样式" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         通过编辑替代文件夹中的文件永久更改网页样式  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      在"**源**"工具的"**** 页面"部分，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击\) ，并将其添加到重写。  同样，覆盖文件夹中已有的文件在图标上有一个紫色点。  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="从源工具中选择文件进行替代" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         从源工具 **中选择** 文件进行替代  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      或者，在网络工具**** 上，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击\) ，并将其添加到覆盖。  当替代生效时，位于您的计算机上而不是来自实时网页的文件。  当替代生效时，在 **网络** 工具上，找到文件名旁边的警告图标。  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="从网络工具中选择文件进行替代" lightbox="../media/javascript-overrides-network.msft.png":::
         从网络工具 **中选择** 文件进行替代  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 覆盖的双向交互  

使用 DevTools 的 **源** 工具提供的编辑器或要更改文件的任何编辑器。  更改将同步访问替代文件夹中文件的所有产品。  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "源工具概述 |Microsoft Docs"  
