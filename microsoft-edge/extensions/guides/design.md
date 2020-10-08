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
# <span data-ttu-id="3f140-104">Microsoft Edge 扩展的设计指南</span><span class="sxs-lookup"><span data-stu-id="3f140-104">Design Guidelines For Microsoft Edge Extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="3f140-105">以下页面包含创建 Microsoft Edge 扩展时要考虑的各种设计方面和 UI 行为。</span><span class="sxs-lookup"><span data-stu-id="3f140-105">The following page contains various design aspects and UI behavior to consider when creating Microsoft Edge extensions.</span></span>  

## <span data-ttu-id="3f140-106">图标</span><span class="sxs-lookup"><span data-stu-id="3f140-106">Icons</span></span>  

<span data-ttu-id="3f140-107">你应该使用矢量图形制作扩展的图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-107">You should make the icons of your extension using a vector graphic.</span></span>  <span data-ttu-id="3f140-108">你必须为你的扩展名创建几个不同大小的图标，如果要打包你的扩展，还必须创建三个附加大小。</span><span class="sxs-lookup"><span data-stu-id="3f140-108">You must create a few different sizes of your icon for your extension, and three additional sizes if you want to package your extension.</span></span>  <span data-ttu-id="3f140-109">Microsoft Edge 扩展不支持 svg 图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-109">Microsoft Edge extensions do not support .svg icons.</span></span>  

<span data-ttu-id="3f140-110">创建扩展图标之前，应查看 [辅助功能][ExtensionsGuidesAccessibility] 指南，以确保你的图标具有足够高的对比度，并且在 Microsoft Edge 的浅色和深色主题中可见。</span><span class="sxs-lookup"><span data-stu-id="3f140-110">Before you create your extension icons, you should review the [accessibility][ExtensionsGuidesAccessibility] guide to ensure that your icons have high enough contrast and are visible in both the light and dark themes of Microsoft Edge.</span></span>  

<span data-ttu-id="3f140-111">尽管支持任何 webkit 图像格式，但建议使用 png 图标进行透明支持。</span><span class="sxs-lookup"><span data-stu-id="3f140-111">While any webkit image format is supported, .png icons are recommended for transparency support.</span></span>  

### <span data-ttu-id="3f140-112">用于您的扩展的图标</span><span class="sxs-lookup"><span data-stu-id="3f140-112">Icons for your extension</span></span>  

<span data-ttu-id="3f140-113">对于你的扩展，你必须为浏览器操作或页面操作创建一个图标大小，然后为 " **扩展** " 窗格创建一个图标大小。</span><span class="sxs-lookup"><span data-stu-id="3f140-113">For your extension, you must create one icon size for the browser action or page action, and one icon size for the **Extensions** pane.</span></span>  <span data-ttu-id="3f140-114">可能会提供每个大小的多个大小以支持高分辨率显示。</span><span class="sxs-lookup"><span data-stu-id="3f140-114">More than one size for each may be provided to support high resolution displays.</span></span>  

<span data-ttu-id="3f140-115">扩展应具有浏览器操作或页面操作图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-115">An extension should have a browser action or page action icon.</span></span>  <span data-ttu-id="3f140-116">浏览器操作和页面操作图标可能会在运行时使用 [browserAction][MSDApiBrowseractionSeticon] 方法或 [pageAction][MDNApiPageactionSeticon] 方法进行更改。</span><span class="sxs-lookup"><span data-stu-id="3f140-116">The browser action and page action icons may be changed at runtime using the [browserAction.setIcon][MSDApiBrowseractionSeticon] method or [pageAction.setIcon][MDNApiPageactionSeticon] method.</span></span>  

#### <span data-ttu-id="3f140-117">浏览器操作</span><span class="sxs-lookup"><span data-stu-id="3f140-117">Browser action</span></span>  

<span data-ttu-id="3f140-118">浏览器操作和页面操作图标的首选大小为 `20px` 、 `25px` 、 `30px` 和 `40px` 。</span><span class="sxs-lookup"><span data-stu-id="3f140-118">The preferred sizes for browser action and page action icons are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="3f140-119">其他受支持的大小包括 `19px` 、 `35px` 和 `38px` 。</span><span class="sxs-lookup"><span data-stu-id="3f140-119">Other supported sizes include `19px`, `35px`, and `38px`.</span></span>  

<span data-ttu-id="3f140-120">文件代码段上的以下 [manifest.js][ExtensionsApisupportManifestkeys] 显示使用 [browser_action][MDNManifestjsonBrowserAction] 键指定的标准和高定义浏览器操作图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-120">The following [manifest.json][ExtensionsApisupportManifestkeys] file snippet shows a standard and high definition browser action icon being specified using the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="3f140-121">相同语法适用于 [page_action][MDNManifestjsonPageAction] 键。</span><span class="sxs-lookup"><span data-stu-id="3f140-121">The same syntax applies for the [page_action][MDNManifestjsonPageAction] key.</span></span>  

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

