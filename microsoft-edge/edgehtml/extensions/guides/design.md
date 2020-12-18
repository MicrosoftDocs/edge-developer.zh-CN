---
description: 了解创建 Microsoft Edge 扩展时要考虑的各种设计方面和 UI 行为。
title: 扩展 - 设计
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， javascript， 设计， 图标， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a32223f93baf44d2ca523e92cf9d7584ad9a8333
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232629"
---
# Microsoft Edge 扩展的设计指南  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

以下页面包含创建 Microsoft Edge 扩展时要考虑的各种设计方面和 UI 行为。  

## 图标  

你应该使用矢量图形制作扩展的图标。  若要打包扩展，必须为扩展创建几个不同的图标大小和三个其他大小。  Microsoft Edge 扩展不支持 .svg 图标。  

创建扩展图标之前，应查看辅助功能指南，以确保[][ExtensionsGuidesAccessibility]图标具有足够高对比度，并且同时在 Microsoft Edge 的浅色和深色主题中可见。  

尽管支持任何 Webkit 图像格式，但建议使用 .png 图标实现透明度支持。  

### 扩展图标  

对于扩展，必须为浏览器操作或页面操作创建一个图标大小，为扩展窗格创建一个**图标大小。**  可以针对每种屏幕提供多个大小以支持高分辨率显示器。  

扩展应具有浏览器操作或页面操作图标。  在运行时，可能会使用 [browserAction.setIcon][MSDApiBrowseractionSeticon] 方法或 [pageAction.setIcon][MDNApiPageactionSeticon] 方法更改浏览器操作和页面操作图标。  

#### 浏览器操作  

浏览器操作和页面操作图标的首选大小为 ， `20px` `25px` 和 `30px` `40px` 。  其他支持的大小包括 `19px` ， `35px` 和 `38px` 。  

以下manifest.js[ 代码][ExtensionsApisupportManifestkeys] 段上的说明显示了使用代码段键指定的标准和 [browser_action浏览器操作][MDNManifestjsonBrowserAction] 图标。  相同的语法适用于[page_action键。][MDNManifestjsonPageAction]  

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

如果浏览器操作已由扩展设置，则它在选择"更多** (...) "** 后显示在"操作"菜单中，或者显示在地址栏旁的"显示"按钮已由用户打开**** 的情况下显示在地址栏的右侧。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="浏览器操作操作菜单":::
         浏览器操作操作菜单 :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="浏览器操作":::
         浏览器操作 :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### 页面操作  

the [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.  页面操作也具有与浏览器操作相同的图标大小要求。  

如果在文件上的manifest.js中指定了 [ 页面操作，][ExtensionsApisupportManifestkeys] 则每当使用 [pageAction.show][MDNApiPageactionShow] 方法时，它都会显示在地址栏中。  

:::image type="complex" source="../media/pageaction.png" alt-text="页面操作":::
   页面操作
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### 管理 UI  

当用户通过转到"更多扩展** (...) **菜单并选择"扩展"导航到扩展窗格时，将在扩展名旁边显示**** 一个图标。  

应指定以下图标大小。  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| `48px` | 显示标准分辨率的图标。 |  
| `128px` | 高分辨率显示的图标。 |  
| `176px` | 显示更高分辨率的图标。 |  


```json
"icons": {
    "48": "images/icon_48.png",
    "128": "images/icon_128.png",
    "176": "images/icon_176.png"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="管理 UI":::
   管理 UI
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### 打包图标  

扩展准备好打包后，必须准备好其他三个图标大小。  

| 大小 | 详细信息 |  
|:--- |:--- |  
| 44px | 在 Windows UI \ (**应用列表中使用**，**设置**  \>  **系统**应用  \>  **&功能**\) 。 |  
| 50px | 打包要求 \ (在任意位置\) 。 |  
| 150px | 用作 Microsoft Store 的图标。 |  


请参阅手动 [打包指南或][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] [ManifoldJS 打包指南][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] ，以确定这些图标的放置位置。  这取决于你选择的打包方法。  

#### Microsoft Store 图标  

如果 Microsoft Store 的 150px 图标具有透明背景，则用户设备的背景色将显示为图标的背景色。  

例如，如果用户已选择粉色作为主题色，则应用商店图标的透明背景显示为粉色。  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Windows 主题色":::
          Windows 主题色 :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="背景色自动选中":::
         背景色自动选中 :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

如果你想要为 Microsoft Store 选取自己的背景色，则必须使背景不透明。  

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。  [请通过][AkaExtensionRequest] Microsoft Store 请求联系我们，你的请求将考虑用于将来的更新。  

<!-- image links -->  

<!--[ImageActionmenuBrowseraction]: ../media/actionmenu-browseraction.png "browser action in action menu"  -->  
<!--[ImageBrowserActionIcon]: ../media/browseractionicon.png "browser action"  -->  
<!--[ImagePageaction]: ../media/pageaction.png "page action"  -->  
<!--[ImageManagementUi]: ../media/management-ui.png "management UI"  -->  
<!--[ImageWindowsAccentColor]: ../media/windows-accent-color.png "Windows accent color"  -->  
<!--[ImageStoreIconTransparencyBackground]: ../media/store-icon-with-transparent-background.png "Background color auto selected"  -->  

<!-- links -->  

[ExtensionsGuidesAccessibility]: ./accessibility.md "辅助功能 |Microsoft Docs"  
[ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]: ./packaging/creating-and-testing-extension-packages.md#assets-folder "Assets 文件夹 - 创建和测试 Microsoft Edge 扩展 AppX 程序包 |Microsoft Docs"  
[ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]: ./packaging/using-manifoldjs-to-package-extensions.md#packaging-with-manifoldjs "使用 ManifoldJS 打包 - 使用 ManifoldJs 创建扩展 AppX 包 |Microsoft Docs"  

[ExtensionsApisupportManifestkeys]: ../API-support/supported-manifest-keys.md "支持的清单密钥 |Microsoft Docs"  

[AkaExtensionRequest]: https://aka.ms/extension-request "联系我们"  

[MSDApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction.setIcon () - API |MDN"  
[MDNApiPageactionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/setIcon "pageAction.setIcon () - API |MDN"  
[MDNApiPageactionShow]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/show "pageAction.show () - API |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action "browser_action - manifest.js|MDN"  
[MDNManifestjsonPageAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action "page_action - manifest.js|MDN"  
