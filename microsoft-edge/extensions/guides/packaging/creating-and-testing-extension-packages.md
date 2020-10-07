---
ms.assetid: 5eefa3d8-8626-4486-bd90-1361400d6468
description: Learn about how to package up your Microsoft Edge extension manually and test it to see if it's packaged correctly.
title: Creating and testing extension packages
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer, packaging
ms.custom: seodec18
ms.openlocfilehash: a76737d76c8f08c8e79992f0804fdbd34d4ed970
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563249"
---
# <span data-ttu-id="bc5b6-104">Creating and testing a Microsoft Edge extension AppX package</span><span class="sxs-lookup"><span data-stu-id="bc5b6-104">Creating and testing a Microsoft Edge extension AppX package</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="bc5b6-105">Microsoft Edge extensions are packaged as AppX, similar to how Universal Windows Apps are packaged.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-105">Microsoft Edge extensions are packaged as AppX, similar to how Universal Windows Apps are packaged.</span></span> <span data-ttu-id="bc5b6-106">As of Windows 10 Anniversary Update, a new schema has been introduced for AppX that allows an AppX to include a Microsoft Edge extension as its content.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-106">As of Windows 10 Anniversary Update, a new schema has been introduced for AppX that allows an AppX to include a Microsoft Edge extension as its content.</span></span>

<span data-ttu-id="bc5b6-107">If you already know how Microsoft Edge extension AppXs are created, you can skip to [Using ManifoldJS to package extension](./using-manifoldjs-to-package-extensions.md) to learn how to use a Node.js based tool to do all of this for you!</span><span class="sxs-lookup"><span data-stu-id="bc5b6-107">If you already know how Microsoft Edge extension AppXs are created, you can skip to [Using ManifoldJS to package extension](./using-manifoldjs-to-package-extensions.md) to learn how to use a Node.js based tool to do all of this for you!</span></span>

> [!NOTE]
> <span data-ttu-id="bc5b6-108">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-108">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="bc5b6-109">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span><span class="sxs-lookup"><span data-stu-id="bc5b6-109">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>



## <span data-ttu-id="bc5b6-110">Preparing the submission folder</span><span class="sxs-lookup"><span data-stu-id="bc5b6-110">Preparing the submission folder</span></span>

<span data-ttu-id="bc5b6-111">To prepare your extension for submission, you need to create a folder with the following structure:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-111">To prepare your extension for submission, you need to create a folder with the following structure:</span></span>

![image of folder structure.](./../../media/packaging_folder-structure.png)

<span data-ttu-id="bc5b6-114">At the root of the folder, you should include an AppXManifest.xml file.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-114">At the root of the folder, you should include an AppXManifest.xml file.</span></span> <span data-ttu-id="bc5b6-115">This file is used to specify the contents and layout of the package.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-115">This file is used to specify the contents and layout of the package.</span></span>

<span data-ttu-id="bc5b6-116">You should also have an Assets folder which contains the UI assets to be used in the Microsoft Store, and an Extension folder that contains your extension's files (scripts, icons, etc).</span><span class="sxs-lookup"><span data-stu-id="bc5b6-116">You should also have an Assets folder which contains the UI assets to be used in the Microsoft Store, and an Extension folder that contains your extension's files (scripts, icons, etc).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc5b6-117">You can create a different folder structure for your package, but the folder structure must match the AppXManifest values.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-117">You can create a different folder structure for your package, but the folder structure must match the AppXManifest values.</span></span>

### <span data-ttu-id="bc5b6-118">AppXManifest.xml</span><span class="sxs-lookup"><span data-stu-id="bc5b6-118">AppXManifest.xml</span></span>
<span data-ttu-id="bc5b6-119">The AppXManifest file is an XML document that contains info the system needs to deploy, display, or update a Windows app.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-119">The AppXManifest file is an XML document that contains info the system needs to deploy, display, or update a Windows app.</span></span> <span data-ttu-id="bc5b6-120">This file also includes package identity, capabilities, and visual elements.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-120">This file also includes package identity, capabilities, and visual elements.</span></span> <span data-ttu-id="bc5b6-121">Every app package must include one AppXManifest file.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-121">Every app package must include one AppXManifest file.</span></span>

