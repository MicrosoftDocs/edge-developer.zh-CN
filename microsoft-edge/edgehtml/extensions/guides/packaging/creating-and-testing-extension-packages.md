---
ms.assetid: 5eefa3d8-8626-4486-bd90-1361400d6468
description: 了解如何手动打包 Microsoft Edge 扩展并测试它以查看其打包是否正确。
title: 创建和测试扩展包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 打包
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 44316f4dd47b3b6b26014ff24673ddfd16a72ddb
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232608"
---
# <span data-ttu-id="1fff8-104">创建和测试 Microsoft Edge 扩展 AppX 程序包</span><span class="sxs-lookup"><span data-stu-id="1fff8-104">Creating and testing a Microsoft Edge extension AppX package</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="1fff8-105">Microsoft Edge 扩展打包为 AppX，类似于打包通用 Windows 应用的方式。</span><span class="sxs-lookup"><span data-stu-id="1fff8-105">Microsoft Edge extensions are packaged as AppX, similar to how Universal Windows Apps are packaged.</span></span> <span data-ttu-id="1fff8-106">自 Windows 10 周年更新起，AppX 引入了一个新架构，允许 AppX 将 Microsoft Edge 扩展作为其内容。</span><span class="sxs-lookup"><span data-stu-id="1fff8-106">As of Windows 10 Anniversary Update, a new schema has been introduced for AppX that allows an AppX to include a Microsoft Edge extension as its content.</span></span>

<span data-ttu-id="1fff8-107">如果你已了解如何创建 Microsoft Edge 扩展 AppX，可以跳到使用 [ManifoldJS](./using-manifoldjs-to-package-extensions.md) 打包扩展，以了解如何使用基于 Node.js 的工具执行所有这些操作！</span><span class="sxs-lookup"><span data-stu-id="1fff8-107">If you already know how Microsoft Edge extension AppXs are created, you can skip to [Using ManifoldJS to package extension](./using-manifoldjs-to-package-extensions.md) to learn how to use a Node.js based tool to do all of this for you!</span></span>

