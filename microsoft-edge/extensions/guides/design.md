---
description: Learn about the various design aspects and UI behavior to consider when creating Microsoft Edge extensions.
title: Extensions - Design
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, javascript, design, icons, developer
ms.openlocfilehash: 622d72453ea3ecd2897efcf8f67e1b2aa7a0937c
ms.sourcegitcommit: da768193c7ae7b611f4fbb1746f16d9818e42bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684062"
---
# Design Guidelines For Microsoft Edge Extensions  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

The following page contains various design aspects and UI behavior to consider when creating Microsoft Edge extensions.  

## Icons  

You should make the icons of your extension using a vector graphic.  You must create a few different sizes of your icon for your extension, and three additional sizes if you want to package your extension.  Microsoft Edge extensions do not support .svg icons.  

Before you create your extension icons, you should review the [accessibility][ExtensionsGuidesAccessibility] guide to ensure that your icons have high enough contrast and are visible in both the light and dark themes of Microsoft Edge.  

While any webkit image format is supported, .png icons are recommended for transparency support.  

### Icons for your extension  

For your extension, you must create one icon size for the browser action or page action, and one icon size for the **Extensions** pane.  More than one size for each may be provided to support high resolution displays.  

An extension should have a browser action or page action icon.  The browser action and page action icons may be changed at runtime using the [browserAction.setIcon][MSDApiBrowseractionSeticon] method or [pageAction.setIcon][MDNApiPageactionSeticon] method.  

#### Browser action  

The preferred sizes for browser action and page action icons are `20px`, `25px`, `30px`, and `40px`.  Other supported sizes include `19px`, `35px`, and `38px`.  

The following [manifest.json][ExtensionsApisupportManifestkeys] file snippet shows a standard and high definition browser action icon being specified using the [browser_action][MDNManifestjsonBrowserAction] key.  The same syntax applies for the [page_action][MDNManifestjsonPageAction] key.  

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

If the browser action has been set by the extension, it appears either in the Actions menu after selecting **More(...)**,  or to the right of the address bar if **Show button next to the address bar** has been toggled on by the user.  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="Browser action in action menu":::
         Browser action in action menu :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="Browser action in action menu":::
         Browser action :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### Page action  

The [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.  Page action also has the same icon size requirements as browser action.  

If page action is specified in the [manifest.json][ExtensionsApisupportManifestkeys] file, it appears within the address bar whenever the [pageAction.show][MDNApiPageactionShow] method is used.  

:::image type="complex" source="../media/pageaction.png" alt-text="Browser action in action menu"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="Browser action in action menu":::
   Management UI
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### Icons for packaging  

Once your extension is ready for packaging, you must have three additional icon sizes ready.  

| Size | Details |  
|:--- |:--- |  
| 44px | Used in the Windows UI \(**App List**, **Settings** \> **System** \> **Apps & features**\). |  
| 50px | Packaging requirement \(not visible anywhere\). |  
| 150px | Used as the icon for the Microsoft Store. |  


See either the [manual packaging guide][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] or the [ManifoldJS packaging guide][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] to determine where these icons is placed.  This depends upon which packaging method you choose.  

#### Microsoft Store icon  

If the 150px icon for the Microsoft Store has a transparent background, the accent color of the user's device appears as the background color of the icon.  

For example, if a user has selected pink as the accent color, the transparent background of your store icon is displayed as pink.  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Browser action in action menu":::
          Windows accent color :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="Browser action in action menu"  
