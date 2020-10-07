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
# <span data-ttu-id="a4bf0-104">Design Guidelines For Microsoft Edge Extensions</span><span class="sxs-lookup"><span data-stu-id="a4bf0-104">Design Guidelines For Microsoft Edge Extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="a4bf0-105">The following page contains various design aspects and UI behavior to consider when creating Microsoft Edge extensions.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-105">The following page contains various design aspects and UI behavior to consider when creating Microsoft Edge extensions.</span></span>  

## <span data-ttu-id="a4bf0-106">Icons</span><span class="sxs-lookup"><span data-stu-id="a4bf0-106">Icons</span></span>  

<span data-ttu-id="a4bf0-107">You should make the icons of your extension using a vector graphic.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-107">You should make the icons of your extension using a vector graphic.</span></span>  <span data-ttu-id="a4bf0-108">You must create a few different sizes of your icon for your extension, and three additional sizes if you want to package your extension.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-108">You must create a few different sizes of your icon for your extension, and three additional sizes if you want to package your extension.</span></span>  <span data-ttu-id="a4bf0-109">Microsoft Edge extensions do not support .svg icons.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-109">Microsoft Edge extensions do not support .svg icons.</span></span>  

<span data-ttu-id="a4bf0-110">Before you create your extension icons, you should review the [accessibility][ExtensionsGuidesAccessibility] guide to ensure that your icons have high enough contrast and are visible in both the light and dark themes of Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-110">Before you create your extension icons, you should review the [accessibility][ExtensionsGuidesAccessibility] guide to ensure that your icons have high enough contrast and are visible in both the light and dark themes of Microsoft Edge.</span></span>  

<span data-ttu-id="a4bf0-111">While any webkit image format is supported, .png icons are recommended for transparency support.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-111">While any webkit image format is supported, .png icons are recommended for transparency support.</span></span>  

### <span data-ttu-id="a4bf0-112">Icons for your extension</span><span class="sxs-lookup"><span data-stu-id="a4bf0-112">Icons for your extension</span></span>  

<span data-ttu-id="a4bf0-113">For your extension, you must create one icon size for the browser action or page action, and one icon size for the **Extensions** pane.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-113">For your extension, you must create one icon size for the browser action or page action, and one icon size for the **Extensions** pane.</span></span>  <span data-ttu-id="a4bf0-114">More than one size for each may be provided to support high resolution displays.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-114">More than one size for each may be provided to support high resolution displays.</span></span>  

<span data-ttu-id="a4bf0-115">An extension should have a browser action or page action icon.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-115">An extension should have a browser action or page action icon.</span></span>  <span data-ttu-id="a4bf0-116">The browser action and page action icons may be changed at runtime using the [browserAction.setIcon][MSDApiBrowseractionSeticon] method or [pageAction.setIcon][MDNApiPageactionSeticon] method.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-116">The browser action and page action icons may be changed at runtime using the [browserAction.setIcon][MSDApiBrowseractionSeticon] method or [pageAction.setIcon][MDNApiPageactionSeticon] method.</span></span>  

#### <span data-ttu-id="a4bf0-117">Browser action</span><span class="sxs-lookup"><span data-stu-id="a4bf0-117">Browser action</span></span>  

<span data-ttu-id="a4bf0-118">The preferred sizes for browser action and page action icons are `20px`, `25px`, `30px`, and `40px`.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-118">The preferred sizes for browser action and page action icons are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="a4bf0-119">Other supported sizes include `19px`, `35px`, and `38px`.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-119">Other supported sizes include `19px`, `35px`, and `38px`.</span></span>  

<span data-ttu-id="a4bf0-120">The following [manifest.json][ExtensionsApisupportManifestkeys] file snippet shows a standard and high definition browser action icon being specified using the [browser_action][MDNManifestjsonBrowserAction] key.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-120">The following [manifest.json][ExtensionsApisupportManifestkeys] file snippet shows a standard and high definition browser action icon being specified using the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="a4bf0-121">The same syntax applies for the [page_action][MDNManifestjsonPageAction] key.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-121">The same syntax applies for the [page_action][MDNManifestjsonPageAction] key.</span></span>  

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