<span data-ttu-id="bc5b6-122">Developers can use the following template for their AppXManifest.xml file:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-122">Developers can use the following template for their AppXManifest.xml file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
  xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
  xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
  xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
  IgnorableNamespaces="uap3">

  <Identity
    Name="[REPLACE WITH PACKAGE/IDENTITYNAME]"
    Publisher="[REPLACE WITH PACKAGE/IDENTITY/PUBLISHER]"
    Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]"/>

  <Properties>
    <DisplayName>[REPLACE WITH RESERVED STORE NAME]</DisplayName>
    <PublisherDisplayName>[REPLACE WITH PACKAGE/PROPERTIES/PUBLISHERDISPLAYNAME]</PublisherDisplayName>
    <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
  </Properties>

  <Dependencies>
    <TargetDeviceFamily Name="Windows.Desktop"
      MinVersion="10.0.14393.0"
      MaxVersionTested="10.0.14800.0" />
  </Dependencies>

  <Resources>
    <Resource Language="en-us"/>
  </Resources>

  <Applications>
    <Application Id="App">
      <uap:VisualElements
        AppListEntry="none"
        DisplayName="[REPLACE WITH RESERVED STORE NAME]"
        Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
        Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
        Description="This is the description of the extension"
        BackgroundColor="white">
      </uap:VisualElements>
    <Extensions>
    <uap3:Extension Category="windows.appExtension">
    <uap3:AppExtension Name="com.microsoft.edge.extension"
        Id="EdgeExtension"
        PublicFolder="Extension"
      DisplayName="[REPLACE WITH RESERVED STORE NAME]">
    </uap3:AppExtension>
    </uap3:Extension>
    </Extensions>
 </Application>
</Applications>
</Package>
```

#### <span data-ttu-id="bc5b6-123">App identity template values</span><span class="sxs-lookup"><span data-stu-id="bc5b6-123">App identity template values</span></span>
<span data-ttu-id="bc5b6-124">Once you've [reserved the name of your extension](./extensions-in-the-windows-dev-center.md#name-reservation) through the Windows Dev Center, you'll be able to find the necessary package identity information needed to replace the following values in AppXManifest.xml:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-124">Once you've [reserved the name of your extension](./extensions-in-the-windows-dev-center.md#name-reservation) through the Windows Dev Center, you'll be able to find the necessary package identity information needed to replace the following values in AppXManifest.xml:</span></span>

- `Name`
- `Publisher`
- `DisplayName`
- `PublisherDisplayName`

<span data-ttu-id="bc5b6-125">You can access your App identity page using the following steps:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-125">You can access your App identity page using the following steps:</span></span>

1. <span data-ttu-id="bc5b6-126">Navigate to [Windows Dev Center](https://developer.microsoft.com/windows/).</span><span class="sxs-lookup"><span data-stu-id="bc5b6-126">Navigate to [Windows Dev Center](https://developer.microsoft.com/windows/).</span></span>
2. <span data-ttu-id="bc5b6-127">Sign in to your developer account.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-127">Sign in to your developer account.</span></span>
3. <span data-ttu-id="bc5b6-128">Navigate to the Dashboard.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-128">Navigate to the Dashboard.</span></span>
4. <span data-ttu-id="bc5b6-129">Select the name of your extension.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-129">Select the name of your extension.</span></span>

   ![extension list](./../../media/select-app.png)
5. <span data-ttu-id="bc5b6-131">Navigate to the App identity page which is under the App management section (after you've registered your app).</span><span class="sxs-lookup"><span data-stu-id="bc5b6-131">Navigate to the App identity page which is under the App management section (after you've registered your app).</span></span>

   ![app identity page](./../../media/app-identity.png)


<span data-ttu-id="bc5b6-133">You can now populate the AppXManifest template with values from the App identity page, as indicated in the template:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-133">You can now populate the AppXManifest template with values from the App identity page, as indicated in the template:</span></span>


```xml
<Identity
  Name="37369abigailc.MyExtension"
  Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
  Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]" />

<Properties>
  <DisplayName>My Extension</DisplayName>
  <PublisherDisplayName>abigailc</PublisherDisplayName>
  <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
