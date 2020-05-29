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

创建扩展图标之前，应查看[辅助功能][ExtensionsGuidesAccessibility]指南，以确保你的图标具有足够高的对比度，并且在 Microsoft Edge 的浅色和深色主题中可见。  

尽管支持任何 webkit 图像格式，但建议使用 png 图标进行透明支持。  

### 用于您的扩展的图标  

对于你的扩展，你必须为浏览器操作或页面操作创建一个图标大小，然后为 "**扩展**" 窗格创建一个图标大小。  可能会提供每个大小的多个大小以支持高分辨率显示。  

扩展应具有浏览器操作或页面操作图标。  浏览器操作和页面操作图标可能会在运行时使用[browserAction][MSDApiBrowseractionSeticon]方法或[pageAction][MDNApiPageactionSeticon]方法进行更改。  

#### 浏览器操作  

浏览器操作和页面操作图标的首选大小为 `20px` 、 `25px` 、 `30px` 和 `40px` 。  其他受支持的大小包括 `19px` 、 `35px` 和 `38px` 。  

以下[清单 json][ExtensionsApisupportManifestkeys]文件代码片段显示了使用[browser_action][MDNManifestjsonBrowserAction]键指定的标准和高定义浏览器操作图标。  相同语法适用于[page_action][MDNManifestjsonPageAction]键。  

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

如果浏览器操作已由扩展设置，则在 "操作" 菜单中选择 "**更多（...）**" 后，它会显示在 "操作" 菜单中，或者，如果用户已切换**地址栏旁边**的 "显示" 按钮，则会在 "操作" 菜单中显示该操作。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="操作菜单中的浏览器操作":::
         操作菜单中的浏览器操作 :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="浏览器操作":::
         浏览器操作 :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### 页面操作  

[Page_action][MDNManifestjsonPageAction]键具有与[browser_action][MDNManifestjsonBrowserAction]键相同的 JSON 清单语法。  页面操作还具有与浏览器操作相同的图标大小要求。  

如果在[manifest 文件 json][ExtensionsApisupportManifestkeys]文件中指定了 page 操作，则只要使用[pageAction][MDNApiPageactionShow]方法，它就会出现在地址栏中。  

:::image type="complex" source="../media/pageaction.png" alt-text="页面操作":::
   页面操作
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### 管理 UI  

当用户通过转到 "**更多（...）** " 菜单并选择 "**扩展**" 导航到 "扩展" 窗格时，将在该扩展名的名称旁边显示一个图标。  

应指定以下图标大小。  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| `48px` | 显示标准分辨率的图标。 |  
| `128px` | 显示高分辨率的图标。 |  
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

### 用于打包的图标  

延长分机准备就绪后，您必须有三个其他图标大小准备就绪。  

| 大小 | 详细信息 |  
|:--- |:--- |  
| 44px | 在 Windows UI \ （**应用列表**，**设置**  \>  **系统**  \>  **应用 & 功能**\）中使用。 |  
| 50像素 | 打包要求 \ （不可见的地方 \）。 |  
| 150px | 用作 Microsoft Store 的图标。 |  


请参阅[手动打包指南][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]或[ManifoldJS 打包指南][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]以确定这些图标放置的位置。  这取决于你选择的打包方法。  

#### Microsoft Store 图标  

如果 Microsoft Store 的150px 图标具有透明背景，则用户设备的主题颜色将显示为图标的背景色。  

例如，如果用户选中 "粉色" 作为主题色，则 "应用商店" 图标的透明背景将显示为粉红色。  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Windows 主题色":::
          Windows 主题色 :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="自动选择的背景色":::
         自动选择的背景色 :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

如果你想要为 Microsoft Store 选择自己的背景色，则必须将背景设置为不透明。  

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。  使用 Microsoft Store 的请求[与我们联系][AkaExtensionRequest]，你的请求将被视为将来的更新。  

<!-- image links -->  

<!--[ImageActionmenuBrowseraction]: ../media/actionmenu-browseraction.png "browser action in action menu"  -->  
<!--[ImageBrowserActionIcon]: ../media/browseractionicon.png "browser action"  -->  
<!--[ImagePageaction]: ../media/pageaction.png "page action"  -->  
<!--[ImageManagementUi]: ../media/management-ui.png "management UI"  -->  
<!--[ImageWindowsAccentColor]: ../media/windows-accent-color.png "Windows accent color"  -->  
<!--[ImageStoreIconTransparencyBackground]: ../media/store-icon-with-transparent-background.png "Background color auto selected"  -->  

<!-- links -->  

[ExtensionsGuidesAccessibility]: ./accessibility.md "辅助功能 |Microsoft 文档"  
[ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]: ./packaging/creating-and-testing-extension-packages.md#assets-folder "资源文件夹-创建和测试 Microsoft Edge 扩展 AppX 程序包 |Microsoft 文档"  
[ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]: ./packaging/using-manifoldjs-to-package-extensions.md#packaging-with-manifoldjs "使用 ManifoldJS 打包时使用 ManifoldJS 创建扩展 AppX 程序包 |Microsoft 文档"  

[ExtensionsApisupportManifestkeys]: ../API-support/supported-manifest-keys.md "支持的清单键 |Microsoft 文档"  

[AkaExtensionRequest]: https://aka.ms/extension-request "与我们联系"  

[MSDApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction setIcon （）-API |MDN"  
[MDNApiPageactionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/setIcon "pageAction setIcon （）-API |MDN"  
[MDNApiPageactionShow]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/show "pageAction （）-API |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action "browser_action 清单 json |MDN"  
[MDNManifestjsonPageAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action "page_action 清单 json |MDN"  