<span data-ttu-id="a4bf0-122">If the browser action has been set by the extension, it appears either in the Actions menu after selecting **More(...)**,  or to the right of the address bar if **Show button next to the address bar** has been toggled on by the user.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-122">If the browser action has been set by the extension, it appears either in the Actions menu after selecting **More(...)**,  or to the right of the address bar if **Show button next to the address bar** has been toggled on by the user.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="Browser action in action menu":::
         <span data-ttu-id="a4bf0-124">Browser action in action menu</span><span class="sxs-lookup"><span data-stu-id="a4bf0-124">Browser action in action menu</span></span> :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="Browser action in action menu":::
         <span data-ttu-id="a4bf0-126">Browser action</span><span class="sxs-lookup"><span data-stu-id="a4bf0-126">Browser action</span></span> :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="a4bf0-127">Page action</span><span class="sxs-lookup"><span data-stu-id="a4bf0-127">Page action</span></span>  

<span data-ttu-id="a4bf0-128">The [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-128">The [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="a4bf0-129">Page action also has the same icon size requirements as browser action.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-129">Page action also has the same icon size requirements as browser action.</span></span>  

<span data-ttu-id="a4bf0-130">If page action is specified in the [manifest.json][ExtensionsApisupportManifestkeys] file, it appears within the address bar whenever the [pageAction.show][MDNApiPageactionShow] method is used.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-130">If page action is specified in the [manifest.json][ExtensionsApisupportManifestkeys] file, it appears within the address bar whenever the [pageAction.show][MDNApiPageactionShow] method is used.</span></span>  

:::image type="complex" source="../media/pageaction.png" alt-text="Browser action in action menu":::
   <span data-ttu-id="a4bf0-132">Page action</span><span class="sxs-lookup"><span data-stu-id="a4bf0-132">Page action</span></span>
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### <span data-ttu-id="a4bf0-133">Management UI</span><span class="sxs-lookup"><span data-stu-id="a4bf0-133">Management UI</span></span>  

<span data-ttu-id="a4bf0-134">When users navigate to the extensions pane by going to the **More(...)** menu and selecting **Extensions**, an icon is displayed next to the name of the extension.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-134">When users navigate to the extensions pane by going to the **More(...)** menu and selecting **Extensions**, an icon is displayed next to the name of the extension.</span></span>  

<span data-ttu-id="a4bf0-135">You should specify the following icon sizes.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-135">You should specify the following icon sizes.</span></span>  

| <span data-ttu-id="a4bf0-136">Key</span><span class="sxs-lookup"><span data-stu-id="a4bf0-136">Key</span></span> | <span data-ttu-id="a4bf0-137">Details</span><span class="sxs-lookup"><span data-stu-id="a4bf0-137">Details</span></span> |  
|:--- |:--- |  
| `48px` | <span data-ttu-id="a4bf0-138">Icon for standard resolution displays.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-138">Icon for standard resolution displays.</span></span> |  
| `128px` | <span data-ttu-id="a4bf0-139">Icon for high resolution displays.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-139">Icon for high resolution displays.</span></span> |  
| `176px` | <span data-ttu-id="a4bf0-140">Icon for even higher resolution displays.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-140">Icon for even higher resolution displays.</span></span> |  


```json
"icons": {
    "48": "images/icon_48.png",
    "128": "images/icon_128.png",
    "176": "images/icon_176.png"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="Browser action in action menu":::
   <span data-ttu-id="a4bf0-142">Management UI</span><span class="sxs-lookup"><span data-stu-id="a4bf0-142">Management UI</span></span>
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### <span data-ttu-id="a4bf0-143">Icons for packaging</span><span class="sxs-lookup"><span data-stu-id="a4bf0-143">Icons for packaging</span></span>  

<span data-ttu-id="a4bf0-144">Once your extension is ready for packaging, you must have three additional icon sizes ready.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-144">Once your extension is ready for packaging, you must have three additional icon sizes ready.</span></span>  

| <span data-ttu-id="a4bf0-145">Size</span><span class="sxs-lookup"><span data-stu-id="a4bf0-145">Size</span></span> | <span data-ttu-id="a4bf0-146">Details</span><span class="sxs-lookup"><span data-stu-id="a4bf0-146">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="a4bf0-147">44px</span><span class="sxs-lookup"><span data-stu-id="a4bf0-147">44px</span></span> | <span data-ttu-id="a4bf0-148">Used in the Windows UI \(**App List**, **Settings** \> **System** \> **Apps & features**\).</span><span class="sxs-lookup"><span data-stu-id="a4bf0-148">Used in the Windows UI \(**App List**, **Settings** \> **System** \> **Apps & features**\).</span></span> |  
| <span data-ttu-id="a4bf0-149">50px</span><span class="sxs-lookup"><span data-stu-id="a4bf0-149">50px</span></span> | <span data-ttu-id="a4bf0-150">Packaging requirement \(not visible anywhere\).</span><span class="sxs-lookup"><span data-stu-id="a4bf0-150">Packaging requirement \(not visible anywhere\).</span></span> |  
| <span data-ttu-id="a4bf0-151">150px</span><span class="sxs-lookup"><span data-stu-id="a4bf0-151">150px</span></span> | <span data-ttu-id="a4bf0-152">Used as the icon for the Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-152">Used as the icon for the Microsoft Store.</span></span> |  


<span data-ttu-id="a4bf0-153">See either the [manual packaging guide][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] or the [ManifoldJS packaging guide][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] to determine where these icons is placed.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-153">See either the [manual packaging guide][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] or the [ManifoldJS packaging guide][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] to determine where these icons is placed.</span></span>  <span data-ttu-id="a4bf0-154">This depends upon which packaging method you choose.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-154">This depends upon which packaging method you choose.</span></span>  

#### <span data-ttu-id="a4bf0-155">Microsoft Store icon</span><span class="sxs-lookup"><span data-stu-id="a4bf0-155">Microsoft Store icon</span></span>  

<span data-ttu-id="a4bf0-156">If the 150px icon for the Microsoft Store has a transparent background, the accent color of the user's device appears as the background color of the icon.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-156">If the 150px icon for the Microsoft Store has a transparent background, the accent color of the user's device appears as the background color of the icon.</span></span>  

<span data-ttu-id="a4bf0-157">For example, if a user has selected pink as the accent color, the transparent background of your store icon is displayed as pink.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-157">For example, if a user has selected pink as the accent color, the transparent background of your store icon is displayed as pink.</span></span>  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="Browser action in action menu":::
          <span data-ttu-id="a4bf0-159">Windows accent color</span><span class="sxs-lookup"><span data-stu-id="a4bf0-159">Windows accent color</span></span> :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="Browser action in action menu":::
         <span data-ttu-id="a4bf0-161">Background color auto selected</span><span class="sxs-lookup"><span data-stu-id="a4bf0-161">Background color auto selected</span></span> :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

<span data-ttu-id="a4bf0-162">If you want to pick your own background color for your Microsoft Store, you must make the background opaque.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-162">If you want to pick your own background color for your Microsoft Store, you must make the background opaque.</span></span>  

> [!NOTE]
> <span data-ttu-id="a4bf0-163">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-163">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="a4bf0-164">[Contact us][AkaExtensionRequest] with your requests for the Microsoft Store, and your request is considered for a future update.</span><span class="sxs-lookup"><span data-stu-id="a4bf0-164">[Contact us][AkaExtensionRequest] with your requests for the Microsoft Store, and your request is considered for a future update.</span></span>  

<!-- image links -->  

<!--[ImageActionmenuBrowseraction]: ../media/actionmenu-browseraction.png "browser action in action menu"  -->  
<!--[ImageBrowserActionIcon]: ../media/browseractionicon.png "browser action"  -->  
<!--[ImagePageaction]: ../media/pageaction.png "page action"  -->  
<!--[ImageManagementUi]: ../media/management-ui.png "management UI"  -->  
<!--[ImageWindowsAccentColor]: ../media/windows-accent-color.png "Windows accent color"  -->  
<!--[ImageStoreIconTransparencyBackground]: ../media/store-icon-with-transparent-background.png "Background color auto selected"  -->  

<!-- links -->  

[ExtensionsGuidesAccessibility]: ./accessibility.md "Accessibility | Microsoft Docs"  
[ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder]: ./packaging/creating-and-testing-extension-packages.md#assets-folder "Assets folder - Creating And Testing A Microsoft Edge Extension AppX Package | Microsoft Docs"  
[ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs]: ./packaging/using-manifoldjs-to-package-extensions.md#packaging-with-manifoldjs "Packaging with ManifoldJS - Using ManifoldJS To Create Extension AppX Packages | Microsoft Docs"  

[ExtensionsApisupportManifestkeys]: ../API-support/supported-manifest-keys.md "Supported Manifest Keys | Microsoft Docs"  

[AkaExtensionRequest]: https://aka.ms/extension-request "Reach out to us"  

[MSDApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction.setIcon() - API | MDN"  
[MDNApiPageactionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/setIcon "pageAction.setIcon() - API | MDN"  
[MDNApiPageactionShow]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/show "pageAction.show() - API | MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action "browser_action - manifest.json | MDN"  
[MDNManifestjsonPageAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action "page_action - manifest.json | MDN"  