</Properties>
```

#### <span data-ttu-id="bc5b6-134">JSON manifest template values</span><span class="sxs-lookup"><span data-stu-id="bc5b6-134">JSON manifest template values</span></span>
<span data-ttu-id="bc5b6-135">Some values in the AppXManifest need to match those that are defined in the JSON manifest.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-135">Some values in the AppXManifest need to match those that are defined in the JSON manifest.</span></span> <span data-ttu-id="bc5b6-136">Please update the following values in appxmanifest.xml based on your extension JSON manifest:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-136">Please update the following values in appxmanifest.xml based on your extension JSON manifest:</span></span>

- `Version` <span data-ttu-id="bc5b6-137">- This is the version listed in your extension's JSON manifest.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-137">- This is the version listed in your extension's JSON manifest.</span></span> <span data-ttu-id="bc5b6-138">The string needs to match the X.X.X.X format where the last integer has to be 0.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-138">The string needs to match the X.X.X.X format where the last integer has to be 0.</span></span> <span data-ttu-id="bc5b6-139">E.g.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-139">E.g.</span></span> <span data-ttu-id="bc5b6-140">1.2.3.0</span><span class="sxs-lookup"><span data-stu-id="bc5b6-140">1.2.3.0</span></span>

   ```xml
   <Identity
     Name="37369abigailc.MyExtension"
     Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
     Version="1.0.0.0" />
   ```

- `Description` <span data-ttu-id="bc5b6-141">- This is a copy of the description in your extension's JSON manifest.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-141">- This is a copy of the description in your extension's JSON manifest.</span></span>

  ```xml
  <uap:VisualElements
    AppListEntry="none"
    DisplayName="My Extension"
    Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
    Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
    Description="This extension will allow you to quickly print by clicking the browser action."
    BackgroundColor="white">
  </uap:VisualElements>
  ```


### <span data-ttu-id="bc5b6-142">Assets folder</span><span class="sxs-lookup"><span data-stu-id="bc5b6-142">Assets folder</span></span>

<span data-ttu-id="bc5b6-143">Within the Assets folder you will need three different icon sizes.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-143">Within the Assets folder you will need three different icon sizes.</span></span> <span data-ttu-id="bc5b6-144">These icons will be used in the Microsoft Store and the Windows UI.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-144">These icons will be used in the Microsoft Store and the Windows UI.</span></span> <span data-ttu-id="bc5b6-145">For more information on these icons, see the [Design](./../design.md#icons-for-packaging) guide.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-145">For more information on these icons, see the [Design](./../design.md#icons-for-packaging) guide.</span></span>

![assets folder with three icon sizes in it](./../../media/assets-folder.png)

<span data-ttu-id="bc5b6-147">Once you've created the necessary UI assets, update AppXManifest.xml to point to the correct files:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-147">Once you've created the necessary UI assets, update AppXManifest.xml to point to the correct files:</span></span>

- <span data-ttu-id="bc5b6-148">44x44</span><span class="sxs-lookup"><span data-stu-id="bc5b6-148">44x44</span></span>

   ```xml
   Square44x44Logo="Assets/icon_44.png"
   ```

- <span data-ttu-id="bc5b6-149">50x50</span><span class="sxs-lookup"><span data-stu-id="bc5b6-149">50x50</span></span>

  ```xml
   <Logo>Assets/icon_50.png</Logo>
  ```

- <span data-ttu-id="bc5b6-150">150x150</span><span class="sxs-lookup"><span data-stu-id="bc5b6-150">150x150</span></span>

  ```xml
  Square150x150Logo="Assets/icon_150.png"
  ```


### <span data-ttu-id="bc5b6-151">Extension folder</span><span class="sxs-lookup"><span data-stu-id="bc5b6-151">Extension folder</span></span>
<span data-ttu-id="bc5b6-152">Copy your extension files (keeping the folder structure) into the Extension folder.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-152">Copy your extension files (keeping the folder structure) into the Extension folder.</span></span> <span data-ttu-id="bc5b6-153">Make sure `manifest.json` is at the root your Extension folder.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-153">Make sure `manifest.json` is at the root your Extension folder.</span></span>

![extension folder with all extension files in it](./../../media/extension-folder.png)


### <span data-ttu-id="bc5b6-155">Supporting more than one locale</span><span class="sxs-lookup"><span data-stu-id="bc5b6-155">Supporting more than one locale</span></span>
<span data-ttu-id="bc5b6-156">If your extension supports more than one language, you may want to configure the AppX package with all the locales that you need so that the correct localized icon and description appear in the Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-156">If your extension supports more than one language, you may want to configure the AppX package with all the locales that you need so that the correct localized icon and description appear in the Microsoft Store.</span></span> <span data-ttu-id="bc5b6-157">See [Localizing extension packages](./localizing-extension-packages.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-157">See [Localizing extension packages](./localizing-extension-packages.md) for more information.</span></span>

### <span data-ttu-id="bc5b6-158">Creating an Appx</span><span class="sxs-lookup"><span data-stu-id="bc5b6-158">Creating an Appx</span></span>

<span data-ttu-id="bc5b6-159">To create an Appx, you'll need to find the path for makeappx.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-159">To create an Appx, you'll need to find the path for makeappx.</span></span> <span data-ttu-id="bc5b6-160">This is usually located in the following location if you're on a 64-bit machine.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-160">This is usually located in the following location if you're on a 64-bit machine.</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64`

