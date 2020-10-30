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
# 使用 Microsoft Edge DevTools 替代使用本地副本的网页资源  

有时，您需要修复无法访问的网页上的问题，或者修补程序涉及缓慢而复杂的生成过程。  你可以在 DevTools 中调试和修复所有类型的问题。 但问题是，更改不会保留。  刷新文件后，所有工作都将丢失。  

" [源][DevToolsSourcesTool] " 工具中的 "替代" 功能可帮助你解决此问题。  

现在，你可以获取当前网页的资源并将其存储在本地。  刷新网页时，浏览器不会从服务器加载资源。  而是让浏览器将其替换为您的资源的本地副本。  

## 将本地文件夹设置为存储替代  

1.  在 " **源** " 工具中，找到左侧的几个部分。  如果 " **覆盖** " 选项未显示，请选择 <code>&#x0226B;</code><!--`≫`--> 转到此处的图标。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             空间不足，无法显示覆盖选项的 "**源**" 工具  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-menu.msft.png":::
             选择 "覆盖" 选项  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择 " **覆盖** " 选项后，必须选择本地计算机上的文件夹来存储要替换的资源文件。  选择 " **+ 选择替代文件夹** " 以搜索文件夹。  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       选择要用于替代的文件夹  
    :::image-end:::  
    
1.  DevTools 警告你必须具有对文件夹的完全访问权限，并且不应显示任何敏感信息。  在警告栏上，选择 " **允许** " 以授予访问权限。  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       向文件夹授予 DevTools 访问权限  
    :::image-end:::  
    
1.  在 " **替代** " 窗格中，应在 "替换文件夹" 旁边显示一个复选框 `Enable Local Overrides` 。  图标旁边将显示一个图标，允许您删除本地替代设置。  您现在已完成对文件夹的设置，并准备将实时资源替换为本地资源。
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       已成功设置覆盖文件夹  
    :::image-end:::  
    
## 将文件添加到替代文件夹  
  
若要将文件添加到替代文件夹，请打开 " **元素** " 工具并检查网页。  若要编辑，请在 " **样式** " 检查器中选择 CSS 文件的名称。  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   在 " **样式** " 检查器中选择文件  
:::image-end:::  

在 " **源代码** 编辑器" 上，将鼠标悬停在所选文件的文件名上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **另存为替代**"。  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-file-name.msft.png":::
   在 **源代码** 编辑器中，添加要覆盖的文件的名称  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   在上下文菜单上，选择 "**另存为替代**"  
:::image-end:::  

文件存储在 "替代" 文件夹中。  验证 DevTools 使用具有正确目录结构的文件的 URL 创建一个名为的文件夹。  文件存储在其中。  编辑器中的文件名现在还显示一个紫色圆点，表示该文件是本地的，而不是实时的。  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   已成功将文件存储在 "替代" 文件夹中  
:::image-end:::  

:::row:::
   :::column span="":::
      在以下示例中，你现在可以更改网页的样式。  若要在文件周围添加红色边框，请在 " **样式** 编辑器" 中复制以下样式，并将其添加到 body 元素。  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      文件将自动保存在您的计算机上。  如果刷新文件，将显示边框，并且不会丢失任何工作。  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         通过编辑 "覆盖" 文件夹中的文件，永久更改网页样式  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      在 " **源** " 工具的 " **页面** " 部分中，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击 "\ ) "，然后将其添加到 "覆盖"。  同样，"覆盖" 文件夹中已有的文件在图标上有一个紫色圆点。  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         从 " **源** " 工具中选择用于替代的文件  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      或者，在 " **网络** " 工具上，将鼠标悬停在任何文件上，打开上下文菜单 \ (右键单击 "\ ) "，然后将其添加到 "覆盖"。  当重写生效时，位于计算机上而不是从 live 网页中的文件。  当覆盖生效时，请在 " **网络** " 工具上，找到文件名旁边的警告图标。  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="空间不足，无法显示覆盖选项的 &quot;源&quot; 工具" lightbox="../media/javascript-overrides-network.msft.png":::
         从 **网络** 工具中选择一个文件进行替代  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 替代的双向交互  

使用 DevTools 的 " **源** " 工具提供的编辑器或要更改文件的任何编辑器。  更改将在所有可访问 "覆盖" 文件夹中的文件的产品之间同步。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources.md "源工具概述 |Microsoft 文档"  
