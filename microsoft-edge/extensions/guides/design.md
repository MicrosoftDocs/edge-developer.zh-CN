---
description: 了解创建 Microsoft Edge 扩展时需要考虑的各种设计方面和 UI 行为。
title: 扩展-设计
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、javascript、设计、图标、开发人员
ms.openlocfilehash: 622d72453ea3ecd2897efcf8f67e1b2aa7a0937c
ms.sourcegitcommit: da768193c7ae7b611f4fbb1746f16d9818e42bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684062"
---
# Microsoft Edge 扩展的设计指南  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

以下页面包含创建 Microsoft Edge 扩展时要考虑的各种设计方面和 UI 行为。  

## 图标  

你应该使用矢量图形制作扩展的图标。  你必须为你的扩展名创建几个不同大小的图标，如果要打包你的扩展，还必须创建三个附加大小。  Microsoft Edge 扩展不支持 svg 图标。  

创建扩展图标之前，应查看 [辅助功能][ExtensionsGuidesAccessibility] 指南，以确保你的图标具有足够高的对比度，并且在 Microsoft Edge 的浅色和深色主题中可见。  

尽管支持任何 webkit 图像格式，但建议使用 png 图标进行透明支持。  

### 用于您的扩展的图标  

对于你的扩展，你必须为浏览器操作或页面操作创建一个图标大小，然后为 " **扩展** " 窗格创建一个图标大小。  可能会提供每个大小的多个大小以支持高分辨率显示。  

扩展应具有浏览器操作或页面操作图标。  浏览器操作和页面操作图标可能会在运行时使用 [browserAction][MSDApiBrowseractionSeticon] 方法或 [pageAction][MDNApiPageactionSeticon] 方法进行更改。  

#### 浏览器操作  

浏览器操作和页面操作图标的首选大小为 `20px` 、 `25px` 、 `30px` 和 `40px` 。  其他受支持的大小包括 `19px` 、 `35px` 和 `38px` 。  

文件代码段上的以下 [manifest.js][ExtensionsApisupportManifestkeys] 显示使用 [browser_action][MDNManifestjsonBrowserAction] 键指定的标准和高定义浏览器操作图标。  相同语法适用于 [page_action][MDNManifestjsonPageAction] 键。  

```json
"browser_action": {
    "default_icon": {
        "20": "images/icon_20.png",
        "40": "images/icon_40.png"
    },
    "default_title": "Fetch page info",
    "default_popup": "popup.html"
}
```  

如果浏览器操作已由扩展设置，则在选择 " **更多 ( ..." ) **或 "地址栏" 旁边的 " **显示" 按钮** 时，它将显示在 "操作" 菜单中，如果用户已切换。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="操作菜单中的浏览器操作":::
         操作菜单中的浏览器操作 :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="操作菜单中的浏览器操作":::
         浏览器操作 :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### 页面操作  

[Page_action][MDNManifestjsonPageAction]键具有与[browser_action][MDNManifestjsonBrowserAction]键相同的 JSON 清单语法。  页面操作还具有与浏览器操作相同的图标大小要求。  

如果在 [manifest.json file 上][ExtensionsApisupportManifestkeys] 指定了 page 操作，则只要使用 [pageAction][MDNApiPageactionShow] 方法，它就会出现在地址栏中。  

:::image type="complex" source="../media/pageaction.png" alt-text="操作菜单中的浏览器操作"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="操作菜单中的浏览器操作" 图标的透明背景将显示为粉红色。  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="操作菜单中的浏览器操作":::
          Windows 主题色 :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="操作菜单中的浏览器操作"  