<span data-ttu-id="bc5b6-161">Execute the following command to create the AppX package for your extension:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-161">Execute the following command to create the AppX package for your extension:</span></span>

`[Path to makeappx] makeappx pack /h SHA256 /d [Path to package folder created in #1] /p [Path to the appx file that you want to create]`

<span data-ttu-id="bc5b6-162">This should look something like this once you've filled in the paths:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-162">This should look something like this once you've filled in the paths:</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe pack /h SHA256 /d "C:\Extension\My Extension" /p C:\Extension\MyExtension.appx`

### <span data-ttu-id="bc5b6-163">Unpacking an Appx</span><span class="sxs-lookup"><span data-stu-id="bc5b6-163">Unpacking an Appx</span></span>
<span data-ttu-id="bc5b6-164">You may want to unpack a previously generated AppX and use it as a starting point for the next iteration of your extension or to confirm that the AppX was created correctly.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-164">You may want to unpack a previously generated AppX and use it as a starting point for the next iteration of your extension or to confirm that the AppX was created correctly.</span></span>

<span data-ttu-id="bc5b6-165">To do this, you can execute the following command to unpack the AppX package of your Microsoft Edge extension:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-165">To do this, you can execute the following command to unpack the AppX package of your Microsoft Edge extension:</span></span>

`[Path to makeappx] makeappx unpack /v /p [Path to appx file you want to unpack] /d [Path to the location where you want to create the package folder]`

<span data-ttu-id="bc5b6-166">This should look something like this when filled out:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-166">This should look something like this when filled out:</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe unpack /v /p "C:\Extension\MyExtension.appx" /d "C:\Extension\My Extension"`





## <span data-ttu-id="bc5b6-167">Testing an AppX package</span><span class="sxs-lookup"><span data-stu-id="bc5b6-167">Testing an AppX package</span></span>

<span data-ttu-id="bc5b6-168">You can test your Microsoft Edge extension AppX package by sideloading it in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-168">You can test your Microsoft Edge extension AppX package by sideloading it in Microsoft Edge.</span></span> <span data-ttu-id="bc5b6-169">Sideloading the extension AppX package is similar to sideloading a Universal Windows app.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-169">Sideloading the extension AppX package is similar to sideloading a Universal Windows app.</span></span> <span data-ttu-id="bc5b6-170">You will need to create a certificate for signing the package, and then add the package to Windows.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-170">You will need to create a certificate for signing the package, and then add the package to Windows.</span></span>

### <span data-ttu-id="bc5b6-171">Signing</span><span class="sxs-lookup"><span data-stu-id="bc5b6-171">Signing</span></span>

<span data-ttu-id="bc5b6-172">See [How to create an app package signing certificate](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) and [How to sign an app package using SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) for info on the signing and certification process for packages.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-172">See [How to create an app package signing certificate](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) and [How to sign an app package using SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) for info on the signing and certification process for packages.</span></span>

> [!NOTE]
> <span data-ttu-id="bc5b6-173">You do not need to sign an extension package before submitting it to the Microsoft Store; the Store ingestion process will take care of that for you!</span><span class="sxs-lookup"><span data-stu-id="bc5b6-173">You do not need to sign an extension package before submitting it to the Microsoft Store; the Store ingestion process will take care of that for you!</span></span>