<span data-ttu-id="3f140-122">如果浏览器操作已由扩展设置，则在选择 " \*\*更多 ( ..." ) \*\*或 "地址栏" 旁边的 " **显示" 按钮** 时，它将显示在 "操作" 菜单中，如果用户已切换。</span><span class="sxs-lookup"><span data-stu-id="3f140-122">If the browser action has been set by the extension, it appears either in the Actions menu after selecting **More(...)**,  or to the right of the address bar if **Show button next to the address bar** has been toggled on by the user.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/actionmenu-browseraction.png" alt-text="操作菜单中的浏览器操作":::
         <span data-ttu-id="3f140-124">操作菜单中的浏览器操作</span><span class="sxs-lookup"><span data-stu-id="3f140-124">Browser action in action menu</span></span> :::image-end:::
      
      <!--![browser action in action menu][ImageActionmenuBrowseraction]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/browseractionicon.png" alt-text="操作菜单中的浏览器操作":::
         <span data-ttu-id="3f140-126">浏览器操作</span><span class="sxs-lookup"><span data-stu-id="3f140-126">Browser action</span></span> :::image-end:::
      
      <!--![browser action][ImageBrowserActionIcon]  -->  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="3f140-127">页面操作</span><span class="sxs-lookup"><span data-stu-id="3f140-127">Page action</span></span>  

<span data-ttu-id="3f140-128">[Page_action][MDNManifestjsonPageAction]键具有与[browser_action][MDNManifestjsonBrowserAction]键相同的 JSON 清单语法。</span><span class="sxs-lookup"><span data-stu-id="3f140-128">The [page_action][MDNManifestjsonPageAction] key has the same JSON manifest syntax as the [browser_action][MDNManifestjsonBrowserAction] key.</span></span>  <span data-ttu-id="3f140-129">页面操作还具有与浏览器操作相同的图标大小要求。</span><span class="sxs-lookup"><span data-stu-id="3f140-129">Page action also has the same icon size requirements as browser action.</span></span>  

<span data-ttu-id="3f140-130">如果在 [manifest.json file 上][ExtensionsApisupportManifestkeys] 指定了 page 操作，则只要使用 [pageAction][MDNApiPageactionShow] 方法，它就会出现在地址栏中。</span><span class="sxs-lookup"><span data-stu-id="3f140-130">If page action is specified in the [manifest.json][ExtensionsApisupportManifestkeys] file, it appears within the address bar whenever the [pageAction.show][MDNApiPageactionShow] method is used.</span></span>  

:::image type="complex" source="../media/pageaction.png" alt-text="操作菜单中的浏览器操作":::
   <span data-ttu-id="3f140-132">页面操作</span><span class="sxs-lookup"><span data-stu-id="3f140-132">Page action</span></span>
:::image-end:::

<!--![page action][ImagePageaction]  -->  

##### <span data-ttu-id="3f140-133">管理 UI</span><span class="sxs-lookup"><span data-stu-id="3f140-133">Management UI</span></span>  

<span data-ttu-id="3f140-134">当用户转到 "扩展" 窗格，通过转到 " \*\*更多 ( ..." ) \*\* 菜单并选择 " **扩展**" 时，将在扩展名的名称旁边显示一个图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-134">When users navigate to the extensions pane by going to the **More(...)** menu and selecting **Extensions**, an icon is displayed next to the name of the extension.</span></span>  

<span data-ttu-id="3f140-135">应指定以下图标大小。</span><span class="sxs-lookup"><span data-stu-id="3f140-135">You should specify the following icon sizes.</span></span>  

| <span data-ttu-id="3f140-136">密钥</span><span class="sxs-lookup"><span data-stu-id="3f140-136">Key</span></span> | <span data-ttu-id="3f140-137">详细信息</span><span class="sxs-lookup"><span data-stu-id="3f140-137">Details</span></span> |  
|:--- |:--- |  
| `48px` | <span data-ttu-id="3f140-138">显示标准分辨率的图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-138">Icon for standard resolution displays.</span></span> |  
| `128px` | <span data-ttu-id="3f140-139">显示高分辨率的图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-139">Icon for high resolution displays.</span></span> |  
| `176px` | <span data-ttu-id="3f140-140">显示更高分辨率的图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-140">Icon for even higher resolution displays.</span></span> |  


```json
"icons": {
    "48": "images/icon_48.png",
    "128": "images/icon_128.png",
    "176": "images/icon_176.png"
},
```  

:::image type="complex" source="../media/management-ui.png" alt-text="操作菜单中的浏览器操作":::
   <span data-ttu-id="3f140-142">管理 UI</span><span class="sxs-lookup"><span data-stu-id="3f140-142">Management UI</span></span>
:::image-end:::

<!--![management UI][ImageManagementUi]  -->  

### <span data-ttu-id="3f140-143">用于打包的图标</span><span class="sxs-lookup"><span data-stu-id="3f140-143">Icons for packaging</span></span>  

<span data-ttu-id="3f140-144">延长分机准备就绪后，您必须有三个其他图标大小准备就绪。</span><span class="sxs-lookup"><span data-stu-id="3f140-144">Once your extension is ready for packaging, you must have three additional icon sizes ready.</span></span>  