> [!NOTE]
> <span data-ttu-id="1fff8-108">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。</span><span class="sxs-lookup"><span data-stu-id="1fff8-108">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="1fff8-109">创建、打包和测试扩展后，请在扩展提交表单上 [提交请求](https://aka.ms/extension-request)。</span><span class="sxs-lookup"><span data-stu-id="1fff8-109">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>

## <span data-ttu-id="1fff8-110">准备提交文件夹</span><span class="sxs-lookup"><span data-stu-id="1fff8-110">Preparing the submission folder</span></span>

<span data-ttu-id="1fff8-111">若要准备你的扩展以提交，你需要创建具有以下结构的文件夹：</span><span class="sxs-lookup"><span data-stu-id="1fff8-111">To prepare your extension for submission, you need to create a folder with the following structure:</span></span>

![文件夹结构的图像。](./../../media/packaging_folder-structure.png)

<span data-ttu-id="1fff8-114">在文件夹的根目录下，应包含AppXManifest.xml文件。</span><span class="sxs-lookup"><span data-stu-id="1fff8-114">At the root of the folder, you should include an AppXManifest.xml file.</span></span> <span data-ttu-id="1fff8-115">此文件用于指定包的内容和布局。</span><span class="sxs-lookup"><span data-stu-id="1fff8-115">This file is used to specify the contents and layout of the package.</span></span>

<span data-ttu-id="1fff8-116">你还应该有一个 Assets 文件夹，其中包含在 Microsoft Store 中使用的 UI 资产，以及一个扩展文件夹，其中包含扩展名的文件 (脚本、图标等) 。</span><span class="sxs-lookup"><span data-stu-id="1fff8-116">You should also have an Assets folder which contains the UI assets to be used in the Microsoft Store, and an Extension folder that contains your extension's files (scripts, icons, etc).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fff8-117">你可以为程序包创建不同的文件夹结构，但文件夹结构必须与 AppXManifest 值匹配。</span><span class="sxs-lookup"><span data-stu-id="1fff8-117">You can create a different folder structure for your package, but the folder structure must match the AppXManifest values.</span></span>

### <span data-ttu-id="1fff8-118">AppXManifest.xml</span><span class="sxs-lookup"><span data-stu-id="1fff8-118">AppXManifest.xml</span></span>
<span data-ttu-id="1fff8-119">AppXManifest 文件是一个 XML 文档，其中包含系统部署、显示或更新 Windows 应用时需要的信息。</span><span class="sxs-lookup"><span data-stu-id="1fff8-119">The AppXManifest file is an XML document that contains info the system needs to deploy, display, or update a Windows app.</span></span> <span data-ttu-id="1fff8-120">此文件还包括程序包标识、功能和视觉元素。</span><span class="sxs-lookup"><span data-stu-id="1fff8-120">This file also includes package identity, capabilities, and visual elements.</span></span> <span data-ttu-id="1fff8-121">每个应用包必须包含一个 AppXManifest 文件。</span><span class="sxs-lookup"><span data-stu-id="1fff8-121">Every app package must include one AppXManifest file.</span></span>

<span data-ttu-id="1fff8-122">开发人员可以将以下模板用于其AppXManifest.xml文件：</span><span class="sxs-lookup"><span data-stu-id="1fff8-122">Developers can use the following template for their AppXManifest.xml file:</span></span>

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

#### <span data-ttu-id="1fff8-123">应用标识模板值</span><span class="sxs-lookup"><span data-stu-id="1fff8-123">App identity template values</span></span>
<span data-ttu-id="1fff8-124">通过 Windows [开发人员中心](./extensions-in-the-windows-dev-center.md#name-reservation) 保留扩展名称后，你将能够查找替换 windows 开发人员中心中的以下值所需的程序包标识AppXManifest.xml：</span><span class="sxs-lookup"><span data-stu-id="1fff8-124">Once you've [reserved the name of your extension](./extensions-in-the-windows-dev-center.md#name-reservation) through the Windows Dev Center, you'll be able to find the necessary package identity information needed to replace the following values in AppXManifest.xml:</span></span>

-   `Name`
-   `Publisher`
-   `DisplayName`
-   `PublisherDisplayName`

<span data-ttu-id="1fff8-125">可以使用以下步骤访问应用标识页：</span><span class="sxs-lookup"><span data-stu-id="1fff8-125">You can access your App identity page using the following steps:</span></span>

1.  <span data-ttu-id="1fff8-126">导航到 [Windows 开发人员中心](https://developer.microsoft.com/windows/)。</span><span class="sxs-lookup"><span data-stu-id="1fff8-126">Navigate to [Windows Dev Center](https://developer.microsoft.com/windows/).</span></span>
2.  <span data-ttu-id="1fff8-127">登录到你的开发人员帐户。</span><span class="sxs-lookup"><span data-stu-id="1fff8-127">Sign in to your developer account.</span></span>
3.  <span data-ttu-id="1fff8-128">导航到仪表板。</span><span class="sxs-lookup"><span data-stu-id="1fff8-128">Navigate to the Dashboard.</span></span>
4.  <span data-ttu-id="1fff8-129">选择扩展的名称。</span><span class="sxs-lookup"><span data-stu-id="1fff8-129">Select the name of your extension.</span></span>
    
    ![扩展列表](./../../media/select-app.png)
    
5.  <span data-ttu-id="1fff8-131">注册应用后，导航到"应用管理"部分 (下的应用标识) 。</span><span class="sxs-lookup"><span data-stu-id="1fff8-131">Navigate to the App identity page which is under the App management section (after you've registered your app).</span></span>
    
    ![应用标识页](./../../media/app-identity.png)
    
<span data-ttu-id="1fff8-133">现在，可以使用"应用标识"页中的值填充 AppXManifest 模板，如模板中指示：</span><span class="sxs-lookup"><span data-stu-id="1fff8-133">You can now populate the AppXManifest template with values from the App identity page, as indicated in the template:</span></span>

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

#### <span data-ttu-id="1fff8-134">JSON 清单模板值</span><span class="sxs-lookup"><span data-stu-id="1fff8-134">JSON manifest template values</span></span>
<span data-ttu-id="1fff8-135">AppXManifest 中的某些值需要匹配 JSON 清单中定义的那些值。</span><span class="sxs-lookup"><span data-stu-id="1fff8-135">Some values in the AppXManifest need to match those that are defined in the JSON manifest.</span></span> <span data-ttu-id="1fff8-136">Please update the following values in appxmanifest.xml based on your extension JSON manifest：</span><span class="sxs-lookup"><span data-stu-id="1fff8-136">Please update the following values in appxmanifest.xml based on your extension JSON manifest:</span></span>

-   `Version` <span data-ttu-id="1fff8-137">- 这是扩展的 JSON 清单中列出的版本。</span><span class="sxs-lookup"><span data-stu-id="1fff8-137">- This is the version listed in your extension's JSON manifest.</span></span> <span data-ttu-id="1fff8-138">字符串需要匹配 X.X.X.X 格式，其中最后一个整数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="1fff8-138">The string needs to match the X.X.X.X format where the last integer has to be 0.</span></span> <span data-ttu-id="1fff8-139">例如</span><span class="sxs-lookup"><span data-stu-id="1fff8-139">E.g.</span></span> <span data-ttu-id="1fff8-140">1.2.3.0</span><span class="sxs-lookup"><span data-stu-id="1fff8-140">1.2.3.0</span></span>
    
    ```xml
    <Identity
         Name="37369abigailc.MyExtension"
         Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
         Version="1.0.0.0" />
    ```  
    
-   `Description` <span data-ttu-id="1fff8-141">- 这是扩展的 JSON 清单中的说明副本。</span><span class="sxs-lookup"><span data-stu-id="1fff8-141">- This is a copy of the description in your extension's JSON manifest.</span></span>
    
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
    
### <span data-ttu-id="1fff8-142">资源文件夹</span><span class="sxs-lookup"><span data-stu-id="1fff8-142">Assets folder</span></span>

<span data-ttu-id="1fff8-143">在"资产"文件夹中，你需要三种不同的图标大小。</span><span class="sxs-lookup"><span data-stu-id="1fff8-143">Within the Assets folder you will need three different icon sizes.</span></span> <span data-ttu-id="1fff8-144">这些图标将在 Microsoft Store 和 Windows UI 中使用。</span><span class="sxs-lookup"><span data-stu-id="1fff8-144">These icons will be used in the Microsoft Store and the Windows UI.</span></span> <span data-ttu-id="1fff8-145">有关这些图标详细信息， [请参阅设计指南](./../design.md#icons-for-packaging) 。</span><span class="sxs-lookup"><span data-stu-id="1fff8-145">For more information on these icons, see the [Design](./../design.md#icons-for-packaging) guide.</span></span>

![包含三个图标大小的 assets 文件夹](./../../media/assets-folder.png)

<span data-ttu-id="1fff8-147">创建必要的 UI 资源后，更新AppXManifest.xml以指向正确的文件：</span><span class="sxs-lookup"><span data-stu-id="1fff8-147">Once you've created the necessary UI assets, update AppXManifest.xml to point to the correct files:</span></span>

-   <span data-ttu-id="1fff8-148">44x44</span><span class="sxs-lookup"><span data-stu-id="1fff8-148">44x44</span></span>
    
    ```xml
    Square44x44Logo="Assets/icon_44.png"
    ```  
    
-   <span data-ttu-id="1fff8-149">50x50</span><span class="sxs-lookup"><span data-stu-id="1fff8-149">50x50</span></span>
    
    ```xml
    <Logo>Assets/icon_50.png</Logo>
    ```  
    
-   <span data-ttu-id="1fff8-150">150x150</span><span class="sxs-lookup"><span data-stu-id="1fff8-150">150x150</span></span>
    
    ```xml
    Square150x150Logo="Assets/icon_150.png"
    ```  
    
### <span data-ttu-id="1fff8-151">扩展文件夹</span><span class="sxs-lookup"><span data-stu-id="1fff8-151">Extension folder</span></span>
<span data-ttu-id="1fff8-152">复制扩展文件 (将文件夹结构) 扩展文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fff8-152">Copy your extension files (keeping the folder structure) into the Extension folder.</span></span> <span data-ttu-id="1fff8-153">请确保 `manifest.json` 在扩展文件夹的根目录下。</span><span class="sxs-lookup"><span data-stu-id="1fff8-153">Make sure `manifest.json` is at the root your Extension folder.</span></span>

![包含所有扩展文件的扩展文件夹](./../../media/extension-folder.png)

### <span data-ttu-id="1fff8-155">支持多个区域设置</span><span class="sxs-lookup"><span data-stu-id="1fff8-155">Supporting more than one locale</span></span>
<span data-ttu-id="1fff8-156">如果你的扩展支持多种语言，你可能想要使用所需的所有区域设置配置 AppX 程序包，以便正确的本地化图标和说明显示在 Microsoft Store 中。</span><span class="sxs-lookup"><span data-stu-id="1fff8-156">If your extension supports more than one language, you may want to configure the AppX package with all the locales that you need so that the correct localized icon and description appear in the Microsoft Store.</span></span> <span data-ttu-id="1fff8-157">有关详细信息 [，请参阅本地化](./localizing-extension-packages.md) 扩展包。</span><span class="sxs-lookup"><span data-stu-id="1fff8-157">See [Localizing extension packages](./localizing-extension-packages.md) for more information.</span></span>

### <span data-ttu-id="1fff8-158">创建 Appx</span><span class="sxs-lookup"><span data-stu-id="1fff8-158">Creating an Appx</span></span>

<span data-ttu-id="1fff8-159">若要创建 Appx，你需要查找 makeappx 的路径。</span><span class="sxs-lookup"><span data-stu-id="1fff8-159">To create an Appx, you'll need to find the path for makeappx.</span></span> <span data-ttu-id="1fff8-160">如果位于 64 位计算机上，则通常位于以下位置。</span><span class="sxs-lookup"><span data-stu-id="1fff8-160">This is usually located in the following location if you're on a 64-bit machine.</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64`

<span data-ttu-id="1fff8-161">执行以下命令，为扩展创建 AppX 包：</span><span class="sxs-lookup"><span data-stu-id="1fff8-161">Execute the following command to create the AppX package for your extension:</span></span>

`[Path to makeappx] makeappx pack /h SHA256 /d [Path to package folder created in #1] /p [Path to the appx file that you want to create]`

<span data-ttu-id="1fff8-162">填充路径后，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fff8-162">This should look something like this once you've filled in the paths:</span></span>

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe pack /h SHA256 /d "C:\Extension\My Extension" /p C:\Extension\MyExtension.appx`

### <span data-ttu-id="1fff8-163">解压缩 Appx</span><span class="sxs-lookup"><span data-stu-id="1fff8-163">Unpacking an Appx</span></span>
<span data-ttu-id="1fff8-164">你可能想要解压缩以前生成的 AppX，并使用它作为下一次扩展迭代的起点，或者确认 AppX 已正确创建。</span><span class="sxs-lookup"><span data-stu-id="1fff8-164">You may want to unpack a previously generated AppX and use it as a starting point for the next iteration of your extension or to confirm that the AppX was created correctly.</span></span>

<span data-ttu-id="1fff8-165">为此，可以执行以下命令解压缩 Microsoft Edge 扩展的 AppX 程序包：</span><span class="sxs-lookup"><span data-stu-id="1fff8-165">To do this, you can execute the following command to unpack the AppX package of your Microsoft Edge extension:</span></span>

```shell
[Path to makeappx] makeappx unpack /v /p [Path to appx file you want to unpack] /d [Path to the location where you want to create the package folder]
```  

<span data-ttu-id="1fff8-166">填写后应如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fff8-166">This should look something like this when filled out:</span></span>

```text
C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe unpack /v /p "C:\Extension\MyExtension.appx" /d "C:\Extension\My Extension"
```  

## <span data-ttu-id="1fff8-167">测试 AppX 程序包</span><span class="sxs-lookup"><span data-stu-id="1fff8-167">Testing an AppX package</span></span>

<span data-ttu-id="1fff8-168">可以通过在 Microsoft Edge 中旁加载 Microsoft Edge 扩展 AppX 程序包来测试它。</span><span class="sxs-lookup"><span data-stu-id="1fff8-168">You can test your Microsoft Edge extension AppX package by sideloading it in Microsoft Edge.</span></span> <span data-ttu-id="1fff8-169">旁加载扩展 AppX 程序包类似于旁加载通用 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="1fff8-169">Sideloading the extension AppX package is similar to sideloading a Universal Windows app.</span></span> <span data-ttu-id="1fff8-170">你需要创建用于对程序包进行签名的证书，然后将程序包添加到 Windows。</span><span class="sxs-lookup"><span data-stu-id="1fff8-170">You will need to create a certificate for signing the package, and then add the package to Windows.</span></span>

### <span data-ttu-id="1fff8-171">签名</span><span class="sxs-lookup"><span data-stu-id="1fff8-171">Signing</span></span>

<span data-ttu-id="1fff8-172">请参阅 [如何创建应用包签名证书](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) 以及如何使用 [SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) 对应用包进行签名，获取有关程序包的签名和认证过程的信息。</span><span class="sxs-lookup"><span data-stu-id="1fff8-172">See [How to create an app package signing certificate](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) and [How to sign an app package using SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) for info on the signing and certification process for packages.</span></span>

> [!NOTE]
> <span data-ttu-id="1fff8-173">在将扩展包提交到 Microsoft Store 之前，无需对它进行签名;应用商店的提供过程将负责你！</span><span class="sxs-lookup"><span data-stu-id="1fff8-173">You do not need to sign an extension package before submitting it to the Microsoft Store; the Store ingestion process will take care of that for you!</span></span>

<span data-ttu-id="1fff8-174">使用创建的证书对程序包进行签名后，本地计算机仍不信任该证书来部署应用包，除非将其安装到本地计算机的受信任证书存储中。</span><span class="sxs-lookup"><span data-stu-id="1fff8-174">After you've signed the package with the certificate that you created, the certificate is still not trusted by the local machine for deployment of app packages until you install it into the trusted certificates store of the local computer.</span></span> <span data-ttu-id="1fff8-175">可以使用 Windows Certutil.exe来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1fff8-175">You can use Certutil.exe, which comes with Windows to do this.</span></span>

<span data-ttu-id="1fff8-176">若要使用 WindowsCertutil.exe 安装证书，Cmd.exe管理员运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1fff8-176">To install certificates with WindowsCertutil.exe, run Cmd.exe as administrator and run the following command:</span></span>

```shell
Certutil -addStore TrustedPeople MyKey.cer
```  

<span data-ttu-id="1fff8-177">一旦证书不再使用，建议通过从管理员命令提示符运行以下命令将其删除：</span><span class="sxs-lookup"><span data-stu-id="1fff8-177">Once the certificates are no longer in use, it is recommended that you remove them by running the following command from an administrator command prompt:</span></span>

```shell
Certutil -delStore TrustedPeople certID
```  

<span data-ttu-id="1fff8-178">certID 是证书的序列号。</span><span class="sxs-lookup"><span data-stu-id="1fff8-178">The certID is the serial number of the certificate.</span></span> <span data-ttu-id="1fff8-179">若要确定证书序列号，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1fff8-179">To determine the certificate serial number, run the following command:</span></span>

```shell
Certutil -store TrustedPeople
```  

### <span data-ttu-id="1fff8-180">部署</span><span class="sxs-lookup"><span data-stu-id="1fff8-180">Deploying</span></span>
<span data-ttu-id="1fff8-181">在 PowerShell 中以管理员角色运行以下命令， (Microsoft Edge 扩展 AppX) ：</span><span class="sxs-lookup"><span data-stu-id="1fff8-181">You can deploy the Microsoft Edge Extension AppX package by running the following command in PowerShell (as administrator):</span></span>

```powershell
Add-AppxPackage [path to AppX]
```  

## <span data-ttu-id="1fff8-182">使用 WebDriver 自动测试</span><span class="sxs-lookup"><span data-stu-id="1fff8-182">Automated testing with WebDriver</span></span>

<span data-ttu-id="1fff8-183">自周年更新起，可以使用 WebDriver 以编程方式在 Microsoft Edge 中旁加载扩展，从而在 Microsoft Edge 在 WebDriver 模式下启动时自动测试扩展。</span><span class="sxs-lookup"><span data-stu-id="1fff8-183">As of the Anniversary Update, you can programmatically sideload your extension in Microsoft Edge with WebDriver, enabling automated testing of extensions when Microsoft Edge is launched in WebDriver mode.</span></span> <span data-ttu-id="1fff8-184">这将允许你为处理页面上内容的任何扩展设置自动测试，并验证是否展示了正确的行为。</span><span class="sxs-lookup"><span data-stu-id="1fff8-184">This will allow you to set up automated tests for any extension that manipulates content on a page and verify that the correct behavior is exhibited.</span></span>

<span data-ttu-id="1fff8-185">若要旁加载扩展以自动测试，你需要将扩展的文件夹存储在 `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\` 下。</span><span class="sxs-lookup"><span data-stu-id="1fff8-185">To sideload your extension for automated testing, you'll need to store your extension's folder under `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\`.</span></span> <span data-ttu-id="1fff8-186">一旦扩展位于目录中，你将需要创建一个对象， `LocalState` [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) 并将其添加到 `extensionPaths` 该对象。</span><span class="sxs-lookup"><span data-stu-id="1fff8-186">Once your extension is in the `LocalState` directory, you'll need to create an [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) object, and add the `extensionPaths` capability to it.</span></span> <span data-ttu-id="1fff8-187">此功能的值是你希望在 Microsoft Edge 以 WebDriver 模式启动时 (的) `LocalState` 的扩展的绝对路径数组。</span><span class="sxs-lookup"><span data-stu-id="1fff8-187">The value of this capability is an array of absolute paths to the extensions (in the `LocalState` directory) you wish to have side loaded when Microsoft Edge starts in WebDriver mode.</span></span>

<span data-ttu-id="1fff8-188">请查看以下 [C#](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) 文件，了解使用 WebDriver 在 Microsoft Edge 中旁加载扩展的完整示例。</span><span class="sxs-lookup"><span data-stu-id="1fff8-188">Check out the following [C# file](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) for a complete sample on side loading extensions in Microsoft Edge with WebDriver.</span></span>
