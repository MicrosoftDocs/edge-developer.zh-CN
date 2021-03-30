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
# <span data-ttu-id="47e26-104">Microsoft Edge 扩展的设计指南</span><span class="sxs-lookup"><span data-stu-id="47e26-104">Design Guidelines For Microsoft Edge Extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="47e26-105">以下页面包含创建 Microsoft Edge 扩展时要考虑的各种设计方面和 UI 行为。</span><span class="sxs-lookup"><span data-stu-id="47e26-105">The following page contains various design aspects and UI behavior to consider when creating Microsoft Edge extensions.</span></span>  

## <span data-ttu-id="47e26-106">图标</span><span class="sxs-lookup"><span data-stu-id="47e26-106">Icons</span></span>  

<span data-ttu-id="47e26-107">你应该使用矢量图形制作扩展的图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-107">You should make the icons of your extension using a vector graphic.</span></span>  <span data-ttu-id="47e26-108">若要打包扩展，必须为扩展创建几个不同的图标大小和三个其他大小。</span><span class="sxs-lookup"><span data-stu-id="47e26-108">You must create a few different sizes of your icon for your extension, and three additional sizes if you want to package your extension.</span></span>  <span data-ttu-id="47e26-109">Microsoft Edge 扩展不支持 .svg 图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-109">Microsoft Edge extensions do not support .svg icons.</span></span>  

<span data-ttu-id="47e26-110">创建扩展图标之前，应查看辅助功能指南，以确保[][ExtensionsGuidesAccessibility]图标具有足够高对比度，并且同时在 Microsoft Edge 的浅色和深色主题中可见。</span><span class="sxs-lookup"><span data-stu-id="47e26-110">Before you create your extension icons, you should review the [accessibility][ExtensionsGuidesAccessibility] guide to ensure that your icons have high enough contrast and are visible in both the light and dark themes of Microsoft Edge.</span></span>  

<span data-ttu-id="47e26-111">尽管支持任何 Webkit 图像格式，但建议使用 .png 图标实现透明度支持。</span><span class="sxs-lookup"><span data-stu-id="47e26-111">While any webkit image format is supported, .png icons are recommended for transparency support.</span></span>  

### <span data-ttu-id="47e26-112">扩展图标</span><span class="sxs-lookup"><span data-stu-id="47e26-112">Icons for your extension</span></span>  

<span data-ttu-id="47e26-113">对于扩展，必须为浏览器操作或页面操作创建一个图标大小，为扩展窗格创建一个**图标大小。**</span><span class="sxs-lookup"><span data-stu-id="47e26-113">For your extension, you must create one icon size for the browser action or page action, and one icon size for the **Extensions** pane.</span></span>  <span data-ttu-id="47e26-114">可以针对每种屏幕提供多个大小以支持高分辨率显示器。</span><span class="sxs-lookup"><span data-stu-id="47e26-114">More than one size for each may be provided to support high resolution displays.</span></span>  

<span data-ttu-id="47e26-115">扩展应具有浏览器操作或页面操作图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-115">An extension should have a browser action or page action icon.</span></span>  <span data-ttu-id="47e26-116">在运行时，可能会使用 [browserAction.setIcon][MSDApiBrowseractionSeticon] 方法或 [pageAction.setIcon][MDNApiPageactionSeticon] 方法更改浏览器操作和页面操作图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-116">The browser action and page action icons may be changed at runtime using the [browserAction.setIcon][MSDApiBrowseractionSeticon] method or [pageAction.setIcon][MDNApiPageactionSeticon] method.</span></span>  

#### <span data-ttu-id="47e26-117">浏览器操作</span><span class="sxs-lookup"><span data-stu-id="47e26-117">Browser action</span></span>  

<span data-ttu-id="47e26-118">浏览器操作和页面操作图标的首选大小为 ， `20px` `25px` 和 `30px` `40px` 。</span><span class="sxs-lookup"><span data-stu-id="47e26-118">The preferred sizes for browser action and page action icons are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="47e26-119">其他支持的大小包括 `19px` ， `35px` 和 `38px` 。</span><span class="sxs-lookup"><span data-stu-id="47e26-119">Other supported sizes include `19px`, `35px`, and `38px`.</span></span>  

