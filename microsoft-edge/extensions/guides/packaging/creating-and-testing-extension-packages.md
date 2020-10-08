---
ms.assetid: 5eefa3d8-8626-4486-bd90-1361400d6468
description: 了解如何手动打包 Microsoft Edge 扩展，并对其进行测试以查看是否已正确打包。
title: 创建和测试扩展包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员、打包
ms.custom: seodec18
ms.openlocfilehash: a76737d76c8f08c8e79992f0804fdbd34d4ed970
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563249"
---
# 创建和测试 Microsoft Edge 扩展 AppX 程序包  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

Microsoft Edge 扩展打包为 AppX，与通用 Windows 应用的打包方式类似。 从 Windows 10 周年更新起，已为 AppX 引入了新架构，允许 AppX 将 Microsoft Edge 扩展包含为其内容。

如果你已知道 Microsoft Edge 扩展 AppXs 是如何创建的，则可以跳过 [使用 ManifoldJS 打包扩展](./using-manifoldjs-to-package-extensions.md) ，了解如何使用基于 Node.js 的工具来为你执行所有这些操作！

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。 创建、打包和测试扩展后，请提交我们的 [扩展提交表单](https://aka.ms/extension-request)上的申请。



## 准备提交文件夹

若要准备要提交的扩展，需要创建具有以下结构的文件夹：

![文件夹结构的图像。 在 "我的扩展文件夹" 中 AppxManifest.xml、"扩展文件夹" 和 "资源" 文件夹](./../../media/packaging_folder-structure.png)

在文件夹的根位置，应包含 AppXManifest.xml 文件。 此文件用于指定程序包的内容和布局。

你还应具有一个资源文件夹，其中包含要在 Microsoft Store 中使用的 UI 资源，以及包含你的扩展名的文件 (脚本、图标等) 的扩展文件夹。

> [!IMPORTANT]
> 你可以为程序包创建不同的文件夹结构，但文件夹结构必须匹配 Package.appxmanifest 值。

### AppXManifest.xml
Package.appxmanifest 文件是一个 XML 文档，其中包含系统部署、显示或更新 Windows 应用所需的信息。 此文件还包括程序包标识、功能和视觉元素。 每个应用包都必须包含一个 Package.appxmanifest 文件。

开发人员可以对其 AppXManifest.xml 文件使用以下模板：

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

#### 应用标识模板值
通过 Windows 开发人员中心 [保留扩展的名称](./extensions-in-the-windows-dev-center.md#name-reservation) 后，你将能够在 AppXManifest.xml 中查找替换以下值所需的必要的程序包标识信息：

- `Name`
- `Publisher`
- `DisplayName`
- `PublisherDisplayName`

你可以使用以下步骤访问应用标识页面：

1. 导航到 [Windows 开发人员中心](https://developer.microsoft.com/windows/)。
2. 登录到你的开发者帐户。
3. 导航到仪表板。
4. 选择您的扩展名的名称。

   ![扩展名列表](./../../media/select-app.png)
5. 导航到 "应用程序标识" 页面，该页面位于 "应用管理" 部分下 (在) 注册应用之后。

   ![应用标识页面](./../../media/app-identity.png)


现在，你可以按照模板中的指示，用应用标识页面中的值填充 Package.appxmanifest 模板：


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

#### JSON 清单模板值
Package.appxmanifest 中的某些值需要与在 JSON 清单中定义的值相匹配。 请根据扩展 JSON 清单更新 appxmanifest.xml 中的以下值：

- `Version` -这是你的扩展的 JSON 清单中列出的版本。 该字符串需要匹配最后一个整数必须为0的 X.x.x.x 格式。 例如 1.2.3.0

   ```xml
   <Identity
     Name="37369abigailc.MyExtension"
     Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
     Version="1.0.0.0" />
   ```

- `Description` -这是扩展的 JSON 清单中说明的副本。

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


### 资源文件夹

在 "资源" 文件夹中，你将需要三个不同的图标大小。 这些图标将在 Microsoft Store 和 Windows UI 中使用。 有关这些图标的详细信息，请参阅 [设计](./../design.md#icons-for-packaging) 指南。

![其中有三个图标大小的 "资源" 文件夹](./../../media/assets-folder.png)

创建必要的 UI 资源后，更新 AppXManifest.xml 以指向正确的文件：

- 44x44

   ```xml
   Square44x44Logo="Assets/icon_44.png"
   ```

- 50x50

  ```xml
   <Logo>Assets/icon_50.png</Logo>
  ```

- 150x150

  ```xml
  Square150x150Logo="Assets/icon_150.png"
  ```


### 扩展文件夹
将扩展文件复制 (将文件夹结构) 保存到扩展文件夹中。 请确保 `manifest.json` 您的扩展文件夹位于根位置。

![包含所有扩展名文件的扩展文件夹](./../../media/extension-folder.png)


### 支持多个区域设置
如果你的扩展支持多种语言，你可能希望配置包含你所需的所有区域设置的 AppX 程序包，以便正确本地化的图标和说明显示在 Microsoft Store 中。 有关详细信息，请参阅 [本地化扩展包](./localizing-extension-packages.md) 。

### 创建 Appx

若要创建 Appx，你需要查找 makeappx 的路径。 如果您使用的是64位计算机，则通常位于以下位置。

`C:\Program Files (x86)\Windows Kits\10\bin\x64`

执行以下命令以创建适用于您的扩展的 AppX 程序包：

`[Path to makeappx] makeappx pack /h SHA256 /d [Path to package folder created in #1] /p [Path to the appx file that you want to create]`

在你填写完路径后，此操作应如下所示：

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe pack /h SHA256 /d "C:\Extension\My Extension" /p C:\Extension\MyExtension.appx`

### 解包 Appx
你可能需要解压缩以前生成的 AppX，并将其用作你的扩展的下一个迭代的起始点，或确认是否正确创建了 AppX。

若要执行此操作，你可以执行以下命令来解压缩 Microsoft Edge 扩展的 AppX 程序包：

`[Path to makeappx] makeappx unpack /v /p [Path to appx file you want to unpack] /d [Path to the location where you want to create the package folder]`

填写以下内容时，此内容应如下所示：

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe unpack /v /p "C:\Extension\MyExtension.appx" /d "C:\Extension\My Extension"`





## 测试 AppX 程序包

你可以通过在 Microsoft Edge 中旁加载来测试你的 Microsoft Edge 扩展 AppX 程序包。 旁加载扩展 AppX 程序包类似于将通用 Windows 应用旁加载。 你将需要创建用于对程序包进行签名的证书，然后将程序包添加到 Windows。

### 签发

了解 [如何创建应用包签名证书](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) 以及 [如何使用 SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) 对程序包的签名和认证过程的相关信息进行签名。

> [!NOTE]
> 您无需在将扩展程序包提交到 Microsoft Store 之前对其进行签名;应用商店接收过程将负责处理你的工作！

使用你创建的证书对程序包进行签名后，在将其安装到本地计算机的 "受信任的证书" 存储中之前，该证书仍不受本地计算机用于部署应用程序包的信任。 你可以使用 Certutil.exe，Windows 提供此功能。

若要通过 WindowsCertutil.exe 安装证书，请以管理员身份运行 Cmd.exe，然后运行以下命令：

`Certutil -addStore TrustedPeople MyKey.cer`

不再使用证书后，建议通过从管理员命令提示符运行以下命令来删除它们：

`Certutil -delStore TrustedPeople certID`

CertID 是证书的序列号。 若要确定证书序列号，请运行以下命令：

`Certutil -store TrustedPeople`

### 部署
你可以通过在 PowerShell (中运行以下命令来部署 Microsoft Edge 扩展 AppX 程序包：管理员) ：

`Add-AppxPackage [path to AppX]`

## 通过 WebDriver 进行自动化测试

在 "周年纪念更新" 中，你可以通过 WebDriver 在 Microsoft Edge 中以编程方式旁加载你的扩展，从而在 WebDriver 模式下启动 Microsoft Edge 时启用自动测试扩展。 这将允许你为处理页面上的内容的任何扩展设置自动测试，并验证是否表现出了正确的行为。

若要旁加载您的扩展以进行自动测试，您需要将您的扩展文件夹存储在 "下" `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\` 。 扩展位于目录中后 `LocalState` ，你将需要创建一个 [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) 对象，并向 `extensionPaths` 其添加功能。 此功能的值是在 `LocalState` WebDriver 模式下启动 Microsoft Edge 时你希望已加载的目录) 中的 (扩展的绝对路径的数组。

有关 WebDriver 的 Microsoft Edge 中的端加载扩展的完整示例，请查看以下 [c # 文件](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) 。