| <span data-ttu-id="3f140-145">大小</span><span class="sxs-lookup"><span data-stu-id="3f140-145">Size</span></span> | <span data-ttu-id="3f140-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="3f140-146">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="3f140-147">44px</span><span class="sxs-lookup"><span data-stu-id="3f140-147">44px</span></span> | <span data-ttu-id="3f140-148">在 Windows UI \ (**应用列表**中使用，**设置**  \>  **系统**  \>  **应用 & 功能**\ ) 。</span><span class="sxs-lookup"><span data-stu-id="3f140-148">Used in the Windows UI \(**App List**, **Settings** \> **System** \> **Apps & features**\).</span></span> |  
| <span data-ttu-id="3f140-149">50像素</span><span class="sxs-lookup"><span data-stu-id="3f140-149">50px</span></span> | <span data-ttu-id="3f140-150">打包要求 \ (在任何位置均不可见 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="3f140-150">Packaging requirement \(not visible anywhere\).</span></span> |  
| <span data-ttu-id="3f140-151">150px</span><span class="sxs-lookup"><span data-stu-id="3f140-151">150px</span></span> | <span data-ttu-id="3f140-152">用作 Microsoft Store 的图标。</span><span class="sxs-lookup"><span data-stu-id="3f140-152">Used as the icon for the Microsoft Store.</span></span> |  


<span data-ttu-id="3f140-153">请参阅 [手动打包指南][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] 或 [ManifoldJS 打包指南][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] 以确定这些图标放置的位置。</span><span class="sxs-lookup"><span data-stu-id="3f140-153">See either the [manual packaging guide][ExtensionsGuidesPackagingCreatingTestingPackagesAssetsFolder] or the [ManifoldJS packaging guide][ExtensionsGuidesPackagingUsingManifoldjsPackagePackagingManifoldjs] to determine where these icons is placed.</span></span>  <span data-ttu-id="3f140-154">这取决于你选择的打包方法。</span><span class="sxs-lookup"><span data-stu-id="3f140-154">This depends upon which packaging method you choose.</span></span>  

#### <span data-ttu-id="3f140-155">Microsoft Store 图标</span><span class="sxs-lookup"><span data-stu-id="3f140-155">Microsoft Store icon</span></span>  

<span data-ttu-id="3f140-156">如果 Microsoft Store 的150px 图标具有透明背景，则用户设备的主题颜色将显示为图标的背景色。</span><span class="sxs-lookup"><span data-stu-id="3f140-156">If the 150px icon for the Microsoft Store has a transparent background, the accent color of the user's device appears as the background color of the icon.</span></span>  

<span data-ttu-id="3f140-157">例如，如果用户选中 "粉色" 作为主题色，则 "应用商店" 图标的透明背景将显示为粉红色。</span><span class="sxs-lookup"><span data-stu-id="3f140-157">For example, if a user has selected pink as the accent color, the transparent background of your store icon is displayed as pink.</span></span>  

:::row:::
   :::column span="1":::
       :::image type="complex" source="../media/windows-accent-color.png" alt-text="操作菜单中的浏览器操作":::
          <span data-ttu-id="3f140-159">Windows 主题色</span><span class="sxs-lookup"><span data-stu-id="3f140-159">Windows accent color</span></span> :::image-end:::
       
       <!--![Windows accent color][ImageWindowsAccentColor]  -->  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/store-icon-with-transparent-background.png" alt-text="操作菜单中的浏览器操作":::
         <span data-ttu-id="3f140-161">自动选择的背景色</span><span class="sxs-lookup"><span data-stu-id="3f140-161">Background color auto selected</span></span> :::image-end:::
      
      <!--![Background color auto selected][ImageStoreIconTransparencyBackground]  -->  
   :::column-end:::
:::row-end:::

<span data-ttu-id="3f140-162">如果你想要为 Microsoft Store 选择自己的背景色，则必须将背景设置为不透明。</span><span class="sxs-lookup"><span data-stu-id="3f140-162">If you want to pick your own background color for your Microsoft Store, you must make the background opaque.</span></span>  

> [!NOTE]
> <span data-ttu-id="3f140-163">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。</span><span class="sxs-lookup"><span data-stu-id="3f140-163">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="3f140-164">使用 Microsoft Store 的请求[与我们联系][AkaExtensionRequest]，你的请求将被视为将来的更新。</span><span class="sxs-lookup"><span data-stu-id="3f140-164">[Contact us][AkaExtensionRequest] with your requests for the Microsoft Store, and your request is considered for a future update.</span></span>  

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

[MSDApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction setIcon ( # A1-API |MDN"  
[MDNApiPageactionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/setIcon "pageAction setIcon ( # A1-API |MDN"  
[MDNApiPageactionShow]: https://developer.mozilla.org/Add-ons/WebExtensions/API/pageAction/show "pageAction。 show ( # A1-API |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action "browser_action-manifest.json |MDN"  
[MDNManifestjsonPageAction]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action "page_action-manifest.json |MDN"  