<span data-ttu-id="47e26-120">以下manifest.js[ 代码][ExtensionsApisupportManifestkeys] 段上的说明显示了使用代码段键指定的标准和 [browser_action浏览器操作][MDNManifestjsonBrowserAction] 图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-120">The following [manifest.json][ExtensionsApisupportManifestkeys] file snippet shows a standard and high definition browser action icon being specified using the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="47e26-121">相同的语法适用于[page_action键。][MDNManifestjsonPageAction]</span><span class="sxs-lookup"><span data-stu-id="47e26-121">The same syntax applies for the [page_action][MDNManifestjsonPageAction] key.</span></span>  

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

<span data-ttu-id="47e26-122">如果浏览器操作已由扩展设置，则它在选择"更多 (...) " 后显示在"操作"菜单中，或者显示在地址栏旁的"显示"按钮已由用户打开 的情况下显示在地址栏的右侧。</span><span class="sxs-lookup"><span data-stu-id="47e26-122">If the browser action has been set by the extension, it appears either in the Actions menu after selecting **More(...)**,  or to the right of the address bar if **Show button next to the address bar** has been toggled on by the user.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="浏览器操作操作菜单":::
         <span data-ttu-id="47e26-124">浏览器操作操作菜单</span><span class="sxs-lookup"><span data-stu-id="47e26-124">Browser action in action menu</span></span> :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="浏览器操作":::
         <span data-ttu-id="47e26-126">浏览器操作</span><span class="sxs-lookup"><span data-stu-id="47e26-126">Browser action</span></span> :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="47e26-127">页面操作</span><span class="sxs-lookup"><span data-stu-id="47e26-127">Page action</span></span>  