<span data-ttu-id="bc5b6-174">After you've signed the package with the certificate that you created, the certificate is still not trusted by the local machine for deployment of app packages until you install it into the trusted certificates store of the local computer.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-174">After you've signed the package with the certificate that you created, the certificate is still not trusted by the local machine for deployment of app packages until you install it into the trusted certificates store of the local computer.</span></span> <span data-ttu-id="bc5b6-175">You can use Certutil.exe, which comes with Windows to do this.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-175">You can use Certutil.exe, which comes with Windows to do this.</span></span>

<span data-ttu-id="bc5b6-176">To install certificates with WindowsCertutil.exe, run Cmd.exe as administrator and run the following command:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-176">To install certificates with WindowsCertutil.exe, run Cmd.exe as administrator and run the following command:</span></span>

`Certutil -addStore TrustedPeople MyKey.cer`

<span data-ttu-id="bc5b6-177">Once the certificates are no longer in use, it is recommended that you remove them by running the following command from an administrator command prompt:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-177">Once the certificates are no longer in use, it is recommended that you remove them by running the following command from an administrator command prompt:</span></span>

`Certutil -delStore TrustedPeople certID`

<span data-ttu-id="bc5b6-178">The certID is the serial number of the certificate.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-178">The certID is the serial number of the certificate.</span></span> <span data-ttu-id="bc5b6-179">To determine the certificate serial number, run the following command:</span><span class="sxs-lookup"><span data-stu-id="bc5b6-179">To determine the certificate serial number, run the following command:</span></span>

`Certutil -store TrustedPeople`

### <span data-ttu-id="bc5b6-180">Deploying</span><span class="sxs-lookup"><span data-stu-id="bc5b6-180">Deploying</span></span>
<span data-ttu-id="bc5b6-181">You can deploy the Microsoft Edge Extension AppX package by running the following command in PowerShell (as administrator):</span><span class="sxs-lookup"><span data-stu-id="bc5b6-181">You can deploy the Microsoft Edge Extension AppX package by running the following command in PowerShell (as administrator):</span></span>

`Add-AppxPackage [path to AppX]`

## <span data-ttu-id="bc5b6-182">Automated testing with WebDriver</span><span class="sxs-lookup"><span data-stu-id="bc5b6-182">Automated testing with WebDriver</span></span>

<span data-ttu-id="bc5b6-183">As of the Anniversary Update, you can programmatically sideload your extension in Microsoft Edge with WebDriver, enabling automated testing of extensions when Microsoft Edge is launched in WebDriver mode.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-183">As of the Anniversary Update, you can programmatically sideload your extension in Microsoft Edge with WebDriver, enabling automated testing of extensions when Microsoft Edge is launched in WebDriver mode.</span></span> <span data-ttu-id="bc5b6-184">This will allow you to set up automated tests for any extension that manipulates content on a page and verify that the correct behavior is exhibited.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-184">This will allow you to set up automated tests for any extension that manipulates content on a page and verify that the correct behavior is exhibited.</span></span>

<span data-ttu-id="bc5b6-185">To sideload your extension for automated testing, you'll need to store your extension's folder under `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\`.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-185">To sideload your extension for automated testing, you'll need to store your extension's folder under `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\`.</span></span> <span data-ttu-id="bc5b6-186">Once your extension is in the `LocalState` directory, you'll need to create an [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) object, and add the `extensionPaths` capability to it.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-186">Once your extension is in the `LocalState` directory, you'll need to create an [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) object, and add the `extensionPaths` capability to it.</span></span> <span data-ttu-id="bc5b6-187">The value of this capability is an array of absolute paths to the extensions (in the `LocalState` directory) you wish to have side loaded when Microsoft Edge starts in WebDriver mode.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-187">The value of this capability is an array of absolute paths to the extensions (in the `LocalState` directory) you wish to have side loaded when Microsoft Edge starts in WebDriver mode.</span></span>

<span data-ttu-id="bc5b6-188">Check out the following [C# file](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) for a complete sample on side loading extensions in Microsoft Edge with WebDriver.</span><span class="sxs-lookup"><span data-stu-id="bc5b6-188">Check out the following [C# file](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) for a complete sample on side loading extensions in Microsoft Edge with WebDriver.</span></span>