<span data-ttu-id="47e26-128">the [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.</span><span class="sxs-lookup"><span data-stu-id="47e26-128">The [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="47e26-129">页面操作也具有与浏览器操作相同的图标大小要求。</span><span class="sxs-lookup"><span data-stu-id="47e26-129">Page action also has the same icon size requirements as browser action.</span></span>  

<span data-ttu-id="47e26-130">如果在文件上的manifest.js中指定了 [ 页面操作，][ExtensionsApisupportManifestkeys] 则每当使用 [pageAction.show][MDNApiPageactionShow] 方法时，它都会显示在地址栏中。</span><span class="sxs-lookup"><span data-stu-id="47e26-130">If page action is specified in the [manifest.json][ExtensionsApisupportManifestkeys] file, it appears within the address bar whenever the [pageAction.show][MDNApiPageactionShow] method is used.</span></span>  

:::image type="complex" source="../media/pageaction.png" alt-text="页面操作":::
   <span data-ttu-id="47e26-132">页面操作</span><span class="sxs-lookup"><span data-stu-id="47e26-132">Page action</span></span>
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### <span data-ttu-id="47e26-133">管理 UI</span><span class="sxs-lookup"><span data-stu-id="47e26-133">Management UI</span></span>  

<span data-ttu-id="47e26-134">当用户通过转到"更多扩展 (...) 菜单并选择"扩展"导航到扩展窗格时，将在扩展名旁边显示 一个图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-134">When users navigate to the extensions pane by going to the **More(...)** menu and selecting **Extensions**, an icon is displayed next to the name of the extension.</span></span>  

<span data-ttu-id="47e26-135">应指定以下图标大小。</span><span class="sxs-lookup"><span data-stu-id="47e26-135">You should specify the following icon sizes.</span></span>  

| <span data-ttu-id="47e26-136">密钥</span><span class="sxs-lookup"><span data-stu-id="47e26-136">Key</span></span> | <span data-ttu-id="47e26-137">详细信息</span><span class="sxs-lookup"><span data-stu-id="47e26-137">Details</span></span> |  
|:--- |:--- |  
| `48px` | <span data-ttu-id="47e26-138">显示标准分辨率的图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-138">Icon for standard resolution displays.</span></span> |  
| `128px` | <span data-ttu-id="47e26-139">高分辨率显示的图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-139">Icon for high resolution displays.</span></span> |  
| `176px` | <span data-ttu-id="47e26-140">显示更高分辨率的图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-140">Icon for even higher resolution displays.</span></span> |  


```json
"icons": {
    "48": "images/icon_48.png",
    "128": "images/icon_128.png",
    "176": "images/icon_176.png"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="管理 UI":::
   <span data-ttu-id="47e26-142">管理 UI</span><span class="sxs-lookup"><span data-stu-id="47e26-142">Management UI</span></span>
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### <span data-ttu-id="47e26-143">打包图标</span><span class="sxs-lookup"><span data-stu-id="47e26-143">Icons for packaging</span></span>  

<span data-ttu-id="47e26-144">扩展准备好打包后，必须准备好其他三个图标大小。</span><span class="sxs-lookup"><span data-stu-id="47e26-144">Once your extension is ready for packaging, you must have three additional icon sizes ready.</span></span>  

| <span data-ttu-id="47e26-145">大小</span><span class="sxs-lookup"><span data-stu-id="47e26-145">Size</span></span> | <span data-ttu-id="47e26-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="47e26-146">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="47e26-147">44px</span><span class="sxs-lookup"><span data-stu-id="47e26-147">44px</span></span> | <span data-ttu-id="47e26-148">在 Windows UI \(**应用列表中使用**，**设置**  \>  **系统**应用  \>  **&功能**\) 。</span><span class="sxs-lookup"><span data-stu-id="47e26-148">Used in the Windows UI \(**App List**, **Settings** \> **System** \> **Apps & features**\).</span></span> |  
| <span data-ttu-id="47e26-149">50px</span><span class="sxs-lookup"><span data-stu-id="47e26-149">50px</span></span> | <span data-ttu-id="47e26-150">打包要求 \(在任意位置\) 。</span><span class="sxs-lookup"><span data-stu-id="47e26-150">Packaging requirement \(not visible anywhere\).</span></span> |  
| <span data-ttu-id="47e26-151">150px</span><span class="sxs-lookup"><span data-stu-id="47e26-151">150px</span></span> | <span data-ttu-id="47e26-152">用作 Microsoft Store 的图标。</span><span class="sxs-lookup"><span data-stu-id="47e26-152">Used as the icon for the Microsoft Store.</span></span> |  


<span data-ttu-id="47e26-153">请参阅手动 [打包指南或][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] [ManifoldJS 打包指南][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] ，以确定这些图标的放置位置。</span><span class="sxs-lookup"><span data-stu-id="47e26-153">See either the [manual packaging guide][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] or the [ManifoldJS packaging guide][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] to determine where these icons is placed.</span></span>  <span data-ttu-id="47e26-154">这取决于你选择的打包方法。</span><span class="sxs-lookup"><span data-stu-id="47e26-154">This depends upon which packaging method you choose.</span></span>  

#### <span data-ttu-id="47e26-155">Microsoft Store 图标</span><span class="sxs-lookup"><span data-stu-id="47e26-155">Microsoft Store icon</span></span>  

<span data-ttu-id="47e26-156">如果 Microsoft Store 的 150px 图标具有透明背景，则用户设备的背景色将显示为图标的背景色。</span><span class="sxs-lookup"><span data-stu-id="47e26-156">If the 150px icon for the Microsoft Store has a transparent background, the accent color of the user's device appears as the background color of the icon.</span></span>  

<span data-ttu-id="47e26-157">例如，如果用户已选择粉色作为主题色，则应用商店图标的透明背景显示为粉色。</span><span class="sxs-lookup"><span data-stu-id="47e26-157">For example, if a user has selected pink as the accent color, the transparent background of your store icon is displayed as pink.</span></span>  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Windows 主题色":::
          <span data-ttu-id="47e26-159">Windows 主题色</span><span class="sxs-lookup"><span data-stu-id="47e26-159">Windows accent color</span></span> :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="背景色自动选中":::
         <span data-ttu-id="47e26-161">背景色自动选中</span><span class="sxs-lookup"><span data-stu-id="47e26-161">Background color auto selected</span></span> :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

<span data-ttu-id="47e26-162">如果你想要为 Microsoft Store 选取自己的背景色，则必须使背景不透明。</span><span class="sxs-lookup"><span data-stu-id="47e26-162">If you want to pick your own background color for your Microsoft Store, you must make the background opaque.</span></span>  

> [!NOTE]
> <span data-ttu-id="47e26-163">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。</span><span class="sxs-lookup"><span data-stu-id="47e26-163">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="47e26-164">[请通过][AkaExtensionRequest] Microsoft Store 请求联系我们，你的请求将考虑用于将来的更新。</span><span class="sxs-lookup"><span data-stu-id="47e26-164">[Contact us][AkaExtensionRequest] with your requests for the Microsoft Store, and your request is considered for a future update.</span></span>  

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
